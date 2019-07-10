---
title: 什么是 EOP
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: 本简介文档将帮助您了解 Exchange Online Protection (EOP) 和一些重要的术语。 这适用于保护 Exchange Online 云托管邮箱的 Office 365 客户和保护本地邮箱 (如 Exchange Server 2016) 的 EOP 独立客户。
ms.openlocfilehash: b0d3aac6e2c7e70ce298309d2053a7d6bb5920c1
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599458"
---
## <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="a32c6-104">什么是 Exchange Online Protection (EOP)</span><span class="sxs-lookup"><span data-stu-id="a32c6-104">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="a32c6-105">Exchange Online Protection (EOP) 是一种基于云的电子邮件筛选服务, 可帮助组织抵御垃圾邮件和恶意软件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-105">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="a32c6-106">如果您的邮箱在 Office 365 中, 它们将自动受 EOP 保护, 因为它是服务的一部分。</span><span class="sxs-lookup"><span data-stu-id="a32c6-106">If you have mailboxes in Office 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="a32c6-107">这包括在 Office 365 和内部部署中具有邮箱的组织, 这些邮箱通常称为混合方案。</span><span class="sxs-lookup"><span data-stu-id="a32c6-107">This includes organizations that have mailboxes in both Office 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="a32c6-108">此外, EOP 还可用于在云中没有邮箱但要保护其内部部署邮箱的客户。</span><span class="sxs-lookup"><span data-stu-id="a32c6-108">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premise mailboxes.</span></span> 

<span data-ttu-id="a32c6-109">EOP 尝试筛选出垃圾邮件, 使您的收件箱不清楚用户不希望看到的内容。</span><span class="sxs-lookup"><span data-stu-id="a32c6-109">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="a32c6-110">通常情况下, 垃圾邮件会传递到 "垃圾邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a32c6-110">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="a32c6-111">一些用户希望进行检查以确保筛选正在执行所需的操作, 因此 "垃圾邮件" 文件夹是用户自己进行签的简单方法。</span><span class="sxs-lookup"><span data-stu-id="a32c6-111">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="a32c6-112">如果垃圾邮件自动进入垃圾邮件文件夹, 这是一件好事。</span><span class="sxs-lookup"><span data-stu-id="a32c6-112">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="a32c6-113">该服务将根据默认或自定义管理员设置的状态, 执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="a32c6-113">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="a32c6-114">换句话说, 用户不应担心在 "垃圾邮件" 文件夹中看到大量垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-114">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="a32c6-115">如果管理员更喜欢移动所有垃圾邮件, 则应配置隔离。</span><span class="sxs-lookup"><span data-stu-id="a32c6-115">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="a32c6-116">有关更多详细信息, 请参阅[在 Office 365 文章中隔离电子](../quarantine-email-messages.md)邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-116">For more details, see the [Quarantine email messages in Office 365](../quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="a32c6-117">重要术语</span><span class="sxs-lookup"><span data-stu-id="a32c6-117">Important terms</span></span>

<span data-ttu-id="a32c6-118">**入站:** 将进入 Office 365 的邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-118">**Inbound:** Messages that are coming into Office 365.</span></span>

<span data-ttu-id="a32c6-119">**出站:** 来自 Office 365 的邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-119">**Outbound:** Messages that are going out of Office 365.</span></span>

<span data-ttu-id="a32c6-120">**Internal:** 来自组织内部的某个人的邮件到组织内的某个人。</span><span class="sxs-lookup"><span data-stu-id="a32c6-120">**Internal:** Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="a32c6-121">这包括在混合方案中的客户和一个邮箱可以在本地, 另一个邮箱位于云中。</span><span class="sxs-lookup"><span data-stu-id="a32c6-121">This includes customers who are in hybrid scenarios and one mailbox could be on-premise and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="a32c6-122">**假负 (FN):** 垃圾邮件和其他不正确发送到收件箱的垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-122">**False Negative (FN):** Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="a32c6-123">**误报 (FP):** 错误地被标记为垃圾邮件并放入垃圾电子邮件文件夹或隔离的合法邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-123">**False Positive (FP):** Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="a32c6-124">**垃圾邮件, 也称为主动电子邮件:** 这是商业广告、连锁信函、政治邮件等的形式。这是一封电子邮件, 用户不会在试图提出产品或试图提交欺诈行为的垃圾邮件发件人注册和发件人。</span><span class="sxs-lookup"><span data-stu-id="a32c6-124">**Spam, also known as unsolicited e-mail:** This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="a32c6-125">**网络钓鱼:**"网络钓鱼" 是一种特殊类型的垃圾邮件, 旨在欺骗您出于提交身份盗窃或欺诈行为的目的而提供个人信息。</span><span class="sxs-lookup"><span data-stu-id="a32c6-125">**Phish:** Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="a32c6-126">这种类型的邮件通常包含恶意链接或附件, 但并不总是。</span><span class="sxs-lookup"><span data-stu-id="a32c6-126">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="a32c6-127">**哄骗:** 哄骗是指当垃圾邮件制造者伪造发件人邮件头, 以便邮件看起来来自于实际来源以外的其他人或其他地方。</span><span class="sxs-lookup"><span data-stu-id="a32c6-127">**Spoof:** Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="a32c6-128">这可以是垃圾邮件, 但最常用于网络钓鱼用户。</span><span class="sxs-lookup"><span data-stu-id="a32c6-128">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="a32c6-129">**模拟:** 这种类型的垃圾邮件也是伪造发件人地址的一种方法, 但通过修改名称或域的一部分使其看起来像真实的来源一样实现。</span><span class="sxs-lookup"><span data-stu-id="a32c6-129">**Impersonation:** This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="a32c6-130">例如, Bi11@micr0s0ft.com, 即 Bill 中的 "l" 实际上是数字十一, 而 Microsoft 中的 "o" 替换为数字零。</span><span class="sxs-lookup"><span data-stu-id="a32c6-130">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="a32c6-131">**批量:** 通常情况下, 用户会请求批量邮件, 尽管有时会在公司向其他公司销售信息时间接使用。</span><span class="sxs-lookup"><span data-stu-id="a32c6-131">**Bulk:** Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="a32c6-132">用户有意注册批量邮件 (如 newletters), 但稍后又忘记了垃圾邮件, 这很常见。</span><span class="sxs-lookup"><span data-stu-id="a32c6-132">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="a32c6-133">当批量邮件发送超过用户的注册和投诉级别变得过高时, 批量邮件将成为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="a32c6-133">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
