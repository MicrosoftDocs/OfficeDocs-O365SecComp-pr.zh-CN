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
ms.openlocfilehash: f4480e6cdf5a845f591ad118858703dee4d4e631
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995233"
---
# <a name="get-started-with-office-365-advanced-threat-protection-plan-2-formerly-office-365-threat-intelligence"></a><span data-ttu-id="a0650-103">开始使用 Office 365 高级威胁保护计划 2 （以前称为 Office 365 威胁智能）</span><span class="sxs-lookup"><span data-stu-id="a0650-103">Get started with Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="a0650-p101">如果您是组织的安全工作组的一部分，您可以使用威胁智能功能来防止用户受到攻击。Office 365 高级威胁保护计划 2 （以前称为 Office 365 威胁智能） 可帮助安全分析师和管理员保留用户安全通过冒泡 up 见解和标识基于什么操作发生的情况其 Office 365 环境。这些见解基于威胁智能数据和到专色模式的对应于攻击行为和可疑活动的系统的全面存储库。</span><span class="sxs-lookup"><span data-stu-id="a0650-p101">If you are part of your organization's security team, you can use Threat Intelligence capabilities to protect your users from attacks. Office 365 Advanced Threat Protection Plan 2 (formerly Office 365 Threat Intelligence) helps security analysts and administrators keep users safe by bubbling up insights and identifying action based on what is happening in their your Office 365 environment. These insights are based on a comprehensive repository of threat intelligence data and systems to spot patterns that correspond to attack behaviors and suspicious activity.</span></span>
  
<span data-ttu-id="a0650-107">阅读此文，了解有关威胁智能和如何入门。</span><span class="sxs-lookup"><span data-stu-id="a0650-107">Read this article to learn more about Threat Intelligence and how to get started.</span></span>
  
## <a name="what-is-threat-intelligence"></a><span data-ttu-id="a0650-108">威胁智能是什么？</span><span class="sxs-lookup"><span data-stu-id="a0650-108">What is Threat Intelligence?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0650-p102">开始在年 2 月 2019年和以后的几个月内推出，Office 365 威胁智能变得 Office 365 高级威胁保护计划 2，与其他威胁保护功能。若要了解详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="a0650-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="a0650-p103">威胁智能是一系列见解和可用于 Office 365 安全性的信息&amp;合规性中心。这些见解有助于防止攻击的 Office 365 用户组织的安全工作组。威胁智能监控信号，来自多个源，如用户活动、 身份验证、 电子邮件、 受到攻击的 Pc 和安全事件中收集数据。业务决策制定者和 Office 365 全局管理员、 安全管理员和安全分析师可以所有使用 Office 365 威胁智能的信息提供了解和响应对 Office 365 用户和知识产权的威胁属性。</span><span class="sxs-lookup"><span data-stu-id="a0650-p103">Threat Intelligence is a collection of insights and information available in the Office 365 Security &amp; Compliance Center. These insights can help your organization's security team protect Office 365 users from attacks. Threat Intelligence monitors signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents. Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use the information Office 365 Threat Intelligence provides to understand and respond to threats against Office 365 users and intellectual property.</span></span>
  
## <a name="get-acquainted-with-the-threat-dashboard-explorer-and-incidents"></a><span data-ttu-id="a0650-115">熟悉的威胁仪表板、 资源管理器和事件</span><span class="sxs-lookup"><span data-stu-id="a0650-115">Get acquainted with the Threat dashboard, Explorer, and Incidents</span></span>

<span data-ttu-id="a0650-116">威胁安全中的智能曲面&amp;合规性中心，为一的工具和报告，包括[威胁仪表板](get-started-with-ti.md#dashboard)、[威胁资源管理器](get-started-with-ti.md#explorer)中和[事件](get-started-with-ti.md#incidents)。</span><span class="sxs-lookup"><span data-stu-id="a0650-116">Threat Intelligence surfaces in the Security &amp; Compliance Center, as a set of tools and reports, including the [Threat dashboard](get-started-with-ti.md#dashboard), [Threat Explorer](get-started-with-ti.md#explorer), and [Incidents](get-started-with-ti.md#incidents).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="a0650-117">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="a0650-117">Threat dashboard</span></span>

<span data-ttu-id="a0650-118">使用威胁仪表板 （这也称为[安全仪表板](security-dashboard.md)） 要快速查看哪些威胁已得到解决，并作为一种可视方式向业务决策者报告如何 Office 365 服务的保护您的业务。</span><span class="sxs-lookup"><span data-stu-id="a0650-118">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威胁智能仪表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="a0650-120">查看和安全中使用此仪表板，&amp;合规性中心中，转到**威胁管理** \> **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="a0650-120">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>
  
### <a name="threat-explorer"></a><span data-ttu-id="a0650-121">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="a0650-121">Threat Explorer</span></span>

<span data-ttu-id="a0650-p104">使用威胁资源管理器 （这也称为资源管理器） 分析威胁、 随时间推移，请参阅攻击量和分析通过威胁系列，攻击者基础结构的详细信息的数据。威胁资源管理器是任何安全分析师调查工作流的起始位置。</span><span class="sxs-lookup"><span data-stu-id="a0650-p104">Use the Threat Explorer (this is also called Explorer) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more. Threat Explorer is the starting place for any security analyst's investigation workflow.</span></span>
  
![威胁资源管理器](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="a0650-125">查看和安全中使用此报告中，&amp;合规性中心中，转到**威胁管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="a0650-125">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
 ### <a name="incidents"></a><span data-ttu-id="a0650-126">事件</span><span class="sxs-lookup"><span data-stu-id="a0650-126">Incidents</span></span>

<span data-ttu-id="a0650-p105">使用 （这也称为调查） 的事件列表中航班安全事件的列表，请参阅。事件用于跟踪可疑的电子邮件，如威胁和进行进一步调查和修复。</span><span class="sxs-lookup"><span data-stu-id="a0650-p105">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents. Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 威胁智能中的当前事件的列表](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="a0650-130">若要查看为您的组织的当前事件列表安全中&amp;合规性中心中，转到**威胁管理** \> **审阅** \> **事件**。</span><span class="sxs-lookup"><span data-stu-id="a0650-130">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![安全中&amp;合规性中心中，选择威胁管理\>审阅](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)
  
## <a name="learn-more-about-malware-amp-threats"></a><span data-ttu-id="a0650-132">了解有关恶意软件&amp;的威胁</span><span class="sxs-lookup"><span data-stu-id="a0650-132">Learn more about Malware &amp; Threats</span></span>

<span data-ttu-id="a0650-p106">作为 Office 365 高级威胁保护计划 2 产品的一部分，安全分析师可以查看有关已知的威胁的详细信息。这很有用，以确定是否有其他预防措施/步骤可以采取保留用户安全。</span><span class="sxs-lookup"><span data-stu-id="a0650-p106">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat. This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![显示有关最新的威胁的信息的安全趋势](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-threat-intelligence"></a><span data-ttu-id="a0650-136">我们如何获取威胁智能？</span><span class="sxs-lookup"><span data-stu-id="a0650-136">How do we get Threat Intelligence?</span></span>

<span data-ttu-id="a0650-p107">**威胁智能属于立即在 Office 365 高级威胁保护计划 2 中**，它包含某些订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5，在 Office 365教育 A5 等。如果您的组织具有不包括 Office 365 ATP 的订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="a0650-p107">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span>
  
1. <span data-ttu-id="a0650-139">作为 Office 365 全局管理员，请转到[https://portal.office.com](https://portal.office.com)和 Office 365 中使用您的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a0650-139">As an Office 365 global administrator, go to [https://portal.office.com](https://portal.office.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="a0650-140">选择**管理** \> **帐单**以查看您的当前订阅所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="a0650-140">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 

    - <span data-ttu-id="a0650-141">如果您看到**Office 365 企业 E5**，然后您的组织具有 Office 365 高级威胁保护计划 2，其中包括威胁智能。</span><span class="sxs-lookup"><span data-stu-id="a0650-141">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2, which includes Threat Intelligence.</span></span> 
    - <span data-ttu-id="a0650-p108">如果您看到其他订阅，例如**Office 365 企业版 E3**或**Office 365 企业版 E1**，请考虑添加高级威胁保护计划 2。（若要执行的操作，选择 **+ 添加订阅**。）</span><span class="sxs-lookup"><span data-stu-id="a0650-p108">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Advanced Threat Protection Plan 2. (To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="a0650-144">在 Office 365 管理中心中，选择**用户** \> **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="a0650-144">In the Office 365 admin center, choose **Users** \> **Active users**.</span></span>
    
5. <span data-ttu-id="a0650-p109">将 Office 365 高级威胁 Protection 许可证分配给所有活动用户。（仅限具有威胁智能功能的许可证的用户会显示在报表中，如资源管理器。）</span><span class="sxs-lookup"><span data-stu-id="a0650-p109">Assign Office 365 Advanced Threat Protection licenses to all active users. (Only users who have a license for Threat Intelligence capabilities will show up in reports, such as Explorer.)</span></span>
    
6. <span data-ttu-id="a0650-p110">分配给将使用 Office 365 高级威胁保护您的组织中人员的角色。请参阅[向 Office 365 安全性授予用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)，请参阅下表和：</span><span class="sxs-lookup"><span data-stu-id="a0650-p110">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection. See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="a0650-149">**若要执行此活动...**</span><span class="sxs-lookup"><span data-stu-id="a0650-149">**To do this activity...**</span></span> <br/> |<span data-ttu-id="a0650-150">**您必须具有这些角色之一**</span><span class="sxs-lookup"><span data-stu-id="a0650-150">**You must have one of these roles**</span></span> <br/> |
|<span data-ttu-id="a0650-151">使用威胁仪表板 （或新的[安全仪表板](security-dashboard.md)）</span><span class="sxs-lookup"><span data-stu-id="a0650-151">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span>  <br/> <span data-ttu-id="a0650-152">查看有关最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="a0650-152">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="a0650-153">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="a0650-153">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="a0650-154">安全管理员 （分配在 Azure Active Directory 管理中心）</span><span class="sxs-lookup"><span data-stu-id="a0650-154">Security Administrator (assigned in the Azure Active Directory admin center)</span></span>  <br/> <span data-ttu-id="a0650-155">安全读者 （分配在 Azure Active Directory 管理中心）</span><span class="sxs-lookup"><span data-stu-id="a0650-155">Security Reader (assigned in the Azure Active Directory admin center)</span></span>  <br/> |
|<span data-ttu-id="a0650-156">使用威胁资源管理器 （也称为资源管理器）</span><span class="sxs-lookup"><span data-stu-id="a0650-156">Use Threat Explorer (also referred to as Explorer)</span></span>  <br/> <span data-ttu-id="a0650-157">分析威胁</span><span class="sxs-lookup"><span data-stu-id="a0650-157">Analyze threats</span></span>  <br/> |<span data-ttu-id="a0650-158">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="a0650-158">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="a0650-159">安全管理员 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-159">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="a0650-160">安全读者 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-160">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="a0650-161">视图事件 （也称为调查）</span><span class="sxs-lookup"><span data-stu-id="a0650-161">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="a0650-162">将电子邮件消息添加到事件</span><span class="sxs-lookup"><span data-stu-id="a0650-162">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="a0650-163">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="a0650-163">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="a0650-164">安全管理员 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-164">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="a0650-165">安全读者 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-165">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="a0650-166">在事件的触发电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="a0650-166">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="a0650-167">查找并删除可疑的电子邮件</span><span class="sxs-lookup"><span data-stu-id="a0650-167">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="a0650-168">Office 365 全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="a0650-168">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="a0650-169">上面的角色和搜索和清除之一 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-169">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
|<span data-ttu-id="a0650-170">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="a0650-170">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>  <br/> <span data-ttu-id="a0650-171">将 Office 365 威胁智能与 SIEM server 相集成</span><span class="sxs-lookup"><span data-stu-id="a0650-171">Integrate Office 365 Threat Intelligence with a SIEM server</span></span>  <br/> |<span data-ttu-id="a0650-172">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="a0650-172">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="a0650-173">安全管理员 (安全中分配&amp;合规性中心)</span><span class="sxs-lookup"><span data-stu-id="a0650-173">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="a0650-174">其他应用程序 （例如 Windows Defender 高级威胁保护门户或 SIEM 服务器） 中分配的相应角色</span><span class="sxs-lookup"><span data-stu-id="a0650-174">Appropriate role assigned in additional applications (such as Windows Defender Advanced Threat Protection portal or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="a0650-175">有关角色、 角色组和权限的信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a0650-175">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="a0650-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a0650-176">Next steps</span></span>

- [<span data-ttu-id="a0650-177">了解威胁跟踪器-新的和值得注意</span><span class="sxs-lookup"><span data-stu-id="a0650-177">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="a0650-178">查找并调查恶意电子邮件已送达 （Office 365 威胁智能）</span><span class="sxs-lookup"><span data-stu-id="a0650-178">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="a0650-179">将 Office 365 威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="a0650-179">Integrate Office 365 Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="a0650-180">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="a0650-180">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

