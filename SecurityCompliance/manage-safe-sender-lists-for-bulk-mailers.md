---
title: 管理邮件群发程序的白名单
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）
ms.openlocfilehash: 27d635ec93dd04df8ebf22d5d3d8f8ead4b7bcf8
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276132"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>管理邮件群发程序的白名单

如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）
  
SMTP MAIL FROM 地址（也称为 RFC 5321.MailFrom 地址）是用来执行 SPF 检查的电子邮件地址，如果不能传递邮件，则退回的邮件会被传递到该路径。默认情况下，即使发件人可以指定不同的返回路径地址，此电子邮件地址也会放入邮件头的返回路径中。
  
"发件人："邮件头中的地址（或称为 RFC 5322.From 地址）是显示在邮件客户端（如 Outlook）中的电子邮件地址。
  
大多数情况下，5321.MailFrom 和 5322.From 地址是相同的。这是典型的个人到个人的通信。但是，当代表其他人发送电子邮件时，地址往往是不同。通常这对于批量电子邮件是经常发生的。
  
例如，假设航空公司 Blue Yonder Airlines 已经将 Margie's Travel 外包出去，从而发送电子邮件广告。然后，您会在收件箱中收到一封来自发件人 blueyonder@news.blueyonderairlines.com 的邮件。在这种情况下，5321.MailFrom 地址是 blueyonder.airlines@margiestravel.com，blueyonder@news.blueyonderairlines.com 是 5322.From 地址，您可以在 Outlook 中看到此地址。由于服务遵守 RFC 5322.From 地址，因此，为避免此邮件被筛选掉，您只需在 Outlook 中将 RFC 5322.From 地址添加为白名即可。
  

