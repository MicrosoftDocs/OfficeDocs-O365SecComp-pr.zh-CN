---
title: 分配 Office 365 安全性的电子数据展示权限&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: 分配所需执行电子数据展示相关的任务使用安全权限&amp;合规性中心。
ms.openlocfilehash: 95f0ed171c37ec84ca8bb8f00e69ab0318cd31cd
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29741155"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="af106-103">分配 Office 365 安全性的电子数据展示权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="af106-103">Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="af106-p101">如果您希望他人在 Office 365 安全性中使用的任何电子数据展示相关工具&amp;合规性中心，您必须将其分配适当的权限。执行此操作的最简单方式是将此人的适当的角色组添加 Office 365 安全中的**权限**页上&amp;合规性中心。本主题介绍执行电子数据展示相关的任务使用安全所需的权限&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="af106-p101">If you want people to use any of the eDiscovery-related tools in the Office 365 Security &amp; Compliance Center, you have to assign them the appropriate permissions. The easiest way to do this is to add the person the appropriate role group on the **Permissions** page in the Office 365 Security &amp; Compliance Center. This topic describes the permissions required to perform eDiscovery-related tasks using the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="af106-p102">在安全的电子数据展示相关的主要角色组&amp;合规性中心称为**电子数据展示管理器**。有此角色组中的两个组子组。</span><span class="sxs-lookup"><span data-stu-id="af106-p102">The primary eDiscovery-related role group in Security &amp; Compliance Center is called **eDiscovery Manager**. There are two subgroups within this role group.</span></span> 
  
- <span data-ttu-id="af106-p103">**电子数据展示管理员**的电子数据展示管理员可以使用内容搜索工具中安全&amp;，在组织搜索内容的位置和执行各种与搜索相关的操作，如预览和导出搜索的合规性中心结果。成员可以还创建和管理电子数据展示事例、 添加和删除成员为大写、 创建案例保留项，并运行的情况下和 Office 365 高级电子数据展示中的访问案例数据相关联的内容搜索。 电子数据展示管理员只能访问和管理他们创建的用例。不能访问或管理由其他电子数据展示管理员创建的案例。</span><span class="sxs-lookup"><span data-stu-id="af106-p103">**eDiscovery Managers** - An eDiscovery Manager can use the Content Search tool in the Security &amp; Compliance Center to search content locations in the organization, and perform various search-related actions such as preview and export search results. Members can also create and manage eDiscovery cases, add and remove members to a case, create case holds, and run Content Searches associated with a case, and access case data in Office 365 Advanced eDiscovery.  An eDiscovery Managers can only access and manage the cases they create. They can't access or manage cases created by other eDiscovery Managers.</span></span> 
    
- <span data-ttu-id="af106-p104">**电子数据展示管理员**的电子数据展示管理员电子数据展示管理员角色组的成员，可执行的相同内容的搜索和电子数据展示管理员可以执行的案例管理相关的任务。此外，电子数据展示管理员可以：</span><span class="sxs-lookup"><span data-stu-id="af106-p104">**eDiscovery Administrators** - An eDiscovery Administrator is a member of the eDiscovery Manager role group, and can perform the same Content Search and case management-related tasks that an eDiscovery Manager can perform. Additionally, an eDiscovery Administrator can:</span></span> 
    
  - <span data-ttu-id="af106-115">访问所有的情况下，安全中**电子数据展示事例**上列出的&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="af106-115">Access all cases that are listed on the **eDiscovery cases** page in the Security &amp; Compliance Center.</span></span> 

  - <span data-ttu-id="af106-116">访问案例的组织中任何情况下的高级电子数据展示中的数据。</span><span class="sxs-lookup"><span data-stu-id="af106-116">Access case data in Advanced eDiscovery for any case in the organization.</span></span>
    
  - <span data-ttu-id="af106-117">将自己添加为任何电子数据展示事例的成员后管理这些事例。</span><span class="sxs-lookup"><span data-stu-id="af106-117">Manage any eDiscovery case after they add themself as a member of the case.</span></span>
  
  <span data-ttu-id="af106-118">出于为什么您可能希望在组织中的电子数据展示管理员，请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="af106-118">See the [More information](#more-information) section for reasons why you might want eDiscovery Administrators in your organization.</span></span> 

> [!NOTE]
> <span data-ttu-id="af106-p105">若要分析使用高级电子数据展示的用户的数据，用户 (数据的 custodian) 必须分配的 Office 365 E5 许可证。此外，可使用 Office 365 E1 或 E3 许可证的用户分配的高级电子数据展示独立许可证。管理员和合规部主管分配给情况下，并使用高级电子数据展示以分析数据不需要 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="af106-p105">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="af106-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="af106-122">Before you begin</span></span>

- <span data-ttu-id="af106-123">您必须是组织管理角色组的成员 （或分配的角色管理角色） 分配安全中的电子数据展示权限&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="af106-123">You have to be a member of the Organization Management role group (or be assigned the Role Management role) to assign eDiscovery permissions in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="af106-p106">您可以使用[Add-rolegroupmember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) cmdlet 中安全&amp;合规性中心 PowerShell，可以将已启用邮件的安全组添加为电子数据展示管理员角色组中的电子数据展示管理员子组的成员。但是，您不能将已启用邮件的安全组添加到电子数据展示管理员组子组。请参阅[详细信息](#more-information)部分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af106-p106">You can use the [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) cmdlet in Security &amp; Compliance Center PowerShell to add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group. However, you can't add a mail-enabled security group to the eDiscovery Administrators subgroup. See the [More information](#more-information) section for more details.</span></span> 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a><span data-ttu-id="af106-127">分配安全中的电子数据展示权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="af106-127">Assign eDiscovery permissions in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="af106-128">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="af106-128">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="af106-129">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="af106-129">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="af106-130">在左侧窗格中的安全&amp;合规性中心，单击**权限**，然后单击**电子数据展示管理器**旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="af106-130">In the left pane of the Security &amp; Compliance Center, click **Permissions**, and then click the checkbox next to **eDiscovery Manager**.</span></span>
    
4. <span data-ttu-id="af106-131">在**电子数据展示管理器**弹出页上，执行下列操作之一基于您想要分配的电子数据展示权限。</span><span class="sxs-lookup"><span data-stu-id="af106-131">On the **eDiscovery Manager** flyout page, do one of the following based on the eDiscovery permissions that you want to assign.</span></span> 
    
  - <span data-ttu-id="af106-p107">**若要将某个用户设置电子数据展示中管理器**旁边**电子数据展示管理器**中，单击**编辑**。在**所选电子数据展示管理员**，单击**编辑**，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)**添加**。选择 （或多个用户） 要添加为电子数据展示管理器中，然后单击**添加**。完成添加用户时，单击**完成**。然后，在**编辑选择的电子数据展示管理器**弹出页上，单击**保存**以保存所做的更改对电子数据展示管理器的成员身份。</span><span class="sxs-lookup"><span data-stu-id="af106-p107">**To make a user an eDiscovery Manager** Next to **eDiscovery Manager**, click **Edit**. Under **Selected eDiscovery Managers**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery manager, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Manager** flyout page, click **Save** to save the changes to the eDiscovery Manager membership.</span></span> 
    
  - <span data-ttu-id="af106-p108">**若要将某个用户设置电子数据展示管理员\*\*\*\*电子数据展示管理员**，旁边单击**编辑**。在**所选电子数据展示管理员**，单击**编辑**，然后单击![添加图标](media/ITPro-EAC-AddIcon.gif)**添加**。选择 （或多个用户） 要添加为电子数据展示管理员，然后单击**添加**。完成添加用户时，单击**完成**。然后，在**编辑选择的电子数据展示管理员**弹出页上，单击**保存**以保存对电子数据展示管理员成员资格的更改。</span><span class="sxs-lookup"><span data-stu-id="af106-p108">**To make a user an eDiscovery Administrator** Next to **eDiscovery Administrator**, click **Edit**. Under **Selected eDiscovery Administrators**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery Administrator, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Administrator** flyout page, click **Save** to save the changes to the eDiscovery Administrator membership.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="af106-p109">您可以使用**添加 eDiscoveryCaseAdmin** cmdlet 来使电子数据展示管理员的用户。但是，用户必须分配案例管理角色才能使用此 cmdlet 以确保它们电子数据展示管理员。有关详细信息，请参阅[添加 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)。</span><span class="sxs-lookup"><span data-stu-id="af106-p109">You can also use the **Add-eDiscoveryCaseAdmin** cmdlet to make a user an eDiscovery Administrator. However, the user must be assigned the Case Management role before you can use this cmdlet to make them an eDiscovery Administrator. For more information, see [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217).</span></span> 
  
<span data-ttu-id="af106-p110">安全中的**权限**页上&amp;合规性中心，您还可以分配用户电子数据展示相关权限，通过将它们添加到合规性管理员、 组织管理和审阅者角色组。电子数据展示相关的 RBAC 角色分配给每个角色组的说明，请参阅[RBAC 角色相关的电子数据展示](#rbac-roles-related-to-ediscovery)部分。</span><span class="sxs-lookup"><span data-stu-id="af106-p110">On the **Permissions** page in the Security &amp; Compliance Center, you can also assign users eDiscovery-related permissions, by adding them to the Compliance Administrator, Organization Management, and Reviewer role groups. For a description of the eDiscovery-related RBAC roles assigned to each of these role groups, see the [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery) section.</span></span> 

## <a name="rbac-roles-related-to-ediscovery"></a><span data-ttu-id="af106-147">RBAC 角色相关的电子数据展示</span><span class="sxs-lookup"><span data-stu-id="af106-147">RBAC roles related to eDiscovery</span></span>

<span data-ttu-id="af106-148">下表列出了安全 & 合规性中心中的电子数据展示相关 RBAC 角色，并指示的内置角色组的每个角色分配给默认情况下。</span><span class="sxs-lookup"><span data-stu-id="af106-148">The following table lists the eDiscovery-related RBAC roles in the Security & Compliance Center, and indicates the built-in role groups that each role is assigned to by default.</span></span> 
    
|<span data-ttu-id="af106-149">**角色**</span><span class="sxs-lookup"><span data-stu-id="af106-149">**Role**</span></span>|<span data-ttu-id="af106-150">**合规性管理员**</span><span class="sxs-lookup"><span data-stu-id="af106-150">**Compliance Administrator**</span></span>|<span data-ttu-id="af106-151">**电子数据展示管理器 & 管理员**</span><span class="sxs-lookup"><span data-stu-id="af106-151">**eDiscovery Manager & Administrator**</span></span>|<span data-ttu-id="af106-152">**组织管理**</span><span class="sxs-lookup"><span data-stu-id="af106-152">**Organization Management**</span></span>|<span data-ttu-id="af106-153">**Reviewer**</span><span class="sxs-lookup"><span data-stu-id="af106-153">**Reviewer**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="af106-154">案例管理</span><span class="sxs-lookup"><span data-stu-id="af106-154">Case Management</span></span> <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="af106-158">合规性搜索</span><span class="sxs-lookup"><span data-stu-id="af106-158">Compliance Search</span></span> <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="af106-162">导出</span><span class="sxs-lookup"><span data-stu-id="af106-162">Export</span></span> <br/> | <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="af106-164">保留</span><span class="sxs-lookup"><span data-stu-id="af106-164">Hold</span></span> <br/>  |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="af106-168">预览</span><span class="sxs-lookup"><span data-stu-id="af106-168">Preview</span></span> <br/>  | <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="af106-170">审查</span><span class="sxs-lookup"><span data-stu-id="af106-170">Review</span></span> <br/>  | <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|<span data-ttu-id="af106-173">RMS 解密</span><span class="sxs-lookup"><span data-stu-id="af106-173">RMS Decrypt</span></span> <br/>  ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|<span data-ttu-id="af106-175">搜索和清除</span><span class="sxs-lookup"><span data-stu-id="af106-175">Search And Purge</span></span> <br/> | <br/> | <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
<span data-ttu-id="af106-177">以下各节介绍了每个电子数据展示相关 RBAC 角色上表中列出。</span><span class="sxs-lookup"><span data-stu-id="af106-177">The following sections describe each of the eDiscovery-related RBAC roles listed in the previous table.</span></span>

### <a name="case-management"></a><span data-ttu-id="af106-178">案例管理</span><span class="sxs-lookup"><span data-stu-id="af106-178">Case Management</span></span>

<span data-ttu-id="af106-p111">此角色允许用户创建、 编辑、 删除和控制对安全 & 合规性中心中的电子数据展示事例的访问。有关详细信息，请参阅[管理 Office 365 安全性的电子数据展示事例&amp;合规性中心](manage-ediscovery-cases.md)。如前所述，您可以使用**添加 eDiscoveryCaseAdmin** cmdlet 以确保它们电子数据展示管理员之前，必须分配用户案例管理角色。</span><span class="sxs-lookup"><span data-stu-id="af106-p111">This role lets users create, edit, delete, and control access to eDiscovery cases in the Security & Compliance Center. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md). As previously explained, a user must be assigned the Case Management role before you can use the **Add-eDiscoveryCaseAdmin** cmdlet to make them an eDiscovery Administrator.</span></span> 

### <a name="compliance-search"></a><span data-ttu-id="af106-182">合规性搜索</span><span class="sxs-lookup"><span data-stu-id="af106-182">Compliance Search</span></span>

<span data-ttu-id="af106-p112">此角色允许用户在安全 & 合规性中心搜索邮箱和公用文件夹、 SharePoint Online 网站，OneDrive for Business 站点的业务对话、 Office 365 组和 Microsoft 团队的 Skype 运行内容搜索工具。此角色允许用户获取搜索结果的估计和创建导出报表，但其他角色所需启动内容搜索操作，如预览、 导出或删除搜索结果。</span><span class="sxs-lookup"><span data-stu-id="af106-p112">This role lets users run the Content Search tool in the Security & Compliance Center to search mailboxes and public folders, SharePoint Online sites, OneDrive for Business sites, Skype for Business conversations, Office 365 Groups, and Microsoft Teams. This role allows a user to get an estimate of the search results and create export reports, but additional roles are needed to initiate content search actions such as previewing, exporting, or deleting search results.</span></span>

<span data-ttu-id="af106-p113">请注意，用户分配合规性搜索角色，但没有预览角色可以预览其预览操作已启动由用户已分配角色预览搜索结果。没有预览角色的用户可以预览的最多 2 周，创建初始预览操作后的结果。</span><span class="sxs-lookup"><span data-stu-id="af106-p113">Note that users assigned the Compliance Search role but don't have the Preview role can preview the results of a search in which the preview action has been initiated by a user that's assigned the Preview role. The user without the Preview role can preview results for up to 2 weeks after the initial preview action was created.</span></span>

<span data-ttu-id="af106-p114">同样，用户分配合规性搜索角色，但没有角色可以下载由已分配的导出角色的用户启动导出操作已在其中搜索结果导出。不导出角色的情况下用户可以下载最多 2 周，创建初始导出操作后的搜索结果。之后，他们将无法下载结果，除非某人与导出角色重新启动导出。</span><span class="sxs-lookup"><span data-stu-id="af106-p114">Similarly, users assigned the Compliance Search role but don't have the Export role can download the results of a search in which the export action has initiated by a user that's assigned the Export role. The user without the Export role can download the results of a search for up to 2 weeks after the initial export action was created. After that they won’t be able to download the results unless someone with the Export role restarts the export.</span></span>

<span data-ttu-id="af106-190">有关详细信息，请参阅[Office 365 中的内容搜索](content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="af106-190">For more information, see [Content Search in Office 365](content-search.md).</span></span> 

### <a name="export"></a><span data-ttu-id="af106-191">导出</span><span class="sxs-lookup"><span data-stu-id="af106-191">Export</span></span>

<span data-ttu-id="af106-p115">角色允许的内容的搜索结果导出到本地计算机的用户。它还允许其准备分析高级电子数据展示中搜索结果。</span><span class="sxs-lookup"><span data-stu-id="af106-p115">The role lets users export the results of a Content Search to a local computer. It also lets them prepare search results for analysis in Advanced eDiscovery.</span></span> 

<span data-ttu-id="af106-194">有关导出搜索结果的详细信息，请参阅[Export 从 Office 365 安全性 & 合规性中心搜索的结果](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="af106-194">For more information about exporting search results, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="hold"></a><span data-ttu-id="af106-195">保留</span><span class="sxs-lookup"><span data-stu-id="af106-195">Hold</span></span>

<span data-ttu-id="af106-p116">此角色允许用户在邮箱、 公用文件夹、 网站、 业务对话的 Skype 放置内容和上的 Office 365 组保留。保持内容时，内容所有者仍然能够修改或删除原始的内容，但将保留内容，直到保留被删除或保留持续时间过期。</span><span class="sxs-lookup"><span data-stu-id="af106-p116">This role lets users place content in mailboxes, public folders, sites, Skype for Business conversations, and Office 365 groups on hold. When content is on hold, content owners will still be able to modify or delete the original content, but the content will be preserved until the hold is removed or until the hold duration expires.</span></span> 

<span data-ttu-id="af106-198">有关保留的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="af106-198">For more information about holds, see:</span></span>

- [<span data-ttu-id="af106-199">Office 365 安全性 & 合规性中心中的电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="af106-199">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](ediscovery-cases.md) 
- [<span data-ttu-id="af106-200">保留策略概述</span><span class="sxs-lookup"><span data-stu-id="af106-200">Overview of retention policies</span></span>](retention-policies.md)

### <a name="preview"></a><span data-ttu-id="af106-201">预览</span><span class="sxs-lookup"><span data-stu-id="af106-201">Preview</span></span>

<span data-ttu-id="af106-p117">此角色允许用户查看已从内容搜索返回的项目的列表。此外将能够打开并查看每个项的列表，以查看其内容。</span><span class="sxs-lookup"><span data-stu-id="af106-p117">This role lets users view a list of items that were returned from a Content Search. They'll also be able to open and view each item from the list to view its contents.</span></span>

### <a name="review"></a><span data-ttu-id="af106-204">审查</span><span class="sxs-lookup"><span data-stu-id="af106-204">Review</span></span>

<span data-ttu-id="af106-p118">此角色允许用户访问中的 Office 365 高级电子数据展示案例数据。此角色的主要用途是授予高级电子数据展示用户访问。此角色分配的用户可以查看和打开安全 & 他们是成员的合规性中心中的电子数据展示页上的情况下的列表。用户访问中安全 & 合规中心的案例后，则可以单击**切换到高级电子数据展示**访问和分析中高级电子数据展示事例数据。此角色不允许用户预览与案例相关联的内容搜索的结果或执行其他内容搜索或案例管理任务。</span><span class="sxs-lookup"><span data-stu-id="af106-p118">This role lets users access case data in Office 365 Advanced eDiscovery. The primary purpose of this role is to give users access to Advanced eDiscovery. Users who are assigned this role can see and open the list of cases on the eDiscovery page in the Security & Compliance Center that they are members of. After the user accesses a case in the Security & Compliance Center, they can click **Switch to Advanced eDiscovery** to access and analyze the case data in Advanced eDiscovery. This role doesn't allow the user to preview the results of a content search that's associated with the case or to perform other content search or case management tasks.</span></span>

### <a name="rms-decrypt"></a><span data-ttu-id="af106-210">RMS 解密</span><span class="sxs-lookup"><span data-stu-id="af106-210">RMS Decrypt</span></span>

<span data-ttu-id="af106-p119">此角色允许用户解密 RMS 加密电子邮件时导出高级电子数据展示中搜索结果或分析准备搜索结果。有关解密的详细信息导出期间的搜索结果，请参阅[从 Office 365 安全性 & 合规性中心搜索的结果的导出](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="af106-p119">This role lets users decrypt RMS-encrypted email messages when exporting search results or preparing search results for analysis in Advanced eDiscovery. For more information about decrypting search results during export, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="search-and-purge"></a><span data-ttu-id="af106-213">搜索和清除</span><span class="sxs-lookup"><span data-stu-id="af106-213">Search And Purge</span></span>

<span data-ttu-id="af106-p120">此角色允许执行批量删除的数据与内容搜索条件匹配的用户。有关详细信息，请参阅[搜索和删除 Office 365 组织中的电子邮件](search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="af106-p120">This role lets users perform bulk removal of data matching the criteria of a content search. For more information, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span> 


## <a name="more-information"></a><span data-ttu-id="af106-216">更多信息</span><span class="sxs-lookup"><span data-stu-id="af106-216">More information</span></span>

- <span data-ttu-id="af106-p121">**为什么创建电子数据展示管理员？** 如上文所述，电子数据展示管理员是可以查看和访问您的组织中的所有电子数据展示事例的电子数据展示管理员角色组的成员。此能够访问所有电子数据展示事例包含两个重要目的：</span><span class="sxs-lookup"><span data-stu-id="af106-p121">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span> 
    
  - <span data-ttu-id="af106-p122">电子数据展示事例的唯一成员之外的人员离开组织，没有人 （包括 Organization Management 角色组的成员或其他电子数据展示管理员角色组的成员） 可以访问该电子数据展示事例，因为它们不是成员用例。在这种情况下，将无法访问情况的数据。由于电子数据展示管理员可以访问组织中的所有电子数据展示事例，他们可以安全中查看大小写，但是&amp;合规性中心并将他们自己或其他电子数据展示经理添加为大小写的成员。</span><span class="sxs-lookup"><span data-stu-id="af106-p122">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="af106-p123">电子数据展示管理员可以查看和访问所有电子数据展示事例，因为他们可以审核和所有情况下监管和合规性搜索相关联。这有助于防止任何误用合规性搜索或电子数据展示事例。因为电子数据展示管理员可以访问合规性搜索结果中的潜在的敏感信息，您应限制是电子数据展示管理员的人数。</span><span class="sxs-lookup"><span data-stu-id="af106-p123">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated compliance searches. This can help to prevent any misuse of compliance searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a compliance search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="af106-p124">另外，电子数据展示管理员安全中&amp;合规性中心将自动添加为高级电子数据展示中的管理员。这意味着人员必须电子数据展示管理员高级电子数据展示，如设置用户和创建情况下，将数据导入到案例中执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="af106-p124">Also, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person must be an eDiscovery Administrator to perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and importing data in to a case.</span></span>
    
- <span data-ttu-id="af106-p125">**可以将组添加为安全中的电子数据展示管理员角色组的成员&amp;合规性中心？** 如上文所述，您可以将已启用邮件的安全组作为电子数据展示管理员角色组中的电子数据展示管理员子组的成员添加中安全使用**Add-rolegroupmember** cmdlet&amp;合规性中心 PowerShell。例如，您可以运行以下命令以将已启用邮件的安全组添加到电子数据展示管理员角色组。</span><span class="sxs-lookup"><span data-stu-id="af106-p125">**Can I add a group as a member of the eDiscovery Manager role group in the Security &amp; Compliance Center?** As previously explained, you can add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group by using the **Add-RoleGroupMember** cmdlet in Security &amp; Compliance Center PowerShell. For example, you can run the following command to add a mail-enabled security group to the eDiscovery Manager role group.</span></span> 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    <span data-ttu-id="af106-p126">请注意，不支持 Exchange 通讯组或 Office 365 组。您必须使用已启用邮件的安全组，您可以创建它在 Exchange Online PowerShell 中使用` New-DistributionGroup -Type Security `命令。您可以还创建启用邮件的安全组 （和添加成员） 在 Exchange 管理中心或 Office 365 管理中心。请注意，可能需要创建新已启用邮件的安全性可添加到电子数据展示管理员角色组后 60 分钟。</span><span class="sxs-lookup"><span data-stu-id="af106-p126">Note that an Exchange distribution group or an Office 365 group aren't supported. You must use a mail-enabled security group, which you can create in Exchange Online PowerShell by using the ` New-DistributionGroup -Type Security ` command. You can also create a mail-enabled security group (and add members) in the Exchange admin center or in the Office 365 admin center. Note that it might take up to 60 minutes after you create it for a new mail-enabled security to be available to add to the eDiscovery Managers role group.</span></span> 
    
    <span data-ttu-id="af106-p127">此外如上文所述，无法进行电子数据展示管理员组中安全使用**添加 eDiscoveryCaseAdmin** cmdlet 启用邮件的安全&amp;合规性中心 PowerShell。您只能作为电子数据展示管理员添加单个用户。</span><span class="sxs-lookup"><span data-stu-id="af106-p127">Also as previously stated, you can't make a mail-enabled security group an eDiscovery Administrator by using the **Add-eDiscoveryCaseAdmin** cmdlet in Security &amp; Compliance Center PowerShell. You can only add individual users as eDiscovery Administrators.</span></span> 
    
    <span data-ttu-id="af106-237">请注意，您还不能添加已启用邮件的安全组成员身份的案例。</span><span class="sxs-lookup"><span data-stu-id="af106-237">Note that you also can't add a mail-enabled security group as a member of a case.</span></span>
