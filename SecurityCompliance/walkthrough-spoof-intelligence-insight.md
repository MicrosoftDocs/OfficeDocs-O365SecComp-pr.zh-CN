---
title: 演练欺骗性的智能洞察力
ms.author: krowley
author: kccross
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
description: 了解新的欺骗智能洞察力的工作原理。
ms.openlocfilehash: 83fa1580a0e7c4717581cc5f23b8f525d6b918e0
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220322"
---
# <a name="walkthrough-spoof-intelligence-insight"></a><span data-ttu-id="32f5f-103">演练: 欺骗性的智能洞察力</span><span class="sxs-lookup"><span data-stu-id="32f5f-103">Walkthrough: spoof intelligence insight</span></span>

<span data-ttu-id="32f5f-p101">通过使用欺骗智能洞察力, 可以快速确定哪些发件人可以合法地向您发送未经身份验证的电子邮件。通过允许他们发送欺骗邮件, 可以降低任何误报给用户带来的风险。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p101">By using the Spoof Intelligence insight, you can quickly determine which senders are legitimately sending you unauthenticated email. By permitting them to send spoofed messages, you can reduce the risk of any false positives going to your users.</span></span>
  
<span data-ttu-id="32f5f-106">此外, 您还可以使用欺骗性智能监视器并管理允许的域对, 以提供额外的安全层, 并防止不安全的邮件到达您的组织。</span><span class="sxs-lookup"><span data-stu-id="32f5f-106">In addition, you can also use Spoof Intelligence monitor and manage permitted domain-pairs to provide an additional layer of security and prevent unsafe messages from arriving in your organization.</span></span>
  
<span data-ttu-id="32f5f-p102">如果您的工作或学校帐户已被授予&amp; Office 365 全局管理员、安全管理员或安全阅读者权限, 则可以使用安全合规性中心中的欺骗智能洞察力。有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p102">You can use the spoof intelligence insight in the Security &amp; Compliance Center if your work or school account has been given Office 365 global administrator, security administrator, or security reader permissions. For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="32f5f-109">如果你不熟悉[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md), 它可能会帮助你了解如何轻松地从仪表板导航到真知灼见和建议的操作。</span><span class="sxs-lookup"><span data-stu-id="32f5f-109">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span>
  
<span data-ttu-id="32f5f-p103">您可以在安全&amp;合规中心中查看来自多个仪表板的欺骗智能洞察力。无论您正在查看哪个仪表板, 真知灼见都会提供相同的详细信息, 并允许您快速执行相同的任务。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p103">You can view the spoof intelligence insight from more than one dashboard in the Security &amp; Compliance Center. Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>
  
<span data-ttu-id="32f5f-p104">这是针对安全&amp;合规中心的几个演练之一。若要导航报告和见解, 请参阅相关主题部分中的演练。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p104">This is one of several walkthroughs for the Security &amp; Compliance Center. To about navigating reports and insights, see the walkthroughs in the Related topics section.</span></span>
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a><span data-ttu-id="32f5f-114">获取安全&amp;合规性中心中的欺骗智能洞察力</span><span class="sxs-lookup"><span data-stu-id="32f5f-114">Getting to the spoof intelligence insight in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="32f5f-115">若要开始, 你需要[转到安全&amp;合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="32f5f-115">To get started, you'll need [go to the Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="32f5f-116">在 "安全&amp;合规性中心" 中, 转到 "**威胁管理** \> **仪表板"。**</span><span class="sxs-lookup"><span data-stu-id="32f5f-116">In the Security &amp; Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>
    
3. <span data-ttu-id="32f5f-p105">在 "**见解**" 行中, 查找欺骗性智能洞察力。如果已启用欺骗智能, 则真知灼见将被**授权的欺骗域在过去30天内进行身份验证失败**。如果尚未启用欺骗保护, 则真知灼见将提示您通过使用标题**启用欺骗保护**来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p105">In the **Insights** row, look for the spoof intelligence insight. If you have enabled spoof intelligence, then the insight is entitled **Spoofed domains that failed authentication of the past 30 days**. If you haven't enabled spoof protection, then the insight will prompt you to do so by using the title **Enable Spoof Protection**.</span></span> 
    
## <a name="about-the-insight-on-the-dashboard"></a><span data-ttu-id="32f5f-120">关于仪表板的洞察力</span><span class="sxs-lookup"><span data-stu-id="32f5f-120">About the insight on the dashboard</span></span>

<span data-ttu-id="32f5f-121">仪表板上的洞察力显示如下所示的信息。</span><span class="sxs-lookup"><span data-stu-id="32f5f-121">The insight on the dashboard shows you information like this.</span></span>
  
![欺骗性智能洞察力的屏幕截图](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
<span data-ttu-id="32f5f-123">此洞察力有两种模式:</span><span class="sxs-lookup"><span data-stu-id="32f5f-123">This insight has two modes:</span></span>
  
 <span data-ttu-id="32f5f-p106">**真知灼见模式**。如果你启用了任何欺骗策略, 则真知灼见将显示在过去30天内受到欺骗智能功能影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p106">**Insight mode**. If you have any spoof policy enabled, then the insight shows you how many mails were impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
 <span data-ttu-id="32f5f-p107">**if 模式**。如果未启用任何欺骗策略, 则真知灼见将显示在过去30天内, 我们的欺骗智能功能*会*影响的邮件数。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p107">**What if mode**. If you do not have any spoof policy enabled, then the insight shows you how many mails  *would*  have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span> 
  
<span data-ttu-id="32f5f-p108">无论哪种方式, 真知灼见中显示的欺骗性域都分为两类;可疑的域对和非可疑域对。这些类别进一步细分为三个不同的存储桶供您查看。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p108">Either way, the spoofed domains displayed in the insight are separated into two categories; suspicious domain pairs and non-suspicious domain pairs. These categories are further subdivided into three different buckets for you to review.</span></span> 
  
<span data-ttu-id="32f5f-130">*域对*是 "发件人:" 地址和发送基础结构的组合。</span><span class="sxs-lookup"><span data-stu-id="32f5f-130">A  *domain pair*  is a combination of the "From:" address and the sending infrastructure.</span></span> 
  
- <span data-ttu-id="32f5f-p109">"发件人" 地址是邮件应用程序显示为 "发件人" 地址的地址。此地址标识电子邮件的作者。即负责撰写邮件的个人或系统的邮箱。这有时称为 "5322.from 地址"。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p109">The "From" address is the address displayed as the From address by your mail application. This address identifies the author of the email. That is, the mailbox of the person or system responsible for writing the message. This is sometimes called the 5322.From address.</span></span>
    
- <span data-ttu-id="32f5f-p110">发送方结构或发件人是发送 IP 地址的 PTR 记录的组织域。如果发送 ip 地址没有 PTR 记录, 则发件人由使用 CIDR 表示法 (/24) 中的255.255.255.0 子网掩码的发送 IP 进行标识。例如, 如果 IP 地址为 192.168.100.100, 则发件人的完整 IP 地址为 192.168.100.100/24。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p110">The sending infrastructure, or sender, is the organizational domain of the PTR record of the sending IP address. If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24). For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>
    
 <span data-ttu-id="32f5f-138">**可疑域对**包括:</span><span class="sxs-lookup"><span data-stu-id="32f5f-138">**Suspicious domain pairs** include:</span></span> 
  
- <span data-ttu-id="32f5f-p111">**高可信度欺骗**。根据历史发送模式和域的信誉分数, Office 365 收到了这些域是可疑的强信号。Office 365 非常确信域是哄骗的, 并且从这些域发送的邮件不太可能是合法的。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p111">**High-confidence spoof**. Office 365 received strong signals that these domains are suspicious, based on the historical sending patterns and the reputation score of the domains. Office 365 is highly confident that the domains are spoofing and that messages sent from these domains are less likely to be legitimate.</span></span> 
    
- <span data-ttu-id="32f5f-p112">**中等可信度欺骗**。根据历史发送模式和域的信誉分数, Office 365 接收到这些域有可疑的中等信号。Office 365 适度确信域是欺骗的, 并且从这些域发送的邮件是合法的。此存储桶具有包含误报 (FPs) 的更多可能性, 而不是高可信度欺骗存储桶。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p112">**Moderate confidence spoof**. Office 365 received moderate signals that these domains are suspicious, based on historical sending patterns and the reputation score of the domains. Office 365 is moderately confident that the domains are spoofing and that messages sent from these domains are legitimate. This bucket has a greater chance of containing false positives (FPs) than the high-confidence spoof bucket.</span></span> 
    
 <span data-ttu-id="32f5f-p113">**非可疑域对**包括**rescued 欺骗**。Rescued 欺骗是指未通过显式身份验证检查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) 但通过了扩展的身份验证检查的域。因此, Office 365 将代表您 rescued 邮件, 并且不会对邮件执行任何反欺骗操作。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p113">**Non-suspicious domain pairs** include **rescued spoof**. Rescued spoof are domains that have failed the explicit authentication checks ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email), [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) but passed our extended authentication checks. As a result of this, Office 365 rescued the mail on your behalf and no anti-spoofing action was taken on the mail.</span></span> 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="32f5f-149">查看有关欺骗性智能洞察力的可疑域对的详细信息</span><span class="sxs-lookup"><span data-stu-id="32f5f-149">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="32f5f-150">在 "哄骗智能洞察力" 中, 单击任一域对 (high、适中或 rescued)。</span><span class="sxs-lookup"><span data-stu-id="32f5f-150">On the spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>
  
<span data-ttu-id="32f5f-p114">此时将显示 "**哄骗智能真知灼见**" 页面, 其中显示了向您的组织发送未经身份验证的邮件的发件人列表。此页上的信息可帮助您确定是否授权欺骗邮件, 或者是否需要执行进一步的操作。您可以按邮件数、欺骗的上次检测日期等对信息进行排序。(例如, 单击 "**邮件数**" 或 "**最后见到**的列标题"。)</span><span class="sxs-lookup"><span data-stu-id="32f5f-p114">The **Spoof Intelligence Insight** page appears showing you a list of senders that are sending unauthenticated mail into your organization. The information on this page helps you determine whether spoofed messages are authorized or not or if you need to take further action. You can sort the information by message count, the date the spoof was last detected, and more. (Click column headings, such as **Message count** or **Last seen**, for example.)</span></span> 
    
2. <span data-ttu-id="32f5f-p115">在表中选择一个项目以打开详细信息窗格, 其中包含有关域对的丰富信息, 其中包括我们捕获此内容的原因、您需要执行的操作、域摘要、域摘要、WhoIs 有关发件人的数据以及我们在你的租户中从相同的发件人处看到的类似电子邮件。在这里, 您还可以选择在**AllowedToSpoof**安全发件人列表中添加或删除域对。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p115">Select an item in the table to open a details pane that contains rich information about the domain pair, including why we caught this, what you need to do, a domain summary, WhoIs data about the sender, and similar emails we have seen in your tenant from the same sender. From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span> 
  
![欺骗智能洞察力详细信息窗格中的域的屏幕截图](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a><span data-ttu-id="32f5f-158">在 AllowedToSpoof 安全发件人列表中添加或删除域</span><span class="sxs-lookup"><span data-stu-id="32f5f-158">Add or remove a domain from the AllowedToSpoof safe sender list</span></span>

<span data-ttu-id="32f5f-p116">在欺骗性智能洞察力的详细信息窗格中查看域对时, 可以在 AllowedToSpoof 安全发件人列表中添加或删除域。只需设置相应的开关即可。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p116">You add or remove a domain from the AllowedToSpoof safe sender list while reviewing the domain pair in the details pane of the spoof intelligence insight. Simply set the toggle accordingly.</span></span>
  
<span data-ttu-id="32f5f-p117">这将修改欺骗性域和发送基础结构的唯一域对组合, 并且不会对整个欺骗域或独立的发送基础结构提供覆盖范围。例如, 如果将以下域对添加到 "AllowedToSpoof" 发件人允许列表:*欺骗域*"gmail.com" 和*发送基础结构*"tm *. mx.com",* 则仅允许来自该域对的邮件欺骗。其他试图欺骗 "gmail.com" 的发件人以及 "tms.mx.com" 尝试欺骗的其他域将继续受到欺骗性智能的保护。</span><span class="sxs-lookup"><span data-stu-id="32f5f-p117">This modifies the unique domain pair combination of the spoofed domain and the sending infrastructure and does not provide coverage for the entire spoofed domain or the sending infrastructure in isolation. For example, if you add the following domain pair to the 'AllowedToSpoof' sender allow list:  *Spoofed Domain*  "gmail.com" and  *Sending Infrastructure*  "tms  *.mx.com",*  then only mail from that domain pair will be allowed to spoof. Other senders attempting to spoof "gmail.com", and other domains that "tms.mx.com" attempt to spoof will continue to be protected by spoof intelligence.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="32f5f-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="32f5f-164">Related topics</span></span>

[<span data-ttu-id="32f5f-165">了解有关欺骗智能的详情</span><span class="sxs-lookup"><span data-stu-id="32f5f-165">Learn more about spoof intelligence</span></span>](learn-about-spoof-intelligence.md)
  
[<span data-ttu-id="32f5f-166">Office 365 中的防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="32f5f-166">Anti-spoofing protection in Office 365</span></span>](anti-spoofing-protection.md)
  
[<span data-ttu-id="32f5f-167">演练 - 从仪表板到见解</span><span class="sxs-lookup"><span data-stu-id="32f5f-167">Walkthrough - From a dashboard to an insight</span></span>](from-a-dashboard-to-an-insight.md)
  
[<span data-ttu-id="32f5f-168">演练 - 从详细报告到见解</span><span class="sxs-lookup"><span data-stu-id="32f5f-168">Walkthrough - From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  
[<span data-ttu-id="32f5f-169">演练 - 从见解到详细报告</span><span class="sxs-lookup"><span data-stu-id="32f5f-169">Walkthrough - From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  

