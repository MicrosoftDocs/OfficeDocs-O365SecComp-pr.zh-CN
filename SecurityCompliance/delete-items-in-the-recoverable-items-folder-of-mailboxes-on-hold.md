---
title: 删除项目可恢复邮件文件夹中的基于云的邮箱置于保留状态的管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/21/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: 管理员： 删除用户的 Exchange Online 邮箱，可恢复的项目文件夹中的项目，即使该邮箱置于合法保留。这是有效的方法来删除已意外溢出至 Office 365 的数据。
ms.openlocfilehash: 0519e389f05ed9952090fb9b163a05d18e3bd762
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23014026"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a><span data-ttu-id="a38ef-104">删除项目可恢复邮件文件夹中的基于云的邮箱置于保留状态的管理员帮助</span><span class="sxs-lookup"><span data-stu-id="a38ef-104">Delete items in the Recoverable Items folder of cloud-based mailboxes on hold - Admin Help</span></span>

<span data-ttu-id="a38ef-p102">Exchange Online 邮箱的可恢复邮件文件夹存在以防止被意外或恶意删除。此外可用于存储项目，将会保留，并且可以访问 Office 365 合规性功能，例如保留和电子数据展示搜索。但是，在某些情况下组织可能会有已意外保留它们必须删除可恢复邮件文件夹中的数据。例如，用户可能不知情的情况下发送或转发电子邮件包含敏感信息或可能严重业务后果的信息。即使将永久删除邮件，可能无限期保留因为合法保留已被设置邮箱上。因为数据已意外溢出至 Office 365，这种情况下被称为数据泄漏。在这些情况下，您可以删除用户的 Exchange Online 邮箱，可恢复的项目文件夹中的项目，即使该邮箱置于保留与 Office 365 中的不同的保留功能之一。保留这些类型包括诉讼保留、 就地保留、 电子数据展示保留和 Office 365 保留策略在 Office 365 安全性中创建&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p102">The Recoverable Items folder for an Exchange Online mailbox exists to protect from accidental or malicious deletions. It's also used to store items that are retained and accessed by Office 365 compliance features, such as holds and eDiscovery searches. However, in some situations organizations might have data that's been unintentionally retained in the Recoverable Items folder that they must delete. For example, a user might unknowingly send or forward an email message that contains sensitive information or information that may have serious business consequences. Even if the message is permanently deleted, it might be retained indefinitely because a legal hold has been placed on the mailbox. This scenario is known as data spillage because data has been unintentionally spilled into Office 365. In these situations, you can delete items in a user's Recoverable Items folder for an Exchange Online mailbox, even if that mailbox is placed on hold with one of the different hold features in Office 365. These types of holds include Litigation Holds, In-Place Holds, eDiscovery holds, and Office 365 retention policies created in the Office 365 Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="a38ef-p103">本文介绍如何从基于云的邮箱置于保留状态的可恢复邮件文件夹中删除项目。此过程涉及禁用对邮箱的访问和禁用单个项目恢复，禁用托管文件夹助理处理邮箱、 暂时删除保留项，从可恢复邮件文件夹中，删除项和然后恢复到先前的配置邮箱。下面是过程：</span><span class="sxs-lookup"><span data-stu-id="a38ef-p103">This article explains how to delete items from the Recoverable Items folder for cloud-based mailboxes that are on hold. This procedure involves disabling access to the mailbox and disabling single item recovery, disabling the Managed Folder Assistant from processing the mailbox, temporarily removing the hold, deleting items from the Recoverable Items folder, and then reverting the mailbox to its previous configuration. Here's the process:</span></span> 
  
[<span data-ttu-id="a38ef-116">步骤 1： 收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="a38ef-116">Step 1: Collect information about the mailbox</span></span>](#step-1-collect-information-about-the-mailbox)

[<span data-ttu-id="a38ef-117">步骤 2： 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-117">Step 2: Prepare the mailbox</span></span>](#step-2-prepare-the-mailbox)

[<span data-ttu-id="a38ef-118">步骤 3： 从邮箱中删除所有保留项</span><span class="sxs-lookup"><span data-stu-id="a38ef-118">Step 3: Remove all holds from the mailbox</span></span>](#step-3-remove-all-holds-from-the-mailbox)

[<span data-ttu-id="a38ef-119">步骤 4： 删除可恢复邮件文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="a38ef-119">Step 4: Delete items in the Recoverable Items folder</span></span>](#step-4-delete-items-in-the-recoverable-items-folder)

[<span data-ttu-id="a38ef-120">步骤 5： 将恢复其先前状态的邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-120">Step 5: Revert the mailbox to its previous state</span></span>](#step-5-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> <span data-ttu-id="a38ef-p104">本文中所述的过程将导致数据被永久删除 （清除） 从 Exchange Online 邮箱。这意味着您从可恢复邮件文件夹中删除的消息无法恢复，不能用于法律或其他合规性目的。如果您想要将置于保持状态的诉讼保留，就地保留，一部分的邮箱中删除邮件保留电子数据展示，或在 Office 365 安全性中创建 Office 365 保留策略&amp;合规性中心，检查您的记录管理或法律之前删除保留项的部门。您的组织可能必须定义上的邮箱是否保留策略或数据泄漏事件优先。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p104">The procedures outlined in this article will result in data being permanently deleted (purged) from an Exchange Online mailbox. That means messages that you delete from the Recoverable Items folder can't be recovered and won't be available for legal discovery or other compliance purposes. If you want to delete messages from a mailbox that's placed on hold as part of a Litigation Hold, In-Place Hold, eDiscovery hold, or Office 365 retention policy created in the Office 365 Security &amp; Compliance Center, check with your records management or legal departments before removing the hold. Your organization might have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="a38ef-125">准备工作</span><span class="sxs-lookup"><span data-stu-id="a38ef-125">Before you begin</span></span>

- <span data-ttu-id="a38ef-126">您必须同时分配的以下管理角色在 Exchange Online 搜索并删除在步骤 4 可恢复邮件文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="a38ef-126">You have to be assigned both of the following management roles in Exchange Online to search for and delete messages from the Recoverable Items folder in Step 4.</span></span>
    
  - <span data-ttu-id="a38ef-p105">**邮箱搜索**-此角色可使您能够搜索组织中的邮箱。默认情况下，Exchange 管理员不分配此角色。要将自己分配此角色，将自己添加为发现管理角色组的成员在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p105">**Mailbox Search** - This role lets you to search mailboxes in your organization. Exchange administrators aren't assigned this role by default. To assign yourself this role, add yourself as a member of the Discovery Management role group in Exchange Online.</span></span> 
    
  - <span data-ttu-id="a38ef-p106">**邮箱导入导出**-此角色可以从用户的邮箱中删除邮件。默认情况下，此角色不分配给任何角色组。若要从用户的邮箱中删除邮件，您可以添加邮箱导入导出角色到 Organization Management 角色组在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p106">**Mailbox Import Export** - This role lets you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> 
    
- <span data-ttu-id="a38ef-p107">非活动邮箱不支持这篇文章中介绍的过程。这是因为您不能重新应用保留 （或 Office 365 保留策略） 到非活动邮箱后将其删除。当您从非活动邮箱删除保留时，它更改为普通软删除邮箱，并将被永久删除从您的组织后，它由托管文件夹助理处理。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p107">The procedure described in this article isn't supported for inactive mailboxes. That's because you can't re-apply a hold (or Office 365 retention policy) to an inactive mailbox after you remove it. When you remove a hold from an inactive mailbox, it's changed to a normal soft-deleted mailbox and will be permanently deleted from your organization after it's processed by the Managed Folder Assistant.</span></span>
    
- <span data-ttu-id="a38ef-p108">已分配给已被锁定与保留锁的 Office 365 保留策略的邮箱，无法执行此过程。这是因为保留锁防止删除或从 Office 365 保留策略和禁用托管文件夹助理邮箱不包括邮箱。有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p108">You can't perform this procedure for a mailbox that has been assigned to an Office 365 retention policy that's been locked with a Preservation Lock. That's because a Preservation Lock prevents you from removing or excluding the mailbox from the Office 365 retention policy and from disabling the Managed Folder Assistant on the mailbox. For more information about locking retention policies, see [Locking a retention policy](retention-policies.md#locking-a-retention-policy).</span></span>
    
- <span data-ttu-id="a38ef-p109">如果邮箱不置于保持状态 （或没有启用单个项目恢复），您可以只从可恢复邮件文件夹中删除项目。有关如何执行此操作的详细信息，请参阅[搜索并删除邮件](https://go.microsoft.com/fwlink/?linkid=852453)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p109">If a mailbox isn't placed on hold (or doesn't have single item recovery enabled), you can simply delete the items from the Recoverable Items folder. For more information about how to do this, see [Search for and delete messages ](https://go.microsoft.com/fwlink/?linkid=852453).</span></span>
  
## <a name="step-1-collect-information-about-the-mailbox"></a><span data-ttu-id="a38ef-141">步骤 1： 收集有关邮箱的信息</span><span class="sxs-lookup"><span data-stu-id="a38ef-141">Step 1: Collect information about the mailbox</span></span>

<span data-ttu-id="a38ef-p110">此第一个步骤是收集从目标邮箱将影响此过程的所选的属性。确保记下这些设置，或将其保存到文本文件中，因为您将更改某些这些属性，然后还原到步骤 5 中的原始值，从可恢复邮件文件夹中删除项目之后。下面是您需要收集邮箱属性的列表。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p110">This first step is to collect selected properties from the target mailbox that will affect this procedure. Be sure to write down these settings or save them to a text file because you'll change some of these properties and then revert back to the original values in Step 5, after you delete items from the Recoverable Items folder. Here's a list of the mailbox properties you need to collect.</span></span>
  
-  <span data-ttu-id="a38ef-145">*SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，将禁用单个恢复并增加步骤 3 中的已删除的邮件保留期。</span><span class="sxs-lookup"><span data-stu-id="a38ef-145">*SingleItemRecoveryEnabled*  and  *RetainDeletedItemsFor*  ; if necessary, you'll disable single recovery and increase the deleted items retention period in Step 3.</span></span> 
    
-  <span data-ttu-id="a38ef-p111">*LitigationHoldEnabled*和*InPlaceHolds* ;您需要确定邮箱置于，以便可以在步骤 3 中临时删除它们的所有保留项。请参阅有关如何确定可能置于邮箱类型保留提示的[详细信息](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p111">*LitigationHoldEnabled*  and  *InPlaceHolds*  ; you need to identify all the holds placed on the mailbox so that you can temporarily remove them in Step 3. See the [More information](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
    
<span data-ttu-id="a38ef-p112">此外，您需要获取邮箱客户端访问设置，因此，以便所有者 （或其他用户） 不能在此过程访问邮箱，您可以暂时禁用它们。最后，您可以在可恢复邮件文件夹中获取的当前大小和项目数。删除在步骤 4 可恢复邮件文件夹中的项目后，您将使用此信息来验证已实际删除项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p112">Additionally, you need to get the mailbox client access settings so you can temporarily disable them so the owner (or other users) can't access the mailbox during this procedure. Finally, you can get the current size and number of items in the Recoverable Items folder. After you delete items in the Recoverable Items folder in Step 4, you'll use this information to verify that items were actually removed.</span></span>
  
1. <span data-ttu-id="a38ef-p113">[连接到 Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。确保用于已分配 Exchange Online 中的适当的管理角色的管理员帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p113">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Be sure to use a user name and password for an administrator account that's been assigned the appropriate management roles in Exchange Online.</span></span> 
    
2. <span data-ttu-id="a38ef-153">运行以下命令以获取有关单个项目恢复和已删除的邮件保留期限。</span><span class="sxs-lookup"><span data-stu-id="a38ef-153">Run the following command to get information about single item recovery and the deleted item retention period.</span></span>

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   <span data-ttu-id="a38ef-p114">如果启用单个项目恢复，则必须将禁用在步骤 2 中。已删除的邮件保留期限不为 30 天 （Exchange Online 中的最大值），然后您可以增加其在步骤 2 中。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p114">If single item recovery is enabled, you'll have to disable it in Step 2. If the deleted item retention period isn't set for 30 days (the maximum value in Exchange Online), then you can increase it in Step 2.</span></span> 
    
3. <span data-ttu-id="a38ef-156">运行以下命令以获取访问设置邮箱的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-156">Run the following command to get the mailbox access settings for the mailbox.</span></span> 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   <span data-ttu-id="a38ef-157">将禁用所有这些访问方法在步骤 2 中。</span><span class="sxs-lookup"><span data-stu-id="a38ef-157">You'll disable all of these access methods in Step 2.</span></span>
    
4. <span data-ttu-id="a38ef-158">运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="a38ef-158">Run the following command to get information about the holds and Office 365 retention policies applied to the mailbox.</span></span>
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > <span data-ttu-id="a38ef-159">如果*InPlaceHolds*属性中有太多值而不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行显示每个值。</span><span class="sxs-lookup"><span data-stu-id="a38ef-159">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
5. <span data-ttu-id="a38ef-160">运行以下命令以获取有关 Office 365 的任何组织范围内保留策略的信息。</span><span class="sxs-lookup"><span data-stu-id="a38ef-160">Run the following command to get information about any organization-wide Office 365 retention policies.</span></span> 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   <span data-ttu-id="a38ef-161">如果您的组织有任何组织范围内的 Office 365 保留策略，必须将邮箱排除在步骤 3 中这些策略。</span><span class="sxs-lookup"><span data-stu-id="a38ef-161">If your organization has any organization-wide Office 365 retention policies, you'll have to exclude the mailbox from these policies in Step 3.</span></span>

   > [!TIP]
    > <span data-ttu-id="a38ef-162">如果*InPlaceHolds*属性中有太多值而不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行显示每个值。</span><span class="sxs-lookup"><span data-stu-id="a38ef-162">If there are too many values in the  *InPlaceHolds*  property and not all of them are displayed, you can run the  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each value on a separate line.</span></span> 
  
6. <span data-ttu-id="a38ef-163">运行以下命令以获取打包在文件夹和子文件夹中用户的主邮箱中可恢复邮件文件夹中的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="a38ef-163">Run the following command to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="a38ef-164">如果启用了用户的存档邮箱，运行以下命令以获取文件夹和子文件夹中其存档邮箱中可恢复邮件文件夹中的大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="a38ef-164">If the user's archive mailbox is enabled, run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in their archive mailbox.</span></span> 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   <span data-ttu-id="a38ef-p115">删除在步骤 4 中的项目时，您可以选择删除或删除用户的主存档邮箱中可恢复邮件文件夹中的项目。请注意，是否为邮箱启用了自动扩展存档，则辅助存档邮箱中的项目不会删除。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p115">When you delete items in Step 4, you can choose to delete or not delete items in the Recoverable Items folder in the user's primary archive mailbox. Note that if auto-expanding archiving is enabled for the mailbox, items in an auxiliary archive mailbox won't be deleted.</span></span>
  
## <a name="step-2-prepare-the-mailbox"></a><span data-ttu-id="a38ef-167">步骤 2： 准备邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-167">Step 2: Prepare the mailbox</span></span>

<span data-ttu-id="a38ef-168">后收集和保存有关邮箱的信息下, 一步是准备好邮箱，通过执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a38ef-168">After collecting and saving information about the mailbox, the next step is to prepare the mailbox by performing the following tasks:</span></span> 
  
- <span data-ttu-id="a38ef-169">**禁用客户端对邮箱的访问权**，以便邮箱所有者无法访问其邮箱并在此过程的邮箱数据进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="a38ef-169">**Disable client access to mailbox** so that the mailbox owner can't access their mailbox and make any changes to the mailbox data during this procedure.</span></span> 
    
- <span data-ttu-id="a38ef-170">为 30 天**增加已删除的邮件保留期限**（Exchange Online 中的最大值），以便之前可以在步骤 4 中删除这些项目不清除从可恢复邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="a38ef-170">**Increase the deleted item retention period** to 30 days (the maximum value in Exchange Online) so that items aren't purged from the Recoverable Items folder before you can delete them in Step 4.</span></span> 
    
- <span data-ttu-id="a38ef-171">**禁用单个项目的恢复**的项目以便不会保留 （已删除的邮件保留期限的持续时间） 后删除从步骤 4 中的可恢复项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="a38ef-171">**Disable single Item recovery** so that items won't be retained (for the duration of the deleted item retention period) after you delete them from the Recoverable Items folder in Step 4.</span></span> 
    
- <span data-ttu-id="a38ef-172">**禁用托管文件夹助理**，以便使其不处理该邮箱并保留在步骤 4 中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-172">**Disable the Managed Folder Assistant** so that it doesn't process the mailbox and retain the items that you delete in Step 4.</span></span> 
    
<span data-ttu-id="a38ef-173">在 Exchange Online PowerShell 中执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="a38ef-173">Perform the following steps in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="a38ef-p116">运行以下命令以禁用对邮箱的所有客户端访问。命令语法假定所有客户端访问方法已启用邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p116">Run the following command to disable all client access to the mailbox. The command syntax assumes that all client access methods were enabled on the mailbox.</span></span>

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > <span data-ttu-id="a38ef-p117">它可能需要长达 60 分钟禁用对邮箱的所有客户端访问方法。请注意禁用这些访问方法不断开其当前登录邮箱所有者。如果所有者未登录，然后他们将无法访问其邮箱后禁用这些访问方法。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p117">It might take up to 60 minutes to disable all client access methods to the mailbox. Note that disabling these access methods won't disconnect the mailbox owner they're currently signed in. If the owner isn't signed in, then they won't be able to access their mailbox after these access methods are disabled.</span></span> 
  
2. <span data-ttu-id="a38ef-p118">运行以下命令以增加最大值 30 天的已删除的邮件保留期限。此，假定当前的设置不超过 30 天。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p118">Run the following command to increase the deleted item retention period the maximum of 30 days. This assumes that the current setting is less than 30 days.</span></span> 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. <span data-ttu-id="a38ef-181">运行以下命令以禁用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="a38ef-181">Run the following command to disable single item recovery.</span></span>
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > <span data-ttu-id="a38ef-p119">它可能需要长达 60 分钟禁用单个项目恢复。不删除可恢复邮件文件夹中的项目，直到此时间已。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p119">It might take up to 60 minutes to disable single item recovery. Don't delete items in the Recoverable Items folder until this period has elapsed.</span></span> 
  
4. <span data-ttu-id="a38ef-p120">运行以下命令以防止托管文件夹助理处理邮箱。如前所述，您可以禁用托管文件夹助理仅当与保留锁的 Office 365 保留策略不应用到的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p120">Run the following command to prevent the Managed Folder Assistant from processing the mailbox. As previously explained, you can disable the Managed Folder Assistant only if an Office 365 retention policy with a Preservation Lock is not applied to the mailbox.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a><span data-ttu-id="a38ef-186">步骤 3： 从邮箱中删除所有保留项</span><span class="sxs-lookup"><span data-stu-id="a38ef-186">Step 3: Remove all holds from the mailbox</span></span>

<span data-ttu-id="a38ef-p121">您可以从可恢复邮件文件夹中删除项目之前的最后一步是删除所有保留项 （即在步骤 1 中确定） 邮箱置于。以便不会保留项，从可恢复邮件文件夹删除后，必须删除所有保留项。以下各节包含有关删除邮箱的保留项的不同类型的信息。请参阅有关如何确定可能置于邮箱类型保留提示的[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p121">The last step before you can delete items from the Recoverable Items folder is to remove all holds (that you identified in Step 1) placed on the mailbox. All holds must be removed so that items won't be retained after you delete them from the Recoverable Items folder. The following sections contain information about removing different types of holds on a mailbox. See the [More information](#more-information) section for tips about how to identify the type hold that might be placed on a mailbox.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="a38ef-191">如前面所述，请与您的记录管理或法律部门邮箱中删除保留之前。</span><span class="sxs-lookup"><span data-stu-id="a38ef-191">As previously stated, check with your records management or legal departments before removing a hold from a mailbox.</span></span> 
  
 ### <a name="litigation-hold"></a><span data-ttu-id="a38ef-192">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="a38ef-192">Litigation Hold</span></span>
  
<span data-ttu-id="a38ef-193">运行以下命令在 Exchange Online PowerShell，可以从邮箱中删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="a38ef-193">Run the following command in Exchange Online PowerShell to remove a Litigation Hold from the mailbox.</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> <span data-ttu-id="a38ef-p122">类似于禁用客户端访问方法和单个项目恢复，可能需要 60 分钟诉讼保留中删除。不要删除从可恢复邮件文件夹的项目，直到此时间已。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p122">Similar to disabling the client access methods and single item recovery, it might take up to 60 minutes to remove the Litigation Hold. Don't delete items from the Recoverable Items folder until this period has elapsed.</span></span> 
  
 ### <a name="in-place-hold"></a><span data-ttu-id="a38ef-196">就地保留</span><span class="sxs-lookup"><span data-stu-id="a38ef-196">In-Place Hold</span></span>
  
<span data-ttu-id="a38ef-p123">运行以下命令在 Exchange Online PowerShell，可以确定邮箱置于就地保留。使用您在步骤 1 中确定的就地保留的 GUID。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p123">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's placed on the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1.</span></span> 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
<span data-ttu-id="a38ef-p124">确定就地保留后，您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 可以从保留中删除邮箱。有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p124">After you identify the In-Place Hold, you can use the Exchange admin center (EAC) or Exchange Online PowerShell to remove the mailbox from the hold. For more information, see [Create or remove an In-Place Hold](https://go.microsoft.com/fwlink/?linkid=852668).</span></span>
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a><span data-ttu-id="a38ef-201">Office 365 的保留策略应用于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-201">Office 365 retention policies applied to specific mailboxes</span></span>
  
<span data-ttu-id="a38ef-p125">运行以下命令， [Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识 Office 365 保留策略应用于邮箱。使用的 GUID (不包括`mbx`或`skp`前缀) 在步骤 1 中确定的保留策略。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p125">Run the following command in [Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the Office 365 retention policy that is applied to the mailbox. Use the GUID (not including the  `mbx` or  `skp` prefix) for the retention policy that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
<span data-ttu-id="a38ef-204">确定保留策略后，转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑上一步，标识的保留策略，并从列表中删除邮箱保留策略中包括的收件人。</span><span class="sxs-lookup"><span data-stu-id="a38ef-204">After you identify the retention policy, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy that you identified in the previous step, and remove the mailbox from the list of recipients that are included in the retention policy.</span></span> 
  
 ### <a name="organization-wide-office-365-retention-policies"></a><span data-ttu-id="a38ef-205">Office 365 组织范围中的保留策略</span><span class="sxs-lookup"><span data-stu-id="a38ef-205">Organization-wide Office 365 retention policies</span></span>
  
<span data-ttu-id="a38ef-p126">组织范围内和 Exchange 范围 Office 365 保留策略应用于组织中的每个邮箱。它们应用于组织级别 （而不是邮箱级别），并且在步骤 1 中运行**Get-organizationconfig** cmdlet 时返回。运行以下命令，[安全&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识组织范围内的 Office 365 保留策略。使用的 GUID (不包括`mbx`前缀) 在步骤 1 中确定的组织范围内保留策略。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p126">Organization-wide and Exchange-wide Office 365 retention policies are applied to every mailbox in the organization. They are applied at the organization level (not the mailbox level) and are returned when you run the **Get-OrganizationConfig** cmdlet in Step 1. Run the following command in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the organization-wide Office 365 retention policies. Use the GUID (not including the  `mbx` prefix) for the organization-wide retention policies that you identified in Step 1.</span></span> 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

<span data-ttu-id="a38ef-p127">确定组织范围内的 Office 365 保留策略后，转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑中标识的每个组织范围内保留策略上一步骤，并将邮箱添加到已排除的收件人列表。此操作将保留策略中删除用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p127">After you identify the organization-wide Office 365 retention policies, go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit each organization-wide retention policy that you identified in the previous step, and add the mailbox to the list of excluded recipients. Doing this will remove the user's mailbox from the retention policy.</span></span> 
  
 ### <a name="ediscovery-case-holds"></a><span data-ttu-id="a38ef-212">电子数据展示事例包含</span><span class="sxs-lookup"><span data-stu-id="a38ef-212">eDiscovery case holds</span></span>
  
<span data-ttu-id="a38ef-p128">运行以下命令，[安全&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识保留项应用于邮箱电子数据展示事例相关联。使用的 GUID (不包括`UniH`前缀) 的电子数据展示保留在步骤 1 中确定。请注意，第二个命令显示的电子数据展示案例保留项相关联; 名称第三个命令显示的保留项的名称。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p128">Run the following commands in [Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/?linkid=627084) to identify the hold associated with an eDiscovery case that's applied to the mailbox. Use the GUID (not including the  `UniH` prefix) for the eDiscovery hold that you identified in Step 1. Note that the second command displays the name of the eDiscovery case the hold is associated with; the third command displays the name of the hold.</span></span> 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

<span data-ttu-id="a38ef-p129">您已确定的电子数据展示事例并保留名称后，转到**搜索&amp;调查**\>安全中的**电子数据展示**页&amp;合规性中心打开这种情况，并从保留中删除邮箱。有关详细信息，请参阅[管理 Office 365 安全性的电子数据展示事例&amp;合规性中心](manage-ediscovery-cases.md)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p129">After you've identified the name of the eDiscovery case and the hold, go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and remove the mailbox from the hold. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md).</span></span>
  
## <a name="step-4-delete-items-in-the-recoverable-items-folder"></a><span data-ttu-id="a38ef-218">步骤 4： 删除可恢复邮件文件夹中的项目</span><span class="sxs-lookup"><span data-stu-id="a38ef-218">Step 4: Delete items in the Recoverable Items folder</span></span>

<span data-ttu-id="a38ef-p130">现在，您就可以实际使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet 在 Exchange Online PowerShell 中删除可恢复邮件文件夹中的项目。运行**Search-mailbox** cmdlet 时，您可以具有三个选项。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p130">Now you're ready to actually delete items in the Recoverable Items folder by using the [Search-Mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet in Exchange Online PowerShell. You have three options when running the **Search-Mailbox** cmdlet.</span></span> 
  
- <span data-ttu-id="a38ef-221">将项目复制到目标邮箱之前，以便您可以查看项目，如有必要，删除它们之前，会删除它们。</span><span class="sxs-lookup"><span data-stu-id="a38ef-221">Copy items to a target mailbox before you delete them so that you can review the items, if necessary, before you delete them.</span></span>
    
- <span data-ttu-id="a38ef-222">将项目复制到目标邮箱并将其删除在同一命令中。</span><span class="sxs-lookup"><span data-stu-id="a38ef-222">Copy items to a target mailbox and delete them in the same command.</span></span>
    
- <span data-ttu-id="a38ef-223">不将其复制到目标邮箱中删除项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-223">Delete items without copying them to a target mailbox.</span></span> 
    
<span data-ttu-id="a38ef-p131">运行时，也将删除用户的主存档邮箱中的可恢复的项目文件夹中项目的注释 * * Search-mailbox * * cmdlet。要防止这样，您可以包括*DoNotIncludeArchive*开关。如前面所述，如果展开存档是启用的邮箱，* * Search-mailbox * * cmdlet 不会删除辅助存档邮箱中的项目。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p131">Note that items in the Recoverable Items folder in the user's primary archive mailbox will also be deleted when you run the ** Search-Mailbox ** cmdlet. To prevent this, you can include the  *DoNotIncludeArchive*  switch. And as previously stated, if auto-expanding archiving is enabled for the mailbox, the ** Search-Mailbox ** cmdlet doesn't deleted items in an auxiliary archive mailbox. For more information about auto-expanding archive, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a38ef-p132">如果添加一个搜索查询（通过使用  *SearchQuery*  参数）， **Search-Mailbox** cmdlet 最多返回搜索结果中的 10,000 个项目。因此，如果添加一个搜索查询，则可能需要多次运行 **Search-Mailbox** 命令才能将 10,000 多个项目删除。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p132">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
  
<span data-ttu-id="a38ef-p133">下面的示例显示这些选项的每个命令语法。这些示例使用`-SearchQuery size>0`参数值，从可恢复邮件文件夹中的所有子文件夹中删除所有项目。如果您需要删除满足特定条件的项目，您还可以使用*SearchQuery*参数指定其他条件，如一条消息或日期范围的主题。请参阅下面的[使用 SearchQuery 参数的其他示例](#other-examples-of-using-the-searchquery-parameter)。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p133">The following examples show the command syntax for each of these options. These examples use the  `-SearchQuery size>0` parameter value, which deletes all items from all subfolders in the Recoverable Items folder. If you need to delete only items that match specific conditions, you can also use the  *SearchQuery*  parameter to specify other conditions, such as the subject of a message or a date range. See the [other examples of using the SearchQuery parameter](#other-examples-of-using-the-searchquery-parameter) below.</span></span> 
  
### <a name="example-1"></a><span data-ttu-id="a38ef-234">示例 1</span><span class="sxs-lookup"><span data-stu-id="a38ef-234">Example 1</span></span>

<span data-ttu-id="a38ef-p134">本示例在用户的可恢复的项目文件夹中的所有项目都复制到您的组织发现搜索邮箱中的文件夹。这样可以永久删除之前查看项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p134">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox. This lets you review the items before you permanently delete them.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

<span data-ttu-id="a38ef-p135">在上面的示例，它不需要将项目复制到发现搜索邮箱。您可以将邮件复制到任何目标邮箱。但是，为了防止对敏感的邮箱数据的访问，建议将邮件复制到了授权人员限制访问权限的邮箱。默认情况下访问默认发现搜索邮箱的权限被限制为发现管理角色组的成员在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p135">In the previous example, it isn't required to copy items to the Discovery Search Mailbox. You can copy messages to any target mailbox. However, to prevent access to potentially sensitive mailbox data, we recommend copying messages to a mailbox that has access restricted to authorized personnel. By default, access to the default Discovery Search Mailbox is restricted to members of the Discovery Management role group in Exchange Online.</span></span> 
  
### <a name="example-2"></a><span data-ttu-id="a38ef-241">示例 2</span><span class="sxs-lookup"><span data-stu-id="a38ef-241">Example 2</span></span>

<span data-ttu-id="a38ef-242">本示例将用户的可恢复项目文件夹中的所有项目都复制到您的组织发现搜索邮箱中的文件夹，然后从用户的可恢复项目文件夹中删除项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-242">This example copies all items in the user's Recoverable Items folder to a folder in your organization's Discovery Search Mailbox and then deletes the items from the user's Recoverable Items folder.</span></span>

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a><span data-ttu-id="a38ef-243">示例 3</span><span class="sxs-lookup"><span data-stu-id="a38ef-243">Example 3</span></span>

<span data-ttu-id="a38ef-244">本示例删除用户的可恢复的项目文件夹中的所有项目，而不将其复制到目标邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-244">This example deletes all items in the user's Recoverable Items folder, without copying them to a target mailbox.</span></span> 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a><span data-ttu-id="a38ef-245">使用 SearchQuery 参数的其他示例</span><span class="sxs-lookup"><span data-stu-id="a38ef-245">Other examples of using the SearchQuery parameter</span></span>

<span data-ttu-id="a38ef-p136">下面是一些使用*SearchQuery*参数来查找特定邮件的示例。如果您使用*SearchQuery*参数来搜索特定项，请考虑将搜索结果复制到目标邮箱，以便您可以查看搜索结果，然后再修订查询必要之前删除的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p136">Here are a few examples of using the  *SearchQuery*  parameter to find specific messages. If you use the  *SearchQuery*  parameter to search for specific items, consider copying the search results to a target mailbox so that you can review the search results and then revise the query if necessary before you delete the results of a search.</span></span> 
  
<span data-ttu-id="a38ef-248">本示例返回包含主题字段中的特定短语的邮件。</span><span class="sxs-lookup"><span data-stu-id="a38ef-248">This example returns messages that contain a specific phrase in the Subject field.</span></span>
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

<span data-ttu-id="a38ef-249">本示例返回在指定的日期范围内发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a38ef-249">This example returns messages that were sent within the specified date range.</span></span>
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
<span data-ttu-id="a38ef-250">本示例返回到指定的人发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a38ef-250">This example returns messages that were sent to the specified person.</span></span>

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a><span data-ttu-id="a38ef-251">验证已删除项目</span><span class="sxs-lookup"><span data-stu-id="a38ef-251">Verify that items were deleted</span></span>

<span data-ttu-id="a38ef-p137">若要验证您已成功删除项目从邮箱的可恢复邮件文件夹，使用**Get-mailboxfolderstatistics** cmdlet 在 Exchange Online PowerShell 检查的规模和可恢复的项目文件夹中的项目的数量。可以将这些统计信息与您在步骤 1 中收集的那些进行比较。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p137">To verify that you've successfully deleted items from the Recoverable Items folder of a mailbox, use **Get-MailboxFolderStatistics** cmdlet in Exchange Online PowerShell to check the size and number of items in Recoverable Items folder. You can compare these statistics with the ones you collected in Step 1.</span></span> 
  
<span data-ttu-id="a38ef-254">中运行以下命令以获取文件夹和子文件夹中用户的主邮箱中可恢复邮件文件夹中的的当前大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="a38ef-254">Run the following command in to get the current size and total number of items in folders and subfolders in the Recoverable Items folder in the user's primary mailbox.</span></span> 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
<span data-ttu-id="a38ef-255">运行以下命令以获取文件夹和子文件夹中用户的存档邮箱中可恢复邮件文件夹中的大小和项目总数。</span><span class="sxs-lookup"><span data-stu-id="a38ef-255">Run the following command to get the size and total number of items in folders and subfolders in the Recoverable Items folder in the user's archive mailbox.</span></span> 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-5-revert-the-mailbox-to-its-previous-state"></a><span data-ttu-id="a38ef-256">步骤 5： 将恢复其先前状态的邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-256">Step 5: Revert the mailbox to its previous state</span></span>

<span data-ttu-id="a38ef-p138">最后一步是将还原回先前的配置的邮箱。这意味着您在步骤 2 中更改的属性重置并重新应用您在步骤 3 中删除保留。这包括：</span><span class="sxs-lookup"><span data-stu-id="a38ef-p138">The final step is to revert the mailbox back to its previous configuration. This means resetting the properties that you changed in Step 2 and re-applying the holds that you removed in Step 3. This includes:</span></span>
  
- <span data-ttu-id="a38ef-p139">更改已删除的邮件保留期限回其以前的值。此外，您可以只需保留这将设置为 30 天，最大值在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p139">Changing the deleted item retention period back to its previous value. Alternatively, you can just leave this set to 30 days, the maximum value in Exchange Online.</span></span>
    
- <span data-ttu-id="a38ef-262">重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="a38ef-262">Re-enabling single Item recovery.</span></span>
    
- <span data-ttu-id="a38ef-263">重新启用客户端访问方法，以便所有者可以访问其邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-263">Re-enabling the client access methods so that the owner can access their mailbox.</span></span>
    
- <span data-ttu-id="a38ef-264">重新应用保留和已删除的 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="a38ef-264">Re-applying the holds and Office 365 retention policies that you removed.</span></span>
    
- <span data-ttu-id="a38ef-265">重新启用托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-265">Re-enabling the Managed Folder Assistant to process the mailbox.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="a38ef-266">我们建议您等待 24 小时后重新应用保持或 Office 365 保留策略 （和验证它是否就地） 重新启用托管文件夹助理处理邮箱之前。</span><span class="sxs-lookup"><span data-stu-id="a38ef-266">We recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant to process the mailbox.</span></span> 
  
<span data-ttu-id="a38ef-267">在 Exchange Online PowerShell 中执行以下步骤 （按指定顺序）。</span><span class="sxs-lookup"><span data-stu-id="a38ef-267">Perform the following steps (in the specified sequence) in Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="a38ef-p140">运行以下命令以更改已删除的邮件保留期限回其原始值。此，假定前面的设置是不超过 30 天。例如 14 天。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p140">Run the following command to change the deleted item retention period back to its original value. This assumes that the previous setting is less than 30 days; for example 14 days.</span></span> 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. <span data-ttu-id="a38ef-270">运行以下命令以重新启用单个项目恢复。</span><span class="sxs-lookup"><span data-stu-id="a38ef-270">Run the following command to re-enable single item recovery.</span></span>
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. <span data-ttu-id="a38ef-271">运行以下命令以重新启用对邮箱的所有客户端访问方法。</span><span class="sxs-lookup"><span data-stu-id="a38ef-271">Run the following command to re-enable all client access methods to the mailbox.</span></span>
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. <span data-ttu-id="a38ef-p141">重新应用您在步骤 3 中删除保留。根据保留项的类型，使用以下过程之一。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p141">Re-apply the holds that you removed in Step 3. Depending on the type of hold, use one of the following procedures.</span></span>
    
    <span data-ttu-id="a38ef-274">**诉讼保留**</span><span class="sxs-lookup"><span data-stu-id="a38ef-274">**Litigation Hold**</span></span>
    
    <span data-ttu-id="a38ef-275">运行以下命令以重新启用邮箱的诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="a38ef-275">Run the following command to re-enable a Litigation Hold for the mailbox.</span></span>
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    <span data-ttu-id="a38ef-276">**In-Place Hold**</span><span class="sxs-lookup"><span data-stu-id="a38ef-276">**In-Place Hold**</span></span>
    
    <span data-ttu-id="a38ef-277">使用 EAC （或 Exchange Online PowerShell） 添加回就地保留的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-277">Use the EAC (or Exchange Online PowerShell) to add the mailbox back to the In-Place Hold.</span></span> 
    
    <span data-ttu-id="a38ef-278">**Office 365 的保留策略应用于特定邮箱**</span><span class="sxs-lookup"><span data-stu-id="a38ef-278">**Office 365 retention policies applied to specific mailboxes**</span></span>
    
    <span data-ttu-id="a38ef-p142">使用安全&amp;合规性中心邮箱将重新添加到 Office 365 保留策略。转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑保留策略，并返回到的收件人的保留策略应用于列表添加邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p142">Use the Security &amp; Compliance Center to add the mailbox back to the Office 365 retention policy. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the retention policy, and add the mailbox back to the list of recipients that the retention policy is applied to.</span></span> 
    
    <span data-ttu-id="a38ef-281">**Office 365 组织范围中的保留策略**</span><span class="sxs-lookup"><span data-stu-id="a38ef-281">**Organization-wide Office 365 retention policies**</span></span>
    
    <span data-ttu-id="a38ef-p143">如果通过排除从策略中删除组织范围内或 Exchange 范围保留策略，然后使用安全&amp;合规性中心以从列表中删除邮箱排除用户。转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑组织范围内保留策略，并从排除收件人列表中删除邮箱。此操作将重新保留策略应用到用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p143">If you removed an organization-wide or Exchange-wide retention policy by excluding it from the policy, then use the Security &amp; Compliance Center to remove the mailbox from the list of excluded users. Go to the **Date governance** \> **Retention** page in the Security &amp; Compliance Center, edit the organization-wide retention policy, and remove the mailbox from the list of excluded recipients. Doing this will re-apply the retention policy to the user's mailbox.</span></span> 
    
    <span data-ttu-id="a38ef-285">**电子数据展示事例包含**</span><span class="sxs-lookup"><span data-stu-id="a38ef-285">**eDiscovery case holds**</span></span>
    
    <span data-ttu-id="a38ef-p144">使用安全&amp;合规性中心添加邮箱备份保留电子数据展示事例与相关联。转到**搜索&amp;调查**\>安全中的**电子数据展示**页&amp;合规中心打开这种情况，并返回到保留项中添加邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p144">Use the Security &amp; Compliance Center to add the mailbox back the hold that's associated with an eDiscovery case. Go to the **Search &amp; investigation** \> **eDiscovery** page in the Security &amp; Compliance Center, open the case, and add the mailbox back to the hold.</span></span> 
    
5. <span data-ttu-id="a38ef-p145">运行以下命令以允许托管文件夹助理再次处理邮箱。如上文所述，我们建议您等待 24 小时后重新应用保持或 Office 365 保留策略 （和验证它是否就地） 重新启用托管文件夹助理之前。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p145">Run the following command to allow the Managed Folder Assistant to process the mailbox again. As previously stated, we recommend that you wait 24 hours after re-applying a hold or Office 365 retention policy (and verifying that it's in place) before you re-enable the Managed Folder Assistant.</span></span> 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. <span data-ttu-id="a38ef-290">若要验证邮箱已被还原回先前的配置，您可以运行以下命令，比较到在步骤 1 中收集的那些设置。</span><span class="sxs-lookup"><span data-stu-id="a38ef-290">To verify that the mailbox has been reverted back to its previous configuration, you can run the following commands and then compare the settings to the ones that you collected in Step 1.</span></span>

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a><span data-ttu-id="a38ef-291">详细信息</span><span class="sxs-lookup"><span data-stu-id="a38ef-291">More information</span></span>

<span data-ttu-id="a38ef-p146">下面是一个表，介绍如何标识不同类型的保留项基于*InPlaceHolds*属性中的值，当您运行**Get-mailbox**或**Get-organizationconfig** cmdlet。如上文所述，必须删除所有保留项和 Office 365 之前邮箱的保留策略可以成功删除可恢复邮件文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p146">Here's a table that describes how to identify different types of holds based on the values in the  *InPlaceHolds*  property when you run the **Get-Mailbox** or **Get-OrganizationConfig** cmdlets. As previously explained, you have to remove all holds and Office 365 retention policies from a mailbox before you can successfully delete items in the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="a38ef-294">**保留类型**</span><span class="sxs-lookup"><span data-stu-id="a38ef-294">**Hold type**</span></span>|<span data-ttu-id="a38ef-295">**示例值**</span><span class="sxs-lookup"><span data-stu-id="a38ef-295">**Example value**</span></span>|<span data-ttu-id="a38ef-296">**如何标识保留项**</span><span class="sxs-lookup"><span data-stu-id="a38ef-296">**How to identify the hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a38ef-297">诉讼保留</span><span class="sxs-lookup"><span data-stu-id="a38ef-297">Litigation Hold</span></span>  <br/> | `True` <br/> |<span data-ttu-id="a38ef-298">*LitigationHoldEnabled*属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="a38ef-298">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="a38ef-299">就地保留</span><span class="sxs-lookup"><span data-stu-id="a38ef-299">In-Place Hold</span></span>  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |<span data-ttu-id="a38ef-p147">*InPlaceHolds*属性将包含邮箱置于就地保留的 GUID。您可以判断这是就地保留因为 GUID 不以前缀开头。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p147">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="a38ef-302">您可以使用 Get-mailboxsearch InPlaceHoldIdentity<hold GUID></span><span class="sxs-lookup"><span data-stu-id="a38ef-302">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="a38ef-303">FL 命令在 Exchange Online PowerShell 中邮箱上获取就地保留的信息。</span><span class="sxs-lookup"><span data-stu-id="a38ef-303">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the mailbox.</span></span>  <br/> |
| <span data-ttu-id="a38ef-304">Office 365 中安全性的保留策略&amp;合规性中心于特定邮箱</span><span class="sxs-lookup"><span data-stu-id="a38ef-304">Office 365 retention policies in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> <span data-ttu-id="a38ef-305">或</span><span class="sxs-lookup"><span data-stu-id="a38ef-305">or</span></span>  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |<span data-ttu-id="a38ef-p148">当您运行**Get-mailbox** cmdlet 时， *InPlaceHolds*属性还包含 Guid 的 Office 365 保留策略应用于邮箱。您可以标识保留策略，因为 GUID 开头`mbx`前缀。请注意，如果保留策略的 GUID 开头`skp`前缀，指示是否保留策略应用于 Skype 业务对话。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p148">When you run the **Get-Mailbox** cmdlet, the  *InPlaceHolds*  property also contains GUIDs of Office 365 retention policies applied to the mailbox. You can identify retention policies because the GUID starts with the  `mbx` prefix. Note that if the GUID of the retention policy starts with the  `skp` prefix, that indicates that the retention policy is applied to Skype for Business conversations.  </span></span><br/> <span data-ttu-id="a38ef-309">到标识 Office 365 应用于邮箱的保留策略，运行以下命令在安全&amp;合规性中心 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a38ef-309">To identity the Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell:</span></span> <br/> <br/><span data-ttu-id="a38ef-310">Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="a38ef-310">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="a38ef-311">FL 名称`<br/><br/>Be sure to remove the  `mbx` or  `skp 前缀当运行此命令。</span><span class="sxs-lookup"><span data-stu-id="a38ef-311">FL Name`<br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="a38ef-312">组织范围内安全中的 Office 365 保留策略&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="a38ef-312">Organization-wide Office 365 retention policies in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="a38ef-313">没有值</span><span class="sxs-lookup"><span data-stu-id="a38ef-313">No value</span></span>  <br/> <span data-ttu-id="a38ef-314">或</span><span class="sxs-lookup"><span data-stu-id="a38ef-314">or</span></span>  <br/>  <span data-ttu-id="a38ef-315">`-mbxe9b52bf7ab3b46a286308ecb29624696`（表示邮箱被排除从组织范围的策略）</span><span class="sxs-lookup"><span data-stu-id="a38ef-315">`-mbxe9b52bf7ab3b46a286308ecb29624696` (indicates that the mailbox is excluded from an organization-wide policy)</span></span>  <br/> |<span data-ttu-id="a38ef-316">即使*InPlaceHolds*属性为空，运行**Get-mailbox** cmdlet 时，可能仍存在一个或多个组织范围内 Office 365 保留策略应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="a38ef-316">Even if the  *InPlaceHolds*  property is empty when you run the **Get-Mailbox** cmdlet, there still might be one or more organization-wide Office 365 retention policies applied to the mailbox.</span></span>  <br/> <span data-ttu-id="a38ef-317">若要验证这一点，您可以运行 Get-organizationconfig</span><span class="sxs-lookup"><span data-stu-id="a38ef-317">To verify this, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="a38ef-318">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="a38ef-318">FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="a38ef-319">FL 名称`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696</span><span class="sxs-lookup"><span data-stu-id="a38ef-319">FL Name`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `-mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696\`</span></span> <br/> |
|<span data-ttu-id="a38ef-320">在安全保留电子数据展示事例&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="a38ef-320">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |<span data-ttu-id="a38ef-p149">*InPlaceHolds*属性还包含与安全中电子数据展示事例关联任何保留项的 GUID&amp;可能置于邮箱的合规性中心。您可以判断这是电子数据展示案例保留，因为 GUID 开头`UniH`前缀。</span><span class="sxs-lookup"><span data-stu-id="a38ef-p149">The  *InPlaceHolds*  property also contains the GUID of any hold associated with an eDiscovery case in the Security &amp; Compliance Center that might be placed on the mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="a38ef-p150">您可以使用`Get-CaseHoldPolicy`cmdlet 中安全&amp;合规性中心 PowerShell，可以获取关于电子数据展示案例与关联邮箱的保留项的信息。例如，可以运行命令 Get CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="a38ef-p150">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="a38ef-325">FL 名称` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`Get ComplianceCase $CaseHold.CaseId</span><span class="sxs-lookup"><span data-stu-id="a38ef-325">FL Name` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="a38ef-326">FL 名称</span><span class="sxs-lookup"><span data-stu-id="a38ef-326">FL Name\`</span></span>


