---
title: 创建查询以查找存储在站点上的敏感数据
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3019fbc5-7f15-4972-8d0e-dc182dc7f836
description: 与数据丢失防护 (DLP) SharePoint Online 中，可以发现文档包含在您的租户整个敏感数据。后发现文档，您可以使用文档所有者，以保护数据。本主题可帮助您表单查询搜索敏感数据。
ms.openlocfilehash: 13954a856dd265e3b735d940c7d334d922713637
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013856"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>创建查询以查找存储在站点上的敏感数据

用户通常存储敏感数据，如信用卡号，社会保险号码，或个人，在其网站，然后随着时间的推移这可以公开使组织面临巨大的数据丢失的风险。存储在网站上的文档，包括 OneDrive for Business 站点 — 无法共享与组织外部的人员不应具有对信息的访问权。与数据丢失防护 (DLP) SharePoint Online 中，可以发现文档包含在您的租户整个敏感数据。后发现文档，您可以使用文档所有者，以保护数据。本主题可帮助您表单查询搜索敏感数据。
  
> [!NOTE]
> 电子发现或电子数据展示和 DLP 是需要[SharePoint Online 计划 2](https://go.microsoft.com/fwlink/?LinkId=510080)的高级功能。 
  
## <a name="forming-a-basic-dlp-query"></a>创建一个基本的 DLP 查询

有三个部分构成的基本 DLP 查询： SensitiveType，count 范围和可信度范围。下图中，所示**SensitiveType:"\<类型\>"** 是必需的并且两个**|\<计数范围\>** 和**|\<可信度范围\>** 是可选的。 
  
![示例查询分为必需和可选两种](media/DLP-query-example-text.png)
  
### <a name="sensitive-type---required"></a>敏感类型 - 必填

因此，每个部件是什么？SharePoint DLP 查询通常开头属性`SensitiveType:"`和信息类型从[敏感信息类型库存](https://go.microsoft.com/fwlink/?LinkID=509999)，命名并结尾`"`。您还可以使用您的组织创建[自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。例如，您可能寻找包含信用卡号的文档。在这种情况下，您将使用以下格式： `SensitiveType:"Credit Card Number"`。由于没有包括计数范围或可信度区域，查询将返回信用卡号检测到的每个文档。这是最简单查询，您可以运行，并且返回大多数的结果。请记住的拼写和间距敏感类型重要的。 
  
### <a name="ranges---optional"></a>范围 - 选填

两个后续两个部件让我们快速检查范围如下所示的范围。在 SharePoint DLP 查询中，基本范围都由两个数字分隔的两个时间段，如下所示： `[number]..[number]`。例如，如果`10..20`是使用，该范围将捕获 10%到 20 的号码。有许多不同的范围组合，并在本主题中介绍的多个。 
  
我们将计数范围添加到查询。可以使用 count 范围定义的文档需要包含之前它包含在查询结果中的敏感信息的次数。例如，如果您希望您的查询返回包含完全五个信用卡号的文档，使用此： `SensitiveType:"Credit Card Number|5"`。计数范围还有助于您确定带来的风险的高度的文档。例如，您的组织可以考虑五台或更多信用卡号文档高风险。若要查找纸此条件的文档，您需要使用此查询： `SensitiveType:"Credit Card Number|5.."`。或者，您可以找到与第五个文档或更少使用此查询信用卡卡号： `SensitiveType:"Credit Card Number|..5"`。 
  
#### <a name="confidence-range"></a>置信区间

最后，可信度范围是可信的检测到的敏感类型是实际的匹配程度。可信度范围的值同样工作来计算区域。您可以不包括计数范围表单查询。例如，若要搜索的任意数量的信用卡号的文档 — 只要可信度范围是 85%或更高版本 — 将使用此查询： `SensitiveType:"Credit Card Number|*|85.."`。 
  
> [!IMPORTANT]
> 星号 ( `*`) 表示任何值的工作原理是通配符。您可以使用通配符 ( `*`) 是计数范围中或可信度范围，而不是在敏感的类型。 
  
### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>电子数据展示中心可用的其他查询属性和搜索运算符

在 SharePoint 中的 DLP 还引入了 LastSensitiveContentScan 属性，可帮助您搜索特定时间段内扫描的文件。有关与查询示例`LastSensitiveContentScan`属性，请参阅下一节中的[复杂查询的示例](form-a-query-to-find-sensitive-data-stored-on-sites.md#BKMK_ExamplesOfComplexQueries)。 
  
您可以将不仅 DLP 特定属性，以创建查询，而且还标准 SharePoint 电子数据展示搜索属性使用如`Author`或`FileExtension`。运算符可用于构建复杂的查询。可用的属性和运算符的列表，请参阅[使用搜索属性和使用电子数据展示的运算符](https://go.microsoft.com/fwlink/?LinkId=510093)博客文章。 
  
## <a name="examples-of-complex-queries"></a>示例

下面的示例使用不同的敏感类型、 属性和运算符来说明如何可以优化您的查询，以查找完全正在查找的内容。
  
|**查询**|**说明**|
|:-----|:-----|
| `SensitiveType:"International Banking Account Number (IBAN)"` <br/> |名称可能听起来有所不同，因为它很长时间，但它是敏感类型的正确名称。请确保使用从[敏感信息类型库存](https://go.microsoft.com/fwlink/?LinkID=509999)的确切名称。您还可以使用您的组织创建[自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)的名称。<br/> |
| SensitiveType:"信用卡号|1..4294967295|1..100"' <br/> |这将返回与至少一个匹配的文档为敏感类型"信用卡号"。每个区域的值是各自的最小和最大值。编写此查询的简单方法是`SensitiveType:"Credit Card Number"`，但其中是为了娱乐中的？<br/> |
| SensitiveType:"信用卡号| 5..25"和 LastSensitiveContentScan:"8/11/2018..8/13/2018"' <br/> |这将返回从 2018 年 8 月 11，通过 2018 年 8 月 13，5-25 信用卡号已扫描的文档。  <br/> |
| SensitiveType:"信用卡号| 5..25"和 LastSensitiveContentScan:"8/11/2018..8/13/2018"不 FileExtension:XLSX <br/> |这将返回从 2018 年 8 月 11，通过 2018 年 8 月 13，5-25 信用卡号已扫描的文档。带 XLSX 扩展名的文件不包含在查询结果中。 `FileExtension`是一个可以包括在查询中的许多属性。有关详细信息，请参阅[使用搜索属性和使用电子数据展示的运算符](https://go.microsoft.com/fwlink/?LinkId=510093)。<br/> |
| `SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"` <br/> |这将返回包含信用卡号或社会保障号的文档。  <br/> |
   
## <a name="examples-of-queries-to-avoid"></a>示例

并非所有查询都创建相等。下表提供了不使用 DLP SharePoint 中的查询的示例，并介绍原因。
  
|**不支持的查询**|**原因**|
|:-----|:-----|
| SensitiveType:"信用卡号|.."` <br/> |必须至少添加一个数值。  <br/> |
| `SensitiveType:"NotARule"` <br/> |"NotARule"不是有效的敏感类型名称。仅名称[敏感信息类型库存](https://go.microsoft.com/fwlink/?LinkID=509999)工作 DLP 查询中。<br/> |
| SensitiveType:"信用卡号|0"' <br/> |为最小值或范围中的最大值，零无效。  <br/> |
| `SensitiveType:"Credit Card Number"` <br/> |很可能很难查看，但没有额外的空白区域之间"Credit"和"卡片"使查询无效。使用从[敏感信息类型库存](https://go.microsoft.com/fwlink/?LinkID=509999)精确敏感的类型名称。<br/> |
| SensitiveType:"信用卡号|1.。 3"' <br/> |不应由空格分隔的两个时间段部分。  <br/> |
| SensitiveType:"信用卡号| |1.|80..."' <br/> |有太多管道分隔符 （|).而是遵循以下格式: SensitiveType:"信用卡号|1.|80..."' <br/> |
| SensitiveType:"信用卡号|1.|80..101"' <br/> |因为可信度值代表百分比，他们不能超过 100。而是介于 1 至 100 选择一个号码。  <br/> |
   
## <a name="for-more-information"></a>详细信息

[查找存储在 SharePoint Online 网站中的敏感数据](https://support.office.com/article/ef788d8f-9748-4025-bfe4-40541ca4cfb2)
  
[敏感信息类型库存](https://go.microsoft.com/fwlink/?LinkID=509999)
  
[运行 Office 365 安全性内容的搜索&amp;合规性中心](run-a-content-search-in-the-security-and-compliance-center.md)
  
[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
  

