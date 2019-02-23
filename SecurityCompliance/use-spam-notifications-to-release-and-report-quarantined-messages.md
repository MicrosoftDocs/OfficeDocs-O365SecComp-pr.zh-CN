---
title: 在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: 如果管理员为用户启用通知, 则会收到一条通知消息, 其中列出了发送到邮箱的邮件, 并被标识为垃圾邮件、批量邮件或网络钓鱼邮件。您可以在收到通知后释放或报告邮件。
ms.openlocfilehash: eb51d8f73ff00781b74cfba4e580668710ce7a76
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216392"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="6daf9-104">在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="6daf9-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="6daf9-105">如果您的管理员为用户启用了垃圾邮件通知, 您将收到一条通知消息, 其中列出发往您的邮箱的邮件, 而不是被标识为垃圾邮件和隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="6daf9-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="6daf9-106">如果你是管理员, 并且想要启用此功能, 则可以在[修改默认反垃圾邮件策略](https://go.microsoft.com/fwlink/?LinkId=800313)时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6daf9-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="6daf9-p102">您收到的邮件包括您拥有的垃圾邮件隔离邮件的数量, 以及列表中最后一条消息的日期和时间 (以通用协调时间或 UTC 为单位)。此列表包含每个邮件的以下内容:</span><span class="sxs-lookup"><span data-stu-id="6daf9-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="6daf9-109">**发件人**隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6daf9-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="6daf9-110">**主题** 隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="6daf9-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="6daf9-111">**日期** 邮件隔离的日期和时间 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="6daf9-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="6daf9-112">**尺寸**邮件的大小, 以千字节 (kb) 为单位。</span><span class="sxs-lookup"><span data-stu-id="6daf9-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="6daf9-113">目前, 您可以对隔离邮件执行以下两个操作:</span><span class="sxs-lookup"><span data-stu-id="6daf9-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="6daf9-114">**释放到收件箱**选择此 "" 将邮件发送到您的收件箱, 您可以在其中查看邮件。</span><span class="sxs-lookup"><span data-stu-id="6daf9-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="6daf9-p103">**报告为非垃圾邮件**选择此 "" 以将邮件副本发送给 Microsoft 进行分析。垃圾邮件团队对邮件进行评估和分析, 并根据分析结果调整反垃圾邮件筛选器规则, 以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="6daf9-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="6daf9-117">请注意以下事项:</span><span class="sxs-lookup"><span data-stu-id="6daf9-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="6daf9-p104">由于与邮件流规则匹配而被隔离的邮件不会包括在用户隔离的邮件中。仅列出垃圾邮件隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="6daf9-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="6daf9-120">您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="6daf9-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

