---
title: 在 Office 365 中隔离电子邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/29/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: 您可以在 Office 365 中为传入电子邮件设置隔离, 在其中已被筛选为垃圾邮件、批量、网络钓鱼邮件和恶意软件的传入电子邮件可以保留下来供以后查看。
ms.openlocfilehash: 5590c9de9ff596c359910b5b1793004ae1913365
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699133"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="3d3f5-103">在 Office 365 中隔离电子邮件</span><span class="sxs-lookup"><span data-stu-id="3d3f5-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="3d3f5-104">可以在 Office 365 中为传入电子邮件设置隔离, 其中已筛选为垃圾邮件的邮件、批量邮件、网络钓鱼邮件、包含恶意软件的邮件以及与指定的邮件流规则匹配的邮件可以保留下来供以后查看。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule can be kept for later review.</span></span>
  
<span data-ttu-id="3d3f5-105">默认情况下, 筛选出的邮件将被发送到收件人的 "垃圾邮件" 文件夹, 但包含默认情况下发送到隔离的恶意软件的邮件除外。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-105">By default, filtered messages are sent to the recipients' Junk Email folder, except for mail that contains malware which is sent to quarantine by default.</span></span> <span data-ttu-id="3d3f5-106">作为管理员, 您可以设置内容筛选器策略, 以将所有筛选出的邮件发送到隔离。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-106">As an admin, you can set up content filter policies to send all filtered messages to quarantine instead.</span></span> <span data-ttu-id="3d3f5-107">您可以对内容筛选邮件执行的不同操作取决于 "[配置垃圾邮件筛选器" 策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-107">The different actions that you can take for content-filtered messages depend on the [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="3d3f5-108">用户和管理员都可以使用隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="3d3f5-109">用户只能在隔离中处理自己的已筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="3d3f5-110">管理员可以搜索和管理所有用户的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-110">Admins can search for and manage quarantined messages for all users.</span></span>

> [!NOTE]
> <span data-ttu-id="3d3f5-111">邮件流规则 (也称为 "传输规则") 隔离的网络钓鱼邮件和邮件仅在管理员隔离区中可用。</span><span class="sxs-lookup"><span data-stu-id="3d3f5-111">Phish messages and messages quarantined by mail flow rule (also known as transport rule) actions are only available in the admin quarantine.</span></span>
  
<span data-ttu-id="3d3f5-112">了解有关使用隔离邮件的详细信息:</span><span class="sxs-lookup"><span data-stu-id="3d3f5-112">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="3d3f5-113">以管理员身份管理隔离邮件</span><span class="sxs-lookup"><span data-stu-id="3d3f5-113">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)

- [<span data-ttu-id="3d3f5-114">以用户身份查找并释放隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="3d3f5-114">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- [<span data-ttu-id="3d3f5-115">使用用户垃圾邮件通知释放和报告垃圾邮件隔离邮件</span><span class="sxs-lookup"><span data-stu-id="3d3f5-115">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)

- [<span data-ttu-id="3d3f5-116">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="3d3f5-116">Quarantine FAQ</span></span>](quarantine-faq.md)
