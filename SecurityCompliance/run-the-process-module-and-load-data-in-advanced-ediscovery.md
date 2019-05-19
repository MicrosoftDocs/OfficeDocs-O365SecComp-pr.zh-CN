---
title: 在 Office 365 高级电子数据展示中运行 Process module 和 load data
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: '了解如何使用 Office 365 安全&amp;合规中心访问 Office 365 高级电子数据展示, 并运行 Process module for a case。  '
ms.openlocfilehash: 89a4be9bf56f35d9d9cbd88494bcae5a5a10fe7a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157014"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中运行 Process module 和 load data

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本节介绍高级电子数据展示过程模块的功能。 
  
除了文件数据之外, 元数据 (如文件类型、扩展名、位置或路径、创建日期和时间、作者、管理员和主题) 可以加载到高级电子数据展示中并为每个事例保存。 有些元数据是由高级电子数据展示计算的, 例如, 在加载本机文件时。 
  
高级电子数据展示提供系统元数据值, 如接近重复的分组或相关性分数。 其他元数据 (如文件批注) 可由管理员添加。 
  
## <a name="running-process"></a>正在运行的进程

> [!NOTE]
> 批处理号在进程中分配给文件以允许跟踪文件。 批处理号还允许对处理选项的进程批处理进行标识。 可以按批处理号和会话筛选其他筛选器。 
  
执行以下步骤以运行进程。
  
1. [打开 "Office 365 安全&amp;合规中心"](go-to-the-securitycompliance-center.md) 。 
    
2. 转到**搜索&amp;调查** \> **电子数据展示**, 然后单击 "**转到高级电子数据展示**"。
    
3. 在高级电子数据展示中, 在 "显示**事例**" 页面中选择适当的事例, 然后单击 "**转到大小写**"。
    
4. 在 "**准备** \> **过程** \> **安装**" 中, 从可用容器列表中选择一个容器。
    
    ![单击 "处理" 以将搜索结果添加到案例](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. 如果要将容器添加为 seed 文件或预先加标签的文件, 请单击 "**高级设置"。** 
    
    使用种子文件加快丰富程度较低的问题 (通常为 2% 或更少) 的培训。 对于种子文件, 建议您选择各种明显相关的文件, 并在每个问题中处理大约20-50 种子 (种子文件太多可能会扭曲相关性结果)。 应由将对问题进行培训的同一人审阅种子文件。
    
    使用预先加标签的文件以自动进行相关性培训。 应标记至少1500个文件, 并将与非相关文件相关的比例与添加到相关性的集合中的比例保持一致。 应手动标记这些文件, 并且您应该自信标记质量。
    
    ![用于处理批处理文件的 "高级设置" 页的屏幕截图](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - 在 "**种子**" 部分中: 
    
    选择 "**标记为种子文件**" 以将容器标记为种子文件。 您还需要根据问题下拉下拉箭头, 选择为**** 其分配每个问题。 从 "**标记**" 下拉选择 "**相关**或**不相关**"。 
    
    > [!NOTE]
    > 将文件设置为**种子**后, 不能将其标记为**预先加标签**的。 
  
  - 在 "**预加标签的文件**" 部分: 
    
    选择 "**标记为预先加加标签的文件**" 以将容器标记为预先加标签的文件。 您还需要根据问题下拉下拉项为其**** 分配每个问题。 从 "**标记**" 下拉选择 "**相关**或**不相关**"。 
    
    > [!NOTE]
    > 将文件设置为**预先加标签**后, 不能将其标记为**种子**。 
  
  - 在 "**电子邮件标签**" 部分。 设置已处理的电子邮件的哪一部分将被标记为种子或预先标记。 
    
6. 若要开始, 请单击 "**处理**"。 完成后, 将显示流程结果。
    
7. Optional如果需要向特定保管人分配数据源, 可以在**保管人** \>中添加和编辑保管人名称**管理**和分配保管人**** \> **assign**中的保管人。 
    
如果向事例添加, 则可以再次处理。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[查看流程模块结果](view-process-module-results-in-advanced-ediscovery.md)

