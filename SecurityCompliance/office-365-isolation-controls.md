---
title: Office 365 隔离控制
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
description: 摘要： 在 Office 365 中的隔离控件的说明。
ms.openlocfilehash: 3a5c06d0675a4503d9f5e5edd58535688fb9180a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526064"
---
# <a name="office-365-isolation-controls"></a>Office 365 隔离控制 

Microsoft 持续致力于确保 Office 365 的多租户体系结构支持企业级安全、 保密性、 隐私、 完整性和可用性的[标准](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)，以及本地和国际标准。给定的规模和服务由 Microsoft 提供的范围，就像变得比较困难和非-最经济如果重要的人员交互是需要管理 Office 365。Office 365 服务提供通过多个全局分布式数据中心，以高度自动化的方式，其中极少的数据中心操作需要人工 touch 和更少的操作所需访问客户内容。我们的人员支持这些服务和数据中心使用自动化的工具和高度安全的远程访问。有关操作的详细信息的某些大型服务是在 Office 365 中，请参阅[场景查看面向 IT 专业人员的 Office 365 的隐藏](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)操作。

Office 365 由提供重要的业务功能并参与到整个 Office 365 体验的多个服务。这些服务的每个旨在为自我包含并与另一个集成。Office 365 设计与[面向服务体系结构](https://msdn.microsoft.com/library/aa480021.aspx)，是指设计和开发提供定义完善的业务功能和[操作安全性的可互操作服务的窗体中的软件的原则保证](http://www.microsoft.com/download/details.aspx?id=40872)，框架，它采用知识获得通过各种 Microsoft，包括 Microsoft[安全开发生命周期](https://www.microsoft.com/sdl/default.aspx)、 [Microsoft 安全响应中心](https://technet.microsoft.com/library/dn440717.aspx)和深入对是唯一的功能网络安全威胁横向的认知度。

Office 365 服务与每个其他，进行互操作，但他们设计和实现，以便他们可以部署和操作作为自治相互独立的服务。Microsoft 隔离职责和 Office 365 以减少未经授权或无意的修改机会的职责范围或误用组织资产。Office 365 团队的全面的基于角色的访问控制机制用一部分定义了角色。

## <a name="customer-content-isolation"></a>内容隔离客户
属于租户的所有客户内容都被隔离从其他租户和管理 Office 365 中使用的操作和系统数据。整个 Office 任何的 365 Office 365 服务或应用程序或租户或本身的 Office 365 系统的信息对未授权访问任何获得的威胁的风险降至最低已经实现多个窗体的保护。有关 Microsoft 如何实现的 Office 365 中的租户数据的逻辑隔离的信息，请参阅[Office 365 中的租户隔离](office-365-tenant-isolation-overview.md)。
