---
title: 处置评审概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: d0c6095b-bfee-4906-a2c7-89c2d7f411c1
description: 在创建时保持在原有的 Office 365 中的内容的标签，您可以选择触发处置回顾末尾的保留期。
ms.openlocfilehash: c0a2933f597c9b314ac4ce2e72de9619fac90082
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013716"
---
# <a name="overview-of-disposition-reviews"></a><span data-ttu-id="6c325-103">处置评审概述</span><span class="sxs-lookup"><span data-stu-id="6c325-103">Overview of disposition reviews</span></span>

<span data-ttu-id="6c325-p101">当内容到达其保留期结束时，有几个原因为什么您可能想要查看的内容来确定是否它可安全删除 （"释放"）。例如，您可能需要：</span><span class="sxs-lookup"><span data-stu-id="6c325-p101">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed"). For example, you might need to:</span></span>
  
- <span data-ttu-id="6c325-106">挂起发生诉讼或审核相关的内容的删除 （"处置"）。</span><span class="sxs-lookup"><span data-stu-id="6c325-106">Suspend the deletion ("disposition") of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="6c325-107">如果该内容研究或历史记录的值，请从处置列表中存档存储中删除内容。</span><span class="sxs-lookup"><span data-stu-id="6c325-107">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="6c325-108">将不同的保留期分配到内容，如果原始策略临时或临时解决方案。</span><span class="sxs-lookup"><span data-stu-id="6c325-108">Assign a different retention period to the content, if the original policy was a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="6c325-109">返回到客户端的内容或转接到另一个组织。</span><span class="sxs-lookup"><span data-stu-id="6c325-109">Return the content to clients or transfer it to another organization.</span></span>
    
<span data-ttu-id="6c325-p102">在创建时保持在原有的 Office 365 中的内容的标签，您可以选择触发处置回顾末尾的保留期。处置回顾： 中</span><span class="sxs-lookup"><span data-stu-id="6c325-p102">When you create a label that retains content in Office 365, you can choose to trigger a disposition review at the end of the retention period. In a disposition review:</span></span>
  
- <span data-ttu-id="6c325-p103">您选择的人接收电子邮件通知他们拥有要查看内容。这些审阅者可以是单个用户、 通讯组或安全组或 Office 365 组。请注意，在每周的基础上，会发送通知。</span><span class="sxs-lookup"><span data-stu-id="6c325-p103">The people you choose receive an email notification that they have content to review. These reviewers can be individual users, distribution or security groups, or Office 365 groups. Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="6c325-115">审阅者转到安全的**处置**页&amp;合规性中心以查看内容。</span><span class="sxs-lookup"><span data-stu-id="6c325-115">The reviewers go to the **Disposition** page in the Security &amp; Compliance Center to review the content.</span></span> 
    
- <span data-ttu-id="6c325-116">对于每个文档审阅者可以：</span><span class="sxs-lookup"><span data-stu-id="6c325-116">For each document, the reviewer can:</span></span>
    
  - <span data-ttu-id="6c325-117">应用不同的标签。</span><span class="sxs-lookup"><span data-stu-id="6c325-117">Apply a different label.</span></span>
    
  - <span data-ttu-id="6c325-118">扩展其保留期。</span><span class="sxs-lookup"><span data-stu-id="6c325-118">Extend its retention period.</span></span>
    
  - <span data-ttu-id="6c325-119">永久删除它。</span><span class="sxs-lookup"><span data-stu-id="6c325-119">Permanently delete it.</span></span>
    
- <span data-ttu-id="6c325-120">审阅者可以查看挂起或历史处置情况，并将该列表导出为.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="6c325-120">Reviewers can view either pending or historical dispositions, and export that list as a .csv file.</span></span>
    
<span data-ttu-id="6c325-121">请注意该处置评审需要的 Office 365 企业 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="6c325-121">Note that disposition reviews require an Office 365 Enterprise E5 subscription.</span></span>
  
<span data-ttu-id="6c325-p104">处置回顾可以在 Exchange 邮箱、 SharePoint 网站、 OneDrive 帐户和 Office 365 组包含内容。仅在审阅者选择要永久删除内容后，则删除等待处置回顾这些位置中的内容。</span><span class="sxs-lookup"><span data-stu-id="6c325-p104">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Office 365 groups. Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>
  
![处置页](media/b7436fb2-1f35-4146-8ca2-32c9d10f7e09.png)
  
## <a name="setting-up-the-disposition-review-by-creating-a-label"></a><span data-ttu-id="6c325-125">通过创建一个标签处置审阅设置</span><span class="sxs-lookup"><span data-stu-id="6c325-125">Setting up the disposition review by creating a label</span></span>

<span data-ttu-id="6c325-p105">这是设置处置审阅的基本工作流程。请注意，此流显示标签正在发布，然后手动应用的用户;或者，将触发处置回顾标签可以是自动应用于的内容。</span><span class="sxs-lookup"><span data-stu-id="6c325-p105">This is the basic workflow for setting up a disposition review. Note that this flow shows a label being published and then manually applied by a user; alternatively, a label that triggers a disposition review can be auto-applied to content.</span></span>
  
![显示如何处置工作流图表](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="6c325-p106">处置回顾是一个选项，当您在 Office 365 中创建标签。请注意，此选项不可用，但仅在使用保留设置标签中保留策略中。</span><span class="sxs-lookup"><span data-stu-id="6c325-p106">A disposition review is an option when you create a label in Office 365. Note that this option is not available in a retention policy but only in a label with retention settings.</span></span>
  
<span data-ttu-id="6c325-131">有关标签的详细信息，请参阅[Overview of 标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="6c325-131">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
![Label 的保留设置](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
  
## <a name="disposing-content"></a><span data-ttu-id="6c325-133">释放内容</span><span class="sxs-lookup"><span data-stu-id="6c325-133">Disposing content</span></span>

<span data-ttu-id="6c325-p107">审阅者通知通过电子邮件时该内容已准备好查看，可以继续转到安全的**处置**页&amp;合规性中心和选择一个或多个项目。然后可以审阅者：</span><span class="sxs-lookup"><span data-stu-id="6c325-p107">When a reviewer is notified by email that content is ready to review, they can go to the **Disposition** page in the Security &amp; Compliance Center and select one or more items. The reviewer can then:</span></span> 
  
- <span data-ttu-id="6c325-136">应用不同的标签。</span><span class="sxs-lookup"><span data-stu-id="6c325-136">Apply a different label.</span></span>
    
- <span data-ttu-id="6c325-137">扩展的保留期。</span><span class="sxs-lookup"><span data-stu-id="6c325-137">Extend the retention period.</span></span>
    
- <span data-ttu-id="6c325-138">永久删除项目。</span><span class="sxs-lookup"><span data-stu-id="6c325-138">Permanently delete the item.</span></span>
    
<span data-ttu-id="6c325-p108">审阅者可以使用以下链接查看文档中的原始位置，如果审阅者具有对该位置的权限。在处置评审，过程内容永远不会移从其原始位置和永远不会删除之前审阅者选择这样做。</span><span class="sxs-lookup"><span data-stu-id="6c325-p108">A reviewer can use the link to view the document in its original location, if the reviewer has permissions for that location. During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>
  
<span data-ttu-id="6c325-p109">请注意，给审阅者每周执行自动发送电子邮件通知。因此，当内容到达其保留期结束时，可能需要最多七天的审阅者接收电子邮件通知的内容正在等待处置。</span><span class="sxs-lookup"><span data-stu-id="6c325-p109">Note that the email notifications are sent automatically to reviewers on a weekly basis. Therefore, when content reaches the end of its retention period, it may take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="6c325-p110">另请注意，审核所有处置操作。若要确保这一点，您必须启用审核功能至少一天的第一个处置操作-之前的详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="6c325-p110">Also note that all disposition actions are audited. To ensure this, you must turn on auditing at least one day prior to the first disposition action - for more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 
  
![文档的处置选项](media/771630fd-a9b0-47cf-983b-fe85eb4cdafd.png)
  
## <a name="permissions-for-disposition"></a><span data-ttu-id="6c325-146">处置的权限</span><span class="sxs-lookup"><span data-stu-id="6c325-146">Permissions for disposition</span></span>

<span data-ttu-id="6c325-p111">若要获取对**处置**页面的访问，请审阅者必须**处置管理**角色和**仅查看审核日志**角色的成员。我们建议创建名处置审阅者的新角色组和将这两种角色添加到角色组，然后添加到角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="6c325-p111">To get access to the **Disposition** page, reviewers must be members of the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="6c325-149">有关详细信息，请参阅[向 Office 365 安全性授予用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6c325-149">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md)</span></span>
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="6c325-150">多长时间，直到释放的内容将被永久删除</span><span class="sxs-lookup"><span data-stu-id="6c325-150">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="6c325-p112">仅在审阅者选择要永久删除内容后，则删除等待处置查看的内容。当审阅者选择此选项时，变为是否可以使用本节中所述的标准的清理过程中的 SharePoint 网站或 OneDrive 帐户的内容：[保留策略就地处理内容的方式](retention-policies.md#how-a-retention-policy-works-with-content-in-place)。</span><span class="sxs-lookup"><span data-stu-id="6c325-p112">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content. When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in this section: [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>
  
<span data-ttu-id="6c325-153">这意味着：</span><span class="sxs-lookup"><span data-stu-id="6c325-153">This means that:</span></span>
  
- <span data-ttu-id="6c325-p113">将文档库中的内容移动到第一阶段回收站**中 7 天**的处置，然后之后的永久删除**93 天**。回收站不通过搜索索引，因此其内容，不到电子数据展示保留可用。</span><span class="sxs-lookup"><span data-stu-id="6c325-p113">Content in a document library will be moved to the first-stage Recycle Bin **within 7 days** of disposition, and then permanently deleted **93 days** after that. The Recycle Bin is not indexed by search and therefore its contents are not available to an eDiscovery hold.</span></span> 
    
- <span data-ttu-id="6c325-156">内容在演示文稿保留库将永久删除**7 天内**的处置。</span><span class="sxs-lookup"><span data-stu-id="6c325-156">Content in the Preservation Hold library will be permanently deleted **within 7 days** of disposition.</span></span> 
    
## <a name="view-pending-and-completed-dispositions"></a><span data-ttu-id="6c325-157">查看挂起的和已完成的处置情况</span><span class="sxs-lookup"><span data-stu-id="6c325-157">View pending and completed dispositions</span></span>

<span data-ttu-id="6c325-158">在安全的**处置**页上&amp;合规性中心，您可以查看挂起的和已完成的处置情况：</span><span class="sxs-lookup"><span data-stu-id="6c325-158">On the **Disposition** page of the Security &amp; Compliance Center, you can view both pending and completed dispositions:</span></span> 
  
- <span data-ttu-id="6c325-p114">**待处理**的处置情况已到达其保留期结束，并且需要处置审阅。复查每个项目，决定是否要对其应用不同的标签、 扩展其保留期，或永久删除。</span><span class="sxs-lookup"><span data-stu-id="6c325-p114">**Pending** dispositions have reached the end of their retention period and require a disposition review. After reviewing each item, decide if you want to apply a different label to it, extend its retention period, or permanently delete it.</span></span> 
    
- <span data-ttu-id="6c325-p115">**已完成**处置情况已批准可用于在处置评审过程删除并现在正在被永久删除。具有不同的标签，应用或保留期扩展一部分回顾不会显示此处的项目。</span><span class="sxs-lookup"><span data-stu-id="6c325-p115">**Completed** dispositions were approved for deletion during a disposition review and are now in the process of being permanently deleted. Items that had a different label applied or their retention period extended as part of a review won't appear here.</span></span> 
    
### <a name="filter-the-disposition-views"></a><span data-ttu-id="6c325-163">筛选处置视图</span><span class="sxs-lookup"><span data-stu-id="6c325-163">Filter the disposition views</span></span>

<span data-ttu-id="6c325-p116">您可以按标签或时间范围筛选这些视图。有关挂起的处置情况，时间范围基于的到期日期。为历史处置情况，时间范围基于删除日期。</span><span class="sxs-lookup"><span data-stu-id="6c325-p116">You can filter these views by label or time range. For pending dispositions, the time range is based on the expiry date. For historical dispositions, the time range is based on the deletion date.</span></span>
  
![处置上的筛选器选项](media/8682a9f5-a77d-45ae-b902-8418a3ebbea1.png)
  
### <a name="export-the-disposition-items"></a><span data-ttu-id="6c325-168">处置项目导出</span><span class="sxs-lookup"><span data-stu-id="6c325-168">Export the disposition items</span></span>

<span data-ttu-id="6c325-169">此外，您可以将任一视图中的项目导出为.csv 文件可以在 Excel 中打开的。</span><span class="sxs-lookup"><span data-stu-id="6c325-169">In addition, you can export the items in either view as a .csv file that you can open in Excel.</span></span>
  
![在 Excel 中的导出的处置数据](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

