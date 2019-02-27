---
title: 搜索统计信息
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a2234d0a0e94e3fbb15f8fac8f6e49cc7b26cfb2
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295654"
---
# <a name="search-statistics"></a><span data-ttu-id="8b45c-102">搜索统计信息</span><span class="sxs-lookup"><span data-stu-id="8b45c-102">Search statistics</span></span>

<span data-ttu-id="8b45c-p101">验证搜索结果的一种方法是查看结果周围的统计信息, 以确保它们符合您的预期。搜索完成后, "搜索详细信息" 浮出控件上将显示高级别统计信息:</span><span class="sxs-lookup"><span data-stu-id="8b45c-p101">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations. When a search completes, high-level statistics are shown on the search details flyout:</span></span>
- <span data-ttu-id="8b45c-105">搜索检索到的项目数和数量</span><span class="sxs-lookup"><span data-stu-id="8b45c-105">Number and volume of items retrieved by the search</span></span>
- <span data-ttu-id="8b45c-106">在搜索位置中找到的部分已编制索引/未编制索引的项目的编号和数量</span><span class="sxs-lookup"><span data-stu-id="8b45c-106">Number and volume of partially indexed/unindexed items that were found in the search locations</span></span>
- <span data-ttu-id="8b45c-p102">搜索的邮箱和位置的数量。若要查看更详细的统计信息, 请单击 "搜索详细信息" 浮出控件中的 "统计信息"。</span><span class="sxs-lookup"><span data-stu-id="8b45c-p102">Number of mailboxes and locations searched. In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary"></a><span data-ttu-id="8b45c-109">摘要</span><span class="sxs-lookup"><span data-stu-id="8b45c-109">Summary</span></span>

<span data-ttu-id="8b45c-p103">在摘要视图中, 你可以看到按位置类型 (如 Exchange) 细分的搜索结果。对于每个位置类型, 您可以查看以下内容:</span><span class="sxs-lookup"><span data-stu-id="8b45c-p103">In Summary view, you can see the search results broken down by location type (e.g. Exchange). For each location type, you can see:</span></span>
- <span data-ttu-id="8b45c-112">包含符合搜索条件的项目的位置数</span><span class="sxs-lookup"><span data-stu-id="8b45c-112">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="8b45c-113">来自符合搜索条件的这些位置的项目数</span><span class="sxs-lookup"><span data-stu-id="8b45c-113">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="8b45c-114">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="8b45c-114">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations"></a><span data-ttu-id="8b45c-115">顶部位置</span><span class="sxs-lookup"><span data-stu-id="8b45c-115">Top locations</span></span>

<span data-ttu-id="8b45c-p104">在 "顶端位置" 视图中, 可以看到具有最匹配项的各个位置。对于每个位置, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="8b45c-p104">In Top locations view, you see the individual locations with the most matches. For each location, you will see:</span></span>
- <span data-ttu-id="8b45c-118">位置名称 (例如, SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="8b45c-118">Location name (e.g. SharePoint URL)</span></span>
- <span data-ttu-id="8b45c-119">位置类型</span><span class="sxs-lookup"><span data-stu-id="8b45c-119">Location type</span></span>
- <span data-ttu-id="8b45c-120">匹配搜索条件的项目数</span><span class="sxs-lookup"><span data-stu-id="8b45c-120">Number of items that matched the search conditions</span></span>
- <span data-ttu-id="8b45c-121">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="8b45c-121">Total volume of items that matched the search conditions.</span></span>

## <a name="queries"></a><span data-ttu-id="8b45c-122">查询</span><span class="sxs-lookup"><span data-stu-id="8b45c-122">Queries</span></span>

<span data-ttu-id="8b45c-p105">如果您已在查询中使用 (c:s) 关键字或关键字行, 则可以在 "每个位置的查询视图" 类型中查看查询细目。对于每个位置类型, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="8b45c-p105">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type. For each location type, you will see:</span></span>

- <span data-ttu-id="8b45c-p106">部分: 此列将包含 "Primary" 或 "关键字" 一词。"Primary" 表示该行显示整个查询的统计信息, 而 "关键字" 表示查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="8b45c-p106">Part: this column will either have the word "Primary" or "Keyword". "Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="8b45c-p107">查询: 行所引用的实际查询组件。如果 Part 为 "Primary", 则为整个查询;如果 Part 为 "关键字", 你将在此处看到一个查询组件。</span><span class="sxs-lookup"><span data-stu-id="8b45c-p107">Query: the actual query component the row refers to. If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="8b45c-129">当您搜索所有 contentin 邮箱 (未指定任何关键字) 时, 实际查询是 (size > = 0), 以便返回所有项目</span><span class="sxs-lookup"><span data-stu-id="8b45c-129">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="8b45c-130">当您搜索 SharePoint Online 和 OneDrive for business 网站时, 将添加以下两个组件:</span><span class="sxs-lookup"><span data-stu-id="8b45c-130">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="8b45c-131">NOT IsExternalContent: 1-排除本地 SharePoint 组织中的任何内容</span><span class="sxs-lookup"><span data-stu-id="8b45c-131">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="8b45c-132">NOT isOneNotePage: 1-排除所有 OneNote 文件, 因为这些文件是与搜索查询相匹配的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="8b45c-132">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="8b45c-133">包含符合搜索条件的项目的位置的数量。</span><span class="sxs-lookup"><span data-stu-id="8b45c-133">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="8b45c-134">来自这些位置的符合搜索条件的项目数。</span><span class="sxs-lookup"><span data-stu-id="8b45c-134">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="8b45c-135">符合搜索条件的项的总数量。</span><span class="sxs-lookup"><span data-stu-id="8b45c-135">Total volume of items that matched the search conditions.</span></span>