---
title: 如何减少 Office 365 中的垃圾邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 了解有助于减少 Office 365 中垃圾邮件的最常用方法。
ms.openlocfilehash: d32cad18cf3972a667f2eb9a11b50d1b12e809a7
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670557"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a><span data-ttu-id="7d940-103">如何减少 Office 365 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7d940-103">How to reduce spam email in Office 365</span></span>

 <span data-ttu-id="7d940-104">**你是否在 Office 365 中收到过多的垃圾邮件？请执行以下操作。**</span><span class="sxs-lookup"><span data-stu-id="7d940-104">**Are you getting too much spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="7d940-p101">我们强烈建议你[使用报告消息加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)报告误报邮件，帮助我们改进筛选器。此外，你可以将邮件*作为附件*转发至 junk@office365.microsoft.com 或 phish@office365.microsoft.com（如果是钓鱼邮件）。</span><span class="sxs-lookup"><span data-stu-id="7d940-p101">We strongly recommend that you report False Negative messages by [using the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. Additionally, you can forward the message *as an attachment* to junk@office365.microsoft.com or phish@office365.microsoft.com (if it was phish).</span></span>

> [!TIP]
> <span data-ttu-id="7d940-p102">如果你认为邮件是垃圾邮件且它位于“垃圾邮件”文件夹中，则这没有问题。如果完全不想在邮箱中看到该邮件，则应更改反垃圾邮件策略以隔离该邮件。有关隔离邮件的更多信息，请参阅[在 Office 365 中隔离电子邮件](quarantine-email-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="7d940-p102">If you think the message is junk and it is in the Junk Email folder, that should not be a problem. If you don't want to see it at all in the mailbox, you should change the antispam policy to quarantine the message. More information on quarantining a message can be found in [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

## <a name="fixing-allowed-spam"></a><span data-ttu-id="7d940-110">修复允许的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="7d940-110">Fixing allowed spam</span></span>

<span data-ttu-id="7d940-p103">我们经常看到客户因配置不正确而使垃圾邮件出现在收件箱中。其中最常见的是在邮件流规则（也称为传输规则）中将域配置为绕过筛选器或者列出允许/安全发件人列表中的域。不推荐这样做，因为这些本应视为垃圾邮件的邮件会跳过垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="7d940-p103">We often see that customers get junk mail into their inbox because of incorrect configurations. The most common of which is configuring your domains in a mail flow rule (also known as a transport rule) to bypass filters or listing your domain(s) in the allowed/safe-senders list. This is not good because these messages skip spam filtering and could have otherwise been caught.</span></span>  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a><span data-ttu-id="7d940-114">其他垃圾邮件过多常见原因的解决方案</span><span class="sxs-lookup"><span data-stu-id="7d940-114">Solutions to other common causes of getting too much spam</span></span>

<span data-ttu-id="7d940-p104">为了让你免受过多垃圾邮件的烦恼，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。</span><span class="sxs-lookup"><span data-stu-id="7d940-p104">In order to protect you from getting too much spam, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="7d940-118">对于管理员</span><span class="sxs-lookup"><span data-stu-id="7d940-118">For admins</span></span>

- <span data-ttu-id="7d940-p105">**让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供最佳保护。请参阅[在管理 DNS 记录时为 Office 365 创建 DNS 记录](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)。</span><span class="sxs-lookup"><span data-stu-id="7d940-p105">**Point your DNS records to Office 365** In order for EOP to provide the best protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. See [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
    
- <span data-ttu-id="7d940-p106">**对所有邮箱都启用垃圾邮件规则**：默认情况下，垃圾邮件筛选操作设为“将邮件移至‘垃圾邮件’文件夹”\*\*\*\*。如果这是当前首选的垃圾邮件策略操作，[还必须对所有邮箱都启用垃圾邮件规则](https://support.office.com/zh-CN/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。若要检查是否已完成此任务，可对一个或多个邮箱运行 Get-MailboxJunkEmailConfiguration cmdlet。例如，若要检查是否已对所有邮箱都启用垃圾邮件规则，可运行下面的命令：Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}。</span><span class="sxs-lookup"><span data-stu-id="7d940-p106">**Enable the junk mail rule on all mailboxes** By default, the spam filtering action is set to **Move message to Junk Email folder**. If this is the preferred and current spam policy action, then each mailbox [must also have the junk mail rule enabled](https://support.office.com/zh-CN/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). To check this, you can run the Get-MailboxJunkEmailConfiguration cmdlet against one or more mailboxes. For example, you might check all mailboxes for this by running the following: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}</span></span>
    
    <span data-ttu-id="7d940-p107">在输出结果中，“Enable”属性应设置为 True。如果设置为 False，可运行 Set-MailboxJunkEmailConfiguration，将它更改为 True。</span><span class="sxs-lookup"><span data-stu-id="7d940-p107">When viewing the output, the Enable property should be set to True. If it is set to False, you can run Set-MailboxJunkEmailConfiguration to change it to True.</span></span>
    
- <span data-ttu-id="7d940-p108">**在本地 Exchange Server 中创建邮件流规则**：如果使用的是 Exchange Online Protection，但邮箱位于本地 Exchange Server 中，必须在本地 Exchange Server 中创建几个邮件流规则。请参阅[面向仅使用 EOP 的客户的说明](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150))。</span><span class="sxs-lookup"><span data-stu-id="7d940-p108">**Create mail flow rules in on-premises Exchange Server** If you are using Exchange Online Protection, but your mailboxes are located in on-premises Exchange Server, then you will need to create a couple of mail flow rules in on-premises Exchange Server. See the [instructions for EOP-only](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).</span></span>
    
- <span data-ttu-id="7d940-p109">**将大量电子邮件标记为“垃圾邮件”**：大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。</span><span class="sxs-lookup"><span data-stu-id="7d940-p109">**Mark bulk email as spam** Bulk email is email which users may have signed up for, but may still be undesirable. In the message header, find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the spam filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values) is handled. You can create different policies or rules for different user preferences.</span></span> 
    
- <span data-ttu-id="7d940-p110">**立即阻止发件人** 在需要立即阻止发件人的情况下，可通过电子邮件地址、域或 IP 地址来阻止。请参阅[使用 EAC 创建邮件流规则来阻止从某个域或用户发送的邮件](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user)。最终用户允许列表中的条目可以覆盖管理员设置的阻止。</span><span class="sxs-lookup"><span data-stu-id="7d940-p110">**Immediately block a sender** In the case where you need to immediately block a sender, you can block by email address, domain, or IP address. See [Use the EAC to create a mail flow rule that blocks messages sent from a domain or user](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user). An entry in an end-user allow list can override a block set by the administrator.</span></span>
    
- <span data-ttu-id="7d940-p111">**为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整可能导致问题出现的任何设置。</span><span class="sxs-lookup"><span data-stu-id="7d940-p111">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
- <span data-ttu-id="7d940-139">**启用 [DKIM](use-dkim-to-validate-outbound-email.md)**，以对出站邮件进行签名，从而增强域和租户内的安全性。</span><span class="sxs-lookup"><span data-stu-id="7d940-139">**Enable [DKIM](use-dkim-to-validate-outbound-email.md)** to sign all your outbound messages to increase the security in your domain and tenant.</span></span>
 > [!TIP]
> <span data-ttu-id="7d940-140">启用 DKIM 后，必须启用 [DMARC](use-dkim-to-validate-outbound-email.md)，这是因为此记录将验证 DKIM 和 SPF 是否正常运行，而且欺骗电子邮件通常没有签名，因为对称私钥和公钥是由 O365 管理。</span><span class="sxs-lookup"><span data-stu-id="7d940-140">After you enable DKIM you must enable [DMARC](use-dkim-to-validate-outbound-email.md) since this record will validate if DKIM and SPF are working correctly and, generally, spoofing emails don't have the signature, since O365 manages your private and public symmetric key.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="7d940-141">对于用户</span><span class="sxs-lookup"><span data-stu-id="7d940-141">For users</span></span>

- <span data-ttu-id="7d940-p112">**启用垃圾邮件规则并检查允许列表**：检查垃圾邮件操作规则是否已启用，并检查发件人或发件人的域是否未在你个人的允许列表中被设为规避筛选。访问这些设置的最佳方法是，转到[“阻止或允许”（垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)中。还可以在其中选择阻止发件人的电子邮件地址或域。</span><span class="sxs-lookup"><span data-stu-id="7d940-p112">**Enable the junk mail rule and check your allow list** Check that the junk mail action rule is enabled and that the sender or sender's domain is not set to bypass in your personal allow list. The best way to access these settings is from [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). While you are there, you may also choose to block the sender's email address or domain.</span></span>
    
- <span data-ttu-id="7d940-p113">**向 Microsoft 举报垃圾邮件**：按照[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)中的说明操作，向 Microsoft 举报垃圾邮件。此外，还可以向 junk@office365.microsoft.com 发送邮件，并附加要举报的一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="7d940-p113">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.</span></span>
    
    <span data-ttu-id="7d940-147">**重要提示**：如果未以附件形式转发邮件，头就会丢失，导致我们无法改进在 Office 365 中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="7d940-147">**Important** If you do not forward the messages as attachments, then the headers will be missing and we will be unable to improve the junk mail filtering in Office 365.</span></span> 
    
- <span data-ttu-id="7d940-p114">**取消订阅大量电子邮件**：如果你申请的邮件（新闻稿、产品公告等）包含来自声誉良好的源的取消订阅链接，建议你直接取消订阅。Office 365 通常不会将这些邮件视为垃圾邮件。你也可以选择阻止发件人，或让管理员更改为将所有大量邮件视为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="7d940-p114">**Unsubscribe from bulk email** If the message was something that you signed up for (newsletters, product announcements, etc.) and contains an unsubscribe link from a reputable source, you may want to simply unsubscribe. Office 365 does not typically treat these messages as spam. You can also choose to block the sender, or ask your administrator to make a change that will cause all bulk mail to be treated as spam.</span></span>
