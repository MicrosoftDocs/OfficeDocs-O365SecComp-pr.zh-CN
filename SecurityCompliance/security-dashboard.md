---
title: 安全仪表板概述 （英文)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/07/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection: M365-security-compliance
description: 使用新的安全仪表板查看 Office 365 威胁保护状态，以及查看和操作安全警告。
ms.openlocfilehash: 403c47ed09e9652a66abeafb93be02589c9b1702
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995123"
---
# <a name="security-dashboard"></a>安全仪表板

## <a name="overview"></a>概述

[安全&amp;合规性中心](go-to-the-securitycompliance-center.md)允许贵组织管理数据保护和合规性。假定您具有所需的权限，在安全仪表板，可以查看您威胁的保护状态，以及查看和操作安全警告。 
  
观看视频以大致了解，，然后阅读本文以了解详细信息。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/3540b1f8-62d2-47fa-a07d-d7ad76f55b0f?autoplay=false]
  
根据组织的 Office 365 订阅包括安全仪表板包含多个小部件，如威胁管理摘要、 威胁保护状态、 全局每周威胁检测、 恶意软件、 和详细信息，如中所述以下各节。
  
若要查看安全仪表板中，在[Office 365 安全性&amp;合规性中心](go-to-the-securitycompliance-center.md)，请转到**威胁管理** \> **仪表板**。
  
> [!NOTE]
> 您必须是 Office 365 全局管理员、 安全管理员或安全读者查看安全仪表板。一些小部件需要查看其他权限。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="threat-management-summary"></a>威胁管理摘要

威胁管理摘要小部件将向您介绍概览如何组织已抵御威胁天前七个 （7）。

![安全仪表板-威胁管理摘要小部件](media/SecDash-ThreatMgmtSummary.png)

您将看到威胁管理摘要中的信息取决于您的订阅所包含的内容。下表描述了将 Office 365 企业版 E3 和 Office 365 企业 E5 包括哪些信息。


|Office 365 企业版 E3  |Office 365 企业版 E5  |
|---------|---------|
|已阻止的恶意软件消息<br/>网络钓鱼邮件被阻止<br>用户报告的邮件<br><br><br><br> |已阻止的恶意软件消息<br>网络钓鱼邮件被阻止<br>用户报告的邮件<br>零时差恶意软件阻止<br>检测到的高级网络钓鱼邮件<br>恶意 Url 阻止 |

若要查看或访问威胁管理摘要小部件，您必须有权查看高级威胁保护报告。若要了解详细信息，请参阅[查看 ATP 报告需要哪些权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="threat-protection-status"></a>威胁保护状态

威胁保护状态小部件显示威胁保护网络钓鱼诈骗和恶意软件的趋势和详细视图的有效性。 

![威胁保护状态小部件](media/tpswidget.png)

详细信息取决于是否在 Office 365 订阅包括[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) 使用或不[Office 365 高级威胁保护](office-365-atp.md)(ATP)。


|如果您的订阅包括... |您将看到这些详细信息 |
|---------|---------|
|EOP，但不是 Office 365 ATP     |已检测和阻止 EOP 恶意电子邮件<br> 请参阅[威胁保护状态报告 (EOP)](view-email-security-reports.md#threat-protection-status-report)。| |
|Office 365 ATP |恶意内容和恶意邮件检测和阻止 EOP 和 Office 365 ATP<br>聚合带有恶意阻止反恶意软件引擎、[零时差自动清除](zero-hour-auto-purge.md)，请和 ATP 功能 （包括[安全链接](atp-safe-links.md)、[安全的附件](atp-safe-attachments.md)和[ATP 防钓鱼](atp-anti-phishing.md)） 的内容的唯一电子邮件数。<br>请参阅[威胁保护状态报告 (ATP)](view-reports-for-atp.md#threat-protection-status-report)。 | 

若要查看或访问威胁保护状态小部件，您必须有权查看高级威胁保护报告。若要了解详细信息，请参阅[查看 ATP 报告需要哪些权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

## <a name="global-weekly-threat-detections"></a>全局每周威胁检测
 
全局每周威胁检测小部件显示过去七个 （7） 天中电子邮件中检测多少威胁。

![全局每周威胁检测小部件](media/globalweeklythreatdetections.png)

下表中所述，指标进行计算：

|度量  |计算方式  |
|---------|---------|
|扫描的邮件 |扫描的邮件数乘以收件人数 |
|停止的威胁  |标识为包含恶意软件乘以收件人数的电子邮件消息的数目 |
|阻止由[ATP](office-365-atp.md) |阻止 ATP 乘以收件人数的电子邮件消息的数目 |
|传递后删除 |删除由[零时差自动清除](zero-hour-auto-purge.md)乘以收件人数的消息数 |

## <a name="malware"></a>恶意软件

恶意软件小部件过去七个 （7） 天内显示有关恶意软件趋势和恶意软件系列类型的详细信息。

![恶意软件趋势和类型系列](media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>见解

见解不仅公开您应当查看的关键问题，他们还包括建议和操作，可以考虑。 

![智能见解](media/smartinsights.png)

例如，您可能会看到正在传递网络钓鱼邮件，因为某些用户禁用了其垃圾邮件选项。若要了解有关见解的工作方式的详细信息，请参阅[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)。
  
## <a name="threat-intelligence"></a>威胁智能

如果您的组织订阅包括[威胁智能功能](office-365-ti.md)，您的安全仪表板具有**威胁智能**节包含高级的工具。贵组织的安全工作组可以使用本节中的信息，以了解新兴市场活动、 调查威胁和管理事件。 
  
![威胁智能可帮助您了解在您的组织目标的攻击](media/threatintelwidget.png)
  
  
## <a name="trends"></a>趋势

安全仪表板的底部附近是**趋势**部分，它总结了为您的组织的电子邮件流趋势。报告提供有关电子邮件归类为垃圾邮件、 恶意软件、 网络钓鱼诈骗和好的电子邮件的信息。单击图块，以查看报告中的更多详细的信息。 
  
![趋势部分总结了组织的电子邮件流趋势](media/trends.png)
  
如果贵组织的 Office 365 订阅包括[威胁智能功能](office-365-ti.md)，还将安全团队可以查看并对其执行操作本部分中具有**最新的威胁管理通知**报表高优先级安全警告。 

若要查看或访问已发送和接收电子邮件小部件，您必须有权查看高级威胁保护报告。若要了解详细信息，请参阅[查看 ATP 报告需要哪些权限？](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)。 

若要查看或访问最近的威胁管理通知小部件，您必须有权查看警报。若要了解详细信息，请参阅[查看警报所需的 RBAC 权限](alert-policies.md#rbac-permissions-required-to-view-alerts)。
  
## <a name="related-topics"></a>相关主题

[查看安全中的电子邮件安全报告&amp;合规性中心](view-email-security-reports.md)
  
[Office 365 高级威胁保护的视图报告](view-reports-for-atp.md)
  
[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 威胁智能](office-365-ti.md)
  

