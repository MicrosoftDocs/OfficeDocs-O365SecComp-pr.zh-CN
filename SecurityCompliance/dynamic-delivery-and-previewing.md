---
title: 使用 Office 365 ATP 安全附件进行动态传递和预览
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/19/2019
audience: Admin
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
ms.openlocfilehash: 2f965c119e9c4fca15e43d281dfc2d00d2c79c23
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599898"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="34094-103">使用 Office 365 ATP 安全附件进行动态传递和预览</span><span class="sxs-lookup"><span data-stu-id="34094-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="34094-104">概述</span><span class="sxs-lookup"><span data-stu-id="34094-104">Overview</span></span>

<span data-ttu-id="34094-105">动态传递是可选择用于[ATP 安全附件](atp-safe-attachments.md)的选项。</span><span class="sxs-lookup"><span data-stu-id="34094-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="34094-106">阅读本文, 了解有关[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的动态传递和附件预览功能的信息。</span><span class="sxs-lookup"><span data-stu-id="34094-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="34094-107">为您的组织[设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)时, 有几个选项可用于处理电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="34094-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="34094-108">其中包括 "**阻止**"、"**替换**" 和 "**动态传递**"。</span><span class="sxs-lookup"><span data-stu-id="34094-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="34094-109">根据配置 ATP 安全附件策略的方式, 在扫描附件时, 电子邮件收件人可能会遇到电子邮件传递的轻微延迟。</span><span class="sxs-lookup"><span data-stu-id="34094-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="34094-110">若要避免邮件延迟, 请选择 "**动态传递**"。</span><span class="sxs-lookup"><span data-stu-id="34094-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>
  
## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="34094-111">动态传递的工作原理</span><span class="sxs-lookup"><span data-stu-id="34094-111">How Dynamic Delivery works</span></span>
  
<span data-ttu-id="34094-112">动态传递通过将电子邮件的正文发送给具有每个电子邮件附件占位符的收件人来消除电子邮件延迟。</span><span class="sxs-lookup"><span data-stu-id="34094-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="34094-113">该占位符将一直保留, 直到通过[ATP 安全附件](atp-safe-attachments.md)扫描并确定附件的副本是安全的。</span><span class="sxs-lookup"><span data-stu-id="34094-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span> 

- <span data-ttu-id="34094-114">每个附件被清除后, 即可打开或下载。</span><span class="sxs-lookup"><span data-stu-id="34094-114">As each attachment is cleared, it is available to open or download.</span></span> 

- <span data-ttu-id="34094-115">如果某个附件被确定为恶意附件, 则会将其发送到隔离区, 其中组织的安全团队 (如 Office 365 全局管理员或安全管理员) 的用户可以[在 Office 365 中管理隔离的邮件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="34094-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="34094-116">大多数 Pdf 和 Office 文档可在 ATP 扫描进行过程中在安全模式下进行预览。</span><span class="sxs-lookup"><span data-stu-id="34094-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="34094-117">如果附件与动态传递预览器不兼容, 则在完成 ATP 安全附件扫描之前, 电子邮件收件人会看到一个附件占位符。</span><span class="sxs-lookup"><span data-stu-id="34094-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="34094-118">如果您使用的是移动设备, 并且 Pdf 在最初不在动态传递预览器中呈现, 请尝试使用移动浏览器登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="34094-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="34094-119">通过动态传递, 用户可以立即阅读并回复他们的电子邮件, 同时分析他们的附件。</span><span class="sxs-lookup"><span data-stu-id="34094-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span> 

<span data-ttu-id="34094-120">ATP 安全附件扫描发生在 Office 365 数据所在的同一个区域中。</span><span class="sxs-lookup"><span data-stu-id="34094-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="34094-121">有关数据中心地理位置的详细信息, 请参阅[您的数据位于何处？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="34094-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span> 
  
## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="34094-122">当有人转发包含附件的电子邮件时, 会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="34094-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="34094-123">假定组织正在对其[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)使用动态传递, 并且有人收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34094-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="34094-124">现在, 假设某人将电子邮件转发给其他人。</span><span class="sxs-lookup"><span data-stu-id="34094-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="34094-125">会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="34094-125">What happens?</span></span> <span data-ttu-id="34094-126">这取决于其他收件人是否包含在 ATP 安全附件策略中。</span><span class="sxs-lookup"><span data-stu-id="34094-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>
  
- <span data-ttu-id="34094-127">如果使用动态传递选项的 ATP 安全附件策略覆盖某个收件人, 则收件人将看到该占位符, 并能够预览兼容文件。</span><span class="sxs-lookup"><span data-stu-id="34094-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>
    
- <span data-ttu-id="34094-128">如果 ATP 安全附件策略未涵盖某个收件人, 则电子邮件和附件将继续进行, 而不需要任何 ATP 安全附件扫描或附件占位符。</span><span class="sxs-lookup"><span data-stu-id="34094-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>
    
## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="34094-129">动态传递所需的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="34094-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="34094-130">您的组织必须具有[Office 365 高级威胁防护](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="34094-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>
    
- <span data-ttu-id="34094-131">必须使用动态传递选项为 ATP 安全附件定义策略 (请参阅[在 Office 365 中设置 Atp 安全附件策略](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="34094-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>
    
- <span data-ttu-id="34094-132">您的组织的电子邮件必须托管在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="34094-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="34094-133">尽管[office 365 高级威胁防护可用于任何 SMTP 邮件传输代理](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp)(如 Exchange Server), 但 ATP 安全附件的动态传递选项要求组织的电子邮件托管在 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="34094-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="34094-134">如果您的电子邮件不是托管在 Office 365 中, 请选择不同的[ATP 安全附件策略选项](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), 如**Block**。</span><span class="sxs-lookup"><span data-stu-id="34094-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>
    
## <a name="additional-considerations"></a><span data-ttu-id="34094-135">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="34094-135">Additional considerations</span></span>

<span data-ttu-id="34094-136">在某些情况下, 不支持动态传递。</span><span class="sxs-lookup"><span data-stu-id="34094-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="34094-137">其中包括以下项：</span><span class="sxs-lookup"><span data-stu-id="34094-137">These include the following:</span></span>
  
- <span data-ttu-id="34094-138">公用文件夹中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="34094-138">Email messages that are in public folders</span></span>
    
- <span data-ttu-id="34094-139">使用自定义规则从用户邮箱中路由的电子邮件, 然后再返回到该用户的邮箱</span><span class="sxs-lookup"><span data-stu-id="34094-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>
    
- <span data-ttu-id="34094-140">移动 (自动或手动) 从托管邮箱移到其他位置 (包括存档文件夹) 的电子邮件</span><span class="sxs-lookup"><span data-stu-id="34094-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>
    
- <span data-ttu-id="34094-141">删除的电子邮件</span><span class="sxs-lookup"><span data-stu-id="34094-141">Email messages that are deleted</span></span>
    
- <span data-ttu-id="34094-142">处于错误状态的用户的邮箱搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="34094-142">A user's mailbox search folder that is in an error state</span></span>
    
- <span data-ttu-id="34094-143">Exchange Online 管理员已在其中启用 Exclaimer 的环境。</span><span class="sxs-lookup"><span data-stu-id="34094-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="34094-144">若要解决此问题, 请参阅[使用 ATP 动态传递和 Exclaimer 时, 带有附件的邮件不会送达](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="34094-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="34094-145">使用[安全/多用途 Internet 邮件扩展 (S/MIME)](s-mime-for-message-signing-and-encryption.md)加密的邮件</span><span class="sxs-lookup"><span data-stu-id="34094-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="34094-146">在不支持动态传递的情况下, ATP 安全附件不会扫描电子邮件。</span><span class="sxs-lookup"><span data-stu-id="34094-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="34094-147">但是, 将检查包含 Url 的附件的电子邮件, 具体取决于您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)的配置方式。</span><span class="sxs-lookup"><span data-stu-id="34094-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="34094-148">在这些情况下, 将检查电子邮件和 Office 文件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="34094-148">In these cases, URLs in email messages and Office files are checked.</span></span>
