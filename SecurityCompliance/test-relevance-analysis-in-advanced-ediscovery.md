---
title: 在 Office 365 高级电子数据展示中测试相关性分析
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: '了解如何在 Office 365 高级电子数据展示中的批处理计算后使用测试选项卡测试、 比较和验证处理的总体质量。  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525423"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中测试相关性分析

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
高级电子数据展示中的测试选项卡，可以测试、 比较和验证处理的总体质量。这些测试批次计算之后执行。通过标记集合中的文件，专家使得关于每个已标记的文件是否是实际与案例相关的最终判断。 
  
在单个和多问题的情况下，每个问题通常执行测试。每个测试后，可以查看结果，并可以与指定的示例测试文件返工测试结果。
  
## <a name="testing-the-rest"></a>测试 rest

"测试 Rest"测试用于验证挑选决策，例如，若要查看仅根据最终高级电子数据展示结果的特定相关性截止分数上方的文件。专家审阅下的所选的截止分数计算该集内的相关文件数的文件的示例。
  
此测试提供的 Rest 人口统计信息和审阅设置和测试之间的比较。审阅设置的结果那些期间培训按相关性计算。结果包含计算、 基于的设置和输入的参数，如：
  
- 测试示例和标识的相关文件中的示例文件数的统计信息。 
    
- 审阅设置和其余，例如，文件数的总体参数的表格比较估计数相关的文件、 估计的丰富和查找其他相关文件的平均成本。成本的参数设置可以由管理员设置。
    
1. 打开**相关性\>测试**选项卡。 
    
2. 在**测试**选项卡中，单击**新建测试**。将显示**创建测试**对话框中，如下面的示例中所示。 
    
    ![相关性测试其余结果](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. 在**测试名称**和**说明**中，键入名称和说明。
    
4. 在**测试类型**列表中，选择**测试 Rest**
    
5. 在**问题 / 类别**列表中，选择问题名称。 
    
6. 在**加载**列表中，选择加载。 
    
7. 在**读取 %**，接受默认值或选择截止相关性分数的值。 
    
8. 在**设置大小**，或接受默认值。请注意还原图标将还原的默认值。
    
9. 单击**开始标记**。生成测试示例。
    
10. 查看和标记中的文件的每个**相关性\>标记**选项卡，完成后，单击**计算**。
    
11. 在测试选项卡，您可以单击**查看结果**，若要查看的测试结果。下图是一个示例。 
    
    ![测试其余结果](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
在上图中，表的**示例参数**部分包含有关使用专家，示例中的文件数和相关的示例中找到的文件数的详细信息。 
  
**总体参数**部分中的表包含的测试结果，包括下面所选截止分数的文件的审阅设置填充和具有所选截止上方的分数的文件的"Rest"填充。为每个总体，显示以下结果： 
  
- 包括具有读取 %-既定截止文件
    
- 文件总数 
    
- 相关文件的估计的数目 
    
- 估计的丰富 
    
- 平均审阅成本的查找另一个的相关文件
    
## <a name="testing-the-slice"></a>测试切片

"测试切片"测试执行测试类似于"测试 Rest"测试，但文件段设置为指定的相关性读取 %。
  
1. 打开**相关性\>测试**选项卡。 
    
2. 在**测试**选项卡中，单击**新建测试**。显示**创建测试**对话框。 
    
3. 在**测试名称**和**说明**中，键入信息。
    
4. 在**测试类型**列表中，选择**测试切片**。
    
5. 在**问题**列表中，选择问题名称。 
    
6. 在**加载**列表中，选择加载。 
    
7. 在**读取 %之间**，接受默认低和高范围值或选择截止相关性分数的值。 
    
8. 在**设置大小**，选择一个值，或接受默认值。
    
    还原图标将还原为默认值。
    
9. 单击**开始标记**。生成测试示例。
    
10. 查看和标记中的文件的每个**相关性\>标记**选项卡，完成后，单击**计算**。 
    
11. 在测试选项卡，您可以单击**查看结果**，若要查看的测试结果。 
    
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解评估中相关性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标签和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标签和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[决定基于结果](decision-based-on-the-results-in-advanced-ediscovery.md)
