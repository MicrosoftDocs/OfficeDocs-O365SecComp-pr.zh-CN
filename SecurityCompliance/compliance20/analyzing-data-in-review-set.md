---
title: 在高级电子数据展示中分析评审集中的数据
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
ms.openlocfilehash: cfed07d473f2af367de4cb2e9fe924a29e4123cd
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155204"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="c103f-102">在高级电子数据展示中分析评审集中的数据</span><span class="sxs-lookup"><span data-stu-id="c103f-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="c103f-103">收集的文档数较大时, 可能很难查看所有文档。</span><span class="sxs-lookup"><span data-stu-id="c103f-103">When the number of collected documents is large, it can be quite difficult to review them all.</span></span> <span data-ttu-id="c103f-104">高级电子数据展示提供了大量工具来分析文档, 以减少要查看的文档量而不丢失任何信息, 并帮助您以一致的方式组织文档。</span><span class="sxs-lookup"><span data-stu-id="c103f-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="c103f-105">若要了解有关这些功能的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="c103f-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="c103f-106">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="c103f-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="c103f-107">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="c103f-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="c103f-108">主题</span><span class="sxs-lookup"><span data-stu-id="c103f-108">Themes</span></span>](themes.md)

<span data-ttu-id="c103f-109">若要分析审阅集中的数据, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c103f-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="c103f-110">为你的事例配置分析设置。</span><span class="sxs-lookup"><span data-stu-id="c103f-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="c103f-111">有关详细信息, 请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c103f-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="c103f-112">打开要分析的审阅集。</span><span class="sxs-lookup"><span data-stu-id="c103f-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="c103f-113">单击 "**管理审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="c103f-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="c103f-114">单击 "**分析**"。</span><span class="sxs-lookup"><span data-stu-id="c103f-114">Click **Analyze**.</span></span>

<span data-ttu-id="c103f-115">可以在案例的 "**作业**" 选项卡上检查分析进度。</span><span class="sxs-lookup"><span data-stu-id="c103f-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="c103f-116">完成分析后, 您可以查看分析报告, 在审核的输出集内运行查询 (请参阅[评审集内的查询](review-set-search.md)), 并查看给定文档的相关文档 (请参阅查看[评审数据集中的数据](reviewing-data-in-review-set.md))。</span><span class="sxs-lookup"><span data-stu-id="c103f-116">After analysis is completed, you can view analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="c103f-117">分析报告</span><span class="sxs-lookup"><span data-stu-id="c103f-117">Analytics report</span></span>

<span data-ttu-id="c103f-118">查看审阅集的分析报告:</span><span class="sxs-lookup"><span data-stu-id="c103f-118">To view a analytics report for a review set:</span></span>

1. <span data-ttu-id="c103f-119">打开评审集。</span><span class="sxs-lookup"><span data-stu-id="c103f-119">Open the review set.</span></span>

2. <span data-ttu-id="c103f-120">单击 "**管理审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="c103f-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="c103f-121">单击 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="c103f-121">Click **Report**.</span></span>

<span data-ttu-id="c103f-122">此报告包含来自分析的四个组件:</span><span class="sxs-lookup"><span data-stu-id="c103f-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="c103f-123">**细目**-在审阅集中发现了多少封电子邮件、附件和松散文档。</span><span class="sxs-lookup"><span data-stu-id="c103f-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="c103f-124">**文档 (不包括附件)** -对多个松散文档进行透视、在数据透视的重复的情况下是唯一的, 或者是另一个文档的完全相同。</span><span class="sxs-lookup"><span data-stu-id="c103f-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="c103f-125">**电子**邮件-有多少封电子邮件是 inclusives、包含的副本、包含的 minuses 或以上都不是。</span><span class="sxs-lookup"><span data-stu-id="c103f-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="c103f-126">**附件**-审阅集中另一个电子邮件附件的电子邮件附件数是唯一的或重复的。</span><span class="sxs-lookup"><span data-stu-id="c103f-126">**Attachments** - How many email attachments were unique or duplicates of a another email attachment in the review set.</span></span>