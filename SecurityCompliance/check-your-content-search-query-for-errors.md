---
title: 检查内容搜索查询中的错误
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: 检查错误和错误，如不支持的字符的内容搜索关键字查询并运行搜索之前小写布尔运算符。如果我们发现的错误，我们将建议的修订后的查询。
ms.openlocfilehash: 6ae14edc29bb7f8bab5dd2306282a69443872633
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038285"
---
# <a name="check-your-content-search-query-for-errors"></a>检查内容搜索查询中的错误

当您创建或编辑内容的搜索时，您可以检查您的查询不支持的字符和不可能大写的布尔运算符的 Office 365。如何？只需，在内容搜索查询页上，单击**检查错误的查询**。 
  
![单击"检查错误的查询"检查您的搜索查询的不受支持的字符](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
下面是我们检查不支持的字符的列表。不支持的字符通常已被隐藏，并且他们通常会导致搜索错误或返回意外的结果。
  
- 不支持**智能引号**-智能单引号和双引号引号 （也称为弯引号）。直引号替换可搜索查询中。 
    
- **非打印和控制字符**-不可打印和控制字符不代表编写的符号，如字母数字字符。不可打印的示例和控制字符包含的文本或单独的行的文本格式的字符。 
    
- **从左到右和从右到左标记**-这些是用于指示文本方向从左到右语言 （例如英语和西班牙语） 和从右到左语言 （如阿拉伯语和希伯来语） 的控制字符。
    
- **小写布尔运算符**-如果您使用布尔运算符，例如**AND**、**或者**，而**不**在搜索查询中，它必须是大写。当我们检查错误的查询时，查询语法将通常指示，尽管可能使用小写运算符; 正在使用布尔运算符例如， `(WordA or WordB) and (WordC or WordD)`。
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a>如果查询包含不受支持的字符，则会发生什么情况？

如果在查询中找到不受支持的字符，一条警告消息显示指出不支持的字符找到的和建议的替代项。然后您然后可以选择保留原始查询或替换建议修改后的查询。下面是警告消息后单击**检查错误的查询**搜索查询的以前的屏幕截图中所显示的一个示例。请注意，原始查询包含引号和小写布尔运算符。 
  
![为查询建议修订与显示警告消息](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a>如何防止在搜索查询中不支持的字符

从其他应用程序 （如 Microsoft Word 或 Microsoft Excel） 复制的查询的部件，然后将其复制到查询页上的内容搜索关键字框时，不支持的字符是通常添加到查询。防止不受支持的字符的最佳方式是，只需键入关键字框中的查询。此外，您可以从 Word 或 Excel 复制查询，然后将其文件 Microsoft 记事本之类的纯文本编辑器中粘贴。然后将该文本文件保存，并选择**编码**下拉列表中的**ANSI** 。这将删除任何格式和不受支持的字符。然后您可以复制并粘贴关键字查询中将查询的文本文件中。 
