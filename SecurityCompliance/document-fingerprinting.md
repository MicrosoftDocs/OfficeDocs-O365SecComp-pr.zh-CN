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
# <a name="document-fingerprinting"></a><span data-ttu-id="dee1e-105">文档指纹</span><span class="sxs-lookup"><span data-stu-id="dee1e-105">Document Fingerprinting</span></span>

<span data-ttu-id="dee1e-p102">您的组织中的信息工作者处理多种类型的典型的一天中的敏感信息。安全中&amp;合规性中心、 文档指纹使您更轻松地通过确定整个组织中使用的标准窗体保护此信息。本主题介绍文档指纹以及如何创建一个使用 PowerShell 背后的概念。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p102">Information workers in your organization handle many kinds of sensitive information during a typical day. In the Security &amp; Compliance Center, Document Fingerprinting makes it easier for you to protect this information by identifying standard forms that are used throughout your organization. This topic describes the concepts behind Document Fingerprinting and how to create one by using PowerShell.</span></span>
  
## <a name="basic-scenario-for-document-fingerprinting"></a><span data-ttu-id="dee1e-109">文档指纹的基本方案</span><span class="sxs-lookup"><span data-stu-id="dee1e-109">Basic scenario for Document Fingerprinting</span></span>

<span data-ttu-id="dee1e-p103">文档指纹是一种标准窗体转换为敏感信息类型，您可以使用的 DLP 策略规则中的数据丢失防护 (DLP) 功能。例如，您可以创建空白专利模板上基于文档指纹，，然后创建检测到的 DLP 策略和包含敏感内容的所有传出专利模板填写的块。（可选） 您可以设置[策略提示](use-notifications-and-policy-tips.md)通知发件人，它们可能发送敏感信息和发件人应验证收件人的限定接收专利。此过程适用于您组织中使用任何基于文本的表单。您可以将上载的表单的其他示例包括：</span><span class="sxs-lookup"><span data-stu-id="dee1e-p103">Document Fingerprinting is a Data Loss Prevention (DLP) feature that converts a standard form into a sensitive information type, which you can use in the rules of your DLP policies. For example, you can create a document fingerprint based on a blank patent template and then create a DLP policy that detects and blocks all outgoing patent templates with sensitive content filled in. Optionally, you can set up [policy tips](use-notifications-and-policy-tips.md) to notify senders that they might be sending sensitive information, and the sender should verify that the recipients are qualified to receive the patents. This process works with any text-based forms used in your organization. Additional examples of forms that you can upload include:</span></span> 
  
- <span data-ttu-id="dee1e-115">政府表单</span><span class="sxs-lookup"><span data-stu-id="dee1e-115">Government forms</span></span>
    
- <span data-ttu-id="dee1e-116">符合《健康保险可携性与责任法案》 (HIPAA) 的表单</span><span class="sxs-lookup"><span data-stu-id="dee1e-116">Health Insurance Portability and Accountability Act (HIPAA) compliance forms</span></span>
    
- <span data-ttu-id="dee1e-117">人力资源部的员工信息表单</span><span class="sxs-lookup"><span data-stu-id="dee1e-117">Employee information forms for Human Resources departments</span></span>
    
- <span data-ttu-id="dee1e-118">组织专门创建的自定义表单</span><span class="sxs-lookup"><span data-stu-id="dee1e-118">Custom forms created specifically for your organization</span></span>
    
<span data-ttu-id="dee1e-p104">理想情况下，您的组织已经具有使用某些形式传输的敏感信息的既定的业务做法。上载一个空的窗体转换为文档指纹和相应的策略设置后，DLP 与该指纹匹配的出站邮件中检测任何文档。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p104">Ideally, your organization already has an established business practice of using certain forms to transmit sensitive information. After you upload an empty form to be converted to a document fingerprint and set up a corresponding policy, the DLP detects any documents in outbound mail that match that fingerprint.</span></span>
  
## <a name="how-document-fingerprinting-works"></a><span data-ttu-id="dee1e-121">文档指纹的工作原理</span><span class="sxs-lookup"><span data-stu-id="dee1e-121">How Document Fingerprinting works</span></span>

<span data-ttu-id="dee1e-p105">您可能已经猜文档没有实际指纹，但名称可以帮助您理解功能。在一个人的指纹具有唯一性的方式相同，文档必须唯一 word 模式。时您上载的文件，DLP 标识文档中的唯一 word 模式、 创建文档指纹基于该模式，并使用该文档指纹检测出站文档包含相同的模式。这正是上载窗体或模板创建文档指纹的最有效的类型。填写表单的所有人使用原始一组相同的单词，然后向文档添加他或她自己的单词。只要出站文档不受密码保护，并且包含的原始表单中的所有文本，DLP 可以确定文档是否与文档指纹匹配。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p105">You've probably already guessed that documents don't have actual fingerprints, but the name helps explain the feature. In the same way that a person's fingerprints have unique patterns, documents have unique word patterns. When you upload a file, DLP identifies the unique word pattern in the document, creates a document fingerprint based on that pattern, and uses that document fingerprint to detect outbound documents containing the same pattern. That's why uploading a form or template creates the most effective type of document fingerprint. Everyone who fills out a form uses the same original set of words and then adds his or her own words to the document. As long as the outbound document isn't password protected and contains all the text from the original form, DLP can determine if the document matches the document fingerprint.</span></span>
  
<span data-ttu-id="dee1e-128">下列示例说明了当您基于父模板创建文档指纹时发生了什么，但您可以使用任何表单作为基础来创建文档指纹。</span><span class="sxs-lookup"><span data-stu-id="dee1e-128">The following example shows what happens if you create a document fingerprint based on a patent template, but you can use any form as a basis for creating a document fingerprint.</span></span>
  
<span data-ttu-id="dee1e-129">**与父模板的文档指纹匹配的父文档示例**</span><span class="sxs-lookup"><span data-stu-id="dee1e-129">**Example of a patent document matching a document fingerprint of a patent template**</span></span>

![Document_Fingerprinting_diagram.png](media/Document_Fingerprinting_diagram.png)
  
<span data-ttu-id="dee1e-p106">与父模板包含空字段"专利 title，""创造者，"和"说明"的每个这些字段说明 — 这是 word 模式。在上载原始专利模板时，它是在支持的文件类型之一和纯文本。此 word 模式中插入文档指纹，这是小型的 Unicode XML 文件包含唯一的哈希值，表示原始文本和指纹的 DLP 转换另存为 Active Directory 中的数据分类。（作为安全措施，原始文档本身不会存储对服务; 存储仅哈希值，和原始文档不能重新构造从哈希值）专利指纹随后会成为可与 DLP 策略关联的敏感信息类型。将指纹 DLP 策略与关联后，DLP 检测到任何包含与专利指纹匹配的文档的出站电子邮件，并根据贵组织的策略处理它们的方式。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p106">The patent template contains the blank fields "Patent title," "Inventors," and "Description" and descriptions for each of those fields—that's the word pattern. When you upload the original patent template, it's in one of the supported file types and in plain text. DLP converts this word pattern into a document fingerprint, which is a small Unicode XML file containing a unique hash value representing the original text, and the fingerprint is saved as a data classification in Active Directory. (As a security measure, the original document itself isn't stored on the service; only the hash value is stored, and the original document can't be reconstructed from the hash value.) The patent fingerprint then becomes a sensitive information type that you can associate with a DLP policy. After you associate the fingerprint with a DLP policy, DLP detects any outbound emails containing documents that match the patent fingerprint and deals with them according to your organization's policy.</span></span> 

<span data-ttu-id="dee1e-p107">例如，您可能想要设置可防止正则员工发送包含专利的传出邮件的 DLP 策略。DLP 将使用的专利指纹检测专利并阻止这些电子邮件。此外，您可能想让您能够将专利发送到其他组织，因为它具有业务需要这样的法律部门。您可以允许通过 DLP 策略中, 创建这些部门例外发送敏感信息的特定部门或可以允许他们覆盖策略提示使用的业务理由。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p107">For example, you might want to set up a DLP policy that prevents regular employees from sending outgoing messages containing patents. DLP will use the patent fingerprint to detect patents and block those emails. Alternatively, you might want to let your legal department to be able to send patents to other organizations because it has a business need for doing so. You can allow specific departments to send sensitive information by creating exceptions for those departments in your DLP policy, or you can allow them to override a policy tip with a business justification.</span></span>
  
### <a name="supported-file-types"></a><span data-ttu-id="dee1e-140">支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="dee1e-140">Supported file types</span></span>

<span data-ttu-id="dee1e-p108">文档指纹支持传输规则中支持的同一文件类型。支持的文件类型的列表，请参阅[支持的邮件流规则内容检查的文件类型](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)。有关文件类型的一个简明： 传输规则和文档指纹都不支持.dotx 文件类型，它可以是令人费解，这是因为在 Word 中的模板文件。当您看到此和其他文档指纹的主题中的"模板"一词时，它是指已建立为标准窗体，不是模板文件类型的文档。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p108">Document Fingerprinting supports the same file types that are supported in transport rules. For a list of supported file types, see [Supported file types for mail flow rule content inspection](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). One quick note about file types: neither transport rules nor Document Fingerprinting supports the .dotx file type, which can be confusing because that's a template file in Word. When you see the word "template" in this and other Document Fingerprinting topics, it refers to a document that you have established as a standard form, not the template file type.</span></span>
  
#### <a name="limitations-of-document-fingerprinting"></a><span data-ttu-id="dee1e-145">文档指纹的限制</span><span class="sxs-lookup"><span data-stu-id="dee1e-145">Limitations of document fingerprinting</span></span>

<span data-ttu-id="dee1e-146">在以下情况下，文档指纹不会检测敏感信息：</span><span class="sxs-lookup"><span data-stu-id="dee1e-146">Document Fingerprinting won't detect sensitive information in the following cases:</span></span>
  
- <span data-ttu-id="dee1e-147">密码保护的文件</span><span class="sxs-lookup"><span data-stu-id="dee1e-147">Password protected files</span></span>
    
- <span data-ttu-id="dee1e-148">仅包含图片的文件</span><span class="sxs-lookup"><span data-stu-id="dee1e-148">Files that contain only images</span></span>
    
- <span data-ttu-id="dee1e-149">不包含用于创建文档指纹的原始表单中所有文本的文档</span><span class="sxs-lookup"><span data-stu-id="dee1e-149">Documents that don't contain all the text from the original form used to create the document fingerprint</span></span>
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a><span data-ttu-id="dee1e-150">使用 PowerShell 创建基于文档指纹的分类规则包</span><span class="sxs-lookup"><span data-stu-id="dee1e-150">Use PowerShell to create a classification rule package based on document fingerprinting</span></span>

<span data-ttu-id="dee1e-p109">请注意，当前可只能通过中安全使用 PowerShell 创建文档指纹&amp;合规性中心。若要连接，请参阅[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p109">Note that you can currently create a document fingerprint only by using PowerShell in the Security &amp; Compliance Center. To connect, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

<span data-ttu-id="dee1e-p110">DLP 使用分类规则包来检测敏感内容。若要创建基于文档指纹的分类规则包，使用**新建 DlpFingerprint**和**新建 DlpSensitiveInformationType** cmdlet。**新建 DlpFingerprint**的结果不会存储外部数据分类规则，因为您始终都运行**新建 DlpFingerprint**和**新建 DlpSensitiveInformationType**或**集 DlpSensitiveInformationType**在相同PowerShell 会话。下面的示例创建新基于文件 C:\My Documents\Contoso Employee Template.docx 的文档指纹。以便您可以使用它与**新建 DlpSensitiveInformationType** cmdlet 相同的 PowerShell 会话中，可以作为变量存储的新的指纹。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p110">DLP uses classification rule packages to detect sensitive content. To create a classification rule package based on a document fingerprint, use the **New-DlpFingerprint** and **New-DlpSensitiveInformationType** cmdlets. Because the results of **New-DlpFingerprint** aren't stored outside the data classification rule, you always run **New-DlpFingerprint** and **New-DlpSensitiveInformationType** or **Set-DlpSensitiveInformationType** in the same PowerShell session. The following example creates a new document fingerprint based on the file C:\My Documents\Contoso Employee Template.docx. You store the new fingerprint as a variable so you can use it with the **New-DlpSensitiveInformationType** cmdlet in the same PowerShell session.</span></span> 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

<span data-ttu-id="dee1e-158">现在，我们可以一起创建名为"Contoso Employee Confidential"的新数据分类规则，该规则使用文件 C:\My Documents\Contoso Customer Information Form.docx 的文档指纹。</span><span class="sxs-lookup"><span data-stu-id="dee1e-158">Now, let's create a new data classification rule named "Contoso Employee Confidential" that uses the document fingerprint of the file C:\My Documents\Contoso Customer Information Form.docx.</span></span>
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

<span data-ttu-id="dee1e-159">您现在可以使用**Get DlpSensitiveInformationType** cmdlet 查找所有 DLP 数据分类规则包，并在此示例中，"Contoso Customer Confidential"是数据分类规则包列表的一部分。</span><span class="sxs-lookup"><span data-stu-id="dee1e-159">You can now use the **Get-DlpSensitiveInformationType** cmdlet to find all DLP data classification rule packages, and in this example, "Contoso Customer Confidential" is part of the data classification rule packages list.</span></span> 
  
<span data-ttu-id="dee1e-p111">最后，将"Contoso Customer Confidential"的数据分类规则包添加到安全中的 DLP 策略&amp;合规性中心。本示例向名为"ConfidentialPolicy"的现有 DLP 策略规则。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p111">Finally, add the "Contoso Customer Confidential" data classification rule package to a DLP policy in the Security &amp; Compliance Center. This example adds a rule to an existing DLP policy named "ConfidentialPolicy".</span></span>

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

<span data-ttu-id="dee1e-p112">下面的示例中所示，还可以在 Exchange Online 中的传输规则中使用数据分类规则包。若要运行此命令，您首先需要[连接到 Exchange Online PowerShell 中](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。另请注意，则需要花时间要同步的安全的规则包&amp;合规性中心到 Exchange Admin Center。</span><span class="sxs-lookup"><span data-stu-id="dee1e-p112">You can also use the data classification rule package in transport rules in Exchange Online, as shown in the following example. To run this command, you first need to [Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Also note that it takes time for the rule package to sync from the Security &amp; Compliance Center to the Exchange Admin Center.</span></span>
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

<span data-ttu-id="dee1e-165">DLP 现在可以检测匹配 Contoso Customer Form.docx 文档指纹的文档。</span><span class="sxs-lookup"><span data-stu-id="dee1e-165">DLP now detects documents that match the Contoso Customer Form.docx document fingerprint.</span></span>
  
<span data-ttu-id="dee1e-166">有关语法和参数信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dee1e-166">For syntax and parameter information, see:</span></span>

- [<span data-ttu-id="dee1e-167">新 DlpFingerprint</span><span class="sxs-lookup"><span data-stu-id="dee1e-167">New-DlpFingerprint</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [<span data-ttu-id="dee1e-168">新 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="dee1e-168">New-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [<span data-ttu-id="dee1e-169">删除 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="dee1e-169">Remove-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [<span data-ttu-id="dee1e-170">设置 DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="dee1e-170">Set-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [<span data-ttu-id="dee1e-171">Get DlpSensitiveInformationType</span><span class="sxs-lookup"><span data-stu-id="dee1e-171">Get-DlpSensitiveInformationType</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
