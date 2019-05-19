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
description: ''
ms.openlocfilehash: a33ecb6e1a2549b6bdc3bde9897b8a75e742b482
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151924"
---
# <a name="build-search-queries"></a><span data-ttu-id="4363f-102">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="4363f-102">Build search queries</span></span>

<span data-ttu-id="4363f-103">在生成查询时, 可以使用各种关键字和条件来定义要查找的项。</span><span class="sxs-lookup"><span data-stu-id="4363f-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="4363f-104">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="4363f-104">Keyword searches</span></span>

<span data-ttu-id="4363f-105">在 "**关键字**" 框中键入搜索查询。</span><span class="sxs-lookup"><span data-stu-id="4363f-105">Type a search query in **Keywords** box.</span></span> <span data-ttu-id="4363f-106">您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="4363f-106">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="4363f-107">您可以使用更复杂的查询, 这些查询使用布尔运算符, 例如**AND**、 **OR**、 **NOT**和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="4363f-107">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="4363f-108">您还可以在文档中搜索敏感信息 (如社会保险号), 或搜索在外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="4363f-108">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="4363f-109">如果将 "关键字" 框留空, 则位于指定内容位置的所有内容都将包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="4363f-109">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="4363f-110">或者, 也可以单击 "**显示关键字列表**" 复选框, 并在每行中键入关键字。</span><span class="sxs-lookup"><span data-stu-id="4363f-110">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="4363f-111">如果这样做, 每行上的关键字都将通过逻辑运算符 ( **c:s**) 连接, 该运算符在创建的搜索查询中的**OR**运算符的功能类似。</span><span class="sxs-lookup"><span data-stu-id="4363f-111">If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="4363f-112">为什么要使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="4363f-112">Why use the keyword list?</span></span> <span data-ttu-id="4363f-113">您可以获取显示与每个关键字匹配的项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="4363f-113">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="4363f-114">这可以帮助您快速确定哪些关键字最有效 (最少)。</span><span class="sxs-lookup"><span data-stu-id="4363f-114">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="4363f-115">您还可以在行中使用关键字短语 (括在括号中)。</span><span class="sxs-lookup"><span data-stu-id="4363f-115">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="4363f-116">有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="4363f-116">For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="4363f-117">条件</span><span class="sxs-lookup"><span data-stu-id="4363f-117">Conditions</span></span>
    
<span data-ttu-id="4363f-118">您可以添加搜索条件以缩小搜索范围, 并返回一组更细化的结果。</span><span class="sxs-lookup"><span data-stu-id="4363f-118">You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="4363f-119">每个条件都会向搜索查询添加一个子句, 该子句在您开始搜索时创建并运行。</span><span class="sxs-lookup"><span data-stu-id="4363f-119">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="4363f-120">条件以逻辑方式连接到关键字查询 (在 "关键字" 框中指定), 逻辑运算符 (**c:c**) 与**AND**运算符的功能相似。</span><span class="sxs-lookup"><span data-stu-id="4363f-120">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="4363f-121">这意味着项目必须同时满足关键字查询和要包含在结果中的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="4363f-121">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="4363f-122">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="4363f-122">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="4363f-123">有关可在搜索查询中使用的条件的列表和说明, 请参阅[内容搜索的关键字查询和搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。</span><span class="sxs-lookup"><span data-stu-id="4363f-123">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


