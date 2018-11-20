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
ms.openlocfilehash: 976c4e21351e352672f3075d0f713e63a634ce42
ms.sourcegitcommit: da4aa7335b577148ecd61e09bbb11039b817b287
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26539104"
---
# <a name="give-users-access-to-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="917e2-103">授予用户访问 Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="917e2-103">Give users access to the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="917e2-p101">用户需要为其分配权限 Office 365 安全性&amp;合规性中心之前可以管理其安全性或合规性功能的任何。为 Office 365 全局管理员或安全中 OrganizationManagement 角色组的成员&amp;合规性中心，您可以向用户授予这些权限。用户仅能用于管理您允许他们访问安全性或合规性功能。</span><span class="sxs-lookup"><span data-stu-id="917e2-p101">Users need to be assigned permissions in the Office 365 Security &amp; Compliance Center before they can manage any of its security or compliance features. As an Office 365 global admin or member of the OrganizationManagement role group in the Security &amp; Compliance Center, you can give these permissions to users. Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="917e2-107">有关不同的权限的详细信息可以授予用户安全中&amp;合规性中心，签出[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="917e2-107">For more information about the different permissions you can give to users in the Security &amp; Compliance Center, check out [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="917e2-108">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="917e2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="917e2-109">您必须是 Office 365 全局管理员或安全中 OrganizationManagement 角色组的成员&amp;合规性中心，以完成本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="917e2-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security &amp; Compliance Center, to complete the steps in this article.</span></span>
    
- <span data-ttu-id="917e2-110">安全角色组&amp;合规性中心可能类似的角色组的名称，在 Exchange Online 中，但它们不相同。</span><span class="sxs-lookup"><span data-stu-id="917e2-110">Role groups for the Security &amp; Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span> 
    
- <span data-ttu-id="917e2-111">角色组成员身份不共享之间 Exchange Online 和安全&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="917e2-111">Role group memberships aren't shared between Exchange Online and the Security &amp; Compliance Center.</span></span>
    
## <a name="use-the-office-365-admin-center-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="917e2-112">使用 Office 365 管理中心让安全的另一个用户访问&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="917e2-112">Use the Office 365 admin center to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="917e2-113">[登录到 Office 365 并转到 Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275)。</span><span class="sxs-lookup"><span data-stu-id="917e2-113">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>
    
2. <span data-ttu-id="917e2-114">在 Office 365 管理中心中，打开**管理中心**，然后单击**安全&amp;合规性**。</span><span class="sxs-lookup"><span data-stu-id="917e2-114">In the Office 365 admin center, open **Admin centers** and then click **Security &amp; Compliance**.</span></span> 
    
3. <span data-ttu-id="917e2-115">安全中&amp;合规性中心中，转到**权限**。</span><span class="sxs-lookup"><span data-stu-id="917e2-115">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
4. <span data-ttu-id="917e2-116">从列表中，选择您想要向其中添加用户并单击**编辑**角色组![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="917e2-116">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
5. <span data-ttu-id="917e2-117">在**成员**下的角色组的属性页上，单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)选择的名称您想要添加的用户 （或用户）。</span><span class="sxs-lookup"><span data-stu-id="917e2-117">In the role group's properties page under **Members**, click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span> 
    
6. <span data-ttu-id="917e2-118">当所选的所有用户想要添加到角色组，请单击**添加-\> \*\* ，然后**确定\*\*。</span><span class="sxs-lookup"><span data-stu-id="917e2-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>
    
7. <span data-ttu-id="917e2-119">单击**保存**以保存对角色组的更改。</span><span class="sxs-lookup"><span data-stu-id="917e2-119">Click **Save** to save the changes to the role group.</span></span> 
    
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="917e2-120">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="917e2-120">How do you know this worked?</span></span>

1. <span data-ttu-id="917e2-121">安全中&amp;合规性中心中，转到**权限**。</span><span class="sxs-lookup"><span data-stu-id="917e2-121">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
2. <span data-ttu-id="917e2-122">从列表中，选择要查看的成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="917e2-122">From the list, select the role group to view the members.</span></span>
    
3. <span data-ttu-id="917e2-123">在右侧，在角色组的详细信息，可以查看的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="917e2-123">On the right, in the role group details, you can view the members of the role group.</span></span>
    
## <a name="use-powershell-to-give-another-user-access-to-the-security-amp-compliance-center"></a><span data-ttu-id="917e2-124">使用 PowerShell 让安全的另一个用户访问&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="917e2-124">Use PowerShell to give another user access to the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="917e2-125">[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="917e2-125">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="917e2-126">使用 **Add-rolegroupmember** 命令将用户添加到组织管理角色，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="917e2-126">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span> 
    
  ```
  Add-RoleGroupMember -Identity "OrganizationManagement" -Member MatildaS
  
  ```

 <span data-ttu-id="917e2-127">**参数**</span><span class="sxs-lookup"><span data-stu-id="917e2-127">**Parameters**</span></span>
  
-  <span data-ttu-id="917e2-128">_-Identity_ 是要向其中添加成员的角色组。</span><span class="sxs-lookup"><span data-stu-id="917e2-128">_-Identity_ is the role group to add a member to.</span></span> 
    
- - <span data-ttu-id="917e2-p102">_成员_是要添加到角色组的邮箱、 通用安全组 (USG) 或计算机。可以指定每次只有一个成员。</span><span class="sxs-lookup"><span data-stu-id="917e2-p102">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group. You can specify only one member at a time.</span></span> 
    
<span data-ttu-id="917e2-131">有关语法和参数的详细信息，请参阅[Add-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510859)。</span><span class="sxs-lookup"><span data-stu-id="917e2-131">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="917e2-132">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="917e2-132">How do you know this worked?</span></span>

<span data-ttu-id="917e2-133">若要验证您是否已提供的用户访问到安全&amp;合规性中心使用**Get-rolegroupmember** cmdlet 可以查看组织管理角色组中，成员下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="917e2-133">To verify that you've given users access to the Security &amp; Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span> 
  
```
Get-RoleGroupMember -Identity "OrganizationManagement"

```

<span data-ttu-id="917e2-134">有关语法和参数的详细信息，请参阅[Get-rolegroupmember](https://go.microsoft.com/fwlink/p/?LinkId=510860)。</span><span class="sxs-lookup"><span data-stu-id="917e2-134">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
  

