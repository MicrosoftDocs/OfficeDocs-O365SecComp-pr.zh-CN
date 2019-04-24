---
title: 使用 office 365 威胁调查和响应功能保持 office 365 用户安全
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
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
ms.openlocfilehash: 9ed20713cac07631e63b969efea402e8dbeb8f6d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254044"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="d8290-103">使用 office 365 威胁调查和响应功能保持 office 365 用户安全</span><span class="sxs-lookup"><span data-stu-id="d8290-103">Keep your Office 365 users safe with Office 365 Threat Investigation and Response capabilities</span></span>

## <a name="overview"></a><span data-ttu-id="d8290-104">概述</span><span class="sxs-lookup"><span data-stu-id="d8290-104">Overview</span></span>

<span data-ttu-id="d8290-105">您是否知道您的 Office 365 用户受攻击或更糟的威胁？</span><span class="sxs-lookup"><span data-stu-id="d8290-105">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="d8290-106">知道如何缓解和恢复面向用户的攻击？</span><span class="sxs-lookup"><span data-stu-id="d8290-106">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="d8290-107">您是否知道您可以使用 Office 365 中已有的安全功能完全完成此操作？</span><span class="sxs-lookup"><span data-stu-id="d8290-107">Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="d8290-108">[office 365 威胁调查和响应](office-365-ti.md)是 office 365 E5 订阅中包含的一系列功能 (作为 office 365 高级威胁防护计划2的一部分)。</span><span class="sxs-lookup"><span data-stu-id="d8290-108">[Office 365 Threat Investigation and Response](office-365-ti.md) is a suite of capabilities included in your Office 365 E5 subscription (as part of Office 365 Advanced Threat Protection Plan 2).</span></span> <span data-ttu-id="d8290-109">Office 365 威胁调查和响应功能已帮助 Microsoft IT 将社会工程活动的平均解决时间降低了 80%, 并将每月的大小写提高了 200%, 与前两个季度相比!</span><span class="sxs-lookup"><span data-stu-id="d8290-109">Office 365 Threat Investigation and Response capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d8290-110">威胁调查和响应功能 (以前称为 office 365 威胁智能) 现在是 office 365 高级威胁防护计划2的一部分, 以及其他威胁防护功能。</span><span class="sxs-lookup"><span data-stu-id="d8290-110">Threat Investigation and Response capabilities (formerly known as Office 365 Threat Intelligence) are now a part of Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="d8290-111">若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="d8290-111">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
<span data-ttu-id="d8290-112">我们最近添加了新功能, 可帮助改进检测和恢复威胁的方式!</span><span class="sxs-lookup"><span data-stu-id="d8290-112">We've recently added new capabilities to help improve how you can detect and recover from threats!</span></span> <span data-ttu-id="d8290-113">下面简单介绍了更新后的威胁调查和响应功能如何提高效率。</span><span class="sxs-lookup"><span data-stu-id="d8290-113">Here's a quick walk through of how the updated Threat investigation and response capabilities can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="d8290-114">检测入侵和威胁</span><span class="sxs-lookup"><span data-stu-id="d8290-114">Detect intrusions and threats</span></span>

<span data-ttu-id="d8290-115">[浏览器](use-explorer-in-security-and-compliance.md)(也称为 "威胁浏览器") 可帮助安全管理员和分析师识别和理解企业中的活动威胁, 因为看似无害的用户配置 (如安全) 可能会规避最复杂的安全设置发件人白名单。</span><span class="sxs-lookup"><span data-stu-id="d8290-115">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists.</span></span> <span data-ttu-id="d8290-116">资源管理器可帮助 Office 365 全局或安全管理员快速确定用户是否已被威胁 (如恶意软件或网络钓鱼诈骗) 所危害。</span><span class="sxs-lookup"><span data-stu-id="d8290-116">Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish.</span></span> <span data-ttu-id="d8290-117">这有助于确定哪些用户最面临威胁的风险以及必需的响应的优先级。</span><span class="sxs-lookup"><span data-stu-id="d8290-117">This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="d8290-118">资源管理器还可帮助管理员导航用户和邮件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d8290-118">Explorer also helps admins navigate the relationships between users and mail.</span></span> <span data-ttu-id="d8290-119">知道有误的特定邮件吗？</span><span class="sxs-lookup"><span data-stu-id="d8290-119">Know of a particular mail that was bad?</span></span> <span data-ttu-id="d8290-120">搜索它以查看哪些用户收到了邮件, 然后按照一系列事件进行操作, 并查看这些用户接下来的操作。</span><span class="sxs-lookup"><span data-stu-id="d8290-120">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="d8290-121">如果尚不具有这些 capabilties, 请[立即试用](https://aka.ms/tryo365threatintel3)!</span><span class="sxs-lookup"><span data-stu-id="d8290-121">If you don't already have these capabilties, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="d8290-122">并[了解有关 Office 365 威胁调查和响应的详细信息](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="d8290-122">And [learn more about Office 365 Threat Investigation and Response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![Office 365 中的威胁资源管理器的屏幕截图, 由恶意软件系列进行颜色编码](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="d8290-124">快速缓解威胁并从威胁中恢复</span><span class="sxs-lookup"><span data-stu-id="d8290-124">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="d8290-125">一旦安全管理员发现了其租户中发生可疑或恶意的问题, 他们就可以使用**事件框架**快速包含和响应该威胁。</span><span class="sxs-lookup"><span data-stu-id="d8290-125">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="d8290-126">通过单击对不需要的邮件进行分组并快速删除用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d8290-126">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="d8290-127">**更新:** 我们已添加了直接从事件框架中删除 (软删除或硬删除) 电子邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="d8290-127">**UPDATE:** We've added the ability to delete (soft or hard delete) emails directly from the Incident Framework.</span></span> <span data-ttu-id="d8290-128">以前的管理员只能将邮件移动到用户的垃圾邮件文件夹, 用户可以在那里恢复项目。</span><span class="sxs-lookup"><span data-stu-id="d8290-128">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="d8290-129">使用新的已发布的删除功能, 现在可以确保永久删除恶意或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="d8290-129">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="d8290-130">如果您还没有这些功能, 请[立即试用](https://aka.ms/tryo365threatintel3)!</span><span class="sxs-lookup"><span data-stu-id="d8290-130">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="d8290-131">并[了解有关 Office 365 威胁调查和响应功能的详细信息](https://aka.ms/readmoreabouto365threatintel)。</span><span class="sxs-lookup"><span data-stu-id="d8290-131">And [learn more about Office 365 Threat Investigation and Response capabilities](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![事件修正的电子邮件列表的屏幕截图](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="d8290-133">利用 Microsoft 的威胁遥测</span><span class="sxs-lookup"><span data-stu-id="d8290-133">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="d8290-134">Office 365 威胁调查和响应功能使用 Microsoft 智能安全图形中的数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="d8290-134">Office 365 Threat Investigation and Response capabilities are powered with data from the Microsoft Intelligent Security Graph.</span></span> <span data-ttu-id="d8290-135">graph 从 1000000000 Windows 设备、450000000000每月 Azure 登录和 400000000000 Office 365 中的每月电子邮件获取最新的威胁信号。</span><span class="sxs-lookup"><span data-stu-id="d8290-135">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="d8290-136">这一无与伦比的威胁信号是为管理员和安全分析员提供了对影响其组织的威胁的完整视图的客户租户的广泛可见性。</span><span class="sxs-lookup"><span data-stu-id="d8290-136">This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
   
## <a name="why-use-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="d8290-137">为什么要使用 Office 365 威胁调查和响应功能？</span><span class="sxs-lookup"><span data-stu-id="d8290-137">Why use Office 365 Threat Investigation and Response capabilities?</span></span>

<span data-ttu-id="d8290-138">Gartner 估计在2017中仅限 $ 90B 用在 cybersecurity 上。</span><span class="sxs-lookup"><span data-stu-id="d8290-138">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity.</span></span> <span data-ttu-id="d8290-139">Sid Deshpande (Gartner 的主要研究分析师) 的报价如下所示: "业界转向检测和响应的方式 .。。</span><span class="sxs-lookup"><span data-stu-id="d8290-139">Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response …</span></span> <span data-ttu-id="d8290-140">发送清除阻止的 futile, 除非将其绑定到检测和响应功能。</span><span class="sxs-lookup"><span data-stu-id="d8290-140">sends a clear message that prevention is futile unless it is tied into a detection and response capability."</span></span> <span data-ttu-id="d8290-141">威胁 investigtion 和响应是每个企业的一系列服务的关键组成部分, 可作为独立服务或作为 Office 365 E5 的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="d8290-141">Threat investigtion and response is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="d8290-142">接下来做什么</span><span class="sxs-lookup"><span data-stu-id="d8290-142">What's Next</span></span>

- <span data-ttu-id="d8290-143">有关此录制的会话中的 Office 365 威胁调查和响应功能的详细信息, 请参阅以下内容:[使用 Office 365 保持在 Cyberattacks 之前](https://myignite.microsoft.com/videos/53723)</span><span class="sxs-lookup"><span data-stu-id="d8290-143">Learn more about Office 365 Threat Investigation and response capabilities  in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="d8290-144">[立即试用 office 365 威胁调查和响应功能, 或立即](https://aka.ms/tryo365threatintel3)开始你的 office E5 试用版!</span><span class="sxs-lookup"><span data-stu-id="d8290-144">[Try out Office 365 Threat Investigation and Response capabilities now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

