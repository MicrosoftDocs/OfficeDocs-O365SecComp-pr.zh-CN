---
title: 隔离常见问题解答
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: 本主题提供了关于托管隔离的常见问题及解答。
ms.openlocfilehash: 907bb7eaee9c7aef490c74677b4f277b89ba3115
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601269"
---
# <a name="quarantine-faq"></a>隔离常见问题解答

本主题提供了关于托管隔离的常见问题及解答。解答适用于 Microsoft Exchange Online 和 Exchange Online Protection 客户。
  
 **问: 如何在隔离中管理恶意软件隔离的邮件？**
  
您需要使用安全&amp;合规性中心, 以便查看和处理发送到隔离的邮件, 因为它们包含恶意软件。 有关详细信息, 请参阅[在 Office 365 中隔离电子邮件消息](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。
  
 **问：如何将该服务配置为将垃圾邮件隔离的邮件发送到隔离邮箱？**
  
答：默认情况下，经过内容筛选的邮件将发送到收件人的垃圾邮件文件夹。但是，管理员可以将内容筛选器策略配置为将垃圾邮件隔离邮件转为发送到隔离邮箱。有关可以对内容筛选邮件执行的不同操作的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
 **问：该服务具有对垃圾邮件隔离消息的管理员和最终用户管理吗？**
  
答：作为管理员，您可以在 Exchange 管理中心 (EAC) 中搜索和查看有关所有隔离的电子邮件的详细信息。在找到邮件后，您可以将它释放给特定用户，同时可以选择向 Microsoft 垃圾邮件分析团队将邮件报告为误报（非垃圾邮件）。有关详细信息，请参阅[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。
  
作为最终用户，您可以通过以下方式管理自己的垃圾邮件隔离邮件： 
  
- 垃圾邮件隔离用户界面。 有关详细信息，请参阅[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。
        
 **问：如何为我的最终用户授予访问垃圾邮件隔离的权限？**
  
A. 若要访问最终用户垃圾邮件隔离邮箱，最终用户必须具有有效 Office 365 用户 ID 和密码。 保护本地邮箱的 EOP 客户必须是通过目录同步或 EAC 创建的有效电子邮件用户。 有关管理用户的详细信息, EOP 管理员可以参阅[Manage mail users IN EOP](eop/manage-mail-users-in-eop.md)。 对于 EOP 独立客户，建议使用目录同步并启用基于目录的边缘阻止，有关详细信息，请参阅[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
  
 **问：除垃圾邮件以外的其他邮件可以发送到隔离邮箱吗？**
  
A. 如果已配置的操作, 则也可以将与邮件流规则 (也称为 "传输规则") 相匹配的邮件发送到管理员隔离。 最终用户隔离仅适用于垃圾邮件。
  
 **问：邮件将在隔离邮箱中保留多长时间？**
  
A. 默认情况下, 垃圾邮件隔离的邮件在隔离中保留30天, 而与邮件流规则匹配的隔离邮件将保留在隔离时间7天内。 在此时间段后, 邮件将被删除且不可检索。 与邮件流规则匹配的隔离邮件的保留期不可配置。 但是, 垃圾邮件隔离邮件的保留期可以通过内容筛选器策略中的 "**保留垃圾邮件 (天)** " 设置来降低。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
 **问：可以一次释放或报告多个被隔离的邮件吗？**
  
答：同时释放或报告多个邮件的功能目前对 EAC 或最终用户的垃圾邮件隔离不可用。但是，管理员可以创建一个远程 Windows PowerShell 脚本来完成此任务。使用 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 搜索邮件，使用 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) 释放邮件。 
  
 **问：搜索被隔离邮件时是否支持通配符？是否可以搜索特定域的隔离邮件？**
  
答：在 Exchange 管理员中心指定搜索条件时，不支持通配符。例如，在搜索某个发件人时，必须指定完整的电子邮件地址。
  
通过远程 Windows PowerShell，管理员可以指定 [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 以搜索特定域的隔离邮件（例如 contoso.com）： 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

可将结果传递给 [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet。包括 -ReleaseToAll 参数以将邮件释放给所有收件人。邮件释放后，无法再次释放该邮件。 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


