---
title: 推出 Office 365 云应用安全后的利用率活动
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 在设置和推出 Office 365 云应用程序安全性之后, 您需要执行某些任务以确保您的配置正确, 并且您已准备好进行定期检查。
ms.openlocfilehash: 232de4df1d1eb4debdddcee2c1d8672d1aeb4b21
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242540"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="25378-103">推出 Office 365 云应用安全后的利用率活动</span><span class="sxs-lookup"><span data-stu-id="25378-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="25378-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="25378-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="25378-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="25378-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="25378-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="25378-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="25378-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="25378-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="25378-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="25378-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="25378-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="25378-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="25378-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="25378-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="25378-111">你在这里!</span><span class="sxs-lookup"><span data-stu-id="25378-111">You are here!</span></span>  <br/> [<span data-ttu-id="25378-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="25378-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="25378-113">office 365 企业版 E5 中提供了 office 365 云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="25378-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="25378-114">如果您的组织使用的是其他 office 365 企业版订阅, 则可以将 Office 365 云应用安全作为附加项购买。</span><span class="sxs-lookup"><span data-stu-id="25378-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="25378-115">(作为全局管理员, 在 Microsoft 365 管理中心中, 选择 "**付费** \> **添加订阅**"。)有关详细信息, 请参阅[office 365 Platform 服务说明: office 365 &amp;安全合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[购买或编辑 Office 365 for business 的加载](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)项。</span><span class="sxs-lookup"><span data-stu-id="25378-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="25378-116">在设置和配置 office 365 云应用安全性之后, 您需要将某些使用任务作为组织的 Office 365 全局管理员或安全管理员执行。</span><span class="sxs-lookup"><span data-stu-id="25378-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="25378-117">通过执行这些任务, 可帮助确保正确配置 Office 365 云应用安全, 策略是最新的, 并且您的组织认识到了 office 365 的价值。</span><span class="sxs-lookup"><span data-stu-id="25378-117">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="25378-118">使用本文作为指导来帮助您规划这些任务。</span><span class="sxs-lookup"><span data-stu-id="25378-118">Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25378-119">您必须是全局管理员或安全管理员才能执行本文中所述的任务。</span><span class="sxs-lookup"><span data-stu-id="25378-119">You must be a global administrator or security administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="25378-120">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="25378-120">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="25378-121">Office 365 云应用程序安全性的初始配置和推出之后的活动</span><span class="sxs-lookup"><span data-stu-id="25378-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="25378-122">在配置和推出 Office 365 云应用安全性之后 (作为全局管理员或安全管理员), 您需要考虑以下几个事项:</span><span class="sxs-lookup"><span data-stu-id="25378-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="25378-123">需要向 IT 部门日历添加哪些任务？</span><span class="sxs-lookup"><span data-stu-id="25378-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="25378-124">如何确保将 Office 365 云应用安全配置为在一段时间内使用适当的策略集？</span><span class="sxs-lookup"><span data-stu-id="25378-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="25378-125">您应将哪些类型的摘要信息发送给 IT 管理链？</span><span class="sxs-lookup"><span data-stu-id="25378-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="25378-126">下表简要概述了要执行的后续任务以及应考虑添加到 IT 部门日历中的定期任务。</span><span class="sxs-lookup"><span data-stu-id="25378-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="25378-127">**持续任务**</span><span class="sxs-lookup"><span data-stu-id="25378-127">**Ongoing tasks**</span></span>|<span data-ttu-id="25378-128">**定期任务**</span><span class="sxs-lookup"><span data-stu-id="25378-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="25378-129">监视要向其发送警报消息的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="25378-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="25378-130">监视行业 cybersecurity 新闻源以获取有关新的网络攻击的最新信息</span><span class="sxs-lookup"><span data-stu-id="25378-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="25378-131">操作安全警报以确定和解决安全事件和风险</span><span class="sxs-lookup"><span data-stu-id="25378-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="25378-132">在中心日志中汇总每个安全事件和解决方案</span><span class="sxs-lookup"><span data-stu-id="25378-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="25378-133">执行 Office 365 云应用安全警报的每月或每季度评审, 以发现异常和分析趋势</span><span class="sxs-lookup"><span data-stu-id="25378-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="25378-134">对现有 office 365 云应用安全策略执行月度或季度检查, 以包括 office 365 云应用安全中的增强功能, 并解决 cybersecurity 中的新 cyberattacks 和发展趋势</span><span class="sxs-lookup"><span data-stu-id="25378-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="25378-135">根据组织在监视和维护安全 stature 的大小和兴趣, 您可以为 IT 管理链编译每月摘要, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="25378-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="25378-136">使用 Office 365 云应用安全标识的不同类型的安全事件</span><span class="sxs-lookup"><span data-stu-id="25378-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="25378-137">来自安全事件的中央日志 (如检测到的事件数) 的摘要信息</span><span class="sxs-lookup"><span data-stu-id="25378-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="25378-138">警报趋势及其解决方法</span><span class="sxs-lookup"><span data-stu-id="25378-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="25378-139">最新的 cybersecurity 趋势</span><span class="sxs-lookup"><span data-stu-id="25378-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="25378-140">Office 365 云应用安全策略更改的建议及其对最终用户的影响</span><span class="sxs-lookup"><span data-stu-id="25378-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="25378-141">在推出 Office 365 云应用安全性之后经过时间之后的活动</span><span class="sxs-lookup"><span data-stu-id="25378-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="25378-142">如果你最初配置或维护 Office 365 云应用安全策略以来已经过 protracted, 请执行以下步骤以返回到反映组织的安全目标和当前功能的配置Office 365 云应用安全性:</span><span class="sxs-lookup"><span data-stu-id="25378-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="25378-143">确定上次对 Office 365 云应用安全性进行的配置更改的日期。</span><span class="sxs-lookup"><span data-stu-id="25378-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="25378-144">了解你当前的 Office 365 云应用安全配置, 并根据需要调整这些策略。</span><span class="sxs-lookup"><span data-stu-id="25378-144">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed.</span></span> <span data-ttu-id="25378-145">例如, 请确保知道通过电子邮件发送警报的位置。</span><span class="sxs-lookup"><span data-stu-id="25378-145">For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="25378-146">有关自上次配置 office 365 云应用安全性以来产品更改的[office 365 云应用安全中的新增功能](new-in-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="25378-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="25378-147">对 Office 365 云应用安全警报和日志进行分析, 以找出异常和分析趋势。</span><span class="sxs-lookup"><span data-stu-id="25378-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="25378-148">检查行业 cybersecurity 的趋势, 了解最新的安全威胁。</span><span class="sxs-lookup"><span data-stu-id="25378-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="25378-149">对当前 Office 365 云应用安全策略集进行所需的更改分析。</span><span class="sxs-lookup"><span data-stu-id="25378-149">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies.</span></span> <span data-ttu-id="25378-150">将 Office 365 云应用安全功能更改、当前异常和 cybersecurity 趋势结合在一起。</span><span class="sxs-lookup"><span data-stu-id="25378-150">Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends.</span></span> <span data-ttu-id="25378-151">建议对现有策略的更改或创建新策略。</span><span class="sxs-lookup"><span data-stu-id="25378-151">Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="25378-152">制定实施策略更改的计划。</span><span class="sxs-lookup"><span data-stu-id="25378-152">Make a plan for implementing the policy changes.</span></span> <span data-ttu-id="25378-153">根据需要, 向最终用户传达建议更改的后果 (socialize)。</span><span class="sxs-lookup"><span data-stu-id="25378-153">Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="25378-154">实施 Office 365 云应用安全策略更改。</span><span class="sxs-lookup"><span data-stu-id="25378-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="25378-155">监视最终用户反馈和 Office 365 云应用安全警报, 并在一段时间后调整策略。</span><span class="sxs-lookup"><span data-stu-id="25378-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="25378-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="25378-156">Next steps</span></span>

- [<span data-ttu-id="25378-157">调查活动</span><span class="sxs-lookup"><span data-stu-id="25378-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="25378-158">挂起或还原用户帐户</span><span class="sxs-lookup"><span data-stu-id="25378-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="25378-159">管理 OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="25378-159">Manage OAuth apps</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="25378-160">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="25378-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="25378-161">查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表</span><span class="sxs-lookup"><span data-stu-id="25378-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

