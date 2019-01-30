---
title: 高级电子数据展示 (Preview) 中的工作集中分析数据
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
ms.openlocfilehash: a6284204fd709bcf936688f36f38f6b3283b1f98
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607423"
---
# <a name="analyzing-data-in-a-working-set-in-advanced-ediscovery-preview"></a><span data-ttu-id="11302-102">高级电子数据展示 (Preview) 中的工作集中分析数据</span><span class="sxs-lookup"><span data-stu-id="11302-102">Analyzing data in a working set in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="11302-p101">大型收集文档数后，它可以是很难查看所有这些错误。高级电子数据展示 （预览） 提供了多种工具来分析的文档，以减少的文档审阅不会丢失任何中的信息，并帮助您组织全面一致的方式的文档数量。若要了解有关这些功能的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11302-p101">When the number of collected documents is large, it can be quite difficult to review them all. Advanced eDiscovery (Preview) provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner. To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="11302-106">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="11302-106">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="11302-107">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="11302-107">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="11302-108">主题</span><span class="sxs-lookup"><span data-stu-id="11302-108">Themes</span></span>](themes.md)

<span data-ttu-id="11302-109">若要分析的工作集的数据：</span><span class="sxs-lookup"><span data-stu-id="11302-109">To analyze data in a working set:</span></span>

1. <span data-ttu-id="11302-p102">配置您的案例分析设置。有关详细信息，请参阅[Configure 搜索和分析 settings](configure-search-analytics-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="11302-p102">Configure analytics settings for your case. For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>
2. <span data-ttu-id="11302-112">打开您要分析的工作集。</span><span class="sxs-lookup"><span data-stu-id="11302-112">Open the working set you wish to analyze.</span></span>
3. <span data-ttu-id="11302-113">转到"管理工作集"。</span><span class="sxs-lookup"><span data-stu-id="11302-113">Go to "Manage working set".</span></span>
4. <span data-ttu-id="11302-114">单击"分析"。</span><span class="sxs-lookup"><span data-stu-id="11302-114">Click "Analyze".</span></span>

<span data-ttu-id="11302-115">在您的情况下，您可以检查作业选项卡中的分析的进度。</span><span class="sxs-lookup"><span data-stu-id="11302-115">You can check the progress of analysis in the Jobs tab in your case.</span></span>

 <span data-ttu-id="11302-116">完成分析后，您可以查看分析报表、 内您工作的运行的查询设置 （有关详细信息，请参阅[设置内您工作的查询](working-set-search.md)） 分析的输出和查看给定文档 （有关详细信息，请参阅[的相关的文档查看工作集中的数据](reviewing-data-in-working-set.md))。</span><span class="sxs-lookup"><span data-stu-id="11302-116">Once analysis is completed, you can view analytics report, run queries within your working set on outputs of the analysis (for more information see [Query within your working set](working-set-search.md)), and see related documents of a given document (for more information see [Reviewing data in working set](reviewing-data-in-working-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="11302-117">分析报告</span><span class="sxs-lookup"><span data-stu-id="11302-117">Analytics report</span></span>

<span data-ttu-id="11302-118">若要查看您的工作集分析报表：</span><span class="sxs-lookup"><span data-stu-id="11302-118">To view a analytics report for your working set:</span></span>

1. <span data-ttu-id="11302-119">打开您的工作集。</span><span class="sxs-lookup"><span data-stu-id="11302-119">Open your working set.</span></span>
2. <span data-ttu-id="11302-120">转到"管理工作集"。</span><span class="sxs-lookup"><span data-stu-id="11302-120">Go to "Manage working set".</span></span>
3. <span data-ttu-id="11302-121">单击"报告"。</span><span class="sxs-lookup"><span data-stu-id="11302-121">Click "Report".</span></span>

<span data-ttu-id="11302-122">报告已从分析的四个组件：</span><span class="sxs-lookup"><span data-stu-id="11302-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="11302-123">**细分**-多少电子邮件、 附件和松散文档中的工作集找到。</span><span class="sxs-lookup"><span data-stu-id="11302-123">**Breakdown** - How many emails, attachments, and loose documents were found in the working set.</span></span>

- <span data-ttu-id="11302-124">**（不包括附件） 的文档**-多少个松散文档已数据透视表，唯一靠近的数据透视副本或完全相同的另一个文档。</span><span class="sxs-lookup"><span data-stu-id="11302-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="11302-125">**电子邮件**-多少封电子邮件已 inclusives、 非独占副本、 非独占技术或以上皆非。</span><span class="sxs-lookup"><span data-stu-id="11302-125">**Emails** - How many emails were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="11302-126">**附件**-多少电子邮件附件已唯一或复制的工作集内的不同的电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="11302-126">**Attachments** - How many email attachments were unique or duplicates of a different email attachment within the working set.</span></span>