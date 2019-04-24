---
title: 什么是 EOP
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: laurawi
ms.date: 2/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: 本简介文档将帮助您了解 Exchange Online Protection (EOP) 和一些重要的术语。 这适用于保护 exchange Online 云托管邮箱的 Office 365 客户和保护本地邮箱 (如 Exchange Server 2016) 的 EOP 独立客户。
ms.openlocfilehash: f23f28b5c15c7057d1fd8ec77cce67bf1746410c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256470"
---
## <a name="what-is-exchange-online-protection-eop"></a>什么是 Exchange Online Protection (EOP)

Exchange Online Protection (EOP) 是一种基于云的电子邮件筛选服务, 可帮助组织抵御垃圾邮件和恶意软件。 如果您的邮箱在 Office 365 中, 它们将自动受 EOP 保护, 因为它是服务的一部分。 这包括在 Office 365 和内部部署中具有邮箱的组织, 这些邮箱通常称为混合方案。 此外, EOP 还可用于在云中没有邮箱但要保护其内部部署邮箱的客户。 

EOP 尝试筛选出垃圾邮件, 使您的收件箱不清楚用户不希望看到的内容。 通常情况下, 垃圾邮件会传递到 "垃圾邮件" 文件夹。 一些用户希望进行检查以确保筛选正在执行所需的操作, 因此 "垃圾邮件" 文件夹是用户自己进行签的简单方法。  

> [!TIP]
> 如果垃圾邮件自动进入垃圾邮件文件夹, 这是一件好事。 该服务将根据默认或自定义管理员设置的状态, 执行所需的操作。 换句话说, 用户不应担心在 "垃圾邮件" 文件夹中看到大量垃圾邮件。 如果管理员更喜欢移动所有垃圾邮件, 则应配置隔离。 有关更多详细信息, 请参阅[在 Office 365 文章中隔离电子](../quarantine-email-messages.md)邮件。

## <a name="important-terms"></a>重要术语

**入站:** 将进入 Office 365 的邮件。

**出站:** 来自 Office 365 的邮件。

**Internal:** 来自组织内部的某个人的邮件到组织内的某个人。 这包括在混合方案中的客户和一个邮箱可以在本地, 另一个邮箱位于云中。

**假负 (FN):** 垃圾邮件和其他不正确发送到收件箱的垃圾邮件。

**误报 (FP):** 错误地被标记为垃圾邮件并放入垃圾电子邮件文件夹或隔离的合法邮件。

**垃圾邮件, 也称为主动电子邮件:** 这是商业广告、连锁信函、政治邮件等的形式。这是一封电子邮件, 用户不会在试图提出产品或试图提交欺诈行为的垃圾邮件发件人注册和发件人。

**网络钓鱼:**"网络钓鱼" 是一种特殊类型的垃圾邮件, 旨在欺骗您出于提交身份盗窃或欺诈行为的目的而提供个人信息。 这种类型的邮件通常包含恶意链接或附件, 但并不总是。

**哄骗:** 哄骗是指当垃圾邮件制造者伪造发件人邮件头, 以便邮件看起来来自于实际来源以外的其他人或其他地方。 这可以是垃圾邮件, 但最常用于网络钓鱼用户。

**模拟:** 这种类型的垃圾邮件也是伪造发件人地址的一种方法, 但通过修改名称或域的一部分使其看起来像真实的来源一样实现。 例如, Bi11@micr0s0ft.com, 即 Bill 中的 "l" 实际上是数字十一, 而 Microsoft 中的 "o" 替换为数字零。

**批量:** 通常情况下, 用户会请求批量邮件, 尽管有时会在公司向其他公司销售信息时间接使用。 用户有意注册批量邮件 (如 newletters), 但稍后又忘记了垃圾邮件, 这很常见。 当批量邮件发送超过用户的注册和投诉级别变得过高时, 批量邮件将成为垃圾邮件。
