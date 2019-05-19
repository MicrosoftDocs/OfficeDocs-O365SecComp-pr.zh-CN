---
title: 出站邮件的高风险传递池
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: 当客户的电子邮件系统遭到恶意软件或恶意垃圾邮件攻击的威胁, 并且通过托管筛选服务发送出站垃圾邮件时, 这可能会导致第三方块上列出的 Office 365 数据中心服务器的 IP 地址列.
ms.openlocfilehash: 0581d4d0ac745f7520f73cd6b4465d72fa1dcf48
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152724"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="aaadb-103">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="aaadb-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="aaadb-p101">当客户的电子邮件系统被恶意软件或恶意垃圾邮件攻击感染后，同时通过托管的筛选服务发送出站垃圾邮件时，这会导致 Office 365 数据中心服务器的 IP 地址被列入第三方阻止列表。不使用托管筛选服务，而使用这些阻止列表的目标服务器将最终退回发送自添加到这些列表的任何托管筛选 IP 地址的所有电子邮件。为防止发生这种情况，所有超出垃圾邮件阈值的出站邮件将通过高风险传送池发送。辅助出站电子邮件池仅用于发送可能的低质量邮件，从而帮助保护网络的其他部分，防止发送很可能导致发送 IP 地址被阻止的邮件。</span><span class="sxs-lookup"><span data-stu-id="aaadb-p101">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists. Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists. To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool. This secondary outbound email pool is only used to send messages that may be of low quality. This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="aaadb-p102">使用专门的高风险传送池有助于确保正常的出站池仅发送已知高质量的邮件。使用此辅助 IP 池有助于减少正常的出站 IP 池被添加到阻止列表的可能性。将高风险传送池置于阻止列表的可能性仍然存在风险。这是由设计决定的。</span><span class="sxs-lookup"><span data-stu-id="aaadb-p102">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality. Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list. The possibility of the high-risk delivery pool being placed on a blocked list remains a risk. This is by design.</span></span>
  
<span data-ttu-id="aaadb-113">为你提供域的 IP 地址的发送域没有地址记录（A 记录），同时没有有助于直接发送邮件到应在 DNS 的某个域接收邮件服务器的 MX 记录的邮件将始终通过高风险传送池路由，无论其垃圾邮件处置如何。</span><span class="sxs-lookup"><span data-stu-id="aaadb-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="aaadb-114">了解传递状态通知 (DSN) 邮件</span><span class="sxs-lookup"><span data-stu-id="aaadb-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="aaadb-115">出站高风险传送池管理所有"出站"或"已失败"(DSN) 邮件的传送。</span><span class="sxs-lookup"><span data-stu-id="aaadb-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="aaadb-116">DSN 邮件激增的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="aaadb-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="aaadb-117">欺骗活动影响使用该服务的其中一位客户</span><span class="sxs-lookup"><span data-stu-id="aaadb-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="aaadb-118">帐户搜集攻击</span><span class="sxs-lookup"><span data-stu-id="aaadb-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="aaadb-119">垃圾邮件攻击</span><span class="sxs-lookup"><span data-stu-id="aaadb-119">A spam attack</span></span>
    
- <span data-ttu-id="aaadb-120">未授权的 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="aaadb-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="aaadb-p103">所有这些问题都会导致该服务处理的 DSN 邮件数量的激增。在很多情况下，这些 DSN 邮件对其他电子邮件服务器和服务来说是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="aaadb-p103">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service. Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="aaadb-123">详细信息</span><span class="sxs-lookup"><span data-stu-id="aaadb-123">For more information</span></span>

[<span data-ttu-id="aaadb-124">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="aaadb-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="aaadb-125">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="aaadb-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

