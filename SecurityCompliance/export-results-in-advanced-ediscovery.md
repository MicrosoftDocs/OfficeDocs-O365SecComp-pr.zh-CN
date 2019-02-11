---
title: 导出 Office 365 高级电子数据展示中的结果
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
ms.assetid: a9951a07-10b3-48cb-b37a-0ffaa24931ad
description: '了解如何定义从 Office 365 高级电子数据展示，包括指定导出批次的参数的过程中导出结果的选项。 '
ms.openlocfilehash: 49dab9820735af3bf5c322fc531c78a6baab2f8e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559045"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a><span data-ttu-id="8ba2c-103">导出 Office 365 高级电子数据展示中的结果</span><span class="sxs-lookup"><span data-stu-id="8ba2c-103">Export results in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="8ba2c-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8ba2c-106">本主题介绍了高级电子数据展示导出安装程序选项。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-106">This topic describes the Advanced eDiscovery Export Setup options.</span></span>
  
 <span data-ttu-id="8ba2c-107">**本主题内容：**</span><span class="sxs-lookup"><span data-stu-id="8ba2c-107">**In this topic:**</span></span>
  
- [<span data-ttu-id="8ba2c-108">定义导出批次和会话</span><span class="sxs-lookup"><span data-stu-id="8ba2c-108">Defining export batches and sessions</span></span>](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [<span data-ttu-id="8ba2c-109">增量和其他导出</span><span class="sxs-lookup"><span data-stu-id="8ba2c-109">Incremental and additional exports</span></span>](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [<span data-ttu-id="8ba2c-110">设置批次导出参数</span><span class="sxs-lookup"><span data-stu-id="8ba2c-110">Set up batch export parameters</span></span>](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [<span data-ttu-id="8ba2c-111">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="8ba2c-111">Export report output files</span></span>](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a><span data-ttu-id="8ba2c-112">定义导出批次和会话</span><span class="sxs-lookup"><span data-stu-id="8ba2c-112">Defining export batches and sessions</span></span>
<span data-ttu-id="8ba2c-113"><a name="BK_Define"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba2c-113"></span></span>

<span data-ttu-id="8ba2c-p102">导出批处理允许导出处理使用一组已定义的参数。高级电子数据展示可以定义自定义每次导出的批次。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p102">An export batch allows export processing using a set of defined parameters. Advanced eDiscovery enables you to define batches to customize each export.</span></span>
  
<span data-ttu-id="8ba2c-p103">每个导出批处理定义参数。默认情况下，将用例的第一个批处理创建名为"导出批处理 01"的批次。您还可以编辑的批处理名称和说明。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p103">Parameters are defined per export batch. A batch named "Export batch 01" is created by default for the first batch of a case. You can also edit the batch name and description.</span></span>
  
<span data-ttu-id="8ba2c-119">高级电子数据展示导出导出批内执行的导出会话。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-119">An export session is an execution of Advanced eDiscovery Export within an export batch.</span></span>
  
## <a name="incremental-and-additional-exports"></a><span data-ttu-id="8ba2c-120">增量和其他导出</span><span class="sxs-lookup"><span data-stu-id="8ba2c-120">Incremental and additional exports</span></span>
<span data-ttu-id="8ba2c-121"><a name="BK_IncrementalReports"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba2c-121"></span></span>

<span data-ttu-id="8ba2c-p104">您可以运行中的导出批次，以确保一致的结果基于同一导出模板和参数的多个导出会话。为批次中的每个会话，您可以导出分析的新处理案例数据和处理每个"增量。"</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p104">You can run multiple export sessions within an export batch, to ensure consistent results based on the same export template and parameters. For each session within a batch, you can export analytics for newly processed case data and process each "incrementally."</span></span>
  
<span data-ttu-id="8ba2c-p105">若要导出使用一组不同的参数，首先需要创建新的批次。新的批次中的第一个会话将产生的处理情况为止，已导入这些文件并将其处理通过一个或多个导入的文件的结果。每一批次重新计算数据透视表、 相似性、 inclusives 等。会话使用批处理定义的参数和数据透视表、 相似性、 inclusives 等每次会话执行不重新计算。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p105">In order to export using a different set of parameters, you first need to create a new batch. The first session in the new batch will produce results for files processed in the case so far, whether or not these files were imported and processed over one or multiple Imports. Each batch recalculates pivots, similarity, inclusives, etc. Sessions use the parameters defined for the batch and do not recalculate pivots, similarity, inclusives, etc. for each session execution.</span></span>
  
<span data-ttu-id="8ba2c-p106">例如，假定种情况下已导入和分析其数据。若要检索近乎重复项和电子邮件超线程的增量数据的结果，请单击以前用来将数据导出的同一批次中的**创建导出会话**。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p106">For example, assume a case was imported and its data analyzed. In order to retrieve Near-duplicates and Email Threading results for the incremental data, click **Create export session** in the same batch that was previously used to export data.</span></span> 
  
## <a name="set-up-batch-export-parameters"></a><span data-ttu-id="8ba2c-129">设置批次导出参数</span><span class="sxs-lookup"><span data-stu-id="8ba2c-129">Set up batch export parameters</span></span>
<span data-ttu-id="8ba2c-130"><a name="BK_SetUpExport"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba2c-130"></span></span>

<span data-ttu-id="8ba2c-p107">电子数据展示导出工具用于从高级电子数据展示的搜索结果导出到本地计算机。为了提高数据传输吞吐量和大的加速导出过程，您可以用于导出搜索结果的计算机上配置的 Windows 注册表设置。如果您想要提高下载速度，配置注册表设置之前您设置导出参数。有关详细信息，请参阅[增加下载速度导出电子数据展示搜索结果从 Office 365 时](increase-download-speeds-when-exporting-ediscovery-results.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p107">The eDiscovery Export Tool is used to export search results from Advanced eDiscovery to your local computer. To increase the data transfer throughput and speed-up the export process, you can configure a Windows Registry setting on the computer that you use to export the search results. If you'd like to increase the download speed, configure the registry setting before you set up the export parameters. For more information, see [Increase the download speed when exporting eDiscovery search results from Office 365](increase-download-speeds-when-exporting-ediscovery-results.md).</span></span>
  
1. <span data-ttu-id="8ba2c-135">高级电子数据展示中, 选择用例，单击**导出** \> **安装程序**。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-135">In Advanced eDiscovery, select a Case and click **Export** \> **Setup**.</span></span>
    
    - <span data-ttu-id="8ba2c-136">从**导出批处理**列表中，选择批处理名称或将结果导出到导出批处理 01、 （默认批次）。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-136">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
    - <span data-ttu-id="8ba2c-p108">若要导出结果的新文件添加到现有用例，继续使用您当前的批次。若要创建的批处理中的会话，请选择的相同的批次编号，单击**创建导出会话**可以使用此选项以增量方式为上一批次，导出相同的参数。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p108">To export results for new files that you added to an existing case, continue with your current batch. To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
    - <span data-ttu-id="8ba2c-p109">若要导出到新的批次，单击**添加**![图标添加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批处理名称**中输入新的名称 （或接受默认值） 以及在**说明批次**的说明。单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p109">To export to a new batch, click **Add** ![add icon](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**. Click **OK**.</span></span>
    
    - <span data-ttu-id="8ba2c-141">若要编辑的批处理名称或说明，请选择中**导出批次**的名称，单击**编辑**![编辑图标](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然后修改字段。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-141">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="8ba2c-p110">您已运行导出批次会话后，他们不能删除。此外，运行第一个会话后，即可进行编辑只有一些参数。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p110">After you've run sessions for an export batch, they cannot be deleted. In addition, only some parameters can be edited once the first session is run.</span></span> 
  
    - <span data-ttu-id="8ba2c-144">若要创建的重复导出批次，请选择**重复导出批处理**![创建重复导出批处理图标](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)在面板中输入名称和重复批次的说明。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-144">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
    - <span data-ttu-id="8ba2c-145">若要删除的导出批次，选择**删除**![删除导出批处理图标](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-145">To delete an export batch, choose **Delete** ![Delete an export batch icon](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
    - <span data-ttu-id="8ba2c-146">若要查看的批次的历史记录，请选择**批处理历史记录**![查看历史记录图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-146">To view the history of a batch, choose **Batch history** ![View history icon](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="8ba2c-147">在**总体**，选择**仅包括文件相关性截止分数上方**和/或**优化导出批次**，如果您想要调整您导出批次的设置。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-147">Under **Population**, select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> 
    
3. <span data-ttu-id="8ba2c-p111">如果您选择**包括仅上方相关性截止分数的文件**，则启用**问题**。如果该文件的相关性分数大于所选问题的截止分数，除非它进行审阅筛选器排除将导出文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p111">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled. If the file's relevance score is higher than the cut-off score for the selected issue, the file will be exported unless it's excluded by the 'For review' filter.</span></span> 
  
    <span data-ttu-id="8ba2c-p112">如果您选择**优化导出批次**，**消除**和筛选器审阅通过域单选按钮处于启用状态。如果您选择**消除**，然后将根据定义的策略筛选出重复文件 [Case 级别 （默认值）： 从每个组重复文件在整个的情况下，所有而不是一个文件将重复消除。Custodian 级别： 所有而不是一个文件将从每个组的相同 custodian 重复文件，重复消除。]导出输出中包含的所有重复的文件的记录。如果您选择**筛选器的查看**字段中，选择**修改下元数据**输入**供审阅**字段设置。选择**包含输入的文件**要包含在包内容中的源代码文件。您可以清除此设置可加快导出过程。请注意，将在任何情况下导出的本机文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p112">If you select **Refine export batch**, the **De-dupe** and Filter by 'For review' field radio buttons are enabled. If you choose **De-dupe**, then duplicate files will be filtered out according to the policy defined [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped. Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.] The export output contains a record of all duplicate files. If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings. Select **Include input files** to include source files in the package content. You can clear this setting to speed up the export process. Note that the Native files will be exported in any case.</span></span> 
    
4. <span data-ttu-id="8ba2c-157">在**元数据**，下从 （每次会话） 的**导出模板**列表中的以下选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-157">Under **Metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
    - <span data-ttu-id="8ba2c-p113">**标准**： 套基本的数据项目、 元数据，而将属性。高级电子数据展示中已处理数据导入和导出数据上载到系统已包含的文件时，请使用此选项。默认情况下，导出模板列创建和填充。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p113">**Standard**: Basic set of data items, metadata, and properties. Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files. By default, export template columns are created and filled.</span></span>
    
    - <span data-ttu-id="8ba2c-p114">**所有**： 整套标准元数据，包括所有处理数据，以及分析和相关性分数。此模板时需要高级电子数据展示执行处理和文件数据上载到外部系统的第一次。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p114">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores. This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
    - <span data-ttu-id="8ba2c-163">**问题**： 选择**所有问题**，或者都选择您已创建的特定问题。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-163">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
5. <span data-ttu-id="8ba2c-164">在**目标**:</span><span class="sxs-lookup"><span data-stu-id="8ba2c-164">Under **Destination**:</span></span>
    
    - <span data-ttu-id="8ba2c-165">**下载到本地计算机**</span><span class="sxs-lookup"><span data-stu-id="8ba2c-165">**Download to local machine**</span></span>
    
    - <span data-ttu-id="8ba2c-166">**导出到用户定义的 Azure blob**： 如果选中此选项，则可以指定容器 URL 和 SAS 令牌。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-166">**Export to user-defined Azure blob**: If this is checked, you can specify a container URL and SAS token.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="8ba2c-p115">一旦导出包存储到用户定义的 Azure blob、 高级电子数据展示; 不再管理的数据它被管理 Azure 的 blob。这意味着，如果您删除这种情况，导出的文件仍将保留在 Azure blob 上。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p115">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery; it's managed by the Azure blob. This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
    - <span data-ttu-id="8ba2c-169">**保存 SAS 将来导出会话令牌**： 如果选中，都将被 SAS 令牌加密以供将来使用高级电子数据展示的内部数据库中。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-169">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="8ba2c-p116">当前该 SA 令牌有效期一个月。如果您尝试在您需要撤消最后一个会话超过一个月后下载，然后再次导出。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p116">Currently the SAS token expires after a month. If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
6. <span data-ttu-id="8ba2c-172">单击**修改**设置进行审阅字段设置。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-172">Click **Modify** to set the 'for review' field settings.</span></span> 
    
    ![导出批次查看字段设置为设置](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
   - <span data-ttu-id="8ba2c-p117">在**查看字段设置**下**选择方案**的下拉列表中，选择的方案和查看范围。根据您选择要显示的设置。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p117">Under **For review field settings**, in **Select scenario** pull-down list, select the scenario and scope of the review. The settings are displayed based on your selection.</span></span>
    
      - <span data-ttu-id="8ba2c-176">**查看所有**（默认值）： 默认情况下选中所有电子邮件、 附件和文档。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-176">**Review all** (default): All emails, attachments, and documents are selected by default.</span></span> 
    
      - <span data-ttu-id="8ba2c-177">**查看一组中的所有唯一内容**： Inclusives 和唯一的非独占副本，电子邮件中的唯一附件设置级别，代表从每个确切的重复项集。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-177">**Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="8ba2c-178">**查看一组-不含副本中的所有唯一内容**： Inclusives，电子邮件中的唯一附件设置级别，代表从每个确切的重复项集。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-178">**Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.</span></span>
    
      - <span data-ttu-id="8ba2c-179">**查看所有的唯一内容及相关的系列文件**： Inclusives，电子邮件设置级别，来自每个完全重复集代表中唯一附件扩展以包含系列文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-179">**Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.</span></span>
    
      - <span data-ttu-id="8ba2c-p118">**自定义**（允许您在对话框中定义的选项）： 默认值是保留当前选定内容并启用所有对话框选项，以允许其所选内容。如果选择此选项，可以然后自定义电子邮件、 文档、 附件的设置和 miscellaneous。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p118">**Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. If you select this option, you can then customize the settings for emails, documents, attachments and miscellaneous.</span></span>
    
    - <span data-ttu-id="8ba2c-182">在**电子邮件**，下选择要导出的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-182">Under **Emails**, select the emails you want to export.</span></span>
    
      - <span data-ttu-id="8ba2c-183">**所有电子邮件**: （默认值） 选择所有电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-183">**All emails**: (default) All emails are selected.</span></span>
    
      - <span data-ttu-id="8ba2c-184">**Inclusives**： 非独占电子邮件的线程，最后一个电子邮件，并且包含所有其他电子邮件从线程。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-184">**Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.</span></span>
    
      - <span data-ttu-id="8ba2c-185">**Inclusives 和唯一的非独占副本**： 非独占副本和 inclusives 具有相同主题、 正文和附件;唯一的非独占副本是唯一的这些电子邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-185">**Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .</span></span>
    
    - <span data-ttu-id="8ba2c-186">在**文档**下选择要导出的文档。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-186">Under **Documents**, select the documents you want to export.</span></span> 
    
      - <span data-ttu-id="8ba2c-187">**所有文档**: （默认值） 选择所有文档。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-187">**All documents**: (default) All documents are selected.</span></span>
    
      - <span data-ttu-id="8ba2c-188">**数据透视表**： 选择的代表近乎重复项集，查看设置时通常使用为基线的文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-188">**Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.</span></span>
    
      - <span data-ttu-id="8ba2c-189">**从每个完全重复集代表**： 唯一近乎重复文件 （包括数据透视表）。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-189">**Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).</span></span>
    
    - <span data-ttu-id="8ba2c-190">在**附件**下选择要导出的附件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-190">Under **Attachments**, select the attachments you want to export.</span></span> 
    
      - <span data-ttu-id="8ba2c-191">**所有附件**: （默认值） 选择所有附件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-191">**All attachments**: (default) All attachments are selected.</span></span>
    
      - <span data-ttu-id="8ba2c-192">**唯一附件事例级别**： 内指定用例的唯一的附件文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-192">**Unique attachment in case level**: Unique attachment files within the specified case.</span></span>
    
      - <span data-ttu-id="8ba2c-193">**电子邮件中的唯一附件设置级别**： 唯一的附件文件中指定的电子邮件大小写。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-193">**Unique attachment in email set level**: Unique attachment files within the specified email case.</span></span>
    
   - <span data-ttu-id="8ba2c-p119">下**Micellaneous**，您可以选择**将文档作为附件**、**将文档作为电子邮件**，或**展开，包括家庭文件**。当您选择**扩展以包含系列文件**，供审阅标记每个文件时，将同时也标记同一系列的所有文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p119">Under**Micellaneous**, you can choose to **Treat attachments as documents**, **Treat emails as documents**, or **Expand to include family files**. When you choose **Expand to include family files**, for each file that is flagged for review, all files of the same family will also be flagged.</span></span>
    
7. <span data-ttu-id="8ba2c-196">选择**保存**以保存设置。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-196">Choose **Save** to save the settings.</span></span> 
    
8. <span data-ttu-id="8ba2c-197">指定导出参数后，若要开始导出批次单击**创建导出会话**。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-197">After you specify export parameters, to start export batch, click **Create export session**.</span></span>
    
    <span data-ttu-id="8ba2c-p120">导出期间，将状态显示在**任务状态**。在**导出摘要**显示结果。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p120">During export, the status is displayed in **Task status**. The results are displayed in **Export summary**.</span></span>
    
9. <span data-ttu-id="8ba2c-200">在**文件下载**窗口中，单击**复制到剪贴板**复制导出密钥。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-200">In the **Download files** window, click **Copy to clipboard** to copy the Export key.</span></span> 
    
    ![下载文件](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
10. <span data-ttu-id="8ba2c-202">单击"关闭"。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-202">Click **Close**.</span></span> 
    
    <span data-ttu-id="8ba2c-203">启动电子数据展示导出工具。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-203">The eDiscovery Export Tool is started.</span></span>
    
    ![电子数据展示导出工具](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
11. <span data-ttu-id="8ba2c-205">在**电子数据展示导出工具**：</span><span class="sxs-lookup"><span data-stu-id="8ba2c-205">In the **eDiscovery Export Tool**:</span></span>
    
    -  <span data-ttu-id="8ba2c-206">在**粘贴将用于连接到源的共享访问签名**，导出密钥该 youcopied 到剪贴板中粘贴步骤 7。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-206">In **Paste the Shared Access Signature that will be used to connect to the source**, paste the Export key that youcopied to the clipboard in step 7.</span></span>
    
    - <span data-ttu-id="8ba2c-207">单击**浏览**，选择用于存储在本地计算机上下载的导出文件的目标位置。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-207">Click **Browse** to select the target location for storing the downloaded export files on the local machine.</span></span> 
    
    - <span data-ttu-id="8ba2c-p121">单击**启动**。导出文件下载到本地计算机。如果您在步骤 4 中选择**导出到用户定义的 Azure blob** ，会话将导出到您选择的 Blob 存储 URL 目标。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p121">Click **Start**.The export files are downloaded to the local machine. If you chose **Export to user-defined Azure blob** in step 4, the session is exported to a Blob storage URL destination of your choosing.</span></span>
    
<span data-ttu-id="8ba2c-210">导出报告中的字段的完整说明，请参阅[导出报表字段](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-210">For a full description of the fields in the export report, see [Export report fields](export-report-fields-in-advanced-ediscovery.md).</span></span>
  
## <a name="export-report-output-files"></a><span data-ttu-id="8ba2c-211">导出报告输出文件</span><span class="sxs-lookup"><span data-stu-id="8ba2c-211">Export report output files</span></span>
<span data-ttu-id="8ba2c-212"><a name="BK_ExportOutputFIles"> </a></span><span class="sxs-lookup"><span data-stu-id="8ba2c-212"></span></span>

<span data-ttu-id="8ba2c-213">下表列出了运行导出批次时生成的输出文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-213">The following table lists the output files that are generated when you run an Export batch.</span></span>
  
|<span data-ttu-id="8ba2c-214">**文件名**</span><span class="sxs-lookup"><span data-stu-id="8ba2c-214">**File name**</span></span>|<span data-ttu-id="8ba2c-215">**文件类型**</span><span class="sxs-lookup"><span data-stu-id="8ba2c-215">**File type**</span></span>|<span data-ttu-id="8ba2c-216">**说明**</span><span class="sxs-lookup"><span data-stu-id="8ba2c-216">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ba2c-217">导出摘要</span><span class="sxs-lookup"><span data-stu-id="8ba2c-217">Export summary</span></span>  <br/> |<span data-ttu-id="8ba2c-218">csv</span><span class="sxs-lookup"><span data-stu-id="8ba2c-218">csv</span></span>  <br/> |<span data-ttu-id="8ba2c-219">电子数据展示导出工具生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-219">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="8ba2c-220">跟踪</span><span class="sxs-lookup"><span data-stu-id="8ba2c-220">Trace</span></span>  <br/> |<span data-ttu-id="8ba2c-221">txt</span><span class="sxs-lookup"><span data-stu-id="8ba2c-221">txt</span></span>  <br/> |<span data-ttu-id="8ba2c-222">电子数据展示导出工具生成的日志文件。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-222">A log file generated by the eDiscovery Export Tool.</span></span>  <br/> |
|<span data-ttu-id="8ba2c-223">已提取的文本文件</span><span class="sxs-lookup"><span data-stu-id="8ba2c-223">Extracted text files</span></span>  <br/> |<span data-ttu-id="8ba2c-224">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="8ba2c-224">File folder</span></span>  <br/> |<span data-ttu-id="8ba2c-225">包含提取的文本文件的导出文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-225">Folder that contains the extracted text files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="8ba2c-226">输入或本机文件</span><span class="sxs-lookup"><span data-stu-id="8ba2c-226">Input or native files</span></span>  <br/> |<span data-ttu-id="8ba2c-227">文件文件夹</span><span class="sxs-lookup"><span data-stu-id="8ba2c-227">File folder</span></span>  <br/> |<span data-ttu-id="8ba2c-228">包含导出的文件的本机和输入文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-228">Folder that contains the native and input files of the exported files.</span></span>  <br/> |
|<span data-ttu-id="8ba2c-229">将列表导出</span><span class="sxs-lookup"><span data-stu-id="8ba2c-229">Export list</span></span>  <br/> |<span data-ttu-id="8ba2c-230">xlsx</span><span class="sxs-lookup"><span data-stu-id="8ba2c-230">xlsx</span></span>  <br/> |<span data-ttu-id="8ba2c-p122">Xlsx 格式的导出的文件元数据。根据模板用户选择要导出到文件中的字段。如果需要创建多个文件，每个包含 100-150 K 行。如果某个值包含字符数多于 Excel 单元格可包含 （当前限制为 32,767 个字符），则值将裁剪到允许的最大长度。修整一个值，如果单元格的背景颜色为红色以向用户指明这。"电子邮件参与者"是可能会超过了长度限制，字段的示例，如果向大型通讯组发送电子邮件。有关输出字段的详细信息，请参阅[导出报告字段](export-report-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p122">Exported files metadata in xlsx format. Fields in files are according to template user selects to export. If needed, several files are created, each contains 100-150K rows. If a certain value contains more characters than an Excel cell can contain (currently the limit is 32,767 characters), then the value will be trimmed to the maximum length allowed. If a value is trimmed, the cell's background color is red to indicate this to the user."Email participants" is an example of a field that can exceed the length limit, if the email was sent to a large distribution. See [Export report fields](export-report-fields-in-advanced-ediscovery.md) for details about the output fields.  </span></span><br/> |
|<span data-ttu-id="8ba2c-237">加载文件</span><span class="sxs-lookup"><span data-stu-id="8ba2c-237">Load file</span></span>  <br/> |<span data-ttu-id="8ba2c-238">csv</span><span class="sxs-lookup"><span data-stu-id="8ba2c-238">csv</span></span>  <br/> |<span data-ttu-id="8ba2c-p123">导出的文件中加载到不同的应用程序的 csv 文件格式的元数据。根据模板用户选择要导出到文件中的字段。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p123">Exported files metadata in csv format for loading into a different application. Fields in files are according to template user selects to export.</span></span>  <br/> |
|<span data-ttu-id="8ba2c-241">成功指标</span><span class="sxs-lookup"><span data-stu-id="8ba2c-241">Success indicator</span></span>  <br/> |<span data-ttu-id="8ba2c-242">txt</span><span class="sxs-lookup"><span data-stu-id="8ba2c-242">txt</span></span>  <br/> |<span data-ttu-id="8ba2c-p124">导出第三方 Azure blob 时，才创建。如果导出完全成功，将创建文件。发生故障，时或部分将不创建成功文件。将允许自动的跟踪不同导出批次/会话状态的根文件夹中创建文件。这是一个空的文件。其名称： TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。</span><span class="sxs-lookup"><span data-stu-id="8ba2c-p124">Only created when exporting to a 3rd party Azure blob. If export succeed completely, the file will be created. In case of failure, or partial success the file will not be created. File will be created in the root folder, allowing automated tracking on different Export batches/sessions statuses. This is an empty file. Its name is: TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8ba2c-249">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ba2c-249">See also</span></span>

[<span data-ttu-id="8ba2c-250">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="8ba2c-250">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8ba2c-251">查看批处理历史记录和导出过去的结果</span><span class="sxs-lookup"><span data-stu-id="8ba2c-251">Viewing batch history and exporting past results</span></span>](view-batch-history-and-export-past-results.md)
  
[<span data-ttu-id="8ba2c-252">Office 365 高级电子数据展示快速设置</span><span class="sxs-lookup"><span data-stu-id="8ba2c-252">Quick setup for Office 365 Advanced eDiscovery</span></span>](quick-setup-for-advanced-ediscovery.md)

[<span data-ttu-id="8ba2c-253">导出报告字段</span><span class="sxs-lookup"><span data-stu-id="8ba2c-253">Export report fields</span></span>](export-report-fields-in-advanced-ediscovery.md)
  
[<span data-ttu-id="8ba2c-254">从 Office 365 导出电子数据展示搜索结果时增加下载速度</span><span class="sxs-lookup"><span data-stu-id="8ba2c-254">Increase the download speed when exporting eDiscovery search results from Office 365</span></span>](increase-download-speeds-when-exporting-ediscovery-results.md)

