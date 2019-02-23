---
title: 使用 Office 365 高级电子数据展示中的相关性模块
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: '了解 Office 365 高级电子数据展示中的相关性模块, 包括用于培训和文件审阅的工作流和指南以及步骤。  '
ms.openlocfilehash: ad44066c8b00bccacf1f4fe2088aa84096c4db84
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217452"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="075de-103">使用 Office 365 高级电子数据展示中的相关性模块</span><span class="sxs-lookup"><span data-stu-id="075de-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="075de-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="075de-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="075de-p102">在高级电子数据展示中, 相关性模块包含与案例相关的相关文件的相关性培训和审核。相关性工作流如下所示, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="075de-p102">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![相关性工作流](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="075de-109">**评估和跟踪周期**:</span><span class="sxs-lookup"><span data-stu-id="075de-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="075de-110">**评估**: 高级电子数据展示基于文件的随机样本启用早期评估, 并使用此评估来制定决策, 以确定预测编码过程的性能。</span><span class="sxs-lookup"><span data-stu-id="075de-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="075de-111">**跟踪**: 高级电子数据展示计算并显示评估的中间结果, 同时监视流程的统计有效性。</span><span class="sxs-lookup"><span data-stu-id="075de-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="075de-112">**培训和跟踪周期**:</span><span class="sxs-lookup"><span data-stu-id="075de-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="075de-113">**标记**: 高级电子数据展示基于每个问题特定于每个问题的相关性条件, 具体取决于专家对各个文件的迭代检查和标记。</span><span class="sxs-lookup"><span data-stu-id="075de-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="075de-114">**跟踪**: 高级电子数据展示计算并显示相关性培训的中间结果, 同时监视流程的统计有效性。</span><span class="sxs-lookup"><span data-stu-id="075de-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="075de-115">**批量计算**: 高级电子数据展示采用积累和学习的相关标准, 将其应用于整个文件集合, 并生成每个文件的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="075de-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="075de-116">**决定**: 高级电子数据展示显示批量计算后应用于整个事例的分析结果, 并显示用于做出文档审阅决策的数据。</span><span class="sxs-lookup"><span data-stu-id="075de-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="075de-117">**测试**: 可以测试高级电子数据展示结果, 以验证高级电子数据展示处理的有效性和有效性。</span><span class="sxs-lookup"><span data-stu-id="075de-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="075de-118">相关培训和审阅指南</span><span class="sxs-lookup"><span data-stu-id="075de-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="075de-119">下面概述了相关培训和审查指南:</span><span class="sxs-lookup"><span data-stu-id="075de-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="075de-p103">**错误和不一致**: 如果在培训过程中进行了标记错误, 请返回到之前的文件示例以更正这些错误。如果要更正的错误太多, 或者案例或问题的新透视, 则应由管理员重新定义相关性条件, 并重新启动相关性培训。</span><span class="sxs-lookup"><span data-stu-id="075de-p103">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="075de-122">**标记和培训**:</span><span class="sxs-lookup"><span data-stu-id="075de-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="075de-p104">应仅根据内容对文件进行标记。请勿考虑元数据, 例如保管人、date 或 file path。</span><span class="sxs-lookup"><span data-stu-id="075de-p104">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="075de-125">在标记文件时, 不要在文本中考虑日期范围指示。</span><span class="sxs-lookup"><span data-stu-id="075de-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="075de-126">在标记文件时不考虑嵌入的图形图像。</span><span class="sxs-lookup"><span data-stu-id="075de-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="075de-p105">如果在标记时使用**带格式的文本视图**图标查看文件, 则不考虑文本的格式。例如, 带有删除线 (通过其中心的一条水平线指示删除) 的词仍被视为已分析文本的一部分的相关性。</span><span class="sxs-lookup"><span data-stu-id="075de-p105">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text. For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="075de-p106">"忽略应用于相关性的文本" (由 "案例管理者" 或 "管理员" 设置) 将在 "相关性" 文本视图中的显示文件内容中删除。如果 "忽略文本" 的值是在已启动相关性培训之后定义的, 则新的被忽略的文本将应用于从定义该位置创建的示例文件。应慎重使用 Ignore Text 功能, 因为它的使用可能会降低文件分析的性能</span><span class="sxs-lookup"><span data-stu-id="075de-p106">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="075de-p107">仅在必要时使用**跳过标签**选项。高级电子数据展示不会基于跳过的文件进行训练。在评估中, 如果很难判断文件是否相关, 最好在可能时标记相关 (R) 或不相关 (NR), 而不是选择 "**跳过**"。当高级电子数据展示评估培训时, 可以看到这些类型的文件的处理效果。</span><span class="sxs-lookup"><span data-stu-id="075de-p107">Use the **Skip tagging** option only when necessary. Advanced eDiscovery does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="075de-136">即使具有非常少的提取文本的文件, 也应在训练中将其标记为 R/NR, 而不是 "Skip" (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="075de-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="075de-137">只要文件可读, 并且可以将其标记为 R/NR, 标记就会影响分类器。</span><span class="sxs-lookup"><span data-stu-id="075de-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="075de-138">"**标记**" 选项卡上的 "显示的示例文件" 列表中的文件序列号允许用户返回到文件的原始显示顺序。</span><span class="sxs-lookup"><span data-stu-id="075de-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="075de-p108">您可以返回到任何示例并更改评估和培训集文件的标记。将在创建下一个示例时应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="075de-p108">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="075de-141">在标记文件时, PDF 格式的 excel 文件的处理方式应与本机 excel 文件相同。</span><span class="sxs-lookup"><span data-stu-id="075de-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="075de-p109">如果不确定文件的相关性标记, 请咨询专家。在相关性培训期间, 标记错误可能会导致在进程中的时间丢失, 并可能对总体结果的质量产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="075de-p109">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="075de-144">关键字列表中定义的关键字将以颜色显示, 以帮助用户在标记时确定相关文件。</span><span class="sxs-lookup"><span data-stu-id="075de-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="075de-p110">**批量计算**: 由专家标记为 R/NR 的文件将获得0或100的分数。这适用于在批处理计算前进行的标记。如果专家在批量计算后将问题切换到空闲并继续标记此问题, 则新标记的分数不会是 100/0, 而是原始分数。</span><span class="sxs-lookup"><span data-stu-id="075de-p110">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="075de-148">**问题和采样模式**: 当完成工作时, 通常会关闭问题 (相关性培训为 "稳定" 和 "已执行批量计算")、问题取消或其他用户正在处理问题。</span><span class="sxs-lookup"><span data-stu-id="075de-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="075de-149">相关培训中的步骤</span><span class="sxs-lookup"><span data-stu-id="075de-149">Steps in Relevance training</span></span>

<span data-ttu-id="075de-p111">在 "**相关性\>跟踪**" 选项卡中, 高级电子数据展示了在处理过程中如何继续进行操作的建议, 并提供以下后续步骤。如果在相关培训过程中建议执行以下每个步骤, 则会对这些含义进行说明。</span><span class="sxs-lookup"><span data-stu-id="075de-p111">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="075de-152">标记/继续标记: 专家对示例中的每个文件和问题执行的文件审阅和相关性标记。</span><span class="sxs-lookup"><span data-stu-id="075de-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="075de-153">暗示: 现有示例需要加上标记。</span><span class="sxs-lookup"><span data-stu-id="075de-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="075de-154">评估/继续评估: 支持早期验证案例问题相关性, 并初步了解为当前事例导入的文件填充的相关性。</span><span class="sxs-lookup"><span data-stu-id="075de-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="075de-155">暗示: 需要或建议进行更多评估。</span><span class="sxs-lookup"><span data-stu-id="075de-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="075de-156">培训/继续培训: 在此过程中, 高级电子数据展示从标记文件示例的专家学习, 并在每个事例的上下文中找出与每个问题相关的相关条件的功能。</span><span class="sxs-lookup"><span data-stu-id="075de-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="075de-157">含义: 此问题需要更多培训;应创建并标记下一个示例。</span><span class="sxs-lookup"><span data-stu-id="075de-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="075de-p112">批处理计算: 高级电子数据展示在培训阶段获取的知识的相关性过程, 并将其应用于整个文件填充。将评估相关文件组中的所有文件的相关性, 并为其分配相关性分数。</span><span class="sxs-lookup"><span data-stu-id="075de-p112">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="075de-160">暗示: 问题已稳定, 可以执行批处理计算。</span><span class="sxs-lookup"><span data-stu-id="075de-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="075de-161">追赶: 相关性指示当专家在滚动负载方案中从其他文件加载中查看和标记所选文件的示例时。</span><span class="sxs-lookup"><span data-stu-id="075de-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="075de-162">暗示: 添加了新的负载, 需要追赶才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="075de-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="075de-163">标记不一致: 进程通过高级电子数据展示算法识别可能对分析产生负面影响的文件标记过程中的不一致情况。</span><span class="sxs-lookup"><span data-stu-id="075de-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="075de-164">暗示: 下一个示例将包含已在之前的示例中标记的文件, 并且必须恢复它们的标记。</span><span class="sxs-lookup"><span data-stu-id="075de-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="075de-165">更新分类器: 允许用户应用标记或种子设定更改。</span><span class="sxs-lookup"><span data-stu-id="075de-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="075de-166">暗示: 可以应用标记和种子设定更改, 而无需手动运行另一个相关性示例。</span><span class="sxs-lookup"><span data-stu-id="075de-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="075de-167">保留: 相关培训过程已完成。</span><span class="sxs-lookup"><span data-stu-id="075de-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="075de-168">暗示: 此时不需要相关培训。</span><span class="sxs-lookup"><span data-stu-id="075de-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="075de-169">虽然高级电子数据展示引导您完成整个过程, 但建议在不同阶段执行后续步骤, 它还允许您在选项卡和页面之间导航, 并做出选择, 以解决可能与您的个人案例、问题或其他方面相关的情况。文档审阅过程。</span><span class="sxs-lookup"><span data-stu-id="075de-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="075de-p113">可以接受或替代高级电子数据展示后续步骤处理选项。如果要执行除建议的下一步之外的步骤, 请单击对话框中展开的问题显示中列出的**下一步**, 单击下一步旁边的 "**修改**" 按钮, 然后选择另一个 "下一步" 选项。</span><span class="sxs-lookup"><span data-stu-id="075de-p113">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="075de-172">在解锁后, 某些选项可能仍处于禁用状态, 因为在此过程中不支持使用这些选项。</span><span class="sxs-lookup"><span data-stu-id="075de-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="075de-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="075de-173">See also</span></span>

[<span data-ttu-id="075de-174">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="075de-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-175">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="075de-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-176">标记和评估</span><span class="sxs-lookup"><span data-stu-id="075de-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-177">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="075de-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-178">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="075de-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-179">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="075de-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="075de-180">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="075de-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

