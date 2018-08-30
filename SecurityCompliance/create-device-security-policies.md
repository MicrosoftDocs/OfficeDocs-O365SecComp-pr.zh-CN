---
title: 创建和部署设备安全策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/9/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewDevicePolicy
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: d310f556-8bfb-497b-9bd7-fe3c36ea2fd6
description: '创建和部署可帮助的 Office 365 中的移动设备管理安全策略步骤防止未经授权的访问 Office 365 组织的信息。 '
ms.openlocfilehash: ab1fc1960a3e55eb3080dde7df0ec742c58b2cc7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272067"
---
# <a name="create-and-deploy-device-security-policies"></a><span data-ttu-id="1ec8d-103">创建和部署设备安全策略</span><span class="sxs-lookup"><span data-stu-id="1ec8d-103">Create and deploy device security policies</span></span>

<span data-ttu-id="1ec8d-p101">可以使用移动设备管理的 Office 365 创建帮助防止未经授权的访问 Office 365 组织的信息的安全策略。在您的组织的用户的设备其中具有适用的 Office 365 许可证和已注册 Office 365 中 MDM 的设备，您可以应用到任何移动设备策略。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p101">You can use Mobile Device Management for Office 365 to create security policies that help protect your organization's information on Office 365 from unauthorized access. You can apply policies to any mobile device in your organization where the user of the device has an applicable Office 365 license and has enrolled the device in MDM for Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="1ec8d-106">准备工作</span><span class="sxs-lookup"><span data-stu-id="1ec8d-106">Before you begin</span></span>

- <span data-ttu-id="1ec8d-p102">了解设备、 移动设备应用程序和 Office 365 MDM 支持的安全设置。请参阅[Office 365 的移动设备管理功能](capabilities-of-mobile-device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p102">Learn about the devices, mobile device apps, and security settings that MDM for Office 365 supports. See [Capabilities of Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md).</span></span>
    
- <span data-ttu-id="1ec8d-p103">创建包含您想要部署到的策略的 Office 365 用户的安全组和用户，您可能想要排除要阻止到 Office 365 的访问。我们建议您的组织部署新的策略之前，您测试策略将它部署到少量用户。您可以创建并使用安全组，其中包含刚刚自己或可以为您测试策略小型 Office 365 用户。若要了解有关安全组的详细信息，请参阅[创建、 编辑或删除安全组](https://go.microsoft.com/fwlink/p/?LinkId=518555)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p103">Create security groups that include Office 365 users that you want to deploy policies to and for users that you might want to exclude from being blocked access to Office 365. We recommend that before you deploy a new policy to your organization, you test the policy by deploying it to a small number of users. You can create and use a security group that includes just yourself or a small number Office 365 users that can test the policy for you. To learn more about security groups, see [Create, edit, or delete a security group](https://go.microsoft.com/fwlink/p/?LinkId=518555).</span></span>
    
- <span data-ttu-id="1ec8d-p104">**重要：** 您可以创建移动设备策略之前，必须激活并针对 Office 365 设置 MDM。请参阅[Overview of Office 365 的移动设备管理](overview-of-mdm.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p104">**Important:** Before you can create a mobile device policy, you must activate and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md).</span></span>
    
- <span data-ttu-id="1ec8d-115">若要创建和部署 Office 365 中的移动设备管理策略，您需要为 Office 365 全局管理员。请参阅[Permissions in Office 365 安全性&amp;合规性中心](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-115">To create and deploy mobile device management policies in Office 365, you need to be an Office 365 global admin. See [Permissions in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/d10608af-7934-490a-818e-e68f17d0e9c1).</span></span>
    
- <span data-ttu-id="1ec8d-p105">部署策略之前，让您知道注册 Office 365 中 MDM 的设备的潜在影响的组织。根据如何设置策略，可以阻止不符合标准的设备访问 Office 365，可以删除数据，包括安装的应用程序、 照片和注册的设备上的个人信息。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p105">Before you deploy policies, let your organization know the potential impacts of enrolling a device in MDM for Office 365. Depending on how you set up the policies, noncompliant devices can be blocked from accessing Office 365 and data, including installed applications, photos, and personal information on an enrolled device, can be deleted.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ec8d-p106">Exchange ActiveSync 移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则，将覆盖策略和在 MDM for Office 365 中创建的访问规则。设备中 MDM 注册 Office 365 后，将忽略任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则应用于该设备。若要了解有关 Exchange ActiveSync 的详细信息，请参阅[Exchange Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p106">Policies and access rules created in MDM for Office 365 will override Exchange ActiveSync mobile device mailbox policies and device access rules created in the Exchange admin center. After a device is enrolled in MDM for Office 365, any Exchange ActiveSync mobile device mailbox policy or device access rule applied to the device will be ignored. To learn more about Exchange ActiveSync, see [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).</span></span> 
  
## <a name="step-1-create-a-security-policy-and-deploy-to-a-test-group"></a><span data-ttu-id="1ec8d-121">步骤 1： 创建的安全策略，并部署到测试组</span><span class="sxs-lookup"><span data-stu-id="1ec8d-121">Step 1: Create a security policy and deploy to a test group</span></span>

<span data-ttu-id="1ec8d-p107">您可以开始之前，请确保您已激活和为 Office 365 设置 MDM。有关说明，请参阅[概述的移动设备管理 Office 365](overview-of-mdm.md) 。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p107">Before you can start, make sure you have activated and set up MDM for Office 365. See [Overview of Mobile Device Management for Office 365](overview-of-mdm.md) for instructions.</span></span> 
  
1. <span data-ttu-id="1ec8d-124">在 Office 365 中，安全中&amp;合规性中心中，转到**数据丢失防护** \> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-124">In Office 365, in the Security &amp; Compliance Center, go to **Data loss prevention** \> **Device security policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ec8d-125">只有在已激活移动设备管理后，**设备安全策略**将显示在菜单中。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-125">The **Device security policies** will appear in the menu only after you have activated Mobile device management.</span></span> 
  
2. <span data-ttu-id="1ec8d-126">选择 **+ 创建策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-126">Choose **+ Create a policy**.</span></span>
    
    ![创建在设备安全策略下的 MDN 设备策略](media/fbcdbecd-0016-42f1-81a9-9fbad610da90.png)
  
3. <span data-ttu-id="1ec8d-128">为新策略，指定**名称**和**说明**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-128">Specify a **Name** and **Description** for the new policy, and then choose **Next**.</span></span>
    
    ![设置设备安全策略的名称](media/d382e845-4a7f-4f72-8a09-813ea4cbd0c4.png)
  
4. <span data-ttu-id="1ec8d-130">在**要在设备上有什么要求？** 页上，指定要应用于移动设备在组织中的要求，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-130">On the **What requirements do you want to have on devices?** page, specify the requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
    ![设置页上的设备安全策略](media/186b3bd5-5e3d-4059-978f-94113111a8ca.png)
  
5. <span data-ttu-id="1ec8d-132">在**您想要配置？** 页上，指定要应用于移动设备在组织中任何其他要求，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-132">On the **What do you want to configure?** page, specify any additional requirements you want applied to mobile devices in your organization, and then choose **Next**.</span></span>
    
6. <span data-ttu-id="1ec8d-133">在**是否要立即应用此策略？** 页上，选择**是**，，然后选择 **+ 添加**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-133">On the **Do you want to apply this policy now?** page, choose **Yes**, and then choose **+ Add**.</span></span> 
    
    ![添加策略](media/89ab7cab-1b7a-4c78-9aa6-3db7d7667f8e.png)
  
7. <span data-ttu-id="1ec8d-135">选择之前将其部署到您的组织，然后选择**添加**将测试策略的组。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-135">Select the group(s) who will test the policy before you deploy it to your organization, and then choose **Add**.</span></span>
    
8. <span data-ttu-id="1ec8d-136">选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-136">Choose **Next**.</span></span>
    
9. <span data-ttu-id="1ec8d-137">查看并确认新的设备策略的详细信息，然后选择**创建此策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-137">Review and confirm the details of the new device policy, and then choose **Create this policy**.</span></span>
    
    ![选择创建创建设备策略 finsih 到此策略](media/e410bcf3-8a36-44ed-9fea-00e742db06fb.png)
  
10. <span data-ttu-id="1ec8d-139">单击“关闭”****。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-139">Click **Close**.</span></span>
    
<span data-ttu-id="1ec8d-p108">将策略应用于每个用户将具有推送到其设备的下次登录到 Office 365 使用其移动设备策略。如果用户没有应用到之前其移动设备的策略，然后部署策略之后, 他们将获得通知包括[注册和激活 MDM for Office 365 步骤](https://go.microsoft.com/fwlink/?LinkId=615272)其设备上。直到它们完成注册，请访问电子邮件、 OneDrive 和其他服务会受到限制。它们完成注册使用 Intune 的公司门户应用程序后，他们将能够使用的服务，该策略将应用于其设备。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p108">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 using their mobile device. If users haven't had a policy applied to their mobile device before, then after you deploy the policy, they'll get a notification on their device that includes the [steps to enroll and activate MDM for Office 365](https://go.microsoft.com/fwlink/?LinkId=615272). Until they complete enrollment, access to email, OneDrive, and other services will be restricted. After they complete enrollment using the Intune Company Portal app, they'll be able to use the services and the policy will be applied to their device.</span></span>
  
## <a name="step-2-verify-your-policy-works"></a><span data-ttu-id="1ec8d-144">步骤 2： 验证策略的工作原理</span><span class="sxs-lookup"><span data-stu-id="1ec8d-144">Step 2: Verify your policy works</span></span>

<span data-ttu-id="1ec8d-145">您已创建的安全策略后，您应该检查策略能够按预期之前将其部署到您的组织的正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-145">After you've created a security policy, you should check that the policy works as you expect before you deploy it to your organization.</span></span>
  
1. <span data-ttu-id="1ec8d-146">在 Office 365 中，转到**安全&amp;合规性中心** \> **数据丢失防护** \> **设备管理**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-146">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention** \> **Device management**.</span></span>
    
2. <span data-ttu-id="1ec8d-p109">在**Office 365 的移动设备管理**页上，选中应用策略的用户设备的状态。您可以筛选或排序的**所有**若要查看所有设备或**已阻止**查看阻止的设备。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p109">On the **Mobile Device Management for Office 365** page, Check the status of user devices that have the policy applied. You can filter or sort by **All** to view all devices, or **Blocked** to view blocked devices.</span></span> 
    
    ![查看由 MDM 管理的设备](media/5c9fd069-b716-40d8-9b36-f9cfeae2139f.png)
  
3. <span data-ttu-id="1ec8d-p110">您还可以执行完整还是选择性擦除设备上。有关说明，请参阅[擦除 Office 365 中的移动设备](wipe-a-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p110">You can also do a full or selective wipe on the device. For instructions, see [Wipe a mobile device in Office 365](wipe-a-mobile-device.md).</span></span>
    
## <a name="step-3-deploy-a-policy-to-your-organization"></a><span data-ttu-id="1ec8d-152">步骤 3： 向您的组织部署策略</span><span class="sxs-lookup"><span data-stu-id="1ec8d-152">Step 3: Deploy a policy to your organization</span></span>

<span data-ttu-id="1ec8d-153">您已创建移动设备策略，并验证其预期的工作方式后，将其部署到您的组织。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-153">After you've created a mobile device policy and verified that it works as expected, deploy it to your organization.</span></span>
  
1. <span data-ttu-id="1ec8d-154">在 Office 365 中，转到**安全&amp;合规性中心** \> **数据丢失防护**\> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-154">In Office 365, go to **Security &amp; Compliance Center** \> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="1ec8d-155">选择您想要部署的策略，然后选择**编辑策略**中\<  _策略名称_\>面板。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-155">Select the policy you want to deploy, and choose **Edit policy** in the \<  _policy name_\> panel.</span></span>
    
3. <span data-ttu-id="1ec8d-156">选择**部署**选项卡。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-156">Select the **Deployment** tab.</span></span> 
    
4. <span data-ttu-id="1ec8d-157">在**部署**选项卡中，选择**** 上方**选择一个或多个安全组包含您想要应用到此策略的人员**，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-157">In the **Deployment** tab, choose **Yes** above **Select one or more security groups that contain the people you want to apply this policy to** and then **Add**.</span></span>
    
  - <span data-ttu-id="1ec8d-p111">在**选择组**面板中，您可以搜索要添加的组，可以由别名或按显示名称筛选。您还可以从**组**列表中添加的现有组。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p111">On the **Select Group** panel, you can search for a group to add, you can filter either by alias or by display name. You can also add an existing group from the **Groups** list.</span></span> 
    
    <span data-ttu-id="1ec8d-160">您可以添加多个组，以应用到的策略。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-160">You can add multiple groups to apply the policy to.</span></span>
    
    <span data-ttu-id="1ec8d-161">选择**添加**底部的面板。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-161">Choose **Add** on the bottom of the panel.</span></span> 
    
5. <span data-ttu-id="1ec8d-162">在**部署**选项卡上选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-162">Choose **Save** on the **Deployment** tab.</span></span> 
    
    ![向您的组织中部署 MDM 策略。](media/dc3e7fe5-201a-4e45-abe3-fc93e0b59028.png)
  
<span data-ttu-id="1ec8d-p112">将策略应用于每个用户将具有推送到其设备的下次登录到 Office 365 从其移动设备策略。如果用户没有应用到其移动设备的策略，它们将与注册和为 MDM 激活的 Office 365 步骤[获取其设备上的通知](https://go.microsoft.com/fwlink/?LinkId=615272)。他们已完成注册后，该策略将应用到其设备。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p112">Each user that the policy applies to will have the policy pushed to their device the next time they sign in to Office 365 from their mobile device. If users haven't had a policy applied to their mobile device, they'll [get a notification on their device](https://go.microsoft.com/fwlink/?LinkId=615272) with steps to enroll and activate it for MDM for Office 365. After they've completed the enrollment, the policy will be applied to their device.</span></span> 
  
## <a name="step-4-block-email-access-for-unsupported-devices"></a><span data-ttu-id="1ec8d-167">不受支持的设备访问的步骤 4： 阻止电子邮件</span><span class="sxs-lookup"><span data-stu-id="1ec8d-167">Step 4: Block email access for unsupported devices</span></span>

<span data-ttu-id="1ec8d-p113">若要有助于保护组织的信息，您应阻止应用程序访问 Office 365 电子邮件的 Office 365 MDM 不支持的移动设备。支持的设备的列表，请参阅[Office 365 的内置移动设备管理功能](capabilities-of-mobile-device-management.md)。若要此操作：</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p113">To help secure your organization's information, you should block app access to Office 365 email for mobile devices that are not supported by MDM for Office 365. See [Capabilities of built-in Mobile Device Management for Office 365](capabilities-of-mobile-device-management.md) for a list of devices that are supported. To do this:</span></span> 
  
1. <span data-ttu-id="1ec8d-171">转到安全&amp;合规性中心\>**数据丢失防护**\> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-171">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="1ec8d-172">选择**管理组织范围内的设备访问设置**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-172">Select **Manage organization-wide device access settings**.</span></span>
    
    ![转到合规性中心\>设备和单击链接的管理设备访问设置。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="1ec8d-174">若要阻止不支持的设备，请选择**如果设备不支持 Office 365 MDM 是否要允许或阻止其使用 Exchange 帐户访问您组织的电子邮件**下的**块** \> **保存**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-174">To block unsupported devices, choose **Block** under **If a device isn't supported by MDM for Office 365, do you want to allow or block it from using an Exchange account to access your organization's email** \> **Save**.</span></span>
  
## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a><span data-ttu-id="1ec8d-175">步骤 5：选择要从条件访问检查中排除的安全组</span><span class="sxs-lookup"><span data-stu-id="1ec8d-175">Step 5: Choose security groups to be excluded from conditional access checks</span></span>

<span data-ttu-id="1ec8d-p114">如果您要从他们的移动设备上的条件访问检查中排除某些人员，并且已为这些人员创建了一个或多个安全组，则在此处添加安全组。这些组中的人员将不会为其受支持的移动设备执行任何策略。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p114">If you want to exclude some people from conditional access checks on their mobile devices and you've created one or more security groups for those people, add the security groups here. The people in these groups will not have any policies enforced for their supported mobile devices.</span></span>
  
1. <span data-ttu-id="1ec8d-178">转到安全&amp;合规性中心\>**数据丢失防护**\> **设备安全策略**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-178">Go to Security &amp; Compliance Center\> **Data loss prevention**\> **Device security policies**.</span></span>
    
2. <span data-ttu-id="1ec8d-179">选择**管理组织范围内的设备访问设置**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-179">Select **Manage organization-wide device access settings**.</span></span>
    
    ![转到合规性中心\>设备和单击链接的管理设备访问设置。](media/b9f4da3c-dfa5-4913-8482-42a077cb4f56.png)
  
3. <span data-ttu-id="1ec8d-p115">选择**添加**以添加您想要从被排除的用户的安全组阻止到 Office 365 的访问。在用户添加到此列表后，他们将能够访问 Office 365 电子邮件时使用的不受支持的设备。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p115">Select **Add** to add the security group that has users that you'd like to exclude from being blocked access to Office 365. When a user has been added to this list, they'll be able to access Office 365 email when using an unsupported device.</span></span> 
    
4. <span data-ttu-id="1ec8d-183">选择您想要使用**选择组**面板中的安全组。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-183">Select the security group you want to use in the **Select group** panel.</span></span> 
    
5. <span data-ttu-id="1ec8d-184">选择的名称，然后**添加** \> **保存**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-184">Select the name, and then **Add** \> **Save**.</span></span>
    
6. <span data-ttu-id="1ec8d-185">在**组织范围内设备访问设置**面板中，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-185">On the **Organization-wide device access settings** panel, choose **Save**.</span></span>
  
## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a><span data-ttu-id="1ec8d-186">安全策略对不同设备类型的影响是什么？</span><span class="sxs-lookup"><span data-stu-id="1ec8d-186">What is the impact of security policies on different device types?</span></span>

<span data-ttu-id="1ec8d-p116">将策略应用于用户的设备时，对每个设备的影响在不同的设备类型之间将稍有不同。请查看以下示例表，了解策略对不同设备的影响。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p116">When you apply a policy to user devices, the impact on each device varies somewhat between different device types. See the following table for examples of the impact of policies on different devices.</span></span>
  


|<span data-ttu-id="1ec8d-189">**安全策略**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-189">**Security Policy**</span></span>|<span data-ttu-id="1ec8d-190">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-190">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="1ec8d-191">**Android 4+**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-191">**Android 4+**</span></span>|<span data-ttu-id="1ec8d-192">**三星 Knox**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-192">**Samsung Knox**</span></span>|<span data-ttu-id="1ec8d-193">**IOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-193">**IOS 6+**</span></span>|<span data-ttu-id="1ec8d-194">**备注**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-194">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ec8d-195">需要加密备份</span><span class="sxs-lookup"><span data-stu-id="1ec8d-195">Require encrypted backup</span></span>  <br/> |<span data-ttu-id="1ec8d-196">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-196">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-197">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-197">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-198">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-198">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-199">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-199">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-200">所需的 IOS 加密备份。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-200">IOS encrypted backup required.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-201">阻止云备份</span><span class="sxs-lookup"><span data-stu-id="1ec8d-201">Block cloud backup</span></span>  <br/> |<span data-ttu-id="1ec8d-202">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-202">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-203">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-203">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-204">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-204">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-205">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-205">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-206">阻止在 Android 上进行 Google 备份（灰显），阻止在 iOS 上进行云备份。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-206">Block Google backup on Android (grayed out), cloud backup on iOS.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-207">阻止文档同步</span><span class="sxs-lookup"><span data-stu-id="1ec8d-207">Block document synchronization</span></span>  <br/> |<span data-ttu-id="1ec8d-208">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-208">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-209">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-209">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-210">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-210">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-211">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-211">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-212">iOS：阻止云中的文档。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-212">iOS: Block documents in the cloud.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-213">阻止照片同步</span><span class="sxs-lookup"><span data-stu-id="1ec8d-213">Block photo synchronization</span></span>  <br/> |<span data-ttu-id="1ec8d-214">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-214">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-215">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-215">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-216">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-216">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-217">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-217">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-218">iOS（本机）：阻止照片流。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-218">iOS (native): Block Photo Stream.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-219">阻止屏幕捕获</span><span class="sxs-lookup"><span data-stu-id="1ec8d-219">Block screen capture</span></span>  <br/> |<span data-ttu-id="1ec8d-220">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-220">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-221">X</span><span class="sxs-lookup"><span data-stu-id="1ec8d-221">X</span></span>  <br/> |<span data-ttu-id="1ec8d-222">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-222">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-223">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-223">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-224">在尝试时被阻止。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-224">Blocked when attempted.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-225">阻止视频会议</span><span class="sxs-lookup"><span data-stu-id="1ec8d-225">Block video conference</span></span>  <br/> |<span data-ttu-id="1ec8d-226">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-226">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-227">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-227">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-228">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-228">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-229">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-229">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-230">FaceTime 在 iOS 上会被阻止，而 Skype 或其他则不会。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-230">FaceTime blocked on iOS, not Skype or others.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-231">阻止发送诊断数据</span><span class="sxs-lookup"><span data-stu-id="1ec8d-231">Block sending diagnostic data</span></span>  <br/> |<span data-ttu-id="1ec8d-232">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-232">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-233">X</span><span class="sxs-lookup"><span data-stu-id="1ec8d-233">X</span></span>  <br/> |<span data-ttu-id="1ec8d-234">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-234">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-235">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-235">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-236">阻止在 Android 上发送 Google 故障报告。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-236">Block sending Google crash report on Android.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-237">阻止对应用商店的访问</span><span class="sxs-lookup"><span data-stu-id="1ec8d-237">Block access to app store</span></span>  <br/> |<span data-ttu-id="1ec8d-238">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-238">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-239">X</span><span class="sxs-lookup"><span data-stu-id="1ec8d-239">X</span></span>  <br/> |<span data-ttu-id="1ec8d-240">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-240">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-241">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-241">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-242">应用商店图标在 Android 主页上缺失，在 Windows 上禁用，在 iOS 上缺失。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-242">App store icon missing on Android home page, disabled on Windows, missing on iOS.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-243">要求提供应用商店的密码</span><span class="sxs-lookup"><span data-stu-id="1ec8d-243">Require password for app store</span></span>  <br/> |<span data-ttu-id="1ec8d-244">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-244">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-245">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-245">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-246">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-246">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-247">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-247">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-248">iOS：购买 iTunes 所需的密码。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-248">iOS: Password required for iTunes purchases.</span></span>  <br/> |
|<span data-ttu-id="1ec8d-249">阻止连接到可移动存储</span><span class="sxs-lookup"><span data-stu-id="1ec8d-249">Block connection to removable storage</span></span>  <br/> |<span data-ttu-id="1ec8d-250">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-250">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-251">X</span><span class="sxs-lookup"><span data-stu-id="1ec8d-251">X</span></span>  <br/> |<span data-ttu-id="1ec8d-252">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-252">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-253">不适用</span><span class="sxs-lookup"><span data-stu-id="1ec8d-253">NA</span></span>  <br/> |<span data-ttu-id="1ec8d-254">Android：SD 卡将呈灰色显示在设置中，Windows 通知用户，安装在那里的应用不可用</span><span class="sxs-lookup"><span data-stu-id="1ec8d-254">Android: SD card will be grayed out in settings, Windows notifies user, apps installed there are not available</span></span>  <br/> |
|<span data-ttu-id="1ec8d-255">阻止蓝牙连接</span><span class="sxs-lookup"><span data-stu-id="1ec8d-255">Block Bluetooth connection</span></span>  <br/> |<span data-ttu-id="1ec8d-256">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-256">✔</span></span>  <br/> |\*\*\*  <br/> |\*\*\*  <br/> |<span data-ttu-id="1ec8d-257">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-257">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-p117">\*\*\*我们不能为 Android 上设置禁用蓝牙。相反，我们禁用需要蓝牙的所有事务： 高级音频通讯组、 音频/视频远程控制、 免提设备、 耳麦、 通讯簿访问和串行端口。使用下列任一时，小型 toast 消息将显示在页面底部。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p117">\*\*\*We can't disable BlueTooth as a setting on Android. Instead, we disable all the transactions that require BlueTooth: Advanced Audio Distribution, Audio/Video Remote Control, hands-free devices, headset, Phone Book Access, and Serial Port. A small toast message appears at the bottom of the page when any of these are used.</span></span>  <br/> |
   
## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a><span data-ttu-id="1ec8d-261">当您删除策略或从策略中删除用户时，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="1ec8d-261">What happens when you delete a policy or remove a user from the policy?</span></span>

<span data-ttu-id="1ec8d-p118">当您删除策略，或从策略已部署到组中删除用户时，策略设置、 Office 365 电子邮件配置文件和缓存的电子邮件可能会删除从用户的设备。请参阅下表，请参阅什么删除了不同的设备类型：</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p118">When you delete a policy or remove a user from a group to which the policy was deployed to, the policy settings, Office 365 email profile and cached emails may be removed from the user's device. See the following table to see what is removed for the different device types:</span></span>
  
|<span data-ttu-id="1ec8d-264">**删除的内容**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-264">**What's removed**</span></span>|<span data-ttu-id="1ec8d-265">**Windows Phone 8.1 +**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-265">**Windows Phone 8.1+**</span></span>|<span data-ttu-id="1ec8d-266">**iOS 6 +**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-266">**iOS 6+**</span></span>|<span data-ttu-id="1ec8d-267">**Android 4 + （包括三星 Knox）**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-267">**Android 4+ (including Samsung Knox)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ec8d-268">托管的电子邮件配置文件\*</span><span class="sxs-lookup"><span data-stu-id="1ec8d-268">Managed email profiles\*</span></span>  <br/> |<span data-ttu-id="1ec8d-269">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-269">✖</span></span>  <br/> |<span data-ttu-id="1ec8d-270">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-270">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-271">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-271">✖</span></span>  <br/> |
|<span data-ttu-id="1ec8d-272">策略设置</span><span class="sxs-lookup"><span data-stu-id="1ec8d-272">Policy settings</span></span>  <br/> |<span data-ttu-id="1ec8d-273">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-273">✔</span></span>  <br/>           <span data-ttu-id="1ec8d-274">除**块从设备发送诊断数据。**</span><span class="sxs-lookup"><span data-stu-id="1ec8d-274">Except for **Block sending diagnostic data from device.**</span></span> <br/> |<span data-ttu-id="1ec8d-275">✔</span><span class="sxs-lookup"><span data-stu-id="1ec8d-275">✔</span></span>  <br/> |<span data-ttu-id="1ec8d-276">✖</span><span class="sxs-lookup"><span data-stu-id="1ec8d-276">✖</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1ec8d-277">\*如果策略已部署选项**托管电子邮件配置文件**，然后选择的托管电子邮件配置文件和缓存电子邮件，将从用户的设备中删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-277">\*If the policy was deployed with the option **Email profile is managed** selected, then the managed email profile and cached emails in that profile will be deleted from the user's device.</span></span> 
  
<span data-ttu-id="1ec8d-p119">已删除的策略应用于每个用户可以从其设备的下次其移动设备使用 MDM 检查 Office 365 中删除的策略。如果您部署新的策略应用于这些用户的设备，他们将提示您重新注册 MDM 在 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-p119">Each user that the removed policy applied to will have the policy removed from their device the next time their mobile device checks in with MDM for Office 365 . If you deploy a new policy that applies to these users' devices, they'll be prompted to re-enroll in MDM for Office 365.</span></span>
  
<span data-ttu-id="1ec8d-280">您还可以[擦除设备](wipe-a-mobile-device.md)，或者完全，或有选择地擦除的设备的组织信息。</span><span class="sxs-lookup"><span data-stu-id="1ec8d-280">You can also [wipe a device](wipe-a-mobile-device.md), either completely, or selectively wipe organizational information from the device.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1ec8d-281">相关主题</span><span class="sxs-lookup"><span data-stu-id="1ec8d-281">Related Topics</span></span>

[<span data-ttu-id="1ec8d-282">Office 365 移动设备管理概述</span><span class="sxs-lookup"><span data-stu-id="1ec8d-282">Overview of Mobile Device Management for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="1ec8d-283">Office 365 移动设备管理功能</span><span class="sxs-lookup"><span data-stu-id="1ec8d-283">Capabilities of Mobile Device Management for Office 365</span></span>](capabilities-of-mobile-device-management.md)
  

