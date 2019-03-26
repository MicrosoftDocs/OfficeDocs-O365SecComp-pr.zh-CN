---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解安全&amp;合规性中心中的资源管理器 (也称为 "威胁浏览器")。
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732255"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用威胁资源管理器

如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md), 并且您具有所需的权限, 则可以使用威胁资源管理器来确定和分析威胁。 例如, 您可以识别和删除已传递的恶意电子邮件, 或查看 Office 365 安全功能捕获的恶意软件。 威胁资源管理器 (也称为浏览器) 是一种功能强大的近实时工具, 可帮助安全操作团队在安全&amp;合规中心中调查和响应威胁。
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
若要使用资源管理器, &amp;请在安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。

> [!IMPORTANT]
> office 365 威胁智能现已成为 office 365 高级威胁防护计划 2, 以及其他威胁防护功能。 若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
      
## <a name="explorer-overview"></a>Explorer 概述

如果您的组织具有[Office 365 威胁调查和响应功能](office-365-ti.md)(这包括在 ATP 计划2中), 并且您具有必要的权限, 则可以使用威胁浏览器 (也称为 "资源管理器") 来识别和分析威胁。 (在安全&amp;合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。)

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

本文介绍了您可以使用资源管理器执行的几项操作 (还有更多可能):

- [查看在电子邮件中检测到的恶意软件](#see-malware-detected-in-email-by-technology), 以及威胁防护技术 (反恶意软件保护、ATP 安全附件等)

- [查看有关仿冒链接 (url) 的数据](#view-data-about-phishing-urls-and-click-verdict), 以及单击 verdicts 的内容 (阻止、允许或访问的 url (无论是警告)

- [查看被报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子](#review-email-messages-reported-by-users)邮件, 并确定任何趋势 (例如, 报告为网络钓鱼的邮件数大于常规邮件数) 

## <a name="see-malware-detected-in-email-by-technology"></a>查看电子邮件中的技术检测到恶意软件

假设您想要查看在电子邮件中检测到的恶意软件, 以及 Office 365 中的哪种技术。 为此, 请使用资源管理器的[电子邮件 > 恶意软件](threat-explorer-views.md#email--malware)视图。

1. 在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. 单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。<br/>您的检测技术现在可用作报告的筛选器。<br/>![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. 选择一个选项, 然后单击 "刷新" 按钮以应用该筛选器。<br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。 在这里, 你可以进行进一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>查看有关仿冒 url 的数据, 然后单击 "判定"

假设您要查看通过电子邮件中的 url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 url 的列表。 为此, 请使用资源管理器的[电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish)视图。

1. 在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)<br/>
3. 单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。
4. 选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击 "**刷新**" 按钮以应用该筛选器。<br/>![url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

报告将刷新以显示检测到的电子邮件中被阻止的仿冒 url (或在出现警告的情况下访问) 以及电子邮件传递状态。 在这里, 你可以进行进一步分析。 例如, 在图表下方, 您可以看到在组织的电子邮件中被阻止的最高 url。 

![阻止的资源管理器 url](media/ExplorerPhishClickVerdictURLs.png) 

选择一个 URL 以查看更详细的信息。

## <a name="review-email-messages-reported-by-users"></a>查看用户报告的电子邮件

假设您要查看组织中的用户通过使用[Outlook 和 web 上的 outlook 的报告消息外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。 为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图。

1. 在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。<br/>![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. 单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。
4. 选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。 <br/>![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)<br/> 

报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。 您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。

## <a name="theres-more"></a>还有更多!

除了本文中介绍的三个方案之外, 您还可以使用浏览器中提供的多种报告方案。 以下是几个更多示例:

- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)

- [查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件](malicious-files-detected-in-spo-odb-or-teams.md)

- [获取有关威胁资源管理器中的视图的概述](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a>如何获取资源管理器

资源管理器包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中。 

若要查看和使用资源管理器, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。 

- 对于安全&amp;合规中心, 您必须具有以下分配的角色之一:
    - 组织管理
    - 安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - 安全读者

- 对于 exchange Online, 必须在 exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 组织管理
    - 仅限查看组织管理
    - “仅供查看收件人”角色
    - 合规性管理

若要了解详细信息, 请参阅以下资源:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a>相关主题

- [自动化调查和响应 (空中)](automated-investigation-response-office.md)

- [威胁资源管理器视图](threat-explorer-views.md)

- [查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
