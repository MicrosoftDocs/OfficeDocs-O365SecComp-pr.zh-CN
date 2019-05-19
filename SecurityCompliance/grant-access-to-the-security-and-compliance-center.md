---
title: 向用户授予对 Office 365 安全&amp;合规中心的访问权限
ms.author: stephow
author: stephow-MSFT
manager: laurawi
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
description: 在管理任何安全或合规性功能之前, 需要&amp;在 Office 365 安全合规中心中为用户分配权限。
ms.openlocfilehash: aa0d1e9af6eb547bbb145d06cabfc431028ec4f0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154294"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="9166d-103">向用户授予对 Office 365 安全&amp;合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="9166d-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="9166d-104">在管理任何安全或合规性功能之前, 需要&amp;在 Office 365 安全合规中心中为用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="9166d-104">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="9166d-105">作为安全&amp;合规中心中的 OrganizationManagement 角色组的 Office 365 全局管理员或成员, 您可以向用户授予这些权限。</span><span class="sxs-lookup"><span data-stu-id="9166d-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="9166d-106">用户将只能管理你授权他们访问的安全或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="9166d-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="9166d-107">若要详细了解可以向安全&amp;合规中心中的用户授予的不同权限, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="9166d-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9166d-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="9166d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9166d-109">您必须是 Office 365 全局管理员或安全&amp;合规中心中的 OrganizationManagement 角色组的成员, 才能完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="9166d-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="9166d-110">安全&amp;符合性中心的角色组可能与 Exchange Online 中的角色组具有相似的名称, 但它们不是相同的。</span><span class="sxs-lookup"><span data-stu-id="9166d-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="9166d-111">角色组成员身份不在 Exchange Online 和安全&amp;合规性中心之间共享。</span><span class="sxs-lookup"><span data-stu-id="9166d-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9166d-112">使用 Office 365 管理中心向另一个用户授予对安全&amp;合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="9166d-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9166d-113">[登录到 Office 365 并转到管理中心](https://go.microsoft.com/fwlink/p/?LinkId=525275)。</span><span class="sxs-lookup"><span data-stu-id="9166d-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="9166d-114">在 "Office 365 管理中心" 中, 打开 "**管理中心**", 然后单击 " \*\* &amp;安全合规性\*\*"。</span><span class="sxs-lookup"><span data-stu-id="9166d-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="9166d-115">在 "安全&amp;合规性中心" 中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="9166d-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="9166d-116">从列表中, 选择要向其添加用户的角色组, 然后单击 "**编辑** ![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="9166d-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="9166d-117">在 "**成员**" 下的角色组的 "属性" 页中](media/ITPro-EAC-AddIcon.gif) , 单击 "**添加**![" "添加" 图标, 然后选择要添加的一个或一组用户的名称。</span><span class="sxs-lookup"><span data-stu-id="9166d-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="9166d-118">在选择了要添加到角色组的所有用户后, 单击 "\*\*添加\> \*\* ", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9166d-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="9166d-119">单击“保存”\*\*\*\* 以保存对角色组的更改。</span><span class="sxs-lookup"><span data-stu-id="9166d-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9166d-120">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="9166d-120">How do you know this worked?</span></span>

1. <span data-ttu-id="9166d-121">在 "安全&amp;合规性中心" 中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="9166d-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="9166d-122">从列表中选择要查看成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="9166d-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="9166d-123">在右侧的 "角色组详细信息" 中, 您可以查看角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="9166d-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="9166d-124">使用 PowerShell 向另一个用户授予对安全&amp;合规中心的访问权限</span><span class="sxs-lookup"><span data-stu-id="9166d-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="9166d-125">[连接到 Office 365 Security _AMP_ 合规中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="9166d-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="9166d-126">使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="9166d-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="9166d-127">**参数**</span><span class="sxs-lookup"><span data-stu-id="9166d-127">**Parameters**</span></span>
  
- <span data-ttu-id="9166d-128">_-Identity_ 是要向其中添加成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="9166d-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- <span data-ttu-id="9166d-129">_Member_是要添加到角色组的邮箱、通用安全组 (USG) 或计算机。</span><span class="sxs-lookup"><span data-stu-id="9166d-129">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="9166d-130">每次只能指定一个成员。</span><span class="sxs-lookup"><span data-stu-id="9166d-130">You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="9166d-131">有关语法和参数的详细信息, 请参阅[外接程序 add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。</span><span class="sxs-lookup"><span data-stu-id="9166d-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="9166d-132">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="9166d-132">How do you know this worked?</span></span>

<span data-ttu-id="9166d-133">若要验证您是否已授予用户对安全&amp;合规中心的访问权限, 请使用**Add-rolegroupmember** cmdlet 查看组织管理角色组中的成员, 如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9166d-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="9166d-134">有关语法和参数的详细信息, 请参阅[add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。</span><span class="sxs-lookup"><span data-stu-id="9166d-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

