---
title: Office 365 高级威胁保护的视图报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection: M365-security-compliance
description: 了解如何查找和使用适用于 Office 365 高级威胁保护安全中报告&amp;合规性中心。
ms.openlocfilehash: a27fdf6c7d04a2526873047d4e2a33bb283878b3
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995223"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 高级威胁保护的视图报告

如果您的组织具有[Office 365 高级威胁保护](office-365-atp.md)(ATP)，并且您[所需的权限](#what-permissions-are-needed-to-view-these-reports)，可以使用中安全性的几个 ATP 报表&amp;合规性中心。(请转到**报告** \> **仪表板**。)
  
![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 报告包括[威胁保护状态报告](#threat-protection-status-report)、 [ATP 文件类型报告](#atp-file-types-report)和[ATP 消息处置报告](#atp-message-disposition-report)。本文介绍 ATP 报告，并包括指向[其他报告以查看](#additional-reports-to-view)。
  
## <a name="threat-protection-status-report"></a>威胁保护状态报告

**威胁保护状态**报告是融合信息恶意内容和恶意邮件检测和[Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) 和[Office 365 ATP](office-365-atp.md)被阻止的单个视图。该报告提供聚合带有反恶意软件引擎、[零时差自动清除 (ZAP)](zero-hour-auto-purge.md)，请和 ATP 功能，如[ATP 安全链接](atp-safe-links.md)， [ATP 安全阻止恶意内容 （文件或网站地址 (Url)） 的唯一电子邮件数附件](atp-safe-attachments.md)，和[ATP 防钓鱼功能](atp-anti-phishing.md)。

> [!NOTE]
> 威胁保护状态报告是适用于[Office 365 ATP](office-365-atp.md)或[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); 客户但是，ATP 客户威胁保护状态报告中显示的信息将可能包含比 EOP 客户可能会看到不同的数据。例如，ATP 客户的威胁保护状态报告将包含有关[SharePoint Online、 OneDrive 或的 Microsoft 团队中检测到恶意文件](atp-for-spo-odb-and-teams.md)的信息。此类信息是特定于 ATP，，因此客户拥有 EOP，但不是 ATP 将不会看到其威胁保护状态报告中的这些信息。
  
若要查看中威胁保护状态报告，[安全&amp;合规性中心](https://protection.office.com)，请转到**报告** \> **仪表板** \> **威胁保护状态**。
  
![ATP 威胁保护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
获取一天，悬停在此图详细的状态。
  
![一天的 ATP 威胁保护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
默认情况下威胁保护状态报告将显示数据的过去七天。但是，您可以选择**筛选器**，并更改要查看最多为 90 天的数据的日期范围。 
  
![ATP 威胁保护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
您还可以使用**通过查看数据**菜单更改报表中显示的信息。 
  
![查看 ATP 威胁保护状态报表选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP 文件类型报告

**ATP 文件类型**报告将显示为恶意检测到[ATP 安全附件](atp-safe-attachments.md)的文件的类型。
  
若要查看此报告中，在[安全&amp;合规性中心](https://protection.office.com)，请转到**报告** \> **仪表板** \> **ATP 文件类型**。
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
当鼠标悬停在某一天时，您可以看到通过[ATP 安全附件](atp-safe-attachments.md)检测到的恶意文件类型的细分结构和[反垃圾邮件&amp;Office 365 中的反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
![一天的 ATP 文件类型报告数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 消息处置报告

**ATP 消息处置**报告将显示您的电子邮件被检测为具有恶意内容所采取的操作。 
  
若要查看此报告中，在[安全&amp;合规性中心](https://protection.office.com)，请转到**报告** \> **仪表板** \> **ATP 消息处置**。
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
当鼠标悬停在图表中的栏时，您可以看到的这一天为检测到的电子邮件执行哪些操作。
  
![ATP 消息处置报告一天的数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>若要查看的其他报告

除了本文中所述的 ATP 报告，多个其他报表有下, 表中所述：

|报告类型  |了解详细信息  |
|---------|---------|
|**电子邮件安全报告**，如前发件人和收件人报告、 欺骗邮件报表和垃圾邮件检测报告。 | [查看安全中的电子邮件安全报告&amp;合规性中心](view-email-security-reports.md)        |
|**资源管理器**（也称为威胁资源管理器，这包含在[Office 365 威胁智能](office-365-ti.md)）     | [在安全中使用资源管理器&amp;合规性中心](use-explorer-in-security-and-compliance.md)        |
|**EOP 和 ATP 结果**（这是通过使用 PowerShell 生成自定义报告）。此报告包含信息，如域、 日期、 事件类型、 方向、 操作和消息计数。  | [Get MailTrafficATPReport cmdlet 参考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EOP 和 ATP 检测**（这是通过使用 PowerShell 生成自定义报告）。此报告包含有关恶意文件或 Url、 网络钓鱼尝试、 模拟，和电子邮件或文件中的其他潜在威胁的详细信息。   | [Get MailDetailATPReport cmdlet 参考](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>查看 ATP 报告需要哪些权限？

若要查看和使用在本文中所述的报告**您必须具有适当的角色分配这两个安全&amp;合规性中心和 Exchange Admin Center**。

- 安全&amp;合规性中心，您必须拥有以下角色分配之一：
    - 组织管理
    - 安全管理员 (这可以在 Azure Active Directory 管理中心分配 ([https://aad.portal.azure.com](https://aad.portal.azure.com))
    - 安全读者

- Exchange Online 中，您必须拥有以下角色分配 Exchange 管理员中心中之一 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - 组织管理
    - 仅限查看组织管理
    - “仅供查看收件人”角色
    - 合规性管理

若要了解详细信息，请参阅以下资源：

- [Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果报表不显示数据？

如果您看不到数据 ATP 报告中，请仔细检查您的策略设置正确。您的组织必须[ATP 安全链接策略](set-up-atp-safe-links-policies.md)和[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)ATP 保护的订单中定义，以准备就绪。另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相关主题

[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)
  
[在安全中创建报表的计划&amp;合规性中心](create-a-schedule-for-a-report.md)
  
[设置和下载安全中的自定义报表&amp;合规性中心](set-up-and-download-a-custom-report.md)
  

