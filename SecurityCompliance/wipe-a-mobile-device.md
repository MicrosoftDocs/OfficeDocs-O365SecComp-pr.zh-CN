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
# <a name="wipe-a-mobile-device-in-office-365"></a><span data-ttu-id="ccb2b-103">Office 365 中擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="ccb2b-103">Wipe a mobile device in Office 365</span></span>
  
<span data-ttu-id="ccb2b-104">内置移动设备管理的 Office 365 可用于执行选择性擦除删除仅组织信息或完整擦除，从移动设备中删除所有信息并将其还原到出厂默认设置。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-104">You can use built-in mobile device management for Office 365 to do a selective wipe to remove only organizational information, or a full wipe to delete all information from a mobile device and restore it to its factory settings.</span></span>
  
## <a name="what-to-know-before-you-begin"></a><span data-ttu-id="ccb2b-105">开始之前应了解</span><span class="sxs-lookup"><span data-stu-id="ccb2b-105">What to know before you begin</span></span>

- <span data-ttu-id="ccb2b-p101">移动设备可以存储组织的敏感信息，并提供对您的组织的 Office 365 资源的访问。为了帮助保护贵组织的信息，可以执行完整擦除或选择性擦除操作：</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p101">Mobile devices can store sensitive organizational information and provide access to your organization's Office 365 resources. To help protect your organization's information, you can do a full wipe or a selective wipe:</span></span>
    
  - <span data-ttu-id="ccb2b-p102">**完整擦除**： 删除上用户的移动设备，包括安装的应用程序、 照片和个人信息的所有数据。擦除完成后，设备还原到出厂默认设置。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p102">**Full wipe**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information. When the wipe is complete, the device is restored to its factory settings.</span></span> 
    
  - <span data-ttu-id="ccb2b-110">**与擦除**： 删除组织数据和离开安装应用程序、 照片和用户的移动设备上的个人信息。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-110">**Selective wipe**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span> 
    
- <span data-ttu-id="ccb2b-111">当擦除设备后 （完整擦除或选择性擦除） 时，将从托管设备的列表中删除设备。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-111">When a device is wiped (full wipe or selective wipe), the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="ccb2b-p103">您可以设置的移动设备管理策略，自动擦除 （完整擦除） 设备后用户多次尝试输入设备的密码特定的次数。请按照本文[创建和部署设备安全策略](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p103">You can set up a mobile device management policy that automatically wipes (full wipe) a device after the user unsuccessfully tries to enter the device's password a specific number of times. Follow the steps in [Create and deploy device security policies](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="ccb2b-114">如果您想了解擦除其设备时，用户将体验，请参阅[的用户和设备的影响是什么？](wipe-a-mobile-device.md#BKMK_Impact)。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-114">If you want to know what a user will experience when you wipe their device, see [What's the user and device impact?](wipe-a-mobile-device.md#BKMK_Impact).</span></span>
    
## <a name="wipe-a-mobile-device"></a><span data-ttu-id="ccb2b-115">擦除移动设备</span><span class="sxs-lookup"><span data-stu-id="ccb2b-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="ccb2b-116">转到[![单击此处以转到 Office 365 管理中心。](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home)。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-116">Go to the [![Click here to go to the Office 365 admin center.](media/e00ba917-c3fb-4173-b344-43eb5c7eeb15.png)](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="ccb2b-117">转到[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **数据丢失防护** \> **设备管理**。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-117">Go to [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)\> **Data loss prevention** \> **Device management**.</span></span>
    
3. <span data-ttu-id="ccb2b-118">选择您想要擦除的设备。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-118">Select the device you want to wipe.</span></span>
    
4. <span data-ttu-id="ccb2b-119">选择您希望执行远程擦除的类型。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-119">Select the type of remote wipe you want to do.</span></span>
    
  - <span data-ttu-id="ccb2b-120">若要执行选择性擦除并删除仅 Office 365 组织信息，请在右窗格中，选择**与擦除**。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-120">To do a selective wipe and delete only Office 365 organization information, in the right pane, select **Selective wipe**.</span></span>
    
  - <span data-ttu-id="ccb2b-121">若要执行完整擦除并将设备还原到出厂默认设置，在右侧窗格中，选择**完整擦除**。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-121">To do a full wipe and restore the device to its factory settings, in the right pane, select **Full wipe**.</span></span>
    
![选择设备，然后选择要执行的擦除类型。](media/ac940abe-0c4a-404e-a842-a1ad2af13ce3.png)
  
5. <span data-ttu-id="ccb2b-123">选择**是**以确认。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-123">Select **Yes** to confirm.</span></span> 
    
<span data-ttu-id="ccb2b-124">擦除完成，直到**设备状态**将显示为**RetirePending**或**RetireIssued**。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-124">Until the wipe finishes, the **Device status** will show as **RetirePending** or **RetireIssued**.</span></span>
  
### <a name="how-do-i-know-it-worked"></a><span data-ttu-id="ccb2b-125">如何知道它是否运行。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-125">How do I know it worked?</span></span>

<span data-ttu-id="ccb2b-126">不再将看到的托管设备列表中的移动设备。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-126">You'll no longer see the mobile device in the list of managed devices.</span></span>
  
## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="ccb2b-127">为什么要擦除设备？</span><span class="sxs-lookup"><span data-stu-id="ccb2b-127">Why would you want to wipe a device?</span></span>

<span data-ttu-id="ccb2b-128">有几个擦除设备原因：</span><span class="sxs-lookup"><span data-stu-id="ccb2b-128">There are several reasons for wiping devices:</span></span>
  
- <span data-ttu-id="ccb2b-p104">智能手机和平板电脑等移动设备变得更加全面的所有的时间。这意味着更方便地在您的用户存储敏感的公司信息 （如个人标识或 2 私有 3 机密 communications） 并在访问它。如果这些移动设备之一的丢失或被盗，立即擦除设备可以帮助防止别人以结尾贵组织的信息。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p104">Mobile devices like smartphones and tablets are becoming more full-featured all the time. This means it's easier for your users to store sensitive corporate information (such as personal identification or confidential communications) and access it on the go. If one of these mobile devices is lost or stolen, wiping the device immediately can help prevent your organization's information from ending up in the wrong hands.</span></span>
    
- <span data-ttu-id="ccb2b-132">当用户离开组织与 Office 365 中 MDM 注册个人设备时，您可以帮助防止通过执行选择性擦除转与该用户组织的信息。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-132">When a user leaves the organization with a personal device that is enrolled in MDM for Office 365, you can help prevent organizational information from going with that user by doing a selective wipe.</span></span>
    
- <span data-ttu-id="ccb2b-p105">如果您的组织提供给用户的移动设备，您可能需要经常将设备重新分配。执行操作之前将其分配给新用户帮助完整擦除设备上的可确保从以前的任何敏感信息，并被删除。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p105">If your organization provides mobile devices to users, you might need to reassign devices from time to time. Doing a full wipe on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>
    
## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="ccb2b-135">用户和设备影响是什么？</span><span class="sxs-lookup"><span data-stu-id="ccb2b-135">What's the user and device impact?</span></span>

<span data-ttu-id="ccb2b-p106">擦除立即发送给移动设备。设备也标记为不符合 AAD 中。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p106">The wipe is sent immediately to the mobile device. The device is also marked as not compliant in AAD.</span></span>
  
<span data-ttu-id="ccb2b-138">下表介绍时有选择地擦除设备后，内容为每种设备类型中删除。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-138">The following table describes what content is removed for each device type when a device is selectively wiped.</span></span>
  
|<span data-ttu-id="ccb2b-139">**内容的影响**</span><span class="sxs-lookup"><span data-stu-id="ccb2b-139">**Content impact**</span></span>|<span data-ttu-id="ccb2b-140">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="ccb2b-140">**Windows Phone 8.1**</span></span>|<span data-ttu-id="ccb2b-141">**iOS 7.1+**</span><span class="sxs-lookup"><span data-stu-id="ccb2b-141">**iOS 7.1+**</span></span>|<span data-ttu-id="ccb2b-142">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="ccb2b-142">**Android 4+**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ccb2b-143">公司门户应用程序\*卸载。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-143">Company Portal app\* is uninstalled.</span></span>  <br/> |<span data-ttu-id="ccb2b-144">不适用</span><span class="sxs-lookup"><span data-stu-id="ccb2b-144">N/A</span></span>  <br/> |<span data-ttu-id="ccb2b-145">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-145">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-146">不适用</span><span class="sxs-lookup"><span data-stu-id="ccb2b-146">N/A</span></span>  <br/> |
|<span data-ttu-id="ccb2b-p107">已删除 （当前 Outlook 和 OneDrive for Business），其中访问控制支持 MDM for Office 365 的应用程序承载的 office 365 应用程序数据。不会删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-p107">Office 365 app data hosted by apps where access control is supported by MDM for Office 365 is removed (currently Outlook and OneDrive for Business). The apps are not removed.</span></span>  <br/> <span data-ttu-id="ccb2b-149">Android 的 outlook 不会删除缓存的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-149">Outlook for Android does not remove cached emails.</span></span>  <br/> |<span data-ttu-id="ccb2b-150">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-150">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-151">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-151">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-152">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-152">✔</span></span>  <br/> |
|<span data-ttu-id="ccb2b-153">设备上不再强制实施应用的 MDM for Office 365 到设备的策略设置，用户可以更改设置。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-153">Policy settings that were applied by MDM for Office 365 to devices are no longer enforced on the device and users can change the settings.</span></span>  <br/> |<span data-ttu-id="ccb2b-154">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-154">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-155">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-155">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-156">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-156">✔</span></span>  <br/> |
|<span data-ttu-id="ccb2b-157">删除 Office 365 MDM 创建的电子邮件配置文件并删除设备上的缓存电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-157">Email profiles created by MDM for Office 365 are removed and cached email on the device is deleted.</span></span>  <br/> |<span data-ttu-id="ccb2b-158">不适用</span><span class="sxs-lookup"><span data-stu-id="ccb2b-158">N/A</span></span>  <br/> |<span data-ttu-id="ccb2b-159">✔</span><span class="sxs-lookup"><span data-stu-id="ccb2b-159">✔</span></span>  <br/> |<span data-ttu-id="ccb2b-160">不适用</span><span class="sxs-lookup"><span data-stu-id="ccb2b-160">N/A</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="ccb2b-161">\*适用于 iOS 应用程序存储和播放存储 Android 设备上提供了公司门户应用程序。</span><span class="sxs-lookup"><span data-stu-id="ccb2b-161">\* Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="ccb2b-162">相关内容</span><span class="sxs-lookup"><span data-stu-id="ccb2b-162">Related content</span></span>

[<span data-ttu-id="ccb2b-163">管理 Office 365 中的移动设备</span><span class="sxs-lookup"><span data-stu-id="ccb2b-163">Manage mobile devices in Office 365</span></span>](set-up-mobile-device-management.md)
  

