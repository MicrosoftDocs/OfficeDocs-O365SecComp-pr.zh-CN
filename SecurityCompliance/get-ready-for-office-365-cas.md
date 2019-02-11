---
title: 准备使用 Office 365 云应用安全
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 开始使用 Office 365 云应用程序安全性
ms.openlocfilehash: 1d1ae464278a5d9aafa5a176298f03174b6a37dc
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29603693"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="cd7f5-103">准备使用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="cd7f5-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="cd7f5-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cd7f5-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="cd7f5-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cd7f5-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="cd7f5-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="cd7f5-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="cd7f5-107">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="cd7f5-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="cd7f5-108">启动评估</span><span class="sxs-lookup"><span data-stu-id="cd7f5-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="cd7f5-109">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="cd7f5-109">You are here!</span></span>  <br/> [<span data-ttu-id="cd7f5-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd7f5-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="cd7f5-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="cd7f5-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="cd7f5-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="cd7f5-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="cd7f5-p101">准备要打开并为您的组织实现 Office 365 云应用程序安全性 （之前被称为高级安全管理），如有需要考虑的几件事。使用本文作为指南来规划 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p101">As you prepare to turn on and implement Office 365 Cloud App Security (formerly known as Advanced Security Management) for your organization, there are a few things to take into account. Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="cd7f5-115">步骤 1： 确定并保护您的全局和安全管理员帐户</span><span class="sxs-lookup"><span data-stu-id="cd7f5-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="cd7f5-p102">全局管理员、 安全管理员和安全读者可以访问 Office 365 云应用程序安全性门户以查看策略、 查看警报，并使用报表。全局管理员和安全管理员可以定义策略，并执行其他操作来保护您的组织。(有关详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)查看贵组织的用户帐户的预防提升的权限。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p102">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports. Global administrators and security administrators can define policies and take other actions to protect your organization. (For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="cd7f5-119">**[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="cd7f5-120">步骤 2： 启用审核日志记录您的组织</span><span class="sxs-lookup"><span data-stu-id="cd7f5-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="cd7f5-p103">对 Office 365 云应用程序安全性以正确的顺序，必须打开审核日志记录。这通常通过 Exchange Online 管理员或全局管理员。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p103">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on. This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="cd7f5-123">**[打开 Office 365 打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)**。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="cd7f5-124">步骤 3： 转到 Office 365 云应用程序安全性门户</span><span class="sxs-lookup"><span data-stu-id="cd7f5-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

<span data-ttu-id="cd7f5-125">您可以获取到 Office 365 云应用程序安全性门户转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)和登录。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-125">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="cd7f5-p104">您还可以从 Office 365 安全性而存在获取&amp;合规性中心。下面是一个好方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p104">You can also get there from the Office 365 Security &amp; Compliance Center. Here's one good way to do it:</span></span>

1. <span data-ttu-id="cd7f5-p105">转到[https://protection.office.com](https://protection.office.com)和登录英寸 (您将转到安全&amp;合规性中心。)</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p105">Go to [https://protection.office.com](https://protection.office.com) and sign in. (This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="cd7f5-130">转到**通知** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-130">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="cd7f5-131">选择**转到 Office 365 云应用程序安全性**转到 Office 365 云应用程序安全性门户。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-131">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span><br> <span data-ttu-id="cd7f5-132">![选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="cd7f5-132">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br><span data-ttu-id="cd7f5-133">当您转到 Office 365 云应用程序安全性门户时，您看到的第一页是策略页上，类似于下图：</span><span class="sxs-lookup"><span data-stu-id="cd7f5-133">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span><br><span data-ttu-id="cd7f5-134">![当您转到 Office 365 云应用程序安全性门户时，启动与策略页](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="cd7f5-134">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span><br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="cd7f5-135">步骤 4： 定义策略和设置提醒&amp;操作</span><span class="sxs-lookup"><span data-stu-id="cd7f5-135">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="cd7f5-p106">全局管理员和安全管理员 Office 365 云应用程序安全性定义策略。在定义策略的过程中，警报和操作也设置。警报是基于标准的视图中显示或通过电子邮件发送的通知。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p106">Global administrators and security administrators define policies in Office 365 Cloud App Security. During the process of defining policies, alerts and actions are also set. An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="cd7f5-p107">有两种类型的 Office 365 云应用程序安全性的通知： 检测可疑活动的异常检测警报和活动通知，定义可能为您的组织在典型的活动。警报通知全局管理员和安全管理员为您的组织不常见的 Office 365 环境中活动时。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p107">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization. Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="cd7f5-141">请参阅以下资源，以了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="cd7f5-141">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="cd7f5-142">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="cd7f5-142">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="cd7f5-143">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="cd7f5-143">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="cd7f5-144">查看和 Office 365 云应用程序安全性通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="cd7f5-144">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    
## <a name="step-5-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="cd7f5-145">步骤 5： 了解有关您组织的云使用情况</span><span class="sxs-lookup"><span data-stu-id="cd7f5-145">Step 5: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="cd7f5-p108">作为全局管理员、 安全管理员或安全读者，您可以了解有关您组织的云通过报告和云发现仪表板 （也称为工作效率应用程序发现） 的使用情况。此仪表板显示有关用户、 应用程序、 web 流量和风险级别信息。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p108">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery). This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![在 Office 365 CAS 门户中，选择发现\>云发现仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="cd7f5-149">若要转到生产效率应用程序发现仪表板，在 Office 365 云应用程序安全性门户中，选择**发现** \> **云发现仪表板**。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-149">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![在 Office 365 CAS 门户中，选择发现](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="cd7f5-p109">若要填充所需的信息的报告，上载日志文件从您的组织的防火墙和代理。若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p109">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies. To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="cd7f5-153">在 Office 365 云应用程序安全性中创建应用程序发现报告</span><span class="sxs-lookup"><span data-stu-id="cd7f5-153">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="cd7f5-154">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="cd7f5-154">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-6-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="cd7f5-155">步骤 6： 管理您的组织使用访问 Office 365 的应用程序</span><span class="sxs-lookup"><span data-stu-id="cd7f5-155">Step 6: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="cd7f5-p110">以全局管理员或安全管理员，您可以管理应用程序，例如自定义应用程序或第三方应用程序，在与 Office 365 其设备上使用您的组织中的人员。例如，假设有人已下载他们想要与 Office 365 一起使用的自定义应用程序。您可以查看用户正在使用的应用程序、 禁止不受信任应用程序，或将应用程序标记为批准可用于跟踪目的。[使用 Office 365 云应用程序安全性的管理 OAuth 应用程序](manage-app-permissions-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p110">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365. For example, suppose that someone has downloaded a custom app they want to use with Office 365. You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes. [Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-7-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="cd7f5-160">步骤 7： 使用 SIEM 服务器与 Office 365 云应用程序安全性</span><span class="sxs-lookup"><span data-stu-id="cd7f5-160">Step 7: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="cd7f5-p111">您的组织使用的安全信息和事件管理 (SIEM) 服务器？Office 365 云应用程序安全性可以现在与集成 SIEM 服务器启用集中式监视进行通知。与 SIEM 服务集成允许您更好地保护同时维护常规安全工作流、 自动化安全过程和关联之间的基于云的云应用程序在本地和事件。SIEM 代理服务器上运行、 提取通知从 Office 365 云应用程序安全性，并将这些通知流式到 SIEM 服务器。请参阅[与 Office 365 云应用程序安全性的 SIEM 集成](integrate-your-siem-server-with-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-p111">Is your organization using a security information and event management (SIEM) server? Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts. Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events. The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server. See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="cd7f5-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd7f5-166">Next steps</span></span>

- [<span data-ttu-id="cd7f5-167">开启 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="cd7f5-167">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="cd7f5-168">尝试动手体验如何可以在此演示 Office 365 云应用程序安全性的强大功能，并创建证明我们[测试实验室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)。</span><span class="sxs-lookup"><span data-stu-id="cd7f5-168">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

