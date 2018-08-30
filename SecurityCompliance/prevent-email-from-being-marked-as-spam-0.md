---
title: 防止电子邮件被标记为 Office 365 和 Exchange Online Protection 中的垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: Office 365 管理员可以阻止好的电子邮件标记为垃圾邮件的发送到隔离为误报提示。自定义安全列表和其他选项，以防止好的电子邮件标记为垃圾邮件。
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524890"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a><span data-ttu-id="fdb18-104">防止电子邮件被标记为 Office 365 和 Exchange Online Protection 中的垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="fdb18-104">Prevent email from being marked as spam in Office 365 and Exchange Online Protection</span></span>

<span data-ttu-id="fdb18-105">使用适当的访问凭据的 Exchange Online 或 Exchange Online Protection (EOP) 管理员可以使用以下步骤以帮助确保通过服务旅行一封电子邮件未标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb18-105">Exchange Online or Exchange Online Protection (EOP) administrators with the appropriate access credentials can use these steps to help ensure that an email message traveling through the service isn't marked as spam.</span></span>
  
<span data-ttu-id="fdb18-p102">很遗憾了合法的良好电子邮件，隔离或阻止垃圾邮件和隔离文件夹中登录。可以使用安全发件人列表或邮件流规则以绕过垃圾邮件筛选，防止良好的电子邮件获取标记为垃圾邮件。当错误地将邮件标记为垃圾邮件垃圾邮件筛选器时，它具有调用误报。Office 365 垃圾邮件筛选器还提供了一些最终用户可以以帮助阻止误报自定义的选项。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p102">It can be frustrating to have legitimate, good email quarantined or blocked as spam and landing in a quarantine folder. You can use a safe sender list or a mail flow rule to bypass spam filtering and prevent good email messages from getting marked as junk mail. When a message is incorrectly marked as spam by the spam filter, it's called a false positive. The Office 365 spam filter also provides some options that end users can customize in order to help prevent false positives.</span></span>
  
<span data-ttu-id="fdb18-110">如果您正在寻找帮助假负邮件，即垃圾邮件的获取时它不应，签出[垃圾邮件与 Office 365 垃圾邮件筛选器以阻止假负问题阻止电子邮件](block-email-spam-to-prevent-false-negatives.md)中的提示。</span><span class="sxs-lookup"><span data-stu-id="fdb18-110">If you're looking for help with false negative mail, that is, a spam message that gets through when it shouldn't, check out the tips in [Block email spam with the Office 365 spam filter to prevent false negative issues](block-email-spam-to-prevent-false-negatives.md).</span></span>
  
## <a name="eop-only-customers-use-directory-synchronization"></a><span data-ttu-id="fdb18-111">仅 EOP 客户： 使用目录同步</span><span class="sxs-lookup"><span data-stu-id="fdb18-111">EOP-only customers: use directory synchronization</span></span>

<span data-ttu-id="fdb18-p103">EOP 是基于云的电子邮件筛选服务，可帮助保护您的组织免受垃圾邮件和恶意软件。如果您有 Office 365 中的邮箱，它们是自动受 EOP，因为它是服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p103">EOP is a cloud-based email filtering service that helps protect your organization against spam and malware. If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service.</span></span> 
  
<span data-ttu-id="fdb18-p104">如果您仅 EOP 客户，即，与您的本地 Exchange 服务器订阅到使用的 EOP 服务，您应使用目录同步同步服务的用户设置。这样可确保您安全发件人列表将由 EOP。有关详细信息，请参阅[Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098)中的"使用目录同步管理邮件用户"。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p104">If you're an EOP-only customer, that is, you subscribe to the EOP service for use with your on-premises Exchange Server, you should sync user settings with the service by using directory synchronization. Doing this ensures that your safe senders lists are respected by EOP. For more information, see "Use directory synchronization to manage mail users" in [Manage Mail Users in EOP](https://go.microsoft.com/fwlink/?LinkId=534098).</span></span>
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a><span data-ttu-id="fdb18-117">阻止 false 正电子邮件使用连接筛选器的 IP 允许列表</span><span class="sxs-lookup"><span data-stu-id="fdb18-117">Prevent false positive email by using the connection filter's IP allow list</span></span>

<span data-ttu-id="fdb18-p105">如果您发现发件人的电子邮件总是移动到您的组织中的垃圾邮件文件夹，您可以将电子邮件发件人的 IP 地址添加到连接筛选器 IP 允许列表。通常，这样可以防止在 false 正响应此发件人为组织内的所有收件人。例外情况是当用户启用选项"安全仅列出： 只有来自人员或域安全发件人列表或安全收件人列表的邮件将传递到收件箱"在 Outlook 中不会将该发件人添加到安全发件人列表。重写该选项的信息，请参阅[疑难解答： 一条消息，该怎么办垃圾文件夹中即使 EOP 标记为非垃圾邮件邮件](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam)。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p105">If you find that a sender's email is always moved to the Junk folders in your organization, you can add the email sender's IP address to your connection filter's IP allow list. Normally, this prevents false positive responses for this sender for all recipients within your organization. The exception is when a user enables the option "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox" in Outlook and does not add that sender to the Safe Sender List. For information on overriding that option, see [Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam).</span></span>
  
 <span data-ttu-id="fdb18-122">**若要将 IP 地址添加到您的连接筛选器的 IP 允许列表**</span><span class="sxs-lookup"><span data-stu-id="fdb18-122">**To add an IP address to your connection filter's IP allow list**</span></span>
  
1. <span data-ttu-id="fdb18-p106">获取来自您希望允许的发件人发送的消息标头。[邮件标头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)中所述，您可以将从您的邮件客户端如 Outlook 或 Outlook Web 上的执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p106">Obtain the header from a message sent by the sender that you want to allow. You can do this from your mail client such as Outlook or Outlook on the Web, as described in [Message Header Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=306583).</span></span>
    
2. <span data-ttu-id="fdb18-125">手动搜索关注 CIP 标签在 X Forefront 反垃圾邮件报表页眉或使用[远程连接分析器](https://testconnectivity.microsoft.com/?tabid=mha)**消息分析器**选项卡的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fdb18-125">Manually search for the IP address following the CIP tag in the X-Forefront-Antispam-Report header or by using the **Message Analyzer** tab of the [Remote Connectivity Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span></span>
    
3. <span data-ttu-id="fdb18-126">添加 IP IP 地址允许通过"使用 EAC 编辑默认连接筛选器策略"中的步骤中[配置连接筛选器策略](https://go.microsoft.com/fwlink/?LinkId=534132)的列表。</span><span class="sxs-lookup"><span data-stu-id="fdb18-126">Add the IP address to the IP allow list by following the steps in "Use the EAC to edit the default connection filter policy" in [Configure the connection filter policy](https://go.microsoft.com/fwlink/?LinkId=534132).</span></span>
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a><span data-ttu-id="fdb18-127">通过配置垃圾邮件筛选器策略阻止 false 正电子邮件</span><span class="sxs-lookup"><span data-stu-id="fdb18-127">Prevent false positive email by configuring spam filter policies</span></span>

<span data-ttu-id="fdb18-128">您可以添加到允许列表的域或单个电子邮件地址，方法是中[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/?LinkID=534136)的步骤。</span><span class="sxs-lookup"><span data-stu-id="fdb18-128">You can add domains or individual email addresses to an allow list by following the steps in [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkID=534136).</span></span>
  
## <a name="review-your-advanced-spam-filter-policies"></a><span data-ttu-id="fdb18-129">查看您的高级垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="fdb18-129">Review your advanced spam filter policies</span></span>

<span data-ttu-id="fdb18-p107">如果您有特殊限制设置中的垃圾邮件筛选器策略，例如，如果您已阻止整个域，则应查看这些检查如果它们可能导致误报。请参阅[配置垃圾邮件筛选器策略](https://go.microsoft.com/fwlink/?LinkId=534136)，并关闭其他[高级垃圾邮件筛选选项](https://go.microsoft.com/fwlink/?LinkId=534137)可能会导致邮件标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p107">If you have special restrictions set up in a spam filter policy, for example, if you have blocked an entire domain, you should review them to check if they may be causing false positives. See [Configure your spam filter policies](https://go.microsoft.com/fwlink/?LinkId=534136), and turn off additional [Advanced spam filtering options](https://go.microsoft.com/fwlink/?LinkId=534137) that might cause messages to be marked as spam.</span></span> 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a><span data-ttu-id="fdb18-132">帮助最终用户创建安全发件人列表来阻止好的电子邮件标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="fdb18-132">Help your end users create a safe sender list to prevent good email from being marked as spam</span></span>
<span data-ttu-id="fdb18-133"><a name="BKMK_email-user-help-safelist"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb18-133"></span></span>

<span data-ttu-id="fdb18-p108">告知用户从其信任到其安全发件人列表中[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)或[Outlook Web 上](https://go.microsoft.com/fwlink/p/?LinkId=294862)的发件人添加地址。若要开始在 Web 上的 Outlook 中，选择**设置**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **选项** \> **阻止或允许**。下图显示将内容添加到安全发件人列表的示例。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p108">Tell your users to add addresses from senders that they trust to their safe sender list in [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) or [Outlook on the Web](https://go.microsoft.com/fwlink/p/?LinkId=294862). To get started in Outlook on the Web, choose **Settings**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **Options** \> **Block or allow**. The following diagram shows an example of adding something to a safe sender list.</span></span>
  
![在 Outlook Web App 中添加安全发件人](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
<span data-ttu-id="fdb18-p109">EOP 也会授予用户安全发件人和收件人，但不是安全的域。这为 true，无论是通过在 Web 上，Outlook 添加还是在 Outlook 中添加域，并使用目录同步同步。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p109">EOP will honor your users' Safe Senders and Recipients, but not Safe Domains. This is true regardless of whether the domain is added through the Outlook on the Web, or added in Outlook and synchronized using Directory Sync.</span></span>
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a><span data-ttu-id="fdb18-140">疑难解答： 一条消息，该怎么办垃圾文件夹中即使 EOP 标记为非垃圾邮件的邮件</span><span class="sxs-lookup"><span data-stu-id="fdb18-140">Troubleshooting: A message ends up in the Junk folder even though EOP marked the message as non-spam</span></span>
<span data-ttu-id="fdb18-141"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb18-141"></span></span>

<span data-ttu-id="fdb18-p110">如果您的用户可以在 Outlook 中启用了"安全仅列出： 来自人员或域的安全发件人列表或安全收件人列表的仅邮件将传递到收件箱"，然后所有电子邮件将转到垃圾邮件文件夹的发件人除非发件人位于 recipient 的安全发件人列表。这将发生无论 EOP 将邮件标记为非垃圾邮件，还是已将 EOP 中的某个规则设置为标记为非垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p110">If your users have the option in Outlook enabled for "Safe Lists Only: Only mail from people or domains on your Safe Senders list or Safe Recipients List will be delivered to your Inbox", then all email will go to the junk folder for a sender unless the sender is on the recipient's Safe Sender list. This will happen regardless of whether EOP marks a message as non-spam, or if you have set up a rule in EOP to mark a message as non-spam.</span></span>
  
<span data-ttu-id="fdb18-144">您可以通过中的说明禁用 Outlook 用户的仅安全列表选项[Outlook： 策略设置禁用垃圾电子邮件用户界面和筛选机制](https://support.microsoft.com/en-us/kb/2180568)。</span><span class="sxs-lookup"><span data-stu-id="fdb18-144">You can disable the Safe Lists Only option for your Outlook users by following the instructions in [Outlook: Policy setting to disable the Junk E-mail UI and filtering mechanism](https://support.microsoft.com/en-us/kb/2180568).</span></span>
  
<span data-ttu-id="fdb18-145">如果在 Web 上的 Outlook 中查看邮件时，将会指示邮件位于垃圾邮件文件夹，因为发件人在收件人的安全发件人列表不是一个黄色安全提示。</span><span class="sxs-lookup"><span data-stu-id="fdb18-145">If you view the message in Outlook on the Web, there will be a yellow safety tip that indicates that the message is in the Junk folder because the sender is not on the recipient's Safe Senders list.</span></span>
  
<span data-ttu-id="fdb18-p111">如果您查看邮件的标头，它可能包括戳 SFV:SKN （IP 允许或 ETR 允许） 或 SFV:NSPM （非垃圾邮件），但该消息仍处于用户的垃圾邮件文件夹。有，该值指示用户具有"仅安全列表"已启用邮件头中为 nothing。这是因为设置在 Outlook 中的用户的"仅安全列表"选项将覆盖的 EOP 设置。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p111">If you look at the header of a message, it may include the stamp SFV:SKN (IP Allow or ETR Allow) or SFV:NSPM (non-spam), but the message is still placed in the user's junk folder. There is nothing in the message header that indicates that the user has "Safe Lists Only" enabled. This happens because the "Safe Lists Only" option set by users in Outlook overrides the EOP setting.</span></span> 
  
 <span data-ttu-id="fdb18-149">**若要验证为什么来自安全发件人的邮件标记为非垃圾邮件邮件头，但仍结束中用户的垃圾文件夹中**</span><span class="sxs-lookup"><span data-stu-id="fdb18-149">**To verify why a message from a safe sender is marked as non-spam in the message header, but still ends up in the user's Junk folder**</span></span>
  
1. <span data-ttu-id="fdb18-150">若要了解如何连接到 Exchange Online PowerShell 中，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="fdb18-150">To learn how to connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span> 
    
2. <span data-ttu-id="fdb18-151">运行以下命令以查看用户的垃圾邮件配置设置：</span><span class="sxs-lookup"><span data-stu-id="fdb18-151">Run the following command to view the user's junk email configuration settings:</span></span>
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    <span data-ttu-id="fdb18-p112">如果 TrustedListsOnly 设置为 True，则表明已启用此设置。如果 ContactsTrusted 设置为 True，则意味着用户信任联系人和安全发件人。TrustedSendersAndDomains 列出用户的安全发件人列表的内容。</span><span class="sxs-lookup"><span data-stu-id="fdb18-p112">If TrustedListsOnly is set to True, it means that this setting is enabled. If ContactsTrusted is set to True, it means that the user trusts both Contacts and Safe Senders. The TrustedSendersAndDomains lists the contents of the user's Safe Senders list.</span></span>
    
## <a name="still-need-help"></a><span data-ttu-id="fdb18-155">仍需要帮助？</span><span class="sxs-lookup"><span data-stu-id="fdb18-155">Still need help?</span></span>
<span data-ttu-id="fdb18-156"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb18-156"></span></span>

<span data-ttu-id="fdb18-157">[![从 Office 365 社区论坛获取帮助](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span><span class="sxs-lookup"><span data-stu-id="fdb18-157">[![Get help from the Office 365 community forums](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)</span></span>
  
<span data-ttu-id="fdb18-158">[![管理员：登录并创建一个服务请求](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span><span class="sxs-lookup"><span data-stu-id="fdb18-158">[![Admins: Sign in and create a service request](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)</span></span>
  
<span data-ttu-id="fdb18-159">[![管理员：电话支持](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span><span class="sxs-lookup"><span data-stu-id="fdb18-159">[![Admins: Call Support](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdb18-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb18-160">See also</span></span>
<span data-ttu-id="fdb18-161"><a name="TroubleshootingJunkEOPNonSpam"> </a></span><span class="sxs-lookup"><span data-stu-id="fdb18-161"></span></span>

[<span data-ttu-id="fdb18-162">垃圾邮件筛选器的概述</span><span class="sxs-lookup"><span data-stu-id="fdb18-162">Overview of the Junk Email Filter</span></span>](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[<span data-ttu-id="fdb18-163">阻止或允许 （垃圾邮件设置）</span><span class="sxs-lookup"><span data-stu-id="fdb18-163">Block or allow (junk email settings)</span></span>](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[<span data-ttu-id="fdb18-164">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="fdb18-164">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)

