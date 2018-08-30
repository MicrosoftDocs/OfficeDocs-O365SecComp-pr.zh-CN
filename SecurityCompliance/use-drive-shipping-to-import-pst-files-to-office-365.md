---
title: 驱动器传送用于将您的组织 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '管理员： 了解如何批量导入您的组织的 PST 文件迁移到 Office 365 邮箱将 PST 文件复制到硬盘驱动器和然后将其传送给 Microsoft。 '
ms.openlocfilehash: ebe88918b6c25e18562db7817d22fbf71f05e4c7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525319"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>驱动器传送用于将您的组织 PST 文件导入到 Office 365

**本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用 Office 365 导入服务和传送以批量导入到用户邮箱的 PST 文件的驱动器。驱动器传送意味着您的 PST 文件复制到硬盘的磁盘驱动器，然后以物理方式提供给 Microsoft 的驱动器。当 Microsoft 收到您的硬盘时，则数据中心人员将向 Microsoft 云存储区数据复制从硬盘驱动器。然后，您有机会修整实际导入到的目标邮箱通过设置控制哪些数据获取导入的筛选器的 PST 数据。开始导入作业后，导入服务从导入 PST 数据存储区到用户邮箱。使用驱动器传送到用户邮箱导入 PST 文件是一种方法将您的组织的电子邮件迁移到 Office 365。
  
下面是使用驱动器传送到 Office 365 邮箱导入 PST 文件所需的步骤：
  
[步骤 1： 下载的安全存储键和 PST 导入工具](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[步骤 2： 将 PST 文件复制到硬盘驱动器上](#step-2-copy-the-pst-files-to-the-hard-drive)

[步骤 3： 创建 PST 导入映射文件](#step-3-create-the-pst-import-mapping-file)

[步骤 4：在 Office 365 中创建 PST 导入作业](#step-4-create-a-pst-import-job-in-office-365)

[步骤 5：将硬盘驱动器寄送到 Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[步骤 6： 筛选数据，并启动 PST 导入作业](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> 您必须执行步骤 1 一次加载下的安全存储密钥和导入工具。执行这些步骤后，按照步骤 2 至步骤 6 每的次您想要附带向 Microsoft 硬盘驱动器。 
  
为经常常见问题有关使用传送到 Office 365 导入 PST 文件，请参阅[使用传送导入 PST 文件的驱动器的常见问题](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)的驱动器。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。
    
    此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：
    
  - 您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。
    
    或
    
  - 您必须是 Office 365 组织中的全局管理员。
    
    > [!TIP]
    > 请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。 
  
- 您需要存储您想要复制到硬盘上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 2 中，您将运行此文件服务器上存储或共享到硬盘上的文件夹的 PST 文件将复制的 Azure 导入导出工具 (WAImportExport.exe)。
    
- 仅为 2.5 英寸固态驱动器 (Ssd) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘支持与 Office 365 导入服务一起使用。您可以使用硬盘最多 10 TB。导入作业将处理仅第一个数据卷上的硬盘中。必须使用 NTFS 格式化数据量。当数据复制到硬盘上，您可以将其直接使用 2.5 英寸 SSD 附加或 2.5 或 3.5 英寸 SATA II/III 连接器或可以附加外部使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器。
    
    > [!IMPORTANT]
    > Office 365 导入服务不支持外部硬盘驱动器附带的内置的 USB 适配器。此外，不能使用内外部的硬盘驱动器上的大小写磁盘。请不要附带外部硬盘驱动器。 
  
- 必须使用 BitLocker 加密硬盘复制到 PST 文件。在步骤 2 中运行该 WAImportExport.exe 工具将帮助您设置 BitLocker。它还生成 BitLocker 加密密钥的 Microsoft 数据中心人员将用于访问上载到 Microsoft 云中的 Azure 存储区的 PST 文件的驱动器。
    
- 驱动器传送是通过 Microsoft 企业协议 (EA) 可用。驱动器传送不提供通过 Microsoft 产品和服务协议 (MPSA)。
    
- 每 GB 的数据 2 美元成本 PST 文件导入使用驱动器传送的 Office 365 邮箱。例如，如果附带包含 1,000 GB (1 TB) 的 PST 文件的硬盘驱动器，成本是 2,000 美元。您可以使用导入费用，合作伙伴。有关查找合作伙伴的信息，请参阅[查找您的 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
    
- 您或您的组织必须拥有 FedEx 或 DHL 帐户。 
    
  - 美国、 巴西和欧洲中的组织必须拥有 FedEx 帐户。
    
  - 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚中的组织必须拥有 DHL 帐户。
    
    Microsoft 将使用（并收费）此帐户将硬盘驱动器返还给您。 
    
- 您寄送到 Microsoft 的硬盘驱动器可能需要跨国际边界。如果出现这种情况，您要负责确保根据适用的法律导入和/或导出该硬盘驱动器及其所包含的数据。寄送硬盘驱动器之前，请联系您的顾问以验证您的驱动器和数据是否可以合法地寄送到确定的 Microsoft 数据中心。这将有助于确保该硬盘及时到达 Microsoft。
    
- 此过程涉及复制并保存的安全存储键及 BitLocker 加密密钥。请确保采取预防措施来保护这些项，如将保护密码或其他安全相关的信息。例如，您可能会将其保存到受密码保护的 Microsoft Word 文档或将其保存到加密的 USB 驱动器。请参阅有关这些项的示例的[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。 
    
- PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议的[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。 
    
- 默认情况下，可以接收的 Office 365 邮箱的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是，此限制的最大邮件接收 Office 365 中的大小为 150 MB。因此，如果导入 PST 文件包含大于 35 MB，我们将自动更改为 150 MB 的目标邮箱上*MaxReceiveSize*属性的值的导入 Office 365 服务的项。这将允许邮件 150 MB 要导入到用户邮箱。 
    
    > [!TIP]
    > 若要确定邮件接收大小为邮箱中，您可以运行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 
  
- 您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。请参阅[步骤 3： 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)的详细信息。 
    
- 在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：
    
  - 指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。 
    
  - 指定**TRUE**值在`IsArchive`参数。 
    
    请参阅[步骤 3： 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)的详细信息。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>步骤 1： 下载的安全存储键和 PST 导入工具

第一步是下载的安全存储密钥和工具，并将使用在步骤 2 到 PST 文件复制到硬盘上。
  
> [!IMPORTANT]
> 您必须使用 Azure 导入/导出工具版本 1 (WAimportExportV1) 使用的驱动器传送方法成功导入 PST 文件。不受支持版本 2 的 Azure 导入/导出工具并使用它将导致不正确准备导入作业的硬盘中。请务必从安全下载 Azure 导入/导出工具&amp;合规性中心在此步骤中的过程。 
  
1. 转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。
    
    > [!NOTE]
    > 如上文所述，您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。 
  
3. 在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。
    
4. 在导入作业向导中，为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。
    
5. 在**选择导入作业类型**页上，单击**传送硬盘驱动器到我们的物理位置之一**，然后单击**下一步**。
    
    ![单击传送到我们的物理位置创建驱动器传送导入作业之一硬盘驱动器](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在**导入数据**页上，执行以下两项操作： 
    
    ![复制的安全存储密钥并下载导入数据页上的 Azure 导入导出工具](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    答： 在步骤 2 中，单击**复制安全存储密钥**。显示存储密钥后，单击**复制到剪贴板**然后将其粘贴并将其保存到文件，以便您可以更高版本访问它。
    
    b.在步骤 3，**下载 Azure 导入/导出工具**以下载并安装 Azure 导入/导出 （版本 1） 工具。
    
    - 在弹出窗口中，单击**保存** \> **另存为**本地计算机上将 WaImportExportV1.zip 文件保存到文件夹。 
    
    - 提取 WaImportExportV1.zip 文件。
    
7. 单击**取消**以关闭向导。 
    
    将转至安全中的**导入**页后&amp;合规性中心时您在步骤 4 中创建导入作业。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>步骤 2： 将 PST 文件复制到硬盘驱动器上

下一步是使用 WAImportExport.exe 工具以将 PST 文件复制到硬盘上。此工具加密的硬盘中使用 BitLocker、 将 Pst 复制到硬盘上，并创建日志文件，用于存储有关复制过程的信息。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。 
  
> [!IMPORTANT]
> 运行 WAImportExport.exe 工具硬盘驱动器上的第一个时间后，您必须使用不同的语法每个时间之后。此过程可将 PST 文件复制到硬盘上的步骤 4 中介绍了此语法。 
  
1. 在您的本地计算机上打开命令提示符。
    
    > [!TIP]
    > 如果您以管理员身份运行命令提示符（打开命令提示符时选择“以管理员身份运行”），将在命令提示符窗口中显示错误消息。这可以帮助您解决运行 WAImportExport.exe 工具时出现的问题。 
  
2. 转到您在步骤 1 中安装 WAImportExport.exe 工具的目录。
    
3. 您首次使用 WAImportExport.exe 将 PST 文件复制到硬盘驱动器时，请运行以下命令。

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    下表描述了各个参数及其所需值。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |指定日志文件的名称。此文件保存到 WAImportExport.exe 工具所在的同一文件夹中。您寄送到 Microsoft 的每个硬盘驱动器必须有一个日志文件。每次您运行 WAImportTool.exe 将 PST 文件复制到硬盘驱动器时，相关信息将追加到该驱动器的日志文件中。 
  <br/> 与在步骤 4 中创建的导入作业相关联的硬盘中并将 PST 文件上载到 Microsoft 云中的 Azure 存储区，Microsoft 数据中心人员将日志文件中使用的信息。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |连接到本地计算机时，请指定硬盘驱动器的驱动器号。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |指定复制会话的名称。会话定义为每次运行 WAImportExport.exe 工具将文件复制到硬盘驱动器。PST 文件复制到使用此参数所指定的会话名称命名的文件夹中。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |组织中的包含将在会话过程中复制的 PST 文件中指定源目录。请务必包围双引号与此参数的值 ("")。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |在其中将上载 Pst Microsoft 云中的 Azure 存储区中指定的目标目录。您必须使用值`ingestiondata/`。请务必包围双引号与此参数的值 ("")。<br/> 或者，也可以添加到此参数的值的其他文件路径。例如，您可以使用源目录 （转换为 URL 格式） 的硬盘，后者中指定的文件路径`/srcdir:`参数。例如，`\\FILESERVER01\PSTs`更改为`FILESERVER01/PSTs`。在这种情况下，您仍必须包括`ingestiondata`中的文件路径。因此，在本例中为的值`/dstdir:`参数应为`"ingestiondata/FILESERVER01/PSTs"`。<br/> 要添加其他文件路径的一个原因是如果必须具有相同的文件名的 Pst 文件。  <br/> > [!NOTE]> PST 文件上载到 Azure 存储区域后的命名空间如果包含可选的路径名，将包括路径名和 PST 文件中; 的名称例如， `FILESERVER01/PSTs/annb.pst`。如果不包括路径名，命名空间是仅 PST 文件名;例如`annb.pst`。           | `/dstdir:"ingestiondata/"` <br/> 或  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |步骤 1 中指定您获取的存储帐户键。请务必包围双引号与此参数的值 ("")。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此开关对硬盘驱动器启用 BitLocker。首次运行 WAImportExport.exe 工具时，此参数是必需的。  <br/> BitLocker 加密密钥复制到日志文件，如果您使用所创建的日志文件`/logfile:`参数。如前所述，如果在日志文件将保存到 WAImportExport.exe 工具所在的同一文件夹中。<br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |此可选参数指定要用于保存日志文件的文件夹。如果未指定，日志文件到 WAImportExport.exe 工具所在的同一文件夹是保存。请务必包围双引号与此参数的值 ("")。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    以下是对每个参数使用实际值的 WAImportExport.exe 工具的语法示例：
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    运行该命令后，显示的状态消息会显示将 PST 文件复制到硬盘驱动器的进度。最终状态消息显示已成功复制的文件总数。 
    
4. 以后每次运行 WAImportExport.ext 工具将 PST 文件复制到同一个硬盘驱动器时运行此命令。

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    下面是运行后续会话将 PST 文件复制到同一个硬盘驱动器的语法示例。  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>步骤 3： 创建 PST 导入映射文件

导入服务在 PST 导入映射文件中，这是一个以逗号分隔值 (CSV) 文件，指定哪些用户邮箱 PST Microsoft 数据中心人员上载到 Azure 存储区的硬盘的 PST 文件后，将使用的信息文件将导入到。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。
  
1. [下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. 打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个 PST 文件复制到硬盘上，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。

    > [!NOTE]
    > 不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。 
  
3. 使用下表中的信息来填充附有所需信息的 CSV 文件。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> | PST 文件将被复制到硬盘发货时向 Microsoft Azure 存储区域中指定的文件夹位置。  <br/>  CSV 文件中的此列中添加的内容取决于什么中指定的`/dstdir:`上一步骤中的参数。  <br/>  如果您使用`/dstdir:"ingestiondata/"`，然后将此参数留空 CSV 文件中。  <br/>  如果您包含的值为可选路径名`/dstdir:`参数 (如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`，然后为 CSV 文件中的此参数中使用的路径名 （不包括"ingestiondata"）。此参数的值是区分大小写。<br/>  两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。将此参数留空，或指定只是可选的路径名。<br/> > [!IMPORTANT]> 文件路径名称案例必须相同中指定的大小写`/dstdir:`上一步骤中的参数。例如，如果您使用`"ingestiondata/FILESERVER01/PSTs"`的子文件夹名称在上一步骤中，但然后使用`fileserver01/psts`的`FilePath`CSV 文件中的参数，将会失败的 PST 文件导入。请务必在这两种情况下使用相同的大小写。           |（保留为空白）  <br/> 或  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。<br/> > [!IMPORTANT]> 大小写的 CSV 文件中的 PST 文件名称必须与已上载到在步骤 2 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定的邮箱的 PST 文件导入到的电子邮件地址。请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入到公用文件夹。<br/> 若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox<identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid。           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：<br/> **FALSE**PST 文件导入到用户的主邮箱中。  <br/> **TRUE**将 PST 文件导入到用户的存档邮箱。这假定[已启用用户的存档邮箱](enable-archive-mailboxes.md)。如果将此参数设置为`TRUE`和用户的存档邮箱未启用，为该用户导入将失败。请注意，如果导入失败的一个用户 (因为其归档未启用，此属性设置为`TRUE`)，不会影响导入作业中的其他用户。<br/>  如果将此参数留空，PST 文件导入到用户的主邮箱。  <br/> **注意：** PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定`TRUE`为此参数指定用户的内部部署邮箱的电子邮件地址和`Mailbox`参数。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。  <br/>  如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。  <br/>  如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为文件夹*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到一个名为**ImportedPst**文件夹。此文件夹将位于收件箱文件夹相同级别的用户的邮箱。<br/> |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。<br/> 有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/> > [!NOTE]> 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。           |（保留为空白）  <br/> 或  <br/>  `932`（这是代码页标识符的 ANSI/OEM 日语）  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>步骤 4：在 Office 365 中创建 PST 导入作业

下一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 3 中创建的 PST 导入映射文件。创建新的作业后，导入服务将使用的信息映射文件中的 PST 文件从硬盘复制到 Azure 存储区，并创建并启动导入作业后，PST 文件导入到指定的用户邮箱。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控**，然后单击**导入**。
    
3. 在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。
    
    > [!NOTE]
    > 如上文所述，您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。 
  
4. 为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。
    
5. 在**选择导入作业类型**页上，单击**传送硬盘驱动器到我们的物理位置之一**，然后单击**下一步**。
    
    ![单击传送到我们的物理位置创建驱动器传送导入作业之一硬盘驱动器](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在步骤 6 中，单击和**我已准备好我硬盘驱动器并有权访问所需的驱动器日志文件****有访问权限的映射文件**复选框，，然后单击**下一步**。
    
    ![单击在步骤 6 中的两个复选框](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. 在**选择驱动器文件**页上，单击**选择驱动器文件**，，然后转到 WAImportExport.exe 工具所在的同一文件夹。在步骤 2 中创建的日志文件将被复制到此文件夹中。
    
    ![单击选择驱动器文件以提交运行 WAImportExport.exe 工具时创建的日志文件](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. 选择的日志文件;例如， `PSTHDD1.jrn`。
    
    > [!TIP]
    > 当您在步骤 2 中运行 WAImportExport.exe 工具时，日志文件的名称已指定`/j:`参数。 
  
9. 驱动器文件的名称出现在**文件名称**下后，单击**验证**检查驱动器文件中的错误。 
    
    ![单击验证来验证所选驱动器文件](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    驱动器文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，包含有关文件失败的原因的信息的错误消息。 
    
    > [!NOTE]
    > 您必须添加并验证每个硬盘向 Microsoft 附带的日志文件。 
  
10. 添加和验证您将向 Microsoft 提供的每个硬盘的日志文件之后, 单击**下一步**。
    
11. 单击![添加图标](media/ITPro-EAC-AddIcon.gif)**选择映射文件**以提交您在步骤 3 中创建的 PST 导入映射文件。 
    
    ![单击选择映射文件以提交您创建的导入作业的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. 后的 CSV 名称文件显示在**映射文件名称**下，单击**验证**检查 CSV 文件中的错误。 
    
    ![单击验证检查 CSV 文件中的错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，失败的文件中的各行的错误消息。 
    
13. 在成功验证 PST 映射文件后，单击**下一步**。
    
14. 在**提供联系信息**页上，在相应的框中键入您的联系人信息。 
    
    请注意，将显示您将提供给您硬盘 Microsoft 位置的地址。此地址是自动生成基于 Office 365 数据中心位置。将此地址复制到文件或屏幕截图。
    
15. 阅读条款和条件文档，单击复选框，然后单击**保存**以提交导入作业。 
    
    导入作业已成功创建，会显示的状态页，其中说明传送过程的驱动器的下一个步骤。
    
16. 在**导入**页上单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)到**刷新**显示传送导入作业的导入作业列表中的新驱动器。请注意，将状态设置为**等待跟踪号码**。您还可以单击导入作业以显示状态弹出页，其中包含有关导入作业的详细的信息。
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>步骤 5：将硬盘驱动器寄送到 Microsoft

下一步是附带的硬盘中向 Microsoft，然后向物料过程提供跟踪号和返回发货驱动器传送作业的信息。驱动器接收由 Microsoft 后，将花费多之间 7 和 10 个工作日的数据中心工作人员将 PST 文件上传到您的组织的 Azure 存储区。
  
> [!NOTE]
> 如果您没有提供的跟踪数量和返回物料过程信息的创建导入作业 14 天内，将过期导入作业。如果发生这种情况，您将需要创建新的驱动器传送导入作业 (请参阅[步骤 4： 在 Office 365 中创建的 PST 导入作业](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) 和重新提交驱动器文件和 PST 导入映射文件。 
  
### <a name="ship-the-hard-drive"></a>寄送硬盘驱动器

将硬盘驱动器寄送到 Microsoft 时，请记住以下几点：
  
- 不附带的 SATA 到 USB 适配器;您只需附带的硬盘中。
    
- 妥善打包硬盘驱动器，例如，使用防静电袋或泡沫包装。
    
- 使用您所选择的交付承运人将硬盘驱动器寄送到 Microsoft。
    
- 附带的硬盘中为您在步骤 4 中创建导入作业时所显示的 Microsoft 位置的地址。请务必传送到地址中包含"Office 365 导入服务"。
    
- 寄送硬盘驱动器之后，请务必记下交付承运人的名称和跟踪号。您将在下一步中提供这些信息。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>输入跟踪号和其他寄送信息

将硬盘驱动器寄送到 Microsoft 后，在导入服务页上完成以下过程。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左窗格中，单击**数据管理**，然后单击**导入**。
    
3. 在**导入**页上，单击适用于您想要输入的跟踪号驱动器货运作业。 
    
4. 在状态弹出页，单击**Enter 跟踪号**。
    
5. 请提供下列发货信息：
    
1. **传递运营商**键入用于附带的硬盘中向 Microsoft 传递运营商的名称。 
    
2. **跟踪数**键入硬盘运送跟踪数。 
    
3. **返回运营商帐号**键入**返回运营商**下列出的运营商贵组织的帐户数。Microsoft 将使用 （和容量） 附带发回给您的硬盘空间此帐户。注意在美国和欧洲，组织必须具有 FedEx 的帐户。在亚洲和世界各地的其余部分的组织必须具有 DHL 的帐户。
    
6. 单击**保存**以保存的导入作业此信息。 
    
    在**导入**页上单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新为驱动器传送导入作业的信息。请注意，状态现在设置为**驱动器在传输过程中**。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步骤 6： 筛选数据，并启动 PST 导入作业

您的硬盘接收由 Microsoft 后，**导入**页上的导入作业的状态将更改为**驱动器收到**。数据中心人员将使用日志文件中的信息将 PST 文件上传到您的组织的 Azure 存储区。此时，状态将更改为**导入正在进行**。如前面所述，将花费多之间 7 至 10 工作日后接收硬盘上载 PST 文件。
  
PST 文件上载到 Azure 后，状态更改为**正在进行分析**。这指示的 Office 365 正在分析 PST 文件中的数据 （以安全方式） 来标识的项目和 PST 文件中包含的其他消息类型的期限。在完成分析，并且已准备好导入数据，导入作业的状态将更改为**完成分析**。此时，您可以选择要导入 PST 文件中包含的所有数据，或可修剪通过设置控制哪些数据获取导入的筛选器导入的数据。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左窗格中，单击**数据调控** > **导入**。
    
3. 在**导入**页上，单击您在步骤 4 中创建的导入作业**已准备好导入到 Office 365** 。 
    
    ![单击您创建的导入作业旁边导入到 Office 365 准备](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    飞出页将显示有关 PST 文件的信息以及其他信息导入作业。
    
4. 单击**导入到 Office 365**。
    
5. 显示**筛选数据**页。它包含生成 Office 365，包括有关数据的期限对 PST 文件执行分析数据见解。此时，您可以选择要筛选的数据将导入或导入原样的所有数据。 
    
    ![您可以修整 PST 文件中的数据或导入的所有](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 执行以下操作之一：
    
    答： 来裁切导入的数据，请单击**是，我希望筛选其之前导入**。
    
    有关筛选 PST 文件中的数据，然后启动导入作业的详细分步说明，请参阅[筛选器数据导入 PST 文件迁移到 Office 365 时](filter-data-when-importing-pst-files.md)。
    
    或
    
    b.若要导入 PST 文件中的所有数据中,，单击**否，我想要导都入的所有内容，** 然后单击**下一步**。
    
7. 如果您选择要导入的所有数据，请单击都**导都入数据**以启动导都入作业。 
    
    在**导入**页上显示的导入作业的状态。单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新**状态**列中显示的状态信息。单击显示状态弹出页，显示状态信息正在导入每个 PST 文件导入作业。导入完成后，PST 文件导入到用户邮箱，状态将更改为**已完成**。

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>查看上载到 Office 365 的 PST 文件的列表

您可以安装和使用 Microsoft Azure 存储资源管理器 （这是一个免费的开源工具） 查看我们您上载到该文档 （通过 Microsoft 数据中心人员） 为您的组织的 Azure 存储区的 PST 文件的列表。您可以执行此操作以验证从您向 Microsoft 发送的硬盘的 PST 文件已成功上载到 Azure 存储区。
  
Microsoft Azure 存储 Explorer 正处于预览。
  
 **重要：** 不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果没有导入作业正在运行，则所有 PST 文件中的 * * ingestiondata * * 容器被删除 30 天后创建的最新的导入作业。 
  
安装 Azure 存储浏览器并连接到 Azure 存储区：
  
1. 执行以下步骤以获取您的组织共享访问签名 (SA) URL。此 URL 是 Microsoft 云的组织和 SAS 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限访问组织的 Azure 存储位置。
    
1. 转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。
    
3. 在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。
    
4. 在导入作业向导中，为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。
    
5. 在**选择导入作业类型**页上，单击**上载数据**，然后单击**下一步**。
    
6. 在步骤 2 中，单击**显示网络上载 SAS URL**。
    
7. 显示 URL 后，将其复制，并将其保存到文件。请务必将复制的完整 URL。
    
    > [!IMPORTANT]
    > 请确保采取预防措施来保护 SAS URL。这可以用于人访问您的组织的 Azure 存储区。 
  
8. 单击**取消**以关闭导入作业向导。 
    
2. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
3. 启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. 单击**使用共享的访问签名 (SA) URI 或连接字符串**，然后单击**下一步**。
    
5. 单击**使用 SAS URI**，将您获得 SAS URL 粘贴步骤 1 中到**URI**下的框中，然后单击**下一步**。
    
6. 在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。
    
    打开**ingestiondata**容器;它包含您的硬盘的 PST 文件。**Ingestiondata**容器位于**存储帐户**下\> **（SAS-Attached 服务）** \> **Blob 容器**。
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. 完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>疑难解答提示
<a name="troubleshootingtips"> </a>

- **由于错误 PST 导入 CSV 映射文件中导入作业失败时，会发生什么情况？** 如果导入作业失败由于映射文件中的错误，您无需重新附带的硬盘中向 Microsoft，以创建新的导入作业。这是因为您提交的硬盘的 PST 文件驱动器传送导入作业已经上载到您的组织的 Azure 存储区。在这种情况下，您只需要在 PST 导入 CSV 映射文件中，修复错误然后创建一个新的"网络上载"导入作业并提交修订后的 CSV 映射文件。若要创建并启动新的网络上载导入作业，请参阅[步骤 5： 在 Office 365 中创建的 PST 导入作业](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步骤 6： 筛选数据，并启动 PST 导入作业](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主题中的"使用网络上载到 Office 365 导入 PST 文件。" 
    
    > [!NOTE]
    > 为了帮助您解决 PST 导入 CSV 映射文件，使用[Azure 存储资源管理器](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具查看**ingestiondata**容器的 PST 文件从您的硬盘已上载到 Azure 存储区中的文件夹结构。映射文件错误通常致 FilePath 参数中的正确值。此参数指定在 Azure 存储区 PST 文件的位置。请参阅 FilePath 参数[步骤 3](#step-3-create-the-pst-import-mapping-file)中的表中的说明。如前所述，通过指定的 Azure 存储区中的 PST 文件的位置`/dstdir:`参数，当您在[步骤 2](#step-2-copy-the-pst-files-to-the-hard-drive)中运行该 WAImportExport.exe 工具。 
  

  
## <a name="more-information"></a>详细信息

- 驱动器传送是有效的方法来将大量存档的消息数据导入到 Office 365 利用供您的组织的合规性功能。存档数据导入到用户邮箱后，您可以：
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)，并[自动扩展存档](enable-unlimited-archiving.md)为用户提供的数据的其他邮箱存储空间。 
    
  - 将邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)保留数据。 
    
  - 使用 Microsoft[电子数据展示工具](search-for-content.md)搜索数据。 
    
  - 应用[Office 365 保留策略](retention-policies.md)以控制数据的保留多长时间，和要采取的保留期过后哪些操作。 
    
  - 搜索[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)与该数据相关的事件。 
    
  - 数据导入到存档数据，出于合规性目的的[非活动邮箱](create-and-manage-inactive-mailboxes.md)。 
    
  - 保护您的组织防止[数据丢失](data-loss-prevention-policies.md)的敏感信息。 
    
- 以下是安全存储帐户密钥和 BitLocker 加密密钥的示例。此示例还包含 WAImportExport.exe 命令的语法，运行此命令可将 PST 文件复制到硬盘驱动器。一定要采取预防措施来保护这些文件，就像保护密码或其他与安全相关的信息一样。
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```
   
- 如前所述，Office 365 导入服务启用设置 （无限期的持续时间） PST 文件导入到邮箱后保留挂起状态。这意味着*RentionHoldEnabled*属性设置为`True`，以便将不会处理分配给邮箱的保留策略。这可以通过防止删除或较旧的消息进行存档的存档策略管理的新导入的邮件的邮箱所有者时间。下面是一些用于管理此保留挂起时可采取的步骤： 
    
  - 在一段后的时间，则可以关闭保留挂起通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令。有关说明，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/p/?LinkId=544749)。
    
  - 您可以配置保留挂起，以便它已关闭，以便将来一些日期。执行此操作通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假设今天的日期是 2016 年 7 月 1，并且您希望保留保留在 30 天内已关闭，将运行以下命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此方案中，将保留*RentionHoldEnabled*属性设置为*True* 。有关详细信息，请参阅[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以更改，以便不会立即删除或移动到用户的存档邮箱均已导入的旧项目分配给邮箱的保留策略的设置。例如，您无法加长删除或存档策略分配给邮箱的保留期限。在此方案中，则会关闭邮箱保留挂起后更改保留策略的设置。有关详细信息，请参阅[Office 365 组织中邮箱的存档和删除策略设置](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。
    

  

