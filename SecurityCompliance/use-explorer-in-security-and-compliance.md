---
title: 在安全中使用资源管理器&amp;合规性中心
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: 了解在安全资源管理器 （也称为威胁资源管理器）&amp;合规性中心。
ms.openlocfilehash: c5b6273120c605cb4233f62b5c52c6a794e554eb
ms.sourcegitcommit: 0cc6083bd8cb2f7bbf18847149c6d5239f2a6403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699925"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="5f8e6-103">在安全中使用资源管理器&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="5f8e6-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="5f8e6-p101">如果您的组织具有[Office 365 威胁智能](office-365-ti.md)，并且您所需的权限，您可以使用资源管理器确定和分析威胁。例如，您可以确定和删除恶意已发送的电子邮件或请参阅 Office 365 安全功能由已捕获的恶意软件。资源管理器 （也称为威胁资源管理器） 是强大的近乎实时报告安全中&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![转到威胁管理\>资源管理器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="5f8e6-108">安全中使用资源管理器，&amp;合规性中心中，转到**威胁管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="5f8e6-109">资源管理器概述</span><span class="sxs-lookup"><span data-stu-id="5f8e6-109">Explorer overview</span></span>

<span data-ttu-id="5f8e6-p102">资源管理器显示您的组织的信息可疑电子邮件中的恶意软件和 Office 365 中的文件，以及其他安全威胁和风险。当您首次打开资源管理器中时，默认视图显示从防病毒的恶意软件检测过去 7 天。资源管理器还可以显示安全保护功能在 Office 365 中，包括[安全链接](atp-safe-links.md)和[安全的附件](atp-safe-attachments.md)，并可进行修改以显示过去 30 天的数据。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p102">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![资源管理器显示有关流行恶意软件和目标的用户的信息](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="5f8e6-114">使用视图菜单来更改显示的信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-114">Use the View menu to change what information is displayed.</span></span>
  
![资源管理器视图菜单](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="5f8e6-p103">资源管理器具有多个筛选和查询功能，使您能够深入了解详细信息，如顶部目标用户、 流行恶意软件家庭和详细信息。每种类型的报告提供了多种方式查看和分析数据。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p103">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f8e6-p104">不要使用通配符字符，例如星号 （\*） 或使用资源管理器问号 （？）。在搜索主题字段中的电子邮件时，资源管理器将执行部分匹配并产生类似于结果通配符搜索。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p104">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="5f8e6-120">电子邮件\>恶意软件</span><span class="sxs-lookup"><span data-stu-id="5f8e6-120">Email \> Malware</span></span>

<span data-ttu-id="5f8e6-121">此视图显示了标识为包含恶意软件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-121">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="5f8e6-122">查看由恶意软件系列、 发件人域、 发件人 IP、 保护状态 （您威胁保护功能和 Office 365 中的策略所采取的操作） 和检测技术 （如何恶意软件检测到） 图表中的信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-122">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![查看关于恶意软件检测到的数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="5f8e6-124">下面的图表，查看有关流行恶意软件系列详细信息顶部目标用户和有关特定消息的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-124">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="5f8e6-125">电子邮件\>网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="5f8e6-125">Email \> Phish</span></span>

<span data-ttu-id="5f8e6-126">此视图显示电子邮件标识为网络钓鱼尝试。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-126">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="5f8e6-127">查看由发件人域、 发件人 IP 和保护状态 （您威胁保护功能和 Office 365 中的策略执行的操作） 的信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-127">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![关于电子邮件标识为网络钓鱼尝试查看数据](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="5f8e6-129">下面的图表，查看有关特定消息的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-129">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="5f8e6-130">电子邮件\>用户报告</span><span class="sxs-lookup"><span data-stu-id="5f8e6-130">Email \> User-reported</span></span>

<span data-ttu-id="5f8e6-131">此视图显示电子邮件用户具有报告为垃圾、 不是垃圾邮件或网络钓鱼电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-131">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="5f8e6-132">通过报表类型 （电子邮件已垃圾、 不是垃圾邮件或网络钓鱼诈骗用户确定） 并传递原因 （原因电子邮件进入特定位置，如的垃圾邮件筛选器策略、 邮件流规则、 被阻止的发件人列表、 安全的发件人列表中，查看信息等）。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-132">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![有关电子邮件的用户查看数据报告为垃圾、 不是垃圾邮件或网络钓鱼](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="5f8e6-134">下面的图表，查看有关特定电子邮件，如主题行、 发件人的 IP 地址、 报告为垃圾邮件、 未垃圾，或网络钓鱼诈骗、 等的邮件的用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-134">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="5f8e6-135">电子邮件\>的所有邮件</span><span class="sxs-lookup"><span data-stu-id="5f8e6-135">Email \> All mail</span></span>

<span data-ttu-id="5f8e6-136">此视图显示所有向上视图的电子邮件活动，包括电子邮件标识为恶意截止到网络钓鱼或恶意软件、，以及所有非恶意邮件 （普通电子邮件、 垃圾邮件、 和批量邮件）。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-136">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="5f8e6-137">如果您收到一条错误，读取**太多的数据以显示**、 添加筛选器，如有必要，缩小范围正在查看的日期范围。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-137">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="5f8e6-p105">要应用筛选器，请选择**发件人**，在列表中，选择一个项目，然后单击刷新按钮。在我们的示例，我们使用**检测技术**为筛选器 （有几个选项可用）。查看按发件人、 发件人的域、 收件人、 主题、 附件的文件名、 恶意软件系列、 保护状态 （您威胁保护功能和 Office 365 中的策略执行的操作）、 （如何恶意软件检测到），检测技术信息和更多。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p105">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![查看关于检测到的电子邮件检测技术提供支持的数据](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="5f8e6-142">下面的图表，查看有关特定电子邮件，如主题行、 收件人、 发件人、 状态和等等的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-142">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="5f8e6-143">内容\>恶意软件</span><span class="sxs-lookup"><span data-stu-id="5f8e6-143">Content \> Malware</span></span>

<span data-ttu-id="5f8e6-144">此视图显示了标识为恶意在 SharePoint Online、 OneDrive for Business 和 Microsoft 团队的文件。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-144">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="5f8e6-145">由恶意软件系列，检测技术，（如何恶意软件检测到），查看信息和工作负荷 （OneDrive、 SharePoint、 或团队）。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-145">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![查看关于恶意软件检测到的数据](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="5f8e6-147">下面的图表，查看有关特定的文件，如附件的文件名、 工作负荷、 文件大小，上次修改文件和更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-147">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="5f8e6-148">（新） ！单击到筛选器功能</span><span class="sxs-lookup"><span data-stu-id="5f8e6-148">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="5f8e6-p106">新增到资源管理器中是单击以筛选的能力。开始在后期年 5 月 2018，当您单击图例中的项目，该项目将成为报表的筛选器。例如，假设我们要看资源管理器中的恶意软件视图：</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p106">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![转到威胁管理\>资源管理器](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="5f8e6-153">此图表导致类似的视图中，单击**ATP Detonation** :</span><span class="sxs-lookup"><span data-stu-id="5f8e6-153">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![筛选以显示仅 ATO Detonation 结果的资源管理器](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="5f8e6-p107">在此视图中，我们现在在看过 detonated 通过[Office 365 ATP 安全附件](atp-safe-attachments.md)的文件的数据。下面的图表，我们可以看到有关具有检测 ATP 安全附件的附件的特定的电子邮件消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p107">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![检测到的附件的电子邮件的特定信息](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="5f8e6-158">选择一个或多个项激活**操作**菜单，它提供了可供选择的选定项的多个选项。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-158">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![选择项目激活操作菜单](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="5f8e6-160">在单击筛选器并导航到具体的详细信息的功能可以将您大量时间调查威胁。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-160">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="5f8e6-161">如何获取资源管理器？</span><span class="sxs-lookup"><span data-stu-id="5f8e6-161">How do I get Explorer?</span></span>

<span data-ttu-id="5f8e6-162">[Office 365 威胁智能](office-365-ti.md)包含资源管理器。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-162">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="5f8e6-p108">您必须具有适当的权限，如授予 security 管理员程序或安全读取器才能查看和使用资源管理器。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5f8e6-p108">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5f8e6-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="5f8e6-165">Related topics</span></span>

[<span data-ttu-id="5f8e6-166">报告和 Office 365 安全性见解&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="5f8e6-166">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="5f8e6-167">查找并调查恶意电子邮件已送达 （Office 365 威胁智能）</span><span class="sxs-lookup"><span data-stu-id="5f8e6-167">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="5f8e6-168">Office 365 中的反垃圾邮件和反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="5f8e6-168">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

