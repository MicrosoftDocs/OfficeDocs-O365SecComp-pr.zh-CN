---
title: 将数据从一个评审集添加到另一个评审集
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
description: ''
ms.openlocfilehash: 9dc75717ac0a57c8ccb38b1e01ec2fcb9c5737ab
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151964"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>从另一个评审集向评审集添加数据

在某些情况下, 可能需要从一次审阅集中 carve 文档的一部分, 并在另一个审阅集中单独使用它们。  如果您已在审阅集中 culled 内容并希望对数据子集运行分析, 这将非常有用。

请遵循本文中的工作流, 将内容从一个审阅集添加到另一个评审集。

## <a name="before-you-begin"></a>开始之前

在开始之前, 您需要创建新的审阅集以将数据添加到。  可以在案例的 "**审阅集**" 选项卡上添加新的审阅集。 有关详细信息, 请参阅[创建审阅集](managing-review-sets.md#create-a-review-set)。

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>步骤 1: 确定要添加到另一评审集的内容

您可以通过选择源评审集或 b seleting 中的特定文档, 将内容从一个评审集添加到另一个评审集。  如果要添加选定项, 请选择相应项, 单击 "**操作**", 然后单击 "**添加到另一个评审集**"。

![添加到另一评审集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>步骤 2: 指定用于添加到另一评审集的选项

在 "**添加到另一张审阅集选项**" 飞出页面中, 选择要将项目添加到的审阅集。 选择是否添加**所有搜索结果**或**选定的项目**。  其他信息提供选项以包括项目中的所有元数据, 以及在将文档添加到新评审集时是否将标记 (通过选中 "**标签**" 复选框) 包括在源评审集中。  

![添加到另一评审集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

单击 **"确定"** 后, 将创建一个新作业 (名为 "**将数据添加到另一个审阅集**"), 以将内容添加到另一个审阅集。  您可以转到 "**作业**" 选项卡并监视此作业的进度。 有关详细信息, 请参阅[管理作业](managing-jobs-ediscovery20.md)。
