---
title: 在 Office 365 安全&amp;合规中心中启用存档邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 安全&amp;合规中心启用存档邮箱, 以支持组织的邮件保留、电子数据展示和保留要求。
ms.openlocfilehash: 39cd5fd8d7991b787d95e39e4994dc9b0786522c
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341793"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="383d9-103">在 Office 365 安全&amp;合规中心中启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="383d9-p101">Office 365 中的存档 (也称为就地存档) 为用户提供额外的邮箱存储空间。打开存档邮箱后, 用户可以使用 Microsoft Outlook 和 web 上的 outlook (以前称为 outlook web App) 访问存档邮箱中的邮件并将其存储在其存档邮箱中。用户还可以在主邮箱与其存档邮箱之间移动或复制邮件。他们还可以使用 "恢复已删除邮件" 工具, 从存档邮箱中的 "可恢复的项目" 文件夹中恢复已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="383d9-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook on the web (formerly known as Outlook Web App). Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="383d9-p102">Office 365 提供了无限制的存档存储量和自动扩展的存档功能。如果启用了自动扩展存档, 然后达到用户存档邮箱中的初始存储配额, Office 365 将自动添加额外的存储空间。这意味着用户不会用尽邮箱存储空间, 并且在最初启用存档邮箱并为您的组织启用自动扩展存档后, 无需管理任何内容。有关详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="383d9-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="383d9-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="383d9-112">Before you begin</span></span>

<span data-ttu-id="383d9-p103">您必须分配有 Exchange Online 中的 "邮件收件人" 角色, 才能启用或禁用存档邮箱。默认情况下, 此角色分配给 Exchange 管理中心中的 "**权限**" 页上的 "收件人管理" 和 "组织管理" 角色组。如果您在安全&amp;合规中心中看不到 "**存档**" 页, 请让管理员为您分配必要的权限。</span><span class="sxs-lookup"><span data-stu-id="383d9-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="383d9-116">启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="383d9-117">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="383d9-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="383d9-118">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="383d9-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="383d9-119">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **存档**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="383d9-p104">将显示 "**存档**" 页。"**存档邮箱**" 列指示是否为每个用户启用或禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="383d9-122">在邮箱的列表中，选择要启用存档邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="383d9-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![在选定用户的细节窗格中单击 "启用" 以启用存档邮箱](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="383d9-124">在所选用户的详细信息窗格中, 单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="383d9-p105">将显示一条警告消息, 指出如果您启用存档邮箱, 用户邮箱中早于分配给邮箱的存档策略的项目将移至新的存档邮箱。作为分配给 Exchange Online 邮箱的保留策略的一部分的默认存档策略将项目移至存档邮箱, 在将项目传递到邮箱或由用户创建的日期之后两年。有关详细信息, 请参阅本文中的**详细**信息部分。</span><span class="sxs-lookup"><span data-stu-id="383d9-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="383d9-128">单击 **"是"** 启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="383d9-p106">可能需要几分钟才能创建存档邮箱。创建后, 会在所选用户的详细信息窗格中显示 "**存档邮箱: 已启用**"。您可能需要单击 "**刷新** ![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="383d9-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="383d9-p107">您还可以通过选择多个已禁用存档邮箱的用户 (使用 Shift 或 Ctrl 键) 来批量启用存档邮箱。选择多个邮箱后, 在详细信息窗格中单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="383d9-134">禁用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="383d9-p108">您还可以使用安全\*\*\*\* &amp;合规中心中的 "存档" 页来禁用用户的存档邮箱。禁用存档邮箱后, 可以在禁用存档邮箱后的30天内将其重新连接到用户的主邮箱。在这种情况下, 将还原存档邮箱的原始内容。30天后, 原始存档邮箱的内容将被永久删除且无法恢复。因此, 如果在禁用存档后30天内重新启用存档, 则会创建一个新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="383d9-p109">请注意, 分配给用户邮箱的默认存档策略将项目移动到存档邮箱的时间, 在该项目送达后两年。如果禁用用户的存档邮箱, 则不会对邮箱项目执行任何操作, 它们将保留在用户的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="383d9-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="383d9-142">要禁用存档邮箱, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="383d9-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="383d9-143">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="383d9-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="383d9-144">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="383d9-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="383d9-145">在安全&amp;合规性中心的左侧窗格中, 单击 "**数据调控** \> **存档**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="383d9-p110">将显示 "**存档**" 页。"**存档邮箱**" 列指示是否为每个用户启用或禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="383d9-148">在邮箱的列表中，选择要禁用存档邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="383d9-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="383d9-149">在详细信息窗格中, 单击 "**禁用**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="383d9-150">将显示一条警告消息, 指出您将有30天时间重新启用存档邮箱, 并且30天后, 存档中的所有信息将永久删除。</span><span class="sxs-lookup"><span data-stu-id="383d9-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="383d9-151">单击 **"是"** 以禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="383d9-p111">可能需要几分钟才能禁用存档邮箱。如果禁用此选项, 则会在所选用户的详细信息窗格中显示 "**存档邮箱: 禁用**"。您可能需要单击 "**刷新** ![刷新"](media/O365-MDM-Policy-RefreshIcon.gif)图标以更新详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="383d9-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="383d9-p112">您还可以通过选择具有已启用存档邮箱的多个用户 (使用 Shift 或 Ctrl 键) 来批量禁用存档邮箱。选择多个邮箱后, 在详细信息窗格中单击 "**禁用**"。</span><span class="sxs-lookup"><span data-stu-id="383d9-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a><span data-ttu-id="383d9-157">使用 Exchange Online PowerShell 启用或禁用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-157">Use Exchange Online PowerShell to enable or disable archive mailboxes</span></span>

<span data-ttu-id="383d9-p113">您还可以使用 Exchange Online PowerShell 启用存档邮箱。使用 PowerShell 的主要原因是您可以为组织中的所有用户快速启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-p113">You can also use Exchange Online PowerShell to enable archive mailboxes. The primary reason to use PowerShell is that you can quickly enable the archive mailbox for all users in your organization.</span></span>

<span data-ttu-id="383d9-p114">第一步是连接到 Exchange Online PowerShell。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="383d9-p114">The first step is to connect to Exchange Online PowerShell. For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="383d9-162">连接到 Exchange Online 后, 可以运行以下各节中的命令来启用或禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-162">After you're connected to Exchange Online, you can run the commands in the following sections to enable or disable archive mailboxes.</span></span>

### <a name="enable-archive-mailboxes"></a><span data-ttu-id="383d9-163">启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-163">Enable archive mailboxes</span></span>

<span data-ttu-id="383d9-164">运行以下命令, 为单个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-164">Run the following command to enable the archive mailbox for a single user.</span></span>
    
  ```
  Enable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="383d9-165">运行以下命令, 为组织中的所有用户启用存档邮箱 (其存档邮箱当前未启用)。</span><span class="sxs-lookup"><span data-stu-id="383d9-165">Run the following command to enable the archive mailbox for all users in your organization (whose archive mailbox is currently not enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
  ```
  
### <a name="disable-archive-mailboxes"></a><span data-ttu-id="383d9-166">禁用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="383d9-166">Disable archive mailboxes</span></span>

<span data-ttu-id="383d9-167">运行以下命令, 为单个用户禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-167">Run the following command to disable the archive mailbox for a single user.</span></span>
    
  ```
  Disable-Mailbox -Identity <username> -Archive
  ```

<span data-ttu-id="383d9-168">运行以下命令, 为组织中的所有用户 (其存档邮箱当前已启用) 禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-168">Run the following command to disable the archive mailbox for all users in your organization (whose archive mailbox is currently enabled).</span></span>
    
  ```
  Get-Mailbox -Filter {ArchiveStatus -Eq "Active" -AND RecipientTypeDetails -eq "UserMailbox"} | Disable-Mailbox -Archive
  ```

## <a name="more-information"></a><span data-ttu-id="383d9-169">更多信息</span><span class="sxs-lookup"><span data-stu-id="383d9-169">More information</span></span>
  
- <span data-ttu-id="383d9-p115">存档邮箱可帮助您和您的用户满足组织的保留、电子数据展示和保留要求。例如, 您可以使用组织的 Exchange 保留策略将邮箱内容移动到用户的存档邮箱。当您使用安全&amp;合规中心中的内容搜索工具搜索特定内容的用户邮箱时, 还会搜索用户的存档邮箱。在你将诉讼保留或应用 Office 365 保留策略到用户的邮箱时, 存档邮箱中的项目也会保留。</span><span class="sxs-lookup"><span data-stu-id="383d9-p115">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="383d9-p116">启用存档邮箱后, 用户可以将邮件存储在其存档邮箱中。用户可以使用 Microsoft Outlook 和 web 上的 outlook 访问其存档邮箱。通过使用这些客户端应用程序中的任何一个, 用户都可以查看其存档邮箱中的邮件, 并在其主邮箱与其存档邮箱之间移动或复制邮件。用户还可以使用 "恢复已删除邮件" 工具, 从存档邮箱的 "可恢复的项目" 文件夹中恢复已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="383d9-p116">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook on the web. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="383d9-p117">启用存档邮箱后, 您的组织可以利用自动分配给每个邮箱的默认 Exchange 保留策略 (也称为 "邮件记录管理" 或 "MRM 策略")。启用存档邮箱后, 默认的 Exchange 保留策略将自动执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="383d9-p117">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="383d9-180">将两年或以上的邮件从用户主邮箱移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="383d9-180">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="383d9-181">将 14 天或以上的邮件从用户主邮箱的"可恢复的项目"文件夹移动到存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="383d9-181">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="383d9-182">有关存档邮箱和 Exchange 保留策略的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="383d9-182">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
    
  - [<span data-ttu-id="383d9-183">保留标记和保留策略</span><span class="sxs-lookup"><span data-stu-id="383d9-183">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="383d9-184">Exchange Online 中的默认保留策略</span><span class="sxs-lookup"><span data-stu-id="383d9-184">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="383d9-185">为 Office 365 组织中的邮箱设置存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="383d9-185">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
