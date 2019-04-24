---
title: 在 Office 365 中管理法律调查
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 使用 Office 365 中安全 & 合规中心中的电子数据展示案例来管理您的组织的法律调查。 如果你拥有 E5 订阅, 则可以使用高级电子数据展示的文本分析、机器学习和预测编码功能进一步分析事例数据。
ms.openlocfilehash: 5bfa4719f2bb065a7064e7dc9d02778a4d032da8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252090"
---
# <a name="manage-legal-investigations-in-office-365"></a>在 Office 365 中管理法律调查

组织有许多理由来响应与组织中的特定执行官或其他员工有关的法律案件。 这可能包括快速查找和保留电子邮件、文档、即时消息对话以及人员在日常工作任务中使用的其他内容位置中的详细调查特定信息。 您可以使用 Security & 合规性中心中的电子数据展示案例工具执行这些和许多其他类似活动。
  
[使用电子数据展示事例管理法律调查](#manage-legal-investigations-with-ediscovery-cases)
  
[使用 Office 365 高级电子数据展示分析事例数据](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**想要了解 Microsoft 如何管理其电子数据展示调查？** 下面是可下载的[技术白皮书](https://go.microsoft.com/fwlink/?linkid=852161), 可说明我们如何使用相同的 Office 365 搜索和调查工具来管理我们的内部电子数据展示工作流。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>使用电子数据展示事例管理法律调查

通过电子数据展示事例, 可以控制哪些用户可以在组织中创建、访问和管理电子数据展示事例。 用例可添加成员并控制他们可以执行的操作类型, 在与法律案件相关的内容位置放置保留, 并使用内容搜索工具在保留状态中搜索可能对你的案例做出响应的内容。 然后, 您还可以导出和下载这些结果, 以供外部审阅者进一步调查。 如果您的 Office 365 组织拥有 E5 订阅, 您还可以在高级电子数据展示中准备搜索结果以供分析。
  
- 通过为组织必须执行的每个法律调查创建和使用电子数据展示事例来[管理您的电子数据展示工作流](ediscovery-cases.md) 
    
- [分配电子数据展示权限](assign-ediscovery-permissions.md)以控制可以在组织中创建和管理电子数据展示事例的用户 
    
- [设置合规性边界](set-up-compliance-boundaries.md)以控制电子数据展示管理器可搜索的用户内容位置 
    
- [搜索组织中的内容](search-for-content.md) 
    
- [为高级电子数据展示准备事例内容](prepare-search-results-for-advanced-ediscovery.md), 以便您可以使用高级电子数据展示功能强大的分析工具 (例如光学字符识别、电子邮件线程和预测编码) 执行分析 
    
### <a name="use-scripts-for-advanced-scenarios"></a>将脚本用于高级方案

与列出的内容搜索方案脚本的前一节一样, 我们还创建了一些安全 & 合规性中心 PowerShell 脚本, 以帮助您管理电子数据展示事例。
  
- [创建一个电子数据展示保留报告](create-a-report-on-holds-in-ediscovery-cases.md), 其中包含有关与组织中的电子数据展示事例相关的所有保留的信息 
    
- 将用户列表的[邮箱和 OneDrive 位置添加](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)到电子数据展示保留 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>使用 Office 365 高级电子数据展示分析事例数据

Office 365 高级电子数据展示构建在上一节中介绍的内容搜索和电子数据展示功能。 创建电子数据展示事例后, 将保管人位置置于保留状态, 并收集可能响应的数据, 然后可以使用文本分析、机器学习和高级的预测编码功能进一步分析数据发现. 这可帮助您的组织快速处理数以千计的电子邮件、文档和其他类型的数据, 以查找最可能与特定事例相关的那些项目。 而且, 我们有统一的案例管理和高级电子数据展示, 以便您可以在安全 & 合规性中心内无缝地管理相同事例。
  
> [!NOTE]
> 若要使用高级电子数据展示分析用户的数据, 必须为用户 (数据管理员) 分配 Office 365 E5 许可证。 或者, 可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。 分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。 
  
### <a name="get-started"></a>入门

开始使用高级电子数据展示的最快方法是在安全 & 合规中心中创建一个事例并准备搜索结果, 在高级电子数据展示中加载这些结果, 然后运行快速分析以分析该事例数据, 然后将结果导出用于外部审阅。
  
- 获取高级电子数据展示工作流的[快速概述](quick-setup-for-advanced-ediscovery.md) 
    
- 通过创建案例、分配电子数据展示权限和添加事例成员来设置高级电子数据展示的[用户和案例](set-up-users-and-cases-in-advanced-ediscovery.md), 所有方法都使用安全 & 合规性中心 
    
- 在高级电子数据展示中为事例[准备和加载搜索数据](prepare-data-for-advanced-ediscovery.md) 
    
- 将[非 Office 365 数据加载](import-non-office-365-data-into-advanced-ediscovery.md)到事例中, 以在高级电子数据展示中对其进行分析 
    
- [使用快速分析](use-express-analysis-in-advanced-ediscovery.md)在案例中快速分析数据, 然后轻松导出结果 
    
### <a name="analyze-data"></a>分析数据

在高级电子数据展示中, 将搜索数据加载到事例中之后, 您将使用分析模块开始对其进行分析。 分析过程的第一部分包括将文件组织成一组唯一的文件、重复项和临近的重复项 (也称为 "文档相似性")。 然后, 将数据再次组织成分层的电子邮件线程和主题组, 并根据需要设置 "忽略文本" 筛选器, 以从分析中排除某些文本。 然后, 运行分析并查看结果。
  
- 了解用于准备在高级电子数据展示中分析数据的[文档相似性](understand-document-similarity-in-advanced-ediscovery.md) 
    
- 设置临近的重复、主题和电子邮件线程[的选项](set-analyze-options-in-advanced-ediscovery.md), 然后运行分析模块 
    
- [设置 "忽略文本" 筛选器](set-ignore-text-in-advanced-ediscovery.md)以排除分析文本和文本字符串;当您运行相关性分析时, 这些筛选器也将忽略文本 
    
- [查看](view-analyze-results-in-advanced-ediscovery.md)分析过程的结果 
    
- 配置分析过程的[高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
### <a name="set-up-relevance-training"></a>设置相关性培训

高级电子数据展示中的预测编码 (称为相关性) 使您能够通过在一小组文档中做出决定 (有关是否相关或不相关) 来培训系统。
  
- [了解如何设置相关性培训](manage-relevance-setup-in-advanced-ediscovery.md)、标记与案例相关的文件, 以及定义案例问题 
    
- [定义案例问题](define-issues-and-assign-users.md)并将每个问题分配给将对文件进行训练的用户 
    
- 将[导入的文件添加到](set-up-loads-to-add-imported-files.md)将添加到相关性培训中的当前或新加载;负载是添加到事例中并用于相关性培训的一批新文件。 
    
- 定义可添加到相关性培训中的[突出显示的关键字](define-highlighted-keywords-and-advanced-options.md);这有助于更好地识别与事例相关的文件 
    
### <a name="run-the-relevance-module"></a>运行相关性模块

设置培训后, 您就可以运行相关性模块并评估相关培训设置的有效性, 这会导致相关性排名, 帮助您决定是否需要执行其他培训, 或者是否准备好开始将文件标记为与你的案例相关。
  
- 了解基于文件示例集的相关评估、标记、跟踪和重新培训的[相关性过程](use-relevance-in-advanced-ediscovery.md)和迭代过程 
    
- [了解评估](assessment-in-relevance-in-advanced-ediscovery.md), 即熟悉案例的专家将查看一组事例文件, 并确定相关性培训的有效性 
    
- [评估事例文件](tagging-and-assessment-in-advanced-ediscovery.md)以计算培训设置的有效性 (称为*丰富*程度), 然后将文件标记为与您的事例相关或不相关。这可帮助您确定当前培训是否足够, 或者是否应调整培训设置。 
    
- 完成评估后[执行相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md), 然后再次将文件标记为与您为事例定义的问题相关或不相关 
    
- [跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)流程, 以确定相关性培训是否已实现评估目标 (称为 "*稳定培训状态*"), 或者是否需要更多培训;您还可以查看每个案例问题的相关性结果 
    
- [根据相关性分析做出决策](decision-based-on-the-results-in-advanced-ediscovery.md), 以确定可导出以供审阅的结果事例文件集的大小 
    
- [测试相关性分析的质量](test-relevance-analysis-in-advanced-ediscovery.md), 以验证在相关性过程中做出的挑选决定 
    
### <a name="export-results"></a>导出结果

在高级电子数据展示中分析事例数据的最后一步是导出分析结果以供外部审阅。
  
- [了解如何导出事例数据](export-case-data-in-advanced-ediscovery.md)
    
- [导出事例数据](export-results-in-advanced-ediscovery.md)
    
- [查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
    
- [导出报告字段](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>其他高级电子数据展示工具

高级电子数据展示不仅提供了分析事例数据、相关性分析和导出数据之外的其他工具和功能。
  
- [运行高级电子数据展示报告](run-reports-in-advanced-ediscovery.md)
    
- [定义大小写和租户设置](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高级电子数据展示实用程序](use-advanced-ediscovery-utilities.md)
