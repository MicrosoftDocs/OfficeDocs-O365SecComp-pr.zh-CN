---
title: 如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: 了解如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”。
ms.openlocfilehash: f7ba560b4eb30abcda4c97617ead883659558bd8
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596715"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”

 **真实电子邮件是否在 Office 365 中被标记为“垃圾邮件”？试试本文中介绍的方法吧。**
  
Exchange Online Protection (EOP) 旨在筛选掉垃圾邮件，让收件箱中没有用户不想看到的内容。但有时 EOP 筛选掉的内容却是用户想看到的。
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>确定邮件被标记为“垃圾邮件”的原因

Office 365 中的许多垃圾邮件问题都可以这样解决：[查看电子邮件的邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)，并确定哪里出错。如果 X-Forefront-Antispam-Report 邮件头包含字符串 SFV:NSPM，表明 Exchange Online Protection (EOP) 扫描了邮件，并认为它不是垃圾邮件。在这种情况下，强烈建议[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，帮助我们改进筛选器。如果头中没有此值，可能表明邮件未通过垃圾邮件扫描，或存在导致邮件被错误分类为垃圾邮件的配置问题。可[详细了解反垃圾邮件的邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。
  
在邮件头中查找以下头和值。
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:BLK**：指明邮件被标记为“垃圾邮件”，因为发送地址位于收件人的阻止的发件人名单中。 
    
- **SFV:SKS**：指明邮件在经内容筛选器筛选前就已被标记为“垃圾邮件”。这可能是因为有将邮件标记为“垃圾邮件”的传输规则。运行邮件跟踪，以确定是否触发了可能已设置高垃圾邮件可信度 (SCL) 的传输规则。 
    
- **SFV:SKB**：指明邮件被标记为“垃圾邮件”，因为它符合垃圾邮件筛选器策略中的阻止列表。 
    
- **SFV:BULK**：指明 x-microsoft-antispam 头中的大量邮件可信度 (BCL) 值高于已为内容筛选器设置的大量邮件阈值。大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。
    
- **CAT:SPOOF** 或 **CAT:PHISH**：指明邮件可能存在欺骗行为。也就是说，无法验证邮件来源，来源可疑。如果有效，发件人需要确保已正确配置 SPF 和 DKIM。请检查 Authentication-Results 头，以获取更多信息。尽管难以让所有发件人都使用正确的电子邮件身份验证方法，但规避这些检查极为危险，最容易导致泄漏发生。 
    
### <a name="x-customspam"></a>x-customspam

- 此头指明邮件被标记为“垃圾邮件”，因为垃圾邮件筛选器中的[高级垃圾邮件选项之一已启用](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)。建议使用默认设置，除非你确实需要这些功能。 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>垃圾邮件过多的其他原因的解决方案

为了提高工作效率，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。
  
### <a name="for-admins"></a>对于管理员

- **让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供保护。如果 MX 没有指向 Office 365，EOP 就不会为用户提供垃圾邮件筛选服务。若要使用其他服务或设备为域提供垃圾邮件筛选服务，应考虑在 EOP 中禁用垃圾邮件保护。为此，可创建将 SCL 值设为 -1 的传输规则。如果稍后决定使用 EOP，请务必删除此传输规则。 
    
- **在 Outlook 中禁用 SmartScreen 筛选**：如果用户使用的是 Outlook 桌面客户端，他们应禁用 SmartScreen 筛选功能（此功能已终止）。如果启用，可能会导致误报。如果运行的是更新后的桌面 Outlook 客户端，无需遵守此要求。 
    
- **为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整任何可能会导致问题发生的设置。
    
- **立即允许发件人**：如果你需要立即允许发件人，强烈建议**仅允许特定发件人的 IP 地址**。也可以创建**同时**查找发件人域和成功的 Authentication-Results 头的传输规则，从而允许发件人，并还确保发件人通过 SPF 或 DKIM 等身份验证检查。 
    
### <a name="for-users"></a>对于用户

- **向 Microsoft 举报垃圾邮件**：按照[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)中的说明操作，向 Microsoft 举报垃圾邮件。此外，还可以向 junk@office365.microsoft.com 发送邮件，并附加要举报的一个或多个邮件。
    
    **重要提示**：如果未以附件形式转发邮件，[头就会丢失，导致我们无法改进](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/)在 Office 365 中的垃圾邮件筛选。 
    
- **将发件人添加到允许列表（但请谨慎使用）**：万不得已的方法是，可使用[“阻止或允许”（垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)。如果这样做，应注意可能会允许定向钓鱼邮件进入收件箱。
    

