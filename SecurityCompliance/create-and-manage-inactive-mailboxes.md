---
title: 在 Office 365 中创建和管理非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 通过对邮箱应用保留或 Office 365 保留策略, 然后删除相应的 Office 365 用户帐户, 可以在 Office 365 中创建非活动邮箱。非活动邮箱中的项目会在保留或应用到其非活动状态的保留策略的持续时间内保留。若要永久删除非活动邮箱, 只需删除保留策略或保留策略即可。
ms.openlocfilehash: 8f798873da7d787b54932438e81aebf2dfe85181
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217772"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a><span data-ttu-id="b2728-105">在 Office 365 中创建和管理非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-105">Create and manage inactive mailboxes in Office 365</span></span>

<span data-ttu-id="b2728-p102">Office 365 使您可以保留已删除邮箱的内容。此功能称为 "[非活动邮箱](inactive-mailboxes-in-office-365.md)"。非活动邮箱允许您在离开您的组织后保留以前的员工的电子邮件。在删除相应的 office 365 用户帐户之前, 如果将诉讼保留或 office 365 保留策略 (在&amp; office 365 安全合规中心中创建) 应用于邮箱, 则邮箱将变为非活动状态。非活动邮箱的内容会在邮箱处于非活动状态之前放置在邮箱保留期间的保留时间内进行保留。这使得管理员、合规性监察官和记录管理员能够在安全&amp;合规中心中使用内容搜索来搜索和导出非活动邮箱的内容。非活动邮箱无法接收电子邮件, 并且不会显示在组织的共享通讯簿或其他列表中。</span><span class="sxs-lookup"><span data-stu-id="b2728-p102">Office 365 makes it possible for you to retain the contents of deleted mailboxes. This feature is called [inactive mailboxes](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. A mailbox becomes inactive when a Litigation Hold or an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) is applied to the mailbox before the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. This allows administrators, compliance officers, and records managers to use Content Search in the Security &amp; Compliance Center to search and export the contents of an inactive mailbox. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2728-p103">我们推迟了创建新的就地保留的2017年7月1日, 将邮箱设为非活动状态。但在今年下半年或明年早些时候, 你将无法在 Exchange Online 中创建新的就地保留。在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。但是, 仍将支持就地保留中的现有非活动邮箱, 并且可以继续管理非活动邮箱的就地保留。这包括更改就地保留的持续时间以及通过删除就地保留来永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="b2728-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="b2728-118">Before you begin</span></span>

- <span data-ttu-id="b2728-p104">若要将邮箱设为非活动邮箱, 必须为其分配一个 Exchange Online 计划2许可证, 以便在删除邮箱之前可以将诉讼保留或 Office 365 保留策略应用于该邮箱。Exchange Online 计划2许可证是 Office 365 企业版 E3 和 E5 订阅的一部分。如果为邮箱分配了 Exchange Online 计划1许可证 (它是 Office 365 企业版 E1 订阅的一部分), 则必须将其分配给单独的 Exchange online 存档许可证, 以便在删除邮箱之前可以对其应用保留。有关详细信息, 请参阅[Exchange Online 存档](https://go.microsoft.com/fwlink/p/?LinkId=286153)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p104">To make a mailbox inactive, it must be assigned an Exchange Online Plan 2 license so that a Litigation Hold or an Office 365 retention policy can be applied to the mailbox before it's deleted. Exchange Online Plan 2 licenses are part of an Office 365 Enterprise E3 and E5 subscriptions. If a mailbox is assigned an Exchange Online Plan 1 license (which is part of an Office 365 Enterprise E1 subscription), you would have to assign it a separate Exchange Online Archiving license so that a hold can be applied to the mailbox before it's deleted. For more information, see [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span></span>
    
- <span data-ttu-id="b2728-p105">删除相应的 Office 365 用户帐户后, 与已删除的 Exchange Online 邮箱相关联的许可证将可用。然后, 您可以向其他用户[分配 Office 365 for business 中的用户许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p105">The license associated with the deleted Exchange Online mailbox will be available after you delete the corresponding Office 365 user account. You can then [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) to another user.</span></span> 
    
- <span data-ttu-id="b2728-p106">如果在删除之前未对邮箱应用诉讼保留策略或 Office 365 保留策略, 则不会保留或发现邮箱的内容。但是, 删除的邮箱可以在删除后的30天内恢复, 但是如果未恢复, 则30天后将永久删除该邮箱及其内容。</span><span class="sxs-lookup"><span data-stu-id="b2728-p106">If a Litigation Hold or an Office 365 retention policy isn't applied to a mailbox before it's deleted, the contents of the mailbox won't be retained or discoverable. However, the deleted mailbox can be recovered within 30 days of deletion, but the mailbox and its contents will be permanently deleted after 30 days if it isn't recovered.</span></span>
    
- <span data-ttu-id="b2728-p107">有关诉讼保留的详细信息, 请参阅[就地保留和诉讼保留](https://go.microsoft.com/fwlink/p/?LinkId=846124)。有关安全&amp;合规性中心中的 Office 365 保留策略的详细信息, 请参阅[Office 365 中的保留策略概述](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p107">For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). For more information about Office 365 retention policies in the Security &amp; Compliance Center, see [Overview of retention policies in Office 365](retention-policies.md).</span></span>
  
## <a name="create-an-inactive-mailbox"></a><span data-ttu-id="b2728-129">创建非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-129">Create an inactive mailbox</span></span>

<span data-ttu-id="b2728-p108">将邮箱设为非活动包括两个步骤: 1) 将邮箱置于诉讼保留状态, 或向其应用 Office 365 保留策略, 并2删除邮箱或对应的 office 365 用户帐户。邮箱处于非活动状态后, 其内容将一直保留, 直到保留策略被删除。</span><span class="sxs-lookup"><span data-stu-id="b2728-p108">Making a mailbox inactive involves two steps: 1) placing the mailbox on Litigation Hold or applying an Office 365 retention policy to it, and 2) deleting the mailbox or corresponding Office 365 user account. After the mailbox is inactive, its contents are retained until the hold or retention policy is removed.</span></span>
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a><span data-ttu-id="b2728-132">步骤 1: 将邮箱置于诉讼保留状态或应用 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="b2728-132">Step 1: Place a mailbox on Litigation Hold or apply an Office 365 retention policy</span></span>

<span data-ttu-id="b2728-p109">将邮箱置于诉讼保留状态或应用 Office 365 保留策略会在邮箱中删除之前保留邮箱中的内容。这两种类型的保留都将保留所有邮箱内容, 包括已删除项目和已修改项目的原始版本。已删除和修改的项目在指定时间段内保留在非活动邮箱中, 或者直到您通过删除应用于非活动邮箱的保留策略或保留策略永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-p109">Placing a mailbox on Litigation Hold or applying an Office 365 retention policy retains the contents in the mailbox before it's deleted. Both types of holds will retain all mailbox content, including deleted items and original versions of modified items. Deleted and modified items are retained in the inactive mailbox for a specified period, or until you permanently delete the inactive mailbox by removing the hold or retention policy that's applied to the inactive mailbox.</span></span>
  
<span data-ttu-id="b2728-136">如果已在邮箱中放置了保留, 或者已将 Office 365 保留策略应用于邮箱, 则您只需删除步骤2中所述的相应 office 365 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b2728-136">If a hold is already placed on a mailbox, or if an Office 365 retention policy is already applied to a mailbox, then all you have to do is delete the corresponding Office 365 user account as explained in Step 2.</span></span>
  
<span data-ttu-id="b2728-137">有关将邮箱置于诉讼保留状态或应用 Office 365 保留策略的分步过程, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="b2728-137">For step-by-step procedures for placing a mailbox on Litigation Hold or applying an Office 365 retention policy, see:</span></span>
  
- [<span data-ttu-id="b2728-138">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b2728-138">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [<span data-ttu-id="b2728-139">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="b2728-139">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
> [!NOTE]
> <span data-ttu-id="b2728-p110">对于诉讼保留和 Office 365 保留策略, 您可以创建无限保留或基于时间的保留。在无限期保留中, 非活动邮箱的内容将永远保留, 或直到删除保留或保留持续时间更改为止。删除保留策略 (假定邮箱已在30天前删除) 后, 非活动邮箱将标记为永久删除, 邮箱的内容将不再保留或不可发现。在基于时间的保留策略或 Office 365 保留策略中, 您可以指定保留的持续时间。此持续时间基于每个项目, 它是从接收或创建邮箱项目的日期计算而来的。邮箱项目的保留过期, 并且该项目移到或位于非活动邮箱的 "可恢复的项目" 文件夹中时, 该项目会在已删除项目的保留期过期后从非活动邮箱中永久删除 (清除)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p110">For Litigation Holds and Office 365 retention policies, you can create an indefinite hold or on a time-based hold. In an indefinite hold, the contents of the inactive mailbox will be retained forever, or until the hold is removed or until the hold duration is changed. After the hold or retention policy is removed (assuming that the mailbox was deleted more than 30 days ago), the inactive mailbox will be marked for permanent deletion and the contents of the mailbox will no longer be retained or discoverable. In a time-based hold or Office 365 retention policy, you specify the duration of the hold. This duration is on a per-item basis and is calculated from the date a mailbox item was received or created. After the hold expires for a mailbox item, and that item moved to or is located in the Recoverable Items folder in the inactive mailbox, the item is permanently deleted (purged) from the inactive mailbox after the deleted item retention period expires.</span></span> 
  
### <a name="step-2-delete-the-mailbox"></a><span data-ttu-id="b2728-146">步骤 2：删除邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-146">Step 2: Delete the mailbox</span></span>

<span data-ttu-id="b2728-p111">将邮箱置于保留状态或将其应用到 Office 365 保留策略后, 下一步是删除邮箱。删除邮箱的最佳方法是在 office 365 管理中心删除对应的 Office 365 用户帐户。有关删除 Office 365 用户帐户的信息, 请参阅[从组织中删除用户](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p111">After the mailbox is placed on hold or an Office 365 retention policy is applied to it, the next step is to delete the mailbox. The best way to delete a mailbox is to delete the corresponding Office 365 user account in the Office 365 admin center. For information about deleting Office 365 user accounts, see [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2728-p112">您还可以使用 Exchange Online PowerShell 中的 "**删除-邮箱**" cmdlet 删除邮箱。有关详细信息, 请参阅[Delete or restore user 邮箱 in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p112">You can also delete the mailbox by using the **Remove-Mailbox** cmdlet in Exchange Online PowerShell. For more information, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span></span> 
  

## <a name="view-a-list-of-inactive-mailboxes"></a><span data-ttu-id="b2728-152">查看非活动邮箱的列表</span><span class="sxs-lookup"><span data-stu-id="b2728-152">View a list of inactive mailboxes</span></span>


<span data-ttu-id="b2728-153">若要查看组织中非活动邮箱的列表, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="b2728-153">To view a list of the inactive mailboxes in your organization:</span></span>
  
1. <span data-ttu-id="b2728-154">转到[https://protection.office.com/](https://protection.office.com/)并使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b2728-154">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="b2728-155">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> \* \* 保留 \* \*"。</span><span class="sxs-lookup"><span data-stu-id="b2728-155">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> \*\* Retention \*\*.</span></span>
    
3. <span data-ttu-id="b2728-156">在 "**保留**" 页上, 单击 "**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)", 然后单击 "**非活动邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="b2728-156">On the **Retention** page, click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), and then click **Inactive mailboxes**.</span></span>
    
    ![在 "保留" 页上, 单击 "更多", 然后单击 "非活动邮箱" 以显示非活动邮箱的列表](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    <span data-ttu-id="b2728-p113">将显示 "**非活动邮箱**" 页。注释将显示组织中的非活动邮箱总数。</span><span class="sxs-lookup"><span data-stu-id="b2728-p113">The **Inactive mailboxes** page is displayed. Note the total number of inactive mailboxes in your organization is displayed.</span></span> 
    
    ![将显示组织中所有非活动邮箱的列表](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
<span data-ttu-id="b2728-161">或者, 您可以在 Exchange Online PowerShell 中运行以下命令, 以显示非活动邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="b2728-161">Alternatively, you can run the following command in Exchange Online PowerShell to display the list of inactive mailboxes.</span></span>

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

<span data-ttu-id="b2728-162">您可以单击!["导出搜索结果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) " 图标 "**导出**" 以查看或下载包含有关组织中非活动邮箱的其他信息的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="b2728-162">You can click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization.</span></span> 
  
<span data-ttu-id="b2728-p114">您还可以运行以下命令, 将非活动邮箱列表和其他信息导出到 CSV 文件中。在此示例中, 将在当前目录中创建 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="b2728-p114">You can also run the following command to export the list of inactive mailboxes and other information to a CSV file. In this example, the CSV file is created in the current directory.</span></span>

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> <span data-ttu-id="b2728-p115">非活动邮箱可能具有与活动用户邮箱相同的 SMTP 地址。在这种情况下, 可以使用**DistinguishedName**或**ExchangeGuid**属性的值来唯一标识非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-p115">It's possible that an inactive mailbox may have the same SMTP address as an active user mailbox. In this case, the value of the **DistinguishedName** or **ExchangeGuid** property can be used to uniquely identify an inactive mailbox.</span></span> 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a><span data-ttu-id="b2728-167">搜索并导出非活动邮箱的内容</span><span class="sxs-lookup"><span data-stu-id="b2728-167">Search and export the contents of an inactive mailbox</span></span>

<span data-ttu-id="b2728-p116">您可以通过使用安全&amp;合规性中心中的内容搜索工具来访问非活动邮箱的内容。当您搜索非活动邮箱时, 可以创建关键字搜索查询以搜索特定项目, 也可以返回非活动邮箱的全部内容。您可以预览搜索结果, 也可以将搜索结果导出到 Outlook 数据 (PST) 文件或单独的电子邮件。有关搜索邮箱和导出搜索结果的分步过程, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="b2728-p116">You can access the contents of the inactive mailbox by using the Content Search tool in the Security &amp; Compliance Center. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:</span></span>
  
- [<span data-ttu-id="b2728-172">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="b2728-172">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="b2728-173">从 Office 365 安全&amp;合规中心导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="b2728-173">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
<span data-ttu-id="b2728-174">以下是在搜索非活动邮箱时要牢记的一些事项。</span><span class="sxs-lookup"><span data-stu-id="b2728-174">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="b2728-175">如果内容搜索包括用户邮箱, 并且该邮箱随后变为非活动状态, 则当您在搜索变为非活动状态后重新运行该搜索时, 内容搜索将继续搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-175">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="b2728-p117">在某些情况下, 用户可能有一个活动邮箱和一个具有相同 SMTP 地址的非活动邮箱。在这种情况下, 将仅搜索您选择作为内容搜索的位置的特定邮箱。换句话说, 如果将用户的邮箱添加到搜索, 则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-p117">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="b2728-p118">强烈建议您避免使用相同 SMTP 地址的活动邮箱和非活动邮箱。如果需要重用当前分配给非活动邮箱的 SMTP 地址, 我们建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱的存档) 中, 然后删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2728-p118">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span>
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="b2728-181">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="b2728-181">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="b2728-p119">将邮箱设为非活动状态后, 可以更改保留或应用于非活动邮箱的 Office 365 保留策略的持续时间。有关分步过程, 请参阅[在 Office 365 中更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p119">After a mailbox is made inactive, you can change the duration of the hold or the Office 365 retention policy applied to the inactive mailbox. For step-by-step procedures, see [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span></span>
  
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="b2728-184">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-184">Recover an inactive mailbox</span></span>

<span data-ttu-id="b2728-p120">如果以前的员工返回到您的组织, 或者如果雇用新员工来承担 departed 员工的工作职责, 则可以恢复非活动邮箱的内容。恢复非活动邮箱时, 邮箱将转换为新邮箱, 非活动邮箱的内容和文件夹结构将保留, 邮箱将链接到新的用户帐户。恢复后, 非活动邮箱将不再存在。有关在恢复非活动邮箱时发生的分步过程和详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p120">If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists. For step-by-step procedures and more information about happens when you recover an inactive mailbox, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a><span data-ttu-id="b2728-189">将非活动邮箱的内容还原到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-189">Restore the contents of an inactive mailbox to another mailbox</span></span>

<span data-ttu-id="b2728-p121">如果另一个员工承担以前员工的工作职责, 或者如果其他人需要访问非活动邮箱的内容, 则可以将非活动邮箱的内容还原 (或合并) 到现有邮箱。在还原非活动邮箱时, 会将内容复制到另一个邮箱。非活动邮箱将保留并保持非活动状态的邮箱。仍可以使用电子数据展示搜索非活动邮箱, 可以将其内容还原到另一个邮箱, 也可以在以后恢复或删除。有关分步过程, 请参阅[在 Office 365 中还原非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p121">If another employee takes on the job responsibilities of a former employee, or if another person needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. When you restore an inactive mailbox, the contents are copied to another mailbox. The inactive mailbox is retained and remains an inactive mailbox. The inactive mailbox can still be searched using eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. For step-by-step procedures, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
  
## <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="b2728-195">删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="b2728-195">Delete an inactive mailbox</span></span>

<span data-ttu-id="b2728-p122">如果不再需要保留非活动邮箱的内容, 可以通过删除保留或删除应用于非活动邮箱的 Office 365 保留策略来永久删除非活动邮箱。如果邮箱已被删除30天以上, 则在删除保留后邮箱将被标记为永久删除, 并且邮箱将变为不可恢复。如果邮箱是在最近30天内删除的, 您仍可以在删除保留策略或保留策略后恢复邮箱。有关删除保留策略或 Office 365 保留策略以永久删除非活动邮箱的分步过程, 请参阅[删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="b2728-p122">If you no longer need to retain the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold or removing the Office 365 retention policy applied to the inactive mailbox. If the mailbox was deleted more than 30 days ago, the mailbox will be marked for permanent deletion after you remove the hold, and the mailbox will become non-recoverable. If the mailbox was deleted within the last 30 days, you can still recover the mailbox after removing the hold or retention policy. For step-by-step procedures for removing a hold or a Office 365 retention policy to permanently delete an inactive mailbox, see [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md).</span></span>