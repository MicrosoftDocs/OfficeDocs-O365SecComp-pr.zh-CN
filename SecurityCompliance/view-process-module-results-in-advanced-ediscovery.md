---
title: 查看 Office 365 高级电子数据展示中的流程模块结果
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
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: '了解如何查找在 Office 365 高级电子数据展示中运行的进程模块的结果, 包括任务状态和过程摘要。  '
ms.openlocfilehash: 0393cde78e559036d92b9ac48245afafc974a8b2
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218052"
---
# <a name="view-process-module-results-in-office-365-advanced-ediscovery"></a>查看 Office 365 高级电子数据展示中的流程模块结果

启动**准备** \> **过程**后, 可以查看进度和结果。 
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="process-task-status"></a>处理任务状态

在**准备** \> **过程** \> **结果**中, 页面显示当前状态 (如果当前正在运行进程) 或最后一个进程状态任务的状态, 如下面的示例所示。
  
![进程模块任务状态](media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
根据所选的流程选项, 显示的任务可能会有所不同。 
  
- **清单**: 高级电子数据展示循环访问选择进行进程的所有文件, 并执行基本的数据收集。
    
- **计算签名**: 计算 MD5 数字签名。
    
- "组合**提取**": 以递归方式从复合文件 (例如, PST, ZIP, MSG) 中提取内部文件或包含的文件。提取的文件存储在事例的事例文件夹中。
    
- **同步数据库**: 内部数据库进程。
    
- **文件复制**: 复制进程文件。始终显示此任务, 即使选择了 "高级复制文件" 选项也是如此。
    
- **文本提取**: 当存在本机文件时, 高级电子数据展示使用 DTSearch 从这些文件中提取文本。这些文件的提取文本作为文本文件存储在 case 文件夹中。
    
- **更新元数据**: 处理加载的元数据。 
    
- **完成**: 最终处理已加载的事例文件的数据 (例如, 识别错误和成功文件)。 
    
任务状态: 在任务完成后显示。运行任务时, 将显示 "运行持续时间"。
  
> [!NOTE]
> 已完成的任务还可能包含已完成处理的文件或有错误的文件的总计。 
  
> [!TIP]
> "取消" 提供回滚选项以停止进程执行, 然后回滚到以前的数据填充或已保存的已处理数据。Rollback 将清除所有已处理的数据。如果您不希望处理的数据丢失 (例如, 您计划重新加载这些文件), 请选择此窗口中的 "取消" 选项以选择不回滚。 
  
## <a name="process-summary"></a>流程摘要

在准备\>流程\>结果\>流程摘要中, 根据成功的文件处理和错误结果显示加载的文件结果的细目。
  
这些窗格显示导入文件统计信息的图形显示, 如下所示:
  
- **流程摘要累积**d: 事例中的所有文件。
    
- **进程摘要最后**: 从上一个会话或操作加载的文件。 
    
- **系列持续**时间: 在案例中的家庭信息 (如果有)。
    
- 如果添加了**种子**文件, 则会在为文件定义的每个问题中列出种子文件的数量。 
    
    如果**种子**文件的标记失败, 也会注明。 
    
- 如果添加了**预先加标签**的文件, 则在为文件定义的每个问题中都会列出预先加标签的文件的数量。 
    
    如果**预先加标签**的文件的标记失败, 也会注明。 
    
![进程模块摘要](media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>流程摘要和最后一个图表

左侧栏包含源 + 提取的文件: 这是找到的所有文件。 
  
右侧条 (已处理) 包括:
  
- 包含加载错误的文件
    
- 已成功加载文件, 其中可能包括: 
    
  - **现有**: 以前加载过且现在再次加载的文件 (包括重复项)。
    
  - **text**: 包含文本的唯一文件。
    
  - **非文本**: 空文本文件、空的本机文本文件、本机非文本文件。 
    
  - **重复**的 s: 包含文本的重复文件。
    
## <a name="last-process-errors"></a>上一个进程错误

在准备\>过程\>结果\>中, 上次处理错误时, 将显示上一次会话或执行的操作中的错误详细信息。
  
![进程模块错误](media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[运行进程模块并加载数据](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

