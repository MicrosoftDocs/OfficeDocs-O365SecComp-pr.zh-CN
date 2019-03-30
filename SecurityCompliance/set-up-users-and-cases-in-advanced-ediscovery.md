---
title: 在 Office 365 高级电子数据展示中设置用户和案例
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
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: '了解如何配置用户角色、创建案例, 以及如何将用户分配到 Office 365 高级电子数据展示中的案例。  '
ms.openlocfilehash: 5a22e0683e49ebdaf8391e092aeb101386e0636b
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999265"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>在 Office 365 高级电子数据展示中设置用户和案例

本主题介绍如何为 Office 365 高级电子数据展示设置用户和案例。
  
> [!NOTE]
> 若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
## <a name="prerequisites"></a>先决条件

在高级电子数据展示中设置事例和用户之前, 需要满足以下条件:
  
- 若要使用高级电子数据展示分析用户的数据, 必须为用户 (数据管理员) 分配 Office 365 E5 许可证。 或者, 可以为具有 Office 365 E1 或 E3 许可证的用户分配高级电子数据展示独立许可证。 分配给案例并使用高级电子数据展示分析数据的管理员和合规性监察官不需要 E5 许可证。 
    
- 您必须是 Office 365 安全&amp;合规中心中的电子数据展示管理器角色组的成员, 才能创建电子数据展示事例并向其添加成员。 若要将自己添加到安全&amp;合规中心中的电子数据展示管理器角色组, 您必须是 Office 365 组织中的全局管理员。 如果您不是全局管理员, 则必须要求全局管理员将您添加到电子数据展示管理器角色组。 有关详细信息，请参阅：
    
  - [Microsoft 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)
    
  - [在 Microsoft 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>步骤 1: 为用户分配电子数据展示权限

第一步是为用户分配安全&amp;合规性中心中的要求权限, 以便可以将其添加为电子数据展示事例的成员。 在安全&amp;合规中心中将用户添加为案例的成员后, 他们将能够在高级电子数据展示中访问此案例。
  
若要向用户分配必要的权限, 以便可以将其添加为电子数据展示事例的成员, 请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)中的第1步。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>步骤 2: 创建电子数据展示事例并添加成员

下一步是在安全&amp;合规中心中创建新的电子数据展示事例并添加成员。 然后, 这种情况的成员将能够访问高级电子数据展示中的案例。
  
1. 若要创建新的电子数据展示事例, 请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-2-create-a-new-case)步骤2。
    
2. 若要将成员添加到电子数据展示事例, 请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-3-add-members-to-a-case)步骤3
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>步骤 3: 在高级电子数据展示中进行案例

创建电子数据展示事例并添加成员后, 您 (或任何情况的成员) 可以在高级电子数据展示中访问相应的事例。 若要在高级电子数据展示中访问事例, 请参阅[Microsoft 365 安全&amp;合规性中心中的电子数据展示事例中的](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)第8步。
  
## <a name="see-also"></a>另请参阅

[Office 365 高级电子数据展示](office-365-advanced-ediscovery.md)
  
[准备数据](prepare-data-for-advanced-ediscovery.md)
 