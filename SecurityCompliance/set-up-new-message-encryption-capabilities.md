---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 新的 Office 365 邮件加密功能基于 Azure 信息保护构建, 贵组织可以将受保护的电子邮件通信与组织内部和外部的人员结合使用。新的 OME 功能适用于其他 Office 365 组织、Outlook.com、Gmail 和其他电子邮件服务。
ms.openlocfilehash: eddafca15fa4efdd3f929145e7933a3b7dfb5f27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220642"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>设置全新的 Office 365 邮件加密功能

使用新的 Office 365 邮件加密 (OME) 功能 (它利用 Azure 信息保护中的保护功能), 您的组织可以轻松地与任何设备上的任何人共享受保护的电子邮件。用户可以使用 Outlook.com、Gmail 和其他电子邮件服务, 通过其他 Office 365 组织以及非 Office 365 客户发送和接收受保护的邮件。

||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。 |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>通过激活 azure 权限管理 (azure 信息保护的一部分) 开始使用 OME

现在很容易开始使用新的 OME 功能。从2018年2月到, Office 365 将自动为数据中心内符合条件的组织启用新的 OME 功能。如果您的组织是新的 Office 365 租户, 并且您的组织具有相应的订阅, 则您的组织是符合条件的。**如果已启用 azure 权限管理 (azure RMS) (azure 信息保护的一部分), 我们会自动为你启用 Office 365 邮件加密。** 您无需执行任何其他操作即可启用 OME。若要激活 azure 权限管理, 请参阅[激活 azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。有关订阅的信息, 请参阅[Office 365 邮件加密 FAQ](ome-faq.md)中的 "我需要使用新的 OME capabilities?" 的 "订阅"。有关购买 azure 信息保护订阅的信息, 请参阅[azure 信息保护](https://azure.microsoft.com/services/information-protection/)。
  
如果您使用的是 Active Directory 权限管理服务 (AD RMS) 的 Exchange Online, 则不能立即启用这些新功能。相反, 您需要先从 AD RMS 迁移到 Azure 信息保护。完成迁移后, 您可以成功完成这些步骤。
  
如果你选择继续使用 Exchange Online 的本地 AD RMS, 而不是迁移到 Azure 信息保护, 你将无法使用这些新功能。
  
## <a name="how-the-new-capabilities-for-ome-work"></a>新功能 OME 的工作方式

新的 Office 365 邮件加密功能使用来自 azure 信息保护的保护功能 (也称为 azure 权限管理 (Azure RMS))。这包括加密、标识和授权策略, 以帮助保护您的电子邮件。您可以使用权限管理模板、"不[转发](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)" 和 "[仅加密" 选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)对邮件进行加密。然后, 用户可以使用这些选项来加密电子邮件和各种 Office 365 附件。有关受支持的附件类型的完整列表, 请参阅[关于电子邮件的 irm 简介中的 "在将 irm 策略附加到邮件时受 irm 策略覆盖的文件类型"](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)。作为管理员, 您还可以定义邮件流规则以应用此保护。例如, 您可以定义一个规则, 其中所有发送到特定收件人或包含主题行中特定词语的未受保护邮件都受到保护以防未经授权访问, 并且收件人无法复制或打印邮件的内容。
  
与早期版本的 OME 不同, 这些新功能可提供统一的发件人体验, 无论您是将邮件发送到组织内部还是位于 Office 365 外部的收件人。此外, 收到受保护电子邮件的收件人将发送到 Outlook 2016 中的 Office 365 帐户或 web 上的 outlook, 而无需执行任何其他操作来查看邮件。无缝运行。使用其他电子邮件客户端和电子邮件服务提供商的收件人也具有改进的体验。有关信息, 请参阅[了解 Office 365 中的受保护邮件](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)和[如何打开受保护的邮件](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)。

有关 OME 的早期版本和新的 OME 功能之间的差异的详细列表, 请参阅[比较版本的 OME](ome-version-comparison.md)。
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>手动设置 OME 的新功能的步骤

为大多数 Office 365 组织自动启用新的 OME 功能。如果您的组织未自动启用 OME, 或者您关闭了新的 OME 功能, 请按照以下步骤手动设置 OME 的新功能。
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>手动设置 OME 的新功能

1. 确保您的组织具有正确的订阅。有关订阅的详细信息, 请参阅[Office 365 邮件加密 FAQ](ome-faq.md)中的 "我需要使用新的 OME capabilities?"。。有关购买 azure 信息保护订阅的信息, 请参阅[azure 信息保护](https://azure.microsoft.com/services/information-protection/)。

2. 决定是希望 Microsoft 管理 Azure 信息保护的根键 (默认值), 还是自己生成和管理此项 (称为 "引入自己的密钥" 或 "BYOK")。如果要自己生成和管理此项, 您需要完成一些步骤, 然后才能设置 OME 的新功能。有关详细信息, 请参阅[规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。Microsoft 建议您在设置 OME 之前完成这些步骤。

3. 通过激活 Azure 权限管理来启用 OME 的新功能。有关说明, 请参阅[激活 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)。执行此操作时, Office 365 将自动为你启用新的 OME 功能。

    > [!TIP]
    > Outlook 网页版将缓存其 UI, 因此在尝试将 OME 的新功能应用于使用此客户端的电子邮件之前, 最好先等待一天。在 UI 更新以反映新的配置之前, OME 的新功能将不可用。UI 更新后, 用户可以使用 OME 的新功能保护电子邮件。
  
4. Optional设置新的邮件流规则或更新现有的邮件流规则, 这些规则定义您希望 Office 365 如何以及何时对从您的组织发送的邮件进行加密。

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>使用 Windows PowerShell 验证是否已正确配置 OME 的新功能

按照以下步骤验证您的租户是否已正确配置为使用 OME 通过 Exchange Online PowerShell 的新功能。
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用以下语法运行 get-irmconfiguration cmdlet:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   例如：

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    其中电子邮件地址是您的 Office 365 组织中的用户的电子邮件地址。虽然可选, 但提供发件人电子邮件地址会强制系统执行其他检查。您的结果应如下所示:

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

    其中, *Contoso*被替换为您的 Office 365 组织的名称。

    结果中返回的默认模板的名称可能不同于上述结果中显示的名称。

    有关默认模板的模板和信息的简介, 请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关 "不要转发" 选项、"仅加密" 选项以及如何创建其他模板的信息, 或者要了解现有模板中包含的权限, 请参阅[为 Azure 权限管理配置使用权限](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)。

3. 运行移除-PSSession cmdlet 以断开与 Rights Management service 的连接。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>后续步骤: 定义使用新的 OME 功能的新邮件流规则

此步骤对于新的 OME 部署是可选的, 但是, 对于已设置了邮件流规则以加密传出邮件的现有 OME 部署, 此步骤是必需的。如果要利用新的 OME 功能, 则必须更新现有的邮件流规则。否则, 您的用户将继续接收使用以前的 HTML 附件格式的加密邮件, 而不是新的无缝 OME 体验。
  
邮件流规则确定应对哪些条件加密电子邮件, 以及删除该加密的条件。为规则设置操作时, 与规则条件匹配的任何邮件在发送时都将进行加密。
  
有关邮件流规则的详细信息, 请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相关主题

[在 Outlook 中发送、查看和回复加密邮件](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[Enable-enable-aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[使用远程 PowerShell 连接到 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[定义用于加密 Office 365 中的电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)
