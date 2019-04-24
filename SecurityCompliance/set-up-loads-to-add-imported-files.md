---
title: 设置加载以在 Office 365 高级电子数据展示中添加导入的文件
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: '查看在 Office 365 高级电子数据展示中执行关联性培训之前, 将导入的文件添加到文件的最后一个已定义负载或批处理的步骤。  '
ms.openlocfilehash: 8c5101628b468719f8aa4f81a4c73cbbb226105f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260732"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d333a-103">设置加载以在 Office 365 高级电子数据展示中添加导入的文件</span><span class="sxs-lookup"><span data-stu-id="d333a-103">Set up loads to add imported files in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d333a-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d333a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d333a-106">在高级电子数据展示中, 加载项是添加到事例中的一批新文件。</span><span class="sxs-lookup"><span data-stu-id="d333a-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="d333a-107">默认情况下, 将定义一个加载项, 并将所有导入的文件添加到其中。</span><span class="sxs-lookup"><span data-stu-id="d333a-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="d333a-108">在执行关联性培训之前, 必须将导入的文件添加到负载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="d333a-109">请考虑以下方案:</span><span class="sxs-lookup"><span data-stu-id="d333a-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="d333a-110">已知新文件与加载到事例数据库的以前的文件相似, 或者以前的文件加载是从文件集合中随机设置的。</span><span class="sxs-lookup"><span data-stu-id="d333a-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="d333a-111">在此实例中, 将导入的文件添加到当前文件加载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="d333a-112">新文件与以前的文件不同 (例如, 从不同的源中), 或者没有以前的知识与以前的加载相似或不同。</span><span class="sxs-lookup"><span data-stu-id="d333a-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="d333a-113">在这种情况下, 将导入的文件添加到新的文件加载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="d333a-114">高级电子数据展示可将此识别为滚动负载方案、调用追赶过程、锁定相关性培训和批量计算, 直到完成追赶, 并且新负载已集成并经过培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="d333a-115">将导入的文件添加到当前负载</span><span class="sxs-lookup"><span data-stu-id="d333a-115">Adding imported files to the current load</span></span>

<span data-ttu-id="d333a-116">必须将所有导入的文件添加到负载, 才能在高级电子数据展示中进行处理。</span><span class="sxs-lookup"><span data-stu-id="d333a-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="d333a-117">导入的文件将添加到最后定义的负载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="d333a-118">如果稍后导入其他文件, 则还必须将它们添加到负载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="d333a-119">在 "**相关性\>关联设置**" 选项卡中, 选择 "**加载**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![相关性设置加载选项卡](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="d333a-121">**包含文件**: 选择要包含的文件的选项。</span><span class="sxs-lookup"><span data-stu-id="d333a-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="d333a-122">默认情况下, 将文件添加到当前负载时基于 "所有文件" 填充。</span><span class="sxs-lookup"><span data-stu-id="d333a-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d333a-123">将所有可用的 culled 文件加载到相关性。</span><span class="sxs-lookup"><span data-stu-id="d333a-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="d333a-124">如果计划仅加载可用文件的子集, 请先咨询支持, 因为加载子集会对相关性定型产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="d333a-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="d333a-125">在 "**负载管理**" 中, 选择一个负载。</span><span class="sxs-lookup"><span data-stu-id="d333a-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="d333a-126">单击 "**添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-126">Click **Add files**.</span></span> <span data-ttu-id="d333a-127">将文件添加到加载中, 并显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="d333a-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="d333a-128">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="d333a-128">Click **OK**.</span></span>
    
<span data-ttu-id="d333a-129">现在, 可以在高级电子数据展示的相关性中处理文件以用于培训文件。</span><span class="sxs-lookup"><span data-stu-id="d333a-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="d333a-130">在事例中编辑加载名称</span><span class="sxs-lookup"><span data-stu-id="d333a-130">Editing a load name within a case</span></span>

<span data-ttu-id="d333a-131">如果更改加载名称, 建议使用对事例有重大意义的名称。</span><span class="sxs-lookup"><span data-stu-id="d333a-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="d333a-132">在 "**相关性\>关联设置**" 选项卡中, 选择 "**加载**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="d333a-133">从 "**加载管理**" 列表中选择一个负载, 然后单击 "**编辑**" 图标。</span><span class="sxs-lookup"><span data-stu-id="d333a-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="d333a-134">将显示 "编辑加载" 窗口。</span><span class="sxs-lookup"><span data-stu-id="d333a-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="d333a-135">输入所做的更改, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d333a-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="d333a-136">将导入的文件添加到新的负载</span><span class="sxs-lookup"><span data-stu-id="d333a-136">Adding imported files to a new load</span></span>

<span data-ttu-id="d333a-137">在开始进行相关性培训或执行批量计算之后, 您可能需要导入和处理其他文件集。</span><span class="sxs-lookup"><span data-stu-id="d333a-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="d333a-138">在追赶过程中, 您可以创建、标记和分析追赶集。</span><span class="sxs-lookup"><span data-stu-id="d333a-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="d333a-139">高级电子数据展示将对新负载中的相关和非相关文件的评估与以前的加载中的相关文件进行比较。</span><span class="sxs-lookup"><span data-stu-id="d333a-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="d333a-140">根据结果, 系统会提示你进行追赶决策 (如有必要), 并根据应计相关性信息提供高级电子数据展示建议。</span><span class="sxs-lookup"><span data-stu-id="d333a-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="d333a-141">滚动加载和追赶功能的变化如下所示:</span><span class="sxs-lookup"><span data-stu-id="d333a-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="d333a-142">在批处理计算完成后导入新的文件加载后, 高级电子数据展示将确定这些文件属于以下类别之一:</span><span class="sxs-lookup"><span data-stu-id="d333a-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="d333a-143">类似 (同类): 不需要一种新的自定义的相关性培训, 并且从以前的负载中应计出的知识可以按 "原样" 应用到新的负载。</span><span class="sxs-lookup"><span data-stu-id="d333a-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="d333a-144">Distinct (异类): 需要新的自定义双向相关性培训, 并且无法应用从以前的加载中应计的知识。</span><span class="sxs-lookup"><span data-stu-id="d333a-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="d333a-145">这些术语指的是文件在两个负载之间的相似性级别, 而不是在加载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="d333a-146">在相关性培训期间导入新的文件负载 (批处理计算之前), 通过追赶功能, 可以继续对美国英语文件集进行相关性培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="d333a-147">高级电子数据展示不会估计新负载与前一个负载是否相似或不同。</span><span class="sxs-lookup"><span data-stu-id="d333a-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="d333a-148">它只收集有关新负载的信息, 并启用相关性培训以继续执行新的和以前的文件集。</span><span class="sxs-lookup"><span data-stu-id="d333a-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="d333a-149">如果相关性培训中存在多个问题以及批量计算后的问题, 则将针对所有问题执行一次弥补过程, 并为每个问题计算并显示结果。</span><span class="sxs-lookup"><span data-stu-id="d333a-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d333a-150">追赶示例的大小可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="d333a-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="d333a-151">它取决于新负载相对于上一次加载的大小, 以及在添加新负载之前完成的样本数。</span><span class="sxs-lookup"><span data-stu-id="d333a-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="d333a-152">追赶示例通常是新负载中的一组200到2000文件。</span><span class="sxs-lookup"><span data-stu-id="d333a-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d333a-153">追赶操作可停止所有其他任务, 并需要进行单独的文件标记和审阅。</span><span class="sxs-lookup"><span data-stu-id="d333a-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="d333a-154">因此, 在大型批处理中添加新文件时, 可以减少开销。</span><span class="sxs-lookup"><span data-stu-id="d333a-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="d333a-155">使用追赶和滚动负载添加新的文件负载</span><span class="sxs-lookup"><span data-stu-id="d333a-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="d333a-156">在 "**相关性\>关联设置**" 选项卡中, 选择 "**加载**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="d333a-157">在 "**加载管理**" 下**+** , 单击图标以添加负载。</span><span class="sxs-lookup"><span data-stu-id="d333a-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="d333a-158">将显示一条确认消息。</span><span class="sxs-lookup"><span data-stu-id="d333a-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="d333a-159">单击" **是**"即可继续。</span><span class="sxs-lookup"><span data-stu-id="d333a-159">Click **Yes** to continue.</span></span> <span data-ttu-id="d333a-160">将显示 "**添加新加载**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="d333a-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d333a-161">仅当对以前的负载执行了操作时, 才可以添加新的负载。</span><span class="sxs-lookup"><span data-stu-id="d333a-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="d333a-162">在 "**添加新负载**" 对话框中, 在 "**加载名称**和**说明**" 中键入信息, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d333a-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="d333a-163">高级电子数据展示添加了新负载。</span><span class="sxs-lookup"><span data-stu-id="d333a-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="d333a-164">若要导入新的加载文件, 请单击 "**添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="d333a-165">所有新文件都将添加到此负载中。</span><span class="sxs-lookup"><span data-stu-id="d333a-165">All new files are added to this load.</span></span> <span data-ttu-id="d333a-166">高级电子数据展示导入文件后, 它会识别滚动负载方案, 并指示后续步骤的追赶。</span><span class="sxs-lookup"><span data-stu-id="d333a-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="d333a-167">单击对话框底部的 "**追赶**" 以运行方案。</span><span class="sxs-lookup"><span data-stu-id="d333a-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="d333a-168">单个追赶集 (通常包含从新负载的200到2000文件) 是为所有问题创建的, 以允许对文件进行并发标记。</span><span class="sxs-lookup"><span data-stu-id="d333a-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="d333a-169">将提供详细信息, 了解加载的内容是否相似或不同、高级电子数据展示是否自动合并或拆分加载, 以及有关在下一步中处理的信息。</span><span class="sxs-lookup"><span data-stu-id="d333a-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="d333a-170">然后, 您可以标记文件并运行计算操作。</span><span class="sxs-lookup"><span data-stu-id="d333a-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="d333a-171">通过使用标记, 可以确定加载的相似或不同之处, 并使您能够继续处理新的文件集。</span><span class="sxs-lookup"><span data-stu-id="d333a-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="d333a-172">检查完追赶集后, 查看追赶结果的**相关性\>跟踪**。</span><span class="sxs-lookup"><span data-stu-id="d333a-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="d333a-173">如果在相关性培训过程中添加了新文件加载 (即, 该问题尚未通过成批计算), 则**继续训练**是下一步, 而不考虑追赶结果。</span><span class="sxs-lookup"><span data-stu-id="d333a-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="d333a-174">新的和以前的加载将作为一个负载进行处理, 并在英国继续进行相关性培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="d333a-175">你现在已完成此过程, 可以继续进行相关性培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="d333a-176">如果在计算批次后添加了新的负载, 请继续执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d333a-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="d333a-177">对于批量计算后添加的新加载, 高级电子数据展示将确定新负载与以前的负载是否相似或不同, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d333a-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="d333a-178">如果发现加载项相似: 无需进行其他相关性培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="d333a-179">仪表板显示建议的下一步是, 再次运行 \* \* 批计算 \* \* 以计算新负载的相关性分数。</span><span class="sxs-lookup"><span data-stu-id="d333a-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="d333a-180">发现加载相似, 因此可以对新文件运行之前的分类器分析。</span><span class="sxs-lookup"><span data-stu-id="d333a-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="d333a-181">如果发现加载是截然不同的: 需要更多相关培训, 下一步是追赶决策。</span><span class="sxs-lookup"><span data-stu-id="d333a-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="d333a-182">选择一个追赶决策, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="d333a-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="d333a-183">如果选择 "**合并加载**", 高级电子数据展示将合并培训集的上一个和新加载。</span><span class="sxs-lookup"><span data-stu-id="d333a-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="d333a-184">尽管第一个加载通过批量计算, 但需要进行更多的培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="d333a-185">继续培训新的和以前的加载。</span><span class="sxs-lookup"><span data-stu-id="d333a-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="d333a-186">然后, 批处理计算将再次运行, 并且应忽略以前的批处理计算分数。</span><span class="sxs-lookup"><span data-stu-id="d333a-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="d333a-187">如果可以重新计算现有负载的相关性分数 (例如, 当尚未启动对现有文件加载的审阅时), 请选择此选择。</span><span class="sxs-lookup"><span data-stu-id="d333a-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="d333a-188">如果选择 "**拆分加载**", 则仅在新负载上继续关联培训。</span><span class="sxs-lookup"><span data-stu-id="d333a-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="d333a-189">在此情况下, 以前的批处理计算分数将保持原样。</span><span class="sxs-lookup"><span data-stu-id="d333a-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="d333a-190">当无法重新计算现有负载的现有相关性分数时, 例如, 如果已启动对现有负载的审阅, 请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="d333a-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="d333a-191">相关性得分与此点向前管理, 不能合并在一起。</span><span class="sxs-lookup"><span data-stu-id="d333a-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="d333a-192">单击 "**继续培训**"。</span><span class="sxs-lookup"><span data-stu-id="d333a-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d333a-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d333a-193">See also</span></span>

[<span data-ttu-id="d333a-194">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="d333a-194">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d333a-195">定义问题和分配用户</span><span class="sxs-lookup"><span data-stu-id="d333a-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="d333a-196">定义突出显示的关键字和高级选项</span><span class="sxs-lookup"><span data-stu-id="d333a-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

