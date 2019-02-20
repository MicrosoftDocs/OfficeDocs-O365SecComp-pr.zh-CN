---
title: 防御 Office 365 中的拒绝服务攻击
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 拒绝服务 (DoS) 攻击概述。
ms.openlocfilehash: cd099bcb225cfa5dd1f44f14d4b7813bef8f7442
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091014"
---
# <a name="defending-against-denial-of-service-attacks-in-office-365"></a>防御 Office 365 中的拒绝服务攻击

## <a name="introduction"></a>简介
microsoft 为超过200个云服务 (包括 microsoft Azure、microsoft Bing、microsoft Office 365、microsoft Dynamics 365、microsoft OneDrive、Skype 和 Xbox Live) 提供托管在我们的全球云中的可信赖基础结构超过100个数据中心的基础结构。

作为具有大量 internet 状态以及提供云服务的显著 internet 属性的全球组织, Microsoft 是黑客和其他恶意用户的一个大型、常见的目标。网络--客户端与 Microsoft 云之间的通信层--是恶意攻击的最大目标之一。事实上, 在很多年中, Microsoft 一直在某种形式的基于网络的 cyberattack 持续和永久地进行。大多数情况下, 至少有一个 Microsoft 的 Internet 属性遇到某种形式的攻击。如果没有可抵御这些攻击的可靠且持久的缓解系统, Microsoft 的云服务将处于脱机状态, 并且对客户不可用。

Microsoft 使用纵深防御安全原则来保护其云服务和网络。 

## <a name="definition-and-symptoms-of-denial-of-service-attacks"></a>拒绝服务攻击的定义和症状
攻击网络服务的一种方法是创建针对服务主机的多个请求, 以使网络和服务器在网络和服务器上严重, 以拒绝向合法用户发送服务。这称为拒绝服务 (DoS) 攻击。当多个参与者、终结点和/或向量执行攻击时, 它称为分布式拒绝服务 (DDoS) 攻击。尽管 motives 和目标各不相同, 但 DoS 和 DDoS 攻击通常由人员或人员的努力阻止 Internet 站点或服务正常运行, 或者暂时或无限期地运行。

[美国计算机紧急就绪团队](https://www.us-cert.gov/)(美国-CERT) 定义 DoS 攻击的症状, 以包括:
- 网络性能异常慢 (打开文件或访问 Internet 站点时)
- 网站不可用
- 无法访问网站
- 收到的垃圾邮件大大增加
- 断开无线连接或有线 Internet 连接
- 长期失去对 Web 或任何 Internet 服务的访问权限

## <a name="related-topics"></a>相关主题
- [防御拒绝服务攻击的核心原则](office-365-core-principles-of-defense-against-dos-attacks.md)
- [Microsoft 的拒绝服务防御策略](office-365-microsoft-dos-defense-strategy.md)
- [防御拒绝服务攻击的 Microsoft 云服务](office-365-defending-cloud-services-against-dos-attacks.md)
