---
title: 使用 Office 365 高级电子数据展示中的快速分析
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
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: 了解如何运行 Office 365 高级电子数据展示的 Express 分析模式
ms.openlocfilehash: a71e6775b1116e805e455815dca53a727d887809
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525268"
---
# <a name="use-express-analysis-in-office-365-advanced-ediscovery"></a>使用 Office 365 高级电子数据展示中的快速分析

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
您可以使用**Express 分析**快速分析案例和导出结果。 
  
Express 分析可用于计算近乎重复项和电子邮件线程和计算主题。您还可以[Express 分析的高级的设置](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)中设置某些主题、 文档相似性和导出文件的参数。
  
## <a name="run-express-analysis"></a>运行 Express 分析

1. 在**Express 分析**(1) 选项卡，选择启用的容器 * * Express 分析 * * (2) 和**高级设置**按钮。 
    
    ![Express 分析页的屏幕截图](media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. 下**分析参数**：
    
  - 如果您想要运行分析，检查**计算近乎重复项和电子邮件线程**。默认情况下选择它。 
    
  - 检查**计算主题**处理所有文件并将主题分配给它们。默认情况下选择它。 
    
3. 在**导出目标**：
    
  - 检查**下载到本地计算机中**下载到本地计算机。 
    
  - 如果您检查**导出到用户定义的 Azure blob**然后您还可以指定容器 URL 和 SAS 令牌。 
    
    > [!NOTE]
    > 一旦导出包存储到用户定义 Azure blob，高级电子数据展示不再管理的数据。它被管理 Azure 的 blob。这意味着，如果您删除这种情况，导出的文件仍将保留在 Azure blob 上。 
  
  - **保存 SAS 将来导出会话令牌**： 如果选中，都将被 SAS 令牌加密以供将来使用高级电子数据展示的内部数据库中。
    
    > [!NOTE]
    > 当前该 SA 令牌有效期一个月。如果您尝试在您需要撤消最后一个会话超过一个月后下载，然后再次导出。 
  
4. 若要启动 express 分析具有默认设置，选择**Express 分析**，并将显示**任务状态**页 
    
    在**任务状态**页上，您可以展开**过程**、**分析**和**导出**选项卡以显示有关 express 运行的详细信息。 
    
    ![屏幕截图的高级电子数据展示 Express 分析任务状态页](media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. 选择**Express 分析摘要**页上列出有关运行的详细的信息。 
    
    在**Express 分析摘要**页的底部，选择**下载上次会话**下载分析文件 tp 本地计算机。您首先需要下载电子数据展示导出工具并粘贴到电子数据展示导出工具的导出密钥。 
    
## <a name="advanced-settings-for-express-analysis"></a>Express 分析的高级的设置
<a name="BK_AdvancedSettings"> </a>

您可以选择设置**高级设置**更改默认 Express 分析参数。 
  
1. 在**分析**部分中： 
    
  - 在**靠近重复项和电子邮件线程**，输入**文档相似性**值，或接受默认的 65%。 
    
  - 在**主题的最大数目**输入或选择一个值主题创建的数目。默认值为 200。 
    
    > [!NOTE]
    > 增加了主题会影响性能，以及使通用化主题的能力。主题的更高版本数、 更精细它们是。例如，如果一 50 主题中包含"篮球、 支路，剪，Lakers"; 例如主题300 主题可能包括单独的主题:"支路"、"剪 2"、"Lakers"。如果您具有"篮球"的任何认知度的主题，并对 ECA 使用该功能，查看主题"篮球"非常有用。但是，如果处理有太多的主题，您可能永远不会看到的单词"篮球"并可能不知道，支路和剪是好篮球主题，若要查看，而不是项目上，启动和用于字形。 
  
  - 选择**建议主题**的**修改**建议主题单词以控制处理的主题。高级电子数据展示将专注于这些建议单词，然后尝试创建一个或多个相关的主题，基于"最大主题数目"设置。 
    
    例如，如果所建议的单词"computer"，并且您"主题的最大数量"指定"2"，高级电子数据展示将尝试生成与 word"computer"的两个主题。两个主题可能是"计算机 software"和"计算机 hardware"，例如。
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **模式**从下拉列表中，选择**主题**选项: 
    
  - **创建和应用模型**： 计算由模型文件的一段中的主题，然后分布在它们之间的文件。
    
  - **创建模型**： 计算一段的文件中的主题模型。划分文件的应用过程是单独完成另一次。
    
  - **应用模型**： 是否以前创建和尚未应用模型，才会显示此选项。这将分割基于主题的文件。
    
2. 在**导出**部分中： 
    
1. **选择导出批次**： 中
    
  - 从**导出批处理**列表中，选择批处理名称或将结果导出到导出批处理 01、 （默认批次）。 
    
  - 若要导出结果的新文件添加到现有用例，继续使用您当前的批次。若要创建的批处理中的会话，请选择的相同的批次编号，单击**创建导出会话**可以使用此选项以增量方式为上一批次，导出相同的参数。 
    
  - 若要导出到新的批次，单击**添加**![图标添加](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)和**批处理名称**中输入新的名称 （或接受默认值） 以及在**说明批次**的说明。单击**确定**。
    
  - 若要编辑的批处理名称或说明，请选择中**导出批次**的名称，单击**编辑**![编辑图标](media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png)，然后修改字段。
    
    > [!NOTE]
    > 您已运行导出批次会话后，他们不能删除。此外，运行第一个会话后，即可进行编辑只有一些参数。 
  
  - 若要创建的重复导出批次，请选择**重复导出批处理**![创建重复导出批处理图标](media/3f6d5f59-e842-4946-a493-473528af0119.jpg)在面板中输入名称和重复批次的说明。 
    
  - 若要删除的导出批次，选择**删除**![删除导出批处理图标](media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)。
    
  - 若要查看的批次的历史记录，请选择**批处理历史记录**![查看历史记录图标](media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)。
    
2. 在定义 p 下**opulation:** 选择**仅包括文件相关性截止分数上方**和/或**优化导出批次**，如果您想要调整您导出批次的设置。如果您选择**包括仅上方相关性截止分数的文件**，然后启用，**问题**，并且如果该文件的相关性分数大于所选问题的截止分数，然后将导出文件。将导出的文件，除非排除了筛选器**进行审阅**。如果您选择**优化导出批处理**，然后**消除**和**Filter by 审阅字段**单选按钮处于启用状态。如果您选择**消除**，然后复制文件将被筛选出根据定义的策略: [Case 级别 （默认值）： 从每个组重复文件在整个的情况下，所有而不是一个文件将重复消除。Custodian 级别： 所有而不是一个文件将从每个组的相同 custodian 重复文件，重复消除。导出输出中可用的所有重复的文件的记录。如果您选择**筛选器的查看**字段中，选择**修改下元数据**输入**供审阅**字段设置。选择**包含输入的文件**要包含在包内容中的源代码文件。您可以清除此选项以加快导出过程。请注意，将在任何情况下导出的本机文件。
    
3. 下**定义元数据**，从 （每次会话） 的**导出模板**列表中的以下选项中进行选择。 
    
  - **标准**： 套基本的数据项目、 元数据，而将属性。高级电子数据展示中已处理数据导入和导出数据上载到系统已包含的文件时，请使用此选项。默认情况下，导出模板列创建和填充。
    
  - **所有**： 整套标准元数据，包括所有处理数据，以及分析和相关性分数。此模板时需要高级电子数据展示执行处理和文件数据上载到外部系统的第一次。
    
  - **问题**： 选择**所有问题**，或者都选择您已创建的特定问题。 
    
选择**确定**保存高级的设置，**还原默认设置**为使用默认值，或**取消**取消设置的高级的设置。 
  
## <a name="see-also"></a>另请参阅
<a name="BK_AdvancedSettings"> </a>

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
