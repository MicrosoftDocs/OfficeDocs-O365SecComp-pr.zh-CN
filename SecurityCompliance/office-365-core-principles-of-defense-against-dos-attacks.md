---
title: Office 365 的防御拒绝服务攻击的核心原则
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 如何 Microsoft 利用吸收、 检测和缓解其防御拒绝服务 (DoS) 攻击中的核心原则。
ms.openlocfilehash: e313d5514e9bc493db78bebffca24a0fae4cbca7
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741095"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a><span data-ttu-id="a1c97-103">防御拒绝服务攻击的核心原则</span><span class="sxs-lookup"><span data-stu-id="a1c97-103">Core Principles of Defense Against Denial-of-Service Attacks</span></span>

<span data-ttu-id="a1c97-p101">三个核心原则时防御网络基于 DoS 攻击吸收、 检测和缓解。检测之前, 发生吸收和检测缓解之前发生。吸收是防御 DoS 攻击的最佳。如果无法检测到攻击，它不能减轻。但如果不能吸收甚至最小 DoS 攻击，然后服务不会排除太长，无法检测到攻击。</span><span class="sxs-lookup"><span data-stu-id="a1c97-p101">The three core principles when defending against network-based DoS attacks are Absorption, Detection, and Mitigation. Absorption happens before detection, and detection happens before mitigation. Absorption is the best defense against a DoS attacks. If the attack can't be detected, it can't be mitigated. But if even the smallest DoS attack can't be absorbed, then services aren't going to survive long enough for the attack to be detected.</span></span>

<span data-ttu-id="a1c97-p102">当然，它通常是不经济可行对于大多数组织而言，这需要技术和技术技能可观投资购买必要承受 DoS 攻击的多余容量。这重点介绍使用 Microsoft 云服务; 的安全优势之一我们的服务巨大规模使我们能够向云客户提供强大的网络保护，经济高效的方式。但是，即使在我们的规模，但是仍必须有吸收、 检测和缓解之间的平衡。若要查找的平衡，我们研究估计我们需要多少承受的攻击增长速率。</span><span class="sxs-lookup"><span data-stu-id="a1c97-p102">Of course, it is generally not economically feasible for most organizations to purchase the excess capacity necessary to absorb DoS attacks, as this requires a considerable investment in technology and technical skills. This highlights one of the security benefits of using Microsoft cloud services; the sheer scale of our services enables us to provide strong network protection to our cloud customers in a cost-effective manner. But even at our scale, though, there must still be a balance between absorption, detection, and mitigation. To find that balance, we study an attack's growth rate to estimate how much we need to absorb.</span></span>

<span data-ttu-id="a1c97-p103">检测是 cat-and-mouse 游戏。您必须不断地查看的新方式人员攻击您或尝试抵御您的系统。检测-> 缓解-> 检测-> 减轻等，是无限期仍的永久持久状态。</span><span class="sxs-lookup"><span data-stu-id="a1c97-p103">Detection is a cat-and-mouse game. You must constantly look for the new ways people are attacking you or trying to defeat your systems. Detect -> Mitigate -> Detect -> Mitigate, etc., is a perpetual, persistent state that will continue indefinitely.</span></span>

## <a name="defending-against-dos-attacks"></a><span data-ttu-id="a1c97-116">防御 DoS 攻击</span><span class="sxs-lookup"><span data-stu-id="a1c97-116">Defending Against DoS Attacks</span></span>

<span data-ttu-id="a1c97-p104">若要成功防御有 DoS 攻击，早期检测是必不可少的。通过大量系统之前检测攻击，人实在可以执行响应计划。</span><span class="sxs-lookup"><span data-stu-id="a1c97-p104">To successfully defend against a DoS attack, early detection is essential. By detecting an attack before the system is overwhelmed, defenders can execute a response plan.</span></span>

<span data-ttu-id="a1c97-119">下面的公式将帮助近似的时间有 DoS 攻击的影响：</span><span class="sxs-lookup"><span data-stu-id="a1c97-119">The following formula will help approximate the time to impact of a DoS attack:</span></span>

   <span data-ttu-id="a1c97-120">**最大容量 （以字节为单位数/秒） / 增长速率 （以字节为单位数/秒） = 影响时间 （以字节为单位数/秒）**</span><span class="sxs-lookup"><span data-stu-id="a1c97-120">**Maximum Capacity (in bytes/sec) / Growth Rate (in bytes/sec) = Time to Impact (in bytes/sec)**</span></span>

<span data-ttu-id="a1c97-p105">如果时间影响之后发生的时间检测，则很可能是 DoS 攻击将会成功。如果时间检测时间到影响之前，发生此事件，然后攻击的服务都应保持联机和访问，如果使用缓解策略。因此，下面是可防御 DoS 攻击的只有两个事项：</span><span class="sxs-lookup"><span data-stu-id="a1c97-p105">If the time-to-detection occurs after time-to-impact, then it is likely the DoS attack will be successful. If the time-to-detection occurs before time-to-impact, then the services being attacked should remain online and accessible, if mitigation strategies are used. Thus, there are only two things that can be done to defend against DoS attacks:</span></span>
- <span data-ttu-id="a1c97-124">增加容量来引发的最大容量 （它反过来提供更多时间来检测攻击）; 上限或</span><span class="sxs-lookup"><span data-stu-id="a1c97-124">Increase capacity to raise the ceiling of maximum capacity (which in turn provides more time to detect an attack); or</span></span>
- <span data-ttu-id="a1c97-125">减少来检测的时间。</span><span class="sxs-lookup"><span data-stu-id="a1c97-125">Decrease the time to detect.</span></span>

<span data-ttu-id="a1c97-p106">增加容量有直接会计影响。Microsoft 建议客户开发至少基本吸收容量，以确保他们可以排除是否有 DoS 攻击的一些级别。实际吸收容量有所不同客户，因为每个客户都有自己阈值暴露、 风险和财务支出。最终，原因经济投资的研究和方式降低时间为检测的时间通常是最经济高效的防御措施。</span><span class="sxs-lookup"><span data-stu-id="a1c97-p106">Increasing capacity has a direct fiscal impact. Microsoft recommends that customers develop at least basic absorption capacity, to ensure that they can survive some level of DoS attack. The actual absorption capacity will vary from customer to customer, as each customer has their own thresholds for exposure, risk, and financial outlay. Ultimately, for economic reasons, investments of research and time in ways to decrease time-to-detection are usually the most cost-effective defense.</span></span>
