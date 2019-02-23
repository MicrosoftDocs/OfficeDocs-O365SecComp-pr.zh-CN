---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当不再需要保留 Office 365 非活动邮箱的内容时, 可以通过删除保留永久删除非活动邮箱。删除保留后, 非活动邮箱将标记为删除, 并在处理后被永久删除。
ms.openlocfilehash: 0dddbb7c5093519914cbf3a2fc33daf709f0a160
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220842"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>删除 Office 365 中的非活动邮箱

非活动邮箱用于在离开组织后保留以前的员工的电子邮件。当您不再需要保留非活动邮箱的内容时, 可以通过删除保留来永久删除非活动邮箱。此外, 还可以将多个保留放在非活动邮箱上。例如, 非活动邮箱可能放置在诉讼保留和一个或多个就地保留中。此外, office 365 保留策略 (在 office 365 安全&amp;合规中心中创建) 可能会应用于非活动邮箱。您必须从非活动邮箱中删除所有保留和 Office 365 保留策略, 才能将其删除。删除保留和保留策略后, 非活动邮箱将标记为删除, 并在处理之后永久删除。
  
> [!IMPORTANT]
> 我们推迟了创建新的就地保留的2017年7月1日, 将邮箱设为非活动状态。但在今年下半年或明年早些时候, 你将无法在 Exchange Online 中创建新的就地保留。在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。但是, 仍将支持就地保留中的现有非活动邮箱, 并且可以继续管理非活动邮箱的就地保留。这包括更改就地保留的持续时间以及通过删除就地保留来永久删除非活动邮箱。 
  
请参阅[详细信息](delete-an-inactive-mailbox.md#moreinfo)部分了解从非活动邮箱删除保留后会发生什么情况。 
  
## <a name="before-you-begin"></a>开始之前

- 您必须使用 Exchange Online PowerShell 从非活动邮箱删除诉讼保留。您不能使用 Exchange 管理中心 (EAC)。有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。您可以使用 Exchange Online PowerShell 或 EAC 从非活动邮箱中删除就地保留。 
    
- 您可以在删除保留并删除非活动邮箱之前, 将非活动邮箱的内容复制到另一个邮箱。有关详细信息, 请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
    
- 如果从非活动邮箱中删除保留策略或 Office 365 保留策略, 并且邮箱的软删除邮箱保留期已过期, 则邮箱将被永久删除。删除后, 将无法恢复。在删除保留项之前, 请确保不再需要邮箱中的内容。如果要重新激活非活动邮箱, 可以对其进行恢复。有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

如前面所述, 诉讼保留、就地保留或 Office 365 保留策略可能位于非活动邮箱上。第一步是标识非活动邮箱上的保留。
  
运行以下命令，显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

如果**LitigationHoldEnabled**属性的值为**True** , 则表示非活动邮箱处于诉讼保留状态。如果非活动邮箱上放置了就地保留, 则保留的 GUID 将显示为**InPlaceHolds**属性的值。例如, 以下两个非活动邮箱的结果将显示在王 Beebe 上设置了诉讼保留, 并将两个就地保留放在 Pilar Pinilla 上。 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 如果非活动邮箱上放置了大量就地保留, 则不会显示所有就地保留 guid。您可以运行以下命令来显示所有就地保留 guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>步骤 2：从非活动邮箱删除保留

在确定了非活动邮箱上设置的保留类型（以及是否存在多个保留）后，接下来是删除邮箱上的保留。如前所述，您必须删除所有保留后方可永久删除非活动邮箱。 
  
### <a name="remove-a-litigation-hold"></a>删除诉讼保留

如前所述，您必须使用 Windows PowerShell 从非活动邮箱删除诉讼保留。不能使用 EAC。运行以下命令以删除诉讼保留。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 若要识别非活动邮箱，最好的方法是通过其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外地指定了错误的邮箱。 
  
### <a name="remove-in-place-holds"></a>删除就地保留

 有两种方法可以从非活动邮箱删除就地保留： 
  
- **删除就地保留对象**如果要永久删除的非活动邮箱是就地保留的唯一源邮箱, 则只需删除就地保留对象即可。 
    
    > [!NOTE]
    > 您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。 
  
- **删除非活动邮箱作为就地保留的源邮箱**如果要保留对就地保留的其他源邮箱, 可以从源邮箱列表中删除非活动邮箱, 并保留就地保留对象。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 删除就地保留

1. 如果您知晓要删除的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取想要永久删除的非活动邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择要删除的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。
    
4. 在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**就地保留**", 取消选中 "**将与所选邮箱中的搜索查询匹配的内容置于保留**状态" 框中, 然后单击 "**保存**"。
    
5. 在 "**就地电子数据展示&amp;保留**" 页上, 再次选择就地保留, 然后单击 "**删除**![删除图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)"。
    
6. 在警告中, 单击 **"是"** 删除就地保留。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 删除就地保留

1. 创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 禁用就地保留上的该保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. 删除该就地保留。
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 EAC 从就地保留删除非活动邮箱

1. 如果您知晓非活动邮箱上设置的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取该邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择非活动邮箱上放置的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。
    
4. 在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**源**"。
    
5. 在源邮箱列表中, 单击要删除的非活动邮箱的名称, 然后单击 "**删除**![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)"。
    
6. 单击 "**保存**" 以保存更改。将显示一条消息, 指出操作已成功完成。 
    
7. 重复步骤 1 至 6 以删除非活动邮箱上设置的其他就地保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 Exchange Online PowerShell 从就地保留中删除非活动邮箱

如果就地保留包含大量的源邮箱, 则该非活动邮箱可能不会在 EAC 的 "**源**" 页上列出。当您编辑就地保留时, "**源**" 页面上最高可显示3000个邮箱。如果未在 "**源**" 页上列出非活动邮箱, 则可以使用 Exchange Online PowerShell 将其从就地保留中删除。 
  
1. 创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 验证非活动邮箱是否作为就地保留的源邮箱列出。 
    
```
  $InPlaceHold.Sources
```

   **注意:** 就地** 保留的 source 属性通过其*LegacyExchangeDN*属性标识源邮箱。由于此属性唯一标识非活动邮箱, 因此使用就地保留中的*源*属性有助于防止删除错误的邮箱。如果两个邮箱具有相同的别名或 SMTP 地址, 这还有助于避免出现问题。 
   
3. 将非活动邮箱从变量中的源邮箱列表中删除。请务必使用上一步中的命令返回的非活动邮箱的**LegacyExchangeDN** 。 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. 验证非活动邮箱已从变量中的源邮箱列表中删除。
    
```
  $InPlaceHold.Sources
```

5. 使用源邮箱的更新列表（其中不包括非活动邮箱）修改就地保留。
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. 验证非活动邮箱已从就地保留的源邮箱列表中删除。
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>更多信息

- **非活动邮箱是一种软删除邮箱。** 在 Exchange Online 中, 软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中软删除的邮箱保留期为30天。这意味着可以在软删除的30天内恢复邮箱。30天后, 软删除邮箱将标记为永久删除, 并且无法恢复。 
    
- **删除非活动邮箱上的保留后, 会发生什么情况？** 邮箱被视为其他软删除邮箱, 并在30天软删除邮箱保留期过期后标记为永久删除。此保留期从最初将邮箱设为非活动状态的日期开始。此日期称为软删除日期, 即在删除相应的 Office 365 用户帐户时, 或者在使用**删除邮箱**cmdlet 删除 Exchange Online 邮箱时的日期。软删除日期不是删除保留的日期。 
    
- **删除保留后, 是否会立即永久删除非活动邮箱？** 如果非活动邮箱的软删除日期早于30天, 则删除保留后, 将不会永久删除该邮箱。邮箱将标记为永久删除, 并在下一次处理时被删除。 
    
- **软删除邮箱保留期对非活动邮箱有何影响？** 如果非活动邮箱的软删除日期超过了在删除保留的日期之前的30天以上, 则该邮箱将标记为永久删除。但是, 如果非活动邮箱在最近30天内有软删除的日期, 并且删除了保留, 则可以将邮箱恢复到, 直到软删除邮箱保留期过期。有关详细信息, 请参阅[删除或还原 Exchange Online 中的用户邮箱](https://go.microsoft.com/fwlink/?linkid=856835)。软删除邮箱保留期过期后, 请按照恢复非活动邮箱的过程操作。有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- **删除保留后, 如何显示非活动邮箱的相关信息？** 在删除保留并将非活动邮箱还原为软删除邮箱后, 不会通过将*InactiveMailboxOnly*参数与**Get 邮箱**cmdlet 一起使用来返回该邮箱。不过, 您可以使用**SoftDeletedMailbox**命令显示有关邮箱的信息。例如: 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
在上面的示例中, *WhenSoftDeleted*属性标识软删除日期, 在此示例中为2014年10月30日。如果此软删除邮箱之前已删除保留的非活动邮箱, 则它将在*WhenSoftDeleted*属性值之后的30天内永久删除。在这种情况下, 邮箱会在2014年11月30日之后永久删除。

