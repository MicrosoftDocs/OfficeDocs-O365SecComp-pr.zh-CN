---
title: 动态交付和与 Office 365 ATP 安全附件预览
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/28/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: 将您 ATP 附件安全策略设置，当您选择动态传递，以避免消息延迟和使人们可以预览正在被扫描的附件。
ms.openlocfilehash: 23017f4f995dfe6a90479d83af9522531d7bf96b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524809"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="7fc4d-103">动态交付和与 Office 365 ATP 安全附件预览</span><span class="sxs-lookup"><span data-stu-id="7fc4d-103">Dynamic delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="7fc4d-p101">动态传递是可以为选择一个选项。阅读此文，了解有关动态交付和[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的附件预览功能。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p101">Dynamic delivery is an option that can be selected for . Read this article to learn about dynamic delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="7fc4d-106">如何进行动态传递工作原理</span><span class="sxs-lookup"><span data-stu-id="7fc4d-106">How dynamic delivery works</span></span>

<span data-ttu-id="7fc4d-p102">当您[在 Office 365 中的 ATP 安全附件策略设置](set-up-atp-safe-attachments-policies.md)，可以选择从几个选项，如**块**、**替换**和**动态传递**。根据您的策略的配置方式，电子邮件收件人可以次要在遇到延迟电子邮件传递时对其附件进行扫描。若要避免出现邮件延迟，请选择**动态传递**。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p102">When you [set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md), you can choose from several options, such as **Block**, **Replace**, and **Dynamic Delivery**. Depending on how your policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="7fc4d-p103">动态交付选项通过发送电子邮件通过与每个电子邮件附件的占位符的正文消除了电子邮件延迟。附件扫描的[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)一直占位符。电子邮件收件人可以读取和对其电子邮件立即响应，了解，正在分析其附件。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p103">The dynamic delivery option eliminates email delays by sending the body of an email message through with a placeholder for each email attachment. The placeholder remains until the attachment is scanned by [ATP Safe Attachments in Office 365](atp-safe-attachments.md). Email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span>
  
<span data-ttu-id="7fc4d-p104">大多数 Pdf 和 Office ATP 扫描正在进行时，可以在安全模式下预览文档。如果某个附件不可与动态传递预览器兼容，电子邮件收件人请参阅附件占位符，直到 ATP 安全附件扫描已完成。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the dynamic delivery previewer, email recipients see the attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>
  
<span data-ttu-id="7fc4d-p105">为每个附件处于清除状态，它都会自动重新附加到原始电子邮件中。如果附件确定恶意，它是发送到隔离，某人贵组织的安全工作组 （例如 Office 365 全局管理员或安全管理员） 可以[管理 Office 365 中的隔离的邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p105">As each attachment is cleared, it is automatically reattached to the original email message. If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="7fc4d-117">当某人的转发电子邮件时，会发生什么情况包含附件？</span><span class="sxs-lookup"><span data-stu-id="7fc4d-117">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="7fc4d-p106">假设其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)中，为组织使用动态传递有人收到包含附件的电子邮件。现在假设其即将转发给其他人的电子邮件。会发生什么情况？这取决于是否 ATP 安全附件策略中包含其他收件人。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p106">Suppose that an organization is using dynamic delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="7fc4d-122">如果收件人使用动态交付选项 ATP 安全附件策略涵盖，收件人会占位符，看到可以预览兼容的文件中。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-122">If a recipient is covered by an ATP Safe Attachments policy using the dynamic delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="7fc4d-123">如果收件人不受 ATP 安全附件策略，然后电子邮件和附件将经过，不含 ATP 安全扫描的附件或附件占位符。</span><span class="sxs-lookup"><span data-stu-id="7fc4d-123">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="7fc4d-124">有什么要求动态传递工作？</span><span class="sxs-lookup"><span data-stu-id="7fc4d-124">What's required for dynamic delivery to work?</span></span>

- <span data-ttu-id="7fc4d-125">您的组织必须具有[Office 365 高级威胁保护](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7fc4d-125">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="7fc4d-126">必须为 ATP 安全附件使用动态交付选项 （请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)） 定义策略</span><span class="sxs-lookup"><span data-stu-id="7fc4d-126">Policies must be defined for ATP Safe Attachments using the dynamic delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="7fc4d-127">必须在 Office 365 中承载您的组织的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7fc4d-127">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="7fc4d-128">是否有为其动态传递不可用的方案？</span><span class="sxs-lookup"><span data-stu-id="7fc4d-128">Are there scenarios for which dynamic delivery is not available?</span></span>

<span data-ttu-id="7fc4d-p107">有某些方案中不支持动态送达。其中包括：</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p107">There are certain scenarios in which dynamic delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="7fc4d-131">在公用文件夹中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7fc4d-131">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="7fc4d-132">外出时的路由，然后再返回到使用自定义规则的用户的邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7fc4d-132">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="7fc4d-133">托管的邮箱超出传到其他位置，包括移动 （自动或手动） 的邮件存档文件夹</span><span class="sxs-lookup"><span data-stu-id="7fc4d-133">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="7fc4d-134">将被删除的邮件</span><span class="sxs-lookup"><span data-stu-id="7fc4d-134">Messages that are deleted</span></span>
    
- <span data-ttu-id="7fc4d-135">处于错误状态的用户的邮箱搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="7fc4d-135">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="7fc4d-p108">Exchange Online 管理员已在其中启用 Exclaimer 的环境。（请参阅[使用 ATP 动态传递和 Exclaimer 时都未将发送带附件的邮件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)）</span><span class="sxs-lookup"><span data-stu-id="7fc4d-p108">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7fc4d-138">相关主题</span><span class="sxs-lookup"><span data-stu-id="7fc4d-138">Related topics</span></span>

[<span data-ttu-id="7fc4d-139">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7fc4d-139">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="7fc4d-140">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="7fc4d-140">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="7fc4d-141">设置 Office 365 中的 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="7fc4d-141">Set up ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
  
[<span data-ttu-id="7fc4d-142">Office 365 中的 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="7fc4d-142">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)

[<span data-ttu-id="7fc4d-143">Office 365 安全性权限&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="7fc4d-143">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

