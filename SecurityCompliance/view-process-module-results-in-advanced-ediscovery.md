---
title: 查看 Office 365 高级电子数据展示中的流程模块结果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何查找在 Office 365 高级电子数据展示，其中包括任务状态和摘要过程中运行的进程模块的结果。  '
ms.openlocfilehash: 01093b0230aaf78ab7ccf1235f0874a0b69aa1bd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524819"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>查看 Office 365 高级电子数据展示中的流程模块结果

**准备**后\>启动**过程**，您可以查看进度和结果。 
  
> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="process-task-status"></a>处理任务状态

在**准备** \> **过程** \> **结果**，页上显示的当前状态 （如果当前正在运行过程） 或最后一个进程状态任务状态在以下示例中所示。
  
![进程模块任务状态](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
显示的任务可能取决于所选进程选项。 
  
- **清单**： 高级电子数据展示循环访问所有进程选定文件，并执行基本的数据集。
    
- **计算签名**： 计算 MD5 数字签名。
    
- **组合提取**： 提取内部或包含文件以递归方式从复合文件 (例如太平洋标准时间，ZIP，MSG)。解压缩的文件存储的大小写的案例文件夹中。
    
- **同步数据库**： 内部数据库过程。
    
- **文件复制**： 副本处理文件。始终显示该任务中，选择高级的复制文件选项的情况下，即使。
    
- **文本提取**： 高级电子数据展示时有本机文件，从使用 DTSearch 这些文件提取文本。作为案例文件夹中的文本文件存储中的这些文件提取的文本。
    
- **更新元数据**： 处理加载元数据。 
    
- **正在**： 完成的数据的内部处理加载案例文件 （例如，确定错误和成功文件）。 
    
任务状态： 显示任务完成后。任务在运行时，将显示运行持续时间。
  
> [!NOTE]
> 已完成的任务可能还包括汇总完成处理的文件或有错误的文件。 
  
> [!TIP]
> "取消"提供了回滚选项，停止过程执行，然后回滚到以前的数据填充或保存处理的数据。回滚清除所有已处理的数据。如果您不希望在此窗口中的选择"取消"选项，可选择不回滚 （例如，您打算将这些文件重新加载） 丢失的处理的数据。 
  
## <a name="process-summary"></a>过程摘要

在准备\>过程\>结果\>进程摘要，加载的文件结果的分解显示根据成功文件处理和错误结果。
  
窗格演示导入的文件统计信息的图形显示，如下所示：
  
- **过程摘要累加**d： 情况的所有文件。
    
- **上次处理摘要**： 从最后一个会话或操作加载的文件。 
    
- **系列上次**： 家族情况 （如果有） 的信息。
    
- 如果**种子**文件已添加，每个已定义的文件的问题列出的种子文件数。 
    
    如果的**种子**文件标记失败，也记下。 
    
- 如果**前标记**文件已添加，每个已定义的文件的问题列出的前已标记的文件数。 
    
    如果**前标记**文件的标记失败，也记下。 
    
![进程模块摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>过程摘要累积和上次图表

左侧的栏包含源 + 解压缩的文件： 这是所有文件找到。 
  
右侧栏处理，包括：
  
- 文件加载错误
    
- 已成功加载的文件，这可能包括： 
    
  - **现有**： 之前已加载并再次 （包括重复项） 现在已加载的文件。
    
  - **文本**： 唯一文件文本。
    
  - **非文本**： 空文本文件、 空本机文本文件、 本机非文本文件。 
    
  - 文本具有**重复**s： 重复文件。
    
## <a name="last-process-errors"></a>最后一个过程错误

在准备\>过程\>结果\>显示最后一个过程错误中的最后一个会话或执行的操作的错误的详细信息。
  
![进程模块错误](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[运行进程模块并将数据加载](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

