---
title: Office 365 威胁调查和响应
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/09/2019
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
description: 了解 office 365 中的威胁智能功能。高级威胁防护可帮助您研究组织的威胁、响应恶意软件、网络钓鱼和 Office 365 已代表您检测到的其他攻击, 并搜索威胁指示器.
ms.openlocfilehash: 54dbe4cc39456189bca2af71294d181adce6f50b
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639029"
---
# <a name="office-365-threat-investigation-and-response"></a><span data-ttu-id="54a16-103">Office 365 威胁调查和响应</span><span class="sxs-lookup"><span data-stu-id="54a16-103">Office 365 Threat Investigation and Response</span></span>

<span data-ttu-id="54a16-104">Office 365 中的威胁调查和响应功能高级威胁防护帮助安全分析员和管理员通过以下方式保护组织的 Office 365 用户:</span><span class="sxs-lookup"><span data-stu-id="54a16-104">Threat investigation and response capabilities in Office 365 Advanced Threat Protection help security analysts and administrators protect their organization's Office 365 users by:</span></span>
  
1. <span data-ttu-id="54a16-105">轻松识别、监视和理解攻击</span><span class="sxs-lookup"><span data-stu-id="54a16-105">Making it easy to identify, monitor and understand attacks</span></span>
    
2. <span data-ttu-id="54a16-106">帮助快速解决 Exchange online、SharePoint online、OneDrive for business 和 Microsoft 团队中的威胁</span><span class="sxs-lookup"><span data-stu-id="54a16-106">Helping to quickly address threats in Exchange Online, SharePoint Online, OneDrive for Business and Microsoft Teams</span></span>
    
3. <span data-ttu-id="54a16-107">提供见解和知识, 以帮助防止针对其组织的攻击</span><span class="sxs-lookup"><span data-stu-id="54a16-107">Providing insights and knowledge to help prevent attacks against their organization</span></span>

4. <span data-ttu-id="54a16-108">对基于严重的电子邮件威胁进行自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="54a16-108">Automated investigation and response for critical email based threats</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="54a16-109">**office 365 高级威胁防护和威胁调查和响应 (以前称为 Office 365 威胁智能) 现在是 office 365 高级威胁防护计划2中的一部分**, 其中包括在某些订阅中, 例如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、office 365 企业版 E5、office 365 教育版 A5 等。如果您的组织有一个不包含 Office 365 ATP 的订阅, 则可能会将 atp 作为加载项进行购买。</span><span class="sxs-lookup"><span data-stu-id="54a16-109">**Office 365 Advanced Threat Protection and Threat Investigation and Responses (previously known as Office 365 Threat Intelligence) are now part of in Office 365 Advanced Threat Protection Plan 2**, which is included in in certain subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has a subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on.</span></span> <span data-ttu-id="54a16-110">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)。</span><span class="sxs-lookup"><span data-stu-id="54a16-110">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp).</span></span> 
  
## <a name="whats-changing"></a><span data-ttu-id="54a16-111">有什么变化？</span><span class="sxs-lookup"><span data-stu-id="54a16-111">What's changing?</span></span>

<span data-ttu-id="54a16-112">以前, office 365 威胁调查和响应功能包含在订阅中, 如 office 365 企业版 E5 中。</span><span class="sxs-lookup"><span data-stu-id="54a16-112">Formerly, Office 365 Threat investigation and responses capabilities were included in subscriptions, such as Office 365 Enterprise E5.</span></span> <span data-ttu-id="54a16-113">但现在, 这些功能现在是 office 365 高级威胁防护计划2的一部分 (这包括在 office 365 企业版 E5 中)。</span><span class="sxs-lookup"><span data-stu-id="54a16-113">This is still the case, and now these features are now part of Office 365 Advanced Threat Protection Plan 2 (and this is included in Office 365 Enterprise E5).</span></span> 

<span data-ttu-id="54a16-114">此外, office 365 威胁调查和响应功能以前可作为 office 365 for business 客户的附加产品购买。</span><span class="sxs-lookup"><span data-stu-id="54a16-114">In addition, Office 365 Threat investigation and response capabilities were formerly available for purchase as an add-on for Office 365 for business customers.</span></span> <span data-ttu-id="54a16-115">现在, 这些功能包括在 office 365 高级威胁防护计划 2 (也包括 office 365 高级威胁防护计划 1)。</span><span class="sxs-lookup"><span data-stu-id="54a16-115">Now, these capabilities are included in Office 365 Advanced Threat Protection Plan 2 (which also includes Office 365 Advanced Threat Protection Plan 1).</span></span> <span data-ttu-id="54a16-116">若要了解详细信息, 请参阅[Office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="54a16-116">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection).</span></span>

<span data-ttu-id="54a16-117">下面是这一切的含义:</span><span class="sxs-lookup"><span data-stu-id="54a16-117">Here's what all this means:</span></span>

- <span data-ttu-id="54a16-118">**如果您的组织已有 Office 365 企业版 E5**, 则您已具有高级威胁防护计划 2, 其中包括威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="54a16-118">**If your organization already has Office 365 Enterprise E5**, then you already have Advanced Threat Protection Plan 2, and this includes Threat investigation and response capabilities.</span></span>

- <span data-ttu-id="54a16-119">**如果您的组织以前的 office 365 威胁情报 (但不是 office 365 高级威胁防护) 作为**其他 Office 365 订阅的外接程序, 则您将拥有 office 365 高级威胁防护计划2。</span><span class="sxs-lookup"><span data-stu-id="54a16-119">**If your organization previously had Office 365 Threat Intelligence (but not Office 365 Advanced Threat Protection) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 2.</span></span> <span data-ttu-id="54a16-120">这包括 Office 365 高级威胁防护计划1和威胁调查和响应功能。</span><span class="sxs-lookup"><span data-stu-id="54a16-120">This includes Office 365 Advanced Threat Protection Plan 1 and Threat investigation and response capabilities.</span></span> 

- <span data-ttu-id="54a16-121">**如果您的组织以前的 office 365 高级威胁防护 (而不是 office 365 威胁智能) 作为**其他 Office 365 订阅的附加项, 则您将拥有 office 365 高级威胁防护计划1。</span><span class="sxs-lookup"><span data-stu-id="54a16-121">**If your organization previously had Office 365 Advanced Threat Protection (but not Office 365 Threat Intelligence) as an add-on** to another Office 365 subscription, then you will have Office 365 Advanced Threat Protection Plan 1.</span></span> <span data-ttu-id="54a16-122">这包括 Office 365 高级威胁防护 (但不是威胁调查和响应功能)。</span><span class="sxs-lookup"><span data-stu-id="54a16-122">This includes Office 365 Advanced Threat Protection (but not Threat investigation and response capabilities).</span></span>

<span data-ttu-id="54a16-123">有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span><span class="sxs-lookup"><span data-stu-id="54a16-123">For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)</span></span>

## <a name="get-started-with-threat-investigation-and-response-capabilities"></a><span data-ttu-id="54a16-124">开始使用威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="54a16-124">Get started with threat investigation and response capabilities</span></span>

<span data-ttu-id="54a16-125">使用以下资源了解有关 Office 365 中的威胁调查和响应功能的详细信息, 以及如何使用它来使组织中的人员更加安全。</span><span class="sxs-lookup"><span data-stu-id="54a16-125">Use the following resources to learn more about threat investigation and response capabilities in Office 365, and how you can use it to keep people in your organization safer.</span></span>
  
- <span data-ttu-id="54a16-126">[开始使用威胁调查和响应](get-started-with-ti.md)(其中包括有关所需角色的信息)</span><span class="sxs-lookup"><span data-stu-id="54a16-126">[Get started with Threat Investigation and Response](get-started-with-ti.md) (this includes information about required roles)</span></span> 
    
- [<span data-ttu-id="54a16-127">了解威胁跟踪-新增和值得注意的事项</span><span class="sxs-lookup"><span data-stu-id="54a16-127">Learn about Threat Trackers - New and Noteworthy</span></span>](threat-trackers.md)
    
- [<span data-ttu-id="54a16-128">查找并调查已传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="54a16-128">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
    
- [<span data-ttu-id="54a16-129">使用攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="54a16-129">Use Attack Simulator</span></span>](attack-simulator.md)
    
- [<span data-ttu-id="54a16-130">将威胁调查和响应与 Windows Defender 高级威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="54a16-130">Integrate Threat Investigation and Response with Windows Defender Advanced Threat Protection</span></span>](integrate-office-365-ti-with-wdatp.md)
    
## <a name="related-topics"></a><span data-ttu-id="54a16-131">相关主题</span><span class="sxs-lookup"><span data-stu-id="54a16-131">Related topics</span></span>

[<span data-ttu-id="54a16-132">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="54a16-132">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="54a16-133">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="54a16-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="54a16-134">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="54a16-134">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
 
