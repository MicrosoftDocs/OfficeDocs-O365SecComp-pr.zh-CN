---
title: Office 365 威胁智能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: 了解高级威胁防护中的威胁智能功能如何帮助您研究组织的威胁、响应恶意软件、网络钓鱼以及 Office 365 代表您检测到的其他攻击, 并搜索威胁指示器。
ms.openlocfilehash: 81a986c4b47d740313356b22fd1c23bd5e472a24
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241925"
---
# <a name="office-365-threat-intelligence"></a><span data-ttu-id="31695-103">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="31695-103">Office 365 Threat Intelligence</span></span>

<span data-ttu-id="31695-104">Office 365 中的威胁智能功能高级威胁防护帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户:</span><span class="sxs-lookup"><span data-stu-id="31695-104">Threat intelligence capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="31695-105">轻松识别、监视和理解攻击</span><span class="sxs-lookup"><span data-stu-id="31695-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="31695-106">帮助快速解决 Exchange online 和 SharePoint online 中的威胁</span><span class="sxs-lookup"><span data-stu-id="31695-106">Helping to quickly address threats in Exchange Online and SharePoint Online</span></span>
    
3. <span data-ttu-id="31695-107">提供见解和知识, 以帮助防止针对其组织的攻击</span><span class="sxs-lookup"><span data-stu-id="31695-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="31695-p101">**威胁智能现已成为 Office 365 高级威胁防护计划2中的一部分**, 在某些订阅 (如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 Business](https://www.microsoft.com/microsoft-365/business)、office 365 企业版 E5、office 365) 中包含。教育版 A5 等。如果您的组织有一个不包含 Office 365 ATP 的订阅, 则可能会将 atp 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="31695-p101">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="31695-110">有什么变化？</span><span class="sxs-lookup"><span data-stu-id="31695-110">What's changing?</span></span>

<span data-ttu-id="31695-p102">以前, office 365 威胁智能包含在订阅中, 如 office 365 企业版 E5 中。但仍是这样, 尽管威胁智能功能现在是 office 365 高级威胁防护计划2的一部分 (在 office 365 企业版 E5 中包含此功能)。</span><span class="sxs-lookup"><span data-stu-id="31695-p102">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5. This is still the case, although Threat Intelligence features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="31695-p103">此外, office 365 威胁智能以前可作为 office 365 for business 客户的附加产品购买。现在, 威胁智能包含在 Office 365 高级威胁防护计划2中。若要了解详细信息, 请参阅[Office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="31695-p103">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers. Now, Threat Intelligence is included in Office 365 Advanced Threat Protection Plan 2. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="31695-116">下面是这一切的含义:</span><span class="sxs-lookup"><span data-stu-id="31695-116">Here's what all this means:</span></span>

- <span data-ttu-id="31695-117">**如果您的组织已有 Office 365 企业版 E5**, 则您已拥有高级威胁防护计划 2, 其中包括威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="31695-117">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat Intelligence capabilities.</span></span>

- <span data-ttu-id="31695-p104">**如果您的组织以前的 office 365 威胁情报 (但不是 office 365 高级威胁防护) 作为**其他 Office 365 订阅的外接程序, 则您将拥有 office 365 高级威胁防护计划2。这包括高级威胁防护和威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="31695-p104">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2. This includes Advanced Threat Protection and Threat Intelligence capabilities.</span></span> 

- <span data-ttu-id="31695-p105">**如果您的组织以前的 office 365 高级威胁防护 (而不是 office 365 威胁智能) 作为**其他 Office 365 订阅的附加项, 则您将拥有 office 365 高级威胁防护计划1。这包括高级威胁防护 (但不是威胁智能功能)。</span><span class="sxs-lookup"><span data-stu-id="31695-p105">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1. This includes Advanced Threat Protection (but not Threat Intelligence capabilities).</span></span>

<span data-ttu-id="31695-122">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="31695-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-intelligence-capabilities"></a><span data-ttu-id="31695-123">获取威胁智能功能入门</span><span class="sxs-lookup"><span data-stu-id="31695-123">Get started with threat intelligence capabilities</span></span>

<span data-ttu-id="31695-124">使用以下资源了解有关威胁智能的详细信息, 以及如何使用它来使组织中的人员更加安全。</span><span class="sxs-lookup"><span data-stu-id="31695-124">Use the following resources to learn more about threat intelligence, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="31695-125">[威胁智能入门](get-started-with-ti.md)(其中包括有关所需角色的信息)</span><span class="sxs-lookup"><span data-stu-id="31695-125">[Get started with Threat Intelligence](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="31695-126">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="31695-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="31695-127">查找并调查已传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="31695-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="31695-128">使用攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="31695-128">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="31695-129">将威胁智能与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="31695-129">Integrate Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="31695-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="31695-130">Related topics</span></span>

[<span data-ttu-id="31695-131">Office 365 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="31695-131">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="31695-132">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="31695-132">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="31695-133">Office 365 安全&amp;合规中心中的权限</span><span class="sxs-lookup"><span data-stu-id="31695-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

