---
title: 设置用于在 Office 365 高级电子数据展示中进行分析的 "忽略文本" 选项
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: '了解在使用 Office 365 高级电子数据展示中的分析和处理模块时, 如何定义要忽略特定文本的规则。  '
ms.openlocfilehash: 3a4c1d17a9a56d3018509a8dcfd6b49abb951676
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260814"
---
# <a name="set-ignore-text-option-for-analyze-in-office-365-advanced-ediscovery"></a>设置用于在 Office 365 高级电子数据展示中进行分析的 "忽略文本" 选项

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
"忽略文本" 功能可应用于以下所有高级电子数据展示模块或以下任一高级电子数据展示模块: 分析 (接近重复项、电子邮件线程、主题) 和相关性。 已忽略的文本不会出现在相关性中显示的文件中, 并且分析/计算将丢弃忽略的文本。
  
如果之前已为已运行的模块定义了 ignore text 功能, 则 "忽略文本" 设置现在将受到保护, 无法进行修改。 但是, 相关性模块的 Ignore Text 功能仍可在任何时候更改。
  
## <a name="how-ignore-text-filters-are-applied"></a>如何应用 "忽略文本" 筛选器

将按输入的顺序应用多个 "忽略文本" 筛选器。 若要更改应用顺序, 必须按所需顺序将其删除并重新输入。
  
例如, 如果文本内容是: "DAVE 小明小红 CAROL 前夕", 以下是忽略文本项和结果的示例:
  
||||
|:-----|:-----|:-----|
|**忽略文本输入** <br/> |**==\>** <br/> |**结果** <br/> |
|"小红", "BOB CAROL"  <br/> |==\>  <br/> |"DAVE 前夕"  <br/> |
|"小红", "BOB ALICE CAROL"  <br/> |==\>  <br/> |"DAVE BOB CAROL 前夕"  <br/> |
   
未实现第二个 "忽略" 文本条目, 因为在应用第一个 "忽略" 文本后, 不会找到该字符串。
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a>在定义 Ignore Text 时使用正则表达式

在定义 Ignore Text 时, 支持使用正则表达式。 以下是正则表达式语法和用法的示例:
  
- 若要删除 (忽略) 文本, 请从行尾开始:
    
     `Begin(.*)$`
    
    其中, "Begin" 是此字符串在行中的初始匹配项。
    
    例如, 对于以下文本:
    
    **这是第一句, 第一行**
    
    **这是第二个句子和第二行 "**
    
    正则表达式 first (.\*)$ 将导致:
    
    **"这是**
    
    **这是第二个句子和第二行 "**
    
- 若要删除在电子邮件线程结束时自动插入的免责声明和法律声明, 请执行以下操作:
    
     `Begin(.|\s)*End`
    
    其中, "Begin" 和 "end" 是换行文本段落的开头和结尾的唯一字符串。 
    
    例如, 以下正则表达式将删除在开始和结束字符串之间的电子邮件线程中的免责声明和法律声明:
    
    **此邮件包含机密信息 (. |\s)\*如果需要验证, 请请求硬复制版本**
    
- 若要删除免责声明 (包括特殊字符), 请执行以下操作: 
    
    例如, 对于以下文本 (在 x 的此处用免责声明表示): 
    
    **/\*\ 此邮件包含机密信息。xxxx xxxx**
    
    **xxxx xxxx xxxx xxxx xxxx xxxx**
    
    **xxxx xxxx 如果需要验证, 请请求硬复制版本。/\*\**
    
    要删除上述免责声明的正则表达式应为: 
    
    **\/\\*\\此邮件包含机密信息\.(. |\s)\*如果需要验证, 请请求硬复制版本\.\/\\*\\**
    
- 正则表达式规则:
    
  - 除空格、"_" 和 "-" 之外不属于字母表的任何字符都必须以 "\"." 开头。
    
  - 正则 eExpression 字段的长度不受限制。
    
> [!TIP]
> 有关正则表达式的说明和详细语法, 请参阅:[正则表达式语言-快速参考](https://msdn.microsoft.com/en-us/library/az24scfc%28v=vs.110%29.aspx)。 
  
## <a name="define-ignore-text-rule"></a>定义 "忽略文本" 规则

1. 在 "**管理\>分析\>分析选项**" 选项卡的 "**忽略文本**" 部分中**+** , 单击图标以添加规则。 
    
2. 在 "**添加忽略文本**" 对话框的 "**名称**" 字段中, 为 "忽略文本" 规则键入一个名称。 
    
    ![添加忽略的文本](media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. 在 "**文本**" 框中, 键入要忽略的文本。 文本字段允许不受限制的字符数。 
    
    > [!TIP]
    > 如上面的窗口中所示, 单击**灯泡**以查看 "忽略文本" 规则的通用语法准则。 
  
4. 如果需要, 选中 "**区分大小写**" 复选框。 
    
5. 在 "**应用于**" 列表中, 选择要应用定义的高级电子数据展示模块。 
    
6. 如果要对示例文本运行测试, 请在 "**输入**" 文本框中键入示例文本, 然后单击 "**测试**"。 结果将显示在 "**输出**" 文本框中。 
    
7. 单击 **"确定"** 以保存 "忽略" 文本规则。 将显示 "定义的忽略文本" 规则。 
    
    ![设置被忽略的文本名称](media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

