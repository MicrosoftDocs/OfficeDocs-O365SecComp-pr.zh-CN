---
title: 使用 Office 365 高级电子数据展示中的快速分析
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何运行 Office 365 高级电子数据展示的 Express 分析模式
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525268"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="ee888-103">使用 Office 365 高级电子数据展示中的快速分析</span><span class="sxs-lookup"><span data-stu-id="ee888-103">Use Express Analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="ee888-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="ee888-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ee888-106">您可以使用**Express 分析**快速分析案例和导出结果。</span><span class="sxs-lookup"><span data-stu-id="ee888-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="ee888-p102">Express 分析可用于计算近乎重复项和电子邮件线程和计算主题。您还可以[Express 分析的高级的设置](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)中设置某些主题、 文档相似性和导出文件的参数。</span><span class="sxs-lookup"><span data-stu-id="ee888-p102">You can use express analysis to calculate near-duplicates and email threads and calculate themes. You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="ee888-109">运行 Express 分析</span><span class="sxs-lookup"><span data-stu-id="ee888-109">Run Express analysis</span></span>

1. <span data-ttu-id="ee888-110">在**Express 分析**(1) 选项卡，选择启用的容器 * * Express 分析 * * (2) 和**高级设置**按钮。</span><span class="sxs-lookup"><span data-stu-id="ee888-110">In the **Express analysis** (1) tab, select a container to enable the ** Express analysis ** (2), and **Advanced settings** buttons.</span></span> 
    
    ![Express 分析页的屏幕截图](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="ee888-112">下**分析参数**：</span><span class="sxs-lookup"><span data-stu-id="ee888-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="ee888-p103">如果您想要运行分析，检查**计算近乎重复项和电子邮件线程**。默认情况下选择它。</span><span class="sxs-lookup"><span data-stu-id="ee888-p103">Check **Calculate near-duplicates and email threads** if you want to run the analysis. It is selected by default.</span></span> 
    
  - <span data-ttu-id="ee888-p104">检查**计算主题**处理所有文件并将主题分配给它们。默认情况下选择它。</span><span class="sxs-lookup"><span data-stu-id="ee888-p104">Check **Calculate Themes** to process all files and assign themes to them. It is selected by default.</span></span> 
    
3. <span data-ttu-id="ee888-117">在**导出目标**：</span><span class="sxs-lookup"><span data-stu-id="ee888-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="ee888-118">检查**下载到本地计算机中**下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ee888-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="ee888-119">如果您检查**导出到用户定义的 Azure blob**然后您还可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="ee888-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ee888-p105">一旦导出包存储到用户定义 Azure blob，高级电子数据展示不再管理的数据。它被管理 Azure 的 blob。这意味着，如果您删除这种情况，导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="ee888-p105">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery. it is managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="ee888-123">**保存 SAS 将来导出会话令牌**： 如果选中，都将被 SAS 令牌加密以供将来使用高级电子数据展示的内部数据库中。</span><span class="sxs-lookup"><span data-stu-id="ee888-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ee888-p106">当前该 SA 令牌有效期一个月。如果您尝试在您需要撤消最后一个会话超过一个月后下载，然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="ee888-p106">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="ee888-126">若要启动 express 分析具有默认设置，选择**Express 分析**，并将显示**任务状态**页</span><span class="sxs-lookup"><span data-stu-id="ee888-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="ee888-127">在**任务状态**页上，您可以展开**过程**、**分析**和**导出**选项卡以显示有关 express 运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ee888-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![屏幕截图的高级电子数据展示 Express 分析任务状态页](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="ee888-129">选择**Express 分析摘要**页上列出有关运行的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ee888-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="ee888-p107">在**Express 分析摘要**页的底部，选择**下载上次会话**下载分析文件 tp 本地计算机。您首先需要下载电子数据展示导出工具并粘贴到电子数据展示导出工具的导出密钥。</span><span class="sxs-lookup"><span data-stu-id="ee888-p107">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer. You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="ee888-132">Express 分析的高级的设置</span><span class="sxs-lookup"><span data-stu-id="ee888-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="ee888-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ee888-133"></span></span>

<span data-ttu-id="ee888-134">您可以选择设置**高级设置**更改默认 Express 分析参数。</span><span class="sxs-lookup"><span data-stu-id="ee888-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="ee888-135">在**分析**部分中：</span><span class="sxs-lookup"><span data-stu-id="ee888-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="ee888-136">在**靠近重复项和电子邮件线程**，输入**文档相似性**值，或接受默认的 65%。</span><span class="sxs-lookup"><span data-stu-id="ee888-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="ee888-p108">在**主题的最大数目**输入或选择一个值主题创建的数目。默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="ee888-p108">In the **Max number of themes** enter or select a value for the number of themes to create. The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ee888-p109">增加了主题会影响性能，以及使通用化主题的能力。主题的更高版本数、 更精细它们是。例如，如果一 50 主题中包含"篮球、 支路，剪，Lakers"; 例如主题300 主题可能包括单独的主题:"支路"、"剪 2"、"Lakers"。如果您具有"篮球"的任何认知度的主题，并对 ECA 使用该功能，查看主题"篮球"非常有用。但是，如果处理有太多的主题，您可能永远不会看到的单词"篮球"并可能不知道，支路和剪是好篮球主题，若要查看，而不是项目上，启动和用于字形。</span><span class="sxs-lookup"><span data-stu-id="ee888-p109">Increasing the number of themes affects performance, as well as the ability of a theme to generalize. The higher the number of themes, the more granular they are. For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers". If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful. But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="ee888-p110">选择**建议主题**的**修改**建议主题单词以控制处理的主题。高级电子数据展示将专注于这些建议单词，然后尝试创建一个或多个相关的主题，基于"最大主题数目"设置。</span><span class="sxs-lookup"><span data-stu-id="ee888-p110">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing. Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="ee888-p111">例如，如果所建议的单词"computer"，并且您"主题的最大数量"指定"2"，高级电子数据展示将尝试生成与 word"computer"的两个主题。两个主题可能是"计算机 software"和"计算机 hardware"，例如。</span><span class="sxs-lookup"><span data-stu-id="ee888-p111">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer". The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="ee888-149">**模式**从下拉列表中，选择**主题**选项:</span><span class="sxs-lookup"><span data-stu-id="ee888-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="ee888-150">**创建和应用模型**： 计算由模型文件的一段中的主题，然后分布在它们之间的文件。</span><span class="sxs-lookup"><span data-stu-id="ee888-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="ee888-p112">**创建模型**： 计算一段的文件中的主题模型。划分文件的应用过程是单独完成另一次。</span><span class="sxs-lookup"><span data-stu-id="ee888-p112">**Create model**: Calculates a themes model from a segment of the files. The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="ee888-p113">**应用模型**： 是否以前创建和尚未应用模型，才会显示此选项。这将分割基于主题的文件。</span><span class="sxs-lookup"><span data-stu-id="ee888-p113">**Apply model**: This option is only shown if a model was created previously and not yet applied. This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="ee888-155">在**导出**部分中：</span><span class="sxs-lookup"><span data-stu-id="ee888-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="ee888-156">**选择导出批次**： 中</span><span class="sxs-lookup"><span data-stu-id="ee888-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="ee888-157">从**导出批处理**列表中，选择批处理名称或将结果导出到导出批处理 01、 （默认批次）。</span><span class="sxs-lookup"><span data-stu-id="ee888-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="ee888-p114">若要导出结果的新文件添加到现有用例，继续使用您当前的批次。若要创建的批处理中的会话，请选择的相同的批次编号，单击**创建导出会话**可以使用此选项以增量方式为上一批次，导出相同的参数。</span><span class="sxs-lookup"><span data-stu-id="ee888-p114">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="ee888-p115">若要导出到新的批次，单击**添加**![图标添加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批处理名称**中输入新的名称 （或接受默认值） 以及在**说明批次**的说明。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ee888-p115">To export to a new batch, click **Add**![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
  - <span data-ttu-id="ee888-162">若要编辑的批处理名称或说明，请选择中**导出批次**的名称，单击**编辑**![编辑图标](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="ee888-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ee888-p116">您已运行导出批次会话后，他们不能删除。此外，运行第一个会话后，即可进行编辑只有一些参数。</span><span class="sxs-lookup"><span data-stu-id="ee888-p116">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="ee888-165">若要创建的重复导出批次，请选择**重复导出批处理**![创建重复导出批处理图标](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)在面板中输入名称和重复批次的说明。</span><span class="sxs-lookup"><span data-stu-id="ee888-165">To create a duplicate export batch, choose **Duplicate export batch**![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="ee888-166">若要删除的导出批次，选择**删除**![删除导出批处理图标](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="ee888-166">To delete an export batch, choose **Delete**![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="ee888-167">若要查看的批次的历史记录，请选择**批处理历史记录**![查看历史记录图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="ee888-167">To view the history of a batch, choose **Batch history**![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="ee888-p117">在定义 p 下**opulation:** 选择**仅包括文件相关性截止分数上方**和/或**优化导出批次**，如果您想要调整您导出批次的设置。如果您选择**包括仅上方相关性截止分数的文件**，然后启用，**问题**，并且如果该文件的相关性分数大于所选问题的截止分数，然后将导出文件。将导出的文件，除非排除了筛选器**进行审阅**。如果您选择**优化导出批处理**，然后**消除**和**Filter by 审阅字段**单选按钮处于启用状态。如果您选择**消除**，然后复制文件将被筛选出根据定义的策略: [Case 级别 （默认值）： 从每个组重复文件在整个的情况下，所有而不是一个文件将重复消除。Custodian 级别： 所有而不是一个文件将从每个组的相同 custodian 重复文件，重复消除。导出输出中可用的所有重复的文件的记录。如果您选择**筛选器的查看**字段中，选择**修改下元数据**输入**供审阅**字段设置。选择**包含输入的文件**要包含在包内容中的源代码文件。您可以清除此选项以加快导出过程。请注意，将在任何情况下导出的本机文件。</span><span class="sxs-lookup"><span data-stu-id="ee888-p117">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch. If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported. The file will be exported unless it's excluded by the ' **For review** filter. If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled. If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped. A record of all duplicate files is available in export output. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files**to include source files in the package content. You can clear this option to speed up the export process. Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="ee888-179">下**定义元数据**，从 （每次会话） 的**导出模板**列表中的以下选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="ee888-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="ee888-p118">**标准**： 套基本的数据项目、 元数据，而将属性。高级电子数据展示中已处理数据导入和导出数据上载到系统已包含的文件时，请使用此选项。默认情况下，导出模板列创建和填充。</span><span class="sxs-lookup"><span data-stu-id="ee888-p118">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="ee888-p119">**所有**： 整套标准元数据，包括所有处理数据，以及分析和相关性分数。此模板时需要高级电子数据展示执行处理和文件数据上载到外部系统的第一次。</span><span class="sxs-lookup"><span data-stu-id="ee888-p119">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="ee888-185">**问题**： 选择**所有问题**，或者都选择您已创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="ee888-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="ee888-186">选择**确定**保存高级的设置，**还原默认设置**为使用默认值，或**取消**取消设置的高级的设置。</span><span class="sxs-lookup"><span data-stu-id="ee888-186">Choose **OK**to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee888-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee888-187">See also</span></span>
<span data-ttu-id="ee888-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="ee888-188"></span></span>

[<span data-ttu-id="ee888-189">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="ee888-189">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)

