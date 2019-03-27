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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当不再需要保留 Office 365 非活动邮箱的内容时, 可以通过删除保留永久删除非活动邮箱。 删除保留后, 非活动邮箱将标记为删除, 并在处理后被永久删除。
ms.openlocfilehash: 51f3181e77db2f36976f01f349f1c628f1e67bcf
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899981"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>删除 Office 365 中的非活动邮箱

非活动邮箱用于在之前的员工离开公司之后保留其电子邮件。 如果您不再需要保留非活动邮箱的内容，可以通过删除保留永久性地删除非活动邮箱。 此外，还可以对非活动邮箱设置多个保留。 例如，非活动邮箱上可以设置诉讼保留以及一个或多个就地保留。 此外, office 365 保留策略 (在 office 365 安全&amp;合规中心中创建) 可能会应用于非活动邮箱。 您必须从非活动邮箱中删除所有保留和 Office 365 保留策略, 才能将其删除。 删除保留和保留策略后, 非活动邮箱将标记为删除, 并在处理之后永久删除。
  
> [!IMPORTANT]
> 我们推迟了最后期限，在 2017 年 7 月 1 后，仍可通过新建就地保留创建非活动邮箱。 But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. 在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。 不过，处于就地保留的现有非活动邮箱仍受支持，可以继续管理这些非活动邮箱的就地保留。 这包括更改就地保留的持续时间，以及通过删除就地保留来永久删除非活动邮箱。 
  
请参阅[More information](#more-information)部分了解从非活动邮箱删除保留后会发生什么情况。 
  
## <a name="before-you-begin"></a>开始之前

- 您必须使用 Exchange Online PowerShell 从非活动邮箱删除诉讼保留。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。 您可以使用 Exchange Online PowerShell 或 EAC 从非活动邮箱中删除就地保留。 
    
- 在删除保留设置和非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱中。 有关详细信息, 请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
    
- 如果从非活动邮箱中删除保留策略或 Office 365 保留策略, 并且邮箱的软删除邮箱保留期已过期, 则邮箱将被永久删除。 在此邮箱删除后，您将无法恢复。 在删除保留设置之前，请确保您不再需要此邮箱中的内容。 如果您想重新激活非活动邮箱，则可以恢复它。 有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

如前面所述, 诉讼保留、就地保留或 Office 365 保留策略可能位于非活动邮箱上。 第一步是识别非活动邮箱上设置的保留。
  
运行以下命令，显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。 如果非活动邮箱被置于就地保留状态，则保留的 GUID 会显示为 **InPlaceHolds** 属性的值。 例如，以下两个非活动邮箱的结果显示 Ann Beebe 设置的是诉讼保留，而 Pilar Pinilla 设置了两个就地保留。 
  
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
> 如果非活动邮箱上设置了许多就地保留，则不会显示所有的就地保留 GUID。 您可以运行以下命令来显示所有就地保留 guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
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

1. 如果您知晓要删除的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取想要永久删除的非活动邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择要删除的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。
    
4. 在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**就地保留**", 取消选中 "**将与所选邮箱中的搜索查询匹配的内容置于保留**状态" 框中, 然后单击 "**保存**"。
    
5. 在 "**就地电子数据展示&amp;保留**" 页上, 再次选择就地保留, 然后单击 "**删除**![删除图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)"。
    
6. 在警告框中，单击“是”**** 删除该就地保留。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 删除就地保留

1. 创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。
    
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

1. 如果您知晓非活动邮箱上设置的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取该邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择非活动邮箱上放置的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。
    
4. 在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**源**"。
    
5. 在源邮箱列表中, 单击要删除的非活动邮箱的名称, 然后单击 "**删除**![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)"。
    
6. 单击“保存”**** 以保存所做的更改。 这将显示一条消息，提示已成功完成该操作。 
    
7. 重复步骤 1 至 6 以删除非活动邮箱上设置的其他就地保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 Exchange Online PowerShell 从就地保留中删除非活动邮箱

如果就地保留中包含大量的源邮箱，则非活动邮箱有可能不会列在 EAC 的“源”页面上****。 在编辑就地保留时，“源”**** 页面上最多显示 3000 个邮箱。 如果未在 "**源**" 页上列出非活动邮箱, 则可以使用 Exchange Online PowerShell 将其从就地保留中删除。 
  
1. 创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 验证非活动邮箱是否作为就地保留的源邮箱列出。 
    
```
  $InPlaceHold.Sources
```

   **注意:** 就地** 保留的 source 属性通过其*LegacyExchangeDN*属性标识源邮箱。 由于此属性唯一标识非活动邮箱, 因此使用就地保留中的*源*属性有助于防止删除错误的邮箱。 如果两个邮箱具有相同的别名或 SMTP 地址，这还有助于避免出现问题。 
   
3. 从变量中的源邮箱列表删除非活动邮箱。 请务必使用上一步中的命令返回的非活动邮箱的**LegacyExchangeDN** 。 
    
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

## <a name="more-information"></a>详细信息

- **非活动邮箱是一种软删除邮箱。** 在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。 Exchange Online 中的软删除邮箱保留期为 30 天。 这意味着该邮箱可以在软删除后 30 天内进行恢复。 30 天后，软删除邮箱将标记为永久删除并且无法恢复。 
    
- **如果删除非活动邮箱的保留设置，后面会怎么样？** 系统会将此邮箱与其他软删除邮箱视为一类，并在 30 天软删除邮箱保留期过期后将其标记为永久删除。 此保留期的起始日以该邮箱初次变为非活动状态的日期为准。 此日期称为软删除日期, 即在删除相应的 Office 365 用户帐户时, 或者在使用**删除邮箱**cmdlet 删除 Exchange Online 邮箱时的日期。 软删除日期不是您删除保留的日期。 
    
- **在您删除非活动邮箱的保留设置后，系统会立即永久删除此邮箱吗？** 如果非活动邮箱的软删除日期是在 30 天之前，则系统不会在您删除保留设置后立即永久删除此邮箱。 该邮箱将标记为永久删除，并在下次处理时删除。 
    
- **软删除邮箱保留期对非活动邮箱有何影响？** 如果非活动邮箱的软删除日期距离之后的保留设置删除日期有 30 多天，则系统会将此邮箱标记为永久删除。 不过，如果距离非活动邮箱的软删除日期还不到 30 天并且您删除保留设置，则您可以在软删除邮箱保留期过期之前恢复此邮箱。 有关详细信息, 请参阅[删除或还原 Exchange Online 中的用户邮箱](https://go.microsoft.com/fwlink/?linkid=856835)。 在软删除邮箱保留期过期后，您可以按照相关步骤操作，恢复非活动邮箱。 有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- **在删除保留设置后，如何显示非活动邮箱的相关信息？** 在删除保留并将非活动邮箱还原为软删除邮箱后, 不会通过将*InactiveMailboxOnly*参数与**Get 邮箱**cmdlet 一起使用来返回该邮箱。 不过, 您可以使用**SoftDeletedMailbox**命令显示有关邮箱的信息。 例如： 
    
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
  
在上面的示例中, *WhenSoftDeleted*属性标识软删除日期, 在此示例中为2014年10月30日。 如果此软删除邮箱之前已删除保留的非活动邮箱, 则它将在*WhenSoftDeleted*属性值之后的30天内永久删除。 在本例中，该邮箱将在 2014 年 11 月 30 日之后永久删除。

