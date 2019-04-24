---
title: 参考：策略、实践和指南
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 制定了各种策略和过程, 并采用了几个行业最佳实践来帮助我们的用户避免滥用、不受欢迎或恶意的电子邮件。
ms.openlocfilehash: a074bb1fbe6fedb9054b98d3723511607fed7304
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261530"
---
# <a name="reference-policies-practices-and-guidelines"></a>参考：策略、实践和指南
  
Microsoft 致力于在 Web 上提供最可信赖的用户体验。因此，Microsoft 已开发了多种策略、过程并采用多个行业的最佳实践，以保护我们的用户免受滥用、不必要或恶意的电子邮件的侵扰。试图向 Office 365 的用户发送电子邮件的发件人应确保用户完全理解并遵循本文中的指南，以帮助避免潜在的传送问题。
  
如果您不遵从这些策略和指南，我们的支持小组可能无法协助您。如果您遵循本文中介绍的指南、实践和策略，但基于您的发送 IP 地址仍然遇到传送问题，请按步骤提交除名请求。有关说明，请参阅 [使用除名门户来将自己从 Office 365 阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
## <a name="general-microsoft-policies"></a>Microsoft 一般性策略
<a name="GenMsftPolicies"> </a>

发送到 Office 365 用户的电子邮件必须遵从管理电子邮件传输和 Office 365 使用的所有 Microsoft 策略。
  
- 适用于 Office 365 的服务条款；尤其是，禁止使用服务发送垃圾邮件或传播恶意软件
    
- [Microsoft 服务协议](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>政府法规
<a name="GovtRegulations"> </a>

发送到 Office 365 用户的电子邮件必须遵循在管辖范围内管理电子邮件通信的所有适用的法律和法规。
  
- [CAN-SPAM Act:A Compliance Guide for Business](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- ["Remove Me" Responses and Responsibilities:Email Marketers Must Honor "Unsubscribe" Claims](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>技术指南
<a name="TechGuidelines"> </a>

发送到 Office 365 的电子邮件应遵循以下文档中列出的适用性建议（某些链接只提供英文版本）。
  
- [RFC 2505:Anti-Spam Recommendations for SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)
    
- [RFC 2920:SMTP Service Extension for Command Pipelining](https://www.ietf.org/rfc/rfc2920.txt)
    
此外，连接到 Office 365 的电子邮件服务器必须遵从以下要求：
  
- 发件人应符合互联网电子邮件传输的所有技术标准，该标准由互联网协会的互联网工程任务组 (IETF) 发布，包括 RFC 5321、RFC 5322 和其他。 
    
- 在给出 500 和 599 之间的数值 SMTP 错误响应代码后（也称为永久未送达响应或 NDR），发件人不得再次向该收件人传输邮件。
    
- 多个未送达响应后，发件人必须停止进一步向该收件人发送邮件的操作。
    
- 邮件不得通过不安全的电子邮件中继或代理服务器传输。
    
- 从单个列表或从由发件人托管的所有列表取消订阅的机制，必须清楚地说明，且易于供收件人查找使用。
    
- 来自动态的 IP 空间的连接可能不被接受。
    
- 电子邮件服务器必须具有有效的反向 DNS 记录。
    
## <a name="reputation-management"></a>信誉管理
<a name="RepManagement"> </a>

发件人、ISP 和其他服务提供商应主动管理出站 IP 地址的信誉。
  
## <a name="office-365-limits"></a>Office 365 限制
<a name="sectionSection4"> </a>

发件人必须遵循 [Exchange Online Protection 限制](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)列出的 Office 365 限制。
  
## <a name="email-delivery-resources-and-organizations"></a>电子邮件传送资源和组织
<a name="sectionSection5"> </a>

Microsoft 积极与行业机构和服务提供商合作，以改善互联网和电子邮件的生态系统。这些组织已经发布了我们支持并建议发件人遵循的最佳实践的文档。这提高了您在世界各地的多个电子邮件服务提供商直接传送邮件的能力。
  
- [信息传送、恶意软件和移动反滥用工作组](https://www.m3aawg.org/)
    
- [在线信任联盟](https://www.otalliance.org/resources)
    
- [Email Sender &amp; Provider Coalition](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>滥用和垃圾邮件报告
<a name="AbuseSpamReports"> </a>

若要报告非法、滥用、不受欢迎或恶意的电子邮件, 请[在 web 上的 Outlook 中报告垃圾电子邮件和网络钓鱼诈骗](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。 发送这些类型的通信将违反 Microsoft 策略，我们将对已确认的报告采取适当措施。
  
## <a name="law-enforcement"></a>法律执行
<a name="sectionSection7"> </a>

如果您是执法机构的成员，想就 Office 365 相关法律文档为 Microsoft Corportation 服务，或如果您对提交给 Microsoft 的法律文档有任何问题，请拨打 (1) (425) 722-1299。
  

