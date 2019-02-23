---
title: 使用驱动器传送将组织的 PST 文件导入到 Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: '对于管理员: 了解如何通过将 pst 文件复制到硬盘并将其发送到 Microsoft, 来批量将组织的 pst 文件导入到 Office 365 邮箱。 '
ms.openlocfilehash: 7a03f7b9092cf75a468f9ddad514c7508cfc006e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217292"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>使用驱动器传送将组织的 PST 文件导入到 Office 365

**本文适用于管理员。您是否尝试将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用 Office 365 导入服务和驱动器传送将 PST 文件批量导入到用户邮箱。驱动器传送意味着您将 PST 文件复制到硬盘驱动器, 然后将该驱动器实际发送到 Microsoft。当 microsoft 收到你的硬盘时, 数据中心人员会将硬盘中的数据复制到 Microsoft 云中的存储区域。然后, 您可以通过设置用于控制要导入哪些数据的筛选器来裁切实际导入到目标邮箱的 PST 数据。在您开始导入作业后, 导入服务会将 PST 数据从存储区域导入到用户邮箱。使用驱动器传送将 PST 文件导入到用户邮箱是将组织的电子邮件迁移到 Office 365 的一种方法。
  
以下是使用驱动器发货将 PST 文件导入到 Office 365 邮箱所需的步骤:
  
[步骤 1: 下载安全存储密钥和 PST 导入工具](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[步骤 2: 将 PST 文件复制到硬驱](#step-2-copy-the-pst-files-to-the-hard-drive)

[步骤 3: 创建 PST 导入映射文件](#step-3-create-the-pst-import-mapping-file)

[步骤 4：在 Office 365 中创建 PST 导入作业](#step-4-create-a-pst-import-job-in-office-365)

[步骤 5：将硬盘驱动器寄送到 Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[步骤 6: 筛选数据并启动 PST 导入作业](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> 您必须执行步骤1一次, 以加载安全存储密钥和导入工具。执行这些步骤后, 请按照步骤2到步骤6操作, 每次要向 Microsoft 发送硬盘时。 
  
有关使用驱动器发货将 PST 文件导入到 Office 365 的常见问题, 请参阅[使用 drive 航运导入 pst 文件的常见问题解答](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己添加为成员。有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "向角色组添加角色" 或 "创建角色组" 部分。
    
    此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:
    
  - 您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。
    
    或者
    
  - 您必须是 Office 365 组织中的全局管理员。
    
    > [!TIP]
    > 请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。 
  
- 您需要将您要复制的 PST 文件存储到您的组织中的文件服务器或共享文件夹中的硬盘驱动器上。在步骤2中, 将运行 Azure 导入导出工具 (waimportexport.exe), 该工具会将存储在此文件服务器或共享文件夹上的 PST 文件复制到硬盘上。
    
- 仅2.5 英寸固态驱动器 (ssd) 或2.5 或3.5 英寸 SATA II/III 内置硬盘可与 Office 365 导入服务配合使用。可以使用最大 10 TB 的硬盘驱动器。对于导入作业, 仅会处理硬盘上的第一个数据量。必须使用 NTFS 格式化数据卷。将数据复制到硬盘时, 可以使用2.5 英寸 SSD 或2.5 或3.5 英寸 SATA ii/iii 连接器直接附加它, 也可以使用外部的2.5 英寸 ssd 或2.5 或3.5 英寸 sata ii/iii USB 适配器将其连接到外部。
    
    > [!IMPORTANT]
    > 内置 USB 适配器附带的外部硬盘驱动器不受 Office 365 导入服务的支持。此外, 不能使用外部硬盘驱动器大小写中的磁盘。请勿发售外部硬盘驱动器。 
  
- 将 PST 文件复制到的硬驱必须使用 BitLocker 加密。您在步骤2中运行的 waimportexport.exe 工具将帮助您设置 BitLocker。它还会生成一个 BitLocker 加密密钥, microsoft 数据中心人员将使用它来访问驱动器, 以将 PST 文件上载到 Microsoft 云中的 Azure 存储区域。
    
- 通过 Microsoft 企业协议 (EA) 提供驱动器运输。无法通过 Microsoft 产品和服务协议 (MPSA) 获取驱动器发货。
    
- 使用驱动器传送将 PST 文件导入到 Office 365 邮箱的成本是每 GB 数据的 $2 美元。例如, 如果您发售的硬盘驱动器包含 1000 GB (1tb) 的 PST 文件, 则成本为 $2000 USD。你可以与合作伙伴合作以支付进口费用。有关查找合作伙伴的信息, 请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
    
- 您或您的组织必须拥有 FedEx 或 DHL 帐户。 
    
  - 美国、巴西和欧洲的组织必须具有 FedEx 帐户。
    
  - 东亚、东南亚、日本、日本、韩国和澳大利亚的组织必须具有 DHL 帐户。
    
    Microsoft 将使用（并收费）此帐户将硬盘驱动器返还给您。 
    
- 您寄送到 Microsoft 的硬盘驱动器可能需要跨国际边界。如果出现这种情况，您要负责确保根据适用的法律导入和/或导出该硬盘驱动器及其所包含的数据。寄送硬盘驱动器之前，请联系您的顾问以验证您的驱动器和数据是否可以合法地寄送到确定的 Microsoft 数据中心。这将有助于确保该硬盘及时到达 Microsoft。
    
- 此过程涉及复制和保存安全存储密钥和 BitLocker 加密密钥。请务必采取预防措施来保护这些密钥, 如保护密码或其他与安全相关的信息。例如, 可以将其保存到受密码保护的 Microsoft Word 文档中, 或将其保存到加密的 USB 驱动器中。有关这些项的示例, 请参阅[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。 
    
- 将 PST 文件导入到 Office 365 邮箱后, 邮箱的保留挂起设置将处于无限期的期限内打开。这意味着将不会处理分配给邮箱的保留策略, 除非您关闭保留挂起或设置关闭保留的日期。我们为什么要这么做呢？如果导入到邮箱的邮件是旧邮件, 则可能会永久删除 (清除), 因为他们的保留期已过, 因为其保留期已根据邮箱配置的保留设置而过期。将邮箱置于保留挂起状态将使邮箱所有者时间管理这些新导入的邮件, 或为您提供更改邮箱保留设置的时间。有关管理保留挂起的建议, 请参阅[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。 
    
- 默认情况下, Office 365 邮箱可以接收的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是, Office 365 中最大邮件接收大小的限制是 150 MB。因此, 如果您导入的 PST 文件中包含大于 35 MB 的项目, 则 Office 365 导入服务会将目标邮箱上的*MaxReceiveSize*属性值自动更改为 150 MB。这将允许将最大为 150 MB 的邮件导入到用户邮箱。 
    
    > [!TIP]
    > 若要标识邮箱的邮件接收大小, 可以在 Exchange Online PowerShell 中运行以下命令: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 
  
- 您可以将 PST 文件导入到 Office 365 中的非活动邮箱。为此, 请在 PST 导入映射文件的`Mailbox`参数中指定非活动邮箱的 GUID。有关详细信息, 请参阅[步骤 3: 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)。 
    
- 在 Exchange 混合部署中, 可以将 PST 文件导入到主邮箱位于本地的用户的基于云的存档邮箱。为此, 请在 PST 导入映射文件中执行以下操作:
    
  - 在`Mailbox`参数中指定用户的内部部署邮箱的电子邮件地址。 
    
  - 在`IsArchive`参数中指定**TRUE**值。 
    
    有关详细信息, 请参阅[步骤 3: 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>步骤 1: 下载安全存储密钥和 PST 导入工具

第一步是下载安全存储密钥和工具, 您将在步骤2中使用此工具将 PST 文件复制到硬盘驱动器。
  
> [!IMPORTANT]
> 您必须使用 Azure 导入/导出工具版本 1 (WAimportExportV1), 才能使用驱动器货运方法成功导入 PST 文件。Azure 导入/导出工具的第2版不受支持, 使用它将导致为导入作业准备硬驱时出现错误。请按照此步骤中的过程操作, 确保从安全&amp;合规中心下载 Azure 导入/导出工具。 
  
1. 转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。
    
    > [!NOTE]
    > 如前所述, 必须为您分配适当的权限以访问安全&amp;合规中心中的 "**导入**" 页。 
  
3. 在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。
    
4. 在 "导入作业向导" 中, 键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。
    
5. 在 "**选择导入作业类型**" 页上, 单击 "**将硬盘驱动器运送到我们的物理位置之一**", 然后单击 "**下一步**"。
    
    ![单击 "将硬盘驱动器运送到我们的物理位置之一", 创建驱动器运输导入作业](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在 "**导入数据**" 页上, 执行以下两项操作: 
    
    ![复制安全存储密钥并下载 "导入数据" 页上的 Azure 导入导出工具](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    在步骤2中, 单击 "**复制安全存储密钥"**。显示存储密钥后, 单击 "**复制到剪贴板**" 并将其粘贴并保存到文件中, 以便稍后对其进行访问。
    
    b. 在步骤3中,**下载 azure 导入/导出工具**以下载并安装 azure 导入/导出 (版本 1) 工具。
    
    - 在弹出窗口中, 单击 "**保存** \> **另存为**", 将 WaImportExportV1 文件保存到本地计算机上的文件夹中。 
    
    - 提取 WaImportExportV1 文件。
    
7. 单击 "**取消**" 关闭该向导。 
    
    当您在步骤4中创建导入作业时&amp; , 您将返回到安全合规性中心中的 "**导入**" 页。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>步骤 2: 将 PST 文件复制到硬驱

下一步是使用 waimportexport.exe 工具将 PST 文件复制到硬盘驱动器。此工具使用 BitLocker 对硬盘进行加密, 将 pst 复制到硬盘, 并创建一个日志文件来存储有关复制过程的信息。若要完成此步骤, PST 文件必须位于组织中的文件共享或文件服务器中。这在下面的过程中称为 "源目录"。 
  
> [!IMPORTANT]
> 在第一次运行 waimportexport.exe 工具之后, 每次运行后, 都必须使用不同的语法。此语法在此过程的步骤4中对将 PST 文件复制到硬盘驱动器的步骤4进行了说明。 
  
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
  <br/> Microsoft 数据中心人员将使用日记文件中的信息将硬驱与您在步骤4中创建的导入作业相关联, 并将 PST 文件上载到 Microsoft 云中的 Azure 存储区域。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |连接到本地计算机时，请指定硬盘驱动器的驱动器号。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |指定复制会话的名称。会话定义为每次运行 WAImportExport.exe 工具将文件复制到硬盘驱动器。PST 文件复制到使用此参数所指定的会话名称命名的文件夹中。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |指定组织中包含将在会话期间复制的 PST 文件的源目录。请务必将此参数的值括在双引号 ("") 中。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |指定将在其中上载 pst 的 Microsoft 云中 Azure 存储区域中的目标目录。必须使用值`ingestiondata/`。请务必将此参数的值括在双引号 ("") 中。<br/> (可选) 还可以向此参数的值添加其他文件路径。例如, 您可以使用硬驱 (转换为 URL 格式) 的源目录的文件路径 (在`/srcdir:`参数中指定)。例如, " `\\FILESERVER01\PSTs` " 更改为`FILESERVER01/PSTs`""。在这种情况下, 您仍`ingestiondata`必须包含在文件路径中。因此, 在此示例中, `/dstdir:`参数的值为。 `"ingestiondata/FILESERVER01/PSTs"`<br/> 添加其他文件路径的一个原因是您的 pst 文件具有相同的文件名。  <br/> > [!NOTE]> 如果包括可选的路径名, 则将 pst 文件上传到 Azure 存储区域后的命名空间将包括该 pst 文件的路径名和名称;例如, `FILESERVER01/PSTs/annb.pst`。如果不包含 pathname, 则命名空间仅为 PST 文件名;例如`annb.pst`。           | `/dstdir:"ingestiondata/"` <br/> 或者  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |指定您在步骤1中获取的存储帐户密钥。请务必将此参数的值括在双引号 ("") 中。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此开关对硬盘驱动器启用 BitLocker。首次运行 WAImportExport.exe 工具时，此参数是必需的。  <br/> 如果使用`/logfile:`参数, 则将 BitLocker 加密密钥复制到日志文件和创建的日志文件中。如前所述, 日记文件保存到 waimportexport.exe 工具所在的同一文件夹中。<br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |此可选参数指定要将日志文件保存到的文件夹。如果未指定, 则会将日志文件保存到 waimportexport.exe 工具所在的同一文件夹中。请务必将此参数的值括在双引号 ("") 中。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
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

## <a name="step-3-create-the-pst-import-mapping-file"></a>步骤 3: 创建 PST 导入映射文件

在 Microsoft 数据中心人员将 pst 文件从硬盘上传到 Azure 存储区域后, 导入服务将使用 PST 导入映射文件中的信息, 该文件是一个逗号分隔值 (CSV) 文件, 该文件指定 pst 的用户邮箱文件将导入到。创建 PST 导入作业时, 将在下一步中提交此 CSV 文件。
  
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

    CSV 文件的第一行 (即标题行) 列出了 pst 导入服务将用于将 pst 文件导入到用户邮箱的参数。每个参数名称之间用逗号分隔。标题行下的每一行表示用于将 PST 文件导入到特定邮箱的参数值。对于复制到硬驱的每个 PST 文件, 您都需要一行。请务必将映射文件中的占位符数据替换为实际数据。

    > [!NOTE]
    > 不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。 
  
3. 使用下表中的信息来填充附有所需信息的 CSV 文件。
    
    |**参数**|**说明**|**示例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定要将数据导入到的 Office 365 服务。若要将 PST 文件导入到用户`Exchange`邮箱, 请使用。<br/> | `Exchange` <br/> |
    | `FilePath` <br/> | 指定在将硬盘驱动器发送到 Microsoft 时, 在 Azure 存储区域中将 PST 文件复制到的文件夹位置。  <br/>  您在 CSV 文件的此列中添加的内容取决于您在中为上`/dstdir:`一步中的参数指定的内容。  <br/>  如果使用`/dstdir:"ingestiondata/"`的是, 则在 CSV 文件中将此参数留空。  <br/>  如果包含`/dstdir:`参数值的可选路径名 (例如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`, 则在 CSV 文件中对此参数使用该路径名 (不包括 "ingestiondata")。此参数的值区分大小写。<br/>  无论采用哪种方式, 都*不要*在`FilePath`参数的值中包含 "ingestiondata"。将此参数留空或仅指定可选路径名。<br/> > [!IMPORTANT]> 文件路径名称的大小写必须与您在上一步中的`/dstdir:`参数中指定的大小写相同。例如, 如果您在上`"ingestiondata/FILESERVER01/PSTs"`一步中使用了子文件夹名称, 但随后在`fileserver01/psts` CSV 文件`FilePath`的参数中使用, 则 PST 文件的导入将失败。请务必在两个实例中使用相同的大小写。           |（保留为空白）  <br/> 或  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |指定将导入到用户邮箱的 PST 文件的名称。此参数的值区分大小写。<br/> > [!IMPORTANT]> CSV 文件中的 pst 文件名的大小写必须与上载到步骤2中的 Azure 存储位置的 pst 文件相同。例如, 如果在 CSV 文件`annb.pst`的`Name`参数中使用, 但实际的 pst 文件的名称是`AnnB.pst`, 则该 pst 文件的导入将失败。请确保 CSV 文件中的 PST 名称使用与实际 pst 文件相同的大小写。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定将向其导入 PST 文件的邮箱的电子邮件地址。请注意, 不能指定公用文件夹, 因为 pst 导入服务不支持将 pst 文件导入到公用文件夹。<br/> 若要将 PST 文件导入到非活动邮箱, 您必须为此参数指定邮箱 GUID。若要获取此 GUID, 请在 Exchange Online 中运行以下 PowerShell 命令:`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> 在某些情况下, 可能会有多个邮箱具有相同的电子邮件地址, 其中一个邮箱是活动邮箱, 另一个邮箱处于软删除 (或非活动) 状态。在这些情况下, 您必须指定邮箱 GUID, 以唯一标识要将 PST 文件导入到的邮箱。若要获取活动邮箱的此 GUID, 请运行以下 PowerShell 命令`Get-Mailbox <identity of active mailbox> | FL Guid`:。若要获取软删除 (或非活动) 邮箱的 GUID, 请运行以下命令`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`:。           | `annb@contoso.onmicrosoft.com` <br/> 或者  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：<br/> **FALSE**将 PST 文件导入到用户的主邮箱。  <br/> **TRUE**将 PST 文件导入到用户的存档邮箱。这假定[用户的存档邮箱已启用](enable-archive-mailboxes.md)。如果将此参数设置为`TRUE`且用户的存档邮箱未启用, 则该用户的导入将失败。请注意, 如果一个用户的导入失败 (因为未启用其存档, 并且此属性设置`TRUE`为), 则导入作业中的其他用户将不会受到影响。<br/>  如果将此参数留空, 则会将 PST 文件导入到用户的主邮箱。  <br/> **注意:** 若要将 PST 文件导入到其主邮箱是本地邮箱的用户的基于云的存档邮箱, 只需`TRUE`为此参数指定, 并为该`Mailbox`参数指定用户的内部部署邮箱的电子邮件地址。  <br/> | `FALSE` <br/> 或者  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定将 PST 文件导入到的邮箱文件夹。  <br/>  如果将此参数留空, 则会将 PST 导入到位于邮箱根级别 (与 "收件箱" 文件夹和其他默认邮箱文件夹相同的级别) 的名为 "**导入**" 的新文件夹中。  <br/>  如果指定`/`, 则 PST 文件中的项目将直接导入到用户的 "收件箱" 文件夹中。  <br/>  如果指定`/<foldername>`, 则 PST 文件中的项目将被导入到名为* \<"\> *文件夹名称" 的文件夹中。例如, 如果使用`/ImportedPst`, 则会将项目导入到名为**ImportedPst**的文件夹中。此文件夹将位于与 "收件箱" 文件夹相同级别的用户邮箱中。<br/> |（保留为空白）  <br/> 或  <br/>  `/` <br/> 或者  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此可选参数指定用于以 ANSI 文件格式导入 PST 文件的代码页的数值。此参数用于从中文、日语和朝鲜语 (CJK) 组织导入 PST 文件, 这是因为这些语言通常使用双字节字符集 (DBCS) 进行字符编码。如果未使用此参数导入使用 DBCS 作为邮箱文件夹名称的语言的 PST 文件, 则在导入这些文件夹名称时通常会出现乱码。<br/> 有关要用于此参数的受支持值的列表, 请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。  <br/> > [!NOTE]> 如前所述, 这是一个可选参数, 无需将其包含在 CSV 文件中。或者, 可以将其包含在一个或多个行中, 并为其保留值为空。           |（保留为空白）  <br/> 或  <br/>  `932`(ANSI/OEM 日语的代码页标识符)  <br/> |
    | `SPFileContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPManifestContainer` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |
    | `SPSiteUrl` <br/> |对于 PST 导入，将该参数留空。   <br/> |不适用  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>步骤 4：在 Office 365 中创建 PST 导入作业

下一步是在 Office 365 中的 "导入服务" 中创建 PST 导入作业。如前面所述, 您将提交在步骤3中创建的 PST 导入映射文件。在创建新作业后, 导入服务将使用映射文件中的信息将 pst 文件从硬盘复制到 Azure 存储区域之后将 pst 文件导入到指定的用户邮箱, 并创建并启动导入作业。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在安全&amp;合规性中心的左侧窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。
    
3. 在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。
    
    > [!NOTE]
    > 如前所述, 必须为您分配适当的权限以访问安全&amp;合规中心中的 "**导入**" 页。 
  
4. 键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。
    
5. 在 "**选择导入作业类型**" 页上, 单击 "**将硬盘驱动器运送到我们的物理位置之一**", 然后单击 "**下一步**"。
    
    ![单击 "将硬盘驱动器运送到我们的物理位置之一", 创建驱动器运输导入作业](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在步骤6中, 单击 "**我已准备好硬盘", 并有权访问必要的驱动器日志文件**, 并有**权访问 "映射文件"** 复选框, 然后单击 "**下一步**"。
    
    ![单击步骤6中的两个复选框](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. 在 "**选择驱动器文件**" 页上, 单击 "**选择驱动器文件**", 然后转到 waimportexport.exe 工具所在的同一文件夹。将在步骤2中创建的日记文件复制到此文件夹。
    
    ![单击 "选择驱动器文件" 以提交运行 waimportexport.exe 工具时创建的日记文件](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. 选择日志文件;例如, `PSTHDD1.jrn`。
    
    > [!TIP]
    > 当您在步骤2中运行 waimportexport.exe 工具时, 该日记文件的名称由`/j:`参数指定。 
  
9. 在驱动器文件名下显示驱动器文件的名称**** 后, 单击 "**验证**" 以检查驱动器文件是否存在错误。 
    
    ![单击 "验证" 以验证您选择的驱动器文件](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    必须成功验证驱动器文件, 才能创建 PST 导入作业。注释成功验证后, 文件名更改为绿色。如果验证失败, 请单击 "**查看日志**" 链接。将打开一个验证错误报告, 其中包含错误消息, 其中包含有关文件失败原因的信息。 
    
    > [!NOTE]
    > 您必须为发布到 Microsoft 的每个硬盘添加和验证日记文件。 
  
10. 为你将发送到 Microsoft 的每个硬盘添加并验证日志文件后, 单击 "**下一步**"。
    
11. 单击!["添加](media/ITPro-EAC-AddIcon.gif)图标" "**选择映射文件**" 以提交您在步骤3中创建的 PST 导入映射文件。 
    
    ![单击 "选择映射文件" 以提交为导入作业创建的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. 在 "**映射**文件名" 下显示 csv 文件的名称后, 单击 "**验证**" 以检查 CSV 文件中的错误。 
    
    ![单击 "验证" 以检查 CSV 文件是否存在错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    必须成功验证 CSV 文件, 才能创建 PST 导入作业。注释成功验证后, 文件名更改为绿色。如果验证失败, 请单击 "**查看日志**" 链接。打开验证错误报告, 并对文件中每个失败的行提供错误消息。 
    
13. 成功验证了 PST 映射文件后, 单击 "**下一步**"。
    
14. 在 "**提供联系人信息**" 页上, 在相应的框中键入您的联系人信息。 
    
    请注意, 将显示您将向其交付硬盘驱动器的 Microsoft 位置的地址。此地址是基于您的 Office 365 数据中心位置自动生成的。将此地址复制到一个文件或获取屏幕截图。
    
15. 阅读条款和条件文档, 单击复选框, 然后单击 "**保存**" 以提交导入作业。 
    
    成功创建导入作业时, 将显示一个状态页面, 说明驱动器发货过程的后续步骤。
    
16. 在 "**导入**" 页面![上,](media/O365-MDM-Policy-RefreshIcon.gif)单击 "刷新图标**刷新**" 以在导入作业列表中显示新的驱动器运输导入作业。请注意, 状态设置为 "**等待跟踪号码**"。您还可以单击 "导入作业" 以显示 "状态弹出页面", 其中包含有关导入作业的更多详细信息。
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>步骤 5：将硬盘驱动器寄送到 Microsoft

下一步是将硬盘驱动器运送到 Microsoft, 然后提供发货的跟踪号码, 并返回驱动器运输作业的发货信息。在 Microsoft 收到该驱动器后, 数据中心人员需要7到10个工作日内将 PST 文件上传到您的组织的 Azure 存储区。
  
> [!NOTE]
> 如果您在创建导入作业的14天内未提供跟踪号码并返回发货信息, 导入作业将会过期。如果发生这种情况, 您必须创建一个新的驱动器运输导入作业 (请参阅[步骤 4: 在 Office 365 中创建 PST 导入作业](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)), 然后重新提交驱动器文件和 PST 导入映射文件。 
  
### <a name="ship-the-hard-drive"></a>寄送硬盘驱动器

将硬盘驱动器寄送到 Microsoft 时，请记住以下几点：
  
- 请勿发售 SATA 到 USB 适配器;您只需运送硬盘。
    
- 妥善打包硬盘驱动器，例如，使用防静电袋或泡沫包装。
    
- 使用您所选择的交付承运人将硬盘驱动器寄送到 Microsoft。
    
- 将硬盘驱动器运送到在步骤4中创建导入作业时显示的 Microsoft 位置的地址。请务必在送货地址中添加 "Office 365 导入服务"。
    
- 寄送硬盘驱动器之后，请务必记下交付承运人的名称和跟踪号。您将在下一步中提供这些信息。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>输入跟踪号和其他寄送信息

将硬盘驱动器寄送到 Microsoft 后，在导入服务页上完成以下过程。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。
    
3. 在 "**导入**" 页上, 单击要为其输入跟踪号码的驱动器货运的作业。 
    
4. 在 "状态弹出" 页上, 单击 "**输入跟踪号**"。
    
5. 请提供下列发货信息：
    
1. **交货承运人**键入您用于将硬盘驱动器运送到 Microsoft 的传递载体的名称。 
    
2. **跟踪号码**键入硬驱发货的跟踪号码。 
    
3. **返回承运人帐号**为在 "**退货承运人**" 下列出的运营商键入您的组织的帐户号码。Microsoft 将使用 (和收费) 此帐户将你的硬盘送回给你。请注意, 美国和欧洲的组织必须具有具有 FedEx 的帐户。亚洲的组织和世界各地的组织都必须具有 DHL 的帐户。
    
6. 单击 "**保存**" 以保存导入作业的此信息。 
    
    在 "**导入**" 页![上,](media/O365-MDM-Policy-RefreshIcon.gif)单击 "刷新图标**刷新**" 以更新驱动器传送导入作业的信息。请注意, 状态现在设置为 **"在传输中的驱动器"**。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步骤 6: 筛选数据并启动 PST 导入作业

Microsoft 在收到你的硬盘后,**导入**页面上的导入作业的状态将更改为 "**已接收的驱动器**"。数据中心人员将使用日记文件中的信息将 PST 文件上传到组织的 Azure 存储区域。在这种情况下, 状态将更改为 **"正在进行导入**"。如前所述, 接收到硬盘以上载 PST 文件后, 将需要7到10个工作日。
  
将 PST 文件上传到 Azure 后, 状态将更改为**正在进行分析**。这表明 Office 365 正在分析 pst 文件中的数据 (以安全和安全的方式), 以标识这些项目的年龄和 pst 文件中包含的不同邮件类型。分析完成并准备导入数据后, 导入作业的状态将更改为 "**分析已完成**"。此时, 您可以选择导入 PST 文件中包含的所有数据, 也可以通过设置用于控制导入数据的筛选器来裁切导入的数据。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在左窗格中, 单击 "**数据调控** > **导入**"。
    
3. 在 "**导入**" 页上, 单击 "已准备好为您在步骤4中创建的导入作业**导入 Office 365** "。 
    
    ![单击您创建的导入作业旁边的 "已准备好导入到 Office 365"](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    将显示一个 "飞出" 页面, 其中包含有关 PST 文件的信息以及有关导入作业的其他信息。
    
4. 单击 "**导入到 Office 365**"。
    
5. 将显示 "**筛选数据**" 页。它包含由 Office 365 对 PST 文件执行的分析生成的数据见解, 包括有关数据期限的信息。此时, 您可以选择筛选将导入的数据, 也可以按自己的方式导入所有数据。 
    
    ![您可以裁切 PST 文件中的数据, 也可以将其全部导入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 执行下列操作之一：
    
    一. 若要修整导入的数据, 请单击 **"是, 我想在导入前筛选它**"。
    
    有关筛选 PST 文件中的数据, 然后启动导入作业的详细分步说明, 请参阅[在将 pst 文件导入到 Office 365 时筛选数据](filter-data-when-importing-pst-files.md)。
    
    或者
    
    b. 若要导入 PST 文件中的所有数据, 请单击 "**否, 我想要导入所有内容",** 然后单击 "**下一步**"。
    
7. 如果选择导入所有数据, 请单击 "**导入数据**" 以启动导入作业。 
    
    导入作业的状态将显示在 "**导入**" 页上。单击!["刷新](media/O365-MDM-Policy-RefreshIcon.gif)图标**刷新**" 以更新显示在 "**状态**" 列中的状态信息。单击 "导入作业" 以显示 "状态弹出页面", 其中显示有关导入的每个 PST 文件的状态信息。导入完成并将 PST 文件导入到用户邮箱后, 状态将更改为 "**已完成**"。

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>查看上传到 Office 365 的 PST 文件的列表

您可以安装并使用 Microsoft Azure 存储资源管理器 (它是免费的开源工具), 以查看我们将上载的 PST 文件的列表 (由 Microsoft 数据中心人员) 到您的组织的 Azure 存储区域。您可以执行此操作, 以验证发送到 Microsoft 的硬盘驱动器中的 PST 文件是否已成功上载到 Azure 存储区。
  
Microsoft Azure 存储资源管理器处于预览阶段。
  
 **重要说明:** 无法使用 Azure 存储资源管理器上传或修改 PST 文件。将 PST 文件导入到 Office 365 的唯一受支持的方法是使用 AzCopy。此外, 也不能删除已上载到 Azure blob 的 PST 文件。如果您尝试删除 PST 文件, 您将收到一条有关不具有所需权限的错误。请注意, 所有 PST 文件都将自动从 Azure 存储区域中删除。如果没有正在进行的导入作业, 则在创建最近的导入作业30天后, * * ingestiondata * * 容器中的所有 PST 文件都会被删除。 
  
若要安装 azure 存储资源管理器并连接到 Azure 存储区, 请执行以下操作:
  
1. 执行以下步骤可获取组织的共享访问签名 (SAS) URL。此 URL 是用于组织的 Microsoft 云中的 Azure 存储位置的网络 URL 和 SAS 密钥的组合。此项为你提供访问组织的 Azure 存储位置所需的权限。
    
1. 转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。 
    
2. 在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。
    
3. 在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。
    
4. 在 "导入作业向导" 中, 键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。
    
5. 在 "**选择导入作业类型**" 页上, 单击 "**上载数据**", 然后单击 "**下一步**"。
    
6. 在步骤2中, 单击 "**显示网络上载 SAS URL**"。
    
7. 显示 URL 后, 将其复制并保存到文件中。请务必复制整个 URL。
    
    > [!IMPORTANT]
    > 请务必采取预防措施来保护 SAS URL。任何人都可以使用它来访问您的组织的 Azure 存储区域。 
  
8. 单击 "**取消**" 以关闭 "导入作业向导"。 
    
2. 下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。
    
3. 启动 Microsoft Azure 存储资源管理器, 在左窗格中右键单击 "**存储帐户**", 然后单击 "**连接到 Azure 存储**"。
    
    ![右键单击 "存储帐户", 然后单击 "连接到 Azure 存储"](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. 单击 "**使用共享访问签名 (SAS) URI 或连接字符串**", 然后单击 "**下一步**"。
    
5. 单击 "**使用 sas URI**", 将您在中的步骤1中获取的 sas URL 粘贴到 " **URI**" 下的框中, 然后单击 "**下一步**"。
    
6. 在 "**连接摘要**" 页上, 您可以查看连接信息, 然后单击 "**连接**"。
    
    打开**ingestiondata**容器;它包含硬盘中的 PST 文件。**ingestiondata**容器位于**存储帐户** \> **(SAS 附加服务)** \> **Blob 容器**下。
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. 使用 Microsoft Azure 存储资源管理器完成后, 右键单击 " **ingestiondata**", 然后单击 "**分离**" 断开与 Azure 存储区域的连接。否则, 下次尝试附加时, 将会收到错误。 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a>疑难解答提示
<a name="troubleshootingtips"> </a>

- **如果由于 PST 导入 CSV 映射文件中的错误而导致导入作业失败, 会发生什么情况？** 如果导入作业由于映射文件中的错误而失败, 则无需将硬盘重新传送到 Microsoft, 即可创建新的导入作业。这是因为您为驱动器运输导入作业提交的硬盘驱动器上的 PST 文件已上传到您的组织的 Azure 存储区。在这种情况下, 只需修复 PST 导入 CSV 映射文件中的错误, 然后创建一个新的 "网络上载" 导入作业并提交修订后的 CSV 映射文件。若要创建和启动新的网络上载导入作业, 请参阅[第5步: 在 Office 365 中创建 PST 导入作业](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步骤 6: 筛选数据并启动 pst 导入作业](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主题 "使用网络上载将 pst 文件导入到 Office 365"。 
    
    > [!NOTE]
    > 若要帮助您对 pst 导入 CSV 映射文件进行故障排除, 请使用[Azure 存储资源管理器](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具在**ingestiondata**容器中查看已上载到 Azure 存储区域的硬驱中的 PST 文件的文件夹结构。映射文件错误通常是由于 FilePath 参数中的值不正确而导致的。此参数指定 PST 文件在 Azure 存储区域中的位置。请参阅[第3步](#step-3-create-the-pst-import-mapping-file)中表中的 FilePath 参数的说明。如前所述, 当您在`/dstdir:` [步骤 2](#step-2-copy-the-pst-files-to-the-hard-drive)中运行 waimportexport.exe 工具时, 由参数指定在 Azure 存储区域中 PST 文件的位置。 
  

  
## <a name="more-information"></a>更多信息

- 驱动器运输是一种将大量存档邮件数据导入到 Office 365 以利用对您的组织可用的合规性功能的有效方法。将存档数据导入到用户邮箱后, 可以执行以下操作:
    
  - 启用[存档邮箱](enable-archive-mailboxes.md)和[自动扩展存档](enable-unlimited-archiving.md)以向用户提供额外的邮箱存储空间来存储数据。 
    
  - 将邮箱置于[诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)以保留数据。 
    
  - 使用 Microsoft[电子数据展示工具](search-for-content.md)搜索数据。 
    
  - 应用[Office 365 保留策略](retention-policies.md)以控制保留数据的时间长度, 以及保留期过期后要执行的操作。 
    
  - 在[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)中搜索与此数据相关的事件。 
    
  - 出于合规目的将数据导入到[非活动邮箱](create-and-manage-inactive-mailboxes.md)以存档数据。 
    
  - 保护您的组织不受敏感信息的[数据丢失](data-loss-prevention-policies.md)。 
    
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
   
- 如前所述, Office 365 导入服务在将 PST 文件导入邮箱后, 将启用保留挂起设置 (无限期)。这意味着*RentionHoldEnabled*属性设置为`True` , 因此不会处理分配给邮箱的保留策略。这使邮箱所有者可以通过阻止删除或存档策略来删除或存档较旧的邮件来管理新导入的邮件。若要管理此保留挂起, 可以执行以下步骤: 
    
  - 在特定时间段后, 可以通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令关闭保留挂起。有关说明, 请参阅[将邮箱放在保留挂起](https://go.microsoft.com/fwlink/p/?LinkId=544749)中。
    
  - 您可以配置保留挂起, 使其在将来某个日期处于关闭状态。可以通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令来执行此操作。例如, 假定今天的日期为2016年7月1日, 并且您希望在30天内关闭保留挂起功能, 请运行以下命令: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在这种情况下, 您可以将*RentionHoldEnabled*属性设置为*True* 。有关详细信息, 请参阅[设置邮箱](https://go.microsoft.com/fwlink/p/?LinkId=150317)。
    
  - 您可以更改已分配给邮箱的保留策略的设置, 以便不会立即删除导入的旧项目, 也不会将其移动到用户的存档邮箱。例如, 您可以延长分配给邮箱的删除或存档策略的保留期限。在这种情况下, 您可以在更改保留策略的设置后关闭邮箱的保留挂起。有关详细信息, 请参阅为[Office 365 组织中的邮箱设置存档和删除策略](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。
    

  

