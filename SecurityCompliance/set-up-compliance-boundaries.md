---
title: 在 Office 365 中为电子数据展示调查设置合规性边界
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/6/2018
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
ms.openlocfilehash: 822d228d64d2fd5432db327db98e8d7329c7d939
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258630"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>在 Office 365 中为电子数据展示调查设置合规性边界

合规性边界创建 Office 365 组织内控制用户内容位置 （如邮箱、 SharePoint 网站和 OneDrive 帐户） 的电子数据展示管理员可以搜索的逻辑边界。此外，合规性边界控制可以访问用来管理法律部门、 人力资源或其他调查组织中的电子数据展示事例。合规性边界需要通常需要尊重地理边框和法规，多国家/地区公司和政府，通常分为不同机构必要。Office 365，您满足合规性边界帮助中搜索和使用电子数据展示事例管理调查的内容时执行这些要求。
  
我们将下图中使用该示例，介绍合规性边界的工作方式。
  
![合规性边界包含搜索权限筛选器的控制对机构和管理员角色的访问组控制对 eDisocovery 情况下访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
本示例中，Contoso LTD 是 Office 365 组织的两个子公司，Fourth Coffee 和 Coho Winery 组成。业务需要的电子数据展示经理和调查员可以仅 Exchange 邮箱、 OneDrive 帐户和 SharePoint 网站中搜索其机构。此外，电子数据展示管理员和调查员只能看到中的电子数据展示事例中其机构，并且他们只能访问它们的成员的用例。下面是合规性边界如何满足这些要求。
  
- 筛选的电子数据展示管理员和调查员可搜索的内容位置的内容搜索控件中的功能搜索权限。这意味着电子数据展示经理和调查 Fourth Coffee 机构中的人员可以仅搜索内容的位置中 Fourth Coffee 子公司。在相同的限制适用于 Coho Winery 子公司。
    
    角色组控制可以查看 Office 365 安全性电子数据展示事例&amp;合规性中心。这意味着，电子数据展示管理员和调查员只能看到他们机构中的电子数据展示事例。
    
- 角色组还控制谁可以分配电子数据展示事例的成员。这意味着电子数据展示管理员和调查员仅可以向他们自己的成员的情况下分配成员。
    
下面是设置合规性边界的过程：
  
[步骤 1： 确定用于定义您机构的用户属性](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步骤 2： 文件与 Microsoft 支持的请求将同步到 OneDrive 帐户的用户属性](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步骤 3： 创建每个代理机构角色组](#step-3-create-a-role-group-for-each-agency)

[步骤 4： 创建搜索权限筛选器以强制实施的合规性边界](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步骤 5： 创建内部机构调查的电子数据展示事例](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步骤 1： 确定用于定义您机构的用户属性

第一步是选择要使用的 Azure Active Directory 属性将定义您的机构。此属性将用于创建管理器来搜索唯一用户分配了此属性的特定值的内容位置的限制电子数据展示搜索权限筛选器。例如，假设 Contoso 决定要使用的**部门**属性。Fourth Coffee 子公司中的用户的此属性的值将为`FourthCoffee`和 Coho Winery 子公司中的用户的值将为`CohoWinery`。在步骤 4 中，将使用此`attribute:value`对 (例如，*部门： FourthCoffee* ) 来限制用户内容电子数据展示管理员可以搜索的位置。 
  
下面是可用于法规遵从性边界的 Azure Active Directory 用户属性的列表：
  
- Company
    
- CountryCode
    
- CustomAttribute1-CustomAttribute15
    
- 部门
    
- 办公室
    
尽管更多的用户属性都可用，特别是对于 Exchange 邮箱，上面列出的属性是当前支持 OneDrive 是唯一的。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步骤 2： 文件与 Microsoft 支持的请求将同步到 OneDrive 帐户的用户属性

下一步是文件与 Microsoft 支持的请求同步您选择在步骤 1 到 OneDrive 中的所有帐户在组织中的 Azure Active Directory 属性。此同步发生时，将属性 （以及它的值） 后您选择在步骤 1 中将映射到名为 SharePoint 中的隐藏托管属性`ComplianceAttribute`。您将使用此属性为在步骤 4 中的 OneDrive 创建搜索权限筛选器。
  
提交到 Microsoft 支持的请求时，包括以下信息：
  
- Office 365 组织的默认域的名称
    
- Azure Active Directory 属性 （从步骤 1) 的名称
    
- 下面的标题或支持请求的用途的说明:"启用 OneDrive for Business 同步与 Azure Active 目录的合规性安全筛选器"。这有助于将请求路由到 Office 365 电子数据展示工程团队将实现请求。
    
工程更改并属性同步到 OneDrive 后，Microsoft 支持将向您发送中所做更改的内部版本号和估计的部署日期。请注意，部署过程，通常采用 4-6 周后提交支持请求。
  
 **重要：** 部署更改之前，您可以完成步骤 3 到步骤 5。但运行内容搜索从指定搜索权限筛选器中之前，部署更改后的 OneDrive 网站不会返回文档。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步骤 3： 创建每个代理机构角色组

下一步是在 Office 365 安全性中创建的角色组&amp;会与您机构对齐的合规性中心。我们建议您通过复制内置电子数据展示管理员组、 添加适当的成员，并删除可能不适用于您的需求的角色创建新的角色组。有关电子数据展示相关的角色的详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
  
若要创建角色组，请转到安全中的**权限**页上&amp;合规性中心并创建每个工作组的角色组中每个将使用合规性边界和电子数据展示事例管理调查的机构。 
  
使用 Contoso 合规性边界方案，需要创建四个角色组和相应的成员添加到每个。
  
- Fourth Coffee 电子数据展示管理员
    
- Fourth Coffee 调查员
    
- Coho Winery 电子数据展示管理员
    
- Coho Winery 调查员
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步骤 4： 创建搜索权限筛选器以强制实施的合规性边界
<a name="step4"> </a>

您已创建的每个机构的角色组后下, 一步是创建关联到其特定代理人每个角色组的搜索权限筛选器，并定义合规性边界本身。您需要创建一个搜索权限的筛选器的每个代理。有关创建安全权限筛选器的详细信息，请参阅[筛选内容搜索的配置权限](permissions-filtering-for-content-search.md)。
  
下面是用于创建用于法规遵从性边界的搜索权限筛选器的语法。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
下面是每个命令中参数的说明：
  
-  `FilterName`-指定筛选器的名称。将以使用使用的介绍，也可标识碳排放量筛选的名称。 
    
-  `Users`-指定用户或组获取应用于它们的内容搜索操作此筛选器。合规性边界此参数指定正在创建的筛选器的机构中的角色组 （即您在步骤 3 中创建）。请注意这是一个多值参数，所以可以包含一个或多个角色组，以逗号分隔。 
    
-  `Filters`-指定筛选器的搜索条件。合规性边界，您将定义的以下筛选器。每个应用于用户的内容位置。 
    
  -  `Mailbox`-指定中定义的角色组的邮箱`Users`参数可以搜索。合规性边界*ComplianceAttribute*是您在步骤 1 中确定的同一个属性，它*AttributeValue*指定碳排放量。此筛选器允许仅在特定的机构; 搜索邮箱角色组的成员例如， `"Mailbox_Department -eq 'FourthCoffee'"` 。 
    
  -  `Site`-指定的角色组中定义的 OneDrive 帐户`Users`参数可以搜索。对于 OneDrive 筛选器，使用实际字符串`ComplianceAttribute`;这将映射到您在步骤 1 中确定并的同步到 OneDrive 帐户，由于您在步骤 2; 中提交支持请求的同一属性 *AttributeValue*指定碳排放量。此筛选器允许仅在特定的机构; 中搜索 OneDrive 帐户角色组的成员例如， `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
  -  `Site_Path`-指定 SharePoint 网站中定义的角色组的`Users`参数可以搜索。*SharePointURL*碳排放量，可以搜索角色组的成员; 中指定的站点例如，`Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`
    
-  `Action`-指定的筛选器应用于的合规性搜索操作的类型。例如，`-Action Search`中定义的角色组的成员时，仅将应用筛选器`Users`参数运行内容的搜索。在此例中导出搜索结果时，不会应用筛选器。合规性边界使用`-Action All`，以便筛选器应用于所有搜索操作。 
    
    内容搜索操作的列表，请参阅[Configure permissions 筛选内容搜索](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的"新建 ComplianceSecurityFilter"一节。
    
下面是会创建支持以下 Contoso 合规性边界方案的两个搜索权限筛选器的示例。
  
 **Fourth Coffee**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a>步骤 5： 创建内部机构调查的电子数据展示事例

最后一步是在安全中创建新的电子数据展示事例&amp;合规性中心，然后添加的角色组 — 您在步骤 3 中创建-用例的成员身份。这将导致使用合规性边界的两个重要特征：
  
- 仅添加到用例的角色组的成员都将能够看到和访问安全中的用例&amp;合规性中心。例如，如果用例的唯一成员 Fourth Coffee 调查员角色组，然后 Fourth Coffee 电子数据展示管理员角色组 （或其他任何角色组的成员） 的成员将无法查看或访问这种情况。
    
- 分配给案例的角色组的成员运行时搜索与案例相关联，它们将仅能搜索其机构 （这由您在步骤 4 中创建的搜索权限筛选器。） 中的内容位置


创建新的用例，并分配成员：
    
1. 转到安全中的**电子数据展示**页上&amp;合规性中心并创建一个新的情形。 
    
2. 在电子数据展示事例的列表中，单击您刚才创建的用例的名称。
    
3. 在**管理此案例**弹出页的**管理角色组**，单击![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**添加**。
    
    ![添加角色组成员身份的电子数据展示事例](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色组的列表中，选择您在步骤 3 中创建的角色组之一，然后单击**添加**。
    
5. 单击以保存更改**管理本例**弹出上的**保存**。 

## <a name="compliance-boundary-limitations"></a>合规性边界限制

管理电子数据展示事例和合规性边界的调查中使用时，请记住以下限制。
  
- 时创建和运行内容搜索，您可以选择您的机构之外的内容位置。但是，由于搜索权限筛选器，不会在搜索结果中包含这些位置的内容。
    
- 合规性边界不适用于电子数据展示事例中保留。这意味着中一个机构电子数据展示的管理器可以将用户置于保持在不同的机构。但是，如果电子数据展示管理器中搜索的内容被置于保持状态的用户的位置，则将强制合规性边界。这意味着电子数据展示管理器将不会很可以搜索用户的内容位置，即使他们都能够将用户置于保留。
    
    此外，保留统计信息将仅适用于内容位置的碳排放量。
    
- 搜索权限筛选器不适用于 Exchange 公用文件夹。

## <a name="searching-and-exporting-sharepoint-content-in-multi-geo-environments"></a>搜索和导出多地理环境中的 SharePoint 内容

搜索权限筛选器还允许您控制其中导出传送内容和[SharePoint 多地理环境](https://go.microsoft.com/fwlink/?linkid=860840)中的数据中心可搜索 SharePoint 网站和 OneDrive 帐户：
  
- 从特定数据中心导出搜索结果。这意味着，您可以指定数据中心位置将从导出结果的搜索。
    
- 路由到附属数据中心的 SharePoint 网站和 OneDrive 帐户的搜索。这意味着您可以指定运行搜索的数据中心位置。
    
使用**Region**参数的**新建 ComplianceSecurityFilter**或**集 ComplianceSecurityFilter** cmdlet 创建或更改将通过路由导出的数据中心。
  
|**参数值**|**数据中心位置**|
|:-----|:-----|
|NAM  <br/> |北美 （实际数据中心按在美国）  <br/> |
|EUR  <br/> |欧洲  <br/> |
|APC  <br/> |亚太地区  <br/> |
|CAN <br/> |加拿大
   
同样，您可以使用**区域**参数值的下列值来控制搜索 SharePoint 和 OneDrive 位置时，内容搜索将运行中的数据中心。请注意下表还会显示将通过路由导出的数据中心。 
  
|**参数值**|**数据中心路由导出位置**|
|:-----|:-----|
|NAM  <br/> |美国  <br/> |
|EUR  <br/> |欧洲  <br/> |
|APC  <br/> |亚太地区  <br/> |
|CAN  <br/> |美国  <br/> |
|AUS  <br/> |亚太地区  <br/> |
|KOR  <br/> |组织的默认数据中心  <br/> |
|GBR  <br/> |欧洲  <br/> |
|JPN  <br/> |亚太地区  <br/> |
|IND  <br/> |亚太地区  <br/> |
|LAM  <br/> |美国  <br/> |
   
 **注意：** 如果不指定搜索权限筛选器的区域参数，然后搜索结果导出从最接近的数据中心中。 
  
下面是使用的示例 **-区域**参数创建搜索权限合规性边界的筛选器时。此，假定 Fourth Coffee 子公司位于北美和欧洲中是 Coho Winery。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
内容多地理环境中保留中搜索和导出 SharePoint 和 OneDrive 时，请记住以下事项。
  
- **Region**参数不控制 Exchange 邮箱; 的搜索搜索邮箱时，将搜索所有数据中心。若要限制的哪些 Exchange 邮箱可以将搜索范围，请使用**筛选器**参数创建或更改搜索权限筛选器时。 
    
- 电子数据展示中搜索多个 SharePoint 区域间的管理器必要时，您需要在指定的备用区域的搜索权限筛选器中创建不同的用户帐户的电子数据展示可用的管理器位置SharePoint 网站或 OneDrive 帐户位于。
    
- 搜索 SharePoint 和 OneDrive 中的内容时, **Region**参数指示到任一主搜索或卫星电子数据展示管理器将在其中进行电子数据展示调查的位置。如果电子数据展示管理器中搜索外部搜索权限筛选器中指定的区域的 SharePoint 和 OneDrive 网站，则将不返回任何搜索结果。 
    
- 所有内容的位置 （包括 Exchange、 Skype 业务、 SharePoint、 onedrive 和其他 Office 365 服务，您可以使用内容搜索工具搜索） 中的内容导出搜索结果时, 将上载到 Azure 存储位置由**Region**参数指定的数据中心。这有助于组织内合规性保持通过不允许跨控制边框要导出的内容。如果搜索权限筛选器中指定的区域，则内容上载到组织的默认区域。 
    
- 您可以编辑现有的搜索权限筛选以添加或更改区域通过运行以下命令：

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>常见问题

 **谁可以创建和管理搜索权限筛选器 （使用新建 ComplianceSecurityFilter 和设置 ComplianceSecurityFilter cmdlet）？**
  
若要创建，查看和修改搜索权限筛选器，您必须是安全中的 Organization Management 角色组的成员&amp;合规性中心。
  
 **如果电子数据展示管理器已分配给多个跨越多个机构的角色组，如何这些搜索一个机构中的内容或其他？**
  
电子数据展示经理可以添加到他们将搜索限制到特定的代理人的搜索查询的参数。例如，如果组织具有指定的**CustomAttribute10**属性区分机构，它们可以将以下追加到其搜索查询中的特定机构搜索邮箱和 OneDrive 帐户： `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **用作搜索权限筛选器中的合规性属性的属性的值更改时，会发生什么情况？**
  
计搜索权限筛选器的筛选器中使用的属性值更改时强制实施的合规性边界最多为 3 天。例如，Contoso 方案中假设 Fourth Coffee 机构中的用户转接到 Coho Winery 碳排放量。因此，在用户对象的**部门**属性的值从*FourthCoffee*更改为*CohoWinery* 。在此情况下，Fourth Coffee 电子数据展示和投资人将为 3 天后更改该属性设置为该用户获得搜索结果。同样，将花费多达 3 天之前 Coho Winery 电子数据展示管理员和调查员将用户获取搜索结果。 
  
 **电子数据展示经理可以看到来自两个单独的合规性边界的内容？**
  
是的。这可以通过将用户添加到角色组具有对这两个机构可见的。
  
 **搜索电子数据展示案例保留、 Office 365 保留策略或 DLP 权限筛选器的工作？**
  
否，不是这次
  
 **如果指定区域保存到其中的导出内容，但在该区域中都没有的 SharePoint 组织的控件，可以仍搜索 SharePoint？**
  
如果您的组织中不存在搜索权限筛选器中指定的区域，将搜索的默认区域。
  
 **可以在组织中创建的搜索权限筛选器的最大数目是什么？**
  
可在组织中创建的搜索权限筛选器的数量没有限制。但是，有 100 多个搜索权限筛选器时，将会影响搜索性能。若要保留在组织中的搜索筛选器权限数目尽可能的小，请创建将规则的 Exchange、 SharePoint 和 OneDrive 合并到单个搜索权限筛选器尽可能的筛选器。
