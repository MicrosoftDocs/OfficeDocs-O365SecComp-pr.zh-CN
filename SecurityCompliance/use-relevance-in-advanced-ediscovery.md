---
title: 使用 Office 365 高级电子数据展示中的相关性模块
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: '了解 Office 365 高级电子数据展示，包括工作流和准则，并进行培训和文件的审阅的步骤中的相关性模块。  '
ms.openlocfilehash: 2cf75ef95291c5393367ce01fb0cd660f9b99145
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525165"
---
# <a name="use-the-relevance-module-in-office-365-advanced-ediscovery"></a>使用 Office 365 高级电子数据展示中的相关性模块

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示，相关性模块包括相关性培训和检查与案例相关的文件。相关性工作流所示，如下所述：
  
![相关性工作流](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- **评估和跟踪的循环**：
    
  - **评估**： 高级电子数据展示启用基于文件的随机示例早期评估，并使用此评估将确定预测的编码过程的性能的决策。 
    
  - **跟踪**： 高级电子数据展示计算并显示监视统计有效性的过程时评估的中间结果。 
    
- **培训和跟踪的循环**：
    
  - **标记**： 高级电子数据展示学习相关性条件特定于基于专家的迭代查看每个问题和标记的单个文件。
    
  - **跟踪**： 高级电子数据展示计算并显示中间结果的相关性培训时监控统计有效性的过程。 
    
- **批次计算**： 高级电子数据展示所需的累积和学习相关性条件，将其应用于整个文件集，并生成相关性分数的每个文件。
    
- **Decide**： 高级电子数据展示显示应用于整个案例后批次计算分析的结果，并显示文档审阅决策的数据。
    
- **测试**： 高级电子数据展示结果可以进行测试，以验证的有效性和高级电子数据展示处理的有效性。
    
## <a name="guidelines-for-relevance-training-and-review"></a>相关性培训和审阅准则

以下是概述相关性培训和审阅准则：
  
- **错误和不一致情况**： 如果在培训过程进行了标记错误，返回到以前的文件示例，用于对其进行更正。如果有太多错误正确或没有在案例或问题的新的角度来看，相关性条件应重新定义由管理员，并且相关性培训重新启动。
    
- **添加标签和培训**： 
    
  - 应根据内容仅标记文件。不考虑元数据，例如 custodian、 日期或文件路径。 
    
  - 执行操作时不考虑日期范围指示文本中的标记文件。
    
  - 标记文件时，不考虑嵌入式图形的图像。
    
  - 如果查看标记时使用的**格式文本视图**图标的文件，不考虑文字的格式。例如，用删除线 （通过其中心指示删除一条横线） 显示 word 仍视为按相关性已分析的文本的一部分。 
    
  - 忽略于相关性 （如案例管理器或管理员组） 的文本中相关性将文本视图中显示的文件内容中移除。如果忽略文本的值已定义相关性培训已开始后，新忽略的文本将应用于从点在其中定义创建的示例文件中。忽略文本功能应谨慎，使用，因为其使用可能会降低文件分析的性能
    
  - 使用**跳过标记**选项仅在必要时。高级电子数据展示不培训基于上跳过的文件。在评估中，如果很难判断文件是否相关，最好是到标记为 Relevant (R) 或不相关 (NR) 尽可能而不是选择**跳过**。当高级电子数据展示计算培训时，它可以然后看到程度如何处理这些类型的文件。
    
  - 应将偶数文件提取文本非常少量标记进行培训作为 R/NR，而不是"跳过"，如果可能。 
    
  - 标记会影响分类器，前提是该文件是可读，可以标记为 R/NR。
    
  - 在显示的示例文件列表**标记**选项卡上的文件序列号允许用户以返回到文件的原始的显示顺序。 
    
  - 您可以返回到任何示例并更改评估的标记和培训设置文件。创建接下来的示例时，将应用所做的更改。
    
  - 应为 PDF 格式的文件的扫描的 Excel 视为相同本机 Excel 文件时标记文件。
    
  - 当有疑问有关标记文件的相关性时，请参阅专家。在相关性培训的不正确标签可能会导致更高版本过程中丢失的时间和还可能产生负面影响的总体结果质量。
    
  - 已定义的关键字的关键字列表将显示在颜色以帮助用户标记时找出有关文件。
    
- **批次计算**： R/NR 专家将接收的 0 或 100 的分数标记的文件。这适用于标记进行之前批次计算。如果专家批次计算后切换到空闲的问题，并继续标记此问题，新的已标记的分数不可 100/0 但而不显示原始分数。
    
- **问题和采样模式**： 问题通常已关闭，它们的工作完成 （稳定相关性培训和执行批次计算） 时取消问题，或当另一个用户正常对问题。
    
## <a name="steps-in-relevance-training"></a>相关性培训中的步骤

在**相关性\>跟踪**选项卡上，高级电子数据展示提供建议如何继续在处理中，使用以下接下来的步骤。当每个以下步骤建议相关性培训过程中，如下所述的含义。 
  
- 标记 / 继续标记： 文件查看和相关性标记执行每个专家的文件和发出中的示例。
    
  - 暗示： 现有的示例需要标记。
    
- 评估 / 继续评估： 使早期验证案例问题相关性和导入当前的用例文件总体的相关性的初步视图。
    
  - 暗示： 更多评估所需或建议。
    
- 培训 / 继续培训： 期间的高级电子数据展示学习从专家用户标记文件的过程示例，并获取能够标识相关性条件相关的每种情况下上下文中的每个问题。
    
  - 暗示： 问题需要更多培训;接下来的示例应创建和标记。 
    
- 批处理计算： 相关性过程中的高级电子数据展示采用知识培训阶段并将其应用于整个文件填充。相关文件组中的所有文件的相关性评估，并分配的相关性分数。
    
  - 稳定隐含： 问题，并可以执行批次计算。
    
- 追赶： 相关性指示当专家审阅和标记在推出加载的情况下，从其他文件加载所选文件的示例。
    
  - 暗示： 已添加的新负载，，，追赶并且才能继续工作。
    
- 标记不一致情况： 进程标识，通过高级电子数据展示算法标记可能会产生负面影响分析的过程在文件中的不一致情况。
    
  - 暗示： 接下来的示例将上一示例中包括已标记的文件和其标记必须重做。
    
- 更新分类器： 允许用户应用标记或种子设定的更改。
    
  - 暗示： 而无需手动运行另一个相关性示例可以应用标记和种子设定的更改。
    
- 保持： 相关性培训过程完成。
    
  - 暗示： 无相关性培训，则需要此位置。
    
尽管高级电子数据展示将指导您完成此过程中，使用建议的不同阶段的后续步骤，但它还允许您之间的选项卡和网页、 导航和对地址的情况下可能与单个情况下，问题以及相关的选项或文档审阅流程。 
  
它是可以接受或重写高级电子数据展示处理选项的下一步。如果您想要执行之外的建议的下一步步骤，请单击**下一步**中扩展的问题显示在对话框中列出，单击**修改**按钮旁边的下一步，以及选择另一个下一步步骤选项。 
  
> [!NOTE]
> 解锁因为它们不受支持的过程中使用此时之后，某些选项可能会被禁用。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解评估中相关性](assessment-in-relevance-in-advanced-ediscovery.md)
  
[标签和评估](tagging-and-assessment-in-advanced-ediscovery.md)
  
[标签和相关性培训](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[跟踪相关性分析](track-relevance-analysis-in-advanced-ediscovery.md)
  
[决定基于结果](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[测试相关性分析](test-relevance-analysis-in-advanced-ediscovery.md)
