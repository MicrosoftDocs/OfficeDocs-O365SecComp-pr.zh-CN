---
title: 授予用户访问 Office 365 安全性&amp;合规性中心
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/18/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户需要为其分配权限 Office 365 安全性&amp;合规性中心之前可以管理其安全性或合规性功能的任何。
ms.openlocfilehash: e0c8b655b1b3300e4ffa9aba1d94e65a9ef26121
ms.sourcegitcommit: 2e41cc24ad92005084f2ba432e724bdcc4e295ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450737"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a>授予用户访问 Office 365 安全性&amp;合规性中心

用户需要为其分配权限 Office 365 安全性&amp;合规性中心之前可以管理其安全性或合规性功能的任何。为 Office 365 全局管理员或安全中 OrganizationManagement 角色组的成员&amp;合规性中心，您可以向用户授予这些权限。用户仅能用于管理您允许他们访问安全性或合规性功能。 
  
有关不同的权限的详细信息可以授予用户安全中&amp;合规性中心，签出[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您必须是 Office 365 全局管理员或安全中 OrganizationManagement 角色组的成员&amp;合规性中心，以完成本文中的步骤。
    
- 安全角色组&amp;合规性中心可能类似的角色组的名称，在 Exchange Online 中，但它们不相同。 
    
- 角色组成员身份不共享之间 Exchange Online 和安全&amp;合规性中心。
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 Office 365 管理中心让安全的另一个用户访问&amp;合规性中心

1. [登录到 Office 365 并转到 Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275)。
    
2. 在 Office 365 管理中心中，打开**管理中心**，然后单击**安全&amp;合规性**。 
    
3. 安全中&amp;合规性中心中，转到**权限**。
    
4. 从列表中，选择您想要向其中添加用户并单击**编辑**角色组![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
5. 在**成员**下的角色组的属性页上，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)选择的名称您想要添加的用户 （或用户）。 
    
6. 当所选的所有用户想要添加到角色组，请单击**添加-\> ** ，然后**确定**。
    
7. 单击**保存**以保存对角色组的更改。 
    
### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

1. 安全中&amp;合规性中心中，转到**权限**。
    
2. 从列表中，选择要查看的成员的角色组。
    
3. 在右侧，在角色组的详细信息，可以查看的角色组的成员。
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a>使用 PowerShell 让安全的另一个用户访问&amp;合规性中心

1. [连接到 Office 365 安全性&amp;合规性中心使用远程 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
    
2. 使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 **参数**
  
-  _-Identity_ 是要向其中添加成员的角色组。 
    
- - _成员_是要添加到角色组的邮箱、 通用安全组 (USG) 或计算机。可以指定每次只有一个成员。 
    
有关语法和参数的详细信息，请参阅[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。
  
### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证您是否已提供的用户访问到安全&amp;合规性中心使用**Get-rolegroupmember** cmdlet 可以查看组织管理角色组中，成员下面的示例中所示。 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

有关语法和参数的详细信息，请参阅[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。
  

