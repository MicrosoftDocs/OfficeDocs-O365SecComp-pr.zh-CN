---
title: 在 Office 365 中恢复非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果以前的员工返回到您的组织, 或者如果雇用新员工来承担 departed 员工的工作职责, 则可以在 Office 365 中恢复非活动邮箱的内容。 恢复非活动邮箱时, 会将其转换为新邮箱, 其中包含非活动邮箱的内容。 '
ms.openlocfilehash: c7f942c518dcc74a4bdb37d67e27e8a63879ab46
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999815"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>在 Office 365 中恢复非活动邮箱

非活动邮箱（一种软删除的邮箱）用于在之前员工离开您的组织后保留他/她的电子邮件。 如果该员工返回到您的组织或其他员工承担前一个员工的工作职责, 则可以通过两种方法使非活动邮箱的内容对用户可用: 
  
- **恢复非活动邮箱**如果以前的员工返回到您的组织, 或者雇用新员工来承担前一个员工的工作职责, 则可以恢复非活动邮箱的内容。 此方法将非活动邮箱转换为一个新的活动邮箱, 其中包含非活动邮箱的内容。 恢复后，非活动邮箱不再存在。 本主题中的过程描述了此方法。 
    
- **还原非活动邮箱**如果其他员工承担前一个员工的工作职责, 或者如果其他用户需要访问非活动邮箱的内容, 则可以将非活动邮箱的内容还原 (或合并) 到现有邮箱。 您还可以从非活动邮箱还原存档。 有关此方法的过程, 请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
    
有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[详细信息](#more-information)部分。
  
> [!NOTE]
> 我们推迟了创建新的就地保留的截止时间, 以使邮箱处于非活动状态。 但在将来的某一时刻, 你将无法在 Exchange Online 中创建新的就地保留。 在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。 不过，处于就地保留的现有非活动邮箱仍受支持，可以继续管理这些非活动邮箱的就地保留。 这包括更改就地保留的持续时间，以及通过删除就地保留来永久删除非活动邮箱。 
  
## <a name="before-you-begin"></a>开始之前

- 您必须使用 Exchange Online PowerShell 来还原非活动邮箱。 不能使用 Exchange 管理中心 (EAC)。 有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 运行以下命令获取组织中非活动邮箱的标识信息。 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    使用此命令返回的信息来恢复特定的非活动邮箱。
    
- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

将**新邮箱**cmdlet 与*InactiveMailbox*参数一起使用可恢复非活动邮箱。 
  
1. 创建包含非活动邮箱的属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 此示例使用在上一个命令中获取的属性，并将非活动邮箱恢复到用户 Ann Beebe 的活动邮箱。 请确保为*Name*和*MicrosoftOnlineServicesID*参数指定的值在您的组织中是唯一的。 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    已恢复的非活动邮箱的主 SMTP 地址将与*MicrosoftOnlineServicesID*参数指定的值相同。 
    
恢复非活动邮箱后，还将创建新的 Office 365 用户帐户。 您必须通过分配许可证来激活此用户帐户。 若要在 Microsoft 365 管理中心分配许可证，请参阅[分配或取消分配 Office 365 商业版许可证](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>更多信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。非活动邮箱将保留，并且仍保留非活动状态。对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 
    
- **恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件： 
    
  - 移除诉讼保留（如果已为非活动邮箱启用）。
    
  - 移除就地保留。这意味着将非活动邮箱作为源邮箱从任何就地保留或就地电子数据展示搜索中删除。 
    
  - 非活动邮箱将从应用于它的任何 Office 365 保留策略中删除。
    
  - 单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)。
    
  - 保留挂起已启用，保留挂起持续时间设置为 30 天。 这意味着, 分配给新邮箱的默认 Exchange 保留策略和任何组织范围或 Exchange 范围的 Office 365 保留策略将不会被处理30天。 这使复职员工或恢复的非活动邮箱的新所有者有时间来管理旧邮件。 否则, exchange 或 office 365 保留策略可能会删除旧邮箱项目 (或根据为 Exchange 或 Office 365 保留策略配置的设置, 将项目移至存档邮箱 (如果已启用)。 30天后, 保留挂起会过期, **RetentionHoldEnabled**邮箱属性设置为**False**, 并且托管文件夹助理将开始处理分配给邮箱的策略。 如果您不需要此额外的时间，则可以删除保留挂起。 您也可以使用 **Set-Mailbox -EndDateForRetentionHold** 命令，增加保留挂起的持续时间。 有关详细信息，请参阅 [Place a mailbox on retention hold](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **如果您需要保留非活动邮箱的原始状态，请将恢复的邮箱置于保留状态。** 若要防止新邮箱所有者或保留策略从已恢复的非活动邮箱中永久删除任何邮件, 可以将邮箱置于诉讼保留中。有关详细信息, 请参阅[将邮箱置于诉讼保留状态](https://go.microsoft.com/fwlink/?linkid=856286)。
    
- **恢复非活动邮箱时可以使用哪些用户 ID？** 恢复非活动邮箱时, 为*MicrosoftOnlineServicesID*参数指定的值可能与与非活动邮箱关联的原始值不同。 您还可以使用原始用户 ID。 但如前面所述, 在恢复非活动邮箱时, 请确保用于*Name*和*MicrosoftOnlineServicesID*的值在组织内是唯一的。 
    
- **如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。您必须通过还原相应的 Office 365 用户帐户来恢复它。有关详细信息，请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。如果存在 **ExternalDirectoryObjectId** 属性的值，则说明软删除邮箱保留期尚未过期，您必须通过还原 Office 365 用户帐户来恢复邮箱。请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **请考虑在恢复非活动邮箱后启用存档邮箱。** 这样，复职用户或新员工就可以将旧邮件移动到存档邮箱。 当保留挂起过期时, 作为分配给 Exchange Online 邮箱的默认 Exchange 保留策略的一部分的存档策略将把两年或更早的项目移动到存档邮箱中。 如果未启用存档邮箱，早于两年的项目将保留在用户的主邮箱中。 有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中启用存档邮箱](enable-archive-mailboxes.md)。
 