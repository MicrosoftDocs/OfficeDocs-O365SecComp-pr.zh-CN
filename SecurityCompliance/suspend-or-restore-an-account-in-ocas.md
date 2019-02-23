---
title: 暂停或还原 Office 365 云应用安全中的用户帐户
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 12/03/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5f02d20f-b9aa-4b2f-ad2d-506a4a3c4540
description: '使用 Office 365 云应用安全, 可以执行的调控操作是挂起或取消暂停用户帐户。 '
ms.openlocfilehash: 3650a5304af0440dc537610994c4bd827f599989
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215092"
---
# <a name="suspend-or-restore-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="57f3d-103">暂停或还原 Office 365 云应用安全中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="57f3d-103">Suspend or restore a user account in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="57f3d-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="57f3d-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="57f3d-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="57f3d-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="57f3d-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="57f3d-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="57f3d-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="57f3d-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="57f3d-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="57f3d-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="57f3d-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="57f3d-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="57f3d-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="57f3d-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="57f3d-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="57f3d-111">You are here!</span></span>  <br/> [<span data-ttu-id="57f3d-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="57f3d-112">Next steps</span></span>](suspend-or-restore-an-account-in-ocas.md#nextsteps) <br/> |
   
<span data-ttu-id="57f3d-p101">假设您收到一条警报, 指出您的组织的 Office 365 的用户帐户中有一个已损坏。或者, 假设您已收到指示用户帐户出错的警报。使用 Office 365 云应用安全, 你可以在调查你收到的通知后挂起用户帐户, 并在以后还原该帐户。</span><span class="sxs-lookup"><span data-stu-id="57f3d-p101">Suppose that you receive an alert that one of your organization's user accounts for Office 365 has been compromised. Or, suppose that you've received an alert that indicates something is wrong with a user account. With Office 365 Cloud App Security, you can suspend a user account and later restore it after you have investigated the alerts you receive.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57f3d-p102">office 365 企业版 E5 中提供了 office 365 云应用安全性。如果您的组织使用的是其他 office 365 企业版订阅, 则可以将 Office 365 云应用安全作为附加项购买。(作为全局管理员, 在 Office 365 管理中心中, 选择 "**付费** \> **添加订阅**"。)有关详细信息, 请参阅[office 365 Platform 服务说明: office 365 &amp;安全合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑 Office 365 for business 的加载](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)项。</span><span class="sxs-lookup"><span data-stu-id="57f3d-p102">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="to-suspend-a-user-account-in-office-365-cloud-app-security"></a><span data-ttu-id="57f3d-119">挂起 Office 365 Cloud App Security 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="57f3d-119">To suspend a user account in Office 365 Cloud App Security</span></span>

<span data-ttu-id="57f3d-p103">挂起用户帐户时, 将阻止用户再次登录。这与在 Office 365 中直接编辑用户帐户相同, 以将登录状态设置为 **"已阻止登录**"。</span><span class="sxs-lookup"><span data-stu-id="57f3d-p103">When you suspend a user account, you prevent the user from signing in again. It's the same as editing the user account directly in Office 365 to set the Sign-in status to **Sign-in blocked**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57f3d-p104">如果阻止用户登录 Office 365 (通过挂起用户或编辑其登录状态), 请注意, 可能需要一小时或更长时间才能对用户的所有设备和客户端 ([在 Office 365 中编辑或更改用户](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)) 进行操作。如果用户登录到 Office 365, 则当 Office 365 要求他们重新登录时, 该阻止才会生效。</span><span class="sxs-lookup"><span data-stu-id="57f3d-p104">If you block a user from signing in to Office 365, either by suspending them or by editing their sign-in status, be aware that it can take an hour or so to take effect on all of the user's devices and clients ([Edit or change a user in Office 365](https://support.office.com/article/42BB3F17-8F9D-4182-B434-5F1C8024E614#SingleUserPreview)). If the user is signed in to Office 365, the block will take effect whenever Office 365 requires them to sign in again.</span></span> 
  
1. <span data-ttu-id="57f3d-p105">作为[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md), 请转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。(这会将您带到&amp;安全合规中心。)</span><span class="sxs-lookup"><span data-stu-id="57f3d-p105">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account. (This takes you to the Security &amp; Compliance Center.)</span></span> 
    
2. <span data-ttu-id="57f3d-126">在 "安全&amp;合规性中心" 中, 选择 "**通知** \> " "**管理高级警报**"。</span><span class="sxs-lookup"><span data-stu-id="57f3d-126">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="57f3d-127">选择 "**转到 Office 365 云应用安全性**"。</span><span class="sxs-lookup"><span data-stu-id="57f3d-127">Choose **Go to Office 365 Cloud App Security**.</span></span><br><span data-ttu-id="57f3d-128">![在 "安全&amp;合规性中心" 中, 选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="57f3d-128">![In the Security &amp; Compliance Center, choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br>
  
4. <span data-ttu-id="57f3d-129">在屏幕顶部的导航栏中, 选择 "**通知**"。</span><span class="sxs-lookup"><span data-stu-id="57f3d-129">In the navigation bar across the top of the screen, choose **Alerts**.</span></span>
    
5. <span data-ttu-id="57f3d-130">在 "**通知**" 列中, 双击与特定用户帐户有关的警报。</span><span class="sxs-lookup"><span data-stu-id="57f3d-130">In the **Alert** column, double-click an alert that pertains to a specific user account.</span></span> 
    
6. <span data-ttu-id="57f3d-131">在 **"帐户**" 下的 "**状态**" 列![中,](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \>选择 "设置设置" 图标 "**暂停用户**"。</span><span class="sxs-lookup"><span data-stu-id="57f3d-131">Under **Accounts**, in the **Status** column, choose Settings ![settings icon](media/e01b75cc-b28f-4b83-8f86-b1b13dc27ab2.png) \> **Suspend user**.</span></span>
    
## <a name="to-restore-a-user-account"></a><span data-ttu-id="57f3d-132">还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="57f3d-132">To restore a user account</span></span>

<span data-ttu-id="57f3d-133">请参阅[在 Office 365 中还原用户](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span><span class="sxs-lookup"><span data-stu-id="57f3d-133">See [Restore a user in Office 365](https://support.office.com/article/2c261e42-5dd1-48b0-845f-2a016d29cfc1)</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="57f3d-134">后续步骤</span><span class="sxs-lookup"><span data-stu-id="57f3d-134">Next steps</span></span>

- [<span data-ttu-id="57f3d-135">查看 Office 365 云应用安全中的警报并执行相应操作</span><span class="sxs-lookup"><span data-stu-id="57f3d-135">Review and take action on alerts in Office 365 Cloud App Security</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="57f3d-136">使用 Office 365 云应用安全管理 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="57f3d-136">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
    
- <span data-ttu-id="57f3d-137">查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)</span><span class="sxs-lookup"><span data-stu-id="57f3d-137">Review your [utilization activities for Office 365 Cloud App Security](utilization-activities-for-ocas.md)</span></span>
    

