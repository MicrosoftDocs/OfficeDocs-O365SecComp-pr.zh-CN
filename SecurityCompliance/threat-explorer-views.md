---
title: 威胁资源管理器中的视图和实时检测
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: 了解在威胁资源管理器和实时检测中可用的各种视图类型。
ms.openlocfilehash: 14cdbbd602e53615abec12bedbac2f16be40111f
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408317"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="f5e25-103">威胁资源管理器中的视图和实时检测</span><span class="sxs-lookup"><span data-stu-id="f5e25-103">Views in Threat Explorer and real-time detections</span></span>

![威胁资源管理器](media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="f5e25-105">[威胁资源管理器](use-explorer-in-security-and-compliance.md)(和实时检测报告) 是一种强大的近实时工具, 可帮助安全操作团队调查和响应安全&amp;合规性中心中的威胁。</span><span class="sxs-lookup"><span data-stu-id="f5e25-105">[Threat Explorer](use-explorer-in-security-and-compliance.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f5e25-106">资源管理器 (和实时检测报告) 显示有关 Office 365 中的电子邮件和文件中可疑的恶意软件和网络钓鱼的信息, 以及组织中的其他安全威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="f5e25-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="f5e25-107">如果您有[Office 365 高级威胁防护](office-365-atp.md)(ATP) 计划 2, 则您将拥有资源管理器。</span><span class="sxs-lookup"><span data-stu-id="f5e25-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="f5e25-108">如果你有 Office 365 ATP 计划 1, 则会进行实时检测。</span><span class="sxs-lookup"><span data-stu-id="f5e25-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="f5e25-109">首次打开浏览器 (或实时检测报告) 时, 默认视图将显示过去7天内的电子邮件恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="f5e25-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="f5e25-110">此报告还可以显示 ATP 检测, 如[安全链接](atp-safe-links.md)检测到的恶意 url, 以及[安全附件](atp-safe-attachments.md)检测到的恶意文件。</span><span class="sxs-lookup"><span data-stu-id="f5e25-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="f5e25-111">可以修改此报告以显示过去30天的数据 (除非您使用的是试用订阅)。</span><span class="sxs-lookup"><span data-stu-id="f5e25-111">This report can be modified to show data for the past 30 days (unless you are using a trial subscription).</span></span> <span data-ttu-id="f5e25-112">试用订阅将仅包含过去七天的数据。</span><span class="sxs-lookup"><span data-stu-id="f5e25-112">Trial subscriptions will include data for the past seven days only.</span></span>

<span data-ttu-id="f5e25-113">使用 "**视图**" 菜单更改要显示的信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-113">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="f5e25-114">工具提示可帮助您确定要使用的视图。</span><span class="sxs-lookup"><span data-stu-id="f5e25-114">Tooltips help you determine which view to use.</span></span>
  
![威胁资源管理器视图菜单](media/ThreatExplorerViewMenu.png)

<span data-ttu-id="f5e25-116">选择视图后, 可以应用筛选器并设置查询以执行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="f5e25-116">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="f5e25-117">以下各节提供了浏览器中提供的各种视图 (或实时检测) 的简要概述。</span><span class="sxs-lookup"><span data-stu-id="f5e25-117">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="f5e25-118">电子邮件 > 恶意软件</span><span class="sxs-lookup"><span data-stu-id="f5e25-118">Email > Malware</span></span>

<span data-ttu-id="f5e25-119">若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="f5e25-119">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="f5e25-120">此视图显示标识为包含恶意软件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-120">This view shows information about email messages that were identified as containing malware.</span></span>  

![查看标识为恶意软件的电子邮件的相关数据](media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="f5e25-122">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="f5e25-122">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f5e25-123">使用此列表可以按发件人、收件人、发件人域、主题、检测技术、保护状态等查看数据。</span><span class="sxs-lookup"><span data-stu-id="f5e25-123">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="f5e25-124">例如, 若要查看对检测到的电子邮件所执行的操作, 请在列表中选择 "**保护状态**"。</span><span class="sxs-lookup"><span data-stu-id="f5e25-124">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="f5e25-125">选择一个选项, 然后单击 "刷新" 按钮将该筛选器应用于报表。</span><span class="sxs-lookup"><span data-stu-id="f5e25-125">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威胁资源管理器的威胁防护状态选项](media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="f5e25-127">在图表下方, 查看有关特定邮件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-127">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="f5e25-128">当您选择列表中的某个项目时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-128">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![打开了浮出控件的威胁资源管理器](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="f5e25-130">电子邮件 > 网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="f5e25-130">Email > Phish</span></span>

<span data-ttu-id="f5e25-131">若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="f5e25-131">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="f5e25-132">此视图显示被标识为 "仿冒尝试" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f5e25-132">This view shows email messages identified as phishing attempts.</span></span>  

![查看标识为 "仿冒尝试" 的电子邮件的相关数据](media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="f5e25-134">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="f5e25-134">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f5e25-135">使用此列表可以按发件人、收件人、发件人域、发件人 IP、URL 域查看数据, 然后单击 "判定", 等等。</span><span class="sxs-lookup"><span data-stu-id="f5e25-135">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="f5e25-136">例如, 若要查看当用户单击被标识为仿冒的 Url 时所采取的操作, 请在列表中选择 **"单击判定**项", 选择一个或多个选项, 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f5e25-136">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![单击网络钓鱼报告的 "判定选项"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="f5e25-138">在图表下方, 查看有关特定邮件、URL 单击、Url 和电子邮件来源的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-138">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![在电子邮件中检测到作为网络钓鱼的 Url](media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="f5e25-140">当您选择列表中的某个项目 (如检测到的 URL) 时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-140">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![有关检测到的 URL 的详细信息](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a><span data-ttu-id="f5e25-142">电子邮件 > 用户报告</span><span class="sxs-lookup"><span data-stu-id="f5e25-142">Email > User-reported</span></span>

<span data-ttu-id="f5e25-143">若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > 由**用户报告的\*\*\*\*电子邮件** > "。</span><span class="sxs-lookup"><span data-stu-id="f5e25-143">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **User-reported**.</span></span> <span data-ttu-id="f5e25-144">此视图显示用户已报告为垃圾邮件、非垃圾邮件或仿冒电子邮件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f5e25-144">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![用户报告的电子邮件](media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="f5e25-146">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="f5e25-146">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="f5e25-147">使用此列表可以按发件人、收件人、报告类型查看信息 (用户决定电子邮件是垃圾邮件, 而不是垃圾邮件或网络钓鱼) 等。</span><span class="sxs-lookup"><span data-stu-id="f5e25-147">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="f5e25-148">例如, 若要查看报告为 "仿冒试" 的电子邮件的信息, 请单击 "**发件人** > **报告类型**", 选择 "**网络钓鱼**", 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f5e25-148">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![为报告类型筛选器选择的网络钓鱼](media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="f5e25-150">在图表下方, 查看有关特定电子邮件 (如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户) 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-150">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![被报告为网络钓鱼尝试的邮件](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="f5e25-152">在列表中选择一个项目以查看其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-152">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="f5e25-153">电子邮件 > 所有电子邮件</span><span class="sxs-lookup"><span data-stu-id="f5e25-153">Email > All email</span></span>

<span data-ttu-id="f5e25-154">若要查看此报告, 请在资源管理器中选择 "**查看** > \*\*\*\* > **全部邮件**"。</span><span class="sxs-lookup"><span data-stu-id="f5e25-154">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="f5e25-155">此视图显示电子邮件活动的一个全视图方式, 包括因网络钓鱼或恶意软件而被标识为恶意的电子邮件, 以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件)。</span><span class="sxs-lookup"><span data-stu-id="f5e25-155">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="f5e25-156">如果收到一条错误, 指示**要显示的数据过多**, 请添加筛选器, 并在必要时缩小正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="f5e25-156">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="f5e25-157">若要应用筛选器, 请选择 "**发件人**", 选择列表中的项目, 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="f5e25-157">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="f5e25-158">在我们的示例中, 我们将**检测技术**用作筛选器 (有几种可用选项)。</span><span class="sxs-lookup"><span data-stu-id="f5e25-158">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="f5e25-159">按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 查看信息、检测技术 (检测恶意软件的方式) 以及多.</span><span class="sxs-lookup"><span data-stu-id="f5e25-159">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![查看检测技术检测到的电子邮件的相关数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="f5e25-161">在图表下方, 查看有关特定电子邮件的详细信息, 如主题行、收件人、发件人、状态等。</span><span class="sxs-lookup"><span data-stu-id="f5e25-161">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="f5e25-162">内容 > 恶意软件</span><span class="sxs-lookup"><span data-stu-id="f5e25-162">Content > Malware</span></span>

<span data-ttu-id="f5e25-163">若要查看此报告, 请在资源管理器 (或实时检测) 中, 选择 "**查看** > **内容** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="f5e25-163">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="f5e25-164">此视图显示了[Office 365 高级威胁防护在 SharePoint Online、OneDrive For business 和 Microsoft 团队中](atp-for-spo-odb-and-teams.md)被标识为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="f5e25-164">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="f5e25-165">查看恶意软件系列的信息、检测技术 (检测恶意软件的方式) 以及工作负荷 (OneDrive、SharePoint 或团队)。</span><span class="sxs-lookup"><span data-stu-id="f5e25-165">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="f5e25-167">在图表下方, 查看有关特定文件的更多详细信息, 如附件文件名、工作负荷、文件大小、上次修改文件的时间等。</span><span class="sxs-lookup"><span data-stu-id="f5e25-167">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="f5e25-168">单击-筛选功能</span><span class="sxs-lookup"><span data-stu-id="f5e25-168">Click-to-filter capabilities</span></span>

<span data-ttu-id="f5e25-169">使用浏览器 (和实时检测), 您可以在单击时应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="f5e25-169">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="f5e25-170">单击图例中的项目, 该项目将成为报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="f5e25-170">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="f5e25-171">例如, 假设我们在资源管理器中查看恶意软件视图:</span><span class="sxs-lookup"><span data-stu-id="f5e25-171">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="f5e25-173">单击此图表中的**ATP 沙箱**将生成如下所示的视图:</span><span class="sxs-lookup"><span data-stu-id="f5e25-173">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![筛选器已筛选为仅显示 ATP 沙箱结果](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="f5e25-175">在此视图中, 我们现在正在查看由[Office 365 ATP 安全附件](atp-safe-attachments.md)触发的文件的数据。</span><span class="sxs-lookup"><span data-stu-id="f5e25-175">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="f5e25-176">在图表下方, 我们可以查看包含由 ATP 安全附件检测到的附件的特定电子邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5e25-176">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![包含检测到的附件的电子邮件的特定详细信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="f5e25-178">选择一个或多个项目将激活 "**操作**" 菜单, 其中提供了几个选项, 可从中选择所选的项目。</span><span class="sxs-lookup"><span data-stu-id="f5e25-178">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![选择项会激活 "操作" 菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="f5e25-180">通过单击并导航到特定详细信息的功能, 可以在调查威胁方面为你节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="f5e25-180">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="f5e25-181">查询和筛选器</span><span class="sxs-lookup"><span data-stu-id="f5e25-181">Queries and filters</span></span>

<span data-ttu-id="f5e25-182">浏览器 (和实时检测报告) 具有多种功能强大的筛选器和查询功能, 使您可以深入了解详细信息, 如主要目标用户、主要恶意软件系列、检测技术等。</span><span class="sxs-lookup"><span data-stu-id="f5e25-182">Explorer (and the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="f5e25-183">每种报告都提供了查看和浏览数据的各种方式。</span><span class="sxs-lookup"><span data-stu-id="f5e25-183">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f5e25-184">请勿在浏览器 (或实时检测) 的查询栏中使用通配符, 如星号 (\*) 或问号 (？)。</span><span class="sxs-lookup"><span data-stu-id="f5e25-184">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="f5e25-185">当您在 "主题" 字段中搜索电子邮件时, 资源管理器 (或实时检测) 将执行与通配符搜索类似的部分匹配和生成结果。</span><span class="sxs-lookup"><span data-stu-id="f5e25-185">When you search on the Subject field for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
