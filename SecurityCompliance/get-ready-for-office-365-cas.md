---
title: 准备使用 Office 365 云应用安全
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/15/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d9ee4d67-f2b3-42b4-9c9e-c4529904990a
description: 开始使用 Office 365 云应用安全
ms.openlocfilehash: 89718adcbb7c77735db3009937d887e88d4a8bc3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254006"
---
# <a name="get-ready-for-office-365-cloud-app-security"></a><span data-ttu-id="b4921-103">准备使用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="b4921-103">Get ready for Office 365 Cloud App Security</span></span>
  
|<span data-ttu-id="b4921-104">评估 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4921-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="b4921-105">规划 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4921-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="b4921-106">部署 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="b4921-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="b4921-107">利用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="b4921-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b4921-108">开始评估</span><span class="sxs-lookup"><span data-stu-id="b4921-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |<span data-ttu-id="b4921-109">你在这里!</span><span class="sxs-lookup"><span data-stu-id="b4921-109">You are here!</span></span>  <br/> [<span data-ttu-id="b4921-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b4921-110">Next step</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="b4921-111">开始部署</span><span class="sxs-lookup"><span data-stu-id="b4921-111">Start deploying</span></span>](turn-on-office-365-cas.md) <br/> |[<span data-ttu-id="b4921-112">开始利用</span><span class="sxs-lookup"><span data-stu-id="b4921-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="b4921-113">在准备为组织启用和实施 Office 365 云应用安全时, 需要考虑一些事项。</span><span class="sxs-lookup"><span data-stu-id="b4921-113">As you prepare to turn on and implement Office 365 Cloud App Security for your organization, there are a few things to take into account.</span></span> <span data-ttu-id="b4921-114">使用本文作为规划 Office 365 云应用程序安全性的指南。</span><span class="sxs-lookup"><span data-stu-id="b4921-114">Use this article as a guide to plan for Office 365 Cloud App Security.</span></span>
    
## <a name="step-1-identify-and-protect-your-global-and-security-administrator-accounts"></a><span data-ttu-id="b4921-115">步骤 1: 标识和保护全局管理员帐户和安全管理员帐户</span><span class="sxs-lookup"><span data-stu-id="b4921-115">Step 1: Identify and protect your global and security administrator accounts</span></span>

<span data-ttu-id="b4921-116">全局管理员、安全管理员和安全读者可以访问 Office 365 云应用安全门户以查看策略、查看通知和使用报表。</span><span class="sxs-lookup"><span data-stu-id="b4921-116">Global administrators, security administrators, and security readers can access the Office 365 Cloud App Security portal to view policies, review alerts, and use reports.</span></span> <span data-ttu-id="b4921-117">全局管理员和安全管理员可以定义策略并执行其他操作来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="b4921-117">Global administrators and security administrators can define policies and take other actions to protect your organization.</span></span> <span data-ttu-id="b4921-118">(有关详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。)查看您的组织的用户帐户, 该帐户具有提升的权限作为预防措施。</span><span class="sxs-lookup"><span data-stu-id="b4921-118">(For more information, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).) Review your organization's user accounts that have elevated permissions as a precaution.</span></span> 
  
 <span data-ttu-id="b4921-119">**[保护 Office 365 全局管理员帐户](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**。</span><span class="sxs-lookup"><span data-stu-id="b4921-119">**[Protect your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)**.</span></span> 
  
## <a name="step-2-turn-on-audit-logging-for-your-organization"></a><span data-ttu-id="b4921-120">步骤 2: 为组织启用审核日志记录</span><span class="sxs-lookup"><span data-stu-id="b4921-120">Step 2: Turn on audit logging for your organization</span></span>

<span data-ttu-id="b4921-121">为了使 Office 365 云应用安全正常工作, 审核日志记录必须处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="b4921-121">In order for Office 365 Cloud App Security to work correct, audit logging must be turned on.</span></span> <span data-ttu-id="b4921-122">这通常是由 Exchange Online 管理员或全局管理员完成的。</span><span class="sxs-lookup"><span data-stu-id="b4921-122">This is typically done by an Exchange Online administrator or a global administrator.</span></span>
  
 <span data-ttu-id="b4921-123">**[启用或禁用 "Office 365 审核日志搜索"](turn-audit-log-search-on-or-off.md)**。</span><span class="sxs-lookup"><span data-stu-id="b4921-123">**[Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md)**.</span></span> 
  
## <a name="step-3-go-to-the-office-365-cloud-app-security-portal"></a><span data-ttu-id="b4921-124">步骤 3: 转到 Office 365 云应用安全门户</span><span class="sxs-lookup"><span data-stu-id="b4921-124">Step 3: Go to the Office 365 Cloud App Security portal</span></span>

<span data-ttu-id="b4921-125">您可以通过转到[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来访问 Office 365 云应用安全门户。</span><span class="sxs-lookup"><span data-stu-id="b4921-125">You can get to the Office 365 Cloud App Security portal by going to [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com) and signing in.</span></span> 

<span data-ttu-id="b4921-126">你也可以从 Office 365 安全&amp;合规中心获取。</span><span class="sxs-lookup"><span data-stu-id="b4921-126">You can also get there from the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="b4921-127">下面是执行此操作的一个不错的方法:</span><span class="sxs-lookup"><span data-stu-id="b4921-127">Here's one good way to do it:</span></span>

1. <span data-ttu-id="b4921-128">转到[https://protection.office.com](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="b4921-128">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="b4921-129">(这会将您带到&amp;安全合规中心。)</span><span class="sxs-lookup"><span data-stu-id="b4921-129">(This takes you to the Security &amp; Compliance Center.)</span></span>
    
2. <span data-ttu-id="b4921-130">转到 "**通知** \> " "**管理高级警报**"。</span><span class="sxs-lookup"><span data-stu-id="b4921-130">Go to **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="b4921-131">选择 "**转到 office 365 云应用安全性**" 以转到 office 365 云应用安全门户。</span><span class="sxs-lookup"><span data-stu-id="b4921-131">Choose **Go to Office 365 Cloud App Security** to go to the Office 365 Cloud App Security portal.</span></span><br> <span data-ttu-id="b4921-132">![选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span><span class="sxs-lookup"><span data-stu-id="b4921-132">![Choose Manage Advanced Alerts to go to Office 365 Cloud App Security](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)</span></span><br><span data-ttu-id="b4921-133">当您转到 Office 365 云应用安全门户时, 您看到的第一页是策略页, 类似于以下图像:</span><span class="sxs-lookup"><span data-stu-id="b4921-133">When you go to the Office 365 Cloud App Security portal, the first page you see is the Policies page, which resembles the following image:</span></span><br><span data-ttu-id="b4921-134">![当您转到 Office 365 云应用安全门户时, 将从 "策略" 页开始](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span><span class="sxs-lookup"><span data-stu-id="b4921-134">![When you go to the Office 365 Cloud App Security portal, you start with the Policies page](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)</span></span><br>
  
## <a name="step-4-define-policies-and-set-up-alerts-amp-actions"></a><span data-ttu-id="b4921-135">步骤 4: 定义策略并设置警报&amp;操作</span><span class="sxs-lookup"><span data-stu-id="b4921-135">Step 4: Define policies and set up alerts &amp; actions</span></span>

<span data-ttu-id="b4921-136">全局管理员和安全管理员定义 Office 365 云应用安全中的策略。</span><span class="sxs-lookup"><span data-stu-id="b4921-136">Global administrators and security administrators define policies in Office 365 Cloud App Security.</span></span> <span data-ttu-id="b4921-137">在定义策略的过程中, 还会设置警报和操作。</span><span class="sxs-lookup"><span data-stu-id="b4921-137">During the process of defining policies, alerts and actions are also set.</span></span> <span data-ttu-id="b4921-138">警报是显示在视图中或通过电子邮件发送的基于条件的通知。</span><span class="sxs-lookup"><span data-stu-id="b4921-138">An alert is a criteria-based notification that appears in a view or is sent via email.</span></span> 
  
<span data-ttu-id="b4921-139">Office 365 Cloud App Security 中有两种类型的警报: 检测可疑活动的异常检测警报和活动警报 (针对组织的可能是反常的活动) 定义的。</span><span class="sxs-lookup"><span data-stu-id="b4921-139">There are two types of alerts in Office 365 Cloud App Security: anomaly detection alerts that detect suspicious activity, and activity alerts, which are defined for activities that might be atypical for your organization.</span></span> <span data-ttu-id="b4921-140">当您的 Office 365 环境中的某个活动在您的组织中不正常时, 会向全局管理员和安全管理员通知这些警报。</span><span class="sxs-lookup"><span data-stu-id="b4921-140">Alerts notify global administrators and security administrators when there's an activity in your Office 365 environment that's unusual for your organization.</span></span>
  
<span data-ttu-id="b4921-141">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="b4921-141">See the following resources to learn more:</span></span>
  
- [<span data-ttu-id="b4921-142">Office 365 云应用安全中的活动策略和警报</span><span class="sxs-lookup"><span data-stu-id="b4921-142">Activity policies and alerts in Office 365 Cloud App Security</span></span>](activity-policies-and-alerts.md)
    
- [<span data-ttu-id="b4921-143">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="b4921-143">Anomaly detection policies in Office 365 Cloud App Security</span></span>](anomaly-detection-policies-in-ocas.md)
    
- [<span data-ttu-id="b4921-144">查看 Office 365 云应用安全警报并对其执行操作</span><span class="sxs-lookup"><span data-stu-id="b4921-144">Review and take action on Office 365 Cloud App Security alerts</span></span>](review-office-365-cas-alerts.md)
    

## <a name="step-5-set-up-conditional-access-app-control"></a><span data-ttu-id="b4921-145">步骤 5: 设置条件访问应用程序控制</span><span class="sxs-lookup"><span data-stu-id="b4921-145">Step 5: Set up Conditional Access App Control</span></span>

<span data-ttu-id="b4921-146">根据某些条件 (如哪些用户可以使用哪些应用程序, 以及在哪里) 设置和强制实施您组织的应用程序上的控件。</span><span class="sxs-lookup"><span data-stu-id="b4921-146">Set up and enforce controls on your organization's apps, based on certain conditions, such as which users can use what apps, and where.</span></span> <span data-ttu-id="b4921-147">定义用户应用程序访问和会话策略, 以确定是否可以下载和加密敏感文档, 阻止对某些应用程序的访问, 为某些应用程序设置只读模式, 并限制来自非企业网络的用户会话。</span><span class="sxs-lookup"><span data-stu-id="b4921-147">Define user app access and session policies to determine whether sensitive documents can be downloaded and encrypted, block access to certain apps, set up read-only mode for certain apps, and restrict user sessions from non-corporate networks.</span></span>

<span data-ttu-id="b4921-148">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="b4921-148">See the following resources to learn more:</span></span>

- [<span data-ttu-id="b4921-149">使用 Office 365 云应用安全条件访问应用控制保护应用</span><span class="sxs-lookup"><span data-stu-id="b4921-149">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>](ocas-conditional-access-app-control.md)

- [<span data-ttu-id="b4921-150">为 Office 365 应用部署条件访问应用控制</span><span class="sxs-lookup"><span data-stu-id="b4921-150">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

## <a name="step-6-learn-about-your-organizations-cloud-usage"></a><span data-ttu-id="b4921-151">步骤 6: 了解组织的云使用情况</span><span class="sxs-lookup"><span data-stu-id="b4921-151">Step 6: Learn about your organization's cloud usage</span></span>

<span data-ttu-id="b4921-152">作为全局管理员、安全管理员或安全读者, 您可以通过报告和云发现仪表板 (也称为 "工作效率应用发现") 了解组织的云使用情况。</span><span class="sxs-lookup"><span data-stu-id="b4921-152">As a global administrator, security administrator, or security reader, you can learn about your organization's cloud usage through reports and a Cloud Discovery dashboard (also called Productivity App Discovery).</span></span> <span data-ttu-id="b4921-153">此仪表板显示有关用户、应用、web 流量和风险级别的信息。</span><span class="sxs-lookup"><span data-stu-id="b4921-153">This dashboard shows information about users, apps, web traffic, and risk levels.</span></span>
  
![在 Office 365 CAS 门户中, 选择 " \>发现云发现" 仪表板](media/61269290-fd82-4d4b-8045-aea1ebc82287.png)
  
<span data-ttu-id="b4921-155">若要转到工作效率应用发现仪表板, 请在 Office 365 云应用安全门户中, 选择 "**发现** \> **云发现仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="b4921-155">To go to the Productivity App Discovery dashboard, in the Office 365 Cloud App Security portal, choose **Discover** \> **Cloud Discovery dashboard**.</span></span>
  
![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)
  
<span data-ttu-id="b4921-157">若要使用所需的信息填充报告, 请从组织的防火墙和代理上载日志文件。</span><span class="sxs-lookup"><span data-stu-id="b4921-157">To populate reports with the information you need, upload your log files from your organization's firewalls and proxies.</span></span> <span data-ttu-id="b4921-158">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="b4921-158">To learn more, see the following resources:</span></span>
  
- [<span data-ttu-id="b4921-159">在 Office 365 中创建应用程序发现报告云应用安全</span><span class="sxs-lookup"><span data-stu-id="b4921-159">Create app discovery reports in Office 365 Cloud App Security</span></span>](create-app-discovery-reports-in-ocas.md)
    
- [<span data-ttu-id="b4921-160">查看 Office 365 云应用安全中的应用发现结果</span><span class="sxs-lookup"><span data-stu-id="b4921-160">Review app discovery findings in Office 365 Cloud App Security</span></span>](review-app-discovery-findings-in-ocas.md)
    
## <a name="step-7-manage-apps-that-your-organization-is-using-to-access-office-365"></a><span data-ttu-id="b4921-161">步骤 7: 管理您的组织用来访问 Office 365 的应用程序</span><span class="sxs-lookup"><span data-stu-id="b4921-161">Step 7: Manage apps that your organization is using to access Office 365</span></span>

<span data-ttu-id="b4921-162">作为全局管理员或安全管理员, 您可以管理组织中的用户在使用 Office 365 的设备上使用的自定义应用程序或第三方应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4921-162">As a global administrator or security administrator, you can manage apps, such as custom apps or third-party apps, that people in your organization are using on their devices with Office 365.</span></span> <span data-ttu-id="b4921-163">例如, 假设有人下载了要与 Office 365 一起使用的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4921-163">For example, suppose that someone has downloaded a custom app they want to use with Office 365.</span></span> <span data-ttu-id="b4921-164">您可以查看用户正在使用的应用程序、禁止不受信任的应用程序, 或将应用标记为针对跟踪目的进行审批。</span><span class="sxs-lookup"><span data-stu-id="b4921-164">You can review the apps people are using, ban untrusted apps, or mark apps as approved for your tracking purposes.</span></span> <span data-ttu-id="b4921-165">[使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="b4921-165">[Manage OAuth apps using Office 365 Cloud App Security](manage-app-permissions-in-ocas.md).</span></span>
  
## <a name="step-8-create-a-maintenance-plan"></a><span data-ttu-id="b4921-166">步骤 8: 创建维护计划</span><span class="sxs-lookup"><span data-stu-id="b4921-166">Step 8: Create a maintenance plan</span></span>

<span data-ttu-id="b4921-167">在设置和配置 office 365 云应用安全性之后, 您需要将某些使用任务作为组织的 Office 365 全局管理员或安全管理员执行。</span><span class="sxs-lookup"><span data-stu-id="b4921-167">After you have set up and configured Office 365 Cloud App Security, you'll want to perform certain utilization tasks as an Office 365 global administrator or security administrator for your organization.</span></span>
<span data-ttu-id="b4921-168">通过执行这些任务, 可帮助确保正确配置 Office 365 云应用安全, 策略是最新的, 并且您的组织认识到了 office 365 的价值。</span><span class="sxs-lookup"><span data-stu-id="b4921-168">By performing these tasks, you'll help ensure that Office 365 Cloud App Security is configured correctly, your policies are up to date, and your organization realizes value from Office 365.</span></span> <span data-ttu-id="b4921-169">使用本文作为指导来帮助您规划这些任务。</span><span class="sxs-lookup"><span data-stu-id="b4921-169">Use this article as a guide to help you plan for these tasks.</span></span> <span data-ttu-id="b4921-170">请参阅[在推出 Office 365 云应用安全性后的使用率活动](utilization-activities-for-ocas.md)。</span><span class="sxs-lookup"><span data-stu-id="b4921-170">See [Utilization activities after rolling out Office 365 Cloud App Security](utilization-activities-for-ocas.md).</span></span>

## <a name="optional-step-9-use-your-siem-server-with-office-365-cloud-app-security"></a><span data-ttu-id="b4921-171">Optional步骤 9: 将 SIEM 服务器与 Office 365 云应用程序安全性结合使用</span><span class="sxs-lookup"><span data-stu-id="b4921-171">(Optional) Step 9: Use your SIEM server with Office 365 Cloud App Security</span></span>

<span data-ttu-id="b4921-172">您的组织是否使用安全信息和事件管理 (SIEM) 服务器？</span><span class="sxs-lookup"><span data-stu-id="b4921-172">Is your organization using a security information and event management (SIEM) server?</span></span> <span data-ttu-id="b4921-173">Office 365 云应用安全现在可以与您的 SIEM 服务器集成以启用对警报的集中式监视。</span><span class="sxs-lookup"><span data-stu-id="b4921-173">Office 365 Cloud App Security can now integrate with your SIEM server to enable centralized monitoring of alerts.</span></span> <span data-ttu-id="b4921-174">与 SIEM 服务集成, 使您能够更好地保护云应用程序, 同时维护您的常规安全工作流、自动化安全过程以及在基于云的事件和本地事件之间进行关联。</span><span class="sxs-lookup"><span data-stu-id="b4921-174">Integrating with a SIEM service allows you to better protect your cloud applications while maintaining your usual security workflow, automating security procedures and correlating between cloud-based and on-premises events.</span></span> <span data-ttu-id="b4921-175">SIEM 代理在您的服务器上运行, 从 Office 365 云应用程序安全性中提取警报, 并将这些警报流出到您的 SIEM 服务器中。</span><span class="sxs-lookup"><span data-stu-id="b4921-175">The SIEM agent runs on your server, pulls alerts from Office 365 Cloud App Security, and streams those alerts into your SIEM server.</span></span> <span data-ttu-id="b4921-176">请参阅[SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="b4921-176">See [SIEM integration with Office 365 Cloud App Security](integrate-your-siem-server-with-office-365-cas.md).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="b4921-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b4921-177">Next steps</span></span>

- [<span data-ttu-id="b4921-178">启用 Office 365 云应用安全</span><span class="sxs-lookup"><span data-stu-id="b4921-178">Turn on Office 365 Cloud App Security</span></span>](turn-on-office-365-cas.md)
    
- <span data-ttu-id="b4921-179">尝试使用我们的[测试实验室指南](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment)获取实践体验, 在这里, 你可以演示 Office 365 云应用安全性的强大功能并创建概念证明。</span><span class="sxs-lookup"><span data-stu-id="b4921-179">Try our [Test Lab Guide](https://docs.microsoft.com/office365/enterprise/cloud-app-security-for-your-office-365-dev-test-environment) for a hands-on experience where you can demonstrate the powerful features of Office 365 Cloud App Security and create a proof of concept.</span></span> 
    

