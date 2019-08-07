---
title: 部署独立的 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: '摘要: 使用这些分步说明部署一个新的独立 SharePoint Online 团队网站。'
ms.openlocfilehash: 06b7fdbc0e387ee2181a850e950537f3fed5ae50
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36053099"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="76868-103">部署独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="76868-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="76868-104">**摘要:** 按照这些分步说明部署一个新的独立 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="76868-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="76868-105">本文是在 Microsoft Office 365 中创建和配置独立的 SharePoint Online 团队网站的分步部署指南。</span><span class="sxs-lookup"><span data-stu-id="76868-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="76868-106">这些步骤假定使用三个默认 SharePoint 组和相应的权限级别, 每个级别的访问权限都有一个基于 Azure Active Directory (AD) 的访问组。</span><span class="sxs-lookup"><span data-stu-id="76868-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="76868-107">第1阶段: 创建和填充团队网站访问组</span><span class="sxs-lookup"><span data-stu-id="76868-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="76868-108">在此阶段中, 您将为三个默认 SharePoint 组创建三个基于 Azure AD 的访问组, 并使用适当的用户帐户填充它们。</span><span class="sxs-lookup"><span data-stu-id="76868-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76868-109">以下步骤假定所有必需的用户帐户都已存在, 并为其分配了适当的许可证。</span><span class="sxs-lookup"><span data-stu-id="76868-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="76868-110">如果不是, 请先添加它们并分配许可证, 然后再继续执行步骤1。</span><span class="sxs-lookup"><span data-stu-id="76868-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="76868-111">步骤 1: 列出网站的 SharePoint Online 管理员</span><span class="sxs-lookup"><span data-stu-id="76868-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="76868-112">确定对应于独立团队网站的 SharePoint Online 管理员的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="76868-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="76868-113">如果您通过 Office 365 管理用户帐户和组, 并且想要使用 Windows PowerShell, 请创建其用户主体名称 (upn) 列表 (示例 UPN: belindan@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="76868-113">If you are managing user accounts and groups through Office 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="76868-114">步骤 2: 列出网站的成员</span><span class="sxs-lookup"><span data-stu-id="76868-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="76868-115">确定与独立团队网站的成员对应的用户帐户集, 这些用户帐户将对存储在网站中的资源进行协作。</span><span class="sxs-lookup"><span data-stu-id="76868-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="76868-116">如果您通过 Office 365 管理用户帐户和组, 并且想要使用 PowerShell, 请创建其 Upn 的列表。</span><span class="sxs-lookup"><span data-stu-id="76868-116">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="76868-117">如果有大量的网站成员, 则可以将 Upn 列表存储在一个文本文件中, 并将它们全部添加到一个 PowerShell 命令中。</span><span class="sxs-lookup"><span data-stu-id="76868-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="76868-118">步骤 3: 列出网站的查看者</span><span class="sxs-lookup"><span data-stu-id="76868-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="76868-119">确定与独立团队网站的查看者相对应的用户帐户集, 这些用户可以查看存储在网站中的资源, 但不能对其内容进行修改, 也不能直接对其内容进行协作。</span><span class="sxs-lookup"><span data-stu-id="76868-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="76868-120">如果您通过 Office 365 管理用户帐户和组, 并且想要使用 PowerShell, 请创建其 Upn 的列表。</span><span class="sxs-lookup"><span data-stu-id="76868-120">If you are managing user accounts and groups through Office 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="76868-121">如果有大量的网站成员, 则可以将 Upn 列表存储在一个文本文件中, 并将它们全部添加到一个 PowerShell 命令中。</span><span class="sxs-lookup"><span data-stu-id="76868-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="76868-122">网站的查看者可能包括行政管理、法律顾问或部门间利益干系人。</span><span class="sxs-lookup"><span data-stu-id="76868-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="76868-123">步骤 4: 在 Azure AD 中为网站创建三个访问组</span><span class="sxs-lookup"><span data-stu-id="76868-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="76868-124">您需要在 Azure AD 中创建以下访问组:</span><span class="sxs-lookup"><span data-stu-id="76868-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="76868-125">网站管理员 (将包含步骤1中的列表)</span><span class="sxs-lookup"><span data-stu-id="76868-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="76868-126">网站成员 (将包含步骤2中的列表)</span><span class="sxs-lookup"><span data-stu-id="76868-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="76868-127">网站查看器 (将包含步骤3中的列表)</span><span class="sxs-lookup"><span data-stu-id="76868-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="76868-128">在浏览器中, 转到 Azure 门户, [https://portal.azure.com](https://portal.azure.com)并使用已分配给用户管理管理员或公司管理员角色的帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="76868-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="76868-129">在 Azure 门户中，单击“**Azure Active Directory”>“组**”。</span><span class="sxs-lookup"><span data-stu-id="76868-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="76868-130">在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。</span><span class="sxs-lookup"><span data-stu-id="76868-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="76868-131">在**新组**边栏上:</span><span class="sxs-lookup"><span data-stu-id="76868-131">On the **New Group** blade:</span></span>
    
  - <span data-ttu-id="76868-132">选择 "**组类型**中的**安全性**"。</span><span class="sxs-lookup"><span data-stu-id="76868-132">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="76868-133">在 "**名称**" 中键入组名称。</span><span class="sxs-lookup"><span data-stu-id="76868-133">Type the group name in **Name**.</span></span>
    
  - <span data-ttu-id="76868-134">在 "**组说明**" 中键入组的说明。</span><span class="sxs-lookup"><span data-stu-id="76868-134">Type a description of the group in **Group description**.</span></span>
    
  - <span data-ttu-id="76868-135">在“**成员身份**”类型中，选择“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="76868-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="76868-136">单击“**创建**”，然后关闭“**组**”边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="76868-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="76868-137">对其他组重复步骤3-5。</span><span class="sxs-lookup"><span data-stu-id="76868-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76868-138">您需要使用 Azure 门户来创建组, 以便他们启用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="76868-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="76868-139">如果后来将 SharePoint Online 独立网站配置为具有 Azure 信息保护标签的高度机密网站来加密文件, 并为特定组分配权限, 则必须已在启用 Office 功能的情况下创建允许的组。</span><span class="sxs-lookup"><span data-stu-id="76868-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="76868-140">Azure AD 组创建后, 无法更改其 Office 功能设置。</span><span class="sxs-lookup"><span data-stu-id="76868-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="76868-141">下面是具有三个网站访问组的结果配置。</span><span class="sxs-lookup"><span data-stu-id="76868-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![用于部署独立 SharePoint Online 网站的三个访问组。](media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="76868-143">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="76868-143">Step 5.</span></span> <span data-ttu-id="76868-144">将用户帐户添加到访问组</span><span class="sxs-lookup"><span data-stu-id="76868-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="76868-145">在此步骤中, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="76868-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="76868-146">将步骤1中的用户列表添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="76868-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="76868-147">将步骤2中的用户列表添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="76868-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="76868-148">将步骤3中的用户列表添加到 "网站查看者访问" 组</span><span class="sxs-lookup"><span data-stu-id="76868-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="76868-149">如果通过 Active Directory 域服务 (AD DS) 管理用户帐户和组, 请使用常规 AD DS 用户和组管理程序将用户添加到相应的访问组, 并等待与 Office 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="76868-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Office 365 subscription.</span></span>
  
<span data-ttu-id="76868-150">如果通过 Office 365 管理用户帐户和组, 则可以使用 Microsoft 365 管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="76868-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="76868-151">如果有任何访问组的组名称重复, 则应使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="76868-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="76868-152">对于 Microsoft 365 管理中心, 使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录, 并使用组将相应的用户帐户和组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="76868-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="76868-153">对于 PowerShell, 首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="76868-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="76868-154">接下来, 使用以下命令块将单个用户帐户添加到访问组中:</span><span class="sxs-lookup"><span data-stu-id="76868-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

> [!TIP]
> <span data-ttu-id="76868-155">对于包含所有 PowerShell 命令的文本文件和基于您的组和用户帐户名称生成 PowerShell 命令的 Excel 配置工作表, 请下载[独立的 SharePoint Online 团队网站部署工具包](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907)。</span><span class="sxs-lookup"><span data-stu-id="76868-155">For a text file that contains all the PowerShell commands and an Excel configuration worksheet that generates PowerShell commands based on your group and user account names, download the [Isolated SharePoint Online Team Site Deployment Kit](https://gallery.technet.microsoft.com/Isolated-SharePoint-Online-0b364907).</span></span> 
  
<span data-ttu-id="76868-156">如果您为文本文件中的任何访问组存储了用户帐户的 Upn, 则可以使用下面的 PowerShell 命令块一次添加所有这些组:</span><span class="sxs-lookup"><span data-stu-id="76868-156">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="76868-157">对于 PowerShell, 使用以下命令块将单个组添加到访问组中:</span><span class="sxs-lookup"><span data-stu-id="76868-157">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="76868-158">结果应如下所示:</span><span class="sxs-lookup"><span data-stu-id="76868-158">The results should be the following:</span></span>
  
- <span data-ttu-id="76868-159">网站管理员 Azure AD 组包含网站管理员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="76868-159">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="76868-160">网站成员 Azure AD 组包含网站成员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="76868-160">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="76868-161">网站查看器 Azure AD 组包含仅可查看网站内容的用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="76868-161">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="76868-162">使用 Microsoft 365 管理中心或以下 PowerShell 命令块验证每个访问组的组成员列表:</span><span class="sxs-lookup"><span data-stu-id="76868-162">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="76868-163">下面是通过使用用户帐户或组填充的三个网站访问组生成的配置。</span><span class="sxs-lookup"><span data-stu-id="76868-163">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![三个使用用户帐户填充的访问组。](media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="76868-165">阶段 2: 创建和配置独立的团队网站</span><span class="sxs-lookup"><span data-stu-id="76868-165">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="76868-166">在此阶段中, 您将创建独立的 SharePoint Online 网站, 并将默认 SharePoint Online 权限级别的权限配置为使用新的基于 Azure AD 的访问组。</span><span class="sxs-lookup"><span data-stu-id="76868-166">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span>
  
<span data-ttu-id="76868-167">首先, 使用这些步骤创建 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="76868-167">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="76868-168">使用将同时用于管理 SharePoint Online 团队网站的帐户（即 SharePoint Online 管理员帐户）登录管理中心。</span><span class="sxs-lookup"><span data-stu-id="76868-168">Sign in to the admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="76868-169">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="76868-169">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="76868-170">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-170">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="76868-171">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="76868-171">In the new **SharePoint** tab of your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="76868-172">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-172">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="76868-173">在 "**网站名称**" 中, 键入团队网站的名称。</span><span class="sxs-lookup"><span data-stu-id="76868-173">In **Site name**, type a name for the team site.</span></span> 
    
6. <span data-ttu-id="76868-174">在 "**团队网站说明" 中,** 键入网站用途的可选说明。</span><span class="sxs-lookup"><span data-stu-id="76868-174">In **Team site description,** type an optional description of the purpose of the site.</span></span>
    
7. <span data-ttu-id="76868-175">在“隐私设置”中，选择“专用 - 仅成员可以访问此网站”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-175">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="76868-176">在“希望添加哪些人员?”窗格中，单击“完成”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-176">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="76868-177">接下来, 从新的 SharePoint Online 团队网站配置权限。</span><span class="sxs-lookup"><span data-stu-id="76868-177">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="76868-178">在工具栏中，依次单击设置图标和“网站权限”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-178">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
2. <span data-ttu-id="76868-179">在“网站权限”窗格中，单击“高级权限设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-179">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
3. <span data-ttu-id="76868-180">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-180">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
    
4. <span data-ttu-id="76868-181">在 "**访问请求设置**" 对话框中, 清除 "**允许成员" 以共享网站和各个文件和文件夹**, 并**允许访问请求**(以便清除所有三个复选框), 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="76868-181">In the **Access Requests Settings** dialog box, clear **Allow member to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
5. <span data-ttu-id="76868-182">在浏览器的 "**权限**" 选项卡上, 单击\*\* \<\*\* 列表中的 "网站名称"> 成员。</span><span class="sxs-lookup"><span data-stu-id="76868-182">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
6. <span data-ttu-id="76868-183">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-183">In **People and Groups**, click **New**.</span></span>
    
7. <span data-ttu-id="76868-184">在 "**共享**" 对话框中, 键入网站成员访问组的名称, 选择它, 然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="76868-184">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
8. <span data-ttu-id="76868-185">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="76868-185">Click the back button on your browser.</span></span>
    
9. <span data-ttu-id="76868-186">单击列表中的 " \*\* \<网站名称"> 所有者\*\*"。</span><span class="sxs-lookup"><span data-stu-id="76868-186">Click **\<site name> Owners** in the list.</span></span>
    
10. <span data-ttu-id="76868-187">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-187">In **People and Groups**, click **New**.</span></span>
    
11. <span data-ttu-id="76868-188">在 "**共享**" 对话框中, 键入 "网站管理员" 访问组的名称, 选择它, 然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="76868-188">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
12. <span data-ttu-id="76868-189">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="76868-189">Click the back button on your browser.</span></span>
    
13. <span data-ttu-id="76868-190">在列表中单击 " \*\* \<网站名称"> 访问者\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-190">Click **\<site name> Visitors** in the list.</span></span>
    
14. <span data-ttu-id="76868-191">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-191">In **People and Groups**, click **New**.</span></span>
    
15. <span data-ttu-id="76868-192">在 "**共享**" 对话框中, 键入 "网站查看者访问" 组的名称, 选择它, 然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="76868-192">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="76868-193">关闭浏览器的“权限”标签页\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="76868-193">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="76868-194">以下是这些权限设置的结果：</span><span class="sxs-lookup"><span data-stu-id="76868-194">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="76868-195">" \*\* \<网站名称> 所有者**" SharePoint 组包含 "网站管理员" 访问组, 其中所有成员都具有 "**完全控制\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="76868-195">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="76868-196">" \*\* \<网站名称> 成员**" SharePoint 组包含 "网站成员" 访问组, 其中所有成员都具有 "**编辑\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="76868-196">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="76868-197">" \*\* \<网站名称> 访问者**" SharePoint 组包含 "网站查看者" 访问组, 其中所有成员都具有 "**读取\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="76868-197">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="76868-198">禁用成员邀请其他成员或非成员请求访问的功能已被禁用。</span><span class="sxs-lookup"><span data-stu-id="76868-198">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="76868-199">下面是配置了三个 SharePoint 组的网站的结果配置, 该网站配置为使用三个访问组, 其中填充了用户帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="76868-199">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![使用访问组和用户帐户的独立 SharePoint Online 网站的最终配置。](media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="76868-201">您和网站成员 (通过其中一个访问组中的组成员身份) 现在可以使用网站的资源进行协作。</span><span class="sxs-lookup"><span data-stu-id="76868-201">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="76868-202">后续步骤</span><span class="sxs-lookup"><span data-stu-id="76868-202">Next step</span></span>

<span data-ttu-id="76868-203">如果需要更改网站访问组成员身份或创建具有自定义权限的文档文件夹, 请参阅[管理独立的 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="76868-203">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="76868-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76868-204">See Also</span></span>

[<span data-ttu-id="76868-205">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="76868-205">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="76868-206">设计独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="76868-206">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="76868-207">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="76868-207">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



