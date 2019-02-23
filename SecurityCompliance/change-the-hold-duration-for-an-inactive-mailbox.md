---
title: 在 Office 365 中更改非活动邮箱的保留期
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: 在 Office 365 邮箱变为非活动状态后, 可以更改分配给非活动邮箱的保留或 Office 365 保留策略的持续时间。保留期定义 "可恢复的项目" 文件夹中的项目的保留时间。
ms.openlocfilehash: 3f92d51505ba8a9a9f4b8e78d0fb79036b6db489
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220612"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>在 Office 365 中更改非活动邮箱的保留期

非活动邮箱用于在离开组织后保留前一个员工的电子邮件。当诉讼保留、就地保留、Office 365 保留策略或与电子数据展示事例相关联的保留在邮箱中时, 邮箱将变为非活动状态, 并且相应的 Office 365 用户帐户将被删除。非活动邮箱的内容会在邮箱处于非活动状态之前放置在邮箱保留期间的保留时间内进行保留。保留期定义 "可恢复的项目" 文件夹中的项目的保留时间。当 "可恢复的项目" 文件夹中某个项目的保留持续时间过期时, 将从非活动邮箱中永久删除 (清除) 该项目。将邮箱设为非活动状态后, 可以更改为非活动邮箱分配的保留或 Office 365 保留策略的持续时间。
  
> [!IMPORTANT]
> 我们推迟了创建新的就地保留的2017年7月1日, 将邮箱设为非活动状态。但在今年下半年或明年早些时候, 你将无法在 Exchange Online 中创建新的就地保留。在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。但是, 仍将支持就地保留中的现有非活动邮箱, 并且可以继续管理非活动邮箱的就地保留。这包括更改就地保留的持续时间以及通过删除就地保留来永久删除非活动邮箱。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。您不能使用 Exchange 管理中心 (EAC)。但您可以使用 Exchange Online PowerShell 或 EAC 更改就地保留的保留期。您可以使用 office 365 安全&amp;合规中心或安全&amp;合规性中心 PowerShell 更改 Office 365 保留策略的保留期。
    
- 若要连接到 Exchange Online powershell 或&amp;安全合规中心 PowerShell, 请参阅下列主题之一:
    
  - [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [连接到 Office 365 安全与合规中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 请注意, 与电子数据展示事例关联的保留是无限的, 这意味着没有可更改的保留持续时间。项目永久保留, 或者在删除保留和删除非活动邮箱之前进行。
    
- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

由于不同类型的保留或一个或多个 Office 365 保留策略可能放置在非活动邮箱上, 因此第一步是标识非活动邮箱上的保留。
  
在 Exchange Online PowerShell 中运行以下命令, 以显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
如果**LitigationHoldEnabled**属性的值为**True** , 则表示非活动邮箱处于诉讼保留状态。如果非活动邮箱上设置了就地保留、电子数据展示保留或 Office 365 保留策略, 则保留或保留策略的 GUID 将显示为**InPlaceHolds**属性的值。例如, 以下显示5个非活动邮箱的结果。 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
下表列出了用于将每个邮箱设为非活动状态的五种不同的保留类型。
  
|**非活动邮箱**|**保留类型**|**如何标识非活动邮箱上的保留**|
|:-----|:-----|:-----|
|王小姐 Beebe  <br/> |诉讼保留  <br/> |*LitigationHoldEnabled*属性设置为`True`。  <br/> |
|Pilar Pinilla  <br/> |就地保留  <br/> |*InPlaceHolds*属性包含非活动邮箱上设置的就地保留的 GUID。您可以指示这是就地保留, 因为 ID 不以前缀开头。<br/> 您可以使用 Exchange `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` Online PowerShell 中的命令来获取非活动邮箱的就地保留的相关信息。  <br/> |
|Mario Necaise  <br/> |安全&amp;合规中心中的组织范围内的 Office 365 保留策略  <br/> |*InPlaceHolds*属性为空。这表示一个或多个组织范围或 (Exchange wide) Office 365 保留策略应用于非活动邮箱。在这种情况下, 您可以`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`在 Exchange Online PowerShell 中运行命令, 以获取组织范围内的 Office 365 保留策略的 guid 列表。应用于 Exchange 邮箱的组织范围的保留策略的 GUID 以`mbx`前缀开头;例如`mbxa3056bb15562480fadb46ce523ff7b02`。<br/> <br/>若要标识应用于非活动邮箱的 Office 365 保留策略, 请在安全&amp;合规中心 PowerShell 中运行以下命令。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |应用于特定邮箱的安全&amp;合规性中心中的 Office 365 保留策略  <br/> |*InPlaceHolds*属性包含应用于非活动邮箱的 Office 365 保留策略的 GUID。您可以告诉这是应用于特定邮箱的保留策略, 因为 GUID 以`mbx`前缀开头。请注意, 如果应用于非活动邮箱的保留策略的 GUID 是使用`skp`前缀启动的, 则表示该保留策略应用于 Skype for business 会话。<br/><br/> 若要标识应用于非活动邮箱的 Office 365 保留策略, 请在安全&amp;合规中心 PowerShell 中运行以下命令。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>运行此命令时, `mbx`请`skp`务必删除或前缀。  <br/> |
|Abraham McMahon  <br/> |安全&amp;合规中心中的电子数据展示事例保留  <br/> |*InPlaceHolds*属性包含非活动邮箱上所放置的电子数据展示事例保留的 GUID。你可以告诉这是电子数据展示事例保留, 因为 GUID 以`UniH`前缀开头。<br/> 您可以使用安全`Get-CaseHoldPolicy` &amp;合规中心 PowerShell 中的 cmdlet 来获取有关非活动邮箱上的保留的电子数据展示事例的相关信息。例如, 您可以运行命令`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`以显示非活动邮箱上的事例保留的名称。运行此命令时, `UniH`请务必删除前缀。<br/><br/> 若要标识非活动邮箱上的保留的电子数据展示事例与关联, 请运行以下命令。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注意:** 建议不要对非活动邮箱使用电子数据展示保留。这是因为电子数据展示事例适用于与法律问题相关的特定的与时间绑定的情况。有时, 法律案例可能会结束, 与事例关联的保留将被删除, 并且电子数据展示事例将关闭 (或删除)。实际上, 如果在非活动邮箱上设置的保留与电子数据展示事例相关联, 并且已释放保留或电子数据展示事例关闭或删除, 则非活动邮箱将被永久删除。 

有关 Office 365 保留策略的详细信息, 请参阅[保留策略概述](retention-policies.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>第 2 步：更改非活动邮箱的保留期

在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>更改诉讼保留的保留期

下面介绍了如何使用 Exchange Online PowerShell 更改非活动邮箱上的诉讼保留的保留期。您不能使用 EAC。运行以下命令以更改保留持续时间。在此示例中, 保留期更改为无限制的时间段。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

结果是非活动邮箱中的项目会无限期保留, 或者直到删除保留或保留持续时间更改为其他值。
  
> [!TIP]
> 标识非活动邮箱的最佳方式是使用**可分辨名称**或 **Exchange GUID** 值。使用下列值之一有助于避免意外指定错误的邮箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>更改就地保留的保留期

 您可以使用 EAC 或 Exchange Online PowerShell 更改就地保留的保留期。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>使用 EAC 更改保留期

1. 如果您知道要更改的就地保留的名称, 请转到下一步。否则, 请运行以下命令以获取非活动邮箱上设置的就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择要更改的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。
    
4. 编辑图标 
    
5. 。
    
1. 在"就地电子数据展示和保留"属性页上，单击"就地保留"。 
    
2. 单击 "**指定天数" 以相对于其接收日期保留项目**, 以保留特定时段内的项目。键入要为其保留项目的天数。 
    
    ![单击"指定自接收日期起保留邮件的天数"可以在特定的时间段内保留项目。](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. 键入所需的项目保留天数。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>使用 Exchange Online PowerShell 更改保留期

1. 如果您知道要更改的就地保留的名称, 请转到下一步。否则, 请运行以下命令以获取非活动邮箱上设置的就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获取的就地保留 GUID。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 运行以下命令，更改保留期。在此示例中，更改后的保留期为 2,555 天（大约 7 年）。 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     运行以下命令，更改保留期。
  
## <a name="more-information"></a>更多信息

- **如何计算非活动邮箱中项目的保留期？** 保留期从邮箱项目的接收或创建原始日期开始计算。 
    
- **保留持续时间过期时会发生什么？** 当 "可恢复的项目" 文件夹中某个邮箱项目的保留持续时间过期时, 将从非活动邮箱中永久删除 (清除) 此项目。如果没有为非活动邮箱上的保留指定持续时间, 则永远不会清除 "可恢复的项目" 文件夹中的项目 (除非对非活动邮箱的保留期进行了更改)。 
    
- **是否仍在非活动邮箱上处理 Exchange 保留策略？** 如果将 exchange 保留策略 (exchange Online 中的邮件记录管理或 MRM) 应用于邮箱 (如果某个邮箱处于非活动状态), 则删除策略 (是使用**删除**保留操作配置的保留标记) 将继续在非活动邮箱上进行处理。这意味着, 当保留期到期时, 使用删除策略标记的项目将移动到 "可恢复的项目" 文件夹中。在项目的保留期过期时, 这些项目会从非活动邮箱中清除。 
    
    相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 **MoveToArchive** 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的“可恢复的项目”文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 
    
- **若要检查新的保留持续时间, 请运行以下命令之一。** 第一个命令适用于诉讼保留;第二个用于就地保留。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **与常规邮箱一样, 托管文件夹助理 (MFA) 也处理非活动邮箱。** 在 Exchange Online 中, MFA 大约每7天处理一次邮箱。更改非活动邮箱的保留期后, 可以使用**start-managedfolderassistant** cmdlet 立即开始处理非活动邮箱的新保留期。运行以下命令。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果非活动邮箱上放置了很多保留项, 则不会显示所有保留 guid。** 您可以运行以下命令来显示非活动邮箱上的所有保留项 (诉讼保留除外) 的 guid。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
