---
title: 在 Office 365 高级电子数据展示中导出报告字段
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 840a5aff-ecd0-4e56-ad22-fe99bc143687
description: 介绍了用于高级电子数据展示的导出报告中包含的所有字段。
ms.openlocfilehash: 3e73cc1c106dfa98bd35f84c352fc89d0e45b74d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154462"
---
# <a name="export-report-fields-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中导出报告字段

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主题介绍了 "标准" 和 "所有" 模板的高级电子数据展示导出报告字段。
  
## <a name="export-report-fields"></a>导出报告字段

下表列出了每个导出模板的字段。
  
|**导出字段名称**|**Group**|**说明**|**在标准模板中可用**|**在所有模板中可用**|
|:-----|:-----|:-----|:-----|:-----|
|Row_number  <br/> |常规  <br/> |行号。  <br/> |是  <br/> |是  <br/> |
|File_ID  <br/> |常规  <br/> |文件 ID。  <br/> |是  <br/> |是  <br/> |
|File_class  <br/> |正在处理  <br/> |File 类。  <br/> |是  <br/> |是  <br/> |
|Family_ID  <br/> |正在处理  <br/> |用于对文件进行分组的数值标识符 (通常为电子邮件实例及其附件)。  <br/> |是  <br/> |是  <br/> |
|For_review  <br/> |正在处理  <br/> |指示将包含在 "导出以供审阅" 中的字段的标志。  <br/> |是  <br/> |是  <br/> |
|Native_file_name  <br/> |正在处理  <br/> |本机文件名, 不引用文件夹和扩展。  <br/> |是  <br/> |是  <br/> |
|保管人  <br/> |常规  <br/> |文件的管理员。  <br/> |是  <br/> |是  <br/> |
|Set_ID  <br/> |分析  <br/> |"ND set" 或 "Email set" id。  <br/> |是  <br/> |是  <br/> |
|Inclusive_type  <br/> |电子邮件  <br/> |根据以下值指示文件是否包含在内: 0-非包含、1个包含项、2个包含项的减号、3个包含副本。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pivot  <br/> |临近重复项  <br/> |指示文件是否为透视。  <br/> |是  <br/> |是  <br/> |
|Similarity_percent  <br/> |临近重复项  <br/> |相对于数据透视的相似性百分比。  <br/> |是  <br/> |是  <br/> |
|Duplicate_subset  <br/> |临近重复项  <br/> |重复子集的唯一标识符。 指示文件是否有精确的文本重复。  <br/> |是  <br/> |是  <br/> |
|日期  <br/> |常规  <br/> |文件日期 (取决于文件类型-电子邮件: 发送日期; 文档: 修改日期)。  <br/> |是  <br/> |是  <br/> |
|Dominant_theme  <br/> |分析  <br/> |文件的主要主题。  <br/> |是  <br/> |是  <br/> |
|Themes_list  <br/> |主题  <br/> |主题名称的列表。  <br/> |是  <br/> |是  <br/> |
|ND_set  <br/> |EquiSet  <br/> |Nearduplicate 集的唯一数字标识符。  <br/> |是  <br/> |是  <br/> |
|Email_set  <br/> |电子邮件  <br/> |电子邮件集的唯一数字标识符。  <br/> |是  <br/> |是  <br/> |
|Email_thread  <br/> |电子邮件  <br/> |描述电子邮件集中的电子邮件的位置由从根节点到当前电子邮件的所有节点 Id 组成, 以句点分隔。  <br/> |是  <br/> |是  <br/> |
|Email_subject  <br/> |电子邮件  <br/> |电子邮件的主题。  <br/> |是  <br/> |是  <br/> |
|Email_date_sent  <br/> |电子邮件  <br/> |发送电子邮件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_participants  <br/> |电子邮件  <br/> |电子邮件线索中所有参与者的电子邮件地址, 包括缺少的链接。  <br/> |是  <br/> |是  <br/> |
|Email_participant_domains  <br/> |电子邮件  <br/> |电子邮件线程中所有参与者的域, 包括缺少的链接。  <br/> |是  <br/> |是  <br/> |
|Email_sender  <br/> |电子邮件  <br/> |电子邮件发件人姓名和/或地址。  <br/> |是  <br/> |是  <br/> |
|Email_sender_domain  <br/> |电子邮件  <br/> |电子邮件发件人的域。  <br/> |是  <br/> |是  <br/> |
|Email_to  <br/> |电子邮件  <br/> |电子邮件的收件人。  <br/> |是  <br/> |是  <br/> |
|Email_cc  <br/> |电子邮件  <br/> |电子邮件的 "抄送" 收件人。  <br/> |是  <br/> |是  <br/> |
|Email_bcc  <br/> |电子邮件  <br/> |电子邮件的密件抄送收件人。  <br/> |是  <br/> |是  <br/> |
|Email_recipient_domains  <br/> |电子邮件  <br/> |电子邮件收件人域 ("收件人"、"抄送" 和 "密件抄送")。  <br/> |是  <br/> |是  <br/> |
|Email_date_received  <br/> |电子邮件  <br/> |接收电子邮件的日期。  <br/> |是  <br/> |是  <br/> |
|Email_action  <br/> |电子邮件  <br/> |值: 根据电子邮件主题: "转发" (针对 "FW:")、"答复" (对于 "RE:") 或 "其他" (其他主题文本)。  <br/> |是  <br/> |是  <br/> |
|Meeting_Start_Date/时间  <br/> ||会议项目的开始日期和时间。  <br/> |是  <br/> |是  <br/> |
|Meeting_End_Date/时间  <br/> ||会议项目结束的日期和时间。  <br/> |是  <br/> |是  <br/> |
|File_relevance_score  <br/> |相关性  <br/> |相关性分数 (0-100)。 每个问题。  <br/> |是  <br/> |是  <br/> |
|Family_relevance_score  <br/> |相关性  <br/> |最大族相关性分数 (0-100)。 每个问题。  <br/> |是  <br/> |是  <br/> |
|Relevance_tag  <br/> |相关性  <br/> |文件的标记, 如果文件是手动标记的相关。 每个问题。  <br/> |是  <br/> |是  <br/> |
|Relevance_load_group  <br/> |相关性  <br/> |指定文件的相关性负载组, 每个问题包含一个字段。  <br/> |是  <br/> |是  <br/> |
|Normalized_relevance_score  <br/> |相关性  <br/> |标准化的相关性分数 (0-100), 可在问题和负载之间进行比较。  <br/> |是  <br/> |是  <br/> |
|Marked_as_seed  <br/> |相关性  <br/> |文件的标记, 如果它在每个问题/类别的相关性中设置为 "种子文件"。  <br/> |是  <br/> |是  <br/> |
|Marked_as_pre-标记  <br/> |相关性  <br/> |文件的标记, 如果它在每个问题/类别的相关性设置为预先标记。  <br/> |是  <br/> |是  <br/> |
|Relevance_status_description  <br/> |相关性  <br/> |相关性状态的说明。  <br/> |是  <br/> |是  <br/> |
|Comment  <br/> |常规  <br/> |用户输入的注释。  <br/> |是  <br/> |是  <br/> |
|Export_input_path  <br/> |正在处理  <br/> |导出输入路径。  <br/> |是  <br/> |是  <br/> |
|Pivot_ID  <br/> |临近重复项  <br/> |文件的数据透视 ID。  <br/> |是  <br/> |是  <br/> |
|Family_size  <br/> |正在处理  <br/> |系列中的文件数。  <br/> |是  <br/> |是  <br/> |
|Native_type  <br/> |正在处理  <br/> |本机文件类型。 例如, 电子表格或演示文稿。  <br/> |是  <br/> |是  <br/> |
|Native_MD5  <br/> |正在处理  <br/> |本地文件的 MD5 哈希值。  <br/> |是  <br/> |是  <br/> |
|Native_size  <br/> |正在处理  <br/> |本机文件大小。  <br/> |是  <br/> |是  <br/> |
|Native_extension  <br/> |正在处理  <br/> |本机文件扩展名。  <br/> |是  <br/> |是  <br/> |
|Doc_date_modified  <br/> |文档属性  <br/> |修改了原生文件的日期, 从文件的元数据中获取。  <br/> |是  <br/> |是  <br/> |
|Doc_date_created  <br/> |文档属性  <br/> |创建本机文件的日期, 从文件的元数据中获取。  <br/> |是  <br/> |是  <br/> |
|Doc_modified_by  <br/> |文档属性  <br/> |修改了本机文件的用户, 该用户是从文件的元数据中获取的。  <br/> |是  <br/> |是  <br/> |
|O365_date_modified  <br/> |文档属性  <br/> |修改了本地原文件的日期 (从 SharePoint 或 Exchange 字段中获取)。  <br/> |是  <br/> |是  <br/> |
|O365_date_created  <br/> |文档属性  <br/> |创建本机文件的日期, 从 SharePoint 或 Exchange 字段中获取。  <br/> |是  <br/> |是  <br/> |
|O365_modified_by  <br/> |文档属性  <br/> |上次修改了本地文件 (从 SharePoint 或 Exchange 字段中获取) 的用户。  <br/> |是  <br/> |是  <br/> |
|Compound_path  <br/> |正在处理  <br/> |包含其复合源的本地文件路径。  <br/> |是  <br/> |是  <br/> |
|Input_path  <br/> |正在处理  <br/> |输入文件的路径。  <br/> |是  <br/> |是  <br/> |
|Input_date_modified  <br/> |正在处理  <br/> |上次修改日期输入文件。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_excl_attach  <br/> |分析  <br/> |将电子邮件集和 ND 的串联设置为审阅。 ' D ' 作为 ND 集的前缀添加, 而 ' E ' 已添加到电子邮件 ssets 中。  <br/> |是  <br/> |是  <br/> |
|ND_ET_sort_incl_attach  <br/> |分析  <br/> |将电子邮件集和设置为审阅的 ND 的串联添加为 ND 集的前缀, 并将 "E" 添加到电子邮件集。 此外, Email_set 中的每封电子邮件后面都有相应的附件。  <br/> |是  <br/> |是  <br/> |
|Deduped_custodians  <br/> |常规  <br/> |Duped 文件的保管人  <br/> |是  <br/> |是  <br/> |
|Deduped_file_IDs  <br/> |常规  <br/> |Duped 文件的 Id  <br/> |是  <br/> |是  <br/> |
|Deduped_paths  <br/> |常规  <br/> |Duped 文件的路径  <br/> |是  <br/> |是  <br/> |
|File_key  <br/> |常规  <br/> |内部标识符以供将来使用。  <br/> |是  <br/> |是  <br/> |
|Export_native_path  <br/> |正在处理  <br/> |导出包中的本机文件的路径。  <br/> |是  <br/> |是  <br/> |
|Extracted_text_path  <br/> |正在处理  <br/> |提取的文件的路径。  <br/> |是  <br/> |是  <br/> |
|Process_batch  <br/> |正在处理  <br/> |导入批次的批处理标识符。  <br/> |是  <br/> |是  <br/> |
|Process_status_ID  <br/> |正在处理  <br/> |表示进程阶段状态的标识符。  <br/> |是  <br/> |是  <br/> |
|Process_status_description  <br/> |正在处理  <br/> |过程阶段状态描述: 成功或错误说明。  <br/> |是  <br/> |是  <br/> |
|Export_status_ID  <br/> |正在处理  <br/> |导出状态的 ID。  <br/> |是  <br/> |是  <br/> |
|Export_status_description  <br/> |正在处理  <br/> |导出状态的说明;成功或错误说明。  <br/> |是  <br/> |是  <br/> |
|Read_percent  <br/> |相关性  <br/> |读% (0-100)。 每个问题。  <br/> |是  <br/> |是  <br/> |
|Doc_author  <br/> |文档属性  <br/> |文档属性: 作者。  <br/> |否  <br/> |可访问  <br/> |
|Doc_comments  <br/> |文档属性  <br/> |文档属性: 注释。  <br/> |否  <br/> |可访问  <br/> |
|Doc_keywords  <br/> |文档属性  <br/> |文档属性: 关键字。  <br/> |否  <br/> |可访问  <br/> |
|Doc_last_saved_by  <br/> |文档属性  <br/> |文档属性: 上次保存者。  <br/> |否  <br/> |可访问  <br/> |
|Doc_revision  <br/> |文档属性  <br/> |文档属性: 修订号。  <br/> |否  <br/> |可访问  <br/> |
|Doc_subject  <br/> |文档属性  <br/> |文档属性: subject。  <br/> |否  <br/> |是  <br/> |
|Doc_template  <br/> |文档属性  <br/> |文档属性: 模板。  <br/> |否  <br/> |是  <br/> |
|Doc_title  <br/> |文档属性  <br/> |文档属性: title。  <br/> |否  <br/> |是  <br/> |
|Email_has_attachment  <br/> |电子邮件  <br/> |指示电子邮件是否有一个或多个附件。  <br/> |否  <br/> |是  <br/> |
|Email_importance  <br/> |电子邮件  <br/> |电子邮件重要性属性。  <br/> |否  <br/> |是  <br/> |
|Email_level  <br/> |电子邮件  <br/> |指示电子邮件在电子邮件线索中的级别。 对于附件, 是附加电子邮件的值。  <br/> |否  <br/> |是  <br/> |
|Email_recipients  <br/> |电子邮件  <br/> |电子邮件收件人的名称和/或地址 (收件人、抄送和密件抄送)。  <br/> |否  <br/> |是  <br/> |
|Email_security  <br/> |电子邮件  <br/> |电子邮件安全属性。  <br/> |否  <br/> |是  <br/> |
|Email_sensitivity  <br/> |电子邮件  <br/> |电子邮件敏感度属性。  <br/> |否  <br/> |是  <br/> |
|Export_batch  <br/> |正在处理  <br/> |文件的上次导出批处理名称。  <br/> |否  <br/> |是  <br/> |
|Export_session  <br/> |正在处理  <br/> |文件的上次导出会话 Id, 包括日期。  <br/> |否  <br/> |是  <br/> |
|Extracted_text_length  <br/> |正在处理  <br/> |提取的文本文件的字符长度。  <br/> |否  <br/> |是  <br/> |
|Family_duplicate_set  <br/> |正在处理  <br/> |与每个的精确文本重复的系列的数字标识符 (分别是系列的所有成员都是完全重复的)。  <br/> |否  <br/> |是  <br/> |
|Has_Text  <br/> |正在处理  <br/> |指示文件中是否有文本: 0-否;1-是。  <br/> |否  <br/> |是  <br/> |
|Input_file_ID  <br/> |正在处理  <br/> |从中提取文件的输入文件的 ID。  <br/> |否  <br/> |是  <br/> |
|Native_SHA_256  <br/> |正在处理  <br/> |SHA-256 的本机文件的哈希值。  <br/> |否  <br/> |是  <br/> |
|O365_authors  <br/> |文档属性  <br/> |修改了本机文件的用户, 这些用户是从 SharePoint 或 Exchange 字段中获取的。  <br/> |否  <br/> |是  <br/> |
|O365_created_by  <br/> |文档属性  <br/> |创建了本地文件的用户 (从 SharePoint 或 Exchange 字段中获取)。  <br/> |否  <br/> |是  <br/> |
|Parent_node  <br/> |电子邮件  <br/> |将电子邮件线程中的节点与不丢失链接的最近父节点相关联。  <br/> |否  <br/> |是  <br/> |
|Set_order_inclusives_first  <br/> |电子邮件  <br/> |电子邮件和附件: 按时间顺序排列 (Inclusives)。 文档: 先透视, 再按相似性分数 (降序)。  <br/> |否  <br/> |是  <br/> |
|Tagged_By  <br/> |相关性  <br/> |将文件标记为与特定问题相关的用户。  <br/> |否  <br/> |是  <br/> |
|Word_count  <br/> |分析  <br/> |文档中的单词数。  <br/> |否  <br/> |是  <br/> |
|||||||||||
||||||
||||||
   
## <a name="related-topics"></a>相关主题

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[使用高级电子数据展示导出事例数据](export-case-data-in-advanced-ediscovery.md)
  
[导出结果](export-results-in-advanced-ediscovery.md)
  
[查看批次历史记录和导出过去的结果](view-batch-history-and-export-past-results.md)
  

