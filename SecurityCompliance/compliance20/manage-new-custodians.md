---
title: 在高级电子数据展示事例中管理保管人
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
ms.openlocfilehash: d9806ecbc23f46ee2d39f8d7e6be07af0d6a83e8
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151614"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="2d4e1-102">在高级电子数据展示事例中管理保管人</span><span class="sxs-lookup"><span data-stu-id="2d4e1-102">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="2d4e1-103">高级电子数据展示中的保管人选项卡包含已添加到事例中的所有保管人的列表。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-103">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="2d4e1-104">向事例添加保管人后, 会自动从 Azure Active Directory 中收集每个保管人的详细信息, 这些信息可在高级电子数据展示中查看。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-104">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![管理保管人](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="2d4e1-106">查看保管人详细信息</span><span class="sxs-lookup"><span data-stu-id="2d4e1-106">View custodian details</span></span>

<span data-ttu-id="2d4e1-107">若要查看有关保管人的详细信息, 请单击 "**保管人**" 选项卡上的 "管理员" 列表。将显示一个弹出页面, 其中包含有关保管人的以下信息:</span><span class="sxs-lookup"><span data-stu-id="2d4e1-107">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="2d4e1-108">联系人信息</span><span class="sxs-lookup"><span data-stu-id="2d4e1-108">Contact information</span></span>

  - <span data-ttu-id="2d4e1-109">**显示名称**-在保管人的通讯簿中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-109">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="2d4e1-110">这通常是保管人的名字、中间名首字母和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-110">This is usually the combination of the custodian’s first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="2d4e1-111">**Mail/SMTP** -保管人的主 SMTP 地址, 例如, brianj@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-111">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="2d4e1-112">请注意, 此外, 还列出了保管人的用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-112">Note that the custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="2d4e1-113">**Title** -保管人的职务。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-113">**Title** - The custodian’s job title.</span></span>

  - <span data-ttu-id="2d4e1-114">**部门**-保管人在其中工作的部门的名称。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-114">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="2d4e1-115">**经理**-管理员的经理。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-115">**Manager** - The custodian’s manager.</span></span> <span data-ttu-id="2d4e1-116">指定的经理将收到此保管人的任何上报通信。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-116">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="2d4e1-117">位置信息</span><span class="sxs-lookup"><span data-stu-id="2d4e1-117">Location information</span></span>

  - <span data-ttu-id="2d4e1-118">**City** -保管人所在的城市。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-118">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="2d4e1-119">**State** -保管人地址中的省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-119">**State** - The state or province in the custodian’s address.</span></span>

  - <span data-ttu-id="2d4e1-120">**国家/地区**-保管人所在的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-120">**Country/Region** - The country/region where the custodian’s is located.</span></span>

  - <span data-ttu-id="2d4e1-121">**Office** -保管人公司中的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-121">**Office** - The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="2d4e1-122">案例信息</span><span class="sxs-lookup"><span data-stu-id="2d4e1-122">Case information</span></span>

  - <span data-ttu-id="2d4e1-123">**保留状态**-指示是否已将保管人置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-123">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="2d4e1-124">**通信状态**: 指示是否已向保管人颁发保留通知。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-124">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="2d4e1-125">如果保管人已发出通知, 则会**发布**此属性的此值。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-125">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="2d4e1-126">如果尚未向保管人颁发通知, 则状态将为 "**取消发布**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-126">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="2d4e1-127">**Status** -事例中的管理员的状态。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-127">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="2d4e1-128">**活动**状态表示保管人是事例的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-128">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="2d4e1-129">如果从某一案例中发布了保管人, 则状态将更改为 "已**发布**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-129">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="2d4e1-130">数据源和索引编制信息</span><span class="sxs-lookup"><span data-stu-id="2d4e1-130">Data sources and indexing information</span></span>

    - <span data-ttu-id="2d4e1-131">**数据源**-显示与保管人关联的数据源 (邮箱、网站和团队) 的计数和类型, 并且是事例的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-131">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="2d4e1-132">**索引更新时间**-指示上次触发高级索引作业的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-132">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="2d4e1-133">此属性还将指示高级索引编制过程当前的运行时间。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-133">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="2d4e1-134">编辑管理员</span><span class="sxs-lookup"><span data-stu-id="2d4e1-134">Edit a custodian</span></span>

<span data-ttu-id="2d4e1-135">在您的案例进展过程中, 您可能会发现, 与特定保管人 & 相关的其他数据源可能与您的情况有关。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-135">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="2d4e1-136">在其他情况下, 您可能需要删除已经过评审并视为不相关的某些数据源。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-136">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="2d4e1-137">若要更新与保管人关联的数据源, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2d4e1-137">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="2d4e1-138">转到**电子数据展示 _GT_ 高级电子数据展示**并打开该事例。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-138">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="2d4e1-139">单击 "**保管人**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-139">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="2d4e1-140">从列表中选择一个管理员并单击弹出页面上的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-140">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![编辑数据源](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="2d4e1-142">单击 "**选择数据源**" 选项卡, 更改管理员的 Exchange 邮箱和 OneDrive 帐户的设置, 单击 "**选择数据源**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-142">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="2d4e1-143">单击 "**选择其他数据源**" 选项卡以添加或删除与保管人相关联的团队、SharePoint 或 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-143">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="2d4e1-144">有关与保管人关联的数据源的详细信息, 请参阅在[将保管人添加到一个案例](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)中的 "步骤 3: 将其他数据源与保管人关联"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-144">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="2d4e1-145">单击 "**将 custodial 保留**" 以启用或禁用保管人的保留。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-145">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="resolve-custodian-processing-errors"></a><span data-ttu-id="2d4e1-146">解决保管人处理错误</span><span class="sxs-lookup"><span data-stu-id="2d4e1-146">Resolve custodian processing errors</span></span>

<span data-ttu-id="2d4e1-147">在用于法律调查的大多数电子数据展示工作流中, 在将管理员添加到合法案例之后, 将搜索保管人的数据的子集。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-147">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="2d4e1-148">由于文件大小非常大或可能损坏, 与管理员关联的数据源中的某些项可能会进行部分索引。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-148">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="2d4e1-149">在高级电子数据展示中使用[高级索引](indexing-custodian-data.md)功能时, 可以根据需要重新对这些项目重新编制索引, 从而自动修正大多数部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-149">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="2d4e1-150">将管理员添加到某个案例后, 与保管人关联的数据源中的数据将自动重新编制索引 (通过高级索引过程)。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-150">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="2d4e1-151">这意味着您可以就地保留数据, 而无需下载和更正数据, 然后将其脱机搜索)。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-151">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="2d4e1-152">但是, 在法律案件的生命周期内, 可能会将新数据源与保管人关联。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-152">However, during the lifecycle of a legal case new data sources might be associated to a custodian.</span></span> <span data-ttu-id="2d4e1-153">在这种情况下, 您可以重新运行高级索引编制进程以修正任何部分已编制索引的项目, 并更新保管人数据的索引, 从而对保管人的数据重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-153">In this case, you re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="2d4e1-154">触发重新编制索引过程以处理部分索引项:</span><span class="sxs-lookup"><span data-stu-id="2d4e1-154">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="2d4e1-155">转到**电子数据展示 _GT_ 高级电子数据展示**并打开该事例。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-155">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="2d4e1-156">单击 "to**保管人" 选项卡**, 然后选择其数据必须为 "编制索引" 的保管人。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-156">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="2d4e1-157">在弹出页面上, 单击 "**更新索引**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-157">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="2d4e1-158">将显示一个对话框, 指出已创建索引作业。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-158">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="2d4e1-159">对保管人数据重新编制索引是一个长期运行的过程;所创建的相应作业称为**重新索引保管人数据**。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-159">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="2d4e1-160">您可以通过监视 "**索引作业状态**" 列中的状态来跟踪 "**作业**" 选项卡或 "**保管人**" 选项卡上的进度。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-160">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="2d4e1-161">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2d4e1-161">For more information, see:</span></span>

- [<span data-ttu-id="2d4e1-162">解决处理错误</span><span class="sxs-lookup"><span data-stu-id="2d4e1-162">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="2d4e1-163">管理作业</span><span class="sxs-lookup"><span data-stu-id="2d4e1-163">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="2d4e1-164">从案例发布管理员</span><span class="sxs-lookup"><span data-stu-id="2d4e1-164">Release a custodian from a case</span></span>

<span data-ttu-id="2d4e1-165">在关闭案例的情况下, 将会发布保管人, 而保管人将不再符合保留内容的义务, 或者当保管人被认为不再与案例相关时。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-165">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="2d4e1-166">如果在发布保留通知之后发布管理员, 则会向管理员发送发布通知。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-166">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="2d4e1-167">此外, 还将删除放置在与保管人关联的数据源上的任何保留。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-167">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="2d4e1-168">如果将管理员放在无人*安静保留*中 (未向其发出任何合法保留通知), 则不会发送发布通知, 但会删除与该保管人关联的数据源上的所有保留项。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-168">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="2d4e1-169">若要释放保管人:</span><span class="sxs-lookup"><span data-stu-id="2d4e1-169">To release a custodian:</span></span> 

1. <span data-ttu-id="2d4e1-170">转到**电子数据展示 _GT_ 高级电子数据展示**并打开该事例。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-170">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.  <span data-ttu-id="2d4e1-171">转到 "**保管人**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-171">Go to the **Custodians** tab.</span></span>

3.  <span data-ttu-id="2d4e1-172">单击 "至**保管人" 选项卡**, 然后选择从该事例发布的管理员。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-172">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="2d4e1-173">在飞出页面上, 单击 "**释放保管人**"。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-173">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="2d4e1-174">将显示一个警告页面, 说明如果将保留项放置在与保管人关联的数据源上, 保留将被删除, 并且与不同的高级电子数据展示事例关联的其他保留仍适用。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-174">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="2d4e1-175">其中包括 Office 365 中的其他类型的保留和保留功能 (如 Office 365 保留策略)。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-175">That includes other types of preservation and retention features in Office 365 (such as an Office 365 retention policy).</span></span>

5. <span data-ttu-id="2d4e1-176">单击 **"是"** 确认要释放保管人。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-176">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="2d4e1-177">请注意, 此用户在 "**保管人**" 选项卡上的状态设置为 "已**发布**", 并且飞出页面上的 "**保留" 状态**更改为**False**。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-177">Note that status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="2d4e1-178">在几种法律情况下, 保管人可能同时涉及。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-178">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="2d4e1-179">当管理员从某一案例发布时, 在其他事务中的保留和通知将不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-179">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="2d4e1-180">批量编辑保管人</span><span class="sxs-lookup"><span data-stu-id="2d4e1-180">Bulk-edit custodians</span></span>

<span data-ttu-id="2d4e1-181">您可以使用批量编辑器同时编辑多个保管人。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-181">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="2d4e1-182">若要执行此操作, 只需在 "**保管人**" 选项卡上选择两个或更多保管人以显示批量编辑器, 然后单击其中一项任务。</span><span class="sxs-lookup"><span data-stu-id="2d4e1-182">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![用于编辑多个保管人的设置的飞出页面](../media/AeDBulkEditCustodians.png)