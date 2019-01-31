---
title: 使用网络上载到 Office 365 导入您的组织 PST 文件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 管理员： 了解如何使用网络上载批量导入到 Office 365 中的用户邮箱的多个 PST 文件。
ms.openlocfilehash: 81c799a8c820e9d9287f4792fe463d6a99b90e36
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666152"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>使用网络上载到 Office 365 导入您的组织 PST 文件

> [!NOTE]
> 本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
以下是需要使用网络上载批量导入到 Office 365 邮箱的多个 PST 文件的分步说明。有关使用网络上载批量导入 PST 文件迁移到 Office 365 邮箱，请参阅[使用网络上载导入 PST 文件的常见问题](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)的常见问题进行了问题。
  
[步骤 1： 复制 SAS URL 并安装 Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[步骤 2： 将 PST 文件上载到 Office 365](#step-2-upload-your-pst-files-to-office-365)

[（可选）步骤 3： 查看列表的 PST 文件上载到 Office 365](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 4： 创建 PST 导入映射文件](#step-4-create-the-pst-import-mapping-file)

[步骤 5：在 Office 365 中创建 PST 导入作业](#step-5-create-a-pst-import-job-in-office-365)

[步骤 6： 筛选数据，并启动 PST 导入作业](#step-6-filter-data-and-start-the-pst-import-job)

请注意，您需要执行步骤 1 仅执行一次将 PST 文件导入到 Office 365 邮箱。执行这些步骤后，按照步骤 2 至步骤 6 每的次您想要上载并导入一批 PST 文件。

## <a name="before-you-begin"></a>准备工作
  
- 您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：
    
  - 您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。
    
    或
    
  - 您必须是 Office 365 组织中的全局管理员。
    
  > [!TIP]
    > 请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。 
  
- 将 PST 文件导入到 Office 365 唯一受支持的方法是使用 Azure AzCopy 工具，如本主题中所述。不能使用 Azure 存储资源管理器上载直接到 Azure 存储区的 PST 文件。
    
- 您需要存储要导入到 Office 365 上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 2 中，您将运行 Azure AzCopy 工具将上载该文件服务器上存储或共享到 Office 365 的文件夹的 PST 文件。
    
- 此过程涉及复制并保存一份包含访问键的 URL。如果您想要查看上载到 Office 365 的 PST 文件的列表，在步骤 2 上载 PST 文件，并在步骤 3 中将使用此信息。请确保采取预防措施来保护此 URL，如将保护密码或其他安全相关的信息。例如受密码保护的 Microsoft Word 文档或加密的 USB 驱动器可能将其保存。请参阅此示例为[详细信息](#more-information)部分组合 URL 和密钥。 
    
- 您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。有关此主题中的**说明**选项卡上，请参阅步骤 4。 
    
- 在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：
    
  - 指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。 
    
  - 指定**TRUE**值在`IsArchive`参数。 
    
    有关详细信息，请参阅[步骤 4](#step-4-create-the-pst-import-mapping-file) 。 
    
- PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议本主题中的**详细信息**选项卡。 
    
- 默认情况下，可以接收的 Office 365 邮箱的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是，此限制的最大邮件接收 Office 365 中的大小为 150 MB。因此，如果导入 PST 文件包含大于 35 MB，我们将自动更改为 150 MB 的目标邮箱上*MaxReceiveSize*属性的值的导入 Office 365 服务的项。这将允许邮件 150 MB 要导入到用户邮箱。 
    
    > [!TIP]
    > 若要确定邮件接收大小为邮箱中，您可以运行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>步骤 1： 复制 SAS URL 并安装 Azure AzCopy

第一步是下载并安装 Azure AzCopy 工具，它是您将运行在步骤 2 到上载 PST 文件迁移到 Office 365 的工具。您还将为您的组织复制 SAS URL。此 URL 是 Microsoft 云的组织和共享访问签名 (SA) 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限将 PST 文件上载到 Azure 存储位置。请确保采取预防措施来保护 SAS URL。它是唯一的组织，并将在步骤 2 中使用。

> [!IMPORTANT]
> 若要导入 PST 文件使用网络上载方法中，我们建议使用以下过程中的步骤 6b 可以下载的 Azure AzCopy 的版本。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。
    
    > [!NOTE]
    > 您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。请参阅**开始之前**部分中的详细信息。 
    
3. 在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。
    
    将显示导入作业向导。
    
4. 为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。
    
5. 在**要上载或附带数据？** 页上，单击**上载数据**，然后单击**下一步**。
    
    ![单击上载以创建网络上载将数据导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在**导入数据**页上，执行以下两项操作： 
    
    ![复制 SAS URL 并下载导入数据页上的 Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    答： 在步骤 2 中，单击**显示网络上载 SAS URL**。显示 SAS URL 后，单击**复制到剪贴板**然后将其粘贴并将其保存到文件，以便您可以更高版本访问它。
    
    b.在步骤 3 中，单击**下载 Azure AzCopy**下载和安装 Azure AzCopy 工具。在弹出窗口中，单击**运行**以安装 AzCopy。 
    
> [!NOTE]
> 您可以**导入数据**页将保持打开状态 （以防您需要再次复制 SAS URL），或单击**取消**以关闭它。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>步骤 2： 将 PST 文件上载到 Office 365

现在您已准备好使用 AzCopy.exe 工具将 PST 文件上载到 Office 365。此工具上载，并将其存储在云中的 Microsoft Azure 的存储位置。如前所述，则上载到 PST 文件的 Azure 的存储位置位于同一区域 Microsoft 数据中心中您的 Office 365 组织所在的位置。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。每次运行 AzCopy 工具，您可以指定一个不同的源目录。 
  
1. 在您的本地计算机上打开命令提示符。
    
2. 转到的目录 AzCopy.exe 工具在步骤 1 中的安装位置。如果您在默认位置安装该工具，请转到`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. 运行以下命令以将 PST 文件上载到 Office 365。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    下表介绍参数以及它们所需的值。请注意您在上一步中获得该信息用于这些参数的值。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |指定包含 PST 文件将上载到 Office 365 组织中的源目录。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |步骤 1 中指定您获取的 SAS URL。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> **提示：**（可选）Azure 的存储位置上载到 PST 文件中，您可以指定子文件夹。通过添加 （之后"ingestiondata") 的子文件夹位置 SAS URL 中执行此操作。第一个示例不指定子文件夹;这意味着 Pst 将上载到根目录 （名为*ingestiondata* ） Azure 的存储位置。第二个示例上载到子文件夹 （名为*PSTFiles* ） 的 PST 文件的 Azure 的存储位置的根目录。<br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> 或  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |将详细状态消息输出到日志文件。默认情况下，详细日志文件名为 AzCopyVerbose.log，所在路径为 %LocalAppData%\Microsoft\Azure\AzCopy。如果对此选项指定现有的文件位置，则详细日志将被附加到该文件中。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |此可选开关指定递归模式，以便 AzCopy 工具会将位于指定源目录中的子文件夹中的 Pst 文件复制`/Source:`参数。  <br/> **注意：** 如果包括此开关，子文件夹中的 PST 文件将 Azure 存储位置中具有不同文件路径名，他们正在上载后。您将需要在您在步骤 4 中创建的 CSV 文件中指定的确切文件路径名。<br/> | `/S` <br/> |
    | `/Y` <br/> |此必需的开关允许使用只写 SAS 令牌，当您将 PST 文件上载到 Azure 存储位置。您在步骤 1 中获得 SAS URL (和指定的`/Dest:`参数) 是只写 SAS URL，因此，您必须包括此开关。请注意，只写 SAS URL 不会阻止您使用 Azure 存储浏览器查看上载到 Azure 存储位置的 PST 文件的列表。<br/> | `/Y` <br/> |
   
以下是对每个参数使用实际值的 AzCopy.exe 工具的语法示例：
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

运行该命令后，显示的状态消息会显示对 PST 文件进行上载的进度。最终状态消息显示已成功上载的文件总数。 

> [!TIP]
> 在成功运行 AzCopy.exe 命令并确认所有参数都正确无误后，保存一份同一个复制信息的位置 （安全） 文件的命令行语法获取在步骤 1 中。然后可以复制并粘贴在命令提示符下每次您想要运行 AzCopy.exe 工具以将 PST 文件上载到 Office 365 的此命令。您可能需要更改的唯一值是为`/Source:`参数。这取决于源目录 PST 文件的位置。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>（可选）步骤 3： 查看列表的 PST 文件上载到 Office 365

作为一个可选步骤，您可以安装和使用 Microsoft Azure 存储浏览器 （这是一个免费的开源工具） 若要查看已上载到 Azure blob PST 文件的列表。有两个理由，让您执行此操作：
  
- 验证 PST 文件从共享的文件夹或组织中的文件服务器已成功上载到 Azure 的 blob。
    
- 验证每个 PST 文件上载到 Azure blob 的文件名 （和子文件夹路径名如果包括了一个）。正在创建 PST 映射文件的下一步，因为您有时必须指定的文件夹路径名和文件名为每个 PST 文件时，这是非常有用。验证这些名称，可帮助减少 PST 映射文件中的潜在错误。
    
Microsoft Azure 存储 Explorer 正处于预览。
  
> [!IMPORTANT]
> 不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果有任何导入作业正在进行，然后中的所有 PST 文件**ingestiondata**容器中将不删除 30 天后创建的最新的导入作业。
  
安装 Azure 存储浏览器并连接到 Azure 存储区：
  
1. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 单击**使用共享的访问签名 (SA) URI 或连接字符串**，然后单击**下一步**。
    
4. 单击**使用 SAS URI**，将在步骤 1 中的获取 SAS URL 粘贴到**URI**下的框，然后单击**下一步**。
    
5. 在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。
    
    打开**ingestiondata**容器;它包含您在步骤 2 中上载的 PST 文件。**Ingestiondata**容器位于**存储帐户**下\> **（SAS-Attached 服务）** \> **Blob 容器**。 
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. 完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步骤 4： 创建 PST 导入映射文件

PST 文件已上载到 Office 365 组织的 Azure 存储位置后下, 一步是创建逗号分隔值 (CSV) 文件，指定 PST 文件将被导入到哪些用户邮箱。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。
  
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
    标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个要导入到用户邮箱的 PST 文件，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。

   **注意：** 不更改包括 SharePoint 参数; 在标题行中的任何内容它们将 PST 导入过程中忽略。 

 3. 使用下表中的信息来填充附有所需信息的 CSV 文件。


    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> |在您上载 PST 文件迁移到在步骤 2 中的 Azure 的存储位置指定的文件夹位置。  <br/> 如果您没有在 SAS URL 中包括的可选子文件夹名称`/Dest:`参数在步骤 2 中，将此参数留空 CSV 文件中。包含子文件夹名称，如果指定此参数中 （请参阅第二个示例）。此参数的值是区分大小写。<br/> 两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。  <br/><br/> **重要：** 这种情况的文件路径名称必须使用如果您在 SAS URL 中包括的可选子文件夹名称的情况下相同`/Dest:`在步骤 2 中的参数。例如，如果您使用`PSTFiles`的子文件夹命名为在步骤 2 中，然后使用`pstfiles`的`FilePath`CSV 文件中的参数，PST 文件导入将失败。请务必在这两种情况下使用相同的大小写。<br/> |（保留为空白）  <br/> 或  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。<br/> <br/>**重要：** CSV 文件中的 PST 文件名称的大小写必须与已上载到在步骤 2 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。<br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定的邮箱的 PST 文件导入到的电子邮件地址。请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入到公用文件夹。<br/> 若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**Note:** In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox<identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command  `Get-mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid。  <br/> | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：<br/><br/>**FALSE** -导入用户的主邮箱的 PST 文件。  <br/> **TRUE** -将 PST 文件导入用户的存档邮箱。这假定[已启用用户的存档邮箱](enable-archive-mailboxes.md)。<br/><br/>如果将此参数设置为`TRUE`和用户的存档邮箱未启用，为该用户导入将失败。请注意，如果导入失败的一个用户 (因为其归档未启用，此属性设置为`TRUE`)，不会影响导入作业中的其他用户。<br/>  如果将此参数留空，PST 文件导入到用户的主邮箱。  <br/> <br/>**注意：** PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定`TRUE`为此参数指定用户的内部部署邮箱的电子邮件地址和`Mailbox`参数。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。  <br/>  如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。  <br/><br/>  如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为文件夹*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到一个名为**ImportedPst**文件夹。此文件夹将位于收件箱文件夹相同级别的用户的邮箱。<br/><br/> **提示：** 考虑运行几个测试批次试验使用此参数，以便您可以确定要导入到 Pst 文件的最佳文件夹位置。  <br/> |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。<br/><br/> 有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/> <br/>**注意：** 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。<br/> |（保留为空白）  <br/> 或  <br/>  `932`（这是代码页标识符的 ANSI/OEM 日语）  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>步骤 5：在 Office 365 中创建 PST 导入作业

下一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 4 中创建的 PST 导入映射文件。创建新的作业后，Office 365 分析 PST 文件中的数据，并使您能够筛选实际上获取导入到邮箱 PST 导入映射文件中指定的数据 （请参阅[步骤 6](#step-6-filter-data-and-start-the-pst-import-job)）。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控**，然后单击**导入**。
    
3. 在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。
    
    **注意：** 您需要分配访问安全性中的**导入**页的适当权限&amp;合规性中心，以创建新的导入作业。请参阅**开始之前**部分中的详细信息。 
    
4. 为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。
    
5. 在**要上载或附带数据？** 页上，单击**上载数据**，然后单击**下一步**。
    
    ![单击上载以创建网络上载将数据导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在**导入数据**页上的步骤 4 中，单击**我已经完成了上载我文件**和**我有权访问映射文件**，选中框中，，然后单击**下一步**。
    
    ![单击在步骤 4 中的两个复选框](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在**选择映射文件**页上，单击**选择映射文件**以提交您在步骤 4 中创建的 PST 导入映射文件。 
    
    ![单击选择映射文件以提交您创建的导入作业的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. 后的 CSV 名称文件显示在**映射文件名称**下，单击**验证**检查 CSV 文件中的错误。 
    
    ![单击验证检查 CSV 文件中的错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，失败的文件中的各行的错误消息。 
    
9. 在成功验证 PST 映射文件后，读取条款和条件的文档，，，然后单击复选框。
    
10. 单击**保存**以提交的作业，然后单击**关闭**后作业已成功创建。 
    
    将显示状态弹出页，**正在进行分析**的状态，并在**导入**页上的列表中显示新的导入作业。 
    
11. 单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新**状态**列中显示的状态信息。当完成分析，并已准备好要导入数据时，状态更改为**完成分析**。
    
    您可以单击导入作业以显示状态弹出页，其中包含有关导入作业状态等的映射文件中列出的每个 PST 文件的详细的信息。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步骤 6： 筛选数据，并启动 PST 导入作业

步骤 5 中创建导入作业后，Office 365 分析 PST 文件中的数据 （以安全方式） 标识的项目和 PST 文件中包含的其他消息类型的期限。在完成分析，并且已准备好导入数据，您可以选择要导入 PST 文件中包含的所有数据或可以修整通过设置控制哪些数据获取导入的筛选器导入的数据。
  
1. 在安全中的**导入**页上&amp;合规性中心，单击步骤 5 中创建的导入作业的**已准备好导入到 Office 365** 。 
    
    ![单击您创建的导入作业旁边导入到 Office 365 准备](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飞出页将显示有关 PST 文件的信息以及其他信息导入作业。
    
2. 在弹出页上，单击**导入到 Office 365**。
    
    显示**筛选数据**页。它包含生成 Office 365，包括有关数据的期限对 PST 文件执行分析数据见解。此时，您可以选择要筛选的数据将导入或导入原样的所有数据。 
    
    ![您可以修整 PST 文件中的数据或导入的所有](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 执行下列操作之一：
    
    答： 来裁切导入的数据，请单击**是，我希望筛选其之前导入**。
    
    有关筛选 PST 文件中的数据，然后启动导入作业的详细分步说明，请参阅[筛选器数据导入 PST 文件迁移到 Office 365 时](filter-data-when-importing-pst-files.md)。
    
    或
    
    b.若要导入 PST 文件中的所有数据中,，单击**否，我想要导都入的所有内容，** 然后单击**下一步**。
    
4. 如果您选择要导入的所有数据，请单击都**导都入数据**以启动导都入作业。 
    
    导入作业的状态是**导入**页上的显示。单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新**状态**列中显示的状态信息。单击显示状态弹出页，显示状态信息正在导入每个 PST 文件导入作业。 

## <a name="how-the-import-process-works"></a>导入过程的工作原理
  
您可以使用网络上载选项和导入 Office 365 服务批量导入到用户邮箱的 PST 文件。网络上载意味着您在 Microsoft 云中的临时存储区上载 PST 文件。然后 Office 365 导入服务将复制的 PST 文件从存储区域到目标用户邮箱。
  
以下是图和 PST 文件导入 Office 365 中的邮箱的网络上载过程的说明。
  
![网络的工作流上载到 Office 365 导入 PST 文件的过程](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **下载 PST 导入工具和密钥对专用的 Azure 存储位置**-第一步是下载 Azure AzCopy 命令行工具和用于将 PST 文件上载到云中 Microsoft Azure 存储位置访问键。您获取这些从 Office 365 安全性**导入**页上&amp;合规性中心。键 （调用安全访问 (SA) 签名密钥、 到专用提供了上载 PST 文件所需的权限和安全 Azure 的存储位置。此访问键所特有的组织，并帮助防止未授权的访问到 PST 文件，它们上载到 Microsoft 云后。请注意到 Office 365 导入 PST 文件不需要组织拥有单独的 Azure 订阅。 
    
2. **上载到 Azure 存储位置的 PST 文件**的下一步是使用 AzCopy.exe 工具 （步骤 1 中下载） 上载，并将 PST 文件存储在驻留在同一区域 Microsoft 数据中心中的 Azure 存储位置其中 Office 365组织所在。若要将它们上载，您希望导入到 Office 365 的 PST 文件必须位于文件共享或组织中的文件服务器。
    
    请注意，您可执行的用于查看 PST 文件的列表，它们上载到 Azure 存储位置后可选步骤。
    
3. **创建 PST 导入映射文件**-PST 文件已上载到 Azure 存储位置后下, 一步是创建指定哪些用户邮箱的 PST 文件将被导入以，请注意，可以是 PST 文件的以逗号分隔的值 (CSV) 文件 导入到用户的主邮箱或其存档邮箱。导入 Office 365 服务将使用该 CSV 文件中的信息导入 PST 文件。
    
4. **创建 PST 导入作业**-下一步是在安全的**导入**页上创建 PST 导入作业&amp;合规性中心和提交上一步中创建的 PST 导入映射文件。创建导入作业后，Office 365 分析 PST 文件中的数据，并使您能够设置控制哪些数据获取实际导入 PST 导入映射文件中指定的邮箱的筛选器。 
    
5. **筛选器，将导入到邮箱的 PST 数据**-导入作业的创建和启动后，Office 365 分析 PST 文件中的数据 （安全、 可靠地） 通过确定项目和 PST 文件中包含的其他消息类型的期限.在完成分析，并且已准备好导入数据，您可以选择要导入 PST 文件中包含的所有数据或可以修整通过设置控制哪些数据获取导入的筛选器导入的数据。
    
6. **启动 PST 导入作业**-启动导入作业后，Office 365 使用的信息在 PST 导入映射文件从他 Azure 的存储位置的 Pst 文件导入到用户邮箱。有关 （包括有关正在导入每个 PST 文件） 导入作业的状态信息显示在安全中的**导入**页上&amp;合规性中心。完成导入作业后，此作业的状态设置为**完成**。
  
## <a name="more-information"></a>更多信息

- 为什么到 Office 365 导入 PST 文件？
    
  - 它是贵组织的存档消息数据导入到 Office 365 的好方法。
    
  - 用户在任意设备上都可以使用数据，因为数据存储在云中。
    
  - 允许您从 PST 文件导入应用于数据的 Office 365 合规性功能，从而帮助您的组织满足合规性需求。这包括：
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)和[自动扩展存档](enable-unlimited-archiving.md)为用户提供其他邮箱空间来存储您导入的数据。 
    
  - 将邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)保留您导入的数据。 
    
  - 使用 Microsoft[电子数据展示工具](search-for-content.md)搜索您导入的数据。 
    
  - 使用[Office 365 保留策略](retention-policies.md)来控制您导入的数据将保留多长时间，和要采取的保留期过后哪些操作。 
    
  - 搜索[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)的邮箱相关的事件的会影响您导入的数据。 
    
  - 将数据导入到存档数据，出于合规性目的的[非活动邮箱](create-and-manage-inactive-mailboxes.md)。 
    
  - 使用[数据丢失预防策略](data-loss-prevention-policies.md)阻止敏感数据泄漏组织外部。 
  
- 下面是一个示例获取在步骤 1 中的共享访问签名 (SA) url。此示例还包含到上载 PST 文件迁移到 Office 365 中运行 AzCopy.exe 工具中的命令的语法。请确保采取预防措施来保护 SAS URL 像将保护密码或其他安全相关的信息。

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
    
   - You can configure the retention hold so that it's turned off on some date in the future. You do this by running the **Set-Mailbox -EndDateForRetentionHold *date*** command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  **Set-Mailbox -EndDateForRetentionHold 8/1/2016**. In this scenario, you would leave the  **RetentionHoldEnabled**  property set to  *True*. For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    
