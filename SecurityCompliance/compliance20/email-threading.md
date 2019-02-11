---
title: 电子邮件会话
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d4328971a6b13c60c4d8b9f5b6db310d72a5b215
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29705993"
---
# <a name="email-threading"></a><span data-ttu-id="8e3d1-102">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="8e3d1-102">Email threading</span></span>

<span data-ttu-id="8e3d1-p101">请考虑一段转的电子邮件对话。在大多数情况下，在线程上的最后一个电子邮件将包含所有上述电子邮件; 中的内容查看最后一个电子邮件将提供完整的对话线程中发生的上下文。电子邮件线程标识此类的电子邮件，以便审阅者可以查看收集文档只需很短，而不会丢失任何上下文。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-p101">Consider an email conversation that has been going on for a while. In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread. Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="8e3d1-106">电子邮件线程作用是什么？</span><span class="sxs-lookup"><span data-stu-id="8e3d1-106">What does email threading do?</span></span>

<span data-ttu-id="8e3d1-p102">每个电子邮件和 desconstructs 电子邮件线程分析其单个邮件;每个电子邮件是单个邮件链。然后，它分析中的工作集可确定电子邮件是否具有唯一的内容或者如果链完全不同的电子邮件中包含的所有电子邮件。最终电子邮件分为四个类别：</span><span class="sxs-lookup"><span data-stu-id="8e3d1-p102">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages. Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email. In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="8e3d1-110">**非独占**： 电子邮件中的最后一条具有唯一的内容，具有电子邮件的所有附件的内容完全包含此电子邮件中其他电子邮件中包含的。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="8e3d1-111">**非独占减去**： 电子邮件中的最后一条具有唯一的内容，但电子邮件不包含一些其他的内容完全包含此电子邮件中的电子邮件中包含的附件。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="8e3d1-112">**非独占的副本**： 非独占/非独占减去电子邮件的完全副本</span><span class="sxs-lookup"><span data-stu-id="8e3d1-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="8e3d1-113">**None**： 完全的标记为非独占/非独占减号至少一个电子邮件中包含此电子邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="8e3d1-114">它是如何在 Outlook 中对话不同？</span><span class="sxs-lookup"><span data-stu-id="8e3d1-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="8e3d1-p103">概览，这听起来非常类似于在 Outlook 中的对话分组。但是，有一些重要的差别。请考虑获得分叉到两个对话; 电子邮件会话例如，某人响应以便对话中的最后两个电子邮件都具有唯一的内容不在对话中的最新的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-p103">At a glance, this sounds very similar to conversation groupings in Outlook. However, there are some important distinctions. Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="8e3d1-p104">Outlook 将仍然分组到单个会话; 电子邮件读取仅最后一个电子邮件将意味着缺少的倒数第二个电子邮件，其中还包含唯一内容上下文。由于电子邮件线程出每个电子邮件将解析为单个组件，并对它们进行比较，电子邮件线程会将标记两个最后两个电子邮件为 inclusives，确保不会错过任何上下文，只要您阅读所有电子邮件标记为非独占。</span><span class="sxs-lookup"><span data-stu-id="8e3d1-p104">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content. Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>