---
title: 在 Office 365 高级电子数据展示中测试相关性分析
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何使用 Office 365 高级电子数据展示中的批量计算之后的 "测试" 选项卡来测试、比较和验证总体处理质量。  '
ms.openlocfilehash: 735a6d8088b4696e2ebc348db435a11914bd0b10
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215832"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="52d1b-103">在 Office 365 高级电子数据展示中测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="52d1b-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="52d1b-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="52d1b-p102">利用高级电子数据展示中的 "测试" 选项卡, 可以测试、比较和验证总体处理质量。这些测试是在批量计算后执行的。通过在集合中标记文件, 专家就是否对每个已标记的文件实际是否与事例相关做出最后的判断。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="52d1b-p103">在单问题和多问题方案中, 测试通常每个问题执行一次。可以在每次测试后查看结果, 并可以使用指定的示例测试文件对测试结果进行改编。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="52d1b-111">测试 rest</span><span class="sxs-lookup"><span data-stu-id="52d1b-111">Testing the rest</span></span>

<span data-ttu-id="52d1b-p104">"测试 Rest" 测试用于验证判定决策, 例如, 基于最终的高级电子数据展示结果仅查看特定相关性截止分数以上的文件。专家会查看选定的截止分数下的文件示例, 以评估该集合中相关文件的数量。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="52d1b-p105">此测试提供评审集与测试 Rest 填充之间的统计信息和比较。评审集的结果是由培训过程中的相关性计算得出的。结果包括基于设置和输入参数的计算, 例如:</span><span class="sxs-lookup"><span data-stu-id="52d1b-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="52d1b-117">测试样本和标识的相关文件中的文件数的示例统计信息。</span><span class="sxs-lookup"><span data-stu-id="52d1b-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="52d1b-p106">以表格形式比较评审集和其余部分的总体参数, 例如, 文件数、估计的相关文件数、估计丰富程度以及查找其他相关文件所需的平均成本。成本参数设置可由管理员进行设置。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="52d1b-120">打开 "**相关性\>测试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="52d1b-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="52d1b-p107">在 "**测试**" 选项卡中, 单击 "**新建测试**"。将显示 "**创建测试**" 对话框, 如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![相关性测试其余结果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="52d1b-124">在 "**测试名称**" 和 "**说明**" 中, 键入名称和说明。</span><span class="sxs-lookup"><span data-stu-id="52d1b-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="52d1b-125">在 "**测试类型**" 列表中, 选择 **"测试 Rest"**</span><span class="sxs-lookup"><span data-stu-id="52d1b-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="52d1b-126">在 "**问题/类别**" 列表中, 选择 "问题名称"。</span><span class="sxs-lookup"><span data-stu-id="52d1b-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="52d1b-127">在 "**加载**" 列表中, 选择负载。</span><span class="sxs-lookup"><span data-stu-id="52d1b-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="52d1b-128">在**读取百分比**中, 接受默认值或为截止的相关性分数选择一个值。</span><span class="sxs-lookup"><span data-stu-id="52d1b-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="52d1b-p108">在 "**设置大小**" 中, 或接受默认值。请注意, 还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="52d1b-p109">单击 "**开始标记**"。生成测试示例。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="52d1b-133">查看并标记\*\* \>相关性标记**选项卡中的每个文件, 完成后, 单击 "**计算\*\*"。</span><span class="sxs-lookup"><span data-stu-id="52d1b-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="52d1b-p110">在 "测试" 选项卡中, 可以单击 "**查看结果**" 以查看测试结果。下图中显示了一个示例。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![测试其余结果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="52d1b-137">在上面的图中, 表的 "**示例参数**" 部分包含有关专家标记的示例中的文件数的详细信息, 以及该示例中找到的相关文件数。</span><span class="sxs-lookup"><span data-stu-id="52d1b-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="52d1b-p111">表的 "**填充参数**" 部分包含测试结果, 包括对文件进行的审阅集填充, 其中分数低于选定的截止点, "Rest" 填充的文件的分数高于选定的截止点。对于每个样本总体, 显示以下结果:</span><span class="sxs-lookup"><span data-stu-id="52d1b-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="52d1b-140">包括具有已读%-规定截止点的文件</span><span class="sxs-lookup"><span data-stu-id="52d1b-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="52d1b-141">总文件数</span><span class="sxs-lookup"><span data-stu-id="52d1b-141">The total number of files</span></span> 
    
- <span data-ttu-id="52d1b-142">估计的相关文件数</span><span class="sxs-lookup"><span data-stu-id="52d1b-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="52d1b-143">估计丰富程度</span><span class="sxs-lookup"><span data-stu-id="52d1b-143">The estimated richness</span></span> 
    
- <span data-ttu-id="52d1b-144">查找另一个相关文件的平均评审成本</span><span class="sxs-lookup"><span data-stu-id="52d1b-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="52d1b-145">测试切片</span><span class="sxs-lookup"><span data-stu-id="52d1b-145">Testing the slice</span></span>

<span data-ttu-id="52d1b-146">"测试切片" 测试执行的测试类似于 "测试 Rest" 测试, 而是对由相关性读取% 指定的一段文件集执行测试。</span><span class="sxs-lookup"><span data-stu-id="52d1b-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="52d1b-147">打开 "**相关性\>测试**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="52d1b-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="52d1b-p112">在 "**测试**" 选项卡中, 单击 "**新建测试**"。将显示 "**创建测试**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="52d1b-150">在 "**测试名称**和**说明**" 中, 键入信息。</span><span class="sxs-lookup"><span data-stu-id="52d1b-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="52d1b-151">在 "**测试类型**" 列表中, 选择 "**测试切片"**。</span><span class="sxs-lookup"><span data-stu-id="52d1b-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="52d1b-152">在 "**问题**" 列表中, 选择 "问题名称"。</span><span class="sxs-lookup"><span data-stu-id="52d1b-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="52d1b-153">在 "**加载**" 列表中, 选择负载。</span><span class="sxs-lookup"><span data-stu-id="52d1b-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="52d1b-154">在 "**读取百分比**" 中, 接受默认的 "低" 和 "高" 范围值, 或选择 "截止相关性分数" 值。</span><span class="sxs-lookup"><span data-stu-id="52d1b-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="52d1b-155">在 "**设置大小**" 中, 选择一个值或接受默认值。</span><span class="sxs-lookup"><span data-stu-id="52d1b-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="52d1b-156">还原图标将还原默认值。</span><span class="sxs-lookup"><span data-stu-id="52d1b-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="52d1b-p113">单击 "**开始标记**"。生成测试示例。</span><span class="sxs-lookup"><span data-stu-id="52d1b-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="52d1b-159">查看并标记\*\* \>相关性标记**选项卡中的每个文件, 完成后, 单击 "**计算\*\*"。</span><span class="sxs-lookup"><span data-stu-id="52d1b-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="52d1b-160">在 "测试" 选项卡中, 可以单击 "**查看结果**" 以查看测试结果。</span><span class="sxs-lookup"><span data-stu-id="52d1b-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="52d1b-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d1b-161">See also</span></span>

[<span data-ttu-id="52d1b-162">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="52d1b-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="52d1b-163">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="52d1b-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="52d1b-164">标记和评估</span><span class="sxs-lookup"><span data-stu-id="52d1b-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="52d1b-165">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="52d1b-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="52d1b-166">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="52d1b-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="52d1b-167">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="52d1b-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

