---
title: 为 Microsoft 365 安全性和合规性做好准备
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: 为全新的 Microsoft 365 安全中心和合规性中心做好准备
ms.openlocfilehash: 6eb30c8439424a60b5cf02d55d771e11cf24ad10
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214962"
---
# <a name="get-ready-for-the-new-microsoft-365-security-center-and-microsoft-365-compliance-center"></a>为新的 Microsoft 365 安全中心和 Microsoft 365 合规中心做好准备

**我们很高兴宣布推出全新的[Microsoft 365 安全中心](#microsoft-365-security-center)和[Microsoft 365 合规性中心](#microsoft-365-compliance-center), 从1月2019结束到3月3日开始推出**。阅读本文, 了解所需内容、[预期](#what-to-expect)的内容以及所需的[许可证和权限](#required-licenses-and-permissions)的概述。

## <a name="microsoft-365-security-center"></a>Microsoft 365 安全中心

新的 Microsoft 365 安全中心包含一个仪表板, 可帮助您管理各个标识、数据、设备、应用程序和基础结构中的安全性, 并对其进行监视。此外, 你还可以轻松访问全新的 Microsoft 安全分数、新的设备威胁报告、新的标识威胁报告以及你的云应用安全报告。 

![新的 Microsoft 365 安全中心](media/m365-security-center.png)

当您首次使用 Microsoft 365 安全中心时, 您将看到屏幕顶部的信息, 以帮助您入门。你还将了解如何轻松导航到你最感兴趣的安全功能。

为你的租户启用 Microsoft 365 安全中心后, 你将能够在[https://security.microsoft.com](https://security.microsoft.com)中访问它。 

> [!NOTE]
> 必须为你分配有效的 Azure Active Directory 角色, 才能访问 Microsoft 365 安全中心。若要了解详细信息, 请参阅 "[必需的许可证和权限](#required-licenses-and-permissions)" 部分 (本文中的)。

## <a name="microsoft-365-compliance-center"></a>Microsoft 365 合规性中心

您的新 microsoft 365 合规性中心提供了 microsoft 合规性管理器的可见性, 以反映您的总体合规性情况并为您提供建议的操作, 可帮助您配置设置以满足复杂合规性义务。您将能够轻松访问灵敏度和保留标签和策略、数据丢失防护 (DLP)、数据管理、电子数据展示、数据主体请求 (dsr)、案例管理和云应用安全性。此外, 您还可以获得可操作的见解并利用智能自动化功能, 以降低您的合规性风险并保护您的数码房地产。 

![Microsoft 365 合规性中心](media/m365-compliance-center.png)

当您首次使用 Microsoft 365 合规性中心时, 您将看到屏幕顶部的信息, 以帮助您入门。你将了解如何轻松导航到你最关注浏览的合规性功能。

为你的租户启用 Microsoft 365 合规中心后, 你将在[https://compliance.microsoft.com](https://compliance.microsoft.com)中访问它。  

> [!NOTE]
> 必须为你分配有效的 Azure Active Directory 角色, 才能访问 Microsoft 365 合规性中心。若要了解详细信息, 请参阅 "[必需的许可证和权限](#required-licenses-and-permissions)" 部分 (本文中的)。

## <a name="what-to-expect"></a>预期内容

### <a name="coming-soon"></a>即将推出！

新的 microsoft 365 安全中心和新的 microsoft 365 合规性中心从1月晚开始推出, 到3月2019。在此时间范围内, 您应该有权访问新的 Microsoft 365 安全中心和 Microsoft 365 合规性中心。

### <a name="easy-access"></a>轻松访问!

通过改进的导航、集成的解决方案和简化的体验, 你将能够查看和访问你最感兴趣的信息, 并利用 Microsoft 365 中功能强大的安全和合规性解决方案。

### <a name="smooth-transition"></a>平滑转换!

您可以预见到新中心的平滑过渡。在完全推出此更改后, 我们计划淘汰以前的 Microsoft 365 Security & 合规性中心 ([https://protection.microsoft.com](https://protection.microsoft.com))。管理员体验将发生更改, 但这不会影响你当前的安全和合规性配置。

在推出此更新之后, 如果您的组织拥有 Microsoft 365 企业版 E3 或 E5, 则您的安全和合规性管理员可以执行以下操作:

- 直接导航到[https://security.microsoft.com](https://security.microsoft.com)和[https://compliance.microsoft.com](https://compliance.microsoft.com); <br>或  
- 转到 microsoft 365 管理中心, 然后导航到新的 Microsoft 365 安全中心和 Microsoft 365 合规性中心 (链接位于左侧导航窗格中的 "管理中心" 下)。

> [!TIP]
> 如果使用的是 office 365 Security & 合规中心 ([https://protection.office.com](http://protection.office.com)), 您仍可以在现有的 office 365 security & 合规性中心中配置和管理 Office 365 设置。在现有的 Office 365 security & 合规中心以及新的 Microsoft 365 安全中心和 Microsoft 365 合规性中心中, 将保留配置。  

## <a name="required-licenses-and-permissions"></a>必需的许可证和权限

若要获取新的 Microsoft 365 安全中心和 microsoft 365 合规性中心, 您的组织必须订阅 Microsoft 365 E3 或 e5 或批量许可等效项 (由 Office 365 企业版 E3 或 E5 组成, 企业移动性 + 安全性)E3 或 E5 以及 Windows 10 企业版 E3/e5)。

必须在 Azure Active Directory 中向用户分配全局管理员、合规性管理员、安全管理员或安全阅读者角色, 才能访问新的 Microsoft 365 安全中心或 Microsoft 365 合规性中心。

- 全局管理员可以同时访问安全中心和合规性中心

- 合规性管理员可以访问合规性中心

- 安全管理员或安全读者可以访问安全中心

> [!NOTE]
> 还有其他角色 (包括安全操作员和合规性数据管理员) 即将推出。

下表汇总了可以跨 Azure、Office 365 和 Windows 访问各个门户的成员:

|Portal  |全局<br/>管理员  |安全性 <br/>管理员<br>或<br>安全性<br>读者 |合规性<br/>管理员  |
|---------|---------|---------|---------|
|[Office 365 安全与合规中心](https://protection.office.com) |是 |支持  |可访问 |
|[Microsoft 365 安全中心](https://security.microsoft.com) |是  | 支持  | 否        |
|[Microsoft 365 合规性中心](https://compliance.microsoft.com) | 可访问 | 否 | 可访问 |
|[合规性管理器](https://aka.ms/compliancemanager) |是 | 支持 |可访问  |
|[Azure Information Protection](https://docs.microsoft.com/azure/information-protection)（Azure 信息保护） |是 |支持 |否 |
|[Azure 安全中心](https://docs.microsoft.com/azure/security-center/)  |是 |支持 |否 |
|[Azure 高级威胁防护](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)  |是 |支持 |否 |
|[Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection?ocid=tia-260153000#windows-defender-atp)和[终结点检测和响应](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)     |是 |支持 |否 |
|[标识保护](https://docs.microsoft.com/azure/active-directory/identity-protection)     |是 |支持 |否 |
|[特权身份管理](https://docs.microsoft.com/azure/active-directory/privileged-identity-management)     |是 |支持 |否 |
|[Intune](https://docs.microsoft.com/intune)     |是 |支持 |可访问 |
|[云应用安全](https://docs.microsoft.com/cloud-app-security/)     |是 |支持 |可访问 |
|[安全分数](https://docs.microsoft.com/office365/securitycompliance/office-365-secure-score)     |是 |支持 |否 |
|[Exchange](https://docs.microsoft.com/exchange/)     |是 |可访问 |可访问 |

## <a name="additional-resources"></a>其他资源

[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)

