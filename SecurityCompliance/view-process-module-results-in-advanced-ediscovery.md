---
title: 查看 Office 365 高级电子数据展示中的流程模块结果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何查找在 Office 365 高级电子数据展示，其中包括任务状态和摘要过程中运行的进程模块的结果。  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524819"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d39a1-103">查看 Office 365 高级电子数据展示中的流程模块结果</span><span class="sxs-lookup"><span data-stu-id="d39a1-103">View Process module results in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="d39a1-104">**准备**后\>启动**过程**，您可以查看进度和结果。</span><span class="sxs-lookup"><span data-stu-id="d39a1-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d39a1-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="d39a1-107">处理任务状态</span><span class="sxs-lookup"><span data-stu-id="d39a1-107">Process task status</span></span>

<span data-ttu-id="d39a1-108">在**准备** \> **过程** \> **结果**，页上显示的当前状态 （如果当前正在运行过程） 或最后一个进程状态任务状态在以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="d39a1-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![进程模块任务状态](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="d39a1-110">显示的任务可能取决于所选进程选项。</span><span class="sxs-lookup"><span data-stu-id="d39a1-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="d39a1-111">**清单**： 高级电子数据展示循环访问所有进程选定文件，并执行基本的数据集。</span><span class="sxs-lookup"><span data-stu-id="d39a1-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="d39a1-112">**计算签名**： 计算 MD5 数字签名。</span><span class="sxs-lookup"><span data-stu-id="d39a1-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="d39a1-p102">**组合提取**： 提取内部或包含文件以递归方式从复合文件 (例如太平洋标准时间，ZIP，MSG)。解压缩的文件存储的大小写的案例文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p102">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG). Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="d39a1-115">**同步数据库**： 内部数据库过程。</span><span class="sxs-lookup"><span data-stu-id="d39a1-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="d39a1-p103">**文件复制**： 副本处理文件。始终显示该任务中，选择高级的复制文件选项的情况下，即使。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p103">**File copy**: Copies Process files. This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="d39a1-p104">**文本提取**： 高级电子数据展示时有本机文件，从使用 DTSearch 这些文件提取文本。作为案例文件夹中的文本文件存储中的这些文件提取的文本。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p104">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch. The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="d39a1-120">**更新元数据**： 处理加载元数据。</span><span class="sxs-lookup"><span data-stu-id="d39a1-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="d39a1-121">**正在**： 完成的数据的内部处理加载案例文件 （例如，确定错误和成功文件）。</span><span class="sxs-lookup"><span data-stu-id="d39a1-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="d39a1-p105">任务状态： 显示任务完成后。任务在运行时，将显示运行持续时间。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p105">Task status: Displayed after task completion. While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d39a1-124">已完成的任务可能还包括汇总完成处理的文件或有错误的文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="d39a1-p106">"取消"提供了回滚选项，停止过程执行，然后回滚到以前的数据填充或保存处理的数据。回滚清除所有已处理的数据。如果您不希望在此窗口中的选择"取消"选项，可选择不回滚 （例如，您打算将这些文件重新加载） 丢失的处理的数据。</span><span class="sxs-lookup"><span data-stu-id="d39a1-p106">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data. Rollback clears all processed data. If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="d39a1-128">过程摘要</span><span class="sxs-lookup"><span data-stu-id="d39a1-128">Process summary</span></span>

<span data-ttu-id="d39a1-129">在准备\>过程\>结果\>进程摘要，加载的文件结果的分解显示根据成功文件处理和错误结果。</span><span class="sxs-lookup"><span data-stu-id="d39a1-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="d39a1-130">窗格演示导入的文件统计信息的图形显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d39a1-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="d39a1-131">**过程摘要累加**d： 情况的所有文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="d39a1-132">**上次处理摘要**： 从最后一个会话或操作加载的文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="d39a1-133">**系列上次**： 家族情况 （如果有） 的信息。</span><span class="sxs-lookup"><span data-stu-id="d39a1-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="d39a1-134">如果**种子**文件已添加，每个已定义的文件的问题列出的种子文件数。</span><span class="sxs-lookup"><span data-stu-id="d39a1-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="d39a1-135">如果的**种子**文件标记失败，也记下。</span><span class="sxs-lookup"><span data-stu-id="d39a1-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="d39a1-136">如果**前标记**文件已添加，每个已定义的文件的问题列出的前已标记的文件数。</span><span class="sxs-lookup"><span data-stu-id="d39a1-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="d39a1-137">如果**前标记**文件的标记失败，也记下。</span><span class="sxs-lookup"><span data-stu-id="d39a1-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![进程模块摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="d39a1-139">过程摘要累积和上次图表</span><span class="sxs-lookup"><span data-stu-id="d39a1-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="d39a1-140">左侧的栏包含源 + 解压缩的文件： 这是所有文件找到。</span><span class="sxs-lookup"><span data-stu-id="d39a1-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="d39a1-141">右侧栏处理，包括：</span><span class="sxs-lookup"><span data-stu-id="d39a1-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="d39a1-142">文件加载错误</span><span class="sxs-lookup"><span data-stu-id="d39a1-142">Files with load errors</span></span>
    
- <span data-ttu-id="d39a1-143">已成功加载的文件，这可能包括：</span><span class="sxs-lookup"><span data-stu-id="d39a1-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="d39a1-144">**现有**： 之前已加载并再次 （包括重复项） 现在已加载的文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="d39a1-145">**文本**： 唯一文件文本。</span><span class="sxs-lookup"><span data-stu-id="d39a1-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="d39a1-146">**非文本**： 空文本文件、 空本机文本文件、 本机非文本文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="d39a1-147">文本具有**重复**s： 重复文件。</span><span class="sxs-lookup"><span data-stu-id="d39a1-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="d39a1-148">最后一个过程错误</span><span class="sxs-lookup"><span data-stu-id="d39a1-148">Last process errors</span></span>

<span data-ttu-id="d39a1-149">在准备\>过程\>结果\>显示最后一个过程错误中的最后一个会话或执行的操作的错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d39a1-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![进程模块错误](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="d39a1-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d39a1-151">See also</span></span>

[<span data-ttu-id="d39a1-152">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="d39a1-152">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d39a1-153">运行进程模块并将数据加载</span><span class="sxs-lookup"><span data-stu-id="d39a1-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

