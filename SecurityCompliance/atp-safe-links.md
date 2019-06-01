---
title: Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: "\"安全链接\" 功能可提供对 Office 文档中的超链接和电子邮件中的超链接的单击时间验证。 使用安全链接保护组织免受网络钓鱼和其他攻击的攻击。"
ms.openlocfilehash: 1be7db8ad96a5fd0b46500288e674946e763385a
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652525"
---
# <a name="office-365-atp-safe-links"></a>Office 365 ATP 安全链接

## <a name="overview-of-office-365-atp-safe-links"></a>Office 365 ATP 安全链接概述

> [!IMPORTANT]
> 本文适用于具有[Office 365 高级威胁防护](office-365-atp.md)的商业客户。 如果您使用的是 Outlook.com、Office 365 家庭版或 Office 365 个人版, 并且您正在查找有关 Outlook 中的安全链接的信息, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

Office 365 ATP 安全链接 ([高级威胁防护](office-365-atp.md)的一部分) 通过在[电子邮件](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email)和[Office 文档](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)中提供 web 地址 (url) 的验证时间, 可帮助保护您的组织。 通过由 Office 365 安全团队设置的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)定义保护。
  
在 ATP 安全链接策略准备就绪后, Office 365 全局管理员、安全管理员和安全读者可以[查看高级威胁防护报告](view-reports-for-atp.md)。 这些报告中的信息可帮助您的安全小组采取进一步的措施来保护您的组织或研究安全事件。

在将[新功能添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)时, Office 365 安全团队可以添加或编辑组织的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。 此外, 您可能会注意到更改和改进, 如我们在 Outlook 中新修订过的[警告页面](atp-safe-links-warning-pages.md)和本机链接呈现。
         
## <a name="how-to-get-atp-safe-links-protection"></a>如何获取 ATP 安全链接保护

**首先, 请确保你的订阅包括[高级威胁防护](office-365-atp.md)**。 在订阅中包含 ATP, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 企业版 E5、Office 365 教育版 A5 等。如果您的组织有一个不包含 Office 365 ATP 的 Office 365 订阅, 则可能会将 ATP 作为加载项进行购买。 有关详细信息，请参阅以下资源： 

- [Office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 
  
**接下来, 请确保已定义 ATP 安全链接策略**。 (请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。)ATP 安全链接功能在以下情况中处于活动状态:
  
- ATP 安全链接策略是为电子邮件和 Office 文档设置的。 (请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。)

- 将 office 365 客户端应用配置为使用新式验证 (这适用于 Office 文档中的 ATP 安全链接保护)。 (请参阅[适用于 Office 2016 的新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。) 
    
- 用户使用其工作或学校帐户登录到 Office 365。 (请参阅[登录到 office 或 office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)
    
- 您的组织的电子邮件通过 Exchange Online Protection。  

**此外, 请确保您具有必要的权限**。 若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。 下表介绍了一些示例:

|Role  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。 (请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>如何确保已准备好 ATP 安全链接保护

作为全局管理员或安全管理员, 请务必定期查看[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。 ATP 安全链接策略确定保护是否仅适用于电子邮件中的超链接或 Office 文档中的 Url。

在 ATP 安全链接策略准备就绪后, 贵组织的安全团队可以参阅查看[高级威胁防护的报告](view-reports-for-atp.md), 了解你的组织的 ATP 安全链接保护的工作原理。 

## <a name="example-scenarios"></a>示例场景
  
下表介绍了一些示例方案, 其中可能存在或可能未实施 ATP 安全链接保护。 (在所有这些情况下, 我们假定组织拥有 Office 365 企业版 E5。
  
|**示例方案**|**在这种情况下 ATP 安全链接保护是否适用？**|
|:-----|:-----|
|Jean 是具有 ATP 安全链接策略的组的成员, 其中包含电子邮件和 Office 文档中的 Url。 Jean 打开某人发送的 PowerPoint 演示文稿, 然后单击演示文稿中的 URL。  <br/> |是。 定义的 ATP 安全链接策略适用于 Jean 的 group、Jean 的电子邮件以及 Jean 打开的 Word、Excel、PowerPoint 或 Visio 文档, 只要 Jean 已登录并使用 Windows、iOS 或 Android 设备上的 Office 365 专业增强版。  <br/> |
|在 Chris 的组织中, 没有任何全局或安全管理员尚未定义任何 ATP 安全链接策略。 Chris 收到一个电子邮件, 其中包含指向恶意网站的 URL。 丽丽不知道 URL 是恶意的并单击链接。  <br/> |否。 包含组织中每个人的 Url 的默认策略必须进行定义, 以便保护生效。  <br/> |
|在 Pat 的组织中, 没有任何全局或安全管理员尚未定义或编辑任何 ATP 安全链接策略。 Pat 打开 Word 文档并单击文件中的 URL。  <br/> |否。 必须定义包含 Office 文档的策略, 才能就地保护。 请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。  <br/> |
|先生/她的组织具有一个列入 "已`http://tailspintoys.com`阻止" 网站的 ATP 安全链接策略。 先生/她收到一封包含的 URL 的`http://tailspintoys.com/aboutus/trythispage`电子邮件。 先生单击 URL。  <br/> |这取决于整个网站及其所有子页是否包含在阻止的 Url 列表中。 请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。  <br/> |
|晓明 (Jean 的同事) 向 Jean 发送电子邮件, 而不知道该电子邮件包含恶意 URL。  <br/> |这取决于是否为在组织内发送的电子邮件定义 ATP 安全链接策略。 请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。  <br/> |


  

