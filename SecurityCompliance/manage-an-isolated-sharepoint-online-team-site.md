---
title: 管理独立 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 摘要： 管理您的独立的 SharePoint Online 团队网站使用这些过程。
ms.openlocfilehash: 22b4cbbdd926635286d23570e1f61b64529d0e76
ms.sourcegitcommit: e0f016aca7befc8806233a492ee916cbe646094f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "25345934"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="2b844-103">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="2b844-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="2b844-104">**摘要：** 管理您的独立的 SharePoint Online 团队网站使用这些过程。</span><span class="sxs-lookup"><span data-stu-id="2b844-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="2b844-105">本文介绍为独立的 SharePoint Online 团队网站的常见管理操作。</span><span class="sxs-lookup"><span data-stu-id="2b844-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="2b844-106">添加新用户</span><span class="sxs-lookup"><span data-stu-id="2b844-106">Add a new user</span></span>

<span data-ttu-id="2b844-107">当某个新人加入网站时，您必须决定在网站中的参与其级别：</span><span class="sxs-lookup"><span data-stu-id="2b844-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="2b844-108">管理： 将新的用户帐户添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="2b844-109">活动的协作： 向网站添加用户帐户成员访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="2b844-110">查看： 将用户帐户添加到网站查看器访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="2b844-111">如果您在管理用户帐户和组通过 Windows Server Active Directory (AD)，将相应的用户添加到适当的访问组使用您正常的 Windows Server AD 用户和组管理过程并等待与同步您Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b844-111">If you are managing user accounts and groups through Windows Server Active Directory (AD), add the appropriate users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="2b844-112">如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b844-112">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="2b844-113">对于 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户添加到适当的访问组。</span><span class="sxs-lookup"><span data-stu-id="2b844-113">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="2b844-p101">Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要向其用户主体名称 (UPN) 与 access 组添加用户帐户，使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="2b844-p101">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="2b844-116">对于包含所有 PowerShell 命令和 Excel 的文本文件配置工作表中生成 PowerShell 命令的基于您的组和用户帐户名，下载[独立 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="2b844-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="2b844-117">若要向其显示名称与 access 组添加用户帐户，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="2b844-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="2b844-118">添加新组</span><span class="sxs-lookup"><span data-stu-id="2b844-118">Add a new group</span></span>

<span data-ttu-id="2b844-119">若要添加到整个组的访问，必须决定参与组的所有成员的站点中的级别：</span><span class="sxs-lookup"><span data-stu-id="2b844-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="2b844-120">管理： 将组添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="2b844-121">活动的协作： 将组添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="2b844-122">查看： 将组添加到网站查看器访问组</span><span class="sxs-lookup"><span data-stu-id="2b844-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="2b844-123">如果您在管理用户帐户和通过 Windows Server AD 的组，将相应的组添加到适当的组使用普通的 Windows Server AD 用户和组管理过程并等待与 Office 365 订阅的同步。</span><span class="sxs-lookup"><span data-stu-id="2b844-123">If you are managing user accounts and groups through Windows Server AD, add the appropriate groups to the appropriate groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="2b844-124">如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b844-124">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="2b844-125">对于 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的组添加到适当的访问组。</span><span class="sxs-lookup"><span data-stu-id="2b844-125">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="2b844-p102">Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。然后，使用以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2b844-p102">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="2b844-128">删除用户</span><span class="sxs-lookup"><span data-stu-id="2b844-128">Remove a user</span></span>

<span data-ttu-id="2b844-129">必须从网站删除某人的访问，它们从组中删除访问它们所当前基于其参与网站成员：</span><span class="sxs-lookup"><span data-stu-id="2b844-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="2b844-130">管理： 删除网站管理员访问组中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="2b844-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="2b844-131">活动的协作： 删除网站成员访问组中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="2b844-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="2b844-132">查看： 删除网站的查看者访问组中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="2b844-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="2b844-133">如果您在管理用户帐户和组通过 Windows Server AD，从使用普通的 Windows Server AD 用户和组管理过程的适当的访问组中删除相应的用户并等待与 Office 365 同步订阅。</span><span class="sxs-lookup"><span data-stu-id="2b844-133">If you are managing user accounts and groups through Windows Server AD, remove the appropriate users from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="2b844-134">如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b844-134">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="2b844-135">为 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录并使用组来从适当的访问组中删除相应的用户。</span><span class="sxs-lookup"><span data-stu-id="2b844-135">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="2b844-p103">Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要从其 UPN 与访问组中删除的用户帐户，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="2b844-p103">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="2b844-138">若要从其显示名称访问组中删除的用户帐户，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="2b844-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="2b844-139">删除组</span><span class="sxs-lookup"><span data-stu-id="2b844-139">Remove a group</span></span>

<span data-ttu-id="2b844-140">删除整个组的访问权限，您可以从它们所当前基于其参与网站成员访问组中删除组：</span><span class="sxs-lookup"><span data-stu-id="2b844-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="2b844-141">管理： 删除从网站管理员访问组的组</span><span class="sxs-lookup"><span data-stu-id="2b844-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="2b844-142">活动的协作： 删除从网站成员访问组的组</span><span class="sxs-lookup"><span data-stu-id="2b844-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="2b844-143">查看： 删除从网站查看器访问组的组</span><span class="sxs-lookup"><span data-stu-id="2b844-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="2b844-144">如果您在管理用户帐户和通过 Windows Server Active Directory 组，从使用您正常的 Windows Server AD 用户和组管理过程的适当的访问组中删除相应的组并等待与同步您Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b844-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="2b844-145">如果您在管理用户帐户和组通过 Office 365，您可以使用 Office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b844-145">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="2b844-146">为 Office 管理中心中，使用已分配的用户帐户管理员或公司管理员角色的用户帐户登录并使用组来从适当的访问组中删除相应的组。</span><span class="sxs-lookup"><span data-stu-id="2b844-146">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="2b844-147">Powershell，第一个[使用 Azure Active Directory V2 PowerShell 模块的连接](https://go.microsoft.com/fwlink/?linkid=842218)。</span><span class="sxs-lookup"><span data-stu-id="2b844-147">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>    
<span data-ttu-id="2b844-148">若要从使用其显示名称的访问组中删除组，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="2b844-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="2b844-149">使用自定义权限创建的文档子文件夹</span><span class="sxs-lookup"><span data-stu-id="2b844-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="2b844-p104">在某些情况下，使用隔离网站内的人员的子集需要进行协作的更多专用位置。对于 SharePoint Online 网站，您可以在网站的文档文件夹中创建子文件夹，并分配自定义权限。那些没有权限将不会看到子文件夹。</span><span class="sxs-lookup"><span data-stu-id="2b844-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="2b844-153">要创建自定义权限文档子文件夹，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2b844-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="2b844-p105">使用网站的管理员访问组的成员的帐户登录到 Office 365。为了帮助，请参阅[从何处登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="2b844-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="2b844-156">转到独立的工作组网站，并单击**文档**。</span><span class="sxs-lookup"><span data-stu-id="2b844-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="2b844-157">浏览到的文件夹中文档文件夹，将包含自定义权限的子文件夹，创建文件夹，然后再打开它。</span><span class="sxs-lookup"><span data-stu-id="2b844-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="2b844-158">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="2b844-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="2b844-159">单击**与共享 > 高级**。</span><span class="sxs-lookup"><span data-stu-id="2b844-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="2b844-160">单击**停止继承权限**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2b844-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="2b844-161">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="2b844-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="2b844-162">单击**与共享 > 高级**。</span><span class="sxs-lookup"><span data-stu-id="2b844-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="2b844-163">单击**授予权限 > 与共享 > 高级**。</span><span class="sxs-lookup"><span data-stu-id="2b844-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="2b844-164">在权限页上单击**\<网站名称 > 列表中的成员**。</span><span class="sxs-lookup"><span data-stu-id="2b844-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="2b844-165">在**\<网站名称 > 成员**页上，选择网站成员访问组旁的复选标记，单击**操作**，单击**删除用户组**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2b844-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="2b844-166">若要添加此子文件夹的特定成员，请单击**新建 > 将用户添加**。</span><span class="sxs-lookup"><span data-stu-id="2b844-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="2b844-167">在**共享**对话框中，键入可以协作处理的子文件夹中的文件，然后单击**共享**的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="2b844-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="2b844-168">刷新网页以查看新的结果。</span><span class="sxs-lookup"><span data-stu-id="2b844-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="2b844-169">在左侧导航窗格中的**组**下, 单击**\<网站名称 > 访问者**组并用于指定一组可以查看文件的子文件夹中 （根据需要） 的用户帐户的步骤 11 至 14。</span><span class="sxs-lookup"><span data-stu-id="2b844-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="2b844-170">在左侧导航窗格中的**组**下, 单击**\<网站名称 > 所有者**组和步骤 11 至 14 用于指定的用户帐户 （根据需要） 可以管理子文件夹中的权限集。</span><span class="sxs-lookup"><span data-stu-id="2b844-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="2b844-171">关闭浏览器中的**人员和组**选项卡。</span><span class="sxs-lookup"><span data-stu-id="2b844-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2b844-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b844-172">See Also</span></span>

[<span data-ttu-id="2b844-173">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="2b844-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="2b844-174">设计独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="2b844-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="2b844-175">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="2b844-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



