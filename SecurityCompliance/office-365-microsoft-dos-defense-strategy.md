---
title: Office 365 Microsoft DoS 防御战略
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
description: Overview of Microsoft 防御战略的处理拒绝服务 (DoS) 攻击。
ms.openlocfilehash: f172db5080ef73402c7e9bc61720eb0f87e844ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524807"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a><span data-ttu-id="8e7e2-103">Microsoft 的拒绝服务防御战略</span><span class="sxs-lookup"><span data-stu-id="8e7e2-103">Microsoft's Denial-of-Service Defense Strategy</span></span>

<span data-ttu-id="8e7e2-p101">由于我们的规模和全球 ア ネ 较唯一 Microsoft 战略的防御基于网络拒绝服务 (DoS) 攻击。此扩展允许 Microsoft 使用一些组织 （提供程序或客户组织） 可以匹配的技术和策略。我们 DoS 战略的基础利用我们全局状态。Microsoft Internet 提供程序，对等的提供程序 （公共和私有） 和专用雇佣世界各地的企业给予我们有大量的 Internet 业务 （其中撰写，使加倍周围每 18 个月）。具有此类大型状态后，Microsoft 可以跨非常大的外围承受攻击。</span><span class="sxs-lookup"><span data-stu-id="8e7e2-p101">Microsoft's strategy for defending against network-based denial-of-service (DoS) attacks is somewhat unique due to our scale and global footprint. This scale allows Microsoft to utilize strategies and techniques that few organizations (providers or customer organizations) can match. The cornerstone of our DoS strategy is leveraging our global presence. Microsoft engages with Internet providers, peering providers (public and private), and private corporations all over the world, giving us a significant Internet presence (which as of this writing, doubles around every 18 months). Having such a large presence enables Microsoft to absorb attacks across a very large surface area.</span></span>

<span data-ttu-id="8e7e2-p102">Microsoft 给定我们独特性质，使用检测和缓解不同于所使用的大型企业的流程。通过我们有许多边的检测和缓解，以及全局、 分布式缓解分离基于我们的策略。很多企业使用第三方解决方案检测和缓解攻击边缘内侧。我们边缘容量变得，如它变为清除个人或特定边缘任何攻击的重要性已非常低。由于我们唯一的配置，我们已分开检测和缓解组件。我们已经部署了多层检测，以使我们来检测同时保持在边缘全局缓解攻击接近为其饱和度磅。此策略可确保我们可以处理多个同时攻击。</span><span class="sxs-lookup"><span data-stu-id="8e7e2-p102">Given our unique nature, Microsoft uses detection and mitigation processes that differ from those used by large enterprises. Our strategy is based on a separation of detection and mitigation, as well as global, distributed mitigation through our many edges. Many enterprises use third-party solutions which detect and mitigate attacks at the edge. As our edge capacity grew, it became clear that the significance of any attack against individual or particular edges was very low. Because of our unique configuration, we have separated the detection and mitigation components. We have deployed multi-tiered detection that enables us to detect attacks closer to their saturation points while maintaining global mitigation at the edge. This strategy ensures we can handle multiple simultaneous attacks.</span></span>

<span data-ttu-id="8e7e2-p103">Microsoft DoS 攻击针对所使用的最有效、 低成本防护之一是以减少我们攻击面。这样，我们要在边缘，而不是分析处理和清理数据内嵌删除不必要的通信。</span><span class="sxs-lookup"><span data-stu-id="8e7e2-p103">One of the most effective and low-cost defenses employed by Microsoft against DoS attacks is to reduce our attack surface. Doing so enables us to drop unwanted traffic at the edge, as opposed to analyzing, processing and scrubbing the data inline.</span></span>

<span data-ttu-id="8e7e2-p104">在与公共网络接口，Microsoft 防火墙、 网络地址转换和 IP 筛选函数使用特殊用途安全设备。我们还使用全局等成本多路径 (ECMP) 路由。全局 ECMP 路由是确保有多个全局路径访问服务的网络框架。借助这些多个路径，对服务攻击应限制为从中攻击发起 – 最终用户将使用其他路径访问这些区域中的服务应受到此类攻击，其他区域的区域。我们还开发使用流数据、 性能指标和其他信息我们自己内部 DoS 关联和检测系统。这是在 Microsoft Azure 其分析数据收集从各种磅 Microsoft 网络上运行 hyperscale 云服务和服务。跨工作负荷 DoS 事件响应小组标识的角色和职责跨团队、 升级的条件和适当各种工作组和事件处理的协议。这些解决方案提供基于网络防范 DoS 攻击。</span><span class="sxs-lookup"><span data-stu-id="8e7e2-p104">At the interface with the public network, Microsoft uses special-purpose security devices for firewall, network address translation, and IP filtering functions. We also use global equal-cost multi-path (ECMP) routing. Global ECMP routing is a network framework that ensures there are multiple global paths to reach a service. Thanks to these multiple paths, an attack against the service should be limited to the region from which the attack originates – other regions should be unaffected by this attack, as end users would use other paths to reach the service in those regions. We have also developed our own internal DoS correlation and detection system that uses flow data, performance metrics and other information. This is a hyperscale cloud service running within Microsoft Azure which analyzes data collected from various points on Microsoft networks and services. A cross-workload DoS incident response team identifies the roles and responsibilities across teams, the criteria for escalations, and the protocols for engaging various teams and for incident handling. These solutions provide network-based protection against DoS attacks.</span></span>

<span data-ttu-id="8e7e2-126">最后，使用基于其协议优化阈值配置了基于云的工作负荷和带宽使用率需要唯一保护的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="8e7e2-126">Finally, cloud-based workloads are configured with optimized thresholds based on their protocol and bandwidth usage needs to uniquely protect that workload.</span></span>
