---
title: 启用无限制存档的 Office 365-管理帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 管理员： 了解如何启用自动扩展 Office 365，其 Exchange Online 邮箱的用户提供不受限制的存储的存档。您可以启用自动扩展为整个组织或特定用户的存档。
ms.openlocfilehash: ede3e75a021d750160268ccf06ac4fe1637d219a
ms.sourcegitcommit: 81c2fd5cd940c51bc43ac7858c7bdfa207ce401a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "23809697"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a><span data-ttu-id="c02e7-104">启用无限制存档的 Office 365-管理帮助</span><span class="sxs-lookup"><span data-stu-id="c02e7-104">Enable unlimited archiving in Office 365 - Admin Help</span></span>

<span data-ttu-id="c02e7-p102">可以使用 Office 365 中 Exchange Online 的自动扩展的存档功能，若要启用存档邮箱的不受限制的存储空间。自动扩展存档打开时，额外的存储空间会将自动添加到用户的存档邮箱时该方法的存储限制。结果是无限的邮箱存储容量。您可以打开自动扩展您的组织中的每个人或特定用户的存档。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p102">You can use the Exchange Online auto-expanding archiving feature in Office 365 to enable unlimited storage space for archive mailboxes. When auto-expanding archiving is turned on, additional storage space is automatically added to a user's archive mailbox when it approaches the storage limit. The result is unlimited mailbox storage capacity. You can turn on auto-expanding archiving for everyone in your organization or just for specific users. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c02e7-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="c02e7-110">Before you begin</span></span>

- <span data-ttu-id="c02e7-p103">您必须是在 Office 365 组织或成员的 Exchange Online 组织中的 Organization Management 角色组，若要启用自动扩展为整个组织或特定用户存档的全局管理员。另外，您必须是已分配要自动扩展为用户启用存档特定的 Mail Recipients 角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p103">You have to be a global administrator in your Office 365 organization or a member of the Organization Management role group in your Exchange Online organization to enable auto-expanding archiving for your entire organization or for specific users. Alternately, you have to be a member of a role group that's assigned the Mail Recipients role to enable auto-expanding archiving for specific users.</span></span>
    
- <span data-ttu-id="c02e7-p104">用户的存档邮箱必须在启用之前可以启用自动扩展存档。必须启用存档邮箱的 Exchange Online 计划 2 许可证分配用户。如果为用户分配一个 Exchange Online 计划 1 许可证，您必须将其分配单独 Exchange Online Archiving 的许可证启用存档邮箱。请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p104">A user's archive mailbox has to be enabled before you can enable auto-expanding archiving. A user must be assigned an Exchange Online Plan 2 license to enable the archive mailbox. If a user is assigned an Exchange Online Plan 1 license, you would have to assign them a separate Exchange Online Archiving license to enable their archive mailbox. See [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md).</span></span>
    
- <span data-ttu-id="c02e7-p105">您还可以使用 PowerShell 启用存档邮箱。请参阅有关您可以使用您的组织中的所有用户的存档邮箱启用的 PowerShell 命令的示例的[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p105">You can also use PowerShell to enable archive mailboxes. See the [More information](#more-information) section for an example of the PowerShell command that you can use to enable archive mailboxes for all users in your organization.</span></span> 
    
- <span data-ttu-id="c02e7-p106">自动扩展存档还支持共享的邮箱。若要共享邮箱的存档，请使用 Exchange Online Archiving 的许可证的 Exchange Online 计划 1 许可证或 Exchange Online 计划 2 许可证，则需要。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p106">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>
    
- <span data-ttu-id="c02e7-p107">不能使用 Exchange 管理中心或安全&amp;合规性中心以启用自动扩展存档。您必须使用 Exchange Online PowerShell 中。若要连接到 Exchange Online 组织使用远程 PowerShell，请参阅[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p107">You can't use the Exchange admin center or the Security &amp; Compliance Center to enable auto-expanding archiving. You have to use Exchange Online PowerShell. To connect to your Exchange Online organization using remote PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a><span data-ttu-id="c02e7-124">启用自动扩展为整个组织存档</span><span class="sxs-lookup"><span data-stu-id="c02e7-124">Enable auto-expanding archiving for your entire organization</span></span>

<span data-ttu-id="c02e7-p108">您可以启用自动扩展您的整个组织的存档。您将其打开后，自动扩展存档将启用的现有用户邮箱和创建的新用户邮箱。当您创建新用户邮箱时，请务必以便自动扩展的存档功能将工作为新用户邮箱启用用户的主存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p108">You can enable auto-expanding archiving for your entire organization. After you turn it on, auto-expanding archiving will be enabled for existing user mailboxes and for new user mailboxes that are created. When you create new user mailboxes, be sure to enable the user's main archive mailbox so the auto-expanding archiving feature will work for the new user mailbox.</span></span>
  
1. [<span data-ttu-id="c02e7-128">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c02e7-128">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="c02e7-129">在 Exchange Online PowerShell 中启用自动扩展您的整个组织的存档中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c02e7-129">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for your entire organization.</span></span>

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a><span data-ttu-id="c02e7-130">自动扩展为用户启用存档特定</span><span class="sxs-lookup"><span data-stu-id="c02e7-130">Enable auto-expanding archiving for specific users</span></span>

<span data-ttu-id="c02e7-p109">而非启用自动扩展您的组织中的每个用户的存档，您可以只启用它为特定用户。因为只有某些用户可能非常大的存档存储需要，您可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p109">Instead of enabling auto-expanding archiving for every user in your organization, you can just enable it for specific users. You might do this because only some users might have a need for a very large archive storage.</span></span>
  
<span data-ttu-id="c02e7-133">当您启用自动扩展特定用户的存档和上的用户的邮箱中保留或分配给 Office 365 保留策略，进行以下两种配置更改：</span><span class="sxs-lookup"><span data-stu-id="c02e7-133">When you enable auto-expanding archiving for a specific user and the user's mailbox in on hold or assigned to an Office 365 retention policy, the following two configurations changes are made:</span></span>
  
- <span data-ttu-id="c02e7-p110">用户的主存档邮箱的存储配额增加了 10 GB （从为 110 GB 的 100 GB)。存档警告配额还增加了 10 GB （从为 100 GB 的 90 GB)。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p110">The storage quota for the user's primary archive mailbox is increased by 10 GB (from 100 GB to 110 GB). The archive warning quota is also increased by 10 GB (from 90 GB to 100 GB).</span></span>
    
- <span data-ttu-id="c02e7-p111">用户的主邮箱中可恢复邮件文件夹的存储配额增加了 10 GB （还从为 110 GB 的 100 GB)。可恢复的项目警告配额还增加了 10 GB （从为 100 GB 的 90 GB)。只有上的邮箱中保留或分配给 Office 365 保留策略，这些更改才适用。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p111">The storage quota for the Recoverable Items folder in the user's primary mailbox is increased by 10 GB (also from 100 GB to 110 GB). The Recoverable Items warning quota is also increased by 10 GB (from 90 GB to 100 GB). These changes are applicable only if the mailbox in on hold or assigned to an Office 365 retention policy.</span></span>
    
<span data-ttu-id="c02e7-p112">添加此附加的空间以防止设置自动扩展存档之前，可能出现的任何存储问题。请注意的其他存储空间*不*添加启用自动扩展为整个组织上, 一节中所述存档时。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p112">This additional space is added to prevent any storage issues that may occur before the auto-expanding archive is provisioned. Note that additional storage space  *is not*  added when you enable auto-expanding archiving for your entire organization, as described in the previous section.</span></span> 
  
1. [<span data-ttu-id="c02e7-141">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c02e7-141">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. <span data-ttu-id="c02e7-p113">若要启用自动扩展存档特定用户的 Exchange Online PowerShell 中运行以下命令。如前所述，您也可以展开该用户的存档之前，必须启用用户的存档邮箱 （主存档）。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p113">Run the following command in Exchange Online PowerShell to enable auto-expanding archiving for a specific user. As previously explained, the user's archive mailbox (main archive) must be enabled before you can turn on auto-expanding archiving for that user.</span></span>
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> <span data-ttu-id="c02e7-p114">在 Exchange 混合部署中，您无法使用**Enable-mailbox AutoExpandingArchive**命令启用自动扩展存档特定主邮箱在本地用户和其存档邮箱是基于云的。若要启用自动扩展 Exchange 混合部署中的基于云的存档邮箱的存档，您必须运行**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell，可以启用自动扩展的存档整个组织中。如果存档邮箱都基于云的用户的主，然后可以使用**Enable-mailbox AutoExpandingArchive**命令来启用自动扩展的特定用户的存档。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p114">In an Exchange hybrid deployment, you can't use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for specific a user whose primary mailbox is on premises and their archive mailbox is cloud-based. To enable auto-expanding archiving for cloud-based archive mailboxes in an Exchange hybrid deployment, you have to run the **Set-OrganizationConfig -AutoExpandingArchive** command in Exchange Online PowerShell to enable auto-expanding archiving for the entire organization. If a user's primary and archive mailboxes are both cloud-based, then you can use the **Enable-Mailbox -AutoExpandingArchive** command to enable auto-expanding archiving for that specific user.</span></span> 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a><span data-ttu-id="c02e7-147">验证已启用自动扩展存档</span><span class="sxs-lookup"><span data-stu-id="c02e7-147">Verify that auto-expanding archiving is enabled</span></span>

<span data-ttu-id="c02e7-148">若要验证已为组织启用自动扩展存档，请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c02e7-148">To verify that auto-expanding archiving is enabled for your organization, run the following command in Exchange Online PowerShell.</span></span>

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

<span data-ttu-id="c02e7-149">值为`True`表示已为组织启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c02e7-149">A value of  `True` indicates that auto-expanding archiving is enabled for the organization.</span></span> 
  
<span data-ttu-id="c02e7-150">若要验证自动扩展存档是启用为某个特定用户，请在 Exchange Online PowerShell 中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="c02e7-150">To verify that auto-expanding archiving is enable for a specific user, run the following command in Exchange Online PowerShell.</span></span>
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
<span data-ttu-id="c02e7-151">值为`True`指示用户是否已启用自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="c02e7-151">A value of  `True` indicates that auto-expanding archiving is enabled for the user.</span></span> 
  
<span data-ttu-id="c02e7-152">启用自动扩展存档后，请牢记以下几点：</span><span class="sxs-lookup"><span data-stu-id="c02e7-152">Keep the following things in mind after you enable auto-expanding archiving:</span></span>
  
- <span data-ttu-id="c02e7-p115">如果您运行**Set-organizationconfig AutoExpandingArchive**命令以启用自动扩展您的组织的存档，您无需运行对单个邮箱**启用邮箱 AutoExpandingArchive** 。请注意该运行**Set-organizationconfig** cmdlet 启用自动扩展存档的组织不更改用户邮箱迁移到的*AutoExpandingArchiveEnabled*属性`True`。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p115">If you run the **Set-OrganizationConfig -AutoExpandingArchive** command to enable auto-expanding archiving for your organization, you don't have to run the **Enable-Mailbox -AutoExpandingArchive** on individual mailboxes. Note that running the **Set-OrganizationConfig** cmdlet to enable auto-expanding archiving for your organization doesn't change the  *AutoExpandingArchiveEnabled*  property on user mailboxes to  `True`.</span></span>
    
- <span data-ttu-id="c02e7-p116">类似地，当启用自动扩展存档时，不会改变*ArchiveQuota*和*ArchiveWarningQuota*邮箱属性的值。实际上，当您启用自动扩展存档的用户邮箱并*AutoExpandingArchiveEnabled*属性设置为`True`的*ArchiveQuota*和*ArchiveWarningQuota*属性只需将被忽略。自动扩展存档启用的用户的邮箱后，下面是这些邮箱属性的示例。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p116">Similarly, the values for the  *ArchiveQuota*  and  *ArchiveWarningQuota*  mailbox properties aren't changed when you enable auto-expanding archiving. In fact, when you enable auto-expanding archiving for a user mailbox and the  *AutoExpandingArchiveEnabled*  property is set to  `True`, the  *ArchiveQuota*  and  *ArchiveWarningQuota*  properties are just ignored. Here's an example of these mailbox properties after auto-expanding archiving is enabled for a user's mailbox.</span></span> 
    
    ![启用自动扩展存档后，将被忽略 ArchiveQuota 和 ArchiveWarningQuota 属性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a><span data-ttu-id="c02e7-159">详细信息</span><span class="sxs-lookup"><span data-stu-id="c02e7-159">More information</span></span>

- <span data-ttu-id="c02e7-p117">您还可以使用 PowerShell 启用存档邮箱。例如，您可以运行以下命令在 Exchange Online PowerShell，可以启用所有用户尚未启用存档邮箱的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p117">You can also use PowerShell to enable archive mailboxes. For example, you can run the following command in Exchange Online PowerShell to enable archive mailboxes for all users whose archive mailbox isn't already enabled.</span></span>

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- <span data-ttu-id="c02e7-p118">打开自动扩展归档您的组织或特定用户后，存档邮箱转换为自动扩展存档 （包括可恢复邮件文件夹） 的存档邮箱达到 90 GB 时。可能需要额外的存储空间设置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p118">After you turn on auto-expanding archiving for your organization or for a specific user, an archive mailbox is converted to an auto-expanding archive when the archive mailbox (including the Recoverable Items folder) reaches 90 GB. It can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
- <span data-ttu-id="c02e7-164">打开自动扩展存档后，就无法关闭。</span><span class="sxs-lookup"><span data-stu-id="c02e7-164">After you turn on auto-expanding archiving, it can't be turned off.</span></span>
    
- <span data-ttu-id="c02e7-p119">自动扩展存档支持 Exchange 混合部署的用户具有本地主邮箱中的基于云的存档邮箱。但是，自动扩展存档的基于云的存档邮箱启用后，您无法关闭板回内部部署 Exchange 组织的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p119">Auto-expanding archiving is supported for cloud-based archive mailboxes in an Exchange hybrid deployment for users who have an on-premises primary mailbox. However, after auto-expanding archiving is enabled for a cloud-based archive mailbox, you can't off-board that archive mailbox back to the on-premises Exchange organization.</span></span>
    
- <span data-ttu-id="c02e7-167">Outlook 客户端，用户可以用来访问其存档邮箱中的其他存储区中的项的列表，请参阅[Office 365 中的不受限制概述 archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的"用于访问自动扩展存档中的项目的 Outlook 要求"部分.</span><span class="sxs-lookup"><span data-stu-id="c02e7-167">For a list of Outlook clients that users can use to access items in the additional storage area in their archive mailbox, see the "Outlook requirements for accessing items in an auto-expanded archive" section in [Overview of unlimited archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).</span></span>
    
- <span data-ttu-id="c02e7-p120">如前面所述，10 GB 添加到用户的主存档邮箱的存储配额 （和到可恢复邮件文件夹上邮箱时保留） 运行时**Enable-mailbox AutoExpandingArchive**命令。这提供了额外的存储，直到自动扩展存储空间设置 （这可能需要长达 30 天）。当您运行**Set-organizationconfig AutoExpandingArchive**要启用自动扩展您的组织中所有邮箱存档时，不会添加此额外的存储空间。如果您启用自动扩展为整个组织，存档，但需要添加其他 10 GB 的存储空间为某个特定用户，您可以在该邮箱上运行**Enable-mailbox AutoExpandingArchive**命令。请注意，您将收到错误消息已启用自动扩展存档，但额外的存储空间将添加到邮箱。</span><span class="sxs-lookup"><span data-stu-id="c02e7-p120">As previously explained, 10 GB is added to the storage quota of the user's primary archive mailbox (and to the Recoverable Items folder if the mailbox is on hold) when you run the **Enable-Mailbox -AutoExpandingArchive** command. This provides additional storage until the auto-expanded storage space is provisioned (which can take up to 30 days). This additional storage space isn't added when you run the **Set-OrganizationConfig -AutoExpandingArchive** to enable auto-expanding archiving for all mailboxes in your organization. If you enabled auto-expanding archiving for the entire organization, but need to add the additional 10 GB of storage space for a specific user, you can run the **Enable-Mailbox -AutoExpandingArchive** command on that mailbox. Note that you will receive an error saying that auto-expanding archiving has already been enabled, but the additional storage space will be added to the mailbox.</span></span> 
