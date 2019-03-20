---
title: Exchange Online Protection 中的报告和邮件跟踪
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。下表描述了 EOP 管理员可用的报告和故障排除工具。
ms.openlocfilehash: c26f3e88edb378f2eb9ae5967e96fadbce69110e
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693161"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="aeeab-105">Exchange Online Protection 中的报告和邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="aeeab-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="aeeab-106">Microsoft Exchange Online Protection (EOP) 提供许多不同的报告，可帮助您确定组织的总体状态和运行状况。</span><span class="sxs-lookup"><span data-stu-id="aeeab-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="aeeab-107">此外，还提供可帮助您解决特定事件（例如邮件没有到达目标收件人）的工具，以及协助满足合规性要求的审核报告。</span><span class="sxs-lookup"><span data-stu-id="aeeab-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="aeeab-108">使用率报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-108">Usage reports</span></span>

<span data-ttu-id="aeeab-109">**Office 365 组活动**查看有关创建和使用的 Office 365 组数量的信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="aeeab-110">**电子邮件活动**查看有关整个组织中发送、接收和读取的邮件数以及特定用户的信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="aeeab-111">**电子邮件应用程序使用**查看有关使用的电子邮件应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-111">**Email app usage** View information about the email apps that are used.</span></span> <span data-ttu-id="aeeab-112">这包括每个应用的连接总数以及正在连接的 Outlook 的版本。</span><span class="sxs-lookup"><span data-stu-id="aeeab-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="aeeab-113">**邮箱使用情况**查看邮箱的已用存储、配额消耗、项目计数和上次活动 (发送或读取活动) 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="aeeab-114">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="aeeab-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="aeeab-115">admin center 中的 office 365 报告-Office 365 组</span><span class="sxs-lookup"><span data-stu-id="aeeab-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="aeeab-116">管理中心内的 Office 365 报告-电子邮件活动</span><span class="sxs-lookup"><span data-stu-id="aeeab-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="aeeab-117">管理中心中的 Office 365 报表-电子邮件应用程序使用情况</span><span class="sxs-lookup"><span data-stu-id="aeeab-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="aeeab-118">管理中心中的 Office 365 报表-邮箱使用情况</span><span class="sxs-lookup"><span data-stu-id="aeeab-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a><span data-ttu-id="aeeab-119">Office &amp; 365 管理中心中的安全合规性报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-119">Security &amp; compliance reports in the Office 365 admin center</span></span>

<span data-ttu-id="aeeab-120">这些增强的报告为 EOP 管理员提供了交互式报告体验, 其中包括摘要信息, 以及深入了解更多详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="aeeab-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="aeeab-121">**高级威胁防护 (ATP)** 查看有关作为 ATP 一部分的安全链接和安全附件的信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="aeeab-122">**EOP**查看组织中的恶意软件检测、欺骗性邮件、垃圾邮件检测和邮件流的相关信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="aeeab-123">查看高级威胁防护和 Exchange Online Protection 报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="aeeab-124">使用 Microsoft Graph 的自定义报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="aeeab-125">使用 microsoft graph 以编程方式创建 office 365 管理中心提供的报告。有关[在 Microsoft graph 中使用 Office 365 使用率报告](https://go.microsoft.com/fwlink/p/?linkid=865135)的主题</span><span class="sxs-lookup"><span data-stu-id="aeeab-125">Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="aeeab-126">使用报告 Web 服务的自定义报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="aeeab-127">使用 REST/ODATA2 查询筛选以编程方式从可用的 Exchange Online Protection PowerShell 报告 cmdlet 创建报告。</span><span class="sxs-lookup"><span data-stu-id="aeeab-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="aeeab-128">请参阅[Office 365 Reporting Web 服务](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span><span class="sxs-lookup"><span data-stu-id="aeeab-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="aeeab-129">Message trace</span><span class="sxs-lookup"><span data-stu-id="aeeab-129">Message trace</span></span>

<span data-ttu-id="aeeab-130">在电子邮件通过 EOP 时，追踪电子邮件信息。</span><span class="sxs-lookup"><span data-stu-id="aeeab-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="aeeab-131">您可以确定电子邮件是否被接收、拒绝、延迟或由服务传递。</span><span class="sxs-lookup"><span data-stu-id="aeeab-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="aeeab-132">它还显示邮件在到达其最终状态之前对邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="aeeab-132">It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="aeeab-133">您可以使用此信息有效地回答用户的问题, 解决邮件流问题, 验证策略更改, 并缓解联系技术支持寻求帮助的需求。</span><span class="sxs-lookup"><span data-stu-id="aeeab-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="aeeab-134">请参阅[跟踪电子](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)邮件</span><span class="sxs-lookup"><span data-stu-id="aeeab-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="aeeab-135">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="aeeab-135">Audit logging</span></span>

<span data-ttu-id="aeeab-136">跟踪管理员对您的组织做出的特定更改。</span><span class="sxs-lookup"><span data-stu-id="aeeab-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="aeeab-137">这些报告可以帮助您解决配置问题或找到安全性或合规性相关问题的原因。</span><span class="sxs-lookup"><span data-stu-id="aeeab-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span>  <span data-ttu-id="aeeab-138">查看[EOP 中的审核报告](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="aeeab-138">see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="aeeab-139">报告和邮件跟踪数据的可用性与延迟</span><span class="sxs-lookup"><span data-stu-id="aeeab-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="aeeab-140">下表描述了 EOP 报告和邮件跟踪数据何时可用以及可用多长时间。</span><span class="sxs-lookup"><span data-stu-id="aeeab-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="aeeab-141">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="aeeab-141">**Report type**</span></span> <br/> |<span data-ttu-id="aeeab-142">**数据可用时间（回溯期）**</span><span class="sxs-lookup"><span data-stu-id="aeeab-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="aeeab-143">**延迟**</span><span class="sxs-lookup"><span data-stu-id="aeeab-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="aeeab-144">邮件保护摘要报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="aeeab-145">90 天</span><span class="sxs-lookup"><span data-stu-id="aeeab-145">90 days</span></span>  <br/> |<span data-ttu-id="aeeab-p106">邮件数据聚合将在 24-48 小时内基本完成。一些小的增量聚合更改可能最多需要 5 天。</span><span class="sxs-lookup"><span data-stu-id="aeeab-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="aeeab-148">邮件保护详细信息报告</span><span class="sxs-lookup"><span data-stu-id="aeeab-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="aeeab-149">90 天</span><span class="sxs-lookup"><span data-stu-id="aeeab-149">90 days</span></span>  <br/> |<span data-ttu-id="aeeab-p107">对于未超过 7 天的详细数据，数据应该会在 24 小时内出现，但可能需要在 48 小时后才会完整。一些小的增量更改可能最多需要 5 天才能出现。</span><span class="sxs-lookup"><span data-stu-id="aeeab-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="aeeab-152">若要查看关于超过 7 天的邮件的详细报告，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="aeeab-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="aeeab-153">邮件跟踪数据</span><span class="sxs-lookup"><span data-stu-id="aeeab-153">Message trace data</span></span>  <br/> |<span data-ttu-id="aeeab-154">90 天</span><span class="sxs-lookup"><span data-stu-id="aeeab-154">90 days</span></span>  <br/> |<span data-ttu-id="aeeab-155">对未超过 7 天的邮件运行邮件跟踪时，邮件应该会在 5-30 分钟内显示。</span><span class="sxs-lookup"><span data-stu-id="aeeab-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="aeeab-156">对超过 7 天的邮件运行邮件跟踪时，获取结果可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="aeeab-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="aeeab-157">无论是通过 Office 365 管理中心还是远程 PowerShell 请求, 数据可用性和延迟都是相同的。</span><span class="sxs-lookup"><span data-stu-id="aeeab-157">Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell.</span></span> 
  

