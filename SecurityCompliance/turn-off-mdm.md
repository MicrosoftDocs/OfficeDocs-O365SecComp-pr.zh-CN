---
title: 如何关闭 Office 365 中的移动设备管理
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- GPA150
- MET150
ms.assetid: 2709cafb-0a8b-44bc-8494-7e2fccfa2b19
description: 按照以下步骤停止从移动设备 Office 365 组织中强制实施 MDM 策略。
ms.openlocfilehash: 6b8f0036ed999b10263f5cc074df27175769e604
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272217"
---
# <a name="how-to-turn-off-mobile-device-management-in-office-365"></a><span data-ttu-id="65710-103">如何关闭 Office 365 中的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="65710-103">How to turn off Mobile Device Management in Office 365</span></span>

<span data-ttu-id="65710-104">若要有效地关闭 MDM 的 Office 365，您 （由安全组定义） 的人员组移除设备管理策略，或删除他们自己的策略。</span><span class="sxs-lookup"><span data-stu-id="65710-104">To effectively turn off MDM for Office 365, you remove groups of people (defined by security groups) from the device management policies, or remove the policies themselves.</span></span> 
  
- <span data-ttu-id="65710-105">从您已创建的设备策略中删除用户安全组中删除用户的组。</span><span class="sxs-lookup"><span data-stu-id="65710-105">Remove groups of users by removing user security groups from the device policies you've created.</span></span> 
    
- <span data-ttu-id="65710-106">让每个人的 MDM 禁用中删除所有 MDM 设备策略。</span><span class="sxs-lookup"><span data-stu-id="65710-106">Disable MDM for everyone by removing all MDM device policies.</span></span> 
    
<span data-ttu-id="65710-p101">这些选项将您的组织中删除设备 MDM 实施。遗憾的是，您不能只是"取消设置"MDM for Office 365 后已设置。</span><span class="sxs-lookup"><span data-stu-id="65710-p101">These options will remove MDM enforcement for devices in your organization. Unfortunately, you can't simply "unprovision" MDM for Office 365 after you've set it up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65710-p102">当您从策略中删除用户安全组或删除他们自己的策略，则应注意对用户的设备的影响。例如，电子邮件配置文件和缓存的电子邮件可能被删除，具体取决于该设备。请参阅：[不同类型的设备上的安全策略的影响是什么？](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span><span class="sxs-lookup"><span data-stu-id="65710-p102">Be aware of the impact on users' devices when you remove user security groups from policies or remove the policies themselves. For example, email profiles and cached emails may be removed, depending on the device. See: [What is the impact of security policies on different device types?](create-device-security-policies.md#what-is-the-impact-of-security-policies-on-different-device-types)</span></span>
  
## <a name="remove-user-security-groups-from-mdm-device-policies"></a><span data-ttu-id="65710-112">从 MDM 设备策略中删除用户安全组</span><span class="sxs-lookup"><span data-stu-id="65710-112">Remove user security groups from MDM device policies</span></span>

1. <span data-ttu-id="65710-113">转到**安全&amp;合规性中心**\> **数据丢失防护** \> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="65710-113">Go to **Security &amp; Compliance Center**\> **Data loss prevention** \> **Device security polices**.</span></span>
    
2. <span data-ttu-id="65710-114">选择设备策略，然后单击![编辑图标](media/O365-MDM-CreatePolicy-EditIcon.gif)**编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="65710-114">Select a device policy, and click ![Edit icon](media/O365-MDM-CreatePolicy-EditIcon.gif) **Edit policy**.</span></span>
    
3. <span data-ttu-id="65710-115">在**部署**中，单击 **-删除**。</span><span class="sxs-lookup"><span data-stu-id="65710-115">Under **Deployment**, click **- Remove**.</span></span>
    
    <span data-ttu-id="65710-116">在**组**下选择安全组。</span><span class="sxs-lookup"><span data-stu-id="65710-116">Under **Groups**, select a security group.</span></span>
    
4.  <span data-ttu-id="65710-117">单击"移除"。</span><span class="sxs-lookup"><span data-stu-id="65710-117">Click **Remove**.</span></span>
    
5. <span data-ttu-id="65710-118">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="65710-118">Click **Save**.</span></span>
    
## <a name="remove-mdm-device-policies"></a><span data-ttu-id="65710-119">删除 MDM 设备策略</span><span class="sxs-lookup"><span data-stu-id="65710-119">Remove MDM device policies</span></span>

1. <span data-ttu-id="65710-120">转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="65710-120">Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**.</span></span>
    
2. <span data-ttu-id="65710-p103">选择设备策略，，然后单击![的回收站图像可以图标。](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **删除策略**。</span><span class="sxs-lookup"><span data-stu-id="65710-p103">Select a device policy, and then click ![Image of the trash can icon.](media/b8bfa783-c0b5-46d9-9570-8a385088e8fe.png) **Delete policy**.</span></span>
    
3. <span data-ttu-id="65710-123">在**警告**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="65710-123">In the **Warning** dialog, click **Yes**.</span></span> 
    

