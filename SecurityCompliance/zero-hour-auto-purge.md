---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180842"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="e7941-104">零时差自动清除 - 防范垃圾邮件和恶意软件</span><span class="sxs-lookup"><span data-stu-id="e7941-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="e7941-105">概述</span><span class="sxs-lookup"><span data-stu-id="e7941-105">Overview</span></span>

<span data-ttu-id="e7941-p102">零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，与网络钓鱼诈骗、 垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到; 恶意内容类型由于邮件内容、 Url 或附件，可以 zapped 邮件。</span><span class="sxs-lookup"><span data-stu-id="e7941-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="e7941-108">默认值是包含任何 Office 365 订阅包含 Exchange Online 邮箱的 Exchange Online Protection 提供 ZAP。</span><span class="sxs-lookup"><span data-stu-id="e7941-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="e7941-109">ZAP 已打开默认情况下，但必须满足下列条件：</span><span class="sxs-lookup"><span data-stu-id="e7941-109">ZAP is turned on by default, but the folowing conditions must be met:</span></span>
  
- <span data-ttu-id="e7941-110">**垃圾邮件操作**设置为**移动到垃圾邮件文件夹的邮件**。</span><span class="sxs-lookup"><span data-stu-id="e7941-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="e7941-111">您还可以创建仅适用于一组用户如果您不希望通过 ZAP 屏蔽所有邮箱的新垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="e7941-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="e7941-p103">用户具有保留其默认垃圾邮件设置，并不关闭垃圾邮件保护。（请参阅在 Outlook 中的用户选项的详细信息的[更改的垃圾邮件筛选保护级别](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)。）</span><span class="sxs-lookup"><span data-stu-id="e7941-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="e7941-114">ZAP 如何工作？</span><span class="sxs-lookup"><span data-stu-id="e7941-114">How does ZAP work?</span></span>

<span data-ttu-id="e7941-p104">Office 365 更新中的反垃圾邮件引擎和恶意软件签名实时每天。但是，用户可能仍获取恶意邮件传递到各种起见，如果内容 weaponized 传递给用户后包括其收件箱。将清除此通过不断监视更新到 Office 365 垃圾邮件和恶意软件签名的地址。ZAP 可以查找并删除以前发送的邮件已被用户的收件箱。</span><span class="sxs-lookup"><span data-stu-id="e7941-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="e7941-119">标识为垃圾邮件的邮件，ZAP 将未读的邮件移动到用户的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="e7941-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="e7941-120">标识为垃圾邮件的邮件，ZAP 将邮件移动到用户的垃圾邮件文件夹，而不管是否已读取电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e7941-120">For mail that is identified as spam, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="e7941-121">对于新检测到恶意软件、 ZAP 中删除附件的电子邮件，而不管是否已读取电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="e7941-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="e7941-122">ZAP 操作是无缝的邮箱用户;他们不通知如果移动电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e7941-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="e7941-123">允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="e7941-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="e7941-124">若要查看或设置的垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="e7941-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="e7941-125">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e7941-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="e7941-126">在**威胁管理**下选择**反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="e7941-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="e7941-127">查看标准的设置。</span><span class="sxs-lookup"><span data-stu-id="e7941-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="e7941-p105">如果您想要自定义设置，选择**自定义**选项卡，并打开**自定义设置**。编辑您的设置，如果您希望，选择 **+ 创建策略**添加新策略。</span><span class="sxs-lookup"><span data-stu-id="e7941-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="e7941-130">若要查看 ZAP 是否移动消息</span><span class="sxs-lookup"><span data-stu-id="e7941-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="e7941-131">如果您想要查看 ZAP 如果移动消息，您可以使用[威胁保护状态报告](view-email-security-reports.md#threat-protection-status-report-new)（或[威胁资源管理器](use-explorer-in-security-and-compliance.md)）。</span><span class="sxs-lookup"><span data-stu-id="e7941-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report-new) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="e7941-132">若要禁用 ZAP</span><span class="sxs-lookup"><span data-stu-id="e7941-132">To disable ZAP</span></span>
  
<span data-ttu-id="e7941-133">如果您想要禁用的 Office 365 租户，将清除或一组用户，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP cmdlet 的**ZapEnabled**参数。</span><span class="sxs-lookup"><span data-stu-id="e7941-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="e7941-134">在以下示例中，名为"Test"的内容筛选器策略禁用 ZAP。</span><span class="sxs-lookup"><span data-stu-id="e7941-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="e7941-135">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="e7941-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="e7941-136">如果合法邮件移动到垃圾邮件文件夹，则会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="e7941-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="e7941-p106">您应遵循的误报报告的常规过程。应为邮件将从收件箱移动到垃圾邮件文件夹的唯一原因，因为该服务已确定的消息是垃圾邮件或恶意。</span><span class="sxs-lookup"><span data-stu-id="e7941-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="e7941-139">如果使用 Office 365 隔离而不是垃圾邮件文件夹？</span><span class="sxs-lookup"><span data-stu-id="e7941-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="e7941-140">ZAP 不将邮件移动到隔离收件箱这一次。</span><span class="sxs-lookup"><span data-stu-id="e7941-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="e7941-141">如果我有自定义邮件流规则 （阻止 / 允许规则）？</span><span class="sxs-lookup"><span data-stu-id="e7941-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="e7941-p107">由管理员 （邮件流规则） 或阻止和允许规则创建的规则的优先级。此类邮件将排除在功能条件。</span><span class="sxs-lookup"><span data-stu-id="e7941-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e7941-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="e7941-144">Related Topics</span></span>

[<span data-ttu-id="e7941-145">Office 365 反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="e7941-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="e7941-146">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="e7941-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

