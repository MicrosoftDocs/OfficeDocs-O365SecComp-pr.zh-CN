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
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a><span data-ttu-id="78d3a-103">驱动器传送用于将您的组织 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="78d3a-103">Use drive shipping to import your organization PST files to Office 365</span></span>

<span data-ttu-id="78d3a-104">**本文是针对管理员。您试图将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="78d3a-104">**This article is for administrators. Are you trying to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="78d3a-p101">使用 Office 365 导入服务和传送以批量导入到用户邮箱的 PST 文件的驱动器。驱动器传送意味着您的 PST 文件复制到硬盘的磁盘驱动器，然后以物理方式提供给 Microsoft 的驱动器。当 Microsoft 收到您的硬盘时，则数据中心人员将向 Microsoft 云存储区数据复制从硬盘驱动器。然后，您有机会修整实际导入到的目标邮箱通过设置控制哪些数据获取导入的筛选器的 PST 数据。开始导入作业后，导入服务从导入 PST 数据存储区到用户邮箱。使用驱动器传送到用户邮箱导入 PST 文件是一种方法将您的组织的电子邮件迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p101">Use the Office 365 Import service and drive shipping to bulk-import PST files to user mailboxes. Drive shipping means that you copy the PST files to a hard disk drive and then physically ship the drive to Microsoft. When Microsoft receives your hard drive, data center personnel will copy the data from the hard drive to a storage area in the Microsoft cloud. Then you have the opportunity to trim the PST data that's actually imported to the target mailboxes by setting filters that control what data gets imported. After you start the import job, the Import service imports the PST data from the storage area to user mailboxes. Using drive shipping to import PST files to user mailboxes is one way to migrate your organization's email to Office 365.</span></span>
  
<span data-ttu-id="78d3a-111">下面是使用驱动器传送到 Office 365 邮箱导入 PST 文件所需的步骤：</span><span class="sxs-lookup"><span data-stu-id="78d3a-111">Here are the steps required to use drive shipping to import PST files to Office 365 mailboxes:</span></span>
  
[<span data-ttu-id="78d3a-112">步骤 1： 下载的安全存储键和 PST 导入工具</span><span class="sxs-lookup"><span data-stu-id="78d3a-112">Step 1: Download the secure storage key and PST Import tool</span></span>](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[<span data-ttu-id="78d3a-113">步骤 2： 将 PST 文件复制到硬盘驱动器上</span><span class="sxs-lookup"><span data-stu-id="78d3a-113">Step 2: Copy the PST files to the hard drive</span></span>](#step-2-copy-the-pst-files-to-the-hard-drive)

[<span data-ttu-id="78d3a-114">步骤 3： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="78d3a-114">Step 3: Create the PST Import mapping file</span></span>](#step-3-create-the-pst-import-mapping-file)

[<span data-ttu-id="78d3a-115">步骤 4：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="78d3a-115">Step 4: Create a PST Import job in Office 365</span></span>](#step-4-create-a-pst-import-job-in-office-365)

[<span data-ttu-id="78d3a-116">步骤 5：将硬盘驱动器寄送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="78d3a-116">Step 5: Ship the hard drive to Microsoft</span></span>](#step-5-ship-the-hard-drive-to-microsoft)

[<span data-ttu-id="78d3a-117">步骤 6： 筛选数据，并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="78d3a-117">Step 6: Filter data and start the PST Import job</span></span>](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> <span data-ttu-id="78d3a-p102">您必须执行步骤 1 一次加载下的安全存储密钥和导入工具。执行这些步骤后，按照步骤 2 至步骤 6 每的次您想要附带向 Microsoft 硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p102">You have to perform Step 1 once to down load the secure storage key and the import tool. After you perform these steps, follow Step 2 through Step 6 each time you want to ship a hard drive to Microsoft.</span></span> 
  
<span data-ttu-id="78d3a-120">为经常常见问题有关使用传送到 Office 365 导入 PST 文件，请参阅[使用传送导入 PST 文件的驱动器的常见问题](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files)的驱动器。</span><span class="sxs-lookup"><span data-stu-id="78d3a-120">For frequently asked questions about using drive shipping to import PST files to Office 365, see [FAQs for using drive shipping to import PST files](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="78d3a-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="78d3a-121">Before you begin</span></span>

- <span data-ttu-id="78d3a-p103">您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新的角色组、 分配的邮箱导入导出角色中，然后将自己添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分中[管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p103">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
    
    <span data-ttu-id="78d3a-127">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="78d3a-127">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
    
  - <span data-ttu-id="78d3a-p104">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p104">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="78d3a-130">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-130">Or</span></span>
    
  - <span data-ttu-id="78d3a-131">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="78d3a-131">You have to be a global administrator in your Office 365 organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="78d3a-p105">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p105">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
- <span data-ttu-id="78d3a-p106">您需要存储您想要复制到硬盘上的文件服务器或在组织中的共享的文件夹的 PST 文件。在步骤 2 中，您将运行此文件服务器上存储或共享到硬盘上的文件夹的 PST 文件将复制的 Azure 导入导出工具 (WAImportExport.exe)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p106">You need to store the PST files that you want to copy to a hard drive on a file server or shared folder in your organization. In Step 2, you'll run the Azure Import Export tool (WAImportExport.exe) that will copy the PST files that are stored on this file server or shared folder to the hard drive.</span></span>
    
- <span data-ttu-id="78d3a-p107">仅为 2.5 英寸固态驱动器 (Ssd) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘支持与 Office 365 导入服务一起使用。您可以使用硬盘最多 10 TB。导入作业将处理仅第一个数据卷上的硬盘中。必须使用 NTFS 格式化数据量。当数据复制到硬盘上，您可以将其直接使用 2.5 英寸 SSD 附加或 2.5 或 3.5 英寸 SATA II/III 连接器或可以附加外部使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p107">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78d3a-p108">Office 365 导入服务不支持外部硬盘驱动器附带的内置的 USB 适配器。此外，不能使用内外部的硬盘驱动器上的大小写磁盘。请不要附带外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p108">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
- <span data-ttu-id="78d3a-p109">必须使用 BitLocker 加密硬盘复制到 PST 文件。在步骤 2 中运行该 WAImportExport.exe 工具将帮助您设置 BitLocker。它还生成 BitLocker 加密密钥的 Microsoft 数据中心人员将用于访问上载到 Microsoft 云中的 Azure 存储区的 PST 文件的驱动器。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p109">The hard drive that you copy the PST files to must be encrypted with BitLocker. The WAImportExport.exe tool that you run in Step 2 will help you set up BitLocker. It also generates a BitLocker encryption key that Microsoft data center personnel will use to access the drive to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>
    
- <span data-ttu-id="78d3a-p110">驱动器传送是通过 Microsoft 企业协议 (EA) 可用。驱动器传送不提供通过 Microsoft 产品和服务协议 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p110">Drive shipping is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
    
- <span data-ttu-id="78d3a-p111">每 GB 的数据 2 美元成本 PST 文件导入使用驱动器传送的 Office 365 邮箱。例如，如果附带包含 1,000 GB (1 TB) 的 PST 文件的硬盘驱动器，成本是 2,000 美元。您可以使用导入费用，合作伙伴。有关查找合作伙伴的信息，请参阅[查找您的 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p111">The cost to import PST files to Office 365 mailboxes using drive shipping is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
    
- <span data-ttu-id="78d3a-153">您或您的组织必须拥有 FedEx 或 DHL 帐户。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-153">You or your organization must have an account with FedEx or DHL.</span></span>
    
  - <span data-ttu-id="78d3a-154">美国、 巴西和欧洲中的组织必须拥有 FedEx 帐户。</span><span class="sxs-lookup"><span data-stu-id="78d3a-154">Organizations in the United States, Brazil, and Europe must have FedEx accounts.</span></span>
    
  - <span data-ttu-id="78d3a-155">中国、 东南方向亚洲，日本、 韩国、 和澳大利亚中的组织必须拥有 DHL 帐户。</span><span class="sxs-lookup"><span data-stu-id="78d3a-155">Organizations in East Asia, Southeast Asia, Japan, Republic of Korea, and Australia must have DHL accounts.</span></span>
    
    <span data-ttu-id="78d3a-156">Microsoft 将使用（并收费）此帐户将硬盘驱动器返还给您。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-156">Microsoft will use (and charge) this account to return the hard drive back to you.</span></span>
    
- <span data-ttu-id="78d3a-p112">您寄送到 Microsoft 的硬盘驱动器可能需要跨国际边界。如果出现这种情况，您要负责确保根据适用的法律导入和/或导出该硬盘驱动器及其所包含的数据。寄送硬盘驱动器之前，请联系您的顾问以验证您的驱动器和数据是否可以合法地寄送到确定的 Microsoft 数据中心。这将有助于确保该硬盘及时到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p112">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the identified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
    
- <span data-ttu-id="78d3a-p113">此过程涉及复制并保存的安全存储键及 BitLocker 加密密钥。请确保采取预防措施来保护这些项，如将保护密码或其他安全相关的信息。例如，您可能会将其保存到受密码保护的 Microsoft Word 文档或将其保存到加密的 USB 驱动器。请参阅有关这些项的示例的[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p113">This procedure involves copying and saving a secure storage key and a BitLocker encryption key. Be sure to take precautions to protect these keys like you would protect passwords or other security-related information. For example, you might save them to a password-protected Microsoft Word document or save them to an encrypted USB drive. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for an example of these keys.</span></span> 
    
- <span data-ttu-id="78d3a-p114">PST 文件导入到 Office 365 邮箱后，设置为该邮箱保留挂起是无限期的持续时间内，打开的。这意味着关闭保留挂起或设置要关闭保留日期之前，将不会处理分配给邮箱的保留策略。为什么做的原因？如果旧导入到邮箱的邮件，它们可能被永久删除 （清除） 由于其保留期已过期基于配置为该邮箱的保留设置。将邮箱放在保留挂起将给邮箱所有者时间来管理这些新导入的邮件或授予时间更改邮箱的保留设置。请参阅有关管理保留挂起的建议的[详细信息](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p114">After PST files are imported to an Office 365 mailbox, the retention hold setting for the mailbox is turned on for an indefinite duration. This means that the retention policy assigned to the mailbox won't be processed until you turn off the retention hold or set a date to turn off the hold. Why do we do this? If messages imported to a mailbox are old, they might be permanently deleted (purged) because their retention period has expired based on the retention settings configured for the mailbox. Placing the mailbox on retention hold will give the mailbox owner time to manage these newly-imported messages or give you time to change the retention settings for the mailbox. See the [More information](use-drive-shipping-to-import-pst-files-to-office-365.md#moreinfo) section for suggestions about managing the retention hold.</span></span> 
    
- <span data-ttu-id="78d3a-p115">默认情况下，可以接收的 Office 365 邮箱的最大邮件大小为 35 MB。这是因为邮箱的*MaxReceiveSize*属性的默认值设置为 35 MB。但是，此限制的最大邮件接收 Office 365 中的大小为 150 MB。因此，如果导入 PST 文件包含大于 35 MB，我们将自动更改为 150 MB 的目标邮箱上*MaxReceiveSize*属性的值的导入 Office 365 服务的项。这将允许邮件 150 MB 要导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p115">By default, the maximum message size that can be received by an Office 365 mailbox is 35 MB. That's because the default value for the  *MaxReceiveSize*  property for a mailbox is set to 35 MB. However, the limit for the maximum message receive size in Office 365 is 150 MB. So if you import a PST file that contains an item larger than 35 MB, the Office 365 Import service we will automatically change the value of the  *MaxReceiveSize*  property on the target mailbox to 150 MB. This allows messages up to 150 MB to be imported to user mailboxes.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="78d3a-176">若要确定邮件接收大小为邮箱中，您可以运行此命令在 Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`。</span><span class="sxs-lookup"><span data-stu-id="78d3a-176">To identify the message receive size for a mailbox, you can run this command in Exchange Online PowerShell:  `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.</span></span> 
  
- <span data-ttu-id="78d3a-p116">您可以向 Office 365 中的非活动邮箱导入 PST 文件。执行此操作通过指定中的非活动邮箱的 GUID `Mailbox` PST 导入映射文件中的参数。请参阅[步骤 3： 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p116">You can import PST files to an inactive mailbox in Office 365. You do this by specifying the GUID of the inactive mailbox in the  `Mailbox` parameter in the PST Import mapping file. See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 
    
- <span data-ttu-id="78d3a-p117">在 Exchange 混合部署，您可以 PST 文件导入为其主邮箱位于内部部署用户的基于云的存档邮箱。通过执行以下 PST 导入映射文件中的执行此操作：</span><span class="sxs-lookup"><span data-stu-id="78d3a-p117">In an Exchange hybrid deployment, you can import PST files to a cloud-based archive mailbox for a user whose primary mailbox is on-premises. You do this by doing the following in the PST Import mapping file:</span></span>
    
  - <span data-ttu-id="78d3a-182">指定用户的内部部署邮箱中的电子邮件地址`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-182">Specify the email address for the user's on-premises mailbox in the  `Mailbox` parameter.</span></span> 
    
  - <span data-ttu-id="78d3a-183">指定**TRUE**值在`IsArchive`参数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-183">Specify the **TRUE** value in the  `IsArchive` parameter.</span></span> 
    
    <span data-ttu-id="78d3a-184">请参阅[步骤 3： 创建 PST 导入映射文件](use-drive-shipping-to-import-pst-files-to-office-365.md#step3)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-184">See [Step 3: Create the PST Import mapping file](use-drive-shipping-to-import-pst-files-to-office-365.md#step3) for more information.</span></span> 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a><span data-ttu-id="78d3a-185">步骤 1： 下载的安全存储键和 PST 导入工具</span><span class="sxs-lookup"><span data-stu-id="78d3a-185">Step 1: Download the secure storage key and PST Import tool</span></span>

<span data-ttu-id="78d3a-186">第一步是下载的安全存储密钥和工具，并将使用在步骤 2 到 PST 文件复制到硬盘上。</span><span class="sxs-lookup"><span data-stu-id="78d3a-186">The first step is to download the secure storage key and the tool and that you will use in Step 2 to copy PST files to the hard drive.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="78d3a-p118">您必须使用 Azure 导入/导出工具版本 1 (WAimportExportV1) 使用的驱动器传送方法成功导入 PST 文件。不受支持版本 2 的 Azure 导入/导出工具并使用它将导致不正确准备导入作业的硬盘中。请务必从安全下载 Azure 导入/导出工具&amp;合规性中心在此步骤中的过程。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p118">You have to use Azure Import/Export tool version 1 (WAimportExportV1) to successfully import PST files by using the drive shipping method. Version 2 of the Azure Import/Export tool isn't supported and using it will result in incorrectly preparing the hard drive for the import job. Be sure to download the Azure Import/Export tool from the Security &amp; Compliance Center by following the procedures in this step.</span></span> 
  
1. <span data-ttu-id="78d3a-190">转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-190">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="78d3a-191">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-191">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78d3a-192">如上文所述，您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="78d3a-192">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
3. <span data-ttu-id="78d3a-193">在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-193">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="78d3a-p119">在导入作业向导中，为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p119">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="78d3a-197">在**选择导入作业类型**页上，单击**传送硬盘驱动器到我们的物理位置之一**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-197">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![单击传送到我们的物理位置创建驱动器传送导入作业之一硬盘驱动器](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="78d3a-199">在**导入数据**页上，执行以下两项操作：</span><span class="sxs-lookup"><span data-stu-id="78d3a-199">On the **Import data** page, do the following two things:</span></span> 
    
    ![复制的安全存储密钥并下载导入数据页上的 Azure 导入导出工具](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    <span data-ttu-id="78d3a-p120">答： 在步骤 2 中，单击**复制安全存储密钥**。显示存储密钥后，单击**复制到剪贴板**然后将其粘贴并将其保存到文件，以便您可以更高版本访问它。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p120">a. In step 2, click **Copy the secure storage key**. After the storage key is displayed, click **Copy to clipboard** and then paste it and save it to a file so you can access it later.</span></span>
    
    <span data-ttu-id="78d3a-p121">b.在步骤 3，**下载 Azure 导入/导出工具**以下载并安装 Azure 导入/导出 （版本 1） 工具。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p121">b. In step 3, **Download the Azure Import/Export tool** to download and install the Azure Import/Export (version 1) tool.</span></span>
    
    - <span data-ttu-id="78d3a-206">在弹出窗口中，单击**保存** \> **另存为**本地计算机上将 WaImportExportV1.zip 文件保存到文件夹。</span><span class="sxs-lookup"><span data-stu-id="78d3a-206">In the pop-up window, click **Save** \> **Save as** to save the WaImportExportV1.zip file to a folder on your local computer.</span></span> 
    
    - <span data-ttu-id="78d3a-207">提取 WaImportExportV1.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-207">Extract the WaImportExportV1.zip file.</span></span>
    
7. <span data-ttu-id="78d3a-208">单击**取消**以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="78d3a-208">Click **Cancel** to close the wizard.</span></span> 
    
    <span data-ttu-id="78d3a-209">将转至安全中的**导入**页后&amp;合规性中心时您在步骤 4 中创建导入作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-209">You'll come back to the **Import** page in the Security &amp; Compliance Center when you create the import job in Step 4.</span></span> 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a><span data-ttu-id="78d3a-210">步骤 2： 将 PST 文件复制到硬盘驱动器上</span><span class="sxs-lookup"><span data-stu-id="78d3a-210">Step 2: Copy the PST files to the hard drive</span></span>

<span data-ttu-id="78d3a-p122">下一步是使用 WAImportExport.exe 工具以将 PST 文件复制到硬盘上。此工具加密的硬盘中使用 BitLocker、 将 Pst 复制到硬盘上，并创建日志文件，用于存储有关复制过程的信息。若要完成此步骤，PST 文件必须位于文件共享或组织中的文件服务器。这就是在下面的过程的源目录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p122">The next step is to use the WAImportExport.exe tool to copy PST files to the hard drive. This tool encrypts the hard drive with BitLocker, copies the PSTs to the hard drive, and creates a journal file that stores information about the copy process. To complete this step, the PST files have to be located in a file share or file server in your organization. This is known as the source directory in the following procedure.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="78d3a-p123">运行 WAImportExport.exe 工具硬盘驱动器上的第一个时间后，您必须使用不同的语法每个时间之后。此过程可将 PST 文件复制到硬盘上的步骤 4 中介绍了此语法。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p123">After you run the WAImportExport.exe tool the first time for a hard drive, you have to use a different syntax each time after that. This syntax is explained in step 4 of this procedure to copy PST files to the hard drive.</span></span> 
  
1. <span data-ttu-id="78d3a-217">在您的本地计算机上打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="78d3a-217">Open a Command Prompt on your local computer.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="78d3a-p124">如果您以管理员身份运行命令提示符（打开命令提示符时选择“以管理员身份运行”），将在命令提示符窗口中显示错误消息。这可以帮助您解决运行 WAImportExport.exe 工具时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p124">If you run the command prompt as an administrator (by selecting "Run as administrator" when you open it) error messages will be displayed in the command prompt window. This can help you troubleshoot problems running the WAImportExport.exe tool.</span></span> 
  
2. <span data-ttu-id="78d3a-220">转到您在步骤 1 中安装 WAImportExport.exe 工具的目录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-220">Go to the directory where you installed the WAImportExport.exe tool in Step 1.</span></span>
    
3. <span data-ttu-id="78d3a-221">您首次使用 WAImportExport.exe 将 PST 文件复制到硬盘驱动器时，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="78d3a-221">Run the following command the first time that you use the WAImportExport.exe to copy PST files to a hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /encrypt /logdir:<Log file location>
    ```

    <span data-ttu-id="78d3a-222">下表描述了各个参数及其所需值。</span><span class="sxs-lookup"><span data-stu-id="78d3a-222">The following table describes the parameters and their required values.</span></span>
    
    |<span data-ttu-id="78d3a-223">**参数**</span><span class="sxs-lookup"><span data-stu-id="78d3a-223">**Parameter**</span></span>|<span data-ttu-id="78d3a-224">**说明**</span><span class="sxs-lookup"><span data-stu-id="78d3a-224">**Description**</span></span>|<span data-ttu-id="78d3a-225">**示例**</span><span class="sxs-lookup"><span data-stu-id="78d3a-225">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `/j:` <br/> |<span data-ttu-id="78d3a-p125">指定日志文件的名称。此文件保存到 WAImportExport.exe 工具所在的同一文件夹中。您寄送到 Microsoft 的每个硬盘驱动器必须有一个日志文件。每次您运行 WAImportTool.exe 将 PST 文件复制到硬盘驱动器时，相关信息将追加到该驱动器的日志文件中。 
</span><span class="sxs-lookup"><span data-stu-id="78d3a-p125">Specifies the name of the journal file. This file is saved to the same folder where the WAImportExport.exe tool is located. Each hard drive you ship to Microsoft must have one journal file. Every time you run the WAImportTool.exe to copy PST files to a hard drive, information will be appended to the journal file for that drive.</span></span>  <br/> <span data-ttu-id="78d3a-230">与在步骤 4 中创建的导入作业相关联的硬盘中并将 PST 文件上载到 Microsoft 云中的 Azure 存储区，Microsoft 数据中心人员将日志文件中使用的信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-230">Microsoft data center personnel will use the information in the journal file to associate the hard drive with the import job that you create in Step 4, and to upload the PST files to the Azure storage area in the Microsoft cloud.</span></span>  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |<span data-ttu-id="78d3a-231">连接到本地计算机时，请指定硬盘驱动器的驱动器号。</span><span class="sxs-lookup"><span data-stu-id="78d3a-231">Specifies the drive letter of the hard drive when it's connected to your local computer.</span></span>  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |<span data-ttu-id="78d3a-p126">指定复制会话的名称。会话定义为每次运行 WAImportExport.exe 工具将文件复制到硬盘驱动器。PST 文件复制到使用此参数所指定的会话名称命名的文件夹中。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-p126">Specifies the name of the copy session. A session is defined as each time you run the WAImportExport.exe tool to copy files to the hard drive. The PST files are copied to a folder named with the session name specified by this parameter.</span></span>  <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |<span data-ttu-id="78d3a-p127">组织中的包含将在会话过程中复制的 PST 文件中指定源目录。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p127">Specifies the source directory in your organization that contains the PST files that will be copied during the session. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |<span data-ttu-id="78d3a-p128">在其中将上载 Pst Microsoft 云中的 Azure 存储区中指定的目标目录。您必须使用值`ingestiondata/`。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p128">Specifies the destination directory in the Azure storage area in the Microsoft cloud where the PSTs will be uploaded. You must use the value  `ingestiondata/`. Be sure to surround the value of this parameter with double-quotation marks (" ").  </span></span><br/> <span data-ttu-id="78d3a-p129">或者，也可以添加到此参数的值的其他文件路径。例如，您可以使用源目录 （转换为 URL 格式） 的硬盘，后者中指定的文件路径`/srcdir:`参数。例如，`\\FILESERVER01\PSTs`更改为`FILESERVER01/PSTs`。在这种情况下，您仍必须包括`ingestiondata`中的文件路径。因此，在本例中为的值`/dstdir:`参数应为`"ingestiondata/FILESERVER01/PSTs"`。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p129">Optionally, you can also add an additional file path to the value of this parameter. For example, you can use the file path of the source directory on the hard drive (converted to a URL format) , which is specified in the  `/srcdir:` parameter. For example,  `\\FILESERVER01\PSTs` is changed to  `FILESERVER01/PSTs`. In this case, you still must include  `ingestiondata` in the file path. So in this example, the value for the  `/dstdir:` parameter would be  `"ingestiondata/FILESERVER01/PSTs"`.  </span></span><br/> <span data-ttu-id="78d3a-245">要添加其他文件路径的一个原因是如果必须具有相同的文件名的 Pst 文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-245">One reason to add the additional file path is if you have PSTs files with the same filename.</span></span>  <br/> <span data-ttu-id="78d3a-p130">> [!NOTE]> PST 文件上载到 Azure 存储区域后的命名空间如果包含可选的路径名，将包括路径名和 PST 文件中; 的名称例如， `FILESERVER01/PSTs/annb.pst`。如果不包括路径名，命名空间是仅 PST 文件名;例如`annb.pst`。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p130">> [!NOTE]> If you include the optional pathname, the namespace for a PST file after it's uploaded to the Azure storage area will include the pathname and the name of the PST file; for example,  `FILESERVER01/PSTs/annb.pst`. If you don't include a pathname, the namespace is only the PST filename; for example  `annb.pst`.</span></span>           | `/dstdir:"ingestiondata/"` <br/> <span data-ttu-id="78d3a-248">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-248">Or</span></span>  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |<span data-ttu-id="78d3a-p131">步骤 1 中指定您获取的存储帐户键。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p131">Specifies the storage account key that you obtained in Step 1. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/encrypt` <br/> |此开关对硬盘驱动器启用 BitLocker。首次运行 WAImportExport.exe 工具时，此参数是必需的。  <br/> <span data-ttu-id="78d3a-p133">BitLocker 加密密钥复制到日志文件，如果您使用所创建的日志文件`/logfile:`参数。如前所述，如果在日志文件将保存到 WAImportExport.exe 工具所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p133">The BitLocker encryption key is copied to the journal file and the log file that is created if you use the  `/logfile:` parameter. As previously explained, the journal file is saved to the same folder where the WAImportExport.exe tool is located.  </span></span><br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |<span data-ttu-id="78d3a-p134">此可选参数指定要用于保存日志文件的文件夹。如果未指定，日志文件到 WAImportExport.exe 工具所在的同一文件夹是保存。请务必包围双引号与此参数的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p134">This optional parameter specifies a folder to save log files to. If not specified, the log files are save to the same folder where the WAImportExport.exe tool is located. Be sure to surround the value of this parameter with double-quotation marks (" ").</span></span>  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    <span data-ttu-id="78d3a-258">以下是对每个参数使用实际值的 WAImportExport.exe 工具的语法示例：</span><span class="sxs-lookup"><span data-stu-id="78d3a-258">Here's an example of the syntax for the WAImportExport.exe tool using actual values for each parameter:</span></span>
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    <span data-ttu-id="78d3a-p135">运行该命令后，显示的状态消息会显示将 PST 文件复制到硬盘驱动器的进度。最终状态消息显示已成功复制的文件总数。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-p135">After you run the command, status messages are displayed that show the progress of copying the PST files to the hard drive. A final status message shows the total number of files that were successfully copied.</span></span>
    
4. <span data-ttu-id="78d3a-261">以后每次运行 WAImportExport.ext 工具将 PST 文件复制到同一个硬盘驱动器时运行此命令。</span><span class="sxs-lookup"><span data-stu-id="78d3a-261">Run this command each subsequent time you run the WAImportExport.ext tool to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> 
    ```

    <span data-ttu-id="78d3a-262">下面是运行后续会话将 PST 文件复制到同一个硬盘驱动器的语法示例。  </span><span class="sxs-lookup"><span data-stu-id="78d3a-262">Here's an example of the syntax for running subsequent sessions to copy PST files to the same hard drive.</span></span>

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/"
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a><span data-ttu-id="78d3a-263">步骤 3： 创建 PST 导入映射文件</span><span class="sxs-lookup"><span data-stu-id="78d3a-263">Step 3: Create the PST Import mapping file</span></span>

<span data-ttu-id="78d3a-p136">导入服务在 PST 导入映射文件中，这是一个以逗号分隔值 (CSV) 文件，指定哪些用户邮箱 PST Microsoft 数据中心人员上载到 Azure 存储区的硬盘的 PST 文件后，将使用的信息文件将导入到。创建 PST 导入作业时，您将提交的下一步此 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p136">After Microsoft data center personnel upload the PST files from the hard drive to the Azure storage area, the Import service will use the information in the PST Import mapping file, which is a comma separated value (CSV) file, that specifies which user mailboxes the PST files will be imported to. You will submit this CSV file in the next step when you create a PST Import job.</span></span>
  
1. <span data-ttu-id="78d3a-266">[下载 PST 导入映射文件的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-266">[Download a copy of the PST Import mapping file](https://go.microsoft.com/fwlink/p/?LinkId=544717).</span></span>
    
2. <span data-ttu-id="78d3a-p137">打开或将 CSV 文件保存到您的本地计算机。下面的示例显示已完成的 PST 导入映射文件（在记事本中打开）。使用 Microsoft Excel 编辑 CSV 文件变得容易得多。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p137">Open or save the CSV file to your local computer. The following example shows a completed PST Import mapping file (opened in NotePad). It's much easier to use Microsoft Excel to edit the CSV file.</span></span>

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

    <span data-ttu-id="78d3a-p138">标题行，CSV 文件的第一行中，列出 PST 导入服务将用于将 PST 文件导入到用户邮箱的参数。每个参数名称并用逗号分隔。在标题行下的各行代表 PST 文件导入到特定邮箱的参数值。对于每个 PST 文件复制到硬盘上，您将需要一行。请务必映射文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p138">The first row, or header row, of the CSV file lists the parameters that will be used by the PST Import service to import the PST files to user mailboxes. Each parameter name is separated by a comma. Each row under the header row represents the parameter values for importing a PST file to a specific mailbox. You will need a row for each PST file that was copied to the hard drive. Be sure to replace the placeholder data in the mapping file with your actual data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78d3a-275">不要更改标题行中的任何内容，包括 SharePoint 参数；这些内容会在 PST 导入过程中被忽略。</span><span class="sxs-lookup"><span data-stu-id="78d3a-275">Don't change anything in the header row, including the SharePoint parameters; they will be ignored during the PST Import process.</span></span> 
  
3. <span data-ttu-id="78d3a-276">使用下表中的信息来填充附有所需信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-276">Use the information in the following table to populate the CSV file with the required information.</span></span>
    
    |<span data-ttu-id="78d3a-277">**参数**</span><span class="sxs-lookup"><span data-stu-id="78d3a-277">**Parameter**</span></span>|<span data-ttu-id="78d3a-278">**说明**</span><span class="sxs-lookup"><span data-stu-id="78d3a-278">**Description**</span></span>|<span data-ttu-id="78d3a-279">**示例**</span><span class="sxs-lookup"><span data-stu-id="78d3a-279">**Example**</span></span>|
    |:-----|:-----|:-----|
    | `Workload` <br/> |<span data-ttu-id="78d3a-p139">指定数据将导入到的 Office 365 服务。若要为用户邮箱导入 PST 文件，请使用`Exchange`。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p139">Specifies the Office 365 service that data will be imported to. To import PST files to user mailboxes, use  `Exchange`.  </span></span><br/> | `Exchange` <br/> |
    | `FilePath` <br/> | <span data-ttu-id="78d3a-282">PST 文件将被复制到硬盘发货时向 Microsoft Azure 存储区域中指定的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="78d3a-282">Specifies the folder location in the Azure storage area that PST files will be copied to when the hard drive is shipped to Microsoft.</span></span>  <br/>  <span data-ttu-id="78d3a-283">CSV 文件中的此列中添加的内容取决于什么中指定的`/dstdir:`上一步骤中的参数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-283">What you add in this column in the CSV file depends on what you specified in for the  `/dstdir:` parameter in the previous step.</span></span>  <br/>  <span data-ttu-id="78d3a-284">如果您使用`/dstdir:"ingestiondata/"`，然后将此参数留空 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="78d3a-284">If you used  `/dstdir:"ingestiondata/"`, then leave this parameter blank in the CSV file.</span></span>  <br/>  <span data-ttu-id="78d3a-p140">如果您包含的值为可选路径名`/dstdir:`参数 (如`/dstdir:"ingestiondata/FILESERVER01/PSTs"`，然后为 CSV 文件中的此参数中使用的路径名 （不包括"ingestiondata"）。此参数的值是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p140">If you included an optional pathname for the value of the  `/dstdir:` parameter (for example,  `/dstdir:"ingestiondata/FILESERVER01/PSTs"`, then use that pathname (not including "ingestiondata") for this parameter in the CSV file. The value for this parameter is case sensitive.  </span></span><br/>  <span data-ttu-id="78d3a-p141">两种方法，在的值*不*包括"ingestiondata"`FilePath`参数。将此参数留空，或指定只是可选的路径名。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p141">Either way,  *don't*  include "ingestiondata" in the value for the  `FilePath` parameter. Leave this parameter blank or specify only the optional pathname.  </span></span><br/> <span data-ttu-id="78d3a-p142">> [!IMPORTANT]> 文件路径名称案例必须相同中指定的大小写`/dstdir:`上一步骤中的参数。例如，如果您使用`"ingestiondata/FILESERVER01/PSTs"`的子文件夹名称在上一步骤中，但然后使用`fileserver01/psts`的`FilePath`CSV 文件中的参数，将会失败的 PST 文件导入。请务必在这两种情况下使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p142">> [!IMPORTANT]>  The case for the file path name must be the same case that you specified in the  `/dstdir:` parameter in the previous step . For example, if you used  `"ingestiondata/FILESERVER01/PSTs"` for the subfolder name in the previous step, but then used  `fileserver01/psts` in the  `FilePath` parameter in CSV file, the import for the PST file will fail. Be sure to use the same case in both instances.</span></span>           |<span data-ttu-id="78d3a-292">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="78d3a-292">(leave blank)</span></span>  <br/> <span data-ttu-id="78d3a-293">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-293">Or</span></span>  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |<span data-ttu-id="78d3a-p143">指定将导入到用户邮箱的 PST 文件的名称。此参数的值是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p143">Specifies the name of the PST file that will be imported to the user mailbox. The value for this parameter is case sensitive.  </span></span><br/> <span data-ttu-id="78d3a-p144">> [!IMPORTANT]> 大小写的 CSV 文件中的 PST 文件名称必须与已上载到在步骤 2 中的 Azure 的存储位置的 PST 文件相同。例如，如果您使用`annb.pst`中`Name`CSV 文件，但实际的 PST 文件的名称中的参数是`AnnB.pst`，该 PST 文件导入将失败。确保 CSV 文件中 PST 的名称，为实际的 PST 文件使用相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p144">> [!IMPORTANT]> The case for the PST file name in the CSV file must be the same as the PST file that was uploaded to the Azure storage location in Step 2. For example, if you use  `annb.pst` in the  `Name` parameter in the CSV file, but the name of the actual PST file is  `AnnB.pst`, the import for that PST file will fail. Be sure that the name of the PST in the CSV file uses the same case as the actual PST file.</span></span>           | `annb.pst` <br/> |
    | `Mailbox` <br/> |<span data-ttu-id="78d3a-p145">指定的邮箱的 PST 文件导入到的电子邮件地址。请注意，不能指定公用文件夹，因为 PST 导入服务不支持将 PST 文件导入到公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p145">Specifies the email address of the mailbox that the PST file will be imported to. Note that you can't specify a public folder because the PST Import Service doesn't support importing PST files to public folders.  </span></span><br/> <span data-ttu-id="78d3a-p146">若要导入非活动邮箱 PST 文件，您必须指定此参数的邮箱的邮箱 GUID。若要获取此 GUID，请运行以下 PowerShell 命令在 Exchange Online: Get-mailbox <identity of inactive mailbox> -InactiveMailboxOnly</span><span class="sxs-lookup"><span data-stu-id="78d3a-p146">To import a PST file to an inactive mailbox, you have to specify the mailbox GUID for this parameter. To obtain this GUID, run the following PowerShell command in Exchange Online:  \`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly</span></span> | <span data-ttu-id="78d3a-303">FL Guid` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-mailbox<identity of active mailbox></span><span class="sxs-lookup"><span data-stu-id="78d3a-303">FL Guid` <br/> > [!NOTE]> In some cases, you might have multiple mailboxes with the same email address, where one mailbox is an active mailbox and the other mailbox is in a soft-deleted (or inactive) state. In these situations, you have to specify the mailbox GUID to uniquely identify the mailbox to import the PST file to. To obtain this GUID for active mailboxes, run the following PowerShell command:  `Get-Mailbox <identity of active mailbox></span></span> | <span data-ttu-id="78d3a-304">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span><span class="sxs-lookup"><span data-stu-id="78d3a-304">FL Guid`. To obtain the GUID for soft-deleted (or inactive) mailboxes, run this command:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox</span></span> | <span data-ttu-id="78d3a-305">FL Guid。</span><span class="sxs-lookup"><span data-stu-id="78d3a-305">FL Guid\`.</span></span>           | `annb@contoso.onmicrosoft.com` <br/> <span data-ttu-id="78d3a-306">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-306">Or</span></span>  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | <span data-ttu-id="78d3a-p147">指定是否要将 PST 文件导入到用户的存档邮箱。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="78d3a-p147">Specifies whether or not to import the PST file to the user's archive mailbox. There are two options:  </span></span><br/> <span data-ttu-id="78d3a-309">**FALSE**PST 文件导入到用户的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="78d3a-309">**FALSE** Imports the PST file to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="78d3a-p148">**TRUE**将 PST 文件导入到用户的存档邮箱。这假定[已启用用户的存档邮箱](enable-archive-mailboxes.md)。如果将此参数设置为`TRUE`和用户的存档邮箱未启用，为该用户导入将失败。请注意，如果导入失败的一个用户 (因为其归档未启用，此属性设置为`TRUE`)，不会影响导入作业中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p148">**TRUE** Imports the PST file to the user's archive mailbox. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). If you set this parameter to  `TRUE` and the user's archive mailbox isn't enabled, the import for that user will fail. Note that if an import fails for one user (because their archive isn't enabled and this property is set to  `TRUE`), the other users in the import job won't be affected.  </span></span><br/>  <span data-ttu-id="78d3a-314">如果将此参数留空，PST 文件导入到用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d3a-314">If you leave this parameter blank, the PST file is imported to the user's primary mailbox.</span></span>  <br/> <span data-ttu-id="78d3a-315">**注意：** PST 文件导入到其主邮箱位于内部部署用户的基于云的存档邮箱中，只需指定`TRUE`为此参数指定用户的内部部署邮箱的电子邮件地址和`Mailbox`参数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-315">**Note:** To import a PST file to a cloud-based archive mailbox for a user whose primary mailbox is on-premises, just specify  `TRUE` for this parameter and specify the email address for the user's on-premises mailbox for the  `Mailbox` parameter.</span></span>  <br/> | `FALSE` <br/> <span data-ttu-id="78d3a-316">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-316">Or</span></span>  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | <span data-ttu-id="78d3a-317">指定 PST 文件导入到的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="78d3a-317">Specifies the mailbox folder that the PST file is imported to.</span></span>  <br/>  <span data-ttu-id="78d3a-318">如果将此参数留空，PST 将导入到新文件夹命名的**导入**位于 （相同级别的收件箱文件夹和其他默认邮箱文件夹） 的邮箱的根级别。</span><span class="sxs-lookup"><span data-stu-id="78d3a-318">If you leave this parameter blank, the PST will be imported to a new folder named **Imported** located at the root level of the mailbox (the same level as the Inbox folder and the other default mailbox folders).</span></span>  <br/>  <span data-ttu-id="78d3a-319">如果指定`/`，PST 文件中的项目在导入将直接在用户的收件箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="78d3a-319">If you specify  `/`, items in the PST file will be imported directly in to the user's Inbox folder.</span></span>  <br/>  <span data-ttu-id="78d3a-p149">如果指定`/<foldername>`，PST 文件中的项目将导入到一个名为文件夹*\<foldername\> * 。例如，如果您使用`/ImportedPst`，项目将导入到一个名为**ImportedPst**文件夹。此文件夹将位于收件箱文件夹相同级别的用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p149">If you specify  `/<foldername>`, items in the PST file will be imported to a folder named  *\<foldername\>*  . For example, if you use  `/ImportedPst`, items would be imported to a folder named **ImportedPst**. This folder will be located in the user's mailbox at the same level as the Inbox folder.  </span></span><br/> |<span data-ttu-id="78d3a-323">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="78d3a-323">(leave blank)</span></span>  <br/> <span data-ttu-id="78d3a-324">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-324">Or</span></span>  <br/>  `/` <br/> <span data-ttu-id="78d3a-325">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-325">Or</span></span>  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |<span data-ttu-id="78d3a-p150">此可选参数指定要用于导入 PST 文件中的 ANSI 文件格式的代码页的数字值。此参数用于中文、 日语和朝鲜语 (CJK) 的组织中导入 PST 文件，因为这些语言通常用于双字节字符集 (DBCS) 字符编码。如果此参数不用于导入 PST 文件的邮箱文件夹名称中使用 DBCS 的语言，文件夹名称是通常会乱码后会在导入。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p150">This optional parameter specifies a numeric value for the code page to use for importing PST files in the ANSI file format. This parameter is used for importing PST files from Chinese, Japanese, and Korean (CJK) organizations because these languages typically use a double byte character set (DBCS) for character encoding. If this parameter isn't used to import PST files for languages that use DBCS for mailbox folder names, the folder names are often garbled after they're imported.  </span></span><br/> <span data-ttu-id="78d3a-329">有关受支持的值用于此参数的列表，请参阅[代码页标识符](https://go.microsoft.com/fwlink/p/?LinkId=328514)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-329">For a list of supported values to use for this parameter, see [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).</span></span>  <br/> <span data-ttu-id="78d3a-p151">> [!NOTE]> 如上文所述，这是一个可选参数，并且没有要包含在 CSV 文件中。或者，您可以将其包括并保留为空的一个或多个行。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p151">> [!NOTE]> As previously stated, this is an optional parameter and you don't have to include it in the CSV file. Or you can include it and leave the value blank for one or more rows.</span></span>           |<span data-ttu-id="78d3a-332">（保留为空白）</span><span class="sxs-lookup"><span data-stu-id="78d3a-332">(leave blank)</span></span>  <br/> <span data-ttu-id="78d3a-333">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-333">Or</span></span>  <br/>  <span data-ttu-id="78d3a-334">`932`（这是代码页标识符的 ANSI/OEM 日语）</span><span class="sxs-lookup"><span data-stu-id="78d3a-334">`932` (which is the code page identifier for ANSI/OEM Japanese)</span></span>  <br/> |
    | `SPFileContainer` <br/> |<span data-ttu-id="78d3a-335">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-335">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="78d3a-336">不适用</span><span class="sxs-lookup"><span data-stu-id="78d3a-336">Not applicable</span></span>  <br/> |
    | `SPManifestContainer` <br/> |<span data-ttu-id="78d3a-337">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-337">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="78d3a-338">不适用</span><span class="sxs-lookup"><span data-stu-id="78d3a-338">Not applicable</span></span>  <br/> |
    | `SPSiteUrl` <br/> |<span data-ttu-id="78d3a-339">对于 PST 导入，将该参数留空。 </span><span class="sxs-lookup"><span data-stu-id="78d3a-339">For PST Import, leave this parameter blank.</span></span>  <br/> |<span data-ttu-id="78d3a-340">不适用</span><span class="sxs-lookup"><span data-stu-id="78d3a-340">Not applicable</span></span>  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a><span data-ttu-id="78d3a-341">步骤 4：在 Office 365 中创建 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="78d3a-341">Step 4: Create a PST Import job in Office 365</span></span>

<span data-ttu-id="78d3a-p152">下一步是创建 Office 365 中导入服务中的 PST 导入作业。如前所述，您将提交您在步骤 3 中创建的 PST 导入映射文件。创建新的作业后，导入服务将使用的信息映射文件中的 PST 文件从硬盘复制到 Azure 存储区，并创建并启动导入作业后，PST 文件导入到指定的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p152">The next step is to create the PST Import job in the Import service in Office 365. As previously explained, you will submit the PST Import mapping file that you created in Step 3. After you create the new job, the Import service will use the information in the mapping file to import the PST files to the specified user mailbox after the PST files are copied from the hard drive to the Azure storage area and you create and start the import job.</span></span>
  
1. <span data-ttu-id="78d3a-345">转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-345">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="78d3a-346">在左侧窗格中的安全&amp;合规性中心，单击**数据调控**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-346">In the left pane of the Security &amp; Compliance Center, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="78d3a-347">在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-347">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78d3a-348">如上文所述，您需要分配适当的权限访问安全中的**导入**页上&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="78d3a-348">As previously stated, you have to be assigned the appropriate permissions to access the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
4. <span data-ttu-id="78d3a-p153">为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p153">Type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="78d3a-352">在**选择导入作业类型**页上，单击**传送硬盘驱动器到我们的物理位置之一**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-352">On the **Choose import job type** page, click **Ship hard drives to one of our physical locations** and then click **Next**.</span></span>
    
    ![单击传送到我们的物理位置创建驱动器传送导入作业之一硬盘驱动器](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. <span data-ttu-id="78d3a-354">在步骤 6 中，单击和**我已准备好我硬盘驱动器并有权访问所需的驱动器日志文件****有访问权限的映射文件**复选框，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-354">In step 6, click the **I've prepared my hard drives and have access to the necessary drive journal files** and **I have access to the mapping file** check boxes, and then click **Next**.</span></span>
    
    ![单击在步骤 6 中的两个复选框](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. <span data-ttu-id="78d3a-p154">在**选择驱动器文件**页上，单击**选择驱动器文件**，，然后转到 WAImportExport.exe 工具所在的同一文件夹。在步骤 2 中创建的日志文件将被复制到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p154">On the **Select the drive file** page, click **Select drive file**, and then go to the same folder where the WAImportExport.exe tool is located. The journal file that was created in Step 2 was copied to this folder.</span></span>
    
    ![单击选择驱动器文件以提交运行 WAImportExport.exe 工具时创建的日志文件](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. <span data-ttu-id="78d3a-359">选择的日志文件;例如， `PSTHDD1.jrn`。</span><span class="sxs-lookup"><span data-stu-id="78d3a-359">Select the journal file; for example, `PSTHDD1.jrn`.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="78d3a-360">当您在步骤 2 中运行 WAImportExport.exe 工具时，日志文件的名称已指定`/j:`参数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-360">When you ran the WAImportExport.exe tool in Step 2, the name of the journal file was specified by the  `/j:` parameter.</span></span> 
  
9. <span data-ttu-id="78d3a-361">驱动器文件的名称出现在**文件名称**下后，单击**验证**检查驱动器文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="78d3a-361">After the name of the drive file appears under **Drive file name**, click **Validate** to check your drive file for errors.</span></span> 
    
    ![单击验证来验证所选驱动器文件](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    <span data-ttu-id="78d3a-p155">驱动器文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，包含有关文件失败的原因的信息的错误消息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p155">The drive file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message with information about why the file failed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="78d3a-367">您必须添加并验证每个硬盘向 Microsoft 附带的日志文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-367">You must add and validate a journal file for each hard drive you ship to Microsoft.</span></span> 
  
10. <span data-ttu-id="78d3a-368">添加和验证您将向 Microsoft 提供的每个硬盘的日志文件之后, 单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-368">After adding and validating a journal file for each hard drive that you'll ship to Microsoft, click **Next**.</span></span>
    
11. <span data-ttu-id="78d3a-369">单击![添加图标](media/ITPro-EAC-AddIcon.gif)**选择映射文件**以提交您在步骤 3 中创建的 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-369">Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Select mapping file** to submit the PST Import mapping file that you created in Step 3.</span></span> 
    
    ![单击选择映射文件以提交您创建的导入作业的 CSV 文件](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. <span data-ttu-id="78d3a-371">后的 CSV 名称文件显示在**映射文件名称**下，单击**验证**检查 CSV 文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="78d3a-371">After the name of the CSV file appears under **Mapping file name**, click **Validate** to check your CSV file for errors.</span></span> 
    
    ![单击验证检查 CSV 文件中的错误](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    <span data-ttu-id="78d3a-p156">CSV 文件已成功验证创建 PST 导入作业。请注意成功验证后，更改文件名为绿色。如果验证失败，请单击**查看日志**链接。打开时验证错误报告，失败的文件中的各行的错误消息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p156">The CSV file has to be successfully validated to create a PST Import job. Note the file name is changed to green after it's successfully validated. If the validation fails, click the **View log** link. A validation error report is opened, with a error message for each row in the file that failed.</span></span> 
    
13. <span data-ttu-id="78d3a-377">在成功验证 PST 映射文件后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-377">After the PST mapping file is successfully validated, click **Next**.</span></span>
    
14. <span data-ttu-id="78d3a-378">在**提供联系信息**页上，在相应的框中键入您的联系人信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-378">On the **Provide contact information** page, type your contact information in the applicable boxes.</span></span> 
    
    <span data-ttu-id="78d3a-p157">请注意，将显示您将提供给您硬盘 Microsoft 位置的地址。此地址是自动生成基于 Office 365 数据中心位置。将此地址复制到文件或屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p157">Note that the address for the Microsoft location that you will ship your hard drives to is displayed. This address is auto-generated based on your Office 365 data center location. Copy this address to a file or take a screenshot.</span></span>
    
15. <span data-ttu-id="78d3a-382">阅读条款和条件文档，单击复选框，然后单击**保存**以提交导入作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-382">Read the terms and conditions document, click the checkbox, and then click **Save** to submit the import job.</span></span> 
    
    <span data-ttu-id="78d3a-383">导入作业已成功创建，会显示的状态页，其中说明传送过程的驱动器的下一个步骤。</span><span class="sxs-lookup"><span data-stu-id="78d3a-383">When the import job is successfully created, a status page is displayed that explains the next steps of the drive shipping process.</span></span>
    
16. <span data-ttu-id="78d3a-p158">在**导入**页上单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)到**刷新**显示传送导入作业的导入作业列表中的新驱动器。请注意，将状态设置为**等待跟踪号码**。您还可以单击导入作业以显示状态弹出页，其中包含有关导入作业的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p158">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to displayed the new drive shipping import job in the list of import jobs. Note that the status is set to **Waiting for tracking number**. You can also click the import job to display the status flyout page, which contains more detailed information about the import job.</span></span>
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a><span data-ttu-id="78d3a-387">步骤 5：将硬盘驱动器寄送到 Microsoft</span><span class="sxs-lookup"><span data-stu-id="78d3a-387">Step 5: Ship the hard drive to Microsoft</span></span>

<span data-ttu-id="78d3a-p159">下一步是附带的硬盘中向 Microsoft，然后向物料过程提供跟踪号和返回发货驱动器传送作业的信息。驱动器接收由 Microsoft 后，将花费多之间 7 和 10 个工作日的数据中心工作人员将 PST 文件上传到您的组织的 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p159">The next step is to ship the hard drive to Microsoft, and then provide the tracking number for the shipment and return shipment information for the drive shipping job. After the drive is received by Microsoft, it will take between 7 and 10 business days for data center personnel to upload your PST files to the Azure storage area for your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78d3a-p160">如果您没有提供的跟踪数量和返回物料过程信息的创建导入作业 14 天内，将过期导入作业。如果发生这种情况，您将需要创建新的驱动器传送导入作业 (请参阅[步骤 4： 在 Office 365 中创建的 PST 导入作业](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) 和重新提交驱动器文件和 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p160">If you don't provide the tracking number and return shipment information within 14 days of creating the import job, the import job will be expired. If this happens, you'll have to create a new drive shipping import job (see [Step 4: Create a PST Import job in Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step4)) and re-submit the drive file and the PST import mapping file.</span></span> 
  
### <a name="ship-the-hard-drive"></a><span data-ttu-id="78d3a-392">寄送硬盘驱动器</span><span class="sxs-lookup"><span data-stu-id="78d3a-392">Ship the hard drive</span></span>

<span data-ttu-id="78d3a-393">将硬盘驱动器寄送到 Microsoft 时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="78d3a-393">Keep the following things in mind when you ship hard drives to Microsoft:</span></span>
  
- <span data-ttu-id="78d3a-394">不附带的 SATA 到 USB 适配器;您只需附带的硬盘中。</span><span class="sxs-lookup"><span data-stu-id="78d3a-394">Don't ship the SATA-to-USB adapter; you only have to ship the hard drive.</span></span>
    
- <span data-ttu-id="78d3a-395">妥善打包硬盘驱动器，例如，使用防静电袋或泡沫包装。</span><span class="sxs-lookup"><span data-stu-id="78d3a-395">Package the hard drive properly; for example, use an anti-static bag or bubble wrap.</span></span>
    
- <span data-ttu-id="78d3a-396">使用您所选择的交付承运人将硬盘驱动器寄送到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="78d3a-396">Use a delivery carrier of your choice to ship the hard drive to Microsoft.</span></span>
    
- <span data-ttu-id="78d3a-p161">附带的硬盘中为您在步骤 4 中创建导入作业时所显示的 Microsoft 位置的地址。请务必传送到地址中包含"Office 365 导入服务"。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p161">Ship the hard drive to the address for the Microsoft location that was displayed when you created the import job in Step 4. Be sure to include "Office 365 Import Service" in the ship-to address.</span></span>
    
- <span data-ttu-id="78d3a-p162">寄送硬盘驱动器之后，请务必记下交付承运人的名称和跟踪号。您将在下一步中提供这些信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p162">After you ship the hard drive, be sure to write down the name of the delivery carrier and the tracking number. You'll provide these in the next step.</span></span>
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a><span data-ttu-id="78d3a-401">输入跟踪号和其他寄送信息</span><span class="sxs-lookup"><span data-stu-id="78d3a-401">Enter the tracking number and other shipping information</span></span>

<span data-ttu-id="78d3a-402">将硬盘驱动器寄送到 Microsoft 后，在导入服务页上完成以下过程。</span><span class="sxs-lookup"><span data-stu-id="78d3a-402">After you've shipped the hard drive to Microsoft, complete the following procedure on the Import service page.</span></span>
  
1. <span data-ttu-id="78d3a-403">转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-403">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="78d3a-404">在左窗格中，单击**数据管理**，然后单击**导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-404">In the left pane, click **Data governance** and then click **Import**.</span></span>
    
3. <span data-ttu-id="78d3a-405">在**导入**页上，单击适用于您想要输入的跟踪号驱动器货运作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-405">On the **Import** page, click the job for the drive shipment that you want to enter the tracking number for.</span></span> 
    
4. <span data-ttu-id="78d3a-406">在状态弹出页，单击**Enter 跟踪号**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-406">On the status flyout page, click **Enter tracking number**.</span></span>
    
5. <span data-ttu-id="78d3a-407">请提供下列发货信息：</span><span class="sxs-lookup"><span data-stu-id="78d3a-407">Provide the following shipping information:</span></span>
    
1. <span data-ttu-id="78d3a-408">**传递运营商**键入用于附带的硬盘中向 Microsoft 传递运营商的名称。</span><span class="sxs-lookup"><span data-stu-id="78d3a-408">**Delivery carrier** Type the name of the delivery carrier that you used to ship the hard drive to Microsoft.</span></span> 
    
2. <span data-ttu-id="78d3a-409">**跟踪数**键入硬盘运送跟踪数。</span><span class="sxs-lookup"><span data-stu-id="78d3a-409">**Tracking number** Type the tracking number for the hard drive shipment.</span></span> 
    
3. <span data-ttu-id="78d3a-p163">**返回运营商帐号**键入**返回运营商**下列出的运营商贵组织的帐户数。Microsoft 将使用 （和容量） 附带发回给您的硬盘空间此帐户。注意在美国和欧洲，组织必须具有 FedEx 的帐户。在亚洲和世界各地的其余部分的组织必须具有 DHL 的帐户。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p163">**Return carrier account number** Type your organization's account number for the carrier that listed under **Return carrier**. Microsoft will use (and charge) this account to ship your hard drive back to you. Note that organizations in the USA and Europe, must have an account with FedEx. Organizations in Asia and the rest of the world, must have an account with DHL.</span></span>
    
6. <span data-ttu-id="78d3a-414">单击**保存**以保存的导入作业此信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-414">Click **Save** to save this information for the import job.</span></span> 
    
    <span data-ttu-id="78d3a-p164">在**导入**页上单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新为驱动器传送导入作业的信息。请注意，状态现在设置为**驱动器在传输过程中**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p164">On the **Import** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the information for your drive shipping import job. Notice that status is now set to **Drives in transit**.</span></span>

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a><span data-ttu-id="78d3a-417">步骤 6： 筛选数据，并启动 PST 导入作业</span><span class="sxs-lookup"><span data-stu-id="78d3a-417">Step 6: Filter data and start the PST Import job</span></span>

<span data-ttu-id="78d3a-p165">您的硬盘接收由 Microsoft 后，**导入**页上的导入作业的状态将更改为**驱动器收到**。数据中心人员将使用日志文件中的信息将 PST 文件上传到您的组织的 Azure 存储区。此时，状态将更改为**导入正在进行**。如前面所述，将花费多之间 7 至 10 工作日后接收硬盘上载 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p165">After your hard drive is received by Microsoft, the status for the import job on the **Import** page will change to **Drives received**. Data center personnel will use the information in the journal file to upload your PST files to the Azure storage area for your organization. At this point, the status will change to **Import in-progress**. As previously stated, it will take between 7 to 10 business days after receiving your hard drive to upload the PST files.</span></span>
  
<span data-ttu-id="78d3a-p166">PST 文件上载到 Azure 后，状态更改为**正在进行分析**。这指示的 Office 365 正在分析 PST 文件中的数据 （以安全方式） 来标识的项目和 PST 文件中包含的其他消息类型的期限。在完成分析，并且已准备好导入数据，导入作业的状态将更改为**完成分析**。此时，您可以选择要导入 PST 文件中包含的所有数据，或可修剪通过设置控制哪些数据获取导入的筛选器导入的数据。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p166">After PST files are uploaded to Azure, the status is changed to **Analysis in progress**. This indicates that Office 365 is analyzing the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When the analysis is completed and the data is ready to import, the status for the import job is changed to **Analysis completed**. At this point, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span>
  
1. <span data-ttu-id="78d3a-426">转到[https://protection.office.com](https://protection.office.com)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-426">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="78d3a-427">在左窗格中，单击**数据调控** > **导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-427">In the left pane, click **Data governance** > **Import**.</span></span>
    
3. <span data-ttu-id="78d3a-428">在**导入**页上，单击您在步骤 4 中创建的导入作业**已准备好导入到 Office 365** 。</span><span class="sxs-lookup"><span data-stu-id="78d3a-428">On the **Import** page, click **Ready to import to Office 365** for the import job that you created in Step 4.</span></span> 
    
    ![单击您创建的导入作业旁边导入到 Office 365 准备](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    <span data-ttu-id="78d3a-430">飞出页将显示有关 PST 文件的信息以及其他信息导入作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-430">A fly out page is displayed with information about the PST files and other information about the import job.</span></span>
    
4. <span data-ttu-id="78d3a-431">单击**导入到 Office 365**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-431">Click **Import to Office 365**.</span></span>
    
5. <span data-ttu-id="78d3a-p167">显示**筛选数据**页。它包含生成 Office 365，包括有关数据的期限对 PST 文件执行分析数据见解。此时，您可以选择要筛选的数据将导入或导入原样的所有数据。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p167">The **Filter your data** page is displayed. It contains the data insights resulting from the analysis performed on the PST files by Office 365, including information about the age of the data. At this point, you have the option to filter the data that will be imported or import all the data as is.</span></span> 
    
    ![您可以修整 PST 文件中的数据或导入的所有](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. <span data-ttu-id="78d3a-436">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="78d3a-436">Do one of the following:</span></span>
    
    <span data-ttu-id="78d3a-p168">答： 来裁切导入的数据，请单击**是，我希望筛选其之前导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p168">a. To trim the data that you import, click **Yes, I want to filter it before importing**.</span></span>
    
    <span data-ttu-id="78d3a-439">有关筛选 PST 文件中的数据，然后启动导入作业的详细分步说明，请参阅[筛选器数据导入 PST 文件迁移到 Office 365 时](filter-data-when-importing-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-439">For detailed step-by-step instructions about filtering the data in the PST files and then starting the import job, see [Filter data when importing PST files to Office 365](filter-data-when-importing-pst-files.md).</span></span>
    
    <span data-ttu-id="78d3a-440">或</span><span class="sxs-lookup"><span data-stu-id="78d3a-440">Or</span></span>
    
    <span data-ttu-id="78d3a-p169">b.若要导入 PST 文件中的所有数据中,，单击**否，我想要导都入的所有内容，** 然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p169">b. To import all data in the PST files, click **No, I want to import everything,** and click **Next**.</span></span>
    
7. <span data-ttu-id="78d3a-443">如果您选择要导入的所有数据，请单击都**导都入数据**以启动导都入作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-443">If you chose to import all the data, click **Import data** to start the import job.</span></span> 
    
    <span data-ttu-id="78d3a-p170">在**导入**页上显示的导入作业的状态。单击![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)**刷新**以更新**状态**列中显示的状态信息。单击显示状态弹出页，显示状态信息正在导入每个 PST 文件导入作业。导入完成后，PST 文件导入到用户邮箱，状态将更改为**已完成**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p170">The status of the import job is displayed on the **Import** page. Click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status information that's displayed in the **Status** column. Click the import job to display the status flyout page, which displays status information about each PST file being imported. When the import is complete and PST files have been imported to user mailboxes, the status will be changed to **Completed**.</span></span>

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a><span data-ttu-id="78d3a-448">查看上载到 Office 365 的 PST 文件的列表</span><span class="sxs-lookup"><span data-stu-id="78d3a-448">View a list of the PST files uploaded to Office 365</span></span>

<span data-ttu-id="78d3a-p171">您可以安装和使用 Microsoft Azure 存储资源管理器 （这是一个免费的开源工具） 查看我们您上载到该文档 （通过 Microsoft 数据中心人员） 为您的组织的 Azure 存储区的 PST 文件的列表。您可以执行此操作以验证从您向 Microsoft 发送的硬盘的 PST 文件已成功上载到 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p171">You can install and use the Microsoft Azure Storage Explorer (which is a free, open source tool) to view the list of the PST files that we're uploaded (by Microsoft data center personnel) to the Azure storage area for your organization. You can do this to verify that PST files from the hard drives that you sent to Microsoft were successfully uploaded to the Azure storage area.</span></span>
  
<span data-ttu-id="78d3a-451">Microsoft Azure 存储 Explorer 正处于预览。</span><span class="sxs-lookup"><span data-stu-id="78d3a-451">The Microsoft Azure Storage Explorer is in Preview.</span></span>
  
 <span data-ttu-id="78d3a-p172">**重要：** 不能使用 Azure 存储资源管理器上载或修改 PST 文件。将 PST 文件导入到 Office 365 唯一受支持的方法是使用 AzCopy。此外，您不能删除已上载到 Azure blob 的 PST 文件。如果尝试删除 PST 文件，您会收到了有关未获得所需的权限的错误。请注意自动从您 Azure 存储区删除所有 PST 文件。如果没有导入作业正在运行，则所有 PST 文件中的 * * ingestiondata * * 容器被删除 30 天后创建的最新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p172">**Important:** You can't use the Azure Storage Explorer to upload or modify PST files. The only supported method for importing PST files to Office 365 is to use AzCopy. Also, you can't delete PST files that you've uploaded to the Azure blob. If you try to delete a PST file, you'll receive an error about not having the required permissions. Note that all PST files are automatically deleted from your Azure storage area. If there are no import jobs in progress, then all PST files in the ** ingestiondata ** container are deleted 30 days after the most recent import job was created.</span></span> 
  
<span data-ttu-id="78d3a-458">安装 Azure 存储浏览器并连接到 Azure 存储区：</span><span class="sxs-lookup"><span data-stu-id="78d3a-458">To install the Azure Storage Explorer and connect to your Azure storage area:</span></span>
  
1. <span data-ttu-id="78d3a-p173">执行以下步骤以获取您的组织共享访问签名 (SA) URL。此 URL 是 Microsoft 云的组织和 SAS 键中的 Azure 存储位置的网络 URL 的组合。此项为您提供所需的权限访问组织的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p173">Perform the following steps to get the Shared Access Signature (SAS) URL for your organization. This URL is a combination of the network URL for the Azure storage location in the Microsoft cloud for your organization and an SAS key. This key provides you with the necessary permissions to access your organization's Azure storage location.</span></span>
    
1. <span data-ttu-id="78d3a-462">转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="78d3a-462">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="78d3a-463">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **导入**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-463">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Import**.</span></span>
    
3. <span data-ttu-id="78d3a-464">在**导入**页上单击![添加图标](media/ITPro-EAC-AddIcon.gif)**新建导入作业**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-464">On the **Import** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New import job**.</span></span>
    
4. <span data-ttu-id="78d3a-p174">在导入作业向导中，为 PST 导入作业中，键入一个名称，然后单击**下一步**。使用小写字母、 数字、 连字符和下划线。您无法使用大写字母或名称中包含空格。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p174">In the import job wizard, type a name for the PST import job, and then click **Next**. Use lowercase letters, numbers, hyphens, and underscores. You can't use uppercase letters or include spaces in the name.</span></span>
    
5. <span data-ttu-id="78d3a-468">在**选择导入作业类型**页上，单击**上载数据**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-468">On the **Choose import job type** page, click **Upload your data** and then click **Next**.</span></span>
    
6. <span data-ttu-id="78d3a-469">在步骤 2 中，单击**显示网络上载 SAS URL**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-469">In step 2, click **Show network upload SAS URL**.</span></span>
    
7. <span data-ttu-id="78d3a-p175">显示 URL 后，将其复制，并将其保存到文件。请务必将复制的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p175">After the URL is displayed, copy it and save it to a file. Be sure to copy the entire URL.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="78d3a-p176">请确保采取预防措施来保护 SAS URL。这可以用于人访问您的组织的 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p176">Be sure to take precautions to protect the SAS URL. This can be used by anyone to access the Azure storage area for your organization.</span></span> 
  
8. <span data-ttu-id="78d3a-474">单击**取消**以关闭导入作业向导。</span><span class="sxs-lookup"><span data-stu-id="78d3a-474">Click **Cancel** to close the import job wizard.</span></span> 
    
2. <span data-ttu-id="78d3a-475">下载并安装[Microsoft Azure 存储资源管理器工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-475">Download and install the [Microsoft Azure Storage Explorer tool](https://go.microsoft.com/fwlink/p/?LinkId=544842).</span></span>
    
3. <span data-ttu-id="78d3a-476">启动 Microsoft Azure 存储资源管理器，在左窗格中右键单击**存储帐户**，然后单击**连接到 Azure 存储**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-476">Start the Microsoft Azure Storage Explorer, right-click **Storage Accounts** in the left pane, and then click **Connect to Azure storage**.</span></span>
    
    ![右键单击存储帐户，然后单击连接到 Azure 存储](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. <span data-ttu-id="78d3a-478">单击**使用共享的访问签名 (SA) URI 或连接字符串**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-478">Click **Use a shared access signature (SAS) URI or connection string** and click **Next**.</span></span>
    
5. <span data-ttu-id="78d3a-479">单击**使用 SAS URI**，将您获得 SAS URL 粘贴步骤 1 中到**URI**下的框中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-479">Click **Use a SAS URI**, paste the SAS URL that you obtained in step 1 in to in the box under **URI**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="78d3a-480">在**连接摘要**页中，您可以查看连接信息，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-480">On the **Connection summary** page, you can review the connection information, and then click **Connect**.</span></span>
    
    <span data-ttu-id="78d3a-p177">打开**ingestiondata**容器;它包含您的硬盘的 PST 文件。**Ingestiondata**容器位于**存储帐户**下\> **（SAS-Attached 服务）** \> **Blob 容器**。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p177">The **ingestiondata** container is opened; it contains the PST files from your hard drive. The **ingestiondata** container is located under **Storage Accounts** \> **(SAS-Attached Services)** \> **Blob Containers**.</span></span>
    
    ![Azure 存储资源管理器显示你上载的 PST 文件的列表](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. <span data-ttu-id="78d3a-p178">完成后使用 Microsoft Azure 存储浏览器，右键单击**ingestiondata**，，然后单击**分离**断开 Azure 存储区。否则，您会收到错误的下次尝试附加。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p178">When you're finished using the Microsoft Azure Storage Explorer, right-click **ingestiondata**, and then click **Detach** to disconnect from your Azure storage area. Otherwise, you'll receive an error the next time you try to attach.</span></span> 
    
    ![右键单击“引入”，然后单击“分离”以从 Azure 存储区域断开连接](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  

  
## <a name="troubleshooting-tips"></a><span data-ttu-id="78d3a-487">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="78d3a-487">Troubleshooting tips</span></span>
<span data-ttu-id="78d3a-488"><a name="troubleshootingtips"> </a></span><span class="sxs-lookup"><span data-stu-id="78d3a-488"></span></span>

- <span data-ttu-id="78d3a-p179">**由于错误 PST 导入 CSV 映射文件中导入作业失败时，会发生什么情况？** 如果导入作业失败由于映射文件中的错误，您无需重新附带的硬盘中向 Microsoft，以创建新的导入作业。这是因为您提交的硬盘的 PST 文件驱动器传送导入作业已经上载到您的组织的 Azure 存储区。在这种情况下，您只需要在 PST 导入 CSV 映射文件中，修复错误然后创建一个新的"网络上载"导入作业并提交修订后的 CSV 映射文件。若要创建并启动新的网络上载导入作业，请参阅[步骤 5： 在 Office 365 中创建的 PST 导入作业](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365)和[步骤 6： 筛选数据，并启动 PST 导入作业](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)主题中的"使用网络上载到 Office 365 导入 PST 文件。"</span><span class="sxs-lookup"><span data-stu-id="78d3a-p179">**What happens if the import job fails because of errors in the PST Import CSV mapping file?** If an import job fails because of errors in the mapping file, you don't have to re-ship the hard drive to Microsoft in order to create a new import job. That's because the PST files from the hard drive that you submitted for the drive shipping import job have already been uploaded to the Azure storage area for your organization. In this case, you just have to fix the errors in the PST Import CSV mapping file, and then create a new "network upload" import job and submit the revised CSV mapping file. To create and start a new network upload import job, see [Step 5: Create a PST Import job in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) and [Step 6: Filter data and start the PST Import job](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) in the topic "Use network upload to import PST files to Office 365."</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="78d3a-p180">为了帮助您解决 PST 导入 CSV 映射文件，使用[Azure 存储资源管理器](#view-a-list-of-the-pst-files-uploaded-to-office-365)工具查看**ingestiondata**容器的 PST 文件从您的硬盘已上载到 Azure 存储区中的文件夹结构。映射文件错误通常致 FilePath 参数中的正确值。此参数指定在 Azure 存储区 PST 文件的位置。请参阅 FilePath 参数[步骤 3](#step-3-create-the-pst-import-mapping-file)中的表中的说明。如前所述，通过指定的 Azure 存储区中的 PST 文件的位置`/dstdir:`参数，当您在[步骤 2](#step-2-copy-the-pst-files-to-the-hard-drive)中运行该 WAImportExport.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p180">To help you troubleshoot the PST Import CSV mapping file, use the [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) tool to view the folder structure in the **ingestiondata** container for the PST files from your hard drive that were uploaded to the Azure storage area. Mapping file errors are typically caused by an incorrect value in the FilePath parameter. This parameter specifies the location of a PST file in the Azure storage area. See the description of the FilePath parameter in table in [Step 3](#step-3-create-the-pst-import-mapping-file). As previously explained, the location of PST files in the Azure storage area was specified by the  `/dstdir:` parameter when you ran the WAImportExport.exe tool in [Step 2](#step-2-copy-the-pst-files-to-the-hard-drive).</span></span> 
  

  
## <a name="more-information"></a><span data-ttu-id="78d3a-499">详细信息</span><span class="sxs-lookup"><span data-stu-id="78d3a-499">More information</span></span>

- <span data-ttu-id="78d3a-p181">驱动器传送是有效的方法来将大量存档的消息数据导入到 Office 365 利用供您的组织的合规性功能。存档数据导入到用户邮箱后，您可以：</span><span class="sxs-lookup"><span data-stu-id="78d3a-p181">Drive shipping is an effective way to import large amounts of archival messaging data to Office 365 to take advantage of the compliance features that are available to your organization. After archival data is imported to user mailboxes, you can:</span></span>
    
  - <span data-ttu-id="78d3a-502">启用[存档邮箱](enable-archive-mailboxes.md)，并[自动扩展存档](enable-unlimited-archiving.md)为用户提供的数据的其他邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="78d3a-502">Enable [archive mailboxes](enable-archive-mailboxes.md) and [auto-expanding archiving](enable-unlimited-archiving.md) to give users additional mailbox storage space for the data.</span></span> 
    
  - <span data-ttu-id="78d3a-503">将邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)保留数据。</span><span class="sxs-lookup"><span data-stu-id="78d3a-503">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) to retain the data.</span></span> 
    
  - <span data-ttu-id="78d3a-504">使用 Microsoft[电子数据展示工具](search-for-content.md)搜索数据。</span><span class="sxs-lookup"><span data-stu-id="78d3a-504">Use Microsoft [eDiscovery tools](search-for-content.md) to search the data.</span></span> 
    
  - <span data-ttu-id="78d3a-505">应用[Office 365 保留策略](retention-policies.md)以控制数据的保留多长时间，和要采取的保留期过后哪些操作。</span><span class="sxs-lookup"><span data-stu-id="78d3a-505">Apply [Office 365 retention policies](retention-policies.md) to control how long the data is retained, and what action to take after the retention period expires.</span></span> 
    
  - <span data-ttu-id="78d3a-506">搜索[Office 365 审核日志](search-the-audit-log-in-security-and-compliance.md)与该数据相关的事件。</span><span class="sxs-lookup"><span data-stu-id="78d3a-506">Search the [Office 365 audit log](search-the-audit-log-in-security-and-compliance.md) for events related to this data.</span></span> 
    
  - <span data-ttu-id="78d3a-507">数据导入到存档数据，出于合规性目的的[非活动邮箱](create-and-manage-inactive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-507">Import data to [inactive mailboxes](create-and-manage-inactive-mailboxes.md) to archive data for compliance purposes.</span></span> 
    
  - <span data-ttu-id="78d3a-508">保护您的组织防止[数据丢失](data-loss-prevention-policies.md)的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="78d3a-508">Protect your organization against [data loss](data-loss-prevention-policies.md) of sensitive information.</span></span> 
    
- <span data-ttu-id="78d3a-p182">以下是安全存储帐户密钥和 BitLocker 加密密钥的示例。此示例还包含 WAImportExport.exe 命令的语法，运行此命令可将 PST 文件复制到硬盘驱动器。一定要采取预防措施来保护这些文件，就像保护密码或其他与安全相关的信息一样。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p182">Here's an example of the secure storage account key and a BitLocker encryption key. This example also contains the syntax for the WAImportExport.exe command that you run to copy PST files to a hard drive. Be sure to take precautions to protect these just like you would protect passwords or other security-related information.</span></span>
    

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
   
- <span data-ttu-id="78d3a-p183">如前所述，Office 365 导入服务启用设置 （无限期的持续时间） PST 文件导入到邮箱后保留挂起状态。这意味着*RentionHoldEnabled*属性设置为`True`，以便将不会处理分配给邮箱的保留策略。这可以通过防止删除或较旧的消息进行存档的存档策略管理的新导入的邮件的邮箱所有者时间。下面是一些用于管理此保留挂起时可采取的步骤：</span><span class="sxs-lookup"><span data-stu-id="78d3a-p183">As previously explained, the Office 365 Import service turns on the retention hold setting (for an indefinite duration) after PST files are imported to a mailbox. This means the  *RentionHoldEnabled*  property is set to  `True` so that the retention policy assigned to the mailbox won't be processed. This gives the mailbox owner time to manage the newly-imported messages by preventing a deletion or archive policy from deleting or archiving older messages. Here are some steps you can take to manage this retention hold:</span></span> 
    
  - <span data-ttu-id="78d3a-p184">在一段后的时间，则可以关闭保留挂起通过运行`Set-Mailbox -RetentionHoldEnabled $false`命令。有关说明，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/p/?LinkId=544749)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p184">After a certain period of time, you can turn off the retention hold by running the  `Set-Mailbox -RetentionHoldEnabled $false` command. For instructions, see [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/p/?LinkId=544749).</span></span>
    
  - <span data-ttu-id="78d3a-p185">您可以配置保留挂起，以便它已关闭，以便将来一些日期。执行此操作通过运行`Set-Mailbox -EndDateForRetentionHold <date>`命令。例如，假设今天的日期是 2016 年 7 月 1，并且您希望保留保留在 30 天内已关闭，将运行以下命令： `Set-Mailbox -EndDateForRetentionHold 8/1/2016`。在此方案中，将保留*RentionHoldEnabled*属性设置为*True* 。有关详细信息，请参阅[Set-mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p185">You can configure the retention hold so that it's turned off on some date in the future. You do this by running the  `Set-Mailbox -EndDateForRetentionHold <date>` command. For example, assuming that today's date is July 1, 2016 and you want the retention hold turned off in 30 days, you would run the following command:  `Set-Mailbox -EndDateForRetentionHold 8/1/2016`. In this scenario, you would leave the  *RentionHoldEnabled*  property set to  *True*  . For more information, see [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).</span></span>
    
  - <span data-ttu-id="78d3a-p186">您可以更改，以便不会立即删除或移动到用户的存档邮箱均已导入的旧项目分配给邮箱的保留策略的设置。例如，您无法加长删除或存档策略分配给邮箱的保留期限。在此方案中，则会关闭邮箱保留挂起后更改保留策略的设置。有关详细信息，请参阅[Office 365 组织中邮箱的存档和删除策略设置](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="78d3a-p186">You can change the settings for the retention policy that's assigned to the mailbox so that older items that were imported won't be immediately deleted or moved to the user's archive mailbox. For example, you could lengthen the retention age for a deletion or archive policy that's assigned to the mailbox. In this scenario, you would turn off the retention hold on the mailbox after you changed the settings of the retention policy. For more information, see [Set up an archive and deletion policy for mailboxes in your Office 365 organization](set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>
    

  

