---
title: Office 365 云应用安全中的新增功能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: reference
ms.date: 01/25/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
description: 查看在 2018 for Office 365 云应用安全中发布的内容
ms.openlocfilehash: 986fb64eedf8184e7835d1fec41845fde13b294b
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263142"
---
# <a name="office-365-cloud-app-security-updates-during-2018"></a>2018期间的 Office 365 云应用安全更新

## <a name="office-365-cloud-app-security-release-138"></a>Office 365 云应用安全发布版138

*2018年12月23日发布*

**以下[Microsoft 云应用安全发布版 138](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-138)**:

- **使用 Windows 上的 Docker 自动进行日志上传**云应用安全性现在支持 windows 10 (在[创建者更新](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)和更新) 和 windows Server ([版本 1709](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1709)及更高版本) 的自动日志上载 (使用 windows 上的 Docker)。 请参阅[本文](https://docs.microsoft.com/cloud-app-security/discovery-docker-windows), 了解详细信息并配置 Docker。  

- **Microsoft 流集成**云应用安全性现在与[Microsoft 流](https://docs.microsoft.com/flow/getting-started)集成, 以提供自定义警报自动化和业务流程行动手册。 请参阅[本文](https://docs.microsoft.com/cloud-app-security/flow-integration), 了解详细信息并配置 Microsoft 流集成。 

## <a name="office-365-cloud-app-security-release-137"></a>Office 365 云应用安全发布版137

*2018年12月8日发布*

**以下[Microsoft 云应用安全发布版 137](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-137)**:

- **增加了对 Dynamics 的支持**云应用安全性现在包括对 Office 365 审核日志中支持的 Microsoft Dynamics 活动的支持。 

- **提醒-新术语!** 为清楚起见, 更改了应用程序权限功能的名称–它现在称为 OAuth 应用程序。 

## <a name="office-365-cloud-app-security-release-136"></a>Office 365 云应用安全发布版136

*2018年11月25日发布*

**以下[Microsoft 云应用安全发布版 136](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-136)**:

- **云发现更新**增强了自定义日志分析器, 以支持其他更复杂的 web 通信日志格式。 作为这些增强功能的一部分, 用户现在可以为 headerless CSV 日志文件输入自定义标头, 对键值文件、进程 Syslog 文件格式等使用特殊分隔符。

- **新异常情况检测策略: 可疑的收件箱操作规则**当在用户的收件箱上设置了删除或移动邮件或文件夹的可疑规则时, 此策略将对您的环境进行配置并触发警告。 这可能表示用户的帐户受到威胁, 该邮件有意隐藏, 并且该邮箱正用于在您的组织中分发垃圾邮件或恶意软件。

- **对应用程序权限策略中的组的支持**云应用安全性现在使您能够根据授权应用的用户的组成员身份, 更精确地定义应用程序权限策略。 例如, 管理员可以决定设置一个策略, 以便在用户要求提供高权限时撤销不常见的应用程序, 仅当授权权限的用户是 administrators 组的成员时。

## <a name="office-365-cloud-app-security-releases-133-134-and-135"></a>Office 365 云应用安全发布133、134和135

*2018年10月发布的*

**以下[Microsoft 云应用安全发布版133、134和 135](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-133-134-135)**:

- **新的异常情况检测策略**将逐步推出:
    
    - 当用户或 IP 地址使用不受 sanctioned 的应用程序执行类似于从您的组织中 exfiltrate 信息的活动时, 会自动启用新的**Data exfiltration to unsanctioned apps**策略以提醒您。
    
    - 新的**多个 "删除 VM 活动**" 策略配置文件: 当用户在单个会话中删除多个 vm (相对于组织中的基准) 时, 您的环境和触发警报。

- **对 i-筛选器的云发现支持**云应用安全云发现功能现已增强对 i-筛选器 syslog 分析程序的支持。

## <a name="office-365-cloud-app-security-release-131"></a>Office 365 云应用安全发布版131

*2018年9月发布的*

**以下[Microsoft 云应用安全发布版 131](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-131)**:

- **在有风险的 OAuth 应用上自动废除权限**您现在可以通过撤消 Office 上的 oauth 应用程序的应用权限来控制用户有权访问哪些 OAuth 应用程序。 在创建应用程序权限策略时, 您现在可以设置策略以撤消应用程序的权限。

- **支持的云发现其他内置分析器**云发现现支持 Forcepoint Web 安全云日志格式。
  
## <a name="office-365-cloud-app-security-release-130"></a>Office 365 云应用安全发布版130

*2018年9月5日发布*

**以下[Microsoft 云应用安全发布版 130](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-130)**:

- **新菜单栏**为了在 microsoft 365 产品中提供更一致的管理体验, 并使您能够更轻松地在 microsoft 安全解决方案之间进行透视, 云应用安全门户菜单栏已移至屏幕左侧。 这种一致的导航体验可帮助您在从一个 Microsoft 安全门户迁移到另一个时向自己定向。<br/>![Office Cloud App Security 中的菜单栏](media/OCAS-MenuBar.png)<br/>

- **对 OAuth 应用分数的影响**现在, 你可以发送云应用安全团队反馈, 让我们了解你的组织中发现有恶意的 OAuth 应用。 此新功能使您能够成为我们安全社区的一部分, 并增强 OAuth 应用程序风险分数和分析。 有关详细信息, 请参阅[Manage OAuth apps](manage-app-permissions-in-ocas.md)。

- **新的云发现分析**程序云发现分析程序现在支持 iboss 安全云网关和 Sophos XG。

## <a name="office-365-cloud-app-security-release-128"></a>Office 365 云应用安全发布版128

*2018年8月5日发布* 
  
**以下[Microsoft 云应用安全发布版 128](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-128)**: 
  
- **跨多个应用程序的 OAuth 应用**程序对于 OAuth 应用程序, 您现在可以在一次操作中禁止或批准多个应用程序。 例如, 您可以查看您的组织中的用户已授予其权限的所有应用程序, 选择要禁止的所有应用程序, 然后单击 "禁止应用程序" 以取消已授予的所有同意, 并且不再允许用户授予对这些应用程序的权限。 若要了解详细信息, 请参阅[使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)。 
    
- **新的建议查询: GDPR-ready 云应用程序**有一个新的建议查询, 可让你识别 GDPR 准备就绪的应用。 您可能已经知道, GDPR 最近已成为安全管理员的头等大事。 此查询可帮助您轻松识别 GDPR 准备好的应用程序, 并通过评估不存在的应用程序的风险来缓解威胁。 若要使用新查询, 请在**云发现**仪表板中的 **"发现的应用**" 选项卡上, 选择 "**查询** > **GDPR 云应用程序**"。<br/>![GDPR-就绪的云应用程序查询](media/OCAS-FindGDPRQueries.png)<br/>
    
## <a name="office-365-cloud-app-security-release-126"></a>Office 365 云应用安全发布版126

*2018年7月7日发布* 
  
**以下[Microsoft 云应用安全发布版 126](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-126)**: 
  
- **可疑活动的自动修正**您现在可以为异常检测策略触发的可疑会话设置自动修正操作。 此增强功能使您能够在发生违规情况时立即收到警报, 并自动应用调控操作, 如挂起用户。 有关详细信息, 请参阅[Office 365 Cloud App Security 中的异常检测策略](anomaly-detection-policies-in-ocas.md)。
    
- **自动检测有风险的 OAuth 应用**除了对连接到您的环境的 OAuth 应用程序的现有调查之外, Office 365 云应用安全性现在还允许您设置自动通知, 让您知道 OAuth 应用程序何时满足特定条件。 例如, 当存在需要高权限级别且由超过50个用户授权的应用时, 可以自动收到通知。 有关详细信息, 请参阅[使用 Office 365 云应用安全管理 OAuth 应用](manage-app-permissions-in-ocas.md)。
    
- **托管安全服务提供程序管理 (MSSP) 支持**Office 365 云应用安全现在为 mssp 提供了更好的管理体验, 并允许您将外部合作伙伴配置为具有 Office 365 云应用安全中当前可用的任何角色的管理员。 此外, 对多个租户拥有访问权限的管理员现在可以轻松地在租户之间进行透视。 
    
## <a name="office-365-cloud-app-security-release-124"></a>Office 365 云应用安全发布版124

*2018年6月10日发布* 
  
**以下[Microsoft 云应用安全发布版 124](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-124)**: 
  
- **作用域部署**企业组织可以根据组成员身份确定要监视和保护的用户的粒度。 此功能使您能够选择其活动不会显示在任何受保护的应用程序中的用户。 作用域监视对于合规性和许可尤其有用。 某些合规性管理法规需要您避免因本地管理法规而不能监控特定国家/地区的用户。 而且, 您可以监视较少的用户, 使其保持在 Office 365 云应用安全许可证的限制范围内。 
    
- **新建电子邮件服务器**Office 365 云应用安全性的电子邮件服务器已更改, 并使用不同的 IP 地址范围。 若要确保能够获取通知, 请将新的 IP 地址添加到反垃圾邮件白名单中。 对于自定义其通知的组织, 云应用安全为您使用 MailChimp (第三方电子邮件服务) 启用此功能。 有关邮件服务器 IP 地址的列表以及启用与 MailChimp 的操作的说明, 请参阅[网络要求 (microsoft cloud app security)](https://docs.microsoft.com/cloud-app-security/network-requirements)和[邮件设置 (microsoft 云应用安全)](https://docs.microsoft.com/cloud-app-security/mail-settings)。
    
## <a name="office-365-cloud-app-security-release-121"></a>Office 365 云应用安全发布版121

*发布日2018年5月6日* 
  
**以下[Microsoft 云应用安全发布版 121](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-121)**: 
  
- **异常检测策略改进**。 Office 365 云应用安全的异常检测策略已得到改进, 可包括两种新类型的威胁检测, 它们将逐步推出: 
    
  - **勒索软件活动。** 通过异常检测扩展了勒索软件检测功能, 为您提供对复杂的勒索软件攻击的更全面的覆盖。 
    
  - **终止的用户活动。** "终止用户" 活动使您能够监视可能已从企业应用程序中取消设置的已终止用户的帐户, 但可能仍有权访问某些公司资源。 
    
    若要查看[异常检测策略](anomaly-detection-policies-in-ocas.md), 请在 Office 365 云应用安全门户中, 选择 "**控制** \> **策略**"。
    
## <a name="office-365-cloud-app-security-release-120"></a>Office 365 云应用安全发布版120

*2018年4月22日发布* 
  
**以下[Microsoft 云应用安全发布版 120](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-120)**: 
  
- **作为用户活动的内部应用程序**。 对于 office 365 和 azure Active Directory (azure ad), 我们现在逐步推出了将内部应用程序检测为 Office 365 和 Azure AD 应用程序 (包括内部和外部) 执行的用户帐户活动的功能。 这样, 你便可以创建策略, 以便在应用程序执行意外和未授权活动时向你发出警报。 
    
- **OAuth 应用列表导出中的更多字段**。 将 OAuth 应用程序列表导出到 csv 时, 将包含其他字段 (如发布者、权限级别和社区使用情况), 以协助实现合规性和调查过程。 
    
## <a name="office-365-cloud-app-security-release-119"></a>Office 365 云应用安全发布版119

*2018年4月1日发布* 
  
**以下[Microsoft 云应用安全发布版 119](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-119)**: 
  
- **对云发现的改进**。 云发现提供了有关顶级用户和 IP 地址的详细信息, 使您可以更轻松地查看有关 Office 365 和其他应用程序的使用情况详细信息。 若要了解详细信息, 请参阅[查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)。
    
    ![云发现仪表板已更新](media/12712681-c0b3-4cb3-b7fd-2cf2ad4e825f.png)
  
## <a name="office-365-cloud-app-security-release-118"></a>Office 365 云应用安全发布版118

*2018年3月18日发布* 
  
**以下[Microsoft 云应用安全发布版 118](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-118)**: 
  
- **Barracuda 支持**。 云发现现在支持 Barracuda f 系列防火墙和 Barracuda f 系列防火墙 web 日志流。 
    
## <a name="office-365-cloud-app-security-release-117"></a>Office 365 云应用安全发布版117

*发布于2018年3月6日* 
  
**以下[Microsoft 云应用安全发布版 117](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-117)**: 
  
- **i-筛选器支持**。 云发现现在支持 i-筛选器。 
    
## <a name="office-365-cloud-app-security-release-116"></a>Office 365 云应用安全发布版116

*2018年2月18日发布* 
  
**以下[Microsoft 云应用安全发布版 116](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-116)**: 
  
- **异常情况检测策略增强**。 Office 365 中的异常检测策略已通过新的基于方案的检测 (包括无法进行的传播、来自可疑 IP 地址的活动和多个失败的登录尝试) 增强。 新策略将自动启用, 从而在你的云环境中提供现成的威胁检测。 此外, 新策略还会从 Office 365 云应用安全检测引擎中公开更多数据, 这有助于加快调查过程, 并包含持续的威胁。 若要了解详细信息, 请参阅 Microsoft 云应用安全文章[获取即时行为分析和异常检测](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)。
    
- **对检查点格式的日志分析器支持**。 云发现日志分析程序现在支持两种其他检查点格式: XML 和 KPC。 
    
## <a name="office-365-cloud-app-security-release-114"></a>Office 365 云应用安全发布版114

*2018年1月21日发布* 
  
**以下[Microsoft 云应用安全发布版 114](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-114)**: 
  
- **服务状态**。 您现在可以通过转到 "**帮助** \> "**系统状态**来检查当前 Office 365 云应用安全服务的状态。 
    
    ![单击 " \>帮助系统状态" 查看系统运行状况状态](media/2b496dac-ed9d-4480-83b6-85f9510d3aea.png)
  
- **活动日志的自定义查询**。 从版本114开始, 在活动日志中创建和保存自定义查询的功能将逐步推出。 利用自定义查询, 可以创建可重复使用的筛选器模板以进行深入调查。 此外, 还添加了建议的查询, 以提供现成的调查模板来筛选活动和发现的应用。 建议的查询包括用于确定风险 (如模拟活动)、管理员活动、有风险的不兼容云存储应用、具有弱加密的企业应用程序以及安全风险的自定义筛选器。 将建议的查询用作起始点, 根据需要对其进行修改, 然后将其另存为新查询。 
    
## <a name="office-365-cloud-app-security-release-113"></a>Office 365 云应用安全发布版113

*2018年1月8日发布* 
  
**以下[Microsoft 云应用安全发布版 113](https://docs.microsoft.com/cloud-app-security/release-notes#cloud-app-security-release-113)**: 
  
- **对通用格式的日志分析器支持**。 云发现日志分析程序现在支持以下通用格式: LEEF、CEF 和 W3C。 

## <a name="related-topics"></a>相关主题

[Office 365 云应用安全中的新增功能](new-in-office-365-cas.md)

[请参阅2017更新 for Office 365 云应用安全](new-in-office-365-cas-2017.md)
    
[推出 Office 365 云应用安全后的利用率活动](utilization-activities-for-ocas.md)