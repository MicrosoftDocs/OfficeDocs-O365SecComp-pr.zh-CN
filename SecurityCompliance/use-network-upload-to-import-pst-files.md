---
title: 使用网络上传将组织 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: '对于管理员: 了解如何使用网络上传将多个 PST 文件批量导入 Office 365 中的用户邮箱。'
ms.openlocfilehash: 73123d5f36a01b31cfc38e6404bd400bb722fb36
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "31814083"
---
# <a name="use-network-upload-to-import-your-organization-pst-files-to-office-365"></a>使用网络上传将组织 PST 文件导入到 Office 365

> [!NOTE]
> 这篇文章面向对象为管理员。 您正在尝试将 PST 文件导入到您自己的邮箱吗？ 请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
下面是使用网络上载批量导入 Office 365 邮箱中的多个 PST 文件所需的分步说明。 有关使用网络上载将 pst 文件批量导入到 Office 365 邮箱的常见问题, 请参阅[使用网络上载导入 pst 文件中的 faq](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files)。
  
[步骤 1: 复制 SAS URL 并安装 Azure AzCopy](#step-1-copy-the-sas-url-and-install-azure-azcopy)

[步骤 2: 将 PST 文件上传到 Office 365](#step-2-upload-your-pst-files-to-office-365)

[Optional步骤 3: 查看已上载到 Office 365 的 PST 文件的列表](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步骤 4: 创建 PST 导入映射文件](#step-4-create-the-pst-import-mapping-file)

[步骤 5: 在 Office 365 中创建 PST 导入作业](#step-5-create-a-pst-import-job-in-office-365)

[步骤 6: 筛选数据并启动 PST 导入作业](#step-6-filter-data-and-start-the-pst-import-job)

请注意, 您只需执行步骤1一次即可将 PST 文件导入到 Office 365 邮箱。 执行这些步骤后, 请按照步骤2到步骤6操作, 每次上载和导入一批 PST 文件。

## <a name="before-you-begin"></a>准备工作
  
- 您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。 默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. 有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "向角色组添加角色" 或 "创建角色组" 部分。
    
    此外, 若要在 Security & 合规性中心中创建导入作业, 必须满足以下条件之一:
    
  - 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
  - 您必须是 Office 365 组织中的全局管理员。
    
  > [!TIP]
    > 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。 若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
- 将 PST 文件导入到 Office 365 的唯一受支持的方法是使用 Azure AzCopy 工具, 如本主题中所述。 无法使用 azure 存储资源管理器将 PST 文件直接上载到 Azure 存储区域。
    
- 您需要将您要导入的 PST 文件存储到组织中的文件服务器或共享文件夹上的 Office 365 中。 在步骤2中, 将运行 Azure AzCopy 工具, 该工具会将存储在此文件服务器或共享文件夹上的 PST 文件上载到 Office 365。
    
- 此过程涉及复制和保存包含访问键的 URL 的副本。 如果要查看上传到 Office 365 的 pst 文件的列表, 则将在步骤2中使用此信息来上载 PST 文件, 并在步骤3中使用此信息。 请务必采取预防措施来保护此 URL, 如保护密码或其他与安全相关的信息。 例如, 您可以将其保存到受密码保护的 Microsoft Word 文档或加密的 USB 驱动器。 有关此组合 URL 和密钥的示例, 请参阅[详细信息](#more-information)部分。 
    
- 您可以将 PST 文件导入到 Office 365 中的非活动邮箱。 为此, 请在 PST 导入映射文件的`Mailbox`参数中指定非活动邮箱的 GUID。 有关信息, 请参阅本主题中的 "**说明**" 选项卡上的步骤4。 
    
- 在 Exchange 混合部署中, 可以将 PST 文件导入到主邮箱位于本地的用户的基于云的存档邮箱。 为此, 请在 PST 导入映射文件中执行以下操作:
    
  - 在`Mailbox`参数中指定用户的内部部署邮箱的电子邮件地址。 
    
  - 在`IsArchive`参数中指定**TRUE**值。 
    
    有关详细信息, 请参阅[步骤 4](#step-4-create-the-pst-import-mapping-file) 。 
    
- 将 PST 文件导入到 Office 365 邮箱后, 邮箱的保留挂起设置将处于无限期的期限内打开。 这意味着将不会处理分配给邮箱的保留策略, 除非您关闭保留挂起或设置关闭保留的日期。 我们为什么要这么做呢？ 如果导入到邮箱的邮件是旧邮件, 则可能会永久删除 (清除), 因为他们的保留期已过, 因为其保留期已根据邮箱配置的保留设置而过期。 将邮箱置于保留挂起状态将使邮箱所有者时间管理这些新导入的邮件, 或为您提供更改邮箱保留设置的时间。 有关管理保留挂起的建议, 请参阅本主题中的 "**详细信息**" 选项卡。 
    
- 默认情况下, Office 365 邮箱可以接收的最大邮件大小为 35 MB。 这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。 但是, Office 365 中最大邮件接收大小的限制是 150 MB。 因此, 如果您导入的 PST 文件中包含大于 35 MB 的项目, 则 Office 365 导入服务会将目标邮箱上的*MaxReceiveSize*属性值自动更改为 150 MB。 这将允许将最大为 150 MB 的邮件导入到用户邮箱。 
    
    > [!TIP]
    > 若要标识邮箱的邮件接收大小, 可以在 Exchange Online PowerShell 中运行以下命令: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 

## <a name="step-1-copy-the-sas-url-and-install-azure-azcopy"></a>步骤 1: 复制 SAS URL 并安装 Azure AzCopy

第一步是下载并安装 Azure AzCopy 工具, 该工具是您将在步骤2中运行以将 PST 文件上载到 Office 365 的工具。 您还将为您的组织复制 SAS URL。 此 URL 是用于组织的 Microsoft 云中的 Azure 存储位置的网络 URL 和共享访问签名 (SAS) 密钥的组合。 此项为你提供将 PST 文件上载到 Azure 存储位置所需的权限。 请务必采取预防措施来保护 SAS URL。 它对您的组织是唯一的, 将在步骤2中使用。

> [!IMPORTANT]
> 若要使用网络上传方法导入 PST 文件, 我们建议您在以下过程中使用可在步骤6b 中下载的 Azure AzCopy 版本。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在安全 & 合规性中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。
    
    > [!NOTE]
    > 必须为您分配适当的权限, 才能访问 Security & 合规中心中的 "**导入**" 页。 有关详细信息, 请参阅 "**开始之前**" 部分。 
    
3. 在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。
    
    将显示 "导入作业向导"。
    
4. 键入 PST 导入作业的名称, 然后单击 "**下一步**"。 使用小写字母、数字、连字符和下划线。 不能在名称中使用大写字母或包含空格。
    
5. 在 "**是否要上载或传送数据？** " 页上, 单击 "**上载数据**", 然后单击 "**下一步**"。
    
    ![单击 "上载数据" 以创建网络上载导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在 "**导入数据**" 页上, 执行以下两项操作: 
    
    ![复制 SAS URL 并在 "导入数据" 页面上下载 Azure AzCopy 工具](media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. 在步骤2中, 单击 "**显示网络上载 SAS URL**"。 显示 SAS URL 后, 单击 "**复制到剪贴板**", 然后将其粘贴并保存到文件中, 以便稍后对其进行访问。
    
    b. 在步骤3中, 单击 "**下载 azure AzCopy** " 以下载并安装 azure AzCopy 工具。 在弹出窗口中, 单击 "**运行**" 以安装 AzCopy。 
    
> [!NOTE]
> 您可以将 "**导入数据**" 页保留为打开状态 (如果需要再次复制 SAS URL) 或单击 "**取消**" 关闭它。 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>步骤 2: 将 PST 文件上传到 Office 365

现在, 您可以使用 AzCopy 工具将 PST 文件上传到 Office 365。 此工具将其上载到 Microsoft 云中的 Azure 存储位置并将其存储在其中。 如前所述, 您将 PST 文件上传到的 Azure 存储位置位于 Office 365 组织所在的相同区域 Microsoft 数据中心。 若要完成此步骤，PST 文件必须位于您的组织中的文件共享或文件服务器中。 这在下面的过程中称为“源目录”。 每次运行 AzCopy 工具时, 都可以指定不同的源目录。 
  
1. 在您的本地计算机上打开命令提示符。
    
2. 转到您在步骤 1 中安装 AzCopy.exe 工具的目录。 如果将该工具安装在默认位置, 请转到`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。
    
3. 运行以下命令, 将 PST 文件上载到 Office 365。

    ```
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
  
    ```
 
    > [!IMPORTANT] 
    > 必须在上一个命令中将目录指定为源位置;您不能指定单个 PST 文件。 将上载源目录中的所有 PST 文件。
 
    下表描述了 AzCopy 参数及其必需的值。 在上一步中获得的信息在这些参数的值中使用。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |指定组织中包含将上载到 Office 365 的 PST 文件的源目录。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |指定您在步骤1中获取的 SAS URL。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> **提示:** Optional您可以在 Azure 存储位置指定一个子文件夹, 将 PST 文件上载到。 为此, 请在 SAS URL 中添加子文件夹位置 (在 "ingestiondata" 之后)。 第一个示例未指定子文件夹;这意味着 pst 将被上载到 Azure 存储位置的根 (名为*ingestiondata* )。 第二个示例将 PST 文件上载到 Azure 存储位置的根目录中的子文件夹 (名为*PSTFiles* )。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> 或  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |将详细状态消息输出到日志文件。默认情况下，详细日志文件名为 AzCopyVerbose.log，所在路径为 %LocalAppData%\Microsoft\Azure\AzCopy。如果对此选项指定现有的文件位置，则详细日志将被附加到该文件中。  <br/> 请务必用双引号 (" ") 引住此参数的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |此可选开关指定递归模式, 以便 AzCopy 工具将复制位于由`/Source:`参数指定的源目录中的子文件夹中的 pst 文件。  <br/> **注意:** 如果包含此开关, 则在上载后, 在 Azure 存储位置中, 子文件夹中的 PST 文件将具有不同的文件路径。 您必须在您在步骤4中创建的 CSV 文件中指定确切的文件路径名。  <br/> | `/S` <br/> |
    | `/Y` <br/> |当您将 PST 文件上传到 Azure 存储位置时, 此必需的开关允许使用仅写 SAS 令牌。 您在步骤 1 (和在参数中`/Dest:`指定) 中获取的 sas url 是只写 sas url, 这就是必须包含此开关的原因。 请注意, 只写 SAS URL 不会阻止你使用 Azure 存储资源管理器查看上载到 Azure 存储位置的 PST 文件的列表。  <br/> | `/Y` <br/> |
   
以下是对每个参数使用实际值的 AzCopy.exe 工具的语法示例：
    
```
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
  
```

运行该命令后，显示的状态消息会显示对 PST 文件进行上载的进度。最终状态消息显示已成功上载的文件总数。 

> [!TIP]
> 在成功运行 AzCopy 命令并验证所有参数是否正确后, 将命令行语法的副本保存到您在步骤1中获取的信息所复制到的相同 (安全) 文件中。 然后, 您可以在每次运行 AzCopy 工具以将 PST 文件上载到 Office 365 时, 在命令提示符下复制并粘贴此命令。 您可能需要更改的唯一值是`/Source:`参数的值。 具体取决于 PST 文件所在的源目录。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Optional步骤 3: 查看已上载到 Office 365 的 PST 文件的列表

作为可选步骤, 您可以安装并使用 Microsoft Azure 存储资源管理器 (它是一个免费的开源工具), 以查看已上载到 Azure blob 的 PST 文件的列表。 有两个很好的理由来执行此操作：
  
- 验证组织中的共享文件夹或文件服务器中的 PST 文件是否已成功上载到 Azure blob。
    
- 验证上载到 Azure blob 的每个 PST 文件的文件名 (和子文件夹路径名)。 当您在下一步中创建 PST 映射文件时，这确实非常有用，因为您必须为每个 PST 文件指定文件夹路径名和文件名。 验证这些名称可以帮助减少 PST 映射文件中的潜在错误。
    
Microsoft Azure 存储资源管理器处于预览阶段。
  
> [!IMPORTANT]
> 无法使用 Azure 存储资源管理器上传或修改 PST 文件。 将 PST 文件导入到 Office 365 的唯一受支持的方法是使用 AzCopy。 此外, 也不能删除已上载到 Azure blob 的 PST 文件。 如果尝试删除 PST 文件，将看到提示没有所需权限的错误消息。 请注意, 所有 PST 文件都将自动从 Azure 存储区域中删除。 If there are no import jobs in progress, then all PST files in the **ingestiondata** container are deleted 30 days after the most recent import job was created.
  
若要安装 azure 存储资源管理器并连接到 Azure 存储区, 请执行以下操作:
  
1. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
2. 启动 Microsoft Azure 存储资源管理器, 在左窗格中右键单击 "**存储帐户**", 然后单击 "**连接到 Azure 存储**"。
    
    ![右键单击 "存储帐户", 然后单击 "连接到 Azure 存储"](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. 单击 "**使用共享访问签名 (SAS) URI 或连接字符串**", 然后单击 "**下一步**"。
    
4. 单击 "**使用 SAS URI**", 将您在步骤1中获取的 SAS URL 粘贴到 " **URI**" 下的框中, 然后单击 "**下一步**"。
    
5. 在 "**连接摘要**" 页上, 您可以查看连接信息, 然后单击 "**连接**"。
    
    打开**ingestiondata**容器;它包含您在步骤2中上载的 PST 文件。 **ingestiondata**容器位于**存储帐户** \> **(SAS 附加服务)** \> **Blob 容器**下。 
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. 使用 Microsoft Azure 存储资源管理器完成后, 右键单击 " **ingestiondata**", 然后单击 "**分离**" 断开与 Azure 存储区域的连接。 否则，下次尝试附加时您会收到错误消息。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步骤 4: 创建 PST 导入映射文件

将 pst 文件上传到 Office 365 组织的 Azure 存储位置之后, 下一步是创建一个逗号分隔值 (CSV) 文件, 该文件指定要将 PST 文件导入到哪些用户邮箱。 创建 PST 导入作业时, 将在下一步中提交此 CSV 文件。
  
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

   **注意:** 请勿更改标题行中的任何内容, 包括 SharePoint 参数;在 PST 导入过程中将忽略它们。 

 3. 使用下表中的信息来填充附有所需信息的 CSV 文件。


    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要将数据导入到的 Office 365 服务。 若要将 PST 文件导入到用户`Exchange`邮箱, 请使用。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |指定您在步骤2中将 PST 文件上载到的 Azure 存储位置中的文件夹位置。  <br/> 如果在步骤2中的`/Dest:`参数中未将可选子文件夹名称包括在 SAS URL 中, 则在 CSV 文件中将此参数留空。 如果包含子文件夹名称, 请在此参数中指定它 (请参阅第二个示例)。 此参数的值区分大小写。  <br/> 无论采用哪种方式, 都*不要*在`FilePath`参数的值中包含 "ingestiondata"。  <br/><br/> **重要说明:** 如果在步骤2的`/Dest:`参数中的 SAS URL 中包含可选子文件夹名称, 则文件路径名称的大小写必须与您使用的大小写相同。 例如, 如果您在步骤`PSTFiles` 2 中用于子文件夹名称, 然后在 CSV `pstfiles`文件中`FilePath`的参数中使用, 则 PST 文件的导入将失败。 请务必在两个实例中使用相同的大小写。  <br/> |（保留为空白）  <br/> 或  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定要导入到用户邮箱的 PST 文件的名称。  此参数的值区分大小写。  <br/> <br/>**重要说明:** CSV 文件中的 pst 文件名的大小写必须与上载到步骤2中的 Azure 存储位置的 pst 文件相同。 例如, 如果在 CSV 文件`annb.pst`的`Name`参数中使用, 但实际的 pst 文件的名称是`AnnB.pst`, 则该 pst 文件的导入将失败。 请确保 CSV 文件中的 PST 名称使用与实际 pst 文件相同的大小写。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定要将 PST 文件导入到其中的邮箱的电子邮件地址。  请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入公用文件夹。  <br/> 若要将 PST 文件导入到非活动邮箱, 您必须为此参数指定邮箱 GUID。 若要获取此 GUID, 请在 Exchange Online 中运行以下 PowerShell 命令:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**注意:** 在某些情况下, 您可能有多个邮箱具有相同的电子邮件地址, 其中一个邮箱是活动邮箱, 另一个邮箱处于软删除 (或非活动) 状态。 在这些情况下, 您必须指定邮箱 GUID, 以唯一标识要将 PST 文件导入到的邮箱。 若要获取活动邮箱的此 GUID, 请运行以下 PowerShell 命令`Get-Mailbox <identity of active mailbox> | FL Guid`:。 若要获取软删除 (或非活动) 邮箱的 GUID, 请运行此`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`命令。  <br/> | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。 有两个选项：  <br/><br/>**FALSE** -将 PST 文件导入到用户的主邮箱。  <br/> **TRUE** -将 PST 文件导入到用户的存档邮箱。 This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). <br/><br/>如果将此参数设置为`TRUE`且用户的存档邮箱未启用, 则该用户的导入将失败。 请注意, 如果一个用户的导入失败 (因为未启用其存档, 并且此属性设置`TRUE`为), 则导入作业中的其他用户将不会受到影响。  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> <br/>**注意:** 若要将 PST 文件导入到其主邮箱是本地邮箱的用户的基于云的存档邮箱, 只需`TRUE`为此参数指定, 并为该`Mailbox`参数指定用户的内部部署邮箱的电子邮件地址。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定将 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空, 则会将 PST 导入到位于邮箱根级别 (与 "收件箱" 文件夹和其他默认邮箱文件夹相同的级别) 的名为 "**导入**" 的新文件夹中。  <br/>  如果指定`/`, 则 PST 文件中的项目将直接导入到用户的 "收件箱" 文件夹中。  <br/><br/>  如果指定`/<foldername>`, 则 PST 文件中的项目将被导入到名为* \<"\> *文件夹名称" 的文件夹中。 例如, 如果使用`/ImportedPst`, 则会将项目导入到名为**ImportedPst**的文件夹中。 此文件夹将位于与 "收件箱" 文件夹相同级别的用户邮箱中。  <br/><br/> **提示:** 请考虑运行几个测试批处理, 以试用此参数, 以便您可以确定将 pst 文件导入到的最佳文件夹位置。  <br/> |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定用于以 ANSI 文件格式导入 PST 文件的代码页的数值。 此参数用于从中文、日语和朝鲜语 (CJK) 组织导入 PST 文件, 这是因为这些语言通常使用双字节字符集 (DBCS) 进行字符编码。 如果未使用此参数导入使用 DBCS 作为邮箱文件夹名称的语言的 PST 文件, 则在导入这些文件夹名称时通常会出现乱码。  <br/><br/> 有关要用于此参数的受支持值的列表, 请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/> <br/>**注意:** 如前所述, 这是一个可选参数, 无需将其包含在 CSV 文件中。 或者, 可以将其包含在一个或多个行中, 并为其保留值为空。  <br/> |（保留为空白）  <br/> 或  <br/>  `932` (ANSI/OEM 日语的代码页标识符)  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>步骤 5: 在 Office 365 中创建 PST 导入作业

下一步是在 Office 365 中的 "导入服务" 中创建 PST 导入作业。 如前面所述, 您将提交在步骤4中创建的 PST 导入映射文件。 在创建新作业之后, Office 365 将分析 pst 文件中的数据, 然后让您有机会筛选实际导入到在 PST 导入映射文件中指定的邮箱的数据 (请参阅[步骤 6](#step-6-filter-data-and-start-the-pst-import-job))。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在安全 & 合规性中心的左侧窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。
    
3. 在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。
    
    **注意:** 您必须分配有适当的权限才能访问 Security & 合规中心中的 "**导入**" 页, 以创建新的导入作业。 有关详细信息, 请参阅 "**开始之前**" 部分。 
    
4. 键入 PST 导入作业的名称, 然后单击 "**下一步**"。 使用小写字母、数字、连字符和下划线。 不能在名称中使用大写字母或包含空格。
    
5. 在 "**是否要上载或传送数据？** " 页上, 单击 "**上载数据**", 然后单击 "**下一步**"。
    
    ![单击 "上载数据" 以创建网络上载导入作业](media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在步骤4中的 "**导入数据**" 页上, 单击 "已**完成上传我的文件**" 和 **"我有权访问映射文件"** 复选框, 然后单击 "**下一步**"。
    
    ![单击步骤4中的两个复选框](media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在 "**选择映射文件**" 页上, 单击 "**选择映射文件**" 以提交您在步骤4中创建的 PST 导入映射文件。 
    
    ![单击 "选择映射文件" 以提交为导入作业创建的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. 在 "**映射**文件名" 下显示 csv 文件的名称后, 单击 "**验证**" 以检查 CSV 文件中的错误。 
    
    ![单击 "验证" 以检查 CSV 文件是否存在错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 文件必须经过成功验证才能创建 PST 导入作业。 注释成功验证后, 文件名更改为绿色。 如果验证失败, 请单击 "**查看日志**" 链接。 打开验证错误报告, 并对文件中每个失败的行提供错误消息。 
    
9. 在成功验证了 PST 映射文件后, 请阅读条款和条件文档, 然后单击该复选框。
    
10. 单击 "**保存**" 以提交作业, 然后在作业成功创建后单击 "**关闭**"。 
    
    显示状态弹出页面, 状态为 "**正在进行分析**", 新的导入作业显示在 "**导入**" 页上的列表中。 
    
11. 单击 "**刷新** ![刷新](media/O365-MDM-Policy-RefreshIcon.gif) " 图标可更新 "**状态**" 列中显示的状态信息。 分析完成并准备好导入数据后, 状态将更改为 "**分析已完成**"。
    
    您可以单击 "导入作业" 以显示 "状态弹出页面", 其中包含有关导入作业的更多详细信息, 如映射文件中列出的每个 PST 文件的状态。
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步骤 6: 筛选数据并启动 PST 导入作业

在步骤5中创建导入作业后, Office 365 将通过标识项目的期限和 pst 文件中包含的不同邮件类型来分析 pst 文件中的数据 (以安全和安全的方式)。 分析完成并准备导入数据后, 可以选择导入 PST 文件中包含的所有数据, 也可以通过设置用于控制导入数据的筛选器来裁切导入的数据。
  
1. 在 Security & 合规性中心的 "**导入**" 页上, 单击 "已准备好为您在步骤5中创建的导入作业**导入 Office 365** "。 
    
    ![单击您创建的导入作业旁边的 "已准备好导入到 Office 365"](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    将显示一个 "飞出" 页面, 其中包含有关 PST 文件的信息以及有关导入作业的其他信息。
    
2. 在弹出页面上, 单击 "**导入到 Office 365**"。
    
    将显示 "**筛选数据**" 页。 它包含由 Office 365 对 PST 文件执行的分析生成的数据见解, 包括有关数据期限的信息。 此时, 您可以选择筛选将导入的数据, 也可以按自己的方式导入所有数据。 
    
    ![您可以裁切 PST 文件中的数据, 也可以将其全部导入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 执行下列操作之一：
    
    a. 若要修整您导入的数据, 请单击 **"是, 我想在导入前筛选它**"。
    
    有关筛选 PST 文件中的数据, 然后启动导入作业的详细分步说明, 请参阅[在将 pst 文件导入到 Office 365 时筛选数据](filter-data-when-importing-pst-files.md)。
    
    或
    
    b. 若要导入 PST 文件中的所有数据, 请单击 "**否, 我想导入所有内容",** 然后单击 "**下一步**"。
    
4. 如果选择导入所有数据, 请单击 "**导入数据**" 以启动导入作业。 
    
    导入作业的状态将显示在 "**导入**" 页上。 单击!["刷新](media/O365-MDM-Policy-RefreshIcon.gif)图标**刷新**" 以更新显示在 "**状态**" 列中的状态信息。 单击 "导入作业" 以显示 "状态弹出页面", 其中显示有关导入的每个 PST 文件的状态信息。 

## <a name="how-the-import-process-works"></a>导入过程的工作原理
  
您可以使用 "网络上载" 选项和 Office 365 导入服务将 PST 文件批量导入到用户邮箱。 网络上载是指将 PST 文件上载到 Microsoft 云中的临时存储区域。 然后, Office 365 导入服务将 PST 文件从存储区域复制到目标用户邮箱。
  
以下是将 PST 文件导入 Office 365 中的邮箱的网络上载过程的图示和说明。
  
![将 PST 文件导入到 Office 365 的网络上载过程的工作流](media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. 将**pst 导入工具和密钥下载到专用 Azure 存储位置**-第一步是下载 azure AzCopy 命令行工具和用于将 PST 文件上载到 Microsoft 云中的 Azure 存储位置的访问密钥。 您可以从 Security & 合规性中心的 "**导入**" 页面中获取这些。 密钥 (称为安全访问签名 (SAS) 密钥) 为你提供将 PST 文件上载到专用和安全 Azure 存储位置所需的权限。 此访问密钥对于您的组织是唯一的, 并且有助于防止在将 PST 文件上传到 Microsoft 云后对其进行未经授权的访问。 请注意, 将 PST 文件导入到 Office 365 不需要您的组织拥有单独的 Azure 订阅。 
    
2. 将**pst 文件上载到 Azure 存储位置**-下一步是使用 AzCopy 工具 (在第1步中下载) 将 PST 文件上载并存储在位于与 Office 365 相同的区域 Microsoft 数据中心的 Azure 存储位置中。组织位于。 若要上传它们, 您要导入到 Office 365 的 PST 文件必须位于组织中的文件共享或文件服务器中。
    
    请注意, 在将 PST 文件上载到 Azure 存储位置之后, 可以执行此可选步骤来查看 PST 文件的列表。
    
3. **创建 pst 导入映射文件**-将 pst 文件上载到 Azure 存储位置之后, 下一步是创建逗号分隔值 (CSV) 文件, 该文件指定要将 pst 文件导入到的用户邮箱, 请注意, pst 文件可以 导入到用户的主邮箱或其存档邮箱。 Office 365 导入服务将使用 CSV 文件中的信息导入 PST 文件。
    
4. **创建 pst 导入作业**-下一步是在 Security & 合规性中心的 "**导入**" 页上创建 pst 导入作业, 并提交在上一步中创建的 pst 导入映射文件。 在创建导入作业之后, Office 365 将分析 PST 文件中的数据, 并为您提供一个设置筛选器的机会, 该筛选器控制实际导入到 PST 导入映射文件中指定的邮箱的数据。 
    
5. **筛选将导入到邮箱的 PST 数据**-在创建和启动导入作业之后, Office 365 将通过标识项目的期限和 pst 文件中包含的不同邮件类型来分析 pst 文件中的数据 (安全和安全). 分析完成并准备导入数据后, 可以选择导入 PST 文件中包含的所有数据, 也可以通过设置用于控制导入数据的筛选器来裁切导入的数据。
    
6. **启动 pst 导入作业**-在开始导入作业后, Office 365 将使用 pst 导入映射文件中的信息将 pst 文件从其 Azure 存储位置导入到用户邮箱。 有关导入作业的状态信息 (包括有关要导入的每个 PST 文件的信息) 将显示在安全 & 合规性中心的 "**导入**" 页上。 导入作业完成后, 会将作业的状态设置为 "**完成**"。
  
## <a name="more-information"></a>更多信息

- 为什么要将 PST 文件导入 Office 365？
    
  - 这是将组织的存档邮件数据导入到 Office 365 的一个不错的方法。
    
  - 用户在任意设备上都可以使用数据，因为数据存储在云中。
    
  - 它通过允许您将 Office 365 合规性功能应用于您导入的 PST 文件中的数据, 帮助满足组织的合规性需求。 具体包括：
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)和[自动扩展存档](enable-unlimited-archiving.md), 以向用户提供额外的邮箱存储空间以存储您导入的数据。 
    
  - 将邮箱置于[诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)以保留您导入的数据。 
    
  - 使用 Microsoft[电子数据展示工具](search-for-content.md)搜索您导入的数据。 
    
  - 使用[Office 365 保留策略](retention-policies.md)来控制您导入的数据将保留多长时间, 以及在保留期到期后要执行的操作。 
    
  - 在[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)中搜索影响您导入的数据的与邮箱相关的事件。 
    
  - 出于合规目的将数据导入到[非活动邮箱](create-and-manage-inactive-mailboxes.md)以存档数据。 
    
  - 使用[数据丢失防护策略](data-loss-prevention-policies.md)防止敏感数据泄露到组织外部。 
  
- 下面是在步骤1中获取的共享访问签名 (sa) URL 的示例。 此示例还包含您在 AzCopy 工具中运行以将 PST 文件上载到 Office 365 的命令的语法。 请务必采取预防措施来保护 SAS URL, 就像保护密码或其他与安全相关的信息一样。

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
    
