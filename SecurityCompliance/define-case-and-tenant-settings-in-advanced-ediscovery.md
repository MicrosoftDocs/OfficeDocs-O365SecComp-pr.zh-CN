---
title: 在 Office 365 高级电子数据展示中定义大小写和租户设置
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: '了解您可以在 Office 365 高级电子数据展示中的事例级别定义的标签、跨模块和租户设置。  '
ms.openlocfilehash: 2e95984651bf4da86bd64cfc3730fae75391410d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256910"
---
# <a name="define-case-and-tenant-settings-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中定义大小写和租户设置

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
本主题中介绍了高级电子数据展示事例和租户设置。
  
## <a name="case-settings"></a>大小写设置

本部分介绍可在事例级别定义的设置。
  
> [!NOTE]
> 如果当前未在高级电子数据展示中选择任何事例, 则 "**事例设置**" 选项卡将处于非活动状态。 
  
### <a name="cross-module"></a>跨模块

以下跨模块设置是应用于高级电子数据展示模块的大小写选项。
  
- 登录后的默认页面: 设置在启动高级电子数据展示时显示的默认页面。
    
- 文件显示名称: 将在整个高级电子数据展示中显示文件的文件标识符, 以标识文件标题/路径或电子邮件主题的高级电子数据展示显示名称的替代方法。
    
1. 通过单击 " **Cogwheel** " 图标打开 "**设置和实用工具**"。 打开 "**设置和\>实用程序机箱设置**" 选项卡\> **跨模块**。 
    
2. 从 "**登录后的默认页面**" 选项中进行选择: 
    
  - **上次登录的最后一页**
    
  - **事例页**
    
3. 单击“**保存**”。
    
## <a name="tenant-settings"></a>租户设置

此部分介绍了高级电子数据展示租户设置。
  
### <a name="user-administration"></a>用户管理

"用户管理" 选项在[设置用户和案例](set-up-users-and-cases-in-advanced-ediscovery.md)中进行说明。
  
### <a name="event-log"></a>事件日志

在高级电子数据展示操作过程中, 事件日志提供了有关高级电子数据展示处理的元数据。 例如, 它包括主要高级电子数据展示过程 (导入、分析、相关性和导出) 的开始时间以及结束时间和状态。 此日志可用于跟踪和解决数据处理活动, 并用于解决错误和警告。
  
1. 通过单击 " **Cogwheel** " 图标打开 "**设置和实用工具**"。 
    
2. 在 "**设置和实用工具\>租户设置**" 选项卡中, 选择 "**事件日志**"。 显示事件日志数据。
    
  - 若要按事例筛选日志输出, 请从 "**事例**" 列表中选择事例。 
    
  - 若要按列对日志进行排序, 请单击列标题。 
    
  - 若要修改列顺序, 请单击并拖动列标题。
    
  - 若要在日志页面之间移动**\>** , **\<** 请单击 "" 和 "图标"。 
    
### <a name="system-information"></a>系统信息

高级电子数据展示版本系统信息和活动任务显示在 "租户设置" 选项卡中。
  
1. 通过单击 " **Cogwheel** " 图标打开 "**设置和实用工具**"。 
    
2. 在 "**设置和实用工具\>租户设置**" 选项卡中, 选择 "**系统信息**"。 将显示版本信息。
    
可以通过单击租户信息下方的 "**刷新**" 图标来更新显示。 
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[使用实用程序](use-advanced-ediscovery-utilities.md)

