---
title: 使用 Office 365 威胁调查和响应功能保持组织安全
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
description: 了解 Office 365 威胁调查和响应功能如何帮助您的组织检测入侵和威胁，并快速缓解和恢复威胁。
ms.openlocfilehash: 217203c0bfa29352bc7e1b2b3976f11966034fb0
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761688"
---
# <a name="keep-your-organization-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="748b3-103">使用 Office 365 威胁调查和响应功能保持组织安全</span><span class="sxs-lookup"><span data-stu-id="748b3-103">Keep your organization safe with Office 365 threat investigation and response capabilities</span></span>

<span data-ttu-id="748b3-104">您是否知道您的 Office 365 用户受攻击或更糟的威胁？</span><span class="sxs-lookup"><span data-stu-id="748b3-104">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="748b3-105">知道如何缓解和恢复面向用户的攻击？</span><span class="sxs-lookup"><span data-stu-id="748b3-105">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="748b3-106">您是否知道您可以使用 Office 365 E5 中已有的安全功能完全完成此操作？</span><span class="sxs-lookup"><span data-stu-id="748b3-106">Did you know you can do exactly this with security capabilities that are already available to you in Office 365 E5?</span></span> 
  
<span data-ttu-id="748b3-107">Office 365 中的[威胁调查和响应](office-365-ti.md)功能包含在 Office 365 E5 订阅中（作为[Office 365 高级威胁防护](office-365-atp.md)计划2的一部分）。</span><span class="sxs-lookup"><span data-stu-id="748b3-107">[Office 365 threat investigation and response](office-365-ti.md) capabilities are included in your Office 365 E5 subscription (as part of [Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2).</span></span> <span data-ttu-id="748b3-108">这些功能已帮助 Microsoft IT 缩短了 80% 的社交工程事件的平均解决时间，并显著提高了机箱吞吐量。</span><span class="sxs-lookup"><span data-stu-id="748b3-108">These capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput dramatically.</span></span> <span data-ttu-id="748b3-109">最近添加了新功能，以帮助改进对威胁进行检测和恢复的方式。</span><span class="sxs-lookup"><span data-stu-id="748b3-109">Recently, new capabilities were added to help improve how you can detect and recover from threats.</span></span> <span data-ttu-id="748b3-110">阅读本文，了解威胁调查和响应功能如何帮助安全操作团队更高效、更有效。</span><span class="sxs-lookup"><span data-stu-id="748b3-110">Read this article to see how threat investigation and response capabilities can help your security operations team be more effective and efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="748b3-111">检测入侵和威胁</span><span class="sxs-lookup"><span data-stu-id="748b3-111">Detect intrusions and threats</span></span>

<span data-ttu-id="748b3-112">[威胁资源管理器](threat-explorer.md)（也称为浏览器）可帮助安全管理员和分析师识别和理解组织中处于活动状态的威胁。</span><span class="sxs-lookup"><span data-stu-id="748b3-112">[Threat Explorer](threat-explorer.md) (also referred to as Explorer) helps security administrators and analysts identify and understand threats that are active in your organization.</span></span> <span data-ttu-id="748b3-113">在看似无害的用户配置（如安全-发件人允许列表）中，即使是最复杂的安全设置也是规避的。</span><span class="sxs-lookup"><span data-stu-id="748b3-113">Even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe-sender allow lists.</span></span> <span data-ttu-id="748b3-114">资源管理器可帮助 Office 365 全局或安全管理员快速确定用户是否受到威胁（如恶意软件或网络钓鱼诈骗）的威胁。</span><span class="sxs-lookup"><span data-stu-id="748b3-114">Explorer helps Office 365 global or security administrators quickly determine whether users have been compromised by threats, such as malware or phish.</span></span> <span data-ttu-id="748b3-115">这有助于确定哪些用户帐户对威胁和必要响应的风险最大。</span><span class="sxs-lookup"><span data-stu-id="748b3-115">This helps prioritize which user accounts are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="748b3-116">资源管理器还可帮助管理员导航用户和邮件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="748b3-116">Explorer also helps administrators navigate the relationships between users and mail.</span></span> <span data-ttu-id="748b3-117">知道有误的特定邮件吗？</span><span class="sxs-lookup"><span data-stu-id="748b3-117">Know of a particular mail that was bad?</span></span> <span data-ttu-id="748b3-118">搜索它以查看哪些用户收到了邮件，然后按照一系列事件进行操作，并查看这些用户接下来的操作。</span><span class="sxs-lookup"><span data-stu-id="748b3-118">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

![Office 365 中的威胁资源管理器的屏幕截图，由恶意软件系列进行颜色编码](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="748b3-120">快速缓解威胁并从威胁中恢复</span><span class="sxs-lookup"><span data-stu-id="748b3-120">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="748b3-121">一旦安全管理员发现了其租户中存在可疑或恶意的问题，他们就可以使用**事件框架**快速包含和响应该威胁。</span><span class="sxs-lookup"><span data-stu-id="748b3-121">Once security administrators have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="748b3-122">通过单击对不需要的邮件进行分组并快速删除用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="748b3-122">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="748b3-123">**更新：** 已添加了直接从事件框架中删除（软删除或硬删除）电子邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="748b3-123">**UPDATE:** The ability to delete (soft or hard delete) email messages directly from the Incident framework has been added.</span></span> <span data-ttu-id="748b3-124">以前的管理员只能将邮件移动到用户的垃圾邮件文件夹，用户可以在那里恢复项目。</span><span class="sxs-lookup"><span data-stu-id="748b3-124">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="748b3-125">使用新的已发布的删除功能，现在可以确保永久删除恶意或不需要的邮件。</span><span class="sxs-lookup"><span data-stu-id="748b3-125">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
    
![事件修正的电子邮件列表的屏幕截图](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="748b3-127">利用 Microsoft 的威胁遥测</span><span class="sxs-lookup"><span data-stu-id="748b3-127">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="748b3-128">Office 365 威胁调查和响应功能使用[Microsoft 智能安全图形](https://go.microsoft.com/fwlink/?linkid=2036223)中的数据提供支持。</span><span class="sxs-lookup"><span data-stu-id="748b3-128">Office 365 threat investigation and response capabilities are powered with data from the [Microsoft Intelligent Security Graph](https://go.microsoft.com/fwlink/?linkid=2036223).</span></span> <span data-ttu-id="748b3-129">Graph 从 1000000000 Windows 设备、450000000000每月 Azure 登录和 400000000000 Office 365 中的每月电子邮件获取最新的威胁信号。</span><span class="sxs-lookup"><span data-stu-id="748b3-129">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="748b3-130">这一无与伦比的威胁信号提供了安全操作团队对影响组织的威胁的更完整视图的广泛可见性。</span><span class="sxs-lookup"><span data-stu-id="748b3-130">This unrivaled threat signal is what gives the broad visibility your security operations team have for a more complete view of the threats impacting your organization.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="748b3-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="748b3-131">Next steps</span></span>

- <span data-ttu-id="748b3-132">了解有关[Office 365 高级威胁防护](office-365-atp.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="748b3-132">Learn more about [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>

- <span data-ttu-id="748b3-133">有关此录制的会话中的 Office 365 威胁调查和响应功能的详细信息，请参阅[office 365](https://myignite.microsoft.com/videos/53723)中的 Cyberattacks。</span><span class="sxs-lookup"><span data-stu-id="748b3-133">Learn more about Office 365 threat investigation and response capabilities in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723).</span></span>

- <span data-ttu-id="748b3-134">如果尚无 Office 365 高级威胁防护计划2，请立即试用或购买。</span><span class="sxs-lookup"><span data-stu-id="748b3-134">If you don't already have Office 365 Advanced Threat Protection Plan 2, try or buy it now.</span></span> <span data-ttu-id="748b3-135">请参阅[Office 365 高级威胁防护：计划和定价](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)。</span><span class="sxs-lookup"><span data-stu-id="748b3-135">See [Office 365 Advanced Threat Protection: Plans and pricing](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content).</span></span>
    
- <span data-ttu-id="748b3-136">使用[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)扩展保护。</span><span class="sxs-lookup"><span data-stu-id="748b3-136">Extend protection with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>