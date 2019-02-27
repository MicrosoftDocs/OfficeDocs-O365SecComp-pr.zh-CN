---
title: 生成搜索查询
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: e62d486b102fa035ae21b379d30bb0657b82acc9
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296215"
---
# <a name="build-search-queries"></a><span data-ttu-id="154ab-102">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="154ab-102">Build search queries</span></span>

<span data-ttu-id="154ab-103">在生成查询时, 可以使用各种关键字和条件来定义要查找的项。</span><span class="sxs-lookup"><span data-stu-id="154ab-103">In building your query, you can use various keywords and conditions to define which items to find.</span></span>

## <a name="keyword-searches"></a><span data-ttu-id="154ab-104">关键字搜索</span><span class="sxs-lookup"><span data-stu-id="154ab-104">Keyword searches</span></span>

<span data-ttu-id="154ab-p101">在 "**关键字**" 框中键入搜索查询。您可以指定关键字、邮件属性 (如发送和接收日期) 或文档属性 (如文件名) 或文档的上次更改日期。您可以使用更复杂的查询, 这些查询使用布尔运算符, 例如**AND**、 **OR**、 **NOT**和**NEAR**。您还可以在文档中搜索敏感信息 (如社会保险号), 或搜索在外部共享的文档。如果将 "关键字" 框留空, 则位于指定内容位置的所有内容都将包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="154ab-p101">Type a search query in **Keywords** box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
<span data-ttu-id="154ab-p102">或者, 也可以单击 "**显示关键字列表**" 复选框, 并在每行中键入关键字。如果这样做, 每行上的关键字都将通过逻辑运算符 ( **c:s**) 连接, 该运算符在创建的搜索查询中的**OR**运算符的功能类似。</span><span class="sxs-lookup"><span data-stu-id="154ab-p102">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
<span data-ttu-id="154ab-p103">为什么要使用关键字列表？您可以获取显示与每个关键字匹配的项目数的统计信息。这可以帮助您快速确定哪些关键字最有效 (最少)。您还可以在行中使用关键字短语 (括在括号中)。有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="154ab-p103">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [Search statistic](search-statistics.md).</span></span>

## <a name="conditions"></a><span data-ttu-id="154ab-117">条件</span><span class="sxs-lookup"><span data-stu-id="154ab-117">Conditions</span></span>
    
<span data-ttu-id="154ab-p104">您可以添加搜索条件以缩小搜索范围, 并返回一组更细化的结果。每个条件都会向搜索查询添加一个子句, 该子句在您开始搜索时创建并运行。条件以逻辑方式连接到关键字查询 (在 "关键字" 框中指定), 逻辑运算符 (**c:c**) 与**AND**运算符的功能相似。这意味着项目必须同时满足关键字查询和要包含在结果中的一个或多个条件。这就是条件如何帮助缩小结果范围的方法。有关可在搜索查询中使用的条件的列表和说明, 请参阅[内容搜索的关键字查询和搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。</span><span class="sxs-lookup"><span data-stu-id="154ab-p104">You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>


