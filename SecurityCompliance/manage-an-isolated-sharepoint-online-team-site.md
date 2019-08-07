---
title: 管理独立的 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: '摘要: 使用这些过程管理独立的 SharePoint Online 团队网站。'
ms.openlocfilehash: e6ed86421ec199ce785e2daff5e9c5447939e69b
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36053077"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="211d4-103">管理独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="211d4-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="211d4-104">**摘要:** 使用这些过程管理独立的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="211d4-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="211d4-105">本文介绍了独立的 SharePoint Online 团队网站的常见管理操作。</span><span class="sxs-lookup"><span data-stu-id="211d4-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="211d4-106">添加新用户</span><span class="sxs-lookup"><span data-stu-id="211d4-106">Add a new user</span></span>

<span data-ttu-id="211d4-107">当有人新建加入网站时, 您必须决定其在网站中的参与级别:</span><span class="sxs-lookup"><span data-stu-id="211d4-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="211d4-108">管理: 将新用户帐户添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="211d4-109">主动协作: 将用户帐户添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="211d4-110">查看: 将用户帐户添加到网站查看者访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="211d4-111">如果通过 Active Directory 域服务 (AD DS) 管理用户帐户和组, 请使用常规 AD DS 用户和组管理过程将相应的用户添加到相应的访问组, 并等待与 Office 365 同步订购.</span><span class="sxs-lookup"><span data-stu-id="211d4-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="211d4-112">如果通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211d4-112">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="211d4-113">对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将相应的用户添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="211d4-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="211d4-114">对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="211d4-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="211d4-115">若要将用户帐户添加到具有其用户主体名称 (UPN) 的访问组, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="211d4-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="211d4-116">对于包含所有 PowerShell 命令的文本文件和基于您的组和用户帐户名称生成 PowerShell 命令的 Excel 配置工作表, 请下载[独立的 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="211d4-116">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 

<span data-ttu-id="211d4-117">若要向具有其显示名称的访问组添加用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="211d4-117">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="211d4-118">添加新组</span><span class="sxs-lookup"><span data-stu-id="211d4-118">Add a new group</span></span>

<span data-ttu-id="211d4-119">若要添加对整个组的访问权限, 您必须确定网站中组的所有成员的参与级别:</span><span class="sxs-lookup"><span data-stu-id="211d4-119">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="211d4-120">管理: 将组添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-120">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="211d4-121">主动协作: 将组添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-121">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="211d4-122">查看: 将组添加到网站查看器访问组</span><span class="sxs-lookup"><span data-stu-id="211d4-122">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="211d4-123">如果通过 AD DS 管理用户帐户和组, 请使用常规 AD DS 用户和组管理过程将适当的组添加到适当的组, 并等待与 Office 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="211d4-123">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="211d4-124">如果您通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211d4-124">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="211d4-125">对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将适当的组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="211d4-125">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="211d4-126">对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="211d4-126">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="211d4-127">然后, 使用以下 PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="211d4-127">Then, use the following PowerShell commands:</span></span>
 
```
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="211d4-128">删除用户</span><span class="sxs-lookup"><span data-stu-id="211d4-128">Remove a user</span></span>

<span data-ttu-id="211d4-129">当必须从网站中删除某人的访问权限时, 您可以从访问组中删除他们当前为其成员的访问组, 具体取决于其在网站中的参与情况:</span><span class="sxs-lookup"><span data-stu-id="211d4-129">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="211d4-130">管理: 从网站管理员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="211d4-130">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="211d4-131">主动协作: 从网站成员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="211d4-131">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="211d4-132">查看: 从网站查看器访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="211d4-132">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="211d4-133">如果通过 AD DS 管理用户帐户和组, 请使用常规 AD DS 用户和组管理过程从适当的访问组中删除相应的用户, 并等待与 Office 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="211d4-133">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="211d4-134">如果您通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211d4-134">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="211d4-135">对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组从相应的访问组中删除相应的用户。</span><span class="sxs-lookup"><span data-stu-id="211d4-135">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="211d4-136">对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="211d4-136">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="211d4-137">若要从具有 UPN 的访问组中删除用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="211d4-137">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="211d4-138">若要从具有显示名称的访问组中删除用户帐户, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="211d4-138">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="211d4-139">删除组</span><span class="sxs-lookup"><span data-stu-id="211d4-139">Remove a group</span></span>

<span data-ttu-id="211d4-140">若要删除对整个组的访问权限, 您可以从访问组中删除其当前为其成员的访问组, 这些组基于其在站点中的参与情况:</span><span class="sxs-lookup"><span data-stu-id="211d4-140">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="211d4-141">管理: 从网站管理员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="211d4-141">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="211d4-142">主动协作: 从网站成员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="211d4-142">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="211d4-143">查看: 从网站查看器访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="211d4-143">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="211d4-144">如果通过 Windows Server Active Directory 管理用户帐户和组, 请使用常规 AD DS 用户和组管理过程从适当的访问组中删除相应的组, 并等待与 Office 365 同步订购.</span><span class="sxs-lookup"><span data-stu-id="211d4-144">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="211d4-145">如果您通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="211d4-145">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="211d4-146">对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组从相应的访问组中删除相应的组。</span><span class="sxs-lookup"><span data-stu-id="211d4-146">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="211d4-147">对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="211d4-147">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="211d4-148">若要使用用户的显示名称从访问组中删除组, 请使用以下 PowerShell 命令块:</span><span class="sxs-lookup"><span data-stu-id="211d4-148">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="211d4-149">使用自定义权限创建 documents 子文件夹</span><span class="sxs-lookup"><span data-stu-id="211d4-149">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="211d4-150">在某些情况下, 在独立网站中工作的人员的子集需要更多的专用空间进行协作。</span><span class="sxs-lookup"><span data-stu-id="211d4-150">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="211d4-151">对于 SharePoint Online 网站, 可以在网站的 "文档" 文件夹中创建一个子文件夹, 并分配自定义权限。</span><span class="sxs-lookup"><span data-stu-id="211d4-151">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="211d4-152">没有权限的人员将看不到子文件夹。</span><span class="sxs-lookup"><span data-stu-id="211d4-152">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="211d4-153">若要创建具有自定义权限的 documents 子文件夹, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="211d4-153">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="211d4-154">使用作为网站的管理员访问组成员的帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="211d4-154">Sign in to Office 365 with an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="211d4-155">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="211d4-155">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="211d4-156">转到独立的团队网站, 然后单击 "**文档**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-156">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="211d4-157">浏览到 "documents" 文件夹中将包含具有自定义权限的子文件夹的文件夹, 创建该文件夹, 然后将其打开。</span><span class="sxs-lookup"><span data-stu-id="211d4-157">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="211d4-158">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="211d4-158">Click **Share**.</span></span>
    
5. <span data-ttu-id="211d4-159">单击 "**共享并 > 高级**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-159">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="211d4-160">单击 "**停止继承权限**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="211d4-160">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="211d4-161">单击"共享"。</span><span class="sxs-lookup"><span data-stu-id="211d4-161">Click **Share**.</span></span>
    
8. <span data-ttu-id="211d4-162">单击 "**共享并 > 高级**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-162">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="211d4-163">单击 "**授予权限 > 与 > 高级共享**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-163">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="211d4-164">在 "权限" 页上, 单击\*\* \<列表中的 "网站名称"> 成员\*\*。</span><span class="sxs-lookup"><span data-stu-id="211d4-164">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="211d4-165">在 " \*\* \<网站名称> 成员**" 页上, 选择 "网站成员访问" 组旁边的复选标记, 单击 "**操作**", 单击 "**从组中删除用户\*\*", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="211d4-165">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="211d4-166">若要将特定成员添加到此子文件夹, 请单击 "**新建 > 添加用户**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-166">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="211d4-167">在 "**共享**" 对话框中, 键入可在子文件夹中的文件上进行协作的用户帐户的名称, 然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="211d4-167">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="211d4-168">刷新网页以查看新结果。</span><span class="sxs-lookup"><span data-stu-id="211d4-168">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="211d4-169">在左侧导航组中的 "**组**" 下, 单击 " \*\* \<网站名称"> "访问者\*\*" 组, 并使用步骤11-14 指定可以查看子文件夹中的文件的用户帐户集 (根据需要)。</span><span class="sxs-lookup"><span data-stu-id="211d4-169">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="211d4-170">在左侧导航组中的 "**组**" 下, 单击 " \*\* \<网站名称"> "所有者\*\*" 组, 然后使用步骤11-14 指定可在子文件夹中管理权限的用户帐户集 (根据需要)。</span><span class="sxs-lookup"><span data-stu-id="211d4-170">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="211d4-171">关闭浏览器中的 "**人员和组**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="211d4-171">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="211d4-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="211d4-172">See Also</span></span>

[<span data-ttu-id="211d4-173">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="211d4-173">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="211d4-174">设计独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="211d4-174">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="211d4-175">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="211d4-175">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



