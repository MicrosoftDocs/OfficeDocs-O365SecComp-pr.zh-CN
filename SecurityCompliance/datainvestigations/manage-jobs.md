---
title: 在数据调查中管理作业
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
ms.openlocfilehash: 6779b9eaf5cd07dbc88f400542b6016e91ec9f4c
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029927"
---
# <a name="manage-jobs-in-data-investigations-preview"></a><span data-ttu-id="30d5d-102">在数据调查中管理作业 (预览)</span><span class="sxs-lookup"><span data-stu-id="30d5d-102">Manage jobs in Data Investigations (Preview)</span></span>

<span data-ttu-id="30d5d-103">下面列出了在数据调查 (预览) 中调查的 "**作业**" 选项卡上跟踪的作业 (通常是长期运行的过程)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-103">Here's a list of the jobs (which are typically long-running processes) that are tracked on the **Jobs** tab of an investigation in Data Investigations (Preview).</span></span> <span data-ttu-id="30d5d-104">这些作业是在使用和管理调查时由用户操作触发的。</span><span class="sxs-lookup"><span data-stu-id="30d5d-104">These jobs are triggered by user actions when using and managing investigations.</span></span>

| <span data-ttu-id="30d5d-105">作业类型 </span><span class="sxs-lookup"><span data-stu-id="30d5d-105">Job type</span></span>           | <span data-ttu-id="30d5d-106">描述</span><span class="sxs-lookup"><span data-stu-id="30d5d-106">Description</span></span>     |
| :----------------- | :----------     |
|<span data-ttu-id="30d5d-107">将数据添加到证据集</span><span class="sxs-lookup"><span data-stu-id="30d5d-107">Adding data to an evidence set</span></span> | <span data-ttu-id="30d5d-108">用户将搜索结果添加到证据集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-108">A user adds the results of a search to an evidence set.</span></span>  <span data-ttu-id="30d5d-109">有关详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-109">For more information, see [Search for data in an investigation](search-for-data.md).</span></span> |
|<span data-ttu-id="30d5d-110">将数据添加到另一个证据集</span><span class="sxs-lookup"><span data-stu-id="30d5d-110">Adding data to another evidence set</span></span> | <span data-ttu-id="30d5d-111">用户将一个证据集的文档添加到同一事例中的不同证据集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-111">A user adds documents from one evidence set to a different evidence set in the same case.</span></span>|
|<span data-ttu-id="30d5d-112">将非 Office 365 数据添加到证据集</span><span class="sxs-lookup"><span data-stu-id="30d5d-112">Adding non-Office 365 data to an evidence set</span></span> | <span data-ttu-id="30d5d-113">用户将非 Office 365 数据上传到证据集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-113">A user uploads non-Office 365 data to an evidence set.</span></span> <span data-ttu-id="30d5d-114">在此过程中, 还会对数据编制索引。</span><span class="sxs-lookup"><span data-stu-id="30d5d-114">The data is also indexed during this process.</span></span> <span data-ttu-id="30d5d-115">例如, 将本地文件服务器或客户端计算机中的文件上传到证据集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-115">For example, files from an on-premises file server or a client computer are uploaded to an evidence set.</span></span> <span data-ttu-id="30d5d-116">有关详细信息, 请参阅将[非 Office 365 数据加载到证据](load-non-office365-data.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-116">For more information, see [Load non-Office 365 data into evidence](load-non-office365-data.md).</span></span>| 
|<span data-ttu-id="30d5d-117">将修正的数据添加到证据集</span><span class="sxs-lookup"><span data-stu-id="30d5d-117">Adding remediated data to an evidence set</span></span> | <span data-ttu-id="30d5d-118">将修正带有处理错误的数据, 并将其重新加载回证据集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-118">Data with processing errors is remediated and loaded back into an evidence set.</span></span> <span data-ttu-id="30d5d-119">有关详细信息, 请参阅[处理调查数据时的错误修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-119">For more information, see [Error remediation when processing data for an investigation](error-remediation.md).</span></span> | 
|<span data-ttu-id="30d5d-120">比较负载集</span><span class="sxs-lookup"><span data-stu-id="30d5d-120">Comparing load sets</span></span> | <span data-ttu-id="30d5d-121">用户查看证据集内不同加载集之间的差异。</span><span class="sxs-lookup"><span data-stu-id="30d5d-121">A user looks at the differences between different load sets in an evidence set.</span></span> <span data-ttu-id="30d5d-122">加载集是将数据添加到证据集的实例。</span><span class="sxs-lookup"><span data-stu-id="30d5d-122">A load set is an instance of adding data to an evidence set.</span></span> <span data-ttu-id="30d5d-123">例如, 如果将两个不同搜索的结果添加到相同的证据集, 每个搜索将代表一个负载集。</span><span class="sxs-lookup"><span data-stu-id="30d5d-123">For example, if you add the results of two different searches to the same evidence set, each would represent a load set.</span></span> <span data-ttu-id="30d5d-124">有关详细信息, 请参阅[管理加载集](manage-load-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-124">For more information, see [Manage load sets](manage-load-sets.md).</span></span> |
|<span data-ttu-id="30d5d-125">将编辑文档转换为 PDF</span><span class="sxs-lookup"><span data-stu-id="30d5d-125">Converting redacted documents to PDF</span></span>|<span data-ttu-id="30d5d-126">在用户 annotates 证据集内的文档并修订其中的一部分后, 他们可以选择将编辑文档转换为 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="30d5d-126">After a user annotates a document in an evidence set and redacts a portion of it, they can choose to convert the redacted document to a PDF file.</span></span> <span data-ttu-id="30d5d-127">这样可确保在导出文档以供演示文稿 whenf, 编辑部分将不可见。</span><span class="sxs-lookup"><span data-stu-id="30d5d-127">This ensures that the redacted portion will not be visible whenf the document is exported for presentation.</span></span> <span data-ttu-id="30d5d-128">有关详细信息, 请参阅[在证据中查看数据](review-data-in-evidence.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-128">For more information, see [Review data in evidence](review-data-in-evidence.md).</span></span> |
|<span data-ttu-id="30d5d-129">估计搜索结果</span><span class="sxs-lookup"><span data-stu-id="30d5d-129">Estimating search results</span></span> | <span data-ttu-id="30d5d-130">在用户创建并运行新的搜索 (或重新运行现有搜索) 后, 搜索工具会在索引中搜索与搜索查询匹配的项目, 并准备一个估计, 其中包括搜索的所有项目的数量和总大小, 以及数据源海洋的数量。rched。</span><span class="sxs-lookup"><span data-stu-id="30d5d-130">After a user creates and runs a new search (or re-runs an existing search), the search tool searches the index for items that match the search query and prepares a estimate that includes the number and total size of all items by the search, and the number of data sources searched.</span></span>  <span data-ttu-id="30d5d-131">有关详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-131">For more information, see [Search for data in an investigation](search-for-data.md).</span></span> | 
|<span data-ttu-id="30d5d-132">准备数据以供导出</span><span class="sxs-lookup"><span data-stu-id="30d5d-132">Preparing data for export</span></span> | <span data-ttu-id="30d5d-133">用户从证据集导出文档。</span><span class="sxs-lookup"><span data-stu-id="30d5d-133">A user exports documents from a from an evidence set.</span></span> <span data-ttu-id="30d5d-134">导出过程完成后, 可以将导出的数据下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="30d5d-134">When the export process is complete, they can download the exported data to a local computer.</span></span> <span data-ttu-id="30d5d-135">有关详细信息, 请参阅[从调查中导出数据](export-data.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-135">For more information, see [Export data from an investigation](export-data.md).</span></span> | 
|<span data-ttu-id="30d5d-136">为错误解决做准备</span><span class="sxs-lookup"><span data-stu-id="30d5d-136">Preparing for error resolution</span></span> |<span data-ttu-id="30d5d-137">当用户在调查的 "**处理**" 选项卡上的 "错误" 视图中选择文件并创建新的错误修正时, 该过程中的第一步是将具有处理错误的文件上传到 Microsoft 云中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="30d5d-137">When a user selects a file and creates a new error remediation in the Error view on the **Processing** tab of an investigation, the first step in the process is to upload the file that has the processing error to an Azure storage location in the Microsoft cloud.</span></span> <span data-ttu-id="30d5d-138">此作业跟踪上载过程的进度。</span><span class="sxs-lookup"><span data-stu-id="30d5d-138">This job tracks the progress of the upload process.</span></span> <span data-ttu-id="30d5d-139">有关错误修正工作流的详细信息, 请参阅[在处理调查数据时出现错误修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-139">For more information about the error remediation workflow, see [Error remediation when processing data for an investigation](error-remediation.md).</span></span>| 
|<span data-ttu-id="30d5d-140">准备搜索预览</span><span class="sxs-lookup"><span data-stu-id="30d5d-140">Preparing search preview</span></span> | <span data-ttu-id="30d5d-141">在用户创建并运行新的搜索 (或重新运行现有搜索) 后, 搜索工具准备可预览的项的示例子集 (与搜索查询匹配)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-141">After a  user creates and runs a new search (or re-runs an existing search), the search tool prepare a sample subset of items (that match the search query) that can be previewed.</span></span> <span data-ttu-id="30d5d-142">预览搜索结果可帮助您确定搜索的有效性。</span><span class="sxs-lookup"><span data-stu-id="30d5d-142">Previewing search results can help you determine the effectiveness of the search.</span></span>  <span data-ttu-id="30d5d-143">有关详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-143">For more information, see [Search for data in an investigation](search-for-data.md).</span></span> | 
|<span data-ttu-id="30d5d-144">重新编制感兴趣的人员的数据索引</span><span class="sxs-lookup"><span data-stu-id="30d5d-144">Re-indexing data of people of interest</span></span> | <span data-ttu-id="30d5d-145">在向调查中添加感兴趣的人时, 会通过名为 "*高级索引*" 的过程对所选的数据源中的所有部分索引项目重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="30d5d-145">When you add a person of interest to an investigation, all partially indexed items in the person of interest's selected data sources are re-indexed by a process called *Advanced indexing*.</span></span> <span data-ttu-id="30d5d-146">在调查的 "**处理**" 选项卡上单击 "在索引视图中**更新索引**" 时也会触发此作业。</span><span class="sxs-lookup"><span data-stu-id="30d5d-146">This job is also triggered when you click **Update index** in Index view on the **Processing** tab of an investigation.</span></span> <span data-ttu-id="30d5d-147">有关详细信息, 请参阅[对数据进行高级索引以进行调查](index-data-people-of-interest.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-147">For more information, see [Advanced indexing of data for an investigation](index-data-people-of-interest.md).</span></span>
|<span data-ttu-id="30d5d-148">运行分析</span><span class="sxs-lookup"><span data-stu-id="30d5d-148">Running analytics</span></span> | <span data-ttu-id="30d5d-149">用户通过运行分析工具 (如近期重复检测、电子邮件线程分析和主题分析) 来分析证据集中的数据。</span><span class="sxs-lookup"><span data-stu-id="30d5d-149">A user analyzes data in an evidence set by running analytics tools such as near duplicate detection, email threading analysis, and themes analysis.</span></span> <span data-ttu-id="30d5d-150">有关详细信息, 请参阅[运行分析以加快检查速度](run-analytics-to-investigate-faster.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-150">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span> | 
|<span data-ttu-id="30d5d-151">标记文档</span><span class="sxs-lookup"><span data-stu-id="30d5d-151">Tagging documents</span></span> | <span data-ttu-id="30d5d-152">当用户在证据集中审阅文档时, 当用户单击 "**标记" 面板**中的 "**开始标记作业**" 时, 将触发此作业。</span><span class="sxs-lookup"><span data-stu-id="30d5d-152">This job is triggered when a user clicks **Start tagging job** in the **Tagging panel** when reviewing documents in an evidence set.</span></span> <span data-ttu-id="30d5d-153">用户可以在证据集中对文档进行标记, 然后在 "查看文档" 面板中批量选择这些文档, 从而启动此作业。</span><span class="sxs-lookup"><span data-stu-id="30d5d-153">A user can start this job after tagging documents in an evidence set and then bulk-selecting them in the view document panel.</span></span> <span data-ttu-id="30d5d-154">有关详细信息, 请参阅[在证据中标记文档](tag-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="30d5d-154">For more information, see [Tag documents in evidence](tag-documents.md).</span></span> | 
|||