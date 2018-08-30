---
title: 支持 DKIM 签名邮件验证
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
description: Exchange Online Protection (EOP) 和 Exchange Online 支持对域名密钥识别邮件标准 (DKIM) 邮件进行入站验证。DKIM 是一种验证邮件的方法，可确认邮件是从它声称的域所发送，而不是由其他人所伪造。它会向负责发送该邮件的组织发送一封电子邮件。DKIM 验证功能自动用于通过 IPv6 通信发送的所有邮件。（有关 IPv6 支持的详细信息，请参阅支持通过 IPv6 发送的匿名入站电子邮件。）
ms.openlocfilehash: d2fab69847732bb7ed54f943d2c7845e06084936
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002248"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>支持 DKIM 签名邮件验证

Exchange Online Protection (EOP) 和 Exchange Online 支持对域名密钥识别邮件标准 ([DKIM](https://www.rfc-editor.org/rfc/rfc6376.txt)) 邮件进行入站验证。DKIM 是一种验证邮件的方法，可确认邮件是从它声称的域所发送，而不是由其他人所伪造。它会向负责发送该邮件的组织发送一封电子邮件。DKIM 验证功能自动用于通过 IPv6 通信发送的所有邮件。（有关 IPv6 支持的详细信息，请参阅[支持通过 IPv6 发送的匿名入站电子邮件](support-for-anonymous-inbound-email-messages-over-ipv6.md)。）
  
DKIM 可在邮件标头中验证出现在 DKIM 签名标头中的数字签名邮件。DKIM 签名验证的结果将标记在符合 RFC 7001（[用于指示邮件身份验证状态的邮件标头字段](https://www.rfc-editor.org/rfc/rfc7001.txt)）的身份验证结果标头中。邮件标头文本将如下所示（其中 contoso.com 是发件人）：
  
 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`
  
管理员可以对 DKIM 验证结果创建 Exchange [Transport Rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)，以根据需要筛选或路由邮件。 
  

