---
title: 向用户授予对 Office 365 安全与合规中心的访问权限
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: 用户需要在 Office 365 安全 & 合规性中心中分配权限, 然后才能管理其任何安全或合规性功能。
ms.openlocfilehash: 7963a8c3db64e83566960abe9298b9a2d636ae53
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2019
ms.locfileid: "35645117"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a>向用户授予对 Office 365 安全与合规中心的访问权限

用户需要在 Office 365 安全 & 合规性中心中分配权限, 然后才能管理其任何安全或合规性功能。 作为 Security & 合规中心中的 OrganizationManagement 角色组的 Office 365 全局管理员或成员, 您可以向用户授予这些权限。 用户将只能管理你授权他们访问的安全或合规性功能。 
  
有关您可以向安全 & 合规中心中的用户授予的不同权限的详细信息, 请查看[Office 365 安全 & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 您必须是 Office 365 全局管理员, 或者是 Security & 合规性中心中的 OrganizationManagement 角色组的成员, 才能完成本文中的步骤。

- Security & 合规中心的角色组可能与 Exchange Online 中的角色组具有相似的名称, 但它们不是相同的。

- 角色组成员身份不在 Exchange Online 与 Security & 合规性中心之间共享。

- 委派访问权限 (分配) 具有代表 (AOBO) 权限的管理的合作伙伴无法访问安全 & 合规中心。

## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>使用 Office 365 管理中心向另一个用户授予对安全 & 合规中心的访问权限

1. [登录到 Office 365 并转到管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。

2. 在 "Office 365 管理中心" 中, 打开 "**管理中心**", 然后单击 "**安全 & 合规性**"。

3. 在安全 & 合规性中心中, 转到 "**权限**"。

4. 从列表中, 选择要向其添加用户的角色组, 然后单击 "**编辑** ![编辑图标](media/O365-MDM-CreatePolicy-EditIcon.gif)"。

5. 在 "**成员**" 下的角色组的 "属性" 页中](media/ITPro-EAC-AddIcon.gif) , 单击 "**添加**![" "添加" 图标, 然后选择要添加的一个或一组用户的名称。

6. 在选择了要添加到角色组的所有用户后, 单击 "**添加\> ** ", 然后单击 **"确定"**。

7. 单击“保存”**** 以保存对角色组的更改。

### <a name="how-do-you-know-this-worked"></a>您如何知道操作成功？

1. 在安全 & 合规性中心中, 转到 "**权限**"。

2. 从列表中选择要查看成员的角色组。

3. 在右侧的 "角色组详细信息" 中, 您可以查看角色组的成员。

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>使用 PowerShell 授予另一个用户对安全 & 合规中心的访问权限

1. [连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

2. 使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **参数**:
  
   - _Identity_是要向其添加成员的角色组。

   - _Member_是要添加到角色组的邮箱、通用安全组 (USG) 或计算机。 每次只能指定一个成员。

有关语法和参数的详细信息, 请参阅[外接程序 add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。
  
### <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证您是否已授予用户对安全 & 合规中心的访问权限, 请使用**add-rolegroupmember** Cmdlet 查看组织管理角色组中的成员, 如以下示例所示。
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

有关语法和参数的详细信息, 请参阅[add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。
