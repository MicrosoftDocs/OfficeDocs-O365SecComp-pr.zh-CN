---
title: Office 365 Microsoft 的 DoS 防御策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Microsoft 用于处理拒绝服务 (DoS) 攻击的防御策略的概述。
ms.openlocfilehash: acc0c74ae9ed434d4718d7b8b3bd9429b3245d46
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262544"
---
# <a name="microsofts-denial-of-service-defense-strategy"></a>Microsoft 的拒绝服务防御策略

Microsoft 针对基于网络的拒绝服务 (DoS) 攻击的策略因规模和全球空间的不同而有所不同。 此扩展使 Microsoft 能够利用一些组织 (提供商或客户组织) 可以匹配的策略和技术。 我们的 DoS 策略的基础是利用我们的全球形象。 Microsoft 与 internet 提供商、对等提供商 (公用和私人) 以及全球各地的私营公司进行了沟通, 为我们提供了大量 Internet 状态 (在这种撰写过程中, 每18个月约两个月)。 具有此类较大的状态使 Microsoft 能够吸收跨一个非常大的外围区域的攻击。

鉴于我们独特的性质, Microsoft 使用不同于大型企业使用的检测和缓解过程。 我们的策略基于检测和缓解的分离, 以及通过我们的许多边缘的全局分布式缓解。 许多企业使用第三方解决方案来检测和缓解边缘的攻击。 随着我们的边缘容量的增长, 对单个或特定边缘的任何攻击的重要性变得非常低。 由于我们的独特配置, 我们已将检测和缓解组件分开。 我们部署了多层检测, 让我们能够检测到更接近其饱和点的攻击, 同时在边缘维护全局缓解。 此策略可确保我们可以同时处理多个并发攻击。

Microsoft 对 DoS 攻击所采用的最有效和低成本的防护之一是减少我们的攻击面。 这样做使我们能够将不需要的流量放在边缘, 而不是分析、处理和净化数据内联。

在与公用网络的接口上, Microsoft 使用专用安全设备进行防火墙、网络地址转换和 IP 筛选功能。 我们还使用全局同等成本多路径 (ECMP) 路由。 全局 ECMP 路由是一个网络框架, 可确保有多个用于访问服务的全局路径。 由于有了这些多路径, 针对服务的攻击应仅限于攻击源自的地区–其他区域应受到此攻击的影响, 因为最终用户将使用其他路径到达这些区域中的服务。 我们还开发了我们自己的内部 DoS 关联和检测系统, 它使用流数据、性能指标和其他信息。 这是在 microsoft Azure 中运行的超大型云服务, 用于分析从 Microsoft 网络和服务上的各个点收集的数据。 跨工作负载 DoS 事件响应团队确定团队中的角色和职责、升级条件以及用于参与各种团队和事件处理的协议。 这些解决方案针对 DoS 攻击提供了基于网络的保护。

最后, 基于云的工作负载根据其协议和带宽使用情况配置优化的阈值, 以唯一保护该工作负载。
