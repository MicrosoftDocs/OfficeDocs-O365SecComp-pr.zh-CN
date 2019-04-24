---
title: 电子邮件会话
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ca4823ecfc06ddc0ef6f6840ad55fec492ac472c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258790"
---
# <a name="email-threading"></a><span data-ttu-id="14841-102">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="14841-102">Email threading</span></span>

<span data-ttu-id="14841-103">考虑一段时间的电子邮件对话。</span><span class="sxs-lookup"><span data-stu-id="14841-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="14841-104">在大多数情况下, 线程上的最后一个电子邮件将包含上述所有电子邮件的内容;查看最后一个电子邮件将提供在线程中发生的对话的完整上下文。</span><span class="sxs-lookup"><span data-stu-id="14841-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="14841-105">电子邮件线程识别此类电子邮件, 以便审阅者可以在不丢失任何上下文的情况下查看所收集的文档的一部分。</span><span class="sxs-lookup"><span data-stu-id="14841-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="14841-106">电子邮件线程处理的功能是什么？</span><span class="sxs-lookup"><span data-stu-id="14841-106">What does email threading do?</span></span>

<span data-ttu-id="14841-107">电子邮件线程分析每封电子邮件并将其 desconstructs 给各个邮件;每封电子邮件是单个邮件的链。</span><span class="sxs-lookup"><span data-stu-id="14841-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="14841-108">然后, 它会分析工作集中的所有电子邮件, 以确定电子邮件是否具有唯一内容, 或者如果该链完全包含在不同的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="14841-108">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="14841-109">在最终电子邮件中分为四个类别:</span><span class="sxs-lookup"><span data-stu-id="14841-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="14841-110">**包含**: 电子邮件中的最后一封邮件具有唯一内容, 并且电子邮件包含其他电子邮件中包含的所有附件, 这些附件中的内容完全包含在此电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="14841-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="14841-111">**包含减去**: 电子邮件中的最后一封邮件具有唯一内容, 但电子邮件不包含其他电子邮件中包含的某些附件, 这些附件中的内容完全包含在此电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="14841-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="14841-112">**包含副本**: 包含/包含的减号电子邮件的精确副本</span><span class="sxs-lookup"><span data-stu-id="14841-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="14841-113">**None**: 此电子邮件的内容完全包含在至少一个标记为包含/包含减号的电子邮件中。</span><span class="sxs-lookup"><span data-stu-id="14841-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="14841-114">它与 Outlook 中的对话有何不同？</span><span class="sxs-lookup"><span data-stu-id="14841-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="14841-115">这听起来非常类似于 Outlook 中的对话分组。</span><span class="sxs-lookup"><span data-stu-id="14841-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="14841-116">但是, 存在一些重要区别。</span><span class="sxs-lookup"><span data-stu-id="14841-116">However, there are some important distinctions.</span></span> <span data-ttu-id="14841-117">考虑与两个对话分叉的电子邮件对话;例如, 有人对对话中不是最新的电子邮件做出响应, 因此对话中的最后两封电子邮件具有独特的内容。</span><span class="sxs-lookup"><span data-stu-id="14841-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="14841-118">Outlook 仍会将电子邮件组合到单个对话中;仅读取最后一个电子邮件意味着缺少第二到最后一个电子邮件的上下文, 这也会包含唯一内容。</span><span class="sxs-lookup"><span data-stu-id="14841-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="14841-119">由于电子邮件线程处理将每封电子邮件解析为单个组件并对它们进行比较, 因此电子邮件线程处理会将最后两封电子邮件标记为 inclusives, 以确保您在阅读所有标记为非独占的电子邮件时不会丢失任何上下文。</span><span class="sxs-lookup"><span data-stu-id="14841-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>