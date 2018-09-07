---
title: 文档指纹
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: 1e0c579c-26e0-462a-a1b0-d7506dfe05fa
description: 您的组织中的信息工作者处理多种类型的典型的一天中的敏感信息。文档指纹，使您更轻松地通过确定整个组织中使用的标准窗体保护此信息。本主题介绍文档指纹以及如何创建一个使用 PowerShell 背后的概念。
ms.openlocfilehash: d73b769e7a014f2642a0fcd66cc6a500c68c46c3
ms.sourcegitcommit: 4be502d1fc6cbaef4c72d599758d51efe3a173c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23867486"
---
# <a name="document-fingerprinting"></a>文档指纹

您的组织中的信息工作者处理多种类型的典型的一天中的敏感信息。安全中&amp;合规性中心、 文档指纹使您更轻松地通过确定整个组织中使用的标准窗体保护此信息。本主题介绍文档指纹以及如何创建一个使用 PowerShell 背后的概念。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文档指纹的基本方案

文档指纹是一种标准窗体转换为敏感信息类型，您可以使用的 DLP 策略规则中的数据丢失防护 (DLP) 功能。例如，您可以创建空白专利模板上基于文档指纹，，然后创建检测到的 DLP 策略和包含敏感内容的所有传出专利模板填写的块。（可选） 您可以设置[策略提示](use-notifications-and-policy-tips.md)通知发件人，它们可能发送敏感信息和发件人应验证收件人的限定接收专利。此过程适用于您组织中使用任何基于文本的表单。您可以将上载的表单的其他示例包括： 
  
- 政府表单
    
- 符合《健康保险可携性与责任法案》 (HIPAA) 的表单
    
- 人力资源部的员工信息表单
    
- 组织专门创建的自定义表单
    
理想情况下，您的组织已经具有使用某些形式传输的敏感信息的既定的业务做法。上载一个空的窗体转换为文档指纹和相应的策略设置后，DLP 与该指纹匹配的出站邮件中检测任何文档。
  
## <a name="how-document-fingerprinting-works"></a>文档指纹的工作原理

您可能已经猜文档没有实际指纹，但名称可以帮助您理解功能。在一个人的指纹具有唯一性的方式相同，文档必须唯一 word 模式。时您上载的文件，DLP 标识文档中的唯一 word 模式、 创建文档指纹基于该模式，并使用该文档指纹检测出站文档包含相同的模式。这正是上载窗体或模板创建文档指纹的最有效的类型。填写表单的所有人使用原始一组相同的单词，然后向文档添加他或她自己的单词。只要出站文档不受密码保护，并且包含的原始表单中的所有文本，DLP 可以确定文档是否与文档指纹匹配。
  
下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。
  
**与父模板的文档指纹匹配的父文档示例**

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
与父模板包含空字段"专利 title，""创造者，"和"说明"的每个这些字段说明 — 这是 word 模式。在上载原始专利模板时，它是在支持的文件类型之一和纯文本。此 word 模式中插入文档指纹，这是小型的 Unicode XML 文件包含唯一的哈希值，表示原始文本和指纹的 DLP 转换另存为 Active Directory 中的数据分类。（作为安全措施，原始文档本身不会存储对服务; 存储仅哈希值，和原始文档不能重新构造从哈希值）专利指纹随后会成为可与 DLP 策略关联的敏感信息类型。将指纹 DLP 策略与关联后，DLP 检测到任何包含与专利指纹匹配的文档的出站电子邮件，并根据贵组织的策略处理它们的方式。 

例如，您可能想要设置可防止正则员工发送包含专利的传出邮件的 DLP 策略。DLP 将使用的专利指纹检测专利并阻止这些电子邮件。此外，您可能想让您能够将专利发送到其他组织，因为它具有业务需要这样的法律部门。您可以允许通过 DLP 策略中, 创建这些部门例外发送敏感信息的特定部门或可以允许他们覆盖策略提示使用的业务理由。
  
### <a name="supported-file-types"></a>支持的文件类型

文档指纹支持传输规则中支持的同一文件类型。支持的文件类型的列表，请参阅[支持的邮件流规则内容检查的文件类型](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。有关文件类型的一个简明： 传输规则和文档指纹都不支持.dotx 文件类型，它可以是令人费解，这是因为在 Word 中的模板文件。当您看到此和其他文档指纹的主题中的"模板"一词时，它是指已建立为标准窗体，不是模板文件类型的文档。
  
#### <a name="limitations-of-document-fingerprinting"></a>文档指纹的限制

在以下情况下，文档指纹不会检测敏感信息：
  
- 密码保护的文件
    
- 仅包含图片的文件
    
- 不包含用于创建文档指纹的原始表单中所有文本的文档
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 创建基于文档指纹的分类规则包

请注意，当前可只能通过中安全使用 PowerShell 创建文档指纹&amp;合规性中心。若要连接，请参阅[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

DLP 使用分类规则包来检测敏感内容。若要创建基于文档指纹的分类规则包，使用**新建 DlpFingerprint**和**新建 DlpSensitiveInformationType** cmdlet。**新建 DlpFingerprint**的结果不会存储外部数据分类规则，因为您始终都运行**新建 DlpFingerprint**和**新建 DlpSensitiveInformationType**或**集 DlpSensitiveInformationType**在相同PowerShell 会话。下面的示例创建新基于文件 C:\My Documents\Contoso Employee Template.docx 的文档指纹。以便您可以使用它与**新建 DlpSensitiveInformationType** cmdlet 相同的 PowerShell 会话中，可以作为变量存储的新的指纹。 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

您现在可以使用**Get DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包，并在此示例中，"Contoso Customer Confidential"是数据分类规则包列表的一部分。 
  
最后，将"Contoso Customer Confidential"的数据分类规则包添加到安全中的 DLP 策略&amp;合规性中心。本示例向名为"ConfidentialPolicy"的现有 DLP 策略规则。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

下面的示例中所示，还可以在 Exchange Online 中的传输规则中使用数据分类规则包。若要运行此命令，您首先需要[连接到 Exchange Online PowerShell 中](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。另请注意，则需要花时间要同步的安全的规则包&amp;合规性中心到 Exchange Admin Center。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP 现在可以检测匹配 Contoso Customer Form.docx 文档指纹的文档。
  
有关语法和参数信息，请参阅：

- [新 DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [新 DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [删除 DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [设置 DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
