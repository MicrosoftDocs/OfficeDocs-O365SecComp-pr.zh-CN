---
title: 导出 Office 365 高级电子数据展示中的结果
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '了解如何定义用于从 Office 365 高级电子数据展示中导出结果的选项, 包括为导出批处理指定参数的过程。 '
ms.openlocfilehash: 02314b0848d8e7bb37a7cb96fa4a721cf2622712
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218092"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="d90d9-103">导出 Office 365 高级电子数据展示中的结果</span><span class="sxs-lookup"><span data-stu-id="d90d9-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="d90d9-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="d90d9-106">本主题介绍高级电子数据展示导出设置选项。</span><span class="sxs-lookup"><span data-stu-id="d90d9-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="d90d9-107">**本主题内容：**</span><span class="sxs-lookup"><span data-stu-id="d90d9-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="d90d9-108">定义导出批处理和会话</span><span class="sxs-lookup"><span data-stu-id="d90d9-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="d90d9-109">增量和其他导出</span><span class="sxs-lookup"><span data-stu-id="d90d9-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="d90d9-110">设置批处理导出参数</span><span class="sxs-lookup"><span data-stu-id="d90d9-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="d90d9-111">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="d90d9-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="d90d9-112">定义导出批处理和会话</span><span class="sxs-lookup"><span data-stu-id="d90d9-112">Defining export batches and sessions</span></span>
<span data-ttu-id="d90d9-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="d90d9-113"></span></span>

<span data-ttu-id="d90d9-p102">导出批处理允许使用一组已定义的参数进行导出处理。利用高级电子数据展示, 可以定义批处理, 以自定义每个导出。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="d90d9-p103">参数是按导出批次定义的。默认情况下, 为事例的第一批次创建名为 "导出批处理 01" 的批处理。您还可以编辑批次名称和说明。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="d90d9-119">导出会话是导出批处理中的高级电子数据展示导出的执行。</span><span class="sxs-lookup"><span data-stu-id="d90d9-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="d90d9-120">增量和其他导出</span><span class="sxs-lookup"><span data-stu-id="d90d9-120">Incremental and additional exports</span></span>
<span data-ttu-id="d90d9-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="d90d9-121"></span></span>

<span data-ttu-id="d90d9-p104">您可以在导出批处理中运行多个导出会话, 以确保基于相同的导出模板和参数的结果一致。对于批处理中的每个会话, 您可以导出新处理的事例数据的分析, 并对每个 "增量" 处理。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="d90d9-p105">为了使用不同的参数集导出, 首先需要创建新的批处理。新批处理中的第一个会话将生成到目前为止处理的文件的结果, 无论这些文件是通过一个还是多个导入进行导入和处理的。每个批处理都会重新计算透视、相似性、inclusives 等。会话使用为批处理定义的参数, 不重新计算每次会话执行的透视、相似性、inclusives 等。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="d90d9-p106">例如, 假定已导入事例并分析其数据。若要检索增量数据的临近重复和电子邮件线程处理结果, 请单击以前用于导出数据的相同批处理中的 "**创建导出会话**"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="d90d9-129">设置批处理导出参数</span><span class="sxs-lookup"><span data-stu-id="d90d9-129">Set up batch export parameters</span></span>
<span data-ttu-id="d90d9-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="d90d9-130"></span></span>

<span data-ttu-id="d90d9-p107">电子数据展示导出工具用于将高级电子数据展示中的搜索结果导出到本地计算机。若要增加数据传输吞吐量并加快导出过程, 可以在用于导出搜索结果的计算机上配置 Windows 注册表设置。如果您想要提高下载速度, 请先配置注册表设置, 然后再设置导出参数。有关详细信息, 请参阅[在从 Office 365 导出电子数据展示搜索结果时提高下载速度](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="d90d9-135">在高级电子数据展示中, 选择一个事例, 然后单击 "**导出** \> **设置**"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="d90d9-136">从 "**导出批处理**" 列表中, 选择 "批次名称" 或 "导出结果" 以导出批处理 01 (默认批处理)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="d90d9-p108">若要导出添加到现有事例中的新文件的结果, 请继续使用当前批处理。若要在批处理中创建会话, 请选择同一批次号码并单击 "**创建导出会话**" 可以使用此选项以增量方式导出与上一批次相同的参数。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="d90d9-p109">若要导出到新批次, \*\*\*\* ![请单击 "](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)添加添加图标", 并在 "批**次名称**" 中输入新名称 (或接受默认值) 和 "**批处理说明**" 中的说明。单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p109">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
    - <span data-ttu-id="d90d9-141">若要编辑批次名称或说明, 请在 "**导出批次**" \*\*\*\* ![中选择名称](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), 单击 "编辑编辑图标", 然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="d90d9-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="d90d9-p110">在为导出批处理运行会话之后, 将无法删除它们。此外, 在第一次运行会话后, 仅可编辑某些参数。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="d90d9-144">若要创建重复的导出批处理, 请选择 "**重复导出批处理** !["。创建](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)重复的导出批处理图标, 并在面板中输入重复批次的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="d90d9-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="d90d9-145">若要删除导出批处理, 请选择 "**删除** ![删除导出批](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)次图标"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="d90d9-146">若要查看批次的历史记录, 请选择 "**批次历史** ![记录视图历史记录" 图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-146">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="d90d9-147">如果要微调导出批处理的设置, 请在 "**填充**" 下选择 "**仅包括关联性截止分数**和/或**优化导出批处理**以上的文件"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="d90d9-p111">如果选择 "**仅包括相关性截止分数的文件**", 则会启用该**问题**。如果文件的相关性分数高于所选问题的截止分数, 则将导出该文件, 除非它被 "审阅" 筛选器排除。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="d90d9-p112">如果选择 "**优化导出批处理**", 将启用 "**重复数据消除**和按 ' 审阅 ' 筛选" 字段单选按钮。如果选择 "**重复**消除", 则将根据定义的策略筛选出重复文件 [事例级别 (默认): 从整个事例中的每一组重复文件中, 除一个文件之外的所有文件都将 duped。保管人级别: 从同一个保管人的每组重复文件中, 除一个文件之外的所有文件都将 duped。导出输出包含所有重复文件的记录。如果选择 **"按 ' 审阅 ' 筛选"** 字段, 请选择 "**元数据" 下**的 "修改" 以输入 **"审阅"** 字段设置。选择 "**包括输入文件**" 以将源文件包含在程序包内容中。您可以清除此设置以加快导出过程。请注意, 在任何情况下都会导出本地文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="d90d9-157">在 "**元数据**" 下, 从 "**导出模板**" 列表中的以下选项中进行选择 (每个会话一次)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="d90d9-p113">**Standard**: 数据项目、元数据和属性的基本集合。如果已在高级电子数据展示中处理导入数据, 并将导出数据上载到已包含文件的系统, 请使用此选项。默认情况下, 将创建并填充 "导出模板" 列。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="d90d9-p114">**All**: 完整的标准元数据集, 包括所有处理数据, 以及分析和相关性分数。当高级电子数据展示执行首次将文件数据上传到外部系统时, 此模板是必需的。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="d90d9-163">**问题**: 选择**所有问题**或选择你创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="d90d9-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="d90d9-164">在 "**目标**:" 下</span><span class="sxs-lookup"><span data-stu-id="d90d9-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="d90d9-165">**下载到本地计算机**</span><span class="sxs-lookup"><span data-stu-id="d90d9-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="d90d9-166">**导出到用户定义的 Azure blob**: 如果选中此选项, 则可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="d90d9-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="d90d9-p115">将导出包存储到用户定义的 Azure blob 后, 数据将不再由高级电子数据展示进行管理;它由 Azure blob 管理。这意味着, 如果删除了该案例, 导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="d90d9-169">**保存 sas 令牌以供将来导出会话**: 如果选中此选项, 则会在高级电子数据展示的内部数据库中对 sas 令牌进行加密, 以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="d90d9-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="d90d9-p116">目前, SAS 令牌在一个月后过期。如果您在多个月后尝试下载, 您必须撤消上次会话, 然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="d90d9-172">单击 "**修改**" 以设置 "审阅" 字段设置。</span><span class="sxs-lookup"><span data-stu-id="d90d9-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![设置以查看导出批处理的域设置](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="d90d9-p117">在 "**查看字段设置**" 下的 "**选择方案**" 下拉列表中, 选择评审的方案和范围。将根据您的选择显示设置。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p117">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review. The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="d90d9-176">**查看所有**(默认值): 默认情况下, 选择所有电子邮件、附件和文档。</span><span class="sxs-lookup"><span data-stu-id="d90d9-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="d90d9-177">**查看集合中的所有唯一内容**: Inclusives 和唯一的包含副本、电子邮件集级别中的唯一附件以及每组完全相同的代表。</span><span class="sxs-lookup"><span data-stu-id="d90d9-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="d90d9-178">**查看无包含副本中的所有唯一内容**: Inclusives、电子邮件集级别中的唯一附件、每组完全相同的代表。</span><span class="sxs-lookup"><span data-stu-id="d90d9-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="d90d9-179">**查看所有独特的内容和相关系列文件**: Inclusives、电子邮件集级别中的唯一附件、每组完全相同的代表、展开以包含 "家庭文件"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="d90d9-p118">**自定义**(允许您定义对话框中的选项): 默认设置是保留当前选择并启用所有对话框选项, 以允许其选择。如果选择此选项, 则可以自定义电子邮件、文档、附件和杂项的设置。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p118">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="d90d9-182">在 "**电子邮件**" 下, 选择要导出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="d90d9-183">**所有电子邮件**: (默认值) 选择所有电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="d90d9-184">**Inclusives**: 包含的电子邮件是某个线程的最后一个电子邮件, 它包含来自该线程的所有其他电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="d90d9-185">**Inclusives 和唯一的包含副本**: 包含相同主题、正文和附件的包含副本和 Inclusives;唯一的包含副本是这些电子邮件的独特副本。</span><span class="sxs-lookup"><span data-stu-id="d90d9-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="d90d9-186">在 "**文档**" 下, 选择要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="d90d9-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="d90d9-187">**所有文档**: (默认值) 所有文档都处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="d90d9-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="d90d9-188">**透视**: 选择为具有邻近重复集的代表的文件, 该文件通常在审阅集时用作基准。</span><span class="sxs-lookup"><span data-stu-id="d90d9-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="d90d9-189">**来自每个精确副本集的代表**: 唯一的邻近重复文件 (包括数据透视)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="d90d9-190">在 "**附件**" 下, 选择要导出的附件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="d90d9-191">**所有附件**: (默认值) 选择所有附件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="d90d9-192">**事例级别中的唯一附件**: 指定的事例内的唯一附件文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="d90d9-193">**电子邮件集级别中的唯一附件**: 指定的电子邮件用例中的唯一附件文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="d90d9-p119">在 "**Micellaneous**" 下, 您可以选择将**附件视为文档**, 将**电子邮件视为文档**, 或者**展开以包含 "家庭文件**"。当您选择 "**扩展" 以包括系列文件**时, 对于标记为要审阅的每个文件, 将同时标记同一系列的所有文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p119">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="d90d9-196">选择 "**保存**" 以保存设置。</span><span class="sxs-lookup"><span data-stu-id="d90d9-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="d90d9-197">指定导出参数后, 若要启动 "导出批处理", 请单击 "**创建导出会话**"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="d90d9-p120">在导出过程中, 状态将显示在 "**任务状态**" 中。结果将显示在 "**导出摘要**" 中。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p120">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="d90d9-200">在 "**下载文件**" 窗口中, 单击 "**复制到剪贴板**" 以复制导出密钥。</span><span class="sxs-lookup"><span data-stu-id="d90d9-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下载文件](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="d90d9-202">单击"关闭"。</span><span class="sxs-lookup"><span data-stu-id="d90d9-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="d90d9-203">启动电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="d90d9-203">The eDiscovery Export Tool is started.</span></span>
    
    ![电子数据展示导出工具](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="d90d9-205">在**电子数据展示导出工具**中:</span><span class="sxs-lookup"><span data-stu-id="d90d9-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="d90d9-206">在 **"粘贴将用于连接到源的共享访问签名**" 中, 将 youcopied 的导出密钥粘贴到步骤7中的 "剪贴板" 中。</span><span class="sxs-lookup"><span data-stu-id="d90d9-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="d90d9-207">单击 "**浏览**" 以选择用于将下载的导出文件存储在本地计算机上的目标位置。</span><span class="sxs-lookup"><span data-stu-id="d90d9-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="d90d9-p121">单击 "**启动**"。将导出文件下载到本地计算机。如果在步骤4中选择 "**导出到用户定义的 Azure blob** ", 则会将会话导出到所选的 blob 存储 URL 目标。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p121">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="d90d9-210">有关导出报告中的字段的完整说明, 请参阅[导出报告字段](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="d90d9-211">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="d90d9-211">Export report output files</span></span>
<span data-ttu-id="d90d9-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="d90d9-212"></span></span>

<span data-ttu-id="d90d9-213">下表列出了运行导出批处理时生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="d90d9-214">**文件名**</span><span class="sxs-lookup"><span data-stu-id="d90d9-214">**File name**</span></span>|<span data-ttu-id="d90d9-215">**文件类型**</span><span class="sxs-lookup"><span data-stu-id="d90d9-215">**File type**</span></span>|<span data-ttu-id="d90d9-216">**说明**</span><span class="sxs-lookup"><span data-stu-id="d90d9-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d90d9-217">导出摘要</span><span class="sxs-lookup"><span data-stu-id="d90d9-217">Export summary</span></span>  <br/> |<span data-ttu-id="d90d9-218">csv</span><span class="sxs-lookup"><span data-stu-id="d90d9-218">csv</span></span>  <br/> |<span data-ttu-id="d90d9-219">由电子数据展示导出工具生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="d90d9-220">跟踪</span><span class="sxs-lookup"><span data-stu-id="d90d9-220">Trace</span></span>  <br/> |<span data-ttu-id="d90d9-221">txt</span><span class="sxs-lookup"><span data-stu-id="d90d9-221">txt</span></span>  <br/> |<span data-ttu-id="d90d9-222">由电子数据展示导出工具生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="d90d9-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="d90d9-223">提取的文本文件</span><span class="sxs-lookup"><span data-stu-id="d90d9-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="d90d9-224">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="d90d9-224">File folder</span></span>  <br/> |<span data-ttu-id="d90d9-225">包含导出文件的提取文本文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d90d9-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="d90d9-226">输入或本机文件</span><span class="sxs-lookup"><span data-stu-id="d90d9-226">Input or native files</span></span>  <br/> |<span data-ttu-id="d90d9-227">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="d90d9-227">File folder</span></span>  <br/> |<span data-ttu-id="d90d9-228">包含导出文件的本机和输入文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d90d9-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="d90d9-229">导出列表</span><span class="sxs-lookup"><span data-stu-id="d90d9-229">Export list</span></span>  <br/> |<span data-ttu-id="d90d9-230">xlsx</span><span class="sxs-lookup"><span data-stu-id="d90d9-230">xlsx</span></span>  <br/> |<span data-ttu-id="d90d9-p122">以 .xlsx 格式导出的文件元数据。文件中的字段根据模板用户选择导出的。如果需要, 将创建多个文件, 每个文件包含 100 150K 行。如果某个值包含的字符数多于 Excel 单元格可以包含的字符数 (当前限制为32767个字符), 则值将被修整为允许的最大长度。如果某个值被修整, 则该单元格的背景色为红色, 表示这对用户。如果将电子邮件发送到大型通讯组, 则 "电子邮件参与者" 是可以超过长度限制的字段的示例。有关输出字段的详细信息, 请参阅[导出报告字段](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p122">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="d90d9-237">加载文件</span><span class="sxs-lookup"><span data-stu-id="d90d9-237">Load file</span></span>  <br/> |<span data-ttu-id="d90d9-238">csv</span><span class="sxs-lookup"><span data-stu-id="d90d9-238">csv</span></span>  <br/> |<span data-ttu-id="d90d9-p123">以 csv 格式导出的文件元数据, 用于加载到不同的应用程序。文件中的字段根据模板用户选择导出的。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p123">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="d90d9-241">成功指示器</span><span class="sxs-lookup"><span data-stu-id="d90d9-241">Success indicator</span></span>  <br/> |<span data-ttu-id="d90d9-242">txt</span><span class="sxs-lookup"><span data-stu-id="d90d9-242">txt</span></span>  <br/> |<span data-ttu-id="d90d9-p124">仅在导出到第三方 Azure blob 时创建。如果完全导出成功, 将创建文件。如果出现故障或部分成功, 将不会创建文件。文件将在根文件夹中创建, 允许在不同的导出批处理/会话状态上进行自动跟踪。这是一个空文件。其名称为: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime。</span><span class="sxs-lookup"><span data-stu-id="d90d9-p124">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d90d9-249">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d90d9-249">See also</span></span>

[<span data-ttu-id="d90d9-250">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="d90d9-250">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="d90d9-251">查看批次历史记录和导出过去的结果</span><span class="sxs-lookup"><span data-stu-id="d90d9-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="d90d9-252">Office 365 高级电子数据展示快速设置</span><span class="sxs-lookup"><span data-stu-id="d90d9-252">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="d90d9-253">导出报告字段</span><span class="sxs-lookup"><span data-stu-id="d90d9-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="d90d9-254">提高导出 Office 365 中的电子数据展示搜索结果时的下载速度</span><span class="sxs-lookup"><span data-stu-id="d90d9-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

