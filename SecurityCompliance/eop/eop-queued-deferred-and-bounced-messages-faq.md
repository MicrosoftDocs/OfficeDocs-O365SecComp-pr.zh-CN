---
title: EOP 排队、延迟以及退回邮件的常见问题
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。
ms.openlocfilehash: 4b2c902adacd6e72e587aadaceecd22dd0084d85
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686422"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>EOP 排队、延迟以及退回邮件的常见问题

本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。
  
 **问：为什么邮件正在排队？**
  
答：如果服务无法连接到用于传递的收件人服务器，则会出现邮件排队或延迟情况。如果从收件人网络中返回 500 系列错误，则不会延迟邮件。
  
 **问：为什么邮件会出现延迟？**
  
答：出现邮件被保留的情况如下：无法连接到收件人服务器以及收件人的服务器返回了"临时性错误"，如连接超时、拒绝连接或 400 系列错误。如果存在永久性故障，如 500 系列错误，则邮件将被返回到收件人。
  
 **问：邮件保持延迟状态多长时间以及什么是重试间隔？**
  
A.2 天，邮件延迟将保留在我们的队列。消息重试次数基于收件人的邮件系统中将返回错误。第一个几延期是 15 分钟或小于与后续重试次数 （通过下一步半打或这样） 增加转移到最大值为 60 分钟的多次重试时间间隔。间隔的持续时间扩展为动态，考虑多个变量，如队列大小和内部邮件优先级。在 basic 中，它为 15 分钟 （或更少） 开始，然后展开从中通过下一步的几个小时到最大的 60 分钟。
  
 **问：恢复电子邮件服务器后，如何分配列队中的邮件？**
  
答：恢复电子邮件服务器后，所有排队的邮件将自动按照服务器中断时接收和排队顺序进行处理。 
  

