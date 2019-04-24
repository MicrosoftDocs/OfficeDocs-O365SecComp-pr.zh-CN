---
title: 创建诉讼保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: e4cb614167f89cb6e99d96aa94027ba90d86543e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258362"
---
# <a name="create-a-litigation-hold"></a>创建诉讼保留

您可以将邮箱置于诉讼保留状态, 以保留所有邮箱内容, 包括已删除项目和已修改项目的原始版本。 将用户邮箱置于诉讼保留状态时, 用户的存档邮箱 (如果已启用) 中的内容也会保留。 创建保留时, 可以指定保留持续时间 (也称为*基于时间的保留*), 以便在指定时间段内保留已删除和已修改的项目, 然后从邮箱中永久删除。 或者, 也可以无限期保留内容 (称为*无限保留*), 或者直到删除诉讼保留。 如果您指定保留持续时间段, 则它将根据接收邮件的日期或创建邮箱项目计算得出。 
  
以下是创建诉讼保留时发生的情况。
  
- 被用户永久删除的项目将保留在用户邮箱中的 "可恢复的项目" 文件夹中的保留期。
    
- 用户在 "可恢复的项目" 文件夹中清除的项目将在保留期间保留。
    
- "可恢复的项目" 文件夹的存储配额从 30 gb 增加到 110 gb。
    
- 用户主和存档邮箱中的项目将保留
    
## <a name="before-you-begin"></a>准备工作

- 若要在诉讼保留中放置 Exchange online 邮箱, 必须为其分配 exchange online 计划2许可证。 如果向某个邮箱分配了 Exchange Online 计划1许可证, 则必须为其分配一个单独的 Exchange online 存档许可证以将其置于保留状态。
    

## <a name="place-a-mailbox-on-litigation-hold"></a>将邮箱置于诉讼保留

以下是使用 Exchange 管理中心将邮箱置于诉讼保留状态的步骤。

1. 转到[https://outlook.office.com/ecp](https://outlook.office.com/ecp)并使用全局管理员帐户登录。

2. 单击左侧导航窗格中的 "**收件人 > 邮箱**"。

3. 选择要置于诉讼保留状态的邮箱, 然后单击 "**编辑**"。

4. 在邮箱属性页上, 单击 "**邮箱功能**"。
    
5. 在 "**诉讼保留: 已禁用**" 下, 单击 "**启用**" 以将邮箱置于诉讼保留状态。
    
6. 在 "**诉讼保留**" 页上, 输入以下可选信息: 
    
    - **诉讼保留持续时间 (天)** -使用此框可以创建基于时间的保留, 并指定在将邮箱置于诉讼保留状态时邮箱项目的保留时间。 持续时间从接收或创建邮箱项目的日期开始计算。 当特定项目的保留持续时间过期时, 将不再保留该项目。 如果将此框保留为空, 则会无限期保留项目或删除保留。 使用天指定持续时间。
    
    - **注意**-使用此框可通知用户其邮箱处于诉讼保留状态。 如果用户使用的是 Outlook 2010 或更高版本, 注释将显示在用户邮箱中的 "帐户信息" 页面上。 若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。
    
    - **URL** -使用此框可将用户定向到网站, 以获取有关诉讼保留的详细信息。 如果用户使用的是 Outlook 2010 或更高版本, 则此 URL 将显示在用户邮箱中的 "帐户信息" 页面上。 若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。

7. 单击 "**诉讼保留**" 页上的 "**保存**", 然后单击 "邮箱属性" 页上的 "**保存**"。

### <a name="create-a-litigation-hold-using-powershell"></a>使用 PowerShell 创建诉讼保留

您还可以通过在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行以下命令来创建诉讼保留:

```
Set-Mailbox <username> -LitigationHoldEnabled $true
```

由于未指定保留持续时间, 上一个命令将无限期保留项目。 若要创建基于时间的保留, 请使用以下命令:

```
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

有关详细信息, 请参阅[设置邮箱](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox)。

## <a name="how-does-litigation-hold-work"></a>诉讼保留的工作原理是什么？

在正常的已删除邮件工作流中，当用户永久删除 (Shift + Delete) 或从已删除邮件文件夹中删除某个邮箱项目时，会将该项目移动到"可恢复的项目"文件夹中的"删除"子文件夹。 当保留期到期时，删除策略（这是使用删除保留操作配置的保留标记）也将项目移动到"删除"子文件夹。 当用户清除"可恢复的项目"文件夹中的某个项目时或者当某个项目的已删除邮件保留期到期时，该项目将被移动到"可恢复的项目"文件夹中的"清除"子文件夹并标记为永久删除。 下一次通过托管文件夹助理 (MFA) 处理邮箱时，将从 Exchange 中清除该邮箱。

如果邮箱置于诉讼保留状态，在由诉讼保留指定的保留期限内会保留"清除"子文件中的项目。保留期限自接收或创建项目的原始日期算起，并且定义了保留"清除"子文件中的项目的时长。"清除"子文件中的某个项目的保留期限到期时，将该项目标记为永久删除，并且下一次通过 MFA 处理邮箱时该项目将从 Exchange 中清除。如果邮箱中设置了无限期保留，则永远不会将项目从"清除"子文件中清除。

下图显示了"可恢复的项目"文件夹中的子文件夹和保留工作流程。

![诉讼保留生命周期](media/LitigationHoldLifeCycle.png)

> [!NOTE]
> 如果将与电子数据展示事例关联的保留放在邮箱中, 清除的项目将从 "删除" 子文件夹移动到 "DiscoveryHolds" 子文件夹, 并在邮箱从电子数据展示保留中释放之前保留。
  