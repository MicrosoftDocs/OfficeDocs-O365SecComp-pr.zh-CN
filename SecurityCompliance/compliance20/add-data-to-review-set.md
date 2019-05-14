---
title: 将搜索结果添加到审阅集
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
ms.openlocfilehash: fc32836026d1a2c449e73a28eafc2f5a631a1705
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527124"
---
# <a name="add-search-results-to-a-review-set"></a>将搜索结果添加到审阅集

当您对搜索结果感到满意并准备好查看和分析这些搜索结果时, 您可以将其添加到审阅集 (在案例中)。 将原始数据复制到评审集还可为您提供高级分析工具, 如主题检测、接近重复检测和电子邮件线程标识, 从而促进评审和分析过程。 您还可以将非 Office 365 数据源中的数据添加到检查集, 以便除了从 Office 365 收集的数据之外, 还可以查看数据。

将搜索结果添加到审阅集时 (检查集位于事例的**审查集**选项卡上) 时, 将发生以下两种情况:

- 搜索结果中的所有项目都将从 live Office 365 服务中的原始数据源复制, 并复制到 Microsoft 云中的安全 Azure 存储位置。

- 将对所有项目 (包括内容和元数据) 进行重新编制索引, 以便审核集中的所有数据在对事例数据的审阅期间完全可搜索。 当您在案例调查过程中搜索评审集中的数据时, 对数据进行重新编制索引会导致完全且快速的搜索。

若要将数据添加到审阅集, 请单击 "**搜索**" 选项卡上的搜索, 然后单击浮出控件页面上的 "**添加结果以查看检查设置**"。

![向评审集添加数据](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

请注意, 您可以添加到现有的审阅集, 也可以创建新的审阅集。  如果添加到新的审阅集, 请指定名称, 然后单击 "**添加**"。

![选择评审集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

向评审集添加数据是一个长期运行的过程。 此过程包括从 Office 365 中的原始数据源 (例如, 从邮箱和网站) 中收集项目, 将它们复制到 Azure 存储位置 (此复制过程也称为 "*摄取*"), 然后对项目重新编制索引。 您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。 完成审阅集处理后, 单击该事例中的 "**查看集**" 选项卡, 然后单击 "检查设置" 以启动进程筛选、查看、标记和导出审阅集中的数据。

## <a name="add-a-sample-to-a-review-set"></a>向评审集添加示例

如果要在将所有搜索结果添加到审阅集之前更全面地验证搜索结果, 您可以将搜索结果的示例添加到审阅集, 而不是添加所有内容。

若要向审阅集添加示例, 请单击 "**搜索**" 选项卡上的搜索, 然后单击浮出控件页面上的 "**示例**"。 在 "**采样参数**" 页上, 选择下列选项之一:

- **可信度百分比**和**可信度间隔百分比**-添加到审阅集的项目将由您设置的统计参数决定。 如果您通常在采样结果时使用置信度和间隔, 请在下拉框中进行指定。 否则, 只需使用默认设置即可。

- **随机样本百分比**-添加到审阅集的项目基于由搜索返回的总项目数的指定百分比的随机选择。

选择并配置上述选项之一后, 选择一个现有的审阅集以将示例添加到, 然后单击 "**发送**"。 同样, 您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。