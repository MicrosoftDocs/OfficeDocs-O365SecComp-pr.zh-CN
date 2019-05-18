---
title: 在高级电子数据展示中设置律师-客户端特权检测
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
description: ''
ms.openlocfilehash: ee5f2257e73467c50a0ecc296d8d3b70b7c3d0f8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155184"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a>在高级电子数据展示中设置律师-客户端特权检测 (预览)

任何发现过程的审阅部分的主要和昂贵的方面是查看特权内容。 高级电子数据展示在您的案例中提供了一种基于 AI 的特权内容检测, 以便您可以更高效地执行此过程。 由于此功能目前在 beta 中, 因此电子数据展示管理员必须选择使用该功能。

## <a name="how-does-it-work"></a>它是如何运行的？

启用此功能后, 当您在一种情况下分析评审集时, 所有文档都通过律师-客户端权限检测模型运行。 模型看上去有两个问题:

- 内容: ML 模型确定文档内容在本质上是合法的可能性。

- 参与者: 如果存在租户的用户上传的律师列表, 模型会将文档的参与者与列表进行比较, 以确定文档是否至少有一个律师参与者。
模型输出每个文档的三个值, 所有这些值都可在审阅集中进行搜索:

- 内容分数: 文档本质上是法律的可能性 (0 到1之间的分数)

- 拥有律师: 如果在上传的律师列表中找到了一个参与者, 则为 True, 否则为 false, 或者没有律师列表。

-  可能的特权: 如果内容得分高于阈值或有律师参与者, 则为 True, 否则为 false。

## <a name="opting-into-attorney-client-privilege-detection"></a>选择加入律师-客户端特权检测

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a>步骤 1: 自愿加入律师-客户端权限检测 (电子数据展示管理)

由于律师-客户端特权检测是预览功能, 因此, 您的电子数据展示管理员需要选择让该功能在你的案例中可用。

- 转到高级电子数据展示页面中的 "配置实验功能"

- 单击 "管理律师-客户端特权检测"。

- 单击切换以打开该功能。

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>步骤 2: 上传律师列表 (可选)

为了充分利用律师-客户端特权检测, 我们建议提供公司工作的电子邮件地址 (律师) 列表或法律角色。 此列表应为不带标题的 CSV, 每行包含一个电子邮件地址。

## <a name="leveraging-attorney-client-privilege-detection"></a>利用律师-客户端特权检测 

### <a name="step-1-analyze-a-review-set"></a>步骤 1: 分析审阅集

分析您的审查集时, 也将运行律师-客户端权限检测。 若要了解有关分析评审集中的数据的详细信息, 请参阅[在高级电子数据展示中分析评审集中的数据](analyzing-data-in-review-set.md)。

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>步骤 2: 创建具有律师-客户端权限检测模型的智能标记组

您可以通过使用智能标记组, 在审查过程中使用律师-客户端权限检测的结果之一主要方法之一。 智能标记组采用 ML 模型的结果, 并在标记旁显示模型的结果, 以便您可以轻松地使用模型的结果 (如果相关), 并在您的审阅过程中使用标记, 就像您在 "标记" 面板中进行任何其他标记一样。 有关详细信息, 请参阅[在高级电子数据展示中设置用于 ML 辅助查看的智能标记](smart-tags.md)。

- 在 "管理标记" 中, 单击 "添加智能标记部分"。

- 选择 "律师-客户端特权检测"。 你将看到, 已创建与模型的可能结果对应的标记组和两个标记。

- 根据您的审阅情况, 重命名标签组和标签。

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a>步骤 3: 使用智能标记组进行权限审阅

查看文档时, 如果模型已确定文档具有潜在权限, 则相应的智能标记将公开结果:

- 如果文档的内容本身可能是合法的, 则会在相应的智能标记旁边显示 "法律内容" 标签。

- 如果文档具有在上载的律师列表中找到的参与者, 则 "律师" 标签将显示在相应的智能标记旁边。