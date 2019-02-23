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
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="9947f-103">为 iOS 设备创建 APNs 证书</span><span class="sxs-lookup"><span data-stu-id="9947f-103">Create an APNs Certificate for iOS devices</span></span>

 <span data-ttu-id="9947f-104">若要在移动设备管理 for Office 365 中管理 iPad 设备 (如 iPad 和 iphone), 必须创建 APNs 证书。</span><span class="sxs-lookup"><span data-stu-id="9947f-104">To manage iOS devices like iPad and iPhones in Mobile Device Management for Office 365 you must create an APNs certificate.</span></span> 
  
<span data-ttu-id="9947f-p101">若要执行此操作, 请按照 "门户" 页面上的 "**设置**" 链接中的步骤操作。(转到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**。)</span><span class="sxs-lookup"><span data-stu-id="9947f-p101">To do this, follow the steps from the **Set up** link on the portal page. (Go to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings**.)</span></span>
  
![设置所需的移动设备管理和推荐步骤](media/d71e3c76-b6b9-4549-ade6-cbfab846d908.png)
  
1. <span data-ttu-id="9947f-108">在 "为**iOS 设备配置 APNs 证书**" 旁边, 选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="9947f-108">Next to **Configure a APNs Certificate for iOS devices**, select **Set up**.</span></span>
    
2. <span data-ttu-id="9947f-109">选择 "**下载你的 CSR 文件**", 并将证书签名请求保存到计算机上你将记住的位置。</span><span class="sxs-lookup"><span data-stu-id="9947f-109">Select **Download your CSR file** and save the Certificate signing request to a somewhere on your computer that you'll remember.</span></span> 
    
    !["安装 APN 证书" 对话框](media/03aa8a24-e95c-4077-9b6b-ef76a86bafd7.png)
  
3. <span data-ttu-id="9947f-111">选择" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9947f-111">Select **Next**.</span></span>
    
4. <span data-ttu-id="9947f-112">创建接入点证书。</span><span class="sxs-lookup"><span data-stu-id="9947f-112">Create an APN certificate.</span></span>
    
  - <span data-ttu-id="9947f-113">选择 " **apple APNS 门户**" 打开 "apple 推送证书" 门户。</span><span class="sxs-lookup"><span data-stu-id="9947f-113">Select **Apple APNS Portal** to open the Apple Push Certificates Portal.</span></span> 
    
    ![选择 Apple APNS 门户的 "安装 APN 通知证书" 对话框](media/ce19f53c-f44a-470b-baf3-9278dfda2ba5.png)
  
  - <span data-ttu-id="9947f-115">使用 Apple ID 登录。</span><span class="sxs-lookup"><span data-stu-id="9947f-115">Sign in with an Apple ID.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9947f-p102">使用与电子邮件帐户关联的公司 Apple ID, 即使管理帐户的用户离开, 也将保留在组织中。保存此 id, 因为在需要续订证书时, 您需要使用相同的 id。</span><span class="sxs-lookup"><span data-stu-id="9947f-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span> 
  
  - <span data-ttu-id="9947f-118">选择 "**创建证书**" 并接受 "**使用条款**"。</span><span class="sxs-lookup"><span data-stu-id="9947f-118">Select **Create a Certificate** and accept the **Terms of Use**.</span></span>
    
  - <span data-ttu-id="9947f-119">**浏览**到从 Office 365 下载到您的计算机的证书签名请求, 然后选择 "**上传**"。</span><span class="sxs-lookup"><span data-stu-id="9947f-119">**Browse** to the Certificate signing request you downloaded to your computer from Office 365 and select **Upload**.</span></span>
    
  - <span data-ttu-id="9947f-120">将 Apple 推送证书门户创建的 APN 证书**下载**到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="9947f-120">**Download** the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="9947f-121">如果您在下载证书时遇到问题, 请刷新浏览器。</span><span class="sxs-lookup"><span data-stu-id="9947f-121">If you're having trouble downloading the certificate, refresh your browser.</span></span> 
  
5. <span data-ttu-id="9947f-122">返回到 Office 365, 然后选择 "**下一步**" 以转到 "**上载 APNS 证书**" 页面。</span><span class="sxs-lookup"><span data-stu-id="9947f-122">Go back to Office 365 and select **Next** to get to the **Upload APNS certificate** page.</span></span> 
    
6. <span data-ttu-id="9947f-123">浏览到从 Apple 推送证书门户下载的 APN 证书。</span><span class="sxs-lookup"><span data-stu-id="9947f-123">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>
    
    ![单击 "浏览" 按钮以选择从 Apple 下载的 APNS 证书](media/afe2849d-af23-4c55-9009-d8f25edaf6c0.png)
  
7. <span data-ttu-id="9947f-125">选择 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="9947f-125">Select **Finish**.</span></span>
    
<span data-ttu-id="9947f-126">返回到**安全&amp;合规中心** \> **安全策略** \> **设备管理** \> **管理设置**以完成安装。</span><span class="sxs-lookup"><span data-stu-id="9947f-126">Go back to **Security &amp; Compliance Center** \> **Security policies** \> **Device management** \> **Manage settings** to complete setup.</span></span> 
  

