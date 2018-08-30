---
title: 了解 Office 365 高级电子数据展示中的相关性评估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: '获取评估阶段和其角色在 Office 365 高级电子数据展示中的相关性培训过程中确定问题的丰富功能的概述。  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525414"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>了解 Office 365 高级电子数据展示中的相关性评估

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
高级电子数据展示启用早期评估，例如，定义的问题和用例导入的数据。高级电子数据展示使专家做出决策与采用方法并将它们应用于文档审阅项目。
  
## <a name="understanding-assessment"></a>了解评估

在评估，专家审阅随机的一组至少 500 文件，用于以确定问题的丰富功能以及生成反映培训结果的统计信息。如果发现足够相关文件要达到统计有助于高级电子数据展示提供准确的统计信息并有效地确定培训进程中的稳定性点的相关性的评估成功。 
  
更高的统计信息，稳定性算法的有效性，更准确评估集中文件相关的次数。评估文件中的相关文件数取决于问题的丰富功能。丰富是中一组相关问题的相关文件的估计的百分比。更丰富的问题将使用较低的丰富比问题更快地达到更多的相关文件。极低丰富的问题 (例如，2%或更少) 需要设置访问大量相关文件的非常大评估。
  
统计信息，在跟踪和 Decide 选项卡培训期间和之后批次计算显示，包括不同的审阅设置的记忆功能的估计值。基于样本的估计设置 （在本例中为评估文件） 统计信息中包含的误差范围和该错误边距的可信度。例如，80%的估计的撤回可能必须为 95%可信度错误加或减 5%的边距。这意味着，估计的检索是实际 75%-85%具有此估计 95%可信度。越大评估集的误差范围成为较小且更准确统计信息。 
  
专家审阅初始评估套 500 文件后，相关性就可以确定当前检索值的错误的边距。相关性还将设置其所建议的用于访问以优化评估一组的错误的默认边距。以下是一些示例：
  
- 如果已设置评估生成错误加或减 10%的边距，将建议相关性将上移动到 （需要没有其他评估审阅） 的培训。 
    
- 如果评估一组由生成错误加或减 13%的边距，相关性可能建议评估文件到达较小的边距的另一组概述。 
    
- 如果极低丰富，相关性可能建议停止评估，即使的误差范围是大型 （使不切实际统计信息），因为评估一组需要访问错误的有用边距太大。
    
每个问题自己丰富、 当前边距的错误，并且结果是，估计其他评估文件数。评估接下来创建根据 （最多 1,000 个在一组) 的文件的最大数。
  
您可以接受的相关性建议或根据需要调整错误的当前边距。错误的默认当前边距由检索次数等于或高于 75%。
  
> [!NOTE]
> 评估阶段可以绕过，在**相关性\>跟踪**扩展问题，清除**评估**复选框，每个问题，然后为"所有问题"视图中的选项卡。但是，结果是，将会出现此问题没有统计信息。> 评估执行之前可以仅完成清除**评估**复选框。仅当每个问题清除该复选框案例中存在多个问题，绕过评估 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[标签和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标签和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[决定基于结果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

