---
title: Office 365 安全功能分数
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 您是否曾想知道贵组织在 Office 365 中的实际安全？安全得分可在这里提供帮助。安全分数根据您在 Office 365 中的常规活动和安全设置来分析组织的安全性, 并分配分数。
ms.openlocfilehash: cf272869981dd73e1ceb4bd7180cc16acaed0516
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "29992356"
---
# <a name="office-365-secure-score"></a>Office 365 安全功能分数

**摘要**您是否曾想知道贵组织在 Office 365 中的实际安全？安全得分可在这里提供帮助。安全分数根据您在 Office 365 中的常规活动和安全设置来分析组织的安全性, 并分配分数。阅读本文, 了解安全分数的概述以及如何使用它。
  
## <a name="how-to-get-to-secure-score"></a>如何获取安全分数

如果您的组织具有包含[Office 365 企业版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 商业](https://docs.microsoft.com/microsoft-365/business/)版或 Office 365 商业高级版的订阅, 并且您拥有[必要的权限](#required-permissions), 则可以通过访问来查看组织的安全分数[https://securescore.office.com](https://securescore.office.com). 

或者, 您也可以访问安全 & 合规性中心[https://protection.office.com](https://protection.office.com)(), 在这里您将找到一个可为您提供当前成绩的安全分数小部件。

![安全分数小部件](media/SecureScoreWidget-o365.png)

该小组件包含指向安全分数仪表板的链接。

![安全分数仪表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>工作原理

安全得分决定了你使用的 Office 365 服务 (如 OneDrive、SharePoint 和 Exchange), 然后将你的设置和活动与 Microsoft 建立的基线进行比较。你将根据你的组织与安全最佳做法的匹配程度获得分数。您还将获得有关可用于改进组织成绩的步骤的建议。 
  
![Office 365 安全记分工具中的操作队列](media/SecureScore-ActionsToTake.png)
  
安全分数根据您购买的服务计算分数。例如, 如果您仅购买了 Exchange online 计划, 则不会对 SharePoint online 安全功能进行评分。分数的分母是应用于所购买的产品的所有基准的所有基线的总和。分子是为其完成的或部分完成的所有控件的总和, 这些控件将满足该控制措施。

展开一个操作, 了解要执行的步骤、它将帮助保护您的威胁, 以及您在建议的情况下, 您的得分将增加多少点。
  
![Office 365 安全记分工具中的扩展操作](media/SecureScore-DetailedActionToTake.png)
  
若要查看您的操作对组织的安全性的影响, 请选择 "**分数分析器**" 选项卡并查看您的历史记录。 
  
![Office 365 安全记分工具的 "分数分析器" 选项卡](media/SecureScore-ScoreAnalyzer-7days.png)
  
在图表下方, 将按类别查看分数和操作的列表。 
  
![显示选定数据点的 "分数分析器" 选项卡上的图形](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
标记为 **[未评分]** 的操作是您可以为组织执行的操作, 但由于它们未连接到安全分数, 因此不会对其进行评分。  

在 "**分数分析器**" 页上, 单击特定天的数据点, 然后向下滚动以查看该日期的已完成和未完成的操作, 以了解已更改的内容。分数每日计算一次 (大约 1:00 AM PST)。如果对已衡量的操作进行了更改, 则分数将自动更新到下一天。最长需要48个小时才能在你的成绩中反映更改。

安全分数并不表示您可能受到破坏的可能性的绝对度量。它表示您已采用的功能, 可以抵消受到破坏的风险的程度。任何服务都不能保证您不会受到破坏, 安全得分不应以任何方式解释为保证。
 
## <a name="how-secure-score-helps"></a>安全分数如何帮助

使用安全分数, 可以通过使用 Office 365 中的内置安全功能 (许多已购买但可能不知道) 来帮助改进组织的安全状态。若要了解有关这些功能的详细信息, 可以帮助您高枕无忧, 这是为了保护组织免受威胁的正确步骤。
  
但不只是将我们的词带给它。使用安全得分的客户看到他们的得分比不使用它的客户多5倍。(其分数的增加与组织中使用的安全功能相对应。)
  
> [!NOTE]
> 安全分数并不表示您可能受到破坏的可能性的绝对度量。它表示已采用的控制措施, 可以抵消受到破坏的风险的程度。任何服务都不能保证您不会受到破坏, 安全得分不应以任何方式解释为保证。 
  
## <a name="required-permissions"></a>必需的权限

若要查看和使用安全分数仪表板, 您必须在[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)中分配以下角色之一:
- 全局管理员
- 记帐管理员
- 用户管理员
- 密码管理员
- Security Administrator
- 安全读者
- Exchange 管理员
- SharePoint 管理员

 未分配管理员角色的用户将无法访问安全分数。

## <a name="related-topics"></a>相关主题

[安全仪表板概述](security-dashboard.md)

[我订阅了哪些产品？](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)
