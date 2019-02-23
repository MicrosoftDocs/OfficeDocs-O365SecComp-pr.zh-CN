---
title: 使用 Office 365 ATP 安全附件进行动态传递和预览
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 设置 ATP 安全附件策略时, 请选择 "动态传递" 以避免邮件延迟, 并使用户能够预览正在扫描的附件。
ms.openlocfilehash: 1fb221d28a4089db8a4278903107c610d6825f5e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218392"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="05fe7-103">使用 Office 365 ATP 安全附件进行动态传递和预览</span><span class="sxs-lookup"><span data-stu-id="05fe7-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

<span data-ttu-id="05fe7-p101">**摘要**: 动态传递是可选择用于[ATP 安全附件](atp-safe-attachments.md)的选项。阅读本文, 了解有关[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的动态传递和附件预览功能的信息。</span><span class="sxs-lookup"><span data-stu-id="05fe7-p101">**Summary**: Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md). Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="05fe7-p102">为您的组织[设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)时, 有几个选项可用于处理电子邮件附件。其中包括 "**阻止**"、"**替换**" 和 "**动态传递**"。根据配置 ATP 安全附件策略的方式, 在扫描附件时, 电子邮件收件人可能会遇到电子邮件传递的轻微延迟。若要避免邮件延迟, 请选择 "**动态传递**"。</span><span class="sxs-lookup"><span data-stu-id="05fe7-p102">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled. These include **Block**, **Replace**, and **Dynamic Delivery**. Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned. To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="05fe7-110">动态传递的工作原理</span><span class="sxs-lookup"><span data-stu-id="05fe7-110">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="05fe7-p103">动态传递通过将电子邮件的正文发送给具有每个电子邮件附件占位符的收件人来消除电子邮件延迟。该占位符将一直保留, 直到通过[ATP 安全附件](atp-safe-attachments.md)扫描并确定附件的副本是安全的。</span><span class="sxs-lookup"><span data-stu-id="05fe7-p103">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment. The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="05fe7-113">每个附件被清除后, 即可打开或下载。</span><span class="sxs-lookup"><span data-stu-id="05fe7-113">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="05fe7-114">如果某个附件被确定为恶意附件, 则会将其发送到隔离区, 其中组织的安全团队 (如 Office 365 全局管理员或安全管理员) 的用户可以[在 Office 365 中管理隔离的邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="05fe7-114">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="05fe7-p104">大多数 pdf 和 Office 文档可在 ATP 扫描进行过程中在安全模式下进行预览。如果附件与动态传递预览器不兼容, 则在完成 ATP 安全附件扫描之前, 电子邮件收件人会看到一个附件占位符。</span><span class="sxs-lookup"><span data-stu-id="05fe7-p104">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway. If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="05fe7-117">如果您使用的是移动设备, 并且 pdf 在最初不在动态传递预览器中呈现, 请尝试使用移动浏览器登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="05fe7-117">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="05fe7-118">通过动态传递, 用户可以立即阅读并回复他们的电子邮件, 同时分析他们的附件。</span><span class="sxs-lookup"><span data-stu-id="05fe7-118">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="05fe7-p105">ATP 安全附件扫描发生在 Office 365 数据所在的同一个区域中。有关数据中心地理位置的详细信息, 请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="05fe7-p105">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides. For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="05fe7-121">当有人转发包含附件的电子邮件时, 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="05fe7-121">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="05fe7-p106">假定组织正在对其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)使用动态传递, 并且有人收到包含附件的电子邮件。现在, 假设某人将电子邮件转发给其他人。会发生什么情况？这取决于其他收件人是否包含在 ATP 安全附件策略中。</span><span class="sxs-lookup"><span data-stu-id="05fe7-p106">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment. Now suppose that person forwards the email message to someone else. What happens? It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="05fe7-126">如果使用动态传递选项的 ATP 安全附件策略覆盖某个收件人, 则收件人将看到该占位符, 并能够预览兼容文件。</span><span class="sxs-lookup"><span data-stu-id="05fe7-126">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="05fe7-127">如果 atp 安全附件策略未涵盖某个收件人, 则电子邮件和附件将会通过, 而不会包含 ATP 安全附件扫描或附件占位符。</span><span class="sxs-lookup"><span data-stu-id="05fe7-127">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="05fe7-128">动态传递所需的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="05fe7-128">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="05fe7-129">您的组织必须具有[Office 365 高级威胁防护](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="05fe7-129">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="05fe7-130">必须使用动态传递选项为 ATP 安全附件定义策略 (请参阅[在 Office 365 中设置 atp 安全附件策略](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="05fe7-130">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="05fe7-131">您的组织的电子邮件必须托管在 Office 365 中</span><span class="sxs-lookup"><span data-stu-id="05fe7-131">Your organization's email must be hosted in Office 365</span></span>
    
## <a name="are-there-scenarios-for-which-dynamic-delivery-is-not-available"></a><span data-ttu-id="05fe7-132">是否存在动态传递不可用的方案？</span><span class="sxs-lookup"><span data-stu-id="05fe7-132">Are there scenarios for which Dynamic Delivery is not available?</span></span>

<span data-ttu-id="05fe7-p107">在某些情况下, 不支持动态传递。其中包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="05fe7-p107">There are certain scenarios in which Dynamic Delivery is not supported. These include the following:</span></span>
  
- <span data-ttu-id="05fe7-135">公用文件夹中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="05fe7-135">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="05fe7-136">使用自定义规则从用户邮箱中路由的电子邮件, 然后再返回到该用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="05fe7-136">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="05fe7-137">移动 (自动或手动) 从托管邮箱移到其他位置 (包括存档文件夹) 的电子邮件</span><span class="sxs-lookup"><span data-stu-id="05fe7-137">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="05fe7-138">删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="05fe7-138">Email messages that are deleted</span></span>
    
- <span data-ttu-id="05fe7-139">处于错误状态的用户的邮箱搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="05fe7-139">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="05fe7-p108">Exchange Online 管理员已在其中启用 Exclaimer 的环境。若要解决此问题, 请参阅[使用 ATP 动态传递和 Exclaimer 时, 带有附件的邮件不会送达](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="05fe7-p108">Environments in which an Exchange Online admin has enabled Exclaimer. To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="05fe7-142">使用[安全/多用途 Internet 邮件扩展 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的邮件</span><span class="sxs-lookup"><span data-stu-id="05fe7-142">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

