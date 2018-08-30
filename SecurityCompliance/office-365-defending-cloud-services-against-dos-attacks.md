---
title: 拒绝服务攻击对 office 365 辩护云服务
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
description: 如何 Microsoft 能够针对拒绝服务 (DoS) 攻击其云服务。
ms.openlocfilehash: f11a4293a35de4d36fd38fce892a4e59919111cc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525516"
---
# <a name="defending-microsoft-cloud-services-against-denial-of-service-attacks"></a>辩护抵御拒绝服务攻击的 Microsoft 云服务

## <a name="introduction"></a>简介
由包含外围防御、 视频摄像机、 安全人员和使用生物、 智能卡和多因素身份验证的安全进入-深度防御安全保护的 Microsoft 数据中心。深度防御安全中继续每个区域的实用工具并对每个物理服务器单位。[Microsoft 云基础结构和操作组](https://www.microsoft.com/en-us/cloud-platform/global-datacenters)提供的核心基础结构和云服务的基础技术。我们数据中心遵守的物理安全和可靠性的行业标准是托管、 受监控，并由 Microsoft 操作人员管理。

为了进一步保护我们云服务，Microsoft 提供的 Microsoft Azure 连续监控和透过测试过程的一部分 DDoS 防御系统。Azure DDoS 防御系统不仅旨在经受攻击从以外，还可以从其他 Azure 租户。Azure 使用标准检测和缓解技术，如 SYN cookie、 速率限制和连接限制可防止受到 DDoS 攻击。

Microsoft 云服务将受到攻击的多个来源的威胁。以缓解以及高度可扩展和动态的 Azure 威胁检测和缓解各种 DoS 威胁防御系统已开发并实施防止 DoS 攻击的基础结构的主要目标和有助于防止针对云的服务中断服务客户。Azure DoS 缓解系统保护入站和出站区域到区域的流量。

大多数 DoS 攻击可启动针对目标网络 (L3) 和传输[打开系统互连](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model)(OSI) 模型 (第 4) 层。针对在 L3 和第 4 层攻击旨在淹没的网络接口或服务与攻击通信占用大量资源和拒绝响应合法的通信的能力。具体而言，L3 和第 4 攻击试图使饱和的网络链接、 设备或服务的容量或淹没的 Cpu 的服务器或虚拟机支持应用程序。

防范 L3 和第 4 攻击 Microsoft 具有设计、 开发和部署解决方案面向专门保护通过保护这些层受到攻击的基础结构和客户目标。保护基础结构可确保用于一个客户的攻击通信不会导致间接伤害或降低服务的其他客户的网络质量。解决方案使用来自数据中心路由器流量采样数据。此数据是由监控服务来检测攻击的网络分析。检测到攻击时，自动的防御机制启动。

## <a name="application-level-defenses"></a>应用程序级防护
Microsoft 工程团队遵循严格的标准[Microsoft 操作安全保障在线培训](https://www.microsoft.com/en-us/SDL/OperationalSecurityAssurance)设置来帮助保护客户数据。Microsoft 云服务有意旨在支持来保护和减少应用程序级 DoS 攻击对非常高负载。我们已实施何处跨多个全局的数据中心与区域隔离和限制的工作负荷的某些功能分发服务的扩展体系结构。

每个客户的国家或地区，该服务的初始安装过程中标识客户的管理员，确定该客户的数据的主存储位置。根据主/备份策略冗余数据中心之间复制的客户数据。主数据中心承载的应用程序软件以及软件上运行的主要客户数据。备份数据中心提供自动故障转移。如果主数据中心停止才能出于任何原因，请求将重定向到备份数据中心中的软件和客户数据的副本。在任何给定时间可能主或备份数据中心中处理客户数据。在多个数据中心之间分布数据减少了受影响的外围，以防攻击数据中心。此外，受影响的数据中心中的服务可以快速重定向到辅助数据中心的恢复机制和副之一反之亦然 （重定向回主数据中心后还原服务）。

单个工作负载包括管理资源利用率的内置功能。例如，限制机制在 Exchange Online 和 SharePoint Online 是防御 DoS 攻击的多层方法的一部分。Exchange Online 用户的限制基于由最终用户，占用的资源的级别是否正在 Active Directory、 Exchange Online 的信息存储，或其他位置的资源。预算被分配给每个客户端限制用户消耗的资源。[工作负载管理](http://technet.microsoft.com/en-us/library/jj150503(v=exchg.150).aspx)基于 Exchange Online 限制用户活动和系统组件。Exchange Online 的功能、 协议或已明确定义的 Exchange Online 的系统资源管理服务，Exchange Online 的工作负荷。每个 Exchange Online 的工作负荷需要系统资源 CPU、 邮箱数据库操作，如或 Active Directory 请求执行用户请求或背景工时。Exchange Online 的工作负荷的示例包括 web、 Exchange ActiveSync、 邮箱迁移和邮箱助理上的 Outlook。租户管理员可以管理 Exchange 工作负载管理限制设置为使用 Exchange 命令行管理程序的用户。有限制其已在 Exchange Online，包括 PowerShell、 Exchange Web 服务和 POP 和 IMAP、 Exchange ActiveSync、 移动设备连接、 recipients 和更多实现的各种格式。同时在本地 Exchange 部署的管理员可以配置限制策略，管理员无法为 Exchange Online 配置限制策略。

限制在 SharePoint Online 中的最常见触发器是客户端对象模型 (CSOM) 代码执行太高频率过多的操作。使用 CSOM、 可以与单个请求，其可超过使用率限制并导致限制每个用户执行多个操作。

无论活动这可能导致中限制用户超过使用率限制，任何进一步请求的用户帐户，通常较短时间内的 SharePoint Online 限制时。用户限制在生效时，该用户的所有操作将受到都控制，直到过期限制，根据以下条件：
- 对于用户直接在浏览器中执行的请求，SharePoint Online 将重定向到限制的信息页上，并请求失败。
- 对于所有其他请求，包括 CSOM 调用 SharePoint Online 返回 HTTP 状态代码 429 （"太多请求"），并请求失败。

如果继续超过使用率限制的其余部分的过程，SharePoint Online 可能完全阻止过程并返回 HTTP 状态代码的 503 （"服务不可用"）。

## <a name="vulnerability-and-penetration-testing"></a>漏洞和透过测试
Microsoft 使用很多[安全技术和实践](https://www.microsoft.com/en-us/trustcenter/security/threatmanagement)现代、 复杂威胁，包括使用的云服务，虚拟反恶意软件组件和服务的[保护其云基础结构](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/)和本地网络机 (Vm) 和其他系统;高级的威胁分析，它监视正常使用模式网络、 系统和用户，并使用机器学习标记超出普通，和常规透过测试任何行为。

除了执行透过测试，并向客户提供[Microsoft 云统一透过测试程序](https://technet.microsoft.com/en-us/mt784683)，我们还与第三方安全专业人员执行的常规漏洞评估和入侵测试针对云服务。我们进行这些第三方漏洞评估的报告可供下载的[服务信任](https://aka.ms/STP)和[服务保证](https://aka.ms/ServiceAssurance)门户。
