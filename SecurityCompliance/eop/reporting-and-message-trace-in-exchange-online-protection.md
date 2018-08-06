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
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="81679-105">Exchange Online Protection 中的报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="81679-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="81679-p102">Microsoft Exchange Online Protection (EOP) 提供了许多不同的报表，可帮助您确定的总体状态和组织的运行状况。还有工具，可帮助您解决特定事件 （如消息未到达到其预期接收人），并审核报告以帮助合规性要求。</span><span class="sxs-lookup"><span data-stu-id="81679-p102">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="81679-108">使用率报告</span><span class="sxs-lookup"><span data-stu-id="81679-108">Usage reports</span></span>

<span data-ttu-id="81679-109">**Office 365 组活动**查看有关创建和使用 Office 365 组数的信息。</span><span class="sxs-lookup"><span data-stu-id="81679-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="81679-110">**电子邮件活动**查看有关发送、 接收和阅读在整个组织，以及通过特定用户的消息数的信息。</span><span class="sxs-lookup"><span data-stu-id="81679-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="81679-p103">**电子邮件应用程序使用率**查看有关所使用的电子邮件应用程序的信息。这包括每个应用程序的连接总数以及进行连接的 Outlook 版本。</span><span class="sxs-lookup"><span data-stu-id="81679-p103">**Email app usage** View information about the email apps that are used. This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="81679-113">**邮箱使用情况**查看有关使用存储的信息、 配额消耗、 项目计数和邮箱的最后一次活动 （发送或读取的活动）。</span><span class="sxs-lookup"><span data-stu-id="81679-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="81679-114">请参阅以下资源的详细信息：</span><span class="sxs-lookup"><span data-stu-id="81679-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="81679-115">管理中心-Office 365 组中的 office 365 报告</span><span class="sxs-lookup"><span data-stu-id="81679-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="81679-116">管理中心-电子邮件活动中的 office 365 报告</span><span class="sxs-lookup"><span data-stu-id="81679-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="81679-117">在管理中心内的电子邮件应用程序使用率的 office 365 报告</span><span class="sxs-lookup"><span data-stu-id="81679-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="81679-118">在管理中心内的邮箱使用情况的 office 365 报告</span><span class="sxs-lookup"><span data-stu-id="81679-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a><span data-ttu-id="81679-119">安全&amp;在 Office 365 管理中心中的合规性报告</span><span class="sxs-lookup"><span data-stu-id="81679-119">Security &amp; compliance reports in the Office 365 admin center</span></span>

<span data-ttu-id="81679-120">这些增强的报告提供交互式的报告体验对于 EOP 管理员，其中包括摘要信息，并能够向下钻取的详细信息。</span><span class="sxs-lookup"><span data-stu-id="81679-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="81679-121">**高级威胁保护 (ATP)** 查看有关安全链接和安全附件 ATP 一部分的信息。</span><span class="sxs-lookup"><span data-stu-id="81679-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="81679-122">**EOP**查看关于恶意软件检测、 带欺骗性的邮件、 垃圾邮件检测和与您的组织的邮件流的信息。</span><span class="sxs-lookup"><span data-stu-id="81679-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="81679-123">高级威胁保护和 Exchange Online Protection 查看报告</span><span class="sxs-lookup"><span data-stu-id="81679-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="81679-124">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="81679-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="81679-125">以编程方式创建报告中可用的 Office 365 管理中心内使用 Microsoft Graph 请参阅[使用在 Microsoft Graph 中的 Office 365 使用率报告](https://go.microsoft.com/fwlink/p/?linkid=865135)的副标题</span><span class="sxs-lookup"><span data-stu-id="81679-125">Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="81679-126">使用报告 Web 服务的自定义报告</span><span class="sxs-lookup"><span data-stu-id="81679-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="81679-127">以编程方式从可用 Exchange Online Protection PowerShell 中使用 REST/ODATA2 查询筛选报告 cmdlet 创建报告。</span><span class="sxs-lookup"><span data-stu-id="81679-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="81679-128">请参阅[Office 365 报告 Web 服务](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="81679-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="81679-129">邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="81679-129">Message trace</span></span>

<span data-ttu-id="81679-p104">通过 EOP 中传输，如下所示电子邮件。您可以确定一封电子邮件是否已收到、 拒绝、 延迟，或由服务发送。它还会显示其达到其最终状态之前，对邮件采取了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="81679-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="81679-133">您可以使用此信息来高效地回答您的用户、 邮件流疑难解答、 验证策略更改，减轻与技术支持联系以寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="81679-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="81679-134">请参阅[跟踪电子邮件](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span><span class="sxs-lookup"><span data-stu-id="81679-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="81679-135">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="81679-135">Audit logging</span></span>

<span data-ttu-id="81679-p105">跟踪特定对您的组织管理员所做的更改。这些报告可帮助您解决配置问题或查找安全性或合规性相关问题的原因。 请参阅[在 EOP 中的审核报告](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="81679-p105">Tracks specific changes made by admins to your organization. These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.  see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="81679-139">报告和邮件跟踪数据的可用性与延迟</span><span class="sxs-lookup"><span data-stu-id="81679-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="81679-140">下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。</span><span class="sxs-lookup"><span data-stu-id="81679-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="81679-141">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="81679-141">**Report type**</span></span> <br/> |<span data-ttu-id="81679-142">**数据可用时间（回溯期）**</span><span class="sxs-lookup"><span data-stu-id="81679-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="81679-143">**延迟**</span><span class="sxs-lookup"><span data-stu-id="81679-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="81679-144">邮件保护摘要报告</span><span class="sxs-lookup"><span data-stu-id="81679-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="81679-145">90 天</span><span class="sxs-lookup"><span data-stu-id="81679-145">90 days</span></span>  <br/> |<span data-ttu-id="81679-p106">邮件数据聚合在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。</span><span class="sxs-lookup"><span data-stu-id="81679-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="81679-148">邮件保护详细报告</span><span class="sxs-lookup"><span data-stu-id="81679-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="81679-149">90 天</span><span class="sxs-lookup"><span data-stu-id="81679-149">90 days</span></span>  <br/> |<span data-ttu-id="81679-p107">对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。</span><span class="sxs-lookup"><span data-stu-id="81679-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="81679-152">若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="81679-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="81679-153">邮件跟踪数据</span><span class="sxs-lookup"><span data-stu-id="81679-153">Message trace data</span></span>  <br/> |<span data-ttu-id="81679-154">90 天</span><span class="sxs-lookup"><span data-stu-id="81679-154">90 days</span></span>  <br/> |<span data-ttu-id="81679-155">对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="81679-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="81679-156">对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="81679-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="81679-157">数据可用性和延迟是相同的是否通过 Office 365 管理中心或远程 PowerShell 请求。</span><span class="sxs-lookup"><span data-stu-id="81679-157">Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell.</span></span> 
  

