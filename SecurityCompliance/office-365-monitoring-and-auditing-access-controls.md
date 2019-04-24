---
title: Office 365 监控和审核访问控制
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
- M365-security-compliance
description: '摘要: Office 365 中可用的各种监视和审核访问控件的摘要。'
ms.openlocfilehash: 753acd1a0bd0d3b4a834263071d431b63836f399
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262534"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a>监视和审核 Office 365 中的访问控件

Microsoft 对所有委派执行全面的监视和审核, 并对 Office 365 中的所有操作执行所有权限的使用。 Office 365 访问控制是基于最小特权原则生成的自动化过程, 并包含数据访问控制和审核:
- 所有允许的访问都可与唯一用户进行跟踪, 管理员负责处理客户内容。
- 捕获访问控制请求、审批和管理操作日志, 以分析安全见解和恶意事件。
- 根据安全组成员身份, 在接近实时的情况中查看访问级别, 以确保只有具有授权的业务理由并满足资格要求的用户才有权访问系统。
- Office 365、其访问控制和支持服务 (包括 Azure Active Directory 和我们的物理数据中心) 定期通过独立第三方进行审核, 以实现[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [iso/iec 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)和其他[标准](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。
- Office 365 工程师需要进行每年一次安全培训, 以查看提升的访问最佳实践和风险, 并确认 Microsoft 的安全和隐私策略, 以继续维护其对服务的权利。

当检测到可疑活动时, 将触发自动警报, 例如短时间内多个失败的登录。 Office 365 安全响应团队使用机器学习和大型数据分析来查看和分析异常访问模式的活动并主动响应异常和违法活动。 Microsoft 还采用了一组专门的渗透测试人员, 并参与定期的红色团队和蓝色的团队练习, 以查找服务中的安全性和访问控制问题。 客户还可以通过使用审核报告和 Office 365 提供的管理活动 API 来验证访问控制系统的有效性。 

有关详细信息, 请参阅 office [365 管理活动 API 参考](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)和[office 365 中的审核与报告](office-365-auditing-and-reporting-overview.md)。
