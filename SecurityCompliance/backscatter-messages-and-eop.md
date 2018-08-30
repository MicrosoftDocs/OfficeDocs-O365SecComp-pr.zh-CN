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
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
description: 退信消息是自动的弹跳发送的邮件服务器，通常是由于传入垃圾邮件。Backscatterer DNSBL 是发送退信消息的 IP 地址的列表。它不是垃圾邮件列表中，并我们不尝试删除 Backscatterer DNSBL 我们的服务器。
ms.openlocfilehash: 2ab5c6a3bec347446452acd3bdfd8c5d309994a9
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002676"
---
# <a name="backscatter-messages-and-eop"></a>退信消息和 EOP

退信邮件是邮件服务器发送的自动退回邮件，这通常是由传入的垃圾邮件所致。Exchange Online Protection (EOP) 是一种垃圾邮件筛选服务，它会拒绝向不存在的收件人及其他可疑目标的电子邮件发送邮件。发生此种情况时，EOP 会生成未送达报告 (NDR) 消息，并将它传回"发件人"。因为垃圾邮件制造者经常在邮件中使用伪造或无效的"发件人"，NDR 发送到的发件人地址可能会导致退信消息。发生此情况时，与 EOP 网络关联的传出服务器可能会列在退信 DNS 阻止列表 (DNSBL) 中。退信 DNSBL 是发送退信消息的 IP 地址的列表。它不是垃圾邮件制造者列表，我们不会尝试从退信 DNSBL 中删除我们的服务器。 
  
> [!TIP]
> 根据退信网站上的说明，对所有传入邮件使用拒绝模式并非该服务的推荐配置或使用。它应改为在安全模式下使用。有关实现正确的退信配置的详细信息，请访问 [Backscatterer.org 网站](http://www.backscatterer.org/?target=usage)。 
  
## <a name="for-more-information"></a>详细信息

[Backscatterer.org IP 列表](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)中的"NDR 退信"条目
  

