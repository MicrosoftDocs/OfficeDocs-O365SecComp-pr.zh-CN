---
title: Exchange Online Protection 中的报告和邮件跟踪
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。下表描述了 EOP 管理员可用的报告和故障排除工具。
ms.openlocfilehash: 39ac70c401cb4a630b95fab89fe3a145495c29eb
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676562"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection 中的报告和邮件跟踪

Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。 此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。

## <a name="usage-reports"></a>使用率报告

**Office 365 组活动**: 查看有关创建和使用的 office 365 组数量的信息。  

**电子邮件活动**: 查看有关整个组织中发送、接收和读取的邮件数的信息以及特定用户的信息。  

**电子邮件应用程序用法**: 查看有关使用的电子邮件应用程序的信息。 这包括每个应用的连接总数以及正在连接的 Outlook 的版本。  

**邮箱使用情况**: 查看邮箱的已用存储、配额消耗、项目计数和上次活动 (发送或读取活动) 的相关信息。

有关详细信息，请参阅以下资源：

- [Admin center 中的 office 365 报告-Office 365 组](https://go.microsoft.com/fwlink/p/?linkid=861610)

- [管理中心内的 Office 365 报告-电子邮件活动](https://go.microsoft.com/fwlink/p/?linkid=859706)

- [管理中心中的 Office 365 报表-电子邮件应用程序使用情况](https://go.microsoft.com/fwlink/p/?linkid=859707)

- [管理中心中的 Office 365 报表-邮箱使用情况](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的安全性 & 合规性报告

这些增强的报告为 EOP 管理员提供了交互式报告体验, 其中包括摘要信息, 以及深入了解更多详细信息的功能。  

**高级威胁防护 (ATP)**: 查看有关作为 ATP 一部分的安全链接和安全附件的信息。  

**EOP**: 查看组织中的恶意软件检测、欺骗邮件、垃圾邮件检测和邮件流的相关信息。  

[查看高级威胁防护和 Exchange Online Protection 报告](https://go.microsoft.com/fwlink/p/?linkid=852409)

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自定义报告

使用 Microsoft Graph 以编程方式创建 Microsoft 365 管理中心提供的报告。有关[在 Microsoft graph 中使用 Office 365 使用率报告](https://go.microsoft.com/fwlink/p/?linkid=865135)的主题

## <a name="custom-reports-using-reporting-web-services"></a>使用报告 Web 服务的自定义报告

使用 REST/ODATA2 查询筛选以编程方式从可用的 Exchange Online Protection PowerShell 报告 cmdlet 创建报告。

请参阅[Office 365 Reporting Web 服务](https://go.microsoft.com/fwlink/p/?LinkId=279926)

## <a name="message-trace"></a>Message trace

在电子邮件通过 EOP 时，追踪电子邮件信息。 您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。 它还显示邮件在到达其最终状态之前对邮件执行的操作。  

您可以使用此信息有效地回答用户的问题, 解决邮件流问题, 验证策略更改, 并缓解联系技术支持寻求帮助的需求。  

请参阅[跟踪电子](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)邮件

## <a name="audit-logging"></a>审核日志记录

跟踪管理员对您的组织做出的特定更改。 这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。 请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>报告和邮件跟踪数据的可用性与延迟

下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。
  
||||
|:-----|:-----|:-----|
|**报告类型**|**数据可用时间（回溯期）**|**延迟**|
|邮件保护摘要报告|90 天|邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。|
|邮件保护详细信息报告|90 天|对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。 <br/><br/> 若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。|
|邮件跟踪数据|90 天|对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。<br/><br/> 对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。|

> [!NOTE]
> 无论是通过 Microsoft 365 管理中心还是远程 PowerShell 请求, 数据可用性和延迟都是相同的。 
