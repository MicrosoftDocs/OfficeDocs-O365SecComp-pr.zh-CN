---
title: 威胁浏览器 (和实时检测)
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/20/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解安全&amp;合规性中心中的资源管理器 (和实时检测)。
ms.openlocfilehash: dff1fae01aa525135226d88b305de7c7c3aefb7c
ms.sourcegitcommit: bc25ea19c0b6d318751eadc4f27902b0054d5e2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36054754"
---
# <a name="threat-explorer-and-real-time-detections"></a>威胁浏览器 (和实时检测)

如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(OFFICE 365 ATP), 并且您拥有[必要的权限](#required-licenses-and-permissions), 则您可以使用**资源管理器**或**实时检测**(以前的*实时报告*)。[请参阅新增功能](#new-features-in-real-time-detections)! 在安全 & 合规性中心中, 转到 "**威胁管理**", 然后选择 "**浏览器**" 或 "**实时检测**"。 

|在 ATP 计划2中, 您将看到:  |在 ATP 计划1中, 您将看到:  |
|---------|---------|
|![威胁资源管理器](media/threatmgmt-explorer.png)      |![实时检测](media/threatmgmt-realtimedetections.png)         |

使用浏览器 (或实时检测) 时, 您将拥有一个强大的报告, 使安全操作团队能够有效地调查威胁并对其做出响应, 这与以下图像类似: 

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

使用此报告, 可以执行以下操作:
- [查看 Office 365 安全功能检测到的恶意软件](#see-malware-detected-in-email-by-technology)
- [查看有关仿冒 Url 的数据, 然后单击 "判定"](#view-data-about-phishing-urls-and-click-verdict)
- [从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response)(仅 ATP 计划 2)
- ...[调查恶意电子邮件,](#more-ways-to-use-explorer-or-real-time-detections)等等!

## <a name="new-features-in-real-time-detections"></a>实时检测中的新功能

资源管理器/实时检测添加新的新字段, 旨在为您提供电子邮件领域的更完整的详细信息。 此更改的目标部分是使搜索更易于进行安全操作人员, 但最终结果是了解问题电子邮件的位置。

这是如何完成的？ 传递状态现已分为两列:

- 传递操作-此电子邮件的状态是什么？
- 送达位置-此电子邮件的路由结果

传递操作是由于现有策略或检测而导致对电子邮件执行的操作。 以下是电子邮件可能执行的操作:

|附带  |Junked  |Blocked  |代替  |
|---------|---------|---------|---------|
|电子邮件已传递到用户的收件箱或文件夹, 用户可以直接访问它。    | 电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹, 并且用户有权访问这些文件夹中的电子邮件。       | 隔离的、失败的或已丢弃的任何电子邮件。 用户完全无法访问它!     | 所有恶意附件都被替换为 .txt 文件的电子邮件, 以表明附件是恶意的。     |

用户可以看到的内容及其不能执行的操作:

|最终用户可以访问  |最终用户无法访问  |
|---------|---------|
|附带     | Blocked        |
|Junked     | 代替        |

"送达位置" 显示运行送达后的策略和检测结果。 它已链接到传递操作。 添加此字段是为了深入了解在发现问题邮件时所采取的操作。 以下是送达位置的 possilbe 值:

1. 收件箱或文件夹–电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则)。
2. 本地或外部–邮箱在云上不存在, 但在本地。
3. 垃圾邮件文件夹–在用户的 "垃圾邮件" 文件夹中的电子邮件。
4. "已删除邮件" 文件夹–用户的 "已删除邮件" 文件夹中的电子邮件。
5. 隔离–隔离中的电子邮件, 并且不在用户的邮箱中。
6. 失败–电子邮件无法访问邮箱。
7. 丢弃–电子邮件在邮件流中的某个位置丢失。

电子邮件日程表是另一个新的浏览器功能, 旨在提高管理员的求职体验。 它会在随机时减少, 因为检查不同位置以尝试了解事件的时间较少。 当电子邮件上的多个事件发生时, 或在同一时间结束时, 这些事件将显示在 "日程表" 视图中。 事实上, 在传递给邮件的某些事件将在 "特殊操作" 列中捕获。 将该邮件的时间线中的信息与邮件投递后执行的特殊操作组合在一起, 管理员可以了解其策略的工作方式, 即最后路由邮件的位置, 在某些情况下, 最终评估是什么。


## <a name="see-malware-detected-in-email-by-technology"></a>查看电子邮件中的技术检测到恶意软件

假设您想要查看 Office 365 技术在电子邮件中检测到的恶意软件。 为此, 请使用[电子邮件 >](threat-explorer-views.md#email--malware)浏览器 (或实时检测) 的恶意软件视图。

1. 在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。 (此示例使用 Explorer。)

2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)<br/>

3. 单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。<br/>您的检测技术现在可用作报告的筛选器。<br/>![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. 选择一个选项, 然后单击 "**刷新**" 按钮以应用该筛选器。<br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。 在这里, 你可以进行进一步分析。

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>查看有关仿冒 Url 的数据, 然后单击 "判定"

假定您要查看通过电子邮件中的 Url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 Url 的列表。 标识所单击的 Url 需要配置[ATP 安全链接](atp-safe-links.md)。 确保已为单击时的保护设置了[Atp 安全链接策略](set-up-atp-safe-links-policies.md), 然后通过 ATP 安全链接单击 "verdicts" 进行日志记录。 

若要查看邮件中的网络钓鱼 Url 并单击网络钓鱼邮件中的 Url, 请使用[电子邮件 >](threat-explorer-views.md#email--phish)浏览器 (或实时检测) 的网络钓鱼视图。

1. 在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。 (此示例使用 Explorer。)

2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。<br/>![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)<br/>

3. 单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。

4. 选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击与应用该筛选器的选项位于同一行中的 "**刷新**" 按钮。 (不要刷新浏览器窗口。)<br/>![Url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    报告将刷新, 以在报告下的 "URL" 选项卡上显示两个不同的 URL 表:

   1. **上面的 url**是您已筛选出的邮件中包含的 url, 并且每个 URL 的电子邮件传递操作都会计数。 在网络钓鱼电子邮件视图中, 此列表通常包含合法的 Url。 攻击者在其邮件中加入了好和坏的 Url, 以尝试传递它们, 但它们会使用户更有趣地单击恶意链接。 Url 表按总电子邮件计数进行排序 (注意: 此列不显示为简化视图)。

   2. 单击 "**上**一条" 可将已单击的安全链接包装的 url 按总点击次数排序 (此列也不显示为简化视图)。 "总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。 在网络钓鱼电子邮件视图中, 这通常是可疑或恶意的 Url, 但可能包含网络钓鱼邮件中的干净 Url。 URL 单击未打开的链接将不会显示在此处。
   
   这两个 Url 表通过传递操作和位置显示网络钓鱼电子邮件中的前几个 Url, 并显示已阻止 (或在出现警告的情况下访问) 的 URL 单击, 以便您可以了解用户收到的潜在错误链接以及用户的交互情况。 在这里, 你可以进行进一步分析。 例如, 在图表下方, 您可以看到在组织的环境中被阻止的电子邮件中的最高 Url。
   
   ![阻止的资源管理器 Url](media/ExplorerPhishClickVerdictURLs.png)
   
   选择一个 URL 以查看更详细的信息。 请注意, 在 "URL 飞出" 对话框中, 将删除对电子邮件的筛选, 以向您显示在您的环境中 URL 公开的完整视图。 这样, 您就可以在资源管理器中筛选出您关注的电子邮件, 查找潜在威胁的特定 Url, 然后展开您对环境中的 URL 公开的了解 (通过 URL 详细信息对话框), 而无需将 URL 筛选器添加到资源管理器视图本身。

## <a name="review-email-messages-reported-by-users"></a>查看用户报告的电子邮件

假设您想要查看您的组织中的用户使用[Outlook 和 web 上的 outlook 的报告邮件外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。 为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图 (或实时检测)。

1. 在 "安全性 & 合规性中心[https://protection.office.com](https://protection.office.com)() 中, 选择"**威胁管理** > **资源管理器**"(或"**实时检测**")。 (此示例使用 Explorer。)

2. 在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。<br/>![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)<br/>

3. 单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。

4. 选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。 <br/>![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)<br/> 

报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。 您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。

## <a name="start-automated-investigation-and-response"></a>启动自动调查和响应

> [!NOTE]
> **Office 365 ATP 计划 2**和**Office 365 E5**中提供了自动调查和响应功能。

(新!)[自动化调查和响应](automated-investigation-response-office.md)可在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。 除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。 

有关此操作的详细信息, 请参阅[示例: 安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>使用资源管理器 (或实时检测) 的更多方法

除了本文中介绍的方案之外, 您还可以使用浏览器 (或实时检测) 中提供的更多报告选项。 
- [查找和调查投递的恶意电子邮件](investigate-malicious-email-that-was-delivered.md)
- [查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件](malicious-files-detected-in-spo-odb-or-teams.md)
- [获取威胁资源管理器中的视图 (和实时检测) 的概述](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

您必须具有[Office 365 ATP](office-365-atp.md)才能获取资源管理器或实时检测。
- 资源管理器包含在 Office 365 ATP 计划2中。 
- 实时检测报告包含在 Office 365 ATP 计划1中。
- 计划为应由 ATP 保护的所有用户分配许可证。 (资源管理器或实时检测将显示许可用户的检测数据。)

若要查看和使用资源管理器或实时检测, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。 

- 对于安全&amp;合规中心, 您必须具有以下分配的角色之一:
    - 组织管理
    - 安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - 安全读者

- 对于 Exchange Online, 必须在 Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 组织管理
    - 仅限查看组织管理
    - “仅供查看收件人”角色
    - 合规性管理

若要了解有关角色和权限的详细信息, 请参阅以下资源:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="some-differences-between-real-time-detection-and-threat-exporter"></a>实时检测和威胁导出程序之间存在一些差异。

 - **实时检测报告**随 atp P1 订阅一起提供, 而**威胁资源管理器**附带 atp P2。
 - **实时检测**报告允许您实时显示检测, 而威胁资源管理器报告可让您在给定攻击中查看更多详细信息。
 - **威胁资源管理器**报告提供了不同的报告集, 可增强您对**实时检测**程序报告的体验。