---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全附件、 防钓鱼的高级的功能和威胁智能。
ms.openlocfilehash: 4899073247f4b39e7cda39f8f35544c436c0b2d7
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995213"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 高级威胁防护

> [!IMPORTANT]
> 本文适用于企业客户。如果您是家庭用户查找有关在 Outlook 中的安全链接的信息，请参阅[高级 Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

## <a name="overview-of-office-365-advanced-threat-protection"></a>Office 365 的高级的威胁保护的概述

Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：
  
- 带[ATP 安全附件](atp-safe-attachments.md)的恶意软件扫描电子邮件附件
    
- 扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)
    
- 识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件
    
- 检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件
    
- 检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
    
**通过 Office 365 ATP 保护由您组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略**。务必定义策略，并进行定期查看和修改这些策略，以使其保持最新和要执行的新功能添加到服务的优点。 

[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。这些报告还可以显示您可能需要以查看并更新您的策略的区域。然后，如果您有标记为恶意软件不应是，或文件您希望 Microsoft 要检查的文件，可以[将文件提交给 Microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。

## <a name="new-features-are-continually-being-added-to-atp"></a>到 ATP 不断添加了新功能

我们将继续向 Office 365 中，添加新功能，并包含 ATP。下面是一些新功能，其中一些调用 ATP 策略必须经过审核和更新的列表。若要了解有关至此 ATP （或 Microsoft 365 一般） 的新功能的详细信息，请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。


|功能更新  |拟办事项  |
|---------|---------|
|开始在年 2 月 2019年和推出通过下的几个月，威胁智能功能被添加到 ATP。此外，如果您的组织当前不具有 ATP，您必须考虑，新选项包括 ATP 计划 1 和 ATP 计划 2。若要了解详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 |查看您的组织订阅，如果需要[购买或编辑加载项](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)。  |
|开始在年 10 月 2018年以及推出通过下的几个月，当人员使用的 Outlook 或 Outlook Web 应用程序 (OWA)、 ATP 安全链接不呈现原始 Url 重写 Url。（我们调用此本机链接呈现）。<br>适用于您的组织本机链接呈现后，此功能将工作 Outlook 365 （单击以运行） 和 OWA 中。|无         |
|年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。 |无         |
|开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。   |[查看和编辑 ATP 安全链接策略](set-up-atp-safe-links-policies.md)  |
|开始在后期年 5 月 2018 安全中[隔离](quarantine-email-messages.md)功能&amp;合规性中心将正在扩展到[的 SharePoint Online 的 OneDrive for Business 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。 |[查看和编辑 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md) |
|从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。 |[查看和编辑 ATP 安全链接策略](set-up-atp-safe-links-policies.md) |
|从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。  |请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |


      
## <a name="get-office-365-atp"></a>获取 Office 365 ATP

Office 365 ATP 包含订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 业务](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5，和 Office 365 教育版 A5 中。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

## <a name="define-policies-for-atp"></a>为 ATP 定义策略

若要定义 （或编辑） ATP 策略，您必须为分配下表中所述的角色之一：

|角色  |其中/如何分配  |
|---------|---------|
|Office 365 全局管理员 |注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。         |
|Security Administrator |Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要了解有关角色和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。

有几种 ATP 策略用于定义和定期查看。

1. **[设置 Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的显示为来自受信任的人员或域。 

2. **[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
3. **[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)** 和从多个选项，如[动态交付和预览过程](dynamic-delivery-and-previewing.md)中进行选择。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>请参阅 ATP 通过查看报告的工作方式

ATP 策略后，报告是可用于显示如何服务运行正常。(在 Office 365 安全性 & 合规性中心中，转到**报告** > **仪表板**。)

[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 为 Office 365 全局管理员、 安全管理员或安全读取器，转到[https://protection.office.com](https://protection.office.com)和登录。
    
2. 转到**报告** > **仪表板**。（若要获取这些报告的帮助，请参阅[View reports 高级威胁 protection](view-reports-for-atp.md)。）
    
3. 如果需要对进行调整您的安全策略。若要获取与此帮助，请参阅以下资源：
      - [Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)
      - [Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)
      - [Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>可疑将文件提交给 Microsoft 进行分析

- 如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。

- 如果您要获取想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），请使用[报告消息加载项](enable-the-report-message-add-in.md)。 
  

