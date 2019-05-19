---
title: Office 365 中的反欺骗保护
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: 本文介绍 Office 365 如何缓解使用伪造发件人域（即欺骗性域）的网络钓鱼攻击。 通过分析邮件并阻止无法使用标准电子邮件身份验证方法或其他发件人信誉技术进行身份验证的邮件，它可以实现这一目标。 实施此更改是为了减少 Office 365 中的组织所面临的网络钓鱼攻击的数量。
ms.openlocfilehash: 455ce577e4ffb3dc4d943004dd3c299e7e6f1eae
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155774"
---
# <a name="anti-spoofing-protection-in-office-365"></a><span data-ttu-id="def73-105">Office 365 中的反欺骗保护</span><span class="sxs-lookup"><span data-stu-id="def73-105">Anti-spoofing protection in Office 365</span></span>

<span data-ttu-id="def73-106">本文介绍 Office 365 如何缓解使用伪造发件人域（即欺骗性域）的网络钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="def73-106">This article describes how Office 365 mitigates against phishing attacks that use forged sender domains, that is, domains that are spoofed.</span></span> <span data-ttu-id="def73-107">通过分析邮件并阻止无法使用标准电子邮件身份验证方法或其他发件人信誉技术进行身份验证的邮件，它可以实现这一目标。</span><span class="sxs-lookup"><span data-stu-id="def73-107">It accomplishes this by analyzing the messages and blocking the ones that cannot be authenticated using standard email authentication methods, nor other sender reputation techniques.</span></span> <span data-ttu-id="def73-108">实施此更改是为了减少 Office 365 中的组织所面临的网络钓鱼攻击的数量。</span><span class="sxs-lookup"><span data-stu-id="def73-108">This change was implemented to reduce the number of phishing attacks to which organizations in Office 365 are exposed.</span></span>
  
<span data-ttu-id="def73-109">本文还介绍了为何要进行此更改、客户如何为此更改做好准备、如何查看将受影响的邮件、如何报告邮件、如何减少误报以及 Microsoft 的发件人应如何为此更改做好准备。</span><span class="sxs-lookup"><span data-stu-id="def73-109">This article also describes why this change is being made, how customers can prepare for this change, how to view messages that will be affected, how to report on messages, how to mitigate false positives, as well as how senders to Microsoft should prepare for this change.</span></span>
  
<span data-ttu-id="def73-110">Microsoft 的反欺骗技术最初部署到拥有 Office 365 企业版 E5 订阅或已为其订阅购买了 Office 365 高级威胁防护 (ATP) 加载项的组织。</span><span class="sxs-lookup"><span data-stu-id="def73-110">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="def73-111">截至 2018 年 10 月，我们已将保护范围扩展到拥有 Exchange Online Protection (EOP) 的组织。</span><span class="sxs-lookup"><span data-stu-id="def73-111">As of October, 2018 we extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="def73-112">此外，Outlook.com 用户也可能会受到影响，具体取决于筛选器相互学习的方式。</span><span class="sxs-lookup"><span data-stu-id="def73-112">Additionally, because of the way all of our filters learn from each other, Outlook.com users may also be affected.</span></span>
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a><span data-ttu-id="def73-113">如何在网络钓鱼攻击中使用欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-113">How spoofing is used in phishing attacks</span></span>

<span data-ttu-id="def73-114">在为用户提供保护方面，Microsoft 非常重视网络钓鱼的威胁。</span><span class="sxs-lookup"><span data-stu-id="def73-114">When it comes to protecting its users, Microsoft takes the threat of phishing seriously.</span></span> <span data-ttu-id="def73-115">垃圾邮件制作者和网络钓鱼者通常使用的技术之一就是欺骗，即伪造发件人，并且邮件似乎来自实际来源以外的某人或某个位置。</span><span class="sxs-lookup"><span data-stu-id="def73-115">One of the techniques that spammers and phishers commonly use is spoofing, which is when the sender is forged, and a message appears to originate from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="def73-116">此技术通常在专门获取用户凭据的网络钓鱼活动中使用。</span><span class="sxs-lookup"><span data-stu-id="def73-116">This technique is often used in phishing campaigns designed to obtain user credentials.</span></span> <span data-ttu-id="def73-117">Microsoft 反欺骗技术专用于检查在 Outlook 等电子邮件客户端中显示的伪造的“发件人: 标头”。</span><span class="sxs-lookup"><span data-stu-id="def73-117">Microsoft's Anti-spoof technology specifically examines forgery of the 'From: header' which is the one that shows up in an email client like Outlook.</span></span> <span data-ttu-id="def73-118">当 Microsoft 高度确信“发件人: 标头”存在欺骗时，它会将该邮件标识为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-118">When Microsoft has high confidence that the From: header is spoofed, it identifies the message as a spoof.</span></span>
  
<span data-ttu-id="def73-119">欺骗邮件会对现实生活中的用户造成两个负面影响：</span><span class="sxs-lookup"><span data-stu-id="def73-119">Spoofing messages have two negative implications for real life users:</span></span>
  
### <a name="1-spoofed-messages-deceive-users"></a><span data-ttu-id="def73-120">1. 欺骗性邮件会误导用户</span><span class="sxs-lookup"><span data-stu-id="def73-120">1. Spoofed messages deceive users</span></span>
  
<span data-ttu-id="def73-121">首先，欺骗性邮件可能会欺骗用户点击链接并放弃使用其凭据、下载恶意软件或回复具有敏感内容的邮件（后者称为商务电子邮件入侵）。</span><span class="sxs-lookup"><span data-stu-id="def73-121">First, a spoofed message may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content (the latter of which is known as Business Email Compromise).</span></span> <span data-ttu-id="def73-122">例如，以下是一封具有伪造发件人 msoutlook94@service.outlook.com 的网络钓鱼邮件：</span><span class="sxs-lookup"><span data-stu-id="def73-122">For example, the following is a phishing message with a spoofed sender of msoutlook94@service.outlook.com:</span></span>
  
![冒充 service.outlook.com 的网络钓鱼邮件](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
<span data-ttu-id="def73-124">上述邮件实际上并非来自 service.outlook.com，而是被网络钓鱼者伪造成这样。</span><span class="sxs-lookup"><span data-stu-id="def73-124">The above did not actually come from service.outlook.com, but instead was spoofed by the phisher to make it look like it did.</span></span> <span data-ttu-id="def73-125">它试图欺骗用户点击邮件中的链接。</span><span class="sxs-lookup"><span data-stu-id="def73-125">It is attempting to trick a user into clicking the link within the message.</span></span>
  
<span data-ttu-id="def73-126">下一个示例是欺骗性的 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="def73-126">The next example is spoofing contoso.com:</span></span>
  
![网络钓鱼邮件 - 商务电子邮件入侵](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
<span data-ttu-id="def73-128">该邮件看似合法，但实际上是一封欺骗性邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-128">The message looks legitimate, but in fact is a spoof.</span></span> <span data-ttu-id="def73-129">此网络钓鱼邮件是一种商务电子邮件入侵，它是网络钓鱼的子类别。</span><span class="sxs-lookup"><span data-stu-id="def73-129">This phishing message is a type of Business Email Compromise which is a subcategory of phishing.</span></span>

### <a name="2-users-confuse-real-messages-for-fake-ones"></a><span data-ttu-id="def73-130">2. 用户将真实邮件与虚假邮件弄混淆</span><span class="sxs-lookup"><span data-stu-id="def73-130">2. Users confuse real messages for fake ones</span></span>
  
<span data-ttu-id="def73-131">其次，欺骗性邮件为了解网络钓鱼邮件的用户带来了不确定性，使其无法区分真实邮件和欺骗性邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-131">Second, spoofed messages create uncertainty for users who know about phishing messages but cannot tell the difference between a real message and spoofed one.</span></span> <span data-ttu-id="def73-132">例如，以下是从 Microsoft 安全帐户电子邮件地址重置实际密码的示例：</span><span class="sxs-lookup"><span data-stu-id="def73-132">For example, the following is an example of an actual password reset from the Microsoft Security account email address:</span></span>
  
![Microsoft 合法密码重置](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
<span data-ttu-id="def73-134">上述邮件确实来自 Microsoft，但与此同时，用户习惯于获取可能诱使其点击链接并放弃使用其凭据、下载恶意软件或回复包含敏感内容的邮件的网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-134">The above message did come from Microsoft, but at the same time, users are used to getting phishing messages that may trick a user into clicking a link and giving up their credentials, downloading malware, or replying to a message with sensitive content.</span></span> <span data-ttu-id="def73-135">由于很难区分真实密码重置和虚假密码重置，因此许多用户会忽略这些邮件，将其报告为垃圾邮件，或者不必要地将该邮件作为遗漏的网络钓鱼欺骗邮件报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="def73-135">Because it is difficult to tell the difference between a real password reset and a fake one, many users ignore these messages, report them as spam, or unnecessarily report the messages back to Microsoft as missed phishing scams.</span></span>

<span data-ttu-id="def73-136">为了阻止欺骗，电子邮件筛选行业开发了 [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、[DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email) 和 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) 等电子邮件身份验证协议。</span><span class="sxs-lookup"><span data-stu-id="def73-136">To stop spoofing, the email filtering industry has developed email authentication protocols such as [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), and [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email).</span></span> <span data-ttu-id="def73-137">DMARC 可防止欺骗活动检查邮件的发件人 - 用户在其电子邮件客户端中看到的发件人（在上面的示例中，它是 service.outlook.com、outlook.com 和 accountprotection.microsoft.com）- 使用已通过 SPF 或 DKIM 验证的域。</span><span class="sxs-lookup"><span data-stu-id="def73-137">DMARC prevents spoofing examining a message's sender - the one that the user sees in their email client (in the examples above, this is service.outlook.com, outlook.com, and accountprotection.microsoft.com) - with the domain that passed SPF or DKIM.</span></span> <span data-ttu-id="def73-138">也就是说，用户看到的域已经过身份验证，因此不会受到欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-138">That is, the domain that the user sees has been authenticated and is therefore not spoofed.</span></span> <span data-ttu-id="def73-139">有关更完整的讨论，请参阅本文后面的“*了解电子邮件身份验证为何并非总能阻止欺骗*”。</span><span class="sxs-lookup"><span data-stu-id="def73-139">For a more complete discussion, see the section "*Understanding why email authentication is not always enough to stop spoofing"*  later on in this article.</span></span>
  
<span data-ttu-id="def73-140">但问题在于电子邮件身份验证记录是可选的，而不是必需的。</span><span class="sxs-lookup"><span data-stu-id="def73-140">However, the problem is that email authentication records are optional, not required.</span></span> <span data-ttu-id="def73-141">因此，具有强大身份验证策略（如 microsoft.com 和 skype.com）的域可以防止欺骗，而发布较弱身份验证策略或根本没有策略的域则是欺骗活动攻击的目标。截至 2018 年 3 月，在财富 500 强企业中，只有 9% 的域发布了强大的电子邮件身份验证策略。</span><span class="sxs-lookup"><span data-stu-id="def73-141">Therefore, while domains with strong authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker authentication policies, or no policy at all, are targets for being spoofed.As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="def73-142">剩余 91％ 的域可能被网络钓鱼者冒充，除非电子邮件筛选器使用其他策略检测到这些欺骗活动，否则可能会将其传递给最终用户并误导他们：</span><span class="sxs-lookup"><span data-stu-id="def73-142">The remaining 91% may be spoofed by a phisher, and unless the email filter detects it using another policy, may be delivered to an end user and deceive them:</span></span>
  
![财富 500 强企业的 DMARC 策略](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
<span data-ttu-id="def73-144">未跻身财富 500 强的已发布强大电子邮件身份验证策略的中小型公司所占比例较小，而对于北美和西欧以外的域，发布强大策略的比例仍较小。</span><span class="sxs-lookup"><span data-stu-id="def73-144">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for domains that are outside of North America and western Europe.</span></span>
  
<span data-ttu-id="def73-145">这是一个大问题，因为企业可能不知道电子邮件身份验证的工作方式，但网络钓鱼者确实了解这一点并且会加以利用。</span><span class="sxs-lookup"><span data-stu-id="def73-145">This is a big problem because while enterprises may not be aware of how email authentication works, phishers do understand and take advantage of the lack of it.</span></span>
  
<span data-ttu-id="def73-146">有关设置 SPF、DKIM 和 DMARC 的信息，请参阅本文档后面的“*Office 365 客户*”部分。</span><span class="sxs-lookup"><span data-stu-id="def73-146">For information on setting up SPF, DKIM, and DMARC, see the section "*Customers of Office 365"*  later on in this document.</span></span> 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a><span data-ttu-id="def73-147">使用隐式电子邮件身份验证阻止欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-147">Stopping spoofing with implicit email authentication</span></span>

<span data-ttu-id="def73-148">由于网络钓鱼和鱼叉式网络钓鱼是一个大问题，并且强大的电子邮件身份验证策略的采用有限，Microsoft 将继续投资打造旨在为客户提供保护的功能。</span><span class="sxs-lookup"><span data-stu-id="def73-148">Because phishing and spear phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft continues to invest in capabilities to protect its customers.</span></span> <span data-ttu-id="def73-149">为此，Microsoft 正在推进*隐式电子邮件身份验证* - 如果域未进行身份验证，Microsoft 会将其视为已发布电子邮件身份验证记录，并在未通过时对其进行相应的处理。</span><span class="sxs-lookup"><span data-stu-id="def73-149">Therefore, Microsoft is moving ahead with  *implicit email authentication* - if a domain doesn't authenticate, Microsoft will treat it as if it had published email authentication records and treat it accordingly if it doesn't pass.</span></span> 
  
<span data-ttu-id="def73-150">为了实现这一目标，Microsoft 为常规电子邮件身份验证构建了大量扩展，包括发件人信誉、发件人/收件人历史记录、行为分析和其他高级技术。</span><span class="sxs-lookup"><span data-stu-id="def73-150">To accomplish this, Microsoft has built numerous extensions to regular email authentication including sender reputation, sender/recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="def73-151">除非包含其他表明其为合法邮件的信号，否则从未发布电子邮件身份验证的域发送的邮件将被标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-151">A message sent from a domain that doesn't publish email authentication will be marked as spoof unless it contains other signals to indicate that it is legitimate.</span></span>
  
<span data-ttu-id="def73-152">通过这样做，最终用户可以确信发送给他们的电子邮件并非欺骗邮件，发件人可以确信没有人冒充他们的域，并且 Office 365 的客户可以提供更好的保护，例如模拟保护。</span><span class="sxs-lookup"><span data-stu-id="def73-152">By doing this, end users can have confidence that an email sent to them has not been spoofed, senders can be confident that nobody is impersonating their domain, and customers of Office 365 can offer even better protection such as Impersonation protection.</span></span>
  
<span data-ttu-id="def73-153">若要查看 Microsoft 的一般声明，请参阅[网络钓鱼第 2 部分 - Office 365 中的增强反欺骗功能](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。</span><span class="sxs-lookup"><span data-stu-id="def73-153">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a><span data-ttu-id="def73-154">识别已分类为欺骗的邮件</span><span class="sxs-lookup"><span data-stu-id="def73-154">Identifying that a message is classified as spoofed</span></span>

### <a name="composite-authentication"></a><span data-ttu-id="def73-155">复合身份验证</span><span class="sxs-lookup"><span data-stu-id="def73-155">Composite authentication</span></span>

<span data-ttu-id="def73-156">虽然 SPF、DKIM 和 DMARC 本身都很有用，但如果邮件没有明确的身份验证记录，它们就无法传递充足的身份验证状态。</span><span class="sxs-lookup"><span data-stu-id="def73-156">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="def73-157">为此，Microsoft 开发了一种算法，可将多个信号组合成一个称为复合身份验证（或简称为“compauth”）的单一值。</span><span class="sxs-lookup"><span data-stu-id="def73-157">Therefore, Microsoft has developed an algorithm that combines multiple signals into a single value called Composite Authentication, or compauth for short.</span></span> <span data-ttu-id="def73-158">Office 365 中的客户可以在邮件头的“*Authentication-Results*”标头中标记 compauth 值。</span><span class="sxs-lookup"><span data-stu-id="def73-158">Customers in Office 365 have compauth values stamped into the *Authentication-Results* header in the message headers.</span></span> 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|<span data-ttu-id="def73-159">**CompAuth 结果**</span><span class="sxs-lookup"><span data-stu-id="def73-159">**CompAuth result**</span></span>|<span data-ttu-id="def73-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="def73-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="def73-161">失败</span><span class="sxs-lookup"><span data-stu-id="def73-161">fail</span></span>|<span data-ttu-id="def73-162">邮件未通过显式身份验证（发送域已在 DNS 中显式发布记录）或隐式身份验证（发送域未在 DNS 中发布记录，而 Office 365 就像已发布记录一样插入结果）。</span><span class="sxs-lookup"><span data-stu-id="def73-162">Message failed explicit authentication (sending domain published records explicitly in DNS) or implicit authentication (sending domain did not publish records in DNS, so Office 365 interpolated the result as if it had published records).</span></span>|
|<span data-ttu-id="def73-163">通过</span><span class="sxs-lookup"><span data-stu-id="def73-163">pass</span></span>|<span data-ttu-id="def73-164">邮件已通过显式身份验证（邮件通过 DMARC 或[最佳猜测通过 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)）或具有高可信度的隐式身份验证（发送域未发布电子邮件身份验证记录，但 Office 365 具有强大的后端信号来指示邮件很有可能是合法邮件）。</span><span class="sxs-lookup"><span data-stu-id="def73-164">Message passed explicit authentication (message passed DMARC, or [Best Guess Passed DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) or implicit authentication with high confidence (sending domain does not publish email authentication records, but Office 365 has strong backend signals to indicate the message is likely legitimate).</span></span>|
|<span data-ttu-id="def73-165">softpass</span><span class="sxs-lookup"><span data-stu-id="def73-165">softpass</span></span>|<span data-ttu-id="def73-166">消息以低到中等可信度通过隐式身份验证（发送域未发布电子邮件身份验证，但 Office 365 具有后端信号来指示邮件为合法邮件，但信号强度较弱）。</span><span class="sxs-lookup"><span data-stu-id="def73-166">Message passed implicit authentication with low-to-medium confidence (sending domain does not publish email authentication, but Office 365 has backend signals to indicate the message is legitimate but the strength of the signal is weaker).</span></span>|
|<span data-ttu-id="def73-167">无</span><span class="sxs-lookup"><span data-stu-id="def73-167">none</span></span>|<span data-ttu-id="def73-168">邮件未进行身份验证（或者它已进行身份验证但不一致），但由于发件人信誉或其他因素而未应用复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="def73-168">Message did not authenticate (or it did authenticate but did not align), but composite authentication not applied due to sender reputation or other factors.</span></span>|
   
|||
|:-----|:-----|
|<span data-ttu-id="def73-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="def73-169">**Reason**</span></span>|<span data-ttu-id="def73-170">**说明**</span><span class="sxs-lookup"><span data-stu-id="def73-170">**Description**</span></span>|
|<span data-ttu-id="def73-171">0xx</span><span class="sxs-lookup"><span data-stu-id="def73-171">0xx</span></span>|<span data-ttu-id="def73-172">邮件未通过复合身份验证。</span><span class="sxs-lookup"><span data-stu-id="def73-172">Message failed composite authentication.</span></span><br/><span data-ttu-id="def73-173">**000** 表示邮件未通过 DMARC 验证，并采取了拒绝或隔离操作。</span><span class="sxs-lookup"><span data-stu-id="def73-173">**000** means the message failed DMARC with an action of reject or quarantine.</span></span>  <br/><span data-ttu-id="def73-174">**001** 表示邮件未通过隐式电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="def73-174">**001** means the message failed implicit email authentication.</span></span> <span data-ttu-id="def73-175">这意味着发送域未发布电子邮件身份验证记录，或者如果已发布，则它们具有较弱的失败策略（SPF 软失败或中性，DMARC 策略为 p=无）。</span><span class="sxs-lookup"><span data-stu-id="def73-175">This means that the sending domain did not have email authentication records published, or if they did, they had a weaker failure policy (SPF soft fail or neutral, DMARC policy of p=none).</span></span>  <br/><span data-ttu-id="def73-176">**002** 表示组织为发件人/域对设置了明确禁止发送欺骗性电子邮件的策略，此设置由管理员手动设置。</span><span class="sxs-lookup"><span data-stu-id="def73-176">**002** means the organization has a policy for the sender/domain pair that is explicitly prohibited from sending spoofed email, this setting is manually set by an administrator.</span></span>  <br/><span data-ttu-id="def73-177">**010** 表示邮件未通过 DMARC 验证，并采取了拒绝或隔离操作，而且发送域是组织的接受域之一（这是自我欺骗或组织内欺骗的一部分）之一。</span><span class="sxs-lookup"><span data-stu-id="def73-177">**010** means the message failed DMARC with an action of reject or quarantine, and the sending domain is one of your organization's accepted-domains (this is part of self-to-self, or intra-org, spoofing).</span></span>  <br/><span data-ttu-id="def73-178">**011** 表示邮件未通过隐式电子邮件身份验证，并采取了拒绝或隔离操作，而且发送域是组织的接受域之一（它是自我欺骗或组织内欺骗的一部分）之一。</span><span class="sxs-lookup"><span data-stu-id="def73-178">**011** means the message failed implicit email authentication, and the sending domain is one of your organization's accepted domains (this is part of self-to-self, or intra-org, spoofing).</span></span>|
|<span data-ttu-id="def73-179">所有其他代码（1xx、2xx、3xx、4xx、5xx）</span><span class="sxs-lookup"><span data-stu-id="def73-179">All other codes (1xx, 2xx, 3xx, 4xx, 5xx)</span></span>|<span data-ttu-id="def73-180">对应于各种内部代码，指明邮件为何已通过隐式身份验证或者未进行身份验证且未执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="def73-180">Corresponds to various internal codes for why a message passed implicit authentication, or had no authentication but no action was applied.</span></span>|
   
<span data-ttu-id="def73-181">通过查看邮件的标头，管理员甚至是最终用户可以确定 Office 365 如何得出发件人可能带欺骗性质的结论。</span><span class="sxs-lookup"><span data-stu-id="def73-181">By looking at the headers of a message, an administrator or even an end user can determine how Office 365 arrives at the conclusion that the sender may be spoofed.</span></span>
  
### <a name="differentiating-between-different-types-of-spoofing"></a><span data-ttu-id="def73-182">区分不同类型的欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-182">Differentiating between different types of spoofing</span></span>

<span data-ttu-id="def73-183">Microsoft 区分两种不同类型的欺骗邮件：</span><span class="sxs-lookup"><span data-stu-id="def73-183">Microsoft differentiates between two different types of spoofing messages:</span></span>
  
 <span data-ttu-id="def73-184">**组织内欺骗**</span><span class="sxs-lookup"><span data-stu-id="def73-184">**Intra-org spoofing**</span></span>
  
<span data-ttu-id="def73-185">也称为自我欺骗，如果“发件人: 地址”中的域与收件人域相同或相一致（当收件人域是组织的[接受域](https://technet.microsoft.com/zh-CN/library/jj945194%28v=exchg.150%29.aspx)之一时），就会发生这种情况。或者，当“发件人: 地址”中的域是同一组织的一部分时，也会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="def73-185">Also known as self-to-self spoofing, this occurs when the domain in the From: address is the same as, or aligns with, the recipient domain (when recipient domain is one of your organization's [Accepted Domains](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)); or, when the domain in the From: address is part of the same organization.</span></span>
  
<span data-ttu-id="def73-186">例如，以下邮件具有来自同一域 (contoso.com) 的发件人和收件人。</span><span class="sxs-lookup"><span data-stu-id="def73-186">For example, the following has sender and recipient from the same domain (contoso.com).</span></span> <span data-ttu-id="def73-187">在电子邮件地址中插入空格以防止垃圾邮件程序在此页面上收集信息：</span><span class="sxs-lookup"><span data-stu-id="def73-187">Spaces are inserted into the email address to prevent spambot harvesting on this page):</span></span>
  
<span data-ttu-id="def73-188">发件人：sender @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="def73-188">From: sender @ contoso.com</span></span>
  
<span data-ttu-id="def73-189">收件人：recipient @ contoso.com</span><span class="sxs-lookup"><span data-stu-id="def73-189">To: recipient @ contoso.com</span></span>
  
<span data-ttu-id="def73-190">以下邮件具有与组织域 (fabrikam.com) 相一致的发件人和收件人域：</span><span class="sxs-lookup"><span data-stu-id="def73-190">The following has the sender and recipient domains aligning with the organizational domain (fabrikam.com):</span></span>
  
<span data-ttu-id="def73-191">发件人：sender @ foo.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="def73-191">From: sender @ foo.fabrikam.com</span></span>
  
<span data-ttu-id="def73-192">收件人：recipient @ bar.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="def73-192">To: recipient @ bar.fabrikam.com</span></span>
  
<span data-ttu-id="def73-193">以下发件人和收件人域不同（microsoft.com 和bing.com），但它们属于同一组织（即两者都是组织的接受域的一部分）：</span><span class="sxs-lookup"><span data-stu-id="def73-193">The following sender and recipient domains are different (microsoft.com and bing.com), but they belong to the same organization (that is, both are part of the organization's Accepted Domains):</span></span>
  
<span data-ttu-id="def73-194">发件人：sender @ microsoft.com</span><span class="sxs-lookup"><span data-stu-id="def73-194">From: sender @ microsoft.com</span></span>
  
<span data-ttu-id="def73-195">收件人：recipient @ bing.com</span><span class="sxs-lookup"><span data-stu-id="def73-195">To: recipient @ bing.com</span></span>
  
<span data-ttu-id="def73-196">未通过组织内欺骗验证的邮件在标头中包含以下值：</span><span class="sxs-lookup"><span data-stu-id="def73-196">Messages that fail intra-org spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="def73-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span><span class="sxs-lookup"><span data-stu-id="def73-197">X-Forefront-Antispam-Report: ...CAT:SPM/HSPM/PHSH;...SFTY:9.11</span></span>
  
<span data-ttu-id="def73-198">其中 CAT 表示邮件的类别，通常标记为 SPM（垃圾邮件），但有时可能是 HSPM（高可信度垃圾邮件）或 PHISH（网络钓鱼），具体取决于邮件中出现的其他模式类型。</span><span class="sxs-lookup"><span data-stu-id="def73-198">The CAT is the category of the message, and it is normally stamped as SPM (spam), but occasionally may be HSPM (high confidence spam) or PHISH (phishing) depending upon what other types of patterns occur in the message.</span></span>
  
<span data-ttu-id="def73-199">SFTY 表示邮件的安全级别，第一个数字 (9) 表示该邮件是网络钓鱼邮件，点 (11) 之后的第二组数字表示它是组织内欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-199">The SFTY is the safety level of the message, the first digit (9) means the message is phishing, and second set of digits after the dot (11) means it is intra-org spoofing.</span></span>
  
<span data-ttu-id="def73-200">组织内欺骗的复合身份验证没有特定的原因代码，将在 2018 年晚些时候进行标记（时间表尚未确定）。</span><span class="sxs-lookup"><span data-stu-id="def73-200">There is no specific reason code for Composite Authentication for intra-org spoofing, that will be stamped later in 2018 (timeline not yet defined).</span></span>
  
 <span data-ttu-id="def73-201">**跨域欺骗**</span><span class="sxs-lookup"><span data-stu-id="def73-201">**Cross-domain spoofing**</span></span>
  
<span data-ttu-id="def73-202">当“发件人: 地址”中的发送域是接收组织的外部域时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="def73-202">This occurs when the sending domain in the From: address is an external domain to the receiving organization.</span></span> <span data-ttu-id="def73-203">由于跨域欺骗而导致未通过复合身份验证的邮件在标头中包含以下值：</span><span class="sxs-lookup"><span data-stu-id="def73-203">Messages that fail Composite Authentication due to cross-domain spoofing contain the following values in the headers:</span></span>
  
<span data-ttu-id="def73-204">Authentication-Results: …</span><span class="sxs-lookup"><span data-stu-id="def73-204">Authentication-Results: …</span></span> <span data-ttu-id="def73-205">compauth=fail reason=000/001</span><span class="sxs-lookup"><span data-stu-id="def73-205">compauth=fail reason=000/001</span></span>
  
<span data-ttu-id="def73-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span><span class="sxs-lookup"><span data-stu-id="def73-206">X-Forefront-Antispam-Report: ...CAT:SPOOF;...SFTY:9.22</span></span>
  
<span data-ttu-id="def73-207">在这两种情况下，邮件中都会标记以下红色安全提示，或者根据收件人邮箱的语言提供自定义等效提示：</span><span class="sxs-lookup"><span data-stu-id="def73-207">In both cases, the following red safety tip is stamped in the message, or an equivalent that is customized to the recipient mailbox's language:</span></span>
  
![红色安全提示 - 欺诈检测](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
<span data-ttu-id="def73-209">只有通过查看“发件人: 地址”并了解收件人电子邮件的内容，或者通过检查电子邮件标头，你才能区分组织内欺骗和跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-209">It's only by looking at the From: address and knowing what your recipient email is, or by inspecting the email headers, that you can differentiate between intra-org and cross-domain spoofing.</span></span>
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a><span data-ttu-id="def73-210">Office 365 的客户如何为新的反欺骗保护做好准备</span><span class="sxs-lookup"><span data-stu-id="def73-210">How customers of Office 365 can prepare themselves for the new anti-spoofing protection</span></span>

### <a name="information-for-administrators"></a><span data-ttu-id="def73-211">为管理员提供的信息</span><span class="sxs-lookup"><span data-stu-id="def73-211">Information for administrators</span></span>

<span data-ttu-id="def73-212">作为 Office 365 中组织的管理员，你应该了解一些重要信息。</span><span class="sxs-lookup"><span data-stu-id="def73-212">As an administrator of an organization in Office 365, there are several key pieces of information you should be aware of.</span></span>
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="def73-213">了解电子邮件身份验证为何并非总能阻止欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-213">Understanding why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="def73-214">新的反欺骗保护依赖电子邮件身份验证（SPF、DKIM 和 DMARC），而不是将邮件标记为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-214">The new anti-spoofing protection relies on email authentication (SPF, DKIM, and DMARC) to not mark a message as spoofing.</span></span> <span data-ttu-id="def73-215">一个常见示例是发送域从未发布过 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="def73-215">A common example is when a sending domain has never published SPF records.</span></span> <span data-ttu-id="def73-216">如果没有 SPF 记录或者设置不正确，则发送的邮件将被标记为欺骗邮件，除非 Microsoft 通过后端智能指明该邮件是合法邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-216">If there are no SPF records or they are incorrectly set up, a sent message will be marked as spoofed unless Microsoft has back-end intelligence that says the message is legitimate.</span></span>
  
<span data-ttu-id="def73-217">例如，在部署反欺骗之前，邮件可能看起来如下：没有 SPF 记录，没有 DKIM 记录，也没有 DMARC 记录：</span><span class="sxs-lookup"><span data-stu-id="def73-217">For example, prior to anti-spoofing being deployed, a message may have looked like the following with no SPF record, no DKIM record, and no DMARC record:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
<span data-ttu-id="def73-218">在部署反欺骗之后，如果你拥有 Office 365 企业版 E5、EOP 或 ATP，则会标记 compauth 值：</span><span class="sxs-lookup"><span data-stu-id="def73-218">After anti-spoofing, if you have Office 365 Enterprise E5, EOP, or ATP, the compauth value is stamped:</span></span>
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

<span data-ttu-id="def73-219">如果 example.com 通过设置 SPF 记录而不是 DKIM 记录来修复此问题，则可通过复合身份验证，因为通过 SPF 验证的域与“发件人: 地址”中的域相一致：</span><span class="sxs-lookup"><span data-stu-id="def73-219">If example.com fixed this by setting up an SPF record but not a DKIM record, this would pass composite authentication because the domain that passed SPF aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="def73-220">或者，如果已设置 DKIM 记录而不是 SPF 记录，则也可通过复合身份验证，因为 DKIM 签名中的域与“发件人: 地址”中的域相一致：</span><span class="sxs-lookup"><span data-stu-id="def73-220">Or, if they set up a DKIM record but not an SPF record, this would also pass composite authentication because the domain in the DKIM-Signature that passed aligned with the domain in the From: address:</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="def73-221">但是，网络钓鱼者还可以设置 SPF 和 DKIM，并使用自己的域对邮件进行签名，而在“发件人: 地址”中指定其他域。</span><span class="sxs-lookup"><span data-stu-id="def73-221">However, a phisher may also set up SPF and DKIM and sign the message with their own domain, but specify a different domain in the From: address.</span></span> <span data-ttu-id="def73-222">SPF 和 DKIM 都不要求域与“发件人: 地址”中的域保持一致，因此除非 example.com 发布了 DMARC 记录，否则不会使用 DMARC 将其标记为欺骗邮件：</span><span class="sxs-lookup"><span data-stu-id="def73-222">Neither SPF nor DKIM requires the domain to align with the domain in the From: address, so unless example.com published DMARC records, this would not be marked as a spoof using DMARC:</span></span> 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

<span data-ttu-id="def73-223">在电子邮件客户端（Outlook、Outlook 网页版或任何其他电子邮件客户端）中，仅显示“发件人:”域，而不显示 SPF 或 DKIM 中的域，这可能误导用户认为该邮件来自 example.com，但它实际上来自 maliciousDomain.com。</span><span class="sxs-lookup"><span data-stu-id="def73-223">In the email client (Outlook, Outlook on the web, or any other email client), only the From: domain is displayed, not the domain in the SPF or DKIM, and that can mislead the user into thinking the message came from example.com, but actually came from maliciousDomain.com.</span></span>
  
![已对邮件进行身份验证，但“发件人:”域与通过 SPF 或 DKIM 验证的域不一致。](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
<span data-ttu-id="def73-225">因此，Office 365 要求“发件人: 地址”中的域与 SPF 或 DKIM 签名中的域保持一致，如果不一致，则需要包含一些其他内部信号，以指明该邮件是合法邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-225">For that reason, Office 365 requires that the domain in the From: address aligns with the domain in the SPF or DKIM signature, and if it doesn't, contains some other internal signals that indicates that the message is legitimate.</span></span> <span data-ttu-id="def73-226">否则，该邮件将为 compauth 失败状态。</span><span class="sxs-lookup"><span data-stu-id="def73-226">Otherwise, the message would be a compauth fail.</span></span> 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

<span data-ttu-id="def73-227">因此，Office 365 反欺骗可以抵御未经过身份验证的域，以及已设置身份验证但与“发件人: 地址”中的域（用户看到并认为该域是邮件的发件人）不一致的域。</span><span class="sxs-lookup"><span data-stu-id="def73-227">Thus, Office 365 anti-spoofing protects against domains with no authentication, and against domains who set up authentication but mismatch against the domain in the From: address as that is the one that the user sees and believes is the sender of the message.</span></span> <span data-ttu-id="def73-228">这适用于组织外部的域以及组织内的域。</span><span class="sxs-lookup"><span data-stu-id="def73-228">This is true both of domains external to your organization, as well as domains within your organization.</span></span>
  
<span data-ttu-id="def73-229">因此，如果你收到的邮件未通过复合身份验证并且被标记为欺骗邮件，即使该邮件通过了 SPF 和 DKIM 验证，也是因为通过 SPF 和 DKIM 验证的域与“发件人: 地址”中的域不一致。</span><span class="sxs-lookup"><span data-stu-id="def73-229">Therefore, if you ever receive a message that failed composite authentication and is marked as spoofed, even though the message passed SPF and DKIM, it's because the domain that passed SPF and DKIM are not aligned with the domain in the From: address.</span></span>
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a><span data-ttu-id="def73-230">了解欺骗性电子邮件处理方式的更改</span><span class="sxs-lookup"><span data-stu-id="def73-230">Understanding changes in how spoofed emails are treated</span></span>

<span data-ttu-id="def73-231">目前，对于 Office 365 中的所有组织 - ATP 和非 ATP - 未通过 DMARC 验证（使用拒绝或隔离策略）的邮件被标记为垃圾邮件并且通常采取高可信度垃圾邮件操作，或者有时采取常规垃圾邮件操作（具体取决于其他垃圾邮件规则是否先将其识别为垃圾邮件）。</span><span class="sxs-lookup"><span data-stu-id="def73-231">Currently, for all organizations in Office 365 - ATP and non-ATP - messages that fail DMARC with a policy of reject or quarantine are marked as spam and usually take the high confidence spam action, or sometimes the regular spam action (depending on whether other spam rules first identify it as spam).</span></span> <span data-ttu-id="def73-232">组织内欺骗检测采取常规垃圾邮件操作。</span><span class="sxs-lookup"><span data-stu-id="def73-232">Intra-org spoof detections take the regular spam action.</span></span> <span data-ttu-id="def73-233">不需要启用此行为，也不能禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="def73-233">This behavior does not need to be enabled, nor can it be disabled.</span></span>
  
<span data-ttu-id="def73-234">但是，对于跨域欺骗性邮件，在此更改之前，将对它们进行常规垃圾邮件、网络钓鱼和恶意软件检查，如果筛选器的其他部分将其标识为可疑邮件，则会将它们分别标记为垃圾邮件、网络钓鱼或恶意软件。</span><span class="sxs-lookup"><span data-stu-id="def73-234">However, for cross-domain spoofing messages, before this change they would go through regular spam, phish, and malware checks and if other parts of the filter identified them as suspicious, would mark them as spam, phish, or malware respectively.</span></span> <span data-ttu-id="def73-235">通过新的跨域欺骗保护，默认情况下，任何无法通过身份验证的邮件都将采取“反网络钓鱼”\>“反欺骗策略”中定义的操作。</span><span class="sxs-lookup"><span data-stu-id="def73-235">With the new cross-domain spoofing protection, any message that can't be authenticated will, by default, take the action defined in the Anti-phishing \> Anti-spoofing policy.</span></span> <span data-ttu-id="def73-236">如果未定义任何操作，则系统会将其移到用户垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="def73-236">If one is not defined, it will be moved to a users Junk Email folder.</span></span> <span data-ttu-id="def73-237">在某些情况下，会在更多可疑邮件中添加红色安全提示。</span><span class="sxs-lookup"><span data-stu-id="def73-237">In some cases, more suspicious messages will also have the red safety tip added to the message.</span></span>
  
<span data-ttu-id="def73-238">这可能会导致以前标记为垃圾邮件的某些邮件仍被标记为垃圾邮件，但现在还会有红色安全提示；在其他情况下，之前标记为非垃圾邮件的邮件将开始标记为垃圾邮件 (CAT:SPOOF)，并添加红色安全提示。</span><span class="sxs-lookup"><span data-stu-id="def73-238">This may result in some messages that were previously marked as spam still getting marked as spam but will now also have a red safety tip; in other cases, messages that were previously marked as non-spam will start getting marked as spam (CAT:SPOOF) with a red safety tip added.</span></span> <span data-ttu-id="def73-239">在其他情况下，将所有垃圾邮件和网络钓鱼移到隔离区的客户现在会看到它们已转移到垃圾邮件文件夹（可以更改此行为，请参阅[更改反欺骗设置](#changing-your-anti-spoofing-settings)）。</span><span class="sxs-lookup"><span data-stu-id="def73-239">In still other cases, customers that were moving all spam and phish to the quarantine would now see them going to the Junk Mail Folder (this behavior can be changed, see [Changing your anti-spoofing settings](#changing-your-anti-spoofing-settings)).</span></span>
  
<span data-ttu-id="def73-240">邮件可能具有多种不同的欺骗方式（请参阅[区分不同类型的欺骗](#differentiating-between-different-types-of-spoofing)），但是截至 2018 年 3 月，Office 365 处理这些邮件的方式尚未统一。</span><span class="sxs-lookup"><span data-stu-id="def73-240">There are multiple different ways a message can be spoofed (see  [Differentiating between different types of spoofing](#differentiating-between-different-types-of-spoofing) earlier in this article) but as of March 2018 the way Office 365 treats these messages is not yet unified.</span></span> <span data-ttu-id="def73-241">下表是快速摘要，其中跨域欺骗保护是一种新行为：</span><span class="sxs-lookup"><span data-stu-id="def73-241">The following table is a quick summary, with Cross-domain spoofing protection being new behavior:</span></span> 
  
|<span data-ttu-id="def73-242">**欺骗类型**</span><span class="sxs-lookup"><span data-stu-id="def73-242">**Type of spoof**</span></span>|<span data-ttu-id="def73-243">**类别**</span><span class="sxs-lookup"><span data-stu-id="def73-243">**Category**</span></span>|<span data-ttu-id="def73-244">**是否添加安全提示？**</span><span class="sxs-lookup"><span data-stu-id="def73-244">**Safety tip added?**</span></span>|<span data-ttu-id="def73-245">**适用于**</span><span class="sxs-lookup"><span data-stu-id="def73-245">**Applies to**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="def73-246">DMARC 失败（隔离或拒绝）</span><span class="sxs-lookup"><span data-stu-id="def73-246">DMARC fail (quarantine or reject)</span></span>  <br/> |<span data-ttu-id="def73-247">HSPM（默认），也可能是 SPM 或 PHSH</span><span class="sxs-lookup"><span data-stu-id="def73-247">HSPM (default), may also be SPM or PHSH</span></span>  <br/> |<span data-ttu-id="def73-248">否（尚未添加）</span><span class="sxs-lookup"><span data-stu-id="def73-248">No (not yet)</span></span>  <br/> |<span data-ttu-id="def73-249">所有 Office 365 客户、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="def73-249">All Office 365 customers, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="def73-250">自我欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-250">Self-to-self</span></span>  <br/> |<span data-ttu-id="def73-251">SPM</span><span class="sxs-lookup"><span data-stu-id="def73-251">SPM</span></span>  <br/> |<span data-ttu-id="def73-252">是</span><span class="sxs-lookup"><span data-stu-id="def73-252">Yes</span></span>  <br/> |<span data-ttu-id="def73-253">所有 Office 365 组织、Outlook.com</span><span class="sxs-lookup"><span data-stu-id="def73-253">All Office 365 organizations, Outlook.com</span></span>  <br/> |
|<span data-ttu-id="def73-254">跨域</span><span class="sxs-lookup"><span data-stu-id="def73-254">Cross-domain</span></span>  <br/> |<span data-ttu-id="def73-255">SPOOF</span><span class="sxs-lookup"><span data-stu-id="def73-255">SPOOF</span></span>  <br/> |<span data-ttu-id="def73-256">是</span><span class="sxs-lookup"><span data-stu-id="def73-256">Yes</span></span>  <br/> |<span data-ttu-id="def73-257">Office 365 高级威胁防护和 E5 客户</span><span class="sxs-lookup"><span data-stu-id="def73-257">Office 365 Advanced Threat Protection and E5 customers</span></span>  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a><span data-ttu-id="def73-258">更改反欺骗设置</span><span class="sxs-lookup"><span data-stu-id="def73-258">Changing your anti-spoofing settings</span></span>

<span data-ttu-id="def73-259">若要创建或更新（跨域）反欺骗设置，请导航到安全 &amp;合规中心的“威胁管理”\>“策略”选项卡下的“反网络钓鱼”\>“反欺骗设置”。</span><span class="sxs-lookup"><span data-stu-id="def73-259">To create or update your (cross-domain) anti-spoofing settings, navigate to the Anti-phishing \> Anti-spoofing settings under the Threat Management \> Policy tab in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="def73-260">如果你从未创建任何反网络钓鱼设置，则需要创建一个：</span><span class="sxs-lookup"><span data-stu-id="def73-260">If you have never created any anti-phishing settings, you will need to create one:</span></span>
  
![反网络钓鱼 - 创建新策略](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
<span data-ttu-id="def73-262">如果你已创建一个，则可以选择它以进行修改：</span><span class="sxs-lookup"><span data-stu-id="def73-262">If you've already created one, you can select it to modify it:</span></span>
  
![反网络钓鱼 - 修改现有策略](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
<span data-ttu-id="def73-264">选择你刚刚创建的策略，然后按照[详细了解反欺骗智能保护](learn-about-spoof-intelligence.md)中所述的步骤执行操作。</span><span class="sxs-lookup"><span data-stu-id="def73-264">Select the policy you just created and proceed through the steps as described in [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).</span></span>
  
![启用或禁用反欺骗](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![启用或禁用反欺骗安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
<span data-ttu-id="def73-267">使用 PowerShell 创建新策略：</span><span class="sxs-lookup"><span data-stu-id="def73-267">To create a new policy by using PowerShell:</span></span> 
  
```powershell
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

<span data-ttu-id="def73-268">然后，你可以按照文档[设置反网络钓鱼策略](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)部分中的说明，使用 PowerShell 修改反网络钓鱼策略参数。</span><span class="sxs-lookup"><span data-stu-id="def73-268">You may then modify the anti-phishing policy parameters using PowerShell, following the documentation at [Set-AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps).</span></span> <span data-ttu-id="def73-269">你可以将 $name 指定为参数：</span><span class="sxs-lookup"><span data-stu-id="def73-269">You may specify the $name as a parameter:</span></span>
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

<span data-ttu-id="def73-270">在 2018 年晚些时候，你不必创建一个默认策略，系统将为组织内的所有收件人创建一个默认策略，因此你不必手动指定它（在最终实施之前，以下屏幕截图可能会发生变更）。</span><span class="sxs-lookup"><span data-stu-id="def73-270">Later in 2018, rather than you having to create a default policy, one will be created for you that is scoped to all the recipients in your organization so you don't have to specify it manually (the screenshots below are subject to change before the final implementation).</span></span>
  
![反网络钓鱼的默认策略](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
<span data-ttu-id="def73-272">与你创建的策略不同，你无法删除默认策略、修改其优先级或选择该策略适用的用户、域或组。</span><span class="sxs-lookup"><span data-stu-id="def73-272">Unlike a policy that you create, you cannot delete the default policy, modify its priority, or choose which users, domains, or groups to scope it to.</span></span>
  
![反网络钓鱼默认策略详细信息](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
<span data-ttu-id="def73-274">使用 PowerShell 设置默认保护：</span><span class="sxs-lookup"><span data-stu-id="def73-274">To set up your default protection by using PowerShell:</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

<span data-ttu-id="def73-275">仅当 Office 365 前面有另一台邮件服务器或服务器时，才应该禁用反欺骗保护（有关详细信息，请参阅“禁用反欺骗的合法情景”）。</span><span class="sxs-lookup"><span data-stu-id="def73-275">You should only disable anti-spoofing protection if you have another mail server or servers in front of Office 365 (see Legitimate scenarios to disable anti-spoofing for more details).</span></span>
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> <span data-ttu-id="def73-276">如果电子邮件路径中的第一个跃点是 Office 365，并且你收到太多标记为欺骗邮件的合法电子邮件，则应该先设置允许其将欺骗性电子邮件发送到你所在域的发件人（请参阅“*管理发送未经身份验证的电子邮件的合法发件人*”一节）。</span><span class="sxs-lookup"><span data-stu-id="def73-276">If the first hop in your email path is Office 365, and you are getting too many legitimate emails marked as spoof, you should first set up your senders that are allowed to send spoofed email to your domain (see the section  *"Managing legitimate senders who are sending unauthenticated email"*  ).</span></span> <span data-ttu-id="def73-277">如果你仍收到太多误报（即标记为欺骗邮件的合法邮件），我们建议你不要完全禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="def73-277">If you are still getting too many false positives (that is, legitimate messages marked as spoof), we do NOT recommend disabling anti-spoofing protection altogether.</span></span> <span data-ttu-id="def73-278">相反，我们建议选择“基本”而不是“高级”保护。</span><span class="sxs-lookup"><span data-stu-id="def73-278">Instead, we recommend choosing Basic instead of High protection.</span></span> <span data-ttu-id="def73-279">解决误报问题比将贵组织暴露在欺骗性电子邮件中更好，后者可能最终导致长期成本显著增加。</span><span class="sxs-lookup"><span data-stu-id="def73-279">It is better to work through false positives than to expose your organization to spoofed email which could end up imposing significantly higher costs in the long term.</span></span>

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="def73-280">管理发送未经身份验证的电子邮件的合法发件人</span><span class="sxs-lookup"><span data-stu-id="def73-280">Managing legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="def73-281">Office 365 会跟踪向贵组织发送未经身份验证的电子邮件的人员。</span><span class="sxs-lookup"><span data-stu-id="def73-281">Office 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="def73-282">如果服务部门认为该发件人不合法，则会将其标记为 *compauth* 失败。</span><span class="sxs-lookup"><span data-stu-id="def73-282">If the service thinks the sender is not legitimate, it will mark it as a *compauth* failure.</span></span> <span data-ttu-id="def73-283">这将归类为“SPOOF”，但具体取决于为邮件应用的反欺骗策略。</span><span class="sxs-lookup"><span data-stu-id="def73-283">This will be classified as SPOOF although it depends on your anti-spoofing policy that was applied to the message.</span></span>
  
<span data-ttu-id="def73-284">但是，作为管理员，你可以指定允许哪些发件人发送欺骗性电子邮件，这会覆盖 Office 365 的决策。</span><span class="sxs-lookup"><span data-stu-id="def73-284">However, as an administrator, you can specify which senders are permitted to send spoofed email, overriding Office 365's decision.</span></span>
  
<span data-ttu-id="def73-285">**方法 1 - 如果你的组织拥有该域，请设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="def73-285">**Method 1 - If your organization owns the domain, set up email authentication**</span></span>
  
<span data-ttu-id="def73-286">如果你拥有多个租户或与多个租户进行交互，则此方法可用于解决组织内欺骗和跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-286">This method can be used to resolve intra-org spoofing, and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="def73-287">它还有助于解决你发送给 Office 365 中的其他客户以及在其他提供程序中托管的第三方的跨域欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-287">It also helps resolve cross-domain spoofing where you send to other customers within Office 365, and also third parties that are hosted in other providers.</span></span>
  
<span data-ttu-id="def73-288">有关详细信息，请参阅 [Office 365 客户](#customers-of-office-365)。</span><span class="sxs-lookup"><span data-stu-id="def73-288">For more details, see [Customers of Office 365](#customers-of-office-365).</span></span>

<span data-ttu-id="def73-289">**方法 2 - 使用反欺骗智能保护配置允许发送未经身份验证的电子邮件的人员**</span><span class="sxs-lookup"><span data-stu-id="def73-289">**Method 2 - Use Spoof intelligence to configure permitted senders of unauthenticated email**</span></span>
  
<span data-ttu-id="def73-290">你也可以使用[反欺骗智能保护](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允许发件人将未经身份验证的邮件传送到你的组织。</span><span class="sxs-lookup"><span data-stu-id="def73-290">You can also use [Spoof Intelligence](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) to permit senders to transmit unauthenticated messages to your organization.</span></span> 
  
<span data-ttu-id="def73-291">对于外部域，冒充的用户位于发件人地址中的域，而发送基础结构是发送 IP 地址（分为 /24 CIDR 范围）或 PTR 记录的组织域（在以下屏幕截图中，发送 IP 可能是 131.107.18.4，其 PTR 记录是 outbound.mail.protection.outlook.com，这将显示为发送基础结构的 outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="def73-291">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the sending IP address (divided up into /24 CIDR ranges), or the organizational domain of the PTR record (in the screenshot below, the sending IP might be 131.107.18.4 whose PTR record is outbound.mail.protection.outlook.com, and this would show up as outlook.com for the sending infrastructure).</span></span>
  
<span data-ttu-id="def73-292">若要允许此发件人发送未经身份验证的电子邮件，请将“**否**”更改为“**是**”。</span><span class="sxs-lookup"><span data-stu-id="def73-292">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>
  
![设置反欺骗允许的发件人](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
<span data-ttu-id="def73-294">你还可以使用 PowerShell 允许特定发件人将邮件发送到你所在的域：</span><span class="sxs-lookup"><span data-stu-id="def73-294">You can also use PowerShell to allow specific sender to spoof your domain:</span></span>
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![通过 Powershell 获取冒充的发件人](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
<span data-ttu-id="def73-296">在上一张图片中，添加了额外的换行符以使此屏幕截图适合查看。</span><span class="sxs-lookup"><span data-stu-id="def73-296">In the previous image, additional line breaks have been added to make this screenshot fit.</span></span> <span data-ttu-id="def73-297">通常情况下，将在单行上显示所有值。</span><span class="sxs-lookup"><span data-stu-id="def73-297">Normally, all the values would appear on a single line.</span></span>
  
<span data-ttu-id="def73-298">编辑文件并查找与 outlook.com 和 bing.com 对应的行，并将 AllowedToSpoof 条目从“否”更改为“是”：</span><span class="sxs-lookup"><span data-stu-id="def73-298">Edit the file and look for the line that corresponds to outlook.com and bing.com, and change the AllowedToSpoof entry from No to Yes:</span></span>
  
![在 Powershell 中将欺骗允许设置为“是”](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
<span data-ttu-id="def73-300">保存该文件，然后运行：</span><span class="sxs-lookup"><span data-stu-id="def73-300">Save the file, and then run:</span></span>
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

<span data-ttu-id="def73-301">现在，将允许 bing.com 发送来自 \*.outlook.com 的未经身份验证的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-301">This will now allow bing.com to send unauthenticated email from \*.outlook.com.</span></span>

<span data-ttu-id="def73-302">**方法 3 - 为发件人/收件人对创建允许条目**</span><span class="sxs-lookup"><span data-stu-id="def73-302">**Method 3 - Create an allow entry for the sender/recipient pair**</span></span>
  
<span data-ttu-id="def73-303">你还可以选择绕过特定发件人的所有垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="def73-303">You can also choose to bypass all spam filtering for a particular sender.</span></span> <span data-ttu-id="def73-304">有关详细信息，请参阅[如何在 Office 365 中将发件人安全地添加到允许列表](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="def73-304">For more details, see [How to securely add a sender to an allow list in Office 365](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/).</span></span>
  
<span data-ttu-id="def73-305">如果使用此方法，它将跳过垃圾邮件和一些网络钓鱼筛选，但不会跳过恶意软件筛选。</span><span class="sxs-lookup"><span data-stu-id="def73-305">If you use this method, it will skip spam and some of the phish filtering, but not malware filtering.</span></span>
  
<span data-ttu-id="def73-306">**方法 4 - 与发件人联系并请求他们设置电子邮件身份验证**</span><span class="sxs-lookup"><span data-stu-id="def73-306">**Method 4 - Contact the sender and ask them to set up email authentication**</span></span>
  
<span data-ttu-id="def73-307">由于存在垃圾邮件和网络钓鱼问题，Microsoft 建议所有发件人设置电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="def73-307">Because of the problem of spam and phishing, Microsoft recommends all senders set up email authentication.</span></span> <span data-ttu-id="def73-308">如果你知道发送域的管理员，请与他们联系并请求他们设置电子邮件身份验证记录，这样你就不必添加任何替代。</span><span class="sxs-lookup"><span data-stu-id="def73-308">If you know an administrator of the sending domain, contact them and request that they set up email authentication records so you do not have to add any overrides.</span></span> <span data-ttu-id="def73-309">有关详细信息，请参阅本文后面的[非 Office 365 客户的域管理员](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="def73-309">For more information, see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers)" later in this article.</span></span> 
  
<span data-ttu-id="def73-310">虽然刚开始可能很难让发送域进行身份验证，但随着时间的推移，随着越来越多的电子邮件筛选器开始放弃甚至拒绝他们的电子邮件，这将使他们设置正确的记录以确保更好地交付。</span><span class="sxs-lookup"><span data-stu-id="def73-310">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span>
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a><span data-ttu-id="def73-311">查看有关多少邮件被标记为欺骗邮件的报表</span><span class="sxs-lookup"><span data-stu-id="def73-311">Viewing reports of how many messages were marked as spoofed</span></span>

<span data-ttu-id="def73-312">启用反欺骗策略后，你可以使用威胁调查和响应功能来获取标记为网络钓鱼的邮件数量。</span><span class="sxs-lookup"><span data-stu-id="def73-312">Once your anti-spoofing policy is enabled, you can use threat investigation and response capabilities to get numbers around how many messages are marked as phish.</span></span> <span data-ttu-id="def73-313">若要执行此操作，请进入“威胁管理”\>“资源管理器”下的安全 &amp; 合规中心 (SCC)，将视图设置为“网络钓鱼”，并按发件人域或保护状态进行分组：</span><span class="sxs-lookup"><span data-stu-id="def73-313">To do this, go into the Security &amp; Compliance Center (SCC) under Threat Management \> Explorer, set the View to Phish, and group by Sender Domain or Protection Status:</span></span>
  
![查看标记为网络钓鱼的邮件数量](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
<span data-ttu-id="def73-315">你可以与各种报表进行交互，以查看有多少邮件标记为网络钓鱼，包括标记为“SPOOF”的邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-315">You can interact with the various reports to see how many were marked as phishing, including messages marked as SPOOF.</span></span> <span data-ttu-id="def73-316">有关详细信息，请参阅[开始使用 Office 365 威胁调查和响应](get-started-with-ti.md)。</span><span class="sxs-lookup"><span data-stu-id="def73-316">To learn more, see [Get started with Office 365 Threat investigation and response](get-started-with-ti.md).</span></span>
  
<span data-ttu-id="def73-317">由于是欺骗而不是其他类型的网络钓鱼（一般网络钓鱼、域或用户模拟等），你无法拆分已标记的邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-317">You can't yet split out which messages were marked due to spoofing as opposed to other types of phishing (general phishing, domain or user impersonation, and so on).</span></span> <span data-ttu-id="def73-318">但是，稍后你可以通过安全 &amp; 合规中心执行此操作。</span><span class="sxs-lookup"><span data-stu-id="def73-318">However, later, you will be able to do this through the Security &amp; Compliance Center.</span></span> <span data-ttu-id="def73-319">完成后，你可以将此报表用作起点，以识别由于身份验证失败而被标记为欺骗邮件的可能合法的发送域。</span><span class="sxs-lookup"><span data-stu-id="def73-319">Once you do, you can use this report as a starting place to identify sending domains that may be legitimate that are being marked as spoof due to failing authentication.</span></span>
  
<span data-ttu-id="def73-320">以下屏幕截图是关于数据外观的建议，但在发布时可能会发生改变：</span><span class="sxs-lookup"><span data-stu-id="def73-320">The following screenshot is a proposal for how this data will look, but may change when released:</span></span>
  
![按检测类型查看网络钓鱼报表](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
<span data-ttu-id="def73-322">对于非 ATP 和 E5 客户，这些报表将在后面的威胁防护状态 (TPS) 报表中提供，但会延迟至少 24 小时。</span><span class="sxs-lookup"><span data-stu-id="def73-322">For non-ATP and E5 customers, these reports will be available later under the Threat Protection Status (TPS) reports, but will be delayed by at least 24 hours.</span></span> <span data-ttu-id="def73-323">此页面将在集成到安全 &amp; 合规中心时进行更新。</span><span class="sxs-lookup"><span data-stu-id="def73-323">This page will be updated as they are integrated into the Security &amp; Compliance Center.</span></span>
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a><span data-ttu-id="def73-324">预测将标记为欺骗邮件的邮件数量</span><span class="sxs-lookup"><span data-stu-id="def73-324">Predicting how many messages will be marked as spoof</span></span>

<span data-ttu-id="def73-325">一旦 Office 365 更新其设置以允许你关闭反欺骗执行，或者启用基本或高级执行，你将能够查看在各种设置下的邮件处置方式的更改。</span><span class="sxs-lookup"><span data-stu-id="def73-325">Once Office 365 updates its settings to let you turn the anti-spoofing enforcement Off, or on with Basic or High enforcement, you will be given the ability to see how message disposition will change at the various settings.</span></span> <span data-ttu-id="def73-326">也就是说，如果反欺骗保护已关闭，那么你将能够看到有多少邮件被检测为欺骗邮件（如果你转向“基本”或者它是基本执行）；如果转向高级执行，那么你将能够看到更多邮件被检测为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-326">That is, if anti-spoofing is Off, you will be able to see how many messages will be detected as Spoof if you turn to Basic; or, if it's Basic, you will be able to see how many more messages will be detected as Spoof if you turn it to High.</span></span>
  
<span data-ttu-id="def73-327">此功能目前正在开发中。</span><span class="sxs-lookup"><span data-stu-id="def73-327">This feature is currently under development.</span></span> <span data-ttu-id="def73-328">随着定义更多详细信息，此页面将使用安全与合规性中心的屏幕截图和 PowerShell 示例进行更新。</span><span class="sxs-lookup"><span data-stu-id="def73-328">As more details are defined, this page will be updated both with screenshots of the Security and Compliance Center, and with PowerShell examples.</span></span>
  
![用于启用反欺骗的“假设”报表](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![允许冒充发件人的可能 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a><span data-ttu-id="def73-331">禁用反欺骗的合法情景</span><span class="sxs-lookup"><span data-stu-id="def73-331">Legitimate scenarios to disable anti-spoofing</span></span>

<span data-ttu-id="def73-332">反欺骗可以更好地保护客户免受网络钓鱼攻击，因此强烈建议不要禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="def73-332">Anti-spoofing better protects customers from phishing attacks, and therefore disabling anti-spoofing protection is strongly discouraged.</span></span> <span data-ttu-id="def73-333">通过禁用它，你可以解决一些短期误报问题，但从长远来看，你将面临更大的风险。</span><span class="sxs-lookup"><span data-stu-id="def73-333">By disabling it, you may resolve some short-term false positives, but long term you will be exposed to more risk.</span></span> <span data-ttu-id="def73-334">在发件人端设置身份验证或对网络钓鱼策略进行调整的成本通常是一次性的，或者只需最少的定期维护。</span><span class="sxs-lookup"><span data-stu-id="def73-334">The cost for setting up authentication on the sender side, or making adjustments in the phishing policies, are usually one-time events or require only minimal, periodic maintenance.</span></span> <span data-ttu-id="def73-335">但是，从数据泄露或资产受损的网络钓鱼攻击中恢复的成本要高得多。</span><span class="sxs-lookup"><span data-stu-id="def73-335">However, the cost to recover from a phishing attack where data has been exposed, or assets have been compromised is much higher.</span></span>
  
<span data-ttu-id="def73-336">出于此原因，最好是解决误报问题而不是禁用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="def73-336">For this reason, it is better to work through anti-spoofing false positives than to disable anti-spoof protection.</span></span>
  
<span data-ttu-id="def73-337">但是，有一种应禁用反欺骗的合法情景，即在邮件路由中有其他邮件筛选产品，而 Office 365 不是电子邮件路径中的第一个跃点：</span><span class="sxs-lookup"><span data-stu-id="def73-337">However, there is a legitimate scenario where anti-spoofing should be disabled, and that is when there are additional mail-filtering products in the message routing, and Office 365 is not the first hop in the email path:</span></span>
  
![客户 MX 记录未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
<span data-ttu-id="def73-339">另一台服务器可能是 Exchange 本地邮件服务器、邮件筛选设备（如 Ironport）或其他云托管服务。</span><span class="sxs-lookup"><span data-stu-id="def73-339">The other server may be an Exchange on-premises mail server, a mail filtering device such as Ironport, or another cloud hosted service.</span></span>
  
<span data-ttu-id="def73-340">如果收件人域的 MX 记录未指向 Office 365，则无需禁用反欺骗，因为 Office 365 会查找你的接收域的 MX 记录，并在其指向其他服务时禁止反欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-340">If the MX record of the recipient domain does not point to Office 365, then there is no need to disable anti-spoofing because Office 365 looks up your receiving domain's MX record and suppresses anti-spoofing if it points to another service.</span></span> <span data-ttu-id="def73-341">如果你不知道域前面是否还有其他服务器，则可以使用 MX Toolbox 等网站查找 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="def73-341">If you don't know if your domain has another server in front, you can use a website like MX Toolbox to look up the MX record.</span></span> <span data-ttu-id="def73-342">它可能显示如下信息：</span><span class="sxs-lookup"><span data-stu-id="def73-342">It might say something like the following:</span></span>
  
![MX 记录指明域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
<span data-ttu-id="def73-344">此域具有未指向 Office 365 的 MX 记录，因此 Office 365 不会应用反欺骗执行。</span><span class="sxs-lookup"><span data-stu-id="def73-344">This domain has an MX record that does not point to Office 365, so Office 365 would not apply anti-spoofing enforcement.</span></span>
  
<span data-ttu-id="def73-345">但是，如果收件人域的 MX 记录*指向* Office 365，即使 Office 365 前面有其他服务，也应禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-345">However, if the MX record of the recipient domain  *does*  point to Office 365, even though there is another service in front of Office 365, then you should disable anti-spoofing.</span></span> <span data-ttu-id="def73-346">最常见的示例是使用收件人重写：</span><span class="sxs-lookup"><span data-stu-id="def73-346">The most common example is through the use of a recipient rewrite:</span></span> 
  
![收件人重写的路由图](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
<span data-ttu-id="def73-348">域 contoso.com 的 MX 记录指向本地服务器，而域 @office365.contoso.net 的 MX 记录则指向 Office 365，因为它在 MX 记录中包含 \*.protection.outlook.com 或 \*.eo.outlook.com：</span><span class="sxs-lookup"><span data-stu-id="def73-348">The domain contoso.com's MX record points to the on-premises server, while the domain @office365.contoso.net's MX record points to Office 365 because it contains \*.protection.outlook.com, or \*.eo.outlook.com in the MX record:</span></span>
  
![MX 记录指向 Office 365，因此可能是收件人重写](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
<span data-ttu-id="def73-350">确保区分收件人域的 MX 记录何时未指向 Office 365，以及何时进行了收件人重写。</span><span class="sxs-lookup"><span data-stu-id="def73-350">Be sure to differentiate when a recipient domain's MX record does not point to Office 365, and when it has undergone a recipient rewrite.</span></span> <span data-ttu-id="def73-351">区分这两种情况非常重要。</span><span class="sxs-lookup"><span data-stu-id="def73-351">It is important to tell the difference between these two cases.</span></span>
  
<span data-ttu-id="def73-352">如果你不确定接收域是否进行了收件人重写，则有时可以通过查看邮件标头来判断。</span><span class="sxs-lookup"><span data-stu-id="def73-352">If you are unsure whether or not your receiving domain has undergone a recipient-rewrite, sometimes you can tell by looking at the message headers.</span></span>
  
<span data-ttu-id="def73-353">a) 首先，在 Authentication-Results 标头中查看收件人域的邮件标头：</span><span class="sxs-lookup"><span data-stu-id="def73-353">a) First, look at the headers in the message for the recipient domain in the Authentication-Results header:</span></span>
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

<span data-ttu-id="def73-354">收件人域位于上面的粗体红色文本中，在本例中为 office365.contoso.net。</span><span class="sxs-lookup"><span data-stu-id="def73-354">The recipient domain is found in the bold red text above, in this case office365.contoso.net.</span></span> <span data-ttu-id="def73-355">这可能与“收件人:”标头中的收件人不同：</span><span class="sxs-lookup"><span data-stu-id="def73-355">This may be different that the recipient in the To: header:</span></span>
  
<span data-ttu-id="def73-356">收件人：示例收件人 \<recipient @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="def73-356">To: Example Recipient \<recipient @ contoso.com\></span></span>
  
<span data-ttu-id="def73-357">执行实际收件人域的 MX 记录查找。</span><span class="sxs-lookup"><span data-stu-id="def73-357">Perform an MX-record lookup of the actual recipient domain.</span></span> <span data-ttu-id="def73-358">如果它包含 \*.protection.outlook.com、mail.messaging.microsoft.com、\*.eo.outlook.com 或 mail.global.frontbridge.com，则表示 MX 指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="def73-358">If it contains \*.protection.outlook.com, mail.messaging.microsoft.com, \*.eo.outlook.com, or mail.global.frontbridge.com, that means that the MX points to Office 365.</span></span>
  
<span data-ttu-id="def73-359">如果它不包含这些值，则表示 MX 未指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="def73-359">If it does not contain those values, then it means that the MX does not point to Office 365.</span></span> <span data-ttu-id="def73-360">你可以使用 MX Toolbox 工具来对此进行验证。</span><span class="sxs-lookup"><span data-stu-id="def73-360">One tool you can use to verify this is MX Toolbox.</span></span>
  
<span data-ttu-id="def73-361">对于此特定示例，以下内容表示 contoso.com 域（看起来像收件人，因为它是“收件人:”标头）具有指向本地服务器的 MX 记录点：</span><span class="sxs-lookup"><span data-stu-id="def73-361">For this particular example, the following says that contoso.com, the domain that looks like the recipient since it was the To: header, has MX record points to an on-prem server:</span></span>
  
![MX 记录指向本地服务器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
<span data-ttu-id="def73-363">但是，实际的收件人是 office365.contoso.net，其 MX 记录指向 Office 365：</span><span class="sxs-lookup"><span data-stu-id="def73-363">However, the actual recipient is office365.contoso.net whose MX record does point to Office 365:</span></span>
  
![MX 指向 Office 365，必须是收件人重写](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
<span data-ttu-id="def73-365">因此，此邮件可能进行了收件人重写。</span><span class="sxs-lookup"><span data-stu-id="def73-365">Therefore, this message has likely undergone a recipient-rewrite.</span></span>
  
<span data-ttu-id="def73-366">b) 其次，务必区分收件人重写的常见用例。</span><span class="sxs-lookup"><span data-stu-id="def73-366">b) Second, be sure to distinguish between common use cases of recipient rewrites.</span></span> <span data-ttu-id="def73-367">如果要将收件人域重写为 \*.onmicrosoft.com，请改为将其重写为 \*.mail.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="def73-367">If you are going to rewrite the recipient domain to \*.onmicrosoft.com, instead rewrite it to \*.mail.onmicrosoft.com.</span></span>
  
<span data-ttu-id="def73-368">一旦确定了在另一台服务器后面路由的最终收件人域，并且收件人域的 MX 记录实际指向Office 365（在其 DNS 记录中发布），则可以继续禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-368">Once you have identified the final recipient domain that is routed behind another server and the recipient domain's MX record actually points to Office 365 (as published in its DNS records), you may proceed to disable anti-spoofing.</span></span>
  
<span data-ttu-id="def73-369">请记住，如果域的路由路径中的第一个跃点是 Office 365，则不希望禁用反欺骗，仅当它位于一个或多个服务之后时才会禁用。</span><span class="sxs-lookup"><span data-stu-id="def73-369">Remember, you don't want to disable anti-spoofing if the domain's first hop in the routing path is Office 365, only when it's behind one or more services.</span></span>
  
### <a name="how-to-disable-anti-spoofing"></a><span data-ttu-id="def73-370">如何禁用反欺骗</span><span class="sxs-lookup"><span data-stu-id="def73-370">How to disable anti-spoofing</span></span>

<span data-ttu-id="def73-371">如果你已创建反网络钓鱼策略，请将 EnableAntispoofEnforcement 参数设置为 $false：</span><span class="sxs-lookup"><span data-stu-id="def73-371">If you already have an Anti-phishing policy created, set the EnableAntispoofEnforcement parameter to $false:</span></span>
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

<span data-ttu-id="def73-372">如果你不知道要禁用的策略的名称，则可以显示它们：</span><span class="sxs-lookup"><span data-stu-id="def73-372">If you don't know the name of the policy (or policies) to disable, you can display them:</span></span>
  
```
Get-AntiphishPolicy | fl Name
```

<span data-ttu-id="def73-373">如果你现在没有任何反网络钓鱼策略，则可以创建一个，然后禁用它（即使没有策略，也会应用反欺骗；在 2018 年晚些时候，将为你创建默认策略，随后你可以禁用它而不是创建一个）。</span><span class="sxs-lookup"><span data-stu-id="def73-373">If you don't have any existing anti-phishing policies, you can create one and then disable it (even if you don't have a policy, anti-spoofing is still applied; later on in 2018, a default policy will be created for you and you can then disable that instead of creating one).</span></span> <span data-ttu-id="def73-374">你必须分多步执行此操作：</span><span class="sxs-lookup"><span data-stu-id="def73-374">You will have to do this in multiple steps:</span></span>
  
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
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

<span data-ttu-id="def73-375">只能通过 cmdlet（稍后将在安全 &amp; 合规中心提供）来禁用反欺骗。</span><span class="sxs-lookup"><span data-stu-id="def73-375">Disabling anti-spoofing is only available via cmdlet (later it will be available in the Security &amp; Compliance Center).</span></span> <span data-ttu-id="def73-376">如果你无权访问 PowerShell，请创建支持票证。</span><span class="sxs-lookup"><span data-stu-id="def73-376">If you do not have access to PowerShell, create a support ticket.</span></span>
  
<span data-ttu-id="def73-377">请记住，这仅适用于发送到 Office 365 时经历间接路由的域。</span><span class="sxs-lookup"><span data-stu-id="def73-377">Remember, this should only be applied to domains that undergo indirect routing when sent to Office 365.</span></span> <span data-ttu-id="def73-378">抵制由于某些误报而禁用反欺骗的诱惑，从长远来看，启用它们会更好。</span><span class="sxs-lookup"><span data-stu-id="def73-378">Resist the temptation to disable anti-spoofing because of some false positives, it will be better in the long run to work through them.</span></span>
  
### <a name="information-for-individual-users"></a><span data-ttu-id="def73-379">面向单个用户的信息</span><span class="sxs-lookup"><span data-stu-id="def73-379">Information for individual users</span></span>

<span data-ttu-id="def73-380">个人用户在如何与反欺骗安全提示进行交互方面受到了限制。</span><span class="sxs-lookup"><span data-stu-id="def73-380">Individual users are limited in how they can interact with the anti-spoofing safety tip.</span></span> <span data-ttu-id="def73-381">但是，你可以通过以下几种方法来解决常见情景问题。</span><span class="sxs-lookup"><span data-stu-id="def73-381">However, there are several things you can do to resolve common scenarios.</span></span>
 
### <a name="common-scenario-1---discussion-lists"></a><span data-ttu-id="def73-382">常见情景 #1 - 讨论列表</span><span class="sxs-lookup"><span data-stu-id="def73-382">Common scenario #1 - Discussion lists</span></span>

<span data-ttu-id="def73-383">由于转发邮件并修改其内容但保留原始“发件人:”地址的方式，已知讨论列表存在反欺骗问题。</span><span class="sxs-lookup"><span data-stu-id="def73-383">Discussion lists are known to have problems with anti-spoofing due to the way they forward the message and modify its contents yet retain the original From: address.</span></span>
  
<span data-ttu-id="def73-384">例如，假设你的电子邮件地址是 user @ contoso.com，并且你对“观鸟”感兴趣并加入讨论列表 birdwatchers @ example.com。</span><span class="sxs-lookup"><span data-stu-id="def73-384">For example, suppose your email address is user @ contoso.com, and you are interested in Bird Watching and join the discussion list birdwatchers @ example.com.</span></span> <span data-ttu-id="def73-385">当你将邮件发送到讨论列表时，你可以通过以下方式发送邮件：</span><span class="sxs-lookup"><span data-stu-id="def73-385">When you send a message to the discussion list, you might send it this way:</span></span>
  
<span data-ttu-id="def73-386">**发件人：** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="def73-386">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="def73-387">**收件人：** 赏鸟者讨论列表 \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="def73-387">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="def73-388">**主题：** 本周到瑞尼尔山顶</span><span class="sxs-lookup"><span data-stu-id="def73-388">**Subject:** Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="def73-389">观赏蓝鸟</span><span class="sxs-lookup"><span data-stu-id="def73-389">Rainier this week</span></span> 
  
<span data-ttu-id="def73-390">有人想本周一起去瑞尼尔山</span><span class="sxs-lookup"><span data-stu-id="def73-390">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="def73-391">赏鸟吗？</span><span class="sxs-lookup"><span data-stu-id="def73-391">Rainier?</span></span>
  
<span data-ttu-id="def73-392">当电子邮件列表收到邮件时，它们将格式化邮件，修改其内容，并向讨论列表上的其余成员重播，他们由来自许多不同电子邮件接收者的参与者组成。</span><span class="sxs-lookup"><span data-stu-id="def73-392">When the email list receives the message, they format the message, modify its contents, and replay it to the rest of the members on the discussion list which is made up of participants from many different email receivers.</span></span>
  
<span data-ttu-id="def73-393">**发件人：** John Doe \<user @ contoso.com\></span><span class="sxs-lookup"><span data-stu-id="def73-393">**From:** John Doe \<user @ contoso.com\></span></span> 
  
<span data-ttu-id="def73-394">**收件人：** 赏鸟者讨论列表 \<birdwatchers @ example.com\></span><span class="sxs-lookup"><span data-stu-id="def73-394">**To:** Birdwatcher's Discussion List \<birdwatchers @ example.com\></span></span> 
  
<span data-ttu-id="def73-395">**主题：**[赏鸟者]本周到瑞尼尔山顶</span><span class="sxs-lookup"><span data-stu-id="def73-395">**Subject:** [BIRDWATCHERS] Great viewing of blue jays at the top of Mt.</span></span> <span data-ttu-id="def73-396">观赏蓝鸟</span><span class="sxs-lookup"><span data-stu-id="def73-396">Rainier this week</span></span> 
  
<span data-ttu-id="def73-397">有人想本周一起去瑞尼尔山</span><span class="sxs-lookup"><span data-stu-id="def73-397">Anyone want to check out the viewing this week from Mt.</span></span> <span data-ttu-id="def73-398">赏鸟吗？</span><span class="sxs-lookup"><span data-stu-id="def73-398">Rainier?</span></span>
  
---
  
<span data-ttu-id="def73-399">此邮件已发送到赏鸟者讨论列表。</span><span class="sxs-lookup"><span data-stu-id="def73-399">This message was sent to the Birdwatchers Discussion List.</span></span> <span data-ttu-id="def73-400">可随时取消订阅。</span><span class="sxs-lookup"><span data-stu-id="def73-400">You can unsubscribe at any time.</span></span>
  
<span data-ttu-id="def73-401">在上面的示例中，重播的邮件具有相同的“发件人:”地址 (user @ contoso.com)，但已通过向主题行添加标记并在邮件底部添加页脚修改了原始邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-401">In the above, the replayed message has the same From: address (user @ contoso.com) but the original message has been modified by adding a tag to the Subject line, and a footer to the bottom of the message.</span></span> <span data-ttu-id="def73-402">这种类型的邮件修改在邮件列表中很常见，并且可能导致误报。</span><span class="sxs-lookup"><span data-stu-id="def73-402">This type of message modification is common in mailing lists, and may result in false positives.</span></span>
  
<span data-ttu-id="def73-403">如果你或组织中的某个人是邮件列表的管理员，则可以将其配置为通过反欺骗检查。</span><span class="sxs-lookup"><span data-stu-id="def73-403">If you or someone in your organization is an administrator of the mailing list, you may be able to configure it to pass anti-spoofing checks.</span></span>
  
- <span data-ttu-id="def73-404">查看 DMARC.org 上的常见问题解答：[在操作邮件列表时，我想与 DMARC 进行交互，我该怎么办？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span><span class="sxs-lookup"><span data-stu-id="def73-404">Check the FAQ at DMARC.org: [I operate a mailing list and I want to interoperate with DMARC, what should I do?](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)</span></span>

- <span data-ttu-id="def73-405">阅读此博客文章中的说明：[关于邮件列表操作员与 DMARC 进行交互以避免失败的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span><span class="sxs-lookup"><span data-stu-id="def73-405">Read the instructions at this blog post: [A tip for mailing list operators to interoperate with DMARC to avoid failures](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)</span></span>

- <span data-ttu-id="def73-406">考虑在邮件列表服务器上安装更新以支持 ARC，请参阅 [https://arc-spec.org](https://arc-spec.org/)</span><span class="sxs-lookup"><span data-stu-id="def73-406">Consider installing updates on your mailing list server to support ARC, see [https://arc-spec.org](https://arc-spec.org/)</span></span>

<span data-ttu-id="def73-407">如果你没有邮件列表的所有权：</span><span class="sxs-lookup"><span data-stu-id="def73-407">If you do not have ownership of the mailing list:</span></span>
  
- <span data-ttu-id="def73-408">你可以请求邮件列表的维护人员实施上述选项之一（他们还应该为从中重播邮件列表的域设置电子邮件身份验证）</span><span class="sxs-lookup"><span data-stu-id="def73-408">You can request the maintainer of the mailing list to implement one of the options above (they should also have email authentication set up for the domain the mailing list is relaying from)</span></span>

- <span data-ttu-id="def73-409">你可以在电子邮件客户端中创建邮箱规则，以将邮件移动到收件箱。</span><span class="sxs-lookup"><span data-stu-id="def73-409">You can create mailbox rules in your email client to move messages to the Inbox.</span></span> <span data-ttu-id="def73-410">你还可以请求组织的管理员设置允许规则或替代，如“管理发送未经身份验证的电子邮件的合法发件人”一节中所述</span><span class="sxs-lookup"><span data-stu-id="def73-410">You can also request your organization's administrators to set up allow rules, or overrides as discussed in the section Managing legitimate senders who are sending unauthenticated email</span></span>

- <span data-ttu-id="def73-411">你可以使用 Office 365 创建支持票证，以便为邮件列表创建替代，以将其视为合法邮件</span><span class="sxs-lookup"><span data-stu-id="def73-411">You can create a support ticket with Office 365 to create an override for the mailing list to treat it as legitimate</span></span>

### <a name="other-scenarios"></a><span data-ttu-id="def73-412">其他情景</span><span class="sxs-lookup"><span data-stu-id="def73-412">Other scenarios</span></span>

1. <span data-ttu-id="def73-413">如果上述常见情景都不适用于你的情况，请将该邮件作为误报报告给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="def73-413">If neither of the above common scenarios applies to your situation, report the message as a false positive back to Microsoft.</span></span> <span data-ttu-id="def73-414">有关详细信息，请参阅本文后面的“[如何向 Microsoft 报告垃圾邮件或非垃圾邮件？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)”部分。</span><span class="sxs-lookup"><span data-stu-id="def73-414">For more information, see the section [How can I report spam or non-spam messages back to Microsoft?](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft) later in this article.</span></span> 

2. <span data-ttu-id="def73-415">你也可以联系电子邮件管理员，他可以将其作为支持票证向 Microsoft 提出。</span><span class="sxs-lookup"><span data-stu-id="def73-415">You may also contact your email administrator who can raise it as a support ticket with Microsoft.</span></span> <span data-ttu-id="def73-416">Microsoft 工程团队将调查邮件被标记为欺骗邮件的原因。</span><span class="sxs-lookup"><span data-stu-id="def73-416">The Microsoft engineering team will investigate why the message was marked as a spoof.</span></span>

3. <span data-ttu-id="def73-417">此外，如果你知道发件人是谁并且确信他们没有被恶意冒充，则可以回复发件人，指明他们正在从未经过身份验证的邮件服务器发送邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-417">Additionally, if you know who the sender is and are confident they are not being maliciously spoofed, you may reply back to the sender indicating that they are sending messages from a mail server that does not authenticate.</span></span> <span data-ttu-id="def73-418">这有时会导致原始发件人联系其 IT 管理员，他们将设置所需的电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="def73-418">This sometimes results in the original sender contacting their IT administrator who will set up the required email authentication records.</span></span>
  
<span data-ttu-id="def73-419">如果有足够多的发件人向域所有者反映他们应该设置电子邮件身份验证记录，这会促使他们采取行动。</span><span class="sxs-lookup"><span data-stu-id="def73-419">When enough senders reply back to domain owners that they should set up email authentication records, it spurs them into taking action.</span></span> <span data-ttu-id="def73-420">虽然 Microsoft 也可与域所有者合作发布所需的记录，但当个人用户提出请求时，它可以提供更多帮助。</span><span class="sxs-lookup"><span data-stu-id="def73-420">While Microsoft also works with domain owners to publish the required records, it helps even more when individual users request it.</span></span>

4. <span data-ttu-id="def73-421">（可选）将发件人添加到“安全发件人”列表中。</span><span class="sxs-lookup"><span data-stu-id="def73-421">Optionally, add the sender to your Safe Senders list.</span></span> <span data-ttu-id="def73-422">但是，请注意，如果网络钓鱼者冒充该帐户，它将递送到你的邮箱。</span><span class="sxs-lookup"><span data-stu-id="def73-422">However, be aware that if a phisher spoofs that account, it will be delivered to your mailbox.</span></span> <span data-ttu-id="def73-423">因此，应谨慎使用此选项。</span><span class="sxs-lookup"><span data-stu-id="def73-423">Therefore, this option should be used sparingly.</span></span>

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a><span data-ttu-id="def73-424">Microsoft 的发件人如何为反欺骗保护做好准备</span><span class="sxs-lookup"><span data-stu-id="def73-424">How senders to Microsoft should prepare for anti-spoofing protection</span></span>

<span data-ttu-id="def73-425">如果你是当前向 Microsoft（Office 365 或 Outlook.com）发送邮件的管理员，则应确保对你的电子邮件进行正确的身份验证，否则系统可能会将其标记为垃圾邮件或网络钓鱼邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-425">If you are an administrator who currently sends messages to Microsoft, either Office 365 or Outlook.com, you should ensure that your email is properly authenticated otherwise it may be marked as spam or phish.</span></span>
  
### <a name="customers-of-office-365"></a><span data-ttu-id="def73-426">Office 365 客户</span><span class="sxs-lookup"><span data-stu-id="def73-426">Customers of Office 365</span></span>

<span data-ttu-id="def73-427">如果你是 Office 365 客户，并且使用 Office 365 发送出站电子邮件：</span><span class="sxs-lookup"><span data-stu-id="def73-427">If you are an Office 365 customer and you use Office 365 to send outbound email:</span></span>
  
- <span data-ttu-id="def73-428">对于你的域，请[在 Office 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span><span class="sxs-lookup"><span data-stu-id="def73-428">For your domains, [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</span></span>

- <span data-ttu-id="def73-429">对于你的主域，请[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="def73-429">For your primary domains, [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md)</span></span>

- <span data-ttu-id="def73-430">[考虑为你的域设置 DMARC 记录](use-dmarc-to-validate-email.md)，以确定谁是合法发件人</span><span class="sxs-lookup"><span data-stu-id="def73-430">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine who are your legitimate senders</span></span>

<span data-ttu-id="def73-431">Microsoft 未针对每个 SPF、DKIM 和 DMARC 提供详细的实施指南。</span><span class="sxs-lookup"><span data-stu-id="def73-431">Microsoft does not provide detailed implementation guidelines for each of SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="def73-432">但是，我们在网上发布了大量信息。</span><span class="sxs-lookup"><span data-stu-id="def73-432">However, there is a lot of information published online.</span></span> <span data-ttu-id="def73-433">此外，还有第三方公司致力于帮助你的组织设置电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="def73-433">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a><span data-ttu-id="def73-434">不是 Office 365 客户的域管理员</span><span class="sxs-lookup"><span data-stu-id="def73-434">Administrators of domains that are not Office 365 customers</span></span>

<span data-ttu-id="def73-435">如果你是域管理员但不是 Office 365 客户：</span><span class="sxs-lookup"><span data-stu-id="def73-435">If you are a domain administrator but are not an Office 365 customer:</span></span>
  
- <span data-ttu-id="def73-436">你应设置 SPF 以发布域的发送 IP 地址，并设置 DKIM（如果可用）以对邮件进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="def73-436">You should set up SPF to publish your domain's sending IP addresses, and also set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="def73-437">你还可以考虑设置 DMARC 记录。</span><span class="sxs-lookup"><span data-stu-id="def73-437">You may also consider setting up DMARC records.</span></span>

- <span data-ttu-id="def73-438">如果有代表你发送电子邮件的批量发件人，则应通过以下方式与他们合作发送电子邮件，即让“发件人:”地址中的发送域（如果它属于你）与通过 SPF 或 DMARC 验证的域保持一致。</span><span class="sxs-lookup"><span data-stu-id="def73-438">If you have bulk senders who are transmitting email on your behalf, you should work with them to send email in a way such that the sending domain in the From: address (if it belongs to you) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="def73-439">如果你拥有本地邮件服务器，或从软件即服务提供程序、Microsoft Azure、GoDaddy、Rackspace、Amazon Web Services 等云托管服务发送，则应该确保它们已添加到你的 SPF 记录中。</span><span class="sxs-lookup"><span data-stu-id="def73-439">If you have on-premises mail servers, or send from a Software-as-a-service provider, or from a cloud-hosting service like Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, or similar, you should ensure that they are added to your SPF record.</span></span>

- <span data-ttu-id="def73-440">如果你的域是由 ISP 托管的小型域，则应根据 ISP 向你提供的说明来设置 SPF 记录。</span><span class="sxs-lookup"><span data-stu-id="def73-440">If you are a small domain that is hosted by an ISP, you should set up your SPF record according to the instructions that is provided to you by your ISP.</span></span> <span data-ttu-id="def73-441">大多数 ISP 都提供这些类型的说明，可在公司的支持页面上找到这些说明。</span><span class="sxs-lookup"><span data-stu-id="def73-441">Most ISPs provide these types of instructions and can be found on the company's support pages.</span></span>

- <span data-ttu-id="def73-442">即使之前不必发布电子邮件身份验证记录也可以，而现在你必须发布要发送给 Microsoft 的电子邮件身份验证记录。</span><span class="sxs-lookup"><span data-stu-id="def73-442">Even if you have not had to publish email authentication records before, and it worked fine, you must still publish email authentication records to send to Microsoft.</span></span> <span data-ttu-id="def73-443">通过这样做，你可以帮助打击网络钓鱼，并降低你或接收邮件的组织遭受网络钓鱼的可能性。</span><span class="sxs-lookup"><span data-stu-id="def73-443">By doing so, you are helping in the fight against phishing, and reducing the possibility that either you, or organizations you send to, will get phished.</span></span>

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a><span data-ttu-id="def73-444">如果你不知道谁将电子邮件作为你的域发送，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="def73-444">What if you don't know who sends email as your domain?</span></span>

<span data-ttu-id="def73-445">许多域均未发布 SPF 记录，因为它们不知道所有发件人都是谁。</span><span class="sxs-lookup"><span data-stu-id="def73-445">Many domains do not publish SPF records because they do not know who all their senders are.</span></span> <span data-ttu-id="def73-446">没关系，你不需要知道他们都是谁。</span><span class="sxs-lookup"><span data-stu-id="def73-446">That's okay, you do not need to know who all of them are.</span></span> <span data-ttu-id="def73-447">相反，你应该先发布自己知道的 SPF 记录，特别是公司通信所在的位置，然后发布中性 SPF 策略，即 ?all:</span><span class="sxs-lookup"><span data-stu-id="def73-447">Instead, you should get started by publishing an SPF record for the ones you do know of, especially where your corporate traffic is located, and publish a neutral SPF policy, ?all:</span></span>
  
<span data-ttu-id="def73-448">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span><span class="sxs-lookup"><span data-stu-id="def73-448">example.com IN TXT "v=spf1 include:spf.example.com ?all"</span></span>
  
<span data-ttu-id="def73-449">中性 SPF 策略意味着从公司基础架构发出的任何电子邮件都将通过所有其他电子邮件接收方的电子邮件身份验证。</span><span class="sxs-lookup"><span data-stu-id="def73-449">The neutral SPF policy means that any email that comes out of your corporate infrastructure will pass email authentication at all other email receivers.</span></span> <span data-ttu-id="def73-450">来自你不知道的发件人的电子邮件将归为中性，这几乎与根本不发布 SPF 记录相同。</span><span class="sxs-lookup"><span data-stu-id="def73-450">Email that comes from senders you don't know about will fall back to neutral, which is almost the same as publishing no SPF record at all.</span></span>
  
<span data-ttu-id="def73-451">发送到 Office 365 时，来自公司通信的电子邮件将标记为已通过身份验证，但来自你不知道的来源的电子邮件仍可能标记为欺骗邮件（具体取决于 Office 365 是否可以对它进行隐式身份验证）。</span><span class="sxs-lookup"><span data-stu-id="def73-451">When sending to Office 365, email that comes from your corporate traffic will be marked as authenticated, but the email that comes from sources you don't know about may still be marked as spoof (depending upon whether or not Office 365 can implicitly authenticate it).</span></span> <span data-ttu-id="def73-452">但是，仍需对所有被 Office 365 标记为欺骗邮件的电子邮件进行改进。</span><span class="sxs-lookup"><span data-stu-id="def73-452">However, this is still an improvement from all email being marked as spoof by Office 365.</span></span>
  
<span data-ttu-id="def73-453">一旦开始使用具有回退策略“?all”的 SPF 记录，你可以逐渐包含越来越多的发送基础结构，然后发布更严格的策略。</span><span class="sxs-lookup"><span data-stu-id="def73-453">Once you've gotten started with an SPF record with a fallback policy of ?all, you can gradually include more and more sending infrastructure and then publish a stricter policy.</span></span> 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a><span data-ttu-id="def73-454">如果你是邮件列表的所有者，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="def73-454">What if you are the owner of a mailing list?</span></span>

<span data-ttu-id="def73-455">请参阅[常见情景 #1 - 讨论列表](#common-scenario-1---discussion-lists)部分。</span><span class="sxs-lookup"><span data-stu-id="def73-455">See the section [Common scenario #1 - Discussion lists](#common-scenario-1---discussion-lists).</span></span>
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a><span data-ttu-id="def73-456">如果你是基础结构提供商（如 Internet 服务提供商 (ISP)、电子邮件服务提供商 (ESP) 或云托管服务），该怎么办？</span><span class="sxs-lookup"><span data-stu-id="def73-456">What if you are an infrastructure provider such as an Internet Service Provider (ISP), Email Service Provider (ESP), or cloud hosting service?</span></span>

<span data-ttu-id="def73-457">如果你负责托管域的电子邮件，并发送电子邮件或提供可以发送电子邮件的托管基础结构，则应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="def73-457">If you host a domain's email, and it sends email, or provide hosting infrastructure that can send email, you should do the following:</span></span>
  
- <span data-ttu-id="def73-458">确保客户提供相关文档来详细说明要在其 SPF 记录中发布的内容</span><span class="sxs-lookup"><span data-stu-id="def73-458">Ensure your customers have documentation detailing what to publish in their SPF records</span></span>

- <span data-ttu-id="def73-459">考虑在出站电子邮件上进行 DKIM 签名，即使客户未明确设置它（使用默认域签名）。</span><span class="sxs-lookup"><span data-stu-id="def73-459">Consider signing DKIM-signatures on outbound email even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="def73-460">你甚至可以使用 DKIM 签名对电子邮件进行双重签名（第一次使用客户的域进行签名（如果已设置该域），第二次使用你公司的 DKIM 签名）</span><span class="sxs-lookup"><span data-stu-id="def73-460">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="def73-461">即使你对来自平台的电子邮件进行身份验证，也无法保证向 Microsoft 的邮件传递，但至少可确保 Microsoft 不会因为未经过身份验证而将你的电子邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-461">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it is not authenticated.</span></span> <span data-ttu-id="def73-462">有关 Outlook.com 如何筛选电子邮件的详细信息，请参阅 [Outlook.com Postmaster 页面](https://postmaster.live.com/pm/postmaster.aspx)。</span><span class="sxs-lookup"><span data-stu-id="def73-462">For more details around how Outlook.com filters email, see the [Outlook.com Postmaster page](https://postmaster.live.com/pm/postmaster.aspx).</span></span>
  
<span data-ttu-id="def73-463">有关服务提供商最佳实践的更多详细信息，请参阅[服务提供商的 M3AAWG 移动消息传递最佳实践](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。</span><span class="sxs-lookup"><span data-stu-id="def73-463">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
  
## <a name="frequently-asked-questions"></a><span data-ttu-id="def73-464">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="def73-464">Frequently Asked Questions</span></span>

### <a name="why-is-microsoft-making-this-change"></a><span data-ttu-id="def73-465">Microsoft 为什么会进行此更改？</span><span class="sxs-lookup"><span data-stu-id="def73-465">Why is Microsoft making this change?</span></span>

<span data-ttu-id="def73-466">由于网络钓鱼攻击的影响，并且电子邮件身份验证已存在超过 15 年，因此 Microsoft 认为继续允许使用未经身份验证的电子邮件的风险高于丢失合法电子邮件的风险。</span><span class="sxs-lookup"><span data-stu-id="def73-466">Because of the impact of phishing attacks, and because email authentication has been around for over 15 years, Microsoft believes that the risk of continue to allow unauthenticated email is higher than the risk of losing legitimate email.</span></span>
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="def73-467">此更改会导致合法电子邮件被标记为垃圾邮件吗？</span><span class="sxs-lookup"><span data-stu-id="def73-467">Will this change cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="def73-468">首先，某些邮件会标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-468">At first, there will be some messages that are marked as spam.</span></span> <span data-ttu-id="def73-469">但是，随着时间的推移，发件人将进行调整，对于大多数电子邮件路径，错误标记为欺骗邮件的邮件数量可以忽略不计。</span><span class="sxs-lookup"><span data-stu-id="def73-469">However, over time, senders will adjust and then the amount of messages mislabeled as spoofed will be negligible for most email paths.</span></span>
  
<span data-ttu-id="def73-470">Microsoft 率先部署了此功能，并在几周后将它部署到其他客户。</span><span class="sxs-lookup"><span data-stu-id="def73-470">Microsoft itself first adopted this feature several weeks before deploying it to the rest of its customers.</span></span> <span data-ttu-id="def73-471">虽然最初出现了中断，但此现象逐渐减少了。</span><span class="sxs-lookup"><span data-stu-id="def73-471">While there was disruption at first, it gradually declined.</span></span>
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a><span data-ttu-id="def73-472">Microsoft 是否会向 Outlook.com 和 Office 365 的非高级威胁防护客户推出此功能？</span><span class="sxs-lookup"><span data-stu-id="def73-472">Will Microsoft bring this feature to Outlook.com and non-Advanced Threat Protection customers of Office 365?</span></span>

<span data-ttu-id="def73-473">Microsoft 的反欺骗技术最初部署到拥有 Office 365 企业版 E5 订阅或已为其订阅购买了 Office 365 高级威胁防护 (ATP) 加载项的组织。</span><span class="sxs-lookup"><span data-stu-id="def73-473">Microsoft's anti-spoofing technology was initially deployed to its organizations that had an Office 365 Enterprise E5 subscription or had purchased the Office 365 Advanced Threat Protection (ATP) add-on for their subscription.</span></span> <span data-ttu-id="def73-474">截至 2018 年 10 月，我们已将保护范围扩展到拥有 Exchange Online Protection (EOP) 的组织。</span><span class="sxs-lookup"><span data-stu-id="def73-474">As of October, 2018 we've extended the protection to organizations that have Exchange Online Protection (EOP) as well.</span></span> <span data-ttu-id="def73-475">将来，我们将为 Outlook.com 发布该功能。</span><span class="sxs-lookup"><span data-stu-id="def73-475">In the future, we may release it for Outlook.com.</span></span> <span data-ttu-id="def73-476">但是，如果我们这样做，可能会有一些未应用的功能，例如报告和自定义替代。</span><span class="sxs-lookup"><span data-stu-id="def73-476">However, if we do, there may be some capabilities that are not applied such as reporting and custom overrides.</span></span>
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="def73-477">如何向 Microsoft 报告垃圾邮件或非垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="def73-477">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="def73-478">你可以使用[适用于 Outlook 的报告消息加载项](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，或者如果未安装它，请[将垃圾邮件、非垃圾邮件和网络欺诈邮件提交给 Microsoft 进行分析](https://technet.microsoft.com/zh-CN/library/jj200769%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="def73-478">You can either use the [Report Message Add-in for Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), or if it isn't installed, [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx).</span></span>
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a><span data-ttu-id="def73-479">我是域管理员，不知道我的所有发件人都是谁！</span><span class="sxs-lookup"><span data-stu-id="def73-479">I'm a domain administrator who doesn't know who all my senders are!</span></span>

<span data-ttu-id="def73-480">请参阅[不是 Office 365 客户的域管理员](#administrators-of-domains-that-are-not-office-365-customers)。</span><span class="sxs-lookup"><span data-stu-id="def73-480">Please see [Administrators of domains that are not Office 365 customers](#administrators-of-domains-that-are-not-office-365-customers).</span></span>
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a><span data-ttu-id="def73-481">如果为组织禁用反欺骗保护会发生什么情况，即使 Office 365 是主筛选器？</span><span class="sxs-lookup"><span data-stu-id="def73-481">What happens if I disable anti-spoofing protection for my organization, even though Office 365 is my primary filter?</span></span>

<span data-ttu-id="def73-482">我们不建议这样做，因为你将接触到更多错过的网络钓鱼和垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-482">We do not recommend this because you will be exposed to more missed phishing and spam messages.</span></span> <span data-ttu-id="def73-483">并非所有网络钓鱼都是欺骗性的，并且并非所有欺骗都会错过。</span><span class="sxs-lookup"><span data-stu-id="def73-483">Not all phishing is spoofing, and not all spoofs will be missed.</span></span> <span data-ttu-id="def73-484">但是，你面临的风险将高于启用反欺骗的客户。</span><span class="sxs-lookup"><span data-stu-id="def73-484">However, your risk will be higher than a customer who enables anti-spoofing.</span></span>
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="def73-485">启用反欺骗保护是否意味着我将免受所有网络钓鱼的侵害？</span><span class="sxs-lookup"><span data-stu-id="def73-485">Does enabling anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="def73-486">遗憾的是，不是，因为网络钓鱼者会不断采用其他技术，如泄露帐户信息或建立免费服务帐户。</span><span class="sxs-lookup"><span data-stu-id="def73-486">Unfortunately, no, because phishers will adapt to use other techniques such as compromised accounts, or setting up accounts of free services.</span></span> <span data-ttu-id="def73-487">但是，反网络钓鱼防护可以更好地检测这些其他类型的网络钓鱼方法，因为 Office 365 的保护层设计在一起工作并且相互叠加。</span><span class="sxs-lookup"><span data-stu-id="def73-487">However, anti-phishing protection works much better to detect these other types of phishing methods because Office 365's protection layers are designed work together and build on top of each other.</span></span>
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a><span data-ttu-id="def73-488">其他大型电子邮件接收器会阻止未经身份验证的电子邮件吗？</span><span class="sxs-lookup"><span data-stu-id="def73-488">Do other large email receivers block unauthenticated email?</span></span>

<span data-ttu-id="def73-489">几乎所有大型电子邮件接收器都实施了传统的 SPF、DKIM 和 DMARC。</span><span class="sxs-lookup"><span data-stu-id="def73-489">Nearly all large email receivers implement traditional SPF, DKIM, and DMARC.</span></span> <span data-ttu-id="def73-490">某些接收器拥有比这些标准更为严格的其他检查，但很少有接收器会像 Office 365 那样阻止未经身份验证的电子邮件并将其视为欺骗邮件。</span><span class="sxs-lookup"><span data-stu-id="def73-490">Some receivers have other checks that are more strict than just those standards, but few go as far as Office 365 to block unauthenticated email and treat them as a spoof.</span></span> <span data-ttu-id="def73-491">但是，对于这种特定类型的电子邮件，大多数行业正变得越来越严格，特别是对于网络钓鱼问题。</span><span class="sxs-lookup"><span data-stu-id="def73-491">However, most of the industry is becoming more and more strict about this particular type of email, particularly because of the problem of phishing.</span></span>
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a><span data-ttu-id="def73-492">如果启用反欺骗，是否仍需要为“SPF 硬失败”启用高级垃圾邮件筛选选项？</span><span class="sxs-lookup"><span data-stu-id="def73-492">Do I still need the Advanced Spam Filtering option enabled for "SPF Hard Fail" if I enable anti-spoofing?</span></span>

<span data-ttu-id="def73-493">否，不再需要此选项，因为反欺骗功能不仅考虑 SPF 硬失败，而且会考虑更广泛的标准。</span><span class="sxs-lookup"><span data-stu-id="def73-493">No, this option is no longer required because the anti-spoofing feature not only considers SPF hard fails, but a much wider set of criteria.</span></span> <span data-ttu-id="def73-494">如果已启用反欺骗并且启用了“SPF 硬失败”选项，则可能会出现更多误报。</span><span class="sxs-lookup"><span data-stu-id="def73-494">If you have anti-spoofing enabled and the SPF Hard Fail option enabled, you will probably get more false positives.</span></span> <span data-ttu-id="def73-495">我们建议禁用此功能，因为它几乎不会额外捕获垃圾邮件或网络钓鱼，而是会产生大多数误报。</span><span class="sxs-lookup"><span data-stu-id="def73-495">We recommend disabling this feature as it would provide almost no additional catch for spam or phish, and instead generate mostly false positives.</span></span>
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a><span data-ttu-id="def73-496">发件人重写方案 (SRS) 是否有助于修复转发的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="def73-496">Does Sender Rewriting Scheme (SRS) help fix forwarded email?</span></span>

<span data-ttu-id="def73-497">SRS 仅部分修复了转发电子邮件的问题。</span><span class="sxs-lookup"><span data-stu-id="def73-497">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="def73-498">通过重写 SMTP MAIL FROM，SRS 可以确保转发的邮件在下一个目的地通过 SPF。</span><span class="sxs-lookup"><span data-stu-id="def73-498">By rewriting the SMTP MAIL FROM, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="def73-499">但是，由于反欺骗基于“发件人:”地址以及 MAIL FROM 或 DKIM 签名域（或其他信号），因此防止将转发的电子邮件标记为欺骗邮件还不够。</span><span class="sxs-lookup"><span data-stu-id="def73-499">However, because anti-spoofing is based upon the From: address in combination with either the MAIL FROM or DKIM-signing domain (or other signals), it is not enough to prevent forwarded email from being marked as spoofed.</span></span>
