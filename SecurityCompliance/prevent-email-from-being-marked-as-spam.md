---
title: 如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: 了解如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”。
ms.openlocfilehash: f7ba560b4eb30abcda4c97617ead883659558bd8
ms.sourcegitcommit: 6d72cdb882b93edf6dfddb5ff2e6d8a16e2fa0bc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25596715"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="f0910-103">如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”</span><span class="sxs-lookup"><span data-stu-id="f0910-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="f0910-104">**真实电子邮件是否在 Office 365 中被标记为“垃圾邮件”？试试本文中介绍的方法吧。**</span><span class="sxs-lookup"><span data-stu-id="f0910-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="f0910-p101">Exchange Online Protection (EOP) 旨在筛选掉垃圾邮件，让收件箱中没有用户不想看到的内容。但有时 EOP 筛选掉的内容却是用户想看到的。</span><span class="sxs-lookup"><span data-stu-id="f0910-p101">Exchange Online Protection (EOP) attempts to filter out spam, keeping your Inbox clear of content that users don't want to see. But sometimes, EOP filters out things that you do want to see.</span></span>
  
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="f0910-107">确定邮件被标记为“垃圾邮件”的原因</span><span class="sxs-lookup"><span data-stu-id="f0910-107">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="f0910-p102">Office 365 中的许多垃圾邮件问题都可以这样解决：[查看电子邮件的邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)，并确定哪里出错。如果 X-Forefront-Antispam-Report 邮件头包含字符串 SFV:NSPM，表明 Exchange Online Protection (EOP) 扫描了邮件，并认为它不是垃圾邮件。在这种情况下，强烈建议[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，帮助我们改进筛选器。如果头中没有此值，可能表明邮件未通过垃圾邮件扫描，或存在导致邮件被错误分类为垃圾邮件的配置问题。可[详细了解反垃圾邮件的邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f0910-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. If you see a message header named X-Forefront-Antispam-Report that contains the string SFV:NSPM, this means that Exchange Online Protection (EOP) scanned the message and thought it was spam. In this case, we strongly recommend that you [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. If you don't see this value in the headers, it could mean either that the mail didn't pass through spam scanning, or that there was a configuration issue which caused the message to be incorrectly classified as spam. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="f0910-113">在邮件头中查找以下头和值。</span><span class="sxs-lookup"><span data-stu-id="f0910-113">In the header, look for the following headings and values.</span></span>
  
### <a name="x-forefront-antispam-report"></a><span data-ttu-id="f0910-114">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="f0910-114">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="f0910-115">**SFV:BLK**：指明邮件被标记为“垃圾邮件”，因为发送地址位于收件人的阻止的发件人名单中。</span><span class="sxs-lookup"><span data-stu-id="f0910-115">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span> 
    
- <span data-ttu-id="f0910-p103">**SFV:SKS**：指明邮件在经内容筛选器筛选前就已被标记为“垃圾邮件”。这可能是因为有将邮件标记为“垃圾邮件”的传输规则。运行邮件跟踪，以确定是否触发了可能已设置高垃圾邮件可信度 (SCL) 的传输规则。</span><span class="sxs-lookup"><span data-stu-id="f0910-p103">**SFV:SKS** Indicates that the message was marked as spam prior to the content filter. This could include a transport rule marking the message as spam. Run a message trace to see if a transport rule triggered which may have set a high spam confidence level (SCL).</span></span> 
    
- <span data-ttu-id="f0910-119">**SFV:SKB**：指明邮件被标记为“垃圾邮件”，因为它符合垃圾邮件筛选器策略中的阻止列表。</span><span class="sxs-lookup"><span data-stu-id="f0910-119">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span> 
    
- <span data-ttu-id="f0910-p104">**SFV:BULK**：指明 x-microsoft-antispam 头中的大量邮件可信度 (BCL) 值高于已为内容筛选器设置的大量邮件阈值。大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。</span><span class="sxs-lookup"><span data-stu-id="f0910-p104">**SFV:BULK** Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter. Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email is handled](https://blogs.msdn.microsoft.com/tzink/2014/08/25/different-levels-of-bulk-mail-filtering-in-office-365/). You can create different policies or rules for different user preferences.</span></span>
    
- <span data-ttu-id="f0910-p105">**CAT:SPOOF** 或 **CAT:PHISH**：指明邮件可能存在欺骗行为。也就是说，无法验证邮件来源，来源可疑。如果有效，发件人需要确保已正确配置 SPF 和 DKIM。请检查 Authentication-Results 头，以获取更多信息。尽管难以让所有发件人都使用正确的电子邮件身份验证方法，但规避这些检查极为危险，最容易导致泄漏发生。</span><span class="sxs-lookup"><span data-stu-id="f0910-p105">**CAT:SPOOF** or **CAT:PHISH** Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious. If valid, the sender will need to make sure that they have proper SPF and DKIM configuration. Check the Authentication-Results header for more information. Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span> 
    
### <a name="x-customspam"></a><span data-ttu-id="f0910-130">x-customspam</span><span class="sxs-lookup"><span data-stu-id="f0910-130">x-customspam</span></span>

- <span data-ttu-id="f0910-p106">此头指明邮件被标记为“垃圾邮件”，因为垃圾邮件筛选器中的[高级垃圾邮件选项之一已启用](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)。建议使用默认设置，除非你确实需要这些功能。</span><span class="sxs-lookup"><span data-stu-id="f0910-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span> 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="f0910-133">垃圾邮件过多的其他原因的解决方案</span><span class="sxs-lookup"><span data-stu-id="f0910-133">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="f0910-p107">为了提高工作效率，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。</span><span class="sxs-lookup"><span data-stu-id="f0910-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="f0910-137">对于管理员</span><span class="sxs-lookup"><span data-stu-id="f0910-137">For admins</span></span>

- <span data-ttu-id="f0910-p108">**让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供保护。如果 MX 没有指向 Office 365，EOP 就不会为用户提供垃圾邮件筛选服务。若要使用其他服务或设备为域提供垃圾邮件筛选服务，应考虑在 EOP 中禁用垃圾邮件保护。为此，可创建将 SCL 值设为 -1 的传输规则。如果稍后决定使用 EOP，请务必删除此传输规则。</span><span class="sxs-lookup"><span data-stu-id="f0910-p108">**Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your MX does not point to Office 365, then EOP will not provide spam filtering for your users. In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP. You can do this by creating a transport rule that sets the SCL value to -1. If you later decide to use EOP, make sure to remove this transport rule.</span></span> 
    
- <span data-ttu-id="f0910-p109">**在 Outlook 中禁用 SmartScreen 筛选**：如果用户使用的是 Outlook 桌面客户端，他们应禁用 SmartScreen 筛选功能（此功能已终止）。如果启用，可能会导致误报。如果运行的是更新后的桌面 Outlook 客户端，无需遵守此要求。</span><span class="sxs-lookup"><span data-stu-id="f0910-p109">**Disable SmartScreen filtering in Outlook** If your users are using the Outlook desktop client, they should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span> 
    
- <span data-ttu-id="f0910-p110">**为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整任何可能会导致问题发生的设置。</span><span class="sxs-lookup"><span data-stu-id="f0910-p110">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
    
- <span data-ttu-id="f0910-p111">**立即允许发件人**：如果你需要立即允许发件人，强烈建议**仅允许特定发件人的 IP 地址**。也可以创建**同时**查找发件人域和成功的 Authentication-Results 头的传输规则，从而允许发件人，并还确保发件人通过 SPF 或 DKIM 等身份验证检查。</span><span class="sxs-lookup"><span data-stu-id="f0910-p111">**Immediately allow a sender** In the case where you need to immediately allow a sender, we strongly recommend that you **ONLY allow a particular sender's IP address**. Alternately, you can allow a sender and also make sure that the sender passes an authentication check like SPF or DKIM by creating a transport rule that looks for **both** the sender domain and a successful Authentication-Results header.</span></span> 
    
### <a name="for-users"></a><span data-ttu-id="f0910-150">对于用户</span><span class="sxs-lookup"><span data-stu-id="f0910-150">For users</span></span>

- <span data-ttu-id="f0910-p112">**向 Microsoft 举报垃圾邮件**：按照[使用“举报邮件”加载项](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)中的说明操作，向 Microsoft 举报垃圾邮件。此外，还可以向 junk@office365.microsoft.com 发送邮件，并附加要举报的一个或多个邮件。</span><span class="sxs-lookup"><span data-stu-id="f0910-p112">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.</span></span>
    
    <span data-ttu-id="f0910-153">**重要提示**：如果未以附件形式转发邮件，[头就会丢失，导致我们无法改进](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/)在 Office 365 中的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="f0910-153">**Important** If you do not forward the messages as attachments, then [the headers will be missing and we will be unable to improve](https://blogs.msdn.microsoft.com/tzink/2017/11/30/when-creating-support-tickets-about-spam-be-sure-to-include-message-headers/) the junk mail filtering in Office 365.</span></span> 
    
- <span data-ttu-id="f0910-p113">**将发件人添加到允许列表（但请谨慎使用）**：万不得已的方法是，可使用[“阻止或允许”（垃圾邮件设置）](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)。如果这样做，应注意可能会允许定向钓鱼邮件进入收件箱。</span><span class="sxs-lookup"><span data-stu-id="f0910-p113">**Add a sender to your allow list - but use sparingly** As a last resort, you can [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). If you do so, you should beware that a targeted phishing attempt may be allowed into your inbox.</span></span>
    

