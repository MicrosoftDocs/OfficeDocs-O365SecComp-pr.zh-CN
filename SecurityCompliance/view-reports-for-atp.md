---
title: 查看 Office 365 高级威胁防护报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 了解如何在安全&amp;合规中心中查找和使用适用于 Office 365 高级威胁防护的报告。
ms.openlocfilehash: 6bf8c3222b0ce4cecd1b14f407f7e9ee42783a75
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408397"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>查看 Office 365 高级威胁防护报告

如果您的组织具有[Office 365 高级威胁防护](office-365-atp.md)(ATP), 并且您具有[必要的权限](#what-permissions-are-needed-to-view-the-atp-reports), 则可以在安全&amp;合规中心中使用多个 ATP 报告。 (转到 "**报表** \> "**仪表板**。)
  
![安全&amp;合规中心仪表板可帮助您了解高级威胁防护的工作情况](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 报告包括以下内容:
- [威胁防护状态报告](#threat-protection-status-report)
- [ATP 文件类型报告](#atp-file-types-report)
- [ATP 邮件处置报告](#atp-message-disposition-report)
- [实时检测或资源管理器](threat-explorer.md)(取决于您是否拥有 OFFICE 365 ATP 计划1或 2)
- ...[等等](#additional-reports-to-view)。 

阅读本文, 了解有关 ATP 报告以及如何使用它们的概述。
  
## <a name="threat-protection-status-report"></a>威胁防护状态报告

**威胁防护状态**报告是一个视图, 它将有关检测到的恶意内容和恶意电子邮件的信息, 以及[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和 Office 365 ATP () 和[Office ATP](office-365-atp.md)结合在一起。 此报告可用于查看一段时间内的检测 (最多90天), 并使安全管理员能够确定趋势或确定策略是否需要调整。 

威胁防护状态报告提供了包含恶意内容的独特电子邮件的聚合计数, 如反恶意软件引擎阻止的文件或网站地址 (Url)、[零小时自动清除 (ZAP)](zero-hour-auto-purge.md)和 ATP 功能 (如[Atp 安全链接](atp-safe-links.md)、 [atp 安全附件](atp-safe-attachments.md)和[atp 反网络钓鱼功能](atp-anti-phishing.md)。 

> [!NOTE]
> 拥有[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) 的客户可以使用威胁防护状态报告;但是, 在 ATP 客户的威胁防护状态报告中显示的信息可能包含不同的 EOP 客户可能看到的数据。 例如, ATP 客户的威胁防护状态报告将包含有关[在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到的恶意文件](atp-for-spo-odb-and-teams.md)的信息。 此类信息特定于 ATP, 因此具有 EOP 但不是 ATP 的客户将不会在其威胁防护状态报告中看到这些详细信息。
  
若要查看威胁防护状态报告, 请在[安全&amp;合规性中心](https://protection.office.com)中转到 "**报告** \> "**仪表板** \> **威胁防护状态**。
  
![ATP 威胁防护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
若要获取一天的详细状态, 请将鼠标悬停在关系图上。
  
![一天的 ATP 威胁防护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
默认情况下, 威胁防护状态报告显示过去七天的数据。 不过, 您可以选择 "**筛选器**" 并将日期范围更改为查看最多90天的数据。 (如果使用的是试用订阅, 则可能限制为30天的数据。)
  
![ATP 威胁防护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
您还可以使用 "**查看数据依据**" 菜单来更改报表中显示的信息。 
  
![查看 ATP 威胁保护状态报告的选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP 文件类型报告

**Atp 文件类型**报告显示通过[ATP 安全附件](atp-safe-attachments.md)检测为恶意的文件类型。
  
若要查看此报告, 请[在&amp;安全合规性中心](https://protection.office.com)中, 转到 "**报告** \> "**仪表板** \> **ATP 文件类型**。
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
当您将鼠标悬停在特定的一天时, 您可以看到由 Office 365 中的[ATP 安全附件](atp-safe-attachments.md)和[ &amp;反垃圾邮件反恶意软件保护](anti-spam-and-anti-malware-protection.md)检测到的恶意文件的类型细目。
  
![ATP 文件类型报告一天的数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 邮件处置报告

**ATP 邮件处置**报告将向您显示检测为包含恶意内容的电子邮件所采取的操作。 
  
若要查看此报告, 请[在&amp;安全合规性中心](https://protection.office.com)中, 转到 "**报告** \> "**仪表板** \> **ATP 邮件处置**。
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
当您将鼠标悬停在图表中的某条上时, 可以看到在那天中对检测到的电子邮件执行了哪些操作。
  
![一天的 ATP 邮件处置报告数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>要查看的其他报告

除了本文中介绍的 ATP 报告之外, 还有几个其他报告可供使用, 如下表所述:

|报告  |详细信息  |
|---------|---------|
|**浏览器**或**实时检测**(Office 365 ATP 计划2客户拥有资源管理器;Office 365 ATP 计划1客户具有实时检测。| [威胁浏览器 (和实时检测)](threat-explorer.md)       |
|**电子邮件安全报告**, 如主要发件人和收件人报告、欺骗邮件报告和垃圾邮件检测报告。 | [查看安全&amp;合规性中心中的电子邮件安全报告](view-email-security-reports.md)        |
|**ATP 安全链接 URL 跟踪**(这是使用 PowerShell 生成的报告。)此报告显示过去七 (7) 天的 ATP 安全链接操作的结果。 |[UrlTrace cmdlet 参考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|**EOP 和 ATP 结果**(这是使用 PowerShell 生成的自定义报表)。 此报告包含域、日期、事件类型、方向、操作和邮件计数等信息。  | [MailTrafficATPReport cmdlet 参考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EOP 和 ATP 检测**(这是使用 PowerShell 生成的自定义报表)。 此报告包含有关电子邮件或文件中的恶意文件或 Url、网络钓鱼企图、模拟和其他潜在威胁的详细信息。   | [MailDetailATPReport cmdlet 参考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>查看 ATP 报告所需的权限是什么？

为了查看和使用本文中介绍的报告,**必须为安全&amp;合规中心和 Exchange 管理中心分配适当的角色**。

- 对于安全&amp;合规中心, 您必须具有以下分配的角色之一:
    - 组织管理
    - 安全管理员 (可在 Azure Active Directory 管理中心中分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - 安全读者

- 对于 Exchange Online, 必须在 Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet 中分配以下角色之一 (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 组织管理
    - 仅限查看组织管理
    - “仅供查看收件人”角色
    - 合规性管理

若要了解详细信息, 请参阅以下资源:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果报告不显示数据, 该怎么办？

如果您未在 ATP 报告中看到数据, 请仔细检查您的策略设置是否正确。 您的组织必须定义[Atp 安全链接策略](set-up-atp-safe-links-policies.md)和[atp 安全附件策略](set-up-atp-safe-attachments-policies.md), 以便将 ATP 保护设置到位。 另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相关主题

[Office 365 安全&amp;合规中心中的报告和见解](reports-and-insights-in-security-and-compliance.md)
  
[在安全&amp;合规中心中创建报表的日程安排](create-a-schedule-for-a-report.md)
  
[在安全&amp;合规中心中设置和下载自定义报告](set-up-and-download-a-custom-report.md)
  

