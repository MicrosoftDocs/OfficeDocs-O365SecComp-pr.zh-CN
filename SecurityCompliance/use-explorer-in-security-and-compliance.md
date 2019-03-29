---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/28/2019
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
ms.openlocfilehash: e6177970edc67c8b9e1c0ae6144f4c37f116012f
ms.sourcegitcommit: 787a0fef671e5dc6f5e805b580321b2edbfad8e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30989607"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="1788e-103">在安全&amp;合规中心中使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="1788e-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="1788e-104">如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md) (ATP), 并且您具有所需的权限, 则可以使用威胁资源管理器 (也称为 "资源管理器") 来确定和分析威胁。</span><span class="sxs-lookup"><span data-stu-id="1788e-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="1788e-105">(若要使用资源管理器, &amp;请在安全合规中心中, 转到 "**威胁管理** \> **资源管理器**"。)</span><span class="sxs-lookup"><span data-stu-id="1788e-105">(To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="1788e-107">资源管理器是一种功能强大的近实时工具, 可帮助安全操作团队调查和响应安全&amp;合规性中心中的威胁。</span><span class="sxs-lookup"><span data-stu-id="1788e-107">Explorer is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1788e-108">下面是您可以执行的一些操作:</span><span class="sxs-lookup"><span data-stu-id="1788e-108">Here are some of the things you can do:</span></span>
- [<span data-ttu-id="1788e-109">查看 Office 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="1788e-109">See malware that was detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="1788e-110">查看有关仿冒 url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="1788e-110">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- [<span data-ttu-id="1788e-111">从资源管理器中的视图启动自动调查和响应过程</span><span class="sxs-lookup"><span data-stu-id="1788e-111">Start an automated investigation and response process from a view in Explorer</span></span>](#start-automated-investigation-and-response)
- <span data-ttu-id="1788e-112">...[更多](#more-ways-to-use-explorer)!</span><span class="sxs-lookup"><span data-stu-id="1788e-112">... [and more](#more-ways-to-use-explorer)!</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="1788e-113">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="1788e-113">See malware detected in email by technology</span></span>

<span data-ttu-id="1788e-114">假设您想要查看在电子邮件中检测到的恶意软件, 以及 Office 365 中的哪种技术。</span><span class="sxs-lookup"><span data-stu-id="1788e-114">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="1788e-115">为此, 请使用资源管理器的[电子邮件 > 恶意软件](threat-explorer-views.md#email--malware)视图。</span><span class="sxs-lookup"><span data-stu-id="1788e-115">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="1788e-116">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-116">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="1788e-117">在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-117">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="1788e-118">![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-118">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="1788e-119">单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-119">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="1788e-120">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="1788e-120">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="1788e-121">![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-121">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="1788e-122">选择一个选项, 然后单击 "刷新" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="1788e-122">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="1788e-124">报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="1788e-124">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="1788e-125">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="1788e-125">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="1788e-126">查看有关仿冒 url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="1788e-126">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="1788e-127">假设您要查看通过电子邮件中的 url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="1788e-127">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="1788e-128">为此, 请使用资源管理器的[电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish)视图。</span><span class="sxs-lookup"><span data-stu-id="1788e-128">To do this, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="1788e-129">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-129">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="1788e-130">在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-130">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="1788e-131">![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-131">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="1788e-132">单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="1788e-132">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="1788e-133">选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击 "**刷新**" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="1788e-133">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="1788e-134">![url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-134">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="1788e-135">报告将刷新以显示检测到的电子邮件中被阻止的仿冒 url (或在出现警告的情况下访问) 以及电子邮件传递状态。</span><span class="sxs-lookup"><span data-stu-id="1788e-135">The report refreshes to show detected phishing URLs in email that were blocked (or visited despite a warning), along with email delivery status.</span></span> <span data-ttu-id="1788e-136">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="1788e-136">From here, you can conduct further analysis.</span></span> <span data-ttu-id="1788e-137">例如, 在图表下方, 您可以看到在组织的电子邮件中被阻止的最高 url。</span><span class="sxs-lookup"><span data-stu-id="1788e-137">For example, below the chart, you can see the top URLs that were blocked in your organization's email.</span></span> 

![阻止的资源管理器 url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="1788e-139">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="1788e-139">Select a URL to view more detailed information.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="1788e-140">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1788e-140">Review email messages reported by users</span></span>

<span data-ttu-id="1788e-141">假设您要查看组织中的用户通过使用[Outlook 和 web 上的 outlook 的报告消息外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1788e-141">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="1788e-142">为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图。</span><span class="sxs-lookup"><span data-stu-id="1788e-142">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="1788e-143">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-143">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="1788e-144">在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-144">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="1788e-145">![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-145">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="1788e-146">单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="1788e-146">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="1788e-147">选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1788e-147">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="1788e-148">![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="1788e-148">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="1788e-149">报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="1788e-149">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="1788e-150">您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1788e-150">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="1788e-151">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="1788e-151">Start automated investigation and response</span></span>

<span data-ttu-id="1788e-152">(新!)[自动调查和响应](automated-investigation-response-office.md)(最近添加到 ATP 计划 2) 可以在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。</span><span class="sxs-lookup"><span data-stu-id="1788e-152">(NEW!) [Automated investigation and response](automated-investigation-response-office.md), recently added to ATP Plan 2, can save your security operations team a lot of time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="1788e-153">除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="1788e-153">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="1788e-154">有关此操作的详细信息, 请参阅[示例: 安全管理员可触发来自威胁资源管理器的调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1788e-154">For details on this, see [Example: A security administrator triggers an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer"></a><span data-ttu-id="1788e-155">使用资源管理器的更多方法</span><span class="sxs-lookup"><span data-stu-id="1788e-155">More ways to use Explorer</span></span>

<span data-ttu-id="1788e-156">除了本文中介绍的方案, 您还可以使用浏览器中提供的更多报告选项。</span><span class="sxs-lookup"><span data-stu-id="1788e-156">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer.</span></span> 
- [<span data-ttu-id="1788e-157">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="1788e-157">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="1788e-158">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="1788e-158">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="1788e-159">获取有关威胁资源管理器中的视图的概述</span><span class="sxs-lookup"><span data-stu-id="1788e-159">Get an overview of the views in Threat Explorer</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="1788e-160">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="1788e-160">Required licenses and permissions</span></span>

<span data-ttu-id="1788e-161">资源管理器包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中。</span><span class="sxs-lookup"><span data-stu-id="1788e-161">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="1788e-162">若要查看和使用资源管理器, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="1788e-162">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="1788e-163">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="1788e-163">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="1788e-164">组织管理</span><span class="sxs-lookup"><span data-stu-id="1788e-164">Organization Management</span></span>
    - <span data-ttu-id="1788e-165">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="1788e-165">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="1788e-166">安全读者</span><span class="sxs-lookup"><span data-stu-id="1788e-166">Security Reader</span></span>

- <span data-ttu-id="1788e-167">对于 exchange Online, 必须在 exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="1788e-167">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="1788e-168">组织管理</span><span class="sxs-lookup"><span data-stu-id="1788e-168">Organization Management</span></span>
    - <span data-ttu-id="1788e-169">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="1788e-169">View-only Organization Management</span></span>
    - <span data-ttu-id="1788e-170">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="1788e-170">View-Only Recipients role</span></span>
    - <span data-ttu-id="1788e-171">合规性管理</span><span class="sxs-lookup"><span data-stu-id="1788e-171">Compliance Management</span></span>

<span data-ttu-id="1788e-172">若要了解有关角色和权限的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="1788e-172">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="1788e-173">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1788e-173">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="1788e-174">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="1788e-174">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
