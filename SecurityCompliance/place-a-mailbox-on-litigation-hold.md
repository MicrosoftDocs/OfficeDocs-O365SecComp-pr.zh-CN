---
title: 将邮箱放到诉讼保留中
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '将邮箱置于"诉讼保留"以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。 '
ms.openlocfilehash: 9c2d5c77a604e4dbe6e1f1db75142d3bf5790618
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002841"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>将邮箱放到诉讼保留中
 
将邮箱置于“诉讼保留”以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。当您将用户邮箱置于诉讼保留状态时，用户的存档邮箱（如果已启用）中的内容也会置于保留状态。已删除和修改的项会在指定时段内保留，或直到您将邮箱从“诉讼保留”中删除。所有此类邮箱项目均会返回到[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx)搜索中。 
  
> [!IMPORTANT]
> 诉讼保留保留用户邮箱中可恢复邮件文件夹中的项目。根据数量和大小的已删除或修改的项目，可能会快速增加的邮箱的可恢复邮件文件夹大小。默认情况下，可恢复邮件文件夹配置使用高配额。在 Exchange Online 中，您将邮箱置于诉讼保留时自动增加此配额。在 Exchange Server 2013，我们建议您监视置于诉讼保留每周执行以确保它们不达到的可恢复的项目配额限制的邮箱。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，需要知道什么？
<a name="sectionSection0"> </a>

- 估计完成时间：5 分钟
    
- “诉讼保留”设置可能需要 60 分钟才能生效。
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [邮件策略和遵从性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"就地保留"条目。 
    
- 若要将 Exchange Online 邮箱置于诉讼保留状态，必须将它分配的 Exchange Online (计划 2) 许可证。如果邮箱已分配的 Exchange Online (计划 1) 许可证，您必须将其单独 Exchange Online Archiving 的许可证将它置于保留分配。
    
- 如前所述，当您置于诉讼保留用户邮箱中用户的存档邮箱的内容将还置于保持状态。如果您置于诉讼保留 Exchange 混合部署中的本地主邮箱，（如果已启用） 的基于云的存档邮箱还将置于保持状态。
    
- 在 Exchange Online 中，可恢复邮件文件夹的配额自动增加到 100 GB 时您将邮箱置于诉讼保留。此文件夹的默认大小为 30 GB。
    
- 诉讼保留保留已删除的项目，并还保留已修改的项目的原始版本，直到保留被删除。您可以选择指定指定的持续时间段内保留邮箱项目保留持续时间。如果指定保留持续时间段，它是从计算日期收到一条消息，或创建邮箱项目。若要保留符合指定的条件的项目，请使用就地保留来创建基于查询的保留。有关详细信息，请参阅[创建或删除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。
    
- 若要使用命令行管理程序将 Exchange Online 邮箱置于保留状态，您必须使用 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。
    
- 不支持将公用文件夹邮箱置于诉讼保留状态。必须使用就地保留来将公用文件夹置于保留状态。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>使用 EAC 将邮箱置于诉讼保留状态
<a name="sectionSection1"> </a>

1. 转到" **收件人**"\>" **邮箱**"。
    
2. 在用户邮箱列表中，单击您想要将置于诉讼保留状态，邮箱，然后单击**编辑**![编辑图标](media/ITPro-EAC-EditIcon.gif)。
    
3. 在邮箱属性页上，单击**邮箱功能。**
    
4. 在**诉讼保留： 已禁用**，单击**启用**以将置于诉讼保留状态的邮箱。 
    
5. 在**诉讼保留**页上，输入以下可选信息： 
    
  - **诉讼保留持续时间 （天）** 使用此框可以指定当邮箱置于诉讼保留多长时间保留邮箱项目。接收或创建邮箱项目时，将从日期计算持续时间。如果将此框保留为空，项目保留无限期或直到保留被删除。使用天指定持续时间。 
    
  - **注释**使用此框通知用户其邮箱位于诉讼保留。如果他们正在使用 Outlook 2010 或更高版本，注释将显示在用户的邮箱。 
    
  - **URL**使用此框可以将用户定向到有关诉讼保留的详细信息的网站。如果他们使用 Outlook 2010 或更高版本，此 URL 将出现在用户邮箱中。 
    
6. 在**诉讼保留**页上，单击**保存**，然后单击邮箱属性页上的**保存**。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>使用命令行管理程序将邮箱无限期置于诉讼保留状态
<a name="sectionSection2"> </a>

此示例将邮箱 bsuneja@contoso.com 置于诉讼保留状态。邮箱中的项目将无限期保留或保留到删除该保留。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> 当您将邮箱无限期置于诉讼保留状态时（不指定持续时间），将  _LitigationHoldDuration_ 属性邮箱的值设置为  `Unlimited`。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>使用命令行管理程序将邮箱置于诉讼保留状态并将项目保留指定的持续时间
<a name="sectionSection3"> </a>

此示例将邮箱 bsuneja@contoso.com 置于诉讼保留状态，并将项目保留 2555 天（大约 7 年）。 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>使用命令行管理程序在指定持续时间内将所有邮箱置于诉讼保留状态
<a name="sectionSection4"> </a>

您的组织可能需要将所有邮箱数据保存一段指定的时间。在您将组织中的所有邮箱置于诉讼保留状态之前，请考虑以下事项：
  
本示例将组织中的所有用户邮箱置于诉讼保留状态，时间为 1 年（365 天）。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

本示例使用 [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet 检索组织中的所有邮箱，指定收件人筛选器以包含所有用户邮箱，然后将邮箱列表输出到 [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet 以启用诉讼保留和保留持续时间。 
  
要将所有用户邮箱置于无限期保留状态，请运行以前的命令，但不包含  _LitigationHoldDuration_ 参数。 
  
请参阅[详细信息](#moreinfo.md)部分，查看在筛选器中使用其他收件人属性以包含或排除一个或多个邮箱的示例。 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>使用命令行管理程序将邮箱从诉讼保留中删除
<a name="sectionSection5"> </a>

此示例将邮箱 bsuneja@contoso.com 从诉讼保留中删除。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

P
## <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？
<a name="sectionSection6"> </a>

要确认已成功地将邮箱置于诉讼保留状态，请执行以下操作之一：
  
- 在 EAC 中：
    
1. 转到" **收件人**"\>" **邮箱**"。
    
2. 在用户邮箱列表中，单击您想要验证的诉讼保留设置的邮箱，然后单击**编辑**![编辑图标](media/ITPro-EAC-EditIcon.gif)。
    
3. 在邮箱属性页上，单击**邮箱功能。**
    
4. 在**诉讼保留**，验证已启用保留。
    
5. 单击**查看详细信息**，以验证邮箱已发出以及由谁应答上诉讼保留时。您还可以验证或更改在可选值**诉讼保留持续时间 （天）**，**请注意**，和**URL**框。 
    
- 在命令行管理程序中，运行以下命令之一：
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    或者
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    如果邮箱无限期置于诉讼保留状态，则将  _LitigationHoldDuration_ 邮箱属性的值设置为  `Unlimited`。
    
## <a name="more-information"></a>详细信息
<a name="moreinfo"> </a>

- 如果您的组织要求在特定时间段内保留所有邮箱数据，则在将组织中的所有邮箱置于诉讼保留状态之前请考虑以下事项。
    
  - 当您使用以前的命令将组织中的所有邮箱（或匹配指定收件人筛选器的邮箱子集）置于保留状态时，只有在您运行该命令时已存在的邮箱才会置于保留状态。如果您稍后创建了新的邮箱，必须再次运行该命令以将其置于保留状态。如果您频繁地创建新邮箱，您可以将该命令作为一个计划任务，按照所需的频率运行。
    
  - 发出的所有邮箱置于诉讼保留状态，可能会显著影响邮箱大小。组织 Exchange Server 2013 中规划足够的存储，以满足组织的保留要求。
    
  - 可恢复邮件文件夹具有自己的存储限制，因此文件夹中的项目不计入邮箱存储限制。如前所述，长时间内保留邮箱数据将结果中的用户的邮箱中可恢复邮件文件夹的增长和存档。若要容纳这种增加在 Exchange Online，可恢复邮件文件夹的配额自动增加从 30 GB 为 100 GB 时您将邮箱置于诉讼保留。 
    
    在 Exchange Server 2013，可恢复邮件文件夹的默认存储限制也是 30 GB。我们建议您定期监视以确保不会超过此限制此文件夹的大小。有关详细信息，请参阅[Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)。
    
- 前面的命令以将所有邮箱置于的保留使用返回的所有用户邮箱的收件人筛选器。您可以使用其他收件人的属性返回您可以通过管道到**Set-mailbox** cmdlet 以置于诉讼保留这些邮箱的特定邮箱的列表。 
    
    下面是根据常规用户或邮箱属性，使用 **Get-Mailbox** 和 **Get-Recipient** cmdlet 返回部分邮箱的一些示例。这些示例假设已填充相关的邮箱属性（例如  _CustomAttributeN_ 或  _Department_）。
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    您可以在筛选器中使用其他用户邮箱属性来添加或排除邮箱。有关详细信息，请参阅[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)。
    

