---
title: Office 365 云应用安全中的异常检测策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 88935b4e-dcb1-47f1-8aca-1bf8fb069db6
description: 'Office 365 云应用程序安全性的异常检测策略使用内置的算法来帮助发现潜在的问题。您应具有至少一个异常检测策略，您可以通过使用筛选器调整 （当您创建它）。 '
ms.openlocfilehash: 80f576d7c1c42ab60c1b031dcd33591f8e1ce4b8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525986"
---
# <a name="anomaly-detection-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="08d38-104">Office 365 云应用安全中的异常检测策略</span><span class="sxs-lookup"><span data-stu-id="08d38-104">Anomaly detection policies in Office 365 Cloud App Security</span></span>

<span data-ttu-id="08d38-105">Office 365 高级安全管理现在是 Office 365 云应用程序安全性。</span><span class="sxs-lookup"><span data-stu-id="08d38-105">Office 365 Advanced Security Management is now Office 365 Cloud App Security.</span></span>
  
|<span data-ttu-id="08d38-106">评估 * *\>**</span><span class="sxs-lookup"><span data-stu-id="08d38-106">****Evaluation** \>**</span></span>|<span data-ttu-id="08d38-107">规划 * *\>**</span><span class="sxs-lookup"><span data-stu-id="08d38-107">****Planning** \>**</span></span>|<span data-ttu-id="08d38-108">部署 * *\>**</span><span class="sxs-lookup"><span data-stu-id="08d38-108">****Deployment** \>**</span></span>|<span data-ttu-id="08d38-109">使用率 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="08d38-109">****Utilization****</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="08d38-110">启动评估</span><span class="sxs-lookup"><span data-stu-id="08d38-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="08d38-111">开始规划</span><span class="sxs-lookup"><span data-stu-id="08d38-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="08d38-112">在这里 ！</span><span class="sxs-lookup"><span data-stu-id="08d38-112">You are here!</span></span>  <br/> [<span data-ttu-id="08d38-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="08d38-113">Next step</span></span>](integrate-your-siem-server-with-office-365-cas.md) <br/> |[<span data-ttu-id="08d38-114">开始利用</span><span class="sxs-lookup"><span data-stu-id="08d38-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |
   
<span data-ttu-id="08d38-115">Office 365 云应用程序安全性开头[Microsoft 云应用程序安全性释放 116](https://docs.microsoft.com/cloud-app-security/release-notes)，包括多个预定义的异常检测策略 （"开"），包括用户、 实体行为分析 (UEBA) 以及学习 (ML) 的计算机。</span><span class="sxs-lookup"><span data-stu-id="08d38-115">Beginning with [Microsoft Cloud App Security release 116](https://docs.microsoft.com/cloud-app-security/release-notes), Office 365 Cloud App Security includes several predefined anomaly detection policies ("out of the box") that include user and entity behavioral analytics (UEBA) and machine learning (ML).</span></span>
  
![若要查看您的异常检测策略，请选择控件\>策略。](media/9663baa5-98bf-45e0-9458-6e572b43ec72.png)
  
<span data-ttu-id="08d38-p102">这些异常检测策略通过提供即时检测，在您的用户和计算机连接到您的网络设备设定大量行为异常提供即时结果。此外，新策略公开来自云应用程序安全性检测引擎，以帮助您调查处理速度和包含持续威胁的其他数据。</span><span class="sxs-lookup"><span data-stu-id="08d38-p102">These anomaly detection policies provide immediate results by providing immediate detections, targeting numerous behavioral anomalies across your users and the machines and devices connected to your network. In addition, the new policies expose more data from the Cloud App Security detection engine to help you speed up the investigation process and contain ongoing threats.</span></span>
  
<span data-ttu-id="08d38-119">作为[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md)，您可以查看，并根据需要进行修改可用于 Office 365 云应用程序安全性的默认策略。</span><span class="sxs-lookup"><span data-stu-id="08d38-119">As a [global administrator or security administrator](permissions-in-the-security-and-compliance-center.md), you can review, and if necessary, revise the default policies that are available with Office 365 Cloud App Security.</span></span>
  
 > [!IMPORTANT]
> <span data-ttu-id="08d38-p103">没有七天期间异常行为通知不会触发初始学习期。异常检测算法经过优化，可减少误报警报的数。</span><span class="sxs-lookup"><span data-stu-id="08d38-p103">There is an initial learning period of seven (7) days during which anomalous behavior alerts are not triggered. The anomaly detection algorithm is optimized to reduce the number of false positive alerts.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="08d38-122">准备工作</span><span class="sxs-lookup"><span data-stu-id="08d38-122">Before you begin</span></span>

<span data-ttu-id="08d38-123">请确保：</span><span class="sxs-lookup"><span data-stu-id="08d38-123">Make sure that:</span></span>
  
- <span data-ttu-id="08d38-124">您的组织具有[Office 365 云应用程序安全性](office-365-cas-overview.md)，并且该服务[开启](turn-on-office-365-cas.md)。</span><span class="sxs-lookup"><span data-stu-id="08d38-124">Your organization has [Office 365 Cloud App Security](office-365-cas-overview.md), and the service is [turned on](turn-on-office-365-cas.md).</span></span>
    
- <span data-ttu-id="08d38-125">[审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态的 Office 365 环境。</span><span class="sxs-lookup"><span data-stu-id="08d38-125">[Audit logging](turn-audit-log-search-on-or-off.md) is turned on for your Office 365 environment.</span></span> 
    
- <span data-ttu-id="08d38-126">您是全局管理员或 Office 365 安全管理员。</span><span class="sxs-lookup"><span data-stu-id="08d38-126">You are a global administrator or security administrator for Office 365.</span></span>
    
## <a name="view-your-anomaly-detection-policies"></a><span data-ttu-id="08d38-127">查看您异常检测策略</span><span class="sxs-lookup"><span data-stu-id="08d38-127">View your anomaly detection policies</span></span>

1. <span data-ttu-id="08d38-128">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="08d38-128">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="08d38-129">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="08d38-129">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="08d38-130">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="08d38-130">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
    <span data-ttu-id="08d38-131">您将转到 Office 365 云应用程序安全策略页。</span><span class="sxs-lookup"><span data-stu-id="08d38-131">This takes you to the Office 365 Cloud App Security Policies page.</span></span>
    
4. <span data-ttu-id="08d38-132">在**类型**列表中，选择**异常检测策略**。</span><span class="sxs-lookup"><span data-stu-id="08d38-132">In the **TYPE** list, choose **Anomaly detection policy**.</span></span>
    
    <span data-ttu-id="08d38-133">贵组织的默认 （或现有） 显示异常检测策略。</span><span class="sxs-lookup"><span data-stu-id="08d38-133">Your organization's default (or existing) anomaly detection policies are displayed.</span></span>
    
    ![多个异常检测策略是默认可在 Office 365 云应用程序安全性](media/2e0ee770-787a-4d4a-bea8-389dc765d4c6.png)
  
5. <span data-ttu-id="08d38-135">选择要查看或编辑其设置策略。</span><span class="sxs-lookup"><span data-stu-id="08d38-135">Select a policy to review or edit its settings.</span></span>
    
6. <span data-ttu-id="08d38-136">选择**更新**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="08d38-136">Choose **Update** to save your changes.</span></span> 
    
## <a name="learn-more-about-anomaly-detection-policies"></a><span data-ttu-id="08d38-137">了解有关异常检测策略</span><span class="sxs-lookup"><span data-stu-id="08d38-137">Learn more about anomaly detection policies</span></span>

<span data-ttu-id="08d38-p104">将自动启用异常检测策略;但是，Office 365 云应用程序安全性有七天的不是所有异常期间检测警报初始学习期。之后，每个会话进行比较活动，当用户处于活动状态、 IP 地址、 设备、 等通过过去的月和风险评分的这些活动检测。这些检测属于试探性异常检测引擎的配置文件环境并触发警报采用了获知您的组织的活动的基线。这些检测还利用计算机学习算法旨在配置文件的用户和登录模式，以减少误报。</span><span class="sxs-lookup"><span data-stu-id="08d38-p104">Anomaly detection policies are automatically enabled; however, Office 365 Cloud App Security has an initial learning period of seven days during which not all anomaly detection alerts are raised. After that, each session is compared to the activity, when users were active, IP addresses, devices, etc. detected over the past month and the risk score of these activities. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity. These detections also leverage machine learning algorithms designed to profile the users and log-in patterns to reduce false positives.</span></span>
  
<span data-ttu-id="08d38-p105">通过扫描用户活动检测到异常。通过查看超过 30 不同的风险指标，分为多个风险因素，如 risky IP 地址、 登录失败，管理活动、 非活动帐户、 位置、 意思差旅、 设备和用户代理和活动频率来计算风险。</span><span class="sxs-lookup"><span data-stu-id="08d38-p105">Anomalies are detected by scanning user activity. The risk is evaluated by looking at over 30 different risk indicators, grouped into multiple risk factors, such as risky IP address, login failures, admin activity, inactive accounts, location, impossible travel, device and user agent, and activity rate.</span></span>
  
<span data-ttu-id="08d38-p106">基于策略的结果，触发安全警告。Office 365 云应用程序安全性查找 Office 365 中的每个用户会话，并从您的组织的基线或从用户的常规活动不同发生变化时通知您。</span><span class="sxs-lookup"><span data-stu-id="08d38-p106">Based on the policy results, security alerts are triggered. Office 365 Cloud App Security looks at every user session in Office 365, and alerts you whenever something happens that is different from the baseline of your organization or from a user's regular activity.</span></span>
  
<span data-ttu-id="08d38-146">下表介绍的默认异常检测策略、 用途，以及它们的工作方式。</span><span class="sxs-lookup"><span data-stu-id="08d38-146">The following table describes the default anomaly detection policies, what they do, and how they work.</span></span>
  
|<span data-ttu-id="08d38-147">**异常检测策略名称**</span><span class="sxs-lookup"><span data-stu-id="08d38-147">**Anomaly detection policy name**</span></span>|<span data-ttu-id="08d38-148">**如何工作**</span><span class="sxs-lookup"><span data-stu-id="08d38-148">**How it works**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08d38-149">意思出差</span><span class="sxs-lookup"><span data-stu-id="08d38-149">Impossible travel</span></span>  <br/> |<span data-ttu-id="08d38-p107">标识两个用户活动 （为一个或多个会话） 源自遥远位置比时间较短的时间段内它可能需要花费用户从第一个位置移动到第二个，指示不同用户使用相同的凭据。此检测利用学习忽略明显"误报"分配给不可能的差旅条件，如 Vpn 和定期由组织中的其他用户的位置的算法的计算机。检测已初始学习期期间其学习新的用户活动模式的七天。</span><span class="sxs-lookup"><span data-stu-id="08d38-p107">Identifies two user activities (is a single or multiple sessions) originating from geographically distant locations within a time period shorter than the time it would have taken the user to travel from the first location to the second, indicating that a different user is using the same credentials. This detection leverages a machine learning algorithm that ignores obvious "false positives" contributing to the impossible travel condition, such as VPNs and locations regularly used by other users in the organization. The detection has an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>  <br/> |
|<span data-ttu-id="08d38-153">来自非频繁的国家/地区的活动</span><span class="sxs-lookup"><span data-stu-id="08d38-153">Activity from infrequent country</span></span>  <br/> |<span data-ttu-id="08d38-p108">认为过活动位置确定新和非频繁位置。异常检测引擎存储有关组织中的用户使用的以前位置信息。活动发生从不最近或从不访问由用户或由组织中的任何用户的位置时，将触发一条通知。</span><span class="sxs-lookup"><span data-stu-id="08d38-p108">Considers past activity locations to determine new and infrequent locations. The anomaly detection engine stores information about previous locations used by users in the organization. An alert is triggered when an activity occurs from a location that was not recently or never visited by the user or by any user in the organization.</span></span>  <br/> |
|<span data-ttu-id="08d38-157">从匿名 IP 地址的活动</span><span class="sxs-lookup"><span data-stu-id="08d38-157">Activity from anonymous IP addresses</span></span>  <br/> |<span data-ttu-id="08d38-p109">标识用户处于活动从已被标识为匿名代理 IP 地址的 IP 地址。要隐藏其设备的 IP 地址，并可用于恶意的人员使用这些代理。此检测利用学习减少了"误报"，如设施标记广泛使用组织中的用户的 IP 地址的算法的计算机。</span><span class="sxs-lookup"><span data-stu-id="08d38-p109">Identifies that users were active from an IP address that has been identified as an anonymous proxy IP address. These proxies are used by people who want to hide their device's IP address, and may be used for malicious intent. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="08d38-161">从可疑 IP 地址的活动</span><span class="sxs-lookup"><span data-stu-id="08d38-161">Activity from suspicious IP addresses</span></span>  <br/> |<span data-ttu-id="08d38-p110">标识用户已从一个 IP 地址，由 Microsoft Threat 智能标识为 risky 活动。这些 IP 地址所涉及恶意活动，例如机器人网 C&amp;C，并可能表明受到攻击的帐户。此检测利用学习减少了"误报"，如设施标记广泛使用组织中的用户的 IP 地址的算法的计算机。</span><span class="sxs-lookup"><span data-stu-id="08d38-p110">Identifies that users were active from an IP address that has been identified as risky by Microsoft Threat Intelligence. These IP addresses are involved in malicious activities, such as Botnet C&amp;C, and may indicate compromised account. This detection leverages a machine learning algorithm that reduces "false positives", such as mis-tagged IP addresses that are widely used by users in the organization.</span></span>  <br/> |
|<span data-ttu-id="08d38-165">特殊的活动 （由用户）</span><span class="sxs-lookup"><span data-stu-id="08d38-165">Unusual activities (by user)</span></span>  <br/> | <span data-ttu-id="08d38-166">标识用户执行特殊的活动，例如：</span><span class="sxs-lookup"><span data-stu-id="08d38-166">Identifies users who perform unusual activities, such as:</span></span>  <br/>  <span data-ttu-id="08d38-167">-多个文件下载</span><span class="sxs-lookup"><span data-stu-id="08d38-167">--Multiple file downloads</span></span>  <br/>  <span data-ttu-id="08d38-168">-文件共享活动</span><span class="sxs-lookup"><span data-stu-id="08d38-168">--File sharing activities</span></span>  <br/>  <span data-ttu-id="08d38-169">-文件删除活动</span><span class="sxs-lookup"><span data-stu-id="08d38-169">--File deletion activities</span></span>  <br/>  <span data-ttu-id="08d38-170">-模拟活动</span><span class="sxs-lookup"><span data-stu-id="08d38-170">--Impersonation activities</span></span>  <br/>  <span data-ttu-id="08d38-171">-管理活动</span><span class="sxs-lookup"><span data-stu-id="08d38-171">--Administrative activities</span></span>  <br/>  <span data-ttu-id="08d38-p111">这些策略查找活动相对于基线教训，单个会话中无法指示违反尝试。这些检测利用学习用户配置文件登录模式的算法的计算机，并减少误报。这些检测属于试探性异常检测引擎的配置文件环境并触发警报采用了获知您的组织的活动的基线。</span><span class="sxs-lookup"><span data-stu-id="08d38-p111">These policies look for activities within a single session with respect to the baseline learned, which could indicate on a breach attempt. These detections leverage a machine learning algorithm that profiles the users log on pattern and reduces false positives. These detections are part of the heuristic anomaly detection engine that profiles your environment and triggers alerts with respect to a baseline that was learned on your organization's activity.</span></span>  <br/> |
|<span data-ttu-id="08d38-175">多个失败的登录尝试次数</span><span class="sxs-lookup"><span data-stu-id="08d38-175">Multiple failed login attempts</span></span>  <br/> |<span data-ttu-id="08d38-176">标识用户失败单个会话中的多个登录尝试的相对于基线教训，这可能表示违反尝试。</span><span class="sxs-lookup"><span data-stu-id="08d38-176">Identifies users that failed multiple login attempts in a single session with respect to the baseline learned, which could indicate on a breach attempt.</span></span>  <br/> |
   
## <a name="triage-anomaly-detection-alerts"></a><span data-ttu-id="08d38-177">会审异常检测警报</span><span class="sxs-lookup"><span data-stu-id="08d38-177">Triage anomaly detection alerts</span></span>
<span data-ttu-id="08d38-178"><a name="triage"> </a></span><span class="sxs-lookup"><span data-stu-id="08d38-178"></span></span>

<span data-ttu-id="08d38-p112">通知逐渐，您可以快速会审这些通知并确定要将哪些首先处理。具有上下文的通知，可以看到更大的图片，并确定是否有恶意确实情况发生。使用以下过程开始浏览通知：</span><span class="sxs-lookup"><span data-stu-id="08d38-p112">As alerts come in, you can triage those alerts quickly and determine which ones to handle first. Having context for an alert enables you to see the bigger picture and determine whether something malicious is indeed happening. Use the following procedure to get started exploring an alert:</span></span>
  
1. <span data-ttu-id="08d38-182">以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="08d38-182">As a global administrator or security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account.</span></span> 
    
2. <span data-ttu-id="08d38-183">安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。</span><span class="sxs-lookup"><span data-stu-id="08d38-183">In the Security &amp; Compliance Center, choose **Alerts** \> **Manage advanced alerts**.</span></span>
    
3. <span data-ttu-id="08d38-184">选择**转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="08d38-184">Choose **Go to Office 365 Cloud App Security**.</span></span>
    
4. <span data-ttu-id="08d38-185">选择**通知**以查看您的通知。</span><span class="sxs-lookup"><span data-stu-id="08d38-185">Choose **Alerts** to view your alerts.</span></span> 
    
5. <span data-ttu-id="08d38-186">获取通知上下文，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="08d38-186">To get context for an alert, follow these steps:</span></span>
    
1. <span data-ttu-id="08d38-187">选择**调查** \> **活动日志**。</span><span class="sxs-lookup"><span data-stu-id="08d38-187">Choose **Investigate** \> **Activity log**.</span></span>
    
2. <span data-ttu-id="08d38-p113">选择一个项目，如用户或 IP 地址。这将打开相关见解纸盒。</span><span class="sxs-lookup"><span data-stu-id="08d38-p113">Select an item, such as a user or IP address. This opens the relevant insights drawer.</span></span>
    
    ![在活动日志中，您可以调查的 IP 地址。](media/32a727c5-e406-4fe2-9443-c1a7fb6628fc.png)
  
3. <span data-ttu-id="08d38-191">在相关见解银中，单击可用的命令，如**显示类似**部分中的图标。</span><span class="sxs-lookup"><span data-stu-id="08d38-191">In the relevant insights drawer, click an available command, such as an icon in the **SHOW SIMILAR** section.</span></span> 
    
    ![在相关见解银，可以单击该时钟图标可查看选定活动的 48 小时内执行的活动](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
4. <span data-ttu-id="08d38-193">深入了解有关所选项目通过继续浏览该项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="08d38-193">Gain insight about the selected item by continuing to explore details for that item.</span></span>
    
<span data-ttu-id="08d38-p114">在多个失败登录通知良言可能可疑，并可指示潜在的强力攻击。但是，此类通知也可能是应用程序配置不正确，导致通知为误报，则返回 true 误报。如果您看到其他可疑活动多失败登录警报，则帐户受到威胁的更高的概率。例如，假设，多失败登录通知后跟活动从或 IP 地址和意思差旅活动，这两个强指标的威胁。您甚至可能会看到相同的用户执行大量下载活动，它通常是攻击者执行 exfiltration 的数据的指示符。它的类，您可以了解 Office 365 云应用程序安全性，若要查看和会审通知，并执行操作中操作在需要时。</span><span class="sxs-lookup"><span data-stu-id="08d38-p114">An alert on multiple failed logins might indeed be suspicious, and can indicate a potential brute-force attack. However, such an alert can also be an application misconfiguration, causing the alert to be a benign true positive. If you see a multiple-failed-logins alert with additional suspicious activities, then there is a higher probability that an account is compromised. For example, suppose that a multiple-failed-login alert is followed by activity from a TOR IP address and impossible travel activity, both strong indicators of compromise. You might even see that the same user performed a mass download activity, which is often an indicator of the attacker performing exfiltration of data. It's things like that that you can explore in Office 365 Cloud App Security to view and triage your alerts, and take action where needed.</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="08d38-200">后续步骤</span><span class="sxs-lookup"><span data-stu-id="08d38-200">Next steps</span></span>
<span data-ttu-id="08d38-201"><a name="nextsteps"> </a></span><span class="sxs-lookup"><span data-stu-id="08d38-201"></span></span>

- [<span data-ttu-id="08d38-202">将 SIEM 服务器集成</span><span class="sxs-lookup"><span data-stu-id="08d38-202">Integrate your SIEM server</span></span>](integrate-your-siem-server-with-office-365-cas.md)
    
- [<span data-ttu-id="08d38-203">查看并通知对其执行操作</span><span class="sxs-lookup"><span data-stu-id="08d38-203">Review and take action on alerts</span></span>](review-office-365-cas-alerts.md)
    
- [<span data-ttu-id="08d38-204">若要简化管理您 IP 地址进行分组</span><span class="sxs-lookup"><span data-stu-id="08d38-204">Group your IP addresses to simplify management</span></span>](group-your-ip-addresses-in-ocas.md)
    

