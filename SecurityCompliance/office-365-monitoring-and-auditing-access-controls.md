---
title: Office 365 监控和审核访问控制
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
description: 摘要： 的各种监控和审核访问控件的 Office 365 中的可用摘要。
ms.openlocfilehash: 7ef25d62ce3c4fa320dd0b164183c6f67be7d76d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525924"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>监控和审核 Office 365 中的访问控制

Microsoft 执行大量的监控和审核的所有委派、 所有权限，使用和 Office 365 中出现的所有操作。Office 365 的访问控制是构建的最小特权原则，并且要合并数据访问控制和审核的原则自动化的过程：
- 跟踪对一个唯一的用户，使管理员负责客户内容其处理所有允许的访问权限。
- 访问控制请求、 批准和管理操作日志捕获的安全见解和恶意事件的分析。
- 访问级别阐述了近乎实时的基于的安全组成员身份，以确保只有具有授权业务理由和符合资格要求用户有权访问系统。
- 定期独立第三方符合[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001) [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)，通过将 office 365，其访问控制和支持的服务，包括 Azure Active Directory 和我们物理数据中心，审核[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)和其他[标准](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。
- Office 365 工程师需要查看提升的访问权限的最佳实践和风险的按年安全培训和确认 Microsoft 的安全和隐私策略继续维护其与服务的权利。

检测到可疑活动，如短时间内的多个失败登录时，将触发自动的通知。Office 365 安全响应团队使用机器学习和 big 数据分析，来查看和分析不规则访问模式的活动和主动响应异常和非法活动。Microsoft 还使用专用的工作组的透过测试人员和参与定期红色团队和蓝色团队练习查找安全和访问控制服务中的问题。客户还可能使用审核报告和管理活动 Office 365 提供的 API 验证访问控制系统的有效性。 

有关详细信息，请参阅[Office 365 管理活动 API 参考](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)和[审核和 Office 365 中的报告](office-365-auditing-and-reporting-overview.md)。
