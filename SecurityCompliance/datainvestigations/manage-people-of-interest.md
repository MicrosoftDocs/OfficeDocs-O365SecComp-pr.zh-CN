---
title: 管理数据调查中感兴趣的人员 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d06dde60ae75cfea1bf1d79f445b613d20a76363
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029893"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a><span data-ttu-id="b2a88-102">管理数据调查中感兴趣的人员 (预览)</span><span class="sxs-lookup"><span data-stu-id="b2a88-102">Manage people of interest in Data Investigations (Preview)</span></span>

<span data-ttu-id="b2a88-103">数据调查通常涉及感兴趣的人。</span><span class="sxs-lookup"><span data-stu-id="b2a88-103">Data investigations often involve people of interest.</span></span> <span data-ttu-id="b2a88-104">通常情况下, 他们是拥有您调查或寻求补救措施的错放、敏感或恶意数据的人。</span><span class="sxs-lookup"><span data-stu-id="b2a88-104">Usually they are people who own the misplaced, sensitive or malicious data that you're investigating or looking to remediate.</span></span> <span data-ttu-id="b2a88-105">在**数据调查 (预览版)** 中, 可以将其添加到查找用于确定搜索范围的数据源, 也可以查看其他信息 (如联系人、位置和活动日志)。</span><span class="sxs-lookup"><span data-stu-id="b2a88-105">In **Data Investigations (Preview)**, you can add them to discover their data sources to use in scoping your search or view additional information such as contact, location and activity logs.</span></span> 


## <a name="add-people-of-interest"></a><span data-ttu-id="b2a88-106">添加感兴趣的人员</span><span class="sxs-lookup"><span data-stu-id="b2a88-106">Add people of interest</span></span>

<span data-ttu-id="b2a88-107">在 "**感兴趣的人员**" 选项卡上, 您可以添加感兴趣的人员并发现他们的数据源 (如可用于确定搜索范围的 Exchange 邮箱或 OneDrive for business 网站)。</span><span class="sxs-lookup"><span data-stu-id="b2a88-107">In **People of interest** tab, you can add people of interest and discover their data sources such as Exchange mailboxes or OneDrive for Business site that you can use to scope your search.</span></span> <span data-ttu-id="b2a88-108">当受关注的人员限制时, 搜索会提高性能和准确性, 因为该工具会重新处理任何未编制索引的数据, 如图像或不受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="b2a88-108">When scoped down by people of interest, searches are more performant and accurate because the tool re-processes any unindexed data such as images or unsupported file types.</span></span> <span data-ttu-id="b2a88-109">您还可以查看其联系人信息、位置信息和活动日志, 您可以使用它们启动通信或进一步调查其活动。</span><span class="sxs-lookup"><span data-stu-id="b2a88-109">You can also see their contact information, location information and activity logs that you can use to initiate communications or further investigate their activities.</span></span> 

<span data-ttu-id="b2a88-110">向调查中添加感兴趣的人员:</span><span class="sxs-lookup"><span data-stu-id="b2a88-110">To add people of interest to an investigation:</span></span>

1. <span data-ttu-id="b2a88-111">从 "**数据调查 (预览)** " 页中, 转到您的调查。</span><span class="sxs-lookup"><span data-stu-id="b2a88-111">From the **Data Investigations (Preview)** page, go to your investigation.</span></span>
 
2. <span data-ttu-id="b2a88-112">选择调查后, 转到 "**感兴趣的人员**" 选项卡, 然后单击 "**添加感兴趣的人**"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-112">After you have selected a investigation, go to the **People of interest** tab and click **+ Add people of interest**.</span></span> 
 
3. <span data-ttu-id="b2a88-113">选择要添加到调查中的人员。</span><span class="sxs-lookup"><span data-stu-id="b2a88-113">Choose people that you want to add to the investigation.</span></span> <span data-ttu-id="b2a88-114">您可以通过键入搜索并从组织的 Azure Active Directory 中选择用户来开始。</span><span class="sxs-lookup"><span data-stu-id="b2a88-114">You can start by typing to search and select the users from your organization's Azure Active Directory.</span></span>
 
4. <span data-ttu-id="b2a88-115">完成感兴趣的人员列表后, 单击 "**下一步**" 以映射其数据源。</span><span class="sxs-lookup"><span data-stu-id="b2a88-115">After you have finalized the list of people of interest, click **Next** to map their data sources.</span></span> 

5. <span data-ttu-id="b2a88-116">Optional对于每个用户, 选择 " **Exchange** " 以添加人员的主 Exchange 邮箱, **OneDrive**将添加人员的主 OneDrive for business 网站。</span><span class="sxs-lookup"><span data-stu-id="b2a88-116">[Optional] For each person, select **Exchange** to add person's primary Exchange mailbox, and **OneDrive** to add person's primary OneDrive for Business site.</span></span>

6. <span data-ttu-id="b2a88-117">Optional单击 "**下一步**" 添加您想要与您感兴趣的人员关联的任何其他数据源。</span><span class="sxs-lookup"><span data-stu-id="b2a88-117">[Optional] Click **Next** to add any additional data sources that you want to associate with your people of interest.</span></span>

7. <span data-ttu-id="b2a88-118">Optional选择 "**更新**", 将内容位置 (如邮箱、网站和团队) 分配给某个人。</span><span class="sxs-lookup"><span data-stu-id="b2a88-118">[Optional] Select **Update** to assign content locations, like mailboxes, sites, and Teams to a person.</span></span> 

8. <span data-ttu-id="b2a88-119">Optional在浮出控件中:</span><span class="sxs-lookup"><span data-stu-id="b2a88-119">[Optional] In the flyout:</span></span>
   
    -  <span data-ttu-id="b2a88-120">**Exchange 邮箱**-单击 "**选择用户、组或团队**", 然后再次单击 "**选择用户、组或团队**"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-120">**Exchange Mailboxes** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="b2a88-121">若要添加更多邮箱, 请使用搜索框查找用户邮箱和通讯组。</span><span class="sxs-lookup"><span data-stu-id="b2a88-121">To add more mailboxes, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="b2a88-122">您还可以添加用于存储 Office 365 组或 Microsoft 团队信息的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2a88-122">You can also add mailboxes used to store an Office 365 Group or a Microsoft Team information.</span></span> <span data-ttu-id="b2a88-123">选中 "用户、组、团队" 复选框, 单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-123">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b2a88-124">当您单击 "选择用户、组或团队以指定邮箱" 时, 显示的邮箱选取器为空。</span><span class="sxs-lookup"><span data-stu-id="b2a88-124">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="b2a88-125">这种设计旨在增强性能。</span><span class="sxs-lookup"><span data-stu-id="b2a88-125">This is by design to enhance performance.</span></span> <span data-ttu-id="b2a88-126">若要将人员添加到此列表, 请在搜索框中键入一个名称 (至少3个字符)。</span><span class="sxs-lookup"><span data-stu-id="b2a88-126">To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="b2a88-127">**SharePoint 网站**-单击 "**选择网站**", 然后再次单击 "**选择网站**", 以指定要添加到人员的其他 SharePoint 和 OneDrive for business 网站 wwant。</span><span class="sxs-lookup"><span data-stu-id="b2a88-127">**SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify additional SharePoint and OneDrive for Business sites that you wwant to add to a person.</span></span> <span data-ttu-id="b2a88-128">您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="b2a88-128">You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="b2a88-129">键入要分配的每个网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="b2a88-129">Type the URL for each site that you want to assign.</span></span> <span data-ttu-id="b2a88-130">单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-130">Click **Choose**, and then click **Done**.</span></span>
     - <span data-ttu-id="b2a88-131">**Microsoft 团队**–单击 "**选择团队**", 然后再次单击 "**选择团队**" 以查看此人是今天的成员的 Microsoft 团队组列表。</span><span class="sxs-lookup"><span data-stu-id="b2a88-131">**Microsoft Teams** – Click **Choose Teams** and then click **Choose Teams** again to view a list of Microsoft Team groups that the person is a member of today.</span></span> <span data-ttu-id="b2a88-132">选择要添加到人员的团队。</span><span class="sxs-lookup"><span data-stu-id="b2a88-132">Select the Teams that you want to add to the person.</span></span> <span data-ttu-id="b2a88-133">选择后, 系统将自动识别 &。选择与该 Microsoft 团队关联的关联 SharePoint 网站和组邮箱。</span><span class="sxs-lookup"><span data-stu-id="b2a88-133">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="b2a88-134">单击 "**选择**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-134">Click **Choose**, and then click **Done**.</span></span>
        
      > [!NOTE]
      > <span data-ttu-id="b2a88-135">若要添加其他 Microsoft 团队, 您需要单独添加邮箱和 SharePoint 网站, 如上所示。</span><span class="sxs-lookup"><span data-stu-id="b2a88-135">To add additional Microsoft Teams, you will need to separately add the mailbox and SharePoint site as shown above.</span></span>

<span data-ttu-id="b2a88-136">完成将数据源映射到感兴趣的人员之后, 可以看到您刚刚添加的邮箱、网站和团队总数的摘要。</span><span class="sxs-lookup"><span data-stu-id="b2a88-136">After you have finished mapping data sources to people of interest, you can see the summary of total mailboxes, sites, and Teams that you just added.</span></span> <span data-ttu-id="b2a88-137">如果你将任何其他数据源映射到感兴趣的人, 并将你的搜索范围限定为关注的人员, 则在整个调查过程中将文档映射到关注的人员, 从而更轻松地组织证据或按感兴趣的人员生成报告。.</span><span class="sxs-lookup"><span data-stu-id="b2a88-137">If you map any additional data sources to people of interest and scope your search by people of interest, the mapping of document to people of interest persist throughout the investigation, making it easier to organize evidence or generate report by people of interest.</span></span> 

## <a name="view-additional-people-of-interest-information"></a><span data-ttu-id="b2a88-138">查看其他感兴趣的人员信息</span><span class="sxs-lookup"><span data-stu-id="b2a88-138">View additional people of interest information</span></span>

<span data-ttu-id="b2a88-139">在 "**感兴趣的人员**" 选项卡上, 单击您 adeed 的人员。</span><span class="sxs-lookup"><span data-stu-id="b2a88-139">In **People of interest** tab, click on a person that you adeed.</span></span> <span data-ttu-id="b2a88-140">在浮出控件中, 您将看到:</span><span class="sxs-lookup"><span data-stu-id="b2a88-140">In a flyout, you'll see:</span></span>

- <span data-ttu-id="b2a88-141">联系人信息</span><span class="sxs-lookup"><span data-stu-id="b2a88-141">Contact information</span></span>

  - <span data-ttu-id="b2a88-142">**显示名称**: 在通讯簿中显示的 peron 的名称。</span><span class="sxs-lookup"><span data-stu-id="b2a88-142">**Display Name**: The peron's name displayed in the address book.</span></span> <span data-ttu-id="b2a88-143">这通常是名字、中间名首字母和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="b2a88-143">This is usually the combination of first name, middle initial and last name.</span></span>
  - <span data-ttu-id="b2a88-144">**Mail/smtp**: 人员的 SMTP 地址, 例如, jeff@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="b2a88-144">**Mail/SMTP**: The SMTP address of the person, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="b2a88-145">**职务**: 职务。</span><span class="sxs-lookup"><span data-stu-id="b2a88-145">**Title**: Job title.</span></span>
  - <span data-ttu-id="b2a88-146">**部门**: 人员在其中工作的部门的名称。</span><span class="sxs-lookup"><span data-stu-id="b2a88-146">**Department**: The name of the department in which the person works.</span></span>
  - <span data-ttu-id="b2a88-147">**经理**: 人员的经理。</span><span class="sxs-lookup"><span data-stu-id="b2a88-147">**Manager**: The person's manager.</span></span> <span data-ttu-id="b2a88-148">管理者接收此人的任何升级通信。</span><span class="sxs-lookup"><span data-stu-id="b2a88-148">Manager receives any escalation communications for this person.</span></span>
  
- <span data-ttu-id="b2a88-149">位置信息</span><span class="sxs-lookup"><span data-stu-id="b2a88-149">Location information</span></span>

  - <span data-ttu-id="b2a88-150">**City**: 人员所在的城市。</span><span class="sxs-lookup"><span data-stu-id="b2a88-150">**City**: The city in which the person is located.</span></span>
  - <span data-ttu-id="b2a88-151">**状态**: 人员所在的省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="b2a88-151">**State**: The state or province in which the person is located.</span></span>
  - <span data-ttu-id="b2a88-152">**国家/地区**: 人员所在的国家/地区;例如, "US" 或 "UK"。</span><span class="sxs-lookup"><span data-stu-id="b2a88-152">**Country/Region**: The country/region in which the person is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="b2a88-153">**office**: 人员的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="b2a88-153">**Office**: The office location of the person.</span></span>

- <span data-ttu-id="b2a88-154">处理状态</span><span class="sxs-lookup"><span data-stu-id="b2a88-154">Processing status</span></span>

  - <span data-ttu-id="b2a88-155">**索引编制状态**: 对数据源进行深入索引的状态</span><span class="sxs-lookup"><span data-stu-id="b2a88-155">**Indexing status**: Status of deep indexing the data sources</span></span>
  - <span data-ttu-id="b2a88-156">**索引上次更新时间**: 上次触发详细索引作业的时间戳。</span><span class="sxs-lookup"><span data-stu-id="b2a88-156">**Indexing Last Updated Time**: Timestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="b2a88-157">**数据源**: 显示映射到人员的邮箱、网站和团队的计数</span><span class="sxs-lookup"><span data-stu-id="b2a88-157">**Data sources**: Shows the count of mailboxes, sites, and Teams mapped to the person</span></span>

- <span data-ttu-id="b2a88-158">更新索引</span><span class="sxs-lookup"><span data-stu-id="b2a88-158">Update index</span></span>
    - <span data-ttu-id="b2a88-159">您可以对此人的数据源重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="b2a88-159">You can re-index this person's data sources.</span></span> 

- <span data-ttu-id="b2a88-160">查看活动</span><span class="sxs-lookup"><span data-stu-id="b2a88-160">View activity</span></span> 

    - <span data-ttu-id="b2a88-161">您可以查看和搜索用户的活动日志。</span><span class="sxs-lookup"><span data-stu-id="b2a88-161">You can view and search user's activity logs.</span></span> <span data-ttu-id="b2a88-162">有关详细信息, 请参阅[查看感兴趣的人员活动](view-people-of-interest-activity.md)</span><span class="sxs-lookup"><span data-stu-id="b2a88-162">For more information, see [View people of interest activity](view-people-of-interest-activity.md)</span></span> 
