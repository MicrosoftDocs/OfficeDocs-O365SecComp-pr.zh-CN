---
title: 了解有关欺骗智能的详情
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/14/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
description: 在安全中使用欺骗智能&amp;反垃圾邮件设置页上的合规性中心以查看所有发件人是欺骗属于您的组织，或者是域或欺骗外部域。Office 365 企业 E5 的一部分或单独的高级威胁保护一部分欺骗智能。
ms.openlocfilehash: a6e5f2daeab20b86354c4bf0d8d8abe0907095d1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525487"
---
# <a name="learn-more-about-spoof-intelligence"></a><span data-ttu-id="9aa3d-104">了解有关欺骗智能的详情</span><span class="sxs-lookup"><span data-stu-id="9aa3d-104">Learn more about spoof intelligence</span></span>

<span data-ttu-id="9aa3d-p102">在安全中使用欺骗智能&amp;上要查看所有发件人是欺骗属于您的组织，或者是域或欺骗外部域的**反垃圾邮件设置页**的合规性中心。Office 365 企业 E5 的一部分或单独的高级威胁保护一部分欺骗智能。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p102">Use spoof intelligence in the Security &amp; Compliance Center on the **Anti-spam settings page** to review all senders who are spoofing either domains that are part of your organization, or spoofing external domains. Spoof intelligence is available as part of Office 365 Enterprise E5 or separately as part of Advanced Threat Protection.</span></span> 
  
## <a name="what-types-of-email-spoofing-can-i-review-and-which-should-i-protect-against-with-spoof-intelligence"></a><span data-ttu-id="9aa3d-107">可以查看哪些类型的电子邮件欺骗和其应我防御与欺骗智能？</span><span class="sxs-lookup"><span data-stu-id="9aa3d-107">What types of email spoofing can I review and which should I protect against with spoof intelligence?</span></span>

<span data-ttu-id="9aa3d-p103">域您自己的您可以查看发件人在伪造您的域，然后选择要允许发件人继续，或阻止发件人。对于外部域，您可以允许发件人域再加上发送的基础结构，但不是单个发送电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p103">For domains you own, you can review senders who are spoofing your domain and then choose to allow the sender to continue or block the sender. For external domains, you can allow the sender domain combined with the sending infrastructure, although not an individual sending email address.</span></span>
  
<span data-ttu-id="9aa3d-p104">当发件人欺骗电子邮件地址时，它们显示发送代表之一贵组织的域或发送给组织外部域中的一个或多个用户帐户的邮件。人怀疑，有一些合法的业务理由欺骗。例如，在这些情况下，不会阻止发件人从欺骗您的域：</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p104">When a sender spoofs an email address, they appear to be sending mail on behalf of one or more user accounts within one of your organization's domains, or an external domain sending to your organization. Surprisingly, there are some legitimate business reasons for spoofing. For example, in these cases, you wouldn't block the sender from spoofing your domain:</span></span>
  
- <span data-ttu-id="9aa3d-113">您有第三方的发件人使用您的域将批量邮件发送给您自己的员工的公司投票。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-113">You have third-party senders who use your domain to send bulk mail to your own employees for company polls.</span></span>
    
- <span data-ttu-id="9aa3d-114">雇佣了外部公司生成和发送代表您的广告或产品更新。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-114">You have hired an external company to generate and send out advertising or product updates on your behalf.</span></span>
    
- <span data-ttu-id="9aa3d-115">助理定期需要的组织内的其他人发送电子邮件的用户。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-115">An assistant who regularly needs to send email for another person within your organization.</span></span>
    
- <span data-ttu-id="9aa3d-116">应用程序配置为欺骗自己的组织为了发送内部通知通过电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-116">An application that is configured to spoof its own organization in order to send internal notifications by email.</span></span>
    
<span data-ttu-id="9aa3d-p105">外部域经常发送带欺骗性的电子邮件和许多鉴于这些原因是合法。例如，下面是出现外部发件人发送带欺骗性的电子邮件的某些合法的情况下：</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p105">External domains frequently send spoofed email, and many of these reasons are legitimate. For example, here are some legitimate cases when external senders send spoofed email:</span></span>
  
- <span data-ttu-id="9aa3d-119">发件人位于讨论邮件列表，和邮件列表中继到邮件列表上的所有参与者原始发件人的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-119">The sender is on a discussion mailing list, and the mailing list is relaying the email from the original sender to all the participants on the mailing list.</span></span>
    
- <span data-ttu-id="9aa3d-120">外部公司发送电子邮件 （例如，自动生成的报告或软件作为服务公司） 的其他公司代表。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-120">An external company is sending email on behalf of another company (for example, an automated report, or a software-as-a-service company).</span></span>
    
<span data-ttu-id="9aa3d-p106">需要一种方法，以确保，由合法伪造者发送的邮件不获取陷入 Office 365 或外部的电子邮件系统中的垃圾邮件筛选器。通常，Office 365 将这些邮件视为垃圾邮件。作为 Office 365 管理员，您可以通过设置安全中的欺骗筛选器阻止此功能&amp;合规性中心。如果您拥有域，您可以配置 SPF、 DKIM 和 DMARC，以允许这些发件人。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p106">You need a way to ensure that the mail sent by legitimate spoofers doesn't get caught up in spam filters in Office 365 or external email systems. Normally, Office 365 treats these email messages as spam. As an Office 365 admin, you have the ability to prevent this by setting up spoof filters in the Security &amp; Compliance Center. If you own the domain, you can configure SPF, DKIM, and DMARC to allow for these senders.</span></span>
  
<span data-ttu-id="9aa3d-p107">另一方面，恶意伪造者，这些在伪造您的域或外部域发送垃圾邮件或网络钓鱼电子邮件的发件人需被阻止。欺骗也是一种网络钓鱼程序来获取用户凭据的常见方法。Office 365 具有内置欺骗保护，以使这些恶意电子邮件从发件人组织。欺骗保护组织的域是始终在所有 Office 365 客户，并启用外部域欺骗保护默认情况下，高级威胁保护客户。若要进一步增强此保护，告诉我们的发件人有权欺骗贵组织的域和代表您发送电子邮件和如果允许任何外部域欺骗中。从未授权的发件人发送的任何电子邮件将被视为垃圾邮件或 Office 365 欺骗。关注欺骗您的域的发件人和帮助我们改善欺骗智能使用安全&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p107">On the other hand, malicious spoofers, those senders that are spoofing your domain, or external domains, to send spam or phishing email, need to be blocked. Spoofing is also a common way for phishers to get user credentials. Office 365 has built-in spoof protection to help shield your organization from senders of these malicious emails. Spoof protection for your organization's domains is always on for all Office 365 customers, and external domain spoof protection is on by default for Advanced Threat Protection customers. To further strengthen this protection, tell us which senders are authorized to spoof your organization's domains and send email on your behalf, and if any external domains are permitted to spoof. Any email sent from a sender that you don't authorize will be treated as spam or spoofing by Office 365. Keep an eye on the senders spoofing your domain and help us improve spoof intelligence by using the Security &amp; Compliance Center.</span></span>
  
## <a name="managing-spoof-intelligence-in-the-security-amp-compliance-center"></a><span data-ttu-id="9aa3d-132">管理安全中的欺骗智能&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="9aa3d-132">Managing spoof intelligence in the Security &amp; Compliance Center</span></span>
<span data-ttu-id="9aa3d-133"><a name="Managespooflist"> </a></span><span class="sxs-lookup"><span data-stu-id="9aa3d-133"></span></span>

<span data-ttu-id="9aa3d-p108">Office 365，始终强制实施欺骗智能策略设置。您不能禁用，但您可以选择要主动管理它的多少。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p108">The spoof intelligence policy you set up is always enforced by Office 365. You cannot disable it, but you can choose how much you want to actively manage it.</span></span>
  
<span data-ttu-id="9aa3d-p109">您可以查看的发件人在伪造您的域或外部域，然后决定是否应该允许每个发件人为此使用安全&amp;合规性中心。每个带欺骗性的用户帐户的发件人欺骗从您的域或外部域，可以查看的信息下, 表中。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p109">You can review the senders who are spoofing your domain, or external domains, and then decide whether each sender should be allowed to do so by using the Security &amp; Compliance Center. For each spoofed user account that a sender spoofs from your domain or an external domain, you can view the information in the following table.</span></span>
  
|<span data-ttu-id="9aa3d-138">**参数**</span><span class="sxs-lookup"><span data-stu-id="9aa3d-138">**Parameter**</span></span>|<span data-ttu-id="9aa3d-139">**说明**</span><span class="sxs-lookup"><span data-stu-id="9aa3d-139">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9aa3d-140">Sender</span><span class="sxs-lookup"><span data-stu-id="9aa3d-140">Sender</span></span>  <br/> |<span data-ttu-id="9aa3d-p110">也称为 true 发件人。这通常是源自欺骗电子邮件的域。Office 365 确定指针欺骗贵组织的发送 IP 地址 (PTR) DNS 记录的域。如果不找到任何域，则此报表显示发件人的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p110">Also called the true sender. This is usually the domain from which the spoof email originates. Office 365 determines the domain of the pointer (PTR) DNS record of the sending IP address that is spoofing your organization. If no domain is found, the report displays the sender's IP address instead.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-145">带欺骗性的用户</span><span class="sxs-lookup"><span data-stu-id="9aa3d-145">Spoofed user</span></span>  <br/> |<span data-ttu-id="9aa3d-146">正在造假发件人的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-146">The user account that is being spoofed by the sender.</span></span>  <br/> <span data-ttu-id="9aa3d-p111">仅限**内部**标签。此字段包含单个电子邮件地址，或如果发件人欺骗多个用户帐户，它包含**多个**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p111">**Internal** tab only. This field contains a single email address, or if the sender is spoofing multiple user accounts, it contains **More than one**.  </span></span><br/> <span data-ttu-id="9aa3d-p112">仅**外部**选项卡。外部域仅包含一个发送的域，并且不包含的完整电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p112">**External** tab only. External domains only contain a sending domain, and do not contain a full email address.  </span></span><br/> <span data-ttu-id="9aa3d-p113">> [!TIP]> **的高级 admins。** 带欺骗性的用户是从也是邮件客户端显示为发件人地址的地址 (5322.From) 地址。有时称为 header.from 地址。通过 SPF 不检查此地址此有效性。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p113">> [!TIP]> **For advanced admins.** The spoofed user is the From (5322.From) address which is also the address displayed as the From address by the mail client. This is sometimes called the header.from address. This validity of this address is not checked by SPF.</span></span>           |
|<span data-ttu-id="9aa3d-155">消息的数目</span><span class="sxs-lookup"><span data-stu-id="9aa3d-155">Number of messages</span></span>  <br/> |<span data-ttu-id="9aa3d-156">发件人发送到您的组织代表标识欺骗发件人的发件人在最近 30 天内的邮件数。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-156">The number of mail messages sent by the sender to your organization on behalf of the identified spoofed sender or senders within the last 30 days.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-157">用户抱怨的数目</span><span class="sxs-lookup"><span data-stu-id="9aa3d-157">Number of user complaints</span></span>  <br/> |<span data-ttu-id="9aa3d-p114">最近 30 天内对此发件人与用户的用户字段的投诉。投诉通常是垃圾邮件向 Microsoft 提交的窗体中。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p114">Complaints filed by users against this sender by your users within the last 30 days. Complaints are usually in the form of junk submissions to Microsoft.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-160">身份验证结果</span><span class="sxs-lookup"><span data-stu-id="9aa3d-160">Authentication result</span></span>  <br/> |<span data-ttu-id="9aa3d-161">此值是**传递**如果发件人通过 Exchange Online Protection (EOP) 发件人的身份验证检查，如 SPF 或 DKIM，**失败**如果发件人失败 EOP 发件人的身份验证检查，或**未知**，如果不是这些检查的结果已知。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-161">This value is **Passed** if the sender passed Exchange Online Protection (EOP) sender authentication checks, such as SPF or DKIM, **Failed** if the sender failed EOP sender authentication checks, or **Unknown** if the result of these checks isn't known.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-162">通过设置的决策</span><span class="sxs-lookup"><span data-stu-id="9aa3d-162">Decision set by</span></span>  <br/> |<span data-ttu-id="9aa3d-163">显示 Office 365 管理员或欺骗智能策略是否确定允许发件人欺骗用户。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-163">Shows whether the Office 365 administrator or the spoof intelligence policy determined whether or not the sender is allowed to spoof the user.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-164">上一次发现</span><span class="sxs-lookup"><span data-stu-id="9aa3d-164">Last seen</span></span>  <br/> |<span data-ttu-id="9aa3d-165">在其收到邮件此发件人代表此欺骗用户最后一个日期。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-165">The last date on which a message was received by this sender on behalf of this spoofed user.</span></span>  <br/> |
|<span data-ttu-id="9aa3d-166">允许欺骗？</span><span class="sxs-lookup"><span data-stu-id="9aa3d-166">Allowed to spoof?</span></span>  <br/> | <span data-ttu-id="9aa3d-p115">显示允许此发件人发送代表欺骗用户的电子邮件。可能值包括：</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p115">Displays whether or not this sender is allowed to send email on behalf of the spoofed user. Possible values include:  </span></span><br/> <span data-ttu-id="9aa3d-169">**是**允许来自此欺骗发件人的所有欺骗的地址欺骗您的组织。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-169">**Yes** All spoofed addresses from this spoofing sender will be allowed to spoof your organization.</span></span>  <br/> <span data-ttu-id="9aa3d-p116">**无**将不允许来自此欺骗发件人的欺骗的地址欺骗您的组织。而是来自此发件人的邮件将被标记为垃圾邮件 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p116">**No** Spoofed addresses from this spoofing sender won't be allowed to spoof your organization. Instead, messages from this sender will be marked as spam by Office 365.  </span></span><br/> <span data-ttu-id="9aa3d-p117">**某些用户**如果发件人欺骗多个用户，将允许来自此发件人某些欺骗的地址欺骗您的组织，其余部分将被标记为垃圾邮件。使用**Detailed**选项卡可查看特定的地址。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p117">**Some users** If a sender is spoofing multiple users, some spoofed addresses from this sender will be allowed to spoof your organization, the rest will be marked as spam. Use the **Detailed** tab to see the specific addresses.  </span></span><br/> |
|<span data-ttu-id="9aa3d-174">欺骗类型</span><span class="sxs-lookup"><span data-stu-id="9aa3d-174">Spoof Type</span></span>  <br/> |<span data-ttu-id="9aa3d-175">此值为**内部**如果域是您的组织已设置域之一，否则值为**外部**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-175">This value is **Internal** if the domain is one of your organization's provisioned domains, otherwise the value is **External**.</span></span>  <br/> |
   
 <span data-ttu-id="9aa3d-176">**若要管理的发件人您的域欺骗使用安全&amp;合规性中心**</span><span class="sxs-lookup"><span data-stu-id="9aa3d-176">**To manage senders who are spoofing your domain by using the Security &amp; Compliance Center**</span></span>
  
1. <span data-ttu-id="9aa3d-177">转到[安全&amp;合规性中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-177">Go to the [Security &amp; Compliance Center](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9aa3d-p118">使用您的工作或学校帐户登录到 Office 365。Office 365 组织中，您的帐户必须具有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p118">Sign in to Office 365 with your work or school account. Your account must have administrator credentials in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="9aa3d-180">安全中&amp;合规性中心中，展开**威胁管理** \> **策略** \> **反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-180">In the Security &amp; Compliance Center, expand **Threat Management** \> **Policy** \> **Anti-spam**.</span></span>
  
![](media/0a098e68-5ecf-40d7-984f-d15fcc1f958d.jpg)
  
4. <span data-ttu-id="9aa3d-181">在右窗格中**反垃圾邮件设置**页上，选择**自定义**选项卡，，然后向下滚动，并展开**欺骗智能策略**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-181">On the **Anti-spam settings** page in the right pane, select the **Custom** tab, and then scroll down and expand **Spoof intelligence policy**.</span></span> 
  
![](media/a5112100-0b37-460f-932d-5b2f98157871.jpg)
  
5. <span data-ttu-id="9aa3d-182">若要查看发件人欺骗您的域的列表，请选择**查看新的发件人**，并选择 * * Your 域 * * 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-182">To view the list of senders spoofing your domain, choose **Review new senders** and select the ** Your Domains ** tab.</span></span> 
    
    <span data-ttu-id="9aa3d-p119">如果您已审查发件人，并且想要更改的一些您以前的选择，则可以选择**我已检查我的状态显示发件人**。在任一情况下，将显示以下窗格。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p119">If you've already reviewed senders, and want to change some of your previous choices, you can choose **Show me senders I already reviewed** instead. In either case, the following panel appears.</span></span> 
  
![](media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)
  
<span data-ttu-id="9aa3d-185">每个欺骗的用户显示在单独的行，以便您可以选择是否允许或阻止发件人从分别欺骗每个用户。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-185">Each spoofed user is displayed in a separate row so that you can choose whether to allow or block the sender from spoofing each user individually.</span></span>
  
<span data-ttu-id="9aa3d-p120">将发件人添加到允许列表中的用户，请从**允许欺骗**列中选择**是**。将发件人添加到阻止列表中的用户，选择**否**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p120">To add a sender to the allow list for a user, select **Yes** from the **Allowed to spoof** column. To add a sender to the block list for a user, choose **No**.</span></span>
  
<span data-ttu-id="9aa3d-p121">若要将域的策略设置不属于您，选择**外部域**选项卡更改任何发件人为**是****允许欺骗**该列允许的发件人发送到您的组织的未经身份验证的电子邮件中。或者，如果您认为 Office 365 中允许发件人发送带欺骗性的电子邮件已错误，更改为**否****允许欺骗**列。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p121">To set the policy for domains you do not own, select the **External Domains** tab. Change any sender to **Yes** in the **Allowed to Spoof** column to permit that sender to send unauthenticated email into your organization. Alternatively, if you think Office 365 has made a mistake in permitting the sender to send spoofed email, change the **Allowed to spoof** column to **No**.</span></span> 
  
![](media/5dbef9cf-103f-49cd-9638-4b0083d6baa7.jpg)
  
6. <span data-ttu-id="9aa3d-190">选择**保存**以保存更改。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-190">Choose **Save** to save any changes.</span></span> 
    
## <a name="configuring-the-anti-spoofing-policy"></a><span data-ttu-id="9aa3d-191">配置反欺骗策略</span><span class="sxs-lookup"><span data-stu-id="9aa3d-191">Configuring the anti-spoofing policy</span></span>
<span data-ttu-id="9aa3d-192"><a name="Managespooflist"> </a></span><span class="sxs-lookup"><span data-stu-id="9aa3d-192"></span></span>

<span data-ttu-id="9aa3d-193">除了允许或阻止从带欺骗性的电子邮件发送到您的组织的特定发件人，您还可以配置所需的筛选器是如何严格、 找到欺骗消息，则时要采取的操作以及启用安全提示反欺骗。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-193">In addition to allowing or blocking a particular sender from sending spoofed email into your organization, you can also configure how strict you want the filter to be, the action to take when a spoofing message is found, and whether or not to enable Safety Tips for anti-spoofing.</span></span>
  
<span data-ttu-id="9aa3d-p122">反欺骗保护应用于电子邮件从发件人的 Office 365 组织外部的域。您可以将策略应用于其邮箱被授权 Office 365 企业 E5 或高级威胁保护使用的收件人。管理反欺骗策略以及其他 ATP 防钓鱼设置。有关 ATP 防钓鱼设置的详细信息，请参阅[Office 365 防钓鱼策略设置](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p122">Anti-spoofing protection is applied to email from senders from domains that are external to your Office 365 organization. You can apply the policy to recipients whose mailboxes are licensed for Office 365 Enterprise E5 or Advanced Threat Protection. You manage the anti-spoofing policy along with the other ATP anti-phishing settings. For more information about ATP anti-phishing settings, see [Set up the Office 365 anti-phishing policies](https://support.office.com/article/set-up-office-365-atp-anti-phishing-policies-5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578?ui=en-US&amp;rs=en-US&amp;ad=US#phishpolicyoptions).</span></span>
  
<span data-ttu-id="9aa3d-p123">Office 365 包括默认反欺骗保护始终运行。此默认保护不安全中可见&amp;合规性中心或通过 Windows PowerShell cmdlet 可检索。不能修改默认反欺骗保护。相反，您可以配置 Office 365 如何严格强制执行您创建的每个防钓鱼策略中的反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p123">Office 365 includes default anti-spoofing protection that's always running. This default protection is not visible in the Security &amp; Compliance Center or retrievable through Windows PowerShell cmdlets. You can't modify the default anti-spoofing protection. Instead, you can configure how strictly Office 365 enforces the anti-spoofing protection in each anti-phishing policy that you create.</span></span> 
  
<span data-ttu-id="9aa3d-p124">即使出现安全中 ATP 防钓鱼策略下的反欺骗策略&amp;合规性中心，它将不能继承其默认行为反垃圾邮件配置下设置现有网络钓鱼。如果您有下**反垃圾邮件**设置\>您要为反欺骗复制**网络钓鱼**，您将需要创建防钓鱼策略，然后编辑防钓鱼策略，以反映您欺骗设置的欺骗部分下面一节，而不是接受在后台运行的默认设置中所述。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p124">Even though the anti-spoofing policy appears under the ATP anti-phishing policy in the Security &amp; Compliance Center, it does not inherit its default behavior from the existing phishing setting under the Anti-spam configuration. If you have settings under **Anti-spam** \> **Phishing** that you want to replicate for anti-spoofing, you will need to create an anti-phishing policy, then edit the spoof portion of the anti-phishing policy to reflect your spoof settings as described in the following section, rather than accepting the default settings that run in the background.</span></span> 
  
 <span data-ttu-id="9aa3d-204">**使用安全配置反钓鱼策略中的反欺骗保护&amp;合规性中心**</span><span class="sxs-lookup"><span data-stu-id="9aa3d-204">**To configure anti-spoofing protection within an anti-phishing policy by using the Security &amp; Compliance Center**</span></span>
  
1. <span data-ttu-id="9aa3d-205">转到[安全&amp;合规性中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-205">Go to the [Security &amp; Compliance Center](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9aa3d-p125">使用您的工作或学校帐户登录到 Office 365。Office 365 组织中，您的帐户必须具有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p125">Sign in to Office 365 with your work or school account. Your account must have administrator credentials in your Office 365 organization.</span></span>
    
3. <span data-ttu-id="9aa3d-208">安全中&amp;合规性中心中，展开**威胁管理** \> **策略** \> **ATP 防钓鱼**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-208">In the Security &amp; Compliance Center, expand **Threat Management** \> **Policy** \> **ATP Anti-phishing**.</span></span> 
    
4. <span data-ttu-id="9aa3d-209">在右窗格中的**防钓鱼**页上，选择您想要配置的防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-209">On the **Anti-phishing** page in the right pane, select the anti-phishing policy you want to configure.</span></span> 
    
5. <span data-ttu-id="9aa3d-210">在页面上出现在**欺骗**行中，选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-210">On the page that appears, in the **Spoof** row, choose **Edit**.</span></span> 
    
6. <span data-ttu-id="9aa3d-p126">在**伪造阈值**页上，如果您选择**默认**，然后将传递显式或隐式传递身份验证的所有邮件，即发送普通电子邮件筛选。如果选择**严格**，然后中型自信地隐式传递身份验证的消息也称为"软传递"复合身份验证、 仍然忽略并标记为欺骗电子邮件。严格的设置不积极并且将生成误报。做出选择，然后选择**操作**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p126">On the **Spoofing thresholds** page, if you select **Default**, then all messages that explicitly or implicitly pass authentication will be delivered, that is, sent for normal email filtering. If you select **Strict**, then messages that pass authentication implicitly with medium confidence, also called a composite authentication of "soft pass", will be ignored anyway and marked as spoofing email messages. The Strict setting is aggressive and will generate false positives. Make your choice and then select **Actions**.</span></span> 
  
![](media/62327314-a65f-49b0-bf60-ab4775e0bc9e.jpg)
  
7. <span data-ttu-id="9aa3d-p127">接下来，配置邮件被检测为跨域欺骗时要采取的操作。默认行为是将邮件移动到收件人的垃圾邮件文件夹。其他选项是将邮件发送到隔离邮箱。有关管理邮件发送到隔离邮件的详细信息，请参阅[Office 365 中的隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p127">Next, configure the actions to take when a message is detected as a cross-domain spoof. The default behavior is to move the message to the recipient's junk email folder. The other option is to send the message to the quarantine. For more information about managing messages sent to quarantine, see [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>
  
![](media/7a868dff-2c4b-46b9-88ca-f2d523ca2307.jpg)
  
8. <span data-ttu-id="9aa3d-p128">选择是否启用或禁用反欺骗安全提示。Office 365 建议以便它们发件人无法验证其标识与交互时警告用户启用的**身份验证失败**安全提示。Office 365 还建议的安全提示启用较小用户组的**身份验证软传递**因为此安全提示可能会产生大量的警告，如果用户从多合法的但未经过身份验证源接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p128">Choose whether to enable or disable anti-spoofing safety tips. Office 365 recommends enabling the **Authentication fails** safety tip in order to warn users when they are interacting with a sender whose identity could not be verified. Office 365 also recommends enabling the safety tip for an **Authentication soft-pass** for smaller groups of users, because this safety tip may generate a lot of warnings if the user receives email from many legitimate, but unauthenticated sources.</span></span> 
  
![](media/1ed675c0-48c2-4587-a957-60eb68dc9628.jpg)
  
<span data-ttu-id="9aa3d-222">做出选择，然后选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-222">Make your choice and then select **Save**.</span></span> 
    
## <a name="other-ways-to-manage-spoofing-and-phishing-with-office-365"></a><span data-ttu-id="9aa3d-223">管理欺骗和网页仿冒与 Office 365 的其他方法</span><span class="sxs-lookup"><span data-stu-id="9aa3d-223">Other ways to manage spoofing and phishing with Office 365</span></span>
<span data-ttu-id="9aa3d-224"><a name="Managespooflist"> </a></span><span class="sxs-lookup"><span data-stu-id="9aa3d-224"></span></span>

<span data-ttu-id="9aa3d-p129">是认真地欺骗和网络钓鱼防护。下面是检查发件人欺骗您的域和帮助防止 2003、1st_office12 组织相关的方法：</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p129">Be diligent about spoofing and phishing protection. Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>
  
- <span data-ttu-id="9aa3d-p130">检查 Exchange Online Protection 欺骗邮件报告为您例程的一部分。您可以使用此报告通常以查看并帮助管理欺骗发件人。有关信息，请参阅中[使用邮件保护报告查看关于恶意软件、 垃圾邮件和规则检测的数据的 Office 365 中](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx)的**欺骗邮件报告**。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p130">Check the Exchange Online Protection spoof mail report as part of your routine. You can use this report often to view and help manage spoofed senders. For information, see **Spoof mail report** in [Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](https://technet.microsoft.com/library/dn500744%28v=exchg.150%29.aspx).</span></span>
    
- <span data-ttu-id="9aa3d-230">对于更高级的 Office 365 管理员：</span><span class="sxs-lookup"><span data-stu-id="9aa3d-230">For more advanced Office 365 admins:</span></span>
    
  - <span data-ttu-id="9aa3d-p131">查看您的发件人策略框架 (SPF) 配置。快速了解到 SPF 并获取快速配置，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。Office 365 如何使用 SPF，更深入地了解或故障排除或非标准部署如混合部署，启动与[Office 365 如何使用发件人策略框架 (SPF) 以防止欺骗](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p131">Review your Sender Policy Framework (SPF) configuration. For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx). For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx).</span></span>
    
  - <span data-ttu-id="9aa3d-p132">查看您的域密钥标识邮件 (DKIM) 配置。应使用 DKIM 除了 SPF 和 DMARC 为了帮助防止伪造者从发送看起来来自您的域的邮件。DKIM，可以将数字签名添加到邮件头中的电子邮件。有关信息，请参阅[使用 DKIM 验证从您在 Office 365 中的域发送出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p132">Review your DomainKeys Identified Mail (DKIM) configuration. You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain. DKIM lets you add a digital signature to email messages in the message header. For information, see [Use DKIM to validate outbound email sent from your domain in Office 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx).</span></span>
    
  - <span data-ttu-id="9aa3d-p133">查看您的基于域的邮件身份验证、 报告和一致性声明 (DMARC) 配置。实现与 SPF DKIM DMARC 提供了其他欺骗和网络钓鱼的电子邮件保护。接收邮件系统确定如何处理邮件的 DMARC 帮助发送从您的域失败 SPF 或 DKIM 检查。有关信息，请参阅[使用 DMARC 用于验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p133">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration. Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email. DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks. For information, see [Use DMARC to validate email in Office 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>
    
  - <span data-ttu-id="9aa3d-p134">使用[Get-PhishFilterPolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) Windows PowerShell cmdlet 上欺骗发件人收集详细的数据，生成允许和阻止列表，并帮助您确定如何生成更全面的 SPF、 DKIM 和 DMARC DNS 记录，而不在在外部的垃圾邮件筛选器受到合法的电子邮件。有关详细信息，请参阅[antispoofing 保护 Office 365 中的工作方式](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="9aa3d-p134">Use the [Get-PhishFilterPolicy](https://technet.microsoft.com/en-us/library/mt735158%28v=exchg.160%29.aspx) Windows PowerShell cmdlet to gather detailed data on spoofed senders, generate allow and block lists, and help you determine how to generate more comprehensive SPF, DKIM, and DMARC DNS records without having your legitimate email get caught in external spam filters. For more information, see [How antispoofing protection works in Office 365](https://blogs.msdn.microsoft.com/tzink/2016/02/23/how-antispoofing-protection-works-in-office-365/).</span></span>
    

