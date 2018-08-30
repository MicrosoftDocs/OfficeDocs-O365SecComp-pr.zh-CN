---
title: 管理 EOP 中的管理员角色组权限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。
ms.openlocfilehash: b773b541b85288b4cb4deaa075cc0346d6bcc646
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002971"
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

1. 在 EAC 中，导航到**权限** \> **管理员角色**中，单击您想要添加的用户或用户到角色组，然后单击**编辑**![编辑图标](../media/ITPro-EAC-EditIcon.gif)。
    
2. 在成员下单击**添加**![添加图标](../media/ITPro-EAC-AddIcon.gif)。将出现选择成员窗口。
    
3. 搜索您要添加的一个或多个用户，或从列表中选择。
    
4. 当您选择了您要添加的用户时，单击**添加**，然后单击**确定**。选择成员窗口将关闭。
    
5. 您将看到用户已添加到**成员**窗格。单击**保存**。
    
    > [!NOTE]
    > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>使用 EAC 从管理员角色组中删除成员

1. 在 EAC 中，导航到**权限** \> **管理员角色**中，单击您想要移除的用户或从用户的角色组，然后单击**编辑**![编辑图标](../media/ITPro-EAC-EditIcon.gif)。
    
2. 在成员下选择用户或用户想要删除并单击**删除**![删除图标](../media/ITPro-EAC-RemoveIcon.gif)。
    
3. 单击**保存**以保存对角色组的更改并返回到**管理员角色**页。若要验证是否已成功删除用户从管理员角色组，请确保成员不再显示在成员下的所选的角色组的详细信息窗格中。 
    
    > [!NOTE]
    > 在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。 
  
## <a name="for-more-information"></a>详细信息

[EOP 中的功能权限](feature-permissions-in-eop.md)
  

