---
title: 在 Office 365 高级电子数据展示中设置分析选项
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '查看设置选项的 Office 365 高级电子数据展示，包括近乎重复项、 电子邮件线程和主题中的分析过程的步骤。  '
ms.openlocfilehash: a0ebbadb180321a3094cb1056ed8e0e6500ee66a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525395"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中设置分析选项

> [!NOTE]
> 高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示，设置之前运行分析分析选项。
  
## <a name="set-analyze-options"></a>设置分析选项

打开**准备\>分析** \> **安装程序**。将显示以下窗口。
  
![设置分析选项](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **近乎重复项和电子邮件线程**如果您想要运行分析，请选中此框。默认情况下选择它。 
  
 **文档相似性**输入 Near 重复阈值或接受默认值 65%。 
  
 **主题**选中此框可处理所有文件并将主题分配给它们。默认情况下不选中此复选框。如果您想要执行处理的主题，请输入以下选项。
  
- **主题的最大数目**输入或选择主题创建的数目的值。默认值为 200。 
    
    > [!NOTE]
    > 增加了主题会影响性能，以及使通用化主题的能力。主题的更高版本数、 更精细它们是。例如，如果一 50 主题中包含"篮球、 支路，剪，Lakers"; 例如主题300 主题可能包括单独的主题:"支路"、"剪 2"、"Lakers"。如果您具有"篮球"的任何认知度的主题，并对 ECA 使用该功能，查看主题"篮球"非常有用。但是，如果处理有太多的主题，您可能永远不会看到的单词"篮球"并可能不知道，支路和剪是好篮球主题，若要查看，而不是项目上，启动和用于字形。 
  
- **建议主题**您可以选择建议主题单词以控制处理的主题。高级电子数据展示将专注于这些建议单词，然后尝试创建一个或多个相关的主题，基于"最大主题数目"设置。 
    
    例如，如果所建议的单词"computer"，并且您"主题的最大数量"指定"2"，高级电子数据展示将尝试生成与 word"computer"的两个主题。两个主题可能是"计算机 software"和"计算机 hardware"，例如。 
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 若要查看、 添加或编辑建议的主题，请单击**修改**。
    
2. 在**建议主题**面板中，单击**添加**![添加图标](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png)图标添加主题。在**添加建议的主题**面板中，添加的单词，以逗号分隔。 
    
3. 在**主题数目**，选择一个值，确定高级电子数据展示将尝试为这些单词 （默认值为 1 主题） 生成的主题的数目。
    
4. 单击**保存**，然后关闭对话框。 
    
    > [!NOTE]
    > 主题的总数目包括建议的主题。总的建议主题不能超过总主题。如果有许多建议主题相对于总主题，因为大多数的主题将专用于建议主题，系统会检测仅少数"小说"主题。 
  
- **模式**从下拉列表中，选择**主题**选项: 
    
  - **创建和应用模型**： 计算由模型文件的一段中的主题，然后分布在它们之间的文件。
    
  - **创建模型**： 计算一段的文件中的主题模型。划分文件的应用过程是单独完成另一次。
    
  - **应用模型**： 是否以前创建和尚未应用模型，才会显示此选项。这将分割基于主题的文件。
    
您还可以[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)并[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)的分析。 
  
您已设置这些选项后，单击**分析**运行。显示[视图分析结果](view-analyze-results-in-advanced-ediscovery.md)。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

