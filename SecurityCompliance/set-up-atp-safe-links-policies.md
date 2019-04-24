---
title: 设置 Office 365 ATP 安全链接策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/26/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 设置安全链接策略以保护您的组织免受 Word、Excel、PowerPoint 和 Visio 文件以及电子邮件中的恶意链接。
ms.openlocfilehash: d02866b7ab9a4da30a14aa0c55a42935926e99e3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32267051"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>设置 Office 365 ATP 安全链接策略

> [!IMPORTANT]
> 本文适用于 Office 365 企业客户。 如果您使用的是 Outlook.com、office 365 家庭版或 office 365 个人版, 并且您正在查找有关 Outlook 中的安全链接的信息, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。

[ATP 安全链接](atp-safe-links.md)是[Office 365 高级威胁防护](office-365-atp.md)(ATP) 的一项功能, 可帮助保护您的组织免受网络钓鱼和其他攻击中使用的恶意链接。 如果您拥有[Office 365 安全&amp;合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限, 则可以设置 ATP 安全链接策略, 以帮助确保当用户单击 "web 地址" (url) 时, 您的组织受到保护。 您的 ATP 安全链接策略可以配置为扫描 Office 文档中的电子邮件和 url 中的 url。
  
[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。 添加新功能时, 您可能需要对现有的 ATP 安全链接策略进行调整。

## <a name="what-to-do"></a>需执行的操作 
  
1. 查看先决条件。
    
2. 查看和编辑适用于每个人的默认 ATP 安全链接策略。 例如, 您可以[为 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。
    
3. 为特定的电子邮件收件人添加或编辑策略, 包括[设置 ATP 安全链接的自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。
    
4. 了解 ATP 安全链接策略选项 (在本文中), 包括最近更改的设置。
    
## <a name="step-1-review-the-prerequisites"></a>步骤 1: 查看先决条件

- 确保您的组织具有[Office 365 高级威胁防护](office-365-atp.md)。
    
- 请确保您具有必要的权限。 若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。 下表介绍了一些示例: <br>

    |Role  |分配的位置/方式  |
    |---------|---------|
    |Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。 (请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
    |Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
    |Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

    若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

- 请确保将 Office 客户端配置为使用[新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)(这适用于 office 文档中的 ATP 安全链接保护)。
    
- [了解 ATP 安全链接策略选项](#step-4-learn-about-atp-safe-links-policy-options)(在本文中)。 

- 最长允许30分钟, 新的或更新的策略将传播到所有的 Office 365 数据中心。
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a>步骤 2: 定义 (或查看) 适用于每个人的 ATP 安全链接策略

当您拥有[Office 365 高级威胁防护功能](office-365-atp.md)时, 将拥有适用于组织中每个人的默认 ATP 安全链接策略。 请务必查看, 如果需要, 请编辑您的默认策略。
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。 
    
2. 在左侧导航中的 "**威胁管理**" 下, 选择 "**策略\> ** **安全链接**"。
    
3. 在 "**适用于整个组织的策略**" 部分, 选择 "**默认**", 然后选择 "**编辑**" ("编辑" 按钮类似于铅笔)。<br/>![单击 "编辑" 编辑安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在 "**阻止以下 url** " 部分中, 指定要阻止组织中的用户访问的一个或多个 url。 (请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。)
    
5. 在 "**应用于除电子邮件以外的内容的设置**" 部分, 选择 (或清除) 要使用的选项。 (我们建议您选择所有选项。) 
    
6. 选择“**保存**”。
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a>步骤 3: 添加 (或编辑) 适用于特定电子邮件收件人的 ATP 安全链接策略

在查看 (或编辑) 适用于每个人的默认 ATP 安全链接策略之后, 下一步是定义适用于特定收件人的其他策略。 例如, 您可以通过定义其他策略来指定您的默认策略的例外。 
  
1. 转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。 
    
2. 在左侧导航中的 "**威胁管理**" 下, 选择 "**策略**"。
    
3. 选择 "**安全链接**"。
    
4. 在 "**适用于特定收件人的策略**" 部分, 选择 "**新建**" ("新建" 按钮类似**+** 于 "加号" ())。<br/>![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定策略的名称、说明和设置。<br/>**示例:** 若要设置一个名为 "无直接单击" 的策略, 且不允许组织中特定组中的用户在没有 ATP 安全链接保护的情况下单击特定网站, 可以指定以下推荐设置: 
    
  - 在 "**名称**" 框中, 键入 "无直接单击"。
    
  - 在 "**说明**" 框中, 键入一个说明 (如), 以防止某些组中的用户在没有 ATP 安全链接验证的情况下单击到网站。
    
  - 在 "**选择操作**" 部分, 选择 **"启用"**。
    
  - 选择 "**使用安全附件扫描可下载的内容**"。
    
  - 如果此选项可用, 请选择 "**将安全链接应用于在组织内发送的邮件"**。
    
  - 选择 **"不允许用户单击到原始 URL"**。
    
  - (这是可选的)在 "**不重写以下 url"** 部分, 指定一个或多个被视为对您的组织而言是安全的 url。 (请参阅[设置自定义 "不重写" url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))
    
  - 在 "**应用**于" 部分中, 选择 **"收件人是其成员**", 然后选择要包括在策略中的组。 选择 "**添加**", 然后选择 **"确定"**。
    
6. 选择“**保存**”。
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a>步骤 4: 了解 ATP 安全链接策略选项

在设置或编辑 ATP 安全链接策略时, 将看到几个可用选项。 如果您想知道这些选项是什么, 下表介绍了每一个选项及其效果。 请注意, 有两种主要的 ATP 安全链接策略可供定义或编辑:
- 适用于每个人的[默认策略](#default-policy-options);并  
- [针对特定收件人的其他策略](#policies-that-apply-to-specific-email-recipients) 

### <a name="default-policy-options"></a>默认策略选项

默认策略选项适用于组织中的所有人。

|此选项  |执行的操作  |
|---------|---------|
| **阻止以下 url** <br/>    | 允许您的组织具有自动阻止的自定义 url 的自定义列表。 当用户单击此列表中的某个 URL 时, 将会看到一个[警告页面](atp-safe-links-warning-pages.md), 说明为什么阻止了该 url。 若要了解详细信息, 请参阅[使用 Office 365 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。 |
| **office 365 专业增强版、适用于 iOS 和 Android 的 office** <br/>    | 如果选择此选项, 则将 ATP 安全链接保护应用于 windows 或 Mac OS 上的 Word、Excel 和 PowerPoint 文件中的 url、iOS 上的 Office 文档、Windows 上的 Visio 2016 和 Office Online (Word Online、PowerPoint online、Excel Online和 OneNote Online) (如果用户已登录到 Office 365)。 |
| **在用户单击 ATP 安全链接时不进行跟踪** <br/>  | 选择此选项后, 将不存储在 Word、Excel、PowerPoint 和 Visio 文档中的 url 的数据。  <br/> |
|**不要让用户点击到原始 URL 的 ATP 安全链接** <br/> |选择此选项后, 用户将无法继续处理被确定为恶意的 URL 之后的[警告页](atp-safe-links-warning-pages.md)。  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a>适用于特定电子邮件收件人的策略

|此选项  |执行的操作  |
|---------|---------|
|**关** <br/> |不扫描电子邮件中的 url。  <br/> 使您能够定义例外规则, 如不扫描电子邮件中的 url 的特定收件人组的 url 的规则。  <br/> |
|**On** <br/> |通过在用户单击电子邮件中的 url 时, 通过 ATP 安全链接保护来重写 url 以路由用户。  <br/> 对被阻止或恶意 url 的列表单击时检查 URL。  <br/> |
|**使用安全附件扫描可下载的内容** <br/> |如果选择此选项, 则会扫描指向可下载内容的 url。  <br/> |
|**将安全链接应用于在组织内发送的邮件** <br/> | 当此选项可用并选中时, 如果电子邮件帐户托管在 Office 365 中, 则会将 ATP 安全链接保护应用于在组织中的人员之间发送的电子邮件。  <br/> |
|**不跟踪用户点击** <br/> |选择此选项后, 请单击 "来自外部发件人的电子邮件中的 url 数据未存储"。 URL 单击 "跟踪" 以查找在组织内发送的电子邮件中的链接当前不受支持。  <br/> |
|**不允许用户单击到原始 URL** <br/> |选择此选项后, 用户将无法继续处理被确定为恶意的 URL 之后的[警告页](atp-safe-links-warning-pages.md)。  <br/> |
|**不重写以下 url** <br/> |将 url 保留为。 保留自定义不需要在组织中对特定电子邮件收件人组进行扫描的安全 url 列表。  有关更多详细信息 (包括对通配符星号 (\*) 支持的最新更改), 请参阅[设置自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。  <br/> |
   
## <a name="next-steps"></a>后续步骤

在 ATP 安全链接策略准备就绪后, 您可以通过查看报告了解 atp 在 orgnization 中的工作原理。 若要了解详细信息, 请参阅以下资源:

- [查看 Office 365 高级威胁防护报告](view-reports-for-atp.md)

- [在安全&amp;合规中心中使用资源管理器](use-explorer-in-security-and-compliance.md)

继续在新功能的前面提供 ATP。 访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)并了解要[添加到 ATP 的新功能](office-365-atp.md#new-features-in-office-365-atp)。