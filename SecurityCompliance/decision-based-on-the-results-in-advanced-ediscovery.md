---
title: 根据 Office 365 高级电子数据展示中的结果执行决策
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
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解 Office 365 高级电子数据展示中的 "确定" 选项卡如何提供可帮助您确定检查事例文件集的正确大小的数据。 '
ms.openlocfilehash: c4767e703d03ef5dbdb808332e873d22094d7bca
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216102"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>根据 Office 365 高级电子数据展示中的结果执行决策

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
 在高级电子数据展示中, "决定" 选项卡提供了其他信息, 用于查看和使用决策支持统计信息来确定审阅事例文件集的大小。 
  
## <a name="using-the-decide-tab"></a>使用 "决定" 选项卡

![相关性决定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此选项卡包含以下内容:
  
- **问题**: 在此处, 你可以从列表中选择感兴趣的问题。 
    
- **复查-撤回比率**: 根据相关性分数比较高级电子数据展示检查。图表中的截止点表示要查看的文件百分比, 映射到相关性分数。这在关联测试阶段使用, 用作用于剔除的导出阈值。默认的截止点 (要查看的文件数) 是撤回和精度之间的平衡最佳的时间点。实际的截止点应根据目标和成本权衡 (% 考评) 和风险 (% 撤回) 来确定用户。使用滑块, 可以调整截止点, 并查看图表和参数上的效果、调整要检索的相关文件的百分比以及验证决策之前的效果。
    
- **参数**: 查看、撤回、下一个相关的和总成本参数是与整个事例的集合相关的相对于评审集的累计计算统计信息。这些参数的定义如下所示:
    
    **审阅**: 根据此截止点要审阅的文件百分比。 
    
    **召回**: 审阅集中相关文件的百分比。 
    
    **下一步相关**: 查看的成本并标识当前不在审阅集中的其他相关文件。 
    
    **总成本**: 查看此百分比事例文件所需的成本。成本参数设置可由事例管理器进行设置。
    
- **按相关性分数分布**: 左侧灰度显示中的文件低于截止分数。工具提示将显示相关性分数以及相对于文件总数的审阅文件集中文件的相关百分比。
    
展开的详细信息窗格将显示其他详细信息。集合中的文件不包含空或 nebulous 文件。"系列文件" 图表示未在相关性中加载但仍作为系列一部分计数的文件。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解相关性方面的评估](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标记和评估](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[执行关联性培训](tagging-and-assessment-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

