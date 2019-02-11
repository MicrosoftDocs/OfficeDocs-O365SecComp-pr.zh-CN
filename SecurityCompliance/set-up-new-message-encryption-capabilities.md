---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 可以使用内置到 Azure 信息保护，您的组织的顶部功能的新 Office 365 邮件加密保护与您的组织内外的人员的电子邮件通信。新的 OME 功能使用其他 Office 365 组织、 Outlook.com、 Gmail 和其他电子邮件服务。
ms.openlocfilehash: a30054bf7b03a3e4fadf9a0e34537c682c10e217
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696246"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>设置全新的 Office 365 邮件加密功能

使用新的 Office 365 邮件加密 (OME) 功能，利用 Azure Information Protection 中的保护功能，您的组织可以轻松地共享受保护的电子邮件与任何设备上的任何人。用户可以发送和接收与其他 Office 365 组织以及非 Office 365 客户使用 Outlook.com、 Gmail 和其他电子邮件服务的受保护的邮件。

||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>开始使用 OME 通过激活 Azure 权限管理 Azure 信息保护的一部分

现在，则很容易入门的新 OME 功能。从年 2 月 2018 Office 365 自动启用合格组织内我们数据中心的新 OME 功能。如果为一个新的 Office 365 租户并且您的组织具有相应的订阅，则合格您的组织。**如果已启用 Azure 权限管理 (Azure RMS)，一部分 Azure 信息保护，则我们为您自动启用 Office 365 邮件加密。** 您无需进行任何其他启用 OME 操作。若要激活 Azure 权限管理，请参阅[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。订阅的信息，请参阅"哪些订阅我需要使用新的 OME capabilities?"在[Office 365 邮件加密 FAQ](ome-faq.md)。有关购买订阅 Azure 信息保护信息，请参阅[Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。
  
如果您使用 Exchange Online 与 Active Directory 权限管理服务 (AD RMS)，不能立即启用这些新功能。相反，您需要从迁移 AD RMS 到 Azure 信息保护第一次。完成迁移后，您可以成功完成这些步骤。
  
如果您选择要继续使用本地 AD RMS 与 Exchange Online 而不是迁移到 Azure 信息保护，您将无法使用这些新功能。
  
## <a name="how-the-new-capabilities-for-ome-work"></a>新功能以 OME 的工作方式

新的 Office 365 邮件加密功能使用的保护功能，也称为从 Azure 信息保护的 Azure 权限管理 (Azure RMS)。这包括加密、 标识和授权的策略，以帮助保护您的电子邮件。您可以使用权限管理模板、[不要转发选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)中，和[仅加密选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)加密邮件。用户可以然后加密电子邮件和 Office 365 附件各种使用这些选项。有关受支持的附件类型的完整列表，请参阅["文件类型涵盖时附加到邮件的 IRM 策略"中的电子邮件的 IRM 简介](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。作为管理员，您还可以定义要应用此保护的邮件流规则。例如，您可以定义其中的往特定收件人或包含特定词语的主题行中的所有未受保护的邮件防止未经授权的访问和收件人不能复制或打印邮件的内容的规则。
  
与以前的版本 OME 不同这些新功能提供统一的发件人的体验，是否要在组织内部或外部 Office 365 的收件人发送邮件。此外，接收发送到 Office 365 帐户 Outlook 2016 或 web 上的 Outlook 中受保护的电子邮件收件人无需采取任何其他操作来查看该邮件。无缝工作。收件人使用其他电子邮件客户端和电子邮件服务提供商还具有改进的体验。有关信息，请参阅[了解 Office 365 中的受保护的邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)和[如何打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

OME 的早期版本和新的 OME 功能之间的差异的详细列表，请参阅[比较 OME 的版本](ome-version-comparison.md)。
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>手动设置的新功能，为 OME 步骤

新的 OME 功能将自动启用对于大多数 Office 365 组织中。如果您的组织不自动具有 OME 启用，或者打开关闭的新 OME 功能，请按照以下步骤手动设置的新功能，为 OME。
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>手动设置的新功能，为 OME

1. 确保您的组织具有右订阅。有关订阅的信息，请参阅"哪些订阅我需要使用新的 OME capabilities?"中的[Office 365 邮件加密 FAQ。](ome-faq.md)。有关购买订阅 Azure 信息保护信息，请参阅[Azure 信息保护](https://azure.microsoft.com/services/information-protection/)。

2. 决定是否要在 Microsoft 管理根密钥的 Azure 信息保护 （默认），或生成并管理此密钥自己 （称为使您自己的项或 BYOK）。如果您想要生成并自己管理此项，需要完成一些步骤之前为 OME 设置的新功能。有关详细信息，请参阅[规划和实现您的 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。Microsoft 建议您之前设置 OME 完成这些步骤。

3. 激活 Azure 权限管理 OME 中启用的新功能。有关说明，请参阅[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。当执行此操作时，Office 365 自动启用新的 OME 功能。

    > [!TIP]
    > 在 Web 上的 outlook 缓存其 UI，因此很好办法等待一天之前您尝试使用此客户端的电子邮件的 OME 应用的新功能。用户界面更新以反映新配置之前，新功能以 OME 将不可用。用户界面更新后，用户可以使用适用于 OME 的新功能保护电子邮件。
  
4. （可选）设置新的邮件流规则或更新现有定义如何以及何时要对从组织发出的邮件进行加密的 Office 365 的邮件流规则。

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>验证 OME 的新功能正确配置，可以使用 Windows PowerShell

按照以下步骤，若要验证正确配置您的租户 OME 通过 Exchange Online PowerShell 中使用的新功能。
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。

2. 运行 Test-irmconfiguration cmdlet 使用以下语法：

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   例如：

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    其中电子邮件地址是用户的 Office 365 组织中的电子邮件地址。可选的提供的发件人电子邮件地址强制执行其他检查系统的同时。您的结果应类似于这些：

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not 
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

    其中*Contoso*被替换 Office 365 组织的名称。

    可能不同于上面结果中显示的结果中返回的默认模板的名称。

    模板和信息的默认模板简介，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关不要转发选项，仅用于加密的选项，以及如何创建其他模板或找出哪些权限中包含的现有模板，请参阅[Configuring Azure 权限管理的使用权限](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)。

3. 运行 Remove-pssession cmdlet，以断开 Rights Management 服务。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>后续步骤： 定义使用新的 OME 功能的新邮件流规则

此步骤是可选的新 OME 部署，但是，此步骤是必需的现有 OME 部署的已邮件流规则设置为加密传出邮件。如果您想要利用新的 OME 功能，则必须更新现有的邮件流规则。否则，您的用户将继续接收加密电子邮件，而不是新的、 无缝 OME 体验使用以前的 HTML 附件格式。
  
邮件流规则确定在什么条件电子邮件消息应进行加密，以及删除加密的条件。设置规则操作时，他们正在发送时，匹配的规则条件的任何邮件进行加密。
  
有关邮件流规则的详细信息，请参阅[定义邮件流规则来加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相关主题

[发送、 查看和回复 Outlook 中的加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[启用 Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[定义用于加密 Office 365 中的电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)
