---
title: Office 365 中的数据复原能力
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
description: 了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 7d43c766615ff1520c6529427116c42795da8565
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525680"
---
# <a name="data-resiliency-in-office-365"></a><span data-ttu-id="2a6df-103">Office 365 中的数据复原能力</span><span class="sxs-lookup"><span data-stu-id="2a6df-103">Data Resiliency in Office 365</span></span>

## <a name="introduction"></a><span data-ttu-id="2a6df-104">简介</span><span class="sxs-lookup"><span data-stu-id="2a6df-104">Introduction</span></span>
<span data-ttu-id="2a6df-p101">在给定云计算的复杂性，Microsoft 后注意，不的大小写但如果操作将会出现错误，而不显示时。我们设计云服务以最大限度提高可靠性和时万一减少对客户的负面影响。我们已移动之外的依赖于复杂的物理基础结构，传统的策略，我们已经直接将云服务构建冗余。我们使用复杂性较低的物理基础结构和更智能的软件数据恢复能力可用于构建到我们的服务，向客户提供高可用性的组合。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p101">Given the complex nature of cloud computing, Microsoft is mindful that it's not a case of if things will go wrong, but rather when. We design our cloud services to maximize reliability and minimize the negative effects on customers when things do go wrong. We have moved beyond the traditional strategy of relying on complex physical infrastructure, and we have built redundancy directly into our cloud services. We use a combination of less complex physical infrastructure and more intelligent software that builds data resiliency into our services and delivers high availability to our customers.</span></span> 

## <a name="resiliency-and-recoverability-are-built-in"></a><span data-ttu-id="2a6df-109">恢复能力和可恢复性是内置</span><span class="sxs-lookup"><span data-stu-id="2a6df-109">Resiliency and Recoverability Are Built-in</span></span> 
<span data-ttu-id="2a6df-p102">在恢复能力和恢复构建开头的基本基础结构和流程将会失败有时假设： 硬件 （基础结构） 将失败，人们将会出错，并且软件将了 bug。时它是说软件开发人员未考虑这些事项做之前云不正确的在典型的 IT 实现如何处理这些问题已之前云非常不同：</span><span class="sxs-lookup"><span data-stu-id="2a6df-p102">Building in resiliency and recovery starts with the assumption that the underlying infrastructure and processes will fail at some point: hardware (infrastructure) will fail, humans will make mistakes, and software will have bugs. While it would be incorrect to say that software developers were not thinking about these things before the cloud, how these issues were handled in a typical IT implementation was very different before the cloud:</span></span> 
- <span data-ttu-id="2a6df-p103">首先，硬件和基础结构保护非常显著。这意味着具有所需的 99.99%可靠性重要的作用与网络冗余的数据中心和服务器已实施基于硬件的群集，双电源、 双网络接口和类似内容。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p103">First, hardware and infrastructure protections were significant. This meant having datacenters with 99.99% reliability required significant power and network redundancy, and servers were implemented with hardware-based clustering, dual power supplies, dual network interfaces, and the like.</span></span> 
- <span data-ttu-id="2a6df-p104">其次，过程是也极为重要。运营团队维护严格过程，更改已采用 windows，且通常有大量项目管理开销。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p104">Second, process was paramount. Operations teams maintained rigorous procedures, change windows were employed, and there was often significant project management overhead.</span></span> 
- <span data-ttu-id="2a6df-p105">第三，部署发生 glacial 步调。部署代码，而无需拥有源意味着等待修补程序版本，并主要版本释放所涉及的硬件替换和重要资本支出。此外，若要更正问题的唯一方式已回滚。因此，大多数 IT 组织将部署仅主要版本，以避免保持最新状态的工作。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p105">Third, deployment took place at a glacial pace. Deploying code without owning the source meant waiting for patch releases, and major version releases involved hardware replacement and significant capital outlay. Moreover, the only way to correct a problem was to rollback. Thus, most IT organizations would deploy only major releases to avoid the work to keep up-to-date.</span></span> 
- <span data-ttu-id="2a6df-120">最后，部署系统的小数以及其 interconnectedness 级别而以往更小比现在。</span><span class="sxs-lookup"><span data-stu-id="2a6df-120">Finally, the scale of deployed systems, as well as the level of their interconnectedness was historically much smaller than it is now.</span></span> 

<span data-ttu-id="2a6df-121">如今，客户而不会损害质量，希望从 Microsoft 的连续创新，这是为什么使用恢复能力和可恢复性记住生成 Microsoft 的服务和软件的原因之一。</span><span class="sxs-lookup"><span data-stu-id="2a6df-121">Today, customers expect continuous innovation from Microsoft without compromising quality, and this is one of the reasons why Microsoft's services and software are built with resiliency and recoverability in mind.</span></span> 

## <a name="office-365-data-resiliency-principles"></a><span data-ttu-id="2a6df-122">Office 365 数据恢复能力原则</span><span class="sxs-lookup"><span data-stu-id="2a6df-122">Office 365 Data Resiliency Principles</span></span> 
<span data-ttu-id="2a6df-p106">恢复能力是指经受某些类型的故障，并且尚未留功能齐全从客户的角度来看基于云的服务的能力。数据恢复能力意味着，无论在 Office 365 中出现哪些问题，关键的客户数据保持不变和不受影响。为此，Office 365 服务都已设计围绕五个特定的恢复能力原则：</span><span class="sxs-lookup"><span data-stu-id="2a6df-p106">Resiliency refers to the ability of a cloud-based service to withstand certain types of failures and yet remain fully-functional from the customers' perspective. Data resiliency means that no matter what failures occur within Office 365, critical customer data remains intact and unaffected. To that end, Office 365 services have been designed around five specific resiliency principles:</span></span> 
- <span data-ttu-id="2a6df-p107">没有关键及非关键数据。在极少数故障情形中，可以删除非关键数据 （例如，是否已阅读邮件）。应在极高强度成本保护关键数据 （例如，如电子邮件的客户数据）。作为一个设计目标，已发送的邮件总是很重要，和诸如邮件是否已读取非关键。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p107">There is critical and non-critical data. Non-critical data (for example, whether a message was read) can be dropped in rare failure scenarios. Critical data (for example, customer data such as email messages) should be protected at extreme cost. As a design goal, delivered mail messages are always critical, and things like whether a message has been read is non-critical.</span></span> 
- <span data-ttu-id="2a6df-130">客户数据副本必须分隔到不同的容错区域或者随着在许多故障域尽可能 （例如，数据中心，可访问 （过程、 服务器或运算符） 的单一凭据） 来提供故障隔离。</span><span class="sxs-lookup"><span data-stu-id="2a6df-130">Copies of customer data must be separated into different fault zones or as many fault domains as possible (e.g., datacenters, accessible by single credentials (process, server, or operator)) to provide failure isolation.</span></span> 
- <span data-ttu-id="2a6df-131">必须为失败原子性、 一致性、 隔离和持久性 （酸） 的任何部分监视关键的客户数据。</span><span class="sxs-lookup"><span data-stu-id="2a6df-131">Critical customer data must be monitored for failing any part of Atomicity, Consistency, Isolation, Durability (ACID).</span></span> 
- <span data-ttu-id="2a6df-p108">必须从损坏保护客户数据。它必须是主动扫描或受监控，可修复的并且可恢复。</span><span class="sxs-lookup"><span data-stu-id="2a6df-p108">Customer data must be protected from corruption. It must be actively scanned or monitored, repairable, and recoverable.</span></span> 
- <span data-ttu-id="2a6df-134">大多数数据丢失结果客户操作，因此允许客户恢复自己使用 GUI 使他们能够还原意外删除的项。</span><span class="sxs-lookup"><span data-stu-id="2a6df-134">Most data loss results from customer actions, so allow customers to recover on their own using a GUI that enables them to restore accidentally deleted items.</span></span> 
 
<span data-ttu-id="2a6df-135">通过这些原则，加上可靠的测试和验证，我们云服务的构建 Office 365 是能够满足和超过的客户的需求，同时确保连续创新和改进的平台。</span><span class="sxs-lookup"><span data-stu-id="2a6df-135">Through the building of our cloud services to these principles, coupled with robust testing and validation, Office 365 is able to meet and exceed the requirements of customers while ensuring a platform for continuous innovation and improvement.</span></span> 

## <a name="related-links"></a><span data-ttu-id="2a6df-136">相关的链接</span><span class="sxs-lookup"><span data-stu-id="2a6df-136">Related Links</span></span>

- [<span data-ttu-id="2a6df-137">处理数据损坏</span><span class="sxs-lookup"><span data-stu-id="2a6df-137">Dealing with Data Corruption</span></span>](office-365-dealing-with-data-corruption.md)
- [<span data-ttu-id="2a6df-138">恶意软件和勒索软件防护</span><span class="sxs-lookup"><span data-stu-id="2a6df-138">Malware and Ransomware Protection</span></span>](office-365-malware-and-ransomware-protection.md)
- [<span data-ttu-id="2a6df-139">监视和自愈</span><span class="sxs-lookup"><span data-stu-id="2a6df-139">Monitoring and Self-Healing</span></span>](office-365-monitoring-and-self-healing.md)
- [<span data-ttu-id="2a6df-140">Exchange 数据恢复能力</span><span class="sxs-lookup"><span data-stu-id="2a6df-140">Exchange Data Resiliency</span></span>](office-365-exchange-data-resiliency.md)
- [<span data-ttu-id="2a6df-141">SharePoint 数据恢复能力</span><span class="sxs-lookup"><span data-stu-id="2a6df-141">SharePoint Data Resiliency</span></span>](office-365-sharepoint-data-resiliency.md)