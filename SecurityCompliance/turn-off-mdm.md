---
title: 如何关闭 Office 365 中的移动设备管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: 按照以下步骤停止从移动设备 Office 365 组织中强制实施 MDM 策略。
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272217"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a>如何关闭 Office 365 中的移动设备管理

若要有效地关闭 MDM 的 Office 365，您 （由安全组定义） 的人员组移除设备管理策略，或删除他们自己的策略。 
  
- 从您已创建的设备策略中删除用户安全组中删除用户的组。 
    
- 让每个人的 MDM 禁用中删除所有 MDM 设备策略。 
    
这些选项将您的组织中删除设备 MDM 实施。遗憾的是，您不能只是"取消设置"MDM for Office 365 后已设置。
  
> [!IMPORTANT]
> 当您从策略中删除用户安全组或删除他们自己的策略，则应注意对用户的设备的影响。例如，电子邮件配置文件和缓存的电子邮件可能被删除，具体取决于该设备。请参阅：[不同类型的设备上的安全策略的影响是什么？](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a>从 MDM 设备策略中删除用户安全组

1. 转到**安全&amp;合规性中心**\> **数据丢失防护** \> **设备安全策略**。
    
2. 选择设备策略，然后单击![编辑图标](media/O365-MDM-CreatePolicy-EditIcon.gif)**编辑策略**。
    
3. 在**部署**中，单击 **-删除**。
    
    在**组**下选择安全组。
    
4.  单击"移除"。
    
5. 单击“保存”****。
    
## <a name="remove-mdm-device-policies"></a>删除 MDM 设备策略

1. 转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。
    
2. 选择设备策略，，然后单击![的回收站图像可以图标。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **删除策略**。
    
3. 在**警告**对话框中，单击**是**。 
    

