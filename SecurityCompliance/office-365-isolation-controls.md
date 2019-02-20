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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 中的隔离控件的说明。'
ms.openlocfilehash: ad39f300445485e46699b509f845ac363d3041fa
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090964"
---
# <a name="office-365-isolation-controls"></a>Office 365 隔离控制 

Microsoft 连续工作, 以确保 Office 365 的多租户体系结构支持企业级安全性、机密性、隐私、完整性和可用性[标准](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)以及本地和国际标准。鉴于 Microsoft 提供的规模和服务范围, 如果需要进行大量的人工交互, 则管理 Office 365 将困难且不经济。Office 365 服务通过多个全局分布式数据中心提供, 采用高度自动化的方式, 在极少的数据中心运营需要人为触摸, 甚至更少的操作需要访问客户内容的情况下。我们的员工通过自动化工具和高度安全的远程访问支持这些服务和数据中心。有关如何在 office 365 中运行大规模服务的一些详细信息, 请参阅[IT 专业人员在 office 365 中的幕后外观](https://channel9.msdn.com/Events/SharePoint-Conference/2014/SPC202)。

Office 365 由多个服务组成, 这些服务可提供重要的业务功能并参与整个 Office 365 体验。这些服务中的每一项都是独立的, 可以相互集成。Office 365 在设计时采用了[面向服务的体系结构](https://msdn.microsoft.com/library/aa480021.aspx)的原则, 定义为以可互操作的服务的形式设计和开发软件, 以提供完善定义的业务功能和[操作安全性保证](http://www.microsoft.com/download/details.aspx?id=40872): 一种框架, 其中包含通过与 microsoft 独有的各种功能获得的知识, 包括 microsoft[安全开发生命周期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全响应中心](https://technet.microsoft.com/library/dn440717.aspx)和深度cybersecurity 威胁前景的认知。

Office 365 服务相互互操作, 但它们已经过设计和实现, 以便可以将它们作为自治服务进行部署, 并相互独立。Microsoft segregates Office 365 的责任和职责范围, 以减少对组织资产进行未经授权或无意的修改或误用的机会。Office 365 团队已将角色定义为全面的基于角色的访问控制机制的一部分。

## <a name="customer-content-isolation"></a>客户内容隔离
属于租户的所有客户内容都与其他租户以及在 Office 365 的管理中使用的操作和系统数据隔离。在整个 office 365 中实施了多种形式的保护, 以最大限度地降低泄露任何 Office 365 服务或应用程序的风险, 或任何对租户或 Office 365 系统本身的信息进行未授权访问的风险。有关 Microsoft 如何在 office 365 中实现租户数据的逻辑隔离的信息, 请参阅[office 365 中的租户隔离](office-365-tenant-isolation-overview.md)。
