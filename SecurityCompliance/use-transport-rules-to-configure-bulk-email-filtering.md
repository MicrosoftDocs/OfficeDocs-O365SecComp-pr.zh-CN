---
title: 使用邮件流规则在 Exchange Online Protection 中配置批量电子邮件筛选
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用 Exchange Online Protection 中的邮件流规则进行批量电子邮件筛选。
ms.openlocfilehash: b7144f16df3e7b9f90a24f1ac224ccb20287d918
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275682"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="e0d24-103">使用邮件流规则在 Exchange Online Protection 中配置批量电子邮件筛选</span><span class="sxs-lookup"><span data-stu-id="e0d24-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="e0d24-p101">您可以使用默认的垃圾邮件内容筛选器策略针对垃圾邮件和批量电子设置公司范围的内容筛选器。请查看[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)和 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) 以了解如何设置内容筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="e0d24-p102">如果您想要更多的选项筛选批量邮件, 则可以创建邮件流规则 (也称为传输规则), 以搜索批量电子邮件中经常找到的文本模式或短语。包含这些特征的任何邮件都将被标记为垃圾邮件。使用这些规则有助于减少组织收到的不需要的批量电子邮件的数量。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0d24-109">在创建已记录的邮件流规则之前, 我们建议您先阅读[垃圾邮件和批量电子邮件之间的区别](what-s-the-difference-between-junk-email-and-bulk-email.md)和[批量投诉级别值](bulk-complaint-level-values.md)之间的区别。</span><span class="sxs-lookup"><span data-stu-id="e0d24-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br><span data-ttu-id="e0d24-p103">下面的步骤为您的整个组织将邮件标记为垃圾邮件。但是，您可以添加其他条件，以仅将这些规则应用于组织中的特定收件人。通过这种方式，主动批量电子邮件筛选设置可应用于具有高度针对性的一些用户，同时又不影响其余用户（主要接收其注册的批量电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p103"> The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="e0d24-113">创建邮件流规则, 以根据文本模式筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="e0d24-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="e0d24-114">在 Exchange 管理中心 (EAC) 中, 转到 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="e0d24-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e0d24-115">单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="e0d24-115">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e0d24-116">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="e0d24-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e0d24-p104">单击 "**更多选项**"。在 "**应用此规则**" 下, 选择 **"主题" 或 "正文** \> "**主题或正文与这些文本模式相匹配**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="e0d24-119">在 "**指定词语或短语**" 对话框中, 添加以下通常在批量电子邮件中找到的正则表达式 (一次一个), 然后在完成后单击 **"确定"** :</span><span class="sxs-lookup"><span data-stu-id="e0d24-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="e0d24-p105">上述列表不是批量电子邮件中找到的一组详尽的正则表达式;可以根据需要添加或删除更多内容。但是, 它是一个很棒的起点。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p105">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span><br><span data-ttu-id="e0d24-p106">在邮件从用于在 ASCII 文本中的 SMTP 服务器之间传输二进制邮件的 MIME 内容传输编码方法解码*之后*, 将在邮件中的主题或其他标头字段中搜索单词或文本模式。不能使用条件或例外来搜索邮件中的主题或其他标头字段的原始 (通常为 Base64) 编码值。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p106">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="e0d24-124">在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="e0d24-125">在 "**指定 scl** " 对话框中, 将 SCL 设置为 " **5**"、" **6**" 或 " **9**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="e0d24-p107">将 scl 设置为5或6将接受**垃圾邮件**操作, 而将 scl 设置为9会采用内容筛选器策略中配置的**高可信度垃圾邮件**操作。该服务将执行内容筛选器策略中的操作集。默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹, 但可以按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的说明配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="e0d24-129">如果配置的操作是隔离邮件, 而不是将其发送到收件人的 "垃圾邮件" 文件夹, 则邮件将作为邮件流规则的匹配项发送到管理员隔离区, 并且不会在最终用户垃圾邮件隔离中或通过最终用户使用垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e0d24-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="e0d24-130">有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d24-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="e0d24-131">保存规则。</span><span class="sxs-lookup"><span data-stu-id="e0d24-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="e0d24-132">创建邮件流规则以根据短语筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="e0d24-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="e0d24-133">在 EAC 中, 转到 "**邮件流** \> **规则**"。</span><span class="sxs-lookup"><span data-stu-id="e0d24-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="e0d24-134">单击 "**添加** !["](media/ITPro-EAC-AddIcon.gif) "添加" 图标, 然后选择 "**创建新规则**"。</span><span class="sxs-lookup"><span data-stu-id="e0d24-134">Click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="e0d24-135">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="e0d24-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="e0d24-p108">单击 "**更多选项**"。在 "在**以下情况应用此规则**" 下, 选择 **"主题" 或 "正文** \> "**主题或正文包含以下任何词语**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p108">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="e0d24-138">在 "**指定词语或短语**" 对话框中, 添加以下在批量电子邮件中常用的短语, 一次添加一个, 然后在完成后单击 **"确定"** :</span><span class="sxs-lookup"><span data-stu-id="e0d24-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="e0d24-p109">此列表不是批量电子邮件中找到的一组详尽的短语。可以根据需要添加或删除更多内容。但是, 它是一个很棒的起点。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p109">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="e0d24-141">在 "**执行以下操作**" 下, 选择 "**修改邮件属性** \> **" "设置垃圾邮件可信度 (SCL)"**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="e0d24-142">在 "**指定 scl** " 对话框中, 将 SCL 设置为 " **5**"、" **6**" 或 " **9**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e0d24-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="e0d24-p110">将 scl 设置为5或6将接受**垃圾邮件**操作, 而将 scl 设置为9会采用内容筛选器策略中配置的**高可信度垃圾邮件**操作。该服务将执行内容筛选器策略中的操作集。默认操作是将邮件传递到收件人的 "垃圾邮件" 文件夹, 但可以按照[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中的说明配置不同的操作。</span><span class="sxs-lookup"><span data-stu-id="e0d24-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="e0d24-146">如果配置的操作是隔离邮件, 而不是将其发送到收件人的 "垃圾邮件" 文件夹, 则邮件将作为邮件流规则的匹配项发送到管理员隔离区, 并且不会在最终用户垃圾邮件隔离中或通过最终用户使用垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e0d24-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="e0d24-147">有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e0d24-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="e0d24-148">保存规则。</span><span class="sxs-lookup"><span data-stu-id="e0d24-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="e0d24-149">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0d24-149">For more information</span></span>

[<span data-ttu-id="e0d24-150">垃圾邮件和批量邮件之间有什么差异？</span><span class="sxs-lookup"><span data-stu-id="e0d24-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="e0d24-151">批量投诉级别值</span><span class="sxs-lookup"><span data-stu-id="e0d24-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="e0d24-152">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="e0d24-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="e0d24-153">高级垃圾邮件筛选选项</span><span class="sxs-lookup"><span data-stu-id="e0d24-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
