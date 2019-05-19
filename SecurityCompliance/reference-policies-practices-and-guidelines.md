---
title: 参考：策略、实践和指南
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 制定了各种策略和过程, 并采用了几个行业最佳实践来帮助我们的用户避免滥用、不受欢迎或恶意的电子邮件。
ms.openlocfilehash: 78b78f58ea2d96775361fe1761221e6c6e993688
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156844"
---
# <a name="reference-policies-practices-and-guidelines"></a><span data-ttu-id="1e505-103">参考：策略、实践和指南</span><span class="sxs-lookup"><span data-stu-id="1e505-103">Reference: Policies, practices, and guidelines</span></span>
  
<span data-ttu-id="1e505-p101">Microsoft 致力于在 Web 上提供最可信赖的用户体验。因此，Microsoft 已开发了多种策略、过程并采用多个行业的最佳实践，以保护我们的用户免受滥用、不必要或恶意的电子邮件的侵扰。试图向 Office 365 的用户发送电子邮件的发件人应确保用户完全理解并遵循本文中的指南，以帮助避免潜在的传送问题。</span><span class="sxs-lookup"><span data-stu-id="1e505-p101">Microsoft is dedicated to helping provide the most trusted user experience on the web. Therefore, Microsoft has developed various policies, procedures, and adopted several industry best practices to help protect our users from abusive, unwanted, or malicious email. Senders attempting to send email to Office 365 users should ensure they fully understand and are following the guidance in this article to help in this effort and to help avoid potential delivery issues.</span></span>
  
<span data-ttu-id="1e505-p102">如果您不遵从这些策略和指南，我们的支持小组可能无法协助您。如果您遵循本文中介绍的指南、实践和策略，但基于您的发送 IP 地址仍然遇到传送问题，请按步骤提交除名请求。有关说明，请参阅 [使用除名门户来将自己从 Office 365 阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="1e505-p102">If you are not in compliance with these policies and guidelines, it may not be possible for our support team to assist you. If you are adhering to the guidelines, practices, and policies presented in this article and are still experiencing delivery issues based on your sending IP address, please follow the steps to submit a delisting request. For instructions, see [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
## <a name="general-microsoft-policies"></a><span data-ttu-id="1e505-110">Microsoft 一般性策略</span><span class="sxs-lookup"><span data-stu-id="1e505-110">General Microsoft policies</span></span>
<span data-ttu-id="1e505-111"><a name="GenMsftPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-111"></span></span>

<span data-ttu-id="1e505-112">发送到 Office 365 用户的电子邮件必须遵从管理电子邮件传输和 Office 365 使用的所有 Microsoft 策略。</span><span class="sxs-lookup"><span data-stu-id="1e505-112">Email sent to Office 365 users must comply with all Microsoft policies governing email transmission and use of Office 365.</span></span>
  
- <span data-ttu-id="1e505-113">适用于 Office 365 的服务条款；尤其是，禁止使用服务发送垃圾邮件或传播恶意软件</span><span class="sxs-lookup"><span data-stu-id="1e505-113">Terms of Services applicable to Office 365; in particular, the prohibition against using the service to spam or distribute malware</span></span>
    
- [<span data-ttu-id="1e505-114">Microsoft 服务协议</span><span class="sxs-lookup"><span data-stu-id="1e505-114">Microsoft Services Agreement</span></span>](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a><span data-ttu-id="1e505-115">政府法规</span><span class="sxs-lookup"><span data-stu-id="1e505-115">Governmental regulations</span></span>
<span data-ttu-id="1e505-116"><a name="GovtRegulations"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-116"></span></span>

<span data-ttu-id="1e505-117">发送到 Office 365 用户的电子邮件必须遵循在管辖范围内管理电子邮件通信的所有适用的法律和法规。</span><span class="sxs-lookup"><span data-stu-id="1e505-117">Email sent to Office 365 users must adhere to all applicable laws and regulations governing email communications in the applicable jurisdiction.</span></span>
  
- [<span data-ttu-id="1e505-118">CAN-SPAM Act:A Compliance Guide for Business</span><span class="sxs-lookup"><span data-stu-id="1e505-118">CAN-SPAM Act: A Compliance Guide for Business</span></span>](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- [<span data-ttu-id="1e505-119">"Remove Me" Responses and Responsibilities:Email Marketers Must Honor "Unsubscribe" Claims</span><span class="sxs-lookup"><span data-stu-id="1e505-119">"Remove Me" Responses and Responsibilities: Email Marketers Must Honor "Unsubscribe" Claims</span></span>](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a><span data-ttu-id="1e505-120">技术指南</span><span class="sxs-lookup"><span data-stu-id="1e505-120">Technical guidelines</span></span>
<span data-ttu-id="1e505-121"><a name="TechGuidelines"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-121"></span></span>

<span data-ttu-id="1e505-122">发送到 Office 365 的电子邮件应遵循以下文档中列出的适用性建议（某些链接只提供英文版本）。</span><span class="sxs-lookup"><span data-stu-id="1e505-122">Email sent to Office 365 should comply with the applicable recommendations listed in the documents below (some links are only available in English).</span></span>
  
- [<span data-ttu-id="1e505-123">RFC 2505:Anti-Spam Recommendations for SMTP MTAs</span><span class="sxs-lookup"><span data-stu-id="1e505-123">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span></span>](https://www.ietf.org/rfc/rfc2505.txt)
    
- [<span data-ttu-id="1e505-124">RFC 2920:SMTP Service Extension for Command Pipelining</span><span class="sxs-lookup"><span data-stu-id="1e505-124">RFC 2920: SMTP Service Extension for Command Pipelining</span></span>](https://www.ietf.org/rfc/rfc2920.txt)
    
<span data-ttu-id="1e505-125">此外，连接到 Office 365 的电子邮件服务器必须遵从以下要求：</span><span class="sxs-lookup"><span data-stu-id="1e505-125">In addition, email servers connecting to Office 365 must adhere to the following requirements:</span></span>
  
- <span data-ttu-id="1e505-126">发件人应符合互联网电子邮件传输的所有技术标准，该标准由互联网协会的互联网工程任务组 (IETF) 发布，包括 RFC 5321、RFC 5322 和其他。</span><span class="sxs-lookup"><span data-stu-id="1e505-126">Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The Internet Society's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.</span></span> 
    
- <span data-ttu-id="1e505-127">在给出 500 和 599 之间的数值 SMTP 错误响应代码后（也称为永久未送达响应或 NDR），发件人不得再次向该收件人传输邮件。</span><span class="sxs-lookup"><span data-stu-id="1e505-127">After given a numeric SMTP error response code between 500 and 599 (also known as a permanent non-delivery response or NDR), the sender must not attempt to retransmit that message to that recipient.</span></span>
    
- <span data-ttu-id="1e505-128">多个未送达响应后，发件人必须停止进一步向该收件人发送邮件的操作。</span><span class="sxs-lookup"><span data-stu-id="1e505-128">After multiple non-delivery responses, the sender must cease further attempts to send email to that recipient.</span></span>
    
- <span data-ttu-id="1e505-129">邮件不得通过不安全的电子邮件中继或代理服务器传输。</span><span class="sxs-lookup"><span data-stu-id="1e505-129">Messages must not be transmitted through insecure email relay or proxy servers.</span></span>
    
- <span data-ttu-id="1e505-130">从单个列表或从由发件人托管的所有列表取消订阅的机制，必须清楚地说明，且易于供收件人查找使用。</span><span class="sxs-lookup"><span data-stu-id="1e505-130">The mechanism for unsubscribing, either from individual lists or all lists hosted by the sender, must be clearly documented and easy for recipients to find and use.</span></span>
    
- <span data-ttu-id="1e505-131">来自动态的 IP 空间的连接可能不被接受。</span><span class="sxs-lookup"><span data-stu-id="1e505-131">Connections from dynamic IP space may not be accepted.</span></span>
    
- <span data-ttu-id="1e505-132">电子邮件服务器必须具有有效的反向 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1e505-132">Email servers must have valid reverse DNS records.</span></span>
    
## <a name="reputation-management"></a><span data-ttu-id="1e505-133">信誉管理</span><span class="sxs-lookup"><span data-stu-id="1e505-133">Reputation management</span></span>
<span data-ttu-id="1e505-134"><a name="RepManagement"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-134"></span></span>

<span data-ttu-id="1e505-135">发件人、ISP 和其他服务提供商应主动管理出站 IP 地址的信誉。</span><span class="sxs-lookup"><span data-stu-id="1e505-135">Senders, ISP's, and other service providers should actively manage the reputation of your outbound IP addresses.</span></span>
  
## <a name="office-365-limits"></a><span data-ttu-id="1e505-136">Office 365 限制</span><span class="sxs-lookup"><span data-stu-id="1e505-136">Office 365 limits</span></span>
<span data-ttu-id="1e505-137"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-137"></span></span>

<span data-ttu-id="1e505-138">发件人必须遵循 [Exchange Online Protection 限制](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)列出的 Office 365 限制。</span><span class="sxs-lookup"><span data-stu-id="1e505-138">Senders must adhere to Office 365 limits listed in [Exchange Online Protection Limits](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx).</span></span>
  
## <a name="email-delivery-resources-and-organizations"></a><span data-ttu-id="1e505-139">电子邮件传送资源和组织</span><span class="sxs-lookup"><span data-stu-id="1e505-139">Email delivery resources and organizations</span></span>
<span data-ttu-id="1e505-140"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-140"></span></span>

<span data-ttu-id="1e505-p103">Microsoft 积极与行业机构和服务提供商合作，以改善互联网和电子邮件的生态系统。这些组织已经发布了我们支持并建议发件人遵循的最佳实践的文档。这提高了您在世界各地的多个电子邮件服务提供商直接传送邮件的能力。</span><span class="sxs-lookup"><span data-stu-id="1e505-p103">Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem. These organizations have published best practice documents that we support and recommend senders adhere to. This improves your ability to deliver email among several email service providers around the world.</span></span>
  
- [<span data-ttu-id="1e505-144">信息传送、恶意软件和移动反滥用工作组</span><span class="sxs-lookup"><span data-stu-id="1e505-144">Messaging Malware Mobile Anti-Abuse Working Group</span></span>](https://www.m3aawg.org/)
    
- [<span data-ttu-id="1e505-145">在线信任联盟</span><span class="sxs-lookup"><span data-stu-id="1e505-145">Online Trust Alliance </span></span>](https://www.otalliance.org/resources)
    
- [<span data-ttu-id="1e505-146">Email Sender &amp; Provider Coalition</span><span class="sxs-lookup"><span data-stu-id="1e505-146">Email Sender &amp; Provider Coalition</span></span>](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a><span data-ttu-id="1e505-147">滥用和垃圾邮件报告</span><span class="sxs-lookup"><span data-stu-id="1e505-147">Abuse and spam reporting</span></span>
<span data-ttu-id="1e505-148"><a name="AbuseSpamReports"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-148"></span></span>

<span data-ttu-id="1e505-149">若要报告非法、滥用、不受欢迎或恶意的电子邮件, 请[在 web 上的 Outlook 中报告垃圾电子邮件和网络钓鱼诈骗](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="1e505-149">To report unlawful, abusive, unwanted or malicious email, please [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="1e505-150">发送这些类型的通信将违反 Microsoft 策略，我们将对已确认的报告采取适当措施。</span><span class="sxs-lookup"><span data-stu-id="1e505-150">Sending these types of communications is a violation of Microsoft policy and appropriate action will be taken on confirmed reports.</span></span>
  
## <a name="law-enforcement"></a><span data-ttu-id="1e505-151">法律执行</span><span class="sxs-lookup"><span data-stu-id="1e505-151">Law enforcement</span></span>
<span data-ttu-id="1e505-152"><a name="sectionSection7"> </a></span><span class="sxs-lookup"><span data-stu-id="1e505-152"></span></span>

<span data-ttu-id="1e505-153">如果您是执法机构的成员，想就 Office 365 相关法律文档为 Microsoft Corportation 服务，或如果您对提交给 Microsoft 的法律文档有任何问题，请拨打 (1) (425) 722-1299。</span><span class="sxs-lookup"><span data-stu-id="1e505-153">If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.</span></span>
  

