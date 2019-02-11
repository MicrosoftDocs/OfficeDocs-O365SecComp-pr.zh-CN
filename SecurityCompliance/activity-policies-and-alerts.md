---
title: Office 365 云应用安全中的活动策略和警报
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定义与 Office 365 云应用程序安全性设置通知以触发特定活动发生或过于频繁发生时的活动策略。通过设置以触发通知的策略，您可以通知有关和监视特定活动。
ms.openlocfilehash: af364e7ff96f6d18b60d3267c5992d4c5533ea8c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29604089"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="4d02d-104">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="4d02d-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

<span data-ttu-id="4d02d-105">Office 365 高级安全管理现在是 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="4d02d-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="4d02d-106">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4d02d-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="4d02d-107">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4d02d-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="4d02d-108">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="4d02d-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="4d02d-109">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="4d02d-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="4d02d-110">启动评估</span><span class="sxs-lookup"><span data-stu-id="4d02d-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="4d02d-111">开始规划</span><span class="sxs-lookup"><span data-stu-id="4d02d-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="4d02d-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="4d02d-112">You are here!</span></span>  <br/> [<span data-ttu-id="4d02d-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4d02d-113">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="4d02d-114">开始利用</span><span class="sxs-lookup"><span data-stu-id="4d02d-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="4d02d-p102">与 Office 365 云应用程序安全性，高级的云管理策略触发特定的活动发生或过于频繁发生的通知。例如，假设用户尝试登录到 Office 365，并在一分钟内 70 时间失败。假设另一个用户下载 7,000 文件，或显示为从加拿大时登录该用户应该位于另一个位置。或糟糕的是，假设已泄露某人的帐户，攻击者在使用该帐户访问您组织的云应用程序和敏感数据。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="4d02d-p103">如果您是[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md)，活动警报通知您事件，如这些时出现。您然后可以执行特定操作，如挂起的用户帐户，直到您可以调查发生了什么变化。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4d02d-p104">Office 365 云应用程序安全性策略是不同[警报策略在 Office 365 安全性&amp;合规性中心](alert-policies.md)。本文中所述的策略在 Office 365 云应用程序安全性门户中，定义和可帮助您更好的活动管理组织的云环境。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="4d02d-123">准备工作</span><span class="sxs-lookup"><span data-stu-id="4d02d-123">Before you begin</span></span>

<span data-ttu-id="4d02d-124">请确保：</span><span class="sxs-lookup"><span data-stu-id="4d02d-124">Make sure that:</span></span>
  
- <span data-ttu-id="4d02d-125">您的组织具有[Office 365 云应用程序安全性](office-365-cas-overview.md)，并且该服务[开启](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="4d02d-125">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="4d02d-126">[审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态的 Office 365 环境。</span><span class="sxs-lookup"><span data-stu-id="4d02d-126">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="4d02d-127">您是全局管理员或 Office 365 安全管理员。</span><span class="sxs-lookup"><span data-stu-id="4d02d-127">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="4d02d-128">创建新的活动策略</span><span class="sxs-lookup"><span data-stu-id="4d02d-128">Create a new activity policy</span></span>

1. <span data-ttu-id="4d02d-129">以全局管理员或 security 管理员程序中，转到云应用程序安全性门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 和登录。</span><span class="sxs-lookup"><span data-stu-id="4d02d-129">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> <br><span data-ttu-id="4d02d-130">您将转到 Office 365 云应用程序安全策略页。</span><span class="sxs-lookup"><span data-stu-id="4d02d-130">This takes you to the Office 365 Cloud App Security Policies page.</span></span><br><span data-ttu-id="4d02d-131">![当您转到 Office 365 云应用程序安全性门户时，启动与策略页](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="4d02d-131">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span>
  
2. <span data-ttu-id="4d02d-132">单击**创建策略**，，然后选择**活动策略**。</span><span class="sxs-lookup"><span data-stu-id="4d02d-132">Click **Create policy**, and then select **Activity policy**.</span></span><br><span data-ttu-id="4d02d-133">![在 O365 CAS 创建策略时，您可以选择活动策略和异常检测策略。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span><span class="sxs-lookup"><span data-stu-id="4d02d-133">![When you create a policy in O365 CAS, you can choose between Activity policies and Anomaly Detection policies.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span></span>
  
3. <span data-ttu-id="4d02d-p105">在**创建活动策略**页中，指定**策略名称**和**说明**。若要在默认模板上基于您的策略，请在**策略模板**列表中，选择一个或不使用模板创建您自己的策略。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span><br><span data-ttu-id="4d02d-136">![您可以与 Office 365 云应用程序安全性创建活动策略。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span><span class="sxs-lookup"><span data-stu-id="4d02d-136">![You can create activity policies with Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span></span>
  
4. <span data-ttu-id="4d02d-p106">选择**策略严重性**（低、 中或高） 的度量如何严重其将您如果此策略会触发一条通知。这将帮助您筛选警报时正在查看其更高版本。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
5. <span data-ttu-id="4d02d-p107">选择该策略的一个**类别**。这将帮助您筛选和排序的已触发通知或组策略时正在查看其进行更改。</span><span class="sxs-lookup"><span data-stu-id="4d02d-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
6. <span data-ttu-id="4d02d-141">选择**活动筛选器**设置其他操作或将触发通知基于此策略的指标。</span><span class="sxs-lookup"><span data-stu-id="4d02d-141">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
7. <span data-ttu-id="4d02d-142">下**活动匹配参数**，指定单个活动匹配筛选器时，将触发策略违规还是指定的数量的重复活动需要先触发警报。</span><span class="sxs-lookup"><span data-stu-id="4d02d-142">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span><br><span data-ttu-id="4d02d-143">如果您选择**Repeated 活动**，请指定活动，时间段的数目和冲突的特定应用程序中的用户或任何应用程序的相同用户是否对计数。</span><span class="sxs-lookup"><span data-stu-id="4d02d-143">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
8. <span data-ttu-id="4d02d-144">（可选） 您可以选择要创建其他通知以接收通知 （通过电子邮件、 文本消息，或两者） 此策略中的**创建通知**。</span><span class="sxs-lookup"><span data-stu-id="4d02d-144">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span><br><span data-ttu-id="4d02d-145">**请确保您的电子邮件提供商不阻止发送的电子邮件`no-reply@cloudappsecurity.com`**。</span><span class="sxs-lookup"><span data-stu-id="4d02d-145">**Make sure that your email provider doesn't block emails sent from `no-reply@cloudappsecurity.com`**.</span></span> 
  
9. <span data-ttu-id="4d02d-146">选择触发挂起用户或需要用户再次登录到 Office 365 应用程序时应采取的**操作**。</span><span class="sxs-lookup"><span data-stu-id="4d02d-146">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
10. <span data-ttu-id="4d02d-147">选择**创建**以完成创建您的策略。</span><span class="sxs-lookup"><span data-stu-id="4d02d-147">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="4d02d-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4d02d-148">Next steps</span></span>

- [<span data-ttu-id="4d02d-149">异常检测策略</span><span class="sxs-lookup"><span data-stu-id="4d02d-149">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="4d02d-150">将 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="4d02d-150">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="4d02d-151">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="4d02d-151">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="4d02d-152">若要简化管理您 IP 地址进行分组</span><span class="sxs-lookup"><span data-stu-id="4d02d-152">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

