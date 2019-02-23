---
title: 在 Office 365 中为电子数据展示调查设置合规性边界
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合规性边界在 Office 365 组织中创建用于控制电子数据展示管理器可搜索的用户内容位置的逻辑边界。合规性边界使用搜索权限筛选 (也称为合规性安全筛选器) 控制特定用户可以搜索哪些邮箱、SharePoint 网站和 OneDrive 帐户。
ms.openlocfilehash: ce7c00130312abab4d4d91fcf04590c109741f26
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218162"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="370b2-104">在 Office 365 中为电子数据展示调查设置合规性边界</span><span class="sxs-lookup"><span data-stu-id="370b2-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="370b2-p102">合规性边界在 Office 365 组织中创建逻辑边界, 以控制电子数据展示管理者可以搜索的用户内容位置 (如邮箱、SharePoint 网站和 OneDrive 帐户)。此外, 合规性边界控制谁可以访问电子数据展示用例, 以管理组织中的法律、人力资源或其他调查。对于必须遵守地理位置 boarders 和管理法规以及政府 (通常分为不同机构) 的多个公司来说, 对合规性边界的需求通常是必需的。在 Office 365 中, 合规性边界可帮助您在执行内容搜索和使用电子数据展示案例管理调查时满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="370b2-p102">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search. Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization. The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies. In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="370b2-109">我们将使用下图中的示例来说明合规性边界的工作原理。</span><span class="sxs-lookup"><span data-stu-id="370b2-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合规性边界包含搜索权限筛选器, 这些筛选器控制对控制对 eDisocovery 事例的访问的机构和管理员角色组的访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="370b2-p103">在此示例中, Contoso 有限公司是由两个子公司、第四个咖啡和 Coho Winery 组成的 Office 365 组织。业务要求电子数据展示 mangers 和调查人员只能在其代理中搜索 Exchange 邮箱、OneDrive 帐户和 SharePoint 网站。此外, 电子数据展示管理员和调查人员只能在其代理中查看电子数据展示事例, 并且只能访问他们所属的案例。下面介绍了合规性边界如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="370b2-p103">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery. The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency. Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of. Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="370b2-p104">内容搜索中的搜索权限筛选功能控制电子数据展示管理者和调查人员可以搜索的内容位置。这意味着第四个咖啡店中的电子数据展示管理者和调查人员只能在第四个咖啡子公司中搜索内容位置。此限制适用于 Coho Winery 子公司。</span><span class="sxs-lookup"><span data-stu-id="370b2-p104">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search. This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary. The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="370b2-p105">角色组控制谁可以查看 Office 365 安全&amp;合规中心中的电子数据展示事例。这意味着电子数据展示管理者和调查人员只能查看其代理中的电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="370b2-p105">Role groups control who can see the eDiscovery cases in the Office 365 Security &amp; Compliance Center. This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="370b2-p106">角色组还控制谁可以向电子数据展示事例分配成员。这意味着电子数据展示管理者和调查人员只能将成员分配给他们自己所属的案例。</span><span class="sxs-lookup"><span data-stu-id="370b2-p106">Role groups also control who can assign members to an eDiscovery case. This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="370b2-122">下面是设置合规性边界的过程:</span><span class="sxs-lookup"><span data-stu-id="370b2-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="370b2-123">步骤 1: 标识用于定义您的机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="370b2-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="370b2-124">步骤 2: 为 Microsoft 支持文件提供将 user 属性同步到 OneDrive 帐户的请求</span><span class="sxs-lookup"><span data-stu-id="370b2-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="370b2-125">步骤 3: 为每个代理创建角色组</span><span class="sxs-lookup"><span data-stu-id="370b2-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="370b2-126">步骤 4: 创建搜索权限筛选器以强制实施合规性边界</span><span class="sxs-lookup"><span data-stu-id="370b2-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="370b2-127">步骤 5: 为机构内调查创建电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="370b2-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="370b2-128">步骤 1: 标识用于定义您的机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="370b2-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="370b2-p107">第一步是选择要使用的 Azure Active Directory 属性, 该属性将定义您的机构。此属性将用于创建搜索权限筛选器, 该筛选器限制电子数据展示管理器仅搜索为该属性分配了特定值的用户的内容位置。例如, 假设 Contoso 决定使用 "**部门**" 属性。对于第四个咖啡店中的用户`FourthCoffee` , 此属性的值为, Coho Winery 子公司中的用户的值为。 `CohoWinery`在步骤4中, 将使用此`attribute:value`对 (例如, "*部门: FourthCoffee* ") 限制电子数据展示管理器可以搜索的用户内容位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-p107">The first step is to choose an Azure Active Directory attribute to use that will define your agencies. This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute. For example, let's say Contoso decides to use the **Department** attribute. The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`. In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="370b2-134">以下是可用于合规性边界的 Azure Active Directory 用户属性的列表:</span><span class="sxs-lookup"><span data-stu-id="370b2-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="370b2-135">Company</span><span class="sxs-lookup"><span data-stu-id="370b2-135">Company</span></span>
    
- <span data-ttu-id="370b2-136">CustomAttribute1-CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="370b2-136">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="370b2-137">部门</span><span class="sxs-lookup"><span data-stu-id="370b2-137">Department</span></span>
    
- <span data-ttu-id="370b2-138">办公室</span><span class="sxs-lookup"><span data-stu-id="370b2-138">Office</span></span>
    
<span data-ttu-id="370b2-139">虽然更多的用户属性 (尤其是对于 Exchange 邮箱), 但上面列出的属性是 OneDrive 当前支持的那些属性。</span><span class="sxs-lookup"><span data-stu-id="370b2-139">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="370b2-140">步骤 2: 为 Microsoft 支持文件提供将 user 属性同步到 OneDrive 帐户的请求</span><span class="sxs-lookup"><span data-stu-id="370b2-140">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="370b2-p108">下一步是向 Microsoft 支持文件发出请求, 以将您在步骤1中选择的 Azure Active Directory 属性同步到组织中的所有 OneDrive 帐户。在此同步发生之后, 您在步骤1中选择的属性 (及其值) 将映射到名为`ComplianceAttribute`的 SharePoint 中的隐藏托管属性。您将使用此属性在步骤4中创建 OneDrive 的搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="370b2-p108">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization. After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`. You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="370b2-144">向 Microsoft 支持部门提交请求时, 请包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="370b2-144">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="370b2-145">Office 365 组织的默认域名</span><span class="sxs-lookup"><span data-stu-id="370b2-145">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="370b2-146">Azure Active Directory 属性的名称 (从步骤 1)</span><span class="sxs-lookup"><span data-stu-id="370b2-146">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="370b2-p109">支持请求的用途的以下标题或说明: "对合规性安全筛选器启用 OneDrive for business 同步和 Azure Active Directory"。这将有助于将请求路由到将实现请求的 Office 365 电子数据展示工程团队。</span><span class="sxs-lookup"><span data-stu-id="370b2-p109">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="370b2-p110">在进行工程更改并将属性同步到 OneDrive 后, Microsoft 支持将向您发送所做更改的内部版本号以及估计的部署日期。请注意, 在提交支持请求后, 部署过程通常需要4-6 周。</span><span class="sxs-lookup"><span data-stu-id="370b2-p110">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date. Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="370b2-p111">**重要说明:** 您可以在部署更改之前完成步骤3到步骤5。但在部署更改之前, 运行内容搜索不会返回在搜索权限筛选器中指定的 OneDrive 网站中的文档。</span><span class="sxs-lookup"><span data-stu-id="370b2-p111">**Important:** You can complete Step 3 through Step 5 before the change is deployed. But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="370b2-153">步骤 3: 为每个代理创建角色组</span><span class="sxs-lookup"><span data-stu-id="370b2-153">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="370b2-p112">下一步是在将与您的机构相一致的 Office &amp; 365 安全合规中心中创建角色组。我们建议您创建新的角色组, 方法是复制内置的电子数据展示管理器组, 添加适当的成员, 并删除可能不适用于您的需求的角色。有关电子数据展示相关角色的详细信息, 请参阅[在 Office 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="370b2-p112">The next step is to create the role groups in the Office 365 Security &amp; Compliance Center that will align with your agencies. We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs. For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="370b2-157">若要创建角色组, 请转到\*\*\*\* 安全&amp;合规中心中的 "权限" 页, 并为每个代理中将使用合规性边界和电子数据展示事例来管理调查的每个团队创建一个角色组。</span><span class="sxs-lookup"><span data-stu-id="370b2-157">To create the role groups, go to the **Permissions** page in the Security &amp; Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="370b2-158">使用 Contoso 合规性边界方案, 需要创建四个角色组, 并向每个角色组添加适当的成员。</span><span class="sxs-lookup"><span data-stu-id="370b2-158">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="370b2-159">第四个咖啡电子数据展示管理器</span><span class="sxs-lookup"><span data-stu-id="370b2-159">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="370b2-160">第四个咖啡调查人员</span><span class="sxs-lookup"><span data-stu-id="370b2-160">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="370b2-161">Coho Winery 电子数据展示管理器</span><span class="sxs-lookup"><span data-stu-id="370b2-161">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="370b2-162">Coho Winery 调查人员</span><span class="sxs-lookup"><span data-stu-id="370b2-162">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="370b2-163">步骤 4: 创建搜索权限筛选器以强制实施合规性边界</span><span class="sxs-lookup"><span data-stu-id="370b2-163">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>
<span data-ttu-id="370b2-164"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="370b2-164"></span></span>

<span data-ttu-id="370b2-p113">为每个代理创建角色组后, 下一步是创建将每个角色组关联到其特定代理并定义合规性边界本身的搜索权限筛选器。您需要为每个代理创建一个搜索权限筛选器。有关创建安全权限筛选器的详细信息, 请参阅[Configure 权限筛选以进行内容搜索](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="370b2-p113">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself. You need to create one search permissions filter for each agency. For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="370b2-168">下面是用于创建用于合规性边界的搜索权限筛选器的语法。</span><span class="sxs-lookup"><span data-stu-id="370b2-168">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="370b2-169">以下是对命令中的每个参数的说明:</span><span class="sxs-lookup"><span data-stu-id="370b2-169">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="370b2-p114">`FilterName`-指定筛选器的名称。使用描述或标识将在其中使用筛选器的机构的名称。</span><span class="sxs-lookup"><span data-stu-id="370b2-p114">`FilterName` - Specifies the name of the filter. Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="370b2-p115">`Users`-指定将此筛选器应用于其执行的内容搜索操作的用户或组。对于合规性边界, 此参数指定要在其上创建筛选器的代理中创建的角色组 (您在步骤3中创建的角色组)。注意这是一个多值参数, 因此您可以包含一个或多个角色组, 以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="370b2-p115">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform. For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for. Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="370b2-p116">`Filters`-指定筛选器的搜索条件。对于合规性边界, 您将定义以下筛选器。每个应用于一个用户内容位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-p116">`Filters` - Specifies the search criteria for the filter. For the compliance boundaries, you will define the following filters. Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="370b2-p117">`Mailbox`-指定`Users`参数中定义的角色组可以搜索的邮箱。对于合规性边界, *ComplianceAttribute*是您在步骤1和*AttributeValue*中标识的与指定机构相同的属性。此筛选器允许角色组的成员仅搜索特定代理中的邮箱;例如, `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="370b2-p117">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search. For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="370b2-p118">`Site`-指定`Users`参数中定义的角色组可以搜索的 OneDrive 帐户。对于 OneDrive 筛选器, 请使用实际字符串`ComplianceAttribute`;这将映射到您在步骤1中标识的相同属性, 并将其同步到 OneDrive 帐户, 这是您在步骤2中提交的支持请求的结果; *AttributeValue*指定代理。此筛选器允许角色组的成员仅搜索特定代理中的 OneDrive 帐户;例如, `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="370b2-p118">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search. For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="370b2-p119">`Site_Path`-指定`Users`参数中定义的角色组可以搜索的 SharePoint 网站。*SharePointURL*指定角色组成员可以搜索的代理中的站点;例如,`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="370b2-p119">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search. The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="370b2-p120">`Action`-指定应用筛选器的合规性搜索操作的类型。例如, 仅`-Action Search`当在`Users`参数中定义的角色组的成员运行内容搜索时, 才会应用筛选器。在这种情况下, 导出搜索结果时不会应用筛选器。对于合规性边界, `-Action All`请使用, 以便将筛选器应用于所有搜索操作。</span><span class="sxs-lookup"><span data-stu-id="370b2-p120">`Action` - Specifies the type of Compliance Search action that the filter is applied to. For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search. In this case, the filter wouldn't be applied when exporting search results. For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="370b2-190">有关内容搜索操作的列表, 请参阅[Configure 权限筛选 for content search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的 "new-compliancesecurityfilter" 一节。</span><span class="sxs-lookup"><span data-stu-id="370b2-190">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="370b2-191">以下是两个搜索权限筛选器的示例, 将创建这些筛选器以支持 Contoso 合规性边界方案。</span><span class="sxs-lookup"><span data-stu-id="370b2-191">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="370b2-192">**第四个咖啡**</span><span class="sxs-lookup"><span data-stu-id="370b2-192">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="370b2-193">**Coho Winery**</span><span class="sxs-lookup"><span data-stu-id="370b2-193">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="370b2-194">步骤 5: 为机构内调查创建电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="370b2-194">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="370b2-p121">最后一步是在安全&amp;合规中心中创建新的电子数据展示事例, 然后添加在步骤3中创建的角色组作为事例的成员。这将导致使用合规性边界的两个重要特征:</span><span class="sxs-lookup"><span data-stu-id="370b2-p121">The final step is to create a new eDiscovery case in the Security &amp; Compliance Center and then add the role group—that you created in Step 3—as a member of the case. This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="370b2-p122">只有添加到案例中的角色组的成员才能查看和访问安全&amp;合规性中心中的案例。例如, 如果第四个 "咖啡调查员" 角色组是事例的唯一成员, 则第四个 "电子数据展示管理者" 角色组的成员 (或任何其他角色组的成员) 将无法查看或访问该案例。</span><span class="sxs-lookup"><span data-stu-id="370b2-p122">Only members of the role group added to the case will be able to see and access the case in the Security &amp; Compliance Center. For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="370b2-199">当分配给某个案例的角色组成员运行与该事例相关联的搜索时, 他们将只能搜索其代理 (由您在步骤4中创建的搜索权限筛选器定义) 中的内容位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-199">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="370b2-200">若要创建新事例并分配成员, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="370b2-200">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="370b2-201">转到安全&amp;合规性中心中的**电子数据展示**页面, 并创建一个新事例。</span><span class="sxs-lookup"><span data-stu-id="370b2-201">Go to the **eDiscovery** page in the Security &amp; Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="370b2-202">在电子数据展示事例的列表中, 单击刚刚创建的事例的名称。</span><span class="sxs-lookup"><span data-stu-id="370b2-202">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="370b2-203">在 "**管理此案例**" 弹出页面的 "管理**角色组**" ![下,](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)单击 "添加图标" "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="370b2-203">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![将角色组添加为电子数据展示事例的成员](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="370b2-205">在角色组列表中, 选择您在步骤3中创建的角色组之一, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="370b2-205">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="370b2-206">单击 "**管理此案例**" 弹出控件上的 "**保存**" 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="370b2-206">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="370b2-207">合规性边界限制</span><span class="sxs-lookup"><span data-stu-id="370b2-207">Compliance boundary limitations</span></span>

<span data-ttu-id="370b2-208">在管理使用合规性边界的电子数据展示案例和调查时, 请牢记以下限制。</span><span class="sxs-lookup"><span data-stu-id="370b2-208">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="370b2-p123">在创建和运行内容搜索时, 您可以选择代理外部的内容位置。但是, 由于搜索权限筛选器, 搜索结果中不会包含这些位置的内容。</span><span class="sxs-lookup"><span data-stu-id="370b2-p123">When creating and running a Content Search, you can select content locations that are outside of your agency. However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="370b2-p124">合规性边界不适用于电子数据展示事例中的保留。这意味着一个机构中的电子数据展示管理器可以将用户置于处于保留状态的不同代理人中。但是, 如果电子数据展示管理器搜索置于保留状态的用户的内容位置, 则将强制实施合规性边界。这意味着, 电子数据展示管理器将无法搜索用户的内容位置, 即使他们能够将用户置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="370b2-p124">Compliance boundaries don't apply to holds in eDiscovery cases. That means an eDiscovery manager in one agency can place a user in a different agency on hold. However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold. That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="370b2-215">此外, 保留统计信息将仅适用于代理中的内容位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-215">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="370b2-216">搜索权限筛选器不适用于 Exchange 公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="370b2-216">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="370b2-217">在多地理位置环境中搜索和导出内容</span><span class="sxs-lookup"><span data-stu-id="370b2-217">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="370b2-218">搜索权限筛选器还使您可以控制在何处路由内容以供导出, 以及在[sharepoint 多地理位置环境](https://go.microsoft.com/fwlink/?linkid=860840)中搜索 sharepoint 网站和 OneDrive 帐户时可以搜索的数据中心:</span><span class="sxs-lookup"><span data-stu-id="370b2-218">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching SharePoint sites and OneDrive accounts in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840):</span></span>
  
- <span data-ttu-id="370b2-p125">从特定的数据中心导出搜索结果。这意味着您可以指定将从中导出搜索结果的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-p125">Export search results from a specific data center. This means that you can specify the data center location that search results will be exported from.</span></span>
    
- <span data-ttu-id="370b2-p126">将 SharePoint 网站和 OneDrive 帐户的路由搜索到附属数据中心。这意味着您可以指定将在其中运行搜索的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="370b2-p126">Route searches of SharePoint sites and OneDrive accounts to a satellite data center. This means you can specify the data center location where searches will be run.</span></span>
    
<span data-ttu-id="370b2-223">将**Region**参数用于**new-compliancesecurityfilter**或**new-compliancesecurityfilter** cmdlet, 以创建或更改导出将路由到的数据中心。</span><span class="sxs-lookup"><span data-stu-id="370b2-223">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
|<span data-ttu-id="370b2-224">**参数值**</span><span class="sxs-lookup"><span data-stu-id="370b2-224">**Parameter value**</span></span>|<span data-ttu-id="370b2-225">**数据中心位置**</span><span class="sxs-lookup"><span data-stu-id="370b2-225">**Data center location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="370b2-226">NAM</span><span class="sxs-lookup"><span data-stu-id="370b2-226">NAM</span></span>  <br/> |<span data-ttu-id="370b2-227">北美 (实际数据中心在美国)</span><span class="sxs-lookup"><span data-stu-id="370b2-227">North American (actual data centers are in the US)</span></span>  <br/> |
|<span data-ttu-id="370b2-228">EUR</span><span class="sxs-lookup"><span data-stu-id="370b2-228">EUR</span></span>  <br/> |<span data-ttu-id="370b2-229">地区</span><span class="sxs-lookup"><span data-stu-id="370b2-229">Europe</span></span>  <br/> |
|<span data-ttu-id="370b2-230">APC</span><span class="sxs-lookup"><span data-stu-id="370b2-230">APC</span></span>  <br/> |<span data-ttu-id="370b2-231">亚太地区</span><span class="sxs-lookup"><span data-stu-id="370b2-231">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="370b2-232">CAN</span><span class="sxs-lookup"><span data-stu-id="370b2-232">CAN</span></span> <br/> |<span data-ttu-id="370b2-233">加拿大</span><span class="sxs-lookup"><span data-stu-id="370b2-233">Canada</span></span>
   
<span data-ttu-id="370b2-p127">同样, 您可以对**区域**参数值使用以下值, 以控制在搜索 SharePoint 和 OneDrive 位置时, 将在哪些数据中心运行内容搜索。请注意, 下表也显示了将通过哪些数据中心导出进行路由。</span><span class="sxs-lookup"><span data-stu-id="370b2-p127">Similarly, you can use the following values for the **Region** parameter values to control which data center that Content Searches will run in when searching SharePoint and OneDrive locations. Note that the following table also shows which data center exports will be routed through.</span></span> 
  
|<span data-ttu-id="370b2-236">**参数值**</span><span class="sxs-lookup"><span data-stu-id="370b2-236">**Parameter value**</span></span>|<span data-ttu-id="370b2-237">**用于导出的数据中心路由位置**</span><span class="sxs-lookup"><span data-stu-id="370b2-237">**Data center routing locations for export**</span></span>|
|:-----|:-----|
|<span data-ttu-id="370b2-238">NAM</span><span class="sxs-lookup"><span data-stu-id="370b2-238">NAM</span></span>  <br/> |<span data-ttu-id="370b2-239">美国</span><span class="sxs-lookup"><span data-stu-id="370b2-239">US</span></span>  <br/> |
|<span data-ttu-id="370b2-240">EUR</span><span class="sxs-lookup"><span data-stu-id="370b2-240">EUR</span></span>  <br/> |<span data-ttu-id="370b2-241">地区</span><span class="sxs-lookup"><span data-stu-id="370b2-241">Europe</span></span>  <br/> |
|<span data-ttu-id="370b2-242">APC</span><span class="sxs-lookup"><span data-stu-id="370b2-242">APC</span></span>  <br/> |<span data-ttu-id="370b2-243">亚太地区</span><span class="sxs-lookup"><span data-stu-id="370b2-243">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="370b2-244">CAN</span><span class="sxs-lookup"><span data-stu-id="370b2-244">CAN</span></span>  <br/> |<span data-ttu-id="370b2-245">美国</span><span class="sxs-lookup"><span data-stu-id="370b2-245">US</span></span>  <br/> |
|<span data-ttu-id="370b2-246">AUS</span><span class="sxs-lookup"><span data-stu-id="370b2-246">AUS</span></span>  <br/> |<span data-ttu-id="370b2-247">亚太地区</span><span class="sxs-lookup"><span data-stu-id="370b2-247">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="370b2-248">KOR</span><span class="sxs-lookup"><span data-stu-id="370b2-248">KOR</span></span>  <br/> |<span data-ttu-id="370b2-249">组织的默认数据中心</span><span class="sxs-lookup"><span data-stu-id="370b2-249">The organization's default data center</span></span>  <br/> |
|<span data-ttu-id="370b2-250">GBR</span><span class="sxs-lookup"><span data-stu-id="370b2-250">GBR</span></span>  <br/> |<span data-ttu-id="370b2-251">地区</span><span class="sxs-lookup"><span data-stu-id="370b2-251">Europe</span></span>  <br/> |
|<span data-ttu-id="370b2-252">JPN</span><span class="sxs-lookup"><span data-stu-id="370b2-252">JPN</span></span>  <br/> |<span data-ttu-id="370b2-253">亚太地区</span><span class="sxs-lookup"><span data-stu-id="370b2-253">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="370b2-254">IND</span><span class="sxs-lookup"><span data-stu-id="370b2-254">IND</span></span>  <br/> |<span data-ttu-id="370b2-255">亚太地区</span><span class="sxs-lookup"><span data-stu-id="370b2-255">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="370b2-256">LAM</span><span class="sxs-lookup"><span data-stu-id="370b2-256">LAM</span></span>  <br/> |<span data-ttu-id="370b2-257">美国</span><span class="sxs-lookup"><span data-stu-id="370b2-257">US</span></span>  <br/> |
   
 <span data-ttu-id="370b2-258">**注意:** 如果没有为搜索权限筛选器指定 Region 参数, 将搜索组织的默认 SharePoint 区域, 然后将搜索结果导出到最接近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="370b2-258">**Note:** If you don't specify the Region parameter for a search permissions filter, the organizations default SharePoint region will be searched, then search results are exported to the closest data center.</span></span> 
  
<span data-ttu-id="370b2-p128">下面的示例展示了如何在为合规性边界创建搜索权限筛选器时使用 **-Region**参数。这假定第四个咖啡子公司位于北美, 并且 Coho Winery 位于欧洲。</span><span class="sxs-lookup"><span data-stu-id="370b2-p128">Here are examples of using the **-Region** parameter when creating search permission filters for compliance boundaries. This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="370b2-261">在多地理位置环境中搜索和导出内容时, 请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="370b2-261">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="370b2-p129">**Region**参数并不控制 Exchange 邮箱的搜索;搜索邮箱时将搜索所有数据中心。若要限制可以搜索的 Exchange 邮箱的作用域, 请在创建或更改搜索权限筛选器时使用**Filters**参数。</span><span class="sxs-lookup"><span data-stu-id="370b2-p129">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes. To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="370b2-264">如果电子数据展示管理器需要在多个 SharePoint 区域中进行搜索, 则需要为该电子数据展示管理器创建一个不同的用户帐户, 该用户帐户可用于搜索权限筛选器中, 以指定备用区域SharePoint 网站或 OneDrive 帐户位于。</span><span class="sxs-lookup"><span data-stu-id="370b2-264">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="370b2-p130">在 SharePoint 和 OneDrive 中搜索内容时,**区域**参数会将搜索定向到电子数据展示管理器将在其中执行电子数据展示调查的主或卫星位置。如果电子数据展示管理器在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站, 则不会返回任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="370b2-p130">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations. If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="370b2-p131">导出搜索结果时, 来自所有内容位置 (包括 Exchange、Skype for business、SharePoint、OneDrive 和其他可使用内容搜索工具搜索的 Office 365 服务) 的内容将被上载到 Azure 存储位置由**Region**参数指定的数据中心。这可帮助组织在合规性范围内不允许跨受控制的边框导出内容。如果未在搜索权限筛选器中指定任何区域, 则会将内容上传到组织的默认区域。</span><span class="sxs-lookup"><span data-stu-id="370b2-p131">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter. This helps organizations stay within compliance by not allowing content to be exported across controlled borders. If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="370b2-270">您可以通过运行以下命令来编辑现有搜索权限筛选器, 以添加或更改区域:</span><span class="sxs-lookup"><span data-stu-id="370b2-270">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="370b2-271">常见问题</span><span class="sxs-lookup"><span data-stu-id="370b2-271">Frequently asked questions</span></span>

 <span data-ttu-id="370b2-272">**谁可以创建和管理搜索权限筛选器 (使用 new-compliancesecurityfilter 和 new-compliancesecurityfilter cmdlet)？**</span><span class="sxs-lookup"><span data-stu-id="370b2-272">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="370b2-273">若要创建、查看和修改搜索权限筛选器, 您必须是安全&amp;合规性中心中 "组织管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="370b2-273">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security &amp; Compliance Center.</span></span>
  
 <span data-ttu-id="370b2-274">**如果将电子数据展示管理器分配给跨多个代理的多个角色组, 如何在一个或多个代理中搜索内容？**</span><span class="sxs-lookup"><span data-stu-id="370b2-274">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="370b2-p132">电子数据展示管理器可以向其搜索查询中添加参数, 以将搜索限制到特定的代理。例如, 如果组织已将**CustomAttribute10**属性指定为区分机构, 则可以在搜索查询中追加以下内容, 以在特定机构中搜索邮箱和 OneDrive 帐户: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="370b2-p132">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency. For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="370b2-277">**如果更改了用作搜索权限筛选器中的符合性属性的属性的值, 会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="370b2-277">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="370b2-p133">如果更改了筛选器中使用的属性的值, 则搜索权限筛选器最长需要3天才能强制实施符合性边界。例如, 在 Contoso 方案中, 假设第四个咖啡店中的用户转移到 Coho Winery 机构。因此, user 对象上的**部门**属性值从*FourthCoffee*更改为*CohoWinery* 。在这种情况下, 第四个咖啡电子数据展示和投资者将在属性更改后的3天内为该用户获取搜索结果。同样, 在 Coho Winery 电子数据展示管理人员和调查人员将获得用户的搜索结果之前, 将需要长达3天。</span><span class="sxs-lookup"><span data-stu-id="370b2-p133">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed. For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency. As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  . In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed. Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="370b2-283">**电子数据展示管理器能否从两个单独的合规性边界中查看内容？**</span><span class="sxs-lookup"><span data-stu-id="370b2-283">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="370b2-p134">是的。为此, 可以将用户添加到对这两个机构都可见的角色组。</span><span class="sxs-lookup"><span data-stu-id="370b2-p134">Yes. This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="370b2-286">**搜索权限筛选器是否适用于电子数据展示事例保留、Office 365 保留策略或 DLP？**</span><span class="sxs-lookup"><span data-stu-id="370b2-286">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="370b2-287">否, 目前不</span><span class="sxs-lookup"><span data-stu-id="370b2-287">No, not at this time</span></span>
  
 <span data-ttu-id="370b2-288">**如果我指定一个区域来控制导出内容的位置, 但我在该区域没有 SharePoint 组织, 是否仍可以搜索 sharepoint？**</span><span class="sxs-lookup"><span data-stu-id="370b2-288">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="370b2-289">如果在搜索权限筛选器中指定的区域在您的组织中不存在, 则将搜索默认区域。</span><span class="sxs-lookup"><span data-stu-id="370b2-289">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="370b2-290">**在组织中可以创建的搜索权限筛选器的最大数目是多少？**</span><span class="sxs-lookup"><span data-stu-id="370b2-290">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="370b2-p135">对于可以在组织中创建的搜索权限筛选器的数量没有限制。但是, 当搜索权限筛选器超过100个时, 搜索性能将受到影响。若要尽可能缩小组织中的搜索权限筛选器的数量, 请创建筛选器, 以便尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中。</span><span class="sxs-lookup"><span data-stu-id="370b2-p135">There is no limit to the number of search permissions filters that can be created in an organization. However, search performance will be impacted when there are more than 100 search permissions filters. To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
