---
title: 搜索和标记
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 在高级电子数据展示中, 搜索和标记模块使您能够在您的案例中搜索、预览和组织文档。 目前, 此模块在 beta 版中。
ms.openlocfilehash: b3e660e6dca014323cfd06f10c14747751aeb386
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158534"
---
# <a name="search-and-tagging"></a>搜索和标记

在高级电子数据展示中, 搜索和标记模块使您能够在您的案例中搜索、预览和组织文档。 目前, 此模块在 beta 版中。 有关搜索和标记的简短演示, 请参阅[使用高级电子数据展示视频管理数据](https://www.youtube.com/watch?v=VaPYL3DHP6I)。

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>在你的案例中搜索文档

在高级电子数据展示案例中处理文档 (并根据需要运行分析或相关性模块) 后, 您可以使用搜索和标记来搜索文档, 然后通过应用大小写特定的标记 (也称为 "标签") 来组织这些文档。 您可以使用提供的条件卡或使用关键字条件卡中类似 KQL 的查询语言来定义搜索查询。 常用 KQL 语法, 如 AND、OR、NOT 和 NEAR (n), 以及尾部多字符通配符 (*)。 

下表列出了您可以使用 KQL 关键字查询搜索的属性。 或者, 您可以使用高级电子数据展示搜索工具中的条件卡将条件 (对于选定的属性) 添加到搜索查询中。

|**属性**|**说明**|
|:-----|:-----|
|**caselabel** <br/> | 标记文档时创建/应用的标记的名称。 <br/> |
|**保管人** <br/> | 与文档关联的保管人;受限制。 <br/> |
|**date** <br/> | 电子邮件的发送日期;网站文档的修改日期。 <br/> |
|**fileid** <br/> | 事例中的文件 ID。 <br/> |
|**类型** <br/> | 本机文件扩展名。 <br/> |
|**fileclass** <br/> | 电子邮件、文档或附件。 <br/> |
|**senderauthor** <br/> | 电子邮件的发件人;网站文档的作者。 <br/> |
|**size** <br/> | 文件大小 (以 KB 为单位)。 <br/> |
|**subjecttitle** <br/> | 电子邮件的主题;网站文档的标题。 <br/> |
|**bcc** <br/> | 电子邮件的 "密件抄送" 字段。 <br/> |
|**cc** <br/> | 电子邮件的 "抄送" 字段。 <br/> |
|**participants** <br/> | 电子邮件线索中所有参与者的电子邮件地址, 包括缺少的链接。 <br/> |
|**received** <br/> | 接收电子邮件的日期。 <br/> |
|**recipients** <br/> | 电子邮件的收件人, 包括在 "收件人"、"抄送" 或 "密件抄送" 字段中。 <br/> |
|**sender** <br/> | 电子邮件的发件人。 <br/> |
|**lastmodifieddate** <br/> | 网站文档的上次修改日期。 <br/> |
|**sent** <br/> | 电子邮件的发送日期。 <br/> |
|**to** <br/> | 在电子邮件的 "收件人" 字段中列出的收件人。 <br/> |
|**编写** <br/> | 网站文档的作者。 <br/> |
|**title** <br/> | 网站文档的标题。 <br/> |
|**dominanttheme**\* <br/> | 项目的主要主题。 <br/> |
|**themeslist**\* <br/> | 与项目相关联的主题。 <br/> |
|**readpercentile_[issuenum]**\*\* <br/> | 项目的已读百分点值, 针对 [issuenum] 定义的问题。 <br/> |
|**relevancescore_[issuenum]**\*\* <br/> | 项目的相关性分数, 针对 [issuenum] 定义的问题。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 如果已手动为项目标记相关性, 则由 [tagname] 定义的标记。 <br/> |
|||

\*仅当主题模块已运行时才可用。

\*\*仅在已运行相关性模块时可用。

或者, 您可以使用高级电子数据展示搜索工具中的条件卡向搜索查询添加条件 (对于选定的属性)。 下面的屏幕截图显示了可以添加到查询中的条件。 "**组**" 列指示属性是应用于电子邮件、网站文档还是两者 (由*常见*值表示)。 此列还标识了在运行相关性模块后可用的可搜索属性。

![高级电子数据展示搜索工具中的搜索条件](media/AeDSearchConditions.png)

有关可搜索属性的详细信息, 请参阅[关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解相关性方面的评估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标记和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根据结果做出决定](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

