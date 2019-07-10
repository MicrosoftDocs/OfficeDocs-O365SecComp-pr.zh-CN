---
title: 创建查询以查找存储在站点上的敏感数据
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 使用 SharePoint Online 中的数据丢失防护 (DLP), 您可以发现在整个租户中包含敏感数据的文档。 在发现文档之后, 可以使用文档所有者来保护数据。 本主题可帮助您形成查询以搜索敏感数据。
ms.openlocfilehash: a200cbd802922a694510e82bb8d394fed6bb2a32
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599318"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>创建查询以查找存储在站点上的敏感数据

用户通常会将敏感数据 (如信用卡号、社会保险号码或个人) 存储在其网站上, 并且随着时间的推移, 这会使组织面临数据丢失的重大风险。 网站上存储的文档 (包括 OneDrive for Business 网站) 可以与组织外部的人员共享, 而不能访问该信息。 使用 SharePoint Online 中的数据丢失防护 (DLP), 您可以发现在整个租户中包含敏感数据的文档。 在发现文档之后, 可以使用文档所有者来保护数据。 本主题可帮助您形成查询以搜索敏感数据。
  
> [!NOTE]
> 电子发现、电子数据展示和 DLP 是需要[SharePoint Online 计划 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高级功能。 
  
## <a name="forming-a-basic-dlp-query"></a>创建一个基本的 DLP 查询

基本的 DLP 查询包括三个部分：SensitiveType、计数范围和置信区间。 如下图所示, **SensitiveType: "\<\>type"** 是必需的, 并且**|\<计数范围\> **和**|\<可信度范围\> **都是可选的。 
  
![示例查询分为必需和可选两种](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感类型 - 必填

那么，每个部分分别是什么？ SharePoint DLP 查询通常以属性`SensitiveType:"`和信息类型名称从[敏感信息类型的清单](https://go.microsoft.com/fwlink/?LinkID=509999)中开始, 并以进行结尾。 `"` 您还可以使用为您的组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。 例如，您可能正在寻找包含信用卡号的文档。 在这种情况下, 您可以使用以下格式: `SensitiveType:"Credit Card Number"` 由于未包含计数范围或置信度范围, 因此查询将返回检测到信用卡号的每个文档。 这是您可以运行的最简单的查询，并会返回最多的结果。 请记住，敏感类型问题的拼写和空格很重要。 
  
### <a name="ranges---optional"></a>范围 - 选填

接下来的两个部分都是范围, 因此让我们快速检查区域的外观。 在 SharePoint DLP 查询中, 基本范围由两个用两个句点隔开的数字表示, 如下所示`[number]..[number]`:。 例如, 如果`10..20`使用, 则该范围将捕获10到20之间的数字。 有许多不同的范围组合，本主题将阐释其中的几个。 
  
让我们将一个计数范围添加到查询中。 您可以使用计数范围定义文档在包含在查询结果中之前需要包含的敏感信息的发生次数。 例如, 如果您希望查询仅返回正好包含五个信用卡号的文档, 请使用以下命令: `SensitiveType:"Credit Card Number|5"`。 计数范围还可以帮助您辨别存在高风险的文档。 例如，您的组织可能认为含有五个或更多信用卡号的文档存在高风险。 若要查找符合此条件的文档, 请使用以下查询`SensitiveType:"Credit Card Number|5.."`: 或者, 您可以使用以下查询查找具有5个或更少信用卡号码的文档`SensitiveType:"Credit Card Number|..5"`:。 
  
#### <a name="confidence-range"></a>置信区间

最后，置信区间是指已检测到敏感类型实际匹配的置信水平。 置信区间的值与计数范围使用的原理相似。 您可以创建一个不包括计数范围的查询。 例如, 若要搜索具有任意数量信用卡号的文档, 只要可信度范围为 85% 或更高, 就可以使用此查询: `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星号 ( `*`) 是一个代表任何值有效的通配符。 可以在计数区域或置信区间`*`(而不是敏感类型) 中使用通配符 ()。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>电子数据展示中心可用的其他查询属性和搜索运算符

SharePoint 中的 DLP 还引入了 LastSensitiveContentScan 属性, 此属性可帮助您搜索在特定时间范围内扫描的文件。 有关`LastSensitiveContentScan`属性的查询示例, 请参阅下一节中的[复杂查询示例](#examples-of-complex-queries)。 
  
您不仅可以使用特定于 DLP 的属性来创建查询, 还可以使用标准的 SharePoint 电子数据展示搜索`Author`属性`FileExtension`(如或)。 您可以使用运算符来构建复杂的查询。 有关可用属性和运算符的列表, 请参阅[Using Search properties And operators With eDiscovery](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。 
  
## <a name="examples-of-complex-queries"></a>示例

下面的示例使用不同的敏感类型、属性和运算符来说明如何优化查询以准确查找您要查找的内容。
  
|**Query**|**说明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |该名称可能看起来很奇怪, 因为它很长, 但它是该敏感类型的正确名称。 请务必使用[敏感信息类型清单](https://go.microsoft.com/fwlink/?LinkID=509999)中的确切名称。 您还可以使用为您的组织创建的[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。  <br/> |
| `SensitiveType:"Credit Card Number|1..4294967295|1..100"` <br/> |这将返回至少有一个与敏感类型 "信用卡号码" 匹配的文档。 每个范围的值分别是最小值和最大值。 编写此查询的更简单的方法`SensitiveType:"Credit Card Number"`是, 但其中有什么有趣之处？  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"` <br/> |这将返回5-25 年8月11日至8月13日 (2018) 从8月 11 2018 日扫描的包含信用卡号的文档。  <br/> |
| `SensitiveType:"Credit Card Number| 5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX` <br/> |这将返回5-25 年8月11日至8月13日 (2018) 从8月 11 2018 日扫描的包含信用卡号的文档。 具有 .XLSX 扩展名的文件不包含在查询结果中。  `FileExtension`是可以包含在查询中的多个属性之一。 有关详细信息, 请参阅将[搜索属性和运算符与电子数据展示结合使用](https://go.microsoft.com/fwlink/?LinkId=510093)。  <br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |这将返回包含信用卡号或社会保障号的文档。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>示例

并非所有查询都一样。 下表提供了在 SharePoint 中不能使用 DLP 的查询示例并介绍了原因。
  
|**不支持的查询**|**原因**|
|:-----|:-----|
| `SensitiveType:"Credit Card Number|.."` <br/> |必须至少添加一个数值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule" 不是有效的敏感类型名称。 仅在 DLP 查询中的[敏感信息类型](https://go.microsoft.com/fwlink/?LinkID=509999)中的名称可供使用。  <br/> |
| `SensitiveType:"Credit Card Number|0"` <br/> |0不是有效的范围中的最小值或最大值。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |可能很难看到, 但在 "信用卡" 和 "卡片" 之间有额外的空白, 这会导致查询无效。 从[敏感信息类型的清单](https://go.microsoft.com/fwlink/?LinkID=509999)中使用精确敏感类型名称。  <br/> |
| `SensitiveType:"Credit Card Number|1. .3"` <br/> |两个句点部分不应由空格分隔。  <br/> |
| `SensitiveType:"Credit Card Number| |1..|80.."` <br/> |管道分隔符过多 (|). 请改为遵循以下格式:`SensitiveType: "Credit Card Number|1..|80.."` <br/> |
| `SensitiveType:"Credit Card Number|1..|80..101"` <br/> |因为可信度值表示百分比, 所以它们不能超过100。 请选择 1 至 100 之间的数值。  <br/> |
   
## <a name="for-more-information"></a>有关详细信息

[敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)
  
[在 Office 365 安全&amp;合规中心中运行内容搜索](run-a-content-search-in-the-security-and-compliance-center.md)
  
[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
  

