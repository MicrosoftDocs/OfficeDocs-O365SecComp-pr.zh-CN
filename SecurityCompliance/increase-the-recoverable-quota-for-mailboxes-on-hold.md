---
title: 为置于保留状态的邮箱增加可恢复项目的配额
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '启用存档邮箱并启用自动扩展以增加的 Office 365 中的邮箱可恢复邮件文件夹大小的存档。 '
ms.openlocfilehash: cd2d07e6ef1637343798ccb71870c8d436f10574
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782089"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>为置于保留状态的邮箱增加可恢复项目的配额

默认保留策略 — 名为默认 MRM 策略 — 即 Exchange Online 中的自动应用于新邮箱包含一个名为可恢复邮件 14 天后移动到存档的保留标记。此保留标记将项目从用户的主邮箱中可恢复邮件文件夹中用户的存档邮箱的可恢复项目文件夹后 14 天保留期项目。对于这种情况，必须启用用户的存档邮箱。如果没有启用存档邮箱，则不执行任何操作，这意味着 14 天保留期过后，在可恢复项目文件夹上的邮箱的保留的项目不会移动到存档邮箱。因为不会删除从邮箱置于保留状态，它有可能，可能会超过可恢复邮件文件夹的存储配额，尤其是用户的存档邮箱未启用。 
  
为了帮助减少超过此限制的机会，可恢复邮件文件夹的存储配额自动增加从 30 GB 为 100 GB 保留发出时对邮箱在 Exchange Online。如果启用存档邮箱，则存档邮箱中可恢复邮件文件夹的存储配额还增加从 30 GB 为 100 GB。如果自动扩展存档功能在 Exchange Online 已启用，用户的存档中可恢复邮件文件夹的存储配额将不受限制。
  
  下表总结了“可恢复项目”文件夹的存储配额。 
  
|**“可恢复的项目”文件夹的位置**|**未置于保留状态的邮箱**|**置于保留状态的邮箱**|
|:-----|:-----|:-----|
|主邮箱  <br/> |30 GB  <br/> |100 GB  <br/> |
|存档邮箱<sup>\*</sup> <br/> |无限制  <br/> |无限制  <br/> |
|**“可恢复的项目”文件夹的总存储配额** <br/> |无限制  <br/> |无限制  <br/> |
   
> [!NOTE]
> <sup>\*</sup>存档邮箱的初始存储配额具有一个 Exchange Online (计划 2) 许可证的用户是 100 GB。但是，当自动扩展存档打开置于保持状态的邮箱、 存储配额同存档邮箱和可恢复邮件文件夹增加到 110 GB。必要时，将设置其他存档存储空间哪些结果中的存档存储无限量。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。 
  
当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：
  
- **启用存档邮箱，启用自动扩展存档**-只需通过启用存档邮箱并将其打开 Exchange 中的自动扩展的存档功能，可以启用不受限制的存储空间留给的可恢复邮件文件夹联机。这将导致 110 GB 的主邮箱和不限制的数量的存储容量用于在用户的存档可恢复邮件文件夹中可恢复邮件文件夹。请参阅如何： [Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。
    
    > [!NOTE]
    > 启用存档以接近超出可恢复邮件文件夹的存储配额的邮箱后，您可能想要运行托管文件夹助理要手动触发助理处理邮箱，以便过期的项目移动可恢复项目文件夹中的存档邮箱。有关说明，请参阅[步骤 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。请注意，可能会将用户邮箱中的其他项移动到新的存档邮箱。请考虑告知用户这可能会发生后启用存档邮箱。 
  
- **创建自定义保留策略上邮箱保留**-除了启用存档邮箱和自动扩展的存档邮箱置于诉讼保留或就地保留，也可以在创建自定义保留策略的邮箱保留。这让我们您将保留策略应用于保持不同于默认 MRM 策略应用于不处于保持状态的邮箱的邮箱。这样可以应用专为置于保持状态的邮箱的保留标记。这包括创建一个新的保留标记为可恢复邮件文件夹。 
    
本主题的剩余部分介绍了为置于保留状态的邮箱创建自定义保留策略的分步步骤。
  
[步骤 1：为“可恢复的项目”文件夹创建自定义保留标记](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[步骤 2： 创建新的保留策略的邮箱置于保留状态](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[步骤 3：为置于保留状态的邮箱应用新的保留策略](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[（可选）步骤 4：运行托管文件夹助理以应用新的保留设置](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>步骤 1：为“可恢复的项目”文件夹创建自定义保留标记

第一步是创建可恢复邮件文件夹的自定义保留标记 （称为保留策略标记或报表）。如前所述，该报表将项目从用户的主邮箱中可恢复邮件文件夹中用户的存档邮箱的可恢复项目文件夹。您需要使用 PowerShell 创建 RPT 可恢复邮件文件夹。不能使用 Exchange 管理员中心 (EAC)。 
  
1. [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. 运行以下命令可创建“可恢复的项目”文件夹的新 RPT：  
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    例如，以下命令将为保留期为 30 天的名为“可恢复的项目在保留邮箱中保留 30 天”的“可恢复的项目”文件夹创建 RPT。这意味着某个项目在“可恢复的项目”文件夹中存在 30 天后，将被移动到用户存档邮箱“可恢复的项目”文件夹中。
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 我们建议可恢复项目报表的保留期 （由_AgeLimitForRetention_参数定义） 是报表将应用于邮箱已删除的邮件保留期限相同。这样，用户的整个已删除的邮件保留期恢复已删除的项目之前他们会移动到存档邮箱。在上面的示例中，保留期设置为 30 天假设的邮箱已删除的邮件保留期限还为 30 天。默认情况下，Exchange Online 邮箱配置为 14 天，保留已删除的项目。但是，您可以更改此设置为 30 天内的最大值。有关详细信息，请参阅[更改在 Exchange Online 邮箱的已删除的邮件保留期限](https://go.microsoft.com/fwlink/p/?LinkId=286940)。 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>步骤 2：为置于保留状态的邮箱创建新的保留策略

下一步是创建新的保留策略，并为其添加保留标记，其中包括在步骤 1 中创建的“可恢复的项目”RPT。这项新策略将在下一步骤中应用于置于保留状态的邮箱。  
  
创建新的保留策略之前，请确定你想要添加的其他保留标记。有关添加到“默认 MRM 策略”的保留标记列表，以及有关创建新的保留标记的信息，请参阅以下内容：
  
- [默认值保留策略在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [支持保留策略标记的默认文件夹](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422)主题中的"创建保留标记"的部分。
    
您可以使用 EAC 或 Exchange Online PowerShell 中创建保留策略。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>使用 EAC 创建保留策略
  
1. 在 EAC 中，转到**合规性管理** \> **保留策略**，然后单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)。
    
2. 在**新的保留策略**页上的在**名称**下，键入描述的保留策略; 目的的名称例如，为**MRM 策略的邮箱置于保留状态**。 
    
3. 在**保留标记**，下单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)。
    
4. 在保留标记的列表中，选择您在步骤 1 中创建可恢复项目报表，然后单击**添加**。
    
    ![选择自定义的“可恢复的项目”保留标记](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. 选择要添加到该保留策略的其他保留标记。例如，可能要添加在默认的 MRM 策略中所含的相同的标记。
    
6. 完成添加保留标记后，请单击**确定**。
    
7. 单击**保存**以创建新的保留策略。 
    
    请注意，在详细信息窗格中显示链接到保留策略的保留标记。
    
    ![在详细信息窗格中显示链接到保留策略的保留标记](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Exchange Online PowerShell 中用于创建保留策略
  
若要为置于保留状态的邮箱创建新的保留策略，请运行以下命令：  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

例如，以下命令将创建保留策略以及上图中显示的链接的保留标记。
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>步骤 3：为置于保留状态的邮箱应用新的保留策略

最后一步是将应用您在步骤 2 到置于保持状态的邮箱在组织中创建新的保留策略。您可以使用 EAC 或 Exchange Online PowerShell 中将保留策略应用于单个邮箱或多个邮箱。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>使用 EAC 应用新的保留策略
  
1. 转到" **收件人**"\>" **邮箱**"。
    
2. 在列表视图中，选择要应用到，将保留策略的邮箱，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
3. 在**用户邮箱**页上，单击**邮箱功能**。
    
4. **保留策略**，下选择您在步骤 2 中创建的保留策略，然后单击**保存**。
    
此外，还可使用 EAC 将保留策略应用到多个邮箱。
  
1. 转到" **收件人**"\>" **邮箱**"。
    
2. 在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。
    
3. 在细节窗格中，单击**更多选项**。
    
4. **保留策略**，下单击**更新**。
    
5. 在**批量分配保留策略**页上，选择您在步骤 2 中创建的保留策略，然后单击**保存**。 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>使用 Exchange Online PowerShell 中新的保留策略应用
  
Exchange Online PowerShell 中可用于将新的保留策略应用于单个邮箱。但实际的 PowerShell 功能是您可以使用它来快速识别所有组织中的邮箱置于诉讼保留或就地保留，并然后应用于所有邮箱上的新的保留策略保留在单个命令。下面是使用 Exchange PowerShell 中将保留策略应用于一个或多个邮箱的一些示例。在步骤 2 中创建保留策略应用的所有示例。
  
本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中置于诉讼保留状态的所有邮箱。
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

本示例将新的保留策略应用于组织中置于就地保留状态的所有邮箱。
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

可以使用 **Get-Mailbox** cmdlet 验证是否已应用新的保留策略。 
  
以下示例可确认之前示例中的命令已将“置于保留状态的邮箱的 MRM 策略”保留策略应用于置于诉讼保留和就地保留状态的邮箱。
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>（可选）步骤 4：运行托管文件夹助理以应用新的保留设置

将新的保留策略应用于置于保持状态的邮箱后，可能需要多达 7 天在 Exchange Online 的托管文件夹助理处理使用新的保留策略中设置这些邮箱。而不是等待托管文件夹助理运行，您可以使用**Start-managedfolderassistant** cmdlet 手动触发助理处理应用到新的保留策略的邮箱。 
  
运行以下命令，启动 Pilar Pinilla 邮箱的托管文件夹助理。
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

运行以下命令，启动置于保留状态的所有邮箱的托管文件夹助理。
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>详细信息

- 启用用户的存档邮箱后，请考虑告知用户，他们的邮箱 （不只是项可恢复邮件文件夹中） 中的其他项可能将移动到存档邮箱。这是因为默认 MRM 策略，分配给 Exchange Online 邮箱包含一个将项目移动到存档邮箱项目已传递到邮箱或创建的日期之后的两年的保留标记 （移动命名默认 2 年进行存档）用户。有关详细信息，请参阅[Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- 启用用户的存档邮箱后，您可能还判断的用户，他们可以恢复已删除其存档邮箱中的可恢复项目文件夹中的项。它们可以通过实现此在 Outlook 中在存档邮箱中，选择**已删除邮件**文件夹，然后单击**主页**选项卡上的**从服务器恢复已删除邮件**。有关恢复已删除项目的详细信息，请参阅[恢复已删除的 Outlook for Windows 中的项目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。 
