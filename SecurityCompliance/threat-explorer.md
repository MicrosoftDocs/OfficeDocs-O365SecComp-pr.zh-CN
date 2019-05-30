---
title: 威胁浏览器 (和实时检测)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: 了解安全&amp;合规性中心中的资源管理器 (和实时检测)。
ms.openlocfilehash: 030f866c5e86daa3dc543bddae7152e19f377d3b
ms.sourcegitcommit: 6c0fcb82178a4ac26375545f328389a6852a81be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34490528"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="cdda2-103">威胁浏览器 (和实时检测)</span><span class="sxs-lookup"><span data-stu-id="cdda2-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="cdda2-104">如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(OFFICE 365 ATP), 并且您拥有[必要的权限](#required-licenses-and-permissions), 则您可以使用**资源管理器**或**实时检测**(以前的*实时报告*)。[请参阅新增功能](#new-features-in-real-time-detections)!</span><span class="sxs-lookup"><span data-stu-id="cdda2-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly *real-time reports* — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="cdda2-105">在 "安全 & 合规性中心" 中, 转到 "**威胁管理**", 然后选择 "**浏览器**" 或 "**实时检测**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="cdda2-106">在 ATP 计划2中, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="cdda2-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="cdda2-107">在 ATP 计划1中, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="cdda2-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![威胁资源管理器](media/threatmgmt-explorer.png)      |![实时检测](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="cdda2-110">使用浏览器 (或实时检测) 时, 您将拥有一个强大的报告, 使安全操作团队能够有效地调查威胁并对其做出响应, 这与以下图像类似:</span><span class="sxs-lookup"><span data-stu-id="cdda2-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="cdda2-112">使用此报告, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cdda2-112">With this report, you can:</span></span>
- [<span data-ttu-id="cdda2-113">查看 Office 365 安全功能检测到的恶意软件</span><span class="sxs-lookup"><span data-stu-id="cdda2-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- [<span data-ttu-id="cdda2-114">查看有关仿冒 Url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="cdda2-114">View data about phishing URLs and click verdict</span></span>](#view-data-about-phishing-urls-and-click-verdict)
- <span data-ttu-id="cdda2-115">[从资源管理器中的视图启动自动调查和响应过程](#start-automated-investigation-and-response)(仅 ATP 计划 2)</span><span class="sxs-lookup"><span data-stu-id="cdda2-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="cdda2-116">...[调查恶意电子邮件,](#more-ways-to-use-explorer-or-real-time-detections)等等!</span><span class="sxs-lookup"><span data-stu-id="cdda2-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="cdda2-117">实时检测中的新功能</span><span class="sxs-lookup"><span data-stu-id="cdda2-117">New features in real-time detections</span></span>

<span data-ttu-id="cdda2-118">对于 Office 365 ATP 计划1客户,*实时检测*报告以前称为 "*实时报告*"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-118">For Office 365 ATP Plan 1 customers, the *real-time detections* report was previously referred to as *real-time reports*.</span></span> <span data-ttu-id="cdda2-119">除了名称更改之外, 还有几个新的功能和增强功能可供推出:</span><span class="sxs-lookup"><span data-stu-id="cdda2-119">In addition to the name change, several new features and enhancements are rolling out:</span></span>

- <span data-ttu-id="cdda2-120">在网络钓鱼视图中, 可以通过[ATP 安全链接](atp-safe-links.md)查看检测到的 url 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="cdda2-120">In the Phish view, you can see more details about detected URLs through [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="cdda2-121">新的详细信息和功能包括:</span><span class="sxs-lookup"><span data-stu-id="cdda2-121">New details and capabilities include:</span></span>
  - <span data-ttu-id="cdda2-122">电子邮件中的 Url</span><span class="sxs-lookup"><span data-stu-id="cdda2-122">URLs in email messages</span></span>
  - <span data-ttu-id="cdda2-123">基于 URL 信息筛选</span><span class="sxs-lookup"><span data-stu-id="cdda2-123">Filtering based on URL information</span></span>
  - <span data-ttu-id="cdda2-124">数据图形中显示的 URL 信息</span><span class="sxs-lookup"><span data-stu-id="cdda2-124">URL information displayed in data graphs</span></span>
  - <span data-ttu-id="cdda2-125">单击时间有关在邮件中单击的数据</span><span class="sxs-lookup"><span data-stu-id="cdda2-125">Time-of-click data about clicks in messages</span></span>

- <span data-ttu-id="cdda2-126">只要 URL 中的更改, 请单击 "判定", 您就会看到一个警告。</span><span class="sxs-lookup"><span data-stu-id="cdda2-126">Whenever there's a change in a URL click verdict, you'll see an alert.</span></span> <span data-ttu-id="cdda2-127">URL 单击 "verdicts" 可以在 URL 沙箱后更改, 或者由 ATP 安全链接保护的用户覆盖[Atp 安全链接警告](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-127">URL click verdicts can change when a URL’s reputation changes post-detonation, or when a user who's protected by ATP Safe Links overrides an [ATP Safe Links warning](atp-safe-links-warning-pages.md).</span></span>  
 
<span data-ttu-id="cdda2-128">通过这些增强功能, 贵组织的安全管理员可以查看比以前更多的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cdda2-128">These enhancements enable your organization's security administrators to view more details than before.</span></span> <span data-ttu-id="cdda2-129">安全管理员可以查看有关 URL 域、未接 Url、单击 "verdicts" 等信息, 然后相应地调整 Office 365 ATP 策略。</span><span class="sxs-lookup"><span data-stu-id="cdda2-129">Security administrators can view information about URL domains, missed URLs, click verdicts, and more, and then adjust Office 365 ATP policies appropriately.</span></span>

> [!NOTE]
> <span data-ttu-id="cdda2-130">当这些功能处于预览阶段时, URL 数据将在有限的天数内可用。</span><span class="sxs-lookup"><span data-stu-id="cdda2-130">While these features are in preview, URL data will be available for a limited number of days.</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="cdda2-131">查看电子邮件中的技术检测到恶意软件</span><span class="sxs-lookup"><span data-stu-id="cdda2-131">See malware detected in email by technology</span></span>

<span data-ttu-id="cdda2-132">假设您想要查看 Office 365 技术在电子邮件中检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="cdda2-132">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="cdda2-133">为此, 请使用资源管理器 (或实时检测) 的[电子邮件 _GT_ 恶意软件](threat-explorer-views.md#email--malware)视图。</span><span class="sxs-lookup"><span data-stu-id="cdda2-133">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="cdda2-134">在 "安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**" (或 "**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="cdda2-134">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="cdda2-135">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="cdda2-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="cdda2-136">在 "**视图**" 菜单中, 选择 "**电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-136">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="cdda2-137">![浏览器的视图菜单](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-137">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="cdda2-138">单击 "**发件人**", 然后选择 "**基本** > **检测技术**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-138">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="cdda2-139">您的检测技术现在可用作报告的筛选器。</span><span class="sxs-lookup"><span data-stu-id="cdda2-139">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="cdda2-140">![恶意软件检测技术](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-140">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="cdda2-141">选择一个选项, 然后单击 "**刷新**" 按钮以应用该筛选器。</span><span class="sxs-lookup"><span data-stu-id="cdda2-141">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="cdda2-142">![选定的检测技术](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-142">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="cdda2-143">报告将刷新, 以显示使用您选择的技术选项在电子邮件中检测到恶意软件的结果。</span><span class="sxs-lookup"><span data-stu-id="cdda2-143">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="cdda2-144">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="cdda2-144">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="cdda2-145">查看有关仿冒 Url 的数据, 然后单击 "判定"</span><span class="sxs-lookup"><span data-stu-id="cdda2-145">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="cdda2-146">假定您要查看通过电子邮件中的 Url 进行的网络钓鱼尝试, 包括允许、阻止和重写的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="cdda2-146">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="cdda2-147">标识所单击的 Url 需要配置[ATP 安全链接](atp-safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-147">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="cdda2-148">确保已为单击时的保护设置了[Atp 安全链接策略](set-up-atp-safe-links-policies.md), 然后通过 ATP 安全链接单击 "verdicts" 进行日志记录。</span><span class="sxs-lookup"><span data-stu-id="cdda2-148">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="cdda2-149">若要查看邮件中的网络钓鱼 Url 并单击网络钓鱼邮件中的 Url, 请使用[电子邮件 _GT_ 网络钓鱼](threat-explorer-views.md#email--phish)视图 (或实时检测)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-149">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="cdda2-150">在 "安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**" (或 "**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="cdda2-150">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="cdda2-151">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="cdda2-151">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="cdda2-152">在 "**视图**" 菜单中, 选择 "**电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-152">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="cdda2-153">![浏览器的视图菜单](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-153">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="cdda2-154">单击 "**发件人**", 然后选择 " **url** > **" 单击 "判定"**。</span><span class="sxs-lookup"><span data-stu-id="cdda2-154">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="cdda2-155">选择一个或多个选项 (如 "已**阻止**" 和 "**阻止被覆盖**"), 然后单击与应用该筛选器的选项位于同一行中的 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="cdda2-155">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="cdda2-156">(不要刷新浏览器窗口。)</span><span class="sxs-lookup"><span data-stu-id="cdda2-156">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="cdda2-157">![Url 并单击 "verdicts"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-157">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="cdda2-158">报告将刷新, 以在报告下的 "URL" 选项卡上显示两个不同的 URL 表:</span><span class="sxs-lookup"><span data-stu-id="cdda2-158">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="cdda2-159">**上面的 url**是您已筛选出的邮件中包含的 url, 并且每个 URL 的电子邮件传递操作都会计数。</span><span class="sxs-lookup"><span data-stu-id="cdda2-159">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="cdda2-160">在网络钓鱼电子邮件视图中, 此列表通常包含合法的 Url。</span><span class="sxs-lookup"><span data-stu-id="cdda2-160">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="cdda2-161">攻击者在其邮件中加入了好和坏的 Url, 以尝试传递它们, 但它们会使用户更有趣地单击恶意链接。</span><span class="sxs-lookup"><span data-stu-id="cdda2-161">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="cdda2-162">Url 表按总电子邮件计数进行排序 (注意: 此列不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-162">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="cdda2-163">单击 "**上**一条" 可将已单击的安全链接包装的 url 按总点击次数排序 (此列也不显示为简化视图)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-163">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="cdda2-164">"总计计数依据" 列指示安全链接单击每个单击的 URL 的 "已判定计数"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-164">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="cdda2-165">在网络钓鱼电子邮件视图中, 这通常是可疑或恶意的 Url, 但可能包含网络钓鱼邮件中的干净 Url。</span><span class="sxs-lookup"><span data-stu-id="cdda2-165">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="cdda2-166">URL 单击未打开的链接将不会显示在此处。</span><span class="sxs-lookup"><span data-stu-id="cdda2-166">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="cdda2-167">这两个 Url 表通过传递操作和位置显示网络钓鱼电子邮件中的前几个 Url, 并显示已阻止 (或在出现警告的情况下访问) 的 URL 单击, 以便您可以了解用户收到的潜在错误链接以及用户的交互情况。</span><span class="sxs-lookup"><span data-stu-id="cdda2-167">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="cdda2-168">在这里, 你可以进行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="cdda2-168">From here, you can conduct further analysis.</span></span> <span data-ttu-id="cdda2-169">例如, 在图表下方, 您可以看到在组织的环境中被阻止的电子邮件中的最高 Url。</span><span class="sxs-lookup"><span data-stu-id="cdda2-169">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![阻止的资源管理器 Url](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="cdda2-171">选择一个 URL 以查看更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="cdda2-171">Select a URL to view more detailed information.</span></span> <span data-ttu-id="cdda2-172">请注意, 在 "URL 飞出" 对话框中, 将删除对电子邮件的筛选, 以向您显示在您的环境中 URL 公开的完整视图。</span><span class="sxs-lookup"><span data-stu-id="cdda2-172">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="cdda2-173">这样, 您就可以在资源管理器中筛选出您关注的电子邮件, 查找潜在威胁的特定 Url, 然后展开您对环境中的 URL 公开的了解 (通过 URL 详细信息对话框), 而无需将 URL 筛选器添加到资源管理器视图本身。</span><span class="sxs-lookup"><span data-stu-id="cdda2-173">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="cdda2-174">查看用户报告的电子邮件</span><span class="sxs-lookup"><span data-stu-id="cdda2-174">Review email messages reported by users</span></span>

<span data-ttu-id="cdda2-175">假设您想要查看您的组织中的用户使用[Outlook 和 web 上的 outlook 的报告邮件外接程序](enable-the-report-message-add-in.md)报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="cdda2-175">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="cdda2-176">为此, 请使用[电子邮件 _GT_ 用户报告](threat-explorer-views.md#email--user-reported)的浏览器 (或实时检测) 视图。</span><span class="sxs-lookup"><span data-stu-id="cdda2-176">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="cdda2-177">在 "安全 & 合规中心 ([https://protection.office.com](https://protection.office.com))" 中, 选择 "**威胁管理** > **资源管理器**" (或 "**实时检测**")。</span><span class="sxs-lookup"><span data-stu-id="cdda2-177">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="cdda2-178">(此示例使用 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="cdda2-178">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="cdda2-179">在 "**视图**" 菜单中, 选择 "**电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-179">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="cdda2-180">![浏览器的视图菜单](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-180">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="cdda2-181">单击 "**发件人**", 然后选择 "**基本** > **报告类型**"。</span><span class="sxs-lookup"><span data-stu-id="cdda2-181">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="cdda2-182">选择一个选项, 如 "**网络钓鱼**", 然后单击 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="cdda2-182">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="cdda2-183">![用户报告的网络钓鱼](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="cdda2-183">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="cdda2-184">报告将刷新, 以显示组织中的人员已报告为网络钓鱼尝试的电子邮件的相关数据。</span><span class="sxs-lookup"><span data-stu-id="cdda2-184">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="cdda2-185">您可以使用此信息进行进一步分析, 如有必要, 调整您的[ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-185">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="cdda2-186">启动自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="cdda2-186">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="cdda2-187">**Office 365 ATP 计划 2**和**Office 365 E5**中提供了自动调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="cdda2-187">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="cdda2-188">(新!)[自动化调查和响应](automated-investigation-response-office.md)可在调查和缓解网络攻击方面为安全操作团队节省大量时间和精力。</span><span class="sxs-lookup"><span data-stu-id="cdda2-188">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="cdda2-189">除了配置可触发安全行动手册的警报外, 还可以从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="cdda2-189">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="cdda2-190">有关此操作的详细信息, 请参阅[示例: 安全管理员从资源管理器触发调查](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)。</span><span class="sxs-lookup"><span data-stu-id="cdda2-190">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="cdda2-191">使用资源管理器 (或实时检测) 的更多方法</span><span class="sxs-lookup"><span data-stu-id="cdda2-191">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="cdda2-192">除了本文中介绍的方案之外, 您还可以使用浏览器 (或实时检测) 中提供的更多报告选项。</span><span class="sxs-lookup"><span data-stu-id="cdda2-192">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="cdda2-193">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="cdda2-193">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="cdda2-194">查看 SharePoint Online、OneDrive 和 Microsoft 团队中检测到的恶意文件</span><span class="sxs-lookup"><span data-stu-id="cdda2-194">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="cdda2-195">获取威胁资源管理器中的视图 (和实时检测) 的概述</span><span class="sxs-lookup"><span data-stu-id="cdda2-195">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="cdda2-196">必需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="cdda2-196">Required licenses and permissions</span></span>

<span data-ttu-id="cdda2-197">您必须具有[Office 365 ATP](office-365-atp.md)才能获取资源管理器或实时检测。</span><span class="sxs-lookup"><span data-stu-id="cdda2-197">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="cdda2-198">资源管理器包含在 Office 365 ATP 计划2中。</span><span class="sxs-lookup"><span data-stu-id="cdda2-198">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="cdda2-199">实时检测报告包含在 Office 365 ATP 计划1中。</span><span class="sxs-lookup"><span data-stu-id="cdda2-199">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>

<span data-ttu-id="cdda2-200">若要查看和使用资源管理器或实时检测, 您必须具有适当的权限, 例如, 授予安全管理员或安全阅读者的权限。</span><span class="sxs-lookup"><span data-stu-id="cdda2-200">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="cdda2-201">对于安全&amp;合规中心, 您必须具有以下分配的角色之一:</span><span class="sxs-lookup"><span data-stu-id="cdda2-201">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="cdda2-202">组织管理</span><span class="sxs-lookup"><span data-stu-id="cdda2-202">Organization Management</span></span>
    - <span data-ttu-id="cdda2-203">安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span><span class="sxs-lookup"><span data-stu-id="cdda2-203">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="cdda2-204">安全读者</span><span class="sxs-lookup"><span data-stu-id="cdda2-204">Security Reader</span></span>

- <span data-ttu-id="cdda2-205">对于 Exchange Online, 必须在 Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span><span class="sxs-lookup"><span data-stu-id="cdda2-205">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="cdda2-206">组织管理</span><span class="sxs-lookup"><span data-stu-id="cdda2-206">Organization Management</span></span>
    - <span data-ttu-id="cdda2-207">仅限查看组织管理</span><span class="sxs-lookup"><span data-stu-id="cdda2-207">View-only Organization Management</span></span>
    - <span data-ttu-id="cdda2-208">“仅供查看收件人”角色</span><span class="sxs-lookup"><span data-stu-id="cdda2-208">View-Only Recipients role</span></span>
    - <span data-ttu-id="cdda2-209">合规性管理</span><span class="sxs-lookup"><span data-stu-id="cdda2-209">Compliance Management</span></span>

<span data-ttu-id="cdda2-210">若要了解有关角色和权限的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="cdda2-210">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="cdda2-211">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cdda2-211">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="cdda2-212">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="cdda2-212">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
