---
title: 管理设备注册 Office 365 中的移动设备管理
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
- MBS150
- MET150
ms.assetid: 28dd276b-beeb-4c5b-8b22-7551186127fe
description: 请按照下列步骤设置向上移动设备管理 (MDM) 在 Office 365 中。
ms.openlocfilehash: 3a84b6904b866e07eb4efabe0f39041b282d0ba9
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272307"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-office-365"></a>管理设备注册 Office 365 中的移动设备管理

内置移动设备管理 Office 365 帮助您保护和管理 iPhones、 Ipad，Androids，如用户的移动设备和 Windows 电话。第一步是登录到 Office 365 和[Office 365 MDM 设置](set-up-mobile-device-management.md)。 
  
您设置它，用户在组织中后的值必须在服务中[注册其设备](enroll-your-mobile-device.md)。然后可以使用 Office 365 MDM 来帮助管理您的组织中的设备。例如，设备安全策略可用于帮助限制访问电子邮件或其他服务、 查看设备报告和远程擦除设备。通常，您将转到[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)执行这些任务。 
  
## <a name="device-management-tasks"></a>设备管理任务

若要打开设备管理面板，请按照下列步骤。 
  
1. 转到 Office 365 管理中心。
    
2. 在搜索字段中，键入移动设备管理，并从结果列表中选择**移动设备管理**。 
    
    ![到 O365 搜索字段类型移动设备管理器](media/e2e2f1c0-e543-431a-959b-e26c2ba328a7.png)
  
MDM for Office 365 设置之后，下面是如何在组织中管理移动设备。 
  
|**若要执行此操作...**|**执行操作**|
|:-----|:-----|
|擦除设备  <br/> |在设备管理面板中，选择*设备名称*，然后**完全擦除**删除所有的信息或**与擦除**删除设备上仅组织的信息。  <br/> 请参阅[擦除 Office 365 中的设备](wipe-a-mobile-device.md)。  <br/> |
|阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件  <br/> |在设备管理面板中，选择**阻止**。  <br/> |
|设置设备策略，如密码要求和安全设置  <br/> |在设备管理面板中，单击\>**设备安全策略** \> **添加 +**。  <br/> 请参阅[创建和部署设备安全策略](create-device-security-policies.md)。  <br/> |
|查看阻止的设备列表  <br/> |在设备管理面板中，在**选择视图**下选择**已阻止**。  <br/> ||
|解除阻止单个用户或一组用户的不相容或不受支持的设备  <br/> | 根据您的情况，可以取消阻止不符合标准的设备几种方法。选择下列选项之一：<br/>  策略已应用于的安全组中移除的用户。转到**Office 365 管理中心** \> **组**，然后选择 * 组名称 *。单击**编辑成员和管理员**。<br/>  删除安全组用户是设备策略中的成员。转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。选择 * 设备策略名称 *，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **部署**。<br/>  取消阻止设备策略的所有不符合标准的设备。转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。选择*设备策略名称*，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **访问要求**。选择**允许访问和报告的冲突**。<br/>  若要取消阻止不符合标准或不受支持设备的用户或一组用户，请转到转到**安全&amp;合规性中心**\> **安全策略** \> **设备管理** \> **管理设备访问设置**.添加安全组与成员您想要排除要阻止对 Office 365 的访问。请参阅[创建、 编辑或删除 Office 365 管理中心中的安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/> |
|您的组织中获取有关设备的详细信息  <br/> |要获得例如，哪些设备是注册，并且符合设备安全策略的详细信息，请按照[获得有关由 MDM 管理的设备的详细信息](get-details-about-mdm-managed-devices.md)中列出的步骤。  <br/> |
|删除用户，以便其设备不再由 MDM  <br/> |编辑具有 MDM 要删除用户的设备管理策略的安全组。请参阅[创建、 编辑或删除 Office 365 管理中心中的安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。<br/> 若要删除所有 Office 365 用户 MDM，请参阅[关闭 Office 365 中的移动设备管理](turn-off-mdm.md)。  <br/> |
   

