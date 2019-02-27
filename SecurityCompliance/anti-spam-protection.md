---
title: Office 365 电子邮件反垃圾邮件保护
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 了解可帮助您阻止 Exchange Online 和 Office 365 中的垃圾邮件的反垃圾邮件设置和筛选器。在 Office 365 中获取过多垃圾邮件？您可以自定义垃圾邮件筛选器和反垃圾邮件策略设置。
ms.openlocfilehash: f4d32bb0efae0a38fdc6789feef73bd5014eb75b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296315"
---
# <a name="office-365-email-anti-spam-protection"></a><span data-ttu-id="d1e4d-105">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="d1e4d-105">Office 365 email anti-spam protection</span></span>

<span data-ttu-id="d1e4d-p102">您是否担心 Office 365 中的垃圾邮件太多？我们已在 Office 365 或 Exchange Online Protection (EOP) 服务中构建了多个垃圾邮件筛选器, 因此你的电子邮件将从你收到第一封邮件起到保护。为了帮助阻止 Office 365 中的垃圾邮件, 您可能需要更改保护设置以处理组织中的特定问题, 例如, 您接收到来自特定发件人的大量垃圾邮件, 或者只是对设置进行微调以使其在量身定制以最大限度地满足组织的需求。若要执行此操作, 您可以更改 Office 365 安全&amp;合规中心中的反垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p102">Are you concerned about too much spam in Office 365? We've built multiple spam filters into your Office 365 or Exchange Online Protection (EOP) service, so your email is protected from the moment you receive your first message. In order to help prevent spam in Office 365, you may want to change a protection setting to deal with a specific issue in your organization—say you're receiving a lot of spam from a particular sender, for example—or to simply fine tune your settings so that they're tailored to best meet the needs of your organization. To do this, you can change anti-spam settings in the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="d1e4d-p103">本文适用于 Office 365 管理员。如果你不是管理员, 但你是 Office 365 用户, 并且想要了解如何处理你收到的垃圾邮件, 这不是你要查找的文章。相反, 如果将 Outlook 用于 PC 或 outlook for Mac, 请从[垃圾邮件筛选器的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)开始。如果您使用 web 上的 Outlook, 请从[了解垃圾电子邮件和网络钓鱼](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)开始。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p103">This article is intended for Office 365 administrators. If you're not an administrator, but you are an Office 365 user and you want to learn how to deal with spam you receive, this isn't the article you're looking for. Instead, if you use Outlook for PC or Outlook for Mac, start with [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). If you use Outlook on the web, start with [Learn about junk email and phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).</span></span>
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a><span data-ttu-id="d1e4d-114">这些选项有助于阻止 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d1e4d-114">These options help you prevent spam in Office 365</span></span>

 <span data-ttu-id="d1e4d-p104">**连接筛选。** 使用连接筛选时, Office 365 会先检查发件人的声誉, 然后再允许邮件访问。您可以创建允许列表或安全发件人列表, 以确保从特定 IP 地址或 ip 地址范围收到发送给您的每封邮件。您还可以创建要从中阻止邮件的 IP 地址列表, 称为阻止列表。有关详细信息, 请参阅[Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。如果你关注 Office 365 中的垃圾邮件, 请使用连接筛选帮助阻止垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p104">**Connection filtering.** When you use connection filtering, Office 365 checks the reputation of the sender before allowing a message to get through. You can create an allow list, or safe sender list, to make sure you receive every message sent to you from a specific IP address or IP address range. You can also create a list of IP addresses from which to block messages, called a block list. For more information, see [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). If you're concerned about spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
<span data-ttu-id="d1e4d-p105">对于拥有 Office 365 企业版 E5 或购买了高级威胁防护 (ATP) 许可证的客户, 欺骗版智能使用连接筛选来创建欺骗您的域的发件人的允许名单和阻止名单。有关详细信息, 请参阅[了解有关欺骗情报的详细](https://go.microsoft.com/fwlink/?LinkID=735009)信息。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p105">For customers who have Office 365 Enterprise E5 or have purchased Advanced Threat Protection (ATP) licenses, connection filtering is used by spoof intelligence to create allow and block lists of senders who are spoofing your domain. For more information, see [Learn more about spoof intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).</span></span>
  
 <span data-ttu-id="d1e4d-p106">**垃圾邮件筛选。** Office 365 使用垃圾邮件筛选检查邮件特征与垃圾邮件的一致性。您可以更改要对标识为垃圾邮件的邮件执行的操作, 并选择是筛选以特定语言编写的邮件, 还是从特定的国家或地区发送邮件。如果要采用严格的垃圾邮件筛选方法, 也可以启用高级垃圾邮件筛选选项。此外, 您还可以配置最终用户垃圾邮件通知, 以便在发送给用户的邮件被发送到隔离时通知用户。(将邮件发送到隔离是可配置的操作之一。)在这些通知中, 最终用户可以释放误报并将其报告给 Microsoft 进行分析。有关详细信息, 请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)。为了帮助阻止 office 365 中的垃圾邮件, 请使用垃圾邮件筛选 (如果你担心 office 365 中的垃圾邮件过多), 请使用连接筛选帮助阻止垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p106">**Spam filtering.** Office 365 checks for message characteristics consistent with spam by using spam filtering. You can change what actions to take on messages identified as spam, and choose whether to filter messages written in specific languages, or sent from specific countries or regions. You can also turn on advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. Additionally, you can configure end-user spam notifications to inform users when messages intended for them were sent to the quarantine instead. (Sending messages to the quarantine is one of the configurable actions.) From these notifications, end users can release false positives and report them to Microsoft for analysis. For more information, see [Configure your spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147). In order to help prevent spam in Office 365, use spam filtering, if you're concerned about too much spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1e4d-p107">对于 EOP 独立客户: 默认情况下, EOP 垃圾邮件筛选器将检测到的垃圾邮件发送到每个收件人的 "垃圾邮件" 文件夹。但是, 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 必须在您的本地服务器上配置两个 Exchange 传输规则, 以检测由 EOP 添加的垃圾邮件头。有关详细信息, 请参阅[确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p107">For EOP standalone customers: By default, the EOP spam filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx).</span></span> 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a><span data-ttu-id="d1e4d-134">如果您在 Office 365 中收到过多垃圾邮件, 则需要额外的信息</span><span class="sxs-lookup"><span data-stu-id="d1e4d-134">Extra information if you receive too much spam in Office 365</span></span>

<span data-ttu-id="d1e4d-135">以下视频概述了如何在 EOP 中配置垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-135">The following video provides an overview of configuring spam filtering in EOP.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
<span data-ttu-id="d1e4d-136">有关更多详细信息, 请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)主题。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-136">For more details, see the [Configure spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) topic.</span></span>
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a><span data-ttu-id="d1e4d-137">检查您的传出邮件以阻止 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d1e4d-137">Check your outgoing messages to prevent spam in Office 365</span></span>

 <span data-ttu-id="d1e4d-p108">**出站筛选。** Office 365 还会进行检查以确保您的用户不会发送垃圾邮件。例如, 用户的计算机可能会受到恶意软件的感染, 从而导致其发送垃圾邮件, 因此我们将针对被称为 "*出站筛选*" 的保护建立保护。无法关闭出站筛选, 但可以配置[配置出站垃圾邮件策略](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)中所述的设置。如果你担心 Office 365 中的垃圾邮件过多, 请使用出站筛选帮助防止 Exchange Online 中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p108">**Outbound filtering.** Office 365 also checks to make sure that your users don't send spam. For instance, a user's computer may get infected with malware that causes it to send spam messages, so we build protection against that called  *outbound filtering*  . You can't turn off outbound filtering, but you can configure the settings described in [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). If you're concerned about too much spam in Office 365, use outbound filtering to help prevent spam in Exchange Online.</span></span>
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a><span data-ttu-id="d1e4d-143">除了基础: 阻止 Office 365 中的垃圾邮件的更多方法</span><span class="sxs-lookup"><span data-stu-id="d1e4d-143">Beyond the basics: More ways to prevent spam in Office 365</span></span>

 <span data-ttu-id="d1e4d-p109">**邮件流规则。** 如果您想要超越内置垃圾邮件筛选功能并创建基于您的业务策略的自定义规则,*[邮件流规则](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*(也称为*传输规则*) 是可帮助您阻止 Office 365 中的垃圾邮件的另一个筛选器。例如, 可以使用邮件流规则为符合特定条件的邮件设置垃圾邮件可信度 (SCL) 值, 如[使用邮件流规则在邮件中设置垃圾邮件可信度 (SCL)](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p109">**Mail flow rules.** If you want to go beyond built-in spam filtering and create custom rules that are based on your business policies,  *[mail flow rules](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*, also called  *transport rules*, are another filter that help you prevent spam in Office 365. For example, you can use mail flow rules to set the spam confidence level (SCL) value for messages that match specific conditions, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).</span></span>
  
 <span data-ttu-id="d1e4d-p110">**电子邮件身份验证。** 使用域名系统 (DNS) 向关于电子邮件发件人的电子邮件添加可验证信息的技术称为电子邮件身份验证。更高级的 Office 365 管理员可以利用以下电子邮件身份验证方法:</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p110">**Email authentication.** Techniques that use the Domain Name System (DNS) to add verifiable information to email messages about the sender of an email message are called email authentication. More advanced Office 365 admins can make use of these email authentication methods:</span></span>
  
- <span data-ttu-id="d1e4d-p111">**发件人策略框架 (SPF)。** SPF 通过验证发件人的 IP 地址对发送域的所声称所有者进行验证, 从而验证电子邮件的来源。若要快速了解 SPF 并使其快速配置, 请参阅[在 Office 365 中设置 SPF 以帮助防止欺骗](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。有关 office 365 如何使用 SPF 的详细信息, 或用于故障排除或非标准部署 (如混合部署) 的更深入了解, 请先[了解 office 365 如何使用发件人策略框架 (SPF) 来防止欺骗](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p111">**Sender Policy Framework (SPF).** SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="d1e4d-p112">**域密钥识别邮件 (DKIM)。** DKIM 允许您在发送的电子邮件的邮件头中将数字签名附加到电子邮件。从你的域接收电子邮件的电子邮件系统使用此数字签名来确定其收到的传入电子邮件是否合法。有关 DKIM 和 office 365 的信息, 请参阅[使用 DKIM 验证从您的域发送的来自 Office 365 的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p112">**DomainKeys Identified Mail (DKIM).** DKIM lets you attach a digital signature to email messages in the message header of emails you send. Email systems that receive email from your domain use this digital signature to determine if incoming email that they receive is legitimate. For information about DKIM and Office 365, see [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="d1e4d-p113">**基于域的邮件身份验证、报告和一致性 (DMARC)。** DMARC 可帮助接收邮件系统确定如何处理未通过 SPF 或 DKIM 检查的邮件, 并为您的电子邮件合作伙伴提供另一个信任级别。有关设置 DMARC 的信息, 请参阅[使用 DMARC 验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p113">**Domain-based Message Authentication, Reporting, and Conformance (DMARC).** DMARC helps receiving mail systems determine what to do with messages that fail SPF or DKIM checks and provides another level of trust for your email partners. For information on setting up DMARC, see [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="d1e4d-161">如果你关注 Office 365 中的垃圾邮件、网络钓鱼和欺骗, 请结合使用 SPF、DKIM 和 DMARC 来帮助防止垃圾邮件和不必要的欺骗。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-161">If you're concerned about spam, phishing, and spoofing in Office 365, use SPF, DKIM, and DMARC together to help prevent spam and unwanted spoofing.</span></span>
  
 <span data-ttu-id="d1e4d-p114">**最终用户托管设置。** 如果你正在寻找有关最终用户如何管理自己的垃圾邮件设置的信息, 请查看[垃圾邮件筛选器的概述](https://go.microsoft.com/fwlink/?LinkId=270065)(针对 Microsoft outlook 用户) 或[了解垃圾邮件和网络钓鱼](https://go.microsoft.com/fwlink/?LinkId=270068)(针对 web 用户的 Outlook)。如果您使用 EOP 来保护本地邮箱, 请务必使用目录同步来确保这些设置已同步到服务。有关设置目录同步的详细信息, 请参阅在[EOP 中管理邮件用户](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)中的 "使用目录同步管理邮件用户"。</span><span class="sxs-lookup"><span data-stu-id="d1e4d-p114">**End-user managed settings.** If you're looking for information about how end users can manage their own spam settings, check out [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=270065) (for Microsoft Outlook users) or [Learn about Junk email and phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (for Outlook on the web users). If you're using EOP to protect on-premises mailboxes, be sure to use directory synchronization to ensure that these settings are synced to the service. For more information about setting up directory synchronization, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="d1e4d-166">更多信息</span><span class="sxs-lookup"><span data-stu-id="d1e4d-166">For more information</span></span>

[<span data-ttu-id="d1e4d-167">博客: 垃圾邮件和仿冒网站如何通过 Office 365？</span><span class="sxs-lookup"><span data-stu-id="d1e4d-167">Blog: Why does spam and phishing get through Office 365?</span></span>](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[<span data-ttu-id="d1e4d-168">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="d1e4d-168">Anti-Spam Protection FAQ</span></span>](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="d1e4d-169">使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件</span><span class="sxs-lookup"><span data-stu-id="d1e4d-169">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](prevent-email-from-being-marked-as-spam-0.md)
  
[<span data-ttu-id="d1e4d-170">如何设置 Office 365 垃圾邮件筛选以帮助阻止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="d1e4d-170">How to set up Office 365 spam filtering to help block junk messages</span></span>](reduce-spam-email.md)
  
[<span data-ttu-id="d1e4d-171">垃圾邮件和批量电子邮件之间有什么区别？</span><span class="sxs-lookup"><span data-stu-id="d1e4d-171">What's the Difference Between Junk Email and Bulk Email?</span></span>](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="d1e4d-172">反垃圾邮件邮件头</span><span class="sxs-lookup"><span data-stu-id="d1e4d-172">Anti-spam message headers</span></span>](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="d1e4d-173">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="d1e4d-173">Backscatter Messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a><span data-ttu-id="d1e4d-174">更多资源</span><span class="sxs-lookup"><span data-stu-id="d1e4d-174">More resources</span></span>

[<span data-ttu-id="d1e4d-175">从 Office 365 社区论坛获取帮助</span><span class="sxs-lookup"><span data-stu-id="d1e4d-175">Get help from the Office 365 community forums</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[<span data-ttu-id="d1e4d-176">管理员：登录并创建服务请求</span><span class="sxs-lookup"><span data-stu-id="d1e4d-176">Admins: Sign in and create a service request</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[<span data-ttu-id="d1e4d-177">管理员：呼叫支持</span><span class="sxs-lookup"><span data-stu-id="d1e4d-177">Admins: Call Support</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=518322)
