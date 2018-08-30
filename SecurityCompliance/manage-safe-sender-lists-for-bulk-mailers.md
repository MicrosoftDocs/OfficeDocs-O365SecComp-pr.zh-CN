---
title: 管理邮件群发程序的白名单
ms.author: krowley
author: kccross
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
description: 如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）
ms.openlocfilehash: 9442bb39e15b9db9a826472dd6110a8fa14130c6
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002991"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="d8807-105">管理邮件群发程序的白名单</span><span class="sxs-lookup"><span data-stu-id="d8807-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="d8807-p102">如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）</span><span class="sxs-lookup"><span data-stu-id="d8807-p102">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently. The service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list. (Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="d8807-p103">SMTP MAIL FROM 地址（也称为 RFC 5321.MailFrom 地址）是用来执行 SPF 检查的电子邮件地址，如果不能传递邮件，则退回的邮件会被传递到该路径。默认情况下，即使发件人可以指定不同的返回路径地址，此电子邮件地址也会放入邮件头的返回路径中。</span><span class="sxs-lookup"><span data-stu-id="d8807-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="d8807-111">"发件人："邮件头中的地址（或称为 RFC 5322.From 地址）是显示在邮件客户端（如 Outlook）中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="d8807-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="d8807-p104">大多数情况下，5321.MailFrom 和 5322.From 地址是相同的。这是典型的个人到个人的通信。但是，当代表其他人发送电子邮件时，地址往往是不同。通常这对于批量电子邮件是经常发生的。</span><span class="sxs-lookup"><span data-stu-id="d8807-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="d8807-p105">例如，假设航空公司 Blue Yonder Airlines 已经将 Margie's Travel 外包出去，从而发送电子邮件广告。然后，您会在收件箱中收到一封来自发件人 blueyonder@news.blueyonderairlines.com 的邮件。在这种情况下，5321.MailFrom 地址是 blueyonder.airlines@margiestravel.com，blueyonder@news.blueyonderairlines.com 是 5322.From 地址，您可以在 Outlook 中看到此地址。由于服务遵守 RFC 5322.From 地址，因此，为避免此邮件被筛选掉，您只需在 Outlook 中将 RFC 5322.From 地址添加为白名即可。</span><span class="sxs-lookup"><span data-stu-id="d8807-p105">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising. You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com. In this case, the 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one you see in Outlook. Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can simply add the RFC 5322.From address as a safe sender in Outlook.</span></span>
  

