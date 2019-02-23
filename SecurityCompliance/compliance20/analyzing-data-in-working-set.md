---
title: 在高级电子数据展示中分析工作集中的数据 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ae024f423ac9b4ab9210ddfab519093a9fee3e42
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216792"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a>在高级电子数据展示中分析工作集中的数据 (预览)

收集的文档数较大时, 可能很难查看所有文档。高级电子数据展示 (预览版) 提供多种工具来分析文档, 以减少要查看的文档量而不丢失任何信息, 并帮助您以一致的方式组织文档。若要了解有关这些功能的详细信息, 请参阅:

- [近似重复检测](near-duplicates.md)
- [电子邮件会话](email-threading.md)
- [主题](themes.md)

若要分析工作集中的数据, 请执行以下操作:

1. 为你的事例配置分析设置。有关详细信息, 请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。
2. 打开您想要分析的工作集。
3. 转到 "管理工作集"。
4. 单击 "分析"。

您可以在您的情况中检查 "作业" 选项卡中的分析进度。

 分析完成后, 您可以查看分析报告、在工作集内运行查询输出的结果 (有关详细信息, 请参阅在[工作集中的查询](working-set-search.md)) 和查看给定文档的相关文档 (有关详细信息, 请参阅[检查工作集中的数据](reviewing-data-in-working-set.md))。

## <a name="analytics-report"></a>分析报告

若要查看工作集的分析报告, 请执行以下操作:

1. 打开您的工作集。
2. 转到 "管理工作集"。
3. 单击 "报告"。

此报告包含来自分析的四个组件:

- **细目**-工作集中发现了多少封电子邮件、附件和松散文档。

- **文档 (不包括附件)** -对多个松散文档进行透视、在数据透视的重复的情况下是唯一的, 或者是另一个文档的完全相同。

- **电子邮件**-inclusives 有多少封电子邮件, 包括副本, 包括 minuses 或以上都不是。

- **附件**-工作集中的不同电子邮件附件的电子邮件附件数是唯一的或重复的。