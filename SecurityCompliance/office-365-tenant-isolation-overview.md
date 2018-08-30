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
# <a name="tenant-isolation-in-office-365"></a><span data-ttu-id="45d65-103">Office 365 中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="45d65-103">Tenant Isolation in Office 365</span></span>

<span data-ttu-id="45d65-p101">云计算同时跨多种客户共享的常见基础结构的概念，从而导致的规模经济的主要优点之一。此概念称为*多租户*。Microsoft 致力于持续确保我们云服务的多租户体系结构支持企业级安全、 保密性、 隐私、 完整性和可用性标准。</span><span class="sxs-lookup"><span data-stu-id="45d65-p101">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale. This concept is called *multi-tenancy*. Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="45d65-107">根据重要方面的投入以及收集从[可信赖计算](https://www.microsoft.com/en-us/twc/default.aspx)[安全开发生命周期](http://www.microsoft.com/security/sdl/default.aspx)的体验，Microsoft 云服务在设计假定所有可能有害的所有租户其他租户，我们已实施安全措施，以阻止的操作的一个租户的影响的安全或服务的另一个租户或访问其他租户的内容。</span><span class="sxs-lookup"><span data-stu-id="45d65-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) and the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="45d65-108">维护多租户环境中的租户隔离的两个主要目标是：</span><span class="sxs-lookup"><span data-stu-id="45d65-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>
1.  <span data-ttu-id="45d65-109">跨租户; 到，客户内容防止泄露或未经授权的访问和</span><span class="sxs-lookup"><span data-stu-id="45d65-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.  <span data-ttu-id="45d65-110">阻止的操作的一个租户产生不利影响其他租户的服务</span><span class="sxs-lookup"><span data-stu-id="45d65-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="45d65-111">整个 Office 365，以防止客户会影响 Office 365 服务或应用程序或未经授权访问的信息的其他租户或 Office 365 系统本身，包括已实现多个窗体的保护：</span><span class="sxs-lookup"><span data-stu-id="45d65-111">Multiple forms of protection have been implemented throughout Office 365 to prevent customers from compromising Office 365 services or applications or gaining unauthorized access to the information of other tenants or the Office 365 system itself, including:</span></span>
- <span data-ttu-id="45d65-112">Office 365 服务的每个租户中的客户内容的逻辑隔离被通过 Azure Active Directory 授权和基于角色的访问控制。</span><span class="sxs-lookup"><span data-stu-id="45d65-112">Logical isolation of customer content within each tenant for Office 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="45d65-113">SharePoint Online 提供数据存储级别的隔离机制。</span><span class="sxs-lookup"><span data-stu-id="45d65-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="45d65-p102">Microsoft 使用严格的物理安全、 背景筛选和多层的加密策略来保护保密性和客户内容的完整性。所有 Office 365 数据中心都具有生物访问控制，与最要求棕榈打印物理访问。此外，所有基于美国的 Microsoft 员工完成所需成功标准背景检查作为雇用过程的一部分。用于 Office 365 中的管理访问的控件的详细信息，请参阅[Office 365 管理访问控制](office-365-administrative-access-controls-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45d65-p102">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content. All Office 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access. In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process. For more information on the controls used for administrative access in Office 365, see [Office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="45d65-p103">Office 365 使用加密客户内容在 rest 和在传输过程中，包括 BitLocker，每个文件加密的服务商技术传输层安全性 (TLS) 和 Internet 协议安全性 (IPsec)。有关 Office 365 中的加密的详细信息，请参阅[Office 365 中的数据加密技术](office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="45d65-p103">Office 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec). For specific details about encryption in Office 365, see [Data Encryption Technologies in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="45d65-120">在一起，上面列出保护提供提供威胁保护和缓解等价于单独的物理隔离提供的强健逻辑隔离控件。</span><span class="sxs-lookup"><span data-stu-id="45d65-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="45d65-121">相关的链接</span><span class="sxs-lookup"><span data-stu-id="45d65-121">Related Links</span></span>
- [<span data-ttu-id="45d65-122">Azure Active Directory 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="45d65-122">Isolation and Access Control in Azure Active Directory</span></span>](office-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="45d65-123">Office Graph 和 Delve 中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="45d65-123">Tenant Isolation in the Office Graph and Delve</span></span>](office-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="45d65-124">Office 365 搜索中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="45d65-124">Tenant Isolation in Office 365 Search</span></span>](office-365-isolation-in-office-365-search.md)
- [<span data-ttu-id="45d65-125">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="45d65-125">Tenant Isolation in Office 365 Video</span></span>](office-365-isolation-in-office-365-video.md)
- [<span data-ttu-id="45d65-126">资源限制</span><span class="sxs-lookup"><span data-stu-id="45d65-126">Resource Limits</span></span>](office-365-resource-limits.md)
- [<span data-ttu-id="45d65-127">监视和测试租户边界</span><span class="sxs-lookup"><span data-stu-id="45d65-127">Monitoring and Testing Tenant Boundaries</span></span>](office-365-monitoring-and-testing.md)
- [<span data-ttu-id="45d65-128">Office 365 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="45d65-128">Isolation and Access Control in Office 365</span></span>](office-365-isolation-in-office-365.md)