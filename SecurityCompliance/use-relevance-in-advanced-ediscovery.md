---
title: 使用 Office 365 高级电子数据展示中的相关性模块
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: '了解 Office 365 高级电子数据展示，包括工作流和准则，并进行培训和文件的审阅的步骤中的相关性模块。  '
ms.openlocfilehash: 2cf75ef95291c5393367ce01fb0cd660f9b99145
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525165"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="3c47f-103">使用 Office 365 高级电子数据展示中的相关性模块</span><span class="sxs-lookup"><span data-stu-id="3c47f-103">Use the Relevance module in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="3c47f-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="3c47f-p102">在高级电子数据展示，相关性模块包括相关性培训和检查与案例相关的文件。相关性工作流所示，如下所述：</span><span class="sxs-lookup"><span data-stu-id="3c47f-p102">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case. The Relevance workflow is shown and described as follows:</span></span>
  
![相关性工作流](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="3c47f-109">**评估和跟踪的循环**：</span><span class="sxs-lookup"><span data-stu-id="3c47f-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="3c47f-110">**评估**： 高级电子数据展示启用基于文件的随机示例早期评估，并使用此评估将确定预测的编码过程的性能的决策。</span><span class="sxs-lookup"><span data-stu-id="3c47f-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="3c47f-111">**跟踪**： 高级电子数据展示计算并显示监视统计有效性的过程时评估的中间结果。</span><span class="sxs-lookup"><span data-stu-id="3c47f-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="3c47f-112">**培训和跟踪的循环**：</span><span class="sxs-lookup"><span data-stu-id="3c47f-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="3c47f-113">**标记**： 高级电子数据展示学习相关性条件特定于基于专家的迭代查看每个问题和标记的单个文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="3c47f-114">**跟踪**： 高级电子数据展示计算并显示中间结果的相关性培训时监控统计有效性的过程。</span><span class="sxs-lookup"><span data-stu-id="3c47f-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="3c47f-115">**批次计算**： 高级电子数据展示所需的累积和学习相关性条件，将其应用于整个文件集，并生成相关性分数的每个文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="3c47f-116">**Decide**： 高级电子数据展示显示应用于整个案例后批次计算分析的结果，并显示文档审阅决策的数据。</span><span class="sxs-lookup"><span data-stu-id="3c47f-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="3c47f-117">**测试**： 高级电子数据展示结果可以进行测试，以验证的有效性和高级电子数据展示处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="3c47f-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="3c47f-118">相关性培训和审阅准则</span><span class="sxs-lookup"><span data-stu-id="3c47f-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="3c47f-119">以下是概述相关性培训和审阅准则：</span><span class="sxs-lookup"><span data-stu-id="3c47f-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="3c47f-p103">**错误和不一致情况**： 如果在培训过程进行了标记错误，返回到以前的文件示例，用于对其进行更正。如果有太多错误正确或没有在案例或问题的新的角度来看，相关性条件应重新定义由管理员，并且相关性培训重新启动。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p103">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them. If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="3c47f-122">**添加标签和培训**：</span><span class="sxs-lookup"><span data-stu-id="3c47f-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="3c47f-p104">应根据内容仅标记文件。不考虑元数据，例如 custodian、 日期或文件路径。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p104">Files should be tagged based on content only. Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="3c47f-125">执行操作时不考虑日期范围指示文本中的标记文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="3c47f-126">标记文件时，不考虑嵌入式图形的图像。</span><span class="sxs-lookup"><span data-stu-id="3c47f-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="3c47f-p105">如果查看标记时使用的**格式文本视图**图标的文件，不考虑文字的格式。例如，用删除线 （通过其中心指示删除一条横线） 显示 word 仍视为按相关性已分析的文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p105">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text. For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="3c47f-p106">忽略于相关性 （如案例管理器或管理员组） 的文本中相关性将文本视图中显示的文件内容中移除。如果忽略文本的值已定义相关性培训已开始后，新忽略的文本将应用于从点在其中定义创建的示例文件中。忽略文本功能应谨慎，使用，因为其使用可能会降低文件分析的性能</span><span class="sxs-lookup"><span data-stu-id="3c47f-p106">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance. If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined. The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="3c47f-p107">使用**跳过标记**选项仅在必要时。高级电子数据展示不培训基于上跳过的文件。在评估中，如果很难判断文件是否相关，最好是到标记为 Relevant (R) 或不相关 (NR) 尽可能而不是选择**跳过**。当高级电子数据展示计算培训时，它可以然后看到程度如何处理这些类型的文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p107">Use the **Skip tagging** option only when necessary. Advanced eDiscovery does not train based on skipped files. In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**. When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="3c47f-136">应将偶数文件提取文本非常少量标记进行培训作为 R/NR，而不是"跳过"，如果可能。</span><span class="sxs-lookup"><span data-stu-id="3c47f-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="3c47f-137">标记会影响分类器，前提是该文件是可读，可以标记为 R/NR。</span><span class="sxs-lookup"><span data-stu-id="3c47f-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="3c47f-138">在显示的示例文件列表**标记**选项卡上的文件序列号允许用户以返回到文件的原始的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="3c47f-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="3c47f-p108">您可以返回到任何示例并更改评估的标记和培训设置文件。创建接下来的示例时，将应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p108">You can go back to any sample and change the tagging of the assessment and training set files. The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="3c47f-141">应为 PDF 格式的文件的扫描的 Excel 视为相同本机 Excel 文件时标记文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="3c47f-p109">当有疑问有关标记文件的相关性时，请参阅专家。在相关性培训的不正确标签可能会导致更高版本过程中丢失的时间和还可能产生负面影响的总体结果质量。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p109">When in doubt regarding the Relevance tagging of a file, consult an expert. Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="3c47f-144">已定义的关键字的关键字列表将显示在颜色以帮助用户标记时找出有关文件。</span><span class="sxs-lookup"><span data-stu-id="3c47f-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="3c47f-p110">**批次计算**： R/NR 专家将接收的 0 或 100 的分数标记的文件。这适用于标记进行之前批次计算。如果专家批次计算后切换到空闲的问题，并继续标记此问题，新的已标记的分数不可 100/0 但而不显示原始分数。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p110">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100. This applies to tagging made before Batch calculation. If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="3c47f-148">**问题和采样模式**： 问题通常已关闭，它们的工作完成 （稳定相关性培训和执行批次计算） 时取消问题，或当另一个用户正常对问题。</span><span class="sxs-lookup"><span data-stu-id="3c47f-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="3c47f-149">相关性培训中的步骤</span><span class="sxs-lookup"><span data-stu-id="3c47f-149">Steps in Relevance training</span></span>

<span data-ttu-id="3c47f-p111">在**相关性\>跟踪**选项卡上，高级电子数据展示提供建议如何继续在处理中，使用以下接下来的步骤。当每个以下步骤建议相关性培训过程中，如下所述的含义。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p111">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps. The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="3c47f-152">标记 / 继续标记： 文件查看和相关性标记执行每个专家的文件和发出中的示例。</span><span class="sxs-lookup"><span data-stu-id="3c47f-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="3c47f-153">暗示： 现有的示例需要标记。</span><span class="sxs-lookup"><span data-stu-id="3c47f-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="3c47f-154">评估 / 继续评估： 使早期验证案例问题相关性和导入当前的用例文件总体的相关性的初步视图。</span><span class="sxs-lookup"><span data-stu-id="3c47f-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="3c47f-155">暗示： 更多评估所需或建议。</span><span class="sxs-lookup"><span data-stu-id="3c47f-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="3c47f-156">培训 / 继续培训： 期间的高级电子数据展示学习从专家用户标记文件的过程示例，并获取能够标识相关性条件相关的每种情况下上下文中的每个问题。</span><span class="sxs-lookup"><span data-stu-id="3c47f-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="3c47f-157">暗示： 问题需要更多培训;接下来的示例应创建和标记。</span><span class="sxs-lookup"><span data-stu-id="3c47f-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="3c47f-p112">批处理计算： 相关性过程中的高级电子数据展示采用知识培训阶段并将其应用于整个文件填充。相关文件组中的所有文件的相关性评估，并分配的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p112">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population. All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="3c47f-160">稳定隐含： 问题，并可以执行批次计算。</span><span class="sxs-lookup"><span data-stu-id="3c47f-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="3c47f-161">追赶： 相关性指示当专家审阅和标记在推出加载的情况下，从其他文件加载所选文件的示例。</span><span class="sxs-lookup"><span data-stu-id="3c47f-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="3c47f-162">暗示： 已添加的新负载，，，追赶并且才能继续工作。</span><span class="sxs-lookup"><span data-stu-id="3c47f-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="3c47f-163">标记不一致情况： 进程标识，通过高级电子数据展示算法标记可能会产生负面影响分析的过程在文件中的不一致情况。</span><span class="sxs-lookup"><span data-stu-id="3c47f-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="3c47f-164">暗示： 接下来的示例将上一示例中包括已标记的文件和其标记必须重做。</span><span class="sxs-lookup"><span data-stu-id="3c47f-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="3c47f-165">更新分类器： 允许用户应用标记或种子设定的更改。</span><span class="sxs-lookup"><span data-stu-id="3c47f-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="3c47f-166">暗示： 而无需手动运行另一个相关性示例可以应用标记和种子设定的更改。</span><span class="sxs-lookup"><span data-stu-id="3c47f-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="3c47f-167">保持： 相关性培训过程完成。</span><span class="sxs-lookup"><span data-stu-id="3c47f-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="3c47f-168">暗示： 无相关性培训，则需要此位置。</span><span class="sxs-lookup"><span data-stu-id="3c47f-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="3c47f-169">尽管高级电子数据展示将指导您完成此过程中，使用建议的不同阶段的后续步骤，但它还允许您之间的选项卡和网页、 导航和对地址的情况下可能与单个情况下，问题以及相关的选项或文档审阅流程。</span><span class="sxs-lookup"><span data-stu-id="3c47f-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="3c47f-p113">它是可以接受或重写高级电子数据展示处理选项的下一步。如果您想要执行之外的建议的下一步步骤，请单击**下一步**中扩展的问题显示在对话框中列出，单击**修改**按钮旁边的下一步，以及选择另一个下一步步骤选项。</span><span class="sxs-lookup"><span data-stu-id="3c47f-p113">It is possible to accept or override Advanced eDiscovery Next step processing choices. If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3c47f-172">解锁因为它们不受支持的过程中使用此时之后，某些选项可能会被禁用。</span><span class="sxs-lookup"><span data-stu-id="3c47f-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3c47f-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c47f-173">See also</span></span>

[<span data-ttu-id="3c47f-174">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="3c47f-174">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-175">了解评估中相关性</span><span class="sxs-lookup"><span data-stu-id="3c47f-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-176">标签和评估</span><span class="sxs-lookup"><span data-stu-id="3c47f-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-177">标签和相关性培训</span><span class="sxs-lookup"><span data-stu-id="3c47f-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-178">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="3c47f-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-179">决定基于结果</span><span class="sxs-lookup"><span data-stu-id="3c47f-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="3c47f-180">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="3c47f-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

