---
title: 注册 Office 365 中的移动设备
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/25/2018
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: c8ac722d-dcaf-4135-8345-3e6327f5d3c5
description: 您的设备上使用 Office 365 服务之前，您可能需要按照以下步骤以注册它在移动设备管理的 Office 365 (MDM)。添加您的工作或在首次向您的设备学校电子邮件帐户时执行此操作。
ms.openlocfilehash: 0584309770cb978a5051bc84082de6e6be0b989e
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706346"
---
# <a name="enroll-your-mobile-device-in-office-365"></a><span data-ttu-id="13561-104">注册 Office 365 中的移动设备</span><span class="sxs-lookup"><span data-stu-id="13561-104">Enroll your mobile device in Office 365</span></span>

<span data-ttu-id="13561-p102">使用工作电话、 平板电脑和其他移动设备是保持好方法通知和时您离开办公室期间从事业务项目。您的设备上使用 Office 365 服务之前，您可能需要先注册它在移动设备管理的 Office 365 (MDM) 使用 Microsoft Intune 的公司门户。</span><span class="sxs-lookup"><span data-stu-id="13561-p102">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you're away from the office. Before you can use Office 365 services with your device, you may need to first enroll it in Mobile Device Management for Office 365 (MDM) using Microsoft Intune Company Portal.</span></span>
  
<span data-ttu-id="13561-p103">组织选择 MDM，以便员工可以使用其移动设备安全地访问工作电子邮件、 日历和文档时业务保护重要数据并满足其合规性要求。[了解 Office 365 中的 MDM](https://support.office.com/article/overview-of-mobile-device-management-mdm-for-office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。</span><span class="sxs-lookup"><span data-stu-id="13561-p103">Organizations choose MDM so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements. [Learn about MDM in Office 365](https://support.office.com/article/overview-of-mobile-device-management-mdm-for-office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="13561-p104">时为 Office 365 中注册您的设备中 MDM，您可能需要设置密码，以及允许您工作的组织擦除设备的选项。设备擦除可以执行 （从 Office 365 管理中心），例如，若要从设备中删除所有数据，如果密码错误地输入次数过多或使用条款会失效。</span><span class="sxs-lookup"><span data-stu-id="13561-p104">When you enroll your device in MDM for Office 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device. A device wipe can be performed (from the Office 365 admin center), for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span> 
  
 <span data-ttu-id="13561-111">**支持的设备**</span><span class="sxs-lookup"><span data-stu-id="13561-111">**Supported devices**</span></span>
  
<span data-ttu-id="13561-p105">MDM 和 InTune 适用于大多数，而不是全部移动设备。支持以下 MDM 与 Office 365。</span><span class="sxs-lookup"><span data-stu-id="13561-p105">MDM and InTune works with most, but not all, mobile devices. The following are supported with MDM for Office 365.</span></span>
  
- <span data-ttu-id="13561-114">iOS 7.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="13561-114">iOS 7.1 or later</span></span>
    
- <span data-ttu-id="13561-115">Android 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="13561-115">Android 4 or later</span></span>
    
- <span data-ttu-id="13561-116">Windows 8.1 （电话和 PC） 和更高版本，以包括 Windows 10</span><span class="sxs-lookup"><span data-stu-id="13561-116">Windows 8.1 (Phone and PC) and later to include Windows 10</span></span>
    
- <span data-ttu-id="13561-117">Windows 10</span><span class="sxs-lookup"><span data-stu-id="13561-117">Windows 10</span></span>
    
<span data-ttu-id="13561-118">如果您的设备未列出，并且您需要使用 MDM 和 Intune，与工作或学校管理员联系。</span><span class="sxs-lookup"><span data-stu-id="13561-118">If your device is not listed above, and you need to use it with MDM and Intune, contact your work or school administrator.</span></span>
  
> [!TIP]
> <span data-ttu-id="13561-119">如果您在遇到问题注册您的设备，请参阅：[与 Office 365 MDM Troubleshoot 设备注册](https://support.office.com/article/Troubleshoot-device-enrollment-with-MDM-for-Office-365-c863b2bf-45f3-483a-ba05-29fc7f4d6434)。</span><span class="sxs-lookup"><span data-stu-id="13561-119">If you're having trouble enrolling your device, see: [Troubleshoot device enrollment with MDM for Office 365](https://support.office.com/article/Troubleshoot-device-enrollment-with-MDM-for-Office-365-c863b2bf-45f3-483a-ba05-29fc7f4d6434).</span></span> 
  
## <a name="set-up-your-mobile-device-with-intune-and-mdm-for-office-365"></a><span data-ttu-id="13561-120">针对 Office 365 设置 MDM Intune 与移动设备</span><span class="sxs-lookup"><span data-stu-id="13561-120">Set up your mobile device with Intune and MDM for Office 365</span></span>

<span data-ttu-id="13561-121">Intune 的公司门户启用一个设备，以管理 Office 365 和 mdm。</span><span class="sxs-lookup"><span data-stu-id="13561-121">The Intune Company Portal enables a device to be managed by Office 365 and MDM.</span></span>
  
### <a name="iphone-or-ipad"></a><span data-ttu-id="13561-122">iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="13561-122">iPhone or iPad</span></span>

> [!TIP]
> <span data-ttu-id="13561-p106">您将无法发送和接收电子邮件，直到完成此步骤。转到 Apple App Store，下载并安装**Intune 的公司门户**。请参阅[设置 iOS 设备访问您的公司资源](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)。</span><span class="sxs-lookup"><span data-stu-id="13561-p106">You won't be able to send and receive email until you complete this step. Go to the Apple App Store, download and install **Intune Company Portal**. See [Set up iOS device access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios).</span></span> 
    
### <a name="android-phone-or-tablet"></a><span data-ttu-id="13561-126">Android 移动电话或平板电脑</span><span class="sxs-lookup"><span data-stu-id="13561-126">Android phone or tablet</span></span>

> [!TIP]
> <span data-ttu-id="13561-p107">您将无法发送和接收电子邮件，直到完成此步骤。转到 Google 播放存储，下载并安装 Intune 的公司门户。请参阅[注册中 Intune Android 设备](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)。</span><span class="sxs-lookup"><span data-stu-id="13561-p107">You won't be able to send and receive email until you complete this step. Go to the Google Play store, download and install Intune Company Portal. See [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span> 
    
## <a name="whats-next"></a><span data-ttu-id="13561-130">什么是下一步</span><span class="sxs-lookup"><span data-stu-id="13561-130">What's next</span></span>

<span data-ttu-id="13561-131">您的设备中 MDM 注册 Office 365 后，您可以开始使用设备上的 Office 应用程序以使用电子邮件、 日历、 联系人和文档。</span><span class="sxs-lookup"><span data-stu-id="13561-131">After your device is enrolled in MDM for Office 365, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
  

