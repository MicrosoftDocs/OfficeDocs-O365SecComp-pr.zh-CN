---
title: Office 365 邮箱迁移
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 用于 Office 365 邮箱迁移的 cmdlet 的简短摘要。
ms.openlocfilehash: f21462b1f4a1838ee617e0d429ba73f01ca2db90
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262574"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 邮箱迁移
通过基于 Exchange 的混合部署, 客户可以选择将本地 Exchange 邮箱移动到[exchange online](https://docs.microsoft.com/Exchange/exchange-online)组织, 或将 exchange Online 邮箱移动到[exchange 内部部署](https://docs.microsoft.com/Exchange/exchange-server)组织。 在内部部署组织和 Exchange Online 组织之间移动邮箱时使用迁移批处理。 客户可以使用以下 cmdlet 查看有关邮箱迁移的统计信息和其他信息:

- [get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供用户邮箱的默认统计信息, 其中包括状态、邮箱大小、存档邮箱大小和完成百分比。
- [Get-邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)-提供组织中的邮箱对象和属性的摘要列表。
- [接收人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供现有的已启用邮件的对象 (例如邮箱、邮件用户、联系人和通讯组) 的列表。
- [new-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供正在进行的邮箱迁移的详细状态。
- [get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供有关邮箱移动和迁移用户的信息。
- [new-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供有关当前迁移批处理的状态信息。
- [get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供有关特定用户的迁移状态的详细信息。
- [get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供有关邮箱的信息, 如大小、邮件数以及上次访问时间。

有关其他 cmdlet 的详细信息, 请参阅[Exchange Online 中的移动和迁移 cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。
