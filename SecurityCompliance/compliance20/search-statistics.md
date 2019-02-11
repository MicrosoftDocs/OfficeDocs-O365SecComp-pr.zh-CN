---
title: 搜索统计信息
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: 0cfc1e5f04887cbdbcc0be8854fc50d6f9b5f1f2
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706003"
---
# <a name="search-statistics"></a><span data-ttu-id="02def-102">搜索统计信息</span><span class="sxs-lookup"><span data-stu-id="02def-102">Search statistics</span></span>

<span data-ttu-id="02def-p101">您可以验证搜索结果的一种方法是查看您的结果，以确保它们与您的期望对齐周围的统计信息。在搜索完成后，高级统计信息将显示在搜索的详细信息弹出：</span><span class="sxs-lookup"><span data-stu-id="02def-p101">One way you can validate your search results is to look at the statistics around your results to make sure they align with your expectations. When a search completes, high-level statistics are shown on the search details flyout:</span></span>
- <span data-ttu-id="02def-105">号码和搜索检索的项目量</span><span class="sxs-lookup"><span data-stu-id="02def-105">Number and volume of items retrieved by the search</span></span>
- <span data-ttu-id="02def-106">号码和量部分编制索引/未编制索引的搜索位置中找到的项目</span><span class="sxs-lookup"><span data-stu-id="02def-106">Number and volume of partially indexed/unindexed items that were found in the search locations</span></span>
- <span data-ttu-id="02def-p102">搜索邮箱和位置的数量。才能查看更多详细统计信息，请单击"统计"从搜索的详细信息弹出。</span><span class="sxs-lookup"><span data-stu-id="02def-p102">Number of mailboxes and locations searched. In order to view more detailed statistics, click on "Statistics" from the search details flyout.</span></span>

## <a name="summary"></a><span data-ttu-id="02def-109">摘要</span><span class="sxs-lookup"><span data-stu-id="02def-109">Summary</span></span>

<span data-ttu-id="02def-p103">在摘要视图中，您可以看到按位置类型 (例如 Exchange) 划分的搜索结果。对于每个位置类型，您可以看到：</span><span class="sxs-lookup"><span data-stu-id="02def-p103">In Summary view, you can see the search results broken down by location type (e.g. Exchange). For each location type, you can see:</span></span>
- <span data-ttu-id="02def-112">有搜索条件匹配的项的位置数</span><span class="sxs-lookup"><span data-stu-id="02def-112">Number of locations that had items that matched the search conditions</span></span>
- <span data-ttu-id="02def-113">从这些位置的搜索条件匹配的项目数</span><span class="sxs-lookup"><span data-stu-id="02def-113">Number of items from these locations that matched the search conditions</span></span>
- <span data-ttu-id="02def-114">总搜索条件匹配的项目量。</span><span class="sxs-lookup"><span data-stu-id="02def-114">Total volume of items that matched the search conditions.</span></span>

## <a name="top-locations"></a><span data-ttu-id="02def-115">顶部的位置</span><span class="sxs-lookup"><span data-stu-id="02def-115">Top locations</span></span>

<span data-ttu-id="02def-p104">在顶部的位置视图中，您将看到与最匹配的各个位置。对于每个位置，您将看到：</span><span class="sxs-lookup"><span data-stu-id="02def-p104">In Top locations view, you see the individual locations with the most matches. For each location, you will see:</span></span>
- <span data-ttu-id="02def-118">位置名称 (例如 SharePoint URL)</span><span class="sxs-lookup"><span data-stu-id="02def-118">Location name (e.g. SharePoint URL)</span></span>
- <span data-ttu-id="02def-119">位置类型</span><span class="sxs-lookup"><span data-stu-id="02def-119">Location type</span></span>
- <span data-ttu-id="02def-120">匹配搜索条件的项目数</span><span class="sxs-lookup"><span data-stu-id="02def-120">Number of items that matched the search conditions</span></span>
- <span data-ttu-id="02def-121">总搜索条件匹配的项目量。</span><span class="sxs-lookup"><span data-stu-id="02def-121">Total volume of items that matched the search conditions.</span></span>

## <a name="queries"></a><span data-ttu-id="02def-122">查询</span><span class="sxs-lookup"><span data-stu-id="02def-122">Queries</span></span>

<span data-ttu-id="02def-p105">如果您使用了 (c:s) 关键字或关键字行在查询中，您可以看到每个位置类型的查询视图中的查询的细分。对于每个位置类型，您将看到：</span><span class="sxs-lookup"><span data-stu-id="02def-p105">If you have used (c:s) keyword or keyword rows in your query, then you can see the breakdown of your query in Queries view per location type. For each location type, you will see:</span></span>

- <span data-ttu-id="02def-p106">部件： 此列会单词"主"或"关键字"。"主要"表示行提供统计信息，介绍整个查询，而"关键字"表示查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="02def-p106">Part: this column will either have the word "Primary" or "Keyword". "Primary" means that the row presents statistics on the entire query, whereas "Keyword" means one of the query components.</span></span>

- <span data-ttu-id="02def-p107">查询： 行引用的实际查询组件。如果"主"部分，这将是整个查询。如果"关键字"部分，您将看到下面的查询组件之一。</span><span class="sxs-lookup"><span data-stu-id="02def-p107">Query: the actual query component the row refers to. If Part is "Primary", this will be the entire query; if Part was "Keyword", you will see one of the query components here.</span></span>
  
  - <span data-ttu-id="02def-129">在搜索内容的所有邮箱 （通过不指定任何关键字） 时，是实际的查询 (大小 > = 0)，以便返回所有项</span><span class="sxs-lookup"><span data-stu-id="02def-129">When you search all contentin mailboxes (by not specifying any keywords), the actual query is (size >= 0) so that all items are returned</span></span>
  
  - <span data-ttu-id="02def-130">在 SharePoint Online 和 OneDrive 搜索业务网站时，会添加两个以下组件：</span><span class="sxs-lookup"><span data-stu-id="02def-130">When you search SharePoint Online and OneDrive for Business sites, the two following components are added:</span></span>
    
    - <span data-ttu-id="02def-131">不 IsExternalContent:1-从内部部署 SharePoint 组织排除任何内容</span><span class="sxs-lookup"><span data-stu-id="02def-131">NOT IsExternalContent:1 - excludes any content from an on-premises SharePoint organization</span></span>
    
    - <span data-ttu-id="02def-132">不 isOneNotePage: 1-排除所有 OneNote 文件，因为这些都是相匹配的搜索查询的任何文档的重复项。</span><span class="sxs-lookup"><span data-stu-id="02def-132">NOT isOneNotePage: 1 - excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="02def-133">位置具有匹配的搜索条件的项目数。</span><span class="sxs-lookup"><span data-stu-id="02def-133">Number of locations that had items that matched the search conditions.</span></span>

- <span data-ttu-id="02def-134">从这些位置的搜索条件匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="02def-134">Number of items from these locations that matched the search conditions.</span></span>

- <span data-ttu-id="02def-135">总搜索条件匹配的项目量。</span><span class="sxs-lookup"><span data-stu-id="02def-135">Total volume of items that matched the search conditions.</span></span>

## <a name="refiners"></a><span data-ttu-id="02def-136">精简程序</span><span class="sxs-lookup"><span data-stu-id="02def-136">Refiners</span></span>

<span data-ttu-id="02def-p108">Exchange 邮箱中，优化器视图为您提供了 ItemClass、 发件人和收件人的其他损害。对于每个位置和优化器值，您可以看到多少个文档已返回在搜索。</span><span class="sxs-lookup"><span data-stu-id="02def-p108">For Exchange mailboxes, refiners view gives you additional breakdowns by ItemClass, Sender, and Recipient. For each location and refiner value, you can see how many documents were returned in the search.</span></span>