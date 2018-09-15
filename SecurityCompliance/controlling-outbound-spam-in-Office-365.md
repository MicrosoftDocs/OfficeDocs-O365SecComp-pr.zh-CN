---
title: 控制在 Office 365 中的出站垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/13/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 如果您的组织发送大量的批量邮件标记为垃圾邮件，您无法获取阻止发送电子邮件与 Office 365。阅读此文，了解有关发生此问题，以及有关该产品可实现的功能。
ms.openlocfilehash: 1e416ded5a7d91376a75075e5de1de60bc8a205b
ms.sourcegitcommit: 17dda7ece5c9e884944a92ac0f842cf1e62ec506
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "23979498"
---
# <a name="controlling-outbound-spam-in-office-365"></a><span data-ttu-id="140dd-104">控制在 Office 365 中的出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="140dd-104">Controlling outbound spam in Office 365</span></span>

<span data-ttu-id="140dd-p102">我们需要认真地管理出站垃圾邮件，因为我们是共享的服务。 有许多客户后面共享资源，其中如果一个客户发送出站垃圾邮件，则它会降低服务的出站 IP 信誉和影响的其他客户的电子邮件的成功的可交付性池中。如果客户 B 会发送垃圾邮件和各种第三方 IP blocklists 列表它使用的 IP 地址，则向客户 A 不平等。</span><span class="sxs-lookup"><span data-stu-id="140dd-p102">We take managing outbound spam seriously because ours is a shared service.  There are many customers behind a shared pool of resources, where if one customer sends outbound spam, it can degrade the outbound IP reputation of the service and affects the successful deliverability of email for other customers. It is unfair to Customer A if Customer B spams and various 3rd party IP blocklists list the IP address that it uses.</span></span>

## <a name="what-admins-can-do-to-control-outbound-spam"></a><span data-ttu-id="140dd-108">管理员可以做什么控制出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="140dd-108">What admins can do to control outbound spam</span></span>

- <span data-ttu-id="140dd-p103">**启用通知时发送垃圾邮件或关闭帐户**。管理员可以获取密，每当消息被标记为出站垃圾邮件并发送通过高风险池。通过监视此邮箱，管理员可以检测到，如果其网络中都拥有受到攻击的帐户或者垃圾邮件筛选器地将其标记为垃圾邮件其电子邮件。 设置出站垃圾邮件策略的详细信息可以找到[此处](configure-the-outbound-spam-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="140dd-p103">**Enable notifications when an account is sending spam or shut down**. Administrators can get bcc’ed whenever a message is marked as outbound spam and sent through the High Risk pool. By monitoring this mailbox, an admin can detect if they have a compromised account in their network or if the spam filter is mistakenly marking their email as spam.  More information on setting up the outbound spam policy can be found [here](configure-the-outbound-spam-policy.md).</span></span>
 
- <span data-ttu-id="140dd-p104">**手动查看从第三方电子邮件提供商的垃圾邮件投诉**。许多第三方电子邮件服务如 Outlook.com、 Yahoo 和 AOL 提供反馈循环其中其服务中的任何用户标记为垃圾邮件我们服务从电子邮件，如果邮件是打包，回向我们发送候审。若要了解有关 Outlook.com 的发件人支持的详细信息，请单击[此处](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。</span><span class="sxs-lookup"><span data-stu-id="140dd-p104">**Manually review spam complaints from 3rd party email providers**. Many 3rd party email services like Outlook.com, Yahoo and AOL provide a Feedback Loop where if any user in their service marks an email from our service as spam, the message is packaged up and sent back to us for review. To learn more about sender support for Outlook.com, click [here](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).</span></span>

## <a name="what-eop-does-to-control-outbound-spam"></a><span data-ttu-id="140dd-116">EOP 用途控制出站垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="140dd-116">What EOP does to control outbound spam</span></span> 

1. <span data-ttu-id="140dd-p105">**职责划分到单独的 Ip 的池的出站通信**。为垃圾邮件扫描客户发送出站通过服务每条消息。如果邮件是垃圾邮件，它通过高风险传递池路由。该 IP 池包含非可交付结果的状态通知和垃圾邮件。不能保证传递到预期接收人，如许多第三方将不会接受电子邮件，因为它发出的电子邮件的质量。</span><span class="sxs-lookup"><span data-stu-id="140dd-p105">**Segregation of outbound traffic into separate pools of IPs**. Every message that customers send outbound through the service is scanned for spam. If the message is spam, it is routed through the High Risk Delivery pool. This IP pool contains non-deliverable status notifications and spam. Delivery to the intended recipient is not guaranteed as many third parties will not accept email because the quality of email it emits.</span></span>

<span data-ttu-id="140dd-p106">拆分流量这样可确保低品质电子邮件 （垃圾邮件，Ndr 退信） 不拖动下的正则出站电子邮件池信誉。高风险池通常具有低信誉在很多接收器周围 Internet，尽管这不是通用。</span><span class="sxs-lookup"><span data-stu-id="140dd-p106">Splitting the traffic this way ensures that the lower quality email (spam, backscatter NDRs) does not drag down the reputation of the regular outbound email pools. The high risk pool typically has low reputation at many receivers around the Internet, although this is not universal.</span></span> 

2. <span data-ttu-id="140dd-p107">**监控的 IP 信誉**。Office 365 查询各种第三方 IP blocklists 和如果我们出站 Ip 任一排列这些生成警报。这样，我们时垃圾邮件已导致我们信誉降低快速做出反应。生成警报时，我们具有内部文档外围需要获取列表中清除哪些步骤。</span><span class="sxs-lookup"><span data-stu-id="140dd-p107">**Monitoring of IP reputation**. Office 365 queries various 3rd party IP blocklists and generates alerts if any of our outbound IPs are listed on them. This allows us to react quickly when spam has caused our reputation to degrade. When an alert is generated, we have internal documentation outlying what steps to take to get delisted.</span></span> 

3. <span data-ttu-id="140dd-p108">**禁用的其余部分帐户发送太多电子邮件时标记为垃圾邮件**。尽管我们将数据库分隔到我们的垃圾邮件和非垃圾邮件到两个单独的出站 IP 池，电子邮件帐户不能无限期地发送垃圾邮件。我们监视其帐户发送垃圾邮件，并且如果它超出披露的限制，阻止帐户发送垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="140dd-p108">**Disabling of offending accounts when they send too much email marked as spam**. Even though we segregate our spam and non-spam into two separate outbound IP pools,  the email accounts cannot send spam indefinitely. We monitor which accounts are sending spam and if it exceeds an undisclosed limit, the account is blocked from sending spam.</span></span>

<span data-ttu-id="140dd-p109">单个邮件标记为垃圾邮件可能是垃圾邮件引擎和也称为误报 misclassification。我们要为其提供的传出; 有机会的高风险池通过发送但是，大量的短时间框架中的消息表明问题以及的发生时，我们阻止从发送任何多个电子邮件帐户。有不同存在单个电子邮件帐户以及聚合整个租户的阈值。</span><span class="sxs-lookup"><span data-stu-id="140dd-p109">A single message marked as spam may be a misclassification by the spam engine and also known as a false positive. We send it through the High Risk pool to give it a chance of going out; however, a large number of messages in a short time frame is indicative of a problem and when that occurs, we block the account from sending any more email. There are different thresholds that exist for individual email accounts as well as in aggregate for the entire tenant.</span></span>

4. <span data-ttu-id="140dd-p110">**禁用的其余部分帐户发送太多太短时间框架中的电子邮件时**。除了上面的标记为垃圾邮件的邮件比例的外观的限制，还有时到达总体无论将邮件标记为垃圾邮件限制阻止帐户的限制。存在此限制的原因是因为受到攻击的帐户无法发送垃圾邮件筛选器的已错过的零时差垃圾邮件。如果可能，有时会让合法批量邮件活动和大规模垃圾邮件市场活动之间的差异很难，，因为这些限制激活限制任何潜在损坏。</span><span class="sxs-lookup"><span data-stu-id="140dd-p110">**Disabling of offending accounts when they send too much email in too short a time frame**. In addition to the limits above that look for a proportion of messages marked as spam, there are also limits that block accounts when they reach an overall limit regardless of whether or not the messages are marked as spam. The reason this limit exists is because a compromised account could send zero-day spam that is missed by the spam filter. Because it is difficult, if not impossible, to sometimes tell the difference between a legitimate mass mailing campaign and a massive spam campaign, these limits activate to limit any potential damage.</span></span>

> [!NOTE]
> <span data-ttu-id="140dd-p111">#3 和 4 中，我们不公布准确的限制。 这是以阻止垃圾邮件游戏系统的发送者并确保，我们在需要时，我们可以更改的限制。限制为足够高，以便平均业务用户将从不命中它们和低，它包含的大多数破坏垃圾消息发送者可以执行操作。</span><span class="sxs-lookup"><span data-stu-id="140dd-p111">For both #3 and #4, we do not advertise the exact limits.  This is to prevent spammers from gaming the system and to ensure that we can change the limits when we need to. The limits are high enough such that an average business user will never hit them and low enough that it contains most of the damage a spammer can do.</span></span> 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a><span data-ttu-id="140dd-141">需要发送出站大量 EOP 通过电子邮件的客户推荐的解决方法</span><span class="sxs-lookup"><span data-stu-id="140dd-141">Recommended workarounds for customers who want to send outbound a lot of email through EOP</span></span>

<span data-ttu-id="140dd-p112">很难想要发送大量与该服务防止受到攻击的帐户和与较差的邮件列表获取做法的批量邮件发件人的电子邮件客户之间的平衡。同样，出站 IP 上第三方 blocklist 登录的成本是高于阻止发送出站电子邮件客户。如在[Exchange Online Service Description](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits)中所述，使用 EOP 发送批量电子邮件不支持使用的服务和仅允许基于"最大努力"。对于想发送批量电子邮件的客户，我们建议：</span><span class="sxs-lookup"><span data-stu-id="140dd-p112">It is difficult to strike a balance between customers who want to send a large volume of email vs. protecting the service from compromised accounts and bulk emailers with poor list acquisition practices. Again, the cost of an outbound IP landing on a 3rd party blocklist is higher than blocking a customer from sending outbound email. As described in the [Exchange Online Service Description](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits), using EOP to send bulk email is not a supported use of the service and is only permitted on a “best-effort” basis. For customers who do want to send bulk email, we recommend the following:</span></span>

<span data-ttu-id="140dd-p113">答：**发送批量电子邮件通过其自己的内部部署邮件服务器**。这意味着客户需要维护其自己的电子邮件基础结构这种类型的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="140dd-p113">a. **Send the bulk email through its own on-premise mail servers**. This means that the customer will have to maintain its own email infrastructure for this type of email.</span></span>

<span data-ttu-id="140dd-p114">b.**使用第三方批量 emailer 发送大量通信**。有几个第三方批量邮件发件人其唯一业务会发送批量电子邮件。它们可以与客户合作以确保它们已良好在通过做法并拥有专用于强制实施该资源。</span><span class="sxs-lookup"><span data-stu-id="140dd-p114">b. **Use a 3rd party bulk emailer to send the mass communication**. There are several 3rd party bulk emailers whose sole business it is to send bulk email. They can work with customers to ensure that they have good emailing practices and they have resources dedicated to enforcing it.</span></span> 

<span data-ttu-id="140dd-p115">消息、 移动、 恶意软件防滥用工作组 (MAAWG) 发布其成员资格名单[此处](http://www.maawg.org/about/roster)。多个批量电子邮件提供程序的列表上，而已知负责 Internet 市民。</span><span class="sxs-lookup"><span data-stu-id="140dd-p115">The Messaging, Mobile, Malware Anti-Abuse Working Group (MAAWG) publishes its membership roster [here](http://www.maawg.org/about/roster). Several bulk email providers are on the list and are known to be responsible Internet citizens.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="140dd-155">更多信息</span><span class="sxs-lookup"><span data-stu-id="140dd-155">For more information</span></span>

[<span data-ttu-id="140dd-156">发件人被阻止发送出站垃圾邮件时的示例通知</span><span class="sxs-lookup"><span data-stu-id="140dd-156">Sample notification when a sender is blocked sending outbound spam</span></span>](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[<span data-ttu-id="140dd-157">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="140dd-157">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="140dd-158">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="140dd-158">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)

[<span data-ttu-id="140dd-159">垃圾邮件可信度</span><span class="sxs-lookup"><span data-stu-id="140dd-159">Spam confidence levels</span></span>](spam-confidence-levels.md)
