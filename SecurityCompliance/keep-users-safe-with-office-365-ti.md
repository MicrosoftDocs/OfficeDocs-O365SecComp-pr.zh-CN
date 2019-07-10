---
title: 使用 Office 365 威胁调查和响应功能保持 Office 365 用户安全
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
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: 了解 Office 365 威胁调查和响应功能如何帮助您的组织检测入侵和威胁, 并快速缓解和恢复威胁。
ms.openlocfilehash: 28fbf0a66370e2e1d407454017943e57f5f368b1
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598978"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="e5552-103">使用 Office 365 威胁调查和响应功能保持 Office 365 用户安全</span><span class="sxs-lookup"><span data-stu-id="e5552-103">Keep your Office 365 users safe with Office 365 threat investigation and response capabilities</span></span>

## <a name="overview"></a><span data-ttu-id="e5552-104">概述</span><span class="sxs-lookup"><span data-stu-id="e5552-104">Overview</span></span>

<span data-ttu-id="e5552-105">您是否知道您的 Office 365 用户受攻击或更糟的威胁？</span><span class="sxs-lookup"><span data-stu-id="e5552-105">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="e5552-106">知道如何缓解和恢复面向用户的攻击？</span><span class="sxs-lookup"><span data-stu-id="e5552-106">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="e5552-107">您是否知道您可以使用 Office 365 中已有的安全功能完全完成此操作？</span><span class="sxs-lookup"><span data-stu-id="e5552-107">Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="e5552-108">Office 365 中的[威胁调查和响应](office-365-ti.md)功能包含在 Office 365 E5 订阅中 (作为 Office 365 高级威胁防护计划2的一部分)。</span><span class="sxs-lookup"><span data-stu-id="e5552-108">[Office 365 threat investigation and response](office-365-ti.md) capabilities are included in your Office 365 E5 subscription (as part of Office 365 Advanced Threat Protection Plan 2).</span></span> <span data-ttu-id="e5552-109">这些功能已帮助 Microsoft IT 缩短了 80% 的社会工程活动的平均解决时间, 以及与前两个季度相比每月 37% 的增长率。</span><span class="sxs-lookup"><span data-stu-id="e5552-109">These capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

<span data-ttu-id="e5552-110">我们最近添加了新功能, 可帮助改进检测和恢复威胁的方式!</span><span class="sxs-lookup"><span data-stu-id="e5552-110">We've recently added new capabilities to help improve how you can detect and recover from threats!</span></span> <span data-ttu-id="e5552-111">下面简单介绍了更新后的威胁调查和响应功能如何提高效率。</span><span class="sxs-lookup"><span data-stu-id="e5552-111">Here's a quick walk through of how the updated Threat investigation and response capabilities can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="e5552-112">检测入侵和威胁</span><span class="sxs-lookup"><span data-stu-id="e5552-112">Detect intrusions and threats</span></span>

<span data-ttu-id="e5552-113">[威胁浏览器 (或实时检测)](threat-explorer.md)(也称为 "威胁浏览器") 可帮助安全管理员和分析师识别和理解企业中的活动威胁, 因为看似无害的用户配置 (如安全) 可能会规避最复杂的安全设置发件人白名单。</span><span class="sxs-lookup"><span data-stu-id="e5552-113">[Threat Explorer (or real-time detections)](threat-explorer.md) (also referred to as Threat Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists.</span></span> <span data-ttu-id="e5552-114">资源管理器可帮助 Office 365 全局或安全管理员快速确定用户是否已被威胁 (如恶意软件或网络钓鱼诈骗) 所危害。</span><span class="sxs-lookup"><span data-stu-id="e5552-114">Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish.</span></span> <span data-ttu-id="e5552-115">这有助于确定哪些用户最面临威胁的风险以及必需的响应的优先级。</span><span class="sxs-lookup"><span data-stu-id="e5552-115">This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="e5552-116">资源管理器还可帮助管理员导航用户和邮件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="e5552-116">Explorer also helps admins navigate the relationships between users and mail.</span></span> <span data-ttu-id="e5552-117">知道有误的特定邮件吗？</span><span class="sxs-lookup"><span data-stu-id="e5552-117">Know of a particular mail that was bad?</span></span> <span data-ttu-id="e5552-118">搜索它以查看哪些用户收到了邮件, 然后按照一系列事件进行操作, 并查看这些用户接下来的操作。</span><span class="sxs-lookup"><span data-stu-id="e5552-118">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="e5552-119">如果您还没有这些功能, 请[立即试用](https://aka.ms/tryo365threatintel3)!</span><span class="sxs-lookup"><span data-stu-id="e5552-119">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="e5552-120">并[了解有关 Office 365 威胁调查和响应的详细信息](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="e5552-120">And [learn more about Office 365 threat investigation and response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![Office 365 中的威胁资源管理器的屏幕截图, 由恶意软件系列进行颜色编码](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="e5552-122">快速缓解威胁并从威胁中恢复</span><span class="sxs-lookup"><span data-stu-id="e5552-122">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="e5552-123">一旦安全管理员发现了其租户中发生可疑或恶意的问题, 他们就可以使用**事件框架**快速包含和响应该威胁。</span><span class="sxs-lookup"><span data-stu-id="e5552-123">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="e5552-124">通过单击对不需要的邮件进行分组并快速删除用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e5552-124">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="e5552-125">**更新:** 我们已添加了直接从事件框架中删除 (软删除或硬删除) 电子邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="e5552-125">**UPDATE:** We've added the ability to delete (soft or hard delete) emails directly from the Incident Framework.</span></span> <span data-ttu-id="e5552-126">以前的管理员只能将邮件移动到用户的垃圾邮件文件夹, 用户可以在那里恢复项目。</span><span class="sxs-lookup"><span data-stu-id="e5552-126">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="e5552-127">使用新的已发布的删除功能, 现在可以确保永久删除恶意或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="e5552-127">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="e5552-128">如果您还没有这些功能, 请[立即试用](https://aka.ms/tryo365threatintel3)!</span><span class="sxs-lookup"><span data-stu-id="e5552-128">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="e5552-129">并[了解有关 Office 365 威胁调查和响应的详细信息](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="e5552-129">And [learn more about Office 365 threat investigation and response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![事件修正的电子邮件列表的屏幕截图](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="e5552-131">利用 Microsoft 的威胁遥测</span><span class="sxs-lookup"><span data-stu-id="e5552-131">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="e5552-132">Office 365 威胁调查和响应功能使用 Microsoft 智能安全图形中的数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="e5552-132">Office 365 threat investigation and response capabilities are powered with data from the Microsoft Intelligent Security Graph.</span></span> <span data-ttu-id="e5552-133">Graph 从 1000000000 Windows 设备、450000000000每月 Azure 登录和 400000000000 Office 365 中的每月电子邮件获取最新的威胁信号。</span><span class="sxs-lookup"><span data-stu-id="e5552-133">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="e5552-134">这一无与伦比的威胁信号是为管理员和安全分析员提供了对影响其组织的威胁的完整视图的客户租户的广泛可见性。</span><span class="sxs-lookup"><span data-stu-id="e5552-134">This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
   
## <a name="why-use-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="e5552-135">为什么要使用 Office 365 威胁调查和响应功能？</span><span class="sxs-lookup"><span data-stu-id="e5552-135">Why use Office 365 threat investigation and response capabilities?</span></span>

<span data-ttu-id="e5552-136">Gartner 估计在2017中仅限 $ 90B 用在 cybersecurity 上。</span><span class="sxs-lookup"><span data-stu-id="e5552-136">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity.</span></span> <span data-ttu-id="e5552-137">Sid Deshpande (Gartner 的主要研究分析师) 的报价如下所示: "业界转向检测和响应的方式 .。。</span><span class="sxs-lookup"><span data-stu-id="e5552-137">Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response …</span></span> <span data-ttu-id="e5552-138">发送清除阻止的 futile, 除非将其绑定到检测和响应功能。</span><span class="sxs-lookup"><span data-stu-id="e5552-138">sends a clear message that prevention is futile unless it is tied into a detection and response capability."</span></span> <span data-ttu-id="e5552-139">威胁调查和响应是每个企业的一系列服务的关键组成部分, 可作为独立服务或作为 Office 365 E5 的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="e5552-139">Threat investigation and response is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="e5552-140">接下来做什么</span><span class="sxs-lookup"><span data-stu-id="e5552-140">What's Next</span></span>

- <span data-ttu-id="e5552-141">有关此录制的会话中的 Office 365 威胁调查和响应功能的详细信息, 请参阅以下内容:[使用 Office 365 保持在 Cyberattacks 之前](https://myignite.microsoft.com/videos/53723)</span><span class="sxs-lookup"><span data-stu-id="e5552-141">Learn more about Office 365 threat investigation and response capabilities  in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="e5552-142">[立即试用 office 365 威胁调查和响应功能, 或立即](https://aka.ms/tryo365threatintel3)开始你的 office E5 试用版!</span><span class="sxs-lookup"><span data-stu-id="e5552-142">[Try out Office 365 threat investigation and response capabilities now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

