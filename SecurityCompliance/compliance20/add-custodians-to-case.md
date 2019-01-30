---
title: 向高级电子数据展示 （预览） 用例添加管理员
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9a7dc6b1c2eeffdcd49be64d1d09d4a2bda782b
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607463"
---
# <a name="add-custodians-to-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="caabb-102">添加管理员的高级电子数据展示 （预览） 案例</span><span class="sxs-lookup"><span data-stu-id="caabb-102">Add custodians to an Advanced eDiscovery (Preview) Case</span></span>

<span data-ttu-id="caabb-p101">使用高级电子数据展示 （预览），您可以利用内置 custodian 管理工具，来协调围绕管理管理员和标识相关、 监控数据源中种情况下工作流。添加管理员后，系统可以自动标识，并进行业务网站保留在其主 Exchange 邮箱和 OneDrive。为您执行您发现，您可能还发现并映射其他邮箱或网站的管理员访问过去或团队中管理员是今天的成员。</span><span class="sxs-lookup"><span data-stu-id="caabb-p101">Using Advanced eDiscovery (Preview), you can leverage the built-in custodian management tool to coordinate your workflows around managing custodians and identifying relevant, custodial data sources within a case. When you add a custodian, the system can automatically identify, and place holds on their primary Exchange mailbox and OneDrive for Business site. As you conduct your discovery, you might also uncover and map additional mailboxes or sites that a custodian accessed in the past or Teams that a custodian is a member of today.</span></span>

<span data-ttu-id="caabb-106">使用以下工作流添加和管理在高级电子数据展示 （预览） 情况下，安全 & 合规中心内的管理员。</span><span class="sxs-lookup"><span data-stu-id="caabb-106">Use the following workflow to add and manage custodians in Advanced eDiscovery (Preview) cases within the Security & Compliance Center.</span></span> 

## <a name="step-1-identify-potential-custodians"></a><span data-ttu-id="caabb-107">步骤 1： 确定潜在的管理员</span><span class="sxs-lookup"><span data-stu-id="caabb-107">Step 1: Identify potential custodians</span></span>

<span data-ttu-id="caabb-p102">第一步是确定您的专家的相应的管理员。若要添加到案例的管理员，您必须是成员的电子数据展示管理员或电子数据展示管理员角色组。</span><span class="sxs-lookup"><span data-stu-id="caabb-p102">The first step is to identify the appropriate custodians for your matter. To add custodians to a case, you must be a member of the eDiscovery Managers or eDiscovery Admins role group.</span></span>   

<span data-ttu-id="caabb-110">将管理员添加到现有高级电子数据展示 （预览） 用例：</span><span class="sxs-lookup"><span data-stu-id="caabb-110">To add custodians to an existing Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="caabb-111">从**高级电子数据展示 （预览）** 页上，转到您的案例。</span><span class="sxs-lookup"><span data-stu-id="caabb-111">From the **Advanced eDiscovery (Preview)** page, go to your case.</span></span>
 
2. <span data-ttu-id="caabb-112">选择了一个案例后，转到**管理员**选项卡，然后单击 **+ 添加 Custodian**。</span><span class="sxs-lookup"><span data-stu-id="caabb-112">After you have selected a case, go to the **Custodians** tab and click **+ Add Custodian**.</span></span> 
 
3. <span data-ttu-id="caabb-p103">选择您想要添加到案例管理员。您可以开始通过键入以下内容搜索并从组织的 Azure Active Directory 中选择的用户。</span><span class="sxs-lookup"><span data-stu-id="caabb-p103">Choose the custodians that you want to add to the case. You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="caabb-115">已完成的管理员列表后，单击**下一步**开始识别潜在的数据源。</span><span class="sxs-lookup"><span data-stu-id="caabb-115">After you have finalized the list of custodians, click **Next** to begin identifying potential data sources.</span></span> 
   
## <a name="optional-step-2-select-custodian-data-sources"></a><span data-ttu-id="caabb-116">（可选）步骤 2： 选择 custodian 数据源</span><span class="sxs-lookup"><span data-stu-id="caabb-116">(Optional) Step 2: Select custodian data sources</span></span>

<span data-ttu-id="caabb-p104">为大写添加管理员后，您可以利用 Office 365，可帮助您确定并保留主 custodian 数据源。此工作流的下一步是选择在步骤 1 中指定管理员所拥有的数据源。</span><span class="sxs-lookup"><span data-stu-id="caabb-p104">After you have added custodians to a case, you can leverage Office 365 to help you identify and preserve the primary custodian data sources. The next step in this workflow is to select the data sources owned by the custodians specified in Step 1.</span></span> 

<span data-ttu-id="caabb-119">标识 custodian 数据源：</span><span class="sxs-lookup"><span data-stu-id="caabb-119">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="caabb-120">如果您希望系统自动确定并将添加 custodian 的主 Exchange 邮箱，请为每个 custodian 中,，选择**Exchange** 。</span><span class="sxs-lookup"><span data-stu-id="caabb-120">For each custodian, select **Exchange** if you would like the system to automatically identify and add the custodian's primary Exchange mailbox.</span></span> 
 
2. <span data-ttu-id="caabb-121">对于每个 custodian，如果您希望系统自动确定并将添加 custodian 主 OneDrive URL 选择**OneDrive** 。</span><span class="sxs-lookup"><span data-stu-id="caabb-121">For each custodian, select **OneDrive** if you would like the system to automatically identify and add the custodian's primary OneDrive URL.</span></span> 

    <span data-ttu-id="caabb-122">所做的选择之后, 他们系统将自动尝试确定的数据源并将其添加到您的案例。</span><span class="sxs-lookup"><span data-stu-id="caabb-122">After you've made your selections, they system will automatically try to identify the data sources and add them to your case.</span></span>
 
4. <span data-ttu-id="caabb-123">单击**下一步**开始映射到您的管理员的其他数据源。</span><span class="sxs-lookup"><span data-stu-id="caabb-123">Click **Next** to begin mapping additional data sources to your custodian.</span></span>

## <a name="optional-step-3-map-additional-data-sources"></a><span data-ttu-id="caabb-124">（可选）步骤 3： 将其他数据源映射</span><span class="sxs-lookup"><span data-stu-id="caabb-124">(Optional) Step 3: Map additional data sources</span></span>

<span data-ttu-id="caabb-p105">根据您的情况下，您可能还需要添加给定的 custodian 可能使用了在过去的邮箱组管理员，有权访问过去 custodian 当前是成员，或网站的位置。除了主 custodian 数据源，可以将其他 Office 365 数据源添加到管理员或利用 Office 365 帮助您识别也可能相关的数据源。</span><span class="sxs-lookup"><span data-stu-id="caabb-p105">Depending on your case, you may also want to add mailboxes that a given custodian may have used in the past, groups where a custodian is currently a member, or sites that a custodian had access to in the past. In addition to primary custodian data sources, you can add additional Office 365 data sources to a custodian or leverage Office 365 to help you identify potentially relevant data sources as well.</span></span> 

<span data-ttu-id="caabb-127">若要映射到特定 custodian 的邮箱、 站点或团队:</span><span class="sxs-lookup"><span data-stu-id="caabb-127">To map mailboxes, sites, or teams to a specific custodian:</span></span>
1. <span data-ttu-id="caabb-128">选择要分配给特定管理员的内容的位置，如邮箱、 网站和团队的**更新**。</span><span class="sxs-lookup"><span data-stu-id="caabb-128">Select **Update** to assign content locations, like mailboxes, sites, and Teams, to a specific custodian.</span></span> 

2. <span data-ttu-id="caabb-129">飞出，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="caabb-129">In the flyout, specify the following:</span></span>
   
  -  <span data-ttu-id="caabb-p106">**Exchange 邮箱**-单击**选择用户、 组或团队**，然后再次单击**选择用户、 组或团队**。若要指定邮箱分配给所选 custodian，使用搜索框查找用户邮箱和通讯组。您还可以为 Office 365 组或 Microsoft 团队分配关联的邮箱。选择用户、 组和团队复选框，单击**选择**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="caabb-p106">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again. To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups. You can also assign the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="caabb-p107">当您单击选择用户、 组或团队指定邮箱时，显示邮箱选取器为空。这是设计以提高性能。要将联系人添加到此列表中，请在搜索框中键入名称 （最少的 3 个字符）。</span><span class="sxs-lookup"><span data-stu-id="caabb-p107">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
   - <span data-ttu-id="caabb-p108">**SharePoint 网站**-单击**选择站点**，然后单击**选择网站**再次指定您想要分配给所选 custodian 的业务网站的其他 SharePoint 和 OneDrive。您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。键入要分配的每个网站的 URL。单击**选择**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="caabb-p108">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you would like to assign to the selected custodian. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Type the URL for each site that you want to assign. Click **Choose**, and then click **Done**.</span></span>
   - <span data-ttu-id="caabb-p109">**Microsoft 团队**– 单击**选择团队**，然后单击**选择团队**再次以查看 Microsoft 团队组管理员是今天的成员的列表。选择您希望将添加到您 custodian 团队。一旦选择，系统将自动标识关联的 SharePoint 网站和组邮箱关联的 Microsoft 团队到 & 选择。单击**选择**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="caabb-p109">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the custodian is a member of today. Select the Teams that you would like to add to your custodian. Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="caabb-145">若要添加其他 Microsoft 团队，您将需要单独添加了邮箱和 SharePoint 网站如上所示。</span><span class="sxs-lookup"><span data-stu-id="caabb-145">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="caabb-p110">映射源后，您可以查看邮箱总数、 网站和工作组刚添加的管理员。当您已为特定 custodian 定稿相关的数据源时，将维护此映射，并扩展到电子数据展示收集、 处理和审阅工作流。</span><span class="sxs-lookup"><span data-stu-id="caabb-p110">After you have finished mapping your sources, you can view the total mailboxes, sites, and Teams for the custodians that you have just added. When you've finalized the data sources relevant for a specific custodian, this mapping will be maintained and extended to the eDiscovery collection, processing, and review workflows.</span></span> 

## <a name="optional-step-4-place-custodians-on-hold"></a><span data-ttu-id="caabb-148">（可选）步骤 4： 位置上的管理员保留</span><span class="sxs-lookup"><span data-stu-id="caabb-148">(Optional) Step 4: Place custodians on hold</span></span>

 <span data-ttu-id="caabb-p111">尚未最终的管理员和您希望将添加到您的情况的数据源后，（可选） 可以将放置一些或全部上您管理员保持状态。当您将置于保持状态的管理员时，直到释放 custodian 从用例，或者直到取消删除保留保留映射到该用户的内容。在某些情况下，您可能想要添加到案例的管理员，而不会将其置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="caabb-p111">After you have finalized the custodians and data sources that you would like to add to your case, you can optionally place some or all of your custodians on hold. When you place a custodian on hold, the content mapped to that user is held until you release the custodian from the case or until you delete the hold. In some cases, you may want to add custodians to a case without placing them on hold.</span></span> 

<span data-ttu-id="caabb-152">将所选的管理员和数据源置于保留：</span><span class="sxs-lookup"><span data-stu-id="caabb-152">To place the selected custodians and data sources on hold:</span></span>

1. <span data-ttu-id="caabb-p112">验证 custodian 选择，然后选择要将置于保持状态的每个 custodian checkox。一旦管理员将置于保持状态，将自动创建包含所有监控源 custodian 保留策略。如果不选中此选项，custodian & 选择数据源将添加到用例，但不是会保留内容。</span><span class="sxs-lookup"><span data-stu-id="caabb-p112">Verify your custodian selections and select the checkox to place each custodian on hold.Once a custodian is placed on hold, a custodian hold policy containing all custodial sources will automatically be created. If the option is not checked, the custodian & selected data sources will be added to the case but the content will not be preserved.</span></span>

2. <span data-ttu-id="caabb-155">转到**保留**选项卡，并选择**Custodian 保留策略**。</span><span class="sxs-lookup"><span data-stu-id="caabb-155">Go to the **Holds** tab and select the **Custodian Hold Policy**.</span></span> 

3. <span data-ttu-id="caabb-156">单击**编辑**以查看所有选定的 custodian 数据源。</span><span class="sxs-lookup"><span data-stu-id="caabb-156">Click **Edit** to view all the selected custodian data sources.</span></span>
