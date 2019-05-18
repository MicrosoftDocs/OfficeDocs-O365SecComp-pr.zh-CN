---
title: 为 iOS 设备创建 APNs 证书
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 8/5/2016
audience: Admin
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
description: 若要在移动设备管理中管理 Office 365 的 iOS 设备 (如 iPad 和 Iphone), 请按照以下步骤操作, 以首次创建 APNs 证书。
ms.openlocfilehash: 17dae3e02520cdac2b1381039844d1657b12c4eb
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153754"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>为 iOS 设备创建 APNs 证书

 若要在移动设备管理 for Office 365 中管理 iPad 设备 (如 iPad 和 Iphone), 必须创建 APNs 证书。 
  
若要执行此操作, 请按照 "门户" 页面上的 "**设置**" 链接中的步骤操作。 (转到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**。)
  
![设置所需的移动设备管理和推荐步骤](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.
    
2. Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember. 
    
    !["安装 APN 证书" 对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3.  Select **Next**. 
    
4.  Create an APN certificate.
    
  - Select **Apple APNS Portal** to open the Apple Push Certificates Portal.  
    
    ![选择 Apple APNS 门户的 "安装 APN 通知证书" 对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - Sign in with an Apple ID.
    
    > [!IMPORTANT]
    > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate. 
  
  - Select **Create a Certificate** and accept the **Terms of Use**.
    
  - **Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.
    
  - **Download** the APN certificate created by the Apple Push Certificate Portal to your computer. 
    
    > [!TIP]
    > If you're having trouble downloading the certificate, refresh your browser. 
  
5. Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page. 
    
6.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
    ![单击 "浏览" 按钮以选择从 Apple 下载的 APNS 证书](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. 选择“完成”****。
    
返回到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**以完成安装。 
  

