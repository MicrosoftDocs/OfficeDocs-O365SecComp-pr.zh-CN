---
title: Office 365 安全性内容搜索限制&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/30/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: '了解如何在 Office 365 安全性内容的搜索功能的限制&amp;合规性中心，如同时搜索的最大数量。 '
ms.openlocfilehash: 896d1fb5aafb7ae28f00c5e19af229415d800f36
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525438"
---
# <a name="limits-for-content-search-in-the-office-365-security-amp-compliance-center"></a>Office 365 安全性内容搜索限制&amp;合规性中心

> [!NOTE]
> 本主题中的限制是不同的当前限制为 Exchange Online 中的就地电子数据展示和 SharePoint Online 中的电子数据展示中心。 
  
各种限制应用于 Office 365 安全性内容的搜索功能&amp;合规性中心。在**内容搜索**页和电子数据展示事例与关联的搜索上运行此包含搜索。这些限制帮助维护的运行状况和质量提供给 Office 365 组织的服务。也是提供与索引编制的电子邮件在 Exchange Online 的搜索相关的限制。不能修改的内容搜索或电子邮件索引限制，但是，以便您可以考虑这些限制时规划、 运行和故障排除内容搜索您应了解它们。 
  
 **目录**
  
[内容搜索限制](limits-for-content-search.md#searchlimits)
  
[索引限制电子邮件](limits-for-content-search.md#indexinglimits)
  
[详细信息](limits-for-content-search.md#moreinfo)
  
## <a name="content-search-limits"></a>内容搜索限制
<a name="searchlimits"> </a>

下表列出了安全中的搜索限制&amp;合规性中心。
  
|**限制说明**|**限制**|
|:-----|:-----|
|可以在单个内容搜索中搜索的站点邮箱的最大数量  <br/> |无限制  <br/> |
|内容搜索您的组织中同时运行的最大数量。  <br/> |无限制  <br/> |
|单个用户可以在同一时间开始的内容搜索最大数量。请注意此限制最可能命中，当用户尝试使用启动多个搜索**Get ComplianceSearch\|开始 ComplianceSearch**中安全性和合规性中心 PowerShell 命令。<br/> |10   <br/> |
|最大预览内容搜索结果时显示在预览页上的每个用户邮箱的项目数。  <br/> |100  <br/> |
|在预览内容搜索结果时显示在预览页的所有用户邮箱中找到的项的最大数目。显示最新的项目。  <br/> |1,000  <br/> |
|可以预览搜索结果的用户邮箱的最大数量。如果有超过 1000 个包含与搜索查询匹配的内容的邮箱，仅前的 1000年邮箱与大多数搜索结果将适用于预览。  <br/> |1,000  <br/> |
|预览内容搜索结果时显示在预览页上的业务网站 SharePoint 和 OneDrive 中找到的项的最大数目。显示最新的项目。  <br/> |200  <br/> |
|（在 SharePoint 和 OneDrive for Business） 的网站可以预览搜索结果的最大数量。如果有 200 个以上的总站点包含与搜索查询匹配的内容，仅与大多数搜索结果的顶部 200 网站将适用于预览。  <br/> |200  <br/> |
|最大每个公用文件夹邮箱预览内容搜索结果时显示在预览页的项目数。  <br/> |100  <br/> |
|在预览内容搜索结果时显示在预览页的所有公用文件夹邮箱中找到的项的最大数目。  <br/> |200  <br/> |
|最大公用可以预览搜索结果的邮箱数。如果有多于 500 个包含与搜索查询匹配的内容的公用文件夹邮箱，仅前的 500 公用文件夹邮箱与大多数搜索结果将适用于预览。  <br/> |500  <br/> |
|最大的内容搜索的搜索查询 （包括运算符和条件） 的字符数。  <br/> **注意：** 此限制查询已展开，这意味着将获取查询扩展针对每个关键字后生效。例如，如果搜索查询有 15 关键字和其他参数和条件，查询获取扩展 15 次，每个都与其他参数和查询的条件。因此，即使限制以下可能的搜索查询中的字符数，它是超过此限制可能会导致扩展的查询。<br/> |**邮箱：** 10,000 个  <br/> **网站：** 4000 搜索最多 20 个网站<sup>1</sup>时搜索所有网站或 2,000 个时 <br/> |
|变体时使用的前缀通配符搜索精确短语搜索查询中或使用前缀通配符和**NEAR**或**ONEAR**布尔运算符时返回的最大数量。  <br/> |10000<sup>2</sup> <br/> |
|最小前缀通配符; alpha 字符数例如， `time*`， `one*`，或`set*`。  <br/> |3   <br/> |
|通过执行操作的"搜索和清除"操作中项目的最大中内容的搜索，您可以删除的邮箱数 (使用**新建 ComplianceSearchAction-清除**命令)。如果您正在执行清除操作操作的内容搜索具有更多的源邮箱超过此限制，则清除操作将失败。有关搜索和清除的详细信息，请参阅[搜索和删除 Office 365 组织中的电子邮件](search-for-and-delete-messages-in-your-organization.md)。<br/> |50,000 个  <br/> |
   
> [!NOTE]
> <sup>1</sup>搜索时 SharePoint 和 OneDrive for Business 位置，所搜索的网站的 Url 中的字符在内针对此限制。> <sup>2</sup>对于非短语查询 （一个关键字值，该值不使用双引号内） 中，我们将使用特殊前缀索引。这会告诉我们，word 文档，但是不其中发生在文档中进行。若要执行的短语查询 （用双引号括起来的关键字值），我们需要比较单词的文档内的短语中的位置。这意味着我们不能使用短语查询的前缀索引。在这种情况下，我们内部展开前缀将扩展到; 所有可能的单词的查询例如，`"time*"`可以扩展到`"time OR timer OR times OR timex OR timeboxed OR …"`。10000 是的变量 word 可以扩展到，不与查询匹配的文档数的最大数量。非短语词没有上限。 
  
[Return to top](limits-for-content-search.md#top)
  
## <a name="indexing-limits-for-email-messages"></a>索引限制电子邮件
<a name="indexinglimits"> </a>

下表描述了可能会导致作为未编制索引的项目或部分索引的项内容的搜索结果中返回一封电子邮件的索引限制。
  
|**索引限制**|**注释**|**说明**|
|:-----|:-----|:-----|
|（不包括 Excel 文件） 的最大附件大小  <br/> |150 MB  <br/> |电子邮件附件编制索引并解析的最大大小。任何附件大于此限制不会分析索引，并包含附件的邮件将被标记为部分编制索引。<br/> > [!NOTE]> 分析是索引服务从附件提取文本、 删除不必要的字符，如标点符号和空格，然后用然后存储在索引中的文本为单词 （称为词汇切分的过程） 中的过程。           |
|Excel 文件的最大大小  <br/> |4 MB  <br/> |Excel 文件的最大大小网站上，或附加到电子邮件将索引进行分析。任何大于所不分析此限制，并将文件或电子邮件的文件附件的邮件将被标记为未编制索引的 Excel 文件。  <br/> |
|附件的最大数量  <br/> |250  <br/> |最大文件附加至将索引进行分析的电子邮件数。如果邮件超过 250 个附件前, 250 附件进行分析和索引，并将邮件标记为部分索引，因为它具有其他未解析的附件。  <br/> |
|最大附件深度  <br/> |30  <br/> |最大嵌套分析的附件数。例如，如果电子邮件具有附加到它的另一条消息，并且附加的邮件有附加的 Word 文档，Word 文档和附加的邮件将索引。最多 30 个嵌套附件将继续此行为。  <br/> |
|附加映像的最大数目  <br/> |0  <br/> |图像的附加到电子邮件跳过分析程序和编制索引。  <br/> |
|用于分析项目的最大时间  <br/> |30 秒  <br/> |最多 30 秒用来分析项目的索引。如果分析的时间超过 30 秒，项目标记为部分编制索引。  <br/> |
|最大分析器输出  <br/> |200 万个字符  <br/> |来自编制索引的分析器的文本输出的最大数量。例如，如果分析程序从文档提取 8 万个字符，只有先 2 万个字符编制索引。  <br/> |
|最大注释标记  <br/> |200 万个  <br/> |电子邮件编制索引后，每个单词将批注与指定的 word 应编制索引的不同的处理指令。每个处理指令集称为批注令牌。若要维护 Office 365 中的服务质量，没有电子邮件 2 万个注释标记的限制。  <br/> |
|在索引中的最大正文大小  <br/> |67 万个字符  <br/> |总的电子邮件及其所有附件正文中的字符数。电子邮件编制索引后，为一个字符串串联和所有附件的邮件正文中的所有文字。编制索引此字符串的最大大小为 67 万个字符。  <br/> |
|正文中的最大唯一令牌  <br/> |100 万  <br/> |如上文所述，令牌是从内容中提取文本和删除标点符号和空格，然后将其划分为存储在索引中的单词 （称为标记） 的结果。例如，短语`"cat, mouse, bird, dog, dog"`包含 5 的令牌。但这些仅 4 是唯一的标记。没有电子邮件，有助于防止索引变得太大使用随机令牌每 100 万个唯一标记的限制。<br/> |
   
[返回顶部](limits-for-content-search.md#top)
  
## <a name="more-information"></a>详细信息
<a name="moreinfo"> </a>

如导出搜索结果以及内容索引没有其他限制的内容搜索相关的其他方面。这些限制的说明，请参阅下列主题：
  
- 
    
- [处理 Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)
    
- [使用 Office 365 电子数据展示调查部分索引项](investigating-partially-indexed-items-in-ediscovery.md)
    
- [SharePoint online 搜索限制](https://support.office.com/article/7c06e9ed-98b6-4304-a900-14773a8fa32f)
    
有关内容搜索的信息，请参阅：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
    
[Return to top](limits-for-content-search.md#top)
  
