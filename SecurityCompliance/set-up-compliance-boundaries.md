---
title: 在 Office 365 中为电子数据展示调查设置合规性边界
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合规性边界来创建 Office 365 组织内逻辑控制电子数据展示管理员可以搜索用户内容位置的边界。合规性边界使用搜索筛选 （也称为遵从性安全筛选器） 来控制哪些邮箱、 SharePoint 网站的权限和 OneDrive 帐户可搜索的特定用户。
ms.openlocfilehash: 2bebd29fa7701ba07aae7170142263aeaec5569e
ms.sourcegitcommit: c7264f3a6a97f1ff544544e2c722e7825e265fa1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "26299236"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="584b1-104">在 Office 365 中为电子数据展示调查设置合规性边界</span><span class="sxs-lookup"><span data-stu-id="584b1-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="584b1-p102">合规性边界创建 Office 365 组织内控制用户内容位置 （如邮箱、 SharePoint 网站和 OneDrive 帐户） 的电子数据展示管理员可以搜索的逻辑边界。此外，合规性边界控制可以访问用来管理法律部门、 人力资源或其他调查组织中的电子数据展示事例。合规性边界需要通常需要尊重地理边框和法规，多国家/地区公司和政府，通常分为不同机构必要。Office 365，您满足合规性边界帮助中搜索和使用电子数据展示事例管理调查的内容时执行这些要求。</span><span class="sxs-lookup"><span data-stu-id="584b1-p102">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search. Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization. The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies. In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="584b1-109">我们将下图中使用该示例，介绍合规性边界的工作方式。</span><span class="sxs-lookup"><span data-stu-id="584b1-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![合规性边界包含搜索权限筛选器的控制对机构和管理员角色的访问组控制对 eDisocovery 情况下访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="584b1-p103">本示例中，Contoso LTD 是 Office 365 组织的两个子公司，Fourth Coffee 和 Coho Winery 组成。业务需要的电子数据展示经理和调查员可以仅 Exchange 邮箱、 OneDrive 帐户和 SharePoint 网站中搜索其机构。此外，电子数据展示管理员和调查员只能看到中的电子数据展示事例中其机构，并且他们只能访问它们的成员的用例。下面是合规性边界如何满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="584b1-p103">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery. The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency. Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of. Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="584b1-p104">筛选的电子数据展示管理员和调查员可搜索的内容位置的内容搜索控件中的功能搜索权限。这意味着电子数据展示经理和调查 Fourth Coffee 机构中的人员可以仅搜索内容的位置中 Fourth Coffee 子公司。在相同的限制适用于 Coho Winery 子公司。</span><span class="sxs-lookup"><span data-stu-id="584b1-p104">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search. This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary. The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="584b1-p105">角色组控制可以查看 Office 365 安全性电子数据展示事例&amp;合规性中心。这意味着，电子数据展示管理员和调查员只能看到他们机构中的电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="584b1-p105">Role groups control who can see the eDiscovery cases in the Office 365 Security &amp; Compliance Center. This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="584b1-p106">角色组还控制谁可以分配电子数据展示事例的成员。这意味着电子数据展示管理员和调查员仅可以向他们自己的成员的情况下分配成员。</span><span class="sxs-lookup"><span data-stu-id="584b1-p106">Role groups also control who can assign members to an eDiscovery case. This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="584b1-122">下面是设置合规性边界的过程：</span><span class="sxs-lookup"><span data-stu-id="584b1-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="584b1-123">步骤 1： 确定用于定义您机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="584b1-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="584b1-124">步骤 2： 文件与 Microsoft 支持的请求将同步到 OneDrive 帐户的用户属性</span><span class="sxs-lookup"><span data-stu-id="584b1-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="584b1-125">步骤 3： 创建每个代理机构角色组</span><span class="sxs-lookup"><span data-stu-id="584b1-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="584b1-126">步骤 4： 创建搜索权限筛选器以强制实施的合规性边界</span><span class="sxs-lookup"><span data-stu-id="584b1-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="584b1-127">步骤 5： 创建内部机构调查的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="584b1-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="584b1-128">步骤 1： 确定用于定义您机构的用户属性</span><span class="sxs-lookup"><span data-stu-id="584b1-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="584b1-p107">第一步是选择要使用的 Azure Active Directory 属性将定义您的机构。此属性将用于创建管理器来搜索唯一用户分配了此属性的特定值的内容位置的限制电子数据展示搜索权限筛选器。例如，假设 Contoso 决定要使用的**部门**属性。Fourth Coffee 子公司中的用户的此属性的值将为`FourthCoffee`和 Coho Winery 子公司中的用户的值将为`CohoWinery`。在步骤 4 中，将使用此`attribute:value`对 (例如，*部门： FourthCoffee* ) 来限制用户内容电子数据展示管理员可以搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="584b1-p107">The first step is to choose an Azure Active Directory attribute to use that will define your agencies. This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute. For example, let's say Contoso decides to use the **Department** attribute. The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`. In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="584b1-134">下面是可用于法规遵从性边界的 Azure Active Directory 用户属性的列表：</span><span class="sxs-lookup"><span data-stu-id="584b1-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="584b1-135">Company</span><span class="sxs-lookup"><span data-stu-id="584b1-135">Company</span></span>
    
- <span data-ttu-id="584b1-136">CountryCode</span><span class="sxs-lookup"><span data-stu-id="584b1-136">CountryCode</span></span>
    
- <span data-ttu-id="584b1-137">CustomAttribute1-CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="584b1-137">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="584b1-138">部门</span><span class="sxs-lookup"><span data-stu-id="584b1-138">Department</span></span>
    
- <span data-ttu-id="584b1-139">办公室</span><span class="sxs-lookup"><span data-stu-id="584b1-139">Office</span></span>
    
<span data-ttu-id="584b1-140">尽管更多的用户属性都可用，特别是对于 Exchange 邮箱，上面列出的属性是当前支持 OneDrive 是唯一的。</span><span class="sxs-lookup"><span data-stu-id="584b1-140">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="584b1-141">步骤 2： 文件与 Microsoft 支持的请求将同步到 OneDrive 帐户的用户属性</span><span class="sxs-lookup"><span data-stu-id="584b1-141">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="584b1-p108">下一步是文件与 Microsoft 支持的请求同步您选择在步骤 1 到 OneDrive 中的所有帐户在组织中的 Azure Active Directory 属性。此同步发生时，将属性 （以及它的值） 后您选择在步骤 1 中将映射到名为 SharePoint 中的隐藏托管属性`ComplianceAttribute`。您将使用此属性为在步骤 4 中的 OneDrive 创建搜索权限筛选器。</span><span class="sxs-lookup"><span data-stu-id="584b1-p108">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization. After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`. You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="584b1-145">提交到 Microsoft 支持的请求时，包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="584b1-145">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="584b1-146">Office 365 组织的默认域的名称</span><span class="sxs-lookup"><span data-stu-id="584b1-146">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="584b1-147">Azure Active Directory 属性 （从步骤 1) 的名称</span><span class="sxs-lookup"><span data-stu-id="584b1-147">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="584b1-p109">下面的标题或支持请求的用途的说明:"启用 OneDrive for Business 同步与 Azure Active 目录的合规性安全筛选器"。这有助于将请求路由到 Office 365 电子数据展示工程团队将实现请求。</span><span class="sxs-lookup"><span data-stu-id="584b1-p109">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="584b1-p110">工程更改并属性同步到 OneDrive 后，Microsoft 支持将向您发送中所做更改的内部版本号和估计的部署日期。请注意，部署过程，通常采用 4-6 周后提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="584b1-p110">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date. Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="584b1-p111">**重要：** 部署更改之前，您可以完成步骤 3 到步骤 5。但运行内容搜索从指定搜索权限筛选器中之前，部署更改后的 OneDrive 网站不会返回文档。</span><span class="sxs-lookup"><span data-stu-id="584b1-p111">**Important:** You can complete Step 3 through Step 5 before the change is deployed. But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="584b1-154">步骤 3： 创建每个代理机构角色组</span><span class="sxs-lookup"><span data-stu-id="584b1-154">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="584b1-p112">下一步是在 Office 365 安全性中创建的角色组&amp;会与您机构对齐的合规性中心。我们建议您通过复制内置电子数据展示管理员组、 添加适当的成员，并删除可能不适用于您的需求的角色创建新的角色组。有关电子数据展示相关的角色的详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="584b1-p112">The next step is to create the role groups in the Office 365 Security &amp; Compliance Center that will align with your agencies. We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs. For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="584b1-158">若要创建角色组，请转到安全中的**权限**页上&amp;合规性中心并创建每个工作组的角色组中每个将使用合规性边界和电子数据展示事例管理调查的机构。</span><span class="sxs-lookup"><span data-stu-id="584b1-158">To create the role groups, go to the **Permissions** page in the Security &amp; Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="584b1-159">使用 Contoso 合规性边界方案，需要创建四个角色组和相应的成员添加到每个。</span><span class="sxs-lookup"><span data-stu-id="584b1-159">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="584b1-160">Fourth Coffee 电子数据展示管理员</span><span class="sxs-lookup"><span data-stu-id="584b1-160">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="584b1-161">Fourth Coffee 调查员</span><span class="sxs-lookup"><span data-stu-id="584b1-161">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="584b1-162">Coho Winery 电子数据展示管理员</span><span class="sxs-lookup"><span data-stu-id="584b1-162">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="584b1-163">Coho Winery 调查员</span><span class="sxs-lookup"><span data-stu-id="584b1-163">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="584b1-164">步骤 4： 创建搜索权限筛选器以强制实施的合规性边界</span><span class="sxs-lookup"><span data-stu-id="584b1-164">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>
<span data-ttu-id="584b1-165"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="584b1-165"></span></span>

<span data-ttu-id="584b1-p113">您已创建的每个机构的角色组后下, 一步是创建关联到其特定代理人每个角色组的搜索权限筛选器，并定义合规性边界本身。您需要创建一个搜索权限的筛选器的每个代理。有关创建安全权限筛选器的详细信息，请参阅[筛选内容搜索的配置权限](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="584b1-p113">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself. You need to create one search permissions filter for each agency. For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="584b1-169">下面是用于创建用于法规遵从性边界的搜索权限筛选器的语法。</span><span class="sxs-lookup"><span data-stu-id="584b1-169">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="584b1-170">下面是每个命令中参数的说明：</span><span class="sxs-lookup"><span data-stu-id="584b1-170">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="584b1-p114">`FilterName`-指定筛选器的名称。将以使用使用的介绍，也可标识碳排放量筛选的名称。</span><span class="sxs-lookup"><span data-stu-id="584b1-p114">`FilterName` - Specifies the name of the filter. Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="584b1-p115">`Users`-指定用户或组获取应用于它们的内容搜索操作此筛选器。合规性边界此参数指定正在创建的筛选器的机构中的角色组 （即您在步骤 3 中创建）。请注意这是一个多值参数，所以可以包含一个或多个角色组，以逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="584b1-p115">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform. For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for. Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="584b1-p116">`Filters`-指定筛选器的搜索条件。合规性边界，您将定义的以下筛选器。每个应用于用户的内容位置。</span><span class="sxs-lookup"><span data-stu-id="584b1-p116">`Filters` - Specifies the search criteria for the filter. For the compliance boundaries, you will define the following filters. Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="584b1-p117">`Mailbox`-指定中定义的角色组的邮箱`Users`参数可以搜索。合规性边界*ComplianceAttribute*是您在步骤 1 中确定的同一个属性，它*AttributeValue*指定碳排放量。此筛选器允许仅在特定的机构; 搜索邮箱角色组的成员例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="584b1-p117">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search. For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="584b1-p118">`Site`-指定的角色组中定义的 OneDrive 帐户`Users`参数可以搜索。对于 OneDrive 筛选器，使用实际字符串`ComplianceAttribute`;这将映射到您在步骤 1 中确定并的同步到 OneDrive 帐户，由于您在步骤 2; 中提交支持请求的同一属性 *AttributeValue*指定碳排放量。此筛选器允许仅在特定的机构; 中搜索 OneDrive 帐户角色组的成员例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="584b1-p118">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search. For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="584b1-p119">`Site_Path`-指定 SharePoint 网站中定义的角色组的`Users`参数可以搜索。*SharePointURL*碳排放量，可以搜索角色组的成员; 中指定的站点例如，`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="584b1-p119">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search. The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="584b1-p120">`Action`-指定的筛选器应用于的合规性搜索操作的类型。例如，`-Action Search`中定义的角色组的成员时，仅将应用筛选器`Users`参数运行内容的搜索。在此例中导出搜索结果时，不会应用筛选器。合规性边界使用`-Action All`，以便筛选器应用于所有搜索操作。</span><span class="sxs-lookup"><span data-stu-id="584b1-p120">`Action` - Specifies the type of Compliance Search action that the filter is applied to. For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search. In this case, the filter wouldn't be applied when exporting search results. For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="584b1-191">内容搜索操作的列表，请参阅[Configure permissions 筛选内容搜索](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的"新建 ComplianceSecurityFilter"一节。</span><span class="sxs-lookup"><span data-stu-id="584b1-191">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="584b1-192">下面是会创建支持以下 Contoso 合规性边界方案的两个搜索权限筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="584b1-192">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="584b1-193">**Fourth Coffee**</span><span class="sxs-lookup"><span data-stu-id="584b1-193">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="584b1-194">**Coho Winery**</span><span class="sxs-lookup"><span data-stu-id="584b1-194">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="584b1-195">步骤 5： 创建内部机构调查的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="584b1-195">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="584b1-p121">最后一步是在安全中创建新的电子数据展示事例&amp;合规性中心，然后添加的角色组 — 您在步骤 3 中创建-用例的成员身份。这将导致使用合规性边界的两个重要特征：</span><span class="sxs-lookup"><span data-stu-id="584b1-p121">The final step is to create a new eDiscovery case in the Security &amp; Compliance Center and then add the role group—that you created in Step 3—as a member of the case. This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="584b1-p122">仅添加到用例的角色组的成员都将能够看到和访问安全中的用例&amp;合规性中心。例如，如果用例的唯一成员 Fourth Coffee 调查员角色组，然后 Fourth Coffee 电子数据展示管理员角色组 （或其他任何角色组的成员） 的成员将无法查看或访问这种情况。</span><span class="sxs-lookup"><span data-stu-id="584b1-p122">Only members of the role group added to the case will be able to see and access the case in the Security &amp; Compliance Center. For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="584b1-200">分配给案例的角色组的成员运行时搜索与案例相关联，它们将仅能搜索其机构 （这由您在步骤 4 中创建的搜索权限筛选器。） 中的内容位置</span><span class="sxs-lookup"><span data-stu-id="584b1-200">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="584b1-201">创建新的用例，并分配成员：</span><span class="sxs-lookup"><span data-stu-id="584b1-201">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="584b1-202">转到安全中的**电子数据展示**页上&amp;合规性中心并创建一个新的情形。</span><span class="sxs-lookup"><span data-stu-id="584b1-202">Go to the **eDiscovery** page in the Security &amp; Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="584b1-203">在电子数据展示事例的列表中，单击您刚才创建的用例的名称。</span><span class="sxs-lookup"><span data-stu-id="584b1-203">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="584b1-204">在**管理此案例**弹出页的**管理角色组**，单击![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**添加**。</span><span class="sxs-lookup"><span data-stu-id="584b1-204">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![添加角色组成员身份的电子数据展示事例](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="584b1-206">在角色组的列表中，选择您在步骤 3 中创建的角色组之一，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="584b1-206">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="584b1-207">单击以保存更改**管理本例**弹出上的**保存**。</span><span class="sxs-lookup"><span data-stu-id="584b1-207">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="584b1-208">合规性边界限制</span><span class="sxs-lookup"><span data-stu-id="584b1-208">Compliance boundary limitations</span></span>

<span data-ttu-id="584b1-209">管理电子数据展示事例和合规性边界的调查中使用时，请记住以下限制。</span><span class="sxs-lookup"><span data-stu-id="584b1-209">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="584b1-p123">时创建和运行内容搜索，您可以选择您的机构之外的内容位置。但是，由于搜索权限筛选器，不会在搜索结果中包含这些位置的内容。</span><span class="sxs-lookup"><span data-stu-id="584b1-p123">When creating and running a Content Search, you can select content locations that are outside of your agency. However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="584b1-p124">合规性边界不适用于电子数据展示事例中保留。这意味着中一个机构电子数据展示的管理器可以将用户置于保持在不同的机构。但是，如果电子数据展示管理器中搜索的内容被置于保持状态的用户的位置，则将强制合规性边界。这意味着电子数据展示管理器将不会很可以搜索用户的内容位置，即使他们都能够将用户置于保留。</span><span class="sxs-lookup"><span data-stu-id="584b1-p124">Compliance boundaries don't apply to holds in eDiscovery cases. That means an eDiscovery manager in one agency can place a user in a different agency on hold. However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold. That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="584b1-216">此外，保留统计信息将仅适用于内容位置的碳排放量。</span><span class="sxs-lookup"><span data-stu-id="584b1-216">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="584b1-217">搜索权限筛选器不适用于 Exchange 公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="584b1-217">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="584b1-218">搜索和导出多地理环境中的内容</span><span class="sxs-lookup"><span data-stu-id="584b1-218">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="584b1-219">搜索权限筛选器还允许您控制其中导出传送内容和搜索[SharePoint 多地理环境](https://go.microsoft.com/fwlink/?linkid=860840)中的 SharePoint 网站和 OneDrive 帐户时，可搜索的数据中心：</span><span class="sxs-lookup"><span data-stu-id="584b1-219">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching SharePoint sites and OneDrive accounts in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840):</span></span>
  
- <span data-ttu-id="584b1-p125">从特定数据中心导出搜索结果。这意味着，您可以指定数据中心位置将从导出结果的搜索。</span><span class="sxs-lookup"><span data-stu-id="584b1-p125">Export search results from a specific data center. This means that you can specify the data center location that search results will be exported from.</span></span>
    
- <span data-ttu-id="584b1-p126">路由到附属数据中心的 SharePoint 网站和 OneDrive 帐户的搜索。这意味着您可以指定运行搜索的数据中心位置。</span><span class="sxs-lookup"><span data-stu-id="584b1-p126">Route searches of SharePoint sites and OneDrive accounts to a satellite data center. This means you can specify the data center location where searches will be run.</span></span>
    
<span data-ttu-id="584b1-224">使用**Region**参数的**新建 ComplianceSecurityFilter**或**集 ComplianceSecurityFilter** cmdlet 创建或更改将通过路由导出的数据中心。</span><span class="sxs-lookup"><span data-stu-id="584b1-224">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
|<span data-ttu-id="584b1-225">**参数值**</span><span class="sxs-lookup"><span data-stu-id="584b1-225">**Parameter value**</span></span>|<span data-ttu-id="584b1-226">**数据中心位置**</span><span class="sxs-lookup"><span data-stu-id="584b1-226">**Data center location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="584b1-227">NAM</span><span class="sxs-lookup"><span data-stu-id="584b1-227">NAM</span></span>  <br/> |<span data-ttu-id="584b1-228">北美 （实际数据中心按在美国）</span><span class="sxs-lookup"><span data-stu-id="584b1-228">North American (actual data centers are in the US)</span></span>  <br/> |
|<span data-ttu-id="584b1-229">EUR</span><span class="sxs-lookup"><span data-stu-id="584b1-229">EUR</span></span>  <br/> |<span data-ttu-id="584b1-230">欧洲</span><span class="sxs-lookup"><span data-stu-id="584b1-230">Europe</span></span>  <br/> |
|<span data-ttu-id="584b1-231">APC</span><span class="sxs-lookup"><span data-stu-id="584b1-231">APC</span></span>  <br/> |<span data-ttu-id="584b1-232">亚太地区</span><span class="sxs-lookup"><span data-stu-id="584b1-232">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="584b1-233">CAN</span><span class="sxs-lookup"><span data-stu-id="584b1-233">CAN</span></span> <br/> |<span data-ttu-id="584b1-234">加拿大</span><span class="sxs-lookup"><span data-stu-id="584b1-234">Canada</span></span>
   
<span data-ttu-id="584b1-p127">同样，您可以使用**区域**参数值的下列值来控制搜索 SharePoint 和 OneDrive 位置时，内容搜索将运行中的数据中心。请注意下表还会显示将通过路由导出的数据中心。</span><span class="sxs-lookup"><span data-stu-id="584b1-p127">Similarly, you can use the following values for the **Region** parameter values to control which data center that Content Searches will run in when searching SharePoint and OneDrive locations. Note that the following table also shows which data center exports will be routed through.</span></span> 
  
|<span data-ttu-id="584b1-237">**参数值**</span><span class="sxs-lookup"><span data-stu-id="584b1-237">**Parameter value**</span></span>|<span data-ttu-id="584b1-238">**数据中心路由导出位置**</span><span class="sxs-lookup"><span data-stu-id="584b1-238">**Data center routing locations for export**</span></span>|
|:-----|:-----|
|<span data-ttu-id="584b1-239">NAM</span><span class="sxs-lookup"><span data-stu-id="584b1-239">NAM</span></span>  <br/> |<span data-ttu-id="584b1-240">美国</span><span class="sxs-lookup"><span data-stu-id="584b1-240">US</span></span>  <br/> |
|<span data-ttu-id="584b1-241">EUR</span><span class="sxs-lookup"><span data-stu-id="584b1-241">EUR</span></span>  <br/> |<span data-ttu-id="584b1-242">欧洲</span><span class="sxs-lookup"><span data-stu-id="584b1-242">Europe</span></span>  <br/> |
|<span data-ttu-id="584b1-243">APC</span><span class="sxs-lookup"><span data-stu-id="584b1-243">APC</span></span>  <br/> |<span data-ttu-id="584b1-244">亚太地区</span><span class="sxs-lookup"><span data-stu-id="584b1-244">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="584b1-245">CAN</span><span class="sxs-lookup"><span data-stu-id="584b1-245">CAN</span></span>  <br/> |<span data-ttu-id="584b1-246">美国</span><span class="sxs-lookup"><span data-stu-id="584b1-246">US</span></span>  <br/> |
|<span data-ttu-id="584b1-247">AUS</span><span class="sxs-lookup"><span data-stu-id="584b1-247">AUS</span></span>  <br/> |<span data-ttu-id="584b1-248">亚太地区</span><span class="sxs-lookup"><span data-stu-id="584b1-248">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="584b1-249">KOR</span><span class="sxs-lookup"><span data-stu-id="584b1-249">KOR</span></span>  <br/> |<span data-ttu-id="584b1-250">组织的默认数据中心</span><span class="sxs-lookup"><span data-stu-id="584b1-250">The organization's default data center</span></span>  <br/> |
|<span data-ttu-id="584b1-251">GBR</span><span class="sxs-lookup"><span data-stu-id="584b1-251">GBR</span></span>  <br/> |<span data-ttu-id="584b1-252">欧洲</span><span class="sxs-lookup"><span data-stu-id="584b1-252">Europe</span></span>  <br/> |
|<span data-ttu-id="584b1-253">JPN</span><span class="sxs-lookup"><span data-stu-id="584b1-253">JPN</span></span>  <br/> |<span data-ttu-id="584b1-254">亚太地区</span><span class="sxs-lookup"><span data-stu-id="584b1-254">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="584b1-255">IND</span><span class="sxs-lookup"><span data-stu-id="584b1-255">IND</span></span>  <br/> |<span data-ttu-id="584b1-256">亚太地区</span><span class="sxs-lookup"><span data-stu-id="584b1-256">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="584b1-257">LAM</span><span class="sxs-lookup"><span data-stu-id="584b1-257">LAM</span></span>  <br/> |<span data-ttu-id="584b1-258">美国</span><span class="sxs-lookup"><span data-stu-id="584b1-258">US</span></span>  <br/> |
   
 <span data-ttu-id="584b1-259">**注意：** 如果不指定搜索权限筛选器的区域参数，将搜索组织默认 SharePoint 区域，然后搜索结果导出到最接近的数据中心。</span><span class="sxs-lookup"><span data-stu-id="584b1-259">**Note:** If you don't specify the Region parameter for a search permissions filter, the organizations default SharePoint region will be searched, then search results are exported to the closest data center.</span></span> 
  
<span data-ttu-id="584b1-p128">下面是使用的示例 **-区域**参数创建搜索权限合规性边界的筛选器时。此，假定 Fourth Coffee 子公司位于北美和欧洲中是 Coho Winery。</span><span class="sxs-lookup"><span data-stu-id="584b1-p128">Here are examples of using the **-Region** parameter when creating search permission filters for compliance boundaries. This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="584b1-262">保留以下操作中应注意时搜索和导出内容多地理环境中。</span><span class="sxs-lookup"><span data-stu-id="584b1-262">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="584b1-p129">**Region**参数不控制 Exchange 邮箱; 的搜索搜索邮箱时，将搜索所有数据中心。若要限制的哪些 Exchange 邮箱可以将搜索范围，请使用**筛选器**参数创建或更改搜索权限筛选器时。</span><span class="sxs-lookup"><span data-stu-id="584b1-p129">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes. To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="584b1-265">电子数据展示中搜索多个 SharePoint 区域间的管理器必要时，您需要在指定的备用区域的搜索权限筛选器中创建不同的用户帐户的电子数据展示可用的管理器位置SharePoint 网站或 OneDrive 帐户位于。</span><span class="sxs-lookup"><span data-stu-id="584b1-265">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="584b1-p130">搜索 SharePoint 和 OneDrive 中的内容时, **Region**参数指示到任一主搜索或卫星电子数据展示管理器将在其中进行电子数据展示调查的位置。如果电子数据展示管理器中搜索外部搜索权限筛选器中指定的区域的 SharePoint 和 OneDrive 网站，则将不返回任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="584b1-p130">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations. If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="584b1-p131">所有内容的位置 （包括 Exchange、 Skype 业务、 SharePoint、 onedrive 和其他 Office 365 服务，您可以使用内容搜索工具搜索） 中的内容导出搜索结果时, 将上载到 Azure 存储位置由**Region**参数指定的数据中心。这有助于组织内合规性保持通过不允许跨控制边框要导出的内容。如果搜索权限筛选器中指定的区域，则内容上载到组织的默认区域。</span><span class="sxs-lookup"><span data-stu-id="584b1-p131">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter. This helps organizations stay within compliance by not allowing content to be exported across controlled borders. If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="584b1-271">您可以编辑现有的搜索权限筛选以添加或更改区域通过运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="584b1-271">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="584b1-272">常见问题</span><span class="sxs-lookup"><span data-stu-id="584b1-272">Frequently asked questions</span></span>

 <span data-ttu-id="584b1-273">**谁可以创建和管理搜索权限筛选器 （使用新建 ComplianceSecurityFilter 和设置 ComplianceSecurityFilter cmdlet）？**</span><span class="sxs-lookup"><span data-stu-id="584b1-273">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="584b1-274">若要创建，查看和修改搜索权限筛选器，您必须是安全中的 Organization Management 角色组的成员&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="584b1-274">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security &amp; Compliance Center.</span></span>
  
 <span data-ttu-id="584b1-275">**如果电子数据展示管理器已分配给多个跨越多个机构的角色组，如何这些搜索一个机构中的内容或其他？**</span><span class="sxs-lookup"><span data-stu-id="584b1-275">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="584b1-p132">电子数据展示经理可以添加到他们将搜索限制到特定的代理人的搜索查询的参数。例如，如果组织具有指定的**CustomAttribute10**属性区分机构，它们可以将以下追加到其搜索查询中的特定机构搜索邮箱和 OneDrive 帐户： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="584b1-p132">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency. For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="584b1-278">**用作搜索权限筛选器中的合规性属性的属性的值更改时，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="584b1-278">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="584b1-p133">计搜索权限筛选器的筛选器中使用的属性值更改时强制实施的合规性边界最多为 3 天。例如，Contoso 方案中假设 Fourth Coffee 机构中的用户转接到 Coho Winery 碳排放量。因此，在用户对象的**部门**属性的值从*FourthCoffee*更改为*CohoWinery* 。在此情况下，Fourth Coffee 电子数据展示和投资人将为 3 天后更改该属性设置为该用户获得搜索结果。同样，将花费多达 3 天之前 Coho Winery 电子数据展示管理员和调查员将用户获取搜索结果。</span><span class="sxs-lookup"><span data-stu-id="584b1-p133">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed. For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency. As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  . In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed. Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="584b1-284">**电子数据展示经理可以看到来自两个单独的合规性边界的内容？**</span><span class="sxs-lookup"><span data-stu-id="584b1-284">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="584b1-p134">是的。这可以通过将用户添加到角色组具有对这两个机构可见的。</span><span class="sxs-lookup"><span data-stu-id="584b1-p134">Yes. This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="584b1-287">**搜索电子数据展示案例保留、 Office 365 保留策略或 DLP 权限筛选器的工作？**</span><span class="sxs-lookup"><span data-stu-id="584b1-287">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="584b1-288">否，不是这次</span><span class="sxs-lookup"><span data-stu-id="584b1-288">No, not at this time</span></span>
  
 <span data-ttu-id="584b1-289">**如果指定区域保存到其中的导出内容，但在该区域中都没有的 SharePoint 组织的控件，可以仍搜索 SharePoint？**</span><span class="sxs-lookup"><span data-stu-id="584b1-289">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="584b1-290">如果您的组织中不存在搜索权限筛选器中指定的区域，将搜索的默认区域。</span><span class="sxs-lookup"><span data-stu-id="584b1-290">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="584b1-291">**可以在组织中创建的搜索权限筛选器的最大数目是什么？**</span><span class="sxs-lookup"><span data-stu-id="584b1-291">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="584b1-p135">可在组织中创建的搜索权限筛选器的数量没有限制。但是，有 100 多个搜索权限筛选器时，将会影响搜索性能。若要保留在组织中的搜索筛选器权限数目尽可能的小，请创建将规则的 Exchange、 SharePoint 和 OneDrive 合并到单个搜索权限筛选器尽可能的筛选器。</span><span class="sxs-lookup"><span data-stu-id="584b1-p135">There is no limit to the number of search permissions filters that can be created in an organization. However, search performance will be impacted when there are more than 100 search permissions filters. To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
