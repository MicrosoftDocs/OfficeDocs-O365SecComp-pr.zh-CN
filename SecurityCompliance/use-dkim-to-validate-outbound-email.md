---
title: 在 Office 365 中使用自定义域中的电子邮件 DKIM
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 摘要： 本文介绍了如何结合使用域密钥识别邮件 (DKIM) 和 Office 365，从而确保目标电子邮件系统信任从自定义域发送的邮件。
ms.openlocfilehash: 98446410ff51e95be23f07bb84de3654cd84f091
ms.sourcegitcommit: a8049055a48375bee7e6ed81fafcb27a7b2fcdff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "35854756"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="a759e-103">使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件</span><span class="sxs-lookup"><span data-stu-id="a759e-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="a759e-104">**摘要:** 本文介绍如何使用域密钥识别的邮件 (DKIM) 和 Office 365, 以确保目标电子邮件系统信任从自定义域发送出站的邮件。</span><span class="sxs-lookup"><span data-stu-id="a759e-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span> 
  
<span data-ttu-id="a759e-p101">除了使用 SPF 和 DMARC 之外，还应使用 DKIM，这样有助于防止欺骗程序假冒从你的域发送邮件。可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。这听起来很复杂，其实不然。配置 DKIM 时，可以使用加密身份验证，授权你的域将域名与电子邮件相关联，或在电子邮件中签署域名。接收从你的域发送的电子邮件的电子邮件系统可以使用此数字签名来确定收到的传入电子邮件是否合法。</span><span class="sxs-lookup"><span data-stu-id="a759e-p101">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain. DKIM lets you add a digital signature to email messages in the message header. Sounds complicated, but it's really not. When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication. Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="a759e-p102">一般来说，可以使用私钥在域的传出电子邮件中加密邮件头。向域 DNS 记录发布公钥，然后接收服务器可用来解码签名。接收服务器使用公钥来确认邮件是否确实是你发送的，而不是假冒你的域的欺骗程序发送的。</span><span class="sxs-lookup"><span data-stu-id="a759e-p102">Basically, you use a private key to encrypt the header in your domain's outgoing email. You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature. They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="a759e-113">Office 365 自动为初始域设置 DKIM。</span><span class="sxs-lookup"><span data-stu-id="a759e-113">Office 365 automatically sets up DKIM for initial domains.</span></span> <span data-ttu-id="a759e-114">初始域是指 Office 365 在你注册此服务时为你创建的域，例如 contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="a759e-114">The initial domain is the domain that Office 365 created for you when you signed up with the service, for example, contoso.onmicrosoft.com.</span></span> <span data-ttu-id="a759e-115">无需执行任何操作，即可为初始域设置 DKIM。</span><span class="sxs-lookup"><span data-stu-id="a759e-115">You don't need to do anything to set up DKIM for your initial domain.</span></span> <span data-ttu-id="a759e-116">有关域的详细信息, 请参阅[域 FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="a759e-116">For more information about domains, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
<span data-ttu-id="a759e-p104">也可以选择不为自定义域配置 DKIM。如果你没有为自定义域设置 DKIM，Office 365 会创建私钥和公钥对，启用 DKIM 签名，然后为自定义域配置 Office 365 默认策略。虽然这足以覆盖大多数 Office 365 客户，但在以下情况下，仍应为自定义域手动配置 DKIM：</span><span class="sxs-lookup"><span data-stu-id="a759e-p104">You can choose to do nothing about DKIM for your custom domain too. If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain. While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="a759e-120">在 Office 365 中拥有多个自定义域</span><span class="sxs-lookup"><span data-stu-id="a759e-120">You have more than one custom domain in Office 365</span></span>
    
- <span data-ttu-id="a759e-121">您同时要设置 DMARC（推荐）</span><span class="sxs-lookup"><span data-stu-id="a759e-121">You're going to set up DMARC too (recommended)</span></span>
    
- <span data-ttu-id="a759e-122">您想要控制您的私钥</span><span class="sxs-lookup"><span data-stu-id="a759e-122">You want control over your private key</span></span>
    
- <span data-ttu-id="a759e-123">您要自定义 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a759e-123">You want to customize your CNAME records</span></span>
    
- <span data-ttu-id="a759e-124">你想为源自第三方域的电子邮件设置 DKIM 密钥，例如，如果你使用第三方群发邮件程序。</span><span class="sxs-lookup"><span data-stu-id="a759e-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>
    
<span data-ttu-id="a759e-125">本文内容：</span><span class="sxs-lookup"><span data-stu-id="a759e-125">In this article:</span></span>
  
- [<span data-ttu-id="a759e-126">DKIM 如何能够比 SPF 更有效地防止 Office 365 中的恶意欺骗现象</span><span class="sxs-lookup"><span data-stu-id="a759e-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)
    
- [<span data-ttu-id="a759e-127">在 Office 365 中手动设置 DKIM 需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="a759e-127">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)
    
- [<span data-ttu-id="a759e-128">在 Office 365 中为多个自定义域配置 DKIM 的具体步骤</span><span class="sxs-lookup"><span data-stu-id="a759e-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)
    
- [<span data-ttu-id="a759e-129">在 Office 365 中为自定义域禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="a759e-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)
    
- [<span data-ttu-id="a759e-130">DKIM 和 Office 365 的默认行为</span><span class="sxs-lookup"><span data-stu-id="a759e-130">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)
    
- [<span data-ttu-id="a759e-131">设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件</span><span class="sxs-lookup"><span data-stu-id="a759e-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)
    
- [<span data-ttu-id="a759e-132">后续步骤：为 Office 365 设置 DKIM 之后</span><span class="sxs-lookup"><span data-stu-id="a759e-132">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)
    
## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="a759e-133">DKIM 如何能够比 SPF 更有效地防止 Office 365 中的恶意欺骗现象</span><span class="sxs-lookup"><span data-stu-id="a759e-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="a759e-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-134"></span></span>

<span data-ttu-id="a759e-p105">虽然 SPF 将信息添加到邮件信封中，但实际上是 DKIM 在邮件头中加密签名。当你转发邮件时，转发服务器可能会截除邮件信封部分。由于数字签名作为电子邮件头的一部分与电子邮件同时存在，因此即使当邮件进行了转发，DKIM 也仍在运行，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a759e-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![关系图显示转发邮件在 SPF 检查失败的情况下传递 DKIM 身份验证](media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="a759e-p106">在此示例中，如果您只发布了域的一条 SPF TXT 记录，收件人的邮件服务器可能已将您的电子邮件标记为垃圾邮件，并生成一个误报结果。在这种情况下，添加 DKIM 可以减少误报垃圾邮件报告。由于 DKIM 依赖于公钥加密（而不仅仅对 IP 地址加密）进行身份验证，DKIM 被认为是比 SPF 更强大的身份验证形式。建议在部署中同时使用 SPF、DKIM 以及 DMARC。</span><span class="sxs-lookup"><span data-stu-id="a759e-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="a759e-p107">具体功能：DKIM 使用私钥将加密的签名插入邮件头。在邮件头中，将签名域或出站域作为 **d =** 字段中的值插入。然后，验证域或收件人的域使用 **d =** 字段从 DNS 中查找公钥，对邮件进行身份验证。如果邮件已经过验证，则 DKIM 检查通过。</span><span class="sxs-lookup"><span data-stu-id="a759e-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span> 
  
## <a name="what-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="a759e-147">在 Office 365 中手动设置 DKIM 需要执行的操作</span><span class="sxs-lookup"><span data-stu-id="a759e-147">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="a759e-148"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-148"></span></span>

<span data-ttu-id="a759e-149">要配置 DKIM，您需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a759e-149">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="a759e-150">在 DNS 中发布自定义域的两条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a759e-150">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
    
- [<span data-ttu-id="a759e-151">在 Office 365 中为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="a759e-151">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)
    
### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="a759e-152">在 DNS 中发布自定义域的两条 CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a759e-152">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="a759e-153"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-153"></span></span>

<span data-ttu-id="a759e-154">对于您要为其在 DNS 中添加 DKIM 签名的每个域，您需要发布两条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a759e-154">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span> <span data-ttu-id="a759e-155">DNS 使用 CNAME 记录指定域的 规范名称是否是其他域名的别名。</span><span class="sxs-lookup"><span data-stu-id="a759e-155">A CNAME record is used by DNS to specify that the canonical name of a domain is an alias for another domain name.</span></span> <span data-ttu-id="a759e-156">应在公开提供的 DNS 服务器上为自定义的域创建 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a759e-156">The CNAME records should be created on the publicly available DNS servers for your customized domains.</span></span> <span data-ttu-id="a759e-157">DNS 中的 CNAME 记录将指向已在 Microsoft DNS 服务器上的 Office 365 的 DNS 中创建的记录。</span><span class="sxs-lookup"><span data-stu-id="a759e-157">The CNAME records in your DNS will point to already created A records that exist in DNS on the Microsoft DNS servers for Office 365.</span></span>
  
 <span data-ttu-id="a759e-p109">Office 365 使用你创建的两条记录执行自动密钥轮替。如果在 Office 365 中除了初始域外你还预配了自定义域，必须为额外配置的每个域发布两条 CNAME 记录。因此，如果有两个域，就必须发布两条额外的 CNAME 记录，依此类推。</span><span class="sxs-lookup"><span data-stu-id="a759e-p109">Office 365 performs automatic key rotation using the two records that you establish. If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>
  
<span data-ttu-id="a759e-161">对 CNAME 记录使用以下格式。</span><span class="sxs-lookup"><span data-stu-id="a759e-161">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a759e-162">如果你是我们的一家 GCC 高级客户, 则会以不同的方式计算_domainGuid_ !</span><span class="sxs-lookup"><span data-stu-id="a759e-162">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="a759e-163">而不是查找您的_initialDomain_的 MX 记录来计算_domainGuid_, 而是直接从自定义域进行计算。</span><span class="sxs-lookup"><span data-stu-id="a759e-163">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="a759e-164">例如, 如果您的自定义域是 "contoso.com", 则 domainGuid 将变成 "contoso-com", 任何句点都将替换为短划线。</span><span class="sxs-lookup"><span data-stu-id="a759e-164">For example, if your customized domain is “contoso.com” your domainGuid becomes “contoso-com”, any periods are replaced with a dash.</span></span> <span data-ttu-id="a759e-165">因此, 无论您的 initialDomain 指向什么 MX 记录, 您都将始终使用上面的方法来计算在您的 CNAME 记录中使用的 domainGuid。</span><span class="sxs-lookup"><span data-stu-id="a759e-165">So, regardless of what MX record your initialDomain points to, you’ll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

  
```
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="a759e-166">其中：</span><span class="sxs-lookup"><span data-stu-id="a759e-166">Where:</span></span>
  
- <span data-ttu-id="a759e-167">对于 Office 365，选择器将始终为"selector1"或"selector2"。</span><span class="sxs-lookup"><span data-stu-id="a759e-167">For Office 365, the selectors will always be "selector1" or "selector2".</span></span> 
    
- <span data-ttu-id="a759e-168">_domainGUID_与在 mail.protection.outlook.com 之前出现的自定义域的自定义 MX 记录中的_domainGUID_相同。</span><span class="sxs-lookup"><span data-stu-id="a759e-168">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="a759e-169">例如, 在域 contoso.com 的以下 MX 记录中, _domainGUID_是 contoso-com:</span><span class="sxs-lookup"><span data-stu-id="a759e-169">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span> 
    
    ```
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="a759e-170">_initialDomain_ 是你注册 Office 365 时所使用的域。</span><span class="sxs-lookup"><span data-stu-id="a759e-170">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="a759e-171">初始域始终以 onmicrosoft.com 结束。</span><span class="sxs-lookup"><span data-stu-id="a759e-171">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="a759e-172">有关确定初始域的信息, 请参阅[域 FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="a759e-172">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
    
<span data-ttu-id="a759e-173">例如，如果你有一个初始域 cohovineyardandwinery.onmicrosoft.com，以及两个自定义域 cohovineyard.com 和 cohowinery.com，那么你需要为额外配置的每个域设置两条 CNAME 记录，总共四条 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a759e-173">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```
Host name:          selector1._domainkey
Points to address or value: **selector1-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: **selector2-cohovineyard-com**._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: **selector1-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
 
Host name:          selector2._domainkey
Points to address or value: **selector2-cohowinery-com**._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="a759e-174">在 Office 365 中为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="a759e-174">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="a759e-175"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-175"></span></span>

<span data-ttu-id="a759e-176">在 DNS 中发布了 CNAME 记录后，就可以通过 Office 365 启用 DKIM 签名。</span><span class="sxs-lookup"><span data-stu-id="a759e-176">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="a759e-177">您可以通过 Microsoft 365 管理中心或使用 PowerShell 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a759e-177">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="a759e-178">通过管理中心为您的自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="a759e-178">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="a759e-179">[登录到 Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)</span><span class="sxs-lookup"><span data-stu-id="a759e-179">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 
    
2. <span data-ttu-id="a759e-180">依次选择左上角的应用启动器图标和" **管理员**"。</span><span class="sxs-lookup"><span data-stu-id="a759e-180">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>
    
3. <span data-ttu-id="a759e-181">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a759e-181">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>
    
4. <span data-ttu-id="a759e-182">依次转到" **保护**"\>" **dkim**"。</span><span class="sxs-lookup"><span data-stu-id="a759e-182">Go to **Protection** \> **dkim**.</span></span>
    
5. <span data-ttu-id="a759e-p114">选择要对其启用 DKIM 的域，然后对" **对此域的邮件进行 DKIM 签名**"选择" **启用**"。为每个自定义域重复执行这一步。</span><span class="sxs-lookup"><span data-stu-id="a759e-p114">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>
    
#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="a759e-185">使用 PowerShell 为自定义域启用 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="a759e-185">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="a759e-186">[连接到 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a759e-186">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="a759e-187">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a759e-187">Run the following command:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName <domain> -Enabled $true
    ```

   <span data-ttu-id="a759e-188">其中, _domain_是您要为其启用 DKIM 签名的自定义域的名称。</span><span class="sxs-lookup"><span data-stu-id="a759e-188">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span> 
    
   <span data-ttu-id="a759e-189">例如，对于域 contoso.com：</span><span class="sxs-lookup"><span data-stu-id="a759e-189">For example, for the domain contoso.com:</span></span>
    
    ```
    New-DkimSigningConfig -DomainName contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="a759e-190">确认已为 Office 365 正确配置 DKIM 签名</span><span class="sxs-lookup"><span data-stu-id="a759e-190">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="a759e-p115">请等待几分钟，然后按以下步骤操作，确认是否已正确配置 DKIM。这样就有时间将域的 DKIM 信息分布到整个网络了。</span><span class="sxs-lookup"><span data-stu-id="a759e-p115">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="a759e-193">从 Office 365 中启用了 DKIM 的域帐户发送一封邮件到其他电子邮件帐户（如 outlook.com 或 Hotmail.com）。</span><span class="sxs-lookup"><span data-stu-id="a759e-193">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
    
- <span data-ttu-id="a759e-p116">不要将 aol.com 帐户用于测试目的。如果 SPF 检查通过，AOL 可能会跳过 DKIM 检查。这会使测试无效。</span><span class="sxs-lookup"><span data-stu-id="a759e-p116">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>
    
- <span data-ttu-id="a759e-p117">打开邮件，然后查看邮件头。查看邮件头的说明因邮件客户端而异。有关在 Outlook 中查看邮件头的说明，请参阅[查看电子邮件头](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C)。</span><span class="sxs-lookup"><span data-stu-id="a759e-p117">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="a759e-p118">进行了 DKIM 签名的邮件将包含主机名以及您在发布 CNAME 条目时定义的域。该邮件如下例所示：</span><span class="sxs-lookup"><span data-stu-id="a759e-p118">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span> 
    
    ```
    From: Example User <example@contoso.com> 
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
        s=selector1; d=contoso.com; t=1429912795; 
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
        bh=<body hash>; 
        b=<signed field>;
    ```

- <span data-ttu-id="a759e-p119">查找身份验证结果标头。尽管每个接收服务用于标记传入邮件的格式稍有不同，但结果应都包括以下类似内容： **DKIM=pass** 或 **DKIM=OK**</span><span class="sxs-lookup"><span data-stu-id="a759e-p119">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span> 
    
## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="a759e-204">在 Office 365 中为多个自定义域配置 DKIM 的具体步骤</span><span class="sxs-lookup"><span data-stu-id="a759e-204">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="a759e-205"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-205"></span></span>

<span data-ttu-id="a759e-p120">如果你在将来决定添加其他自定义域，并且想要为新域启用 DKIM，必须为每个域完成本文中介绍的步骤。尤其需要完成[在 Office 365 中手动设置 DKIM 需要执行的操作](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)中的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="a759e-p120">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="a759e-208">在 Office 365 中为自定义域禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="a759e-208">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="a759e-209"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-209"></span></span>

<span data-ttu-id="a759e-p121">禁用签名策略不会完全禁用 DKIM。一段时间后，Office 365 将自动为您的域应用默认的 Office 365 策略。有关详细信息，请参阅 [DKIM 和 Office 365 的默认行为](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)。</span><span class="sxs-lookup"><span data-stu-id="a759e-p121">Disabling the signing policy does not completely disable DKIM. After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain. For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="a759e-213">使用 Windows PowerShell 禁用 DKIM 签名策略</span><span class="sxs-lookup"><span data-stu-id="a759e-213">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="a759e-214">[连接到 Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a759e-214">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>
    
2. <span data-ttu-id="a759e-215">为您要为其禁用 DKIM 签名的每个域运行以下命令之一。</span><span class="sxs-lookup"><span data-stu-id="a759e-215">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity <domain>
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="a759e-216">例如：</span><span class="sxs-lookup"><span data-stu-id="a759e-216">For example:</span></span>
    
    ```
    $p=Get-DkimSigningConfig -identity contoso.com
    $p[0] | set-DkimSigningConfig -enabled $false
    ```

   <span data-ttu-id="a759e-217">或</span><span class="sxs-lookup"><span data-stu-id="a759e-217">Or</span></span>
    
    ```
    Set-DkimSigningConfig -identity $p[<number>].identity -enabled $false
    ```

    <span data-ttu-id="a759e-218">其中, _number_是策略的索引。</span><span class="sxs-lookup"><span data-stu-id="a759e-218">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="a759e-219">例如：</span><span class="sxs-lookup"><span data-stu-id="a759e-219">For example:</span></span> 
    
    ```
    Set-DkimSigningConfig -identity $p[0].identity -enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="a759e-220">DKIM 和 Office 365 的默认行为</span><span class="sxs-lookup"><span data-stu-id="a759e-220">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="a759e-221"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-221"></span></span>

<span data-ttu-id="a759e-222">如果不启用 DKIM, Office 365 将自动为您的默认域创建1024位 DKIM 公钥, 以及在我们的数据中心内部存储的关联私钥。</span><span class="sxs-lookup"><span data-stu-id="a759e-222">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="a759e-223">默认情况下，Office 365 对没有合适策略的域使用默认签名配置。</span><span class="sxs-lookup"><span data-stu-id="a759e-223">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="a759e-224">也就是说，如果你未自行设置 DKIM，Office 365 将使用其默认策略，以及其为域启用 DKIM 所创建的密钥。</span><span class="sxs-lookup"><span data-stu-id="a759e-224">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="a759e-225">此外，如果在启用 DKIM 签名之后禁用它，一段时间后，Office 365 将自动为域应用 Office 365 默认策略。</span><span class="sxs-lookup"><span data-stu-id="a759e-225">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="a759e-p124">在以下示例中，假定 fabrikam.com 的 DKIM 已由 Office 365（而不是域管理员）启用。这表明 DNS 中没有所需的 CNAME。来自此域的电子邮件的 DKIM 签名如下所示：</span><span class="sxs-lookup"><span data-stu-id="a759e-p124">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>
  
```
From: Second Example <second.example@fabrikam.com> 
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed; 
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795; 
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type; 
    bh=<body hash>; 
    b=<signed field>;
```

<span data-ttu-id="a759e-229">在此示例中，主机名和域包含在 fabrikam.com 的 DKIM 签名由域管理员启用情况下 CNAME 将指向的值。</span><span class="sxs-lookup"><span data-stu-id="a759e-229">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="a759e-230">发送自 Office 365 的每封邮件将最终进行 DKIM 签名。</span><span class="sxs-lookup"><span data-stu-id="a759e-230">Eventually, every single message sent from Office 365 will be DKIM-signed.</span></span> <span data-ttu-id="a759e-231">如果自行启用 DKIM，该域将与发件人地址（此例中为 fabrikam.com）中的域相同。</span><span class="sxs-lookup"><span data-stu-id="a759e-231">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="a759e-232">如果不自行启用，该域将不同于发件人地址中的域，而是会使用组织的初始域。</span><span class="sxs-lookup"><span data-stu-id="a759e-232">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="a759e-233">有关确定初始域的信息, 请参阅[域 FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain)。</span><span class="sxs-lookup"><span data-stu-id="a759e-233">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="a759e-234">设置 DKIM 以便第三方服务可以代表自定义域发送或假冒电子邮件</span><span class="sxs-lookup"><span data-stu-id="a759e-234">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="a759e-235"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-235"></span></span>

<span data-ttu-id="a759e-p126">一些批量电子邮件服务提供商或服务型软件提供商允许你为来自其服务的电子邮件设置 DKIM 密钥。这需要你自己和第三方之间进行协调，从而设置必要的 DNS 记录。任何两个组织的操作过程都不会完全相同。相反，此过程完全因组织而异。</span><span class="sxs-lookup"><span data-stu-id="a759e-p126">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="a759e-240">显示为 contoso.com 和 bulkemailprovider.com 正确配置了 DKIM 的示例邮件如下所示：</span><span class="sxs-lookup"><span data-stu-id="a759e-240">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="a759e-241">在此示例中，为了获得该结果：</span><span class="sxs-lookup"><span data-stu-id="a759e-241">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="a759e-242">批量电子邮件提供商为 Contoso 提供一个 DKIM 公钥。</span><span class="sxs-lookup"><span data-stu-id="a759e-242">Bulk Email Provider gave Contoso a public DKIM key.</span></span>
    
2. <span data-ttu-id="a759e-243">Contoso 将 DKIM 密钥发布到 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a759e-243">Contoso published the DKIM key to its DNS record.</span></span>
    
3. <span data-ttu-id="a759e-p127">发送电子邮件时，批量电子邮件提供商使用相应的私钥对密钥进行签名。这样一来，批量电子邮件提供商可以将 DKIM 签名附加到邮件头中。</span><span class="sxs-lookup"><span data-stu-id="a759e-p127">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>
    
4. <span data-ttu-id="a759e-p128">接收电子邮件系统通过对 From 中的域进行 DKIM-Signature d=\<domain\> 值验证来执行 DKIM 检查：(5322.From) 邮件的地址。在此示例中，值匹配：</span><span class="sxs-lookup"><span data-stu-id="a759e-p128">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:</span></span>
    
    <span data-ttu-id="a759e-248">发件人 @**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="a759e-248">sender@**contoso.com**</span></span>
    
    <span data-ttu-id="a759e-249">d =**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="a759e-249">d=**contoso.com**</span></span>
    
## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="a759e-250">后续步骤：为 Office 365 设置 DKIM 之后</span><span class="sxs-lookup"><span data-stu-id="a759e-250">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="a759e-251"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="a759e-251"></span></span>

<span data-ttu-id="a759e-252">尽管 DKIM 旨在帮助防止欺骗，但 DKIM 与 SPF 和 DMARC 协同工作效果更佳。</span><span class="sxs-lookup"><span data-stu-id="a759e-252">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="a759e-253">设置了 DKIM 后，如果你尚未设置 SPF，则应执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a759e-253">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="a759e-254">有关 SPF 的快速介绍以及如何快速配置 SPF 的信息，请参阅[Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="a759e-254">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="a759e-255">有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="a759e-255">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="a759e-256">之后，请参阅[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a759e-256">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="a759e-257">[反垃圾邮件邮件头](anti-spam-message-headers.md)包括 Office 365 用于 DKIM 检查的语法和标头字段。</span><span class="sxs-lookup"><span data-stu-id="a759e-257">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span> 
  

