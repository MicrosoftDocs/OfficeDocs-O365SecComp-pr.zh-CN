---
title: 当邮件为红色标记时, 如何组合策略和保护
description: 当电子邮件标记为恶意软件、垃圾邮件、高可信度垃圾邮件、网络钓鱼, 以及 EOP 和/或 ATP 时, 将应用哪些策略以及要采取的操作。
keywords: security、恶意软件、Microsoft 365、M365、security center、ATP、Windows Defender ATP、Office 365 atp、Azure atp
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 03/26/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 7aa0f89eed379273cb069cd65c083749a9552e91
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30926461"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>在您的电子邮件上运行多个保护方法和检测扫描时应用什么策略

您的传入邮件可能会被多个保护形式 (例如 *, EOP 和*ATP) 标记, 以及多个检测扫描 (例如垃圾邮件*和*网络钓鱼)。 这是因为 atp 客户有 atp 反网络钓鱼策略, 并为 EOP 客户提供了 EOP 反网络钓鱼策略。 这也意味着邮件可能会针对恶意软件、网络钓鱼和用户模拟浏览多个检测扫描。 对于所有此活动, 可能会对应用的策略产生一些困惑。

通常情况下, 应用于邮件的策略在**CAT (Category)** 属性中的**X-Forefront-反垃圾邮件报告**标头中进行标识。 如果您有多个反网络钓鱼策略, 则会应用最高优先级的策略。

以下策略适用于_所有组织_。

|优先级 |策略  |类别  |托管 |
|---------|---------|---------|---------|
|1     | 恶意软件      | MALW      | 恶意软件策略   |
|双面     | 网络钓鱼     | PHSH     | 配置垃圾邮件筛选器策略     |
|第三章     | 高可信度垃圾邮件      | HSPM        | 配置垃圾邮件筛选器策略        |
|4     | 网络钓鱼        | SPOOF        | 反网络钓鱼策略、欺骗性智能        |
|5     | 垃圾邮件         | SPM         | 配置垃圾邮件筛选器策略         |
|型     | 批量邮件         | BULK        | 配置垃圾邮件筛选器策略         |

此外, 这些策略适用于_具有 ATP 的组织_。

|优先级 |策略  |类别  |托管 |
|---------|---------|---------|---------|
|步     | 域模拟         | DIMP         | 设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略        |
|utf-8     | 用户模拟        | UIMP         | 设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略         |

例如, 如果您有两个策略:

|策略  |优先级  |用户/域模拟  |反欺骗  |
|---------|---------|---------|---------|
|A     | 1        | 开        |关         |
|B     | 双面        | 关        | 开        |

如果一封邮件同时被标识为_用户模拟_和_欺骗_(请参阅上表中的反欺骗), 并且范围为策略 a 的同一组用户的范围为策略 B, 则该邮件将被标记并被视为_欺骗_邮件, 但不由于反欺骗已关闭, 并且**欺骗以更高优先级 (4) 而不是用户模拟 (8) 运行**, 因此应用了操作。

若要应用其他类型的网络钓鱼策略, 您将需要调整应用不同策略的用户的设置。



