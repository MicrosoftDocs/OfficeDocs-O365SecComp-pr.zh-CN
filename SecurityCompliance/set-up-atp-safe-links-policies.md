---
title: 设置 Office 365 ATP 安全链接策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: 设置以从 Word、 Excel、 PowerPoint 和 Visio 文件中以及电子邮件中的恶意链接保护您的组织的安全链接策略。
ms.openlocfilehash: 0f43cf1eec63df4b70f88abf36e8f097da72ebbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525842"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a>设置 Office 365 ATP 安全链接策略

[ATP 安全链接](atp-safe-links.md)， [Office 365 高级威胁保护](office-365-atp.md)(ATP) 的一项功能可帮助您的组织防止恶意欺诈和其他攻击中使用的链接。如果您有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)，您可以设置 ATP 安全链接策略以帮助确保当人员单击 web 地址 (Url) 时，保护您的组织。可以将 ATP 安全链接策略配置为扫描电子邮件中的 Url 和 Office 文档中的 Url。
  
不断到 ATP 安全链接添加了新功能：
  
- 在最晚年 10 月 2017，扩展 ATP 安全链接保护应用于为 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint Windows、 iOS 和 Android 设备和 Windows 上的 Visio 文件中的 Url 或电子邮件中的 Url。
    
- 从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织中的用户之间发送的电子邮件。
    
- 从开始后期年 3 月 2018年，ATP 安全链接保护扩展要应用于在 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus Mac 操作系统上的 Url。
    
- 从开始年 5 月 2018年，[警告页面](atp-safe-links-warning-pages.md)更新与新的配色方案、 更多详细信息，和以继续前进到而不考虑给定的建议的网站的功能。 

添加新功能时，您可能需要对您现有的 ATP 安全链接策略进行调整。

## <a name="what-to-do"></a>需执行的操作 
  
1. [查看先决条件](#review-the-prerequisites)
    
2. [定义可应用于所有人 ATP 安全链接策略](set-up-atp-safe-links-policies.md#reveddefaultscc)，包括[设置您的自定义阻止 Url 列表 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)
    
3. [添加特定的电子邮件收件人的策略](set-up-atp-safe-links-policies.md#addemailpolscc)，包括[设置您自定义"执行不重写"Url 列表 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
    
4. [了解 ATP 安全链接策略选项](set-up-atp-safe-links-policies.md#policyoptions)，包括的最新更改的设置
    
## <a name="review-the-prerequisites"></a>查看先决条件

- 请确保您的组织具有[Office 365 高级威胁保护](office-365-atp.md)。
    
- 请确保您具有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。
    
- [了解 ATP 安全链接策略选项](#learn-about-atp-safe-links-policy-options)（本文中）。 
    
- 允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。
    
## <a name="define-an-atp-safe-links-policy-that-applies-to-everyone"></a>定义适用于每个人的 ATP 安全链接策略

如果您有高级威胁保护 Office 365 企业版中，您将有 ATP 安全链接策略定义适用于您的组织中的每个人。您可以编辑您的策略任一安全中&amp;合规性中心或 Exchange 管理员中心。我们建议使用安全&amp;合规性中心以查看或编辑任何 ATP 策略。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 在左侧导航窗格中，**威胁管理**下面，选择**策略\>****安全的链接**。
    
3. 在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。 
    
    ![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. 在**阻止以下 Url**部分中，指定您想要阻止访问从组织中的人员的一个或多个 Url。（请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)）。
    
5. 在**设置，将应用于除电子邮件的内容**部分中，选中 （或清除） 您想要使用的选项。（我们建议您选择的所有选项。） 
    
6. 选择**保存**。
    
## <a name="add-a-policy-for-specific-email-recipients"></a>为特定的电子邮件收件人添加策略

已定义的所有用户的策略后，请考虑添加为特定的电子邮件收件人的组策略。这样，您可以指定为默认策略例外。您可以添加策略使用任一安全&amp;合规性中心 （推荐） 或 Exchange 管理员中心。我们建议使用安全&amp;合规性中心以查看或编辑任何 ATP 策略。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 在左侧导航窗格中，**威胁管理**下面，选择**策略**。
    
3. 选择**安全的链接**。
    
4. 在**的可以应用到特定收件人的策略**部分中，选择**新建**(新建按钮图像类似一个加号 ( **+**))。
    
    ![选择新建以添加特定的电子邮件收件人的安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. 指定策略的名称、说明和设置。
    
    **示例：** 若要设置名为"通过没有直接单击"不允许人员没有 ATP 安全链接保护的特定网站点阅贵组织中的特定组中的策略，您可以指定以下建议的设置： 
    
  - 在**名称**框中，键入没有直接点击率。
    
  - 在**说明**框中，键入类似，防止通过单击而无需 ATP 安全链接验证的网站中的特定组中的人员的说明。
    
  - 在**选择操作**部分中，选择**上**。
    
  - 选择**使用安全附件扫描可下载的内容**。
    
  - 如果此选项才可用，选择**应用发送组织内的邮件的安全链接**。
    
  - 选择**不允许用户通过单击到原始 URL**。
    
  - （这是可选的）在**不重写以下 Url**部分中，指定一个或多个被视为安全的组织的 Url。（请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)）
    
  - 在**应用于**部分中，选择**收件人是的成员**，，然后选择您想要包括在您的策略的组。选择**添加**，然后选择**确定**。
    
6. 选择**保存**。
    
## <a name="learn-about-atp-safe-links-policy-options"></a>了解 ATP 安全链接策略选项

设置或编辑 ATP 安全链接策略时，将看到可用的几个选项。如果您想知道这些选项什么下, 表介绍每个和受到影响。请注意，有两种主要的策略定义或编辑： 适用于每个人的默认策略和其他策略定义的特定收件人。
  
|**此策略**|**此选项**|**执行的操作**|
|:-----|:-----|:-----|
|默认 （定义后，默认策略适用于组织中的每个人）  <br/> |**阻止以下 Url** <br/> |允许贵组织拥有的自动阻止 Url 的自定义列表。当用户单击此列表中的 URL 时，它们将转到说明为什么阻止 URL[页警告](atp-safe-links-warning-pages.md)。<br/> 请参阅的详细信息，如新添加支持多达三个通配符星号的[设置使用 ATP 安全链接的自定义阻止 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)(\*)。  <br/> |
|默认  <br/> |**Office 365 ProPlus，适用于 iOS 的 Office 和 Android** <br/> |选中此选项后，ATP 安全链接保护文档中的应用到 Url 中打开 Office 365 ProPlus （Word、 Excel 和 PowerPoint 在 Windows 或 Mac 操作系统上的） iOS 或 Android 设备，在 Windows 和 Office Online (Word Visio 2016 上的 Office 文档Online、 PowerPoint Online、 Excel Online 和 OneNote Online），提供用户已登录到 Office 365。  <br/> > [!TIP]> 如果您看到仅**在 Windows 上的 Office 2016**，然后功能更新尚未达到 Office 365 环境尚未 （和即将推出）。之前，ATP 安全链接保护适用于 Word 2016、 Excel 2016、 PowerPoint 2016 或 Visio 2016 Windows 上运行。           |
|默认  <br/> |**当用户单击 ATP 安全链接不跟踪** <br/> |选中此选项后，单击数据的 Word、 Excel、 PowerPoint 和 Visio 文档中的 Url，而未存储。  <br/> |
|默认  <br/> |**不要让用户单击通过 ATP 原始 URL 的安全链接** <br/> |选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**关** <br/> |不扫描电子邮件中的 Url。  <br/> 可以定义例外规则，例如不扫描 Url 电子邮件中一组特定的收件人的规则。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**在** <br/> |当用户单击 Url 电子邮件中，可向路由用户通过 ATP 安全链接保护 Url。  <br/> 检查时针对阻止列表或恶意 Url 的列表的 URL。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**使用安全附件扫描可下载内容** <br/> |选中此选项后，会扫描指向可下载内容的 Url。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**适用于组织中发送的邮件的安全链接** <br/> | *此功能推出年 3 月 2018年中的开头。*  <br/> 可用并选中此选项时，为您提供的电子邮件帐户的组织中的人员之间发送的邮件位于 Office 365 中的电子邮件应用 ATP 安全链接保护。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**不跟踪用户单击** <br/> |选中此选项后，单击数据为来自外部发件人的电子邮件中的 Url，而未存储。  <br/> 当前不支持 URL 单击跟踪的组织中发送的电子邮件中的链接。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**不允许用户通过单击到原始 URL** <br/> |选中此选项后，用户将无法继续过[警告页](atp-safe-links-warning-pages.md)被确定为恶意 url。  <br/> |
|创建特定的电子邮件收件人的策略  <br/> |**不重写以下 Url** <br/> |与离开 Url。保留自定义列表的安全无需扫描一组特定的电子邮件收件人在组织中的 Url。<br/> 请参阅的详细信息，包括支持的通配符星号的最新更改的[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)(\*)。  <br/> |
   
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 中的 ATP 安全链接](atp-safe-links.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[查看高级威胁保护报告](view-reports-for-atp.md)

[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)
  
