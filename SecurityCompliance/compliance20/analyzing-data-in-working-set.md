---
title: 在高级电子数据展示中分析工作集中的数据 (预览)
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
ms.openlocfilehash: e3f3e863423fe4312a944eb6f04a58182e11665c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295475"
---
# <a name="analyze-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="ee1a6-102">在高级电子数据展示中分析工作集中的数据 (预览)</span><span class="sxs-lookup"><span data-stu-id="ee1a6-102">Analyze data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="ee1a6-p101">收集的文档数较大时, 可能很难查看所有文档。高级电子数据展示 (预览版) 提供多种工具来分析文档, 以减少要查看的文档量而不丢失任何信息, 并帮助您以一致的方式组织文档。若要了解有关这些功能的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="ee1a6-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="ee1a6-106">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="ee1a6-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="ee1a6-107">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="ee1a6-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="ee1a6-108">主题</span><span class="sxs-lookup"><span data-stu-id="ee1a6-108">Themes</span></span>](themes.md)

<span data-ttu-id="ee1a6-109">若要分析工作集中的数据, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ee1a6-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="ee1a6-p102">为你的事例配置分析设置。有关详细信息, 请参阅[配置搜索和分析设置](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="ee1a6-112">打开您想要分析的工作集。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="ee1a6-113">转到 "管理工作集"。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="ee1a6-114">单击 "分析"。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-114">Click "Analyze".</span></span>

<span data-ttu-id="ee1a6-115">您可以在您的情况中检查 "作业" 选项卡中的分析进度。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="ee1a6-116">分析完成后, 您可以查看分析报告、在工作集内运行查询输出的结果 (有关详细信息, 请参阅在[工作集中的查询](working-set-search.md)) 和查看给定文档的相关文档 (有关详细信息, 请参阅[检查工作集中的数据](reviewing-data-in-working-set.md))。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="ee1a6-117">分析报告</span><span class="sxs-lookup"><span data-stu-id="ee1a6-117">Analytics report</span></span>

<span data-ttu-id="ee1a6-118">若要查看工作集的分析报告, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ee1a6-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="ee1a6-119">打开您的工作集。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-119">Open your working set.</span></span>
2. <span data-ttu-id="ee1a6-120">转到 "管理工作集"。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="ee1a6-121">单击 "报告"。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-121">Click "Report".</span></span>

<span data-ttu-id="ee1a6-122">此报告包含来自分析的四个组件:</span><span class="sxs-lookup"><span data-stu-id="ee1a6-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="ee1a6-123">**细目**-工作集中发现了多少封电子邮件、附件和松散文档。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="ee1a6-124">**文档 (不包括附件)** -对多个松散文档进行透视、在数据透视的重复的情况下是唯一的, 或者是另一个文档的完全相同。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="ee1a6-125">**电子邮件**-inclusives 有多少封电子邮件, 包括副本, 包括 minuses 或以上都不是。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="ee1a6-126">**附件**-工作集中的不同电子邮件附件的电子邮件附件数是唯一的或重复的。</span><span class="sxs-lookup"><span data-stu-id="ee1a6-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>