---
title: 向高级电子数据展示案例中添加保管人
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8cc3d7db959c31c4657bb8c0d270f014e598e143
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155334"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="20d87-102">向高级电子数据展示案例中添加保管人</span><span class="sxs-lookup"><span data-stu-id="20d87-102">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="20d87-103">使用高级电子数据展示中的内置保管人管理工具来调整工作流, 使其围绕管理保管人和标识与事例关联的相关 custodial 数据源。</span><span class="sxs-lookup"><span data-stu-id="20d87-103">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="20d87-104">当您添加管理员时, 系统可以自动识别其 Exchange 邮箱和 OneDrive for Business 帐户并将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="20d87-104">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="20d87-105">在调查的发现过程中, 你可能还会确定保管人 (如邮箱、网站或团队) 对保管人进行访问或参与的其他数据源 (如邮箱、网站或团队)。</span><span class="sxs-lookup"><span data-stu-id="20d87-105">During the discovery process of your investigation, you might also identify additional data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="20d87-106">在这种情况下, 您可以使用保管人管理工具将这些数据源与特定保管人相关联。</span><span class="sxs-lookup"><span data-stu-id="20d87-106">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="20d87-107">向事例中添加保管人并将其与其他数据源关联之后, 可以快速保留数据并搜索 custodial 数据。</span><span class="sxs-lookup"><span data-stu-id="20d87-107">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="20d87-108">使用以下工作流在高级电子数据展示事例中添加和管理保管人。</span><span class="sxs-lookup"><span data-stu-id="20d87-108">Use the following workflow to add and manage custodians in Advanced eDiscovery cases.</span></span> 

![保管人管理选项卡](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a><span data-ttu-id="20d87-110">开始之前</span><span class="sxs-lookup"><span data-stu-id="20d87-110">Before you begin</span></span>

<span data-ttu-id="20d87-111">若要将保管人添加到案例, 您必须是电子数据展示管理器角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="20d87-111">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="20d87-112">这将为您提供将保管人添加到事例的必要权限, 并在 custodial 数据源上放置保留。</span><span class="sxs-lookup"><span data-stu-id="20d87-112">This will provide you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span>


## <a name="step-1-add-potential-custodians"></a><span data-ttu-id="20d87-113">步骤 1: 添加潜在保管人</span><span class="sxs-lookup"><span data-stu-id="20d87-113">Step 1: Add potential custodians</span></span>

<span data-ttu-id="20d87-114">第一步是确定并向事例中添加保管人。</span><span class="sxs-lookup"><span data-stu-id="20d87-114">The first step is to identify and add custodians to the case.</span></span>

1. <span data-ttu-id="20d87-115">在**高级电子数据展示**主页上, 单击要向保管人添加保管人的事例。</span><span class="sxs-lookup"><span data-stu-id="20d87-115">On the **Advanced eDiscovery** home page, click the case the you want to add custodians to.</span></span> 
 
2. <span data-ttu-id="20d87-116">单击 "**保管人**" 选项卡, 然后单击 " **+ 添加保管人**"。</span><span class="sxs-lookup"><span data-stu-id="20d87-116">Click the **Custodians** tab and then click **+ Add custodians**.</span></span>

3. <span data-ttu-id="20d87-117">查找要添加到该事例的保管人。</span><span class="sxs-lookup"><span data-stu-id="20d87-117">Find the custodians to add  to the case.</span></span> <span data-ttu-id="20d87-118">键入人员姓名的第一部分, 以显示组织的 Azure Active Directory 中的用户。</span><span class="sxs-lookup"><span data-stu-id="20d87-118">Type the first part of a person's name to display users from your organization's Azure Active Directory.</span></span> <span data-ttu-id="20d87-119">找到正确的人员后, 单击其名称以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="20d87-119">When you find the correct person, click their name to add them to the list.</span></span>

   ![确定潜在保管人](../media/AddCustodianStep1.png)
 
4. <span data-ttu-id="20d87-121">添加所有相关保管人后, 单击 "**下一步**" 以选择保管人的主数据源。</span><span class="sxs-lookup"><span data-stu-id="20d87-121">After added all the relevant custodians, click **Next** to select the custodians' primary data sources.</span></span>
  
## <a name="step-2-select-custodian-data-sources"></a><span data-ttu-id="20d87-122">步骤 2: 选择保管人数据源</span><span class="sxs-lookup"><span data-stu-id="20d87-122">Step 2: Select custodian data sources</span></span>

<span data-ttu-id="20d87-123">在添加了保管人之后, 保管人工具将帮助您识别每个保管人拥有的主数据源;具体来说, 这些数据位置是管理员的 Exchange 邮箱和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="20d87-123">After adding custodians, the custodian tool will help you identify the primary data sources owned by each custodian; specifically these data locations are the custodian's Exchange mailbox and OneDrive account.</span></span> 

<span data-ttu-id="20d87-124">若要确定保管人数据源, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="20d87-124">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="20d87-125">若要选择所有保管人的 Exchange 邮箱, 请单击列顶部的 " **exchange** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="20d87-125">To select the Exchange mailbox for all custodians, click the **Exchange** checkbox at the top of the column.</span></span> <span data-ttu-id="20d87-126">请注意, 您可以取消选中任何特定保管人的复选框, 以将邮箱删除为 custodial 位置。</span><span class="sxs-lookup"><span data-stu-id="20d87-126">Note that you can then unselect the checkbox for any specific custodian to remove a mailbox as a custodial location.</span></span> <span data-ttu-id="20d87-127">或者, 也可以将 " **Exchange** " 复选框保留为未选中状态, 然后选中各个保管人的复选框。</span><span class="sxs-lookup"><span data-stu-id="20d87-127">Alternatively, you can leave the **Exchange** checkbox at the top of the column unselected and then select the checkbox for individual custodians.</span></span> 
 
   ![选择 Custodial 数据源](../media/AddCustodianStep2.png)
 
2. <span data-ttu-id="20d87-129">对保管人的 OneDrive 帐户重复相同的操作。</span><span class="sxs-lookup"><span data-stu-id="20d87-129">Repeat the same thing for the custodians' OneDrive accounts.</span></span> 

    <span data-ttu-id="20d87-130">选择保管人数据源后, 系统会自动尝试确定和验证这些数据源, 然后将它们作为与保管人关联的数据源添加到事例中。</span><span class="sxs-lookup"><span data-stu-id="20d87-130">After select the custodian data sources, they system automatically attempts to identify and verify these data sources, and then adds them to the case as data sources associated with the custodians.</span></span>
 
4. <span data-ttu-id="20d87-131">在这种情况下, 单击 "**下一步**" 开始将其他数据源与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="20d87-131">Click **Next** to begin associating additional data sources to the custodians in the case.</span></span>

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a><span data-ttu-id="20d87-132">步骤 3: 将其他数据源与管理员关联</span><span class="sxs-lookup"><span data-stu-id="20d87-132">Step 3: Associate additional data sources to a custodian</span></span>

<span data-ttu-id="20d87-133">根据要调查的情况, 您可能还需要在特定保管人访问的邮箱中搜索 (和保留内容)、管理员当前是其成员的 Office 365 组或管理员也访问的网站。</span><span class="sxs-lookup"><span data-stu-id="20d87-133">Depending on the case you're investigating, you may also need to search (and preserve content in) mailboxes that a specific custodian may have accessed, Office 365 groups that a custodian is currently a member of, or sites that a custodian has also accessed.</span></span> <span data-ttu-id="20d87-134">因此, 除了在上一步中指定的主保管人数据源之外, 还可以将附加的 Office 365 数据源与事例中的管理员相关联。</span><span class="sxs-lookup"><span data-stu-id="20d87-134">So in addition to the primary custodian data sources that you specified in the previous step, you can also associate additional Office 365 data sources with a custodian in the case.</span></span> 

<span data-ttu-id="20d87-135">若要将邮箱、网站或团队映射到特定保管人, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="20d87-135">To map mailboxes, sites, or teams to a specific custodian:</span></span>

1. <span data-ttu-id="20d87-136">在 "**选择其他数据源**" 页上, 在特定保管人的行中单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="20d87-136">On the **Select additional data sources** page, click **Add** in the row for the specific custodian.</span></span> 
  
   ![映射其他数据源](../media/AddCustodianStep3.PNG)

2. <span data-ttu-id="20d87-138">在飞出页面上, 您可以指定来自任何以下 Office 365 服务的数据源:</span><span class="sxs-lookup"><span data-stu-id="20d87-138">On the flyout page, you can specify a data source from any the following Office 365 services:</span></span>
  
   -  <span data-ttu-id="20d87-139">**Exchange 电子邮件**-单击 "**选择用户、组或团队**", 然后再次单击 "**选择用户、组或团队"** 。</span><span class="sxs-lookup"><span data-stu-id="20d87-139">**Exchange email** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="20d87-140">使用搜索框查找要与保管人相关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="20d87-140">Use the search box to find mailboxes to associate with the custodian.</span></span> <span data-ttu-id="20d87-141">若要指定要分配给选定的保管人的邮箱, 请使用搜索框查找用户邮箱和通讯组。</span><span class="sxs-lookup"><span data-stu-id="20d87-141">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="20d87-142">您还可以为 Office 365 组或 Microsoft 团队分配相关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="20d87-142">You can also assign the associated mailbox for an Office 365 group or a Microsoft Team.</span></span> <span data-ttu-id="20d87-143">选中 "用户、组、团队" 复选框, 单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="20d87-143">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="20d87-144">当您单击 "选择用户、组或团队以指定邮箱" 时, 显示的邮箱选取器为空。</span><span class="sxs-lookup"><span data-stu-id="20d87-144">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="20d87-145">这种设计旨在增强性能。</span><span class="sxs-lookup"><span data-stu-id="20d87-145">This is by design to enhance performance.</span></span> <span data-ttu-id="20d87-146">若要将邮箱添加到此列表, 请在搜索框中键入名称或别名 (至少为3个字符)。</span><span class="sxs-lookup"><span data-stu-id="20d87-146">To add mailbox to this list, type a name or alias (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="20d87-147">**SharePoint 网站**-单击 "**选择网站**", 然后再次单击 "**选择网站**" 以显示组织中的 SharePoint 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="20d87-147">**SharePoint sites** - Click **Choose sites** and then click **Choose sites** again to display a list of SharePoint sites in your organization.</span></span> <span data-ttu-id="20d87-148">若要将网站与管理员关联, 可以在列表中选择一个网站, 也可以键入与 Office 365 组、Microsoft 团队或 OneDrive 帐户关联的其他网站或网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="20d87-148">To associate a site with the custodian, you can select a site in the list or you can type the URL of a different site or a site associated with a Office 365 group, Microsoft Team, or a OneDrive account.</span></span>
     
     - <span data-ttu-id="20d87-149">**团队**–单击 "**选择团队**", 然后再次单击 "**选择团队**" 以显示管理员是其当前成员的 Microsoft 团队列表。</span><span class="sxs-lookup"><span data-stu-id="20d87-149">**Teams** – Click **Choose teams** and then click **Choose teams** again to display a list of Microsoft Teams that the custodian is a currently member of.</span></span> <span data-ttu-id="20d87-150">选择您想要添加到您的管理员的团队。</span><span class="sxs-lookup"><span data-stu-id="20d87-150">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="20d87-151">选择后, 系统将自动识别 &。选择与该 Microsoft 团队关联的关联 SharePoint 网站和组邮箱。</span><span class="sxs-lookup"><span data-stu-id="20d87-151">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="20d87-152">单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="20d87-152">Click **Choose**, and then click **Done**.</span></span>

       ![映射数据源](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > <span data-ttu-id="20d87-154">若要将其他团队与管理员关联, 您必须使用**Exchange 邮件**和**SharePoint 网站**位置, 单独添加与团队关联的邮箱和网站。</span><span class="sxs-lookup"><span data-stu-id="20d87-154">To associate an additional team with a custodian, you have to separately add the mailbox and site associated with the team by using the **Exchange mail** and **SharePoint sites** locations.</span></span>

<span data-ttu-id="20d87-155">完成将其他数据源与保管人相关联后, 可以在 "**选择其他数据源" 页**上查看与每个保管人关联的邮箱、网站和团队的总数。</span><span class="sxs-lookup"><span data-stu-id="20d87-155">After you have finished associating additional data sources with the custodians, you can view the total number of mailboxes, sites, and teams associated with each custodian on the **Select additional data sources page**.</span></span> <span data-ttu-id="20d87-156">在为特定保管人提供相关数据源后, 在收集、处理和审查电子数据展示工作流中的阶段时, 将会维护和使用此关联。</span><span class="sxs-lookup"><span data-stu-id="20d87-156">When you've finalized the relevant data sources for a specific custodian, this association will be maintained and used during the collection, processing, and review stages in eDiscovery workflow.</span></span>

## <a name="step-4-place-custodians-on-hold"></a><span data-ttu-id="20d87-157">步骤 4: 将保管人置于保留状态</span><span class="sxs-lookup"><span data-stu-id="20d87-157">Step 4: Place custodians on hold</span></span>

<span data-ttu-id="20d87-158">定稿保管人和数据源以添加到事例后, 可以选择将某些或所有保管人置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="20d87-158">After you've finalized the custodians and data sources to add to the case, you can optionally place some or all of the custodians on hold.</span></span> <span data-ttu-id="20d87-159">当您将保管人置于保留状态时, 将保留与保管人关联的所有内容位置中的所有内容, 直到您从中删除保留或释放该保管人时为止。</span><span class="sxs-lookup"><span data-stu-id="20d87-159">When you place a custodian on hold, all content in all content locations that are associated to the custodian is preserved until you remove the hold or release the custodian from the.</span></span> <span data-ttu-id="20d87-160">在某些情况下, 您可能需要将保管人添加到事例中, 而无需将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="20d87-160">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="20d87-161">将保管人和数据源置于保留状态:</span><span class="sxs-lookup"><span data-stu-id="20d87-161">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="20d87-162">在 "**将所选保管人置于保留**状态" 页上, 单击列顶部的 "**保留**" 复选框以将所有保管人置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="20d87-162">On the **Place a hold on the selected custodians** page, click the **Hold** checkbox at the top of the column to place all custodians on hold.</span></span> <span data-ttu-id="20d87-163">请注意, 您可以取消选中任何特定保管人的复选框以将其从保留中删除。</span><span class="sxs-lookup"><span data-stu-id="20d87-163">Note that you can then unselect the checkbox for any specific custodian to remove from the hold.</span></span> <span data-ttu-id="20d87-164">或者, 您可以在未选中的列顶部保留**保留**复选框, 然后选中各个保管人的复选框。</span><span class="sxs-lookup"><span data-stu-id="20d87-164">Alternatively, you can leave the **Hold** checkbox at the top of the column unselected and then select the checkbox for individual custodians.</span></span> 
 
   ![就地保留](../media/AddCustodianStep5.PNG)

2. <span data-ttu-id="20d87-166">验证保管人保留选择, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="20d87-166">Verify the custodian hold selections and then click **Complete**.</span></span>

<span data-ttu-id="20d87-167">如果不将 a 保留保留在保管人中, 则保管人及其关联的数据源将被添加到该事例中, 但这些数据源中的内容将不会置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="20d87-167">If you don't place a a hold a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources will not be placed on hold.</span></span>

<span data-ttu-id="20d87-168">将管理员置于保留状态后, 将自动创建包含所有 custodial 源的保管人保留策略。</span><span class="sxs-lookup"><span data-stu-id="20d87-168">After a custodian is placed on hold, a custodian hold policy that contains all custodial sources will be automatically created.</span></span> <span data-ttu-id="20d87-169">若要查看此策略:</span><span class="sxs-lookup"><span data-stu-id="20d87-169">To view this policy:</span></span>

1. <span data-ttu-id="20d87-170">在该事例的**主页**上, 单击 "**保留**" 选项卡, 然后单击 " **CustodianHold-Guid**"</span><span class="sxs-lookup"><span data-stu-id="20d87-170">On the **Home** page of the case, click the **Holds** tab and then click **CustodianHold-Guid**,</span></span>  

2. <span data-ttu-id="20d87-171">在弹出页面上, 单击 "**编辑保留**" 以查看处于保留状态的所有保管人数据源。</span><span class="sxs-lookup"><span data-stu-id="20d87-171">On the flyout page, click **Edit hold** to view all the custodian data sources that are placed on hold.</span></span>

