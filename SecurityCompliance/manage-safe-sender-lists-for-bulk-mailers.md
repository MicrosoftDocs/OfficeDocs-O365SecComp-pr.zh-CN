---
title: 管理邮件群发程序的白名单
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 如果您想使用白名单，您应当了解 Exchange Online Protection (EOP) 和 Outlook 处理进程的方式是不同的。通过检查 RFC 5321.MailFrom 地址和 RFC 5322.From 地址，服务遵守白名单和安全域，而 Outlook 将 RFC 5322.From 地址添加到用户的白名单中。（注意：服务对黑名单和阻止域检查 5321.MailFrom 地址和 5322.From 地址。）
ms.openlocfilehash: f73cc3fc88318c4f625bf5579f73d92625624fd5
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598788"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a><span data-ttu-id="48c7e-105">管理邮件群发程序的安全发件人列表</span><span class="sxs-lookup"><span data-stu-id="48c7e-105">Manage safe sender lists for bulk mailers</span></span>

<span data-ttu-id="48c7e-106">如果要使用安全发件人列表, 则应知道 Exchange Online Protection (EOP) 和 Outlook 处理的处理方式不同。</span><span class="sxs-lookup"><span data-stu-id="48c7e-106">If you want to use safe sender lists, you should know that Exchange Online Protection (EOP) and Outlook handle processing differently.</span></span> <span data-ttu-id="48c7e-107">Office 365 服务通过检查 RFC 5321 和5321.Mailfrom 地址以及 RFC 5322.from (发件人地址) 来尊重安全发件人和域, 而 Outlook 将 RFC 5322.from 从地址添加到用户的安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="48c7e-107">The Office 365 service respects safe senders and domains by inspecting the RFC 5321.MailFrom address and the RFC 5322.From address, while Outlook adds the RFC 5322.From address to a user's safe sender list.</span></span> <span data-ttu-id="48c7e-108">(注意: 该服务将检查阻止的发件人和域的5321和5322.from 地址。)</span><span class="sxs-lookup"><span data-stu-id="48c7e-108">(Note: The service inspects both the 5321.MailFrom address and 5322.From address for blocked senders and domains.)</span></span>
  
<span data-ttu-id="48c7e-p103">SMTP MAIL FROM 地址（也称为 RFC 5321.MailFrom 地址）是用来执行 SPF 检查的电子邮件地址，如果不能传递邮件，则退回的邮件会被传递到该路径。默认情况下，即使发件人可以指定不同的返回路径地址，此电子邮件地址也会放入邮件头的返回路径中。</span><span class="sxs-lookup"><span data-stu-id="48c7e-p103">The SMTP MAIL FROM address, otherwise known as the RFC 5321.MailFrom address, is the email address that's used to perform SPF checks, and if the mail can't be delivered, the path to which the bounced message is delivered. It's this email address that is placed into the Return-Path in the message headers by default, though it's possible for the sender to designate a different Return-Path address.</span></span>
  
<span data-ttu-id="48c7e-111">"发件人："邮件头中的地址（或称为 RFC 5322.From 地址）是显示在邮件客户端（如 Outlook）中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="48c7e-111">The From: address in the message headers, otherwise known as the RFC 5322.From address, is the email address that is displayed in the mail client such as Outlook.</span></span>
  
<span data-ttu-id="48c7e-p104">大多数情况下，5321.MailFrom 和 5322.From 地址是相同的。这是典型的个人到个人的通信。但是，当代表其他人发送电子邮件时，地址往往是不同。通常这对于批量电子邮件是经常发生的。</span><span class="sxs-lookup"><span data-stu-id="48c7e-p104">Much of the time, the 5321.MailFrom and 5322.From addresses are the same. This is typical for person-to-person communication. However, when email is sent on behalf of someone else, the addresses are frequently different. This usually happens most often for bulk email messages.</span></span>
  
<span data-ttu-id="48c7e-116">例如，假设航空公司 Blue Yonder Airlines 已经将 Margie's Travel 外包出去，从而发送电子邮件广告。</span><span class="sxs-lookup"><span data-stu-id="48c7e-116">For example, suppose that the airline Blue Yonder Airlines has contracted out Margie's Travel to send out its email advertising.</span></span> <span data-ttu-id="48c7e-117">然后，您会在收件箱中收到一封来自发件人 blueyonder@news.blueyonderairlines.com 的邮件。</span><span class="sxs-lookup"><span data-stu-id="48c7e-117">You then get a message in your inbox from sender blueyonder@news.blueyonderairlines.com.</span></span> <span data-ttu-id="48c7e-118">在这种情况下, 5321 地址为 blueyonder.airlines@margiestravel.com, blueyonder@news.blueyonderairlines.com 是5322.from。发件人地址是在 Outlook 中看到的。</span><span class="sxs-lookup"><span data-stu-id="48c7e-118">In this case, 5321.MailFrom address is blueyonder.airlines@margiestravel.com, and blueyonder@news.blueyonderairlines.com is the 5322.From address which is the one, you see in Outlook.</span></span> <span data-ttu-id="48c7e-119">由于服务考虑到 RFC 5322.from, 以防止筛选出此邮件, 因此可以在 Outlook 中将 RFC 5322.from (作为用户) 添加到安全发件人, 或者, 如果您是管理员设置邮件流规则, 如[反垃圾邮件中所示。"保护](anti-spam-protection.md)" 部分。</span><span class="sxs-lookup"><span data-stu-id="48c7e-119">Because the service respects the RFC 5322.From address, to prevent this message from getting filtered, you can add the RFC 5322.From address as a safe sender in Outlook (as a user) or, if you're an administrator set up a mailflow rule as shown on the [Anti-spam Protection](anti-spam-protection.md) section.</span></span>
  

