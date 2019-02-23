---
title: Office 365 中的数据复原能力
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
description: 了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 1e85f431edeec0a4548b1d37b65a4b1a6cbef8eb
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215632"
---
# <a name="data-resiliency-in-office-365"></a><span data-ttu-id="8ac1a-103">Office 365 中的数据复原能力</span><span class="sxs-lookup"><span data-stu-id="8ac1a-103">Data Resiliency in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="8ac1a-104">简介</span><span class="sxs-lookup"><span data-stu-id="8ac1a-104">Introduction</span></span>
<span data-ttu-id="8ac1a-p101">考虑到云计算的复杂特性, Microsoft 注意, 如果出现问题, 则不是这样, 而是不会出现什么情况。我们设计云服务, 以最大限度地提高可靠性并最大限度地减少客户发生错误时对客户造成的负面影响。我们已经迁移到依赖复杂物理基础结构的传统策略之外, 我们已直接在云服务中构建冗余。我们使用的是不太复杂的物理基础结构和更智能软件的组合, 可将数据弹性构建到服务中, 并为我们的客户提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p101">Given the complex nature of cloud computing, Microsoft is mindful that it's not a case of if things will go wrong, but rather when. We design our cloud services to maximize reliability and minimize the negative effects on customers when things do go wrong. We have moved beyond the traditional strategy of relying on complex physical infrastructure, and we have built redundancy directly into our cloud services. We use a combination of less complex physical infrastructure and more intelligent software that builds data resiliency into our services and delivers high availability to our customers.</span></span> 

## <a name="resiliency-and-recoverability-are-built-in"></a><span data-ttu-id="8ac1a-109">恢复能力和可恢复性内置</span><span class="sxs-lookup"><span data-stu-id="8ac1a-109">Resiliency and Recoverability Are Built-in</span></span> 
<span data-ttu-id="8ac1a-p102">在恢复能力和恢复中, 从以下假设假定基础基础结构和过程将在某种程度上失败: 硬件 (基础结构) 将失败, 人会犯错误, 并且软件将产生错误。虽然软件开发人员不会在云之前考虑这些问题, 但在典型的 it 实施中如何处理这些问题在云之前是非常不同的, 这是不可能的:</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p102">Building in resiliency and recovery starts with the assumption that the underlying infrastructure and processes will fail at some point: hardware (infrastructure) will fail, humans will make mistakes, and software will have bugs. While it would be incorrect to say that software developers were not thinking about these things before the cloud, how these issues were handled in a typical IT implementation was very different before the cloud:</span></span> 
- <span data-ttu-id="8ac1a-p103">首先, 硬件和基础结构保护是非常重要的。这意味着具有 99.99% 可靠性的数据中心需要大量电源和网络冗余, 并且服务器是使用基于硬件的群集、双电源、双网络接口等实现的。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p103">First, hardware and infrastructure protections were significant. This meant having datacenters with 99.99% reliability required significant power and network redundancy, and servers were implemented with hardware-based clustering, dual power supplies, dual network interfaces, and the like.</span></span> 
- <span data-ttu-id="8ac1a-p104">其次, 流程非常重要。操作团队维护了严格的过程, 已雇用更改窗口, 并且经常发生重大的项目管理开销。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p104">Second, process was paramount. Operations teams maintained rigorous procedures, change windows were employed, and there was often significant project management overhead.</span></span> 
- <span data-ttu-id="8ac1a-p105">第三, 部署采用 glacial 节奏进行。在不拥有资源的情况下部署代码意味着要等待修补程序版本, 主版本的版本涉及硬件更换和显著的资本 outlay。此外, 纠正问题的唯一方法是回滚。因此, 大多数 IT 组织仅部署主要版本, 以避免工作保持最新。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p105">Third, deployment took place at a glacial pace. Deploying code without owning the source meant waiting for patch releases, and major version releases involved hardware replacement and significant capital outlay. Moreover, the only way to correct a problem was to rollback. Thus, most IT organizations would deploy only major releases to avoid the work to keep up-to-date.</span></span> 
- <span data-ttu-id="8ac1a-120">最后, 部署的系统的规模以及其 interconnectedness 的级别以前比现在更小。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-120">Finally, the scale of deployed systems, as well as the level of their interconnectedness was historically much smaller than it is now.</span></span> 

<span data-ttu-id="8ac1a-121">目前, 客户预期来自 microsoft 的连续创新不会降低质量, 这也是 microsoft 服务和软件以恢复和恢复为依据而构建的原因之一。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-121">Today, customers expect continuous innovation from Microsoft without compromising quality, and this is one of the reasons why Microsoft's services and software are built with resiliency and recoverability in mind.</span></span> 

## <a name="office-365-data-resiliency-principles"></a><span data-ttu-id="8ac1a-122">Office 365 数据恢复原则</span><span class="sxs-lookup"><span data-stu-id="8ac1a-122">Office 365 Data Resiliency Principles</span></span> 
<span data-ttu-id="8ac1a-p106">弹性是指基于云的服务经受某些类型的故障的能力, 但从客户的角度来看功能完全正常。数据恢复意味着无论 Office 365 中发生什么故障, 关键客户数据保持不变且不受影响。为此, Office 365 服务在设计方面围绕了五种特定的恢复原则:</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p106">Resiliency refers to the ability of a cloud-based service to withstand certain types of failures and yet remain fully-functional from the customers' perspective. Data resiliency means that no matter what failures occur within Office 365, critical customer data remains intact and unaffected. To that end, Office 365 services have been designed around five specific resiliency principles:</span></span> 
- <span data-ttu-id="8ac1a-p107">存在关键和非关键数据。非关键数据 (例如, 是否已读取邮件) 可以在罕见故障方案中删除。关键数据 (例如, 客户数据 (如电子邮件) 应以极高的成本进行保护。作为设计目标, 已传递的邮件始终是关键的, 例如邮件是否已被阅读是不重要的。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p107">There is critical and non-critical data. Non-critical data (for example, whether a message was read) can be dropped in rare failure scenarios. Critical data (for example, customer data such as email messages) should be protected at extreme cost. As a design goal, delivered mail messages are always critical, and things like whether a message has been read is non-critical.</span></span> 
- <span data-ttu-id="8ac1a-130">客户数据的副本必须分成不同的故障区域或尽可能多的故障域 (例如, 数据中心可通过单个凭据 (process、server 或 operator) 来提供故障隔离)。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-130">Copies of customer data must be separated into different fault zones or as many fault domains as possible (e.g., datacenters, accessible by single credentials (process, server, or operator)) to provide failure isolation.</span></span> 
- <span data-ttu-id="8ac1a-131">必须监视关键客户数据, 以确保原子性、一致性、隔离、持续性 (ACID) 的任何部分失败。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-131">Critical customer data must be monitored for failing any part of Atomicity, Consistency, Isolation, Durability (ACID).</span></span> 
- <span data-ttu-id="8ac1a-p108">必须保护客户数据不受损坏。必须主动扫描或监视、修复和恢复。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-p108">Customer data must be protected from corruption. It must be actively scanned or monitored, repairable, and recoverable.</span></span> 
- <span data-ttu-id="8ac1a-134">大多数数据丢失结果来自客户操作, 因此允许客户使用 GUI 自行恢复, 使他们能够还原意外删除的项目。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-134">Most data loss results from customer actions, so allow customers to recover on their own using a GUI that enables them to restore accidentally deleted items.</span></span> 
 
<span data-ttu-id="8ac1a-135">通过将我们的云服务与这些原则相结合, Office 365 能够满足和超过客户的需求, 同时确保平台能够进行持续的创新和改进。</span><span class="sxs-lookup"><span data-stu-id="8ac1a-135">Through the building of our cloud services to these principles, coupled with robust testing and validation, Office 365 is able to meet and exceed the requirements of customers while ensuring a platform for continuous innovation and improvement.</span></span> 

## <a name="related-links"></a><span data-ttu-id="8ac1a-136">相关链接</span><span class="sxs-lookup"><span data-stu-id="8ac1a-136">Related Links</span></span>

- [<span data-ttu-id="8ac1a-137">处理数据损坏</span><span class="sxs-lookup"><span data-stu-id="8ac1a-137">Dealing with Data Corruption</span></span>](office-365-dealing-with-data-corruption.md)
- [<span data-ttu-id="8ac1a-138">恶意软件和勒索软件防护</span><span class="sxs-lookup"><span data-stu-id="8ac1a-138">Malware and Ransomware Protection</span></span>](office-365-malware-and-ransomware-protection.md)
- [<span data-ttu-id="8ac1a-139">监视和自愈</span><span class="sxs-lookup"><span data-stu-id="8ac1a-139">Monitoring and Self-Healing</span></span>](office-365-monitoring-and-self-healing.md)
- [<span data-ttu-id="8ac1a-140">Exchange 数据恢复能力</span><span class="sxs-lookup"><span data-stu-id="8ac1a-140">Exchange Data Resiliency</span></span>](office-365-exchange-data-resiliency.md)
- [<span data-ttu-id="8ac1a-141">SharePoint 数据恢复能力</span><span class="sxs-lookup"><span data-stu-id="8ac1a-141">SharePoint Data Resiliency</span></span>](office-365-sharepoint-data-resiliency.md)