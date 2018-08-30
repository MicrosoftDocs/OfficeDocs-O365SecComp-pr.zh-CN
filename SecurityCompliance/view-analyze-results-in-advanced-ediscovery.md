---
title: 查看 Office 365 高级电子数据展示中的分析结果
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: '了解在何处可以查看 Office 365 高级电子数据展示，其中包括显示的任务选项的定义中的分析过程的结果。  '
ms.openlocfilehash: 8f1de53e5548c8721f8fbfdb83374edb18379114
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525790"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>查看 Office 365 高级电子数据展示中的分析结果

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
高级电子数据展示，进度和分析过程的结果可在查看各种显示如下所述。
  
## <a name="view-analyze-task-status"></a>查看分析任务状态

在**准备\>分析\>结果\>任务状态**，状态显示期间和之后分析进程执行。 
  
![分析任务状态](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
显示的任务可能取决于所选的选项。 
  
- **和/ET： 安装程序**： 准备运行，例如，设置运行和案例参数。
    
- **和/ET： 和计算**： 进程近乎重复分析的文件。
    
- **和/ET: ET 计算**： 执行电子邮件线程分析对整个电子邮件设置。
    
- **和/ET： 数据透视表和相似之处**： 执行数据透视表和文件相似性处理。
    
- **和/ET： 元数据更新**： 完成收集数据库中的文件的新数据。
    
- **主题： 主题计算**： 运行主题分析。（仅当选择显示。）
    
- **任务状态**： 任务完成后显示此行。任务在运行时，将显示运行持续时间。
    
> [!NOTE]
> 分析结果的重复项附近和电子邮件线程 （和和 ED） 应用于要处理的文档数。它不包括完全重复的文件。 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>查看重复项附近和电子邮件线程状态

**目标**总体结果目标总体中显示文档、 电子邮件、 附件和错误的数。 
  
**文档**结果显示数据透视表、 唯一附近的重复项和完全重复的文件的数。 
  
**电子邮件**结果显示的非独占、 包容减去，唯一的非独占副本数和电子邮件的其余部分。不同类型的电子邮件结果是： 
  
- **非独占**： 非独占电子邮件是在电子邮件线程中的终止节点，其中包含的线程的所有以前的历史记录。因此，审阅者可以安全地关注非独占电子邮件，而无需阅读主题中前面的消息。 
    
- **非独占减去**： 非独占电子邮件被指定为非独占减号，如果有一个或多个非独占的消息的父项相关联的不同附件。在此上下文，父用于邮件的电子邮件线程或对话向上位于的术语包含该特定的非独占电子邮件中。审阅者可以使用非独占减去指示为信号，尽管它可能不需要查看的非独占的电子邮件父级内容，可能很有用，若要查看的非独占路径父项相关联的附件。 
    
- **非独占的副本**： 非独占电子邮件被指定为非独占副本时的副本的其他邮件标记为非独占或减去非独占。换句话说，此消息具有相同的主题和正文为另一个非独占邮件，并且，因此，共同位于同一个节点。由于之间复制邮件包含相同的内容，它们可以通常跳过的审核流程。 
    
- **Rest**： 这表示不包含任何唯一的内容，并因此不属于任何以前的三种类别的电子邮件。这些电子邮件消息不需要进行审阅。如果邮件包含不在的更高版本之间的电子邮件的附件，然后附件可能需要进行审阅。这指示非独占减去主题中的电子邮件的存在情况。
    
**附件**结果显示附件，根据此类作为唯一的类型和重复项的数量。 
  
![近似重复和电子邮件线程](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](view-analyze-results-in-advanced-ediscovery.md)

