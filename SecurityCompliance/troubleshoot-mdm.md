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
# <a name="troubleshoot-device-enrollment-with-mdm-for-office-365"></a><span data-ttu-id="1777c-104">排查设备注册 MDM 与 Office 365</span><span class="sxs-lookup"><span data-stu-id="1777c-104">Troubleshoot device enrollment with MDM for Office 365</span></span>

<span data-ttu-id="1777c-p102">如果您运行到问题，当您尝试 Office 365 中注册的设备中移动设备管理 (MDM) 时，尝试以跟踪问题此处列出的步骤。如果的常规步骤不解决问题，请参阅更高版本部分使用您的设备类型的特定步骤之一。</span><span class="sxs-lookup"><span data-stu-id="1777c-p102">If you're running into issues when you try to enroll a device in Mobile Device Management (MDM) for Office 365, try the steps listed here to track down the problem. If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>
  
## <a name="steps-to-try-first"></a><span data-ttu-id="1777c-107">尝试首先步骤</span><span class="sxs-lookup"><span data-stu-id="1777c-107">Steps to try first</span></span>

<span data-ttu-id="1777c-108">要开始，请检查以下项目：</span><span class="sxs-lookup"><span data-stu-id="1777c-108">To start, check the following:</span></span>
  
- <span data-ttu-id="1777c-109">请确保，设备不已经注册了其他移动设备管理提供程序，如 Intune。</span><span class="sxs-lookup"><span data-stu-id="1777c-109">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="1777c-110">请确保设备设置为正确的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1777c-110">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="1777c-111">切换到不同 Wi-fi 或移动设备上的网络。</span><span class="sxs-lookup"><span data-stu-id="1777c-111">Switch to a different Wi-Fi or cellular network on the device.</span></span>
    
- <span data-ttu-id="1777c-112">Android 或 iOS 设备，卸载并重新 Intune 的公司门户应用程序安装在设备上。</span><span class="sxs-lookup"><span data-stu-id="1777c-112">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span>
    
## <a name="ios-phone-or-tablet"></a><span data-ttu-id="1777c-113">iOS 电话或平板电脑</span><span class="sxs-lookup"><span data-stu-id="1777c-113">iOS phone or tablet</span></span>

- <span data-ttu-id="1777c-114">请确保您已[设置 APNs 证书](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7)。</span><span class="sxs-lookup"><span data-stu-id="1777c-114">Make sure that you've [set up an APNs certificate](https://support.office.com/article/522b43f4-a2ff-46f6-962a-dd4f47e546a7).</span></span>
    
- <span data-ttu-id="1777c-p103">在**设置** \> **常规** \> **配置文件**（或**设备管理**），请确保不已安装的**管理配置文件**。如果是，则将其删除。</span><span class="sxs-lookup"><span data-stu-id="1777c-p103">In **Settings** \> **General** \> **Profile** (or **Device Management**), make sure that a **Management Profile** is not already installed. If it is, remove it.</span></span> 
    
- <span data-ttu-id="1777c-117">如果您看到错误消息，"设备无法注册，"登录到 Office 365，并确保许可证，其中包括 Exchange Online 的已分配给的用户的登录到设备。</span><span class="sxs-lookup"><span data-stu-id="1777c-117">If you see the error message, "Device failed to enroll," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="1777c-118">如果您看到错误消息，"配置文件安装失败，"尝试下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1777c-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
  - <span data-ttu-id="1777c-119">确保 Safari 默认浏览器在设备上，且未禁用 cookie。</span><span class="sxs-lookup"><span data-stu-id="1777c-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
  - <span data-ttu-id="1777c-120">重新启动设备，然后导航到 portal.manage.microsoft.com、 登录您的 Office 365 用户 ID 和密码，并尝试手动安装配置文件。</span><span class="sxs-lookup"><span data-stu-id="1777c-120">Reboot the device, then navigate to portal.manage.microsoft.com, sign in with your Office 365 user ID and password, and attempt to install the profile manually.</span></span>
    
## <a name="windows-rt-tablet"></a><span data-ttu-id="1777c-121">Windows RT 平板电脑</span><span class="sxs-lookup"><span data-stu-id="1777c-121">Windows RT tablet</span></span>

- <span data-ttu-id="1777c-122">请确保您的域[以使用 MDM 的 Office 365 中设置](set-up-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1777c-122">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="1777c-123">确保用户已选择**打开**而不是选择**加入**。</span><span class="sxs-lookup"><span data-stu-id="1777c-123">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>
    
## <a name="windows-phone"></a><span data-ttu-id="1777c-124">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1777c-124">Windows Phone</span></span>

- <span data-ttu-id="1777c-125">请确保您的域[以使用 MDM 的 Office 365 中设置](set-up-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1777c-125">Make sure that your domain is [set up in Office 365 to work with MDM](set-up-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="1777c-126">请确保设备正在运行 Windows 8.1，或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1777c-126">Make sure the device is running Windows 8.1 or later.</span></span>
    
## <a name="android-phone-or-tablet"></a><span data-ttu-id="1777c-127">Android 移动电话或平板电脑</span><span class="sxs-lookup"><span data-stu-id="1777c-127">Android phone or tablet</span></span>

- <span data-ttu-id="1777c-128">确保设备运行 Android 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1777c-128">Make sure the device is running Android 4.0 or later.</span></span>
    
- <span data-ttu-id="1777c-129">如果您看到错误消息，"我们无法注册该设备，"登录到 Office 365，并确保许可证，其中包括 Exchange Online 的已分配给的用户的登录到设备。</span><span class="sxs-lookup"><span data-stu-id="1777c-129">If you see the error message, "We couldn't enroll this device," sign in to Office 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="1777c-130">检查上的**通知区域**设备有任何必需的最终用户操作挂起，并时，完成操作。</span><span class="sxs-lookup"><span data-stu-id="1777c-130">Check the **Notification Area** on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span> 
    

