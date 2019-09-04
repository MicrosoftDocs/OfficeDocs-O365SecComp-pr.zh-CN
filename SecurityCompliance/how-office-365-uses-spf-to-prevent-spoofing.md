---
title: Office 365 如何使用发件人策略框架 (SPF) 来防止欺骗
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/15/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3aff33c5-1416-4867-a23b-e0c0c5b4d2be
ms.collection:
- M365-security-compliance
description: 摘要： 本文介绍了 Office 365 如何在 DNS 中使用发件人策略框架 (SPF) TXT 记录，以确保目标电子邮件系统信任从自定义域发送的邮件。 这适用于从 Office 365 发送的出站邮件。 从 Office 365 发送给 Office 365 收件人的邮件始终可通过 SPF。
ms.openlocfilehash: 41055f5eb2f3fe3e4e54f7b863b3739ec51c198a
ms.sourcegitcommit: 8be0297950840e33dc693d139b69ee142edbed81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2019
ms.locfileid: "36714011"
---
# <a name="how-office-365-uses-sender-policy-framework-spf-to-prevent-spoofing"></a><span data-ttu-id="d3d81-105">Office 365 如何使用发件人策略框架 (SPF) 来防止欺骗</span><span class="sxs-lookup"><span data-stu-id="d3d81-105">How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing</span></span>

 <span data-ttu-id="d3d81-p102">**摘要：** 本文介绍了 Office 365 如何在 DNS 中使用发件人策略框架 (SPF) TXT 记录，以确保目标电子邮件系统信任从自定义域发送的邮件。这适用于从 Office 365 发送的出站邮件。从 Office 365 发送给 Office 365 收件人的邮件始终可通过 SPF。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p102">**Summary:** This article describes how Office 365 uses the Sender Policy Framework (SPF) TXT record in DNS to ensure that destination email systems trust messages sent from your custom domain. This applies to outbound mail sent from Office 365. Messages sent from Office 365 to a recipient within Office 365 will always pass SPF.</span></span> 
  
<span data-ttu-id="d3d81-p103">SPF TXT 记录是一个 DNS 记录，通过验证发出电子邮件的域的域名，帮助阻止欺骗和钓鱼。SPF 根据发送域的可疑所有者来验证发件人的 IP 地址，从而验证电子邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p103">An SPF TXT record is a DNS record that helps prevent spoofing and phishing by verifying the domain name from which email messages are sent. SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d3d81-p104">Internet 工程任务组 (IETF) 于 2014 年弃用 SPF 记录类型。请务必在 DNS 中改用 TXT 记录来发布 SPF 信息。为清楚起见，本文的其余部分使用 SPF TXT 记录一词。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p104">SPF record types were deprecated by the Internet Engineering Task Force (IETF) in 2014. Instead, ensure that you use TXT records in DNS to publish your SPF information. The rest of this article uses the term SPF TXT record for clarity.</span></span> 
  
<span data-ttu-id="d3d81-114">域管理员在 DNS 的 TXT 记录中发布 SPF 信息。</span><span class="sxs-lookup"><span data-stu-id="d3d81-114">Domain administrators publish SPF information in TXT records in DNS.</span></span> <span data-ttu-id="d3d81-115">SPF 信息可以标识得到授权的出站电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="d3d81-115">The SPF information identifies authorized outbound email servers.</span></span> <span data-ttu-id="d3d81-116">目标电子邮件系统验证邮件是否来自得到授权的出站电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="d3d81-116">Destination email systems verify that messages originate from authorized outbound email servers.</span></span> <span data-ttu-id="d3d81-117">如果您已熟悉 SPF，或者有一个简单的部署，则只需了解要针对 Office 365 在 DNS 的 SPF TXT 记录中包含的内容，您可以转到[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-117">If you are already familiar with SPF, or you have a simple deployment, and just need to know what to include in your SPF TXT record in DNS for Office 365, you can go to [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="d3d81-118">如果您没有完全托管在 Office 365 中的部署，或者您希望了解有关 SPF 的工作原理或如何针对 Office 365 解决 SPF 的详细信息，请继续阅读。</span><span class="sxs-lookup"><span data-stu-id="d3d81-118">If you do not have a deployment that is fully-hosted in Office 365, or you want more information about how SPF works or how to troubleshoot SPF for Office 365, keep reading.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3d81-119">以前，如果还使用了 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-119">Previously, you had to add a different SPF TXT record to your custom domain if you also used SharePoint Online.</span></span> <span data-ttu-id="d3d81-120">现在，不再需要这样做。</span><span class="sxs-lookup"><span data-stu-id="d3d81-120">This is no longer required.</span></span> <span data-ttu-id="d3d81-121">此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。</span><span class="sxs-lookup"><span data-stu-id="d3d81-121">This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder.</span></span> <span data-ttu-id="d3d81-122">虽然无需立即进行任何更改，但如果看到“查找次数太多”错误消息，请修改 SPF TXT 记录，如[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="d3d81-122">You do not need to make any changes immediately, but if you receive the "too many lookups" error, modify your SPF TXT record as described in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
     
## <a name="how-spf-works-to-prevent-spoofing-and-phishing-in-office-365"></a><span data-ttu-id="d3d81-123">SPF 在 Office 365 中防止欺骗和钓鱼的工作原理</span><span class="sxs-lookup"><span data-stu-id="d3d81-123">How SPF works to prevent spoofing and phishing in Office 365</span></span>
<span data-ttu-id="d3d81-124"><a name="HowSPFWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-124"></span></span>

<span data-ttu-id="d3d81-p107">SPF 确定是否允许发件人代表域发送邮件。如果不允许发件人发送邮件，即电子邮件无法通过接收服务器上的 SPF 检查，那么在该服务器上配置垃圾邮件策略会确定如何处理该邮件。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p107">SPF determines whether or not a sender is permitted to send on behalf of a domain. If the sender is not permitted to do so, that is, if the email fails the SPF check on the receiving server, the spam policy configured on that server determines what to do with the message.</span></span>
  
<span data-ttu-id="d3d81-p108">每个 SPF TXT 记录包含三个部分：SPF TXT 记录声明、允许从你的域和可以代表你的域发送邮件的外部域发送邮件的 IP 地址，以及强制规则。三个部分俱全，才算是有效的 SPF TXT 记录。本文介绍了 SPF TXT 记录的构成方式，以及使用 Office 365 服务的最佳做法。此外，还提供了说明链接，指导你如何使用你的域注册机构将记录发布到 DNS。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p108">Each SPF TXT record contains three parts: the declaration that it is an SPF TXT record, the IP addresses that are allowed to send mail from your domain and the external domains that can send on your domain's behalf, and an enforcement rule. You need all three in a valid SPF TXT record. This article describes how you form your SPF TXT record and provides best practices for working with the services in Office 365. Links to instructions on working with your domain registrar to publish your record to DNS are also provided.</span></span>
  
### <a name="spf-basics-ip-addresses-allowed-to-send-from-your-custom-domain"></a><span data-ttu-id="d3d81-131">SPF 基础知识：允许从自定义域发送邮件的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="d3d81-131">SPF basics: IP addresses allowed to send from your custom domain</span></span>
<span data-ttu-id="d3d81-132"><a name="SPFBasicsIPaddresses"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-132"></span></span>

<span data-ttu-id="d3d81-133">看看 SPF 规则的基本语法：</span><span class="sxs-lookup"><span data-stu-id="d3d81-133">Take a look at the basic syntax for an SPF rule:</span></span>
  
<span data-ttu-id="d3d81-134">v=spf1 \<IP\> \<强制规则\></span><span class="sxs-lookup"><span data-stu-id="d3d81-134">v=spf1 \<IP\> \<enforcement rule\></span></span>
  
<span data-ttu-id="d3d81-135">例如，假设 contoso.com 存在以下 SPF 规则：</span><span class="sxs-lookup"><span data-stu-id="d3d81-135">For example, let's say the following SPF rule exists for contoso.com:</span></span>
  
<span data-ttu-id="d3d81-136">v=spf1 \<IP 地址 #1\> \<IP 地址 #2\> \<IP 地址 #3\> \<强制规则\></span><span class="sxs-lookup"><span data-stu-id="d3d81-136">v=spf1 \<IP address #1\> \<IP address #2\> \<IP address #3\> \<enforcement rule\></span></span>
  
<span data-ttu-id="d3d81-137">在本示例中，SPF 规则指示接收电子邮件服务器仅为域 contoso.com 接受来自这些 IP 地址的邮件。</span><span class="sxs-lookup"><span data-stu-id="d3d81-137">In this example, the SPF rule instructs the receiving email server to only accept mail from these IP addresses for the domain contoso.com:</span></span>
  
- <span data-ttu-id="d3d81-138">IP 地址 #1</span><span class="sxs-lookup"><span data-stu-id="d3d81-138">IP address #1</span></span>
    
- <span data-ttu-id="d3d81-139">IP 地址 #2</span><span class="sxs-lookup"><span data-stu-id="d3d81-139">IP address #2</span></span>
    
- <span data-ttu-id="d3d81-140">IP 地址 #3</span><span class="sxs-lookup"><span data-stu-id="d3d81-140">IP address #3</span></span>
    
<span data-ttu-id="d3d81-p109">此 SPF 规则指示接收电子邮件服务器，如果邮件是从 contoso.com 发送，而不是从这三个 IP 地址中的任何一个发送，则接收服务器应将强制规则应用于邮件。强制规则通常是下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p109">This SPF rule tells the receiving email server that if a message comes from contoso.com, but not from one of these three IP addresses, the receiving server should apply the enforcement rule to the message. The enforcement rule is usually one of these options:</span></span>
  
- <span data-ttu-id="d3d81-p110">**硬失败。** 在邮件信封中用"硬失败"标记邮件，然后此类型的邮件遵照接收服务器的配置垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p110">**Hard fail.** Mark the message with 'hard fail' in the message envelope and then follow the receiving server's configured spam policy for this type of message.</span></span> 
    
- <span data-ttu-id="d3d81-p111">**软失败。** 在邮件信封中用"软失败"标记邮件。通常，电子邮件服务器配置为始终传递这些邮件。大多数最终用户不会看到此标记。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p111">**Soft fail.** Mark the message with 'soft fail' in the message envelope. Typically, email servers are configured to deliver these messages anyway. Most end users do not see this mark.</span></span> 
    
- <span data-ttu-id="d3d81-p112">**中性。** 不执行任何操作，即不标记邮件信封。通常将此选项保留用于测试，而且也很少使用。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p112">**Neutral.** Do nothing, that is, do not mark the message envelope. This is usually reserved for testing purposes and is rarely used.</span></span> 
    
<span data-ttu-id="d3d81-p113">下面的示例显示了 SPF 在不同情况中的工作原理。在这些示例中，contoso.com 是发件人，woodgrovebank.com 收件人。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p113">The following examples show how SPF works in different situations. In these examples, contoso.com is the sender and woodgrovebank.com is the receiver.</span></span>
  
### <a name="example-1-email-authentication-of-a-message-sent-directly-from-sender-to-receiver"></a><span data-ttu-id="d3d81-154">示例 1：直接从发送人发送到收件人的邮件的电子邮件身份验证</span><span class="sxs-lookup"><span data-stu-id="d3d81-154">Example 1: Email authentication of a message sent directly from sender to receiver</span></span>
<span data-ttu-id="d3d81-155"><a name="spfExample1"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-155"></span></span>

<span data-ttu-id="d3d81-156">SPF 最适用于从发件人到收件人的路径是直接路径的情况，例如：</span><span class="sxs-lookup"><span data-stu-id="d3d81-156">SPF works best when the path from sender to receiver is direct, for example:</span></span>
  
![关系图显示 SPF 如何在将电子邮件直接从服务器发送到服务器时对其进行身份验证。](media/835c20a7-ed4c-49c4-91fe-b8ebb3e452a1.jpg)
  
<span data-ttu-id="d3d81-158">Woodgrovebank.com 接收邮件时，如果 IP 地址 #1 在 contoso.com 的 SPF TXT 记录中，则消息通过 SPF 检查并进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d3d81-158">When woodgrovebank.com receives the message, if IP address #1 is in the SPF TXT record for contoso.com, the message passes the SPF check and is authenticated.</span></span>
  
### <a name="example-2-spoofed-sender-address-fails-the-spf-check"></a><span data-ttu-id="d3d81-159">示例 2：欺骗性发件人地址无法通过 SPF 检查</span><span class="sxs-lookup"><span data-stu-id="d3d81-159">Example 2: Spoofed sender address fails the SPF check</span></span>
<span data-ttu-id="d3d81-160"><a name="spfExample2"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-160"></span></span>

<span data-ttu-id="d3d81-161">假设欺诈者找到办法欺骗 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="d3d81-161">Suppose a phisher finds a way to spoof contoso.com:</span></span>
  
![关系图显示 SPF 如何在欺骗服务器发送电子邮件时对其进行身份验证。](media/235dac3d-cdc5-466e-86e0-37b5979de198.jpg)
  
<span data-ttu-id="d3d81-163">由于 IP 地址 #12 不在 contoso.com 的 SPF TXT 记录中，邮件无法通过 SPF 检查，收件人可以选择将其标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d3d81-163">Since IP address #12 is not in contoso.com's SPF TXT record, the message fails the SPF check and the receiver may choose to mark it as spam.</span></span>
  
### <a name="example-3-spf-and-forwarded-messages"></a><span data-ttu-id="d3d81-164">示例 3：SPF 和转发的邮件</span><span class="sxs-lookup"><span data-stu-id="d3d81-164">Example 3: SPF and forwarded messages</span></span>
<span data-ttu-id="d3d81-165"><a name="spfExample3"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-165"></span></span>

<span data-ttu-id="d3d81-p114">SPF 的一个缺点是它对转发的电子邮件不起作用。例如，假设 woodgrovebank.com 的用户已经设置了转发规则将所有电子邮件发送到 outlook.com 帐户：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p114">One drawback of SPF is that it doesn't work when an email has been forwarded. For example, suppose the user at woodgrovebank.com has set up a forwarding rule to send all email to an outlook.com account:</span></span>
  
![关系图显示转发邮件时，SPF 如何无法对电子邮件进行身份验证。](media/6e92acd6-463e-4a1b-8327-fb1cf861f356.jpg)
  
<span data-ttu-id="d3d81-p115">此邮件最初可以通过 woodgrovebank.com 的 SPF 检查，但无法通过 outlook.com 的 SPF 检查，因为 IP #25 不在 contoso.com 的 SPF TXT 记录中。Outlook.com 则可能将邮件标记为垃圾邮件。若要解决此问题，请结合使用 SPF 和其他电子邮件身份验证方法（如 DKIM 和 DMARC）。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p115">The message originally passes the SPF check at woodgrovebank.com but it fails the SPF check at outlook.com because IP #25 is not in contoso.com's SPF TXT record. Outlook.com might then mark the message as spam. To work around this problem, use SPF in conjunction with other email authentication methods such as DKIM and DMARC.</span></span>
  
### <a name="spf-basics-including-third-party-domains-that-can-send-mail-on-behalf-of-your-domain"></a><span data-ttu-id="d3d81-172">SPF 基础知识：包括可以代表您的域发送邮件的第三方域</span><span class="sxs-lookup"><span data-stu-id="d3d81-172">SPF basics: Including third-party domains that can send mail on behalf of your domain</span></span>
<span data-ttu-id="d3d81-173"><a name="SPFBasicsIncludes"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-173"></span></span>

<span data-ttu-id="d3d81-p116">除 IP 地址外，您还可以配置您的 SPF TXT 记录以包括域作为发件人。这些都作为"include"语句添加到 SPF TXT 记录中。例如，contoso.com 可能想要包括所有来自 contoso.net 以及它另外拥有的 contoso.org 的邮件服务器的 IP 地址。为了实现此目的，contoso.com 发布了 SPF TXT 记录，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p116">In addition to IP addresses, you can also configure your SPF TXT record to include domains as senders. These are added to the SPF TXT record as "include" statements. For example, contoso.com might want to include all of the IP addresses of the mail servers from contoso.net and contoso.org which it also owns. To do this, contoso.com publishes an SPF TXT record that looks like this:</span></span>
  
```
IN TXT "v=spf1 include:contoso.net include:contoso.org -all"
```

<span data-ttu-id="d3d81-178">当接收服务器在 DNS 中看到此记录时, 它还对 contoso.net 的 SPF TXT 记录执行 DNS 查找, 然后对 contoso.org 执行 DNS 查找。如果它在 contoso.net 或 contoso.org 的记录中找到附加的 include 语句, 它也会遵循这些语句。</span><span class="sxs-lookup"><span data-stu-id="d3d81-178">When the receiving server sees this record in DNS, it also performs a DNS lookup on the SPF TXT record for contoso.net and then for contoso.org. If it finds an additional include statement within the records for contoso.net or contoso.org, it will follow those too.</span></span> <span data-ttu-id="d3d81-179">为了帮助防止拒绝服务攻击，一封电子邮件的 DNS 查找的最大次数是 10 次。</span><span class="sxs-lookup"><span data-stu-id="d3d81-179">In order to help prevent denial of service attacks, the maximum number of DNS lookups for a single email message is 10.</span></span> <span data-ttu-id="d3d81-180">每个 include 语句都表示一个额外的 DNS 查找。</span><span class="sxs-lookup"><span data-stu-id="d3d81-180">Each include statement represents an additional DNS lookup.</span></span> <span data-ttu-id="d3d81-181">如果邮件超过 10 次限制，则该邮件将无法通过 SPF 检查。</span><span class="sxs-lookup"><span data-stu-id="d3d81-181">If a message exceeds the 10 limit, the message fails SPF.</span></span> <span data-ttu-id="d3d81-182">邮件达到此限制后, 取决于接收服务器的配置方式, 发件人可能会收到一条消息, 指出邮件生成的 "查找次数过多" 或 "邮件的最大跃点计数" (可能会在查找循环, 并超过了 DNS 超时值)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-182">Once a message reaches this limit, depending on the way the receiving server is configured, the sender may get a message that says the message generated "too many lookups" or that the "maximum hop count for the message has been exceeded" (which can happen when the lookups loop and surpass the DNS timeout).</span></span> <span data-ttu-id="d3d81-183">有关如何避免出现这种情况的提示，请参阅[故障排除：Office 365 中 SPF 的最佳实践](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-183">For tips on how to avoid this, see [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>
  
## <a name="requirements-for-your-spf-txt-record-and-office-365"></a><span data-ttu-id="d3d81-184">SPF TXT 记录和 Office 365 的要求</span><span class="sxs-lookup"><span data-stu-id="d3d81-184">Requirements for your SPF TXT record and Office 365</span></span>
<span data-ttu-id="d3d81-185"><a name="SPFReqsinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-185"></span></span>

<span data-ttu-id="d3d81-p118">如果你在设置 Office 365 时设置邮件，则表明已经创建了 SPF TXT 记录，将 Microsoft 邮件服务器标识为域的合法邮件源。此记录可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p118">If you set up mail when you set up Office 365, you already created an SPF TXT record that identifies the Microsoft messaging servers as a legitimate source of mail for your domain. This record probably looks like this:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d3d81-188">如果是完全托管的 Office 365 客户（即没有发送出站邮件的本地邮件服务器），这就是唯一需要为 Office 365 发布的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-188">If you're a fully-hosted Office 365 customer, that is, you have no on-premises mail servers that send outbound mail, this is the only SPF TXT record that you need to publish for Office 365.</span></span>
  
<span data-ttu-id="d3d81-189">如果您拥有混合部署（即您有部分邮箱为本地邮箱，有部分托管在 Office 365 中），或者如果您是 Exchange Online Protection (EOP) 独立客户（即您的组织使用 EOP 保护您的本地邮箱），您应该将每个本地边缘邮件服务器的出站 IP 地址添加到 DNS 的 SPF TXT 记录中。</span><span class="sxs-lookup"><span data-stu-id="d3d81-189">If you have a hybrid deployment (that is, you have some mailboxes on-premises and some hosted in Office 365), or if you're an Exchange Online Protection (EOP) standalone customer (that is, your organization uses EOP to protect your on-premises mailboxes), you should add the outbound IP address for each of your on-premises edge mail servers to the SPF TXT record in DNS.</span></span>
  
## <a name="form-your-spf-txt-record-for-office-365"></a><span data-ttu-id="d3d81-190">为 Office 365 构成您的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="d3d81-190">Form your SPF TXT record for Office 365</span></span>
<span data-ttu-id="d3d81-191"><a name="FormYourSPF"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-191"></span></span>

<span data-ttu-id="d3d81-p119">请参考本文中的语法信息，构成自定义域的 SPF TXT 记录。尽管还有其他语法选项本文未提及，这些都是最常用的选项。在构成记录后，需要在域注册机构更新记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p119">Use the syntax information in this article to form the SPF TXT record for your custom domain. Although there are other syntax options that are not mentioned here, these are the most commonly used options. Once you have formed your record, you need to update the record at your domain registrar.</span></span>
  
<span data-ttu-id="d3d81-p120">有关 Office 365 需要包含的域的信息，请参阅 [SPF 所需的外部 DNS 记录](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。使用[分步操作说明](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)更新域注册机构的 SPF (TXT) 记录。如果未列出你的注册机构，你将需要单独联系他们以了解如何更新你的记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p120">For information about the domains you will need to include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US). Use the [step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records for your domain registrar. If your registrar is not listed, you will need to contact them separately to learn how to update your record.</span></span> 
  
### <a name="spf-txt-record-syntax-for-office-365"></a><span data-ttu-id="d3d81-198">Office 365 的 SPF TXT 记录语法</span><span class="sxs-lookup"><span data-stu-id="d3d81-198">SPF TXT record syntax for Office 365</span></span>
<span data-ttu-id="d3d81-199"><a name="SPFSyntaxO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-199"></span></span>

<span data-ttu-id="d3d81-200">Office 365 的典型 SPF TXT 记录具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="d3d81-200">A typical SPF TXT record for Office 365 has the following syntax:</span></span>
  
```
v=spf1 [<ip4>|<ip6>:<IP address>] [include:<domain name>] <enforcement rule>
```

<span data-ttu-id="d3d81-201">例如：</span><span class="sxs-lookup"><span data-stu-id="d3d81-201">For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 include:spf.protection.outlook.com -all
```

<span data-ttu-id="d3d81-202">其中：</span><span class="sxs-lookup"><span data-stu-id="d3d81-202">where:</span></span>
  
- <span data-ttu-id="d3d81-p121">**v=spf1** 是必需的，用于将 TXT 记录定义为 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p121">**v=spf1** is required. This defines the TXT record as an SPF TXT record.</span></span> 
    
- <span data-ttu-id="d3d81-p122">**ip4** 表示您使用的是 IP 第 4 版地址。 **ip6** 表示您使用的是 IP 第 6 版地址。如果您使用的是 IPv6 IP 地址，则将 **ip4** 替换为本文示例中的 **ip6**。您还可以使用 CIDR 表示法指定 IP 地址范围，例如 **ip4:192.168.0.1/26**。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p122">**ip4** indicates that you are using IP version 4 addresses. **ip6** indicates that you are using IP version 6 addresses. If you are using IPv6 IP addresses, replace **ip4** with **ip6** in the examples in this article. You can also specify IP address ranges using CIDR notation, for example **ip4:192.168.0.1/26**.</span></span>
    
-  <span data-ttu-id="d3d81-p123">_IP address_ 是要添加到 SPF TXT 记录的 IP 地址。通常情况下，这是组织的出站邮件服务器的 IP 地址。可以列出多个出站邮件服务器。有关详细信息，请参阅 [示例：多个出站本地邮件服务器和 Office 365 的 SPF TXT 记录](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p123">_IP address_ is the IP address that you want to add to the SPF TXT record. Usually, this is the IP address of the outbound mail server for your organization. You can list multiple outbound mail servers. For more information, see [Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#ExampleSPFMultipleMailServerO365).</span></span>
    
-  <span data-ttu-id="d3d81-p124">_domain name_ 是您想要添加为合法发件人的域。有关 Office 365 应包含的域名列表，请参阅 [SPF 所需的外部 DNS 记录](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p124">_domain name_ is the domain you want to add as a legitimate sender. For a list of domain names you should include for Office 365, see [External DNS records required for SPF](https://support.office.com/article/External-Domain-Name-System-records-for-Office-365-c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
- <span data-ttu-id="d3d81-215">强制规则通常是下列之一：</span><span class="sxs-lookup"><span data-stu-id="d3d81-215">Enforcement rule is usually one of the following:</span></span>
    
  - <span data-ttu-id="d3d81-216">-all</span><span class="sxs-lookup"><span data-stu-id="d3d81-216">-all</span></span>
    
    <span data-ttu-id="d3d81-p125">表示硬失败。如果您知道您的域的所有授权 IP 地址，请在 SPF TXT 记录中列出这些地址并使用 -all（硬失败）限定符。此外，如果您仅使用 SPF，即不使用 DMARC 或 DKIM，您应使用 -all 限定符。我们建议您始终使用此限定符。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p125">Indicates hard fail. If you know all of the authorized IP addresses for your domain, list them in the SPF TXT record and use the -all (hard fail) qualifier. Also, if you are only using SPF, that is, you are not using DMARC or DKIM, you should use the -all qualifier. We recommend that you use always this qualifier.</span></span>
    
  - <span data-ttu-id="d3d81-221">~all</span><span class="sxs-lookup"><span data-stu-id="d3d81-221">~all</span></span>
    
    <span data-ttu-id="d3d81-p126">表示软失败。如果您不确定是否有 IP 地址的完整列表，那么您应该使用 ~all（软失败）限定符。此外，如果您使用的是 p=quarantine 或 p=reject 的 DMARC，则可以使用 ~all。否则，请使用 -all。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p126">Indicates soft fail. If you're not sure that you have the complete list of IP addresses, then you should use the ~all (soft fail) qualifier. Also, if you are using DMARC with p=quarantine or p=reject, then you can use ~all. Otherwise, use -all.</span></span>
    
  - <span data-ttu-id="d3d81-226">?all</span><span class="sxs-lookup"><span data-stu-id="d3d81-226">?all</span></span>
    
    <span data-ttu-id="d3d81-p127">表示中性。这在测试 SPF 时使用。不建议您在实时部署中使用此限定符。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p127">Indicates neutral. This is used when testing SPF. We do not recommend that you use this qualifier in your live deployment.</span></span>
    
### <a name="example-spf-txt-record-to-use-when-all-of-your-mail-is-sent-by-office-365"></a><span data-ttu-id="d3d81-230">示例：在所有邮件均由 Office 365 发送时使用的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="d3d81-230">Example: SPF TXT record to use when all of your mail is sent by Office 365</span></span>
<span data-ttu-id="d3d81-231"><a name="ExampleSPFNoSP"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-231"></span></span>

<span data-ttu-id="d3d81-232">如果所有邮件均由 Office 365 发送，请使用以下 SPF TXT 记录：</span><span class="sxs-lookup"><span data-stu-id="d3d81-232">If all of your mail is sent by Office 365, use this in your SPF TXT record:</span></span>
  
```
v=spf1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-a-hybrid-scenario-with-one-on-premises-exchange-server-and-office-365"></a><span data-ttu-id="d3d81-233">示例：包含一个本地 Exchange Server 和 Office 365 的混合应用场景的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="d3d81-233">Example: SPF TXT record for a hybrid scenario with one on-premises Exchange Server and Office 365</span></span>
<span data-ttu-id="d3d81-234"><a name="ExampleSPFHybridOneExchangeServer"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-234"></span></span>

<span data-ttu-id="d3d81-235">在混合环境中，如果本地 Exchange Server 的 IP 地址为 192.168.0.1，为了将 SPF 强制规则设置为硬故障，请构成如下 SPF TXT 记录：</span><span class="sxs-lookup"><span data-stu-id="d3d81-235">In a hybrid environment, if the IP address of your on-premises Exchange Server is 192.168.0.1, in order to set the SPF enforcement rule to hard fail, form the SPF TXT record as follows:</span></span>
  
```
v=spf1 ip4:192.168.0.1 include:spf.protection.outlook.com -all
```

### <a name="example-spf-txt-record-for-multiple-outbound-on-premises-mail-servers-and-office-365"></a><span data-ttu-id="d3d81-236">示例：多个出站本地邮件服务器和 Office 365 的 SPF TXT 记录</span><span class="sxs-lookup"><span data-stu-id="d3d81-236">Example: SPF TXT record for multiple outbound on-premises mail servers and Office 365</span></span>
<span data-ttu-id="d3d81-237"><a name="ExampleSPFMultipleMailServerO365"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-237"></span></span>

<span data-ttu-id="d3d81-p128">如果有多个出站邮件服务器，可以在 SPF TXT 记录中添加每个邮件服务器的 IP 地址，并用空格（后跟"ip4:"语句）分隔每个 IP 地址。例如：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p128">If you have multiple outbound mail servers, include the IP address for each mail server in the SPF TXT record and separate each IP address with a space followed by an "ip4:" statement. For example:</span></span>
  
```
v=spf1 ip4:192.168.0.1 ip4:192.168.0.2 ip4:192.168.0.3 include:spf.protection.outlook.com -all
```

## <a name="next-steps-set-up-spf-for-office-365"></a><span data-ttu-id="d3d81-240">后续步骤：为 Office 365 设置 SPF</span><span class="sxs-lookup"><span data-stu-id="d3d81-240">Next steps: Set up SPF for Office 365</span></span>
<span data-ttu-id="d3d81-241"><a name="SPFNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-241"></span></span>

<span data-ttu-id="d3d81-242">只要 SPF TXT 记录已构成，就请按[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)中的步骤操作，将记录添加到你的域中。</span><span class="sxs-lookup"><span data-stu-id="d3d81-242">Once you have formulated your SPF TXT record, follow the steps in [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) to add it to your domain.</span></span> 
  
<span data-ttu-id="d3d81-p129">尽管 SPF 旨在帮助防止欺骗，但还有 SPF 无法防止的欺骗技术。为了防止这些欺骗，在你设置 SPF 后，也应该为 Office 365 配置 DKIM 和 DMARC。请参阅[使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)了解入门知识。之后，请参阅[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p129">Although SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against. In order to protect against these, once you have set up SPF, you should also configure DKIM and DMARC for Office 365. To get started, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md). Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
  
## <a name="troubleshooting-best-practices-for-spf-in-office-365"></a><span data-ttu-id="d3d81-247">疑难解答：Office 365 中 SPF 的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="d3d81-247">Troubleshooting: Best practices for SPF in Office 365</span></span>
<span data-ttu-id="d3d81-248"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-248"></span></span>

<span data-ttu-id="d3d81-p130">只能为自定义域创建一个 SPF TXT 记录。创建多个记录会导致轮循机制发生，并且 SPF 也会失败。为了避免发生这种情况，可以为每个子域单独创建记录。例如，为 contoso.com 创建一个记录，为 bulkmail.contoso.com 创建另一个记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p130">You can only create one SPF TXT record for your custom domain. Creating multiple records causes a round robin situation and SPF will fail. To avoid this, you can create separate records for each subdomain. For example, create one record for contoso.com and another record for bulkmail.contoso.com.</span></span>
  
<span data-ttu-id="d3d81-p131">如果在传递邮件之前，电子邮件引起超过 10 次 DNS 查找，那么接收邮件服务器将使用永久性错误进行响应，也称为  _permerror_，并且会导致邮件无法通过 SPF 检查。接收服务器还可能使用未送达报告 (NDR) 进行响应，其中包含一个类似以下的错误：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p131">If an email message causes more than 10 DNS lookups before it is delivered, the receiving mail server will respond with a permanent error, also called a  _permerror_, and cause the message to fail the SPF check. The receiving server may also respond with a non-delivery report (NDR) that contains an error similar to these:</span></span>
  
- <span data-ttu-id="d3d81-255">邮件超出跃点计数。</span><span class="sxs-lookup"><span data-stu-id="d3d81-255">The message exceeded the hop count.</span></span>
    
- <span data-ttu-id="d3d81-256">邮件需要的查找次数过多。</span><span class="sxs-lookup"><span data-stu-id="d3d81-256">The message required too many lookups.</span></span>
    
## <a name="avoiding-the-too-many-lookups-error-when-you-use-third-party-domains-with-office-365"></a><span data-ttu-id="d3d81-257">在您结合使用第三方域和 Office 365 时，避免"查找次数过多"错误</span><span class="sxs-lookup"><span data-stu-id="d3d81-257">Avoiding the "too many lookups" error when you use third-party domains with Office 365</span></span>
<span data-ttu-id="d3d81-258"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-258"></span></span>

<span data-ttu-id="d3d81-p132">第三方域的一些 SPF TXT 记录指示接收服务器执行大量 DNS 查找。例如，在撰写本文时，Salesforce.com 的记录中包含 5 个 include 语句：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p132">Some SPF TXT records for third-party domains direct the receiving server to perform a large number of DNS lookups. For example, at the time of this writing, Salesforce.com contains 5 include statements in its record:</span></span>
  
```
v=spf1 include:_spf.google.com
include:_spfblock.salesforce.com
include:_qa.salesforce.com
include:_spfblock1.salesforce.com
include:spf.mandrillapp.com mx ~all
```

<span data-ttu-id="d3d81-p133">若要避免此错误，您可以实现一个允许任何人发送批量电子邮件的策略，例如，必须使用为此专门创建的一个子域。然后，您可以为包含批量电子邮件的子域定义不同的 SPF TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p133">To avoid the error, you can implement a policy where anyone sending bulk email, for example, has to use a subdomain specifically for this purpose. You then define a different SPF TXT record for the subdomain that includes the bulk email.</span></span>
  
 <span data-ttu-id="d3d81-p134">在某些情况下，如 salesforce.com 示例，您必须使用您的 SPF TXT 记录中的域，但在其他情况下，第三方可能已创建要用于此目的的一个子域。例如，exacttarget.com 已经创建了一个需要用于您的 SPF TXT 记录的子域：</span><span class="sxs-lookup"><span data-stu-id="d3d81-p134">In some cases, like the salesforce.com example, you have to use the domain in your SPF TXT record, but in other cases, the third-party may have already created a subdomain for you to use for this purpose. For example, exacttarget.com has created a subdomain that you need to use for your SPF TXT record:</span></span> 
  
```
cust-spf.exacttarget.com
```

<span data-ttu-id="d3d81-265">当您的 SPF TXT 记录中包含第三方域时，您需要与第三方进行确认要使用哪些域或子域以避免运行次数达到 10 次查找限制。</span><span class="sxs-lookup"><span data-stu-id="d3d81-265">When you include third-party domains in your SPF TXT record, you need to confirm with the third-party which domain or subdomain to use in order to avoid running into the 10 lookup limit.</span></span>
  
## <a name="how-to-view-your-current-spf-txt-record-and-determine-the-number-of-lookups-that-it-requires"></a><span data-ttu-id="d3d81-266">如何查看当前 SPF TXT 记录，并确定它需要的查找次数</span><span class="sxs-lookup"><span data-stu-id="d3d81-266">How to view your current SPF TXT record and determine the number of lookups that it requires</span></span>
<span data-ttu-id="d3d81-267"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-267"></span></span>

<span data-ttu-id="d3d81-p135">可以使用 nslookup 查看 DNS 记录，包括 SPF TXT 记录。或者，如果需要，还可以使用许多免费的联机工具来查看 SPF TXT 记录的内容。通过查看 SPF TXT 记录并遵循 include 语句链和重定向，可以确定记录需要的 DNS 查找次数。一些联机工具甚至会计算并显示查找次数。跟踪查找次数将有助于防止从组织发送的邮件触发接收服务器生成永久性错误（称为 permerror）。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p135">You can use nslookup to view your DNS records, including your SPF TXT record. Or, if you prefer, there are a number of free, online tools available that you can use to view the contents of your SPF TXT record. By looking at your SPF TXT record and following the chain of include statements and redirects, you can determine how many DNS lookups the record requires. Some online tools will even count and display these lookups for you. Keeping track of this number will help prevent messages sent from your organization from triggering a permanent error, called a permerror, from the receiving server.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="d3d81-273">详细信息</span><span class="sxs-lookup"><span data-stu-id="d3d81-273">For more information</span></span>
<span data-ttu-id="d3d81-274"><a name="SPFTroubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="d3d81-274"></span></span>

<span data-ttu-id="d3d81-p136">需要有关添加 SPF TXT 记录的？我们提供有关更新多种流行域注册机构的 SPF (TXT) 记录的[分步操作说明](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404)。[反垃圾邮件邮件头](anti-spam-message-headers.md)包括 Office 365 进行 SPF 检查时使用的语法和标头字段。</span><span class="sxs-lookup"><span data-stu-id="d3d81-p136">Need help adding the SPF TXT record? [Step-by-step instructions](https://office.microsoft.com/en-us/office365-suite-help/create-dns-records-for-office-365-HA102851099.aspx?CTT=5&amp;origin=HA102818404) for updating SPF (TXT) records at a variety of popular domain registrars is available. [Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for SPF checks.</span></span> 
  

