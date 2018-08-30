---
title: 了解 Office 365 高级电子数据展示中的文档相似性
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
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '查看 Office 365 高级电子数据展示中的文档相似性值，最少的两个文件被视为近乎重复的类似级别工作原理。 '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525234"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a>了解 Office 365 高级电子数据展示中的文档相似性

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示，文档相似性是类似的所需的两个文档都视为近乎重复项的最低级别。
  
> [!TIP]
> 对于大多数业务应用程序，建议使用相似性值的 60%-75%。对于很差的质量光学字符识别 (OCR) 材料可以应用较低的相似性值。 
  
> [!NOTE]
> 它已设置并运行给定情况后，无法更改的相似性值。 
  
集中 Near 副本 （和），可能有文档类似低于相似性阈值级别。加入和组中，为文档中必须有至少一个文档具有类似超出相似性级别设置和。 
  
例如，假定相似性设置为 80%，文档 F1 类似于文档 F2 85%的级别，文档 F2 类似于文档 F3 90%的级别。 
  
但是，文档 F1 可能类似于文档 F3 仅 70%，低于的阈值级别。不过，此示例中，在文档 F1、 F2 和 F3 所有显示在一个和设置。同样，使用相似性值的 80%，我们可能已创建两组，EquiSet 1 和 EquiSet 2。EquiSet 1 包含文档 E1 和 E2。Equiset 2 包含文档 F1、 F2 和 F3。 
  
级别的类似如下所示：
  
![文档相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
假定另一个文档，X1，则现在插入。X1 和 E3 之间类似是 87%。同样，之间 X1 和 F1 类似是 92%。因此，EquiSet-1、-2，EquiSet 和 X1 现在合并到一个和设置。
  
![文档相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> 如果任何两个文档或分配给和一，它们仍保留在一起在和一组相同，即使其他文档添加到集中如果合并集。 
  
设置将合并后，新文档添加到一组时，可以更改数据透视表文档。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

