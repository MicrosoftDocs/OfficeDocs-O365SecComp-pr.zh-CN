---
title: 近似重复检测
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
description: ''
ms.openlocfilehash: 941809193a3342d8c7b9de991370848aee4af070
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32252000"
---
# <a name="near-duplicate-detection"></a>近似重复检测

考虑要审阅的一组文档, 其中子集基于同一个模板, 大多数采用相同的样本语言, 但此处和此处有一些差异。 如果某个审阅者可以识别此子集, 请仔细查看其中一项, 并查看 rest 的不同之处, 他们不会错过任何独特的信息, 而只需要花费一小时间来阅读所有文档封面。 临近的重复检测将多个类似的文档组合在一起, 以帮助您更有效地查看您的审阅过程。

## <a name="how-does-it-work"></a>它是如何运行的？

在接近重复检测运行时, 系统会使用文本分析每个文档。 然后, 它将每个文档进行比较, 以确定它们的相似性是否大于设定的阈值。 如果是, 则将文档组合在一起。 对所有文档进行了比较和分组后, 每个组中的一个文档将标记为 "pivot";在审阅文档中, 可以先查看数据透视, 并查看相同临近重复集的其他文档, 重点介绍正在审阅的数据透视和文档之间的差异。