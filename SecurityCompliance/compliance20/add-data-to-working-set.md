---
title: 将搜索结果添加到工作集
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958283"
---
# <a name="add-search-results-to-a-working-set"></a>将搜索结果添加到工作集

确定并 culled 针对 Exchange、SharePoint 和 OneDrive for business 进行搜索之后, 您可以将结果添加到工作集中。 工作集代表我们将为闪电快速搜索结果编制索引的一组静态文档, 分析电子邮件线索识别 (接近重复检测和主题)。  您还可以将非 office 365 数据源中的数据与从 office 365 中收集的数据并排添加到 live 中。

若要将数据添加到工作集, 请首先选择搜索, 然后在搜索结果中, 单击 "*将结果添加到工作集*" 按钮。

![将数据添加到工作集](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

然后, 您可以选择添加到现有工作集或新的*工作集*。  如果要添加到新的工作集, 请指定名称并最后单击 "*添加*" 按钮。

![选择工作集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

将数据添加到工作集是一个长时间运行的过程, 可以在 "作业" 选项卡或 "*搜索*" 选项卡的 "*工作集状态*" 列中跟踪进度。 此过程包括从 Office 365 收集项目并最终摄取 & 索引。  工作集处理完成后, 您可以通过单击 "*工作集*" 选项卡, 然后单击工作集导航到工作集。  然后, 您可以继续搜索、审阅、标记和导出任何相关数据。

## <a name="adding-a-sample-to-a-working-set"></a>向工作集添加示例

如果要在收集搜索检索到的所有文档之前验证搜索结果的 thorougly, 可以将搜索结果的随机样本添加到工作集, 而不是添加所有内容。

若要向工作集添加示例, 请先选择搜索, 然后在搜索结果浮出控件中, 单击 "*示例*按钮"。

然后, 您可以选择采样的参数。 有两个选项：
- 置信度级别和间隔: 将选择示例大小以满足给定的统计参数。
- 百分比: 根据搜索返回的项目数和所选参数来确定样本大小。

最后, 选择要向其中添加示例的工作集。 在这里, 您可以检查过程的状态, 就像将整个搜索添加到工作集中一样。 