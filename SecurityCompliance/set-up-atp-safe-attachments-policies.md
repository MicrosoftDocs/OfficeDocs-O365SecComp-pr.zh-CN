---
title: 设置 Office 365 ATP 安全附件策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 定义安全附件策略以保护您的组织免受电子邮件中的恶意文件的攻击。
ms.openlocfilehash: 532a4b6ab2d26506f10adb621a29718a32d52ff6
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652695"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>设置 Office 365 ATP 安全附件策略

> [!IMPORTANT]
> 本文适用于具有[Office 365 高级威胁防护](office-365-atp.md)的商业客户。 如果您是在 Outlook 中查找有关安全附件的信息的主用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

用户定期发送、接收和共享附件, 如文档、演示文稿、电子表格等。 只需查看一封电子邮件, 就能判断附件是安全还是恶意的, 并不总是容易。 您需要的最后一件事是您的组织的 wreaking havoc 的恶意附件。 幸运的是, [Office 365 高级威胁防护](office-365-atp.md)(ATP) 可能会有所帮助。 您可以设置[ATP 安全附件](atp-safe-attachments.md)策略, 以帮助确保组织免受不安全电子邮件附件的攻击。 
  
## <a name="what-to-do"></a>需执行的操作 
  
1. 查看先决条件
    
2. 设置 ATP 安全附件策略
    
3. 了解 ATP 安全附件策略选项
    
## <a name="step-1-review-the-prerequisites"></a>步骤 1: 查看先决条件

- 确保您的组织具有[Office 365 高级威胁防护](office-365-atp.md)。
    
- 请确保您具有必要的权限。 若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。 下表介绍了一些示例: <br>

    |Role  |分配的位置/方式  |
    |---------|---------|
    |Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。 (请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
    |Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
    
    若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- [了解 ATP 安全附件策略选项](#step-3-learn-about-atp-safe-attachments-policy-options)(在本文中)。 某些选项 (如 "监视器" 或 "替换" 选项) 可能会导致在扫描附件时出现电子邮件的轻微延迟。 若要避免邮件延迟, 请考虑使用[动态传递和预览](dynamic-delivery-and-previewing.md)。
    
- 最长允许30分钟, 新的或更新的策略将传播到所有的 Office 365 数据中心。
    
## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>步骤 2: 设置 (或编辑) ATP 安全附件策略
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。 
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下, 选择 "**策略** \> **安全附件**"。
    
3. 如果你发现**启用了 SharePoint、OneDrive 和 Microsoft 团队的 ATP**, 我们建议你选择此选项。 这将为 Office 365 环境启用[适用于 SharePoint、OneDrive 和 Microsoft 团队的 office 365 高级威胁防护](atp-for-spo-odb-and-teams.md)。 
    
4. 选择 "**新建**" ("新建" 按钮类似于**+** 加号 ()), 开始创建策略。
    
5. 指定策略的名称、说明和设置。<br/><br/>**示例:** 若要设置一个名为 "无延迟" 的策略, 该策略将立即传递所有人的邮件, 然后在扫描完附件后将附件, 您可以指定以下设置: 
    
      - 在 "**名称**" 框中, 键入 "无延迟"。
    
      - 在 "**说明**" 框中, 键入一个说明, 例如, 在扫描后立即传递邮件和将附件。
    
      - 在 "响应" 部分中, 选择 "**动态传递**" 选项。 ([了解有关使用 ATP 安全附件进行动态传递和预览的详细信息](dynamic-delivery-and-previewing.md)。)
    
      - 在 "**重定向附件**" 部分中, 选择 "启用重定向" 和 "键入将调查恶意附件的 Office 365 全局管理员、安全管理员或安全分析员的电子邮件地址" 选项。 
    
      - 在 "**应用**于" 部分中, 选择 **"收件人域**", 然后选择您的域。 选择 "**添加**", 然后选择 **"确定"**。
    
6. 选择“保存”****。
    
考虑为您的组织设置多个 ATP 安全附件策略。 这些策略将按其在**ATP 安全附件**页面上列出的顺序应用。 在定义或编辑策略之后, 至少需要30分钟才能使策略在整个 Microsoft 数据中心中生效。 
  
## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>步骤 3: 了解 ATP 安全附件策略选项

设置 ATP 安全附件策略时, 可以从多种选项 (包括监视器、阻止、替换、动态传递等) 中进行选择。 如果您想了解这些选项的功能, 下表总结了每个选项及其效果。
  
|**选项**|**Effect**|**在需要执行以下操作时使用:**|
|:-----|:-----|:-----|
|**关** <br/> |不扫描附件中的恶意软件  <br/> 不延迟邮件传递  <br/> |对内部发件人、扫描仪、传真或仅发送已知、良好附件的智能主机关闭扫描  <br/> 避免路由内部邮件中不必要的延迟  <br/> **对于大多数用户, 不建议使用此选项。它使您能够为一小组内部发件人关闭 ATP 安全附件扫描。**           |
|**监视器** <br/> |传递包含附件的邮件, 然后跟踪检测到的恶意软件所发生的情况  <br/> |查看检测到的恶意软件在您的组织中的位置  <br/> |
|**阻止** <br/> |阻止包含检测到的恶意软件附件的邮件继续  <br/> 将带有检测到的恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md), 安全管理员或分析师可以在其中查看并释放 (或删除) 这些邮件  <br/> 自动阻止将来的邮件和附件  <br/> |使用相同的恶意软件附件保护贵组织免受重复攻击  <br/> |
|**Replace** <br/> |删除检测到的恶意软件附件  <br/> 通知收件人已删除附件  <br/> 将带有检测到的恶意软件的邮件发送到[Office 365 中的隔离](manage-quarantined-messages-and-files.md), 安全管理员或分析师可以在其中查看并释放 (或删除) 这些邮件  <br/> |对收件人可见由于检测到的恶意软件, 附件已被删除  <br/> |
|**动态传递** <br/> |立即传递邮件  <br/> 在扫描完成之前将附件替换为占位符文件, 然后在未检测到恶意软件的情况下将附件。  <br/> 包括扫描过程中大多数 Pdf 和 Office 文件的附件预览功能  <br/> 将带有检测到的恶意软件的邮件发送到隔离, 安全管理员或分析师可以在其中查看并释放 (或删除) 这些邮件  <br/> [了解有关使用 ATP 安全附件的动态传递和预览](dynamic-delivery-and-previewing.md) <br/> |避免邮件延迟, 同时防止收件人受到恶意文件的攻击  <br/> 允许收件人在扫描发生时以安全模式预览附件  <br/> |
|**启用重定向** <br/> |当选择 "监视器"、"阻止" 或 "替换" 选项时应用  <br/> 将附件发送到安全管理员或分析师可以调查的指定电子邮件地址  <br/> |使安全管理员和分析师能够研究可疑附件  <br/> |
   
## <a name="next-steps"></a>后续步骤

在 ATP 安全附件策略准备就绪后, 您可以通过查看报告了解 ATP 是如何为您的组织工作的。 若要了解详细信息, 请参阅以下资源:
- [查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)
- [在安全&amp;合规中心中使用资源管理器](use-explorer-in-security-and-compliance.md)

继续在新功能的前面提供 ATP。 访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)并了解要[添加到 ATP 的新功能](office-365-atp.md#new-features-in-office-365-atp)。
 