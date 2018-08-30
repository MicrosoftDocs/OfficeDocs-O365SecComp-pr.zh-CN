---
title: 在 Office 365 高级电子数据展示中设置加载以添加导入的文件
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: '查看导入的文件添加到最后一个定义的负载或批，在 Office 365 高级电子数据展示中执行相关性培训之前的文件的步骤。  '
ms.openlocfilehash: 2c986578b969b671351930fd6939a90e3a821dc2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525927"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2b7cf-103">在 Office 365 高级电子数据展示中设置加载以添加导入的文件</span><span class="sxs-lookup"><span data-stu-id="2b7cf-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="2b7cf-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="2b7cf-p102">在高级电子数据展示，负载为一批新的文件添加到用例。默认情况下，定义一个负载和所有导入的文件添加到它。在执行之前相关性培训，必须导入的文件添加到负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p102">In Advanced eDiscovery, a load is a new batch of files added to a case. By default, one load is defined and all imported files are added to it. Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="2b7cf-109">请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="2b7cf-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="2b7cf-p103">新的文件将已知类似于以前的文件加载到区分大小的数据库，或文件的以前负载是一组随机从文件集合。在此情况下，将添加到当前文件加载的导入的文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p103">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection. In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="2b7cf-p104">新的文件 （例如，来自不同源） 的以前的或不同必须它们相似或以前加载到不同没有预备知识。在此方案中，将添加到新文件加载的导入的文件。高级电子数据展示识别为滚动加载方案、 调用追赶进程锁定相关性培训和批次计算，直至完成追赶，和集成和培训的新负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p104">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads. In this scenario, add the imported files to a new file load. Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="2b7cf-115">将导入的文件添加到的当前负载</span><span class="sxs-lookup"><span data-stu-id="2b7cf-115">Adding imported files to the current load</span></span>

<span data-ttu-id="2b7cf-p105">所有导入的文件必须添加到高级电子数据展示中处理负载。导入的文件将添加到最后一个定义的负载。如果以后导入其他文件，他们还必须添加到负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p105">All imported files must be added to a load to be processed in Advanced eDiscovery. Imported files are added to the last defined load. If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="2b7cf-119">在**相关性\>相关性设置**选项卡上，选择**负载**。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相关性设置加载选项卡](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="2b7cf-p106">**包含文件**： 选择要包括的文件的选项。默认情况下，"所有文件"作为总体基于将文件添加到的当前负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p106">**Include files**: Select an option for files to include. By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2b7cf-p107">将所有可用的 culled 的文件加载到相关性。如果您打算加载子集的可用的文件，请先咨询支持，因为加载子集产生不利影响相关性培训。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p107">Load all available culled files into Relevance. If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="2b7cf-125">在**负载管理**中，选择加载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="2b7cf-p108">单击**添加文件**。将文件添加到负载并显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p108">Click **Add files**. The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="2b7cf-128">单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-128">Click **OK**.</span></span>
    
<span data-ttu-id="2b7cf-129">培训文件的高级电子数据展示相关性中可以现在要处理的文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="2b7cf-130">编辑案例中的负载名称</span><span class="sxs-lookup"><span data-stu-id="2b7cf-130">Editing a load name within a case</span></span>

<span data-ttu-id="2b7cf-131">如果更改负载名称，建议使用非常重要与案例的名称。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="2b7cf-132">在**相关性\>相关性设置**选项卡上，选择**负载**。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="2b7cf-p109">从**负载管理**列表中，选择负载，然后单击**编辑**图标。将显示编辑负载窗口。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p109">From the **Loads management** list, select a load and click the **Edit** icon. The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="2b7cf-135">输入所做的更改，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="2b7cf-136">将导入的文件添加到新负载</span><span class="sxs-lookup"><span data-stu-id="2b7cf-136">Adding imported files to a new load</span></span>

<span data-ttu-id="2b7cf-137">启动后相关性培训或执行批次计算，您可能想要导入和处理一组额外的文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="2b7cf-p110">期间追赶，可以创建、 标记，并分析追赶集。高级电子数据展示进行比较的评估过程中的新负载于以前加载相关和非相关文件。基于结果，提示您进行追赶决策，如果有必要，和高级电子数据展示提供基于应计的相关信息的建议。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p110">During Catch-up, you can create, tag, and analyze the Catch-up set. Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads. Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="2b7cf-141">回滚加载和追赶功能有所不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b7cf-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="2b7cf-142">新文件加载导入后批次计算时，高级电子数据展示确定程度文件分为以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="2b7cf-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="2b7cf-143">类似 （已同类）： 新的自定义的一轮相关性培训，则不需要和应计从以前负载的知识可应用于"按原样"的新负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="2b7cf-144">Distinct （异类）： 新的自定义的一轮相关性培训是必需的并且不能应用应计从以前负载的知识。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="2b7cf-145">将这些术语引用的相似性文件加载之间，而不通过负载级别。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="2b7cf-p111">导入时新文件加载期间相关性培训 （才能批次计算），追赶可以继续相关性培训美国的文件集。高级电子数据展示不估计的新负载是否类似于或不同的以前的负载。它只是收集信息的新负载，使相关性培训内容以继续在新的和以前设置的文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p111">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set. Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load. It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="2b7cf-149">有相关性培训中的多个问题以及问题后批次计算，追赶过程解决所有问题，一次执行和结果计算和显示每个问题。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b7cf-p112">追赶示例的大小可能会有所不同。它依赖于相对于上一加载的新负载的大小以及完成之前添加的新负载样本数。追赶示例通常是一组中的新负载 200 到 2000 文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p112">The size of the Catch-up sample may vary. It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load. The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="2b7cf-p113">追赶停止任何其他任务，并需要单个文件标记和审阅。因此，您可以减少开销时采用大型批次中添加新文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p113">Catch-up stops any other tasks and requires individual file tagging and review. Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="2b7cf-155">添加新文件加载使用追赶和滚动加载</span><span class="sxs-lookup"><span data-stu-id="2b7cf-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="2b7cf-156">在**相关性\>相关性设置**选项卡上，选择**负载**。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="2b7cf-p114">在**负载管理**下单击**+** 图标添加负载。将显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p114">Under **Loads management**, click the **+** icon to add a load. A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="2b7cf-p115">单击**是**以继续。显示**添加新加载**对话框。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p115">Click **Yes** to continue. The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2b7cf-161">如果操作执行的以前的负载，您可以仅添加新的负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="2b7cf-p116">在**添加新加载**对话框中，在**加载名称**和**说明**中键入信息，然后单击**确定**。高级电子数据展示中添加新的负载。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p116">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**. Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="2b7cf-p117">若要导入新加载文件，请单击**添加文件**。所有的新文件添加到该负载。高级电子数据展示导入文件后，它识别滚动加载方案，并指示追赶作为下一步。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p117">To import the new load file, click **Add files**. All new files are added to this load. After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="2b7cf-167">单击**追赶**对话框的底部运行方案。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="2b7cf-168">所有问题，以允许并发文件标记为创建单个追赶集，通常包含的新负载，200 到 2000 文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="2b7cf-169">有关加载是否相似或不同、 高级电子数据展示合并还是自动拆分加载和信息提供了详细信息的下一步中关于处理。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="2b7cf-p118">然后，您可以标记文件并运行计算操作。标记启用相关性以确定加载是否相似或不同，并使您能够继续使用上一组新的文件。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p118">You can then tag files and run a calculate operation. The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="2b7cf-172">检查追赶设置后，查看**相关性\>跟踪**追赶结果。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="2b7cf-173">如果在相关性培训过程中添加新文件加载 （也就是说，问题不发往通过批次计算），**继续培训**可以是下一步，无论追赶结果。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="2b7cf-p119">相关性培训继续在美国的设置和新的和以前加载处理作为一个负载。您现在完成此过程，可以继续相关性培训。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p119">The new and previous loads are processed as one load and Relevance training continues on the united set. You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="2b7cf-176">如果批次计算之后添加新的负载，请继续以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="2b7cf-177">批次计算后添加的新加载，高级电子数据展示确定新负载是类似于还是以前加载不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b7cf-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="2b7cf-p120">如果加载找到要与此类似： 无其他相关性培训是必要。仪表板显示建议的下一步是运行 * * 批处理计算 * * 再次用于计算相关性分数的新负载。加载找到要类似，以便可以对新文件运行了以前的分类器分析。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p120">If loads were found to be similar: No additional Relevance training is necessary. The dashboard shows the recommended next step is to run ** Batch calculation ** again to calculate Relevance scores for the new load. Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="2b7cf-p121">如果加载发现截然不同： 更多相关性培训是必需的下, 一步是追赶决策。选择追赶决策，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p121">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision. Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="2b7cf-p122">如果您选择**合并加载**，高级电子数据展示将合并为培训集以前和新负载。尽管第一次加载经历批次计算，但需要更多培训。继续一起培训新和以前负载。批次计算然后再次运行，并应忽略上一批次计算分数。时相关性分数的现有加载能够重新计算，例如，现有文件加载的审阅尚未启动时，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p122">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set. Although the first load went through Batch calculation, more training is needed. Continue training new and previous loads together. Batch calculation will then run again and the previous Batch calculation scores should be ignored. Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="2b7cf-p123">如果您选择**拆分加载**，仅在新加载继续相关性培训。在此情况下上, 一批次计算分数将保持原样。当现有相关性分数的现有负载不会重新计算，例如，如果已开始查看现有加载的内容，请选择此选项。相关性分数从此时起分开管理，并不能合并。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-p123">If you select **Split loads**, continue Relevance training only on the new load. In this instance, previous Batch calculation scores will remain as is. Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started. Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="2b7cf-192">单击**继续培训**。</span><span class="sxs-lookup"><span data-stu-id="2b7cf-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2b7cf-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b7cf-193">See also</span></span>

[<span data-ttu-id="2b7cf-194">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="2b7cf-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2b7cf-195">定义问题和分配用户</span><span class="sxs-lookup"><span data-stu-id="2b7cf-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="2b7cf-196">定义突出显示关键字和高级选项</span><span class="sxs-lookup"><span data-stu-id="2b7cf-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

