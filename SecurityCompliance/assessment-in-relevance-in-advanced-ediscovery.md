---
title: 了解 Office 365 高级电子数据展示中的相关性评估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: '获取评估阶段和其角色在 Office 365 高级电子数据展示中的相关性培训过程中确定问题的丰富功能的概述。  '
ms.openlocfilehash: a54a4134609b16568586f3cb6b60ebdeba860bac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525414"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6e4b9-103">了解 Office 365 高级电子数据展示中的相关性评估</span><span class="sxs-lookup"><span data-stu-id="6e4b9-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="6e4b9-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6e4b9-p102">高级电子数据展示启用早期评估，例如，定义的问题和用例导入的数据。高级电子数据展示使专家做出决策与采用方法并将它们应用于文档审阅项目。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p102">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case. Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="6e4b9-108">了解评估</span><span class="sxs-lookup"><span data-stu-id="6e4b9-108">Understanding assessment</span></span>

<span data-ttu-id="6e4b9-p103">在评估，专家审阅随机的一组至少 500 文件，用于以确定问题的丰富功能以及生成反映培训结果的统计信息。如果发现足够相关文件要达到统计有助于高级电子数据展示提供准确的统计信息并有效地确定培训进程中的稳定性点的相关性的评估成功。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p103">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results. Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="6e4b9-p104">更高的统计信息，稳定性算法的有效性，更准确评估集中文件相关的次数。评估文件中的相关文件数取决于问题的丰富功能。丰富是中一组相关问题的相关文件的估计的百分比。更丰富的问题将使用较低的丰富比问题更快地达到更多的相关文件。极低丰富的问题 (例如，2%或更少) 需要设置访问大量相关文件的非常大评估。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p104">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm. The number of relevant files within the assessment files depends on the richness of the issue. Richness is the estimated percent of relevant files in the set relevant to an issue. Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness. Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="6e4b9-p105">统计信息，在跟踪和 Decide 选项卡培训期间和之后批次计算显示，包括不同的审阅设置的记忆功能的估计值。基于样本的估计设置 （在本例中为评估文件） 统计信息中包含的误差范围和该错误边距的可信度。例如，80%的估计的撤回可能必须为 95%可信度错误加或减 5%的边距。这意味着，估计的检索是实际 75%-85%具有此估计 95%可信度。越大评估集的误差范围成为较小且更准确统计信息。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p105">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets. In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin. For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%. This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence. The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="6e4b9-p106">专家审阅初始评估套 500 文件后，相关性就可以确定当前检索值的错误的边距。相关性还将设置其所建议的用于访问以优化评估一组的错误的默认边距。以下是一些示例：</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p106">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values. Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set. Following are some examples:</span></span>
  
- <span data-ttu-id="6e4b9-124">如果已设置评估生成错误加或减 10%的边距，将建议相关性将上移动到 （需要没有其他评估审阅） 的培训。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="6e4b9-125">如果评估一组由生成错误加或减 13%的边距，相关性可能建议评估文件到达较小的边距的另一组概述。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="6e4b9-126">如果极低丰富，相关性可能建议停止评估，即使的误差范围是大型 （使不切实际统计信息），因为评估一组需要访问错误的有用边距太大。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="6e4b9-p107">每个问题自己丰富、 当前边距的错误，并且结果是，估计其他评估文件数。评估接下来创建根据 （最多 1,000 个在一组) 的文件的最大数。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p107">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files. The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="6e4b9-p108">您可以接受的相关性建议或根据需要调整错误的当前边距。错误的默认当前边距由检索次数等于或高于 75%。</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p108">You can accept the Relevance recommendations or adjust the current margin of error according to your needs. The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e4b9-p109">评估阶段可以绕过，在**相关性\>跟踪**扩展问题，清除**评估**复选框，每个问题，然后为"所有问题"视图中的选项卡。但是，结果是，将会出现此问题没有统计信息。> 评估执行之前可以仅完成清除**评估**复选框。仅当每个问题清除该复选框案例中存在多个问题，绕过评估</span><span class="sxs-lookup"><span data-stu-id="6e4b9-p109">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e4b9-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e4b9-135">See also</span></span>

[<span data-ttu-id="6e4b9-136">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="6e4b9-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6e4b9-137">标签和评估</span><span class="sxs-lookup"><span data-stu-id="6e4b9-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6e4b9-138">标签和相关性培训</span><span class="sxs-lookup"><span data-stu-id="6e4b9-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6e4b9-139">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="6e4b9-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6e4b9-140">决定基于结果</span><span class="sxs-lookup"><span data-stu-id="6e4b9-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6e4b9-141">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="6e4b9-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

