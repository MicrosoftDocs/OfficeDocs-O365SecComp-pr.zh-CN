---
title: Office 365 邮箱迁移
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 用于 Office 365 邮箱迁移的 cmdlet 的简短摘要。
ms.openlocfilehash: 86896d956072b5c11e3b3292363bb32312ff1187
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525658"
---
# <a name="office-365-mailbox-migrations"></a>Office 365 邮箱迁移
基于 Exchange 混合部署，客户可以选择内部部署 Exchange 邮箱移动到[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)组织或 Exchange Online 邮箱移动到[Exchange 内部部署](https://docs.microsoft.com/Exchange/exchange-server)组织。在本地和 Exchange Online 组织之间移动邮箱时，将使用迁移批次。客户可以查看统计信息和邮箱迁移使用以下 cmdlet 的其他信息：

- [Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供默认统计信息的用户邮箱，其中包括状态、 邮箱大小，存档邮箱大小和完成百分比。
- [Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供组织中的邮箱对象和属性的摘要列表。
- [Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) -提供如邮箱、 邮件用户、 联系人和通讯组的现有已启用邮件的对象的列表。
- [Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持续的邮箱迁移的详细的状态。
- [Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -为移动和迁移的用户提供有关邮箱的信息。
- [Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供有关当前迁移批次的状态信息。
- [Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -为某个特定用户提供有关迁移状态的详细的信息。
- [Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供有关邮箱，如大小、 消息，数和上次访问的时间信息。

有关其他 cmdlet 的详细信息，请参阅[Exchange Online 中的移动和迁移 cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。
