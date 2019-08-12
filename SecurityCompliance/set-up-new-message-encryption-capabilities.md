---
title: 设置全新的 Office 365 邮件加密功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 新的 Office 365 邮件加密功能在 Azure 信息保护的基础上构建, 你的组织可使用受保护的电子邮件通信，与组织内部和外部的人员通信。 新的 OME 功能适用于其他 Office 365 组织、Outlook.com、Gmail 和其他电子邮件服务。
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854796"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>设置全新的 Office 365 邮件加密功能

通过新的 Office 365 邮件加密 (OME) 功能，组织可与任何设备上的任何人共享受保护的电子邮件。 用户可使用 Outlook.com、Gmail 和其他电子邮件服务与其他 Office 365 组织以及非 Office 365 客户交换受保护的邮件。

||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。 本文面向管理员和 IT 专业人员。 如果只是在查找发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合你的需求的文章。 |
||

请按照下列步骤操作，确保 Office 365 组织中提供了新的 OME 功能。

## <a name="verify-that-azure-rights-management-is-active"></a>验证 Azure 权限管理处于活跃状态

全新的 OME 功能利用[Azure 权限管理服务 (Azure RMS)](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-information-protection)中的保护功能, 它是[Azure 信息保护](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)用于通过加密和访问控制来保护电子邮件和文档的技术。

使用全新的 OME 功能的唯一前提是必须在组织的租户中激活[Azure 权限管理](https://docs.microsoft.com/zh-CN/azure/information-protection/what-is-azure-rms)。 如果是这样，Office 365 将自动激活全新的 OME 功能，无需执行任何操作。

对于最符合条件的计划，也会自动激活 Azure RMS，因此你可能也不需要在此方面执行任何操作。 有关详细信息，请参阅[激活 Azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。

>[!IMPORTANT]
>如果通过 Exchange Online 使用 Active Directory 权限管理服务 (AD RMS)，则需要先[迁移到 Azure 信息保护](https://docs.microsoft.com/zh-CN/azure/information-protection/migrate-from-ad-rms-to-azure-rms)，然后才能使用全新的 OME 功能。 OME 与 AD RMS 不兼容。  

有关详细信息，请参阅：

- [使用新的 OME 功能需要订阅什么？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)检查你的订阅计划是否包含 Azure 信息保护 (包括 Azure RMS 功能)。
- 针对购买符合条件的订阅的[Azure 信息保护](https://azure.microsoft.com/en-us/services/information-protection/)。  

### <a name="manually-activating-azure-rights-management"></a>请手动激活 Azure 权限管理

如果禁用了 Azure RMS，或者由于某种原因未自动激活，则可在以下各项中将其手动激活：

- 
  **Microsoft 365 管理中心**：有关说明，请参阅[如何从管理中心激活 Azure 权限管理](https://docs.microsoft.com/zh-CN/azure/information-protection/activate-office365)。
- **Azure 门户**：有关说明，请参阅[如何从 Azure 门户激活 Azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>配置 Azure 信息保护租户密钥的管理

这是一个可选步骤。 允许 Microsoft 管理 Azure 信息保护的根密钥是默认设置，并且是推荐给为大多数 Office 365 租户使用的最佳做法。 如果是这种情况, 则无需执行任何操作。

有多种原因（例如合规性要求）可能需要您生成和管理自己的根密钥（也称为自带密钥 (BYOK)）。 如果是这种情况，我们建议你在设置新的 OME 功能前完成所需的步骤。 有关详细信息，请参阅[规划和实施 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>在 Exchange Online PowerShell 中验证新的 OME 配置

可验证 Office 365 租户是否已正确配置为使用[Exchange Online PowerShell](https://docs.microsoft.com/zh-CN/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的新 OME 功能。
  
1. 使用 Office 365 租户中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/zh-CN/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

2. 运行 Get-IRMConfiguration cmdlet。

     将看到 AzureRMSLicensingEnabled 参数的值 $True, 它表示在租户中配置了 OME。 如果未配置，请使用 Set-IRMConfiguration 将 AzureRMSLicensingEnabled 的值设置为 $True 以启用 OME。

3. 使用以下语法运行 Test-IRMConfiguration cmdlet：

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **示例**：

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - 向发件人提供电子邮件是可选项，但会强制系统执行其他检查。 使用 Office 365 租户中任何用户的电子邮件地址。

     结果应类似于：

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

   - Office 365 组织名称将替换*Contoso*。

   - 默认模板名称可能与上面显示的不同。 有关详细信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/zh-CN/azure/information-protection/configure-policy-templates)。

4. 运行 Remove-PSSession cmdlet，从权限管理服务断开连接。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>后续步骤：定义邮件流规则以使用新的 OME 功能

如果有之前配置的用于在 Office 365 组织中对电子邮件进行加密的邮件流规则，则需要更新现有规则，以使用新的 OME 功能。 对于新部署，你需要创建新的邮件流规则。

>[!IMPORTANT]
>如果不更新现有的邮件流规则，你的用户将继续收到使用之前的 HTML 附件格式的加密邮件，而不是新的无缝 OME 体验。

邮件流规则确定应在哪些条件下对电子邮件进行加密，以及删除该加密的条件。 为规则设置操作时, 任何匹配规则条件的邮件都会在发送时进行加密。
  
有关创建 OME 邮件流规则的步骤，请参阅[定义邮件流规则以在 Office 365 中加密电子邮件](define-mail-flow-rules-to-encrypt-email.md)。

若要更新现有规则以使用新的 OME 功能，请执行以下操作：

1. 在 Microsoft 365 管理中心，转到“**管理中心>Exchange”。
2. 在 Exchange 管理中心，转到“**邮件流>规则**”。
3. 对于每条规则, 在**执行下列操作**中：
    - 选择“**修改邮件安全性**”。
    - 选择“**应用 Office 365 邮件加密和权限保护**”。
    - 从列表中选择 RMS 模板。
    - 选择“**保存**”。
    - 选择“**确定**”。
