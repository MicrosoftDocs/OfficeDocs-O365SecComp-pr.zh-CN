---
title: 在开发/测试环境中保护 SharePoint Online 网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 摘要：在开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。
ms.openlocfilehash: bc17f5a4009b7a967a395084e8a058c45bbad82e
ms.sourcegitcommit: 6122eb026c558a5126c40845e656fbb0c40cb32a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36053129"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a><span data-ttu-id="4926d-103">在开发/测试环境中保护 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="4926d-103">Secure SharePoint Online sites in a dev/test environment</span></span>

 <span data-ttu-id="4926d-104">**摘要：** 在开发/测试环境中创建公共、专用、敏感和高度机密的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="4926d-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in a dev/test environment.</span></span>
  
<span data-ttu-id="4926d-105">本文提供了有关如何创建开发/测试环境的分步说明，该环境中包括用于[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)解决方案的四种不同类型的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="4926d-105">This article provides step-by-step instructions to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) solution.</span></span>
  
![安全 SharePoint Online 开发/测试环境中的所有四个团队网站。](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
<span data-ttu-id="4926d-107">使用此开发/测试环境来试验信息保护行为，并根据具体要求微调设置，然后在生产中部署 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="4926d-107">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-create-your-devtest-environment"></a><span data-ttu-id="4926d-108">阶段 1：创建开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="4926d-108">Phase 1: Create your dev/test environment</span></span>

<span data-ttu-id="4926d-109">在此阶段，将获取用于虚拟组织的 Office 365 和企业移动性 + 安全性 (EMS) 的试用订阅。</span><span class="sxs-lookup"><span data-stu-id="4926d-109">In this phase, you obtain trial subscriptions for Office 365 and Enterprise Mobility + Security (EMS) for a fictional organization.</span></span>
  
<span data-ttu-id="4926d-110">首先，按照 [Office 365 开发/测试环境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的**阶段 2** 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4926d-110">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="4926d-111">下一步，注册 EMS 试用订阅，并将其作为 Office 365 试用订阅添加到同一组织。</span><span class="sxs-lookup"><span data-stu-id="4926d-111">Next, sign up for the EMS trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="4926d-112">如有需要，请使用试用订阅的全局管理员帐户的凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-112">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-113">在左侧导航栏中，依次单击 **“计费”>“购买服务”**。</span><span class="sxs-lookup"><span data-stu-id="4926d-113">In the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="4926d-p101">在“购买服务”页上，找到“企业移动性 + 安全性 E5”项。将鼠标指针悬停在此项之上，然后单击“开始免费试用”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-p101">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
4. <span data-ttu-id="4926d-116">在“确认订单”页上，单击“立即试用”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
5. <span data-ttu-id="4926d-117">在“订单签收”页中，单击“继续”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="4926d-118">接下来，为全局管理员帐户启用企业移动性 + 安全性 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="4926d-118">Next, enable the Enterprise Mobility + Security E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="4926d-119">在浏览器的“Microsoft 365 管理中心”标签页的左侧导航中，单击“用户”>“活动用户”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="4926d-120">单击全局管理员帐户，然后针对“产品许可证”单击“编辑”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="4926d-121">在“**产品许可证**”窗格，将**企业移动 +安全 E5** 的产品许可证设置为“**打开**”，单击“**保存**”，然后单击“**关闭**”两次。</span><span class="sxs-lookup"><span data-stu-id="4926d-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="4926d-122">阶段 2：创建和配置 Azure Active Directory (AD) 组和用户</span><span class="sxs-lookup"><span data-stu-id="4926d-122">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="4926d-123">此阶段为虚构组织创建和配置 Azure AD 组和用户。</span><span class="sxs-lookup"><span data-stu-id="4926d-123">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="4926d-124">首先，通过 Azure 门户为典型组织创建一系列组。</span><span class="sxs-lookup"><span data-stu-id="4926d-124">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="4926d-p102">在浏览器中创建单独的标签页，然后转到 Azure 门户 ([https://portal.azure.com](https://portal.azure.com))。如有需要，请使用 Office 365 E5 试用订阅的全局管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="4926d-p102">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-127">在 Azure 门户中，单击“**Azure Active Directory”>“组**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-127">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="4926d-128">在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-128">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="4926d-129">在“**组**”边栏选项卡上：</span><span class="sxs-lookup"><span data-stu-id="4926d-129">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="4926d-130">在“**组类型**”中，选择“**Office 365**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-130">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="4926d-131">在“**名称**”中键入**高层管理人员**。</span><span class="sxs-lookup"><span data-stu-id="4926d-131">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="4926d-132">在“**成员身份**”类型中，选择“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-132">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="4926d-133">单击“**创建**”，然后关闭“**组**”边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="4926d-133">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="4926d-134">对以下组名称重复步骤 3-5：</span><span class="sxs-lookup"><span data-stu-id="4926d-134">Repeat steps 3-5 for the following group names:</span></span>
    
  - <span data-ttu-id="4926d-135">IT 人员</span><span class="sxs-lookup"><span data-stu-id="4926d-135">IT staff</span></span>
    
  - <span data-ttu-id="4926d-136">研究人员</span><span class="sxs-lookup"><span data-stu-id="4926d-136">Research staff</span></span>
    
  - <span data-ttu-id="4926d-137">正式员工</span><span class="sxs-lookup"><span data-stu-id="4926d-137">Regular staff</span></span>
    
  - <span data-ttu-id="4926d-138">市场营销人员</span><span class="sxs-lookup"><span data-stu-id="4926d-138">Marketing staff</span></span>
    
  - <span data-ttu-id="4926d-139">销售人员</span><span class="sxs-lookup"><span data-stu-id="4926d-139">Sales staff</span></span>
    
7. <span data-ttu-id="4926d-140">使浏览器中的 Azure 门户选项卡保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="4926d-140">Keep the Azure portal tab in your browser open.</span></span>
    
<span data-ttu-id="4926d-141">然后配置自动授权，以便组的成员可自动分配 Office 365 和 EMS 订阅的许可证。</span><span class="sxs-lookup"><span data-stu-id="4926d-141">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="4926d-142">在 Azure 门户中，单击“**Azure Active Directory”>“许可证”>“所有产品**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-142">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="4926d-143">在列表中，选择“**企业移动性 + 安全性 E5**”和“**Office 365 企业版 E5**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-143">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="4926d-144">在“**分配许可证**”边栏选项卡中，单击“**用户和组**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-144">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="4926d-145">在组列表中，选择以下各项：</span><span class="sxs-lookup"><span data-stu-id="4926d-145">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="4926d-146">高层管理人员</span><span class="sxs-lookup"><span data-stu-id="4926d-146">C-Suite</span></span>
    
  - <span data-ttu-id="4926d-147">IT 人员</span><span class="sxs-lookup"><span data-stu-id="4926d-147">IT staff</span></span>
    
  - <span data-ttu-id="4926d-148">研究人员</span><span class="sxs-lookup"><span data-stu-id="4926d-148">Research staff</span></span>
    
  - <span data-ttu-id="4926d-149">正式员工</span><span class="sxs-lookup"><span data-stu-id="4926d-149">Regular staff</span></span>
    
  - <span data-ttu-id="4926d-150">市场营销人员</span><span class="sxs-lookup"><span data-stu-id="4926d-150">Marketing staff</span></span>
    
  - <span data-ttu-id="4926d-151">销售人员</span><span class="sxs-lookup"><span data-stu-id="4926d-151">Sales staff</span></span>
    
5. <span data-ttu-id="4926d-152">单击“**选择**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-152">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="4926d-153">关闭浏览器中的 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="4926d-153">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="4926d-154">接下来，[连接到 Azure Active Directory PowerShell Graph 模块](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4926d-154">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="4926d-155">填写组织名称、位置和公用密码并从 PowerShell 命令提示符或集成脚本环境 (ISE) 中运行以下命令，创建用户帐户并将其添加到相应的组：</span><span class="sxs-lookup"><span data-stu-id="4926d-155">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="4926d-156">此处使用公用密码旨在自动配置开发/测试环境，简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="4926d-156">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="4926d-157">显然，对于生产订阅，这是非常不鼓励的。</span><span class="sxs-lookup"><span data-stu-id="4926d-157">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="4926d-158">请按照以下步骤验证基于组的许可是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="4926d-158">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="4926d-159">在浏览器的“**Microsoft Office 主页**”标签页中，单击“**管理**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="4926d-159">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="4926d-160">在浏览器的新“**Microsoft 365 管理中心**”标签页中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-160">From the new **Office Admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="4926d-161">在用户列表中，单击“CEO”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-161">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="4926d-162">在列出 CEO 用户帐户属性的窗格中，验证已向其分配“企业移动性 + 安全性 E5”和“Office 365 企业版 E5”许可证（位于“产品许可证”中）\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*。 </span><span class="sxs-lookup"><span data-stu-id="4926d-162">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="4926d-163">阶段 3：创建 Office 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="4926d-163">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="4926d-164">此阶段将针对 SharePoint Online 团队网站文档文件夹的不同安全级别创建保留标签。</span><span class="sxs-lookup"><span data-stu-id="4926d-164">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>


1. <span data-ttu-id="4926d-165">使用全局管理员帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="4926d-166">在浏览器的“**主页 - Microsoft 365 合规性**”选项卡中，单击“**分类 > 标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-166">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="4926d-167">单击“**保留标签 > 创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-167">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="4926d-168">在“**命名标签**”窗格上的“**命名标签**”中键入“**内部公用**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-168">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="4926d-169">在“**文件计划描述符**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-169">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="4926d-170">在“**标签设置**”窗格中，根据需要将“**保留**”设置为“**开**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-170">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="4926d-171">在“**查看设置**”窗格中，单击“**创建标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-171">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="4926d-172">对具有以下名称的其他标签重复步骤 3-7：</span><span class="sxs-lookup"><span data-stu-id="4926d-172">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="4926d-173">Private</span><span class="sxs-lookup"><span data-stu-id="4926d-173">Private</span></span>
    
  - <span data-ttu-id="4926d-174">敏感</span><span class="sxs-lookup"><span data-stu-id="4926d-174">Sensitive</span></span>
    
  - <span data-ttu-id="4926d-175">高度机密</span><span class="sxs-lookup"><span data-stu-id="4926d-175">Highly Confidential</span></span>
  
9. <span data-ttu-id="4926d-176">在“开始”>“标签”窗格中，单击“发布标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-176">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="4926d-177">在“选择要发布的标签”窗格中，单击“选择要发布的标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-177">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="4926d-178">在“选择标签”窗格中，单击“添加”并选择全部四个标签\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-178">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="4926d-179">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-179">Click **Done**.</span></span>
    
13. <span data-ttu-id="4926d-180">在“选择要发布的标签”窗格中，单击“下一步”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-180">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="4926d-181">在“**选择位置**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-181">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="4926d-182">在“**命名策略**”窗格中，在“**名称**”中键入“**示例组织**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-182">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="4926d-183">在“**查看设置**”窗格中，单击“**发布标签**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-183">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="4926d-184">阶段 4：创建 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="4926d-184">Phase 4: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="4926d-185">在此阶段中，将为示例组织创建和配置四种类型的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="4926d-185">In this phase, you create and configure the four types of SharePoint Online team sites for your example organization.</span></span>
  
### <a name="organization-wide-team-site"></a><span data-ttu-id="4926d-186">组织范围团队网站</span><span class="sxs-lookup"><span data-stu-id="4926d-186">Organization wide team site</span></span>

<span data-ttu-id="4926d-187">要创建基线公共 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4926d-187">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="4926d-188">如有需要，请使用试用订阅的全局管理员帐户的凭据登录 [Office 365 门户](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-188">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-189">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-189">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="4926d-190">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-190">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="4926d-191">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-191">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="4926d-192">在“网站名称”中，键入“组织范围”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-192">In **Site name**, type **Organization wide**.</span></span> 
    
6. <span data-ttu-id="4926d-193">在“**团队网站描述**”中，键入“**用于整个组织的 SharePoint 网站**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-193">In **Team site description**, type **SharePoint site for the entire organization**.</span></span>
    
7. <span data-ttu-id="4926d-194">在“**隐私设置**”中，选择“**公用 - 组织中的任何人均可访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-194">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-195">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-195">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="4926d-196">接下来，针对内部公共标签配置组织范围团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="4926d-196">Next, configure the documents folder of the Organization wide team site for the Internal Public label.</span></span>
  
1. <span data-ttu-id="4926d-197">在浏览器的“**组织范围 - 主页**”标签页中，单击“**文档**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-197">In the **Organization wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="4926d-198">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-198">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="4926d-199">在“**权限和管理**”下，单击“**向此库中的项应用标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="4926d-200">在“**设置 - 应用标签**”中，选择“**内部公用**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-200">In **Settings-Apply Label**, select **Internal Public**, and then click **Save**.</span></span>
    
### <a name="project-1-team-site"></a><span data-ttu-id="4926d-201">项目 1 团队网站</span><span class="sxs-lookup"><span data-stu-id="4926d-201">Project 1 team site</span></span>

<span data-ttu-id="4926d-202">要为组织内的项目创建基线专用 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4926d-202">To create a baseline private SharePoint Online team site for a project within the organization, do the following:</span></span>
  
1. <span data-ttu-id="4926d-203">如有需要，请使用试用订阅的全局管理员帐户的凭据登录 [Office 365 门户](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-203">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-204">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="4926d-205">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-205">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="4926d-206">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-206">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="4926d-207">在“**网站名称**”中，键入“**项目 1**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-207">In **Site name**, type **Project 1**.</span></span> 
    
6. <span data-ttu-id="4926d-208">在“**团队网站描述**”中，键入“**用于项目 1 的 SharePoint 网站**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-208">In **Team site description,** type **SharePoint site for Project 1**.</span></span>
    
7. <span data-ttu-id="4926d-209">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-209">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-210">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-210">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="4926d-211">接下来，针对专用标签配置项目 1 团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="4926d-211">Next, configure the documents folder of the Project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="4926d-212">在浏览器的“**项目 1 - 主页**”标签页中，单击“**文档**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-212">In the **Project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="4926d-213">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-213">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="4926d-214">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-214">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="4926d-215">在“**设置 - 应用标签**”中，选择“**专用**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-215">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="marketing-campaigns-team-site"></a><span data-ttu-id="4926d-216">市场营销活动团队网站</span><span class="sxs-lookup"><span data-stu-id="4926d-216">Marketing campaigns team site</span></span>

<span data-ttu-id="4926d-217">要为市场营销活动资源创建敏感级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4926d-217">To create a sensitive-level isolated SharePoint Online team site for marketing campaign resources, do the following:</span></span>

 
1. <span data-ttu-id="4926d-218">如有需要，请使用试用订阅的全局管理员帐户的凭据登录 [Office 365 门户](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-218">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-219">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-219">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="4926d-220">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-220">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="4926d-221">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-221">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="4926d-222">在“团队网站名称”中，键入“市场营销活动”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-222">In **Team site name**, type **Marketing campaigns**.</span></span>
    
6. <span data-ttu-id="4926d-223">在“**团队网站描述**”中，键入“**用于市场营销活动资源的 SharePoint 网站(敏感)**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-223">In **Team site description**, type **SharePoint site for marketing campaign resources (sensitive)**.</span></span>
    
7.  <span data-ttu-id="4926d-224">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-224">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-225">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-225">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="4926d-226">在浏览器上的新“**市场营销活动**”标签页上，依次单击工具栏中的设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-226">On the new **Marketing campaigns** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="4926d-227">在“**网站权限**”窗格中，单击“**高级权限设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-227">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="4926d-228">在浏览器的新“**权限**”标签页中，单击“**访问请求设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-228">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="4926d-229">在“**访问请求设置**”对话框中，取消勾选“**允许成员共享网站和单独的文件和文件夹**”和“**允许成员邀请他人到网站成员组**”复选框，在“**发送所有访问请求**”中键入 **ITAdmin1@**\<组织名称>**.onmicrosoft.com**，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-229">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="4926d-230">单击列表中的“**市场营销活动成员**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-230">Click **Marketing campaigns Members** in the list.</span></span>
    
14. <span data-ttu-id="4926d-231">在“**人员和组**”页中，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-231">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="4926d-232">在“**共享**”对话框中，键入并选中**市场营销人员**，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-232">In the **Share** dialog box, type **Marketing staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="4926d-233">对 **Researcher1** 用户帐户重复步骤 14 和 15。</span><span class="sxs-lookup"><span data-stu-id="4926d-233">Repeat steps 14 and 15 for the **Researcher1** user account.</span></span>
    
17. <span data-ttu-id="4926d-234">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="4926d-234">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="4926d-235">单击列表中的“**市场营销活动所有者**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-235">Click **Marketing campaigns Owners** in the list.</span></span>
    
19. <span data-ttu-id="4926d-236">在“**人员和组**”页中，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-236">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="4926d-237">在“共享”\*\*\*\* 对话框中，键入并选择“IT staff”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-237">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="4926d-238">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="4926d-238">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="4926d-239">关闭浏览器上的“**人员和组**”标签页，单击浏览器上的“**市场营销活动 - 主页**”标签页，然后关闭“**网站权限**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4926d-239">Close the **People and Groups** tab in your browser, click the **Marketing campaigns-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="4926d-240">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="4926d-240">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="4926d-241">市场营销活动-成员：SharePoint 组仅包含“市场营销活动”组（其中包含全局管理员用户帐户）、“市场营销人员”组（其中包含 Marketing1 和 Marketing2 用户帐户）以及 Researcher1 用户帐户\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-241">The **Marketing campaigns-Members** SharePoint group contains only the **Marketing campaigns** group (which contains the global administrator user account), the **Marketing staff** group (which contains the Marketing1 and Marketing2 user accounts), and the **Researcher1** user account.</span></span>
    
- <span data-ttu-id="4926d-242">市场营销活动-所有者：SharePoint 组仅包含“IT 人员”组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-242">The **Marketing campaigns-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="4926d-243">市场营销活动-访问者：SharePoint 组不包含任何组或用户帐户\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-243">The **Marketing campaigns-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="4926d-244">成员不能修改网站级权限（此设置只能由**市场营销活动 - 所有者**组的成员执行）。</span><span class="sxs-lookup"><span data-stu-id="4926d-244">Members cannot modify site-level permissions (this can only be done by members of the **Marketing campaigns-Owners** group).</span></span>
    
- <span data-ttu-id="4926d-245">其他用户帐户无法访问网站或其资源，但可以请求访问网站，将向 ITAdmin1 用户帐户邮箱发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4926d-245">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="4926d-246">接下来，针对敏感标签配置市场营销活动团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="4926d-246">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="4926d-247">在浏览器的“**市场营销活动 - 主页**”标签页中，单击“**文档**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-247">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="4926d-248">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-248">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="4926d-249">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-249">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="4926d-250">在“**设置 - 应用标签**”中，选择“**敏感**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-250">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="4926d-251">接下来，配置数据丢失防护 (DLP) 策略，以便在用户共享关于含敏感标签的 SharePoint Online 团队网站（包括组织外的营销活动网站）的文档时进行通知。</span><span class="sxs-lookup"><span data-stu-id="4926d-251">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="4926d-252">使用全局管理员帐户登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="4926d-252">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="4926d-253">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-253">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="4926d-254">在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-254">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="4926d-255">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-255">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="4926d-256">在“命名策略”\*\*\*\* 窗格中，在“名称”中键入 \*\*Sensitive label SharePoint Online team sites\*\*\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-256">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="4926d-257">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-257">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="4926d-258">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-258">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-259">在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-259">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="4926d-260">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-260">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="4926d-261">在“**保留标签**”窗格中，单击“**添加**”，选择“**敏感**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-261">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="4926d-262">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-262">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="4926d-263">在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-263">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="4926d-264">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-264">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="4926d-265">在“自定义策略提示和电子邮件通知”\*\*\*\* 窗格中，单击“自定义策略提示文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-265">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="4926d-266">在文本框中，键入或粘贴以下提示之一，具体取决于是否已实现 Azure 信息保护来保护高度机密文件：</span><span class="sxs-lookup"><span data-stu-id="4926d-266">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="4926d-p104">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="4926d-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="4926d-270">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4926d-270">Click **OK**.</span></span>
    
17. <span data-ttu-id="4926d-271">在“如果检测到敏感信息，希望采取什么操作?”\*\*\*\* 窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-271">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="4926d-272">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-272">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="4926d-273">在“**查看设置**”窗格中，单击“**创建**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-273">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="4926d-274">公司战略团队网站</span><span class="sxs-lookup"><span data-stu-id="4926d-274">Company strategy team site</span></span>

<span data-ttu-id="4926d-275">若要针对组织首席执行官的公司战略资源创建高度机密级别的独立 SharePoint Online 团队网站，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4926d-275">To create an isolated SharePoint Online team site at the highly confidential level for strategic company resources of the chief executives of the organization, do the following:</span></span>
  
1. <span data-ttu-id="4926d-276">如有需要，请使用试用订阅的全局管理员帐户的凭据登录 [Office 365 门户](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-276">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="4926d-277">在磁贴列表中，单击“SharePoint”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-277">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="4926d-278">在浏览器的新“SharePoint”标签页中，单击“+ 创建网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-278">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="4926d-279">在“创建网站”页中，单击“团队网站”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-279">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="4926d-280">在“团队网站名称”中，键入“公司战略”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-280">In **Team site name**, type **Company strategy**.</span></span>
    
6. <span data-ttu-id="4926d-281">在“**团队网站描述**”中，键入“**针对公司战略的 SharePoint 网站(高度机密)**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-281">In **Team site description**, type **SharePoint site for company strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="4926d-282">在“**隐私设置**”中，选择“**专用 - 仅成员可以访问此网站**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-282">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-283">在“**希望添加哪些人员?**”窗格中，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-283">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="4926d-284">在浏览器的新“**公司战略**”标签页中，依次单击工具栏的设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-284">On the new **Company strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="4926d-285">在“**网站权限**”窗格中，单击“**高级权限设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-285">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="4926d-286">在浏览器的新“权限”标签页中，单击“访问请求设置”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-286">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="4926d-287">在“**访问请求设置**”对话框中，清除“**允许成员共享网站和单独的文件和文件夹**”和“**允许成员邀请他人到网站成员组**”（这样三个复选框全被清除），然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-287">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="4926d-288">单击列表中的“**公司战略成员**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-288">Click **Company strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="4926d-289">在“**人员和组**”页中，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-289">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="4926d-290">在“**共享**”对话框中，键入并选择“**高层管理人员**”，然后单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-290">In the **Share** dialog box, type **C-Suite**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="4926d-291">单击列表中的“**公司战略所有者**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-291">Click **Company strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="4926d-292">在“**人员和组**”页中，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-292">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="4926d-293">在“共享”\*\*\*\* 对话框中，键入并选择“IT staff”\*\*\*\*，然后单击“共享”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-293">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="4926d-294">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="4926d-294">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="4926d-295">关闭浏览器上的“**人员和组**”标签页，单击浏览器上的“**公司战略 - 主页**”标签页，然后关闭“**网站权限**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4926d-295">Close the **People and Groups** tab in your browser, click the **Company strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="4926d-296">权限的配置结果如下所示：</span><span class="sxs-lookup"><span data-stu-id="4926d-296">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="4926d-297">公司战略-成员：SharePoint 组仅包含“高层管理人员”组（其中仅包含 CEO、CFO和 CIO 用户帐户）和“公司战略”组（其中仅包含全局管理员用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="4926d-297">The **Company strategy-Members** SharePoint group contains only the **C-Suite** group (which contains only the CEO, CFO, and CIO user accounts) and the **Company strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="4926d-298">**公司战略 - 所有者**：SharePoint 组仅包含“**IT 人员**”组（其中仅包含 ITAdmin1 和 ITAdmin2 用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="4926d-298">The **Company strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="4926d-299">**公司战略 - 访问者**：SharePoint 组不包含任何组或用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4926d-299">The **Company strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="4926d-300">成员不能修改网站级别权限（仅“公司战略-所有者”组的成员才可进行修改）。</span><span class="sxs-lookup"><span data-stu-id="4926d-300">Members cannot modify site-level permissions (this can only be done by members of the **Company strategy-Owners** group).</span></span>
    
- <span data-ttu-id="4926d-p105">其他用户帐户无法访问网站或其资源，也无法请求访问网站。 网站的其他权限必须由全局管理员或“公司战略-所有者”组的成员履行。</span><span class="sxs-lookup"><span data-stu-id="4926d-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Company strategy-Owners** group.</span></span>
    
<span data-ttu-id="4926d-303">接下来，针对高度机密标签配置公司战略团队网站的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="4926d-303">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="4926d-304">在浏览器的“**公司战略 - 主页**”标签页中，单击“**文档**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-304">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="4926d-305">单击设置图标，然后单击“**库设置**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-305">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="4926d-306">在“权限和管理”下，单击“向此库中的项应用标签”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-306">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="4926d-307">在“**设置 - 应用标签**”中，选择“**高度机密**”，然后单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-307">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="4926d-308">接下来，配置 DLP 策略，当用户在具有“高度机密”标签的 SharePoint Online 团队网站（包括组织外的公司战略网站）上共享文档时，该策略会阻止用户。</span><span class="sxs-lookup"><span data-stu-id="4926d-308">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="4926d-309">使用全局管理员登录 [Microsoft 365 合规性门户](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="4926d-309">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="4926d-310">在浏览器的新“**Microsoft 365 合规**”标签页中，单击“**策略 > 数据丢失防护**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-310">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="4926d-311">在“**主页 > 数据丢失防护**”窗格中，单击“**创建策略**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-311">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="4926d-312">在“从模板开始或创建自定义策略”\*\*\*\* 窗格中，单击“自定义”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-312">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="4926d-313">在“命名策略”\*\*\*\* 窗格中，在“名称”中键入 \*\*Highly Confidential label SharePoint Online team sites\*\*\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-313">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="4926d-314">在“选择位置”窗格中，单击“允许选择特定位置”，然后单击“下一步”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-314">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="4926d-315">在位置列表中，禁用“**Exchange 电子邮件**”、“**OneDrive 帐户**”和“**Teams 聊天和频道消息**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-315">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="4926d-316">在“**自定义要保护的内容类型**”窗格中，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-316">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="4926d-317">在“**选择要保护的内容类型**”窗格中，单击下拉框中的“**添加**”，然后单击“**保留标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-317">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="4926d-318">在“**保留标签**”窗格中，单击“**添加**”，选择“**高度机密**”标签，然后依次单击“**添加**”和“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-318">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="4926d-319">在“选择要保护的内容类型”窗格中，单击“保存”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-319">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="4926d-320">在“**自定义要保护的敏感信息类型**”窗格中，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-320">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="4926d-321">在“如果检测到敏感信息，希望采取什么操作?”窗格中，单击“自定义提示和电子邮件”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-321">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="4926d-322">在“自定义策略提示和电子邮件通知”\*\*\*\* 窗格中，单击“自定义策略提示文本”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-322">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="4926d-323">在文本框中，键入或粘贴以下提示之一，具体取决于是否已实现 Azure 信息保护来保护高度机密文件：</span><span class="sxs-lookup"><span data-stu-id="4926d-323">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="4926d-p106">要与组织外部的用户共享，请下载并打开文件。 依次单击“文件”、“保护文档”、“使用密码加密”，然后指定强密码。 通过单独的电子邮件或其他通信方式发送密码。</span><span class="sxs-lookup"><span data-stu-id="4926d-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="4926d-327">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4926d-327">Click **OK**.</span></span>
    
17. <span data-ttu-id="4926d-328">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-328">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="4926d-329">在“是否希望立即启用策略或先进行测试?”\*\*\*\* 窗格中，单击“是，立即启用”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-329">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="4926d-330">在“查看设置”\*\*\*\* 窗格中，单击“创建”\*\*\*\*，然后单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-330">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
   
    
<span data-ttu-id="4926d-331">接下来，按照[使用 Microsoft 365 管理中心激活 Azure RMS](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="4926d-331">Next, follow the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="4926d-332">接下来，通过执行以下步骤，使用新策略以及保护和权限的高层管理人员组的子标签作用域来配置 Azure 信息保护：</span><span class="sxs-lookup"><span data-stu-id="4926d-332">Next, configure Azure Information Protection with a new policy and sub-label scoped for the C-Suite group for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="4926d-333">如果需要，使用全局管理员帐户登录 [Microsoft 365 管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="4926d-333">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="4926d-334">在浏览器的单独标签页中，转到 Azure 门户 ([https://portal.azure.com](https://portal.azure.com))。</span><span class="sxs-lookup"><span data-stu-id="4926d-334">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="4926d-335">如果是首次配置 Azure 信息保护，请参阅这些[说明](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time)。</span><span class="sxs-lookup"><span data-stu-id="4926d-335">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>
    
4. <span data-ttu-id="4926d-336">在列表窗格中，单击“**更多服务**”，键入“**信息**”，然后单击“**Azure 信息保护**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-336">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="4926d-337">单击“**标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-337">Click **Labels**.</span></span>
    
6. <span data-ttu-id="4926d-338">右键单击“**高度机密**”标签，然后单击“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-338">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="4926d-339">在“**名称**”和“**说明**”中键入“**高层管理人员**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-339">Type **C-Suite members** in **Name** and **Description**.</span></span>
    
8. <span data-ttu-id="4926d-340">在“**为包含此标签的文档和电子邮件设置权限**”中，单击“**保护**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-340">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="4926d-341">在“保护”部分中，单击“Azure (云密钥)”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-341">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="4926d-342">在“保护”边栏选项卡中，在“保护设置”下，单击“+ 添加权限”\*\*\*\*\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-342">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="4926d-343">在“**添加权限**”边栏选项卡的“**指定用户和组**”下，单击“**+ 浏览目录**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-343">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="4926d-344">在“**AAD 用户和组**”窗格中，选择“**高层管理人员**”，然后单击“**选择**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-344">On the **AAD Users and Groups** pane, select **C-Suite**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="4926d-345">在“**从预设或设置自定义中选择权限**”下，单击“**自定义**”，然后依次单击“**查看权限**”、“**编辑内容**”、“**保存**”、“**答复**”和“**全部答复**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4926d-345">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="4926d-346">单击“**确定**”两次。</span><span class="sxs-lookup"><span data-stu-id="4926d-346">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="4926d-347">在“**子标签**”边栏选项卡上，单击“**保存**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-347">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="4926d-348">在“Azure 信息保护”\*\*\*\* 边栏选项卡上，单击“策略”>“添加新策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-348">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="4926d-349">在“策略名称”\*\*\*\* 中键入 **CompanyStrategy**，并在“描述”\*\*\*\* 中键入**公司战略团队网站中的文档**。</span><span class="sxs-lookup"><span data-stu-id="4926d-349">Type **CompanyStrategy** in **Policy name** and **Documents in the Company strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="4926d-350">单击“选择获取此策略的用户或组”>“用户/组”\*\*\*\*，然后选择“高层管理人员”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-350">Click **Select which users or groups get this policy > User/Groups**, and then select **C-Suite**.</span></span>
    
19. <span data-ttu-id="4926d-351">单击“**选择”>“确定**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-351">Click **Select > OK**.</span></span>

20. <span data-ttu-id="4926d-p107">单击“**添加或删除标签**”。在“**策略: 添加或删除标签**”窗格中，单击“**高层管理人员**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4926d-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **C-Suite**, and then click **OK**.</span></span>   

21. <span data-ttu-id="4926d-354">单击“保存”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4926d-354">Click **Save**, and then click **OK**.</span></span>
    
<span data-ttu-id="4926d-355">若要使用 Azure 信息保护和此新标签保护文档，必须在测试计算机上[安装 Azure 信息保护客户端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)，从管理中心安装 Office，然后使用试用订阅的“高层管理人员\*\*\*\*”组中的帐户从 Microsoft Word 登录。</span><span class="sxs-lookup"><span data-stu-id="4926d-355">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **C-Suite** group of your trial subscription.</span></span>
  
<span data-ttu-id="4926d-356">现在，可以在这四个网站中创建文档，并使用试用订阅中的各种用户帐户进行访问测试。</span><span class="sxs-lookup"><span data-stu-id="4926d-356">You are now ready to create documents in these four sites and test access to them with various user accounts in your trial subscription.</span></span>
  
<span data-ttu-id="4926d-357">下面是针对全部四个 SharePoint Online 团队网站的整体配置。</span><span class="sxs-lookup"><span data-stu-id="4926d-357">Here is the overall configuration for all four SharePoint Online team sites.</span></span>
  
![安全 SharePoint Online 开发/测试环境中的所有四个团队网站。](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a><span data-ttu-id="4926d-359">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4926d-359">Next step</span></span>

<span data-ttu-id="4926d-360">如果已准备好进行安全 SharePoint Online 网站的生产部署，请参阅[保护 SharePoint Online 网站和文件](secure-sharepoint-online-sites-and-files.md)，了解详细信息，获取分步部署文章的链接。</span><span class="sxs-lookup"><span data-stu-id="4926d-360">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4926d-361">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4926d-361">See Also</span></span>

[<span data-ttu-id="4926d-362">保护 SharePoint Online 网站和文件</span><span class="sxs-lookup"><span data-stu-id="4926d-362">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="4926d-363">云应用和混合解决方案</span><span class="sxs-lookup"><span data-stu-id="4926d-363">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="4926d-364">Microsoft 针对政治宣传活动、非营利组织和其他敏捷性组织的安全指南</span><span class="sxs-lookup"><span data-stu-id="4926d-364">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




