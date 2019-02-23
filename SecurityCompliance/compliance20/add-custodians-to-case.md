---
title: 向高级电子数据展示 (预览) 案例中添加保管人
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c36e0a2228db042d50361460e2e22f13556e8715
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218212"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="b94a0-102">向高级电子数据展示 (预览) 案例中添加保管人</span><span class="sxs-lookup"><span data-stu-id="b94a0-102">Add custodians to an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="b94a0-p101">使用高级电子数据展示 (预览版), 您可以利用内置的保管人管理工具在工作流周围管理保管人, 并在事例中识别相关的 custodial 数据源。当您添加管理员时, 系统可以自动识别其主 Exchange 邮箱和 OneDrive for business 网站上的, 并将其置于保留中。在您进行发现时, 您可能还会发现并映射在过去或团队中, 管理员在今天的成员处访问的其他邮箱或网站。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="b94a0-106">使用以下工作流在安全 & 合规中心内的高级电子数据展示 (预览版) 案例中添加和管理保管人。</span><span class="sxs-lookup"><span data-stu-id="b94a0-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="b94a0-107">步骤 1: 确定潜在保管人</span><span class="sxs-lookup"><span data-stu-id="b94a0-107">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="b94a0-p102">第一步是确定适当的保管人, 以了解你的事宜。若要将保管人添加到案例, 您必须是电子数据展示管理器或电子数据展示管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

<span data-ttu-id="b94a0-110">将保管人添加到现有的高级电子数据展示 (预览版) 案例:</span><span class="sxs-lookup"><span data-stu-id="b94a0-110">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="b94a0-111">在 "**高级电子数据展示 (预览)** " 页上, 转到您的案例。</span><span class="sxs-lookup"><span data-stu-id="b94a0-111">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="b94a0-112">选择了事例后, 转到 "**保管人**" 选项卡, 然后单击 " **+ 添加保管人**"。</span><span class="sxs-lookup"><span data-stu-id="b94a0-112">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="b94a0-p103">选择要添加到事例的保管人。您可以通过键入搜索并从组织的 Azure Active Directory 中选择用户来开始。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="b94a0-115">完成保管人列表后, 单击 "**下一步**" 以开始标识潜在的数据源。</span><span class="sxs-lookup"><span data-stu-id="b94a0-115">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
   
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="b94a0-116">Optional步骤 2: 选择保管人数据源</span><span class="sxs-lookup"><span data-stu-id="b94a0-116">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="b94a0-p104">向事例添加了保管人后, 可以利用 Office 365 来帮助您识别和保留主保管人数据源。此工作流中的下一步是选择在步骤1中指定的保管人所拥有的数据源。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

<span data-ttu-id="b94a0-119">若要确定保管人数据源, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="b94a0-119">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="b94a0-120">对于每个保管人, 如果希望系统自动识别和添加管理员的主 Exchange 邮箱, 请选择 " **Exchange** "。</span><span class="sxs-lookup"><span data-stu-id="b94a0-120">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="b94a0-121">对于每个保管人, 如果希望系统自动识别和添加保管人的主 OneDrive URL, 请选择 " **OneDrive** "。</span><span class="sxs-lookup"><span data-stu-id="b94a0-121">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="b94a0-122">做出选择后, 系统会自动尝试识别数据源并将其添加到你的事例。</span><span class="sxs-lookup"><span data-stu-id="b94a0-122">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="b94a0-123">单击 "**下一步**" 开始将其他数据源映射到你的保管人。</span><span class="sxs-lookup"><span data-stu-id="b94a0-123">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="b94a0-124">Optional步骤 3: 映射其他数据源</span><span class="sxs-lookup"><span data-stu-id="b94a0-124">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="b94a0-p105">根据您的情况, 您可能还需要添加给定的用户可以在过去使用的邮箱、保管人当前是其成员的组, 或者是保管人对过去有权访问的网站。除了主保管人数据源之外, 还可以向保管人或利用 office 365 添加其他 Office 365 数据源, 以帮助您识别潜在的相关数据源。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

<span data-ttu-id="b94a0-127">若要将邮箱、网站或团队映射到特定保管人, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="b94a0-127">To map mailboxes, sites, or teams to a specific custodian:</span></span>

1. <span data-ttu-id="b94a0-128">选择 "**更新**", 将内容位置 (如邮箱、网站和团队) 分配给特定的保管人。</span><span class="sxs-lookup"><span data-stu-id="b94a0-128">Select **Update** to assign content locations, like mailboxes, sites, and Teams to a specific custodian.</span></span> 

2. <span data-ttu-id="b94a0-129">在浮出控件中, 指定以下内容:</span><span class="sxs-lookup"><span data-stu-id="b94a0-129">In the flyout, specify the following:</span></span>
   
  -  <span data-ttu-id="b94a0-p106">**Exchange 邮箱**-单击 "**选择用户、组或团队**", 然后再次单击 "**选择用户、组或团队**"。若要指定要分配给选定的保管人的邮箱, 请使用搜索框查找用户邮箱和通讯组。您还可以为 Office 365 组或 Microsoft 团队分配相关联的邮箱。选中 "用户、组、团队" 复选框, 单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="b94a0-p107">当您单击 "选择用户、组或团队以指定邮箱" 时, 显示的邮箱选取器为空。这是设计使然可提高性能。若要将人员添加到此列表, 请在搜索框中键入一个名称 (至少3个字符)。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
   - <span data-ttu-id="b94a0-p108">**SharePoint 网站**-单击 "**选择网站**", 然后再次单击 "**选择网站**", 以指定要分配给选定的管理员的其他 SharePoint 和 OneDrive for business 网站。您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。键入要分配的每个网站的 URL。单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
   - <span data-ttu-id="b94a0-p109">**Microsoft 团队**–单击 "**选择团队**", 然后再次单击 "**选择团队**", 查看保管人所属的 Microsoft 团队组列表。选择您想要添加到您的管理员的团队。选择后, 系统将自动识别 &。选择与该 Microsoft 团队关联的关联 SharePoint 网站和组邮箱。单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="b94a0-145">若要添加其他 Microsoft 团队, 您需要单独添加邮箱和 SharePoint 网站, 如上所示。</span><span class="sxs-lookup"><span data-stu-id="b94a0-145">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="b94a0-p110">完成源映射后, 可以查看您刚刚添加的保管人的邮箱、网站和团队总数。完成与特定保管人相关的数据源后, 此映射将被维护并扩展到电子数据展示集合、处理和审阅工作流。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="b94a0-148">Optional步骤 4: 将保管人置于保留状态</span><span class="sxs-lookup"><span data-stu-id="b94a0-148">(Optional) Step 4: Place custodians on hold</span></span>

 <span data-ttu-id="b94a0-p111">完成要添加到您的保管人的保管人和数据源后, 您可以选择将某些或所有保管人置于保留状态。当您将保管人置于保留状态时, 映射到该用户的内容将一直保留, 直到您从案例中释放该保管人或删除保留。在某些情况下, 您可能需要将保管人添加到事例中, 而无需将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="b94a0-152">将所选的保管人和数据源置于保留状态:</span><span class="sxs-lookup"><span data-stu-id="b94a0-152">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="b94a0-p112">验证您的保管人选择, 并选中复选框以将每个保管人置于保留状态。一旦将管理员置于保留状态, 将会自动创建包含所有 custodial 源的保管人保留策略。如果未选中此选项, 则会将所选数据源的保管人 & 添加到该事例中, 但不会保留内容。</span><span class="sxs-lookup"><span data-stu-id="b94a0-p112">Verify your custodian selections and select the checkbox to place each custodian on hold.Once a custodian is placed on hold, a custodian hold policy containing all custodial sources will automatically be created. If the option is not checked, the custodian & selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="b94a0-155">转到 "**保留**" 选项卡, 然后选择 "**保管人保留" 策略**。</span><span class="sxs-lookup"><span data-stu-id="b94a0-155">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="b94a0-156">单击 "**编辑**" 查看所有选定的保管人数据源。</span><span class="sxs-lookup"><span data-stu-id="b94a0-156">Click **Edit** to view all the selected custodian data sources.</span></span>
