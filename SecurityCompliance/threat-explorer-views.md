---
title: 威胁资源管理器视图
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/18/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: 了解在 Office 365 高级威胁防护计划2中的资源管理器 (也称为威胁浏览器) 中可用的各种类型的视图。
ms.openlocfilehash: bcfa044db6844d9459b3dd62d9ced1cd37a999ec
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736231"
---
# <a name="threat-explorer-views"></a><span data-ttu-id="5c54b-103">威胁资源管理器视图</span><span class="sxs-lookup"><span data-stu-id="5c54b-103">Threat Explorer views</span></span>

<span data-ttu-id="5c54b-104">[威胁资源管理器](use-explorer-in-security-and-compliance.md)是一种强大的近实时工具, 可帮助安全操作团队在安全&amp;合规中心中调查和响应威胁。</span><span class="sxs-lookup"><span data-stu-id="5c54b-104">[Threat Explorer](use-explorer-in-security-and-compliance.md) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5c54b-105">资源管理器显示有关 Office 365 中的电子邮件和文件中可疑的恶意软件和网络钓鱼的信息, 以及组织中的其他安全威胁和风险。</span><span class="sxs-lookup"><span data-stu-id="5c54b-105">Explorer displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

<span data-ttu-id="5c54b-106">首次打开资源管理器时, 默认视图将显示过去7天内的电子邮件恶意软件检测。</span><span class="sxs-lookup"><span data-stu-id="5c54b-106">When you first open Explorer, the default view shows email malware detections for the past 7 days.</span></span> 

![威胁资源管理器](media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="5c54b-108">资源管理器还可以显示 Office 365 中的安全保护功能, 包括[安全链接](atp-safe-links.md)和[安全附件](atp-safe-attachments.md), 并且可以修改以显示过去30天的数据。</span><span class="sxs-lookup"><span data-stu-id="5c54b-108">Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span> 

> [!NOTE]
> <span data-ttu-id="5c54b-109">如果你拥有 Office 365 高级威胁防护计划2或 Office 365 E5 的试用订阅, 你将只能看到过去7天的检测和电子邮件数据。</span><span class="sxs-lookup"><span data-stu-id="5c54b-109">If you have a trial subscription for Office 365 Advanced Threat Protection Plan 2 or Office 365 E5, you will only see detections and email data for the past 7 days.</span></span>
  
<span data-ttu-id="5c54b-110">使用 "**视图**" 菜单更改要显示的信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-110">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="5c54b-111">工具提示可帮助您确定要使用的视图。</span><span class="sxs-lookup"><span data-stu-id="5c54b-111">Tooltips help you determine which view to use.</span></span>
  
![威胁资源管理器视图菜单](media/ThreatExplorerViewMenu.png)

<span data-ttu-id="5c54b-113">选择视图后, 可以应用筛选器并设置查询以执行进一步分析。</span><span class="sxs-lookup"><span data-stu-id="5c54b-113">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="5c54b-114">以下各节提供了浏览器中提供的各种视图的简要概述。</span><span class="sxs-lookup"><span data-stu-id="5c54b-114">The following sections provide a brief overview of the various views available in Explorer.</span></span>  

## <a name="email--malware"></a><span data-ttu-id="5c54b-115">电子邮件 > 恶意软件</span><span class="sxs-lookup"><span data-stu-id="5c54b-115">Email > Malware</span></span>

<span data-ttu-id="5c54b-116">若要查看此报告, 请在资源管理器中选择 "**查看** > **电子邮件** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-116">To view this report, in Explorer, choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="5c54b-117">此视图显示标识为包含恶意软件的电子邮件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-117">This view shows information about email messages that were identified as containing malware.</span></span>  

![查看标识为恶意软件的电子邮件的相关数据](media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="5c54b-119">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5c54b-119">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5c54b-120">使用此列表可以按发件人、收件人、发件人域、主题、检测技术、保护状态等查看数据。</span><span class="sxs-lookup"><span data-stu-id="5c54b-120">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="5c54b-121">例如, 若要查看对检测到的电子邮件所执行的操作, 请在列表中选择 "**保护状态**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-121">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="5c54b-122">选择一个选项, 然后单击 "刷新" 按钮将该筛选器应用于报表。</span><span class="sxs-lookup"><span data-stu-id="5c54b-122">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![威胁资源管理器的威胁防护状态选项](media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="5c54b-124">在图表下方, 查看有关特定邮件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-124">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="5c54b-125">当您选择列表中的某个项目时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-125">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![打开了浮出控件的威胁资源管理器](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="5c54b-127">电子邮件 > 网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="5c54b-127">Email > Phish</span></span>

<span data-ttu-id="5c54b-128">若要查看此报告, 请在资源管理器中选择 "**查看** > **电子邮件** > **网络钓鱼**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-128">To view this report, in Explorer, choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="5c54b-129">此视图显示被标识为 "仿冒尝试" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5c54b-129">This view shows email messages identified as phishing attempts.</span></span>  

![查看标识为 "仿冒尝试" 的电子邮件的相关数据](media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="5c54b-131">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5c54b-131">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5c54b-132">使用此列表可以按发件人、收件人、发件人域、发件人 IP、URL 域查看数据, 然后单击 "判定", 等等。</span><span class="sxs-lookup"><span data-stu-id="5c54b-132">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="5c54b-133">例如, 若要查看当用户单击被标识为仿冒的 url 时所采取的操作, 请在列表中选择 **"单击判定**项", 选择一个或多个选项, 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5c54b-133">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![单击网络钓鱼报告的 "判定选项"](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="5c54b-135">在图表下方, 查看有关特定邮件、URL 单击、url 和电子邮件来源的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-135">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![在电子邮件中检测到作为网络钓鱼的 url](media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="5c54b-137">当您选择列表中的某个项目 (如检测到的 URL) 时, 将打开一个弹出窗格, 可在其中了解有关所选项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-137">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![有关检测到的 URL 的详细信息](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a><span data-ttu-id="5c54b-139">电子邮件 > 用户报告</span><span class="sxs-lookup"><span data-stu-id="5c54b-139">Email > User-reported</span></span>

<span data-ttu-id="5c54b-140">若要查看此报告, 请在资源管理器中选择 "**查看** > **电子邮件** > **用户报告**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-140">To view this report, in Explorer, choose **View** > **Email** > **User-reported**.</span></span> <span data-ttu-id="5c54b-141">此视图显示用户已报告为垃圾邮件、非垃圾邮件或仿冒电子邮件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5c54b-141">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![用户报告的电子邮件](media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="5c54b-143">单击 "**发件人**" 打开查看选项列表。</span><span class="sxs-lookup"><span data-stu-id="5c54b-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="5c54b-144">使用此列表可以按发件人、收件人、报告类型查看信息 (用户决定电子邮件是垃圾邮件, 而不是垃圾邮件或网络钓鱼) 等。</span><span class="sxs-lookup"><span data-stu-id="5c54b-144">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="5c54b-145">例如, 若要查看报告为 "仿冒试" 的电子邮件的信息, 请单击 "**发件人** > **报告类型**", 选择 "**网络钓鱼**", 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5c54b-145">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![为报告类型筛选器选择的网络钓鱼](media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="5c54b-147">在图表下方, 查看有关特定电子邮件 (如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户) 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-147">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![被报告为网络钓鱼尝试的邮件](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="5c54b-149">在列表中选择一个项目以查看其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-149">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="5c54b-150">电子邮件 > 所有电子邮件</span><span class="sxs-lookup"><span data-stu-id="5c54b-150">Email > All email</span></span>

<span data-ttu-id="5c54b-151">若要查看此报告, 请在资源管理器中选择 "**查看** > \*\*\*\* > **全部邮件**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-151">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="5c54b-152">此视图显示电子邮件活动的一个全视图方式, 包括因网络钓鱼或恶意软件而被标识为恶意的电子邮件, 以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件)。</span><span class="sxs-lookup"><span data-stu-id="5c54b-152">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="5c54b-153">如果收到一条错误, 指示**要显示的数据过多**, 请添加筛选器, 并在必要时缩小正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="5c54b-153">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="5c54b-154">若要应用筛选器, 请选择 "**发件人**", 选择列表中的项目, 然后单击 "刷新" 按钮。</span><span class="sxs-lookup"><span data-stu-id="5c54b-154">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="5c54b-155">在我们的示例中, 我们将**检测技术**用作筛选器 (有几种可用选项)。</span><span class="sxs-lookup"><span data-stu-id="5c54b-155">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="5c54b-156">按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 查看信息、检测技术 (检测恶意软件的方式) 以及多.</span><span class="sxs-lookup"><span data-stu-id="5c54b-156">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![查看检测技术检测到的电子邮件的相关数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="5c54b-158">在图表下方, 查看有关特定电子邮件的详细信息, 如主题行、收件人、发件人、状态等。</span><span class="sxs-lookup"><span data-stu-id="5c54b-158">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="5c54b-159">内容 > 恶意软件</span><span class="sxs-lookup"><span data-stu-id="5c54b-159">Content > Malware</span></span>

<span data-ttu-id="5c54b-160">若要查看此报告, 请在资源管理器中选择 "**查看** > **内容** > **恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="5c54b-160">To view this report, in Explorer, choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="5c54b-161">此视图显示了[Office 365 高级威胁防护在 SharePoint Online、OneDrive for business 和 Microsoft 团队中](atp-for-spo-odb-and-teams.md)被标识为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="5c54b-161">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5c54b-162">查看恶意软件系列的信息、检测技术 (检测恶意软件的方式) 以及工作负荷 (OneDrive、SharePoint 或团队)。</span><span class="sxs-lookup"><span data-stu-id="5c54b-162">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="5c54b-164">在图表下方, 查看有关特定文件的更多详细信息, 如附件文件名、工作负荷、文件大小、上次修改文件的时间等。</span><span class="sxs-lookup"><span data-stu-id="5c54b-164">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="5c54b-165">单击-筛选功能</span><span class="sxs-lookup"><span data-stu-id="5c54b-165">Click-to-filter capabilities</span></span>

<span data-ttu-id="5c54b-166">使用资源管理器, 您可以在单击时应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="5c54b-166">With Explorer, you can apply a filter in a click.</span></span> <span data-ttu-id="5c54b-167">单击图例中的项目, 该项目将成为报表的筛选器。</span><span class="sxs-lookup"><span data-stu-id="5c54b-167">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="5c54b-168">例如, 假设我们在资源管理器中查看恶意软件视图:</span><span class="sxs-lookup"><span data-stu-id="5c54b-168">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="5c54b-170">单击此图表中的**ATP 沙箱**将生成如下所示的视图:</span><span class="sxs-lookup"><span data-stu-id="5c54b-170">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![筛选器已筛选为仅显示 ATP 沙箱结果](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="5c54b-172">在此视图中, 我们现在正在查看由[Office 365 ATP 安全附件](atp-safe-attachments.md)触发的文件的数据。</span><span class="sxs-lookup"><span data-stu-id="5c54b-172">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="5c54b-173">在图表下方, 我们可以查看包含由 ATP 安全附件检测到的附件的特定电子邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c54b-173">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![包含检测到的附件的电子邮件的特定详细信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="5c54b-175">选择一个或多个项目将激活 "**操作**" 菜单, 其中提供了几个选项, 可从中选择所选的项目。</span><span class="sxs-lookup"><span data-stu-id="5c54b-175">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![选择项会激活 "操作" 菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="5c54b-177">通过单击并导航到特定详细信息的功能, 可以在调查威胁方面为你节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="5c54b-177">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="5c54b-178">查询和筛选器</span><span class="sxs-lookup"><span data-stu-id="5c54b-178">Queries and filters</span></span>

<span data-ttu-id="5c54b-179">资源管理器具有多种功能强大的筛选器和查询功能, 使您可以深入了解详细信息, 如主要目标用户、主要恶意软件系列、检测技术等。</span><span class="sxs-lookup"><span data-stu-id="5c54b-179">Explorer has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="5c54b-180">每种报告都提供了查看和浏览数据的各种方式。</span><span class="sxs-lookup"><span data-stu-id="5c54b-180">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c54b-181">请勿在浏览器的查询栏中使用通配符, 如星号 (\*) 或问号 (？)。</span><span class="sxs-lookup"><span data-stu-id="5c54b-181">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), in the query bar for Explorer.</span></span> <span data-ttu-id="5c54b-182">当您在 "主题" 字段中搜索电子邮件时, 资源管理器将执行部分匹配并生成类似于通配符搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="5c54b-182">When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>
