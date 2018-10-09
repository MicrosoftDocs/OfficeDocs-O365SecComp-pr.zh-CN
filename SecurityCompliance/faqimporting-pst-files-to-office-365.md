---
title: 有关将 PST 文件导入到 Office 365 常见问题
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有关使用 Office 365 导入服务将生成组织的 PST 文件导入到 Office 365 邮箱，常见问题 (英文） 的管理员。 '
ms.openlocfilehash: 7230e68f896766df643f12b2a132f987670e9afa
ms.sourcegitcommit: eecf6f3aafbf460ee2ff9988f2b055e62b1fdb9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454049"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="02f98-103">有关将 PST 文件导入到 Office 365 常见问题</span><span class="sxs-lookup"><span data-stu-id="02f98-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="02f98-104">**本文是针对管理员。是否要将 PST 文件导入到您自己的邮箱？请参阅[导入电子邮件、 联系人和日历从 Outlook.pst 文件](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="02f98-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="02f98-p101">以下是一些有关使用 Office 365 导入服务批量导入 PST 文件迁移到 Office 365 邮箱的常见问题。有关如何导入 PST 文件的详细信息，请参阅[Overview of 导入 PST 文件迁移到 Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。</span><span class="sxs-lookup"><span data-stu-id="02f98-p101">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes. For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="02f98-107">使用网络上载以导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="02f98-107">Using network upload to import PST files</span></span>

<span data-ttu-id="02f98-108">有关分步说明，请参阅[使用网络上载以导入 PST 文件迁移到 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="02f98-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="02f98-109">**需要在 Office 365 导入服务中创建导入作业哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="02f98-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="02f98-p102">您必须为其分配导入导出邮箱角色在 Exchange Online 到 Office 365 邮箱导入 PST 文件。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。</span><span class="sxs-lookup"><span data-stu-id="02f98-p102">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="02f98-115">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="02f98-115">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="02f98-p103">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="02f98-p103">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="02f98-118">或者</span><span class="sxs-lookup"><span data-stu-id="02f98-118">Or</span></span>
    
- <span data-ttu-id="02f98-119">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="02f98-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="02f98-p104">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="02f98-p104">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="02f98-122">**在哪里网络上载可用**</span><span class="sxs-lookup"><span data-stu-id="02f98-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="02f98-p105">在美国、 加拿大、 巴西、 英国、 法国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚是当前可用网络上载。网络上载很快就会提供在多个区域中。</span><span class="sxs-lookup"><span data-stu-id="02f98-p105">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="02f98-125">**什么是使用网络上载导入 PST 文件的定价？**</span><span class="sxs-lookup"><span data-stu-id="02f98-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="02f98-126">使用网络上载以导入 PST 文件是免费的。</span><span class="sxs-lookup"><span data-stu-id="02f98-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="02f98-p106">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在 Office 365 管理中心中的已完成的导入作业的文件列表中。虽然仍可能会导入作业列出在**导入到 Office 365 的数据**页上，查看旧导入作业的详细信息中可能为空的 PST 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="02f98-p106">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Office 365 admin center. Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="02f98-129">**导入到 Office 365 支持哪些版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="02f98-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="02f98-p107">有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用网络上载以导入到 Office 365 组织的 PST 文件](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步骤 4。</span><span class="sxs-lookup"><span data-stu-id="02f98-p107">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="02f98-134">此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="02f98-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="02f98-135">**我将我的 PST 文件上载到 Azure 存储区后，长它们保存在 Azure 正在删除之前？**</span><span class="sxs-lookup"><span data-stu-id="02f98-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="02f98-p108">如果您使用的网络上载方法来导入 PST 文件，您可以将它们上载到名为**ingestiondata**Azure blob 容器。如果没有导入作业正在进行**导入**页上的安全性&amp;合规性中心)，然后在 Azure 中**ingestiondata**容器中的所有 PST 文件将被都删除 30 天后在安全&amp;合规性中心。这还意味着您必须在安全中创建新的导入作业&amp;到 Azure 文件上载 PST 30 天内的合规性中心 （中所述步骤 5 中的网络上载说明）。</span><span class="sxs-lookup"><span data-stu-id="02f98-p108">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**. If there are no import jobs in progress on the **Import** page in the Security &amp; Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security &amp; Compliance Center. That also means you have to create a new import job in the Security &amp; Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="02f98-p109">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="02f98-p109">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="02f98-141">**导入到邮箱的 PST 文件需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="02f98-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="02f98-p110">这取决于您的网络的容量，但它通常采用的每个 tb 的数据上载到您的组织的 Azure 存储区的几个小时。PST 文件复制到 Azure 存储区域后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据迁移到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="02f98-p110">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="02f98-p111">如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="02f98-p111">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="02f98-148">**导入 PST 文件时有邮件大小限制吗？**</span><span class="sxs-lookup"><span data-stu-id="02f98-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="02f98-p112">是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。</span><span class="sxs-lookup"><span data-stu-id="02f98-p112">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="02f98-151">**邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**</span><span class="sxs-lookup"><span data-stu-id="02f98-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="02f98-p113">是的。在导入过程不会更改原始消息元数据。</span><span class="sxs-lookup"><span data-stu-id="02f98-p113">Yes. The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="02f98-154">**是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**</span><span class="sxs-lookup"><span data-stu-id="02f98-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="02f98-p114">是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="02f98-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="02f98-157">**可以使用网络上载到 Office 365 中的非活动邮箱导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="02f98-158">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="02f98-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="02f98-159">**可以使用网络上载到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="02f98-160">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="02f98-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="02f98-161">**可以使用网络上载到 Exchange Online 中公用文件夹中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="02f98-162">否，您不能 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="02f98-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="02f98-163">使用驱动器传送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="02f98-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="02f98-164">有关分步说明，请参阅[使用传送导入到 Office 365 的 PST 文件的驱动器](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="02f98-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="02f98-165">**需要在 Office 365 导入服务中创建导入作业哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="02f98-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="02f98-p115">您必须为其分配到 Office 365 邮箱导入 PST 文件导入导出邮箱角色。默认情况下，此角色不分配给任何角色组在 Exchange Online。您可以向组织管理角色组中添加邮箱导入导出角色。或者，您可以创建新角色组、 分配的邮箱导入导出角色中，然后将自己或其他用户添加为成员。有关详细信息，请参阅"添加角色向角色组"或"创建角色组"部分[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688)中。</span><span class="sxs-lookup"><span data-stu-id="02f98-p115">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes. By default, this role isn't assigned to any role group in Exchange Online. You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="02f98-171">此外，若要创建导入作业 Office 365 安全性&amp;必须满足合规中心，下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="02f98-171">Additionally, to create import jobs in the Office 365 Security &amp; Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="02f98-p116">您必须分配 Mail Recipients 角色在 Exchange Online。默认情况下，此角色分配给组织管理和 Recipient Management 角色组。</span><span class="sxs-lookup"><span data-stu-id="02f98-p116">You have to be assigned the Mail Recipients role in Exchange Online. By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="02f98-174">或者</span><span class="sxs-lookup"><span data-stu-id="02f98-174">Or</span></span>
    
- <span data-ttu-id="02f98-175">您必须是 Office 365 组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="02f98-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="02f98-p117">请考虑在 Exchange Online 的专门用于将 PST 文件导入到 Office 365 中创建新的角色组。最小的导入 PST 文件所需的权限级别，将邮箱导入导出和 Mail Recipients 角色分配给新角色组中，，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="02f98-p117">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365. For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="02f98-178">**驱动器发运可用？**</span><span class="sxs-lookup"><span data-stu-id="02f98-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="02f98-p118">在美国、 加拿大、 巴西、 英国、 欧洲、 印度、 中国、 东南方向亚洲，日本、 韩国、 和澳大利亚驱动器传送是当前可用。驱动器传送很快就会提供在多个区域中。</span><span class="sxs-lookup"><span data-stu-id="02f98-p118">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia. Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="02f98-181">**哪些商业许可协议支持驱动器传送？**</span><span class="sxs-lookup"><span data-stu-id="02f98-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="02f98-p119">可通过 Microsoft 企业协议 (EA) 传送到 Office 365 导入 PST 文件的驱动器。驱动器传送不提供通过 Microsoft 产品和服务协议 (MPSA)。</span><span class="sxs-lookup"><span data-stu-id="02f98-p119">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA). Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="02f98-184">**什么是使用传送到 Office 365 导入 PST 文件的驱动器的定价？**</span><span class="sxs-lookup"><span data-stu-id="02f98-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="02f98-p120">若要使用驱动器传送到 Office 365 邮箱导入 PST 文件的成本是每 GB 的数据 2 美元。例如，如果附带包含 1,000 GB (1 TB) 的 PST 文件的硬盘驱动器，成本是 2,000 美元。您可以使用导入费用，合作伙伴。有关查找合作伙伴的信息，请参阅[查找您的 Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="02f98-p120">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="02f98-189">**驱动器传送的操作支持哪些类型的硬盘驱动器？**</span><span class="sxs-lookup"><span data-stu-id="02f98-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="02f98-p121">仅为 2.5 英寸固态驱动器 (Ssd) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘支持与 Office 365 导入服务一起使用。您可以使用硬盘最多 10 TB。导入作业将处理仅第一个数据卷上的硬盘中。必须使用 NTFS 格式化数据量。当数据复制到硬盘上，您可以将其直接使用 2.5 英寸 SSD 附加或 2.5 或 3.5 英寸 SATA II/III 连接器或可以附加外部使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器。</span><span class="sxs-lookup"><span data-stu-id="02f98-p121">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service. You can use hard drives up to 10 TB. For import jobs, only the first data volume on the hard drive will be processed. The data volume must be formatted with NTFS. When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="02f98-p122">Office 365 导入服务不支持外部硬盘驱动器附带的内置的 USB 适配器。此外，不能使用内外部的硬盘驱动器上的大小写磁盘。请不要附带外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="02f98-p122">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="02f98-198">**单个导入作业可以提供多少硬盘驱动器？**</span><span class="sxs-lookup"><span data-stu-id="02f98-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="02f98-199">您可以提供 10 硬盘驱动器单个导入作业的最大值。</span><span class="sxs-lookup"><span data-stu-id="02f98-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="02f98-200">**我附带我硬盘后，如何长，转到 Microsoft 数据中心？**</span><span class="sxs-lookup"><span data-stu-id="02f98-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="02f98-p123">这取决于几件事，例如您接近 Microsoft 数据中心，您用于附带硬盘驱动器 （例如下, 一个工作日传递、 两天传递或度数送达） 哪种类型的传送选项。与大多数 shippers，您可以使用跟踪数跟踪您传递的状态。</span><span class="sxs-lookup"><span data-stu-id="02f98-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="02f98-203">**我硬盘到达 Microsoft 数据中心后，如何长时间将我的 PST 文件上载到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="02f98-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="02f98-p124">在 Microsoft 数据中心收到您的硬盘后，将花费多之间 7 至 10 个工作日将 PST 文件上载到您的组织的 Microsoft Azure 存储区。PST 文件将上载到名为**ingestiondata**Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="02f98-p124">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization. The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="02f98-206">**导入到邮箱的 PST 文件需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="02f98-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="02f98-p125">PST 文件上载到 Azure 存储区后，Office 365 分析 PST 文件中的数据 （以安全方式） 来标识的项目和 PST 文件中包含的其他消息类型的期限。完成此分析后，您必须导入 PST 文件中的所有数据的选项或设置筛选器与控制哪些数据获取导入。开始导入作业后，PST 文件导入到 Office 365 邮箱至少 24 GB 每日的速率。如果此速率，不能满足需要，可以考虑将电子邮件数据导入到 Office 365 的其他方法。有关详细信息，请参阅[方法迁移到 Office 365 的多个电子邮件帐户](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)。</span><span class="sxs-lookup"><span data-stu-id="02f98-p125">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files. When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported. After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day. If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365. For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="02f98-p126">如果不同 PST 文件导入到不同的目标邮箱，导入过程会发生并行;换句话说，每个邮箱 PST 对导入同时。同样，如果多个 PST 文件导入到的同一邮箱，它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="02f98-p126">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="02f98-214">**Microsoft 将我的 PST 文件上载到 Azure 后，长它们保存在 Azure 正在删除之前？**</span><span class="sxs-lookup"><span data-stu-id="02f98-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="02f98-215">中的 Azure 的存储位置 （在 blob 容器中名为**ingestiondata** ），贵组织的所有 PST 文件将被都删除 30 天后在安全的**导入**页上创建的最新的导入作业&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="02f98-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="02f98-p127">这还意味着从 Azure 存储区删除 PST 文件后，他们正在不再显示在安全中完成导入作业的文件列表中&amp;合规性中心。尽管安全中的**导入**页上，系统可能仍列出导入作业&amp;合规中心的 PST 文件列表可能为空，当您查看旧导入作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="02f98-p127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security &amp; Compliance Center. Although an import job might still be listed on the **Import** page in the Security &amp; Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="02f98-218">**导入到 Office 365 支持哪些版本的 PST 文件格式？**</span><span class="sxs-lookup"><span data-stu-id="02f98-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="02f98-p128">有两个版本的 PST 文件格式： ANSI 和 Unicode。我们建议导入使用 Unicode PST 文件格式的文件。但是，使用 ANSI PST 文件格式，如使用双字节字符的语言的文件 (DBCS)，也可以导入到 Office 365。有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送导入 PST 文件迁移到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="02f98-p128">There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365. For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="02f98-223">此外，可以到 Office 365 导入 PST 文件从 Outlook 2007 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="02f98-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="02f98-224">**导入 PST 文件时有邮件大小限制吗？**</span><span class="sxs-lookup"><span data-stu-id="02f98-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="02f98-p129">是的。如果 PST 文件中包含大于 150 MB 邮箱项目，将在导入过程跳过项目。</span><span class="sxs-lookup"><span data-stu-id="02f98-p129">Yes. If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="02f98-227">**邮件属性，例如当邮件已发送或接收，收件人和其他属性，PST 文件导入到 Office 365 邮箱时保留的列表？**</span><span class="sxs-lookup"><span data-stu-id="02f98-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="02f98-p130">是的。导入过程中未更改的原始消息元数据</span><span class="sxs-lookup"><span data-stu-id="02f98-p130">Yes. The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="02f98-230">**是否有我想要导入到邮箱的 PST 文件的文件夹层次结构中的级别数限制？**</span><span class="sxs-lookup"><span data-stu-id="02f98-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="02f98-p131">是的。无法导入 PST 文件具有 300 或多个级别的嵌套文件夹。</span><span class="sxs-lookup"><span data-stu-id="02f98-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="02f98-233">**可以使用驱动器传送到 Office 365 中的非活动邮箱导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="02f98-234">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="02f98-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="02f98-235">**可以使用驱动器传送到联机存档邮箱的 Exchange 混合部署中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="02f98-236">是，此功能现已推出的。</span><span class="sxs-lookup"><span data-stu-id="02f98-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="02f98-237">**可以使用驱动器传送到 Exchange Online 中公用文件夹中导入 PST 文件？**</span><span class="sxs-lookup"><span data-stu-id="02f98-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="02f98-238">否，您不能 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="02f98-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="02f98-239">**运回我之前，可以 Microsoft 擦除我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="02f98-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="02f98-p132">否，Microsoft 不能擦除之前传送它们返回到客户的硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。</span><span class="sxs-lookup"><span data-stu-id="02f98-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="02f98-242">**Microsoft 可以清除而不是传送给我我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="02f98-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="02f98-p133">否，Microsoft 能销毁硬盘驱动器。硬盘驱动器相同时它们接收由 Microsoft 它们所处的状态返回给您。</span><span class="sxs-lookup"><span data-stu-id="02f98-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="02f98-245">**返回传送的操作支持哪些 courier 服务？**</span><span class="sxs-lookup"><span data-stu-id="02f98-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="02f98-p134">如果您在美国或欧洲客户，Microsoft 使用 FedEx 返回硬盘驱动器。对于所有其他区域，Microsoft 使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="02f98-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="02f98-248">**返回传送成本是什么？**</span><span class="sxs-lookup"><span data-stu-id="02f98-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="02f98-p135">返回传送成本有所不同，具体取决于您接近 Microsoft 数据中心的传送到硬盘空间。Microsoft 将 bill 返回您的硬盘您 FedEx 或 DHL 的帐户。返回传送的成本是您的责任。</span><span class="sxs-lookup"><span data-stu-id="02f98-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="02f98-252">**可以使用自定义 courier 传送服务，如 FedEx 自定义的传送提供给 Microsoft 我硬盘驱动器上？**</span><span class="sxs-lookup"><span data-stu-id="02f98-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="02f98-253">是。</span><span class="sxs-lookup"><span data-stu-id="02f98-253">Yes.</span></span>
  
 <span data-ttu-id="02f98-254">**如果我必须附带我到另一个国家/地区的硬盘，还有什么我需要做？**</span><span class="sxs-lookup"><span data-stu-id="02f98-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="02f98-p136">向 Microsoft 附带的硬盘可能需要跨国际边框。如果是这样，您负责确保的硬盘和它包含的数据将导入和/或适用法律按照导出。前传送硬盘驱动器，请与您的顾问验证，您的驱动器和数据合法可以传送到指定的 Microsoft 数据中心。这将有助于确保它及时到达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="02f98-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
