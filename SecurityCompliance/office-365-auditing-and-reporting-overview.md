---
title: Office 365 中的审核与报告
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 12/03/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
description: Office 365 中的审核和报告功能以及服务保证的概述。
ms.openlocfilehash: 0167239e854d9b96d9505f4264ada225804eef96
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30091034"
---
# <a name="auditing-and-reporting-in-office-365"></a>Office 365 中的审核与报告

## <a name="introduction"></a>简介
Microsoft 云服务包括几个审核和报告功能, 客户可以使用这些功能来跟踪其租户内的用户和管理活动, 如对 Exchange online 和 SharePoint online 租户配置设置所做的更改。以及用户对文档和其他项目所做的更改。客户可以使用云服务中提供的审核信息和报告更有效地管理用户体验、缓解风险并满足合规性义务。

## <a name="office-365-security--compliance-center"></a>Office 365 安全与合规中心
[office 365 Security & 合规性中心](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8)是一个用于保护 Office 365 中的数据的一站式门户, 其中包括许多审核和报告功能。这是 Office 365 合规性中心的演变。安全 & 合规性中心适用于具有数据保护或合规性需求的组织, 或者要审核用户和管理员活动的组织。您可以使用安全 & 合规性中心来管理组织的所有 Office 365 数据的合规性。您可以[http://protection.office.com](http://protection.office.com/)使用 Office 365 管理员帐户访问安全 & 合规性中心。

Security & 合规性中心包含导航窗格, 可提供对多个功能的访问权限:
- **警报**-使你能够管理警报、查看与安全相关的警报, 以及使用[Office 365 云应用安全](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/office-365-cas-overview)管理高级通知。 
- **权限**-使您能够向组织中的人员[分配权限](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76), 例如合规性管理员、电子数据展示管理器和其他人, 以便他们能够在安全 & 合规性中心执行任务。您可以为 Security & 合规中心中的大多数功能分配权限, 但必须使用 Exchange 管理中心和 SharePoint 管理中心配置其他权限。
- **威胁管理**-使您能够创建和应用使用[Office 365 移动设备管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)的设备管理策略、设置组织的[数据丢失防护](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) 策略、配置电子邮件筛选、反恶意软件、域密钥识别邮件 (DKIM)、安全附件、安全链接和 OAuth 应用。
- **数据管理**-使您能够[将其他系统中的电子邮件或 SharePoint 数据导入到 Office 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)中,[配置存档邮箱](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce), 并为电子邮件和组织中的其他内容设置[保留策略](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)。
- **搜索 & 调查**-提供[内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)、隔离和[电子数据展示案例管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)工具, 以快速深入了解 Exchange Online 邮箱、组和公用文件夹 (SharePoint) 之间的活动在线和 OneDrive for business。
- **报告**-使你能够快速访问 SharePoint Online、OneDrive for business、Exchange Online 和 Azure AD 的[报告](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)。
- **服务保证**-提供有关 Microsoft 如何为 Office 365、Azure、microsoft Dynamics CRM Online、microsoft Intune 和其他云服务等全球标准维护安全性、隐私和合规性的信息。此外, 还包括对第三方 ISO、SOC 和其他审核报告的访问权限, 以及已审核的控件, 这些控件提供有关已由 Office 365 的第三方审计员测试和验证的各种控件的详细信息。

## <a name="service-assurance"></a>服务保证
我们的管控行业中的许多客户都受广泛合规性要求的制约。若要执行自己的风险评估, 客户通常需要了解有关 Office 365 如何维护其数据的安全性和隐私的详细信息。Microsoft 致力于在其云服务中提供客户数据的安全和隐私, 并通过提供其操作的透明视图并轻松访问独立合规性报告和评估, 从而赢得客户信任。

服务保证提供了操作的透明性, 以及 Microsoft 如何在 Office 365 中维护客户数据的安全、隐私和合规性的相关信息。它包括第三方审核报告以及 Office 365 主题中的一库白皮书、faq 和其他材料, 例如数据加密、数据恢复、安全事件管理等。客户可以使用此信息来执行自己的法规风险评估。合规性监察官可以分配 "服务保证用户" 角色, 以向用户授予服务保证的访问权限。租户管理员还可以通过[Microsoft 云服务信任门户](http://aka.ms/STP)(STP) 为外部用户 (如独立审计员) 提供服务保证仪表板中的信息的访问权限。有关如何访问 STP 的详细信息, 请参阅[microsoft Office 365 for business、Azure 和 Dynamics CRM Online 订阅中的服务信任门户的服务信任门户入门](http://aka.ms/STPHelp)。

## <a name="onedrive-for-business-admin-center"></a>OneDrive for business 管理中心
新的 Microsoft OneDrive 管理中心可帮助你快速轻松地在一个位置管理组织的 OneDrive for business 设置。若要使用 OneDrive 管理中心, 您必须允许对 onedrive.com 的访问。您还必须是组织的全局管理员或具有 SharePoint 管理员角色的自定义管理员。访问上[https://admin.onedrive.com](https://admin.onedrive.com/)的 OneDrive for business 管理员中心预览。

主要功能包括一个合规性区域, 该区域为管理员提供了指向 Office 365 安全与合规中心的链接, 以实现关键方案 (如搜索审核日志、使用 DLP、保留、电子数据展示和警报)。

## <a name="related-links"></a>相关链接
- [电子数据展示和搜索功能](office-365-ediscovery-and-search-features.md)
- [Office 365 报告功能](office-365-reporting-features.md)
- [Office 365 管理活动 API](office-365-management-activity-api.md)
- [Office 365 邮箱迁移](office-365-mailbox-migrations.md)
- [Office 365 工程部的内部日志记录](office-365-internal-logging.md)