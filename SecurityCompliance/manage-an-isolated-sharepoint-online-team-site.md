---
title: 管理独立 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: '摘要: 使用这些过程管理独立的 SharePoint Online 团队网站。'
ms.openlocfilehash: 81a6fcd80bb3e4950eb7b783d1ad964b9bc67cc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214482"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="d720d-103">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d720d-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="d720d-104">**摘要:** 使用这些过程管理独立的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="d720d-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="d720d-105">本文介绍了独立的 SharePoint Online 团队网站的常见管理操作。</span><span class="sxs-lookup"><span data-stu-id="d720d-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="d720d-106">添加新用户</span><span class="sxs-lookup"><span data-stu-id="d720d-106">Add a new user</span></span>

<span data-ttu-id="d720d-107">当有人新建加入网站时, 您必须决定其在网站中的参与级别:</span><span class="sxs-lookup"><span data-stu-id="d720d-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="d720d-108">管理: 将新用户帐户添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="d720d-109">主动协作: 将用户帐户添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="d720d-110">查看: 将用户帐户添加到网站查看者访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="d720d-111">如果通过 Windows Server Active Directory (AD) 管理用户帐户和组, 请使用正常的 Windows server AD 用户和组管理程序将相应的用户添加到相应的访问组, 并等待与您的计算机同步Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="d720d-111">If you are managing user accounts and groups through Windows Server Active Directory (AD), add the appropriate users to the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="d720d-112">如果您通过 office 365 管理用户帐户和组, 则可以使用 office 管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d720d-112">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="d720d-113">对于 Office 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将相应的用户添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="d720d-113">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="d720d-p101">对于 PowerShell, 首先[使用 Azure Active Directory V2 PowerShell 模块进行连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要将用户帐户添加到具有其用户主体名称 (UPN) 的访问组, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="d720d-p101">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="d720d-116">对于包含所有 powershell 命令的文本文件和基于您的组和用户帐户名称生成 PowerShell 命令的 Excel 配置工作表, 请下载[独立的 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="d720d-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="d720d-117">若要向具有其显示名称的访问组添加用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="d720d-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="d720d-118">添加新组</span><span class="sxs-lookup"><span data-stu-id="d720d-118">Add a new group</span></span>

<span data-ttu-id="d720d-119">若要添加对整个组的访问权限, 您必须确定网站中组的所有成员的参与级别:</span><span class="sxs-lookup"><span data-stu-id="d720d-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="d720d-120">管理: 将组添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="d720d-121">主动协作: 将组添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="d720d-122">查看: 将组添加到网站查看器访问组</span><span class="sxs-lookup"><span data-stu-id="d720d-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="d720d-123">如果通过 Windows Server ad 管理用户帐户和组, 请使用正常的 Windows server ad 用户和组管理过程将适当的组添加到适当的组, 并等待与 Office 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="d720d-123">If you are managing user accounts and groups through Windows Server AD, add the appropriate groups to the appropriate groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="d720d-124">如果您通过 office 365 管理用户帐户和组, 则可以使用 office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d720d-124">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="d720d-125">对于 Office 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将适当的组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="d720d-125">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="d720d-p102">对于 PowerShell, 首先[使用 Azure Active Directory V2 PowerShell 模块进行连接](https://go.microsoft.com/fwlink/?linkid=842218)。然后, 使用以下 PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="d720d-p102">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="d720d-128">删除用户</span><span class="sxs-lookup"><span data-stu-id="d720d-128">Remove a user</span></span>

<span data-ttu-id="d720d-129">当必须从网站中删除某人的访问权限时, 您可以从访问组中删除他们当前为其成员的访问组, 具体取决于其在网站中的参与情况:</span><span class="sxs-lookup"><span data-stu-id="d720d-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="d720d-130">管理: 从网站管理员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="d720d-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="d720d-131">主动协作: 从网站成员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="d720d-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="d720d-132">查看: 从网站查看器访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="d720d-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="d720d-133">如果通过 Windows Server ad 管理用户帐户和组, 请使用正常的 Windows server ad 用户和组管理过程从适当的访问组中删除相应的用户, 并等待与 Office 365 同步订购.</span><span class="sxs-lookup"><span data-stu-id="d720d-133">If you are managing user accounts and groups through Windows Server AD, remove the appropriate users from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="d720d-134">如果您通过 office 365 管理用户帐户和组, 则可以使用 office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d720d-134">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="d720d-135">对于 Office 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组从相应的访问组中删除相应的用户。</span><span class="sxs-lookup"><span data-stu-id="d720d-135">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="d720d-p103">对于 PowerShell, 首先[使用 Azure Active Directory V2 PowerShell 模块进行连接](https://go.microsoft.com/fwlink/?linkid=842218)。若要从具有 UPN 的访问组中删除用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="d720d-p103">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218). To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="d720d-138">若要从具有显示名称的访问组中删除用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="d720d-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="d720d-139">删除组</span><span class="sxs-lookup"><span data-stu-id="d720d-139">Remove a group</span></span>

<span data-ttu-id="d720d-140">若要删除对整个组的访问权限, 您可以从访问组中删除其当前为其成员的访问组, 这些组基于其在站点中的参与情况:</span><span class="sxs-lookup"><span data-stu-id="d720d-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="d720d-141">管理: 从网站管理员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="d720d-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="d720d-142">主动协作: 从网站成员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="d720d-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="d720d-143">查看: 从网站查看器访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="d720d-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="d720d-144">如果通过 Windows Server Active Directory 管理用户帐户和组, 请使用正常的 Windows server AD 用户和组管理过程从适当的访问组中删除相应的组, 并等待与您的计算机同步Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="d720d-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal Windows Server AD user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="d720d-145">如果您通过 office 365 管理用户帐户和组, 则可以使用 office 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d720d-145">If you are managing user accounts and groups through Office 365, you can use the Office Admin center or PowerShell:</span></span>
  
- <span data-ttu-id="d720d-146">对于 Office 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组从相应的访问组中删除相应的组。</span><span class="sxs-lookup"><span data-stu-id="d720d-146">For the Office Admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="d720d-147">对于 PowerShell, 首先[使用 Azure Active Directory V2 PowerShell 模块进行连接](https://go.microsoft.com/fwlink/?linkid=842218)。</span><span class="sxs-lookup"><span data-stu-id="d720d-147">For PowerShell, first [Connect with the Azure Active Directory V2 PowerShell module](https://go.microsoft.com/fwlink/?linkid=842218).</span></span>    
<span data-ttu-id="d720d-148">若要使用用户的显示名称从访问组中删除组, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="d720d-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="d720d-149">使用自定义权限创建 documents 子文件夹</span><span class="sxs-lookup"><span data-stu-id="d720d-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="d720d-p104">在某些情况下, 在独立网站中工作的人员的子集需要更多的专用空间进行协作。对于 SharePoint Online 网站, 可以在网站的 "文档" 文件夹中创建一个子文件夹, 并分配自定义权限。没有权限的人员将看不到子文件夹。</span><span class="sxs-lookup"><span data-stu-id="d720d-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="d720d-153">若要创建具有自定义权限的 documents 子文件夹, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d720d-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="d720d-p105">使用作为网站的管理员访问组成员的帐户登录到 Office 365。若要获取帮助, 请参阅[登录到 Office 365 的位置](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="d720d-p105">Sign in to Office 365 with an account that is a member of the admins access group for the site. For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="d720d-156">转到独立的团队网站, 然后单击 "**文档**"。</span><span class="sxs-lookup"><span data-stu-id="d720d-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="d720d-157">浏览到 "documents" 文件夹中将包含具有自定义权限的子文件夹的文件夹, 创建该文件夹, 然后将其打开。</span><span class="sxs-lookup"><span data-stu-id="d720d-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="d720d-158">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="d720d-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="d720d-159">单击 "**与 > 共享**" "高级"。</span><span class="sxs-lookup"><span data-stu-id="d720d-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="d720d-160">单击 "**停止继承权限**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d720d-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="d720d-161">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="d720d-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="d720d-162">单击 "**与 > 共享**" "高级"。</span><span class="sxs-lookup"><span data-stu-id="d720d-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="d720d-163">单击 "**授予权限 > 与 > 共享**" "高级"。</span><span class="sxs-lookup"><span data-stu-id="d720d-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="d720d-164">在 "权限" 页上, 单击\*\* \<列表中的 "网站 name> 成员"\*\*。</span><span class="sxs-lookup"><span data-stu-id="d720d-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="d720d-165">在 " \*\* \<网站 name> 成员**" 页上, 选中 "网站成员访问" 组旁边的复选标记, 单击 "**操作**", 单击 "**从组中删除用户\*\*", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d720d-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="d720d-166">若要向该子文件夹添加特定成员, 请单击 "**新建 > 添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="d720d-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="d720d-167">在 "**共享**" 对话框中, 键入可在子文件夹中的文件上进行协作的用户帐户的名称, 然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="d720d-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="d720d-168">刷新网页以查看新结果。</span><span class="sxs-lookup"><span data-stu-id="d720d-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="d720d-169">在左侧导航组中的 "**组**" 下, 单击 " \*\* \<网站 name> 访问者\*\*" 组, 并使用步骤11-14 指定可以查看子文件夹中的文件的用户帐户集 (根据需要)。</span><span class="sxs-lookup"><span data-stu-id="d720d-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="d720d-170">在左侧导航组中的 "**组**" 下, 单击 " \*\* \<网站 name> 所有者\*\*" 组, 并使用步骤11-14 指定可在子文件夹中管理权限的用户帐户集 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="d720d-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="d720d-171">关闭浏览器中的 "**人员和组**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d720d-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d720d-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d720d-172">See Also</span></span>

[<span data-ttu-id="d720d-173">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d720d-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="d720d-174">设计独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d720d-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="d720d-175">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="d720d-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



