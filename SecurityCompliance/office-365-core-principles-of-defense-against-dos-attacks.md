---
title: Office 365 防御拒绝服务攻击的核心原则
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft 如何在防御拒绝服务 (DoS) 攻击的同时, 利用其核心原则、检测和缓解措施。
ms.openlocfilehash: 17dc583258cdb4781dbe2a715e1ce153ee769ed3
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091004"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>防御拒绝服务攻击的核心原则

防御基于网络的 DoS 攻击时的三个核心原则是吸收、检测和缓解。在检测之前全部发生, 并在缓解之前发生检测。吸收对 DoS 攻击的最佳防御能力。如果无法检测到攻击, 则无法缓解攻击。但是, 如果甚至无法吸收最小的 DoS 攻击, 则服务的运行时间将不足以检测到攻击。

当然, 大多数组织通常不能经济地购买吸收 DoS 攻击所需的额外容量, 因为这需要在技术和技术方面获得相当大的投资。这将重点介绍使用 Microsoft 云服务的安全优势之一;我们的服务的巨大规模使我们能够以经济高效的方式为云客户提供强大的网络保护。不过, 即使是我们的规模, 在吸收、检测和缓解之间仍必须取得平衡。为了找出这一平衡, 我们研究了攻击的增长速度, 以估计我们需要吸收的程度。

检测是一种 cat 和鼠标游戏。您必须不断寻找用户攻击您或试图击败系统的新方法。> 缓解-> 检测-> 缓解等是永久的持久状态, 它将无限期地继续进行。

## <a name="defending-against-dos-attacks"></a>防御 DoS 攻击

若要成功抵御 DoS 攻击, 早期检测是必不可少的。通过在系统被淹没之前检测攻击, defenders 可以执行响应计划。

下面的公式将帮助估计 DoS 攻击的影响时间:

   **最大容量 (以字节/秒为单位)/增长率 (以字节/秒为单位) = 影响的时间 (以字节/秒为单位)**

如果检测时间在影响时间之后发生, 则 DoS 攻击很可能会成功。如果检测时间在影响时间之前发生, 则受攻击的服务应保持联机并可访问, 前提是使用了缓解策略。因此, 防御 DoS 攻击只需要执行以下两项操作:
- 增加容量以提升最大容量的上限 (进而提供更多的时间来检测攻击);和
- 缩短要检测的时间。

增加的容量有直接的财政影响。Microsoft 建议客户至少开发基本的最大容量, 以确保能够经受一定程度的 DoS 攻击。实际的最大容量将因客户而异, 因为每个客户都有自己的针对暴露、风险和财务 outlay 的阈值。最终, 出于经济方面的考虑, 在减少检测时间的方法方面的投资通常是最经济划算的防御措施。
