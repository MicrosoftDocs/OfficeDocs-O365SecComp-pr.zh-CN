---
title: 跟踪 Office 365 高级电子数据展示中的相关性分析
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: '了解如何查看和解释 Office 365 高级电子数据展示中的案例问题的相关性培训状态和结果。  '
ms.openlocfilehash: 8bdfd2ddb88215b7217d1cc4cdacf2e775a0d977
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264386"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="68c4a-103">跟踪 Office 365 高级电子数据展示中的相关性分析</span><span class="sxs-lookup"><span data-stu-id="68c4a-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="68c4a-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="68c4a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="68c4a-106">在高级电子数据展示中, "相关性跟踪" 选项卡将显示在 "标签" 选项卡中执行的相关性培训的计算有效性, 并指示要在相关的迭代培训过程中执行的下一步。</span><span class="sxs-lookup"><span data-stu-id="68c4a-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="68c4a-107">跟踪相关性培训状态</span><span class="sxs-lookup"><span data-stu-id="68c4a-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="68c4a-108">在关联性跟踪中查看以下有关案例问题的详细信息, 如下面的 "**问题名称**" 对话框示例中所示。</span><span class="sxs-lookup"><span data-stu-id="68c4a-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="68c4a-109">**评估**: 此进度指示器显示对此点执行的相关性培训在误差误差方面达到评估目标的程度。</span><span class="sxs-lookup"><span data-stu-id="68c4a-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="68c4a-110">同时还会显示相关培训结果的丰富程度。</span><span class="sxs-lookup"><span data-stu-id="68c4a-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="68c4a-111">**培训**: 此颜色编码的进度指示器和工具提示显示指示相关性培训结果稳定性和一个数值尺度, 其中显示为每个问题标记的相关性培训样本数。</span><span class="sxs-lookup"><span data-stu-id="68c4a-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="68c4a-112">专家监视迭代相关性培训过程的进度。</span><span class="sxs-lookup"><span data-stu-id="68c4a-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="68c4a-113">**批处理计算**: 此进度指示器提供有关批处理计算完成情况的信息。</span><span class="sxs-lookup"><span data-stu-id="68c4a-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="68c4a-114">**下一步**: 显示要执行的下一步的建议。</span><span class="sxs-lookup"><span data-stu-id="68c4a-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="68c4a-115">在此示例中, 将显示一个已成功完成的问题评估, 由已完成的颜色进度指示器和复选标记指示。</span><span class="sxs-lookup"><span data-stu-id="68c4a-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="68c4a-116">标记已在进行中, 但仍将该事例视为不稳定 (稳定性状态也会在工具提示中显示)。</span><span class="sxs-lookup"><span data-stu-id="68c4a-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="68c4a-117">下一步建议是 "培训"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-117">The next step recommendation is "Training".</span></span> 
    
    ![相关性跟踪培训第 1 步](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="68c4a-119">展开的视图将显示其他信息和选项。</span><span class="sxs-lookup"><span data-stu-id="68c4a-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="68c4a-120">在给定现有 (已标记) 评估文件的情况下, 显示的当前误差边距是当前评估状态下的召回的错误边距。</span><span class="sxs-lookup"><span data-stu-id="68c4a-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="68c4a-121">通过清除每个问题的**评估**复选框, 然后针对 "所有问题", 可以绕过评估阶段。</span><span class="sxs-lookup"><span data-stu-id="68c4a-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="68c4a-122">但因此, 此问题不会提供任何统计信息。</span><span class="sxs-lookup"><span data-stu-id="68c4a-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="68c4a-123">> 清除 "**评估**" 复选框只能在执行评估之前完成。</span><span class="sxs-lookup"><span data-stu-id="68c4a-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="68c4a-124">在案例中存在多个问题的情况下, 仅当针对每个问题清除该复选框时, 才会跳过评估</span><span class="sxs-lookup"><span data-stu-id="68c4a-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="68c4a-125">在第一组示例文件中未完成评估时, 评估可能是添加更多文件的下一步。</span><span class="sxs-lookup"><span data-stu-id="68c4a-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="68c4a-126">在**关联** \> **跟踪**中, 培训进度指示器和工具提示指示达到稳定性所需的额外示例的估计数。</span><span class="sxs-lookup"><span data-stu-id="68c4a-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="68c4a-127">此估计为所需的其他培训提供了指导方针。</span><span class="sxs-lookup"><span data-stu-id="68c4a-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![相关性跟踪培训](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="68c4a-129">完成标记后, 如果需要继续培训, 请单击 "**培训**"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="68c4a-130">另一组示例文件是从加载的文件集生成的, 用于其他培训。</span><span class="sxs-lookup"><span data-stu-id="68c4a-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="68c4a-131">然后, 将返回到 "标记" 选项卡, 以标记和训练更多文件。</span><span class="sxs-lookup"><span data-stu-id="68c4a-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="68c4a-132">达到稳定的培训级别</span><span class="sxs-lookup"><span data-stu-id="68c4a-132">Reaching stable training levels</span></span>

<span data-ttu-id="68c4a-133">在评估文件实现了稳定的培训级别后, 高级电子数据展示可以进行批量计算。</span><span class="sxs-lookup"><span data-stu-id="68c4a-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68c4a-134">通常, 在三个稳定的培训示例之后, 下一步是 "批量计算"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="68c4a-135">例如, 当来自较早示例中的文件的标记发生更改或添加种子文件时, 可能会出现异常。</span><span class="sxs-lookup"><span data-stu-id="68c4a-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="68c4a-136">执行批处理计算</span><span class="sxs-lookup"><span data-stu-id="68c4a-136">Performing Batch calculation</span></span>

<span data-ttu-id="68c4a-137">在成功完成培训后的下一步 (当进度栏显示稳定的培训状态时, 在工具提示中显示选中状态和稳定状态), 批处理计算将作为下一步执行。批量计算将相关培训中获取的知识应用于整个文件填充, 以评估文件的相关性并分配相关性得分。</span><span class="sxs-lookup"><span data-stu-id="68c4a-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="68c4a-138">如果存在多个问题, 则批处理计算在每个问题中完成。</span><span class="sxs-lookup"><span data-stu-id="68c4a-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="68c4a-139">在批处理计算期间, 在处理所有文件时监视进度。</span><span class="sxs-lookup"><span data-stu-id="68c4a-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="68c4a-140">在这里, 建议的下一步是 "无", 这表明此时不需要进行任何额外的迭代相关性培训。</span><span class="sxs-lookup"><span data-stu-id="68c4a-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="68c4a-141">下一阶段是 "**相关性\>决定**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="68c4a-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="68c4a-142">如果要在计算批次后导入新文件, 管理员可以将导入的文件添加到新的负载。</span><span class="sxs-lookup"><span data-stu-id="68c4a-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68c4a-143">如果在批处理计算期间单击 "**取消**", 则该过程会保存已执行的操作。</span><span class="sxs-lookup"><span data-stu-id="68c4a-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="68c4a-144">如果再次运行批处理计算, 该过程将从上次执行的点继续。</span><span class="sxs-lookup"><span data-stu-id="68c4a-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="68c4a-145">评估标记一致性</span><span class="sxs-lookup"><span data-stu-id="68c4a-145">Assessing tagging consistency</span></span>

<span data-ttu-id="68c4a-146">如果文件标记中存在不一致, 则会影响分析。</span><span class="sxs-lookup"><span data-stu-id="68c4a-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="68c4a-147">当结果不是最佳或一致性不确定时, 可以使用高级电子数据展示标记一致性流程。</span><span class="sxs-lookup"><span data-stu-id="68c4a-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="68c4a-148">返回可能不一致的标记文件的列表, 并根据需要对其进行查看和重新标记。</span><span class="sxs-lookup"><span data-stu-id="68c4a-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68c4a-149">在七个或更多的培训完成后, 可在 "**相关性** \> **跟踪** \> **问题** \> " 中查看 "**详细结果** \> **培训进度**" 中的标记一致性。</span><span class="sxs-lookup"><span data-stu-id="68c4a-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="68c4a-150">一次对一个问题完成了此评审。</span><span class="sxs-lookup"><span data-stu-id="68c4a-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="68c4a-151">在**关联\>跟踪**中, 展开问题的行。</span><span class="sxs-lookup"><span data-stu-id="68c4a-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="68c4a-152">在 "**下一步**" 的右侧, 单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="68c4a-153">选择 "**标记不一致**" 作为 "**下一步**" 选项, 7 个培训示例后, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="68c4a-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="68c4a-154">选择**标记不一致**。</span><span class="sxs-lookup"><span data-stu-id="68c4a-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="68c4a-155">将打开 "**标记**" 选项卡, 其中显示了必要时要重新标记的不一致列表。</span><span class="sxs-lookup"><span data-stu-id="68c4a-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="68c4a-156">单击 "**计算**" 以提交更改。</span><span class="sxs-lookup"><span data-stu-id="68c4a-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="68c4a-157">标记不一致的下一步是 "培训"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="68c4a-158">查看和使用相关性结果</span><span class="sxs-lookup"><span data-stu-id="68c4a-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="68c4a-159">在 "**相关性\>跟踪**" 选项卡中, 展开问题的行, 然后单击 "**详细结果**" 旁边的 "**查看**"。</span><span class="sxs-lookup"><span data-stu-id="68c4a-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="68c4a-160">将显示详细的结果窗格, 如下所示, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="68c4a-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相关性培训详细结果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="68c4a-162">标记摘要</span><span class="sxs-lookup"><span data-stu-id="68c4a-162">Tagging summary</span></span>

 <span data-ttu-id="68c4a-163">在下面显示的示例中, "**标记摘要**" 显示了每个评估、培训和追赶文件标记过程的总计。</span><span class="sxs-lookup"><span data-stu-id="68c4a-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![相关性跟踪标记摘要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="68c4a-165">关键字</span><span class="sxs-lookup"><span data-stu-id="68c4a-165">Keywords</span></span>

<span data-ttu-id="68c4a-166">关键字是由高级电子数据展示作为文件是否相关的重要指示器而标识的文件中的唯一字符串、单词、短语或单词序列。</span><span class="sxs-lookup"><span data-stu-id="68c4a-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="68c4a-167">标记为相关的文件中的 "包括" 列列表关键字和权重, "Exclude" 列列出标记为不相关的文件中的关键字和权重。</span><span class="sxs-lookup"><span data-stu-id="68c4a-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="68c4a-168">高级电子数据展示分配负数或正数关键字权重值。</span><span class="sxs-lookup"><span data-stu-id="68c4a-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="68c4a-169">权重越高, 在批处理计算过程中, 将在其中显示关键字的文件分配更高的相关性分数的可能性越高。</span><span class="sxs-lookup"><span data-stu-id="68c4a-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="68c4a-170">高级电子数据展示列表关键字可用于对由专家构建的列表或在文件审阅过程中任意时刻的间接健全检查的补充。</span><span class="sxs-lookup"><span data-stu-id="68c4a-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="68c4a-171">培训进度</span><span class="sxs-lookup"><span data-stu-id="68c4a-171">Training progress</span></span>

<span data-ttu-id="68c4a-172">"**培训进度**" 窗格包括培训进度图和质量指示器的显示, 如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="68c4a-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![相关性跟踪培训进度](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="68c4a-174">**培训质量指示器**: 显示标记一致性的等级, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="68c4a-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="68c4a-175">**优秀**: 文件以一致的方式标记。</span><span class="sxs-lookup"><span data-stu-id="68c4a-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="68c4a-176">(显示绿色光)</span><span class="sxs-lookup"><span data-stu-id="68c4a-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="68c4a-177">**中**: 某些文件的标记可能不一致。</span><span class="sxs-lookup"><span data-stu-id="68c4a-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="68c4a-178">(显示黄色指示灯)</span><span class="sxs-lookup"><span data-stu-id="68c4a-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="68c4a-179">**警告**: 许多文件的标记可能不一致。</span><span class="sxs-lookup"><span data-stu-id="68c4a-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="68c4a-180">(显示的红色指示灯)</span><span class="sxs-lookup"><span data-stu-id="68c4a-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="68c4a-181">**培训进度图**: 显示与 F 度量值相比, 在大量相关培训周期后的相关性培训稳定性程度。</span><span class="sxs-lookup"><span data-stu-id="68c4a-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="68c4a-182">当我们在图形中从左到右移动时, 置信区间会缩小, 并在高级电子数据展示优化时, 与 F 度量标准一起使用, 以确定稳定性。</span><span class="sxs-lookup"><span data-stu-id="68c4a-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68c4a-183">相关性使用 F2 的 F 度量标准, 在这种情况下, 回调的精确度应为精度的两倍。</span><span class="sxs-lookup"><span data-stu-id="68c4a-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="68c4a-184">对于高丰富的情况 (超过 25%), 相关性使用 F1 (1:1 比率)。</span><span class="sxs-lookup"><span data-stu-id="68c4a-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="68c4a-185">可以在**关联设置** \> "**高级设置**" 中配置 F 度量比率。</span><span class="sxs-lookup"><span data-stu-id="68c4a-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="68c4a-186">批量计算结果</span><span class="sxs-lookup"><span data-stu-id="68c4a-186">Batch calculation results</span></span>

<span data-ttu-id="68c4a-187">"**批量计算结果**" 窗格包含为相关性而计分的文件数, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="68c4a-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="68c4a-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="68c4a-188">**Success**</span></span>
    
- <span data-ttu-id="68c4a-189">**空**: 不包含任何文本, 例如, 仅空格/制表符</span><span class="sxs-lookup"><span data-stu-id="68c4a-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="68c4a-190">**失败**: 由于大小过大或无法读取</span><span class="sxs-lookup"><span data-stu-id="68c4a-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="68c4a-191">已**忽略**: 由于大小过大</span><span class="sxs-lookup"><span data-stu-id="68c4a-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="68c4a-192">**Nebulous**: 包含无意义的文本或没有与问题相关的功能</span><span class="sxs-lookup"><span data-stu-id="68c4a-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="68c4a-193">空、失败、被忽略或 Nebulous 将接收相关性分数为-1。</span><span class="sxs-lookup"><span data-stu-id="68c4a-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="68c4a-194">培训统计</span><span class="sxs-lookup"><span data-stu-id="68c4a-194">Training statistics</span></span>

<span data-ttu-id="68c4a-195">"**培训统计信息**" 窗格根据来自高级电子数据展示相关性培训的结果显示统计信息和曲线图。</span><span class="sxs-lookup"><span data-stu-id="68c4a-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相关性跟踪培训统计数据](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="68c4a-197">此视图显示以下内容:</span><span class="sxs-lookup"><span data-stu-id="68c4a-197">This view shows the following:</span></span>
  
- <span data-ttu-id="68c4a-198">**评审-撤回比率**: 根据 hypothetically 线性评审中的相关性分数比较结果。</span><span class="sxs-lookup"><span data-stu-id="68c4a-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="68c4a-199">根据设置的审阅集大小估计撤回。</span><span class="sxs-lookup"><span data-stu-id="68c4a-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="68c4a-200">**参数**: 相对于整个事例的文件填充与评审集相关的累计计算统计信息。</span><span class="sxs-lookup"><span data-stu-id="68c4a-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="68c4a-201">**审阅**: 根据此截止点要审阅的文件百分比。</span><span class="sxs-lookup"><span data-stu-id="68c4a-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="68c4a-202">**召回**: 审阅集中相关文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="68c4a-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="68c4a-203">**按相关性分数分布**: 左侧灰度显示中的文件低于截止分数。</span><span class="sxs-lookup"><span data-stu-id="68c4a-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="68c4a-204">工具提示将显示相关性分数以及相对于文件总数的审阅文件集中文件的相关百分比。</span><span class="sxs-lookup"><span data-stu-id="68c4a-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="68c4a-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68c4a-205">See also</span></span>

[<span data-ttu-id="68c4a-206">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="68c4a-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="68c4a-207">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="68c4a-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68c4a-208">执行和查看评估</span><span class="sxs-lookup"><span data-stu-id="68c4a-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68c4a-209">执行关联性培训</span><span class="sxs-lookup"><span data-stu-id="68c4a-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68c4a-210">根据结果做出决策</span><span class="sxs-lookup"><span data-stu-id="68c4a-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="68c4a-211">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="68c4a-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

