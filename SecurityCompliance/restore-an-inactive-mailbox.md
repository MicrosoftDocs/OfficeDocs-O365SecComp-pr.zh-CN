---
title: 在 Office 365 中还原非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 如果新员工或其他用户需要访问 Office 365 中非活动邮箱的内容, 则可以将非活动邮箱的内容还原 (或合并) 到现有邮箱。
ms.openlocfilehash: 671b13b913cddcfc3a7784d621b01b864b07e4e3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214232"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>在 Office 365 中还原非活动邮箱

非活动邮箱 (一种软删除的邮箱类型) 用于在离开组织后保留前一个员工的电子邮件。如果其他员工承担 departed 员工的工作职责, 或者如果该员工返回到您的组织, 则可以通过两种方式使非活动邮箱的内容对用户可用: 
  
- **还原非活动邮箱** 如果另一名员工接替离职员工的工作职责，或者如果另一个用户需要访问非活动邮箱的内容，您可以将非活动邮箱的内容还原（或 合并）到某个现有邮箱。您还可以从非活动邮箱还原存档。还原后，非活动邮箱将保留，并仍保留为非活动状态。本主题介绍还原非活动邮箱的过程。 
    
- **恢复非活动邮箱**如果 departed 员工返回到您的组织, 或者要雇用新员工来承担 departed 员工的工作职责, 则可以恢复非活动邮箱的内容。此方法将非活动邮箱转换为包含非活动邮箱内容的新邮箱。恢复后, 非活动邮箱将不再存在。有关分步过程, 请参阅[在 Office 365 中恢复非活动邮箱](recover-an-inactive-mailbox.md)。
    
有关还原和恢复非活动邮箱之间的差异的更多详细信息, 请参阅本文中的**详细信息**一节。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须使用 Exchange Online PowerShell 来还原非活动邮箱。您不能使用 Exchange 管理中心 (EAC)。有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
- 在 Exchange Online PowerShell 中运行以下命令, 以获取组织中非活动邮箱的标识信息。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     使用此命令返回的信息来还原特定的非活动邮箱。
    
- 有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。
    
## <a name="restore-an-inactive-mailbox"></a>还原非活动邮箱

将 **New-MailboxRestoreRequest** cmdlet 与  _SourceMailbox_ 和  _TargetMailbox_ 参数一起使用，将非活动邮箱的内容还原到现有邮箱。有关使用此 cmdlet 的详细信息，请参阅 [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)。
  
1. 创建包含非活动邮箱的属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 将非活动邮箱的内容还原到现有邮箱。非活动邮箱（源邮箱）的内容将合并到现有邮箱（目标邮箱）中的相应文件夹。
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   或者，可以指定要从非活动邮箱还原内容的目标邮箱中的顶级文件夹。如果指定的目标文件夹或目标文件夹结构在目标邮箱中不存在，将在还原过程中创建。 
    
    本示例将邮箱项目和子文件夹从非活动邮箱复制到目标邮箱的顶级文件夹结构中一个名为"非活动邮箱"的文件夹。
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>从非活动邮箱还原存档

如果非活动邮箱具有存档邮箱，您还可以将其还原到现有邮箱的存档邮箱。要从非活动邮箱还原存档，必须向用于还原非活动邮箱的命令添加  _SourceIsArchive_ 和  _TargetIsAchive_ 开关。 
  
1. 创建包含非活动邮箱的属性的变量。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 在上一命令中，使用 **DistinguishedName** 或 **ExchangeGUID** 属性的值来标识非活动邮箱。这些属性对于您组织中的每个邮箱都是唯一的，但活动和非活动邮箱可能具有相同的主 SMTP 地址。 
  
2. 将非活动邮箱的存档（源存档）内容还原到现有邮箱的存档（目标存档）。在此示例中，将源存档的内容复制到目标邮箱的存档中一个名为"非活动邮箱存档"的文件夹。

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>更多信息

- **恢复和还原非活动邮箱的主要区别是什么？** 在恢复非活动邮箱时, 邮箱将转换为新邮箱, 保留非活动邮箱的内容和文件夹结构, 并将邮箱链接到新的用户帐户。恢复后, 非活动邮箱将不再存在, 对新邮箱中的内容所做的任何更改都将影响最初在非活动邮箱中保留的内容。反过来, 还原非活动邮箱时, 只是将内容复制到另一个邮箱。非活动邮箱将保留并保持非活动状态的邮箱。对目标邮箱中的内容所做的任何更改都不会影响非活动邮箱中保留的原始内容。仍然可以使用 Office 365 安全&amp;合规中心中的[内容搜索工具](run-a-content-search-in-the-security-and-compliance-center.md)搜索非活动邮箱, 可以将其内容还原到另一个邮箱, 也可以在以后恢复或删除它。 
    
- **如何查找非活动邮箱？** 要获取您组织中的非活动邮箱的列表，并显示可用于恢复非活动邮箱的信息，可以运行此命令。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **使用诉讼保留或 Office 365 保留策略保留非活动邮箱内容。** 如果要在还原非活动邮箱后保留该邮箱的状态, 可以在还原非活动邮箱之前将目标邮箱置于[诉讼保留](https://go.microsoft.com/fwlink/?linkid=856286)或应用[Office 365 保留策略](retention-policies.md)。这将阻止在将非活动邮箱还原到目标邮箱之后永久删除这些项目。 
    
- 在**还原非活动邮箱之前, 请先在目标邮箱上启用保留挂起。** 由于非活动邮箱中的邮箱项目可能是旧的, 因此在还原非活动邮箱之前, 可以考虑在目标邮箱上启用保留挂起。将邮箱放在保留挂起中时, 在删除保留挂起或保留挂起期过期之前, 不会处理分配给它的保留策略。这将为目标邮箱的所有者提供管理非活动邮箱的旧邮件的时间。否则, 保留策略可能会删除旧项目 (或根据为目标邮箱配置的保留设置, 将项目移至存档邮箱 (如果已启用)。有关详细信息, 请参阅[在 Exchange Online 中将邮箱置于保留挂起](https://go.microsoft.com/fwlink/?linkid=856300)状态。
    
- **AllowLegacyDNMismatch 开关有什么作用？** 在上面的示例中, 还原非活动邮箱时, **AllowLegacyDNMismatch**开关用于允许将非活动邮箱还原到不同的目标邮箱。在典型的还原方案中, 目标是还原源邮箱和目标邮箱是同一个邮箱的内容。因此, 默认情况下, **new-mailboxrestorerequest** cmdlet 会进行检查以确保源邮箱和目标邮箱上的**LegacyExchangeDN**属性值相同。这有助于防止您意外地将源邮箱还原到错误的目标邮箱中。如果您尝试在不使用**AllowLegacyDNMismatch**开关的情况下还原非活动邮箱, 则在源邮箱和目标邮箱的**LegacyExchangeDN**属性值不同的情况下, 该命令可能会失败。 
    
- **可以使用 New-MailboxRestoreRequest cmdlet 与其他参数实现非活动邮箱的其他还原方案。** 例如，您可以运行此命令，将非活动邮箱的存档还原到目标邮箱的主邮箱。 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  通过运行此命令，还可以将非活动的主邮箱还原到目标邮箱的存档中。

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **TargetRootFolder 参数有什么作用？** 如前面所述，您可以使用 **TargetRootFolder** 参数指定将向其还原非活动邮箱内容的目标邮箱中文件夹结构顶部的一个文件夹（也称为 根）。如果不使用此参数，非活动邮箱中的邮箱项目将合并到目标邮箱相应的默认文件夹中，并在目标邮箱的根目录中重新创建自定义文件夹。下图重点说明不使用和使用 **TargetRootFolder** 参数的区别。 
    
    **不使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**
    
    ![不使用 TargetRootFolder 参数时的屏幕截图](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **使用 TargetRootFolder 参数时目标邮箱中的文件夹层次结构**
    
    ![使用 TargetRootFolder 参数时的屏幕截图](media/300da592-7323-48db-b8a4-07012259d113.png)

  

