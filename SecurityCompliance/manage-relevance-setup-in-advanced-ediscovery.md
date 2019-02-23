---
title: 管理 Office 365 高级电子数据展示中的相关性设置
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: 获取有关在 Office 365 高级电子数据展示中设置相关性定型的建议，以计算文件相关性分数并生成分析结果。
ms.openlocfilehash: e2ab772c900068c140e365c10b681da3983bea6b
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215622"
---
# <a name="manage-relevance-setup-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8d086-103">管理 Office 365 高级电子数据展示中的相关性设置</span><span class="sxs-lookup"><span data-stu-id="8d086-103">Manage Relevance setup in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8d086-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="8d086-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="8d086-p102">高级电子数据展示中的相关性技术采用专家指导软件，用于计算文件的相关性分数。高级电子数据展示中的相关性技术可用于早期案件集评估 (ECA)、采集和文件样本审阅。</span><span class="sxs-lookup"><span data-stu-id="8d086-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="8d086-p103">高级电子数据展示包括对与案件集相关的文件执行相关性定型和标记的组件。高级电子数据展示从相关和非相关文件的定型样本中学习，以计算每个文件的相关性分数，并生成可在文件审阅过程期间和之后使用的分析结果。</span><span class="sxs-lookup"><span data-stu-id="8d086-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="8d086-110">相关性定型设置准则</span><span class="sxs-lookup"><span data-stu-id="8d086-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="8d086-p104">在高级电子数据展示内的“案件集”\*\*\*\* 窗口中，选择一个案件集，再单击“转到案件集”\*\*\*\*。依次单击“相关性”\*\*\*\* 和“相关性设置”\*\*\*\*。请遵循下面建议的相关性设置准则。</span><span class="sxs-lookup"><span data-stu-id="8d086-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="8d086-114">**标记**：迭代相关性定型过程的效力取决于专家能否精确、一致地标记文件样本。</span><span class="sxs-lookup"><span data-stu-id="8d086-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="8d086-115">**案件集问题**：</span><span class="sxs-lookup"><span data-stu-id="8d086-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="8d086-p105">对于每个问题，请在整个相关性定型过程中使用相同的专家。禁止多个专家同时标记同一问题。</span><span class="sxs-lookup"><span data-stu-id="8d086-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="8d086-118">确定每组文件是否仅与特定问题相关。</span><span class="sxs-lookup"><span data-stu-id="8d086-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="8d086-p106">如果问题定义过于笼统，高级电子数据展示可能会过多生成实际并不相关的文件。如果问题定义过于狭隘，相关性定型过程的耗时可能更长。</span><span class="sxs-lookup"><span data-stu-id="8d086-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="8d086-121">在每个相关性定型周期中，高级电子数据展示以一个未解决问题为重点，并相应地显示中期样本结果。</span><span class="sxs-lookup"><span data-stu-id="8d086-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="8d086-p107">在多问题方案中，使用采样模式，可以将问题选择纳入处理过程。除非采样模式变化，否则不会处理定义为“关闭”的问题。问题只能对一个专家处于“空闲”或“打开”状态。</span><span class="sxs-lookup"><span data-stu-id="8d086-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="8d086-p108">高级电子数据展示可用于生成候选特权文件。请单独设置特权的相关问题。如果可能，请先定型和采集相关性，再仅对采集的集合定型特权（将采集的集合重新加载为单独的案件集）。</span><span class="sxs-lookup"><span data-stu-id="8d086-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="8d086-p109">仅当没有打开的样本时，才能执行批计算（单击“批计算”后即可查看已打开样本的用户列表）。若要“关闭”其他用户的样本（仅当这些用户不要标记样本时，才能这样做），管理员可以结合使用“修改相关性”实用工具和“所有用户样本”选项。</span><span class="sxs-lookup"><span data-stu-id="8d086-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="8d086-p110">**元数据**：高级电子数据展示以内容为重点，不将元数据视为相关性条件的一部分。</span><span class="sxs-lookup"><span data-stu-id="8d086-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="8d086-132">**丰富度**：如果评估后的问题丰富度低于 3%，建议使用已知的相关和非相关文件为相关性定型设定种子。</span><span class="sxs-lookup"><span data-stu-id="8d086-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="8d086-p111">**文件大小**：相关性忽略大文件（已提取文本的字符数超过 5,242,880 个）。此类文件不参与相关性定型过程，并且在批计算后不会收到相关性分数。大小超过 5MB 的文件可以包含在评估集中。</span><span class="sxs-lookup"><span data-stu-id="8d086-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="8d086-136">设置案件集问题</span><span class="sxs-lookup"><span data-stu-id="8d086-136">Setting up case issues</span></span>

<span data-ttu-id="8d086-137">若要查找此部分介绍的参数，可以在高级电子数据展示内依次单击“相关性”\*\*\*\* 和“相关性设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8d086-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="8d086-138">必须向要定型文件的用户分配问题。</span><span class="sxs-lookup"><span data-stu-id="8d086-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="8d086-139">然后，必须将已导入文件添加到正在处理的负载中。</span><span class="sxs-lookup"><span data-stu-id="8d086-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="8d086-140">谨慎定义和整理问题，因为这可能会影响相关性定型结果。</span><span class="sxs-lookup"><span data-stu-id="8d086-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="8d086-141">设置参数后，审阅者/专家便可以开始在“相关性”\*\*\*\* 选项卡中定型文件。</span><span class="sxs-lookup"><span data-stu-id="8d086-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8d086-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d086-142">See also</span></span>

[<span data-ttu-id="8d086-143">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="8d086-143">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8d086-144">定义问题和分配用户</span><span class="sxs-lookup"><span data-stu-id="8d086-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="8d086-145">设置将已导入文件添加到的负载</span><span class="sxs-lookup"><span data-stu-id="8d086-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="8d086-146">定义突出显示的关键字和高级选项</span><span class="sxs-lookup"><span data-stu-id="8d086-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

