---
title: 在 EOP 中管理组
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: Exchange Online Protection (EOP) 可用于创建启用邮件的 Exchange 组织的组。您还可以使用 EOP 定义或更新指定成员资格、 电子邮件地址和组的其他方面的组属性。
ms.openlocfilehash: 1af39e3a55864a9a87f90e0a00957ebf1631bb45
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003171"
---
# <a name="manage-groups-in-eop"></a>在 EOP 中管理组

 您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。您可以根据需要创建通讯组和安全组。可以使用 Exchange 管理中心 (EAC) 或通过远程 Windows PowerShell 创建这些组。 
  
## <a name="types-of-mail-enabled-groups"></a>启用邮件的组的类型

您可以为 Exchange 组织创建两种类型的组：
  
- [在 EAC 中创建组](manage-groups-in-eop.md)（也称为"通讯组"）是需要接收或发送与共同关心领域相关的电子邮件的电子邮件用户的集合，例如小组或其他临时组。通讯组专用于分发电子邮件。在 EOP 中，通讯组是指任何启用邮件的组，无论其是否有安全性上下文。
    
- [在 EAC 中编辑或删除组](manage-groups-in-eop.md)（也称为"安全组"）是需要获得管理员角色的访问权限的电子邮件用户的集合。例如，您可能想向特定组的用户授予管理员角色权限，使他们能够配置反垃圾邮件和反恶意邮件设置。
    
    > [!NOTE]
    > 默认情况下，所有启用邮件的新安全组都要求对所有发件人进行身份验证。这样可防止外部发件人将邮件发送到启用邮件的安全组。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"通讯组和安全组"条目。 
    
- 请注意，在使用远程 PowerShell cmdlet 创建和管理组时，您可能会遇到限制。
    
- 此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。
    
- 要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用远程 PowerShell 连接到 Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="create-a-group-in-the-eac"></a>在 EAC 中创建组

1. 在 Exchange 管理员中心 (EAC) 中，转到**收件人** \> **组**。
    
2. 单击**新建**![添加图标](../media/ITPro-EAC-AddIcon.gif)，然后单击**通讯组**或**安全组**，根据您的需要。在搜索过程中，请参阅[类型的已启用邮件的组](manage-groups-in-eop.md)。 
    
3. 在**新建通讯组**或**新的安全组**页上，填写以下字段： 
    
  - **显示名称**键入是唯一的组织和 EOP 用户有意义的显示名称。所需的显示名称。 
    
  - **别名**键入组的别名的最多为 64 个字符所特有的组织。EOP 用户在键入的别名： 线电子邮件和别名解析为组的显示名称。如果您更改别名，该组的主 SMTP 地址将还更改，并且将包含新别名。别名是必需的。 
    
  - **说明**键入组的说明，以使人们知道该组的用途。 
    
  - **所有者**默认情况下，创建组的人是所有者。您可以通过选择**添加**添加所有者![添加图标](../media/ITPro-EAC-AddIcon.gif)。所有组必须都有至少一个所有者。
    
    > [!NOTE]
    > 所有者不必是组的成员。 
  
  - **成员**若要添加的组成员并指定是否需要对人员加入或离开该组进行审批，请使用此部分。要添加到组的成员，单击**添加**![添加图标](../media/ITPro-EAC-AddIcon.gif)。
    
4. 单击**确定**返回原始页面。 
    
5. 后完成后，单击**保存**以创建组。新组应出现在组列表。 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>在 EAC 中编辑或删除组

1. 在 EAC 中，导航到**收件人** \> **组**。
    
2. 执行以下操作之一：
    
  - 编辑组： 在组列表中，单击通讯或您想要查看或更改的安全组，然后单击**编辑**![编辑图标](../media/ITPro-EAC-EditIcon.gif)。您可以更新常规设置、 添加或删除组的所有者，以及添加或删除组成员，根据需要。
    
  - 若要删除的组： 选择组，并单击**删除**![删除图标](../media/ITPro-EAC-RemoveIcon.gif)。
    
3. 当您完成更改后时，单击**保存**。
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 创建、编辑或删除组

本部分提供了有关使用远程 Windows PowerShell 创建组和更改其属性的信息。它还演示了如何删除现有的组。 
  
 **使用远程 Windows PowerShell 创建组**
  
该示例使用 [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet 创建别名为"itadmin"且名称为"IT 管理员"的通信组。还会将用户添加为该组的成员。 
  
```
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

若要创建安全组，而不是通讯组，请改为指定  `-Type "Security"`。 
  
若要验证已成功创建"IT 管理员"组，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 显示有关新组的信息： 
  
```
Get-Recipient "IT Administrators" | Format-List

```

若要获取组中成员的列表，请运行 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示： 
  
```
Get-DistributionGroupMember "IT Administrators"

```

若要获取所有组的完整列表，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示： 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **使用远程 Windows PowerShell 更改组的属性**
  
使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 查看或更改组的属性。使用远程 PowerShell 代替 EAC 的一个优势是可以更改多个组的属性。 
  
下面是使用远程 Windows PowerShell 更改组属性的一些示例。
  
此示例使用 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 将"西雅图员工"组的主 SMTP 地址（也称为答复地址）更改为 sea.employees@contoso.com。 
  
```
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

若要验证已成功更改组的属性，请使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 验证更改。使用远程 PowerShell 的一个优势是可以查看多个组的多个属性。在之前更改主 SMTP 地址组的示例中，运行以下命令来验证新值： 
  
```
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

此示例使用 [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet 更新"西雅图员工"组的所有成员。使用逗号分隔所有成员。 
  
```
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

若要获取组"西雅图员工"中所有成员的列表，请使用 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示： 
  
```
Get-DistributionGroupMember "Seattle Employees"

```

 **使用远程 Windows PowerShell 删除组**
  
此示例使用 [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet 删除名为"IT 管理员"的通讯组。 
  
```
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

若要验证该组已删除，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示，并确认该组（在此案例中为"IT 管理员"）已删除。 
  
```
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


