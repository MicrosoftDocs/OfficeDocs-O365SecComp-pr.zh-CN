---
title: 如何避免在 Office 365 中发生误报
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 34823bbc-a3e3-4949-ba42-97c73997eeed
description: 了解如何避免在 Office 365 中发生误报和将真实电子邮件标记为“垃圾邮件”。
ms.openlocfilehash: 10d71519da1639073122b0a89652753f466f6dbe
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341473"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a><span data-ttu-id="89f6c-103">如何避免在 Office 365 中将真实电子邮件标记为“垃圾邮件”</span><span class="sxs-lookup"><span data-stu-id="89f6c-103">How to prevent real email from being marked as spam in Office 365</span></span>

 <span data-ttu-id="89f6c-104">**真实电子邮件是否在 Office 365 中被标记为“垃圾邮件”？试试本文中介绍的方法吧。**</span><span class="sxs-lookup"><span data-stu-id="89f6c-104">**Is your real email getting marked as spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="89f6c-p101">如果发生误报，则应使用“[使用报告消息](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)”加载项将此邮件报告给 Microsoft。此外，还可以将此邮件*作为附件*转发至 not_junk@office365.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p101">If you get a false positive, you should report the message to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can forward the message *as an attachment* to not_junk@office365.microsoft.com.</span></span>

<span data-ttu-id="89f6c-107">**重要提示** 如果未将邮件作为附件转发，则标头将会缺失并且我们无法在 Office 365 中改进垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="89f6c-107">**Important** If you do not forward the messages as an attachment, then the headers will be missing and we will be unable to improve the junk mail filtering in Office 365.</span></span>
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a><span data-ttu-id="89f6c-108">确定邮件被标记为“垃圾邮件”的原因</span><span class="sxs-lookup"><span data-stu-id="89f6c-108">Determine the reason why the message was marked as spam</span></span>

<span data-ttu-id="89f6c-p102">Office 365 中的许多垃圾邮件问题都可以这样解决：[查看电子邮件的邮件头](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)，并确定哪里出错。你需要查找名为 X-Forefront-Antispam-Report 的标头。你可以[详细了解反垃圾邮件的邮件头](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p102">Many issues with spam in Office 365 can be resolved by [View e-mail message headers](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c) and determining what went wrong. You will need to look for a header named X-Forefront-Antispam-Report. You can [learn more about anti-spam message headers](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="89f6c-112">在邮件头中查找以下头和值。</span><span class="sxs-lookup"><span data-stu-id="89f6c-112">In the header, look for the following headings and values.</span></span>
  
### <a name="x-forefront-antispam-report"></a><span data-ttu-id="89f6c-113">X-Forefront-Antispam-Report</span><span class="sxs-lookup"><span data-stu-id="89f6c-113">X-Forefront-Antispam-Report</span></span>

- <span data-ttu-id="89f6c-114">**SFV:SPM** 指明邮件被 EOP 垃圾邮件筛选器标记为“垃圾邮件”。</span><span class="sxs-lookup"><span data-stu-id="89f6c-114">**SFV:SPM** Indicates that the message was marked as spam because of the EOP spam filters.</span></span> 

- <span data-ttu-id="89f6c-115">**SFV:BLK**：指明邮件被标记为“垃圾邮件”，因为发送地址位于收件人的阻止的发件人名单中。</span><span class="sxs-lookup"><span data-stu-id="89f6c-115">**SFV:BLK** Indicates that the message was marked as spam because the sending address is on the recipient's Blocked Senders List.</span></span> 
    
- <span data-ttu-id="89f6c-p103">**SFV:SKS**：指明邮件在经内容筛选器筛选前就已被标记为“垃圾邮件”。这可能包含邮件流规则（也称为传输规则），它将邮件标记为“垃圾邮件”。运行邮件跟踪，以确定是否触发了可能已设置高垃圾邮件可信度 (SCL) 的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p103">**SFV:SKS** Indicates that the message was marked as spam prior to the content filter. This could include a transport rule marking the message as spam. Run a message trace to see if a transport rule triggered which may have set a high spam confidence level (SCL).</span></span> 
    
- <span data-ttu-id="89f6c-119">**SFV:SKB**：指明邮件被标记为“垃圾邮件”，因为它符合垃圾邮件筛选器策略中的阻止列表。</span><span class="sxs-lookup"><span data-stu-id="89f6c-119">**SFV:SKB** Indicates that the message was marked as spam because it matched a block list in the spam filter policy.</span></span> 
    
- <span data-ttu-id="89f6c-p104">**SFV:BULK**：指明 x-microsoft-antispam 头中的大量邮件可信度 (BCL) 值高于已为内容筛选器设置的大量邮件阈值。大量电子邮件是指用户已申请，但仍不想接收的电子邮件。在邮件头中的 X-Microsoft-Antispam 头内，找到 BCL（大量邮件可信度）属性。如果 BCL 值低于垃圾邮件筛选器中设置的阈值，建议调整阈值，以将这些类型的大量邮件标记为“垃圾邮件”。用户对[大量电子邮件的处理方式](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values)的容忍度和偏好不同。可创建因用户偏好而异的不同策略或规则。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p104">**SFV:BULK** Indicates that the Bulk Complaint Level (BCL) value located in the x-microsoft-antispam header is above the Bulk threshold that has been set for the content filter. Bulk email is email which users may have signed up for, but may still be undesirable. In the message header find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the Spam Filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email is handled](https://docs.microsoft.com/zh-CN/office365/SecurityCompliance/bulk-complaint-level-values). You can create different policies or rules for different user preferences.</span></span>
    
- <span data-ttu-id="89f6c-p105">**CAT:SPOOF** 或 **CAT:PHISH**：指明邮件可能存在欺骗行为。也就是说，无法验证邮件来源，来源可疑。如果有效，发件人需要确保已正确配置 SPF 和 DKIM。请检查 Authentication-Results 头，以获取更多信息。尽管难以让所有发件人都使用正确的电子邮件身份验证方法，但规避这些检查极为危险，最容易导致泄漏发生。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p105">**CAT:SPOOF** or **CAT:PHISH** Indicates that the message appears to be spoofed, meaning that the message source cannot be validated and could be suspicious. If valid, the sender will need to make sure that they have proper SPF and DKIM configuration. Check the Authentication-Results header for more information. Although it may be difficult to get all senders to use proper email authentication methods, bypassing these checks can be extremely dangerous and is the top cause of compromises.</span></span> 
    
### <a name="x-customspam"></a><span data-ttu-id="89f6c-130">x-customspam</span><span class="sxs-lookup"><span data-stu-id="89f6c-130">x-customspam</span></span>

- <span data-ttu-id="89f6c-p106">此头指明邮件被标记为“垃圾邮件”，因为垃圾邮件筛选器中的[高级垃圾邮件选项之一已启用](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)。建议使用默认设置，除非你确实需要这些功能。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p106">The presence of this header indicates that the message was marked as spam because one of the [advanced spam options is enabled](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx) in your spam filter. Unless you need these features, we recommend that you use the default settings.</span></span> 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a><span data-ttu-id="89f6c-133">垃圾邮件过多的其他原因的解决方案</span><span class="sxs-lookup"><span data-stu-id="89f6c-133">Solutions to additional causes of too much spam</span></span>

<span data-ttu-id="89f6c-p107">为了提高工作效率，Exchange Online Protection (EOP) 要求管理员必须完成一些任务。如果你不是 Office 365 租户的管理员，且收到过多垃圾邮件，建议你与管理员一起完成这些任务。如果不愿意这样做，可跳至用户部分。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p107">In order to work effectively, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="89f6c-137">对于管理员</span><span class="sxs-lookup"><span data-stu-id="89f6c-137">For admins</span></span>

- <span data-ttu-id="89f6c-p108">**让 DNS 记录指向 Office 365**：所有域的邮件交换器 (MX) DNS 记录都必须指向 Office 365，且只能指向 Office 365，这样 EOP 才能提供保护。如果 MX 没有指向 Office 365，EOP 就不会为用户提供垃圾邮件筛选服务。若要使用其他服务或设备为域提供垃圾邮件筛选服务，应考虑在 EOP 中禁用垃圾邮件保护。为此，可创建将 SCL 值设为 -1 的邮件流规则。如果稍后决定使用 EOP，请务必删除邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p108">**Point your DNS records to Office 365** In order for EOP to provide protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. If your MX does not point to Office 365, then EOP will not provide spam filtering for your users. In the situation where you wish to use another service or appliance to provide spam filtering for your domain, you should consider disabling the spam protection in EOP. You can do this by creating a transport rule that sets the SCL value to -1. If you later decide to use EOP, make sure to remove this transport rule.</span></span> 
    
- <span data-ttu-id="89f6c-p109">**为用户启用“举报邮件”加载项**：强烈建议[为用户启用“举报邮件”加载项](enable-the-report-message-add-in.md)。作为管理员，还可以查看用户发送的反馈，并使用任意模式来调整任何可能会导致问题发生的设置。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p109">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for your users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="89f6c-145">对于用户</span><span class="sxs-lookup"><span data-stu-id="89f6c-145">For users</span></span>
    
- <span data-ttu-id="89f6c-p110">**创建安全发件人列表** 用户可以在 [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) 或 [Outlook 网页版](https://go.microsoft.com/fwlink/p/?LinkId=294862)中将受信任的发件人地址添加到安全发件人列表中。若要在 Outlook 网页版中开始使用，请选择“**设置**”![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \>“**选项**”\>“**组织或允许**”。下图所示为向安全发件人列表添加内容的示例。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p110">**Create a safe sender list** Users can add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>
  
![在 Outlook 网页版中添加安全发件人](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
<span data-ttu-id="89f6c-p111">EOP 将会指定用户的安全发件人和收件人，但不是安全域。无论该域是已添加到 Outlook 网页版中还是已添加到 Outlook 并使用 Directory Sync 进行同步，情况均是如此。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p111">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>

- <span data-ttu-id="89f6c-p112">**在 Outlook 中禁用 SmartScreen 筛选**：如果使用的是旧版 Outlook 桌面客户端，则你应禁用 SmartScreen 筛选功能（此功能已终止）。如果启用，可能会导致误报。如果运行的是更新后的桌面 Outlook 客户端，无需遵守此要求。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p112">**Disable SmartScreen filtering in Outlook** If you are using an older Outlook desktop client, you should disable the SmartScreen filtering functionality, which has been discontinued. If enabled, it can cause false positives. This should not be required if running an updated desktop Outlook client.</span></span>

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="89f6c-155">疑难解答：即便 EOP 已将邮件标记为“非垃圾邮件”，邮件还是出现在“垃圾邮件”文件夹中</span><span class="sxs-lookup"><span data-stu-id="89f6c-155">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>
<span data-ttu-id="89f6c-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="89f6c-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span></span>

<span data-ttu-id="89f6c-p113">如果用户在 Outlook 中启用了“仅限安全列表：仅来自安全发件人列表或安全收件人列表的人员或域的邮件将传送至收件箱”，则所有电子邮件均会投递至某个发件人的垃圾邮件文件夹，除非该发件人位于收件人的安全发件人列表上。无论 EOP 是否已将邮件标记为“非垃圾邮件”，或者已在 EOP 中设立将邮件标记为“非垃圾邮件”的规则，情况均会如此。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p113">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>
  
<span data-ttu-id="89f6c-159">可以按照 [Outlook：禁用垃圾邮件 UI 和筛选机制的策略设置](https://support.microsoft.com/zh-CN/kb/2180568)中的说明，为 Outlook 用户禁用“仅限安全列表”选项。</span><span class="sxs-lookup"><span data-stu-id="89f6c-159">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/zh-CN/kb/2180568).</span></span>
  
<span data-ttu-id="89f6c-160">如果在 Outlook 网页版中查看邮件，则其中显示的黄色安全提示指示邮件位于垃圾邮件文件夹中，因为该发件人不在收件人的安全发件人列表中。</span><span class="sxs-lookup"><span data-stu-id="89f6c-160">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>
  
<span data-ttu-id="89f6c-p114">如果查看邮件头，则其中可能包含戳记 SFV:SKN（IP 允许或 ETR 允许）或 SFV:NSPM（非垃圾邮件），但邮件仍位于用户的垃圾邮件文件夹中。如果邮件头中没有任何内容，则表示用户已启用“仅限安全列表”选项。这是因为用户在 Outlook 中设置的“仅限安全列表”选项将会覆盖 EOP 设置。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p114">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span> 
  
 <span data-ttu-id="89f6c-164">**查证为何来自某个安全发件人的邮件在邮件头中被标记为“非垃圾邮件”，但仍出现在用户的垃圾邮件文件夹中**</span><span class="sxs-lookup"><span data-stu-id="89f6c-164">**To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**</span></span>
  
1. <span data-ttu-id="89f6c-165">若要了解如何连接到 Exchange Online PowerShell，请查阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="89f6c-165">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> 
    
2. <span data-ttu-id="89f6c-166">运行以下命令，以查看用户的垃圾邮件配置设置：</span><span class="sxs-lookup"><span data-stu-id="89f6c-166">Run the following command to view the user's junk email configuration settings:</span></span>
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- <span data-ttu-id="89f6c-167">如果 TrustedListsOnly 已设为 True，则这意味着此设置已启用</span><span class="sxs-lookup"><span data-stu-id="89f6c-167">If TrustedListsOnly is set to True, it means that this setting is enabled</span></span>
- <span data-ttu-id="89f6c-168">如果 ContactsTrusted 已设为 True，则这意味着用户信任联系人和安全发件人</span><span class="sxs-lookup"><span data-stu-id="89f6c-168">If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders</span></span>
- <span data-ttu-id="89f6c-169">TrustedSendersAndDomains 将列出用户的安全发件人列表中的内容</span><span class="sxs-lookup"><span data-stu-id="89f6c-169">The TrustedSendersAndDomains lists the contents of the user's Safe Senders list</span></span>


## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="89f6c-170">仅限 EOP 客户：使用目录同步</span><span class="sxs-lookup"><span data-stu-id="89f6c-170">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="89f6c-p115">如果为仅限 EOP 客户，即，你已订阅 EOP 服务以用于本地 (Exchange) 单子邮件服务器，则应使用目录同步功能将用户设置与该服务同步。这样做可确保 EOP 接受你的安全发件人列表。有关更多信息，请参阅[在 EOP 中管理邮件用户](https://go.microsoft.com/fwlink/?LinkId=534098)中的“使用目录同步管理邮件用户”。</span><span class="sxs-lookup"><span data-stu-id="89f6c-p115">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises (Exchange) email server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
