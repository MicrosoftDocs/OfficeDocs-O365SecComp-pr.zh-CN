---
title: 在 Office 365 高级电子数据展示中设置分析高级设置
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: '了解如何为 Office 365 高级电子数据展示中的分析过程配置高级设置, 包括接近重复的电子邮件线程和主题。 '
ms.openlocfilehash: d8dfb9f3ecfcda0f267dfccdc716eda40fe450b2
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260852"
---
# <a name="set-analyze-advanced-settings-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中设置分析高级设置

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
高级电子数据展示可提供分析模块设置的默认高级参数。 下面的过程介绍了可指定的设置。
  
1. 在 "**准备\>分析\>设置**" 选项卡上, 单击页面底部的 "**高级设置**"。 将显示以下面板。 
    
    ![设置分析高级设置](media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. 在 "**临近副本" 和 "电子邮件线程" 参数**中, 根据需要选择以下值:
    
  - **最小单词数**: 单词的最小数目, 在以下情况下, 不会将文件提交到接近重复的分析。 
    
  - **最大单词数**: 单词的最大数目, 超过该数目时不会将文件提交到接近重复的分析。
    
  - **电子邮件相似性**: 将两封电子邮件视为相似的最小 resemblance 级别。 值始终等于或大于文档相似性。 默认值为 90%。
    
3. 在 "**主题参数**" 中, 选中 "将**数字包含在主题分析**中" 复选框, 以在分析期间包含处理主题过程中的数字。 
    
4. 单击“保存”****。 
    
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[了解文档相似性](understand-document-similarity-in-advanced-ediscovery.md)
  
[设置分析选项](set-analyze-options-in-advanced-ediscovery.md)
  
[设置忽略文本](set-ignore-text-in-advanced-ediscovery.md)
  
[查看分析结果](view-analyze-results-in-advanced-ediscovery.md)

