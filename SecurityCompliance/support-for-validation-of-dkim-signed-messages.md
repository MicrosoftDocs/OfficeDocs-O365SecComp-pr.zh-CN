---
title: 支持 DKIM 签名邮件验证
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: 了解 Exchange Online Protection 和 Exchange Online 中的 DKIM 签名邮件验证
ms.openlocfilehash: 75c104af4b3e6126bac37024de2c7f6ab337a028
ms.sourcegitcommit: 1947ad3c0dde9163ba9b6834d8b38bd04b4264a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "36643264"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a><span data-ttu-id="44be4-103">支持 DKIM 签名邮件验证</span><span class="sxs-lookup"><span data-stu-id="44be4-103">Support for validation of DKIM signed messages</span></span>

<span data-ttu-id="44be4-104">Exchange Online Protection (EOP) 和 Exchange Online 支持对域密钥标识邮件 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 邮件进行入站验证。</span><span class="sxs-lookup"><span data-stu-id="44be4-104">Exchange Online Protection (EOP) and Exchange Online support inbound validation of Domain Keys Identified Mail ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) messages.</span></span> <span data-ttu-id="44be4-105">DKIM 是一种方法, 用于验证邮件是否已从其发出的域发送, 以及其他人未被别人盗用。</span><span class="sxs-lookup"><span data-stu-id="44be4-105">DKIM is a method for validating that a message was sent from the domain it says it originated from and that it was not spoofed by someone else.</span></span> <span data-ttu-id="44be4-106">这将电子邮件绑定到负责发送它的组织上。</span><span class="sxs-lookup"><span data-stu-id="44be4-106">It ties an email message to the organization responsible for sending it.</span></span> <span data-ttu-id="44be4-107">DKIM 验证将自动用于通过 IPv6 通信发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="44be4-107">DKIM verification is automatically used for all messages sent over IPv6 communications.</span></span> <span data-ttu-id="44be4-108">在通过 IPv4 发送邮件时, Office 365 现在还支持 DKIM。</span><span class="sxs-lookup"><span data-stu-id="44be4-108">Office 365 also now supports DKIM when mail is sent over IPv4.</span></span> <span data-ttu-id="44be4-109">(有关 IPv6 支持的详细信息, 请参阅[通过 ipv6 对匿名入站电子邮件的支持](support-for-anonymous-inbound-email-messages-over-ipv6.md)。)</span><span class="sxs-lookup"><span data-stu-id="44be4-109">(For more information about IPv6 support, see [Support for anonymous inbound email messages over IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md).)</span></span>
  
<span data-ttu-id="44be4-p102">DKIM 可在邮件标头中验证出现在 DKIM 签名标头中的数字签名邮件。DKIM 签名验证的结果将标记在符合 RFC 7001（[用于指示邮件身份验证状态的邮件标头字段](https://www.rfc-editor.org/rfc/rfc7001.txt)）的身份验证结果标头中。邮件标头文本将如下所示（其中 contoso.com 是发件人）：</span><span class="sxs-lookup"><span data-stu-id="44be4-p102">DKIM validates a digitally signed message that appears in the DKIM-Signature header in the message headers. The results of a DKIM-Signature validation is stamped in the Authentication-Results header which conforms with RFC 7001 ([Message Header Field for Indicating Message Authentication Status](https://www.rfc-editor.org/rfc/rfc7001.txt)). The message header text appears similar to the following (where contoso.com is the sender):</span></span>
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
<span data-ttu-id="44be4-113">管理员可以在 DKIM 验证结果中创建 Exchange[邮件流规则](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)(也称为传输规则), 以根据需要筛选或路由邮件。</span><span class="sxs-lookup"><span data-stu-id="44be4-113">Admins can create Exchange [mail flow rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx) (also known as transport rules) on the results of a DKIM validation to filter or route messages as needed.</span></span> 
  

