---
title: 支持通过 IPv6 发送的匿名入站电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: 了解如何为 Exchange Online Protection 和 Exchange Online 配置来自 IPv6 源的匿名邮件支持。
ms.openlocfilehash: b6b1a0f42d879929de5059b6e197bd5fe14887dc
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600725"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>支持通过 IPv6 发送的匿名入站电子邮件

Exchange Online Protection (EOP) 和 Exchange Online 支持通过 IPv6 通信，从并非通过传输层安全 (TLS) 发送邮件的发件人接收匿名入站电子邮件。 您可以通过在[https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)microsoft 支持中打开 microsoft 365 管理中心, 单击 "**支持**", 然后单击 "**新建服务请求**", 选择通过以下方式在 IPv6 上接收邮件。 如果您未选择加入 IPv6，将继续通过 IPv4 接收邮件。
  
通过 IPv6 将邮件传输到服务的发件人必须符合以下两个要求：
  
1. 发件人的 IPv6 地址必须具有有效的 PTR 记录（发件人 IPv6 地址的[反向 DNS 记录](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)）。 
    
2. 发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。
    
无论您在选择 IPv6 之前进行了怎样的配置，都必须满足这些要求。 如果满足这两个要求，邮件将通过服务提供的正常电子邮件筛选。 如果不满足其中的一个或多个, 将使用以下450响应之一拒绝邮件:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
如果您未选择通过 IPv6 接收邮件，且发件人通过手动连接到邮件服务器，尝试强制通过 IPv6 发送邮件，邮件将被拒绝并返回如下所示的 550 响应：
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>详细信息

[支持 DKIM 签名邮件验证](support-for-validation-of-dkim-signed-messages.md)
  

