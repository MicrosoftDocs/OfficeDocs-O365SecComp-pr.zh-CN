---
title: 将 PST 文件导入到 Office 365 的常见问题解答
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有关使用 office 365 导入服务将 organizaiton 的 PST 文件导入到 office 365 邮箱的管理员的常见问题。 '
ms.openlocfilehash: 9ca2e206a1d06c1398181c51e41b4dc68d8d965c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218402"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="7e3b6-103">将 PST 文件导入到 Office 365 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="7e3b6-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="7e3b6-104">**本文适用于管理员。是否要将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="7e3b6-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="7e3b6-p101">下面是一些有关使用 office 365 导入服务批量导入 PST 文件到 office 365 邮箱的常见问题。有关如何导入 pst 文件的详细信息, 请参阅[将 pst 文件导入到 Office 365 概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p101">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes. For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="7e3b6-107">使用网络上载导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="7e3b6-107">Using network upload to import PST files</span></span>

<span data-ttu-id="7e3b6-108">有关分步说明, 请参阅[使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="7e3b6-109">**在 Office 365 导入服务中创建导入作业所需的权限是什么？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="7e3b6-p102">您必须在 Exchange Online 中分配 "邮箱导入导出" 角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己或其他用户添加为成员。有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p102">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="7e3b6-115">此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:</span><span class="sxs-lookup"><span data-stu-id="7e3b6-115">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="7e3b6-p103">您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p103">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="7e3b6-118">或者</span><span class="sxs-lookup"><span data-stu-id="7e3b6-118">Or</span></span>
    
- <span data-ttu-id="7e3b6-119">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="7e3b6-p104">请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p104">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="7e3b6-122">**网络上传的可用位置是什么？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="7e3b6-p105">网络上传目前适用于美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、朝鲜共和国和澳大利亚。不久将在更多区域中提供网络上载。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p105">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="7e3b6-125">**使用网络上载导入 PST 文件的价格是多少？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="7e3b6-126">使用网络上传来导入 PST 文件是免费的。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="7e3b6-p106">这也意味着, 在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在 Office 365 管理中心中已完成导入作业的文件列表中。尽管导入作业可能仍在 "**导入数据到 Office 365** " 页上列出, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p106">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="7e3b6-129">**导入 Office 365 支持哪种版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="7e3b6-p107">有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用网络上载将组织的 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)" 中的步骤4。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p107">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="7e3b6-134">此外, 还可以将 Outlook 2007 和更高版本中的 PST 文件导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="7e3b6-135">**将 PST 文件上传到 azure 存储区域后, 它们在被删除之前保留在 azure 中的时间是多少？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="7e3b6-p108">使用网络上传方法导入 PST 文件时, 会将这些文件上传到名为**ingestiondata**的 Azure blob 容器中。如果安全&amp;合规中心中的 "**导入**" 页上没有正在进行的导入作业, 则在安全性\*\*\*\* &amp;合规性中心。这也意味着, 您必须在将 PST 文件上传到 Azure &amp;的30天内, 在安全合规中心 (在网络上载说明中的步骤5中介绍) 中创建新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p108">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="7e3b6-p109">这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全&amp;合规性中心中已完成导入作业的文件列表中。尽管安全&amp;合规中心中的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p109">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="7e3b6-141">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p110">这取决于网络的容量, 但通常需要几个小时才能将每 tb 的数据上载到您的组织的 Azure 存储区域。将 pst 文件复制到 Azure 存储区域后, pst 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。如果此比率不能满足您的需求, 则可以考虑将电子邮件数据迁移到 Office 365 的其他方法。有关详细信息, 请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p110">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="7e3b6-p111">如果将不同的 PST 文件导入到不同的目标邮箱, 则导入过程将并行发生;换言之, 每个 PST/邮箱对同时导入。同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p111">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="7e3b6-148">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="7e3b6-p112">是的。如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p112">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="7e3b6-151">**是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p113">是的。在导入过程中不会更改原始的邮件元数据。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p113">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="7e3b6-154">**对于要导入到邮箱中的 PST 文件, 文件夹层次结构中的级别数是否有限制？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p114">是的。您不能导入包含300或更多级别的嵌套文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="7e3b6-157">**可以使用网络上载将 PST 文件导入到 Office 365 中的非活动邮箱吗？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="7e3b6-158">是的, 此功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="7e3b6-159">**是否可以使用网络上载将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="7e3b6-160">是的, 此功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="7e3b6-161">**是否可以使用网络上载将 PST 文件导入到 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="7e3b6-162">否, 不能将 PST 文件导入到公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="7e3b6-163">使用驱动器发货以导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="7e3b6-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="7e3b6-164">有关分步说明, 请参阅[使用驱动器发货将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="7e3b6-165">**在 Office 365 导入服务中创建导入作业所需的权限是什么？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="7e3b6-p115">您必须分配有邮箱导入导出角色, 才能将 PST 文件导入到 Office 365 邮箱。默认情况下, 此角色不会分配给 Exchange Online 中的任何角色组。您可以将邮箱导入导出角色添加到 "组织管理" 角色组。或者, 您可以创建新的角色组, 分配邮箱导入导出角色, 然后将自己或其他用户添加为成员。有关详细信息, 请参阅在[Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的 "将角色添加到角色组" 或 "创建角色组" 部分。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p115">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="7e3b6-171">此外, 若要在 Office 365 安全&amp;合规中心中创建导入作业, 必须满足以下条件之一:</span><span class="sxs-lookup"><span data-stu-id="7e3b6-171">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="7e3b6-p116">您必须在 Exchange Online 中向您分配 "邮件收件人" 角色。默认情况下, 将此角色分配给组织管理和收件人管理角色组。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p116">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="7e3b6-174">或者</span><span class="sxs-lookup"><span data-stu-id="7e3b6-174">Or</span></span>
    
- <span data-ttu-id="7e3b6-175">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="7e3b6-p117">请考虑在 Exchange Online 中创建一个专门用于将 PST 文件导入到 Office 365 的新角色组。若要获取导入 PST 文件所需的最低级别权限, 请将 "邮箱导入导出" 和 "邮件收件人" 角色分配给新的角色组, 然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p117">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="7e3b6-178">**驱动器运输在什么位置？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="7e3b6-p118">目前, 在美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、韩国和澳大利亚都可以使用驱动器运输。很快将在更多区域中提供驱动器运输。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p118">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="7e3b6-181">**哪些商业许可协议支持驱动器传送？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="7e3b6-p119">将 PST 文件导入到 Office 365 的驱动器发货通过 Microsoft 企业协议 (EA) 提供。无法通过 Microsoft 产品和服务协议 (MPSA) 获取驱动器发货。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p119">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="7e3b6-184">**使用驱动器发货将 PST 文件导入到 Office 365 的定价是多少？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="7e3b6-p120">使用驱动器传送将 PST 文件导入到 Office 365 邮箱的成本为每 GB 数据的 $2 美元。例如, 如果您提供的硬盘驱动器包含 1000 GB (1 TB) 的 PST 文件, 则开销为 $2000 USD。你可以与合作伙伴合作以支付进口费用。有关查找合作伙伴的信息, 请参阅[查找 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p120">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="7e3b6-189">**驱动器传送支持哪种类型的硬驱？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="7e3b6-p121">仅2.5 英寸固态驱动器 (ssd) 或2.5 或3.5 英寸 SATA II/III 内置硬盘可与 Office 365 导入服务配合使用。可以使用最大 10 TB 的硬盘驱动器。对于导入作业, 仅会处理硬盘上的第一个数据量。必须使用 NTFS 格式化数据卷。将数据复制到硬盘时, 可以使用2.5 英寸 SSD 或2.5 或3.5 英寸 SATA ii/iii 连接器直接附加它, 也可以使用外部的2.5 英寸 ssd 或2.5 或3.5 英寸 sata ii/iii USB 适配器将其连接到外部。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p121">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7e3b6-p122">内置 USB 适配器附带的外部硬盘驱动器不受 Office 365 导入服务的支持。此外, 不能使用外部硬盘驱动器大小写中的磁盘。请勿发售外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p122">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="7e3b6-198">**我可以为一个导入作业发货多少个硬盘驱动器？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="7e3b6-199">最多可以为一个导入作业发货10个硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="7e3b6-200">**在我发货硬盘后, 获取 Microsoft 数据中心需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="7e3b6-p123">这取决于一些事项, 如您与 Microsoft 数据中心的邻近程度, 以及您用于运输硬盘的运输选项类型 (例如, 下一天交付、两天交付或基础交付)。对于大多数运货商, 您可以使用跟踪号码来跟踪您的交货状态。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="7e3b6-203">**硬盘驱动器到达 Microsoft 数据中心后, 将 PST 文件上传到 Azure 需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="7e3b6-p124">在 Microsoft 数据中心收到硬盘驱动器后, 需要7到10个工作日才能将 PST 文件上传到组织的 Microsoft Azure 存储区域。PST 文件将被上传到名为**ingestiondata**的 Azure blob 容器中。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p124">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="7e3b6-206">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p125">将 pst 文件上传到 Azure 存储区域后, Office 365 将分析 pst 文件中的数据 (以安全和安全的方式), 以确定这些项目的年龄以及 pst 文件中包含的不同邮件类型。完成此分析后, 您可以选择导入 PST 文件中的所有数据, 也可以将筛选器设置为, 以控制导入的数据。在您开始导入作业后, PST 文件将以每日至少 24 GB 的速度导入到 Office 365 邮箱中。如果此比率不能满足您的需求, 则可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息, 请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p125">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="7e3b6-p126">如果将不同的 PST 文件导入到不同的目标邮箱, 则导入过程将并行发生;换言之, 每个 PST/邮箱对同时导入。同样, 如果将多个 PST 文件导入到同一个邮箱, 则会同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p126">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="7e3b6-214">**Microsoft 将我的 PST 文件上载到 azure 后, 它们在被删除之前在 azure 中保留的时间是多少？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="7e3b6-215">在安全&amp;合规中心的 "**导入**" 页上创建最近的导入作业30天后, 将在您的组织的 Azure 存储位置中的所有 PST 文件 (在 blob 容器中为**ingestiondata** ) 删除。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7e3b6-p127">这也意味着在从 Azure 存储区域中删除 PST 文件后, 这些文件将不再显示在安全&amp;合规性中心中已完成导入作业的文件列表中。尽管安全&amp;合规中心中的**导入**页面仍可能会列出导入作业, 但在查看较旧的导入作业的详细信息时, PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="7e3b6-218">**导入 Office 365 支持哪种版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="7e3b6-p128">有两个版本的 PST 文件格式: ANSI 和 Unicode。建议导入使用 Unicode PST 文件格式的文件。但是, 使用 ANSI PST 文件格式的文件 (例如, 使用双字节字符集 (DBCS) 的语言的文件) 也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息, 请参阅 "[使用驱动器传送将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)" 中的步骤3。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p128">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="7e3b6-223">此外, 还可以将 Outlook 2007 和更高版本中的 PST 文件导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="7e3b6-224">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="7e3b6-p129">是的。如果 PST 文件包含大于 150 MB 的邮箱项目, 则在导入过程中将跳过该项目。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="7e3b6-227">**是邮件属性, 例如邮件的发送或接收时间、将 PST 文件导入到 Office 365 邮箱时所保留的收件人和其他属性的列表？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p130">是的。在导入过程中不更改原始邮件元数据</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p130">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="7e3b6-230">**对于要导入到邮箱中的 PST 文件, 文件夹层次结构中的级别数是否有限制？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="7e3b6-p131">是的。您不能导入包含300或更多级别的嵌套文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="7e3b6-233">**我是否可以使用驱动器发货将 PST 文件导入 Office 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="7e3b6-234">是的, 此功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="7e3b6-235">**是否可以使用驱动器发货将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="7e3b6-236">是的, 此功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="7e3b6-237">**我是否可以使用驱动器发货以将 PST 文件导入到 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="7e3b6-238">否, 不能将 PST 文件导入到公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="7e3b6-239">**Microsoft 可以先擦除我的硬盘, 然后再将其传送回我？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="7e3b6-p132">否, Microsoft 无法在将硬驱运输回客户之前将其擦除。硬驱将返回到 Microsoft 收到它们时所处的状态。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="7e3b6-242">**Microsoft 是否可以清除硬盘, 而不是将其传送回我的硬盘？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="7e3b6-p133">否, Microsoft 无法销毁你的硬驱。硬驱将返回到 Microsoft 收到它们时所处的状态。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="7e3b6-245">**退货装运支持哪些快递服务？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="7e3b6-p134">如果你是美国或欧洲的客户, Microsoft 使用 FedEx 返回你的硬盘。对于所有其他地区, Microsoft 使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="7e3b6-248">**退货的送货费用是多少？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="7e3b6-p135">根据您与您发送到的 Microsoft 数据中心的邻近程度, 返回发货费用会有所不同。Microsoft 将向你的 FedEx 或 DHL 帐户计费, 以返回你的硬驱。退货交付的成本是您的责任。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="7e3b6-252">**我可以使用自定义的快递发货服务 (如 FedEx 自定义装运) 将我的硬盘发送到 Microsoft 吗？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="7e3b6-253">可以。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-253">Yes.</span></span>
  
 <span data-ttu-id="7e3b6-254">**如果我需要将我的硬盘驱动器运送到另一个国家/地区, 是否有我需要执行的操作？**</span><span class="sxs-lookup"><span data-stu-id="7e3b6-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="7e3b6-p136">您发布到 Microsoft 的硬盘驱动器可能需要跨国际边框。如果是这种情况, 您将负责确保按照适用的法律导入和/或导出硬盘及其包含的数据。在运送硬盘之前, 请咨询你的顾问以验证你的驱动器和数据是否可以合法发送到指定的 Microsoft 数据中心。这将有助于确保它及时进入 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
