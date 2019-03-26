---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
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
ms.openlocfilehash: 202898873bb9611c747aed335d295c749c7cd0fa
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30732255"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="6751f-103">在安全&amp;合规中心中使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="6751f-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="6751f-104">如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md), 并且您具有所需的权限, 则可以使用威胁资源管理器来确定和分析威胁。</span><span class="sxs-lookup"><span data-stu-id="6751f-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), and you have the necessary permissions, you can use Threat Explorer to identify and analyze threats.</span></span> <span data-ttu-id="6751f-105">例如, 您可以识别和删除已传递的恶意电子邮件, 或查看 Office 365 安全功能捕获的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="6751f-105">For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features.</span></span> <span data-ttu-id="6751f-106">威胁资源管理器 (也称为浏览器) 是一种功能强大的近实时工具, 可帮助安全操作团队在安全&amp;合规中心中调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="6751f-106">Threat Explorer (also referred to as Explorer) is a powerful near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span>
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="6751f-108">若要使用资源管理器, &amp;请在安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6751f-109">office 365 威胁智能现已成为 office 365 高级威胁防护计划 2, 以及其他威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="6751f-109">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="6751f-110">若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="6751f-110">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="6751f-111">Explorer 概述</span><span class="sxs-lookup"><span data-stu-id="6751f-111">Explorer overview</span></span>

<span data-ttu-id="6751f-112">如果您的组织具有[Office 365 威胁调查和响应功能](office-365-ti.md)(这包括在 ATP 计划2中), 并且您具有必要的权限, 则可以使用威胁浏览器 (也称为 "资源管理器") 来识别和分析威胁。</span><span class="sxs-lookup"><span data-stu-id="6751f-112">If your organization has [Office 365 Threat investigation and response capabilities](office-365-ti.md) (this is included in ATP Plan 2), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="6751f-113">(在安全&amp;合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。)</span><span class="sxs-lookup"><span data-stu-id="6751f-113">(In the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="6751f-115">本文介绍了您可以使用资源管理器执行的几项操作 (还有更多可能):</span><span class="sxs-lookup"><span data-stu-id="6751f-115">This article describes a few things you can do with Explorer (there are many more possibilities):</span></span>

- <span data-ttu-id="6751f-116">[查看在电子邮件中检测到的恶意软件](#see-malware-detected-in-email-by-technology), 以及威胁防护技术 (反恶意软件保护、ATP 安全附件等)</span><span class="sxs-lookup"><span data-stu-id="6751f-116">[See what kinds of malware were detected in email](#see-malware-detected-in-email-by-technology), and by threat protection technology (anti-malware protection, ATP Safe Attachments, etc.)</span></span>

- <span data-ttu-id="6751f-117">[查看有关仿冒链接 (url) 的数据](#view-data-about-phishing-urls-and-click-verdict), 以及单击 verdicts 的内容 (阻止、允许或访问的 url (无论是警告)</span><span class="sxs-lookup"><span data-stu-id="6751f-117">[View data about phishing links (URLs)](#view-data-about-phishing-urls-and-click-verdict), and what the click verdicts were (URLs blocked, allowed, or visited despite warnings)</span></span>

- <span data-ttu-id="6751f-118">[查看被报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子](#review-email-messages-reported-by-users)邮件, 并确定任何趋势 (例如, 报告为网络钓鱼的邮件数大于常规邮件数)</span><span class="sxs-lookup"><span data-stu-id="6751f-118">[Review email messages that were reported as Junk, Not Junk, or Phishing](#review-email-messages-reported-by-users), and identify any trends (such as a larger than usual number of messages reported as Phish)</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="6751f-119">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="6751f-119">See malware detected in email by technology</span></span>

<span data-ttu-id="6751f-120">假设您想要查看在电子邮件中检测到的恶意软件, 以及 Office 365 中的哪种技术。</span><span class="sxs-lookup"><span data-stu-id="6751f-120">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="6751f-121">为此, 请使用资源管理器的[电子邮件 > 恶意软件](threat-explorer-views.md#email--malware)视图。</span><span class="sxs-lookup"><span data-stu-id="6751f-121">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="6751f-122">在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-122">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="6751f-123">在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-123">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="6751f-124">![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-124">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="6751f-125">单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-125">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="6751f-126">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6751f-126">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="6751f-127">![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-127">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="6751f-128">选择一个选项, 然后单击 "刷新" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="6751f-128">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="6751f-130">报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="6751f-130">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="6751f-131">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="6751f-131">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="6751f-132">查看有关仿冒 url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="6751f-132">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="6751f-133">假设您要查看通过电子邮件中的 url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="6751f-133">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="6751f-134">为此, 请使用资源管理器的[电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish)视图。</span><span class="sxs-lookup"><span data-stu-id="6751f-134">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="6751f-135">在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-135">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="6751f-136">在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-136">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="6751f-137">![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-137">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="6751f-138">单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="6751f-138">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="6751f-139">选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击 "**刷新**" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="6751f-139">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="6751f-140">![url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-140">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="6751f-141">报告将刷新以显示检测到的电子邮件中被阻止的仿冒 url (或在出现警告的情况下访问) 以及电子邮件传递状态。</span><span class="sxs-lookup"><span data-stu-id="6751f-141">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="6751f-142">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="6751f-142">From here, you can conduct further analysis.</span></span> <span data-ttu-id="6751f-143">例如, 在图表下方, 您可以看到在组织的电子邮件中被阻止的最高 url。</span><span class="sxs-lookup"><span data-stu-id="6751f-143">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![阻止的资源管理器 url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="6751f-145">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="6751f-145">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="6751f-146">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="6751f-146">Review email messages reported by users</span></span>

<span data-ttu-id="6751f-147">假设您要查看组织中的用户通过使用[Outlook 和 web 上的 outlook 的报告消息外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6751f-147">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="6751f-148">为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图。</span><span class="sxs-lookup"><span data-stu-id="6751f-148">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="6751f-149">在 "Office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-149">In the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="6751f-150">在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-150">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="6751f-151">![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-151">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="6751f-152">单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="6751f-152">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="6751f-153">选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="6751f-153">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="6751f-154">![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="6751f-154">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="6751f-155">报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="6751f-155">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="6751f-156">您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6751f-156">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="theres-more"></a><span data-ttu-id="6751f-157">还有更多!</span><span class="sxs-lookup"><span data-stu-id="6751f-157">There's more!</span></span>

<span data-ttu-id="6751f-158">除了本文中介绍的三个方案之外, 您还可以使用浏览器中提供的多种报告方案。</span><span class="sxs-lookup"><span data-stu-id="6751f-158">In addition to the three scenarios outlined in this article, you have many reporting scenarios available with Explorer.</span></span> <span data-ttu-id="6751f-159">以下是几个更多示例:</span><span class="sxs-lookup"><span data-stu-id="6751f-159">Here are a few more examples:</span></span>

- [<span data-ttu-id="6751f-160">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="6751f-160">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)

- [<span data-ttu-id="6751f-161">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="6751f-161">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

- [<span data-ttu-id="6751f-162">获取有关威胁资源管理器中的视图的概述</span><span class="sxs-lookup"><span data-stu-id="6751f-162">Get an overview of the views in Threat Explorer</span></span>](threat-explorer-views.md)

## <a name="how-to-get-explorer"></a><span data-ttu-id="6751f-163">如何获取资源管理器</span><span class="sxs-lookup"><span data-stu-id="6751f-163">How to get Explorer</span></span>

<span data-ttu-id="6751f-164">资源管理器包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中。</span><span class="sxs-lookup"><span data-stu-id="6751f-164">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="6751f-165">若要查看和使用资源管理器, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="6751f-165">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="6751f-166">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="6751f-166">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="6751f-167">组织管理</span><span class="sxs-lookup"><span data-stu-id="6751f-167">Organization Management</span></span>
    - <span data-ttu-id="6751f-168">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="6751f-168">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="6751f-169">安全读者</span><span class="sxs-lookup"><span data-stu-id="6751f-169">Security Reader</span></span>

- <span data-ttu-id="6751f-170">对于 exchange Online, 必须在 exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="6751f-170">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="6751f-171">组织管理</span><span class="sxs-lookup"><span data-stu-id="6751f-171">Organization Management</span></span>
    - <span data-ttu-id="6751f-172">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="6751f-172">View-only Organization Management</span></span>
    - <span data-ttu-id="6751f-173">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="6751f-173">View-Only Recipients role</span></span>
    - <span data-ttu-id="6751f-174">合规性管理</span><span class="sxs-lookup"><span data-stu-id="6751f-174">Compliance Management</span></span>

<span data-ttu-id="6751f-175">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="6751f-175">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="6751f-176">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="6751f-176">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="6751f-177">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="6751f-177">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="related-topics"></a><span data-ttu-id="6751f-178">相关主题</span><span class="sxs-lookup"><span data-stu-id="6751f-178">Related topics</span></span>

- [<span data-ttu-id="6751f-179">自动化调查和响应 (空中)</span><span class="sxs-lookup"><span data-stu-id="6751f-179">Automated Investigation and Response (AIR)</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="6751f-180">威胁资源管理器视图</span><span class="sxs-lookup"><span data-stu-id="6751f-180">Threat Explorer views</span></span>](threat-explorer-views.md)

- [<span data-ttu-id="6751f-181">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="6751f-181">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
