---
title: 退信消息和 EOP
ms.author: tracyp
author: MSFTTracyP
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
ms.collection:
- M365-security-compliance
description: 退信邮件是邮件服务器发送的自动弹跳邮件, 通常是由于传入的垃圾邮件造成的。退信 DNSBL 是发送退信邮件的 IP 地址的列表。它不是垃圾邮件制造者列表, 我们不会尝试从退信 DNSBL 中删除我们的服务器。
ms.openlocfilehash: 73f8631c50bcfb8a023b2b6007b7ccf48038e16e
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275292"
---
# <a name="backscatter-messages-and-eop"></a>退信消息和 EOP

退信邮件是邮件服务器发送的自动退回邮件，这通常是由传入的垃圾邮件所致。Exchange Online Protection (EOP) 是一种垃圾邮件筛选服务，它会拒绝向不存在的收件人及其他可疑目标的电子邮件发送邮件。发生此种情况时，EOP 会生成未送达报告 (NDR) 消息，并将它传回"发件人"。因为垃圾邮件制造者经常在邮件中使用伪造或无效的"发件人"，NDR 发送到的发件人地址可能会导致退信消息。发生此情况时，与 EOP 网络关联的传出服务器可能会列在退信 DNS 阻止列表 (DNSBL) 中。退信 DNSBL 是发送退信消息的 IP 地址的列表。它不是垃圾邮件制造者列表，我们不会尝试从退信 DNSBL 中删除我们的服务器。 
  
> [!TIP]
> 根据退信网站上的说明，对所有传入邮件使用拒绝模式并非该服务的推荐配置或使用。它应改为在安全模式下使用。有关实现正确的退信配置的详细信息，请访问 [Backscatterer.org 网站](http://www.backscatterer.org/?target=usage)。 
  
## <a name="for-more-information"></a>详细信息

[Backscatterer.org IP 列表](https://blogs.msdn.com/b/tzink/archive/2012/08/22/the-backscatterer-org-ip-list.aspx)
  
请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)中的 "NDR 退信" 条目
  

