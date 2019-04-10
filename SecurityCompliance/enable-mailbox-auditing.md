---
title: 管理邮箱审核
ms.author: chrisda
author: chrisda
manager: serdars
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 默认情况下, 邮箱审核日志记录在 Microsoft 365 (也称为默认邮箱审核或邮箱审核) 中处于打开状态。 这意味着邮箱所有者、代理人和管理员执行的某些操作将自动记录在邮箱审核日志中, 在此日志中可以搜索在邮箱上执行的活动。
ms.openlocfilehash: 38632798aedfa34ee7568a7038d5ff906888619c
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745314"
---
# <a name="manage-mailbox-auditing"></a>管理邮箱审核
  
从2019年1月起, microsoft 将默认为所有 Microsoft 365 组织启用邮箱审核日志记录。 这意味着邮箱所有者、代理人和管理员执行的某些操作将会自动记录, 并且在邮箱审核日志中搜索相应的邮箱审核记录时, 将会提供相应的邮箱审核记录。 默认情况下, 邮箱审核启用前, 您必须为组织中的每个用户邮箱手动启用它。 

以下是邮箱审核在默认情况下的一些优点:

- 创建新邮箱时, 默认情况下将启用审核。 您无需为新用户手动启用它。 

- 您将不会管理已审核的邮箱操作。 默认情况下, 会为每种类型的登录审核一组已定义的邮箱操作。 这些[登录类型](#mailbox-actions-logged-by-default)为 "所有者"、"代理" 和 "管理员"。

- 默认情况下, 将审核由 Microsoft 发布的新邮箱操作。 当 Microsoft 发布新邮箱操作 (尤其是帮助保护组织并帮助进行法庭调查) 时, 会自动将其添加到默认情况下审核的邮箱操作列表中。 这意味着您无需向所有者、代理人或管理员执行的邮箱操作列表中添加新的操作。 

- 确保您正在审核对所有邮箱的相同操作, 以便您在整个组织中拥有一致的邮箱审核策略。

> [!TIP]
> 需要注意的重要一点是, 在默认情况下, 在上一次发布邮箱审核, 您不必执行任何操作来管理邮箱审核。 但是, 如果您想要了解详细信息, 请更改默认设置中的行为, 或将其全部关闭, 本文可帮助您解决此问题。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>默认情况下验证邮箱审核启用

若要验证您的组织的默认邮箱审核是否已启用, 请在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行以下命令:

```
Get-OrganizationConfig | FL AuditDisabled
``` 

**如果值为 False** , 则表示已为您的组织启用默认邮箱审核。 

默认情况下邮箱审核启用时 (当*AuditDisabled*属性设置为**False**时), 组织设置将覆盖特定邮箱的邮箱审核设置。 例如, 如果邮箱的*AuditEnabled*属性设置为**False**, 但对组织启用了默认邮箱审核, 则会为该邮箱审核默认邮箱操作。 如果为特定邮箱显式禁用了邮箱审核, 而您仍希望禁用邮箱审核, 则可以为邮箱所有者和已委派邮箱访问权限的其他用户设置邮箱审核旁路。 有关详细信息, 请参阅本文中的[绕过邮箱审核日志记录](#bypass-mailbox-audit-logging)一节。

> [!NOTE]
> 默认情况下, 邮箱审核处于打开状态时, 如果当前设置为**False**, 则邮箱的*AuditEnabled*属性不会更改为**True** 。 换句话说, 默认情况下邮箱审核将忽略邮箱的*AuditEnabled*属性。

## <a name="supported-mailbox-types"></a>支持的邮箱类型

下表显示了默认情况下邮箱审核当前支持的邮箱类型:

|邮箱类型|支持|不支持|
|:---------|:---------:|:---------:|
|用户邮箱    |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       |         |
|共享邮箱    |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |       |
|Office 365 组邮箱    |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)         |         |
|资源邮箱    |      |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)        |
|公用文件夹邮箱    |       |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)  |
||||

## <a name="mailbox-actions-logged-by-default"></a>默认情况下记录的邮箱操作

默认情况下, 会为以下每种登录类型记录一组邮箱操作:  

   - **Owner** -邮箱所有者。 
   
   - **Delegate** -向某人的邮箱分配了 SendAs、SendOnBehalf 或 FullAccess 权限的另一个用户。 请注意, 被分配到用户邮箱的 FullAccess 权限的管理员也被视为代理用户。
   
    - 仅在以下情况下, 管理员才认为管理员登录类型会访问**管理员**邮箱:
    
       - 使用以下其中一种 Microsoft 电子数据展示工具搜索邮箱时: 

         - 合规性中心中的内容搜索。
       
         -  合规中心中的电子数据展示或高级电子数据展示。
       
         - Exchange Online 中的就地电子数据展示。
       - 当使用[Microsoft Exchange Server MAPI 编辑器](https://go.microsoft.com/fwlink/p/?linkId=204086)访问邮箱时。     

下表列出了默认情况下针对每个登录类型的当前记录的邮箱操作。

|管理操作|委派操作|所有者操作|
|:---------|:---------|:---------|
|创建    |创建       | HardDelete        |
|HardDelete    |HardDelete        |MoveToDeletedItems       |
|MoveToDeletedItems    |MoveToDeletedItems         |SoftDelete         |
|SendAs    |SendAs      |    更新     |
|SendOnBehalf    |SendOnBehalf       |UpdateCalendarDelegation        |
|SoftDelete     |SoftDelete      | UpdateFolderPermissions        |
|更新    |更新       |UpdateInboxRules         |
|UpdateCalendarDelegation    | UpdateFolderPermissions        |         |
|UpdateFolderPermissions     | UpdateInboxRules        |         |
|UpdateInboxRules     |         |         |
||||

以下是这些邮箱操作的说明。 

|邮箱操作|描述|
|:---------|:---------|
|**创建** <br/> |项目是在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建的;例如, 创建一个新的会议请求。 请注意, 不会审核创建、发送或接收邮件。 此外, 还不会审核创建邮箱文件夹的情况。  <br/> |
|**HardDelete** <br/> |已将某个邮件从"已恢复邮件"文件夹中清除。  <br/> |
|**MoveToDeletedItems** <br/> |邮件已被删除并移动到 "已删除邮件" 文件夹。  <br/> |
|**SendAs** <br/> |邮件是使用 SendAs 权限发送的。 这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。  <br/> |
|**SendOnBehalf** <br/> |邮件是使用 SendOnBehalf 权限发送的。 这表示另一个用户代表邮箱所有者发送了邮件。 该邮件指示收件人代表发送邮件的收件人和实际发送邮件的收件人。  <br/> |
|**SoftDelete** <br/> |邮件已从 "已删除邮件" 文件夹中永久删除或删除。 软删除的项目将移动到 "可恢复的项目" 文件夹中。  <br/> |
|**更新** <br/> |更改了邮件或其属性。  <br/> |
|**UpdateCalendarDelegation** <br/> |向邮箱分配了日历委派。 日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。  <br/> |
|**UpdateFolderPermissions** <br/> |更改了文件夹权限。 文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。  <br/> |
|**UpdateInboxRules** <br/> |添加、删除或更改了收件箱规则。 "收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。  <br/> |
|||

有关邮箱操作的完整列表, 包括可用但不包含在一组默认操作中的操作, 请参阅本文中的[邮箱审核操作](#mailbox-auditing-actions)一节。

> [!IMPORTANT]
> 如果您已将邮箱操作明确配置为在邮箱审核启用前对任何登录类型进行审核, 则邮箱的现有配置将优先, 且不会被默认邮箱覆盖本节中介绍的操作。 如果您想要还原为默认邮箱操作, 您可以通过运行 "**设置邮箱-DefaultAuditSet** " 命令来执行此操作。 有关执行此操作的详细信息, 请参阅本文中的[还原默认邮箱操作](#restore-the-default-mailbox-actions)一节。

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>验证是否为每个登录类型记录了默认邮箱操作

在上发布邮箱审核时, 默认情况下已添加名为 " *DefaultAuditSet* " 的新邮箱属性。 此属性指示是否为指定邮箱的每个登录类型审核默认邮箱操作 (由 Microsoft 管理)。 您可以运行以下命令来显示此属性的值:

```
Get-Mailbox <username> | FL DefaultAuditSet
```

值`Admin, Delegate, Owner`表示审核所有三种登录类型的默认邮箱操作, 并且组织中的管理员*未*更改任何登录类型的操作。 注释默认情况下, 这是在组织中最初启用邮箱审核之后的默认状态。 

如果组织中的管理员已更改为登录类型审核的邮箱操作 (通过使用带有*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数的**Set-邮箱**cmdlet), 则值为*DefaultAuditSet*属性将与默认值不同。 例如, "值" `Owner`表示审核邮箱所有者的默认邮箱操作, 并且已更改`Delegate`和`Admin`的操作已更改。 如果没有为*DefaultAuditSet*属性 (也称为*null*值) 显示任何值, 则所有这三种登录类型的邮箱操作都已更改。

有关更改已审核的邮箱操作的详细信息, 请参阅本文中[默认情况下记录的更改或还原邮箱操作](#change-or-restore-mailbox-actions-logged-by-default)一节。

### <a name="display-a-list-of-mailbox-actions-logged-by-default"></a>显示默认情况下记录的邮箱操作的列表

您可以在 Exchange Online PowerShell 中运行以下命令, 以显示当前针对每个登录类型的邮箱的邮箱操作列表:

**所有者操作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditOwner
```

**委派操作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditDelegate
```

**管理操作**

```
Get-Mailbox <username> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>更改或还原默认情况下记录的邮箱操作

如前所述, 默认情况下邮箱审核的主要好处之一是, 您不必管理已审核的邮箱操作。 Microsoft 为你执行此操作, 并将在其发布时自动添加默认情况下要审核的新邮箱操作。 但是, 您的组织可能有理由审核一组不同于默认的邮箱操作。 本节介绍如何更改针对每个登录类型进行审核的邮箱操作, 以及如何还原为 Microsoft 托管的默认操作。

> [!IMPORTANT]
> 如果您对默认情况下记录的用户的邮箱操作进行了任何更改 (如下一节中所述), 则不会针对这些邮箱审核任何新的 Microsoft 邮箱操作。 您必须将新的邮箱操作显式添加到已针对某个登录类型进行审核的操作列表中。

### <a name="change-the-mailbox-actions-to-audit"></a>更改要审核的邮箱操作

您可以将**设置邮箱**cmdlet 与*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数结合使用, 以更改已审核的邮箱操作, 具体取决于登录类型。 由于这些与审核相关的参数是多值参数 (这意味着它们可以有多个值), 因此有两种不同的方法可用于更改这些参数。

- 您可以使用以下语法指定覆盖现有操作的多个邮箱操作: `action1,action2,...actionN`。

- 您可以使用以下语法在不影响任何现有记录的情况下添加或删除一个或多个`@{Add="action1","value2"}`邮箱`@{Remove="action1","action2"}`操作: 或。

无论您使用哪种方法来更改被审核的邮箱操作, 默认情况下已审核的邮箱操作 (对于您更改的登录类型) 将不再由 Microsoft 进行管理。 此外, 您更改的登录类型的值不会显示在[前面所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)的*DefaultAuditSet*邮箱参数中。

下面的示例展示了使用其中一种方法更改要针对每种不同登录类型进行审核的邮箱操作的一些示例。 

本示例通过使用 SoftDelete 和 HardDelete 覆盖默认操作来更改管理员邮箱的操作。 

```
Set-Mailbox <username> -AuditAdmin HardDelete,SoftDelete
```

本示例添加 "mailboxlogin 该值 owner" 操作。 

```
Set-Mailbox <username> -AuditOwner @{Add="MailboxLogin"}
```

本示例将删除 MoveToDeletedItems 委派操作。

```
Set-Mailbox <username> -AuditDelegate @{Remove="MoveToDeletedItems"}
```

#### <a name="checking-the-defaultauditset-property"></a>检查 DefaultAuditSet 属性

更改登录类型的默认邮箱操作后, 邮箱上的*DefaultAuditSet*属性将自动更新以反映此更改。 例如, 如果您在第`Get-Mailbox <username> | FL DefaultAuditSet`一次添加或删除邮箱所有者操作之后运行, 则该命令将仅返回值`Admin, Delegate`。 这表示所有者的默认邮箱操作已更改。这也意味着由 Microsoft 发布的任何新邮箱所有者操作将不会自动添加到此邮箱中。 对于更改 "管理员" 或 "委派" 登录类型的邮箱操作, 也是如此。

### <a name="restore-the-default-mailbox-actions"></a>还原默认邮箱操作

如果对已针对某个登录类型进行了审核的邮箱操作进行了更改, 则可以通过运行此`Set-Mailbox -DefaultAuditSet`命令来还原已审核的默认邮箱操作。 执行此操作时, 将发生以下情况:

- 当前的邮箱操作列表将被替换为相应登录类型的默认邮箱操作。
 
- 由 Microsoft 发布的任何新邮箱操作将自动添加到相应登录类型的列表中。

- [DefaultAuditSet 邮箱属性](#checking-the-defaultauditset-property)将进行更新, 以包含适当的登录类型。

若要还原所有登录类型的默认邮箱操作, 请运行以下命令:

```
Set-Mailbox <username> -DefaultAuditSet Admin,Delegate,Owner
```

您可以使用此命令还原任何登录类型的默认邮箱操作 (通过使用*DefaultAuditSet*参数的**Admin**、 **Delegate**或**Owner**值)。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>为你的组织默认关闭邮箱审核

如果您的组织决定不想审核邮箱操作, 您可以通过在 Exchange Online PowerShell 中运行以下命令, 在默认情况下为您的整个组织禁用邮箱审核:

```
Set-OrganizationConfig -AuditDisabled $true
```

如果默认情况下邮箱审核处于关闭状态 ( *AuditDisabled*属性设置为**True**), 则将发生以下情况:

- 对您的组织禁用邮箱审核。

- 即使邮箱的*AuditEnabled*属性设置为**True**, 也不会审核任何邮箱操作 (从组织禁用审核的时间开始)。

- 不会为新邮箱启用邮箱审核, 并将新的 (或现有) 邮箱的*AuditEnabled*属性设置为**True**将被忽略。

- 将忽略任何邮箱审核绕过关联设置 (使用**get-mailboxauditbypassassociation** cmdlet 配置)。

- 现有邮箱审核记录将一直保留, 直到记录的审核日志期限过期为止。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>默认情况下启用邮箱审核

若要为您的组织重新启用邮箱审核, 只需在 Exchange Online PowerShell 中运行以下命令:

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>绕过邮箱审核日志记录

目前, 在组织中启用默认邮箱审核时, 不能禁用特定邮箱的邮箱审核。 例如, 将*AuditEnabled*邮箱属性设置为**False**将被忽略。  但是, 仍可以使用 Exchange Online PowerShell 中的**get-mailboxauditbypassassociation** cmdlet 来防止记录特定用户执行的邮箱操作。 当您绕过邮箱审核时, 不会审核由特定用户执行的邮箱操作, 无论在哪个邮箱上执行这些操作。 如果您绕过特定用户的邮箱审核, 则不会记录该用户执行的邮箱所有者操作。 如果为该用户分配了对另一个用户的邮箱 (或共享邮箱) 的权限, 则第一个用户执行的委派操作也不会被记录。

若要绕过特定用户的邮箱审核日志记录, 请运行以下命令:

```
Set-MailboxAuditBypassAssociation -Identity <username> -AuditByPassEnabled $true
```

若要验证是否对指定用户跳过审核, 请运行以下命令:

```
Get-MailboxAuditBypassAssociation -Identity <username> | FL AuditByPassEnabled
```

**如果值为 True, 则**表示对该用户绕过邮箱审核日志记录。

## <a name="mailbox-auditing-actions"></a>邮箱审核操作
  
下表汇总了针对每个用户登录类型进行审核的操作。 在表中, 星号 ( **\*** ) 表示默认情况下记录操作。 "**否**" 表示无法为该登录类型记录操作。 请注意，分配有对用户邮箱的“完全访问”权限的管理员被视为委派用户。 
  
|**操作**|**说明**|**Admin**|**委派用户**|**Owner**|
|:-----|:-----|:-----|:-----|:-----|
|**Copy** <br/> |已将某个邮件复制到另一个文件夹。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**Create** <br/> |在邮箱的日历、联系人、备注或任务文件夹中创建项目；例如，创建新的会议请求。 请注意, 不会审核创建、发送或接收邮件。 此外, 还不会审核创建邮箱文件夹的情况。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**FolderBind**\** <br/> |已访问某个邮箱文件夹。 当管理员或委派打开邮箱时, 也会记录此操作。  <br/> |是  <br/> |是  <br/> |否  <br/> |
|**HardDelete** <br/> |已将某个邮件从"已恢复邮件"文件夹中清除。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**mailboxlogin 该值** <br/> |用户已登录到其邮箱。  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**MessageBind**\*** <br/> |在预览窗格查看邮件或打开邮件。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**移动** <br/> |已将某个邮件移至另一个文件夹。  <br/> |是  <br/> |是  <br/> |是  <br/> |
|**MoveToDeletedItems** <br/> |邮件已被删除并移动到 "已删除邮件" 文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**SendAs** <br/> |邮件是使用 SendAs 权限发送的。 这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SendOnBehalf** <br/> |邮件是使用 SendOnBehalf 权限发送的。 这表示另一个用户代表邮箱所有者发送了邮件。 该邮件指示收件人代表发送邮件的收件人和实际发送邮件的收件人。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SoftDelete** <br/> |邮件已从 "已删除邮件" 文件夹中永久删除或删除。 软删除的项目将移动到 "可恢复的项目" 文件夹中。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**更新** <br/> |更改了邮件或其属性。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateCalendarDelegation** <br/> |向邮箱分配了日历委派。 日历委派向组织中的其他人授予对邮箱所有者日历的管理权限。  <br/> |是\*  <br/> |否  <br/> |是\*  <br/> |
|**UpdateFolderPermissions** <br/> |更改了文件夹权限。 文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateInboxRules** <br/> |已添加、删除或更改收件箱规则。 "收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>默认情况下, 在为登录类型启用默认邮箱审核时进行审核。 <br/><br/>  <sup>\*\*</sup>合并由代理人执行的文件夹绑定操作的审核记录。 在24小时的时间范围内为单个文件夹访问生成一个审核记录。 <br/><br/> Exchange Online 中已弃用 MessageBind 操作, 并且不再可将其添加到管理登录类型的邮箱操作列表中。 <sup> \* \* \* </sup> 

## <a name="more-information"></a>更多信息

- 默认情况下, 邮箱审核日志记录将保留90天, 然后被删除。 您可以使用 Exchange Online PowerShell 中的 "**设置邮箱-AuditLogAgeLimit** " 命令更改审核日志记录的期限。 请注意, 为邮箱审核记录增加默认期限限制不会影响 Microsoft 365 审核日志中邮箱审核日志记录的90天期限限制。 例如, 如果将邮箱审核日志记录的期限增加到365天, 则在相应事件发生后的 Microsoft 365 审核日志中将仅在90天内搜索邮箱审核记录。 在这种情况下, 您必须在用户的邮箱审核日志中搜索超过90天的记录。 有关搜索邮箱审核日志的详细信息, 请参阅[search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)。

- 如果您已在邮箱审核之前对邮箱的*AuditLogAgeLimit*属性进行了更改, 则该邮箱的现有审核日志期限将不会更改, 否则将不会更改该邮箱的现有审核日志期限。换言之, 默认情况下邮箱审核不会影响邮箱审核记录的当前期限。

- 邮箱审核日志记录存储在每个用户邮箱的 "可恢复的项目" 文件夹中的子文件夹 (称为*审核*) 中。 请记住有关邮箱审核记录和 "可恢复的项目" 文件夹的以下事项。
   
    - 邮箱审核记录根据 "可恢复的项目" 文件夹的存储配额进行计数, 默认情况下 30GB (警告配额为 20 GB)。 请注意, 当在邮箱上放置保留项或将邮箱分配给合规中心中的保留策略时, "可恢复的项目" 文件夹的存储配额会自动增加至 100 GB (90 MB 警告配额)。

    - 邮箱审核记录也会对["可恢复的项目" 文件夹的文件夹限制进行](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)计数。 可存储在 "审核" 子文件夹中的项目的最大数量 (在此示例中为 "审核记录") 为3000000个项目。 

      > [!NOTE]
      > 邮箱默认情况下的审核不太可能会影响存储配额或 "可恢复的项目" 文件夹的文件夹限制。 

    - 您可以在 Exchange Online PowerShell 中运行以下命令, 以在 "可恢复的项目" 文件夹的 "审核" 子文件夹中显示项目的大小和数量: 
       ```
       Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | FL FolderPath,FolderSize,ItemsInFolder
       ```

     - 您不能直接访问 "可恢复的项目" 文件夹中的审核日志记录;相反, 您可以使用**search-mailboxauditlog** cmdlet 或搜索 Microsoft 365 审核日志来查找和查看邮箱审核记录。

- 如果将邮箱置于保留或分配到合规中心中的保留策略, 则审核日志记录仍将保留, 以供邮箱的*AuditLogAgeLimit*属性 (默认设置为 "90 天") 定义的持续时间保留。 若要延长保留邮箱的审核日志记录, 您必须通过增加*AuditLogAgeLimit*属性的值来增加保留期。