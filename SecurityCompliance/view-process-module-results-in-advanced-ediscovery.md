---
title: 查看 Office 365 高级电子数据展示中的流程模块结果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何查找在 Office 365 高级电子数据展示中运行的进程模块的结果, 包括任务状态和过程摘要。  '
ms.openlocfilehash: 0393cde78e559036d92b9ac48245afafc974a8b2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218052"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="88f51-103">查看 Office 365 高级电子数据展示中的流程模块结果</span><span class="sxs-lookup"><span data-stu-id="88f51-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="88f51-104">启动**准备** \> **过程**后, 可以查看进度和结果。</span><span class="sxs-lookup"><span data-stu-id="88f51-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="88f51-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="88f51-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="88f51-107">处理任务状态</span><span class="sxs-lookup"><span data-stu-id="88f51-107">Process task status</span></span>

<span data-ttu-id="88f51-108">在**准备** \> **过程** \> **结果**中, 页面显示当前状态 (如果当前正在运行进程) 或最后一个进程状态任务的状态, 如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="88f51-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![进程模块任务状态](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="88f51-110">根据所选的流程选项, 显示的任务可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="88f51-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="88f51-111">**清单**: 高级电子数据展示循环访问选择进行进程的所有文件, 并执行基本的数据收集。</span><span class="sxs-lookup"><span data-stu-id="88f51-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="88f51-112">**计算签名**: 计算 MD5 数字签名。</span><span class="sxs-lookup"><span data-stu-id="88f51-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="88f51-p102">"组合**提取**": 以递归方式从复合文件 (例如, PST, ZIP, MSG) 中提取内部文件或包含的文件。提取的文件存储在事例的事例文件夹中。</span><span class="sxs-lookup"><span data-stu-id="88f51-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="88f51-115">**同步数据库**: 内部数据库进程。</span><span class="sxs-lookup"><span data-stu-id="88f51-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="88f51-p103">**文件复制**: 复制进程文件。始终显示此任务, 即使选择了 "高级复制文件" 选项也是如此。</span><span class="sxs-lookup"><span data-stu-id="88f51-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="88f51-p104">**文本提取**: 当存在本机文件时, 高级电子数据展示使用 DTSearch 从这些文件中提取文本。这些文件的提取文本作为文本文件存储在 case 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="88f51-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="88f51-120">**更新元数据**: 处理加载的元数据。</span><span class="sxs-lookup"><span data-stu-id="88f51-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="88f51-121">**完成**: 最终处理已加载的事例文件的数据 (例如, 识别错误和成功文件)。</span><span class="sxs-lookup"><span data-stu-id="88f51-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="88f51-p105">任务状态: 在任务完成后显示。运行任务时, 将显示 "运行持续时间"。</span><span class="sxs-lookup"><span data-stu-id="88f51-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88f51-124">已完成的任务还可能包含已完成处理的文件或有错误的文件的总计。</span><span class="sxs-lookup"><span data-stu-id="88f51-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="88f51-p106">"取消" 提供回滚选项以停止进程执行, 然后回滚到以前的数据填充或已保存的已处理数据。Rollback 将清除所有已处理的数据。如果您不希望处理的数据丢失 (例如, 您计划重新加载这些文件), 请选择此窗口中的 "取消" 选项以选择不回滚。</span><span class="sxs-lookup"><span data-stu-id="88f51-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="88f51-128">流程摘要</span><span class="sxs-lookup"><span data-stu-id="88f51-128">Process summary</span></span>

<span data-ttu-id="88f51-129">在准备\>流程\>结果\>流程摘要中, 根据成功的文件处理和错误结果显示加载的文件结果的细目。</span><span class="sxs-lookup"><span data-stu-id="88f51-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="88f51-130">这些窗格显示导入文件统计信息的图形显示, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="88f51-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="88f51-131">**流程摘要累积**d: 事例中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="88f51-132">**进程摘要最后**: 从上一个会话或操作加载的文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="88f51-133">**系列持续**时间: 在案例中的家庭信息 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="88f51-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="88f51-134">如果添加了**种子**文件, 则会在为文件定义的每个问题中列出种子文件的数量。</span><span class="sxs-lookup"><span data-stu-id="88f51-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="88f51-135">如果**种子**文件的标记失败, 也会注明。</span><span class="sxs-lookup"><span data-stu-id="88f51-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="88f51-136">如果添加了**预先加标签**的文件, 则在为文件定义的每个问题中都会列出预先加标签的文件的数量。</span><span class="sxs-lookup"><span data-stu-id="88f51-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="88f51-137">如果**预先加标签**的文件的标记失败, 也会注明。</span><span class="sxs-lookup"><span data-stu-id="88f51-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![进程模块摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="88f51-139">流程摘要和最后一个图表</span><span class="sxs-lookup"><span data-stu-id="88f51-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="88f51-140">左侧栏包含源 + 提取的文件: 这是找到的所有文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="88f51-141">右侧条 (已处理) 包括:</span><span class="sxs-lookup"><span data-stu-id="88f51-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="88f51-142">包含加载错误的文件</span><span class="sxs-lookup"><span data-stu-id="88f51-142">Files with load errors</span></span>
    
- <span data-ttu-id="88f51-143">已成功加载文件, 其中可能包括:</span><span class="sxs-lookup"><span data-stu-id="88f51-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="88f51-144">**现有**: 以前加载过且现在再次加载的文件 (包括重复项)。</span><span class="sxs-lookup"><span data-stu-id="88f51-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="88f51-145">**text**: 包含文本的唯一文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="88f51-146">**非文本**: 空文本文件、空的本机文本文件、本机非文本文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="88f51-147">**重复**的 s: 包含文本的重复文件。</span><span class="sxs-lookup"><span data-stu-id="88f51-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="88f51-148">上一个进程错误</span><span class="sxs-lookup"><span data-stu-id="88f51-148">Last process errors</span></span>

<span data-ttu-id="88f51-149">在准备\>过程\>结果\>中, 上次处理错误时, 将显示上一次会话或执行的操作中的错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="88f51-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![进程模块错误](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="88f51-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88f51-151">See also</span></span>

[<span data-ttu-id="88f51-152">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="88f51-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="88f51-153">运行进程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="88f51-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

