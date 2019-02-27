---
title: 在 Office 365 中启用邮箱审核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中, 可以启用邮箱审核日志记录, 以记录邮箱所有者、代理和管理员的邮箱访问权限。默认情况下, 未打开 Office 365 中的邮箱审核。为邮箱启用邮箱审核日志记录后, 可以在 Office 365 审核日志中搜索在该邮箱上执行的活动。
ms.openlocfilehash: a9bc84bad8532dd546d5ce3e2f149151967050d6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295915"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>在 Office 365 中启用邮箱审核
  
在 Office 365 中, 可以启用邮箱审核日志记录, 以记录邮箱所有者、代理和管理员的邮箱访问权限。默认情况下, 未打开 Office 365 中的邮箱审核。这意味着, 当您搜索 Office 365 审核日志中的邮箱活动时, 邮箱审核事件不会出现在结果中。但在为用户邮箱启用邮箱审核日志记录后, 您可以在审核日志中搜索邮箱活动。此外, 当邮箱审核日志记录打开时, 默认情况下会记录管理员、委派和所有者执行的某些操作。若要记录 (然后搜索) 其他操作, 请参阅第3步。

## <a name="before-you-begin"></a>准备工作
  
- 您必须使用 Exchange Online PowerShell 启用邮箱审核日志记录。您不能使用 "Office 365 &amp;安全合规中心" 或 "Exchange 管理中心"。
    
- 您无法对与 Microsoft 团队中的 Office 365 组或团队相关联的邮箱启用邮箱审核日志记录。
    
- 分配了用户邮箱"完全访问"权限的管理员被视为委派用户。
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>步骤 1: 连接到 Exchange Online PowerShell

1. 在本地计算机上，打开 Windows PowerShell 并运行以下命令。
   
    ```
    $UserCredential = Get-Credential
    ```

2. 在 " **Windows PowerShell 凭据请求**" 对话框中, 键入 Office 365 全局管理员帐户的用户名和密码, 然后单击 **"确定"**。
    
3. 运行以下命令：
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. 运行以下命令。

    ```
    Import-PSSession $Session
    ```
   
4. 要验证您是否已连接至您的 Exchange Online 组织，请运行以下命令获取组织中所有邮箱的列表。
    
    ```
    Get-Mailbox
    ```
  
有关详细信息，或者如果您在连接到 Exchange Online 组织时遇到问题，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。
  
## <a name="step-2-enable-mailbox-audit-logging"></a>步骤 2：启用邮箱审核日志记录

在连接到 Exchange Online 组织后, 使用 PowerShell 启用邮箱的邮箱审核日志记录。或者, 您可以为组织中的所有邮箱启用邮箱审核。
  
本示例为 Pilar Pinilla 的邮箱启用邮箱审核日志记录。
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

本示例为您组织中的所有用户邮箱启用邮箱审核日志记录。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>步骤 3：指定要审核的所有者操作

为邮箱启用审核时, 默认情况下会审核邮箱所有者执行的某些操作。您必须指定要审核的其他所有者操作。有关默认情况下记录的所有者操作以及可以审核的其他操作的列表和说明, 请参阅 "[邮箱审核操作](#mailbox-auditing-actions)" 部分中的表。 
  
本示例将**mailboxlogin 该值**和**HardDelete**所有者操作添加到 Pilar Pinilla 邮箱的邮箱审核中。本示例假定已为此邮箱启用了邮箱审核。 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

本示例为 "Don 大厅" 的邮箱启用邮箱审核日志记录, 并指定仅记录由邮箱所有者执行的**mailboxlogin 该值**操作。请注意, 此示例覆盖默认的 UpdateFolderPermissions 操作。 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
本示例将**mailboxlogin 该值**、 **HardDelete**和**SoftDelete** owner 操作添加到组织中的所有邮箱。本示例假定已对所有邮箱启用了邮箱审核。 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已为某个邮箱成功启用邮箱审核日志记录，请使用 **Get-Mailbox** cmdlet 检索该邮箱的审核设置。 
  
本示例检索 Pilar Pinilla 的审核设置。

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
本示例为您组织中的所有用户邮箱检索审核设置。

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
**AuditEnabled**属性的值**为 True**时, 将验证是否已启用邮箱审核日志记录。 
    
## <a name="mailbox-auditing-actions"></a>邮箱审核操作
  
下表列出了邮箱审核日志记录可以记录的操作。该表包含可为不同用户登录类型记录的操作。在表中, "**否**" 表示无法为该登录类型记录操作。星号 ( **\*** ) 表示为邮箱启用邮箱审核日志记录时, 默认情况下会记录该操作。 
  
|**操作**|**说明**|**管理员**|**委派用户\*\*\***|**所有者**|
|:-----|:-----|:-----|:-----|:-----|
|**复制** <br/> |已将某个邮件复制到另一个文件夹。  <br/> |是  <br/> |不支持  <br/> |否  <br/> |
|**创建** <br/> |在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建项;例如, 创建一个新的会议请求。请注意, 不会审核创建、发送或接收邮件。此外, 还不会审核创建邮箱文件夹的情况。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**FolderBind** <br/> |已访问某个邮箱文件夹。当管理员或代理人打开邮箱时，也将记录此操作。  <br/> |是  <br/> |是\*\*  <br/> |否  <br/> |
|**HardDelete** <br/> |已将某个邮件从"已恢复邮件"文件夹中清除。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**mailboxlogin 该值** <br/> |用户登录其邮箱。  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**MessageBind** <br/> |在预览窗格查看邮件或打开邮件。  <br/> |是  <br/> |不支持  <br/> |否  <br/> |
|**移动** <br/> |已将某个邮件移至另一个文件夹。  <br/> |是  <br/> |支持  <br/> |可访问  <br/> |
|**MoveToDeletedItems** <br/> |已将某个邮件删除并移至“已删除邮件”文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**SendAs** <br/> |已使用 SendAs 权限发送某个邮件。这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SendOnBehalf** <br/> |已使用 SendOnBehalf 权限发送某个邮件。这表示另一个用户代表邮箱所有者发送了邮件。此邮件向收件人表明，此邮件是代表谁发送的以及实际发送此邮件的是谁。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SoftDelete** <br/> |已将某个邮件永久删除或从“已删除邮件”文件夹中删除。软删除的项目将移至“可恢复的项目”文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**更新** <br/> |已更改某个邮件或其属性。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**UpdateCalendarDelegation** <br/> |向邮箱分配了日历委派。日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。  <br/> |是\*  <br/> |否  <br/> |是\*  <br/> |
|**UpdateFolderPermissions** <br/> |更改了文件夹权限。文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateInboxRules** <br/> |已添加、删除或更改收件箱规则。"收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup> 如果为邮箱启用了审核功能，则默认为已审核。<br/><br/>  <sup>\*\*</sup>合并由代理人执行的文件夹绑定操作的条目。在24小时的时间跨度内为单个文件夹访问生成一个日志条目。<br/><br/><sup>\*\*\*</sup>已向其分配了对用户邮箱的完全访问权限的管理员被视为委派用户。 
  
如果不再需要审核特定类型的邮箱操作, 则应修改邮箱的审核日志记录配置, 以禁用这些操作。在达到审核日志条目的保留期限限制之前, 不会清除现有日志条目。有关审核日志条目保留期限的详细信息, 请参阅在[Office 365 Security & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#before-you-begin)中的 "开始之前" 部分。
  
## <a name="more-infotab"></a>[详细信息](#tab/)
  
- 使用 Office 365 审核日志搜索已记录的邮箱活动。您可以搜索特定用户邮箱的活动。下面的屏幕截图显示了您可以在 Office 365 审核日志中搜索的邮箱活动的列表。请注意, 这些活动与本主题中的 "邮箱审核操作" 一节中所述的操作相同。
    
    ![通过在 "活动" 下拉列表中选择 "Exchange 邮箱活动", 可以在 Office 365 审核日志中搜索邮箱审核操作](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    下表介绍了可以搜索的每个邮箱活动并显示相应的邮箱审核操作。
    
    |**审核日志中的活动**|**邮箱审核操作**|
    |:-----|:-----|
    |创建的邮箱项目  <br/> |Create  <br/> |
    |将邮件复制到另一个文件夹  <br/> |Copy  <br/> |
    |登录到邮箱的用户  <br/> |mailboxlogin 该值  <br/> |
    |使用 "代表发送" 权限发送的邮件  <br/> |SendOnBehalf  <br/> |
    |已清除邮箱中的邮件  <br/> |HardDelete  <br/> |
    |将邮件移动到 "已删除邮件" 文件夹  <br/> |MoveToDeletedItems  <br/> |
    |将邮件移动到另一个文件夹  <br/> |Move  <br/> |
    |使用 "代理发送" 权限发送邮件  <br/> |SendAs  <br/> |
    |更新的邮件  <br/> |Update  <br/> |
    |从 "已删除邮件" 文件夹中删除邮件  <br/> |SoftDelete  <br/> |
    |向文件夹添加了权限  <br/> |UpdateFolderPermissions  <br/> |
    |修改文件夹的权限  <br/> |UpdateFolderPermissions  <br/> |
    |从文件夹删除权限  <br/> |UpdateFolderPermissions  <br/> |
    |添加或删除了具有 "代理访问日历" 文件夹的用户  <br/> |UpdateCalendarDelegation  <br/> |
   
    请注意, 所**添加的代理邮箱权限**和**已删除的代理邮箱权限**活动在前面的屏幕截图中并不与邮箱审核操作相关。它们指示管理员是否分配或删除了 FullAccess 邮箱权限。 
    
    有关 office 365 审核日志的信息, 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。
    
- 只有在以下情况下，才视为由管理员访问邮箱：
    
  - Exchange Online 中的就地电子数据展示或 Office 365 中的内容搜索用于搜索邮箱。
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用于访问邮箱。 
    
- 为邮箱启用审核日志记录时，也可以指定将记录每种登录类型（管理员、委派用户或所有者）的哪些用户操作（例如，访问、移动或删除邮件）。 
    
- 若要禁用邮箱审核日志记录，请运行以下命令：

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- 运行 "**获取邮箱**" cmdlet 时, 不会显示为每种类型的用户审核的操作。但您可以运行以下命令来显示特定用户登录类型的所有已审核操作。 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- 您还可以导出邮箱审核日志, 并指定要为一个或多个用户包括的条目。报告和审核日志中的每个条目都包含有关执行操作的执行者以及执行操作的时间以及操作是否成功的信息。有关详细信息, 请参阅[导出邮箱审核日志](https://go.microsoft.com/fwlink/p/?LinkID=404104)。
