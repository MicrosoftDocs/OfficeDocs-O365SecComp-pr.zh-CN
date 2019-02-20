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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: '摘要: Office 365 中可用的各种监视和审核访问控件的摘要。'
ms.openlocfilehash: 7a7023f61a72bd1368bb25754b33e40581a403b9
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090904"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a><span data-ttu-id="4ebb8-103">监视和审核 Office 365 中的访问控件</span><span class="sxs-lookup"><span data-stu-id="4ebb8-103">Monitoring and Auditing Access Controls in Office 365</span></span>

<span data-ttu-id="4ebb8-p101">Microsoft 对所有委派执行全面的监视和审核, 并对 Office 365 中的所有操作执行所有权限的使用。Office 365 访问控制是基于最小特权原则生成的自动化过程, 并包含数据访问控制和审核:</span><span class="sxs-lookup"><span data-stu-id="4ebb8-p101">Microsoft performs extensive monitoring and auditing of all delegation, all use of privileges, and all operations that occur within Office 365. Office 365 access control is an automated process built on the principle of least privilege and to incorporate data access controls and audits:</span></span>
- <span data-ttu-id="4ebb8-106">所有允许的访问都可与唯一用户进行跟踪, 管理员负责处理客户内容。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-106">All permitted access is traceable to a unique user, making administrators accountable for their handling of customer content.</span></span>
- <span data-ttu-id="4ebb8-107">捕获访问控制请求、审批和管理操作日志, 以分析安全见解和恶意事件。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-107">Access control requests, approvals, and administrative operations logs are captured for analysis of security insights and malicious events.</span></span>
- <span data-ttu-id="4ebb8-108">根据安全组成员身份, 在接近实时的情况中查看访问级别, 以确保只有具有授权的业务理由并满足资格要求的用户才有权访问系统。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-108">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="4ebb8-109">Office 365、其访问控制和支持服务 (包括 Azure Active Directory 和我们的物理数据中心) 定期通过独立第三方进行审核, 以实现[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [iso/iec 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、[FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)和其他[标准](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-109">Office 365, its access controls, and supporting services, including Azure Active Directory and our physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="4ebb8-110">Office 365 工程师需要进行每年一次安全培训, 以查看提升的访问最佳实践和风险, 并确认 Microsoft 的安全和隐私策略, 以继续维护其对服务的权利。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-110">Office 365 engineers are required to take yearly security training reviewing elevated access best practices and risks and acknowledge Microsoft's security and privacy policies to continue maintaining their entitlements to the service.</span></span>

<span data-ttu-id="4ebb8-p102">当检测到可疑活动时, 将触发自动警报, 例如短时间内多个失败的登录。Office 365 安全响应团队使用机器学习和大型数据分析来查看和分析异常访问模式的活动并主动响应异常和违法活动。Microsoft 还采用了一组专门的渗透测试人员, 并参与定期的红色团队和蓝色的团队练习, 以查找服务中的安全性和访问控制问题。客户还可以通过使用审核报告和 Office 365 提供的管理活动 API 来验证访问控制系统的有效性。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-p102">Automated alerts are triggered when suspicious activity is detected, such as multiple failed logins within a short period. The Office 365 Security Response team uses machine learning and big data analysis to review and analyze activity for irregular access patterns and to proactively respond to anomalous and illicit activities. Microsoft also employs a dedicated team of penetration testers and engages in periodic red team and blue team exercises to find security and access control issues in the service. Customers may also verify the effectiveness of access control systems by using audit reports and the management activity API provided by Office 365.</span></span> 

<span data-ttu-id="4ebb8-115">有关详细信息, 请参阅 office [365 管理活动 API 参考](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)和[office 365 中的审核与报告](office-365-auditing-and-reporting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-115">For more information, see [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).</span></span>
