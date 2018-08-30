---
title: 根据 Office 365 高级电子数据展示中的结果执行决策
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: '了解如何在 Office 365 高级电子数据展示中的 Decide 选项卡提供数据，可帮助您确定正确的审阅一套案例文件的大小。 '
ms.openlocfilehash: 58a181e00ad5843ccbbde4dcb47050eccf199225
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525119"
---
# <a name="decision-based-on-the-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="73fe0-103">根据 Office 365 高级电子数据展示中的结果执行决策</span><span class="sxs-lookup"><span data-stu-id="73fe0-103">Decision based on the results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="73fe0-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="73fe0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="73fe0-106">在高级电子数据展示，Decide 选项卡提供其他信息来查看和使用决策支持统计信息用于确定案例文件的审阅集的大小。</span><span class="sxs-lookup"><span data-stu-id="73fe0-106">In Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span> 
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="73fe0-107">使用 Decide 选项卡</span><span class="sxs-lookup"><span data-stu-id="73fe0-107">Using the Decide tab</span></span>

![相关性决定](media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="73fe0-109">此选项卡包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="73fe0-109">This tab includes the following:</span></span>
  
- <span data-ttu-id="73fe0-110">**问题**： 从此处，您可以选择列表中的感兴趣的问题。</span><span class="sxs-lookup"><span data-stu-id="73fe0-110">**Issue**: From here, you can select the issue of interest from the list.</span></span> 
    
- <span data-ttu-id="73fe0-p102">**查看检索比率**： 根据相关性分数的高级比较电子数据展示审阅。图表中的截止点表示文件，若要查看，的百分比映射到的相关性分数。这用于在相关性测试阶段以及导出阈值挑选。若要查看的文件数的默认分界点位于检索和精度之间的平衡最好的点。根据目标的成本权衡 （%审阅） 和风险 （%检索次数） 的用户应确定实际的分界点。使用滑块，您可以调整分界点并调整百分比的相关文件要检索和验证决定之前时，请参阅图和参数，影响。</span><span class="sxs-lookup"><span data-stu-id="73fe0-p102">**Review-recall ratio**: Comparison of Advanced eDiscovery review according to Relevance scores. The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score. This is used in the Relevance Test phase and as an Export threshold for culling. The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal. The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>
    
- <span data-ttu-id="73fe0-p103">**参数**： 查看，应该还记得下, 一步相关和总成本参数是相关的相对于整个用例集合设置的审阅累积计算的统计信息。有关这些参数的定义如下所示：</span><span class="sxs-lookup"><span data-stu-id="73fe0-p103">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case. Definitions for these parameters are as follows:</span></span>
    
    <span data-ttu-id="73fe0-118">**查看**： 的文件的百分比，若要查看基于此截止。</span><span class="sxs-lookup"><span data-stu-id="73fe0-118">**Review**: Percentage of files to review based on this cutoff.</span></span> 
    
    <span data-ttu-id="73fe0-119">**撤回**： 查看组中的相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="73fe0-119">**Recall**: Percentage of relevant files in the review set.</span></span> 
    
    <span data-ttu-id="73fe0-120">**下一步相关**： 若要查看并确定当前没有评审中设置的其他相关文件的成本。</span><span class="sxs-lookup"><span data-stu-id="73fe0-120">**Next relevant**: Cost to review and identify an additional relevant file that is not currently in the review set.</span></span> 
    
    <span data-ttu-id="73fe0-p104">**总成本**： 成本查看此案例文件的百分比。成本的参数设置可以通过案例管理器设置。</span><span class="sxs-lookup"><span data-stu-id="73fe0-p104">**Total cost**: Cost for reviewing this percentage of the case files. Cost parameter settings can be set by the Case manager.</span></span>
    
- <span data-ttu-id="73fe0-p105">**按相关性分数的通讯组**： 中向左暗灰色显示的文件如下截止分数。工具提示显示相对于文件总数设置的审阅文件中的相关性分数和相关的文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="73fe0-p105">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
<span data-ttu-id="73fe0-p106">扩展的详细信息窗格中显示的其他详细信息。文件集合图表中的不包括为空或模糊文件。护理亲属文件图表表示文件的都不加载中相关性，但仍计为系列的一部分。</span><span class="sxs-lookup"><span data-stu-id="73fe0-p106">The expanded Details pane displays additional details. Files in collection figures do not include empty or nebulous files. Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73fe0-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73fe0-128">See also</span></span>

[<span data-ttu-id="73fe0-129">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="73fe0-129">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="73fe0-130">了解评估中相关性</span><span class="sxs-lookup"><span data-stu-id="73fe0-130">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="73fe0-131">标签和评估</span><span class="sxs-lookup"><span data-stu-id="73fe0-131">Tagging and Assessment</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="73fe0-132">执行相关性培训</span><span class="sxs-lookup"><span data-stu-id="73fe0-132">Performing Relevance training</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="73fe0-133">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="73fe0-133">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="73fe0-134">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="73fe0-134">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

