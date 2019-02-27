---
title: 在高级电子数据展示 (预览版) 案例中管理保管人
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
ms.openlocfilehash: 95a1bcbbc279ad4e476fc479e701b0f8a921c83b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295675"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="96f44-102">在高级电子数据展示 (预览版) 案例中管理保管人</span><span class="sxs-lookup"><span data-stu-id="96f44-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="96f44-p101">"保管人" 选项卡包含在此情况下的所有保管人的可排序列表。将保管人添加到某个案例后, 将自动从 Azure Active Directory 收集有关每个保管人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96f44-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="96f44-105">查看保管人详细信息</span><span class="sxs-lookup"><span data-stu-id="96f44-105">Viewing custodian details</span></span>

<span data-ttu-id="96f44-p102">在将保管人添加到一个事例并从 "**保管人**" 选项卡上的列表中进行选择后, 将显示包含保管人详细信息的浮出控件页面。在此处, 你可以查看与该保管人相关的所有详细信息。浮出控件页面包含以下字段:</span><span class="sxs-lookup"><span data-stu-id="96f44-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="96f44-108">联系人信息</span><span class="sxs-lookup"><span data-stu-id="96f44-108">Contact information</span></span>

  - <span data-ttu-id="96f44-p103">**显示名称**: 在保管人的通讯簿中显示的名称。这通常是保管人的名字、中间名首字母和姓氏的组合。</span><span class="sxs-lookup"><span data-stu-id="96f44-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="96f44-111">**Mail/SMTP**: 保管人的 SMTP 地址, 例如, jeff@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="96f44-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="96f44-112">**Title**: 保管人的职务。</span><span class="sxs-lookup"><span data-stu-id="96f44-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="96f44-113">**部门**: 保管人在其中工作的部门的名称。</span><span class="sxs-lookup"><span data-stu-id="96f44-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="96f44-p104">**经理**: 管理员的经理。指定的经理将收到此保管人的任何上报通信。</span><span class="sxs-lookup"><span data-stu-id="96f44-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="96f44-116">位置信息</span><span class="sxs-lookup"><span data-stu-id="96f44-116">Location information</span></span>

  - <span data-ttu-id="96f44-117">**City**: 保管人所在的城市。</span><span class="sxs-lookup"><span data-stu-id="96f44-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="96f44-118">**状态**: 保管人地址中的省/市/自治区。</span><span class="sxs-lookup"><span data-stu-id="96f44-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="96f44-119">**国家/地区**: 保管人所在的国家/地区;例如, "US" 或 "UK"。</span><span class="sxs-lookup"><span data-stu-id="96f44-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="96f44-120">**office**: 保管人公司所在地的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="96f44-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="96f44-121">案例信息</span><span class="sxs-lookup"><span data-stu-id="96f44-121">Case information</span></span>

  - <span data-ttu-id="96f44-122">**保留状态**: 指示是否已将保管人置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="96f44-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="96f44-p105">**通信状态**: 指示是否已向保管人颁发保留通知。如果已向保管人发出通知, 则会将其标记为 "*已发布*"。如果尚未向保管人发出通知, 则会*取消发布*此状态。</span><span class="sxs-lookup"><span data-stu-id="96f44-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="96f44-p106">**状态**: 事例内管理员的状态。如果保管人仍处于保留状态, 则此项将*处于活动状态*。如果从某一案例中删除了管理员, 其状态将更改为 "已*发布*"。</span><span class="sxs-lookup"><span data-stu-id="96f44-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="96f44-129">处理状态</span><span class="sxs-lookup"><span data-stu-id="96f44-129">Processing status</span></span>

  - <span data-ttu-id="96f44-130">**索引编制状态**: 指示详细索引作业的状态。</span><span class="sxs-lookup"><span data-stu-id="96f44-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="96f44-131">**索引上次更新时间**: 指示上次触发深层索引作业的时间的 datestamp。</span><span class="sxs-lookup"><span data-stu-id="96f44-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="96f44-132">**数据源**: 显示为保管人选择的邮箱、网站和团队的计数。</span><span class="sxs-lookup"><span data-stu-id="96f44-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="96f44-133">更新管理员</span><span class="sxs-lookup"><span data-stu-id="96f44-133">Updating a custodian</span></span>

<span data-ttu-id="96f44-p107">在您的案例进展过程中, 您可能会发现, 与特定保管人 & 相关的其他数据源可能与您的情况有关。在其他情况下, 您可能需要删除已经过评审并视为不相关的某些数据源。</span><span class="sxs-lookup"><span data-stu-id="96f44-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="96f44-136">若要更新保管人和选定的数据源, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="96f44-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="96f44-137">从**电子数据展示 > 高级电子数据展示 (预览)** 中选择现有事例。</span><span class="sxs-lookup"><span data-stu-id="96f44-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="96f44-138">在这种情况下, 单击 "**保管人**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="96f44-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="96f44-139">从列表中选择保管人, 然后单击 "**编辑源**"。</span><span class="sxs-lookup"><span data-stu-id="96f44-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="96f44-140">通过单击 "**选择数据源**" 更新 Exchange 和 OneDrive 位置的选择。</span><span class="sxs-lookup"><span data-stu-id="96f44-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="96f44-p108">通过单击以**选择其他数据源**, 添加或删除映射用户的团队、SharePoint 或 Exchange 邮箱。有关如何将数据源映射到管理员的详细信息, 请参阅[向事例添加保管人](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="96f44-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="96f44-143">若要更新保管人保留状态, 请单击 "**放置 custodial 保留**", 并启用或禁用保管人的保留。</span><span class="sxs-lookup"><span data-stu-id="96f44-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="96f44-144">您可以选择多个保管人来执行批量操作, 如重新编制索引、释放或编辑一组保管人。</span><span class="sxs-lookup"><span data-stu-id="96f44-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="96f44-145">解决保管人处理错误</span><span class="sxs-lookup"><span data-stu-id="96f44-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="96f44-p109">在大多数合法工作流中, 在为特定调查添加保管人之后, 将搜索用户数据的子集。由于较大的文件大小或可能的损坏, 保管人数据源中的某些项目可能会部分编制索引。使用高级电子数据展示 (预览) 深度索引功能, 可以通过重新爬网并根据需要重新对这些项目重新编制索引来自动修正这些部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="96f44-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="96f44-p110">将管理员添加到某个事例时, 其数据将自动成为 "深层索引", 从而允许用户就地保留这些部分索引项, 而无需在 Office 365 之外下载、修正和重新运行搜索。在案例的生命周期中, 用户可以修正项目或为给定的保管人添加新的数据源。这可能需要更新保管人索引。</span><span class="sxs-lookup"><span data-stu-id="96f44-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="96f44-152">触发重新编制索引过程以处理部分索引项:</span><span class="sxs-lookup"><span data-stu-id="96f44-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="96f44-153">转到**电子数据展示 > 高级电子数据展示 (预览)** 并选择现有事例。</span><span class="sxs-lookup"><span data-stu-id="96f44-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="96f44-154">在这种情况下, 单击 "to**保管人" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="96f44-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="96f44-155">选择需要重新编制索引的保管人, 然后单击浮出控件页面上的 "**更新索引**"。</span><span class="sxs-lookup"><span data-stu-id="96f44-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="96f44-156">通过单击 "**保管人**" 选项卡上 "**索引作业状态**" 列中的链接, 检查保管人索引的状态。</span><span class="sxs-lookup"><span data-stu-id="96f44-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="96f44-157">还可以在 "**作业**" 选项卡上跟踪重新编制索引过程的状态。</span><span class="sxs-lookup"><span data-stu-id="96f44-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="96f44-158">有关重新编制索引和修正部分索引项目的详细信息, 请参阅[Fix 处理错误](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="96f44-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="96f44-159">从案例中释放管理员</span><span class="sxs-lookup"><span data-stu-id="96f44-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="96f44-160">在关闭案例的情况下, 将会发布保管人, 而保管人就不再符合为事例保留内容的义务, 或者当保管人被认为不再与特定事例相关时。</span><span class="sxs-lookup"><span data-stu-id="96f44-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="96f44-p111">如果在发布保留通知之后发布管理员, 则会向管理员发送发布通知。此外, 还将删除任何已发布保管人的 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="96f44-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="96f44-163">如果将管理员放在无人安静保留中 (未向其发出任何合法保留通知), 则将删除任何已发布的保管人的 custodial 保留。</span><span class="sxs-lookup"><span data-stu-id="96f44-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="96f44-164">若要释放保管人:</span><span class="sxs-lookup"><span data-stu-id="96f44-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="96f44-165">转到 "**保管人**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="96f44-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="96f44-166">从列表中选择管理员并单击弹出页面上的 "**释放保管人**"。</span><span class="sxs-lookup"><span data-stu-id="96f44-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="96f44-167">将 "**保管人**" 选项卡上的保管人的状态设置为 "已**发布**", 并且飞出页面上的 "**保留" 状态**将更改为 "**非活动**"。</span><span class="sxs-lookup"><span data-stu-id="96f44-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="96f44-p112">在几个合法保留方面, 可以同时参与保管人。当管理员从某一案例发布时, 将不会影响所有其他问题的保留和通知。</span><span class="sxs-lookup"><span data-stu-id="96f44-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="96f44-170">相关信息</span><span class="sxs-lookup"><span data-stu-id="96f44-170">Related information</span></span>

 - [<span data-ttu-id="96f44-171">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="96f44-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="96f44-172">处理通信</span><span class="sxs-lookup"><span data-stu-id="96f44-172">Work with communications</span></span>](managing-custodian-communications.md)
