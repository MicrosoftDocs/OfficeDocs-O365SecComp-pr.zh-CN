---
title: Office 365 ATP 安全附件
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/17/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6e13311e-92ae-495e-a619-56d770199170
ms.collection:
- M365-security-compliance
description: "\"安全附件\" 功能可提供电子邮件附件的单击时间验证。 使用安全附件保护组织免受用户在电子邮件中发送或接收的恶意文件的攻击。"
ms.openlocfilehash: 9077a555ca7f753448b866ce26f6ff4af5a165bd
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598568"
---
# <a name="office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件

## <a name="overview-of-office-365-atp-safe-attachments"></a>Office 365 ATP 安全附件概述

ATP 安全附件 (和[ATP 安全链接](atp-safe-links.md)) 是[Office 365 高级威胁防护](office-365-atp.md)(ATP) 的一部分。 ATP 安全附件功能将检查电子邮件附件是否是恶意的, 然后采取措施保护您的组织。 ATP 安全附件功能可根据由 Office 365 全局或安全管理员设置的[ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)来保护您的组织。 
  
还可以将 ATP 保护扩展到 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件。 若要了解详细信息, 请参阅[适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 高级威胁防护](atp-for-spo-odb-and-teams.md)。
  
## <a name="how-to-get-atp-safe-attachments"></a>如何获取 ATP 安全附件

首先, 请确保你的订阅包括[高级威胁防护](office-365-atp.md)。 在订阅中包含 ATP, 如[microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 E5、Office 365 A5 等。如果您的组织有一个不包含 Office 365 ATP 的 Office 365 订阅, 则可能会将 ATP 作为加载项进行购买。 有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。 

接下来, 请确保定义了 ATP 安全附件策略。 (请参阅[设置 Office 365 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md))ATP 安全附件功能在以下情况中处于活动状态:
  
- 已设置 ATP 安全附件策略。 (请参阅[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)。)

- 用户使用其工作或学校帐户登录到 Office 365。 (请参阅[登录到 office 或 office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)

若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。 下表介绍了一些示例:

|Role  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。 (请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

## <a name="how-to-know-if-atp-safe-attachments-protection-is-in-place"></a>如何知道 ATP 安全附件保护是否已就绪

在您[定义 (或查看) ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)后, 通过[查看报告来查看高级威胁防护](view-reports-for-atp.md), 一种有效的方法是查看服务的工作方式。
  
下表介绍了一些示例方案。 在所有这些情况下, 我们假定组织拥有包含高级威胁防护的 Office 365 订阅。
  
|**示例方案**|**在这种情况下 ATP 安全附件保护是否适用？**|
|:-----|:-----|
|Pat 的组织具有 Office 365 E5, 但尚未为 ATP 安全附件定义任何策略。  <br/> |否。 虽然功能可用, 但必须至少定义一个 ATP 安全附件策略, 才能将 ATP 安全附件保护到位。  <br/> |
|先生为在 Contoso 的销售部门的员工。 先生/她的组织有一个仅适用于财务员工的 ATP 安全附件策略。  <br/> |否。 在这种情况下, 财务员工将具有 ATP 安全附件保护, 但在定义包含这些组的策略之前, 其他员工 (包括销售部门) 将不会。  <br/> |
|昨天, Jean 的组织中的 Office 365 管理员设置适用于所有员工的 ATP 安全附件策略。 在今天的早期, Jean 收到包含附件的电子邮件。  <br/> |是。 在此示例中, Jean 具有高级威胁防护的许可证, 并且已定义了包含 Jean 的 ATP 安全附件策略。 新策略通常需要30分钟的时间才能在数据中心内生效;由于在这种情况下已过一天, 因此该策略应有效。  <br/> |
|丽丽的组织有 Office 365 E5, 其中的 ATP 安全附件策略适用于组织中的所有人。 Chris 收到包含附件的电子邮件, 并将邮件转发给组织外部的其他人。  <br/> |对于 Chris 收到的邮件, ATP 安全附件保护已就绪。 如果收件人的组织还设置了 ATP 安全附件策略, 则 Chris 转发的邮件将在转发的邮件到达时服从这些策略。  <br/> |
|晓明的组织已准备好 ATP 安全附件策略, 并且已打开[SharePoint、OneDrive 和 Microsoft 团队的 atp](atp-for-spo-odb-and-teams.md) 。 晓明假定已扫描 SharePoint Online 中的每个文件, 并且可以安全地打开或下载。  <br/> |根据定义的策略, ATP 安全附件保护已就绪;但是, 这并不意味着会扫描 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的每个文件。 (若要了解详细信息, 请参阅[适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。)  <br/> |

## <a name="submitting-files-for-malware-analysis"></a>提交文件以进行恶意软件分析

- 如果您收到要请求 Microsoft 进行分析的文件, 请访问[提交文件以进行恶意软件分析](https://aka.ms/wdsi/submit)。

- 如果您收到一封要提交给 Microsoft 进行分析的电子邮件 (包含或不带附件), 请使用[报告消息外接程序](enable-the-report-message-add-in.md)。
