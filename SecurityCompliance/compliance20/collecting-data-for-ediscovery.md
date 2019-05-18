---
title: 在高级电子数据展示中收集事例数据
ms.author: esclee
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8e67c3c8a693e627bade9e581f0f1e246bf6802a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151884"
---
# <a name="collect-data-for-a-case-in-advanced-ediscovery"></a><span data-ttu-id="4727b-102">在高级电子数据展示中收集事例数据</span><span class="sxs-lookup"><span data-stu-id="4727b-102">Collect data for a case in Advanced eDiscovery</span></span>

<span data-ttu-id="4727b-103">确定了您的保管人和数据源对您的情况有意义之后, 就可以确定要深入研究的文档集。</span><span class="sxs-lookup"><span data-stu-id="4727b-103">Once you have identified custodians and data sources that are of interest for your case, it's time to identify the set of documents to delve into.</span></span> <span data-ttu-id="4727b-104">您可以使用高级电子数据展示中的搜索工具, 在 Office 365 中从 custodial 和非 custodial 位置进行识别。</span><span class="sxs-lookup"><span data-stu-id="4727b-104">You can use the Search tool in Advanced eDiscovery to identify these from custodial and non-custodial locations in Office 365.</span></span>

<span data-ttu-id="4727b-105">运行搜索后, 您将能够查看检索到的项目的统计信息, 例如与搜索查询匹配项目数最多的位置。</span><span class="sxs-lookup"><span data-stu-id="4727b-105">After you run a search, you will be able to view statistics on the retrieved items such as the locations that had the most items that matched the search query.</span></span> <span data-ttu-id="4727b-106">您还可以预览结果的子集。</span><span class="sxs-lookup"><span data-stu-id="4727b-106">You can also preview a subset of the results.</span></span> <span data-ttu-id="4727b-107">在确定了要进一步检查的文档集后, 可以将搜索结果添加到审阅集以供收集和处理。</span><span class="sxs-lookup"><span data-stu-id="4727b-107">When you've identified the set of documents that want to further examine, you can add the search results to a review set to collect and process.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="4727b-108">Create a search</span><span class="sxs-lookup"><span data-stu-id="4727b-108">Create a search</span></span>

<span data-ttu-id="4727b-109">单击 "**搜索**" 选项卡上的 "**新建搜索**" 将启动一个向导, 引导您完成创建搜索的向导。</span><span class="sxs-lookup"><span data-stu-id="4727b-109">Clicking **New search** on the **Searches** tab will start a wizard that guides you through creating a search.</span></span> <span data-ttu-id="4727b-110">有关如何创建搜索的详细信息, 请参阅[创建搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="4727b-110">For detailed information on how to create a search, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="4727b-111">创建搜索后, 会显示包含详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="4727b-111">After a search is created, a flyout page with details is displayed.</span></span> <span data-ttu-id="4727b-112">请注意, "**统计**" 和 "**预览**" 按钮最初显示为灰色, 因为尚未完成搜索。</span><span class="sxs-lookup"><span data-stu-id="4727b-112">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search has not completed yet.</span></span> <span data-ttu-id="4727b-113">您可以在 "**搜索**" 选项卡上跟踪搜索进度。</span><span class="sxs-lookup"><span data-stu-id="4727b-113">You can keep track of the progress of the search on the **Searches** tab.</span></span>

## <a name="view-search-results-and-statistics"></a><span data-ttu-id="4727b-114">查看搜索结果和统计信息</span><span class="sxs-lookup"><span data-stu-id="4727b-114">View search results and statistics</span></span>
<span data-ttu-id="4727b-115">内容搜索有两个组件: 统计信息 (估计) 和预览。</span><span class="sxs-lookup"><span data-stu-id="4727b-115">There are two components of a content search: Statistics (Estimates) and Preview.</span></span> <span data-ttu-id="4727b-116">由于每个组件都已完成, 在**搜索**选项卡上的相应列中显示的状态将从 "已**提交**到**正在进行**" 更改为 "**已完成**"。</span><span class="sxs-lookup"><span data-stu-id="4727b-116">As each of these components complete, you will see the status displayed in the corresponding columns on the **Searches** tab change from from **Submitted** to **In progress** to **Completed**.</span></span>

<span data-ttu-id="4727b-117">完成搜索估计后, 单击搜索以显示弹出页面, 这将显示有关搜索结果的一些高级统计信息。</span><span class="sxs-lookup"><span data-stu-id="4727b-117">Once the search estimate is completed, click the search to display the flyout page, which will display some high-level statistics about the results of the search.</span></span> <span data-ttu-id="4727b-118">在这种情况下, "**统计**" 按钮将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4727b-118">At this point, the **Statistics** button will be active.</span></span> <span data-ttu-id="4727b-119">您可以单击它以查看搜索统计信息, 例如:</span><span class="sxs-lookup"><span data-stu-id="4727b-119">You can click it to see search statistics, such as:</span></span>

- <span data-ttu-id="4727b-120">Summary</span><span class="sxs-lookup"><span data-stu-id="4727b-120">Summary</span></span>
- <span data-ttu-id="4727b-121">顶部位置</span><span class="sxs-lookup"><span data-stu-id="4727b-121">Top locations</span></span>
- <span data-ttu-id="4727b-122">Queries</span><span class="sxs-lookup"><span data-stu-id="4727b-122">Queries</span></span>

<span data-ttu-id="4727b-123">有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="4727b-123">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

<span data-ttu-id="4727b-124">完成预览后,**预览**按钮将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4727b-124">Once preview is completed, the **Preview** button will be active.</span></span> <span data-ttu-id="4727b-125">单击它可预览结果的样本子集。</span><span class="sxs-lookup"><span data-stu-id="4727b-125">Click it to preview a sampled subset of the results.</span></span>

## <a name="adding-search-results-to-a-review-set"></a><span data-ttu-id="4727b-126">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="4727b-126">Adding search results to a review set</span></span>

<span data-ttu-id="4727b-127">当您准备收集和处理整个搜索结果时, 可以通过将其添加到审阅集来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4727b-127">When you are ready to collect and process the entire results of a search, you can do so by adding it to a review set.</span></span> <span data-ttu-id="4727b-128">有关详细信息, 请参阅[将数据添加到审阅集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="4727b-128">For details, see [Add data to a review set](add-data-to-review-set.md).</span></span> 