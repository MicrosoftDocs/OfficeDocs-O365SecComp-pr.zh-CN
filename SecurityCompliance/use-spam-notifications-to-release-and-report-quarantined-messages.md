---
title: 在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/14/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 如果管理员为用户启用通知, 则会收到一条通知消息, 其中列出了发送到邮箱的邮件, 并被标识为垃圾邮件、批量邮件或网络钓鱼邮件。 您可以在收到通知后释放或报告邮件。
ms.openlocfilehash: de67987b0028102bdf61889ce54ca4215182e279
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638969"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="b194f-104">在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件</span><span class="sxs-lookup"><span data-stu-id="b194f-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="b194f-105">如果您的管理员为用户启用了垃圾邮件通知, 您将收到一条通知消息, 其中列出发往您的邮箱的邮件, 而不是被标识为垃圾邮件和隔离的邮件。</span><span class="sxs-lookup"><span data-stu-id="b194f-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="b194f-106">如果你是管理员, 并且想要启用此功能, 则可以在[修改默认反垃圾邮件策略](https://go.microsoft.com/fwlink/?LinkId=800313)时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="b194f-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="b194f-107">您收到的邮件包括您拥有的垃圾邮件隔离邮件的数量, 以及列表中最后一条消息的日期和时间 (以通用协调时间或 UTC 为单位)。</span><span class="sxs-lookup"><span data-stu-id="b194f-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="b194f-108">此列表包含每个邮件的以下内容:</span><span class="sxs-lookup"><span data-stu-id="b194f-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="b194f-109">**发件人**隔离邮件的发送名称和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b194f-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="b194f-110">**主题** 隔离邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="b194f-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="b194f-111">**日期** 邮件隔离的日期和时间 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="b194f-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="b194f-112">**尺寸**邮件的大小, 以千字节 (kb) 为单位。</span><span class="sxs-lookup"><span data-stu-id="b194f-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="b194f-113">以下是您可以使用隔离邮件执行的操作:</span><span class="sxs-lookup"><span data-stu-id="b194f-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="b194f-114">如果要在执行操作之前预览内容或标题, 请**预览**邮件。</span><span class="sxs-lookup"><span data-stu-id="b194f-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="b194f-115">如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。</span><span class="sxs-lookup"><span data-stu-id="b194f-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="b194f-116">如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。</span><span class="sxs-lookup"><span data-stu-id="b194f-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="b194f-117">**发布 &** 如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 以供将来的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b194f-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="b194f-118">请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。</span><span class="sxs-lookup"><span data-stu-id="b194f-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="b194f-119">**发布 & 报告**, 如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b194f-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="b194f-120">如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。</span><span class="sxs-lookup"><span data-stu-id="b194f-120">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="b194f-121">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="b194f-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="b194f-122">由于与邮件流规则匹配而被隔离的邮件不会包括在用户隔离的邮件中。</span><span class="sxs-lookup"><span data-stu-id="b194f-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="b194f-123">只有垃圾邮件隔离邮件才会列出。</span><span class="sxs-lookup"><span data-stu-id="b194f-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="b194f-124">您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。</span><span class="sxs-lookup"><span data-stu-id="b194f-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

