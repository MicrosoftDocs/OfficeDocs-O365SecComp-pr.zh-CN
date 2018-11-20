---
title: 动态传递和与 Office 365 ATP 安全附件预览
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
description: 将您 ATP 附件安全策略设置，当您选择动态传递，以避免消息延迟和使人们可以预览正在被扫描的附件。
ms.openlocfilehash: a272253594dda7ea720bb1e8b59e38e870f2f036
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238424"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="457e1-103">动态传递和与 Office 365 ATP 安全附件预览</span><span class="sxs-lookup"><span data-stu-id="457e1-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="457e1-p101">**摘要**： 动态传递是可以为[ATP 安全附件](atp-safe-attachments.md)选择一个选项。阅读此文，了解有关动态交付和[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的附件预览功能。</span><span class="sxs-lookup"><span data-stu-id="457e1-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="457e1-106">动态传递的工作原理</span><span class="sxs-lookup"><span data-stu-id="457e1-106">How Dynamic Delivery works</span></span>

<span data-ttu-id="457e1-p102">当[ATP 安全附件策略设置](set-up-atp-safe-attachments-policies.md)为贵组织有多种选择如何处理电子邮件附件。其中包括**阻止**、**替换**和**动态传递**。根据 ATP 安全附件策略的配置方式，电子邮件收件人可以次要在遇到延迟电子邮件传递时对其附件进行扫描。若要避免出现邮件延迟，请选择**动态传递**。</span><span class="sxs-lookup"><span data-stu-id="457e1-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients can experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
<span data-ttu-id="457e1-p103">动态传递通过将通过一封电子邮件的正文发送给收件人提供每个电子邮件附件的占位符，消除了电子邮件延迟。扫描附件的副本并将其由为安全起见[ATP 安全附件](atp-safe-attachments.md)一直占位符。大多数 Pdf 和 Office ATP 扫描正在进行时，可以在安全模式下预览文档。如果某个附件不可与动态传递预览器兼容，电子邮件收件人请参阅附件占位符，直到 ATP 安全附件扫描已完成。</span><span class="sxs-lookup"><span data-stu-id="457e1-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md). Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

- <span data-ttu-id="457e1-115">每个附件处于清除状态，它是可用于打开或下载。</span><span class="sxs-lookup"><span data-stu-id="457e1-115">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="457e1-116">如果附件确定恶意，它是发送到隔离，某人贵组织的安全工作组 （例如 Office 365 全局管理员或安全管理员） 可以[管理 Office 365 中的隔离的邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="457e1-116">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="457e1-117">使用动态传递电子邮件收件人可以读取和对其电子邮件立即响应，了解，正在分析其附件。</span><span class="sxs-lookup"><span data-stu-id="457e1-117">With Dynamic Delivery, email recipients can read and respond to their email messages right away, knowing that their attachments are being analyzed.</span></span> 

<span data-ttu-id="457e1-p104">ATP 安全附件扫描考虑放置在 Office 365 数据所在的同一区域中。有关数据中心地理区域的详细信息，请参阅[其中是位于数据？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="457e1-p104">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="457e1-120">当某人的转发电子邮件时，会发生什么情况包含附件？</span><span class="sxs-lookup"><span data-stu-id="457e1-120">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="457e1-p105">假设其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)中，为组织使用动态传递有人收到包含附件的电子邮件。现在假设其即将转发给其他人的电子邮件。会发生什么情况？这取决于是否 ATP 安全附件策略中包含其他收件人。</span><span class="sxs-lookup"><span data-stu-id="457e1-p105">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person is about to forward the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="457e1-125">如果收件人使用动态交付选项 ATP 安全附件策略涵盖，收件人会占位符，看到可以预览兼容的文件中。</span><span class="sxs-lookup"><span data-stu-id="457e1-125">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="457e1-126">如果收件人不受 ATP 安全附件策略，然后电子邮件和附件将经过，不含 ATP 安全扫描的附件或附件占位符。</span><span class="sxs-lookup"><span data-stu-id="457e1-126">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="457e1-127">有什么要求动态传递工作？</span><span class="sxs-lookup"><span data-stu-id="457e1-127">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="457e1-128">您的组织必须具有[Office 365 高级威胁保护](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="457e1-128">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="457e1-129">必须为 ATP 安全附件使用动态交付选项 （请参阅[Set up Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)） 定义策略</span><span class="sxs-lookup"><span data-stu-id="457e1-129">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="457e1-130">必须在 Office 365 中承载您的组织的电子邮件</span><span class="sxs-lookup"><span data-stu-id="457e1-130">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="457e1-131">是否有为其动态传递不可用的方案？</span><span class="sxs-lookup"><span data-stu-id="457e1-131">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="457e1-p106">有某些方案中不支持动态送达。其中包括：</span><span class="sxs-lookup"><span data-stu-id="457e1-p106">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="457e1-134">在公用文件夹中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="457e1-134">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="457e1-135">外出时的路由，然后再返回到使用自定义规则的用户的邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="457e1-135">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="457e1-136">托管的邮箱超出传到其他位置，包括移动 （自动或手动） 的邮件存档文件夹</span><span class="sxs-lookup"><span data-stu-id="457e1-136">Messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="457e1-137">将被删除的邮件</span><span class="sxs-lookup"><span data-stu-id="457e1-137">Messages that are deleted</span></span>
    
- <span data-ttu-id="457e1-138">处于错误状态的用户的邮箱搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="457e1-138">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="457e1-p107">Exchange Online 管理员已在其中启用 Exclaimer 的环境。（请参阅[使用 ATP 动态传递和 Exclaimer 时都未将发送带附件的邮件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)）</span><span class="sxs-lookup"><span data-stu-id="457e1-p107">Environments in which an Exchange Online admin has enabled Exclaimer. (See [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery))</span></span>

- <span data-ttu-id="457e1-141">使用安全/多用途 Internet 邮件扩展 ([S/MIME](s-mime-for-message-signing-and-encryption.md)) 加密的邮件</span><span class="sxs-lookup"><span data-stu-id="457e1-141">Messages encrypted with Secure/Multipurpose Internet Mail Extensions ([S/MIME](s-mime-for-message-signing-and-encryption.md))</span></span>
    
