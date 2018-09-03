---
title: Office 365 高级威胁保护的视图报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 了解如何查找和使用适用于 Office 365 高级威胁保护安全中报告&amp;合规性中心。
ms.openlocfilehash: 13b2a4c142a223a8a912c9017b6033b0b5a1548b
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782109"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 高级威胁保护的视图报告

如果您的组织具有[Office 365 高级威胁保护](office-365-atp.md)(ATP)，并且您所需的权限，可以使用中安全性的几个 ATP 报表&amp;合规性中心。(请转到**报告** \> **仪表板**。)
  
![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
ATP 报告包括威胁保护状态报告、 ATP 文件类型报表和 ATP 消息处置报告。本文介绍 ATP 报告，并包括指向其他报告以查看。
  
## <a name="threat-protection-status-report"></a>威胁保护状态报告

**威胁保护状态**报告是融合恶意内容和恶意邮件检测和阻止的 Exchange Online 和高级威胁保护信息的单个视图。该报告提供聚合带有反恶意软件引擎、[零时差自动清除 (ZAP)](zero-hour-auto-purge.md)，请和高级威胁保护功能，如[ATP 安全链接](atp-safe-links.md)， [ATP 阻止恶意内容 （文件或 Url） 的唯一电子邮件数安全附件](atp-safe-attachments.md)，和[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)。
  
若要查看安全威胁保护状态报告，&amp;合规性中心中，转到**报告** \> **仪表板** \> **威胁保护状态**。
  
![ATP 威胁保护状态报告](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
获取一天，悬停在此图详细的状态。
  
![一天的 ATP 威胁保护状态数据](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
默认情况下威胁保护状态报告将显示数据的过去七天。但是，您可以选择**筛选器**，并更改要查看最多为 90 天的数据的日期范围。 
  
![ATP 威胁保护状态筛选器](media/4f703369-642b-402b-9758-b9c828283410.png)
  
您还可以使用**通过查看数据**菜单更改报表中显示的信息。 
  
![查看 ATP 威胁保护状态报表选项](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>ATP 文件类型报告

**ATP 文件类型**报告将显示为恶意检测到[ATP 安全附件](atp-safe-attachments.md)的文件的类型。
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **ATP 文件类型**。
  
![ATP 文件类型报告](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
当鼠标悬停在某一天时，您可以看到通过[ATP 安全附件](atp-safe-attachments.md)检测到的恶意文件类型的细分结构和[反垃圾邮件&amp;Office 365 中的反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
![一天的 ATP 文件类型报告数据](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>ATP 消息处置报告

**ATP 消息处置**报告将显示您的电子邮件被检测为具有恶意内容所采取的操作。 
  
若要查看此报告中，安全中&amp;合规性中心中，转到**报告** \> **仪表板** \> **ATP 消息处置**。
  
![ATP 邮件处置报告](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
当鼠标悬停在图表中的栏时，您可以看到的这一天为检测到的电子邮件执行哪些操作。
  
![ATP 消息处置报告一天的数据](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>若要查看的其他报告

除了本文中所述的 ATP 报告，[电子邮件安全报告](view-email-security-reports.md)可安全&amp;合规性中心。电子邮件安全报告包括[前发件人和收件人报告](view-email-security-reports.md#top-senders-and-recipients-report)、[欺骗邮件报告](view-email-security-reports.md#spoof-mail-report)、[垃圾邮件检测报告](view-email-security-reports.md#spam-detections-report)，等等。
  
如果您的组织具有[Office 365 威胁智能](office-365-ti.md)，也可以[使用资源管理器中的安全中&amp;合规性中心](use-explorer-in-security-and-compliance.md)。
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>查看这些报告需要哪些权限？

为了查看和使用本文中所述的电子邮件安全报告，您必须具有安全中分配相应角色&amp;合规性中心和 Exchange Admin Center。
  
|**角色组**|**其中分配**|**了解更多**|
|:-----|:-----|:-----|
| 以下各项之一：  <br/>  组织管理  <br/>  Security Administrator  <br/>  安全读者  <br/> |安全&amp;合规性中心  <br/> |[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md) <br/> |
| 以下各项之一：  <br/>  组织管理  <br/>  仅查看组织管理  <br/>  仅查看收件人角色  <br/>  遵从性管理  <br/> |Exchange 管理中心  <br/> |[Exchange Online 中的功能权限](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果报表不显示数据？

如果您不会在报表中看到数据，请仔细检查您的策略设置正确。您的组织必须[ATP 安全链接策略](set-up-atp-safe-links-policies.md)和[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)ATP 保护的订单中定义，以准备就绪。另请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](anti-spam-and-anti-malware-protection.md)。
  
## <a name="related-topics"></a>相关主题

[报告和 Office 365 安全性见解&amp;合规性中心](reports-and-insights-in-security-and-compliance.md)
  
[在安全中创建报表的计划&amp;合规性中心](create-a-schedule-for-a-report.md)
  
[设置和下载安全中的自定义报表&amp;合规性中心](set-up-and-download-a-custom-report.md)
  

