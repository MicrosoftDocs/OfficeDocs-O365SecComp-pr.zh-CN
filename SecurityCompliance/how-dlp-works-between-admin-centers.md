---
title: DLP 在安全&amp;合规中心和 Exchange 管理中心之间如何工作
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解安全&amp;合规性中心中的 dlp 如何在 Exchange 管理中心中使用 dlp 和传输规则。
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215642"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="fe670-103">DLP 在安全&amp;合规中心和 Exchange 管理中心之间如何工作</span><span class="sxs-lookup"><span data-stu-id="fe670-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="fe670-104">在 Office 365 中, 可以在两个不同的管理中心中创建数据丢失防护 (DLP) 策略:</span><span class="sxs-lookup"><span data-stu-id="fe670-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="fe670-p101">在**安全&amp;合规性中心**中, 可以创建一个 DLP 策略来帮助保护 SharePoint、OneDrive 和 Exchange 中的内容。如果可能, 我们建议您在此处创建 DLP 策略。有关详细信息, 请参阅[安全&amp;合规性中心中的 DLP](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fe670-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="fe670-p102">在**exchange 管理中心**中, 可以创建 DLP 策略来帮助保护仅在 Exchange 中的内容。此策略可以使用 Exchange 传输规则, 因此它具有更多特定于处理电子邮件的选项。有关详细信息, 请参阅[Exchange 管理中心中的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。</span><span class="sxs-lookup"><span data-stu-id="fe670-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="fe670-111">在这些管理中心创建的 DLP 策略并排工作-本主题说明了如何操作。</span><span class="sxs-lookup"><span data-stu-id="fe670-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全与合规中心和 Exchange 管理中心中的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="fe670-113">安全&amp;合规中心中的 dlp 如何在 Exchange 管理中心中处理 dlp 和传输规则</span><span class="sxs-lookup"><span data-stu-id="fe670-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="fe670-p103">在安全&amp;合规中心中创建 DLP 策略后, 该策略将部署到策略中包含的所有位置。如果策略包括 exchange Online, 则策略的同步方式与 exchange 管理中心内创建的 DLP 策略完全相同。</span><span class="sxs-lookup"><span data-stu-id="fe670-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="fe670-p104">如果您在 Exchange 管理中心中创建了 DLP 策略, 这些策略将继续与您在安全&amp;合规中心中创建的电子邮件的任何策略并排工作。但请注意, 在 Exchange 管理中心中创建的规则优先。将首先处理所有 Exchange 传输规则, 然后处理来自安全&amp;合规性中心的 DLP 规则。</span><span class="sxs-lookup"><span data-stu-id="fe670-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="fe670-119">这意味着:</span><span class="sxs-lookup"><span data-stu-id="fe670-119">This means that:</span></span>
  
- <span data-ttu-id="fe670-120">Exchange 传输规则阻止的邮件不会通过安全&amp;合规中心中创建的 DLP 规则进行扫描。</span><span class="sxs-lookup"><span data-stu-id="fe670-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="fe670-121">如果 Exchange 传输规则以使其与安全&amp;合规中心中的 DLP 策略匹配的方式 (例如添加外部用户) 修改邮件, 则 DLP 规则将检测此问题并根据需要强制实施策略。</span><span class="sxs-lookup"><span data-stu-id="fe670-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="fe670-122">另请注意, 使用 "停止处理" 操作的 Exchange 传输规则不会影响安全&amp;合规中心中的 DLP 规则处理, 它们仍将被处理。</span><span class="sxs-lookup"><span data-stu-id="fe670-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="fe670-123">安全&amp;合规性中心与 Exchange 管理中心中的策略提示</span><span class="sxs-lookup"><span data-stu-id="fe670-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="fe670-p105">策略提示可使用在 Exchange 管理中心中创建的 dlp 策略和邮件流规则, 或使用在安全&amp;合规性中心中创建的 dlp 策略, 但不能同时使用这两种策略。这是因为这些策略存储在不同的位置, 但策略提示只能从一个位置进行绘制。</span><span class="sxs-lookup"><span data-stu-id="fe670-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="fe670-p106">如果已在 exchange 管理中心中配置了策略提示, 则在安全&amp;合规中心中配置的任何策略提示都不会显示在 web 上的 outlook 和 outlook 2013 及更高版本中的用户, 直到您在 Exchange 管理中心中关闭提示。这样可确保您在选择切换到安全&amp;合规中心之前, 当前的 Exchange 传输规则将继续有效。</span><span class="sxs-lookup"><span data-stu-id="fe670-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="fe670-128">请注意, 虽然策略提示只能从一个位置进行绘制, 但总是会发送电子邮件通知, 即使您在安全&amp;合规中心和 Exchange 管理中心中使用的是 DLP 策略也是如此。</span><span class="sxs-lookup"><span data-stu-id="fe670-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

