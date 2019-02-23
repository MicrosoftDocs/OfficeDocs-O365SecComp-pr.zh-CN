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
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '对于管理员: 了解如何在 Office 365 中启用自动扩展存档, 从而为用户提供对其 Exchange Online 邮箱的无限制存储。您可以为整个组织或仅为特定用户启用自动扩展存档。'
ms.openlocfilehash: 39098ffc78d0379436cafb20e5a484ec0e7aa283
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215392"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>在 Office 365 中启用无限制存档-管理员帮助

您可以使用 Office 365 中的 Exchange Online 自动扩展存档功能为存档邮箱启用无限存储空间。启用自动扩展存档后, 会在用户的存档邮箱接近存储限制时自动向其添加额外的存储空间。结果是邮箱存储容量无限制。您可以为组织中的所有人或仅为特定用户启用自动扩展存档。有关自动扩展存档的详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。

## <a name="before-you-begin"></a>准备工作

- 您必须是 Office 365 组织中的全局管理员或 Exchange Online 组织中 "组织管理" 角色组的成员, 才能为您的整个组织或特定用户启用自动扩展存档。或者, 您必须是分配有 "邮件收件人" 角色的角色组的成员, 才能为特定用户启用自动扩展存档。
    
- 必须先启用用户的存档邮箱, 然后才能启用自动扩展存档。必须为用户分配 Exchange Online 计划2许可证, 才能启用存档邮箱。如果向某个用户分配了 exchange Online 计划1许可证, 则必须为他们分配一个单独的 Exchange online 存档许可证, 以启用其存档邮箱。请参阅[在 Office 365 安全&amp;合规中心中启用存档邮箱](enable-archive-mailboxes.md)。
    
- 您还可以使用 PowerShell 启用存档邮箱。有关可用于为组织中的所有用户启用存档邮箱的 PowerShell 命令示例, 请参阅[详细信息](#more-information)部分。 
    
- 自动扩展存档还支持共享邮箱。若要为共享邮箱启用存档, 需要具有 exchange online 存档许可证的 exchange online 计划2许可证或 exchange online 计划1许可证。
    
- 您不能使用 Exchange 管理中心或安全&amp;合规中心来启用自动扩展存档。您必须使用 Exchange Online PowerShell。若要使用远程 PowerShell 连接到您的 Exchange online 组织, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>为您的整个组织启用自动扩展存档

您可以为您的整个组织启用自动扩展存档。打开该功能后, 将为现有用户邮箱和创建的新用户邮箱启用自动扩展存档。创建新的用户邮箱时, 请务必启用用户的主存档邮箱, 以便自动扩展的存档功能将适用于新用户邮箱。
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 在 Exchange Online PowerShell 中运行以下命令, 为整个组织启用自动扩展存档。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>为特定用户启用自动扩展存档

不必为组织中的每个用户启用自动扩展存档, 只需为特定用户启用它即可。您可以这样做, 因为只有某些用户可能需要非常大的存档存储空间。
  
如果为特定用户启用了自动扩展存档, 并为该用户的邮箱保留或分配了 Office 365 保留策略, 则会进行以下两项配置更改:
  
- 用户的主存档邮箱的存储配额增加了 10 gb (从 100 gb 增加到 110 gb)。存档警告配额也增加了 10 gb (从 90 gb 增加到 100 gb)。
    
- 用户的主邮箱中的 "可恢复的项目" 文件夹的存储配额增加了 10 gb (也是从 100 gb 增加到 110 gb)。可恢复邮件警告配额也增加了 10 gb (从 90 gb 增加到 100 gb)。仅当邮箱处于保留状态或分配到 Office 365 保留策略时, 这些更改才适用。
    
添加此额外空间是为了防止在设置自动扩展存档之前可能发生的任何存储问题。请注意, 为整个组织启用自动扩展存档时*不会*添加额外的存储空间, 如上一节中所述。 
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 在 Exchange Online PowerShell 中运行以下命令, 为特定用户启用自动扩展存档。如前所述, 必须先启用用户的存档邮箱 (主存档), 然后才能为该用户启用自动扩展存档。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> 在 Exchange 混合部署中, 不能使用**AutoExpandingArchive**命令为其主邮箱位于本地的用户启用自动扩展存档, 并为其存档邮箱提供基于云的存档邮箱。若要在 exchange 混合部署中为基于云的存档邮箱启用自动扩展存档, 您必须在 exchange Online PowerShell 中运行**set-organizationconfig-AutoExpandingArchive**命令, 以启用自动扩展存档整个组织。如果用户的主邮箱和存档邮箱都是基于云的邮箱, 则可以使用**AutoExpandingArchive**命令为该特定用户启用自动扩展存档。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>验证是否已启用自动扩展存档

若要验证是否已为您的组织启用自动扩展存档, 请在 Exchange Online PowerShell 中运行以下命令。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

值`True`表示已为组织启用自动扩展存档。 
  
若要验证是否为特定用户启用了自动扩展存档, 请在 Exchange Online PowerShell 中运行以下命令。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
值`True`表示已为用户启用自动扩展存档。 
  
启用自动扩展存档后, 请牢记以下事项:
  
- 如果您运行**set-organizationconfig-AutoExpandingArchive**命令为您的组织启用自动扩展存档, 则无需对各个邮箱运行**启用邮箱-AutoExpandingArchive** 。请注意, 运行**set-organizationconfig** cmdlet 以启用组织的自动扩展存档不会将用户邮箱上的*AutoExpandingArchiveEnabled*属性更改为`True`。
    
- 同样, 在启用自动扩展存档时, *ArchiveQuota*和*ArchiveWarningQuota*邮箱属性的值不会更改。实际上, 如果为用户邮箱启用自动扩展存档, 并且*AutoExpandingArchiveEnabled*属性设置为`True`, 则只会忽略*ArchiveQuota*和*ArchiveWarningQuota*属性。以下是在为用户邮箱启用自动扩展存档后, 这些邮箱属性的示例。 
    
    ![启用自动扩展存档后, ArchiveQuota 和 ArchiveWarningQuota 属性将被忽略](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>更多信息

- 您还可以使用 PowerShell 启用存档邮箱。例如, 您可以在 Exchange Online PowerShell 中运行以下命令, 为其存档邮箱尚未启用的所有用户启用存档邮箱。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 为您的组织或特定用户启用自动扩展存档后, 当存档邮箱 (包括 "可恢复的项目" 文件夹) 达到 90 GB 时, 存档邮箱将转换为自动扩展存档。最多可能需要30天的时间来设置额外的存储空间。
    
- 在打开自动扩展存档后, 将无法关闭该功能。
    
- 对于具有内部部署主邮箱的用户, Exchange 混合部署中的基于云的存档邮箱支持自动扩展存档。但是, 在为基于云的存档邮箱启用自动扩展存档后, 不能将存档邮箱移回内部部署 Exchange 组织。
    
- 有关用户可用于访问其存档邮箱中的其他存储区域中的项目的 outlook 客户端的列表, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的 "访问自动扩展存档中的项目的 Outlook 要求" 一节.
    
- 如前所述, 运行**AutoExpandingArchive**命令时, 将 10 GB 添加到用户的主存档邮箱的存储配额 (如果邮箱处于保留状态, 则添加到 "可恢复的项目" 文件夹)。这将在预配扩展存储空间 (最多可能需要30天) 之前提供额外的存储空间。当您运行**set-organizationconfig-AutoExpandingArchive**为组织中的所有邮箱启用自动扩展存档时, 将不会添加此额外的存储空间。如果为整个组织启用了自动扩展存档, 但需要为特定用户添加额外的 10 GB 存储空间, 则可以在该邮箱上运行 "**启用-邮箱-AutoExpandingArchive** " 命令。请注意, 您将收到一条错误消息, 指出已启用自动扩展存档, 但额外的存储空间将添加到邮箱中。 
