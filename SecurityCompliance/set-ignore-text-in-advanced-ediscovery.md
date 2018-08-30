---
title: 在 Office 365 高级电子数据展示中为分析设置“忽略文本”选项
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解如何定义要使用 Office 365 高级电子数据展示中的分析和过程模块时忽略特定文本的规则。  '
ms.openlocfilehash: eb7e7052979087b7dba98aac3b0c9ab75ec0d02a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525447"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中为分析设置“忽略文本”选项

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
忽略文本功能可以应用于所有或任何以下高级电子数据展示模块： 分析 （重复附近，电子邮件线程主题） 和相关性。忽略的文本不会出现在文件中相关性，显示和分析/计算将放弃忽略的文本。
  
如果忽略文本功能之前已经运行的模块的定义忽略文本设置将现在受保护不被修改。但是，仍可以随时更改相关性模块的忽略文本功能。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何应用忽略文本筛选器

多个忽略文本筛选器中的输入顺序应用。若要更改所应用的顺序，它们必须删除并重新输入所需的顺序。
  
例如，如果文本内容:"DAVE BOB 刘爱琳 CAROL 前夕"，下面是示例忽略文本条目和的结果：
  
||||
|:-----|:-----|:-----|
|**忽略文本条目** <br/> |**==\>** <br/> |**结果** <br/> |
|"刘爱琳""BOB 康"  <br/> |==\>  <br/> |"DAVE 前夕"  <br/> |
|"刘爱琳"，"BOB 刘爱琳 CAROL"  <br/> |==\>  <br/> |"DAVE BOB CAROL 前夕"  <br/> |
   
由于字符串找不到此类应用第一个忽略文本后未实现的第二个忽略文本项。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>在定义忽略文本时使用正则表达式

定义忽略文本时使用支持正则表达式。正则表达式语法和用法的示例如下：
  
- 若要删除 （忽略） 从开始到结束的行的文本：
    
     `Begin(.*)$`
    
    "开始"所在的行中的此字符串的初始匹配项。
    
    例如，对于以下文本：
    
    **"This is 第一句和第一行**
    
    **这是第二个句子和第二行"**
    
    正则表达式 first(.\*)$ 将导致：
    
    **"This is**
    
    **这是第二个句子和第二行"**
    
- 若要删除免责声明和自动插入到电子邮件线程的末尾的法律语句：
    
     `Begin(.|\s)*End`
    
    其中"开始"和"结束"是唯一的字符串的开头和换行的文本段落的末尾。 
    
    例如，下面的正则表达式将删除免责声明和 Begin 和 End 字符串之间的电子邮件主题中的法律语句：
    
    **此消息包含机密信息 (。 |\s)\*如果需要验证，则请请求书面版本**
    
- 若要删除免责声明 （包括特殊字符）： 
    
    例如，对于 （带免责声明此处由 x） 的以下文本： 
    
    **/\*\ 此邮件包含机密信息。格式格式**
    
    **格式格式格式格式格式格式格式**
    
    **格式格式如果验证是必需的请请求书面版本。/\*\**
    
    应删除上述免责声明的正则表达式： 
    
    **\/\\*\\此消息包含机密信息\.(。 |\s)\*如果需要验证，则请请求书面版本\.\/\\*\\**
    
- 正则表达式规则：
    
  - 不属于除空格，"_"字母任何字符和"-"前面必须有"\"。
    
  - 正则 eExpression 字段可以是无限的长度。
    
> [!TIP]
> 说明和正则表达式的详细的语法，请参阅：[正则表达式语言-快速参考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定义忽略文本规则

1. 在**管理\>分析\>分析选项**选项卡上**忽略文字**部分中，单击**+** 添加规则的图标。 
    
2. 在**添加忽略文本**对话框中，在**名称**字段中，键入忽略文本规则的名称。 
    
    ![添加忽略的文本](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 在**文本**框中，键入要忽略的文本。文本字段允许任意的数量的字符。 
    
    > [!TIP]
    > 如下所示在上面的窗口中，单击**灯泡**以查看忽略文本规则的通用语法指南。 
  
4. 如果需要，请选择**区分大小写**复选框。 
    
5. 在**应用于**列表中，选择要应用的定义中的高级电子数据展示模块。 
    
6. 如果您希望示例文本上运行测试，在**输入**文本框中键入示例文本，然后单击**测试**。结果将显示在**输出**文本框中。 
    
7. 单击**确定**以保存忽略文本规则。显示定义的忽略文本规则。 
    
    ![设置被忽略的文本名称](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

