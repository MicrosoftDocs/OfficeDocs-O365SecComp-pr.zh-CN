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
# <a name="office-365-email-anti-spam-protection"></a>Office 365 电子邮件反垃圾邮件保护

Office 365 中的垃圾邮件太多您担心？我们已将多个垃圾邮件筛选器内置您的 Office 365 或 Exchange Online Protection (EOP) 服务，以便从接收您第一条消息仍未受保护您的电子邮件。为了帮助防止 Office 365 中的垃圾邮件，您可能想要更改处理您的组织中的特定问题的保护设置 — 说您正在接收大量的垃圾邮件来自特定发件人，例如 — 或到只可以精细优化您的设置，以便它们定制最好地满足组织的需求。为此，您可以更改 Office 365 安全性的反垃圾邮件设置&amp;合规性中心。
  
本文适用于 Office 365 管理员。如果您不是管理员，但您是 Office 365 用户，并且想要了解如何处理您收到的垃圾邮件，这不是您在寻找一文。相反，如果您使用的 PC Outlook 或 Outlook for Mac，从开始[垃圾邮件筛选器的概述](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。如果您使用 Outlook web 上的，从开始[了解垃圾邮件和网络钓鱼](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)。
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>这些选项，有助于防止 Office 365 中的垃圾邮件

 **连接筛选。** 当您使用的连接筛选时，Office 365 检查发件人信誉之前允许获取一条消息。您可以创建允许列表中或安全发件人列表中，以确保您收到来自特定 IP 地址或 IP 地址范围发送给您每条消息。您还可以创建从其阻止邮件，调用阻止列表的 IP 地址的列表。有关详细信息，请参阅[配置连接筛选器策略](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)。如果您担心 Office 365 中的垃圾邮件，使用连接筛选以防止出现垃圾邮件。
  
对于具有 Office 365 企业 E5 或购买高级威胁保护 (ATP) 许可证的客户，连接筛选使用欺骗智能创建允许和阻止发件人在伪造您的域的列表。有关详细信息，请参阅[了解更多有关欺骗智能](https://go.microsoft.com/fwlink/?LinkID=735009)。
  
 **垃圾邮件筛选。** Office 365 检查邮件特征符合垃圾邮件使用垃圾邮件筛选。您可以更改要对邮件标识为垃圾邮件，并选择是否以筛选以特定语言撰写或从特定国家或地区发送的邮件的操作。您还可以打开高级垃圾邮件筛选选项，如果您想要使用垃圾邮件筛选保守方法。此外，还可以配置最终用户垃圾邮件通知，告知用户而时适用于它们的邮件发送到隔离邮箱。（将邮件发送到隔离邮箱是之一的可配置的操作。）从这些通知中，最终用户可以释放误报和报告给 Microsoft 进行分析。有关详细信息，请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)。为了帮助防止 Office 365 中的垃圾邮件，请使用垃圾邮件筛选，如果您担心 Office 365 中的垃圾邮件太多，使用连接筛选以防止出现垃圾邮件。
  
> [!NOTE]
> 为独立 EOP 客户： 默认情况下，EOP 垃圾邮件筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，为了确保**将邮件移至垃圾邮件文件夹**操作将处理的本地邮箱，必须配置两个 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)。 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>如果您收到垃圾邮件太多 Office 365 中的额外信息

下面的视频提供配置垃圾邮件筛选在 EOP 中的概述。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
有关详细信息，请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/p/?LinkId=617147)主题。 
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>检查您的传出消息以防止 Office 365 中的垃圾邮件

 **出站筛选。** Office 365 还会进行检查以确保您的用户不发送垃圾邮件。例如，用户的计算机可能获取感染后，即可发送垃圾邮件，因此我们构建防范调用*出站筛选*的恶意软件。无法关闭出站筛选，但您可以配置[配置出站垃圾邮件策略](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)中所述的设置。如果您担心 Office 365 中的垃圾邮件太多，则可以使用出站筛选，为了帮助防止 Exchange Online 中的垃圾邮件。
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>除基础知识： 更多的方式，以防止 Office 365 中的垃圾邮件
<a name="BeyondBasics"> </a>

 **邮件流规则。** 如果您希望超越内置垃圾邮件筛选和创建自定义规则的基于业务政策，*[邮件流规则](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*，也称作*传输规则*，帮助您的另一个筛选器阻止 Office 365 中的垃圾邮件。例如，您可以使用邮件流规则设置的垃圾邮件可信度级别 (SCL) 值符合特定条件的邮件[使用设置垃圾邮件可信度 (SCL) 在消息中的邮件流规则](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)中所述。 
  
 **电子邮件身份验证。** 域名系统 (DNS) 用于将可验证信息添加到有关电子邮件的发件人的电子邮件的技术称为电子邮件身份验证。更高级的 Office 365 管理员可以使用这些电子邮件身份验证方法： 
  
- **发件人策略框架 (SPF)。** SPF 通过验证声称的发送域所有者对发件人的 IP 地址来验证电子邮件的原点而言的。快速了解到 SPF 并获取快速配置，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)。Office 365 如何使用 SPF，更深入地了解或故障排除或非标准部署如混合部署，启动与[Office 365 如何使用发件人策略框架 (SPF) 以防止欺骗](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)。
    
- **域密钥识别邮件 (DKIM)。** DKIM 允许您附加到您发送的电子邮件的电子邮件邮件头中的数字签名。从您的域中接收电子邮件的电子邮件系统使用此数字签名来确定是否合法收到的传入电子邮件。有关 DKIM 和 Office 365 的信息，请参阅[使用 DKIM 验证从您在 Office 365 中的域发送出站电子邮件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)。
    
- **基于域的邮件身份验证、 报告和一致性声明 (DMARC)。** 接收邮件系统的 DMARC 帮助确定如何处理失败 SPF 或 DKIM 检查和电子邮件合作伙伴提供其他的信任级别的消息。DMARC 设置的信息，请参阅[使用 DMARC 用于验证 Office 365 中的电子邮件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。
    
如果您担心垃圾邮件和网络钓鱼欺骗 Office 365 中，使用 SPF、 DKIM 和 DMARC 一起为了帮助防止垃圾邮件和不需要欺骗。
  
 **最终用户管理设置。** 如果您正在寻找有关最终用户如何管理他们自己的垃圾邮件设置的信息，则签出[的垃圾邮件筛选器概述](https://go.microsoft.com/fwlink/?LinkId=270065)（针对 Microsoft Outlook 用户） 或[了解垃圾邮件和网络钓鱼](https://go.microsoft.com/fwlink/?LinkId=270068)（对于 web 用户的 Outlook)。如果您使用 EOP 保护本地邮箱，请务必使用目录同步，以确保这些设置都会同步到服务。有关设置目录同步的详细信息，请参阅在[EOP 中的管理邮件用户](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)的"使用目录同步管理邮件用户"。
  
## <a name="for-more-information"></a>详细信息
<a name="BeyondBasics"> </a>

[博客： 为什么垃圾邮件和网络钓鱼获取通过 Office 365？](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[反垃圾邮件保护常见问题](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[使用安全列表或其他技术阻止误报电子邮件被标记为垃圾邮件](prevent-email-from-being-marked-as-spam-0.md)
  
[如何设置 Office 365 垃圾邮件筛选以帮助阻止垃圾邮件](block-email-spam-to-prevent-false-negatives.md)
  
[垃圾邮件和批量邮件之间的区别是什么？](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[反垃圾邮件邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[退信消息和 EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  
## <a name="still-need-help"></a>仍需要帮助？
<a name="BeyondBasics"> </a>

[![从 Office 365 社区论坛获取帮助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理员：登录并创建一个服务请求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理员：电话支持](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

