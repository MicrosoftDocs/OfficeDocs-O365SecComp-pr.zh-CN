---
title: 批量投诉级别值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: 批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。 一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。 这些邮件使收件人产生少量抱怨。 其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。 为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。 BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。 BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。 Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。 此评级显示在每封邮件的"X-Microsoft-Antispam"标头中。 有关此邮件头的详细信息，请参阅反垃圾邮件邮件头。
ms.openlocfilehash: e6d639098adc8c29b09b186ff72e38c5f5ac4e81
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243813"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="83de8-112">批量投诉级别值</span><span class="sxs-lookup"><span data-stu-id="83de8-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="83de8-113">批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="83de8-113">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="83de8-114">一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。</span><span class="sxs-lookup"><span data-stu-id="83de8-114">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="83de8-115">这些邮件使收件人产生少量抱怨。</span><span class="sxs-lookup"><span data-stu-id="83de8-115">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="83de8-116">其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。</span><span class="sxs-lookup"><span data-stu-id="83de8-116">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="83de8-117">为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。</span><span class="sxs-lookup"><span data-stu-id="83de8-117">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="83de8-118">BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。</span><span class="sxs-lookup"><span data-stu-id="83de8-118">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="83de8-119">BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。</span><span class="sxs-lookup"><span data-stu-id="83de8-119">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="83de8-120">Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。</span><span class="sxs-lookup"><span data-stu-id="83de8-120">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="83de8-121">此分级在每封邮件的**X-Microsoft 反垃圾**邮件头中公开。</span><span class="sxs-lookup"><span data-stu-id="83de8-121">This rating is exposed in the **X-Microsoft-Antispam** header of every message.</span></span> <span data-ttu-id="83de8-122">有关此邮件头的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="83de8-122">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="83de8-123">通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。</span><span class="sxs-lookup"><span data-stu-id="83de8-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="83de8-p103">未来会添加更多的 BCL 值并将包含在此处。下表列出并描述了当前正在使用的 BCL 值。</span><span class="sxs-lookup"><span data-stu-id="83de8-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="83de8-126">**BCL 值**</span><span class="sxs-lookup"><span data-stu-id="83de8-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="83de8-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="83de8-127">**Description**</span></span> <br/> |
|<span data-ttu-id="83de8-128">0</span><span class="sxs-lookup"><span data-stu-id="83de8-128">0</span></span>  <br/> |<span data-ttu-id="83de8-129">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="83de8-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="83de8-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="83de8-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="83de8-131">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="83de8-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="83de8-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="83de8-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="83de8-133">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="83de8-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="83de8-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="83de8-134">8, 9</span></span>  <br/> |<span data-ttu-id="83de8-135">邮件来自于产生大量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="83de8-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

