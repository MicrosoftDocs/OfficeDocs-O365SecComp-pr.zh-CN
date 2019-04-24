---
title: 了解 Office 365 高级电子数据展示中的相关性评估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 获取评估阶段及其在 Office 365 高级电子数据展示中的相关性培训期间确定问题丰富程度的角色的概述。
ms.openlocfilehash: 1ddaa7ef37f762d7b63bb6c0c51193ff382b8d6b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250199"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a>了解 Office 365 高级电子数据展示中的相关性评估

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
高级电子数据展示支持早期评估, 例如, 针对定义的问题和为事例导入的数据。 高级电子数据展示使专家能够做出与采用方法相关的决策, 并将它们应用于文档审阅项目。
  
## <a name="understanding-assessment"></a>了解评估

在评估中, 专家将检查至少500文件的随机集, 这些文件用于确定问题的丰富程度并生成反映培训结果的统计信息。 当找到足够的相关文件以达到统计级别时, 将会成功进行评估, 从而帮助高级电子数据展示相关性以提供准确的统计信息, 并在培训过程中有效地确定稳定化点。 
  
评估集中相关文件的数量越高, 统计信息和稳定性算法的有效性就越准确。 评估文件中相关文件的数量取决于问题的丰富程度。 丰富程度是与问题相关的集合中的相关文件的预计百分比。 较大丰富的问题比较低丰富的问题更快地获得更多的相关文件。 非常低的丰富程度的问题 (例如, 2% 或更低) 将需要非常大的评估设置, 以达到大量相关文件。
  
"跟踪" 和 "决定批次计算后" 选项卡中显示的统计信息包括针对不同审查集的召回估计。 在 "统计信息" 中, 基于示例集的估计 (在此示例中为 "评估文件") 包括错误的边距和该误差边距的置信度级别。 例如, 估计撤回百分比为 80% 时, 其置信度为 95% 的值可能为正负 5%。 这意味着估计撤回实际为 75%-85%, 并且此估计的置信度为 95%。 评估集越大, 错误的发生幅度变小, 并且统计信息更准确。 
  
在专家查看了500个文件的初始评估集后, 相关性能够确定召回值的误差的当前边距。 相关性还将设置为优化评估集而建议达到的默认误差。 以下是一些示例:
  
- 如果评估设置已产生了大于或减 10% 的误差, 则相关性将建议继续进行培训 (不需要进行其他评估审查)。 
    
- 如果评估设置已产生的误差为加上或减 13%, 相关性可能建议对另一组评估文件进行审阅, 以达到较小的利润率。 
    
- 如果丰富程度极低, 相关性可能建议停止评估, 即使错误的发生幅度很大 (使统计数据不切实际) 也是如此, 因为所需的评估设置过大的误差幅度太大。
    
每个问题都有其自己的丰富程度、当前误差范围, 并产生估计的额外评估文件数。 根据最大文件数 (一组中最多为 1000) 创建下一个评估集。
  
您可以接受相关性建议, 也可以根据需要调整当前误差。 在等于或高于 75% 时, 将确定默认的错误当前边距。
  
> [!NOTE]
> 通过清除每个问题的 "**评估**" 复选框, 然后针对 "所有问题", 可以绕过评估阶段的展开视图的 "**相关性\>跟踪**" 选项卡中的该问题。 但因此, 此问题不会提供任何统计信息。 > 清除 "**评估**" 复选框只能在执行评估之前完成。 在案例中存在多个问题的情况下, 仅当针对每个问题清除该复选框时, 才会跳过评估 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[标记和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标记和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[根据结果做出决定](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)

