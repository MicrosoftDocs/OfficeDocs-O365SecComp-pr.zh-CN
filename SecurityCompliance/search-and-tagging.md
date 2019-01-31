---
title: 搜索和标记
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。
ms.openlocfilehash: 013e559ca55e9a877dfb2f8747c4696f81e1e095
ms.sourcegitcommit: 25f1028643d8a20d17306e8b09cafea46eaf7a58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2019
ms.locfileid: "29666142"
---
# <a name="search-and-tagging"></a>搜索和标记

高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。搜索和标签的简要演示，请参阅[管理您的数据与高级电子数据展示](https://www.youtube.com/watch?v=VaPYL3DHP6I)视频。

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>在您的案例中搜索文档

在处理文档中的高级电子数据展示案例 （并 （可选） 运行分析或相关性模块之后），您可以使用搜索和标签可搜索文档，然后将其组织通过应用特定于案例的标记 （也称为标签）。您可以定义搜索查询使用提供的条件卡或中包含关键字使用类似的 KQL 查询语言条件卡片。常见的 KQL 语法，例如 AND、 OR，NOT、 NEAR(n) 且受支持，以及尾随多字符通配符 （*）。 

下表列出了您可以搜索使用 KQL 关键字查询的属性。此外，您可以使用高级电子数据展示搜索工具中的条件卡片搜索查询添加条件 （针对所选属性）。

|**属性**|**说明**|
|:-----|:-----|
|**caselabel** <br/> | 创建/应用时标记文档的标记的名称。 <br/> |
|**custodian** <br/> | 在与文档; 关联 custodian受到限制。 <br/> |
|**日期** <br/> | 发送电子邮件; 日期网站文档修改的日期。 <br/> |
|**fileid** <br/> | 在这种情况文件 ID。 <br/> |
|**文件类型** <br/> | 本机文件扩展名。 <br/> |
|**fileclass** <br/> | 电子邮件、 文档或附件。 <br/> |
|**senderauthor** <br/> | 发件人的电子邮件;网站文档的作者。 <br/> |
|**大小** <br/> | Kb 文件的大小。 <br/> |
|**subjecttitle** <br/> | 电子邮件; 的主题网站文档标题。 <br/> |
|**bcc** <br/> | 电子邮件的密件抄送字段中。 <br/> |
|**cc** <br/> | 电子邮件的抄送字段中。 <br/> |
|**参与者** <br/> | 在电子邮件线程，包括缺失的链接中的所有参与者的电子邮件地址。 <br/> |
|**接收** <br/> | 接收电子邮件的日期。 <br/> |
|**收件人** <br/> | 收件人的电子邮件，包括在收件人、 抄送或密件抄送字段。 <br/> |
|**sender** <br/> | 发件人的电子邮件。 <br/> |
|**lastmodifieddate** <br/> | 上次修改日期网站文档。 <br/> |
|**发送** <br/> | 发送电子邮件的日期。 <br/> |
|**自** <br/> | 收件人的电子邮件收件人字段中列出。 <br/> |
|**作者** <br/> | 网站文档的作者。 <br/> |
|**title** <br/> | 网站文档的标题。 <br/> |
|**dominanttheme**\* <br/> | 项目基准主题。 <br/> |
|**themeslist**\* <br/> | 与项目相关联的主题。 <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | 由 [issuenum] 定义问题的项目，读取百分点值。 <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | 由 [issuenum] 定义问题的项目相关性分数。 <br/> |
|**relevancetag_ [tagname]**\*\* <br/> | 如果项目具有已手动标记相关性，由 [tagname] 定义的标记。 <br/> |
|||

\*如果已运行主题模块仅可用。

\*\*如果已运行相关性模块仅可用。

或者，可以使用的条件卡片高级电子数据展示搜索工具中添加到搜索查询的条件 （针对所选属性）。下面的屏幕快照显示了可以添加到查询的条件。**组**列指示属性是否适用于电子邮件、 网站文档，或同时 （由*公共*的值）。此列同时也会指出后运行相关性模块提供的可搜索属性。

![在高级电子数据展示搜索工具中的搜索条件](media/AeDSearchConditions.png)

有关可搜索的属性的详细信息，请参阅[关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解评估中相关性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标签和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标签和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[决定基于结果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

