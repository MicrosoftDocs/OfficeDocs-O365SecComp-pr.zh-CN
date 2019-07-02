---
title: Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: laurawi
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
ms.openlocfilehash: c8b0815368e80151f8ee55161b9bcbaa98065228
ms.sourcegitcommit: b9d8a43cb3afcdc8820bc9470c5707eff8fc6616
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2019
ms.locfileid: "34852806"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="95de2-103">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="95de2-103">Office 365 threat investigation and response</span></span>

<span data-ttu-id="95de2-104">Office 365 中的威胁调查和响应功能[高级威胁防护](office-365-atp.md)帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户:</span><span class="sxs-lookup"><span data-stu-id="95de2-104">Threat investigation and response capabilities in [Office 365 Advanced Threat Protection](office-365-atp.md) help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="95de2-105">轻松识别、监视和理解攻击</span><span class="sxs-lookup"><span data-stu-id="95de2-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="95de2-106">帮助快速解决 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft 团队中的威胁</span><span class="sxs-lookup"><span data-stu-id="95de2-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="95de2-107">提供见解和知识, 以帮助防止针对其组织的攻击</span><span class="sxs-lookup"><span data-stu-id="95de2-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="95de2-108">对基于严重的电子邮件威胁进行自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="95de2-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="95de2-109">**Office 365 高级威胁防护和威胁调查和响应 (以前称为 Office 365 威胁智能) 现在是 office 365 高级威胁防护计划 2**, 以及中附带的其他威胁防护功能某些订阅, 例如[microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 E5、office 365 A5 等。如果您的组织有一个不包含 Office 365 ATP 的订阅, 则可能会将 ATP 作为加载项进行购买。</span><span class="sxs-lookup"><span data-stu-id="95de2-109">**Office 365 Advanced Threat Protection and Threat Investigation and Response (previously known as Office 365 Threat Intelligence) are now Office 365 Advanced Threat Protection Plan 2**, along with additional threat protection capabilities included in in certain subscriptions, such as [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 E5, Office 365 A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="95de2-110">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="95de2-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="95de2-111">有什么变化？</span><span class="sxs-lookup"><span data-stu-id="95de2-111">What's changing?</span></span>

<span data-ttu-id="95de2-112">以前, Office 365 威胁智能包含在订阅中, 如 Office 365 E5 中。</span><span class="sxs-lookup"><span data-stu-id="95de2-112">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 E5.</span></span> <span data-ttu-id="95de2-113">在这种情况下, 由于威胁调查和响应功能现已成为 Office 365 高级威胁防护计划2的一部分 (在 Office 365 E5 中包含), 因此仍是这样。</span><span class="sxs-lookup"><span data-stu-id="95de2-113">This is still the case, as threat investigation and response capabilities are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 E5).</span></span> 

<span data-ttu-id="95de2-114">此外, Office 365 威胁智能以前可作为 Office 365 for business 客户的附加产品购买。</span><span class="sxs-lookup"><span data-stu-id="95de2-114">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="95de2-115">现在, 这些功能包括在 Office 365 高级威胁防护计划2中 (以及 Office 365 高级威胁防护计划1中的所有功能)。</span><span class="sxs-lookup"><span data-stu-id="95de2-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (along with all the features in Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="95de2-116">若要了解详细信息, 请参阅[Office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="95de2-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="95de2-117">下面是这一切的含义:</span><span class="sxs-lookup"><span data-stu-id="95de2-117">Here's what all this means:</span></span>

- <span data-ttu-id="95de2-118">**如果你的组织已有 Office 365 E5**, 则你已具有高级威胁防护计划 2, 这包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="95de2-118">**If your organization already has Office 365 E5**, then you already have Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span>

- <span data-ttu-id="95de2-119">**如果您的组织以前的 office 365 威胁情报 (但不是 office 365 高级威胁防护) 作为**其他 Office 365 订阅的外接程序, 您现在将拥有 Office 365 高级威胁防护计划 2, 其中包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="95de2-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 2, and this includes threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="95de2-120">**如果贵组织以前的 office 365 高级威胁防护 (而不是 office 365 威胁智能) 作为**其他 Office 365 订阅的附加项, 则现在将拥有 Office 365 高级威胁防护计划1。</span><span class="sxs-lookup"><span data-stu-id="95de2-120">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will now have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="95de2-121">这包括 Office 365 高级威胁防护计划 1, 但不包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="95de2-121">This includes Office 365 Advanced Threat Protection Plan 1, (but not threat investigation and response capabilities).</span></span>

<span data-ttu-id="95de2-122">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="95de2-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="95de2-123">开始使用威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="95de2-123">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="95de2-124">使用以下资源了解有关 Office 365 中的威胁调查和响应功能的详细信息, 以及如何使用它来使组织中的人员更加安全。</span><span class="sxs-lookup"><span data-stu-id="95de2-124">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="95de2-125">[开始使用威胁调查和响应](get-started-with-ti.md)(其中包括有关所需角色的信息)</span><span class="sxs-lookup"><span data-stu-id="95de2-125">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="95de2-126">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="95de2-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)

- [<span data-ttu-id="95de2-127">通过自动化调查和响应 (空气) 功能节省时间和精力</span><span class="sxs-lookup"><span data-stu-id="95de2-127">Save time and effort with Automated Investigation and Response (AIR) capabilities</span></span>](automated-investigation-response-office.md)

- [<span data-ttu-id="95de2-128">使用威胁浏览器 (或实时检测) 来识别和调查电子邮件和文件中的恶意内容</span><span class="sxs-lookup"><span data-stu-id="95de2-128">Use Threat Explorer (or real-time detections) to identify and investigate malicious content in email and files</span></span>](threat-explorer.md)
    
- [<span data-ttu-id="95de2-129">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="95de2-129">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="95de2-130">使用攻击模拟器模拟攻击并提高用户意识</span><span class="sxs-lookup"><span data-stu-id="95de2-130">Use Attack Simulator to simulate attacks and increase user awareness</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="95de2-131">将威胁调查和响应功能与 Microsoft Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="95de2-131">Integrate Threat Investigation and Response capabilities with Microsoft Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="95de2-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="95de2-132">Related topics</span></span>

[<span data-ttu-id="95de2-133">威胁资源管理器视图</span><span class="sxs-lookup"><span data-stu-id="95de2-133">Threat Explorer views</span></span>](threat-explorer-views.md)

[<span data-ttu-id="95de2-134">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="95de2-134">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="95de2-135">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="95de2-135">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="95de2-136">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="95de2-136">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
