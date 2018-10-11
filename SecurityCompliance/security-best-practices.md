---
title: Office 365 的安全最佳做法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
description: 通过遵循这些建议的最佳实践数据违反或受到攻击的帐户的可能性降到最低。
ms.openlocfilehash: 63bda11afdd1e02e9e12e8c505aca7100c4deade
ms.sourcegitcommit: a36d2692396786f49c8765c65145e5093578e9a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498088"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="1d6fe-103">Office 365 的安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="1d6fe-103">Security best practices for Office 365</span></span>

<span data-ttu-id="1d6fe-104">通过遵循这些建议的最佳实践数据违反或受到攻击的帐户的可能性降到最低。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="1d6fe-p101">本文包含最佳实践快速的列表。有关更多深入分析和安全设置的信息，请参阅[Office 365 安全路线图： Top 优先级的前 30 天，90 天及其他认证实战](security-roadmap.md)。在这篇文章，您将发现信息基于现实世界攻击的调查其中我们顶部的 Microsoft Office 365 网络安全专家将提供指导如何评估风险和实现最重要的安全、 遵从性和信息保护控制来保护您的 Office 365 租户。您将了解如何设置优先级威胁、 到技术战略翻译威胁，然后到实现功能和控件使系统的方法。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p101">This article contains a quick list of best practices. For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md). In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant. You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="1d6fe-109">使用 Office 365 安全分数</span><span class="sxs-lookup"><span data-stu-id="1d6fe-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="1d6fe-p102">安全 Score 是一个安全分析工具，建议您可以以进一步降低风险。安全分数查看您的 Office 365 设置和活动，并对它们进行比较到由 Microsoft 建立一个比较基准。您将获取基于您在与最佳安全做法如何对齐的分数。有关如何获取安全分数和使用它来提高 Office 365 组织的安全性的详细信息，请参阅[介绍 Office 365 安全分数](office-365-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p102">Secure Score is a security analytics tool that recommends what you can do to further reduce risk. Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft. You'll get a score based on how aligned you are with best security practices. For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="1d6fe-114">要试用安全分数？</span><span class="sxs-lookup"><span data-stu-id="1d6fe-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="1d6fe-115">使用工作或学校帐户已分配的[有关 Office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)的 Office 365 角色，[登录到 Office 365](https://www.office.com/signin)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="1d6fe-116">访问安全分数在[https://SecureScore.office.com](https://SecureScore.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="1d6fe-117">使用多因素身份验证 (MFA)</span><span class="sxs-lookup"><span data-stu-id="1d6fe-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="1d6fe-p103">MFA 通过要求用户确认电话呼叫、 短信或其智能电话上正确输入自己的密码后应用程序通知向强密码策略额外的保护程序。就地 MFA，与 Office 365 用户帐户仍然会保护针对未经授权的访问，即使用户的密码受到威胁。帐户受到保护，因为后已满足其他质询没有向之前帐户授予访问。受到攻击或被盗密码不就足够了。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p103">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised. Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied. A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="1d6fe-122">规划多因素身份验证的 Office 365 部署</span><span class="sxs-lookup"><span data-stu-id="1d6fe-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)
    
- [<span data-ttu-id="1d6fe-123">为 Office 365 用户设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="1d6fe-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)
    
## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="1d6fe-124">使用 Office 365 云应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="1d6fe-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="1d6fe-p104">将基于您的业务需求，以便跟踪异常活动和对其执行操作的策略设置。设置与 Office 365 云应用程序安全性的通知，以便管理员可以查看异常或 risky 用户活动，如下载大量数据，多失败尝试登录时或登录从一个未知或危险的 IP 地址。对于与 Office 365 企业 E5 计划的组织，您可以立即开始使用 Office 365 云应用程序安全性。如果您有不同的企业计划，您可以作为购买 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p104">Set up policies based on your business needs to track anomalous activity and act on it. Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address. For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away. If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="1d6fe-129">O365 云应用程序安全性概述</span><span class="sxs-lookup"><span data-stu-id="1d6fe-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)
    
- [<span data-ttu-id="1d6fe-130">开启 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="1d6fe-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
## <a name="secure-mail-flow"></a><span data-ttu-id="1d6fe-131">安全邮件流</span><span class="sxs-lookup"><span data-stu-id="1d6fe-131">Secure mail flow</span></span>

<span data-ttu-id="1d6fe-132">通过电子邮件传输的实现富客户端功能集 in Exchange Online Protection 和获得更好的保证有关每个电子邮件、 发件人的标识和防御未知的恶意软件、 病毒和恶意 Url。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="1d6fe-133">配置您的组织的[Office 365 电子邮件防垃圾邮件保护](anti-spam-protection.md)策略。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span> 
    
- <span data-ttu-id="1d6fe-134">了解有关的信息，然后使用[高级的威胁保护安全的附件和安全的链接](https://technet.microsoft.com/library/mt148491.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>
    
- <span data-ttu-id="1d6fe-135">[添加到您的组织的反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="1d6fe-136">了解并为用户启用[Office 365 中的电子邮件中的安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span> 
    
- <span data-ttu-id="1d6fe-137">若要验证您的组织发送的邮件，并有助于防止欺骗，如果您使用的自定义域名 Office 365 中的组织，将设置 SPF、 DKIM，和 DMARC:</span><span class="sxs-lookup"><span data-stu-id="1d6fe-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>
    
  - <span data-ttu-id="1d6fe-138">[设置 Office 365 为了帮助防止欺骗中的 SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-138">[Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="1d6fe-139">[使用 DKIM 验证从您在 Office 365 中的自定义域发送出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>
    
  - <span data-ttu-id="1d6fe-140">[使用 DMARC 用于验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="1d6fe-141">启用邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="1d6fe-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="1d6fe-p105">某些审核日志记录将自动为您启用在 Office 365;但是，邮箱审核日志记录不会默认情况下。使用 Exchange Online PowerShell 中启用了 Office 365 中的所有用户邮箱的审核日志记录。有关信息，请参阅[启用邮箱审核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p105">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default. You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell. For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="1d6fe-p106">启用后可以审核日志记录您[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)以找出用户已登录到您的用户邮箱，发送消息，并由邮箱所有者、 委派用户执行其他活动或管理员。包含 Office 365 中的邮箱活动的列表默认情况下审核日志，请参阅[Exchange 邮箱活动](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p106">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator. For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="1d6fe-147">可以使用审核日志执行其他操作的信息，如更改的时间，可以将项保存在审核日志，请参阅[邮箱审核日志记录中 Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="1d6fe-148">配置数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="1d6fe-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="1d6fe-p107">DLP 允许您确定敏感数据，并创建策略，以防止用户无意或有意共享数据。DLP 适用于跨 Office 365，以便用户可以保持兼容不中断其工作流的情况包括 Exchange Online、 SharePoint Online 和 OneDrive。有关详细信息，请参阅[Overview of 数据丢失预防策略](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p107">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data. DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow. For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="1d6fe-152">使用客户密码箱</span><span class="sxs-lookup"><span data-stu-id="1d6fe-152">Use Customer Lockbox</span></span>

<span data-ttu-id="1d6fe-p108">作为 Office 365 管理员，您可以使用客户密码箱控制 Microsoft 支持工程师帮助会话期间访问您的数据的方式。在其中工程师需要访问数据以排除和修复问题的情况下，客户密码箱允许您批准或拒绝访问请求。如果您批准其工程师可以访问的数据。每个请求具有过期时间，一旦解决问题，关闭请求和访问权限被吊销。客户密码箱包含在 Office 365 企业版 5 计划中，或您可以购买与任何其他 Office 365 企业计划单独的订阅。有关信息，请参阅[Office 365 客户密码箱请求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-p108">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session. In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request. If you approve it, the engineer can access the data. Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked. Customer Lockbox is included in the Office 365 Enterprise 5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan. For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="1d6fe-159">亲自试用</span><span class="sxs-lookup"><span data-stu-id="1d6fe-159">Try it yourself</span></span>
<span data-ttu-id="1d6fe-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="1d6fe-160"></span></span>

<span data-ttu-id="1d6fe-161">请参阅 Office 365 试用版订阅之前采用它们在生产中使用这些安全功能。</span><span class="sxs-lookup"><span data-stu-id="1d6fe-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="1d6fe-162">创建 Office 365 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="1d6fe-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)
    
- [<span data-ttu-id="1d6fe-163">配置和测试 MFA 用户帐户</span><span class="sxs-lookup"><span data-stu-id="1d6fe-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)
    
- [<span data-ttu-id="1d6fe-164">配置和测试 Office 365 云应用程序安全性，通知您的全局管理员活动</span><span class="sxs-lookup"><span data-stu-id="1d6fe-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)
    
- [<span data-ttu-id="1d6fe-165">配置和测试 ATP 可疑的电子邮件</span><span class="sxs-lookup"><span data-stu-id="1d6fe-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)
    
- <span data-ttu-id="1d6fe-166">检查每个上述步骤您的试用[Office 365 安全分数](https://securescore.office.com/)</span><span class="sxs-lookup"><span data-stu-id="1d6fe-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span> 
    

