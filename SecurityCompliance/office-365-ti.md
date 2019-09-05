---
title: Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/23/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: 了解 Office 365 中的威胁智能功能。高级威胁防护可帮助您研究组织的威胁、响应恶意软件、网络钓鱼和 Office 365 已代表您检测到的其他攻击，并搜索威胁指示器.
ms.openlocfilehash: 1d31f3a464060f5b72730e15895d918e61aa09a1
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761648"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="94cd9-103">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="94cd9-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="94cd9-104">Office 365 中的威胁调查和响应功能[高级威胁防护](office-365-atp.md)帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户：</span><span class="sxs-lookup"><span data-stu-id="94cd9-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
- <span data-ttu-id="94cd9-105">轻松识别、监控和理解 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="94cd9-105">Making it easy to identify, monitor and understand cyberattacks</span></span>
    
- <span data-ttu-id="94cd9-106">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 团队中的威胁</span><span class="sxs-lookup"><span data-stu-id="94cd9-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
- <span data-ttu-id="94cd9-107">提供有关帮助安全操作的见解和知识，以防止针对组织的 cyberattacks</span><span class="sxs-lookup"><span data-stu-id="94cd9-107">Providing insights and knowledge to help security operations prevent cyberattacks against their organization</span></span>

- <span data-ttu-id="94cd9-108">对基于电子邮件的关键威胁采用[自动调查和响应](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="94cd9-108">Employing [automated investigation and response](automated-investigation-response-office.md) for critical email-based threats</span></span>
    
<span data-ttu-id="94cd9-109">威胁调查和响应功能提供了对 Office 365 安全&amp;合规中心中提供的威胁和相关响应操作的见解。</span><span class="sxs-lookup"><span data-stu-id="94cd9-109">Threat investigation and response capabilities provide insights into threats and related response actions that are available in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="94cd9-110">这些见解可帮助您的组织的安全团队保护 Office 365 用户免受电子邮件或基于文件的攻击。</span><span class="sxs-lookup"><span data-stu-id="94cd9-110">These insights can help your organization's security team protect Office 365 users from email- or file-based attacks.</span></span> <span data-ttu-id="94cd9-111">这些功能可帮助监视信号和收集来自多个源（如用户活动、身份验证、电子邮件、受损电脑和安全事件）的数据。</span><span class="sxs-lookup"><span data-stu-id="94cd9-111">The capabilities help monitor signals and gathers data from multiple sources, such as user activity, authentication, email, compromised PCs, and security incidents.</span></span> <span data-ttu-id="94cd9-112">业务决策者和 Office 365 全局管理员、安全管理员和安全分析员都可以使用此信息来了解和响应针对 Office 365 用户的威胁，并保护知识产权。</span><span class="sxs-lookup"><span data-stu-id="94cd9-112">Business decision makers and Office 365 global administrators, security administrators, and security analysts can all use this information to understand and respond to threats against Office 365 users and protect intellectual property.</span></span>

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a><span data-ttu-id="94cd9-113">了解威胁调查和响应工具</span><span class="sxs-lookup"><span data-stu-id="94cd9-113">Get acquainted with threat investigation and response tools</span></span>

<span data-ttu-id="94cd9-114">安全&amp;合规中心中的威胁调查和响应功能，作为一组工具和响应工作流，包括[威胁仪表板](#threat-dashboard)、[资源管理器](#threat-explorer)、[事件](#incidents)、[攻击模拟器](#attack-simulator)和[自动调查 & 响应](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="94cd9-114">Threat investigation and response capabilities surface in the Security &amp; Compliance Center, as a set of tools and response workflows, including the [threat dashboard](#threat-dashboard), [Explorer](#threat-explorer), [Incidents](#incidents), [Attack Simulator](#attack-simulator), and [Automated Investigation & Response](automated-investigation-response-office.md).</span></span>
  
### <a name="threat-dashboard"></a><span data-ttu-id="94cd9-115">威胁仪表板</span><span class="sxs-lookup"><span data-stu-id="94cd9-115">Threat dashboard</span></span>

<span data-ttu-id="94cd9-116">使用 "威胁" 仪表板（也称为 "安全"[仪表板](security-dashboard.md)）快速查看已解决的威胁，并以直观方式向业务决策者报告 Office 365 服务如何保护您的业务。</span><span class="sxs-lookup"><span data-stu-id="94cd9-116">Use the Threat dashboard (this is also referred to as the [Security dashboard](security-dashboard.md)) to quickly see what threats have been addressed, and as a visual way to report to business decision makers how Office 365 services are securing your business.</span></span>
  
![威胁仪表板](media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
<span data-ttu-id="94cd9-118">若要查看和使用此仪表板，请&amp;在安全合规性中心中，转到 "**威胁管理** \> "**仪表板**。</span><span class="sxs-lookup"><span data-stu-id="94cd9-118">To view and use this dashboard, in the Security &amp; Compliance Center, go to **Threat management** \> **Dashboard**.</span></span>

<span data-ttu-id="94cd9-119">若要详细了解</span><span class="sxs-lookup"><span data-stu-id="94cd9-119">To learn more about</span></span> 
  
### <a name="threat-explorer"></a><span data-ttu-id="94cd9-120">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="94cd9-120">Threat Explorer</span></span>

<span data-ttu-id="94cd9-121">使用[威胁浏览器（和实时检测）](threat-explorer.md)来分析威胁，查看一段时间内的攻击量，并根据威胁系列、攻击者基础结构等对数据进行分析。</span><span class="sxs-lookup"><span data-stu-id="94cd9-121">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats, see the volume of attacks over time, and analyze data by threat families, attacker infrastructure, and more.</span></span> <span data-ttu-id="94cd9-122">威胁资源管理器（也称为浏览器）是任何安全分析员的调查工作流的起始位置。</span><span class="sxs-lookup"><span data-stu-id="94cd9-122">Threat Explorer (also referred to as Explorer) is the starting place for any security analyst's investigation workflow.</span></span>
  
![威胁资源管理器](media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
<span data-ttu-id="94cd9-124">若要查看和使用此报告，请在&amp;安全合规性中心中，转到 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="94cd9-124">To view and use this report, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
  
### <a name="incidents"></a><span data-ttu-id="94cd9-125">例</span><span class="sxs-lookup"><span data-stu-id="94cd9-125">Incidents</span></span>

<span data-ttu-id="94cd9-126">使用 "事件" 列表（也称为 "调查"）查看飞行安全事件的列表。</span><span class="sxs-lookup"><span data-stu-id="94cd9-126">Use the Incidents list (this is also called Investigations) to see a list of in flight security incidents.</span></span> <span data-ttu-id="94cd9-127">事件用于跟踪可疑电子邮件等威胁，并进行进一步调查和修正。</span><span class="sxs-lookup"><span data-stu-id="94cd9-127">Incidents are used to track threats such as suspicious email messages, and to conduct further investigation and remediation.</span></span>
  
![Office 365 中的当前威胁事件列表](media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
<span data-ttu-id="94cd9-129">若要查看您的组织的当前事件列表，请在安全&amp;合规性中心中，转到 "**威胁管理** \> **审核** \> **事件**"。</span><span class="sxs-lookup"><span data-stu-id="94cd9-129">To view the list of current incidents for your organization, in the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Incidents**.</span></span>
  
![在 "安全&amp;合规性中心" 中， \>选择 "威胁管理审核"](media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a><span data-ttu-id="94cd9-131">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="94cd9-131">Attack Simulator</span></span>

<span data-ttu-id="94cd9-132">使用攻击模拟器在您的组织中设置和运行真实的 cyberattacks，并在真正的 cyberattack 影响您的企业之前识别易受攻击的人员。</span><span class="sxs-lookup"><span data-stu-id="94cd9-132">Use Attack Simulator to set up and run realistic cyberattacks in your organization, and identify vulnerable people before a real cyberattack affects your business.</span></span> <span data-ttu-id="94cd9-133">若要了解详细信息，请参阅[Office 365 中的攻击模拟器](attack-simulator.md)。</span><span class="sxs-lookup"><span data-stu-id="94cd9-133">To learn more, see [Attack Simulator in Office 365](attack-simulator.md).</span></span>

### <a name="automated-investigation-and-response"></a><span data-ttu-id="94cd9-134">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="94cd9-134">Automated investigation and response</span></span>

<span data-ttu-id="94cd9-135">使用自动调查和响应（空气）功能来节省与内容、设备和人员相关的时间和精力，以防止组织中的威胁带来风险。</span><span class="sxs-lookup"><span data-stu-id="94cd9-135">Use automated investigation and response (AIR) capabilities to save time and effort correlating content, devices, and people at risk from threats in your organization.</span></span> <span data-ttu-id="94cd9-136">只要触发了某些警报，或安全操作团队启动时，AIR 进程就可以开始。</span><span class="sxs-lookup"><span data-stu-id="94cd9-136">AIR processes can begin whenever certain alerts are triggered, or when started by your security operations team.</span></span> <span data-ttu-id="94cd9-137">若要了解详细信息，请参阅[使用 Office 365 的自动化调查和响应（AIR）](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="94cd9-137">To learn more, see [Automated Investigation and Response (AIR) with Office 365](automated-investigation-response-office.md).</span></span> 
  
## <a name="threat-intelligence-widgets"></a><span data-ttu-id="94cd9-138">威胁智能小部件</span><span class="sxs-lookup"><span data-stu-id="94cd9-138">Threat intelligence widgets</span></span>

<span data-ttu-id="94cd9-139">作为 Office 365 高级威胁防护计划2产品的一部分，安全分析员可以查看已知威胁的详细信息。</span><span class="sxs-lookup"><span data-stu-id="94cd9-139">As part of the Office 365 Advanced Threat Protection Plan 2 offering, security analysts can review details about a known threat.</span></span> <span data-ttu-id="94cd9-140">这有助于确定是否存在可采取的更多预防措施/步骤，以确保用户安全。</span><span class="sxs-lookup"><span data-stu-id="94cd9-140">This is useful to determine whether there are additional preventative measures/steps that can be taken to keep users safe.</span></span>
  
![显示有关最近威胁的信息的安全趋势](media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a><span data-ttu-id="94cd9-142">如何获取这些功能？</span><span class="sxs-lookup"><span data-stu-id="94cd9-142">How do we get these capabilities?</span></span>

<span data-ttu-id="94cd9-143">Office 365 高级威胁防护计划2和企业版 E5 中包含 office 365 威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="94cd9-143">Office 365 threat investigation and response capabilities are included in Office 365 Advanced Threat Protection Plan 2 and Enterprise E5.</span></span> 

> [!TIP]
> <span data-ttu-id="94cd9-144">如果您的组织具有不包含这些威胁调查和响应功能的 Office 365 订阅，则可能会将 Office 365 高级威胁防护计划2作为加载项进行购买。</span><span class="sxs-lookup"><span data-stu-id="94cd9-144">If your organization has an Office 365 subscription that does not include these threat investigation and response capabilities, you can potentially purchase Office 365 Advanced Threat Protection Plan 2 as an add-on.</span></span> <span data-ttu-id="94cd9-145">有关计划选项的详细信息，请参阅[office 365 高级威胁防护服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)和[购买或编辑适用于 Office 365 for business 的加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。</span><span class="sxs-lookup"><span data-stu-id="94cd9-145">For more information about plan options, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) and [Buy or edit an add-on for Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>
  
1. <span data-ttu-id="94cd9-146">作为 Office 365 全局管理员，请转到[https://admin.microsoft.com](https://admin.microsoft.com)并使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="94cd9-146">As an Office 365 global administrator, go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in using your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="94cd9-147">选择 "**管理员** \> **帐单**" 以查看您的当前订阅包括的内容。</span><span class="sxs-lookup"><span data-stu-id="94cd9-147">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> 
    - <span data-ttu-id="94cd9-148">如果您看到**office 365 企业版 E5**，则您的组织具有 Office 365 高级威胁防护计划2（其中包括威胁调查和响应功能）。</span><span class="sxs-lookup"><span data-stu-id="94cd9-148">If you see **Office 365 Enterprise E5**, then your organization has Office 365 Advanced Threat Protection Plan 2 (which includes threat investigation and response capabilities).</span></span> 
    - <span data-ttu-id="94cd9-149">如果你看到不同的订阅（如**Office 365 企业版 E3**或**Office 365 企业版 E1**），请考虑添加 Office 365 高级威胁防护计划2。</span><span class="sxs-lookup"><span data-stu-id="94cd9-149">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="94cd9-150">（为此，请选择 " **+ 添加订阅**"。）</span><span class="sxs-lookup"><span data-stu-id="94cd9-150">(To do that, choose **+ Add subscription**.)</span></span>
    
3. <span data-ttu-id="94cd9-151">在 Microsoft 365 管理中心，选择 "**用户** \> **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="94cd9-151">In the Microsoft 365 admin center, choose **Users** \> **Active users**.</span></span>
    
4. <span data-ttu-id="94cd9-152">向所有活动用户分配 Office 365 高级威胁防护计划2许可证。</span><span class="sxs-lookup"><span data-stu-id="94cd9-152">Assign Office 365 Advanced Threat Protection Plan 2 licenses to all active users.</span></span> <span data-ttu-id="94cd9-153">（只有拥有此项许可证的用户才会显示在报告中，如 Explorer。）</span><span class="sxs-lookup"><span data-stu-id="94cd9-153">(Only users who have a license for this will show up in reports, such as Explorer.)</span></span>
    
5. <span data-ttu-id="94cd9-154">为组织中将使用 Office 365 高级威胁防护的人员分配角色。</span><span class="sxs-lookup"><span data-stu-id="94cd9-154">Assign roles to people in your organization who will be working with the Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="94cd9-155">请参阅[向用户授予对 Office 365 安全&amp;合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)，并参阅下表：</span><span class="sxs-lookup"><span data-stu-id="94cd9-155">See [Give users access to the Office 365 Security &amp; Compliance Center](grant-access-to-the-security-and-compliance-center.md), and refer to the following table:</span></span><br/>

  |<span data-ttu-id="94cd9-156">**若要执行此活动 .。。**</span><span class="sxs-lookup"><span data-stu-id="94cd9-156">**To do this activity...**</span></span> <br/> |<span data-ttu-id="94cd9-157">**您必须具有以下角色之一**</span><span class="sxs-lookup"><span data-stu-id="94cd9-157">**You must have one of these roles**</span></span> <br/> |  
  |:-----|:-----|
  |<span data-ttu-id="94cd9-158">使用威胁仪表板（或新[安全仪表板](security-dashboard.md)）</span><span class="sxs-lookup"><span data-stu-id="94cd9-158">Use the Threat dashboard (or the new [Security dashboard](security-dashboard.md))</span></span><br/> <span data-ttu-id="94cd9-159">查看有关最近或当前威胁的信息</span><span class="sxs-lookup"><span data-stu-id="94cd9-159">View information about recent or current threats</span></span>  <br/> |<span data-ttu-id="94cd9-160">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="94cd9-160">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="94cd9-161">安全管理员（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-161">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="94cd9-162">安全读者（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-162">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="94cd9-163">使用[威胁浏览器（和实时检测）](threat-explorer.md)分析威胁</span><span class="sxs-lookup"><span data-stu-id="94cd9-163">Use [Threat Explorer (and real-time detections)](threat-explorer.md) to analyze threats</span></span>  <br/> |<span data-ttu-id="94cd9-164">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="94cd9-164">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="94cd9-165">安全管理员（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-165">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="94cd9-166">安全读者（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-166">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="94cd9-167">查看事件（也称为调查）</span><span class="sxs-lookup"><span data-stu-id="94cd9-167">View Incidents (also referred to as Investigations)</span></span> <br/> <span data-ttu-id="94cd9-168">将电子邮件添加到事件</span><span class="sxs-lookup"><span data-stu-id="94cd9-168">Add email messages to an incident</span></span>  <br/> |<span data-ttu-id="94cd9-169">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="94cd9-169">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="94cd9-170">安全管理员（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-170">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="94cd9-171">安全读者（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-171">Security Reader (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="94cd9-172">触发事件中的电子邮件操作</span><span class="sxs-lookup"><span data-stu-id="94cd9-172">Trigger email actions in an incident</span></span>  <br/> <span data-ttu-id="94cd9-173">查找和删除可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="94cd9-173">Find and delete suspicious email messages</span></span>  <br/> |<span data-ttu-id="94cd9-174">Office 365 全局管理员或安全管理员</span><span class="sxs-lookup"><span data-stu-id="94cd9-174">Office 365 Global Administrator or Security Administrator</span></span>  <br/> <span data-ttu-id="94cd9-175">上述角色之一和搜索和清除（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-175">One of the roles above and Search and Purge (assigned in the Security &amp; Compliance Center)</span></span>  <br/> |
  |<span data-ttu-id="94cd9-176">将 Office 365 高级威胁防护计划2与 Microsoft Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="94cd9-176">Integrate Office 365 Advanced Threat Protection Plan 2 with Microsoft Defender ATP</span></span>  <br/> <span data-ttu-id="94cd9-177">将 Office 365 高级威胁防护计划2与 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="94cd9-177">Integrate Office 365 Advanced Threat Protection Plan 2 with a SIEM server</span></span>  <br/> |<span data-ttu-id="94cd9-178">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="94cd9-178">Office 365 Global Administrator</span></span>  <br/> <span data-ttu-id="94cd9-179">安全管理员（在安全&amp;合规中心中分配）</span><span class="sxs-lookup"><span data-stu-id="94cd9-179">Security Administrator (assigned in the Security &amp; Compliance Center)</span></span>  <br/> <span data-ttu-id="94cd9-180">在其他应用程序（如 Microsoft Defender Security Center 或 SIEM server）中分配的相应角色</span><span class="sxs-lookup"><span data-stu-id="94cd9-180">Appropriate role assigned in additional applications (such as Microsoft Defender Security Center or a SIEM server)</span></span>  <br/> |
   
<span data-ttu-id="94cd9-181">有关角色、角色组和权限的信息，请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="94cd9-181">For information about roles, role groups, and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="94cd9-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="94cd9-182">Next steps</span></span>

- [<span data-ttu-id="94cd9-183">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="94cd9-183">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="94cd9-184">查找并调查已传递的恶意电子邮件（Office 365 威胁调查和响应）</span><span class="sxs-lookup"><span data-stu-id="94cd9-184">Find and investigate malicious email that was delivered (Office 365 Threat Investigation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="94cd9-185">集成 Office 365 威胁调查和响应与 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="94cd9-185">Integrate Office 365 Threat Investigation and Response with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
- [<span data-ttu-id="94cd9-186">了解攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="94cd9-186">Learn about Attack Simulator</span></span>](attack-simulator.md)
  

