---
title: 管理设备注册 Office 365 中的移动设备管理
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
- MBS150
- MET150
ms.assetid: 28dd276b-beeb-4c5b-8b22-7551186127fe
description: 请按照下列步骤设置向上移动设备管理 (MDM) 在 Office 365 中。
ms.openlocfilehash: 3a84b6904b866e07eb4efabe0f39041b282d0ba9
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272307"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-office-365"></a><span data-ttu-id="aa0a5-103">管理设备注册 Office 365 中的移动设备管理</span><span class="sxs-lookup"><span data-stu-id="aa0a5-103">Manage devices enrolled in Mobile Device Management in Office 365</span></span>

<span data-ttu-id="aa0a5-p101">内置移动设备管理 Office 365 帮助您保护和管理 iPhones、 Ipad，Androids，如用户的移动设备和 Windows 电话。第一步是登录到 Office 365 和[Office 365 MDM 设置](set-up-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p101">The built-in Mobile Device Management for Office 365 helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones. The first step is to sign in to Office 365 and [set up MDM for Office 365](set-up-mobile-device-management.md).</span></span> 
  
<span data-ttu-id="aa0a5-p102">您设置它，用户在组织中后的值必须在服务中[注册其设备](enroll-your-mobile-device.md)。然后可以使用 Office 365 MDM 来帮助管理您的组织中的设备。例如，设备安全策略可用于帮助限制访问电子邮件或其他服务、 查看设备报告和远程擦除设备。通常，您将转到[转到 Office 365 安全性&amp;合规性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p102">After you've set it up, the people in your organization must [enroll their devices](enroll-your-mobile-device.md) in the service. Then you can use MDM for Office 365 to help manage devices in your organization. For example, you can use device security policies to help limit email access or other services, view devices reports, and remotely wipe a device. You'll typically go to the [Go to the Office 365 Security &amp; Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) to do these tasks.</span></span> 
  
## <a name="device-management-tasks"></a><span data-ttu-id="aa0a5-110">设备管理任务</span><span class="sxs-lookup"><span data-stu-id="aa0a5-110">Device management tasks</span></span>

<span data-ttu-id="aa0a5-111">若要打开设备管理面板，请按照下列步骤。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-111">To get to the device management panel, follow these steps.</span></span> 
  
1. <span data-ttu-id="aa0a5-112">转到 Office 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-112">Go to the Office 365 admin center.</span></span>
    
2. <span data-ttu-id="aa0a5-113">在搜索字段中，键入移动设备管理，并从结果列表中选择**移动设备管理**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-113">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 
    
    ![到 O365 搜索字段类型移动设备管理器](media/e2e2f1c0-e543-431a-959b-e26c2ba328a7.png)
  
<span data-ttu-id="aa0a5-115">MDM for Office 365 设置之后，下面是如何在组织中管理移动设备。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-115">After you've got MDM for Office 365 set up, here's how you can manage the mobile devices in your organization.</span></span> 
  
|<span data-ttu-id="aa0a5-116">**若要执行此操作...**</span><span class="sxs-lookup"><span data-stu-id="aa0a5-116">**To do this…**</span></span>|<span data-ttu-id="aa0a5-117">**执行操作**</span><span class="sxs-lookup"><span data-stu-id="aa0a5-117">**Do this**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aa0a5-118">擦除设备</span><span class="sxs-lookup"><span data-stu-id="aa0a5-118">Wipe a device</span></span>  <br/> |<span data-ttu-id="aa0a5-119">在设备管理面板中，选择*设备名称*，然后**完全擦除**删除所有的信息或**与擦除**删除设备上仅组织的信息。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-119">In the Device Management panel, select  *device name*  , then **Full wipe** to delete all information or **Selective wipe** to delete only organizational information on the device.</span></span>  <br/> <span data-ttu-id="aa0a5-120">请参阅[擦除 Office 365 中的设备](wipe-a-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-120">See [Wipe a device in Office 365](wipe-a-mobile-device.md).</span></span>  <br/> |
|<span data-ttu-id="aa0a5-121">阻止不受支持的设备使用 Exchange ActiveSync 访问 Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="aa0a5-121">Block unsupported devices from accessing Exchange email using Exchange ActiveSync</span></span>  <br/> |<span data-ttu-id="aa0a5-122">在设备管理面板中，选择**阻止**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-122">In the Device Management panel, select **Block**.</span></span>  <br/> |
|<span data-ttu-id="aa0a5-123">设置设备策略，如密码要求和安全设置</span><span class="sxs-lookup"><span data-stu-id="aa0a5-123">Set up device policies like password requirements and security settings</span></span>  <br/> |<span data-ttu-id="aa0a5-124">在设备管理面板中，单击\>**设备安全策略** \> **添加 +**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-124">In the Device Management panel, click \> **Device security policies** \> **Add +**.</span></span>  <br/> <span data-ttu-id="aa0a5-125">请参阅[创建和部署设备安全策略](create-device-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-125">See [Create and deploy device security policies](create-device-security-policies.md).</span></span>  <br/> |
|<span data-ttu-id="aa0a5-126">查看阻止的设备列表</span><span class="sxs-lookup"><span data-stu-id="aa0a5-126">View list of blocked devices</span></span>  <br/> |<span data-ttu-id="aa0a5-127">在设备管理面板中，在**选择视图**下选择**已阻止**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-127">In the Device Management panel, under **Select a view** select **Blocked**.</span></span>  <br/> ||
|<span data-ttu-id="aa0a5-128">解除阻止单个用户或一组用户的不相容或不受支持的设备</span><span class="sxs-lookup"><span data-stu-id="aa0a5-128">Unblock noncompliant or unsupported device for a user or group of users</span></span>  <br/> | <span data-ttu-id="aa0a5-p103">根据您的情况，可以取消阻止不符合标准的设备几种方法。选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p103">You can unblock noncompliant devices several ways depending on your situation. Pick one of the following:  </span></span><br/>  <span data-ttu-id="aa0a5-p104">策略已应用于的安全组中移除的用户。转到**Office 365 管理中心** \> **组**，然后选择 * 组名称 *。单击**编辑成员和管理员**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p104">Remove the user or users from the security group the policy has been applied to. Go to **Office 365 admin center** \> **Groups**, and then select  * group name *  . Click **Edit members and admins**.  </span></span><br/>  <span data-ttu-id="aa0a5-p105">删除安全组用户是设备策略中的成员。转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。选择 * 设备策略名称 *，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **部署**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p105">Remove the security group the users are a member of from the device policy. Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**. Select  * device policy name *  , then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **Deployment**.  </span></span><br/>  <span data-ttu-id="aa0a5-p106">取消阻止设备策略的所有不符合标准的设备。转到**安全&amp;合规性中心**\> **安全策略** \> **设备安全策略**。选择*设备策略名称*，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **访问要求**。选择**允许访问和报告的冲突**。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p106">Unblock all noncompliant devices for a device policy. Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device security policies**. Select  *device policy name*  and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif) \> **Access requirements**. Select **Allow access and report violation**.  </span></span><br/>  <span data-ttu-id="aa0a5-p107">若要取消阻止不符合标准或不受支持设备的用户或一组用户，请转到转到**安全&amp;合规性中心**\> **安全策略** \> **设备管理** \> **管理设备访问设置**.添加安全组与成员您想要排除要阻止对 Office 365 的访问。请参阅[创建、 编辑或删除 Office 365 管理中心中的安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p107">To unblock a noncompliant or unsupported device for a user or a group of users, go to Go to **Security &amp; Compliance Center**\> **Security policies** \> **Device management** \> **Manage device access settings**. Add a security group with the members you want to exclude from being blocked access to Office 365. See [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).  </span></span><br/> |
|<span data-ttu-id="aa0a5-144">您的组织中获取有关设备的详细信息</span><span class="sxs-lookup"><span data-stu-id="aa0a5-144">Get details about the devices in your organization</span></span>  <br/> |<span data-ttu-id="aa0a5-145">要获得例如，哪些设备是注册，并且符合设备安全策略的详细信息，请按照[获得有关由 MDM 管理的设备的详细信息](get-details-about-mdm-managed-devices.md)中列出的步骤。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-145">To get details such as which devices are enrolled and compliant with device security policies, follow the steps outlined in [Get details about devices managed by MDM](get-details-about-mdm-managed-devices.md).</span></span>  <br/> |
|<span data-ttu-id="aa0a5-146">删除用户，以便其设备不再由 MDM</span><span class="sxs-lookup"><span data-stu-id="aa0a5-146">Remove users so their devices are no longer managed by MDM</span></span>  <br/> |<span data-ttu-id="aa0a5-p108">编辑具有 MDM 要删除用户的设备管理策略的安全组。请参阅[创建、 编辑或删除 Office 365 管理中心中的安全组](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-p108">Edit the security group which has device management policies for MDM to remove the user. See [Create, edit, or delete a security group in the Office 365 admin center](https://support.office.com/article/55c96b32-e086-4c9e-948b-a018b44510cb).  </span></span><br/> <span data-ttu-id="aa0a5-149">若要删除所有 Office 365 用户 MDM，请参阅[关闭 Office 365 中的移动设备管理](turn-off-mdm.md)。</span><span class="sxs-lookup"><span data-stu-id="aa0a5-149">To remove MDM from all your Office 365 users, see [Turn off Mobile Device Management in Office 365](turn-off-mdm.md).</span></span>  <br/> |
   

