---
title: 在 Office 365 安全&amp;合规中心中启用存档邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 安全&amp;合规中心启用存档邮箱, 以支持组织的邮件保留、电子数据展示和保留要求。
ms.openlocfilehash: 39cd5fd8d7991b787d95e39e4994dc9b0786522c
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341793"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a>在 Office 365 安全&amp;合规中心中启用存档邮箱
  
Office 365 中的存档 (也称为就地存档) 为用户提供额外的邮箱存储空间。打开存档邮箱后, 用户可以使用 Microsoft Outlook 和 web 上的 outlook (以前称为 outlook web App) 访问存档邮箱中的邮件并将其存储在其存档邮箱中。用户还可以在主邮箱与其存档邮箱之间移动或复制邮件。他们还可以使用 "恢复已删除邮件" 工具, 从存档邮箱中的 "可恢复的项目" 文件夹中恢复已删除的邮件。 
  
> [!TIP]
> Office 365 提供了无限制的存档存储量和自动扩展的存档功能。如果启用了自动扩展存档, 然后达到用户存档邮箱中的初始存储配额, Office 365 将自动添加额外的存储空间。这意味着用户不会用尽邮箱存储空间, 并且在最初启用存档邮箱并为您的组织启用自动扩展存档后, 无需管理任何内容。有关详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。 
  
## <a name="before-you-begin"></a>准备工作

您必须分配有 Exchange Online 中的 "邮件收件人" 角色, 才能启用或禁用存档邮箱。默认情况下, 此角色分配给 Exchange 管理中心中的 "**权限**" 页上的 "收件人管理" 和 "组织管理" 角色组。如果您在安全&amp;合规中心中看不到 "**存档**" 页, 请让管理员为您分配必要的权限。 
  
## <a name="enable-an-archive-mailbox"></a>启用存档邮箱
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **存档**"。
    
    将显示 "**存档**" 页。"**存档邮箱**" 列指示是否为每个用户启用或禁用存档邮箱。 
    
4. 在邮箱的列表中，选择要启用存档邮箱的用户。
    
    ![在选定用户的细节窗格中单击 "启用" 以启用存档邮箱](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. 在所选用户的详细信息窗格中, 单击 "**启用**"。 
    
    将显示一条警告消息, 指出如果您启用存档邮箱, 用户邮箱中早于分配给邮箱的存档策略的项目将移至新的存档邮箱。作为分配给 Exchange Online 邮箱的保留策略的一部分的默认存档策略将项目移至存档邮箱, 在将项目传递到邮箱或由用户创建的日期之后两年。有关详细信息, 请参阅本文中的**详细**信息部分。 
    
6. 单击 **"是"** 启用存档邮箱。 
    
    可能需要几分钟才能创建存档邮箱。创建后, 会在所选用户的详细信息窗格中显示 "**存档邮箱: 已启用**"。您可能需要单击 "**刷新** ![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。 
    
> [!TIP]
> 您还可以通过选择多个已禁用存档邮箱的用户 (使用 Shift 或 Ctrl 键) 来批量启用存档邮箱。选择多个邮箱后, 在详细信息窗格中单击 "**启用**"。 
  
## <a name="disable-an-archive-mailbox"></a>禁用存档邮箱
  
您还可以使用安全**** &amp;合规中心中的 "存档" 页来禁用用户的存档邮箱。禁用存档邮箱后, 可以在禁用存档邮箱后的30天内将其重新连接到用户的主邮箱。在这种情况下, 将还原存档邮箱的原始内容。30天后, 原始存档邮箱的内容将被永久删除且无法恢复。因此, 如果在禁用存档后30天内重新启用存档, 则会创建一个新的存档邮箱。 
  
请注意, 分配给用户邮箱的默认存档策略将项目移动到存档邮箱的时间, 在该项目送达后两年。如果禁用用户的存档邮箱, 则不会对邮箱项目执行任何操作, 它们将保留在用户的主邮箱中。
  
要禁用存档邮箱, 请执行以下操作:
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **存档**"。
    
    将显示 "**存档**" 页。"**存档邮箱**" 列指示是否为每个用户启用或禁用存档邮箱。 
    
4. 在邮箱的列表中，选择要禁用存档邮箱的用户。
    
5. 在详细信息窗格中, 单击 "**禁用**"。 
    
    将显示一条警告消息, 指出您将有30天时间重新启用存档邮箱, 并且30天后, 存档中的所有信息将永久删除。 
    
6. 单击 **"是"** 以禁用存档邮箱。 
    
    可能需要几分钟才能禁用存档邮箱。如果禁用此选项, 则会在所选用户的详细信息窗格中显示 "**存档邮箱: 禁用**"。您可能需要单击 "**刷新** ![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。 
    
> [!TIP]
> 您还可以通过选择具有已启用存档邮箱的多个用户 (使用 Shift 或 Ctrl 键) 来批量禁用存档邮箱。选择多个邮箱后, 在详细信息窗格中单击 "**禁用**"。 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>使用 Exchange Online PowerShell 启用或禁用存档邮箱

您还可以使用 Exchange Online PowerShell 启用存档邮箱。使用 PowerShell 的主要原因是您可以为组织中的所有用户快速启用存档邮箱。

第一步是连接到 Exchange Online PowerShell。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

连接到 Exchange Online 后, 可以运行以下各节中的命令来启用或禁用存档邮箱。

### <a name="enable-archive-mailboxes"></a>启用存档邮箱

运行以下命令, 为单个用户启用存档邮箱。
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

运行以下命令, 为组织中的所有用户启用存档邮箱 (其存档邮箱当前未启用)。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a>禁用存档邮箱

运行以下命令, 为单个用户禁用存档邮箱。
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

运行以下命令, 为组织中的所有用户 (其存档邮箱当前已启用) 禁用存档邮箱。
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a>更多信息
  
- 存档邮箱可帮助您和您的用户满足组织的保留、电子数据展示和保留要求。例如, 您可以使用组织的 Exchange 保留策略将邮箱内容移动到用户的存档邮箱。当您使用安全&amp;合规中心中的内容搜索工具搜索特定内容的用户邮箱时, 还会搜索用户的存档邮箱。在你将诉讼保留或应用 Office 365 保留策略到用户的邮箱时, 存档邮箱中的项目也会保留。
  
- 启用存档邮箱后, 用户可以将邮件存储在其存档邮箱中。用户可以使用 Microsoft Outlook 和 web 上的 outlook 访问其存档邮箱。通过使用这些客户端应用程序中的任何一个, 用户都可以查看其存档邮箱中的邮件, 并在其主邮箱与其存档邮箱之间移动或复制邮件。用户还可以使用 "恢复已删除邮件" 工具, 从存档邮箱的 "可恢复的项目" 文件夹中恢复已删除的邮件。 
  
- 启用存档邮箱后, 您的组织可以利用自动分配给每个邮箱的默认 Exchange 保留策略 (也称为 "邮件记录管理" 或 "MRM 策略")。启用存档邮箱后, 默认的 Exchange 保留策略将自动执行以下操作: 
  
    - 将两年或以上的邮件从用户主邮箱移动到存档邮箱。 
    
    - 将 14 天或以上的邮件从用户主邮箱的"可恢复的项目"文件夹移动到存档邮箱中的"可恢复的项目"文件夹。
    
- 有关存档邮箱和 Exchange 保留策略的详细信息, 请参阅:
    
  - [保留标记和保留策略](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [为 Office 365 组织中的邮箱设置存档和删除策略](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
