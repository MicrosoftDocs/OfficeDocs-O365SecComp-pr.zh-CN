---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/10/2019
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
ms.openlocfilehash: 626d827712760aa0b7b6faf75d94f525cfe38dc2
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524006"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a>在安全&amp;合规中心中使用威胁资源管理器

如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md), 并且您具有所需的权限, 则可以使用威胁资源管理器来确定和分析威胁。 例如, 您可以识别和删除已传递的恶意电子邮件, 或查看 Office 365 安全功能捕获的恶意软件。 威胁资源管理器 (也称为浏览器) 是一种功能强大的近实时工具, 可帮助安全操作团队在安全&amp;合规中心中调查和响应威胁。
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
若要使用资源管理器, &amp;请在安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。

> [!IMPORTANT]
> office 365 威胁智能现已成为 office 365 高级威胁防护计划2的一部分, 其中包含额外的威胁防护功能。 若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。
      
## <a name="explorer-overview"></a>Explorer 概述

资源管理器显示有关 Office 365 中的电子邮件和文件中可疑的恶意软件和网络钓鱼的信息, 以及组织中的其他安全威胁和风险。 首次打开资源管理器时, 默认视图将显示过去7天内的电子邮件恶意软件检测。 资源管理器还可以显示 Office 365 中的安全保护功能, 包括[安全链接](atp-safe-links.md)和[安全附件](atp-safe-attachments.md), 并且可以修改以显示过去30天的数据。 如果你有 Office 365 的试用订阅高级威胁防护计划2或 Office 365 E5, 你将只能看到过去7天的检测和电子邮件数据。
  
![资源管理器显示有关主要恶意软件和目标用户的信息](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
使用 "视图" 菜单更改要显示的信息。
  
![浏览器的视图菜单](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
资源管理器具有几个筛选和查询功能, 这些功能使您能够深入了解详细信息, 如主要目标用户、主要恶意软件系列、检测技术等。 每种报告都提供了查看和浏览数据的各种方式。

> [!IMPORTANT]
> 不要在浏览器中使用通配符, 如星号 (*) 或问号 (？)。 当您在 "主题" 字段中搜索电子邮件时, 资源管理器将执行部分匹配并生成类似于通配符搜索的结果。

## <a name="email--malware"></a>电子\>邮件恶意软件

此视图显示标识为包含恶意软件的电子邮件。  

在图表中查看由恶意软件系列、发件人域、发件人 IP、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 和检测技术 (检测到恶意软件) 的信息。  

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

在图表下方, 查看有关主要恶意软件系列、主要目标用户和特定邮件的详细信息的详细信息。 

## <a name="email--phish"></a>电子\>邮件网络钓鱼

此视图显示被标识为 "仿冒尝试" 的电子邮件。  

按发件人域、发件人 IP 和保护状态查看信息 (由 Office 365 中的威胁防护功能和策略执行的操作)。 

![查看标识为 "仿冒尝试" 的电子邮件的相关数据](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

在图表下方, 查看有关特定邮件的更多详细信息。 

## <a name="email--user-reported"></a>电子\>邮件用户报告

此视图显示用户已报告为垃圾邮件、非垃圾邮件或仿冒电子邮件的电子邮件。  

按报告类型查看信息 (用户确定电子邮件是垃圾邮件, 而非垃圾邮件或网络钓鱼), 传递原因 (电子邮件发送到特定位置的原因 (如垃圾邮件筛选器策略、邮件流规则、阻止发件人列表、安全发件人列表)等)。  

![查看报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件用户的相关数据](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

在图表下方, 查看有关特定电子邮件 (如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户) 的更多详细信息。 

## <a name="email--all-mail"></a>通过\>电子邮件发送所有邮件

此视图显示电子邮件活动的一个全视图方式, 包括因网络钓鱼或恶意软件而被标识为恶意的电子邮件, 以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件)。 

> [!NOTE]
> 如果收到一条错误, 指示**要显示的数据过多**, 请添加筛选器, 并在必要时缩小正在查看的日期范围。 

若要应用筛选器, 请选择 "**发件人**", 选择列表中的项目, 然后单击 "刷新" 按钮。 在我们的示例中, 我们将**检测技术**用作筛选器 (有几种可用选项)。 按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 查看信息、检测技术 (检测恶意软件的方式) 以及多. 

![查看检测技术检测到的电子邮件的相关数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

在图表下方, 查看有关特定电子邮件的详细信息, 如主题行、收件人、发件人、状态等。 

## <a name="content--malware"></a>内容\>恶意软件

此视图显示了 Office 365 高级威胁防护在 SharePoint Online、OneDrive for business 和 Microsoft 团队中被标识为恶意的文件。

查看恶意软件系列的信息、检测技术 (检测恶意软件的方式) 以及工作负荷 (OneDrive、SharePoint 或团队)。 

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

在图表下方, 查看有关特定文件的更多详细信息, 如附件文件名、工作负荷、文件大小、上次修改文件的时间等。 
  
## <a name="new-click-to-filter-capabilities"></a>(新!)单击-筛选功能

浏览器的新增功能是可以通过单击进行筛选。 当您单击图例中的项目时, 该项目将成为报表的筛选器。 例如, 假设我们在资源管理器中查看恶意软件视图:
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
单击此图表中的**ATP 沙箱**将生成如下所示的视图: 
  
![筛选器已筛选为仅显示 ATO 沙箱结果](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
在此视图中, 我们现在正在查看由[Office 365 ATP 安全附件](atp-safe-attachments.md)触发的文件的数据。 在图表下方, 我们可以查看包含由 ATP 安全附件检测到的附件的特定电子邮件的详细信息。
  
![包含检测到的附件的电子邮件的特定详细信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
选择一个或多个项目将激活 "**操作**" 菜单, 其中提供了几个选项, 可从中选择所选的项目。 
  
![选择项会激活 "操作" 菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
通过单击并导航到特定详细信息的功能, 可以在调查威胁方面为你节省大量时间。
  
## <a name="how-do-i-get-explorer"></a>如何获取资源管理器？

资源管理器包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中。 

若要查看和使用资源管理器, 您必须具有适当的权限, 如已授予安全管理员或安全阅读者的权限。 若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="related-topics"></a>相关主题

[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[查找并调查已传递的恶意电子邮件 (Office 365 威胁 Invesitgation and Response)](investigate-malicious-email-that-was-delivered.md)
  
[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)
  

