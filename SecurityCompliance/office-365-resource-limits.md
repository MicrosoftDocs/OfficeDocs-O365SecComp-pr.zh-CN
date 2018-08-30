---
title: Office 365 资源限制
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
description: 摘要： 有关资源的信息的 Office 365 中的各种应用程序的限制。
ms.openlocfilehash: a2e7ef42f9bf224363f3b10a5e450d6127f11585
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526069"
---
# <a name="resource-limits"></a><span data-ttu-id="aaa98-103">资源限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-103">Resource Limits</span></span>

<span data-ttu-id="aaa98-p101">资源限制强制使用配额 （限制） 和限制。Azure Active Directory 和单个 Office 365 服务，请同时使用。限制是特定于服务的和更改随着时间的推移，如添加新功能。有关的各种服务的当前限制的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="aaa98-p101">Resource limits are enforced using quotas (limits) and throttling. Azure Active Directory and the individual Office 365 services use both. Limits are service-specific and change over time as new capabilities are added. For details on the current limits for the various services, see the following topics:</span></span>
- [<span data-ttu-id="aaa98-108">Azure Active Directory service 限制和限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-108">Azure Active Directory service limits and restrictions</span></span>](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [<span data-ttu-id="aaa98-109">Exchange Online 限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [<span data-ttu-id="aaa98-110">Exchange Online Protection 限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="aaa98-111">SharePoint Online 的软件边界和限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="aaa98-112">Skype 的业务限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="aaa98-113">Yammer REST API 和速率限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="aaa98-114">在 Sway 文件大小限制</span><span class="sxs-lookup"><span data-stu-id="aaa98-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="aaa98-p102">除了这些限制，整个 Azure Active Directory 和 Office 365 中使用几种限制机制。限制服务中是尤其重要，假定将针对广泛使用的服务的客户的优化在 Microsoft 数据中心中的网络资源。限制机制包括：</span><span class="sxs-lookup"><span data-stu-id="aaa98-p102">In addition to these limits, several throttling mechanisms are used throughout Azure Active Directory and Office 365. Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services. Throttling mechanisms include:</span></span>
- <span data-ttu-id="aaa98-118">Azure Active Directory 和 Office 365 功能用户级别限制的限制的事务或 （通过脚本或代码） 可以由单个用户执行的并发呼叫数。</span><span class="sxs-lookup"><span data-stu-id="aaa98-118">Azure Active Directory and Office 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="aaa98-p103">默认限制策略的 PowerShell 分配给在租户创建每个租户。这些设置会影响其他项，如可由一名管理员打开的同时 PowerShell 会话的最大数目。</span><span class="sxs-lookup"><span data-stu-id="aaa98-p103">A default PowerShell throttling policy is assigned to each tenant at tenant creation. These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="aaa98-121">每个 Exchange Online 客户已针对 EWS 客户端操作的默认 Exchange Web Services (EWS) 策略和限制的适用于所有 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="aaa98-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
