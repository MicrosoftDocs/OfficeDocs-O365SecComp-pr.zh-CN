---
title: 创建 iOS 设备 APNs 证书
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: 若要管理 Office 365 的 iOS 设备，如 iPad 和 Iphone 移动设备管理中的，按照以下步骤可先创建 APNs 证书。
ms.openlocfilehash: 28e8888d7dd57c3052cdcb5994725f11a5f0445f
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272047"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>创建 iOS 设备 APNs 证书

 若要管理的 Office 365 的 iOS 设备，例如 iPad 和 Iphone 在移动设备管理必须创建 APNs 证书。 
  
为此，请在门户页面上的**设置**链接从按照的步骤。(请转到**安全&amp;合规性中心** \> **安全策略** \> **设备管理** \> **管理设置**。)
  
![设置建议的步骤和所需的移动设备管理](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. 旁边**配置 iOS 设备 APNs 证书**，选择**设置**。
    
2. 选择**下载 CSR 文件**并保存到这二者的证书签名请求将请记住在计算机上。 
    
    ![安装 APN 证书对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. 选择**下一步**。
    
4. 创建 APN 证书。
    
  - 选择以打开 Apple 推送证书门户**Apple APNS 门户**。 
    
    ![使用 Apple APNS 门户选择安装 APN 通知证书对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - 登录 Apple id。
    
    > [!IMPORTANT]
    > 使用 Apple ID 与即使管理帐户的用户离开将保持与您的组织的电子邮件帐户关联的公司。保存此 ID，因为您需要在需要时续订证书使用相同的 ID。 
  
  - 选择**创建的证书**，并接受**使用条款**。
    
  - **浏览**证书签名请求从 Office 365 下载到您的计算机，并选择**上载**。
    
  - **下载**APN 证书创建 Apple 推送证书门户到您的计算机。 
    
    > [!TIP]
    > 如果您在遇到问题下载证书，请刷新浏览器。 
  
5. 返回到 Office 365，并选择**下一步**，转到**上载 APNS 证书**页。 
    
6. 浏览到从 Apple 推送证书门户下载 APN 证书。
    
    ![单击浏览按钮以选择 APNS cert 从 Apple 下载](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 选择**完成**。
    
转到**安全&amp;合规性中心** \> **安全策略** \> **设备管理** \> **管理设置**以完成安装。 
  

