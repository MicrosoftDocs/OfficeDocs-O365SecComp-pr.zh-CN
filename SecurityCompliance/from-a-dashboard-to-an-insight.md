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
ms.collection:
- M365-security-compliance
description: 了解如何从仪表板转到与安全&amp;合规中心中推荐的操作有关的见解。
ms.openlocfilehash: 9f241ce52d76744d2bb6f7b789438110c295ee01
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492751"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="9df8a-103">演练 - 从仪表板到见解</span><span class="sxs-lookup"><span data-stu-id="9df8a-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="9df8a-104">如果你不熟悉[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md), 它可能会帮助你了解如何轻松地从仪表板导航到真知灼见和建议的操作。</span><span class="sxs-lookup"><span data-stu-id="9df8a-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="9df8a-105">这是针对安全&amp;合规中心的几个演练之一。</span><span class="sxs-lookup"><span data-stu-id="9df8a-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9df8a-106">若要查看其他演练, 请参阅 "[相关主题](#related-topics)" 部分。</span><span class="sxs-lookup"><span data-stu-id="9df8a-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="9df8a-107">演练: 从一个仪表板到一个洞察力</span><span class="sxs-lookup"><span data-stu-id="9df8a-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="9df8a-108">我们来看一看从仪表板到报告的流程, 直至了解和操作。</span><span class="sxs-lookup"><span data-stu-id="9df8a-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="9df8a-109">(这是一个简短的[欺骗智能](learn-about-spoof-intelligence.md)示例。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="9df8a-110">我们从[ &amp;安全合规中心](https://protection.office.com)中的安全仪表板开始。</span><span class="sxs-lookup"><span data-stu-id="9df8a-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="9df8a-111">(转到 "**威胁管理** \> "**仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="9df8a-112">![在 "安全&amp;合规性中心" 中, \>选择 "威胁管理仪表板"](media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="9df8a-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="9df8a-113">在**Insights**行中, 我们发现了一个洞察力, 表明我们需要查看一些可能可疑的域。</span><span class="sxs-lookup"><span data-stu-id="9df8a-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="9df8a-114">(在 "**见解**" 行中, 单击 "**域对**"。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="9df8a-115">![Insights 行提到了潜在的欺骗问题](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="9df8a-115">![The Insights row mentions potential spoofing concerns](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="9df8a-116">我们将获取与欺骗智能相关的活动列表。</span><span class="sxs-lookup"><span data-stu-id="9df8a-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="9df8a-117">这些实例是发送的电子邮件看起来好像来自我们的组织, 但实际上是从其他组织发送的。</span><span class="sxs-lookup"><span data-stu-id="9df8a-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="9df8a-118">目标是确定欺骗邮件是否已获得授权。</span><span class="sxs-lookup"><span data-stu-id="9df8a-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="9df8a-119">![欺骗性智能见解](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="9df8a-119">![Spoof intelligence insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="9df8a-120">在此列表中, 我们可以按邮件数、哄骗的上次检测日期等对信息进行排序。</span><span class="sxs-lookup"><span data-stu-id="9df8a-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="9df8a-121">(单击 "列标题", 如 "**邮件数**" 或**最后一次查看**的 "排序方式"。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="9df8a-122">在列表中选择一项将打开一个详细信息窗格, 我们可以在其中看到其他信息, 包括检测到的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9df8a-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="9df8a-123">(单击列表中的项目, 并查看相关信息和建议。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![选择项目时将打开一个详细信息窗格](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="9df8a-125">请注意, 在窗格顶部, 可以选择将发件人添加到组织的允许发件人列表。</span><span class="sxs-lookup"><span data-stu-id="9df8a-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="9df8a-126">(不要选择 **"添加到 ' AllowedtoSpoof ' 发件人允许列表**", 直到您确定要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9df8a-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="9df8a-127">[了解有关欺骗智能的详细信息](learn-about-spoof-intelligence.md)。)</span><span class="sxs-lookup"><span data-stu-id="9df8a-127">[Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="9df8a-128">![您可以授权发件人](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="9df8a-128">![You can authorize a sender](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="9df8a-129">通过这种方式, 我们可以从仪表板移动到真知灼见和推荐的操作。</span><span class="sxs-lookup"><span data-stu-id="9df8a-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9df8a-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="9df8a-130">Related topics</span></span>

[<span data-ttu-id="9df8a-131">演练: 从洞察力到详细报告</span><span class="sxs-lookup"><span data-stu-id="9df8a-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="9df8a-132">演练: 从详细报告到洞察力</span><span class="sxs-lookup"><span data-stu-id="9df8a-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

