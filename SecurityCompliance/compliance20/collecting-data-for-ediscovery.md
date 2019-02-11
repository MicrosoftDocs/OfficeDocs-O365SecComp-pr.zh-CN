---
title: 收集数据高级电子数据展示 (Preview) 中用例
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 11e2c336512c91d65bd046c3022d5375ebecde4a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695048"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="d0ca2-102">收集数据高级电子数据展示 (Preview) 中用例</span><span class="sxs-lookup"><span data-stu-id="d0ca2-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="d0ca2-p101">一旦您确定管理员和感兴趣您用例的数据源，就可以确定的深入探讨的文档集。您可以使用高级电子数据展示 (Preview) 中搜索工具确定这些从 Office 365 中的监控和非监控位置。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="d0ca2-p102">运行搜索后，您将能够查看统计数据检索的项目，如有匹配的搜索查询的大多数项目的位置。您还可以预览结果的子集。您已确定的要进一步检查的文档集，可以将搜索结果添加为收集和处理工作集。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="d0ca2-108">创建搜索</span><span class="sxs-lookup"><span data-stu-id="d0ca2-108">Create a search</span></span>

<span data-ttu-id="d0ca2-p103">单击**搜索**选项卡上的**新的搜索**将启动一个向导，引导您完成创建搜索。有关如何创建搜索的详细信息，请参阅[Create 搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="d0ca2-p104">创建搜索后，将显示弹出页面的详细信息。请注意，**统计信息**和**预览**按钮最初灰显因为尚未完成搜索。您可以跟踪的**搜索**选项卡上的搜索的进度。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="d0ca2-114">查看搜索结果和统计信息</span><span class="sxs-lookup"><span data-stu-id="d0ca2-114">View search results and statistics</span></span>
<span data-ttu-id="d0ca2-p105">有两个组件的内容搜索： 统计信息 （估计值） 和预览。为每个完成这些组件，您将看到从**已提交**更改，为**正在**以**完成**在**搜索**选项卡上的相应列中显示的状态。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="d0ca2-p106">完成搜索 estimate 后，单击搜索以显示弹出页上，将显示有关搜索结果的一些高级统计信息。此时，**统计信息**按钮将处于活动状态。您可以单击以查看搜索统计信息，例如：</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="d0ca2-120">摘要</span><span class="sxs-lookup"><span data-stu-id="d0ca2-120">Summary</span></span>
- <span data-ttu-id="d0ca2-121">顶部的位置</span><span class="sxs-lookup"><span data-stu-id="d0ca2-121">Top locations</span></span>
- <span data-ttu-id="d0ca2-122">查询</span><span class="sxs-lookup"><span data-stu-id="d0ca2-122">Queries</span></span>
- <span data-ttu-id="d0ca2-123">精简程序</span><span class="sxs-lookup"><span data-stu-id="d0ca2-123">Refiners</span></span>

<span data-ttu-id="d0ca2-124">有关搜索统计信息的详细信息，请参阅[搜索统计信息](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="d0ca2-p107">完成预览后，**预览**按钮将处于活动状态。单击此按钮预览样本的结果的子集。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="d0ca2-127">添加到工作集的搜索结果</span><span class="sxs-lookup"><span data-stu-id="d0ca2-127">Adding search results to a working set</span></span>

<span data-ttu-id="d0ca2-p108">当您准备收集和处理整个的搜索结果时，您可以通过将其添加到工作集来完成操作。有关详细信息，请参阅[将数据添加到工作集](add-data-to-working-set.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ca2-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 