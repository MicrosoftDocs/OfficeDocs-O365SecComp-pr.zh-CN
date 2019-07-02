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
ms.openlocfilehash: 39ee2b535c89419e161558cba2122e325228ffb1
ms.sourcegitcommit: 7b5e4a7a51f3cdd741deb77a2d60a18e2316618d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33520712"
---
# <a name="monitoring-and-auditing-access-controls-in-office-365"></a><span data-ttu-id="c32ab-103">监视和审核 Office 365 中的访问控件</span><span class="sxs-lookup"><span data-stu-id="c32ab-103">Monitoring and Auditing Access Controls in Office 365</span></span>

<span data-ttu-id="c32ab-104">Microsoft 对 Office 365 中发生的所有委派、特权和操作执行全面的监视和审核。</span><span class="sxs-lookup"><span data-stu-id="c32ab-104">Microsoft performs extensive monitoring and auditing of all delegation, privileges, and operations that occur within Office 365.</span></span> <span data-ttu-id="c32ab-105">Office 365 访问控制是基于最小特权原则构建的自动化过程, 并包含数据访问控制和审核:</span><span class="sxs-lookup"><span data-stu-id="c32ab-105">Office 365 access control is an automated process built on the principle of least privilege and incorporate data access controls and audits:</span></span>

- <span data-ttu-id="c32ab-106">所有允许的访问都可供唯一用户跟踪。</span><span class="sxs-lookup"><span data-stu-id="c32ab-106">All permitted access is traceable to a unique user.</span></span> <span data-ttu-id="c32ab-107">管理员负责处理客户内容。</span><span class="sxs-lookup"><span data-stu-id="c32ab-107">Administrators are accountable for their handling of customer content.</span></span>
- <span data-ttu-id="c32ab-108">捕获访问控制请求、审批和管理操作日志, 以分析安全和恶意事件。</span><span class="sxs-lookup"><span data-stu-id="c32ab-108">Access control requests, approvals, and administrative operations logs are captured for analysis of security and malicious events.</span></span>
- <span data-ttu-id="c32ab-109">根据安全组成员身份, 在接近实时的情况中查看访问级别, 以确保只有具有授权的业务理由并满足资格要求的用户才有权访问系统。</span><span class="sxs-lookup"><span data-stu-id="c32ab-109">Access levels are reviewed in near real-time based on security group membership to ensure that only users who have authorized business justifications and meet the eligibility requirements have access to the systems.</span></span>
- <span data-ttu-id="c32ab-110">Office 365、其访问控制和支持服务 (包括 Azure Active Directory 和物理数据中心) 定期通过独立第三方进行审核, 以实现[ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001)、 [iso/iec 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC)、 [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP)和其他[标准](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="c32ab-110">Office 365, its access controls, and supporting services, including Azure Active Directory and physical datacenters, are regularly audited by independent third-parties for compliance with [ISO/IEC 27001](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/en-us/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/en-us/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP), and other [standards](https://www.microsoft.com/en-us/TrustCenter/Compliance?service=Office#Icons).</span></span>
- <span data-ttu-id="c32ab-111">Office 365 工程师必须参加年度安全培训, 查看提升的访问最佳步骤, 并确认 Microsoft 的安全和隐私政策, 以维持对服务的权利。</span><span class="sxs-lookup"><span data-stu-id="c32ab-111">Office 365 engineers must take yearly security training, review elevated access best procedures, and acknowledge Microsoft's security and privacy policies to maintain entitlements to the service.</span></span>

<span data-ttu-id="c32ab-112">当检测到可疑活动 (如短时间内的多个失败的登录) 时, 自动通知会触发。</span><span class="sxs-lookup"><span data-stu-id="c32ab-112">Automated alerts trigger when suspicious activity is detected, such as multiple failed logins within a short period.</span></span> <span data-ttu-id="c32ab-113">Office 365 安全响应团队使用机器学习和大型数据分析来查看和分析活动、查找不规则的访问模式并主动响应异常和违法活动。</span><span class="sxs-lookup"><span data-stu-id="c32ab-113">The Office 365 Security Response team uses machine learning and big data analysis to review and analyze activity, look for irregular access patterns, and proactively respond to anomalous and illicit activities.</span></span> <span data-ttu-id="c32ab-114">Microsoft 还采用了一组专门的渗透测试人员, 并参与定期的红色团队和蓝色的团队练习, 以查找服务中的安全性和访问控制问题。</span><span class="sxs-lookup"><span data-stu-id="c32ab-114">Microsoft also employs a dedicated team of penetration testers and engages in periodic Red Team and Blue Team exercises to find security and access control issues in the service.</span></span> <span data-ttu-id="c32ab-115">客户可以通过使用由 Office 365 提供的审核报告和管理活动 API 来验证访问控制系统的有效性。</span><span class="sxs-lookup"><span data-stu-id="c32ab-115">Customers can verify the effectiveness of access control systems by using audit reports and the management activity API provided by Office 365.</span></span>

<span data-ttu-id="c32ab-116">有关详细信息, 请参阅 Office [365 管理活动 API 参考](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx)和[office 365 中的审核与报告](office-365-auditing-and-reporting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c32ab-116">For more information, see [Office 365 Management Activity API reference](https://msdn.microsoft.com/en-us/library/office/mt227394.aspx) and [Auditing and Reporting in Office 365](office-365-auditing-and-reporting-overview.md).</span></span>
