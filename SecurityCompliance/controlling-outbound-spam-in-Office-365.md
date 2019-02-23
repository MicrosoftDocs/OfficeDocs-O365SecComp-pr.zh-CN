---
title: 控制 Office 365 中的出站垃圾邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 09/18/2018
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
description: 如果您的组织发送大量垃圾邮件, 并将其标记为垃圾邮件, 则可能会阻止您使用 Office 365 发送电子邮件。阅读本文, 了解有关此操作的原因以及您可以执行的操作的详细信息。
ms.openlocfilehash: 476e1ddff73493881708e050fb7834e6bd6b272a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217332"
---
# <a name="controlling-outbound-spam-in-office-365"></a><span data-ttu-id="c9d4a-104">控制 Office 365 中的出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="c9d4a-104">Controlling outbound spam in Office 365</span></span>

<span data-ttu-id="c9d4a-p102">我们会认真管理出站垃圾邮件, 因为我们是共享服务。 共享资源池背后有许多客户, 如果一个客户发送出站垃圾邮件, 它可能会降低服务的出站 IP 信誉, 并影响其他客户的电子邮件的成功 deliverability。如果 customer B spams 和不同的第三方 IP blocklists 列出了它使用的 ip 地址, 则客户 A 对 customer A 不公平。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p102">We take managing outbound spam seriously because ours is a shared service.  There are many customers behind a shared pool of resources, where if one customer sends outbound spam, it can degrade the outbound IP reputation of the service and affects the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="c9d4a-108">管理员可控制出站垃圾邮件的操作</span><span class="sxs-lookup"><span data-stu-id="c9d4a-108">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="c9d4a-p103">**在帐户发送垃圾邮件或关机时启用通知**。只要邮件被标记为出站垃圾邮件并通过高风险池发送, 管理员就可以获取密件抄送。通过监视此邮箱, 管理员可以检测其网络中是否有受损帐户, 或垃圾邮件筛选器是否错误地将其电子邮件标记为垃圾邮件。 可在[此处](configure-the-outbound-spam-policy.md)找到有关设置出站垃圾邮件策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p103">**Enable notifications when an account is sending spam or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network or if the spam filter is mistakenly marking their email as spam.  More information on setting up the outbound spam policy can be found [here](configure-the-outbound-spam-policy.md).</span></span>
 
- <span data-ttu-id="c9d4a-p104">**手动查看第三方电子邮件提供商发来的垃圾邮件投诉**。许多第三方电子邮件服务 (如 Outlook.com、Yahoo 和 AOL) 都提供反馈循环, 如果服务中的任何用户将我们的服务中的电子邮件标记为垃圾邮件, 则会将该邮件打包并发送回我们进行审阅。若要了解有关 Outlook.com 的发件人支持的详细信息, 请单击[此处](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p104">**Manually review spam complaints from 3rd party email providers**. Many 3rd party email services like Outlook.com, Yahoo and AOL provide a Feedback Loop where if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review. To learn more about sender support for Outlook.com, click [here](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).</span></span>

## <a name="what-eop-does-to-control-outbound-spam"></a><span data-ttu-id="c9d4a-116">控制出站垃圾邮件的 EOP</span><span class="sxs-lookup"><span data-stu-id="c9d4a-116">What EOP does to control outbound spam</span></span> 

1. <span data-ttu-id="c9d4a-p105">将**出站流量分为不同 ip 池中的隔离流量**。将扫描客户通过服务发送出站的每封邮件, 以查找垃圾邮件。如果邮件是垃圾邮件, 它将通过高风险传递池进行路由。此 IP 池包含未送达状态通知和垃圾邮件。不能保证传递给预期收件人, 因为由于它发出电子邮件的质量原因, 许多第三方不会接受电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p105">**Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the High Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.</span></span><br/><br/><span data-ttu-id="c9d4a-p106">以这种方式拆分流量可确保较低质量的电子邮件 (垃圾邮件、退信 ndr) 不会向下拖动常规出站电子邮件池的信誉。在 Internet 周围的多个接收器上, 高风险池通常具有较低的声誉, 尽管这不是通用的。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p106">Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal.</span></span> 

2. <span data-ttu-id="c9d4a-p107">**监视 IP 信誉**。Office 365 查询各种第三方 IP blocklists, 如果其中列出了任何出站 ip, 将生成警报。这使我们能够在垃圾邮件导致名誉下降时快速做出反应。生成警报时, 我们有内部文档外外部要采取什么步骤来获取 delisted。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p107">**Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted.</span></span> 

3. <span data-ttu-id="c9d4a-p108">在**发送过多电子邮件标记为垃圾邮件时禁用违犯的帐户**。即使我们将垃圾邮件和非垃圾邮件隔离成两个单独的出站 IP 池, 电子邮件帐户也无法无限期发送垃圾邮件。我们会监视哪些帐户将发送垃圾邮件, 如果超过 undisclosed 限制, 将阻止该帐户发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p108">**Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds an undisclosed limit, the account is blocked from sending spam.</span></span><br/><br/><span data-ttu-id="c9d4a-p109">标记为垃圾邮件的单个邮件可能是垃圾邮件引擎的 misclassification, 也称为误报。我们将通过高风险池发送它, 为其带来了机会。但是, 短时间内的大量邮件表示存在问题, 在发生此问题时, 将阻止该帐户发送更多的电子邮件。单个电子邮件帐户以及整个租户的聚合中存在不同的阈值。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p109">A single message marked as spam may be a misclassification by the spam engine and also known as a false positive. We send it through the High Risk pool to give it a chance of going out; however, a large number of messages in a short time frame is indicative of a problem and when that occurs, we block the account from sending any more email. There are different thresholds that exist for individual email accounts as well as in aggregate for the entire tenant.</span></span>

4. <span data-ttu-id="c9d4a-p110">在**过短时间内发送电子邮件过多的电子邮件时禁用违犯的帐户**。除了上述限制以查找标记为垃圾邮件的邮件的比例之外, 还会在达到总限制时阻止帐户, 而不管邮件是否被标记为垃圾邮件。此限制存在的原因是因为受到威胁的帐户可能会发送垃圾邮件筛选器错过的零天垃圾邮件。由于很难 (如果不可能), 有时会告知合法大宗邮件市场活动与大量垃圾邮件市场活动之间的区别, 这些限制将激活, 以限制任何可能的损坏。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p110">**Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam. The reason this limit exists is because a compromised account could send zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.</span></span>

> [!NOTE]
> <span data-ttu-id="c9d4a-p111">对于 #3 和 #4, 我们不会公布确切的限制。 这是为了防止垃圾邮件制造者游戏系统, 并确保我们可以在需要时更改限制。这些限制值足够高, 因此一般的业务用户永远不会击中这些限制, 并且其不足以确保垃圾邮件制造者可以执行的大多数损坏。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p111">For both #3 and #4, we do not advertise the exact limits.  This is to prevent spammers from gaming the system and to ensure that we can change the limits when we need to. The limits are high enough such that an average business user will never hit them and low enough that it contains most of the damage a spammer can do.</span></span> 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a><span data-ttu-id="c9d4a-141">对于希望通过 EOP 向出站发送大量电子邮件的客户推荐的解决方法</span><span class="sxs-lookup"><span data-stu-id="c9d4a-141">Recommended workarounds for customers who want to send outbound a lot of email through EOP</span></span>

<span data-ttu-id="c9d4a-p112">如果客户要发送大量的电子邮件, 则需要在客户之间达到平衡, 而不是使用较差的列表获取做法来保护服务免受受损帐户和批量 emailers。此外, 第三方阻止列表上的出站 IP 登录的开销高于阻止客户发送出站电子邮件的成本。如[Exchange Online 服务说明](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits)中所述, 使用 EOP 发送批量电子邮件不是服务的受支持的使用, 并且只允许 "最大努力"。对于想要发送批量电子邮件的客户, 我们建议您执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p112">It is difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices. Again, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. As described in the [Exchange Online Service Description](https://technet.microsoft.com/library/exchange-online-limits.aspx#RecipientLimits), using EOP to send bulk email is not a supported use of the service and is only permitted on a “best-effort” basis. For customers who do want to send bulk email, we recommend the following:</span></span>

1. <span data-ttu-id="c9d4a-p113">**通过其自己的内部部署邮件服务器发送批量电子邮件**。这意味着客户必须为此类电子邮件维护自己的电子邮件基础结构。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p113">**Send the bulk email through its own on-premises mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email.</span></span>

2. <span data-ttu-id="c9d4a-p114">**使用第三方批量 emailer 发送大量通信**。有几个第三方批量 emailers, 其唯一业务是指发送批量电子邮件。他们可以与客户合作, 以确保他们具有良好的电子邮件活动, 并且他们有专门实施它的资源。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p114">**Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it.</span></span> 

<span data-ttu-id="c9d4a-p115">消息传递、移动、恶意软件反滥用工作组 (MAAWG) 将[在此处](http://www.maawg.org/about/roster)发布其成员名单。列表中有多个批量电子邮件提供商, 并且已知它们负责 Internet 公民。</span><span class="sxs-lookup"><span data-stu-id="c9d4a-p115">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster [here](http://www.maawg.org/about/roster). Several bulk email providers are on the list and are known to be responsible Internet citizens.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="c9d4a-153">更多信息</span><span class="sxs-lookup"><span data-stu-id="c9d4a-153">For more information</span></span>

[<span data-ttu-id="c9d4a-154">发件人被阻止发送出站垃圾邮件时的示例通知</span><span class="sxs-lookup"><span data-stu-id="c9d4a-154">Sample notification when a sender is blocked sending outbound spam</span></span>](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[<span data-ttu-id="c9d4a-155">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="c9d4a-155">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="c9d4a-156">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="c9d4a-156">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="c9d4a-157">垃圾邮件可信度</span><span class="sxs-lookup"><span data-stu-id="c9d4a-157">Spam confidence levels</span></span>](spam-confidence-levels.md)
