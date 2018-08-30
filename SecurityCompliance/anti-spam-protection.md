---
title: Office 365 电子邮件防垃圾邮件保护
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 了解有关反垃圾邮件设置和筛选器可帮助防止在 Exchange Online 和 Office 365 中的垃圾邮件。获取 Office 365 中的垃圾邮件太多？您可以自定义垃圾邮件筛选器和反垃圾邮件策略设置。
ms.openlocfilehash: 5547904633a0be9ad57fa7431aeddf1267871662
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525437"
---
# <a name="office-365-email-anti-spam-protection"></a><span data-ttu-id="96935-105">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="96935-105">Office 365 email anti-spam protection</span></span>

<span data-ttu-id="96935-p102">Office 365 中的垃圾邮件太多您担心？我们已将多个垃圾邮件筛选器内置您的 Office 365 或 Exchange Online Protection (EOP) 服务，以便从接收您第一条消息仍未受保护您的电子邮件。为了帮助防止 Office 365 中的垃圾邮件，您可能想要更改处理您的组织中的特定问题的保护设置 — 说您正在接收大量的垃圾邮件来自特定发件人，例如 — 或到只可以精细优化您的设置，以便它们定制最好地满足组织的需求。为此，您可以更改 Office 365 安全性的反垃圾邮件设置&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="96935-p102">Are you concerned about too much spam in Office 365? We've built multiple spam filters into your Office 365 or Exchange Online Protection (EOP) service, so your email is protected from the moment you receive your first message. In order to help prevent spam in Office 365, you may want to change a protection setting to deal with a specific issue in your organization—say you're receiving a lot of spam from a particular sender, for example—or to simply fine tune your settings so that they're tailored to best meet the needs of your organization. To do this, you can change anti-spam settings in the Office 365 Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="96935-p103">本文适用于 Office 365 管理员。如果您不是管理员，但您是 Office 365 用户，并且想要了解如何处理您收到的垃圾邮件，这不是您在寻找一文。相反，如果您使用的 PC Outlook 或 Outlook for Mac，从开始[垃圾邮件筛选器的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。如果您使用 Outlook web 上的，从开始[了解垃圾邮件和网络钓鱼](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)。</span><span class="sxs-lookup"><span data-stu-id="96935-p103">This article is intended for Office 365 administrators. If you're not an administrator, but you are an Office 365 user and you want to learn how to deal with spam you receive, this isn't the article you're looking for. Instead, if you use Outlook for PC or Outlook for Mac, start with [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). If you use Outlook on the web, start with [Learn about junk email and phishing](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31).</span></span>
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a><span data-ttu-id="96935-114">这些选项，有助于防止 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="96935-114">These options help you prevent spam in Office 365</span></span>

 <span data-ttu-id="96935-p104">**连接筛选。** 当您使用的连接筛选时，Office 365 检查发件人信誉之前允许获取一条消息。您可以创建允许列表中或安全发件人列表中，以确保您收到来自特定 IP 地址或 IP 地址范围发送给您每条消息。您还可以创建从其阻止邮件，调用阻止列表的 IP 地址的列表。有关详细信息，请参阅[配置连接筛选器策略](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。如果您担心 Office 365 中的垃圾邮件，使用连接筛选以防止出现垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="96935-p104">**Connection filtering.** When you use connection filtering, Office 365 checks the reputation of the sender before allowing a message to get through. You can create an allow list, or safe sender list, to make sure you receive every message sent to you from a specific IP address or IP address range. You can also create a list of IP addresses from which to block messages, called a block list. For more information, see [Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx). If you're concerned about spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
<span data-ttu-id="96935-p105">对于具有 Office 365 企业 E5 或购买高级威胁保护 (ATP) 许可证的客户，连接筛选使用欺骗智能创建允许和阻止发件人在伪造您的域的列表。有关详细信息，请参阅[了解更多有关欺骗智能](https://go.microsoft.com/fwlink/?LinkID=735009)。</span><span class="sxs-lookup"><span data-stu-id="96935-p105">For customers who have Office 365 Enterprise E5 or have purchased Advanced Threat Protection (ATP) licenses, connection filtering is used by spoof intelligence to create allow and block lists of senders who are spoofing your domain. For more information, see [Learn more about spoof intelligence](https://go.microsoft.com/fwlink/?LinkID=735009).</span></span>
  
 <span data-ttu-id="96935-p106">**垃圾邮件筛选。** Office 365 检查邮件特征符合垃圾邮件使用垃圾邮件筛选。您可以更改要对邮件标识为垃圾邮件，并选择是否以筛选以特定语言撰写或从特定国家或地区发送的邮件的操作。您还可以打开高级垃圾邮件筛选选项，如果您想要使用垃圾邮件筛选保守方法。此外，还可以配置最终用户垃圾邮件通知，告知用户而时适用于它们的邮件发送到隔离邮箱。（将邮件发送到隔离邮箱是之一的可配置的操作。）从这些通知中，最终用户可以释放误报和报告给 Microsoft 进行分析。有关详细信息，请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)。为了帮助防止 Office 365 中的垃圾邮件，请使用垃圾邮件筛选，如果您担心 Office 365 中的垃圾邮件太多，使用连接筛选以防止出现垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="96935-p106">**Spam filtering.** Office 365 checks for message characteristics consistent with spam by using spam filtering. You can change what actions to take on messages identified as spam, and choose whether to filter messages written in specific languages, or sent from specific countries or regions. You can also turn on advanced spam filtering options if you want to pursue an aggressive approach to spam filtering. Additionally, you can configure end-user spam notifications to inform users when messages intended for them were sent to the quarantine instead. (Sending messages to the quarantine is one of the configurable actions.) From these notifications, end users can release false positives and report them to Microsoft for analysis. For more information, see [Configure your spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147). In order to help prevent spam in Office 365, use spam filtering, if you're concerned about too much spam in Office 365, use connection filtering to help prevent spam.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96935-p107">为独立 EOP 客户： 默认情况下，EOP 垃圾邮件筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，为了确保**将邮件移至垃圾邮件文件夹**操作将处理的本地邮箱，必须配置两个 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96935-p107">For EOP standalone customers: By default, the EOP spam filters send spam-detected messages to each recipients' Junk Email folder. However, in order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx).</span></span> 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a><span data-ttu-id="96935-134">如果您收到垃圾邮件太多 Office 365 中的额外信息</span><span class="sxs-lookup"><span data-stu-id="96935-134">Extra information if you receive too much spam in Office 365</span></span>

<span data-ttu-id="96935-135">下面的视频提供配置垃圾邮件筛选在 EOP 中的概述。</span><span class="sxs-lookup"><span data-stu-id="96935-135">The following video provides an overview of configuring spam filtering in EOP.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
<span data-ttu-id="96935-136">有关详细信息，请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)主题。</span><span class="sxs-lookup"><span data-stu-id="96935-136">For more details, see the [Configure spam filter policies](https://go.microsoft.com/fwlink/p/?LinkId=617147) topic.</span></span> 
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a><span data-ttu-id="96935-137">检查您的传出消息以防止 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="96935-137">Check your outgoing messages to prevent spam in Office 365</span></span>

 <span data-ttu-id="96935-p108">**出站筛选。** Office 365 还会进行检查以确保您的用户不发送垃圾邮件。例如，用户的计算机可能获取感染后，即可发送垃圾邮件，因此我们构建防范调用*出站筛选*的恶意软件。无法关闭出站筛选，但您可以配置[配置出站垃圾邮件策略](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)中所述的设置。如果您担心 Office 365 中的垃圾邮件太多，则可以使用出站筛选，为了帮助防止 Exchange Online 中的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="96935-p108">**Outbound filtering.** Office 365 also checks to make sure that your users don't send spam. For instance, a user's computer may get infected with malware that causes it to send spam messages, so we build protection against that called  *outbound filtering*  . You can't turn off outbound filtering, but you can configure the settings described in [Configure the outbound spam policy](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx). If you're concerned about too much spam in Office 365, use outbound filtering to help prevent spam in Exchange Online.</span></span>
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a><span data-ttu-id="96935-143">除基础知识： 更多的方式，以防止 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="96935-143">Beyond the basics: More ways to prevent spam in Office 365</span></span>
<span data-ttu-id="96935-144"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="96935-144"></span></span>

 <span data-ttu-id="96935-p109">**邮件流规则。** 如果您希望超越内置垃圾邮件筛选和创建自定义规则的基于业务政策，*[邮件流规则](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*，也称作*传输规则*，帮助您的另一个筛选器阻止 Office 365 中的垃圾邮件。例如，您可以使用邮件流规则设置的垃圾邮件可信度级别 (SCL) 值符合特定条件的邮件[使用设置垃圾邮件可信度 (SCL) 在消息中的邮件流规则](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="96935-p109">**Mail flow rules.** If you want to go beyond built-in spam filtering and create custom rules that are based on your business policies,  *[mail flow rules](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*  , also called  *transport rules*  , are another filter that help you prevent spam in Office 365. For example, you can use mail flow rules to set the spam confidence level (SCL) value for messages that match specific conditions, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx).</span></span> 
  
 <span data-ttu-id="96935-p110">**电子邮件身份验证。** 域名系统 (DNS) 用于将可验证信息添加到有关电子邮件的发件人的电子邮件的技术称为电子邮件身份验证。更高级的 Office 365 管理员可以使用这些电子邮件身份验证方法：</span><span class="sxs-lookup"><span data-stu-id="96935-p110">**Email authentication.** Techniques that use the Domain Name System (DNS) to add verifiable information to email messages about the sender of an email message are called email authentication. More advanced Office 365 admins can make use of these email authentication methods:</span></span> 
  
- <span data-ttu-id="96935-p111">**发件人策略框架 (SPF)。** SPF 通过验证声称的发送域所有者对发件人的 IP 地址来验证电子邮件的原点而言的。快速了解到 SPF 并获取快速配置，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。Office 365 如何使用 SPF，更深入地了解或故障排除或非标准部署如混合部署，启动与[Office 365 如何使用发件人策略框架 (SPF) 以防止欺骗](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96935-p111">**Sender Policy Framework (SPF).** SPF validates the origin of email messages by verifying the IP address of the sender against the alleged owner of the sending domain. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="96935-p112">**域密钥识别邮件 (DKIM)。** DKIM 允许您附加到您发送的电子邮件的电子邮件邮件头中的数字签名。从您的域中接收电子邮件的电子邮件系统使用此数字签名来确定是否合法收到的传入电子邮件。有关 DKIM 和 Office 365 的信息，请参阅[使用 DKIM 验证从您在 Office 365 中的域发送出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96935-p112">**DomainKeys Identified Mail (DKIM).** DKIM lets you attach a digital signature to email messages in the message header of emails you send. Email systems that receive email from your domain use this digital signature to determine if incoming email that they receive is legitimate. For information about DKIM and Office 365, see [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="96935-p113">**基于域的邮件身份验证、 报告和一致性声明 (DMARC)。** 接收邮件系统的 DMARC 帮助确定如何处理失败 SPF 或 DKIM 检查和电子邮件合作伙伴提供其他的信任级别的消息。DMARC 设置的信息，请参阅[使用 DMARC 用于验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="96935-p113">**Domain-based Message Authentication, Reporting, and Conformance (DMARC).** DMARC helps receiving mail systems determine what to do with messages that fail SPF or DKIM checks and provides another level of trust for your email partners. For information on setting up DMARC, see [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
<span data-ttu-id="96935-162">如果您担心垃圾邮件和网络钓鱼欺骗 Office 365 中，使用 SPF、 DKIM 和 DMARC 一起为了帮助防止垃圾邮件和不需要欺骗。</span><span class="sxs-lookup"><span data-stu-id="96935-162">If you're concerned about spam, phishing, and spoofing in Office 365, use SPF, DKIM, and DMARC together to help prevent spam and unwanted spoofing.</span></span>
  
 <span data-ttu-id="96935-p114">**最终用户管理设置。** 如果您正在寻找有关最终用户如何管理他们自己的垃圾邮件设置的信息，则签出[的垃圾邮件筛选器概述](https://go.microsoft.com/fwlink/?LinkId=270065)（针对 Microsoft Outlook 用户） 或[了解垃圾邮件和网络钓鱼](https://go.microsoft.com/fwlink/?LinkId=270068)（对于 web 用户的 Outlook)。如果您使用 EOP 保护本地邮箱，请务必使用目录同步，以确保这些设置都会同步到服务。有关设置目录同步的详细信息，请参阅在[EOP 中的管理邮件用户](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)的"使用目录同步管理邮件用户"。</span><span class="sxs-lookup"><span data-stu-id="96935-p114">**End-user managed settings.** If you're looking for information about how end users can manage their own spam settings, check out [Overview of the Junk Email Filter](https://go.microsoft.com/fwlink/?LinkId=270065) (for Microsoft Outlook users) or [Learn about Junk email and phishing](https://go.microsoft.com/fwlink/?LinkId=270068) (for Outlook on the web users). If you're using EOP to protect on-premises mailboxes, be sure to use directory synchronization to ensure that these settings are synced to the service. For more information about setting up directory synchronization, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="96935-167">详细信息</span><span class="sxs-lookup"><span data-stu-id="96935-167">For more information</span></span>
<span data-ttu-id="96935-168"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="96935-168"></span></span>

[<span data-ttu-id="96935-169">博客： 为什么垃圾邮件和网络钓鱼获取通过 Office 365？</span><span class="sxs-lookup"><span data-stu-id="96935-169">Blog: Why does spam and phishing get through Office 365?</span></span>](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[<span data-ttu-id="96935-170">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="96935-170">Anti-Spam Protection FAQ</span></span>](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="96935-171">使用安全列表或其他技术阻止误报电子邮件被标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="96935-171">Prevent false positive email marked as spam with a safelist or other techniques</span></span>](prevent-email-from-being-marked-as-spam-0.md)
  
[<span data-ttu-id="96935-172">如何设置 Office 365 垃圾邮件筛选以帮助阻止垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="96935-172">How to set up Office 365 spam filtering to help block junk messages</span></span>](block-email-spam-to-prevent-false-negatives.md)
  
[<span data-ttu-id="96935-173">垃圾邮件和批量邮件之间的区别是什么？</span><span class="sxs-lookup"><span data-stu-id="96935-173">What's the Difference Between Junk Email and Bulk Email?</span></span>](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="96935-174">反垃圾邮件邮件头</span><span class="sxs-lookup"><span data-stu-id="96935-174">Anti-spam message headers</span></span>](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="96935-175">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="96935-175">Backscatter Messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  
## <a name="still-need-help"></a><span data-ttu-id="96935-176">仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="96935-176">Still need help?</span></span>
<span data-ttu-id="96935-177"><a name="BeyondBasics"> </a></span><span class="sxs-lookup"><span data-stu-id="96935-177"></span></span>

<span data-ttu-id="96935-178">[![从 Office 365 社区论坛获取帮助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span><span class="sxs-lookup"><span data-stu-id="96935-178">[![Get help from the Office 365 community forums](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span></span>
  
<span data-ttu-id="96935-179">[![管理员：登录并创建一个服务请求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span><span class="sxs-lookup"><span data-stu-id="96935-179">[![Admins: Sign in and create a service request](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span></span>
  
<span data-ttu-id="96935-180">[![管理员：电话支持](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span><span class="sxs-lookup"><span data-stu-id="96935-180">[![Admins: Call Support](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span></span>
  

