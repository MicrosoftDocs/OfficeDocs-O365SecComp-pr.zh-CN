---
title: 在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: 如果您的管理员已启用的用户的通知，您会收到一封通知邮件，其中列出了标识为垃圾邮件、 批量或网络钓鱼邮件的消息发送到您的邮箱。您可以释放或报告之后要通知的邮件。
ms.openlocfilehash: e355a94af5ac295503a8e205b1a896afc1c54fb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525150"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="08ddd-104">在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="08ddd-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="08ddd-105">如果您的管理员已启用的用户的垃圾邮件通知，您会收到一封通知邮件，其中列出了发往您的邮箱的标识为垃圾邮件，而隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="08ddd-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="08ddd-106">如果您是管理员，并希望启用此功能，您可以选择选项时您[修改默认反垃圾邮件策略](https://go.microsoft.com/fwlink/?LinkId=800313)。</span><span class="sxs-lookup"><span data-stu-id="08ddd-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="08ddd-p102">您收到的邮件包括列表中的垃圾邮件隔离的邮件的日期和时间 （以协调世界时或 UTC） 的最后一条消息数。列表中包括以下关于每封邮件：</span><span class="sxs-lookup"><span data-stu-id="08ddd-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="08ddd-109">**发件人**隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="08ddd-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="08ddd-110">**主题** 隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="08ddd-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="08ddd-111">**日期** 邮件隔离的日期和时间 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="08ddd-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="08ddd-112">**大小**邮件，千字节 (Kb) 中的大小。</span><span class="sxs-lookup"><span data-stu-id="08ddd-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="08ddd-113">目前，有两个操作，您可以对隔离的邮件：</span><span class="sxs-lookup"><span data-stu-id="08ddd-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="08ddd-114">**释放到收件箱**选择此选项可将该邮件发送到收件箱，您可以查看。</span><span class="sxs-lookup"><span data-stu-id="08ddd-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="08ddd-p103">**报告为非垃圾邮件**选择此选项可将邮件的副本发送给 Microsoft 进行分析。垃圾邮件团队评估和分析该消息，并根据分析结果，调整反垃圾邮件筛选器规则，以允许通过消息。</span><span class="sxs-lookup"><span data-stu-id="08ddd-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="08ddd-117">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="08ddd-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="08ddd-p104">用户隔离邮件中不包含将被隔离，因为它们与邮件流规则匹配的邮件。列出了仅垃圾邮件隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="08ddd-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="08ddd-120">您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="08ddd-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

