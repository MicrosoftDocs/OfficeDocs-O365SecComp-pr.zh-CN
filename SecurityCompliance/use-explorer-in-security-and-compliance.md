---
title: 在安全&amp;合规中心中使用威胁资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/31/2019
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
ms.openlocfilehash: c782e5962164b7d35947befe526c20f7dc0943d5
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264688"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="a8604-103">在安全&amp;合规中心中使用威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="a8604-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="a8604-104">如果您的组织具有[Office 365 高级威胁防护计划 2](office-365-ti.md) (ATP), 并且您具有所需的权限, 则可以使用威胁资源管理器 (也称为 "资源管理器") 来确定和分析威胁。</span><span class="sxs-lookup"><span data-stu-id="a8604-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md) (ATP), and you have the necessary permissions, you can use Threat Explorer (also referred to as Explorer) to identify and analyze threats.</span></span> <span data-ttu-id="a8604-105">(若要使用资源管理器, &amp;请在安全合规中心中, 转到 "**威胁管理** \> **资源管理器**"。)</span><span class="sxs-lookup"><span data-stu-id="a8604-105">(To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.)</span></span>

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="a8604-107">资源管理器是一种功能强大的近实时工具, 可帮助安全操作团队调查和响应安全&amp;合规性中心中的威胁。</span><span class="sxs-lookup"><span data-stu-id="a8604-107">Explorer is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="a8604-108">下面是您可以执行的一些操作:</span><span class="sxs-lookup"><span data-stu-id="a8604-108">Here are some of the things you can do:</span></span>
- [<span data-ttu-id="a8604-109">查看 Office 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="a8604-109">See malware that was detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="a8604-110">查看有关仿冒 url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="a8604-110">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- [<span data-ttu-id="a8604-111">从资源管理器中的视图启动自动调查和响应过程</span><span class="sxs-lookup"><span data-stu-id="a8604-111">Start an automated investigation and response process from a view in Explorer</span></span>](#start-automated-investigation-and-response)
- <span data-ttu-id="a8604-112">...[更多](#more-ways-to-use-explorer)!</span><span class="sxs-lookup"><span data-stu-id="a8604-112">... [and more](#more-ways-to-use-explorer)!</span></span>

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="a8604-113">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="a8604-113">See malware detected in email by technology</span></span>

<span data-ttu-id="a8604-114">假设您想要查看在电子邮件中检测到的恶意软件, 以及 Office 365 中的哪种技术。</span><span class="sxs-lookup"><span data-stu-id="a8604-114">Suppose you want to see malware that was detected in email, and by what technology in Office 365.</span></span> <span data-ttu-id="a8604-115">为此, 请使用资源管理器的[电子邮件 > 恶意软件](threat-explorer-views.md#email--malware)视图。</span><span class="sxs-lookup"><span data-stu-id="a8604-115">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer.</span></span>

1. <span data-ttu-id="a8604-116">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-116">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a8604-117">在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-117">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="a8604-118">![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-118">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>
3. <span data-ttu-id="a8604-119">单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-119">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="a8604-120">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="a8604-120">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="a8604-121">![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-121">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 
4. <span data-ttu-id="a8604-122">选择一个选项, 然后单击 "刷新" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="a8604-122">Select an option, and then click the Refresh button to apply that filter.</span></span><br/>![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

<span data-ttu-id="a8604-124">报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="a8604-124">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="a8604-125">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="a8604-125">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="a8604-126">查看有关仿冒 url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="a8604-126">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="a8604-127">假设您要查看通过电子邮件中的 url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 url 的列表。</span><span class="sxs-lookup"><span data-stu-id="a8604-127">Suppose you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span>  <span data-ttu-id="a8604-128">若要标识所单击的 url, 则需要[ATP 安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a8604-128">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md).</span></span> <span data-ttu-id="a8604-129">(请确保已将[atp 安全链接策略](set-up-atp-safe-links-policies.md)设置并应用到用户的单击时保护和日志记录的单击 verdicts 依据 ATP 安全链接。)若要查看邮件中的网络钓鱼 url 并单击网络钓鱼邮件中的 url, 请使用资源管理器的[电子邮件 > 网络钓鱼](threat-explorer-views.md#email--phish)视图。</span><span class="sxs-lookup"><span data-stu-id="a8604-129">(Make sure you have set up and applied [ATP Safe Links policies](set-up-atp-safe-links-policies.md) to your users for click-time protection and logging of click verdicts by ATP Safe Links.) To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer.</span></span>

1. <span data-ttu-id="a8604-130">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-130">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a8604-131">在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-131">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="a8604-132">![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-132">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>
3. <span data-ttu-id="a8604-133">单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="a8604-133">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>
4. <span data-ttu-id="a8604-134">选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击 "**刷新**" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="a8604-134">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="a8604-135">![url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-135">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

<span data-ttu-id="a8604-136">在下面的 "URL" 选项卡上, 报告将刷新以显示两个不同的 URL 表:</span><span class="sxs-lookup"><span data-stu-id="a8604-136">The report refreshes to show two different URL tables on the URL tab below:</span></span>
1. <span data-ttu-id="a8604-137">**上面的 url**是您已筛选出的邮件中包含的 url, 并且每个 URL 的电子邮件传递操作都会计数。</span><span class="sxs-lookup"><span data-stu-id="a8604-137">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="a8604-138">在网络钓鱼电子邮件视图中, 此列表通常包含合法的 url。</span><span class="sxs-lookup"><span data-stu-id="a8604-138">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="a8604-139">攻击者在其邮件中加入了好和坏的 url, 以尝试传递它们, 但它们会使用户更有趣地单击恶意链接。</span><span class="sxs-lookup"><span data-stu-id="a8604-139">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they'll make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="a8604-140">url 表按总电子邮件计数进行排序 (注意: 此列不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="a8604-140">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>
2. <span data-ttu-id="a8604-141">单击 "**上**一条" 可将已单击的安全链接包装的 url 按总点击次数排序 (此列也不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="a8604-141">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="a8604-142">"总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。</span><span class="sxs-lookup"><span data-stu-id="a8604-142">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="a8604-143">在网络钓鱼电子邮件视图中, 这些链接通常是可疑或恶意链接, 但可能包含出现在网络钓鱼邮件中的清理 url。</span><span class="sxs-lookup"><span data-stu-id="a8604-143">In the phish email view, these will more often be suspicious or malicious links, but could include clean URLs that happen to be in phish messages.</span></span> <span data-ttu-id="a8604-144">URL 单击未打开的链接将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="a8604-144">URL clicks on unwrapped links will not show up here.</span></span>

<span data-ttu-id="a8604-145">这两个 url 表通过传递状态显示网页仿冒电子邮件中的主要 url, 并显示已阻止 (或在出现警告的情况下访问) 的 url 单击, 以便您可以了解用户收到的潜在的错误链接以及用户的交互情况。</span><span class="sxs-lookup"><span data-stu-id="a8604-145">The two URLs tables show top URLs in phishing emails by delivery status, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="a8604-146">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="a8604-146">From here, you can conduct further analysis.</span></span> <span data-ttu-id="a8604-147">例如, 在图表下方, 您可以看到在组织的环境中被阻止的电子邮件中的最高 url。</span><span class="sxs-lookup"><span data-stu-id="a8604-147">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span> 

![阻止的资源管理器 url](media/ExplorerPhishClickVerdictURLs.png) 

<span data-ttu-id="a8604-149">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="a8604-149">Select a URL to view more detailed information.</span></span> <span data-ttu-id="a8604-150">请注意, 在 "URL 飞出" 对话框中, 将删除对电子邮件的筛选, 以向您显示完整的 URL 在您的环境中的公开视图。</span><span class="sxs-lookup"><span data-stu-id="a8604-150">Note that in the URL flyout dialog, the filtering on emails is removed in order to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="a8604-151">这样, 您就可以在资源管理器中筛选出您关注的电子邮件, 查找潜在威胁的特定 url, 然后展开您对环境中的 url 公开的了解 (通过 URL 详细信息对话框), 而无需将 url 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="a8604-151">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="a8604-152">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8604-152">Review email messages reported by users</span></span>

<span data-ttu-id="a8604-153">假设您要查看组织中的用户通过使用[Outlook 和 web 上的 outlook 的报告消息外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8604-153">Suppose you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="a8604-154">为此, 请使用[电子邮件 >](threat-explorer-views.md#email--user-reported)浏览器的用户报告视图。</span><span class="sxs-lookup"><span data-stu-id="a8604-154">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer.</span></span>

1. <span data-ttu-id="a8604-155">在 "安全 & 合规性中心[https://protection.office.com](https://protection.office.com)()" 中, 选择 "**威胁管理** > **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-155">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer**.</span></span>
2. <span data-ttu-id="a8604-156">在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-156">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="a8604-157">![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-157">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>
3. <span data-ttu-id="a8604-158">单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="a8604-158">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>
4. <span data-ttu-id="a8604-159">选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="a8604-159">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="a8604-160">![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="a8604-160">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="a8604-161">报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="a8604-161">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="a8604-162">您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a8604-162">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="a8604-163">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="a8604-163">Start automated investigation and response</span></span>

<span data-ttu-id="a8604-164">(新!)[自动调查和响应](automated-investigation-response-office.md)(最近添加到 ATP 计划 2) 可以在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。</span><span class="sxs-lookup"><span data-stu-id="a8604-164">(NEW!) [Automated investigation and response](automated-investigation-response-office.md), recently added to ATP Plan 2, can save your security operations team a lot of time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="a8604-165">除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="a8604-165">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="a8604-166">有关此操作的详细信息, 请参阅[示例: 安全管理员可触发来自威胁资源管理器的调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="a8604-166">For details on this, see [Example: A security administrator triggers an investigation from Threat Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer"></a><span data-ttu-id="a8604-167">使用资源管理器的更多方法</span><span class="sxs-lookup"><span data-stu-id="a8604-167">More ways to use Explorer</span></span>

<span data-ttu-id="a8604-168">除了本文中介绍的方案, 您还可以使用浏览器中提供的更多报告选项。</span><span class="sxs-lookup"><span data-stu-id="a8604-168">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer.</span></span> 
- [<span data-ttu-id="a8604-169">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8604-169">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="a8604-170">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="a8604-170">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="a8604-171">获取有关威胁资源管理器中的视图的概述</span><span class="sxs-lookup"><span data-stu-id="a8604-171">Get an overview of the views in Threat Explorer</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="a8604-172">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="a8604-172">Required licenses and permissions</span></span>

<span data-ttu-id="a8604-173">资源管理器包含在[Office 365 高级威胁防护计划 2](office-365-ti.md)中。</span><span class="sxs-lookup"><span data-stu-id="a8604-173">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="a8604-174">若要查看和使用资源管理器, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="a8604-174">To view and use Explorer, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="a8604-175">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="a8604-175">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="a8604-176">组织管理</span><span class="sxs-lookup"><span data-stu-id="a8604-176">Organization Management</span></span>
    - <span data-ttu-id="a8604-177">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="a8604-177">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="a8604-178">安全读者</span><span class="sxs-lookup"><span data-stu-id="a8604-178">Security Reader</span></span>

- <span data-ttu-id="a8604-179">对于 exchange Online, 必须在 exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="a8604-179">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="a8604-180">组织管理</span><span class="sxs-lookup"><span data-stu-id="a8604-180">Organization Management</span></span>
    - <span data-ttu-id="a8604-181">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="a8604-181">View-only Organization Management</span></span>
    - <span data-ttu-id="a8604-182">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="a8604-182">View-Only Recipients role</span></span>
    - <span data-ttu-id="a8604-183">合规性管理</span><span class="sxs-lookup"><span data-stu-id="a8604-183">Compliance Management</span></span>

<span data-ttu-id="a8604-184">若要了解有关角色和权限的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="a8604-184">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="a8604-185">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="a8604-185">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="a8604-186">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="a8604-186">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
