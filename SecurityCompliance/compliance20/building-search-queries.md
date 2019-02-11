---
title: 生成搜索查询
ms.author: markjjo
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
ms.openlocfilehash: c337b49491fca11e0ba5bc13d22ac3e54038c400
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695068"
---
# <a name="build-search-queries"></a><span data-ttu-id="1b327-102">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="1b327-102">Build search queries</span></span>

<span data-ttu-id="1b327-103">在生成您的查询，您可以使用各种关键字和条件定义要查找的项。</span><span class="sxs-lookup"><span data-stu-id="1b327-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="1b327-104">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="1b327-104">Keyword searches</span></span>

<span data-ttu-id="1b327-p101">在**关键字**框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用使用布尔运算符，例如**AND**、**或**、 \*\*\*\*，和**NEAR**更复杂的查询。您还可以搜索文档或搜索外部共享的文档中的敏感信息 （如社会保险号码）。如果保留关键字框为空，则将在搜索结果中包含位于指定的内容位置的所有内容。</span><span class="sxs-lookup"><span data-stu-id="1b327-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="1b327-p102">或者，您可以单击**显示关键字列表**复选框，键入每行中的关键字。如果这样做，每个行的关键字进行连接的逻辑运算符 ( **c:s**) 中创建的搜索查询的**OR**运算符功能类似的。</span><span class="sxs-lookup"><span data-stu-id="1b327-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="1b327-p103">为什么使用关键字列表？您可以获取显示的项目数与每个关键字匹配的统计信息。这可以帮助您快速识别的关键字是最 （和至少） 有效。行中，您还可以使用关键字短语 （用括号括起来）。有关搜索统计信息的详细信息，请参阅[搜索统计信息](search-statistics.md)。</span><span class="sxs-lookup"><span data-stu-id="1b327-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="1b327-117">条件</span><span class="sxs-lookup"><span data-stu-id="1b327-117">Conditions</span></span>
    
<span data-ttu-id="1b327-p104">您可以添加搜索条件以缩小搜索范围并返回更精确的结果集。每个条件向搜索查询创建和启动搜索时运行一个子句。条件逻辑**AND**运算符功能类似的逻辑运算符 (**c:c**) 通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的一个或多个条件。这是如何帮助条件以缩小结果。列表以及您可以使用搜索查询中的条件的说明，请参阅[关键字查询及搜索内容搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)中的"搜索条件"部分。</span><span class="sxs-lookup"><span data-stu-id="1b327-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


