---
title: Exchange Online Protection 中的报告和邮件跟踪
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。下表描述了 EOP 管理员可用的报告和故障排除工具。
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027139"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection 中的报告和邮件跟踪

Microsoft Exchange Online Protection (EOP) 提供了许多不同的报表，可帮助您确定的总体状态和组织的运行状况。还有工具，可帮助您解决特定事件 （如消息未到达到其预期接收人），并审核报告以帮助合规性要求。 

## <a name="usage-reports"></a>使用率报告

**Office 365 组活动**查看有关创建和使用 Office 365 组数的信息。  

**电子邮件活动**查看有关发送、 接收和阅读在整个组织，以及通过特定用户的消息数的信息。  

**电子邮件应用程序使用率**查看有关所使用的电子邮件应用程序的信息。这包括每个应用程序的连接总数以及进行连接的 Outlook 版本。  

**邮箱使用情况**查看有关使用存储的信息、 配额消耗、 项目计数和邮箱的最后一次活动 （发送或读取的活动）。

请参阅以下资源的详细信息：

- [管理中心-Office 365 组中的 office 365 报告](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [管理中心-电子邮件活动中的 office 365 报告](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [在管理中心内的电子邮件应用程序使用率的 office 365 报告](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [在管理中心内的邮箱使用情况的 office 365 报告](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a>安全&amp;在 Office 365 管理中心中的合规性报告

这些增强的报告提供交互式的报告体验对于 EOP 管理员，其中包括摘要信息，并能够向下钻取的详细信息。  

**高级威胁保护 (ATP)** 查看有关安全链接和安全附件 ATP 一部分的信息。  

**EOP**查看关于恶意软件检测、 带欺骗性的邮件、 垃圾邮件检测和与您的组织的邮件流的信息。  

[高级威胁保护和 Exchange Online Protection 查看报告](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自定义报告

以编程方式创建报告中可用的 Office 365 管理中心内使用 Microsoft Graph 请参阅[使用在 Microsoft Graph 中的 Office 365 使用率报告](https://go.microsoft.com/fwlink/p/?linkid=865135)的副标题 

##<a name="custom-reports-using-reporting-web-services"></a>使用报告 Web 服务的自定义报告

以编程方式从可用 Exchange Online Protection PowerShell 中使用 REST/ODATA2 查询筛选报告 cmdlet 创建报告。

请参阅[Office 365 报告 Web 服务](https://go.microsoft.com/fwlink/p/?LinkId=279926) 

##<a name="message-trace"></a>邮件跟踪

通过 EOP 中传输，如下所示电子邮件。您可以确定一封电子邮件是否已收到、 拒绝、 延迟，或由服务发送。它还会显示其达到其最终状态之前，对邮件采取了哪些操作。  

您可以使用此信息来高效地回答您的用户、 邮件流疑难解答、 验证策略更改，减轻与技术支持联系以寻求帮助。  

请参阅[跟踪电子邮件](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx) 

## <a name="audit-logging"></a>审核日志记录

跟踪特定对您的组织管理员所做的更改。这些报告可帮助您解决配置问题或查找安全性或合规性相关问题的原因。 请参阅[在 EOP 中的审核报告](auditing-reports-in-eop.md) 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a>报告和邮件跟踪数据的可用性与延迟

下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。
  
||||
|:-----|:-----|:-----|
|**报告类型** <br/> |**数据可用时间（回溯期）** <br/> |**延迟** <br/> |
|邮件保护摘要报告  <br/> |90 天  <br/> |邮件数据聚合在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。  <br/> |
|邮件保护详细报告  <br/> |90 天  <br/> |对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。  <br/> 若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。  <br/> |
|邮件跟踪数据  <br/> |90 天  <br/> |对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。  <br/> 对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。  <br/> |
   
> [!NOTE]
> 数据可用性和延迟是相同的是否通过 Office 365 管理中心或远程 PowerShell 请求。 
  

