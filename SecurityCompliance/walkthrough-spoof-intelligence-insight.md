---
title: 演练欺骗性的智能洞察力
ms.author: tracyp
author: MSFTTracyP
ms.date: 7/30/2018
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 了解新的欺骗智能洞察力的工作原理。
ms.openlocfilehash: 4303b8f2524e6722e7febbbd06ab9daa853ed802
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267242"
---
# <a name="walkthrough-spoof-intelligence-insight"></a>演练: 欺骗性的智能洞察力

通过使用欺骗智能洞察力, 可以快速确定哪些发件人可以合法地向您发送未经身份验证的电子邮件。 通过允许他们发送欺骗邮件, 可以降低任何误报给用户带来的风险。
  
此外, 您还可以使用欺骗性智能监视器并管理允许的域对, 以提供额外的安全层, 并防止不安全的邮件到达您的组织。
  
如果您的工作或学校帐户已被授予&amp; Office 365 全局管理员、安全管理员或安全阅读者权限, 则可以使用安全合规性中心中的欺骗智能洞察力。 有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
  
如果你不熟悉[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md), 它可能会帮助你了解如何轻松地从仪表板导航到真知灼见和建议的操作。
  
您可以在安全&amp;合规中心中查看来自多个仪表板的欺骗智能洞察力。 无论您正在查看哪个仪表板, 真知灼见都会提供相同的详细信息, 并允许您快速执行相同的任务。
  
这是针对安全&amp;合规中心的几个演练之一。 若要导航报告和见解, 请参阅相关主题部分中的演练。
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>获取安全&amp;合规性中心中的欺骗智能洞察力

1. 若要开始, 你需要[转到安全&amp;合规中心](go-to-the-securitycompliance-center.md)。
    
2. 在 "安全&amp;合规性中心" 中, 转到 "**威胁管理** \> **仪表板"。**
    
3. 在 "**见解**" 行中, 查找欺骗性智能洞察力。 如果已启用欺骗智能, 则真知灼见将被**授权的欺骗域在过去30天内进行身份验证失败**。 如果尚未启用欺骗保护, 则真知灼见将提示您通过使用标题**启用欺骗保护**来执行此操作。 
    
## <a name="about-the-insight-on-the-dashboard"></a>关于仪表板的洞察力

仪表板上的洞察力显示如下所示的信息。
  
![欺骗性智能洞察力的屏幕截图](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
此洞察力有两种模式:
  
 **真知灼见模式**。 如果你启用了任何欺骗策略, 则真知灼见将显示在过去30天内受到欺骗智能功能影响的邮件数。 
  
 **if 模式**。 如果未启用任何欺骗策略, 则真知灼见将显示在过去30天内, 我们的欺骗智能功能*会*影响的邮件数。 
  
无论哪种方式, 真知灼见中显示的欺骗性域都分为两类;可疑的域对和非可疑域对。 这些类别进一步细分为三个不同的存储桶供您查看。 
  
*域对*是 "发件人:" 地址和发送基础结构的组合。 
  
- "发件人" 地址是邮件应用程序显示为 "发件人" 地址的地址。 此地址标识电子邮件的作者。 即，负责撰写邮件的个人或系统的邮箱。 有时称其为" 5322.From 地址"。
    
- 发送方结构或发件人是发送 IP 地址的 PTR 记录的组织域。 如果发送 ip 地址没有 PTR 记录, 则发件人由使用 CIDR 表示法 (/24) 中的255.255.255.0 子网掩码的发送 IP 进行标识。 例如, 如果 IP 地址为 192.168.100.100, 则发件人的完整 IP 地址为 192.168.100.100/24。
    
 **可疑域对**包括: 
  
- **高可信度欺骗**。 根据历史发送模式和域的信誉分数, Office 365 收到了这些域是可疑的强信号。 Office 365 非常确信域是哄骗的, 并且从这些域发送的邮件不太可能是合法的。 
    
- **中等可信度欺骗**。 根据历史发送模式和域的信誉分数, Office 365 接收到这些域有可疑的中等信号。 Office 365 适度确信域是欺骗的, 并且从这些域发送的邮件是合法的。 此存储桶具有包含误报 (FPs) 的更多可能性, 而不是高可信度欺骗存储桶。 
    
 **非可疑域对**包括**rescued 欺骗**。 Rescued 欺骗是指未通过显式身份验证检查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)、 [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)) 但通过了扩展的身份验证检查的域。 因此, Office 365 将代表您 rescued 邮件, 并且不会对邮件执行任何反欺骗操作。 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>查看有关欺骗性智能洞察力的可疑域对的详细信息

1. 在 "哄骗智能洞察力" 中, 单击任一域对 (high、适中或 rescued)。
  
此时将显示 "**哄骗智能真知灼见**" 页面, 其中显示了向您的组织发送未经身份验证的邮件的发件人列表。 此页上的信息可帮助您确定是否授权欺骗邮件, 或者是否需要执行进一步的操作。 您可以按邮件数、欺骗的上次检测日期等对信息进行排序。 (例如, 单击 "**邮件数**" 或 "**最后见到**的列标题"。) 
    
2. 在表中选择一个项目以打开详细信息窗格, 其中包含有关域对的丰富信息, 其中包括我们捕获此内容的原因、您需要执行的操作、域摘要、域摘要、WhoIs 有关发件人的数据以及我们在你的租户中从相同的发件人处看到的类似电子邮件。 在这里, 您还可以选择在**AllowedToSpoof**安全发件人列表中添加或删除域对。 
  
![欺骗智能洞察力详细信息窗格中的域的屏幕截图](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>在 AllowedToSpoof 安全发件人列表中添加或删除域

在欺骗性智能洞察力的详细信息窗格中查看域对时, 可以在 AllowedToSpoof 安全发件人列表中添加或删除域。 只需设置相应的开关即可。
  
这将修改欺骗性域和发送基础结构的唯一域对组合, 并且不会对整个欺骗域或独立的发送基础结构提供覆盖范围。 例如, 如果将以下域对添加到 "AllowedToSpoof" 发件人允许列表:*欺骗域*"gmail.com" 和*发送基础结构*"tm *. mx.com",* 则仅允许来自该域对的邮件欺骗。 其他试图欺骗 "gmail.com" 的发件人以及 "tms.mx.com" 尝试欺骗的其他域将继续受到欺骗性智能的保护。 
  
## <a name="related-topics"></a>相关主题

[详细了解防欺骗智能](learn-about-spoof-intelligence.md)
  
[Office 365 中的防欺骗保护](anti-spoofing-protection.md)
  
[演练 - 从仪表板到见解](from-a-dashboard-to-an-insight.md)
  
[演练 - 从详细报告到见解](from-a-detailed-report-to-an-insight.md)
  
[演练 - 从见解到详细报告](from-an-insight-to-a-detailed-report.md)
  

