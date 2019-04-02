---
title: Office 365 的安全最佳做法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/22/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: 9295e396-e53d-49b9-ae9b-0b5828cdedc3
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 通过遵循这些建议的最佳实践, 最大程度地降低数据泄露或泄露帐户的潜能。
ms.openlocfilehash: bd4b911cd5972b7d6dc9b55c17e375d326b1d571
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31026333"
---
# <a name="security-best-practices-for-office-365"></a><span data-ttu-id="64e47-103">Office 365 的安全最佳做法</span><span class="sxs-lookup"><span data-stu-id="64e47-103">Security best practices for Office 365</span></span>

<span data-ttu-id="64e47-104">通过遵循这些建议的最佳实践, 最大程度地降低数据泄露或泄露帐户的潜能。</span><span class="sxs-lookup"><span data-stu-id="64e47-104">Minimize the potential of a data breach or a compromised account by following these recommended best practices.</span></span>
  
<span data-ttu-id="64e47-105">本文包含最佳实践的快速列表。</span><span class="sxs-lookup"><span data-stu-id="64e47-105">This article contains a quick list of best practices.</span></span> <span data-ttu-id="64e47-106">有关设置安全性的更深入的分析和信息, 请参阅[Office 365 安全路线图: 前30天、90天和之后的主要优先级](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="64e47-106">For more in-depth analysis and information on setting up security, see [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md).</span></span> <span data-ttu-id="64e47-107">在这篇文章中, 您将根据实际攻击的调查查找信息, 其中我们的主要 Microsoft Office 365 cybersecurity 专家为如何评估风险和实现最关键的安全性、合规性和信息提供了指导保护 Office 365 租户的保护控制。</span><span class="sxs-lookup"><span data-stu-id="64e47-107">In that article, you'll find information based on investigations of real-world attacks, where our top Microsoft Office 365 cybersecurity experts provide coaching on how to assess risk and implement the most critical security, compliance, and information protection controls to protect your Office 365 tenant.</span></span> <span data-ttu-id="64e47-108">您将了解如何对威胁进行优先级划分, 将威胁转换为技术策略, 然后采用系统化的方法来实现功能和控制。</span><span class="sxs-lookup"><span data-stu-id="64e47-108">You'll learn how to prioritize threats, translate threats into technical strategy, and then take a systematic approach to implementing features and controls.</span></span>
  
## <a name="use-office-365-secure-score"></a><span data-ttu-id="64e47-109">使用 Office 365 安全分数</span><span class="sxs-lookup"><span data-stu-id="64e47-109">Use Office 365 Secure Score</span></span>

<span data-ttu-id="64e47-110">安全得分是一种安全分析工具, 它建议您可以执行哪些操作以进一步降低风险。</span><span class="sxs-lookup"><span data-stu-id="64e47-110">Secure Score is a security analytics tool that recommends what you can do to further reduce risk.</span></span> <span data-ttu-id="64e47-111">安全分数查看 Office 365 设置和活动, 并将它们与 Microsoft 建立的基准进行比较。</span><span class="sxs-lookup"><span data-stu-id="64e47-111">Secure Score looks at your Office 365 settings and activities and compares them to a baseline established by Microsoft.</span></span> <span data-ttu-id="64e47-112">你将根据最佳安全实践的对齐方式获得分数。</span><span class="sxs-lookup"><span data-stu-id="64e47-112">You'll get a score based on how aligned you are with best security practices.</span></span> <span data-ttu-id="64e47-113">若要详细了解如何获取安全得分并使用它来提高 office 365 组织的安全性, 请参阅[简介 office 365 安全分数](office-365-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="64e47-113">For more information about how to get Secure Score and use it to increase the security of your Office 365 organization, see [Introducing the Office 365 Secure Score](office-365-secure-score.md).</span></span>
  
<span data-ttu-id="64e47-114">想要试用安全分数？</span><span class="sxs-lookup"><span data-stu-id="64e47-114">Want to try out Secure Score?</span></span>
  
<span data-ttu-id="64e47-115">使用已分配了 office 365[关于 office 365 管理员角色](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)角色的工作或学校帐户,[登录到 Office 365](https://www.office.com/signin)。</span><span class="sxs-lookup"><span data-stu-id="64e47-115">Using a work or school account that has been assigned the Office 365 [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) role, [sign in to Office 365](https://www.office.com/signin).</span></span>
  
<span data-ttu-id="64e47-116">在上[https://SecureScore.office.com](https://SecureScore.office.com)访问安全分数。</span><span class="sxs-lookup"><span data-stu-id="64e47-116">Access Secure Score at [https://SecureScore.office.com](https://SecureScore.office.com).</span></span>
  
## <a name="use-multi-factor-authentication-mfa"></a><span data-ttu-id="64e47-117">使用多重身份验证 (MFA)</span><span class="sxs-lookup"><span data-stu-id="64e47-117">Use multi-factor authentication (MFA)</span></span>

<span data-ttu-id="64e47-118">通过在正确输入密码后, 通过请求用户在智能手机上确认电话呼叫、短信或应用程序通知, MFA 向强密码策略添加了一层额外的保护。</span><span class="sxs-lookup"><span data-stu-id="64e47-118">MFA adds an additional layer of protection to a strong password strategy by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password.</span></span> <span data-ttu-id="64e47-119">在进行 MFA 时, 即使用户的密码受到威胁, Office 365 用户帐户仍会受到保护以防未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="64e47-119">With MFA in place, Office 365 user accounts are still protected against unauthorized access even if a user's password is compromised.</span></span> <span data-ttu-id="64e47-120">帐户受到保护, 因为在满足其他挑战之前, 不向帐户授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="64e47-120">Accounts are protected because access is not granted to an account until after the additional challenge has been satisfied.</span></span> <span data-ttu-id="64e47-121">已泄露或被盗的密码不足。</span><span class="sxs-lookup"><span data-stu-id="64e47-121">A compromised or stolen password is not enough.</span></span>
  
- [<span data-ttu-id="64e47-122">规划 Office 365 部署的多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="64e47-122">Plan for multi-factor authentication for Office 365 Deployments</span></span>](https://support.office.com/article/043807b2-21db-4d5c-b430-c8a6dee0e6ba)

- [<span data-ttu-id="64e47-123">为 Office 365 用户设置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="64e47-123">Set up multi-factor authentication for Office 365 users</span></span>](https://support.office.com/article/8f0454b2-f51a-4d9c-bcde-2c48e41621c6)

## <a name="use-office-365-cloud-app-security"></a><span data-ttu-id="64e47-124">使用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="64e47-124">Use Office 365 Cloud App Security</span></span>

<span data-ttu-id="64e47-125">根据您的业务需求来设置策略, 以跟踪异常活动并对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="64e47-125">Set up policies based on your business needs to track anomalous activity and act on it.</span></span> <span data-ttu-id="64e47-126">设置与 Office 365 云应用安全有关的通知, 以便管理员可以查看异常或风险的用户活动, 如下载大量数据、多次失败的登录尝试或来自未知或危险的 IP 地址的登录。</span><span class="sxs-lookup"><span data-stu-id="64e47-126">Set up alerts with Office 365 Cloud App Security so that admins can review unusual or risky user activity, such as downloading large amounts of data, multiple failed sign-in attempts, or sign-ins from an unknown or dangerous IP address.</span></span> <span data-ttu-id="64e47-127">对于具有 Office 365 企业版 E5 计划的组织, 可以立即开始使用 office 365 云应用安全。</span><span class="sxs-lookup"><span data-stu-id="64e47-127">For organizations with an Office 365 Enterprise E5 plan, you can start using Office 365 Cloud App Security right away.</span></span> <span data-ttu-id="64e47-128">如果你有一个不同的企业计划, 则可以将 Office 365 云应用安全作为加载项进行购买。</span><span class="sxs-lookup"><span data-stu-id="64e47-128">If you have a different enterprise plan, you can purchase Office 365 Cloud App Security as an add-on.</span></span>
  
- [<span data-ttu-id="64e47-129">O365 云应用安全概述</span><span class="sxs-lookup"><span data-stu-id="64e47-129">Overview of O365 Cloud App Security</span></span>](office-365-cas-overview.md)

- [<span data-ttu-id="64e47-130">启用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="64e47-130">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)

## <a name="secure-mail-flow"></a><span data-ttu-id="64e47-131">安全邮件流</span><span class="sxs-lookup"><span data-stu-id="64e47-131">Secure mail flow</span></span>

<span data-ttu-id="64e47-132">在 Exchange Online Protection 中实现丰富的功能集, 并更好地保证每封电子邮件的发件人的身份, 并防止通过电子邮件传输的未知恶意软件、病毒和恶意 url。</span><span class="sxs-lookup"><span data-stu-id="64e47-132">Implement the rich feature set in Exchange Online Protection and gain greater assurance about the identity of the sender of each email message, and protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>
  
- <span data-ttu-id="64e47-133">为您的组织配置[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)策略。</span><span class="sxs-lookup"><span data-stu-id="64e47-133">Configure [Office 365 Email Anti-Spam Protection](anti-spam-protection.md) policies for your organization.</span></span>

- <span data-ttu-id="64e47-134">了解并使用[安全附件和安全链接的高级威胁防护](https://technet.microsoft.com/library/mt148491.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64e47-134">Learn about and then use [Advanced threat protection for safe attachments and safe links](https://technet.microsoft.com/library/mt148491.aspx).</span></span>

- <span data-ttu-id="64e47-135">向[你的组织添加反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64e47-135">[Add anti-malware protection to your organization](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="64e47-136">了解并为用户启用[Office 365 中电子邮件中的安全提示](safety-tips-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="64e47-136">Learn about and enable [Safety tips in email messages in Office 365](safety-tips-in-office-365.md) for your users.</span></span>

- <span data-ttu-id="64e47-137">如果您在 Office 365 中为您的组织使用自定义域, 请设置 SPF、DKIM 和 DMARC 以验证您的组织发送的邮件并帮助防止欺骗:</span><span class="sxs-lookup"><span data-stu-id="64e47-137">If you're using a custom domain for your organization in Office 365, set up SPF, DKIM, and then DMARC to validate mail sent by your organization and to help prevent spoofing:</span></span>

  - <span data-ttu-id="64e47-138">[在 Office 365 中设置 SPF 以帮助防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="64e47-138">[Set up SPF in Office 365 to help prevent spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>

  - <span data-ttu-id="64e47-139">[使用 DKIM 验证从 Office 365 中的自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)。</span><span class="sxs-lookup"><span data-stu-id="64e47-139">[Use DKIM to validate outbound email sent from your custom domain in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing).</span></span>

  - <span data-ttu-id="64e47-140">[使用 DMARC 验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64e47-140">[Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

## <a name="enable-mailbox-audit-logging"></a><span data-ttu-id="64e47-141">启用邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="64e47-141">Enable mailbox audit logging</span></span>

<span data-ttu-id="64e47-142">在 Office 365 中会自动为你启用一些审核日志记录;但是, 邮箱审核日志记录在默认情况下不会启用。</span><span class="sxs-lookup"><span data-stu-id="64e47-142">Some audit logging is automatically enabled for you in Office 365; however, mailbox audit logging is not turned on by default.</span></span> <span data-ttu-id="64e47-143">您可以使用 Exchange Online PowerShell 为 Office 365 中的所有用户邮箱启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="64e47-143">You turn on audit logging for all user mailboxes in Office 365 by using Exchange Online PowerShell.</span></span> <span data-ttu-id="64e47-144">有关信息, 请参阅[在 Office 365 中启用邮箱审核](https://go.microsoft.com/fwlink/p/?LinkID=626109)。</span><span class="sxs-lookup"><span data-stu-id="64e47-144">For information, see [Enable mailbox auditing in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=626109).</span></span>
  
<span data-ttu-id="64e47-145">启用审核日志记录后, 可以[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md), 以查明登录到用户邮箱的用户、已发送的邮件以及邮箱所有者、委派用户执行的其他活动或管理员。</span><span class="sxs-lookup"><span data-stu-id="64e47-145">After you've enabled audit logging you can [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md) to find out who has logged into your user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span> <span data-ttu-id="64e47-146">有关默认情况下包含在 Office 365 审核日志中的邮箱活动的列表, 请参阅[Exchange 邮箱活动](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities)。</span><span class="sxs-lookup"><span data-stu-id="64e47-146">For a list of mailbox activities that are included in the Office 365 audit log by default, see [Exchange mailbox activities](search-the-audit-log-in-security-and-compliance.md#exchange-mailbox-activities).</span></span>
  
<span data-ttu-id="64e47-147">有关您可以使用审核日志执行的其他操作的信息, 如更改在审核日志中保存条目的时间量, 请参阅[Exchange 2016 中的邮箱审核日志记录](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="64e47-147">For information about other actions you can perform with the audit log, such as changing the amount of time to save entries in the audit log, see [Mailbox audit logging in Exchange 2016](https://technet.microsoft.com/en-us/library/ff459237%28v=exchg.160%29.aspx).</span></span>
  
## <a name="configure-data-loss-prevention-dlp"></a><span data-ttu-id="64e47-148">配置数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="64e47-148">Configure Data Loss Prevention (DLP)</span></span>

<span data-ttu-id="64e47-149">DLP 允许您标识敏感数据, 并创建有助于防止用户意外或有意地共享数据的策略。</span><span class="sxs-lookup"><span data-stu-id="64e47-149">DLP allows you to identify sensitive data and create policies that help prevent your users from accidentally or intentionally sharing the data.</span></span> <span data-ttu-id="64e47-150">DLP 在 Office 365 中工作, 包括 Exchange online、SharePoint online 和 OneDrive, 以便您的用户在不中断其工作流的情况下保持合规性。</span><span class="sxs-lookup"><span data-stu-id="64e47-150">DLP works across Office 365 including Exchange Online, SharePoint Online, and OneDrive so that your users can stay compliant without interrupting their workflow.</span></span> <span data-ttu-id="64e47-151">有关详细信息，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="64e47-151">For more information, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
## <a name="use-customer-lockbox"></a><span data-ttu-id="64e47-152">使用客户密码箱</span><span class="sxs-lookup"><span data-stu-id="64e47-152">Use Customer Lockbox</span></span>

<span data-ttu-id="64e47-153">作为 Office 365 管理员，您可以使用客户锁箱来控制 Microsoft 技术支持工程师在帮助会话期间访问您数据的方式。</span><span class="sxs-lookup"><span data-stu-id="64e47-153">As an Office 365 admin, you can use Customer Lockbox to control how a Microsoft support engineer accesses your data during a help session.</span></span> <span data-ttu-id="64e47-154">如果工程师需要访问您的数据以进行故障排除和解决问题，那么您可以使用客户锁箱批准或拒绝该访问请求。</span><span class="sxs-lookup"><span data-stu-id="64e47-154">In cases where the engineer requires access to your data to troubleshoot and fix an issue, Customer Lockbox allows you to approve or reject the access request.</span></span> <span data-ttu-id="64e47-155">如果你批准它, 则工程师可以访问数据。</span><span class="sxs-lookup"><span data-stu-id="64e47-155">If you approve it, the engineer can access the data.</span></span> <span data-ttu-id="64e47-156">每个请求都有过期时间，一旦问题得以解决，即关闭请求并吊销该访问权限。</span><span class="sxs-lookup"><span data-stu-id="64e47-156">Each request has an expiration time, and once the issue is resolved, the request is closed and access is revoked.</span></span> <span data-ttu-id="64e47-157">客户密码箱包含在 office 365 企业版 E5 计划中, 也可以使用任何其他 Office 365 企业版计划购买单独的订阅。</span><span class="sxs-lookup"><span data-stu-id="64e47-157">Customer Lockbox is included in the Office 365 Enterprise E5 plan, or you can purchase a separate subscription with any other Office 365 enterprise plan.</span></span> <span data-ttu-id="64e47-158">有关信息, 请参阅[Office 365 客户密码箱请求](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2)。</span><span class="sxs-lookup"><span data-stu-id="64e47-158">For information, see [Office 365 Customer Lockbox Requests](https://support.office.com/article/36f9cdd1-e64c-421b-a7e4-4a54d16440a2).</span></span>
  
## <a name="try-it-yourself"></a><span data-ttu-id="64e47-159">亲自试用</span><span class="sxs-lookup"><span data-stu-id="64e47-159">Try it yourself</span></span>
<span data-ttu-id="64e47-160"><a name="SecureScore"> </a></span><span class="sxs-lookup"><span data-stu-id="64e47-160"></span></span>

<span data-ttu-id="64e47-161">在将其采用生产环境之前, 请参阅在 Office 365 试用订阅中工作的这些安全功能。</span><span class="sxs-lookup"><span data-stu-id="64e47-161">See these security features working in an Office 365 trial subscription prior to adopting them in production.</span></span>
  
- [<span data-ttu-id="64e47-162">创建 Office 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="64e47-162">Create an Office 365 trial subscription</span></span>](https://technet.microsoft.com/library/mt736406.aspx)

- [<span data-ttu-id="64e47-163">为用户帐户配置和测试 MFA</span><span class="sxs-lookup"><span data-stu-id="64e47-163">Configure and test MFA for a user account</span></span>](https://technet.microsoft.com/library/mt492459.aspx)

- [<span data-ttu-id="64e47-164">配置和测试 Office 365 云应用安全性以通知您全局管理活动</span><span class="sxs-lookup"><span data-stu-id="64e47-164">Configure and test Office 365 Cloud App Security to notify you of global admin activity</span></span>](https://technet.microsoft.com/library/mt757250.aspx)

- [<span data-ttu-id="64e47-165">配置和测试可疑电子邮件的 ATP</span><span class="sxs-lookup"><span data-stu-id="64e47-165">Configure and test ATP for suspicious email</span></span>](https://technet.microsoft.com/library/mt490479.aspx)

- <span data-ttu-id="64e47-166">在上述每个步骤中检查试用版订阅的[Office 365 安全分数](https://securescore.office.com/)</span><span class="sxs-lookup"><span data-stu-id="64e47-166">Check the [Office 365 Secure Score](https://securescore.office.com/) for your trial subscription for each of the above steps</span></span>