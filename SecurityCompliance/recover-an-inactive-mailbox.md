---
title: 恢复 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/21/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
description: '如果以前员工返回给您的组织，或新员工加入才能离开员工职责，您可以恢复 Office 365 中的非活动邮箱的内容。非活动邮箱恢复时，它会将其转换为新邮箱包含非活动邮箱的内容。 '
ms.openlocfilehash: dcc84e44454a75f8b4dac953599632d632f340b9
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525962"
---
# <a name="recover-an-inactive-mailbox-in-office-365"></a>恢复 Office 365 中的非活动邮箱

非活动邮箱 （这是一种软删除邮箱） 用于保留以前员工的电子邮件，他/她离开组织之后。如果该员工返回给您的组织或另一个雇员承担前雇员的工作职责，有两种方式，您可以将非活动邮箱的内容提供给用户： 
  
- **恢复非活动邮箱**如果以前的员工返回到您的组织，或者如果新员工加入执行前雇员的工作职责，您可以恢复非活动邮箱的内容。此方法将非活动邮箱转换为新的活动邮箱包含非活动邮箱的内容。将在恢复之后，非活动邮箱不再存在。本主题中的过程介绍了此方法。 
    
- **还原非活动邮箱**如果另一个雇员承担的以前的员工的工作职责或另一个用户需要访问非活动邮箱的内容，您可以还原 （或合并） 到现有邮箱的非活动邮箱的内容。您还可以从非活动邮箱还原存档。此方法的过程，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。
    
有关恢复和还原非活动邮箱之间的差异的详细信息，以及恢复非活动邮箱后所发生情况的描述，请参阅[详细信息](recover-an-inactive-mailbox.md#moreinfo)部分。
  
> [!NOTE]
> 我们已推迟创建新的就地保留进行非活动邮箱的最后期限。但是，有时将来，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。 
  
## <a name="before-you-begin"></a>准备工作

- 您需要使用 Exchange Online PowerShell 中还原非活动邮箱。不能使用 Exchange 管理员中心 (EAC)。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 运行以下命令获取组织中非活动邮箱的标识信息。 

    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

    使用此命令返回的信息来恢复特定的非活动邮箱。
    
- 有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="recover-an-inactive-mailbox"></a>恢复非活动邮箱

使用**New-mailbox** cmdlet 与*InactiveMailbox*参数来恢复非活动邮箱。 
  
1. 创建包含非活动邮箱的属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```
   
    > [!IMPORTANT]
    > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 本示例使用在上一个命令中获得的属性，并恢复到 Ann Beebe 的用户活动邮箱的非活动邮箱。确保在您的组织内唯一的*名称*和*MicrosoftOnlineServicesID*参数指定的值。 

    ```
    New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
    ```

    恢复的非活动邮箱的主 SMTP 地址会*MicrosoftOnlineServicesID*参数指定相同的值。 
    
恢复非活动邮箱后，还将创建新的 Office 365 用户帐户。您必须通过分配许可证来激活此用户帐户。若要在 Office 365 管理中心中分配许可证，请参阅[为 Office 365 商业版分配或取消分配许可证](https://go.microsoft.com/fwlink/p/?LinkId=276798)。
  
## <a name="more-information"></a>详细信息

- **恢复和还原非活动邮箱的主要区别是什么？** 恢复非活动邮箱时，邮箱基本上会转换为一个新邮箱，将保留非活动邮箱的的内容和文件夹结构，并将邮箱链接到新的用户帐户。恢复后，非活动邮箱不再存在，并且对新邮箱中的内容所做的任何更改都会影响最初保留在非活动邮箱中内容。相反，还原非活动邮箱时，只是将内容复制到另一个邮箱。非活动邮箱将保留，并且仍保留非活动状态。对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。仍可以使用就地电子数据展示搜索非活动邮箱，可以将其内容还原到另一个邮箱，也可以在以后将其恢复或删除。 
    
- **恢复非活动邮箱时，会发生什么情况？** 恢复非活动邮箱时，将发生以下事件： 
    
  - 移除诉讼保留（如果已为非活动邮箱启用）。
    
  - 移除就地保留。这意味着将非活动邮箱作为源邮箱从任何就地保留或就地电子数据展示搜索中删除。 
    
  - 从 Office 365 的任何保留策略中删除非活动邮箱，因为应用于它。
    
  - 单个项目恢复期间（由 **RetainDeletedItemsFor** 邮箱属性定义）设置为 30 天。通常情况下，在 Exchange Online 中创建新邮箱时，此保留期设置为 14 天。将此值设置为最大值 30 天，可留出更多时间从非活动邮箱中恢复任何已永久删除（或清除）的数据。您也可以禁用单个项目恢复，或将单个项目恢复期设置为默认的 14 天。有关详细信息，请参阅 [Enable or disable single item recovery for a mailbox](https://go.microsoft.com/fwlink/?linkid=856769)。
    
  - 启用保留挂起时，并且保留保留持续时间设置为 30 天。这意味着，默认 Exchange 保留策略和任何组织范围内或 Exchange 范围内的 Office 365 已分配给新邮箱的保留策略不会处理 30 天。这使返回员工或新的已恢复的非活动邮箱时间的所有者管理旧邮件。否则为在 Exchange 或 Office 365 保留策略可能会删除旧的邮箱项目 （或将项目移动到存档邮箱中，如果已启用） 的已到期基于 Exchange 或 Office 365 保留策略配置的设置。30 天后保留挂起过期， **RetentionHoldEnabled** mailbox 属性设置为**False**，以及托管文件夹助理开始处理分配给邮箱的策略。如果您不需要此的更多时间，您可以只删除保留挂起。此外，您可以使用**Set-mailbox EndDateForRetentionHold**命令增加保留挂起的持续时间。有关详细信息，请参阅[就地保留邮箱保留](https://go.microsoft.com/fwlink/?linkid=856300)。
    
- **置于已恢复的邮箱的保留，如果您需要保留非活动邮箱的原始状态。** 若要防止新邮箱所有者或保留策略从已恢复的非活动邮箱中永久删除任何消息，您可以将邮箱置于诉讼保留的详细信息，请参阅[Place 上诉讼保留的邮箱](https://go.microsoft.com/fwlink/?linkid=856286)。
    
- **哪些用户 ID 您可以使用恢复非活动邮箱时？** 非活动邮箱恢复时，为*MicrosoftOnlineServicesID*参数指定的值可以是不同于原始的非活动邮箱相关联。您还可以使用原始用户 id。但是，如前面所述，请确保非活动邮箱恢复时在您的组织内唯一用于*名称*和*MicrosoftOnlineServicesID*的值。 
    
- **如果非活动邮箱的邮箱保留期尚未过期该怎么办？** 如果非活动邮箱是在 30 天内进行软删除的，则不能使用 **New-Mailbox -InactiveMailbox** 命令对其进行恢复。您必须通过还原相应的 Office 365 用户帐户来恢复它。有关详细信息，请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **如何知道非活动邮箱的软删除邮箱保留期是否已过期？** 运行以下命令。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL ExternalDirectoryObjectId
  ```

    如果不存在 **ExternalDirectoryObjectId** 属性的值，则说明邮箱保留期已过期，您可以通过运行 **New-Mailbox -InactiveMailbox** 命令恢复非活动邮箱。如果存在 **ExternalDirectoryObjectId** 属性的值，则说明软删除邮箱保留期尚未过期，您必须通过还原 Office 365 用户帐户来恢复邮箱。请参阅 [删除或还原用户](https://go.microsoft.com/fwlink/p/?LinkId=279162)。
    
- **考虑后恢复非活动邮箱启用存档邮箱。** 这样可以返回用户或新员工将旧邮件移动到存档邮箱。保留挂起过期时, 的存档策略的默认 Exchange 保留策略分配到 Exchange Online 邮箱移动两年的项目或较旧的存档邮箱到的一部分。如果不启用存档邮箱，两年以前的项目将保留在用户的主邮箱。有关详细信息，请参阅[Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)。
 