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
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
description: 本主题提供了关于托管隔离的常见问题及解答。
ms.openlocfilehash: 1473e682faab0471f5a6356e8d54a65a9baf291a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792493"
---
# <a name="quarantine-faq"></a>隔离常见问题解答

本主题提供了关于托管隔离的常见问题及解答。解答适用于 Microsoft Exchange Online 和 Exchange Online Protection 客户。
  
 **问： 如何在隔离管理恶意软件隔离邮件？**
  
您需要使用安全&amp;合规性中心以查看并使用发送到隔离因为它们包含恶意软件的邮件。有关详细信息，请参阅[Office 365 中的隔离电子邮件](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。
  
 **问：如何将该服务配置为将垃圾邮件隔离的邮件发送到隔离邮箱？**
  
答：默认情况下，经过内容筛选的邮件将发送到收件人的垃圾邮件文件夹。但是，管理员可以将内容筛选器策略配置为将垃圾邮件隔离邮件转为发送到隔离邮箱。有关可以对内容筛选邮件执行的不同操作的详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
 **问：该服务具有对垃圾邮件隔离消息的管理员和最终用户管理吗？**
  
答：作为管理员，您可以在 Exchange 管理中心 (EAC) 中搜索和查看有关所有隔离的电子邮件的详细信息。在找到邮件后，您可以将它释放给特定用户，同时可以选择向 Microsoft 垃圾邮件分析团队将邮件报告为误报（非垃圾邮件）。有关详细信息，请参阅[以管理员身份查找并释放隔离邮件](find-and-release-quarantined-messages-as-an-administrator.md)。
  
作为最终用户，您可以通过以下方式管理自己的垃圾邮件隔离邮件： 
  
- 垃圾邮件隔离用户界面。有关详细信息，请参阅[Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。
        
 **问：如何为我的最终用户授予访问垃圾邮件隔离的权限？**
  
答： 以便访问最终用户垃圾邮件隔离，最终用户必须具有有效的 Office 365 用户 ID 和密码。保护内部部署邮箱的 EOP 客户必须是有效的电子邮件用户通过目录同步或 EAC 创建。有关管理用户的详细信息，EOP 管理员可以引用[在 EOP 中的管理邮件用户](eop/manage-mail-users-in-eop.md)。对于独立 EOP 客户，我们建议使用目录同步和启用 Directory Based Edge Blocking;有关详细信息，请参阅[使用 Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。
  
 **问：除垃圾邮件以外的其他邮件可以发送到隔离邮箱吗？**
  
答：匹配传输规则的邮件也可能发送到管理员隔离邮箱（如果这是已配置的操作）。最终用户隔离邮箱仅隔离垃圾邮件。
  
 **问：邮件将在隔离邮箱中保留多长时间？**
  
答： 默认情况下，垃圾邮件隔离邮件将保存在隔离 30 天时匹配传输规则的隔离的邮件隔离邮箱中保留 7 天。这段时间后邮件将被删除，并且不可检索。匹配传输规则的隔离邮件的保留期不可配置。但是，可以通过在内容筛选器策略的**保留期限 （天） 的垃圾邮件**设置缩短的垃圾邮件隔离邮件的保留期。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。
  
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


