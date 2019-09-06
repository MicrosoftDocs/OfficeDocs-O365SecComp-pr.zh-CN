---
title: Office 365 高级威胁防护
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 03/28/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 高级威胁防护包括安全附件、安全链接、高级反钓鱼工具、报告工具和威胁智能功能。
ms.openlocfilehash: d9dda9b19f601e26d01a18f7602f4fae3e0a0cb4
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761718"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 高级威胁防护

> [!IMPORTANT]
> 本文适用于拥有 [Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的企业客户。 如果你使用的是 Outlook.com、Office 365 家庭版或 Office 365 个人版，并且正在查找有关 Outlook 中安全链接的信息，请参阅[高级 Outlook.com 安全](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="overview"></a>概述

Office 365 高级威胁防护 (ATP) 可保护你的组织免受电子邮件、链接 (URL) 和协作工具带来的恶意威胁。 ATP 包括：

- [威胁防护策略](#configure-atp-policies)：定义威胁防护策略，为组织设置适当级别的保护。 

- [报告](#view-atp-reports)：查看实时报告，监视组织中的 ATP 性能。 

- [威胁调查和响应功能](#use-threat-investigation-and-response-capabilities)：使用前沿工具调查、理解、模拟和阻止威胁。 

- [自动化调查和响应功能](#save-time-with-automated-investigation-and-response)：节省时间和精力来调查和缓解威胁。

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP 计划 1 和计划 2

ATP 包含在 Office 365 E5 中；但是，ATP 计划 1 和 ATP 计划 2 可各自用作特定订阅的加载项。 若要了解详细信息，请参阅[跨高级威胁防护 (ATP) 计划的功能可用性](https://docs.microsoft.com/zh-CN/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="configure-atp-policies"></a>配置 ATP 策略

Office 365 ATP 提供了大量工具，可为组织设置适当级别的保护。 

组织的安全团队必须在 Office 365 安全与合规中心中为每一个 ATP 工具定义策略。 转到“威胁管理”**** > “策略”**** 访问策略选项。 （若要获取有关此方面的帮助，请参阅[快速入门指南：设置 Office 365 高级威胁防护](checklist-atp-setup.md)。）

为组织定义的策略将确定预定义威胁的行为和保护级别。 策略选项非常灵活。 例如，组织的安全团队可以在用户、组织、收件人和域级别设置细化的威胁防护。 定期查看策略非常重要，因为每天都会出现新的威胁和挑战。  

- [ATP 安全附件](atp-safe-attachments.md)：提供可通过检查电子邮件附件查找恶意内容来保护邮件系统的零日防护。 它会将无病毒/恶意软件签名的所有邮件和附件路由到特殊环境，然后使用机器学习和分析技术检测恶意意向。 如果未找到可疑活动，邮件将转发到邮箱。 若要了解详细信息，请参阅[设置 Office 365 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。

- [ATP 安全链接](atp-safe-links.md)：在诸如电子邮件和 Office 文件中提供 URL 的单击时验证。 正在进行保护并适用于邮件和 Office 环境。 每次单击时都扫描链接：安全链接仍然可访问，恶意链接被动态阻止。 若要了解详细信息，请参阅[设置 Office 365 ATP 安全链接策略](https://docs.microsoft.com/zh-CN/office365/securitycompliance/set-up-atp-safe-links-policies)。 

- [适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)：当用户协作和共享文件时，可通过识别和阻止工作组网站和文档库中的恶意文件来保护你的组织。 有关详细信息，请参阅[开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。 

- [ATP 防钓鱼防护](atp-anti-phishing.md)：检测模拟用户和自定义域的尝试。 它应用机器学习模型和高级模仿检测算法，防止钓鱼攻击。 若要了解详细信息，请参阅[设置 Office 365 ATP 防钓鱼和防钓鱼策略](set-up-anti-phishing-policies.md)。

## <a name="view-atp-reports"></a>查看 ATP 报告

Office 365 ATP 包含用于监视 ATP 性能的高级[报告仪表板](view-reports-for-atp.md)。 可在安全与合规中心的**报告 > 仪表板**上访问该文件。 

实时更新报告，为你提供最新见解。 这些报告还提供建议并向你提醒即将面临的威胁。 预定义的报告包括以下内容： 

- [威胁资源管理器（或实时检测）](threat-explorer.md)

- [威胁防护状态](view-reports-for-atp.md#threat-protection-status-report)

- [ATP 文件类型报告](view-reports-for-atp.md#atp-file-types-report)

- [ATP 邮件处置报告](view-reports-for-atp.md#atp-message-disposition-report)

- ...等等。 

## <a name="use-threat-investigation-and-response-capabilities"></a>使用威胁调查和响应功能

Office 365 ATP 计划 2 包括同类最佳的[威胁调查和响应工具](office-365-ti.md)，可让组织的安全团队预测、理解和防范恶意攻击。 

- [威胁跟踪器](threat-trackers.md)提供有关主流网络安全问题的最新智能。 例如，你可以查看有关最新恶意软件的信息，并采取措施，然后将其作为组织的实际威胁。 可用的跟踪器包括[值得注意的跟踪器](threat-trackers.md#noteworthy-trackers)、[趋势跟踪器](threat-trackers.md#trending-trackers)、[跟踪的查询](threat-trackers.md#tracked-queries)和[已保存的查询](threat-trackers.md#saved-queries)。

- [威胁资源管理器（或实时检测）](threat-explorer.md)（也称为“资源管理器”）是一种实时报表，可用于识别和分析最近的威胁。 可配置资源管理器显示自定义期间的数据。

- [攻击仿真程序](attack-simulator.md)使你能够在组织中运行现实的攻击方案以确定漏洞。 可仿真当前类型的攻击，包括[显示名称鱼叉式网络钓鱼攻击](attack-simulator.md#display-name-spear-phishing-attack)、[密码喷涂攻击](attack-simulator.md#password-spray-attack)、 [强力密码攻击](attack-simulator.md#brute-force-password-attack)等等。
    
## <a name="save-time-with-automated-investigation-and-response"></a>节省自动调查和响应的时间

（**新增！**）调查可能的网络攻击时，时间至关重要。 越快地识别和缓解威胁，组织就越好。 Office 365 ATP 计划 2 现在将包括[自动化调查和响应 (AIR)](automated-investigation-response-office.md) 功能。 （如果尚无这些功能，则可以使用 ATP 计划 2 立即提供这些功能。）

AIR 包括一组可自动启动（例如触发预警时）或手动启动（例如从资源管理器中的视图启动）的安全手册。 AIR 可以有效且高效地节省安全操作团队缓解威胁的时间和精力。 若要了解详细信息，请参阅[使用 Office 365 实现自动化调查和响应 (AIR)](automated-investigation-response-office.md)。

## <a name="permissions-required-to-use-atp-features"></a>使用 ATP 功能所需的权限

若要访问安全与合规中心中的 ATP 功能，你必须分配有相应的角色。 下表提供一些示例：

|角色或角色组  |了解详细信息的资源  |
|---------|---------|
|Office 365 全局管理员 |[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|安全管理员 |[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/zh-CN/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 组织管理 |[Exchange Online 中的权限](https://docs.microsoft.com/zh-CN/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

有关详细信息，请参阅：

- [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md) 

- [向用户授予对安全与合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>获取 Office 365 ATP

Office 365 ATP 计划 2 包含在 Office 365 企业版 E5、Office 365 教育版 A5 和 Microsoft 365 商业版中。 如果你的订阅未包括 Office 365 ATP，则可以将 ATP 计划 1 或 ATP 计划 2 作为加载项附加到特定订阅进行购买。 若要了解详细信息，请参阅以下资源：

- 有关包含 ATP 计划的订阅的列表，请参阅 [Office 365 高级威胁防护 (ATP) 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)。

- 有关计划 1 和 2 中所含功能的列表，请参阅[高级威胁防护 (ATP) 计划中的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 请参阅[获得正确的 Office 365 高级威胁防护](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)，比较计划和购买 Office 365 ATP。

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP 中的新功能

向 Office 365 ATP 持续添加新功能。 若要了解详细信息，请参阅以下资源：

- [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供了开发和推出的新功能列表。

- [Office 365 高级威胁防护服务说明](https://docs.microsoft.com/zh-CN/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)介绍了 ATP 计划中的功能和可用性。
