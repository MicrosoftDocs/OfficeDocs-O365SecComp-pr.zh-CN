---
title: 出站邮件的高风险传递池
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/24/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
description: 时由恶意软件或恶意垃圾邮件攻击中，已泄露客户的电子邮件系统，其发送出站垃圾邮件通过托管的筛选服务，这可能会导致在第三方块上所列出的 Office 365 数据中心服务器的 IP 地址列出。
ms.openlocfilehash: 69548488f70944a319a449bfc4ac1cb1bffd7b1c
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003131"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a>出站邮件的高风险传递池

当客户的电子邮件系统被恶意软件或恶意垃圾邮件攻击感染后，同时通过托管的筛选服务发送出站垃圾邮件时，这会导致 Office 365 数据中心服务器的 IP 地址被列入第三方阻止列表。不使用托管筛选服务，而使用这些阻止列表的目标服务器将最终退回发送自添加到这些列表的任何托管筛选 IP 地址的所有电子邮件。为防止发生这种情况，所有超出垃圾邮件阈值的出站邮件将通过高风险传送池发送。辅助出站电子邮件池仅用于发送可能的低质量邮件，从而帮助保护网络的其他部分，防止发送很可能导致发送 IP 地址被阻止的邮件。
  
使用专门的高风险传送池有助于确保正常的出站池仅发送已知高质量的邮件。使用此辅助 IP 池有助于减少正常的出站 IP 池被添加到阻止列表的可能性。将高风险传送池置于阻止列表的可能性仍然存在风险。这是由设计决定的。
  
为你提供域的 IP 地址的发送域没有地址记录（A 记录），同时没有有助于直接发送邮件到应在 DNS 的某个域接收邮件服务器的 MX 记录的邮件将始终通过高风险传送池路由，无论其垃圾邮件处置如何。
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a>了解传递状态通知 (DSN) 邮件

出站高风险传送池管理所有"出站"或"已失败"(DSN) 邮件的传送。
  
DSN 邮件激增的可能原因包括：
  
- 欺骗活动影响使用该服务的其中一位客户
    
- 帐户搜集攻击
    
- 垃圾邮件攻击
    
- 未授权的 SMTP 服务器
    
所有这些问题都会导致该服务处理的 DSN 邮件数量的激增。在很多情况下，这些 DSN 邮件对其他电子邮件服务器和服务来说是垃圾邮件。
  
## <a name="for-more-information"></a>详细信息

[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)
  

