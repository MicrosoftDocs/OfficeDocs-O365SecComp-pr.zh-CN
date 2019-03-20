---
title: 查看 Office 365 高级威胁防护报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 了解如何在安全&amp;合规中心中查找和使用适用于 Office 365 高级威胁防护的报告。
ms.openlocfilehash: 3a128103d16ed03edb18becde96a5d20ee6eca9b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692401"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="be25b-103">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="be25b-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="be25b-104">如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(ATP), 并且您具有[必要的权限](#what-permissions-are-needed-to-view-these-reports), 则可以在安全&amp;合规中心中使用多个 ATP 报告。</span><span class="sxs-lookup"><span data-stu-id="be25b-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="be25b-105">(转到 "**报表** \> "**仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="be25b-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![安全&amp;合规中心仪表板可帮助您了解高级威胁防护的工作情况](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="be25b-107">atp 报告包括[威胁防护状态报告](#threat-protection-status-report)、 [atp 文件类型报告](#atp-file-types-report)和[atp 邮件处置报告](#atp-message-disposition-report)。</span><span class="sxs-lookup"><span data-stu-id="be25b-107">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report).</span></span> <span data-ttu-id="be25b-108">本文介绍 ATP 报告, 并包含指向[要查看的其他报告](#additional-reports-to-view)的链接。</span><span class="sxs-lookup"><span data-stu-id="be25b-108">This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="be25b-109">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="be25b-109">Threat Protection Status report</span></span>

<span data-ttu-id="be25b-110">**威胁防护状态**报告是一个视图, 它将有关检测到的恶意内容和恶意电子邮件的信息, 以及[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和 Office 365 ATP () 和[Office ATP](office-365-atp.md)结合在一起。</span><span class="sxs-lookup"><span data-stu-id="be25b-110">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="be25b-111">该报告提供了包含恶意内容 (文件或网站地址 (url)) 的独特电子邮件的聚合计数, 该邮件受反恶意软件引擎阻止、[零小时自动清除 (ZAP)](zero-hour-auto-purge.md)和 atp 功能, 如[atp 安全链接](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和[ATP 反网络钓鱼功能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="be25b-111">The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="be25b-112">拥有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) 的客户可以使用威胁防护状态报告;但是, 在 ATP 客户的威胁防护状态报告中显示的信息可能包含不同的 EOP 客户可能看到的数据。</span><span class="sxs-lookup"><span data-stu-id="be25b-112">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="be25b-113">例如, ATP 客户的威胁防护状态报告将包含有关[在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](atp-for-spo-odb-and-teams.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="be25b-113">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="be25b-114">此类信息特定于 ATP, 因此具有 EOP 但不是 ATP 的客户将不会在其威胁防护状态报告中看到这些详细信息。</span><span class="sxs-lookup"><span data-stu-id="be25b-114">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="be25b-115">若要查看威胁防护状态报告, 请在[安全&amp;合规性中心](https://protection.office.com)中转到 "**报告** \> "**仪表板** \> **威胁防护状态**。</span><span class="sxs-lookup"><span data-stu-id="be25b-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP 威胁防护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="be25b-117">若要获取一天的详细状态, 请将鼠标悬停在关系图上。</span><span class="sxs-lookup"><span data-stu-id="be25b-117">To get detailed status for a day, hover over the graph.</span></span>
  
![一天的 ATP 威胁防护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="be25b-119">默认情况下, 威胁防护状态报告显示过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="be25b-119">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="be25b-120">不过, 您可以选择 "**筛选器**" 并将日期范围更改为查看最多90天的数据。</span><span class="sxs-lookup"><span data-stu-id="be25b-120">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP 威胁防护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="be25b-122">您还可以使用 "**查看数据依据**" 菜单来更改报表中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="be25b-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![查看 ATP 威胁保护状态报告的选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="be25b-124">ATP 文件类型报告</span><span class="sxs-lookup"><span data-stu-id="be25b-124">ATP File Types report</span></span>

<span data-ttu-id="be25b-125">**atp 文件类型**报告显示通过[ATP 安全附件](atp-safe-attachments.md)检测为恶意的文件类型。</span><span class="sxs-lookup"><span data-stu-id="be25b-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="be25b-126">若要查看此报告, 请[在&amp;安全合规性中心](https://protection.office.com)中, 转到 "**报告** \> "**仪表板** \> **ATP 文件类型**。</span><span class="sxs-lookup"><span data-stu-id="be25b-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="be25b-128">当您将鼠标悬停在特定的一天时, 您可以看到由 Office 365 中的[ATP 安全附件](atp-safe-attachments.md)和[ &amp;反垃圾邮件反恶意软件保护](anti-spam-and-anti-malware-protection.md)检测到的恶意文件的类型细目。</span><span class="sxs-lookup"><span data-stu-id="be25b-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP 文件类型报告一天的数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="be25b-130">ATP 邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="be25b-130">ATP Message Disposition report</span></span>

<span data-ttu-id="be25b-131">**ATP 邮件处置**报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="be25b-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="be25b-132">若要查看此报告, 请[在&amp;安全合规性中心](https://protection.office.com)中, 转到 "**报告** \> "**仪表板** \> **ATP 邮件处置**。</span><span class="sxs-lookup"><span data-stu-id="be25b-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="be25b-134">当您将鼠标悬停在图表中的某条上时, 可以看到在那天中对检测到的电子邮件执行了哪些操作。</span><span class="sxs-lookup"><span data-stu-id="be25b-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![一天的 ATP 邮件处置报告数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="be25b-136">要查看的其他报告</span><span class="sxs-lookup"><span data-stu-id="be25b-136">Additional reports to view</span></span>

<span data-ttu-id="be25b-137">除了本文中介绍的 ATP 报告之外, 还有几个其他报告可供使用, 如下表所述:</span><span class="sxs-lookup"><span data-stu-id="be25b-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="be25b-138">报告类型</span><span class="sxs-lookup"><span data-stu-id="be25b-138">Report type</span></span>  |<span data-ttu-id="be25b-139">了解更多</span><span class="sxs-lookup"><span data-stu-id="be25b-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="be25b-140">**电子邮件安全报告**, 如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。</span><span class="sxs-lookup"><span data-stu-id="be25b-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="be25b-141">查看安全&amp;合规性中心中的电子邮件安全报告</span><span class="sxs-lookup"><span data-stu-id="be25b-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="be25b-142">**浏览器**(也称为 "威胁资源管理器", 它包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中)</span><span class="sxs-lookup"><span data-stu-id="be25b-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md))</span></span>     | [<span data-ttu-id="be25b-143">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="be25b-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="be25b-144">**EOP 和 ATP 结果**(这是使用 PowerShell 生成的自定义报表)。</span><span class="sxs-lookup"><span data-stu-id="be25b-144">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="be25b-145">此报告包含域、日期、事件类型、方向、操作和邮件计数等信息。</span><span class="sxs-lookup"><span data-stu-id="be25b-145">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="be25b-146">MailTrafficATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="be25b-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="be25b-147">**EOP 和 ATP 检测**(这是使用 PowerShell 生成的自定义报表)。</span><span class="sxs-lookup"><span data-stu-id="be25b-147">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="be25b-148">此报告包含有关电子邮件或文件中的恶意文件或 url、网络钓鱼企图、模拟和其他潜在威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="be25b-148">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="be25b-149">MailDetailATPReport cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="be25b-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="be25b-150">查看 ATP 报告所需的权限是什么？</span><span class="sxs-lookup"><span data-stu-id="be25b-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="be25b-151">为了查看和使用本文中介绍的报告,**必须为安全&amp;合规中心和 Exchange 管理中心分配适当的角色**。</span><span class="sxs-lookup"><span data-stu-id="be25b-151">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="be25b-152">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="be25b-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="be25b-153">组织管理</span><span class="sxs-lookup"><span data-stu-id="be25b-153">Organization Management</span></span>
    - <span data-ttu-id="be25b-154">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="be25b-154">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="be25b-155">安全读者</span><span class="sxs-lookup"><span data-stu-id="be25b-155">Security Reader</span></span>

- <span data-ttu-id="be25b-156">对于 exchange Online, 必须在 exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="be25b-156">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="be25b-157">组织管理</span><span class="sxs-lookup"><span data-stu-id="be25b-157">Organization Management</span></span>
    - <span data-ttu-id="be25b-158">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="be25b-158">View-only Organization Management</span></span>
    - <span data-ttu-id="be25b-159">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="be25b-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="be25b-160">合规性管理</span><span class="sxs-lookup"><span data-stu-id="be25b-160">Compliance Management</span></span>

<span data-ttu-id="be25b-161">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="be25b-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="be25b-162">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="be25b-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="be25b-163">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="be25b-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="be25b-164">如果报告不显示数据, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="be25b-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="be25b-165">如果您未在 ATP 报告中看到数据, 请仔细检查您的策略设置是否正确。</span><span class="sxs-lookup"><span data-stu-id="be25b-165">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="be25b-166">您的组织必须定义[atp 安全链接策略](set-up-atp-safe-links-policies.md)和[atp 安全附件策略](set-up-atp-safe-attachments-policies.md), 以便将 ATP 保护设置到位。</span><span class="sxs-lookup"><span data-stu-id="be25b-166">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="be25b-167">另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="be25b-167">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="be25b-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="be25b-168">Related topics</span></span>

[<span data-ttu-id="be25b-169">Office 365 安全&amp;合规中心中的报告和见解</span><span class="sxs-lookup"><span data-stu-id="be25b-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="be25b-170">在安全&amp;合规中心中创建报表的日程安排</span><span class="sxs-lookup"><span data-stu-id="be25b-170">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="be25b-171">在安全&amp;合规中心中设置和下载自定义报告</span><span class="sxs-lookup"><span data-stu-id="be25b-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

