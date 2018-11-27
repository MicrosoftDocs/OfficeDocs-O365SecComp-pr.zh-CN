---
title: 在安全中使用资源管理器&amp;合规性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: 了解在安全资源管理器 （也称为威胁资源管理器）&amp;合规性中心。
ms.openlocfilehash: 1b3088028651b445d890333a25804902843d915d
ms.sourcegitcommit: 7f45890ecfa5e15575df4e3ebe472a8dd8d99112
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674917"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a>在安全中使用资源管理器&amp;合规性中心

如果您的组织具有[Office 365 威胁智能](office-365-ti.md)，并且您所需的权限，您可以使用资源管理器确定和分析威胁。例如，您可以确定和删除恶意已发送的电子邮件或请参阅 Office 365 安全功能由已捕获的恶意软件。资源管理器 （也称为威胁资源管理器） 是强大的近乎实时报告安全中&amp;合规性中心。
  
![转到威胁管理\>资源管理器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
安全中使用资源管理器，&amp;合规性中心中，转到**威胁管理** \> **资源管理器**。
      
## <a name="explorer-overview"></a>资源管理器概述

资源管理器显示您的组织的信息可疑电子邮件中的恶意软件和 Office 365 中的文件，以及其他安全威胁和风险。当您首次打开资源管理器中时，默认视图显示从防病毒的恶意软件检测过去 7 天。资源管理器还可以显示安全保护功能在 Office 365 中，包括[安全链接](atp-safe-links.md)和[安全的附件](atp-safe-attachments.md)，并可进行修改以显示过去 30 天的数据。
  
![资源管理器显示有关流行恶意软件和目标的用户的信息](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
使用视图菜单来更改显示的信息。
  
![资源管理器视图菜单](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
资源管理器具有多个筛选和查询功能，使您能够深入了解详细信息，如顶部目标用户、 流行恶意软件家庭和详细信息。每种类型的报告提供了多种方式查看和分析数据。

> [!IMPORTANT]
> 不要使用通配符字符，例如星号 （*） 或使用资源管理器问号 （？）。在搜索主题字段中的电子邮件时，资源管理器将执行部分匹配并产生类似于结果通配符搜索。

## <a name="email--malware"></a>电子邮件\>恶意软件

此视图显示了标识为包含恶意软件的电子邮件。  

查看由恶意软件系列、 发件人域、 发件人 IP、 保护状态 （您威胁保护功能和 Office 365 中的策略所采取的操作） 和检测技术 （如何恶意软件检测到） 图表中的信息。  

![查看关于恶意软件检测到的数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

下面的图表，查看有关流行恶意软件系列详细信息顶部目标用户和有关特定消息的更多详细信息。 

## <a name="email--phish"></a>电子邮件\>网络钓鱼

此视图显示电子邮件标识为网络钓鱼尝试。  

查看由发件人域、 发件人 IP 和保护状态 （您威胁保护功能和 Office 365 中的策略执行的操作） 的信息。 

![关于电子邮件标识为网络钓鱼尝试查看数据](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

下面的图表，查看有关特定消息的更多详细信息。 

## <a name="email--user-reported"></a>电子邮件\>用户报告

此视图显示电子邮件用户具有报告为垃圾、 不是垃圾邮件或网络钓鱼电子邮件。  

通过报表类型 （电子邮件已垃圾、 不是垃圾邮件或网络钓鱼诈骗用户确定） 并传递原因 （原因电子邮件进入特定位置，如的垃圾邮件筛选器策略、 邮件流规则、 被阻止的发件人列表、 安全的发件人列表中，查看信息等）。  

![有关电子邮件的用户查看数据报告为垃圾、 不是垃圾邮件或网络钓鱼](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

下面的图表，查看有关特定电子邮件，如主题行、 发件人的 IP 地址、 报告为垃圾邮件、 未垃圾，或网络钓鱼诈骗、 等的邮件的用户的详细信息。 

## <a name="email--all-mail"></a>电子邮件\>的所有邮件

此视图显示所有向上视图的电子邮件活动，包括电子邮件标识为恶意截止到网络钓鱼或恶意软件、，以及所有非恶意邮件 （普通电子邮件、 垃圾邮件、 和批量邮件）。 

> [!NOTE]
> 如果您收到一条错误，读取**太多的数据以显示**、 添加筛选器，如有必要，缩小范围正在查看的日期范围。 

要应用筛选器，请选择**发件人**，在列表中，选择一个项目，然后单击刷新按钮。在我们的示例，我们使用**检测技术**为筛选器 （有几个选项可用）。查看按发件人、 发件人的域、 收件人、 主题、 附件的文件名、 恶意软件系列、 保护状态 （您威胁保护功能和 Office 365 中的策略执行的操作）、 （如何恶意软件检测到），检测技术信息和更多。 

![查看关于检测到的电子邮件检测技术提供支持的数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

下面的图表，查看有关特定电子邮件，如主题行、 收件人、 发件人、 状态和等等的详细信息。 

## <a name="content--malware"></a>内容\>恶意软件

此视图显示了标识为恶意在 SharePoint Online、 OneDrive for Business 和 Microsoft 团队的文件。

由恶意软件系列，检测技术，（如何恶意软件检测到），查看信息和工作负荷 （OneDrive、 SharePoint、 或团队）。 

![查看关于恶意软件检测到的数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

下面的图表，查看有关特定的文件，如附件的文件名、 工作负荷、 文件大小，上次修改文件和更多详细信息。 
  
## <a name="new-click-to-filter-capabilities"></a>（新） ！单击到筛选器功能

新增到资源管理器中是单击以筛选的能力。开始在后期年 5 月 2018，当您单击图例中的项目，该项目将成为报表的筛选器。例如，假设我们要看资源管理器中的恶意软件视图：
  
![转到威胁管理\>资源管理器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
此图表导致类似的视图中，单击**ATP Detonation** : 
  
![筛选以显示仅 ATO Detonation 结果的资源管理器](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
在此视图中，我们现在在看过 detonated 通过[Office 365 ATP 安全附件](atp-safe-attachments.md)的文件的数据。下面的图表，我们可以看到有关具有检测 ATP 安全附件的附件的特定的电子邮件消息的详细信息。
  
![检测到的附件的电子邮件的特定信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
选择一个或多个项激活**操作**菜单，它提供了可供选择的选定项的多个选项。 
  
![选择项目激活操作菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
在单击筛选器并导航到具体的详细信息的功能可以将您大量时间调查威胁。
  
## <a name="how-do-i-get-explorer"></a>如何获取资源管理器？

[Office 365 威胁智能](office-365-ti.md)包含资源管理器。 

您必须具有适当的权限，如授予 security 管理员程序或安全读取器才能查看和使用资源管理器。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="related-topics"></a>相关主题

[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)
  
[查找并调查恶意电子邮件已送达 （Office 365 威胁智能）](investigate-malicious-email-that-was-delivered.md)
  
[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)
  

