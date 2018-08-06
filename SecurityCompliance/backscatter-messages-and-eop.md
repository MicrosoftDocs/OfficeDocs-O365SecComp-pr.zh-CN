---
title: 退信消息和 EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
description: 退信消息是自动的弹跳发送的邮件服务器，通常是由于传入垃圾邮件。Backscatterer DNSBL 是发送退信消息的 IP 地址的列表。它不是垃圾邮件列表中，并我们不尝试删除 Backscatterer DNSBL 我们的服务器。
ms.openlocfilehash: 8f8a60715f9fb12ca53ffddc6d4fca6e9fab2ede
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028169"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="a31f6-105">退信消息和 EOP</span><span class="sxs-lookup"><span data-stu-id="a31f6-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="a31f6-p102">退信邮件是邮件服务器发送的自动退回邮件，这通常是由传入的垃圾邮件所致。Exchange Online Protection (EOP) 是一种垃圾邮件筛选服务，它会拒绝向不存在的收件人及其他可疑目标的电子邮件发送邮件。发生此种情况时，EOP 会生成未送达报告 (NDR) 消息，并将它传回"发件人"。因为垃圾邮件制造者经常在邮件中使用伪造或无效的"发件人"，NDR 发送到的发件人地址可能会导致退信消息。发生此情况时，与 EOP 网络关联的传出服务器可能会列在退信 DNS 阻止列表 (DNSBL) 中。退信 DNSBL 是发送退信消息的 IP 地址的列表。它不是垃圾邮件制造者列表，我们不会尝试从退信 DNSBL 中删除我们的服务器。</span><span class="sxs-lookup"><span data-stu-id="a31f6-p102">Backscatter messages are the automated bounce messages that are sent by mail servers, typically as a result of incoming spam. Because Exchange Online Protection (EOP) is a spam filtering service, email messages sent to nonexistent recipients and to other suspicious destinations are rejected by our service. When this happens, EOP generates a non-delivery report (NDR) message and delivers it back to the "sender." Because spammers frequently use a forged or invalid "From" address in their messages, the sender address to which the NDR is sent may result in a backscatter message. When this happens, outgoing servers that are associated with the EOP network may be listed on the Backscatterer DNS Block List (DNSBL). The Backscatterer DNSBL is a list of IP addresses that send backscatter messages. It isn't a spammer list, and we don't try to remove our servers from the Backscatterer DNSBL.</span></span> 
  
> [!TIP]
> <span data-ttu-id="a31f6-p103">根据退信网站上的说明，对所有传入邮件使用拒绝模式并非该服务的推荐配置或使用。它应改为在安全模式下使用。有关实现正确的退信配置的详细信息，请访问 [Backscatterer.org 网站](http://www.backscatterer.org/?target=usage)。</span><span class="sxs-lookup"><span data-stu-id="a31f6-p103">According to the instructions on the Backscatterer website, the use of reject mode for all incoming mail isn't a recommended configuration or use of that service. It should be used in safe mode instead. For more information about implementing the correct backscatter configuration, visit the [Backscatterer.org website](http://www.backscatterer.org/?target=usage).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="a31f6-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a31f6-116">For more information</span></span>

[<span data-ttu-id="a31f6-117">Backscatterer.org IP 列表</span><span class="sxs-lookup"><span data-stu-id="a31f6-117">The Backscatterer.org IP list</span></span>](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
<span data-ttu-id="a31f6-118">请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)中的"NDR 退信"条目</span><span class="sxs-lookup"><span data-stu-id="a31f6-118">See the "NDR backscatter" entry in [Advanced spam filtering  options](advanced-spam-filtering-asf-options.md)</span></span>
  

