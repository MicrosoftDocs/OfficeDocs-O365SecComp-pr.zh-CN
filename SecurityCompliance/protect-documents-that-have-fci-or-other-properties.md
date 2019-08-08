---
title: 创建 DLP 策略来保护具有 FCI 或其他属性的文档
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 许多组织已拥有一个使用 Windows Server 文件分类基础结构 (FCI)、SharePoint 中的文档属性或由第三方系统应用的文档属性识别和分类敏感信息的流程。 如果您的组织就是这样，则可以在 Office 365 中创建一个 DLP 策略，来识别已由 Windows Server FCI 或其他系统应用到文档的属性，从而在带有特定 FCI 或其他属性值的 Office 文档上强制应用该 DLP 策略。
ms.openlocfilehash: 5f464c2918d7ea91fa5c65b28bc477ee7cc768e3
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230956"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>创建 DLP 策略来保护具有 FCI 或其他属性的文档

在 Office 365 中，您可以使用数据丢失防护 (DLP) 策略来识别、监视和保护敏感信息。许多组织已拥有一个使用 Windows Server 文件分类基础结构 (FCI)、SharePoint 中的文档属性或由第三方系统应用的文档属性识别和分类敏感信息的流程。如果您的组织就是这样，则可以在 Office 365 中创建一个 DLP 策略，来识别已由 Windows Server FCI 或其他系统应用到文档的属性，从而在带有特定 FCI 或其他属性值的 Office 文档上强制应用该 DLP 策略。
  
![显示 Office 365 和外部分类系统的图表](media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
例如，您的组织可能会使用 Windows Server FCI 来识别包含个人身份信息 (PII) 的文档（如社会保险号），然后通过基于文档中找到的 PII 的类型和出现次数将“个人身份信息”**** 属性设置为“高”****、“中等”****、“低”****、“公开”**** 或“非 PII”**** 来对文档进行分类。 在 Office 365 中，您可以创建 DLP 策略，来标识将该属性设置为特定值（如“高”**** 和“中等”****）的文档，然后对这些文件执行操作，如阻止访问。 如果将属性设置为“低”****，则同一个策略可以使用其他规则来执行不同的操作，如发送电子邮件通知。 通过这种方式, Office 365 中的 DLP 与 Windows Server FCI 集成, 并可帮助保护从基于 Windows Server 的文件服务器上传或共享到 Office 365 的 Office 文档。
  
DLP 策略只需查找特定的属性名称/值对。可以使用任何文档属性，只要该属性具有 SharePoint 搜索的相应托管属性。例如，SharePoint 网站集可能使用名为“行程报告”**** 的内容类型，包含名为“客户”**** 的必填字段。只要有人创建行程报告，就必须输入客户名称。此属性名称/值对还可在 DLP 策略中使用 — 例如，当“客户”**** 字段包含“Contoso”**** 时，您希望有一个规则可以阻止外部用户访问此文档。
  
请注意, 如果您想要将 DLP 策略应用于具有特定 Office 365 标签的内容, 则不应遵循此处的步骤。 请改为了解如何将[标签用作 DLP 策略中的条件](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)。
  
## <a name="before-you-create-the-dlp-policy"></a>在创建 DLP 策略之前

您需要在 SharePoint 管理中心中创建托管属性，才能在 DLP 策略中使用 Windows Server FCI 属性或其他属性。 下面介绍了原因。
  
示例
  
这很重要，因为 Office 365 中的 DLP 使用搜索爬网程序来识别网站上的敏感信息，并对其进行分类，然后将该敏感信息存储在搜索索引的一个安全部分。当您将文档上载到 Office 365 时，SharePoint 会自动创建基于文档属性的已爬网属性。但是，要在 DLP 策略中使用 FCI 或其他属性，该已爬网属性需要映射到托管属性，以便将包含该属性的内容保留在索引中。
  
有关搜索和托管属性的详细信息, 请参阅[在 SharePoint Online 中管理搜索架构](http://go.microsoft.com/fwlink/p/?LinkID=627454)。
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>步骤 1：将包含所需属性的文档上载到 Office 365

首先需要上载包含要在您的 DLP 策略中引用的属性的文档。 Office 365 将检测此属性，并从该属性自动创建已爬网属性。 在下一步中, 您将创建托管属性, 然后将托管属性映射到此已爬网属性。
  
### <a name="step-2-create-a-managed-property"></a>步骤 2：创建托管属性

1. 登录到 Microsoft 365 管理中心。
    
2. 在左侧导航中, 选择 "**管理中心** \> " " **SharePoint**"。 You're now in the SharePoint admin center.
    
3. 在左侧导航中, 选择 "**搜索管理**" 页\>上的 "**搜索** \> " "**管理搜索架构**"。
    
    ![SharePoint 管理中心内的搜索管理页面](media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. 在 "**托管属性**" \>页上**新建托管属性**。
    
    ![突出显示“新建托管属性”按钮的“托管属性”页面](media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. 输入属性的名称和说明。此名称将显示在您的 DLP 策略中。
    
6. 对于“类型”****，选择“文本”****。 
    
7. 在“主要特征”**** 下，选择“可查询”**** 和“可检索”****。
    
8. 在 "到已\> **爬网属性的映射**" 下**添加映射**。
    
9. 在 "已**爬网属性选择**" 对话框中, \>查找并选择与将在 DLP 策略\> **"确定"** 中使用的 Windows Server FCI 属性或其他属性相对应的已爬网属性。
    
    ![已爬网属性选择对话框](media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. 在页面\>底部的 **"确定"**。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>创建使用 FCI 属性或其他属性的 DLP 策略

在此示例中, 组织在其基于 Windows Server 的文件服务器上使用 FCI;具体来说, 他们使用的是名为**个人身份信息**的 FCI 分类属性, 其可能**** 值为**高**、中、**低**、**公共**和**不是 PII**。 现在他们想要在 Office 365 的 DLP 策略中利用其现有的 FCI 分类。
  
首先，它们按照上述步骤在 SharePoint Online 中创建托管属性，该属性映射到从 FCI 属性自动创建的已爬网属性。
  
接下来, 他们创建一个 DLP 策略, 其中两个规则都使用条件**文档属性包含以下任一值**:
  
- **FCI PII 内容-高、中等**如果 FCI 分类属性的**个人可识别信息**等于**高**或**适中**, 并且与组织外部的人员共享文档, 则第一个规则将限制对文档的访问。 
    
- **FCI PII 内容-低**如果 FCI 分类属性的**个人可识别信息**等于**较低**, 并且与组织外部的人员共享文档, 则第二条规则会向文档所有者发送通知。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>使用 PowerShell 创建 DLP 策略

请注意, 条件**文档属性包含这些值中的任何一个**暂时在安全&amp;合规性中心的 UI 中不可用, 但你仍可以使用 PowerShell 使用此条件。 您`New\Set\Get-DlpCompliancePolicy`可以使用 cmdlet 来使用 DLP 策略, 并`New\Set\Get-DlpComplianceRule`将 cmdlet 与`ContentPropertyContainsWords`参数一起使用, 以添加条件**文档属性包含这些值中的任何一个**。
  
有关这些 cmdlet 的详细信息, 请参阅[Office 365 &amp;安全合规中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。
  
1. [使用远程 PowerShell 连接到 Office 365 安全与合规中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用`New-DlpCompliancePolicy`创建策略。
    
    下面是 PowerShell 示例, 用于创建适用于所有位置的 DLP 策略。
    
      ```
      New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
      ```

3. 通过`New-DlpComplianceRule`使用 (其中一个规则针对**低**值) 和另一个规则用于**高**和**中等**值, 创建上述两个规则。 
    
    下面是创建这两个规则的 PowerShell 示例。 请注意, 属性名称/值对括在引号中, 并且属性名称可以指定多个以逗号分隔的多个值, 不包含空格, 如`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`
    
      ```
      New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
      ```

    请注意, Windows Server FCI 包含许多内置属性, 包括本示例中使用的**个人身份信息**。 每个组织的每个属性的可能值可能各不相同。 此处使用的 "**高**"、"**中等**" 和 "**低**" 值仅是一个示例。 对于您的组织, 您可以在基于 Windows Server 的文件服务器上的文件服务器资源管理器中查看 Windows Server FCI 分类属性及其可能的值。 有关详细信息, 请参阅[创建分类属性](http://go.microsoft.com/fwlink/p/?LinkID=627456)。
    
完成后, 策略应具有两个新规则, 它们都使用**文档属性包含这些值条件中的任何一个**。 请注意, 此条件不会显示在 UI 中, 但会显示其他条件、操作和设置。 
  
一个规则阻止访问其中“个人身份信息”**** 属性等于“高”**** 或“中等”**** 的内容。 第二个规则会发送有关“个人身份信息”**** 属性等于“低”**** 的内容的通知。
  
![显示刚创建的两条规则的“新建 DLP 策略”对话框](media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>创建 DLP 策略之后

执行前面各节中的步骤将创建一个 DLP 策略, 该策略将使用该属性快速检测内容, 但前提是该内容是新上载的 (以便内容已编制索引), 或者该内容是旧的, 但只是进行了编辑 (以便重新编制内容索引).
  
若要在任意位置检测包含该属性的内容，您可能需要手动请求对您的库、网站或网站集重新编制索引，以便 DLP 策略识别包含该属性的所有内容。在 SharePoint Online 中，内容基于已定义的爬网计划进行自动爬网。爬网程序选取自上次爬网以来已更改的内容，并更新索引。如果您需要在下一次计划的爬网之前，让您的 DLP 策略保护内容，您可以执行下列步骤。
  
> [!CAUTION]
> 重新编制网站的索引可能会导致搜索系统上的负荷大量增加。 除非您的方案确实需要, 否则不要对网站重新编制索引。 
  
有关详细信息, 请参阅[手动对网站、库或列表的请求爬网和重新编制索引](http://go.microsoft.com/fwlink/p/?LinkID=627457)。
  
### <a name="re-index-a-site-optional"></a>重新编制网站的索引（可选）

1. 在网站上, 选择 "**设置**" (右上角的齿轮\>图标) "**网站设置**"。
    
2. 在 "**搜索**" 下, 选择 "**搜索和脱机可用性** \>重新**索引网站**"。
    
## <a name="more-information"></a>更多信息

- [数据丢失防护策略概述](data-loss-prevention-policies.md)
    
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
    
- [发送通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
    
- [敏感信息类型库存](what-the-sensitive-information-types-look-for.md)
    

