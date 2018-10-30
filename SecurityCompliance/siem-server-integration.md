---
title: 与 Microsoft 365 SIEM 服务器集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 10/29/2018
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- SIEM
description: 摘要： 阅读这篇文章，获取 SIEM server 与 Microsoft 365 的集成的概述。
ms.openlocfilehash: bd512ca6d75928712e3444581a78610a0869123d
ms.sourcegitcommit: 63ed467fc3e1ab1ab9ee122df97c64737169834e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2018
ms.locfileid: "25842675"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>SIEM server 与 Microsoft 365 服务和应用程序的集成

## <a name="overview"></a>概述

如果您的组织使用的安全信息和事件管理 (SIEM) 的服务器，或者如果您打算很快获取 SIEM 服务器，您可能想知道的将如何集成进行 Microsoft 365，包括 Office 365 企业版。是否需要 SIEM 服务器取决于多个因素，如贵组织的安全要求。Microsoft 365 提供了多种安全功能;但是，如果您的组织有内容和应用程序在本地和在云中 （如所混合云部署的大小写），则可以考虑添加额外保护 SIEM 服务器。或者，如果您的组织必须满足的特别严格的安全要求，则可以考虑将 SIEM 服务器添加到您的环境。

## <a name="siem-server-integration-microsoft-365"></a>SIEM 服务器集成 Microsoft 365

SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。下表列出了多个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入和位置单击以了解有关 SIEM 服务器集成。 

| Microsoft 365 服务或应用程序 | SIEM 服务器输入 | 若要了解更多的资源 |
| --- | --- | --- |
| [Office 365 高级威胁防护](office-365-atp.md) <br/>   或   <br/>[Office 365 威胁智能](office-365-ti.md) | 审核日志 | [与 Office 365 威胁智能和高级威胁保护 SIEM 集成](siem-integration-with-office-365-ti.md) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | 日志集成 | [与 Microsoft 云应用程序安全性的 SIEM 集成](https://docs.microsoft.com/cloud-app-security/siem) |
| [Office 365 云应用安全](office-365-cas-overview.md) | 日志集成 | [将 SIEM 服务器与 Office 365 云应用安全集成](integrate-your-siem-server-with-office-365-cas.md) |
| [Windows Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection/) | 日志集成 | [SIEM 工具拉通知](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection) |
| [Azure 安全中心](https://docs.microsoft.com/azure/security-center/security-center-intro)（威胁保护和威胁检测） | 警报 | [Azure 安全数据导出到 SIEM-管道配置-预览](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
| [Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) | 审核日志 | [集成 Azure Active Directory 审核日志](https://docs.microsoft.com/azure/security/security-azure-log-integration-ad) |
| [Azure 高级的威胁分析](https://docs.microsoft.com/azure/security/azure-threat-detection) | 日志集成 | [ATA SIEM 日志参考 （英文）](https://docs.microsoft.com/advanced-threat-analytics/cef-format-sa) |

## <a name="audit-logging-must-be-turned-on"></a>必须打开审核日志记录

请确保之前配置 SIEM 服务器集成审核日志记录已打开。 

- SharePoint online，OneDrive for Business 和 Azure Active Directory[中的安全性和合规性中心启用审核日志记录](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。

- 有关 Exchange Online，[使用 Windows PowerShell 开启审核日志记录](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)。
 
## <a name="see-also"></a>另请参阅

[云应用和混合解决方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[云采用测试实验室指南 (TLG)](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


