---
title: 抵制发送到 Office 365 的垃圾邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
ms.collection:
- M365-security-compliance
description: Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。跨 Microsoft 电子邮件平台应用 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼筛选技术，以便为用户提供整个网络的最新反垃圾和反网络钓鱼工具及创新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。
ms.openlocfilehash: 510b04d3f111c269d5f8579abcc809ddc283636b
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692851"
---
# <a name="fighting-junk-email-sent-to-office-365"></a><span data-ttu-id="f2600-105">抵制发送到 Office 365 的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="f2600-105">Fighting junk email sent to Office 365</span></span>

<span data-ttu-id="f2600-p102">Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。跨 Microsoft 电子邮件平台应用 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼筛选技术，以便为用户提供整个网络的最新反垃圾和反网络钓鱼工具及创新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。</span><span class="sxs-lookup"><span data-stu-id="f2600-p102">Microsoft's email safety roadmap involves an unmatched cross-product approach. Exchange Online Protection (EOP) anti-spam and anti-phishing filtering technology is being applied across Microsoft's email platforms to provide users with the latest anti-spam and anti-phishing tools and innovations throughout the network. The goal for EOP is to offer a comprehensive and usable email service that helps detect and protect users from junk email, fraudulent email threats (phishing), and malware.</span></span>
  
## <a name="the-challenge"></a><span data-ttu-id="f2600-109">挑战</span><span class="sxs-lookup"><span data-stu-id="f2600-109">The challenge</span></span>

<span data-ttu-id="f2600-p103">无论对于客户，还是对于营销人员、支持人员、销售组织和各种规模的企业，电子邮件已经成为一个重要的通信工具。随着电子邮件的普及，电子邮件滥用的问题也日趋严重。无人监控的垃圾邮件会阻塞收件箱和网络、影响用户满意度，并阻碍合法电子邮件通信的有效性。这就是 Microsoft 仍继续致力于反垃圾邮件技术的原因。简单地说，它从包含和筛选垃圾邮件开始。</span><span class="sxs-lookup"><span data-stu-id="f2600-p103">Email has become an important communication tool not only for consumers but also for marketers, support staff, sales organizations, and businesses of all sizes. As email use has grown, so has email abuse. Unmonitored junk email can clog inboxes and networks, impact user satisfaction, and hamper the effectiveness of legitimate email communications. That's why Microsoft continues to invest in anti-spam technologies. Simply put, it starts by containing and filtering junk email.</span></span> 
  
## <a name="our-efforts"></a><span data-ttu-id="f2600-115">我们的努力</span><span class="sxs-lookup"><span data-stu-id="f2600-115">Our efforts</span></span>

<span data-ttu-id="f2600-116">EOP 提供了大量步骤，以最大程度减少垃圾邮件对我们用户的电子邮件体验产生的负面影响。</span><span class="sxs-lookup"><span data-stu-id="f2600-116">EOP offers a number of steps to minimize the negative impact junk email has on our users' email experience.</span></span>
  
### <a name="exchange-online-protection-technology"></a><span data-ttu-id="f2600-117">Exchange Online Protection 技术</span><span class="sxs-lookup"><span data-stu-id="f2600-117">Exchange Online Protection technology</span></span>

<span data-ttu-id="f2600-p104">为了帮助减少垃圾电子邮件，包含垃圾邮件保护的 EOP 使用专有的 EOP 筛选技术，以标识垃圾邮件，并将其从合法邮件分离出来。EOP 内容筛选器从我们的消费者平台 (Outlook.com) 了解已知的垃圾邮件、网络钓鱼威胁和用户反馈。这些数据类型帮助定型 EOP 技术，以识别合法的电子邮件和垃圾邮件，是发件人信誉的关键输入。垃圾邮件分类程序中正在进行的、来自 EOP 用户的反馈可以帮助确保 EOP 技术经过不断的定型和提高。</span><span class="sxs-lookup"><span data-stu-id="f2600-p104">To help reduce junk email, EOP includes junk email protection using proprietary EOP filtering technologies which screen email to identify and separate junk email from legitimate email. The EOP content filter learns from known spam and phishing threats and user feedback from our consumer platform, Outlook.com. These types of data help train EOP technologies to recognize legitimate email and junk email and are key inputs into sender reputation. Ongoing feedback from EOP users in the junk email classification program helps ensure that the EOP technologies are continually trained and improved.</span></span>
  
#### <a name="how-does-eop-work"></a><span data-ttu-id="f2600-122">EOP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="f2600-122">How does EOP work?</span></span>

<span data-ttu-id="f2600-p105">当外部用户向 EOP 用户发送电子邮件时，EOP 筛选技术将评估邮件的内容，并基于该邮件是垃圾邮件的概率为其分配一个等级。该分级作为一个名为"垃圾邮件可信度" (SCL) 的邮件属性在邮件中存储。当邮件发送到 EOP 中的其他反垃圾邮件保护层时，SCL 等级保留在电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="f2600-p105">When an external user sends an email message to an EOP user, EOP filtering technologies evaluate the content of the message and assigns a rating to the message based on the probability that the message is junk email. This rating is stored as a message property called a Spam Confidence Level (SCL) within the message itself. The SCL rating stays with the message as it is sent to other anti-spam protection layers within EOP.</span></span> 
  
<span data-ttu-id="f2600-p106">设置 EOP 内的规则以处理具有多种 SCL 等级的电子邮件。如果邮件 SCL 的等级大于某一阈值，则被视为垃圾邮件。该邮件将被隔离或传送到用户垃圾邮件文件夹，这取决于系统管理员如何配置垃圾邮件传送选项。</span><span class="sxs-lookup"><span data-stu-id="f2600-p106">Rules inside EOP are set to handle email messages with various SCL ratings. If a message has an SCL rating higher than a certain threshold, it is considered spam. The message will be quarantined or delivered to the user's junk mail folder depending on how the system administrator configures the spam delivery option.</span></span>
  
#### <a name="eop-filters"></a><span data-ttu-id="f2600-129">EOP 筛选器</span><span class="sxs-lookup"><span data-stu-id="f2600-129">EOP filters</span></span>

<span data-ttu-id="f2600-130">除了反垃圾邮件筛选技术以外，EOP 还允许系统管理员设置筛选器级别，以进一步自定义向他们的用户帐户的电子邮件传送。</span><span class="sxs-lookup"><span data-stu-id="f2600-130">In addition to the anti-spam filtering technologies, EOP also gives the system administrator the ability to set filter levels to further customize the delivery of email to their user accounts.</span></span> <span data-ttu-id="f2600-131">管理员可以轻松地将发件人或域名添加到安全发件人和域列表，以便来自该发件人或域的电子邮件永远不会被视为垃圾邮件，而无需考虑邮件内容。</span><span class="sxs-lookup"><span data-stu-id="f2600-131">Administrators can easily add a sender or domain name to the Safe Senders and Domains List so that the email from that sender or domain is never treated as junk regardless of the content of the message.</span></span> <span data-ttu-id="f2600-132">有关信息, 请参阅[Exchange Online 中的安全发件人和阻止的发件人列表](safe-sender-and-blocked-sender-lists-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="f2600-132">For information, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md).</span></span>
  
### <a name="phishing-protection"></a><span data-ttu-id="f2600-133">网络钓鱼防护</span><span class="sxs-lookup"><span data-stu-id="f2600-133">Phishing protection</span></span>

<span data-ttu-id="f2600-p108">网络钓鱼（Phishing，读作"fishing"）是一种身份盗用的形式，也是互联网增长最快的威胁之一。您通常可以标识出钓鱼邮件（当它请求个人或财务信息，或通过包含一个网站的链接来请求该类信息）。EOP 提供钓鱼保护作为 EOP 筛选技术的专有部分。EOP 筛选技术分析电子邮件，帮助检测欺诈性链接或欺骗域，以保护用户免受这些在线诈骗类型的侵扰。</span><span class="sxs-lookup"><span data-stu-id="f2600-p108">Phishing (pronounced "fishing") is a form of identity theft and one of the fastest growing threats on the Internet. You can often identify a phishing message when it requests personal or financial information or includes a link to a website that requests such information. EOP offers phishing protection as part of the proprietary EOP filtering technologies. EOP filtering technologies analyze email to help detect fraudulent links or spoofed domains to help protect users from these types of online scams.</span></span>
  
#### <a name="how-does-phishing-protection-work"></a><span data-ttu-id="f2600-138">网络钓鱼防护的工作原理</span><span class="sxs-lookup"><span data-stu-id="f2600-138">How does phishing protection work?</span></span>

<span data-ttu-id="f2600-p109">通常会发送一个网络钓鱼邮件，此邮件包含一个链接，一旦点击，该链接将重定向用户至看起来是有效的欺诈性网站（看起来像是您的财务机构或在线服务）。该网络钓鱼网站通常提示用户输入个人信息（如用户姓名、密码和身份证号）。在网络钓鱼站点输入的任何信息，会帮助网络钓鱼者窃取您的身份。网络钓鱼者通过使用已知的、受信任的品牌名称和标志使其显得合法化。EOP 提供的网络钓鱼筛选技术检查邮件中潜在的网络钓鱼特性。如果找到，该电子邮件将被移动到垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="f2600-p109">Often a phishing email will be sent containing a link, once clicked the link redirects users to a fraudulent web site that appears valid (like your financial institution or online service). This phishing site usually prompts users to enter personal information like user names, passwords, and social security numbers. Any information you enter on the phishing site helps the phisher steal your identity. By using well-known trusted brand names and logos, phishers are able to appear legitimate. Phishing filter technology offered in EOP checks for potential phishing characteristics in email. If found, the email is moved to the Junk folder.</span></span>
  
<span data-ttu-id="f2600-145">Microsoft 重点关注反钓鱼技术的两个方面：第一，防止网络钓鱼电子邮件到达我们的用户，第二，帮助消除用户被欺诈性电子邮件和网站欺骗的可能性。</span><span class="sxs-lookup"><span data-stu-id="f2600-145">Microsoft is focusing its anti-phishing technology efforts on two fronts: first by helping to prevent phishing email messages from reaching our users and second by helping to eliminate the possibility of users being deceived by spoofed emails and web sites.</span></span> 
  
> [!TIP]
> <span data-ttu-id="f2600-146">当用户访问已知或潜在的钓鱼网站时，Internet Explorer 版本 7 及以上版本将阻止或警告用户，这样用户就不会被骗提供个人信息。[确保您有 Internet Explorer 的最新版本](https://www.microsoft.com/windows/ie/default.mspx)。</span><span class="sxs-lookup"><span data-stu-id="f2600-146">Internet Explorer version 7 and above will block or warn users when they visit known or potential phishing sites so that they aren't tricked into providing personal information.[Make sure that you have the latest version of Internet Explorer](https://www.microsoft.com/windows/ie/default.mspx).</span></span> 
  
#### <a name="authentication"></a><span data-ttu-id="f2600-147">身份验证</span><span class="sxs-lookup"><span data-stu-id="f2600-147">Authentication</span></span>

<span data-ttu-id="f2600-p110">域欺骗是一种模仿合法电子邮件地址以使其看起来合法的欺骗方式。恶意的个人或组织在网络钓鱼诈骗中使用诈骗来引诱用户泄漏敏感的个人信息。披露此类信息可能会导致身份被盗和其他类型的欺诈。</span><span class="sxs-lookup"><span data-stu-id="f2600-p110">Domain spoofing is a way of imitating a legitimate email address to make fraudulent email look legitimate. Spoofing is used by malicious individuals or organizations in phishing scams to lure people into divulging sensitive personal information. Disclosure of such information can lead to identify theft and other types of fraud.</span></span>
  
<span data-ttu-id="f2600-p111">EOP 使用发件人保护架构框架 (SPF)、域密钥识别邮件 (DKIM)、基于域的邮件身份验证、举报和一致性 (DMARC) 和其他隐式身份验证，以验证邮件的实际来源域与其声称的来源域相同。我们建议所有发件人使用 SPF 和 DKIM 保护其收件人免受垃圾邮件和钓鱼欺诈的侵害。此外，我们建议发件人考虑发布 DMARC 以拒绝或隔离未经身份验证的发件人发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="f2600-p111">EOP uses Sender Protection Framework (SPF), DomainKeys Identified Mail (DKIM), and Domain-based Message Authentication, Reporting, and Conformance (DMARC), and other implicit authentications to verify that messages came from the domain they claim to come from. We recommend that all senders use SPF and DKIM to protect their recipients from junk email and phishing scams. We recommend senders consider publishing a DMARC to reject or quarantine mail sent from unauthorized senders.</span></span>
  
- <span data-ttu-id="f2600-154">若要了解有关 SPF 的详细信息，请参阅 [RFC 7208](https://tools.ietf.org/html/rfc7208) 和 [发件人策略框架](http://www.openspf.org/)。</span><span class="sxs-lookup"><span data-stu-id="f2600-154">To learn more about SPF, see [RFC 7208](https://tools.ietf.org/html/rfc7208) and [Sender Policy Framework](http://www.openspf.org/).</span></span>
    
- <span data-ttu-id="f2600-155">若要了解有关 DKIM 的详细信息，请参阅 [RFC 6376](https://tools.ietf.org/html/rfc6376) 和 [DKIM.org](http://dkim.org/)。</span><span class="sxs-lookup"><span data-stu-id="f2600-155">To learn more about DKIM, see [RFC 6376](https://tools.ietf.org/html/rfc6376) and [DKIM.org](http://dkim.org/).</span></span>
    
- <span data-ttu-id="f2600-156">若要了解有关 DMARC 的详细信息，请参阅 [DMARC.org](https://dmarc.org/)。</span><span class="sxs-lookup"><span data-stu-id="f2600-156">To learn more about DMARC, see [DMARC.org](https://dmarc.org/).</span></span>
    
### <a name="legislation"></a><span data-ttu-id="f2600-157">立法</span><span class="sxs-lookup"><span data-stu-id="f2600-157">Legislation</span></span>

<span data-ttu-id="f2600-p112">在 Microsoft，我们认为新技术开发和自我管理需要有效的政府政策和法律体系的支持。全球垃圾邮件的激增促使许多立法机构规范商业电子邮件。现在，很多国家/地区都出台了反垃圾邮件法。美国已针对垃圾邮件的管理制定了相应的联邦法律，同时各个州也制定了相关的法律，这种互补措施有助于减少垃圾邮件，同时确保合法的电子商务能够正常开展。CAN-SPAM Act（反垃圾邮件法）为抵制欺诈和欺骗性电子邮件提供了更有力的法律武器。</span><span class="sxs-lookup"><span data-stu-id="f2600-p112">At Microsoft, we believe that the development of new technologies and self-regulation requires the support of effective government policy and legal frameworks. The worldwide spam proliferation has spurred numerous legislative bodies to regulate commercial email. Many countries/regions now have spam-fighting laws in place. The United States has both federal and state laws governing spam, and this complementary approach is helping to curtail spam while enabling legitimate e-commerce to prosper. The CAN-SPAM Act expands the tools available for curbing fraudulent and deceptive email messages.</span></span>
  

