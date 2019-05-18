---
title: 将搜索结果添加到审阅集
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
ms.openlocfilehash: 4de390972672509422e055cd3fd6a9f65d54a7ba
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155234"
---
# <a name="add-search-results-to-a-review-set"></a><span data-ttu-id="0c834-102">将搜索结果添加到审阅集</span><span class="sxs-lookup"><span data-stu-id="0c834-102">Add search results to a review set</span></span>

<span data-ttu-id="0c834-103">当您对搜索结果感到满意并准备好查看和分析这些搜索结果时, 您可以将其添加到审阅集 (在案例中)。</span><span class="sxs-lookup"><span data-stu-id="0c834-103">When you're satisfied with the results of a search and you're ready to review and analyze those search results, you can add them to a review set in the case.</span></span> <span data-ttu-id="0c834-104">将原始数据复制到评审集还可为您提供高级分析工具, 如主题检测、接近重复检测和电子邮件线程标识, 从而促进评审和分析过程。</span><span class="sxs-lookup"><span data-stu-id="0c834-104">Copying the original data to the review set also facilitates the review and analysis process by providing you with advanced analytics tools such as themes detection, near-duplicate detection, and email thread identification.</span></span> <span data-ttu-id="0c834-105">您还可以将非 Office 365 数据源中的数据添加到检查集, 以便除了从 Office 365 收集的数据之外, 还可以查看数据。</span><span class="sxs-lookup"><span data-stu-id="0c834-105">You can also add data from non-Office 365 data sources to a review set so that you can review that data in addition to the data you collect from Office 365.</span></span>

<span data-ttu-id="0c834-106">将搜索结果添加到审阅集时 (检查集位于事例的**审查集**选项卡上) 时, 将发生以下两种情况:</span><span class="sxs-lookup"><span data-stu-id="0c834-106">When you add the results of a search to a review set (review sets are located on the **Review sets** tab of the case), the following two things occur:</span></span>

- <span data-ttu-id="0c834-107">搜索结果中的所有项目都将从 live Office 365 服务中的原始数据源复制, 并复制到 Microsoft 云中的安全 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="0c834-107">All items in the search results are copied from the original data source in the live Office 365 services, and copied to a secure Azure storage location in the Microsoft cloud.</span></span>

- <span data-ttu-id="0c834-108">将对所有项目 (包括内容和元数据) 进行重新编制索引, 以便审核集中的所有数据在对事例数据的审阅期间完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="0c834-108">All items (including the content and metadata) are re-indexed so that all data in the review set is fully searchable during the review of the case data.</span></span> <span data-ttu-id="0c834-109">当您在案例调查过程中搜索评审集中的数据时, 对数据进行重新编制索引会导致完全且快速的搜索。</span><span class="sxs-lookup"><span data-stu-id="0c834-109">Re-indexing the data results in thorough and very fast searches when you search the data in the review set during the case investigation.</span></span>

<span data-ttu-id="0c834-110">若要将数据添加到审阅集, 请单击 "**搜索**" 选项卡上的搜索, 然后单击浮出控件页面上的 "**添加结果以查看检查设置**"。</span><span class="sxs-lookup"><span data-stu-id="0c834-110">To add data to a review set, click a search on the **Searches** tab and then click **Add results to review set** on the flyout page.</span></span>

![向评审集添加数据](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="0c834-112">请注意, 您可以添加到现有的审阅集, 也可以创建新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="0c834-112">Note that you can add to an existing review set or create a new review set.</span></span>  <span data-ttu-id="0c834-113">如果添加到新的审阅集, 请指定名称, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="0c834-113">If adding to a new review set, specify the name and then click **Add**.</span></span>

![选择评审集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="0c834-115">向评审集添加数据是一个长期运行的过程。</span><span class="sxs-lookup"><span data-stu-id="0c834-115">Adding data to a review set is a long-running process.</span></span> <span data-ttu-id="0c834-116">此过程包括从 Office 365 中的原始数据源 (例如, 从邮箱和网站) 中收集项目, 将它们复制到 Azure 存储位置 (此复制过程也称为 "*摄取*"), 然后对项目重新编制索引。</span><span class="sxs-lookup"><span data-stu-id="0c834-116">This process includes gathering items from the original data sources in Office 365 (for example, from mailboxes and sites), copying them to the Azure storage location (this copying process is also called *ingestion*), and then re-indexing the items.</span></span> <span data-ttu-id="0c834-117">您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="0c834-117">You can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span> <span data-ttu-id="0c834-118">完成审阅集处理后, 单击该事例中的 "**查看集**" 选项卡, 然后单击 "检查设置" 以启动进程筛选、查看、标记和导出审阅集中的数据。</span><span class="sxs-lookup"><span data-stu-id="0c834-118">After the review set processing is completed, click the **Review sets** tab in the case, and then click the review set to start the process filtering, reviewing, tagging, and exporting data in the review set.</span></span>

## <a name="add-a-sample-to-a-review-set"></a><span data-ttu-id="0c834-119">向评审集添加示例</span><span class="sxs-lookup"><span data-stu-id="0c834-119">Add a sample to a review set</span></span>

<span data-ttu-id="0c834-120">如果要在将所有搜索结果添加到审阅集之前更全面地验证搜索结果, 您可以将搜索结果的示例添加到审阅集, 而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="0c834-120">If you want to validate the results of a search more thoroughly before adding all of them to a review set, you can add a sample of the search results to a review set instead of adding everything.</span></span>

<span data-ttu-id="0c834-121">若要向审阅集添加示例, 请单击 "**搜索**" 选项卡上的搜索, 然后单击浮出控件页面上的 "**示例**"。</span><span class="sxs-lookup"><span data-stu-id="0c834-121">To add a sample to a review set, click a search on the **Searches** tab and click **Sample** on the flyout page.</span></span> <span data-ttu-id="0c834-122">在 "**采样参数**" 页上, 选择下列选项之一:</span><span class="sxs-lookup"><span data-stu-id="0c834-122">On the **Sampling parameters** page, choose one of the following options:</span></span>

- <span data-ttu-id="0c834-123">**可信度百分比**和**可信度间隔百分比**-添加到审阅集的项目将由您设置的统计参数决定。</span><span class="sxs-lookup"><span data-stu-id="0c834-123">**Confidence level %** and **Confidence interval %** - The items added to the review set will be determined by the statistical parameters that you set.</span></span> <span data-ttu-id="0c834-124">如果您通常在采样结果时使用置信度和间隔, 请在下拉框中进行指定。</span><span class="sxs-lookup"><span data-stu-id="0c834-124">If you typically use a confidence level and interval when sampling results, specify them in the drop-down boxes.</span></span> <span data-ttu-id="0c834-125">否则, 只需使用默认设置即可。</span><span class="sxs-lookup"><span data-stu-id="0c834-125">Otherwise, just use the default settings.</span></span>

- <span data-ttu-id="0c834-126">**随机样本百分比**-添加到审阅集的项目基于由搜索返回的总项目数的指定百分比的随机选择。</span><span class="sxs-lookup"><span data-stu-id="0c834-126">**Random sample %** - The items added to the review set is based on a random selection of the specified percentage of the total number of items returned by the search.</span></span>

<span data-ttu-id="0c834-127">选择并配置上述选项之一后, 选择一个现有的审阅集以将示例添加到, 然后单击 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="0c834-127">After selecting and configuring one of the previous options, choose an existing review set to add the sample to and then click **Send**.</span></span> <span data-ttu-id="0c834-128">同样, 您可以在 "**作业**" 选项卡或 "**搜索**" 选项卡上通过监视 "添加的**数据到评审集**" 列中的状态来跟踪进度。</span><span class="sxs-lookup"><span data-stu-id="0c834-128">Again, you can track the progress on the **Jobs** tab or on the **Searches** tab by monitoring the status in the **Added data to review set** column.</span></span>