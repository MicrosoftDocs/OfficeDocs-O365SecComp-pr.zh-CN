---
title: 在 Office 365 高级电子数据展示中运行流程模块
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
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: '了解有关准备的案例文件的 Office 365 数据分析与 Office 365 高级电子数据展示的指导标准。  '
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525955"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中运行流程模块

在**准备**期间案例文件加载到高级电子数据展示\>**过程**。 
  
> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a>准则： 准备高级电子数据展示数据

- **质量**： 清楚地标识与案例相关的案例文件填充。
    
- **加载**： 将文件加载到高级电子数据展示可以访问的位置。
    
- **文件 ID**： 高级电子数据展示中的唯一的文件标识符。如果没有文件标识符导入，高级电子数据展示自动生成 id。如果您映射后续处理负载中的 ID，并将初始过程负载以外的其他路径，高级电子数据展示将取代路径 （而不添加一个新的文件项）。ID 可用作导出过程中的引用。ID 值不应为"-1"。
    
- **MD5**： 此签名用于区分 （两个文件均不被视为完全重复除非他们拥有相同 MD5） 的文件。默认情况下，高级电子数据展示计算 MD5 的文件。当加载的文件文本文件时，建议加载并映射而不是计算高级电子数据展示中的原始 MD5 值。
    
- **文件类型和名称**：
    
  - 高级电子数据展示可以处理的各种格式的文件，并将加载本机文件解压缩到标准格式，如\*。TXT、 HTML，或。比本机文件 XML。 处理的文本文件。提取的文本文件存储的大小写的文件夹中。
    
  - 不加载无法提取，例如系统文件或图形的图像的文件。这些文件可能会延迟处理。
    
  - 验证显著名文件名和路径正确。
    
- **文件路径**： 高级电子数据展示可以加载文件路径长度最多 400 个字符。
    
- **文本提取**： 时从本机文件，除了普通文本提取文本还提取以下： 隐藏的文本 （Excel 和.doc），隐藏列 (Excel) （例如，跟踪更改 (.doc)，扬声器 notes (.ppt) 嵌入对象Excel 中的对象.ppt）。可以在文本编辑器中查看这些。
    
- **忽略文本**： 运行过程之后，并在分析定义此可选功能。忽略应谨慎使用文本，因为其使用可能会降低文件分析的性能。
    
- **多语言文本**： 高级电子数据展示当前未处理的标记、 custodian 和问题的多语言名称。
    
- **元数据**： 确定是否要保存以供将来参考，日期范围，文件大小、 文件类型，如案例数据库中 custodian，并使用者的元数据。文件已加载无需重新运行库存或添加开销重新处理后，可以加载元数据。 
    
  - 如果路径最初已加载的文件，将时更高版本导入元数据映射路径列。有可能，请参阅按 ID 文件并将映射其他路径。文件路径更改时，这是一个非常有用的方案。
    
  - 如果按文件 ID 最初已加载的文件，将在加载元数据时映射 ID 列。引用路径 （而不是 ID) 的文件将导致文件重新加载与一个不同的 id。高级电子数据展示创建文件的副本而不显示该加载元数据的现有文件。
    
- **系列**： 不能加载不 （标头的系列） 其父级的系列。 
    
- **文件大小**： 文件加载到高级电子数据展示的大小没有限制。分析 （分析、 相关性等），限制为 5,242,880 提取的文本的字符。较大的文件将被忽略 （例如，在相关性，文件不参与相关性培训进程和批次计算后将不会接收的相关性分数）。
    
- **文件数量**： 没有任何建议的限制，可以在单个案例中处理的文件数。性能取决于您的系统的资源。 
    
## <a name="filtering-files"></a>筛选文件

用户定义的标签可与一组文件排除过程或其他任务关联。每个进程会话相关联批处理 id。尽管批处理 ID 不是对相关性专家可见的这可以使用搜索实用程序，通过添加当前批次的筛选器和标记所有相应文件的用户定义的标签。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[运行进程模块并将数据加载](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[查看过程模块结果](view-process-module-results-in-advanced-ediscovery.md)

