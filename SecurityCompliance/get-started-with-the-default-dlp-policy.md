---
title: 开始使用默认 DLP 策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 在创建首个数据丢失防护 (DLP) 策略之前, DLP 将帮助使用默认策略保护您的敏感信息。 此默认策略及其建议 (如下所示) 有助于在组织外部的人员共享包含信用卡号的电子邮件或文档时通知你, 以确保敏感内容的安全。
ms.openlocfilehash: fa48025a7b979ad69c600b21a10fbb62567234c3
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638939"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="83210-104">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="83210-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="83210-105">在创建首个数据丢失防护 (DLP) 策略之前, DLP 将帮助使用默认策略保护您的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="83210-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="83210-106">此默认策略及其建议 (如下所示) 有助于在组织外部的人员共享包含信用卡号的电子邮件或文档时通知你, 以确保敏感内容的安全。</span><span class="sxs-lookup"><span data-stu-id="83210-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="83210-107">你将在安全&amp;合规中心的**主页**上看到此建议。</span><span class="sxs-lookup"><span data-stu-id="83210-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="83210-108">您可以使用此小组件快速查看共享敏感信息的时间和大小, 然后只需单击一次或两次, 从而精炼默认的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="83210-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="83210-109">您还可以随时编辑默认的 DLP 策略, 因为它是完全可自定义的。</span><span class="sxs-lookup"><span data-stu-id="83210-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="83210-110">请注意, 如果最初看不到建议, 请尝试在 "**建议为你**" 部分的底部单击 " **+ 更多**"。</span><span class="sxs-lookup"><span data-stu-id="83210-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![名为 "进一步保护共享内容" 的小组件](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="83210-112">查看报告并优化默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="83210-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="83210-113">当小组件显示用户与组织外部的人员共享敏感信息时, 请选择底部的 "**优化 DLP 策略**"。</span><span class="sxs-lookup"><span data-stu-id="83210-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="83210-114">详细报告显示了在过去30天内共享包含信用卡号的内容的时间和数量。</span><span class="sxs-lookup"><span data-stu-id="83210-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="83210-115">请注意, 规则匹配最长可能需要48小时才能在小部件中显示。</span><span class="sxs-lookup"><span data-stu-id="83210-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="83210-116">为了帮助保护敏感信息, 默认的 DLP 策略为:</span><span class="sxs-lookup"><span data-stu-id="83210-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="83210-117">检测何时包含至少一个信用卡号的 Exchange、SharePoint 和 OneDrive 中的内容与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="83210-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="83210-118">显示策略提示, 并在用户尝试与组织外部的人员共享此敏感信息时向用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="83210-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="83210-119">有关这些选项的详细信息, 请参阅[发送电子邮件通知和显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="83210-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="83210-120">生成详细的活动报告, 以便您可以跟踪与组织外部的人员共享内容以及他们何时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="83210-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="83210-121">您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据](search-the-audit-log-in-security-and-compliance.md)(其中**活动** = **DLP**) 查看此信息。</span><span class="sxs-lookup"><span data-stu-id="83210-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="83210-122">若要快速优化默认的 DLP 策略, 您可以选择使用它:</span><span class="sxs-lookup"><span data-stu-id="83210-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="83210-123">当用户与组织外部的人员共享此敏感信息时, 向您发送事件报告电子邮件。</span><span class="sxs-lookup"><span data-stu-id="83210-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="83210-124">将其他用户添加到电子邮件事件报告中。</span><span class="sxs-lookup"><span data-stu-id="83210-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="83210-125">阻止访问包含敏感信息的内容, 但允许用户覆盖和共享或发送 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="83210-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="83210-126">有关事件报告或限制访问的详细信息, 请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="83210-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="83210-127">如果以后要更改这些选项, 您可以随时编辑默认的 DLP 策略-请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="83210-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![名为的小组件的设置进一步保护共享内容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="83210-129">编辑默认的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="83210-129">Edit the default DLP policy</span></span>

<span data-ttu-id="83210-130">此策略名为 "**默认 Office 365 DLP 策略**", 显示在安全&amp;合规中心的 "**策略**" 页上的 "**数据丢失防护**" 下。</span><span class="sxs-lookup"><span data-stu-id="83210-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="83210-131">此策略可完全自定义, 与你从头开始创建的任何 DLP 策略相同。</span><span class="sxs-lookup"><span data-stu-id="83210-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="83210-132">您还可以关闭或删除策略, 以便用户不再接收策略提示或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="83210-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名为 "默认 Office 365 dlp 策略" 的 dlp 策略](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="83210-134">小组件何时出现且不显示</span><span class="sxs-lookup"><span data-stu-id="83210-134">When the widget does and does not appear</span></span>

<span data-ttu-id="83210-135">"安全&amp;合规性中心"**主页**的 "**建议**" 部分会显示名为 "**进一步保护共享内容**" 的小部件。</span><span class="sxs-lookup"><span data-stu-id="83210-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="83210-136">仅在以下情况时显示此小组件:</span><span class="sxs-lookup"><span data-stu-id="83210-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="83210-137">安全&amp;合规中心或 Exchange 管理中心中没有数据丢失防护策略。</span><span class="sxs-lookup"><span data-stu-id="83210-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="83210-138">此小组件旨在帮助你开始使用 dlp, 因此如果你已具有 dlp 策略, 则不会显示它。</span><span class="sxs-lookup"><span data-stu-id="83210-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="83210-139">在过去30天内, 与组织外部的某个人共享的包含至少一张信用卡的内容已被共享。</span><span class="sxs-lookup"><span data-stu-id="83210-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="83210-140">请注意, 规则匹配最长可能需要48个小时才能用于小组件, 因此, 在检测到外部共享敏感信息后, 可能需要长达两天的时间才能显示建议。</span><span class="sxs-lookup"><span data-stu-id="83210-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="83210-141">最后, 在使用小部件优化默认的 DLP 策略后, 该小部件将从**主页**中消失。</span><span class="sxs-lookup"><span data-stu-id="83210-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

