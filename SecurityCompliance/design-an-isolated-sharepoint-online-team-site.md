---
title: 设计独立的 SharePoint Online 团队网站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: '摘要: 逐步完成独立的 SharePoint Online 团队网站的设计过程。'
ms.openlocfilehash: 09748fcc22a4a48efc4346ff75a225db612a0ef4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257147"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a>设计独立的 SharePoint Online 团队网站

 **摘要:** 逐步完成独立的 SharePoint Online 团队网站的设计过程。
  
本文将指导您完成在创建独立的 SharePoint Online 团队网站之前必须做出的关键设计决策。
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a>第1阶段: 确定您的 SharePoint 组和权限级别

默认情况下, 每个 sharepoint Online 团队网站都使用以下 SharePoint 组创建:
  
- \<网站 name> 成员
    
- \<网站 name> 访问者
    
- \<网站 name> 所有者
    
这些组与 Office 365 和 Azure Active Directory (AD) 组是分开的, 并且是为网站资源分配权限的基础。
  
确定 SharePoint 组成员在网站中可执行的操作的特定权限集是权限级别。 默认情况下, SharePoint Online 团队网站具有三个权限级别: "编辑"、"读取" 和 "完全控制"。 下表显示了 SharePoint 组和分配的权限级别的默认关联:
  
|**SharePoint 组**|**权限级别**|
|:-----|:-----|
|\<网站 name> 成员  <br/> |编辑  <br/> |
|\<网站 name> 访问者  <br/> |读取  <br/> |
|\<网站 name> 所有者  <br/> |完全控制  <br/> |
   
 **最佳实践:** 您可以创建其他 SharePoint 组和权限级别。 但是, 我们建议使用独立 sharepoint Online 网站的默认 SharePoint 组和权限级别。
  
下面是默认的 SharePoint 组和权限级别。
  
![sharepoint Online 网站的默认 sharepoint 组和权限级别。](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a>第2阶段: 将权限分配给具有访问组的用户

您可以通过将用户帐户或用户帐户所属的 Office 365 或 Azure AD 组添加到 SharePoint 组, 向用户分配权限。 添加后, 通过 office 365 或 Azure AD 组中的成员身份直接或间接分配的 office 365 用户帐户将被分配与 SharePoint 组相关联的权限级别。
  
使用默认 SharePoint 组作为示例:
  
- " ** \<网站 name> 成员**" SharePoint 组 (可包含用户帐户和组) 的成员被分配到 "**编辑**" 权限级别
    
- " ** \<网站 name> 访问者**" SharePoint 组的成员 (可包含用户帐户和组) 被分配有 "**读取**" 权限级别
    
- 网站 name> 所有者的成员 SharePoint 组 (可包含用户帐户和组) 被分配了 "**完全控制**" 权限级别** \<**
    
 **最佳实践:** 虽然您可以通过单个用户帐户管理权限, 但我们建议您改用一个 Azure AD 组 (称为 "访问组")。 这简化了通过访问组中的成员资格管理权限, 而不是管理每个 SharePoint 组的用户帐户列表。
  
office 365 的 Azure AD 组与 office 365 组不同。 Azure AD 组显示在 Office 管理中心中, 其**类型**设置为 "**安全性**", 并且没有电子邮件地址。 可以在以下范围内管理 Azure AD 组:
  
- Windows Server Active Directory (AD)
    
    这些组是在本地 Windows Server AD 基础结构中创建并同步到 Office 365 订阅的组。 在 Office 管理中心中, 这些组的**状态**为 "已**与 active directory 同步**"。
    
- Office 365
    
    这些组是使用 Office 管理中心、Azure 门户或 Microsoft PowerShell 创建的组。 在 Office 管理中心中, 这些组的**状态**为**云**。
    
 **最佳实践:** 如果使用的是本地 Windows server AD 并与 Office 365 订阅同步, 请使用 Windows Server ad 执行用户和组管理。
  
对于独立的 SharePoint Online 团队网站, 建议的组结构如下所示:
  
|**SharePoint 组**|**基于 Azure AD 的访问组**|**权限级别**|
|:-----|:-----|:-----|
|\<网站 name> 成员  <br/> |\<网站 name> 成员  <br/> |编辑  <br/> |
|\<网站 name> 访问者  <br/> |\<网站 name> 查看者  <br/> |读取  <br/> |
|\<网站 name> 所有者  <br/> |\<网站 name> 管理员  <br/> |完全控制  <br/> |
   
 **最佳实践:** 虽然您可以使用 Office 365 或 Azure AD 组作为 SharePoint 组的成员, 但我们建议使用 Azure ad 组。 Azure AD 组通过 Windows Server AD 或 Office 365 进行管理, 使您可以更灵活地使用嵌套组来分配权限。
  
下面是配置为使用基于 Azure AD 的访问组的默认 SharePoint 组。
  
![使用访问组作为默认 SharePoint Online 网站组的成员。](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
在设计三个访问组时, 请记住以下几点:
  
- site name> Admins access 组中应该只有少数成员, 这些成员对应于管理团队网站的少数 SharePoint Online 管理员。 ** \<**
    
- 大多数网站成员都位于** \<网站 name> 成员**或** \<网站 name> 查看**器访问组中。 由于** \<site name> members** access 组中的网站成员能够删除或修改网站中的资源, 因此请仔细考虑其成员资格。 如果不确定, 请将网站成员添加到** \<网站 name> 查看者**访问组。
    
下面的示例展示了名为 ProjectX 的独立网站的 SharePoint 组和访问组。
  
![使用名为 ProjectX 的 SharePoint Online 网站的访问组的示例。](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a>第3阶段: 使用嵌套的 Azure AD 组

对于限制为少数用户的项目, 向网站的 SharePoint 组添加的基于 Azure AD 的访问组的单个级别将适合大多数场景。 但是, 如果您的人员数量很多, 并且这些人已经是已建立的 Azure AD 组的成员, 则可以通过使用嵌套组或包含其他组作为成员的组来更轻松地分配 SharePoint 权限。
  
例如, 您想要创建独立的 SharePoint online 团队网站, 以便在销售、市场营销、工程、法律和支持部门的执行官之间进行协作, 这些部门已经有了拥有行政用户帐户的自己的组所属. 而不是为新网站成员创建一个新组, 并在其中放置所有单个执行人员的用户帐户, 为新组中的每个部门放置现有管理组。
  
 如果您在多个组织之间共享 Office 365 订阅, 则组织的独立网站的单个级别的组成员身份可能因用户帐户数量的巨大而受到很大的管理。 在这种情况下, 您可以对包含组织内的组的每个组织使用嵌套的 Azure AD 组来管理权限。
  
要使用嵌套的 Azure AD 组, 请执行以下操作:
  
1. 标识或创建将包含用户帐户的 Azure AD 组, 并将相应的用户帐户添加为成员。
    
2. 创建将包含其他 azure ad 组的基于 Azure ad 的容器访问组, 并将这些组添加为成员。
    
3.  若要获取容器访问组的适当级别的访问权限, 请标识 SharePoint 组和相应的权限级别。
    
> [!NOTE]
> 您不能使用嵌套的 Office 365 组。 
  
下面是 ProjectX 成员访问组的嵌套 Azure AD 组的示例。
  
![对 ProjectX 网站的成员访问组使用嵌套访问组的示例。](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
由于研究、工程和项目领导团队中的所有用户帐户都打算成为网站成员, 因此将其 Azure AD 组添加到 ProjectX 成员访问组中会更加简单。
  
## <a name="next-step"></a>后续步骤

当您准备好在生产中创建和配置独立网站时, 请参阅[部署独立的 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)。
  
## <a name="see-also"></a>另请参阅

[独立 SharePoint Online 团队网站](isolated-sharepoint-online-team-sites.md)
  
[管理独立 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)

[部署独立 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)



