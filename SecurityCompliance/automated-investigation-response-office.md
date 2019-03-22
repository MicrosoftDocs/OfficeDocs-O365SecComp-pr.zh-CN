---
title: 使用 Office 365 威胁智能进行自动调查和响应 (空中)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/21/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护中的自动化调查和响应功能。
ms.openlocfilehash: c2d5acd0bf26dc28b30f26488adf47de2c834fb6
ms.sourcegitcommit: a56128c7be5d59e976851c27301031e19fa1997d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30736233"
---
# <a name="automated-investigation-and-response-air-with-office-365-threat-intelligence"></a><span data-ttu-id="6323e-103">使用 Office 365 威胁智能进行自动调查和响应 (空中)</span><span class="sxs-lookup"><span data-stu-id="6323e-103">Automated Investigation and Response (AIR) with Office 365 Threat Intelligence</span></span>

<span data-ttu-id="6323e-104">自动化调查和响应 (空中) (即将推出[Office 365 威胁调查和响应功能](office-365-ti.md)) 使您能够对目前存在的已知威胁运行自动调查和补救措施。</span><span class="sxs-lookup"><span data-stu-id="6323e-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="6323e-105">阅读本文以了解空气的概述, 以及它如何帮助您的组织更有效地缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-105">Read this article to get an overview of AIR and how it can help your organization mitigate threats more effectively and efficiently.</span></span> <span data-ttu-id="6323e-106">Tolearn 有关何时可用空气的详细信息, 请参阅[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="6323e-106">Tolearn more about when AIR will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="6323e-107">警报</span><span class="sxs-lookup"><span data-stu-id="6323e-107">Alerts</span></span>

<span data-ttu-id="6323e-108">[警报](alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="6323e-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for Security Operations team workflows for incident response.</span></span> <span data-ttu-id="6323e-109">在确保没有威胁 unaddressed 的情况下, 确定用于调查的正确通知集的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="6323e-109">Prioritizing the right set of alerts for investigation while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="6323e-110">在手动对通知进行调查时, 安全操作团队必须在威胁的风险下对实体 (例如, 内容、设备和用户) 进行搜寻和关联。</span><span class="sxs-lookup"><span data-stu-id="6323e-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="6323e-111">此类任务和工作流非常耗时, 并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="6323e-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="6323e-112">通过空气、调查和响应自动化到关键安全和威胁管理警报, 可自动触发安全响应行动手册。</span><span class="sxs-lookup"><span data-stu-id="6323e-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="6323e-113">若要查看警报, 请在 "Office 365 Security & 合规中心" 中, 选择 "**通知** > " "**查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="6323e-113">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span>

![链接到调查的警报](media/air-alerts-page-details.png) 

<span data-ttu-id="6323e-115">选择一个警报以查看其详细信息, 然后在那里使用 "**查看调查**" 链接转到相应的[调查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="6323e-115">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span>

## <a name="security-playbooks"></a><span data-ttu-id="6323e-116">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="6323e-116">Security playbooks</span></span>

<span data-ttu-id="6323e-117">安全行动手册是在 Microsoft 威胁防护中处于自动化的中心的后端策略。</span><span class="sxs-lookup"><span data-stu-id="6323e-117">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="6323e-118">AIR 中提供的安全行动手册基于常见的实际安全方案。</span><span class="sxs-lookup"><span data-stu-id="6323e-118">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="6323e-119">当您的组织中触发一个警报时, 将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="6323e-119">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="6323e-120">通知触发后, 关联的行动手册将自动运行。</span><span class="sxs-lookup"><span data-stu-id="6323e-120">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="6323e-121">行动手册将运行调查, 查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等), 并根据其发现建议一组可供组织安全团队控制和缓解的操作威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-121">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.) and, based on its findings, recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="6323e-122">你将使用空中获取的安全行动手册旨在解决组织目前面临的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-122">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="6323e-123">它们基于安全操作和事件响应团队的输入, 包括帮助保护 Microsoft 资产的人员。</span><span class="sxs-lookup"><span data-stu-id="6323e-123">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="6323e-124">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="6323e-124">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="6323e-125">作为空气的一部分, 安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="6323e-125">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="6323e-126">**第1阶段 (4 月 2019)**: 行动手册包括安全管理员查看和批准的建议。</span><span class="sxs-lookup"><span data-stu-id="6323e-126">**Phase 1 (April 2019)**: Playbooks include recommendations that security administrators review and approve.</span></span> 

- <span data-ttu-id="6323e-127">**第2阶段 (6 月2019日)**: 安全管理员可以选择允许安全行动手册在没有管理交互的情况下自动采取行动。</span><span class="sxs-lookup"><span data-stu-id="6323e-127">**Phase 2 (June 2019)**: Security administrators will have the option to allow security playbooks to take action automatically, without administrative interaction.</span></span>

<span data-ttu-id="6323e-128">阶段1将包括以下行动手册:</span><span class="sxs-lookup"><span data-stu-id="6323e-128">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="6323e-129">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="6323e-129">User-reported phish message</span></span>
- <span data-ttu-id="6323e-130">URL 单击 "判定更改" 和 "ATP 安全链接阻止替代"</span><span class="sxs-lookup"><span data-stu-id="6323e-130">URL click verdict change and ATP Safe Links block override</span></span>
- <span data-ttu-id="6323e-131">恶意软件 ZAP</span><span class="sxs-lookup"><span data-stu-id="6323e-131">Malware ZAP</span></span>
- <span data-ttu-id="6323e-132">网络钓鱼 ZAP</span><span class="sxs-lookup"><span data-stu-id="6323e-132">Phish ZAP</span></span>
- <span data-ttu-id="6323e-133">手动调查 (使用资源管理器)</span><span class="sxs-lookup"><span data-stu-id="6323e-133">Manual investigations (using Explorer)</span></span>

<span data-ttu-id="6323e-134">计划为第2阶段提供几个更多的行动手册。</span><span class="sxs-lookup"><span data-stu-id="6323e-134">Several more playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="6323e-135">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="6323e-135">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="6323e-136">每个行动手册包括:</span><span class="sxs-lookup"><span data-stu-id="6323e-136">Each playbook includes:</span></span> 
- <span data-ttu-id="6323e-137">根调查</span><span class="sxs-lookup"><span data-stu-id="6323e-137">a root investigation,</span></span> 
- <span data-ttu-id="6323e-138">向下寻找其他潜在威胁的步骤, 以及</span><span class="sxs-lookup"><span data-stu-id="6323e-138">steps to hunt down other potential threats, and</span></span> 
- <span data-ttu-id="6323e-139">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="6323e-139">recommended threat remediation.</span></span>

<span data-ttu-id="6323e-140">每个高级别步骤都包含多个执行的子步骤, 以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="6323e-140">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-user-reported-phish-message"></a><span data-ttu-id="6323e-141">示例: 用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="6323e-141">Example: User-reported phish message</span></span>

<span data-ttu-id="6323e-142">当组织中的用户提交电子邮件并将其报告给 Microsoft 时, 将使用[outlook 或 outlook Web Access 的报告消息外接程序](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="6323e-142">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="6323e-143">这将触发基于系统的信息警报, 该警报将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="6323e-143">This triggers a system-based informational alert that automatically launches the investigation playbook.</span></span>

<span data-ttu-id="6323e-144">在根调查阶段, 会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="6323e-144">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="6323e-145">具体包括：</span><span class="sxs-lookup"><span data-stu-id="6323e-145">These include:</span></span>
- <span data-ttu-id="6323e-146">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="6323e-146">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="6323e-147">发件人数;</span><span class="sxs-lookup"><span data-stu-id="6323e-147">Who sent it;</span></span>
- <span data-ttu-id="6323e-148">发送电子邮件的位置 (发送基础结构);</span><span class="sxs-lookup"><span data-stu-id="6323e-148">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="6323e-149">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="6323e-149">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="6323e-150">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="6323e-150">An assessment from our analysts;</span></span>
- <span data-ttu-id="6323e-151">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="6323e-151">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="6323e-152">等等。</span><span class="sxs-lookup"><span data-stu-id="6323e-152">and more.</span></span>

<span data-ttu-id="6323e-153">根调查完成后, 行动手册提供了建议采取的操作列表。</span><span class="sxs-lookup"><span data-stu-id="6323e-153">After the root investigation is complete, the playbook provides a list of recommended actions to take.</span></span>
  
<span data-ttu-id="6323e-154">接下来, 执行几个搜寻步骤:</span><span class="sxs-lookup"><span data-stu-id="6323e-154">Next, several hunting steps are executed:</span></span>

- <span data-ttu-id="6323e-155">搜索其他电子邮件群集中的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6323e-155">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="6323e-156">该信号与其他平台 (如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)) 共享。</span><span class="sxs-lookup"><span data-stu-id="6323e-156">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="6323e-157">确定是否有用户在可疑电子邮件上点击了 "已通过"。</span><span class="sxs-lookup"><span data-stu-id="6323e-157">A determination is made on whether any users have clicked through on the suspicious email message.</span></span>
- <span data-ttu-id="6323e-158">跨 Office 365 [EOP](eop/exchange-online-protection-eop.md)和[ATP](office-365-atp.md)执行检查以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="6323e-158">A check is done across Office 365 [EOP](eop/exchange-online-protection-eop.md) and [ATP](office-365-atp.md) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="6323e-159">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="6323e-159">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="6323e-160">此检查在[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)中利用信号, 关联任何相关的事件或警报。</span><span class="sxs-lookup"><span data-stu-id="6323e-160">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related events or alerts.</span></span> 

<span data-ttu-id="6323e-161">在搜寻阶段, 会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-161">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span>  

<span data-ttu-id="6323e-162">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="6323e-162">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="6323e-163">在此阶段中, 将根据 theinvestigation 和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="6323e-163">During this phase, remediation steps are taken, based on theinvestigation and hunting phases.</span></span>  

## <a name="getting-started"></a><span data-ttu-id="6323e-164">入门</span><span class="sxs-lookup"><span data-stu-id="6323e-164">Getting started</span></span>

<span data-ttu-id="6323e-165">若要访问你的调查, 作为 Office 365 全局管理员或安全管理员, 请转到 office 365 安全 & 合规中心[https://protection.office.com](https://protection.office.com)() 并登录。</span><span class="sxs-lookup"><span data-stu-id="6323e-165">To access your investigations, as an Office 365 global administrator or security administrator, Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="6323e-166">然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="6323e-166">Then, do one of the following:</span></span>

- <span data-ttu-id="6323e-167">在左侧导航中, 转到 "**威胁管理** > **调查**"。</span><span class="sxs-lookup"><span data-stu-id="6323e-167">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="6323e-168">或者</span><span class="sxs-lookup"><span data-stu-id="6323e-168">or</span></span>

- <span data-ttu-id="6323e-169">访问威胁管理仪表板 (在安全 & 合规性中心中, 转到 "**威胁管理** > **仪表板**")。</span><span class="sxs-lookup"><span data-stu-id="6323e-169">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空中小部件](media/air-widgets.png)

<span data-ttu-id="6323e-171">您的空中小部件将显示在[安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="6323e-171">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="6323e-172">选择要开始的小部件。</span><span class="sxs-lookup"><span data-stu-id="6323e-172">Select a widget to get started.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="6323e-173">自动调查</span><span class="sxs-lookup"><span data-stu-id="6323e-173">Automated investigations</span></span>

<span data-ttu-id="6323e-174">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="6323e-174">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="6323e-176">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-176">You can:</span></span>
- <span data-ttu-id="6323e-177">直接导航到调查 (选择**调查 ID**)。</span><span class="sxs-lookup"><span data-stu-id="6323e-177">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="6323e-178">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="6323e-178">Apply filters.</span></span> <span data-ttu-id="6323e-179">从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="6323e-179">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="6323e-180">将数据导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6323e-180">Export the data to a CSV file.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="6323e-181">调查图形</span><span class="sxs-lookup"><span data-stu-id="6323e-181">Investigation graph</span></span>

<span data-ttu-id="6323e-182">当您打开特定调查时, 您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="6323e-182">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="6323e-183">此页面显示所有不同的实体: 电子邮件、用户 (及其活动) 以及自动调查为触发的警报一部分的设备。</span><span class="sxs-lookup"><span data-stu-id="6323e-183">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](media/air-investigationgraphpage.png)

<span data-ttu-id="6323e-185">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-185">You can:</span></span>
- <span data-ttu-id="6323e-186">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-186">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="6323e-187">查看调查计时的摘要。</span><span class="sxs-lookup"><span data-stu-id="6323e-187">View a summary of the investigation timings.</span></span>
- <span data-ttu-id="6323e-188">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6323e-188">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="6323e-189">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6323e-189">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="6323e-190">通知调查</span><span class="sxs-lookup"><span data-stu-id="6323e-190">Alert investigation</span></span>

<span data-ttu-id="6323e-191">在调查的 "**通知**" 选项卡上, 您可以查看与调查相关的所有警报。</span><span class="sxs-lookup"><span data-stu-id="6323e-191">On the **Alerts** tab for an investigation, you can see all of the alerts relevant to the investigation.</span></span> <span data-ttu-id="6323e-192">详细信息包括触发调查的警报以及与调查相关的其他警报 (如有风险的登录、成批下载等)。</span><span class="sxs-lookup"><span data-stu-id="6323e-192">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="6323e-193">在此页面中, 安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="6323e-193">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](media/air-investigationalertspage.png)

<span data-ttu-id="6323e-195">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-195">You can:</span></span>
- <span data-ttu-id="6323e-196">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-196">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="6323e-197">在列表中选择一个警报, 打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="6323e-197">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="6323e-198">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="6323e-198">Email investigation</span></span>

<span data-ttu-id="6323e-199">在调查的 "**电子邮件**" 选项卡上, 您可以看到标识为调查一部分的所有电子邮件群集。</span><span class="sxs-lookup"><span data-stu-id="6323e-199">On the **Email** tab for an investigation, you can see all the email clusters identified as part of the investigation.</span></span> 

<span data-ttu-id="6323e-200">由于组织中的用户发送和接收的电子邮件数量巨大, 因此</span><span class="sxs-lookup"><span data-stu-id="6323e-200">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="6323e-201">根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化;</span><span class="sxs-lookup"><span data-stu-id="6323e-201">clustering email messages based on similar attributes from a message header, body, URL and attachment;</span></span> 
- <span data-ttu-id="6323e-202">将恶意电子邮件与优质电子邮件分开;并</span><span class="sxs-lookup"><span data-stu-id="6323e-202">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="6323e-203">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="6323e-203">taking action on malicious email messages</span></span> 

<span data-ttu-id="6323e-204">可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="6323e-204">can take many hours.</span></span> <span data-ttu-id="6323e-205">现在, AIR 可以自动执行此过程, 从而节省了贵组织的安全团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="6323e-205">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="6323e-206">例如, 请考虑以下图像。</span><span class="sxs-lookup"><span data-stu-id="6323e-206">As an example, consider the following image.</span></span> <span data-ttu-id="6323e-207">三封电子邮件的第一个群集被认为是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="6323e-207">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="6323e-208">找到具有相同 IP 和主题的类似邮件的另一个群集, 并被视为恶意邮件, 因为在初始检测过程中, 其中一些邮件被标识为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="6323e-208">Another cluster of similar messages with the same IP and subject was found and is considered to be malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中电子邮件调查页面](media/air-investigationemailpage.png)

<span data-ttu-id="6323e-210">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-210">You can:</span></span>
- <span data-ttu-id="6323e-211">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-211">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="6323e-212">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="6323e-212">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>

![使用浮出控件详细信息的航空调查电子邮件](media/air-investigationemailpageflyoutdetails.png)

### <a name="user-investigation"></a><span data-ttu-id="6323e-214">用户调查</span><span class="sxs-lookup"><span data-stu-id="6323e-214">User investigation</span></span>

<span data-ttu-id="6323e-215">在 "**用户**" 选项卡上, 您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="6323e-215">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> 

<span data-ttu-id="6323e-216">例如, 在下图中, 空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="6323e-216">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="6323e-217">可通过此选项卡中的详细视图查看调查的其他详细信息 (证据)。</span><span class="sxs-lookup"><span data-stu-id="6323e-217">Additional details (evidence) of the investigation are available through detailed views within this tab.</span></span>

![空中调查用户页](media/air-investigationuserspage.png)

<span data-ttu-id="6323e-219">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-219">You can:</span></span>
- <span data-ttu-id="6323e-220">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-220">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="6323e-221">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="6323e-221">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="6323e-222">机器调查</span><span class="sxs-lookup"><span data-stu-id="6323e-222">Machine investigation</span></span>

<span data-ttu-id="6323e-223">在 "**计算机**" 选项卡上, 您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="6323e-223">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空中调查计算机页面](media/air-investigationmachinepage.png)

<span data-ttu-id="6323e-225">作为调查的一部分, 空中将电子邮件威胁与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="6323e-225">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="6323e-226">例如, 调查会将文件哈希传递到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)以进行调查。</span><span class="sxs-lookup"><span data-stu-id="6323e-226">For example, an investigation passes a file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="6323e-227">这样, 就可以为您的用户自动调查相关的计算机, 并帮助确保在云中和设备之间解决威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-227">This allows for automated investigation of relevant machines for your users and helps to ensure that threats are addressed both in the cloud and across your devices.</span></span> 

<span data-ttu-id="6323e-228">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-228">You can:</span></span>
- <span data-ttu-id="6323e-229">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-229">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="6323e-230">选择一台计算机以打开指向相关[Windows Defender ATP 调查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)的视图。</span><span class="sxs-lookup"><span data-stu-id="6323e-230">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection).</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="6323e-231">实体调查</span><span class="sxs-lookup"><span data-stu-id="6323e-231">Entity investigation</span></span>

<span data-ttu-id="6323e-232">在 "**实体**" 选项卡上, 您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="6323e-232">On the **Entities** tab, you can see all the machines identified as part of the investigation.</span></span> 

<span data-ttu-id="6323e-233">在这里, 你可以看到调查的实体。</span><span class="sxs-lookup"><span data-stu-id="6323e-233">Here, you can see the investigated entities.</span></span> <span data-ttu-id="6323e-234">您可以查看实体类型的详细信息, 例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="6323e-234">You can see details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="6323e-235">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="6323e-235">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

!["航空调查实体" 页](media/air-investigationentitiespage.png)

<span data-ttu-id="6323e-237">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-237">You can:</span></span>
- <span data-ttu-id="6323e-238">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-238">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="6323e-239">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="6323e-239">Select an entity to open a fly-out page that shows the related entity detail.</span></span>

![空中调查实体详细信息](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="6323e-241">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="6323e-241">Playbook log</span></span>

<span data-ttu-id="6323e-242">在 "**日志**" 选项卡上, 您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="6323e-242">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="6323e-243">该日志将捕获由 Office 365 威胁智能功能作为空气的一部分完成的所有操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="6323e-243">The log captures a complete inventory of all actions completed by Office 365 Threat Intelligence capabilities as part of AIR.</span></span> <span data-ttu-id="6323e-244">它提供了所执行的所有步骤的清晰视图, 包括操作本身、说明以及实际开始时间到完成的持续时间。</span><span class="sxs-lookup"><span data-stu-id="6323e-244">It provides a clear view of all the steps taken, including the Action itself, a description and the duration of the actual from start to finish.</span></span> 

![航空调查日志页](media/air-investigationlogpage.png)

<span data-ttu-id="6323e-246">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-246">You can:</span></span>
- <span data-ttu-id="6323e-247">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-247">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="6323e-248">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6323e-248">Export the results to a CSV file.</span></span>
- <span data-ttu-id="6323e-249">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="6323e-249">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="6323e-250">建议的操作</span><span class="sxs-lookup"><span data-stu-id="6323e-250">Recommended actions</span></span>

<span data-ttu-id="6323e-251">在 "**操作**" 选项卡上, 您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="6323e-251">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="6323e-252">操作会捕获 Microsoft 建议在调查结束时执行的所有步骤的完整列表。</span><span class="sxs-lookup"><span data-stu-id="6323e-252">Actions capture a complete list of all the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="6323e-253">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="6323e-253">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="6323e-254">单击 "**批准**" 将允许开始修正。</span><span class="sxs-lookup"><span data-stu-id="6323e-254">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="6323e-255">(可能需要适当的权限。</span><span class="sxs-lookup"><span data-stu-id="6323e-255">(Appropriate permissions might be required.</span></span> <span data-ttu-id="6323e-256">例如, 安全读者可以查看操作但不能批准。</span><span class="sxs-lookup"><span data-stu-id="6323e-256">For example, a Security Reader can view actions but not approve them.)</span></span>  

![航空调查操作页](media/air-investigationactionspage.png)

<span data-ttu-id="6323e-258">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6323e-258">You can:</span></span>
- <span data-ttu-id="6323e-259">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="6323e-259">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="6323e-260">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="6323e-260">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="6323e-261">批准建议的操作。</span><span class="sxs-lookup"><span data-stu-id="6323e-261">Approve recommended actions.</span></span> <span data-ttu-id="6323e-262">(这些都将立即以注释形式启动。)</span><span class="sxs-lookup"><span data-stu-id="6323e-262">(These are started immediately with comments.)</span></span>
- <span data-ttu-id="6323e-263">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6323e-263">Export the results to a CSV file.</span></span>
- <span data-ttu-id="6323e-264">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="6323e-264">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="6323e-265">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="6323e-265">How to get AIR</span></span>

<span data-ttu-id="6323e-266">目前, AIR 处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="6323e-266">Currently, AIR is in preview.</span></span> <span data-ttu-id="6323e-267">发布后, 空气将包含在以下订阅中:</span><span class="sxs-lookup"><span data-stu-id="6323e-267">When released, AIR will be included in the following subscriptions:</span></span>

- <span data-ttu-id="6323e-268">Microsoft 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="6323e-268">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="6323e-269">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="6323e-269">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="6323e-270">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="6323e-270">Microsoft Threat Protection</span></span>
- <span data-ttu-id="6323e-271">Office 365 高级威胁防护计划2</span><span class="sxs-lookup"><span data-stu-id="6323e-271">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="6323e-272">若要了解有关功能可用性的详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="6323e-272">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
