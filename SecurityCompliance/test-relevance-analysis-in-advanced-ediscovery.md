---
title: 在 Office 365 高级电子数据展示中测试相关性分析
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何在 Office 365 高级电子数据展示中的批处理计算后使用测试选项卡测试、 比较和验证处理的总体质量。  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525423"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="de06e-103">在 Office 365 高级电子数据展示中测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="de06e-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="de06e-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="de06e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="de06e-p102">高级电子数据展示中的测试选项卡，可以测试、 比较和验证处理的总体质量。这些测试批次计算之后执行。通过标记集合中的文件，专家使得关于每个已标记的文件是否是实际与案例相关的最终判断。</span><span class="sxs-lookup"><span data-stu-id="de06e-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="de06e-p103">在单个和多问题的情况下，每个问题通常执行测试。每个测试后，可以查看结果，并可以与指定的示例测试文件返工测试结果。</span><span class="sxs-lookup"><span data-stu-id="de06e-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="de06e-111">测试 rest</span><span class="sxs-lookup"><span data-stu-id="de06e-111">Testing the rest</span></span>

<span data-ttu-id="de06e-p104">"测试 Rest"测试用于验证挑选决策，例如，若要查看仅根据最终高级电子数据展示结果的特定相关性截止分数上方的文件。专家审阅下的所选的截止分数计算该集内的相关文件数的文件的示例。</span><span class="sxs-lookup"><span data-stu-id="de06e-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="de06e-p105">此测试提供的 Rest 人口统计信息和审阅设置和测试之间的比较。审阅设置的结果那些期间培训按相关性计算。结果包含计算、 基于的设置和输入的参数，如：</span><span class="sxs-lookup"><span data-stu-id="de06e-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="de06e-117">测试示例和标识的相关文件中的示例文件数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="de06e-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="de06e-p106">审阅设置和其余，例如，文件数的总体参数的表格比较估计数相关的文件、 估计的丰富和查找其他相关文件的平均成本。成本的参数设置可以由管理员设置。</span><span class="sxs-lookup"><span data-stu-id="de06e-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="de06e-120">打开**相关性\>测试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de06e-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="de06e-p107">在**测试**选项卡中，单击**新建测试**。将显示**创建测试**对话框中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="de06e-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![相关性测试其余结果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="de06e-124">在**测试名称**和**说明**中，键入名称和说明。</span><span class="sxs-lookup"><span data-stu-id="de06e-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="de06e-125">在**测试类型**列表中，选择**测试 Rest**</span><span class="sxs-lookup"><span data-stu-id="de06e-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="de06e-126">在**问题 / 类别**列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="de06e-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="de06e-127">在**加载**列表中，选择加载。</span><span class="sxs-lookup"><span data-stu-id="de06e-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="de06e-128">在**读取 %**，接受默认值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="de06e-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="de06e-p108">在**设置大小**，或接受默认值。请注意还原图标将还原的默认值。</span><span class="sxs-lookup"><span data-stu-id="de06e-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="de06e-p109">单击**开始标记**。生成测试示例。</span><span class="sxs-lookup"><span data-stu-id="de06e-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="de06e-133">查看和标记中的文件的每个**相关性\>标记**选项卡，完成后，单击**计算**。</span><span class="sxs-lookup"><span data-stu-id="de06e-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="de06e-p110">在测试选项卡，您可以单击**查看结果**，若要查看的测试结果。下图是一个示例。</span><span class="sxs-lookup"><span data-stu-id="de06e-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![测试其余结果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="de06e-137">在上图中，表的**示例参数**部分包含有关使用专家，示例中的文件数和相关的示例中找到的文件数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="de06e-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="de06e-p111">**总体参数**部分中的表包含的测试结果，包括下面所选截止分数的文件的审阅设置填充和具有所选截止上方的分数的文件的"Rest"填充。为每个总体，显示以下结果：</span><span class="sxs-lookup"><span data-stu-id="de06e-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="de06e-140">包括具有读取 %-既定截止文件</span><span class="sxs-lookup"><span data-stu-id="de06e-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="de06e-141">文件总数</span><span class="sxs-lookup"><span data-stu-id="de06e-141">The total number of files</span></span> 
    
- <span data-ttu-id="de06e-142">相关文件的估计的数目</span><span class="sxs-lookup"><span data-stu-id="de06e-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="de06e-143">估计的丰富</span><span class="sxs-lookup"><span data-stu-id="de06e-143">The estimated richness</span></span> 
    
- <span data-ttu-id="de06e-144">平均审阅成本的查找另一个的相关文件</span><span class="sxs-lookup"><span data-stu-id="de06e-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="de06e-145">测试切片</span><span class="sxs-lookup"><span data-stu-id="de06e-145">Testing the slice</span></span>

<span data-ttu-id="de06e-146">"测试切片"测试执行测试类似于"测试 Rest"测试，但文件段设置为指定的相关性读取 %。</span><span class="sxs-lookup"><span data-stu-id="de06e-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="de06e-147">打开**相关性\>测试**选项卡。</span><span class="sxs-lookup"><span data-stu-id="de06e-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="de06e-p112">在**测试**选项卡中，单击**新建测试**。显示**创建测试**对话框。</span><span class="sxs-lookup"><span data-stu-id="de06e-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="de06e-150">在**测试名称**和**说明**中，键入信息。</span><span class="sxs-lookup"><span data-stu-id="de06e-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="de06e-151">在**测试类型**列表中，选择**测试切片**。</span><span class="sxs-lookup"><span data-stu-id="de06e-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="de06e-152">在**问题**列表中，选择问题名称。</span><span class="sxs-lookup"><span data-stu-id="de06e-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="de06e-153">在**加载**列表中，选择加载。</span><span class="sxs-lookup"><span data-stu-id="de06e-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="de06e-154">在**读取 %之间**，接受默认低和高范围值或选择截止相关性分数的值。</span><span class="sxs-lookup"><span data-stu-id="de06e-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="de06e-155">在**设置大小**，选择一个值，或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="de06e-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="de06e-156">还原图标将还原为默认值。</span><span class="sxs-lookup"><span data-stu-id="de06e-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="de06e-p113">单击**开始标记**。生成测试示例。</span><span class="sxs-lookup"><span data-stu-id="de06e-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="de06e-159">查看和标记中的文件的每个**相关性\>标记**选项卡，完成后，单击**计算**。</span><span class="sxs-lookup"><span data-stu-id="de06e-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="de06e-160">在测试选项卡，您可以单击**查看结果**，若要查看的测试结果。</span><span class="sxs-lookup"><span data-stu-id="de06e-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="de06e-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de06e-161">See also</span></span>

[<span data-ttu-id="de06e-162">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="de06e-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="de06e-163">了解评估中相关性</span><span class="sxs-lookup"><span data-stu-id="de06e-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="de06e-164">标签和评估</span><span class="sxs-lookup"><span data-stu-id="de06e-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="de06e-165">标签和相关性培训</span><span class="sxs-lookup"><span data-stu-id="de06e-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="de06e-166">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="de06e-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="de06e-167">决定基于结果</span><span class="sxs-lookup"><span data-stu-id="de06e-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

