---
title: 了解 Office 365 高级电子数据展示中的相关性评估
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1d33d4fb-91ed-41c0-b72e-5a26eca3a2a7
description: 获取评估阶段及其在 Office 365 高级电子数据展示中的相关性培训期间确定问题丰富程度的角色的概述。
ms.openlocfilehash: 77d9449ad15fd3a53709f2a28a96b06ab54556eb
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598658"
---
# <a name="understand-assessment-in-relevance-in-office-365-advanced-ediscovery"></a><span data-ttu-id="755b5-103">了解 Office 365 高级电子数据展示中的相关性评估</span><span class="sxs-lookup"><span data-stu-id="755b5-103">Understand Assessment in Relevance in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="755b5-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="755b5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="755b5-106">高级电子数据展示支持早期评估, 例如, 针对定义的问题和为事例导入的数据。</span><span class="sxs-lookup"><span data-stu-id="755b5-106">Advanced eDiscovery enables early assessment, for example, for the defined issues and the data imported for a case.</span></span> <span data-ttu-id="755b5-107">高级电子数据展示使专家能够做出与采用方法相关的决策, 并将它们应用于文档审阅项目。</span><span class="sxs-lookup"><span data-stu-id="755b5-107">Advanced eDiscovery enables the expert to make decisions pertaining to an adopted approach and to apply them to the document review project.</span></span>
  
## <a name="understanding-assessment"></a><span data-ttu-id="755b5-108">了解评估</span><span class="sxs-lookup"><span data-stu-id="755b5-108">Understanding assessment</span></span>

<span data-ttu-id="755b5-109">在评估中, 专家将检查至少500文件的随机集, 这些文件用于确定问题的丰富程度并生成反映培训结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="755b5-109">In Assessment, the expert reviews a random set of at least 500 files, which are used to determine the richness of the issues and to produce statistics that reflect the training results.</span></span> <span data-ttu-id="755b5-110">当找到足够的相关文件以达到统计级别时, 将会成功进行评估, 从而帮助高级电子数据展示相关性以提供准确的统计信息, 并在培训过程中有效地确定稳定化点。</span><span class="sxs-lookup"><span data-stu-id="755b5-110">Assessment is successful when enough relevant files are found to reach a statistical level that will help Advanced eDiscovery Relevance to provide accurate statistics and to effectively determine the stabilization point in the training process.</span></span> 
  
<span data-ttu-id="755b5-111">评估集中相关文件的数量越高, 统计信息和稳定性算法的有效性就越准确。</span><span class="sxs-lookup"><span data-stu-id="755b5-111">The higher the number of relevant files in the assessment set, the more accurate the statistics and the effectiveness of the stability algorithm.</span></span> <span data-ttu-id="755b5-112">评估文件中相关文件的数量取决于问题的丰富程度。</span><span class="sxs-lookup"><span data-stu-id="755b5-112">The number of relevant files within the assessment files depends on the richness of the issue.</span></span> <span data-ttu-id="755b5-113">丰富程度是与问题相关的集合中的相关文件的预计百分比。</span><span class="sxs-lookup"><span data-stu-id="755b5-113">Richness is the estimated percent of relevant files in the set relevant to an issue.</span></span> <span data-ttu-id="755b5-114">较大丰富的问题比较低丰富的问题更快地获得更多的相关文件。</span><span class="sxs-lookup"><span data-stu-id="755b5-114">Issues with higher richness will reach a higher number of relevant files more quickly than issues with lower richness.</span></span> <span data-ttu-id="755b5-115">非常低的丰富程度的问题 (例如, 2% 或更低) 将需要非常大的评估设置, 以达到大量相关文件。</span><span class="sxs-lookup"><span data-stu-id="755b5-115">Issues with extremely low richness (for example, 2% or less) will require a very large assessment set to reach a significant number of Relevant files.</span></span>
  
<span data-ttu-id="755b5-116">"跟踪" 和 "决定批次计算后" 选项卡中显示的统计信息包括针对不同审查集的召回估计。</span><span class="sxs-lookup"><span data-stu-id="755b5-116">The statistics, which are presented in the Track and Decide tabs during training and after Batch calculation, include estimations of recall for different review sets.</span></span> <span data-ttu-id="755b5-117">在 "统计信息" 中, 基于示例集的估计 (在此示例中为 "评估文件") 包括错误的边距和该误差边距的置信度级别。</span><span class="sxs-lookup"><span data-stu-id="755b5-117">In statistics, estimations that are based on a sample set (in this case, the assessment files) include the margin of error and the confidence level of that error margin.</span></span> <span data-ttu-id="755b5-118">例如, 估计撤回百分比为 80% 时, 其置信度为 95% 的值可能为正负 5%。</span><span class="sxs-lookup"><span data-stu-id="755b5-118">For example, estimated recall of 80% might have a margin of error of plus or minus 5% with a confidence level of 95%.</span></span> <span data-ttu-id="755b5-119">这意味着估计撤回实际为 75%-85%, 并且此估计的置信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="755b5-119">This means that the estimated recall is actually 75%-85% and this estimation has 95% confidence.</span></span> <span data-ttu-id="755b5-120">评估集越大, 错误的发生幅度变小, 并且统计信息更准确。</span><span class="sxs-lookup"><span data-stu-id="755b5-120">The larger the assessment set, the margin of error becomes smaller and the statistics are more accurate.</span></span> 
  
<span data-ttu-id="755b5-121">在专家查看了500个文件的初始评估集后, 相关性能够确定召回值的误差的当前边距。</span><span class="sxs-lookup"><span data-stu-id="755b5-121">After the expert reviews an initial assessment set of 500 files, Relevance is able to determine the current margin of error of the recall values.</span></span> <span data-ttu-id="755b5-122">相关性还将设置为优化评估集而建议达到的默认误差。</span><span class="sxs-lookup"><span data-stu-id="755b5-122">Relevance will also set a default margin of error that it recommends to reach to optimize the assessment set.</span></span> <span data-ttu-id="755b5-123">以下是一些示例:</span><span class="sxs-lookup"><span data-stu-id="755b5-123">Following are some examples:</span></span>
  
- <span data-ttu-id="755b5-124">如果评估设置已产生了大于或减 10% 的误差, 则相关性将建议继续进行培训 (不需要进行其他评估审查)。</span><span class="sxs-lookup"><span data-stu-id="755b5-124">If the assessment set already yielded a margin of error of plus or minus 10%, Relevance will recommend to move on to training (no additional assessment review is needed).</span></span> 
    
- <span data-ttu-id="755b5-125">如果评估设置已产生的误差为加上或减 13%, 相关性可能建议对另一组评估文件进行审阅, 以达到较小的利润率。</span><span class="sxs-lookup"><span data-stu-id="755b5-125">If the assessment set yielded a margin of error of plus or minus 13%, Relevance might recommend the review of another set of assessment files to reach a smaller margin.</span></span> 
    
- <span data-ttu-id="755b5-126">如果丰富程度极低, 相关性可能建议停止评估, 即使错误的发生幅度很大 (使统计数据不切实际) 也是如此, 因为所需的评估设置过大的误差幅度太大。</span><span class="sxs-lookup"><span data-stu-id="755b5-126">If richness is extremely low, Relevance might recommend stopping assessment even though the margin of error is large (making statistics impractical), because the assessment set needed to reach a useful margin of error is too large.</span></span>
    
<span data-ttu-id="755b5-127">每个问题都有其自己的丰富程度、当前误差范围, 并产生估计的额外评估文件数。</span><span class="sxs-lookup"><span data-stu-id="755b5-127">Each issue has its own richness, current margin of error, and as a result, estimated number of additional assessment files.</span></span> <span data-ttu-id="755b5-128">根据最大文件数 (一组中最多为 1000) 创建下一个评估集。</span><span class="sxs-lookup"><span data-stu-id="755b5-128">The next assessment set is created according to the maximum number of files (up to 1,000 in a single set).</span></span>
  
<span data-ttu-id="755b5-129">您可以接受相关性建议, 也可以根据需要调整当前误差。</span><span class="sxs-lookup"><span data-stu-id="755b5-129">You can accept the Relevance recommendations or adjust the current margin of error according to your needs.</span></span> <span data-ttu-id="755b5-130">在等于或高于 75% 时, 将确定默认的错误当前边距。</span><span class="sxs-lookup"><span data-stu-id="755b5-130">The default current margin of error is determined for recall at equal or above 75%.</span></span>
  
> [!NOTE]
> <span data-ttu-id="755b5-131">通过清除每个问题的 "**评估**" 复选框, 然后针对 "所有问题", 可以绕过评估阶段的展开视图的 "**相关性\>跟踪**" 选项卡中的该问题。</span><span class="sxs-lookup"><span data-stu-id="755b5-131">The Assessment stage can be bypassed, in the **Relevance \> Track** tab in the expanded view for an issue, by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="755b5-132">但因此, 此问题不会提供任何统计信息。</span><span class="sxs-lookup"><span data-stu-id="755b5-132">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="755b5-133">> 清除 "**评估**" 复选框只能在执行评估之前完成。</span><span class="sxs-lookup"><span data-stu-id="755b5-133">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="755b5-134">在案例中存在多个问题的情况下, 仅当针对每个问题清除该复选框时, 才会跳过评估</span><span class="sxs-lookup"><span data-stu-id="755b5-134">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="755b5-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="755b5-135">See also</span></span>

[<span data-ttu-id="755b5-136">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="755b5-136">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="755b5-137">标记和评估</span><span class="sxs-lookup"><span data-stu-id="755b5-137">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="755b5-138">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="755b5-138">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="755b5-139">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="755b5-139">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="755b5-140">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="755b5-140">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="755b5-141">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="755b5-141">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

