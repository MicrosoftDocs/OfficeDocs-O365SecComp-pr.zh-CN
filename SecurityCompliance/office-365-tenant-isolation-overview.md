---
title: Office 365 中的租户隔离
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
description: Microsoft 对 Office 365 强制实施租户隔离的方式的摘要。
ms.openlocfilehash: dceff3b73ac01d3e0422a190d450ee28f7fdfb27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220272"
---
# <a name="tenant-isolation-in-office-365"></a><span data-ttu-id="c1e89-103">Office 365 中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="c1e89-103">Tenant Isolation in Office 365</span></span>

<span data-ttu-id="c1e89-p101">云计算的主要优势之一是多个客户之间共享的通用基础结构的概念, 从而导致规模经济。此概念称为*多租户*。Microsoft 连续工作, 以确保云服务的多租户体系结构支持企业级安全性、机密性、隐私、完整性和可用性标准。</span><span class="sxs-lookup"><span data-stu-id="c1e89-p101">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale. This concept is called *multi-tenancy*. Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="c1e89-107">根据可[信赖的计算](https://www.microsoft.com/en-us/twc/default.aspx)和[安全开发生命周期](http://www.microsoft.com/security/sdl/default.aspx)收集到的大量投资和经验, Microsoft 云服务的设计假定所有租户都有可能与所有租户进行恶意其他租户, 我们已经实施了安全措施, 以防止一个租户的操作影响另一个租户的安全或服务, 或访问其他租户的内容。</span><span class="sxs-lookup"><span data-stu-id="c1e89-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/en-us/twc/default.aspx) and the [Security Development Lifecycle](http://www.microsoft.com/security/sdl/default.aspx), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="c1e89-108">在多租户环境中维护租户隔离的两个主要目标是:</span><span class="sxs-lookup"><span data-stu-id="c1e89-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>
1.  <span data-ttu-id="c1e89-109">防止对租户之间的客户内容的泄露或未经授权访问;并</span><span class="sxs-lookup"><span data-stu-id="c1e89-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.  <span data-ttu-id="c1e89-110">防止一个租户的操作对另一个租户的服务产生不利影响</span><span class="sxs-lookup"><span data-stu-id="c1e89-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="c1e89-111">在整个 office 365 中实施了多种形式的保护, 以防止客户损害 Office 365 服务或应用程序, 或未经授权访问其他租户或 Office 365 系统本身的信息, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="c1e89-111">Multiple forms of protection have been implemented throughout Office 365 to prevent customers from compromising Office 365 services or applications or gaining unauthorized access to the information of other tenants or the Office 365 system itself, including:</span></span>
- <span data-ttu-id="c1e89-112">通过 Azure Active Directory 授权和基于角色的访问控制实现每个租户中的客户内容在 Office 365 服务中的逻辑隔离。</span><span class="sxs-lookup"><span data-stu-id="c1e89-112">Logical isolation of customer content within each tenant for Office 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="c1e89-113">SharePoint Online 在存储级别提供了数据隔离机制。</span><span class="sxs-lookup"><span data-stu-id="c1e89-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="c1e89-p102">Microsoft 使用严格的物理安全、背景屏蔽和多层加密策略来保护客户内容的机密性和完整性。所有 Office 365 数据中心都具有生物特征访问控制, 大多数情况下需要 palm 打印才能获得物理访问权限。此外, 所有基于美国的 Microsoft 员工都需要在聘用过程中成功完成标准背景检查。有关 office 365 中用于管理访问的控件的详细信息, 请参阅[office 365 管理访问控制](office-365-administrative-access-controls-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e89-p102">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content. All Office 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access. In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process. For more information on the controls used for administrative access in Office 365, see [Office 365 Administrative Access Controls](office-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="c1e89-p103">Office 365 使用服务端技术来加密 rest 和传输中的客户内容, 包括 BitLocker、文件加密、传输层安全性 (TLS) 和 Internet 协议安全性 (IPsec)。有关 office 365 中的加密的具体详细信息, 请参阅[office 365 中的数据加密技术](office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e89-p103">Office 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec). For specific details about encryption in Office 365, see [Data Encryption Technologies in Office 365](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="c1e89-120">上面列出的保护功能提供了可靠的逻辑隔离控制, 它们提供了与独立的物理隔离提供的威胁防护和缓解等效项。</span><span class="sxs-lookup"><span data-stu-id="c1e89-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="c1e89-121">相关链接</span><span class="sxs-lookup"><span data-stu-id="c1e89-121">Related Links</span></span>
- [<span data-ttu-id="c1e89-122">Azure Active Directory 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="c1e89-122">Isolation and Access Control in Azure Active Directory</span></span>](office-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="c1e89-123">Office Graph 和 Delve 中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="c1e89-123">Tenant Isolation in the Office Graph and Delve</span></span>](office-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="c1e89-124">Office 365 搜索中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="c1e89-124">Tenant Isolation in Office 365 Search</span></span>](office-365-isolation-in-office-365-search.md)
- [<span data-ttu-id="c1e89-125">Office 365 视频中的租户隔离</span><span class="sxs-lookup"><span data-stu-id="c1e89-125">Tenant Isolation in Office 365 Video</span></span>](office-365-isolation-in-office-365-video.md)
- [<span data-ttu-id="c1e89-126">资源限制</span><span class="sxs-lookup"><span data-stu-id="c1e89-126">Resource Limits</span></span>](office-365-resource-limits.md)
- [<span data-ttu-id="c1e89-127">监视和测试租户边界</span><span class="sxs-lookup"><span data-stu-id="c1e89-127">Monitoring and Testing Tenant Boundaries</span></span>](office-365-monitoring-and-testing.md)
- [<span data-ttu-id="c1e89-128">Office 365 中的隔离和访问控制</span><span class="sxs-lookup"><span data-stu-id="c1e89-128">Isolation and Access Control in Office 365</span></span>](office-365-isolation-in-office-365.md)