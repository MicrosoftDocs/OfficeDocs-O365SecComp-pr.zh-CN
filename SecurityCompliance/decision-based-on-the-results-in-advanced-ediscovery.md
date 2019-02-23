---
title: 根据 Office 365 高级电子数据展示中的结果执行决策
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解 Office 365 高级电子数据展示中的 "确定" 选项卡如何提供可帮助您确定检查事例文件集的正确大小的数据。 '
ms.openlocfilehash: c4767e703d03ef5dbdb808332e873d22094d7bca
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216102"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="3b0e7-103">根据 Office 365 高级电子数据展示中的结果执行决策</span><span class="sxs-lookup"><span data-stu-id="3b0e7-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="3b0e7-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="3b0e7-106">在高级电子数据展示中, "决定" 选项卡提供了其他信息, 用于查看和使用决策支持统计信息来确定审阅事例文件集的大小。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="3b0e7-107">使用 "决定" 选项卡</span><span class="sxs-lookup"><span data-stu-id="3b0e7-107">Using the Decide tab</span></span>

![相关性决定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="3b0e7-109">此选项卡包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="3b0e7-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="3b0e7-110">**问题**: 在此处, 你可以从列表中选择感兴趣的问题。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="3b0e7-p102">**复查-撤回比率**: 根据相关性分数比较高级电子数据展示检查。图表中的截止点表示要查看的文件百分比, 映射到相关性分数。这在关联测试阶段使用, 用作用于剔除的导出阈值。默认的截止点 (要查看的文件数) 是撤回和精度之间的平衡最佳的时间点。实际的截止点应根据目标和成本权衡 (% 考评) 和风险 (% 撤回) 来确定用户。使用滑块, 可以调整截止点, 并查看图表和参数上的效果、调整要检索的相关文件的百分比以及验证决策之前的效果。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="3b0e7-p103">**参数**: 查看、撤回、下一个相关的和总成本参数是与整个事例的集合相关的相对于评审集的累计计算统计信息。这些参数的定义如下所示:</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="3b0e7-118">**审阅**: 根据此截止点要审阅的文件百分比。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="3b0e7-119">**召回**: 审阅集中相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="3b0e7-120">**下一步相关**: 查看的成本并标识当前不在审阅集中的其他相关文件。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="3b0e7-p104">**总成本**: 查看此百分比事例文件所需的成本。成本参数设置可由事例管理器进行设置。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="3b0e7-p105">**按相关性分数分布**: 左侧灰度显示中的文件低于截止分数。工具提示将显示相关性分数以及相对于文件总数的审阅文件集中文件的相关百分比。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="3b0e7-p106">展开的详细信息窗格将显示其他详细信息。集合中的文件不包含空或 nebulous 文件。"系列文件" 图表示未在相关性中加载但仍作为系列一部分计数的文件。</span><span class="sxs-lookup"><span data-stu-id="3b0e7-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3b0e7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b0e7-128">See also</span></span>

[<span data-ttu-id="3b0e7-129">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3b0e7-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3b0e7-130">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="3b0e7-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3b0e7-131">标记和评估</span><span class="sxs-lookup"><span data-stu-id="3b0e7-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3b0e7-132">执行关联性培训</span><span class="sxs-lookup"><span data-stu-id="3b0e7-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3b0e7-133">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="3b0e7-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3b0e7-134">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="3b0e7-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

