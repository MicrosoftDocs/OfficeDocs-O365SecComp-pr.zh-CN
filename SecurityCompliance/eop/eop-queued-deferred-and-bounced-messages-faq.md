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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="b2cc0-103">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="b2cc0-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="b2cc0-104">本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。</span><span class="sxs-lookup"><span data-stu-id="b2cc0-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="b2cc0-105">**问：为什么邮件正在排队？**</span><span class="sxs-lookup"><span data-stu-id="b2cc0-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="b2cc0-p101">答：如果服务无法连接到用于传递的收件人服务器，则会出现邮件排队或延迟情况。如果从收件人网络中返回 500 系列错误，则不会延迟邮件。</span><span class="sxs-lookup"><span data-stu-id="b2cc0-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="b2cc0-109">**问：为什么邮件会出现延迟？**</span><span class="sxs-lookup"><span data-stu-id="b2cc0-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="b2cc0-p102">答：出现邮件被保留的情况如下：无法连接到收件人服务器以及收件人的服务器返回了"临时性错误"，如连接超时、拒绝连接或 400 系列错误。如果存在永久性故障，如 500 系列错误，则邮件将被返回到收件人。</span><span class="sxs-lookup"><span data-stu-id="b2cc0-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="b2cc0-113">**问：邮件保持延迟状态多长时间以及什么是重试间隔？**</span><span class="sxs-lookup"><span data-stu-id="b2cc0-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="b2cc0-p103">A.2 天，邮件延迟将保留在我们的队列。消息重试次数基于收件人的邮件系统中将返回错误。第一个几延期是 15 分钟或小于与后续重试次数 （通过下一步半打或这样） 增加转移到最大值为 60 分钟的多次重试时间间隔。间隔的持续时间扩展为动态，考虑多个变量，如队列大小和内部邮件优先级。在 basic 中，它为 15 分钟 （或更少） 开始，然后展开从中通过下一步的几个小时到最大的 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="b2cc0-p103">A. Messages in deferral will remain in our queues for 2 days. Message retry attempts are based on the error we get back from the recipient's mail system. The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes. The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority. In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="b2cc0-120">**问：恢复电子邮件服务器后，如何分配列队中的邮件？**</span><span class="sxs-lookup"><span data-stu-id="b2cc0-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="b2cc0-p104">答：恢复电子邮件服务器后，所有排队的邮件将自动按照服务器中断时接收和排队顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="b2cc0-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

