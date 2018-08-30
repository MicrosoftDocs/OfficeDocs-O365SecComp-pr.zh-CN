---
title: 反垃圾邮件保护常见问题解答
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
description: 本主题提供了有关反垃圾邮件保护的常见问题和解答。 解答适用于 Microsoft Exchange Online 和 Exchange Online Protection (EOP) 客户。
ms.openlocfilehash: 77b3dc26d55f75e7476a3b52a550174a3876c56f
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003071"
---
# <a name="anti-spam-protection-faq"></a><span data-ttu-id="c91f3-104">反垃圾邮件保护常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c91f3-104">Anti-spam protection FAQ</span></span>

<span data-ttu-id="c91f3-p102">本主题提供了有关反垃圾邮件保护的常见问题和解答。 解答适用于 Microsoft Exchange Online 和 Exchange Online Protection (EOP) 客户。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p102">This topic provides frequently asked questions and answers about anti-spam protection. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection (EOP) customers.</span></span> 
  
> [!TIP]
> <span data-ttu-id="c91f3-p103">有关问题和解答有关安全发件人和阻止发件人列表，请参阅[安全发件人和阻止发件人列表在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)。有关问题和解答有关隔离，请参阅[隔离常见问题解答](quarantine-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p103">For questions and answers about safe sender and blocked sender lists, see [Safe sender and blocked sender lists in Exchange Online](safe-sender-and-blocked-sender-lists-faq.md). For questions and answers about the quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span> 
  
 <span data-ttu-id="c91f3-109">**问：默认情况下，如何处理检测到的垃圾邮件？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-109">**Q. By default, what happens to a spam-detected message?**</span></span>
  
<span data-ttu-id="c91f3-p104">A. **对于入站邮件：** 大部分垃圾邮件都是通过基于发件人 IP 地址的连接筛选检测到的。 然后，服务会检查邮件内容。 默认情况下，内容筛选的垃圾邮件会发送到发件人的垃圾邮件文件夹。 可以更改此操作。 例如，可以选择将垃圾邮件发送到隔离区，而不是配置内容筛选策略。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p104">A. **For inbound messages:** The majority of spam is deleted via connection filtering, which is based on the IP address of the sender. The service then inspects the contents of the message. By default, content-filtered spam is sent to the recipient's Junk Email folder. You can change this action. For example, you can choose to send spam messages to the quarantine instead by configuring the content filter policy.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c91f3-p105">为独立 EOP 客户： 为了确保**移动到垃圾邮件文件夹的邮件**操作将处理的本地邮箱，必须配置这两种 Exchange 传输规则，来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p105">For EOP standalone customers: In order to ensure that the **Move message to Junk Email folder** action will work with on-premises mailboxes, you must configure two Exchange Transport rules on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
 <span data-ttu-id="c91f3-118">**对于出站邮件：** 邮件要么通过高风险传递池进行路由，要么被退回、未传递。不管是哪种情况，发件人都会收到一封告知其邮件未传递的传递状态通知 (DSN) 邮件。</span><span class="sxs-lookup"><span data-stu-id="c91f3-118">**For outbound messages:** The message is either routed through the higher risk delivery pool or is bounced and not delivered, in which case the sender should receive a delivery status notification (DSN) message telling them that the message couldn't be delivered.</span></span> 
  
 <span data-ttu-id="c91f3-119">**问：什么是零日垃圾邮件变体，该服务将如何处理它？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-119">**Q. What's a zero-day spam variant and how is it handled by the service?**</span></span>
  
<span data-ttu-id="c91f3-p106">答： 零时差垃圾邮件 variant 是第一代、 以前未知的垃圾邮件永远不会已捕获或分析，variant，因此我们垃圾邮件内容筛选器尚未没有可用于检测其任何信息。零时差垃圾邮件后示例是捕获和分析我们垃圾邮件分析师，如果它符合垃圾邮件分类标准，我们垃圾邮件内容筛选器更新来检测，并且它不再被认为"零时差。"(**注意：** 如果您收到一条消息，以帮助我们改善服务可能 variant 零时差垃圾邮件，请将邮件提交给 Microsoft 使用[提交垃圾邮件、 非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 的中所述的方法之一分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。)</span><span class="sxs-lookup"><span data-stu-id="c91f3-p106">A. A zero-day spam variant is a first generation, previously unknown variant of spam that's never been captured or analyzed, so our spam content filters don't yet have any information available for detecting it. After a zero-day spam sample is captured and analyzed by our spam analysts, if it meets the spam classification criteria, our spam content filters are updated to detect it, and it's no longer considered "zero-day." ( **Note:** If you receive a message that may be a zero-day spam variant, in order to help us improve the service, please submit the message to Microsoft using one of the methods described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).)</span></span>
  
 <span data-ttu-id="c91f3-124">**问：我需要配置用于提供反垃圾邮件保护的服务吗？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-124">**Q. Do I need to configure the service to provide anti-spam protection?**</span></span>
  
<span data-ttu-id="c91f3-p107">答：在您注册服务和添加域之后，反垃圾邮件筛选通过默认反垃圾邮件策略在全公司自动启用。 无需进行任何其他配置，即可优化默认策略，为您提供保护（除了上文提及的针对 EOP 独立客户的例外情况以外）。 作为管理员，您可以编辑默认反垃圾邮件策略，以便最好地满足贵组织的需求。 更精确地讲，您也可以创建自定义内容筛选策略，并将其应用到特定的用户、组或者组织中的域。 自定义策略的优先级总是高于默认策略，但您可以更改自定义策略的优先级（即运行顺序）。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p107">A. After you sign up for the service and add your domain, spam filtering is automatically enabled company-wide through the default anti-spam policies. The default policies are tuned to protect you without needing any additional configuration (aside from the exception noted above for EOP standalone customers). As an admin, you can edit the default anti-spam policies so that they're tailored to best meet the needs of your organization. For greater granularity, you can also create custom content filter policies and apply them to specified users, groups, or domains in your organization. Custom policies always take precedence over the default policy, but you can change the priority (that is, the running order) of your custom policies.</span></span>
  
<span data-ttu-id="c91f3-131">有关配置反垃圾邮件策略的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="c91f3-131">For more about configuring your anti-spam policies, see the following topics:</span></span>
  
[<span data-ttu-id="c91f3-132">配置连接筛选器策略</span><span class="sxs-lookup"><span data-stu-id="c91f3-132">Configure the connection filter policy</span></span>](configure-the-connection-filter-policy.md)
  
[<span data-ttu-id="c91f3-133">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="c91f3-133">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
[<span data-ttu-id="c91f3-134">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="c91f3-134">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
 <span data-ttu-id="c91f3-135">**问：如果我对一个反垃圾邮件策略进行了更改，更改保存之后需要多久才会生效？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-135">**Q. If I make a change to an anti-spam policy, how long does it take after I save my changes for them to take effect?**</span></span>
  
<span data-ttu-id="c91f3-p108">答：可能需要 1 小时，更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p108">A. It may take up to 1 hour for the changes to take effect.</span></span>
  
 <span data-ttu-id="c91f3-138">**问：批量电子邮件筛选会自动启用吗？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-138">**Q. Is bulk email filtering automatically enabled?**</span></span>
  
<span data-ttu-id="c91f3-p109">答： 默认情况下，为新客户启用**批量邮件**高级垃圾邮件筛选选项。对于已迁移的客户，此设置将匹配您的 FOPE 配置。有关批量电子邮件的详细信息，请参阅[垃圾邮件和批量邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c91f3-p109">A. By default, the **Bulk mail** advanced spam filtering option is enabled for new customers. For migrated customers, this setting will match your FOPE configuration. For more information about bulk email, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>
  
 <span data-ttu-id="c91f3-143">**问：该服务是否提供 URL 筛选？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-143">**Q. Does the service provide URL filtering?**</span></span>
  
<span data-ttu-id="c91f3-p110">答：提供，该服务具有可检查邮件内的 URL 的 URL 筛选器。 如果检测到与已知垃圾邮件或恶意内容相关联的 URL，则将该邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p110">A. Yes the service has a URL filter that checks for URLs within messages. If URLs associated with known spam or malicious content are detected then the message is marked as spam.</span></span>
  
 <span data-ttu-id="c91f3-147">**问：客户如何使用此服务将假负（垃圾邮件）和误报（非垃圾邮件）邮件发送到 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-147">**Q. How can customers using the service send false negative (spam) and false positive (non-spam) messages to Microsoft?**</span></span>
  
<span data-ttu-id="c91f3-p111">答： 垃圾邮件和非垃圾邮件可以分析多种方式提交给 Microsoft。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p111">A. Spam and non-spam messages can be submitted to Microsoft for analysis in several ways. For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="c91f3-151">**问：我可以获取垃圾邮件报告吗？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-151">**Q. Can I get spam reports?**</span></span>
  
<span data-ttu-id="c91f3-p112">答：可以，例如，您可以在 Office 365 管理中心中获取垃圾邮件检测报告。 此报告将垃圾邮件数量显示为唯一邮件的计数。 有关报告的详细信息，请参阅下列链接：</span><span class="sxs-lookup"><span data-stu-id="c91f3-p112">A. Yes, for example you can get a spam detection report in the Office 365 admin center. This report shows spam volume as a count of unique messages. For more information about reporting, see the following links:</span></span>
  
<span data-ttu-id="c91f3-156">Exchange Online 客户：[监视、 报告和邮件跟踪在 Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span><span class="sxs-lookup"><span data-stu-id="c91f3-156">Exchange Online customers: [Monitoring, Reporting, and Message Tracing in Exchange Online](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)</span></span>
  
<span data-ttu-id="c91f3-157">Exchange Online Protection 客户：[报告和邮件跟踪在 Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span><span class="sxs-lookup"><span data-stu-id="c91f3-157">Exchange Online Protection customers: [Reporting and message trace in Exchange Online Protection](eop/reporting-and-message-trace-in-exchange-online-protection.md)</span></span>
  
 <span data-ttu-id="c91f3-158">**问：有人发送一封邮件给我，但是我找不到它。 我怀疑此邮件可能被检测为垃圾邮件了。 有什么工具可以让我找到这封邮件吗？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-158">**Q. Someone sent me a message and I can't find it. I suspect that it may have been detected as spam. Is there a tool that I can use to find out?**</span></span>
  
<span data-ttu-id="c91f3-p113">答：有的，邮件跟踪工具可以使您在电子邮件通过服务时跟踪它们，以了解所发生的情况。 有关如何使用邮件跟踪工具找到邮件被标识为垃圾邮件的原因的详细信息，请参阅[邮件被标记为垃圾邮件？](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)</span><span class="sxs-lookup"><span data-stu-id="c91f3-p113">A. Yes, the message trace tool enables you to follow email messages as they pass through the service, in order to find out what happened to them. For more information about how to use the message trace tool to find out why a message was marked as spam, see [Was a message marked as spam? ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)</span></span>
  
 <span data-ttu-id="c91f3-162">**问：如果我的用户发送出站垃圾邮件，服务将会限制（速率限制）我的邮件吗？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-162">**Q. Will the service throttle (rate limit) my mail if my users send outbound spam?**</span></span>
  
<span data-ttu-id="c91f3-p114">A.如果通过服务发送自用户的超过一半的邮件是在某段时间范围内（例如，每小时）发送的，则邮件被 Office 365 确定为垃圾邮件，该用户将被阻止发送邮件。大多数情况下，如果出站邮件确定为垃圾邮件，将会通过高风险传送池路由，这会降低正常的出站 IP 池添加至阻止列表的可能性。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p114">A. If more than half of the mail that is sent from a user through the service within a certain time frame (for example, per hour), is determined to be spam by Office 365, the user will be blocked from sending messages. In most cases, if an outbound message is determined to be spam, it is routed through the high-risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span>
  
<span data-ttu-id="c91f3-p115">当发件人被阻止发送出站垃圾邮件时，您可以发送通知到一个特定的电子邮件地址。 有关此设置的详细信息，请参阅[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p115">You can send a notification to a specified email address when a sender is blocked sending outbound spam. For more information about this setting, see [Configure the outbound spam policy](configure-the-outbound-spam-policy.md).</span></span>
  
 <span data-ttu-id="c91f3-168">**问：是否可以与 Exchange Online 同时使用第三方反垃圾邮件和反恶意软件提供程序？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-168">**Q. Can I use a third-party anti-spam and anti-malware provider in conjunction with Exchange Online?**</span></span>
  
<span data-ttu-id="c91f3-p116">答：可以，您可以配置另一个垃圾邮件和恶意软件筛选服务来保护 Exchange Online 邮箱。 要对入站邮件执行此操作，您应通过将 MX 记录更改为指向第三方提供程序来将电子邮件重定向到第三方提供程序，然后将邮件重定向到 EOP 进行其他处理。 要对出站邮件执行此操作，请将邮件传递目标配置为第三方提供程序（智能主机），如[Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)中所示。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p116">A. Yes, you may configure another spam and malware filtering service to protect your Exchange Online mailboxes. To do this for inbound mail, you should redirect your email messages to the third-party provider by changing your MX records to point to the third-party provider, and then redirect the messages to EOP for additional processing. To do this for outbound mail, please configure the message delivery destination to the third-party provider (smart host), as shown in [Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx).</span></span>
  
 <span data-ttu-id="c91f3-173">**Q. Microsoft 是否拥有任何有关如何保护自己免受网络钓鱼诈骗之害的文档？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-173">**Q. Does Microsoft have any documentation about how I can protect myself from phishing scams?**</span></span>
  
<span data-ttu-id="c91f3-p117">答：我们有。请参阅下列文章：</span><span class="sxs-lookup"><span data-stu-id="c91f3-p117">A. Yes we do, please consult the following articles:</span></span>
  
[<span data-ttu-id="c91f3-176">获取有关网络钓鱼诈骗、彩票欺诈和其他类型的诈骗的帮助</span><span class="sxs-lookup"><span data-stu-id="c91f3-176">Get help with phishing scams, lottery fraud, and other types of scams</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[<span data-ttu-id="c91f3-177">电子邮件和网络诈骗： 如何保护自己</span><span class="sxs-lookup"><span data-stu-id="c91f3-177">Email and web scams: How to help protect yourself</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 <span data-ttu-id="c91f3-178">**问：正在调查将垃圾邮件和恶意邮件发送给谁，还是正在移交给执法机构？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-178">**Q. Are spam and malware messages being investigated as to who sent them, or being transferred to law enforcement entities?**</span></span>
  
<span data-ttu-id="c91f3-p118">答：此服务专注于垃圾邮件和恶意软件检测和删除，尽管我们可能有时会专门调查危险或破坏性的垃圾邮件或攻击活动，并找到肇事者。 这可能涉及与法律和数字犯罪机构合作，以击溃垃圾邮件制造者僵尸网络、阻止垃圾邮件制造者使用服务（如果他们使用此服务来向外发送邮件）并向执法机构提供刑事诉讼的相关信息。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p118">A. The service focuses on spam and malware detection and removal, though we may occasionally investigate especially dangerous or damaging spam or attack campaigns and pursue the perpetrators. This may involve working with our legal and digital crime units to take down a spammer botnet, blocking the spammer from using the service (if they're using it for sending outbound email), and passing the information on to law enforcement for criminal prosecution.</span></span>
  
 <span data-ttu-id="c91f3-182">**问：确保我的电子邮件已发送的一系列发送出站电子邮件的最佳做法是什么？**</span><span class="sxs-lookup"><span data-stu-id="c91f3-182">**Q. What are a set of best outbound mailing practices that will ensure that my mail is delivered?**</span></span>
  
<span data-ttu-id="c91f3-p119">答：以下所述的指导是发送出站电子邮件的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p119">A. The guidelines presented below are best practices for sending outbound email messages.</span></span>
  
1. <span data-ttu-id="c91f3-185">**电子邮件的发送域应在 DNS 中解析。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-185">**The sending domain of the email should resolve in DNS.**</span></span>
    
    <span data-ttu-id="c91f3-p120">例如，如果发件人，user@example.com 域 example.com 解析为 IP 地址 192.0.43.10 发送。如果发送域没有 A 记录，并且在 DNS 中，服务没有 MX 记录将通过其高风险传递池无论消息的内容是否是垃圾邮件路由邮件。有关高风险传递池的详细信息，请参阅[高风险传递池用于出站邮件](high-risk-delivery-pool-for-outbound-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p120">For example, if the sender is user@example.com, the domain example.com resolves to the IP address 192.0.43.10. If a sending domain has no A-record and no MX record in DNS, the service will route the message through its higher risk delivery pool regardless of whether or not the content of the message is spam. For more information about the higher risk delivery pool, see [High-risk delivery pool for outbound messages](high-risk-delivery-pool-for-outbound-messages.md).</span></span> 
    
2. <span data-ttu-id="c91f3-189">**出站电子邮件服务器的发送 IP 地址应该有一个反向 DNS (PTR) 条目。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-189">**The sending IP address of the outbound mail server should have a reverse DNS (PTR) entry.**</span></span>
    
    <span data-ttu-id="c91f3-190">例如，如果从 IP 地址 192.0.43.10 发送，该 IP 的反向 DNS 条目就是 43-10.any.icann.org。</span><span class="sxs-lookup"><span data-stu-id="c91f3-190">For example, if sending from the IP address 192.0.43.10, the reverse DNS entry for this IP is 43-10.any.icann.org.</span></span> 
    
3. <span data-ttu-id="c91f3-191">**HELO/EHLO 和 MAIL FROM 命令需要保持一致，并且不是以 IP 地址形式呈现，而是以域名形式呈现。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-191">**The HELO/EHLO and MAIL FROM commands should be consistent and be present in the form of a domain name rather than an IP address.**</span></span>
    
    <span data-ttu-id="c91f3-192">HELO/EHLO 命令需要配置成与发送 IP 地址的反向 DNS 相匹配，使域在邮件头的各个部分保持相同。</span><span class="sxs-lookup"><span data-stu-id="c91f3-192">The HELO/EHLO command should be configured to match the reverse DNS of the sending IP address so that the domain remains the same across the various parts of the message headers.</span></span>
    
4. <span data-ttu-id="c91f3-193">**确保在 DNS 中设置了正确的 SPF。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-193">**Ensure that proper SPF records are set up in DNS.**</span></span>
    
    <span data-ttu-id="c91f3-p121">SPF 记录是一种机制，用于验证从域发出的邮件是否确实来自域并且不带有欺骗性质。 有关 SPF 记录的详细信息，请参阅下列链接：</span><span class="sxs-lookup"><span data-stu-id="c91f3-p121">SPF records are a mechanism for validating that mail sent from a domain really is coming from that domain and is not spoofed. For more information about SPF records, see the following links:</span></span>
    
    [<span data-ttu-id="c91f3-196">在 Office 365 中设置 SPF 以防止欺骗</span><span class="sxs-lookup"><span data-stu-id="c91f3-196">Set up SPF in Office 365 to help prevent spoofing</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [<span data-ttu-id="c91f3-197">为 Office 365 创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c91f3-197">Create DNS records for Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. <span data-ttu-id="c91f3-198">**使用 DKIM 对电子邮件签名，用较宽松的规范签名。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-198">**Signing email with DKIM, sign with relaxed canonicalization.**</span></span>
    
    <span data-ttu-id="c91f3-p122">如果发件人希望使用域名密钥识别邮件标准 (DKIM) 对邮件签名，并想通过服务发送出站电子邮件，需要使用较宽松的标头规范化算法签名。 用严格的标头规范签名可能导致签名通过服务时变得无效。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p122">If a sender wants to sign their messages using Domain Keys Identified Mail (DKIM) and they want to send outbound mail through the service, they should sign using the relaxed header canonicalization algorithm. Signing with strict header canonicalization may invalidate the signature when it passes through the service.</span></span>
    
6. <span data-ttu-id="c91f3-201">**域所有者在 WHOIS 数据库中需要有正确的信息。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-201">**Domain owners should have accurate information in the WHOIS database.**</span></span>
    
    <span data-ttu-id="c91f3-202">这标识了域所有者以及如何通过稳定的父公司、联系点和名称服务器联系他们。</span><span class="sxs-lookup"><span data-stu-id="c91f3-202">This identifies the owners of the domain and how to contact them by entering the stable parent company, point of contact, and name servers.</span></span>
    
7. <span data-ttu-id="c91f3-203">**对于邮件群发程序，发件人： 名字需要反映发送邮件的人，而邮件的主题行应该是对邮件内容的简短摘要。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-203">**For bulk mailers, the From: name should reflect who is sending the message, while the subject line of the message should be a brief summary on what the message is about.**</span></span>
    
    <span data-ttu-id="c91f3-p123">邮件正文应该对提供内容、服务或产品有一个清楚的说明。 例如，如果发件人为 Contoso 公司发送一个群发邮件，电子邮件的"发件人"以及"主题"应与以下内容类似：</span><span class="sxs-lookup"><span data-stu-id="c91f3-p123">The message body should have a clear indication of the offering, service, or product. For example, if a sender is sending out a bulk mailing for the Contoso company, the following is what the email From and Subject should resemble:</span></span>
    
    <span data-ttu-id="c91f3-206">发件人： marketing@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c91f3-206">From: marketing@contoso.com</span></span>
    
    <span data-ttu-id="c91f3-207">主题： 圣诞季的新更新目录！</span><span class="sxs-lookup"><span data-stu-id="c91f3-207">Subject: New updated catalog for the Christmas season!</span></span> 
    
    <span data-ttu-id="c91f3-208">以下是不能执行的操作的一个示例，因为该示例是非描述性的：</span><span class="sxs-lookup"><span data-stu-id="c91f3-208">The following is an example of what not to do because it is not descriptive:</span></span>
    
    <span data-ttu-id="c91f3-209">发件人： user@hotmail.com</span><span class="sxs-lookup"><span data-stu-id="c91f3-209">From: user@hotmail.com</span></span>
    
    <span data-ttu-id="c91f3-210">主题： 目录</span><span class="sxs-lookup"><span data-stu-id="c91f3-210">Subject: Catalogs</span></span>
    
8. <span data-ttu-id="c91f3-211">**如果将群发邮件发送给很多个收件人，并且邮件是新闻稿的格式，那么在邮件底部应该存在取消订阅的方法。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-211">**If sending a bulk mailing to many recipients and the message is in newsletter format, there should be a way of unsubscribing at the bottom of the message.**</span></span>
    
    <span data-ttu-id="c91f3-212">取消订阅的选项应该与以下内容相似：</span><span class="sxs-lookup"><span data-stu-id="c91f3-212">The unsubscribe option should resemble the following:</span></span>
    
    <span data-ttu-id="c91f3-p124">该邮件由 sender@fabrikam.com 发送给 example@contoso.com。更新配置文件/电子邮件地址 | 通过 **SafeUnsubscribe** 即时删除 | 隐私策略</span><span class="sxs-lookup"><span data-stu-id="c91f3-p124">This message was sent to example@contoso.com by sender@fabrikam.com. Update Profile/Email Address | Instant removal with **SafeUnsubscribe**™ | Privacy Policy</span></span>
    
9. <span data-ttu-id="c91f3-215">**如果发送群发邮件，需使用双重选择执行列表获取。如果您是一个邮件群发者，双重选择是行业的最佳做法。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-215">**If sending bulk email, list acquisition should be performed using double opt-in. If you are a bulk mailer, double opt-in is an industry best practice.**</span></span>
    
    <span data-ttu-id="c91f3-216">双重加入是要求用户采取以下两种操作注册市场邮件的做法。</span><span class="sxs-lookup"><span data-stu-id="c91f3-216">Double opt-in is the practice of requiring a user to take two actions to sign up for marketing mail:</span></span>
    
1. <span data-ttu-id="c91f3-217">第一次在用户单击一个之前未选中的复选框（其中他们选择接收营销人员发送的其他促销或电子邮件）时选择。</span><span class="sxs-lookup"><span data-stu-id="c91f3-217">Once when the user clicks on a previously unchecked check box where they opt-in to receive further offers or email messages from the marketer.</span></span>
    
2. <span data-ttu-id="c91f3-218">第二次在营销人员向用户提供的电子邮件地址发送确认邮件，要求用户在时间敏感型链接上单击时选择。</span><span class="sxs-lookup"><span data-stu-id="c91f3-218">A second time when the marketer sends a confirmation email to the user's provided email address asking them to click on a time-sensitive link that will complete their confirmation.</span></span>
    
    <span data-ttu-id="c91f3-219">使用双重选择为群发邮件发件人构建良好的信誉。</span><span class="sxs-lookup"><span data-stu-id="c91f3-219">Using double opt-in builds a good reputation for bulk email senders.</span></span>
    
10. <span data-ttu-id="c91f3-220">**群发邮件发件人应创建透明内容，以便他们负起责任：**</span><span class="sxs-lookup"><span data-stu-id="c91f3-220">**Bulk senders should create transparent content for which they can be held accountable:**</span></span>
    
1. <span data-ttu-id="c91f3-221">收件人将发件人添加到通讯簿上的冗长请求应清楚地表明这些操作无法保证邮件传送的安全性。</span><span class="sxs-lookup"><span data-stu-id="c91f3-221">Verbiage requesting that recipients add the sender to the address book should clearly state that such action is not a guarantee of delivery.</span></span>
    
2. <span data-ttu-id="c91f3-222">当在邮件正文构建重定向时，使用一致的链接样式。</span><span class="sxs-lookup"><span data-stu-id="c91f3-222">When constructing redirects in the body of the message, use a consistent link style.</span></span>
    
3. <span data-ttu-id="c91f3-223">请不要发送大容量图片或附件，或仅含一张图片的邮件。</span><span class="sxs-lookup"><span data-stu-id="c91f3-223">Don't send large images or attachments, or messages that are solely composed of an image.</span></span>
    
4. <span data-ttu-id="c91f3-224">当采用跟踪像素（网络臭虫或信号），清楚地说明公开隐私或 P3P 设置。</span><span class="sxs-lookup"><span data-stu-id="c91f3-224">When employing tracking pixels (web bugs or beacons), clearly state their presence in your public privacy or P3P settings.</span></span>
    
11. <span data-ttu-id="c91f3-225">**格式出站传输状态通知。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-225">**Format outbound delivery status notifications.**</span></span>
    
    <span data-ttu-id="c91f3-226">当生成传送状态通知邮件时，发件人需按照 [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715) 指定的退回格式发送邮件。</span><span class="sxs-lookup"><span data-stu-id="c91f3-226">When generating delivery status notification messages, senders should follow the format of a bounce as specified in [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715).</span></span>
    
12. <span data-ttu-id="c91f3-227">**清除退回的不存在用户的电子邮件地址。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-227">**Remove bounced email addresses for non-existent users.**</span></span>
    
    <span data-ttu-id="c91f3-p125">如果您接收到一个指示不再使用某电子邮件地址的 NDR，请从列表中清除不存在的电子邮件别名。 电子邮件地址会随时间发生变化，大家有时会丢弃这些地址。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p125">If you receive an NDR indicating that an email address is no longer in use, remove the non-existent email alias from your list. Email addresses change over time, and people sometimes discard them.</span></span>
    
13. <span data-ttu-id="c91f3-230">**使用 Hotmail 的智能网络数据服务 (SNDS) 程序。**</span><span class="sxs-lookup"><span data-stu-id="c91f3-230">**Use Hotmail's Smart Network Data Services (SNDS) program.**</span></span>
    
    <span data-ttu-id="c91f3-p126">Hotmail 使用名为智能网络数据服务的程序，使发件人可以检查最终用户提交的抱怨。 SNDS 是疑难解答 Hotmail 传送问题的初始门户。</span><span class="sxs-lookup"><span data-stu-id="c91f3-p126">Hotmail uses a program called Smart Network Data Services that allows senders to check complaints submitted by end users. The SNDS is the primary portal for troubleshooting delivery problems to Hotmail.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="c91f3-233">详细信息</span><span class="sxs-lookup"><span data-stu-id="c91f3-233">For more information</span></span>

[<span data-ttu-id="c91f3-234">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="c91f3-234">Office 365 Email Anti-Spam Protection</span></span>](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[<span data-ttu-id="c91f3-235">Exchange Online 中的安全发件人和阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="c91f3-235">Safe sender and blocked sender lists in Exchange Online</span></span>](safe-sender-and-blocked-sender-lists-faq.md)
  
[<span data-ttu-id="c91f3-236">反垃圾邮件邮件头</span><span class="sxs-lookup"><span data-stu-id="c91f3-236">Anti-spam message headers</span></span>](anti-spam-message-headers.md)
  
[<span data-ttu-id="c91f3-237">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="c91f3-237">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
  

