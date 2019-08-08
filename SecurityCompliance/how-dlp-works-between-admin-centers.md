---
title: DLP 在安全与合规中心和 Exchange 管理中心中之间的工作原理
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全 & 合规中心中的 DLP 如何与 Exchange 管理中心中的 DLP 和邮件流规则 (传输规则) 结合使用。
ms.openlocfilehash: 65df871361eca66dca543cd2a6dcb0a529446169
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230616"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="822da-103">DLP 在安全与合规中心和 Exchange 管理中心中之间的工作原理</span><span class="sxs-lookup"><span data-stu-id="822da-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="822da-104">在 Office 365 中, 可以在两个不同的管理中心中创建数据丢失防护 (DLP) 策略:</span><span class="sxs-lookup"><span data-stu-id="822da-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="822da-105">在**安全 & 合规性中心**中, 您可以创建一个 DLP 策略来帮助保护 SharePoint、OneDrive、Exchange 和 Microsoft 团队中的内容。</span><span class="sxs-lookup"><span data-stu-id="822da-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="822da-106">如果可能, 我们建议您在此处创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="822da-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="822da-107">有关详细信息, 请参阅[Security & 合规性中心中的 DLP](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="822da-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="822da-108">在**exchange 管理中心**中, 可以创建 DLP 策略来帮助保护仅在 Exchange 中的内容。</span><span class="sxs-lookup"><span data-stu-id="822da-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="822da-109">此策略可以使用 Exchange 邮件流规则 (也称为传输规则), 因此它具有特定于处理电子邮件的更多选项。</span><span class="sxs-lookup"><span data-stu-id="822da-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="822da-110">有关详细信息, 请参阅[Exchange 管理中心中的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。</span><span class="sxs-lookup"><span data-stu-id="822da-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="822da-111">在这些管理中心创建的 DLP 策略并排工作-本主题说明了如何操作。</span><span class="sxs-lookup"><span data-stu-id="822da-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全与合规中心和 Exchange 管理中心中的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="822da-113">安全 & 合规中心中的 DLP 如何在 Exchange 管理中心中处理 DLP 和邮件流规则</span><span class="sxs-lookup"><span data-stu-id="822da-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="822da-114">在安全 & 合规中心中创建 DLP 策略后, 该策略将部署到策略中包含的所有位置。</span><span class="sxs-lookup"><span data-stu-id="822da-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="822da-115">如果策略包括 Exchange Online, 则策略的同步方式与 Exchange 管理中心内创建的 DLP 策略完全相同。</span><span class="sxs-lookup"><span data-stu-id="822da-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="822da-116">如果您在 Exchange 管理中心中创建了 DLP 策略, 则这些策略将继续与您在安全 & 合规中心中创建的电子邮件的任何策略并排工作。</span><span class="sxs-lookup"><span data-stu-id="822da-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="822da-117">但请注意, 在 Exchange 管理中心中创建的规则优先。</span><span class="sxs-lookup"><span data-stu-id="822da-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="822da-118">首先处理所有 Exchange 邮件流规则, 然后处理安全性 & 合规性中心中的 DLP 规则。</span><span class="sxs-lookup"><span data-stu-id="822da-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="822da-119">这意味着:</span><span class="sxs-lookup"><span data-stu-id="822da-119">This means that:</span></span>
  
- <span data-ttu-id="822da-120">由 Exchange 邮件流规则阻止的邮件不会通过在安全 & 合规中心中创建的 DLP 规则进行扫描。</span><span class="sxs-lookup"><span data-stu-id="822da-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="822da-121">如果 Exchange 邮件流规则以使其与安全 & 合规中心中的 DLP 策略匹配的方式 (例如添加外部用户) 修改邮件, 则 DLP 规则将检测此问题并根据需要强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="822da-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="822da-122">另请注意, 使用 "停止处理" 操作的 Exchange 邮件流规则不会影响安全 & 合规中心中的 DLP 规则处理, 它们仍将被处理。</span><span class="sxs-lookup"><span data-stu-id="822da-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="822da-123">安全 & 合规性中心与 Exchange 管理中心中的策略提示</span><span class="sxs-lookup"><span data-stu-id="822da-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="822da-124">策略提示可使用在 Exchange 管理中心中创建的 DLP 策略和邮件流规则, 或使用在安全 & 合规性中心中创建的 DLP 策略, 但不能同时使用这两种策略。</span><span class="sxs-lookup"><span data-stu-id="822da-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="822da-125">这是因为这些策略存储在不同的位置, 但策略提示只能从一个位置进行绘制。</span><span class="sxs-lookup"><span data-stu-id="822da-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="822da-126">如果已在 Exchange 管理中心中配置了策略提示, 则在安全 & 合规性中心中配置的任何策略提示都不会显示在 web 上的 Outlook 和 Outlook 2013 及更高版本中, 直到您关闭 Exchange 管理中心中的提示。</span><span class="sxs-lookup"><span data-stu-id="822da-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="822da-127">这样可确保您当前的 Exchange 邮件流规则将继续运行, 直到您选择切换到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="822da-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="822da-128">请注意, 虽然策略提示只能从一个位置进行绘制, 但总是发送电子邮件通知, 即使您在安全 & 合规中心和 Exchange 管理中心中使用的是 DLP 策略也是如此。</span><span class="sxs-lookup"><span data-stu-id="822da-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

