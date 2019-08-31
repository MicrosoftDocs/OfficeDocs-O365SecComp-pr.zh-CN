---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: 零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已发送到用户收件箱的垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。 ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: 91bb167c988e49a40895f851a518ee255abdbf08
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "36698964"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="60ad4-104">零时差自动清除 - 防范垃圾邮件和恶意软件</span><span class="sxs-lookup"><span data-stu-id="60ad4-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="60ad4-105">概述</span><span class="sxs-lookup"><span data-stu-id="60ad4-105">Overview</span></span>

<span data-ttu-id="60ad4-106">零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已传递给用户的收件箱的包含网络钓鱼、垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。</span><span class="sxs-lookup"><span data-stu-id="60ad4-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="60ad4-107">ZAP 的工作方式取决于检测到的恶意内容的类型;由于邮件内容、Url 或附件, 邮件可能会 zapped。</span><span class="sxs-lookup"><span data-stu-id="60ad4-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="60ad4-108">ZAP 可与包含 Exchange Online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online 保护一起使用。</span><span class="sxs-lookup"><span data-stu-id="60ad4-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="60ad4-109">默认情况下, ZAP 处于打开状态, 但必须满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="60ad4-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="60ad4-110">**垃圾邮件操作**设置为 "**将邮件移动到垃圾邮件" 文件夹**。</span><span class="sxs-lookup"><span data-stu-id="60ad4-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="60ad4-111">您还可以创建仅适用于一组用户的新垃圾邮件筛选器策略 (如果您不希望由 ZAP 筛选所有邮箱)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="60ad4-112">用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。</span><span class="sxs-lookup"><span data-stu-id="60ad4-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="60ad4-113">(有关 Outlook 中用户选项的详细信息, 请参阅[更改垃圾邮件筛选器中的保护级别](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。)</span><span class="sxs-lookup"><span data-stu-id="60ad4-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="60ad4-114">ZAP 的工作方式</span><span class="sxs-lookup"><span data-stu-id="60ad4-114">How ZAP works</span></span>

<span data-ttu-id="60ad4-115">Office 365 每天实时更新反垃圾邮件引擎和恶意软件签名。</span><span class="sxs-lookup"><span data-stu-id="60ad4-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="60ad4-116">但是, 用户仍可能会因各种原因而将恶意邮件传递到其收件箱, 其中包括在将内容传递给用户后 weaponized 内容。</span><span class="sxs-lookup"><span data-stu-id="60ad4-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="60ad4-117">ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此情况。</span><span class="sxs-lookup"><span data-stu-id="60ad4-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="60ad4-118">ZAP 可查找并删除已在用户收件箱中的以前传递的邮件。</span><span class="sxs-lookup"><span data-stu-id="60ad4-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="60ad4-119">对于邮箱用户, ZAP 操作是无缝的;如果移动电子邮件, 则不会收到通知。</span><span class="sxs-lookup"><span data-stu-id="60ad4-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="60ad4-120">消息不得早于2天。</span><span class="sxs-lookup"><span data-stu-id="60ad4-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="60ad4-121">允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)(也称为传输规则) 和最终用户规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="60ad4-122">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="60ad4-122">Malware ZAP</span></span>

<span data-ttu-id="60ad4-123">对于新检测到的恶意软件, ZAP 将从电子邮件中删除附件, 并将邮件正文保留在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="60ad4-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="60ad4-124">无论邮件的阅读状态如何, 都会删除附件。</span><span class="sxs-lookup"><span data-stu-id="60ad4-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="60ad4-125">在恶意软件策略中, 默认情况下会启用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="60ad4-126">您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet 上的*ZapEnabled*参数禁用恶意软件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="60ad4-127">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="60ad4-127">Phish ZAP</span></span>

<span data-ttu-id="60ad4-128">对于在传递后被标识为网络钓鱼的邮件, ZAP 将根据用户所涵盖的垃圾邮件策略采取措施。</span><span class="sxs-lookup"><span data-stu-id="60ad4-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="60ad4-129">如果将策略网络钓鱼操作设置为对邮件执行操作 (重定向、删除、隔离、移动到垃圾), 则 ZAP 会将邮件移动到用户收件箱的 "垃圾邮件" 文件夹, 而不管邮件的阅读状态如何。</span><span class="sxs-lookup"><span data-stu-id="60ad4-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="60ad4-130">如果策略网络钓鱼操作未设置为 "采取操作" (添加 X 标头、"修改主题"、"无操作"), 则 ZAP 不会对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="60ad4-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="60ad4-131">了解有关如何在此处[配置垃圾邮件筛选器策略](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60ad4-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="60ad4-132">默认情况下, 会在垃圾邮件策略中启用网络钓鱼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="60ad4-133">您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet 上的*ZapEnabled*参数禁用网络钓鱼 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="60ad4-134">垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="60ad4-134">Spam ZAP</span></span>

<span data-ttu-id="60ad4-135">对于在传递后被标识为垃圾邮件的邮件, ZAP 将根据用户所涵盖的垃圾邮件策略采取措施。</span><span class="sxs-lookup"><span data-stu-id="60ad4-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="60ad4-136">如果 "策略垃圾邮件" 操作设置为 "对邮件执行操作 (重定向、删除、隔离、移动到垃圾)", 则 ZAP 会将邮件移到用户收件箱的 "垃圾邮件" 文件夹中 (如果该邮件未读)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="60ad4-137">如果策略垃圾操作未设置为 "采取操作" (添加 X 标头、"修改主题"、"无操作"), 则 ZAP 不会对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="60ad4-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="60ad4-138">了解有关如何在此处[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="60ad4-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="60ad4-139">垃圾邮件策略中默认启用垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="60ad4-140">您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) Cmdlet 的*ZapEnabled*参数禁用垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="60ad4-141">**Set-hostedcontentfilterpolicy** cmdlet 上的*ZapEnabled*参数将禁用或启用此策略的网络钓鱼 ZAP 和垃圾邮件 zap。</span><span class="sxs-lookup"><span data-stu-id="60ad4-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="60ad4-142">您不能在同一策略中单独启用或禁用网络钓鱼 ZAP 和垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="60ad4-143">如何查看 ZAP 是否移动了邮件</span><span class="sxs-lookup"><span data-stu-id="60ad4-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="60ad4-144">若要确定 ZAP 是否移动了邮件, 可以使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)或[威胁浏览器 (和实时检测)](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="60ad4-145">禁用 ZAP</span><span class="sxs-lookup"><span data-stu-id="60ad4-145">Disable ZAP</span></span>

<span data-ttu-id="60ad4-146">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="60ad4-147">若要连接到 Exchange Online Protection PowerShell, 请参阅[连接到 Exchange Online Protection powershell](https://go.microsoft.com/fwlink/p/?linkid=627290)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="60ad4-148">禁用恶意软件 ZAP \* \*</span><span class="sxs-lookup"><span data-stu-id="60ad4-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="60ad4-149">此示例在名为 "Test" 的恶意软件筛选器策略中禁用 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="60ad4-150">有关语法和参数的详细信息, 请参阅[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="60ad4-151">禁用网络钓鱼 ZAP 和垃圾邮件 ZAP</span><span class="sxs-lookup"><span data-stu-id="60ad4-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="60ad4-152">此示例在名为 "Test" 的内容筛选器策略中禁用了网络钓鱼 ZAP 和垃圾邮件 ZAP。</span><span class="sxs-lookup"><span data-stu-id="60ad4-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="60ad4-153">有关语法和参数的详细信息, 请参阅[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="60ad4-154">常见问题</span><span class="sxs-lookup"><span data-stu-id="60ad4-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="60ad4-155">如果将合法邮件移动到 "垃圾邮件" 文件夹中, 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="60ad4-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="60ad4-156">您应遵循正常的报告过程[假阳性](prevent-email-from-being-marked-as-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-156">You should follow the normal reporting process for [false-positives](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="60ad4-157">将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是, 该服务已确定邮件是垃圾邮件还是恶意邮件。</span><span class="sxs-lookup"><span data-stu-id="60ad4-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="60ad4-158">如果我使用的是 Office 365 隔离, 而不是垃圾邮件文件夹, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="60ad4-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="60ad4-159">此时, ZAP 不会将邮件从收件箱中移入隔离区。</span><span class="sxs-lookup"><span data-stu-id="60ad4-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="60ad4-160">如果我有自定义邮件流规则 (阻止/允许规则), 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="60ad4-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="60ad4-161">由管理员 (邮件流规则) 或阻止和允许规则创建的规则优先。</span><span class="sxs-lookup"><span data-stu-id="60ad4-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="60ad4-162">将从功能条件中排除此类邮件, 以便邮件流遵循规则操作 (阻止/允许规则)。</span><span class="sxs-lookup"><span data-stu-id="60ad4-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="60ad4-163">如果邮件被移到另一个文件夹 (例如收件箱规则), 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="60ad4-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="60ad4-164">在这种情况下, ZAP 仍适用, 除非邮件已被删除或在垃圾邮件中。</span><span class="sxs-lookup"><span data-stu-id="60ad4-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="60ad4-165">相关主题</span><span class="sxs-lookup"><span data-stu-id="60ad4-165">Related Topics</span></span>

[<span data-ttu-id="60ad4-166">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="60ad4-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="60ad4-167">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="60ad4-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
