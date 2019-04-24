---
title: Office 365 管理活动 API
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-analytics
description: 有关 Office 365 管理活动 API 的简短摘要。
ms.openlocfilehash: 3405eaac000111fb5d5f054edcbe6816aa9af9e7
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262554"
---
# <a name="office-365-management-activity-api"></a><span data-ttu-id="72bea-103">Office 365 管理活动 API</span><span class="sxs-lookup"><span data-stu-id="72bea-103">Office 365 Management Activity API</span></span>
<span data-ttu-id="72bea-104">Microsoft 提供了 reporting services, 使管理员能够获取有关其 Office 365 租户的聚合事务信息。</span><span class="sxs-lookup"><span data-stu-id="72bea-104">Microsoft provides reporting services that enable administrators to obtain aggregated transactional information about their Office 365 tenant.</span></span> <span data-ttu-id="72bea-105">[Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)使用行业标准的 RESTful 设计和 OAuth v2 进行身份验证, 使您能够轻松开始体验检索数据, 并将数据 ingesting 到可视化工具和应用程序中。</span><span class="sxs-lookup"><span data-stu-id="72bea-105">The [Office 365 Management Activity API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) uses an industry-standard RESTful design and OAuth v2 for authentication, which makes it easy to start experimenting with retrieving data and ingesting it into visualization tools and applications.</span></span> <span data-ttu-id="72bea-106">API 提供了一个数据源, 其中包括有关 Office 365 中的用户、管理员、操作和安全活动的信息。</span><span class="sxs-lookup"><span data-stu-id="72bea-106">The API provides a data feed that includes information about user, administrator, operations, and security activity in Office 365.</span></span> <span data-ttu-id="72bea-107">数据可出于法规目的而保留, 也可与本地基础结构或其他源中的日志数据采购结合使用, 以构建企业范围内的操作、安全性和合规性的监控解决方案。</span><span class="sxs-lookup"><span data-stu-id="72bea-107">The data can be kept for regulatory purposes, or combined with log data procured from an on-premises infrastructure or other sources to build a monitoring solution for operations, security, and compliance across the enterprise.</span></span>

<span data-ttu-id="72bea-108">使用 Office 365 管理活动 API，可从 Office 365 和 Azure Active Directory 活动日志中获取各个用户、管理员、系统以及策略操作和事件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="72bea-108">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="72bea-109">API 提供了一个一致的审核架构, 其中包含10个以上的字段, 这些字段在所有服务中都是通用的。</span><span class="sxs-lookup"><span data-stu-id="72bea-109">The API provides a consistent audit schema with over 10 fields that are in common across all the services.</span></span> <span data-ttu-id="72bea-110">这使组织能够在事件之间建立轻松的连接, 并允许新方法对数据进行原因。</span><span class="sxs-lookup"><span data-stu-id="72bea-110">This allows organizations to make easy connections between events, and it enables new ways to reason over the data.</span></span> <span data-ttu-id="72bea-111">几十个独立软件供应商 (isv) 与 Microsoft 建立了合作, 并基于 API 建立了解决方案。</span><span class="sxs-lookup"><span data-stu-id="72bea-111">Dozens of Independent Software Vendors (ISVs) have partnered with Microsoft and built solutions based on the API.</span></span> <span data-ttu-id="72bea-112">有些解决方案仅重点关注 Office 365 数据, 而其他解决方案则提供从多个云提供程序和内部部署系统中提取数据的功能, 以创建所有操作、安全性和合规性相关活动的统一视图。</span><span class="sxs-lookup"><span data-stu-id="72bea-112">Some solutions are focused solely on Office 365 data, while others provide the ability to ingest data from multiple cloud providers and on-premises systems to create a unified view of all operations, security, and compliance-related activity.</span></span> <span data-ttu-id="72bea-113">有关详细信息, 请参阅[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。</span><span class="sxs-lookup"><span data-stu-id="72bea-113">For more information, see the [Office 365 Management Activity API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>
