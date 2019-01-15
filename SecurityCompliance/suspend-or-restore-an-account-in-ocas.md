---
title: 暂停或还原 Office 365 云应用安全中的用户帐户
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: '与 Office 365 云应用程序安全性，您可以采取的治理操作的挂起或 unsuspend 的用户帐户。 '
ms.openlocfilehash: 09d6ae870aa1a6b0a619ccf20f8cc19b392e23a8
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014844"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="bbf03-103">暂停或还原 Office 365 云应用安全中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="bbf03-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="bbf03-104">Office 365 高级安全管理现在是 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="bbf03-104">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="bbf03-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bbf03-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="bbf03-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bbf03-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="bbf03-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="bbf03-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="bbf03-108">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="bbf03-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="bbf03-109">启动评估</span><span class="sxs-lookup"><span data-stu-id="bbf03-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="bbf03-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="bbf03-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="bbf03-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="bbf03-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="bbf03-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="bbf03-112">You are here!</span></span>  <br/> [<span data-ttu-id="bbf03-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bbf03-113">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="bbf03-p101">假定收到一个 Office 365 组织的用户帐户已泄露的警报。或者，假设您已收到一条警报，指示有问题的用户帐户。与 Office 365 云应用程序安全性，可以挂起的用户帐户和更高版本将其还原后调查收到通知。</span><span class="sxs-lookup"><span data-stu-id="bbf03-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbf03-p102">Office 365 云应用程序安全性是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 云应用程序安全性。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="bbf03-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="bbf03-120">Office 365 云应用程序安全性挂起的用户帐户</span><span class="sxs-lookup"><span data-stu-id="bbf03-120">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="bbf03-p103">当您挂起的用户帐户时，可以防止用户再次登录。已编辑的用户帐户直接的 Office 365 设置为**登录被阻止**的登录状态相同。</span><span class="sxs-lookup"><span data-stu-id="bbf03-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bbf03-p104">如果您阻止用户与登录到 Office 365 中，通过这些挂起或通过编辑其登录状态，请注意，可能需要一小时或这样才会生效上所有用户的设备和客户端 （[编辑或更改 Office 365 中的用户](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)）。如果用户登录到 Office 365，阻止将会生效，只要 Office 365 要求其再次登录。</span><span class="sxs-lookup"><span data-stu-id="bbf03-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="bbf03-p105">作为[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md)，请转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。(您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="bbf03-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="bbf03-127">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="bbf03-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="bbf03-128">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="bbf03-128">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="bbf03-129">![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="bbf03-129">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="bbf03-130">在屏幕顶部导航栏中，选择**通知**。</span><span class="sxs-lookup"><span data-stu-id="bbf03-130">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="bbf03-131">在**通知**列中，双击警报与特定的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bbf03-131">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="bbf03-132">在**帐户**下的**状态**列中，选择设置![设置图标](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **挂起用户**。</span><span class="sxs-lookup"><span data-stu-id="bbf03-132">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="bbf03-133">若要还原的用户帐户</span><span class="sxs-lookup"><span data-stu-id="bbf03-133">To restore a user account</span></span>

<span data-ttu-id="bbf03-134">请参阅[还原 Office 365 中的用户](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="bbf03-134">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="bbf03-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bbf03-135">Next steps</span></span>

- [<span data-ttu-id="bbf03-136">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="bbf03-136">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="bbf03-137">使用 Office 365 云应用安全管理 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="bbf03-137">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="bbf03-138">查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="bbf03-138">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

