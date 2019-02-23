---
title: Office 365 云应用安全中的活动策略和警报
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 使用 Office 365 云应用安全性定义活动策略, 以设置在特定活动发生或发生过于频繁时触发的警报。通过设置策略来触发通知, 可以通知并监视特定活动。
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219762"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a><span data-ttu-id="660e3-104">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="660e3-104">Activity policies and alerts in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="660e3-105">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="660e3-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="660e3-106">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="660e3-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="660e3-107">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="660e3-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="660e3-108">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="660e3-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="660e3-109">开始评估</span><span class="sxs-lookup"><span data-stu-id="660e3-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="660e3-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="660e3-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="660e3-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="660e3-111">You are here!</span></span>  <br/> [<span data-ttu-id="660e3-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="660e3-112">Next step</span></span>](anomaly-detection-policies-in-ocas.md) <br/> |[<span data-ttu-id="660e3-113">开始利用</span><span class="sxs-lookup"><span data-stu-id="660e3-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="660e3-p102">借助 Office 365 云应用安全性, 高级云管理策略将触发发生或发生过于频繁的特定活动的警报。例如, 假设用户尝试登录到 Office 365, 并在一分钟内失败70次。假设另一位用户下载7000文件, 或看起来像是从加拿大登录, 而该用户应位于另一个位置。或者更糟的是, 假设某人的帐户受到威胁, 并且攻击者使用该帐户访问您组织的云应用程序和敏感数据。</span><span class="sxs-lookup"><span data-stu-id="660e3-p102">With Office 365 Cloud App Security, advanced cloud management policies trigger alerts for specific activities that happen or happen too frequently. For example, suppose a user tries to sign in to Office 365 and fails 70 times in one minute. Suppose that another user downloads 7,000 files, or appears to be signed in from Canada, when that user is supposed to be in another location. Or worse, suppose that someone's account has been compromised, and an attacker is using that account to access your organization's cloud apps and sensitive data.</span></span>
  
<span data-ttu-id="660e3-p103">如果您是[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md), 活动警报会在发生类似事件时通知您。然后, 您可以执行特定操作, 如挂起用户帐户, 直到您能够调查所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="660e3-p103">If you are a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), activity alerts notify you when events like these occur. You can then take specific actions, such as suspending a user account until you can investigate what happened.</span></span>
  
> [!NOTE]
> <span data-ttu-id="660e3-p104">office 365 云应用安全策略与[office 365 安全&amp;合规中心中的警报策略](alert-policies.md)不同。本文中所述的活动策略在 Office 365 云应用安全门户中定义, 可帮助您更好地管理组织的云环境。</span><span class="sxs-lookup"><span data-stu-id="660e3-p104">Office 365 Cloud App Security policies are different from [alert policies in the Office 365 Security &amp; Compliance Center](alert-policies.md). The activity policies described in this article are defined in the Office 365 Cloud App Security portal, and can help you better manage your organization's cloud environment.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="660e3-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="660e3-122">Before you begin</span></span>

<span data-ttu-id="660e3-123">请确保：</span><span class="sxs-lookup"><span data-stu-id="660e3-123">Make sure that:</span></span>
  
- <span data-ttu-id="660e3-124">您的组织具有[Office 365 云应用安全性](office-365-cas-overview.md), 并且该服务已[打开](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="660e3-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="660e3-125">已为您的 Office 365 环境启用[审核日志记录](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="660e3-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="660e3-126">您是 Office 365 的全局管理员或安全管理员。</span><span class="sxs-lookup"><span data-stu-id="660e3-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="create-a-new-activity-policy"></a><span data-ttu-id="660e3-127">创建新的活动策略</span><span class="sxs-lookup"><span data-stu-id="660e3-127">Create a new activity policy</span></span>

1. <span data-ttu-id="660e3-128">作为全局管理员或安全管理员, 请转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="660e3-128">As a global administrator or security administrator, go to the Cloud App Security portal ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) and sign in.</span></span> <br><span data-ttu-id="660e3-129">将转到 "Office 365 云应用安全策略" 页。</span><span class="sxs-lookup"><span data-stu-id="660e3-129">This takes you to the Office 365 Cloud App Security Policies page.</span></span><br><span data-ttu-id="660e3-130">![当您转到 Office 365 云应用安全门户时, 将从 "策略" 页开始](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="660e3-130">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span>
  
2. <span data-ttu-id="660e3-131">单击 "**创建策略**", 然后选择 "**活动策略**"。</span><span class="sxs-lookup"><span data-stu-id="660e3-131">Click **Create policy**, and then select **Activity policy**.</span></span><br><span data-ttu-id="660e3-132">![在 O365 CAS 中创建策略时, 可以在活动策略和异常情况检测策略之间进行选择。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span><span class="sxs-lookup"><span data-stu-id="660e3-132">![When you create a policy in O365 CAS, you can choose between Activity policies and Anomaly Detection policies.](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)</span></span>
  
3. <span data-ttu-id="660e3-p105">在 "**创建活动策略**" 页上, 指定**策略名称**和**说明**。若要将策略基于默认模板, 请在 "**策略模板**" 列表中选择一个模板, 或在不使用模板的情况下创建自己的策略。</span><span class="sxs-lookup"><span data-stu-id="660e3-p105">On the **Create activity policy** page, specify the **Policy name** and **Description**. To base your policy on a default template, choose one in the **Policy template** list, or create your own policy without using a template.</span></span><br><span data-ttu-id="660e3-135">![您可以使用 Office 365 云应用安全性创建活动策略。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span><span class="sxs-lookup"><span data-stu-id="660e3-135">![You can create activity policies with Office 365 Cloud App Security.](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)</span></span>
  
4. <span data-ttu-id="660e3-p106">选择**策略严重性**(低、中或高), 以衡量在此策略触发警报时对您有多严重。这将帮助您在以后查看警报时对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="660e3-p106">Choose a **Policy severity** (Low, Medium, or High) that measures how serious it is to you if this policy triggers an alert. This will help you filter alerts when you're reviewing them later.</span></span> 
    
5. <span data-ttu-id="660e3-p107">为此策略选择一个**类别**。这将帮助您筛选和排序已触发的警报, 或在审阅以进行更改时对策略进行分组。</span><span class="sxs-lookup"><span data-stu-id="660e3-p107">Choose a **Category** for this policy. This will help you filter and sort alerts that have been triggered, or to group policies when you're reviewing them to make changes.</span></span> 
    
6. <span data-ttu-id="660e3-140">选择 "**活动筛选器**" 以设置将触发基于此策略的警报的其他操作或指标。</span><span class="sxs-lookup"><span data-stu-id="660e3-140">Choose **Activity filters** to set up other actions or metrics that will trigger an alert based on this policy.</span></span> 
    
7. <span data-ttu-id="660e3-141">在 "**活动匹配参数**" 下, 指定单个活动匹配筛选器时是否将触发策略违规, 或者在警报触发之前是否需要指定数量的重复活动。</span><span class="sxs-lookup"><span data-stu-id="660e3-141">Under **Activity match parameters**, specify whether a policy violation will be triggered when a single activity matches the filters, or if a specified number of repeated activities is required before the alert triggers.</span></span><br><span data-ttu-id="660e3-142">如果选择 "**重复活动**", 请指定活动的数量、时间范围, 以及是否会对特定应用程序中的用户或与任何应用程序相同的用户计数冲突。</span><span class="sxs-lookup"><span data-stu-id="660e3-142">If you select **Repeated activity**, specify the number of activities, the time frame, and whether a violation will count for a user within a specific app or for the same user with any app.</span></span>
    
8. <span data-ttu-id="660e3-143">(可选) 可以选择 "**创建通知**", 以创建从该策略接收通知的其他通知 (通过电子邮件、短信或两者)。</span><span class="sxs-lookup"><span data-stu-id="660e3-143">Optionally, you can select **Create alert** to create additional alerts to receive notifications from this policy (via email, text message, or both).</span></span><br><span data-ttu-id="660e3-144">**确保您的电子邮件提供商不会阻止发送`no-reply@cloudappsecurity.com`的电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="660e3-144">**Make sure that your email provider doesn't block emails sent from `no-reply@cloudappsecurity.com`**.</span></span> 
  
9. <span data-ttu-id="660e3-145">选择触发警报时应采取的**操作**, 以挂起用户或要求用户再次登录 Office 365 应用。</span><span class="sxs-lookup"><span data-stu-id="660e3-145">Choose the **Actions** that should be taken when an alert is triggered to suspend the user or require the user to sign in again to Office 365 apps.</span></span> 
    
10. <span data-ttu-id="660e3-146">选择 "**创建**" 以完成策略的创建。</span><span class="sxs-lookup"><span data-stu-id="660e3-146">Choose **Create** to finish creating your policy.</span></span> 
    
## <a name="next-steps"></a><span data-ttu-id="660e3-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="660e3-147">Next steps</span></span>

- [<span data-ttu-id="660e3-148">异常情况检测策略</span><span class="sxs-lookup"><span data-stu-id="660e3-148">Anomaly detection policies</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="660e3-149">集成您的 SIEM 服务器</span><span class="sxs-lookup"><span data-stu-id="660e3-149">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="660e3-150">查看警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="660e3-150">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="660e3-151">将 IP 地址分组以简化管理</span><span class="sxs-lookup"><span data-stu-id="660e3-151">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

