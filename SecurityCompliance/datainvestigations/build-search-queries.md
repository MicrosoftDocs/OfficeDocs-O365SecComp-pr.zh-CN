---
title: 生成搜索查询
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
description: 使用 Microsoft 365 中的数据调查时, 使用关键字和条件缩小搜索范围的范围。
ms.openlocfilehash: 913306ff488d9cf2ba715c26eaa49f6f8e1473aa
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649937"
---
# <a name="build-search-queries"></a><span data-ttu-id="040a7-103">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="040a7-103">Build search queries</span></span>

<span data-ttu-id="040a7-104">在构建搜索查询时, 可以使用关键字来查找特定内容和条件, 以缩小搜索范围, 以返回与调查最相关的项目。</span><span class="sxs-lookup"><span data-stu-id="040a7-104">When building search queries, you can use keywords to find specific content and conditions to narrow the scope of the search to return items that are most relevant to your investigation.</span></span>

![使用关键字和条件缩小搜索结果范围](../media/SearchQueryBox.png)

## <a name="keyword-searches"></a><span data-ttu-id="040a7-106">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="040a7-106">Keyword searches</span></span>

<span data-ttu-id="040a7-107">在搜索查询的 "**关键字**" 框中键入关键字查询。</span><span class="sxs-lookup"><span data-stu-id="040a7-107">Type a keyword query in the **Keywords** box in the search query.</span></span> <span data-ttu-id="040a7-108">您可以指定关键字、电子邮件属性 (如发送和接收日期) 或文档属性 (如文件名称或上次更改文档的日期)。</span><span class="sxs-lookup"><span data-stu-id="040a7-108">You can specify keywords, email message properties, (such as sent and received dates), or document properties (such as file names or the date that a document was last changed).</span></span> <span data-ttu-id="040a7-109">您可以使用更复杂的查询, 这些查询使用布尔运算符, 例如**AND**、 **OR**、 **NOT**和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="040a7-109">You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="040a7-110">您还可以在 SharePoint 和 OneDrive (而不是电子邮件) 中搜索文档中的敏感信息 (如社会保险号), 或搜索在外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="040a7-110">You can also search for sensitive information (such as social security numbers) in documents in SharePoint and OneDrive (not in email messages), or search for documents that have been shared externally.</span></span> <span data-ttu-id="040a7-111">如果将 "**关键字**" 框留空, 则位于指定内容位置的所有内容都将包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="040a7-111">If you leave the **Keywords** box empty, all content located in the specified content locations is included in the search results.</span></span>
    
<span data-ttu-id="040a7-112">或者, 也可以单击 "**显示关键字列表**" 复选框, 并在每行中键入关键字或关键字短语。</span><span class="sxs-lookup"><span data-stu-id="040a7-112">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword or keyword phrase in each row.</span></span> <span data-ttu-id="040a7-113">如果执行此操作, 则每行中的关键字都将通过逻辑运算符 (表示为*c:s*) 连接到创建的搜索查询中的**OR**运算符的功能相似。</span><span class="sxs-lookup"><span data-stu-id="040a7-113">If you do this, the keywords in each row are connected by a logical operator (represented as *c:s*) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> <span data-ttu-id="040a7-114">这意味着搜索结果中包含任何行中包含任意关键字的项。</span><span class="sxs-lookup"><span data-stu-id="040a7-114">This means that items that contain any keyword in any row are included in the search results.</span></span>

![使用关键字列表获取查询中每个关键字的统计信息](../media/KeywordListSearch.png)

<span data-ttu-id="040a7-116">为什么要使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="040a7-116">Why use the keyword list?</span></span> <span data-ttu-id="040a7-117">您可以获取统计信息, 以显示与关键字列表中的每个关键字匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="040a7-117">You can get statistics that show how many items match each keyword in the keyword list.</span></span> <span data-ttu-id="040a7-118">这可帮助您快速识别最有效 (最少) 的关键字。</span><span class="sxs-lookup"><span data-stu-id="040a7-118">This can help you quickly identify the keywords that are the most (and least) effective.</span></span> <span data-ttu-id="040a7-119">您还可以在关键字列表的行中使用关键字短语 (括在括号中)。</span><span class="sxs-lookup"><span data-stu-id="040a7-119">You can also use a keyword phrase (surrounded by parentheses) in a row in the keywords list.</span></span> <span data-ttu-id="040a7-120">有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="040a7-120">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

> [!NOTE]
> <span data-ttu-id="040a7-121">为了帮助减少由大型关键字列表导致的问题, 在关键字列表中限制为最多20行。</span><span class="sxs-lookup"><span data-stu-id="040a7-121">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list.</span></span>

## <a name="conditions"></a><span data-ttu-id="040a7-122">条件</span><span class="sxs-lookup"><span data-stu-id="040a7-122">Conditions</span></span>
    
<span data-ttu-id="040a7-123">您可以添加搜索条件以缩小搜索范围, 并返回更精致的结果集。</span><span class="sxs-lookup"><span data-stu-id="040a7-123">You can add search conditions to narrow the scope of a search and return a more refined set of results.</span></span> <span data-ttu-id="040a7-124">每个条件都会向搜索查询添加一个子句, 该子句在您开始搜索时创建并运行。</span><span class="sxs-lookup"><span data-stu-id="040a7-124">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="040a7-125">条件以逻辑方式连接到关键字查询 (在 "关键字" 框中指定), 逻辑运算符 (表示为 " *c:c*") 与**AND**运算符的功能相似。</span><span class="sxs-lookup"><span data-stu-id="040a7-125">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (which is represented as *c:c*) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="040a7-126">这意味着项目必须同时满足关键字查询和要包含在搜索结果中的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="040a7-126">That means that items have to satisfy both the keyword query and one or more conditions to be included in the search results.</span></span> <span data-ttu-id="040a7-127">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="040a7-127">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="040a7-128">有关可在搜索查询中使用的条件的列表和说明, 请参阅[关键字查询和搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。</span><span class="sxs-lookup"><span data-stu-id="040a7-128">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>
