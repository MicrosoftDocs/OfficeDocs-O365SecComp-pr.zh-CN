---
title: What's new in Office 365 云应用程序安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 12/26/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: 请参阅 what's new in Office 365 云应用程序安全性
ms.openlocfilehash: 9f0c93d0de6ae8be72456c874ef8f5e3d42264e2
ms.sourcegitcommit: 25f72d20e76463c2f0a075dfc0116f00c934bd77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/27/2018
ms.locfileid: "27447060"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a>What's new in Office 365 云应用程序安全性

**摘要**阅读这篇文章，获取 Office 365 云应用程序安全性 （之前被称为 Office 365 高级安全管理），这由[Microsoft 云应用程序安全性](https://aka.ms/whatiscas)中的更新和新功能的简单概述。
  
> [!TIP]
> 添加或改进功能时，将经常，更新这篇文章。发布约两周，Microsoft 云应用程序安全性更新后的 office 365 云应用程序安全性更新并不是所有 Microsoft 云应用程序安全性更新都应用于 Office 365 云应用程序安全性。此外，一周或更多 Office 365 云应用程序安全性环境中显示其发布日期后，可能需要的新功能。

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 云应用程序安全性版本 138

*年 12 月 23 2018*

**以下[Microsoft 云应用程序安全性释放 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **自动日志上载使用 Docker Windows 上**云应用程序安全性现在支持 Windows 10 自动日志上载 ([秋季创建者更新](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)和更高版本) 和 Windows Server ([版本 1709年](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709)和更高版本) Windows 上使用 Docker。请参阅[本文](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows)以了解详细信息并配置 Docker。  

- **Microsoft 流集成**与[Microsoft 流](https://docs.microsoft.com/flow/getting-started)提供自定义警报自动化和业务流程 playbooks 现在集成云应用程序安全性。请参阅[本文](https://docs.microsoft.com/cloud-app-security/flow-integration)以了解详细信息并配置 Microsoft 流集成。 


## <a name="office-365-cloud-app-security-release-137"></a>Office 365 云应用程序安全性版本 137

*年 12 月 8 2018*

**以下[Microsoft 云应用程序安全性释放 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **添加了支持的动态**云应用程序安全性现在包括支持的 Microsoft Dynamics 活动的受支持的 Office 365 审核日志。 

- **达 – 新术语 ！** 为清楚起见，已更改的应用程序权限功能名称 – 现在称为 OAuth 应用程序。 


## <a name="office-365-cloud-app-security-release-136"></a>Office 365 云应用程序安全性版本 136

*年 11 月 25 2018*

**以下[Microsoft 云应用程序安全性释放 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **云发现更新**自定义日志分析器的增强支持其他和更复杂的 web 流量日志格式。一部分这些增强功能用户现在可以输入 headerless CSV 日志文件的自定义标头，键值文件使用特殊的分隔符，处理 Syslog 文件格式和更多内容。

- **新异常检测策略： 可疑收件箱操作规则**删除或移动邮件或文件夹的可疑规则设置在用户的收件箱上时，此策略配置文件您的环境和触发器通知。这可能表示受到威胁的用户帐户的邮件已被有意被隐藏，和邮箱使用分发垃圾邮件或您的组织中的恶意软件。

- **支持在应用程序的权限策略的组**云应用程序安全性现在为您提供了更详细地，定义应用程序的权限策略的能力根据授权应用程序的用户组成员身份。例如，管理员可以决定将撤消不常用的应用程序，如果授权权限的用户是 administrators 组的成员时，才要求高权限策略设置。


## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Office 365 云应用程序安全性释放 133、 134 和 135

*年 10 月-年 11 月发布 2018*

**以下[Microsoft 云应用程序安全性释放 133、 134 和 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- 逐步推出**新异常检测策略**：
    
    - 新的**未批准的应用程序的数据 exfiltration**策略自动启用的用户或 IP 地址使用的不认可执行类似尝试 exfiltrate 信息从您的组织的活动应用程序时发出警报。
    
    - 新的**多个删除 VM 活动**策略配置文件环境，并在用户在单个会话中相对于在您的组织中的基线删除多个 Vm 时触发通知。

- **云发现 i 筛选器的支持**现在的云应用程序安全云发现功能已增强 i 筛选器系统日志分析程序的支持。


## <a name="office-365-cloud-app-security-release-131"></a>Office 365 云应用程序安全性版本 131

*年 9 月 16 2018*

**以下[Microsoft 云应用程序安全性释放 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **自动撤消 risky OAuth 应用程序的权限**现在，您可以控制的 OAuth 应用程序用户有权访问，通过吊销 OAuth 上的应用程序 Office 的应用程序权限。时创建的应用程序权限策略，您现在可以设置策略取消应用程序的权限。

- **支持云发现其他内置分析**云发现现在支持 Forcepoint Web 安全云日志格式。

  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 云应用程序安全性版本 130

*年 9 月 5 2018*

**以下[Microsoft 云应用程序安全性释放 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **新的菜单栏**若要跨 Microsoft 365 产品提供更一致的管理体验并使您能够更轻松地透视 Microsoft 安全解决方案之间，云应用程序安全性门户菜单栏已移动到屏幕的左侧。此一致的导航体验时将其从一个 Microsoft 安全门户移到另一个定向自己的帮助。<br/>![Office 云应用程序安全性的菜单栏](media/OCAS-MenuBar.png)<br/>

- **影响 OAuth 应用程序分数**现在，您可以发送的云应用程序安全性团队反馈，以便让我们知道是否存在组织中的恶意视图可能会发现 OAuth 应用程序。这一新功能，可以是我们安全社区的和增强 OAuth 应用程序风险分数和分析。有关详细信息，请参阅[管理 OAuth 应用程序](manage-app-permissions-in-ocas.md)。

- **新的云发现分析程序**云发现分析程序现在支持 iboss 安全云网关和 Sophos XG。


## <a name="office-365-cloud-app-security-release-128"></a>Office 365 云应用程序安全性版本 128

*年 8 月 5 2018* 
  
**以下[Microsoft 云应用程序安全性释放 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **跨多个应用程序的 OAuth 应用程序**对于 OAuth 应用程序，您现在可以禁止或审批的单个操作中的多个应用程序。例如，您可以查看的已在组织中的用户授予权限，选择您要禁止，所有应用程序，然后单击要取消授予所有许可禁止应用程序的所有应用程序，并将不再允许用户授予对这些应用程序的权限。若要了解详细信息，请参阅[使用 Office 365 云应用程序安全性的管理 OAuth 应用程序](manage-app-permissions-in-ocas.md)。 
    
- **新建建议的查询： GDPR 准备云应用程序**没有新的建议的查询，以使您能够识别的 GDPR 准备发现应用程序。您可能已经知道，GDPR 最近已成为对于安全管理员最高的优先级。此查询可帮助您轻松地识别的 GDPR 就绪，应用程序并通过来评估不的应用程序的风险缓解威胁。用于新查询，**云发现**仪表板， **Discovered 应用程序**选项卡中，选择**查询** > **GDPR 准备云应用程序**。<br/>![GDPR 准备云应用程序查询](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 云应用程序安全性版本 126

*年 7 月 7 2018* 
  
**以下[Microsoft 云应用程序安全性释放 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **自动修复可疑活动**您现在可以由异常检测策略触发的可疑会话设置自动修复操作。此增强功能，您可以立即违反发生时通知和自动应用调控操作，如挂起用户。有关详细信息，请参阅[Office 365 云应用程序安全性的异常检测 policies](anomaly-detection-policies-in-ocas.md)。
    
- **自动检测 risky OAuth 应用程序**除了 OAuth 连接到您的环境的应用程序的现有调查，Office 365 云应用程序安全性现在允许您设置自动的通知，让您知道 OAuth 应用程序时满足特定条件。例如，您可以自动通知应用程序时，需要高权限级别，并且已授权 50 个以上的用户。有关详细信息，请参阅[使用 Office 365 云应用程序安全性的管理 OAuth 应用程序](manage-app-permissions-in-ocas.md)。
    
- **管理安全服务提供程序管理 (MSSP) 支持**Office 365 云应用程序安全性现在为 MSSPs，提供更好的管理体验，并允许您将外部合作伙伴配置为与任何当前提供 Office 365 云应用程序安全性的角色的管理员。此外，对多个租户具有访问权限的管理员可以立即轻松透视之间租户中。 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 云应用程序安全性版本 124

*年 6 月 10 2018* 
  
**以下[Microsoft 云应用程序安全性释放 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **范围内部署**企业组织粒度可以确定哪些用户可以监视和保护根据组成员身份。此功能，可以选择其活动将不会显示任何受保护的应用程序的用户。范围监视是对于合规性和许可特别有用。某些管理法规导致用您避免监控从本地法规由于某些国家/地区的用户。然后可以监视较少的用户，以保持在您的 Office 365 云应用程序安全性许可证的限制内。 
    
- **新的电子邮件服务器**Office 365 云应用程序安全性的电子邮件服务器已更改，并使用不同的 IP 地址范围。若要确保您可以获取通知，到反垃圾邮件白名单中添加新的 IP 地址。对于自定义其通知的组织，云应用程序安全性使此为您使用 MailChimp，第三方电子邮件服务。列表中邮件服务器 IP 地址和启用与 MailChimp 一起工作的说明，请参阅[网络要求 （Microsoft 云应用程序安全性）](https://docs.microsoft.com/cloud-app-security/network-requirements)和[邮件设置 （Microsoft 云应用程序安全性）](https://docs.microsoft.com/cloud-app-security/mail-settings)。
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 云应用程序安全性版本 121

*年 5 月 6 2018* 
  
**以下[Microsoft 云应用程序安全性释放 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **异常检测策略改进**。Office 365 云应用程序安全异常检测策略得到了改进，以包括两种新类型的逐步推出的威胁检测： 
    
  - **勒索软件活动。** 使用异常检测为您提供更全面针对复杂勒索软件攻击的扩展勒索软件检测功能。 
    
  - **终止用户活动。** 终止用户活动使您可以监视人员可能已取消设置从企业应用程序，但用户可能仍终止用户的帐户有权访问特定的企业资源。 
    
    若要查看您的[异常检测策略](anomaly-detection-policies-in-ocas.md)，在 Office 365 云应用程序安全性门户中，选择**控件** \> **策略**。
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 云应用程序安全性版本 120

*年 4 月 22 2018* 
  
**以下[Microsoft 云应用程序安全性释放 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **为用户活动的内部应用程序**。有关 Office 365 和 Azure Active Directory (Azure AD)，我们现在逐步推出检测内部应用程序作为 Office 365 和 Azure AD 的应用程序 （内部和外部） 执行的用户帐户活动的能力。这使您创建策略，提醒您如果应用程序执行意外和未经授权的活动。 
    
- **OAuth 的应用程序列表中的多个字段导出**。将 OAuth 应用程序列表导出到 csv，如 publisher，其他字段时权限级别和社区的使用情况都包含帮助与合规性和调查过程。 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 云应用程序安全性版本 119

*年 4 月 1 2018* 
  
**以下[Microsoft 云应用程序安全性释放 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **云发现的改进**。云发现提供有关最多用户和 IP 地址的详细信息，使其更轻松地查看使用率有关 Office 365 的详细信息和其他应用程序。若要了解详细信息，请参阅[Office 365 云应用程序安全性的查看应用程序发现结果](review-app-discovery-findings-in-ocas.md)。
    
    ![已更新，云发现仪表板](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 云应用程序安全性版本 118

*年 3 月 18 2018* 
  
**以下[Microsoft 云应用程序安全性释放 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Barracuda 支持**。云发现现在支持 Barracuda F 系列防火墙和 Barracuda F 系列防火墙 web 日志流。 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 云应用程序安全性版本 117

*年 3 月 6 2018* 
  
**以下[Microsoft 云应用程序安全性释放 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i 筛选器支持**。云发现现在支持 i 筛选器。 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 云应用程序安全性版本 116

*年 2 月 18 2018* 
  
**以下[Microsoft 云应用程序安全性释放 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **异常检测策略增强功能**。异常检测策略中包括意思差旅，从可疑的 IP 地址的活动的新基于场景的检测已得到增强 Office 365 云应用程序安全性和多次登录尝试失败。自动启用的新策略，在云环境提供的框威胁检测。此外，新策略公开来自 Office 365 云应用程序安全性检测引擎，这有助于加快调查过程，并且包含持续威胁的其他数据。若要了解详细信息，请参阅 Microsoft 云应用程序安全性文章，[获取即时行为分析和异常检测](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)。
    
- **日志分析器支持检查点格式**。云发现日志分析程序现在支持以下两种其他检查点格式： XML，and KPC。 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 云应用程序安全性版本 114

*年 1 月 21 2018* 
  
**以下[Microsoft 云应用程序安全性释放 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **服务状态**。您现在可以通过转到**帮助**来检查当前的 Office 365 云应用程序安全性服务状态\>**系统状态**。 
    
    ![单击帮助\>系统状态，查看系统运行状况状态](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **活动日志的自定义查询**。从开始 114 版本中，创建和保存活动日志中的自定义查询的能力推出逐步。自定义查询使您能够创建可重用的深入探究调查的筛选器模板。此外，建议的查询已进行了添加以便提供的框调查模板筛选您的活动和发现应用程序。建议的查询包括自定义筛选器来标识与弱加密和安全风险的风险，例如模拟活动管理员活动、 risky 不符合标准的云存储应用程序、 企业应用程序。作为起点使用建议的查询和对其进行修改，根据需要然后将其保存为新查询。 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 云应用程序安全性版本 113

*年 1 月 8 2018* 
  
**以下[Microsoft 云应用程序安全性释放 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **日志分析器支持泛型格式**。云发现日志分析程序现在支持以下泛型格式： LEEF、 CEF 和 W3C。 

## <a name="releases-prior-to-113"></a>113 之前的版本

[请参阅 2017 updates for Office 365 云应用程序安全性](new-in-office-365-cas-2017.md)
    
