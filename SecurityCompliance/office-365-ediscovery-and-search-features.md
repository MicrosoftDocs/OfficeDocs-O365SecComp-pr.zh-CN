---
title: Office 365 电子数据展示和搜索功能概述
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
description: 电子数据展示功能和 Office 365 中的审核使用和透明度其他搜索功能的概述。
ms.openlocfilehash: 2d5cc2533c195b51f685aebd8da4462518116905
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525436"
---
# <a name="ediscovery-and-search-features"></a>电子数据展示和搜索功能 

## <a name="ediscovery"></a>电子数据展示
电子数据展示功能的管理员，合规部主管，提供了一个位置和其他授权用户进行全面调查到 Office 365 用户活动。具有适当权限的安全官员可以执行搜索并保留对内容的位置。搜索结果是相同的结果获得内容搜索，只不过应用任何保留为创建电子数据展示事例。为了安全，加密的电子数据展示搜索结果，并可以使用[高级电子数据展示](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)分析导出的数据。

## <a name="content-search"></a>内容搜索
[内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)是以前的电子数据展示搜索工具中的安全性和合规性中心提供改进缩放和性能功能的新电子数据展示搜索工具。内容搜索可用于搜索邮箱、 公用文件夹、 SharePoint Online 网站和 OneDrive for Business 位置。内容搜索专为大型搜索而设计。有邮箱和网站，您可以搜索的数量没有限制。还有没有限制可以同时运行的搜索数。在运行搜索、 内容源的数量和搜索结果显示在搜索页上，可在其中预览结果，或将其导出到本地计算机的详细信息窗格中的估计的数目。如果贵组织拥有的 Office 365 企业 E5 订阅，则可以[准备结果](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)以供分析使用[Office 365 高级电子数据展示](http://go.microsoft.com/fwlink/p/?LinkID=620116)的强大分析功能。

## <a name="audit-log-search"></a>审核日志搜索
除了跟踪其 Office 365 组织中的更改，客户可以查看审核报告和导出审核日志。一旦 Office 365 租户启用了审核，用户和该租户管理活动是记录在事件日志，并使其可供搜索。例如，您可以使用邮箱审核日志记录来跟踪邮箱所有者以外的用户邮箱上执行的操作。此外，合规部主管可以使用搜索和筛选功能查看如果用户具有查看或下载特定文档，或者如果管理员已执行用户管理活动或对在过去 90 天的租户配置所做的更改。搜索结果可以包含特定用户或管理员进行的活动的有价值鉴定信息。用户和管理 Office 365 中记录的活动的说明，请参阅[Office 365 中的 Audited 活动](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents)。

SharePoint Online 和 OneDrive for Business 中的事件日志中显示其发生的 30 分钟内。匹配项的 24 小时内的审核日志中出现的 Exchange Online 中的事件。从 Azure AD 的登录事件匹配项，分钟内都可用且从 Azure AD 其他目录事件匹配项的 24 小时内。此外可以进行进一步分析导出审核日志搜索结果中的事件。（最多 50,000 条目可以从单个审核日志搜索导出。若要导出此限制的多个条目，减少了日期范围，或运行多个审核日志搜索。）

下表详细一些活动报告中显示的信息。请参阅[Office 365 中的详细的属性审核日志](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
)的有关哪些收集属性的每个 Office 365 工作负载的详细信息。

| 属性 | 描述 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日期 | 该事件的日期和时间 |
| 用户 | 执行操作的用户 |
| ClientIP | 活动已记录时所使用的设备的 IPv4 或 IPv6 地址。 |
| CreationTime | 日期和时间以协调世界时 (UTC) 用户执行活动时。 |
| EventSource | 标识事件发生。可能的值为 SharePoint 和 ObjectModel。 |
| ID | 报告条目 ID。ID 唯一标识报告条目。 |
| Operation | 用户或活动，对应于此用户活动的显示结果中选择的值的名称。 |
| 组织 Id | 发生事件的组织的 Office 365 服务的 GUID。 |
| UserAgent | 有关用户的浏览器提供的浏览器的信息。 |
| 用户 Id | 执行操作 （在操作属性中指定） 所记录的记录所导致的用户。 |
| UserType | 用户执行操作的类型。下列值指示用户类型。 |
|  | 0 指示常规用户。 |
|  | 2 指示您的 Office 365 组织中的管理员。 |
|  | 3 指示 Microsoft 数据中心管理员或 datacenter 系统帐户。 |
| 工作负荷 | Office 365 服务中的活动发生。此属性的可能值包括： |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Azure Active Directory 报告 |


搜索 Office 365 的详细步骤审核日志，请参阅[Office 365 安全性和合规性中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="search-unified-audit-log"></a>搜索统一的审核日志
安全性和合规性中心中的审核日志搜索功能可用于搜索的统一的审核日志。Office 365 还提供了搜索使用远程 PowerShell 此日志的功能。具体而言，Exchange Online PowerShell 中的[搜索 UnifiedAuditLog cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps)可用于搜索统一的审核日志中的用户操作与有关从 Exchange Online、 SharePoint Online 的 OneDrive for Business 和 Azure AD 的事件。您可以搜索指定的日期范围中的所有事件或可以筛选基于特定的标准，如特定操作，执行操作或目标对象的用户的结果。管理员可以使用最多为 3 同时运行的 Exchange Online PowerShell 会话拆分大的日期范围搜索。
