---
title: 抵制发送到 Office 365 的垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5fd7d05b-96db-456f-81d6-1ac0e5bff530
description: Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。跨 Microsoft 电子邮件平台应用 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼筛选技术，以便为用户提供整个网络的最新反垃圾和反网络钓鱼工具及创新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。
ms.openlocfilehash: d4047e373b7808fe4b30dd23a1e7486ee7eb5a66
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002871"
---
# <a name="fighting-junk-email-sent-to-office-365"></a>抵制发送到 Office 365 的垃圾邮件

Microsoft 的电子邮件安全路线图包括不匹配的跨产品方法。跨 Microsoft 电子邮件平台应用 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼筛选技术，以便为用户提供整个网络的最新反垃圾和反网络钓鱼工具及创新。 EOP 的目标是提供全面且可用的电子邮件服务，以帮助用户检测垃圾邮件、诈骗电子邮件威胁（网络钓鱼）和恶意软件，并免受其侵扰。
  
## <a name="the-challenge"></a>挑战

无论对于客户，还是对于营销人员、支持人员、销售组织和各种规模的企业，电子邮件已经成为一个重要的通信工具。随着电子邮件的普及，电子邮件滥用的问题也日趋严重。无人监控的垃圾邮件会阻塞收件箱和网络、影响用户满意度，并阻碍合法电子邮件通信的有效性。这就是 Microsoft 仍继续致力于反垃圾邮件技术的原因。简单地说，它从包含和筛选垃圾邮件开始。  
  
## <a name="our-efforts"></a>我们的努力

EOP 提供了大量步骤，以最大程度减少垃圾邮件对我们用户的电子邮件体验产生的负面影响。
  
### <a name="exchange-online-protection-technology"></a>Exchange Online Protection 技术

为了帮助减少垃圾电子邮件，包含垃圾邮件保护的 EOP 使用专有的 EOP 筛选技术，以标识垃圾邮件，并将其从合法邮件分离出来。EOP 内容筛选器从我们的消费者平台 (Outlook.com) 了解已知的垃圾邮件、网络钓鱼威胁和用户反馈。这些数据类型帮助定型 EOP 技术，以识别合法的电子邮件和垃圾邮件，是发件人信誉的关键输入。垃圾邮件分类程序中正在进行的、来自 EOP 用户的反馈可以帮助确保 EOP 技术经过不断的定型和提高。
  
#### <a name="how-does-eop-work"></a>EOP 的工作原理

当外部用户向 EOP 用户发送电子邮件时，EOP 筛选技术将评估邮件的内容，并基于该邮件是垃圾邮件的概率为其分配一个等级。该分级作为一个名为"垃圾邮件可信度" (SCL) 的邮件属性在邮件中存储。当邮件发送到 EOP 中的其他反垃圾邮件保护层时，SCL 等级保留在电子邮件中。 
  
设置 EOP 内的规则以处理具有多种 SCL 等级的电子邮件。如果邮件 SCL 的等级大于某一阈值，则被视为垃圾邮件。该邮件将被隔离或传送到用户垃圾邮件文件夹，这取决于系统管理员如何配置垃圾邮件传送选项。
  
#### <a name="eop-filters"></a>EOP 筛选器

反垃圾邮件筛选技术，除了 EOP 还使系统管理员能够设置筛选器级别来进一步自定义电子邮件传递到这些用户帐户。管理员可以向安全发件人和域列表轻松添加发件人或域的名称，以便从发件人或域的电子邮件永远不会视为垃圾邮件的内容无论。有关信息，请参阅[安全发件人和阻止发件人列表在 Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)。
  
### <a name="phishing-protection"></a>网络钓鱼防护

网络钓鱼（Phishing，读作“fishing”）是一种身份盗用的形式，也是互联网增长最快的威胁之一。您通常可以标识出钓鱼邮件（当它请求个人或财务信息，或通过包含一个网站的链接来请求该类信息）。EOP 提供钓鱼保护作为 EOP 筛选技术的专有部分。EOP 筛选技术分析电子邮件，帮助检测欺诈性链接或欺骗域，以保护用户免受这些在线诈骗类型的侵扰。
  
#### <a name="how-does-phishing-protection-work"></a>网络钓鱼防护的工作原理

通常会发送一个网络钓鱼邮件，此邮件包含一个链接，一旦点击，该链接将重定向用户至看起来是有效的欺诈性网站（看起来像是您的财务机构或在线服务）。该网络钓鱼网站通常提示用户输入个人信息（如用户姓名、密码和身份证号）。在网络钓鱼站点输入的任何信息，会帮助网络钓鱼者窃取您的身份。网络钓鱼者通过使用已知的、受信任的品牌名称和标志使其显得合法化。EOP 提供的网络钓鱼筛选技术检查邮件中潜在的网络钓鱼特性。如果找到，该电子邮件将被移动到垃圾邮件文件夹。
  
Microsoft 重点关注反钓鱼技术的两个方面：第一，防止网络钓鱼电子邮件到达我们的用户，第二，帮助消除用户被欺诈性电子邮件和网站欺骗的可能性。 
  
> [!TIP]
> 当用户访问已知或潜在的钓鱼网站时，Internet Explorer 版本 7 及以上版本将阻止或警告用户，这样用户就不会被骗提供个人信息。[确保您有 Internet Explorer 的最新版本](https://www.microsoft.com/windows/ie/default.mspx)。 
  
#### <a name="authentication"></a>身份验证

域欺骗是一种模仿合法电子邮件地址以使其看起来合法的欺骗方式。恶意的个人或组织在网络钓鱼诈骗中使用诈骗来引诱用户泄漏敏感的个人信息。披露此类信息可能会导致身份被盗和其他类型的欺诈。
  
EOP 使用发件人保护架构框架 (SPF)、域密钥识别邮件 (DKIM)、基于域的邮件身份验证、举报和一致性 (DMARC) 和其他隐式身份验证，以验证邮件的实际来源域与其声称的来源域相同。我们建议所有发件人使用 SPF 和 DKIM 保护其收件人免受垃圾邮件和钓鱼欺诈的侵害。此外，我们建议发件人考虑发布 DMARC 以拒绝或隔离未经身份验证的发件人发送的邮件。
  
- 若要了解有关 SPF 的详细信息，请参阅 [RFC 7208](https://tools.ietf.org/html/rfc7208) 和 [发件人策略框架](http://www.openspf.org/)。
    
- 若要了解有关 DKIM 的详细信息，请参阅 [RFC 6376](https://tools.ietf.org/html/rfc6376) 和 [DKIM.org](http://dkim.org/)。
    
- 若要了解有关 DMARC 的详细信息，请参阅 [DMARC.org](https://dmarc.org/)。
    
### <a name="legislation"></a>立法

在 Microsoft，我们认为新技术开发和自我管理需要有效的政府政策和法律体系的支持。全球垃圾邮件的激增促使许多立法机构规范商业电子邮件。现在，很多国家/地区都出台了反垃圾邮件法。美国已针对垃圾邮件的管理制定了相应的联邦法律，同时各个州也制定了相关的法律，这种互补措施有助于减少垃圾邮件，同时确保合法的电子商务能够正常开展。CAN-SPAM Act（反垃圾邮件法）为抵制欺诈和欺骗性电子邮件提供了更有力的法律武器。
  

