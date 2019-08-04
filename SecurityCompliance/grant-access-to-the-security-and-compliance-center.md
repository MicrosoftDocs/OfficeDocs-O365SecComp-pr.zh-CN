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
ms.openlocfilehash: ea774648efcfe80461eae937f80856acaf1db224
ms.sourcegitcommit: 7c1cb9e8adb1c3e9c667f4cf02ca3cec3ec1e171
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792008"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="2ffd6-103">向用户授予对 Office 365 安全与合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="2ffd6-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="2ffd6-104">用户需要在 Office 365 安全 & 合规性中心中分配权限, 然后才能管理其任何安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="2ffd6-105">作为 Security & 合规中心中的 OrganizationManagement 角色组的 Office 365 全局管理员或成员, 您可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="2ffd6-106">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="2ffd6-107">有关您可以向安全 & 合规中心中的用户授予的不同权限的详细信息, 请查看[Office 365 安全 & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2ffd6-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="2ffd6-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2ffd6-109">您必须是 Office 365 全局管理员, 或者是 Security & 合规性中心中的 OrganizationManagement 角色组的成员, 才能完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="2ffd6-110">Security & 合规中心的角色组可能与 Exchange Online 中的角色组具有相似的名称, 但它们不是相同的。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="2ffd6-111">角色组成员身份不在 Exchange Online 与 Security & 合规性中心之间共享。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="2ffd6-112">委派访问权限 (分配) 具有代表 (AOBO) 权限的管理的合作伙伴无法访问安全 & 合规中心。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="2ffd6-113">使用管理中心向另一个用户授予对安全 & 合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="2ffd6-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="2ffd6-114">[登录到 Office 365 并转到管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-114">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>

2. <span data-ttu-id="2ffd6-115">在 Microsoft 365 管理中心, 打开 "**管理中心**", 然后单击 "**安全 & 合规性**"。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="2ffd6-116">在安全 & 合规性中心中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="2ffd6-117">从列表中, 选择要向其添加用户的角色组, 然后单击 "**编辑** ![编辑图标](media/O365-MDM-CreatePolicy-EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="2ffd6-118">在 "**成员**" 下的角色组的 "属性" 页中](media/ITPro-EAC-AddIcon.gif) , 单击 "**添加**![" "添加" 图标, 然后选择要添加的一个或一组用户的名称。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-118">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="2ffd6-119">在选择了要添加到角色组的所有用户后, 单击 "\*\*添加\> \*\* ", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="2ffd6-120">单击“保存”\*\*\*\* 以保存对角色组的更改。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2ffd6-121">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="2ffd6-121">How do you know this worked?</span></span>

1. <span data-ttu-id="2ffd6-122">在安全 & 合规性中心中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="2ffd6-123">从列表中选择要查看成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="2ffd6-124">在右侧的 "角色组详细信息" 中, 您可以查看角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="2ffd6-125">使用 PowerShell 授予另一个用户对安全 & 合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="2ffd6-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="2ffd6-126">[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="2ffd6-127">使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="2ffd6-128">**参数**:</span><span class="sxs-lookup"><span data-stu-id="2ffd6-128">**Parameters**:</span></span>
  
   - <span data-ttu-id="2ffd6-129">_Identity_是要向其添加成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="2ffd6-130">_Member_是要添加到角色组的邮箱、通用安全组 (USG) 或计算机。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="2ffd6-131">每次只能指定一个成员。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="2ffd6-132">有关语法和参数的详细信息, 请参阅[外接程序 add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2ffd6-133">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="2ffd6-133">How do you know this worked?</span></span>

<span data-ttu-id="2ffd6-134">若要验证您是否已授予用户对安全 & 合规中心的访问权限, 请使用**add-rolegroupmember** Cmdlet 查看组织管理角色组中的成员, 如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="2ffd6-135">有关语法和参数的详细信息, 请参阅[add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。</span><span class="sxs-lookup"><span data-stu-id="2ffd6-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
