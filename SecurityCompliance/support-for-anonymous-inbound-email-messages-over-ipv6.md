---
title: 支持通过 IPv6 发送的匿名入站电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/4/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
description: Exchange Online Protection (EOP) 和 Exchange Online 支持通过 IPv6 的发件人不会发送邮件通过传输层安全性 (TLS) 的通信接收的匿名入站的电子邮件。您可以加入从 UNRESOLVED_TOKEN_VAL(exMCSS) 请求此功能，通过打开在 Office 365 管理中心通过 IPv6 接收邮件https://portal.office.com/adminportal/home，单击支持，然后单击新建服务请求)。如果您不加入到您将继续通过 IPv4 接收消息的 IPv6。
ms.openlocfilehash: a07e79732e9027d5848b787101be11066b5f0cb5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026289"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="d2208-105">支持通过 IPv6 发送的匿名入站电子邮件</span><span class="sxs-lookup"><span data-stu-id="d2208-105">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="d2208-p102">Exchange Online Protection (EOP) 和 Exchange Online 支持通过 IPv6 的发件人不会发送邮件通过传输层安全性 (TLS) 的通信接收的匿名入站的电子邮件。您可以加入从 UNRESOLVED_TOKEN_VAL(exMCSS) 请求此功能，通过打开在 Office 365 管理中心通过 IPv6 接收邮件[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)，单击**支持**，然后单击**新建服务请求**)。如果您不加入到您将继续通过 IPv4 接收消息的 IPv6。</span><span class="sxs-lookup"><span data-stu-id="d2208-p102">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS). You can opt-in to receive messages over IPv6 by requesting this functionality from UNRESOLVED_TOKEN_VAL(exMCSS) by opening the Office 365 admin center at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home), clicking **Support**, and then clicking **New service request**). If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="d2208-109">通过 IPv6 将邮件传输到服务的发件人必须符合以下两个要求：</span><span class="sxs-lookup"><span data-stu-id="d2208-109">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="d2208-110">发件人的 IPv6 地址必须具有有效的 PTR 记录（发件人 IPv6 地址的[反向 DNS 记录](https://en.wikipedia.org/wiki/Reverse_DNS_lookup)）。</span><span class="sxs-lookup"><span data-stu-id="d2208-110">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="d2208-111">发件人必须通过 SPF 验证（在 [RFC 7208](https://tools.ietf.org/html/rfc7208) 中定义）或 [DKIM 验证](http://dkim.org/)（在 [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt) 中定义）。</span><span class="sxs-lookup"><span data-stu-id="d2208-111">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](http://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="d2208-p103">满足这些要求是必需的无论您之前在选择加入到 IPv6 的配置。如果满足这两个要求，将经过邮件正常的电子邮件筛选服务提供。如果一个或另一个不满足，消息将被拒绝具有以下 450 响应之一：</span><span class="sxs-lookup"><span data-stu-id="d2208-p103">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6. If both requirements are met, the message will go through normal email message filtering provided by the service. If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="d2208-115">如果您未选择通过 IPv6 接收邮件，且发件人通过手动连接到邮件服务器，尝试强制通过 IPv6 发送邮件，邮件将被拒绝并返回如下所示的 550 响应：</span><span class="sxs-lookup"><span data-stu-id="d2208-115">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="d2208-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2208-116">For more information</span></span>

[<span data-ttu-id="d2208-117">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="d2208-117">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  
