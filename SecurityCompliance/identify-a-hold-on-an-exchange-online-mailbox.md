---
title: 如何识别为 Exchange Online 邮箱设置的保留类型
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
ms.openlocfilehash: d24e51bca0e3d290f110b1ab40f3ee9ae7993678
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525670"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>如何识别为 Exchange Online 邮箱设置的保留类型

本文介绍如何标识放置在 Office 365 中的 Exchange Online 邮箱的保留项。

Office 365 提供多种方式的组织可以防止邮箱内容被永久删除。这将允许组织保留内容以满足合规性将或法律或其他类型的调查的持续时间。下面是在 Office 365 中的保留功能 （也称为保留项） 的列表：

- **诉讼保留**-于 Exchange Online 中的用户邮箱的保留项。

- **电子数据展示保留**-与安全性和合规性中心中的电子数据展示事例关联的保留项。电子数据展示保留项可以为 Office 365 组和 Microsoft 团队对用户邮箱和相应的邮箱应用。

- **就地保留**— 通过使用在 Exchange 管理中心中的就地电子数据展示和保留工具应用于用户邮箱的保留中心在 Exchange Online。

- **Office 365 保留策略**-Office 365 组和 Microsoft 团队保留用户邮箱和相应的邮箱中 Exchange Online 中的内容。您可以创建保留策略进行业务对话，存储在用户邮箱中保留 Skype。

  有两种类型的 Office 365 可以分配给邮箱的保留策略。

    - **特定位置保留策略**-这是分配给特定用户的内容位置策略。在 Exchange Online PowerShell 中使用 Get-mailbox cmdlet，以获取有关分配给特定邮箱的保留策略的信息。

    - **组织范围内保留策略**-这是分配给您的组织中的所有内容位置策略。在 Exchange Online PowerShell 中使用 Get-organizationconfig cmdlet，以获取有关组织范围内保留策略的信息。有关详细信息，请参阅 Office 365 概述保留策略中的"将保留策略应用于整个组织或特定位置"一节。

若要管理邮箱置于保留状态，您可能需要确定上，以便您可以执行任务，如更改保留持续时间、 临时或永久删除保留项，或从 Office 365 保留策略中排除邮箱置于邮箱的保留项的类型。在这些情况下，第一步是确定邮箱置于保留项的类型。因为可以对单个邮箱放置多个保留 （和不同类型的保留），您必须确定置于邮箱，如果您想要删除或更改这些保留项的所有保留项。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>步骤 1： 获取保留项的 GUID 置于邮箱

在 Exchange Online PowerShell 中获取对邮箱置于保留项的 GUID，可以运行以下两个 cmdlet。获取 GUID 后，您使用它来标识在步骤 2 中的特定保留项。请注意，诉讼保留未被标识的 GUID。诉讼保留项是启用或禁用的邮箱。

- **Get-mailbox** -使用此 cmdlet，以确定是否诉讼保留的邮箱启用以及获取 Guid 电子数据展示保留、 就地保留，和 Office 365 专门分配给某个邮箱的保留策略。此 cmdlet 的输出将还指示邮箱是否已明确排除从组织范围内保留策略。

- **Get-organizationconfig** -使用此 cmdlet 可获取的组织范围内保留策略的 Guid。

要连接到 Exchange Online PowerShell 中，请参阅[Connect to Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。

### <a name="get-mailbox"></a>Get-Mailbox

运行以下命令以获取有关保留和 Office 365 保留策略应用于邮箱的信息。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。

下表介绍了如何确定不同类型的保留项运行**Get-mailbox** cmdlet 时基于*InPlaceHolds*属性中的值。


|保留类型  |示例值  |如何标识保留项  |
|---------|---------|---------|
|诉讼保留     |    `True`     |     如果*LitigationHoldEnabled*属性设置为诉讼保留的邮箱启用`True`。    |
|电子数据展示保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds 属性*包含与电子数据展示事例中安全性和合规性中心关联任何保留项的 GUID。您可以判断这是电子数据展示保留，因为 GUID 开头`UniH`前缀 （这表示统一保留）。      |
|就地保留     |     `c0ba3ce811b6432a8751430937152491` <br/> 或 <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*属性将包含邮箱置于就地保留的 GUID。您可以判断这是就地保留 GUID 也不会以前缀开头或使用启动，因为`cld`前缀。     |
|Office 365 专门应用于邮箱的保留策略     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> 或 <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds 属性将包含任何特定位置的保留策略应用于邮箱的 Guid。您可以标识保留策略，因为 GUID 开头`mbx`或`skp`前缀。`skp`前缀表明到 Skype 应用保留策略的用户的邮箱中的业务对话。    |
|从组织范围内的 Office 365 保留策略中排除     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     如果从组织范围内的 Office 365 保留策略中排除邮箱，从排除邮箱的保留策略的 GUID InPlaceHolds 属性中显示，并由`-mbx`前缀。    |

### <a name="get-organizationconfig"></a>Get-organizationconfig
如果运行**Get-mailbox** cmdlet 时， *InPlaceHolds*属性为空，仍可能存在一个或多个组织范围内 Office 365 保留策略应用于邮箱。运行以下命令在 Exchange Online PowerShell，可以获取 Guid 的列表用于组织范围内的 Office 365 保留策略。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> 如果 InPlaceHolds 属性中有太多值而不是全部显示，则可以运行`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`命令单独占一行上显示每个 GUID。

下表介绍不同类型的组织范围内保留项以及如何确定每种类型基于运行**Get-organizationconfig** cmdlet 时*InPlaceHolds*属性中包含的 Guid。


|保留类型  |示例值  |描述  |
|---------|---------|---------|
|Office 365 的保留策略应用于 Exchange 邮箱、 Exchange 公用文件夹和团队聊天    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   组织范围内保留策略应用于 Exchange 邮箱，Exchange 公用文件夹和来开始的 Guid 标识 1xN 聊天中的 Microsoft 团队`mbx`前缀。请注意，1xN 聊天存储在单个聊天参与者的邮箱。      |
|Office 365 的保留策略应用于 Office 365 组和团队通道邮件     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    由开头的 Guid 标识组织范围内保留策略应用于 Office 365 组和 Microsoft 团队中的通道邮件`grp`前缀。请注意，通道消息存储在与 Microsoft 团队相关联的组邮箱。     |

有关详细信息保留策略应用于的 Microsoft 团队，请参阅"团队位置"部分[的保留策略概述](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>了解保留策略的 InPlaceHolds 值的格式

前缀 （mbx、 skp 或组） 的标识为 Office 365 保留策略的 InPlaceHolds 属性中的项目，除了值还包含后缀标识配置策略的保留操作的类型。例如，下面的示例中以粗体突出显示的操作后缀：

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

下表定义的三种可能的保留期操作：

|值  |描述  |
|---------|---------|
|**1**     | 指示保留策略配置为删除的项目;策略不会保留的项目。        |
|**2**    |    指示保留策略已配置为容纳项目;保留期过后，策略不会删除项目。     |
|**3**     |   指示保留策略配置为保留项目，然后再删除它们的保留期过后。      |

有关保留操作的详细信息，请参阅[Overview of 保留策略](retention-policies.md#retaining-content-for-a-specific-period-of-time)中的"在特定时间内的保留内容"部分。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>步骤 2： 使用 GUID 标识保留项

获取应用于邮箱的保留 GUID 后下, 一步是使用该 GUID 标识保留项。使用保留 GUID，以下各节显示如何标识保留项 （和其他信息） 的名称。

### <a name="ediscovery-holds"></a>电子数据展示保留项

若要确定应用于邮箱的电子数据展示保留的安全性和合规性中心 PowerShell 中运行以下命令。使用电子数据展示的 GUID （不包括 UniH 前缀） 保留在步骤 1 中确定。第一个命令创建变量包含保留; 有关信息在其他命令中使用此变量。第二个命令显示与保留电子数据展示事例的名称。第三个命令显示保留项的名称和保留应用于邮箱的列表。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

若要连接到安全性和合规性中心 PowerShell，请参阅[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="in-place-holds"></a>就地保留

在 Exchange Online PowerShell 中标识应用于邮箱就地保留中运行以下命令。使用您在步骤 1 中确定的就地保留的 GUID。该命令显示的保留项的名称和保留应用于邮箱的列表。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
请注意，如果 GUID 的就地保留开头`cld`前缀，请确保包含前缀，运行上述命令时。

### <a name="office-365-retention-policies"></a>Office 365 保留策略

运行以下命令安全性和合规性中心 PowerShell 中标识应用于邮箱的 Office 365 保留策略 （组织范围内或特定位置）。使用您在步骤 1 中确定的 GUID （不包括 mbx、 skp 或组前缀或的操作后缀）。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="next-steps"></a>后续步骤

确定应用于邮箱的保留项后，您可以执行任务更改的保留项的持续时间临时或永久删除保留项，如或 Office 365 保留策略，对于从策略中排除非活动邮箱。有关执行到保留项相关的任务的详细信息，请参阅以下主题之一：

- 运行[集 RetentionCompliancePolicy AddExchangeLocationException\<用户邮箱 >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)中排除的组织范围内的 Office 365 保留策略的邮箱的安全性和合规性中心 PowerShell 命令。请注意，此命令可仅用于保留策略其中*ExchangeLocation*属性的值等于`All`。

- 运行[Set-mailbox ExcludeFromOrgHolds\<前缀或后缀不保留 GUID >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)命令在 Exchange Online PowerShell 中排除的组织范围内的 Office 365 保留策略的非活动邮箱。

- [更改在 Office 365 中的非活动邮箱的保留持续时间](change-the-hold-duration-for-an-inactive-mailbox.md)

- [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

- [删除保留状态云邮箱的“可恢复的项目”文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
