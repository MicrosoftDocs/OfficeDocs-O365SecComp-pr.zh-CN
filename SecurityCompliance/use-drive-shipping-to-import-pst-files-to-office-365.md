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
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="35588-103">使用驱动器传送将组织的 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="35588-103">Use drive shipping to import your organization PST files to Office 365</span></span>

<span data-ttu-id="35588-104">**本文适用于管理员。您是否尝试将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="35588-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="35588-p101">使用 Office 365 导入服务和驱动器传送将 PST 文件批量导入到用户邮箱。驱动器传送意味着您将 PST 文件复制到硬盘驱动器, 然后将该驱动器实际发送到 Microsoft。当 microsoft 收到你的硬盘时, 数据中心人员会将硬盘中的数据复制到 Microsoft 云中的存储区域。然后, 您可以通过设置用于控制要导入哪些数据的筛选器来裁切实际导入到目标邮箱的 PST 数据。在您开始导入作业后, 导入服务会将 PST 数据从存储区域导入到用户邮箱。使用驱动器传送将 PST 文件导入到用户邮箱是将组织的电子邮件迁移到 Office 365 的一种方法。</span><span class="sxs-lookup"><span data-stu-id="35588-p101">Use the Office 365 Import service and drive shipping to bulk-import PST files to user mailboxes. Drive shipping means that you copy the PST files to a hard disk drive and then physically ship the drive to Microsoft. When Microsoft receives your hard drive, data center personnel will copy the data from the hard drive to a storage area in the Microsoft cloud. Then you have the opportunity to trim the PST data that's actually imported to the target mailboxes by setting filters that control what data gets imported. After you start the import job, the Import service imports the PST data from the storage area to user mailboxes. Using drive shipping to import PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
  
<span data-ttu-id="35588-111">以下是使用驱动器发货将 PST 文件导入到 Office 365 邮箱所需的步骤:</span><span class="sxs-lookup"><span data-stu-id="35588-111">Here are the steps required to use drive shipping to import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="35588-112">步骤 1: 下载安全存储密钥和 PST 导入工具</span><span class="sxs-lookup"><span data-stu-id="35588-112">Step 1: Download the secure storage key and PST Import tool</span></span>](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[<span data-ttu-id="35588-113">步骤 2: 将 PST 文件复制到硬驱</span><span class="sxs-lookup"><span data-stu-id="35588-113">Step 2: Copy the PST files to the hard drive</span></span>](#step-2-copy-the-pst-files-to-the-hard-drive)

[<span data-ttu-id="35588-114">步骤 3: 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="35588-114">Step 3: Create the PST Import mapping file</span></span>](#step-3-create-the-pst-import-mapping-file)

[<span data-ttu-id="35588-115">步骤 4：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="35588-115">Step 4: Create a PST Import job in Office 365</span></span>](#step-4-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="35588-116">步骤 5：将硬盘驱动器寄送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="35588-116">Step 5: Ship the hard drive to Microsoft</span></span>](#step-5-ship-the-hard-drive-to-microsoft)

[<span data-ttu-id="35588-117">步骤 6: 筛选数据并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="35588-117">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> <span data-ttu-id="35588-p102">您必须执行步骤1一次, 以加载安全存储密钥和导入工具。执行这些步骤后, 请按照步骤2到步骤6操作, 每次要向 Microsoft 发送硬盘时。</span><span class="sxs-lookup"><span data-stu-id="35588-p102">You have to perform Step 1 once to down load the secure storage key and the import tool. After you perform these steps, follow Step 2 through Step 6 each time you want to ship a hard drive to Microsoft.</span></span> 
  
<span data-ttu-id="35588-120">有关使用驱动器发货将 PST 文件导入到 Office 365 的常见问题, 请参阅[使用 drive 航运导入 pst 文件的常见问题解答](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)。</span><span class="sxs-lookup"><span data-stu-id="35588-120">For frequently asked questions about using drive shipping to import PST files to Office 365, see [FAQs for using drive shipping to import PST files](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="35588-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="35588-121">Before you begin</span></span>

- <span data-ttu-id="35588-p103">您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己添加为成员。有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "向角色组添加角色" 或 "创建角色组" 部分。</span><span class="sxs-lookup"><span data-stu-id="35588-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="35588-127">此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:</span><span class="sxs-lookup"><span data-stu-id="35588-127">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="35588-p104">您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。</span><span class="sxs-lookup"><span data-stu-id="35588-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="35588-130">或者</span><span class="sxs-lookup"><span data-stu-id="35588-130">Or</span></span>
    
  - <span data-ttu-id="35588-131">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="35588-131">You have to be a global administrator in your Office 365 organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35588-p105">请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="35588-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="35588-p106">您需要将您要复制的 PST 文件存储到您的组织中的文件服务器或共享文件夹中的硬盘驱动器上。在步骤2中, 将运行 Azure 导入导出工具 (waimportexport.exe), 该工具会将存储在此文件服务器或共享文件夹上的 PST 文件复制到硬盘上。</span><span class="sxs-lookup"><span data-stu-id="35588-p106">You need to store the PST files that you want to copy to a hard drive on a file server or shared folder in your organization. In Step 2, you'll run the Azure Import Export tool (WAImportExport.exe) that will copy the PST files that are stored on this file server or shared folder to the hard drive.</span></span>
    
- <span data-ttu-id="35588-p107">仅2.5 英寸固态驱动器 (ssd) 或2.5 或3.5 英寸 SATA II/III 内置硬盘可与 Office 365 导入服务配合使用。可以使用最大 10 TB 的硬盘驱动器。对于导入作业, 仅会处理硬盘上的第一个数据量。必须使用 NTFS 格式化数据卷。将数据复制到硬盘时, 可以使用2.5 英寸 SSD 或2.5 或3.5 英寸 SATA ii/iii 连接器直接附加它, 也可以使用外部的2.5 英寸 ssd 或2.5 或3.5 英寸 sata ii/iii USB 适配器将其连接到外部。</span><span class="sxs-lookup"><span data-stu-id="35588-p107">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35588-p108">内置 USB 适配器附带的外部硬盘驱动器不受 Office 365 导入服务的支持。此外, 不能使用外部硬盘驱动器大小写中的磁盘。请勿发售外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="35588-p108">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
- <span data-ttu-id="35588-p109">将 PST 文件复制到的硬驱必须使用 BitLocker 加密。您在步骤2中运行的 waimportexport.exe 工具将帮助您设置 BitLocker。它还会生成一个 BitLocker 加密密钥, microsoft 数据中心人员将使用它来访问驱动器, 以将 PST 文件上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="35588-p109">The hard drive that you copy the PST files to must be encrypted with BitLocker. The WAImportExport.exe tool that you run in Step 2 will help you set up BitLocker. It also generates a BitLocker encryption key that Microsoft data center personnel will use to access the drive to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="35588-p110">通过 Microsoft 企业协议 (EA) 提供驱动器运输。无法通过 Microsoft 产品和服务协议 (MPSA) 获取驱动器发货。</span><span class="sxs-lookup"><span data-stu-id="35588-p110">Drive shipping is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
    
- <span data-ttu-id="35588-p111">使用驱动器传送将 PST 文件导入到 Office 365 邮箱的成本是每 GB 数据的 $2 美元。例如, 如果您发售的硬盘驱动器包含 1000 GB (1tb) 的 PST 文件, 则成本为 $2000 USD。你可以与合作伙伴合作以支付进口费用。有关查找合作伙伴的信息, 请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="35588-p111">The cost to import PST files to Office 365 mailboxes using drive shipping is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
    
- <span data-ttu-id="35588-153">您或您的组织必须拥有 FedEx 或 DHL 帐户。 </span><span class="sxs-lookup"><span data-stu-id="35588-153">You or your organization must have an account with FedEx or DHL.</span></span>
    
  - <span data-ttu-id="35588-154">美国、巴西和欧洲的组织必须具有 FedEx 帐户。</span><span class="sxs-lookup"><span data-stu-id="35588-154">Organizations in the United States, Brazil, and Europe must have FedEx accounts.</span></span>
    
  - <span data-ttu-id="35588-155">东亚、东南亚、日本、日本、韩国和澳大利亚的组织必须具有 DHL 帐户。</span><span class="sxs-lookup"><span data-stu-id="35588-155">Organizations in East Asia, Southeast Asia, Japan, Republic of Korea, and Australia must have DHL accounts.</span></span>
    
    <span data-ttu-id="35588-156">Microsoft 将使用（并收费）此帐户将硬盘驱动器返还给您。 </span><span class="sxs-lookup"><span data-stu-id="35588-156">Microsoft will use (and charge) this account to return the hard drive back to you.</span></span>
    
- <span data-ttu-id="35588-p112">您寄送到 Microsoft 的硬盘驱动器可能需要跨国际边界。如果出现这种情况，您要负责确保根据适用的法律导入和/或导出该硬盘驱动器及其所包含的数据。寄送硬盘驱动器之前，请联系您的顾问以验证您的驱动器和数据是否可以合法地寄送到确定的 Microsoft 数据中心。这将有助于确保该硬盘及时到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="35588-p112">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the identified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
    
- <span data-ttu-id="35588-p113">此过程涉及复制和保存安全存储密钥和 BitLocker 加密密钥。请务必采取预防措施来保护这些密钥, 如保护密码或其他与安全相关的信息。例如, 可以将其保存到受密码保护的 Microsoft Word 文档中, 或将其保存到加密的 USB 驱动器中。有关这些项的示例, 请参阅[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="35588-p113">This procedure involves copying and saving a secure storage key and a BitLocker encryption key. Be sure to take precautions to protect these keys like you would protect passwords or other security-related information. For example, you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for an example of these keys.</span></span> 
    
- <span data-ttu-id="35588-p114">将 PST 文件导入到 Office 365 邮箱后, 邮箱的保留挂起设置将处于无限期的期限内打开。这意味着将不会处理分配给邮箱的保留策略, 除非您关闭保留挂起或设置关闭保留的日期。我们为什么要这么做呢？如果导入到邮箱的邮件是旧邮件, 则可能会永久删除 (清除), 因为他们的保留期已过, 因为其保留期已根据邮箱配置的保留设置而过期。将邮箱置于保留挂起状态将使邮箱所有者时间管理这些新导入的邮件, 或为您提供更改邮箱保留设置的时间。有关管理保留挂起的建议, 请参阅[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="35588-p114">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="35588-p115">默认情况下, Office 365 邮箱可以接收的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是, Office 365 中最大邮件接收大小的限制是 150 MB。因此, 如果您导入的 PST 文件中包含大于 35 MB 的项目, 则 Office 365 导入服务会将目标邮箱上的*MaxReceiveSize*属性值自动更改为 150 MB。这将允许将最大为 150 MB 的邮件导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="35588-p115">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="35588-176">若要标识邮箱的邮件接收大小, 可以在 Exchange Online PowerShell 中运行以下命令: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="35588-176">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 
  
- <span data-ttu-id="35588-p116">您可以将 PST 文件导入到 Office 365 中的非活动邮箱。为此, 请在 PST 导入映射文件的`Mailbox`参数中指定非活动邮箱的 GUID。有关详细信息, 请参阅[步骤 3: 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)。</span><span class="sxs-lookup"><span data-stu-id="35588-p116">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 
    
- <span data-ttu-id="35588-p117">在 Exchange 混合部署中, 可以将 PST 文件导入到主邮箱位于本地的用户的基于云的存档邮箱。为此, 请在 PST 导入映射文件中执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="35588-p117">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="35588-182">在`Mailbox`参数中指定用户的内部部署邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="35588-182">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="35588-183">在`IsArchive`参数中指定**TRUE**值。</span><span class="sxs-lookup"><span data-stu-id="35588-183">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="35588-184">有关详细信息, 请参阅[步骤 3: 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)。</span><span class="sxs-lookup"><span data-stu-id="35588-184">See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a><span data-ttu-id="35588-185">步骤 1: 下载安全存储密钥和 PST 导入工具</span><span class="sxs-lookup"><span data-stu-id="35588-185">Step 1: Download the secure storage key and PST Import tool</span></span>

<span data-ttu-id="35588-186">第一步是下载安全存储密钥和工具, 您将在步骤2中使用此工具将 PST 文件复制到硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="35588-186">The first step is to download the secure storage key and the tool and that you will use in Step 2 to copy PST files to the hard drive.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35588-p118">您必须使用 Azure 导入/导出工具版本 1 (WAimportExportV1), 才能使用驱动器货运方法成功导入 PST 文件。Azure 导入/导出工具的第2版不受支持, 使用它将导致为导入作业准备硬驱时出现错误。请按照此步骤中的过程操作, 确保从安全&amp;合规中心下载 Azure 导入/导出工具。</span><span class="sxs-lookup"><span data-stu-id="35588-p118">You have to use Azure Import/Export tool version 1 (WAimportExportV1) to successfully import PST files by using the drive shipping method. Version 2 of the Azure Import/Export tool isn't supported and using it will result in incorrectly preparing the hard drive for the import job. Be sure to download the Azure Import/Export tool from the Security &amp; Compliance Center by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="35588-190">转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="35588-190">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="35588-191">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。</span><span class="sxs-lookup"><span data-stu-id="35588-191">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35588-192">如前所述, 必须为您分配适当的权限以访问安全&amp;合规中心中的 "**导入**" 页。</span><span class="sxs-lookup"><span data-stu-id="35588-192">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
3. <span data-ttu-id="35588-193">在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。</span><span class="sxs-lookup"><span data-stu-id="35588-193">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="35588-p119">在 "导入作业向导" 中, 键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。</span><span class="sxs-lookup"><span data-stu-id="35588-p119">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="35588-197">在 "**选择导入作业类型**" 页上, 单击 "**将硬盘驱动器运送到我们的物理位置之一**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-197">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![单击 "将硬盘驱动器运送到我们的物理位置之一", 创建驱动器运输导入作业](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="35588-199">在 "**导入数据**" 页上, 执行以下两项操作:</span><span class="sxs-lookup"><span data-stu-id="35588-199">On the **Import data** page, do the following two things:</span></span> 
    
    ![复制安全存储密钥并下载 "导入数据" 页上的 Azure 导入导出工具](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    <span data-ttu-id="35588-p120">在步骤2中, 单击 "**复制安全存储密钥"**。显示存储密钥后, 单击 "**复制到剪贴板**" 并将其粘贴并保存到文件中, 以便稍后对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="35588-p120">a. In step 2, click **Copy the secure storage key**. After the storage key is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="35588-p121">b. 在步骤3中,**下载 azure 导入/导出工具**以下载并安装 azure 导入/导出 (版本 1) 工具。</span><span class="sxs-lookup"><span data-stu-id="35588-p121">b. In step 3, **Download the Azure Import/Export tool** to download and install the Azure Import/Export (version 1) tool.</span></span>
    
    - <span data-ttu-id="35588-206">在弹出窗口中, 单击 "**保存** \> **另存为**", 将 WaImportExportV1 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35588-206">In the pop-up window, click **Save** \> **Save as** to save the WaImportExportV1.zip file to a folder on your local computer.</span></span> 
    
    - <span data-ttu-id="35588-207">提取 WaImportExportV1 文件。</span><span class="sxs-lookup"><span data-stu-id="35588-207">Extract the WaImportExportV1.zip file.</span></span>
    
7. <span data-ttu-id="35588-208">单击 "**取消**" 关闭该向导。</span><span class="sxs-lookup"><span data-stu-id="35588-208">Click **Cancel** to close the wizard.</span></span> 
    
    <span data-ttu-id="35588-209">当您在步骤4中创建导入作业时&amp; , 您将返回到安全合规性中心中的 "**导入**" 页。</span><span class="sxs-lookup"><span data-stu-id="35588-209">You'll come back to the **Import** page in the Security &amp; Compliance Center when you create the import job in Step 4.</span></span> 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a><span data-ttu-id="35588-210">步骤 2: 将 PST 文件复制到硬驱</span><span class="sxs-lookup"><span data-stu-id="35588-210">Step 2: Copy the PST files to the hard drive</span></span>

<span data-ttu-id="35588-p122">下一步是使用 waimportexport.exe 工具将 PST 文件复制到硬盘驱动器。此工具使用 BitLocker 对硬盘进行加密, 将 pst 复制到硬盘, 并创建一个日志文件来存储有关复制过程的信息。若要完成此步骤, PST 文件必须位于组织中的文件共享或文件服务器中。这在下面的过程中称为 "源目录"。</span><span class="sxs-lookup"><span data-stu-id="35588-p122">The next step is to use the WAImportExport.exe tool to copy PST files to the hard drive. This tool encrypts the hard drive with BitLocker, copies the PSTs to the hard drive, and creates a journal file that stores information about the copy process. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="35588-p123">在第一次运行 waimportexport.exe 工具之后, 每次运行后, 都必须使用不同的语法。此语法在此过程的步骤4中对将 PST 文件复制到硬盘驱动器的步骤4进行了说明。</span><span class="sxs-lookup"><span data-stu-id="35588-p123">After you run the WAImportExport.exe tool the first time for a hard drive, you have to use a different syntax each time after that. This syntax is explained in step 4 of this procedure to copy PST files to the hard drive.</span></span> 
  
1. <span data-ttu-id="35588-217">在您的本地计算机上打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="35588-217">Open a Command Prompt on your local computer.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35588-p124">如果您以管理员身份运行命令提示符（打开命令提示符时选择“以管理员身份运行”），将在命令提示符窗口中显示错误消息。这可以帮助您解决运行 WAImportExport.exe 工具时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="35588-p124">If you run the command prompt as an administrator (by selecting "Run as administrator" when you open it) error messages will be displayed in the command prompt window. This can help you troubleshoot problems running the WAImportExport.exe tool.</span></span> 
  
2. <span data-ttu-id="35588-220">转到您在步骤 1 中安装 WAImportExport.exe 工具的目录。</span><span class="sxs-lookup"><span data-stu-id="35588-220">Go to the directory where you installed the WAImportExport.exe tool in Step 1.</span></span>
    
3. <span data-ttu-id="35588-221">您首次使用 WAImportExport.exe 将 PST 文件复制到硬盘驱动器时，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="35588-221">Run the following command the first time that you use the WAImportExport.exe to copy PST files to a hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    <span data-ttu-id="35588-222">下表描述了各个参数及其所需值。</span><span class="sxs-lookup"><span data-stu-id="35588-222">The following table describes the parameters and their required values.</span></span>
    
    |<span data-ttu-id="35588-223">**参数**</span><span class="sxs-lookup"><span data-stu-id="35588-223">**Parameter**</span></span>|<span data-ttu-id="35588-224">**说明**</span><span class="sxs-lookup"><span data-stu-id="35588-224">**Description**</span></span>|<span data-ttu-id="35588-225">**示例**</span><span class="sxs-lookup"><span data-stu-id="35588-225">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/j:` <br/> |<span data-ttu-id="35588-p125">指定日志文件的名称。此文件保存到 WAImportExport.exe 工具所在的同一文件夹中。您寄送到 Microsoft 的每个硬盘驱动器必须有一个日志文件。每次您运行 WAImportTool.exe 将 PST 文件复制到硬盘驱动器时，相关信息将追加到该驱动器的日志文件中。 
</span><span class="sxs-lookup"><span data-stu-id="35588-p125">Specifies the name of the journal file. This file is saved to the same folder where the WAImportExport.exe tool is located. Each hard drive you ship to Microsoft must have one journal file. Every time you run the WAImportTool.exe to copy PST files to a hard drive, information will be appended to the journal file for that drive.</span></span>  <br/> <span data-ttu-id="35588-230">Microsoft 数据中心人员将使用日记文件中的信息将硬驱与您在步骤4中创建的导入作业相关联, 并将 PST 文件上载到 Microsoft 云中的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="35588-230">Microsoft data center personnel will use the information in the journal file to associate the hard drive with the import job that you create in Step 4, and to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |<span data-ttu-id="35588-231">连接到本地计算机时，请指定硬盘驱动器的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="35588-231">Specifies the drive letter of the hard drive when it's connected to your local computer.</span></span>  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |<span data-ttu-id="35588-p126">指定复制会话的名称。会话定义为每次运行 WAImportExport.exe 工具将文件复制到硬盘驱动器。PST 文件复制到使用此参数所指定的会话名称命名的文件夹中。 </span><span class="sxs-lookup"><span data-stu-id="35588-p126">Specifies the name of the copy session. A session is defined as each time you run the WAImportExport.exe tool to copy files to the hard drive. The PST files are copied to a folder named with the session name specified by this parameter.</span></span>  <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |<span data-ttu-id="35588-p127">指定组织中包含将在会话期间复制的 PST 文件的源目录。请务必将此参数的值括在双引号 ("") 中。</span><span class="sxs-lookup"><span data-stu-id="35588-p127">Specifies the source directory in your organization that contains the PST files that will be copied during the session. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |<span data-ttu-id="35588-p128">指定将在其中上载 pst 的 Microsoft 云中 Azure 存储区域中的目标目录。必须使用值`ingestiondata/`。请务必将此参数的值括在双引号 ("") 中。</span><span class="sxs-lookup"><span data-stu-id="35588-p128">Specifies the destination directory in the Azure storage area in the Microsoft cloud where the PSTs will be uploaded. You must use the value  `ingestiondata/`. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/> <span data-ttu-id="35588-p129">(可选) 还可以向此参数的值添加其他文件路径。例如, 您可以使用硬驱 (转换为 URL 格式) 的源目录的文件路径 (在`/srcdir:`参数中指定)。例如, " `\\FILESERVER01\PSTs` " 更改为`FILESERVER01/PSTs`""。在这种情况下, 您仍`ingestiondata`必须包含在文件路径中。因此, 在此示例中, `/dstdir:`参数的值为。 `"ingestiondata/FILESERVER01/PSTs"`</span><span class="sxs-lookup"><span data-stu-id="35588-p129">Optionally, you can also add an additional file path to the value of this parameter. For example, you can use the file path of the source directory on the hard drive (converted to a URL format) , which is specified in the  `/srcdir:` parameter. For example,  `\\FILESERVER01\PSTs` is changed to  `FILESERVER01/PSTs`. In this case, you still must include  `ingestiondata` in the file path. So in this example, the value for the  `/dstdir:` parameter would be  `"ingestiondata/FILESERVER01/PSTs"`.  </span></span><br/> <span data-ttu-id="35588-245">添加其他文件路径的一个原因是您的 pst 文件具有相同的文件名。</span><span class="sxs-lookup"><span data-stu-id="35588-245">One reason to add the additional file path is if you have PSTs files with the same filename.</span></span>  <br/> <span data-ttu-id="35588-p130">> [!NOTE]> 如果包括可选的路径名, 则将 pst 文件上传到 Azure 存储区域后的命名空间将包括该 pst 文件的路径名和名称;例如, `FILESERVER01/PSTs/annb.pst`。如果不包含 pathname, 则命名空间仅为 PST 文件名;例如`annb.pst`。</span><span class="sxs-lookup"><span data-stu-id="35588-p130">> [!NOTE]> If you include the optional pathname, the namespace for a PST file after it's uploaded to the Azure storage area will include the pathname and the name of the PST file; for example,  `FILESERVER01/PSTs/annb.pst`. If you don't include a pathname, the namespace is only the PST filename; for example  `annb.pst`.</span></span>           | `/dstdir:"ingestiondata/"` <br/> <span data-ttu-id="35588-248">或者</span><span class="sxs-lookup"><span data-stu-id="35588-248">Or</span></span>  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |<span data-ttu-id="35588-p131">指定您在步骤1中获取的存储帐户密钥。请务必将此参数的值括在双引号 ("") 中。</span><span class="sxs-lookup"><span data-stu-id="35588-p131">Specifies the storage account key that you obtained in Step 1. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此开关对硬盘驱动器启用 BitLocker。首次运行 WAImportExport.exe 工具时，此参数是必需的。  <br/> <span data-ttu-id="35588-p133">如果使用`/logfile:`参数, 则将 BitLocker 加密密钥复制到日志文件和创建的日志文件中。如前所述, 日记文件保存到 waimportexport.exe 工具所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35588-p133">The BitLocker encryption key is copied to the journal file and the log file that is created if you use the  `/logfile:` parameter. As previously explained, the journal file is saved to the same folder where the WAImportExport.exe tool is located.  </span></span><br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |<span data-ttu-id="35588-p134">此可选参数指定要将日志文件保存到的文件夹。如果未指定, 则会将日志文件保存到 waimportexport.exe 工具所在的同一文件夹中。请务必将此参数的值括在双引号 ("") 中。</span><span class="sxs-lookup"><span data-stu-id="35588-p134">This optional parameter specifies a folder to save log files to. If not specified, the log files are save to the same folder where the WAImportExport.exe tool is located. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    <span data-ttu-id="35588-258">以下是对每个参数使用实际值的 WAImportExport.exe 工具的语法示例：</span><span class="sxs-lookup"><span data-stu-id="35588-258">Here's an example of the syntax for the WAImportExport.exe tool using actual values for each parameter:</span></span>
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    <span data-ttu-id="35588-p135">运行该命令后，显示的状态消息会显示将 PST 文件复制到硬盘驱动器的进度。最终状态消息显示已成功复制的文件总数。 </span><span class="sxs-lookup"><span data-stu-id="35588-p135">After you run the command, status messages are displayed that show the progress of copying the PST files to the hard drive. A final status message shows the total number of files that were successfully copied.</span></span>
    
4. <span data-ttu-id="35588-261">以后每次运行 WAImportExport.ext 工具将 PST 文件复制到同一个硬盘驱动器时运行此命令。</span><span class="sxs-lookup"><span data-stu-id="35588-261">Run this command each subsequent time you run the WAImportExport.ext tool to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    <span data-ttu-id="35588-262">下面是运行后续会话将 PST 文件复制到同一个硬盘驱动器的语法示例。  </span><span class="sxs-lookup"><span data-stu-id="35588-262">Here's an example of the syntax for running subsequent sessions to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a><span data-ttu-id="35588-263">步骤 3: 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="35588-263">Step 3: Create the PST Import mapping file</span></span>

<span data-ttu-id="35588-p136">在 Microsoft 数据中心人员将 pst 文件从硬盘上传到 Azure 存储区域后, 导入服务将使用 PST 导入映射文件中的信息, 该文件是一个逗号分隔值 (CSV) 文件, 该文件指定 pst 的用户邮箱文件将导入到。创建 PST 导入作业时, 将在下一步中提交此 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="35588-p136">After Microsoft data center personnel upload the PST files from the hard drive to the Azure storage area, the Import service will use the information in the PST Import mapping file, which is a comma separated value (CSV) file, that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="35588-266">[下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="35588-266">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="35588-p137">打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。</span><span class="sxs-lookup"><span data-stu-id="35588-p137">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>

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

    <span data-ttu-id="35588-p138">CSV 文件的第一行 (即标题行) 列出了 pst 导入服务将用于将 pst 文件导入到用户邮箱的参数。每个参数名称之间用逗号分隔。标题行下的每一行表示用于将 PST 文件导入到特定邮箱的参数值。对于复制到硬驱的每个 PST 文件, 您都需要一行。请务必将映射文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="35588-p138">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that was copied to the hard drive. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35588-275">不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。</span><span class="sxs-lookup"><span data-stu-id="35588-275">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="35588-276">使用下表中的信息来填充附有所需信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="35588-276">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="35588-277">**参数**</span><span class="sxs-lookup"><span data-stu-id="35588-277">**Parameter**</span></span>|<span data-ttu-id="35588-278">**说明**</span><span class="sxs-lookup"><span data-stu-id="35588-278">**Description**</span></span>|<span data-ttu-id="35588-279">**示例**</span><span class="sxs-lookup"><span data-stu-id="35588-279">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="35588-p139">指定要将数据导入到的 Office 365 服务。若要将 PST 文件导入到用户`Exchange`邮箱, 请使用。</span><span class="sxs-lookup"><span data-stu-id="35588-p139">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> | <span data-ttu-id="35588-282">指定在将硬盘驱动器发送到 Microsoft 时, 在 Azure 存储区域中将 PST 文件复制到的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="35588-282">Specifies the folder location in the Azure storage area that PST files will be copied to when the hard drive is shipped to Microsoft.</span></span>  <br/>  <span data-ttu-id="35588-283">您在 CSV 文件的此列中添加的内容取决于您在中为上`/dstdir:`一步中的参数指定的内容。</span><span class="sxs-lookup"><span data-stu-id="35588-283">What you add in this column in the CSV file depends on what you specified in for the  `/dstdir:` parameter in the previous step.</span></span>  <br/>  <span data-ttu-id="35588-284">如果使用`/dstdir:"ingestiondata/"`的是, 则在 CSV 文件中将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="35588-284">If you used  `/dstdir:"ingestiondata/"`, then leave this parameter blank in the CSV file.</span></span>  <br/>  <span data-ttu-id="35588-p140">如果包含`/dstdir:`参数值的可选路径名 (例如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`, 则在 CSV 文件中对此参数使用该路径名 (不包括 "ingestiondata")。此参数的值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="35588-p140">If you included an optional pathname for the value of the  `/dstdir:` parameter (for example,  `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, then use that pathname (not including "ingestiondata") for this parameter in the CSV file. The value for this parameter is case sensitive.  </span></span><br/>  <span data-ttu-id="35588-p141">无论采用哪种方式, 都*不要*在`FilePath`参数的值中包含 "ingestiondata"。将此参数留空或仅指定可选路径名。</span><span class="sxs-lookup"><span data-stu-id="35588-p141">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter. Leave this parameter blank or specify only the optional pathname.  </span></span><br/> <span data-ttu-id="35588-p142">> [!IMPORTANT]> 文件路径名称的大小写必须与您在上一步中的`/dstdir:`参数中指定的大小写相同。例如, 如果您在上`"ingestiondata/FILESERVER01/PSTs"`一步中使用了子文件夹名称, 但随后在`fileserver01/psts` CSV 文件`FilePath`的参数中使用, 则 PST 文件的导入将失败。请务必在两个实例中使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="35588-p142">> [!IMPORTANT]>  The case for the file path name must be the same case that you specified in the  `/dstdir:` parameter in the previous step . For example, if you used  `"ingestiondata/FILESERVER01/PSTs"` for the subfolder name in the previous step, but then used  `fileserver01/psts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="35588-292">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="35588-292">(leave blank)</span></span>  <br/> <span data-ttu-id="35588-293">或</span><span class="sxs-lookup"><span data-stu-id="35588-293">Or</span></span>  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="35588-p143">指定将导入到用户邮箱的 PST 文件的名称。此参数的值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="35588-p143">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="35588-p144">> [!IMPORTANT]> CSV 文件中的 pst 文件名的大小写必须与上载到步骤2中的 Azure 存储位置的 pst 文件相同。例如, 如果在 CSV 文件`annb.pst`的`Name`参数中使用, 但实际的 pst 文件的名称是`AnnB.pst`, 则该 pst 文件的导入将失败。请确保 CSV 文件中的 PST 名称使用与实际 pst 文件相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="35588-p144">> [!IMPORTANT]> The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="35588-p145">指定将向其导入 PST 文件的邮箱的电子邮件地址。请注意, 不能指定公用文件夹, 因为 pst 导入服务不支持将 pst 文件导入到公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="35588-p145">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="35588-p146">若要将 PST 文件导入到非活动邮箱, 您必须为此参数指定邮箱 GUID。若要获取此 GUID, 请在 Exchange Online 中运行以下 PowerShell 命令:`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span><span class="sxs-lookup"><span data-stu-id="35588-p146">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`</span></span> <br/> <span data-ttu-id="35588-p147">> [!NOTE]> 在某些情况下, 可能会有多个邮箱具有相同的电子邮件地址, 其中一个邮箱是活动邮箱, 另一个邮箱处于软删除 (或非活动) 状态。在这些情况下, 您必须指定邮箱 GUID, 以唯一标识要将 PST 文件导入到的邮箱。若要获取活动邮箱的此 GUID, 请运行以下 PowerShell 命令`Get-Mailbox <identity of active mailbox> | FL Guid`:。若要获取软删除 (或非活动) 邮箱的 GUID, 请运行以下命令`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`:。</span><span class="sxs-lookup"><span data-stu-id="35588-p147">> [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox> | FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="35588-307">或者</span><span class="sxs-lookup"><span data-stu-id="35588-307">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="35588-p148">指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="35588-p148">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="35588-310">**FALSE**将 PST 文件导入到用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="35588-310">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="35588-p149">**TRUE**将 PST 文件导入到用户的存档邮箱。这假定[用户的存档邮箱已启用](enable-archive-mailboxes.md)。如果将此参数设置为`TRUE`且用户的存档邮箱未启用, 则该用户的导入将失败。请注意, 如果一个用户的导入失败 (因为未启用其存档, 并且此属性设置`TRUE`为), 则导入作业中的其他用户将不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="35588-p149">**TRUE** Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="35588-315">如果将此参数留空, 则会将 PST 文件导入到用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="35588-315">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="35588-316">**注意:** 若要将 PST 文件导入到其主邮箱是本地邮箱的用户的基于云的存档邮箱, 只需`TRUE`为此参数指定, 并为该`Mailbox`参数指定用户的内部部署邮箱的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="35588-316">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="35588-317">或者</span><span class="sxs-lookup"><span data-stu-id="35588-317">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="35588-318">指定将 PST 文件导入到的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="35588-318">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="35588-319">如果将此参数留空, 则会将 PST 导入到位于邮箱根级别 (与 "收件箱" 文件夹和其他默认邮箱文件夹相同的级别) 的名为 "**导入**" 的新文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35588-319">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="35588-320">如果指定`/`, 则 PST 文件中的项目将直接导入到用户的 "收件箱" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35588-320">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="35588-p150">如果指定`/<foldername>`, 则 PST 文件中的项目将被导入到名为\* \<"\> \*文件夹名称" 的文件夹中。例如, 如果使用`/ImportedPst`, 则会将项目导入到名为**ImportedPst**的文件夹中。此文件夹将位于与 "收件箱" 文件夹相同级别的用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="35588-p150">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/> |<span data-ttu-id="35588-324">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="35588-324">(leave blank)</span></span>  <br/> <span data-ttu-id="35588-325">或</span><span class="sxs-lookup"><span data-stu-id="35588-325">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="35588-326">或者</span><span class="sxs-lookup"><span data-stu-id="35588-326">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="35588-p151">此可选参数指定用于以 ANSI 文件格式导入 PST 文件的代码页的数值。此参数用于从中文、日语和朝鲜语 (CJK) 组织导入 PST 文件, 这是因为这些语言通常使用双字节字符集 (DBCS) 进行字符编码。如果未使用此参数导入使用 DBCS 作为邮箱文件夹名称的语言的 PST 文件, 则在导入这些文件夹名称时通常会出现乱码。</span><span class="sxs-lookup"><span data-stu-id="35588-p151">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/> <span data-ttu-id="35588-330">有关要用于此参数的受支持值的列表, 请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。</span><span class="sxs-lookup"><span data-stu-id="35588-330">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <span data-ttu-id="35588-p152">> [!NOTE]> 如前所述, 这是一个可选参数, 无需将其包含在 CSV 文件中。或者, 可以将其包含在一个或多个行中, 并为其保留值为空。</span><span class="sxs-lookup"><span data-stu-id="35588-p152">> [!NOTE]> As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="35588-333">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="35588-333">(leave blank)</span></span>  <br/> <span data-ttu-id="35588-334">或</span><span class="sxs-lookup"><span data-stu-id="35588-334">Or</span></span>  <br/>  <span data-ttu-id="35588-335">`932`(ANSI/OEM 日语的代码页标识符)</span><span class="sxs-lookup"><span data-stu-id="35588-335">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="35588-336">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="35588-336">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="35588-337">不适用</span><span class="sxs-lookup"><span data-stu-id="35588-337">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="35588-338">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="35588-338">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="35588-339">不适用</span><span class="sxs-lookup"><span data-stu-id="35588-339">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="35588-340">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="35588-340">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="35588-341">不适用</span><span class="sxs-lookup"><span data-stu-id="35588-341">Not applicable</span></span>  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="35588-342">步骤 4：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="35588-342">Step 4: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="35588-p153">下一步是在 Office 365 中的 "导入服务" 中创建 PST 导入作业。如前面所述, 您将提交在步骤3中创建的 PST 导入映射文件。在创建新作业后, 导入服务将使用映射文件中的信息将 pst 文件从硬盘复制到 Azure 存储区域之后将 pst 文件导入到指定的用户邮箱, 并创建并启动导入作业。</span><span class="sxs-lookup"><span data-stu-id="35588-p153">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 3. After you create the new job, the Import service will use the information in the mapping file to import the PST files to the specified user mailbox after the PST files are copied from the hard drive to the Azure storage area and you create and start the import job.</span></span>
  
1. <span data-ttu-id="35588-346">转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="35588-346">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="35588-347">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="35588-347">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="35588-348">在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。</span><span class="sxs-lookup"><span data-stu-id="35588-348">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35588-349">如前所述, 必须为您分配适当的权限以访问安全&amp;合规中心中的 "**导入**" 页。</span><span class="sxs-lookup"><span data-stu-id="35588-349">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
4. <span data-ttu-id="35588-p154">键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。</span><span class="sxs-lookup"><span data-stu-id="35588-p154">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="35588-353">在 "**选择导入作业类型**" 页上, 单击 "**将硬盘驱动器运送到我们的物理位置之一**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-353">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![单击 "将硬盘驱动器运送到我们的物理位置之一", 创建驱动器运输导入作业](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="35588-355">在步骤6中, 单击 "**我已准备好硬盘", 并有权访问必要的驱动器日志文件**, 并有**权访问 "映射文件"** 复选框, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-355">In step 6, click the **I've prepared my hard drives and have access to the necessary drive journal files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![单击步骤6中的两个复选框](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. <span data-ttu-id="35588-p155">在 "**选择驱动器文件**" 页上, 单击 "**选择驱动器文件**", 然后转到 waimportexport.exe 工具所在的同一文件夹。将在步骤2中创建的日记文件复制到此文件夹。</span><span class="sxs-lookup"><span data-stu-id="35588-p155">On the **Select the drive file** page, click **Select drive file**, and then go to the same folder where the WAImportExport.exe tool is located. The journal file that was created in Step 2 was copied to this folder.</span></span>
    
    ![单击 "选择驱动器文件" 以提交运行 waimportexport.exe 工具时创建的日记文件](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. <span data-ttu-id="35588-360">选择日志文件;例如, `PSTHDD1.jrn`。</span><span class="sxs-lookup"><span data-stu-id="35588-360">Select the journal file; for example, `PSTHDD1.jrn`.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="35588-361">当您在步骤2中运行 waimportexport.exe 工具时, 该日记文件的名称由`/j:`参数指定。</span><span class="sxs-lookup"><span data-stu-id="35588-361">When you ran the WAImportExport.exe tool in Step 2, the name of the journal file was specified by the  `/j:` parameter.</span></span> 
  
9. <span data-ttu-id="35588-362">在驱动器文件名下显示驱动器文件的名称\*\*\*\* 后, 单击 "**验证**" 以检查驱动器文件是否存在错误。</span><span class="sxs-lookup"><span data-stu-id="35588-362">After the name of the drive file appears under **Drive file name**, click **Validate** to check your drive file for errors.</span></span> 
    
    ![单击 "验证" 以验证您选择的驱动器文件](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    <span data-ttu-id="35588-p156">必须成功验证驱动器文件, 才能创建 PST 导入作业。注释成功验证后, 文件名更改为绿色。如果验证失败, 请单击 "**查看日志**" 链接。将打开一个验证错误报告, 其中包含错误消息, 其中包含有关文件失败原因的信息。</span><span class="sxs-lookup"><span data-stu-id="35588-p156">The drive file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message with information about why the file failed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35588-368">您必须为发布到 Microsoft 的每个硬盘添加和验证日记文件。</span><span class="sxs-lookup"><span data-stu-id="35588-368">You must add and validate a journal file for each hard drive you ship to Microsoft.</span></span> 
  
10. <span data-ttu-id="35588-369">为你将发送到 Microsoft 的每个硬盘添加并验证日志文件后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-369">After adding and validating a journal file for each hard drive that you'll ship to Microsoft, click **Next**.</span></span>
    
11. <span data-ttu-id="35588-370">单击!["添加](media/ITPro-EAC-AddIcon.gif)图标" "**选择映射文件**" 以提交您在步骤3中创建的 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="35588-370">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Select mapping file** to submit the PST Import mapping file that you created in Step 3.</span></span> 
    
    ![单击 "选择映射文件" 以提交为导入作业创建的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. <span data-ttu-id="35588-372">在 "**映射**文件名" 下显示 csv 文件的名称后, 单击 "**验证**" 以检查 CSV 文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="35588-372">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![单击 "验证" 以检查 CSV 文件是否存在错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="35588-p157">必须成功验证 CSV 文件, 才能创建 PST 导入作业。注释成功验证后, 文件名更改为绿色。如果验证失败, 请单击 "**查看日志**" 链接。打开验证错误报告, 并对文件中每个失败的行提供错误消息。</span><span class="sxs-lookup"><span data-stu-id="35588-p157">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
13. <span data-ttu-id="35588-378">成功验证了 PST 映射文件后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-378">After the PST mapping file is successfully validated, click **Next**.</span></span>
    
14. <span data-ttu-id="35588-379">在 "**提供联系人信息**" 页上, 在相应的框中键入您的联系人信息。</span><span class="sxs-lookup"><span data-stu-id="35588-379">On the **Provide contact information** page, type your contact information in the applicable boxes.</span></span> 
    
    <span data-ttu-id="35588-p158">请注意, 将显示您将向其交付硬盘驱动器的 Microsoft 位置的地址。此地址是基于您的 Office 365 数据中心位置自动生成的。将此地址复制到一个文件或获取屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="35588-p158">Note that the address for the Microsoft location that you will ship your hard drives to is displayed. This address is auto-generated based on your Office 365 data center location. Copy this address to a file or take a screenshot.</span></span>
    
15. <span data-ttu-id="35588-383">阅读条款和条件文档, 单击复选框, 然后单击 "**保存**" 以提交导入作业。</span><span class="sxs-lookup"><span data-stu-id="35588-383">Read the terms and conditions document, click the checkbox, and then click **Save** to submit the import job.</span></span> 
    
    <span data-ttu-id="35588-384">成功创建导入作业时, 将显示一个状态页面, 说明驱动器发货过程的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="35588-384">When the import job is successfully created, a status page is displayed that explains the next steps of the drive shipping process.</span></span>
    
16. <span data-ttu-id="35588-p159">在 "**导入**" 页面![上,](media/O365-MDM-Policy-RefreshIcon.gif)单击 "刷新图标**刷新**" 以在导入作业列表中显示新的驱动器运输导入作业。请注意, 状态设置为 "**等待跟踪号码**"。您还可以单击 "导入作业" 以显示 "状态弹出页面", 其中包含有关导入作业的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="35588-p159">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to displayed the new drive shipping import job in the list of import jobs. Note that the status is set to **Waiting for tracking number**. You can also click the import job to display the status flyout page, which contains more detailed information about the import job.</span></span>
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a><span data-ttu-id="35588-388">步骤 5：将硬盘驱动器寄送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="35588-388">Step 5: Ship the hard drive to Microsoft</span></span>

<span data-ttu-id="35588-p160">下一步是将硬盘驱动器运送到 Microsoft, 然后提供发货的跟踪号码, 并返回驱动器运输作业的发货信息。在 Microsoft 收到该驱动器后, 数据中心人员需要7到10个工作日内将 PST 文件上传到您的组织的 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="35588-p160">The next step is to ship the hard drive to Microsoft, and then provide the tracking number for the shipment and return shipment information for the drive shipping job. After the drive is received by Microsoft, it will take between 7 and 10 business days for data center personnel to upload your PST files to the Azure storage area for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35588-p161">如果您在创建导入作业的14天内未提供跟踪号码并返回发货信息, 导入作业将会过期。如果发生这种情况, 您必须创建一个新的驱动器运输导入作业 (请参阅[步骤 4: 在 Office 365 中创建 PST 导入作业](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)), 然后重新提交驱动器文件和 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="35588-p161">If you don't provide the tracking number and return shipment information within 14 days of creating the import job, the import job will be expired. If this happens, you'll have to create a new drive shipping import job (see [Step 4: Create a PST Import job in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) and re-submit the drive file and the PST import mapping file.</span></span> 
  
### <a name="ship-the-hard-drive"></a><span data-ttu-id="35588-393">寄送硬盘驱动器</span><span class="sxs-lookup"><span data-stu-id="35588-393">Ship the hard drive</span></span>

<span data-ttu-id="35588-394">将硬盘驱动器寄送到 Microsoft 时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="35588-394">Keep the following things in mind when you ship hard drives to Microsoft:</span></span>
  
- <span data-ttu-id="35588-395">请勿发售 SATA 到 USB 适配器;您只需运送硬盘。</span><span class="sxs-lookup"><span data-stu-id="35588-395">Don't ship the SATA-to-USB adapter; you only have to ship the hard drive.</span></span>
    
- <span data-ttu-id="35588-396">妥善打包硬盘驱动器，例如，使用防静电袋或泡沫包装。</span><span class="sxs-lookup"><span data-stu-id="35588-396">Package the hard drive properly; for example, use an anti-static bag or bubble wrap.</span></span>
    
- <span data-ttu-id="35588-397">使用您所选择的交付承运人将硬盘驱动器寄送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="35588-397">Use a delivery carrier of your choice to ship the hard drive to Microsoft.</span></span>
    
- <span data-ttu-id="35588-p162">将硬盘驱动器运送到在步骤4中创建导入作业时显示的 Microsoft 位置的地址。请务必在送货地址中添加 "Office 365 导入服务"。</span><span class="sxs-lookup"><span data-stu-id="35588-p162">Ship the hard drive to the address for the Microsoft location that was displayed when you created the import job in Step 4. Be sure to include "Office 365 Import Service" in the ship-to address.</span></span>
    
- <span data-ttu-id="35588-p163">寄送硬盘驱动器之后，请务必记下交付承运人的名称和跟踪号。您将在下一步中提供这些信息。</span><span class="sxs-lookup"><span data-stu-id="35588-p163">After you ship the hard drive, be sure to write down the name of the delivery carrier and the tracking number. You'll provide these in the next step.</span></span>
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a><span data-ttu-id="35588-402">输入跟踪号和其他寄送信息</span><span class="sxs-lookup"><span data-stu-id="35588-402">Enter the tracking number and other shipping information</span></span>

<span data-ttu-id="35588-403">将硬盘驱动器寄送到 Microsoft 后，在导入服务页上完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="35588-403">After you've shipped the hard drive to Microsoft, complete the following procedure on the Import service page.</span></span>
  
1. <span data-ttu-id="35588-404">转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="35588-404">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="35588-405">在左窗格中, 单击 "**数据管理**", 然后单击 "**导入**"。</span><span class="sxs-lookup"><span data-stu-id="35588-405">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="35588-406">在 "**导入**" 页上, 单击要为其输入跟踪号码的驱动器货运的作业。</span><span class="sxs-lookup"><span data-stu-id="35588-406">On the **Import** page, click the job for the drive shipment that you want to enter the tracking number for.</span></span> 
    
4. <span data-ttu-id="35588-407">在 "状态弹出" 页上, 单击 "**输入跟踪号**"。</span><span class="sxs-lookup"><span data-stu-id="35588-407">On the status flyout page, click **Enter tracking number**.</span></span>
    
5. <span data-ttu-id="35588-408">请提供下列发货信息：</span><span class="sxs-lookup"><span data-stu-id="35588-408">Provide the following shipping information:</span></span>
    
1. <span data-ttu-id="35588-409">**交货承运人**键入您用于将硬盘驱动器运送到 Microsoft 的传递载体的名称。</span><span class="sxs-lookup"><span data-stu-id="35588-409">**Delivery carrier** Type the name of the delivery carrier that you used to ship the hard drive to Microsoft.</span></span> 
    
2. <span data-ttu-id="35588-410">**跟踪号码**键入硬驱发货的跟踪号码。</span><span class="sxs-lookup"><span data-stu-id="35588-410">**Tracking number** Type the tracking number for the hard drive shipment.</span></span> 
    
3. <span data-ttu-id="35588-p164">**返回承运人帐号**为在 "**退货承运人**" 下列出的运营商键入您的组织的帐户号码。Microsoft 将使用 (和收费) 此帐户将你的硬盘送回给你。请注意, 美国和欧洲的组织必须具有具有 FedEx 的帐户。亚洲的组织和世界各地的组织都必须具有 DHL 的帐户。</span><span class="sxs-lookup"><span data-stu-id="35588-p164">**Return carrier account number** Type your organization's account number for the carrier that listed under **Return carrier**. Microsoft will use (and charge) this account to ship your hard drive back to you. Note that organizations in the USA and Europe, must have an account with FedEx. Organizations in Asia and the rest of the world, must have an account with DHL.</span></span>
    
6. <span data-ttu-id="35588-415">单击 "**保存**" 以保存导入作业的此信息。</span><span class="sxs-lookup"><span data-stu-id="35588-415">Click **Save** to save this information for the import job.</span></span> 
    
    <span data-ttu-id="35588-p165">在 "**导入**" 页![上,](media/O365-MDM-Policy-RefreshIcon.gif)单击 "刷新图标**刷新**" 以更新驱动器传送导入作业的信息。请注意, 状态现在设置为 **"在传输中的驱动器"**。</span><span class="sxs-lookup"><span data-stu-id="35588-p165">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the information for your drive shipping import job. Notice that status is now set to **Drives in transit**.</span></span>

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="35588-418">步骤 6: 筛选数据并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="35588-418">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="35588-p166">Microsoft 在收到你的硬盘后,**导入**页面上的导入作业的状态将更改为 "**已接收的驱动器**"。数据中心人员将使用日记文件中的信息将 PST 文件上传到组织的 Azure 存储区域。在这种情况下, 状态将更改为 **"正在进行导入**"。如前所述, 接收到硬盘以上载 PST 文件后, 将需要7到10个工作日。</span><span class="sxs-lookup"><span data-stu-id="35588-p166">After your hard drive is received by Microsoft, the status for the import job on the **Import** page will change to **Drives received**. Data center personnel will use the information in the journal file to upload your PST files to the Azure storage area for your organization. At this point, the status will change to **Import in-progress**. As previously stated, it will take between 7 to 10 business days after receiving your hard drive to upload the PST files.</span></span>
  
<span data-ttu-id="35588-p167">将 PST 文件上传到 Azure 后, 状态将更改为**正在进行分析**。这表明 Office 365 正在分析 pst 文件中的数据 (以安全和安全的方式), 以标识这些项目的年龄和 pst 文件中包含的不同邮件类型。分析完成并准备导入数据后, 导入作业的状态将更改为 "**分析已完成**"。此时, 您可以选择导入 PST 文件中包含的所有数据, 也可以通过设置用于控制导入数据的筛选器来裁切导入的数据。</span><span class="sxs-lookup"><span data-stu-id="35588-p167">After PST files are uploaded to Azure, the status is changed to **Analysis in progress**. This indicates that Office 365 is analyzing the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, the status for the import job is changed to **Analysis completed**. At this point, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="35588-427">转到[https://protection.office.com](https://protection.office.com)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="35588-427">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="35588-428">在左窗格中, 单击 "**数据调控** > **导入**"。</span><span class="sxs-lookup"><span data-stu-id="35588-428">In the left pane, click **Data governance** > **Import**.</span></span>
    
3. <span data-ttu-id="35588-429">在 "**导入**" 页上, 单击 "已准备好为您在步骤4中创建的导入作业**导入 Office 365** "。</span><span class="sxs-lookup"><span data-stu-id="35588-429">On the **Import** page, click **Ready to import to Office 365** for the import job that you created in Step 4.</span></span> 
    
    ![单击您创建的导入作业旁边的 "已准备好导入到 Office 365"](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="35588-431">将显示一个 "飞出" 页面, 其中包含有关 PST 文件的信息以及有关导入作业的其他信息。</span><span class="sxs-lookup"><span data-stu-id="35588-431">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="35588-432">单击 "**导入到 Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="35588-432">Click **Import to Office 365**.</span></span>
    
5. <span data-ttu-id="35588-p168">将显示 "**筛选数据**" 页。它包含由 Office 365 对 PST 文件执行的分析生成的数据见解, 包括有关数据期限的信息。此时, 您可以选择筛选将导入的数据, 也可以按自己的方式导入所有数据。</span><span class="sxs-lookup"><span data-stu-id="35588-p168">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![您可以裁切 PST 文件中的数据, 也可以将其全部导入](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. <span data-ttu-id="35588-437">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="35588-437">Do one of the following:</span></span>
    
    <span data-ttu-id="35588-p169">一. 若要修整导入的数据, 请单击 **"是, 我想在导入前筛选它**"。</span><span class="sxs-lookup"><span data-stu-id="35588-p169">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="35588-440">有关筛选 PST 文件中的数据, 然后启动导入作业的详细分步说明, 请参阅[在将 pst 文件导入到 Office 365 时筛选数据](filter-data-when-importing-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="35588-440">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="35588-441">或者</span><span class="sxs-lookup"><span data-stu-id="35588-441">Or</span></span>
    
    <span data-ttu-id="35588-p170">b. 若要导入 PST 文件中的所有数据, 请单击 "**否, 我想要导入所有内容",** 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-p170">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
7. <span data-ttu-id="35588-444">如果选择导入所有数据, 请单击 "**导入数据**" 以启动导入作业。</span><span class="sxs-lookup"><span data-stu-id="35588-444">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="35588-p171">导入作业的状态将显示在 "**导入**" 页上。单击!["刷新](media/O365-MDM-Policy-RefreshIcon.gif)图标**刷新**" 以更新显示在 "**状态**" 列中的状态信息。单击 "导入作业" 以显示 "状态弹出页面", 其中显示有关导入的每个 PST 文件的状态信息。导入完成并将 PST 文件导入到用户邮箱后, 状态将更改为 "**已完成**"。</span><span class="sxs-lookup"><span data-stu-id="35588-p171">The status of the import job is displayed on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported. When the import is complete and PST files have been imported to user mailboxes, the status will be changed to **Completed**.</span></span>

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="35588-449">查看上传到 Office 365 的 PST 文件的列表</span><span class="sxs-lookup"><span data-stu-id="35588-449">View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="35588-p172">您可以安装并使用 Microsoft Azure 存储资源管理器 (它是免费的开源工具), 以查看我们将上载的 PST 文件的列表 (由 Microsoft 数据中心人员) 到您的组织的 Azure 存储区域。您可以执行此操作, 以验证发送到 Microsoft 的硬盘驱动器中的 PST 文件是否已成功上载到 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="35588-p172">You can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that we're uploaded (by Microsoft data center personnel) to the Azure storage area for your organization. You can do this to verify that PST files from the hard drives that you sent to Microsoft were successfully uploaded to the Azure storage area.</span></span>
  
<span data-ttu-id="35588-452">Microsoft Azure 存储资源管理器处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="35588-452">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="35588-p173">**重要说明:** 无法使用 Azure 存储资源管理器上传或修改 PST 文件。将 PST 文件导入到 Office 365 的唯一受支持的方法是使用 AzCopy。此外, 也不能删除已上载到 Azure blob 的 PST 文件。如果您尝试删除 PST 文件, 您将收到一条有关不具有所需权限的错误。请注意, 所有 PST 文件都将自动从 Azure 存储区域中删除。如果没有正在进行的导入作业, 则在创建最近的导入作业30天后, \* \* ingestiondata \* \* 容器中的所有 PST 文件都会被删除。</span><span class="sxs-lookup"><span data-stu-id="35588-p173">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the \*\* ingestiondata \*\* container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="35588-459">若要安装 azure 存储资源管理器并连接到 Azure 存储区, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="35588-459">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="35588-p174">执行以下步骤可获取组织的共享访问签名 (SAS) URL。此 URL 是用于组织的 Microsoft 云中的 Azure 存储位置的网络 URL 和 SAS 密钥的组合。此项为你提供访问组织的 Azure 存储位置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="35588-p174">Perform the following steps to get the Shared Access Signature (SAS) URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and an SAS key. This key provides you with the necessary permissions to access your organization's Azure storage location.</span></span>
    
1. <span data-ttu-id="35588-463">转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="35588-463">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="35588-464">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **导入**"。</span><span class="sxs-lookup"><span data-stu-id="35588-464">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
3. <span data-ttu-id="35588-465">在 "**导入**" 页![上,](media/ITPro-EAC-AddIcon.gif)单击 "添加图标" "**新建导入作业**"。</span><span class="sxs-lookup"><span data-stu-id="35588-465">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="35588-p175">在 "导入作业向导" 中, 键入 PST 导入作业的名称, 然后单击 "**下一步**"。使用小写字母、数字、连字符和下划线。不能在名称中使用大写字母或包含空格。</span><span class="sxs-lookup"><span data-stu-id="35588-p175">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="35588-469">在 "**选择导入作业类型**" 页上, 单击 "**上载数据**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-469">On the **Choose import job type** page, click **Upload your data** and then click **Next**.</span></span>
    
6. <span data-ttu-id="35588-470">在步骤2中, 单击 "**显示网络上载 SAS URL**"。</span><span class="sxs-lookup"><span data-stu-id="35588-470">In step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="35588-p176">显示 URL 后, 将其复制并保存到文件中。请务必复制整个 URL。</span><span class="sxs-lookup"><span data-stu-id="35588-p176">After the URL is displayed, copy it and save it to a file. Be sure to copy the entire URL.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35588-p177">请务必采取预防措施来保护 SAS URL。任何人都可以使用它来访问您的组织的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="35588-p177">Be sure to take precautions to protect the SAS URL. This can be used by anyone to access the Azure storage area for your organization.</span></span> 
  
8. <span data-ttu-id="35588-475">单击 "**取消**" 以关闭 "导入作业向导"。</span><span class="sxs-lookup"><span data-stu-id="35588-475">Click **Cancel** to close the import job wizard.</span></span> 
    
2. <span data-ttu-id="35588-476">下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="35588-476">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
3. <span data-ttu-id="35588-477">启动 Microsoft Azure 存储资源管理器, 在左窗格中右键单击 "**存储帐户**", 然后单击 "**连接到 Azure 存储**"。</span><span class="sxs-lookup"><span data-stu-id="35588-477">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![右键单击 "存储帐户", 然后单击 "连接到 Azure 存储"](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. <span data-ttu-id="35588-479">单击 "**使用共享访问签名 (SAS) URI 或连接字符串**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-479">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
5. <span data-ttu-id="35588-480">单击 "**使用 sas URI**", 将您在中的步骤1中获取的 sas URL 粘贴到 " **URI**" 下的框中, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="35588-480">Click **Use a SAS URI**, paste the SAS URL that you obtained in step 1 in to in the box under **URI**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="35588-481">在 "**连接摘要**" 页上, 您可以查看连接信息, 然后单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="35588-481">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="35588-p178">打开**ingestiondata**容器;它包含硬盘中的 PST 文件。**ingestiondata**容器位于**存储帐户** \> **(SAS 附加服务)** \> **Blob 容器**下。</span><span class="sxs-lookup"><span data-stu-id="35588-p178">The **ingestiondata** container is opened; it contains the PST files from your hard drive. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span>
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. <span data-ttu-id="35588-p179">使用 Microsoft Azure 存储资源管理器完成后, 右键单击 " **ingestiondata**", 然后单击 "**分离**" 断开与 Azure 存储区域的连接。否则, 下次尝试附加时, 将会收到错误。</span><span class="sxs-lookup"><span data-stu-id="35588-p179">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a><span data-ttu-id="35588-488">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="35588-488">Troubleshooting tips</span></span>
<span data-ttu-id="35588-489"><a name="troubleshootingtips"> </a></span><span class="sxs-lookup"><span data-stu-id="35588-489"></span></span>

- <span data-ttu-id="35588-p180">**如果由于 PST 导入 CSV 映射文件中的错误而导致导入作业失败, 会发生什么情况？** 如果导入作业由于映射文件中的错误而失败, 则无需将硬盘重新传送到 Microsoft, 即可创建新的导入作业。这是因为您为驱动器运输导入作业提交的硬盘驱动器上的 PST 文件已上传到您的组织的 Azure 存储区。在这种情况下, 只需修复 PST 导入 CSV 映射文件中的错误, 然后创建一个新的 "网络上载" 导入作业并提交修订后的 CSV 映射文件。若要创建和启动新的网络上载导入作业, 请参阅[第5步: 在 Office 365 中创建 PST 导入作业](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步骤 6: 筛选数据并启动 pst 导入作业](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主题 "使用网络上载将 pst 文件导入到 Office 365"。</span><span class="sxs-lookup"><span data-stu-id="35588-p180">**What happens if the import job fails because of errors in the PST Import CSV mapping file?** If an import job fails because of errors in the mapping file, you don't have to re-ship the hard drive to Microsoft in order to create a new import job. That's because the PST files from the hard drive that you submitted for the drive shipping import job have already been uploaded to the Azure storage area for your organization. In this case, you just have to fix the errors in the PST Import CSV mapping file, and then create a new "network upload" import job and submit the revised CSV mapping file. To create and start a new network upload import job, see [Step 5: Create a PST Import job in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) and [Step 6: Filter data and start the PST Import job](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) in the topic "Use network upload to import PST files to Office 365."</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="35588-p181">若要帮助您对 pst 导入 CSV 映射文件进行故障排除, 请使用[Azure 存储资源管理器](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具在**ingestiondata**容器中查看已上载到 Azure 存储区域的硬驱中的 PST 文件的文件夹结构。映射文件错误通常是由于 FilePath 参数中的值不正确而导致的。此参数指定 PST 文件在 Azure 存储区域中的位置。请参阅[第3步](#step-3-create-the-pst-import-mapping-file)中表中的 FilePath 参数的说明。如前所述, 当您在`/dstdir:` [步骤 2](#step-2-copy-the-pst-files-to-the-hard-drive)中运行 waimportexport.exe 工具时, 由参数指定在 Azure 存储区域中 PST 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="35588-p181">To help you troubleshoot the PST Import CSV mapping file, use the [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) tool to view the folder structure in the **ingestiondata** container for the PST files from your hard drive that were uploaded to the Azure storage area. Mapping file errors are typically caused by an incorrect value in the FilePath parameter. This parameter specifies the location of a PST file in the Azure storage area. See the description of the FilePath parameter in table in [Step 3](#step-3-create-the-pst-import-mapping-file). As previously explained, the location of PST files in the Azure storage area was specified by the  `/dstdir:` parameter when you ran the WAImportExport.exe tool in [Step 2](#step-2-copy-the-pst-files-to-the-hard-drive).</span></span> 
  

  
## <a name="more-information"></a><span data-ttu-id="35588-500">更多信息</span><span class="sxs-lookup"><span data-stu-id="35588-500">More information</span></span>

- <span data-ttu-id="35588-p182">驱动器运输是一种将大量存档邮件数据导入到 Office 365 以利用对您的组织可用的合规性功能的有效方法。将存档数据导入到用户邮箱后, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="35588-p182">Drive shipping is an effective way to import large amounts of archival messaging data to Office 365 to take advantage of the compliance features that are available to your organization. After archival data is imported to user mailboxes, you can:</span></span>
    
  - <span data-ttu-id="35588-503">启用[存档邮箱](enable-archive-mailboxes.md)和[自动扩展存档](enable-unlimited-archiving.md)以向用户提供额外的邮箱存储空间来存储数据。</span><span class="sxs-lookup"><span data-stu-id="35588-503">Enable [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space for the data.</span></span> 
    
  - <span data-ttu-id="35588-504">将邮箱置于[诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)以保留数据。</span><span class="sxs-lookup"><span data-stu-id="35588-504">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data.</span></span> 
    
  - <span data-ttu-id="35588-505">使用 Microsoft[电子数据展示工具](search-for-content.md)搜索数据。</span><span class="sxs-lookup"><span data-stu-id="35588-505">Use Microsoft [eDiscovery tools](search-for-content.md) to search the data.</span></span> 
    
  - <span data-ttu-id="35588-506">应用[Office 365 保留策略](retention-policies.md)以控制保留数据的时间长度, 以及保留期过期后要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="35588-506">Apply [Office 365 retention policies](retention-policies.md) to control how long the data is retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="35588-507">在[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)中搜索与此数据相关的事件。</span><span class="sxs-lookup"><span data-stu-id="35588-507">Search the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for events related to this data.</span></span> 
    
  - <span data-ttu-id="35588-508">出于合规目的将数据导入到[非活动邮箱](create-and-manage-inactive-mailboxes.md)以存档数据。</span><span class="sxs-lookup"><span data-stu-id="35588-508">Import data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="35588-509">保护您的组织不受敏感信息的[数据丢失](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="35588-509">Protect your organization against [data loss](data-loss-prevention-policies.md) of sensitive information.</span></span> 
    
- <span data-ttu-id="35588-p183">以下是安全存储帐户密钥和 BitLocker 加密密钥的示例。此示例还包含 WAImportExport.exe 命令的语法，运行此命令可将 PST 文件复制到硬盘驱动器。一定要采取预防措施来保护这些文件，就像保护密码或其他与安全相关的信息一样。</span><span class="sxs-lookup"><span data-stu-id="35588-p183">Here's an example of the secure storage account key and a BitLocker encryption key. This example also contains the syntax for the WAImportExport.exe command that you run to copy PST files to a hard drive. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    

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
   
- <span data-ttu-id="35588-p184">如前所述, Office 365 导入服务在将 PST 文件导入邮箱后, 将启用保留挂起设置 (无限期)。这意味着*RentionHoldEnabled*属性设置为`True` , 因此不会处理分配给邮箱的保留策略。这使邮箱所有者可以通过阻止删除或存档策略来删除或存档较旧的邮件来管理新导入的邮件。若要管理此保留挂起, 可以执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="35588-p184">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="35588-p185">在特定时间段后, 可以通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令关闭保留挂起。有关说明, 请参阅[将邮箱放在保留挂起](https://go.microsoft.com/fwlink/p/?LinkId=544749)中。</span><span class="sxs-lookup"><span data-stu-id="35588-p185">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="35588-p186">您可以配置保留挂起, 使其在将来某个日期处于关闭状态。可以通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令来执行此操作。例如, 假定今天的日期为2016年7月1日, 并且您希望在30天内关闭保留挂起功能, 请运行以下命令: `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在这种情况下, 您可以将*RentionHoldEnabled*属性设置为*True* 。有关详细信息, 请参阅[设置邮箱](https://go.microsoft.com/fwlink/p/?LinkId=150317)。</span><span class="sxs-lookup"><span data-stu-id="35588-p186">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="35588-p187">您可以更改已分配给邮箱的保留策略的设置, 以便不会立即删除导入的旧项目, 也不会将其移动到用户的存档邮箱。例如, 您可以延长分配给邮箱的删除或存档策略的保留期限。在这种情况下, 您可以在更改保留策略的设置后关闭邮箱的保留挂起。有关详细信息, 请参阅为[Office 365 组织中的邮箱设置存档和删除策略](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="35588-p187">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
    

  

