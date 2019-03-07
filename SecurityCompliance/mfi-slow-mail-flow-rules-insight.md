---
title: 慢邮件流规则见解
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 5/3/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: 管理员可以了解 Office 365 Security & 合规中心的邮件流仪表板中的邮件流规则的慢速见解。
ms.openlocfilehash: 8188ee0da15ac337499866783ca4f2d893062d5b
ms.sourcegitcommit: 6aa82374eef09d2c1921f93bda3eabeeb28aadeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30454874"
---
# <a name="slow-mail-flow-rules-insight"></a><span data-ttu-id="bef55-103">慢邮件流规则见解</span><span class="sxs-lookup"><span data-stu-id="bef55-103">Slow mail flow rules insight</span></span>

<span data-ttu-id="bef55-104">低效率的邮件流规则 (也称为传输规则) 可能会导致贵组织的邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="bef55-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="bef55-105">此洞察力可报告影响组织的邮件流的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="bef55-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="bef55-106">这些规则类型的示例如下:</span><span class="sxs-lookup"><span data-stu-id="bef55-106">Examples of these types of rules are:</span></span>

- <span data-ttu-id="bef55-107">使用的条件**是**大型组的成员。</span><span class="sxs-lookup"><span data-stu-id="bef55-107">Conditions that use **Is member of** for large groups.</span></span>

- <span data-ttu-id="bef55-108">使用复杂正则表达式 (regex) 模式匹配的条件。</span><span class="sxs-lookup"><span data-stu-id="bef55-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>

- <span data-ttu-id="bef55-109">使用附件中的内容检查的条件。</span><span class="sxs-lookup"><span data-stu-id="bef55-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="bef55-110">这些洞察力将帮助您识别和微调邮件流规则, 以帮助减少邮件流延迟。</span><span class="sxs-lookup"><span data-stu-id="bef55-110">The insight will help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Office 365 Security & 合规中心的邮件流仪表板中的邮件流规则速度较慢](media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

<span data-ttu-id="bef55-112">单击 "**查看详细信息**" 时, 将显示一个弹出窗格, 可在其中查看规则。</span><span class="sxs-lookup"><span data-stu-id="bef55-112">When you click **View details**, a flyout pane appears where you can review the rule.</span></span> <span data-ttu-id="bef55-113">在浮出控件窗格中, 也可以单击 "**查看示例消息**" 来查看规则所影响的邮件类型。</span><span class="sxs-lookup"><span data-stu-id="bef55-113">In the flyout pane, can also click **view sample messages** to see what kind of messages are impacted by the rule.</span></span>

![在邮件流仪表板中单击慢速邮件流规则中的 "查看详细信息" 后的浮出控件窗格](media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)
