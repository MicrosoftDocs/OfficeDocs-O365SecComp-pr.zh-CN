---
title: 安全仪表板概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: 使用新的安全仪表板查看 Office 365 的威胁防护状态, 查看安全警报并对其采取操作。
ms.openlocfilehash: 78e6a67ace757cca9d25086c601ab4b4437c7bf8
ms.sourcegitcommit: 5a93c2f3df35d06a59a7fbaff5c91f7afde11781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857662"
---
# <a name="security-dashboard"></a>安全仪表板

## <a name="overview"></a>概述

[安全&amp;合规性中心](go-to-the-securitycompliance-center.md)使您的组织能够管理数据保护和合规性。 如果您具有必要的权限, 安全仪表板将使您能够查看威胁保护状态, 并查看安全警报并对其采取措施。 
  
观看视频以获取概述, 然后阅读本文以了解详细信息。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
根据组织的 Office 365 订阅包括的内容, 安全仪表板包含多个小部件, 如威胁管理摘要、威胁保护状态、全局的每周威胁检测、恶意软件等, 如中所述。以下各节。
  
若要查看安全仪表板, 请在 " [Office &amp; 365 安全合规中心](go-to-the-securitycompliance-center.md)" 中, 转到 "**威胁管理** \> **仪表板**"。
  
> [!NOTE]
> 您必须是 Office 365 全局管理员、安全管理员或安全读者才能查看安全仪表板。 某些小部件需要其他权限才能查看。 若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="threat-management-summary"></a>威胁管理摘要

威胁管理摘要小部件告诉你组织在过去七天 (7) 天内抵御威胁的方式。

![安全仪表板-威胁管理摘要小部件](media/SecDash-ThreatMgmtSummary.png)

您在威胁管理摘要中看到的信息取决于订阅所包含的内容。 下表介绍了 Office 365 E3 和 Office 365 E5 包含的信息。


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|阻止的恶意软件邮件<br/>阻止的仿冒邮件<br>用户报告的邮件<br><br><br><br> |阻止的恶意软件邮件<br>阻止的仿冒邮件<br>用户报告的邮件<br>已阻止零天恶意软件<br>检测到高级网络钓鱼邮件<br>阻止的恶意 Url |

若要查看或访问 "威胁管理摘要" 小部件, 您必须具有查看高级威胁防护报告的权限。 若要了解详细信息, 请参阅[查看 ATP 报告所需的权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="threat-protection-status"></a>威胁保护状态

威胁防护状态构件显示了威胁防护的有效性, 并提供了有关网络钓鱼和恶意软件的趋势分析和详细视图。 

![威胁防护状态小部件](media/tpswidget.png)

详细信息取决于 Office 365 订阅是否包含具有或不包含[office 365 高级威胁防护](office-365-atp.md)(ATP) 的[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP)。


|如果你的订阅包括 .。。 |你将看到这些详细信息 |
|---------|---------|
|EOP, 而不是 Office 365 ATP     |EOP 检测到并阻止的恶意电子邮件<br> 请参阅[威胁防护状态报告 (EOP)](view-email-security-reports.md#threat-protection-status-report)。| |
|Office 365 ATP |EOP 和 Office 365 ATP 检测到并阻止了恶意内容和恶意电子邮件<br>由反恶意软件引擎、[零小时自动清除](zero-hour-auto-purge.md)和 atp 功能 (包括[安全链接](atp-safe-links.md)、[安全附件](atp-safe-attachments.md)和[atp 反网络钓鱼](atp-anti-phishing.md)) 阻止的包含恶意内容的独特电子邮件的聚合计数。<br>请参阅[威胁防护状态报告 (ATP)](view-reports-for-atp.md#threat-protection-status-report)。 | 

若要查看或访问威胁防护状态小部件, 您必须具有查看高级威胁防护报告的权限。 若要了解详细信息, 请参阅[查看 ATP 报告所需的权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="global-weekly-threat-detections"></a>全球每周威胁检测
 
"全球每周威胁检测" 小部件显示在过去七 (7) 天的电子邮件中检测到的威胁数。

![全球每周威胁检测小组件](media/globalweeklythreatdetections.png)

指标的计算如下表所述:

|多重  |如何计算  |
|---------|---------|
|扫描的邮件 |扫描的电子邮件数乘以收件人数 |
|威胁已停止  |被标识为包含恶意软件的电子邮件数乘以收件人数 |
|由[ATP](office-365-atp.md)阻止 |由 ATP 阻止的电子邮件数乘以收件人数 |
|传递后删除 |由[零小时自动清除](zero-hour-auto-purge.md)删除的邮件数乘以收件人数 |

## <a name="malware"></a>恶意软件

恶意软件小组件显示过去七 (7) 天的恶意软件趋势和恶意软件系列类型的详细信息。

![恶意软件趋势和系列类型](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>见解

不只是 Insights 应查看的表面密钥问题, 它们还包括建议和要考虑的操作。 

![智能见解](media/smartinsights.png)

例如, 您可能会看到网络钓鱼电子邮件被传递, 因为某些用户禁用了其 "垃圾邮件" 选项。 若要详细了解见解的工作方式, 请参阅[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)。
  
## <a name="threat-investigation-and-response"></a>威胁调查和响应

如果贵组织的订阅包括[Office 365 高级威胁防护计划 2](office-365-ti.md), 则安全仪表板包含一个包含高级威胁调查和响应工具的部分。 您的组织的安全团队可以使用本节中的信息来了解新兴的市场活动、调查威胁和管理事件。 
  
![威胁智能可帮助您了解组织的目标攻击](media/threatintelwidget.png)
  
  
## <a name="trends"></a>趋势

靠近安全仪表板底部的是 "**趋势**" 部分, 它汇总了贵组织的电子邮件流趋势。 报告提供有关分类为垃圾邮件、恶意软件、网络钓鱼尝试和优质电子邮件的电子邮件的信息。 单击平铺可在报告中查看更详细的信息。 
  
![趋势部分汇总了组织的电子邮件流趋势](media/trends.png)
  
如果组织的 Office 365 订阅包括[office 365 高级威胁防护计划 2](office-365-ti.md), 您还将在此部分中添加一个**最近的威胁管理警报**报告, 使安全团队能够查看并对其执行操作高优先级的安全警报。 

若要查看或访问已发送和已接收的电子邮件小组件, 您必须具有查看高级威胁防护报告的权限。 若要了解详细信息, 请参阅[查看 ATP 报告所需的权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

若要查看或访问最新的威胁管理警报小部件, 您必须具有查看警报的权限。 若要了解详细信息, 请参阅[查看警报所需的 RBAC 权限](alert-policies.md#rbac-permissions-required-to-view-alerts)。
  
## <a name="related-topics"></a>相关主题

[查看安全&amp;合规性中心中的电子邮件安全报告](view-email-security-reports.md)
  
[查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 威胁调查和响应](office-365-ti.md)
  

