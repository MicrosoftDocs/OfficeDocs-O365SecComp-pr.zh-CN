---
title: 查看 Office 365 高级电子数据展示中的分析结果
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解在 Office 365 高级电子数据展示中查看分析过程结果的位置, 包括所显示的任务选项的定义。  '
ms.openlocfilehash: 990bcbb3c6626521d40f7ce057c764200d5047b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218822"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>查看 Office 365 高级电子数据展示中的分析结果

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中, 分析过程的进度和结果可在各种显示器中查看, 如下所述。
  
## <a name="view-analyze-task-status"></a>查看分析任务状态

在**准备\>分析\>结果\>任务状态**中, 状态在分析流程执行期间和之后都会显示。 
  
![分析任务状态](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
根据所选的选项, 显示的任务可能会有所不同。 
  
- **ND/ET: setup**: 为运行做准备, 例如, 设置运行和用例参数。
    
- **nd/ET: nd 计算**: 处理文件的近乎重复的分析。
    
- **ND/ET: ET 计算**: 对整个电子邮件集执行电子邮件线程分析。
    
- **ND/ET: 透视和相似性**: 执行透视和文件相似性处理。
    
- **ND/ET: 元数据更新**: 最终完成在数据库中的文件上收集的新数据。
    
- **主题: 主题计算**: 运行主题分析。(仅在选中时显示。)
    
- **任务状态**: 此代码行在任务完成后显示。运行任务时, 将显示 "运行持续时间"。
    
> [!NOTE]
> 邻近重复和电子邮件线程 (ND 和 ED) 的分析结果适用于要处理的文档数。它不包含完全重复的文件。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>查看临近的重复和电子邮件线程状态

**目标**填充结果显示目标填充中的文档数、电子邮件、附件和错误。 
  
**文档**结果显示透视次数、唯一的临近重复项和完全重复的文件。 
  
**电子**邮件结果显示包含的包含的、包含的减去、唯一的包含副本的数量以及其余的电子邮件。不同类型的电子邮件结果为: 
  
- **包括**: 包含电子邮件的电子邮件线程中的终止节点, 并包含该线程的所有以前的历史记录。因此, 审阅者可以安全地重点关注包含的电子邮件, 而无需读取该线程中的前一封邮件。 
    
- **包含减号**: 如果有一个或多个不同的附件与包含的邮件的父项关联, 则将包含的电子邮件指定为包含的减号。在此上下文中, 术语 "父级" 用于向上的电子邮件线程或该特定包含电子邮件中包含的对话的邮件。审阅者可以使用包含的减号表示作为信号, 尽管可能不需要查看包含的电子邮件父项的内容, 但查看与包含的路径父项关联的附件可能很有用。 
    
- **包含副本**: 如果是被标记为包含或包含减号的另一封邮件的副本, 则将包含的电子邮件指定为包含副本。换句话说, 此邮件与另一个包含邮件具有相同的主题和正文, 因此共同驻留在同一节点中。由于包含副本邮件包含相同的内容, 因此通常可以在审阅过程中跳过它们。 
    
- **rest**: 这表示电子邮件不包含任何唯一的内容, 因此不属于上述三个类别中的任何一个。不需要查看这些电子邮件。如果邮件包含不在后续包含的电子邮件中的附件, 则可能需要审阅附件。这由线程中的包含负电子邮件的存在指示。
    
**附件**结果将根据此类类型 (唯一和重复) 显示附件数。 
  
![近似重复和电子邮件线程](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](view-analyze-results-in-advanced-ediscovery.md)

