---
title: 批量投诉级别值
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/5/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
description: 批量邮件群发程序因其发送模式、内容创建以及列表获取做法的不同而不同。一些是合理的批量邮件群发程序，可以将所需的邮件和相关内容发送到它们的订阅者。这些邮件使收件人产生少量抱怨。其他批量邮件群发程序发送与垃圾邮件极其相似的未经请求的邮件，并且使收件人产生许多抱怨。为了区分这些类型的批量邮件群发程序，会为批量邮件群发程序中的邮件分配批量投诉级别 (BCL) 评级。BCL 评级范围介于 1 到 9 之间，这取决于批量邮件群发程序产生抱怨的可能性大小。BCL 评级为 9 的发件人可能使收件人产生许多抱怨，而 BCL 评级为 3 的发件人产生许多抱怨的可能性较小。Microsoft 使用内部和第三方源识别批量邮件，并确定适当的 BCL。此评级显示在每封邮件的"X-Microsoft-Antispam"标头中。有关此邮件头的详细信息，请参阅反垃圾邮件邮件头。
ms.openlocfilehash: adf179ba4a309f2ed22275179013b576888960c6
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026259"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="aa668-112">批量投诉级别值</span><span class="sxs-lookup"><span data-stu-id="aa668-112">Bulk Complaint Level values</span></span>

<span data-ttu-id="aa668-p102">批量邮件程序在其发送模式，内容创建和邮件列表获取做法不同。一些良好批量广告邮件发送需要的具有向其订阅者的相关内容的邮件。这些邮件从收件人生成几投诉。其他批量邮件程序发送的紧密类似于垃圾邮件并从收件人生成许多投诉垃圾的邮件。为了区分这些类型的批量邮件程序，来自批量邮件程序的邮件是分配给批量投诉级别 (BCL)。BCL 评级范围为 1 到 9，具体取决于如何可能群发是生成的投诉。可能从收件人生成许多投诉发件人已分级 BCL 9，而 BCL 3 的分级不太生成许多投诉。Microsoft 使用内部和第三方源来确定批量邮件，并确定相应的 BCL。**X-Microsoft 的反垃圾邮件**标头的每个邮件中公开此分级。有关此邮件头的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="aa668-p102">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices. Some are good bulk mailers that send wanted messages with relevant content to their subscribers. These messages generate few complaints from recipients. Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients. To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating. BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints. A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints. Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL. This rating is exposed in the **X-Microsoft-Antispam** header of every message. For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
<span data-ttu-id="aa668-123">通过按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的步骤操作，您可以使用 BCL 值设置您组织所需的批量筛选级别。</span><span class="sxs-lookup"><span data-stu-id="aa668-123">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
  
<span data-ttu-id="aa668-p103">未来会添加更多的 BCL 值并将包含在此处。下表列出并描述了当前正在使用的 BCL 值。</span><span class="sxs-lookup"><span data-stu-id="aa668-p103">More BCL values are being added and will be included here in the future. The following table lists and describes the BCL values that are currently in use.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aa668-126">**BCL 值**</span><span class="sxs-lookup"><span data-stu-id="aa668-126">**BCL Value**</span></span> <br/> |<span data-ttu-id="aa668-127">**说明**</span><span class="sxs-lookup"><span data-stu-id="aa668-127">**Description**</span></span> <br/> |
|<span data-ttu-id="aa668-128">0</span><span class="sxs-lookup"><span data-stu-id="aa668-128">0</span></span>  <br/> |<span data-ttu-id="aa668-129">邮件不是由批量发件人发送。</span><span class="sxs-lookup"><span data-stu-id="aa668-129">The message isn't from a bulk sender.</span></span>  <br/> |
|<span data-ttu-id="aa668-130">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="aa668-130">1, 2, 3</span></span>  <br/> |<span data-ttu-id="aa668-131">邮件来自于产生少量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="aa668-131">The message is from a bulk sender that generates few complaints.</span></span>  <br/> |
|<span data-ttu-id="aa668-132">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="aa668-132">4, 5, 6, 7</span></span>  <br/> |<span data-ttu-id="aa668-133">邮件来自于产生各种各样的抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="aa668-133">The message is from a bulk sender that generates a mixed number of complaints.</span></span>  <br/> |
|<span data-ttu-id="aa668-134">8, 9</span><span class="sxs-lookup"><span data-stu-id="aa668-134">8, 9</span></span>  <br/> |<span data-ttu-id="aa668-135">邮件来自于产生大量抱怨的批量发件人。</span><span class="sxs-lookup"><span data-stu-id="aa668-135">The message is from a bulk sender that generates a high number of complaints</span></span>  <br/> |
   

