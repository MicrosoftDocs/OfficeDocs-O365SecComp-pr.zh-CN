---
title: 在高级电子数据展示中收集数据事例 (预览)
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2e9e7836a2dc777410b88ffac1aea0c5137b7b89
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218992"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery-preview"></a><span data-ttu-id="4cd05-102">在高级电子数据展示中收集数据事例 (预览)</span><span class="sxs-lookup"><span data-stu-id="4cd05-102">Collect data for a case in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="4cd05-p101">确定了您的保管人和数据源对您的情况有意义之后, 就可以确定要深入研究的文档集。您可以使用高级电子数据展示 (预览版) 中的搜索工具, 在 Office 365 中从 custodial 和非 custodial 位置进行识别。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p101">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into. You can use the Search tool in Advanced eDiscovery (Preview) to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="4cd05-p102">运行搜索后, 您将能够查看检索到的项目的统计信息, 例如与搜索查询匹配项目数最多的位置。您还可以预览结果的子集。在确定了要进一步检查的文档集后, 可以将搜索结果添加到工作集以供收集和处理。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p102">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query. You can also preview a subset of the results. When you've identified the set of documents that want to further examine, you can add the search results to a working set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="4cd05-108">创建搜索</span><span class="sxs-lookup"><span data-stu-id="4cd05-108">Create a search</span></span>

<span data-ttu-id="4cd05-p103">单击 "**搜索**" 选项卡上的 "**新建搜索**" 将启动一个向导, 引导您完成创建搜索的向导。有关如何创建搜索的详细信息, 请参阅[创建搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p103">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search. For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="4cd05-p104">创建搜索后, 会显示包含详细信息的飞出页面。请注意, "**统计**" 和 "**预览**" 按钮最初显示为灰色, 因为尚未完成搜索。您可以在 "**搜索**" 选项卡上跟踪搜索进度。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p104">After a search is created, a flyout page with details is displayed. Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet. You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="4cd05-114">查看搜索结果和统计信息</span><span class="sxs-lookup"><span data-stu-id="4cd05-114">View search results and statistics</span></span>
<span data-ttu-id="4cd05-p105">内容搜索有两个组件: 统计信息 (估计) 和预览。由于每个组件都已完成, 在**搜索**选项卡上的相应列中显示的状态将从 "已**提交**到**正在进行**" 更改为 "**已完成**"。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p105">There are two components of a content search: Statistics (Estimates) and Preview. As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="4cd05-p106">完成搜索估计后, 单击搜索以显示弹出页面, 这将显示有关搜索结果的一些高级统计信息。在这种情况下, "**统计**" 按钮将处于活动状态。您可以单击它以查看搜索统计信息, 例如:</span><span class="sxs-lookup"><span data-stu-id="4cd05-p106">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search. At this point, the **Statistics** button will be active. You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="4cd05-120">摘要</span><span class="sxs-lookup"><span data-stu-id="4cd05-120">Summary</span></span>
- <span data-ttu-id="4cd05-121">顶部位置</span><span class="sxs-lookup"><span data-stu-id="4cd05-121">Top locations</span></span>
- <span data-ttu-id="4cd05-122">查询</span><span class="sxs-lookup"><span data-stu-id="4cd05-122">Queries</span></span>
- <span data-ttu-id="4cd05-123">精简程序</span><span class="sxs-lookup"><span data-stu-id="4cd05-123">Refiners</span></span>

<span data-ttu-id="4cd05-124">有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="4cd05-124">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="4cd05-p107">完成预览后,**预览**按钮将处于活动状态。单击它可预览结果的样本子集。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p107">Once preview is completed, the **Preview** button will be active. Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-working-set"></a><span data-ttu-id="4cd05-127">将搜索结果添加到工作集</span><span class="sxs-lookup"><span data-stu-id="4cd05-127">Adding search results to a working set</span></span>

<span data-ttu-id="4cd05-p108">当您准备收集和处理整个搜索结果时, 可以通过将其添加到工作集中来执行此操作。有关详细信息, 请参阅[将数据添加到工作集](add-data-to-working-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd05-p108">When you are ready to collect and process the entire results of a search, you can do so by adding it to a working set. For details, see [Add data to a working set](add-data-to-working-set.md).</span></span> 