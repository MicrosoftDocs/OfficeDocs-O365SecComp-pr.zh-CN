---
title: 使用 DMARC 验证 Office 365 中的电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4a05898c-b8e4-4eab-bd70-ee912e349737
ms.collection:
- M365-security-compliance
description: 了解如何配置基于域的邮件身份验证、报告和一致性 (DMARC), 以验证从 Office 365 组织发送的邮件。
ms.openlocfilehash: 997e90c7620b4b3ca14903da843475f4d724222a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600378"
---
# <a name="use-dmarc-to-validate-email-in-office-365"></a><span data-ttu-id="680cb-103">使用 DMARC 验证 Office 365 中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-103">Use DMARC to validate email in Office 365</span></span>

<span data-ttu-id="680cb-104">基于域的邮件身份验证、报告和一致性 ([DMARC](https://dmarc.org)) 适用于发件人策略框架 (SPF) 和域密钥识别邮件 (DKIM), 用于对邮件发件人进行身份验证, 并确保目标电子邮件系统信任从发送的邮件您的域。</span><span class="sxs-lookup"><span data-stu-id="680cb-104">Domain-based Message Authentication, Reporting, and Conformance ([DMARC](https://dmarc.org)) works with Sender Policy Framework (SPF) and DomainKeys Identified Mail (DKIM) to authenticate mail senders and ensure that destination email systems trust messages sent from your domain.</span></span> <span data-ttu-id="680cb-105">实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="680cb-105">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="680cb-106">DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-106">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span>
  
## <a name="how-do-spf-and-dmarc-work-together-to-protect-email-in-office-365"></a><span data-ttu-id="680cb-107">SPF 和 DMARC 如何协同工作来保护 Office 365 中的电子邮件？</span><span class="sxs-lookup"><span data-stu-id="680cb-107">How do SPF and DMARC work together to protect email in Office 365?</span></span>
<span data-ttu-id="680cb-108"><a name="SPFandDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-108"></span></span>

 <span data-ttu-id="680cb-p102">电子邮件可能包含多个发送方、发件人或地址。这些地址用于不同用途。例如，以下列地址为例：</span><span class="sxs-lookup"><span data-stu-id="680cb-p102">An email message may contain multiple originator, or sender, addresses. These addresses are used for different purposes. For example, consider these addresses:</span></span> 
  
- <span data-ttu-id="680cb-112">"发件人发件人 **" 地址**: 标识发件人并指定在邮件传递时出现任何问题 (例如, 未送达通知) 时将返回通知发送到的位置。</span><span class="sxs-lookup"><span data-stu-id="680cb-112">**"Mail From" address**: Identifies the sender and specifies where to send return notices if any problems occur with the delivery of the message, such as non-delivery notices.</span></span> <span data-ttu-id="680cb-113">该地址出现在电子邮件的信封部分，而电子邮件应用程序通常不显示此地址。</span><span class="sxs-lookup"><span data-stu-id="680cb-113">This appears in the envelope portion of an email message and is not usually displayed by your email application.</span></span> <span data-ttu-id="680cb-114">有时称其为" 5321.MailFrom 地址"或"反向路径地址"。</span><span class="sxs-lookup"><span data-stu-id="680cb-114">This is sometimes called the 5321.MailFrom address or the reverse-path address.</span></span>
    
- <span data-ttu-id="680cb-115">**"发件人" 地址**: 邮件应用程序显示为 "发件人" 地址的地址。</span><span class="sxs-lookup"><span data-stu-id="680cb-115">**"From" address**: The address displayed as the From address by your mail application.</span></span> <span data-ttu-id="680cb-116">此地址标识电子邮件的作者。</span><span class="sxs-lookup"><span data-stu-id="680cb-116">This address identifies the author of the email.</span></span> <span data-ttu-id="680cb-117">即，负责撰写邮件的个人或系统的邮箱。</span><span class="sxs-lookup"><span data-stu-id="680cb-117">That is, the mailbox of the person or system responsible for writing the message.</span></span> <span data-ttu-id="680cb-118">有时称其为" 5322.From 地址"。</span><span class="sxs-lookup"><span data-stu-id="680cb-118">This is sometimes called the 5322.From address.</span></span>
    
<span data-ttu-id="680cb-p105">SPF 使用 DNS TXT 记录为给定的域提供获得授权的发送 IP 地址的列表。通常情况下，仅会针对 5321.MailFrom 地址执行 SPF 检查。这意味着，使用 SPF 本身时 5322.From 地址未通过身份验证。这样允许用户接收通过 SPF 检查但具有伪造的 5322.From 发件人地址的邮件。以下面的 SMTP 脚本为例：</span><span class="sxs-lookup"><span data-stu-id="680cb-p105">SPF uses a DNS TXT record to provide a list of authorized sending IP addresses for a given domain. Normally, SPF checks are only performed against the 5321.MailFrom address. This means that the 5322.From address is not authenticated when you use SPF by itself. This allows for a scenario where a user can receive a message which passes an SPF check but has a spoofed 5322.From sender address. For example, consider this SMTP transcript:</span></span>
  
```
S: Helo woodgrovebank.com
S: Mail from: phish@phishing.contoso.com
S: Rcpt to: astobes@tailspintoys.com
S: data
S: To: "Andrew Stobes" <astobes@tailspintoys.com>
S: From: "Woodgrove Bank Security" <security@woodgrovebank.com>
S: Subject: Woodgrove Bank - Action required
S:
S: Greetings User,
S: 
S: We need to verify your banking details.
S: Please click the following link to verify that we have the right information for your account.
S: 
S: http://short.url/woodgrovebank/updateaccount/12-121.aspx
S:
S: Thank you,
S: Woodgrove Bank
S: .
```

<span data-ttu-id="680cb-124">在此脚本中，发件人地址如下所示：</span><span class="sxs-lookup"><span data-stu-id="680cb-124">In this transcript, the sender addresses are as follows:</span></span>
  
- <span data-ttu-id="680cb-125">邮件发件人地址 (5321) (5321.Mailfrom): phish@phishing.contoso.com</span><span class="sxs-lookup"><span data-stu-id="680cb-125">Mail from address (5321.MailFrom): phish@phishing.contoso.com</span></span>
    
- <span data-ttu-id="680cb-126">发件人地址 (5322.From)：security@woodgrovebank.com</span><span class="sxs-lookup"><span data-stu-id="680cb-126">From address (5322.From): security@woodgrovebank.com</span></span>
    
<span data-ttu-id="680cb-p106">如果你配置了 SPF，那么接收服务器针对从 phish@phishing.contoso.com 地址发送的邮件执行检查。如果该邮件来自 phishing.contoso.com 域的有效源，则会通过 SPF 检查。由于电子邮件客户端仅显示发件人地址，用户可以看到此邮件来自 security@woodgrovebank.com。单独使用 SPF，永远不会验证 woodgrovebank.com 的有效性。</span><span class="sxs-lookup"><span data-stu-id="680cb-p106">If you configured SPF, then the receiving server performs a check against the Mail from address phish@phishing.contoso.com. If the message came from a valid source for the domain phishing.contoso.com then the SPF check passes. Since the email client only displays the From address, the user sees that this message came from security@woodgrovebank.com. With SPF alone, the validity of woodgrovebank.com was never authenticated.</span></span>
  
<span data-ttu-id="680cb-p107">使用 DMARC 时，接收服务器还会针对发件人地址执行检查。在上面的示例中，如果正好存在 woodgrovebank.com 的 DMARC TXT 记录，那么针对发件人地址的检查会失败。</span><span class="sxs-lookup"><span data-stu-id="680cb-p107">When you use DMARC, the receiving server also performs a check against the From address. In the example above, if there is a DMARC TXT record in place for woodgrovebank.com, then the check against the From address fails.</span></span>
  
## <a name="what-is-a-dmarc-txt-record"></a><span data-ttu-id="680cb-133">什么是 DMARC TXT 记录？</span><span class="sxs-lookup"><span data-stu-id="680cb-133">What is a DMARC TXT record?</span></span>
<span data-ttu-id="680cb-134"><a name="WhatisDMARC"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-134"></span></span>

<span data-ttu-id="680cb-p108">像 SPF 的 DNS 记录一样，DMARC 的记录是一个 DNS 文本 (TXT) 记录，有助于防止欺骗和钓鱼。在 DNS 中发布 DMARC TXT 记录。DMARC TXT 记录根据发送域的可疑所有者来验证电子邮件作者的 IP 地址，从而验证电子邮件的来源。 DMARC TXT 记录可以标识得到授权的出站电子邮件服务器。然后，目标电子邮件系统可以验证接收的邮件是否来自得到授权的出站电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="680cb-p108">Like the DNS records for SPF, the record for DMARC is a DNS text (TXT) record that helps prevent spoofing and phishing. You publish DMARC TXT records in DNS. DMARC TXT records validate the origin of email messages by verifying the IP address of an email's author against the alleged owner of the sending domain. The DMARC TXT record identifies authorized outbound email servers. Destination email systems can then verify that messages they receive originate from authorized outbound email servers.</span></span>
  
<span data-ttu-id="680cb-140">Microsoft 的 DMARC TXT 记录如下所示：</span><span class="sxs-lookup"><span data-stu-id="680cb-140">Microsoft's DMARC TXT record looks something like this:</span></span>
  
```
_dmarc.microsoft.com.   3600    IN      TXT     "v=DMARC1; p=none; pct=100; rua=mailto:d@rua.agari.com; ruf=mailto:d@ruf.agari.com; fo=1" 
```

<span data-ttu-id="680cb-p109">Microsoft 将其 DMARC 报告发送至 [Agari](https://agari.com)（第三方）。 Agari 收集并分析 DMARC 报告。</span><span class="sxs-lookup"><span data-stu-id="680cb-p109">Microsoft sends its DMARC reports to [Agari](https://agari.com), a 3rd party. Agari collects and analyzes DMARC reports.</span></span>
  
## <a name="implement-dmarc-for-inbound-mail"></a><span data-ttu-id="680cb-143">为入站邮件实现 DMARC</span><span class="sxs-lookup"><span data-stu-id="680cb-143">Implement DMARC for inbound mail</span></span>
<span data-ttu-id="680cb-144"><a name="implementDMARCinbound"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-144"></span></span>

<span data-ttu-id="680cb-p110">你不必为在 Office 365 中收到的邮件设置 DMARC。我们已经为你处理好了一切。如果你想了解未通过我们的 DMARC 检查时如何处理邮件，请参阅 [Office 365 如何处理未通过 DMARC 的入站电子邮件](use-dmarc-to-validate-email.md#inbounddmarcfail)。</span><span class="sxs-lookup"><span data-stu-id="680cb-p110">You don't have to do a thing to set up DMARC for mail that you receive in Office 365. We've taken care of everything for you. If you want to learn what happens to mail that fails to pass our DMARC checks, see [How Office 365 handles inbound email that fails DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail).</span></span>
  
## <a name="implement-dmarc-for-outbound-mail-from-office-365"></a><span data-ttu-id="680cb-148">从 Office 365 中为出站邮件实现 DMARC</span><span class="sxs-lookup"><span data-stu-id="680cb-148">Implement DMARC for outbound mail from Office 365</span></span>
<span data-ttu-id="680cb-149"><a name="implementDMARCoutbound"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-149"></span></span>

<span data-ttu-id="680cb-p111">如果使用 Office 365 但没有使用自定义域，即，使用 onmicrosoft.com，无需执行任何其他操作即可为组织配置或实现 DMARC。SPF 已为你和 Office 365 自动设置就绪，并为发送邮件生成 DKIM 签名。有关此签名的详细信息，请参阅 [DKIM 和 Office 365 的默认行为](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="680cb-p111">If you use Office 365 but you aren't using a custom domain, that is, you use onmicrosoft.com, you don't need to do anything else to configure or implement DMARC for your organization. SPF is already set up for you and Office 365 automatically generates a DKIM signature for your outgoing mail. For more information about this signature, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
 <span data-ttu-id="680cb-p112">如果有自定义域，或者除了 Office 365 以外还使用本地 Exchange 服务器，则需要为出站邮件手动实现 DMARC。可以通过以下步骤为自定义域实现 DMARC：</span><span class="sxs-lookup"><span data-stu-id="680cb-p112">If you have a custom domain or you are using on-premises Exchange servers in addition to Office 365, you need to manually implement DMARC for your outbound mail. Implementing DMARC for your custom domain includes these steps:</span></span> 
  
- [<span data-ttu-id="680cb-155">步骤 1：为域标识邮件的有效源</span><span class="sxs-lookup"><span data-stu-id="680cb-155">Step 1: Identify valid sources of mail for your domain</span></span>](use-dmarc-to-validate-email.md#IdentifyValidSources)
    
- [<span data-ttu-id="680cb-156">步骤 2：在 Office 365 中为域设置 SPF</span><span class="sxs-lookup"><span data-stu-id="680cb-156">Step 2: Set up SPF for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigSPF)
    
- [<span data-ttu-id="680cb-157">步骤 3：在 Office 365 中为自定义域设置 DKIM</span><span class="sxs-lookup"><span data-stu-id="680cb-157">Step 3: Set up DKIM for your custom domain in Office 365</span></span>](use-dmarc-to-validate-email.md#ConfigDKIM)
    
- [<span data-ttu-id="680cb-158">步骤 4：在 Office 365 中为域生成 DMARC TXT 记录</span><span class="sxs-lookup"><span data-stu-id="680cb-158">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>](use-dmarc-to-validate-email.md#CreateDMARCRecord)
    
### <a name="step-1-identify-valid-sources-of-mail-for-your-domain"></a><span data-ttu-id="680cb-159">步骤 1：为域标识邮件的有效源</span><span class="sxs-lookup"><span data-stu-id="680cb-159">Step 1: Identify valid sources of mail for your domain</span></span>
<span data-ttu-id="680cb-160"><a name="IdentifyValidSources"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-160"></span></span>

<span data-ttu-id="680cb-p113">如果你已经设置了 SPF，那么你已经通过了本练习。但是，对于 DMARC，还有其他一些注意事项。为域标识邮件的源时需要回答以下两个问题：</span><span class="sxs-lookup"><span data-stu-id="680cb-p113">If you have already set up SPF then you have already gone through this exercise. However, for DMARC, there are additional considerations. When identifying sources of mail for your domain there are two questions you need to answer:</span></span>
  
- <span data-ttu-id="680cb-164">哪些 IP 地址从我的域发送邮件？</span><span class="sxs-lookup"><span data-stu-id="680cb-164">What IP addresses send messages from my domain?</span></span>
    
- <span data-ttu-id="680cb-165">对于第三方代表我发送的邮件，5321.MailFrom 和 5322.From 域会匹配吗？</span><span class="sxs-lookup"><span data-stu-id="680cb-165">For mail sent from third parties on my behalf, will the 5321.MailFrom and 5322.From domains match?</span></span>
    
### <a name="step-2-set-up-spf-for-your-domain-in-office-365"></a><span data-ttu-id="680cb-166">步骤 2：在 Office 365 中为域设置 SPF</span><span class="sxs-lookup"><span data-stu-id="680cb-166">Step 2: Set up SPF for your domain in Office 365</span></span>
<span data-ttu-id="680cb-167"><a name="ConfigSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-167"></span></span>

<span data-ttu-id="680cb-168">既然你拥有了所有的有效发件人的列表，你可以按照步骤[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="680cb-168">Now that you have a list of all your valid senders you can follow the steps to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span>
  
<span data-ttu-id="680cb-169">例如，假定 contoso.com 从 Exchange Online 中发送邮件，本地 Exchange 服务器的 IP 地址是 192.168.0.1，并且 Web 应用程序的 IP 地址是 192.168.100.100，则 SPF TXT 记录将如下所示：</span><span class="sxs-lookup"><span data-stu-id="680cb-169">For example, assuming contoso.com sends mail from Exchange Online, an on-premises Exchange server whose IP address is 192.168.0.1, and a web application whose IP address is 192.168.100.100, the SPF TXT record would look like this:</span></span>
  
```
contoso.com  IN  TXT  " v=spf1 ip4:192.168.0.1 ip4:192.168.100.100 include:spf.protection.outlook.com -all"
```

<span data-ttu-id="680cb-170">作为最佳做法，请确保 SPF TXT 记录考虑第三方发件人。</span><span class="sxs-lookup"><span data-stu-id="680cb-170">As a best practice, ensure that your SPF TXT record takes into account third-party senders.</span></span>
  
### <a name="step-3-set-up-dkim-for-your-custom-domain-in-office-365"></a><span data-ttu-id="680cb-171">步骤 3：在 Office 365 中为自定义域设置 DKIM</span><span class="sxs-lookup"><span data-stu-id="680cb-171">Step 3: Set up DKIM for your custom domain in Office 365</span></span>
<span data-ttu-id="680cb-172"><a name="ConfigDKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-172"></span></span>

<span data-ttu-id="680cb-p114">一旦设置了 SPF，就需要设置 DKIM。你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。如果你不设置 DKIM，反而允许 Office 365 对你的域使用默认的 DKIM 配置，则 DMARC 可能会失败。这是因为默认的 DKIM 配置使用你的初始 onmicrosoft.com 域作为 5322.From 地址，而不是使用自定义域。这将强制从你的域发送的所有电子邮件的 5321.MailFrom 和 5322.From 地址不匹配。</span><span class="sxs-lookup"><span data-stu-id="680cb-p114">Once you have set up SPF, you need to set up DKIM. DKIM lets you add a digital signature to email messages in the message header. If you do not set up DKIM and instead allow Office 365 to use the default DKIM configuration for your domain, DMARC may fail. This is because the default DKIM configuration uses your initial onmicrosoft.com domain as the 5322.From address, not your custom domain. This forces a mismatch between the 5321.MailFrom and the 5322.From addresses in all email sent from your domain.</span></span>
  
<span data-ttu-id="680cb-p115">如果你有代表你发送邮件的第三方发件人，并且他们发送的邮件的 5321.MailFrom 和 5322.From 地址不匹配，则该电子邮件将无法通过 DMARC。若要避免此问题，你需要专门为具有该第三方发件人的域设置 DKIM。这将允许 Office 365 验证来自此第三方服务的电子邮件。 但是，它也允许其他方（例如，Yahoo、Gmail 和 Comcast）验证通过该第三方发送给他们的电子邮件，就好像电子邮件是由你发送的一样。这是有好处的，因为它允许你的客户构建对你的域的信任，无论他们的邮箱位于何处，与此同时，Office 365 不会因欺骗而将邮件标记为垃圾邮件，因为它通过了对你的域的身份验证检查。</span><span class="sxs-lookup"><span data-stu-id="680cb-p115">If you have third-party senders that send mail on your behalf and the mail they send has mismatched 5321.MailFrom and 5322.From addresses, DMARC will fail for that email. To avoid this, you need to set up DKIM for your domain specifically with that third-party sender. This allows Office 365 to authenticate email from this 3rd-party service. However, it also allows others, for example, Yahoo, Gmail, and Comcast, to verify email sent to them by the third-party as if it was email sent by you. This is beneficial because it allows your customers to build trust with your domain no matter where their mailbox is located, and at the same time Office 365 won't mark a message as spam due to spoofing because it passes authentication checks for your domain.</span></span>
  
<span data-ttu-id="680cb-183">有关为域设置 DKIM 的说明，包括如何为第三方发件人设置 DKIM，以便他们可以欺骗你的域，请参阅[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="680cb-183">For instructions on setting up DKIM for your domain, including how to set up DKIM for third-party senders so they can spoof your domain, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>
  
### <a name="step-4-form-the-dmarc-txt-record-for-your-domain-in-office-365"></a><span data-ttu-id="680cb-184">步骤 4：在 Office 365 中为域生成 DMARC TXT 记录</span><span class="sxs-lookup"><span data-stu-id="680cb-184">Step 4: Form the DMARC TXT record for your domain in Office 365</span></span>
<span data-ttu-id="680cb-185"><a name="CreateDMARCRecord"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-185"></span></span>

<span data-ttu-id="680cb-p116">尽管还有此处未提及的其他语法选项，但这些都是最常用于 Office 365 的选项。在 Office 365 中为域生成 DMARC TXT 记录，格式如下：</span><span class="sxs-lookup"><span data-stu-id="680cb-p116">Although there are other syntax options that are not mentioned here, these are the most commonly used options for Office 365. Form the DMARC TXT record for your domain in the format:</span></span>
  
```
_dmarc.domain  TTL  IN  TXT  "v=DMARC1; pct=100; p=policy"
```

<span data-ttu-id="680cb-188">其中：</span><span class="sxs-lookup"><span data-stu-id="680cb-188">where:</span></span>
  
- <span data-ttu-id="680cb-189">*域*是你想要保护的域。</span><span class="sxs-lookup"><span data-stu-id="680cb-189">*domain* is the domain you want to protect.</span></span> <span data-ttu-id="680cb-190">默认情况下，该记录可保护从该域和所有子域发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-190">By default, the record protects mail from the domain and all subdomains.</span></span> <span data-ttu-id="680cb-191">例如, 如果指定\_dmarc.contoso.com, 则 dmarc 将保护来自域和所有子域的邮件, 如 housewares.contoso.com 或 plumbing.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="680cb-191">For example, if you specify \_dmarc.contoso.com, then DMARC protects mail from the domain and all subdomains, such as housewares.contoso.com or plumbing.contoso.com.</span></span> 
    
- <span data-ttu-id="680cb-p118">*TTL* 应始终相当于一小时。用于 TTL 的单位可以为小时（1 小时）、分钟（60 分钟）或秒（3600 秒），具体取决于你的域的注册机构。</span><span class="sxs-lookup"><span data-stu-id="680cb-p118">*TTL* should always be the equivalent of one hour. The unit used for TTL, either hours (1 hour), minutes (60 minutes), or seconds (3600 seconds), will vary depending on the registrar for your domain.</span></span> 
    
- <span data-ttu-id="680cb-194">*pct = 100*表示应将此规则用于电子邮件的 100%。</span><span class="sxs-lookup"><span data-stu-id="680cb-194">*pct=100* indicates that this rule should be used for 100% of email.</span></span>
    
- <span data-ttu-id="680cb-p119">*策略*指定 DMARC 失败时你希望接收服务器遵循的策略。你可以将策略设置为无、隔离或拒绝。</span><span class="sxs-lookup"><span data-stu-id="680cb-p119">*policy* specifies what policy you want the receiving server to follow if DMARC fails. You can set the policy to none, quarantine, or reject.</span></span> 
    
<span data-ttu-id="680cb-197">有关要使用的选项的信息，请熟悉[在 Office 365 中实现 DMARC 的最佳做法](use-dmarc-to-validate-email.md#DMARCbestpractices)中的概念。</span><span class="sxs-lookup"><span data-stu-id="680cb-197">For information about which options to use, become familiar with the concepts in [Best practices for implementing DMARC in Office 365](use-dmarc-to-validate-email.md#DMARCbestpractices).</span></span>
  
<span data-ttu-id="680cb-198">示例：</span><span class="sxs-lookup"><span data-stu-id="680cb-198">Examples:</span></span>
  
- <span data-ttu-id="680cb-199">策略设置为无</span><span class="sxs-lookup"><span data-stu-id="680cb-199">Policy set to none</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=none"
    ```

- <span data-ttu-id="680cb-200">策略设置为隔离</span><span class="sxs-lookup"><span data-stu-id="680cb-200">Policy set to quarantine</span></span>
  
    ```
    _dmarc.contoso.com 3600 IN  TXT  "v=DMARC1; p=quarantine"
    ```

- <span data-ttu-id="680cb-201">策略设置为拒绝</span><span class="sxs-lookup"><span data-stu-id="680cb-201">Policy set to reject</span></span>
  
    ```
    _dmarc.contoso.com  3600 IN  TXT  "v=DMARC1; p=reject"
    ```

<span data-ttu-id="680cb-p120">生成记录后，你需要在你的域注册机构中更新记录。有关为 Office 365 将 DMARC TXT 记录添加到 DNS 记录的说明，请参阅[管理 DNS 记录时为 Office 365 创建 DNS 记录](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。</span><span class="sxs-lookup"><span data-stu-id="680cb-p120">Once you have formed your record, you need to update the record at your domain registrar. For instructions on adding the DMARC TXT record to your DNS records for Office 365, see [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
  
## <a name="best-practices-for-implementing-dmarc-in-office-365"></a><span data-ttu-id="680cb-204">在 Office 365 中实现 DMARC 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="680cb-204">Best practices for implementing DMARC in Office 365</span></span>
<span data-ttu-id="680cb-205"><a name="DMARCbestpractices"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-205"></span></span>

<span data-ttu-id="680cb-p121">你可以逐渐实现 DMARC，而不会影响邮件流的其余部分。创建和实施遵循以下步骤的推广计划。首先使用任一子域执行以下每一个步骤，然后使用其他子域，最后使用组织内的顶级域，然后再继续下一步骤。</span><span class="sxs-lookup"><span data-stu-id="680cb-p121">You can implement DMARC gradually without impacting the rest of your mail flow. Create and implement a roll out plan that follows these steps. Do each of these steps first with a sub-domain, then other sub-domains, and finally with the top-level domain in your organization before moving on to the next step.</span></span>
  
1. <span data-ttu-id="680cb-209">监视实现 DMARC 的影响</span><span class="sxs-lookup"><span data-stu-id="680cb-209">Monitor the impact of implementing DMARC</span></span>
    
    <span data-ttu-id="680cb-p122">从请求 DMARC 接收器向你发送关于使用该域时看到的消息的统计信息的子域或域的简单的监视模式记录开始。监视模式记录是将策略设置为无 (p=none) 的 DMARC TXT 记录。许多公司发布了 p=none 的 DMARC TXT 记录，因为他们不确定通过发布更严格的 DMARC 策略可能会丢失多少电子邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-p122">Start with a simple monitoring-mode record for a sub-domain or domain that requests that DMARC receivers send you statistics about messages that they see using that domain. A monitoring-mode record is a DMARC TXT record that has its policy set to none (p=none). Many companies publish a DMARC TXT record with p=none because they are unsure about how much email they may lose by publishing a more restrictive DMARC policy.</span></span> 
    
    <span data-ttu-id="680cb-p123">即使在邮件传递基础结构中实现 SPF 或 DKIM 之前，你也可以这样做。但是，你将无法使用 DMARC 有效地隔离或拒绝邮件，直到你也实现了 SPF 和 DKIM 之后才可以。当引入 SPF 和 DKIM 时，通过 DMARC 生成的报告将提供通过这些检查和未通过检查的邮件的数量和源。你可以轻松地查看这些邮件占用了多少合法通信量，并解决所有问题。你还将开始看到即将发送的欺诈邮件的数量以及发送地点。</span><span class="sxs-lookup"><span data-stu-id="680cb-p123">You can do this even before you've implemented SPF or DKIM in your messaging infrastructure. However, you won't be able to effectively quarantine or reject mail by using DMARC until you also implement SPF and DKIM. As you introduce SPF and DKIM, the reports generated through DMARC will provide the numbers and sources of messages that pass these checks, and those that don't. You can easily see how much of your legitimate traffic is or isn't covered by them, and troubleshoot any problems. You'll also begin to see how many fraudulent messages are being sent, and from where.</span></span>
    
2. <span data-ttu-id="680cb-218">请求外部邮件系统隔离未通过 DMARC 的邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-218">Request that external mail systems quarantine mail that fails DMARC</span></span>
    
    <span data-ttu-id="680cb-p124">当你相信全部或大部分合法通信受 SPF 和 DKIM 保护，并且了解实现 DMARC 的影响时，你可以实施隔离策略。隔离策略是策略设置为隔离 (p=quarantine) 的 DMARC TXT 记录。通过执行此操作，你将要求 DMARC 接收器将来自你的域的未通过 DMARC 的邮件放入相当于垃圾邮件文件夹的本地位置，而不是客户的收件箱。</span><span class="sxs-lookup"><span data-stu-id="680cb-p124">When you believe that all or most of your legitimate traffic is protected by SPF and DKIM, and you understand the impact of implementing DMARC, you can implement a quarantine policy. A quarantine policy is a DMARC TXT record that has its policy set to quarantine (p=quarantine). By doing this, you are asking DMARC receivers to put messages from your domain that fail DMARC into the local equivalent of a spam folder instead of your customers' inboxes.</span></span>
    
3. <span data-ttu-id="680cb-222">请求外部邮件系统不接受未通过 DMARC 的邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-222">Request that external mail systems not accept messages that fail DMARC</span></span>
    
    <span data-ttu-id="680cb-p125">最后一步是实施拒绝策略。拒绝策略是策略设置为拒绝 (p=reject) 的 DMARC TXT 记录。执行此操作时，你将要求 DMARC 接收器不接受未通过 DMARC 检查的邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-p125">The final step is implementing a reject policy. A reject policy is a DMARC TXT record that has its policy set to reject (p=reject). When you do this, you're asking DMARC receivers not to accept messages that fail the DMARC checks.</span></span> 
    
## <a name="how-office-365-handles-outbound-email-that-fails-dmarc"></a><span data-ttu-id="680cb-226">Office 365 如何处理未通过 DMARC 的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-226">How Office 365 handles outbound email that fails DMARC</span></span>
<span data-ttu-id="680cb-227"><a name="outbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-227"></span></span>

<span data-ttu-id="680cb-228">如果从 Office 365 出站邮件且 DMARC 失败, 并且您已将策略设置为 p = 隔离或 p = 拒绝, 则邮件将通过[高风险传递池中的出站邮件进行](high-risk-delivery-pool-for-outbound-messages.md)路由。</span><span class="sxs-lookup"><span data-stu-id="680cb-228">If a message is outbound from Office 365 and fails DMARC, and you have set the policy to p=quarantine or p=reject, the message is routed through the [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> <span data-ttu-id="680cb-229">出站电子邮件不存在任何替代方法。</span><span class="sxs-lookup"><span data-stu-id="680cb-229">There is no override for outbound email.</span></span>
  
<span data-ttu-id="680cb-p127">如果你发布 DMARC 拒绝策略 (p=reject)，则 Office 365 中的任何其他客户都无法欺骗你的域，因为通过服务中继出站邮件时邮件将无法通过你的域的 SPF 或 DKIM。 不过，如果你发布 DMARC 拒绝策略，但并非所有电子邮件均通过 Office 365 进行了验证，部分可能会被标记为入站电子邮件的垃圾邮件（如上所述），或者如果你不发布 SPF 且尝试通过服务将其中继到出站，邮件将被拒绝。 例如，当你生成 DMARC TXT 记录时，如果你忘记包括代表你的域发送邮件的服务器和应用的某些 IP 地址，就会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="680cb-p127">If you publish a DMARC reject policy (p=reject), no other customer in Office 365 can spoof your domain because messages will not be able to pass SPF or DKIM for your domain when relaying a message outbound through the service. However, if you do publish a DMARC reject policy but don't have all of your email authenticated through Office 365, some of it may be marked as spam for inbound email (as described above), or it will be rejected if you do not publish SPF and try to relay it outbound through the service. This happens, for example, if you forget to include some of the IP addresses for servers and apps that send mail on behalf of your domain when you form your DMARC TXT record.</span></span>
  
## <a name="how-office-365-handles-inbound-email-that-fails-dmarc"></a><span data-ttu-id="680cb-233">Office 365 如何处理未通过 DMARC 的入站电子邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-233">How Office 365 handles inbound email that fails DMARC</span></span>
<span data-ttu-id="680cb-234"><a name="inbounddmarcfail"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-234"></span></span>

<span data-ttu-id="680cb-p128">如果发送服务器的 DMARC 策略是 p=reject，则 EOP 会将该邮件标记为垃圾邮件，而不是拒绝它。换句话说，对于入站电子邮件，Office 365 将 p=reject 和 p=quarantine 视为相同方式。</span><span class="sxs-lookup"><span data-stu-id="680cb-p128">If the DMARC policy of the sending server is p=reject, EOP marks the message as spam instead of rejecting it. In other words, for inbound email, Office 365 treats p=reject and p=quarantine the same way.</span></span>
  
<span data-ttu-id="680cb-p129">之所以像这样配置 office 365，是因为某些合法的电子邮件可能会无法通过 DMARC。例如，如果将邮件发送到一个邮件列表，然后将其中继到所有列表参与者，则该邮件可能无法通过 DMARC。如果 Office 365 拒绝这些邮件，人们可能会丢失合法的电子邮件，而且无法进行检索。 相反，这些邮件仍然无法通过 DMARC，但会将其标记为垃圾邮件而不是拒绝。如果需要，用户仍可以在其收件箱中获得这些邮件，方法如下：</span><span class="sxs-lookup"><span data-stu-id="680cb-p129">Office 365 is configured like this because some legitimate email may fail DMARC. For example, a message might fail DMARC if it is sent to a mailing list that then relays the message to all list participants. If Office 365 rejected these messages, people could lose legitimate email and have no way to retrieve it. Instead, these messages will still fail DMARC but they will be marked as spam and not rejected. If desired, users can still get these messages in their inbox through these methods:</span></span>
  
- <span data-ttu-id="680cb-242">用户使用其电子邮件客户端分别添加安全发件人</span><span class="sxs-lookup"><span data-stu-id="680cb-242">Users add safe senders individually by using their email client</span></span>
    
- <span data-ttu-id="680cb-243">管理员为所有用户创建一个 Exchange 邮件流规则 (也称为传输规则), 以允许这些特定发件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-243">Administrators create an Exchange mail flow rule (also known as a transport rule) for all users that allows messages for those particular senders.</span></span> 
    
## <a name="troubleshooting-your-dmarc-implementation"></a><span data-ttu-id="680cb-244">DMARC 实现疑难解答</span><span class="sxs-lookup"><span data-stu-id="680cb-244">Troubleshooting your DMARC implementation</span></span>
<span data-ttu-id="680cb-245"><a name="dmarctroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-245"></span></span>

<span data-ttu-id="680cb-246">如果你已配置了域的 MX 记录，其中 EOP 不是第一项，将不会为你的域强制执行 DMARC 失败。</span><span class="sxs-lookup"><span data-stu-id="680cb-246">If you have configured your domain's MX records where EOP is not the first entry, DMARC failures will not be enforced for your domain.</span></span> 
  
<span data-ttu-id="680cb-p130">如果你是 Office 365 客户，并且你的域的主 MX 记录不指向 EOP，你将不会获得 DMARC 的好处。例如，如果你将 MX 记录指向你的本地邮件服务器，然后使用连接器将电子邮件路由到 EOP，则 DMARC 将不起作用。在这种情况下，接收域是一个接受的域，但 EOP 不是主 MX。例如，假设 contoso.com 本身指向其 MX 并将 EOP 用作辅助 MX 记录，contoso.com 的 MX 记录将如下所示：</span><span class="sxs-lookup"><span data-stu-id="680cb-p130">If you're an Office 365 customer, and your domain's primary MX record does not point to EOP, you will not get the benefits of DMARC. For example, DMARC won't work if you point the MX record to your on-premises mail server and then route email to EOP by using a connector. In this scenario, the receiving domain is one of your Accepted-Domains but EOP is not the primary MX. For example, suppose contoso.com points its MX at itself and uses EOP as a secondary MX record, contoso.com's MX record looks like the following:</span></span>
  
```
contoso.com     3600   IN  MX  0  mail.contoso.com
contoso.com     3600   IN  MX  10 contoso-com.mail.protection.outlook.com
```

<span data-ttu-id="680cb-251">由于它是主 MX，全部或大部分电子邮件将首先被路由到 mail.contoso.com，然后将邮件路由到 EOP。</span><span class="sxs-lookup"><span data-stu-id="680cb-251">All, or most, email will first be routed to mail.contoso.com since it's the primary MX, and then mail will get routed to EOP.</span></span> <span data-ttu-id="680cb-252">在某些情况下，你甚至不可能将 EOP 列为 MX 记录，并直接挂接连接器来路由你的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="680cb-252">In some cases, you might not even list EOP as an MX record at all and simply hook up connectors to route your email.</span></span> <span data-ttu-id="680cb-253">EOP 不一定是要完成的 DMARC 验证的第一个条目。</span><span class="sxs-lookup"><span data-stu-id="680cb-253">EOP does not have to be the first entry for DMARC validation to be done.</span></span> <span data-ttu-id="680cb-254">它只是确保验证, 因为我们无法确保所有内部部署/非 O365 服务器将执行 DMARC 检查。</span><span class="sxs-lookup"><span data-stu-id="680cb-254">It just ensures the validation, as we cannot be certain that all on-premise/non-O365 servers will do DMARC checks.</span></span>  <span data-ttu-id="680cb-255">当您设置 DMARC TXT 记录时, DMARC 有资格强制实施客户的域 (而不是服务器), 但在接收服务器上实际执行强制。</span><span class="sxs-lookup"><span data-stu-id="680cb-255">DMARC is eligible to be enforced for a customer’s domain (not server) when you set up the DMARC TXT record, but it is up to the receiving server to actually do the enforcement.</span></span>  <span data-ttu-id="680cb-256">如果将 EOP 设置为接收服务器, 则 EOP 执行 DMARC 强制。</span><span class="sxs-lookup"><span data-stu-id="680cb-256">If you set up EOP as the receiving server, then EOP does the DMARC enforcement.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="680cb-257">详细信息</span><span class="sxs-lookup"><span data-stu-id="680cb-257">For more information</span></span>
<span data-ttu-id="680cb-258"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-258"></span></span>

<span data-ttu-id="680cb-p132">想要了解有关 DMARC 的详细信息？以下资源可以派上用场。</span><span class="sxs-lookup"><span data-stu-id="680cb-p132">Want more information about DMARC? These resources can help.</span></span>
  
- <span data-ttu-id="680cb-261">[反垃圾邮件邮件头](anti-spam-message-headers.md) 包括 Office 365 执行 DMARC 检查时使用的语法和标头字段。</span><span class="sxs-lookup"><span data-stu-id="680cb-261">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DMARC checks.</span></span> 
    
- <span data-ttu-id="680cb-262">参加 M[3](https://www.m3aawg.org/activities/training/dmarc-training-series)AAWG（消息、恶意软件、移动反滥用工作组）提供的 <sup>DMARC 培训系列</sup>。</span><span class="sxs-lookup"><span data-stu-id="680cb-262">Take the [DMARC Training Series](https://www.m3aawg.org/activities/training/dmarc-training-series) from M <sup>3</sup>AAWG (Messaging, Malware, Mobile Anti-Abuse Working Group).</span></span>
    
- <span data-ttu-id="680cb-263">使用检查表，位于 [dmarcian](https://space.dmarcian.com/deployment/)。</span><span class="sxs-lookup"><span data-stu-id="680cb-263">Use the checklist at [dmarcian](https://space.dmarcian.com/deployment/).</span></span>
    
- <span data-ttu-id="680cb-264">直接访问源，位于 [DMARC.org](https://dmarc.org)。</span><span class="sxs-lookup"><span data-stu-id="680cb-264">Go directly to the source at [DMARC.org](https://dmarc.org).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="680cb-265">另请参阅</span><span class="sxs-lookup"><span data-stu-id="680cb-265">See also</span></span>
<span data-ttu-id="680cb-266"><a name="sectionSection8"> </a></span><span class="sxs-lookup"><span data-stu-id="680cb-266"></span></span>

[<span data-ttu-id="680cb-267">Office 365 如何使用发件人策略框架 (SPF) 来防止欺骗</span><span class="sxs-lookup"><span data-stu-id="680cb-267">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)
  
[<span data-ttu-id="680cb-268">在 Office 365 中设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="680cb-268">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
  
[<span data-ttu-id="680cb-269">使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="680cb-269">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md)

