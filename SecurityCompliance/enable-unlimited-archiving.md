---
title: 在 Office 365 中启用无限制存档-管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '对于管理员: 了解如何在 Office 365 中启用自动扩展存档, 从而为用户提供对其 Exchange Online 邮箱的无限制存储。您可以为整个组织或仅为特定用户启用自动扩展存档。'
ms.openlocfilehash: 96e9fdd4b645df9e52cf9e11c3a43a80ef029ffa
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296025"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="1c7bf-104">在 Office 365 中启用无限制存档-管理员帮助</span><span class="sxs-lookup"><span data-stu-id="1c7bf-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="1c7bf-p102">您可以使用 Office 365 中的 Exchange Online 自动扩展存档功能为存档邮箱启用无限存储空间。启用自动扩展存档后, 会在用户的存档邮箱接近存储限制时自动向其添加额外的存储空间。结果是邮箱存储容量无限制。您可以为组织中的所有人或仅为特定用户启用自动扩展存档。有关自动扩展存档的详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1c7bf-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="1c7bf-110">Before you begin</span></span>

- <span data-ttu-id="1c7bf-p103">您必须是 Office 365 组织中的全局管理员或 Exchange Online 组织中 "组织管理" 角色组的成员, 才能为您的整个组织或特定用户启用自动扩展存档。或者, 您必须是分配有 "邮件收件人" 角色的角色组的成员, 才能为特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="1c7bf-p104">必须先启用用户的存档邮箱, 然后才能启用自动扩展存档。必须为用户分配 Exchange Online 计划2许可证, 才能启用存档邮箱。如果向某个用户分配了 exchange Online 计划1许可证, 则必须为他们分配一个单独的 Exchange online 存档许可证, 以启用其存档邮箱。请参阅[在 Office 365 安全&amp;合规中心中启用存档邮箱](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="1c7bf-p105">您还可以使用 PowerShell 启用存档邮箱。有关可用于为组织中的所有用户启用存档邮箱的 PowerShell 命令示例, 请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="1c7bf-p106">自动扩展存档还支持共享邮箱。若要为共享邮箱启用存档, 需要具有 exchange online 存档许可证的 exchange online 计划2许可证或 exchange online 计划1许可证。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="1c7bf-p107">您不能使用 Exchange 管理中心或安全&amp;合规中心来启用自动扩展存档。您必须使用 Exchange Online PowerShell。若要使用远程 PowerShell 连接到您的 Exchange online 组织, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="1c7bf-124">为您的整个组织启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="1c7bf-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="1c7bf-p108">您可以为您的整个组织启用自动扩展存档。打开该功能后, 将为现有用户邮箱和创建的新用户邮箱启用自动扩展存档。创建新的用户邮箱时, 请务必启用用户的主存档邮箱, 以便自动扩展的存档功能将适用于新用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="1c7bf-128">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1c7bf-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="1c7bf-129">在 Exchange Online PowerShell 中运行以下命令, 为整个组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="1c7bf-130">为特定用户启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="1c7bf-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="1c7bf-p109">不必为组织中的每个用户启用自动扩展存档, 只需为特定用户启用它即可。您可以这样做, 因为只有某些用户可能需要非常大的存档存储空间。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="1c7bf-133">如果为特定用户启用了自动扩展存档, 并为该用户的邮箱保留或分配了 Office 365 保留策略, 则会进行以下两项配置更改:</span><span class="sxs-lookup"><span data-stu-id="1c7bf-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="1c7bf-p110">用户的主存档邮箱的存储配额增加了 10 gb (从 100 gb 增加到 110 gb)。存档警告配额也增加了 10 gb (从 90 gb 增加到 100 gb)。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p110">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB). The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="1c7bf-p111">用户的主邮箱中的 "可恢复的项目" 文件夹的存储配额增加了 10 gb (也是从 100 gb 增加到 110 gb)。可恢复邮件警告配额也增加了 10 gb (从 90 gb 增加到 100 gb)。仅当邮箱处于保留状态或分配到 Office 365 保留策略时, 这些更改才适用。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p111">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB). These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="1c7bf-p112">添加此额外空间是为了防止在设置自动扩展存档之前可能发生的任何存储问题。请注意, 为整个组织启用自动扩展存档时*不会*添加额外的存储空间, 如上一节中所述。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p112">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="1c7bf-141">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1c7bf-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="1c7bf-p113">在 Exchange Online PowerShell 中运行以下命令, 为特定用户启用自动扩展存档。如前所述, 必须先启用用户的存档邮箱 (主存档), 然后才能为该用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p113">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="1c7bf-p114">在 Exchange 混合部署中, 不能使用**AutoExpandingArchive**命令为其主邮箱位于本地的用户启用自动扩展存档, 并为其存档邮箱提供基于云的存档邮箱。若要在 exchange 混合部署中为基于云的存档邮箱启用自动扩展存档, 您必须在 exchange Online PowerShell 中运行**set-organizationconfig-AutoExpandingArchive**命令, 以启用自动扩展存档整个组织。如果用户的主邮箱和存档邮箱都是基于云的邮箱, 则可以使用**AutoExpandingArchive**命令为该特定用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p114">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="1c7bf-147">验证是否已启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="1c7bf-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="1c7bf-148">若要验证是否已为您的组织启用自动扩展存档, 请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="1c7bf-149">值`True`表示已为组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="1c7bf-150">若要验证是否为特定用户启用了自动扩展存档, 请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="1c7bf-151">值`True`表示已为用户启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="1c7bf-152">启用自动扩展存档后, 请牢记以下事项:</span><span class="sxs-lookup"><span data-stu-id="1c7bf-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="1c7bf-p115">如果您运行**set-organizationconfig-AutoExpandingArchive**命令为您的组织启用自动扩展存档, 则无需对各个邮箱运行**启用邮箱-AutoExpandingArchive** 。请注意, 运行**set-organizationconfig** cmdlet 以启用组织的自动扩展存档不会将用户邮箱上的*AutoExpandingArchiveEnabled*属性更改为`True`。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p115">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="1c7bf-p116">同样, 在启用自动扩展存档时, *ArchiveQuota*和*ArchiveWarningQuota*邮箱属性的值不会更改。实际上, 如果为用户邮箱启用自动扩展存档, 并且*AutoExpandingArchiveEnabled*属性设置为`True`, 则只会忽略*ArchiveQuota*和*ArchiveWarningQuota*属性。以下是在为用户邮箱启用自动扩展存档后, 这些邮箱属性的示例。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p116">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![启用自动扩展存档后, ArchiveQuota 和 ArchiveWarningQuota 属性将被忽略](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="1c7bf-159">更多信息</span><span class="sxs-lookup"><span data-stu-id="1c7bf-159">More information</span></span>

- <span data-ttu-id="1c7bf-p117">您还可以使用 PowerShell 启用存档邮箱。例如, 您可以在 Exchange Online PowerShell 中运行以下命令, 为其存档邮箱尚未启用的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p117">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="1c7bf-p118">为您的组织或特定用户启用自动扩展存档后, 当存档邮箱 (包括 "可恢复的项目" 文件夹) 达到 90 GB 时, 存档邮箱将转换为自动扩展存档。最多可能需要30天的时间来设置额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p118">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="1c7bf-164">在打开自动扩展存档后, 将无法关闭该功能。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="1c7bf-p119">对于具有内部部署主邮箱的用户, Exchange 混合部署中的基于云的存档邮箱支持自动扩展存档。但是, 在为基于云的存档邮箱启用自动扩展存档后, 不能将存档邮箱移回内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p119">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="1c7bf-167">有关用户可用于访问其存档邮箱中的其他存储区域中的项目的 outlook 客户端的列表, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的 "访问自动扩展存档中的项目的 Outlook 要求" 一节.</span><span class="sxs-lookup"><span data-stu-id="1c7bf-167">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="1c7bf-p120">如前所述, 运行**AutoExpandingArchive**命令时, 将 10 GB 添加到用户的主存档邮箱的存储配额 (如果邮箱处于保留状态, 则添加到 "可恢复的项目" 文件夹)。这将在预配扩展存储空间 (最多可能需要30天) 之前提供额外的存储空间。当您运行**set-organizationconfig-AutoExpandingArchive**为组织中的所有邮箱启用自动扩展存档时, 将不会添加此额外的存储空间。如果为整个组织启用了自动扩展存档, 但需要为特定用户添加额外的 10 GB 存储空间, 则可以在该邮箱上运行 "**启用-邮箱-AutoExpandingArchive** " 命令。请注意, 您将收到一条错误消息, 指出已启用自动扩展存档, 但额外的存储空间将添加到邮箱中。</span><span class="sxs-lookup"><span data-stu-id="1c7bf-p120">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 
