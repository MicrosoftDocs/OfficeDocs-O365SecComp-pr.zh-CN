---
title: 在 Office 365 高级电子数据展示中设置分析选项
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: '查看为 Office 365 高级电子数据展示中的分析过程设置选项的步骤, 包括临近重复项、电子邮件线索和主题。  '
ms.openlocfilehash: 6d853d701613fcbe61c6e98b3bf55ae99eefd901
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156664"
---
# <a name="set-analyze-options-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中设置分析选项

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中, 在运行分析之前设置 "分析" 选项。
  
## <a name="set-analyze-options"></a>设置分析选项

打开**准备\>分析** \> **设置**。 将显示以下窗口。
  
![设置分析选项](media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **临近的重复和电子邮件线索**如果要运行分析, 请选中此框。 默认情况下选中此选项。 
  
 **文档相似性**输入 "接近重复的阈值" 值或接受默认值 "65%"。 
  
 **主题**选中此框可处理所有文件并为其分配主题。 默认情况下, 未选中此复选框。 如果要执行主题处理, 请输入以下选项。
  
- **主题的最大数量**为要创建的主题数输入或选择一个值。 默认值为 200。 
    
    > [!NOTE]
    > 增加主题的数量将影响性能, 并使主题能够通用化。 主题的数量越高, 它们的粒度就越多。 例如, 如果一组50主题包含一个主题, 如 "篮球、Spurs、Clippers、Lakers", 则300主题可能包含单独的主题: "Spurs"、"Clippers"、"Lakers"。 如果您不知道主题 "篮球" 并对 ECA 使用此功能, 则查看主题 "篮球" 可能有用。 但是, 如果处理的主题过多, 则您可能永远无法看到 "篮球" 一词, 也可能不知道 Spurs 和 Clippers 是要查看的理想的篮球主题, 而不是执行启动并用于头发的项目。 
  
- **建议的主题**您可以建议用主题单词来控制主题处理。 高级电子数据展示将重点放在这些建议的单词上, 并根据 "最大主题数" 设置尝试创建一个或多个相关主题。 
    
    例如, 如果建议的单词是 "computer", 并且您将 "2" 指定为 "最大主题数", 高级电子数据展示将尝试生成与 "computer" 一词相关的两个主题。 例如, 这两个主题可能是 "计算机软件" 和 "计算机硬件"。 
    
    ![添加建议的主题](media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. 若要查看、添加或编辑建议的主题, 请单击 "**修改**"。
    
2. 在 "**建议的主题**" 面板中, 单击 "](media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **添加** ![" "添加图标" 图标以添加主题。 在 "**添加建议的主题**" 面板中, 添加单词, 并以逗号分隔。 
    
3. 在 "**主题数量**" 中, 选择一个值以确定高级电子数据展示将尝试为这些单词生成的主题数 (默认为1主题)。
    
4. 单击 "**保存**", 然后关闭对话框。 
    
    > [!NOTE]
    > 主题的总数包括建议的主题。 建议的主题总数不能超过总主题。 如果有多个建议的主题相对于总主题, 则系统只会检测到几个 "novel" 主题, 因为大多数主题将专用于建议的主题。 
  
- **模式**从下拉列表中, 选择 "**主题**" 选项: 
    
  - **创建和应用模型**: 从一段文件的模型计算主题, 然后在它们之间分发文件。
    
  - **创建模型**: 计算来自一段文件的主题模型。 拆分文件的应用过程是在其他时间单独完成的。
    
  - **应用模型**: 仅当以前创建且尚未应用模型时, 才会显示此选项。 这将根据主题划分这些文件。
    
您还可以[设置 "忽略文本](set-ignore-text-in-advanced-ediscovery.md)" 并设置分析的[高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)。 
  
设置这些选项后, 请单击 "**分析**" 以运行。 显示 "[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)"。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[设置分析高级设置](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

