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
ms.openlocfilehash: 119cdd9d932b6c1be847c406988efa80b8534795
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607464"
---
# <a name="building-search-queries"></a>生成搜索查询
在生成您的查询，您可以使用各种关键字和条件定义要查找的项。

## <a name="keyword-searches"></a>关键字搜索
在**关键字**框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用使用布尔运算符，例如**AND**、**或**、 ****，和**NEAR**更复杂的查询。您还可以搜索文档或搜索外部共享的文档中的敏感信息 （如社会保险号码）。如果保留关键字框为空，则将在搜索结果中包含位于指定的内容位置的所有内容。
    
或者，您可以单击**显示关键字列表**复选框，键入每行中的关键字。如果这样做，每个行的关键字进行连接的逻辑运算符 ( **c:s**) 中创建的搜索查询的**OR**运算符功能类似的。 
    
为什么使用关键字列表？您可以获取显示的项目数与每个关键字匹配的统计信息。这可以帮助您快速识别的关键字是最 （和至少） 有效。行中，您还可以使用关键字短语 （用括号括起来）。有关搜索统计信息的详细信息，请参阅[搜索统计信息](search-statistics.md)。

## <a name="conditions"></a>条件    
您可以添加搜索条件以缩小搜索范围并返回更精确的结果集。每个条件向搜索查询创建和启动搜索时运行一个子句。条件逻辑**AND**运算符功能类似的逻辑运算符 (**c:c**) 通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的一个或多个条件。这是如何帮助条件以缩小结果。列表以及您可以使用搜索查询中的条件的说明，请参阅[关键字查询及搜索内容搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)中的"搜索条件"部分。


