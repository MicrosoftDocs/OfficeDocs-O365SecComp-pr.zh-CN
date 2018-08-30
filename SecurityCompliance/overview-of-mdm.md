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
# <a name="overview-of-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="ccd8a-106">移动设备管理 (MDM) for Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="ccd8a-106">Overview of Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="ccd8a-p102">您可以管理和安全的移动设备，当他们使用移动设备管理 Office 365 连接到 Office 365 组织。移动设备，如智能手机和平板电脑的用于访问工作电子邮件、 日历、 联系人和文档播放中确保员工获取完成随时随地从任何地方工作的重要部分。因此，很重要，帮助保护贵组织的信息的人员使用设备时。设置设备安全策略和访问规则，以及他们正在丢失或被盗擦除移动设备，可以使用 Office 365 MDM。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p102">You can manage and secure mobile devices when they're connected to your Office 365 organization by using Mobile Device Management for Office 365. Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere. So it's critical that you help protect your organization's information when people use devices. You can use MDM for Office 365 to set device security policies and access rules, and to wipe mobile devices if they're lost or stolen.</span></span>
  
![在 android 移动电话上 MDM](media/69b9a9f6-13ac-4e36-99ca-95e82e0375aa.png)
  
## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="ccd8a-112">您可以管理哪些类型的设备？</span><span class="sxs-lookup"><span data-stu-id="ccd8a-112">What types of devices can you manage?</span></span>

<span data-ttu-id="ccd8a-p103">Office 365 MDM 可用于管理移动设备，如 Windows Phone、 Android、 iPhone 和 iPad 的许多类型。若要管理移动设备使用您的组织中的人员，每个人必须具有适用的 Office 365 许可证，并且其设备必须在 MDM 注册 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p103">You can use MDM for Office 365 to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad. To manage mobile devices used by people in your organization, each person must have an applicable Office 365 license and their device must be enrolled in MDM for Office 365.</span></span> 
  
<span data-ttu-id="ccd8a-115">若要查看每个类型的设备支持的 Office 365 MDM，请参阅[功能的移动设备管理 Office 365](capabilities-of-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-115">To see what MDM for Office 365 supports for each type of device, see [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
  
## <a name="setup-steps-for-mdm"></a><span data-ttu-id="ccd8a-116">MDM 的安装步骤</span><span class="sxs-lookup"><span data-stu-id="ccd8a-116">Setup steps for MDM</span></span>

<span data-ttu-id="ccd8a-p104">Office 365 全局管理员必须完成以下步骤来激活并针对 Office 365 设置 MDM。按照上[设置 MDM Office 365 的](set-up-mobile-device-management.md)详细的步骤，请参阅主题中的指南。下面是快速汇总：</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p104">An Office 365 global admin must complete the following steps to activate and set up MDM for Office 365. Follow the guidance in the topic on [setting up MDM for Office 365](set-up-mobile-device-management.md) to see detailed steps. Here's a quick summary:</span></span> 
  
> <span data-ttu-id="ccd8a-120">步骤 1： 针对 Office 365 激活 MDM 按照中[设置向上移动设备管理 (MDM) 在 Office 365 中](set-up-mobile-device-management.md)的步骤。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-120">Step 1: Activate MDM for Office 365 by following steps in the [Set up Mobile Device Management (MDM) in Office 365](set-up-mobile-device-management.md).</span></span>
    
> <span data-ttu-id="ccd8a-121">步骤 2： 设置 MDM for Office 365 的例如，创建用于管理 iOS 设备的 APNs 证书并添加您的域，以支持 Windows phone 的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-121">Step 2: Set up MDM for Office 365 by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>
    
> <span data-ttu-id="ccd8a-p105">步骤 3： 创建设备策略，并将它们应用于的用户组。时执行此操作时，用户将收到[注册消息在其设备上](enroll-your-mobile-device.md)。和它们已完成注册，其设备将受限制的已为其设置的策略。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p105">Step 3: Create device policies and apply them to groups of users. When you do this, your users will get an [enrollment message on their device](enroll-your-mobile-device.md). And when they've completed enrollment, their devices will be restricted by the policies you've set up for them.</span></span>
    
    ![Creating an MDN device policy under Device security policies](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
## <a name="device-management-tasks"></a><span data-ttu-id="ccd8a-125">设备管理任务</span><span class="sxs-lookup"><span data-stu-id="ccd8a-125">Device management tasks</span></span>

<span data-ttu-id="ccd8a-p106">Office 365 设置了 MDM 和您的用户已注册其设备后，可以管理设备、 阻止访问，或需要擦除的设备。了解有关[一些常见的设备管理任务](manage-devices-in-mdm.md)，包括完成任务的位置。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p106">After you've got MDM for Office 365 set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if needed. Learn more about [some common device management tasks](manage-devices-in-mdm.md), including where to complete the tasks.</span></span>
  
## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="ccd8a-128">管理设备和应用程序的其他方法</span><span class="sxs-lookup"><span data-stu-id="ccd8a-128">Other ways to manage devices and apps</span></span>

<span data-ttu-id="ccd8a-129">如果您需要更多比 MDM for Office 365 的功能包括、 签出此[MDM 和 Microsoft Intune 功能的比较](choose-between-mdm-and-intune.md)，以查看是否 Intune 订阅将符合贵组织的需求。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-129">If you need more functionality than MDM for Office 365 includes, check out this [comparison of MDM and Microsoft Intune features](choose-between-mdm-and-intune.md) to see if an Intune subscription would meet your organization's needs.</span></span> 
  
<span data-ttu-id="ccd8a-p107">如果您只需移动应用程序管理 (MAM)，有可能是更新自己的设备上工作项目的人员 Intune 将提供除了注册和管理设备的另一个选项。Intune 订阅允许您设置 MAM 策略通过使用 Azure 门户，即使不会加入 Intune 人的设备。请参阅[使用 MAM 策略保护应用程序数据](https://go.microsoft.com/fwlink/?LinkId=825439)。</span><span class="sxs-lookup"><span data-stu-id="ccd8a-p107">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices. An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune. See [Protect app data using MAM policies](https://go.microsoft.com/fwlink/?LinkId=825439).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ccd8a-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccd8a-133">See also</span></span>

[<span data-ttu-id="ccd8a-134">获取有关由 MDM 管理的设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="ccd8a-134">Get details about devices managed by MDM</span></span>](get-details-about-mdm-managed-devices.md)

[<span data-ttu-id="ccd8a-135">针对 Office 365 设置 MDM</span><span class="sxs-lookup"><span data-stu-id="ccd8a-135">Set up MDM for Office 365</span></span>](set-up-mobile-device-management.md)
  
[<span data-ttu-id="ccd8a-136">注册 MDM 中的移动设备</span><span class="sxs-lookup"><span data-stu-id="ccd8a-136">Enroll mobile devices in MDM</span></span>](enroll-your-mobile-device.md)
  
[<span data-ttu-id="ccd8a-137">管理设备报名参加 MDM</span><span class="sxs-lookup"><span data-stu-id="ccd8a-137">Manage devices enrolled in MDM</span></span>](manage-devices-in-mdm.md)

