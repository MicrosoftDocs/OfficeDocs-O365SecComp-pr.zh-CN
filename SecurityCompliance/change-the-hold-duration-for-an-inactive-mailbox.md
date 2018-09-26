---
title: 更改在 Office 365 中的非活动邮箱的保留持续时间
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 邮箱进行非活动状态后，您可以更改保持或 Office 365 分配给非活动邮箱的保留策略的持续时间。保留持续时间定义在可恢复项目文件夹保留多长时间的项目。
ms.openlocfilehash: e3d1d6c7ec0311813dfa1144cc960d2fed9e160d
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038055"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>更改在 Office 365 中的非活动邮箱的保留持续时间

非活动邮箱用于保留以前员工的电子邮件，他/她离开组织之后。邮箱变为非活动状态时诉讼保留、 就地保留、 Office 365 保留策略，或保留与电子数据展示事例相关联的置于邮箱，并删除相应的 Office 365 用户帐户。非活动邮箱的内容将保留在邮箱发出，已处于非活动状态的保留项的持续时间。保留持续时间定义在可恢复项目文件夹保留多长时间的项目。保留持续时间过后可恢复邮件文件夹中的项，该项被永久删除 （清除） 从非活动邮箱。非活动邮箱后，您可以更改保持或 Office 365 分配给非活动邮箱的保留策略的持续时间。
  
> [!IMPORTANT]
> 我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须使用 Exchange Online PowerShell 中，若要更改的非活动邮箱诉讼保留的保留持续时间。不能使用 Exchange 管理员中心 (EAC)。但您可以使用 Exchange Online PowerShell 中或 EAC 若要更改保留持续时间的就地保留。您可以使用 Office 365 安全性&amp;合规性中心或安全&amp;合规性中心 PowerShell，可以更改的 Office 365 保留策略的保留持续时间。
    
- 连接到 Exchange Online PowerShell 中或安全&amp;合规性中心 PowerShell 中，请参阅以下主题之一：
    
  - [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [连接到 Office 365 安全与合规中心 PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 请注意，包含与电子数据展示事例关联是无限期保留，这意味着没有可更改没有保留持续时间。不限次数或直到保留被删除，并删除非活动邮箱保留项。
    
- 有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>第 1 步：识别非活动邮箱上设置的保留

由于不同类型的保留项或一个或多个 Office 365 保留策略可能放置在非活动邮箱中，第一步是确定在非活动邮箱保留。
  
运行以下命令在 Exchange Online PowerShell，可以显示组织中的所有非活动邮箱的保留信息。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**LitigationHoldEnabled**属性的值为**True**指示非活动邮箱位于诉讼保留。如果就地保留电子数据展示保留，或 Office 365 保留策略放置在非活动邮箱，保留或保留策略的 GUID 显示为**InPlaceHolds**属性的值。例如，下面的示例显示 5 的非活动邮箱的结果。 
  
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
   
下表标识用于使每个邮箱处于非活动状态的五个不同的保留类型。
  
|**非活动邮箱**|**保留类型**|**如何标识非活动邮箱的保留项**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |诉讼保留  <br/> |*LitigationHoldEnabled*属性设置为`True`。  <br/> |
|Pilar Pinilla  <br/> |就地保留  <br/> |*InPlaceHolds*属性将包含非活动邮箱置于就地保留的 GUID。您可以判断这是就地保留因为 ID 不以前缀开头。<br/> 您可以使用 Get-mailboxsearch InPlaceHoldIdentity<hold GUID> | FL 命令在 Exchange Online PowerShell 中获得非活动邮箱上的就地保留的信息。  <br/> |
|Mario Necaise  <br/> |组织范围内安全中的 Office 365 保留策略&amp;合规性中心  <br/> |*InPlaceHolds*属性为空。这指示的一个或多个组织范围或 （Exchange 范围） Office 365 保留策略应用于非活动邮箱。在这种情况下，您可以运行 Get-organizationconfig | Select-object-ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名称<br/><br/>
|康 Olson  <br/> |Office 365 安全中的保留策略&amp;合规性中心于特定邮箱  <br/> |*InPlaceHolds*属性将包含 Office 365 保留策略应用于非活动邮箱的 GUID。您可以判断这是因为 GUID 开头应用于特定邮箱的保留策略`mbx`前缀。请注意，如果的保留策略应用于非活动邮箱 GUID 入门`skp`，指明的保留策略应用于 Skype 业务对话的前缀。<br/><br/> 到标识 Office 365 应用于非活动邮箱的保留策略，运行以下命令在安全&amp;合规性中心 PowerShell。<br/><br/> Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名称` <br/><br/>Be sure to remove the  `mbx` or  `skp 前缀当运行此命令。  <br/> |
|当年 McMahon  <br/> |在安全保留电子数据展示事例&amp;合规性中心  <br/> |*InPlaceHolds*属性包含放置在非活动邮箱的电子数据展示案例保留项的 GUID。您可以判断这是电子数据展示案例保留，因为 GUID 开头`UniH`前缀。<br/> 您可以使用`Get-CaseHoldPolicy`cmdlet 中安全&amp;合规性中心 PowerShell，可以获取关于电子数据展示案例非活动邮箱的保留项关联的信息。例如，可以运行命令 Get CaseHoldPolicy<hold GUID without prefix> | FL 名称` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `Get ComplianceCase $CaseHold.CaseId | FL 名称<br/><br/><br/> **注意：** 我们不建议使用电子数据展示保留为非活动邮箱。这是因为电子数据展示事例适用于特定的时间限制的情况下相关法律问题。有时，很可能会法律案件和保留与案例关联将被删除，将电子数据展示事例关闭 （或删除）。实际上，如果放置在非活动邮箱的保留电子数据展示事例，与相关联和释放保留项或关闭电子数据展示事例或将其删除，非活动邮箱将被永久删除。 

有关 Office 365 保留策略的详细信息，请参阅[Overview of 保留策略](retention-policies.md)。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>第 2 步：更改非活动邮箱的保留期

在确定了非活动邮箱上设置的保留的类型（以及是否设置多个保留）后，下一步就要更改保留期了。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>更改诉讼保留的保留期

下面是如何使用 Exchange Online PowerShell 中的非活动邮箱置于诉讼保留更改保留持续时间。不能使用 EAC。运行以下命令以更改保留持续时间。本示例中，保留持续时间变为无限期的时间。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

结果是无限期或直到保留被删除或保留持续时间更改为不同的值，将保留非活动邮箱中的项目。
  
> [!TIP]
> 标识非活动邮箱的最佳方式是使用**可分辨名称**或 **Exchange GUID** 值。使用下列值之一有助于避免意外指定错误的邮箱。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>更改就地保留的保留期

 您可以使用 EAC 或 Exchange Online PowerShell 中，若要更改保留持续时间的就地保留。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>使用 EAC 更改保留期

1. 如果您知道您想要更改的就地保留的名称，请转到下一步。否则，运行以下命令以获取非活动邮箱置于就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获得的就地保留 GUID。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
3. 选择您想要更改，就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. 编辑图标 
    
5. 。
    
1. 在"就地电子数据展示和保留"属性页上，单击"就地保留"。 
    
2. 单击要在特定时间保留项目的**指定天数保留项目相对于其接收日期**。键入您想要保留的项目的天数。 
    
    ![单击"指定自接收日期起保留邮件的天数"可以在特定的时间段内保留项目。](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. 键入所需的项目保留天数。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>使用 Exchange Online PowerShell 中更改保留持续时间

1. 如果您知道您想要更改的就地保留的名称，请转到下一步。否则，运行以下命令以获取非活动邮箱置于就地保留的名称。使用您在[步骤 1](#step-1-identify-the-holds-on-an-inactive-mailbox)中获得的就地保留 GUID。

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
    
- **保留持续时间过期时，会发生什么情况？** 保留持续时间过后可恢复邮件文件夹中的邮箱项，该项被永久删除 （清除） 从非活动邮箱。如果没有为非活动邮箱置于保留指定的持续时间，可恢复邮件文件夹中的项目永远不会被清除 （除非已更改为非活动邮箱的保留持续时间）。 
    
- **是仍在非活动邮箱上处理 Exchange 保留策略？** 如果 （邮件传递记录管理或 MRM，Exchange Online 中的功能） 的 Exchange 保留策略应用于邮箱已处于非活动状态时，将删除策略 （即配置**删除**保留操作的保留标记）继续在非活动邮箱上进行处理。这意味着用删除策略标记的项目移动到可恢复邮件文件夹保留期到期时。为某个项目的保留持续时间过期时，这些项目然后会清除从非活动邮箱。 
    
    相反，分配给非活动邮箱的保留策略中包含的所有存档策略（配置了 **MoveToArchive** 保留操作的保留标记）会遭到忽略。也就是说，在保留期过期时，非活动邮箱中标记有存档策略的项目会保留在主邮箱中。这些项目不会移到存档邮箱或其中的“可恢复的项目”文件夹内。由于用户无法登录非活动邮箱，因此没有理由消耗数据中心资源来处理存档策略。 
    
- **若要检查新保留持续时间，请运行以下命令之一。** 第一个命令是诉讼保留;第二个是就地保留。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **像常规邮箱托管文件夹助理 (MFA) 还处理非活动邮箱。** 在 Exchange Online 中，MFA 每 7 天的大约一次处理邮箱。更改非活动邮箱的保留持续时间后，您可以使用**Start-managedfolderassistant** cmdlet 立即开始处理非活动邮箱的新保留持续时间。运行以下命令。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **如果大量的保留项被放置在非活动邮箱，并非所有保留项将显示 Guid。** 您可以运行以下命令以显示的所有 （除诉讼保留） 保留放置在非活动邮箱的 Guid。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
