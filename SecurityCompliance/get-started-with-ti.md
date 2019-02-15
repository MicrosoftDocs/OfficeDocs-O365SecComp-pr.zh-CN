---
title: 开始使用 Office 365 威胁智能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 38e9b67f-d188-490f-bc91-a1ae4b270441
ms.collection:
- M365-security-compliance
description: 了解 Office 365 威胁智能以及如何入门。
ms.openlocfilehash: 6412f575bbe581aa469c7ad615213564b728d0aa
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051163"
---
# <a name="get-started-with-threat-intelligence"></a><span data-ttu-id="4c190-103">威胁智能入门</span><span class="sxs-lookup"><span data-stu-id="4c190-103">Get started with Threat Intelligence</span></span>

<span data-ttu-id="4c190-p101">如果您是组织的安全团队的一部分, 则可以使用威胁智能功能来保护您的用户免受攻击。Office 365 高级威胁防护计划 2 (以前称为 "office 365 威胁智能") 可帮助安全分析员和管理员根据您的 Office 365 环境中发生的情况, 通过冒泡和识别操作使用户保持安全。这些见解基于威胁智能数据和系统的综合存储库, 以提供与攻击行为和可疑活动对应的发现模式。</span><span class="sxs-lookup"><span data-stu-id="4c190-p101">If you are part of your organization's security team, you can use Threat Intelligence capabilities to protect your users from attacks. Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment. These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="4c190-107">阅读本文, 了解有关威胁智能和入门方式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c190-107">Read this article to learn more about Threat Intelligence and how to get started.</span></span>
  
## <a name="what-is-threat-intelligence"></a><span data-ttu-id="4c190-108">什么是威胁智能？</span><span class="sxs-lookup"><span data-stu-id="4c190-108">What is Threat Intelligence?</span></span>

<span data-ttu-id="4c190-p102">威胁智能是 Office 365 安全&amp;合规中心中提供的见解和信息的集合。这些见解可帮助贵组织的安全团队保护 Office 365 用户免受攻击。威胁智能监视信号并收集来自多个源 (如用户活动、身份验证、电子邮件、受损电脑和安全事件) 的数据。业务决策者和 Office 365 全局管理员、安全管理员和安全分析员都可以使用 office 365 威胁智能提供的信息来了解有关 office 365 用户和知识的威胁并对其做出响应财产.</span><span class="sxs-lookup"><span data-stu-id="4c190-p102">Threat Intelligence is a collection of insights and information available in the Office 365 Security &amp; Compliance Center. These insights can help your organization's security team protect Office 365 users from attacks. Threat Intelligence monitors signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents. Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use the information Office 365 Threat Intelligence provides to understand and respond to threats against Office 365 users and intellectual property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c190-p103">从2019年2月起开始, 在接下来的几个月中, office 365 威胁情报将成为 office 365 高级威胁防护计划 2, 其中包含其他威胁防护功能。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="4c190-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="4c190-115">了解威胁仪表板、资源管理器和事件</span><span class="sxs-lookup"><span data-stu-id="4c190-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="4c190-116">安全&amp;合规中心中的威胁智能图面, 作为一组工具和报告, 包括[威胁仪表板](get-started-with-ti.md#dashboard)、[威胁浏览器](get-started-with-ti.md#explorer)和[事件](get-started-with-ti.md#incidents)。</span><span class="sxs-lookup"><span data-stu-id="4c190-116">Threat Intelligence surfaces in the Security &amp; Compliance Center, as a set of tools and reports, including the [Threat dashboard](get-started-with-ti.md#dashboard), [Threat Explorer](get-started-with-ti.md#explorer), and [Incidents](get-started-with-ti.md#incidents).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="4c190-117">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="4c190-117">Threat dashboard</span></span>

<span data-ttu-id="4c190-118">使用 "威胁" 仪表板 (也称为 "安全"[仪表板](security-dashboard.md)) 快速查看已解决的威胁, 并以直观方式向业务决策者报告 Office 365 服务如何保护您的业务。</span><span class="sxs-lookup"><span data-stu-id="4c190-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威胁智能仪表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="4c190-120">若要查看和使用此仪表板, 请&amp;在安全合规性中心中, 转到 "**威胁管理** \> "**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="4c190-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="4c190-121">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="4c190-121">Threat Explorer</span></span>

<span data-ttu-id="4c190-p104">使用威胁资源管理器 (也称为 "资源管理器") 分析威胁、查看一段时间内的攻击量, 以及根据威胁系列、攻击者基础结构等对数据进行分析。威胁资源管理器是任何安全分析员的调查工作流的起始位置。</span><span class="sxs-lookup"><span data-stu-id="4c190-p104">Use the Threat Explorer (this is also called Explorer) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more. Threat Explorer is the starting place for any security analyst's investigation workflow.</span></span>
  
![威胁资源管理器](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="4c190-125">若要查看和使用此报告, 请在&amp;安全合规性中心中, 转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="4c190-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="4c190-126">例</span><span class="sxs-lookup"><span data-stu-id="4c190-126">Incidents</span></span>

<span data-ttu-id="4c190-p105">使用 "事件" 列表 (也称为 "调查") 查看飞行安全事件的列表。事件用于跟踪可疑电子邮件等威胁, 并进行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="4c190-p105">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents. Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 威胁智能中的当前事件列表](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="4c190-130">若要查看您的组织的当前事件列表, 请在安全&amp;合规性中心中, 转到 "**威胁管理** \> **审核** \> **事件**"。</span><span class="sxs-lookup"><span data-stu-id="4c190-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![在 "安全&amp;合规性中心" 中, \>选择 "威胁管理审核"](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="4c190-132">了解有关恶意软件&amp;威胁的详细信息</span><span class="sxs-lookup"><span data-stu-id="4c190-132">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="4c190-p106">作为 Office 365 高级威胁防护计划2产品的一部分, 安全分析员可以查看已知威胁的详细信息。这有助于确定是否存在可采取的更多预防措施/步骤, 以确保用户安全。</span><span class="sxs-lookup"><span data-stu-id="4c190-p106">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat. This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![显示有关最近威胁的信息的安全趋势](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-threat-intelligence"></a><span data-ttu-id="4c190-136">如何获取威胁智能？</span><span class="sxs-lookup"><span data-stu-id="4c190-136">How do we get Threat Intelligence?</span></span>

<span data-ttu-id="4c190-p107">**威胁智能现已成为 Office 365 高级威胁防护计划2中的一部分**, 在某些订阅 (如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 企业版 E5、office 365) 中包含。教育版 A5 等。如果您的组织有一个不包含 Office 365 ATP 的订阅, 则可能会将 atp 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="4c190-p107">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span>
  
1. <span data-ttu-id="4c190-139">作为 office 365 全局管理员, 请转到[https://portal.office.com](https://portal.office.com)并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="4c190-139">As an Office 365 global administrator, go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="4c190-140">选择 "**管理员** \> **帐单**" 以查看您的当前订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="4c190-140">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 

    - <span data-ttu-id="4c190-141">如果您看到**office 365 企业版 E5**, 则您的组织具有 office 365 高级威胁防护计划 2, 其中包括威胁智能。</span><span class="sxs-lookup"><span data-stu-id="4c190-141">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2, which includes Threat Intelligence.</span></span> 
    - <span data-ttu-id="4c190-p108">如果你看到不同的订阅 (如**Office 365 企业版 E3**或**office 365 企业版 E1**), 请考虑添加高级威胁防护计划2。(为此, 请选择 " **+ 添加订阅**"。)</span><span class="sxs-lookup"><span data-stu-id="4c190-p108">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Advanced Threat Protection Plan 2. (To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="4c190-144">在 Office 365 管理中心中, 选择 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="4c190-144">In the Office 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="4c190-p109">将 Office 365 高级威胁防护许可证分配给所有活动用户。(只有拥有威胁智能功能许可证的用户才会显示在报告中, 如 Explorer)。</span><span class="sxs-lookup"><span data-stu-id="4c190-p109">Assign Office 365 Advanced Threat Protection licenses to all active users. (Only users who have a license for Threat Intelligence capabilities will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="4c190-p110">为组织中将使用 Office 365 高级威胁防护的人员分配角色。请参阅[向用户授予对 Office 365 安全&amp;合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md), 并参阅下表:</span><span class="sxs-lookup"><span data-stu-id="4c190-p110">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection. See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="4c190-149">**若要执行此活动 .。。**</span><span class="sxs-lookup"><span data-stu-id="4c190-149">**To do this activity...**</span></span> <br/> |<span data-ttu-id="4c190-150">**您必须具有以下角色之一**</span><span class="sxs-lookup"><span data-stu-id="4c190-150">**You must have one of these roles**</span></span> <br/> |
|<span data-ttu-id="4c190-151">使用威胁仪表板 (或新[安全仪表板](security-dashboard.md))</span><span class="sxs-lookup"><span data-stu-id="4c190-151">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span>  <br/> <span data-ttu-id="4c190-152">查看有关最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="4c190-152">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="4c190-153">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="4c190-153">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="4c190-154">安全管理员 (在 Azure Active Directory 管理中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-154">Security Administrator (assigned in the Azure Active Directory admin center)</span></span>  <br/> <span data-ttu-id="4c190-155">安全读者 (在 Azure Active Directory 管理中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-155">Security Reader (assigned in the Azure Active Directory admin center)</span></span>  <br/> |
|<span data-ttu-id="4c190-156">使用威胁资源管理器 (也称为资源管理器)</span><span class="sxs-lookup"><span data-stu-id="4c190-156">Use Threat Explorer (also referred to as Explorer)</span></span>  <br/> <span data-ttu-id="4c190-157">分析威胁</span><span class="sxs-lookup"><span data-stu-id="4c190-157">Analyze threats</span></span>  <br/> |<span data-ttu-id="4c190-158">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="4c190-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="4c190-159">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="4c190-160">安全读者 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="4c190-161">查看事件 (也称为调查)</span><span class="sxs-lookup"><span data-stu-id="4c190-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="4c190-162">将电子邮件添加到事件</span><span class="sxs-lookup"><span data-stu-id="4c190-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="4c190-163">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="4c190-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="4c190-164">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="4c190-165">安全读者 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="4c190-166">触发事件中的电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="4c190-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="4c190-167">查找和删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="4c190-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="4c190-168">Office 365 全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="4c190-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="4c190-169">上述角色之一和搜索和清除 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="4c190-170">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="4c190-170">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>  <br/> <span data-ttu-id="4c190-171">将 Office 365 威胁智能与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="4c190-171">Integrate Office 365 Threat Intelligence with a SIEM server</span></span>  <br/> |<span data-ttu-id="4c190-172">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="4c190-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="4c190-173">安全管理员 (在安全&amp;合规中心中分配)</span><span class="sxs-lookup"><span data-stu-id="4c190-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="4c190-174">在其他应用程序中分配的相应角色 (如 Windows Defender 高级威胁防护门户或 SIEM server)</span><span class="sxs-lookup"><span data-stu-id="4c190-174">Appropriate role assigned in additional applications (such as Windows Defender Advanced Threat Protection portal or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="4c190-175">有关角色、角色组和权限的信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4c190-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="4c190-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4c190-176">Next steps</span></span>

- [<span data-ttu-id="4c190-177">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="4c190-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="4c190-178">查找并调查提供的恶意电子邮件 (Office 365 威胁智能)</span><span class="sxs-lookup"><span data-stu-id="4c190-178">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="4c190-179">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="4c190-179">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="4c190-180">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="4c190-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

