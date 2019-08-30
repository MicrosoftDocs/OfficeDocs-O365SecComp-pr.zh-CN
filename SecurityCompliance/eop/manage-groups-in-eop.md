---
title: 在 EOP 中管理组
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。 您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。
ms.openlocfilehash: 9ce501c5d51561a7be86963ae98b62046995e46f
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676732"
---
# <a name="manage-groups-in-eop"></a>在 EOP 中管理组

 您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。您可以根据需要创建通讯组和安全组。可以使用 Exchange 管理中心 (EAC) 或通过远程 Windows PowerShell 创建这些组。
  
## <a name="types-of-mail-enabled-groups"></a>启用邮件的组的类型

您可以为 Exchange 组织创建两种类型的组：
  
- 通讯组是电子邮件用户 (如团队或其他临时组) 的集合, 这些用户需要接收或发送有关感兴趣的常见领域的电子邮件。 通讯组专用于分发电子邮件。 在 EOP 中，通讯组是指任何启用邮件的组，无论其是否有安全性上下文。

- 安全组是需要管理员角色访问权限的电子邮件用户的集合。 例如，您可能想向特定组的用户授予管理员角色权限，使他们能够配置反垃圾邮件和反恶意邮件设置。

    > [!NOTE]
    > 默认情况下，所有启用邮件的新安全组都要求对所有发件人进行身份验证。这样可防止外部发件人将邮件发送到启用邮件的安全组。
  
## <a name="before-you-begin"></a>准备工作

- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"通讯组和安全组"条目。

- 若要打开 Exchange 管理中心, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。

- 请注意, 在使用 Exchange Online Protection PowerShell cmdlet 创建和管理组时, 可能会遇到限制。

- 本主题中的 PowerShell 过程使用一种批处理方法, 该方法会导致在几分钟内发生传播延迟, 然后才能看到命令的结果。

- 若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。 
  
## <a name="create-a-group-in-the-eac"></a>在 EAC 中创建组

1. 在 EAC 中, 转到 "**收件人** \> **组**"。

2. 单击 "**新建** ![添加](../media/ITPro-EAC-AddIcon.gif)图标", 然后单击 "**通讯组**" 或 "**安全组**", 具体取决于您的需要。

3. 在 "**新建通讯组**" 或 "**新建安全组**" 页上, 配置以下设置:

   - **显示名称**: 键入您的组织独有的显示名称, 并对 EOP 用户有意义。 显示名称是必填项。

   - **别名**: 键入一个最高为64个字符的组别名, 这些字符对您的组织是唯一的。 EOP 用户在"收件人"电子邮件行中键入别名，别名会解析成组的显示名称。 如果您更改别名，组的主 SMTP 地址也会更改，并会包含新别名。 别名为必填项。 

   - **说明**: 键入组的说明, 以便用户了解组的用途。 

   - **所有者**: 默认情况下, 创建组的人员是所有者。 您可以通过选择 "**添加** ![添加" 图标](../media/ITPro-EAC-AddIcon.gif)来添加所有者。 所有组都必须至少有一个所有者。

     > [!NOTE]
     > 所有者不必是组的成员。
  
   - **Members**: 使用此部分可添加组成员并指定是否需要审批人员加入或离开组。 若要向组中添加成员, **** ![请单击 "](../media/ITPro-EAC-AddIcon.gif)添加添加图标"。

4. 单击“确定”**** 返回原始页面。

5. 完成后, 请单击 "**保存**" 以创建组。 此时，新组应该会出现在组列表中。

## <a name="edit-or-remove-a-group-in-the-eac"></a>在 EAC 中编辑或删除组

1. In the EAC, navigate to **Recipients** \> **Groups**.

2. 采取以下步骤之一：

   - 若要编辑组, 请执行以下操作: 在组列表中, 单击要查看或更改的组, 然后单击 "**编辑** ![编辑](../media/ITPro-EAC-EditIcon.gif)图标"。 您可以根据需要更新常规设置、添加或删除组所有者, 以及添加或删除组成员。

   - 若要删除组, 请选择组, 然后**** ![单击 "删除](../media/ITPro-EAC-RemoveIcon.gif)删除图标"。

3. 完成更改后, 请单击 "**保存**"。

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 创建、编辑或删除组

本节提供有关在 Exchange Online Protection PowerShell 中创建组和更改其属性的信息。 它还演示了如何删除现有的组。
  
### <a name="create-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 创建组
  
该示例使用 [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet 创建别名为"itadmin"且名称为"IT 管理员"的通信组。还会将用户添加为该组的成员。
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**注意**: 若要创建安全组, 而不是通讯组, 请使用`Security` *Type*参数的值。
  
若要验证是否成功创建了 IT 管理员组, 请运行以下命令以显示有关新组的信息:
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

有关语法和参数的详细信息, 请参阅 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)"。

若要获取组中成员的列表, 请运行以下命令:
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

有关语法和参数的详细信息, 请参阅[get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)。

若要获取所有组的完整列表, 请运行以下命令:
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 更改组的属性
  
使用 PowerShell (而不是 EAC) 的优势在于能够更改多个组的属性。
  
下面是使用 Exchange Online Protection PowerShell 更改组属性的一些示例。
  
本示例使用将 "西雅图员工" 组的主 SMTP 地址 (也称为 "回复地址") 更改为 sea.employees@contoso.com。
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

有关语法和参数的详细信息, 请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)。

若要验证是否已成功更改了组的属性, 请运行以下命令来验证新值:
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

本示例更新 "西雅图员工" 组的所有成员。 使用逗号分隔所有成员。
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

有关语法和参数的详细信息, 请参阅[EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)。

若要获取组 "西雅图员工" 中所有成员的列表, 请运行以下命令: 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 删除组
  
本示例使用删除名为 "IT 管理员" 的通讯组。
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

有关语法和参数的详细信息, 请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)。

若要验证是否已删除该组, 请运行以下命令, 并确认该组 (在此示例中为 "It 管理员") 已删除。
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
