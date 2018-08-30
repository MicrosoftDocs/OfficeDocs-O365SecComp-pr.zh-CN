---
title: 推出 Office 365 云应用安全后的利用率活动
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 86f414ad-81de-4703-b40a-c6615bbe9108
description: 您已设置并推出 Office 365 云应用程序安全性后，您需要执行某些任务，以确保您的配置正确，并且您已准备好定期检查。
ms.openlocfilehash: bc8cfad8eb9d9444066c3193ec2978e9ffd9f56a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525173"
---
# <a name="utilization-activities-after-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="e5f9a-103">推出 Office 365 云应用安全后的利用率活动</span><span class="sxs-lookup"><span data-stu-id="e5f9a-103">Utilization activities after rolling out Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="e5f9a-104">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e5f9a-104">****Evaluation** \>**</span></span>|<span data-ttu-id="e5f9a-105">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e5f9a-105">****Planning** \>**</span></span>|<span data-ttu-id="e5f9a-106">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="e5f9a-106">****Deployment** \>**</span></span>|<span data-ttu-id="e5f9a-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="e5f9a-107">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="e5f9a-108">启动评估</span><span class="sxs-lookup"><span data-stu-id="e5f9a-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="e5f9a-109">开始规划</span><span class="sxs-lookup"><span data-stu-id="e5f9a-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="e5f9a-110">开始部署</span><span class="sxs-lookup"><span data-stu-id="e5f9a-110">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |<span data-ttu-id="e5f9a-111">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="e5f9a-111">You are here!</span></span>  <br/> [<span data-ttu-id="e5f9a-112">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5f9a-112">Next step</span></span>](review-office-365-cas-alerts.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="e5f9a-p101">Office 365 云应用程序安全性是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 云应用程序安全性。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p101">Office 365 Cloud App Security is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
<span data-ttu-id="e5f9a-116">您已设置并配置 Office 365 云应用程序安全性之后，您需要为 Office 365 全局管理员或安全管理员为您的组织中执行某些利用率任务。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-116">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span> 

<span data-ttu-id="e5f9a-p102">通过执行这些任务，您将帮助确保正确配置了 Office 365 云应用程序安全性，您的策略是最新版本，并且您的组织实现从 Office 365 的值。使用本文作为指南可帮助您规划有关执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p102">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365. Use this article as a guide to help you plan for these tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5f9a-p103">您必须是要执行本文中描述的任务的全局管理员或 security 管理员程序。若要了解详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p103">You must be a global administrator or security administrator to perform the tasks described in this article. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
    
## <a name="activities-after-the-initial-configuration-and-rollout-of-office-365-cloud-app-security"></a><span data-ttu-id="e5f9a-121">活动后的初始配置和推出 Office 365 云应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="e5f9a-121">Activities after the initial configuration and rollout of Office 365 Cloud App Security</span></span>

<span data-ttu-id="e5f9a-122">Office 365 云应用程序安全性已配置并推出，以全局管理员或安全管理员之后必须要考虑的几个事项：</span><span class="sxs-lookup"><span data-stu-id="e5f9a-122">After Office 365 Cloud App Security is configured and rolled out, as a global administrator or security administrators, you have several things to consider:</span></span>
  
- <span data-ttu-id="e5f9a-123">需要添加到 IT 部门日历哪些任务？</span><span class="sxs-lookup"><span data-stu-id="e5f9a-123">What tasks need to be added to the IT department calendar?</span></span>
    
- <span data-ttu-id="e5f9a-124">如何确保 Office 365 云应用程序安全性配置为随时间使用适当的策略集？</span><span class="sxs-lookup"><span data-stu-id="e5f9a-124">How can you make sure Office 365 Cloud App Security is configured to use the right set of policies over time?</span></span>
    
- <span data-ttu-id="e5f9a-125">IT 管理链向上，您应发送哪些类型的摘要信息？</span><span class="sxs-lookup"><span data-stu-id="e5f9a-125">What kinds of summary information should you send up the IT management chain?</span></span>
    
<span data-ttu-id="e5f9a-126">下表简要概述的过程中需要执行的任务和应考虑将添加到您的 IT 部门的日历的定期任务。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-126">The following table briefly summarizes the ongoing tasks you'll want to perform and periodic tasks you should consider adding to your IT department's calendar.</span></span>
  
|<span data-ttu-id="e5f9a-127">**正在进行的任务**</span><span class="sxs-lookup"><span data-stu-id="e5f9a-127">**Ongoing tasks**</span></span>|<span data-ttu-id="e5f9a-128">**定期任务**</span><span class="sxs-lookup"><span data-stu-id="e5f9a-128">**Periodic tasks**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e5f9a-129">监视向其发送通知消息的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="e5f9a-129">Monitor the email accounts to which you are sending alert messages</span></span>  <br/>  <span data-ttu-id="e5f9a-130">有关新网络攻击的最新信息的监视行业网络安全新闻源</span><span class="sxs-lookup"><span data-stu-id="e5f9a-130">Monitor industry cybersecurity news feeds for the latest information about new cyber attacks</span></span>  <br/>  <span data-ttu-id="e5f9a-131">操作安全警告，以确定并解决安全事件和风险</span><span class="sxs-lookup"><span data-stu-id="e5f9a-131">Act on security alerts to identify and address security incidents and risks</span></span>  <br/>  <span data-ttu-id="e5f9a-132">总结了每个安全事件和中央日志中的解决方案</span><span class="sxs-lookup"><span data-stu-id="e5f9a-132">Summarize each security incident and resolution in a central log</span></span>  <br/> | <span data-ttu-id="e5f9a-133">执行 Office 365 云应用程序安全性通知专色异常的月份或季度评论和分析趋势</span><span class="sxs-lookup"><span data-stu-id="e5f9a-133">Perform monthly or quarterly reviews of Office 365 Cloud App Security alerts to spot anomalies and analyze trends</span></span>  <br/>  <span data-ttu-id="e5f9a-134">审查月份或季度的您现有的 Office 365 云应用程序安全策略，以包含在 Office 365 云应用程序安全性和地址的新事件和怒趋势中的增强功能</span><span class="sxs-lookup"><span data-stu-id="e5f9a-134">Perform monthly or quarterly reviews of your existing Office 365 Cloud App Security policies to include enhancements in Office 365 Cloud App Security and address new cyberattacks and trends in cybersecurity</span></span>  <br/> |
   
<span data-ttu-id="e5f9a-135">取决于组织的规模和监视和维护安全 stature 感兴趣，您可以为您的 IT 管理链包含搜集每月汇总：</span><span class="sxs-lookup"><span data-stu-id="e5f9a-135">Depending on your organization's size and interest in monitoring and maintaining a security stature, you can compile a monthly summary for your IT management chain that includes:</span></span>
  
- <span data-ttu-id="e5f9a-136">不同类型的标识与 Office 365 云应用程序安全性的安全事件</span><span class="sxs-lookup"><span data-stu-id="e5f9a-136">The different types of security incidents identified with Office 365 Cloud App Security</span></span>
    
- <span data-ttu-id="e5f9a-137">您中央日志中的安全事件，如检测到的事件的数量的摘要信息</span><span class="sxs-lookup"><span data-stu-id="e5f9a-137">Summary information from your central log of the security incidents, such as number of incidents detected</span></span>
    
- <span data-ttu-id="e5f9a-138">警报的趋势和它们已得到解决</span><span class="sxs-lookup"><span data-stu-id="e5f9a-138">Alert trends and how they were addressed</span></span>
    
- <span data-ttu-id="e5f9a-139">最新的网络安全趋势</span><span class="sxs-lookup"><span data-stu-id="e5f9a-139">The latest cybersecurity trends</span></span>
    
- <span data-ttu-id="e5f9a-140">有关 Office 365 云应用程序安全策略更改和及其对最终用户的影响的建议</span><span class="sxs-lookup"><span data-stu-id="e5f9a-140">Recommendations for Office 365 Cloud App Security policy changes and their impact on end users</span></span>
    
## <a name="activities-after-time-has-passed-since-rolling-out-office-365-cloud-app-security"></a><span data-ttu-id="e5f9a-141">活动时间过后以来推出 Office 365 云应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="e5f9a-141">Activities after time has passed since rolling out Office 365 Cloud App Security</span></span>

<span data-ttu-id="e5f9a-142">如果长的时间量最初配置或维护您的 Office 365 云应用程序安全策略后，，执行以下步骤以返回到反映您的组织的安全目标和当前功能的配置Office 365 云应用程序安全性：</span><span class="sxs-lookup"><span data-stu-id="e5f9a-142">If a protracted amount of time has passed since you initially configured or maintained your Office 365 Cloud App Security policies, take the following steps to get back to a configuration that reflects your organization's security goals and the current capabilities of Office 365 Cloud App Security:</span></span>
  
1. <span data-ttu-id="e5f9a-143">确定上次对 Office 365 云应用程序安全性的配置更改的日期。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-143">Determine the date of the last configuration change for Office 365 Cloud App Security.</span></span>
    
2. <span data-ttu-id="e5f9a-p104">了解您当前的 Office 365 云应用程序安全性配置，并根据需要调整这些策略。例如，请确保您知道要发送电子邮件的通知。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p104">Understand your current Office 365 Cloud App Security configuration and adjust those policies as needed. For example, make sure you know where alerts are being sent via email.</span></span>
    
3. <span data-ttu-id="e5f9a-146">自从上次配置 Office 365 云应用程序安全性，请参阅的产品更改[what's new in Office 365 云应用程序安全性](new-in-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-146">See [what's new in Office 365 Cloud App Security](new-in-office-365-cas.md) for product changes since you last configured Office 365 Cloud App Security.</span></span> 
    
4. <span data-ttu-id="e5f9a-147">执行 Office 365 云应用程序安全性通知和专色异常日志分析并分析趋势。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-147">Perform an analysis of Office 365 Cloud App Security alerts and logs to spot anomalies and analyze trends.</span></span>
    
5. <span data-ttu-id="e5f9a-148">检查行业网络安全趋势以便意识到最新的安全威胁。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-148">Check industry cybersecurity trends to become aware of the latest security threats.</span></span>
    
6. <span data-ttu-id="e5f9a-p105">执行分析对当前的 Office 365 云应用程序安全策略集所需要的更改。Office 365 云应用程序安全性功能更改、 当前的异常和网络安全趋势合并。建议对现有策略或创建新策略的更改。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p105">Perform an analysis of the changes that need to be made to the current set of Office 365 Cloud App Security policies. Incorporate Office 365 Cloud App Security feature changes, current anomalies, and cybersecurity trends. Recommend changes to existing policies or the creation of new policies.</span></span>
    
7. <span data-ttu-id="e5f9a-p106">使实现策略更改的计划。通信 （社交） 的后果的最终用户根据需要将建议的更改。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-p106">Make a plan for implementing the policy changes. Communicate (socialize) the consequences of the proposed changes with your end users as needed.</span></span>
    
8. <span data-ttu-id="e5f9a-154">实现 Office 365 云应用程序安全策略更改。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-154">Implement the Office 365 Cloud App Security policy changes.</span></span>
    
9. <span data-ttu-id="e5f9a-155">监视最终用户反馈和 Office 365 云应用程序安全警告，并调整随着时间的推移策略。</span><span class="sxs-lookup"><span data-stu-id="e5f9a-155">Monitor end user feedback and Office 365 Cloud App Security alerts and adjust policies over time.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="e5f9a-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e5f9a-156">Next steps</span></span>

- [<span data-ttu-id="e5f9a-157">调查活动</span><span class="sxs-lookup"><span data-stu-id="e5f9a-157">Investigate an activity</span></span>](investigate-an-activity-in-office-365-cas.md)
    
- [<span data-ttu-id="e5f9a-158">暂停或还原的用户帐户</span><span class="sxs-lookup"><span data-stu-id="e5f9a-158">Suspend or restore a user account</span></span>](suspend-or-restore-an-account-in-ocas.md)
    
- [<span data-ttu-id="e5f9a-159">管理应用程序的权限</span><span class="sxs-lookup"><span data-stu-id="e5f9a-159">Manage app permissions</span></span>](manage-app-permissions-in-ocas.md)
    
- [<span data-ttu-id="e5f9a-160">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="e5f9a-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
- <span data-ttu-id="e5f9a-161">查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表</span><span class="sxs-lookup"><span data-stu-id="e5f9a-161">View a list of supported [Web traffic logs and data sources](web-traffic-logs-and-data-sources-for-ocas.md)</span></span>
    

