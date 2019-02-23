---
title: 设计独立 SharePoint Online 团队网站
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
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216152"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="c4751-103">设计独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="c4751-103">Design an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="c4751-104">**摘要:** 逐步完成独立的 SharePoint Online 团队网站的设计过程。</span><span class="sxs-lookup"><span data-stu-id="c4751-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="c4751-105">本文将指导您完成在创建独立的 SharePoint Online 团队网站之前必须做出的关键设计决策。</span><span class="sxs-lookup"><span data-stu-id="c4751-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>
  
## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="c4751-106">第1阶段: 确定您的 SharePoint 组和权限级别</span><span class="sxs-lookup"><span data-stu-id="c4751-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="c4751-107">默认情况下, 每个 sharepoint Online 团队网站都使用以下 SharePoint 组创建:</span><span class="sxs-lookup"><span data-stu-id="c4751-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>
  
- <span data-ttu-id="c4751-108">\<网站 name> 成员</span><span class="sxs-lookup"><span data-stu-id="c4751-108">\<site name> Members</span></span>
    
- <span data-ttu-id="c4751-109">\<网站 name> 访问者</span><span class="sxs-lookup"><span data-stu-id="c4751-109">\<site name> Visitors</span></span>
    
- <span data-ttu-id="c4751-110">\<网站 name> 所有者</span><span class="sxs-lookup"><span data-stu-id="c4751-110">\<site name> Owners</span></span>
    
<span data-ttu-id="c4751-111">这些组与 Office 365 和 Azure Active Directory (AD) 组是分开的, 并且是为网站资源分配权限的基础。</span><span class="sxs-lookup"><span data-stu-id="c4751-111">These groups are separate from Office 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>
  
<span data-ttu-id="c4751-p101">确定 SharePoint 组成员在网站中可执行的操作的特定权限集是权限级别。默认情况下, SharePoint Online 团队网站具有三个权限级别: "编辑"、"读取" 和 "完全控制"。下表显示了 SharePoint 组和分配的权限级别的默认关联:</span><span class="sxs-lookup"><span data-stu-id="c4751-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>
  
|<span data-ttu-id="c4751-115">**SharePoint 组**</span><span class="sxs-lookup"><span data-stu-id="c4751-115">**SharePoint group**</span></span>|<span data-ttu-id="c4751-116">**权限级别**</span><span class="sxs-lookup"><span data-stu-id="c4751-116">**Permission level**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c4751-117">\<网站 name> 成员</span><span class="sxs-lookup"><span data-stu-id="c4751-117">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c4751-118">编辑</span><span class="sxs-lookup"><span data-stu-id="c4751-118">Edit</span></span>  <br/> |
|<span data-ttu-id="c4751-119">\<网站 name> 访问者</span><span class="sxs-lookup"><span data-stu-id="c4751-119">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c4751-120">读取</span><span class="sxs-lookup"><span data-stu-id="c4751-120">Read</span></span>  <br/> |
|<span data-ttu-id="c4751-121">\<网站 name> 所有者</span><span class="sxs-lookup"><span data-stu-id="c4751-121">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c4751-122">完全控制</span><span class="sxs-lookup"><span data-stu-id="c4751-122">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c4751-p102">**最佳实践:** 您可以创建其他 SharePoint 组和权限级别。但是, 我们建议使用独立 sharepoint Online 网站的默认 SharePoint 组和权限级别。</span><span class="sxs-lookup"><span data-stu-id="c4751-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>
  
<span data-ttu-id="c4751-125">下面是默认的 SharePoint 组和权限级别。</span><span class="sxs-lookup"><span data-stu-id="c4751-125">Here are the default SharePoint groups and permission levels.</span></span>
  
![SharePoint Online 网站的默认 SharePoint 组和权限级别。](media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)
  
## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="c4751-127">第2阶段: 将权限分配给具有访问组的用户</span><span class="sxs-lookup"><span data-stu-id="c4751-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="c4751-p103">您可以通过将用户帐户或用户帐户所属的 Office 365 或 Azure AD 组添加到 SharePoint 组, 向用户分配权限。添加后, 通过 office 365 或 Azure AD 组中的成员身份直接或间接分配的 office 365 用户帐户将被分配与 SharePoint 组相关联的权限级别。</span><span class="sxs-lookup"><span data-stu-id="c4751-p103">You can assign permissions to users by adding their user account, or an Office 365 or Azure AD group of which the user account is a member, to the SharePoint groups. Once added, the Office 365 user accounts, either directly or indirectly via membership in an Office 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>
  
<span data-ttu-id="c4751-130">使用默认 SharePoint 组作为示例:</span><span class="sxs-lookup"><span data-stu-id="c4751-130">Using the default SharePoint groups as an example:</span></span>
  
- <span data-ttu-id="c4751-131">" \*\* \<网站 name> 成员**" SharePoint 组 (可包含用户帐户和组) 的成员被分配到 "**编辑\*\*" 权限级别</span><span class="sxs-lookup"><span data-stu-id="c4751-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>
    
- <span data-ttu-id="c4751-132">" \*\* \<网站 name> 访问者**" SharePoint 组的成员 (可包含用户帐户和组) 被分配有 "**读取\*\*" 权限级别</span><span class="sxs-lookup"><span data-stu-id="c4751-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>
    
- <span data-ttu-id="c4751-133">网站 name> 所有者的成员 SharePoint 组 (可包含用户帐户和组) 被分配了 "**完全控制**" 权限级别\*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="c4751-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>
    
 <span data-ttu-id="c4751-p104">**最佳实践:** 虽然您可以通过单个用户帐户管理权限, 但我们建议您改用一个 Azure AD 组 (称为 "访问组")。这简化了通过访问组中的成员资格管理权限, 而不是管理每个 SharePoint 组的用户帐户列表。</span><span class="sxs-lookup"><span data-stu-id="c4751-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>
  
<span data-ttu-id="c4751-p105">office 365 的 Azure AD 组与 office 365 组不同。Azure AD 组显示在 Office 管理中心中, 其**类型**设置为 "**安全性**", 并且没有电子邮件地址。可以在以下范围内管理 Azure AD 组:</span><span class="sxs-lookup"><span data-stu-id="c4751-p105">Azure AD groups for Office 365 are different than Office 365 groups. Azure AD groups appear in the Office Admin center with their **Type** set to **Security** and do not have an email address. Azure AD groups can be managed within:</span></span>
  
- <span data-ttu-id="c4751-139">Windows Server Active Directory (AD)</span><span class="sxs-lookup"><span data-stu-id="c4751-139">Windows Server Active Directory (AD)</span></span>
    
    <span data-ttu-id="c4751-p106">这些组是在本地 Windows Server AD 基础结构中创建并同步到 Office 365 订阅的组。在 Office 管理中心中, 这些组的**状态**为 "已**与 active directory 同步**"。</span><span class="sxs-lookup"><span data-stu-id="c4751-p106">These are groups that have been created in your on-premises Windows Server AD infrastructure and synchronized to your Office 365 subscription. In the Office Admin center, these groups have a **Status** of **Synched with active directory**.</span></span>
    
- <span data-ttu-id="c4751-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="c4751-142">Office 365</span></span>
    
    <span data-ttu-id="c4751-p107">这些组是使用 Office 管理中心、Azure 门户或 Microsoft PowerShell 创建的组。在 Office 管理中心中, 这些组的**状态**为**云**。</span><span class="sxs-lookup"><span data-stu-id="c4751-p107">These are groups that have been created using either the Office Admin center, the Azure portal, or Microsoft PowerShell. In the Office Admin center, these groups have a **Status** of **Cloud**.</span></span>
    
 <span data-ttu-id="c4751-145">**最佳实践:** 如果使用的是本地 Windows server AD 并与 Office 365 订阅同步, 请使用 Windows Server ad 执行用户和组管理。</span><span class="sxs-lookup"><span data-stu-id="c4751-145">**Best practice:** If you are using Windows Server AD on-premises and synchronizing with your Office 365 subscription, perform your user and group management with Windows Server AD.</span></span>
  
<span data-ttu-id="c4751-146">对于独立的 SharePoint Online 团队网站, 建议的组结构如下所示:</span><span class="sxs-lookup"><span data-stu-id="c4751-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>
  
|<span data-ttu-id="c4751-147">**SharePoint 组**</span><span class="sxs-lookup"><span data-stu-id="c4751-147">**SharePoint group**</span></span>|<span data-ttu-id="c4751-148">**基于 Azure AD 的访问组**</span><span class="sxs-lookup"><span data-stu-id="c4751-148">**Azure AD-based access group**</span></span>|<span data-ttu-id="c4751-149">**权限级别**</span><span class="sxs-lookup"><span data-stu-id="c4751-149">**Permission level**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4751-150">\<网站 name> 成员</span><span class="sxs-lookup"><span data-stu-id="c4751-150">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c4751-151">\<网站 name> 成员</span><span class="sxs-lookup"><span data-stu-id="c4751-151">\<site name> Members</span></span>  <br/> |<span data-ttu-id="c4751-152">编辑</span><span class="sxs-lookup"><span data-stu-id="c4751-152">Edit</span></span>  <br/> |
|<span data-ttu-id="c4751-153">\<网站 name> 访问者</span><span class="sxs-lookup"><span data-stu-id="c4751-153">\<site name> Visitors</span></span>  <br/> |<span data-ttu-id="c4751-154">\<网站 name> 查看者</span><span class="sxs-lookup"><span data-stu-id="c4751-154">\<site name> Viewers</span></span>  <br/> |<span data-ttu-id="c4751-155">读取</span><span class="sxs-lookup"><span data-stu-id="c4751-155">Read</span></span>  <br/> |
|<span data-ttu-id="c4751-156">\<网站 name> 所有者</span><span class="sxs-lookup"><span data-stu-id="c4751-156">\<site name> Owners</span></span>  <br/> |<span data-ttu-id="c4751-157">\<网站 name> 管理员</span><span class="sxs-lookup"><span data-stu-id="c4751-157">\<site name> Admins</span></span>  <br/> |<span data-ttu-id="c4751-158">完全控制</span><span class="sxs-lookup"><span data-stu-id="c4751-158">Full control</span></span>  <br/> |
   
 <span data-ttu-id="c4751-p108">**最佳实践:** 虽然您可以使用 Office 365 或 Azure AD 组作为 SharePoint 组的成员, 但我们建议使用 Azure ad 组。Azure AD 组通过 Windows Server AD 或 Office 365 进行管理, 使您可以更灵活地使用嵌套组来分配权限。</span><span class="sxs-lookup"><span data-stu-id="c4751-p108">**Best practice:** Although you can use either Office 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups. Azure AD groups, managed either through Windows Server AD or Office 365, give you more flexibility to use nested groups to assign permissions.</span></span>
  
<span data-ttu-id="c4751-161">下面是配置为使用基于 Azure AD 的访问组的默认 SharePoint 组。</span><span class="sxs-lookup"><span data-stu-id="c4751-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>
  
![将访问组用作默认 SharePoint Online 网站用户组的成员。](media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)
  
<span data-ttu-id="c4751-163">在设计三个访问组时, 请记住以下几点:</span><span class="sxs-lookup"><span data-stu-id="c4751-163">When designing the three access groups, keep the following in mind:</span></span>
  
- <span data-ttu-id="c4751-164">site name> Admins access 组中应该只有少数成员, 这些成员对应于管理团队网站的少数 SharePoint Online 管理员。 \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="c4751-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>
    
- <span data-ttu-id="c4751-p109">大多数网站成员都位于\*\* \<网站 name> 成员**或** \<网站 name> 查看**器访问组中。由于** \<site name> members\*\* access 组中的网站成员能够删除或修改网站中的资源, 因此请仔细考虑其成员资格。如果不确定, 请将网站成员添加到\*\* \<网站 name> 查看者\*\*访问组。</span><span class="sxs-lookup"><span data-stu-id="c4751-p109">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups. Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership. When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>
    
<span data-ttu-id="c4751-168">下面的示例展示了名为 ProjectX 的独立网站的 SharePoint 组和访问组。</span><span class="sxs-lookup"><span data-stu-id="c4751-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>
  
![对名为 ProjectX 的 SharePoint Online 网站使用访问组的示例。](media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)
  
## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="c4751-170">第3阶段: 使用嵌套的 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="c4751-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="c4751-p110">对于限制为少数用户的项目, 向网站的 SharePoint 组添加的基于 Azure AD 的访问组的单个级别将适合大多数场景。但是, 如果您的人员数量很多, 并且这些人已经是已建立的 Azure AD 组的成员, 则可以通过使用嵌套组或包含其他组作为成员的组来更轻松地分配 SharePoint 权限。</span><span class="sxs-lookup"><span data-stu-id="c4751-p110">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios. However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>
  
<span data-ttu-id="c4751-p111">例如, 您想要创建独立的 SharePoint online 团队网站, 以便在销售、市场营销、工程、法律和支持部门的执行官之间进行协作, 这些部门已经有了拥有行政用户帐户的自己的组所属.而不是为新网站成员创建一个新组, 并在其中放置所有单个执行人员的用户帐户, 为新组中的每个部门放置现有管理组。</span><span class="sxs-lookup"><span data-stu-id="c4751-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>
  
 <span data-ttu-id="c4751-p112">如果您在多个组织之间共享 Office 365 订阅, 则组织的独立网站的单个级别的组成员身份可能因用户帐户数量的巨大而受到很大的管理。在这种情况下, 您可以对包含组织内的组的每个组织使用嵌套的 Azure AD 组来管理权限。</span><span class="sxs-lookup"><span data-stu-id="c4751-p112">If you are sharing an Office 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts. In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>
  
<span data-ttu-id="c4751-177">要使用嵌套的 Azure AD 组, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c4751-177">To use nested Azure AD groups:</span></span>
  
1. <span data-ttu-id="c4751-178">标识或创建将包含用户帐户的 Azure AD 组, 并将相应的用户帐户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c4751-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>
    
2. <span data-ttu-id="c4751-179">创建将包含其他 azure ad 组的基于 Azure ad 的容器访问组, 并将这些组添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c4751-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>
    
3.  <span data-ttu-id="c4751-180">若要获取容器访问组的适当级别的访问权限, 请标识 SharePoint 组和相应的权限级别。</span><span class="sxs-lookup"><span data-stu-id="c4751-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4751-181">您不能使用嵌套的 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="c4751-181">You cannot use nested Office 365 groups.</span></span> 
  
<span data-ttu-id="c4751-182">下面是 ProjectX 成员访问组的嵌套 Azure AD 组的示例。</span><span class="sxs-lookup"><span data-stu-id="c4751-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>
  
![对 ProjectX 网站的成员访问组使用嵌套访问组的示例。](media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)
  
<span data-ttu-id="c4751-184">由于研究、工程和项目领导团队中的所有用户帐户都打算成为网站成员, 因此将其 Azure AD 组添加到 ProjectX 成员访问组中会更加简单。</span><span class="sxs-lookup"><span data-stu-id="c4751-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c4751-185">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4751-185">Next step</span></span>

<span data-ttu-id="c4751-186">当您准备好在生产中创建和配置独立网站时, 请参阅[部署独立的 SharePoint Online 团队网站](deploy-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="c4751-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4751-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4751-187">See Also</span></span>

[<span data-ttu-id="c4751-188">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="c4751-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="c4751-189">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="c4751-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="c4751-190">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="c4751-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



