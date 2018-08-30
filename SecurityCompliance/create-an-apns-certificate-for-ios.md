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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="98807-103">创建 iOS 设备 APNs 证书</span><span class="sxs-lookup"><span data-stu-id="98807-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="98807-104">若要管理的 Office 365 的 iOS 设备，例如 iPad 和 Iphone 在移动设备管理必须创建 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="98807-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="98807-p101">为此，请在门户页面上的**设置**链接从按照的步骤。(请转到**安全&amp;合规性中心** \> **安全策略** \> **设备管理** \> **管理设置**。)</span><span class="sxs-lookup"><span data-stu-id="98807-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![设置建议的步骤和所需的移动设备管理](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="98807-108">旁边**配置 iOS 设备 APNs 证书**，选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="98807-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="98807-109">选择**下载 CSR 文件**并保存到这二者的证书签名请求将请记住在计算机上。</span><span class="sxs-lookup"><span data-stu-id="98807-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    ![安装 APN 证书对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="98807-111">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="98807-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="98807-112">创建 APN 证书。</span><span class="sxs-lookup"><span data-stu-id="98807-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="98807-113">选择以打开 Apple 推送证书门户**Apple APNS 门户**。</span><span class="sxs-lookup"><span data-stu-id="98807-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![使用 Apple APNS 门户选择安装 APN 通知证书对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="98807-115">登录 Apple id。</span><span class="sxs-lookup"><span data-stu-id="98807-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="98807-p102">使用 Apple ID 与即使管理帐户的用户离开将保持与您的组织的电子邮件帐户关联的公司。保存此 ID，因为您需要在需要时续订证书使用相同的 ID。</span><span class="sxs-lookup"><span data-stu-id="98807-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="98807-118">选择**创建的证书**，并接受**使用条款**。</span><span class="sxs-lookup"><span data-stu-id="98807-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="98807-119">**浏览**证书签名请求从 Office 365 下载到您的计算机，并选择**上载**。</span><span class="sxs-lookup"><span data-stu-id="98807-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="98807-120">**下载**APN 证书创建 Apple 推送证书门户到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="98807-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="98807-121">如果您在遇到问题下载证书，请刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="98807-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="98807-122">返回到 Office 365，并选择**下一步**，转到**上载 APNS 证书**页。</span><span class="sxs-lookup"><span data-stu-id="98807-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="98807-123">浏览到从 Apple 推送证书门户下载 APN 证书。</span><span class="sxs-lookup"><span data-stu-id="98807-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![单击浏览按钮以选择 APNS cert 从 Apple 下载](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="98807-125">选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="98807-125">Select **Finish**.</span></span>
    
<span data-ttu-id="98807-126">转到**安全&amp;合规性中心** \> **安全策略** \> **设备管理** \> **管理设置**以完成安装。</span><span class="sxs-lookup"><span data-stu-id="98807-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

