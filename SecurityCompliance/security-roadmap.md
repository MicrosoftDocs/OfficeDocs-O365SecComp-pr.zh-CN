---
title: Office 365 安全路线图-顶部优先级的前 30 天，90 天及其他认证实战
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: '来自 Microsoft 的网络安全团队用于实现安全功能，以保护您的 Office 365 环境的主要建议。 '
ms.openlocfilehash: 58767ea9a2b825d1583d9135f9d8edcb0d20d7c2
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "25450077"
---
# <a name="office-365-security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>Office 365 安全路线图-顶部优先级的前 30 天，90 天及其他认证实战

本文包括来自 Microsoft 的网络安全团队用于实现安全功能，以保护您的 Office 365 环境的主要建议。本文改编 Microsoft Ignite 会话 —[如网络专业人员的安全保护 Office 365: Top 优先级的前 30 天，90 天及其他认证实战](https://www.youtube.com/watch?v=luignzNyR-o)。此会话已被开发并演示者标记 Simos 和 Matt Kemelhar，企业网络安全的架构师。
  
本文内容：
  
- [路线图产出](security-roadmap.md#Roadmap)
    
- [30 天 — 强大的快速 wins](security-roadmap.md#Thirdaydays)
    
- [90 天 — 增强保护](security-roadmap.md#Ninetydays)
    
- [超出](security-roadmap.md#Beyond)
    
## <a name="roadmap-outcomes"></a>路线图产出
<a name="Roadmap"> </a>

这些路线图建议被暂存跨三个阶段具有以下目标逻辑顺序。

|||
|:-----|:-----|
| |结果
|30 天|快速配置：  <br/> • 基本管理保护  <br/> • 日志记录和分析  <br/> • 基本标识保护  <br/> 租户配置  <br/>  准备利益干系人  <br/> |
|90 天|高级的保护：  <br/> • 管理帐户  <br/>  • 数据&amp;用户帐户  <br/>  可见性合规性、 威胁和用户需求  <br/>  调整和实施默认策略和保护功能  <br/> |
|超出|调整和优化关键策略和控件  <br/> 扩展保护内部部署的依赖关系  <br/> 与 （法律、 内部威胁等） 的业务和安全流程集成  <br/> |
  

   
## <a name="30-days--powerful-quick-wins"></a>30 天 — 强大的快速 wins
<a name="Thirdaydays"> </a>

这些任务可快速完成，对用户产生的影响很小。
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> |• 检查安全分数，并记下您当前的分数 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 打开 Office 365 的审核日志记录。请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。<br/> •[配置 Office 365 租户为了提高安全性](tenant-wide-setup-for-increased-security.md)。  <br/>  • 定期查看仪表板和在 Office 365 安全性和合规性中心和云应用程序安全性的报告。  <br/> |
|威胁防护  <br/> |[连接到 Microsoft 云应用程序安全性的 Office 365](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)启动监控的默认威胁检测策略用于异常行为。计七天生成异常检测的基线。<br><br/>  实现保护管理员帐户 （英文）：  <br/> • 使用专用的管理帐户管理活动。  <br/>  • 强制实施多因素身份验证 (MFA) 的管理帐户。  <br/>  • 管理活动使用[高级安全 Windows 10 设备](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure)。  <br/> |
|标识和访问管理  <br/> |•[启用 Azure Active Directory 标识保护](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。  <br/> ？ 对于联合的身份环境，实施帐户安全性 （密码长度、 老化、 复杂性等）。  <br/> |
|信息保护  <br/> | 查看示例信息保护建议。信息保护要求在您的组织之间的协调。开始使用这些资源：<br/> • [GDPR 的 office 365 的信息保护](http://aka.ms/o365gdpr) <br/> •[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files)（包括共享、 分类、 数据丢失防护和 Azure 信息保护）  <br/> |
   
## <a name="90-days--enhanced-protections"></a>90 天 — 增强保护
<a name="Ninetydays"> </a>

虽然这些任务需要多花一点时间来计划和实现，但会显著改善安全态势。 
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> | • 检查您的环境的建议操作安全分数 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 继续定期查看仪表板和 Office 365 安全性和合规性中心、 云应用程序安全性和 SIEM 工具中的报告。  <br/>  • 查找并实施软件更新。  <br/>  • 准则攻击模拟矛网络钓鱼、 密码-喷涂和密码强力攻击使用[攻击模拟器](https://support.office.com/article/attack-simulator-office-365-da5845db-c578-4a41-b2cb-5a09689a551b)（包含[Office 365 威胁智能](office-365-ti.md)）。  <br/>  • 通过查看 （在调查选项卡） 中云应用程序安全性的内置报表共享风险的外观。  <br/>  • 检查检查状态适用于您的组织 （如 GDPR，NIST 800 171) 的法规[合规性管理器](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md)。  <br/> |
|威胁防护  <br/> | 实现保护管理帐户的增强的功能：  <br/>  • 管理活动配置[特权访问工作站](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations)（小爪印儿）。  <br/>  • 配置[Azure AD 权限身份管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。  <br/>  • 配置从 Office 365、 云应用程序安全性和其他服务，包括 AD FS 收集日志记录数据的安全信息和事件 (SIEM) 管理工具。Office 365 审核日志存储仅 90 天的数据。捕获此类数据 SIEM 工具中的，可以更长时间段中存储数据。<br/> |
|标识和访问管理  <br/> | • 启用和强制 MFA 执行的所有用户。  <br/>  • 实现一组[条件的访问和相关的策略](https://docs.microsoft.com/en-us/microsoft-365/enterprise/microsoft-365-policies-configurations)。 |
|信息保护  <br/> | 调整和实现信息保护策略。这些资源包括示例：<br/> • [GDPR 的 office 365 的信息保护](http://aka.ms/o365gdpr) <br/> •[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/Office365/enterprise/secure-sharepoint-online-sites-and-files) <br/> <br> 使用数据丢失预防策略和 Office 365 中 （而不是云应用程序安全性） 的 Office 365 中存储的数据的监视工具。 <br><br>云应用程序安全性使用 Office 365，用于高级警报 （而非数据丢失防护） 的功能。  <br/> |
   
## <a name="beyond"></a>超出
<a name="Beyond"> </a>

这些是构建以前的工作的重要安全措施。 
  
|||
|:-----|:-----|
|区域  <br/> |任务  <br/> |
|安全管理  <br/> |• 继续下一步操作规划使用安全分数 ( [https://securescore.office.com](https://securescore.office.com))。  <br/>  • 继续定期查看仪表板和 Office 365 安全性和合规性中心、 云应用程序安全性和 SIEM 工具中的报告。  <br/>  • 继续查找并实施软件更新。  <br/>  • 集成到您的法律电子数据展示和威胁响应流程。  <br/> |
|威胁防护  <br/> | • 为本地 （AD、 AD FS） 的标识组件实现[安全特权访问](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)(SPA)。  <br/>  • 使用云应用程序安全性监视的内部人员威胁。  <br/>  • 发现使用云应用程序安全性的卷影 IT saas 与使用。  <br/> |
|标识和访问管理  <br/> | • 优化信息保护策略：  <br/>  • Azure 信息保护和 Office 365 数据丢失防护 (DLP)。  <br/>  • 云应用程序的安全策略和通知。  <br/> |
|信息保护  <br/> | • 优化策略以及操作过程。  <br/>  ？ 使用 Azure AD 身份保护识别内幕威胁。  <br/> |
   
另请参阅：[如何缓解如 Petya 和 WannaCrypt 快速事件](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)。 
  

