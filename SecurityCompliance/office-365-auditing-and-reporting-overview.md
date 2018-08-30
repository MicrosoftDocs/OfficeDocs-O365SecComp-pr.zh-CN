---
title: Office 365 中的审核与报告
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 审核和报告中为服务保证或 Office 365 功能的概述。
ms.openlocfilehash: 055a24523260bf14220d5436dcdd010f31f5d8cd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525682"
---
# <a name="auditing-and-reporting-in-office-365"></a>Office 365 中的审核与报告

## <a name="introduction"></a>简介
Microsoft 云服务包括几审核和报告客户可用于跟踪用户和管理活动中其租户，如对其 Exchange Online 和 SharePoint Online 租户配置设置，所做更改的功能和用户对文档和其他项目所做更改。客户可以使用的审核信息和云服务中可用的报告更有效地管理的用户体验、 缓解风险和履行法规遵从性要求。

## <a name="office-365-security--compliance-center"></a>Office 365 安全与合规中心
[Office 365 安全性和合规性中心](https://support.office.com/article/Go-to-the-Office-365-Security-Compliance-Center-7e696a40-b86b-4a20-afcc-559218b7b1b8)是用于保护 Office 365 中的数据的一站式门户，并包括许多审核和报告功能。它是 Office 365 合规中心的发展。安全性和合规性中心专为具有数据的组织保护或合规性需求，或想要审核用户和管理员的活动。您可以使用安全性和合规性中心管理法规遵从性的所有组织的 Office 365 数据。您可以访问安全性和合规性中心，网址为[http://protection.office.com](http://protection.office.com/)使用 Office 365 管理员帐户。

安全性和合规性中心包括访问多个功能为您提供的导航窗格：
- **通知**-可以管理通知、 查看与安全相关的警报，以及管理使用[高级安全管理](https://support.office.com/article/overview-of-office-365-cloud-app-security-81f0ee9a-9645-45ab-ba56-de9cbccab475)的高级的通知。 
- **权限**-使您能够[分配权限](https://support.office.com/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76)如合规性管理员、 电子数据展示经理和其他人向您的组织中的人员，以便他们可以在 [安全性和合规性中心执行任务。您可以分配权限的大多数功能中的安全性和合规性中心，但必须使用 Exchange 管理中心和 SharePoint 管理中心来配置其他权限。
- **威胁管理**-使您能够创建和应用设备使用[Office 365 移动设备管理](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)，可以设置为贵组织配置电子邮件筛选的[数据丢失防护](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)(DLP) 策略的管理策略反恶意软件、 域密钥标识邮件 (DKIM)、 安全附件、 安全链接和应用程序权限。
- **数据调控**-允许您[导入电子邮件或其他系统到 Office 365 中的 SharePoint 数据](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84)，[配置存档邮箱](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)，并设置电子邮件和贵组织中的其他内容的[保留策略](https://support.office.com/article/Retention-in-the-Office-365-Security-Compliance-Center-2a0fc432-f18c-45aa-a539-30ab035c608c)。
- **搜索和调查**-提供了[内容搜索](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a)、[审核日志](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)、 隔离和[电子数据展示案例管理](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da)工具，可以快速深入跨 Exchange Online 邮箱、 组和 SharePoint 的公用文件夹的活动联机和 OneDrive for Business。
- **报表**-可以快速访问[报告](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a)的 SharePoint Online、 OneDrive for Business、 Exchange Online 和 Azure AD。
- **服务保证**-提供有关 Microsoft 如何维护安全、 隐私和合规性全球标准的 Office 365、 Azure、 Microsoft Dynamics CRM Online、 Microsoft Intune 和其他云服务的信息。此外包括对第三方 ISO、 SOC，和其他审核报告，以及审核控件，它提供有关各种控件已测试和验证 Office 365 的第三方审核员的详细信息的访问。

## <a name="service-assurance"></a>服务保证
我们很多客户管控行业中受到广泛的合规性要求。若要执行自己的风险评估，客户通常需要有关 Office 365 如何维护的安全性和隐私其数据的详细信息。Microsoft 致力到的安全性和隐私其云服务中的客户数据和获取客户信任通过提供其操作，并轻松地访问独立的兼容性报告和评估的透明视图。

服务保证提供透明度操作和有关 Microsoft 如何维护安全、 隐私和 Office 365 中的客户数据的合规性的信息。它包括白皮书、 常见问题解答和其他资料库以及 Office 365 主题，例如数据加密、 数据恢复能力、 安全事件管理和上的第三方审核报告。客户可以使用此信息来执行自己的法规风险评估。合规部主管可以分配要授予用户访问服务保证的"服务保证 User"角色。租户管理员还可以提供外部用户，例如独立 auditors 有权通过[Microsoft 云服务信任门户](http://aka.ms/STP)(STP) 服务保证仪表板中的信息。有关如何访问 STP 的详细信息，请访问[入门服务信任门户的 Office 365 业务、 Azure 和 Dynamics CRM Online 订阅](http://aka.ms/STPHelp)。

## <a name="onedrive-for-business-admin-center"></a>OneDrive for Business Admin Center
在新的 Microsoft OneDrive 管理中心可帮助您快速和轻松地管理组织的 OneDrive for Business 设置在一个位置。若要使用 OneDrive 管理中心，您必须允许访问 onedrive.com。您还必须是您的组织，全局管理员或自定义管理与 SharePoint 管理员角色。访问 OneDrive for Business admin center 预览在[https://admin.onedrive.com](https://admin.onedrive.com/)。

关键功能包括为管理员提供链接到的 Office 365 安全性和合规性中心的主要方案，如搜索审核日志、 使用 DLP、 保留和电子数据展示，和警报的合规性区域。

## <a name="related-links"></a>相关的链接
- [电子数据展示和搜索功能](office-365-ediscovery-and-search-features.md)
- [Office 365 报告功能](office-365-reporting-features.md)
- [Office 365 管理活动 API](office-365-management-activity-api.md)
- [Office 365 邮箱迁移](office-365-mailbox-migrations.md)
- [Office 365 工程部的内部日志记录](office-365-internal-logging.md)