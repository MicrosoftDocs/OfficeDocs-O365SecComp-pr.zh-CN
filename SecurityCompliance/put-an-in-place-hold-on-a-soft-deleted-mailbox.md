---
title: 将就地保留置于 Exchange Online 中的软删除邮箱上
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。
ms.openlocfilehash: 70feb265e95741406dbf170c6be70bd83b2ec081
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223521"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>将就地保留置于 Exchange Online 中的软删除邮箱上

了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。
  
> [!NOTE]
> 我们已推迟在 Exchange online 中创建新的就地保留的截止时间 (在 Office 365 和 Exchange Online 独立计划中)。但在今年下半年或明年早些时候, 你将无法在 Exchange Online 中创建新的就地保留。作为使用就地保留的替代方法, 您可以在 Office 365 安全&amp;合规中心中使用[电子数据展示案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留策略](https://go.microsoft.com/fwlink/?linkid=827811)。在取消新的就地保留之后, 您仍可以修改现有的就地保留, 并在 exchange Server 2013 中创建新的就地保留, 并且仍支持 exchange 混合部署。而且, 您仍可以将邮箱置于诉讼保留状态。 
  
您可能会遇到这样的情况: 某人已离开您的组织, 并且其相应的用户帐户和邮箱已被删除。随后, 您会发现邮箱中有需要保留的信息。您可以执行什么操作？如果已删除的邮箱保留期尚未过期, 则可以对已删除的邮箱 (称为软删除的邮箱) 设置就地保留, 并使其成为非活动邮箱。*非活动邮箱*用于在离开组织后保留以前的员工的电子邮件。非活动邮箱的内容将保留在软删除邮箱上被置为非活动状态时对其进行就地保留的持续时间。将邮箱设为非活动状态后, 可以使用 Exchange online 中的就地电子数据展示、Office 365 安全&amp;合规中心中的内容搜索或 SharePoint Online 中的电子数据展示中心来搜索邮箱。 
  
> [!NOTE]
> 在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着该邮箱可以在删除后 30 天内进行恢复（或变为非活动邮箱）。30 天后，软删除邮箱将标记为永久删除并且无法恢复或变为非活动邮箱。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须在 Windows PowerShell 中使用**new-mailboxsearch** cmdlet 在软删除的邮箱上放置就地保留。您不能在 SharePoint Online 中使用 Exchange 管理中心 (EAC) 或电子数据展示中心。 
    
- 若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 运行以下命令获取组织中软删除邮箱的标识信息。 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱概述](inactive-mailboxes-in-office-365.md)。
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>将就地保留置于软删除邮箱以使其变为非活动邮箱

使用 **New-MailboxSearch** cmdlet 将软删除邮箱变为非活动邮箱。有关详细信息，请参阅 [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。
  
1. 创建包含软删除邮箱的属性的变量。 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 在上一个命令中, 使用**DistinguishedName**或**ExchangeGuid**属性的值来标识软删除的邮箱。这些属性对于组织中的每个邮箱都是唯一的, 但是, 活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。 
  
2. 创建就地保留并将其置于软删除邮箱上。在此示例中，未指定保留持续时间。这意味着项目将被无限期保留或一直保留到将该保留从非活动邮箱中删除为止。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   还可以在创建就地保留时指定保留持续时间。此示例保留非活动邮箱中的项目近 7 年。
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. 一段时间后，运行下列命令之一，验证软删除邮箱是否为非活动邮箱。
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    或
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>详细信息

在将软删除邮箱变为非活动邮箱后，有多种方法可以管理该邮箱。有关详细信息，请参阅：
  
- [更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [恢复非活动邮箱](recover-an-inactive-mailbox.md)
    
- [还原非活动邮箱](restore-an-inactive-mailbox.md)
    
- [删除非活动邮箱](delete-an-inactive-mailbox.md)(通过删除保留)
