---
title: 搜索和标记
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525484"
---
# <a name="search-and-tagging"></a>搜索和标记

高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="search-the-documents-in-your-case"></a>在您的案例中搜索文档

一旦您已处理高级电子数据展示中的文档和 （可选） 运行分析模块或相关性模块，您可以使用搜索和添加标签搜索通过这种情况中的文档并将它们组织使用特定于案例的标记。您可以定义查询使用提供的条件卡中，或通过关键字中的类似的 KQL 查询语言条件卡片。常见的 KQL 语法，例如 AND、 OR，NOT、 NEAR(n) 且受支持，以及尾随多字符通配符 （*）。在查询语言属性名称中支持以下属性：

- caselabel： 创建/应用标记中搜索和添加标签用于用例 
- 管理员： 分配情况-受限制的管理员
- 日期： 发送电子邮件的日期、 修改日期的文档
- fileid： 文件 ID 在这种情况
- filetype： 本机文件扩展名
- fileclass： 电子邮件、 文档或附件
- senderauthor： 发件人的电子邮件，文档作者
- 大小： kb 的文件的大小
- subjecttitle： 的电子邮件，标题的文档主题
- bcc
- cc
- 参与者： 电子邮件地址的电子邮件线程，包括缺失的链接中的所有参与者
- 接收： 接收日期
- 收件人： 电子邮件收件人的名称或地址 （，抄送，密件抄送)
- sender
- lastmodifieddate： 上次修改日期的文档
- 发送： 发送的电子邮件的日期
- 至
- 作者： 作者的电子邮件
- 标题： 文档的标题
- dominanttheme： 项目的基准主题\*
- themeslist： 与项目相关联的主题\*
- readpercentile_ [issuenum]: 读取百分点值的项目问题 [issuenum]\*\*
- relevancescore_ [issuenum]: [issuenum] 问题项目的相关性分数\*\*
- relevancetag_ [issuenum]: 如果手动已项目标记为相关性，其标记 [issuenum]\*\*

\*如果已运行主题模块唯一可用\*\*唯一可用，如果已运行相关性模块
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解评估中相关性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标签和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标签和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[决定基于结果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

