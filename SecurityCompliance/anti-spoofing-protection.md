---
title: Office 365 中的防欺骗保护
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/06/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
description: 本文介绍了 Office 365 如何缓解使用伪造的发件人域 (即欺骗的域) 的网络钓鱼攻击。它通过分析邮件并阻止可通过使用标准电子邮件身份验证方法 neithe 的身份验证的邮件, 也不会阻止其他发件人信誉技术, 从而实现这一点。实施此更改是为了减少向中公开的 Office 365 中的网络钓鱼攻击数。
ms.openlocfilehash: 041d2ee2cbad1c051c0ca4724d42b189215f0e82
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223871"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="539ef-105">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="539ef-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="539ef-p102">本文介绍了 Office 365 如何缓解使用伪造的发件人域 (即欺骗的域) 的网络钓鱼攻击。它通过分析邮件并阻止无法使用标准电子邮件身份验证方法 (也不能通过其他发件人信誉技术) 进行身份验证的邮件来实现这一点。正在实施此更改, 以减少客户暴露给的网络钓鱼攻击数。</span><span class="sxs-lookup"><span data-stu-id="539ef-p102">This article describes how Office 365 mitigates against phishing attacks that uses forged sender domains, that is, domains that are spoofed. It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques. This change is being implemented to reduce the number of phishing attacks customers are exposed to.</span></span>
  
<span data-ttu-id="539ef-109">此外, 本文还介绍了进行此更改的原因、客户如何准备进行此更改、如何查看将受到影响的邮件、如何对邮件进行报告、如何减少误报, 以及 Microsoft 的发件人如何为此做好准备更改.</span><span class="sxs-lookup"><span data-stu-id="539ef-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="539ef-p103">Microsoft 的反欺骗技术最初部署到其组织中的 office 365 企业版 E5 订阅或购买了 office 365 高级威胁防护 (ATP) 附加的订阅。从10月起, 2018 我们已扩展了对具有 Exchange Online protection (EOP) 的组织的保护。此外, 由于所有筛选器彼此之间都了解, Outlook.com 用户可能也会受到影响。</span><span class="sxs-lookup"><span data-stu-id="539ef-p103">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="539ef-113">如何在网络钓鱼攻击中使用欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="539ef-p104">在保护其用户的过程中, Microsoft 会严肃对待网络钓鱼威胁。垃圾邮件制造者和仿冒者通常使用的一种技术是哄骗, 这就是当发件人被伪造时, 消息显示为来自于实际来源以外的某人或其他地方。此技术通常用在旨在获取用户凭据的网络钓鱼活动中。Microsoft 的反欺骗技术专门检查 "发件人: 头" 的伪造, 即在电子邮件客户端 (如 Outlook) 中显示的。当 Microsoft 对 "发件人" 标头具有欺骗性的可信度时, 它会将邮件标识为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="539ef-p104">When it comes to protecting its users, Microsoft takes the threat of phishing seriously. One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source. This technique is often used in phishing campaigns designed to obtain user credentials. Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook. When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="539ef-119">哄骗邮件对真实用户有两个负面影响:</span><span class="sxs-lookup"><span data-stu-id="539ef-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="539ef-120">1. 欺骗性邮件欺骗用户</span><span class="sxs-lookup"><span data-stu-id="539ef-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="539ef-p105">首先, 欺骗性邮件可能会欺骗用户单击链接并放弃其凭据、下载恶意软件或回复包含敏感内容的邮件 (后者称为业务电子邮件泄露)。例如, 以下是具有 msoutlook94@service.outlook.com 欺骗发件人的网络钓鱼邮件:</span><span class="sxs-lookup"><span data-stu-id="539ef-p105">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise). For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![网络钓鱼邮件模拟 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="539ef-p106">上面实际上并不是来自 service.outlook.com, 而是由 phisher 欺骗以使其看起来像是一样。它试图欺骗用户单击邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="539ef-p106">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did. It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="539ef-126">下一个示例是哄骗 contoso.com:</span><span class="sxs-lookup"><span data-stu-id="539ef-126">The next example is spoofing contoso.com:</span></span>
  
![网络钓鱼邮件-业务电子邮件受损](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="539ef-p107">邮件看起来合法, 但实际上是欺骗。此网络钓鱼邮件是一种商业电子邮件泄露, 它是网络钓鱼的子类别。</span><span class="sxs-lookup"><span data-stu-id="539ef-p107">The message looks legitimate, but in fact is a spoof. This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="539ef-130">2. 用户混淆了假冒邮件的真实邮件</span><span class="sxs-lookup"><span data-stu-id="539ef-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="539ef-p108">其次, 欺骗邮件为了解网络钓鱼邮件的用户带来不确定性, 但不能辨别实际邮件和欺骗邮件之间的区别。例如, 以下是 Microsoft 安全帐户电子邮件地址中的实际密码重置示例:</span><span class="sxs-lookup"><span data-stu-id="539ef-p108">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one. For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法密码重置](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="539ef-p109">上述邮件确实来自 Microsoft, 但同时也用于获取网络钓鱼邮件, 这些邮件可能会欺骗用户单击链接并放弃其凭据、下载恶意软件或回复包含敏感内容的邮件。由于很难区分实际密码重置和伪造密码的区别, 许多用户会忽略这些邮件, 将它们报告为垃圾邮件, 或者不必要地将邮件作为错过的网络钓鱼骗局报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="539ef-p109">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content. Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>
    
<span data-ttu-id="539ef-p110">为了防止欺骗, 电子邮件筛选行业制定了电子邮件身份验证协议, 如[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)和[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)。DMARC 阻止电子邮件的发件人 (在其电子邮件客户端中看到的是用户在其电子邮件客户端中看到的) (在上述示例中, 为 service.outlook.com、outlook.com 和 accountprotection.microsoft.com) 以及通过了已通过 SPF 或 DKIM 的域。也就是说, 用户看到的域已经过身份验证, 因此是不欺骗的。有关更全面的讨论, 请参阅本文档后面的 "*了解为什么电子邮件身份验证并非始终足以阻止欺骗"* 。</span><span class="sxs-lookup"><span data-stu-id="539ef-p110">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email). DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM. That is, the domain that the user sees has been authenticated and is therefore not spoofed. For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this document.</span></span> 
  
<span data-ttu-id="539ef-p111">但是, 问题在于电子邮件身份验证记录是可选的, 而不是必需的。因此, 当保护具有类似 microsoft.com 和 skype.com 等强身份验证策略的域时, 不会受到欺骗的攻击、发布不够安全的身份验证策略或根本没有策略的域都是欺骗目标。从2018年3月起, 在财富500中仅有 9% 的公司将发布强大的电子邮件身份验证策略。其余 91% 可能被 phisher 欺骗, 除非电子邮件筛选器使用另一个策略检测它, 否则可能会将其传递给最终用户并欺骗他们:</span><span class="sxs-lookup"><span data-stu-id="539ef-p111">However, the problem is that email authentication records are optional, not required. Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies. The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![《财富500》公司的 DMARC 策略](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="539ef-144">发布强电子邮件身份验证策略的不在财富500中的中小型公司的比例较小, 并且对北美和西欧范围之外的域仍然较小。</span><span class="sxs-lookup"><span data-stu-id="539ef-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="539ef-145">这是一个很大的问题, 因为企业可能不知道电子邮件身份验证的工作方式, 而仿冒确实知道并充分利用缺少的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="539ef-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="539ef-146">有关设置 SPF、DKIM 和 DMARC 的信息, 请参阅本文档后面的 "*Office 365 的客户*" 一节。</span><span class="sxs-lookup"><span data-stu-id="539ef-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="539ef-147">通过隐式电子邮件身份验证停止欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="539ef-p112">由于网络钓鱼和 spear 的网络钓鱼是这样一个问题, 并且由于强大的电子邮件身份验证策略的采用有限, Microsoft 将继续投资保护其客户的功能。因此, microsoft 将继续进行*隐式电子邮件身份验证*-如果域不进行身份验证, 则 microsoft 会将其视为已发布的电子邮件身份验证记录, 并在未通过的情况下进行相应处理。</span><span class="sxs-lookup"><span data-stu-id="539ef-p112">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers. Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="539ef-p113">为实现此目的, Microsoft 已为常规电子邮件身份验证 (包括发件人信誉、发件人/收件人历史记录、行为分析和其他高级技术) 构建了大量扩展。从不发布电子邮件身份验证的域发送的邮件将被标记为欺骗, 除非它包含其他指示它是合法的信号。</span><span class="sxs-lookup"><span data-stu-id="539ef-p113">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques. A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="539ef-152">通过执行此操作, 最终用户可以确信发送给他们的电子邮件未被欺骗, 发件人可以确信没有人模拟其域, 而 Office 365 的客户可以提供更好的保护, 如模拟保护。</span><span class="sxs-lookup"><span data-stu-id="539ef-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="539ef-153">若要查看 Microsoft 的常规通知, 请参阅[网络钓鱼的海洋第2部分-Office 365 中增强的反欺骗](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。</span><span class="sxs-lookup"><span data-stu-id="539ef-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="539ef-154">确定邮件已分类为欺骗邮件</span><span class="sxs-lookup"><span data-stu-id="539ef-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="539ef-155">复合身份验证</span><span class="sxs-lookup"><span data-stu-id="539ef-155">Composite authentication</span></span>

<span data-ttu-id="539ef-p114">虽然 SPF、DKIM 和 DMARC 本身都很有用, 但在邮件没有显式身份验证记录的情况下, 它们不会传达足够的身份验证状态。因此, Microsoft 已经开发了将多个信号组合为单个称为复合身份验证的值的算法, 或将 compauth 用于短时间。Office 365 中的客户具有在邮件头的*身份验证结果*标头中标记的 compauth 值。</span><span class="sxs-lookup"><span data-stu-id="539ef-p114">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records. Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short. Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="539ef-159">**CompAuth 结果**</span><span class="sxs-lookup"><span data-stu-id="539ef-159">**CompAuth result**</span></span>|<span data-ttu-id="539ef-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="539ef-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="539ef-161">失败</span><span class="sxs-lookup"><span data-stu-id="539ef-161">fail</span></span>|<span data-ttu-id="539ef-162">消息无法显式身份验证 (在 dns 中显式发送域已发布的记录) 或隐式身份验证 (发送域在 dns 中未发布记录, 因此 Office 365 将结果插上为已发布的记录一样)。</span><span class="sxs-lookup"><span data-stu-id="539ef-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="539ef-163">超出</span><span class="sxs-lookup"><span data-stu-id="539ef-163">pass</span></span>|<span data-ttu-id="539ef-164">邮件已通过显式身份验证 (通过 DMARC 传递的邮件, 或[最佳推测传递的 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) 或具有高可信度的隐式身份验证 (发送域不会发布电子邮件身份验证记录, 但 Office 365 具有强大的后端信号来指明邮件可能是合法的。</span><span class="sxs-lookup"><span data-stu-id="539ef-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="539ef-165">softpass</span><span class="sxs-lookup"><span data-stu-id="539ef-165">softpass</span></span>|<span data-ttu-id="539ef-166">邮件已通过低到中等可信度的隐式身份验证 (发送域不会发布电子邮件身份验证, 但 Office 365 有后端信号指示邮件是合法的, 但信号强度较弱)。</span><span class="sxs-lookup"><span data-stu-id="539ef-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="539ef-167">无</span><span class="sxs-lookup"><span data-stu-id="539ef-167">none</span></span>|<span data-ttu-id="539ef-168">邮件未进行身份验证 (或身份验证但未对齐), 但由于发件人信誉或其他因素而未应用复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="539ef-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="539ef-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="539ef-169">**Reason**</span></span>|<span data-ttu-id="539ef-170">**说明**</span><span class="sxs-lookup"><span data-stu-id="539ef-170">**Description**</span></span>|
|<span data-ttu-id="539ef-171">0xx</span><span class="sxs-lookup"><span data-stu-id="539ef-171">0xx</span></span>|<span data-ttu-id="539ef-172">邮件的复合身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="539ef-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="539ef-173">**000**表示邮件失败, DMARC 操作为 "拒绝" 或 "隔离"。</span><span class="sxs-lookup"><span data-stu-id="539ef-173">**000** means the message failed DMARC with an action of reject or quarantine.</span></span>  <br/><span data-ttu-id="539ef-p115">**001**表示邮件的隐式电子邮件身份验证失败。这意味着发送域未发布电子邮件身份验证记录, 或者如果用户执行了此操作, 则它们具有较弱的失败策略 (SPF soft fail 或中立性, p = none 的 DMARC 策略)。</span><span class="sxs-lookup"><span data-stu-id="539ef-p115">**001** means the message failed implicit email authentication. This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).  </span></span><br/><span data-ttu-id="539ef-176">**002**表示组织具有对发件人/域对 (明确禁止发送欺骗电子邮件) 的策略, 管理员手动设置此设置。</span><span class="sxs-lookup"><span data-stu-id="539ef-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="539ef-177">**010**表示邮件失败, DMARC 操作为 "拒绝或隔离", 并且发送域是组织的接受域之一 (这是自到自助或组织内电子欺骗的一部分)。</span><span class="sxs-lookup"><span data-stu-id="539ef-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="539ef-178">**011**表示邮件的隐式电子邮件身份验证失败, 并且发送域是组织的接受域之一 (这是自到自助或组织内电子欺骗的一部分)。</span><span class="sxs-lookup"><span data-stu-id="539ef-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="539ef-179">所有其他代码 (1xx、2xx、3xx、4xx、5xx)</span><span class="sxs-lookup"><span data-stu-id="539ef-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="539ef-180">对应于邮件通过隐式身份验证传递的原因的各种内部代码, 或者不进行身份验证但未应用任何操作。</span><span class="sxs-lookup"><span data-stu-id="539ef-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="539ef-181">通过查看邮件的邮件头, 管理员甚至最终用户可以确定 Office 365 如何达到最终的结果, 即发件人可能被欺骗。</span><span class="sxs-lookup"><span data-stu-id="539ef-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="539ef-182">区分不同类型的欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="539ef-183">Microsoft 在两种不同类型的欺骗邮件中进行区分:</span><span class="sxs-lookup"><span data-stu-id="539ef-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="539ef-184">**组织内欺骗**</span><span class="sxs-lookup"><span data-stu-id="539ef-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="539ef-185">如果发件人: address 中的域与收件人域相同 (当收件人域是组织的[接受域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)之一时), 则会出现这种情况。或者, 当 "发件人:" 地址中的域是同一组织的一部分时。</span><span class="sxs-lookup"><span data-stu-id="539ef-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="539ef-p116">例如, 下面的发件人和收件人来自同一个域 (contoso.com)。在电子邮件地址中插入空格, 以防止垃圾邮件程序在此页上收集):</span><span class="sxs-lookup"><span data-stu-id="539ef-p116">For example, the following has sender and recipient from the same domain (contoso.com). Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="539ef-188">发件人: 发件人 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ef-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="539ef-189">收件人: 收件人 @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="539ef-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="539ef-190">以下是发件人和收件人域与组织域 (fabrikam.com) 的协调:</span><span class="sxs-lookup"><span data-stu-id="539ef-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="539ef-191">发件人: 发件人 @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="539ef-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="539ef-192">收件人: 收件人 @ bar.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="539ef-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="539ef-193">以下发件人和收件人域不同 (microsoft.com 和 bing.com), 但它们属于同一组织 (即, 这两个都是组织的接受域的一部分):</span><span class="sxs-lookup"><span data-stu-id="539ef-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="539ef-194">发件人: 发件人 @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="539ef-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="539ef-195">收件人: 收件人 @ bing.com</span><span class="sxs-lookup"><span data-stu-id="539ef-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="539ef-196">在组织内欺骗失败的邮件包含标头中的以下值:</span><span class="sxs-lookup"><span data-stu-id="539ef-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="539ef-197">X-Forefront-反垃圾邮件报告: .。。CAT: SPM/HSPM/PHSH; .。。SFTY: 9.11</span><span class="sxs-lookup"><span data-stu-id="539ef-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="539ef-198">CAT 是邮件的类别, 通常被标记为 SPM (垃圾邮件), 但偶尔可能是 HSPM (高可信度垃圾邮件) 或网络钓鱼 (网络钓鱼), 具体取决于邮件中出现的其他类型的模式。</span><span class="sxs-lookup"><span data-stu-id="539ef-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="539ef-199">SFTY 是邮件的安全级别, 第一个数字 (9) 表示邮件是网络钓鱼, 而点 (11) 后的第二组数字表示它是组织内欺骗。</span><span class="sxs-lookup"><span data-stu-id="539ef-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="539ef-200">组织内欺骗的复合身份验证没有特定的原因代码, 将在 2018 (尚未定义时间线) 中稍后对其进行标记。</span><span class="sxs-lookup"><span data-stu-id="539ef-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="539ef-201">**跨域欺骗**</span><span class="sxs-lookup"><span data-stu-id="539ef-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="539ef-p117">当发件人: address 中的发送域是接收组织的外部域时, 会发生这种情况。由于跨域欺骗导致复合身份验证失败的邮件包含标头中的以下值:</span><span class="sxs-lookup"><span data-stu-id="539ef-p117">This occurs when the sending domain in the From: address is an external domain to the receiving organization. Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="539ef-p118">身份验证-结果: .。。compauth = 失败原因 = 000/001</span><span class="sxs-lookup"><span data-stu-id="539ef-p118">Authentication-Results: … compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="539ef-206">X-Forefront-反垃圾邮件报告: .。。分类程序: 欺骗; .。。SFTY: 9.22</span><span class="sxs-lookup"><span data-stu-id="539ef-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="539ef-207">在这两种情况下, 邮件中都会标记以下红色安全提示, 或将自定义为收件人邮箱语言的等效项:</span><span class="sxs-lookup"><span data-stu-id="539ef-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![红色安全提示-欺诈检测](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="539ef-209">仅通过查看 "发件人:" 地址和了解收件人电子邮件的内容, 或通过检查电子邮件头来区分您可以区分组织内部和跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="539ef-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="539ef-210">Office 365 的客户如何为新的反欺骗保护进行自我准备</span><span class="sxs-lookup"><span data-stu-id="539ef-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="539ef-211">为管理员提供的信息</span><span class="sxs-lookup"><span data-stu-id="539ef-211">Information for administrators</span></span>

<span data-ttu-id="539ef-212">作为 Office 365 中的组织的管理员, 您应了解几个重要的信息部分。</span><span class="sxs-lookup"><span data-stu-id="539ef-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="539ef-213">了解为什么电子邮件身份验证始终不足以阻止欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="539ef-p119">新的反欺骗保护依赖于电子邮件身份验证 (SPF、DKIM 和 DMARC), 而不是将邮件标记为欺骗。一个常见的示例是发送域中从未发布的 SPF 记录。如果没有 SPF 记录或未正确设置它们, 则发送的邮件将被标记为 "欺骗", 除非 Microsoft 具有表明该邮件是合法邮件的后端智能。</span><span class="sxs-lookup"><span data-stu-id="539ef-p119">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing. A common example is when a sending domain has never published SPF records. If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="539ef-217">例如, 在部署反欺骗之前, 可能会出现一条消息, 看起来没有 SPF 记录, 没有 DKIM 记录, 并且没有 DMARC 记录:</span><span class="sxs-lookup"><span data-stu-id="539ef-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="539ef-218">反欺骗之后, 如果您有 Office 365 企业版 E5、EOP 或 ATP, compauth 值将被标记:</span><span class="sxs-lookup"><span data-stu-id="539ef-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="539ef-219">如果 example.com 通过设置 spf 记录而不是 DKIM 记录进行修复, 则此操作将传递复合身份验证, 因为在 From: address: 中传递了与域对齐的 SPF 的域。</span><span class="sxs-lookup"><span data-stu-id="539ef-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="539ef-220">或者, 如果他们设置的是 DKIM 记录, 而不是 SPF 记录, 这也会通过复合身份验证, 因为 DKIM 签名中的域与 "发件人: address:" 中的域相一致。</span><span class="sxs-lookup"><span data-stu-id="539ef-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="539ef-p120">但是, phisher 还可以设置 SPF 和 DKIM, 并使用其自己的域对邮件进行签名, 但在 "发件人:" 地址中指定不同的域。SPF 和 DKIM 都不要求域与 From: address 中的域对齐, 因此, 除非 example.com 发布 DMARC 记录, 否则不会将其标记为使用 DMARC 的欺骗:</span><span class="sxs-lookup"><span data-stu-id="539ef-p120">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address. Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="539ef-223">在电子邮件客户端 (outlook、web 上的 outlook 或任何其他电子邮件客户端) 中, 仅显示 "发件人: 域", 而不是 SPF 或 DKIM 中的域, 这会误导用户认为邮件来自 example.com, 但实际上来自 maliciousDomain.com.</span><span class="sxs-lookup"><span data-stu-id="539ef-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![经过身份验证的邮件, 但发件人: 域与传递的 SPF 或 DKIM 不一致](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="539ef-p121">出于此原因, Office 365 要求 "发件人: 地址" 中的域与 SPF 或 DKIM 签名中的域对齐, 如果不是, 则包含其他一些内部信号, 指示邮件是合法的。否则, 邮件将为 compauth 失败。</span><span class="sxs-lookup"><span data-stu-id="539ef-p121">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate. Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="539ef-p122">因此, Office 365 反欺骗可防止不进行身份验证的域, 并针对设置身份验证但不与 "发件人: 地址" 中的域不匹配的域 (即, "发件人" 地址中的域不匹配) 的域, 这是邮件的发件人。这既适用于组织外部的域, 也是组织中的域。</span><span class="sxs-lookup"><span data-stu-id="539ef-p122">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message. This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="539ef-229">因此, 如果您收到一条消息, 表明复合身份验证失败, 并且被标记为欺骗, 即使邮件已通过 spf 和 DKIM, 也是因为传递的 spf 和 DKIM 的域与 From: address 中的域不一致。</span><span class="sxs-lookup"><span data-stu-id="539ef-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="539ef-230">了解如何处理欺骗性电子邮件的更改</span><span class="sxs-lookup"><span data-stu-id="539ef-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="539ef-p123">目前, 对于 Office 365 中的所有组织, 通过拒绝或隔离策略将 DMARC 失败的电子邮件将被标记为垃圾邮件, 并且通常会采取高可信度垃圾邮件操作 (具体取决于其他垃圾邮件操作), 也可以是常规垃圾邮件操作 (具体取决于其他垃圾邮件)。规则首先将其标识为垃圾邮件)。组织内部欺骗检测采用常规的垃圾邮件操作。此行为不需要启用, 也不会被禁用。</span><span class="sxs-lookup"><span data-stu-id="539ef-p123">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam). Intra-org spoof detections take the regular spam action. This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="539ef-p124">但是, 对于跨域欺骗邮件, 在此更改之前, 它们将通过常规垃圾邮件、网络钓鱼和恶意软件检查, 如果筛选器的其他部分识别为可疑, 则应分别将其标记为垃圾邮件、网络钓鱼或恶意软件。通过新的跨域欺骗保护, 默认情况下, 任何无法通过身份验证的邮件都将采取反欺骗性\>反欺骗策略中定义的操作。如果未定义, 则会将其移动到 "用户垃圾邮件" 文件夹。在某些情况下, 更可疑的邮件也会添加到邮件中的红色安全提示。</span><span class="sxs-lookup"><span data-stu-id="539ef-p124">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively. With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy. If one is not defined, it will be moved to a users Junk Email folder. In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="539ef-p125">这可能会导致一些以前标记为垃圾邮件的邮件仍被标记为垃圾邮件, 但现在也会显示红色安全提示;在其他情况下, 以前标记为非垃圾邮件的邮件会开始添加红色安全提示, 并将其标记为垃圾邮件 (CAT: 欺骗)。在其他情况下, 将所有垃圾邮件和网络钓鱼转到隔离的客户现在会看到它们转到 "垃圾邮件" 文件夹 (此行为可能会更改, 请参阅[更改反欺骗设置](#changing-your-anti-spoofing-settings))。</span><span class="sxs-lookup"><span data-stu-id="539ef-p125">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added. In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="539ef-p126">有多种不同的方法可欺骗邮件 (请参阅本文前面的[不同类型的欺骗之间的区分](#differentiating-between-different-types-of-spoofing)), 但从3月2018日起, Office 365 处理这些邮件的方式还不是统一的。下表是一个快速摘要, 其中包含跨域欺骗保护的新行为:</span><span class="sxs-lookup"><span data-stu-id="539ef-p126">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified. The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="539ef-242">**哄骗类型**</span><span class="sxs-lookup"><span data-stu-id="539ef-242">**Type of spoof**</span></span>|<span data-ttu-id="539ef-243">**类别**</span><span class="sxs-lookup"><span data-stu-id="539ef-243">**Category**</span></span>|<span data-ttu-id="539ef-244">**是否添加安全提示？**</span><span class="sxs-lookup"><span data-stu-id="539ef-244">**Safety tip added?**</span></span>|<span data-ttu-id="539ef-245">**应用于**</span><span class="sxs-lookup"><span data-stu-id="539ef-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="539ef-246">DMARC 失败 (隔离或拒绝)</span><span class="sxs-lookup"><span data-stu-id="539ef-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="539ef-247">HSPM (默认值), 也可以是 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="539ef-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="539ef-248">否 (尚未)</span><span class="sxs-lookup"><span data-stu-id="539ef-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="539ef-249">所有 Office 365 客户, Outlook.com</span><span class="sxs-lookup"><span data-stu-id="539ef-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="539ef-250">自到自我</span><span class="sxs-lookup"><span data-stu-id="539ef-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="539ef-251">SPM</span><span class="sxs-lookup"><span data-stu-id="539ef-251">SPM</span></span>  <br/> |<span data-ttu-id="539ef-252">可访问</span><span class="sxs-lookup"><span data-stu-id="539ef-252">Yes</span></span>  <br/> |<span data-ttu-id="539ef-253">所有 Office 365 组织, Outlook.com</span><span class="sxs-lookup"><span data-stu-id="539ef-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="539ef-254">跨域</span><span class="sxs-lookup"><span data-stu-id="539ef-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="539ef-255">哄骗</span><span class="sxs-lookup"><span data-stu-id="539ef-255">SPOOF</span></span>  <br/> |<span data-ttu-id="539ef-256">可访问</span><span class="sxs-lookup"><span data-stu-id="539ef-256">Yes</span></span>  <br/> |<span data-ttu-id="539ef-257">Office 365 高级威胁防护和 E5 客户</span><span class="sxs-lookup"><span data-stu-id="539ef-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="539ef-258">更改反欺骗设置</span><span class="sxs-lookup"><span data-stu-id="539ef-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="539ef-p127">若要创建或更新 (跨域) 的反欺骗设置, 请导航到安全\> \> &amp;合规中心中 "威胁管理策略" 选项卡下的 "反钓鱼" 反欺骗设置。如果从未创建任何反网络钓鱼设置, 您将需要创建一个:</span><span class="sxs-lookup"><span data-stu-id="539ef-p127">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center. If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![Antiphishing-创建新策略](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="539ef-262">如果您已经创建了一个, 可以选择它来修改它:</span><span class="sxs-lookup"><span data-stu-id="539ef-262">If you've already created one, you can select it to modify it:</span></span>
  
![Antiphishing-修改现有策略](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="539ef-264">选择您刚刚创建的策略, 并按照[详细了解欺骗情报](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)中所述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="539ef-264">Select the policy you just created and proceed through the steps as described on [Learn More about Spoof Intelligence.](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span>
  
![启用或禁用 antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![启用或禁用 antispoofing 安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="539ef-267">若要通过 PowerShell 创建新策略, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="539ef-267">To create a new policy via PowerShell:</span></span> 
  
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

<span data-ttu-id="539ef-p128">然后, 您可以按照[AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)中的文档修改使用 PowerShell 的反网络钓鱼策略参数。您可以将 $name 指定为参数:</span><span class="sxs-lookup"><span data-stu-id="539ef-p128">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps). You may specify the $name as a parameter:</span></span>
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="539ef-270">稍后在2018中, 而不是创建默认策略时, 将为您创建一个范围限定于组织中的所有收件人的用户, 以便您无需手动指定它 (下图中的屏幕截图将在最终实施之前更改)。</span><span class="sxs-lookup"><span data-stu-id="539ef-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![Antiphishing 的默认策略](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="539ef-272">与所创建的策略不同, 您不能删除默认策略, 也不能修改其优先级, 也不能选择将其作用域的用户、域或组。</span><span class="sxs-lookup"><span data-stu-id="539ef-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![Antiphishing 默认策略详细信息](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="539ef-274">若要通过 PowerShell 设置默认保护, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="539ef-274">To set up your default protection via PowerShell:</span></span>
  
```
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="539ef-275">如果你在 Office 365 前端使用其他邮件服务器或服务器, 应仅禁用反欺骗保护 (有关详细信息, 请参阅合法方案以禁用反欺骗)。</span><span class="sxs-lookup"><span data-stu-id="539ef-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span> 
  
```
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="539ef-p129">如果您的电子邮件路径中的第一个跃点是 Office 365, 并且您要将过多的合法电子邮件标记为欺骗, 应首先设置允许向您的域发送欺骗电子邮件的发件人 (请参阅 *"管理正在发送的合法发件人" 一节。nauthenticated email "* )。如果仍收到过多误报 (例如, 被标记为欺骗的合法邮件), 我们建议您不要完全禁用反欺骗保护。相反, 我们建议选择 "基本" 而不是 "高" 保护。                   与向组织公开欺骗性的电子邮件相比, 更好的方法是使用误报, 这可能会导致长期产生显著增加的成本。</span><span class="sxs-lookup"><span data-stu-id="539ef-p129">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ). If you are still getting too many false positives (e.g., legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether. Instead, we recommend choosing Basic instead of High protection.                    It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="539ef-280">管理发送未经身份验证的电子邮件的合法发件人</span><span class="sxs-lookup"><span data-stu-id="539ef-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="539ef-p130">Office 365 跟踪向您的组织发送未经身份验证的电子邮件的用户。如果服务认为发件人不合法, 它会将其标记为*compauth*失败。这将归为欺骗, 尽管这取决于应用于邮件的反欺骗策略。</span><span class="sxs-lookup"><span data-stu-id="539ef-p130">Office 365 keeps track of who is sending unauthenticated email to your organization. If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure. This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span> 
  
<span data-ttu-id="539ef-284">但是, 作为管理员, 您可以指定允许哪些发件人发送欺骗电子邮件, 替代 Office 365 的决定。</span><span class="sxs-lookup"><span data-stu-id="539ef-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="539ef-285">**方法 1-如果你的组织拥有域, 请设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="539ef-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="539ef-p131">此方法可用于在您拥有或与多个租户进行交互的情况下解析组织内欺骗和跨域欺骗。它还有助于解析在 Office 365 中发送给其他客户的跨域欺骗, 以及其他提供商托管的第三方。</span><span class="sxs-lookup"><span data-stu-id="539ef-p131">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants. It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="539ef-288">有关更多详细信息, 请参阅[Office 365 的客户](#customers-of-office-365)。</span><span class="sxs-lookup"><span data-stu-id="539ef-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span> 
 
<span data-ttu-id="539ef-289">**方法 2-使用欺骗智能配置未经身份验证的电子邮件的允许发件人**</span><span class="sxs-lookup"><span data-stu-id="539ef-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="539ef-290">您还可以使用[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf), 以允许发件人将未经过身份验证的邮件传输到您的组织。</span><span class="sxs-lookup"><span data-stu-id="539ef-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="539ef-291">对于外部域, 欺骗用户是 "发件人" 地址中的域, 而 "发送" 基础结构是发送 IP 地址 (分成/24 个 CIDR 范围) 或 PTR 记录的组织域 (在下面的屏幕截图中, 发送 IP 可能是131.107.18.4 其 PTR 记录是 outbound.mail.protection.outlook.com 的, 这将显示为发送基础结构的 outlook.com。</span><span class="sxs-lookup"><span data-stu-id="539ef-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="539ef-292">若要允许此发件人发送未经身份验证的电子邮件, 请将**No**改为**是**。</span><span class="sxs-lookup"><span data-stu-id="539ef-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![设置 antispoofing 允许的发件人](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="539ef-294">您还可以使用 PowerShell 来允许特定发件人欺骗您的域:</span><span class="sxs-lookup"><span data-stu-id="539ef-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span> 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![通过 Powershell 获取欺骗性发件人](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="539ef-296">在上一个图像中, 添加了额外的换行符以使此屏幕截图合适, 但实际上所有值都将出现在单行中。</span><span class="sxs-lookup"><span data-stu-id="539ef-296">In the previous image, additional line breaks have been added to make this screenshot fit, but in actuality all the values would appear on a single line.</span></span>
  
<span data-ttu-id="539ef-297">编辑文件并查找与 outlook.com 和 bing.com 相对应的行, 并将 AllowedToSpoof 条目从 "否" 更改为 "是":</span><span class="sxs-lookup"><span data-stu-id="539ef-297">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof Entry from No to Yes:</span></span>
  
![通过 Powershell 将欺骗允许设置为是](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="539ef-299">保存该文件, 然后运行:</span><span class="sxs-lookup"><span data-stu-id="539ef-299">Save the file, and then run:</span></span> 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="539ef-300">这现在将允许 bing.com 从 outlook.com 发送未经身份\*验证的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="539ef-300">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="539ef-301">**方法 3-为发件人/收件人对创建允许条目**</span><span class="sxs-lookup"><span data-stu-id="539ef-301">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="539ef-p132">您还可以选择绕过特定发件人的所有垃圾邮件筛选。有关更多详细信息, 请参阅[如何在 Office 365 中安全地将发件人添加到允许列表](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="539ef-p132">You can also choose to bypass all spam filtering for a particular sender. For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="539ef-304">如果使用此方法, 它将跳过垃圾邮件和某些网络钓鱼筛选, 但不会对恶意软件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="539ef-304">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="539ef-305">**方法 4-联系发件人并要求他们设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="539ef-305">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="539ef-p133">由于垃圾邮件和网络钓鱼问题, Microsoft 建议所有发件人设置电子邮件身份验证。如果您知道发送域的管理员, 请与他们联系并请求他们设置电子邮件身份验证记录, 这样您就不必添加任何替代。有关详细信息, 请参阅本文后面的[非 Office 365 客户的域管理员](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="539ef-p133">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication. If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides. For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="539ef-309">有时, 随着时间的推移, 如果越来越多的电子邮件筛选器启动 junking 甚至拒绝他们的电子邮件, 可能会很难进行身份验证, 这将导致用户设置正确的记录以确保更好地进行传递。</span><span class="sxs-lookup"><span data-stu-id="539ef-309">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="539ef-310">查看标记为欺骗的邮件的报告</span><span class="sxs-lookup"><span data-stu-id="539ef-310">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="539ef-p134">启用反欺骗策略后, 您可以使用威胁情报获取有关标记为网络钓鱼的邮件数的数字。为此, 请进入 "威胁管理&amp; \>资源管理器" 下的 "安全合规中心 (SCC)", 将视图设置为网络钓鱼, 并按发件人域或保护状态分组:</span><span class="sxs-lookup"><span data-stu-id="539ef-p134">Once your anti-spoofing policy is enabled, you can use Threat Intelligence to get numbers around how many messages are marked as phish. To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![查看标记为网络钓鱼的邮件数](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="539ef-p135">您可以与各种报告进行交互, 以查看标记为网络钓鱼的邮件数, 包括标记为欺骗的邮件。若要了解详细信息, 请参阅[Office 365 威胁智能入门入门](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)。</span><span class="sxs-lookup"><span data-stu-id="539ef-p135">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF. To learn more, see [Get started with Office 365 Threat Intelligence](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441).</span></span>
  
<span data-ttu-id="539ef-p136">您还不能拆分那些由于哄骗和其他类型的网络钓鱼 (常规网络钓鱼、域或用户模拟等) 而标记的邮件。不过, 在随后的2018中, 你将能够通过安全&amp;合规性中心执行此操作。执行此操作后, 您可以使用此报告作为一种开始位置, 用于识别可能是合法的发送域, 因为身份验证失败而被标记为欺骗。</span><span class="sxs-lookup"><span data-stu-id="539ef-p136">You cannot yet split out which messages were marked due to spoofing vs. other types of phishing (general phishing, domain or user impersonation, and so on). However, later in 2018, you will be able to do this through the Security &amp; Compliance Center. Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="539ef-319">下面的屏幕截图是此数据外观的建议, 但在发布后可能会发生变化:</span><span class="sxs-lookup"><span data-stu-id="539ef-319">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![按检测类型查看网络钓鱼报告](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="539ef-p137">对于非 ATP 和 E5 客户, 这些报告将在 "威胁防护状态 (TPS)" 报告下的2018的后面提供, 但将延迟至少24小时。此页面将在集成到安全&amp;合规性中心时进行更新。</span><span class="sxs-lookup"><span data-stu-id="539ef-p137">For non-ATP and E5 customers, these reports will be available later in 2018 under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours. This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="539ef-323">预测将把多少封邮件标记为欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-323">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="539ef-p138">在后面的2018中, 一旦 Office 365 更新了其设置以允许您关闭反欺骗强制实施, 或者在基本或高强制实施的情况下, 您就可以查看邮件处置在不同设置下的更改方式。也就是说, 如果反欺骗已关闭, 你将能够查看将被检测为欺骗的邮件的数量 (如果你启用了 "基本");或者, 如果它是基本的, 您将能够查看将多少封邮件检测为欺骗邮件 (如果您将其设为 "高")。</span><span class="sxs-lookup"><span data-stu-id="539ef-p138">Later in 2018, once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings. That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="539ef-p139">此功能目前正在开发中。由于定义了更多详细信息, 此页面将随安全与合规中心的屏幕截图以及 PowerShell 示例一起进行更新。</span><span class="sxs-lookup"><span data-stu-id="539ef-p139">This feature is currently under development. As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![启用 antispoofing 的 "假设" 报告](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![允许欺骗发件人的可能的 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a><span data-ttu-id="539ef-330">了解如何组合垃圾邮件、网络钓鱼和高级网络钓鱼检测</span><span class="sxs-lookup"><span data-stu-id="539ef-330">Understanding how spam, phishing, and advanced phishing detections are combined</span></span>

<span data-ttu-id="539ef-p140">使用 Exchange Online (带有或不带 ATP) 的组织可以指定在服务将邮件标识为恶意软件、垃圾邮件、高可信度垃圾邮件、网络钓鱼和批量时要采取的操作。对于 atp 客户的 atp 反网络钓鱼策略和 EOP 客户的反网络钓鱼策略, 以及邮件可能遇到多个检测类型 (例如, 恶意软件、网络钓鱼和用户模拟) 的情况下, 可能会对其产生一些困惑。策略适用。</span><span class="sxs-lookup"><span data-stu-id="539ef-p140">Organizations that use Exchange Online, with or without ATP, can specify which actions to take when the service identifies messages as malware, spam, high confidence spam, phishing, and bulk. With the ATP Anti-phishing policies for ATP customers, and the Anti-phishing policies for EOP customers, and the fact that a message may hit multiple detection types (for example, malware, phishing, and user-impersonation), there may be some confusion as to which policy applies.</span></span> 
  
<span data-ttu-id="539ef-333">通常情况下, 应用于邮件的策略在 CAT (Category) 属性中的 X-Forefront-反垃圾邮件报告标头中进行标识。</span><span class="sxs-lookup"><span data-stu-id="539ef-333">In general, the policy applied to a message is identified in the X-Forefront-Antispam-Report header in the CAT (Category) property.</span></span> 
  
|<span data-ttu-id="539ef-334">**优先级**</span><span class="sxs-lookup"><span data-stu-id="539ef-334">**Priority**</span></span>|<span data-ttu-id="539ef-335">**政策**</span><span class="sxs-lookup"><span data-stu-id="539ef-335">**Policy**</span></span>|<span data-ttu-id="539ef-336">**类别**</span><span class="sxs-lookup"><span data-stu-id="539ef-336">**Category**</span></span>|<span data-ttu-id="539ef-337">**在什么情况下托管？**</span><span class="sxs-lookup"><span data-stu-id="539ef-337">**Where managed?**</span></span>|<span data-ttu-id="539ef-338">**应用于**</span><span class="sxs-lookup"><span data-stu-id="539ef-338">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="539ef-339">1</span><span class="sxs-lookup"><span data-stu-id="539ef-339">1</span></span>  <br/> |<span data-ttu-id="539ef-340">恶意软件</span><span class="sxs-lookup"><span data-stu-id="539ef-340">Malware</span></span>  <br/> |<span data-ttu-id="539ef-341">MALW</span><span class="sxs-lookup"><span data-stu-id="539ef-341">MALW</span></span>  <br/> |[<span data-ttu-id="539ef-342">恶意软件策略</span><span class="sxs-lookup"><span data-stu-id="539ef-342">Malware policy</span></span>](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="539ef-343">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-343">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-344">双面</span><span class="sxs-lookup"><span data-stu-id="539ef-344">2</span></span>  <br/> |<span data-ttu-id="539ef-345">骗术</span><span class="sxs-lookup"><span data-stu-id="539ef-345">Phishing</span></span>  <br/> |<span data-ttu-id="539ef-346">PHSH</span><span class="sxs-lookup"><span data-stu-id="539ef-346">PHSH</span></span>  <br/> |[<span data-ttu-id="539ef-347">托管的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="539ef-347">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="539ef-348">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-348">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-349">第三章</span><span class="sxs-lookup"><span data-stu-id="539ef-349">3</span></span>  <br/> |<span data-ttu-id="539ef-350">可信度高的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="539ef-350">High confidence spam</span></span>  <br/> |<span data-ttu-id="539ef-351">HSPM</span><span class="sxs-lookup"><span data-stu-id="539ef-351">HSPM</span></span>  <br/> |[<span data-ttu-id="539ef-352">托管的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="539ef-352">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="539ef-353">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-353">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-354">4</span><span class="sxs-lookup"><span data-stu-id="539ef-354">4</span></span>  <br/> |<span data-ttu-id="539ef-355">冒充</span><span class="sxs-lookup"><span data-stu-id="539ef-355">Spoofing</span></span>  <br/> |<span data-ttu-id="539ef-356">哄骗</span><span class="sxs-lookup"><span data-stu-id="539ef-356">SPOOF</span></span>  <br/> |<span data-ttu-id="539ef-357">[反网络钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553)、[欺骗性智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span><span class="sxs-lookup"><span data-stu-id="539ef-357">[Anti-phishing policy](https://go.microsoft.com/fwlink/?linkid=864553),          [Spoof intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)</span></span> <br/> |<span data-ttu-id="539ef-358">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-358">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-359">5</span><span class="sxs-lookup"><span data-stu-id="539ef-359">5</span></span>  <br/> |<span data-ttu-id="539ef-360">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="539ef-360">Spam</span></span>  <br/> |<span data-ttu-id="539ef-361">SPM</span><span class="sxs-lookup"><span data-stu-id="539ef-361">SPM</span></span>  <br/> |[<span data-ttu-id="539ef-362">托管的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="539ef-362">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="539ef-363">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-363">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-364">6 </span><span class="sxs-lookup"><span data-stu-id="539ef-364">6</span></span>  <br/> |<span data-ttu-id="539ef-365">群发</span><span class="sxs-lookup"><span data-stu-id="539ef-365">Bulk</span></span>  <br/> |<span data-ttu-id="539ef-366">群发</span><span class="sxs-lookup"><span data-stu-id="539ef-366">BULK</span></span>  <br/> |[<span data-ttu-id="539ef-367">托管的内容筛选器策略</span><span class="sxs-lookup"><span data-stu-id="539ef-367">Hosted content filter policy</span></span>](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |<span data-ttu-id="539ef-368">所有组织</span><span class="sxs-lookup"><span data-stu-id="539ef-368">All organizations</span></span>  <br/> |
|<span data-ttu-id="539ef-369">7 </span><span class="sxs-lookup"><span data-stu-id="539ef-369">7</span></span>  <br/> |<span data-ttu-id="539ef-370">域模拟</span><span class="sxs-lookup"><span data-stu-id="539ef-370">Domain Impersonation</span></span>  <br/> |<span data-ttu-id="539ef-371">DIMP</span><span class="sxs-lookup"><span data-stu-id="539ef-371">DIMP</span></span>  <br/> |[<span data-ttu-id="539ef-372">反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="539ef-372">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="539ef-373">仅含 ATP 的组织</span><span class="sxs-lookup"><span data-stu-id="539ef-373">Organizations with ATP only</span></span>  <br/> |
|<span data-ttu-id="539ef-374">8 </span><span class="sxs-lookup"><span data-stu-id="539ef-374">8</span></span>  <br/> |<span data-ttu-id="539ef-375">用户模拟</span><span class="sxs-lookup"><span data-stu-id="539ef-375">User Impersonation</span></span>  <br/> |<span data-ttu-id="539ef-376">UIMP</span><span class="sxs-lookup"><span data-stu-id="539ef-376">UIMP</span></span>  <br/> |[<span data-ttu-id="539ef-377">反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="539ef-377">Anti-phishing policy</span></span>](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |<span data-ttu-id="539ef-378">仅含 ATP 的组织</span><span class="sxs-lookup"><span data-stu-id="539ef-378">Organizations with ATP only</span></span> <br/> |
   
<span data-ttu-id="539ef-p141">如果有多个不同的反网络钓鱼策略, 则会应用最高优先级的策略。例如, 假设您有两个策略:</span><span class="sxs-lookup"><span data-stu-id="539ef-p141">If you have multiple different Anti-phishing policies, the one at the highest priority will apply. For example, suppose you have two policies:</span></span>
  
|<span data-ttu-id="539ef-381">**政策**</span><span class="sxs-lookup"><span data-stu-id="539ef-381">**Policy**</span></span>|<span data-ttu-id="539ef-382">**优先级**</span><span class="sxs-lookup"><span data-stu-id="539ef-382">**Priority**</span></span>|<span data-ttu-id="539ef-383">**用户/域模拟**</span><span class="sxs-lookup"><span data-stu-id="539ef-383">**User/Domain Impersonation**</span></span>|<span data-ttu-id="539ef-384">**反欺骗**</span><span class="sxs-lookup"><span data-stu-id="539ef-384">**Anti-spoofing**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="539ef-385">A</span><span class="sxs-lookup"><span data-stu-id="539ef-385">A</span></span>  <br/> |<span data-ttu-id="539ef-386">1</span><span class="sxs-lookup"><span data-stu-id="539ef-386">1</span></span>  <br/> |<span data-ttu-id="539ef-387">On</span><span class="sxs-lookup"><span data-stu-id="539ef-387">On</span></span>  <br/> |<span data-ttu-id="539ef-388">Off</span><span class="sxs-lookup"><span data-stu-id="539ef-388">Off</span></span>  <br/> |
|<span data-ttu-id="539ef-389">B</span><span class="sxs-lookup"><span data-stu-id="539ef-389">B</span></span>  <br/> |<span data-ttu-id="539ef-390">双面</span><span class="sxs-lookup"><span data-stu-id="539ef-390">2</span></span>  <br/> |<span data-ttu-id="539ef-391">关</span><span class="sxs-lookup"><span data-stu-id="539ef-391">Off</span></span>  <br/> |<span data-ttu-id="539ef-392">位置</span><span class="sxs-lookup"><span data-stu-id="539ef-392">On</span></span>  <br/> |
   
<span data-ttu-id="539ef-393">如果邮件传入且被标识为欺骗和用户模拟, 并且同一组用户的范围限定为策略 a 和策略 B, 则邮件将被视为欺骗邮件, 但由于反欺骗已关闭, 因此不会应用任何操作, 并且欺骗以高于用户模拟的优先级 (4) 运行 (8)。</span><span class="sxs-lookup"><span data-stu-id="539ef-393">If a message comes in and is identified as both spoofing and user impersonation, and the same set of users is scoped to Policy A and Policy B, then the message is treated as a spoof but no action is applied since Anti-spoofing is turned off, and SPOOF runs at a higher priority (4) than User Impersonation (8).</span></span>
  
<span data-ttu-id="539ef-394">若要应用其他类型的网络钓鱼策略, 您将需要调整应用不同策略的用户的设置。</span><span class="sxs-lookup"><span data-stu-id="539ef-394">To make other types of phishing policy apply, you will need to adjust the settings of who the various policies are applied to.</span></span>
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="539ef-395">禁用反欺骗的合法方案</span><span class="sxs-lookup"><span data-stu-id="539ef-395">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="539ef-p142">反欺骗可更好地保护客户免受网络钓鱼攻击, 因此强烈建议不要禁用反欺骗保护。通过禁用它, 可以解决某些短期误报, 但长期会暴露给更多风险。在发件人端上设置身份验证或在网络钓鱼策略中进行调整的成本通常是一次性事件, 或者只需要最少的定期维护。但是, 从数据泄露的网络钓鱼攻击中恢复的成本, 或资产受到危害的成本高得多。</span><span class="sxs-lookup"><span data-stu-id="539ef-p142">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged. By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk. The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance. However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="539ef-400">因此, 最好通过反欺骗误报, 而不是禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="539ef-400">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="539ef-401">但是, 有一个合法方案应禁用反欺骗, 这就是邮件路由中存在其他邮件筛选产品, 而 Office 365 不是电子邮件路径中的第一个跃点:</span><span class="sxs-lookup"><span data-stu-id="539ef-401">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客户 MX 记录未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="539ef-403">其他服务器可以是 Exchange 本地邮件服务器、邮件筛选设备 (如 Ironport) 或其他云托管服务。</span><span class="sxs-lookup"><span data-stu-id="539ef-403">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="539ef-p143">如果收件人域的 MX 记录未指向 Office 365, 则无需禁用反欺骗, 因为 Office 365 会查看您的接收域的 MX 记录, 如果它指向其他服务, 则禁止反欺骗。如果您不知道您的域在前面是否有另一台服务器, 则可以使用 mx 工具箱等网站来查找 mx 记录。它可能会说出如下所示的内容:</span><span class="sxs-lookup"><span data-stu-id="539ef-p143">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service. If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record. It might say something like the following:</span></span>
  
![MX 记录指示域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="539ef-408">此域具有不指向 office 365 的 MX 记录, 因此 Office 365 将不会应用反欺骗强制实施。</span><span class="sxs-lookup"><span data-stu-id="539ef-408">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="539ef-p144">但是, 如果收件人域的 MX 记录指向 office \*\* 365, 即使 office 365 前面有另一个服务, 也应禁用反欺骗。最常见的示例是使用收件人重写:</span><span class="sxs-lookup"><span data-stu-id="539ef-p144">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing. The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件人重写的路由关系图](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="539ef-412">域 contoso .com 的 mx 记录指向内部部署服务器, 而域 @office365 的 mx 记录指向 Office 365, 因为它包含\*protection.outlook.com 或\*eo.outlook.com 在 MX 记录中:</span><span class="sxs-lookup"><span data-stu-id="539ef-412">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 记录指向 Office 365, 因此可能会重写收件人](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="539ef-p145">请务必区分收件人域的 MX 记录不指向 Office 365 时, 以及当它完成了收件人重写的时间。一定要区分这两种情况的区别。</span><span class="sxs-lookup"><span data-stu-id="539ef-p145">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite. It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="539ef-416">如果您不确定接收域是否已完成收件人重写, 有时可以通过查看邮件头来判断。</span><span class="sxs-lookup"><span data-stu-id="539ef-416">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="539ef-417">a) 首先, 在身份验证-结果标头中查看收件人域邮件中的邮件头:</span><span class="sxs-lookup"><span data-stu-id="539ef-417">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span> 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="539ef-p146">在上面的红色粗体文本中找到收件人域, 在此示例中为 office365.contoso.net。这可能与收件人: 头中的收件人不同:</span><span class="sxs-lookup"><span data-stu-id="539ef-p146">The recipient domain is found in the bold red text above, in this case office365.contoso.net. This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="539ef-420">收件人: 示例收件人\<收件人 @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="539ef-420">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="539ef-p147">执行实际收件人域的 MX 记录查找。如果它包含\*protection.outlook.com、mail.messaging.microsoft.com、 \*eo.outlook.com 或 mail.global.frontbridge.com, 则表示 MX 指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="539ef-p147">Perform an MX-record lookup of the actual recipient domain. If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="539ef-p148">如果它不包含这些值, 则表示 MX 不指向 Office 365。您可以使用一种工具来验证这是 MX 工具箱。</span><span class="sxs-lookup"><span data-stu-id="539ef-p148">If it does not contain those values, then it means that the MX does not point to Office 365. One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="539ef-425">在此特定示例中, 以下说出的是 contoso.com, 因为它是 "收件人: 标头" 的域, MX 记录指向本地 server:</span><span class="sxs-lookup"><span data-stu-id="539ef-425">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 记录指向本地服务器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="539ef-427">但是, 实际的收件人是 office365.contoso.net, 其 MX 记录指向 Office 365:</span><span class="sxs-lookup"><span data-stu-id="539ef-427">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 指向 Office 365, 必须是收件人重写](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="539ef-429">因此, 此邮件可能已完成收件人重写。</span><span class="sxs-lookup"><span data-stu-id="539ef-429">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="539ef-p149">b) 其次, 请务必区分收件人重写的常见用例。如果要将收件人域\*重写为 onmicrosoft.com, 则改为将其重写\*为. mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="539ef-p149">b) Second, be sure to distinguish between common use cases of recipient rewrites. If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="539ef-432">确定了路由到另一台服务器后面的最终收件人域, 并且收件人域的 MX 记录实际指向 Office 365 (在其 DNS 记录中发布) 后, 您可以继续禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="539ef-432">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="539ef-433">请记住, 如果路由路径中的第一个跃点是 Office 365, 则不需要禁用反欺骗, 仅当它位于一个或多个服务的后面时。</span><span class="sxs-lookup"><span data-stu-id="539ef-433">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="539ef-434">如何禁用反欺骗</span><span class="sxs-lookup"><span data-stu-id="539ef-434">How to disable anti-spoofing</span></span>

<span data-ttu-id="539ef-435">如果您已创建了一个反网络钓鱼策略, 请将 EnableAntispoofEnforcement 参数设置为 $false:</span><span class="sxs-lookup"><span data-stu-id="539ef-435">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span> 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

<span data-ttu-id="539ef-436">如果您不知道要禁用的策略的名称 (或策略), 则可以显示它们:</span><span class="sxs-lookup"><span data-stu-id="539ef-436">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span> 
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="539ef-p150">如果没有任何现有的反网络钓鱼策略, 则可以创建一个这些策略, 然后将其禁用 (即使您没有策略, 仍会应用反欺骗; 在2018中, 稍后将为您创建一个默认策略, 然后您可以禁用它而不是创建一个).您必须按多个步骤执行此操作:</span><span class="sxs-lookup"><span data-stu-id="539ef-p150">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one). You will have to do this in multiple steps:</span></span> 
  
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

<span data-ttu-id="539ef-p151">禁用反欺骗只是通过 cmdlet 提供 (在第2季度中, 在安全&amp;合规中心中将提供此功能)。如果您对 PowerShell 没有访问权限, 请创建支持票证。</span><span class="sxs-lookup"><span data-stu-id="539ef-p151">Disabling anti-spoofing is only available via cmdlet (later in Q2 2018 it will be available in the Security &amp; Compliance Center). If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="539ef-p152">请记住, 这仅适用于发送到 Office 365 时进行间接路由的域。避免由于某些误报而禁用反欺骗的诱惑, 它在运行时可能会更好。</span><span class="sxs-lookup"><span data-stu-id="539ef-p152">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365. Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="539ef-443">单个用户的信息</span><span class="sxs-lookup"><span data-stu-id="539ef-443">Information for individual users</span></span>

<span data-ttu-id="539ef-p153">单个用户在如何与反欺骗安全提示进行交互方面受到限制。不过, 可以通过几种方法来解决常见方案。</span><span class="sxs-lookup"><span data-stu-id="539ef-p153">Individual users are limited in how they can interact with the anti-spoofing safety tip. However, there are several things you can do to resolve common scenarios.</span></span>
  
### <a name="common-scenario-1---mailbox-forwarding"></a><span data-ttu-id="539ef-446">常见方案 #1-邮箱转发</span><span class="sxs-lookup"><span data-stu-id="539ef-446">Common scenario #1 - Mailbox forwarding</span></span>

<span data-ttu-id="539ef-p154">如果使用其他电子邮件服务并将电子邮件转发到 Office 365 或 Outlook.com, 则可能会将您的电子邮件标记为哄骗并收到红色的安全提示。当转发器是 Outlook.com、Office 365、Gmail 或任何其他使用[ARC 协议](https://arc-spec.org)的服务之一时, Office 365 和 Outlook.com 计划自动解决此情况。但是, 在部署该修补程序之前, 用户应使用 "已连接帐户" 功能直接导入邮件, 而不是使用转发选项。</span><span class="sxs-lookup"><span data-stu-id="539ef-p154">If you use another email service and forward your email to Office 365 or Outlook.com, your email may be marked as spoofing and receive a red safety tip. Office 365 and Outlook.com plan to address this automatically when the forwarder is one of Outlook.com, Office 365, Gmail, or any other service that uses the [ARC protocol](https://arc-spec.org). However, until that fix is deployed, users should use the Connected Accounts feature to import their messages directly, rather than using the forwarding option.</span></span>
  
<span data-ttu-id="539ef-450">若要在 office 365 中设置连接的帐户, 请选择 office 365 web \>界面邮件\>邮件\>帐户\>连接帐户右上角的齿轮图标。</span><span class="sxs-lookup"><span data-stu-id="539ef-450">To set up connected accounts in Office 365, select the Gear icon in the top right corner of the Office 365 web interface \> Mail \> Mail \> Accounts \> Connected accounts.</span></span>
  
!["Office 365-已连接帐户" 选项](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
<span data-ttu-id="539ef-452">在 Outlook.com 中, 该过程是 "齿轮\> " \>图标\>选项\>邮件帐户已连接帐户。</span><span class="sxs-lookup"><span data-stu-id="539ef-452">In Outlook.com, the process is the Gear icon \> Options \> Mail \> Accounts \> Connected accounts.</span></span>
  
### <a name="common-scenario-2---discussion-lists"></a><span data-ttu-id="539ef-453">常见方案 #2-讨论列表</span><span class="sxs-lookup"><span data-stu-id="539ef-453">Common scenario #2 - Discussion lists</span></span>

<span data-ttu-id="539ef-454">如果讨论列表转发邮件和修改其内容, 则这些列表会遇到防欺骗问题, 同时保留原始的发件人: 地址。</span><span class="sxs-lookup"><span data-stu-id="539ef-454">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="539ef-p155">例如, 假设您的电子邮件地址是用户 @ contoso.com, 并且您希望鸟瞰和加入讨论列表 birdwatchers @ example.com。向讨论列表发送邮件时, 可以通过以下方式发送邮件:</span><span class="sxs-lookup"><span data-stu-id="539ef-p155">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com. When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="539ef-457">**发件人:** John Doe \<用户 @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="539ef-457">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="539ef-458">**到:** Birdwatcher 的讨论列表\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="539ef-458">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="539ef-p156">**主题:** 很好地查看 Mt 顶部的蓝色 jays。 Rainier</span><span class="sxs-lookup"><span data-stu-id="539ef-p156">**Subject:** Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="539ef-p157">任何人都希望从 Rainier 中查看这一周？</span><span class="sxs-lookup"><span data-stu-id="539ef-p157">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
<span data-ttu-id="539ef-463">当电子邮件列表收到邮件时, 它们会对邮件进行格式设置, 修改其内容, 并将其重放到讨论列表上的其余成员, 这些内容由许多不同的电子邮件接收器的参与者组成。</span><span class="sxs-lookup"><span data-stu-id="539ef-463">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="539ef-464">**发件人:** John Doe \<用户 @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="539ef-464">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="539ef-465">**到:** Birdwatcher 的讨论列表\<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="539ef-465">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="539ef-p158">**主题:**[BIRDWATCHERS]很好地查看 Mt 顶部的蓝色 jays。 Rainier</span><span class="sxs-lookup"><span data-stu-id="539ef-p158">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt. Rainier this week</span></span> 
  
<span data-ttu-id="539ef-p159">任何人都希望从 Rainier 中查看这一周？</span><span class="sxs-lookup"><span data-stu-id="539ef-p159">Anyone want to check out the viewing this week from Mt. Rainier?</span></span>
  
---
  
<span data-ttu-id="539ef-p160">此邮件已发送到 Birdwatchers 讨论列表。您可以随时取消订阅。</span><span class="sxs-lookup"><span data-stu-id="539ef-p160">This message was sent to the Birdwatchers Discussion List. You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="539ef-p161">在上面的邮件中, 重播邮件与 "address" (user @ contoso.com) 相同, 但原始邮件已通过将标记添加到 "主题" 行, 并将页脚添加到邮件底部来进行修改。这种类型的邮件修改在邮件列表中很常见, 可能会导致误报。</span><span class="sxs-lookup"><span data-stu-id="539ef-p161">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message. This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="539ef-474">如果您或组织中的某个人是邮寄列表的管理员, 则可以将其配置为传递反欺骗检查。</span><span class="sxs-lookup"><span data-stu-id="539ef-474">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="539ef-475">检查 DMARC.org 中的 FAQ:[我运行的是邮寄列表, 我想与 DMARC 进行互操作, 我该怎么办？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="539ef-475">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>
    
- <span data-ttu-id="539ef-476">阅读以下博客文章中的说明:[用于与 DMARC 进行互操作以避免故障的邮件列表运算符提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="539ef-476">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>
    
- <span data-ttu-id="539ef-477">请考虑在邮寄列表服务器上安装更新以支持 ARC, 请参阅[https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="539ef-477">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>
    
<span data-ttu-id="539ef-478">如果您没有邮寄列表的所有权:</span><span class="sxs-lookup"><span data-stu-id="539ef-478">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="539ef-479">您可以请求邮件列表的 maintainer 实现上述选项之一 (他们还应为邮寄列表正在中继的域设置电子邮件身份验证)</span><span class="sxs-lookup"><span data-stu-id="539ef-479">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>
    
- <span data-ttu-id="539ef-p162">您可以在电子邮件客户端中创建邮箱规则, 将邮件移动到 "收件箱"。您还可以请求贵组织的管理员设置允许规则或重写, 如管理发送未经身份验证的电子邮件的合法发件人一节中所述。</span><span class="sxs-lookup"><span data-stu-id="539ef-p162">You can create mailbox rules in your email client to move messages to the Inbox. You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>
    
- <span data-ttu-id="539ef-482">您可以使用 Office 365 创建支持票证, 以创建用于将其视为合法邮件列表的覆盖</span><span class="sxs-lookup"><span data-stu-id="539ef-482">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>
    
### <a name="other-scenarios"></a><span data-ttu-id="539ef-483">其他方案</span><span class="sxs-lookup"><span data-stu-id="539ef-483">Other scenarios</span></span>

1. <span data-ttu-id="539ef-p163">如果上述两种方案都不适合您的情况, 请将邮件报告为误报返回给 Microsoft。有关详细信息, 请参阅本文后面的[如何向 Microsoft 报告垃圾邮件或非垃圾邮件消息](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)一节。</span><span class="sxs-lookup"><span data-stu-id="539ef-p163">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft. For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 
    
2. <span data-ttu-id="539ef-p164">你也可以联系你的电子邮件管理员, 将其作为 Microsoft 的支持票证提出。Microsoft 工程团队将调查邮件被标记为欺骗的原因。</span><span class="sxs-lookup"><span data-stu-id="539ef-p164">You may also contact your email administrator who can raise it as a support ticket with Microsoft. The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>
    
3. <span data-ttu-id="539ef-p165">此外, 如果您知道发件人是谁, 并且确信他们不是恶意欺骗的, 则可以回复给发件人, 以表明他们正在从不进行身份验证的邮件服务器发送邮件。这有时会导致原始发件人联系其 IT 管理员, 以设置所需的电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="539ef-p165">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate. This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="539ef-p166">当发件人回复到应设置电子邮件身份验证记录的域所有者时, 它会 spurs 他们采取措施。虽然 Microsoft 也能与域所有者合作以发布所需的记录, 但在各个用户请求的情况下, 它更有帮助。</span><span class="sxs-lookup"><span data-stu-id="539ef-p166">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action. While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>
    
4. <span data-ttu-id="539ef-p167">(可选) 将发件人添加到安全发件人列表。但是, 请注意, 如果 phisher 假冒该帐户, 则会将其传递到您的邮箱。因此, 应谨慎使用此选项。</span><span class="sxs-lookup"><span data-stu-id="539ef-p167">Optionally, add the sender to your Safe Senders list. However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox. Therefore, this option should be used sparingly.</span></span>
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="539ef-495">发件人到 Microsoft 应如何为反欺骗保护做准备</span><span class="sxs-lookup"><span data-stu-id="539ef-495">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="539ef-496">如果你是当前向 Microsoft 发送邮件的管理员 (Office 365 或 Outlook.com, 则应确保你的电子邮件进行了正确的身份验证, 否则可能会将其标记为垃圾邮件或网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="539ef-496">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span> 
  
### <a name="customers-of-office-365"></a><span data-ttu-id="539ef-497">Office 365 的客户</span><span class="sxs-lookup"><span data-stu-id="539ef-497">Customers of Office 365</span></span>

<span data-ttu-id="539ef-498">如果你是 office 365 客户, 并且使用 office 365 发送出站电子邮件:</span><span class="sxs-lookup"><span data-stu-id="539ef-498">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="539ef-499">对于您的域, 请[在 Office 365 中设置 SPF 以帮助防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span><span class="sxs-lookup"><span data-stu-id="539ef-499">For your domains, [Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)</span></span>
    
- <span data-ttu-id="539ef-500">对于主域, 请[使用 DKIM 验证从 Office 365 中的自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span><span class="sxs-lookup"><span data-stu-id="539ef-500">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)</span></span>
    
- <span data-ttu-id="539ef-501">考虑为您的域[设置 DMARC 记录](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email), 以确定您的合法发件人。</span><span class="sxs-lookup"><span data-stu-id="539ef-501">[Consider setting up DMARC records](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) for your domain to determine who are your legitimate senders</span></span> 
    
<span data-ttu-id="539ef-p168">Microsoft 不提供每个 SPF、DKIM 和 DMARC 的详细实施指南。但是, 联机发布了大量信息。还有第三方公司专门帮助您的组织设置电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="539ef-p168">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC. However, there is a lot of information published online. There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="539ef-505">非 Office 365 客户的域的管理员</span><span class="sxs-lookup"><span data-stu-id="539ef-505">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="539ef-506">如果你是域管理员, 但不是 Office 365 客户:</span><span class="sxs-lookup"><span data-stu-id="539ef-506">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="539ef-p169">应设置 SPF 以发布域的发送 IP 地址, 还应设置 DKIM (如果可用) 以对邮件进行数字签名。您还可以考虑设置 DMARC 记录。</span><span class="sxs-lookup"><span data-stu-id="539ef-p169">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages. You may also consider setting up DMARC records.</span></span>
    
- <span data-ttu-id="539ef-509">如果你有代表你传输电子邮件的批量发件人, 则应使用它们以一种方式发送电子邮件, 以便发件人: address (如果属于你) 中的发送域与传递 SPF 或 DMARC 的域相一致。</span><span class="sxs-lookup"><span data-stu-id="539ef-509">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>
    
- <span data-ttu-id="539ef-510">如果您有本地邮件服务器, 或从软件即服务提供商或从云托管服务 (如 Microsoft Azure、GoDaddy、Rackspace、Amazon Web 服务或类似的云托管服务) 发送, 则应确保它们已添加到您的 SPF 记录中。</span><span class="sxs-lookup"><span data-stu-id="539ef-510">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>
    
- <span data-ttu-id="539ef-p170">如果您是由 isp 托管的小型域, 则应根据 isp 提供给您的说明设置 SPF 记录。大多数 isp 提供这些类型的说明, 可在公司的支持页面中找到。</span><span class="sxs-lookup"><span data-stu-id="539ef-p170">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP. Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>
    
- <span data-ttu-id="539ef-p171">即使您在之前没有发布电子邮件身份验证记录, 并且它正常工作, 您仍必须发布电子邮件身份验证记录以发送给 Microsoft。通过执行此操作, 你可以帮助抵御网络钓鱼, 并减少你或你发送到的组织将获得 phished 的可能性。</span><span class="sxs-lookup"><span data-stu-id="539ef-p171">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft. By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="539ef-515">如果你不知道谁将电子邮件作为你的域发送, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="539ef-515">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="539ef-p172">许多域不会发布 SPF 记录, 因为它们不知道其所有发件人是谁。这没关系, 您无需知道所有这些都是谁。相反, 应首先发布您知道的一个 SPF 记录 (尤其是公司流量所在的位置), 并发布一个中性的 spf 策略？所有:</span><span class="sxs-lookup"><span data-stu-id="539ef-p172">Many domains do not publish SPF records because they do not know who all their senders are. That's okay, you do not need to know who all of them are. Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="539ef-519">TXT "v = spf1 中的 example.com 包括 include spf.protection.outlook.com？ all"</span><span class="sxs-lookup"><span data-stu-id="539ef-519">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="539ef-p173">非特定 SPF 策略意味着, 来自企业基础结构的任何电子邮件都将在所有其他电子邮件接收器中传递电子邮件身份验证。来自你不知道的发件人的电子邮件将回退到中立, 这几乎与根本不发布任何 SPF 记录相同。</span><span class="sxs-lookup"><span data-stu-id="539ef-p173">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers. Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="539ef-p174">发送到 Office 365 时, 来自公司流量的电子邮件将被标记为已通过身份验证, 但是来自你不知道的来源的电子邮件可能仍被标记为欺骗 (取决于 Office 365 能否对其进行隐式身份验证)。但是, 这仍是从 Office 365 标记为欺骗的所有电子邮件中的改进。</span><span class="sxs-lookup"><span data-stu-id="539ef-p174">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it). However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="539ef-524">开始使用回退策略为 "全部" 的 SPF 记录后, 可以逐步包含更多的发送基础结构, 然后发布更严格的策略。</span><span class="sxs-lookup"><span data-stu-id="539ef-524">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="539ef-525">如果您是邮寄列表的所有者, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="539ef-525">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="539ef-526">请参阅 "[常见方案 #2-讨论列表](#common-scenario-2---discussion-lists)" 一节。</span><span class="sxs-lookup"><span data-stu-id="539ef-526">See the section [Common scenario #2 - Discussion lists](#common-scenario-2---discussion-lists).</span></span> 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="539ef-527">如果您是基础结构提供商 (ISP)、电子邮件服务提供商 (ESP) 或云托管服务, 该怎么办？</span><span class="sxs-lookup"><span data-stu-id="539ef-527">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="539ef-528">如果你托管域的电子邮件, 并且它发送电子邮件或提供可发送电子邮件的托管基础结构, 则应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="539ef-528">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="539ef-529">确保您的客户具有详细说明在其 SPF 记录中发布的内容的文档</span><span class="sxs-lookup"><span data-stu-id="539ef-529">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>
    
- <span data-ttu-id="539ef-p175">考虑对出站电子邮件签名 DKIM-签名, 即使客户未明确设置 (使用默认域进行签名) 也是如此。您甚至可以使用 DKIM 签名对电子邮件进行双重签名 (如果用户已对其进行了设置, 则使用一次对其进行双重签名) 以及公司的 DKIM 签名的第二次。</span><span class="sxs-lookup"><span data-stu-id="539ef-p175">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain). You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>
    
<span data-ttu-id="539ef-p176">即使您对源自您的平台的电子邮件进行身份验证, 也不能保证 Deliverability, 但至少可确保 microsoft 不会对您的电子邮件进行垃圾邮件, 因为它未经过身份验证。有关 Outlook.com 如何筛选电子邮件的更多详细信息, 请参阅[Outlook.com 邮局主管页](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="539ef-p176">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated. For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="539ef-534">有关服务提供商最佳做法的更多详细信息, 请参阅[M3AAWG Mobile 消息处理最佳实践 for service providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。</span><span class="sxs-lookup"><span data-stu-id="539ef-534">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="539ef-535">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="539ef-535">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="539ef-536">为什么 Microsoft 要进行此更改？</span><span class="sxs-lookup"><span data-stu-id="539ef-536">Why is Microsoft making this change?</span></span>

<span data-ttu-id="539ef-537">由于网络钓鱼攻击的影响, 并且电子邮件身份验证已有超过15年的时间, Microsoft 认为, 继续允许未经身份验证的电子邮件的风险高于丢失合法电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="539ef-537">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="539ef-538">此更改是否会导致合法电子邮件被标记为垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="539ef-538">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="539ef-p177">最初, 会有一些邮件被标记为垃圾邮件。然而, 随着时间的推移, 发件人将会进行调整, 然后 mislabeled 的邮件数量将被视为可忽略的大多数电子邮件路径。</span><span class="sxs-lookup"><span data-stu-id="539ef-p177">At first, there will be some messages that are marked as spam. However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="539ef-p178">Microsoft 本身在将此功能部署到其客户的其余部分之前, 先在几周内采用此功能。在第一次发生中断时, 会逐渐拒绝。</span><span class="sxs-lookup"><span data-stu-id="539ef-p178">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers. While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="539ef-543">Microsoft 是否会将此功能引入 Office 365 的 Outlook.com 和非高级威胁防护客户？</span><span class="sxs-lookup"><span data-stu-id="539ef-543">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="539ef-p179">Microsoft 的反欺骗技术最初部署到其组织中的 office 365 企业版 E5 订阅或购买了 office 365 高级威胁防护 (ATP) 附加的订阅。从10月起, 2018 我们已扩展了对具有 Exchange Online protection (EOP) 的组织的保护。将来, 我们可能会将其发布到 Outlook.com。但是, 如果我们这样做, 可能会有一些未应用的功能, 如报告和自定义替代。</span><span class="sxs-lookup"><span data-stu-id="539ef-p179">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription. As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well. In the future, we may release it for Outlook.com. However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="539ef-548">如何将垃圾邮件或非垃圾邮件报告回 Microsoft？</span><span class="sxs-lookup"><span data-stu-id="539ef-548">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="539ef-549">您可以使用 Outlook 的[报告消息外接程序](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), 如果未安装, 请将垃圾邮件[、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="539ef-549">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="539ef-550">我是一个不知道我的所有发件人是谁的域管理员!</span><span class="sxs-lookup"><span data-stu-id="539ef-550">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="539ef-551">请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="539ef-551">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="539ef-552">如果我对我的组织禁用反欺骗保护 (即使 Office 365 是我的主要筛选器), 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="539ef-552">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="539ef-p180">我们不建议这样做, 因为你将暴露给更多丢失的网络钓鱼和垃圾邮件。并不是所有的网络钓鱼都是哄骗, 并且并非所有欺骗都将丢失。但是, 您的风险将高于启用反欺骗的客户。</span><span class="sxs-lookup"><span data-stu-id="539ef-p180">We do not recommend this because you will be exposed to more missed phishing and spam messages. Not all phishing is spoofing, and not all spoofs will be missed. However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="539ef-556">启用反欺骗保护意味着我将受到保护, 防止所有网络钓鱼？</span><span class="sxs-lookup"><span data-stu-id="539ef-556">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="539ef-p181">遗憾的是, 因为仿冒者将使用其他技术 (如受损帐户) 或设置免费服务帐户进行调整。但是, 反网络钓鱼保护的工作速度更好, 可以检测到这些其他类型的网络钓鱼方法, 因为 Office 365 的保护层设计在一起, 并在彼此之上构建。</span><span class="sxs-lookup"><span data-stu-id="539ef-p181">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services. However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="539ef-559">其他大型电子邮件接收器是否阻止未经身份验证的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="539ef-559">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="539ef-p182">几乎所有大型电子邮件接收器都实现传统的 SPF、DKIM 和 DMARC。有些接收器具有比这些标准更严格的其他检查, 但几乎不像 Office 365 那样阻止未经身份验证的电子邮件, 并将其视为欺骗。但是, 大多数行业越来越严格地了解这种特定类型的电子邮件, 尤其是由于网络钓鱼问题。</span><span class="sxs-lookup"><span data-stu-id="539ef-p182">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC. Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof. However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="539ef-563">如果启用反欺骗, 我是否仍需要为 "SPF Hard Fail" 启用高级垃圾邮件筛选选项？</span><span class="sxs-lookup"><span data-stu-id="539ef-563">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="539ef-p183">不需要, 此选项不再是必需的, 因为反欺骗功能不仅认为 SPF 硬失败, 而且一组更广泛的条件。如果启用了反欺骗并启用了 "SPF 硬故障" 选项, 则可能会获得更多误报。我们建议禁用此功能, 因为它不会为垃圾邮件或网络钓鱼提供几乎额外的捕获, 而是生成大多数误报。</span><span class="sxs-lookup"><span data-stu-id="539ef-p183">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria. If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives. We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="539ef-567">发件人重写方案 (SRS) 是否帮助修复转发的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="539ef-567">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="539ef-p184">SRS 仅部分修复了转发的电子邮件的问题。通过重写 SMTP 邮件, SRS 可以确保转发的邮件在下一个目的地传递 SPF。但是, 由于反欺骗是基于发件人: 地址与邮件发件人或 DKIM 签名域 (或其他信号) 的结合, 因此阻止转发的电子邮件被标记为欺骗的是不够的。</span><span class="sxs-lookup"><span data-stu-id="539ef-p184">SRS only partially fixes the problem of forwarded email. By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination. However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>
  

