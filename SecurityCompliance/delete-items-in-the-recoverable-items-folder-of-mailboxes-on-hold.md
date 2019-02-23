---
title: 删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '对于管理员: 删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目, 即使该邮箱位于 "合法保留" 中也是如此。这是一种删除意外溅入 Office 365 中的数据的有效方法。'
ms.openlocfilehash: f3518dc1009b4e95472473f76e6cd41011bc6b3e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216952"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="836ae-104">删除保留的基于云的邮箱的 "可恢复的项目" 文件夹中的项目-管理员帮助</span><span class="sxs-lookup"><span data-stu-id="836ae-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="836ae-p102">Exchange Online 邮箱的 "可恢复的项目" 文件夹存在, 以防止意外或恶意删除。它还用于存储由 Office 365 合规性功能 (如保留和电子数据展示搜索) 保留和访问的项目。但是, 在某些情况下, 组织可能会在必须删除的 "可恢复的项目" 文件夹中包含意外保留的数据。例如, 用户可能在不知情的情况下发送或转发包含敏感信息的电子邮件或可能有严重业务后果的信息。即使邮件永久删除, 它仍可能会无限期保留, 因为邮箱中已设置了合法保留。此方案称为数据外泄, 因为数据被意外地溅入 Office 365 中。在这些情况下, 您可以删除 Exchange Online 邮箱的用户的 "可恢复的项目" 文件夹中的项目, 即使该邮箱是使用 Office 365 中的一种不同的保留功能来保留的。这些保留类型包括诉讼保留、就地保留、电子数据展示保留和在 office 365 安全&amp;合规中心中创建的 office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="836ae-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="836ae-p103">本文介绍如何从处于保留状态的基于云的邮箱的 "可恢复的项目" 文件夹中删除项目。此过程涉及到禁用对邮箱的访问和禁用单个项目恢复, 禁用托管文件夹助理处理邮箱, 暂时删除保留, 从 "可恢复的项目" 文件夹中删除项目, 然后还原邮箱设置为其以前的配置。过程如下:</span><span class="sxs-lookup"><span data-stu-id="836ae-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="836ae-116">步骤 1: 收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="836ae-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="836ae-117">步骤 2: 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="836ae-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="836ae-118">步骤 3: 从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="836ae-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="836ae-119">步骤 4: 从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="836ae-119">Step 4: Remove the delay hold from the mailbox</span></span>](#step-4-remove-the-delay-hold-from-the-mailbox)

[<span data-ttu-id="836ae-120">步骤 5: 删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="836ae-120">Step 5: Delete items in the Recoverable Items folder</span></span>](#step-5-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="836ae-121">步骤 6: 将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="836ae-121">Step 6: Revert the mailbox to its previous state</span></span>](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="836ae-p104">本文中所述的过程将导致从 Exchange Online 邮箱永久删除 (清除) 的数据。这意味着无法恢复从 "可恢复的项目" 文件夹中删除的邮件, 也不会提供用于法律查询或其他合规性的邮件。如果要从作为诉讼保留的一部分的邮箱中删除邮件, 请在 "office 365 安全&amp;合规中心" 中创建的 "就地保留"、"电子数据展示保留" 或 "office 365 保留策略" 中进行检查, 以确保您的记录管理或法律部门, 然后再删除保留。您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。</span><span class="sxs-lookup"><span data-stu-id="836ae-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="836ae-126">准备工作</span><span class="sxs-lookup"><span data-stu-id="836ae-126">Before you begin</span></span>

- <span data-ttu-id="836ae-127">您必须在 Exchange Online 中为以下两个管理角色分配搜索和删除步骤5中的 "可恢复的项目" 文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="836ae-127">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 5.</span></span>
    
  - <span data-ttu-id="836ae-p105">**邮箱搜索**-此角色允许您在组织中搜索邮箱。默认情况下, 不会为 Exchange 管理员分配此角色。若要为自己分配此角色, 请将自己添加为 Exchange Online 中的 "发现管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="836ae-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="836ae-p106">**邮箱导入导出**-此角色允许您删除用户邮箱中的邮件。默认情况下, 此角色不会分配给任何角色组。若要从用户的邮箱中删除邮件, 您可以将邮箱导入导出角色添加到 Exchange Online 中的 "组织管理" 角色组。</span><span class="sxs-lookup"><span data-stu-id="836ae-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="836ae-p107">非活动邮箱不支持本文中介绍的过程。这是因为在删除保留项 (或 Office 365 保留策略) 后, 不能将其重新应用到非活动邮箱。从非活动邮箱删除保留时, 它会更改为标准软删除邮箱, 并且在托管文件夹助理处理后, 将从组织中永久删除。</span><span class="sxs-lookup"><span data-stu-id="836ae-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="836ae-p108">您无法对已被分配到 Office 365 保留策略的邮箱执行此过程, 该保留策略已通过保留锁定进行锁定。这是因为保留锁可防止您从 Office 365 保留策略中删除或排除邮箱, 也无法在邮箱上禁用托管文件夹助理。有关锁定保留策略的详细信息, 请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="836ae-p109">如果未将邮箱置于保留状态 (或未启用单个项目恢复), 则只需从 "可恢复的项目" 文件夹中删除这些项目即可。有关如何执行此操作的详细信息, 请参阅[搜索和删除邮件](https://go.microsoft.com/fwlink/?linkid=852453)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="836ae-142">步骤 1: 收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="836ae-142">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="836ae-p110">第一步是收集将影响此过程的目标邮箱中的所选属性。请务必记下这些设置或将其保存到一个文本文件中, 因为在从 "可恢复的项目" 文件夹中删除项目后, 您将更改其中一些属性, 然后再还原为第6步中的原始值。下面列出了需要收集的邮箱属性。</span><span class="sxs-lookup"><span data-stu-id="836ae-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 6, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="836ae-146">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要, 您将禁用单个恢复并在步骤3中增加已删除项目的保留期。</span><span class="sxs-lookup"><span data-stu-id="836ae-146">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="836ae-p111">*LitigationHoldEnabled*和*InPlaceHolds* ;您需要确定邮箱上放置的所有保留, 以便可以在步骤3中临时删除它们。请参阅[详细信息](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)部分, 了解有关如何识别邮箱上可能放置的类型保留的提示。</span><span class="sxs-lookup"><span data-stu-id="836ae-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="836ae-p112">此外, 您还需要获取邮箱客户端访问设置, 以便您可以暂时禁用它们, 以便所有者 (或其他用户) 在此过程中无法访问邮箱。最后, 您可以获取 "可恢复的项目" 文件夹中的当前大小和项目数。在第5步中删除 "可恢复的项目" 文件夹中的项目后, 将使用此信息验证是否实际删除了这些项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 5, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="836ae-p113">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。请务必对已在 Exchange Online 中为其分配了适当管理角色的管理员帐户使用用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="836ae-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="836ae-154">运行以下命令以获取有关单个项目恢复和已删除项目保留期限的信息。</span><span class="sxs-lookup"><span data-stu-id="836ae-154">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="836ae-p114">如果启用了单个项目恢复, 则必须在第2步中禁用它。如果已删除项目的保留期未设置为30天 (Exchange Online 中的最大值), 则可以在第2步中增加它。</span><span class="sxs-lookup"><span data-stu-id="836ae-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="836ae-157">运行以下命令以获取邮箱的邮箱访问设置。</span><span class="sxs-lookup"><span data-stu-id="836ae-157">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="836ae-158">您将在步骤2中禁用所有这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="836ae-158">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="836ae-159">运行以下命令以获取有关保留和适用于邮箱的 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="836ae-159">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="836ae-160">如果*InPlaceHolds*属性中的值过多, 并且不是全部显示, 则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="836ae-160">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="836ae-161">运行以下命令以获取有关组织范围内的 Office 365 保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="836ae-161">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="836ae-162">如果您的组织具有任何组织范围的 Office 365 保留策略, 则必须在步骤3中将邮箱排除在这些策略之外。</span><span class="sxs-lookup"><span data-stu-id="836ae-162">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="836ae-163">如果*InPlaceHolds*属性中的值过多, 并且不是全部显示, 则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令以在单独的行中显示每个值。</span><span class="sxs-lookup"><span data-stu-id="836ae-163">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="836ae-164">运行以下命令, 获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="836ae-164">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="836ae-165">如果已启用用户的存档邮箱, 请运行以下命令, 以获取存档邮箱中 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="836ae-165">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="836ae-p115">删除步骤5中的项目时, 可以选择删除或不删除用户的主存档邮箱中的 "可恢复的项目" 文件夹中的项目。请注意, 如果为邮箱启用了自动扩展存档, 则不会删除辅助存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-p115">When you delete items in Step 5, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="836ae-168">步骤 2: 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="836ae-168">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="836ae-169">收集并保存有关邮箱的信息后, 下一步是通过执行以下任务来准备邮箱:</span><span class="sxs-lookup"><span data-stu-id="836ae-169">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="836ae-170">**禁用对邮箱的客户端访问**, 以便邮箱所有者无法访问其邮箱, 并在此过程中对邮箱数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="836ae-170">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="836ae-171">将**已删除项目的保留期增加**到30天 (Exchange Online 中的最大值), 以便从 "可恢复的项目" 文件夹中清除这些项目, 然后才能在步骤5中将其删除。</span><span class="sxs-lookup"><span data-stu-id="836ae-171">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 5.</span></span> 
    
- <span data-ttu-id="836ae-172">**禁用单个项目恢复**, 以便在从第5步中的 "可恢复的项目" 文件夹中删除项目后, 将不会保留项目 (在已删除项目的保留期内)。</span><span class="sxs-lookup"><span data-stu-id="836ae-172">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 5.</span></span> 
    
- <span data-ttu-id="836ae-173">**禁用托管文件夹助理**, 使其不处理邮箱, 并保留您在步骤5中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-173">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 5.</span></span> 
    
<span data-ttu-id="836ae-174">在 Exchange Online PowerShell 中执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="836ae-174">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="836ae-p116">运行以下命令以禁用对邮箱的所有客户端访问。命令语法假定已在邮箱上启用所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="836ae-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="836ae-p117">最长可能需要60分钟才能禁用邮箱的所有客户端访问方法。请注意, 禁用这些访问方法不会断开他们当前登录的邮箱所有者。如果未登录到所有者, 则在禁用这些访问方法后, 他们将无法访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="836ae-p118">运行以下命令, 将已删除项目的保留期增加到最大30天。这假定当前设置少于30天。</span><span class="sxs-lookup"><span data-stu-id="836ae-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="836ae-182">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="836ae-182">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="836ae-p119">可能需要长达60分钟才能禁用单个项目恢复。在此期间之前, 请勿删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="836ae-p120">运行以下命令以阻止托管文件夹助理处理邮箱。正如前面所述, 仅当具有保留锁定的 Office 365 保留策略未应用于邮箱时, 才可以禁用托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="836ae-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="836ae-187">步骤 3: 从邮箱中删除所有保留</span><span class="sxs-lookup"><span data-stu-id="836ae-187">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="836ae-p121">从 "可恢复的项目" 文件夹中删除项目之前的最后一步是删除邮箱上的所有保留 (在第1步中标识)。必须删除所有保留, 以便在从 "可恢复的项目" 文件夹中删除项目后, 不会保留这些项目。以下各节包含有关删除邮箱的不同类型的保留的信息。请参阅[详细信息](#more-information)部分, 了解有关如何识别邮箱上可能放置的类型保留的提示。有关详细信息, 请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox. For additional information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="836ae-193">如前所述, 在从邮箱中删除保留之前, 请与您的记录管理或法律部门核实。</span><span class="sxs-lookup"><span data-stu-id="836ae-193">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="836ae-194">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="836ae-194">Litigation Hold</span></span>
  
<span data-ttu-id="836ae-195">在 Exchange Online PowerShell 中运行以下命令, 以从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="836ae-195">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="836ae-p122">类似于禁用客户端访问方法和单个项目恢复, 可能需要长达60分钟的时间才能删除诉讼保留。在此时间段过后, 请勿从 "可恢复的项目" 文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="836ae-198">就地保留</span><span class="sxs-lookup"><span data-stu-id="836ae-198">In-Place Hold</span></span>
  
<span data-ttu-id="836ae-p123">在 Exchange Online PowerShell 中运行以下命令, 以标识邮箱中放置的就地保留。对您在步骤1中标识的就地保留使用 GUID。</span><span class="sxs-lookup"><span data-stu-id="836ae-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="836ae-p124">在确定就地保留之后, 可以使用 exchange 管理中心 (EAC) 或 exchange Online PowerShell 将邮箱从保留中删除。有关详细信息, 请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="836ae-203">应用于特定邮箱的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="836ae-203">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="836ae-p125">在[office 365 安全&amp;合规中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令, 以确定应用于邮箱的 Office 365 保留策略。对您在步骤1中标识`mbx`的`skp`保留策略使用 GUID (不包括或前缀)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="836ae-206">在确定保留策略后, 请转到&amp;安全合规中心中的 "**日期调控** \> "**保留**页, 编辑在上一步中标识的保留策略, 并从列表中删除该邮箱。保留策略中包含的收件人。</span><span class="sxs-lookup"><span data-stu-id="836ae-206">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="836ae-207">组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="836ae-207">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="836ae-p126">组织范围和 Exchange 范围的 Office 365 保留策略应用于组织中的每个邮箱。它们在组织级别 (而不是邮箱级别) 应用, 并在您在步骤1中运行**set-organizationconfig** cmdlet 时返回。在[安全&amp;合规中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令, 以确定组织范围内的 Office 365 保留策略。对您在步骤1中确定`mbx`的组织范围的保留策略使用 GUID (不包括前缀)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="836ae-p127">在确定组织范围内的 Office 365 保留策略后, 请转到&amp;安全合规中心中的 "**日期调控** \> "**保留**页, 编辑您在中标识的每个组织范围内的保留策略。上一步, 并将邮箱添加到排除的收件人列表中。执行此操作会将用户的邮箱从保留策略中删除。</span><span class="sxs-lookup"><span data-stu-id="836ae-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 

### <a name="office-365-retention-labels"></a><span data-ttu-id="836ae-214">Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="836ae-214">Office 365 retention labels</span></span>

<span data-ttu-id="836ae-p128">每当用户应用配置为保留内容或保留内容, 然后将内容删除到其邮箱中的任何文件夹或项目的标签时, *ComplianceTagHoldApplied*邮箱属性将设置为**True**。如果发生这种情况, 则认为邮箱处于保留状态, 就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。</span><span class="sxs-lookup"><span data-stu-id="836ae-p128">Whenever a user applies a label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy.</span></span>

<span data-ttu-id="836ae-217">若要查看*ComplianceTagHoldApplied*属性的值, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="836ae-217">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="836ae-p129">确定邮箱处于保留状态, 因为保留标签应用于文件夹或项目, 您可以使用 Security & 合规性中心中的内容搜索工具来搜索带标签的项目, 方法是使用 new-compliancetag 搜索条件。有关详细信息, 请参阅关键字查询中的 "搜索条件" 部分[和内容搜索的搜索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p129">After you've identified that a mailbox is on hold because a retention label is applied to a folder or item, you can use the Content Search tool in the Security & Compliance Center to search for labeled items by using the ComplianceTag search condition. For more information, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#conditions-for-common-properties).</span></span>

<span data-ttu-id="836ae-220">有关标签的详细信息, 请参阅[Office 365 概述标签](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="836ae-220">For more information about labels, see [Overview of Office 365 labels](labels.md).</span></span>

 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="836ae-221">电子数据展示事例保留</span><span class="sxs-lookup"><span data-stu-id="836ae-221">eDiscovery case holds</span></span>
  
<span data-ttu-id="836ae-p130">在[安全&amp;合规中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)中运行以下命令, 以确定与应用于邮箱的电子数据展示事例关联的保留。使用您在步骤1中确定`UniH`的电子数据展示保留的 GUID (不包括前缀)。请注意, 第二个命令显示与保留相关联的电子数据展示事例的名称;第三个命令显示保留的名称。</span><span class="sxs-lookup"><span data-stu-id="836ae-p130">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="836ae-p131">确定电子数据展示事例的名称和保留后, 请转到安全&amp;合规性中心中的 "**搜索&amp;调查** \*\*\*\* \>电子数据展示" 页, 打开事例, 并从保留中删除邮箱。有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中管理电子数据展示事例](manage-ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p131">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a><span data-ttu-id="836ae-227">步骤 4: 从邮箱中删除延迟保留</span><span class="sxs-lookup"><span data-stu-id="836ae-227">Step 4: Remove the delay hold from the mailbox</span></span>

<span data-ttu-id="836ae-p132">从邮箱中删除了任何类型的保留后, *DelayHoldApplied*邮箱属性的值将设置为**True**。在下次托管文件夹助理处理邮箱并检测已删除保留时, 会发生这种情况。这称为*延迟保留*, 意味着实际删除保留的延迟时间为30天, 以防止永久删除邮箱中的数据。(延迟保留的目的是使管理员有机会搜索或恢复在删除保留后将清除的邮箱项目。) 将延迟保留放在邮箱上时, 该邮箱仍被视为无限持续时间处于保留状态, 就像该邮箱处于诉讼保留状态一样。30天后, 延迟保留过期, Office 365 将自动尝试删除延迟保留 (通过将*DelayHoldApplied*属性设置为**False**), 以便实际删除保留。</span><span class="sxs-lookup"><span data-stu-id="836ae-p132">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted from the mailbox. (The purpose of a delay hold is to give admins an opportunity to search for or recover mailbox items that will be purged after a hold is removed.)  When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold is actually removed.</span></span> 

<span data-ttu-id="836ae-p133">在您可以删除步骤5中的项目之前, 必须从邮箱中删除延迟保留。首先, 通过在 Exchange Online PowerShell 中运行以下命令来确定是否对邮箱应用延迟保留:</span><span class="sxs-lookup"><span data-stu-id="836ae-p133">Before you can delete items in Step 5, you have to remove the delay hold from the mailbox. First, determine if the delay hold is applied to the mailbox by running the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="836ae-p134">如果将*DelayHoldApplied*属性的值设置为**False**, 则不会在邮箱上放置延迟保留。您可以转到步骤5并删除 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-p134">If the value of the *DelayHoldApplied* property is set to **False**, a delay hold has not been placed on the mailbox. You can go to Step 5 and delete items in the Recoverable Items folder.</span></span>

<span data-ttu-id="836ae-237">如果*DelayHoldApplied*属性的值设置为**True**, 请运行以下命令删除延迟保留:</span><span class="sxs-lookup"><span data-stu-id="836ae-237">If the value of the *DelayHoldApplied* property is set to **True**, run the following command to remove the delay hold:</span></span>

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="836ae-238">请注意, 您必须在 Exchange Online 中向您分配 "合法保留" 角色, 才能使用*RemoveDelayHoldApplied*参数。</span><span class="sxs-lookup"><span data-stu-id="836ae-238">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter.</span></span>

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="836ae-239">步骤 5: 删除 "可恢复的项目" 文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="836ae-239">Step 5: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="836ae-p135">现在, 您可以使用 Exchange Online PowerShell 中的[搜索-邮箱](https://go.microsoft.com/fwlink/?linkid=852595)cmdlet 实际删除 "可恢复的项目" 文件夹中的项目。运行**搜索邮箱**cmdlet 时有三个选项。</span><span class="sxs-lookup"><span data-stu-id="836ae-p135">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="836ae-242">先将项目复制到目标邮箱, 然后再将其删除, 以便在删除之前可以查看这些项目 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="836ae-242">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="836ae-243">将项目复制到目标邮箱, 并在同一命令中将其删除。</span><span class="sxs-lookup"><span data-stu-id="836ae-243">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="836ae-244">删除项目, 而不将其复制到目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-244">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="836ae-p136">请注意, 当您运行**搜索邮箱**cmdlet 时, 用户的主存档邮箱中的 "可恢复的项目" 文件夹中的项目也会随之删除。若要防止出现这种情况, 可以包含*DoNotIncludeArchive*开关。如前所述, 如果为邮箱启用了自动扩展存档, 则 \* \* 搜索-邮箱 \* \* cmdlet 不会删除辅助存档邮箱中的项目。有关自动扩展存档的详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p136">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the **Search-Mailbox** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the \*\* Search-Mailbox \*\* cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="836ae-p137">如果添加一个搜索查询（通过使用  *SearchQuery*  参数）， **Search-Mailbox** cmdlet 最多返回搜索结果中的 10,000 个项目。因此，如果添加一个搜索查询，则可能需要多次运行 **Search-Mailbox** 命令才能将 10,000 多个项目删除。</span><span class="sxs-lookup"><span data-stu-id="836ae-p137">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="836ae-p138">下面的示例显示了每个选项的命令语法。这些示例使用`-SearchQuery size>0`参数值, 这将从 "可恢复的项目" 文件夹中删除所有子文件夹中的所有项目。如果需要仅删除符合特定条件的项目, 则还可以使用*SearchQuery*参数指定其他条件, 如邮件主题或日期范围。请参阅下面的[使用 SearchQuery 参数的其他示例](#other-examples-of-using-the-searchquery-parameter)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p138">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="836ae-255">示例 1</span><span class="sxs-lookup"><span data-stu-id="836ae-255">Example 1</span></span>

<span data-ttu-id="836ae-p139">本示例将用户的 "可恢复的项目" 文件夹中的所有项目复制到组织的发现搜索邮箱中的一个文件夹中。这样, 你就可以在永久删除项目之前查看它们。</span><span class="sxs-lookup"><span data-stu-id="836ae-p139">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="836ae-p140">在上面的示例中, 不需要将项目复制到发现搜索邮箱。您可以将邮件复制到任何目标邮箱。但是, 为了防止对潜在敏感邮箱数据的访问, 我们建议将邮件复制到对已授权的人员有限制的邮箱中。默认情况下, 对默认发现搜索邮箱的访问权限限制为 Exchange Online 中发现管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="836ae-p140">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="836ae-262">示例 2</span><span class="sxs-lookup"><span data-stu-id="836ae-262">Example 2</span></span>

<span data-ttu-id="836ae-263">本示例将用户的 "可恢复的项目" 文件夹中的所有项目复制到组织的发现搜索邮箱中的一个文件夹中, 然后从用户的 "可恢复的项目" 文件夹中删除这些项目。</span><span class="sxs-lookup"><span data-stu-id="836ae-263">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="836ae-264">示例 3</span><span class="sxs-lookup"><span data-stu-id="836ae-264">Example 3</span></span>

<span data-ttu-id="836ae-265">本示例删除用户的 "可恢复的项目" 文件夹中的所有项目, 而不将其复制到目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-265">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="836ae-266">使用 SearchQuery 参数的其他示例</span><span class="sxs-lookup"><span data-stu-id="836ae-266">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="836ae-p141">以下是使用*SearchQuery*参数查找特定邮件的几个示例。如果使用*SearchQuery*参数搜索特定项目, 请考虑将搜索结果复制到目标邮箱, 以便可以查看搜索结果, 然后在删除搜索结果之前修改查询 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p141">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="836ae-269">本示例返回在 "Subject" 字段中包含特定短语的邮件。</span><span class="sxs-lookup"><span data-stu-id="836ae-269">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="836ae-270">本示例返回在指定日期范围内发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="836ae-270">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="836ae-271">本示例返回发送给指定人员的邮件。</span><span class="sxs-lookup"><span data-stu-id="836ae-271">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="836ae-272">验证项目是否已被删除</span><span class="sxs-lookup"><span data-stu-id="836ae-272">Verify that items were deleted</span></span>

<span data-ttu-id="836ae-p142">若要验证是否已成功删除邮箱的 "可恢复的项目" 文件夹中的项目, 请使用 Exchange Online PowerShell 中的**get-mailboxfolderstatistics** cmdlet 检查 "可恢复的项目" 文件夹中的邮件大小和数量。您可以将这些统计信息与您在步骤1中收集的统计信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="836ae-p142">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="836ae-275">在中运行以下命令, 以获取用户主邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="836ae-275">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="836ae-276">运行以下命令以获取用户存档邮箱中的 "可恢复的项目" 文件夹中的文件夹和子文件夹中的项目大小和总数。</span><span class="sxs-lookup"><span data-stu-id="836ae-276">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="836ae-277">步骤 6: 将邮箱还原到其以前的状态</span><span class="sxs-lookup"><span data-stu-id="836ae-277">Step 6: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="836ae-p143">最后一步是将邮箱还原回其以前的配置。这意味着重置您在步骤2中更改的属性, 并重新应用您在步骤3中删除的保留。这包括:</span><span class="sxs-lookup"><span data-stu-id="836ae-p143">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="836ae-p144">将已删除项目的保留期更改回其以前的值。或者, 您可以仅将此设置保留为30天, 即 Exchange Online 中的最大值。</span><span class="sxs-lookup"><span data-stu-id="836ae-p144">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="836ae-283">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="836ae-283">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="836ae-284">重新启用客户端访问方法, 以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-284">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="836ae-285">重新应用已删除的保留和 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="836ae-285">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="836ae-286">重新启用托管文件夹助理以处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-286">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="836ae-287">建议您在重新启用托管文件夹助理以处理邮箱之前, 等待24小时后再应用保留策略 (并验证是否已就绪)。</span><span class="sxs-lookup"><span data-stu-id="836ae-287">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="836ae-288">在 Exchange Online PowerShell 中执行以下步骤 (按指定的顺序)。</span><span class="sxs-lookup"><span data-stu-id="836ae-288">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="836ae-p145">运行以下命令, 将已删除项目的保留期更改回其原始值。这假定上一个设置的时间不到30天;例如14天。</span><span class="sxs-lookup"><span data-stu-id="836ae-p145">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="836ae-291">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="836ae-291">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="836ae-292">运行以下命令, 将所有客户端访问方法重新启用到邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-292">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="836ae-p146">重新应用您在步骤3中删除的保留。根据保留的类型, 使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="836ae-p146">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="836ae-295">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="836ae-295">**Litigation Hold**</span></span>
    
    <span data-ttu-id="836ae-296">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="836ae-296">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="836ae-297">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="836ae-297">**In-Place Hold**</span></span>
    
    <span data-ttu-id="836ae-298">使用 EAC (或 Exchange Online PowerShell) 将邮箱重新添加到就地保留。</span><span class="sxs-lookup"><span data-stu-id="836ae-298">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="836ae-299">**应用于特定邮箱的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="836ae-299">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="836ae-p147">使用安全&amp;合规性中心将邮箱重新添加到 Office 365 保留策略。转到安全&amp;合规中心中的 "**日期调控** \> "**保留**页, 编辑保留策略, 并将邮箱重新添加到应用保留策略的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="836ae-p147">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="836ae-302">**组织范围内的 Office 365 保留策略**</span><span class="sxs-lookup"><span data-stu-id="836ae-302">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="836ae-p148">如果通过从策略中排除组织范围或 Exchange 范围内的保留策略, 请使用安全&amp;合规性中心将邮箱从排除的用户列表中删除。转到安全&amp;合规中心中的 "**日期调控** \> "**保留**页, 编辑组织范围的保留策略, 并将邮箱从已排除的收件人列表中删除。执行此操作将把保留策略重新应用到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-p148">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="836ae-306">**电子数据展示事例保留**</span><span class="sxs-lookup"><span data-stu-id="836ae-306">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="836ae-p149">使用安全&amp;合规性中心将邮箱重新添加到与电子数据展示事例相关联的保留。转到安全&amp;合规中心中的 "**搜索&amp;调查** \> **电子数据展示**" 页, 打开事例, 并将邮箱重新添加到保留。</span><span class="sxs-lookup"><span data-stu-id="836ae-p149">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="836ae-p150">运行以下命令, 以允许托管文件夹助理再次处理邮箱。如前所述, 我们建议您在重新启用托管文件夹助理之前, 请等待24小时后再重新应用保留策略 (并验证是否已就绪)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p150">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="836ae-311">若要验证是否已将邮箱还原回其以前的配置, 可以运行以下命令, 然后将设置与您在步骤1中收集的设置进行比较。</span><span class="sxs-lookup"><span data-stu-id="836ae-311">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="836ae-312">更多信息</span><span class="sxs-lookup"><span data-stu-id="836ae-312">More information</span></span>

<span data-ttu-id="836ae-p151">下面的表格介绍了在运行 set-organizationconfig cmdlet 或\*\*\*\* cmdlet 时, 如何根据*InPlaceHolds*属性中的值标识不同类型的\*\*\*\* 保留。有关更多详细信息, 请参阅[如何识别 Exchange Online 邮箱上放置的保留类型](identify-a-hold-on-an-exchange-online-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="836ae-p151">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. For more detailed information, see [How to identify the type of hold placed on an Exchange Online mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

<span data-ttu-id="836ae-315">如前所述, 在成功删除 "可恢复的项目" 文件夹中的项目之前, 必须从邮箱中删除所有保留和 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="836ae-315">As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="836ae-316">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="836ae-316">**Hold type**</span></span>|<span data-ttu-id="836ae-317">**示例值**</span><span class="sxs-lookup"><span data-stu-id="836ae-317">**Example value**</span></span>|<span data-ttu-id="836ae-318">**如何识别保留**</span><span class="sxs-lookup"><span data-stu-id="836ae-318">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="836ae-319">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="836ae-319">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="836ae-320">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="836ae-320">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="836ae-321">就地保留</span><span class="sxs-lookup"><span data-stu-id="836ae-321">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="836ae-p152">*InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。您可以指示这是就地保留, 因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="836ae-p152">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="836ae-324">您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取有关邮箱的就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="836ae-324">You can use the  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="836ae-325">应用于特定邮箱的安全&amp;合规性中心中的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="836ae-325">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="836ae-326">或</span><span class="sxs-lookup"><span data-stu-id="836ae-326">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="836ae-p153">当您运行**邮箱获取**cmdlet 时, *InPlaceHolds*属性还包含应用于邮箱的 Office 365 保留策略的 guid。您可以确定保留策略, 因为 GUID 以`mbx`前缀开头。请注意, 如果保留策略的 GUID 以`skp`前缀开头, 则表示该保留策略应用于 Skype for business 会话。</span><span class="sxs-lookup"><span data-stu-id="836ae-p153">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="836ae-330">若要标识应用于邮箱的 Office 365 保留策略, 请在安全&amp;合规中心 PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="836ae-330">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="836ae-331">运行此命令时, `mbx`请`skp`务必删除或前缀。</span><span class="sxs-lookup"><span data-stu-id="836ae-331">Be sure to remove the  `mbx` or  `skp` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="836ae-332">安全&amp;合规中心中的组织范围内的 Office 365 保留策略</span><span class="sxs-lookup"><span data-stu-id="836ae-332">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="836ae-333">无值</span><span class="sxs-lookup"><span data-stu-id="836ae-333">No value</span></span>  <br/> <span data-ttu-id="836ae-334">或</span><span class="sxs-lookup"><span data-stu-id="836ae-334">or</span></span>  <br/>  <span data-ttu-id="836ae-335">`-mbxe9b52bf7ab3b46a286308ecb29624696`(指示邮箱已从组织范围的策略中排除)</span><span class="sxs-lookup"><span data-stu-id="836ae-335">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="836ae-336">即使在运行**邮箱**cmdlet 时, *InPlaceHolds*属性为空, 仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="836ae-336">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="836ae-p154">若要验证这一点, 可以在`Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell 中运行命令, 以获取组织范围内的 Office 365 保留策略的 guid 列表。应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`。</span><span class="sxs-lookup"><span data-stu-id="836ae-p154">To verify this, you can run the  `Get-OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  </span></span><br/> <span data-ttu-id="836ae-339">若要标识应用于邮箱的组织范围内的 Office 365 保留策略, 请在安全&amp;合规中心 PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="836ae-339">To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/><span data-ttu-id="836ae-340">请注意, 如果从组织范围内的 Office 365 保留策略中排除了某个邮箱, 则在运行 "**获取邮箱**" cmdlet 时, 该保留策略的 GUID 将显示在用户邮箱的*InPlaceHolds*属性中。它是由前缀`-mbx`标识的;例如,`-mbxe9b52bf7ab3b46a286308ecb29624696`</span><span class="sxs-lookup"><span data-stu-id="836ae-340">Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696`</span></span> <br/> |
|<span data-ttu-id="836ae-341">安全&amp;合规中心中的电子数据展示事例保留</span><span class="sxs-lookup"><span data-stu-id="836ae-341">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="836ae-p155">*InPlaceHolds*属性还包含与可能放置在邮箱上的电子数据展示事例&amp;相关联的任何保留的 GUID。你可以告诉这是电子数据展示事例保留, 因为 GUID 以`UniH`前缀开头。</span><span class="sxs-lookup"><span data-stu-id="836ae-p155">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="836ae-p156">您可以使用安全`Get-CaseHoldPolicy` &amp;合规中心 PowerShell 中的 cmdlet 来获取有关与邮箱相关的电子数据展示事例的信息。例如, 您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示邮箱上的事例保留的名称。运行此命令时, `UniH`请务必删除前缀。</span><span class="sxs-lookup"><span data-stu-id="836ae-p156">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  </span></span><br/><br/> <span data-ttu-id="836ae-347">若要标识与邮箱的保留内容相关联的电子数据展示事例, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="836ae-347">To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:</span></span><br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


