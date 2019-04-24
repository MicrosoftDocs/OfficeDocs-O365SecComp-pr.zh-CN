---
title: 将搜索结果添加到工作集
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
ms.openlocfilehash: 7830b483190a69e6055fae369580064c5df42f49
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243377"
---
# <a name="add-search-results-to-a-working-set"></a><span data-ttu-id="bff59-102">将搜索结果添加到工作集</span><span class="sxs-lookup"><span data-stu-id="bff59-102">Add search results to a working set</span></span>

<span data-ttu-id="bff59-103">确定并 culled 针对 Exchange、SharePoint 和 OneDrive for business 进行搜索之后, 您可以将结果添加到工作集中。</span><span class="sxs-lookup"><span data-stu-id="bff59-103">After you've identified and culled with searches against Exchange, SharePoint and OneDrive for business, you can add the results to a working set.</span></span> <span data-ttu-id="bff59-104">工作集代表我们将为闪电快速搜索结果编制索引的一组静态文档, 分析电子邮件线索识别 (接近重复检测和主题)。</span><span class="sxs-lookup"><span data-stu-id="bff59-104">Working sets represent a static set of documents that we will index for lightning fast search results, analyze for email thread identification, near duplicate detection and themes.</span></span>  <span data-ttu-id="bff59-105">您还可以将非 office 365 数据源中的数据与从 office 365 中收集的数据并排添加到 live 中。</span><span class="sxs-lookup"><span data-stu-id="bff59-105">You can also add data from Non-Office 365 data sources to live side by side with the data you collect from Office 365.</span></span>

<span data-ttu-id="bff59-106">若要将数据添加到工作集, 请首先选择搜索, 然后在搜索结果中, 单击 "*将结果添加到工作集*" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bff59-106">To add data to a working set, start by selecting a search, in the search results fly out, click the *+ Add results to working set* button.</span></span>

![将数据添加到工作集](../media/c1b4fc00-7a15-4587-b9b0-ce594bb02e4d.png)

<span data-ttu-id="bff59-108">然后, 您可以选择添加到现有工作集或新的*工作集*。</span><span class="sxs-lookup"><span data-stu-id="bff59-108">You can then choose to add to an existing working set or a *New working set*.</span></span>  <span data-ttu-id="bff59-109">如果要添加到新的工作集, 请指定名称并最后单击 "*添加*" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bff59-109">If adding to a new working set, specify the name and finally click the *Add* button.</span></span>

![选择工作集](../media/e8c6ab51-da8d-4c39-9b21-26bfdf453fb9.png)

<span data-ttu-id="bff59-111">将数据添加到工作集是一个长时间运行的过程, 可以在 "作业" 选项卡或 "*搜索*" 选项卡的 "*工作集状态*" 列中跟踪进度。 此过程包括从 Office 365 收集项目并最终摄取 & 索引。</span><span class="sxs-lookup"><span data-stu-id="bff59-111">Adding data to a working set is a long running process, you can either track the progress in the Jobs tab or in the *Working set status* column in the *Searches* tab.  The process includes gathering items from Office 365 and finally Ingestion & Indexing.</span></span>  <span data-ttu-id="bff59-112">工作集处理完成后, 您可以通过单击 "*工作集*" 选项卡, 然后单击工作集导航到工作集。</span><span class="sxs-lookup"><span data-stu-id="bff59-112">Once working set processing is completed, you can navigate to the working set by clicking on the *Working Sets* tab and then clicking on the working set.</span></span>  <span data-ttu-id="bff59-113">然后, 您可以继续搜索、审阅、标记和导出任何相关数据。</span><span class="sxs-lookup"><span data-stu-id="bff59-113">You can then move on to searching, reviewing, tagging and exporting any relevant data.</span></span>

## <a name="adding-a-sample-to-a-working-set"></a><span data-ttu-id="bff59-114">向工作集添加示例</span><span class="sxs-lookup"><span data-stu-id="bff59-114">Adding a sample to a working set</span></span>

<span data-ttu-id="bff59-115">如果要在收集搜索检索到的所有文档之前验证搜索结果的 thorougly, 可以将搜索结果的随机样本添加到工作集, 而不是添加所有内容。</span><span class="sxs-lookup"><span data-stu-id="bff59-115">If you would like to validate your search results more thorougly before collecting all documents that were retrieved by your search, you can add a random sample of the search results to a working set instead of adding everything.</span></span>

<span data-ttu-id="bff59-116">若要向工作集添加示例, 请先选择搜索, 然后在搜索结果浮出控件中, 单击 "*示例*按钮"。</span><span class="sxs-lookup"><span data-stu-id="bff59-116">To add a sample to a working set, start by selecting a search, in the search results flyout, click *Sample* button.</span></span>

<span data-ttu-id="bff59-117">然后, 您可以选择采样的参数。</span><span class="sxs-lookup"><span data-stu-id="bff59-117">You can then choose the parameter of your sampling.</span></span> <span data-ttu-id="bff59-118">有两个选项：</span><span class="sxs-lookup"><span data-stu-id="bff59-118">There are two options:</span></span>
- <span data-ttu-id="bff59-119">置信度级别和间隔: 将选择示例大小以满足给定的统计参数。</span><span class="sxs-lookup"><span data-stu-id="bff59-119">Confidence level and interval: sample size will be chosen to satisfy the given statistical parameters.</span></span>
- <span data-ttu-id="bff59-120">百分比: 根据搜索返回的项目数和所选参数来确定样本大小。</span><span class="sxs-lookup"><span data-stu-id="bff59-120">Percentage: sample size will be determined based on the number of items that was returned by the search, and the chosen parameter.</span></span>

<span data-ttu-id="bff59-121">最后, 选择要向其中添加示例的工作集。</span><span class="sxs-lookup"><span data-stu-id="bff59-121">Finally, choose the working set to add the sample to.</span></span> <span data-ttu-id="bff59-122">在这里, 您可以检查过程的状态, 就像将整个搜索添加到工作集中一样。</span><span class="sxs-lookup"><span data-stu-id="bff59-122">From there, you can check the status of the process just as you would for adding a whole search into a working set.</span></span> 