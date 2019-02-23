---
title: Office 365 电子数据展示和搜索功能概述
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
description: 有关电子数据展示功能的概述, 以及 Office 365 中用于审核使用和透明度的其他搜索功能。
ms.openlocfilehash: 0d1d0341407546659f4efffac8409edd46312810
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214853"
---
# <a name="ediscovery-and-search-features"></a>电子数据展示和搜索功能 

## <a name="ediscovery"></a>电子数据展示
电子数据展示功能为管理员、合规专员和其他经授权的用户提供了单一位置, 以在 Office 365 用户活动中进行全面调查。具有适当权限的安全主管可以执行搜索并对内容进行就地保留。搜索结果与从内容搜索中获取的结果相同, 不同之处在于为应用的任何保留创建电子数据展示事例。来自电子数据展示搜索的结果将针对安全性进行加密, 并且可以使用[高级电子数据展示](https://support.office.com/article/office-365-advanced-ediscovery-fd53438a-a760-45f6-9df4-861b50161ae4)来分析导出的数据。

## <a name="content-search"></a>内容搜索
[内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)是安全 & 合规性中心中的新电子数据展示搜索工具, 它提供了通过以前的电子数据展示搜索工具改进的扩展能力和性能功能。您可以使用内容搜索来搜索邮箱、公用文件夹、SharePoint Online 网站和 OneDrive for business 位置。内容搜索专为进行超大型搜索而设计。您可以搜索的邮箱和网站的数量没有限制。对于可以同时运行的搜索的数量也没有限制。在运行搜索后, 搜索页面的详细信息窗格中将显示内容源的数量和估计的搜索结果数, 您可以在其中预览结果, 或将其导出到本地计算机。如果您的组织具有 office 365 企业版 E5 订阅, 您还可以使用[office 365 高级电子数据展示](http://go.microsoft.com/fwlink/p/?LinkID=620116)的强大分析功能来准备要分析的[结果](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a#prepare)。

## <a name="audit-log-search"></a>审核日志搜索
除了在 Office 365 组织中跟踪更改之外, 客户还可以查看审核报告和导出审核日志。为 Office 365 租户启用审核后, 会在事件日志中记录该租户的用户和管理活动并使其可供搜索。例如, 您可以使用邮箱审核日志记录来跟踪邮箱所有者之外的用户对邮箱执行的操作。此外, 合规性监察官可以使用搜索和筛选功能来查看用户是否已查看或下载了特定文档, 或者管理员是否已在过去的90天内执行了用户管理活动或对租户配置进行了更改。搜索结果可包含有关用户或管理员执行的特定活动的有价值的取证信息。有关在 office 365 中记录的用户和管理活动的说明, 请参阅[office 365 中的审核活动](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c#auditlogevents)。

SharePoint Online 和 OneDrive for business 中的事件在日志中出现的30分钟内显示在日志中。来自 Exchange Online 的事件出现在发生的24小时内的审核日志中。来自 azure ad 的登录事件在发生几分钟内可用, 并且来自 azure ad 的其他目录事件在发生24小时内可用。还可以导出审核日志搜索结果中的事件, 以供进一步分析。(最多可以从单个审核日志搜索中导出50000个条目。若要导出此限制的更多条目, 请缩小日期范围或运行多个审核日志搜索。

下表详细介绍了活动报告中显示的一些信息。有关每个 office 365 工作负荷所收集的属性的详细信息, 请参阅[Office 365 审核日志中的详细属性](https://support.office.com/article/detailed-properties-in-the-office-365-audit-log-ce004100-9e7f-443e-942b-9b04098fcfc3
)。

| 属性 | 说明 |
|----------------|----------------------------------------------------------------------------------------------------------------------|
| 日期 | 事件的日期和时间 |
| 用户 | 执行操作的用户 |
| ClientIP | 记录活动时使用的设备的 IPv4 或 IPv6 地址。 |
| CreationTime | 用户执行活动时的日期和时间 (采用协调通用时间 (UTC))。 |
| EventSource | 标识发生的事件。可能的值为 SharePoint 和 ObjectModel。 |
| ID | 报告条目的 ID。ID 唯一标识报告条目。 |
| Operation | 用户或活动的名称, 对应于在 "此用户活动的显示结果" 中选择的值。 |
| OrganizationId | 发生事件的组织的 Office 365 服务的 GUID。 |
| UserAgent | 浏览器所提供的有关用户浏览器的信息。 |
| UserId | 执行操作 (在 Operation 属性中指定) 导致记录记录的用户。 |
| UserType | 执行操作的用户的类型。以下值指示用户类型。 |
|  | 0表示常规用户。 |
|  | 2表示 Office 365 组织中的管理员。 |
|  | 3表示 Microsoft 数据中心管理员或数据中心系统帐户。 |
| 工作负荷 | 发生活动的 Office 365 服务。此属性的可能值为: |
|  | Exchange Online |
|  | SharePoint Online |
|  | OneDrive for Business |
|  | Azure Active Directory 报告 |


有关搜索 office 365 审核日志的详细步骤, 请参阅[在 office 365 安全 & 合规中心中搜索审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)。

## <a name="search-unified-audit-log"></a>搜索统一审核日志
Security & 合规性中心中的审核日志搜索功能可用于搜索统一审核日志。Office 365 还提供了使用远程 PowerShell 搜索此日志的功能。具体说来, exchange online PowerShell 中的[UnifiedAuditLog cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/Search-UnifiedAuditLog?view=exchange-ps)可用于搜索与来自 Exchange online、SharePoint online、OneDrive for business 和 Azure AD 的用户操作相关的事件的统一审核日志。您可以搜索指定日期范围内的所有事件, 也可以根据特定条件 (如特定操作、执行操作的用户或目标对象) 筛选结果。管理员最多可使用3个同时运行的 Exchange Online PowerShell 会话来拆分大型日期范围搜索。
