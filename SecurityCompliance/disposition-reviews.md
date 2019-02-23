---
title: 处置评审概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: 在创建保留 Office 365 中的内容的标签时, 可以选择在保留期结束时触发处置评审。
ms.openlocfilehash: 0948d61131595d4111f656c385c58258c5cce99c
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215002"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="2a8f6-103">处置评审概述</span><span class="sxs-lookup"><span data-stu-id="2a8f6-103">Overview of disposition reviews</span></span>

<span data-ttu-id="2a8f6-p101">当内容到达其保留期结束时, 您可能需要查看内容以决定是否可以安全地删除 ("已释放"), 这有几个原因。例如, 您可能需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="2a8f6-106">在诉讼或审核的情况中, 挂起相关内容的删除 ("处置")。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="2a8f6-107">如果内容具有信息检索或历史值, 则从处置列表中移除要存储在存档中的内容。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="2a8f6-108">如果原始策略是临时或临时解决方案, 则为内容分配不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="2a8f6-109">将内容返回给客户端或将其转移到其他组织。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="2a8f6-p102">在创建保留 Office 365 中的内容的标签时, 可以选择在保留期结束时触发处置评审。在处置评审中:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="2a8f6-p103">您选择的人会收到一封电子邮件通知, 告知他们有要审阅的内容。这些审阅者可以是单独的用户、通讯组或安全组, 也可以是 Office 365 组。请注意, 每周会发送通知。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="2a8f6-115">审阅者转到安全\*\*\*\* &amp;合规中心中的 "处置" 页面, 以查看内容。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="2a8f6-116">对于每个文档, 审阅者可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="2a8f6-117">应用不同的标签。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="2a8f6-118">延长其保留期。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="2a8f6-119">将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="2a8f6-120">审阅者可以查看挂起或历史处置, 并将该列表导出为 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="2a8f6-121">请注意, 处置评审需要 Office 365 企业版 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="2a8f6-p104">处置评审可以包含 Exchange 邮箱、SharePoint 网站、OneDrive 帐户和 Office 365 组中的内容。在这些位置中等待处置评审的内容仅在审阅者选择永久删除内容后才会被删除。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![处置页面](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="2a8f6-125">通过创建标签设置处置评审</span><span class="sxs-lookup"><span data-stu-id="2a8f6-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="2a8f6-p105">这是用于设置处置评审的基本工作流。请注意, 此流显示要发布的标签, 然后由用户手动应用;或者, 可以将触发处置评审的标签自动应用于内容。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![显示处置的工作流的图表](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="2a8f6-p106">当您在 Office 365 中创建标签时, 可以选择进行处置评审。请注意, 在保留策略中不提供此选项, 但只能在具有保留设置的标签中使用。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="2a8f6-131">若要详细了解标签，请参阅[标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![标签的保留设置](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="2a8f6-133">处置内容</span><span class="sxs-lookup"><span data-stu-id="2a8f6-133">Disposing content</span></span>

<span data-ttu-id="2a8f6-p107">当通过电子邮件通知审阅者可以查看内容时, 他们可以转到安全&amp;合规性中心中的 "**处置**" 页面, 并选择一个或多个项目。然后, 审阅者可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="2a8f6-136">应用不同的标签。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-136">Apply a different label.</span></span>
    
- <span data-ttu-id="2a8f6-137">延长保留期。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="2a8f6-138">永久删除项目。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="2a8f6-p108">如果审阅者拥有对该位置的权限, 则审阅者可以使用该链接查看其原始位置的文档。在处置评审过程中, 内容永远不会从其原始位置移动, 并且在审阅者选择执行此操作之前永远不会删除。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="2a8f6-p109">请注意, 电子邮件通知将在每周的基础上自动发送给审阅者。因此, 当内容到达其保留期的末尾时, 审阅者可能需要长达七天的时间才能接收到内容正在等待处置的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="2a8f6-p110">另请注意, 审核所有处置操作。为确保这一点, 必须至少在第一次处置操作之前打开审核 (至少一天)-有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![文档的处置选项](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="2a8f6-146">处置权限</span><span class="sxs-lookup"><span data-stu-id="2a8f6-146">Permissions for disposition</span></span>

<span data-ttu-id="2a8f6-p111">若要获取对 "**处置**" 页面的访问权限, 审阅者必须是 "**处置管理**" 角色和 "**仅查看审核日志**" 角色的成员。我们建议创建一个名为 "处置审阅者" 的新角色组, 将这两个角色添加到该角色组, 然后将成员添加到该角色组。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="2a8f6-149">有关详细信息, 请参阅[向用户授予对 Office 365 安全&amp;合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="2a8f6-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="2a8f6-150">在永久删除已释放内容之前的时间</span><span class="sxs-lookup"><span data-stu-id="2a8f6-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="2a8f6-p112">等待处置评审的内容仅在审阅者选择永久删除内容后才会被删除。当审阅者选择此选项时, SharePoint 网站或 OneDrive 帐户中的内容将符合本部分中所述的标准清理过程:[保留策略如何处理就地内容](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="2a8f6-153">这意味着:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-153">This means that:</span></span>
  
- <span data-ttu-id="2a8f6-p113">文档库中的内容将被移至第一阶段回收站中的**7 天内**, 然后在该时间之后永久删除**93 天**。回收站不是通过搜索编制索引, 因此其内容不适用于电子数据展示保留。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="2a8f6-156">保留保留库中的内容将在部署后的**7 天内**永久删除。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="2a8f6-157">查看待处理和已完成处置</span><span class="sxs-lookup"><span data-stu-id="2a8f6-157">View pending and completed dispositions</span></span>

<span data-ttu-id="2a8f6-158">在安全\*\*\*\* &amp;合规性中心的 "处置" 页面上, 您可以查看挂起和已完成的处理:</span><span class="sxs-lookup"><span data-stu-id="2a8f6-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="2a8f6-p114">**挂起**的处置已达到其保留期的结束时间, 需要进行处置评审。检查每个项目后, 决定是否要对其应用不同的标签, 延长保留期, 或将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="2a8f6-p115">**已完成**的处置已在处置评审过程中被批准删除, 现在正处于永久删除过程中。在审阅中应用了不同标签或其保留期延长的项目不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="2a8f6-163">筛选处置视图</span><span class="sxs-lookup"><span data-stu-id="2a8f6-163">Filter the disposition views</span></span>

<span data-ttu-id="2a8f6-p116">您可以按标签或时间范围筛选这些视图。对于挂起的处置, 时间范围基于到期日期。对于历史处置, 时间范围基于删除日期。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
!["处置" 页面上的筛选器选项](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="2a8f6-168">导出处置项</span><span class="sxs-lookup"><span data-stu-id="2a8f6-168">Export the disposition items</span></span>

<span data-ttu-id="2a8f6-169">此外, 还可以将其中一个视图中的项导出为可在 Excel 中打开的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="2a8f6-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![Excel 中的已导出处置数据](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

