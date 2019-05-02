---
title: 在高级电子数据展示中分析评审集中的数据
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
ms.openlocfilehash: c765234e1aa0738415f66f90b66ebce0fcab2505
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527108"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>在高级电子数据展示中分析评审集中的数据

收集的文档数较大时, 可能很难查看所有文档。 高级电子数据展示提供了大量工具来分析文档, 以减少要查看的文档量而不丢失任何信息, 并帮助您以一致的方式组织文档。 若要了解有关这些功能的详细信息, 请参阅:

- [近似重复检测](near-duplicates.md)

- [电子邮件会话](email-threading.md)

- [主题](themes.md)

若要分析审阅集中的数据, 请执行以下操作:

1. 为你的事例配置分析设置。 有关详细信息, 请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。

2. 打开要分析的审阅集。

3. 单击 "**管理审阅集**"。

4. 单击 "**分析**"。

可以在案例的 "**作业**" 选项卡上检查分析进度。

 完成分析后, 您可以查看分析报告, 在审核的输出集内运行查询 (请参阅[评审集内的查询](review-set-search.md)), 并查看给定文档的相关文档 (请参阅查看[评审数据集中的数据](reviewing-data-in-review-set.md))。

## <a name="analytics-report"></a>分析报告

查看审阅集的分析报告:

1. 打开评审集。

2. 单击 "**管理审阅集**"。

3. 单击 "**报告**"。

此报告包含来自分析的四个组件:

- **细目**-在审阅集中发现了多少封电子邮件、附件和松散文档。

- **文档 (不包括附件)** -对多个松散文档进行透视、在数据透视的重复的情况下是唯一的, 或者是另一个文档的完全相同。

- **电子**邮件-有多少封电子邮件是 inclusives、包含的副本、包含的 minuses 或以上都不是。

- **附件**-审阅集中另一个电子邮件附件的电子邮件附件数是唯一的或重复的。