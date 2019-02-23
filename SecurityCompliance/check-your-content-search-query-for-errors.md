---
title: 检查内容搜索查询中是否有错误
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 在运行搜索之前, 请检查关键字查询的内容搜索是否存在错误和拼写错误 (如不受支持的字符和小写布尔运算符)。如果发现错误, 我们将建议已修改的查询。
ms.openlocfilehash: 00612116f345e2a01471d5c83df77f4bc8db9ce5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215932"
---
# <a name="check-your-content-search-query-for-errors"></a>检查内容搜索查询中是否有错误

在创建或编辑内容搜索时, 可以让 Office 365 检查您对不受支持的字符和布尔运算符 (可能不大写) 的查询。计算?只需在内容搜索的 "查询" 页上单击 "**检查查询以查找打字错误**"。 
  
![单击 "检查查询是否输入拼写" 以检查不受支持的字符的搜索查询](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
下面列出了我们检查的不受支持的字符。不受支持的字符通常是隐藏的, 它们通常会导致搜索错误或返回意外的结果。
  
- **智能引号**-不支持智能化单引号和双引号 (也称为 "弯引号")。在搜索查询中只能使用直引号。 
    
- **非打印字符和控制字符**-非打印字符和控制字符不代表写入的符号, 如字母数字字符。非打印字符和控制字符的示例包括格式文本或单独文本行的字符。 
    
- **从左到右和从右到左标记**-这些是用于指示从左到右语言 (如英语和西班牙语) 和从右到左语言 (如阿拉伯语和希伯来语) 的文字方向的控制字符。
    
- **小写布尔运算符**-如果在搜索查询中使用布尔运算符, 例如**AND**、 **OR**和**NOT** , 则它必须为大写。当我们检查输入拼写的查询时, 查询语法通常会指示是否使用了布尔运算符, 即使可能使用了小写运算符也是如此。例如, `(WordA or WordB) and (WordC or WordD)`。
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查询包含不受支持的字符, 会发生什么情况？

如果在查询中找到不受支持的字符, 则会显示一条警告消息, 指出找到了不支持的字符, 并建议了替代方法。然后, 您可以选择保留原始查询或将其替换为建议的修订后的查询。下面的示例展示了在上一屏幕截图中单击搜索查询的 "**检查查询是否录入**" 后显示的警告消息。请注意, 原始查询包含智能引号和小写布尔运算符。 
  
![将显示一条警告消息, 其中包含查询的建议修订](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何在搜索查询中阻止不受支持的字符

当您从其他应用程序 (如 microsoft Word 或 microsoft Excel) 复制查询或查询的某些部分并将其复制到内容搜索的查询页面上的关键字框中时, 通常会将不受支持的字符添加到查询中。阻止不受支持的字符的最佳方式是只在 "关键字" 框中键入查询。或者, 也可以从 Word 或 Excel 复制查询, 然后将其粘贴到纯文本编辑器 (如 Microsoft 记事本) 中的文件中。然后保存文本文件, 并在 "**编码**" 下拉列表中选择 " **ANSI** "。这将删除所有格式和不受支持的字符。然后, 可以将文本文件中的查询复制并粘贴到关键字查询框中。 
