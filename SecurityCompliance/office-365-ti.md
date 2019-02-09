---
title: Office 365 威胁智能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
description: 了解高级威胁 Protection 中的威胁智能功能如何帮助您研究针对您的组织的威胁、 响应恶意软件和网络钓鱼，代表您检测到 Office 365 其他攻击和搜索威胁指标。
ms.openlocfilehash: 5dfd0377c4cafe89c5f69ea080f07d04d892329e
ms.sourcegitcommit: c1c41744c2de89c9e172f817c8f73bb0ada81a58
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2019
ms.locfileid: "29792257"
---
# <a name="office-365-threat-intelligence"></a><span data-ttu-id="615cc-103">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="615cc-103">Office 365 Threat Intelligence</span></span>

<span data-ttu-id="615cc-104">在 Office 365 高级威胁保护威胁智能功能帮助安全分析师和管理员保护其组织的 Office 365 用户:</span><span class="sxs-lookup"><span data-stu-id="615cc-104">Threat intelligence capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="615cc-105">方便地标识、 监视和了解攻击</span><span class="sxs-lookup"><span data-stu-id="615cc-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="615cc-106">帮助快速解决威胁在 Exchange Online 和 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="615cc-106">Helping to quickly address threats in Exchange Online and SharePoint Online</span></span>
    
3. <span data-ttu-id="615cc-107">提供见解和知识为了帮助防止针对其组织攻击</span><span class="sxs-lookup"><span data-stu-id="615cc-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="615cc-p101">**威胁智能属于立即在 Office 365 高级威胁保护计划 2 中**，它包含某些订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5，在 Office 365教育 A5 等。如果您的组织具有不包括 Office 365 ATP 的订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="615cc-p101">**Threat Intelligence is now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="615cc-110">有什么变化？</span><span class="sxs-lookup"><span data-stu-id="615cc-110">What's changing?</span></span>

<span data-ttu-id="615cc-p102">以前，订阅，例如 Office 365 企业 E5 中包含 Office 365 威胁智能。这仍是这种情况，尽管威胁智能功能现在是 Office 365 高级威胁保护计划 2 的一部分 （和这包含在 Office 365 企业 E5）。</span><span class="sxs-lookup"><span data-stu-id="615cc-p102">Formerly, Office 365 Threat Intelligence was included in subscriptions, such as Office 365 Enterprise E5. This is still the case, although Threat Intelligence features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="615cc-p103">此外，Office 365 威胁智能作为 Office 365 企业客户的是以前可供购买。现在，威胁智能包含在 Office 365 高级威胁保护计划 2 中。若要了解详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="615cc-p103">In addition, Office 365 Threat Intelligence was formerly available for purchase as an add-on for Office 365 for business customers. Now, Threat Intelligence is included in Office 365 Advanced Threat Protection Plan 2. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="615cc-116">下面是所有这意味着：</span><span class="sxs-lookup"><span data-stu-id="615cc-116">Here's what all this means:</span></span>

- <span data-ttu-id="615cc-117">**如果您的组织已经具有 Office 365 企业 E5**，则您已具有高级威胁保护计划 2，并且这包括威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="615cc-117">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat Intelligence capabilities.</span></span>

- <span data-ttu-id="615cc-p104">**如果您的组织原来作为 Office 365 威胁智能 （但不是 Office 365 高级威胁保护）** 到另一个 Office 365 订阅，则您将具有 Office 365 高级威胁保护计划 2。这包括高级威胁保护和威胁智能功能。</span><span class="sxs-lookup"><span data-stu-id="615cc-p104">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2. This includes Advanced Threat Protection and Threat Intelligence capabilities.</span></span> 

- <span data-ttu-id="615cc-p105">**如果您的组织原来作为 Office 365 高级威胁保护 （但不是 Office 365 威胁智能）** 到另一个 Office 365 订阅，则您将具有 Office 365 高级威胁保护计划 1。这包括高级威胁保护 （但不是威胁智能功能）。</span><span class="sxs-lookup"><span data-stu-id="615cc-p105">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1. This includes Advanced Threat Protection (but not Threat Intelligence capabilities).</span></span>

<span data-ttu-id="615cc-122">有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection 服务说明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="615cc-122">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-intelligence-capabilities"></a><span data-ttu-id="615cc-123">入门威胁智能功能</span><span class="sxs-lookup"><span data-stu-id="615cc-123">Get started with threat intelligence capabilities</span></span>

<span data-ttu-id="615cc-124">使用以下资源可了解有关威胁智能以及如何使用它来使您的组织中的人员更安全的详细信息。</span><span class="sxs-lookup"><span data-stu-id="615cc-124">Use the following resources to learn more about threat intelligence, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="615cc-125">[威胁智能入门](get-started-with-ti.md)（这包括必需的角色的信息）</span><span class="sxs-lookup"><span data-stu-id="615cc-125">[Get started with Threat Intelligence](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="615cc-126">了解威胁跟踪器-新的和值得注意</span><span class="sxs-lookup"><span data-stu-id="615cc-126">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="615cc-127">查找并调查恶意已发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="615cc-127">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="615cc-128">使用攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="615cc-128">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="615cc-129">与 Windows Defender 高级威胁保护集成威胁智能</span><span class="sxs-lookup"><span data-stu-id="615cc-129">Integrate Threat Intelligence with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="615cc-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="615cc-130">Related topics</span></span>

[<span data-ttu-id="615cc-131">Office 365 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="615cc-131">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="615cc-132">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="615cc-132">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="615cc-133">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="615cc-133">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

