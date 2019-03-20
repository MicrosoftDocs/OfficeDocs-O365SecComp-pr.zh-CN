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
# <a name="manage-groups-in-eop"></a><span data-ttu-id="754e2-104">在 EOP 中管理组</span><span class="sxs-lookup"><span data-stu-id="754e2-104">Manage groups in EOP</span></span>

 <span data-ttu-id="754e2-p102">您可以使用 Exchange Online Protection (EOP) 为 Exchange 组织创建启用邮件的组。您还可以使用 EOP 定义或更新可指定成员资格、电子邮件地址和组其他方面的组属性。您可以根据需要创建通讯组和安全组。可以使用 Exchange 管理中心 (EAC) 或通过远程 Windows PowerShell 创建这些组。</span><span class="sxs-lookup"><span data-stu-id="754e2-p102">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span> 
  
## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="754e2-109">启用邮件的组的类型</span><span class="sxs-lookup"><span data-stu-id="754e2-109">Types of mail-enabled groups</span></span>

<span data-ttu-id="754e2-110">您可以为 Exchange 组织创建两种类型的组：</span><span class="sxs-lookup"><span data-stu-id="754e2-110">You can create two types of groups for your Exchange organization:</span></span>
  
- <span data-ttu-id="754e2-p103">[在 EAC 中创建组](manage-groups-in-eop.md)（也称为"通讯组"）是需要接收或发送与共同关心领域相关的电子邮件的电子邮件用户的集合，例如小组或其他临时组。通讯组专用于分发电子邮件。在 EOP 中，通讯组是指任何启用邮件的组，无论其是否有安全性上下文。</span><span class="sxs-lookup"><span data-stu-id="754e2-p103">[Create a group in the EAC](manage-groups-in-eop.md) (also known as distribution groups) are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest. Distribution groups are exclusively for distributing email messages. In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>
    
- <span data-ttu-id="754e2-p104">[在 EAC 中编辑或删除组](manage-groups-in-eop.md)（也称为"安全组"）是需要获得管理员角色的访问权限的电子邮件用户的集合。例如，您可能想向特定组的用户授予管理员角色权限，使他们能够配置反垃圾邮件和反恶意邮件设置。</span><span class="sxs-lookup"><span data-stu-id="754e2-p104">[Edit or remove a group in the EAC](manage-groups-in-eop.md) (also known as security groups) are collections of email users who need access permissions for Admin roles. For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="754e2-p105">默认情况下，所有启用邮件的新安全组都要求对所有发件人进行身份验证。这样可防止外部发件人将邮件发送到启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="754e2-p105">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="754e2-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="754e2-118">Before you begin</span></span>

- <span data-ttu-id="754e2-p106">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [EOP 中的功能权限](feature-permissions-in-eop.md)主题中的"通讯组和安全组"条目。</span><span class="sxs-lookup"><span data-stu-id="754e2-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
    
- <span data-ttu-id="754e2-121">请注意，在使用远程 PowerShell cmdlet 创建和管理组时，您可能会遇到限制。</span><span class="sxs-lookup"><span data-stu-id="754e2-121">Be aware that when creating and managing groups by using remote PowerShell cmdlets, you may encounter throttling.</span></span>
    
- <span data-ttu-id="754e2-122">此 cmdlet 使用批处理方法，在显示 cmdlet 结果之前，有几分钟的传播延迟。</span><span class="sxs-lookup"><span data-stu-id="754e2-122">This cmdlet uses a batch processing method that results in a propagation delay of a few minutes before the results of the cmdlet are visible.</span></span>
    
- <span data-ttu-id="754e2-123">要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[使用远程 PowerShell 连接到 Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="754e2-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell?view=exchange-ps).</span></span>
    
- <span data-ttu-id="754e2-124">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="754e2-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="754e2-p107">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="754e2-p107">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="754e2-128">在 EAC 中创建组</span><span class="sxs-lookup"><span data-stu-id="754e2-128">Create a group in the EAC</span></span>

1. <span data-ttu-id="754e2-129">在 Exchange 管理中心 (EAC) 中, 转到 "**收件人** \> **组**"。</span><span class="sxs-lookup"><span data-stu-id="754e2-129">In the Exchange admin center (EAC), go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="754e2-130">单击 "**新建**![添加](../media/ITPro-EAC-AddIcon.gif)图标", 然后单击 "**通讯组**" 或 "**安全组**", 具体取决于您的需要。</span><span class="sxs-lookup"><span data-stu-id="754e2-130">Click **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span> <span data-ttu-id="754e2-131">请参阅[Types of mail-enabled groups](manage-groups-in-eop.md)了解区别。</span><span class="sxs-lookup"><span data-stu-id="754e2-131">See [Types of mail-enabled groups](manage-groups-in-eop.md) for the distinction.</span></span> 
    
3. <span data-ttu-id="754e2-132">在“新建通讯组”\*\*\*\* 或“新建安全组”\*\*\*\* 页面上，填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="754e2-132">On the **New distribution group** or **New security group** page, complete the following fields:</span></span> 
    
  - <span data-ttu-id="754e2-133">**显示名称**键入您的组织独有的显示名称, 并对 EOP 用户有意义。</span><span class="sxs-lookup"><span data-stu-id="754e2-133">**Display name** Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="754e2-134">显示名称是必填项。</span><span class="sxs-lookup"><span data-stu-id="754e2-134">The display name is required.</span></span> 
    
  - <span data-ttu-id="754e2-135">**别名**键入一个最高为64个字符的组别名, 这些字符对您的组织是唯一的。</span><span class="sxs-lookup"><span data-stu-id="754e2-135">**Alias** Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="754e2-136">EOP 用户在"收件人"电子邮件行中键入别名，别名会解析成组的显示名称。</span><span class="sxs-lookup"><span data-stu-id="754e2-136">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="754e2-137">如果您更改别名，组的主 SMTP 地址也会更改，并会包含新别名。</span><span class="sxs-lookup"><span data-stu-id="754e2-137">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="754e2-138">别名为必填项。</span><span class="sxs-lookup"><span data-stu-id="754e2-138">The alias is required.</span></span> 
    
  - <span data-ttu-id="754e2-139">**说明**键入组的说明, 以便用户了解组的用途。</span><span class="sxs-lookup"><span data-stu-id="754e2-139">**Description** Type a description of the group so that people will know the purpose of the group.</span></span> 
    
  - <span data-ttu-id="754e2-140">**所有者**默认情况下, 创建组的人员是所有者。</span><span class="sxs-lookup"><span data-stu-id="754e2-140">**Owners** By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="754e2-141">您可以通过选择 "**添加**![添加" 图标](../media/ITPro-EAC-AddIcon.gif)来添加所有者。</span><span class="sxs-lookup"><span data-stu-id="754e2-141">You can add an owner by choosing **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="754e2-142">所有组都必须至少有一个所有者。</span><span class="sxs-lookup"><span data-stu-id="754e2-142">All groups must have at least one owner.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="754e2-143">所有者不必是组的成员。</span><span class="sxs-lookup"><span data-stu-id="754e2-143">Owners don't have to be members of the group.</span></span> 
  
  - <span data-ttu-id="754e2-144">**成员**使用此部分可以添加组成员, 并指定是否需要审批人员加入或离开组。</span><span class="sxs-lookup"><span data-stu-id="754e2-144">**Members** Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="754e2-145">若要向组中添加成员, \*\*\*\*![请单击 "](../media/ITPro-EAC-AddIcon.gif)添加添加图标"。</span><span class="sxs-lookup"><span data-stu-id="754e2-145">To add members to the group, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="754e2-146">单击“确定”\*\*\*\* 返回原始页面。</span><span class="sxs-lookup"><span data-stu-id="754e2-146">Click **OK** to return to the original page.</span></span> 
    
5. <span data-ttu-id="754e2-147">完成后, 请单击 "**保存**" 以创建组。</span><span class="sxs-lookup"><span data-stu-id="754e2-147">When you've finished, click **Save** to create the group.</span></span> <span data-ttu-id="754e2-148">此时，新组应该会出现在组列表中。</span><span class="sxs-lookup"><span data-stu-id="754e2-148">The new group should appear in the list of groups.</span></span> 
    
## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="754e2-149">在 EAC 中编辑或删除组</span><span class="sxs-lookup"><span data-stu-id="754e2-149">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="754e2-150">In the EAC, navigate to **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="754e2-150">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="754e2-151">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="754e2-151">Do one of the following:</span></span>
    
  - <span data-ttu-id="754e2-152">若要编辑组, 请执行以下操作: 在组列表中, 单击要查看或更改的分发或安全组, 然后单击 "**编辑** ![编辑](../media/ITPro-EAC-EditIcon.gif)图标"。</span><span class="sxs-lookup"><span data-stu-id="754e2-152">To edit a group: In the list of groups, click the distribution or security group that you want to view or change, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="754e2-153">您可以根据需要更新常规设置、添加或删除组所有者，以及添加或删除组成员。</span><span class="sxs-lookup"><span data-stu-id="754e2-153">You can update general settings, add or remove group owners, and add or remove group members, as needed.</span></span>
    
  - <span data-ttu-id="754e2-154">若要删除组, 请选择组, 然后\*\*\*\*![单击 "删除](../media/ITPro-EAC-RemoveIcon.gif)删除图标"。</span><span class="sxs-lookup"><span data-stu-id="754e2-154">To remove a group: Select the group and click **Remove**![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>
    
3. <span data-ttu-id="754e2-155">完成更改后, 请单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="754e2-155">When you're finished making your changes, click **Save**.</span></span>
    
## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="754e2-156">使用远程 Windows PowerShell 创建、编辑或删除组</span><span class="sxs-lookup"><span data-stu-id="754e2-156">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="754e2-p115">本部分提供了有关使用远程 Windows PowerShell 创建组和更改其属性的信息。它还演示了如何删除现有的组。</span><span class="sxs-lookup"><span data-stu-id="754e2-p115">This section provides information about creating groups and changing their properties by using remote Windows PowerShell. It also shows how to remove an existing group.</span></span> 
  
 <span data-ttu-id="754e2-159">**使用远程 Windows PowerShell 创建组**</span><span class="sxs-lookup"><span data-stu-id="754e2-159">**To create a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="754e2-p116">该示例使用 [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet 创建别名为"itadmin"且名称为"IT 管理员"的通信组。还会将用户添加为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="754e2-p116">This example uses the [New-EOPDistributionGroup](http://technet.microsoft.com/library/4610dfe5-fca8-4ba8-be3c-535d1753e0f4.aspx) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span> 
  
```Powershell
New-EOPDistributionGroup -Type "Distribution" -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy "Member1"

```

<span data-ttu-id="754e2-162">若要创建安全组，而不是通讯组，请改为指定  `-Type "Security"`。</span><span class="sxs-lookup"><span data-stu-id="754e2-162">To create a security group instead of a distribution group, specify  `-Type "Security"` instead.</span></span> 
  
<span data-ttu-id="754e2-163">若要验证已成功创建"IT 管理员"组，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 显示有关新组的信息：</span><span class="sxs-lookup"><span data-stu-id="754e2-163">To verify that you've successfully created the IT Administrators group, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to display information about the new group:</span></span> 
  
```Powershell
Get-Recipient "IT Administrators" | Format-List

```

<span data-ttu-id="754e2-164">若要获取组中成员的列表，请运行 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="754e2-164">To get a list of members in the group, run the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "IT Administrators"

```

<span data-ttu-id="754e2-165">若要获取所有组的完整列表，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="754e2-165">To get a full list of all your groups, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | FT | more

```

 <span data-ttu-id="754e2-166">**使用远程 Windows PowerShell 更改组的属性**</span><span class="sxs-lookup"><span data-stu-id="754e2-166">**To change the properties of a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="754e2-p117">使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) 和 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 查看或更改组的属性。使用远程 PowerShell 代替 EAC 的一个优势是可以更改多个组的属性。</span><span class="sxs-lookup"><span data-stu-id="754e2-p117">Use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) and [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlets to view and change properties for groups. An advantage of using remote PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span> 
  
<span data-ttu-id="754e2-169">下面是使用远程 Windows PowerShell 更改组属性的一些示例。</span><span class="sxs-lookup"><span data-stu-id="754e2-169">Here are some examples of using remote Windows PowerShell to change group properties.</span></span>
  
<span data-ttu-id="754e2-170">此示例使用 [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet 将"西雅图员工"组的主 SMTP 地址（也称为答复地址）更改为 sea.employees@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="754e2-170">This example uses the [Set-EOPDistributionGroup](http://technet.microsoft.com/library/689a66c5-a524-4870-88f3-091fd6eae3b7.aspx) cmdlet to change the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span> 
  
```Powershell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"

```

<span data-ttu-id="754e2-p118">若要验证已成功更改组的属性，请使用 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet 验证更改。使用远程 PowerShell 的一个优势是可以查看多个组的多个属性。在之前更改主 SMTP 地址组的示例中，运行以下命令来验证新值：</span><span class="sxs-lookup"><span data-stu-id="754e2-p118">To verify that you've successfully changed the properties for a group, use the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet to verify the changes. One advantage of using remote PowerShell is that you can view multiple properties for multiple groups. In the previous example where the primary SMTP address group was changed, run the following command to verify the new value:</span></span> 
  
```Powershell
Get-Recipient "Seattle Employees" | FL "PrimarySmtpAddress"

```

<span data-ttu-id="754e2-p119">此示例使用 [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet 更新"西雅图员工"组的所有成员。使用逗号分隔所有成员。</span><span class="sxs-lookup"><span data-stu-id="754e2-p119">This example uses the [Update-EOPDistributionGroupMember](http://technet.microsoft.com/library/a6d4f790-1b94-42f8-af6f-fa79c504d8ec.aspx) cmdlet to update all the members of the Seattle Employees group. Use a comma to separate all members.</span></span> 
  
```Powershell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")

```

<span data-ttu-id="754e2-176">若要获取组"西雅图员工"中所有成员的列表，请使用 [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="754e2-176">To get the list of all the members in the group Seattle Employees, use the [Get-DistributionGroupMember](http://technet.microsoft.com/library/15c71bc5-4246-44ac-8b34-8ccd585294b5.aspx) cmdlet as follows:</span></span> 
  
```Powershell
Get-DistributionGroupMember "Seattle Employees"

```

 <span data-ttu-id="754e2-177">**使用远程 Windows PowerShell 删除组**</span><span class="sxs-lookup"><span data-stu-id="754e2-177">**To remove a group using remote Windows PowerShell**</span></span>
  
<span data-ttu-id="754e2-178">此示例使用 [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet 删除名为"IT 管理员"的通讯组。</span><span class="sxs-lookup"><span data-stu-id="754e2-178">This example uses the [Remove-EOPDistributionGroup](http://technet.microsoft.com/library/a17b1307-3187-40b0-a438-c7b35a34c002.aspx) cmdlet to remove a distribution group named IT Administrators.</span></span> 
  
```Powershell
Remove-EOPDistributionGroup -Identity "IT Administrators" 

```

<span data-ttu-id="754e2-179">若要验证该组已删除，请运行 [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet，如下所示，并确认该组（在此案例中为"IT 管理员"）已删除。</span><span class="sxs-lookup"><span data-stu-id="754e2-179">To verify that the group was removed, run the [Get-Recipient](http://technet.microsoft.com/library/2ce6250f-0ad3-4b29-870c-e1d6e1e154bc.aspx) cmdlet as follows, and confirm that the group (in this case "It Administrators") was deleted.</span></span> 
  
```Powershell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"

```


