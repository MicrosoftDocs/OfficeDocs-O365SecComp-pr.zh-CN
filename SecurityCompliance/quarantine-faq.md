---
title: 隔离常见问题解答
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: 本主题提供了关于托管隔离的常见问题及解答。
ms.openlocfilehash: 6aebeadc5155cbdb8cbeeb73e29c8b8cb0d53767
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027079"
---
# <a name="quarantine-faq"></a><span data-ttu-id="9d4fe-103">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="9d4fe-103">Quarantine FAQ</span></span>

<span data-ttu-id="9d4fe-p101">本主题提供了关于托管隔离的常见问题及解答。解答适用于 Microsoft Exchange Online 和 Exchange Online Protection 客户。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p101">This topic provides frequently asked questions and answers about the hosted quarantine. Answers are applicable for Microsoft Exchange Online and Exchange Online Protection customers.</span></span>
  
 <span data-ttu-id="9d4fe-106">**问： 如何在隔离管理恶意软件隔离邮件？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-106">**Q. How do I manage malware-quarantined messages in quarantine?**</span></span>
  
<span data-ttu-id="9d4fe-p102">您需要使用安全&amp;合规性中心以查看并使用发送到隔离因为它们包含恶意软件的邮件。有关详细信息，请参阅[Office 365 中的隔离电子邮件](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p102">You need to use the Security &amp; Compliance Center in order to view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
 <span data-ttu-id="9d4fe-109">**问：如何将该服务配置为将垃圾邮件隔离的邮件发送到隔离邮箱？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-109">**Q. How do I configure the service to send spam-quarantined messages to the quarantine?**</span></span>
  
<span data-ttu-id="9d4fe-p103">答：默认情况下，经过内容筛选的邮件将发送到收件人的垃圾邮件文件夹。但是，管理员可以将内容筛选器策略配置为将垃圾邮件隔离邮件转为发送到隔离邮箱。有关可以对内容筛选邮件执行的不同操作的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p103">A. By default, content-filtered messages are sent to the recipients Junk Email folder. However, admins can configure content filter policies to send spam-quarantined messages to the quarantine instead. For more information about the different actions that can be performed on content-filtered messages, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="9d4fe-114">**问：该服务具有对垃圾邮件隔离消息的管理员和最终用户管理吗？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-114">**Q. Does the service have administrator and end user management of spam-quarantined messages?**</span></span>
  
<span data-ttu-id="9d4fe-p104">答：作为管理员，您可以在 Exchange 管理中心 (EAC) 中搜索和查看有关所有隔离的电子邮件的详细信息。在找到邮件后，您可以将它释放给特定用户，同时可以选择向 Microsoft 垃圾邮件分析团队将邮件报告为误报（非垃圾邮件）。有关详细信息，请参阅[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p104">A. As an administrator, you can search for and view details about all quarantined email messages in the Exchange admin center (EAC). After locating the message, you can release it to specific users and optionally report it as a false positive (not junk) to the Microsoft Spam Analysis Team. For more information, see [Find and release quarantined messages as an administrator](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>
  
<span data-ttu-id="9d4fe-119">作为最终用户，您可以通过以下方式管理自己的垃圾邮件隔离邮件：</span><span class="sxs-lookup"><span data-stu-id="9d4fe-119">As an end user, you can manage your own spam-quarantined messages via:</span></span> 
  
- <span data-ttu-id="9d4fe-p105">垃圾邮件隔离用户界面。有关详细信息，请参阅[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p105">The spam quarantine user interface. For more information, see [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).</span></span>
        
 <span data-ttu-id="9d4fe-122">**问：如何为我的最终用户授予访问垃圾邮件隔离的权限？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-122">**Q. How do I grant access to the spam quarantine for my end users?**</span></span>
  
<span data-ttu-id="9d4fe-p106">答： 以便访问最终用户垃圾邮件隔离，最终用户必须具有有效的 Office 365 用户 ID 和密码。保护内部部署邮箱的 EOP 客户必须是有效的电子邮件用户通过目录同步或 EAC 创建。有关管理用户的详细信息，EOP 管理员可以引用[在 EOP 中的管理邮件用户](eop/manage-mail-users-in-eop.md)。对于独立 EOP 客户，我们建议使用目录同步和启用 Directory Based Edge Blocking;有关详细信息，请参阅[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p106">A. In order to access the end user spam quarantine, end users must have a valid Office 365 user ID and password. EOP customers protecting on-premises mailboxes must be valid email users created via directory synchronization or the EAC. For more information about managing users, EOP admins can refer to [Manage mail users in EOP](eop/manage-mail-users-in-eop.md). For EOP standalone customers, we recommend using directory synchronization and enabling Directory Based Edge Blocking; for more information, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
 <span data-ttu-id="9d4fe-128">**问：除垃圾邮件以外的其他邮件可以发送到隔离邮箱吗？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-128">**Q. Can anything other than spam be sent to the quarantine?**</span></span>
  
<span data-ttu-id="9d4fe-p107">答：匹配传输规则的邮件也可能发送到管理员隔离邮箱（如果这是已配置的操作）。最终用户隔离邮箱仅隔离垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p107">A. Messages that match a transport rule can also be sent to the administrator quarantine, if that's the configured action. The end user quarantine is for spam only.</span></span>
  
 <span data-ttu-id="9d4fe-132">**问：邮件将在隔离邮箱中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-132">**Q. For how long are messages kept in the quarantine?**</span></span>
  
<span data-ttu-id="9d4fe-p108">答： 默认情况下，垃圾邮件隔离邮件将保存在隔离的 15 天时匹配传输规则的隔离的邮件隔离邮箱中保留 7 天。这段时间后邮件将被删除，并且不可检索。匹配传输规则的隔离邮件的保留期不可配置。但是，可以通过在内容筛选器策略的**保留期限 （天） 的垃圾邮件**设置缩短的垃圾邮件隔离邮件的保留期。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p108">A. By default, spam-quarantined messages are kept in the quarantine for 15 days, while quarantined messages that matched a transport rule are kept in the quarantine for 7 days. After this period of time the messages are deleted and are not retrievable. The retention period for quarantined messages that matched a transport rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
 <span data-ttu-id="9d4fe-139">**问：可以一次释放或报告多个被隔离的邮件吗？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-139">**Q. Can I release or report more than one quarantined message at a time?**</span></span>
  
<span data-ttu-id="9d4fe-p109">答：同时释放或报告多个邮件的功能目前对 EAC 或最终用户的垃圾邮件隔离不可用。但是，管理员可以创建一个远程 Windows PowerShell 脚本来完成此任务。使用 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 搜索邮件，使用 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 释放邮件。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p109">A. The ability to release or report multiple messages at once is not currently available in the EAC or the end user spam quarantine. However, admins can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
  
 <span data-ttu-id="9d4fe-144">**问：搜索被隔离邮件时是否支持通配符？是否可以搜索特定域的隔离邮件？**</span><span class="sxs-lookup"><span data-stu-id="9d4fe-144">**Q. Are wildcards supported when searching for quarantined messages? Can I search for quarantined messages for a specific domain?**</span></span>
  
<span data-ttu-id="9d4fe-p110">答：在 Exchange 管理员中心指定搜索条件时，不支持通配符。例如，在搜索某个发件人时，必须指定完整的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p110">A. Wildcards are not supported when specifying search criteria in the Exchange admin center. For example, when searching for a sender, you must specify the full email address.</span></span>
  
<span data-ttu-id="9d4fe-148">通过远程 Windows PowerShell，管理员可以指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 以搜索特定域的隔离邮件（例如 contoso.com）：</span><span class="sxs-lookup"><span data-stu-id="9d4fe-148">Using remote Windows PowerShell, admins can specify the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for quarantined messages for a specific domain (for example, contoso.com):</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

<span data-ttu-id="9d4fe-p111">可将结果传递给 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet。包括 -ReleaseToAll 参数以将邮件释放给所有收件人。邮件释放后，无法再次释放该邮件。</span><span class="sxs-lookup"><span data-stu-id="9d4fe-p111">The results can be passed to the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet. Include the -ReleaseToAll parameter to release the message to all recipients. Once a message is released, it can't be released again.</span></span> 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

