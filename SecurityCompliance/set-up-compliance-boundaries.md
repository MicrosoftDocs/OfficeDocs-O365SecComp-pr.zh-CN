---
title: 在 Office 365 中为电子数据展示调查设置合规性边界
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: 使用合规性边界在 Office 365 组织中创建用于控制电子数据展示管理器可搜索的用户内容位置的逻辑边界。 合规性边界使用搜索权限筛选 (也称为合规性安全筛选器) 控制特定用户可以搜索哪些邮箱、SharePoint 网站和 OneDrive 帐户。
ms.openlocfilehash: 44c157b8f155755c6a48830231074643a830f498
ms.sourcegitcommit: 226adb6d05015da16138b315dd2f5b937bf4354d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "36302421"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a>在 Office 365 中为电子数据展示调查设置合规性边界

合规性边界在 Office 365 组织中创建逻辑边界, 以控制电子数据展示管理者可以搜索的用户内容位置 (如邮箱、SharePoint 网站和 OneDrive 帐户)。 此外, 合规性边界控制谁可以访问电子数据展示用例, 以管理组织中的法律、人力资源或其他调查。 对于必须遵守地理位置 boarders 和管理法规以及政府的政府 (通常分为不同的机构) 的多国公司来说, 需求是合规性边界所必需的。 在 Office 365 中, 合规性边界可帮助您在执行内容搜索和使用电子数据展示案例管理调查时满足这些要求。
  
我们使用下图中的示例来说明合规性边界的工作原理。
  
![合规性边界包含搜索权限筛选器, 这些筛选器控制对对电子数据展示案例的访问进行控制的代理和管理员角色组的访问](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
在此示例中, Contoso 有限公司是由两个子公司、第四个咖啡和 Coho Winery 组成的 Office 365 组织。 业务要求电子数据展示 mangers 和调查人员只能在其代理中搜索 Exchange 邮箱、OneDrive 帐户和 SharePoint 网站。 此外, 电子数据展示管理者和调查人员只能查看其代理中的电子数据展示案例, 并且只能访问他们所属的案例。 下面介绍了合规性边界如何满足这些要求。
  
- 内容搜索中的搜索权限筛选功能控制电子数据展示管理者和调查人员可以搜索的内容位置。 这意味着第四个咖啡店中的电子数据展示管理者和调查人员只能在第四个咖啡子公司中搜索内容位置。 此限制适用于 Coho Winery 子公司。
    
    角色组控制哪些用户可以查看安全 & 合规中心中的电子数据展示事例。 这意味着电子数据展示管理者和调查人员只能查看其代理中的电子数据展示事例。
    
- 角色组还控制谁可以向电子数据展示事例分配成员。 这意味着电子数据展示管理者和调查人员只能将成员分配给他们自己所属的案例。
    
下面是设置合规性边界的过程:
  
[步骤 1: 标识用于定义您的机构的用户属性](#step-1-identify-a-user-attribute-to-define-your-agencies)

[步骤 2: 为 Microsoft 支持文件提供将 user 属性同步到 OneDrive 帐户的请求](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[步骤 3: 为每个代理创建角色组](#step-3-create-a-role-group-for-each-agency)

[步骤 4: 创建搜索权限筛选器以强制实施合规性边界](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[步骤 5: 为机构内调查创建电子数据展示事例](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>步骤 1: 标识用于定义您的机构的用户属性

第一步是选择要使用的 Azure Active Directory 属性, 该属性将定义您的机构。 此属性将用于创建搜索权限筛选器, 该筛选器限制电子数据展示管理器仅搜索为该属性分配了特定值的用户的内容位置。 例如, 假设 Contoso 决定使用 "**部门**" 属性。 对于第四个咖啡店中的用户`FourthCoffee` , 此属性的值为, Coho Winery 子公司中的用户的值为。 `CohoWinery` 在步骤4中, 使用此`attribute:value`对 (例如, "*部门: FourthCoffee*") 限制电子数据展示管理器可以搜索的用户内容位置。 
  
以下是可用于合规性边界的 Azure Active Directory 用户属性的列表:
  
- Company
    
- CustomAttribute1 — CustomAttribute15
    
- 部门
    
- 办公室

- C (两个字母的国家/地区代码)
    
虽然更多的用户属性 (尤其是对于 Exchange 邮箱), 但上面列出的属性是 OneDrive 当前支持的那些属性。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>步骤 2: 为 Microsoft 支持文件提供将 user 属性同步到 OneDrive 帐户的请求

下一步是向 Microsoft 支持文件发出请求, 以将您在步骤1中选择的 Azure Active Directory 属性同步到组织中的所有 OneDrive 帐户。 在此同步发生之后, 您在步骤1中选择的属性 (及其值) 将映射到名为`ComplianceAttribute`的 SharePoint 中的隐藏托管属性。 您可以使用此属性在步骤4中创建 OneDrive 的搜索权限筛选器。
  
向 Microsoft 支持部门提交请求时, 请包含以下信息:
  
- Office 365 组织的默认域名
    
- Azure Active Directory 属性的名称 (从步骤 1)
    
- 支持请求的用途的以下标题或说明: "对合规性安全筛选器启用 OneDrive for Business 同步和 Azure Active Directory"。 这有助于将请求路由到将实现请求的 Office 365 电子数据展示工程团队。
    
在进行工程更改并将属性同步到 OneDrive 后, Microsoft 支持将向您发送所做更改的内部版本号以及估计的部署日期。 在提交支持请求后, 部署过程通常需要4–6周。
  
 **重要说明:** 您可以在部署更改之前完成步骤3到步骤5。 但在部署更改之前, 运行内容搜索不会返回在搜索权限筛选器中指定的 OneDrive 网站中的文档。 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>步骤 3: 为每个代理创建角色组

下一步是在安全 & 合规性中心中创建将与您的机构相一致的角色组。 我们建议您通过复制内置的电子数据展示管理器组, 添加适当的成员, 并删除可能不适用于您的需求的角色来创建角色组。 有关电子数据展示相关角色的详细信息, 请参阅[在 Office 365 安全 & 合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。
  
若要创建角色组, 请转到 Security & 合规性中心中的 "**权限**" 页, 并为每个要使用合规性边界和电子数据展示事例来管理调查的代理中的每个团队创建一个角色组。 
  
使用 Contoso 合规性边界方案, 需要创建四个角色组, 并向每个角色组添加适当的成员。
  
- 第四个咖啡电子数据展示管理器
    
- 第四个咖啡调查人员
    
- Coho Winery 电子数据展示管理器
    
- Coho Winery 调查人员
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>步骤 4: 创建搜索权限筛选器以强制实施合规性边界

为每个代理创建角色组后, 下一步是创建将每个角色组关联到其特定代理并定义合规性边界本身的搜索权限筛选器。 您需要为每个代理创建一个搜索权限筛选器。 有关创建安全权限筛选器的详细信息, 请参阅[Configure 权限筛选以进行内容搜索](permissions-filtering-for-content-search.md)。
  
下面是用于创建用于合规性边界的搜索权限筛选器的语法。

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```
  
以下是对命令中的每个参数的说明:
  
-  `FilterName`: 指定筛选器的名称。 使用描述或标识使用筛选器的机构的名称。 
    
-  `Users`: 指定将此筛选器应用于其执行的内容搜索操作的用户或组。 对于合规性边界, 此参数指定要在其上创建筛选器的代理中创建的角色组 (您在步骤3中创建的角色组)。 注意这是一个多值参数, 因此您可以包含一个或多个角色组, 以逗号分隔。 
    
-  `Filters`: 指定筛选器的搜索条件。 对于合规性边界, 请定义以下筛选器。 每个应用于一个内容位置。 
    
    -  `Mailbox`: 指定`Users`参数中定义的角色组可以搜索的邮箱。 对于合规性边界, *ComplianceAttribute*是您在步骤1和*AttributeValue*中标识的与指定机构相同的属性。 此筛选器允许角色组的成员仅搜索特定代理中的邮箱;例如, `"Mailbox_Department -eq 'FourthCoffee'"`。 
    
    -  `Site`: 指定`Users`参数中定义的角色组可以搜索的 OneDrive 帐户。 对于 OneDrive 筛选器, 请使用实际字符串`ComplianceAttribute`。 这将映射到您在步骤1中标识的相同属性, 并且由于您在步骤2中提交的支持请求而将其同步到 OneDrive 帐户。 *AttributeValue*指定代理。 此筛选器允许角色组的成员仅搜索特定代理中的 OneDrive 帐户;例如, `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。
    
    -  `Site_Path`: 指定`Users`参数中定义的角色组可以搜索的 SharePoint 网站。 *SharePointURL*指定角色组成员可以搜索的代理中的站点;例如, `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`请注意`Site` , `Site_Path`筛选器由 **-或**运算符连接。
    
     > [!NOTE]
     > `Filters`参数的语法包含*筛选器列表*。 筛选器列表是包含邮箱筛选器和使用逗号分隔的网站筛选器的筛选器列表。 在上面的示例中, 请注意, 逗号分隔**Mailbox_ComplianceAttribute**和**Site_ComplianceAttribute**: `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"`。 在运行内容搜索期间处理此筛选器时, 将从 "筛选器" 列表中创建两个搜索权限筛选器: 一个邮箱筛选器和一个网站筛选器。 使用筛选器列表的另一种方法是为每个代理创建两个单独的搜索权限筛选器: 针对邮箱属性的一个搜索权限筛选器和一个网站属性筛选器。 在这两种情况下, 结果都是相同的。 使用筛选器列表或创建单独的搜索权限筛选器是一个优先考虑事项。

-  `Action`: 指定应用筛选器的合规性搜索操作的类型。 例如, 仅`-Action Search`当`Users`参数中定义的角色组的成员运行内容搜索时, 才会应用筛选器。 在这种情况下, 导出搜索结果时不会应用筛选器。 对于合规性边界, `-Action All`请使用, 以便将筛选器应用于所有搜索操作。 
    
    有关内容搜索操作的列表, 请参阅[Configure 权限筛选 For Content search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)中的 "new-compliancesecurityfilter" 一节。

以下是两个搜索权限筛选器的示例, 将创建这些筛选器以支持 Contoso 合规性边界方案。 这两个示例都包含一个逗号分隔的筛选器列表, 其中邮箱和网站筛选器包含在相同的搜索权限筛选器中, 并用逗号分隔。
  
 **第四个咖啡**

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 **Coho Winery**

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>步骤 5: 为机构内调查创建电子数据展示案例

最后一步是在安全 & 合规中心中创建电子数据展示事例, 然后将您在步骤3中创建的角色组添加为事例的成员。 这将导致使用合规性边界的两个重要特征:
  
- 只有添加到此案例中的角色组的成员才能查看和访问安全 & 合规性中心中的案例。 例如, 如果第四个 "咖啡调查员" 角色组是事例的唯一成员, 则第四个 "电子数据展示管理者" 角色组的成员 (或任何其他角色组的成员) 将无法查看或访问该案例。
    
- 当分配给某个案例的角色组成员运行与该事例相关联的搜索时, 他们将只能搜索其代理 (由您在步骤4中创建的搜索权限筛选器定义) 中的内容位置。


若要创建事例并分配成员, 请执行以下操作:
    
1. 转到 Security & 合规中心中的**电子数据展示**页面, 并创建一个案例。 
    
2. 在电子数据展示事例的列表中, 单击您创建的事例的名称。
    
3. 在 "**管理此案例**" 弹出页面的 "**管理角色组**" ![下,](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)单击 "添加图标" "**添加**"。
    
    ![将角色组添加为电子数据展示事例的成员](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 在角色组列表中, 选择您在步骤3中创建的角色组之一, 然后单击 "**添加**"。
    
5. 单击 "**管理此案例**" 弹出控件上的 "**保存**" 以保存更改。 

## <a name="compliance-boundary-limitations"></a>合规性边界限制

在管理使用合规性边界的电子数据展示案例和调查时, 请牢记以下限制。
  
- 在创建和运行内容搜索时, 您可以选择代理外部的内容位置。 但是, 由于搜索权限筛选器, 搜索结果中不会包含这些位置的内容。
    
- 合规性边界不适用于电子数据展示事例中的保留。 这意味着一个机构中的电子数据展示管理器可以将用户置于处于保留状态的不同代理人中。 但是, 如果电子数据展示管理器搜索置于保留状态的用户的内容位置, 则将强制实施合规性边界。 这意味着, 电子数据展示管理器将无法搜索用户的内容位置, 即使他们能够将用户置于保留状态。
    
    此外, 保留统计信息将仅适用于代理中的内容位置。
    
- 搜索权限筛选器不适用于 Exchange 公用文件夹。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>在多地理位置环境中搜索和导出内容

搜索权限筛选器还使您可以控制内容的路由位置, 以及在[SharePoint 多地理位置环境](https://go.microsoft.com/fwlink/?linkid=860840)中搜索内容位置时可搜索的数据中心。
  
- **导出搜索结果:** 您可以从特定数据中心导出来自 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户的搜索结果。 这意味着您可以指定将从中导出搜索结果的数据中心位置。

    将**Region**参数用于**new-compliancesecurityfilter**或**new-compliancesecurityfilter** cmdlet, 以创建或更改导出将路由到的数据中心。
  
    |**参数值**|**数据中心位置**|
    |:-----|:-----|
    |NAM  <br/> |北美 (数据中心在美国)  <br/> |
    |EUR  <br/> |欧洲  <br/> |
    |APC  <br/> |亚太地区  <br/> |
    |CAN <br/> |加拿大|
    |||
    
- **路由内容搜索:** 您可以将 SharePoint 网站和 OneDrive 帐户的内容搜索路由到附属数据中心。 这意味着您可以指定将在其中运行搜索的数据中心位置。
    
    在**区域**参数值中使用以下值来控制在搜索 SharePoint 网站和 OneDrive 位置时, 将在哪个数据中心运行内容搜索。 
  
    |**参数值**|**SharePoint 的数据中心路由位置**|
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
    |||

   如果没有为搜索权限筛选器指定**Region**参数, 将搜索组织的默认 SharePoint 区域, 然后将搜索结果导出到最接近的数据中心。

> [!TIP]
> 为了简化概念,**区域**参数控制用于在 SharePoint 和 OneDrive 中搜索内容的数据中心。 这不适用于搜索 Exchange 中的内容, 因为 Exchange 内容搜索不受数据中心地理位置的约束。 此外, 相同的**区域**参数值还可能规定导出的数据中心已通过路由。 这通常需要控制跨地理位置的数据移动 boarders。<br/><br/>如果您使用的是高级电子数据展示, 则在 SharePoint 和 OneDrive 中搜索内容不受数据中心地理位置的约束。 有关高级电子数据展示的详细信息, 请参阅[Microsoft 365 中的高级电子数据展示解决方案概述](compliance20/overview-ediscovery-20.md)。

下面的示例展示了如何在为合规性边界创建搜索权限筛选器时使用**Region**参数。 这假定第四个咖啡子公司位于北美, 并且 Coho Winery 位于欧洲。 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
在多地理位置环境中搜索和导出内容时, 请记住以下事项。
  
- **Region**参数并不控制 Exchange 邮箱的搜索。 搜索邮箱时将搜索所有数据中心。 若要限制可以搜索的 Exchange 邮箱的作用域, 请在创建或更改搜索权限筛选器时使用**Filters**参数。 
    
- 如果电子数据展示管理器需要跨多个 SharePoint 区域进行搜索, 则需要为该电子数据展示管理器创建一个不同的用户帐户, 该用户帐户可在搜索权限筛选器中用于指定 SharePoint 的备用区域网站或 OneDrive 帐户位于。
    
- 在 SharePoint 和 OneDrive 中搜索内容时,**区域**参数会将搜索定向到电子数据展示管理器将在其中执行电子数据展示调查的主或卫星位置。 如果电子数据展示管理器在搜索权限筛选器中指定的区域之外搜索 SharePoint 和 OneDrive 网站, 则不会返回任何搜索结果。 
    
- 导出搜索结果时, 将会将所有内容位置的内容 (包括 Exchange、Skype for Business、SharePoint、OneDrive 和其他可以使用内容搜索工具搜索的 Office 365 服务) 上传到 Azure 存储位置由**Region**参数指定的数据中心。 这可帮助组织在合规性范围内不允许跨受控制的边框导出内容。 如果未在搜索权限筛选器中指定任何区域, 则会将内容上传到组织的默认区域。 
    
- 您可以通过运行以下命令来编辑现有搜索权限筛选器, 以添加或更改区域:

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a>常见问题

 **谁可以创建和管理搜索权限筛选器 (使用 New-compliancesecurityfilter 和 New-compliancesecurityfilter cmdlet)？**
  
若要创建、查看和修改搜索权限筛选器, 您必须是 Security & 合规性中心中的 "组织管理" 角色组的成员。
  
 **如果将电子数据展示管理器分配给跨多个代理的多个角色组, 如何在一个或多个代理中搜索内容？**
  
电子数据展示管理器可以向其搜索查询中添加参数, 以将搜索限制到特定的代理。 例如, 如果组织已将**CustomAttribute10**属性指定为区分机构, 则可以在搜索查询中追加以下内容, 以在特定机构中搜索邮箱和 OneDrive 帐户: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。
  
 **如果更改了用作搜索权限筛选器中的符合性属性的属性的值, 会发生什么情况？**
  
如果更改了筛选器中使用的属性的值, 搜索权限筛选器将花费最长三天的时间来强制实施符合性边界。 例如, 在 Contoso 方案中, 假设第四个咖啡店中的用户转移到 Coho Winery 机构。 因此, user 对象上的**部门**属性值从*FourthCoffee*更改为*CohoWinery*。 在这种情况下, 第四个咖啡电子数据展示和投资者将在属性更改后的三天内为该用户获取搜索结果。 同样, 在 Coho Winery 电子数据展示管理人员和调查人员获取用户的搜索结果之前, 最长需要三天。 
  
 **电子数据展示管理器能否从两个单独的合规性边界中查看内容？**
  
是。 为此, 可以将用户添加到对这两个机构都可见的角色组。
  
 **搜索权限筛选器是否适用于电子数据展示事例保留、Office 365 保留策略或 DLP？**
  
否, 目前没有。
  
 **如果我指定一个区域来控制导出内容的位置, 但我在该区域没有 SharePoint 组织, 是否仍可以搜索 SharePoint？**
  
如果在搜索权限筛选器中指定的区域在您的组织中不存在, 则将搜索默认区域。
  
 **在组织中可以创建的搜索权限筛选器的最大数目是多少？**
  
对于可以在组织中创建的搜索权限筛选器的数量没有限制。 但是, 当搜索权限筛选器超过100个时, 搜索性能将受到影响。 若要尽可能缩小组织中的搜索权限筛选器的数量, 请创建筛选器, 以便尽可能将 Exchange、SharePoint 和 OneDrive 的规则合并到单个搜索权限筛选器中。
