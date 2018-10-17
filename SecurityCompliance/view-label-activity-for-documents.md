---
title: 查看文档的标签活动
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 5/9/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: af341600-5f68-40b3-a73e-73562715acd1
description: 使用 Office 365 安全与合规中心内的标签活动资源管理器，可快速搜索和查看过去 30 天内 SharePoint 和 OneDrive for Business 中所有内容的标签活动。此为实时数据，可便于你明确了解租户中发生了什么。
ms.openlocfilehash: 69e99ea7af683d7850cd56f356ad0ac99f8c084e
ms.sourcegitcommit: 397a5fe594e4cf4bb64c0c6f233d310ef3cbd922
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25540388"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="9f59f-104">查看文档的标签活动</span><span class="sxs-lookup"><span data-stu-id="9f59f-104">View label activity for documents</span></span>

<span data-ttu-id="9f59f-p102">建议在创建标签后验证这些标签是否已按预期应用于内容。使用 Office 365 安全与合规中心内的标签活动资源管理器，可快速搜索和查看过去 30 天内 SharePoint 和 OneDrive for Business 中所有内容的标签活动。此为实时数据，可便于你明确了解租户中发生了什么。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p102">After you create your labels, you'll want to verify that they're being applied to content as you intended. With the Label Activity Explorer in the Office 365 Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days. This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="9f59f-108">例如，标签活动资源管理器可用于：</span><span class="sxs-lookup"><span data-stu-id="9f59f-108">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="9f59f-109">查看每个标签每天应用多少次（最多查看 30 天的应用次数）。</span><span class="sxs-lookup"><span data-stu-id="9f59f-109">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="9f59f-110">查看谁在哪天标记了哪个文件（其中还提供指向文件驻留网站的链接）。</span><span class="sxs-lookup"><span data-stu-id="9f59f-110">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="9f59f-111">查看哪些文件的标签已变更或遭删除、新旧标签分别是什么，以及更改者是谁。</span><span class="sxs-lookup"><span data-stu-id="9f59f-111">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="9f59f-p103">筛选数据，以查看特定标签、文件或用户的所有标签活动。还可以按位置（SharePoint 还是 OneDrive for Business）以及标签是手动应用还是自动应用来筛选标签活动。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p103">Filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="9f59f-p104">查看文件夹或各个文档的标签活动。即将可以查看文件夹中有多少个文件继承文件夹的标签。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p104">View label activity for folders as well as individual documents. Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="9f59f-116">若要转到标签活动资源管理器，请在安全与合规中心内依次单击“数据管理”\*\*\*\*\>“标签活动资源管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9f59f-116">You can find the Label Activity Explorer in the Security &amp; Compliance Center \> **Data governance** \> **Label Activity Explorer**.</span></span>
  
<span data-ttu-id="9f59f-117">请注意，必须有 Office 365 企业版 E5 订阅，才能使用标签活动资源管理器。</span><span class="sxs-lookup"><span data-stu-id="9f59f-117">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![标签活动资源管理器](media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="9f59f-119">查看文件或文件夹的标签活动</span><span class="sxs-lookup"><span data-stu-id="9f59f-119">View label activities for files or folders</span></span>

<span data-ttu-id="9f59f-p105">在标签活动资源管理器的顶部，可选择是查看文件的标签活动，还是查看文件夹的标签活动。请注意，文件夹活动只包含文件夹本身的活动，并不包含文件夹内文件的活动。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p105">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders. Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="9f59f-p106">建议查看文件夹的标签活动，因为文件夹中的所有文件都会继承文件夹的标签（已显式应用有标签的文件除外）。因此，标记文件夹可能会影响大量文件。有关详细信息，请参阅[向 SharePoint 库、文件夹或文档集中的所有内容应用默认保留标签](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p106">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them). Therefore, labeling folders might affect a significant number of files. For more information, see [Applying a default label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![用于显示文件和文件夹的标签活动的下拉菜单](media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="9f59f-126">标签活动</span><span class="sxs-lookup"><span data-stu-id="9f59f-126">Label activities</span></span>

 <span data-ttu-id="9f59f-p107">“标签活动”\*\*\*\* 包括所有标签操作：**添加**、**删除**或**更改**标签。使用此视图，可全面了解每个标签每天应用于多少个文件。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p107">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label. You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="9f59f-129">标签更改</span><span class="sxs-lookup"><span data-stu-id="9f59f-129">Label changes</span></span>

 <span data-ttu-id="9f59f-p108">“标签更改”\*\*\*\* 包括可能存在风险的标签**删除**或**更改**操作。使用此视图，可快速查看这类存在风险的操作，以及谁执行了这些操作。在图表下面的活动列表中，可选择一个文件，再单击此文件在右侧细节窗格中的链接。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p108">**Label changes** includes the potentially risky actions of **removing** or **changing** a label. You can use this view to quickly see such risky actions and the user who performed them. In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![标签活动的细节窗格](media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="9f59f-134">筛选标签活动</span><span class="sxs-lookup"><span data-stu-id="9f59f-134">Filter label activity</span></span>

<span data-ttu-id="9f59f-p109">可快速筛选数据，以查看特定标签、文件或用户的所有标签活动。也可以按位置（SharePoint 还是 OneDrive for Business）以及标签是手动应用还是自动应用来筛选标签活动。</span><span class="sxs-lookup"><span data-stu-id="9f59f-p109">You can quickly filter the data to see all the label activity for a specific label, file, or user. You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![标签活动筛选器](media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

