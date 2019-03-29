---
title: 配置 Office 365 租户以提高安全性
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: 引导您完成影响 Office 365 环境安全性的租户范围设置的建议配置。 您的安全需求可能需要更高或更低的安全性。 使用这些建议作为起点。
ms.openlocfilehash: 26f7bebd1eab1f43da356786bdef5f3fff860053
ms.sourcegitcommit: 54d58da1777eb83adb82826d1bb1adb94903c8e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30955265"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>配置 Office 365 租户以提高安全性

本主题将引导您完成影响 Office 365 环境安全性的租户范围设置的建议配置。 您的安全需求可能需要更高或更低的安全性。 使用这些建议作为起点。
  
## <a name="check-office-365-secure-score"></a>检查 Office 365 安全分数

office 365 安全分数根据您的常规活动和安全设置来分析 office 365 组织的安全性, 并给出分数。 首先记录你的当前分数。 调整某些租户范围的设置将增加你的成绩。 目标不能达到最大分数, 但请注意保护您的环境不会对用户的工作效率造成负面影响的机会。 请参阅[简介 Office 365 安全分数](office-365-secure-score.md)。
  
## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>在 Microsoft 365 安全中心调整威胁管理策略

Microsoft 365 安全中心包含可保护您的环境的功能。 它还包括可用于监视和执行操作的报告和仪表板。 某些区域附带了默认策略配置。 某些区域不包含默认策略或规则。 请访问 "威胁管理" 下的这些策略, 以调整更安全的环境的威胁管理设置。 
  
|区域 * * * *|包含默认策略 * * * *|建议 * * * *|
|:-----|:-----|:-----|
|**反网络钓鱼** <br/> |是  <br/> | 如果您有自定义域, 请创建反网络钓鱼策略来保护您最有价值的用户 (如 CEO) 的电子邮件帐户, 并保护您的域。 查看[设置反网络钓鱼策略](set-up-anti-phishing-policies.md), 并使用示例作为指南创建策略: "示例: 用于保护用户和域的反网络钓鱼策略。"|
|**反恶意软件引擎** <br/> |是  <br/> | 编辑默认策略:  <br/> &ensp;&ensp;•常见附件类型筛选器—选择 "开"  <br/><br>  您还可以创建自定义恶意软件筛选器策略, 并将其应用到组织中的指定用户、组或域。  <br/> <br> 详细信息：  <br/> &ensp;&ensp;•[反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;•[配置反恶意软件策略](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP 安全附件** <br/> |否  <br/> | 在安全附件的主页上, 通过选中此框来保护 SharePoint、OneDrive 和 Microsoft 团队中的文件:  <br/>  &ensp;&ensp;•打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP  <br/> <br> 使用以下设置添加新的安全附件策略:  <br/>  &ensp;&ensp;•阻止—使用检测到的恶意软件阻止当前和将来的电子邮件和附件 (选择此选项)  <br/>  &ensp;&ensp;•启用重定向-(选中此框并输入电子邮件地址, 如管理员或隔离帐户)  <br/>  &ensp;&ensp;•如果恶意软件扫描附件超时或发生错误, 则应用上述选择 (选中此框)  <br/>  &ensp;&ensp;•适用于—收件人域为 (选择您的域)  <br/>  <br>详细信息:[设置 Office 365 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md) <br/> |
|**ATP 安全链接** <br/> |是  <br/> | 将此设置添加到整个组织的默认策略:  <br/> &ensp;&ensp;•使用中的安全链接: office 365 专业增强版中的 office for iOS 和 Android (选择此选项)。  <br/> <br>针对特定收件人的推荐策略:  <br/>  &ensp;&ensp;•当用户单击链接 (选择此选项) 时, 将对 url 进行重写并对已知恶意链接列表进行检查。  <br/>  &ensp;&ensp;•使用安全附件扫描可下载的内容 (选中此框)。  <br/>  &ensp;&ensp;•适用于—收件人域为 (选择您的域)。  <br/> <br> 有关详细信息, 请: [Office 365 ATP 安全链接](atp-safe-links.md)。  <br/> |
|**反垃圾邮件 (邮件筛选)** <br/> |是  <br/> | 要监视的内容:  <br/>  &ensp;&ensp;•垃圾邮件过多—选择 "自定义设置" 并编辑 "默认垃圾邮件筛选器" 策略。  <br/>  &ensp;&ensp;•欺骗性智能—查看欺骗您的域的发件人。 阻止或允许这些发件人。  <br/>  <br>有关详细信息, 请执行以下操作: [Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)。  <br/> |
|***电子邮件身份验证*** <br/> |是  <br/> |电子邮件身份验证使用域名系统 (DNS) 将可验证的信息添加到有关电子邮件发件人的电子邮件中。 office 365 为其默认域 (onmicrosoft.com) 设置电子邮件身份验证, 但 Office 365 管理员还可以对自定义域使用电子邮件身份验证。 使用三种身份验证方法: <br/> <br> &ensp;&ensp;•发件人策略框架 (或 SPF)。<br/>&ensp;&ensp;&ensp;&ensp;-有关设置, 请参阅[在 Office 365 中设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 <br/> &ensp;&ensp;•域密钥识别邮件 (DKIM)。 <br/> &ensp;&ensp;&ensp;&ensp;-请参阅[在 Office 365 中使用自定义域中的电子邮件 DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)。 <br>&ensp;&ensp;&ensp;&ensp;-配置 DKIM 后, 在安全中心启用它。<br/> &ensp;&ensp;•基于域的邮件身份验证、报告和一致性 (DMARC)。 <br/> &ensp;&ensp;&ensp;&ensp;-适用于 DMARC 安装程序[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。<br/>  <br/>
|

> [!NOTE]
> 对于 SPF、混合部署和故障排除的非标准部署: [Office 365 如何使用发件人策略框架 (SPF) 来防止欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>查看安全与合规中心中的仪表板和报告

请访问这些报告和仪表板, 以了解有关你的环境运行状况的详细信息。 当您的组织使用 Office 365 服务时, 这些报告中的数据将变得更加丰富。 现在, 先熟悉你可以监视的内容并对其执行操作。 有关详细信息, 请参阅: [Microsoft 365 安全与合规中心中的报告](reports-in-security-and-compliance.md)。
  
|仪表板 * * * *|****说明****|
|:-----|:-----|
|威胁管理仪表板  <br/> |在安全中心的 "威胁管理" 部分, 使用此仪表板查看已处理的威胁, 并作为一种方便的工具, 用于向业务决策制定者报告已完成的威胁调查和响应功能保护您的企业。  <br/> |
|威胁资源管理器  <br/> |这也是安全中心的 "威胁管理" 部分。 如果要调查或遇到针对 Office 365 租户的攻击, 请使用威胁资源管理器分析威胁。 威胁资源管理器显示一段时间内的攻击量, 并且您可以通过威胁系列、攻击者基础结构等对此数据进行分析。 您还可以标记事件列表的任何可疑电子邮件。  <br/> |
|报告-仪表板  <br/> |在安全中心的 "报告" 部分, 查看您的 SharePoint online 和 Exchange Online 组织的审核报告。 您还可以从 "查看报告" 页访问 azure Active Directory (azure ad) 用户登录报告、用户活动报告和 azure AD 审核日志。  <br/> |
   
![安全中心仪表板](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>配置其他 Exchange Online 租户范围设置

在 Exchange 管理中心中, 许多用于安全性和保护的控件也包含在安全中心中。 您无需在这两个位置进行配置。 以下是建议的两个附加设置。 
  
|区域 * * * *|包含默认策略 * * * *|建议 * * * *|
|:-----|:-----|:-----|
|**邮件流**(邮件流规则, 也称为传输规则)|否|添加邮件流规则, 以帮助抵御勒索软件的侵害。 请参阅本文中的 "如何使用 Exchange 传输规则跟踪或阻止由勒索软件使用的文件扩展名的电子邮件"。在此博客文章中:[如何处理勒索软件](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/)。  <br><br/> 创建邮件流规则, 以阻止将电子邮件自动转发到外部域。 有关详细信息, 请参阅[通过安全分数缓解客户端外部转发规则](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。 <br/><br/> 详细信息: [Exchange Online 中的邮件流规则 (传输规则)](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx)|
|**启用新式验证**|否|Office 365 中的新式验证是使用多重身份验证 (MFA) 的先决条件。 建议使用 MFA 来保护对云资源 (包括电子邮件) 的访问。 <br/><br/> 请参阅以下主题:  <br/>•[在 Exchange Online 中启用或禁用新式验证](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) <br/>• [Skype for business Online: 为你的租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> 默认情况下, 将为 Office 2016 客户端、SharePoint Online 和 OneDrive for business 启用新式验证。 <br/><br/> 详细信息:[使用 office 365 新式身份验证与 office 客户端](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a)|
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在 SharePoint 管理中心中配置租户范围内的共享策略

Microsoft 关于在更高级别的保护 (从基准保护开始) 中配置 SharePoint 团队网站的建议。 有关详细信息, 请参阅[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
在基线级别配置的 SharePoint 团队网站允许使用匿名访问链接与外部用户共享文件。 建议使用此方法, 而不是在电子邮件中发送文件。 
  
若要支持基准保护的目标, 请按照此处的建议配置租户范围内的共享策略。 与此租户范围的策略相比, 对各个网站的共享设置的限制可能更大, 但不会更好。 
  
|区域 * * * *|包含默认策略 * * * *|建议 * * * *|
|:-----|:-----|:-----|
|**共享**(SharePoint Online 和 OneDrive for business)|是|默认情况下启用外部共享。 建议使用以下设置: <br/>•允许与经过身份验证的外部用户共享, 并使用匿名访问链接 (默认设置)。 <br/>  •匿名访问链接将在这几天内过期。 如果需要, 请输入一个数字, 如30天。 <br/>•默认链接类型-选择 "内部" (仅限组织中的 "人员")。 希望使用匿名链接进行共享的用户必须从 "共享" 菜单中选择此选项。 <br/><br/> 详细信息:[外部共享概述](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85)|
   
SharePoint 管理中心和 OneDrive for business 管理中心包括相同的设置。 任何一个管理中心的设置都适用于这两种情况。
  
## <a name="configure-settings-in-azure-active-directory"></a>在 Azure Active Directory 中配置设置

请务必在 Azure Active Directory 中访问这两个区域, 以完成针对更安全的环境的租户范围安装。
  
### <a name="configure-named-locations-under-conditional-access"></a>配置命名位置 (在条件访问下)

如果你的组织包含具有安全网络访问权限的办公室, 请将受信任的 IP 地址范围添加到 Azure Active Directory 作为已命名的位置。 此功能有助于减少登录风险事件报告的误报数。 
  
请参阅: [Azure Active Directory 中的已命名位置](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>阻止不支持新式身份验证的应用程序

多因素身份验证需要支持新式身份验证的应用。 不支持新式身份验证的应用程序无法通过使用条件访问规则来阻止。
  
对于安全环境, 请务必为不支持新式身份验证的应用程序禁用身份验证。 您可以在 Azure Active Directory 中执行此操作, 其中包含即将推出的控件。
  
同时, 请使用下列方法之一为 SharePoint Online 和 OneDrive for business 实现此目的:
  
- 使用 PowerShell, 请参阅[阻止不使用新式身份验证的应用](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)程序。
    
- 在 SharePoint 管理中心的 "设备访问" 页上配置此设置: "控制不使用新式身份验证的应用程序的访问"。 选择 "阻止"。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>开始使用云应用安全或 Office 365 云应用安全

使用 Office 365 云应用安全性评估风险、对可疑活动发出警报并自动采取措施。 需要 Office 365 E5 计划。
  
或者, 在授予访问权限、全面控制和改进对所有云应用程序 (包括 Office 365) 的保护后, 使用 Microsoft 云应用安全获取更深入的可见性。 
  
由于此解决方案建议了 EMS E5 计划, 因此我们建议您从云应用安全性开始, 以便可以将其与环境中的其他 SaaS 应用程序一起使用。 从默认策略和设置开始。
  
详细信息：
  
- [部署 Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [有关 Microsoft Cloud App Security 的更多信息](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Overview of Office 365 Cloud App Security](office-365-cas-overview.md)
    
![Cloud App Security 仪表板](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>其他资源

这些文章和指南提供了有关保护 Office 365 环境的其他说明性信息:
  
- [针对政治活动、非营利组织和其他 agile 组织的 Microsoft 安全指南](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)(您可以在任何环境 (尤其是仅限云环境) 中使用这些建议 
    
- [推荐的用于标识和设备的安全策略和配置](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)(这些建议包括针对 AD FS 环境的帮助) 
    

