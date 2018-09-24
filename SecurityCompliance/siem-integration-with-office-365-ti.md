---
title: 与 Office 365 威胁智能和高级威胁保护 SIEM 集成
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
description: 将您的组织 SIEM 服务器与 Office 365 威胁智能解决方案和使用 Office 365 活动管理 API 的高级威胁保护集成。
ms.openlocfilehash: 057d8ac101b96f37846ac751645934279d45dc88
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972254"
---
# <a name="siem-integration-with-office-365-threat-intelligence-and-advanced-threat-protection"></a>与 Office 365 威胁智能和高级威胁保护 SIEM 集成

如果您的组织正在使用安全事件和事件管理 (SIEM) 服务器，您可以与 SIEM 服务器集成 Office 365 威胁智能和高级威胁保护。SIEM 集成，可以查看信息，如通过 Office 365 高级保护和威胁智能 SIEM server 报表中检测到恶意软件。若要设置 SIEM 集成，您可以使用[Office 365 活动管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活动管理 API 检索贵组织的 Office 365 和 Azure Active Directory 活动日志用户、 管理、 系统和策略操作和事件的信息。[Office 365 高级威胁保护和威胁智能架构](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-intelligence-schema)适用于威胁智能和/或高级威胁保护，因此如果您的组织具有高级威胁保护但不是威胁智能 （反之亦然），您可以仍将该相同的 API 用于您 SIEM 服务器集成。 

SIEM 服务器或其他类似系统应轮询访问检测事件**audit.general**工作负荷。若要了解更多信息，请参见[开始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 

> [!IMPORTANT]
> 您必须是 Office 365 全局管理员或具有安全管理员角色分配中安全性和合规性中心设置与 Office 365 威胁智能和高级威胁保护 SIEM 集成。<br/>必须为您的 Office 365 环境开启审核日志记录。要获取与此帮助，请参阅[打开 Office 365 审核日志搜索打开或关闭](turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相关主题

[Office 365 威胁智能](office-365-ti.md)

[Office 365 高级威胁防护](office-365-atp.md)

[智能报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)
  
[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)
  

