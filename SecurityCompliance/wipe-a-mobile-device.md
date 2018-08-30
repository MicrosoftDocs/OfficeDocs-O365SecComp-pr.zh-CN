---
title: Office 365 中擦除移动设备
ms.author: dianef
author: dianef77
manager: scotv
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_WipeDevice
- O365E_WipeDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 9d727c7d-8b47-4499-bf24-d046b449214c
description: 内置移动设备管理的 Office 365 可用于执行选择性擦除删除仅组织信息或完整擦除，从移动设备中删除所有信息并将其还原到出厂默认设置。
ms.openlocfilehash: d3eb28575924ca3bb4a647ae9af2f96b55116a53
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272497"
---
# <a name="wipe-a-mobile-device-in-office-365"></a>Office 365 中擦除移动设备
  
内置移动设备管理的 Office 365 可用于执行选择性擦除删除仅组织信息或完整擦除，从移动设备中删除所有信息并将其还原到出厂默认设置。
  
## <a name="what-to-know-before-you-begin"></a>开始之前应了解

- 移动设备可以存储组织的敏感信息，并提供对您的组织的 Office 365 资源的访问。为了帮助保护贵组织的信息，可以执行完整擦除或选择性擦除操作：
    
  - **完整擦除**： 删除上用户的移动设备，包括安装的应用程序、 照片和个人信息的所有数据。擦除完成后，设备还原到出厂默认设置。 
    
  - **与擦除**： 删除组织数据和离开安装应用程序、 照片和用户的移动设备上的个人信息。 
    
- 当擦除设备后 （完整擦除或选择性擦除） 时，将从托管设备的列表中删除设备。
    
- 您可以设置的移动设备管理策略，自动擦除 （完整擦除） 设备后用户多次尝试输入设备的密码特定的次数。请按照本文[创建和部署设备安全策略](create-device-security-policies.md)。
    
- 如果您想了解擦除其设备时，用户将体验，请参阅[的用户和设备的影响是什么？](wipe-a-mobile-device.md#BKMK_Impact)。
    
## <a name="wipe-a-mobile-device"></a>擦除移动设备

1. 转到[![单击此处以转到 Office 365 管理中心。](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home)。

2. 转到[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **数据丢失防护** \> **设备管理**。
    
3. 选择您想要擦除的设备。
    
4. 选择您希望执行远程擦除的类型。
    
  - 若要执行选择性擦除并删除仅 Office 365 组织信息，请在右窗格中，选择**与擦除**。
    
  - 若要执行完整擦除并将设备还原到出厂默认设置，在右侧窗格中，选择**完整擦除**。
    
![选择设备，然后选择要执行的擦除类型。](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. 选择**是**以确认。 
    
擦除完成，直到**设备状态**将显示为**RetirePending**或**RetireIssued**。
  
### <a name="how-do-i-know-it-worked"></a>如何知道它是否运行。

不再将看到的托管设备列表中的移动设备。
  
## <a name="why-would-you-want-to-wipe-a-device"></a>为什么要擦除设备？

有几个擦除设备原因：
  
- 智能手机和平板电脑等移动设备变得更加全面的所有的时间。这意味着更方便地在您的用户存储敏感的公司信息 （如个人标识或 2 私有 3 机密 communications） 并在访问它。如果这些移动设备之一的丢失或被盗，立即擦除设备可以帮助防止别人以结尾贵组织的信息。
    
- 当用户离开组织与 Office 365 中 MDM 注册个人设备时，您可以帮助防止通过执行选择性擦除转与该用户组织的信息。
    
- 如果您的组织提供给用户的移动设备，您可能需要经常将设备重新分配。执行操作之前将其分配给新用户帮助完整擦除设备上的可确保从以前的任何敏感信息，并被删除。
    
## <a name="whats-the-user-and-device-impact"></a>用户和设备影响是什么？

擦除立即发送给移动设备。设备也标记为不符合 AAD 中。
  
下表介绍时有选择地擦除设备后，内容为每种设备类型中删除。
  
|**内容的影响**|**Windows Phone 8.1**|**iOS 7.1+**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|公司门户应用程序\*卸载。  <br/> |不适用  <br/> |✔  <br/> |不适用  <br/> |
|已删除 （当前 Outlook 和 OneDrive for Business），其中访问控制支持 MDM for Office 365 的应用程序承载的 office 365 应用程序数据。不会删除应用程序。  <br/> Android 的 outlook 不会删除缓存的电子邮件。  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|设备上不再强制实施应用的 MDM for Office 365 到设备的策略设置，用户可以更改设置。  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|删除 Office 365 MDM 创建的电子邮件配置文件并删除设备上的缓存电子邮件。  <br/> |不适用  <br/> |✔  <br/> |不适用  <br/> |
   
> [!NOTE]
> \*适用于 iOS 应用程序存储和播放存储 Android 设备上提供了公司门户应用程序。 
  
## <a name="related-content"></a>相关内容

[管理 Office 365 中的移动设备](set-up-mobile-device-management.md)
  

