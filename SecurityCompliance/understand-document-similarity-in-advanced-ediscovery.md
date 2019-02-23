---
title: 了解 Office 365 高级电子数据展示中的文档相似性
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
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '查看 "文档相似性" 值 (两个文件的最小 resemblance 级别, 将其视为邻近的重复项) 在 Office 365 高级电子数据展示中起作用。 '
ms.openlocfilehash: eb8f07ceedb10bd0152693dd1e82a28797d86a5a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220422"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>了解 Office 365 高级电子数据展示中的文档相似性

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中, "文档相似性" 是两个文档被视为临近重复项所需的最低级别的 resemblance。
  
> [!TIP]
> 对于大多数业务应用程序, 建议使用相似性值 60%-75%。对于质量非常差的光学字符识别 (OCR) 材料, 可以应用较低的相似性值。 
  
> [!NOTE]
> 在设置和运行给定的事例后, 不能更改相似性值。 
  
在接近重复 (ND) 集内, 可能存在低于相似性阈值的 resemblance 级别的文档。对于要加入 nd 集的文档, 在 nd 集中必须至少有一个文档的 resemblance 级别超过相似性。 
  
例如, 假设相似性设置为 80%, 文档 F1 类似于 85% 级别的文档 f2, 文档 f2 类似于文档 F3 的级别为 90%。 
  
但是, 文档 F1 在仅为 70% 的级别 (低于阈值) 可能会类似于文档 F3。尽管如此, 在此示例中, 文档 F1、F2 和 F3 都显示在一对等设置中。同样, 使用相似性值 80%, 我们可能创建了两个集合, EquiSet-1 和 EquiSet。EquiSet-1 包含文档 E1 和 E2。Equiset-2 包含文档 F1、F2 和 F3。 
  
resemblance 的级别如下所示:
  
![文档相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
假定现在已插入另一个文档 X1。X1 和 E3 之间的 resemblance 为 87%。同样, X1 和 F1 之间的 resemblance 为 92%。因此, EquiSet-1、EquiSet-2 和 X1 现已组合到一个 ND 集中。
  
![文档相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 如果将任意两个文档分配给一个 nd 集, 它们将保持在相同的 nd 集中, 即使其他文档添加到了该集或者合并了这些集也是如此。 
  
合并设置后, 在将新文档添加到集合中时, 数据透视文档可能会发生变化。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

