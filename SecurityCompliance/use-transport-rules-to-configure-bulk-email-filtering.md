---
title: 使用邮件流规则配置 Exchange Online Protection 中筛选批量电子邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
description: 管理员可以了解如何使用 Exchange Online Protection 中的邮件流规则，以筛选批量电子邮件。
ms.openlocfilehash: ce95872d3d80436dce4c62037caea9a5f735726d
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "27382803"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="aedfa-103">使用邮件流规则配置 Exchange Online Protection 中筛选批量电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="aedfa-p101">您可以使用默认的垃圾邮件内容筛选器策略针对垃圾邮件和批量电子设置公司范围的内容筛选器。请查看[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)和 [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) 以了解如何设置内容筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p101">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies. Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](http://technet.microsoft.com/library/f597aa65-baa7-49d0-8832-2a300073f211.aspx) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="aedfa-p102">如果需要更多选项以筛选批量邮件，您可以创建邮件流规则 （也称作传输规则） 搜索的文本模式或批量电子邮件中常见的短语。包含这些特征任何邮件将被标记为垃圾邮件。使用这些规则可帮助减少您的组织接收的多余的垃圾电子邮件的量。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p102">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails. Any message containing these characteristics will be marked as spam. Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>
  
<span data-ttu-id="aedfa-109">**注意**：</span><span class="sxs-lookup"><span data-stu-id="aedfa-109">**Notes**:</span></span>

- <span data-ttu-id="aedfa-110">创建邮件流规则记录本主题之前，我们建议您先阅读[垃圾邮件和批量邮件之间的区别是什么？](what-s-the-difference-between-junk-email-and-bulk-email.md)和[批量投诉级别值](bulk-complaint-level-values.md)。</span><span class="sxs-lookup"><span data-stu-id="aedfa-110">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span> 
  
- <span data-ttu-id="aedfa-p103">下面的步骤为您的整个组织将邮件标记为垃圾邮件。但是，您可以添加其他条件，以仅将这些规则应用于组织中的特定收件人。通过这种方式，主动批量电子邮件筛选设置可应用于具有高度针对性的一些用户，同时又不影响其余用户（主要接收其注册的批量电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p103">The following procedures mark a message as spam for your entire organization. However, you can add another condition to apply these rules only to specific recipients in your organization. This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
### <a name="create-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="aedfa-114">创建要筛选批量电子邮件根据文本模式的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="aedfa-114">Create mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="aedfa-115">在 Exchange 管理员中心 (EAC) 中，转到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-115">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="aedfa-116">单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-116">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="aedfa-117">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="aedfa-117">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="aedfa-p104">单击**更多选项**。在**以下情况应用此规则**，请选择**主题或正文** \> **主题或正文匹配这些文本模式**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p104">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="aedfa-120">在**指定词语或短语**对话框中，添加以下正则表达式通常在批量电子邮件，一次一台中找到和完成后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="aedfa-120">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="aedfa-121">如果您将无法查看此电子邮件的内容\,请</span><span class="sxs-lookup"><span data-stu-id="aedfa-121">If you are unable to view the content of this email\, please</span></span>
    
   - <span data-ttu-id="aedfa-122">\\>(安全 )?取消订阅( 此处)?\\</a\\></span><span class="sxs-lookup"><span data-stu-id="aedfa-122">\\>(safe )?unsubscribe( here)?\\</a\\></span></span>
    
   - <span data-ttu-id="aedfa-123">如果您不希望接收类似进一步 communications\,请</span><span class="sxs-lookup"><span data-stu-id="aedfa-123">If you do not wish to receive further communications like this\, please</span></span>
    
   - <span data-ttu-id="aedfa-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span><span class="sxs-lookup"><span data-stu-id="aedfa-p105">\\<img height\="?1"? width\="?1"? src\=.?http\://</span></span>
    
   - <span data-ttu-id="aedfa-127">若要停止接收 这些\s+电子邮件\:http\://</span><span class="sxs-lookup"><span data-stu-id="aedfa-127">To stop receiving these\s+emails\:http\://</span></span>
    
   - <span data-ttu-id="aedfa-128">若要取消订阅 \w+ (e\-?信件|e?-?邮件|新闻稿)</span><span class="sxs-lookup"><span data-stu-id="aedfa-128">To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)</span></span>
    
   - <span data-ttu-id="aedfa-129">不再 (愿望 )?(以 )?(发送|接收) \w+ 电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-129">no longer (wish )?(to )?(be sent|receive) \w+ email</span></span>
    
   - <span data-ttu-id="aedfa-130">如果您将无法查看此电子邮件的内容\,，请单击此处</span><span class="sxs-lookup"><span data-stu-id="aedfa-130">If you are unable to view the content of this email\, please click here</span></span>
    
   - <span data-ttu-id="aedfa-131">若要确保收到 (您每日 deals | 我们 e ?mails)\,添加</span><span class="sxs-lookup"><span data-stu-id="aedfa-131">To ensure you receive (your daily deals|our e-?mails)\, add</span></span>
    
   - <span data-ttu-id="aedfa-132">如果您不希望再接收这些电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-132">If you no longer wish to receive these emails</span></span>
    
   - <span data-ttu-id="aedfa-133">若要更改您的 (订阅首选项|首选项或取消订阅)</span><span class="sxs-lookup"><span data-stu-id="aedfa-133">to change your (subscription preferences|preferences or unsubscribe)</span></span>
    
   - <span data-ttu-id="aedfa-134">单击 (此处可|该) 取消订阅</span><span class="sxs-lookup"><span data-stu-id="aedfa-134">click (here to|the) unsubscribe</span></span>
    
   <span data-ttu-id="aedfa-135">**注意**：</span><span class="sxs-lookup"><span data-stu-id="aedfa-135">**Notes**:</span></span>

   - <span data-ttu-id="aedfa-p106">在以上列表不是详尽组批量电子邮件; 中找到的正则表达式可以添加或删除根据需要的详细信息。但是，它是很好的起点。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p106">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
   - <span data-ttu-id="aedfa-p107">搜索单词或主题中的文本模式或消息中的其他标头字段发生从编码方法用来将二进制邮件 ASCII 文本中的 SMTP 服务器之间传输的 MIME 内容传输解码*后*邮件。不能使用条件或例外的原始搜索 (通常是 Base64) 编码的主题或消息中的其他标头字段的值。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p107">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="aedfa-140">在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-140">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="aedfa-141">在**指定 SCL**对话框中，将 SCL 设置为**5**、 **6**或**9**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-141">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="aedfa-p108">将 SCL 设置为 5 或 6 只**垃圾邮件**操作，同时设置到 9 的 SCL**高可信度垃圾邮件**操作，如内容筛选器策略中配置。服务将执行的操作中的内容筛选器策略设置。默认操作是将邮件传递到收件人的垃圾邮件文件夹，但可以配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p108">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="aedfa-145">为邮件流规则匹配项，并将不可用最终用户垃圾邮件隔离邮箱中或通过最终用户，邮件如果您配置的操作是隔离邮件，而不是将其发送给收件人的垃圾邮件文件夹，发送到管理员隔离垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="aedfa-145">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="aedfa-146">有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="aedfa-146">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="aedfa-147">保存规则。</span><span class="sxs-lookup"><span data-stu-id="aedfa-147">Save the rule.</span></span>
    
### <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="aedfa-148">创建筛选批量电子邮件根据短语的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="aedfa-148">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="aedfa-149">在 EAC 中，转到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="aedfa-150">单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)，然后选择**创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-150">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="aedfa-151">指定规则名称。</span><span class="sxs-lookup"><span data-stu-id="aedfa-151">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="aedfa-p109">单击**更多选项**。在**以下情况应用此规则**，请选择**主题或正文** \> **主题或正文中包含以下任何词语**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p109">Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="aedfa-154">在**指定词语或短语**对话框中，添加以下短语通常在批量电子邮件，一次一台中找到和完成后单击**确定**:</span><span class="sxs-lookup"><span data-stu-id="aedfa-154">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - <span data-ttu-id="aedfa-155">更改首选项或取消订阅</span><span class="sxs-lookup"><span data-stu-id="aedfa-155">to change your preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="aedfa-156">修改电子邮件首选项或取消订阅</span><span class="sxs-lookup"><span data-stu-id="aedfa-156">Modify email preferences or unsubscribe</span></span>
    
   - <span data-ttu-id="aedfa-157">这是一封促销电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-157">This is a promotional email</span></span>
    
   - <span data-ttu-id="aedfa-158">由于您申请了订阅，因此向您发送此电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-158">You are receiving this email because you requested a subscription</span></span>
    
   - <span data-ttu-id="aedfa-159">单击此处可取消订阅</span><span class="sxs-lookup"><span data-stu-id="aedfa-159">click here to unsubscribe</span></span>
    
   - <span data-ttu-id="aedfa-160">由于您进行了订阅，因此向您发送了此电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-160">You have received this email because you are subscribed</span></span>
    
   - <span data-ttu-id="aedfa-161">如果您不再希望收到我们的电子邮件新闻稿</span><span class="sxs-lookup"><span data-stu-id="aedfa-161">If you no longer wish to receive our email newsletter</span></span>
    
   - <span data-ttu-id="aedfa-162">取消订阅此新闻稿</span><span class="sxs-lookup"><span data-stu-id="aedfa-162">to unsubscribe from this newsletter</span></span>
    
   - <span data-ttu-id="aedfa-163">如果您在查看此电子邮件时遇到问题</span><span class="sxs-lookup"><span data-stu-id="aedfa-163">If you have trouble viewing this email</span></span>
    
   - <span data-ttu-id="aedfa-164">这是一个广告</span><span class="sxs-lookup"><span data-stu-id="aedfa-164">This is an advertisement</span></span>
    
   - <span data-ttu-id="aedfa-165">您想取消订阅或更改</span><span class="sxs-lookup"><span data-stu-id="aedfa-165">you would like to unsubscribe or change your</span></span>
    
   - <span data-ttu-id="aedfa-166">以网页形式查看此电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-166">view this email as a webpage</span></span>
    
   - <span data-ttu-id="aedfa-167">由于您进行了订阅，因此向您发送此电子邮件</span><span class="sxs-lookup"><span data-stu-id="aedfa-167">You are receiving this email because you are subscribed</span></span>
    
   <span data-ttu-id="aedfa-p110">**注意**： 同样，此列表不是详尽套批量电子邮件; 中找到的短语可以添加或删除根据需要的详细信息。但是，它是很好的起点。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p110">**Note**: Once again, this list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed. However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="aedfa-170">在**执行以下操作**，下选择**修改邮件属性** \> **将垃圾邮件可信度 (SCL) 设置**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-170">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="aedfa-171">在**指定 SCL**对话框中，将 SCL 设置为**5**、 **6**或**9**，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aedfa-171">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="aedfa-p111">将 SCL 设置为 5 或 6 只**垃圾邮件**操作，同时设置到 9 的 SCL**高可信度垃圾邮件**操作，如内容筛选器策略中配置。服务将执行的操作中的内容筛选器策略设置。默认操作是将邮件传递到收件人的垃圾邮件文件夹，但可以配置不同的操作，如[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="aedfa-p111">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="aedfa-175">为邮件流规则匹配项，并将不可用最终用户垃圾邮件隔离邮箱中或通过最终用户，邮件如果您配置的操作是隔离邮件，而不是将其发送给收件人的垃圾邮件文件夹，发送到管理员隔离垃圾邮件通知。</span><span class="sxs-lookup"><span data-stu-id="aedfa-175">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="aedfa-176">有关服务中 SCL 值的详细信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="aedfa-176">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="aedfa-177">保存规则。</span><span class="sxs-lookup"><span data-stu-id="aedfa-177">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="aedfa-178">详细信息</span><span class="sxs-lookup"><span data-stu-id="aedfa-178">For more information</span></span>

[<span data-ttu-id="aedfa-179">垃圾邮件和批量邮件之间有什么差异？</span><span class="sxs-lookup"><span data-stu-id="aedfa-179">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="aedfa-180">批量投诉级别值</span><span class="sxs-lookup"><span data-stu-id="aedfa-180">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="aedfa-181">配置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="aedfa-181">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="aedfa-182">高级垃圾邮件筛选选项</span><span class="sxs-lookup"><span data-stu-id="aedfa-182">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
