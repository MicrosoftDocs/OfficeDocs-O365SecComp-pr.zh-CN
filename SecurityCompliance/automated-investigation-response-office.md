---
title: 使用 Office 365 的自动化调查和响应 (空中)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/22/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护中的自动化调查和响应功能。
ms.openlocfilehash: c6cfc03588e580382f673b2e9be8543bfcaf9ac1
ms.sourcegitcommit: f6073deec39a18581ed12abef18728417a52cdf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2019
ms.locfileid: "30747558"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a>使用 Office 365 的自动化调查和响应 (空中)

自动化调查和响应 (空中) (即将推出[Office 365 威胁调查和响应功能](office-365-ti.md)) 使您能够对目前存在的已知威胁运行自动调查和补救措施。 阅读本文以了解空气的概述, 以及它如何帮助您的组织和安全操作团队更有效地缓解威胁。 若要了解更多有关 AIR 中的其他功能何时可用的详细信息, 请参阅[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="alerts"></a>警报

[警报](alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。 在确保没有威胁 unaddressed 的情况下, 确定用于调查的正确通知集的优先顺序。 在手动对通知进行调查时, 安全操作团队必须在威胁的风险下对实体 (例如, 内容、设备和用户) 进行搜寻和关联。 此类任务和工作流非常耗时, 并涉及多个工具和系统。 通过空气、调查和响应自动化到关键安全和威胁管理警报, 可自动触发安全响应行动手册。 

在2019年4月的最初发行版中, 根据以下单个事件通知策略生成的警报将自动调查。 

1. 检测到潜在的恶意 URL 单击
2. 用户报告为网络钓鱼的电子邮件 *
3. 包含在传递后删除的恶意软件的电子邮件 *
4. 包含在传递后删除的网络钓鱼 url 的电子邮件 *

* 注意: 已将这些警报分配给安全和合规中心内的各个警报策略中的 "信息性" 严重性, 并关闭电子邮件通知。 可以通过警报策略配置启用这些策略。

若要查看警报, 请在 "Office 365 Security & 合规中心" 中, 选择 "**通知** > " "**查看警报**"。 选择一个警报以查看其详细信息, 然后在那里使用 "**查看调查**" 链接转到相应的[调查](#investigation-graph)。

![链接到调查的警报](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a>安全行动手册

安全行动手册是在 Microsoft 威胁防护中处于自动化的中心的后端策略。 AIR 中提供的安全行动手册基于常见的实际安全方案。 当您的组织中触发一个警报时, 将自动启动安全行动手册。 通知触发后, 关联的行动手册将自动运行。 行动手册将运行调查, 查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等), 并根据其发现建议一组可供组织安全团队控制和缓解的操作威胁。 

你将使用空中获取的安全行动手册旨在解决组织目前面临的最常见威胁。 它们基于安全操作和事件响应团队的输入, 包括帮助保护 Microsoft 和客户资产的人员。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全行动手册在几个阶段推出

作为空气的一部分, 安全行动手册在几个阶段推出

- **第1阶段 (4 月 2019)**: 行动手册包含安全管理员查看和批准的操作建议。 

- **第2阶段 (6 月 2019)**: 安全管理员可以将安全行动手册配置为自动执行操作, 而无需管理交互。

阶段1将包括以下行动手册:
- 用户报告的网络钓鱼邮件
- URL 单击 "判定更改" 
- 恶意软件检测到送达后 (恶意软件 ZAP)
- 网络钓鱼检测到传递后的 zap (网络钓鱼 zap)
- 手动电子邮件调查 (使用威胁资源管理器)

规划第2阶段的其他几项行动手册。

### <a name="playbooks-include-investigation-and-recommendations"></a>行动手册包括调查和建议

每个行动手册包括: 
- 根调查 
- 确定并关联其他潜在威胁所需的步骤, 以及 
- 建议的威胁补救措施。

每个高级别步骤都包含多个执行的子步骤, 以提供对威胁的深入、详细和详尽的响应。

## <a name="example-user-reported-phish-message"></a>示例: 用户报告的网络钓鱼邮件

当组织中的用户提交电子邮件并将其报告给 Microsoft 时, 将使用[outlook 或 outlook Web Access 的报告消息外接程序](enable-the-report-message-add-in.md)。 这将触发基于系统的信息警报, 该警报将自动启动调查行动手册。

在根调查阶段, 会评估电子邮件的各个方面。 具体包括：
- 确定它可能属于哪种类型的威胁;
- 发件人数;
- 发送电子邮件的位置 (发送基础结构);
- 是否已传递或阻止电子邮件的其他实例;
- 我们分析家中的一种评估;
- 电子邮件是否与任何已知的市场活动相关联;
- 等等。

根调查完成后, 行动手册提供了建议采取的操作列表。
  
接下来, 执行以下几个威胁调查和搜寻步骤:

- 搜索其他电子邮件群集中的类似电子邮件。
- 该信号与其他平台 (如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)) 共享。
- 确定是否有用户通过了可疑电子邮件中的任何链接单击过。
- 跨 office 365 Exchange Online Protection ([EOP]) (EOP/exchange online-EOP) 和 Office 365 高级 Therat 保护 ([ATP]) (Office-365-atp.md) 执行检查, 以查看用户是否报告了任何其他类似的邮件。
- 将执行检查以查看是否已泄露用户。 此检查在[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)中利用信号, 关联任何相关的用户活动异常。 

在搜寻阶段, 会为各种搜寻步骤分配风险和威胁。  

修正是行动手册的最后阶段。 在此阶段中, 将根据 theinvestigation 和搜寻阶段采取补救措施。  

## <a name="getting-started"></a>入门

若要访问您的调查, 作为 Office 365 全局管理员、安全管理员或安全读者, 请转到 office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com)) 并登录。 然后执行下列操作之一：

- 在左侧导航中, 转到 "**威胁管理** > **调查**"。

    或

- 访问威胁管理仪表板 (在安全 & 合规性中心中, 转到 "**威胁管理** > **仪表板**")。

![空中小部件](media/air-widgets.png)

您的空中小部件将显示在[安全仪表板](security-dashboard.md)的顶部。 选择要开始的小部件。

您也可以直接从相关警报访问 invesitgation。

### <a name="automated-investigations"></a>自动调查

"自动调查" 页面显示您的组织的调查及其当前状态。

![空气的主要调查页面](media/air-maininvestigationpage.png) 
  
可以执行下列操作：
- 直接导航到调查 (选择**调查 ID**)。
- 应用筛选器。 从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。
- 将数据导出到 CSV 文件。

### <a name="investigation-graph"></a>调查图形

当您打开特定调查时, 您将看到 "调查图形" 页。 此页面显示所有不同的实体: 电子邮件、用户 (及其活动) 以及自动调查为触发的警报一部分的设备。

![空中调查图形页面](media/air-investigationgraphpage.png)

可以执行下列操作：
- 获取当前调查的直观概述。
- 查看调查计时的摘要。
- 在可视化中选择一个节点以查看该节点的详细信息。
- 在顶部选择一个选项卡以查看该选项卡的详细信息。

### <a name="alert-investigation"></a>通知调查

在调查的 "**通知**" 选项卡上, 您可以查看与调查相关的警报。 详细信息包括触发调查的警报以及与调查相关的其他警报 (如有风险的登录、成批下载等)。 在此页面中, 安全分析员还可以查看各个通知的其他详细信息。

![空气警报页面](media/air-investigationalertspage.png)

可以执行下列操作：
- 获取当前触发警报和任何关联警报的直观概述。
- 在列表中选择一个警报, 打开显示完整警报详细信息的飞出页面。

### <a name="email-investigation"></a>电子邮件调查

在调查的 "**电子邮件**" 选项卡上, 您可以看到标识为调查一部分的所有电子邮件群集。 

由于组织中的用户发送和接收的电子邮件数量巨大, 因此 
- 根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化; 
- 将恶意电子邮件与优质电子邮件分开;并 
- 对恶意电子邮件采取操作 

可能需要几个小时。 现在, AIR 可以自动执行此过程, 从而节省了贵组织的安全团队的时间和精力。 

例如, 请考虑以下方案。 三封电子邮件的第一个群集被认为是网络钓鱼。 找到具有相同 IP 和主题的类似邮件的另一个群集, 并被视为恶意邮件, 因为在初始检测过程中将其部分标识为网络钓鱼。 

![空中电子邮件调查页面](media/air-investigationemailpage.png)

可以执行下列操作：
- 获取当前群集结果和发现的威胁的直观概述。
- 单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。

![使用浮出控件详细信息的航空调查电子邮件](media/air-investigationemailpageflyoutdetails.png)

* 注意: 在电子邮件上下文中, 您可能会在调查过程中看到一个卷异常威胁曲面。 卷异常表示与早期的时间段相比, 调查事件时间周围类似电子邮件中的峰值。 这种具有类似特征 (例如, subject 和发件人域、正文相似性和发件人 IP) 的电子邮件通信的峰值是电子邮件宣传活动或攻击的典型启动。 不过, 有时批量和 spom 电子邮件活动也共享这些特征。 由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比, 大量异常会带来潜在的威胁, 因此可能会降低严重程度。

### <a name="user-investigation"></a>用户调查

在 "**用户**" 选项卡上, 您可以看到标识为调查的一部分的所有用户。 

例如, 在下图中, 空气根据创建的新收件箱规则确定了安全指标和异常情况。 可通过此选项卡中的详细视图查看调查的其他详细信息 (证据)。损坏的迹象和异常也可能包含来自[Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。

![空中调查用户页](media/air-investigationuserspage.png)

可以执行下列操作：
- 获取已确定的用户结果和发现的风险的直观概述。
- 选择用户以打开显示完整警报详细信息的飞出页面。

### <a name="machine-investigation"></a>机器调查

在 "**计算机**" 选项卡上, 您可以看到标识为调查的一部分的所有计算机。 

![空中调查计算机页面](media/air-investigationmachinepage.png)

作为调查的一部分, 空中将电子邮件威胁与设备相关联。 例如, 调查会将文件哈希传递到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)以进行调查。 这样, 就可以为您的用户自动调查相关的计算机, 并帮助确保在云中和设备之间解决威胁。 

可以执行下列操作：
- 获取发现的当前计算机和威胁的直观概述。
- 选择一台计算机以打开在 windows defender atp Security Center 中相关的[Windows defender atp 调查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)中的视图。

### <a name="entity-investigation"></a>实体调查

在 "**实体**" 选项卡上, 您可以看到标识为调查的一部分的所有计算机。 

在这里, 你可以看到调查的实体。 您可以查看实体类型的详细信息, 例如电子邮件、群集、IP 地址、用户等。 您还可以查看已分析的实体数以及与每个实体相关联的威胁。 

!["航空调查实体" 页](media/air-investigationentitiespage.png)

可以执行下列操作：
- 获取发现的调查实体和威胁的直观概述。
- 选择一个实体以打开显示相关实体详细信息的飞出页面。

![空中调查实体详细信息](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>行动手册日志

在 "**日志**" 选项卡上, 您可以查看调查过程中的所有操作手册步骤。 该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有操作的完整清单。 它提供了所执行的所有步骤的清晰视图, 包括操作本身、说明以及实际开始时间到完成的持续时间。 

![航空调查日志页](media/air-investigationlogpage.png)

可以执行下列操作：
- 获取有关执行操作手册步骤的直观概述。
- 将结果导出到 CSV 文件。
- 筛选视图。

### <a name="recommended-actions"></a>建议的操作

在 "**操作**" 选项卡上, 您可以查看在调查完成后建议用于修正的所有操作手册操作。 

操作会捕获 Microsoft 建议在调查结束时执行的步骤。 您可以通过选择一个或多个操作来采取补救措施。 单击 "**批准**" 将允许开始修正。 (需要适当的权限。 例如, 安全读者可以查看操作但不能批准。  

![航空调查操作页](media/air-investigationactionspage.png)

可以执行下列操作：
- 获取对操作手册建议的操作的直观概述。
- 选择一个或多个操作。
- 使用注释批准或拒绝建议的操作。
- 将结果导出到 CSV 文件。
- 筛选视图。

## <a name="how-to-get-air"></a>如何获取空中

目前, Office 365 AIR 处于预览阶段。 Office 365 AIR 将包含在以下订阅中:

- Microsoft 365 企业版 E5
- Office 365 企业版 E5
- Microsoft 威胁防护
- Office 365 高级威胁防护计划2

若要了解有关功能可用性的详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。
