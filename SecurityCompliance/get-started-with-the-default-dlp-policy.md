---
title: 开始使用默认 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/10/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
description: 您甚至创建第一个数据丢失防护 (DLP) 策略之前，DLP 帮助保护您的敏感信息与默认策略。此默认策略和敏感内容安全的电子邮件或文档包含 credit 卡片号码时通知您已与您的组织外部的某个人共享其建议 （如下所示） 帮助保留。
ms.openlocfilehash: 1b522a2c04e72353970ef5dfcd62183023a01994
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526067"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="876da-104">开始使用默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="876da-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="876da-p102">您甚至创建第一个数据丢失防护 (DLP) 策略之前，DLP 帮助保护您的敏感信息与默认策略。此默认策略和敏感内容安全的电子邮件或文档包含 credit 卡片号码时通知您已与您的组织外部的某个人共享其建议 （如下所示） 帮助保留。您将看到此建议的安全**主页**页上&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="876da-p102">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy. This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization. You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="876da-p103">您可以使用此小部件若要快速查看何时以及共享多少敏感信息，然后优化中只需单击一两的默认 DLP 策略。因为它是完全可自定义，您还可以随时编辑默认 DLP 策略。请注意，如果您看不到开始时，建议您尝试单击 **+ 详细**底部的**为您的推荐**部分。</span><span class="sxs-lookup"><span data-stu-id="876da-p103">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two. You can also edit the default DLP policy at any time because it's fully customizable. Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![小部件名为进一步保护共享的内容](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="876da-112">查看报告，并优化默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="876da-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="876da-113">当小部件显示用户具有与组织外部的人员共享敏感信息时，请选择底部**优化 DLP 策略**。</span><span class="sxs-lookup"><span data-stu-id="876da-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="876da-p104">详细的报告将显示过去 30 天中的时间和方式共享已包含信用卡号的内容量。注意规则匹配项可能需要 48 小时小部件中显示。</span><span class="sxs-lookup"><span data-stu-id="876da-p104">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days. Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="876da-116">若要帮助保护敏感信息，默认 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="876da-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="876da-117">检测何时 Exchange、 SharePoint 和包含至少一个信用卡号的 OneDrive 中的内容与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="876da-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="876da-p105">显示策略提示，并在尝试与组织外部的人员共享此敏感信息时向用户发送的电子邮件通知。有关这些选项的详细信息，请参阅[发送电子邮件通知和显示策略提示的 DLP 策略](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="876da-p105">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization. For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="876da-p106">生成详细的活动报告，以便您可以跟踪人员与组织外部的人员共享内容和他们是何时等内容。您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据](search-the-audit-log-in-security-and-compliance.md)(其中**活动** = **DLP**) 以查看此信息。</span><span class="sxs-lookup"><span data-stu-id="876da-p106">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it. You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="876da-122">若要快速细化默认 DLP 策略，您可以选择已：</span><span class="sxs-lookup"><span data-stu-id="876da-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="876da-123">请向您发送事件报告电子邮件时用户与组织外部的人员共享此敏感信息。</span><span class="sxs-lookup"><span data-stu-id="876da-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="876da-124">将其他用户添加到电子邮件事件报告。</span><span class="sxs-lookup"><span data-stu-id="876da-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="876da-125">阻止对包含敏感信息的内容的访问，但允许用户重写并共享或发送如果需。</span><span class="sxs-lookup"><span data-stu-id="876da-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="876da-126">有关事件报告或限制访问的详细信息，请参阅[Overview of 数据丢失预防策略](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="876da-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="876da-127">如果您想要稍后更改这些选项，您可以编辑默认随时-DLP 策略，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="876da-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![设置小部件名为进一步保护共享的内容](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="876da-129">编辑默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="876da-129">Edit the default DLP policy</span></span>

<span data-ttu-id="876da-130">此策略名为**默认的 Office 365 DLP 策略**，并显示在**策略**页的安全**数据丢失防护**下方&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="876da-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="876da-p107">此策略可完全自定义，任何，从头开始创建您自己的 DLP 策略相同。您还可以关闭或删除策略，以便用户无法再接收策略提示或发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="876da-p107">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch. You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名为默认的 Office 365 DLP 策略的 DLP 策略](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="876da-134">小部件时执行，不显示</span><span class="sxs-lookup"><span data-stu-id="876da-134">When the widget does and does not appear</span></span>

<span data-ttu-id="876da-135">名为**进一步保护共享的内容**小部件将显示在**主页**页的安全**为您的推荐**部分&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="876da-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="876da-136">此小部件时才显示：</span><span class="sxs-lookup"><span data-stu-id="876da-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="876da-p108">安全中有无数据丢失预防策略&amp;合规性中心或 Exchange Admin Center。此小部件旨在帮助您开始使用 DLP，因此它不出现如果您已有 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="876da-p108">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange Admin Center. This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="876da-139">已与您的组织在过去 30 天内外部的某个人共享内容包含至少一个信用卡。</span><span class="sxs-lookup"><span data-stu-id="876da-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="876da-140">注意规则匹配项可能需要 48 小时可对小部件，因此检测到外部共享的敏感信息后，可能需要两天显示的建议。</span><span class="sxs-lookup"><span data-stu-id="876da-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="876da-141">最后，小部件用于优化默认 DLP 策略后，将从**主页**页消失小部件。</span><span class="sxs-lookup"><span data-stu-id="876da-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

