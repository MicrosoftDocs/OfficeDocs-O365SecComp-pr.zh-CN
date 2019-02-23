---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已发送到用户收件箱的垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: eac984289cf5e2785e8ff61e4a3dd3e0c0d99732
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213562"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="6d50b-104">零时差自动清除 - 防范垃圾邮件和恶意软件</span><span class="sxs-lookup"><span data-stu-id="6d50b-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="6d50b-105">概述</span><span class="sxs-lookup"><span data-stu-id="6d50b-105">Overview</span></span>

<span data-ttu-id="6d50b-p102">零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已传递给用户的收件箱的包含网络钓鱼、垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。ZAP 的工作方式取决于检测到的恶意内容的类型;由于邮件内容、url 或附件, 邮件可能会 zapped。</span><span class="sxs-lookup"><span data-stu-id="6d50b-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="6d50b-108">ZAP 可与包含 exchange online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online 保护一起使用。</span><span class="sxs-lookup"><span data-stu-id="6d50b-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="6d50b-109">默认情况下, ZAP 处于打开状态, 但必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="6d50b-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="6d50b-110">**垃圾邮件操作**设置为 "**将邮件移动到垃圾邮件" 文件夹**。</span><span class="sxs-lookup"><span data-stu-id="6d50b-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="6d50b-111">您还可以创建仅适用于一组用户的新垃圾邮件筛选器策略 (如果您不希望由 ZAP 筛选所有邮箱)。</span><span class="sxs-lookup"><span data-stu-id="6d50b-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="6d50b-p103">用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。(有关 Outlook 中用户选项的详细信息, 请参阅[更改垃圾邮件筛选器中的保护级别](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)。)</span><span class="sxs-lookup"><span data-stu-id="6d50b-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="6d50b-114">ZAP 的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="6d50b-114">How does ZAP work?</span></span>

<span data-ttu-id="6d50b-p104">Office 365 每天实时更新反垃圾邮件引擎和恶意软件签名。但是, 用户仍可能会因各种原因而将恶意邮件传递到其收件箱, 其中包括在将内容传递给用户后 weaponized 内容。ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此情况。ZAP 可查找并删除已在用户收件箱中的以前传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="6d50b-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="6d50b-119">对于被标识为垃圾邮件的邮件, ZAP 将未读邮件移动到用户的 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d50b-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="6d50b-120">对于被标识为垃圾邮件的邮件, ZAP 将邮件移动到用户的垃圾邮件文件夹, 而不管是否已阅读电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6d50b-120">For mail that is identified as spam, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="6d50b-121">对于新检测到的恶意软件, ZAP 将从电子邮件中删除附件, 而不管是否已阅读电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6d50b-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="6d50b-122">对于邮箱用户, ZAP 操作是无缝的;如果移动电子邮件, 则不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="6d50b-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="6d50b-123">允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="6d50b-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="6d50b-124">查看或设置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6d50b-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="6d50b-125">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="6d50b-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="6d50b-126">在 "**威胁管理**" 下, 选择 "**反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="6d50b-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="6d50b-127">查看标准设置。</span><span class="sxs-lookup"><span data-stu-id="6d50b-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="6d50b-p105">如果要自定义设置, 请选择 "**自定义**" 选项卡, 然后打开 "**自定义设置**"。编辑设置, 如果需要, 请选择 " **+ 创建策略**" 以添加新策略。</span><span class="sxs-lookup"><span data-stu-id="6d50b-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="6d50b-130">查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="6d50b-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="6d50b-131">如果要查看 ZAP 是否移动了邮件, 可以使用 "[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)" (或 "[威胁资源管理器](use-explorer-in-security-and-compliance.md)")。</span><span class="sxs-lookup"><span data-stu-id="6d50b-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="6d50b-132">禁用 ZAP</span><span class="sxs-lookup"><span data-stu-id="6d50b-132">To disable ZAP</span></span>
  
<span data-ttu-id="6d50b-133">如果要对 Office 365 租户或一组用户禁用 ZAP, 请使用[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)的**ZapEnabled**参数 (EOP cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="6d50b-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="6d50b-134">在下面的示例中, 对名为 "Test" 的内容筛选器策略禁用了 ZAP。</span><span class="sxs-lookup"><span data-stu-id="6d50b-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="6d50b-135">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6d50b-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="6d50b-136">如果将合法邮件移动到 "垃圾邮件" 文件夹中, 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="6d50b-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="6d50b-p106">您应遵循正常的报告过程假阳性。将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是, 该服务已确定邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="6d50b-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="6d50b-139">如果我使用的是 Office 365 隔离, 而不是垃圾邮件文件夹, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="6d50b-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="6d50b-140">此时, ZAP 不会将邮件从收件箱中移入隔离区。</span><span class="sxs-lookup"><span data-stu-id="6d50b-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="6d50b-141">如果我有自定义邮件流规则 (阻止/允许规则), 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="6d50b-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="6d50b-p107">由管理员 (邮件流规则) 或阻止和允许规则创建的规则优先。将从功能条件中排除此类邮件。</span><span class="sxs-lookup"><span data-stu-id="6d50b-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6d50b-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="6d50b-144">Related Topics</span></span>

[<span data-ttu-id="6d50b-145">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="6d50b-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="6d50b-146">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="6d50b-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

