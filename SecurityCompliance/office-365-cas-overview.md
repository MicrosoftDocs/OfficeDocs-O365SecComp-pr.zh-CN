---
title: Overview of Office 365 Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/22/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 81f0ee9a-9645-45ab-ba56-de9cbccab475
description: 'office 365 云应用安全可帮助您深入了解 Office 365 中的可疑活动, 以便您可以调查可能存在问题的情况, 并在必要时采取措施解决安全问题。 '
ms.openlocfilehash: 960e4c75a4da13e1a0365f75d290cd18587abd58
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001205"
---
# <a name="overview-of-office-365-cloud-app-security"></a><span data-ttu-id="6b8b1-103">Overview of Office 365 Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6b8b1-103">Overview of Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="6b8b1-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6b8b1-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="6b8b1-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6b8b1-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="6b8b1-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="6b8b1-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="6b8b1-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="6b8b1-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6b8b1-108">你在这里!</span><span class="sxs-lookup"><span data-stu-id="6b8b1-108">You are here!</span></span>  <br/> [<span data-ttu-id="6b8b1-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b8b1-109">Next step</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="6b8b1-110">开始规划</span><span class="sxs-lookup"><span data-stu-id="6b8b1-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |[<span data-ttu-id="6b8b1-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="6b8b1-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="6b8b1-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="6b8b1-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
> [!NOTE]
> <span data-ttu-id="6b8b1-113">office 365 企业版 E5 中提供了 office 365 云应用安全性。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-113">Office 365 Cloud App Security is available in Office 365 Enterprise E5.</span></span> <span data-ttu-id="6b8b1-114">如果您的组织使用的是其他 office 365 企业版订阅, 则可以将 Office 365 云应用安全作为附加项购买。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-114">If your organization is using another Office 365 Enterprise subscription, Office 365 Cloud App Security can be purchased as an add-on.</span></span> <span data-ttu-id="6b8b1-115">(作为全局管理员, 在 Microsoft 365 管理中心中, 选择 "**付费** \> **添加订阅**"。)有关详细信息, 请参阅[office 365 Platform 服务说明: office 365 &amp;安全合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[购买或编辑 Office 365 for business 的加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-115">(As a global administrator, in the Microsoft 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span> 
  
<span data-ttu-id="6b8b1-116">office 365 云应用安全使您可以深入了解 Office 365 中的可疑活动, 以便调查可能存在问题的情况, 并在必要时采取措施解决安全问题。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-116">Office 365 Cloud App Security gives you insight into suspicious activity in Office 365 so you can investigate situations that are potentially problematic and, if needed, take action to address security issues.</span></span> <span data-ttu-id="6b8b1-117">使用 Office 365 云应用安全, 您可以收到触发警报的通知, 以发现不正常或可疑的活动、如何访问和使用组织中的数据、暂停用户帐户显示可疑活动, 以及需要触发警报后, 用户可以重新登录到 Office 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-117">With Office 365 Cloud App Security, you can receive notifications of triggered alerts for atypical or suspicious activities, see how your organization's data in Office 365 is accessed and used, suspend user accounts exhibiting suspicious activity, and require users to log back in to Office 365 apps after an alert has been triggered.</span></span> <span data-ttu-id="6b8b1-118">阅读本文, 了解 Office 365 云应用安全特性和功能的概述。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-118">Read this article to get an overview of Office 365 Cloud App Security features and capabilities.</span></span>
  
    
## <a name="how-to-find-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="6b8b1-119">如何查找 Office 365 云应用安全门户</span><span class="sxs-lookup"><span data-stu-id="6b8b1-119">How to find the Office 365 Cloud App Security portal</span></span>

> [!NOTE]
> <span data-ttu-id="6b8b1-120">若要访问 office 365 云应用安全门户, 您必须是 office 365 全局管理员、安全管理员或安全阅读者。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-120">To access the Office 365 Cloud App Security portal, you must be an Office 365 global administrator, security administrator, or security reader.</span></span> <span data-ttu-id="6b8b1-121">若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-121">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> 
  
<span data-ttu-id="6b8b1-122">您可以通过转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来访问 Office 365 云应用安全门户。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-122">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="6b8b1-123">你也可以从 Office 365 安全&amp;合规中心获取。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-123">You can also get there from the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="6b8b1-124">下面是执行此操作的一个不错的方法:</span><span class="sxs-lookup"><span data-stu-id="6b8b1-124">Here's one good way to do it:</span></span>
  
1. <span data-ttu-id="6b8b1-125">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="6b8b1-126">(这会将您带到&amp;安全合规中心。)</span><span class="sxs-lookup"><span data-stu-id="6b8b1-126">(This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="6b8b1-127">在 "安全&amp;合规性中心" 中, 选择 "**通知** \> " "**管理高级警报**"。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-127">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span> <br/><span data-ttu-id="6b8b1-128">![选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="6b8b1-128">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br/><span data-ttu-id="6b8b1-129">(如果尚未启用 office 365 云应用安全, 并且你是全局管理员, 请[启用 office 365 云应用安全](turn-on-office-365-cas.md)。)</span><span class="sxs-lookup"><span data-stu-id="6b8b1-129">(If Office 365 Cloud App Security is not yet enabled, and you are a global administrator, [turn on Office 365 Cloud App Security](turn-on-office-365-cas.md).)</span></span>
    
3. <span data-ttu-id="6b8b1-130">选择 "**转到 Office 365 云应用安全性**"。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-130">Choose **Go to Office 365 Cloud App Security**.</span></span> 
    
## <a name="policies"></a><span data-ttu-id="6b8b1-131">策略</span><span class="sxs-lookup"><span data-stu-id="6b8b1-131">Policies</span></span>

<span data-ttu-id="6b8b1-132">Office 365 云应用安全性适用于为您的组织定义的策略。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-132">Office 365 Cloud App Security works with the policies that are defined for your organization.</span></span> <span data-ttu-id="6b8b1-133">使用 Office 365 云应用安全, 你的组织将获得许多预定义的异常检测策略和多个活动策略模板。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-133">With Office 365 Cloud App Security, your organization gets many predefined anomaly detection policies and several templates for activity policies.</span></span> <span data-ttu-id="6b8b1-134">这些策略旨在检测常规异常, 确定从有风险的 IP 地址登录的用户、检测勒索软件活动、检测非公司 IP 地址的管理员活动等。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-134">These policies are designed to detect general anomalies, identify users logging in from a risky IP address, detect ransomware activities, detect administrator activities from non-corporate IP addresses, and more.</span></span>
  
![在 CAS 门户中, 选择 " \>控制模板" 以查看或创建策略模板](media/88f615b4-aa8a-480c-b239-323dfcd628e1.png)
  
<span data-ttu-id="6b8b1-136">若要查看/使用策略模板, 请在 Office 365 云应用安全门户中, 转到 "**控件** \> **模板**"。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-136">To view/use policy templates, in the Office 365 Cloud App Security portal, go to **Control** \> **Templates**.</span></span> 
  
![在 O365 CAS 门户中, 选择 "控制"](media/287c2ea9-5172-4697-8e0e-b9ab654105bc.png)
  
<span data-ttu-id="6b8b1-138">若要了解有关策略的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="6b8b1-138">To learn more about policies, see the following resources:</span></span>
  
- [<span data-ttu-id="6b8b1-139">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="6b8b1-139">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="6b8b1-140">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="6b8b1-140">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
## <a name="alerts"></a><span data-ttu-id="6b8b1-141">警报</span><span class="sxs-lookup"><span data-stu-id="6b8b1-141">Alerts</span></span>

<span data-ttu-id="6b8b1-142">定义策略时, 警报会通知您检测到的可疑或非常规活动。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-142">When policies are defined, alerts notify you about suspicious or atypical activities that were detected.</span></span> <span data-ttu-id="6b8b1-143">若要查看组织的通知, 请在屏幕顶部的导航栏中选择 "**通知**"。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-143">To view alerts for your organization, choose **Alerts** in the navigation bar across the top of the screen.</span></span> 
  
![在 "通知" 页面上, 您可以查看触发的警报以及执行的任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
<span data-ttu-id="6b8b1-145">当警报被触发时, 您可以查看它们, 以了解有关正在进行的操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-145">As alerts are triggered you can review them to learn more about what is going on.</span></span> <span data-ttu-id="6b8b1-146">然后, 如果活动仍可疑, 则可以采取措施。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-146">Then, if the activity is still suspicious, you can take action.</span></span> <span data-ttu-id="6b8b1-147">例如, 您可以通知用户一个问题、挂起用户登录 office 365, 或要求用户重新登录 office 365 应用。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-147">For example, you can notify a user about an issue, suspend a user from signing in to Office 365, or require a user to sign back in to Office 365 apps.</span></span>
  
<span data-ttu-id="6b8b1-148">若要了解有关通知的详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="6b8b1-148">To learn more about alerts, see the following resources:</span></span>
  
- [<span data-ttu-id="6b8b1-149">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="6b8b1-149">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="6b8b1-150">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="6b8b1-150">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="6b8b1-151">查看 Office 365 云应用安全警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="6b8b1-151">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="activity-logs"></a><span data-ttu-id="6b8b1-152">活动日志</span><span class="sxs-lookup"><span data-stu-id="6b8b1-152">Activity logs</span></span>

<span data-ttu-id="6b8b1-153">查看有关 Office 365 云应用安全中的 "活动日志" 页上的用户活动的信息。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-153">View information about user activities on your Activity log page in Office 365 Cloud App Security.</span></span>
  
![在 O365 CAS 门户中, 选择 " \>调查活动日志"](media/ec19e77d-4e11-49fc-ab7c-0e8b0c29c93c.png)
  
<span data-ttu-id="6b8b1-155">若要获取此页面, 请在 Office 365 云应用安全门户中, 转到 "**调查** \> **活动日志**"。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-155">To get to this page, in the Office 365 Cloud App Security portal, go to **Investigate** \> **Activity log**.</span></span> 
  
![在 O365 CAS 门户中, 选择 "调查"。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
<span data-ttu-id="6b8b1-157">你也可以将 web 流量日志与 Office 365 云应用安全性结合使用。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-157">You can use your web traffic logs with Office 365 Cloud App Security, too.</span></span> <span data-ttu-id="6b8b1-158">这些日志文件中包含的详细信息越多, 您对用户活动的可见性越好。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-158">The more details that are included in those log files, the better visibility you'll have into user activity.</span></span> <span data-ttu-id="6b8b1-159">您可以使用 Barracuda、Blue Coat、Check Point、Cisco、Clavister、Dell SonicWALL、Fortinet、刺柏、McAfee、Microsoft、Palo Alto、Sophos、Squid、Websence、Zscaler 等的日志文件。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-159">You can use log files from Barracuda, Blue Coat, Check Point, Cisco, Clavister, Dell SonicWALL, Fortinet, Juniper, McAfee, Microsoft, Palo Alto, Sophos, Squid, Websence, Zscaler, and more.</span></span>
  
[<span data-ttu-id="6b8b1-160">了解有关 Office 365 云应用安全的 web 流量日志和数据源</span><span class="sxs-lookup"><span data-stu-id="6b8b1-160">Learn about web traffic logs and data sources for Office 365 Cloud App Security</span></span>](web-traffic-logs-and-data-sources-for-ocas.md)
  
## <a name="oauth-apps"></a><span data-ttu-id="6b8b1-161">OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="6b8b1-161">OAuth apps</span></span>

<span data-ttu-id="6b8b1-162">使用 office 365 云应用安全, 可以允许或阻止组织中的人员使用第三方应用访问 Office 365 中的数据。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-162">With Office 365 Cloud App Security, you can allow or prevent people in your organization to use third-party apps that access data in Office 365.</span></span>
  
![在 O365 CAS 中, 可以从 "调查" 菜单访问 "管理 OAuth 应用" 页面。](media/78272cda-986f-4b3b-bbbe-8c236c74f5d3.png)
  
<span data-ttu-id="6b8b1-164">若要获取此页面, 请转到**调查** \> **OAuth 应用**。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-164">To get to this page, go to **Investigate** \> **OAuth apps**.</span></span> 
  
![在 O365 CAS 门户中, 选择 "调查"。](media/8c7b87c9-71a6-4952-adb2-185e941ffe9a.png)
  
[<span data-ttu-id="6b8b1-166">使用 Office 365 云应用安全管理 OAuth 应用</span><span class="sxs-lookup"><span data-stu-id="6b8b1-166">Manage OAuth apps using Office 365 Cloud App Security</span></span>](manage-app-permissions-in-ocas.md)
  
## <a name="cloud-discovery-dashboard"></a><span data-ttu-id="6b8b1-167">云发现仪表板</span><span class="sxs-lookup"><span data-stu-id="6b8b1-167">Cloud Discovery Dashboard</span></span>

<span data-ttu-id="6b8b1-168">**云发现仪表板**(也称为 "**生产率应用发现**") 显示组织中的云应用使用情况的相关信息。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-168">The **Cloud Discovery Dashboard**, also referred to as **Productivity App Discovery**, shows information about cloud app usage within your organization.</span></span> <span data-ttu-id="6b8b1-169">您可以使用此仪表板查看有关应用、用户、流量、事务等的信息。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-169">You can view information about apps, users, traffic, transactions, and more using this dashboard.</span></span> <span data-ttu-id="6b8b1-170">云发现仪表板类似于以下图像:</span><span class="sxs-lookup"><span data-stu-id="6b8b1-170">The Cloud Discovery Dashboard resembles the following image:</span></span> 
  
![在 Office 365 CAS 门户中, 选择 " \>发现云发现" 仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="6b8b1-172">若要获取此仪表板, 请在 Office 365 云应用安全门户中, 转到 "**发现** \> **云发现" 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="6b8b1-172">To get to this dashboard, in the Office 365 Cloud App Security portal, go to **Discover** \> **Cloud Discovery dashboard**.</span></span> 
  
![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
[<span data-ttu-id="6b8b1-174">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="6b8b1-174">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
  
## <a name="next-steps"></a><span data-ttu-id="6b8b1-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6b8b1-175">Next steps</span></span>

- <span data-ttu-id="6b8b1-176">获取[Office 365 云应用安全使用案例和使用指南](https://aka.ms/O365CASGuide)</span><span class="sxs-lookup"><span data-stu-id="6b8b1-176">Get the [Office 365 Cloud App Security Use Cases and Usage Guide](https://aka.ms/O365CASGuide)</span></span>
    
- [<span data-ttu-id="6b8b1-177">准备使用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="6b8b1-177">Get ready for Office 365 Cloud App Security</span></span>](get-ready-for-office-365-cas.md)
    

