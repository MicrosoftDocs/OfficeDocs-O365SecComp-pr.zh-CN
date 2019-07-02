---
title: SIEM server 与 Microsoft 365 的集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: '摘要: 阅读本文, 了解 SIEM server 与 Microsoft 365 集成的概述。'
ms.openlocfilehash: 9138cbc395b90f50fa60bf545066c17cf26d7edf
ms.sourcegitcommit: f2798d46acfbd56314e809cd3fe0350be807e420
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2019
ms.locfileid: "35014761"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server 与 Microsoft 365 服务和应用程序的集成

## <a name="overview"></a>概述

如果您的组织使用的是安全信息和事件管理 (SIEM) 服务器, 或者您打算马上获取 SIEM 服务器, 那么您可能想知道如何与您的 Microsoft 365 (包括 Office 365 E5) 集成。 您是否需要 SIEM 服务器取决于多个因素, 例如组织的安全要求。 Microsoft 365 提供了多种安全功能;但是, 如果您的组织在本地和云中有内容和应用程序 (如混合云部署的情况), 则可以考虑添加 SIEM 服务器以实现额外保护。 或者, 如果您的组织具有特别严格的安全要求, 必须满足这些要求, 则可以考虑将 SIEM 服务器添加到您的环境中。

## <a name="siem-server-integration-microsoft-365"></a>SIEM server 集成 Microsoft 365

SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。 下表列出了几个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入, 以及在哪里可以了解有关 SIEM server 集成的更多信息。 

| Microsoft 365 服务或应用程序 | SIEM 服务器输入 | 要了解详细信息的资源 |
| --- | --- | --- |
| [Office 365 高级威胁防护](office-365-atp.md) <br/>或<br/>[Office 365 威胁智能](office-365-ti.md) | 审核日志 | [SIEM 与 Office 365 高级威胁防护的集成](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 日志集成 | [SIEM 与 Microsoft Cloud App Security 的集成](https://docs.microsoft.com/cloud-app-security/siem) |
| [Microsoft 威胁防护](https://docs.microsoft.com/windows/security/threat-protection/) | 日志集成 | [将警报拉入 SIEM 工具](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)(威胁防护和威胁检测) | 警报 | [Azure 安全数据导出到 SIEM 配置-预览](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Azure 高级威胁分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure 监视器 | [博客使用 Azure Monitor 与 SIEM 工具集成](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |日志集成 |[将 Microsoft Graph 安全性 API 警报与 SIEM 集成](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>必须打开审核日志记录

在配置 SIEM server 集成之前, 请确保审核日志记录已打开。 

- 对于 SharePoint Online、OneDrive for business 和 Azure Active Directory,[审核日志记录在安全 & 合规性中心中打开](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。

- 对于 Exchange Online,[审核日志记录是使用 Windows PowerShell 打开](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)的。
 
## <a name="see-also"></a>另请参阅

[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[云应用测试实验室指南 (TLG) ](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


