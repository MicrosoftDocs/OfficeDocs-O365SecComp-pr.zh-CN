---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。
ms.openlocfilehash: dc8901dc7c1db5b323ccbeee610647b8a302fcb3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525008"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="1060f-104">零时差自动清除 - 防范垃圾邮件和恶意软件</span><span class="sxs-lookup"><span data-stu-id="1060f-104">Zero-hour auto purge - protection against spam and malware</span></span>

<span data-ttu-id="1060f-p102">零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。</span><span class="sxs-lookup"><span data-stu-id="1060f-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with spam or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected.</span></span>
  
<span data-ttu-id="1060f-107">默认值是包含任何 Office 365 订阅包含 Exchange Online 邮箱的 Exchange Online Protection 提供 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1060f-107">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>
  
## <a name="how-does-zap-work"></a><span data-ttu-id="1060f-108">ZAP 如何工作？</span><span class="sxs-lookup"><span data-stu-id="1060f-108">How does ZAP work?</span></span>

<span data-ttu-id="1060f-p103">Office 365 更新中的反垃圾邮件引擎和恶意软件签名实时每天。但是，用户可能仍获取恶意邮件传递到各种原因，包括何时内容已 weaponized 一次后第一次传递到用户的收件箱。将清除的地址这通过不断监视更新到 Office 365 垃圾邮件和恶意软件签名，并可以因此查找和收件箱中已删除之前已发送的邮件。已被标识为垃圾邮件的邮件，ZAP 将未读的邮件移动到用户的垃圾邮件文件夹。为新检测到恶意软件、 ZAP 从电子邮件，而不管是否已读取邮件，或不删除附件。相反的以前正确分类为恶意邮件的邮件，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="1060f-p103">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including when the content was weaponized at a time after it was first delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures, and can therefore find and remove previously delivered messages already in inboxes. For mail that was already identified as spam, ZAP moves unread messages to the user's Junk mail folder. For newly detected malware, ZAP removes the attachments from the email message, regardless of whether the mail was read or not. The reverse is true for messages that were incorrectly classified as malicious.</span></span>
  
<span data-ttu-id="1060f-115">ZAP 操作是无缝邮箱用户，他或她不通知邮件已被移动。</span><span class="sxs-lookup"><span data-stu-id="1060f-115">The ZAP action is seamless for the mailbox user, he or she is not notified the mail has been moved.</span></span>
  
<span data-ttu-id="1060f-116">允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1060f-116">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
 <span data-ttu-id="1060f-117">**本文内容：**</span><span class="sxs-lookup"><span data-stu-id="1060f-117">**In this article:**</span></span>
  
> [<span data-ttu-id="1060f-118">设置垃圾邮件筛选器策略</span><span class="sxs-lookup"><span data-stu-id="1060f-118">Set spam filter policy</span></span>](zero-hour-auto-purge.md#BK_SetSpam)
    
> [<span data-ttu-id="1060f-119">请参阅 ZAP 是否移动消息</span><span class="sxs-lookup"><span data-stu-id="1060f-119">See if ZAP moved your message</span></span>](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [<span data-ttu-id="1060f-120">禁用 ZAP</span><span class="sxs-lookup"><span data-stu-id="1060f-120">Disable ZAP</span></span>](zero-hour-auto-purge.md#BK_Posh)
    
> [<span data-ttu-id="1060f-121">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="1060f-121">FAQ</span></span>](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a><span data-ttu-id="1060f-122">使用 ZAP</span><span class="sxs-lookup"><span data-stu-id="1060f-122">Working with ZAP</span></span>

<span data-ttu-id="1060f-123">ZAP 已打开默认情况下，但您需要确保满足两个条件：</span><span class="sxs-lookup"><span data-stu-id="1060f-123">ZAP is turned on by default, but you do have to make sure a couple of conditions are met:</span></span>
  
- <span data-ttu-id="1060f-124">垃圾邮件筛选器策略设置为[移动到垃圾邮件文件夹的邮件](zero-hour-auto-purge.md#BK_SetSpam)。</span><span class="sxs-lookup"><span data-stu-id="1060f-124">Spam filter policy is set to [Move message to Junk Email folder](zero-hour-auto-purge.md#BK_SetSpam).</span></span>
    
    <span data-ttu-id="1060f-125">您还可以创建仅适用于一组用户如果您不希望通过 ZAP 屏蔽所有邮箱的新垃圾邮件筛选器策略。</span><span class="sxs-lookup"><span data-stu-id="1060f-125">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>
    
- <span data-ttu-id="1060f-126">用户的[选项\>垃圾邮件](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F)。</span><span class="sxs-lookup"><span data-stu-id="1060f-126">The user's [Options \> Junk Email](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).</span></span>
    
<span data-ttu-id="1060f-127">如果要[查看 ZAP 如果移动消息](zero-hour-auto-purge.md#BK_DidZAPMove)，您可以使用 Exchange Online 邮件跟踪工具。</span><span class="sxs-lookup"><span data-stu-id="1060f-127">If you want [to see if ZAP moved your message](zero-hour-auto-purge.md#BK_DidZAPMove), you can use the Exchange Online message trace tool.</span></span>
  
<span data-ttu-id="1060f-128">管理员还可以[禁用 ZAP](zero-hour-auto-purge.md#BK_Posh)使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1060f-128">Admins can also [disable ZAP](zero-hour-auto-purge.md#BK_Posh) by using PowerShell.</span></span> 
  
 <span data-ttu-id="1060f-129">**将垃圾邮件筛选器策略设置**</span><span class="sxs-lookup"><span data-stu-id="1060f-129">**To set spam filter policy**</span></span>
  
1. <span data-ttu-id="1060f-130">登录到[从何处登录到 Office 365 的业务](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)和选择**保护** \> **垃圾邮件筛选器**。</span><span class="sxs-lookup"><span data-stu-id="1060f-130">Sign in to the [Where to sign in to Office 365 for business](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) and choose **protection** \> **spam filter**.</span></span> 
    
    ![在 EAC 中，选择保护，然后垃圾邮件筛选器](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. <span data-ttu-id="1060f-132">选择您想要调整的筛选器策略，或选择**添加**![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)创建一个新。</span><span class="sxs-lookup"><span data-stu-id="1060f-132">Either choose the filter policy you want to adjust, or choose **add**![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) to create a new one.</span></span> 
    
    <span data-ttu-id="1060f-p104">在以前的屏幕截图，策略名为"Default"，但如果创建额外的垃圾邮件筛选器策略您可以为其提供一个不同的名称。此外可以将策略应用于仅一组有限的用户。</span><span class="sxs-lookup"><span data-stu-id="1060f-p104">In the previous screen shot, the policy is named "Default", but if you create additional spam filter policies you can give them a different name. You can also apply the policy to only a limited set of users.</span></span>
    
3. <span data-ttu-id="1060f-135">在策略窗口中，选择**垃圾邮件和批量操作**，并确保**垃圾邮件**被设置为**将邮件移至垃圾邮件文件夹**。</span><span class="sxs-lookup"><span data-stu-id="1060f-135">In the policy window, choose **spam and bulk actions**, and make sure that **Spam** is set to **Move message to Junk Email folder**.</span></span> 
    
    <span data-ttu-id="1060f-136">如果您选择**保存**，将策略应用于 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="1060f-136">If you choose **Save** at this point, the policy applies to your Office 365 tenant.</span></span> 
    
    ![设置垃圾邮件和批量 Mpve 邮件到垃圾邮件文件夹的操作](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. <span data-ttu-id="1060f-p105">如果您创建新策略，并且想要将策略应用于一组的用户，滚动到**应用于**部分和菜单控件中策略筛选窗口中，选择**收件人**、**域**或**组成员身份**您要应用该策略。您还可以设置其他条件和例外。</span><span class="sxs-lookup"><span data-stu-id="1060f-p105">If you created a new policy, and you want to apply the policy to only a set of users, scroll to the **Applied To** section in the policy filter window, and in the menu controls choose the **recipients**, **domain**, or **group memberships** you want to apply the policy to. You can also set additional conditions and exceptions.</span></span> 
    
    ![在应用于部分中，选择收件人](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    <span data-ttu-id="1060f-141">选择**保存**以将策略应用于所选用户。</span><span class="sxs-lookup"><span data-stu-id="1060f-141">Choose **Save** to apply the policy to the selected users.</span></span> 
    
 <span data-ttu-id="1060f-142">**若要查看 ZAP 是否移动消息**</span><span class="sxs-lookup"><span data-stu-id="1060f-142">**To see if ZAP moved your message**</span></span>
  
- <span data-ttu-id="1060f-143">可以使用[查找和修复为业务管理 Office 365 的电子邮件传递问题](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)来确定邮件是否已通过 ZAP 移动：</span><span class="sxs-lookup"><span data-stu-id="1060f-143">You can use the [Find and fix email delivery issues as an Office 365 for business admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) to determine if the message was moved by ZAP:</span></span> 
    
    <span data-ttu-id="1060f-144">查看您的跟踪详细信息，以确定一条消息，已通过 ZAP 移动中的文本"零时差自动清除 (ZAP)"。</span><span class="sxs-lookup"><span data-stu-id="1060f-144">Look for the text "Zero-Hour Auto Purge (ZAP)" in your trace details to identify a message that was moved by ZAP.</span></span>
    
 <span data-ttu-id="1060f-145">**若要禁用 ZAP**</span><span class="sxs-lookup"><span data-stu-id="1060f-145">**To disable ZAP**</span></span>
  
- <span data-ttu-id="1060f-146">如果您想要禁用的 Office 365 租户，将清除或一组用户，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP cmdlet 的**ZapEnabled**参数。</span><span class="sxs-lookup"><span data-stu-id="1060f-146">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
    <span data-ttu-id="1060f-147">在以下示例中，名为"Test"的内容筛选器策略禁用 ZAP。</span><span class="sxs-lookup"><span data-stu-id="1060f-147">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a><span data-ttu-id="1060f-148">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="1060f-148">FAQ</span></span>
<span data-ttu-id="1060f-149"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="1060f-149"></span></span>

 <span data-ttu-id="1060f-150">**如果合法邮件移动到垃圾邮件文件夹，则会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="1060f-150">**What happens if a legitimate message is moved to the junk mail folder?**</span></span>
  
<span data-ttu-id="1060f-p106">您应遵循的误报报告的常规过程。应为邮件将从收件箱移动到垃圾邮件文件夹的唯一原因，因为该服务已确定的消息是垃圾邮件或恶意。</span><span class="sxs-lookup"><span data-stu-id="1060f-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
 <span data-ttu-id="1060f-153">**如果使用 Office 365 隔离而不是垃圾邮件文件夹？**</span><span class="sxs-lookup"><span data-stu-id="1060f-153">**What if I use the Office 365 quarantine instead of the junk mail folder?**</span></span>
  
<span data-ttu-id="1060f-154">ZAP 不将邮件移动到隔离收件箱这一次。</span><span class="sxs-lookup"><span data-stu-id="1060f-154">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
 <span data-ttu-id="1060f-155">**如果我有自定义邮件流规则 （阻止 / 允许规则）？**</span><span class="sxs-lookup"><span data-stu-id="1060f-155">**What If I have a custom mail flow rule (Block/ Allow Rule)?**</span></span>
  
<span data-ttu-id="1060f-p107">由管理员 （邮件流规则） 或阻止和允许规则创建的规则的优先级。此类邮件将排除在功能条件。</span><span class="sxs-lookup"><span data-stu-id="1060f-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1060f-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="1060f-158">Related Topics</span></span>
<span data-ttu-id="1060f-159"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="1060f-159"></span></span>

[<span data-ttu-id="1060f-160">Office 365 电子邮件反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="1060f-160">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="1060f-161">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="1060f-161">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

