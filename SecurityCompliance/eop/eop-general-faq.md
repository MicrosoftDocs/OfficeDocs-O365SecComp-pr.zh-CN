---
title: EOP 一般常见问题解答
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9dbff00a-474e-4452-aeb5-5be9a6b8c6d5
description: 我们在此处回答了有关 Microsoft Exchange Online Protection (EOP) 云托管电子邮件筛选服务的一般常见问题。有关其他常见问题 (FAQ) 的主题，请转到下列链接：
ms.openlocfilehash: 9a8ac96678e33623803e95998780b4544dec5a78
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027379"
---
# <a name="eop-general-faq"></a>EOP 一般常见问题解答

我们在此处回答了有关 Microsoft Exchange Online Protection (EOP) 云托管电子邮件筛选服务的一般常见问题。有关其他常见问题 (FAQ) 的主题，请转到下列链接：
  
- [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)
    
- [委派管理常见问题解答](delegated-administration-faq.md)
    
- [反垃圾邮件保护常见问题](../anti-spam-protection-faq.md)
    
- [Exchange Online 中的安全发件人和阻止发件人列表](../safe-sender-and-blocked-sender-lists-faq.md)
    
- [隔离常见问题解答](../quarantine-faq.md)
    
- [反恶意软件保护常见问题解答](../anti-malware-protection-faq-eop.md)
    
- [Message Trace FAQ](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx)
    
- [FOPE 到 EOP 的转换常见问题解答](http://technet.microsoft.com/library/e0e76b89-b0d3-4c0a-bfc8-137b579e983b.aspx)
    
 **问：什么是 EOP？**
  
答：EOP 是云托管的内置电子邮件筛选服务，用于保护客户免受垃圾邮件和恶意邮件的攻击和实现自定义策略规则。
  
 **问：如何注册以获得 EOP 试用版或购买 EOP？**
  
答：在 [Exchange Online 保护主页](https://go.microsoft.com/fwlink/p/?LinkId=279912)上注册 EOP 试用版或通过 Web 购买 EOP。请注意，购买试用版的功能与付费订阅相同，但还包含 [Exchange Enterprise CAL with Services](https://go.microsoft.com/fwlink/p/?LinkId=320619) 订阅计划中提供的其他功能。 
  
 **问：EOP 如何定价？**
  
答：EOP 由用户许可。有关最新定价信息，请参阅 [Exchange Online 保护主页](https://go.microsoft.com/fwlink/p/?LinkId=279912)。
  
 **问：EOP 投入生产需要多长时间？**
  
答：当您按照[设置 EOP 服务](set-up-your-eop-service.md)中的步骤更改 MX 记录时，您的邮件通过 EOP 传递，筛选会立即开始。MX 记录通过 DNS 传播可能需要花费 24-48 小时。在此过程中，您可以随时在 Exchange 管理中心 (EAC) 中精细调整保护设置。
  
 **问：必须使用 Microsoft Office 365 的所有功能，才能使用 EOP 吗？如果我只想使用 EOP 保护该怎么办，只使用它就足够了吗？**
  
答：你可以使用 EOP 保护内部部署邮箱，无需使用任何其他 Office 365 功能。这称为独立订阅。可以在 [Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)中找到 EOP 功能列表。
  
 **问：通过 EOP 注册电子邮件筛选时为什么需要 Office 365 租户？**
  
答：Office 365 是可以通过 Office 365 租户访问的产品和服务集合的名称。将 Office 365 租户视为可以向其添加电子邮件筛选许可证的起始点。
  
 **问：EOP 是否具有可在其中查找已知问题及预期解决方案的通信门户？有哪些新功能？**
  
答：Office 365 管理中心将包含一部分此类信息。如果您受到服务级别事件的影响，在登录 Office 365 管理中心后应查看通信警报（通常伴随着铃图标）。我们建议您阅读项目信息并根据情况进行处理。
  
关于新的 EOP 功能，[适用于企业的 Office 365 路线图](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)在找到有关即将推出的新功能的信息方面是不错的资源。我们还会在[官方博客](https://go.microsoft.com/fwlink/p/?LinkId=392724)网站上发布有关新功能的博客文章。 
  
 **问：该服务对旧版 Exchange 版本（比如 Exchange Server 2010）和非 Exchange 环境也有效吗？**
  
答：是的，该服务是不受服务器限制的，可以与任何 SMTP 邮件传输代理一起使用。
  
 **问：何种规模的组织可以使用该服务？**
  
答：任何规模。EOP 网络有足够的容量容纳您的增长，无论您的组织增长有多快。
  
 **设置 EOP 需要什么权限？**
  
要配置 EOP，您必须是 Office 365 全局管理员或 Exchange 公司管理员（组织管理角色组）。
  
 **问：如何知道我的数据和私人信息是安全的？**
  
答：若要了解有关我们确保你的数据和私人信息安全所采取的步骤（包括有关服务级别协议 (SLA) 的信息），请转到 [Office 365 信任中心](https://go.microsoft.com/fwlink/p/?LinkId=285405)。
  
 **问：是否有任何限制是我需要了解的，例如邮件大小限制？**
  
答：是的。有关 EOP 中限制的详细信息，请参阅 [Exchange Online Protection 限制](https://go.microsoft.com/fwlink/p/?LinkId=402617)。 
  
 **问：EOP 是否支持远程 Windows PowerShell？**
  
答：是的，可通过远程 Windows PowerShell 获得完整 EOP 功能。有关详细信息，请参阅 [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)。
  

