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
# <a name="enable-mailbox-auditing-in-office-365"></a><span data-ttu-id="d553e-105">在 Office 365 中启用邮箱审核</span><span class="sxs-lookup"><span data-stu-id="d553e-105">Enable mailbox auditing in Office 365</span></span>
  
<span data-ttu-id="d553e-p102">在 Office 365 中，您可以打开邮箱审核日志记录，记录邮箱所有者、 委派和管理员访问邮箱。默认情况下，Office 365 中的邮箱审核功能不被打开的。这意味着邮箱审核事件时搜索邮箱活动的 Office 365 审核日志不会显示在结果中。但您启用邮箱审核日志记录用户邮箱后，您可以搜索邮箱活动的审核日志。此外，当邮箱审核日志记录处于打开状态，由管理员，代理人执行某些操作并所有者记录默认情况下。记录 （和然后搜索） 其他操作，请参阅 Step 3。</span><span class="sxs-lookup"><span data-stu-id="d553e-p102">In Office 365, you can turn on mailbox audit logging to log mailbox access by mailbox owners, delegates, and administrators. By default, mailbox auditing in Office 365 isn't turned on. That means mailbox auditing events won't appear in the results when you search the Office 365 audit log for mailbox activity. But after you turn on mailbox audit logging for a user mailbox, you can search the audit log for mailbox activity. Additionally, when mailbox audit logging is turned on, some actions performed by administrators, delegates, and owners are logged by default. To log (and then search for) additional actions, see Step 3.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d553e-112">开始之前</span><span class="sxs-lookup"><span data-stu-id="d553e-112">Before you begin</span></span>
  
- <span data-ttu-id="d553e-p103">您必须使用 Exchange Online PowerShell 中启用邮箱审核日志记录。不能使用 Office 365 安全性&amp;合规性中心或 Exchange 管理员中心。</span><span class="sxs-lookup"><span data-stu-id="d553e-p103">You have to use Exchange Online PowerShell to enable mailbox audit logging. You can't use the Office 365 Security &amp; Compliance Center or the Exchange admin center.</span></span>
    
- <span data-ttu-id="d553e-115">无法启用邮箱审核日志记录的邮箱，与 Office 365 组或团队中的 Microsoft 团队相关联。</span><span class="sxs-lookup"><span data-stu-id="d553e-115">You can't enable mailbox audit logging for the mailbox that's associated with an Office 365 Group or a team in Microsoft Teams.</span></span>
    
- <span data-ttu-id="d553e-116">分配了用户邮箱"完全访问"权限的管理员被视为委派用户。</span><span class="sxs-lookup"><span data-stu-id="d553e-116">An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span>
  
## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="d553e-117">步骤 1： 连接到 Exchange Online PowerShell 中</span><span class="sxs-lookup"><span data-stu-id="d553e-117">Step 1: Connect to Exchange Online PowerShell</span></span>

1. <span data-ttu-id="d553e-118">在本地计算机上，打开 Windows PowerShell 并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d553e-118">On your local computer, open Windows PowerShell and run the following command.</span></span>
   
    ```
    $UserCredential = Get-Credential
    ```

2. <span data-ttu-id="d553e-119">在**Windows PowerShell 凭据请求**对话框中，键入用户名和密码的 Office 365 全局管理员帐户，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d553e-119">In the **Windows PowerShell Credential Request** dialog box, type user name and password for an Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="d553e-120">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d553e-120">Run the following command:</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="d553e-121">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d553e-121">Run the following command.</span></span>

    ```
    Import-PSSession $Session
    ```
   
4. <span data-ttu-id="d553e-122">要验证您是否已连接至您的 Exchange Online 组织，请运行以下命令获取组织中所有邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="d553e-122">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```
  
<span data-ttu-id="d553e-123">有关详细信息，或者如果您在连接到 Exchange Online 组织时遇到问题，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="d553e-123">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span>
  
## <a name="step-2-enable-mailbox-audit-logging"></a><span data-ttu-id="d553e-124">步骤 2：启用邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="d553e-124">Step 2: Enable mailbox audit logging</span></span>

<span data-ttu-id="d553e-p104">在连接到 Exchange Online 组织后，使用 PowerShell 启用邮箱审核日志记录邮箱。此外，您可以启用邮箱审核您的组织中所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-p104">After you connect to your Exchange Online organization, use PowerShell to enable mailbox audit logging for a mailbox. Alternatively, you can enable mailbox auditing for all mailboxes in your organization.</span></span>
  
<span data-ttu-id="d553e-127">本示例启用邮箱审核日志记录 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-127">This example enables mailbox audit logging for Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

<span data-ttu-id="d553e-128">本示例为您组织中的所有用户邮箱启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="d553e-128">This example enables mailbox audit logging for all user mailboxes in your organization.</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a><span data-ttu-id="d553e-129">步骤 3：指定要审核的所有者操作</span><span class="sxs-lookup"><span data-stu-id="d553e-129">Step 3: Specify owner actions to audit</span></span>

<span data-ttu-id="d553e-p105">启用邮箱审核时，默认情况下审核邮箱所有者执行一些操作。您必须指定审核其他所有者操作。请参阅列表以及默认情况下记录的所有者操作和可审核的其他操作的说明[邮箱审核操作](#mailbox-auditing-actions)部分中的表。</span><span class="sxs-lookup"><span data-stu-id="d553e-p105">When you enable auditing for a mailbox, some actions performed by the mailbox owner are audited by default. You have to specify other owner actions to audit. See the table in the [Mailbox auditing actions](#mailbox-auditing-actions) section for a list and description of owner actions that are logged by default and the other actions that can be audited.</span></span> 
  
<span data-ttu-id="d553e-p106">本示例将**MailboxLogin**和**HardDelete**所有者操作添加到邮箱审核 Pilar Pinilla 的邮箱。本示例假定的邮箱审核已启用此邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-p106">This example adds the **MailboxLogin** and **HardDelete** owner actions to mailbox auditing for Pilar Pinilla's mailbox. This example assumes that mailbox auditing has already been enabled for this mailbox.</span></span> 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

<span data-ttu-id="d553e-p107">本示例启用邮箱审核日志记录 Don 大厅邮箱，并指定邮箱所有者执行的**MailboxLogin**操作将会记录。请注意，本示例会覆盖默认 UpdateFolderPermissions 操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-p107">This example enables mailbox audit logging for Don Hall's mailbox and specifies that only the **MailboxLogin** action performed by the mailbox owner will be logged. Note that this example overwrites the default UpdateFolderPermissions action.</span></span> 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
<span data-ttu-id="d553e-p108">本示例向组织中所有邮箱的**MailboxLogin**、 **HardDelete**和**SoftDelete**所有者操作。本示例假定的邮箱审核已启用的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-p108">This example adds the **MailboxLogin**, **HardDelete**, and **SoftDelete** owner actions to all mailboxes in the organization. This example assumes that mailbox auditing has already been enabled for all mailboxes.</span></span> 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d553e-139">怎样才能知道这是否已正常工作？</span><span class="sxs-lookup"><span data-stu-id="d553e-139">How do you know this worked?</span></span>

<span data-ttu-id="d553e-140">若要验证是否已为某个邮箱成功启用邮箱审核日志记录，请使用 **Get-Mailbox** cmdlet 检索该邮箱的审核设置。</span><span class="sxs-lookup"><span data-stu-id="d553e-140">To verify that you have successfully enabled mailbox audit logging for a mailbox, use the **Get-Mailbox** cmdlet to retrieve the auditing settings for that mailbox.</span></span> 
  
<span data-ttu-id="d553e-141">本示例检索 Pilar Pinilla 的审核设置。</span><span class="sxs-lookup"><span data-stu-id="d553e-141">This example retrieves the auditing settings for Pilar Pinilla.</span></span>

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
<span data-ttu-id="d553e-142">本示例为您组织中的所有用户邮箱检索审核设置。</span><span class="sxs-lookup"><span data-stu-id="d553e-142">This example retrieves the auditing settings for all user mailboxes in your organization.</span></span>

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
<span data-ttu-id="d553e-143">**AuditEnabled**属性的值为**True**验证该邮箱审核日志记录已启用。</span><span class="sxs-lookup"><span data-stu-id="d553e-143">A value of **True** for the **AuditEnabled** property verifies that mailbox audit logging is enabled.</span></span> 
    
## <a name="mailbox-auditing-actions"></a><span data-ttu-id="d553e-144">邮箱审核操作</span><span class="sxs-lookup"><span data-stu-id="d553e-144">Mailbox auditing actions</span></span>
  
<span data-ttu-id="d553e-p109">下表列出了可以由邮箱记录的操作审核日志记录。表包含了可以为不同用户登录类型记录的操作。在表中，**否**指示操作无法会为该登录类型记录。星号 ( **\*** ) 指示为邮箱启用了邮箱审核日志记录时，默认情况下记录操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-p109">The following table lists the actions that can be logged by mailbox audit logging. The table includes which action can be logged for the different user logon types. In the table, a **No** indicates that an action can't be logged for that logon type. An asterisk ( **\*** ) indicates that the action is logged by default when mailbox audit logging is enabled for the mailbox.</span></span> 
  
|<span data-ttu-id="d553e-149">**操作**</span><span class="sxs-lookup"><span data-stu-id="d553e-149">**Action**</span></span>|<span data-ttu-id="d553e-150">**说明**</span><span class="sxs-lookup"><span data-stu-id="d553e-150">**Description**</span></span>|<span data-ttu-id="d553e-151">**管理员**</span><span class="sxs-lookup"><span data-stu-id="d553e-151">**Admin**</span></span>|<span data-ttu-id="d553e-152">**委派用户\*\*\***</span><span class="sxs-lookup"><span data-stu-id="d553e-152">**Delegate\*\*\***</span></span>|<span data-ttu-id="d553e-153">**所有者**</span><span class="sxs-lookup"><span data-stu-id="d553e-153">**Owner**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d553e-154">**复制**</span><span class="sxs-lookup"><span data-stu-id="d553e-154">**Copy**</span></span> <br/> |<span data-ttu-id="d553e-155">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-155">A message was copied to another folder.</span></span>  <br/> |<span data-ttu-id="d553e-156">是</span><span class="sxs-lookup"><span data-stu-id="d553e-156">Yes</span></span>  <br/> |<span data-ttu-id="d553e-157">否</span><span class="sxs-lookup"><span data-stu-id="d553e-157">No</span></span>  <br/> |<span data-ttu-id="d553e-158">否</span><span class="sxs-lookup"><span data-stu-id="d553e-158">No</span></span>  <br/> |
|<span data-ttu-id="d553e-159">**创建**</span><span class="sxs-lookup"><span data-stu-id="d553e-159">**Create**</span></span> <br/> |<span data-ttu-id="d553e-p110">邮箱; 中的日历、 联系人、 备注或任务文件夹中创建项目例如，创建一个新的会议请求。请注意，不审核创建、 发送或接收邮件。此外，不审核创建邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-p110">An item is created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox; for example, a new meeting request is created. Note that creating, sending, or receiving a message isn't audited. Also, creating a mailbox folder is not audited.</span></span>  <br/> |<span data-ttu-id="d553e-163">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-163">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-164">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-164">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-165">是</span><span class="sxs-lookup"><span data-stu-id="d553e-165">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-166">**记录 FolderBind**</span><span class="sxs-lookup"><span data-stu-id="d553e-166">**FolderBind**</span></span> <br/> |<span data-ttu-id="d553e-p111">已访问某个邮箱文件夹。当管理员或代理人打开邮箱时，也将记录此操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-p111">A mailbox folder was accessed. This action is also logged when the admin or delegate opens the mailbox.</span></span>  <br/> |<span data-ttu-id="d553e-169">是</span><span class="sxs-lookup"><span data-stu-id="d553e-169">Yes</span></span>  <br/> |<span data-ttu-id="d553e-170">是\*\*</span><span class="sxs-lookup"><span data-stu-id="d553e-170">Yes\*\*</span></span>  <br/> |<span data-ttu-id="d553e-171">否</span><span class="sxs-lookup"><span data-stu-id="d553e-171">No</span></span>  <br/> |
|<span data-ttu-id="d553e-172">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="d553e-172">**HardDelete**</span></span> <br/> |<span data-ttu-id="d553e-173">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="d553e-173">A message was purged from the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="d553e-174">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-174">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-175">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-175">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-176">是</span><span class="sxs-lookup"><span data-stu-id="d553e-176">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-177">**MailboxLogin**</span><span class="sxs-lookup"><span data-stu-id="d553e-177">**MailboxLogin**</span></span> <br/> |<span data-ttu-id="d553e-178">用户登录其邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-178">The user signed in to their mailbox.</span></span>  <br/> |<span data-ttu-id="d553e-179">否</span><span class="sxs-lookup"><span data-stu-id="d553e-179">No</span></span>  <br/> |<span data-ttu-id="d553e-180">否</span><span class="sxs-lookup"><span data-stu-id="d553e-180">No</span></span>  <br/> |<span data-ttu-id="d553e-181">是</span><span class="sxs-lookup"><span data-stu-id="d553e-181">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-182">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="d553e-182">**MessageBind**</span></span> <br/> |<span data-ttu-id="d553e-183">在预览窗格查看邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="d553e-183">A message was viewed in the preview pane or opened.</span></span>  <br/> |<span data-ttu-id="d553e-184">是</span><span class="sxs-lookup"><span data-stu-id="d553e-184">Yes</span></span>  <br/> |<span data-ttu-id="d553e-185">否</span><span class="sxs-lookup"><span data-stu-id="d553e-185">No</span></span>  <br/> |<span data-ttu-id="d553e-186">否</span><span class="sxs-lookup"><span data-stu-id="d553e-186">No</span></span>  <br/> |
|<span data-ttu-id="d553e-187">**移动**</span><span class="sxs-lookup"><span data-stu-id="d553e-187">**Move**</span></span> <br/> |<span data-ttu-id="d553e-188">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-188">A message was moved to another folder.</span></span>  <br/> |<span data-ttu-id="d553e-189">是</span><span class="sxs-lookup"><span data-stu-id="d553e-189">Yes</span></span>  <br/> |<span data-ttu-id="d553e-190">是</span><span class="sxs-lookup"><span data-stu-id="d553e-190">Yes</span></span>  <br/> |<span data-ttu-id="d553e-191">是</span><span class="sxs-lookup"><span data-stu-id="d553e-191">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-192">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="d553e-192">**MoveToDeletedItems**</span></span> <br/> |<span data-ttu-id="d553e-193">已将某个邮件删除并移至“已删除邮件”文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-193">A message was deleted and moved to the Deleted Items folder.</span></span>  <br/> |<span data-ttu-id="d553e-194">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-194">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-195">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-195">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-196">是</span><span class="sxs-lookup"><span data-stu-id="d553e-196">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-197">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="d553e-197">**SendAs**</span></span> <br/> |<span data-ttu-id="d553e-p112">已使用 SendAs 权限发送某个邮件。这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="d553e-p112">A message was sent using the SendAs permission. This means another user sent the message as though it came from the mailbox owner.</span></span>  <br/> |<span data-ttu-id="d553e-200">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-200">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-201">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-201">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-202">否</span><span class="sxs-lookup"><span data-stu-id="d553e-202">No</span></span>  <br/> |
|<span data-ttu-id="d553e-203">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="d553e-203">**SendOnBehalf**</span></span> <br/> |<span data-ttu-id="d553e-p113">已使用 SendOnBehalf 权限发送某个邮件。这表示另一个用户代表邮箱所有者发送了邮件。此邮件向收件人表明，此邮件是代表谁发送的以及实际发送此邮件的是谁。</span><span class="sxs-lookup"><span data-stu-id="d553e-p113">A message was sent using the SendOnBehalf permission. This means another user sent the message on behalf of the mailbox owner. The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>  <br/> |<span data-ttu-id="d553e-207">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-207">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-208">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-208">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-209">否</span><span class="sxs-lookup"><span data-stu-id="d553e-209">No</span></span>  <br/> |
|<span data-ttu-id="d553e-210">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="d553e-210">**SoftDelete**</span></span> <br/> |<span data-ttu-id="d553e-p114">已将某个邮件永久删除或从“已删除邮件”文件夹中删除。软删除的项目将移至“可恢复的项目”文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-p114">A message was permanently deleted or deleted from the Deleted Items folder. Soft-deleted items are moved to the Recoverable Items folder.</span></span>  <br/> |<span data-ttu-id="d553e-213">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-213">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-214">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-214">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-215">是</span><span class="sxs-lookup"><span data-stu-id="d553e-215">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-216">**更新**</span><span class="sxs-lookup"><span data-stu-id="d553e-216">**Update**</span></span> <br/> |<span data-ttu-id="d553e-217">已更改某个邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="d553e-217">A message or its properties was changed.</span></span>  <br/> |<span data-ttu-id="d553e-218">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-218">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-219">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-219">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-220">是</span><span class="sxs-lookup"><span data-stu-id="d553e-220">Yes</span></span>  <br/> |
|<span data-ttu-id="d553e-221">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="d553e-221">**UpdateCalendarDelegation**</span></span> <br/> |<span data-ttu-id="d553e-p115">日历委派已分配给某个邮箱。日历委派提供相同的组织权限，以管理邮箱所有者的日历中的其他人。</span><span class="sxs-lookup"><span data-stu-id="d553e-p115">A calendar delegation was assigned to a mailbox. Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>  <br/> |<span data-ttu-id="d553e-224">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-224">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-225">否</span><span class="sxs-lookup"><span data-stu-id="d553e-225">No</span></span>  <br/> |<span data-ttu-id="d553e-226">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-226">Yes\*</span></span>  <br/> |
|<span data-ttu-id="d553e-227">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="d553e-227">**UpdateFolderPermissions**</span></span> <br/> |<span data-ttu-id="d553e-p116">文件夹的权限已更改。文件夹权限控制您的组织中哪些用户可以访问邮箱和邮件位于这些文件夹中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d553e-p116">A folder permission was changed. Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>  <br/> |<span data-ttu-id="d553e-230">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-230">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-231">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-231">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-232">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-232">Yes\*</span></span>  <br/> |
|<span data-ttu-id="d553e-233">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="d553e-233">**UpdateInboxRules**</span></span> <br/> |<span data-ttu-id="d553e-p117">已添加、 删除或更改收件箱规则。收件箱规则用于处理基于指定条件的用户的收件箱中的邮件，并执行操作，达到规则的条件时，例如将邮件移到指定的文件夹或删除一条消息。</span><span class="sxs-lookup"><span data-stu-id="d553e-p117">An inbox rule has been added, removed, or changed. Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>  <br/> |<span data-ttu-id="d553e-236">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-236">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-237">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-237">Yes\*</span></span>  <br/> |<span data-ttu-id="d553e-238">是\*</span><span class="sxs-lookup"><span data-stu-id="d553e-238">Yes\*</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d553e-239"><sup>\*</sup> 如果为邮箱启用了审核功能，则默认为已审核。</span><span class="sxs-lookup"><span data-stu-id="d553e-239"><sup>\*</sup> Audited by default if auditing is enabled for a mailbox.</span></span><br/><br/>  <span data-ttu-id="d553e-p118"><sup>\*\*</sup>合并文件夹绑定操作执行的条目。为 24 小时的时间跨度内的单个文件夹访问生成一个日志条目。</span><span class="sxs-lookup"><span data-stu-id="d553e-p118"><sup>\*\*</sup> Entries for folder bind actions performed by delegates are consolidated. One log entry is generated for individual folder access within a time span of 24 hours.</span></span><br/><br/><span data-ttu-id="d553e-242"><sup>\*\*\*</sup>具有已分配给用户的邮箱的完全访问权限的管理员被视为代理用户。</span><span class="sxs-lookup"><span data-stu-id="d553e-242"><sup>\*\*\*</sup> An administrator who has been assigned the Full Access permission to a user's mailbox is considered a delegate user.</span></span> 
  
<span data-ttu-id="d553e-p119">如果您不再需要某些类型的邮箱操作进行审核，您应修改邮箱的审核日志记录配置以禁用这些操作。直到达到审核日志条目的保留期限限制不会清除现有日志条目。有关保留时间的审核日志条目的详细信息，请参阅中[搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#before-you-begin)的"开始之前"一节。</span><span class="sxs-lookup"><span data-stu-id="d553e-p119">If you no longer require certain types of mailbox actions to be audited, you should modify the mailbox's audit logging configuration to disable those actions. Existing log entries aren't purged until the retention age limit for audit log entries is reached. For more information about the retention age for audit log entries, see the "Before you begin" section in [Search the audit log in the Office 365 Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#before-you-begin).</span></span>
  
## <a name="more-infotab"></a>[<span data-ttu-id="d553e-246">详细信息</span><span class="sxs-lookup"><span data-stu-id="d553e-246">More info</span></span>](#tab/)
  
- <span data-ttu-id="d553e-p120">使用 Office 365 审核日志搜索已记录的邮箱活动。您可以搜索特定用户邮箱的活动。以下屏幕快照显示了您可以在 Office 365 审核日志中搜索的邮箱活动的列表。请注意，这些活动本主题中的"邮箱审核操作"部分所述的相同操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-p120">Use the Office 365 audit log to search for mailbox activity that have been logged. You can search for activity for a specific user mailbox. The following screenshot shows a list of mailbox activities that you can search for in the Office 365 audit log. Note that these activities are the same actions that are described in the "Mailbox auditing actions" section in this topic.</span></span>
    
    ![可以通过在活动下拉列表中选择"Exchange 邮箱活动"来搜索邮箱审核操作的 Office 365 审核日志](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    <span data-ttu-id="d553e-252">下表介绍每个邮箱活动，您可以搜索，并显示相应的邮箱审核操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-252">The following table describes each mailbox activity that you can search for and shows the corresponding mailbox auditing action.</span></span>
    
    |<span data-ttu-id="d553e-253">**审核日志中的活动**</span><span class="sxs-lookup"><span data-stu-id="d553e-253">**Activity in the audit log**</span></span>|<span data-ttu-id="d553e-254">**邮箱审核操作**</span><span class="sxs-lookup"><span data-stu-id="d553e-254">**Mailbox auditing action**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="d553e-255">创建的邮箱项目</span><span class="sxs-lookup"><span data-stu-id="d553e-255">Created mailbox item</span></span>  <br/> |<span data-ttu-id="d553e-256">Create</span><span class="sxs-lookup"><span data-stu-id="d553e-256">Create</span></span>  <br/> |
    |<span data-ttu-id="d553e-257">复制到另一个文件夹的邮件</span><span class="sxs-lookup"><span data-stu-id="d553e-257">Copied messages to another folder</span></span>  <br/> |<span data-ttu-id="d553e-258">Copy</span><span class="sxs-lookup"><span data-stu-id="d553e-258">Copy</span></span>  <br/> |
    |<span data-ttu-id="d553e-259">登录到邮箱的用户</span><span class="sxs-lookup"><span data-stu-id="d553e-259">User signed in to mailbox</span></span>  <br/> |<span data-ttu-id="d553e-260">MailboxLogin</span><span class="sxs-lookup"><span data-stu-id="d553e-260">MailboxLogin</span></span>  <br/> |
    |<span data-ttu-id="d553e-261">发送邮件使用代表发送权限</span><span class="sxs-lookup"><span data-stu-id="d553e-261">Sent message using Send On Behalf permissions</span></span>  <br/> |<span data-ttu-id="d553e-262">SendOnBehalf</span><span class="sxs-lookup"><span data-stu-id="d553e-262">SendOnBehalf</span></span>  <br/> |
    |<span data-ttu-id="d553e-263">从邮箱的已清除的邮件</span><span class="sxs-lookup"><span data-stu-id="d553e-263">Purged messages from the mailbox</span></span>  <br/> |<span data-ttu-id="d553e-264">HardDelete</span><span class="sxs-lookup"><span data-stu-id="d553e-264">HardDelete</span></span>  <br/> |
    |<span data-ttu-id="d553e-265">移动到已删除邮件文件夹的邮件</span><span class="sxs-lookup"><span data-stu-id="d553e-265">Moved messages to Deleted Items folder</span></span>  <br/> |<span data-ttu-id="d553e-266">MoveToDeletedItems</span><span class="sxs-lookup"><span data-stu-id="d553e-266">MoveToDeletedItems</span></span>  <br/> |
    |<span data-ttu-id="d553e-267">将邮件移到另一个文件夹</span><span class="sxs-lookup"><span data-stu-id="d553e-267">Moved messages to another folder</span></span>  <br/> |<span data-ttu-id="d553e-268">Move</span><span class="sxs-lookup"><span data-stu-id="d553e-268">Move</span></span>  <br/> |
    |<span data-ttu-id="d553e-269">发送邮件使用 Send As 权限</span><span class="sxs-lookup"><span data-stu-id="d553e-269">Sent message using Send As permissions</span></span>  <br/> |<span data-ttu-id="d553e-270">SendAs</span><span class="sxs-lookup"><span data-stu-id="d553e-270">SendAs</span></span>  <br/> |
    |<span data-ttu-id="d553e-271">更新的消息</span><span class="sxs-lookup"><span data-stu-id="d553e-271">Updated message</span></span>  <br/> |<span data-ttu-id="d553e-272">Update</span><span class="sxs-lookup"><span data-stu-id="d553e-272">Update</span></span>  <br/> |
    |<span data-ttu-id="d553e-273">删除已删除邮件文件夹的邮件</span><span class="sxs-lookup"><span data-stu-id="d553e-273">Deleted messages from Deleted Items folder</span></span>  <br/> |<span data-ttu-id="d553e-274">SoftDelete</span><span class="sxs-lookup"><span data-stu-id="d553e-274">SoftDelete</span></span>  <br/> |
    |<span data-ttu-id="d553e-275">添加了对文件夹的权限</span><span class="sxs-lookup"><span data-stu-id="d553e-275">Added permissions to folder</span></span>  <br/> |<span data-ttu-id="d553e-276">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="d553e-276">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="d553e-277">修改后的文件夹的权限</span><span class="sxs-lookup"><span data-stu-id="d553e-277">Modified permissions of folder</span></span>  <br/> |<span data-ttu-id="d553e-278">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="d553e-278">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="d553e-279">从文件夹已删除的权限</span><span class="sxs-lookup"><span data-stu-id="d553e-279">Removed permissions from folder</span></span>  <br/> |<span data-ttu-id="d553e-280">UpdateFolderPermissions</span><span class="sxs-lookup"><span data-stu-id="d553e-280">UpdateFolderPermissions</span></span>  <br/> |
    |<span data-ttu-id="d553e-281">添加或删除用户对日历文件夹的代理访问</span><span class="sxs-lookup"><span data-stu-id="d553e-281">Added or removed user with delegate access to calendar folder</span></span>  <br/> |<span data-ttu-id="d553e-282">UpdateCalendarDelegation</span><span class="sxs-lookup"><span data-stu-id="d553e-282">UpdateCalendarDelegation</span></span>  <br/> |
   
    <span data-ttu-id="d553e-p121">请注意，以前的屏幕截图中所示**添加代理邮箱权限**和**删除代理邮箱权限**活动不到邮箱审核操作相关。及其指示是否管理员分配或删除 FullAccess 邮箱权限。</span><span class="sxs-lookup"><span data-stu-id="d553e-p121">Note that the **Added delegate mailbox permissions** and **Removed delegate mailbox permissions** activities shown in the previous screenshot aren't related to mailbox auditing actions. They indicate whether an administrator assigned or removed the FullAccess mailbox permission.</span></span> 
    
    <span data-ttu-id="d553e-285">有关 Office 365 审核日志的信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="d553e-285">For information about the Office 365 audit log, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
- <span data-ttu-id="d553e-286">只有在以下情况下，才视为由管理员访问邮箱：</span><span class="sxs-lookup"><span data-stu-id="d553e-286">Mailboxes are considered to be accessed by an administrator only in the following scenarios:</span></span>
    
  - <span data-ttu-id="d553e-287">使用 Exchange Online 或 Office 365 中的内容搜索中的就地电子数据展示搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-287">In-Place eDiscovery in Exchange Online or Content Search in Office 365 is used to search a mailbox.</span></span>
    
  - <span data-ttu-id="d553e-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) 用于访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="d553e-288">[Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086) is used to access the mailbox.</span></span> 
    
- <span data-ttu-id="d553e-289">为邮箱启用审核日志记录时，也可以指定将记录每种登录类型（管理员、委派用户或所有者）的哪些用户操作（例如，访问、移动或删除邮件）。 </span><span class="sxs-lookup"><span data-stu-id="d553e-289">When you enable audit logging for a mailbox, you can also specify which user actions (for example, accessing, moving, or deleting a message) will be logged for each logon type (admin, delegate, or owner).</span></span>
    
- <span data-ttu-id="d553e-290">若要禁用邮箱审核日志记录，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d553e-290">To disable mailbox audit logging, run the following command:</span></span>

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- <span data-ttu-id="d553e-p122">运行**Get-mailbox** cmdlet 时，不会显示为每种类型的用户审核的操作。但是，您可以运行以下命令以显示特定用户登录类型的所有审核的操作。</span><span class="sxs-lookup"><span data-stu-id="d553e-p122">The actions that are audited for each type of user aren't displayed when you run the **Get-Mailbox** cmdlet. But you can run the following commands to display all the audited actions for a specific user logon type.</span></span> 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- <span data-ttu-id="d553e-p123">您还可以导出邮箱审核日志，并指定要包含一个或多个用户的条目。报表和审核日志中的每个条目包含有关用户执行操作时，将执行的操作，和操作是否成功的信息。有关详细信息，请参阅[导出邮箱审核日志](https://go.microsoft.com/fwlink/p/?LinkID=404104)。</span><span class="sxs-lookup"><span data-stu-id="d553e-p123">You can also export a mailbox audit log and specify the entries to include for one or more users. Each entry in the report and the audit log includes information about who performed the action and when, the action performed , and whether the action was successful. For more information, see [Export mailbox audit logs](https://go.microsoft.com/fwlink/p/?LinkID=404104).</span></span>
