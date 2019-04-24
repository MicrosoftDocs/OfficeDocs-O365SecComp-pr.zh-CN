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
# <a name="office-365-management-activity-api"></a>Office 365 管理活动 API
Microsoft 提供了 reporting services, 使管理员能够获取有关其 Office 365 租户的聚合事务信息。 [Office 365 管理活动 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)使用行业标准的 RESTful 设计和 OAuth v2 进行身份验证, 使您能够轻松开始体验检索数据, 并将数据 ingesting 到可视化工具和应用程序中。 API 提供了一个数据源, 其中包括有关 Office 365 中的用户、管理员、操作和安全活动的信息。 数据可出于法规目的而保留, 也可与本地基础结构或其他源中的日志数据采购结合使用, 以构建企业范围内的操作、安全性和合规性的监控解决方案。

使用 Office 365 管理活动 API，可从 Office 365 和 Azure Active Directory 活动日志中获取各个用户、管理员、系统以及策略操作和事件的相关信息。 API 提供了一个一致的审核架构, 其中包含10个以上的字段, 这些字段在所有服务中都是通用的。 这使组织能够在事件之间建立轻松的连接, 并允许新方法对数据进行原因。 几十个独立软件供应商 (isv) 与 Microsoft 建立了合作, 并基于 API 建立了解决方案。 有些解决方案仅重点关注 Office 365 数据, 而其他解决方案则提供从多个云提供程序和内部部署系统中提取数据的功能, 以创建所有操作、安全性和合规性相关活动的统一视图。 有关详细信息, 请参阅[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。
