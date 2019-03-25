---
title: 使用 Office 365 的自动化调查和响应 (空中)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 了解 Office 365 高级威胁防护中的自动化调查和响应功能。
ms.openlocfilehash: 9c01121ed6389f4a9014fe1ee1298b0e840f06ab
ms.sourcegitcommit: 1706b618c9ec63ed05aebb5f84a77b5bfb50734a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "30792506"
---
# <a name="automated-investigation-and-response-air-with-office-365"></a><span data-ttu-id="32d94-103">使用 Office 365 的自动化调查和响应 (空中)</span><span class="sxs-lookup"><span data-stu-id="32d94-103">Automated Investigation and Response (AIR) with Office 365</span></span>

<span data-ttu-id="32d94-104">自动化调查和响应 (空中) (即将推出[Office 365 威胁调查和响应功能](office-365-ti.md)) 使您能够对目前存在的已知威胁运行自动调查和补救措施。</span><span class="sxs-lookup"><span data-stu-id="32d94-104">Automated Investigation and Response (AIR) (coming soon to [Office 365 Threat investigation and response capabilities](office-365-ti.md)) enables you to run automated investigation and remediation to well-known threats that exist today.</span></span> <span data-ttu-id="32d94-105">阅读本文以了解空气的概述, 以及它如何帮助您的组织和安全操作团队更有效地缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-105">Read this article to get an overview of AIR and how it can help your organization and security operations teams mitigate threats more effectively and efficiently.</span></span> 

<span data-ttu-id="32d94-106">若要了解有关何时可使用空中功能的详细信息, 请参阅[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="32d94-106">To learn more about when  AIR features will be available, see the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

## <a name="alerts"></a><span data-ttu-id="32d94-107">警报</span><span class="sxs-lookup"><span data-stu-id="32d94-107">Alerts</span></span>

<span data-ttu-id="32d94-108">[警报](alert-policies.md#viewing-alerts)表示用于事件响应的安全操作团队工作流的触发器。</span><span class="sxs-lookup"><span data-stu-id="32d94-108">[Alerts](alert-policies.md#viewing-alerts) represent triggers for security operations team workflows for incident response.</span></span> <span data-ttu-id="32d94-109">确定要调查的正确通知集的优先级, 同时确保没有威胁是 unaddressed 的挑战。</span><span class="sxs-lookup"><span data-stu-id="32d94-109">Prioritizing the right set of alerts for investigation, while making sure no threats are unaddressed is challenging.</span></span> <span data-ttu-id="32d94-110">在手动对通知进行调查时, 安全操作团队必须在威胁的风险下对实体 (例如, 内容、设备和用户) 进行搜寻和关联。</span><span class="sxs-lookup"><span data-stu-id="32d94-110">When investigations into alerts are performed manually, Security Operations teams must hunt and correlate entities (e.g. content, devices and users) at risk from threats.</span></span> <span data-ttu-id="32d94-111">此类任务和工作流非常耗时, 并涉及多个工具和系统。</span><span class="sxs-lookup"><span data-stu-id="32d94-111">Such tasks and workflows are very time consuming and involve multiple tools and systems.</span></span> <span data-ttu-id="32d94-112">通过空气、调查和响应自动化到关键安全和威胁管理警报, 可自动触发安全响应行动手册。</span><span class="sxs-lookup"><span data-stu-id="32d94-112">With AIR, investigation and response are automated into key security and threat management alerts that trigger your security response playbooks automatically.</span></span> 

<span data-ttu-id="32d94-113">在2019年4月的最初发行版中, 通过以下单个事件通知策略生成的警报将自动调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-113">In the initial release of AIR in April 2019, alerts generated from following single events alert policies will be auto-investigated.</span></span> 

1. <span data-ttu-id="32d94-114">检测到潜在的恶意 URL 单击</span><span class="sxs-lookup"><span data-stu-id="32d94-114">A potentially malicious URL click was detected</span></span>
2. <span data-ttu-id="32d94-115">用户报告为网络钓鱼的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="32d94-115">Email reported by user as phish\*</span></span>
3. <span data-ttu-id="32d94-116">包含在传递后删除的恶意软件的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="32d94-116">Email messages containing malware removed after delivery\*</span></span>
4. <span data-ttu-id="32d94-117">包含在传递后删除的网络钓鱼 url 的电子邮件 \*</span><span class="sxs-lookup"><span data-stu-id="32d94-117">Email messages containing phish URLs removed after delivery\*</span></span>

<span data-ttu-id="32d94-118">\***注意**: 已在安全 & 合规性中心内为这些警报分配了 "信息性" 严重性, 并关闭了电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="32d94-118">\***Note**: These alerts have been assigned an "Informational" severity in the respective alert policies within the Security & Compliance Center with email notifications turned off.</span></span> <span data-ttu-id="32d94-119">可以通过警报策略配置启用这些策略。</span><span class="sxs-lookup"><span data-stu-id="32d94-119">These can be turned on through the Alert policy configuration.</span></span>

<span data-ttu-id="32d94-120">若要查看警报, 请在 "Office 365 Security & 合规中心" 中, 选择 "**通知** > " "**查看警报**"。</span><span class="sxs-lookup"><span data-stu-id="32d94-120">To view alerts, in the Office 365 Security & Compliance Center, choose **Alerts** > **View alerts**.</span></span> <span data-ttu-id="32d94-121">选择一个警报以查看其详细信息, 然后在那里使用 "**查看调查**" 链接转到相应的[调查](#investigation-graph)。</span><span class="sxs-lookup"><span data-stu-id="32d94-121">Select an alert to view its details, and from there, use the **View investigation** link to go to the corresponding [investigation](#investigation-graph).</span></span> <span data-ttu-id="32d94-122">请注意, 默认情况下通知视图中隐藏了信息警报。</span><span class="sxs-lookup"><span data-stu-id="32d94-122">Note that informational alerts are hidden in the alert view by default.</span></span> <span data-ttu-id="32d94-123">若要查看它们, 您需要更改警报筛选以包含信息警报。</span><span class="sxs-lookup"><span data-stu-id="32d94-123">To see them, you need to change the alert filtering to include informational alerts.</span></span>

<span data-ttu-id="32d94-124">如果您的组织通过警报管理系统、服务管理系统或安全信息和事件管理 (SIEM) 系统管理安全警报, 则可以通过电子邮件通知或通过[电子邮件通知将 Office 365 警报发送到该系统。Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="32d94-124">If your organization manages your security alerts through a alert management system, service management system, or Security Information and Event Management (SIEM) system, you can send Office 365 alerts to that system via either email notification or via the [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> <span data-ttu-id="32d94-125">通过电子邮件或 API 的调查通知通知将包含访问 Office 365 Security & 合规中心中的警报的链接, 从而使分配的安全管理员能够快速导航到调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-125">The investigation alert notifications via email or API will include links to access the alerts in the Office 365 Security & Compliance Center, enabling the assigned security administrator to navigate quickly to the investigation.</span></span>

![链接到调查的警报](media/air-alerts-page-details.png) 


## <a name="security-playbooks"></a><span data-ttu-id="32d94-127">安全行动手册</span><span class="sxs-lookup"><span data-stu-id="32d94-127">Security playbooks</span></span>

<span data-ttu-id="32d94-128">安全行动手册是在 Microsoft 威胁防护中处于自动化的中心的后端策略。</span><span class="sxs-lookup"><span data-stu-id="32d94-128">Security playbooks are back-end policies that are at the heart of automation in Microsoft Threat Protection.</span></span> <span data-ttu-id="32d94-129">AIR 中提供的安全行动手册基于常见的实际安全方案。</span><span class="sxs-lookup"><span data-stu-id="32d94-129">The security playbooks provided in AIR are based on common real-world security scenarios.</span></span> <span data-ttu-id="32d94-130">当您的组织中触发一个警报时, 将自动启动安全行动手册。</span><span class="sxs-lookup"><span data-stu-id="32d94-130">A security playbook is launched automatically when an alert is triggered within your organization.</span></span> <span data-ttu-id="32d94-131">通知触发后, 关联的行动手册将自动运行。</span><span class="sxs-lookup"><span data-stu-id="32d94-131">Once the alert triggers, the associated playbook is run automatically.</span></span> <span data-ttu-id="32d94-132">行动手册将运行调查, 查看所有关联的元数据 (包括电子邮件、用户、主题、发件人等)。</span><span class="sxs-lookup"><span data-stu-id="32d94-132">The playbook runs an investigation, looking at all the associated metadata (including email messages, users, subjects, senders, etc.).</span></span> <span data-ttu-id="32d94-133">根据行动手册的发现, AIR 推荐了您的组织的安全团队可采取的一组操作来控制和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-133">Based on the playbook's findings, AIR recommends a set of actions that your organization's security team can take to control and mitigate the threat.</span></span> 

<span data-ttu-id="32d94-134">你将使用空中获取的安全行动手册旨在解决组织目前面临的最常见威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-134">The security playbooks you'll get with AIR are designed to tackle the most frequent threats that organizations face today.</span></span> <span data-ttu-id="32d94-135">它们基于安全操作和事件响应团队的输入, 包括帮助保护 Microsoft 和客户资产的人员。</span><span class="sxs-lookup"><span data-stu-id="32d94-135">They're based on input from Security Operations and Incident Response teams, including those who help defend Microsoft and our customers assets.</span></span>

### <a name="security-playbooks-are-rolling-out-in-phases"></a><span data-ttu-id="32d94-136">安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="32d94-136">Security playbooks are rolling out in phases</span></span>

<span data-ttu-id="32d94-137">作为空气的一部分, 安全行动手册在几个阶段推出</span><span class="sxs-lookup"><span data-stu-id="32d94-137">As part of AIR, security playbooks are rolling out in phases</span></span>

- <span data-ttu-id="32d94-138">**第1阶段 (4 月 2019)**: 行动手册包含安全管理员查看和批准的操作建议。</span><span class="sxs-lookup"><span data-stu-id="32d94-138">**Phase 1 (April 2019)**: Playbooks include recommendations for actions that security administrators review and approve.</span></span> 

- <span data-ttu-id="32d94-139">**阶段 2 (6 月2019日)**: 行动手册改进和安全管理员可以选择将安全行动手册配置为在没有管理交互的情况下自动执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-139">**Phase 2 (post-June 2019)**: Playbook improvements, plus security administrators will have the option to configure security playbooks to take some actions automatically without administrative interaction.</span></span>

<span data-ttu-id="32d94-140">阶段1将包括以下行动手册:</span><span class="sxs-lookup"><span data-stu-id="32d94-140">Phase 1 will include the following playbooks:</span></span>
- <span data-ttu-id="32d94-141">用户报告的网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="32d94-141">User-reported phish message</span></span>
- <span data-ttu-id="32d94-142">URL 单击 "判定更改"</span><span class="sxs-lookup"><span data-stu-id="32d94-142">URL click verdict change</span></span> 
- <span data-ttu-id="32d94-143">恶意软件检测到送达后 (恶意软件 ZAP)</span><span class="sxs-lookup"><span data-stu-id="32d94-143">Malware detected post-delivery (Malware ZAP)</span></span>
- <span data-ttu-id="32d94-144">网络钓鱼检测到传递后的 zap (网络钓鱼 zap)</span><span class="sxs-lookup"><span data-stu-id="32d94-144">Phish detected post-delivery ZAP (Phish ZAP)</span></span>
- <span data-ttu-id="32d94-145">手动电子邮件调查 (使用威胁资源管理器)</span><span class="sxs-lookup"><span data-stu-id="32d94-145">Manual e-mail investigations (using Threat Explorer)</span></span>

<span data-ttu-id="32d94-146">规划第2阶段的其他几项行动手册。</span><span class="sxs-lookup"><span data-stu-id="32d94-146">Several other playbooks are planned for Phase 2.</span></span>

### <a name="playbooks-include-investigation-and-recommendations"></a><span data-ttu-id="32d94-147">行动手册包括调查和建议</span><span class="sxs-lookup"><span data-stu-id="32d94-147">Playbooks include investigation and recommendations</span></span>

<span data-ttu-id="32d94-148">每个行动手册包括:</span><span class="sxs-lookup"><span data-stu-id="32d94-148">Each playbook includes:</span></span> 
- <span data-ttu-id="32d94-149">根调查</span><span class="sxs-lookup"><span data-stu-id="32d94-149">a root investigation,</span></span> 
- <span data-ttu-id="32d94-150">确定并关联其他潜在威胁所需的步骤, 以及</span><span class="sxs-lookup"><span data-stu-id="32d94-150">steps taken to identify and correlate other potential threats, and</span></span> 
- <span data-ttu-id="32d94-151">建议的威胁补救措施。</span><span class="sxs-lookup"><span data-stu-id="32d94-151">recommended threat remediation actions.</span></span>

<span data-ttu-id="32d94-152">每个高级别步骤都包含多个执行的子步骤, 以提供对威胁的深入、详细和详尽的响应。</span><span class="sxs-lookup"><span data-stu-id="32d94-152">Each high-level step includes many sub-steps that are executed to provide a deep, detailed, and exhaustive response to threats.</span></span>

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a><span data-ttu-id="32d94-153">示例: 用户报告的网络钓鱼邮件启动调查行动手册</span><span class="sxs-lookup"><span data-stu-id="32d94-153">Example: A user-reported phish message launches an investigation playbook</span></span>

<span data-ttu-id="32d94-154">当组织中的用户提交电子邮件并使用[outlook 或 outlook Web Access 的报告邮件加载项](enable-the-report-message-add-in.md)将其报告给 Microsoft 时, 该报告也会发送到您的系统, 并在用户报告的视图中显示在资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="32d94-154">When a user in your organization submits an email message and reports it to Microsoft by using the [Report Message add-in for Outlook or Outlook Web Access](enable-the-report-message-add-in.md), the report is also sent to your system and is visible in Explorer in the User-reported view.</span></span> <span data-ttu-id="32d94-155">此用户报告的消息现在会触发基于系统的信息警报, 这将自动启动调查行动手册。</span><span class="sxs-lookup"><span data-stu-id="32d94-155">This user-reported message now triggers a system-based informational alert, which automatically launches the investigation playbook.</span></span>

<span data-ttu-id="32d94-156">在根调查阶段, 会评估电子邮件的各个方面。</span><span class="sxs-lookup"><span data-stu-id="32d94-156">During the root investigation phase, various aspects of the email are assessed.</span></span> <span data-ttu-id="32d94-157">具体包括：</span><span class="sxs-lookup"><span data-stu-id="32d94-157">These include:</span></span>
- <span data-ttu-id="32d94-158">确定它可能属于哪种类型的威胁;</span><span class="sxs-lookup"><span data-stu-id="32d94-158">A determination about what type of threat it might be;</span></span>
- <span data-ttu-id="32d94-159">发件人数;</span><span class="sxs-lookup"><span data-stu-id="32d94-159">Who sent it;</span></span>
- <span data-ttu-id="32d94-160">发送电子邮件的位置 (发送基础结构);</span><span class="sxs-lookup"><span data-stu-id="32d94-160">Where the email was sent from (sending infrastructure);</span></span>
- <span data-ttu-id="32d94-161">是否已传递或阻止电子邮件的其他实例;</span><span class="sxs-lookup"><span data-stu-id="32d94-161">Whether other instances of the email were delivered or blocked;</span></span>
- <span data-ttu-id="32d94-162">我们分析家中的一种评估;</span><span class="sxs-lookup"><span data-stu-id="32d94-162">An assessment from our analysts;</span></span>
- <span data-ttu-id="32d94-163">电子邮件是否与任何已知的市场活动相关联;</span><span class="sxs-lookup"><span data-stu-id="32d94-163">Whether the email is associated with any known campaigns;</span></span>
- <span data-ttu-id="32d94-164">等等。</span><span class="sxs-lookup"><span data-stu-id="32d94-164">and more.</span></span>

<span data-ttu-id="32d94-165">根调查完成后, 行动手册提供了要对其关联的原始电子邮件和实体执行的建议操作的列表。</span><span class="sxs-lookup"><span data-stu-id="32d94-165">After the root investigation is complete, the playbook provides a list of recommended actions to take on the original email and entities associated with it.</span></span>
  
<span data-ttu-id="32d94-166">接下来, 执行以下几个威胁调查和搜寻步骤:</span><span class="sxs-lookup"><span data-stu-id="32d94-166">Next, several threat investigation and hunting steps are executed:</span></span>

- <span data-ttu-id="32d94-167">搜索其他电子邮件群集中的类似电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-167">Similar email messages in other email clusters are searched.</span></span>
- <span data-ttu-id="32d94-168">该信号与其他平台 (如[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)) 共享。</span><span class="sxs-lookup"><span data-stu-id="32d94-168">The signal is shared with other platforms, such as [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).</span></span>
- <span data-ttu-id="32d94-169">确定是否有用户通过可疑电子邮件中的任何恶意链接单击过。</span><span class="sxs-lookup"><span data-stu-id="32d94-169">A determination is made on whether any users have clicked through any malicious links in suspicious email messages.</span></span>
- <span data-ttu-id="32d94-170">跨 office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) 和 Office 365 高级威胁防护 ([ATP](office-365-atp.md)) 执行检查以查看用户是否报告了任何其他类似的消息。</span><span class="sxs-lookup"><span data-stu-id="32d94-170">A check is done across Office 365 Exchange Online Protection ([EOP](eop/exchange-online-protection-eop.md)) and Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) to see if there are any other similar messages reported by users.</span></span>
- <span data-ttu-id="32d94-171">将执行检查以查看是否已泄露用户。</span><span class="sxs-lookup"><span data-stu-id="32d94-171">A check is done to see if a user has been compromised.</span></span> <span data-ttu-id="32d94-172">此检查在[Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)中利用信号, 关联任何相关的用户活动异常。</span><span class="sxs-lookup"><span data-stu-id="32d94-172">This check leverages signals across [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlating any related user activity anomalies.</span></span> 

<span data-ttu-id="32d94-173">在搜寻阶段, 会为各种搜寻步骤分配风险和威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-173">During the hunting phase, risks and threats are assigned to various hunting steps.</span></span> 

<span data-ttu-id="32d94-174">修正是行动手册的最后阶段。</span><span class="sxs-lookup"><span data-stu-id="32d94-174">Remediation is the final phase of the playbook.</span></span> <span data-ttu-id="32d94-175">在此阶段中, 将根据调查和搜寻阶段采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="32d94-175">During this phase, remediation steps are taken, based on the investigation and hunting phases.</span></span> 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a><span data-ttu-id="32d94-176">示例: 安全管理员触发来自威胁资源管理器的调查</span><span class="sxs-lookup"><span data-stu-id="32d94-176">Example: A security administrator triggers an investigation from Threat Explorer</span></span>

<span data-ttu-id="32d94-177">除了由警报触发的自动调查之外, 组织的安全操作团队可以通过[威胁资源管理器](use-explorer-in-security-and-compliance.md)中的视图触发自动调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-177">In addition to automatic investigations that are triggered by an alert, your organization's security operations team can trigger an automatic investigation from a view in [Threat Explorer](use-explorer-in-security-and-compliance.md).</span></span>

<span data-ttu-id="32d94-178">例如, 假设您正在查看资源管理器中有关用户报告的消息的数据。</span><span class="sxs-lookup"><span data-stu-id="32d94-178">For example, suppose that you are viewing data in Explorer about user-reported messages.</span></span> <span data-ttu-id="32d94-179">您可以在结果列表中选择一个项目, 然后单击 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="32d94-179">You can select an item in the list of results, and then click **Investigate**.</span></span>

![使用调查按钮的资源管理器中的用户报告的消息](media/Explorer-UserReported-Investigate.png)

<span data-ttu-id="32d94-181">作为另一个示例, 假设您要查看检测为包含恶意软件的电子邮件的数据, 并且有几封电子邮件被检测为包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="32d94-181">As another example, suppose you are viewing data about email messages detected as containing malware, and there are several email messages detected as containing malware.</span></span> <span data-ttu-id="32d94-182">您可以选择 "**电子邮件**" 选项卡, 选择一个或多个电子邮件, 然后在 "**操作**" 菜单上选择 "**调查**"。</span><span class="sxs-lookup"><span data-stu-id="32d94-182">You can select the **Email** tab, select one or more email messages, and then, on the **Actions** menu, select **Investigate**.</span></span> 

![在资源管理器中开始调查恶意软件](media/Explorer-Malware-Email-ActionsInvestigate.png)

<span data-ttu-id="32d94-184">与由警报触发的行动手册类似, 通过资源管理器中的视图触发的自动调查包括根调查、标识和关联威胁的步骤以及缓解这些威胁的建议操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-184">Similar to playbooks triggered by an alert, automatic investigations that are triggered from a view in Explorer include a root investigation, steps to identify and correlate threats, and recommended actions to mitigate those threats.</span></span>

## <a name="get-started"></a><span data-ttu-id="32d94-185">入门</span><span class="sxs-lookup"><span data-stu-id="32d94-185">Get started</span></span>

<span data-ttu-id="32d94-186">若要访问您的调查, 作为 Office 365 全局管理员、安全管理员或安全读者, 请转到 office 365 安全 & 合规中心 ([https://protection.office.com](https://protection.office.com)) 并登录。</span><span class="sxs-lookup"><span data-stu-id="32d94-186">To access your investigations, as an Office 365 global administrator, security administrator, or security reader, go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span> <span data-ttu-id="32d94-187">然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="32d94-187">Then, do one of the following:</span></span>

- <span data-ttu-id="32d94-188">在左侧导航中, 转到 "**通知** > " "**查看通知**", 打开与调查相关的警报之一, 然后单击 "通知" 弹出窗口底部的 "**查看调查**" 链接。</span><span class="sxs-lookup"><span data-stu-id="32d94-188">In the left navigation, go to **Alerts** > **View alerts**, open one of the investigation related alerts, then click the **View investigation** link at the bottom of the alert flyout.</span></span> 

    <span data-ttu-id="32d94-189">或</span><span class="sxs-lookup"><span data-stu-id="32d94-189">or</span></span>

- <span data-ttu-id="32d94-190">在左侧导航中, 转到 "**威胁管理** > **调查**"。</span><span class="sxs-lookup"><span data-stu-id="32d94-190">In the left navigation, go to **Threat management** > **Investigations**.</span></span>

    <span data-ttu-id="32d94-191">或</span><span class="sxs-lookup"><span data-stu-id="32d94-191">or</span></span>

- <span data-ttu-id="32d94-192">访问威胁管理仪表板 (在安全 & 合规性中心中, 转到 "**威胁管理** > **仪表板**")。</span><span class="sxs-lookup"><span data-stu-id="32d94-192">Visit the Threat management dashboard (In the Security & Compliance Center, go to **Threat management** > **Dashboard**).</span></span>

![空中小部件](media/air-widgets.png)

<span data-ttu-id="32d94-194">您的空中小部件将显示在[安全仪表板](security-dashboard.md)的顶部。</span><span class="sxs-lookup"><span data-stu-id="32d94-194">Your AIR widgets will appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="32d94-195">选择要开始的小部件。</span><span class="sxs-lookup"><span data-stu-id="32d94-195">Select a widget to get started.</span></span>

<span data-ttu-id="32d94-196">您也可以直接从相关警报访问调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-196">You may also access an investigation directly from the related Alerts.</span></span>

### <a name="automated-investigations"></a><span data-ttu-id="32d94-197">自动调查</span><span class="sxs-lookup"><span data-stu-id="32d94-197">Automated investigations</span></span>

<span data-ttu-id="32d94-198">"自动调查" 页面显示您的组织的调查及其当前状态。</span><span class="sxs-lookup"><span data-stu-id="32d94-198">The automated investigations page shows your organization's investigations and their current states.</span></span>

![空气的主要调查页面](media/air-maininvestigationpage.png) 
  
<span data-ttu-id="32d94-200">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-200">You can:</span></span>
- <span data-ttu-id="32d94-201">直接导航到调查 (选择**调查 ID**)。</span><span class="sxs-lookup"><span data-stu-id="32d94-201">Navigate directly to an investigation (select an **Investigation ID**).</span></span>
- <span data-ttu-id="32d94-202">应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="32d94-202">Apply filters.</span></span> <span data-ttu-id="32d94-203">从**调查类型**、**时间范围**、**状态**或这些情况的组合中进行选择。</span><span class="sxs-lookup"><span data-stu-id="32d94-203">Choose from **Investigation Type**, **Time range**, **Status**, or a combination of these.</span></span>
- <span data-ttu-id="32d94-204">将数据导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="32d94-204">Export the data to a CSV file.</span></span>

<span data-ttu-id="32d94-205">调查状态指示分析和操作的进度。</span><span class="sxs-lookup"><span data-stu-id="32d94-205">The investigation status indicates the progress of the analysis and actions.</span></span> <span data-ttu-id="32d94-206">在调查运行时, 状态将发生更改, 以指示是否找到了威胁, 并指示是否已批准操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-206">As the investigation runs, the status will change to indicate whether threats were found, as well as indicate whether actions have been approved.</span></span> 
- <span data-ttu-id="32d94-207">**启动**: 调查已排入队列, 以便尽快开始</span><span class="sxs-lookup"><span data-stu-id="32d94-207">**Starting**: The investigation is queued to begin soon</span></span>
- <span data-ttu-id="32d94-208">**正在运行**: 调查已开始, 正在执行其 "分析</span><span class="sxs-lookup"><span data-stu-id="32d94-208">**Running**: The investigation has started and is conducting its' analysis</span></span>
- <span data-ttu-id="32d94-209">**未找到威胁**: 调查已完成其分析, 未发现任何威胁</span><span class="sxs-lookup"><span data-stu-id="32d94-209">**No Threats Found**: The investigation has completed its' analysis and no threats were found</span></span>
- <span data-ttu-id="32d94-210">已**由系统终止**: 调查未关闭并在7天后过期</span><span class="sxs-lookup"><span data-stu-id="32d94-210">**Terminated By System**: The investigation was not closed and expired after 7 days</span></span>
- <span data-ttu-id="32d94-211">**待处理操作**: 调查发现存在建议操作的威胁</span><span class="sxs-lookup"><span data-stu-id="32d94-211">**Pending Action**: The investigation found threats with actions recommended</span></span>
- <span data-ttu-id="32d94-212">**发现的威胁**: 调查发现威胁, 但威胁没有在空中可用的操作</span><span class="sxs-lookup"><span data-stu-id="32d94-212">**Threats Found**: The investigation found threats, but the threats do not have actions available within AIR</span></span>
- <span data-ttu-id="32d94-213">已**修正**: investgation 已完成且已完全修正 (已批准所有操作)</span><span class="sxs-lookup"><span data-stu-id="32d94-213">**Remediated**: The investgation finished and was fully remediated (all actions were approved)</span></span>
- <span data-ttu-id="32d94-214">**部分修正**: 调查已完成, 某些建议的操作已获得批准</span><span class="sxs-lookup"><span data-stu-id="32d94-214">**Partially Remediated**: The investigation finished and some of the recommended actions were approved</span></span>
- <span data-ttu-id="32d94-215">已**被用户终止**: 管理员终止了调查</span><span class="sxs-lookup"><span data-stu-id="32d94-215">**Terminated By User**: An admin terminated the investigation</span></span>
- <span data-ttu-id="32d94-216">**失败**: 调查过程中出现错误, 使其无法达到威胁的结论</span><span class="sxs-lookup"><span data-stu-id="32d94-216">**Failed**: An error occurred during the investigation that prevented it from reaching a conclusion on threats</span></span>
- <span data-ttu-id="32d94-217">**按限制排队**: 调查因系统处理限制而正在等待分析 (以保护服务性能)</span><span class="sxs-lookup"><span data-stu-id="32d94-217">**Queued By Throttling**: The investigation is waiting for analysis due to system processing limitations (to protect service performance)</span></span>
- <span data-ttu-id="32d94-218">**由限制终止**: 由于调查卷和系统处理限制, 无法在足够的时间内完成调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-218">**Terminated By Throttling**: The investigation could not be completed in sufficient time due to investigation volume and system processing limitations.</span></span> <span data-ttu-id="32d94-219">您可以通过在资源管理器中选择电子邮件并选择调查操作来重新触发调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-219">You can re-trigger the investigation by selecting the email in Explorer and selecting the Investigate action.</span></span>

### <a name="investigation-graph"></a><span data-ttu-id="32d94-220">调查图形</span><span class="sxs-lookup"><span data-stu-id="32d94-220">Investigation graph</span></span>

<span data-ttu-id="32d94-221">当您打开特定调查时, 您将看到 "调查图形" 页。</span><span class="sxs-lookup"><span data-stu-id="32d94-221">When you open a specific investigation, you see the investigation graph page.</span></span> <span data-ttu-id="32d94-222">此页面显示所有不同的实体: 电子邮件、用户 (及其活动) 以及自动调查为触发的警报一部分的设备。</span><span class="sxs-lookup"><span data-stu-id="32d94-222">This page shows all the different entities: email messages, users (and their activities), and devices that were automatically investigated as part of the alert that was triggered.</span></span>

![空中调查图形页面](media/air-investigationgraphpage.png)

<span data-ttu-id="32d94-224">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-224">You can:</span></span>
- <span data-ttu-id="32d94-225">获取当前调查的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-225">Get a visual overview of the current investigation.</span></span>
- <span data-ttu-id="32d94-226">查看调查持续时间的摘要。</span><span class="sxs-lookup"><span data-stu-id="32d94-226">View a summary of the investigation duration.</span></span>
- <span data-ttu-id="32d94-227">在可视化中选择一个节点以查看该节点的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32d94-227">Select a node in the visualization to view details for that node.</span></span>
- <span data-ttu-id="32d94-228">在顶部选择一个选项卡以查看该选项卡的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32d94-228">Select a tab across the top to view details for that tab.</span></span>

### <a name="alert-investigation"></a><span data-ttu-id="32d94-229">通知调查</span><span class="sxs-lookup"><span data-stu-id="32d94-229">Alert investigation</span></span>

<span data-ttu-id="32d94-230">在调查的 "**通知**" 选项卡上, 您可以查看与调查相关的警报。</span><span class="sxs-lookup"><span data-stu-id="32d94-230">On the **Alerts** tab for an investigation, you can see alerts relevant to the investigation.</span></span> <span data-ttu-id="32d94-231">详细信息包括触发调查的警报以及与调查相关的其他警报 (如有风险的登录、成批下载等)。</span><span class="sxs-lookup"><span data-stu-id="32d94-231">Details include the alert that triggered the investigation and other alerts, such as risky sign-in, mass download, etc., that are correlated to the investigation.</span></span> <span data-ttu-id="32d94-232">在此页面中, 安全分析员还可以查看各个通知的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="32d94-232">From this page, a security analyst can also view additional details on individual alerts.</span></span>

![空气警报页面](media/air-investigationalertspage.png)

<span data-ttu-id="32d94-234">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-234">You can:</span></span>
- <span data-ttu-id="32d94-235">获取当前触发警报和任何关联警报的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-235">Get a visual overview of the current triggering alert and any associated alerts.</span></span>
- <span data-ttu-id="32d94-236">在列表中选择一个警报, 打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="32d94-236">Select an alert in the list to open a fly-out page that shows full alert details.</span></span>

### <a name="email-investigation"></a><span data-ttu-id="32d94-237">电子邮件调查</span><span class="sxs-lookup"><span data-stu-id="32d94-237">Email investigation</span></span>

<span data-ttu-id="32d94-238">在调查的 "**电子邮件**" 选项卡上, 您可以查看标识为调查一部分的电子邮件的所有群集。</span><span class="sxs-lookup"><span data-stu-id="32d94-238">On the **Email** tab for an investigation, you can see all the clusters of email identified as part of the investigation.</span></span> 

<span data-ttu-id="32d94-239">由于组织中的用户发送和接收的电子邮件数量巨大, 因此</span><span class="sxs-lookup"><span data-stu-id="32d94-239">Given the sheer volume of email that users in an organization send and receive, the process of</span></span> 
- <span data-ttu-id="32d94-240">根据邮件头、正文、URL 和附件中的类似属性对电子邮件进行群集化;</span><span class="sxs-lookup"><span data-stu-id="32d94-240">clustering email messages based on similar attributes from a message header, body, URL and attachments;</span></span> 
- <span data-ttu-id="32d94-241">将恶意电子邮件与优质电子邮件分开;并</span><span class="sxs-lookup"><span data-stu-id="32d94-241">separating malicious email from the good email; and</span></span> 
- <span data-ttu-id="32d94-242">对恶意电子邮件采取操作</span><span class="sxs-lookup"><span data-stu-id="32d94-242">taking action on malicious email messages</span></span> 

<span data-ttu-id="32d94-243">可能需要几个小时。</span><span class="sxs-lookup"><span data-stu-id="32d94-243">can take many hours.</span></span> <span data-ttu-id="32d94-244">现在, AIR 可以自动执行此过程, 从而节省了贵组织的安全团队的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="32d94-244">AIR now automates this process, saving your organization's security team time and effort.</span></span> 

<span data-ttu-id="32d94-245">电子邮件分析步骤中可能会标识两种不同类型的电子邮件群集: 相似性群集和指示器群集。</span><span class="sxs-lookup"><span data-stu-id="32d94-245">Two different types of email clusters may be identified during the email analysis step: similarity clusters, and indicator clusters.</span></span> 
- <span data-ttu-id="32d94-246">相似性群集是包含相似的发件人和内容属性的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-246">Similarity clusters are email messages that contain similar sender and content attributes.</span></span> <span data-ttu-id="32d94-247">根据原始检测结果评估这些群集中的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="32d94-247">These clusters are evaluated for malicious content based on the original detection findings.</span></span> <span data-ttu-id="32d94-248">包含足够恶意检测的电子邮件群集将被视为恶意的。</span><span class="sxs-lookup"><span data-stu-id="32d94-248">Email clusters that contain enough malicious detections will be considered malicious.</span></span>
- <span data-ttu-id="32d94-249">指示器群集是包含来自原始电子邮件的指示器实体 (文件哈希或 URL) 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-249">Indicator clusters are email messages that contain the same indicator entity (file hash or URL) from the original email.</span></span> <span data-ttu-id="32d94-250">将原始文件/URL 实体标识为恶意时, AIR 会将指示器判定应用于包含该实体的整个群集的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-250">When the original file/URL entity is identified as malicious, AIR will apply the indicator verdict to the entire cluster of email messages containing that entity.</span></span> <span data-ttu-id="32d94-251">作为恶意软件标识的文件意味着包含该文件的电子邮件的群集将被视为恶意软件电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-251">As a file identified as malware will mean that the cluster of email messages containing that file will be treated as malware email messages.</span></span>

<span data-ttu-id="32d94-252">群集的目标是查找与攻击或市场活动的一部分由同一发件人发送的其他相关电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-252">The goal of clustering is to find other related email messages that are sent by the same sender as part of an attack or a campaign.</span></span>

<span data-ttu-id="32d94-253">"**电子邮件**" 选项卡还将显示与调查相关的电子邮件项目, 例如用户报告的电子邮件详细信息、报告的原始电子邮件、电子邮件 zapped (由于恶意软件/网络钓鱼诈骗等)。</span><span class="sxs-lookup"><span data-stu-id="32d94-253">The **Email** tab will also show email items related to the investigation, such as the user-reported email details, the original email reported, the email message(s) zapped due to malware/phish, etc.</span></span>

<span data-ttu-id="32d94-254">"电子邮件" 选项卡上标识的电子邮件计数当前代表 "**电子邮件**" 选项卡上显示的所有电子邮件的总数。由于电子邮件将出现在多个群集中, 因此标识的电子邮件的实际总数 (并受修正操作影响) 将是在所有群集和原始收件人的电子邮件中显示的唯一电子邮件的计数信息.</span><span class="sxs-lookup"><span data-stu-id="32d94-254">The email count identified on the email tab currently represents the sum total of all email messages shown on the **Email** tab. Since email messages will be present in multiple clusters, the actual total count of email messages identified (and affected by remediation actions) will be the count of unique email messages present across all of the clusters and original recipients' email messages.</span></span> 

<span data-ttu-id="32d94-255">根据每个收件人, 资源管理器和空中计数电子邮件, 因为安全 verdicts、操作和传递位置将因每个收件人而异。</span><span class="sxs-lookup"><span data-stu-id="32d94-255">Both Explorer and AIR count email messages on a per recipient basis, since the security verdicts, actions, and delivery locations will vary on a per recipient basis.</span></span> <span data-ttu-id="32d94-256">因此, 发送给三个用户的原始电子邮件将计为三个电子邮件 (而不是一个电子邮件) 的总数。</span><span class="sxs-lookup"><span data-stu-id="32d94-256">Thus an original email sent to three users will count as a total of three email messages instead of one email.</span></span> <span data-ttu-id="32d94-257">注释可能会出现两次或多次计数电子邮件的情况, 因为电子邮件可能会对其进行多个操作, 并且在发生所有操作后, 可能会有多个电子邮件副本。</span><span class="sxs-lookup"><span data-stu-id="32d94-257">Note there may be cases where an email gets counted two or more times, since the email may have multiple actions on it and there may be multiple copies of the email once all actions occur.</span></span> <span data-ttu-id="32d94-258">例如, 在传递时检测到的恶意软件电子邮件可能会导致阻止 (隔离) 的电子邮件和替换的电子邮件 (受警告文件替换的威胁文件, 然后传递到用户的邮箱)。</span><span class="sxs-lookup"><span data-stu-id="32d94-258">For example a malware email that is detected at delivery may result in both a blocked (quarantined) email and a replaced email (threat file replaced with an warning file, then delivered to user's mailbox).</span></span> <span data-ttu-id="32d94-259">由于在系统中有电子邮件的两个副本, 因此这两个副本可能会在群集计数中进行计数。</span><span class="sxs-lookup"><span data-stu-id="32d94-259">Since there are literally two copies of the email in the system - these may both be counted in cluster counts.</span></span> 

<span data-ttu-id="32d94-260">电子邮件计数是在调查时计算的, 当您打开调查 flyouts 时, 会重新计算一些计数 (基于基础查询)。</span><span class="sxs-lookup"><span data-stu-id="32d94-260">Email counts are calculated at the time of the investigation and some counts are re-calculated when you open investigation flyouts (based on an underlying query).</span></span> <span data-ttu-id="32d94-261">"电子邮件" 选项卡上显示的电子邮件群集的电子邮件计数以及在调查时将计算在 "群集浮出控件" 上显示的电子邮件数量值。</span><span class="sxs-lookup"><span data-stu-id="32d94-261">The email counts shown for the email clusters on the email tab and the email quantity value shown on cluster flyout are calculated at the time of investigation.</span></span> <span data-ttu-id="32d94-262">在 "群集" 浮出控件的 "电子邮件" 选项卡底部显示的电子邮件计数以及浏览器中显示的电子邮件数将反映在调查的初始分析之后收到的电子邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="32d94-262">The email count shown at the bottom of the email tab of the cluster flyout, as well as the count of email messages shown in Explorer will reflect email messages received after the investigation's initial analysis.</span></span> <span data-ttu-id="32d94-263">因此, 显示原始数量10封电子邮件的电子邮件群集会在调查分析阶段和管理员审查调查时, 显示总的电子邮件列表15个电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32d94-263">Thus an email cluster that shows an original quantity of 10 email messages would show an email list total of 15 when 5 more email messages arrive between the investigation analysis phase and when the admin reviews the investigation.</span></span> <span data-ttu-id="32d94-264">在不同的视图中显示这两个计数将完成, 以指示调查时的电子邮件影响和当前的影响, 直到运行补救时间为止。</span><span class="sxs-lookup"><span data-stu-id="32d94-264">Showing both counts in different views is done to indicate the email impact at the time of investigation and the current impact up until the time that remediation is run.</span></span>

<span data-ttu-id="32d94-265">例如, 请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="32d94-265">As an example, consider the following scenario.</span></span> <span data-ttu-id="32d94-266">三封电子邮件的第一个群集被认为是网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="32d94-266">The first cluster of three email messages were deemed to be phish.</span></span> <span data-ttu-id="32d94-267">找到具有相同 IP 和主题的类似邮件的另一个群集, 并被视为恶意邮件, 因为在初始检测过程中将其部分标识为网络钓鱼。</span><span class="sxs-lookup"><span data-stu-id="32d94-267">Another cluster of similar messages with the same IP and subject was found and considered malicious, as some of them were identified as phish during initial detection.</span></span> 

![空中电子邮件调查页面](media/air-investigationemailpage.png)

<span data-ttu-id="32d94-269">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-269">You can:</span></span>
- <span data-ttu-id="32d94-270">获取当前群集结果和发现的威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-270">Get a visual overview of the current clustering results and threats found.</span></span>
- <span data-ttu-id="32d94-271">单击 "群集" 实体或威胁列表打开显示完整警报详细信息的弹出页面。</span><span class="sxs-lookup"><span data-stu-id="32d94-271">Click a cluster entity or a threat list to open a fly-out page that shows the full alert details.</span></span>
- <span data-ttu-id="32d94-272">单击 "电子邮件群集详细信息" 选项卡顶部的 "在资源管理器中打开" 链接进一步调查电子邮件群集</span><span class="sxs-lookup"><span data-stu-id="32d94-272">Further investigate the email cluster by clicking the 'Open in Explorer' link at the top of the 'Email cluster details' tab</span></span>

![使用浮出控件详细信息的航空调查电子邮件](media/air-investigationemailpageflyoutdetails.png)

<span data-ttu-id="32d94-274">\* 注意: 在电子邮件上下文中, 您可能会在调查过程中看到一个卷异常威胁曲面。</span><span class="sxs-lookup"><span data-stu-id="32d94-274">\*Note: In the context of email, you may see a volume anomaly threat surface as part of the investigation.</span></span> <span data-ttu-id="32d94-275">卷异常表明调查事件时间与之前的时间框架相比, 与调查事件的类似电子邮件中的峰值。</span><span class="sxs-lookup"><span data-stu-id="32d94-275">A volume anomaly indicates a spike in similar email messages around the investigation event time compared to earlier timeframes.</span></span> <span data-ttu-id="32d94-276">这种具有类似特征 (例如, subject 和发件人域、正文相似性和发件人 IP) 的电子邮件通信的峰值是电子邮件宣传活动或攻击的典型启动。</span><span class="sxs-lookup"><span data-stu-id="32d94-276">This spike in email traffic with similar characteristics (e.g. subject and sender domain, body similarity and sender IP) is typical of the start of email campaigns or attacks.</span></span> <span data-ttu-id="32d94-277">但是, 批量、垃圾邮件和合法电子邮件活动通常共享这些特征。</span><span class="sxs-lookup"><span data-stu-id="32d94-277">However, bulk, spam, and legitimate email campaigns commonly share these characteristics.</span></span> <span data-ttu-id="32d94-278">由于使用反病毒引擎、沙箱或恶意信誉识别的恶意软件或网络钓鱼威胁相比, 大量异常会带来潜在的威胁, 因此可能会降低严重程度。</span><span class="sxs-lookup"><span data-stu-id="32d94-278">Volume anomalies represent a potential threat, and accordingly could be less severe compared to malware or phish threats that are identified using anti-virus engines, detonation or malicious reputation.</span></span>

### <a name="user-investigation"></a><span data-ttu-id="32d94-279">用户调查</span><span class="sxs-lookup"><span data-stu-id="32d94-279">User investigation</span></span>

<span data-ttu-id="32d94-280">在 "**用户**" 选项卡上, 您可以看到标识为调查的一部分的所有用户。</span><span class="sxs-lookup"><span data-stu-id="32d94-280">On the **Users** tab, you can see all the users identified as part of the investigation.</span></span> <span data-ttu-id="32d94-281">当存在事件或指示用户可能受到影响或受到威胁时, 将在调查中显示用户。</span><span class="sxs-lookup"><span data-stu-id="32d94-281">Users will appear in the investigation when there is an event or indication that the user may be affected or compromised.</span></span>

<span data-ttu-id="32d94-282">例如, 在下图中, 空气根据创建的新收件箱规则确定了安全指标和异常情况。</span><span class="sxs-lookup"><span data-stu-id="32d94-282">For example, in the following image, AIR has identified indicators of compromise and anomalies based on a new inbox rule that was created.</span></span> <span data-ttu-id="32d94-283">可通过此选项卡中的详细视图查看调查的其他详细信息 (证据)。损坏的迹象和异常也可能包含来自[Microsoft 云应用安全性](https://docs.microsoft.com/cloud-app-security)的异常检测。</span><span class="sxs-lookup"><span data-stu-id="32d94-283">Additional details (evidence) of the investigation are available through detailed views within this tab. Indicators of compromise and anomalies may also include anomaly detections from [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span>

![空中调查用户页](media/air-investigationuserspage.png)

<span data-ttu-id="32d94-285">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-285">You can:</span></span>
- <span data-ttu-id="32d94-286">获取已确定的用户结果和发现的风险的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-286">Get a visual overview of identified user results and risks found.</span></span>
- <span data-ttu-id="32d94-287">选择用户以打开显示完整警报详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="32d94-287">Select a user to open a fly-out page that shows the full alert details.</span></span>

### <a name="machine-investigation"></a><span data-ttu-id="32d94-288">机器调查</span><span class="sxs-lookup"><span data-stu-id="32d94-288">Machine investigation</span></span>

<span data-ttu-id="32d94-289">在 "**计算机**" 选项卡上, 您可以看到标识为调查的一部分的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="32d94-289">On the **Machines** tab, you can see all the machines identified as part of the investigation.</span></span> 

![空中调查计算机页面](media/air-investigationmachinepage.png)

<span data-ttu-id="32d94-291">作为调查的一部分, 空中将电子邮件威胁与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="32d94-291">As part of the investigation, AIR correlates email threats to devices.</span></span> <span data-ttu-id="32d94-292">例如, 调查会将恶意文件哈希传递到[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)以进行调查。</span><span class="sxs-lookup"><span data-stu-id="32d94-292">For example, an investigation passes a malicious file hash across to [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) to investigate.</span></span> <span data-ttu-id="32d94-293">这样, 就可以为您的用户自动调查相关的计算机, 以帮助确保在云中和终结点上解决威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-293">This allows for automated investigation of relevant machines for your users, to help ensure that threats are addressed both in the cloud and across your endpoints.</span></span> 

<span data-ttu-id="32d94-294">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-294">You can:</span></span>
- <span data-ttu-id="32d94-295">获取发现的当前计算机和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-295">Get a visual overview of the current machines and threats found.</span></span>
- <span data-ttu-id="32d94-296">选择一台计算机以打开在 windows defender atp Security Center 中相关的[Windows defender atp 调查](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)中的视图。</span><span class="sxs-lookup"><span data-stu-id="32d94-296">Select a machine to open a view that into the related [Windows Defender ATP investigations](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) in the Windows Defender ATP Security Center.</span></span>

### <a name="entity-investigation"></a><span data-ttu-id="32d94-297">实体调查</span><span class="sxs-lookup"><span data-stu-id="32d94-297">Entity investigation</span></span>

<span data-ttu-id="32d94-298">在 "**实体**" 选项卡上, 您可以看到标识为调查的一部分的所有实体。</span><span class="sxs-lookup"><span data-stu-id="32d94-298">On the **Entities** tab, you can see all the entities identified as part of the investigation.</span></span> 

<span data-ttu-id="32d94-299">在这里, 您可以查看调查的实体和实体类型的详细信息, 例如电子邮件、群集、IP 地址、用户等。</span><span class="sxs-lookup"><span data-stu-id="32d94-299">Here, you can see the investigated entities and details of the types of entities, such as email messages, clusters, IP addresses, users, and more.</span></span> <span data-ttu-id="32d94-300">您还可以查看已分析的实体数以及与每个实体相关联的威胁。</span><span class="sxs-lookup"><span data-stu-id="32d94-300">You can also see how many entities were analyzed, and the threats that were associated with each.</span></span> 

!["航空调查实体" 页](media/air-investigationentitiespage.png)

<span data-ttu-id="32d94-302">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-302">You can:</span></span>
- <span data-ttu-id="32d94-303">获取发现的调查实体和威胁的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-303">Get a visual overview of the investigation entities and threats found.</span></span>
- <span data-ttu-id="32d94-304">选择一个实体以打开显示相关实体详细信息的飞出页面。</span><span class="sxs-lookup"><span data-stu-id="32d94-304">Select an entity to open a fly-out page that shows the related entity details.</span></span>

![空中调查实体详细信息](media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a><span data-ttu-id="32d94-306">行动手册日志</span><span class="sxs-lookup"><span data-stu-id="32d94-306">Playbook log</span></span>

<span data-ttu-id="32d94-307">在 "**日志**" 选项卡上, 您可以查看调查过程中的所有操作手册步骤。</span><span class="sxs-lookup"><span data-stu-id="32d94-307">On the **Log** tab, you can see all the playbook steps that have occurred during the investigation.</span></span> <span data-ttu-id="32d94-308">该日志将捕获由 Office 365 自动调查功能作为空气的一部分完成的所有操作的完整清单。</span><span class="sxs-lookup"><span data-stu-id="32d94-308">The log captures a complete inventory of all actions completed by Office 365 auto-investigation capabilities as part of AIR.</span></span> <span data-ttu-id="32d94-309">它提供了所执行的所有步骤的清晰视图, 包括操作本身、说明以及实际 "开始到完成" 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="32d94-309">It provides a clear view of all the steps taken, including the action itself, a description, and the duration of the actual from start to finish.</span></span> 

![航空调查日志页](media/air-investigationlogpage.png)

<span data-ttu-id="32d94-311">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-311">You can:</span></span>
- <span data-ttu-id="32d94-312">获取有关执行操作手册步骤的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-312">Get see a visual overview of the playbook steps taken.</span></span>
- <span data-ttu-id="32d94-313">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="32d94-313">Export the results to a CSV file.</span></span>
- <span data-ttu-id="32d94-314">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="32d94-314">Filter the view.</span></span>

### <a name="recommended-actions"></a><span data-ttu-id="32d94-315">建议的操作</span><span class="sxs-lookup"><span data-stu-id="32d94-315">Recommended actions</span></span>

<span data-ttu-id="32d94-316">在 "**操作**" 选项卡上, 您可以查看在调查完成后建议用于修正的所有操作手册操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-316">On the **Actions** tab, you can see all the playbook actions that are recommended for remediation after the investigation has completed.</span></span> 

<span data-ttu-id="32d94-317">操作会捕获 Microsoft 建议在调查结束时执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="32d94-317">Actions capture the steps Microsoft recommends you take at the end of a investigation.</span></span> <span data-ttu-id="32d94-318">您可以通过选择一个或多个操作来采取补救措施。</span><span class="sxs-lookup"><span data-stu-id="32d94-318">You can take remediation actions here by selecting one or more actions.</span></span> <span data-ttu-id="32d94-319">单击 "**批准**" 将允许开始修正。</span><span class="sxs-lookup"><span data-stu-id="32d94-319">Clicking **Approve** will allow remediation to begin.</span></span> <span data-ttu-id="32d94-320">(需要适当的权限-需要 "搜索和清除" 角色才能从资源管理器和 AIR 运行操作)。</span><span class="sxs-lookup"><span data-stu-id="32d94-320">(Appropriate permissions are needed - the 'Search And Purge' role is required to run actions from Explorer and AIR).</span></span> <span data-ttu-id="32d94-321">例如, 安全读者可以查看操作但不能批准。</span><span class="sxs-lookup"><span data-stu-id="32d94-321">For example, a Security Reader can view actions but not approve them.</span></span> <span data-ttu-id="32d94-322">注意-您无需批准每个操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-322">Note - you do not have to approve every action.</span></span> <span data-ttu-id="32d94-323">如果您不同意建议的操作, 或者您的组织不选择特定类型的操作, 则可以选择**拒绝**这些操作, 也可以仅忽略它们, 不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-323">If you do not agree with the recommended action or your organization does not choose certain types of actions - then you can either choose to **Reject** the actions or simply ignore them and take no action.</span></span> <span data-ttu-id="32d94-324">审核和/或拒绝所有操作将完全关闭调查, 而保留某些操作不完整将导致调查状态更改为 "部分修正" 状态。</span><span class="sxs-lookup"><span data-stu-id="32d94-324">Approving and/or rejecting all actions will let the investigation fully close, while leaving some actions incomplete will result in the investigation status changing to a partially remediated state.</span></span>

![航空调查操作页](media/air-investigationactionspage.png)

<span data-ttu-id="32d94-326">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="32d94-326">You can:</span></span>
- <span data-ttu-id="32d94-327">获取对操作手册建议的操作的直观概述。</span><span class="sxs-lookup"><span data-stu-id="32d94-327">Get a visual overview of the playbook-recommended actions.</span></span>
- <span data-ttu-id="32d94-328">选择一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-328">Select a single action or multiple actions.</span></span>
- <span data-ttu-id="32d94-329">使用注释批准或拒绝建议的操作。</span><span class="sxs-lookup"><span data-stu-id="32d94-329">Approve or reject recommended actions with comments.</span></span>
- <span data-ttu-id="32d94-330">将结果导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="32d94-330">Export the results to a CSV file.</span></span>
- <span data-ttu-id="32d94-331">筛选视图。</span><span class="sxs-lookup"><span data-stu-id="32d94-331">Filter the view.</span></span>

## <a name="how-to-get-air"></a><span data-ttu-id="32d94-332">如何获取空中</span><span class="sxs-lookup"><span data-stu-id="32d94-332">How to get AIR</span></span>

<span data-ttu-id="32d94-333">目前, Office 365 AIR 功能处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="32d94-333">Currently, Office 365 AIR features are in preview.</span></span> <span data-ttu-id="32d94-334">当普遍可用时, Office 365 AIR 功能将包含在以下订阅中:</span><span class="sxs-lookup"><span data-stu-id="32d94-334">When generally available, Office 365 AIR features will be included in the following subscriptions:</span></span>

- <span data-ttu-id="32d94-335">Microsoft 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="32d94-335">Microsoft 365 Enterprise E5</span></span>
- <span data-ttu-id="32d94-336">Office 365 企业版 E5</span><span class="sxs-lookup"><span data-stu-id="32d94-336">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="32d94-337">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="32d94-337">Microsoft Threat Protection</span></span>
- <span data-ttu-id="32d94-338">Office 365 高级威胁防护计划2</span><span class="sxs-lookup"><span data-stu-id="32d94-338">Office 365 Advanced Threat Protection Plan 2</span></span>

<span data-ttu-id="32d94-339">若要了解有关功能可用性的详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="32d94-339">To learn more about feature availability, visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>
