---
title: 演练欺骗智能见解
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 请参阅新欺骗智能洞察的工作原理。
ms.openlocfilehash: ca9c4ae6f2d65ef2700a2e02acd5b4f1dfbfe903
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22596091"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="0f0a9-103">演练： 欺骗智能见解</span><span class="sxs-lookup"><span data-stu-id="0f0a9-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="0f0a9-p101">通过使用欺骗智能洞察，您可以快速确定合法未经验证电子邮件发送的发件人。通过允许发送带欺骗性的消息，可以减少任何误报转到您的用户的风险。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p101">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email. By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="0f0a9-106">此外，您还可以使用欺骗智能监视和管理提供额外的安全和防止遭受不安全邮件到达组织中的允许的域的对。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="0f0a9-p102">您可以使用欺骗智能洞察中安全&amp;合规性中心如果您的工作或学校帐户已被授予，Office 365 全局管理员、 安全管理员或安全读者权限。有关详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p102">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="0f0a9-109">如果您是新手[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)，它可能有助于请参阅如何您可以轻松地从导航仪表板到见解和建议的操作。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="0f0a9-p103">您可以安全中查看来自多个仪表板欺骗智能洞察&amp;合规性中心。无论您要看的仪表板，洞察提供相同的详细信息，并允许您快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p103">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center. Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="0f0a9-p104">这是一个安全的几个演练&amp;合规性中心。若要导航报表和见解，请参阅相关的主题部分中的演练。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p104">This is one of several walkthroughs for the Security &amp; Compliance Center. To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="0f0a9-114">获取安全中欺骗智能洞察到&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="0f0a9-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="0f0a9-115">若要开始，您将需要[转到安全&amp;合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-115">To get started, you'll need [go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="0f0a9-116">安全中&amp;合规性中心中，转到**威胁管理** \> **仪表板。**</span><span class="sxs-lookup"><span data-stu-id="0f0a9-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="0f0a9-p105">在**洞察力**行中，查找欺骗智能见解。如果已启用欺骗智能然后洞察有权获得**Spoofed 域的失败过去 30 天的身份验证**。如果尚未启用欺骗保护，然后洞察将提示您以使用标题**启用欺骗保护**完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p105">In the **Insights** row, look for the spoof intelligence insight. If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**. If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="0f0a9-120">关于仪表板上洞察</span><span class="sxs-lookup"><span data-stu-id="0f0a9-120">About the insight on the dashboard</span></span>

<span data-ttu-id="0f0a9-121">仪表板上的洞察显示类似的信息。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-121">The insight on the dashboard shows you information like this.</span></span>
  
![欺骗智能洞察的屏幕截图](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="0f0a9-123">此洞察有两种模式：</span><span class="sxs-lookup"><span data-stu-id="0f0a9-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="0f0a9-p106">**洞察模式**。如果必须启用任何欺骗策略，然后洞察显示过去 30 天内，多少邮件受到我们欺骗智能功能。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p106">**Insight mode**. If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="0f0a9-p107">**如果模式**。如果您没有启用任何欺骗策略，然后洞察显示多少邮件*将*具有已受我们欺骗智能功能过去 30 天内。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p107">**What if mode**. If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="0f0a9-p108">无论进行上述，带欺骗性的域中的洞察显示可分为两类;可疑域对和非可疑域对。这些类别进一步到要查看的三个不同存储桶细分。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p108">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs. These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="0f0a9-130">*域对*是组合的"从:"地址和发送基础结构。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="0f0a9-p109">"从"地址是邮件应用程序显示为发件人地址的地址。此地址标识的电子邮件的作者。即负责编写邮件系统的人的邮箱。有时称为 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p109">The "From" address is the address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="0f0a9-p110">发送的基础结构或发件人发送的 IP 地址的 PTR 记录的组织域。如果发送 IP 地址具有没有 PTR 记录，则发件人标识与 255.255.255.0 发送的 IP 子网掩码 CIDR 表示法 （/ 24）。例如，如果该 IP 地址是 192.168.100.100 发件人的完整 IP 地址是 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p110">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address. If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24). For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="0f0a9-138">**可疑域对**包括：</span><span class="sxs-lookup"><span data-stu-id="0f0a9-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="0f0a9-p111">**高可信度欺骗**。Office 365 收到强信号这些域的可疑，基于历史发送模式和的域的信誉分数。Office 365 的域的欺骗和从这些域发送邮件不太可能合法高信心。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p111">**High-confidence spoof**. Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains. Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="0f0a9-p112">**中等可信度欺骗**。Office 365 收到中等信号这些域的可疑，根据历史发送模式和的域的信誉分数。Office 365 的域的欺骗和从这些域发送邮件是合法中等信心。此地址散列表元具有更好的包含误报 (FPs) 比高可信度欺骗地址散列表元。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p112">**Moderate confidence spoof**. Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains. Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate. This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="0f0a9-p113">**非可疑域对**包括**rescued 欺骗**。挽救的欺骗是已失败的显式身份验证检查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)， [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email))，但传递我们扩展身份验证检查的域。由于此，Office 365 rescued 代表您的邮件并没有反欺骗采取操作的邮件。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p113">**Non-suspicious domain pairs** include **rescued spoof**. Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks. As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="0f0a9-149">查看有关可疑域名对从欺骗智能洞察详细的信息</span><span class="sxs-lookup"><span data-stu-id="0f0a9-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="0f0a9-150">在欺骗智能洞察中，单击的任何域对 （高、 中等或挽救）。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="0f0a9-p114">将显示**欺骗智能洞察**页，显示您的用户发送到您的组织未经身份验证的邮件的发件人列表。此页上的信息可帮助您确定是否或未授权欺骗的邮件或是否需要进一步执行操作。您可以排序邮件计数欺骗上次检测到，日期信息和详细信息。（例如单击列标题，例如**消息计数**或**上一次发现**。）</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p114">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization. The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action. You can sort the information by message count, the date the spoof was last detected, and more. (Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="0f0a9-p115">选择要打开包含大量信息的域对详细信息窗格中的表中的项目，包括为什么我们捕获此，您需要做什么，一个域摘要，我们已从同一发件人租户中看到类似电子邮件发件人，以及 WhoIs 数据。从此处，您还可以添加或移除**AllowedToSpoof**安全发件人列表中的域对。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p115">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender. From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![欺骗智能洞察详细信息窗格中的域的屏幕截图](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="0f0a9-158">添加或从 AllowedToSpoof 安全发件人列表中删除域</span><span class="sxs-lookup"><span data-stu-id="0f0a9-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="0f0a9-p116">添加或查看详细信息窗格中的欺骗智能洞察的域对时从 AllowedToSpoof 安全发件人列表中删除域。只需相应地设置切换。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p116">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight. Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="0f0a9-p117">这修改带欺骗性的域和发送基础结构的唯一域对组合并不提供范围的整个欺骗的域或隔离中的发送基础结构。例如，如果将以下两个域添加到 AllowedToSpoof 发件人允许列表：*造假域*"gmail.com"和*发送基础结构*"tm *。 mx.com"，* ，然后将允许仅从该域对邮件欺骗。试图欺骗"gmail.com"和"tms.mx.com"尝试欺骗将继续受到欺骗智能保护其他域的其他发件人。</span><span class="sxs-lookup"><span data-stu-id="0f0a9-p117">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation. For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof. Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="0f0a9-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="0f0a9-164">Related topics</span></span>

[<span data-ttu-id="0f0a9-165">了解有关欺骗智能的详情</span><span class="sxs-lookup"><span data-stu-id="0f0a9-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="0f0a9-166">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="0f0a9-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="0f0a9-167">演练 - 从仪表板到见解</span><span class="sxs-lookup"><span data-stu-id="0f0a9-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="0f0a9-168">演练 - 从详细报告到见解</span><span class="sxs-lookup"><span data-stu-id="0f0a9-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="0f0a9-169">演练 - 从见解到详细报告</span><span class="sxs-lookup"><span data-stu-id="0f0a9-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

