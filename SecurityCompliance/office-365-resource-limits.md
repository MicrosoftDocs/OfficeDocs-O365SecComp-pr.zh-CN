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
# <a name="resource-limits"></a>资源限制

资源限制强制使用配额 （限制） 和限制。Azure Active Directory 和单个 Office 365 服务，请同时使用。限制是特定于服务的和更改随着时间的推移，如添加新功能。有关的各种服务的当前限制的详细信息，请参阅以下主题：
- [Azure Active Directory service 限制和限制](https://msdn.microsoft.com/en-us/library/azure/dn764971.aspx)
- [Exchange Online 限制](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx)
- [Exchange Online Protection 限制](https://technet.microsoft.com/en-us/library/exchange-online-protection-limits.aspx)
- [SharePoint Online 的软件边界和限制](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [Skype 的业务限制](https://technet.microsoft.com/en-us/library/skype-for-business-online-limits.aspx)
- [Yammer REST API 和速率限制](https://developer.yammer.com/docs/rest-api-rate-limits)
- [在 Sway 文件大小限制](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

除了这些限制，整个 Azure Active Directory 和 Office 365 中使用几种限制机制。限制服务中是尤其重要，假定将针对广泛使用的服务的客户的优化在 Microsoft 数据中心中的网络资源。限制机制包括：
- Azure Active Directory 和 Office 365 功能用户级别限制的限制的事务或 （通过脚本或代码） 可以由单个用户执行的并发呼叫数。
- 默认限制策略的 PowerShell 分配给在租户创建每个租户。这些设置会影响其他项，如可由一名管理员打开的同时 PowerShell 会话的最大数目。
- 每个 Exchange Online 客户已针对 EWS 客户端操作的默认 Exchange Web Services (EWS) 策略和限制的适用于所有 Outlook 客户端。
