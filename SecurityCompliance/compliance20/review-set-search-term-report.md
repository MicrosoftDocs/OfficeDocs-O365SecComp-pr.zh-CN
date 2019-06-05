---
title: 生成评审集的搜索词报告
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 877c0017359ab9193c4cae81cbef4240909053a8
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34714991"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="03e12-102">生成评审集的搜索词报告</span><span class="sxs-lookup"><span data-stu-id="03e12-102">Generate search term report for a review set</span></span>

<span data-ttu-id="03e12-103">在电子数据展示中, 用于查询文档的最常用条件之一是使用关键字搜索词。</span><span class="sxs-lookup"><span data-stu-id="03e12-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="03e12-104">通过识别包含特定关键字 (也称为*术语*) 的文档, 审阅者可开始对其所面临的内容进行深入了解。</span><span class="sxs-lookup"><span data-stu-id="03e12-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="03e12-105">在 Microsoft 365 中的高级电子数据展示中, 可以通过在审阅集中对已保存的查询生成搜索词报告来精确执行此操作。</span><span class="sxs-lookup"><span data-stu-id="03e12-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="03e12-106">步骤 1: 在审阅集中创建保存的查询</span><span class="sxs-lookup"><span data-stu-id="03e12-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="03e12-107">若要生成有意义的搜索词报告, 请创建一个保存的查询, 该查询将定义要为其生成搜索词报告的审阅集中的一组文档。</span><span class="sxs-lookup"><span data-stu-id="03e12-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="03e12-108">例如, 可以使用日期范围或实际的搜索词集 (通过使用关键字条件卡片) 创建查询。</span><span class="sxs-lookup"><span data-stu-id="03e12-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="03e12-109">若要了解有关审阅集查询的详细信息, 请参阅[在审阅集中查询数据](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="03e12-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="03e12-110">步骤 2: 生成搜索词报告</span><span class="sxs-lookup"><span data-stu-id="03e12-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="03e12-111">有两种不同的方法可以生成搜索词报告: 通过您在步骤1中创建的已保存查询的上下文菜单, 或通过搜索词报告管理控制台。</span><span class="sxs-lookup"><span data-stu-id="03e12-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="03e12-112">若要使用上下文菜单, 请打开您在步骤1中创建的已保存查询的上下文菜单, 然后单击 "**生成搜索词报告**"。</span><span class="sxs-lookup"><span data-stu-id="03e12-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="03e12-113">若要使用管理控制台, 请转到 "**管理审阅集" > 查看搜索词报告**", 单击"**新建**", 然后选择您在步骤1中创建的已保存的查询。</span><span class="sxs-lookup"><span data-stu-id="03e12-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="03e12-114">然后, 输入要报告的术语, 由行分隔;如果在第1步使用的关键字条件卡中创建了已保存的查询, 则浮出控件页面将使用保存的查询中使用的第一个关键字条件卡片中的术语预先填充。</span><span class="sxs-lookup"><span data-stu-id="03e12-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="03e12-115">然后, 选择 "最大为三个轴进行报告", 然后单击 "**生成**", 这将启动搜索词报告生成作业。</span><span class="sxs-lookup"><span data-stu-id="03e12-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="03e12-116">什么是透视？</span><span class="sxs-lookup"><span data-stu-id="03e12-116">What is a pivot?</span></span>

<span data-ttu-id="03e12-117">透视是将如何组织报告。</span><span class="sxs-lookup"><span data-stu-id="03e12-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="03e12-118">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="03e12-118">Consider the following example.</span></span>

- <span data-ttu-id="03e12-119">已保存的查询检索10个文档: doc1 到 doc10。</span><span class="sxs-lookup"><span data-stu-id="03e12-119">The saved query retrieves 10 documents: doc1 thru doc10.</span></span>

- <span data-ttu-id="03e12-120">doc1、doc2、doc3、doc4、doc5、doc6 和 doc7 包含术语 "电子数据展示"。</span><span class="sxs-lookup"><span data-stu-id="03e12-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="03e12-121">doc6、doc7、doc8、doc9 和 doc10 包含 "调查" 一词。</span><span class="sxs-lookup"><span data-stu-id="03e12-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="03e12-122">doc1、doc3、doc5、doc7、doc9 来自保管人 A。</span><span class="sxs-lookup"><span data-stu-id="03e12-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="03e12-123">doc2、doc4、doc6、doc8、doc10 来自保管人 B。</span><span class="sxs-lookup"><span data-stu-id="03e12-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="03e12-124">在这种情况下, 如果您要根据保管人生成搜索词 "电子数据展示" 和 "调查", 并在保管人上进行透视, 则搜索词报告将按如下方式进行组织:</span><span class="sxs-lookup"><span data-stu-id="03e12-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="03e12-125">"电子数据展示"-管理员 A: 4 个文档</span><span class="sxs-lookup"><span data-stu-id="03e12-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="03e12-126">"电子数据展示"-管理员 B: 3 个文档</span><span class="sxs-lookup"><span data-stu-id="03e12-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="03e12-127">"调查"-管理员 A: 2 个文档</span><span class="sxs-lookup"><span data-stu-id="03e12-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="03e12-128">"调查"-管理员 B: 3 个文档</span><span class="sxs-lookup"><span data-stu-id="03e12-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="03e12-129">步骤 3: 下载报告</span><span class="sxs-lookup"><span data-stu-id="03e12-129">Step 3: Download report</span></span>

<span data-ttu-id="03e12-130">在搜索术语管理控制台中, 可以跟踪以前创建的搜索词报告作业的状态。</span><span class="sxs-lookup"><span data-stu-id="03e12-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="03e12-131">作业完成后, 可以单击搜索词报告所在的行, 然后单击 "下载", 这将下载 CSV 格式的搜索词报告。</span><span class="sxs-lookup"><span data-stu-id="03e12-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="03e12-132">每个行都有一个 (搜索词, 透视) 元组, 并且每行都包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="03e12-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="03e12-133">检索的文档数量是多少？</span><span class="sxs-lookup"><span data-stu-id="03e12-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="03e12-134">在文档中找到的搜索词有多少次？</span><span class="sxs-lookup"><span data-stu-id="03e12-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="03e12-135">检索到的文档总容量是多少？</span><span class="sxs-lookup"><span data-stu-id="03e12-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="03e12-136">检索了多少个系列？</span><span class="sxs-lookup"><span data-stu-id="03e12-136">How many families were retrieved?</span></span>

- <span data-ttu-id="03e12-137">这些系列的总文档数是多少 (包括没有搜索词的文档) 是什么？</span><span class="sxs-lookup"><span data-stu-id="03e12-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="03e12-138">上述总容量是多少？</span><span class="sxs-lookup"><span data-stu-id="03e12-138">What is the total volume of the above?</span></span>