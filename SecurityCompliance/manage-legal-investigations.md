---
title: 管理 Office 365 中的法律调查
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: 在 Office 365 安全性中使用电子数据展示事例&amp;合规性中心管理组织的法律调查。如果您有 E5 订阅，您可以使用文本分析、 机器学习和预测编码功能的高级电子数据展示来进一步分析案例数据。
ms.openlocfilehash: 4e7b9117b3f0cb2fd6d4e70a7767f3cbe7b79724
ms.sourcegitcommit: 01813cb9bbc2400d21bc99144745af953f9356e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25719046"
---
# <a name="manage-legal-investigations-in-office-365"></a>管理 Office 365 中的法律调查

组织有响应法律案件涉及特定的执行官或您的组织中的其他员工的多个原因。这样做可能会快速查找并保留的进一步调查中电子邮件、 文档、 即时消息对话和其他内容的位置中其日常工作的任务的用户使用的特定信息。您可以通过使用 Office 365 安全性中电子数据展示案例工具执行这些组件及其他类似的多个活动&amp;合规性中心。
  
[管理法律调查与电子数据展示事例](#manage-legal-investigations-with-ediscovery-cases)
  
[分析使用 Office 365 高级电子数据展示事例数据](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**想要了解 Microsoft 如何管理其电子数据展示调查？** 下面是一种[技术白皮书](https://go.microsoft.com/fwlink/?linkid=852161)可以下载说明如何我们使用相同的 Office 365 搜索和调查工具管理我们内部电子数据展示工作流。
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>管理法律调查与电子数据展示事例

电子数据展示事例使您可以控制可以创建、 访问和管理组织中的电子数据展示事例。使用情况下添加成员和控制哪些类型的操作，他们可以执行，将内容位置置于保留与法律案件，并使用内容搜索工具来搜索位置保留可能对您的案例响应的内容。然后您还可以导出并下载进一步外部审阅者的调查这些结果。如果您的 Office 365 组织的 E5 订阅，您可以准备分析高级电子数据展示中搜索结果。
  
- [管理电子数据展示工作流](ediscovery-cases.md)创建并使用每个法律调查电子数据展示事例贵组织必须将要 
    
- 以控制哪些人可以创建和管理组织中的电子数据展示事例[分配电子数据展示权限](assign-ediscovery-permissions.md) 
    
- [设置合规性边界](set-up-compliance-boundaries.md)来控制电子数据展示管理员可以搜索用户内容位置 
    
- 您的组织中[的内容的搜索](search-for-content.md) 
    
- [准备高级电子数据展示案例内容](prepare-search-results-for-advanced-ediscovery.md)以便您可以执行分析使用高级电子数据展示的强大分析工具，如光学字符识别、 电子邮件超线程，和预测编码 
    
### <a name="use-scripts-for-advanced-scenarios"></a>高级方案中使用脚本

像上一节列出用于内容搜索方案脚本，我们已创建一些安全&amp;合规性中心 PowerShell 脚本能够帮助您管理电子数据展示事例。
  
- 您的组织中[创建电子数据展示保留报告](create-a-report-on-holds-in-ediscovery-cases.md)包含有关所有信息保留电子数据展示事例相关联 
    
- [添加邮箱和 OneDrive 位置](use-a-script-to-add-users-to-a-hold-in-ediscovery.md)的一组用户的电子数据展示保留 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>分析使用 Office 365 高级电子数据展示事例数据

Office 365 高级电子数据展示基于前面几节中所述的内容搜索和电子数据展示功能。创建电子数据展示事例后上的位置 custodian 位置，并收集数据可能响应大小写的您可以然后进一步分析数据使用的文本分析、 学习，计算机和高级的预测编码功能电子数据展示。这可以帮助您快速处理数千个电子邮件、 文档和其他类型的数据，以查找最有可能的那些项目与特定案例相关的组织。以便您可以无缝地管理安全性中相同的大小写，我们已统一案例管理和高级电子数据展示&amp;合规性中心。
  
> [!NOTE]
> 若要分析使用高级电子数据展示的用户的数据，用户 (数据的 custodian) 必须分配的 Office 365 E5 许可证。此外，可使用 Office 365 E1 或 E3 许可证的用户分配的高级电子数据展示独立许可证。管理员和合规部主管分配给情况下，并使用高级电子数据展示以分析数据不需要 E5 许可证。 
  
### <a name="get-started"></a>入门

开始使用高级电子数据展示的最快方式是创建案例并准备中安全的搜索结果&amp;合规性中心加载高级电子数据展示，在这些结果，并运行 Express 分析可分析 case 数据，然后将导出外部审阅结果。
  
- 高级电子数据展示工作流的[快速概览](quick-setup-for-advanced-ediscovery.md) 
    
- 通过创建案例高级电子数据展示中[设置用户和情况下](set-up-users-and-cases-in-advanced-ediscovery.md)，将电子数据展示权限分配和添加案例成员，所有使用安全&amp;合规性中心 
    
- [准备和负载搜索数据](prepare-data-for-advanced-ediscovery.md)中与在高级电子数据展示案例 
    
- [加载非 Office 365 数据](import-non-office-365-data-into-advanced-ediscovery.md)中为案例分析高级电子数据展示中 
    
- [使用 Express 分析](use-express-analysis-in-advanced-ediscovery.md)快速分析用例中的数据，然后方便地将导出结果 
    
### <a name="analyze-data"></a>分析数据

搜索数据加载到中高级电子数据展示案例后，您将使用分析模块启动分析它。分析过程的第一部分包含组织到组中的唯一文件，重复项的文件和近乎重复项 （又称文档相似性）。然后您将再次将数据组织为电子邮件线程和主题的分层结构组，并 （可选） 设置忽略文本筛选器，某些文本排除分析。然后您将运行分析，并查看结果。
  
- [了解有关文档相似性](understand-document-similarity-in-advanced-ediscovery.md)准备高级电子数据展示中分析数据 
    
- 为近乎重复项、 主题和电子邮件超线程，然后运行分析模块中[设置选项](set-analyze-options-in-advanced-ediscovery.md) 
    
- [设置忽略文本筛选器](set-ignore-text-in-advanced-ediscovery.md)从正在分析; 排除文本和文本字符串运行相关性分析时，这些筛选器还将忽略文本 
    
- 分析过程的[查看结果](view-analyze-results-in-advanced-ediscovery.md) 
    
- 分析过程的[高级设置的配置](set-analyze-advanced-settings-in-advanced-ediscovery.md) 
    
### <a name="set-up-relevance-training"></a>设置相关性培训

预测高级中编码 （称为的相关性） 电子数据展示可以培训上所需通过让您决定 （关于是否内容是相关或不） 的系统上的小型文档集。
  
- [了解如何设置相关性培训](manage-relevance-setup-in-advanced-ediscovery.md)，标记与案例相关的文件和定义案例问题 
    
- [定义案例问题](define-issues-and-assign-users.md)并将每个问题分配给将培训文件的用户 
    
- [添加到当前或新负载导入的文件](set-up-loads-to-add-imported-files.md)将添加到的相关性培训;负载是一批新的文件添加到用例和然后可用于相关性培训 
    
- [定义突出显示关键字](define-highlighted-keywords-and-advanced-options.md)可以添加到的相关性培训;这可以帮助您更好地标识与案例相关的文件 
    
### <a name="run-the-relevance-module"></a>运行相关性模块

后设置培训，您就可以运行相关性模块并评估此结果的相关性排名，可帮助您决定如果您需要执行其他培训，或者如果您已经准备好开始标记文件作为的培训设置的有效性与您的案例相关。
  
- [了解有关相关性过程](use-relevance-in-advanced-ediscovery.md)和评估的迭代过程，标记、 跟踪和重新培训基于示例组文件 
    
- [了解评估](assessment-in-relevance-in-advanced-ediscovery.md)，其中专家熟悉的与案例评审一案例文件并确定的相关性培训效果 
    
- [Assess 案例文件](tagging-and-assessment-in-advanced-ediscovery.md)来计算有效性 （称为*丰富*） 的培训设置，然后选择作为相关或与您的案例; 不相关的标记文件这有助于您确定当前的培训是否足够，或者是否应调整培训设置。 
    
- [执行相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)后评估已完成，，然后再次标记为用例文件作为相关或不相关到已定义的问题 
    
- [跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)过程，以确定您评估目标 （称为*稳定培训状态*） 或是否需要更多培训; 是否实现相关性培训您还可以查看每个案例问题的相关性结果 
    
- [根据相关性分析做出决定](decision-based-on-the-results-in-advanced-ediscovery.md)确定用例的结果集的大小文件的可导出供审阅 
    
- [测试相关性分析的质量](test-relevance-analysis-in-advanced-ediscovery.md)以验证挑选相关性过程中所做的决策 
    
### <a name="export-results"></a>导出结果

案例中分析数据高级电子数据展示的最后一步是导出外部审阅分析的结果。
  
- [了解如何导出案例数据](export-case-data-in-advanced-ediscovery.md)
    
- [将数据导出案例](export-results-in-advanced-ediscovery.md)
    
- [查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
    
- [导出报表字段](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>其他高级电子数据展示工具

高级电子数据展示提供其他工具和功能之外分析案例数据，相关性分析和导出数据的功能。
  
- [运行高级电子数据展示报告](run-reports-in-advanced-ediscovery.md)
    
- [定义案例和租户设置](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [高级电子数据展示实用程序](use-advanced-ediscovery-utilities.md)
