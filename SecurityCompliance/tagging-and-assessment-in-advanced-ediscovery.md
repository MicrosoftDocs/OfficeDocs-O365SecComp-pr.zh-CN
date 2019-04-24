---
title: Office 365 高级电子数据展示中的标记和评估
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
description: '查看执行评估培训的步骤, 包括标记文件, 并查看 Office 365 高级电子数据展示中的评估结果。 '
ms.openlocfilehash: 02dae23b6489b40243272beea1d79e871ca6a911
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260340"
---
# <a name="tagging-and-assessment-in-office-365-advanced-ediscovery"></a><span data-ttu-id="3d075-103">Office 365 高级电子数据展示中的标记和评估</span><span class="sxs-lookup"><span data-stu-id="3d075-103">Tagging and Assessment in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="3d075-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3d075-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="3d075-106">本节介绍高级电子数据展示相关性评估模块的过程。</span><span class="sxs-lookup"><span data-stu-id="3d075-106">This section describes the procedure for the Advanced eDiscovery Relevance Assessment module.</span></span> 
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="3d075-107">执行评估培训和分析</span><span class="sxs-lookup"><span data-stu-id="3d075-107">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="3d075-108">在 "**相关性\>跟踪**" 选项卡中, 单击 "**评估**以启动案例评估"。</span><span class="sxs-lookup"><span data-stu-id="3d075-108">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span> 
    
    <span data-ttu-id="3d075-109">例如, 在此过程中, 将创建一个包含500个文件的示例评估集, 并显示 "**标记**" 选项卡, 其中包含 "标记" 面板、显示的 "文件内容" 和 "其他标记" 选项。</span><span class="sxs-lookup"><span data-stu-id="3d075-109">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 
    
    ![评估的相关性标记选项卡](media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="3d075-111">查看示例中的每个文件, 为每个事例问题确定文件的相关性, 并使用 "**标记" 面板**窗格中的相关性 (R)、"不相关" ("NR") 和 "跳过" 按钮标记文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-111">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="3d075-112">评估需要500带标记的文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-112">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="3d075-113">如果文件被 "跳过", 您将收到更多文件以进行标记。</span><span class="sxs-lookup"><span data-stu-id="3d075-113">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="3d075-114">在示例中为所有文件添加标签后, 单击 "**计算**"。</span><span class="sxs-lookup"><span data-stu-id="3d075-114">After tagging all files in the sample, click **Calculate**.</span></span> 
    
    <span data-ttu-id="3d075-115">评估当前错误边距和丰富程度将计算并显示在 "**相关性跟踪**" 选项卡中, 每个问题的详细信息都已展开, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="3d075-115">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="3d075-116">有关此对话框的更多详细信息将在后面的 "审阅评估结果" 一节中介绍。</span><span class="sxs-lookup"><span data-stu-id="3d075-116">More details about this dialog are described in the later section "Reviewing Assessments results".</span></span> 
    
    ![相关性跟踪 - 评估](media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="3d075-118">默认情况下, 建议您在问题的评估进度指示器已完成时继续执行默认的下一步, 这表明评估示例已评审并标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-118">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="3d075-119">> 否则, 如果要查看 "**跟踪**" 选项卡结果并控制错误和下一步的边距, 请依次单击 "**修改**至**下一步**" 和 "**继续评估**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="3d075-119">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span> 
  
1. <span data-ttu-id="3d075-120">单击 "**评估**" 复选框右侧的 "**修改**", 查看并指定每个问题的评估参数。</span><span class="sxs-lookup"><span data-stu-id="3d075-120">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="3d075-121">将显示每个问题的 "**评估级别**" 对话框, 如以下示例所示:</span><span class="sxs-lookup"><span data-stu-id="3d075-121">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 
    
    ![评估级别案例问题](media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="3d075-123">在 "**评估级**" 对话框中计算并显示问题的以下参数:</span><span class="sxs-lookup"><span data-stu-id="3d075-123">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 
    
    <span data-ttu-id="3d075-124">**撤回估计的目标误差**: 根据此值, 计算需要审阅的额外文件的估计数量。</span><span class="sxs-lookup"><span data-stu-id="3d075-124">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="3d075-125">用于撤回的边距大于 75%, 可信度为 95%。</span><span class="sxs-lookup"><span data-stu-id="3d075-125">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span> 
    
    <span data-ttu-id="3d075-126">**所需的其他评估文件**: 指示在当前错误边距的要求尚未满足时, 需要多少更多文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-126">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 
    
2. <span data-ttu-id="3d075-127">若要调整当前错误边距并查看不同误差边距的效果 (每个问题), 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3d075-127">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>
    
1. <span data-ttu-id="3d075-128">在 "**选择问题**" 列表中, 选择一个问题。</span><span class="sxs-lookup"><span data-stu-id="3d075-128">In the **Select issue** list, select an issue.</span></span> 
    
2. <span data-ttu-id="3d075-129">在 "**撤回估计的目标错误边距**" 中, 输入一个新值。</span><span class="sxs-lookup"><span data-stu-id="3d075-129">In **Target error margin for recall estimates**, enter a new value.</span></span>
    
3. <span data-ttu-id="3d075-130">单击 "**更新值**" 以查看调整的影响。</span><span class="sxs-lookup"><span data-stu-id="3d075-130">Click **Update values** to see the impact of the adjustments.</span></span> 
    
3. <span data-ttu-id="3d075-131">单击 "**评估级**" 对话框中的 "**高级**", 查看以下其他参数和详细信息:</span><span class="sxs-lookup"><span data-stu-id="3d075-131">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 
    
    ![评估级别案例问题高级视图](media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    <span data-ttu-id="3d075-133">**估计丰富**程度: 根据当前评估结果估计的丰富程度</span><span class="sxs-lookup"><span data-stu-id="3d075-133">**Estimated richness**: Estimated richness according to the current assessment results</span></span>
    
    <span data-ttu-id="3d075-134">**对于 "假定撤回**:" 默认情况下, 目标错误边距适用于 75% 以上的召回。</span><span class="sxs-lookup"><span data-stu-id="3d075-134">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="3d075-135">如果要在不同的撤回值范围内更改此参数并控制错误的宽度, 请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3d075-135">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 
    
    <span data-ttu-id="3d075-136">**置信度级别**: 默认情况下, 建议的误差边距为 95%。</span><span class="sxs-lookup"><span data-stu-id="3d075-136">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="3d075-137">如果要更改此参数, 请单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3d075-137">Click **Edit** if you want to change this parameter.</span></span> 
    
    <span data-ttu-id="3d075-138">**预期丰富程度误差边距**: 如果已更新值, 则在审阅所有其他评估文件之后, 这是大量丰富的错误的预期边距。</span><span class="sxs-lookup"><span data-stu-id="3d075-138">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>
    
    <span data-ttu-id="3d075-139">**所需的其他评估文件**: 根据已更新的值, 需要查看的其他评估文件的数量才能到达目标。</span><span class="sxs-lookup"><span data-stu-id="3d075-139">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>
    
    <span data-ttu-id="3d075-140">**所需的评估文件总数**: 假设更新的值、检查所需的总评估文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-140">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>
    
    <span data-ttu-id="3d075-141">**评估中预期的相关文件数**: 在审阅所有其他评估文件后, 已知更新的值、整个评估中的预期相关文件数。</span><span class="sxs-lookup"><span data-stu-id="3d075-141">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>
    
4. <span data-ttu-id="3d075-142">如果更改了参数, 请单击 "**重新计算值**"。</span><span class="sxs-lookup"><span data-stu-id="3d075-142">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="3d075-143">完成后, 如果存在一个问题, 请单击 **"确定"** 保存更改 (如果有多个问题要查看或修改然后**完成**, 请单击 "**下一步**")。</span><span class="sxs-lookup"><span data-stu-id="3d075-143">When you are done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 
    
    <span data-ttu-id="3d075-144">如果存在多个问题, 在所有问题都经过评审或调整之后, 将显示一个**评估级别: 摘要**对话框, 如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="3d075-144">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 
    
    ![评估级别摘要](media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="3d075-146">在成功完成评估后, 请继续阅读相关培训中的下一阶段。</span><span class="sxs-lookup"><span data-stu-id="3d075-146">Upon successful completion of assessment, proceed to the next stage in Relevance training.</span></span>
    
## <a name="reviewing-assessment-results"></a><span data-ttu-id="3d075-147">查看评估结果</span><span class="sxs-lookup"><span data-stu-id="3d075-147">Reviewing assessment results</span></span>

<span data-ttu-id="3d075-148">在标记评估示例后, 评估结果将计算并显示在 "相关性跟踪" 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="3d075-148">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="3d075-149">已展开的曲目显示中显示以下结果:</span><span class="sxs-lookup"><span data-stu-id="3d075-149">The following results are displayed in the expanded Track display:</span></span> 
  
- <span data-ttu-id="3d075-150">评估撤回估计的当前错误边距</span><span class="sxs-lookup"><span data-stu-id="3d075-150">Assessment current error margin for recall estimates</span></span>
    
- <span data-ttu-id="3d075-151">估计丰富程度</span><span class="sxs-lookup"><span data-stu-id="3d075-151">Estimated richness</span></span>
    
- <span data-ttu-id="3d075-152">所需的其他评估文件 (审阅)</span><span class="sxs-lookup"><span data-stu-id="3d075-152">Additional assessment files required (for review)</span></span>
    
<span data-ttu-id="3d075-153">评估当前误差边距是高级电子数据展示建议的错误边距。</span><span class="sxs-lookup"><span data-stu-id="3d075-153">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="3d075-154">为 "所需的其他评估文件" 显示的数字对应于该建议。</span><span class="sxs-lookup"><span data-stu-id="3d075-154">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="3d075-155">评估进度指示器显示评估的完成级别, 在给定当前错误边距的情况下。</span><span class="sxs-lookup"><span data-stu-id="3d075-155">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="3d075-156">在进行评估时, 用户将标记另一个评估示例。</span><span class="sxs-lookup"><span data-stu-id="3d075-156">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="3d075-157">评估进度指示器显示评估为 "已完成" 时, 表示已完成评估示例评审并标记了足够的相关文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-157">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="3d075-158">展开的跟踪显示将显示建议的下一步、评估统计信息和对详细结果的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3d075-158">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="3d075-159">当丰富程度极低时, 要生成有用的相关文件所需的额外评估文件数非常高。</span><span class="sxs-lookup"><span data-stu-id="3d075-159">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="3d075-160">然后, 高级电子数据展示将建议迁移到 "培训"。</span><span class="sxs-lookup"><span data-stu-id="3d075-160">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="3d075-161">评估进度指示器将带阴影显示, 并且不会有任何统计信息可用。</span><span class="sxs-lookup"><span data-stu-id="3d075-161">The assessment progress indicator will be shaded, and no statistics will be available.</span></span> 
  
<span data-ttu-id="3d075-162">如果没有基于统计的稳定性, 则会有较低级别的精确性和置信度的结果。</span><span class="sxs-lookup"><span data-stu-id="3d075-162">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="3d075-163">但是, 当您不需要知道找到的相关文件的百分比时, 可以使用这些结果查找相关文件。</span><span class="sxs-lookup"><span data-stu-id="3d075-163">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="3d075-164">同样, 此状态也可用于培训较低丰富的问题, 其中相关性分数可加快对与特定问题相关的文件的访问。</span><span class="sxs-lookup"><span data-stu-id="3d075-164">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="3d075-165">在 "**相关性\>跟踪**" 选项卡中, 展开 "问题显示" 中, 可以使用以下查看选项: > 建议的下一步, 如**下一步:** 通过单击 "**修改**" 按钮, 可以绕过标记 (每个问题)右键, 然后在**下一步**中选择不同的步骤。</span><span class="sxs-lookup"><span data-stu-id="3d075-165">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available: > The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="3d075-166">如果评估进度指示器尚未完成, 则评估将是下一个推荐的选项, 以标记更多评估文件并提高统计信息准确性。</span><span class="sxs-lookup"><span data-stu-id="3d075-166">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> <span data-ttu-id="3d075-167">> 您可以通过单击 "**修改**", 并在 "**评估级别" 对话框**中更改 "**撤回估计" 的目标误差**, 然后单击 "**更新值**" 来更改错误边距并评估其影响。</span><span class="sxs-lookup"><span data-stu-id="3d075-167">> You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="3d075-168">此外, 在此对话框中, 可以通过单击 "**高级**" 来查看高级选项。</span><span class="sxs-lookup"><span data-stu-id="3d075-168">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> <span data-ttu-id="3d075-169">> 您可以通过单击 "**视图**" 来查看其他评估级别统计信息及其影响。</span><span class="sxs-lookup"><span data-stu-id="3d075-169">> You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="3d075-170">在显示的 "详细结果" 对话框中, 如果有至少500个标记的评估文件, 并且至少18个文件已标记为与问题相关, 则统计信息将可用于每个问题。</span><span class="sxs-lookup"><span data-stu-id="3d075-170">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3d075-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d075-171">See also</span></span>

[<span data-ttu-id="3d075-172">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3d075-172">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3d075-173">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="3d075-173">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3d075-174">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="3d075-174">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3d075-175">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="3d075-175">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3d075-176">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="3d075-176">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3d075-177">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="3d075-177">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

