---
title: 移动设备管理 (MDM) for Office 365 概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365M_MDMConfigDomains
- O365E_MDMConfigDomains
- ms.o365.cc.DevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: faa7d8e5-645d-4d59-839c-c8d4c1869e4a
description: 您可以管理和安全的移动设备，当他们使用移动设备管理 Office 365 连接到 Office 365 组织。移动设备，如智能手机和平板电脑的用于访问工作电子邮件、 日历、 联系人和文档播放中确保员工获取完成随时随地从任何地方工作的重要部分。因此，很重要，帮助保护贵组织的信息的人员使用设备时。设置设备安全策略和访问规则，以及他们正在丢失或被盗擦除移动设备，可以使用 Office 365 MDM。
ms.openlocfilehash: f06cef11b68ee0673f13c54738f07f4556495fdd
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272487"
---
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a>移动设备管理 (MDM) for Office 365 概述

您可以管理和安全的移动设备，当他们使用移动设备管理 Office 365 连接到 Office 365 组织。移动设备，如智能手机和平板电脑的用于访问工作电子邮件、 日历、 联系人和文档播放中确保员工获取完成随时随地从任何地方工作的重要部分。因此，很重要，帮助保护贵组织的信息的人员使用设备时。设置设备安全策略和访问规则，以及他们正在丢失或被盗擦除移动设备，可以使用 Office 365 MDM。
  
![在 android 移动电话上 MDM](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a>您可以管理哪些类型的设备？

Office 365 MDM 可用于管理移动设备，如 Windows Phone、 Android、 iPhone 和 iPad 的许多类型。若要管理移动设备使用您的组织中的人员，每个人必须具有适用的 Office 365 许可证，并且其设备必须在 MDM 注册 Office 365。 
  
若要查看每个类型的设备支持的 Office 365 MDM，请参阅[功能的移动设备管理 Office 365](capabilities-of-mobile-device-management.md)。
  
## <a name="setup-steps-for-mdm"></a>MDM 的安装步骤

Office 365 全局管理员必须完成以下步骤来激活并针对 Office 365 设置 MDM。按照上[设置 MDM Office 365 的](set-up-mobile-device-management.md)详细的步骤，请参阅主题中的指南。下面是快速汇总： 
  
> 步骤 1： 针对 Office 365 激活 MDM 按照中[设置向上移动设备管理 (MDM) 在 Office 365 中](set-up-mobile-device-management.md)的步骤。
    
> 步骤 2： 设置 MDM for Office 365 的例如，创建用于管理 iOS 设备的 APNs 证书并添加您的域，以支持 Windows phone 的域名系统 (DNS) 记录。
    
> 步骤 3： 创建设备策略，并将它们应用于的用户组。时执行此操作时，用户将收到[注册消息在其设备上](enroll-your-mobile-device.md)。和它们已完成注册，其设备将受限制的已为其设置的策略。
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a>设备管理任务

Office 365 设置了 MDM 和您的用户已注册其设备后，可以管理设备、 阻止访问，或需要擦除的设备。了解有关[一些常见的设备管理任务](manage-devices-in-mdm.md)，包括完成任务的位置。
  
## <a name="other-ways-to-manage-devices-and-apps"></a>管理设备和应用程序的其他方法

如果您需要更多比 MDM for Office 365 的功能包括、 签出此[MDM 和 Microsoft Intune 功能的比较](choose-between-mdm-and-intune.md)，以查看是否 Intune 订阅将符合贵组织的需求。 
  
如果您只需移动应用程序管理 (MAM)，有可能是更新自己的设备上工作项目的人员 Intune 将提供除了注册和管理设备的另一个选项。Intune 订阅允许您设置 MAM 策略通过使用 Azure 门户，即使不会加入 Intune 人的设备。请参阅[使用 MAM 策略保护应用程序数据](https://go.microsoft.com/fwlink/?LinkId=825439)。 
  
## <a name="see-also"></a>另请参阅

[获取有关由 MDM 管理的设备的详细信息](get-details-about-mdm-managed-devices.md)

[针对 Office 365 设置 MDM](set-up-mobile-device-management.md)
  
[注册 MDM 中的移动设备](enroll-your-mobile-device.md)
  
[管理设备报名参加 MDM](manage-devices-in-mdm.md)

