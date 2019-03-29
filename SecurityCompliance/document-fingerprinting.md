---
title: 文档指纹
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: 组织中的信息工作人员每天会处理大量的敏感信息。 "文档指纹"可识别贵组织中使用的标准表单，以便于您保护此信息。 本主题介绍文档指纹背后的概念, 以及如何使用 PowerShell 创建一个概念。
ms.openlocfilehash: bf28d1d901598337a5c9c18d80590b136c539d26
ms.sourcegitcommit: a79eb9907759d4cd849c3f948695a9ff890b19bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30866348"
---
# <a name="document-fingerprinting"></a>文档指纹

组织中的信息工作人员每天会处理大量的敏感信息。 在安全&amp;合规性中心中, 文档指纹可使您更轻松地通过标识在整个组织中使用的标准表单来保护此信息。 本主题介绍文档指纹背后的概念, 以及如何使用 PowerShell 创建一个概念。
  
## <a name="basic-scenario-for-document-fingerprinting"></a>文档指纹的基本方案

文档指纹是一项数据丢失防护 (DLP) 功能, 可将标准窗体转换为敏感信息类型, 您可以在 DLP 策略的规则中使用。 例如，您可以基于空白父模板来创建文档指纹，然后创建 DLP 策略，用于检测和阻止所有包含敏感内容的传出父模板。 (可选) 您可以设置[策略提示](use-notifications-and-policy-tips.md)以通知发件人他们可能发送敏感信息, 并且发件人应验证收件人是否有资格接收专利。 此过程与组织中使用的任何基于文本的表单一起使用。 您可以上载的其他表单示例包括： 
  
- 政府表单
    
- 符合《健康保险可携性与责任法案》 (HIPAA) 的表单
    
- 人力资源部的员工信息表单
    
- 组织专门创建的自定义表单
    
理想情况下，贵组织已经创建使用特定表单传输敏感信息的业务实践。 在上载要转换为文档指纹的空表单并设置相应的策略后, DLP 将检测出出出出出站邮件中与该指纹匹配的任何文档。
  
## <a name="how-document-fingerprinting-works"></a>文档指纹的工作原理

您可能已经猜到，文档并非真的有指纹，只是"指纹"这个词可以表明其功能。 人的指纹各不相同，同理，文档的单词模式也各不相同。 上载文件时, DLP 将标识文档中的唯一单词模式, 根据该模式创建文档指纹, 并使用该文档指纹检测包含相同模式的出站文档。 这也是为什么上载表单或模板可以创建最有效的文档指纹的原因。 填写表单的每个人使用相同的单词集，然后在文档中添加自己的词句。 只要出站文档不受密码保护, 并且包含原始表单中的所有文本, DLP 就可以确定文档是否与文档指纹相匹配。
  
下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。
  
**与父模板的文档指纹匹配的父文档示例**

![Document_Fingerprinting_diagram](media/Document_Fingerprinting_diagram.png)
  
专利模板包含空字段 "专利权 title"、"Inventors" 和 "Description" 以及每个字段的说明, 即 word 模式。 上载原始专利模板时, 它采用受支持的文件类型之一和纯文本格式。 DLP 将此 word 模式转换为文档指纹, 这是一个包含代表原始文本的唯一哈希值的小型 Unicode XML 文件, 并且指纹在 Active Directory 中保存为数据分类。 (作为一种安全措施, 原始文档本身不存储在服务上; 仅存储哈希值, 并且无法从哈希值重新构造原始文档。)专利指纹将成为可与 DLP 策略关联的敏感信息类型。 将指纹与 DLP 策略相关联后, DLP 将检测任何包含符合专利指纹的文档的出站电子邮件, 并根据您的组织的策略对其进行处理。 

例如, 您可能希望设置一个 DLP 策略, 以防止普通员工发送包含专利的传出邮件。 DLP 将使用专利指纹来检测专利并阻止这些电子邮件。 或者, 您可能希望让法律部门能够将专利发送给其他组织, 因为这样做有业务需求。 您可以通过在 DLP 策略中为这些部门创建例外来允许特定部门发送敏感信息, 也可以允许他们使用业务理由覆盖策略提示。
  
### <a name="supported-file-types"></a>支持的文件类型

文档指纹支持在邮件流规则 (也称为传输规则) 中受支持的相同文件类型。 有关受支持的文件类型的列表, 请参阅[邮件流规则内容检查支持的文件类型](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。 有关文件类型的快速说明: 邮件流规则和文档指纹都不支持 .dotx 文件类型, 因为这是 Word 中的模板文件, 这样做可能会造成混淆。 当您在本主题或其他文档指纹主题中看到"template"一词时，它是指您构建为标准模板的文档，而非模板文件类型。
  
#### <a name="limitations-of-document-fingerprinting"></a>文档指纹的限制

在下列情况下, 文档指纹不会检测敏感信息:
  
- 密码保护的文件
    
- 仅包含图片的文件
    
- 不包含用于创建文档指纹的原始表单中所有文本的文档
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>使用 PowerShell 创建基于文档指纹的分类规则包

请注意, 当前可以在安全&amp;合规中心中使用 PowerShell 创建文档指纹。 若要进行连接, 请参阅[连接到 Office 365 Security & 合规中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

DLP 使用分类规则包来检测敏感内容。 若要创建基于文档指纹的分类规则包, 请使用**DlpFingerprint**和**DlpSensitiveInformationType** cmdlet。 由于**DlpFingerprint**的结果不会存储在数据分类规则的外部, 因此您始终在相同的**DlpFingerprint**和**DlpSensitiveInformationType**或**DlpSensitiveInformationType**中运行新的PowerShell 会话。 以下示例基于文件 C:\My Documents\Contoso Employee Template.docx 创建新的文档指纹。 将新的指纹存储为变量, 以便您可以在同一 PowerShell 会话中将其与**DlpSensitiveInformationType** cmdlet 一起使用。 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

现在, 您可以使用**DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包, 在此示例中, "Contoso Customer 保密" 是 "数据分类规则包" 列表的一部分。 
  
最后, 将 "Contoso Customer 保密" 数据分类规则包添加到安全&amp;合规中心中的 DLP 策略。 本示例将一个规则添加到名为 "ConfidentialPolicy" 的现有 DLP 策略中。

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

您还可以在 Exchange Online 中使用邮件流规则中的数据分类规则包, 如下面的示例所示。 若要运行此命令, 首先需要[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。 另请注意, 规则包从安全&amp;合规中心同步到 Exchange 管理中心需要花费一些时间。
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP 现在检测与 Contoso Customer 表单的 .docx 文档指纹相匹配的文档。
  
有关语法和参数的信息, 请参阅:

- [新 DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [新 DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
