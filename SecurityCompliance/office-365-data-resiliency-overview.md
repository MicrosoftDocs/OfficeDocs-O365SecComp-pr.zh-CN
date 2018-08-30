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
# <a name="data-resiliency-in-office-365"></a>Office 365 中的数据复原能力

## <a name="introduction"></a>简介
在给定云计算的复杂性，Microsoft 后注意，不的大小写但如果操作将会出现错误，而不显示时。我们设计云服务以最大限度提高可靠性和时万一减少对客户的负面影响。我们已移动之外的依赖于复杂的物理基础结构，传统的策略，我们已经直接将云服务构建冗余。我们使用复杂性较低的物理基础结构和更智能的软件数据恢复能力可用于构建到我们的服务，向客户提供高可用性的组合。 

## <a name="resiliency-and-recoverability-are-built-in"></a>恢复能力和可恢复性是内置 
在恢复能力和恢复构建开头的基本基础结构和流程将会失败有时假设： 硬件 （基础结构） 将失败，人们将会出错，并且软件将了 bug。时它是说软件开发人员未考虑这些事项做之前云不正确的在典型的 IT 实现如何处理这些问题已之前云非常不同： 
- 首先，硬件和基础结构保护非常显著。这意味着具有所需的 99.99%可靠性重要的作用与网络冗余的数据中心和服务器已实施基于硬件的群集，双电源、 双网络接口和类似内容。 
- 其次，过程是也极为重要。运营团队维护严格过程，更改已采用 windows，且通常有大量项目管理开销。 
- 第三，部署发生 glacial 步调。部署代码，而无需拥有源意味着等待修补程序版本，并主要版本释放所涉及的硬件替换和重要资本支出。此外，若要更正问题的唯一方式已回滚。因此，大多数 IT 组织将部署仅主要版本，以避免保持最新状态的工作。 
- 最后，部署系统的小数以及其 interconnectedness 级别而以往更小比现在。 

如今，客户而不会损害质量，希望从 Microsoft 的连续创新，这是为什么使用恢复能力和可恢复性记住生成 Microsoft 的服务和软件的原因之一。 

## <a name="office-365-data-resiliency-principles"></a>Office 365 数据恢复能力原则 
恢复能力是指经受某些类型的故障，并且尚未留功能齐全从客户的角度来看基于云的服务的能力。数据恢复能力意味着，无论在 Office 365 中出现哪些问题，关键的客户数据保持不变和不受影响。为此，Office 365 服务都已设计围绕五个特定的恢复能力原则： 
- 没有关键及非关键数据。在极少数故障情形中，可以删除非关键数据 （例如，是否已阅读邮件）。应在极高强度成本保护关键数据 （例如，如电子邮件的客户数据）。作为一个设计目标，已发送的邮件总是很重要，和诸如邮件是否已读取非关键。 
- 客户数据副本必须分隔到不同的容错区域或者随着在许多故障域尽可能 （例如，数据中心，可访问 （过程、 服务器或运算符） 的单一凭据） 来提供故障隔离。 
- 必须为失败原子性、 一致性、 隔离和持久性 （酸） 的任何部分监视关键的客户数据。 
- 必须从损坏保护客户数据。它必须是主动扫描或受监控，可修复的并且可恢复。 
- 大多数数据丢失结果客户操作，因此允许客户恢复自己使用 GUI 使他们能够还原意外删除的项。 
 
通过这些原则，加上可靠的测试和验证，我们云服务的构建 Office 365 是能够满足和超过的客户的需求，同时确保连续创新和改进的平台。 

## <a name="related-links"></a>相关的链接

- [处理数据损坏](office-365-dealing-with-data-corruption.md)
- [恶意软件和勒索软件防护](office-365-malware-and-ransomware-protection.md)
- [监视和自愈](office-365-monitoring-and-self-healing.md)
- [Exchange 数据恢复能力](office-365-exchange-data-resiliency.md)
- [SharePoint 数据恢复能力](office-365-sharepoint-data-resiliency.md)