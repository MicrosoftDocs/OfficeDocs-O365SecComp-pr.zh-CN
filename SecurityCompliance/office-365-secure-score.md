---
title: Office 365 安全功能分数
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/25/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9e7160f-2c34-4bd0-a548-5ddcc862eaef
description: 想知道如何安全组织真的是 Office 365 中？安全分数此处以帮助。安全分数分析基于您的正则活动和 Office 365 中的安全设置的组织的安全性，并分配分数。
ms.openlocfilehash: bc0379e40b09e63e5fded1b1a289d40c306def91
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559085"
---
# <a name="office-365-secure-score"></a>Office 365 安全功能分数

**摘要**想知道如何安全组织真的是 Office 365 中？安全分数此处以帮助。安全分数分析基于您的正则活动和 Office 365 中的安全设置的组织的安全性，并分配分数。阅读这篇文章，获取安全分数和如何使用它的概述。
  
## <a name="how-to-get-to-secure-score"></a>如何获取安全分数

如果您的组织具有订阅包含[Office 365 企业版](https://docs.microsoft.com/office365/enterprise/)、 [Microsoft 365 企业版](https://docs.microsoft.com/microsoft-365/business/)或 Office 365 企业高级版，并且您[所需的权限](#required-permissions)，则可以通过访问查看贵组织的安全分数[https://securescore.office.com](https://securescore.office.com). 

此外，您可以访问安全 & 合规性中心 ([https://protection.office.com](https://protection.office.com))，将在其中找到您当前的分数为您提供一个安全分数构件。

![安全分数小部件](media/SecureScoreWidget-o365.png)

小部件包含将向安全分数仪表板的链接。

![安全分数仪表板](media/SecureScore-WelcomeScreen.png)
  
## <a name="how-it-works"></a>如何工作

安全分数确定哪些然后您将 （如 OneDrive、 SharePoint 和 Exchange） 的 Office 365 服务比较您的设置和到由 Microsoft 建立一个比较基准的活动。您将获取的分数，具体取决于您的组织也对齐是与安全性最佳实践。您还将建议上以提高组织的分数可采取的步骤。 
  
![在 Office 365 安全分数工具的操作队列](media/SecureScore-ActionsToTake.png)
  
安全分数计算您根据您购买的服务的分数。例如，如果仅购买 Exchange Online 的计划，您不被计分 SharePoint Online 的安全功能。分数的分母，为是适用于您购买的产品的控件的所有比较基准的总数。分子是为其所有控件的已完成或部分已完成的操作，以满足该控件的总和。

展开要了解有关什么步骤，它将帮助保护，从您的威胁和多少 points 您分数会增加后遵循建议的操作。
  
![在 Office 365 安全分数工具扩展的操作](media/SecureScore-DetailedActionToTake.png)
  
若要对贵组织的安全性，请参阅您的操作的影响，选择**分数分析器**选项卡，并查看历史记录。 
  
![Office 365 安全分数工具分数分析器选项卡](media/SecureScore-ScoreAnalyzer-7days.png)
  
下面的图表中，您将看到分数和操作的列表，按类别。 
  
![图表显示所选数据点分数分析器选项卡](media/SecureScore-Analyzer-breakdownbelowchart.png)
 
您可以执行的您的组织，如 **[不对评分]** 是标记的操作，但因为它们不连接到安全分数，不对评分。  

上**分数分析器**页上，单击某一天，数据点，然后向下滚动到的已完成并不完整的操作，以找出哪些该天的更改，请参阅。分数计算每一天 (大约 1:00 PST) 一次。如果您更改了测量操作，分数将自动更新一天。计 48 小时才能反映您分数的更改。

安全分数不 express 绝对的度量单位的方式可能要获取破坏。它表示您采用可以偏移正在看见的风险的功能的范围。没有服务都无法保证，您将不违反，和安全分数不应视为以任何方式保证。
 
## <a name="how-secure-score-helps"></a>如何帮助保护分数

安全分数，有助于提高组织的安全状况 （其中许多您已购买，但可能不知道的） 的 Office 365 中使用的内置安全功能。若要了解有关这些功能可帮助您放心，您采取右步骤保护您的组织免受威胁。
  
但不只是为其相信我们所说。使用安全分数客户已看到其分数增加 5 次比客户不使用它。（及其分数增加对应于在组织中使用的安全功能）。
  
> [!NOTE]
> 安全分数不 express 绝对的度量单位的方式可能要获取破坏。它表示您采用控件可以偏移正在看见的风险的程度。没有服务都无法保证，您将不违反，和安全分数不应视为以任何方式保证。 
  
## <a name="required-permissions"></a>必需的权限

若要查看和使用安全分数仪表板，您必须为分配 Azure Active Directory 中的以下角色之一：
- 全局管理员
- 帐务管理员
- 用户管理员
- 密码管理员
- Security Administrator
- 安全读者
- Exchange 管理员
- SharePoint 管理员

 未分配管理员角色的用户将无法访问 Secure 分数。

## <a name="related-topics"></a>相关主题

[安全仪表板概述 （英文)](security-dashboard.md)

[我订阅了哪些产品？](https://docs.microsoft.com/office365/admin/admin-overview/what-subscription-do-i-have?view=o365-worldwide)