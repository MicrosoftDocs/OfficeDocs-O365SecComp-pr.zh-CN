---
title: 管理 EOP 中的管理员角色组权限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。
ms.openlocfilehash: aed32c8a9224bc60ef3e4a1ac9be9d797e61bda8
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693421"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>管理 EOP 中的管理员角色组权限
  
在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成时间：5-10 分钟
    
- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。 
    
- Office 365 中的特定权限映射到 EOP 管理员角色组权限。有关详细信息，请参阅[分配管理员角色](https://go.microsoft.com/fwlink/p/?LinkId=286708)中"我的 Office 365 权限扩展到了哪些服务？"部分中的"Exchange Online 中的角色"列。
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="what-do-you-want-to-do"></a>您想执行什么操作？

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>使用 EAC 向管理员角色组分配成员

1. 在 EAC 中, 导航到 "**权限** \> " "**管理员角色**", 单击要向其添加用户的角色组, 然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。
    
2. 在 "成员" ****![下, 单击](../media/ITPro-EAC-AddIcon.gif)"添加" "添加" 图标。 将显示"选择成员"窗口。
    
3. 搜索您要添加的一个或多个用户，或从列表中选择。
    
4. 选择您要添加的一个或多个用户后，单击“添加”****，然后单击“确定”****。“选择成员”窗口将会关闭。
    
5. 您会看到用户已经添加到“成员”**** 窗格。单击“保存”****。
    
    > [!NOTE]
    > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>使用 EAC 从管理员角色组中删除成员

1. 在 EAC 中, 导航到 "**权限** \> " "**管理员角色**", 单击要从中删除一个或一组用户的角色组, 然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。
    
2. 在 "成员" 下, 选择要删除的一个或一或一些****![用户, 然后](../media/ITPro-EAC-RemoveIcon.gif)单击 "删除删除图标"。
    
3. 单击“保存”**** 将更改保存到角色组并返回“管理员角色”**** 页。 若要验证您已成功从管理员角色组删除用户，确保该用户不会再出现在选定角色组详细信息窗格中的"成员"下。 
    
    > [!NOTE]
    > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。 
  
## <a name="for-more-information"></a>详细信息

[EOP 中的功能权限](feature-permissions-in-eop.md)
  

