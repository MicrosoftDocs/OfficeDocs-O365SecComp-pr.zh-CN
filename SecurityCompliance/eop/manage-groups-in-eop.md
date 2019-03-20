---
title: 在 EOP 中管理组
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。 您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。
ms.openlocfilehash: db649e4fd955d13e50e96007e8e38fe2c1de5b4d
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693294"
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

1. 在 Exchange 管理中心 (EAC) 中, 转到 "**收件人** \> **组**"。
    
2. 单击 "**新建**![添加](../media/ITPro-EAC-AddIcon.gif)图标", 然后单击 "**通讯组**" 或 "**安全组**", 具体取决于您的需要。 请参阅[Types of mail-enabled groups](manage-groups-in-eop.md)了解区别。 
    
3. 在“新建通讯组”**** 或“新建安全组”**** 页面上，填写以下字段： 
    
  - **显示名称**键入您的组织独有的显示名称, 并对 EOP 用户有意义。 显示名称是必填项。 
    
  - **别名**键入一个最高为64个字符的组别名, 这些字符对您的组织是唯一的。 EOP 用户在"收件人"电子邮件行中键入别名，别名会解析成组的显示名称。 如果您更改别名，组的主 SMTP 地址也会更改，并会包含新别名。 别名为必填项。 
    
  - **说明**键入组的说明, 以便用户了解组的用途。 
    
  - **所有者**默认情况下, 创建组的人员是所有者。 您可以通过选择 "**添加**![添加" 图标](../media/ITPro-EAC-AddIcon.gif)来添加所有者。 所有组都必须至少有一个所有者。
    
    > [!NOTE]
    > 所有者不必是组的成员。 
  
  - **成员**使用此部分可以添加组成员, 并指定是否需要审批人员加入或离开组。 若要向组中添加成员, ****![请单击 "](../media/ITPro-EAC-AddIcon.gif)添加添加图标"。
    
4. 单击“确定”**** 返回原始页面。 
    
5. 完成后, 请单击 "**保存**" 以创建组。 此时，新组应该会出现在组列表中。 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a>在 EAC 中编辑或删除组

1. In the EAC, navigate to **Recipients** \> **Groups**.
    
2. 执行下列操作之一：
    
  - 若要编辑组, 请执行以下操作: 在组列表中, 单击要查看或更改的分发或安全组, 然后单击 "**编辑** ![编辑](../media/ITPro-EAC-EditIcon.gif)图标"。 您可以根据需要更新常规设置、添加或删除组所有者，以及添加或删除组成员。
    
  - 若要删除组, 请选择组, 然后****![单击 "删除](../media/ITPro-EAC-RemoveIcon.gif)删除图标"。
    
3. 完成更改后, 请单击 "**保存**"。
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>使用远程 Windows PowerShell 创建、编辑或删除组

本部分提供了有关使用远程 Windows PowerShell 创建组和更改其属性的信息。它还演示了如何删除现有的组。 
  
 **使用远程 Windows PowerShell 创建组**
  
该示例使用 [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet 创建别名为"itadmin"且名称为"IT 管理员"的通信组。还会将用户添加为该组的成员。 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

若要创建安全组，而不是通讯组，请改为指定  `-Type "Security"`。 
  
若要验证已成功创建"IT 管理员"组，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 显示有关新组的信息： 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

若要获取组中成员的列表，请运行 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示： 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

若要获取所有组的完整列表，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示： 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 **使用远程 Windows PowerShell 更改组的属性**
  
使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 查看或更改组的属性。使用远程 PowerShell 代替 EAC 的一个优势是可以更改多个组的属性。 
  
下面是使用远程 Windows PowerShell 更改组属性的一些示例。
  
此示例使用 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 将"西雅图员工"组的主 SMTP 地址（也称为答复地址）更改为 sea.employees@contoso.com。 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

若要验证已成功更改组的属性，请使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 验证更改。使用远程 PowerShell 的一个优势是可以查看多个组的多个属性。在之前更改主 SMTP 地址组的示例中，运行以下命令来验证新值： 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

此示例使用 [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet 更新"西雅图员工"组的所有成员。使用逗号分隔所有成员。 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

若要获取组"西雅图员工"中所有成员的列表，请使用 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示： 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 **使用远程 Windows PowerShell 删除组**
  
此示例使用 [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet 删除名为"IT 管理员"的通讯组。 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

若要验证该组已删除，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示，并确认该组（在此案例中为"IT 管理员"）已删除。 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


