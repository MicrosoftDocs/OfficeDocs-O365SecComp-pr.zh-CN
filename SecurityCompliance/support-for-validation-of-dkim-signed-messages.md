---
title: 支持 DKIM 签名邮件验证
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: 了解 DKIM 验证签名 Exchange Online Protection 和 Exchange Online 中的邮件
ms.openlocfilehash: 22f0d1c4fdd6b1e159db732d6ef3d956efbf99c9
ms.sourcegitcommit: 75b985b2574f4be70cf352498ea300b3d99dd338
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2018
ms.locfileid: "26255827"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="eb789-103">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="eb789-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="eb789-p101">Exchange Online Protection (EOP) 和 Exchange Online 支持对域名密钥识别邮件标准 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 邮件进行入站验证。DKIM 是一种验证邮件的方法，可确认邮件是从它声称的域所发送，而不是由其他人所伪造。它会向负责发送该邮件的组织发送一封电子邮件。DKIM 验证功能自动用于通过 IPv6 通信发送的所有邮件。（有关 IPv6 支持的详细信息，请参阅[支持通过 IPv6 发送的匿名入站电子邮件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。）</span><span class="sxs-lookup"><span data-stu-id="eb789-p101">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages. DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else. It ties an email message to the organization responsible for sending it. DKIM verification is automatically used for all messages sent over IPv6 communications. (For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="eb789-p102">DKIM 可在邮件标头中验证出现在 DKIM 签名标头中的数字签名邮件。DKIM 签名验证的结果将标记在符合 RFC 7001（[用于指示邮件身份验证状态的邮件标头字段](https://www.rfc-editor.org/rfc/rfc7001.txt)）的身份验证结果标头中。邮件标头文本将如下所示（其中 contoso.com 是发件人）：</span><span class="sxs-lookup"><span data-stu-id="eb789-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="eb789-112">管理员可以筛选 DKIM 验证结果创建 Exchange[邮件流规则](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)（也称作传输规则） 或路由邮件作为需要。</span><span class="sxs-lookup"><span data-stu-id="eb789-112">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

