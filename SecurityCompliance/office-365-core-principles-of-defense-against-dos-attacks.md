---
title: Office 365 的防御拒绝服务攻击的核心原则
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 如何 Microsoft 利用吸收、 检测和缓解其防御拒绝服务 (DoS) 攻击中的核心原则。
ms.openlocfilehash: 8355a7897c788241092363a23e198423e81c587a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524799"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防御拒绝服务攻击的核心原则
三个核心原则时防御网络基于 DoS 攻击吸收、 检测和缓解。检测之前, 发生吸收和检测缓解之前发生。吸收是防御 DoS 攻击的最佳。如果无法检测到攻击，它不能减轻。但如果不能吸收甚至最小 DoS 攻击，然后服务不会排除太长，无法检测到攻击。

当然，它通常是不经济可行对于大多数组织而言，这需要技术和技术技能可观投资购买必要承受 DoS 攻击的多余容量。这重点介绍使用 Microsoft 云服务; 的安全优势之一我们的服务巨大规模使我们能够向云客户提供强大的网络保护，经济高效的方式。但是，即使在我们的规模，但是仍必须有吸收、 检测和缓解之间的平衡。若要查找的平衡，我们研究估计我们需要多少承受的攻击增长速率。

检测是 cat-and-mouse 游戏。您必须不断地查看的新方式人员攻击您或尝试抵御您的系统。检测-> 减轻-> 检测-> 减轻等，是无限期仍的永久持久状态。

## <a name="defending-against-dos-attacks"></a>防御 DoS 攻击
若要成功防御有 DoS 攻击，早期检测是必不可少的。通过大量系统之前检测攻击，人实在可以执行响应计划。

下面的公式将帮助近似的时间有 DoS 攻击的影响：

   **最大容量 / （最大容量 X 增长速率） = 时间的影响**

如果时间影响之后发生的时间检测，则很可能是 DoS 攻击将会成功。如果时间检测时间到影响之前，发生此事件，然后攻击的服务都应保持联机和访问，如果使用缓解策略。因此，下面是可防御 DoS 攻击的只有两个事项：
- 增加容量来引发的最大容量 （它反过来提供更多时间来检测攻击）; 上限或
- 减少来检测的时间。

增加容量有直接会计影响。Microsoft 建议客户开发至少基本吸收容量，以确保他们可以排除是否有 DoS 攻击的一些级别。实际吸收容量有所不同客户，因为每个客户都有自己阈值暴露、 风险和财务支出。最终，原因经济投资的研究和方式降低时间为检测的时间通常是最经济高效的防御措施。
