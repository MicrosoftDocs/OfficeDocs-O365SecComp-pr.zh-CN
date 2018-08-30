---
title: Office 365 高级威胁保护的视图报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 08/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 了解如何查找和使用适用于 Office 365 高级威胁保护安全中报告&amp;合规性中心。
ms.openlocfilehash: bd02989711629cc67f7a7d5e061862a1146ff21b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525236"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="61eea-103">Office 365 高级威胁保护的视图报告</span><span class="sxs-lookup"><span data-stu-id="61eea-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="61eea-p101">如果您的组织具有[Office 365 高级威胁保护](office-365-atp.md)(ATP)，并且您所需的权限，可以使用中安全性的几个 ATP 报表&amp;合规性中心。(请转到**报告** \> **仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="61eea-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the necessary permissions, you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="61eea-p102">ATP 报告包括[威胁保护状态报告](view-reports-for-atp.md#advancedthreats)、 [ATP 文件类型报告](view-reports-for-atp.md#atpfiletypes)和[ATP 消息处置报告](view-reports-for-atp.md#atpmessagedisp)。本文介绍 ATP 报告，并包括指向[其他报告以查看](view-reports-for-atp.md#addl)。</span><span class="sxs-lookup"><span data-stu-id="61eea-p102">ATP reports include the [Threat protection status report](view-reports-for-atp.md#advancedthreats), the [ATP File Types report](view-reports-for-atp.md#atpfiletypes), and the [ATP Message Disposition report](view-reports-for-atp.md#atpmessagedisp). This article describes the ATP reports and includes links to [Additional reports to view](view-reports-for-atp.md#addl).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="61eea-109">威胁保护状态报告</span><span class="sxs-lookup"><span data-stu-id="61eea-109">Threat protection status report</span></span>

<span data-ttu-id="61eea-p103">**威胁保护状态**报告是融合恶意内容和恶意邮件检测和阻止的 Exchange Online 和高级威胁保护信息的单个视图。该报告提供聚合带有反恶意软件引擎、[零时差自动清除 (ZAP)](zero-hour-auto-purge.md)，请和高级威胁保护功能，如[ATP 安全链接](atp-safe-links.md)， [ATP 阻止恶意内容 （文件或 Url） 的唯一电子邮件数安全附件](atp-safe-attachments.md)，和[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="61eea-p103">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).</span></span>
  
<span data-ttu-id="61eea-112">若要查看安全威胁保护状态报告，&amp;合规性中心中，转到**报告** \> **仪表板** \> **威胁保护状态**。</span><span class="sxs-lookup"><span data-stu-id="61eea-112">To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![ATP 威胁保护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="61eea-114">获取一天，悬停在此图详细的状态。</span><span class="sxs-lookup"><span data-stu-id="61eea-114">To get detailed status for a day, hover over the graph.</span></span>
  
![一天的 ATP 威胁保护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="61eea-p104">默认情况下威胁保护状态报告将显示数据的过去七天。但是，您可以选择**筛选器**，并更改要查看最多为 90 天的数据的日期范围。</span><span class="sxs-lookup"><span data-stu-id="61eea-p104">By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP 威胁保护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="61eea-119">您还可以使用**通过查看数据**菜单更改报表中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="61eea-119">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![查看 ATP 威胁保护状态报表选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="61eea-121">ATP 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="61eea-121">ATP File Types report</span></span>

<span data-ttu-id="61eea-122">**ATP 文件类型**报告将显示为恶意检测到[ATP 安全附件](atp-safe-attachments.md)的文件的类型。</span><span class="sxs-lookup"><span data-stu-id="61eea-122">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="61eea-123">若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **ATP 文件类型**。</span><span class="sxs-lookup"><span data-stu-id="61eea-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="61eea-125">当鼠标悬停在某一天时，您可以看到通过[ATP 安全附件](atp-safe-attachments.md)检测到的恶意文件类型的细分结构和[反垃圾邮件&amp;Office 365 中的反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="61eea-125">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![一天的 ATP 文件类型报告数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="61eea-127">ATP 消息处置报告</span><span class="sxs-lookup"><span data-stu-id="61eea-127">ATP Message Disposition report</span></span>

<span data-ttu-id="61eea-128">**ATP 消息处置**报告将显示您的电子邮件被检测为具有恶意内容所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="61eea-128">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="61eea-129">若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **ATP 消息处置**。</span><span class="sxs-lookup"><span data-stu-id="61eea-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="61eea-131">当鼠标悬停在图表中的栏时，您可以看到的这一天为检测到的电子邮件执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="61eea-131">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![ATP 消息处置报告一天的数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="61eea-133">若要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="61eea-133">Additional reports to view</span></span>

<span data-ttu-id="61eea-p105">除了本文中所述的 ATP 报告，[电子邮件安全报告](view-email-security-reports.md)可安全&amp;合规性中心。电子邮件安全报告包括[前发件人和收件人报告](view-email-security-reports.md#top-senders-and-recipients-report)、[欺骗邮件报告](view-email-security-reports.md#spoof-mail-report)、[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)，等等。</span><span class="sxs-lookup"><span data-stu-id="61eea-p105">In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.</span></span>
  
<span data-ttu-id="61eea-136">如果您的组织具有[Office 365 威胁智能](office-365-ti.md)，也可以[使用资源管理器中的安全中&amp;合规性中心](use-explorer-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="61eea-136">And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).</span></span>
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="61eea-137">查看这些报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="61eea-137">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="61eea-138">为了查看和使用本文中所述的电子邮件安全报告，您必须具有安全中分配相应角色&amp;合规性中心和 Exchange Admin Center。</span><span class="sxs-lookup"><span data-stu-id="61eea-138">In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="61eea-139">**角色组**</span><span class="sxs-lookup"><span data-stu-id="61eea-139">**Role group**</span></span>|<span data-ttu-id="61eea-140">**其中分配**</span><span class="sxs-lookup"><span data-stu-id="61eea-140">**Where assigned**</span></span>|<span data-ttu-id="61eea-141">**了解更多**</span><span class="sxs-lookup"><span data-stu-id="61eea-141">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="61eea-142">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="61eea-142">One of the following:</span></span>  <br/>  <span data-ttu-id="61eea-143">组织管理</span><span class="sxs-lookup"><span data-stu-id="61eea-143">Organization Management</span></span>  <br/>  <span data-ttu-id="61eea-144">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="61eea-144">Security Administrator</span></span>  <br/>  <span data-ttu-id="61eea-145">安全读者</span><span class="sxs-lookup"><span data-stu-id="61eea-145">Security Reader</span></span>  <br/> |<span data-ttu-id="61eea-146">安全&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="61eea-146">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="61eea-147">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="61eea-147">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="61eea-148">以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="61eea-148">One of the following:</span></span>  <br/>  <span data-ttu-id="61eea-149">组织管理</span><span class="sxs-lookup"><span data-stu-id="61eea-149">Organization Management</span></span>  <br/>  <span data-ttu-id="61eea-150">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="61eea-150">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="61eea-151">仅查看收件人角色</span><span class="sxs-lookup"><span data-stu-id="61eea-151">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="61eea-152">遵从性管理</span><span class="sxs-lookup"><span data-stu-id="61eea-152">Compliance Management</span></span>  <br/> |<span data-ttu-id="61eea-153">Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="61eea-153">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="61eea-154">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="61eea-154">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="61eea-155">如果报表不显示数据？</span><span class="sxs-lookup"><span data-stu-id="61eea-155">What if the reports aren't showing data?</span></span>

<span data-ttu-id="61eea-p106">如果您不会在报表中看到数据，请仔细检查您的策略设置正确。您的组织必须[ATP 安全链接策略](set-up-atp-safe-links-policies.md)和[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)ATP 保护的订单中定义，以准备就绪。另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="61eea-p106">If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="61eea-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="61eea-159">Related topics</span></span>

[<span data-ttu-id="61eea-160">报告和 Office 365 安全性见解&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="61eea-160">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="61eea-161">在安全中创建报表的计划&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="61eea-161">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="61eea-162">设置和下载安全中的自定义报表&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="61eea-162">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

