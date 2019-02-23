---
title: 在 Office 365 中启用邮箱审核
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: 在 Office 365 中, 可以启用邮箱审核日志记录, 以记录邮箱所有者、代理和管理员的邮箱访问权限。默认情况下, 未打开 Office 365 中的邮箱审核。为邮箱启用邮箱审核日志记录后, 可以在 Office 365 审核日志中搜索在该邮箱上执行的活动。
ms.openlocfilehash: bb110e95d27feb8ae82b62803d218a2b38528692
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214602"
---
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="1e712-105">在 Office 365 中启用邮箱审核</span><span class="sxs-lookup"><span data-stu-id="1e712-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="1e712-p102">在 Office 365 中, 可以启用邮箱审核日志记录, 以记录邮箱所有者、代理和管理员的邮箱访问权限。默认情况下, 未打开 Office 365 中的邮箱审核。这意味着, 当您搜索 Office 365 审核日志中的邮箱活动时, 邮箱审核事件不会出现在结果中。但在为用户邮箱启用邮箱审核日志记录后, 您可以在审核日志中搜索邮箱活动。此外, 当邮箱审核日志记录打开时, 默认情况下会记录管理员、委派和所有者执行的某些操作。若要记录 (然后搜索) 其他操作, 请参阅第3步。</span><span class="sxs-lookup"><span data-stu-id="1e712-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1e712-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="1e712-112">Before you begin</span></span>
  
- <span data-ttu-id="1e712-p103">您必须使用 Exchange Online PowerShell 启用邮箱审核日志记录。您不能使用 "Office 365 &amp;安全合规中心" 或 "Exchange 管理中心"。</span><span class="sxs-lookup"><span data-stu-id="1e712-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="1e712-115">您无法对与 Microsoft 团队中的 Office 365 组或团队相关联的邮箱启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="1e712-115">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="1e712-116">分配了用户邮箱"完全访问"权限的管理员被视为委派用户。</span><span class="sxs-lookup"><span data-stu-id="1e712-116">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="1e712-117">步骤 1: 连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e712-117">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="1e712-118">在本地计算机上，打开 Windows PowerShell 并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1e712-118">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="1e712-119">在 " **Windows PowerShell 凭据请求**" 对话框中, 键入 Office 365 全局管理员帐户的用户名和密码, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1e712-119">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="1e712-120">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e712-120">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="1e712-121">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1e712-121">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="1e712-122">要验证您是否已连接至您的 Exchange Online 组织，请运行以下命令获取组织中所有邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="1e712-122">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="1e712-123">有关详细信息，或者如果您在连接到 Exchange Online 组织时遇到问题，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="1e712-123">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="1e712-124">步骤 2：启用邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="1e712-124">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="1e712-p104">在连接到 Exchange Online 组织后, 使用 PowerShell 启用邮箱的邮箱审核日志记录。或者, 您可以为组织中的所有邮箱启用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="1e712-p104">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="1e712-127">本示例为 Pilar Pinilla 的邮箱启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="1e712-127">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="1e712-128">本示例为您组织中的所有用户邮箱启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="1e712-128">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="1e712-129">步骤 3：指定要审核的所有者操作</span><span class="sxs-lookup"><span data-stu-id="1e712-129">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="1e712-p105">为邮箱启用审核时, 默认情况下会审核邮箱所有者执行的某些操作。您必须指定要审核的其他所有者操作。有关默认情况下记录的所有者操作以及可以审核的其他操作的列表和说明, 请参阅 "[邮箱审核操作](#mailbox-auditing-actions)" 部分中的表。</span><span class="sxs-lookup"><span data-stu-id="1e712-p105">When you enable auditing for a mailbox, some actions performed by the mailbox owner are audited by default. You have to specify other owner actions to audit. See the table in the [Mailbox auditing actions](#mailbox-auditing-actions) section for a list and description of owner actions that are logged by default and the other actions that can be audited.</span></span> 
  
<span data-ttu-id="1e712-p106">本示例将**mailboxlogin 该值**和**HardDelete**所有者操作添加到 Pilar Pinilla 邮箱的邮箱审核中。本示例假定已为此邮箱启用了邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="1e712-p106">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="1e712-p107">本示例为 "Don 大厅" 的邮箱启用邮箱审核日志记录, 并指定仅记录由邮箱所有者执行的**mailboxlogin 该值**操作。请注意, 此示例覆盖默认的 UpdateFolderPermissions 操作。</span><span class="sxs-lookup"><span data-stu-id="1e712-p107">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="1e712-p108">本示例将**mailboxlogin 该值**、 **HardDelete**和**SoftDelete** owner 操作添加到组织中的所有邮箱。本示例假定已对所有邮箱启用了邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="1e712-p108">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="1e712-139">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="1e712-139">How do you know this worked?</span></span>

<span data-ttu-id="1e712-140">若要验证是否已为某个邮箱成功启用邮箱审核日志记录，请使用 **Get-Mailbox** cmdlet 检索该邮箱的审核设置。</span><span class="sxs-lookup"><span data-stu-id="1e712-140">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="1e712-141">本示例检索 Pilar Pinilla 的审核设置。</span><span class="sxs-lookup"><span data-stu-id="1e712-141">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="1e712-142">本示例为您组织中的所有用户邮箱检索审核设置。</span><span class="sxs-lookup"><span data-stu-id="1e712-142">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="1e712-143">**AuditEnabled**属性的值**为 True**时, 将验证是否已启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="1e712-143">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="1e712-144">邮箱审核操作</span><span class="sxs-lookup"><span data-stu-id="1e712-144">Mailbox auditing actions</span></span>
  
<span data-ttu-id="1e712-p109">下表列出了邮箱审核日志记录可以记录的操作。该表包含可为不同用户登录类型记录的操作。在表中, "**否**" 表示无法为该登录类型记录操作。星号 ( **\*** ) 表示为邮箱启用邮箱审核日志记录时, 默认情况下会记录该操作。</span><span class="sxs-lookup"><span data-stu-id="1e712-p109">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox.</span></span> 
  
|<span data-ttu-id="1e712-149">**操作**</span><span class="sxs-lookup"><span data-stu-id="1e712-149">**Action**</span></span>|<span data-ttu-id="1e712-150">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e712-150">**Description**</span></span>|<span data-ttu-id="1e712-151">**管理员**</span><span class="sxs-lookup"><span data-stu-id="1e712-151">**Admin**</span></span>|<span data-ttu-id="1e712-152">**委派用户\*\*\***</span><span class="sxs-lookup"><span data-stu-id="1e712-152">**Delegate\*\*\***</span></span>|<span data-ttu-id="1e712-153">**所有者**</span><span class="sxs-lookup"><span data-stu-id="1e712-153">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1e712-154">**复制**</span><span class="sxs-lookup"><span data-stu-id="1e712-154">**Copy**</span></span> <br/> |<span data-ttu-id="1e712-155">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e712-155">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="1e712-156">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-156">Yes</span></span>  <br/> |<span data-ttu-id="1e712-157">不支持</span><span class="sxs-lookup"><span data-stu-id="1e712-157">No</span></span>  <br/> |<span data-ttu-id="1e712-158">否</span><span class="sxs-lookup"><span data-stu-id="1e712-158">No</span></span>  <br/> |
|<span data-ttu-id="1e712-159">**创建**</span><span class="sxs-lookup"><span data-stu-id="1e712-159">**Create**</span></span> <br/> |<span data-ttu-id="1e712-p110">在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建项;例如, 创建一个新的会议请求。请注意, 不会审核创建、发送或接收邮件。此外, 还不会审核创建邮箱文件夹的情况。</span><span class="sxs-lookup"><span data-stu-id="1e712-p110">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="1e712-163">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-163">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-164">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-164">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-165">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-165">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-166">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="1e712-166">**FolderBind**</span></span> <br/> |<span data-ttu-id="1e712-p111">已访问某个邮箱文件夹。当管理员或代理人打开邮箱时，也将记录此操作。</span><span class="sxs-lookup"><span data-stu-id="1e712-p111">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="1e712-169">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-169">Yes</span></span>  <br/> |<span data-ttu-id="1e712-170">是\*\*</span><span class="sxs-lookup"><span data-stu-id="1e712-170">Yes\*\*</span></span>  <br/> |<span data-ttu-id="1e712-171">否</span><span class="sxs-lookup"><span data-stu-id="1e712-171">No</span></span>  <br/> |
|<span data-ttu-id="1e712-172">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="1e712-172">**HardDelete**</span></span> <br/> |<span data-ttu-id="1e712-173">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="1e712-173">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="1e712-174">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-174">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-175">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-175">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-176">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-176">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-177">**mailboxlogin 该值**</span><span class="sxs-lookup"><span data-stu-id="1e712-177">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="1e712-178">用户登录其邮箱。</span><span class="sxs-lookup"><span data-stu-id="1e712-178">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="1e712-179">否</span><span class="sxs-lookup"><span data-stu-id="1e712-179">No</span></span>  <br/> |<span data-ttu-id="1e712-180">否</span><span class="sxs-lookup"><span data-stu-id="1e712-180">No</span></span>  <br/> |<span data-ttu-id="1e712-181">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-181">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-182">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="1e712-182">**MessageBind**</span></span> <br/> |<span data-ttu-id="1e712-183">在预览窗格查看邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="1e712-183">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="1e712-184">是</span><span class="sxs-lookup"><span data-stu-id="1e712-184">Yes</span></span>  <br/> |<span data-ttu-id="1e712-185">不支持</span><span class="sxs-lookup"><span data-stu-id="1e712-185">No</span></span>  <br/> |<span data-ttu-id="1e712-186">否</span><span class="sxs-lookup"><span data-stu-id="1e712-186">No</span></span>  <br/> |
|<span data-ttu-id="1e712-187">**移动**</span><span class="sxs-lookup"><span data-stu-id="1e712-187">**Move**</span></span> <br/> |<span data-ttu-id="1e712-188">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e712-188">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="1e712-189">是</span><span class="sxs-lookup"><span data-stu-id="1e712-189">Yes</span></span>  <br/> |<span data-ttu-id="1e712-190">支持</span><span class="sxs-lookup"><span data-stu-id="1e712-190">Yes</span></span>  <br/> |<span data-ttu-id="1e712-191">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-191">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-192">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="1e712-192">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="1e712-193">已将某个邮件删除并移至“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e712-193">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="1e712-194">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-194">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-195">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-195">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-196">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-196">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-197">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="1e712-197">**SendAs**</span></span> <br/> |<span data-ttu-id="1e712-p112">已使用 SendAs 权限发送某个邮件。这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="1e712-p112">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="1e712-200">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-200">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-201">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-201">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-202">否</span><span class="sxs-lookup"><span data-stu-id="1e712-202">No</span></span>  <br/> |
|<span data-ttu-id="1e712-203">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="1e712-203">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="1e712-p113">已使用 SendOnBehalf 权限发送某个邮件。这表示另一个用户代表邮箱所有者发送了邮件。此邮件向收件人表明，此邮件是代表谁发送的以及实际发送此邮件的是谁。</span><span class="sxs-lookup"><span data-stu-id="1e712-p113">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="1e712-207">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-207">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-208">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-208">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-209">否</span><span class="sxs-lookup"><span data-stu-id="1e712-209">No</span></span>  <br/> |
|<span data-ttu-id="1e712-210">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="1e712-210">**SoftDelete**</span></span> <br/> |<span data-ttu-id="1e712-p114">已将某个邮件永久删除或从“已删除邮件”文件夹中删除。软删除的项目将移至“可恢复的项目”文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e712-p114">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="1e712-213">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-213">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-214">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-214">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-215">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-215">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-216">**更新**</span><span class="sxs-lookup"><span data-stu-id="1e712-216">**Update**</span></span> <br/> |<span data-ttu-id="1e712-217">已更改某个邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="1e712-217">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="1e712-218">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-218">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-219">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-219">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-220">可访问</span><span class="sxs-lookup"><span data-stu-id="1e712-220">Yes</span></span>  <br/> |
|<span data-ttu-id="1e712-221">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="1e712-221">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="1e712-p115">向邮箱分配了日历委派。日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。</span><span class="sxs-lookup"><span data-stu-id="1e712-p115">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="1e712-224">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-224">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-225">否</span><span class="sxs-lookup"><span data-stu-id="1e712-225">No</span></span>  <br/> |<span data-ttu-id="1e712-226">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-226">Yes\*</span></span>  <br/> |
|<span data-ttu-id="1e712-227">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="1e712-227">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="1e712-p116">更改了文件夹权限。文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="1e712-p116">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="1e712-230">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-230">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-231">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-231">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-232">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="1e712-233">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="1e712-233">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="1e712-p117">已添加、删除或更改收件箱规则。"收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="1e712-p117">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="1e712-236">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-236">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-237">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-237">Yes\*</span></span>  <br/> |<span data-ttu-id="1e712-238">是\*</span><span class="sxs-lookup"><span data-stu-id="1e712-238">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1e712-239"><sup>\*</sup> 如果为邮箱启用了审核功能，则默认为已审核。</span><span class="sxs-lookup"><span data-stu-id="1e712-239"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="1e712-p118"><sup>\*\*</sup>合并由代理人执行的文件夹绑定操作的条目。在24小时的时间跨度内为单个文件夹访问生成一个日志条目。</span><span class="sxs-lookup"><span data-stu-id="1e712-p118"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="1e712-242"><sup>\*\*\*</sup>已向其分配了对用户邮箱的完全访问权限的管理员被视为委派用户。</span><span class="sxs-lookup"><span data-stu-id="1e712-242"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="1e712-p119">如果不再需要审核特定类型的邮箱操作, 则应修改邮箱的审核日志记录配置, 以禁用这些操作。在达到审核日志条目的保留期限限制之前, 不会清除现有日志条目。有关审核日志条目保留期限的详细信息, 请参阅在[Office 365 Security & 合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md#before-you-begin)中的 "开始之前" 部分。</span><span class="sxs-lookup"><span data-stu-id="1e712-p119">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the retention age limit for audit log entries is reached. For more information about the retention age for audit log entries, see the "Before you begin" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#before-you-begin).</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="1e712-246">详细信息</span><span class="sxs-lookup"><span data-stu-id="1e712-246">More info</span></span>](#tab/)
  
- <span data-ttu-id="1e712-p120">使用 Office 365 审核日志搜索已记录的邮箱活动。您可以搜索特定用户邮箱的活动。下面的屏幕截图显示了您可以在 Office 365 审核日志中搜索的邮箱活动的列表。请注意, 这些活动与本主题中的 "邮箱审核操作" 一节中所述的操作相同。</span><span class="sxs-lookup"><span data-stu-id="1e712-p120">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![通过在 "活动" 下拉列表中选择 "Exchange 邮箱活动", 可以在 Office 365 审核日志中搜索邮箱审核操作](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="1e712-252">下表介绍了可以搜索的每个邮箱活动并显示相应的邮箱审核操作。</span><span class="sxs-lookup"><span data-stu-id="1e712-252">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="1e712-253">**审核日志中的活动**</span><span class="sxs-lookup"><span data-stu-id="1e712-253">**Activity in the audit log**</span></span>|<span data-ttu-id="1e712-254">**邮箱审核操作**</span><span class="sxs-lookup"><span data-stu-id="1e712-254">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="1e712-255">创建的邮箱项目</span><span class="sxs-lookup"><span data-stu-id="1e712-255">Created mailbox item</span></span>  <br/> |<span data-ttu-id="1e712-256">Create</span><span class="sxs-lookup"><span data-stu-id="1e712-256">Create</span></span>  <br/> |
    |<span data-ttu-id="1e712-257">将邮件复制到另一个文件夹</span><span class="sxs-lookup"><span data-stu-id="1e712-257">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="1e712-258">Copy</span><span class="sxs-lookup"><span data-stu-id="1e712-258">Copy</span></span>  <br/> |
    |<span data-ttu-id="1e712-259">登录到邮箱的用户</span><span class="sxs-lookup"><span data-stu-id="1e712-259">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="1e712-260">mailboxlogin 该值</span><span class="sxs-lookup"><span data-stu-id="1e712-260">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="1e712-261">使用 "代表发送" 权限发送的邮件</span><span class="sxs-lookup"><span data-stu-id="1e712-261">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="1e712-262">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="1e712-262">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="1e712-263">已清除邮箱中的邮件</span><span class="sxs-lookup"><span data-stu-id="1e712-263">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="1e712-264">HardDelete</span><span class="sxs-lookup"><span data-stu-id="1e712-264">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="1e712-265">将邮件移动到 "已删除邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="1e712-265">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="1e712-266">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="1e712-266">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="1e712-267">将邮件移动到另一个文件夹</span><span class="sxs-lookup"><span data-stu-id="1e712-267">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="1e712-268">Move</span><span class="sxs-lookup"><span data-stu-id="1e712-268">Move</span></span>  <br/> |
    |<span data-ttu-id="1e712-269">使用 "代理发送" 权限发送邮件</span><span class="sxs-lookup"><span data-stu-id="1e712-269">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="1e712-270">SendAs</span><span class="sxs-lookup"><span data-stu-id="1e712-270">SendAs</span></span>  <br/> |
    |<span data-ttu-id="1e712-271">更新的邮件</span><span class="sxs-lookup"><span data-stu-id="1e712-271">Updated message</span></span>  <br/> |<span data-ttu-id="1e712-272">Update</span><span class="sxs-lookup"><span data-stu-id="1e712-272">Update</span></span>  <br/> |
    |<span data-ttu-id="1e712-273">从 "已删除邮件" 文件夹中删除邮件</span><span class="sxs-lookup"><span data-stu-id="1e712-273">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="1e712-274">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="1e712-274">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="1e712-275">向文件夹添加了权限</span><span class="sxs-lookup"><span data-stu-id="1e712-275">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="1e712-276">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="1e712-276">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="1e712-277">修改文件夹的权限</span><span class="sxs-lookup"><span data-stu-id="1e712-277">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="1e712-278">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="1e712-278">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="1e712-279">从文件夹删除权限</span><span class="sxs-lookup"><span data-stu-id="1e712-279">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="1e712-280">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="1e712-280">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="1e712-281">添加或删除了具有 "代理访问日历" 文件夹的用户</span><span class="sxs-lookup"><span data-stu-id="1e712-281">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="1e712-282">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="1e712-282">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="1e712-p121">请注意, 所**添加的代理邮箱权限**和**已删除的代理邮箱权限**活动在前面的屏幕截图中并不与邮箱审核操作相关。它们指示管理员是否分配或删除了 FullAccess 邮箱权限。</span><span class="sxs-lookup"><span data-stu-id="1e712-p121">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="1e712-285">有关 office 365 审核日志的信息, 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="1e712-285">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="1e712-286">只有在以下情况下，才视为由管理员访问邮箱：</span><span class="sxs-lookup"><span data-stu-id="1e712-286">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="1e712-287">Exchange Online 中的就地电子数据展示或 Office 365 中的内容搜索用于搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="1e712-287">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="1e712-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用于访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="1e712-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="1e712-289">为邮箱启用审核日志记录时，也可以指定将记录每种登录类型（管理员、委派用户或所有者）的哪些用户操作（例如，访问、移动或删除邮件）。 </span><span class="sxs-lookup"><span data-stu-id="1e712-289">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="1e712-290">若要禁用邮箱审核日志记录，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1e712-290">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="1e712-p122">运行 "**获取邮箱**" cmdlet 时, 不会显示为每种类型的用户审核的操作。但您可以运行以下命令来显示特定用户登录类型的所有已审核操作。</span><span class="sxs-lookup"><span data-stu-id="1e712-p122">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="1e712-p123">您还可以导出邮箱审核日志, 并指定要为一个或多个用户包括的条目。报告和审核日志中的每个条目都包含有关执行操作的执行者以及执行操作的时间以及操作是否成功的信息。有关详细信息, 请参阅[导出邮箱审核日志](https://go.microsoft.com/fwlink/p/?LinkID=404104)。</span><span class="sxs-lookup"><span data-stu-id="1e712-p123">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
