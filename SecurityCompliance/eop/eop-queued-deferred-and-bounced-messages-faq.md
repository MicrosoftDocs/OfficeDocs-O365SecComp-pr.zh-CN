---
title: EOP 排队、延迟以及退回邮件的常见问题
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
description: 本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。
ms.openlocfilehash: e8fdb07d11a1f540e94b82730eb848a97f51523a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256260"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="a4476-103">EOP 排队、延迟以及退回邮件的常见问题</span><span class="sxs-lookup"><span data-stu-id="a4476-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="a4476-104">本主题回答了有关在 Microsoft Exchange Online Protection (EOP) 筛选过程中涉及已排队、延迟或退回邮件的常见问题。</span><span class="sxs-lookup"><span data-stu-id="a4476-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>
  
 <span data-ttu-id="a4476-105">**问：为什么邮件正在排队？**</span><span class="sxs-lookup"><span data-stu-id="a4476-105">**Q. Why is mail queuing?**</span></span>
  
<span data-ttu-id="a4476-p101">答：如果服务无法连接到用于传递的收件人服务器，则会出现邮件排队或延迟情况。如果从收件人网络中返回 500 系列错误，则不会延迟邮件。</span><span class="sxs-lookup"><span data-stu-id="a4476-p101">A. Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery. It will not defer messages if a 500-series error is returned from the recipient network.</span></span>
  
 <span data-ttu-id="a4476-109">**问：为什么邮件会出现延迟？**</span><span class="sxs-lookup"><span data-stu-id="a4476-109">**Q. How does a message become deferred?**</span></span>
  
<span data-ttu-id="a4476-p102">答：出现邮件被保留的情况如下：无法连接到收件人服务器以及收件人的服务器返回了"临时性错误"，如连接超时、拒绝连接或 400 系列错误。如果存在永久性故障，如 500 系列错误，则邮件将被返回到收件人。</span><span class="sxs-lookup"><span data-stu-id="a4476-p102">A. Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error. If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>
  
 <span data-ttu-id="a4476-113">**问：邮件保持延迟状态多长时间以及什么是重试间隔？**</span><span class="sxs-lookup"><span data-stu-id="a4476-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>
  
<span data-ttu-id="a4476-114">A.</span><span class="sxs-lookup"><span data-stu-id="a4476-114">A.</span></span> <span data-ttu-id="a4476-115">延期的邮件将在我们的队列中保留 2 天。</span><span class="sxs-lookup"><span data-stu-id="a4476-115">Messages in deferral will remain in our queues for 2 days.</span></span> <span data-ttu-id="a4476-116">重试发送邮件的依据为从收件人的邮件系统返回的错误。</span><span class="sxs-lookup"><span data-stu-id="a4476-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="a4476-117">前几个 deferrals 为15分钟或更短, 随后的重试次数 (在接下来的6到6或更长时间) 内, 将多次重试次数增加到最大的60分钟。</span><span class="sxs-lookup"><span data-stu-id="a4476-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="a4476-118">间隔持续时间扩展是动态的, 其中考虑了多个变量 (如队列大小和内部邮件优先级)。</span><span class="sxs-lookup"><span data-stu-id="a4476-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="a4476-119">在基本版中, 启动时间为15分钟 (或更短), 然后在接下来的几小时内扩展到60分钟的最大值。</span><span class="sxs-lookup"><span data-stu-id="a4476-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>
  
 <span data-ttu-id="a4476-120">**问：恢复电子邮件服务器后，如何分配列队中的邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4476-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>
  
<span data-ttu-id="a4476-p104">答：恢复电子邮件服务器后，所有排队的邮件将自动按照服务器中断时接收和排队顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="a4476-p104">A. After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span> 
  

