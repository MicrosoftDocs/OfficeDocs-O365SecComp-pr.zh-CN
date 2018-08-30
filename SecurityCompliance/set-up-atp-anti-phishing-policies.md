---
title: 设置 Office 365 ATP 防钓鱼策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
description: ATP 防钓鱼保护，一部分 Office 365 高级威胁保护，可帮助您的组织防止恶意基于模拟的网络钓鱼攻击和其他网络钓鱼攻击。如果您的 Office 365 企业版全局或安全管理员，您可以设置 ATP 防钓鱼策略。网络钓鱼攻击来自在窗体的各种基于商品攻击到目标的矛网络钓鱼或 whaling。具有不断增长的复杂性，很难甚至培训眼睛标识其中一些复杂攻击。幸运的是，可以帮助 Office 365 高级威胁保护。您可以设置 ATP 防钓鱼策略，以帮助确保您的组织受到此类攻击。
ms.openlocfilehash: 73bcc148f3bd4f0700020c147cfa9cbb2734bc34
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525721"
---
# <a name="set-up-office-365-atp-anti-phishing-policies"></a>设置 Office 365 ATP 防钓鱼策略

[ATP 防钓鱼保护](atp-anti-phishing.md)，一部分[Office 365 高级威胁保护](office-365-atp.md)，可帮助您的组织防止恶意基于模拟的网络钓鱼攻击和其他网络钓鱼攻击。如果您的 Office 365 企业版全局或安全管理员，您可以设置 ATP 防钓鱼策略。网络钓鱼攻击来自在窗体的各种基于商品攻击到目标的矛网络钓鱼或 whaling。具有不断增长的复杂性，很难甚至培训眼睛标识其中一些复杂攻击。幸运的是，可以帮助 Office 365 高级威胁保护。您可以设置 ATP 防钓鱼策略，以帮助确保您的组织受到此类攻击。
  
> [!NOTE]
> ATP 防钓鱼才高级威胁防护，提供与 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。(作为全局管理员在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关规划选项的详细信息，请参阅[比较 Office 365 的业务计划](https://go.microsoft.com/fwlink/?linkid=844053)。请确保您的组织使用 Office 365 ProPlus 的最新版本 Windows 上以充分利用 ATP 防钓鱼保护。 
  
要执行的操作：
  
1. [查看先决条件](set-up-atp-anti-phishing-policies.md#phishprereq)
    
2. [了解 ATP 防钓鱼策略选项](set-up-atp-anti-phishing-policies.md#phishpolicyoptions)
    
3. [设置 ATP 防钓鱼策略](set-up-atp-anti-phishing-policies.md#addphishpolicy)
    
## <a name="review-the-prerequisites"></a>查看先决条件

- 确保您的**公司管理员**或**安全管理员**角色组的成员。 
    
- [了解 ATP 防钓鱼策略选项](set-up-atp-anti-phishing-policies.md#phishpolicyoptions)（本文中）。 
    
- 您将可能将多个 ATP 防钓鱼策略设置为您的组织。Office 365 强制实施这些策略他们正在安全中为**ATP 防钓鱼**页面上列出的顺序&amp;合规性中心。一旦已检查的策略选项，请花一些时间来每个确定您将需要多少个策略和优先级。 
    
- Plan to 花约 5-15 分钟设置您的第一个 ATP 防钓鱼策略。
    
- 允许最多 30 分钟的新的或更新策略传播到所有 Office 365 数据中心。
    
## <a name="set-up-an-atp-anti-phishing-policy"></a>设置 ATP 防钓鱼策略
<a name="addphishpolicy"> </a>

添加、 编辑和删除 Office 365 安全性 ATP 防钓鱼策略&amp;合规性中心。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. Office 365 安全性&amp;合规性中心在左侧的导航窗格中，**威胁管理**下面，选择**策略**。
    
3. 在**策略**页中，选择**ATP 防钓鱼**。
    
4. 在**防钓鱼**页上，执行以下任一操作： 
    
  - 若要添加新的策略选择 **+ 创建**。
    
  - 若要编辑现有策略，请从**防钓鱼**页面上显示列表中选择的策略名称。在显示页上，选择**编辑策略**。
    
    向导启动指导您通过定义防钓鱼策略。
    
5. 指定名称、 说明和您的策略设置。有关详细信息，请参阅[了解 ATP 防钓鱼策略选项](set-up-atp-anti-phishing-policies.md#phishpolicyoptions)。 
    
6. 一次检查您的设置，根据需要选择**创建此策略**或**保存**。 
    
## <a name="learn-about-atp-anti-phishing-policy-options"></a>了解 ATP 防钓鱼策略选项
<a name="phishpolicyoptions"> </a>

为您设置或编辑 ATP 防钓鱼策略，您可以选择多个选项下表中所述：
  
|**此设置**|**执行的操作**|**时要使用：**|
|:-----|:-----|:-----|
|**添加用户以保护** <br/> |定义策略将受保护的电子邮件地址。您可以添加您想要防止模拟的最多为 20 内部和外部地址。  <br/> |当您想要确保来自组织外部的邮件不是一个要保护的用户列表上的用户模拟。您可能想要保护的用户的示例包括高级管理人员、 业务所有者、 外部董事会成员，等等。<br/> 此列表的受保护的用户是人员的不同对其应用该策略，确切地说，则为其实施此策略的列表。定义适用于列表的**应用于**部分的策略选项。<br/> 例如，如果您将添加 Mary Smith \<marys@contoso.com\>作为来保护用户，然后将策略应用于"所有用户"组。这将确保，将该策略作用于出现模拟"Mary Smith"到"所有用户"组中的用户发送邮件。<br/> |
|**添加域，以保护** <br/> |允许您选择您想要防止模拟的域。您可以指定此策略，包括所有自定义域、 的域，以逗号分隔列表或二者的组合。如果您选择**自动包括我拥有的域**，并且稍后将域添加到您的 Office 365 组织，此防钓鱼策略将在新域的位置。<br/> |每当您想要确保来自组织外部的邮件不模拟的其中一个域中的已验证的域或伙伴域的列表定义。  <br/> |
|**选择操作** <br/> |选择 Office 365 检测模拟试图针对用户和域添加到策略时要采取的操作。在相同的防钓鱼策略中，您可以选择不同的用户和域的操作。这些操作应用于任何已通过 Office 365 被标识为模拟的用户帐户的传入电子邮件或受保护的此防钓鱼策略的域。<br/> **隔离邮件**将 Office 365 隔离中发送电子邮件。当您选择此选项时，不向原始收件人发送电子邮件。<br/> **重定向到另一个电子邮件地址的消息**将您指定的电子邮件地址发送电子邮件。您可以指定多个电子邮件地址。当您选择此选项时，不向原始收件人发送电子邮件。<br/> **移动到收件人的垃圾邮件文件夹的邮件**电子邮件会发送到收件人的垃圾电子邮件文件夹。当您选择此选项时，电子邮件仍将发送到原始收件人，但不是放置在收件人的收件箱。<br/> **将邮件传递，并将添加到密件抄送行其他地址**电子邮件将传递给原始收件人。此外，您确定用户将添加到邮件的密件抄送行交付之前。当您选择此选项时，仍会将电子邮件发送到原始收件人的收件箱中。<br/> **不能应用任何操作**电子邮件将传递到原始收件人的收件箱中。将电子邮件上不执行任何其他操作。<br/> **启用网络钓鱼保护提示**允许电子邮件中的反钓鱼安全提示。  <br/> |当您想要的 Office 365 已确定为用户或域策略中定义的模拟的邮件执行的操作。  <br/> |
|**启用邮箱智能** <br/> |启用或禁用此策略的邮箱智能。您只能启用邮箱智能对于基于云的帐户，即，其邮箱位于 Office 365 中完全的帐户。  <br/> |当您想要更好的基于每个用户的单个发件人映射为用户模拟结果。邮箱智能是围绕发送和接收来自邮件的人员。此智能允许 Office 365 自定义以便更好地处理 false 产生积极的模拟策略在用户级别。  <br/> |
|**添加受信任的发件人和域** <br/> |定义电子邮件地址和不会被视为模拟通过此策略的域。为受信任的发件人添加邮件从发件人电子邮件地址和域和域以往任何时候都不属于基于模拟的攻击。因此，操作和设置此策略中的不会应用到邮件来自下列发件人和域。  <br/> |当用户与域或触发模拟但被视为安全的用户进行交互。例如，如果伙伴具有相同/类似显示名或域名作为列表上定义的用户。  <br/> |
|**应用于** <br/> |定义策略的规则将其传入的电子邮件的收件人。您可以创建条件和例外与策略相关联的收件人。  <br/> 例如，可以将规则应用于您的域中的所有收件人为您的组织中创建的全局策略。  <br/> 您还可以创建例外规则，例如不扫描一组特定收件人的电子邮件的规则。  <br/> |每个策略都必须与一组用户，例如，在特定组或域中的用户相关联。  <br/> |
   
您的组织已设置 ATP 防钓鱼策略后，您可以看到服务通过[查看报告的高级威胁保护](view-reports-for-atp.md)的工作方式。
  
## <a name="example-anti-phishing-policy-to-protect-a-user-and-a-domain"></a>示例： 防钓鱼策略来保护用户和域
<a name="phishpolicyoptions"> </a>

本示例将名为"域和 CEO"提供用户和域防止模拟，并将策略应用于所有 contoso.com 域中的用户收到的电子邮件的策略设置。安全管理员已确定的策略，必须满足这些业务需求：
  
- 需要为 CEO 的提供保护策略电子邮件帐户和整个域。
    
- 确定要针对 CEO 的用户帐户的模拟尝试的邮件需要重定向到安全管理员的电子邮件地址。
    
- 确定要模拟尝试对域的消息不紧急，应隔离供以后查看。
    
Contoso 的安全管理员可能要创建满足这些需求防钓鱼策略使用类似于下面的值。
  
|||
|:-----|:-----|
|**设置或选项** <br/> |**示例** <br/> |
|Name  <br/> |域和 CEO  <br/> |
|描述  <br/> |确保，CEO 和我们的域不被模拟。  <br/> |
|添加用户以保护  <br/> |至少 CEO 的电子邮件地址。  <br/> |
|添加域，以保护  <br/> |组织域包含 CEO office。  <br/> |
|选择操作  <br/> |如果由模拟用户发送电子邮件： 选择**重定向到另一个电子邮件地址的消息**，然后键入安全管理员，例如，securityadmin@contoso.com 的电子邮件地址。  <br/> 如果由模拟域发送电子邮件： 选择**隔离邮件**。  <br/> |
|邮箱智能  <br/> |默认情况下，邮箱智能处于选中状态时创建新的防钓鱼策略。保留此设置**在**为了获得最佳结果。<br/> |
|添加受信任的发件人和域  <br/> |此示例中，不定义任何重写。  <br/> |
|应用于  <br/> |选择**的收件人的域**。在**下列任一**，选择**选择**。选择 **+ 添加**。在列表中选择的域名，例如，contoso.com，名称旁边的复选框，然后选择**添加**。选择**完成**。<br/> |
   
## <a name="delete-an-atp-anti-phishing-policy"></a>删除 ATP 防钓鱼策略
<a name="phishpolicyoptions"> </a>

您可以添加和编辑安全中的策略&amp;合规性中心。我们建议使用安全&amp;合规性中心以查看或编辑任何 ATP 策略。
  
1. 转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 在左侧导航窗格中，**威胁管理**下面，选择**策略**。
    
3. 在**策略**页中，选择**ATP 防钓鱼**。
    
4. 在**防钓鱼**页上，选择从在**防钓鱼**上显示的列表的策略名称。在显示页上，选择**删除策略**。允许您更改传播到所有 Office 365 数据中心最多 30 分钟。
    
## <a name="related-topics"></a>相关主题
<a name="phishpolicyoptions"> </a>

[Office 365 高级威胁防护](office-365-atp.md)
  
[Office 365 中的防钓鱼保护](anti-phishing-protection.md)
  
[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)
  
[ATP Office 365 中的安全链接](atp-safe-links.md)
  
[设置 Office 365 中的 ATP 安全链接策略](set-up-atp-safe-links-policies.md)
  
[Office 365 中的 ATP 安全附件](atp-safe-attachments.md)
  
[设置 Office 365 中的 ATP 附件安全策略](set-up-atp-safe-attachments-policies.md)
  
[查看高级威胁保护报告](view-reports-for-atp.md)
  
