---
title: Office 365 中的防欺骗保护
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: 本文介绍如何 Office 365 缓解了对网络钓鱼攻击使用伪造发件人域，即，造假的域。这是通过实现通过分析邮件和阻止的那些类型的值可以是经过 neithe 身份验证通过使用标准电子邮件身份验证方法，也其他发件人信誉方法。实现此更改是为了减少向公开 Office 365 中的组织的网络钓鱼攻击的数。
ms.openlocfilehash: 19e7ea957592a486a559dac222a51139bf79b574
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769856"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="6819e-105">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="6819e-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="6819e-p102">本文介绍如何 Office 365 缓解了对网络钓鱼攻击使用伪造发件人域，即，造假的域。它来实现此通过分析邮件和阻止的无法使用标准电子邮件身份验证方法，也其他发件人信誉技术身份验证。实现此更改是为了减少向公开客户的网络钓鱼攻击的数。</span><span class="sxs-lookup"><span data-stu-id="6819e-p102">This article describes how Office 365 mitigates against phishing attacks that uses forged sender domains, that is, domains that are spoofed. It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques. This change is being implemented to reduce the number of phishing attacks customers are exposed to.</span></span>
  
<span data-ttu-id="6819e-109">本文还介绍了为什么要进行此更改、 客户如何准备此更改、 如何查看将受影响的邮件，如何对邮件报告、 如何缓解误报，以及发件人向 Microsoft 对此应做好准备发生更改。</span><span class="sxs-lookup"><span data-stu-id="6819e-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="6819e-p103">Microsoft 的反欺骗技术已最初部署到其组织的 Office 365 企业 E5 订阅或已购买 Office 365 高级威胁保护 (ATP) 加载项为其订阅。从 2018 年 10 月，我们已扩展到以及具有 Exchange Online Protection (EOP) 的组织的保护。此外，由于我们筛选器的所有相互学习的方式，Outlook.com 用户也可能受到影响。</span><span class="sxs-lookup"><span data-stu-id="6819e-p103">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="6819e-113">如何欺骗网络钓鱼攻击中使用</span><span class="sxs-lookup"><span data-stu-id="6819e-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="6819e-p104">当谈到保护用户时，Microsoft 非常重视网络钓鱼的威胁。垃圾邮件和网络钓鱼者常使用的方法之一欺骗，这时伪造是发件人，并显示一条消息以源自从某人或其他地方之外的实际的源。在设计用来获取用户凭据的网络钓鱼活动中通常使用此技术。Microsoft 的反欺骗技术专门检查伪造的从： 标头这是如 Outlook 电子邮件客户端中显示的一个。当 Microsoft 具有高可信度的 From： 造假标头，它标识为欺骗的消息。</span><span class="sxs-lookup"><span data-stu-id="6819e-p104">When it comes to protecting its users, Microsoft takes the threat of phishing seriously. One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source. This technique is often used in phishing campaigns designed to obtain user credentials. Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook. When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="6819e-119">欺骗邮件都具有两个负面影响所作的实际用户：</span><span class="sxs-lookup"><span data-stu-id="6819e-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="6819e-120">1.欺骗邮件欺骗用户</span><span class="sxs-lookup"><span data-stu-id="6819e-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="6819e-p105">首先，带欺骗性的消息可能会诱使用户单击的链接和放弃其凭据、 下载恶意软件，或答复邮件包含敏感内容 （后一种称为业务电子邮件威胁）。例如，下面是网络钓鱼邮件 msoutlook94@service.outlook.com 欺骗发件人为：</span><span class="sxs-lookup"><span data-stu-id="6819e-p105">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise). For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![网络钓鱼邮件模拟 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="6819e-p106">上述并不实际来自于 service.outlook.com，但网络钓鱼者以使其看一样而被盗用。正在尝试诱使用户单击消息中的链接。</span><span class="sxs-lookup"><span data-stu-id="6819e-p106">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did. It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="6819e-126">下一个示例欺骗 contoso.com:</span><span class="sxs-lookup"><span data-stu-id="6819e-126">The next example is spoofing contoso.com:</span></span>
  
![网络钓鱼邮件的业务电子邮件威胁](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="6819e-p107">消息看起来是合法，但实际上是欺骗。此网络钓鱼邮件是一种类型的业务电子邮件威胁即网络钓鱼的子类别。</span><span class="sxs-lookup"><span data-stu-id="6819e-p107">The message looks legitimate, but in fact is a spoof. This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="6819e-130">2.用户将混淆假结构的实际邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="6819e-p108">第二个、 带欺骗性消息创建用户了解网络钓鱼邮件，但无法判断实际消息和欺骗的一个之间的差异的不的确定性。例如，以下是从 Microsoft 安全帐户的电子邮件地址重置实际密码的示例：</span><span class="sxs-lookup"><span data-stu-id="6819e-p108">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one. For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法密码重置](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="6819e-p109">上面的消息未来自 Microsoft，但同时，用户将用来获取网络钓鱼邮件的可能会诱使用户单击的链接和放弃其凭据、 下载恶意软件，或答复邮件包含敏感内容。因为很难告知实际密码重置和一个虚假之间的差异，很多用户忽略这些消息、 将其报告为垃圾邮件，或不必要地邮件后向 Microsoft 报告为错过网络钓鱼诈骗。</span><span class="sxs-lookup"><span data-stu-id="6819e-p109">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content. Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>
    
<span data-ttu-id="6819e-p110">若要停止欺骗，电子邮件筛选行业开发了[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)，等[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)电子邮件身份验证协议。DMARC 阻止欺骗检查邮件的发件人-用户看到其电子邮件客户端中的一个 （在上述示例中，这是 service.outlook.com、 outlook.com 和 accountprotection.microsoft.com）-使用 SPF 或 DKIM 传递的域。即，用户看到的域已经过身份验证，因此不被篡改。有关更全面讨论，请参阅"*了解为什么电子邮件身份验证并不总是足以停止欺骗"* 本文档中的更高版本上。</span><span class="sxs-lookup"><span data-stu-id="6819e-p110">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM. That is, the domain that the user sees has been authenticated and is therefore not spoofed. For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this document.</span></span> 
  
<span data-ttu-id="6819e-p111">但是，问题在于该记录是可选的不需要的电子邮件身份验证。因此，同时使用强身份验证策略的域 like microsoft.com ヘ skype.com シ シ 术从欺骗的所有发布较弱的身份验证策略或无策略，是正在造假的目标域。从年 3 月 2018年只有 9%的域中财富 500 的公司的发布强的电子邮件身份验证策略。剩余的 91%可能被钓鱼欺骗和除非电子邮件筛选器检测到它使用其他策略可能会传递给最终用户和欺骗它们：</span><span class="sxs-lookup"><span data-stu-id="6819e-p111">However, the problem is that email authentication records are optional, not required. Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies. The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![DMARC 策略的财富 500 公司](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="6819e-144">小型到中型调整公司的比例不在发布强的电子邮件身份验证策略财富 500 是较小，和较小仍北美和西欧之外的域。</span><span class="sxs-lookup"><span data-stu-id="6819e-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="6819e-145">这是一个大问题，因为网络钓鱼者时企业可能不知道的电子邮件身份验证的工作方式，执行了解并充分利用缺乏。</span><span class="sxs-lookup"><span data-stu-id="6819e-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="6819e-146">SPF、 DKIM 和 DMARC 设置的信息，请参阅部分"本文档中的更高版本上*的 Office 365" 的客户*。</span><span class="sxs-lookup"><span data-stu-id="6819e-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="6819e-147">停止欺骗隐式电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="6819e-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="6819e-p112">由于网络钓鱼和矛网络钓鱼此类问题，且强的电子邮件身份验证策略的有限采用，因为 Microsoft 不断功能保护其客户购买。因此，Microsoft 将使用*隐式电子邮件身份验证*-提前移如果域不进行身份验证，Microsoft 将将其视为它具有发布电子邮件身份验证记录和将其视为相应地，如果它不传递。</span><span class="sxs-lookup"><span data-stu-id="6819e-p112">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers. Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="6819e-p113">若要实现此目的，Microsoft 已经构建了大量扩展正则电子邮件身份验证包括发件人信誉、 发件人/收件人历史记录、 行为的分析和其他高级的技术。不发布电子邮件身份验证的域发送的消息将标记为欺骗除非它包含其他信号以指明它是合法。</span><span class="sxs-lookup"><span data-stu-id="6819e-p113">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques. A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="6819e-152">这样，最终用户可以向其发送电子邮件不伪造可信度，发件人可以确信没有人正在模拟他们的域和 Office 365 的客户可以提供更好的保护，如模拟保护。</span><span class="sxs-lookup"><span data-stu-id="6819e-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="6819e-153">若要查看 Microsoft 的常规通知，请参阅[Sea 的网络钓鱼诈骗第 2 部分-Office 365 中的增强反欺骗](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。</span><span class="sxs-lookup"><span data-stu-id="6819e-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="6819e-154">标识一条消息被归类为造假</span><span class="sxs-lookup"><span data-stu-id="6819e-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="6819e-155">复合身份验证</span><span class="sxs-lookup"><span data-stu-id="6819e-155">Composite authentication</span></span>

<span data-ttu-id="6819e-p114">时 SPF、 DKIM 和 DMARC 所有有用本身，它们不在事件消息的产生任何显式身份验证记录通信足够身份验证状态。因此，Microsoft 开发了将多个信号合并为单个值调用 short 复合身份验证或 compauth 算法。Office 365 中的客户具有到邮件头中的*身份验证结果*页眉标 compauth 值。</span><span class="sxs-lookup"><span data-stu-id="6819e-p114">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records. Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short. Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="6819e-159">**CompAuth 结果**</span><span class="sxs-lookup"><span data-stu-id="6819e-159">**CompAuth result**</span></span>|<span data-ttu-id="6819e-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="6819e-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6819e-161">失败</span><span class="sxs-lookup"><span data-stu-id="6819e-161">fail</span></span>|<span data-ttu-id="6819e-162">邮件无法显式身份验证 （发送域发布记录显式在 DNS 中） 或隐式身份验证 （发送以便 Office 365 内结果，就好像它具有发布记录域未在 DNS 中，发布记录）。</span><span class="sxs-lookup"><span data-stu-id="6819e-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="6819e-163">传递</span><span class="sxs-lookup"><span data-stu-id="6819e-163">pass</span></span>|<span data-ttu-id="6819e-164">消息传递显式身份验证 （消息传递 DMARC 或[最佳猜测传递 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或使用高可信度隐式身份验证 （发送域不发布电子邮件身份验证记录，但 Office 365 具有强的后端信号以指明消息可能合法)。</span><span class="sxs-lookup"><span data-stu-id="6819e-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="6819e-165">softpass</span><span class="sxs-lookup"><span data-stu-id="6819e-165">softpass</span></span>|<span data-ttu-id="6819e-166">消息传递低到中级自信地隐式身份验证 （发送域不发布电子邮件身份验证，但 Office 365 具有后端信号，以指示邮件是合法但较弱的信号的均强度）。</span><span class="sxs-lookup"><span data-stu-id="6819e-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="6819e-167">无</span><span class="sxs-lookup"><span data-stu-id="6819e-167">none</span></span>|<span data-ttu-id="6819e-168">邮件未通过验证 （或者未进行身份验证但未在对齐），但不是应用由于发件人信誉或其他因素的复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="6819e-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="6819e-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="6819e-169">**Reason**</span></span>|<span data-ttu-id="6819e-170">**说明**</span><span class="sxs-lookup"><span data-stu-id="6819e-170">**Description**</span></span>|
|<span data-ttu-id="6819e-171">0xx</span><span class="sxs-lookup"><span data-stu-id="6819e-171">0xx</span></span>|<span data-ttu-id="6819e-172">消息失败复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="6819e-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="6819e-p115">**000**意味着 DMARC 与拒绝或隔离操作失败的消息。                   -001 意味着隐式电子邮件身份验证失败的消息。这意味着的发送域没有电子邮件身份验证记录发布，或者如果那样，它们必须较弱的失败策略 (SPF 软故障或 neutral，DMARC 策略的 p = none)。</span><span class="sxs-lookup"><span data-stu-id="6819e-p115">**000** means the message failed DMARC with an action of reject or quarantine.                    - 001 means the message failed implicit email authentication. This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).  </span></span><br/><span data-ttu-id="6819e-176">**002**表示组织具有显式禁止发送带欺骗性的电子邮件的发件人/域对的策略，由管理员手动设置此设置。</span><span class="sxs-lookup"><span data-stu-id="6819e-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="6819e-177">**010**表示 DMARC 与拒绝或隔离，操作失败的消息并发送域是您组织的接受域之一 (这是自签名自我或组织内的一部分欺骗)。</span><span class="sxs-lookup"><span data-stu-id="6819e-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="6819e-178">**011**表示隐式电子邮件身份验证失败的消息并发送域是您组织的接受域之一 (这是自签名自我或组织内的一部分欺骗)。</span><span class="sxs-lookup"><span data-stu-id="6819e-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="6819e-179">所有其他代码 （1xx 2xx、 3xx、 4xx、 5xx）</span><span class="sxs-lookup"><span data-stu-id="6819e-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="6819e-180">为什么一条消息传递隐式身份验证，或具有任何身份验证但不应用任何操作对应的各种内部代码。</span><span class="sxs-lookup"><span data-stu-id="6819e-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="6819e-181">通过查看邮件的标头，管理员或甚至最终用户将可以确定 Office 365 如何到达发件人可能具有欺骗性组成部分。</span><span class="sxs-lookup"><span data-stu-id="6819e-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="6819e-182">区分不同类型的欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="6819e-183">Microsoft 区分两种不同类型的欺骗消息：</span><span class="sxs-lookup"><span data-stu-id="6819e-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="6819e-184">**组织内欺骗**</span><span class="sxs-lookup"><span data-stu-id="6819e-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="6819e-185">也称为自我到自我欺骗时，发生这种情况时在从域： 地址相同，或与收件人域 （当收件人的域为贵组织的[接受域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)之一）; 对齐或者，当在从域： 地址属于同一组织。</span><span class="sxs-lookup"><span data-stu-id="6819e-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="6819e-p116">例如，以下包含发件人和收件人来自同一个域 (contoso.com)。空格插入到电子邮件地址，以防止此页上的 spambot 网络）：</span><span class="sxs-lookup"><span data-stu-id="6819e-p116">For example, the following has sender and recipient from the same domain (contoso.com). Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="6819e-188">从： 发件人 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="6819e-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="6819e-189">收件人: @ contoso.com 的收件人</span><span class="sxs-lookup"><span data-stu-id="6819e-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="6819e-190">以下具有与组织的域 (fabrikam.com) 对齐的发件人和收件人的域：</span><span class="sxs-lookup"><span data-stu-id="6819e-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="6819e-191">从： 发件人 @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="6819e-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="6819e-192">收件人: @ bar.fabrikam.com 收件人</span><span class="sxs-lookup"><span data-stu-id="6819e-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="6819e-193">下列发件人和收件人域不相同 （microsoft.com 和 bing.com），但属于同一组织 （即，两者都是组织的接受域的一部分）：</span><span class="sxs-lookup"><span data-stu-id="6819e-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="6819e-194">从： 发件人 @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6819e-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="6819e-195">收件人: @ bing.com 收件人</span><span class="sxs-lookup"><span data-stu-id="6819e-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="6819e-196">失败欺骗组织内的邮件包含头中的以下值：</span><span class="sxs-lookup"><span data-stu-id="6819e-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="6819e-197">X Forefront 反垃圾邮件报告:...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="6819e-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="6819e-198">CAT is 消息的类别和它通常标为 SPM （垃圾邮件），但有时是 HSPM （高可信度垃圾邮件） 或网络钓鱼 （网络钓鱼） 具体取决于哪些其他类型的模式中可能会出现该邮件。</span><span class="sxs-lookup"><span data-stu-id="6819e-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="6819e-199">SFTY 是邮件的安全级别、 第一个数字 (9) 表示邮件是网络钓鱼，以及另一位数字后点 (11) 意味着它为组织内欺骗。</span><span class="sxs-lookup"><span data-stu-id="6819e-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="6819e-200">没有为复合身份验证组织内欺骗，都将标后面 2018 （尚未定义时间线） 的具体原因代码。</span><span class="sxs-lookup"><span data-stu-id="6819e-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="6819e-201">**跨域欺骗**</span><span class="sxs-lookup"><span data-stu-id="6819e-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="6819e-p117">发生这种情况时在从的发送域： 地址是到接收组织外部域。由于跨域欺骗失败复合身份验证的邮件包含头中的以下值：</span><span class="sxs-lookup"><span data-stu-id="6819e-p117">This occurs when the sending domain in the From: address is an external domain to the receiving organization. Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="6819e-p118">身份验证结果:...compauth = 失败原因 = 000/001</span><span class="sxs-lookup"><span data-stu-id="6819e-p118">Authentication-Results: … compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="6819e-206">X Forefront 反垃圾邮件报告:...CAT:SPOOF;...SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="6819e-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="6819e-207">在这两种情况下，以下红色安全提示被标邮件或为自定义为收件人邮箱的语言的等效项中：</span><span class="sxs-lookup"><span data-stu-id="6819e-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![红色安全提示-欺诈检测](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="6819e-209">它只是看 From： 地址和知道您收件人的电子邮件什么，或按检查电子邮件的标头，您可以区分组织内和跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="6819e-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="6819e-210">Office 365 的客户可以如何准备自己的新反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="6819e-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="6819e-211">管理员的的信息</span><span class="sxs-lookup"><span data-stu-id="6819e-211">Information for administrators</span></span>

<span data-ttu-id="6819e-212">作为 Office 365 中组织的管理员，有几个关键您应了解的信息。</span><span class="sxs-lookup"><span data-stu-id="6819e-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="6819e-213">了解为什么电子邮件身份验证并不总是足以停止欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="6819e-p119">新反欺骗保护依赖于电子邮件身份验证 （SPF、 DKIM 和 DMARC），不标记为欺骗邮件。发送域已从不发布 SPF 记录时的常见示例。如果没有 SPF 记录或他们不正确设置，则已发送的邮件将被标记为造假除非 Microsoft 具有指示邮件是合法的后端智能。</span><span class="sxs-lookup"><span data-stu-id="6819e-p119">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing. A common example is when a sending domain has never published SPF records. If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="6819e-217">例如，反欺骗正在部署前, 一条消息可能类似没有 SPF 记录，没有 DKIM 记录，与没有 DMARC 记录以下：</span><span class="sxs-lookup"><span data-stu-id="6819e-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="6819e-218">后反欺骗，如果您具有 Office 365 企业 E5、 EOP 或 ATP，被标 compauth 值：</span><span class="sxs-lookup"><span data-stu-id="6819e-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="6819e-219">如果 example.com 解决这设置 SPF 记录，但不是一个 DKIM 记录，因为传递 SPF 的域与源中的域对齐，这将传递复合身份验证： 地址：</span><span class="sxs-lookup"><span data-stu-id="6819e-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="6819e-220">或者，如果他们设置 DKIM 记录，但不是 SPF 记录，这会因为传递 DKIM 签名中的域与源中的域对齐地还通过复合身份验证： 地址：</span><span class="sxs-lookup"><span data-stu-id="6819e-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="6819e-p120">然而，钓鱼可能还设置 SPF 和 DKIM，签名邮件自己域，但在从指定不同的域： 地址。SPF 和 DKIM 都不需要符合在从域的域： 解决，除非 example.com 发布 DMARC 记录，这会将标记为使用 DMARC 欺骗，因此：</span><span class="sxs-lookup"><span data-stu-id="6819e-p120">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address. Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="6819e-223">在电子邮件客户端 (Outlook，在 web 或任何其他电子邮件客户端上的 Outlook)，仅从： 显示域、 不是在域中 SPF 或 DKIM，并且会以为消息来自 example.com，但实际上是来自 maliciousDomain.com 误导用户.</span><span class="sxs-lookup"><span data-stu-id="6819e-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![经过身份验证的消息，但从： 域未与什么传递 SPF 或 DKIM 对齐](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="6819e-p121">因此，Office 365 需要在从域： 与 SPF 或 DKIM 签名中的域对齐地址和邮件如果它不，包含指示的某些其他内部信号是合法。否则，该消息将是 compauth 失败。</span><span class="sxs-lookup"><span data-stu-id="6819e-p121">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate. Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="6819e-p122">因此，Office 365 反欺骗保护与无身份验证的域和设置身份验证，但不匹配，针对在从域的域： 地址，它是一个用户看到和认为是邮件的发件人。这是这两种为贵组织中的域或组织外部的域，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="6819e-p122">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message. This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="6819e-229">因此，如果您曾收到一条消息，复合身份验证失败和标记为造假，即使邮件传递 SPF 和 DKIM，这是因为传递 SPF 和 DKIM 域不符合在从域： 地址。</span><span class="sxs-lookup"><span data-stu-id="6819e-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="6819e-230">了解如何欺骗电子邮件中的更改被视为</span><span class="sxs-lookup"><span data-stu-id="6819e-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="6819e-p123">目前，所有组织中 Office 365-ATP 和非-ATP-消息 DMARC 与拒绝或隔离的策略标记为垃圾邮件和通常需要高可信度垃圾邮件操作，或有时正则垃圾邮件操作的失败 (具体取决于其他垃圾邮件规则首先标识为垃圾邮件）。组织内欺骗检测执行常规垃圾邮件的操作。此行为不需要启用，也可以禁用。</span><span class="sxs-lookup"><span data-stu-id="6819e-p123">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam). Intra-org spoof detections take the regular spam action. This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="6819e-p124">但是的跨域欺骗邮件之前此更改它们经过正则垃圾邮件和网络钓鱼诈骗、 恶意软件检查并如果筛选器的其他部件将它们标识为可疑，会将它们标记为垃圾邮件、 网络钓鱼诈骗、 或恶意软件分别。通过使用新的跨域欺骗保护，无法进行身份验证的任何消息，默认情况下，需要防钓鱼中定义的操作\>防欺骗策略。如果未定义，它将移动到用户的垃圾邮件文件夹。在某些情况下，更可疑邮件还必须添加到邮件中的红色安全提示。</span><span class="sxs-lookup"><span data-stu-id="6819e-p124">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively. With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy. If one is not defined, it will be moved to a users Junk Email folder. In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="6819e-p125">这可能会导致先前已标记为垃圾邮件仍获取标记为垃圾邮件，但现在还具有红色安全提示; 某些消息在其他情况下，添加先前已标记为非垃圾邮件将开始获取标记为垃圾邮件 (CAT:SPOOF) 的红色安全提示信息的邮件。在仍其他情况下，已将所有垃圾邮件和网络钓鱼诈骗移动到隔离邮箱的客户将立即看到到垃圾邮件文件夹将其 （此行为可更改，请参阅[更改反欺骗设置](#changing-your-anti-spoofing-settings)）。</span><span class="sxs-lookup"><span data-stu-id="6819e-p125">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added. In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="6819e-p126">有多种不同的方式可以 （请参阅上文中的[不同类型的欺骗之间 Differentiating](#differentiating-between-different-types-of-spoofing) ） 欺骗一条消息，但年 3 月 2018年从 Office 365 将这些邮件处理的方式不尚未统一。下表是摘要，使用跨域欺骗保护正在新行为：</span><span class="sxs-lookup"><span data-stu-id="6819e-p126">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified. The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="6819e-242">**欺骗的类型**</span><span class="sxs-lookup"><span data-stu-id="6819e-242">**Type of spoof**</span></span>|<span data-ttu-id="6819e-243">**类别**</span><span class="sxs-lookup"><span data-stu-id="6819e-243">**Category**</span></span>|<span data-ttu-id="6819e-244">**添加的安全提示？**</span><span class="sxs-lookup"><span data-stu-id="6819e-244">**Safety tip added?**</span></span>|<span data-ttu-id="6819e-245">**应用于**</span><span class="sxs-lookup"><span data-stu-id="6819e-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6819e-246">DMARC 失败 （隔离或拒绝）</span><span class="sxs-lookup"><span data-stu-id="6819e-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="6819e-247">HSPM （默认），也可能会 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="6819e-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="6819e-248">否 （尚未）</span><span class="sxs-lookup"><span data-stu-id="6819e-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="6819e-249">所有 Office 365 客户 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="6819e-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="6819e-250">自我到自我</span><span class="sxs-lookup"><span data-stu-id="6819e-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="6819e-251">SPM</span><span class="sxs-lookup"><span data-stu-id="6819e-251">SPM</span></span>  <br/> |<span data-ttu-id="6819e-252">是</span><span class="sxs-lookup"><span data-stu-id="6819e-252">Yes</span></span>  <br/> |<span data-ttu-id="6819e-253">所有 Office 365 组织 Outlook.com</span><span class="sxs-lookup"><span data-stu-id="6819e-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="6819e-254">跨域</span><span class="sxs-lookup"><span data-stu-id="6819e-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="6819e-255">欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-255">SPOOF</span></span>  <br/> |<span data-ttu-id="6819e-256">是</span><span class="sxs-lookup"><span data-stu-id="6819e-256">Yes</span></span>  <br/> |<span data-ttu-id="6819e-257">Office 365 高级威胁保护和 E5 客户</span><span class="sxs-lookup"><span data-stu-id="6819e-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="6819e-258">更改反欺骗设置</span><span class="sxs-lookup"><span data-stu-id="6819e-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="6819e-p127">若要创建或更新 （跨域） 反欺骗设置，请导航到防钓鱼\>下威胁管理反欺骗设置\>安全中的策略选项卡&amp;合规性中心。如果从未创建任何防钓鱼设置，您需要创建一个权限级别：</span><span class="sxs-lookup"><span data-stu-id="6819e-p127">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center. If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![反钓鱼-创建新的策略](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="6819e-262">如果您已经创建了一个，则可以选择它对其进行修改：</span><span class="sxs-lookup"><span data-stu-id="6819e-262">If you've already created one, you can select it to modify it:</span></span>
  
![反钓鱼-修改现有策略](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="6819e-264">选择您刚刚创建的策略，然后继续完成的步骤上, 所述[了解更多有关欺骗智能。](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="6819e-264">Select the policy you just created and proceed through the steps as described on [Learn More about Spoof Intelligence.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span>
  
![启用或禁用 antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![启用或禁用 antispoofing 安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="6819e-267">若要创建新策略通过 PowerShell 自定义：</span><span class="sxs-lookup"><span data-stu-id="6819e-267">To create a new policy via PowerShell:</span></span> 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

<span data-ttu-id="6819e-p128">然后，您可以修改，使用 PowerShell 关注的文档[集 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)防钓鱼策略参数。您可以指定 $name 作为参数：</span><span class="sxs-lookup"><span data-stu-id="6819e-p128">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). You may specify the $name as a parameter:</span></span>
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="6819e-270">更高版本中 2018，而不是您无需创建默认策略，将创建一个，因此您无需手动指定给您的组织中的所有收件人作用域 （下面的屏幕截图是最终的实现之前恕）。</span><span class="sxs-lookup"><span data-stu-id="6819e-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![反钓鱼的默认策略](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="6819e-272">与您创建的策略，不同，不能删除默认策略、 修改其优先级，或选择分配给哪些用户、 域或组。</span><span class="sxs-lookup"><span data-stu-id="6819e-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![反钓鱼默认策略的详细信息](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="6819e-274">设置您通过 PowerShell 自定义的默认保护：</span><span class="sxs-lookup"><span data-stu-id="6819e-274">To set up your default protection via PowerShell:</span></span>
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="6819e-275">您只应禁用反欺骗保护，如果您有另一个邮件服务器或 Office 365 之前的服务器 （请参阅合法方案禁用反欺骗的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="6819e-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span> 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="6819e-p129">如果您的电子邮件路径中的第一个跃点是 Office 365，并收到太多合法的电子邮件标记为欺骗，您应首先设置您允许欺骗电子邮件发送到您的域的发件人 （请参见 *"Managing 合法发件人发送 u 部分nauthenticated 电子邮件"* )。如果您仍收到太多误报 （例如，合法邮件标记为欺骗），建议您不要完全禁用反欺骗保护。相反，我们建议而不高保护中选择基本。                   最好能够通过误报比以公开其最终会强制显著提高成本施加长期欺骗电子邮件组织。</span><span class="sxs-lookup"><span data-stu-id="6819e-p129">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ). If you are still getting too many false positives (e.g., legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether. Instead, we recommend choosing Basic instead of High protection.                    It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="6819e-280">管理合法发件人发送未经身份验证的电子邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="6819e-p130">跟踪人员将未经身份验证的电子邮件发送到您的组织的 office 365。如果服务认为发件人不是合法，它会将其标记为*compauth*失败。这将归类为欺骗，尽管这取决于您已应用于邮件的反欺骗策略。</span><span class="sxs-lookup"><span data-stu-id="6819e-p130">Office 365 keeps track of who is sending unauthenticated email to your organization. If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure. This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span> 
  
<span data-ttu-id="6819e-284">但是，作为管理员，您可以指定的发件人都可以发送带欺骗性的电子邮件，重写 Office 365 的决策。</span><span class="sxs-lookup"><span data-stu-id="6819e-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="6819e-285">**方法 1-如果您的组织拥有的域，设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="6819e-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="6819e-p131">此方法可用于解决组织内欺骗，和跨域欺骗在您拥有或交互的情况下使用多个租户。它还有助于解决跨域欺骗，发送到 Office 365 中的其他客户以及第三方中其他提供程序承载的。</span><span class="sxs-lookup"><span data-stu-id="6819e-p131">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants. It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="6819e-288">有关详细信息，请参阅[Office 365 客户](#customers-of-office-365)。</span><span class="sxs-lookup"><span data-stu-id="6819e-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span> 
 
<span data-ttu-id="6819e-289">**方法 2-使用欺骗智能配置允许的发件人的未经身份验证的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="6819e-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="6819e-290">您还可以使用[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允许发件人传输到您的组织的未经身份验证的消息。</span><span class="sxs-lookup"><span data-stu-id="6819e-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="6819e-291">对于外部域，带欺骗性的用户是域中发件人地址，发送基础结构时发送 IP 地址 (分为/24 CIDR 范围)，或组织域的 PTR 记录 （在下面的屏幕截图，发送 IP 可能是的 131.107.18.4 其 PTR 记录是 outbound.mail.protection.outlook.com，并且这将显示为 outlook.com 发送基础结构）。</span><span class="sxs-lookup"><span data-stu-id="6819e-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="6819e-292">要允许此发件人发送未经身份验证的电子邮件，请将更改为**是**的**否**。</span><span class="sxs-lookup"><span data-stu-id="6819e-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![设置允许的发件人的 antispoofing](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="6819e-294">您还可以使用 PowerShell 允许特定发件人欺骗您的域：</span><span class="sxs-lookup"><span data-stu-id="6819e-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span> 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![获取欺骗发件人通过 Powershell 自定义](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="6819e-296">在上图中，以使此屏幕截图适应，但实际上所有值会都显示在一行上，具有已添加其他换行符。</span><span class="sxs-lookup"><span data-stu-id="6819e-296">In the previous image, additional line breaks have been added to make this screenshot fit, but in actuality all the values would appear on a single line.</span></span>
  
<span data-ttu-id="6819e-297">编辑文件寻找 outlook.com 和 bing.com，对应的行和 AllowedToSpoof 项更改为是无从：</span><span class="sxs-lookup"><span data-stu-id="6819e-297">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof Entry from No to Yes:</span></span>
  
![设置欺骗允许通过 Powershell 自定义是](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="6819e-299">保存文件，然后运行：</span><span class="sxs-lookup"><span data-stu-id="6819e-299">Save the file, and then run:</span></span> 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="6819e-300">现在，这将使 bing.com 发送未经身份验证电子邮件从\*。 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6819e-300">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="6819e-301">**方法 3-创建发件人/收件人对允许条目**</span><span class="sxs-lookup"><span data-stu-id="6819e-301">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="6819e-p132">您还可以选择绕过所有垃圾邮件筛选特定发件人。有关详细信息，请参阅[如何安全地添加到 Office 365 中的允许列表的发件人](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="6819e-p132">You can also choose to bypass all spam filtering for a particular sender. For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="6819e-304">如果您使用此方法，它将跳过垃圾邮件和一些网络钓鱼诈骗筛选，但不是恶意软件筛选。</span><span class="sxs-lookup"><span data-stu-id="6819e-304">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="6819e-305">**方法 4-联系人发件人，请他们设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="6819e-305">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="6819e-p133">垃圾邮件和网络钓鱼的问题，因为 Microsoft 建议设置电子邮件身份验证的所有发件人。如果您知道的发送域管理员，请联系它们和他们设置电子邮件身份验证记录因此不需要添加任何重写的请求。有关详细信息，请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)"后面的这篇文章。</span><span class="sxs-lookup"><span data-stu-id="6819e-p133">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication. If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides. For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="6819e-309">可能会变得比较困难，首先获取发送域进行身份验证，随时间推移，越来越多电子邮件筛选器启动 junking 或甚至拒绝其电子邮件，它将导致他们设置相应的记录以确保提供更好。</span><span class="sxs-lookup"><span data-stu-id="6819e-309">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="6819e-310">查看多少邮件已标记为造假报告</span><span class="sxs-lookup"><span data-stu-id="6819e-310">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="6819e-p134">启用您反欺骗策略后，您可以使用威胁智能若要解决多少邮件标记为网络钓鱼诈骗的号码。若要执行此操作，请转到安全&amp;下威胁管理合规性中心 (SCC)\>资源管理器中，通过发件人域或保护状态将视图设置为网络钓鱼诈骗、 和组：</span><span class="sxs-lookup"><span data-stu-id="6819e-p134">Once your anti-spoofing policy is enabled, you can use Threat Intelligence to get numbers around how many messages are marked as phish. To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![查看多少邮件标记为网络钓鱼诈骗](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="6819e-p135">您可以与各种报告以查看多少已标记为网络钓鱼，包括消息标记为欺骗进行交互。若要了解详细信息，请参阅[开始使用 Office 365 威胁智能](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)。</span><span class="sxs-lookup"><span data-stu-id="6819e-p135">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF. To learn more, see [Get started with Office 365 Threat Intelligence](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).</span></span>
  
<span data-ttu-id="6819e-p136">尚未无法拆分出的邮件已标记由于欺骗与其他类型的网络钓鱼 （常规网络钓鱼、 域或用户模拟等）。但是，后面 2018，您将能够执行此操作通过安全&amp;合规性中心。做后，可以作为起点使用此报告来标识可能是合法的被标记为欺骗由于出现故障的身份验证的发送域。</span><span class="sxs-lookup"><span data-stu-id="6819e-p136">You cannot yet split out which messages were marked due to spoofing vs. other types of phishing (general phishing, domain or user impersonation, and so on). However, later in 2018, you will be able to do this through the Security &amp; Compliance Center. Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="6819e-319">下面的屏幕快照是如何此数据的外观，但可能会改变发布时的建议：</span><span class="sxs-lookup"><span data-stu-id="6819e-319">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![查看网络钓鱼报告按检测类型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="6819e-p137">对于非 ATP 和 E5 客户，这些报告更高版本中 2018 下威胁保护状态 (TP) 报告中，将提供，但将推迟至少 24 小时。该页面将更新，如集成安全性&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="6819e-p137">For non-ATP and E5 customers, these reports will be available later in 2018 under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours. This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="6819e-323">预测多少邮件将被标记为欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-323">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="6819e-p138">后面 2018 Office 365 一次更新其设置让您关闭反欺骗实施，或在与基本或高实施，将为您提供能够看到消息处置将如何在各种设置更改。也就是说，如果反欺骗处于关闭状态，您将能够看到多少邮件将被检测为欺骗，如果您启用到 Basic;或者，如果是 Basic，您将能够看到多少更多邮件将被检测为欺骗，如果将它转换为高。</span><span class="sxs-lookup"><span data-stu-id="6819e-p138">Later in 2018, once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings. That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="6819e-p139">此功能目前正在开发。定义更多详细信息，则该页面将更新同时与的安全性和合规性中心的屏幕截图和 PowerShell 示例。</span><span class="sxs-lookup"><span data-stu-id="6819e-p139">This feature is currently under development. As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
!["如果"启用 antispoofing 报告](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![可能允许欺骗发件人的 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="6819e-330">了解如何垃圾邮件、 网络钓鱼和检测兼而有之高级网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="6819e-330">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="6819e-p140">如果组织使用或不 ATP，使用 Exchange Online 中，可以指定的服务标识为恶意软件、 垃圾邮件、 高可信度垃圾邮件、 网络钓鱼和批量邮件时要采取哪些操作。使用 ATP 客户的 ATP 防钓鱼策略和 EOP 客户的防钓鱼策略和一条消息可能命中多个检测类型 （例如，恶意软件、 网络钓鱼和用户模拟） 这一事实，可能有一些混乱策略适用。</span><span class="sxs-lookup"><span data-stu-id="6819e-p140">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk. With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span> 
  
<span data-ttu-id="6819e-333">一般情况下，CAT （类别） 属性中的 X Forefront 反垃圾邮件报表页眉中标识应用于邮件的策略。</span><span class="sxs-lookup"><span data-stu-id="6819e-333">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span> 
  
|<span data-ttu-id="6819e-334">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6819e-334">**Priority**</span></span>|<span data-ttu-id="6819e-335">**策略**</span><span class="sxs-lookup"><span data-stu-id="6819e-335">**Policy**</span></span>|<span data-ttu-id="6819e-336">**类别**</span><span class="sxs-lookup"><span data-stu-id="6819e-336">**Category**</span></span>|<span data-ttu-id="6819e-337">**其中托管？**</span><span class="sxs-lookup"><span data-stu-id="6819e-337">**Where managed?**</span></span>|<span data-ttu-id="6819e-338">**应用于**</span><span class="sxs-lookup"><span data-stu-id="6819e-338">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6819e-339">1</span><span class="sxs-lookup"><span data-stu-id="6819e-339">1</span></span>  <br/> |<span data-ttu-id="6819e-340">恶意软件</span><span class="sxs-lookup"><span data-stu-id="6819e-340">Malware</span></span>  <br/> |<span data-ttu-id="6819e-341">MALW</span><span class="sxs-lookup"><span data-stu-id="6819e-341">MALW</span></span>  <br/> |[<span data-ttu-id="6819e-342">恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="6819e-342">Malware policy</span></span>](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="6819e-343">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-343">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-344">2</span><span class="sxs-lookup"><span data-stu-id="6819e-344">2</span></span>  <br/> |<span data-ttu-id="6819e-345">网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="6819e-345">Phishing</span></span>  <br/> |<span data-ttu-id="6819e-346">PHSH</span><span class="sxs-lookup"><span data-stu-id="6819e-346">PHSH</span></span>  <br/> |[<span data-ttu-id="6819e-347">承载的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6819e-347">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="6819e-348">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-348">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-349">3</span><span class="sxs-lookup"><span data-stu-id="6819e-349">3</span></span>  <br/> |<span data-ttu-id="6819e-350">可信度高的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-350">High confidence spam</span></span>  <br/> |<span data-ttu-id="6819e-351">HSPM</span><span class="sxs-lookup"><span data-stu-id="6819e-351">HSPM</span></span>  <br/> |[<span data-ttu-id="6819e-352">承载的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6819e-352">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="6819e-353">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-353">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-354">4</span><span class="sxs-lookup"><span data-stu-id="6819e-354">4</span></span>  <br/> |<span data-ttu-id="6819e-355">欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-355">Spoofing</span></span>  <br/> |<span data-ttu-id="6819e-356">欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-356">SPOOF</span></span>  <br/> |<span data-ttu-id="6819e-357">[防钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553)，[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="6819e-357">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553),          [Spoof intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span> <br/> |<span data-ttu-id="6819e-358">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-358">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-359">5</span><span class="sxs-lookup"><span data-stu-id="6819e-359">5</span></span>  <br/> |<span data-ttu-id="6819e-360">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-360">Spam</span></span>  <br/> |<span data-ttu-id="6819e-361">SPM</span><span class="sxs-lookup"><span data-stu-id="6819e-361">SPM</span></span>  <br/> |[<span data-ttu-id="6819e-362">承载的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6819e-362">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="6819e-363">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-363">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-364">6</span><span class="sxs-lookup"><span data-stu-id="6819e-364">6</span></span>  <br/> |<span data-ttu-id="6819e-365">批量</span><span class="sxs-lookup"><span data-stu-id="6819e-365">Bulk</span></span>  <br/> |<span data-ttu-id="6819e-366">批量</span><span class="sxs-lookup"><span data-stu-id="6819e-366">BULK</span></span>  <br/> |[<span data-ttu-id="6819e-367">承载的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="6819e-367">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="6819e-368">所有组织</span><span class="sxs-lookup"><span data-stu-id="6819e-368">All organizations</span></span>  <br/> |
|<span data-ttu-id="6819e-369">7</span><span class="sxs-lookup"><span data-stu-id="6819e-369">7</span></span>  <br/> |<span data-ttu-id="6819e-370">域模拟</span><span class="sxs-lookup"><span data-stu-id="6819e-370">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="6819e-371">DIMP</span><span class="sxs-lookup"><span data-stu-id="6819e-371">DIMP</span></span>  <br/> |[<span data-ttu-id="6819e-372">防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="6819e-372">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="6819e-373">仅组织 ATP</span><span class="sxs-lookup"><span data-stu-id="6819e-373">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="6819e-374">8</span><span class="sxs-lookup"><span data-stu-id="6819e-374">8</span></span>  <br/> |<span data-ttu-id="6819e-375">用户模拟</span><span class="sxs-lookup"><span data-stu-id="6819e-375">User Impersonation</span></span>  <br/> |<span data-ttu-id="6819e-376">UIMP</span><span class="sxs-lookup"><span data-stu-id="6819e-376">UIMP</span></span>  <br/> |[<span data-ttu-id="6819e-377">防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="6819e-377">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="6819e-378">仅组织 ATP</span><span class="sxs-lookup"><span data-stu-id="6819e-378">Organizations with ATP only</span></span> <br/> |
   
<span data-ttu-id="6819e-p141">如果您有多个不同的防钓鱼策略，将应用的最高优先级的一个。例如，假设您有两个策略：</span><span class="sxs-lookup"><span data-stu-id="6819e-p141">If you have multiple different Anti-phishing policies, the one at the highest priority will apply. For example, suppose you have two policies:</span></span>
  
|<span data-ttu-id="6819e-381">**策略**</span><span class="sxs-lookup"><span data-stu-id="6819e-381">**Policy**</span></span>|<span data-ttu-id="6819e-382">**优先级**</span><span class="sxs-lookup"><span data-stu-id="6819e-382">**Priority**</span></span>|<span data-ttu-id="6819e-383">**用户/域模拟**</span><span class="sxs-lookup"><span data-stu-id="6819e-383">**User/Domain Impersonation**</span></span>|<span data-ttu-id="6819e-384">**反欺骗**</span><span class="sxs-lookup"><span data-stu-id="6819e-384">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6819e-385">A</span><span class="sxs-lookup"><span data-stu-id="6819e-385">A</span></span>  <br/> |<span data-ttu-id="6819e-386">1</span><span class="sxs-lookup"><span data-stu-id="6819e-386">1</span></span>  <br/> |<span data-ttu-id="6819e-387">On</span><span class="sxs-lookup"><span data-stu-id="6819e-387">On</span></span>  <br/> |<span data-ttu-id="6819e-388">Off</span><span class="sxs-lookup"><span data-stu-id="6819e-388">Off</span></span>  <br/> |
|<span data-ttu-id="6819e-389">B</span><span class="sxs-lookup"><span data-stu-id="6819e-389">B</span></span>  <br/> |<span data-ttu-id="6819e-390">2</span><span class="sxs-lookup"><span data-stu-id="6819e-390">2</span></span>  <br/> |<span data-ttu-id="6819e-391">关</span><span class="sxs-lookup"><span data-stu-id="6819e-391">Off</span></span>  <br/> |<span data-ttu-id="6819e-392">位置</span><span class="sxs-lookup"><span data-stu-id="6819e-392">On</span></span>  <br/> |
   
<span data-ttu-id="6819e-393">如果一条消息起作用，并被标识为欺骗和用户模拟和一组相同的用户范围的策略和策略 B，则邮件将被视为欺骗但没有操作应用相防欺骗处于关闭状态并在用户模拟 (8) 比更高的优先级 (4) 欺骗运行。</span><span class="sxs-lookup"><span data-stu-id="6819e-393">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="6819e-394">若要进行其他类型的网络钓鱼策略应用，您将需要调整谁的各种策略应用于的设置。</span><span class="sxs-lookup"><span data-stu-id="6819e-394">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="6819e-395">若要禁用反欺骗的合法方案</span><span class="sxs-lookup"><span data-stu-id="6819e-395">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="6819e-p142">更好地反欺骗保证客户的网络钓鱼攻击，因此强烈建议您不要禁用反欺骗保护。通过禁用它，您可能会解决一些短期误报，但您将会面临详细风险的长期。设置在发件人一侧，身份验证或网络钓鱼策略中进行调整的成本通常一次性事件，或需要最少、 定期维护。但是，其中已公开数据，网络钓鱼攻击恢复成本或资产已泄露是高得多。</span><span class="sxs-lookup"><span data-stu-id="6819e-p142">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged. By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk. The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance. However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="6819e-400">因此，最好能够通过比要禁用防欺骗保护反欺骗误报。</span><span class="sxs-lookup"><span data-stu-id="6819e-400">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="6819e-401">但是，没有合法的方案，其中应禁用反欺骗，并有其他邮件筛选时的邮件路由，和 Office 365 中的产品不是电子邮件路径中的第一个跃点：</span><span class="sxs-lookup"><span data-stu-id="6819e-401">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客户 MX 记录未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="6819e-403">其他服务器可能 Exchange 内部部署邮件服务器，筛选设备 Ironport，如邮件或其他云托管服务。</span><span class="sxs-lookup"><span data-stu-id="6819e-403">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="6819e-p143">如果收件人的域的 MX 记录未指向 Office 365，则不需要禁用反欺骗因为 Office 365 查找接收域的 MX 记录，并禁止反欺骗指向另一项服务。如果您不知道您的域如果前端具有另一台服务器，您可以使用类似 MX 工具箱的网站以查找 MX 记录。它可能会显示类似以下内容：</span><span class="sxs-lookup"><span data-stu-id="6819e-p143">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service. If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record. It might say something like the following:</span></span>
  
![MX 记录表示域不指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="6819e-408">此域有 MX 记录未指向 Office 365 中，以便 Office 365 不适用反欺骗实施的。</span><span class="sxs-lookup"><span data-stu-id="6819e-408">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="6819e-p144">但是，如果*执行*的收件人域的 MX 记录指向 Office 365 中，即使没有之前 Office 365 另一项服务，然后您应禁用反欺骗。最常见的示例是通过使用收件人重写：</span><span class="sxs-lookup"><span data-stu-id="6819e-p144">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing. The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件人重写的路由关系图](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="6819e-412">域 contoso.com 的 MX 记录指向内部部署服务器，同时域 @office365.contoso.net MX 记录指向在 Office 365，因为它包含\*。 protection.outlook.com，或\*。 eo.outlook.com 的 MX 记录中：</span><span class="sxs-lookup"><span data-stu-id="6819e-412">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 记录指向 Office 365，因此可能收件人重写](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="6819e-p145">请务必区分以及它已经过收件人重写时的收件人域的 MX 记录未指向 Office 365。务必告知这两种情况之间的差异。</span><span class="sxs-lookup"><span data-stu-id="6819e-p145">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite. It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="6819e-416">如果您不确定接收域已经过收件人重写，有时您可以通过查看判断在邮件头。</span><span class="sxs-lookup"><span data-stu-id="6819e-416">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="6819e-417">） 首先，查看中的身份验证结果标头中的收件人域的邮件的标头：</span><span class="sxs-lookup"><span data-stu-id="6819e-417">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span> 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="6819e-p146">上方，在此案例 office365.contoso.net 的加粗红色文本中找到的收件人的域。这可能不同，在收件人收件人： 标头：</span><span class="sxs-lookup"><span data-stu-id="6819e-p146">The recipient domain is found in the bold red text above, in this case office365.contoso.net. This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="6819e-420">收件人： 示例收件人\<@ contoso.com 收件人\></span><span class="sxs-lookup"><span data-stu-id="6819e-420">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="6819e-p147">执行实际的收件人域的 MX 记录查找。如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com， \*。 eo.outlook.com 或 mail.global.frontbridge.com，这意味着 MX 指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6819e-p147">Perform an MX-record lookup of the actual recipient domain. If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="6819e-p148">如果它不包含这些值，则意味着 MX 不指向 Office 365。一个工具可用于验证这是 MX 工具箱。</span><span class="sxs-lookup"><span data-stu-id="6819e-p148">If it does not contain those values, then it means that the MX does not point to Office 365. One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="6819e-425">对于此特定的示例，以下显示该 contoso.com，如下所示收件人，因为它，收件人的域： 标头，具有 MX 记录指向上 prem 服务器：</span><span class="sxs-lookup"><span data-stu-id="6819e-425">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 记录指向上 prem 服务器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="6819e-427">但是，实际收件人是的 office365.contoso.net 其 MX 记录执行指向 Office 365:</span><span class="sxs-lookup"><span data-stu-id="6819e-427">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 指向 Office 365 必须收件人重写](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="6819e-429">因此，此消息可能经历收件人重写。</span><span class="sxs-lookup"><span data-stu-id="6819e-429">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="6819e-p149">b） 第二，请务必区分收件人重写的常见的使用案例。如果您要重写的收件人域\*。 onmicrosoft.com，而是将其重写\*。 mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="6819e-p149">b) Second, be sure to distinguish between common use cases of recipient rewrites. If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="6819e-432">一旦您已经确定路由后面另一台服务器的最终的收件人域并收件人域的 MX 记录实际指向 Office 365 （如发布其 DNS 记录中），您可以继续禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="6819e-432">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="6819e-433">请记住，您不想要禁用反欺骗如果域的路由路径中的第一个跃点是 Office 365 中，仅时隐藏一个或多个服务。</span><span class="sxs-lookup"><span data-stu-id="6819e-433">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="6819e-434">如何禁用反欺骗</span><span class="sxs-lookup"><span data-stu-id="6819e-434">How to disable anti-spoofing</span></span>

<span data-ttu-id="6819e-435">如果您已创建的防钓鱼策略，设置为 $false EnableAntispoofEnforcement 参数：</span><span class="sxs-lookup"><span data-stu-id="6819e-435">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span> 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

<span data-ttu-id="6819e-436">如果您不知道策略 （或策略） 若要禁用的名称，则可以显示它们：</span><span class="sxs-lookup"><span data-stu-id="6819e-436">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span> 
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="6819e-p150">如果您没有任何现有的防钓鱼策略，可以创建一个，然后禁用它 （即使您没有策略、 反欺骗，则仍应用; 在 2018年中更高版本、 将为您创建的默认策略和您然后可以而不是创建一个禁用的）.您将需要执行此操作在多个步骤：</span><span class="sxs-lookup"><span data-stu-id="6819e-p150">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one). You will have to do this in multiple steps:</span></span> 
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

<span data-ttu-id="6819e-p151">禁用反欺骗才可用 cmdlet 通过 (后面 Q2 2018 它将提供安全中&amp;合规性中心)。如果您没有访问 PowerShell，创建支持票证，从而。</span><span class="sxs-lookup"><span data-stu-id="6819e-p151">Disabling anti-spoofing is only available via cmdlet (later in Q2 2018 it will be available in the Security &amp; Compliance Center). If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="6819e-p152">请记住，这只应应用到经过间接路由时发送到 Office 365 的域。抵御诱惑因某些误报禁用反欺骗，它将从长远来看最好通过这些工作。</span><span class="sxs-lookup"><span data-stu-id="6819e-p152">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365. Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="6819e-443">各个用户的的信息</span><span class="sxs-lookup"><span data-stu-id="6819e-443">Information for individual users</span></span>

<span data-ttu-id="6819e-p153">单个用户将仅限于它们与反欺骗安全提示的交互方式。但是，有几个您可以执行的操作来解决常见方案。</span><span class="sxs-lookup"><span data-stu-id="6819e-p153">Individual users are limited in how they can interact with the anti-spoofing safety tip. However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="6819e-446">常见方案 #1-邮箱转接</span><span class="sxs-lookup"><span data-stu-id="6819e-446">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="6819e-p154">如果您使用其他电子邮件服务，并将您的电子邮件转发给 Office 365 或 Outlook.com，您的电子邮件可能被标记为欺骗和收到红色安全提示。Office 365 和 Outlook.com 计划自动解决此问题转发器时 Outlook.com、 Office 365、 Gmail 或使用[弧协议](https://arc-spec.org)的任何其他服务之一。但是，部署该修补程序，直到用户应使用已连接帐户功能导入其邮件直接，而不是使用转接选项。</span><span class="sxs-lookup"><span data-stu-id="6819e-p154">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip. Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org). However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="6819e-450">若要设置 Office 365 中的已连接帐户，在 Office 365 web 接口的右上角中选择齿轮图标\>邮件\>邮件\>帐户\>连接帐户。</span><span class="sxs-lookup"><span data-stu-id="6819e-450">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
![连接的 office 365-帐户选项](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="6819e-452">在 Outlook.com，该过程将齿轮图标\>选项\>邮件\>帐户\>连接帐户。</span><span class="sxs-lookup"><span data-stu-id="6819e-452">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="6819e-453">常见方案 #2-讨论列出</span><span class="sxs-lookup"><span data-stu-id="6819e-453">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="6819e-454">讨论列表已知遇到问题，请使用反欺骗由于方式它们转发邮件和修改其内容，但保留从原始： 地址。</span><span class="sxs-lookup"><span data-stu-id="6819e-454">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="6819e-p155">例如，假设您的电子邮件地址是用户 @ contoso.com，以及您感兴趣鸟监视并加入讨论列表 birdwatchers @ example.com。当一条消息发送到讨论列表中时，您可能发送这种方式：</span><span class="sxs-lookup"><span data-stu-id="6819e-p155">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com. When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="6819e-457">**从：** John Doe \<@ contoso.com 的用户\></span><span class="sxs-lookup"><span data-stu-id="6819e-457">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="6819e-458">**到：** Birdwatcher 的讨论列表\<@ example.com birdwatchers\></span><span class="sxs-lookup"><span data-stu-id="6819e-458">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="6819e-p156">**使用者：** 本周的蓝色 jays 顶部保持联系突出的绝佳查看</span><span class="sxs-lookup"><span data-stu-id="6819e-p156">**Subject:** Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="6819e-p157">任何人都要签出查看从保持联系突出本周？</span><span class="sxs-lookup"><span data-stu-id="6819e-p157">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
<span data-ttu-id="6819e-463">当电子邮件列表收到邮件时，他们格式化的消息、 修改其内容，并重播上从许多不同的电子邮件接收器的参与者构成讨论列表的成员的其余部分。</span><span class="sxs-lookup"><span data-stu-id="6819e-463">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="6819e-464">**从：** John Doe \<@ contoso.com 的用户\></span><span class="sxs-lookup"><span data-stu-id="6819e-464">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="6819e-465">**到：** Birdwatcher 的讨论列表\<@ example.com birdwatchers\></span><span class="sxs-lookup"><span data-stu-id="6819e-465">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="6819e-p158">**使用者：**[BIRDWATCHERS]本周的蓝色 jays 顶部保持联系突出的绝佳查看</span><span class="sxs-lookup"><span data-stu-id="6819e-p158">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="6819e-p159">任何人都要签出查看从保持联系突出本周？</span><span class="sxs-lookup"><span data-stu-id="6819e-p159">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
---
  
<span data-ttu-id="6819e-p160">此消息发送到 Birdwatchers 讨论列表。您可以随时取消订阅。</span><span class="sxs-lookup"><span data-stu-id="6819e-p160">This message was sent to the Birdwatchers Discussion List. You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="6819e-p161">在上文中，重播的消息具有相同的： 地址 （用户 @ contoso.com），但原始邮件已被修改通过将标签添加到主题行和到底部的邮件页脚。此类型的邮件修改共同点邮件列表，并可能会导致误报。</span><span class="sxs-lookup"><span data-stu-id="6819e-p161">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message. This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="6819e-474">如果您或您的组织中的某人的邮件列表管理员，您可能能够将其配置为通过反欺骗检查。</span><span class="sxs-lookup"><span data-stu-id="6819e-474">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="6819e-475">检查在 DMARC.org 常见问题：[我操作邮件列表和我希望与 DMARC 互操作，应该怎样做？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="6819e-475">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>
    
- <span data-ttu-id="6819e-476">阅读此博客文章处的说明：[邮件列表运算符来实现互操作 DMARC 以避免出现故障的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="6819e-476">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>
    
- <span data-ttu-id="6819e-477">请考虑要支持弧，请参阅您邮件列表服务器上安装更新[https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="6819e-477">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>
    
<span data-ttu-id="6819e-478">如果您没有所有权的邮件列表：</span><span class="sxs-lookup"><span data-stu-id="6819e-478">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="6819e-479">您可以请求邮件列表的 maintainer，以实现上面 （他们应已设置为邮件列表来自的域的电子邮件身份验证） 的选项之一</span><span class="sxs-lookup"><span data-stu-id="6819e-479">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>
    
- <span data-ttu-id="6819e-p162">您可以在您的电子邮件客户端将邮件移动到收件箱中创建邮箱规则。您还可以请求组织的管理员设置允许规则，或覆盖为节所述管理合法的发件人发送未经身份验证的电子邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-p162">You can create mailbox rules in your email client to move messages to the Inbox. You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>
    
- <span data-ttu-id="6819e-482">您可以使用 Office 365 创建邮件列表会将其视为合法覆盖创建支持票证从而</span><span class="sxs-lookup"><span data-stu-id="6819e-482">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>
    
### <a name="other-scenarios"></a><span data-ttu-id="6819e-483">其他方案</span><span class="sxs-lookup"><span data-stu-id="6819e-483">Other scenarios</span></span>

1. <span data-ttu-id="6819e-p163">如果这两个以上的常见方案适用于您的情况，为 false 的正整数后向 Microsoft 报告邮件。有关详细信息，请参阅部分[如何报告垃圾邮件或非垃圾邮件后向 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)本文后面。</span><span class="sxs-lookup"><span data-stu-id="6819e-p163">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft. For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 
    
2. <span data-ttu-id="6819e-p164">您还可以联系可引发它与 Microsoft 支持票证，从而为您的电子邮件管理员。Microsoft 工程团队将调查为什么邮件被标记为欺骗。</span><span class="sxs-lookup"><span data-stu-id="6819e-p164">You may also contact your email administrator who can raise it as a support ticket with Microsoft. The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>
    
3. <span data-ttu-id="6819e-p165">此外，如果您知道发件人是且确信它们不被恶意造假，您可能回发件人，指示它们从邮件服务器的身份验证不发送邮件答复。这有时会导致原始发件人将设置所需的电子邮件身份验证记录其 IT 管理员联系。</span><span class="sxs-lookup"><span data-stu-id="6819e-p165">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate. This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="6819e-p166">当足够发件人答复回域所有者它们应设置电子邮件身份验证记录时，它 spurs 它们采取操作。当 Microsoft 还适用于域所有者发布所需的记录时，它帮助更多时各个用户请求。</span><span class="sxs-lookup"><span data-stu-id="6819e-p166">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action. While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>
    
4. <span data-ttu-id="6819e-p167">（可选） 将发件人添加到安全发件人列表。但请注意，如果钓鱼欺骗该帐户，它将传递到您的邮箱。因此，应谨慎使用此选项。</span><span class="sxs-lookup"><span data-stu-id="6819e-p167">Optionally, add the sender to your Safe Senders list. However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox. Therefore, this option should be used sparingly.</span></span>
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="6819e-495">向 Microsoft 的发件人应如何准备反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="6819e-495">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="6819e-496">如果您是当前将邮件发送给 Microsoft，管理员 Office 365 或 Outlook.com 中，您应该确保您的电子邮件进行正确身份验证否则被标记为垃圾邮件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="6819e-496">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span> 
  
### <a name="customers-of-office-365"></a><span data-ttu-id="6819e-497">Office 365 的客户</span><span class="sxs-lookup"><span data-stu-id="6819e-497">Customers of Office 365</span></span>

<span data-ttu-id="6819e-498">如果您是 Office 365 客户，并且您使用 Office 365 发送出站电子邮件：</span><span class="sxs-lookup"><span data-stu-id="6819e-498">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="6819e-499">为您的域，[设置 Office 365 为了帮助防止欺骗中的 SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span><span class="sxs-lookup"><span data-stu-id="6819e-499">For your domains, [Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span></span>
    
- <span data-ttu-id="6819e-500">有关主域，[使用 DKIM 验证从您在 Office 365 中的自定义域发送出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span><span class="sxs-lookup"><span data-stu-id="6819e-500">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span></span>
    
- <span data-ttu-id="6819e-501">[考虑 DMARC 记录设置](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)为您的域以确定您的合法发件人是谁</span><span class="sxs-lookup"><span data-stu-id="6819e-501">[Consider setting up DMARC records](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) for your domain to determine who are your legitimate senders</span></span> 
    
<span data-ttu-id="6819e-p168">Microsoft 不提供对每个 SPF、 DKIM，以及 DMARC 详细的实现准则。但是，没有大量联机发布的信息。还有第三方公司专用于帮助组织设置电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="6819e-p168">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC. However, there is a lot of information published online. There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="6819e-505">不是 Office 365 客户的域的管理员</span><span class="sxs-lookup"><span data-stu-id="6819e-505">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="6819e-506">如果您是域管理员，但不是 Office 365 客户：</span><span class="sxs-lookup"><span data-stu-id="6819e-506">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="6819e-p169">您应当设置 SPF 以发布您的域的发送 IP 地址，并还设置 DKIM （如果可用） 消息进行数字签名。您可能会考虑设置 DMARC 记录。</span><span class="sxs-lookup"><span data-stu-id="6819e-p169">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages. You may also consider setting up DMARC records.</span></span>
    
- <span data-ttu-id="6819e-509">如果您有批量的发件人正在传送代表您的电子邮件，则应使用它们的方式发送电子邮件以便在从的发送域： 地址 （如果您属于） 与将传递 SPF 或 DMARC 域对齐。</span><span class="sxs-lookup"><span data-stu-id="6819e-509">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>
    
- <span data-ttu-id="6819e-510">如果您具有内部部署邮件服务器，或从软件作为服务提供程序，或从云承载的服务，如 Microsoft Azure、 GoDaddy、 机架、 Amazon Web 服务发送或类似，您应该确保已添加到您的 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="6819e-510">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>
    
- <span data-ttu-id="6819e-p170">如果您是位于由 ISP 较小的域，您应设置根据说明您的 ISP 提供给您的 SPF 记录。大多数 Isp 提供这些类型的说明，并可在公司的支持页面上找到。</span><span class="sxs-lookup"><span data-stu-id="6819e-p170">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP. Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>
    
- <span data-ttu-id="6819e-p171">即使您已经不发布电子邮件之前，身份验证记录，并且它正常运行，您仍必须发布电子邮件身份验证记录，将发送给 Microsoft。这样，您在网络钓鱼抵御帮助并减少您向的组织获取 phished 的可能性。</span><span class="sxs-lookup"><span data-stu-id="6819e-p171">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft. By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="6819e-515">如果您不知道谁将作为您的域发送电子邮件？</span><span class="sxs-lookup"><span data-stu-id="6819e-515">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="6819e-p172">许多域不发布 SPF 记录，因为它们不知道其所有发件人是谁。没关系，不需要知道谁能全部。相反，您应开始通过发布为您知道，尤其是您企业的通信设备的位置，并发布的非特定的 SPF 策略的 SPF 记录？ 所有：</span><span class="sxs-lookup"><span data-stu-id="6819e-p172">Many domains do not publish SPF records because they do not know who all their senders are. That's okay, you do not need to know who all of them are. Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="6819e-519">example.com IN TXT"v = spf1 include:spf.example.com？ 所有"</span><span class="sxs-lookup"><span data-stu-id="6819e-519">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="6819e-p173">非特定的 SPF 策略意味着，利用您公司的基础结构中的任何电子邮件将通过电子邮件身份验证在所有其他电子邮件接收器。来自您不知道有关的发件人的电子邮件将回退到 neutral，几乎相同发布根本没有 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="6819e-p173">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers. Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="6819e-p174">在发送到 Office 365 时，来自您的企业通信的电子邮件将被标记为经过身份验证，但来自您不了解的内容源的电子邮件可能仍被标记为欺骗 （具体取决于 Office 365 可以隐式验证）。但是，这仍是来自所有电子邮件被标记为欺骗 Office 365 的改进。</span><span class="sxs-lookup"><span data-stu-id="6819e-p174">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it). However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="6819e-524">一旦您已变得入门 SPF 记录与一个回退的策略？ 所有，您可以逐步包括更发送基础结构，然后发布更严格的策略。</span><span class="sxs-lookup"><span data-stu-id="6819e-524">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="6819e-525">如果您是邮件列表的所有者？</span><span class="sxs-lookup"><span data-stu-id="6819e-525">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="6819e-526">请参阅[常见方案 #2-讨论列出](#common-scenario-2---discussion-lists)的部分。</span><span class="sxs-lookup"><span data-stu-id="6819e-526">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span> 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="6819e-527">如果您将如 Internet 服务提供程序 (ISP)、 电子邮件服务提供程序 (ESP) 或云承载服务的基础结构提供程序。</span><span class="sxs-lookup"><span data-stu-id="6819e-527">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="6819e-528">如果主机域的电子邮件，并且其发送电子邮件，或提供可发送电子邮件的宿主基础结构，您应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6819e-528">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="6819e-529">确保您的客户详细介绍要在其 SPF 记录中发布的文档</span><span class="sxs-lookup"><span data-stu-id="6819e-529">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>
    
- <span data-ttu-id="6819e-p175">请考虑 DKIM 签名登录出站电子邮件中，即使客户不明确其进行设置 （与默认域登录）。您可以偶数 double 登录 （一次使用他们具有其进行设置，如果客户的域和第二次与贵公司的 DKIM 签名） DKIM 签名与电子邮件</span><span class="sxs-lookup"><span data-stu-id="6819e-p175">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain). You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>
    
<span data-ttu-id="6819e-p176">不能保证向 Microsoft 可交付性，即使验证电子邮件来自您的平台，但至少可确保 Microsoft 不会不垃圾电子邮件，因为它不进行身份验证。围绕 Outlook.com 如何筛选电子邮件的详细信息，请参阅[Outlook.com 邮局主管页](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6819e-p176">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated. For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="6819e-534">有关服务提供程序的最佳实践的详细信息，请参阅[M3AAWG 移动消息的最佳实践服务提供商](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。</span><span class="sxs-lookup"><span data-stu-id="6819e-534">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="6819e-535">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="6819e-535">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="6819e-536">Microsoft 为什么进行此更改？</span><span class="sxs-lookup"><span data-stu-id="6819e-536">Why is Microsoft making this change?</span></span>

<span data-ttu-id="6819e-537">由于影响网络钓鱼的攻击，和电子邮件身份验证已围绕 15 年以上，因为 Microsoft 认为，继续允许未经身份验证的电子邮件的风险大于丢失合法的电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="6819e-537">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="6819e-538">此更改会导致合法的电子邮件标记为垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="6819e-538">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="6819e-p177">首先，将某些标记为垃圾邮件的邮件。但是，一段时间，发件人将调整并且将然后对于大多数电子邮件路径可以忽略错误地标记为带欺骗性的消息的数量。</span><span class="sxs-lookup"><span data-stu-id="6819e-p177">At first, there will be some messages that are marked as spam. However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="6819e-p178">Microsoft 本身首先采用此功能之前将其部署到其客户的其余部分的几周。时出现在第一张、 逐步拒绝其中断。</span><span class="sxs-lookup"><span data-stu-id="6819e-p178">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers. While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="6819e-543">将 Microsoft 置于此功能的 Office 365 Outlook.com 和非高级威胁保护客户？</span><span class="sxs-lookup"><span data-stu-id="6819e-543">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="6819e-p179">Microsoft 的反欺骗技术已最初部署到其组织的 Office 365 企业 E5 订阅或已购买 Office 365 高级威胁保护 (ATP) 加载项为其订阅。从 2018 年 10 月，我们已扩展到以及具有 Exchange Online Protection (EOP) 的组织的保护。将来，我们可能为 Outlook.com 发布它。但是，如果我们这样做，可能不会应用如报告某些功能，并将覆盖自定义。</span><span class="sxs-lookup"><span data-stu-id="6819e-p179">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. In the future, we may release it for Outlook.com. However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="6819e-548">如何报告垃圾邮件或非垃圾邮件后向 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="6819e-548">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="6819e-549">您可以使用[报告消息外接程序 Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，或者如果它不安装，[提交垃圾邮件、 非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6819e-549">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="6819e-550">我不知道我所有发件人是谁域管理员 ！</span><span class="sxs-lookup"><span data-stu-id="6819e-550">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="6819e-551">请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="6819e-551">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="6819e-552">如果，？ 我禁用反欺骗保护我的组织，即使 Office 365 是我主要筛选器</span><span class="sxs-lookup"><span data-stu-id="6819e-552">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="6819e-p180">建议不要这因为您将会面临更错过网络钓鱼和垃圾邮件。不是所有网络钓鱼欺骗，而且不是所有欺骗将会都丢失。但是，您风险将高于启用反欺骗的客户。</span><span class="sxs-lookup"><span data-stu-id="6819e-p180">We do not recommend this because you will be exposed to more missed phishing and spam messages. Not all phishing is spoofing, and not all spoofs will be missed. However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="6819e-556">启用反欺骗保护意思我将从所有网络钓鱼保护？</span><span class="sxs-lookup"><span data-stu-id="6819e-556">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="6819e-p181">遗憾的是，否，因为适应网络钓鱼程序将使用其他方法，例如泄露帐户或设置的免费服务帐户。但是，防钓鱼保护的工作方式得更好地检测这些其他类型的网络钓鱼方法，因为层是 Office 365 保护一起设计工作和彼此构建。</span><span class="sxs-lookup"><span data-stu-id="6819e-p181">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services. However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="6819e-559">其他大型电子邮件接收器阻止未经身份验证的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="6819e-559">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="6819e-p182">几乎所有大型电子邮件接收器实现传统 SPF、 DKIM 和 DMARC。某些接收器具有其他检查比那些标准，但少转为未经验证的 Office 365 阻止更严格的电子邮件并将其视为欺骗。但是，大部分行业变得更严格有关此特定类型的电子邮件，特别是由于网络钓鱼的问题。</span><span class="sxs-lookup"><span data-stu-id="6819e-p182">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC. Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof. However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="6819e-563">是否仍需要启用"SPF 硬失败"如果启用反欺骗高级垃圾邮件筛选选项？</span><span class="sxs-lookup"><span data-stu-id="6819e-563">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="6819e-p183">否，因为反欺骗功能不仅认为 SPF 硬失败，但更广泛的条件，则不再需要此选项。如果您具有启用反欺骗并启用了 SPF 硬失败选项，您可能会获得更多误报。建议为垃圾邮件或网络钓鱼诈骗、 提供几乎没有任何其他捕获并相反生成主要误报禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="6819e-p183">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria. If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives. We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="6819e-567">发件人重写方案 (SR) 帮助修复转发电子邮件？</span><span class="sxs-lookup"><span data-stu-id="6819e-567">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="6819e-p184">SR 仅部分修复的问题的转发电子邮件。通过重写 SMTP 邮件从，SR 可以确保转发的邮件传递 SPF 下一个目标上。但是，由于反欺骗基于 From： 地址结合 MAIL FROM 或 DKIM 签名域 （或其他信号），它是不够以防止被标记为造假转发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6819e-p184">SRS only partially fixes the problem of forwarded email. By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination. However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>
  

