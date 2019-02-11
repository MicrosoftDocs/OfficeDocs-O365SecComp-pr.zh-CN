---
title: 管理管理员在高级电子数据展示 （预览） 情况下
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
ms.openlocfilehash: cce823924502fa2617d7819dc0967733fbc072e0
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29706093"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-preview-case"></a><span data-ttu-id="1ce01-102">管理管理员在高级电子数据展示 （预览） 情况下</span><span class="sxs-lookup"><span data-stu-id="1ce01-102">Manage custodians in an Advanced eDiscovery (Preview) case</span></span>

<span data-ttu-id="1ce01-p101">管理员选项卡包含情况下的所有管理员可排序的列表。向用例添加管理员后，将自动从 Azure Active Directory 中收集有关每个 custodian 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p101">The Custodians tab contains a sortable list of all the custodians in the case. After you add custodians to a case, details about each custodian will automatically be collected from Azure Active Directory.</span></span>

## <a name="viewing-custodian-details"></a><span data-ttu-id="1ce01-105">查看 custodian 详细信息</span><span class="sxs-lookup"><span data-stu-id="1ce01-105">Viewing custodian details</span></span>

<span data-ttu-id="1ce01-p102">管理员添加到案例并从**管理员**选项卡上的列表中选择后，将显示弹出页包含 custodian 详细信息。从此处，您可以查看与该 custodian 相关的所有详细信息。飞出页包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="1ce01-p102">The flyout page that contains custodian details appears after you add a custodian to a case and select them from the list on the **Custodians** tab. From here, you can view all the details related to that custodian. The flyout page contains the following fields:</span></span>

- <span data-ttu-id="1ce01-108">联系人信息</span><span class="sxs-lookup"><span data-stu-id="1ce01-108">Contact information</span></span>

  - <span data-ttu-id="1ce01-p103">**显示名称**： custodian 通讯簿中显示的名称。这通常是名字的 custodian，中间的初始和最后一个名称的组合。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p103">**Display Name**: The name displayed in the address book for the custodian. This is usually the combination of the custodian’s first name, middle initial and last name.</span></span>
  - <span data-ttu-id="1ce01-111">**邮件/SMTP**: custodian，例如，jeff@contoso.onmicrosoft.com 的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="1ce01-111">**Mail/SMTP**: The SMTP address for the custodian, for example, jeff@contoso.onmicrosoft.com.</span></span>  
  - <span data-ttu-id="1ce01-112">**标题**： custodian 的职务。</span><span class="sxs-lookup"><span data-stu-id="1ce01-112">**Title**: The custodian’s job title.</span></span>
  - <span data-ttu-id="1ce01-113">**部门**： custodian 适用于该部门的名称。</span><span class="sxs-lookup"><span data-stu-id="1ce01-113">**Department**: The name for the department in which the custodian works.</span></span>
  - <span data-ttu-id="1ce01-p104">**管理器**： 管理员管理器。指定的经理将收到此 custodian 任何升级通信。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p104">**Manager**: The custodian’s manager. The designated manager will receive any Escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="1ce01-116">位置信息</span><span class="sxs-lookup"><span data-stu-id="1ce01-116">Location information</span></span>

  - <span data-ttu-id="1ce01-117">**市/县**： custodian 所在的市/县。</span><span class="sxs-lookup"><span data-stu-id="1ce01-117">**City**: The city in which the custodian is located.</span></span>
  - <span data-ttu-id="1ce01-118">**状态**： 在地址 custodian/自治区。</span><span class="sxs-lookup"><span data-stu-id="1ce01-118">**State**: The state or province in the custodian’s address.</span></span>
  - <span data-ttu-id="1ce01-119">**国家/地区**： custodian 所在; 国家/地区例如，"美国"或"英国"。</span><span class="sxs-lookup"><span data-stu-id="1ce01-119">**Country/Region**: The country/region in which the custodian’s is located; for example, “US” or “UK”.</span></span>
  - <span data-ttu-id="1ce01-120">**Office**： 的业务 custodian 就地的办公室位置。</span><span class="sxs-lookup"><span data-stu-id="1ce01-120">**Office**: The office location in the custodian’s place of business.</span></span>

- <span data-ttu-id="1ce01-121">案例信息</span><span class="sxs-lookup"><span data-stu-id="1ce01-121">Case information</span></span>

  - <span data-ttu-id="1ce01-122">**挂起状态**： 指示是否已 custodian 置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="1ce01-122">**Hold status**: Indicates if the custodian has been placed on hold.</span></span> 
  - <span data-ttu-id="1ce01-p105">**通信状态**： 指示是否已被 custodian 颁发保留通知。如果管理员已发布一条通知，然后这将被标记为*已发布*。如果管理员不发出通知，则将此状态*未发布*。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p105">**Communication status**: Indicates if the custodian has been issued a hold notice. If the custodian has been issued a notice, then this will be marked as *Published*. If the custodian has not been issued a notice, then this status will be *Un-Published*.</span></span> 
  - <span data-ttu-id="1ce01-p106">**状态**： 这种情况内 custodian 的状态。如果管理员是仍处于保持状态的大小写，这将处于*活动状态*。如果管理员已从案例，其状态将更改为*发布*。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p106">**Status**: The status of the custodian within the case. This will be *Active* if the custodian is still on hold for the case. If a custodian is removed from a case, their status will change to *Released*.</span></span> 

- <span data-ttu-id="1ce01-129">处理状态</span><span class="sxs-lookup"><span data-stu-id="1ce01-129">Processing status</span></span>

  - <span data-ttu-id="1ce01-130">**索引状态**： 指示深入索引作业的状态。</span><span class="sxs-lookup"><span data-stu-id="1ce01-130">**Indexing status**: Indicates the status of the deep indexing job.</span></span>  
  - <span data-ttu-id="1ce01-131">**索引上次更新时间**： 指示上次触发深入索引作业时的日期戳。</span><span class="sxs-lookup"><span data-stu-id="1ce01-131">**Indexing Last Updated Time**: Indicates the datestamp of when the deep indexing job was last triggered.</span></span>
  - <span data-ttu-id="1ce01-132">**数据源**： 显示的邮箱、 网站和团队已选定为 custodian 的计数。</span><span class="sxs-lookup"><span data-stu-id="1ce01-132">**Data sources**: Shows the count of mailboxes, sites, and Teams that have been selected for the custodian.</span></span>

## <a name="updating-a-custodian"></a><span data-ttu-id="1ce01-133">更新管理员</span><span class="sxs-lookup"><span data-stu-id="1ce01-133">Updating a custodian</span></span>

<span data-ttu-id="1ce01-p107">随着案例进展，您可能会发现可能会出现与特定 custodian & 相关的其他数据源您的案例。在其他情况下，您可能要删除已审阅并视为不相关的特定数据源。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p107">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case. In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="1ce01-136">若要更新管理员和所选的数据源：</span><span class="sxs-lookup"><span data-stu-id="1ce01-136">To update a custodian and the selected data sources:</span></span>

1. <span data-ttu-id="1ce01-137">从**电子数据展示 > 高级电子数据展示 (Preview)** 中选择现有用例。</span><span class="sxs-lookup"><span data-stu-id="1ce01-137">Select an existing case from the **eDiscovery > Advanced eDiscovery (Preview)**.</span></span>
  
2. <span data-ttu-id="1ce01-138">情况下，单击**管理员**选项卡。</span><span class="sxs-lookup"><span data-stu-id="1ce01-138">In the case, click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="1ce01-139">从列表中选择 custodian(s)，单击**编辑源**。</span><span class="sxs-lookup"><span data-stu-id="1ce01-139">Select the custodian(s) from the list and click **Edit sources**.</span></span>
  
4. <span data-ttu-id="1ce01-140">通过单击**选择数据源**中更新 Exchange 和 OneDrive 位置的选择。</span><span class="sxs-lookup"><span data-stu-id="1ce01-140">Update selections for Exchange and OneDrive locations by clicking **Choose data sources**.</span></span>
  
5. <span data-ttu-id="1ce01-p108">添加或删除工作组、 SharePoint、 或 Exchange 邮箱映射用户通过单击**选择其他数据源**。有关如何可以映射数据源到管理员的详细信息，请参阅[添加管理员为大写](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p108">Add or remove Teams, SharePoint, or Exchange mailboxes mapped the user by clicking to **Select additional data sources**. For more information about how you to map data sources to a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span>
  
6. <span data-ttu-id="1ce01-143">若要更新的 custodian 保留状态，单击**位置监控保留**，和启用或禁用管理员保留项。</span><span class="sxs-lookup"><span data-stu-id="1ce01-143">To update the custodian hold status, click **Place custodial holds**, and enable or disable the hold for custodians.</span></span>

> [!TIP]
> <span data-ttu-id="1ce01-144">您可以选择多个管理员执行批量操作，如重新编制索引、 释放，或编辑一的管理员。</span><span class="sxs-lookup"><span data-stu-id="1ce01-144">You can select multiple custodians to perform bulk actions, like re-indexing, releasing, or editing a set of custodians.</span></span>

## <a name="resolving-custodian-processing-errors"></a><span data-ttu-id="1ce01-145">处理 custodian 处理错误</span><span class="sxs-lookup"><span data-stu-id="1ce01-145">Resolving custodian processing errors</span></span>

<span data-ttu-id="1ce01-p109">在大多数法律工作流中，管理员添加的特定调查之后, 将搜索的用户的数据子集。由于大文件大小或可能已损坏，管理员的数据源中的某些项目可能部分索引。使用高级电子数据展示 （预览） 深度索引功能，这些部分索引的项可以自动修正通过重新爬网并重新编制索引按需型这些项。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p109">In most Legal workflows, after custodians are added for a specific investigation, a subset of the users’ data will be searched. Due to large file sizes or possible corruption, some items within the custodians’ data sources may be partially indexed. Using the Advanced eDiscovery (Preview) deep indexing capability, these partially indexed items can be automatically remediated by re-crawling and re-indexing these items on demand.</span></span> 

<span data-ttu-id="1ce01-p110">当管理员添加到种情况下时，他们的数据将自动"深度编制"，从而允许用户离开这些部分编制索引的位置，而不必下载、 修正和重新运行搜索之外 Office 365 中的项目。生命周期内种情况下，用户可能修正项目或给定 custodian 添加新数据源。这可能需要将更新的 Custodian 索引。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p110">When a custodian is added to a case, their data will automatically be "deep indexed”, allowing users to leave these partially indexed items in place instead of having to download, remediate and re-run searches outside of Office 365. During the lifecycle of a case, a user may remediate items or add new data sources for a given custodian. This may require the Custodian Index to be updated.</span></span> 

<span data-ttu-id="1ce01-152">若要部分触发地址重新索引进程的索引项：</span><span class="sxs-lookup"><span data-stu-id="1ce01-152">To trigger a re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="1ce01-153">转到**电子数据展示 > 高级电子数据展示 （预览）** 并选择一个现有的情况。</span><span class="sxs-lookup"><span data-stu-id="1ce01-153">Go to **eDiscovery > Advanced eDiscovery (Preview)** and select an existing case.</span></span>

2. <span data-ttu-id="1ce01-154">情况下，单击**管理员选项卡**。</span><span class="sxs-lookup"><span data-stu-id="1ce01-154">In the case, click to **Custodians tab**.</span></span> 

3. <span data-ttu-id="1ce01-155">选择需要重新编制索引，custodian(s)，然后单击在弹出上的**更新索引**。</span><span class="sxs-lookup"><span data-stu-id="1ce01-155">Select the custodian(s) that needs to be re-indexed, and then click **Update index** on the flyout page.</span></span>

4. <span data-ttu-id="1ce01-156">单击**管理员**选项卡上的**索引作业状态**列中的链接来检查 custodian 索引的状态。</span><span class="sxs-lookup"><span data-stu-id="1ce01-156">Check the status of the custodian index by clicking the link in the **Indexing job Status** column on the **Custodians** tab.</span></span>  

5. <span data-ttu-id="1ce01-157">在**作业**选项卡上，还可以跟踪重新索引进程的状态。</span><span class="sxs-lookup"><span data-stu-id="1ce01-157">The status for the re-indexing process can also be tracked on the **Jobs** tab.</span></span>

<span data-ttu-id="1ce01-158">有关重新索引和补救部分索引项的详细信息，请参阅[修复处理错误](processing-data-for-case.md)。</span><span class="sxs-lookup"><span data-stu-id="1ce01-158">For more information about re-indexing and remediating partially indexed items, see [Fix processing errors](processing-data-for-case.md).</span></span>

## <a name="releasing-a-custodian-from-a-case"></a><span data-ttu-id="1ce01-159">释放从案例管理员</span><span class="sxs-lookup"><span data-stu-id="1ce01-159">Releasing a custodian from a case</span></span>

<span data-ttu-id="1ce01-160">管理员年发布的情况下，种情况下关闭、 custodian 不再义务保留内容的情况下，或当管理员将被视为不再可能相关到特定 case。</span><span class="sxs-lookup"><span data-stu-id="1ce01-160">A custodian is released in situations where a case is closed, a custodian is no longer under obligation to preserve content for a case, or when a custodian is deemed to no longer be relevant to a particular case.</span></span> 

<span data-ttu-id="1ce01-p111">如果保留通知已发布后，管理员释放时，将向管理员发送发行说明。此外，还将删除任何监控保留的已发布的管理员。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p111">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian. In addition, any custodial holds attributed to the released custodians will also be removed.</span></span>

<span data-ttu-id="1ce01-163">如果管理员发出保持无提示他们已未发出任何合法保留通知，任何监控保留的已发布的管理员将被删除。</span><span class="sxs-lookup"><span data-stu-id="1ce01-163">If the custodian was placed on a silent hold, where they were not issued any legal hold notifications, then any custodial holds attributed to the released custodians will be removed.</span></span>  

<span data-ttu-id="1ce01-164">发布管理员：</span><span class="sxs-lookup"><span data-stu-id="1ce01-164">To release a custodian:</span></span> 

1.  <span data-ttu-id="1ce01-165">转到**管理员**选项卡。</span><span class="sxs-lookup"><span data-stu-id="1ce01-165">Go to the **Custodians** tab.</span></span>

2.  <span data-ttu-id="1ce01-166">从列表中选择 custodian 和弹出页上，单击**版本管理员**。</span><span class="sxs-lookup"><span data-stu-id="1ce01-166">Select the custodian from the list and click **Release custodians** on the flyout page.</span></span>

    <span data-ttu-id="1ce01-167">在**管理员**选项卡上 custodian 的状态设置为**发布**和**挂起状态**弹出上更改为**非活动**。</span><span class="sxs-lookup"><span data-stu-id="1ce01-167">The status of the custodian on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **Inactive**.</span></span> 

> [!TIP]
> <span data-ttu-id="1ce01-p112">管理员将同时中可能涉及几个合法保留案件。当管理员从案例释放时，保存和其他案件通知不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="1ce01-p112">A custodian might be simultaneously be involved in several legal hold matters. When a custodian is released from a case, the holds and notifications across other matters will not be impacted.</span></span>

## <a name="related-information"></a><span data-ttu-id="1ce01-170">相关信息</span><span class="sxs-lookup"><span data-stu-id="1ce01-170">Related information</span></span>

 - [<span data-ttu-id="1ce01-171">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="1ce01-171">Error remediation when processing data</span></span>](error-remediation.md) 
- [<span data-ttu-id="1ce01-172">处理通信</span><span class="sxs-lookup"><span data-stu-id="1ce01-172">Work with communications</span></span>](managing-custodian-communications.md)
