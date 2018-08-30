---
title: Office 365 中的租户隔离
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
description: Microsoft 如何强制实施 Office 365 租户隔离的摘要。
ms.openlocfilehash: fcf66ee65c2a4cfdf73ae0eac77f54bd555d059d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525467"
---
# <a name="tenant-isolation-in-office-365"></a>Office 365 中的租户隔离

云计算同时跨多种客户共享的常见基础结构的概念，从而导致的规模经济的主要优点之一。此概念称为*多租户*。Microsoft 致力于持续确保我们云服务的多租户体系结构支持企业级安全、 保密性、 隐私、 完整性和可用性标准。

根据重要方面的投入以及收集从[可信赖计算](https://www.microsoft.com/en-us/twc/default.aspx)[安全开发生命周期](http://www.microsoft.com/security/sdl/default.aspx)的体验，Microsoft 云服务在设计假定所有可能有害的所有租户其他租户，我们已实施安全措施，以阻止的操作的一个租户的影响的安全或服务的另一个租户或访问其他租户的内容。

维护多租户环境中的租户隔离的两个主要目标是：
1.  跨租户; 到，客户内容防止泄露或未经授权的访问和
2.  阻止的操作的一个租户产生不利影响其他租户的服务

整个 Office 365，以防止客户会影响 Office 365 服务或应用程序或未经授权访问的信息的其他租户或 Office 365 系统本身，包括已实现多个窗体的保护：
- Office 365 服务的每个租户中的客户内容的逻辑隔离被通过 Azure Active Directory 授权和基于角色的访问控制。
- SharePoint Online 提供数据存储级别的隔离机制。
- Microsoft 使用严格的物理安全、 背景筛选和多层的加密策略来保护保密性和客户内容的完整性。所有 Office 365 数据中心都具有生物访问控制，与最要求棕榈打印物理访问。此外，所有基于美国的 Microsoft 员工完成所需成功标准背景检查作为雇用过程的一部分。用于 Office 365 中的管理访问的控件的详细信息，请参阅[Office 365 管理访问控制](office-365-administrative-access-controls-overview.md)。
- Office 365 使用加密客户内容在 rest 和在传输过程中，包括 BitLocker，每个文件加密的服务商技术传输层安全性 (TLS) 和 Internet 协议安全性 (IPsec)。有关 Office 365 中的加密的详细信息，请参阅[Office 365 中的数据加密技术](office-365-encryption-in-the-microsoft-cloud-overview.md)。

在一起，上面列出保护提供提供威胁保护和缓解等价于单独的物理隔离提供的强健逻辑隔离控件。

## <a name="related-links"></a>相关的链接
- [Azure Active Directory 中的隔离和访问控制](office-365-isolation-in-azure-active-directory.md)
- [Office Graph 和 Delve 中的租户隔离](office-365-isolation-in-graph-and-delve.md)
- [Office 365 搜索中的租户隔离](office-365-isolation-in-office-365-search.md)
- [Office 365 视频中的租户隔离](office-365-isolation-in-office-365-video.md)
- [资源限制](office-365-resource-limits.md)
- [监视和测试租户边界](office-365-monitoring-and-testing.md)
- [Office 365 中的隔离和访问控制](office-365-isolation-in-office-365.md)