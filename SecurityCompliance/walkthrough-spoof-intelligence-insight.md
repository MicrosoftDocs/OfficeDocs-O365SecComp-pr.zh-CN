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
# <a name="walkthrough-spoof-intelligence-insight"></a>演练： 欺骗智能见解

通过使用欺骗智能洞察，您可以快速确定合法未经验证电子邮件发送的发件人。通过允许发送带欺骗性的消息，可以减少任何误报转到您的用户的风险。
  
此外，您还可以使用欺骗智能监视和管理提供额外的安全和防止遭受不安全邮件到达组织中的允许的域的对。
  
您可以使用欺骗智能洞察中安全&amp;合规性中心如果您的工作或学校帐户已被授予，Office 365 全局管理员、 安全管理员或安全读者权限。有关详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
  
如果您是新手[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)，它可能有助于请参阅如何您可以轻松地从导航仪表板到见解和建议的操作。
  
您可以安全中查看来自多个仪表板欺骗智能洞察&amp;合规性中心。无论您要看的仪表板，洞察提供相同的详细信息，并允许您快速执行相同的任务。
  
这是一个安全的几个演练&amp;合规性中心。若要导航报表和见解，请参阅相关的主题部分中的演练。
  
## <a name="getting-to-the-spoof-intelligence-insight-in-the-security-amp-compliance-center"></a>获取安全中欺骗智能洞察到&amp;合规性中心

1. 若要开始，您将需要[转到安全&amp;合规性中心](go-to-the-securitycompliance-center.md)。
    
2. 安全中&amp;合规性中心中，转到**威胁管理** \> **仪表板。**
    
3. 在**洞察力**行中，查找欺骗智能见解。如果已启用欺骗智能然后洞察有权获得**Spoofed 域的失败过去 30 天的身份验证**。如果尚未启用欺骗保护，然后洞察将提示您以使用标题**启用欺骗保护**完成此操作。 
    
## <a name="about-the-insight-on-the-dashboard"></a>关于仪表板上洞察

仪表板上的洞察显示类似的信息。
  
![欺骗智能洞察的屏幕截图](media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)
  
此洞察有两种模式：
  
 **洞察模式**。如果必须启用任何欺骗策略，然后洞察显示过去 30 天内，多少邮件受到我们欺骗智能功能。 
  
 **如果模式**。如果您没有启用任何欺骗策略，然后洞察显示多少邮件*将*具有已受我们欺骗智能功能过去 30 天内。 
  
无论进行上述，带欺骗性的域中的洞察显示可分为两类;可疑域对和非可疑域对。这些类别进一步到要查看的三个不同存储桶细分。 
  
*域对*是组合的"从:"地址和发送基础结构。 
  
- "从"地址是邮件应用程序显示为发件人地址的地址。此地址标识的电子邮件的作者。即负责编写邮件系统的人的邮箱。有时称为 5322.From 地址。
    
- 发送的基础结构或发件人发送的 IP 地址的 PTR 记录的组织域。如果发送 IP 地址具有没有 PTR 记录，则发件人标识与 255.255.255.0 发送的 IP 子网掩码 CIDR 表示法 （/ 24）。例如，如果该 IP 地址是 192.168.100.100 发件人的完整 IP 地址是 192.168.100.100/24。
    
 **可疑域对**包括： 
  
- **高可信度欺骗**。Office 365 收到强信号这些域的可疑，基于历史发送模式和的域的信誉分数。Office 365 的域的欺骗和从这些域发送邮件不太可能合法高信心。 
    
- **中等可信度欺骗**。Office 365 收到中等信号这些域的可疑，根据历史发送模式和的域的信誉分数。Office 365 的域的欺骗和从这些域发送邮件是合法中等信心。此地址散列表元具有更好的包含误报 (FPs) 比高可信度欺骗地址散列表元。 
    
 **非可疑域对**包括**rescued 欺骗**。挽救的欺骗是已失败的显式身份验证检查 ( [SPF](https://docs.microsoft.com/office365/SecurityCompliance/how-office-365-uses-spf-to-prevent-spoofing)， [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)， [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email))，但传递我们扩展身份验证检查的域。由于此，Office 365 rescued 代表您的邮件并没有反欺骗采取操作的邮件。 
  
## <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>查看有关可疑域名对从欺骗智能洞察详细的信息

1. 在欺骗智能洞察中，单击的任何域对 （高、 中等或挽救）。
  
将显示**欺骗智能洞察**页，显示您的用户发送到您的组织未经身份验证的邮件的发件人列表。此页上的信息可帮助您确定是否或未授权欺骗的邮件或是否需要进一步执行操作。您可以排序邮件计数欺骗上次检测到，日期信息和详细信息。（例如单击列标题，例如**消息计数**或**上一次发现**。） 
    
2. 选择要打开包含大量信息的域对详细信息窗格中的表中的项目，包括为什么我们捕获此，您需要做什么，一个域摘要，我们已从同一发件人租户中看到类似电子邮件发件人，以及 WhoIs 数据。从此处，您还可以添加或移除**AllowedToSpoof**安全发件人列表中的域对。 
  
![欺骗智能洞察详细信息窗格中的域的屏幕截图](media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)
  
## <a name="add-or-remove-a-domain-from-the-allowedtospoof-safe-sender-list"></a>添加或从 AllowedToSpoof 安全发件人列表中删除域

添加或查看详细信息窗格中的欺骗智能洞察的域对时从 AllowedToSpoof 安全发件人列表中删除域。只需相应地设置切换。
  
这修改带欺骗性的域和发送基础结构的唯一域对组合并不提供范围的整个欺骗的域或隔离中的发送基础结构。例如，如果将以下两个域添加到 AllowedToSpoof 发件人允许列表：*造假域*"gmail.com"和*发送基础结构*"tm *。 mx.com"，* ，然后将允许仅从该域对邮件欺骗。试图欺骗"gmail.com"和"tms.mx.com"尝试欺骗将继续受到欺骗智能保护其他域的其他发件人。 
  
## <a name="related-topics"></a>相关主题

[了解有关欺骗智能的详情](learn-about-spoof-intelligence.md)
  
[Office 365 中的防欺骗保护](anti-spoofing-protection.md)
  
[演练 - 从仪表板到见解](from-a-dashboard-to-an-insight.md)
  
[演练 - 从详细报告到见解](from-a-detailed-report-to-an-insight.md)
  
[演练 - 从见解到详细报告](from-an-insight-to-a-detailed-report.md)
  

