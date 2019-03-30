---
title: 定义问题并在 Office 365 高级电子数据展示中分配用户
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
ms.assetid: 48d37ee7-05bd-4cb8-9723-a8959ad23fbe
description: 了解如何在 Office 365 高级电子数据展示中添加或编辑问题, 包括向用户分配用户或删除电子数据展示事例的问题。
ms.openlocfilehash: 80ea6e2579b8bc68b70e2181d9c986c91c890836
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000635"
---
# <a name="define-issues-and-assign-users-in-office-365-advanced-ediscovery"></a>定义问题并在 Office 365 高级电子数据展示中分配用户

> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
在高级电子数据展示中, 可以在一个事例中定义一个或多个问题。 定义问题允许对主题进行进一步的分类。 在连接到新事例时, 将提供一个默认问题。 您可以编辑默认问题名称并将用户分配给问题。 
  
## <a name="adding-or-editing-an-issue-and-assigning-users"></a>添加或编辑问题并为用户分配

1. 在 "**相关性\>关联设置**" \>选项卡中, 选择 "**问题**"。
    
    ![相关性设置问题](media/dfd8f9ef-b167-4ed9-980e-00ae98a97169.png)
  
2. 若要添加问题, 请单击 * * + * * 图标。 将显示 "**添加问题**" 对话框。 
    
    ![相关性设置添加问题](media/c8e94982-139a-472a-b85d-282f2d742046.png)
  
    若要编辑问题, 请单击 "**编辑**" 图标。 
    
3. 在 "**问题名称**" 中, 键入对事例具有描述性和意义的名称。 
    
4. 在 "**说明**" 中, 键入有关问题的信息。
    
5. 选中 "**启用并发培训**" 复选框以启用该选项。 此设置允许多个审阅者同时处理同一问题 (分在单独的示例中)。 
    
6. 在 "**为用户分配问题**" 中的 "**所有用户**" 列表中, 选择要分配给该问题的用户, 然后单击向右箭头以将用户添加到 "**选定的用户**" 列表。 根据需要重复此操作。 在上面显示的窗口中, "Admin" 显示为选定的用户。 
    
    > [!NOTE]
    > 可以在相关培训周期前后修改对问题的用户分配。 
  
7. 在 "**所选用户**" 中, 从所选用户的名称旁边的下拉列表中, 选择以下采样模式之一: 
    
  - **打开**: 可以查看和标记这些文件。 这是默认设置。
    
  - **空闲**: 可以查看文件;"标记" 是可选的。
    
  - **Off**: 无法查看或标记文件。
    
8. 添加完问题后, 单击 **"确定"**。
    
## <a name="deleting-issues"></a>删除问题

仅在定义问题后立即将其删除 (即从数据库中删除), 并且不会对该问题执行任何实际工作。 
  
1. 在 "**相关性\>关联设置**" 选项卡中, 选择 "**问题**"。
    
2. 选择要从数据库中删除的问题, 然后单击 "**删除**"。
    
3. 将显示一条确认消息。 单击"是"以确认。 
    
4. 单击“确定”****。
    
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[设置将已导入文件添加到的负载](set-up-loads-to-add-imported-files.md)
  
[定义突出显示的关键字和高级选项](define-highlighted-keywords-and-advanced-options.md)

