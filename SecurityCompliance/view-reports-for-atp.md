---
title: Office 365 高级威胁保护的视图报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 了解如何查找和使用适用于 Office 365 高级威胁保护安全中报告&amp;合规性中心。
ms.openlocfilehash: e9d3088f81d1020e70de4c2260fba81cd469715d
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706316"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="d83f0-103">Office 365 高级威胁保护的视图报告</span><span class="sxs-lookup"><span data-stu-id="d83f0-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="d83f0-p101">如果您的组织具有[Office 365 高级威胁保护](office-365-atp.md)(ATP)，并且您[所需的权限](#what-permissions-are-needed-to-view-these-reports)，可以使用中安全性的几个 ATP 报表&amp;合规性中心。(请转到**报告** \> **仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="d83f0-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="d83f0-p102">ATP 报告包括[威胁保护状态报告](#threat-protection-status-report)、 [ATP 文件类型报告](#atp-file-types-report)和[ATP 消息处置报告](#atp-message-disposition-report)。本文介绍 ATP 报告，并包括指向[其他报告以查看](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="d83f0-109">威胁保护状态报告</span><span class="sxs-lookup"><span data-stu-id="d83f0-109">Threat Protection Status report</span></span>

<span data-ttu-id="d83f0-p103">**威胁保护状态**报告是融合信息恶意内容和恶意邮件检测和[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)被阻止的单个视图。该报告提供聚合带有反恶意软件引擎、[零时差自动清除 (ZAP)](zero-hour-auto-purge.md)，请和 ATP 功能，如[ATP 安全链接](atp-safe-links.md)， [ATP 安全阻止恶意内容 （文件或网站地址 (Url)） 的唯一电子邮件数附件](atp-safe-attachments.md)，和[ATP 防钓鱼功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d83f0-p104">威胁保护状态报告是适用于[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); 客户但是，ATP 客户威胁保护状态报告中显示的信息将可能包含比 EOP 客户可能会看到不同的数据。例如，ATP 客户的威胁保护状态报告将包含有关[SharePoint Online、 OneDrive 或的 Microsoft 团队中检测到恶意文件](atp-for-spo-odb-and-teams.md)的信息。此类信息是特定于 ATP，，因此客户拥有 EOP，但不是 ATP 将不会看到其威胁保护状态报告中的这些信息。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="d83f0-115">若要查看中威胁保护状态报告，[安全&amp;合规性中心](https://security.microsoft.com)，请转到**报告** \> **仪表板** \> **威胁保护状态**。</span><span class="sxs-lookup"><span data-stu-id="d83f0-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP 威胁保护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="d83f0-117">获取一天，悬停在此图详细的状态。</span><span class="sxs-lookup"><span data-stu-id="d83f0-117">To get detailed status for a day, hover over the graph.</span></span>
  
![一天的 ATP 威胁保护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="d83f0-p105">默认情况下威胁保护状态报告将显示数据的过去七天。但是，您可以选择**筛选器**，并更改要查看最多为 90 天的数据的日期范围。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP 威胁保护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="d83f0-122">您还可以使用**通过查看数据**菜单更改报表中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="d83f0-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![查看 ATP 威胁保护状态报表选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="d83f0-124">ATP 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="d83f0-124">ATP File Types report</span></span>

<span data-ttu-id="d83f0-125">**ATP 文件类型**报告将显示为恶意检测到[ATP 安全附件](atp-safe-attachments.md)的文件的类型。</span><span class="sxs-lookup"><span data-stu-id="d83f0-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="d83f0-126">若要查看此报告中，在[安全&amp;合规性中心](https://security.microsoft.com)，请转到**报告** \> **仪表板** \> **ATP 文件类型**。</span><span class="sxs-lookup"><span data-stu-id="d83f0-126">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="d83f0-128">当鼠标悬停在某一天时，您可以看到通过[ATP 安全附件](atp-safe-attachments.md)检测到的恶意文件类型的细分结构和[反垃圾邮件&amp;Office 365 中的反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d83f0-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![一天的 ATP 文件类型报告数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="d83f0-130">ATP 消息处置报告</span><span class="sxs-lookup"><span data-stu-id="d83f0-130">ATP Message Disposition report</span></span>

<span data-ttu-id="d83f0-131">**ATP 消息处置**报告将显示您的电子邮件被检测为具有恶意内容所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="d83f0-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="d83f0-132">若要查看此报告中，在[安全&amp;合规性中心](https://security.microsoft.com)，请转到**报告** \> **仪表板** \> **ATP 消息处置**。</span><span class="sxs-lookup"><span data-stu-id="d83f0-132">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="d83f0-134">当鼠标悬停在图表中的栏时，您可以看到的这一天为检测到的电子邮件执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="d83f0-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![ATP 消息处置报告一天的数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="d83f0-136">若要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="d83f0-136">Additional reports to view</span></span>

<span data-ttu-id="d83f0-137">除了本文中所述的 ATP 报告，多个其他报表有下, 表中所述：</span><span class="sxs-lookup"><span data-stu-id="d83f0-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>


|<span data-ttu-id="d83f0-138">报告类型</span><span class="sxs-lookup"><span data-stu-id="d83f0-138">Report type</span></span>  |<span data-ttu-id="d83f0-139">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="d83f0-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="d83f0-140">**电子邮件安全报告**，如前发件人和收件人报告、 欺骗邮件报表和垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="d83f0-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="d83f0-141">查看安全中的电子邮件安全报告&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="d83f0-142">**资源管理器**（也称为威胁资源管理器，这包含在[Office 365 威胁智能](office-365-ti.md)）</span><span class="sxs-lookup"><span data-stu-id="d83f0-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="d83f0-143">在安全中使用资源管理器&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="d83f0-p106">**EOP 和 ATP 结果**（这是通过使用 PowerShell 生成自定义报告）。此报告包含信息，如域、 日期、 事件类型、 方向、 操作和消息计数。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="d83f0-146">Get MailTrafficATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="d83f0-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="d83f0-p107">**EOP 和 ATP 检测**（这是通过使用 PowerShell 生成自定义报告）。此报告包含有关恶意文件或 Url、 网络钓鱼尝试、 模拟，和电子邮件或文件中的其他潜在威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="d83f0-149">Get MailDetailATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="d83f0-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="d83f0-150">查看 ATP 报告需要哪些权限？</span><span class="sxs-lookup"><span data-stu-id="d83f0-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="d83f0-151">为了查看和使用本文中所述的报告，您必须具有适当的角色分配中的安全性&amp;合规性中心和 Exchange Admin Center。</span><span class="sxs-lookup"><span data-stu-id="d83f0-151">In order to view and use the reports described in this article, you must have an appropriate role assigned in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>

- <span data-ttu-id="d83f0-152">安全&amp;合规性中心，您必须拥有以下角色分配之一：</span><span class="sxs-lookup"><span data-stu-id="d83f0-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="d83f0-153">组织管理</span><span class="sxs-lookup"><span data-stu-id="d83f0-153">Organization Management</span></span>
    - <span data-ttu-id="d83f0-154">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="d83f0-154">Security Administrator</span></span>
    - <span data-ttu-id="d83f0-155">安全读者</span><span class="sxs-lookup"><span data-stu-id="d83f0-155">Security Reader</span></span>

- <span data-ttu-id="d83f0-156">有关 Exchange Online 中，必须具有以下角色分配之一：</span><span class="sxs-lookup"><span data-stu-id="d83f0-156">For Exchange Online, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="d83f0-157">组织管理</span><span class="sxs-lookup"><span data-stu-id="d83f0-157">Organization Management</span></span>
    - <span data-ttu-id="d83f0-158">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="d83f0-158">View-only Organization Management</span></span>
    - <span data-ttu-id="d83f0-159">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="d83f0-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="d83f0-160">合规性管理</span><span class="sxs-lookup"><span data-stu-id="d83f0-160">Compliance Management</span></span>

<span data-ttu-id="d83f0-161">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="d83f0-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="d83f0-162">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="d83f0-163">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="d83f0-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d83f0-164">如果报表不显示数据？</span><span class="sxs-lookup"><span data-stu-id="d83f0-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d83f0-p108">如果您看不到数据 ATP 报告中，请仔细检查您的策略设置正确。您的组织必须[ATP 安全链接策略](set-up-atp-safe-links-policies.md)和[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)ATP 保护的订单中定义，以准备就绪。另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d83f0-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d83f0-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="d83f0-168">Related topics</span></span>

[<span data-ttu-id="d83f0-169">报告和 Office 365 安全性见解&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d83f0-170">在安全中创建报表的计划&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-170">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="d83f0-171">设置和下载安全中的自定义报表&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="d83f0-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

