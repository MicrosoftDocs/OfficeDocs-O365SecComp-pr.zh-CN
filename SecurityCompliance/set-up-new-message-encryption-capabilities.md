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
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296185"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>设置全新的 Office 365 邮件加密功能

新的 Office 365 邮件加密 (OME) 功能允许组织与任何设备上的任何人共享受保护的电子邮件。用户可以使用 Outlook.com、Gmail 和其他电子邮件服务与其他 Office 365 组织和非 Office 365 客户交换受保护的邮件。


>[!NOTE]
>本文适用于管理员和 IT 专业人员。如果您是最终用户, 请参阅适用解决方案的[Office 365 邮件加密 (OME)](ome.md)中的文章列表。

请按照下面的步骤操作, 以确保新的 OME 功能在 Office 365 租户中可用。 

## <a name="verify-azure-rights-management-arm-is-active"></a>验证 Azure 权限管理 (ARM) 是否处于活动状态

>[!NOTE]
>新的 OME 功能利用[azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)中的保护功能, 即[azure 权限管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)使用的技术。

使用新的 OME 功能的唯一先决条件是必须在 Office 365 租户中激活[Azure 权限管理 (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) 。如果是这样, Office 365 将自动激活新的 OME 功能, 无需执行任何操作。 

还会自动为最符合条件的计划激活 ARM, 因此您可能不需要在这方面执行任何操作。有关详细信息, 请参阅[激活 Azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)。

>[!IMPORTANT]
>如果将 Active Directory 权限管理服务 (AD RMS) 与 Exchange Online 结合使用, 则需要先[迁移到 Azure 信息保护](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms), 然后才能使用新的 OME 功能。AD RMS 与 ARM 不兼容。  

有关详细信息, 请参阅:

- [使用新的 OME 功能需要什么订阅？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)检查订阅计划是否包含 Azure 信息保护 (包括 ARM)。   
-  有关购买符合条件的订阅的信息, 请参阅[Azure 信息保护](https://azure.microsoft.com/en-us/services/information-protection/)。  

### <a name="manually-activating-arm"></a>手动激活 ARM

如果禁用了 ARM, 或者如果由于某种原因未自动激活, 则可以在中手动激活:

- **Office 365 管理中心**: 有关说明[, 请参阅如何从 Office 365 管理中心激活 Azure 权限管理](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)
- **Azure 门户**: 了解[如何从 azure 门户激活 azure 权限管理](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure), 以获取相关说明。 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>配置 Azure 信息保护租户密钥的管理

这是一个可选步骤。允许 Microsoft 管理 Azure 信息保护的根是默认设置, 为大多数 Office 365 租户提供建议的最佳实践。如果是这种情况, 则无需执行任何操作。 

有许多原因 (例如合规性要求), 可能需要您生成和管理自己的根密钥 (也称为 "引入自己的密钥 (BYOK)")。如果是这种情况, 建议您在设置新的 OME 功能之前完成所需的步骤。有关详细[信息, 请参阅规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>在 Exchange Online PowerShell 中验证新的 OME 配置

您可以验证您的 Office 365 租户是否已正确配置为使用[Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)中的新 OME 功能。
  
1. 使用 Office 365 租户中具有全局管理员权限的帐户[连接到 Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。

2. 使用以下语法运行 get-irmconfiguration cmdlet:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **示例**： 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - 提供发件人电子邮件是可选的, 但强制系统执行其他检查。使用 Office 365 租户中任何用户的电子邮件地址。 
     
    您的结果应类似于:

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

   - 你的 Office 365 组织名称将替换*Contoso*。

   - 默认的模板名称可能与上面显示的不同。有关详细[信息, 请参阅配置和管理用于 Azure 信息保护的模板](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)。

3. 运行移除-PSSession cmdlet 以断开与 Rights Management service 的连接。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a>将邮件流规则更新为使用新的 OME 功能

如果以前配置的邮件流规则用于在 Office 365 租户中[对电子邮件进行加密](define-mail-flow-rules-to-encrypt-email.md), 则需要更新这些现有的规则, 以使用新的 OME 功能。对于新的部署, 此阶段不需要执行此步骤。   

>[!Note]
>邮件流规则定义对电子邮件进行加密的条件, 以及应删除加密的条件。有关详细信息, 请参阅[定义邮件流规则, 以对 Office 365 中的电子邮件进行加密](define-mail-flow-rules-to-encrypt-email.md)。

若要更新现有规则以使用新的 OME 功能, 请执行以下操作:

1. 在 Office 365 管理中心, 转到**管理中心中心 > Exchange**。

2. 在 Exchange 管理中心中, 转到 "**邮件流" > Rules**。 
3. 对于每个规则, 请**执行以下**操作:
    - 选择 **"修改邮件安全性"**。
    - 选择 "**应用 Office 365 邮件加密和权限保护**"。
    - 从列表中选择一个 RMS 模板
    - 选择" **保存** "。
    - 选择“**确定**”。
  
>[!IMPORTANT]
>如果不更新现有的邮件流规则, 则用户将继续接收使用以前的 HTML 附件格式的加密邮件, 而不是新的 OME 功能。
