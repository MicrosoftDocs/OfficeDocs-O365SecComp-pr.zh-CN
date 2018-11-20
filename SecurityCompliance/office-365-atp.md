---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全的附件和高级的防钓鱼功能。For Business 和 Microsoft 团队之前，还进行了高级的威胁保护扩展到 SharePoint Online、 OneDrive 中的文件。
ms.openlocfilehash: 1e6a2dc16bf5fb8dbf1b242a3495d8fb87cfda1c
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238474"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 高级威胁防护

## <a name="overview"></a>概述

Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：
  
- 带[ATP 安全附件](atp-safe-attachments.md)的恶意软件扫描电子邮件附件
    
- 扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)
    
- 识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件
    
- 检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件
    
- 检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
    
**通过 Office 365 ATP 保护由您组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略**。非常重要定期查看和修改您的策略，以使其保持最新和要执行的新功能添加到服务的优点。[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。这些报告还可以显示您可能需要以查看并更新您的策略的区域。然后，如果您有标记为恶意软件不应是，或文件您希望 Microsoft 要检查的文件，可以[将文件提交给 Microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。

## <a name="new-features-are-continually-being-added-to-atp"></a>到 ATP 不断添加了新功能

我们将继续向 Office 365 中，添加新功能，并包含 ATP。下面是一些新功能，其中一些调用 ATP 策略必须经过审核和更新的列表。若要了解有关至此 ATP （或 Microsoft 365 一般） 的新功能的详细信息，请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。
  
- 从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。（请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。）
    
- 从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）

- 开始在后期年 5 月 2018 安全中[隔离](quarantine-email-messages.md)功能&amp;合规性中心将正在扩展到[的 SharePoint Online 的 OneDrive for Business 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。
 
- 开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）

- 年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。 
 
- 开始在年 10 月 2018年以及推出通过下的几个月，当用户正在使用 Outlook Web 应用程序 (OWA) 或 Outlook、 ATP 安全链接不呈现原始 Url 重写 Url。（我们调用此本机链接可见性）。

      
## <a name="get-office-365-atp"></a>获取 Office 365 ATP

> [!IMPORTANT]
> Office 365 ATP 包含订阅，如 Microsoft 365 企业版、 Office 365 企业 E5、 Office 365 教育版 A5，和[Microsoft 365 企业版](https://docs.microsoft.com/en-us/microsoft-365/business/security-features)中。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

1. 作为全局或安全管理员，请转到[https://portal.office.com](https://portal.office.com)和使用 Office 365 您工作或学校的帐户登录。 
    
2. 选择**管理** \> **帐单**以查看您的当前订阅所包含的内容。 <br/>![以全局管理员身份，登录在 portal.office.com 并转到管理\>帐单](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. 如果您看到**Office 365 企业 E5**、 **Office 365 教育版 A5**或**Microsoft 365 企业版**，然后您的组织具有 ATP。 <br/>如果您看到其他订阅，例如**Office 365 企业版 E3**或**Office 365 企业版 E1**，请考虑添加 ATP。为此，请选择 **+ 添加订阅**。
    
ATP 后下, 一步是为您的安全团队定义策略。 
  
## <a name="define-policies-for-atp"></a>为 ATP 定义策略

- **[设置 Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的状态显示为来自受信任的人员或域 

- **[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
- **[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)** 可以包括[动态交付和预览](dynamic-delivery-and-previewing.md)
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>请参阅 ATP 通过查看报告的工作方式

ATP 策略后，报告是可用于显示如何服务运行正常。

[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 请确保您是 Office 365 全局管理员、 安全管理员或安全读取器。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)
    
2. [查看报告的高级威胁保护](view-reports-for-atp.md)。
    
3. 如果需要对进行调整您的安全策略。请参阅以下资源：

  - [Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)
    
  - [Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)
    
  - [Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>可疑将文件提交给 Microsoft 进行分析

- 如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。

- 如果您要获取想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），请使用[报告消息加载项](enable-the-report-message-add-in.md)。 
  

