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
description: 了解可帮助您阻止 Exchange Online 和 Office 365 中的垃圾邮件的反垃圾邮件设置和筛选器。 在 Office 365 中获取过多垃圾邮件？ 您可以自定义垃圾邮件筛选器和反垃圾邮件策略设置。
ms.openlocfilehash: 253ef10ac98b10377252a7a43fa306dd5a0ea90a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242510"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 电子邮件反垃圾邮件保护

您是否担心 Office 365 中的垃圾邮件太多？ 我们已在 Office 365 或 Exchange Online Protection (EOP) 服务中构建了多个垃圾邮件筛选器, 因此你的电子邮件将从你收到第一封邮件起到保护。 为了帮助阻止 Office 365 中的垃圾邮件, 您可能需要更改保护设置以处理组织中的特定问题, 例如, 您接收到来自特定发件人的大量垃圾邮件, 或者只是对设置进行微调以使其在量身定制以最大限度地满足组织的需求。 若要执行此操作, 您可以更改 Office 365 安全&amp;合规中心中的反垃圾邮件设置。
  
本文适用于 Office 365 管理员。 如果你不是管理员, 但你是 Office 365 用户, 并且想要了解如何处理你收到的垃圾邮件, 这不是你要查找的文章。 相反, 如果将 Outlook 用于 PC 或 outlook for Mac, 请从[垃圾邮件筛选器的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)开始。 如果您使用 web 上的 Outlook, 请从[了解垃圾电子邮件和网络钓鱼](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)开始。
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>这些选项有助于阻止 Office 365 中的垃圾邮件

 **连接筛选**: 当您使用连接筛选时, Office 365 将检查发件人的信誉, 然后允许邮件通过。 您可以创建允许列表或安全发件人列表, 以确保从特定 IP 地址或 ip 地址范围收到发送给您的每封邮件。 您还可以创建要从中阻止邮件的 IP 地址列表, 称为阻止列表。 有关详细信息，请参阅[Configure the Connection Filter Policy](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。 如果你关注 Office 365 中的垃圾邮件, 请使用连接筛选帮助阻止垃圾邮件。
  
对于拥有 Office 365 企业版 E5 或购买了高级威胁防护 (ATP) 许可证的客户, 欺骗版智能使用连接筛选来创建欺骗您的域的发件人的允许名单和阻止名单。 有关详细信息, 请参阅[了解有关欺骗情报的详细](https://go.microsoft.com/fwlink/?LinkID=735009)信息。
  
 **垃圾邮件筛选**: Office 365 使用垃圾邮件筛选检查邮件特征与垃圾邮件的一致性。 您可以更改要对已识别为垃圾邮件采取的操作，同时选择是否筛选以特定语言编写，或来自特定国家或地区的邮件。 如果您希望主动进行垃圾邮件筛选，您也可以启用高级垃圾邮件筛选选项。 此外，您可以配置最终用户垃圾邮件通知，在原本要发送给用户的邮件被发送到隔离邮箱时通知用户。 (将邮件发送到隔离是可配置的操作之一。)在这些通知中, 最终用户可以释放误报并将其报告给 Microsoft 进行分析。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)。 为了帮助阻止 office 365 中的垃圾邮件, 请使用垃圾邮件筛选 (如果你担心 office 365 中的垃圾邮件过多), 请使用连接筛选帮助阻止垃圾邮件。
  
> [!NOTE]
> 对于 EOP 独立客户: 默认情况下, EOP 垃圾邮件筛选器将检测到的垃圾邮件发送到每个收件人的 "垃圾邮件" 文件夹。 但是, 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 必须在您的本地服务器上配置两个 Exchange 邮件流规则 (也称为传输规则), 以检测添加的垃圾邮件头EOP. 有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>如果您在 Office 365 中收到过多垃圾邮件, 则需要额外的信息

以下视频概述了如何在 EOP 中配置垃圾邮件筛选。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
有关更多详细信息, 请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)主题。
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>检查您的传出邮件以阻止 Office 365 中的垃圾邮件

 **出站筛选**: Office 365 还会进行检查以确保您的用户不会发送垃圾邮件。 例如, 用户的计算机可能会受到恶意软件的感染, 从而导致其发送垃圾邮件, 因此我们将针对被称为 "*出站筛选*" 的保护建立保护。 无法关闭出站筛选, 但可以配置[配置出站垃圾邮件策略](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)中所述的设置。 如果您担心 Office 365 中的垃圾邮件太多，可使用出站筛选功能，以帮助在 Exchange Online 中阻止垃圾邮件。
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>除了基础: 阻止 Office 365 中的垃圾邮件的更多方法

 **邮件流规则**: 如果您想要超越内置垃圾邮件筛选功能并创建基于您的业务策略的自定义规则,_[邮件流规则](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)_(也称为_传输规则_) 是可帮助您阻止 Office 中的垃圾邮件的另一个筛选器365。 例如, 可以使用邮件流规则为符合特定条件的邮件设置垃圾邮件可信度 (SCL) 值, 如[使用邮件流规则在邮件中设置垃圾邮件可信度 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)中所述。
  
 **电子邮件身份验证**: 使用域名系统 (DNS) 向关于电子邮件发件人的电子邮件添加可验证信息的技术称为电子邮件身份验证。 更高级的 Office 365 管理员可以利用以下电子邮件身份验证方法:
  
- **发件人策略框架 (SPF)**: SPF 验证发件人的 IP 地址是否针对发送域的声称所有者来验证电子邮件的来源。 有关 SPF 的快速介绍以及如何快速配置 SPF 的信息，请参阅[Set up SPF in Office 365 to help prevent spoofing](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。 有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。

- **域密钥识别邮件 (DKIM)**: DKIM 允许您在发送的电子邮件的邮件头中, 将数字签名附加到电子邮件。 从你的域接收电子邮件的电子邮件系统使用此数字签名来确定其收到的传入电子邮件是否合法。 有关 DKIM 和 office 365 的信息, 请参阅[使用 DKIM 验证从您的域发送的来自 Office 365 的出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。

- **基于域的邮件身份验证、报告和一致性 (DMARC)**: DMARC 帮助接收邮件系统, 以确定如何处理失败的 SPF 或 DKIM 检查的邮件, 并为您的电子邮件合作伙伴提供另一个信任级别。 有关设置 DMARC 的信息, 请参阅[使用 DMARC 验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

如果你关注 Office 365 中的垃圾邮件、网络钓鱼和欺骗, 请结合使用 SPF、DKIM 和 DMARC 来帮助防止垃圾邮件和不必要的欺骗。
  
 **最终用户托管设置**: 如果你正在寻找有关最终用户如何管理自己的垃圾邮件设置的信息, 请查看[垃圾邮件筛选器的概述](https://go.microsoft.com/fwlink/?LinkId=270065)(针对 Microsoft Outlook 用户) 或[了解垃圾邮件和网络钓鱼](https://go.microsoft.com/fwlink/?LinkId=270068)(针对Outlook 网页用户)。 如果您使用 EOP 来保护本地邮箱, 请务必使用目录同步来确保这些设置已同步到服务。 有关如何设置目录同步的详细信息，请参阅[在 EOP 中管理邮件用户](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)中的"使用目录同步管理邮件用户"。
  
## <a name="for-more-information"></a>有关详细信息

[博客: 垃圾邮件和仿冒网站如何通过 Office 365？](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[反垃圾邮件保护常见问题](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[使用安全列表或其他技术避免出现标记为“垃圾邮件”的误报电子邮件](prevent-email-from-being-marked-as-spam-0.md)
  
[如何设置 Office 365 垃圾邮件筛选以帮助阻止垃圾邮件](reduce-spam-email.md)
  
[垃圾邮件和批量电子邮件之间有什么区别？](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[反垃圾邮件邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[退信消息和 EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)

## <a name="more-resources"></a>更多资源

[从 Office 365 社区论坛获取帮助](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[管理员：登录并创建服务请求](https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[管理员：呼叫支持](https://go.microsoft.com/fwlink/p/?LinkID=518322)
