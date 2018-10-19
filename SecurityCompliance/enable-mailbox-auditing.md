---
title: 在 Office 365 中启用邮箱审核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中，您可以打开邮箱审核日志记录，记录邮箱所有者、 委派和管理员访问邮箱。默认情况下，Office 365 中的邮箱审核功能不被打开的。启用邮箱审核日志记录邮箱后，您可以搜索活动执行邮箱上的 Office 365 审核日志。
ms.openlocfilehash: 6d3de226e7c0e03be824b14e1b16fadaae3f040e
ms.sourcegitcommit: 8294182d4dd124f035a221de0b90159ef7eec4ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "25639661"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>在 Office 365 中启用邮箱审核
  
在 Office 365 中，您可以打开邮箱审核日志记录，记录邮箱所有者、 委派和管理员访问邮箱。默认情况下，Office 365 中的邮箱审核功能不被打开的。这意味着邮箱审核事件时搜索邮箱活动的 Office 365 审核日志不会显示在结果中。但您启用邮箱审核日志记录用户邮箱后，您可以搜索邮箱活动的审核日志。此外，当邮箱审核日志记录处于打开状态，由管理员，代理人执行某些操作并所有者记录默认情况下。记录 （和然后搜索） 其他操作，请参阅 Step 3。

## <a name="before-you-begin"></a>开始之前
  
- 您必须使用 Exchange Online PowerShell 中启用邮箱审核日志记录。不能使用 Office 365 安全性&amp;合规性中心或 Exchange 管理员中心。
    
- 无法启用邮箱审核日志记录的邮箱，与 Office 365 组或团队中的 Microsoft 团队相关联。
    
- 分配了用户邮箱"完全访问"权限的管理员被视为委派用户。
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>步骤 1： 连接到 Exchange Online PowerShell 中

1. 在本地计算机上，打开 Windows PowerShell 并运行以下命令。
   
    ```
    $UserCredential = Get-Credential
    ```

2. 在**Windows PowerShell 凭据请求**对话框中，键入用户名和密码的 Office 365 全局管理员帐户，，然后单击**确定**。
    
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

在连接到 Exchange Online 组织后，使用 PowerShell 启用邮箱审核日志记录邮箱。此外，您可以启用邮箱审核您的组织中所有邮箱。
  
本示例启用邮箱审核日志记录 Pilar Pinilla 的邮箱。
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

本示例为您组织中的所有用户邮箱启用邮箱审核日志记录。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>步骤 3：指定要审核的所有者操作

启用邮箱审核时，默认情况下审核邮箱所有者执行一些操作。您必须指定审核其他所有者操作。请参阅列表以及默认情况下记录的所有者操作和可审核的其他操作的说明[邮箱审核操作](#mailbox-auditing-actions)部分中的表。 
  
本示例将**MailboxLogin**和**HardDelete**所有者操作添加到邮箱审核 Pilar Pinilla 的邮箱。本示例假定的邮箱审核已启用此邮箱。 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

本示例启用邮箱审核日志记录 Don 大厅邮箱，并指定邮箱所有者执行的**MailboxLogin**操作将会记录。请注意，本示例会覆盖默认 UpdateFolderPermissions 操作。 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
本示例向组织中所有邮箱的**MailboxLogin**、 **HardDelete**和**SoftDelete**所有者操作。本示例假定的邮箱审核已启用的所有邮箱。 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>怎样才能知道这是否已正常工作？

若要验证是否已为某个邮箱成功启用邮箱审核日志记录，请使用 **Get-Mailbox** cmdlet 检索该邮箱的审核设置。 
  
本示例检索 Pilar Pinilla 的审核设置。

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
本示例为您组织中的所有用户邮箱检索审核设置。

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
**AuditEnabled**属性的值为**True**验证该邮箱审核日志记录已启用。 
    
## <a name="mailbox-auditing-actions"></a>邮箱审核操作
  
下表列出了可以由邮箱记录的操作审核日志记录。表包含了可以为不同用户登录类型记录的操作。在表中，**否**指示操作无法会为该登录类型记录。星号 ( **\*** ) 指示为邮箱启用了邮箱审核日志记录时，默认情况下记录操作。 
  
|**操作**|**说明**|**管理员**|**委派用户\*\*\***|**所有者**|
|:-----|:-----|:-----|:-----|:-----|
|**复制** <br/> |已将某个邮件复制到另一个文件夹。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**创建** <br/> |邮箱; 中的日历、 联系人、 备注或任务文件夹中创建项目例如，创建一个新的会议请求。请注意，不审核创建、 发送或接收邮件。此外，不审核创建邮箱文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**记录 FolderBind** <br/> |已访问某个邮箱文件夹。当管理员或代理人打开邮箱时，也将记录此操作。  <br/> |是  <br/> |是\*\*  <br/> |否  <br/> |
|**HardDelete** <br/> |已将某个邮件从"已恢复邮件"文件夹中清除。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**MailboxLogin** <br/> |用户登录其邮箱。  <br/> |否  <br/> |否  <br/> |是  <br/> |
|**MessageBind** <br/> |在预览窗格查看邮件或打开邮件。  <br/> |是  <br/> |否  <br/> |否  <br/> |
|**移动** <br/> |已将某个邮件移至另一个文件夹。  <br/> |是  <br/> |是  <br/> |是  <br/> |
|**MoveToDeletedItems** <br/> |已将某个邮件删除并移至“已删除邮件”文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**SendAs** <br/> |已使用 SendAs 权限发送某个邮件。这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SendOnBehalf** <br/> |已使用 SendOnBehalf 权限发送某个邮件。这表示另一个用户代表邮箱所有者发送了邮件。此邮件向收件人表明，此邮件是代表谁发送的以及实际发送此邮件的是谁。  <br/> |是\*  <br/> |是\*  <br/> |否  <br/> |
|**SoftDelete** <br/> |已将某个邮件永久删除或从“已删除邮件”文件夹中删除。软删除的项目将移至“可恢复的项目”文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**更新** <br/> |已更改某个邮件或其属性。  <br/> |是\*  <br/> |是\*  <br/> |是  <br/> |
|**UpdateCalendarDelegation** <br/> |日历委派已分配给某个邮箱。日历委派提供相同的组织权限，以管理邮箱所有者的日历中的其他人。  <br/> |是\*  <br/> |否  <br/> |是\*  <br/> |
|**UpdateFolderPermissions** <br/> |文件夹的权限已更改。文件夹权限控制您的组织中哪些用户可以访问邮箱和邮件位于这些文件夹中的文件夹。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
|**UpdateInboxRules** <br/> |已添加、 删除或更改收件箱规则。收件箱规则用于处理基于指定条件的用户的收件箱中的邮件，并执行操作，达到规则的条件时，例如将邮件移到指定的文件夹或删除一条消息。  <br/> |是\*  <br/> |是\*  <br/> |是\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup> 如果为邮箱启用了审核功能，则默认为已审核。<br/><br/>  <sup>\*\*</sup>合并文件夹绑定操作执行的条目。为 24 小时的时间跨度内的单个文件夹访问生成一个日志条目。<br/><br/><sup>\*\*\*</sup>具有已分配给用户的邮箱的完全访问权限的管理员被视为代理用户。 
  
如果您不再需要某些类型的邮箱操作进行审核，您应修改邮箱的审核日志记录配置以禁用这些操作。直到达到审核日志条目的保留期限限制不会清除现有日志条目。有关保留时间的审核日志条目的详细信息，请参阅中[搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#before-you-begin)的"开始之前"一节。
  
## <a name="more-infotab"></a>[详细信息](#tab/)
  
- 使用 Office 365 审核日志搜索已记录的邮箱活动。您可以搜索特定用户邮箱的活动。以下屏幕快照显示了您可以在 Office 365 审核日志中搜索的邮箱活动的列表。请注意，这些活动本主题中的"邮箱审核操作"部分所述的相同操作。
    
    ![可以通过在活动下拉列表中选择"Exchange 邮箱活动"来搜索邮箱审核操作的 Office 365 审核日志](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    下表介绍每个邮箱活动，您可以搜索，并显示相应的邮箱审核操作。
    
    |**审核日志中的活动**|**邮箱审核操作**|
    |:-----|:-----|
    |创建的邮箱项目  <br/> |Create  <br/> |
    |复制到另一个文件夹的邮件  <br/> |Copy  <br/> |
    |登录到邮箱的用户  <br/> |MailboxLogin  <br/> |
    |发送邮件使用代表发送权限  <br/> |SendOnBehalf  <br/> |
    |从邮箱的已清除的邮件  <br/> |HardDelete  <br/> |
    |移动到已删除邮件文件夹的邮件  <br/> |MoveToDeletedItems  <br/> |
    |将邮件移到另一个文件夹  <br/> |Move  <br/> |
    |发送邮件使用 Send As 权限  <br/> |SendAs  <br/> |
    |更新的消息  <br/> |Update  <br/> |
    |删除已删除邮件文件夹的邮件  <br/> |SoftDelete  <br/> |
    |添加了对文件夹的权限  <br/> |UpdateFolderPermissions  <br/> |
    |修改后的文件夹的权限  <br/> |UpdateFolderPermissions  <br/> |
    |从文件夹已删除的权限  <br/> |UpdateFolderPermissions  <br/> |
    |添加或删除用户对日历文件夹的代理访问  <br/> |UpdateCalendarDelegation  <br/> |
   
    请注意，以前的屏幕截图中所示**添加代理邮箱权限**和**删除代理邮箱权限**活动不到邮箱审核操作相关。及其指示是否管理员分配或删除 FullAccess 邮箱权限。 
    
    有关 Office 365 审核日志的信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。
    
- 只有在以下情况下，才视为由管理员访问邮箱：
    
  - 使用 Exchange Online 或 Office 365 中的内容搜索中的就地电子数据展示搜索邮箱。
    
  - [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用于访问邮箱。 
    
- 为邮箱启用审核日志记录时，也可以指定将记录每种登录类型（管理员、委派用户或所有者）的哪些用户操作（例如，访问、移动或删除邮件）。 
    
- 若要禁用邮箱审核日志记录，请运行以下命令：

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- 运行**Get-mailbox** cmdlet 时，不会显示为每种类型的用户审核的操作。但是，您可以运行以下命令以显示特定用户登录类型的所有审核的操作。 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- 您还可以导出邮箱审核日志，并指定要包含一个或多个用户的条目。报表和审核日志中的每个条目包含有关用户执行操作时，将执行的操作，和操作是否成功的信息。有关详细信息，请参阅[导出邮箱审核日志](https://go.microsoft.com/fwlink/p/?LinkID=404104)。
