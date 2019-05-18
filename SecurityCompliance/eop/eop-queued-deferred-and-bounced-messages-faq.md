---
title: EOP 排队、延迟以及退回邮件的常见问题
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。
ms.openlocfilehash: 7d584d8356cfca805427c5dd41dc3dee2ee57e85
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150264"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排队、延迟以及退回邮件的常见问题

本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。
  
 **问：为什么邮件正在排队？**
  
答：如果服务无法连接到用于传递的收件人服务器，则会出现邮件排队或延迟情况。如果从收件人网络中返回 500 系列错误，则不会延迟邮件。
  
 **问：为什么邮件会出现延迟？**
  
答：出现邮件被保留的情况如下：无法连接到收件人服务器以及收件人的服务器返回了"临时性错误"，如连接超时、拒绝连接或 400 系列错误。如果存在永久性故障，如 500 系列错误，则邮件将被返回到收件人。
  
 **问：邮件保持延迟状态多长时间以及什么是重试间隔？**
  
A. 延期的邮件将在我们的队列中保留 2 天。 重试发送邮件的依据为从收件人的邮件系统返回的错误。 前几个 deferrals 为15分钟或更短, 随后的重试次数 (在接下来的6到6或更长时间) 内, 将多次重试次数增加到最大的60分钟。 间隔持续时间扩展是动态的, 其中考虑了多个变量 (如队列大小和内部邮件优先级)。 在基本版中, 启动时间为15分钟 (或更短), 然后在接下来的几小时内扩展到60分钟的最大值。
  
 **问：恢复电子邮件服务器后，如何分配列队中的邮件？**
  
答：恢复电子邮件服务器后，所有排队的邮件将自动按照服务器中断时接收和排队顺序进行处理。 
  

