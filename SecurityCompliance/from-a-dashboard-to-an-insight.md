---
title: 演练 - 从仪表板到见解
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
description: 了解如何可以从仪表板访问与安全中建议的操作的真知灼见&amp;合规性中心。
ms.openlocfilehash: 933bf6e86bc1ddce9259d071b69654f68e4dd370
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706146"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="1225b-103">演练 - 从仪表板到见解</span><span class="sxs-lookup"><span data-stu-id="1225b-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="1225b-104">如果您是新手[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)，它可能有助于请参阅如何您可以轻松地从导航仪表板到见解和建议的操作。</span><span class="sxs-lookup"><span data-stu-id="1225b-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="1225b-p101">这是一个安全的几个演练&amp;合规性中心。若要查看其他演练，请参阅[相关的主题](#related-topics)部分。</span><span class="sxs-lookup"><span data-stu-id="1225b-p101">This is one of several walkthroughs for the Security &amp; Compliance Center. To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="1225b-107">演练： 从洞察仪表板</span><span class="sxs-lookup"><span data-stu-id="1225b-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="1225b-p102">让我们该工作流中从仪表板向洞察和操作的报告。（这是一个简短[欺骗智能](learn-about-spoof-intelligence.md)示例）。</span><span class="sxs-lookup"><span data-stu-id="1225b-p102">Let's walk through the flow from a dashboard to a report to an insight and action. (This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="1225b-p103">我们首先在安全仪表板[安全&amp;合规性中心](https://security.microsoft.com)。(请转到**威胁管理** \> **仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="1225b-p103">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://security.microsoft.com). (Go to **Threat management** \> **Dashboard**.)</span></span>
    
    ![安全中&amp;合规性中心中，选择威胁管理\>仪表板](media/05a38660-eb13-4960-a266-11809c453d95.png)
  
2. <span data-ttu-id="1225b-p104">在**洞察力**行中，我们注意到洞察指示我们需要查看可能可疑某些域。（在**洞察力**行中，单击**域对**。）</span><span class="sxs-lookup"><span data-stu-id="1225b-p104">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious. (In the **Insights** row, click **Domain pairs**.)</span></span>
    
    ![洞察力行提到欺骗的潜在问题](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)
  
3. <span data-ttu-id="1225b-p105">我们获得欺骗智能相关的活动的列表。这些是电子邮件已发送到哪里的看上去像它们来自我们的组织，但事实上，，从另一个组织发送的实例。目标是决定是否或未授权欺骗的邮件。</span><span class="sxs-lookup"><span data-stu-id="1225b-p105">We get a list of activities related to spoof intelligence. These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization. The goal is to determine whether the spoofed messages are authorized or not.</span></span>
    
    ![欺骗智能见解](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)
  
    <span data-ttu-id="1225b-p106">此列表中，我们可以排序邮件计数、 欺骗上次检测到的日期和详细信息。（单击列标题，例如**消息计数**或**上一次发现**以查看如何排序的工作原理。）</span><span class="sxs-lookup"><span data-stu-id="1225b-p106">In this list, we can sort the information by message count, date the spoofing was last detected, and more. (Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="1225b-p107">选择列表中的项目打开，我们可以看到其他信息，包括类似检测到的电子邮件的详细信息窗格。（单击项目列表中，并查看的信息和建议）。</span><span class="sxs-lookup"><span data-stu-id="1225b-p107">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected. (Click an item in the list, and review the information and recommendations.)</span></span>
    
    ![选择项目将打开的详细信息窗格](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)
  
5. <span data-ttu-id="1225b-p108">请注意，在顶部窗格中，我们可以选择将发件人添加到我们的组织允许的发件人列表。（不选择**添加到 AllowedtoSpoof 发件人允许列表**除非您确认需要执行此操作。[了解更多有关欺骗智能](learn-about-spoof-intelligence.md)。）</span><span class="sxs-lookup"><span data-stu-id="1225b-p108">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list. (Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this. [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span>
    
    ![您可以授权发件人](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)
  
<span data-ttu-id="1225b-129">这种方式，我们可以从仪表板移动到见解和建议的操作。</span><span class="sxs-lookup"><span data-stu-id="1225b-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1225b-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="1225b-130">Related topics</span></span>

[<span data-ttu-id="1225b-131">演练： 从对详细报告见解</span><span class="sxs-lookup"><span data-stu-id="1225b-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="1225b-132">演练： 从到洞察的详细报告</span><span class="sxs-lookup"><span data-stu-id="1225b-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

