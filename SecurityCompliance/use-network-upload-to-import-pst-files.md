---
title: 使用网络上载将组织 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 面向管理员：了解如何使用网络上载将多个 PST 文件批量导入 Office 365 中的用户邮箱。
ms.openlocfilehash: bd15216df69e003a5aaddb2ec21ede4da5c5c312
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854816"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>使用网络上载将组织 PST 文件导入到 Office 365

> [!NOTE]
> 本文适用于管理员。 你正在尝试将 PST 文件导入到自己的邮箱吗？ 请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
下面是使用网络上载将多个 PST 文件批量导入到 Office 365 邮箱所需的分步说明。 有关使用网络上载将 PST 文件批量导入到 Office 365 邮箱的常见问题，请参阅[使用网络上载导入 PST 文件的常见问题](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)。
  
[步骤 1：复制 SAS URL 并安装 Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[步骤 2：将 PST 文件上载到 Office 365](#step-2-upload-your-pst-files-to-office-365)

[（可选）步骤 3：查看已上载到 Office 365 的 PST 文件的列表](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 4：创建 PST 导入映射文件](#step-4-create-the-pst-import-mapping-file)

[步骤 5：在 Office 365 中创建 PST 导入作业](#step-5-create-a-pst-import-job-in-office-365)

[步骤 6：筛选数据并启动 PST 导入作业](#step-6-filter-data-and-start-the-pst-import-job)

请注意，你只需执行步骤 1 一次，就可以将 PST 文件导入到 Office 365 邮箱。 执行这些步骤后，每当你想要上载和导入一批 PST 文件时，请按照步骤 2 到步骤 6 进行操作。

## <a name="before-you-begin"></a>准备工作
  
- 必须分配有 Exchange Online 中的“邮箱导入导出”角色，才能将 PST 文件导入到 Office 365 邮箱。 默认情况下，不会向 Exchange Online 中任何角色组分配此角色。 您可以向“组织管理”角色组添加“邮箱导入导出”角色。 或者，您可以创建一个新的角色组，分配“邮箱导入导出”角色，然后将自己添加为成员。 有关详细信息，请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。
    
    此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：
    
  - 必须分配有 Exchange Onlin 中的“邮件收件人”角色。 默认情况下，此角色分配给“组织管理和收件人管理”角色组。
    
    或
    
  - 必须是你的 Office365 组织中的全局管理员。
    
  > [!TIP]
    > 请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。 若要获取导入 PST 文件所需的最低级别权限，请将“邮箱导入导出”和“邮件收件人”角色分配给新角色组，然后添加成员。 
  
- 唯一受支持的将 PST 文件导入到 Office 365 的方法是使用 Azure AzCopy 工具，如本主题中所述。 无法使用 Azure 存储资源管理器将 PST 文件直接上载到 Azure 存储区域。
    
- 你需要将要导入到 Office365 中的 PST 文件存储在自己组织中的文件服务器或共享文件夹中。 在步骤 2 中，你将运行 Azure AzCopy 工具，该工具会将存储在此文件服务器或共享文件夹中的 PST 文件上载到 Office 365。
    
- 此过程涉及复制和保存包含访问密钥的 URL 副本。 此信息将在步骤 2 中用于上载 PST 文件，而且如果要查看上载到 Office 365 的 PST 文件列表，还会在步骤 3 中用到。 请务必采取预防措施来保护此 URL，就像保护密码或其他与安全相关的信息一样。 例如，你可以将其保存到受密码保护的 Microsoft Word 文档或加密的 USB 驱动器。 请参阅[更多信息](#more-information)部分，查看此组合 URL 和密钥的示例。 
    
- 你可以将 PST 文件导入 Office 365 中的非活动邮箱。 可通过在 PST 导入映射文件中的 `Mailbox` 参数中指定非活动邮箱的 GUID 来实现此操作。 有关信息，请参阅本主题中“**说明**”选项卡上的步骤 4。 
    
- 在 Exchange 混合部署中，对于主邮箱位于本地的用户，可将 PST 文件导入到基于云的存档邮箱中。 为此，请在 PST 导入映射文件中执行以下操作：
    
  - 在 `Mailbox` 参数中指定用户本地邮箱的电子邮件地址。 
    
  - 在 `IsArchive` 参数中指定 **TRUE** 值。 
    
    请参阅[步骤 4](#step-4-create-the-pst-import-mapping-file) 以了解更多信息。 
    
- 将 PST 文件导入到 Office 365 邮箱后，邮箱的保留挂起设置将无限期打开。 这意味着分配给该邮箱的保留策略将不会得到处理，除非你关闭保留挂起或设置关闭挂起的日期。 我们为什么要这样做？ 如果导入到邮箱的邮件是旧邮件，则可能会被永久删除（清除），因为根据为邮箱配置的保留设置，它们的保留期已过期。 将邮箱置于保留挂起状态将为邮箱所有者提供时间来管理这些新导入的邮件，或为你提供时间来更改邮箱的保留设置。 有关管理保留挂起的建议，请参阅本主题中的“**更多信息**”选项卡。 
    
- 默认情况下，Office 365 邮箱可以接收的最大邮件大小为 35 MB。 这是因为邮箱的 *MaxReceiveSize* 属性的默认值被设置为 35 MB。 但是，Office 365 中最大邮件接收大小的限制为 150 MB。 因此，如果你导入的 PST 文件中包含大于 35 MB 的项目，则 Office 365 导入服务会自动将目标邮箱上的 *MaxReceiveSize* 属性值更改为 150 MB。 这将允许将最大 150 MB 的邮件导入到用户邮箱。 
    
    > [!TIP]
    > 若要确定邮箱的邮件接收大小，可在 Exchange Online PowerShell 中运行此命令：`Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>步骤 1：复制 SAS URL 并安装 Azure AzCopy

第一步是下载并安装 Azure AzCopy 工具，你将在步骤 2 中运行该工具，以将 PST 文件上载到 Office 365。 你还将复制组织的 SAS URL。 此 URL 是组织 Microsoft 云中 Azure 存储位置的网络 URL 与共享访问签名 (SAS) 密钥的组合。 此密钥为你提供将 PST 文件上载到 Azure 存储位置所需的权限。 请务必采取预防措施来保护 SAS URL。 它是你的组织所特有的，并将在步骤 2 中使用。

> [!IMPORTANT]
> 若要使用网络上载方法导入 PST 文件，建议使用可以在以下过程的步骤 6b 中下载的 Azure AzCopy 版本。
  
1. 转到 [https://protection.office.com](https://protection.office.com)，然后使用你 Office365 组织中的管理员帐户的凭据进行登录。 
    
2. 在安全与合规中心的左窗格中，单击“**数据管理**”\>“**导入**”。
    
    > [!NOTE]
    > 你必须分配有相应的权限，才能访问安全与合规中心中的“**导入**”页面。 有关更多详细信息，请参阅**准备工作**部分。 
    
3. 在“**导入**”页面上，单击 ![添加图标](media/ITPro-EAC-AddIcon.gif)“**新建导入作业**”。
    
    系统将显示导入作业向导。
    
4. 为 PST 导入作业键入一个名称，然后单击“**下一步**”。 请使用小写字母、数字、连字符和下划线。 无法在名称中使用大写字母或包含空格。
    
5. 在“**你想要上载或发送数据?**”页面上，单击“**上传你的数据**”，然后单击“**下一步**”。
    
    ![单击“上传你的数据”以创建网络上载导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在“**导入数据**”页面上，执行以下两项操作： 
    
    ![在“导入数据”页面上复制 SAS URL 并下载 Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. 在步骤 2 中，单击“**显示网络上传 SAS URL**”。 系统显示 SAS URL 后，单击“**复制到剪贴板**”，然后将其粘贴并保存到文件中，以便以后可以访问它。
    
    b. 在步骤 3 中，单击“**下载 Azure AzCopy**”以下载并安装 Azure AzCopy 工具。 在弹出的窗口中，单击“**运行**”来安装 AzCopy。 
    
> [!NOTE]
> 可将“**导入数据**”页面保留为打开状态（如果需要再次复制 SAS URL），也可以单击“**取消**”将其关闭。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>步骤 2：将 PST 文件上载到 Office 365

现在你就可以使用 AzCopy 工具将 PST 文件上载到 Office 365。 此工具将其上载并存储在 Microsoft 云中的 Azure 存储位置。 如前所述，将 PST 文件上载到的 Azure 存储位置位于 Office 365 组织所在的区域 Microsoft 数据中心。 若要完成此步骤，PST 文件必须位于你组织中的文件共享或文件服务器中。 这在下面的过程中称为源目录。 每次运行 AzCopy 工具时，都可以指定不同的源目录。 
  
1. 在您的本地计算机上打开命令提示符。
    
2. 转到您在步骤 1 中安装 AzCopy.exe 工具的目录。 如果在默认位置安装该工具，请转到 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. 运行以下命令以将 PST 文件上载到 Office 365。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > 必须在上一个命令中将某个目录指定为源位置；无法指定单个 PST 文件。 系统将上载源目录中的所有 PST 文件。
 
    下表介绍了 AzCopy.exe 参数及其所需的值。 在上一步中获得的信息会用在这些参数的值中。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |指定组织中包含将被上载到 Office 365 的 PST 文件的源目录。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |指定你在步骤 1 中获得的 SAS URL。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> **提示：**（可选）可指定要将 PST 文件上载到的 Azure 存储位置中的子文件夹。 你可以通过在 SAS URL 中添加子文件夹位置（在“ingestiondata”后面）来执行此操作。 第一个示例未指定子文件夹；这意味着 PST 将被上载到 Azure 存储位置的根文件夹（名为 *ingestiondata*）中。 第二个示例会将 PST 文件上载到 Azure 存储位置根文件夹中的一个子文件夹（名为 *PSTFiles*）中。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> 或  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |将详细状态消息输出到日志文件。默认情况下，详细日志文件名为 AzCopyVerbose.log，所在路径为 %LocalAppData%\Microsoft\Azure\AzCopy。如果对此选项指定现有的文件位置，则详细日志将被附加到该文件中。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |此可选开关指定递归模式，这样，AzCopy 工具将复制位于 `/Source:` 参数指定的源目录的子文件夹中的 PST 文件。  <br/> **注意：** 如果包含该开关，子文件夹中的 PST 文件在上载后将在 Azure 存储位置中具有不同的文件路径名。 你必须在步骤 4 中创建的 CSV 文件中指定确切的文件路径名。  <br/> | `/S` <br/> |
    | `/Y` <br/> |此必需开关允许在将 PST 文件上载到 Azure 存储位置时使用只写 SAS 令牌。 在步骤 1 中获得（并在 `/Dest:` 参数中指定）的 SAS URL 是一个只写 SAS URL，这便是必须包含此开关的原因。 请注意，只写 SAS URL 不会阻止你使用 Azure 存储资源管理器查看上载到 Azure 存储位置的 PST 文件的列表。  <br/> | `/Y` <br/> |
   
以下是对每个参数使用实际值的 AzCopy.exe 工具的语法示例：
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

运行该命令后，显示的状态消息会显示对 PST 文件进行上载的进度。最终状态消息显示已成功上载的文件总数。

> [!TIP]
> 在成功运行 AzCopy.exe 命令并验证所有参数都正确后，将命令行语法副本保存到你复制在步骤 1 中获得的信息的相同（安全）文件中。 然后，每次要运行 AzCopy.exe 工具将 PST 文件上载到 Office 365 时，你可以在命令提示符处复制并粘贴此命令。 唯一可能需要你更改的值是 `/Source:` 参数的值。 这具体取决于 PST 文件所在的源目录。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（可选）步骤 3：查看已上载到 Office 365 的 PST 文件的列表

在该可选步骤中，你可以安装并使用 Microsoft Azure 存储资源管理器（这是一个免费的开源工具）查看已上载到 Azure blob 的 PST 文件的列表。 有两个很好的理由来执行此操作：
  
- 验证 PST 文件是否已从你所在组织中的共享文件夹或文件服务器成功上载到 Azure blob。
    
- 验证已上载到 Azure blob 的每个 PST 文件的文件名（和子文件夹路径名，如果包含子文件夹）。 当您在下一步中创建 PST 映射文件时，这确实非常有用，因为您必须为每个 PST 文件指定文件夹路径名和文件名。 验证这些名称可以帮助减少 PST 映射文件中的潜在错误。
    
Microsoft Azure 存储资源管理器处于预览阶段。
  
> [!IMPORTANT]
> 无法使用 Azure 存储资源管理器上载或修改 PST 文件。 唯一受支持的将 PST 文件导入 Office 365 的方法是使用 AzCopy。 此外，无法删除已上载到 Azure blob 的 PST 文件。 如果尝试删除 PST 文件，将看到提示没有所需权限的错误消息。 请注意，所有 PST 文件都会自动从 Azure 存储区域删除。 如果没有正在进行的导入作业，则 **ingestiondata** 容器中的所有 PST 文件都会在创建最新导入作业 30 天后被删除。
  
若要安装 Azure 存储资源管理器并连接到 Azure 存储区域，请执行以下操作：
  
1. 下载并安装 [Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器，右键单击左窗格中的“**存储帐户**”，然后单击“**连接到 Azure 存储**”。
    
    ![右键单击“存储帐户”，然后单击“连接到 Azure 存储”](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 单击“**使用共享访问签名(SAS) URI 或连接字符串**”，然后单击“**下一步**”。
    
4. 单击“**使用 SAS URI**”，将在步骤 1 中获得的 SAS URL 粘贴到 “**URI**”下的框中，然后单击“**下一步**”。
    
5. 在“**连接摘要**”页面上，可以查看连接信息，然后单击“**连接**”。
    
    **ingestiondata** 容器已打开；其中包含你在步骤 2 中上载的 PST 文件。 **ingestiondata** 容器位于“**存储帐户**”\>“**(SAS 附加服务)**”\>“**Blob 容器**”下。 
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. 使用完 Microsoft Azure 存储资源管理器后，右键单击“**ingestiondata**”，然后单击“**分离**”断开与 Azure 存储区域的连接。 否则，下次尝试附加时会收到错误消息。 
    
    ![右键单击“ingestion”，然后单击“分离”以断开与 Azure 存储区域的连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步骤 4：创建 PST 导入映射文件

将 PST 文件上载到你所在 Office 365 组织的 Azure 存储位置后，下一步是创建一个逗号分隔值 (CSV) 文件，用于指定要将 PST 文件导入到哪些用户邮箱。 在下一步中，创建 PST 导入作业时，将提交此 CSV 文件。
  
1. [下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. 打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。


    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    该 CSV 文件的第一行（或者说标题行）列出了 PST 导入服务将用于将 PST 文件导入到用户邮箱中的参数。 每个参数名称都用逗号分隔开。 标题行下的每一行代表将 PST 文件导入到特定邮箱所对应的参数值。 您将需要用一行来对应每个要导入到用户邮箱中的 PST 文件。 一定要用实际数据替换映射文件中的占位符数据。

   **注意：** 不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。 

 3. 使用下表中的信息为 CSV 文件填充所需的信息。


    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定数据将导入到的 Office 365 服务。 若要将 PST 文件导入到用户邮箱，请使用 `Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |指定在步骤 2 中将 PST 文件上载到的 Azure 存储位置中的文件夹位置。  <br/> 如果在步骤 2 中你未在 SAS URL 中的 `/Dest:` 参数中包含可选子文件夹名称，请在 CSV 文件中将此参数留空。 如果包含了子文件夹名称，请在此参数中指定该名称（请参阅第二个示例）。 此参数的值区分大小写。  <br/> 无论采用哪种方法，均*不要*在 `FilePath` 参数的值中包含“ingestiondata”。  <br/><br/> **重要提示**：如果在步骤 2 中你在 SAS URL 中的 `/Dest:` 参数中包含了可选子文件夹名称，则文件路径名称的大小写必须与你使用的大小写相同。 例如，如果你在步骤 2 中将 `PSTFiles` 用作子文件夹名称，然后在 CSV 文件中的 `FilePath` 参数中使用 `pstfiles`，则导入 PST 文件将会失败。 请务必在两种情况下都使用相同的大小写。  <br/> |（保留为空白）  <br/> 或  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定要导入到用户邮箱的 PST 文件的名称。 此参数的值区分大小写。  <br/> <br/>**重要提示：** CSV 文件中的 PST 文件名的大小写必须与在步骤 2 中上载到 Azure 存储位置的 PST 文件相同。 例如，如果在 CSV 文件中的 `Name` 参数中使用 `annb.pst`，但实际 PST 文件的名称为 `AnnB.pst`，则导入该 PST 文件将会失败。 请确保 CSV 文件中的 PST 名称使用与实际 PST 文件相同的大小写。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定要将 PST 文件导入到的邮箱的电子邮件地址。 请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入公用文件夹。  <br/> 若要将 PST 文件导入到非活动邮箱，必须为此参数指定邮箱 GUID。 若要获取此 GUID，请在 Exchange Online 中运行以下 PowerShell 命令：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**注意：** 在某些情况下，你可能有多个邮箱具有相同的电子邮件地址，其中一个邮箱是活动邮箱，另一个邮箱处于软删除（或非活动）状态。 在这种情况下，必须指定邮箱 GUID 来唯一标识要将 PST 文件导入到的邮箱。 若要获取活动邮箱的此 GUID，请运行以下 PowerShell 命令：`Get-Mailbox <identity of active mailbox> | FL Guid`。 若要获取软删除（或非活动）邮箱的 GUID，请运行此命令：`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。  <br/> | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。 有两个选项：  <br/><br/>**FALSE** - 将 PST 文件导入到用户的主邮箱。  <br/> **TRUE** - 将 PST 文件导入到用户的存档邮箱。 这是假设[用户的存档邮箱已启用](enable-archive-mailboxes.md)的情况下。 <br/><br/>如果将此参数设置为 `TRUE`，但用户的存档邮箱未启用，则针对此用户进行的导入将失败。 请注意，如果针对某个用户的导入失败（因为他们的存档邮箱未启用，并且此属性设置为 `TRUE`），导入作业中的其他用户将不会受到影响。  <br/>  如果将此参数留空，PST 文件会导入到用户的主邮箱中。  <br/> <br/>**注意：** 若要针对主邮箱位于本地的某个用户将 PST 文件导入到基于云的存档邮箱，只需将此参数指定为 `TRUE`，并将 `Mailbox` 参数指定为该用户本地邮箱的电子邮件地址。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要将 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空，则 PST 将被导入到位于邮箱根级别的名为“**导入**”的新文件夹中（与“收件箱”文件夹和其他默认邮箱文件夹属于同一级别）。  <br/>  如果指定 `/`，PST 文件中的项目将被直接导入到用户的“收件箱”文件夹中。  <br/><br/>  如果指定 `/<foldername>`，PST 文件中的项目将被导入到名为 *\<foldername\>* 的文件夹中。 例如，如果使用 `/ImportedPst`，项目将被导入到名为 **ImportedPst** 的文件夹中。 此文件夹将位于用户邮箱内，与“收件箱”文件夹属于同一级别。  <br/><br/> **提示：** 请考虑运行几个测试批次来试验此参数，以便确定要将 PST 文件导入到的最佳文件夹位置。  <br/> |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定用于导入 ANSI 文件格式的 PST 文件的代码页的数值。 此参数用于从中国、日本和韩国 (CJK) 组织导入 PST 文件，因为这些语言通常使用双字节字符集 (DBCS) 进行字符编码。 对于为邮箱文件夹名使用 DBCS 的语言，如果此参数未用于导入 PST 文件，则在导入文件后，这些文件夹名通常会混淆。  <br/><br/> 有关要用于此参数的受支持值的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/> <br/>**注意：** 如前所述，这是一个可选参数，不一定非要在 CSV 文件中包含该参数。 或者，你可以包含该参数，并在一行或多行中将其值留空。  <br/> |（保留为空白）  <br/> 或  <br/>  `932`（这是 ANSI/OEM 日语的代码页标识符）  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。  <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。  <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。  <br/> |不适用  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>步骤 5：在 Office 365 中创建 PST 导入作业

下一步是在 Office 365 的导入服务中创建 PST 导入作业。 如前所述，你将提交在步骤 4 中创建的 PST 导入映射文件。 在你创建新作业后，Office 365 将分析 PST 文件中的数据，然后为你提供一个筛选数据的机会，以确定哪些数据可以实际导入到 PST 导入映射文件中指定的邮箱（请参阅[步骤 6](#step-6-filter-data-and-start-the-pst-import-job)）。
  
1. 转到 [https://protection.office.com](https://protection.office.com)，然后使用你 Office365 组织中的管理员帐户的凭据进行登录。 
    
2. 在安全与合规中心的左窗格中，单击“**数据管理**”，然后单击“**导入**”。
    
3. 在“**导入**”页面上，单击 ![添加图标](media/ITPro-EAC-AddIcon.gif)“**新建导入作业**”。
    
    **注意：** 你必须分配有相应的权限，才能访问安全与合规中心中的“**导入**”页面来创建新的导入作业。 有关更多详细信息，请参阅**准备工作**部分。 
    
4. 为 PST 导入作业键入一个名称，然后单击“**下一步**”。 请使用小写字母、数字、连字符和下划线。 无法在名称中使用大写字母或包含空格。
    
5. 在“**你想要上载或发送数据?**”页面上，单击“**上传你的数据**”，然后单击“**下一步**”。
    
    ![单击“上传你的数据”以创建网络上载导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在步骤 4 的“**导入数据**”页面上，单击“**我已完成上载我的文件**”和“**我有权访问该映射文件**”复选框，然后单击“**下一步**”。
    
    ![单击步骤 4 中的两个复选框](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在“**选择映射文件**”页面上，单击“**选择映射文件**”以提交在步骤 4 中创建的 PST 导入映射文件。 
    
    ![单击“选择映射文件”以提交为导入作业创建的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. CSV 文件的名称出现在“**映射文件名**”之下后，单击“**验证**”来检查 CSV 文件是否有错误。 
    
    ![单击“验证”来检查 CSV 文件是否有错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 文件必须经过成功验证才能创建 PST 导入作业。 注意，文件名在成功验证后会更改为绿色。 如果验证失败，请单击“**查看日志**”链接。 系统将打开一个验证错误报告，显示文件中失败的每一行所对应的错误消息。 
    
9. 在成功验证 PST 映射文件后，请阅读条款和条件文档，然后单击复选框。
    
10. 单击“**保存**”来提交作业，然后在成功创建作业后单击“**关闭**”。 
    
    系统将显示一个状态浮出页面，其中状态为“**正在分析**”，新导入作业将显示在“**导入**”页面上的列表中。 
    
11. 单击“**刷新**”![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif) 以更新“**状态**”列中显示的状态信息。 当分析完成且数据准备就绪可供导入时，状态将更改为“**分析已完成**”。
    
    可以单击导入作业以显示状态浮出页面，其中包含有关导入作业的更多详细信息，例如映射文件中列出的每个 PST 文件的状态。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步骤 6：筛选数据并启动 PST 导入作业

当你在步骤 5 中创建导入作业后，Office 365 将通过确定项目的存在时长以及 PST 文件中所含的不同邮件类型来分析 PST 文件中的数据（以安全的方式）。 分析完成且数据准备就绪可供导入后，你可以选择导入 PST 文件中包含的所有数据，或者通过设置用于控制可导入哪些数据的筛选器来减少导入的数据。
  
1. 在安全与合规中心的“**导入**”页面上，单击在步骤 5 中创建的导入作业所对应的“**已准备好导入到 Office 365**”。 
    
    ![单击你创建的导入作业旁边的“已准备好导入到 Office 365”](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    系统将显示一个浮出页面，其中包含有关 PST 文件的信息和有关导入作业的其他信息。
    
2. 在浮出页面上，单击“**导入到 Office 365**”。
    
    系统将显示“**筛选数据**”页面。 该页面包含通过 Office 365 对 PST 文件进行的分析得出的数据洞察，其中包括有关数据存在时长的信息。 此时，你可以选择筛选将要导入的数据或按原样导入所有数据。 
    
    ![你可以对 PST 文件中的数据进行缩减或导入所有数据](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 执行下列操作之一：
    
    a. 若要缩减导入的数据，请单击“**是，我想在导入前将其筛选**”。
    
    有关筛选 PST 文件中的数据然后启动导入作业的详细分步说明，请参阅[在将 PST 文件导入到 Office 365 时筛选数据](filter-data-when-importing-pst-files.md)。
    
    或
    
    b. 若要导入 PST 文件中的所有数据，请单击“**不，我想要导入所有内容**”，然后单击“**下一步**”。
    
4. 如果你选择导入所有数据，请单击“**导入数据**”来启动导入作业。 
    
    导入作业的状态将显示在“**导入**”页面上。 单击 ![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)“**刷新**”以更新“**状态**”列中显示的状态信息。 单击导入作业以显示状态浮出页面，该页面将显示正在导入的每个 PST 文件的状态信息。 

## <a name="how-the-import-process-works"></a>导入过程的工作原理
  
你可以使用网络上载选项和 Office 365 导入服务将 PST 文件批量导入到用户邮箱。 网络上载意味着你在 Microsoft 云中的临时存储区域上载 PST 文件。 然后，Office 365 导入服务将 PST 文件从存储区域复制到目标用户邮箱。
  
下面是向 Office 365 中的邮箱导入 PST 文件的网络上载过程的图示和说明。
  
![将 PST 文件导入到 Office 365 的网络上载过程的工作流](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **将 PST 导入工具和密钥下载到专用 Azure 存储位置** - 第一步是下载用于将 PST 文件上载到 Microsoft 云中的 Azure 存储位置的 Azure AzCopy 命令行工具和访问密钥。 需要从安全与合规中心的“**导入**”页面获取工具和密钥。 密钥（称为安全访问签名 (SAS) 密钥）为你提供将 PST 文件上载到专用的安全 Azure 存储位置所需的权限。 此访问密钥对组织是唯一的，有助于防止在 PST 文件上载至 Microsoft 云之后对其进行未经授权的访问。 请注意，将 PST 文件导入到 Office 365 不需要你的组织拥有单独的 Azure 订阅。 
    
2. **将 PST 文件上载到 Azure 存储位置** - 下一步是使用 AzCopy.exe 工具（已在步骤 1 中下载）将 PST 文件上载并存储到 Azure 存储位置，该存储位置位于你的 Office 365 组织所在的区域 Microsoft 数据中心。 若要上载，想要导入至 Office 365 的 PST 文件必须位于组织的文件共享或文件服务器上。
    
    请注意，在将 PST 文件上载到 Azure 存储位置之后，你可以执行一个可选步骤来查看这些文件的列表。
    
3. **创建 PST 导入映射文件** - 将 PST 文件上载到 Azure 存储位置后，下一步是创建逗号分隔值 (CSV) 文件，用于指定要将 PST 文件导入到哪些用户邮箱，请注意，PST 文件可导入到用户的主邮箱或其存档邮箱。 Office 365 导入服务将使用 CSV 文件中的信息来导入 PST 文件。
    
4. **创建 PST 导入作业** - 下一步是在安全与合规中心的“**导入**”页面上创建 PST 导入作业并提交在上一步骤创建的 PST 导入映射文件。 在你创建导入作业后，Office 365 将分析 PST 文件中的数据，然后为你提供设置筛选器的机会，以便控制哪些数据可以实际导入到 PST 导入映射文件中指定的邮箱。 
    
5. **筛选将要导入到邮箱的 PST 数据** - 创建并启动导入作业之后，Office 365 将通过确定项目的存在时长以及 PST 文件中所含的不同邮件类型来分析 PST 文件中的数据（以安全的方式）。 分析完成且数据准备就绪可供导入后，你可以选择导入 PST 文件中包含的所有数据，或者通过设置用于控制可导入哪些数据的筛选器来减少导入的数据。
    
6. **开始 PST 导入作业** - 开始导入作业之后，Office 365 使用 PST 导入映射文件中的信息将 PST 文件从 Azure 存储位置导入到用户邮箱。 与导入作业相关的状态信息（包括与每个导入的 PST 文件相关的信息）将显示在安全与合规中心的“**导入**”页面。 导入作业完成后，作业的状态将设置为“**完成**”。
  
## <a name="more-information"></a>更多信息

- 为什么要将 PST 文件导入到 Office 365？
    
  - 这是将组织的存档邮件数据导入到 Office 365 的好方法。
    
  - 用户在任意设备上都可以使用数据，因为数据存储在云中。
    
  - 它允许你将 Office 365 合规功能应用于你导入的 PST 文件中的数据，从而帮助满足你组织的合规性需求。 这包括：
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)和[自动展开存档](enable-unlimited-archiving.md)，从而向用户提供额外的邮箱存储空间来存储你导入的数据。 
    
  - 使邮箱处于“[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)”状态以保留导入的数据。 
    
  - 使用 Microsoft [电子数据展示工具](search-for-content.md)搜索你导入的数据。 
    
  - 使用 [Office 365 保留策略](retention-policies.md)来控制导入数据的保留时间，以及在保留期到期后要执行的操作。 
    
  - 在 [Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)中搜索影响你导入的数据的邮箱相关事件。 
    
  - 将数据导入到[非活动邮箱](create-and-manage-inactive-mailboxes.md)，以出于合规目的对数据进行存档。 
    
  - 使用[数据丢失防护策略](data-loss-prevention-policies.md)来防止敏感数据被泄露到组织外部。 
  
- 下面是在步骤 1 中获得的共享访问签名 (SAS) URL 示例。 此示例还包含你在 AzCopy.exe 工具中运行的用于将 PST 文件上载到 Office 365 的命令的语法。 请务必采取预防措施来保护 SAS URL，就像保护密码或其他与安全相关的信息一样。

    ```
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
``

- As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RetentionHoldEnabled*  property is set to  **True** so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold: 
    
    - After a certain period of time, you can turn off the retention hold by running the **Set-Mailbox -RetentionHoldEnabled $false** command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is June 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
