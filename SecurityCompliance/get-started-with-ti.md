---
title: 开始使用 Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: 了解 Office 365 威胁调查和响应, 以及如何开始。
ms.openlocfilehash: 8bd5e68abfa036d1257fb08fb1dd2b730f7de821
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599248"
---
# <a name="get-started-with-threat-investigation-and-response-in-office-365-advanced-threat-protection"></a><span data-ttu-id="76094-103">在 Office 365 高级威胁防护中开始使用威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="76094-103">Get started with threat investigation and response in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="76094-104">如果您是组织的安全团队的一部分, 则可以使用 Office 365 威胁调查和响应功能来保护您的用户免受攻击。</span><span class="sxs-lookup"><span data-stu-id="76094-104">If you are part of your organization's security team, you can use Office 365 threat investigation and response capabilities to protect your users from attacks.</span></span> <span data-ttu-id="76094-105">Office 365 高级威胁防护计划 2 (以前称为 Office 365 威胁智能) 可帮助安全分析员和管理员根据 Office 365 中发生的情况, 通过冒泡方式和标识操作来确保用户安全环境.</span><span class="sxs-lookup"><span data-stu-id="76094-105">Office 365 Advanced Threat Protection Plan 2 (formerly known as Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment.</span></span> <span data-ttu-id="76094-106">这些见解基于威胁智能数据和系统的综合存储库, 以提供与攻击行为和可疑活动对应的发现模式。</span><span class="sxs-lookup"><span data-stu-id="76094-106">These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="76094-107">阅读本文, 了解有关威胁调查和响应的详细信息, 以及如何开始。</span><span class="sxs-lookup"><span data-stu-id="76094-107">Read this article to learn more about threat investigation and response, and how to get started.</span></span>
  
## <a name="what-are-the-threat-investigation-and-response-capabilities-included-in-office-365"></a><span data-ttu-id="76094-108">Office 365 中包含哪些威胁调查和响应功能？</span><span class="sxs-lookup"><span data-stu-id="76094-108">What are the threat investigation and response capabilities included in Office 365?</span></span>

<span data-ttu-id="76094-109">威胁调查和响应功能有助于推动对 Office 365 安全&amp;合规中心中提供的威胁和相关响应操作的深入了解。</span><span class="sxs-lookup"><span data-stu-id="76094-109">Threat investigation and response capabilities help drive insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="76094-110">这些见解可帮助组织的安全团队保护 Office 365 用户免受电子邮件或基于文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="76094-110">These insights can help your organization's security team protect Office 365 users from email or file based attacks.</span></span> <span data-ttu-id="76094-111">这些功能可帮助监视信号和收集来自多个源 (如用户活动、身份验证、电子邮件、受损电脑和安全事件) 的数据。</span><span class="sxs-lookup"><span data-stu-id="76094-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="76094-112">业务决策者和 Office 365 全局管理员、安全管理员和安全分析员都可以使用此信息来了解和响应针对 Office 365 用户的威胁, 并保护其知识产权。</span><span class="sxs-lookup"><span data-stu-id="76094-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect their intellectual property.</span></span>

## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="76094-113">了解威胁仪表板、资源管理器和事件</span><span class="sxs-lookup"><span data-stu-id="76094-113">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="76094-114">安全&amp;合规中心中的这些威胁调查和响应功能, 作为一组工具和响应工作流, 包括[威胁仪表板](#threat-dashboard)、[威胁资源管理器](#threat-explorer)、[事件](get-started-with-ti.md#incidents)、[攻击模拟器](attack-simulator.md)和自动调查 & 响应。</span><span class="sxs-lookup"><span data-stu-id="76094-114">These threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Threat Explorer](#threat-explorer), [Incidents](get-started-with-ti.md#incidents), [Attack Simulator](attack-simulator.md), and Automated Investigations & Response.</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="76094-115">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="76094-115">Threat dashboard</span></span>

<span data-ttu-id="76094-116">使用 "威胁" 仪表板 (也称为 "安全"[仪表板](security-dashboard.md)) 快速查看已解决的威胁, 并以直观方式向业务决策者报告 Office 365 服务如何保护您的业务。</span><span class="sxs-lookup"><span data-stu-id="76094-116">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威胁仪表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="76094-118">若要查看和使用此仪表板, 请&amp;在安全合规性中心中, 转到 "**威胁管理** \> "**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="76094-118">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="76094-119">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="76094-119">Threat Explorer</span></span>

<span data-ttu-id="76094-120">使用[威胁浏览器 (和实时检测)](threat-explorer.md)来分析威胁, 查看一段时间内的攻击量, 并根据威胁系列、攻击者基础结构等对数据进行分析。</span><span class="sxs-lookup"><span data-stu-id="76094-120">Use the [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="76094-121">威胁资源管理器 (也称为浏览器) 是任何安全分析员的调查工作流的起始位置。</span><span class="sxs-lookup"><span data-stu-id="76094-121">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![威胁资源管理器](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="76094-123">若要查看和使用此报告, 请在&amp;安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="76094-123">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="76094-124">例</span><span class="sxs-lookup"><span data-stu-id="76094-124">Incidents</span></span>

<span data-ttu-id="76094-125">使用 "事件" 列表 (也称为 "调查") 查看飞行安全事件的列表。</span><span class="sxs-lookup"><span data-stu-id="76094-125">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="76094-126">事件用于跟踪可疑电子邮件等威胁, 并进行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="76094-126">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 中的当前威胁事件列表](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="76094-128">若要查看您的组织的当前事件列表, 请在安全&amp;合规性中心中, 转到 "**威胁管理** \> **审核** \> **事件**"。</span><span class="sxs-lookup"><span data-stu-id="76094-128">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![在 "安全&amp;合规性中心" 中, \>选择 "威胁管理审核"](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="76094-130">了解有关恶意软件&amp;威胁的详细信息</span><span class="sxs-lookup"><span data-stu-id="76094-130">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="76094-131">作为 Office 365 高级威胁防护计划2产品的一部分, 安全分析员可以查看已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="76094-131">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="76094-132">这有助于确定是否存在可采取的更多预防措施/步骤, 以确保用户安全。</span><span class="sxs-lookup"><span data-stu-id="76094-132">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![显示有关最近威胁的信息的安全趋势](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-threat-investigation-and-response-capabilities"></a><span data-ttu-id="76094-134">我们如何获取这些威胁调查和响应功能？</span><span class="sxs-lookup"><span data-stu-id="76094-134">How do we get these Threat investigation and response capabilities?</span></span>

<span data-ttu-id="76094-135">Office 365 高级威胁防护计划2和企业版 E5 365 中包含 office 威胁 Invesigation 和响应功能。</span><span class="sxs-lookup"><span data-stu-id="76094-135">Office 365 Threat Invesigation and Response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="76094-136">如果你的组织具有不包含这些威胁调查和响应功能的 Office 365 订阅, 你可以将其作为加载项购买, 并附带 Office 365 高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="76094-136">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can purchase these as an add-on along with Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="76094-137">有关计划选项的详细信息, 请参阅[office 365 Platform 服务说明: office 365 &amp;安全合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)和[购买或编辑 Office 365 for business 的加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。</span><span class="sxs-lookup"><span data-stu-id="76094-137">For more information about plan options, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="76094-138">作为 Office 365 全局管理员, 请转到[https://admin.microsoft.com](https://admin.microsoft.com)并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="76094-138">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="76094-139">选择 "**管理员** \> **帐单**" 以查看您的当前订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="76094-139">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="76094-140">如果您看到**office 365 企业版 E5**, 则您的组织具有 Office 365 高级威胁防护计划 2 (其中包括威胁调查和响应功能)。</span><span class="sxs-lookup"><span data-stu-id="76094-140">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="76094-141">如果你看到不同的订阅 (如**Office 365 企业版 E3**或**Office 365 企业版 E1**), 请考虑添加 Office 365 高级威胁防护计划2。</span><span class="sxs-lookup"><span data-stu-id="76094-141">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="76094-142">(为此, 请选择 " **+ 添加订阅**"。)</span><span class="sxs-lookup"><span data-stu-id="76094-142">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="76094-143">在 Microsoft 365 管理中心, 选择 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="76094-143">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="76094-144">向所有活动用户分配 Office 365 高级威胁防护计划2许可证。</span><span class="sxs-lookup"><span data-stu-id="76094-144">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="76094-145">(只有拥有此项许可证的用户才会显示在报告中, 如 Explorer。)</span><span class="sxs-lookup"><span data-stu-id="76094-145">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="76094-146">为组织中将使用 Office 365 高级威胁防护的人员分配角色。</span><span class="sxs-lookup"><span data-stu-id="76094-146">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="76094-147">请参阅[向用户授予对 Office 365 安全&amp;合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md), 并参阅下表:</span><span class="sxs-lookup"><span data-stu-id="76094-147">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="76094-148">**若要执行此活动 .。。**</span><span class="sxs-lookup"><span data-stu-id="76094-148">**To do this activity...**</span></span> <br/> |<span data-ttu-id="76094-149">**您必须具有以下角色之一**</span><span class="sxs-lookup"><span data-stu-id="76094-149">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="76094-150">使用威胁仪表板 (或新[安全仪表板](security-dashboard.md))</span><span class="sxs-lookup"><span data-stu-id="76094-150">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="76094-151">查看有关最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="76094-151">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="76094-152">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="76094-152">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="76094-153">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-153">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="76094-154">安全读者 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-154">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="76094-155">使用[威胁浏览器 (和实时检测)](threat-explorer.md)分析威胁</span><span class="sxs-lookup"><span data-stu-id="76094-155">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="76094-156">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="76094-156">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="76094-157">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-157">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="76094-158">安全读者 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-158">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="76094-159">查看事件 (也称为调查)</span><span class="sxs-lookup"><span data-stu-id="76094-159">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="76094-160">将电子邮件添加到事件</span><span class="sxs-lookup"><span data-stu-id="76094-160">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="76094-161">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="76094-161">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="76094-162">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-162">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="76094-163">安全读者 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-163">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="76094-164">触发事件中的电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="76094-164">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="76094-165">查找和删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="76094-165">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="76094-166">Office 365 全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="76094-166">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="76094-167">上述角色之一和搜索和清除 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-167">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="76094-168">将 Office 365 高级威胁防护计划2与 Microsoft Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="76094-168">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="76094-169">将 Office 365 高级威胁防护计划2与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="76094-169">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="76094-170">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="76094-170">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="76094-171">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="76094-171">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="76094-172">在其他应用程序 (如 Microsoft Defender Security Center 或 SIEM server) 中分配的相应角色</span><span class="sxs-lookup"><span data-stu-id="76094-172">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="76094-173">有关角色、角色组和权限的信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="76094-173">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="76094-174">后续步骤</span><span class="sxs-lookup"><span data-stu-id="76094-174">Next steps</span></span>

- [<span data-ttu-id="76094-175">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="76094-175">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="76094-176">查找并调查已传递的恶意电子邮件 (Office 365 威胁调查和响应)</span><span class="sxs-lookup"><span data-stu-id="76094-176">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="76094-177">集成 Office 365 威胁调查和响应与 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="76094-177">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="76094-178">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="76094-178">Learn about Attack Simulator</span></span>](attack-simulator.md)
  
## <a name="additional-information"></a><span data-ttu-id="76094-179">其他信息</span><span class="sxs-lookup"><span data-stu-id="76094-179">Additional information</span></span>

- [<span data-ttu-id="76094-180">Office 365 高级威胁防护计划和定价</span><span class="sxs-lookup"><span data-stu-id="76094-180">Office 365 Advanced Threat Protection plans and pricing</span></span>](https://products.office.com/exchange/advance-threat-protection) 

- [<span data-ttu-id="76094-181">Office 365 高级威胁防护服务说明</span><span class="sxs-lookup"><span data-stu-id="76094-181">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
