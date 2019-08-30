---
title: 在 EOP 中管理组
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
description: 您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。 您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。
ms.openlocfilehash: 9ce501c5d51561a7be86963ae98b62046995e46f
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676732"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="55bcc-104">在 EOP 中管理组</span><span class="sxs-lookup"><span data-stu-id="55bcc-104">Manage groups in EOP</span></span>

 <span data-ttu-id="55bcc-p102">您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。您可以根据需要创建通讯组和安全组。可以使用 Exchange 管理中心 (EAC) 或通过远程 Windows PowerShell 创建这些组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="55bcc-109">启用邮件的组的类型</span><span class="sxs-lookup"><span data-stu-id="55bcc-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="55bcc-110">您可以为 Exchange 组织创建两种类型的组：</span><span class="sxs-lookup"><span data-stu-id="55bcc-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="55bcc-111">通讯组是电子邮件用户 (如团队或其他临时组) 的集合, 这些用户需要接收或发送有关感兴趣的常见领域的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="55bcc-111">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="55bcc-112">通讯组专用于分发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="55bcc-112">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="55bcc-113">在 EOP 中，通讯组是指任何启用邮件的组，无论其是否有安全性上下文。</span><span class="sxs-lookup"><span data-stu-id="55bcc-113">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="55bcc-114">安全组是需要管理员角色访问权限的电子邮件用户的集合。</span><span class="sxs-lookup"><span data-stu-id="55bcc-114">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="55bcc-115">例如，您可能想向特定组的用户授予管理员角色权限，使他们能够配置反垃圾邮件和反恶意邮件设置。</span><span class="sxs-lookup"><span data-stu-id="55bcc-115">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55bcc-p105">默认情况下，所有启用邮件的新安全组都要求对所有发件人进行身份验证。这样可防止外部发件人将邮件发送到启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="55bcc-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="55bcc-118">Before you begin</span></span>

- <span data-ttu-id="55bcc-p106">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"通讯组和安全组"条目。</span><span class="sxs-lookup"><span data-stu-id="55bcc-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="55bcc-121">若要打开 Exchange 管理中心, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-121">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](../exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="55bcc-122">请注意, 在使用 Exchange Online Protection PowerShell cmdlet 创建和管理组时, 可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="55bcc-122">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="55bcc-123">本主题中的 PowerShell 过程使用一种批处理方法, 该方法会导致在几分钟内发生传播延迟, 然后才能看到命令的结果。</span><span class="sxs-lookup"><span data-stu-id="55bcc-123">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="55bcc-124">若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection, 请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-124">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="55bcc-125">有关可能适用于本主题中的过程的键盘快捷方式的信息, 请参阅 exchange [Online 中 exchange 管理中心的键盘快捷方式](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-125">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="55bcc-126">是否有任何疑问？</span><span class="sxs-lookup"><span data-stu-id="55bcc-126">Having problems?</span></span> <span data-ttu-id="55bcc-127">在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)论坛中寻求帮助。</span><span class="sxs-lookup"><span data-stu-id="55bcc-127">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="55bcc-128">在 EAC 中创建组</span><span class="sxs-lookup"><span data-stu-id="55bcc-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="55bcc-129">在 EAC 中, 转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-129">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="55bcc-130">单击 "**新建** ![添加](../media/ITPro-EAC-AddIcon.gif)图标", 然后单击 "**通讯组**" 或 "**安全组**", 具体取决于您的需要。</span><span class="sxs-lookup"><span data-stu-id="55bcc-130">Click **New** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="55bcc-131">在 "**新建通讯组**" 或 "**新建安全组**" 页上, 配置以下设置:</span><span class="sxs-lookup"><span data-stu-id="55bcc-131">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="55bcc-132">**显示名称**: 键入您的组织独有的显示名称, 并对 EOP 用户有意义。</span><span class="sxs-lookup"><span data-stu-id="55bcc-132">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="55bcc-133">显示名称是必填项。</span><span class="sxs-lookup"><span data-stu-id="55bcc-133">The display name is required.</span></span>

   - <span data-ttu-id="55bcc-134">**别名**: 键入一个最高为64个字符的组别名, 这些字符对您的组织是唯一的。</span><span class="sxs-lookup"><span data-stu-id="55bcc-134">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="55bcc-135">EOP 用户在"收件人"电子邮件行中键入别名，别名会解析成组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="55bcc-135">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="55bcc-136">如果您更改别名，组的主 SMTP 地址也会更改，并会包含新别名。</span><span class="sxs-lookup"><span data-stu-id="55bcc-136">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="55bcc-137">别名为必填项。</span><span class="sxs-lookup"><span data-stu-id="55bcc-137">The alias is required.</span></span> 

   - <span data-ttu-id="55bcc-138">**说明**: 键入组的说明, 以便用户了解组的用途。</span><span class="sxs-lookup"><span data-stu-id="55bcc-138">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span> 

   - <span data-ttu-id="55bcc-139">**所有者**: 默认情况下, 创建组的人员是所有者。</span><span class="sxs-lookup"><span data-stu-id="55bcc-139">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="55bcc-140">您可以通过选择 "**添加** ![添加" 图标](../media/ITPro-EAC-AddIcon.gif)来添加所有者。</span><span class="sxs-lookup"><span data-stu-id="55bcc-140">You can add an owner by choosing **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="55bcc-141">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="55bcc-141">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="55bcc-142">所有者不必是组的成员。</span><span class="sxs-lookup"><span data-stu-id="55bcc-142">Owners don't have to be members of the group.</span></span>
  
   - <span data-ttu-id="55bcc-143">**Members**: 使用此部分可添加组成员并指定是否需要审批人员加入或离开组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-143">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="55bcc-144">若要向组中添加成员, \*\*\*\* ![请单击 "](../media/ITPro-EAC-AddIcon.gif)添加添加图标"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-144">To add members to the group, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="55bcc-145">单击“确定”\*\*\*\* 返回原始页面。</span><span class="sxs-lookup"><span data-stu-id="55bcc-145">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="55bcc-146">完成后, 请单击 "**保存**" 以创建组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-146">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="55bcc-147">此时，新组应该会出现在组列表中。</span><span class="sxs-lookup"><span data-stu-id="55bcc-147">The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="55bcc-148">在 EAC 中编辑或删除组</span><span class="sxs-lookup"><span data-stu-id="55bcc-148">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="55bcc-149">In the EAC, navigate to **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="55bcc-149">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="55bcc-150">采取以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="55bcc-150">Do one of the following steps:</span></span>

   - <span data-ttu-id="55bcc-151">若要编辑组, 请执行以下操作: 在组列表中, 单击要查看或更改的组, 然后单击 "**编辑** ![编辑](../media/ITPro-EAC-EditIcon.gif)图标"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-151">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="55bcc-152">您可以根据需要更新常规设置、添加或删除组所有者, 以及添加或删除组成员。</span><span class="sxs-lookup"><span data-stu-id="55bcc-152">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="55bcc-153">若要删除组, 请选择组, 然后\*\*\*\* ![单击 "删除](../media/ITPro-EAC-RemoveIcon.gif)删除图标"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-153">To remove a group: Select the group and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="55bcc-154">完成更改后, 请单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-154">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="55bcc-155">使用远程 Windows PowerShell 创建、编辑或删除组</span><span class="sxs-lookup"><span data-stu-id="55bcc-155">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="55bcc-156">本节提供有关在 Exchange Online Protection PowerShell 中创建组和更改其属性的信息。</span><span class="sxs-lookup"><span data-stu-id="55bcc-156">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="55bcc-157">它还演示了如何删除现有的组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-157">It also shows how to remove an existing group.</span></span>
  
### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="55bcc-158">使用远程 Windows PowerShell 创建组</span><span class="sxs-lookup"><span data-stu-id="55bcc-158">Create a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="55bcc-p115">该示例使用 [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet 创建别名为"itadmin"且名称为"IT 管理员"的通信组。还会将用户添加为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="55bcc-p115">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>
  
```Powershell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="55bcc-161">**注意**: 若要创建安全组, 而不是通讯组, 请使用`Security` *Type*参数的值。</span><span class="sxs-lookup"><span data-stu-id="55bcc-161">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>
  
<span data-ttu-id="55bcc-162">若要验证是否成功创建了 IT 管理员组, 请运行以下命令以显示有关新组的信息:</span><span class="sxs-lookup"><span data-stu-id="55bcc-162">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>
  
```Powershell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="55bcc-163">有关语法和参数的详细信息, 请参阅 "[获取-收件人](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient)"。</span><span class="sxs-lookup"><span data-stu-id="55bcc-163">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="55bcc-164">若要获取组中成员的列表, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="55bcc-164">To get a list of members in the group, run the following command:</span></span>
  
```Powershell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="55bcc-165">有关语法和参数的详细信息, 请参阅[get-distributiongroupmember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-165">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="55bcc-166">若要获取所有组的完整列表, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="55bcc-166">To get a full list of all your groups, run the following command:</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="55bcc-167">使用远程 Windows PowerShell 更改组的属性</span><span class="sxs-lookup"><span data-stu-id="55bcc-167">Change the properties of a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="55bcc-168">使用 PowerShell (而不是 EAC) 的优势在于能够更改多个组的属性。</span><span class="sxs-lookup"><span data-stu-id="55bcc-168">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>
  
<span data-ttu-id="55bcc-169">下面是使用 Exchange Online Protection PowerShell 更改组属性的一些示例。</span><span class="sxs-lookup"><span data-stu-id="55bcc-169">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>
  
<span data-ttu-id="55bcc-170">本示例使用将 "西雅图员工" 组的主 SMTP 地址 (也称为 "回复地址") 更改为 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="55bcc-170">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="55bcc-171">有关语法和参数的详细信息, 请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-171">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="55bcc-172">若要验证是否已成功更改了组的属性, 请运行以下命令来验证新值:</span><span class="sxs-lookup"><span data-stu-id="55bcc-172">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>
  
```Powershell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="55bcc-173">本示例更新 "西雅图员工" 组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="55bcc-173">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="55bcc-174">使用逗号分隔所有成员。</span><span class="sxs-lookup"><span data-stu-id="55bcc-174">Use a comma to separate all members.</span></span>
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="55bcc-175">有关语法和参数的详细信息, 请参阅[EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-175">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="55bcc-176">若要获取组 "西雅图员工" 中所有成员的列表, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="55bcc-176">To get the list of all the members in the group Seattle Employees, run the following command:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="55bcc-177">使用远程 Windows PowerShell 删除组</span><span class="sxs-lookup"><span data-stu-id="55bcc-177">Remove a group using remote Windows PowerShell</span></span>
  
<span data-ttu-id="55bcc-178">本示例使用删除名为 "IT 管理员" 的通讯组。</span><span class="sxs-lookup"><span data-stu-id="55bcc-178">This example uses removes the distribution group named IT Administrators.</span></span>
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="55bcc-179">有关语法和参数的详细信息, 请参阅[set-eopdistributiongroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup)。</span><span class="sxs-lookup"><span data-stu-id="55bcc-179">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="55bcc-180">若要验证是否已删除该组, 请运行以下命令, 并确认该组 (在此示例中为 "It 管理员") 已删除。</span><span class="sxs-lookup"><span data-stu-id="55bcc-180">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
