---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/1/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全的附件和高级的防钓鱼功能。For Business 和 Microsoft 团队之前，还进行了高级的威胁保护扩展到 SharePoint Online、 OneDrive 中的文件。
ms.openlocfilehash: dbf604dfc6367ac225e57158e6b784952c081773
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525441"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 高级威胁防护

Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：
  
- 扫描[ATP 安全附件](atp-safe-attachments.md)的电子邮件的附件
    
- 扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)
    
- 识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件
    
- 检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件
    
- 检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
    
通过 Office 365 ATP 保护取决于组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略。[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。然后，可以[可疑将文件提交给 Microsoft 进行分析](office-365-atp.md#submitlalware)。
  
> [!IMPORTANT]
> Office 365 ATP 包含订阅，例如 Office 365 企业 E5 和 Office 365 教育版 A5，以及截止年 4 月 30 2018年还[Microsoft 365 业务安全功能](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc)。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁 Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx)。 
      
## <a name="get-office-365-atp"></a>获取 Office 365 ATP

1. 作为全局或安全管理员，请转到[https://portal.office.com](https://portal.office.com)和使用 Office 365 您工作或学校的帐户登录。 
    
2. 选择**管理** \> **帐单**以查看您的当前订阅所包含的内容。 
    
    ![以全局管理员身份，登录在 portal.office.com 并转到管理\>帐单](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)
  
3. 如果您看到**Office 365 企业 E5**、 **Office 365 教育版 A5**或**Microsoft 365 企业版**，然后您的组织具有 ATP。 
    
    如果您看到其他订阅，例如**Office 365 企业版 E3**或**Office 365 企业版 E1**，请考虑添加 ATP。为此，请选择 **+ 添加订阅**。
    
ATP 后下, 一步是为您的安全团队定义的[安全链接](atp-safe-links.md)、[安全的附件](atp-safe-attachments.md)和[防钓鱼](set-up-atp-anti-phishing-policies.md)保护策略。 
  
[要执行什么操作？](office-365-atp.md#TOC)
  
## <a name="define-policies-for-atp"></a>为 ATP 定义策略

- **[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
- **[Office 365 中的策略设置 ATP 安全附件](set-up-atp-safe-attachments-policies.md)** 中可以包含[动态传递以及预览](dynamic-delivery-and-previewing.md)
    
- **[设置 Office 365 中的 ATP 防钓鱼策略](set-up-atp-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的状态显示为来自受信任的人员或域 
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>请参阅 ATP 通过查看报告的工作方式

ATP 策略后，报告是可用于显示如何服务运行正常。

[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 请确保您是 Office 365 全局管理员、 安全管理员或安全读取器。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)
    
2. [高级威胁保护和 Exchange Online Protection 查看报告](view-reports-for-atp.md)。
    
3. 如果需要对进行调整您的安全策略。请参阅以下资源：
    
  - [Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)
    
  - [Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
    
  - [Office 365 中的 ATP 防钓鱼策略](set-up-atp-anti-phishing-policies.md)
    
[要执行什么操作？](office-365-atp.md)
  
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>可疑将文件提交给 Microsoft 进行分析

如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。
  
## <a name="related-topics"></a>相关主题

[Office 365 安全性概述&amp;合规性中心](https://support.office.com/article/a5f2fd18-b029-4257-b5a8-ae83e7768c85)
  
[查看高级威胁保护报告](view-reports-for-atp.md)
  
[威胁管理 Office 365 安全性&amp;合规性中心](threat-management.md)
  

