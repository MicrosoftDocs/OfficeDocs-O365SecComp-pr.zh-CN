---
title: 垃圾邮件和批量邮件之间有什么差异？
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/7/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: 客户有时 askwhat 是垃圾邮件和批量电子邮件之间的区别？本主题旨在说明不同之处, 并提供有关 exchange online 和 exchange online Protection (EOP) 中可用的不同选项的信息。
ms.openlocfilehash: 146cc5654e39441be3544f7ac24bd1300811936f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32266924"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="57841-103">垃圾邮件和批量邮件之间有什么差异？</span><span class="sxs-lookup"><span data-stu-id="57841-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="57841-p101">客户有时会询问"垃圾邮件和批量邮件之间有什么差异？"本主题的目地是说明差异，并提供关于适用于 Exchange Online 和 Exchange Online Protection (EOP) 的不同选项的信息。</span><span class="sxs-lookup"><span data-stu-id="57841-p101">Customers sometimes ask "what's the difference between junk email and bulk email messages?" The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="57841-106">**什么是垃圾邮件？**</span><span class="sxs-lookup"><span data-stu-id="57841-106">**What's junk email?**</span></span>
  
<span data-ttu-id="57841-p102">垃圾邮件是经服务筛选的未经请求的（并且通常是不必要的）电子邮件。默认情况下，服务根据发送 IP 地址的信誉拒绝垃圾邮件。但是，如果邮件通过 IP 检查，但内容筛选器将其归为垃圾邮件，那么该邮件将会被发送到预期收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="57841-p102">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service. By default, the service rejects the spam message based on the reputation of the sending IP address. However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57841-110">对经过内容筛选的邮件执行的操作可通过 Exchange 管理中心 (EAC) 的内容筛选器策略进行配置，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="57841-110">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="57841-111">此外, 如果您不同意垃圾邮件分类, 您可以通过几种方式报告您认为是垃圾邮件或非垃圾邮件的邮件, 如[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交到 microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="57841-111">Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="57841-112">**什么是批量邮件？**</span><span class="sxs-lookup"><span data-stu-id="57841-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="57841-p104">批量邮件也称为灰色邮件，是一种更难分类的电子邮件。垃圾邮件是一种持续性的威胁，而批量邮件通常包含广告或营销信息，不太可能重复向您发送。某些用户希望接收批量邮件，并且他们实际上可能是有意注册以接收这些邮件，而其他用户则可能会将这些类型的邮件视为垃圾邮件。例如，某些用户希望接收来自 Contoso Corporation 的广告电子邮件或参加即将举行的网络安全相关会议的邀请，而其他用户则将此类电子邮件视为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="57841-p104">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify. Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly. Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam. For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="57841-117">如何管理批量邮件</span><span class="sxs-lookup"><span data-stu-id="57841-117">How to manage bulk email</span></span>

<span data-ttu-id="57841-p105">确定如何管理批量邮件并非轻而易举之事，因为如果将批量邮件归为垃圾邮件，那么希望接收这类邮件的用户可能会提出投诉，并将其提交为错误标记为垃圾邮件的误报（非垃圾邮件）邮件。另一方面，如果允许发送所有批量邮件，那么不希望接收这类邮件的用户可能会提出投诉，并将其提交为错误发送到其收件箱的漏报垃圾邮件（假负）。</span><span class="sxs-lookup"><span data-stu-id="57841-p105">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam. On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="57841-120">在内容筛选器策略中启用批量邮件敏感度控件</span><span class="sxs-lookup"><span data-stu-id="57841-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="57841-121">根据您公司有关批量电子邮件的策略，管理员可以选择分配批量电子邮件的阈值。</span><span class="sxs-lookup"><span data-stu-id="57841-121">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email.</span></span> <span data-ttu-id="57841-122">可通过 EAC 中的内容筛选器策略配置该设置。</span><span class="sxs-lookup"><span data-stu-id="57841-122">The setting is configurable via content filter policies in the EAC.</span></span> <span data-ttu-id="57841-123">有关步骤, 请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="57841-123">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) for the steps.</span></span> <span data-ttu-id="57841-124">您可以从1-9 中选择一个阈值设置, 其中1将最大批量电子邮件标记为垃圾邮件, 9 允许传递大多数批量电子邮件。</span><span class="sxs-lookup"><span data-stu-id="57841-124">You can choose a threshold setting from 1-9, where 1 marks most bulk email as spam, and 9 allows most bulk email to be delivered.</span></span> <span data-ttu-id="57841-125">然后，服务执行配置的操作，如将邮件发送到收件人的"垃圾邮件"文件夹。</span><span class="sxs-lookup"><span data-stu-id="57841-125">The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

