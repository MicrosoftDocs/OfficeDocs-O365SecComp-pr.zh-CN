---
title: 在高级电子数据展示中设置智能标记
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智能标记允许您在阅读高级电子数据展示事例中的内容时应用机器学习功能。 使用智能标记组来显示机器学习检测模型的结果, 如律师-客户端权限模型。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703825"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>在高级电子数据展示中设置智能标记

在审阅集中审阅案例文档时, 高级电子数据展示中的机器学习 (ML) 功能可帮助您更高效地进行决策过程。 智能标记是将 ML 功能引入记录决策的一种方法: 在审阅过程中标记文档时。 创建智能标记组时, 与智能标记组关联的 ML 模型的结果将以内嵌方式与标记组中的标记显示在一起的决策。 当你查看特定文档时, 这有助于实时查看 ML 结果信息。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何设置智能标记组

1. 在审阅集中, 单击 "**管理审阅集**", 然后单击 "**管理标记**"。

2. 单击 "**添加标记组**", 然后选择 "**添加智能标记组**"。

3. 选择要与标记组关联的 ML 模型。
    
   这将创建一个标记组和*N*个子标记, 其中*N*是模型的可能输出的数目。 例如,[律师-客户端权限检测模型](attorney-privilege-detection.md)有两个可能的输出: 

   - **肯定**–用于标记包含律师-客户端权限内容的文档。
   
   - **负**–用于标记不包含律师-客户端权限内容的文档。
    
    如果选择此模型, 则会为审阅集创建包含两个子标签的标记组 (一个名为**正数**的子标记和另一个命名的**负数**)。 在此示例中, 每个子标记对应于律师-客户端权限检测模型中的一个可能的输出。

4. (可选) 您可以重命名标记组和子标记。 例如, 您可以将**正数**标记重命名为 "**特权**", 而**否定**标记为 "**无权限**"。

## <a name="how-to-use-smart-tags"></a>如何使用智能标记

在审阅文档时, 该模型的结果将显示在相应的子标记旁边。 例如, 如果您有一个用于律师-客户端权限检测的智能标记组, 并且您查看的文档具有潜在权限, 则该结论的原因将显示在相应标记的旁边。 请务必注意, 标记不会自动应用于文档。 审阅者做出有关如何标记文档的决定。