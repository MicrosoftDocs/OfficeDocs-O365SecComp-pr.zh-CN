---
title: 查询审阅集中的数据
ms.author: markjjo
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
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154004"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="49879-102">查询审阅集中的数据</span><span class="sxs-lookup"><span data-stu-id="49879-102">Query the data in a review set</span></span>

<span data-ttu-id="49879-103">在大多数情况下, 能够深入了解审阅集中存在的内容, 并对其进行组织以提高效率以供查看, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="49879-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="49879-104">在审阅集中的查询使您能够将重点放在符合您一次定义的条件的文档子集上。</span><span class="sxs-lookup"><span data-stu-id="49879-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="49879-105">在审阅集中创建和运行查询</span><span class="sxs-lookup"><span data-stu-id="49879-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="49879-106">若要在审阅集中创建和运行查询, 请单击您的审阅集中的 "新建查询"。</span><span class="sxs-lookup"><span data-stu-id="49879-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="49879-107">命名查询并定义条件后, 请单击 "保存" 以运行查询。</span><span class="sxs-lookup"><span data-stu-id="49879-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="49879-108">若要运行以前保存的查询, 只需单击已保存的查询即可。</span><span class="sxs-lookup"><span data-stu-id="49879-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="49879-109">有关可以搜索的元数据列表, 请参阅[文档元数据字段](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="49879-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="49879-110">构建查询</span><span class="sxs-lookup"><span data-stu-id="49879-110">Building your query</span></span>

<span data-ttu-id="49879-111">您可以在关键字条件卡中使用条件卡片和查询语言的组合生成查询。</span><span class="sxs-lookup"><span data-stu-id="49879-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="49879-112">您可以将条件卡组合成一个块, 以创建更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="49879-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="49879-113">条件卡片</span><span class="sxs-lookup"><span data-stu-id="49879-113">Condition card</span></span>

<span data-ttu-id="49879-114">审阅集中的每个可搜索字段都有一个对应的条件卡, 可用于生成查询。</span><span class="sxs-lookup"><span data-stu-id="49879-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="49879-115">有多种类型的条件卡:</span><span class="sxs-lookup"><span data-stu-id="49879-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="49879-116">Freetext: freetext 条件卡片用于文本字段, 如 subject。</span><span class="sxs-lookup"><span data-stu-id="49879-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="49879-117">您可以通过用逗号分隔多个搜索词来列出它们。</span><span class="sxs-lookup"><span data-stu-id="49879-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="49879-118">日期: 日期条件卡片用于日期字段 (如 "上次修改日期")。</span><span class="sxs-lookup"><span data-stu-id="49879-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="49879-119">搜索选项: 搜索选项条件卡片将为您的审阅集中的特定字段提供可能的值列表。</span><span class="sxs-lookup"><span data-stu-id="49879-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="49879-120">这用于在您的审核集中有有限数量的可能值的字段, 如发件人。</span><span class="sxs-lookup"><span data-stu-id="49879-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="49879-121">关键字: 关键字条件卡片是 freetext 条件卡的特定实例, 可用于搜索术语, 或在中使用类似 KQL 的查询语言。</span><span class="sxs-lookup"><span data-stu-id="49879-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="49879-122">有关更多详细信息, 请参阅下文。</span><span class="sxs-lookup"><span data-stu-id="49879-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="49879-123">查询语言</span><span class="sxs-lookup"><span data-stu-id="49879-123">Query language</span></span>

<span data-ttu-id="49879-124">除了条件卡片之外, 还可以使用关键字卡片中类似于 KQL 的查询语言来手工创建查询。</span><span class="sxs-lookup"><span data-stu-id="49879-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="49879-125">查询语言支持标准 KQL 语法, 如 AND、OR、NOT 和 NEAR (n)。</span><span class="sxs-lookup"><span data-stu-id="49879-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="49879-126">它还支持单字符通配符 (？) 和多字符通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="49879-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="49879-127">筛选</span><span class="sxs-lookup"><span data-stu-id="49879-127">Filter</span></span>

<span data-ttu-id="49879-128">除了可以保存的查询之外, 还可以使用筛选器将其他条件动态覆盖到查询结果中。</span><span class="sxs-lookup"><span data-stu-id="49879-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="49879-129">筛选器与查询的不同之处在于以下几个重要方式:</span><span class="sxs-lookup"><span data-stu-id="49879-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="49879-130">筛选器是瞬态的 (即它们不会持续在不同的会话中), 而是将查询保存到评审集。</span><span class="sxs-lookup"><span data-stu-id="49879-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="49879-131">筛选器始终是累加的;筛选器将应用于您在此时生效的查询的顶部, 而应用查询将替换有效的查询。</span><span class="sxs-lookup"><span data-stu-id="49879-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>