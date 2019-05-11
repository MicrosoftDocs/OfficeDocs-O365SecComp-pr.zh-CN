---
title: 在高级电子数据展示中设置用于律师的智能标记-客户端权限检测
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 721426f23aec862bcefbd13b8e61415dac3aeb27
ms.sourcegitcommit: aa8ea45d5854f8906714e0a407937585ec7993ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "33951693"
---
# <a name="set-up-smart-tags-for-ml-assisted-review-in-advanced-ediscovery"></a>在高级电子数据展示中设置用于 ML 协助审阅的智能标记

高级电子数据展示中的机器学习功能旨在帮助提高文档的决策流程效率。 智能标记是将机器学习功能引入记录决策的一种方法: 标签和标记组。 创建智能标记组时, 映射到该组的 ML 模型的决策将以内嵌方式与组中的标记一起显示, 以帮助您在根据上下文中查看信息。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何设置智能标记组

1. 在审阅集中, 转到 "**管理审阅集** -> **管理标记**"。

2. 单击 "**添加标记组**" 旁边的下拉箭头, 然后选择 "**添加智能标记组**"。

3. 选择要映射到此组的模型。 这将创建一个 tag 节和 N 个子标记, 其中 N 是模型的可能输出的数目。 例如, 律师-客户端权限检测模型有两个可能的输出-特权和非特权;选择此模型将在审阅集中创建两个子标记, 每个子标记对应一个可能的输出。

4. 根据需要, 重命名标记组和标记。

## <a name="how-to-use-a-smart-tag-group"></a>如何使用智能标记组

审阅文档时, 将在相应的标记值旁边公开模型的结果。 例如, 如果您有一个用于律师-客户端权限检测的智能标记组, 并且您查看该模型已确定的文档可能是有权限的, 则您将在相应标记旁边看到原因。 请务必注意, 标记不会自动应用;出于所有意图和目的, 智能标记组中的标记的行为就像普通标记一样, 只是在适当情况下, 它们会在它们旁边公开模型结果。