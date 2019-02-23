---
title: Office 365 防御拒绝服务攻击的核心原则
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft 如何在防御拒绝服务 (DoS) 攻击的同时, 利用其核心原则、检测和缓解措施。
ms.openlocfilehash: dfe179924f7414b0120697023f3daf7e6b6661b6
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216002"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="a606f-103">防御拒绝服务攻击的核心原则</span><span class="sxs-lookup"><span data-stu-id="a606f-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="a606f-p101">防御基于网络的 DoS 攻击时的三个核心原则是吸收、检测和缓解。在检测之前全部发生, 并在缓解之前发生检测。吸收对 DoS 攻击的最佳防御能力。如果无法检测到攻击, 则无法缓解攻击。但是, 如果甚至无法吸收最小的 DoS 攻击, 则服务的运行时间将不足以检测到攻击。</span><span class="sxs-lookup"><span data-stu-id="a606f-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="a606f-p102">当然, 大多数组织通常不能经济地购买吸收 DoS 攻击所需的额外容量, 因为这需要在技术和技术方面获得相当大的投资。这将重点介绍使用 Microsoft 云服务的安全优势之一;我们的服务的巨大规模使我们能够以经济高效的方式为云客户提供强大的网络保护。不过, 即使是我们的规模, 在吸收、检测和缓解之间仍必须取得平衡。为了找出这一平衡, 我们研究了攻击的增长速度, 以估计我们需要吸收的程度。</span><span class="sxs-lookup"><span data-stu-id="a606f-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="a606f-p103">检测是一种 cat 和鼠标游戏。您必须不断寻找用户攻击您或试图击败系统的新方法。> 缓解-> 检测-> 缓解等是永久的持久状态, 它将无限期地继续进行。</span><span class="sxs-lookup"><span data-stu-id="a606f-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="a606f-116">防御 DoS 攻击</span><span class="sxs-lookup"><span data-stu-id="a606f-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="a606f-p104">若要成功抵御 DoS 攻击, 早期检测是必不可少的。通过在系统被淹没之前检测攻击, defenders 可以执行响应计划。</span><span class="sxs-lookup"><span data-stu-id="a606f-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="a606f-119">下面的公式将帮助估计 DoS 攻击的影响时间:</span><span class="sxs-lookup"><span data-stu-id="a606f-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="a606f-120">**最大容量 (以字节/秒为单位)/增长率 (以字节/秒为单位) = 影响的时间 (以字节/秒为单位)**</span><span class="sxs-lookup"><span data-stu-id="a606f-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="a606f-p105">如果检测时间在影响时间之后发生, 则 DoS 攻击很可能会成功。如果检测时间在影响时间之前发生, 则受攻击的服务应保持联机并可访问, 前提是使用了缓解策略。因此, 防御 DoS 攻击只需要执行以下两项操作:</span><span class="sxs-lookup"><span data-stu-id="a606f-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="a606f-124">增加容量以提升最大容量的上限 (进而提供更多的时间来检测攻击);和</span><span class="sxs-lookup"><span data-stu-id="a606f-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="a606f-125">缩短要检测的时间。</span><span class="sxs-lookup"><span data-stu-id="a606f-125">Decrease the time to detect.</span></span>

<span data-ttu-id="a606f-p106">增加的容量有直接的财政影响。Microsoft 建议客户至少开发基本的最大容量, 以确保能够经受一定程度的 DoS 攻击。实际的最大容量将因客户而异, 因为每个客户都有自己的针对暴露、风险和财务 outlay 的阈值。最终, 出于经济方面的考虑, 在减少检测时间的方法方面的投资通常是最经济划算的防御措施。</span><span class="sxs-lookup"><span data-stu-id="a606f-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
