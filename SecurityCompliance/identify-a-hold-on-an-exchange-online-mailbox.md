---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: 了解如何识别可在 Office 365 邮箱中放置的不同类型的保留。 这些保留类型包括诉讼保留、电子数据展示保留和 Office 365 保留策略。 您还可以确定是否已从组织范围的保留策略中排除了用户
ms.openlocfilehash: 29ae9d7ba8be2bf0064c163605aee9ad8fd5fd07
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154194"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何识别为 Exchange Online 邮箱设置的保留类型

本文介绍如何确定在 Office 365 的 Exchange Online 邮箱中放置的保留。

Office 365 提供了多种方法, 使您的组织可以阻止邮箱内容被永久删除。 这样, 贵组织可以保留内容以满足合规性 regulars 或法律或其他类型调查的持续时间。 下面列出了 Office 365 中的保留功能 (也称为 "*保留*"):

- 应用于 Exchange Online 中的用户邮箱的**诉讼保留**项。

- 与安全与合规中心中的电子数据展示事例相关联的**电子数据展示保留**-保留。 可将电子数据展示保留应用于用户邮箱以及 Office 365 组和 Microsoft 团队对应的邮箱。

- 在 Exchange Online 中使用 Exchange 管理中心内的就地电子数据展示 & 保留工具将应用于用户邮箱的**就地保留**保留。

- **Office 365 保留策略**-在 Exchange Online 中的用户邮箱中以及 Office 365 组和 Microsoft 团队对应的邮箱中保留内容。 可以创建保留策略保留 Skype for Business 对话, 这些会话存储在用户邮箱中。

  有两种类型的 Office 365 保留策略可分配给邮箱。

    - **特定位置保留策略**-这些策略是分配给特定用户的内容位置的策略。 您可以使用 Exchange Online PowerShell 中的**邮箱获取**cmdlet 获取有关分配给特定邮箱的保留策略的信息。

    - **组织范围内的保留策略**-这些策略是分配给组织中的所有内容位置的策略。 您可以使用 Exchange Online PowerShell 中的**set-organizationconfig** cmdlet 来获取有关组织范围的保留策略的信息。
  有关详细信息, 请参阅[Office 365 保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)中的 "将保留策略应用于整个组织或特定位置" 部分。

- **Office 365 保留标签**-如果用户应用 office 365 保留标签 (配置为保留内容或保留内容, 然后将内容删除) 到其邮箱中的*任何*文件夹或项目中, 则邮箱上的保留将与邮箱被放在邮箱之外, 就像邮箱是置于诉讼保留或分配到 Office 365 保留策略。 有关详细信息, 请参阅[保留邮箱处于保留状态, 因为已将保留标签应用于本文中的文件夹或项目](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)部分。

若要管理处于保留状态的邮箱, 您可能需要确定邮箱中放置的保留类型, 以便可以执行诸如更改保留持续时间、临时或永久删除保留或从 Office 365 保留策略中排除邮箱等任务。 在这些情况下, 第一步是确定邮箱上放置的保留类型。 由于可以将多个保留 (和不同类型的保留) 放置在单个邮箱上, 因此, 如果您想要删除或更改这些保留项, 则必须标识邮箱上的所有保留。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>步骤 1: 获取邮箱中放置的保留的 GUID

您可以在 Exchange Online PowerShell 中运行以下两个 cmdlet, 以获取邮箱中放置的保留的 GUID。 获取 GUID 后, 可以使用它来标识步骤2中的特定保留。 请注意, GUID 不会识别诉讼保留。 为邮箱启用或禁用诉讼保留。

- **获取邮箱**-使用此 cmdlet 可确定是否对邮箱启用了诉讼保留, 以及如何获取专门分配给邮箱的电子数据展示保留、就地保留和 Office 365 保留策略的 guid。 此 cmdlet 的输出还将指示是否已从组织范围的保留策略中显式排除了邮箱。

- **Set-organizationconfig** -使用此 cmdlet 获取组织范围的保留策略的 guid。

若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值过多, 并且不是全部显示, 则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。

下表介绍在运行 InPlaceHolds cmdlet 时, 如何根据** 属性中的值标识不同类型的保留。 ****


|保留类型  |示例值  |如何识别保留  |
|---------|---------|---------|
|诉讼保留     |    `True`     |     如果将*LitigationHoldEnabled*属性设置为`True`, 则为邮箱启用诉讼保留。    |
|电子数据展示保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 属性*包含与安全与合规中心中的电子数据展示事例关联的任何保留的 GUID。 你可以告诉这是电子数据展示保留, 因为 GUID 以`UniH`前缀 (表示统一保留) 开头。      |
|就地保留     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*属性包含邮箱中放置的就地保留的 GUID。 您可以指示这是就地保留, 因为 GUID 既不以前缀开头, 也不以`cld`前缀开头。     |
|专用于邮箱的 Office 365 保留策略     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 属性包含应用于邮箱的任何特定位置保留策略的 Guid。 您可以确定保留策略, 因为 GUID 以`mbx`或`skp`前缀开头。 `skp`前缀指示将保留策略应用于用户邮箱中的 Skype for business 会话。    |
|从组织范围的 Office 365 保留策略中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果从组织范围的 Office 365 保留策略中排除了邮箱, 则从 InPlaceHolds 属性中排除的保留策略的 GUID 将显示在 "" 属性中, 并由`-mbx`前缀进行标识。    |

### <a name="get-organizationconfig"></a>Set-organizationconfig
如果运行**邮箱**cmdlet 时, *InPlaceHolds*属性为空, 则仍可能会将一个或多个组织范围内的 Office 365 保留策略应用于邮箱。 在 Exchange Online PowerShell 中运行以下命令, 获取组织范围内的 Office 365 保留策略的 Guid 列表。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中的值过多, 并且不是全部显示, 则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令将每个 GUID 显示在单独的行上。

下表介绍了不同类型的组织范围的保留, 以及在运行**set-organizationconfig** cmdlet 时如何根据*InPlaceHolds*属性中包含的 guid 标识每种类型。


|保留类型  |示例值  |说明  |
|---------|---------|---------|
|应用于 Exchange 邮箱、Exchange 公用文件夹和团队聊天的 Office 365 保留策略    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   在 Microsoft 团队中应用于 Exchange 邮箱、Exchange 公用文件夹和1xN 聊天的组织范围内的保留策略由以`mbx`前缀开头的 guid 进行标识。 请注意, 1xN 聊天存储在各个聊天参与者的邮箱中。      |
|应用于 Office 365 组和团队频道消息的 office 365 保留策略     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    在 Microsoft 团队中应用于 Office 365 组和频道消息的组织范围内的保留策略由以`grp`前缀开头的 guid 标识。 请注意, 信道邮件存储在与 Microsoft 团队相关联的组邮箱中。     |

有关应用于 Microsoft 团队的详细信息保留策略, 请参阅[保留策略](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)的 "团队位置" 一节概述。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlaceHolds 值的格式

除了将 InPlaceHolds 属性中的项目标识为 Office 365 保留策略的前缀 (mbx、skp 或 grp) 之外, 此值还包含一个标识为策略配置的保留操作类型的后缀。 例如, 在以下示例中, 操作后缀以粗体突出显示:

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

下表定义了三种可能的保留操作:

|值  |说明  |
|---------|---------|
|**1**     | 指示保留策略已配置为删除项目;策略不会保留项目。        |
|**双面**    |    指示保留策略配置为保留项;在保留期过期后, 策略不会删除项目。     |
|**第三章**     |   指示保留策略配置为保留项目, 然后在保留期过期后将其删除。      |

有关保留操作的详细信息, 请参阅[保留策略概述](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的 "在特定时间段内保留内容" 部分。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>步骤 2: 使用 GUID 标识保留

获取应用于邮箱的保留的 GUID 后, 下一步是使用该 GUID 标识保留。 以下各节介绍如何使用保留 GUID 标识保留的名称 (和其他信息)。

### <a name="ediscovery-holds"></a>电子数据展示保留

在 Security & 合规性中心 PowerShell 中运行以下命令, 以确定应用于邮箱的电子数据展示保留。 使用您在步骤1中确定的电子数据展示保留的 GUID (不包括 UniH 前缀)。 第一个命令创建包含有关保留的信息的变量;在其他命令中使用此变量。 第二个命令显示与保留相关联的电子数据展示事例的名称。 第三个命令显示保留的名称和应用保留的邮箱列表。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

若要连接到安全 & 合规性中心 PowerShell, 请参阅[connect To Security _AMP_ 合规中心 powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在 Exchange Online PowerShell 中运行以下命令, 以确定应用于邮箱的就地保留。 对您在步骤1中标识的就地保留使用 GUID。 该命令将显示保留的名称和应用保留的邮箱列表。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
请注意, 如果就地保留的 GUID 以`cld`前缀开头, 请确保在运行前一个命令时包含前缀。

### <a name="office-365-retention-policies"></a>Office 365 保留策略

在 Security & 合规中心 PowerShell 中运行以下命令, 以标识应用于邮箱的 Office 365 保留策略 (组织范围或特定位置)。 使用您在步骤1中标识的 GUID (不包括 mbx、skp 或 grp 前缀或操作后缀)。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>由于已将保留标签应用于文件夹或项目, 因此标识邮箱处于保留状态

只要用户应用配置为保留内容或保留内容的保留标签, 然后将内容删除到其邮箱中的任何文件夹或项目, *ComplianceTagHoldApplied*邮箱属性将设置为**True**。 如果发生这种情况, 则认为邮箱处于保留状态, 就像将其置于诉讼保留状态或分配到 Office 365 保留策略一样。 当*ComplianceTagHoldApplied*属性设置为**True**时, 可能会出现以下情况:

- 如果删除了邮箱或用户的 Office 365 用户帐户, 则邮箱将成为[非活动邮箱](inactive-mailboxes-in-office-365.md)。
- 将无法禁用邮箱 (主邮箱或存档邮箱 (如果已启用)。
- 邮箱中的项目可能会超过预期的保留时间。 这是因为邮箱处于保留状态, 因此不会永久删除 (清除) 任何项目。

若要查看*ComplianceTagHoldApplied*属性的值, 请在 Exchange Online PowerShell 中运行以下命令:

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

有关保留标签的详细信息, 请参阅[Office 365 的概述保留标签](labels.md)。

## <a name="managing-mailboxes-on-delay-hold"></a>在延迟保留时管理邮箱

从邮箱中删除了任何类型的保留后, *DelayHoldApplied*邮箱属性的值将设置为**True**。 在下次托管文件夹助理处理邮箱并检测已删除保留时, 会发生这种情况。 这称为*延迟保留*, 表示实际删除保留的延迟为30天, 以防止永久删除 (清除) 邮箱中的数据。 这使管理员有机会搜索或恢复在实际删除保留后将清除的邮箱项目。 将延迟保留放在邮箱上时, 该邮箱仍被视为无限持续时间处于保留状态, 就像该邮箱处于诉讼保留状态一样。 30天后, 延迟保留将到期, Office 365 将自动尝试删除延迟保留 (通过将*DelayHoldApplied*属性设置为**False**), 以便实际删除保留。 在*DelayHoldApplied*属性设置为**False**之后, 在下一次托管文件夹助理处理邮箱时, 将清除标记为要删除的项目。

若要查看邮箱的*DelayHoldApplied*属性的值, 请在 Exchange Online PowerShell 中运行以下命令。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

若要在过期之前删除延迟保留, 可以在 Exchange Online PowerShell 中运行以下命令: 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
请注意, 您必须在 Exchange Online 中向您分配 "合法保留" 角色, 才能使用*RemoveDelayHoldApplied*参数 

若要删除非活动邮箱的延迟保留, 请在 Exchange Online PowerShell 中运行以下命令:

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> 在上一命令中指定非活动邮箱的最佳方法是使用其可分辨名称或 Exchange GUID 值。 使用下列值之一有助于避免意外指定错误的邮箱。 

## <a name="next-steps"></a>后续步骤

在确定了应用于邮箱的保留后, 可以执行一些任务, 例如更改保留的持续时间、临时或永久删除保留, 或者在 Office 365 保留策略 (不包括策略中的非活动邮箱) 的情况下执行此操作。 有关执行与保留相关的任务的详细信息, 请参阅下列主题之一:

- 在 Security & 合规中心 PowerShell 中运行[new-retentioncompliancepolicy-AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)命令, 以将邮箱从组织范围的 Office 365 保留策略中排除。 请注意, 此命令仅可用于*ExchangeLocation*属性值等于`All`的保留策略。

- 在 Exchange Online PowerShell 中运行 "[设置邮箱-ExcludeFromOrgHolds \<保留 GUID, 但不使用前缀或 suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) " 命令从组织范围的 Office 365 保留策略中排除非活动邮箱。

- [在 Office 365 中更改非活动邮箱的保留期](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

- [删除保留状态云邮箱的“可恢复的项目”文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
