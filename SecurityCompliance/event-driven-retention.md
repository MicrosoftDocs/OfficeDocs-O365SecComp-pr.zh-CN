---
title: 事件驱动保留概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: dd851332-747b-45b9-82de-e3cd7d01c8a7
description: 使用 Office 365 中的标签，能让保留期以特定类型事件何时发生为依据。也就是说，事件触发开始计算保留期，并对包含与相应事件类型关联的标签的所有内容强制执行标签的保留操作。事件驱动保留通常用于记录管理流程。
ms.openlocfilehash: a5433b0515a8c4cde8e5ebf187b1a658f7d43cb4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213632"
---
# <a name="overview-of-event-driven-retention"></a><span data-ttu-id="c1bd0-105">事件驱动保留概述</span><span class="sxs-lookup"><span data-stu-id="c1bd0-105">Overview of event-driven retention</span></span>

<span data-ttu-id="c1bd0-p102">如果你保留内容，保留期通常是以内容年限为依据。例如，可以先将文档自创建起保留 7 年，再删除它们。不过，使用 Office 365 中的标签，还能让保留期以特定类型事件何时发生为依据。也就是说，事件触发开始计算保留期，并对包含与相应事件类型关联的标签的所有内容强制执行标签的保留操作。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p102">When you retain content, the retention period is often based on the age of the content - for example, you might retain documents for seven years after they're created and then delete them. But with labels in Office 365, you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="c1bd0-109">例如，可对以下事件结合使用标签和事件驱动保留：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-109">For example, you can use labels with event-driven retention for:</span></span>
  
- <span data-ttu-id="c1bd0-p103">**员工离开组织**：假设必须将员工记录自员工离开组织起保留 10 年。10 年之后，需要处置所有与离职员工的聘用、绩效和解雇有关的文档。触发 10 年保留期的事件是员工离开组织。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p103">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization. After 10 years elapse, all documents related to the hiring, performance, and termination of that employee need to be disposed. The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="c1bd0-p104">**合同到期**：假设必须将与合同相关的所有记录自合同到期起保留 5 年。触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p104">**Contract expiration** Suppose that all records related to contracts need to be retained for five years from the time the contract expires. The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="c1bd0-p105">**产品生存期**：组织可能会对技术规范等内容规定与产品最后生产日期相关的保留要求。在这种情况下，触发保留期的事件是最后生产日期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p105">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="c1bd0-p106">事件驱动保留通常用于记录管理流程。也就是说：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p106">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="c1bd0-p107">基于事件的标签也通常将内容分类为记录。有关详细信息，请参阅[使用内容搜索来查找所有已应用有特定保留标签的内容](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p107">Labels based on events also usually classify content as a record. For more information, see [Using Content Search to find all content with a specific retention label applied to it](labels.md#using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it).</span></span>
    
- <span data-ttu-id="c1bd0-121">如果文档已声明为记录，但其触发事件尚未发生，那么文档会无限期保留（因为无法永久删除记录），直到触发文档保留期的事件发生。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-121">A document that's been declared as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="c1bd0-p108">基于事件的标签通常会在保留期到期时触发处置评审，这样记录管理者便能手动评审和处置内容。有关详细信息，请参阅[处置评审概述](disposition-reviews.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p108">Labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose the content. For more information, see [Overview of disposition reviews](disposition-reviews.md).</span></span>
    
<span data-ttu-id="c1bd0-p109">基于事件的标签的功能与 Office 365 中的任何标签都相同。若要了解详情，请参阅[标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p109">A label based on an event has the same capabilities as any label in Office 365. To learn more, see [Overview of labels](labels.md).</span></span>
    
## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="c1bd0-126">了解事件类型、标签、事件和资产 ID 之间的关系</span><span class="sxs-lookup"><span data-stu-id="c1bd0-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="c1bd0-p110">为了成功使用事件驱动保留，请务必了解事件类型、标签、事件和资产 ID 之间的关系，如下所示。关系图后面紧跟着就是说明。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p110">To successfully use event-driven retention, it's important to understand the relationship between event types, labels, events, and asset IDs as illustrated here. An explanation follows the diagram.</span></span>
  
![事件类型、标签、事件和资产 ID 的关系图](media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![事件类型、标签、事件和资产 ID 的关系图](media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="c1bd0-p111">为不同类型的内容创建标签，再将标签与事件类型相关联。例如，不同类型的产品文件和记录的标签与“产品生存期”事件类型相关联，因为必须将这些记录自产品生存期结束起保留 10 年。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p111">You create labels for different types of content and then associate them with a type of event. For example, labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="c1bd0-p112">用户（通常为记录管理者）将这些标签应用于内容，并（对 SharePoint 和 OneDrive 文档）输入每项的资产 ID。在本示例中，资产 ID 是产品名称或组织使用的代码。所以，每个产品的记录都分配有标签，且每条记录都有一个包含资产 ID 的属性。此关系图表示组织的所有产品记录的**全部内容**，且每项都有记录所属产品的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p112">Users (typically records managers) apply those labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item. In this example, the asset ID is a product name or code used by the organization. Thus, each product's records are assigned a label, and each record has a property that contains an asset ID. The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="c1bd0-p113">事件类型是“产品生存期”，即事件是特定产品的生存期结束。当相应事件类型的事件（在本示例中，为产品生存期结束）发生时，创建指定以下信息的事件：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p113">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs - in this case, when a product reaches its end of life - you create an event that specifies:</span></span>
    
  - <span data-ttu-id="c1bd0-139">资产 ID（对于 SharePoint 和 OneDrive 文档）</span><span class="sxs-lookup"><span data-stu-id="c1bd0-139">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
  - <span data-ttu-id="c1bd0-p114">关键字（对于 Exchange 项）。在本示例中，组织在包含产品记录的邮件中使用产品代码，因此 Exchange 项的关键字与 SharePoint 和 OneDrive 文档的资产 ID 相同。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p114">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
  - <span data-ttu-id="c1bd0-p115">事件发生日期。此日期用作保留期的开始日期，只能是当前日期或未来日期，不能是过去日期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p115">The date when the event occurred. This date is used as the start of the retention period. This date can only be the current or a future date, not a past date.</span></span>
    
4. <span data-ttu-id="c1bd0-p116">在你创建事件后，事件日期会同步到包含与相应事件类型关联的标签和指定资产 ID 或关键字的所有内容。与任何标签一样，此同步最长可能需要 7 天才能完成。在上面的关系图中，所有用红圈圈出的项的保留期由此事件触发。也就是说，当此产品的生存期结束时，这个事件就会触发此产品的记录的保留期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p116">After you create an event, that event date is synced to all of the content that has a label of that event type and that contains the specified asset ID or keyword. Like any label, this syncing can take up to 7 days. In the diagram above, all of the items circled in red have their retention period triggered by this event - in other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>
    
<span data-ttu-id="c1bd0-p117">请务必了解，如果没有为事件指定资产 ID 或关键字，那么包含与相应事件类型相关的标签的**所有内容**的保留期都会由此事件触发。也就是说，将会开始保留上面关系图中的所有内容。这可能并不符合你的预期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p117">It's important to understand that if you don't specify an asset ID or keywords for an event, **all of the content** with a label of that event type will have its retention period triggered by the event. This means that in the diagram above, all of the content would start being retained. This may not be what you intend.</span></span> 
  
<span data-ttu-id="c1bd0-p118">最后请注意，每个标签都有自己的保留设置。在本示例中，它们全都指定保留 10 年，但事件也可触发保留期不同的各个标签。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p118">Finally, remember that each label has its own retention settings. In this example, they all specify 10 years, but it's possible for an event to trigger labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="c1bd0-153">如何设置事件驱动保留</span><span class="sxs-lookup"><span data-stu-id="c1bd0-153">How to set up event-driven retention</span></span>

<span data-ttu-id="c1bd0-p119">下面是事件驱动保留的简要工作流，后面紧跟着是更详细的步骤。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p119">Here's the high-level workflow for event-driven retention. More detailed steps follow below.</span></span>
  
![事件驱动保留的设置工作流的关系图](media/161146d9-e0fc-4248-abc1-a18045eaad5c.png)
  
### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="c1bd0-157">第 1 步：创建保留期以事件为依据的标签</span><span class="sxs-lookup"><span data-stu-id="c1bd0-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="c1bd0-158">在安全与合规中心内的左侧导航栏中，依次选择“分类”\*\*\*\* 下的“标签”\*\*\*\*\>“创建标签”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-158">In the Security &amp; Compliance Center, in the left navigation, under **Classifications**, choose **Labels** \> **Create a label**.</span></span>
  
<span data-ttu-id="c1bd0-p120">创建标签后，启用“保留”，再按如下所示选择选项，以根据事件保留或删除内容。也就是说，在第 5 步中在“事件”\*\*\*\* 页上创建事件前，保留设置不会生效。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p120">When you create the label, turn on retention, and then choose the option shown below to retain or delete the content based on an event. This means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="c1bd0-p121">请注意，事件驱动保留通常用于分类为记录的内容。因此，创建基于事件的标签时，通常会选中“使用标签将内容分类为记录”\*\*\*\* 选项。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p121">Note that event-driven retention is typically used for content that's classified as a record. For this reason, when you create labels based on an event, you typically choose the option to **Use label to classify content as a "Record"**.</span></span>
  
<span data-ttu-id="c1bd0-163">另请注意，事件驱动保留要求保留设置必须：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-163">Also note that event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="c1bd0-164">保留内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-164">Retain the content.</span></span>
    
- <span data-ttu-id="c1bd0-165">在保留期到期时自动删除内容或触发处置评审。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![让标签基于事件的选项](media/a4902281-5196-4194-9737-f30231d95861.png)
  
### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="c1bd0-167">第 2 步：选择与此标签关联的事件类型</span><span class="sxs-lookup"><span data-stu-id="c1bd0-167">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="c1bd0-p122">在标签设置中，选择让标签基于**事件**的选项后，便会看到“选择事件类型”\*\*\*\* 选项。事件类型就是对要与标签相关联的事件的一般描述。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p122">In the label settings, after you choose the option to base the label on **an event**, you'll see the option to **Choose an event type**. An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="c1bd0-170">例如，如果创建“产品生存期”事件类型，所创建基于事件的标签的名称描述了，要将标签应用于什么类型的内容（如“产品开发文件”或“产品业务决策记录”）。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-170">For example, if you create an event type named Product Lifetime, you'll create event-based labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>
  
<span data-ttu-id="c1bd0-171">请注意，一旦选择事件类型和创建标签后，便无法再更改事件类型。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-171">Note that once you choose an event type and create the label, the event type cannot be changed.</span></span>
  
![用于创建或选择事件类型的选项](media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-label"></a><span data-ttu-id="c1bd0-173">第 3 步：发布或自动应用标签</span><span class="sxs-lookup"><span data-stu-id="c1bd0-173">Step 3: Publish or auto-apply the label</span></span>

<span data-ttu-id="c1bd0-p123">就像任何标签一样，必须发布或自动应用基于事件的标签，才能将标签手动或自动应用于内容。请在“标签”\*\*\*\* 页上执行此操作。请注意，将内容分类为记录的标签只能在发布后手动应用于内容，而不能自动应用于内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p123">Just like any label, you need to publish or auto-apply an event-based label, so that it's manually or automatically applied to content. Do this on the **Labels** page. Note that labels that classify content as a record can only be published and manually applied to content; they can't be auto-applied to content.</span></span> 
  
![用于发布或自动应用标签的选项](media/c9232c54-bbc0-40d2-abc2-122d5d1e70af.png)
  
### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="c1bd0-178">第 4 步：输入资产 ID</span><span class="sxs-lookup"><span data-stu-id="c1bd0-178">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="c1bd0-p124">在事件驱动标签应用于内容后，你可以输入每项的资产 ID。例如，组织可能会使用：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p124">After an event-driven label is applied to content, you can enter an asset ID for each item. For example, your organization might use:</span></span>
  
- <span data-ttu-id="c1bd0-181">产品代码：可用于仅保留特定产品的内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-181">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="c1bd0-182">项目代码：可用于仅保留特定项目的内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-182">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="c1bd0-183">员工 ID：可用于仅保留特定人员的内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-183">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="c1bd0-p125">请注意，“资产 ID”就是 SharePoint 和 OneDrive for Business 中的另一文档属性。组织可能已使用其他文档属性和 ID 来分类内容。如果是这样，也可以在创建事件时使用这些属性和值（请参阅下面的第 6 步）。重要的是，组织必须在文档属性中使用一些属性:值组合，以便关联相应项和事件类型。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p125">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business. Your organization may already use other document properties and IDs to classify content. If so, you can also use those properties and values when you create an event - see Step 6 below. The important point is that your organization must use some property:value combination in the document properties to associate that item with an event type.</span></span>
  
![用于输入资产 ID 的文本框](media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="c1bd0-189">第 5 步：创建事件</span><span class="sxs-lookup"><span data-stu-id="c1bd0-189">Step 5: Create an event</span></span>

<span data-ttu-id="c1bd0-p126">当相应事件类型的特定实例（例如，产品的生存期结束）发生时，请转到安全与合规中心内的“事件”页，并创建事件。需要通过创建事件来手动触发事件。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p126">When a particular instance of that event type occurs - for example, a product reaches its end of life - go to the Events page in the Security &amp; Compliance Center and create an event. You need to manually trigger an event by creating it.</span></span>
  
![安全与合规中心内的“事件”页](media/811bddfb-a7e9-4990-bf5e-abe0dfb91809.png)
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="c1bd0-193">第 6 步：选择第 2 步中标签使用的相同事件类型</span><span class="sxs-lookup"><span data-stu-id="c1bd0-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="c1bd0-p127">创建事件后，选择第 2 步中标签使用的相同事件类型（例如，“产品生存期”）。只有包含与相应事件类型关联的标签，内容的保留期才会被触发。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p127">When you create the event, choose the same event type used by the label in step 2 - for example, Product Lifetime. Only content with labels applied to it of that event type will have its retention period triggered.</span></span>
  
![“事件设置”中用于选择事件类型的选项](media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="c1bd0-197">第 7 步：输入关键字或资产 ID</span><span class="sxs-lookup"><span data-stu-id="c1bd0-197">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="c1bd0-p128">现在指定 SharePoint 和 OneDrive 内容的资产 ID，或指定 Exchange 内容的关键字，以缩小内容范围。对于资产 ID，只会对包含指定属性:值对的内容强制执行保留操作。如果未输入资产 ID，包含与相应事件类型关联的标签的**所有内容**都会被应用相同的保留日期。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p128">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content or keywords for Exchange content. For asset IDs, retention will be enforced only on content with the specified property:value pair. If an asset ID is not entered, **all of the content** with labels of that event type get the same retention date applied to them.</span></span> 
  
<span data-ttu-id="c1bd0-p129">请注意，“资产 ID”就是 SharePoint 和 OneDrive for Business 中的另一文档属性。如果使用的是“资产 ID”属性，应在下面的资产 ID 框中输入 ComplianceAssetID:\<value\>。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p129">Understand that Asset ID is simply another document property in SharePoint and OneDrive for Business. If you're using the Asset ID property, you would enter ComplianceAssetID:\<value\> in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="c1bd0-p130">组织可能已向与此事件类型相关的文档应用其他属性和 ID。例如，如果你需要检测特定产品的记录，那么 ID 可能是自定义属性 ProductID 和值“XYZ”的组合。在这种情况下，应在下面的资产 ID 框中输入 ProductID:XYZ。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p130">Your organization might have applied other properties and IDs to the documents related to this event type. For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ". In this case, you'd enter ProductID:XYZ in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="c1bd0-p131">对于 Exchange 项，可添加关键字。可使用搜索运算符（如 AND、OR 和 NOT）优化查询。若要详细了解运算符，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p131">For Exchange items, you can include keywords. You can refine your query by using search operators like AND, OR, and NOT. For more information on operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="c1bd0-p132">最后，选择事件发生日期。此日期用作保留期的开始日期。在你创建事件后，事件日期会同步到包含与相应事件类型关联的标签、资产 ID 和关键字的所有内容。与任何标签一样，此同步最长可能需要 7 天才能完成。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p132">Finally, choose the date when the event occurred; this date is used as the start of the retention period. After you create an event, that event date is synced to all of the content with a label of that event type, asset ID, and keywords. Like any label, this syncing can take up to 7 days.</span></span>
  
![“事件设置”页](media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)
  
## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="c1bd0-213">使用内容搜索来查找所有包含特定标签或资产 ID 的内容</span><span class="sxs-lookup"><span data-stu-id="c1bd0-213">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="c1bd0-214">在标签分配到内容后，可使用安全与合规中心内的内容搜索，查找所有已使用特定标签进行分类或包含特定资产 ID 的内容。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-214">After labels are assigned to content, you can use content search in the Security &amp; Compliance Center to find all content that's classified with a specific label or that contains a specific asset ID.</span></span>
  
<span data-ttu-id="c1bd0-215">创建内容搜索后：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-215">When you create a content search:</span></span>
  
- <span data-ttu-id="c1bd0-216">若要查找所有包含特定标签的内容，请选择“合规性标记”\*\*\*\* 条件，再输入完整或部分标签名称并使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-216">To find all content with a specific label, choose the **Compliance Tag** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="c1bd0-217">若要查找所有包含特定资产 ID 的内容，请输入 **ComplianceAssetID** 属性和值，如 ComplianceAssetID:\<value\>。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-217">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, like ComplianceAssetID:\<value\>.</span></span> 
    
<span data-ttu-id="c1bd0-218">有关详细信息，请参阅[适用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-218">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="c1bd0-219">权限</span><span class="sxs-lookup"><span data-stu-id="c1bd0-219">Permissions</span></span>

<span data-ttu-id="c1bd0-p133">评审者必须是包含 **“处置管理”** 角色和 **“仅供查看审核日志”** 角色的角色组的成员，才能获取对“事件”\*\*\*\* 页的访问权限。建议新建“处置评审者”角色组，向此角色组添加这两个角色，再将成员添加到角色组中。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p133">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="c1bd0-222">有关详细信息，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-222">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="c1bd0-223">使用 PowerShell 自动触发事件</span><span class="sxs-lookup"><span data-stu-id="c1bd0-223">Automate events by using PowerShell</span></span>

<span data-ttu-id="c1bd0-p134">在 Office 365 安全与合规中心内，只能手动创建事件；事件无法在发生时自动触发。不过，可使用 PowerShell 脚本在业务应用程序中自动触发基于事件的保留。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p134">In the Office 365 Security &amp; Compliance Center, you can only create events manually; it's not possible to automatically trigger an event when it occurs. However, you can use a PowerShell script to automate event-based retention from your business applications.</span></span>
  
<span data-ttu-id="c1bd0-p135">目前，我们正在努力开发 API，以便用户能关联业务应用程序（如 HR、CRM 或财务应用程序）和事件驱动保留。例如，你将能关联 HR 系统和事件驱动保留，这样当某位员工离开组织时，就会自动触发相应事件类型的事件。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-p135">We are currently working on APIs, so that you can connect your business applications (such as HR, CRM, or financial applications) to event-driven retention. For example, you'll be able to connect your HR system to event-driven retention, so that when an employee leaves the organization, and event of that event type is automatically triggered.</span></span>
  
<span data-ttu-id="c1bd0-228">在此之前，可对事件驱动保留使用下面的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c1bd0-228">Until then, here are the PowerShell cmdlets available for event-driven retention:</span></span>
  
- [<span data-ttu-id="c1bd0-229">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="c1bd0-229">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="c1bd0-230">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="c1bd0-230">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="c1bd0-231">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="c1bd0-231">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="c1bd0-232">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="c1bd0-232">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="c1bd0-233">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="c1bd0-233">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="c1bd0-234">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="c1bd0-234">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

