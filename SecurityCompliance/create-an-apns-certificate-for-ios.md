---
title: 为 iOS 设备创建 APNs 证书
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365M_APNCertMDM
- O365E_APNCertMDM
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 522b43f4-a2ff-46f6-962a-dd4f47e546a7
description: 若要在移动设备管理中管理 Office 365 的 iOS 设备 (如 iPad 和 iphone), 请按照以下步骤操作, 以首次创建 APNs 证书。
ms.openlocfilehash: 5f82690f0add5f1aae95a089d9cdfc0b320ae596
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220452"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>为 iOS 设备创建 APNs 证书

 若要在移动设备管理 for Office 365 中管理 iPad 设备 (如 iPad 和 iphone), 必须创建 APNs 证书。 
  
若要执行此操作, 请按照 "门户" 页面上的 "**设置**" 链接中的步骤操作。(转到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**。)
  
![设置所需的移动设备管理和推荐步骤](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. 在 "为**iOS 设备配置 APNs 证书**" 旁边, 选择 "**设置**"。
    
2. 选择 "**下载你的 CSR 文件**", 并将证书签名请求保存到计算机上你将记住的位置。 
    
    !["安装 APN 证书" 对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. 选择" **下一步**"。
    
4. 创建接入点证书。
    
  - 选择 " **apple APNS 门户**" 打开 "apple 推送证书" 门户。 
    
    ![选择 Apple APNS 门户的 "安装 APN 通知证书" 对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - 使用 Apple ID 登录。
    
    > [!IMPORTANT]
    > 使用与电子邮件帐户关联的公司 Apple ID, 即使管理帐户的用户离开, 也将保留在组织中。保存此 id, 因为在需要续订证书时, 您需要使用相同的 id。 
  
  - 选择 "**创建证书**" 并接受 "**使用条款**"。
    
  - **浏览**到从 Office 365 下载到您的计算机的证书签名请求, 然后选择 "**上传**"。
    
  - 将 Apple 推送证书门户创建的 APN 证书**下载**到您的计算机。 
    
    > [!TIP]
    > 如果您在下载证书时遇到问题, 请刷新浏览器。 
  
5. 返回到 Office 365, 然后选择 "**下一步**" 以转到 "**上载 APNS 证书**" 页面。 
    
6. 浏览到从 Apple 推送证书门户下载的 APN 证书。
    
    ![单击 "浏览" 按钮以选择从 Apple 下载的 APNS 证书](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 选择 "**完成**"。
    
返回到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**以完成安装。 
  

