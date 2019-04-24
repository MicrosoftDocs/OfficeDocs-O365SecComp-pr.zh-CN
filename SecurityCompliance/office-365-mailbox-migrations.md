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
# <a name="office-365-mailbox-migrations"></a><span data-ttu-id="10eb2-103">Office 365 邮箱迁移</span><span class="sxs-lookup"><span data-stu-id="10eb2-103">Office 365 Mailbox Migrations</span></span>
<span data-ttu-id="10eb2-104">通过基于 Exchange 的混合部署, 客户可以选择将本地 Exchange 邮箱移动到[exchange online](https://docs.microsoft.com/Exchange/exchange-online)组织, 或将 exchange Online 邮箱移动到[exchange 内部部署](https://docs.microsoft.com/Exchange/exchange-server)组织。</span><span class="sxs-lookup"><span data-stu-id="10eb2-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="10eb2-105">在内部部署组织和 Exchange Online 组织之间移动邮箱时使用迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="10eb2-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span> <span data-ttu-id="10eb2-106">客户可以使用以下 cmdlet 查看有关邮箱迁移的统计信息和其他信息:</span><span class="sxs-lookup"><span data-stu-id="10eb2-106">Customers can review statistics and other information about mailbox migrations using the following cmdlets:</span></span>

- <span data-ttu-id="10eb2-107">[get-moverequeststatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) -提供用户邮箱的默认统计信息, 其中包括状态、邮箱大小、存档邮箱大小和完成百分比。</span><span class="sxs-lookup"><span data-stu-id="10eb2-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequestStatistics?view=exchange-ps) - Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size and percentage complete.</span></span>
- <span data-ttu-id="10eb2-108">[Get-邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
)-提供组织中的邮箱对象和属性的摘要列表。</span><span class="sxs-lookup"><span data-stu-id="10eb2-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox?view=exchange-ps
) - Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="10eb2-109">[接收人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps)-提供现有的已启用邮件的对象 (例如邮箱、邮件用户、联系人和通讯组) 的列表。</span><span class="sxs-lookup"><span data-stu-id="10eb2-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient?view=exchange-ps) - Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts and distribution groups.</span></span>
- <span data-ttu-id="10eb2-110">[new-moverequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) -提供正在进行的邮箱迁移的详细状态。</span><span class="sxs-lookup"><span data-stu-id="10eb2-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MoveRequest?view=exchange-ps) - Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="10eb2-111">[get-migrationuser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) -提供有关邮箱移动和迁移用户的信息。</span><span class="sxs-lookup"><span data-stu-id="10eb2-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUser?view=exchange-ps) - Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="10eb2-112">[new-migrationbatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) -提供有关当前迁移批处理的状态信息。</span><span class="sxs-lookup"><span data-stu-id="10eb2-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationBatch?view=exchange-ps) - Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="10eb2-113">[get-migrationuserstatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) -提供有关特定用户的迁移状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="10eb2-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/Get-MigrationUserStatistics?view=exchange-ps) - Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="10eb2-114">[get-mailboxstatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) -提供有关邮箱的信息, 如大小、邮件数以及上次访问时间。</span><span class="sxs-lookup"><span data-stu-id="10eb2-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-MailboxStatistics?view=exchange-ps) - Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="10eb2-115">有关其他 cmdlet 的详细信息, 请参阅[Exchange Online 中的移动和迁移 cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="10eb2-115">For more information on additional cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
