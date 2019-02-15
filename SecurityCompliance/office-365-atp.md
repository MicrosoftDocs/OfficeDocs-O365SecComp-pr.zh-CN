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
description: Office 365 高级威胁防护包括欺骗情报、安全链接、安全附件、高级反钓鱼功能和威胁情报。
ms.openlocfilehash: d78b37ca048187a298b6e083b54ad68b949638ef
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051173"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 高级威胁防护

## <a name="overview-of-office-365-advanced-threat-protection"></a>Office 365 高级威胁防护概述

> [!IMPORTANT]
> 本文适用于商业客户。如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

Office 365 高级威胁防护 (ATP) 通过以下方式帮助保护您的组织免受恶意攻击:
  
- 使用[ATP 安全附件](atp-safe-attachments.md)扫描电子邮件附件中的恶意软件
    
- 使用[ATP 安全链接](atp-safe-links.md)扫描电子邮件和 Office 文档中的 web 地址 (url)
    
- 使用[适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)识别和阻止在线库中的恶意文件
    
- 使用[欺骗智能](learn-about-spoof-intelligence.md)检查电子邮件, 以获取未经授权的欺骗
    
- 当有人尝试使用[Office 365 中的 ATP 反钓鱼功能](atp-anti-phishing.md)模拟你的用户和你的组织的自定义域时进行检测
    
**通过 Office 365 ATP 进行保护取决于您的组织的安全团队为安全链接、安全附件和反网络钓鱼定义的策略**。定义策略并定期查看和修订这些策略以使其保持最新并充分利用添加到服务中的新功能, 这一点非常重要。 

[报告可](view-reports-for-atp.md)用于显示 ATP 在您的组织中的工作原理。这些报告还可以向你显示可能需要查看和更新策略的领域。而且, 如果您的文件不应被标记为恶意软件, 或者您希望 Microsoft 检查的文件, 则可以[将文件提交到 microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。

## <a name="new-features-are-continually-being-added-to-atp"></a>将新功能连续添加到 ATP

我们将继续向 Office 365 添加新功能, 其中包括 ATP。下面列出了几个新功能, 其中一些是用于检查和更新 ATP 策略的。若要了解有关即将 ATP (或常规 microsoft 365) 的新功能的详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。


|功能更新  |交办事项  |
|---------|---------|
|从2019年2月开始, 在接下来的几个月中推出, 将威胁智能功能添加到 ATP。此外, 如果您的组织当前没有 ATP, 您将具有要考虑的新选项, 包括 atp 计划1和 atp 计划2。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 |查看组织的订阅, 如果需要, 请[购买或编辑加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。  |
|从10月2018开始, 在接下来的几个月中开始, 当用户使用 outlook 或 Outlook Web 应用程序 (OWA) 时, ATP 安全链接将呈现原始 url, 而不是重写的 url。(我们称之为本机链接呈现。)<br>当您的组织提供本机链接呈现时, 此功能将在 Outlook 365 (即点即用) 和 OWA 中运行。|无         |
|从9月2018日起开始, [Office 365 ATP 警告页面](atp-safe-links-warning-pages.md)可提供新的配色方案、更多详细信息和继续转到网站的功能, 尽管有警告和建议。 |无         |
|从2018的下半年开始, 将 ATP 安全链接保护扩展为适用于 office Online (Word Online、Excel Online、PowerPoint online 和 OneNote online) 中的 url 和 Mac 上的 office 365 专业增强版。   |[查看和编辑 ATP 安全链接策略](set-up-atp-safe-links-policies.md)  |
|从后期开始可能为 2018 [](quarantine-email-messages.md) , 安全&amp;合规中心中的隔离功能将扩展到[SharePoint Online、OneDrive for business 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。 |[查看和编辑 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md) |
|从2018年3月起, 将对 ATP 安全链接保护进行扩展, 以应用于在组织内的人员之间发送的电子邮件。 |[查看和编辑 ATP 安全链接策略](set-up-atp-safe-links-policies.md) |
|2006年10月2017日开始, 将 ATP 安全链接保护扩展为应用于电子邮件中的 url 以及 office 365 专业增强版文档 (如 Word、Excel、PowerPoint 和 Visio on Windows) 中的 url, 以及 iOS 和 Android 设备上的 office 应用。  |确保您正在使用[Office 的新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) |

## <a name="get-office-365-atp"></a>获取 Office 365 ATP

Office 365 ATP 包含在订阅中, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 企业版 E5 和 office 365 教育版 A5。如果您的组织有一个不包含 office 365 ATP 的 office 365 订阅, 则可能会将 ATP 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

## <a name="define-policies-for-atp"></a>为 ATP 定义策略

若要定义 (或编辑) ATP 策略, 您必须分配下表中所述的角色之一:

|角色  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> 若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

有几种 ATP 策略可供定义和定期查看。

1. **[在 Office 365 中设置 ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)**, 包括基于模拟的攻击, 以防止发出似乎来自受信任人或域的电子邮件的攻击者。 

2. **[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)**, 包括组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
3. **[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**, 并从多个选项 (例如[动态传递和预览](dynamic-delivery-and-previewing.md)) 中进行选择。
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a>查看报表查看 ATP 的工作原理

在 ATP 策略准备就绪后, 报告可用于显示服务的工作方式。(在 "Office 365 安全 & 合规中心" 中, 转到 "**报告** > "**仪表板**。)

[![安全&amp;合规中心仪表板可帮助您了解高级威胁防护的工作情况](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)
  
1. 作为 Office 365 全局管理员、安全管理员或安全阅读者, 请转到[https://protection.office.com](https://protection.office.com)并登录。
    
2. 转到 "**报表** > "**仪表板**。(若要获取有关这些报告的帮助, 请参阅[查看高级威胁防护的报告](view-reports-for-atp.md)。)
    
3. 如果需要, 请对安全策略进行调整。若要获取有关此方面的帮助, 请参阅以下资源:
    - [ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)
    - [ATP 安全链接策略](set-up-atp-safe-links-policies.md)
    - [ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a>将可疑文件提交给 Microsoft 进行分析

- 如果您收到怀疑可能是恶意软件的文件, 则可以将该文件提交给 Microsoft 进行分析。访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。

- 如果你收到一封要提交给 Microsoft 进行分析的电子邮件 (带有或不带附件), 请使用[报告邮件加载项](enable-the-report-message-add-in.md)。 
  

