---
title: DLP 方式之间的安全&amp;合规性中心和 Exchange 管理中心
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 了解如何在安全的 DLP&amp;合规中心的工作方式与 Exchange 管理员中心中的 DLP 和传输规则一起。
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525681"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="3cb28-103">DLP 方式之间的安全&amp;合规性中心和 Exchange 管理中心</span><span class="sxs-lookup"><span data-stu-id="3cb28-103">How DLP works between the Security &amp; Compliance Center and Exchange Admin Center</span></span>

<span data-ttu-id="3cb28-104">在 Office 365 中，您可以创建两个不同的管理中心中的数据丢失防护 (DLP) 策略：</span><span class="sxs-lookup"><span data-stu-id="3cb28-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="3cb28-p101">在**安全&amp;合规性中心**，您可以创建单个 DLP 策略，以帮助保护 SharePoint、 OneDrive 和 Exchange 中的内容。如果可能，我们建议您创建 DLP 策略。有关详细信息，请参阅[安全中的 DLP&amp;合规性中心](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p101">In the **Security &amp; Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, and Exchange. When possible, we recommend that you create a DLP policy here. For more information, see [DLP in the Security &amp; Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="3cb28-p102">在**Exchange 管理中心**中，您可以创建 DLP 策略来帮助保护仅在 Exchange 中的内容。此策略可以使用 Exchange 传输规则，因此必须处理电子邮件到特定的更多选项。有关详细信息，请参阅[Exchange Admin Center 中的 DLP](https://go.microsoft.com/fwlink/?linkid=852311)。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p102">In the **Exchange Admin Center**, you can create a DLP policy to help protect content only in Exchange. This policy can use Exchange transport rules, so it has more options specific to handling email. For more information, see [DLP in the Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="3cb28-111">DLP 策略中这些管理员创建中心工作并排-本主题介绍如何。</span><span class="sxs-lookup"><span data-stu-id="3cb28-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![安全性和合规性中心以及 Exchange Admin Center 中的 DLP 页面](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a><span data-ttu-id="3cb28-113">如何在安全的 DLP&amp;合规中心的工作方式与 Exchange 管理员中心中的 DLP 和传输规则一起</span><span class="sxs-lookup"><span data-stu-id="3cb28-113">How DLP in the Security &amp; Compliance Center works with DLP and transport rules in the Exchange Admin Center</span></span>

<span data-ttu-id="3cb28-p103">在安全中创建的 DLP 策略后&amp;合规性中心，策略部署到所有策略中包括的位置。如果该策略包括 Exchange Online，该策略的那里同步和实施中在 Exchange 管理中心中创建的 DLP 策略的方式完全相同。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p103">After you create a DLP policy in the Security &amp; Compliance Center, the policy is deployed to all of the locations included in the policy. If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="3cb28-p104">如果您已在 Exchange 管理中心创建 DLP 策略，这些策略将继续工作并排在安全中创建的电子邮件的任何策略&amp;合规性中心。但请注意，在 Exchange 管理中心中创建的规则优先。首先，处理所有 Exchange 传输规则和 DLP 规则从安全的然后&amp;都处理合规性中心。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p104">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security &amp; Compliance Center. But note that rules created in the Exchange admin center take precedence. All Exchange transport rules are processed first, and then the DLP rules from the Security &amp; Compliance Center are processed.</span></span>
  
<span data-ttu-id="3cb28-119">这意味着：</span><span class="sxs-lookup"><span data-stu-id="3cb28-119">This means that:</span></span>
  
- <span data-ttu-id="3cb28-120">通过 Exchange 传输规则阻止的邮件不会扫描在安全中创建的 DLP 规则&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="3cb28-120">Messages that are blocked by Exchange transport rules won't get scanned by DLP rules created in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="3cb28-121">如果 Exchange 传输规则以修改中一种方法，使它在安全性 DLP 策略匹配的邮件&amp;合规性中心-例如添加外部用户-然后 DLP 规则将检测这并根据需要强制执行策略。</span><span class="sxs-lookup"><span data-stu-id="3cb28-121">If an Exchange transport rule modifies a message in a way that causes it to match a DLP policy in the Security &amp; Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="3cb28-122">使用"stop 处理"操作的 Exchange 传输规则不会影响 DLP 处理的注意安全中的规则而且&amp;合规性中心-将仍然处理它们。</span><span class="sxs-lookup"><span data-stu-id="3cb28-122">Also note that Exchange transport rules that use the "stop processing" action don't affect the processing of DLP rules in the Security &amp; Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="3cb28-123">策略提示安全中&amp;与 Exchange 管理员中心的合规性中心</span><span class="sxs-lookup"><span data-stu-id="3cb28-123">Policy tips in the Security &amp; Compliance Center vs. the Exchange Admin Center</span></span>

<span data-ttu-id="3cb28-p105">策略提示可使用 DLP 策略的工作和邮件流规则在 Exchange 管理中心，或在安全中创建的 DLP 策略创建&amp;合规性中心，但不是能同时。这是因为这些策略存储在不同的位置，但只能从单个位置可以绘制策略提示。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p105">Policy tips can work either with DLP policies and mail flow rules created in the Exchange Admin Center, or with DLP policies created in the Security &amp; Compliance Center, but not both. This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="3cb28-p106">如果您已在 Exchange 管理中心，任何安全中配置的策略提示配置策略提示&amp;合规性中心将不会显示向 web 上的 Outlook 和 Outlook 2013 和之前关闭 Exchange 管理中心中的提示，更高版本中的用户。这样可确保您当前的 Exchange 传输规则将继续工作之前您选择切换到安全&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="3cb28-p106">If you've configured policy tips in the Exchange Admin Center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange Admin Center. This ensures that your current Exchange transport rules will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>
  
<span data-ttu-id="3cb28-128">请注意，只能从一个位置，可以绘制策略提示时发送电子邮件通知始终发送，即使您正在使用中的安全性的 DLP 策略&amp;合规性中心和 Exchange Admin Center。</span><span class="sxs-lookup"><span data-stu-id="3cb28-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange Admin Center.</span></span>
  

