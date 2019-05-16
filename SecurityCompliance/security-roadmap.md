---
title: Office 365 安全路线图-前30天、90天及以上的首要优先级
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 'Microsoft cybersecurity 团队提供的用于实施安全功能以保护您的 Office 365 环境的主要建议。 '
ms.openlocfilehash: d6ac885d2517a7933df52b34124654784012c677
ms.sourcegitcommit: 7be8617ce75909f0fa1a2f6e72749e2ef4bb2d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2019
ms.locfileid: "34088815"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 安全路线图-前30天、90天及以上的首要优先级

本文包括来自 Microsoft cybersecurity 团队的最佳建议, 这些建议可实施安全功能来保护您的 Office 365 环境。 本文适用于 Microsoft Ignite 会话 ([如 cybersecurity pro) 安全的 Office 365: 前30天、90天和之后的主要优先级](https://www.youtube.com/watch?v=luignzNyR-o)。 此会话是通过标记 Simos 和 Matt Kemelhar (企业 Cybersecurity 架构师) 开发和展示的。
  
本文内容：
  
- [路线图结果](security-roadmap.md#Roadmap)
    
- [30天—功能强大的快速 wins](security-roadmap.md#Thirdaydays)
    
- [90天—增强型保护](security-roadmap.md#Ninetydays)
    
- [满足](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>路线图结果
<a name="Roadmap"> </a>

这些路线图建议按逻辑顺序在三个阶段之间暂存, 具有以下目标。

|||
|:-----|:-----|
| |结果
|30 天|快速配置:  <br/> •基本管理保护  <br/> •日志记录和分析  <br/> •基本标识保护  <br/> 租户配置  <br/>  准备利益干系人  <br/> |
|90 天|高级保护:  <br/> •管理员帐户  <br/>  •数据&amp;用户帐户  <br/>  对合规性、威胁和用户需求的可见性  <br/>  调整和实施默认策略和保护  <br/> |
|满足|调整和优化主要策略和控件  <br/> 将保护扩展到本地依赖项  <br/> 与业务和安全流程集成 (法律、内幕威胁等)  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30天—功能强大的快速 wins
<a name="Thirdaydays"> </a>

这些任务可快速完成，对用户产生的影响很小。
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> |•检查安全得分并记录你的当前得分 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  •打开 Office 365 的审核日志记录。 请参阅[搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。  <br/> •[配置 Office 365 租户以提高安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  •定期查看 Microsoft 365 安全中心和云应用安全中的仪表板和报告。  <br/> |
|威胁防护  <br/> |[将 Office 365 连接到 Microsoft 云应用安全](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security), 开始使用默认威胁检测策略对反常行为进行监视。 为异常检测构建基准需要七天时间。  <br><br/>  对管理员帐户实施保护:  <br/> •使用专用管理员帐户进行管理活动。  <br/>  •为管理员帐户强制实施多重身份验证 (MFA)。  <br/>  •使用[高度安全的 Windows 10 设备](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)进行管理活动。  <br/> |
|标识和访问管理  <br/> |•[启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> •对于联合身份环境, 强制实施帐户安全性 (密码长度、年龄、复杂性等)。  <br/> |
|信息保护  <br/> | 查看示例信息保护建议。 信息保护需要跨整个组织进行协作。 开始使用这些资源：  <br/> •[适用于 GDPR 的 Office 365 信息保护](http://aka.ms/o365gdpr) <br/> •[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)(包括共享、分类、数据丢失防护和 Azure 信息保护)  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90天—增强型保护
<a name="Ninetydays"> </a>

虽然这些任务需要多花一点时间来计划和实现，但会显著改善安全态势。 
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> | •检查安全分数以了解针对你的环境的[https://securescore.office.com](https://securescore.office.com)建议操作 ()。  <br/>  •继续定期查看 Microsoft 365 安全中心、云应用安全和 SIEM 工具中的仪表板和报告。  <br/>  •查找并实施软件更新。  <br/>  •使用[攻击模拟器](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)(包含在[Office 365 威胁智能](office-365-ti.md)中) 对 spear 进行攻击模拟, 从而实现网络钓鱼、密码喷涂和强力密码攻击。  <br/>  •通过查看 Cloud App Security 中的内置报告 (在 "调查" 选项卡上), 查找共享风险。  <br/>  •检查[合规性管理器](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)以查看适用于您的组织的规章的状态 (如 GDPR、NIST 800-171)。  <br/> |
|威胁防护  <br/> | 为管理员帐户实施增强的保护:  <br/>  •为管理员活动配置[权限访问工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)(PAWs)。  <br/>  •配置[AZURE AD 特权标识管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。  <br/>  •配置安全信息和事件管理 (SIEM) 工具以收集来自 Office 365、云应用安全性和其他服务 (包括 AD FS) 的日志记录数据。 Office 365 审核日志仅存储90天的数据。 通过在 SIEM 工具中捕获此数据, 可以将数据存储在更长的时间段中。  <br/> |
|标识和访问管理  <br/> | •为所有用户启用和强制执行 MFA。  <br/>  •实现一组[条件访问和相关策略](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。 |
|信息保护  <br/> | 修改和实施信息保护策略。 这些资源包括示例:  <br/> •[适用于 GDPR 的 Office 365 信息保护](http://aka.ms/o365gdpr) <br/> •[保护 SharePoint Online 网站和文件](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> 对于存储在 Office 365 中的数据, 使用数据丢失防护策略和监视工具 (而不是云应用安全) 在 Office 365 中。 <br><br>使用适用于 Office 365 的云应用安全性进行高级警报功能 (而不是数据丢失防护)。  <br/> |
   
## <a name="beyond"></a>满足
<a name="Beyond"> </a>

这些是在以前的工作上构建的重要安全措施。 
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> |•使用安全得分继续规划下一步操作[https://securescore.office.com](https://securescore.office.com)()。  <br/>  •继续定期查看 Microsoft 365 安全中心、云应用安全和 SIEM 工具中的仪表板和报告。  <br/>  •继续查找并实施软件更新。  <br/>  •将电子数据展示集成到你的法律和威胁响应流程中。  <br/> |
|威胁防护  <br/> | •为本地 (AD、AD FS) 上的标识组件实施[安全的特权访问](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA)。  <br/>  •使用云应用安全来监视内幕威胁。  <br/>  •通过使用云应用安全性发现影子 IT SaaS 使用。  <br/> |
|标识和访问管理  <br/> | •优化策略和操作过程。  <br/>  •使用 Azure AD 标识保护来确定内部威胁。  |
|信息保护  <br/> | 优化信息保护策略:  <br/>  • Microsoft 365 和 Office 365 敏感标签和数据丢失防护 (DLP) 或 Azure 信息保护。  <br/>  •云应用安全策略和警报。  <br/> |
   
另请参阅:[如何缓解快速 cyberattacks, 如 Petya 和 WannaCrypt](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。 
  

