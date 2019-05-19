---
title: 垃圾邮件可信度
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。
ms.openlocfilehash: 4eba1dc6fa1bbadcfd135a7bf43e7353755df6c4
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158264"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="18d51-106">垃圾邮件可信度</span><span class="sxs-lookup"><span data-stu-id="18d51-106">Spam confidence levels</span></span>

<span data-ttu-id="18d51-p102">当对电子邮件进行垃圾邮件筛选时，将为该邮件分配一个垃圾邮件得分。该得分将被映射到单个垃圾邮件可信度 (SCL) 分级，并标记在 X 标头中。此项服务将基于 SCL 分级的垃圾邮件可信度解释对邮件采取操作。下表显示了筛选器如何解释不同的 SCL 分级，以及为每个分级的入站邮件所采取的默认操作。</span><span class="sxs-lookup"><span data-stu-id="18d51-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="18d51-111">**SCL 分级**</span><span class="sxs-lookup"><span data-stu-id="18d51-111">**SCL Rating**</span></span>|<span data-ttu-id="18d51-112">**垃圾邮件可信度解释**</span><span class="sxs-lookup"><span data-stu-id="18d51-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="18d51-113">**默认操作**</span><span class="sxs-lookup"><span data-stu-id="18d51-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="18d51-114">-1</span><span class="sxs-lookup"><span data-stu-id="18d51-114">-1</span></span>|<span data-ttu-id="18d51-115">来自安全发件人、安全收件人或安全列表 IP 地址 (受信任合作伙伴) 的非垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18d51-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="18d51-116">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="18d51-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="18d51-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="18d51-117">0, 1</span></span>|<span data-ttu-id="18d51-118">非垃圾邮件, 因为邮件已被扫描并确定为干净。</span><span class="sxs-lookup"><span data-stu-id="18d51-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="18d51-119">将邮件传递到收件人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="18d51-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="18d51-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="18d51-120">5, 6</span></span>|<span data-ttu-id="18d51-121">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="18d51-121">Spam</span></span>|<span data-ttu-id="18d51-122">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="18d51-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="18d51-123">7、8、9</span><span class="sxs-lookup"><span data-stu-id="18d51-123">7, 8, 9</span></span>|<span data-ttu-id="18d51-124">可信度高的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="18d51-124">High confidence spam</span></span>|<span data-ttu-id="18d51-125">将邮件传递到收件人的垃圾邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="18d51-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="18d51-126">该服务不设置 SCL 等级2、3、4、7和8。</span><span class="sxs-lookup"><span data-stu-id="18d51-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="18d51-127">SCL 分级为 5 或 6 的邮件被认为是可疑垃圾邮件，比 SCL 分级为 9 的无疑邮件更难以确定是垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18d51-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="18d51-128">可在 Exchange 管理中心通过内容筛选器策略为垃圾邮件和高可信度垃圾邮件配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="18d51-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="18d51-129">有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="18d51-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="18d51-130">您还可以使用邮件流规则 (也称为传输规则) 来设置符合特定条件的邮件的 SCL 分级, 如[使用邮件流规则在邮件中设置垃圾邮件可信度 (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="18d51-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="18d51-131">如果使用邮件流规则将 SCL 设置为7、8或 9, 则邮件将被视为高可信度垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="18d51-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="18d51-p104">![LinkedIn Learning 短图标](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **刚开始接触 Office 365？**         发现 LinkedIn Learning 向 **Office 365 admins and IT pros**提供的免费视频课程。</span><span class="sxs-lookup"><span data-stu-id="18d51-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

