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
ms.openlocfilehash: 92ee107ad096393fbccbc9a3dbe81d8e7dd28da9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525996"
---
# <a name="export-results-in-office-365-advanced-ediscovery"></a>导出 Office 365 高级电子数据展示中的结果

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主题介绍了高级电子数据展示导出安装程序选项。
  
 **本主题内容：**
  
- [定义导出批次和会话](export-results-in-advanced-ediscovery.md#BK_Define)
    
- [增量和其他导出](export-results-in-advanced-ediscovery.md#BK_IncrementalReports)
    
- [设置批次导出参数](export-results-in-advanced-ediscovery.md#BK_SetUpExport)
    
- [导出报告输出文件](export-results-in-advanced-ediscovery.md#BK_ExportOutputFIles)
    
## <a name="defining-export-batches-and-sessions"></a>定义导出批次和会话
<a name="BK_Define"> </a>

导出批处理允许导出处理使用一组已定义的参数。高级电子数据展示可以定义自定义每次导出的批次。
  
每个导出批处理定义参数。默认情况下，将用例的第一个批处理创建名为"导出批处理 01"的批次。您还可以编辑的批处理名称和说明。
  
高级电子数据展示导出导出批内执行的导出会话。
  
## <a name="incremental-and-additional-exports"></a>增量和其他导出
<a name="BK_IncrementalReports"> </a>

您可以运行中的导出批次，以确保一致的结果基于同一导出模板和参数的多个导出会话。为批次中的每个会话，您可以导出分析的新处理案例数据和处理每个"增量。"
  
若要导出使用一组不同的参数，首先需要创建新的批次。新的批次中的第一个会话将产生的处理情况为止，已导入这些文件并将其处理通过一个或多个导入的文件的结果。每一批次重新计算数据透视表、 相似性、 inclusives 等。会话使用批处理定义的参数和数据透视表、 相似性、 inclusives 等每次会话执行不重新计算。
  
例如，假定种情况下已导入和分析其数据。若要检索近乎重复项和电子邮件超线程的增量数据的结果，请单击以前用来将数据导出的同一批次中的**创建导出会话**。 
  
## <a name="set-up-batch-export-parameters"></a>设置批次导出参数
<a name="BK_SetUpExport"> </a>

电子数据展示导出工具用于从高级电子数据展示的搜索结果导出到本地计算机。为了提高数据传输吞吐量和大的加速导出过程，您可以用于导出搜索结果的计算机上配置的 Windows 注册表设置。如果您想要提高下载速度，配置注册表设置之前您设置导出参数。有关详细信息，请参阅[增加下载速度导出电子数据展示搜索结果从 Office 365 时](increase-download-speeds-when-exporting-ediscovery-results.md)。
  
1. 高级电子数据展示中, 选择用例，单击**导出** \> **安装程序**。
    
  - 从**导出批处理**列表中，选择批处理名称或将结果导出到导出批处理 01、 （默认批次）。 
    
  - 若要导出结果的新文件添加到现有用例，继续使用您当前的批次。若要创建的批处理中的会话，请选择的相同的批次编号，单击**创建导出会话**可以使用此选项以增量方式为上一批次，导出相同的参数。 
    
  - 若要导出到新的批次，单击**添加**![图标添加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批处理名称**中输入新的名称 （或接受默认值） 以及在**说明批次**的说明。单击**确定**。
    
  - 若要编辑的批处理名称或说明，请选择中**导出批次**的名称，单击**编辑**![编辑图标](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然后修改字段。
    
    > [!NOTE]
    > 您已运行导出批次会话后，他们不能删除。此外，运行第一个会话后，即可进行编辑只有一些参数。 
  
  - 若要创建的重复导出批次，请选择**重复导出批处理**![创建重复导出批处理图标](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)在面板中输入名称和重复批次的说明。 
    
  - 若要删除的导出批次，选择**删除**![删除导出批处理图标](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。
    
  - 若要查看的批次的历史记录，请选择**批处理历史记录**![查看历史记录图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。
    
2. 在**总体**，选择**仅包括文件相关性截止分数上方**和/或**优化导出批次**，如果您想要调整您导出批次的设置。 
    
3. 如果您选择**包括仅上方相关性截止分数的文件**，则启用**问题**。如果该文件的相关性分数大于所选问题的截止分数，除非它进行审阅筛选器排除将导出文件。 
  
如果您选择**优化导出批次**，**消除**和筛选器审阅通过域单选按钮处于启用状态。如果您选择**消除**，然后将根据定义的策略筛选出重复文件 [Case 级别 （默认值）： 从每个组重复文件在整个的情况下，所有而不是一个文件将重复消除。Custodian 级别： 所有而不是一个文件将从每个组的相同 custodian 重复文件，重复消除。]导出输出中包含的所有重复的文件的记录。如果您选择**筛选器的查看**字段中，选择**修改下元数据**输入**供审阅**字段设置。选择**包含输入的文件**要包含在包内容中的源代码文件。您可以清除此设置可加快导出过程。请注意，将在任何情况下导出的本机文件。 
    
4. 在**元数据**，下从 （每次会话） 的**导出模板**列表中的以下选项中进行选择。 
    
  - **标准**： 套基本的数据项目、 元数据，而将属性。高级电子数据展示中已处理数据导入和导出数据上载到系统已包含的文件时，请使用此选项。默认情况下，导出模板列创建和填充。
    
  - **所有**： 整套标准元数据，包括所有处理数据，以及分析和相关性分数。此模板时需要高级电子数据展示执行处理和文件数据上载到外部系统的第一次。
    
  - **问题**： 选择**所有问题**，或者都选择您已创建的特定问题。 
    
5. 在**目标**:
    
  - **下载到本地计算机**
    
  - **导出到用户定义的 Azure blob**： 如果选中此选项，则可以指定容器 URL 和 SAS 令牌。
    
    > [!NOTE]
    > 一旦导出包存储到用户定义的 Azure blob、 高级电子数据展示; 不再管理的数据它被管理 Azure 的 blob。这意味着，如果您删除这种情况，导出的文件仍将保留在 Azure blob 上。 
  
  - **保存 SAS 将来导出会话令牌**： 如果选中，都将被 SAS 令牌加密以供将来使用高级电子数据展示的内部数据库中。
    
    > [!NOTE]
    > 当前该 SA 令牌有效期一个月。如果您尝试在您需要撤消最后一个会话超过一个月后下载，然后再次导出。 
  
6. 单击**修改**设置"审阅字段设置。 
    
> ![为导出批次查看字段 seetings 设置](media/39451aba-f6fe-4a01-8ed0-0be6a6ce889a.png)
  
    In **For review field settings** panel, in **Select scenario**, select the scenario and scope of the review. The settings are displayed based on your selection.
    
    **Review all** (default): All emails, attachments, and documents are selected by default. 
    
    **Review all unique content in a set**: Inclusives and unique inclusive copies, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content in a set - no inclusive copies**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates.
    
    **Review all unique content and related family files**: Inclusives, unique attachments in email set level, representative from every set of exact duplicates, expand to include family files.
    
    **Custom** (allows you to define the options in the dialog): The default is to keep current selections and enable all dialog options, to allow their selection. 
    
    If you select custom, you can then customize the settings for emails, documents, attachments and miscellaneous.
    
> 在**电子邮件**中选择要导出的电子邮件： 
    
    **All emails**: (default) All emails are selected.
    
    **Inclusives**: An inclusive email is a last email of a thread, and it contains all the other emails from the thread.
    
    **Inclusives and unique inclusive copies**: Inclusive copies and inclusives with the same subject, body and attachments; unique inclusive copies are unique copies of these emails .
    
> 在**文档**中选择要导出的文档： 
    
    **All documents**: (default) All documents are selected.
    
    **Pivots**: A file chosen as representative of near-duplicates set, which is typically used as the baseline when reviewing the set.
    
    **Representative from every set of exact duplicates**: Unique near-duplicate files (including the pivot).
    
> **附件**中选择要导出的附件 
    
    **All attachments**: (default) All attachments are selected.
    
    **Unique attachment in case level**: Unique attachment files within the specified case.
    
    **Unique attachment in email set level**: Unique attachment files within the specified email case.
    
> 在**Micellaneous**可以**将文档作为附件**、**将文档作为电子邮件**，或**展开，包括家庭文件**中进行选择。当您选择**扩展以包含系列文件**，供审阅标记每个文件时，将同时也标记同一系列的所有文件。
    
    Choose **Save** to save the settings. 
    
7. 指定导出参数后，若要开始导出批次单击**创建导出会话**。
    
    导出期间，将状态显示在**任务状态**。在**导出摘要**显示结果。
    
8. 在**文件下载**窗口中，单击**复制到剪贴板**复制导出密钥。 
    
    ![下载文件](media/99cf2c13-4954-479f-9741-80d7458c1a15.png)
  
9. 单击“关闭”****。 
    
    启动电子数据展示导出工具。
    
    ![电子数据展示导出工具](media/705756ca-ee97-4d24-b70f-8b23513f6d11.gif)
  
10. 在**电子数据展示导出工具**：
    
1. 在**粘贴将用于连接到源的共享访问签名**，导出密钥该 youcopied 到剪贴板中粘贴步骤 7。
    
2. 单击**浏览**，选择用于存储在本地计算机上下载的导出文件的目标位置。 
    
11. 单击**启动**。导出文件下载到本地计算机。如果您在步骤 4 中选择**导出到用户定义的 Azure blob** ，会话将导出到您选择的 Blob 存储 URL 目标。 
    
导出报告中的字段的完整说明，请参阅[导出报表字段](export-report-fields-in-advanced-ediscovery.md)。
  
## <a name="export-report-output-files"></a>导出报告输出文件
<a name="BK_ExportOutputFIles"> </a>

下表列出了运行导出批次时生成的输出文件。
  
|**文件名**|**文件类型**|**说明**|
|:-----|:-----|:-----|
|导出摘要  <br/> |csv  <br/> |电子数据展示导出工具生成的日志文件。  <br/> |
|跟踪  <br/> |txt  <br/> |电子数据展示导出工具生成的日志文件。  <br/> |
|已提取的文本文件  <br/> |文件文件夹  <br/> |包含提取的文本文件的导出文件的文件夹。  <br/> |
|输入或本机文件  <br/> |文件文件夹  <br/> |包含导出的文件的本机和输入文件的文件夹。  <br/> |
|将列表导出  <br/> |xlsx  <br/> |Xlsx 格式的导出的文件元数据。根据模板用户选择要导出到文件中的字段。如果需要创建多个文件，每个包含 100-150 K 行。如果某个值包含字符数多于 Excel 单元格可包含 （当前限制为 32,767 个字符），则值将裁剪到允许的最大长度。修整一个值，如果单元格的背景颜色为红色以向用户指明这。"电子邮件参与者"是可能会超过了长度限制，字段的示例，如果向大型通讯组发送电子邮件。有关输出字段的详细信息，请参阅[导出报告字段](export-report-fields-in-advanced-ediscovery.md)。<br/> |
|加载文件  <br/> |csv  <br/> |导出的文件中加载到不同的应用程序的 csv 文件格式的元数据。根据模板用户选择要导出到文件中的字段。  <br/> |
|成功指标  <br/> |txt  <br/> |导出第三方 Azure blob 时，才创建。如果导出完全成功，将创建文件。发生故障，时或部分将不创建成功文件。将允许自动的跟踪不同导出批次/会话状态的根文件夹中创建文件。这是一个空的文件。其名称： TenantId_CaseId_ExternalCaseId_CaseName_ExportBatchId_SessionId_DateTime.txt。  <br/> |
   
## <a name="see-also"></a>另请参阅
<a name="BK_ExportOutputFIles"> </a>

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
  
[Office 365 高级电子数据展示快速设置](quick-setup-for-advanced-ediscovery.md)

[导出报表字段](export-report-fields-in-advanced-ediscovery.md)
  
[从 Office 365 导出电子数据展示搜索结果时增加下载速度](increase-download-speeds-when-exporting-ediscovery-results.md)

