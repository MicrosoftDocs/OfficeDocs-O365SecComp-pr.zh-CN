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
ms.openlocfilehash: 6dd49433a1692d3a0ba23af57e7e2d9544f8a2b1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524822"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>启用无限制存档的 Office 365-管理帮助

可以使用 Office 365 中 Exchange Online 的自动扩展的存档功能，若要启用存档邮箱的不受限制的存储空间。自动扩展存档打开时，额外的存储空间会将自动添加到用户的存档邮箱时该方法的存储限制。结果是无限的邮箱存储容量。您可以打开自动扩展您的组织中的每个人或特定用户的存档。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。

## <a name="before-you-begin"></a>准备工作

- 您必须是在 Office 365 组织或成员的 Exchange Online 组织中的 Organization Management 角色组，若要启用自动扩展为整个组织或特定用户存档的全局管理员。另外，您必须是已分配要自动扩展为用户启用存档特定的 Mail Recipients 角色的角色组的成员。
    
- 用户的存档邮箱必须在启用之前可以启用自动扩展存档。必须启用存档邮箱的 Exchange Online 计划 2 许可证分配用户。如果为用户分配一个 Exchange Online 计划 1 许可证，您必须将其分配单独 Exchange Online Archiving 的许可证启用存档邮箱。请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)。
    
- 您还可以使用 PowerShell 启用存档邮箱。请参阅有关您可以使用您的组织中的所有用户的存档邮箱启用的 PowerShell 命令的示例的[详细信息](#more-information)部分。 
    
- 自动扩展存档还支持共享的邮箱。若要共享邮箱的存档，请使用 Exchange Online Archiving 的许可证的 Exchange Online 计划 1 许可证或 Exchange Online 计划 2 许可证，则需要。
    
- 不能使用 Exchange 管理中心或安全&amp;合规性中心以启用自动扩展存档。您必须使用 Exchange Online PowerShell 中。若要连接到 Exchange Online 组织使用远程 PowerShell，请参阅[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>启用自动扩展为整个组织存档

您可以启用自动扩展您的整个组织的存档。您将其打开后，自动扩展存档将启用的现有用户邮箱和创建的新用户邮箱。当您创建新用户邮箱时，请务必以便自动扩展的存档功能将工作为新用户邮箱启用用户的主存档邮箱。
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 在 Exchange Online PowerShell 中启用自动扩展您的整个组织的存档中运行以下命令。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>自动扩展为用户启用存档特定

而非启用自动扩展您的组织中的每个用户的存档，您可以只启用它为特定用户。因为只有某些用户可能非常大的存档存储需要，您可能需要执行此操作。
  
当启用自动扩展存档特定用户时，还进行以下两种配置更改：
  
- 用户的主存档邮箱的存储配额增加了 10 GB （从为 110 GB 的 100 GB)。
    
- 用户的主邮箱中可恢复邮件文件夹的存储配额增加了 10 GB （还从为 110 GB 的 100 GB)。仅适用于上的邮箱中保留此更改。
    
添加此附加的空间以防止设置自动扩展存档之前，可能出现的任何存储问题。请注意的其他存储空间*不*添加启用自动扩展为整个组织上, 一节中所述存档时。 
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 若要启用自动扩展存档特定用户的 Exchange Online PowerShell 中运行以下命令。如前所述，您也可以展开该用户的存档之前，必须启用用户的存档邮箱 （主存档）。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> 在 Exchange 混合部署中，您无法使用**Enable-mailbox AutoExpandingArchive**命令启用自动扩展存档特定主邮箱在本地用户和其存档邮箱是基于云的。若要启用自动扩展 Exchange 混合部署中的基于云的存档邮箱的存档，您必须运行**Set-organizationconfig AutoExpandingArchive**命令在 Exchange Online PowerShell，可以启用自动扩展的存档整个组织中。如果存档邮箱都基于云的用户的主，然后可以使用**Enable-mailbox AutoExpandingArchive**命令来启用自动扩展的特定用户的存档。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>验证已启用自动扩展存档

若要验证已为组织启用自动扩展存档，请在 Exchange Online PowerShell 中运行以下命令。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

值为`True`表示已为组织启用自动扩展存档。 
  
若要验证自动扩展存档是启用为某个特定用户，请在 Exchange Online PowerShell 中运行以下命令。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
值为`True`指示用户是否已启用自动扩展存档。 
  
启用自动扩展存档后，请牢记以下几点：
  
- 如果您运行**Set-organizationconfig AutoExpandingArchive**命令以启用自动扩展您的组织的存档，您无需运行对单个邮箱**启用邮箱 AutoExpandingArchive** 。请注意该运行**Set-organizationconfig** cmdlet 启用自动扩展存档的组织不更改用户邮箱迁移到的*AutoExpandingArchiveEnabled*属性`True`。
    
- 类似地，当启用自动扩展存档时，不会改变*ArchiveQuota*和*ArchiveWarningQuota*邮箱属性的值。实际上，当您启用自动扩展存档的用户邮箱并*AutoExpandingArchiveEnabled*属性设置为`True`的*ArchiveQuota*和*ArchiveWarningQuota*属性只需将被忽略。自动扩展存档启用的用户的邮箱后，下面是这些邮箱属性的示例。 
    
    ![启用自动扩展存档后，将被忽略 ArchiveQuota 和 ArchiveWarningQuota 属性](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>详细信息

- 您还可以使用 PowerShell 启用存档邮箱。例如，您可以运行以下命令在 Exchange Online PowerShell，可以启用所有用户尚未启用存档邮箱的存档邮箱。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 打开自动扩展归档您的组织或特定用户后，存档邮箱转换为自动扩展存档 （包括可恢复邮件文件夹） 的存档邮箱达到 90 GB 时。可能需要额外的存储空间设置为最多 30 天。
    
- 打开自动扩展存档后，就无法关闭。
    
- 自动扩展存档支持 Exchange 混合部署的用户具有本地主邮箱中的基于云的存档邮箱。但是，自动扩展存档的基于云的存档邮箱启用后，您无法关闭板回内部部署 Exchange 组织的存档邮箱。
    
- Outlook 客户端，用户可以用来访问其存档邮箱中的其他存储区中的项的列表，请参阅[Office 365 中的不受限制概述 archiving](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)中的"用于访问自动扩展存档中的项目的 Outlook 要求"部分.
    
- 如前面所述，10 GB 添加到用户的主存档邮箱的存储配额 （和到可恢复邮件文件夹上邮箱时保留） 运行时**Enable-mailbox AutoExpandingArchive**命令。这提供了额外的存储，直到自动扩展存储空间设置 （这可能需要长达 30 天）。当您运行**Set-organizationconfig AutoExpandingArchive**要启用自动扩展您的组织中所有邮箱存档时，不会添加此额外的存储空间。如果您启用自动扩展为整个组织，存档，但需要添加其他 10 GB 的存储空间为某个特定用户，您可以在该邮箱上运行**Enable-mailbox AutoExpandingArchive**命令。请注意，您将收到错误消息已启用自动扩展存档，但额外的存储空间将添加到邮箱。 
