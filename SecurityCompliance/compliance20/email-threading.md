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
ms.openlocfilehash: 2340128f508a3be389afce86596f7e6395a0bb7e
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607467"
---
# <a name="email-threading"></a>电子邮件会话
请考虑一段转的电子邮件对话。在大多数情况下，在线程上的最后一个电子邮件将包含所有上述电子邮件; 中的内容查看最后一个电子邮件将提供完整的对话线程中发生的上下文。电子邮件线程标识此类的电子邮件，以便审阅者可以查看收集文档只需很短，而不会丢失任何上下文。

## <a name="what-does-email-threading-do"></a>电子邮件线程作用是什么？
每个电子邮件和 desconstructs 电子邮件线程分析其单个邮件;每个电子邮件是单个邮件链。然后，它分析中的工作集可确定电子邮件是否具有唯一的内容或者如果链完全不同的电子邮件中包含的所有电子邮件。最终电子邮件分为四个类别：
- Inclusives： 电子邮件中的最后一条具有唯一的内容，具有电子邮件的所有附件的内容完全包含此电子邮件中其他电子邮件中包含的。
- 含减去： 电子邮件中的最后一条具有唯一的内容，但电子邮件不包含一些其他的内容完全包含此电子邮件中的电子邮件中包含的附件。
- 非独占的副本： 非独占/非独占减去电子邮件的完全副本
- None： 此电子邮件的内容完全包含标记为非独占/非独占减号的至少一个电子邮件中。

## <a name="how-is-it-different-from-conversations-in-outlook"></a>它是如何在 Outlook 中对话不同？
概览，这听起来非常类似于在 Outlook 中的对话分组。但是，有一些重要的差别。请考虑获得分叉到两个对话; 电子邮件会话例如，某人响应以便对话中的最后两个电子邮件都具有唯一的内容不在对话中的最新的电子邮件。

Outlook 将仍然分组到单个会话; 电子邮件读取仅最后一个电子邮件将意味着缺少的倒数第二个电子邮件，其中还包含唯一内容上下文。由于电子邮件线程出每个电子邮件将解析为单个组件，并对它们进行比较，电子邮件线程会将标记两个最后两个电子邮件为 inclusives，确保不会错过任何上下文，只要您阅读所有电子邮件标记为非独占。