---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/31/2019
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
ms.openlocfilehash: c782e5962164b7d35947befe526c20f7dc0943d5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264688"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用威胁资源管理器

如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md) (ATP), 并且您具有所需的权限, 则可以使用威胁资源管理器 (也称为 "资源管理器") 来确定和分析威胁。 (若要使用资源管理器, &amp;请在安全合规中心中, 转到 "**威胁管理** \> **资源管理器**"。)

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

资源管理器是一种功能强大的近实时工具, 可帮助安全操作团队调查和响应安全&amp;合规性中心中的威胁。 下面是您可以执行的一些操作:
- [查看 Office 365 安全功能检测到的恶意软件](#see-malware-detected-in-email-by-technology)
- [查看有关仿冒 url 的数据, 然后单击 "判定"](#view-data-about-phishing-urls-and-click-verdict)
- [从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response)
- ...[更多](#more-ways-to-use-explorer)!

## <a name="see-malware-detected-in-email-by-technology"></a>查看电子邮件中的技术检测到恶意软件

假设您想要查看在电子邮件中检测到的恶意软件, 以及 Office 365 中的哪种技术。 为此, 请使用资源管理器的[电子邮件 > 恶意软件](threat-explorer-views.md#email--malware)视图。

1. 在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)<br/>
3. 单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。<br/>您的检测技术现在可用作报告的筛选器。<br/>![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)<br/> 
4. 选择一个选项, 然后单击 "刷新" 按钮以应用该筛选器。<br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。 在这里, 你可以进行进一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>查看有关仿冒 url 的数据, 然后单击 "判定"

假设您要查看通过电子邮件中的 url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 url 的列表。  若要标识所单击的 url, 则需要[ATP 安全链接](atp-safe-links.md)。 (请确保已将[atp 安全链接策略](set-up-atp-safe-links-policies.md)设置并应用到用户的单击时保护和日志记录的单击 verdicts 依据 ATP 安全链接。)若要查看邮件中的网络钓鱼 url 并单击网络钓鱼邮件中的 url, 请使用资源管理器的[电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish)视图。

1. 在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)<br/>
3. 单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。
4. 选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击 "**刷新**" 按钮以应用该筛选器。<br/>![url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

在下面的 "URL" 选项卡上, 报告将刷新以显示两个不同的 URL 表:
1. **上面的 url**是您已筛选出的邮件中包含的 url, 并且每个 URL 的电子邮件传递操作都会计数。 在网络钓鱼电子邮件视图中, 此列表通常包含合法的 url。 攻击者在其邮件中加入了好和坏的 url, 以尝试传递它们, 但它们会使用户更有趣地单击恶意链接。 url 表按总电子邮件计数进行排序 (注意: 此列不显示为简化视图)。
2. 单击 "**上**一条" 可将已单击的安全链接包装的 url 按总点击次数排序 (此列也不显示为简化视图)。 "总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。 在网络钓鱼电子邮件视图中, 这些链接通常是可疑或恶意链接, 但可能包含出现在网络钓鱼邮件中的清理 url。 URL 单击未打开的链接将不会显示在此处。

这两个 url 表通过传递状态显示网页仿冒电子邮件中的主要 url, 并显示已阻止 (或在出现警告的情况下访问) 的 url 单击, 以便您可以了解用户收到的潜在的错误链接以及用户的交互情况。 在这里, 你可以进行进一步分析。 例如, 在图表下方, 您可以看到在组织的环境中被阻止的电子邮件中的最高 url。 

![阻止的资源管理器 url](media/ExplorerPhishClickVerdictURLs.png) 

选择一个 URL 以查看更详细的信息。 请注意, 在 "URL 飞出" 对话框中, 将删除对电子邮件的筛选, 以向您显示完整的 URL 在您的环境中的公开视图。 这样, 您就可以在资源管理器中筛选出您关注的电子邮件, 查找潜在威胁的特定 url, 然后展开您对环境中的 url 公开的了解 (通过 URL 详细信息对话框), 而无需将 url 筛选器添加到资源管理器视图本身。

## <a name="review-email-messages-reported-by-users"></a>查看用户报告的电子邮件

假设您要查看组织中的用户通过使用[Outlook 和 web 上的 outlook 的报告消息外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。 为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图。

1. 在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。
2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。<br/>![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)<br/>
3. 单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。
4. 选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。 <br/>![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)<br/> 

报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。 您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>启动自动调查和响应

(新!)[自动调查和响应](automated-investigation-response-office.md)(最近添加到 ATP 计划 2) 可以在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。 除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。 

有关此操作的详细信息, 请参阅[示例: 安全管理员可触发来自威胁资源管理器的调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer"></a>使用资源管理器的更多方法

除了本文中介绍的方案, 您还可以使用浏览器中提供的更多报告选项。 
- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件](malicious-files-detected-in-spo-odb-or-teams.md)
- [获取有关威胁资源管理器中的视图的概述](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

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

若要了解有关角色和权限的详细信息, 请参阅以下资源:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
