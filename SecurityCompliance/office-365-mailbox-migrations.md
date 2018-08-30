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
# <a name="office-365-mailbox-migrations"></a><span data-ttu-id="966b1-103">Office 365 邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="966b1-103">Office 365 Mailbox Migrations</span></span>
<span data-ttu-id="966b1-p101">基于 Exchange 混合部署，客户可以选择内部部署 Exchange 邮箱移动到[Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)组织或 Exchange Online 邮箱移动到[Exchange 内部部署](https://docs.microsoft.com/Exchange/exchange-server)组织。在本地和 Exchange Online 组织之间移动邮箱时，将使用迁移批次。客户可以查看统计信息和邮箱迁移使用以下 cmdlet 的其他信息：</span><span class="sxs-lookup"><span data-stu-id="966b1-p101">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization. Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations. Customers can review statistics and other information about mailbox migrations using the following cmdlets:</span></span>

- <span data-ttu-id="966b1-107">[Get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供默认统计信息的用户邮箱，其中包括状态、 邮箱大小，存档邮箱大小和完成百分比。</span><span class="sxs-lookup"><span data-stu-id="966b1-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.</span></span>
- <span data-ttu-id="966b1-108">[Get-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) -提供组织中的邮箱对象和属性的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="966b1-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="966b1-109">[Get-recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) -提供如邮箱、 邮件用户、 联系人和通讯组的现有已启用邮件的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="966b1-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.</span></span>
- <span data-ttu-id="966b1-110">[Get-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供持续的邮箱迁移的详细的状态。</span><span class="sxs-lookup"><span data-stu-id="966b1-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="966b1-111">[Get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -为移动和迁移的用户提供有关邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="966b1-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="966b1-112">[Get-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供有关当前迁移批次的状态信息。</span><span class="sxs-lookup"><span data-stu-id="966b1-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="966b1-113">[Get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -为某个特定用户提供有关迁移状态的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="966b1-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="966b1-114">[Get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供有关邮箱，如大小、 消息，数和上次访问的时间信息。</span><span class="sxs-lookup"><span data-stu-id="966b1-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="966b1-115">有关其他 cmdlet 的详细信息，请参阅[Exchange Online 中的移动和迁移 cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="966b1-115">For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
