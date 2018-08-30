---
title: 导出 Office 365 高级电子数据展示中的报告字段
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 介绍了高级电子数据展示的导出报告中包含的所有字段。
ms.openlocfilehash: a578523098248bcfa16ea8ba97d756d97ba060fa
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525091"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>导出 Office 365 高级电子数据展示中的报告字段

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主题介绍标准和所有模板的高级电子数据展示导出报告字段。
  
## <a name="export-report-fields"></a>导出报表字段

下表列出了每个导出模板的字段。
  
|**导出字段名称**|**组**|**说明**|**在标准的模板中可用**|**在所有模板中可用**|
|:-----|:-----|:-----|:-----|:-----|
|方式  <br/> |概要  <br/> |行号。  <br/> |是  <br/> |是  <br/> |
|File_ID  <br/> |概要  <br/> |文件 id。  <br/> |是  <br/> |是  <br/> |
|File_class  <br/> |处理  <br/> |文件类。  <br/> |是  <br/> |是  <br/> |
|Family_ID  <br/> |处理  <br/> |用于分组文件 （通常电子邮件实例和附件） 的数字标识符。  <br/> |是  <br/> |是  <br/> |
|For_review  <br/> |处理  <br/> |用于指示将供审阅的导出中包含的字段的标志。  <br/> |是  <br/> |是  <br/> |
|Native_file_name  <br/> |处理  <br/> |本机文件名称，而不引用文件夹和分机号。  <br/> |是  <br/> |是  <br/> |
|管理员  <br/> |概要  <br/> |该文件的管理员。  <br/> |是  <br/> |是  <br/> |
|Set_ID  <br/> |分析  <br/> |"和设置"或者"电子邮件设置"的 id。  <br/> |是  <br/> |是  <br/> |
|Inclusive_type  <br/> |电子邮件  <br/> |根据以下值指示是否包含文件： 0-不含，1-非独占，2-非独占减去，3-非独占的副本。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pivot  <br/> |Near 重复项  <br/> |指示该文件是透视。  <br/> |是  <br/> |是  <br/> |
|Similarity_percent  <br/> |Near 重复项  <br/> |相对于数据透视表的相似性的百分比。  <br/> |是  <br/> |是  <br/> |
|Duplicate_subset  <br/> |Near 重复项  <br/> |重复的子集的唯一标识符。指示文件是否有准确无误重复项。  <br/> |是  <br/> |是  <br/> |
|日期  <br/> |概要  <br/> |文件的日期 (取决于文件类型的电子邮件： 发送日期; 文档： 修改日期)。  <br/> |是  <br/> |是  <br/> |
|Dominant_theme  <br/> |分析  <br/> |文件的主要主题。  <br/> |是  <br/> |是  <br/> |
|Themes_list  <br/> |主题  <br/> |主题名称的列表。  <br/> |是  <br/> |是  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate 组的唯一数字标识符。  <br/> |是  <br/> |是  <br/> |
|Email_set  <br/> |电子邮件  <br/> |设置电子邮件的唯一数字标识符。  <br/> |是  <br/> |是  <br/> |
|Email_thread  <br/> |电子邮件  <br/> |描述该位置的电子邮件中的电子邮件设置从根的所有节点 Id-包含为当前电子邮件、 句点隔开。  <br/> |是  <br/> |是  <br/> |
|Email_subject  <br/> |电子邮件  <br/> |电子邮件的主题。  <br/> |是  <br/> |是  <br/> |
|Email_date_sent  <br/> |电子邮件  <br/> |已发送电子邮件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_participants  <br/> |电子邮件  <br/> |在电子邮件线程，包括缺失的链接中的所有参与者的电子邮件地址。  <br/> |是  <br/> |是  <br/> |
|Email_participant_domains  <br/> |电子邮件  <br/> |在电子邮件线程，包括缺少链接中的所有参与者的域。  <br/> |是  <br/> |是  <br/> |
|Email_sender  <br/> |电子邮件  <br/> |电子邮件发件人姓名和/或地址。  <br/> |是  <br/> |是  <br/> |
|Email_sender_domain  <br/> |电子邮件  <br/> |电子邮件发件人的域。  <br/> |是  <br/> |是  <br/> |
|Email_to  <br/> |电子邮件  <br/> |给电子邮件的收件人。  <br/> |是  <br/> |是  <br/> |
|Email_cc  <br/> |电子邮件  <br/> |抄送收件人的电子邮件。  <br/> |是  <br/> |是  <br/> |
|Email_bcc  <br/> |电子邮件  <br/> |电子邮件的密件抄送收件人。  <br/> |是  <br/> |是  <br/> |
|Email_recipient_domains  <br/> |电子邮件  <br/> |电子邮件收件人 (To、 抄送和密件抄送） 的域。  <br/> |是  <br/> |是  <br/> |
|Email_date_received  <br/> |电子邮件  <br/> |在其接收电子邮件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_action  <br/> |电子邮件  <br/> |值： 根据电子邮件主题:"转接"(用于"FW:")，"答复"(用于"RE:") 或"其他"（其他使用者文本）。  <br/> |是  <br/> |是  <br/> |
|Meeting_Start_Date/时间  <br/> ||日期和开始会议项目时间。  <br/> |是  <br/> |是  <br/> |
|Meeting_End_Date/时间  <br/> ||日期和结束会议项目时间。  <br/> |是  <br/> |是  <br/> |
|File_relevance_score  <br/> |相关性  <br/> |相关性分数 (0-100)。每个问题。  <br/> |是  <br/> |是  <br/> |
|Family_relevance_score  <br/> |相关性  <br/> |最大系列相关性分数 (0-100)。每个问题。  <br/> |是  <br/> |是  <br/> |
|Relevance_tag  <br/> |相关性  <br/> |标记的文件，如果该文件已手动标记中相关性。每个问题。  <br/> |是  <br/> |是  <br/> |
|Relevance_load_group  <br/> |相关性  <br/> |相关性负载组中，指定的文件，每个问题的域。  <br/> |是  <br/> |是  <br/> |
|Normalized_relevance_score  <br/> |相关性  <br/> |规范化的相关性分数 (0-100)，这是相当问题和加载之间。  <br/> |是  <br/> |是  <br/> |
|Marked_as_seed  <br/> |相关性  <br/> |标记的文件，如果它已设置可为每个相关性问题/类别中的种子文件。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pre 标记  <br/> |相关性  <br/> |标记的文件，如果已设置为每个相关性问题/类别中前标记。  <br/> |是  <br/> |是  <br/> |
|Relevance_status_description  <br/> |相关性  <br/> |相关性状态的说明。  <br/> |是  <br/> |是  <br/> |
|注释  <br/> |概要  <br/> |将用户输入的注释。  <br/> |是  <br/> |是  <br/> |
|Export_input_path  <br/> |处理  <br/> |导出输入的路径。  <br/> |是  <br/> |是  <br/> |
|Pivot_ID  <br/> |Near 重复项  <br/> |数据透视表的文件的 ID。  <br/> |是  <br/> |是  <br/> |
|Family_size  <br/> |处理  <br/> |系列中的文件数。  <br/> |是  <br/> |是  <br/> |
|Native_type  <br/> |处理  <br/> |本机文件类型。例如，电子表格或演示文稿。  <br/> |是  <br/> |是  <br/> |
|Native_MD5  <br/> |处理  <br/> |本机文件 MD5 哈希值。  <br/> |是  <br/> |是  <br/> |
|Native_size  <br/> |处理  <br/> |本机文件大小。  <br/> |是  <br/> |是  <br/> |
|Native_extension  <br/> |处理  <br/> |本机文件扩展名。  <br/> |是  <br/> |是  <br/> |
|Doc_date_modified  <br/> |文档属性  <br/> |本机文件的修改，取自文件的元数据的日期。  <br/> |是  <br/> |是  <br/> |
|Doc_date_created  <br/> |文档属性  <br/> |日期本机创建文件时，取自文件的元数据。  <br/> |是  <br/> |是  <br/> |
|Doc_modified_by  <br/> |文档属性  <br/> |修改摘自该文件的元数据的本机文件的用户。  <br/> |是  <br/> |是  <br/> |
|O365_date_modified  <br/> |文档属性  <br/> |日期本机文件进行了修改，取自 SharePoint 或 Exchange 字段。  <br/> |是  <br/> |是  <br/> |
|O365_date_created  <br/> |文档属性  <br/> |创建日期本机文件，取自 SharePoint 或 Exchange 的字段。  <br/> |是  <br/> |是  <br/> |
|O365_modified_by  <br/> |文档属性  <br/> |上次修改用户从 SharePoint 或 Exchange 字段所需的本机文件。  <br/> |是  <br/> |是  <br/> |
|Compound_path  <br/> |处理  <br/> |包括其复合源的本机文件路径。  <br/> |是  <br/> |是  <br/> |
|Input_path  <br/> |处理  <br/> |输入文件的路径。  <br/> |是  <br/> |是  <br/> |
|Input_date_modified  <br/> |处理  <br/> |上次修改日期输入文件。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |串联电子邮件设置并为查看和设置。具有同时和组，以及 E 前缀添加到电子邮件 ssets 添加。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |串联电子邮件设置和供审阅设置将同时添加到和集和 E 前缀添加到电子邮件设置。此外，每个电子邮件中 Email_set 后跟及其相应的附件。  <br/> |是  <br/> |是  <br/> |
|Deduped_custodians  <br/> |概要  <br/> |重复消除文件的管理员  <br/> |是  <br/> |是  <br/> |
|Deduped_file_IDs  <br/> |概要  <br/> |重复消除文件的 Id  <br/> |是  <br/> |是  <br/> |
|Deduped_paths  <br/> |概要  <br/> |重复消除文件的路径  <br/> |是  <br/> |是  <br/> |
|File_key  <br/> |概要  <br/> |以供将来使用的内部标识符。  <br/> |是  <br/> |是  <br/> |
|Export_native_path  <br/> |处理  <br/> |导出包中的本机文件的路径。  <br/> |是  <br/> |是  <br/> |
|Extracted_text_path  <br/> |处理  <br/> |提取文件的路径。  <br/> |是  <br/> |是  <br/> |
|Process_batch  <br/> |处理  <br/> |导入批次的批处理标识符。  <br/> |是  <br/> |是  <br/> |
|Process_status_ID  <br/> |处理  <br/> |表示进程阶段状态的标识符。  <br/> |是  <br/> |是  <br/> |
|Process_status_description  <br/> |处理  <br/> |处理阶段状态说明： 成功或错误说明。  <br/> |是  <br/> |是  <br/> |
|Export_status_ID  <br/> |处理  <br/> |导出状态的 ID。  <br/> |是  <br/> |是  <br/> |
|Export_status_description  <br/> |处理  <br/> |导出状态; 的说明成功或错误说明。  <br/> |是  <br/> |是  <br/> |
|Read_percent  <br/> |相关性  <br/> |阅读 %(0-100)。每个问题。  <br/> |是  <br/> |是  <br/> |
|Doc_author  <br/> |文档属性  <br/> |文档属性： 作者。  <br/> |否  <br/> |是  <br/> |
|Doc_comments  <br/> |文档属性  <br/> |文档属性： 注释。  <br/> |否  <br/> |是  <br/> |
|Doc_keywords  <br/> |文档属性  <br/> |文档属性： 关键字。  <br/> |否  <br/> |是  <br/> |
|Doc_last_saved_by  <br/> |文档属性  <br/> |文档属性： 上次保存的。  <br/> |否  <br/> |是  <br/> |
|Doc_revision  <br/> |文档属性  <br/> |文档属性： 修订号。  <br/> |否  <br/> |是  <br/> |
|Doc_subject  <br/> |文档属性  <br/> |文档属性： 主题。  <br/> |否  <br/> |是  <br/> |
|Doc_template  <br/> |文档属性  <br/> |文档属性： 模板。  <br/> |否  <br/> |是  <br/> |
|Doc_title  <br/> |文档属性  <br/> |文档属性： title。  <br/> |否  <br/> |是  <br/> |
|Email_has_attachment  <br/> |电子邮件  <br/> |指示此电子邮件是否具有一个或多个附件。  <br/> |否  <br/> |是  <br/> |
|Email_importance  <br/> |电子邮件  <br/> |Importance 属性的电子邮件。  <br/> |否  <br/> |是  <br/> |
|Email_level  <br/> |电子邮件  <br/> |指示的电子邮件主题中的电子邮件的级别。对于附件，附加的电子邮件的值。  <br/> |否  <br/> |是  <br/> |
|Email_recipients  <br/> |电子邮件  <br/> |名称和/或地址 （收件人、 抄送和密件抄送） 电子邮件收件人。  <br/> |否  <br/> |是  <br/> |
|Email_security  <br/> |电子邮件  <br/> |电子邮件安全属性。  <br/> |否  <br/> |是  <br/> |
|Email_sensitivity  <br/> |电子邮件  <br/> |电子邮件 sensitivity 属性。  <br/> |否  <br/> |是  <br/> |
|Export_batch  <br/> |处理  <br/> |文件的上次导出批处理名称。  <br/> |否  <br/> |是  <br/> |
|Export_session  <br/> |处理  <br/> |文件的上次导出会话 Id 包括日期。  <br/> |否  <br/> |是  <br/> |
|Extracted_text_length  <br/> |处理  <br/> |提取文本文件的字符长度。  <br/> |否  <br/> |是  <br/> |
|Family_duplicate_set  <br/> |处理  <br/> |系列准确无误重复的每个其他的数字标识符 （分别-系列的所有成员都都完全重复）。  <br/> |否  <br/> |是  <br/> |
|Has_Text  <br/> |处理  <br/> |指示是否有文本在文件： 0-无;1-是。  <br/> |否  <br/> |是  <br/> |
|Input_file_ID  <br/> |处理  <br/> |从从中提取文件的输入文件的 ID。  <br/> |否  <br/> |是  <br/> |
|Native_SHA_256  <br/> |处理  <br/> |本机文件 160、SHA 256 哈希值。  <br/> |否  <br/> |是  <br/> |
|O365_authors  <br/> |文档属性  <br/> |修改本机文件中，从 SharePoint 或 Exchange 字段所需的用户。  <br/> |否  <br/> |是  <br/> |
|O365_created_by  <br/> |文档属性  <br/> |创建本机文件后，从 SharePoint 或 Exchange 字段所需的用户。  <br/> |否  <br/> |是  <br/> |
|Parent_node  <br/> |电子邮件  <br/> |与不是缺少链接的最接近的父节点的电子邮件主题中的节点。  <br/> |否  <br/> |是  <br/> |
|Set_order_inclusives_first  <br/> |电子邮件  <br/> |电子邮件和附件： 计数器时间顺序 (Inclusives 第一个)。文档： 透视第一个和 rest 按相似性分数，降序。  <br/> |否  <br/> |是  <br/> |
|Tagged_By  <br/> |相关性  <br/> |针对特定问题中相关性标记文件的用户。  <br/> |否  <br/> |是  <br/> |
|Word_count  <br/> |分析  <br/> |在文档中的单词数。  <br/> |否  <br/> |是  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>相关主题

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[导出使用高级电子数据展示事例数据](export-case-data-in-advanced-ediscovery.md)
  
[导出结果](export-results-in-advanced-ediscovery.md)
  
[查看批处理历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
  

