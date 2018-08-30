---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当不再需要保留的 Office 365 非活动邮箱内容时，可以永久删除非活动邮箱中删除该保留。后删除保留，非活动邮箱标记为删除，则在处理后将被永久删除。
ms.openlocfilehash: 91b73fff6ca319735289abe7ea9351b5fba931a0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524876"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>删除 Office 365 中的非活动邮箱

非活动邮箱用于保留以前员工的电子邮件，他/她离开组织之后。当不再需要保留的非活动邮箱内容时，可以永久删除非活动邮箱中删除该保留。另外，还有可能多个保留中可能置于非活动邮箱。例如，可能会在诉讼保留和上一个或多个就地保留放非活动邮箱。此外，Office 365 保留策略 (在 Office 365 安全性中创建&amp;合规性中心) 可能应用于非活动邮箱。您必须将其删除非活动邮箱中删除所有保留项和 Office 365 保留策略。删除保留和保留策略后，非活动邮箱标记为删除，则在处理后将被永久删除。
  
> [!IMPORTANT]
> 我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。 
  
请参阅[详细信息](delete-an-inactive-mailbox.md#moreinfo)部分了解从非活动邮箱删除保留后会发生什么情况。 
  
## <a name="before-you-begin"></a>开始之前

- 您必须使用 Exchange Online PowerShell 中，从非活动邮箱中删除诉讼保留。不能使用 Exchange 管理员中心 (EAC)。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。您可以使用 Exchange Online PowerShell 中或 EAC 从非活动邮箱删除就地保留。 
    
- 删除保留和删除非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱。有关详细信息，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
    
- 如果从非活动邮箱删除保留或 Office 365 保留策略和邮箱软删除邮箱保留期内已过期，则将永久删除邮箱。删除后，将无法恢复。删除保留之前，请确保您不再需要的邮箱中的内容。如果您想要重新激活非活动邮箱，则可以恢复它。有关详细信息，请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- 有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

如前面所述，可能上非活动邮箱置于诉讼保留、 就地保留，或 Office 365 的保留策略。第一步是确定在非活动邮箱保留。
  
运行以下命令，显示组织中所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled**属性的值为**True**指示非活动邮箱位于诉讼保留。如果放置在非活动邮箱就地保留，保留项的 GUID 显示为**InPlaceHolds**属性的值。例如，两个非活动邮箱的以下结果显示诉讼保留将置于 Ann Beebe 和的两个就地保留被放置在 Pilar Pinilla。 
  
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
> 如果大量的就地保留被放置在非活动邮箱中，将显示不是所有就地保留 Guid。您可以运行以下命令以显示所有就地保留 Guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
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
  
- **删除就地保留对象**如果您想要永久删除非活动邮箱是就地保留的唯一源邮箱，您可以只删除就地保留对象。 
    
    > [!NOTE]
    > 您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。 
  
- **删除非活动邮箱作为源邮箱的就地保留**如果您想要保留的就地保留的其他源邮箱，您可以从的源邮箱列表中删除非活动邮箱并保留就地保留对象。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>使用 EAC 删除就地保留

1. 如果您知晓要删除的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取想要永久删除的非活动邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
<<<<<<< 头
3. 选择您想要删除就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
=======
3. 选择您想要删除就地保留，然后单击**编辑**！[编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
>>>>>>> markjjo 转换
    
4. 在**就地电子数据展示&amp;保留**属性页上，单击**就地保留**，取消选中**选定的邮箱中的搜索查询匹配上的位置内容保留**框中，，然后单击**保存**。
    
5. 在**就地电子数据展示&amp;保留**页上，再次选择就地保留命令，然后单击**删除**![删除图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。
    
6. 在警告框中，单击**是**以删除就地保留。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>使用 Exchange Online PowerShell 中删除就地保留

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
    
3. 选择放置在非活动邮箱，就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 在**就地电子数据展示&amp;保留**属性页上，单击**源**。
    
5. 在源邮箱的列表中，单击您想要删除非活动邮箱的名称，然后单击**删除**![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)。
    
6. 单击**保存**以保存更改。将显示一条消息，告知操作已成功完成。 
    
7. 重复步骤 1 至 6 以删除非活动邮箱上设置的其他就地保留。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>使用 Exchange Online PowerShell 中删除非活动邮箱就地保留

如果就地保留包含大量的源邮箱，则可能不会在 EAC 中的**源**页上列出非活动邮箱。最多 3000 邮箱时将显示在**源**页上，编辑就地保留。如果非活动邮箱不在**源**页上列出，您可以使用 Exchange Online PowerShell 中删除就地保留从。 
  
1. 创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 验证非活动邮箱是否作为就地保留的源邮箱列出。 
    
```
  $InPlaceHold.Sources
```

   **注意：** 就地保留的*源*属性由其*LegacyExchangeDN*属性标识的源邮箱。因为此属性用于唯一标识非活动邮箱，使用就地保留的*源*属性有助于防止删除错误的邮箱。这还有助于避免出现问题，如果两个邮箱具有相同的别名或 SMTP 地址。 
   
3. 从变量中的源邮箱列表中删除非活动邮箱。请务必使用上一步中的命令返回非活动邮箱**LegacyExchangeDN** 。 
    
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

- **非活动邮箱是一种软删除邮箱。** 在 Exchange Online 中，软删除邮箱是已删除，但可以在特定的保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着正在软删除 30 天内，可以恢复邮箱。30 天后软删除邮箱标记为永久删除，并且无法恢复。 
    
- **删除非活动邮箱的保留项后，会发生什么情况？** 邮箱视为其他软删除邮箱和 30 天软删除邮箱保留期过后标记为永久删除。此保留期启动邮箱首先建立时处于非活动状态的日期。此日期称为软删除日期，是已删除相应的 Office 365 用户帐户或使用**Remove-mailbox** cmdlet 删除 Exchange Online 邮箱时的日期。软删除日期不是您在其删除保留项的日期。 
    
- **立即后删除该保留永久删除非活动邮箱？** 如果非活动邮箱的软删除日期已超过 30 天，只要删除保留，不会永久删除邮箱。邮箱将标记为永久删除，并删除的下次处理。 
    
- **软删除邮箱保留期如何影响非活动邮箱？** 如果非活动邮箱的软删除日期为 30 天保留已删除的日期之前，邮箱为永久删除标记。但是，如果非活动邮箱已最近 30 天内的软删除日期，并且您删除保留，直到软删除邮箱保留期到期，则可以恢复邮箱。有关详细信息，请参阅[删除或还原 Exchange 在 Online 用户邮箱](https://go.microsoft.com/fwlink/?linkid=856835)。软删除邮箱保留期过后，您已按照非活动邮箱恢复过程。有关详细信息，请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。
    
- **保留被删除之后如何显示有关非活动邮箱的信息？** 保留被删除和非活动邮箱恢复为软删除邮箱后，它不会返回*InactiveMailboxOnly*参数使用**Get-mailbox** cmdlet。但您可以通过使用**Get-mailbox SoftDeletedMailbox**命令显示有关邮箱的信息。例如： 
    
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
  
在上述示例中， *WhenSoftDeleted*属性标识的软删除日期，它在本例中为 2014 年 10 月 30 日。如果此软删除邮箱以前为其保留已删除非活动邮箱，它将永久删除 30 天后*WhenSoftDeleted*属性的值。在这种情况下，邮箱之后 2014 年 11 月 30 日永久删除。

