---
title: What's new in Office 365 云应用程序安全性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 11/28/2018
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: d674763c-a4c9-4604-8623-68c1836d27f3
description: 请参阅 what's new in Office 365 云应用程序安全性
ms.openlocfilehash: a3ca4504d80cbb39b51ecbcf3a5165bc5139e07c
ms.sourcegitcommit: bf628da123a89d9422e8cff02165b1e2d35dfe12
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26872010"
---
# <a name="what-is-new-in-office-365-cloud-app-security"></a>What's new in Office 365 云应用程序安全性

**摘要**阅读这篇文章，获取 Office 365 云应用程序安全性 （之前被称为 Office 365 高级安全管理），这由[Microsoft 云应用程序安全性](https://aka.ms/whatiscas)中的更新和新功能的简单概述。
  
添加或改进功能时，将经常，更新这篇文章。发布约两周，Microsoft 云应用程序安全性更新后的 office 365 云应用程序安全性更新并不是所有 Microsoft 云应用程序安全性更新都应用于 Office 365 云应用程序安全性。此外，一周或更多 Office 365 云应用程序安全性环境中显示其发布日期后，可能需要的新功能。

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

- **影响 OAuth 应用程序分数**现在，您可以发送的云应用程序安全性团队反馈，以便让我们知道是否存在组织中的恶意视图可能会发现 OAuth 应用程序。这一新功能，可以是我们安全社区的和增强 OAuth 应用程序风险分数和分析。有关详细信息，请参阅[管理应用程序权限](manage-app-permissions-in-ocas.md)。

- **新的云发现分析程序**云发现分析程序现在支持 iboss 安全云网关和 Sophos XG。


## <a name="office-365-cloud-app-security-release-128"></a>Office 365 云应用程序安全性版本 128

*年 8 月 5 2018* 
  
**以下[Microsoft 云应用程序安全性释放 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **跨多个应用程序的应用程序权限**对于已被授予应用程序权限的应用程序，您现在可以禁止或审批的单个操作中的多个应用程序。例如，您可以查看的已在组织中的用户授予权限，选择您要禁止，所有应用程序，然后单击要取消授予所有许可禁止应用程序的所有应用程序，并将不再允许用户授予对这些应用程序的权限。 
    
- **新建建议的查询： GDPR 准备**没有新的建议的查询，以使您能够识别的 GDPR 准备发现应用程序。GDPR 最近已成为对于安全管理员最高的优先级。此查询可帮助您轻松地识别的 GDPR 就绪，应用程序并通过来评估不的应用程序的风险缓解威胁。 
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 云应用程序安全性版本 126

*年 7 月 7 2018* 
  
**以下[Microsoft 云应用程序安全性释放 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **自动修复可疑活动**您现在可以由异常检测策略触发的可疑会话设置自动修复操作。此增强功能，您可以立即违反发生时通知和自动应用调控操作，如挂起用户。有关详细信息，请参阅[Office 365 云应用程序安全性的异常检测 policies](anomaly-detection-policies-in-ocas.md)。
    
- **自动检测 risky OAuth 应用程序**除了 OAuth 连接到您的环境的应用程序的现有调查，Office 365 云应用程序安全性现在允许您设置自动的通知，让您知道 OAuth 应用程序时满足特定条件。例如，您可以自动通知应用程序时，需要高权限级别，并且已授权 50 个以上的用户。有关详细信息，请参阅[管理使用 Office 365 云应用程序安全性的应用程序权限](manage-app-permissions-in-ocas.md)。
    
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
    
- **导出应用程序权限列表中的多个字段**。时将应用程序权限列表导出到 csv，如 publisher，其他字段的权限级别和社区的使用情况都包含帮助与合规性和调查过程。 
    
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
    
## <a name="office-365-cloud-app-security-release-112"></a>Office 365 云应用程序安全性版本 112

*发布 2017 年 12 月 24，* 
  
**以下[Microsoft 云应用程序安全性释放 112](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-112)**: 
  
- **相关洞察纸盒**。在活动日志中，您现在可以通过单击用户名或 IP 地址上访问相关洞察纸盒。 
    
    ![单击用户名称或 IP 地址，以查看相关洞察银活动日志中。](media/8e32b3fa-8c0c-4c5e-b248-fe7d7e1b516d.png)
  
- **若要查看单击多个活动的能力**。在相关洞察银，您可以单击时钟图标可查看选定活动的 48 小时内执行的所有活动。 
    
    ![在相关见解银，可以单击该时钟图标可查看选定活动的 48 小时内执行的活动](media/c6c96aa0-98e5-4205-8873-45f8d6fd0843.png)
  
- **Juniper SRX 日志分析器改进**。改进了对 Juniper SRX 云发现日志分析器。 
    
## <a name="office-365-cloud-app-security-release-111"></a>Office 365 云应用程序安全性版本 111

*发布 2017 年 12 月 10，* 
  
**以下[Microsoft 云应用程序安全性释放 111](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-111)**: 
  
- **时间筛选器的改进**。时间筛选器现在是易于使用。若要访问时间筛选，在视图中，如活动日志，策略、 通知，使用高级视图中，选择的筛选器列表中的**日期**。然后选择一个选项，如之前、 之后，或在之间要应用时间筛选器。 
    
    ![使用日期筛选器可查看之前、 之后或日期之间的信息。](media/9dbb2a10-f68f-413b-8b4e-88911152cb92.png)
  
## <a name="office-365-cloud-app-security-release-110"></a>Office 365 云应用程序安全性版本 110

*发布 2017 年 11 月 26，* 
  
**以下[Microsoft 云应用程序安全性释放 110](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-110)**: 
  
- **现已推出通常 SIEM 服务器集成**。连接到 Office 365 云应用程序安全性 SIEM 服务器。您现在可以发送通知和活动自动为您所选择的 SIEM 服务器通过配置 SIEM 代理。请参阅[SIEM 服务器与 Office 365 云应用程序安全性集成](integrate-your-siem-server-with-office-365-cas.md)。
    
- **更轻松地访问以帮助内容**。在右上角中使用新问号，现在可以访问中的 Office 365 云应用程序安全性门户页中的帮助内容。上下文相关，使您所需的信息、 基于一页上的每个链接。 
    
- **向我们发送反馈**。使用笑脸右上角中，您可以立即发送反馈从 Office 365 云应用程序安全性门户的每一页。这样，您可以报告 bug、 请求的新功能和直接与 Office 365 云应用程序安全性团队共享您的体验。 
    
## <a name="office-365-cloud-app-security-release-102"></a>Office 365 云应用程序安全性版本 102

*发布 2017 年 8 月 13，* 
  
**以下[Microsoft 云应用程序安全性释放 102](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-102)**: 
  
- **新用户调查操作**启用额外的向下钻取级别为用户调查。在调查页上，您可以将鼠标悬停在活动、 用户或帐户，并将其应用作为筛选器，并据此，您可以查看相关的活动或事件。 
    
## <a name="office-365-cloud-app-security-release-100"></a>Office 365 云应用程序安全性版本 100

*发布 2017 年 7 月 17，* 
  
**以下[Microsoft 云应用程序安全性版本 100](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-100)**: 
  
- **安全扩展**是可在其中集中管理所有安全扩展插件对 Office 365 云应用程序安全性，包括 API 令牌和 SIEM 代理的新仪表板。若要查看安全扩展仪表板，请按照下列步骤： 
    
1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。(您将转到安全&amp;合规性中心。) 
    
2. 转到**通知** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。
    
    ![安全中&amp;合规性中心中，选择警报\>管理高级通知\>转到高级安全管理](media/9792b121-9cd4-4faa-a6e0-81cfab4bf2f2.png)
  
4. 选择**设置** \> **安全扩展**。
    
    ![在 ASM 门户中，选择设置\>安全扩展](media/f03d47a1-91ff-41b9-9baf-b514cffe41a8.png)
  
- **改进了分析**。云发现日志分析机制中所做的改进。都可能会显著较低，发生内部错误。 
    
- **预期日志格式**。云发现日志的预期的日志格式现在提供 Syslog 格式和 FTP 格式的示例。 
    
## <a name="related-topics"></a>相关主题

[Office 365 云应用程序安全性帮助内容](office-365-cas-help.md)
  
[推出 Office 365 云应用安全后的利用率活动](utilization-activities-for-ocas.md)
  
[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)
  

