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
ms.locfileid: "32243803"
---
# <a name="email-threading"></a>电子邮件会话

考虑一段时间的电子邮件对话。 在大多数情况下, 线程上的最后一个电子邮件将包含上述所有电子邮件的内容;查看最后一个电子邮件将提供在线程中发生的对话的完整上下文。 电子邮件线程识别此类电子邮件, 以便审阅者可以在不丢失任何上下文的情况下查看所收集的文档的一部分。

## <a name="what-does-email-threading-do"></a>电子邮件线程处理的功能是什么？

电子邮件线程分析每封电子邮件并将其 desconstructs 给各个邮件;每封电子邮件是单个邮件的链。 然后, 它会分析工作集中的所有电子邮件, 以确定电子邮件是否具有唯一内容, 或者如果该链完全包含在不同的电子邮件中。 在最终电子邮件中分为四个类别:

- **包含**: 电子邮件中的最后一封邮件具有唯一内容, 并且电子邮件包含其他电子邮件中包含的所有附件, 这些附件中的内容完全包含在此电子邮件中。


- **包含减去**: 电子邮件中的最后一封邮件具有唯一内容, 但电子邮件不包含其他电子邮件中包含的某些附件, 这些附件中的内容完全包含在此电子邮件中。

- **包含副本**: 包含/包含的减号电子邮件的精确副本

- **None**: 此电子邮件的内容完全包含在至少一个标记为包含/包含减号的电子邮件中。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>它与 Outlook 中的对话有何不同？
这听起来非常类似于 Outlook 中的对话分组。 但是, 存在一些重要区别。 考虑与两个对话分叉的电子邮件对话;例如, 有人对对话中不是最新的电子邮件做出响应, 因此对话中的最后两封电子邮件具有独特的内容。

Outlook 仍会将电子邮件组合到单个对话中;仅读取最后一个电子邮件意味着缺少第二到最后一个电子邮件的上下文, 这也会包含唯一内容。 由于电子邮件线程处理将每封电子邮件解析为单个组件并对它们进行比较, 因此电子邮件线程处理会将最后两封电子邮件标记为 inclusives, 以确保您在阅读所有标记为非独占的电子邮件时不会丢失任何上下文。