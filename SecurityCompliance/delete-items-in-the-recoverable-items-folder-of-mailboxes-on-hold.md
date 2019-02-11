---
title: 删除项目可恢复邮件文件夹中的基于云的邮箱置于保留状态的管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
ms.openlocfilehash: e80f5182bc425d71c6219decd48d41cf3dce6bba
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "28009638"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>删除项目可恢复邮件文件夹中的基于云的邮箱置于保留状态的管理员帮助

Exchange Online 邮箱的可恢复邮件文件夹存在以防止被意外或恶意删除。此外可用于存储项目，将会保留，并且可以访问 Office 365 合规性功能，例如保留和电子数据展示搜索。但是，在某些情况下组织可能会有已意外保留它们必须删除可恢复邮件文件夹中的数据。例如，用户可能不知情的情况下发送或转发电子邮件包含敏感信息或可能严重业务后果的信息。即使将永久删除邮件，可能无限期保留因为合法保留已被设置邮箱上。因为数据已意外溢出至 Office 365，这种情况下被称为数据泄漏。在这些情况下，您可以删除用户的 Exchange Online 邮箱，可恢复的项目文件夹中的项目，即使该邮箱置于保留与 Office 365 中的不同的保留功能之一。保留这些类型包括诉讼保留、 就地保留、 电子数据展示保留和 Office 365 保留策略在 Office 365 安全性中创建&amp;合规性中心。 
  
 本文介绍如何从基于云的邮箱置于保留状态的可恢复邮件文件夹中删除项目。此过程涉及禁用对邮箱的访问和禁用单个项目恢复，禁用托管文件夹助理处理邮箱、 暂时删除保留项，从可恢复邮件文件夹中，删除项和然后恢复到先前的配置邮箱。下面是过程： 
  
[步骤 1： 收集有关邮箱的信息](#step-1-collect-information-about-the-mailbox)

[步骤 2： 准备邮箱](#step-2-prepare-the-mailbox)

[步骤 3： 从邮箱中删除所有保留项](#step-3-remove-all-holds-from-the-mailbox)

[步骤 4： 删除邮箱延迟保留项](#step-4-remove-the-delay-hold-from-the-mailbox)

[步骤 5： 删除可恢复邮件文件夹中的项目](#step-5-delete-items-in-the-recoverable-items-folder)

[步骤 6： 将恢复其先前状态的邮箱](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> 本文中所述的过程将导致数据被永久删除 （清除） 从 Exchange Online 邮箱。这意味着您从可恢复邮件文件夹中删除的消息无法恢复，不能用于法律或其他合规性目的。如果您想要将置于保持状态的诉讼保留，就地保留，一部分的邮箱中删除邮件保留电子数据展示，或在 Office 365 安全性中创建 Office 365 保留策略&amp;合规性中心，检查您的记录管理或法律之前删除保留项的部门。您的组织可能必须定义上的邮箱是否保留策略或数据泄漏事件优先。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须同时分配的以下管理角色在 Exchange Online 搜索并删除在步骤 5 中可恢复邮件文件夹中的邮件。
    
  - **邮箱搜索**-此角色可使您能够搜索组织中的邮箱。默认情况下，Exchange 管理员不分配此角色。要将自己分配此角色，将自己添加为发现管理角色组的成员在 Exchange Online。 
    
  - **邮箱导入导出**-此角色可以从用户的邮箱中删除邮件。默认情况下，此角色不分配给任何角色组。若要从用户的邮箱中删除邮件，您可以添加邮箱导入导出角色到 Organization Management 角色组在 Exchange Online。 
    
- 非活动邮箱不支持这篇文章中介绍的过程。这是因为您不能重新应用保留 （或 Office 365 保留策略） 到非活动邮箱后将其删除。当您从非活动邮箱删除保留时，它更改为普通软删除邮箱，并将被永久删除从您的组织后，它由托管文件夹助理处理。
    
- 已分配给已被锁定与保留锁的 Office 365 保留策略的邮箱，无法执行此过程。这是因为保留锁防止删除或从 Office 365 保留策略和禁用托管文件夹助理邮箱不包括邮箱。有关锁定保留策略的详细信息，请参阅[锁定保留策略](retention-policies.md#locking-a-retention-policy)。
    
- 如果邮箱不置于保持状态 （或没有启用单个项目恢复），您可以只从可恢复邮件文件夹中删除项目。有关如何执行此操作的详细信息，请参阅[搜索并删除邮件](https://go.microsoft.com/fwlink/?linkid=852453)。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>步骤 1： 收集有关邮箱的信息

此第一个步骤是收集从目标邮箱将影响此过程的所选的属性。确保记下这些设置，或将其保存到文本文件中，因为您将更改某些这些属性，然后还原回步骤 6 中的原始值，从可恢复邮件文件夹中删除项目之后。下面是您需要收集邮箱属性的列表。
  
-  *SingleItemRecoveryEnabled*和*RetainDeletedItemsFor* ;如有必要，将禁用单个恢复并增加步骤 3 中的已删除的邮件保留期。 
    
-  *LitigationHoldEnabled*和*InPlaceHolds* ;您需要确定邮箱置于，以便可以在步骤 3 中临时删除它们的所有保留项。请参阅有关如何确定可能置于邮箱类型保留提示的[详细信息](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)部分。 
    
此外，您需要获取邮箱客户端访问设置，因此，以便所有者 （或其他用户） 不能在此过程访问邮箱，您可以暂时禁用它们。最后，您可以在可恢复邮件文件夹中获取的当前大小和项目数。删除在步骤 5 中可恢复邮件文件夹中的项目后，您将使用此信息来验证已实际删除项目。
  
1. [连接到 Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。确保用于已分配 Exchange Online 中的适当的管理角色的管理员帐户的用户名和密码。 
    
2. 运行以下命令以获取有关单个项目恢复和已删除的邮件保留期限。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   如果启用单个项目恢复，则必须将禁用在步骤 2 中。已删除的邮件保留期限不为 30 天 （Exchange Online 中的最大值），然后您可以增加其在步骤 2 中。 
    
3. 运行以下命令以获取访问设置邮箱的邮箱。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   将禁用所有这些访问方法在步骤 2 中。
    
4. 运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 如果*InPlaceHolds*属性中有太多值而不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行显示每个值。 
  
5. 运行以下命令以获取有关 Office 365 的任何组织范围内保留策略的信息。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   如果您的组织有任何组织范围内的 Office 365 保留策略，必须将邮箱排除在步骤 3 中这些策略。

   > [!TIP]
    > 如果*InPlaceHolds*属性中有太多值而不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行显示每个值。 
  
6. 运行以下命令以获取打包在文件夹和子文件夹中用户的主邮箱中可恢复邮件文件夹中的当前大小和项目总数。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   如果启用了用户的存档邮箱，运行以下命令以获取文件夹和子文件夹中其存档邮箱中可恢复邮件文件夹中的大小和项目总数。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   删除在步骤 5 中的项目时，您可以选择删除或删除用户的主存档邮箱中可恢复邮件文件夹中的项目。请注意，是否为邮箱启用了自动扩展存档，则辅助存档邮箱中的项目不会删除。
  
## <a name="step-2-prepare-the-mailbox"></a>步骤 2： 准备邮箱

后收集和保存有关邮箱的信息下, 一步是准备好邮箱，通过执行以下任务： 
  
- **禁用客户端对邮箱的访问权**，以便邮箱所有者无法访问其邮箱并在此过程的邮箱数据进行任何更改。 
    
- 为 30 天**增加已删除的邮件保留期限**（Exchange Online 中的最大值），以便在步骤 5 中删除之前，项目不从可恢复邮件文件夹中清除。 
    
- **禁用单个项目的恢复**的项目以便不会保留 （已删除的邮件保留期限的持续时间） 后删除从步骤 5 中可恢复邮件文件夹。 
    
- **禁用托管文件夹助理**，以便使其不处理该邮箱并保留在步骤 5 中删除的项目。 
    
在 Exchange Online PowerShell 中执行以下步骤。
  
1. 运行以下命令以禁用对邮箱的所有客户端访问。命令语法假定所有客户端访问方法已启用邮箱。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > 它可能需要长达 60 分钟禁用对邮箱的所有客户端访问方法。请注意禁用这些访问方法不断开其当前登录邮箱所有者。如果所有者未登录，然后他们将无法访问其邮箱后禁用这些访问方法。 
  
2. 运行以下命令以增加最大值 30 天的已删除的邮件保留期限。此，假定当前的设置不超过 30 天。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 运行以下命令以禁用单个项目恢复。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 它可能需要长达 60 分钟禁用单个项目恢复。不删除可恢复邮件文件夹中的项目，直到此时间已。 
  
4. 运行以下命令以防止托管文件夹助理处理邮箱。如前所述，您可以禁用托管文件夹助理仅当与保留锁的 Office 365 保留策略不应用到的邮箱。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>步骤 3： 从邮箱中删除所有保留项

您可以从可恢复邮件文件夹中删除项目之前的最后一步是删除所有保留项 （即在步骤 1 中确定） 邮箱置于。以便不会保留项，从可恢复邮件文件夹删除后，必须删除所有保留项。以下各节包含有关删除邮箱的保留项的不同类型的信息。请参阅有关如何确定可能置于邮箱类型保留提示的[详细信息](#more-information)部分。有关其他信息，请参阅[如何识别的类型保留放置在 Exchange Online 邮箱](identify-a-hold-on-an-exchange-online-mailbox.md)。
  
> [!CAUTION]
> 如前面所述，请与您的记录管理或法律部门邮箱中删除保留之前。 
  
 ### <a name="litigation-hold"></a>诉讼保留
  
运行以下命令在 Exchange Online PowerShell，可以从邮箱中删除诉讼保留。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> 类似于禁用客户端访问方法和单个项目恢复，可能需要 60 分钟诉讼保留中删除。不要删除从可恢复邮件文件夹的项目，直到此时间已。 
  
 ### <a name="in-place-hold"></a>就地保留
  
运行以下命令在 Exchange Online PowerShell，可以确定邮箱置于就地保留。使用您在步骤 1 中确定的就地保留的 GUID。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
确定就地保留后，您可以使用 Exchange 管理中心 (EAC) 或 Exchange Online PowerShell 可以从保留中删除邮箱。有关详细信息，请参阅[创建或删除就地保留](https://go.microsoft.com/fwlink/?linkid=852668)。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 的保留策略应用于特定邮箱
  
运行以下命令， [Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识 Office 365 保留策略应用于邮箱。使用的 GUID (不包括`mbx`或`skp`前缀) 在步骤 1 中确定的保留策略。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
确定保留策略后，转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑上一步，标识的保留策略，并从列表中删除邮箱保留策略中包括的收件人。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Office 365 组织范围中的保留策略
  
组织范围内和 Exchange 范围 Office 365 保留策略应用于组织中的每个邮箱。它们应用于组织级别 （而不是邮箱级别），并且在步骤 1 中运行**Get-organizationconfig** cmdlet 时返回。运行以下命令，[安全&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识组织范围内的 Office 365 保留策略。使用的 GUID (不包括`mbx`前缀) 在步骤 1 中确定的组织范围内保留策略。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

确定组织范围内的 Office 365 保留策略后，转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑中标识的每个组织范围内保留策略上一步骤，并将邮箱添加到已排除的收件人列表。此操作将保留策略中删除用户邮箱。 

### <a name="office-365-retention-labels"></a>Office 365 保留标签

只要用户应用配置保留内容或保留，然后删除任何文件夹或其邮箱中的项目的内容的标签，则将*ComplianceTagHoldApplied* mailbox 属性设置为**True**。这种情况下，邮箱被认为保持状态，就像它置于诉讼保留或分配给 Office 365 保留策略。

若要查看*ComplianceTagHoldApplied*属性的值，请在 Exchange Online PowerShell 中运行以下命令：

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

您已确定邮箱是置于保持状态，因为保留标签应用于文件夹或项目后，您可以使用安全 & 合规性中心中内容搜索工具搜索标记的项目使用 ComplianceTag 搜索条件。有关详细信息，请参阅[关键字查询及搜索内容搜索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)中的"搜索条件"部分。

有关标签的详细信息，请参阅[Office 365 概述标签](labels.md)。

 ### <a name="ediscovery-case-holds"></a>电子数据展示事例包含
  
运行以下命令，[安全&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)标识保留项应用于邮箱电子数据展示事例相关联。使用的 GUID (不包括`UniH`前缀) 的电子数据展示保留在步骤 1 中确定。请注意，第二个命令显示的电子数据展示案例保留项相关联; 名称第三个命令显示的保留项的名称。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

您已确定的电子数据展示事例并保留名称后，转到**搜索&amp;调查**\>安全中的**电子数据展示**页&amp;合规性中心打开这种情况，并从保留中删除邮箱。有关详细信息，请参阅[管理 Office 365 安全性的电子数据展示事例&amp;合规性中心](manage-ediscovery-cases.md)。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>步骤 4： 删除邮箱延迟保留项

从邮箱中删除任何类型的保留项后， *DelayHoldApplied*邮箱属性的值设置为**True**。托管文件夹助理处理邮箱和检测已删除保留在下次出现此情况。这称为*延迟保留*，意味着实际删除的保留项的延迟，30 天，以防止数据从邮箱被永久删除。（延迟保留项的旨在使管理员可以搜索或恢复将被清除后保留被删除的邮箱项目。） 延迟保留邮箱置于，当邮箱是仍可保持不受限制的持续时间，作为邮箱是否在诉讼保留。30 天后过期延迟保留，和 Office 365 将自动尝试 （通过将*DelayHoldApplied*属性设置为**False**） 删除延迟保留以便实际删除该保留。 

您可以删除在步骤 5 中的项目之前，您必须从邮箱中删除延迟保留。首先，确定是否延迟保留应用于邮箱的 Exchange Online PowerShell 中运行以下命令：

```
Get-Mailbox <username> | FL DelayHoldApplied
```

如果*DelayHoldApplied*属性的值设置为**False**，已不被邮箱上设置延迟保留。您可以转到步骤 5 和删除可恢复邮件文件夹中的项目。

如果*DelayHoldApplied*属性的值设置为**True**，则运行以下命令以删除延迟保留：

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
请注意，您必须将分配给法律挂起角色在 Exchange Online 使用*RemoveDelayHoldApplied*参数。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>步骤 5： 删除可恢复邮件文件夹中的项目

现在，您就可以实际使用[Search-mailbox](https://go.microsoft.com/fwlink/?linkid=852595) cmdlet 在 Exchange Online PowerShell 中删除可恢复邮件文件夹中的项目。运行**Search-mailbox** cmdlet 时，您可以具有三个选项。 
  
- 将项目复制到目标邮箱之前，以便您可以查看项目，如有必要，删除它们之前，会删除它们。
    
- 将项目复制到目标邮箱并将其删除在同一命令中。
    
- 不将其复制到目标邮箱中删除项目。 
    
请注意运行**Search-mailbox** cmdlet 时也将删除用户的主存档邮箱中可恢复邮件文件夹中的项目。要防止这样，您可以包括*DoNotIncludeArchive*开关。如前面所述，如果展开存档是启用的邮箱，* * Search-mailbox * * cmdlet 不会删除辅助存档邮箱中的项目。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。
  
> [!NOTE]
> 如果添加一个搜索查询（通过使用  *SearchQuery*  参数）， **Search-Mailbox** cmdlet 最多返回搜索结果中的 10,000 个项目。因此，如果添加一个搜索查询，则可能需要多次运行 **Search-Mailbox** 命令才能将 10,000 多个项目删除。 
  
下面的示例显示这些选项的每个命令语法。这些示例使用`-SearchQuery size>0`参数值，从可恢复邮件文件夹中的所有子文件夹中删除所有项目。如果您需要删除满足特定条件的项目，您还可以使用*SearchQuery*参数指定其他条件，如一条消息或日期范围的主题。请参阅下面的[使用 SearchQuery 参数的其他示例](#other-examples-of-using-the-searchquery-parameter)。 
  
### <a name="example-1"></a>示例 1

本示例在用户的可恢复的项目文件夹中的所有项目都复制到您的组织发现搜索邮箱中的文件夹。这样可以永久删除之前查看项目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

在上面的示例，它不需要将项目复制到发现搜索邮箱。您可以将邮件复制到任何目标邮箱。但是，为了防止对敏感的邮箱数据的访问，建议将邮件复制到了授权人员限制访问权限的邮箱。默认情况下访问默认发现搜索邮箱的权限被限制为发现管理角色组的成员在 Exchange Online。 
  
### <a name="example-2"></a>示例 2

本示例将用户的可恢复项目文件夹中的所有项目都复制到您的组织发现搜索邮箱中的文件夹，然后从用户的可恢复项目文件夹中删除项目。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>示例 3

本示例删除用户的可恢复的项目文件夹中的所有项目，而不将其复制到目标邮箱。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>使用 SearchQuery 参数的其他示例

下面是一些使用*SearchQuery*参数来查找特定邮件的示例。如果您使用*SearchQuery*参数来搜索特定项，请考虑将搜索结果复制到目标邮箱，以便您可以查看搜索结果，然后再修订查询必要之前删除的搜索结果。 
  
本示例返回包含主题字段中的特定短语的邮件。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

本示例返回在指定的日期范围内发送的邮件。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
本示例返回到指定的人发送的邮件。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>验证已删除项目

若要验证您已成功删除项目从邮箱的可恢复邮件文件夹，使用**Get-mailboxfolderstatistics** cmdlet 在 Exchange Online PowerShell 检查的规模和可恢复的项目文件夹中的项目的数量。可以将这些统计信息与您在步骤 1 中收集的那些进行比较。 
  
中运行以下命令以获取文件夹和子文件夹中用户的主邮箱中可恢复邮件文件夹中的的当前大小和项目总数。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
运行以下命令以获取文件夹和子文件夹中用户的存档邮箱中可恢复邮件文件夹中的大小和项目总数。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>步骤 6： 将恢复其先前状态的邮箱

最后一步是将还原回先前的配置的邮箱。这意味着您在步骤 2 中更改的属性重置并重新应用您在步骤 3 中删除保留。这包括：
  
- 更改已删除的邮件保留期限回其以前的值。此外，您可以只需保留这将设置为 30 天，最大值在 Exchange Online。
    
- 重新启用单个项目恢复。
    
- 重新启用客户端访问方法，以便所有者可以访问其邮箱。
    
- 重新应用保留和已删除的 Office 365 保留策略。
    
- 重新启用托管文件夹助理处理邮箱。
    
> [!IMPORTANT]
> 我们建议您等待 24 小时后重新应用保持或 Office 365 保留策略 （和验证它是否就地） 重新启用托管文件夹助理处理邮箱之前。 
  
在 Exchange Online PowerShell 中执行以下步骤 （按指定顺序）。
  
1. 运行以下命令以更改已删除的邮件保留期限回其原始值。此，假定前面的设置是不超过 30 天。例如 14 天。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 运行以下命令以重新启用单个项目恢复。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 运行以下命令以重新启用对邮箱的所有客户端访问方法。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 重新应用您在步骤 3 中删除保留。根据保留项的类型，使用以下过程之一。
    
    **诉讼保留**
    
    运行以下命令以重新启用邮箱的诉讼保留。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    使用 EAC （或 Exchange Online PowerShell） 添加回就地保留的邮箱。 
    
    **Office 365 的保留策略应用于特定邮箱**
    
    使用安全&amp;合规性中心邮箱将重新添加到 Office 365 保留策略。转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑保留策略，并返回到的收件人的保留策略应用于列表添加邮箱。 
    
    **Office 365 组织范围中的保留策略**
    
    如果通过排除从策略中删除组织范围内或 Exchange 范围保留策略，然后使用安全&amp;合规性中心以从列表中删除邮箱排除用户。转到**日期调控** \> **保留**页面安全中的&amp;合规性中心编辑组织范围内保留策略，并从排除收件人列表中删除邮箱。此操作将重新保留策略应用到用户的邮箱。 
    
    **电子数据展示事例包含**
    
    使用安全&amp;合规性中心添加邮箱备份保留电子数据展示事例与相关联。转到**搜索&amp;调查**\>安全中的**电子数据展示**页&amp;合规中心打开这种情况，并返回到保留项中添加邮箱。 
    
5. 运行以下命令以允许托管文件夹助理再次处理邮箱。如上文所述，我们建议您等待 24 小时后重新应用保持或 Office 365 保留策略 （和验证它是否就地） 重新启用托管文件夹助理之前。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. 若要验证邮箱已被还原回先前的配置，您可以运行以下命令，比较到在步骤 1 中收集的那些设置。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>更多信息

下面是一个表，介绍如何标识不同类型的保留项基于*InPlaceHolds*属性中的值，当您运行**Get-mailbox**或**Get-organizationconfig** cmdlet。有关详细信息，请参阅[如何识别的类型保留放置在 Exchange Online 邮箱](identify-a-hold-on-an-exchange-online-mailbox.md)。

如上文所述，必须删除所有保留项和 Office 365 之前邮箱的保留策略可以成功删除可恢复邮件文件夹中的项目。 
  
|**保留类型**|**示例值**|**如何标识保留项**|
|:-----|:-----|:-----|
|诉讼保留  <br/> | `True` <br/> |*LitigationHoldEnabled*属性设置为`True`。  <br/> |
|就地保留  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*属性将包含邮箱置于就地保留的 GUID。您可以判断这是就地保留因为 GUID 不以前缀开头。<br/> 您可以使用`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`命令在 Exchange Online PowerShell 中邮箱上获取就地保留的信息。  <br/> |
| Office 365 中安全性的保留策略&amp;合规性中心于特定邮箱  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> 或  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |当您运行**Get-mailbox** cmdlet 时， *InPlaceHolds*属性还包含 Guid 的 Office 365 保留策略应用于邮箱。您可以标识保留策略，因为 GUID 开头`mbx`前缀。请注意，如果保留策略的 GUID 开头`skp`前缀，指示是否保留策略应用于 Skype 业务对话。<br/> 到标识 Office 365 应用于邮箱的保留策略，运行以下命令在安全&amp;合规性中心 PowerShell: <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>请务必删除`mbx`或`skp`前缀当运行此命令。  <br/> |
|组织范围内安全中的 Office 365 保留策略&amp;合规性中心  <br/> |没有值  <br/> 或  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`（表示邮箱被排除从组织范围的策略）  <br/> |即使*InPlaceHolds*属性为空，运行**Get-mailbox** cmdlet 时，可能仍存在一个或多个组织范围内 Office 365 保留策略应用于邮箱。  <br/> 若要验证这一点，您可以运行`Get-OrganizationConfig | FL InPlaceHolds`命令在 Exchange Online PowerShell 中，若要获取组织范围内的 Office 365 保留策略的 Guid 的列表。适用于 Exchange 邮箱开始与组织范围内保留策略的 GUID`mbx`前缀;例如`mbxa3056bb15562480fadb46ce523ff7b02`。<br/> 为标识组织范围内的 Office 365 保留策略应用于邮箱，运行以下命令在安全&amp;合规性中心 PowerShell: <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>请注意，是否从组织范围内的 Office 365 保留策略中排除邮箱，将保留策略的 GUID 显示用户的邮箱的*InPlaceHolds*属性中运行**Get-mailbox** cmdlet 中; 时由前缀`-mbx`;例如，`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|在安全保留电子数据展示事例&amp;合规性中心  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*属性还包含与安全中电子数据展示事例关联任何保留项的 GUID&amp;可能置于邮箱的合规性中心。您可以判断这是电子数据展示案例保留，因为 GUID 开头`UniH`前缀。<br/> 您可以使用`Get-CaseHoldPolicy`cmdlet 中安全&amp;合规性中心 PowerShell，可以获取关于电子数据展示案例与关联邮箱的保留项的信息。例如，可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`显示邮箱上的案例保留项的名称。请务必删除`UniH`前缀当运行此命令。<br/><br/> 为标识与邮箱保留电子数据展示事例，运行以下命令：<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


