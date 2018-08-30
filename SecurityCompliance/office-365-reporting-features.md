---
title: Office 365 报告功能
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
description: 报告 Office 365 中的功能的说明。
ms.openlocfilehash: 5a448089de5d517b81551269416c4a6f91599725
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525991"
---
# <a name="office-365-reporting-features"></a>Office 365 报告功能 

## <a name="introduction"></a>简介
Office 365 中的报告功能提供了多种审核报告的 Azure Active Directory (AD)，Exchange Online 中，设备管理、 监督审阅和数据丢失防护 (DLP)。这些是不同且相互独立的 Office 365 活动报告。

## <a name="office-365-reports-dashboard"></a>Office 365 报告仪表板
Office 365 管理中心预览中的报告仪表板显示跨 Office 365 使用率活动。Office 365 全局管理员或 Exchange Online、 SharePoint Online，或 Skype 业务管理员可以获取粒度深入了解该服务的使用情况。报告可提供见解如使用特定的 Office 365 服务和 Office Professional Plus 多少邮件流过组织已激活的用户数量的用户数。报表上次 7、 30、 90，和 180 天才可用。

可以使用以下报表：
- [电子邮件活动报告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Email-activity-1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44)
- [Microsoft Office 激活报告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--Microsoft-Office-activations-87c24ae2-82e0-4d1e-be01-c3bcc3f18c60)
- [SharePoint Online 网站使用率报告](https://support.office.com/article/Office-365-Reports-in-the-admin-center-preview--SharePoint-site-usage-4ecfb843-e5d5-464d-8bf6-7ed512a9b213)
- [OneDrive for Business 使用情况报告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Preview--OneDrive-for-Business-usage-0de3b312-c4e8-4e4b-a02d-32b2f726a680)
- [Yammer 活动报告](https://support.office.com/article/View-the-Yammer-Activity-report-in-the-Office-365-admin-center-preview-c7c9f938-5b8e-4d52-b1a2-c7c32cb2312a)
- [Skype 的业务活动报告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/activity-report)
- [Skype 的业务-对等活动报告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/peer-to-peer-activity-report)
- [Skype 业务会议组织者报告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-organizer-activity-report)
- [Skype 的业务会议参与者活动报告](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online-reporting/conference-participant-activity-report)

有关详细信息，请参阅[Office 365 管理中心中的活动报告](https://support.office.com/article/activity-reports-in-the-office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)。


## <a name="azure-active-directory-reports"></a>Azure Active Directory 报告
Office 365 使用 Azure AD 身份验证和标识管理。Office 365 管理员可以使用 Azure 生成的报告以查找异常活动和到他们的数据未经授权的访问。您可以使用 Azure AD 中访问和使用报表深入了解的完整性和贵组织的目录的安全性。使用此信息，管理员可以更好地确定可能的安全风险可能是，以便他们可以充分规划以缓解这些风险。

Azure AD 报告可以导出到 Microsoft Excel，并可以与 Office 365 中，从其他数据，例如搜索结果的审核日志，提供洞察访问、 身份验证以及应用程序级别的活动关联起来。当启用 Azure AD Premium，高级的异常和资源使用率报告才可用。这些高级有助于提高组织的安全状况和帮助组织响应通过利用有关设备访问和应用程序使用情况分析的潜在威胁的报告。有关详细信息，请参阅[Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/reports-monitoring/overview-reports/)。

## <a name="exchange-online-audit-reports"></a>Exchange Online 审核报告
Exchange Online 审核报告包含邮箱访问和对组织的 Exchange Online 租户管理员所做更改的详细信息。启用邮箱审核后，您可以使用下表中的任务来运行报表和导出 Exchange Online 审核日志。

>**注意**： 您必须启用邮箱审核日志记录每个邮箱，以便审核的事件都保存在该邮箱的审核日志。如果邮箱审核日志记录不为邮箱启用的该邮箱的事件不会保存在审核日志，并且不会出现在邮箱审核报告。有关详细信息，请参阅[启用邮箱审核](https://support.office.com/article/Enable-mailbox-auditing-in-Office-365-aaca8987-5b62-458b-9882-c28476a66918)。

| 任务 | 描述 |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [运行非所有者邮箱访问报告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report) | 显示已访问的邮箱所有者以外的任何人的邮箱的列表。该报告包含有关谁访问邮箱的信息，在邮箱中何时采取的操作和操作是否已成功完成。 |
| [导出邮箱审核日志](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs) | 邮箱审核日志包含在访问和操作执行邮箱所有者以外的用户邮箱中的信息。管理员可以指定邮箱以及日期范围以生成报表。日志在 XML 中导出、 附加到邮件并发送给管理员确定的特定用户。 |
| [运行管理员角色组报告](https://docs.microsoft.com/Office365/SecurityCompliance/eop/run-an-administrator-role-group-report-in-eop-eop) | 管理员角色组用于向用户分配管理特权。这些权限允许用户执行管理任务，如重置密码、 创建或修改邮箱，并将管理权限分配给其他用户。管理角色组报告显示向角色组，包括添加或删除成员的更改。 |
| [查看管理员审核日志](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-administrator-audit-log) | 创建所有，管理员审核日志报告列表更新和删除由 Exchange Online 中的管理员执行的功能。日志条目提供有关运行的 cmdlet、 使用哪些参数、 用户运行此 cmdlet，和哪些对象已受影响的信息。 |
| [邮箱内容搜索和保留](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) | 邮箱上提供任何更改就地电子数据展示或就地保留设置的详细的信息。 |
| [导出管理员审核日志](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/search-role-group-changes) | 管理员审核日志记录管理的特定操作如创建、 更新和删除在 Exchange Online。日志的结果导出到 XML 和管理员可以选择将此日志发送到用户组。 |
| [运行每个邮箱的诉讼保留报告](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/per-mailbox-litigation-hold-report) | 提供对诉讼的任何更改的详细信息保留邮箱上的设置。 |
| [查看并导出外部管理审核日志](https://docs.microsoft.com/exchange/security-and-compliance/exchange-auditing-reports/view-external-admin-audit-log) | 包含由外部管理员执行的操作的详细信息。项提供的 cmdlet 是运行、 使用哪些参数和任何操作的创建、 修改或删除 Exchange Online 中的对象的信息。 |

## <a name="device-compliance-reports"></a>设备合规性报告
您可以管理和安全的移动设备，当他们使用 Office 365 移动设备管理 (MDM) 连接到 Office 365 组织。移动设备，如智能手机和平板电脑的用于访问工作电子邮件、 日历、 联系人和文档播放中确保员工能够随时随地工作和从任何位置的重要部分。因此，很关键您保护组织的信息。设置设备安全策略和访问规则，以及他们正在丢失或被盗擦除移动设备，您可以使用 Office 365 MDM。

MDM 合规性报告提供保护访问 Office 365 数据的移动设备而由组织设置的策略的概述。报告允许通过合规性状态、 报告的冲突、 阻止的设备和由于安全策略之前已多少设备的设备的筛选。有关详细信息，请参阅[概述的移动设备管理 Office 365](https://support.office.com/article/Overview-of-Mobile-Device-Management-for-Office-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a)。

## <a name="data-loss-prevention"></a>数据丢失防护
DLP 策略帮助管理安全性和组织中的信息流。您可以设置策略，以阻止访问内容、 加密数据，或通知的策略和策略违反行为使用应用程序中 DLP 策略提示用户。DLP 报告提供深入的策略和规则匹配、 重写和误报数。

在 Office 365 管理中心可用于查看有关您的 DLP 策略图形的图表或表格格式中检测到的消息数的信息。具体而言，DLP 策略匹配发送和接收邮件，并发送和接收邮件的 DLP 规则匹配。您还可以使用 Exchange 管理中心过去 24 小时内查看数匹配、 重写和误报为每个策略。但是，此数据不是可用图表。如果您下载在 Excel 中使用的报表，您可以查看更多详细信息，如谁在哪一天上, 发送的邮件，和哪些策略匹配触发。有关详细信息，请参阅[查看有关 DLP 策略检测报告](https://technet.microsoft.com/en-us/library/jj889415(v=exchg.150).aspx)。

## <a name="auditing-in-yammer-enterprise"></a>Yammer Enterprise 中的审核功能
Yammer Enterprise 为管理员提供从其 Yammer 网络通过[Yammer 数据导出 API](https://support.office.com/article/export-data-from-yammer-enterprise-b303d8f3-007d-4ad4-81f8-54fb1ecfb3f2)，或手动 Yammer 网络管理员页上通过导出用户活动数据的能力。限制为在 Yammer 中的网络管理员导出日志的功能。（所有的 Office 365 全局管理员是 Yammer 网络管理员）。

可以导出的以下数据：

| Filename | 描述 |
|----------------------------|-------------------------------------------------------------------------|
| Users.csv | 网络中的所有新，挂起的和已挂起的用户 |
| Messages.csv | 网络中的所有邮件 |
| Files.csv （元数据） | 元数据文件名，例如文件 API URL，格式为上载器 ID，在上载等。 |
| Files.csv （原始文件） | 已由用户上载到 Yammer 的原始文件的 zip 文件 |
| Topics.csv | 在网络上创建的主题 |
| Pages.csv | 通过网络中的用户创建的页面 （注释） |
| Admins.csv | 所有已验证网络上的管理员 |
| Networks.csv | 所有 Yammer 外部网络 |

*表 3-Yammer 网络数据文件可用于客户的导出*

Yammer 企业数据也是通过 Office 365 活动报告提供的。此外，Yammer 主动数据通过使用上公开其他日志记录，通过 Office 365 管理活动 API，且原因能够使用 Power BI。有关这些功能，请参阅[Office 路线图](https://fasttrack.microsoft.com/roadmap?filters=yammer)的详细信息。
