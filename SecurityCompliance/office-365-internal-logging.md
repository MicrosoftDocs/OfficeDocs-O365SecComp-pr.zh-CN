---
title: Office 365 的 Office 365 工程内部日志记录
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 说明如何内部日志记录的 Office 365 工程团队的工作原理。
ms.openlocfilehash: 4cade759fb4c095565b4e1f85ce15ed546177082
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038185"
---
# <a name="internal-logging-for-office-365-engineering"></a>Office 365 工程部的内部日志记录
除了事件和可用于客户的日志数据，还有一些可供 Office 365 工程师内部日志数据收集系统。许多不同类型的日志数据上载到数据计算调用宇宙服务的内部、 大从 Office 365 服务器。每个服务工作组会从其各自的服务器的审核日志上载到聚合和分析的宇宙数据库。此数据传输通过 FIPS 140 2 验证 TLS 连接上专门批准的端口和协议使用专有自动化工具调用 Office 数据加载程序 (ODL) 发生此事件。工具用于在 Office 365 中收集和处理审核记录不允许永久或不可逆转地更改原始审核记录的内容或时间排序。

服务团队使用宇宙作为中央存储库的应用程序使用率，来测量系统和运行性能，并查找异常情况和可能指示问题或安全问题的模式进行分析。每个服务工作组上载比较基准的登录到宇宙，具体取决于他们希望分析，通常包括：
- 事件日志
- AppLocker 日志
- 性能数据
- 系统中心数据
- 呼叫详细记录
- 体验质量数据
- IIS Web 服务器日志
- SQL Server 日志
- 系统日志数据
- 安全审核日志

将数据上载到宇宙之前, ODL 应用程序使用清理服务模糊化包含客户数据，例如租户信息和最终用户身份信息的任何字段并将这些字段替换哈希值。Anonymized 和哈希日志是重写，然后上载到宇宙。服务团队对宇宙中进行关联，警报，并报告其数据运行作用域的查询。由服务团队中; 确定宇宙中的审核日志数据保留期大多数审核日志数据保留 90 天或更长时间支持安全事件调查，从而满足法规保留要求。

Office 365 中宇宙存储的数据访问仅限于授权的人员。Microsoft 限制对服务工作组成员的负责审核功能有限子集的审核功能的管理。这些团队成员不具有能够修改或删除数据从宇宙，并记录和审核日志记录机制宇宙对所有更改。

每个服务工作组的授权某些应用程序来执行特定的分析来访问其日志数据进行分析。例如，Office 365 安全工作组使用数据从宇宙通过专有的事件日志分析程序关联，通知中，并在 Office 365 生产环境中生成可操作可能可疑活动的报告。若要更正漏洞，并提高该服务的总体性能使用此数据的报告。如果特定警报或报表需要进一步调查，服务人员可以请求将数据导入回 Office 365 服务。以来特定日志正在从宇宙导入中加密和服务人员有权访问解密密钥，目标日志以编程方式传递通过作用域的结果返回到授权的服务人员解密服务。从本练习发现的任何漏洞报告并上报使用 Microsoft 的标准安全事件管理通道。
