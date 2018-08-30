---
title: 在 Office 365 高级电子数据展示中跟踪相关性分析
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: '了解如何查看和解释的相关性培训状态和 Office 365 高级电子数据展示中的案例问题的结果。  '
ms.openlocfilehash: a19f7eaabf5dc15eefaa7209ded8261020d0d557
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526059"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="a5612-103">在 Office 365 高级电子数据展示中跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="a5612-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="a5612-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a5612-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a5612-106">在高级电子数据展示，相关性跟踪选项卡显示在标记选项卡中执行的相关性培训的计算的有效性，指示要在相关性迭代培训过程中执行下一步。</span><span class="sxs-lookup"><span data-stu-id="a5612-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="a5612-107">跟踪相关性培训状态</span><span class="sxs-lookup"><span data-stu-id="a5612-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="a5612-108">查看以下详细信息中相关性跟踪案例的问题，如下面的示例的以下**问题名称**对话框中所示。</span><span class="sxs-lookup"><span data-stu-id="a5612-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="a5612-p102">**评估**： 此进度指示器显示哪些一定程度上培训执行到该点的相关性取得了评估目标方面的误差。此外会显示相关性培训结果的丰富功能。</span><span class="sxs-lookup"><span data-stu-id="a5612-p102">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error. The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="a5612-p103">**培训**： 此彩色的进度指示器和工具提示显示指示相关性培训结果稳定性和显示的相关性培训样本数的数值刻度标记每个问题。专家监视迭代相关性培训进程的进度。</span><span class="sxs-lookup"><span data-stu-id="a5612-p103">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue. The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="a5612-113">**批次计算**： 此进度指示器提供相关信息的批次计算完成。</span><span class="sxs-lookup"><span data-stu-id="a5612-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="a5612-114">**下一步**： 显示建议您执行的下一步。</span><span class="sxs-lookup"><span data-stu-id="a5612-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="a5612-p104">在示例中，将显示问题的成功完成的评估，由已完成的颜色进度指示器和复选标记指示。标记正在进行，但这种情况仍被视为不稳定 （还显示工具提示中稳定性状态）。下一个步骤建议"培训"。</span><span class="sxs-lookup"><span data-stu-id="a5612-p104">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark. Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip). The next step recommendation is "Training".</span></span> 
    
    ![相关性跟踪培训第 1 步](media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="a5612-p105">扩展的视图显示的其他信息和选项。显示当前错误边距的当前状态的评估，给定现有 （已标记） 评估文件检索错误边距。</span><span class="sxs-lookup"><span data-stu-id="a5612-p105">The expanded view displays additional information and options. The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="a5612-p106">清除**评估**复选框，每个问题，然后为"所有问题"，可以绕过的评估阶段。但是，结果是，将会出现此问题没有统计信息。> 评估执行之前可以仅完成清除**评估**复选框。仅当每个问题清除该复选框案例中存在多个问题，绕过评估</span><span class="sxs-lookup"><span data-stu-id="a5612-p106">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues". However, as a result, there will be no statistics for this issue. > Clearing the **Assessment** check box can only be done before assessment is performed. Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="a5612-125">当评估未完成与第一个示例文件的设置，评估可能用于标记更多文件下一步。</span><span class="sxs-lookup"><span data-stu-id="a5612-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="a5612-p107">在**相关性** \> **跟踪**、 培训进度指示器和工具提示指示到达稳定性所需的其他示例的估计的数目。这一估算提供所需的其他培训准则。</span><span class="sxs-lookup"><span data-stu-id="a5612-p107">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability. This estimate provides a guideline for the additional training needed.</span></span>
    
    ![相关性跟踪培训](media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="a5612-p108">当您完成标记，如果您需要继续培训，请单击**培训**。从其他培训设置加载的文件生成的文件的另一示例组。然后，您将返回到标记选项卡标记和培训更多的文件。</span><span class="sxs-lookup"><span data-stu-id="a5612-p108">When you're done tagging and if you need to continue training, click **Training**. Another sample set of files is generated from the loaded file set for additional training. You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="a5612-132">达到稳定培训级别</span><span class="sxs-lookup"><span data-stu-id="a5612-132">Reaching stable training levels</span></span>

<span data-ttu-id="a5612-133">评估文件已获得培训稳定级别后，高级电子数据展示可用于批次计算。</span><span class="sxs-lookup"><span data-stu-id="a5612-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5612-p109">通常，三稳定的培训示例后下, 一步是"批次计算"。可能存在异常，例如，与来自早期示例或种子的文件时添加标记文件没有更改。</span><span class="sxs-lookup"><span data-stu-id="a5612-p109">Usually, after three stable training samples, the next step is "Batch calculation". There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="a5612-136">执行批次计算</span><span class="sxs-lookup"><span data-stu-id="a5612-136">Performing Batch calculation</span></span>

<span data-ttu-id="a5612-137">（稳定培训状态显示时的进度栏中，选中标记和稳定状态的工具提示中。） 在培训成功完成后，将作为下一步执行批次计算批次计算应用到整个文件总体，若要评估文件的相关性和分配相关性分数的相关性培训过程中获得的知识。</span><span class="sxs-lookup"><span data-stu-id="a5612-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="a5612-p110">当存在多个问题时，批次进行计算每个问题。在批次计算过程中处理的所有文件时监视进度。</span><span class="sxs-lookup"><span data-stu-id="a5612-p110">When there is more than one issue, Batch calculation is done per issue. During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="a5612-p111">此处，建议的下一步是"None"，这表明，此时任何其他迭代相关性培训是必需的。下一阶段是**相关性\>Decide**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a5612-p111">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point. The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="a5612-142">如果您想要在批次计算后导入新的文件，管理员可以将导入的文件添加到新的负载。</span><span class="sxs-lookup"><span data-stu-id="a5612-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5612-p112">如果您在批次计算过程中单击**取消**，将保存过程已执行。如果您运行再次批次计算，过程将继续从最后一个执行点。</span><span class="sxs-lookup"><span data-stu-id="a5612-p112">If you click **Cancel** during Batch calculation, the process saves what was already executed. If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="a5612-145">评估标记的一致性</span><span class="sxs-lookup"><span data-stu-id="a5612-145">Assessing tagging consistency</span></span>

<span data-ttu-id="a5612-p113">如果文件标记处于不一致，则会影响分析。结果并非最佳或一致性不确定时，可以使用高级电子数据展示标记一致性过程。返回的可能规章标记文件的列表，并且可以审核和重新标记，根据需要。</span><span class="sxs-lookup"><span data-stu-id="a5612-p113">If there are inconsistencies in file tagging, it can affect the analysis. The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt. A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5612-p114">可以在**相关性**中查看以下评估，标记一致性的七个或多个培训舍入后\>**跟踪** \> **问题** \> **详细的结果** \> **培训进度**。一次，此审阅功能的一个问题。</span><span class="sxs-lookup"><span data-stu-id="a5612-p114">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**. This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="a5612-151">在**相关性\>跟踪**，展开问题的行。</span><span class="sxs-lookup"><span data-stu-id="a5612-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="a5612-152">**下一步**的右侧，单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="a5612-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="a5612-153">为**下一步**选项后七个培训示例选择**标记不一致情况**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a5612-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="a5612-p115">选择**标记不一致情况**。**标记**选项卡打开显示重新标记必要的不一致的列表。</span><span class="sxs-lookup"><span data-stu-id="a5612-p115">Select **Tag inconsistencies**. The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="a5612-p116">单击**计算**提交所做的更改。下一步后标记不一致情况"培训"。</span><span class="sxs-lookup"><span data-stu-id="a5612-p116">Click **Calculate** to submit the changes. The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="a5612-158">查看和使用相关性结果</span><span class="sxs-lookup"><span data-stu-id="a5612-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="a5612-p117">在**相关性\>跟踪**选项卡，展开问题的行，旁边**详细的结果**中，单击**视图**。详细的结果窗格是显示，为显示和如下所述。</span><span class="sxs-lookup"><span data-stu-id="a5612-p117">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**. The Detailed results panes are displayed, as shown and described below.</span></span>
  
![相关性培训详细结果](media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="a5612-162">标记摘要</span><span class="sxs-lookup"><span data-stu-id="a5612-162">Tagging summary</span></span>

 <span data-ttu-id="a5612-163">在示例中所示，**标签摘要**评估、 培训和标记流程追赶文件的每个显示总计。</span><span class="sxs-lookup"><span data-stu-id="a5612-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![相关性跟踪标记摘要](media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="a5612-165">Keywords</span><span class="sxs-lookup"><span data-stu-id="a5612-165">Keywords</span></span>

<span data-ttu-id="a5612-p118">关键字是唯一的字符串、 word、 短语或高级电子数据展示由识别的文件是否相关的大量标记为一个文件中的单词的顺序。"包含"列列出关键字，将 weights 重复文件标记为相关中, 和"排除"列列出的关键字和权重文件标记为不相关。</span><span class="sxs-lookup"><span data-stu-id="a5612-p118">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant. The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="a5612-p119">高级电子数据展示分配负数或正数关键字的 weight 值。更高的权重，显示该关键字文件期间批次计算分配更高的相关性分数的可能性就越高。</span><span class="sxs-lookup"><span data-stu-id="a5612-p119">Advanced eDiscovery assigns negative or positive keyword weight values. The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="a5612-170">高级电子数据展示的关键字列表可用于构建一个专家或作为间接健全检查列表进行了补充文件中的任意位置审阅过程。</span><span class="sxs-lookup"><span data-stu-id="a5612-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="a5612-171">培训进度</span><span class="sxs-lookup"><span data-stu-id="a5612-171">Training progress</span></span>

<span data-ttu-id="a5612-172">**培训进度**窗格包括培训进度图形和质量指示器显示，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a5612-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![相关性跟踪培训进度](media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="a5612-174">**培训质量指标**： 显示标记的一致性的分级信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5612-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="a5612-p120">**良好**： 始终标记文件。（显示浅绿色）</span><span class="sxs-lookup"><span data-stu-id="a5612-p120">**Good**: Files are tagged consistently. (Green light displayed)</span></span>
    
- <span data-ttu-id="a5612-p121">**中等**： 某些文件可能规章标记。（显示黄色浅色）</span><span class="sxs-lookup"><span data-stu-id="a5612-p121">**Medium**: Some files may be tagged inconsistently. (Yellow light displayed)</span></span>
    
- <span data-ttu-id="a5612-p122">**警告**： 文件多可能规章标记。（红灯显示）</span><span class="sxs-lookup"><span data-stu-id="a5612-p122">**Warning**: Many files may be tagged inconsistently. (Red light displayed)</span></span>
    
 <span data-ttu-id="a5612-p123">**培训进度图**： 数相比的 F 度量值的相关性培训周期之后显示相关性培训稳定性的程度。随着我们从左边向右移动，在图形，置信区间缩小和由，F 度量值，以及高级电子数据展示相关性以确定稳定性相关性培训的结果时进行优化。</span><span class="sxs-lookup"><span data-stu-id="a5612-p123">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value. As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a5612-p124">相关性使用 F2，其中检索接收精度为两倍权重 F 度量指标。具有的案例高丰富 （超过 25%)，相关性使用 F1 （1:1 比率）。F 度量比率可以配置**相关性设置**中\>**高级的设置**。</span><span class="sxs-lookup"><span data-stu-id="a5612-p124">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision. For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio). The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="a5612-186">批处理计算结果</span><span class="sxs-lookup"><span data-stu-id="a5612-186">Batch calculation results</span></span>

<span data-ttu-id="a5612-187">**批次计算结果**窗格包括已评分的相关性，如下所示的文件数：</span><span class="sxs-lookup"><span data-stu-id="a5612-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="a5612-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="a5612-188">**Success**</span></span>
    
- <span data-ttu-id="a5612-189">**空**： 不包含任何文本，例如，仅/制表符</span><span class="sxs-lookup"><span data-stu-id="a5612-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="a5612-190">**失败**： 由于过多的大小或无法读取</span><span class="sxs-lookup"><span data-stu-id="a5612-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="a5612-191">**Ignored**： 由于过多的大小</span><span class="sxs-lookup"><span data-stu-id="a5612-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="a5612-192">**Nebulous**： 包含无意义的文本或没有功能相关的问题</span><span class="sxs-lookup"><span data-stu-id="a5612-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="a5612-193">为空，失败、 Ignored 或 Nebulous 将收到-1 的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="a5612-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="a5612-194">培训统计信息</span><span class="sxs-lookup"><span data-stu-id="a5612-194">Training statistics</span></span>

<span data-ttu-id="a5612-195">**培训统计信息**窗格显示统计信息和图形根据高级电子数据展示相关性培训的结果。</span><span class="sxs-lookup"><span data-stu-id="a5612-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![相关性跟踪培训统计数据](media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="a5612-197">此视图显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="a5612-197">This view shows the following:</span></span>
  
- <span data-ttu-id="a5612-p125">**查看检索比率**： 比较结果根据相关性分数在假定线性审阅。检索给定设置的审阅设置大小估计。</span><span class="sxs-lookup"><span data-stu-id="a5612-p125">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review. Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="a5612-200">**参数**： 累积计算相关的审阅相对于整个用例文件总体设置的统计信息。</span><span class="sxs-lookup"><span data-stu-id="a5612-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="a5612-201">**查看**： 的文件的百分比，若要查看基于此截止。</span><span class="sxs-lookup"><span data-stu-id="a5612-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="a5612-202">**撤回**： 查看集中文件相关的百分比。</span><span class="sxs-lookup"><span data-stu-id="a5612-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="a5612-p126">**按相关性分数的通讯组**： 中向左暗灰色显示的文件如下截止分数。工具提示显示相对于文件总数设置的审阅文件中的相关性分数和相关的文件的百分比。</span><span class="sxs-lookup"><span data-stu-id="a5612-p126">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score. A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a5612-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5612-205">See also</span></span>

[<span data-ttu-id="a5612-206">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="a5612-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a5612-207">了解评估中相关性</span><span class="sxs-lookup"><span data-stu-id="a5612-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a5612-208">执行操作，并查看评估</span><span class="sxs-lookup"><span data-stu-id="a5612-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a5612-209">执行相关性培训</span><span class="sxs-lookup"><span data-stu-id="a5612-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a5612-210">做出决策基于结果</span><span class="sxs-lookup"><span data-stu-id="a5612-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a5612-211">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="a5612-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

