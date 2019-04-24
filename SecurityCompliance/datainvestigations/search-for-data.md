---
title: 在调查中搜索数据
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
ms.openlocfilehash: 5f52f26c4443addd0e108794e1d3635a9b8efb98
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258050"
---
# <a name="search-for-data-in-an-investigation"></a><span data-ttu-id="90909-102">在调查中搜索数据</span><span class="sxs-lookup"><span data-stu-id="90909-102">Search for data in an investigation</span></span>

<span data-ttu-id="90909-103">在数据调查的 "**搜索**" 选项卡上, 您可以使用关键字和条件在 Office 365 的内容位置中搜索错放的、机密的或敏感的数据。</span><span class="sxs-lookup"><span data-stu-id="90909-103">On the **Search** tab in a data investigation, you can search for misplaced, confidential, or sensitive data in content locations in Office 365 using keywords and conditions.</span></span> 

<span data-ttu-id="90909-104">在运行搜索后, 可以查看搜索返回的项目的统计信息, 例如, 项目数与搜索查询匹配的内容位置。</span><span class="sxs-lookup"><span data-stu-id="90909-104">After you run a search, you can view statistics on the items returned by the search, such as the content locations that had the most items that matched the search query.</span></span> <span data-ttu-id="90909-105">您还可以预览结果的子集。</span><span class="sxs-lookup"><span data-stu-id="90909-105">You can also preview a subset of the results.</span></span> <span data-ttu-id="90909-106">在确定了要进一步调查的文档集后, 可以将搜索结果添加到证据集, 以便进一步处理和分析。</span><span class="sxs-lookup"><span data-stu-id="90909-106">After you've identified the set of documents that want to further investigate, you can add the results of the search to an evidence set to further process and analyze.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="90909-107">Create a search</span><span class="sxs-lookup"><span data-stu-id="90909-107">Create a search</span></span>

1. <span data-ttu-id="90909-108">在调查中, 单击 "**搜索**" 选项卡, 然后单击 "**新建搜索**"。</span><span class="sxs-lookup"><span data-stu-id="90909-108">In an investigation, click the **Searches** tab, and then click **New search**.</span></span> 

    <span data-ttu-id="90909-109">将显示一个向导, 引导您完成创建搜索的过程。</span><span class="sxs-lookup"><span data-stu-id="90909-109">A wizard is displayed that will guide you through the process of creating a search.</span></span>

2. <span data-ttu-id="90909-110">为搜索输入搜索名称和可选说明。</span><span class="sxs-lookup"><span data-stu-id="90909-110">Enter a search name and an optional description for the search.</span></span>

3. <span data-ttu-id="90909-111">定义您的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="90909-111">Define your search criteria.</span></span> <span data-ttu-id="90909-112">您可以使用预建的条件卡或使用关键字查询中的搜索属性名称来添加搜索条件。</span><span class="sxs-lookup"><span data-stu-id="90909-112">You can add conditions for the search by using the pre-built condition cards or by using search property names in the keyword query.</span></span> <span data-ttu-id="90909-113">有关详细信息, 请参阅[构建搜索查询](build-search-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="90909-113">For more information, see [Build search queries](build-search-queries.md).</span></span>

4. <span data-ttu-id="90909-114">选择要搜索的内容位置 (数据源)。</span><span class="sxs-lookup"><span data-stu-id="90909-114">Choose the content locations (data sources) to search.</span></span> <span data-ttu-id="90909-115">您可以通过选择感兴趣的特定人员的内容位置 (如果您向调查中添加了任何内容) 来限定搜索范围。</span><span class="sxs-lookup"><span data-stu-id="90909-115">You can scope the search by selecting the content locations of specific people of interest (if you added any to the investigation).</span></span> <span data-ttu-id="90909-116">如果您已向调查中添加了感兴趣的人, 则可以按照[管理相关人员](manage-people-of-interest.md#add-people-of-interest)中的步骤进行添加。</span><span class="sxs-lookup"><span data-stu-id="90909-116">If you have added people of interest to the investigation, you can add them by following the steps in [Manage people of interest](manage-people-of-interest.md#add-people-of-interest).</span></span>
 
    <span data-ttu-id="90909-117">在某些情况下, 您可能需要先搜索组织中的所有内容位置;或者, 您可能需要搜索不是由特定人员所拥有的位置。</span><span class="sxs-lookup"><span data-stu-id="90909-117">In some cases, you may first need to search all content locations in your organization; alternatively, you may need to search locations that aren't owned by a specific person.</span></span> <span data-ttu-id="90909-118">在这种情况下, 您可以选择搜索整个组织或特定 Office 365 服务 (如 Exchange、SharePoint、OneDrive 或团队) 的所有位置。</span><span class="sxs-lookup"><span data-stu-id="90909-118">In this scenarios, you can choose to search your entire organization, or all locations for a specific Office 365 services (such as Exchange, SharePoint, OneDrive of Business, or Teams.</span></span>

5. <span data-ttu-id="90909-119">保存并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="90909-119">Save and run the search.</span></span>

<span data-ttu-id="90909-120">创建搜索后, 会显示一个弹出页面, 其中包含有关搜索的详细信息。</span><span class="sxs-lookup"><span data-stu-id="90909-120">After the search is created, a flyout page is displayed with details about the search.</span></span> <span data-ttu-id="90909-121">请注意,**统计信息**和**预览**按钮最初显示为灰色, 因为搜索尚未完成。</span><span class="sxs-lookup"><span data-stu-id="90909-121">Note that the **Statistics** and **Preview** buttons are initially grayed out because the search hasn't completed.</span></span> <span data-ttu-id="90909-122">您可以通过监视 "**搜索**" 选项卡上的 "**状态**" 列来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="90909-122">You can keep track of the progress of by monitoring the **Status** column on the **Searches** tab.</span></span>

## <a name="view-statistics-and-search-results"></a><span data-ttu-id="90909-123">查看统计信息和搜索结果</span><span class="sxs-lookup"><span data-stu-id="90909-123">View statistics and search results</span></span>

<span data-ttu-id="90909-124">在创建并启动数据调查搜索之后, 该工具将使用您定义的搜索条件 (搜索查询和内容位置), 并在 live service 中搜索符合搜索条件的项目的索引。</span><span class="sxs-lookup"><span data-stu-id="90909-124">After you create and start a data investigation search, the tool uses the search criteria (the search query and content locations) that you defined and searches an index in the live service for items that match your search criteria.</span></span> <span data-ttu-id="90909-125">搜索完成后, 将返回以下三个搜索组件:</span><span class="sxs-lookup"><span data-stu-id="90909-125">There are three components of a search that are returned when the search is complete:</span></span> 

- <span data-ttu-id="90909-126">**估计**-由于搜索仅搜索索引 (而不是实际的内容位置), 因此搜索结果为估计值 (根据在索引中找到的匹配搜索结果的内容)。</span><span class="sxs-lookup"><span data-stu-id="90909-126">**Estimate** - Because the search only searches an index (rather than the actual content locations), the results of a search are an estimate (based on what was found in the index that matched the search results).</span></span> <span data-ttu-id="90909-127">估计的摘要显示在 "**状态**" 下的 "搜索" 飞出页面中。</span><span class="sxs-lookup"><span data-stu-id="90909-127">A summary of the estimate is displayed on the search flyout page under **Status**.</span></span> <span data-ttu-id="90909-128">请注意, 搜索的估计过程的状态将显示在 "**估计状态**" 列中的 "**搜索**" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="90909-128">Note that the status for the estimate process for a search is displayed on the **Searches** tab in the **Estimate status** column.</span></span> <span data-ttu-id="90909-129">搜索估计完成后, 此状态将设置为 "**成功**"。</span><span class="sxs-lookup"><span data-stu-id="90909-129">When the search estimate is complete, this status is set to **Successful**.</span></span>

- <span data-ttu-id="90909-130">**统计**信息-统计信息提供有关搜索结果的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="90909-130">**Statistics** - Statistics provide more detailed information about the search results.</span></span> <span data-ttu-id="90909-131">其中包括：</span><span class="sxs-lookup"><span data-stu-id="90909-131">This includes the following:</span></span>

    - <span data-ttu-id="90909-132">摘要-类似于弹出页面上显示的搜索估计结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="90909-132">Summary - Statistics similar to the search estimate results displayed on the flyout page.</span></span>
    - <span data-ttu-id="90909-133">顶部位置-有关与搜索查询匹配的搜索的每个内容位置中搜索查询的项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="90909-133">Top locations - Statistics about the number of items that match the search query in each content location that was searched.</span></span> 
    - <span data-ttu-id="90909-134">查询-有关搜索查询的详细统计信息, 包括与搜索查询中的每个条件匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="90909-134">Queries - Detailed statistics about the search query, including the number of items that match each condition in a search query.</span></span>

    <span data-ttu-id="90909-135">单击弹出页面上的 "**统计**" 以查看这些统计信息。</span><span class="sxs-lookup"><span data-stu-id="90909-135">Click **Statistics** on the flyout page to view these statistics.</span></span> <span data-ttu-id="90909-136">请注意, 在 "**搜索**" 选项卡上的 "**评估" 状态**的值设置为 "**成功**" 之前, 此按钮处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="90909-136">Note that this button is inactive until the value of the **Estimate status** on the **Searches** tab is set to **Successful**.</span></span> <span data-ttu-id="90909-137">有关搜索统计信息的详细信息, 请参阅[搜索统计](search-statistics.md)信息。</span><span class="sxs-lookup"><span data-stu-id="90909-137">For more information about search statistics, see [Search statistics](search-statistics.md).</span></span>

- <span data-ttu-id="90909-138">**预览**-搜索完成后, 可以从搜索返回的搜索结果的示例子集查看实际项目。</span><span class="sxs-lookup"><span data-stu-id="90909-138">**Preview** - When the search is complete, you can view the actual items from a sample subset of the search results returned by the search.</span></span> <span data-ttu-id="90909-139">您可以在项目类型的本机视图中查看, 任何也可以查看有关该项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="90909-139">YOu can view in the native view of the item type, any you can also view metadata about the item.</span></span> <span data-ttu-id="90909-140">这是快速确定您的搜索结果是否是您所需的, 还是需要编辑并重新运行搜索结果的良好方法。</span><span class="sxs-lookup"><span data-stu-id="90909-140">This is a good way to quickly determine if your search results are what you expected or if you need to edit the search and re-run it.</span></span> <span data-ttu-id="90909-141">单击弹出页面上的 "**预览**" 以查看搜索结果中的项目。</span><span class="sxs-lookup"><span data-stu-id="90909-141">Click  **Preview** on the flyout page to view items from the search results.</span></span> <span data-ttu-id="90909-142">请注意, 在 "**搜索**" 选项卡上的 "**预览状态**" 值设置为 "**成功**" 之前, 此按钮处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="90909-142">Note that this button is inactive until the value of the **Preview status** on the **Searches** tab is set to **Successful**.</span></span>
 
> [!NOTE]
> <span data-ttu-id="90909-143">"**搜索**" 选项卡上的 "**估计状态**" 和 "**预览状态**" 列的状态值将**提交**、**进行中**和**成功**。</span><span class="sxs-lookup"><span data-stu-id="90909-143">The status values for the **Estimate status** and **Preview status** columns on the **Searches** tab are **Submitted**, **In progress**, and **Successful**.</span></span> <span data-ttu-id="90909-144">如果搜索出现错误, 则会显示 "**失败**" 状态。</span><span class="sxs-lookup"><span data-stu-id="90909-144">If there is an error with the search, the status of **Failed** is displayed.</span></span>

## <a name="add-search-results-to-evidence"></a><span data-ttu-id="90909-145">将搜索结果添加到证据</span><span class="sxs-lookup"><span data-stu-id="90909-145">Add search results to evidence</span></span>

<span data-ttu-id="90909-146">当您对搜索结果感到满意并准备好分析和修正这些搜索结果时, 您可以将它们添加到调查中的证据集。</span><span class="sxs-lookup"><span data-stu-id="90909-146">When you're satisfied with the results of a search and you're ready to analyze and remediate those search results, you can add them to an evidence set in the investigation.</span></span> <span data-ttu-id="90909-147">将项目添加到 "**证据**" 选项卡上的证据集时, 将发生以下两种情况:</span><span class="sxs-lookup"><span data-stu-id="90909-147">When you add items to an evidence set on the **Evidence** tab, the following two things occur:</span></span>

- <span data-ttu-id="90909-148">将从 live service 中的数据源复制搜索结果中的所有项目, 并将其复制到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="90909-148">All items in the search results are copied from the data source in the live service, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="90909-149">将对所有项目 (包括内容和元数据) 进行重新编制索引, 以便证据集中的所有数据在调查过程中完全可供搜索。</span><span class="sxs-lookup"><span data-stu-id="90909-149">All items (including the content and metadata) are re-indexed so that all data in the evidence set is fully searchable during your investigation.</span></span> <span data-ttu-id="90909-150">当您在调查过程中搜索证据集中的数据时, 对数据进行重新编制索引将导致完全且快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="90909-150">Re-indexing the data results in thorough and very fast searches when you search the data in the evidence set during your investigation.</span></span>

<span data-ttu-id="90909-151">将实时数据复制到 Azure 中的证据集的一个优点是, 对于时间敏感或关键事件, 您可以通过立即删除 live service 中的原始数据源中的可疑内容, 然后调查事件, 具体方法是分析已复制到 Azure 存储位置的隔离环境的证据。</span><span class="sxs-lookup"><span data-stu-id="90909-151">One advantage of copying the live data to an evidence set in Azure is that for time-sensitive or critical incidents, you can quickly contain the damage by immediately deleting suspicious content in the original data source in the live service and then investigating the incident by analyzing the evidence that was copied to the quarantined environment of the Azure storage location.</span></span> 

<span data-ttu-id="90909-152">将原始数据复制到证据集还可以通过向您提供高级分析工具 (如主题检测、接近重复检测和电子邮件线程标识) 来促进您的调查。</span><span class="sxs-lookup"><span data-stu-id="90909-152">Copying the original data to the evidence set also facilitates your investigation by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span>

<span data-ttu-id="90909-153">如有必要, 您还可以将非 Office 365 数据源中的数据添加到证据集, 以便将其与从 Office 365 中收集的数据存储在一起。</span><span class="sxs-lookup"><span data-stu-id="90909-153">If necessary, you can also add data from non-Office 365 data sources to an evidence set so that it's stored along with the data you collect from Office 365.</span></span>

<span data-ttu-id="90909-154">若要将数据添加到如集, 请在 "**搜索**" 选项卡上选择一个搜索, 然后单击弹出页面上的 "**将结果添加到证据**"。</span><span class="sxs-lookup"><span data-stu-id="90909-154">To add data to an an evidenced set, select a search on the **Searches** tab, and then clicking **Add results to evidence** on the flyout page.</span></span> <span data-ttu-id="90909-155">请注意, 您可以将数据添加到现有证据集, 也可以即时创建新的证据集。</span><span class="sxs-lookup"><span data-stu-id="90909-155">Note that you can add data to an existing evidence set or create a new evidence set on the fly.</span></span>

### <a name="tracking-the-progress-of-adding-search-results-to-evidence"></a><span data-ttu-id="90909-156">跟踪将搜索结果添加到证据的进度</span><span class="sxs-lookup"><span data-stu-id="90909-156">Tracking the progress of adding search results to evidence</span></span>

<span data-ttu-id="90909-157">将数据添加到证据集是一个长期运行的过程。</span><span class="sxs-lookup"><span data-stu-id="90909-157">Adding data to an evidence set is a long-running process.</span></span> <span data-ttu-id="90909-158">该过程包括从 Office 365 中收集原始数据源 (例如, 从邮箱和网站), 并将其复制到 Azure 存储位置 (此复制过程也称为*摄取*), 然后对项目重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="90909-158">The process includes collecting the items the original data source from Office 365 ( for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="90909-159">您可以在 "**作业**" 选项卡上或 "**搜索**" 选项卡上的 "**向证据中添加数据**" 列中跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="90909-159">You can either track the progress on the **Jobs** tab or on the **Searches** tab in the **Added data to evidence** column.</span></span> <span data-ttu-id="90909-160">完成证据处理的处理后, 可以转到 "**证据**" 选项卡, 单击证据集, 然后根据需要搜索、检查、标记和导出相关数据, 从而开始进行调查。</span><span class="sxs-lookup"><span data-stu-id="90909-160">After the processing of evidence processing is completed, you can go to the **Evidence** tab, click the evidence set, and then start your investigation by searching, reviewing, tagging, and exporting the relevant data as necessary.</span></span>