---
title: 威胁资源管理器中的视图和实时检测
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: 了解在威胁资源管理器和实时检测中可用的各种视图类型。
ms.openlocfilehash: 82476f9af3b703904fff40c8347f2848cf919dfc
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230386"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>威胁资源管理器中的视图和实时检测

![威胁资源管理器](media/ThreatExplorerFirstOpened.png)

[威胁资源管理器](use-explorer-in-security-and-compliance.md)(和实时检测报告) 是一种强大的近实时工具, 可帮助安全操作团队调查和响应安全&amp;合规性中心中的威胁。 资源管理器 (和实时检测报告) 显示有关 Office 365 中的电子邮件和文件中可疑的恶意软件和网络钓鱼的信息, 以及组织中的其他安全威胁和风险。 

- 如果您有[Office 365 高级威胁防护](office-365-atp.md)(ATP) 计划 2, 则您将拥有资源管理器。
- 如果你有 Office 365 ATP 计划 1, 则会进行实时检测。

首次打开浏览器 (或实时检测报告) 时, 默认视图将显示过去7天内的电子邮件恶意软件检测。 此报告还可以显示 ATP 检测, 如[安全链接](atp-safe-links.md)检测到的恶意 url, 以及[安全附件](atp-safe-attachments.md)检测到的恶意文件。 可以修改此报告以显示过去30天的数据 (除非您使用的是试用订阅)。 试用订阅将仅包含过去七天的数据。

使用 "**视图**" 菜单更改要显示的信息。 工具提示可帮助您确定要使用的视图。
  
![威胁资源管理器视图菜单](media/ThreatExplorerViewMenu.png)

选择视图后, 可以应用筛选器并设置查询以执行进一步分析。 以下各节提供了浏览器中提供的各种视图 (或实时检测) 的简要概述。  

## <a name="email--malware"></a>电子邮件 > 恶意软件

若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **电子邮件** > **恶意软件**"。 此视图显示标识为包含恶意软件的电子邮件的相关信息。  

![查看标识为恶意软件的电子邮件的相关数据](media/ExplorerEmailMalwareMenu.png) 

单击 "**发件人**" 打开查看选项列表。 使用此列表可以按发件人、收件人、发件人域、主题、检测技术、保护状态等查看数据。 

例如, 若要查看对检测到的电子邮件所执行的操作, 请在列表中选择 "**保护状态**"。 选择一个选项, 然后单击 "刷新" 按钮将该筛选器应用于报表。

![威胁资源管理器的威胁防护状态选项](media/ThreatExplorerProtectionStatusOptions.png)

在图表下方, 查看有关特定邮件的更多详细信息。 当您选择列表中的某个项目时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。 

![打开了浮出控件的威胁资源管理器](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>电子邮件 > 网络钓鱼

若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **电子邮件** > **网络钓鱼**"。 此视图显示被标识为 "仿冒尝试" 的电子邮件。  

![查看标识为 "仿冒尝试" 的电子邮件的相关数据](media/ThreatExplorerEmailPhish.png) 

单击 "**发件人**" 打开查看选项列表。 使用此列表可以按发件人、收件人、发件人域、发件人 IP、URL 域查看数据, 然后单击 "判定", 等等。 

例如, 若要查看当用户单击被标识为仿冒的 Url 时所采取的操作, 请在列表中选择 **"单击判定**项", 选择一个或多个选项, 然后单击 "刷新" 按钮。

![单击网络钓鱼报告的 "判定选项"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

在图表下方, 查看有关特定邮件、URL 单击、Url 和电子邮件来源的更多详细信息。 

![在电子邮件中检测到作为网络钓鱼的 Url](media/ThreatExplorerEmailPhishURLs.png)

当您选择列表中的某个项目 (如检测到的 URL) 时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。 

![有关检测到的 URL 的详细信息](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>电子邮件 > 提交

若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **电子邮件** > **提交**"。 此视图显示用户已报告为垃圾邮件、非垃圾邮件或仿冒电子邮件的电子邮件。 

![用户报告的电子邮件](media/ThreatExplorerEmailUserReportedViewOptions.png) 

单击 "**发件人**" 打开查看选项列表。 使用此列表可以按发件人、收件人、报告类型查看信息 (用户决定电子邮件是垃圾邮件, 而不是垃圾邮件或网络钓鱼) 等。 

例如, 若要查看报告为 "仿冒试" 的电子邮件的信息, 请单击 "**发件人** > **报告类型**", 选择 "**网络钓鱼**", 然后单击 "刷新" 按钮。

![为报告类型筛选器选择的网络钓鱼](media/ThreatExplorerEmailUserReportedPhishSelected.png)

在图表下方, 查看有关特定电子邮件 (如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户) 的更多详细信息。 

![被报告为网络钓鱼尝试的邮件](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

在列表中选择一个项目以查看其他详细信息。

## <a name="email--all-email"></a>电子邮件 > 所有电子邮件

若要查看此报告, 请在资源管理器中选择 "**查看** > **** > **全部邮件**"。 此视图显示电子邮件活动的一个全视图方式, 包括因网络钓鱼或恶意软件而被标识为恶意的电子邮件, 以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件)。 

> [!NOTE]
> 如果收到一条错误, 指示**要显示的数据过多**, 请添加筛选器, 并在必要时缩小正在查看的日期范围。 

若要应用筛选器, 请选择 "**发件人**", 选择列表中的项目, 然后单击 "刷新" 按钮。 在我们的示例中, 我们将**检测技术**用作筛选器 (有几种可用选项)。 按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 查看信息、检测技术 (检测恶意软件的方式) 以及多. 

![查看检测技术检测到的电子邮件的相关数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

在图表下方, 查看有关特定电子邮件的详细信息, 如主题行、收件人、发件人、状态等。 

## <a name="content--malware"></a>内容 > 恶意软件

若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **内容** > **恶意软件**"。 此视图显示了[Office 365 高级威胁防护在 SharePoint Online、OneDrive For business 和 Microsoft 团队中](atp-for-spo-odb-and-teams.md)被标识为恶意的文件。

查看恶意软件系列的信息、检测技术 (检测恶意软件的方式) 以及工作负荷 (OneDrive、SharePoint 或团队)。 

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

在图表下方, 查看有关特定文件的更多详细信息, 如附件文件名、工作负荷、文件大小、上次修改文件的时间等。 
  
## <a name="click-to-filter-capabilities"></a>单击-筛选功能

使用浏览器 (和实时检测), 您可以在单击时应用筛选器。 单击图例中的项目, 该项目将成为报表的筛选器。 例如, 假设我们在资源管理器中查看恶意软件视图:
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
单击此图表中的**ATP 沙箱**将生成如下所示的视图: 
  
![筛选器已筛选为仅显示 ATP 沙箱结果](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
在此视图中, 我们现在正在查看由[Office 365 ATP 安全附件](atp-safe-attachments.md)触发的文件的数据。 在图表下方, 我们可以查看包含由 ATP 安全附件检测到的附件的特定电子邮件的详细信息。
  
![包含检测到的附件的电子邮件的特定详细信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
选择一个或多个项目将激活 "**操作**" 菜单, 其中提供了几个选项, 可从中选择所选的项目。 
  
![选择项会激活 "操作" 菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
通过单击并导航到特定详细信息的功能, 可以在调查威胁方面为你节省大量时间。

## <a name="queries-and-filters"></a>查询和筛选器

资源管理器 (以及实时检测报告) 具有多种功能强大的筛选器和查询功能, 使您可以深入了解详细信息, 如主要目标用户、主要恶意软件系列、检测技术等。 每种报告都提供了查看和浏览数据的各种方式。

> [!IMPORTANT]
> 请勿在浏览器 (或实时检测) 的查询栏中使用通配符 (如星号或问号)。 当您在 "**主题" 字段**中搜索电子邮件时, 资源管理器 (或实时检测) 将执行与通配符搜索类似的部分匹配和生成结果。
