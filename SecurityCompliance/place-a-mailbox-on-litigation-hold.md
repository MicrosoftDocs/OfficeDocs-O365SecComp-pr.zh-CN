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
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '将邮箱置于"诉讼保留"以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。 '
ms.openlocfilehash: b2d2a60fddb51aa310d01a765c1ebbbf127ecd19
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296975"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>将邮箱置于诉讼保留
 
将邮箱置于“诉讼保留”以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。当您将用户邮箱置于诉讼保留状态时，用户的存档邮箱（如果已启用）中的内容也会置于保留状态。已删除和修改的项会在指定时段内保留，或直到您将邮箱从“诉讼保留”中删除。所有此类邮箱项目均会返回到[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx)搜索中。 
  
> [!IMPORTANT]
> 诉讼保留保留用户邮箱中的 "可恢复的项目" 文件夹中的项目。根据删除或修改的项目的数量和大小, 邮箱的 "可恢复邮件" 文件夹的大小可能会迅速增加。默认情况下, "可恢复的项目" 文件夹配置了高配额。在 Exchange Online 中, 当你将邮箱置于诉讼保留状态时, 此配额会自动增加。在 Exchange Server 2013 中, 我们建议您每周监视处于诉讼保留状态的邮箱, 以确保它们不会达到可恢复项目配额的限制。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

- 估计完成时间：5 分钟
    
- “诉讼保留”设置可能需要 60 分钟才能生效。
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [邮件策略和遵从性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"就地保留"条目。 
    
- 若要将 Exchange online 邮箱置于诉讼保留状态, 则必须为其分配一个 exchange online (计划 2) 许可证。如果向某个邮箱分配了 Exchange Online (计划 1) 许可证, 则必须为其分配一个单独的 exchange online 存档许可证以将其置于保留状态。
    
- 如前所述, 在对用户邮箱设置诉讼保留时, 用户的存档邮箱中的内容也会置于保留状态。如果对 Exchange 混合部署中的内部部署主邮箱设置了诉讼保留, 则基于云的存档邮箱 (如果已启用) 也将置于保留状态。
    
- 在 Exchange Online 中, 当您将邮箱置于诉讼保留状态时, "可恢复的项目" 文件夹的配额会自动增加到 100 GB。此文件夹的默认大小为 30 GB。
    
- 诉讼保留保留已删除项目, 同时保留已修改项目的原始版本, 直到取消保留。您可以选择指定保留持续时间, 这将保留指定持续时间段内的邮箱项目。如果指定保留持续时间段, 则它将根据接收邮件的日期或创建邮箱项目计算得出。若要保留符合指定条件的项目, 请使用就地保留来创建基于查询的保留。有关详细信息, 请参阅[创建或删除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。
    
- 若要使用命令行管理程序将 Exchange online 邮箱置于保留状态, 则必须使用 Exchange online PowerShell。有关详细信息, 请参阅[使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。
    
- 不支持将公用文件夹邮箱置于诉讼保留状态。必须使用就地保留来将公用文件夹置于保留状态。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>使用 EAC 将邮箱置于诉讼保留状态
<a name="sectionSection1"> </a>

1. 转到" **收件人**"\>" **邮箱**"。
    
2. 在用户邮箱列表中, 单击要置于诉讼保留状态的邮箱, 然后单击 "**编辑** ![编辑图标](media/ITPro-EAC-EditIcon.gif)"。
    
3. 在邮箱属性页上, 单击 "**邮箱功能"。**
    
4. 在 "**诉讼保留: 已禁用**" 下, 单击 "**启用**" 以将邮箱置于诉讼保留状态。 
    
5. 在 "**诉讼保留**" 页上, 输入以下可选信息: 
    
  - **诉讼保留持续时间 (天)** 使用此框可以指定将邮箱置于诉讼保留状态时邮箱项目的保留时间。持续时间从接收或创建邮箱项目的日期开始计算。如果将此框保留为空, 则项目将无限期保留或在删除保留之前进行。使用 "天" 指定持续时间。 
    
  - **注释**使用此框通知用户其邮箱处于诉讼保留状态。如果用户使用的是 Outlook 2010 或更高版本, 注释将显示在用户的邮箱中。 
    
  - **URL**使用此框将用户定向到网站, 以获取有关诉讼保留的详细信息。如果用户使用的是 Outlook 2010 或更高版本, 则此 URL 将显示在用户的邮箱中。 
    
6. 单击 "**诉讼保留**" 页上的 "**保存**", 然后单击 "邮箱属性" 页上的 "**保存**"。 
  
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
    
2. 在用户邮箱列表中, 单击要为其验证诉讼保留设置的邮箱, 然后单击 "**编辑** ![编辑图标](media/ITPro-EAC-EditIcon.gif)"。
    
3. 在邮箱属性页上, 单击 "**邮箱功能"。**
    
4. 在 "**诉讼保留**" 下, 验证保留是否已启用。
    
5. 单击 "**查看详细信息**" 以验证何时将邮箱置于诉讼保留状态和谁。您还可以验证或更改 "可选的**诉讼保留持续时间 (天)**"、"**注释**" 和 " **URL** " 框中的值。 
    
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
    
  - 将所有邮箱置于诉讼保留会显著影响邮箱大小。在 Exchange Server 2013 组织中, 规划足够的存储空间以满足组织的保留要求。
    
  - "可恢复的项目" 文件夹有其自己的存储限制, 因此文件夹中的项目不计入邮箱存储限制。如前所述, 将邮箱数据保留很长一段时间将导致用户邮箱和存档中的 "可恢复的项目" 文件夹的增长。为了适应 Exchange Online 中的这一增长, 当您将邮箱置于诉讼保留状态时, "可恢复的项目" 文件夹的配额会自动从 30 gb 增加到 100 GB。 
    
    在 Exchange Server 2013 中, "可恢复的项目" 文件夹的默认存储限制也是 30 GB。建议您定期监视此文件夹的大小, 以确保其不会达到限制。有关详细信息, 请参阅 "[可恢复的项目" 文件夹](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)。
    
- 对所有邮箱置于保留状态的前一个命令使用返回所有用户邮箱的收件人筛选器。您可以使用其他收件人属性来返回特定邮箱的列表, 然后您可以通过管道将这些邮箱传递给**设置邮箱**cmdlet, 以对这些邮箱进行诉讼保留。 
    
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
    

