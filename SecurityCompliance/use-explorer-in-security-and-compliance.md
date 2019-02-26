---
title: 在安全&amp;合规中心中使用资源管理器
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
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
ms.openlocfilehash: 4a28626d0e643d7a7b96a34656e7678c71a86c66
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241964"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="ac573-103">在安全&amp;合规中心中使用资源管理器</span><span class="sxs-lookup"><span data-stu-id="ac573-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="ac573-p101">如果您的组织具有[Office 365 威胁智能](office-365-ti.md), 并且您拥有必要的权限, 则可以使用资源管理器确定和分析威胁。例如, 您可以识别和删除已传递的恶意电子邮件, 或查看 Office 365 安全功能捕获的恶意软件。资源管理器 (也称为威胁浏览器) 是安全&amp;合规中心中功能强大的近实时报告。</span><span class="sxs-lookup"><span data-stu-id="ac573-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="ac573-108">若要使用资源管理器, &amp;请在安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="ac573-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac573-p102">从2019年2月起开始, 在接下来的几个月中, office 365 威胁情报将成为 office 365 高级威胁防护计划 2, 其中包含其他威胁防护功能。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ac573-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="ac573-111">Explorer 概述</span><span class="sxs-lookup"><span data-stu-id="ac573-111">Explorer overview</span></span>

<span data-ttu-id="ac573-p103">资源管理器显示有关 Office 365 中的电子邮件和文件中的可疑恶意软件, 以及组织的其他安全威胁和风险。首次打开资源管理器时, 默认视图显示过去7天内防病毒软件检测到的恶意软件。资源管理器还可以显示 Office 365 中的安全保护功能, 包括[安全链接](atp-safe-links.md)和[安全附件](atp-safe-attachments.md), 并且可以修改以显示过去30天的数据。</span><span class="sxs-lookup"><span data-stu-id="ac573-p103">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![资源管理器显示有关主要恶意软件和目标用户的信息](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="ac573-116">使用 "视图" 菜单更改要显示的信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-116">Use the View menu to change what information is displayed.</span></span>
  
![浏览器的视图菜单](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="ac573-p104">资源管理器具有几个筛选和查询功能, 这些功能使您能够深入了解详细信息, 如主要的目标用户、主要的恶意软件系列等。每种报告都提供了查看和浏览数据的各种方式。</span><span class="sxs-lookup"><span data-stu-id="ac573-p104">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac573-p105">不要在浏览器中使用通配符, 如星号 (\*) 或问号 (？)。当您在 "主题" 字段中搜索电子邮件时, 资源管理器将执行部分匹配并生成类似于通配符搜索的结果。</span><span class="sxs-lookup"><span data-stu-id="ac573-p105">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="ac573-122">电子\>邮件恶意软件</span><span class="sxs-lookup"><span data-stu-id="ac573-122">Email \> Malware</span></span>

<span data-ttu-id="ac573-123">此视图显示标识为包含恶意软件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ac573-123">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="ac573-124">在图表中查看由恶意软件系列、发件人域、发件人 IP、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 和检测技术 (检测到恶意软件) 的信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-124">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="ac573-126">在图表下方, 查看有关主要恶意软件系列、主要目标用户和特定邮件的详细信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-126">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="ac573-127">电子\>邮件网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="ac573-127">Email \> Phish</span></span>

<span data-ttu-id="ac573-128">此视图显示被标识为 "仿冒尝试" 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ac573-128">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="ac573-129">按发件人域、发件人 IP 和保护状态查看信息 (由 Office 365 中的威胁防护功能和策略执行的操作)。</span><span class="sxs-lookup"><span data-stu-id="ac573-129">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![查看标识为 "仿冒尝试" 的电子邮件的相关数据](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="ac573-131">在图表下方, 查看有关特定邮件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-131">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="ac573-132">电子\>邮件用户报告</span><span class="sxs-lookup"><span data-stu-id="ac573-132">Email \> User-reported</span></span>

<span data-ttu-id="ac573-133">此视图显示用户已报告为垃圾邮件、非垃圾邮件或仿冒电子邮件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ac573-133">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="ac573-134">按报告类型查看信息 (用户确定电子邮件是垃圾邮件, 而非垃圾邮件或网络钓鱼), 传递原因 (电子邮件发送到特定位置的原因 (如垃圾邮件筛选器策略、邮件流规则、阻止发件人列表、安全发件人列表)等)。</span><span class="sxs-lookup"><span data-stu-id="ac573-134">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![查看报告为垃圾邮件、非垃圾邮件或网络钓鱼的电子邮件用户的相关数据](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="ac573-136">在图表下方, 查看有关特定电子邮件 (如主题行、发件人的 IP 地址、将邮件报告为垃圾邮件、非垃圾邮件或网络钓鱼的用户) 的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-136">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="ac573-137">通过\>电子邮件发送所有邮件</span><span class="sxs-lookup"><span data-stu-id="ac573-137">Email \> All mail</span></span>

<span data-ttu-id="ac573-138">此视图显示电子邮件活动的一个全视图方式, 包括因网络钓鱼或恶意软件而被标识为恶意的电子邮件, 以及所有非恶意邮件 (普通电子邮件、垃圾邮件和批量邮件)。</span><span class="sxs-lookup"><span data-stu-id="ac573-138">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="ac573-139">如果收到一条错误, 指示**要显示的数据过多**, 请添加筛选器, 并在必要时缩小正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="ac573-139">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="ac573-p106">若要应用筛选器, 请选择 "**发件人**", 选择列表中的项目, 然后单击 "刷新" 按钮。在我们的示例中, 我们将**检测技术**用作筛选器 (有几种可用选项)。按发件人、发件人的域、收件人、主题、附件文件名、恶意软件系列、保护状态 (由 Office 365 中的威胁防护功能和策略执行的操作) 查看信息、检测技术 (检测恶意软件的方式) 以及多.</span><span class="sxs-lookup"><span data-stu-id="ac573-p106">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![查看检测技术检测到的电子邮件的相关数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="ac573-144">在图表下方, 查看有关特定电子邮件的详细信息, 如主题行、收件人、发件人、状态等。</span><span class="sxs-lookup"><span data-stu-id="ac573-144">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="ac573-145">内容\>恶意软件</span><span class="sxs-lookup"><span data-stu-id="ac573-145">Content \> Malware</span></span>

<span data-ttu-id="ac573-146">此视图显示在 SharePoint Online、OneDrive for business 和 Microsoft 团队中被标识为恶意的文件。</span><span class="sxs-lookup"><span data-stu-id="ac573-146">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="ac573-147">查看恶意软件系列的信息、检测技术 (检测恶意软件的方式) 以及工作负荷 (OneDrive、SharePoint 或团队)。</span><span class="sxs-lookup"><span data-stu-id="ac573-147">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![查看检测到的恶意软件的相关数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="ac573-149">在图表下方, 查看有关特定文件的更多详细信息, 如附件文件名、工作负荷、文件大小、上次修改文件的时间等。</span><span class="sxs-lookup"><span data-stu-id="ac573-149">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="ac573-150">(新!)单击-筛选功能</span><span class="sxs-lookup"><span data-stu-id="ac573-150">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="ac573-p107">浏览器的新增功能是可以通过单击进行筛选。从后期开始可能为2018在单击图例中的项目时, 该项目将成为报表的筛选器。例如, 假设我们在资源管理器中查看恶意软件视图:</span><span class="sxs-lookup"><span data-stu-id="ac573-p107">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![转到 "威胁\>管理资源管理器"](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="ac573-155">单击此图表中的**ATP 沙箱**将生成如下所示的视图:</span><span class="sxs-lookup"><span data-stu-id="ac573-155">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![筛选器已筛选为仅显示 ATO 沙箱结果](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="ac573-p108">在此视图中, 我们现在正在查看由[Office 365 ATP 安全附件](atp-safe-attachments.md)触发的文件的数据。在图表下方, 我们可以查看包含由 ATP 安全附件检测到的附件的特定电子邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac573-p108">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![包含检测到的附件的电子邮件的特定详细信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="ac573-160">选择一个或多个项目将激活 "**操作**" 菜单, 其中提供了几个选项, 可从中选择所选的项目。</span><span class="sxs-lookup"><span data-stu-id="ac573-160">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![选择项会激活 "操作" 菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="ac573-162">通过单击并导航到特定详细信息的功能, 可以在调查威胁方面为你节省大量时间。</span><span class="sxs-lookup"><span data-stu-id="ac573-162">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="ac573-163">如何获取资源管理器？</span><span class="sxs-lookup"><span data-stu-id="ac573-163">How do I get Explorer?</span></span>

<span data-ttu-id="ac573-164">资源管理器包含在[Office 365 威胁智能](office-365-ti.md)中。</span><span class="sxs-lookup"><span data-stu-id="ac573-164">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="ac573-p109">若要查看和使用资源管理器, 您必须具有适当的权限, 如已授予安全管理员或安全阅读者的权限。若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ac573-p109">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ac573-167">相关主题</span><span class="sxs-lookup"><span data-stu-id="ac573-167">Related topics</span></span>

[<span data-ttu-id="ac573-168">Office 365 安全&amp;合规中心中的报告和见解</span><span class="sxs-lookup"><span data-stu-id="ac573-168">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="ac573-169">查找并调查提供的恶意电子邮件 (Office 365 威胁智能)</span><span class="sxs-lookup"><span data-stu-id="ac573-169">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="ac573-170">Office 365 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="ac573-170">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

