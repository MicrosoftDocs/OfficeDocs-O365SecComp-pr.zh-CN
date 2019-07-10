---
title: Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/18/2019
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
description: 了解 Office 365 中的威胁智能功能。高级威胁防护可帮助您研究组织的威胁、响应恶意软件、网络钓鱼和 Office 365 已代表您检测到的其他攻击, 并搜索威胁指示器.
ms.openlocfilehash: 7e0ce37b33ea2c019005585fd70107145fbfc8aa
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598078"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="bfe7d-103">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="bfe7d-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="bfe7d-104">Office 365 中的威胁调查和响应功能[高级威胁防护](office-365-atp.md)帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户:</span><span class="sxs-lookup"><span data-stu-id="bfe7d-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="bfe7d-105">轻松识别、监视和理解攻击</span><span class="sxs-lookup"><span data-stu-id="bfe7d-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="bfe7d-106">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 团队中的威胁</span><span class="sxs-lookup"><span data-stu-id="bfe7d-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="bfe7d-107">提供见解和知识, 以帮助防止针对其组织的攻击</span><span class="sxs-lookup"><span data-stu-id="bfe7d-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="bfe7d-108">对基于严重的电子邮件威胁进行自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="bfe7d-108">Automated investigation and response for critical email based threats</span></span>
    
 
## <a name="whats-changing"></a><span data-ttu-id="bfe7d-109">有什么变化？</span><span class="sxs-lookup"><span data-stu-id="bfe7d-109">What's changing?</span></span>

<span data-ttu-id="bfe7d-110">以前, Office 365 威胁智能包含在订阅中, 如 Office 365 E5 中。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-110">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="bfe7d-111">在这种情况下, 由于威胁调查和响应功能现已成为 Office 365 高级威胁防护计划2的一部分 (在 Office 365 E5 中包含), 因此仍是这样。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-111">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="bfe7d-112">此外, Office 365 威胁智能以前可作为 Office 365 for business 客户的附加产品购买。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-112">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="bfe7d-113">现在, 这些功能包括在 Office 365 高级威胁防护计划2中 (以及 Office 365 高级威胁防护计划1中的所有功能)。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-113">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="bfe7d-114">若要了解详细信息, 请参阅[Office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-114">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="bfe7d-115">下面是这一切的含义:</span><span class="sxs-lookup"><span data-stu-id="bfe7d-115">Here's what all this means:</span></span>

- <span data-ttu-id="bfe7d-116">**如果你的组织已有 Office 365 E5**, 则你已具有高级威胁防护计划 2, 这包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-116">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="bfe7d-117">**如果您的组织以前的 office 365 威胁情报 (但不是 office 365 高级威胁防护) 作为**其他 Office 365 订阅的外接程序, 您现在将拥有 Office 365 高级威胁防护计划 2, 其中包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-117">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="bfe7d-118">**如果贵组织以前的 office 365 高级威胁防护 (而不是 office 365 威胁智能) 作为**其他 Office 365 订阅的附加项, 则现在将拥有 Office 365 高级威胁防护计划1。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-118">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="bfe7d-119">这包括 Office 365 高级威胁防护计划 1, 但不包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-119">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="bfe7d-120">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="bfe7d-120">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="bfe7d-121">开始使用威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="bfe7d-121">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="bfe7d-122">使用以下资源了解有关 Office 365 中的威胁调查和响应功能的详细信息, 以及如何使用它来使组织中的人员更加安全。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-122">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="bfe7d-123">[开始使用威胁调查和响应](get-started-with-ti.md)(其中包括有关所需角色的信息)</span><span class="sxs-lookup"><span data-stu-id="bfe7d-123">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="bfe7d-124">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="bfe7d-124">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="bfe7d-125">通过自动化调查和响应 (空气) 功能节省时间和精力</span><span class="sxs-lookup"><span data-stu-id="bfe7d-125">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="bfe7d-126">使用威胁浏览器 (或实时检测) 来识别和调查电子邮件和文件中的恶意内容</span><span class="sxs-lookup"><span data-stu-id="bfe7d-126">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="bfe7d-127">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="bfe7d-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="bfe7d-128">使用攻击模拟器模拟攻击并提高用户意识</span><span class="sxs-lookup"><span data-stu-id="bfe7d-128">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="bfe7d-129">将威胁调查和响应功能与 Microsoft Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="bfe7d-129">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="bfe7d-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="bfe7d-130">Related topics</span></span>

[<span data-ttu-id="bfe7d-131">威胁资源管理器视图</span><span class="sxs-lookup"><span data-stu-id="bfe7d-131">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="bfe7d-132">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="bfe7d-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="bfe7d-133">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="bfe7d-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="bfe7d-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="bfe7d-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
