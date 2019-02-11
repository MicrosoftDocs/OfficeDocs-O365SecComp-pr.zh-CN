---
title: 配置 Office 365 租户以提高安全性
ms.author: tracyp
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
description: 指导您完成推荐配置租户范围会影响您的 Office 365 环境的安全性的设置。您的安全需求可能需要更多或更少的安全。使用这些建议作为起点。
ms.openlocfilehash: fa5e5980fd28a360a1469ca65d6598e708ad44f6
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29786329"
---
# <a name="configure-your-office-365-tenant-for-increased-security"></a>配置 Office 365 租户以提高安全性

本主题将指导您完成推荐配置租户范围会影响您的 Office 365 环境的安全性的设置。您的安全需求可能需要更多或更少的安全。使用这些建议作为起点。
  
## <a name="check-office-365-secure-score"></a>检查 Office 365 安全分数

Office 365 安全分数分析基于您的正则活动和安全设置的 Office 365 组织的安全性和分配分数。应记下您当前的分数首先。调整一些租户范围的设置将提高您的分数。目标是不以实现最大分数，但要注意的机会来保护您的环境，而不产生负面影响的用户的工作效率。请参阅[介绍 Office 365 安全分数](office-365-secure-score.md)。
  
## <a name="tune-threat-management-policies-in-the-office-365-security-amp-compliance-center"></a>调整威胁管理策略在 Office 365 安全性&amp;合规性中心

Office 365 安全性&amp;合规性中心包含保护您的环境的功能。它还包括报表和仪表板可用来监视和执行操作。某些区域附带的默认策略配置。某些区域不包括默认策略或规则。访问这些威胁管理来优化威胁管理设置的更安全的环境下的策略。 
  
|区域 ***|包含默认策略 ***|建议 ***|
|:-----|:-----|:-----|
|**防钓鱼** <br/> |是  <br/> | 如果您有自定义的域，创建防钓鱼策略，以保护您最有价值的用户，例如您 CEO 的电子邮件帐户，以及保护您的域。查看[防钓鱼策略设置](set-up-anti-phishing-policies.md)，创建一个策略作为指南使用示例:"示例： 防钓鱼保护用户和域策略。"|
|**反恶意软件引擎** <br/> |是  <br/> | 编辑默认策略：  <br/> &ensp;&ensp;• 公共附件筛选器的类型 — 选择  <br/><br>  此外可以创建自定义恶意软件筛选器策略并将它们应用于指定的用户、 组或域中您的组织。  <br/> <br> 详细信息：  <br/> &ensp;&ensp;•[反恶意软件保护](https://technet.microsoft.com/en-us/library/jj200669%28v=exchg.150%29.aspx) <br/> &ensp;&ensp;•[配置反恶意软件策略](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |
|**ATP 安全附件** <br/> |否  <br/> | 在主页上的安全附件，通过选中此框保护 SharePoint、 OneDrive 和 Microsoft 团队中的文件：  <br/>  &ensp;&ensp;• 打开 ATP SharePoint、 OneDrive 和 Microsoft 团队  <br/> <br> 使用这些设置添加新的安全的附件策略：  <br/>  &ensp;&ensp;• Block-阻止当前和将来的电子邮件和附件与检测到恶意软件 （选择此选项）  <br/>  &ensp;&ensp;• 启用重定向 — （选中此复选框和输入的电子邮件地址，例如管理员或隔离帐户）  <br/>  &ensp;&ensp;• 应用以上所选内容，如果恶意软件扫描的附件超时或错误发生 （选中此复选框）  <br/>  &ensp;&ensp;• 应用于 — 是 （选择您的域） 的收件人域  <br/>  <br>详细信息：[设置 Office 365 ATP 附件安全策略](set-up-atp-safe-attachments-policies.md) <br/> |
|**ATP 安全链接** <br/> |是  <br/> | 将此设置添加到整个组织的默认策略：  <br/> &ensp;&ensp;• 使用中的安全链接： Office 365 ProPlus、 适用于 iOS 的 Office 和 Android （选择此选项）。  <br/> <br>对特定收件人的建议的策略：  <br/>  &ensp;&ensp;将重写 • Url，并将其签针对一组已知的恶意链接，当用户单击的链接 （选择此选项）。  <br/>  &ensp;&ensp;• 要扫描的可下载内容的使用安全附件 （选中此复选框）。  <br/>  &ensp;&ensp;• 应用于 — 是 （选择您的域） 的收件人域。  <br/> <br> 详细信息： [Office 365 ATP 安全链接](atp-safe-links.md)。  <br/> |
|**反垃圾邮件 （邮件筛选）** <br/> |是  <br/> | 要监视的内容：  <br/>  &ensp;&ensp;• 太多垃圾邮件 — 选择自定义设置和编辑默认垃圾邮件筛选器策略。  <br/>  &ensp;&ensp;• 欺骗智能 — 查看欺骗您的域的发件人。阻止或允许这些发件人。<br/>  <br>详细信息： [Office 365 电子邮件防垃圾邮件保护](anti-spam-protection.md)。  <br/> |
|***电子邮件身份验证*** <br/> |是  <br/> |电子邮件身份验证使用域名系统 (DNS) 将可验证信息添加到有关电子邮件发件人的电子邮件。Office 365 设置其默认域 (onmicrosoft.com) 的电子邮件身份验证，但 Office 365 管理员也可以为自定义域使用电子邮件身份验证。使用三种身份验证方法：<br/> <br> &ensp;&ensp;• 发件人策略框架 （或 SPF）。安装程序，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。<br/> &ensp;&ensp;• 域密钥识别邮件 (DKIM)。若要使用 DKIM，请参阅[使用 DKIM 验证从您在 Office 365 中的自定义域发送出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)。<br>&ensp;&ensp;&ensp;&ensp;&ensp;-已配置 DKIM 后，您可以为您的组织在安全启用它&amp;合规性中心。<br/> &ensp;&ensp;• 基于域的邮件身份验证、 报告和一致性声明 (DMARC)。若要设置 DMARC，请参阅[使用 DMARC 用于验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。<br/>  <br/>
|

> [!NOTE]
> 非标准部署的 SPF、 混合部署和故障排除： [Office 365 如何使用发件人策略框架 (SPF) 以防止欺骗](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-security-amp-compliance-center"></a>安全中查看仪表板和报告&amp;合规性中心

访问这些报告和仪表板以了解有关您的环境的运行状况。这些报告中的数据将成为更丰富，根据您的组织使用 Office 365 服务。现在，熟悉什么可以监视并对其执行操作。有关详细信息，请参阅： [Reports in Office 365 安全性&amp;合规性中心](reports-in-security-and-compliance.md)。
  
|仪表板 ***|****Description****|
|:-----|:-----|
|威胁管理仪表板  <br/> |安全威胁管理部分&amp;合规性中心，请使用用于报告给上威胁智能已具有如何完成业务决策者的此仪表板的已处理，请参阅威胁以及方便的工具来保护您业务。  <br/> |
|威胁资源管理器  <br/> |这也是安全的威胁管理一节&amp;合规性中心。如果您正在调查或遇到攻击对 Office 365 租户，使用威胁资源管理器来分析威胁。威胁资源管理器显示您的攻击音量随时间推移，并可以分析通过威胁系列，攻击者基础结构的详细信息此数据。您还可以标记事件列表的任何可疑电子邮件。  <br/> |
|报告 — 仪表板  <br/> |在报告部分中的安全&amp;的 SharePoint Online 和 Exchange Online 组织的合规性中心查看审核报告。您还可以访问 Azure Active Directory (AD) 用户注册报告，用户活动报告，并从查看报告页的 Azure AD 审核日志。  <br/> |
   
![安全&amp;合规性中心仪表板](media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)
  
## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>配置其他 Exchange Online 租户范围的设置

中的安全性和合规性中心还包含很多安全和保护 Exchange 管理中心中的控件。不需要配置这些在两个位置。以下是几个建议的其他设置。 
  
|区域 ***|包含默认策略 ***|建议 ***|
|:-----|:-----|:-----|
|**邮件流**（传输规则）  <br/> |否  <br/> | 添加帮助防止勒索软件的邮件流规则。请参阅"如何使用 Exchange 传输规则来跟踪或阻止的文件扩展名使用勒索软件的电子邮件"，在此博客文章：[如何处理勒索软件](https://blogs.technet.microsoft.com/office365security/how-to-deal-with-ransomware/)。<br><br/> 创建传输规则阻止向外部域的自动转发电子邮件。有关详细信息，请参阅[缓解客户端外部转发规则安全分数](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)。<br/> <br>详细信息： [Mail flow 规则 （传输规则） 在 Exchange Online](https://technet.microsoft.com/en-us/library/jj919238%28v=exchg.150%29.aspx) <br/> |
|**启用现代身份验证** <br/> |否  <br/> | Office 365 中的现代身份验证是使用多因素身份验证 (MFA) 的先决条件。MFA 建议保护云资源，包括电子邮件的访问权限。<br/>  <br>请参阅下列主题：  <br/> [启用或禁用在 Exchange 在联机现代身份验证](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662)？ <br/> • [Skype 业务 online： 启用您的租户的现代身份验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/>  <br>Office 2016 客户端、 SharePoint Online 和 OneDrive for Business 的情况下，默认情况下启用现代身份验证。  <br/>  <br>详细信息：[使用 Office 365 与 Office 客户端的现代身份验证](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a) <br/> |
   
## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>在 SharePoint 管理中心中配置租户范围的共享策略

Microsoft 建议的配置 SharePoint 工作组网站在增加的保护，启动与比较基准保护级别。有关详细信息，请参阅[安全 SharePoint Online 网站和文件](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)
  
SharePoint 工作组网站在基线级别配置允许使用匿名访问链接与外部用户共享文件。推荐采用此方法，而不是电子邮件中发送文件。 
  
若要支持的比较基准保护目标，配置租户范围的共享策略，如此处建议。可以比此租户范围的策略，但不是更 permissive 更严格共享为单个站点的设置。 
  
|区域 ***|包含默认策略 ***|建议 ***|
|:-----|:-----|:-----|
|**共享**（SharePoint Online 和 OneDrive for Business）  <br/> |是  <br/> | 默认情况下，启用外部共享。建议使用这些设置：<br/>  • 允许共享验证外部用户和使用匿名访问链接 （默认设置）。  <br/>  在多个 days 过期 • 匿名访问的链接。如果需要，如 30 天，请输入一个号码。<br/>  • 默认链接类型 — 选择内部 （仅组织中的人员）。希望共享使用匿名链接的用户必须从共享菜单中选择此选项。<br/>  <br>详细信息：[外部共享概述 （英文)](https://support.office.com/article/c8a462eb-0723-4b0b-8d0a-70feafe4be85) <br/> |
   
SharePoint 管理中心和 OneDrive for Business 管理中心包括相同的设置。在任一管理中心设置适用于两者。
  
## <a name="configure-settings-in-azure-active-directory"></a>在 Azure Active Directory 中配置设置

请务必访问 Azure Active Directory 完成租户范围设置为更安全的环境中这两个区域。
  
### <a name="configure-named-locations-under-conditional-access"></a>配置命名的位置 （在下条件访问）

如果您的组织包括安全网络访问的办公室，为命名位置向 Azure Active Directory 添加受信任的 IP 地址范围。此功能可帮助减少报告误报登录风险事件数。 
  
请参阅： [Azure Active Directory 中的命名位置](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)
  
### <a name="block-apps-that-dont-support-modern-authentication"></a>阻止应用程序不支持现代身份验证

多重身份验证需要支持现代身份验证的应用程序。不支持现代的身份验证的应用程序不能被使用条件访问规则。
  
安全环境，请务必禁用不支持现代身份验证的应用程序的身份验证。您可以这样做 Azure Active Directory 中与即将提供的控件。
  
同时，使用以下方法之一来完成此有关 SharePoint Online 和 OneDrive for Business:
  
- 使用 PowerShell，请参阅[阻止应用程序不使用现代身份验证](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication)。
    
- 在 SharePoint 管理中心中将此配置，在"设备访问页 —"控制从不使用现代身份验证的应用程序的访问"。选择阻止。 
    
## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>入门云应用程序安全性或 Office 365 云应用程序安全性

使用 Office 365 云应用程序安全性评估风险，到通知可疑的活动，并自动执行操作。需要 Office 365 E5 计划。
  
或者，使用 Microsoft 云应用程序安全性获取偶数后被授予访问权限更深入地介绍可见性、 全面控件和改进的保护所有云应用程序，包括 Office 365。 
  
由于此解决方案建议 EMS E5 计划，我们建议您开始与云应用程序安全性，以便您可以使用此与其他 saas 与应用程序在您的环境中。开始与默认策略和设置。
  
详细信息：
  
- [部署 Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
    
- [有关 Microsoft Cloud App Security 的更多信息](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security)
    
- [Office 365 云应用安全概述](office-365-cas-overview.md)
    
![Cloud App Security 仪表板](media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)
  
## <a name="additional-resources"></a>其他资源

这些文章和指南提供了保护您的 Office 365 环境的其他规定性的信息：
  
- [政治市场活动、 盈利和其他敏捷组织的 Microsoft 安全指南](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)（您可以在任何环境中，尤其是仅使用云的环境中使用这些建议） 
    
- [推荐安全策略和配置标识和设备](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-365-policies-configurations)（这些建议包含 AD FS 环境帮助） 
    

