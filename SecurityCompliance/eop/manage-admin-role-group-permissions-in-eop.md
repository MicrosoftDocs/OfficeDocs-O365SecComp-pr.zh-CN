---
title: 管理 EOP 中的管理员角色组权限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。
ms.openlocfilehash: 35f248bce26d28c8ab7465ff983629eb01db407b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150154"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="ad0a7-104">在 EOP 中管理管理员角色组权限</span><span class="sxs-lookup"><span data-stu-id="ad0a7-104">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="ad0a7-p102">在 Microsoft Exchange Online Protection (EOP) 中，您可以使用 Exchange 管理中心 (EAC) 让用户成为一个或多个角色组的成员，以便为他们分配执行特定管理任务所需的权限。您还可以使用 EAC 将用户从一个或多个角色组中删除。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p102">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad0a7-107">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="ad0a7-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad0a7-108">估计完成时间：5-10 分钟</span><span class="sxs-lookup"><span data-stu-id="ad0a7-108">Estimated time to complete: 5-10 minutes</span></span>
    
- <span data-ttu-id="ad0a7-p103">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"用户、联系人和角色组"条目。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="ad0a7-p104">Office 365 中的特定权限映射到 EOP 管理员角色组权限。有关详细信息，请参阅[分配管理员角色](https://go.microsoft.com/fwlink/p/?LinkId=286708)中"我的 Office 365 权限扩展到了哪些服务？"部分中的"Exchange Online 中的角色"列。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p104">Certain permissions in Office 365 map to EOP admin role group permissions. For more information, see the "Role in Exchange Online" column in the "Which services do my Office 365 permissions extend to?" section in [Assigning Admin Roles](https://go.microsoft.com/fwlink/p/?LinkId=286708).</span></span>
    
- <span data-ttu-id="ad0a7-114">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="ad0a7-p105">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="ad0a7-118">您想执行什么操作？</span><span class="sxs-lookup"><span data-stu-id="ad0a7-118">What do you want to do?</span></span>

### <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="ad0a7-119">使用 EAC 向管理员角色组分配成员</span><span class="sxs-lookup"><span data-stu-id="ad0a7-119">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="ad0a7-120">在 EAC 中, 导航到 "**权限** \> " "**管理员角色**", 单击要向其添加用户的角色组, 然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-120">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="ad0a7-121">在 "成员" \*\*\*\*![下, 单击](../media/ITPro-EAC-AddIcon.gif)"添加" "添加" 图标。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-121">Under Members, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="ad0a7-122">将显示"选择成员"窗口。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-122">The Select Members window will appear.</span></span>
    
3. <span data-ttu-id="ad0a7-123">搜索您要添加的一个或多个用户，或从列表中选择。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-123">Search for the user or users that you wish to add, or select them from the list.</span></span>
    
4. <span data-ttu-id="ad0a7-p107">选择您要添加的一个或多个用户后，单击“添加”\*\*\*\*，然后单击“确定”\*\*\*\*。“选择成员”窗口将会关闭。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p107">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>
    
5. <span data-ttu-id="ad0a7-p108">您会看到用户已经添加到“成员”\*\*\*\* 窗格。单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-p108">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad0a7-128">在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-128">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
### <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="ad0a7-129">使用 EAC 从管理员角色组中删除成员</span><span class="sxs-lookup"><span data-stu-id="ad0a7-129">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="ad0a7-130">在 EAC 中, 导航到 "**权限** \> " "**管理员角色**", 单击要从中删除一个或一组用户的角色组, 然后单击 "**编辑** ![编辑图标](../media/ITPro-EAC-EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-130">In the EAC, navigate to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>
    
2. <span data-ttu-id="ad0a7-131">在 "成员" 下, 选择要删除的一个或一或一些\*\*\*\*![用户, 然后](../media/ITPro-EAC-RemoveIcon.gif)单击 "删除删除图标"。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-131">Under Members, select the user or users that you want to remove and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="ad0a7-132">单击“保存”\*\*\*\* 将更改保存到角色组并返回“管理员角色”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-132">Click **Save** to save the change to the role group and return to the **Admin Roles** page.</span></span> <span data-ttu-id="ad0a7-133">若要验证您已成功从管理员角色组删除用户，确保该用户不会再出现在选定角色组详细信息窗格中的"成员"下。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-133">To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ad0a7-134">在角色组中添加或删除成员后，用户可能必须先注销，然后重新登录才会看到其管理权限的更改。</span><span class="sxs-lookup"><span data-stu-id="ad0a7-134">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="ad0a7-135">详细信息</span><span class="sxs-lookup"><span data-stu-id="ad0a7-135">For more information</span></span>

[<span data-ttu-id="ad0a7-136">EOP 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="ad0a7-136">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
  

