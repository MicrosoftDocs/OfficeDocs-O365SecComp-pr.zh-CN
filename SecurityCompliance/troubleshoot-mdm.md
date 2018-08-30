---
title: 排查设备注册 MDM 与 Office 365
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/17/2015
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: c863b2bf-45f3-483a-ba05-29fc7f4d6434
description: 如果您运行到问题，当您尝试 Office 365 中注册的设备中移动设备管理 (MDM) 时，尝试以跟踪问题此处列出的步骤。如果的常规步骤不解决问题，请参阅更高版本部分使用您的设备类型的特定步骤之一。
ms.openlocfilehash: 490259fc623b38ab5ad6cf8553c5074c77b77426
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272107"
---
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a>排查设备注册 MDM 与 Office 365

如果您运行到问题，当您尝试 Office 365 中注册的设备中移动设备管理 (MDM) 时，尝试以跟踪问题此处列出的步骤。如果的常规步骤不解决问题，请参阅更高版本部分使用您的设备类型的特定步骤之一。
  
## <a name="steps-to-try-first"></a>尝试首先步骤

要开始，请检查以下项目：
  
- 请确保，设备不已经注册了其他移动设备管理提供程序，如 Intune。
    
- 请确保设备设置为正确的日期和时间。
    
- 切换到不同 Wi-fi 或移动设备上的网络。
    
- Android 或 iOS 设备，卸载并重新 Intune 的公司门户应用程序安装在设备上。
    
## <a name="ios-phone-or-tablet"></a>iOS 电话或平板电脑

- 请确保您已[设置 APNs 证书](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)。
    
- 在**设置** \> **常规** \> **配置文件**（或**设备管理**），请确保不已安装的**管理配置文件**。如果是，则将其删除。 
    
- 如果您看到错误消息，"设备无法注册，"登录到 Office 365，并确保许可证，其中包括 Exchange Online 的已分配给的用户的登录到设备。
    
- 如果您看到错误消息，"配置文件安装失败，"尝试下列选项之一：
    
  - 确保 Safari 默认浏览器在设备上，且未禁用 cookie。
    
  - 重新启动设备，然后导航到 portal.manage.microsoft.com、 登录您的 Office 365 用户 ID 和密码，并尝试手动安装配置文件。
    
## <a name="windows-rt-tablet"></a>Windows RT 平板电脑

- 请确保您的域[以使用 MDM 的 Office 365 中设置](set-up-mobile-device-management.md)。
    
- 确保用户已选择**打开**而不是选择**加入**。
    
## <a name="windows-phone"></a>Windows Phone

- 请确保您的域[以使用 MDM 的 Office 365 中设置](set-up-mobile-device-management.md)。
    
- 请确保设备正在运行 Windows 8.1，或更高版本。
    
## <a name="android-phone-or-tablet"></a>Android 移动电话或平板电脑

- 确保设备运行 Android 4.0 或更高版本。
    
- 如果您看到错误消息，"我们无法注册该设备，"登录到 Office 365，并确保许可证，其中包括 Exchange Online 的已分配给的用户的登录到设备。
    
- 检查上的**通知区域**设备有任何必需的最终用户操作挂起，并时，完成操作。 
    

