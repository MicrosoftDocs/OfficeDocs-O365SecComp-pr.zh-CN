---
title: SIEM 与 Office 365 高级威胁防护的集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: 将组织的 SIEM 服务器与 office 365 高级威胁防护以及 office 365 活动管理 API 中相关的威胁事件集成。
ms.openlocfilehash: fa9dcda0556684b748068cbe5ee848ba443d7667
ms.sourcegitcommit: f25a667e4c7d11c43c87604d576f1e6d6155b14f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30536172"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>SIEM 与 Office 365 高级威胁防护的集成

如果您的组织使用的是安全事件和事件管理 (SIEM) 服务器, 则可以将 Office 365 高级威胁防护与您的 SIEM 服务器集成。 SIEM 集成使您能够查看 SIEM 服务器报告中的 Office 365 高级保护检测到的恶意软件或网络钓鱼信息。 若要设置 SIEM 集成, 请使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活动管理 API 检索组织的 Office 365 和 Azure Active Directory 活动日志中的用户、管理员、系统和策略操作以及事件的相关信息。 [Office 365 高级威胁防护架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)使用高级威胁防护功能, 因此, 如果您的组织具有 Office 365 高级威胁防护计划1或计划2或 Office 365 E5, 您仍可以对您的 SIEM 服务器集成使用相同的 API。 

SIEM 服务器或其他类似系统应轮询**审核。常规**工作负荷以访问检测事件。 若要了解详细信息, 请参阅[Office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 此外, **AuditLogRecordType**的以下值与 Office 365 ATP 事件相关:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>枚举：AuditLogRecordType - 类型：Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|值|成员名称|说明|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Exchange Online Protection 和 Office 365 高级威胁防护中的网络钓鱼和恶意软件事件。|
|41|ThreatIntelligenceUrl|ATP 安全链接从 Office 365 高级威胁防护的阻止时间和阻止覆盖事件。|
|47|ThreatIntelligenceAtpContent|Office 365 高级威胁防护中的 SharePoint Online、OneDrive for business 和 Microsoft 团队中的文件的网络钓鱼和恶意软件事件。|

> [!IMPORTANT]
> 您必须是 Office 365 全局管理员, 或者已为安全 & 合规中心分配安全管理员角色, 以便设置 SIEM 与 Office 365 高级威胁防护的集成。<br/>必须为你的 Office 365 环境启用审核日志记录。 若要获取有关此功能的帮助, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相关主题

[Office 365 威胁调查和响应](office-365-ti.md)

[Office 365 高级威胁防护](office-365-atp.md)

[Office 365 安全&amp;合规中心中的智能报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
