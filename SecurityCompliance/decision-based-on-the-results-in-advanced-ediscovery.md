---
title: 根据 Office 365 高级电子数据展示中的结果执行决策
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解如何在 Office 365 高级电子数据展示中的 Decide 选项卡提供数据，可帮助您确定正确的审阅一套案例文件的大小。 '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525119"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a>根据 Office 365 高级电子数据展示中的结果执行决策

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
 在高级电子数据展示，Decide 选项卡提供其他信息来查看和使用决策支持统计信息用于确定案例文件的审阅集的大小。 
  
## <a name="using-the-decide-tab"></a>使用 Decide 选项卡

![相关性决定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
此选项卡包括以下组件：
  
- **问题**： 从此处，您可以选择列表中的感兴趣的问题。 
    
- **查看检索比率**： 根据相关性分数的高级比较电子数据展示审阅。图表中的截止点表示文件，若要查看，的百分比映射到的相关性分数。这用于在相关性测试阶段以及导出阈值挑选。若要查看的文件数的默认分界点位于检索和精度之间的平衡最好的点。根据目标的成本权衡 （%审阅） 和风险 （%检索次数） 的用户应确定实际的分界点。使用滑块，您可以调整分界点并调整百分比的相关文件要检索和验证决定之前时，请参阅图和参数，影响。
    
- **参数**： 查看，应该还记得下, 一步相关和总成本参数是相关的相对于整个用例集合设置的审阅累积计算的统计信息。有关这些参数的定义如下所示：
    
    **查看**： 的文件的百分比，若要查看基于此截止。 
    
    **撤回**： 查看组中的相关文件的百分比。 
    
    **下一步相关**： 若要查看并确定当前没有评审中设置的其他相关文件的成本。 
    
    **总成本**： 成本查看此案例文件的百分比。成本的参数设置可以通过案例管理器设置。
    
- **按相关性分数的通讯组**： 中向左暗灰色显示的文件如下截止分数。工具提示显示相对于文件总数设置的审阅文件中的相关性分数和相关的文件的百分比。
    
扩展的详细信息窗格中显示的其他详细信息。文件集合图表中的不包括为空或模糊文件。护理亲属文件图表表示文件的都不加载中相关性，但仍计为系列的一部分。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解评估中相关性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标签和评估](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[执行相关性培训](tagging-and-assessment-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

