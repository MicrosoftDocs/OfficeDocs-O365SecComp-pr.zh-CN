---
title: Office 365 资源限制
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
description: '摘要: 有关 Office 365 中各种应用程序的资源限制的信息。'
ms.openlocfilehash: ee44bde8bd93d3628ed3f31f5bbbce024a3056b5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220212"
---
# <a name="resource-limits"></a><span data-ttu-id="5fd52-103">资源限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-103">Resource Limits</span></span>

<span data-ttu-id="5fd52-p101">使用配额 (限制) 和限制来强制实施资源限制。Azure Active Directory 和单独的 Office 365 服务使用两者。在添加新功能时, 限制因服务而异并随时间而变化。有关各种服务的当前限制的详细信息, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="5fd52-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="5fd52-108">Azure Active Directory 服务限制和限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="5fd52-109">Exchange Online 限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="5fd52-110">Exchange Online Protection 限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="5fd52-111">SharePoint Online 软件边界和限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="5fd52-112">Skype for business 限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="5fd52-113">Yammer REST API 和速率限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="5fd52-114">Sway 中的文件大小限制</span><span class="sxs-lookup"><span data-stu-id="5fd52-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="5fd52-p102">除了这些限制之外, 在整个 Azure Active Directory 和 Office 365 中使用了多个限制机制。如果 Microsoft 数据中心中的网络资源针对使用服务的广泛客户进行了优化, 则服务中的限制尤为重要。限制机制包括:</span><span class="sxs-lookup"><span data-stu-id="5fd52-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="5fd52-118">Azure Active Directory 和 Office 365 功能用户级别限制, 它限制单个用户可以执行的事务或并发呼叫 (按脚本或代码) 的数量。</span><span class="sxs-lookup"><span data-stu-id="5fd52-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="5fd52-p103">在创建租户时, 会为每个租户分配一个默认的 PowerShell 限制策略。这些设置会影响其他项目, 如一台管理员可打开的最大并发 PowerShell 会话数。</span><span class="sxs-lookup"><span data-stu-id="5fd52-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="5fd52-121">每个 Exchange Online 客户都有一个默认的 exchange Web 服务 (EWS) 策略, 该策略针对 EWS 客户端操作进行了优化, 并具有适用于所有 Outlook 客户端的限制。</span><span class="sxs-lookup"><span data-stu-id="5fd52-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
