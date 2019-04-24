---
title: 运行分析功能以加快调查
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
ms.openlocfilehash: 9516035fb6c758fdff1852249fff2815f19af559
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257610"
---
# <a name="run-analytics-to-investigate-faster"></a>运行分析功能以加快调查

当证据集合很大时, 很难完全查看它们。 一组证据通常包含相同或相似的电子邮件或文档的多个副本。 数据调查 (预览版) 提供了大量分析工具, 可帮助您减少需要查看的文档量, 而不会丢失任何信息。 若要了解有关这些功能的详细信息, 请参阅:

- [近似重复检测](near-duplicates.md)

- [电子邮件会话](email-threading.md)

- [主题](themes.md)

若要分析证据集中的数据, 请执行以下操作:

1. 配置调查的分析设置。 有关详细信息, 请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。

2. 打开证据集。

3. 单击 "**管理证据**"。

4. 在 "**分析**" 下, 单击 "**分析**"。

您可以在调查中检查 "**作业**" 选项卡上的分析进度。 触发的作业类型称为 "**正在运行分析**"。

 完成分析后, 您可以在右侧面板中看到您正在查看的文档的完全相同或接近重复的列表。 若要选择您正在查看的文档的所有副本, 可以使用此面板轻松完成此操作。 若要了解有关此面板上的其他功能的详细信息, 请参阅[查看证据中的数据](review-data-in-evidence.md)。 

您还可以使用分析的输出 (如主题) 在证据中运行其他查询。 有关详细信息, 请参阅[在证据中查询数据](evidence-query.md)。

## <a name="analytics-report"></a>分析报告

若要查看证据的分析报告, 请执行以下操作:

1. 打开证据集。

2. 单击 "**管理证据**"。

3. 在 "**分析**" 下, 单击 "**查看报告**"。

此报告包含来自分析的四个组件:

- **细目**-在证据集中找到的原始电子邮件、附件和文档的数量。

- **电子邮件**-inclusives 的 eamil 邮件数、包含 minuses、包含的副本或不包含以上内容。
   - Inclusives: 电子邮件线程中的最后一封邮件, 其中包含所有以前的历史记录, 需要审阅。
   - 包含 minuses: 包含一个或多个需要审阅的不同附件的线程中的消息。
   - 包含的副本: 是另一个包含或包含的减号邮件 (主题和正文) 的副本的邮件。

- **附件**-相同证据中的不同电子邮件附件的唯一或重复的电子邮件附件数。

- **文档 (不包括电子邮件附件)** -需要审阅的独特文档数, 例如, 最接近副本集的最代表文档或另一个文档的完全相同的文档数。