---
title: 在 Office 365 高级电子数据展示中使用快速分析
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何运行 Office 365 高级电子数据展示的快速分析模式
ms.openlocfilehash: 04b48db445f114fd6138b099703e826c6b4ce7c0
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156154"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ed5bd-103">在 Office 365 高级电子数据展示中使用快速分析</span><span class="sxs-lookup"><span data-stu-id="ed5bd-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ed5bd-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ed5bd-106">可以使用**快速分析**快速分析事例并导出结果。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="ed5bd-107">可以使用快速分析来计算临近的重复和电子邮件线索, 并计算主题。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="ed5bd-108">您还可以在 "快速分析" 的 "[高级设置](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)" 中为主题、文档相似性和导出文件设置某些参数。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="ed5bd-109">运行快速分析</span><span class="sxs-lookup"><span data-stu-id="ed5bd-109">Run Express analysis</span></span>

1. <span data-ttu-id="ed5bd-110">在 "**快速分析**(1)" 选项卡中, 选择要启用 \* \* Express 分析 \* \* (2) 和**高级设置**按钮的容器。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![快速分析页面的屏幕截图](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="ed5bd-112">在 "**分析参数**" 下:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="ed5bd-113">如果要运行分析, 请选中 "**计算临近的重复项和电子邮件线程**"。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="ed5bd-114">默认情况下选中此选项。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="ed5bd-115">选中 "**计算主题**" 以处理所有文件并为其分配主题。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="ed5bd-116">默认情况下选中此选项。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="ed5bd-117">在 "**导出目标**:" 下:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="ed5bd-118">检查 "**下载到本地**计算机" 以下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="ed5bd-119">如果选中 "**导出到用户定义的 Azure blob** ", 则还可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ed5bd-120">将导出包存储到用户定义的 Azure blob 后, 数据将不再由高级电子数据展示进行管理。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="ed5bd-121">它由 Azure blob 管理。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="ed5bd-122">这意味着, 如果删除了该案例, 导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="ed5bd-123">**保存 sas 令牌以供将来导出会话**: 如果选中此选项, 则会在高级电子数据展示的内部数据库中对 sas 令牌进行加密, 以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed5bd-124">目前, SAS 令牌在一个月后过期。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="ed5bd-125">如果您在多个月后尝试下载, 您必须撤消上次会话, 然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="ed5bd-126">若要使用默认设置启动 express 分析, 请选择 "**快速分析**", "**任务状态**" 页将显示</span><span class="sxs-lookup"><span data-stu-id="ed5bd-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="ed5bd-127">在 "**任务状态**" 页上, 可以\*\*\*\* 展开 "**分析**和**导出**" 选项卡, 以显示有关 express 运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![高级电子数据展示快速分析任务状态页的屏幕截图](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="ed5bd-129">选择 "**快速分析摘要**" 页, 列出有关运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="ed5bd-130">在 " **Express 分析摘要**" 页面的底部, 选择 "**下载上次会话**" 以下载分析文件 tp 您的本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="ed5bd-131">您首先必须下载电子数据展示导出工具, 并将导出密钥粘贴到电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="ed5bd-132">快速分析的高级设置</span><span class="sxs-lookup"><span data-stu-id="ed5bd-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="ed5bd-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ed5bd-133"></span></span>

<span data-ttu-id="ed5bd-134">您可以选择设置**高级设置**来更改默认的快速分析参数。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="ed5bd-135">在 "**分析**" 部分:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="ed5bd-136">在**临近的重复和电子邮件线程**中, 输入 "**文档相似性**" 值, 或接受默认值 "65%"。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="ed5bd-137">在 "**最大主题数**" 中, 输入或选择要创建的主题数的值。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="ed5bd-138">默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ed5bd-139">增加主题的数量将影响性能, 并使主题能够通用化。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="ed5bd-140">主题的数量越高, 它们的粒度就越多。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="ed5bd-141">例如, 如果一组50主题包含一个主题, 如 "篮球、Spurs、Clippers、Lakers", 则300主题可能包含单独的主题: "Spurs"、"Clippers"、"Lakers"。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="ed5bd-142">如果您不知道主题 "篮球" 并对 ECA 使用此功能, 则查看主题 "篮球" 可能有用。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="ed5bd-143">但是, 如果处理的主题过多, 则您可能永远无法看到 "篮球" 一词, 也可能不知道 Spurs 和 Clippers 是要查看的理想的篮球主题, 而不是执行启动并用于头发的项目。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="ed5bd-144">在**建议的主题**中, 选择 "**修改**" 以建议主题词来控制主题处理。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="ed5bd-145">高级电子数据展示将重点放在这些建议的单词上, 并根据 "最大主题数" 设置尝试创建一个或多个相关主题。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="ed5bd-146">例如, 如果建议的单词是 "computer", 并且您将 "2" 指定为 "最大主题数", 高级电子数据展示将尝试生成与 "computer" 一词相关的两个主题。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="ed5bd-147">例如, 这两个主题可能是 "计算机软件" 和 "计算机硬件"。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="ed5bd-149">**模式**从下拉列表中, 选择 "**主题**" 选项:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="ed5bd-150">**创建和应用模型**: 从一段文件的模型计算主题, 然后在它们之间分发文件。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="ed5bd-151">**创建模型**: 计算来自一段文件的主题模型。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="ed5bd-152">拆分文件的应用过程是在其他时间单独完成的。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="ed5bd-153">**应用模型**: 仅当以前创建且尚未应用模型时, 才会显示此选项。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="ed5bd-154">这将根据主题划分这些文件。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="ed5bd-155">在 "**导出**" 部分:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="ed5bd-156">在 "**选择导出批处理**" 中:</span><span class="sxs-lookup"><span data-stu-id="ed5bd-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="ed5bd-157">从 "**导出批处理**" 列表中, 选择 "批次名称" 或 "导出结果" 以导出批处理 01 (默认批处理)。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="ed5bd-158">若要导出添加到现有事例中的新文件的结果, 请继续使用当前批处理。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="ed5bd-159">若要在批处理中创建会话, 请选择同一批次号码并单击 "**创建导出会话**" 可以使用此选项以增量方式导出与上一批次相同的参数。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="ed5bd-160">若要导出到新批次, \*\*\*\* ![请单击 "](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)添加添加图标", 并在 "批**次名称**" 中输入新名称 (或接受默认值) 和 "**批处理说明**" 中的说明。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-160">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="ed5bd-161">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="ed5bd-162">若要编辑批次名称或说明, 请在 "**导出批次**" \*\*\*\* ![中选择名称](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), 单击 "编辑编辑图标", 然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ed5bd-163">在为导出批处理运行会话之后, 将无法删除它们。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="ed5bd-164">此外, 在第一次运行会话后, 仅可编辑某些参数。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="ed5bd-165">若要创建重复的导出批处理, 请选择 "**重复导出批处理** !["。创建](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)重复的导出批处理图标, 并在面板中输入重复批次的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="ed5bd-166">若要删除导出批处理, 请选择 "**删除** ![删除导出批](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)次图标"。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="ed5bd-167">若要查看批次的历史记录, 请选择 "**批次历史** ![记录视图历史记录" 图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-167">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="ed5bd-168">在 "定义 p **opulation** " 下, 选择 "**仅包括相关性截止分数**和/或**优化导出批次**以上的文件" (如果要微调导出批处理的设置)。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="ed5bd-169">如果选择 "**仅包括相关性截止分数以上的文件**", 则会启用该**问题**, 如果文件的相关性分数高于所选问题的截止分数, 则导出文件。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="ed5bd-170">除非 " **For 审阅**" 筛选器排除了该文件, 否则将导出该文件。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="ed5bd-171">如果选择 "**优化导出批处理**", 则将启用 "**重复数据消除**和**按 ' 审阅 ' 筛选" 字段**单选按钮。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="ed5bd-172">如果选择 "**重复**消除", 则将根据定义的策略将重复文件筛选掉: [事例级别 (默认): 从整个事例中的每一组重复文件中, 除一个文件之外的所有文件都将 duped。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="ed5bd-173">保管人级别: 从同一个保管人的每组重复文件中, 除一个文件之外的所有文件都将 duped。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="ed5bd-174">导出输出中提供了所有重复文件的记录。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="ed5bd-175">如果选择 **"按 ' 审阅 ' 筛选"** 字段, 请选择 "**元数据" 下**的 "修改" 以输入 **"审阅"** 字段设置。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="ed5bd-176">选择 "**包括输入文件**" 以将源文件包含在程序包内容中。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-176">Select **Include input files**to include source files in the package content.</span></span> <span data-ttu-id="ed5bd-177">您可以清除此选项以加快导出过程。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="ed5bd-178">请注意, 在任何情况下都会导出本地文件。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="ed5bd-179">在 "**定义元数据**" 下, 从 "**导出模板**" 列表中的以下选项中进行选择 (每个会话一次)。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="ed5bd-180">**Standard**: 数据项目、元数据和属性的基本集合。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="ed5bd-181">如果已在高级电子数据展示中处理导入数据, 并将导出数据上载到已包含文件的系统, 请使用此选项。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="ed5bd-182">默认情况下, 将创建并填充 "导出模板" 列。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="ed5bd-183">**All**: 完整的标准元数据集, 包括所有处理数据, 以及分析和相关性分数。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="ed5bd-184">当高级电子数据展示执行首次将文件数据上传到外部系统时, 此模板是必需的。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="ed5bd-185">**问题**: 选择**所有问题**或选择你创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="ed5bd-186">选择 **"确定"** 以保存 "高级设置"、"**还原默认**值以使用默认值" 或 "**取消**" 取消设置高级设置。</span><span class="sxs-lookup"><span data-stu-id="ed5bd-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed5bd-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed5bd-187">See also</span></span>
<span data-ttu-id="ed5bd-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ed5bd-188"></span></span>

[<span data-ttu-id="ed5bd-189">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="ed5bd-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

