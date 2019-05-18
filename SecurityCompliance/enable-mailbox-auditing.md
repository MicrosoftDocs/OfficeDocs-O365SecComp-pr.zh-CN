---
title: 管理邮箱审核
ms.author: chrisda
author: chrisda
manager: serdars
audience: Admin
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
description: 默认情况下, 邮箱审核日志记录在 Microsoft 365 (也称为默认邮箱审核或邮箱审核) 中处于打开状态。 这意味着邮箱所有者、代理人和管理员执行的某些操作将自动记录在邮箱审核日志中, 在此日志中可以搜索在邮箱上执行的活动。
ms.openlocfilehash: 8e5901586b6ee8e34d3e71b0b256f9aa7c86c7de
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154774"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="cc13a-104">管理邮箱审核</span><span class="sxs-lookup"><span data-stu-id="cc13a-104">Manage mailbox auditing</span></span>

<span data-ttu-id="cc13a-105">从2019年1月起, Microsoft 将默认为所有 Microsoft 365 组织启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all Microsoft 365 organizations.</span></span> <span data-ttu-id="cc13a-106">这意味着邮箱所有者、代理人和管理员执行的某些操作将会自动记录, 当您在邮箱审核日志中搜索时, 相应的邮箱审核记录将可用。</span><span class="sxs-lookup"><span data-stu-id="cc13a-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="cc13a-107">默认情况下, 邮箱审核启用前, 您必须为组织中的每个用户邮箱手动启用它。</span><span class="sxs-lookup"><span data-stu-id="cc13a-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="cc13a-108">以下是邮箱审核在默认情况下的一些优点:</span><span class="sxs-lookup"><span data-stu-id="cc13a-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="cc13a-109">当您创建新邮箱时, 将自动启用审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="cc13a-110">您无需为新用户手动启用它。</span><span class="sxs-lookup"><span data-stu-id="cc13a-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="cc13a-111">您无需管理已审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="cc13a-112">默认情况下, 会为每个登录类型 (管理员、代理和所有者) 审核一组预定义的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="cc13a-113">当 Microsoft 发布新邮箱操作 (尤其是帮助保护组织并帮助进行法庭调查的操作) 时, 会自动将该操作添加到默认情况下审核的邮箱操作列表中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-113">When Microsoft releases a new mailbox action (particularly actions that help protect your organization and help with forensic investigations), the action is automatically added to the list of mailbox actions that are audited by default.</span></span> <span data-ttu-id="cc13a-114">这意味着您无需监视对邮箱添加的新操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="cc13a-115">您的组织中有一致的邮箱审核策略 (因为您正在审核对所有邮箱的相同操作)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!TIP]
> <span data-ttu-id="cc13a-116">有关默认情况下的邮箱审核发布的重要事项是: 不需要执行任何操作来管理邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-116">The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="cc13a-117">但是, 若要了解详细信息, 自定义邮箱审核的默认设置, 或将其全部关闭, 本主题可为你有所帮助。</span><span class="sxs-lookup"><span data-stu-id="cc13a-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="cc13a-118">默认情况下验证邮箱审核启用</span><span class="sxs-lookup"><span data-stu-id="cc13a-118">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="cc13a-119">若要验证您的组织的默认邮箱审核是否已启用, 请在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-119">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="cc13a-120">值**为 False**表示对组织启用默认情况下邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-120">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="cc13a-121">默认情况下, 此设置将覆盖特定邮箱上的邮箱审核设置。</span><span class="sxs-lookup"><span data-stu-id="cc13a-121">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="cc13a-122">例如, 如果对邮箱禁用了邮箱审核 (邮箱上的*AuditEnabled*属性为**False** ), 则仍将审核邮箱的默认邮箱操作, 因为默认情况下邮箱审核启用了组织.</span><span class="sxs-lookup"><span data-stu-id="cc13a-122">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="cc13a-123">若要将特定邮箱的邮箱审核功能保持为禁用状态, 请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核旁路。</span><span class="sxs-lookup"><span data-stu-id="cc13a-123">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="cc13a-124">有关详细信息, 请参阅本主题中的[绕过邮箱审核日志记录](#bypass-mailbox-audit-logging)一节。</span><span class="sxs-lookup"><span data-stu-id="cc13a-124">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="cc13a-125">如果为组织启用了默认情况下的邮箱审核, 则受影响的邮箱的*AuditEnabled*属性不会从**False**更改为**True**。</span><span class="sxs-lookup"><span data-stu-id="cc13a-125">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="cc13a-126">换言之, 默认情况下邮箱审核将忽略邮箱上的*AuditEnabled*属性。</span><span class="sxs-lookup"><span data-stu-id="cc13a-126">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="cc13a-127">支持的邮箱类型</span><span class="sxs-lookup"><span data-stu-id="cc13a-127">Supported mailbox types</span></span>

<span data-ttu-id="cc13a-128">下表显示了默认情况下邮箱审核当前支持的邮箱类型:</span><span class="sxs-lookup"><span data-stu-id="cc13a-128">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="cc13a-129">**邮箱类型**</span><span class="sxs-lookup"><span data-stu-id="cc13a-129">**Mailbox type**</span></span>|<span data-ttu-id="cc13a-130">**支持**</span><span class="sxs-lookup"><span data-stu-id="cc13a-130">**Supported**</span></span>|<span data-ttu-id="cc13a-131">**不支持**</span><span class="sxs-lookup"><span data-stu-id="cc13a-131">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="cc13a-132">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="cc13a-132">User mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="cc13a-134">共享邮箱</span><span class="sxs-lookup"><span data-stu-id="cc13a-134">Shared mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="cc13a-136">Office 365 组邮箱</span><span class="sxs-lookup"><span data-stu-id="cc13a-136">Office 365 Group mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="cc13a-138">资源邮箱</span><span class="sxs-lookup"><span data-stu-id="cc13a-138">Resource mailboxes</span></span>||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-140">公用文件夹邮箱</span><span class="sxs-lookup"><span data-stu-id="cc13a-140">Public folder mailboxes</span></span>||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="cc13a-142">登录类型和邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-142">Logon types and mailbox actions</span></span>

<span data-ttu-id="cc13a-143">登录类型对对邮箱执行了审核操作的用户进行分类。</span><span class="sxs-lookup"><span data-stu-id="cc13a-143">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="cc13a-144">以下列表介绍了邮箱审核日志记录中使用的登录类型:</span><span class="sxs-lookup"><span data-stu-id="cc13a-144">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="cc13a-145">**Owner**: 邮箱所有者 (与邮箱关联的帐户)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-145">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="cc13a-146">**委派**:</span><span class="sxs-lookup"><span data-stu-id="cc13a-146">**Delegate**:</span></span>

  - <span data-ttu-id="cc13a-147">向另一个邮箱分配了 SendAs、SendOnBehalf 或 FullAccess 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="cc13a-147">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="cc13a-148">为用户的邮箱分配了 FullAccess 权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="cc13a-148">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="cc13a-149">**管理员**:</span><span class="sxs-lookup"><span data-stu-id="cc13a-149">**Admin**:</span></span>

  - <span data-ttu-id="cc13a-150">使用以下其中一种 Microsoft 电子数据展示工具搜索邮箱:</span><span class="sxs-lookup"><span data-stu-id="cc13a-150">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="cc13a-151">合规性中心中的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="cc13a-151">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="cc13a-152">合规中心中的电子数据展示或高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="cc13a-152">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="cc13a-153">Exchange Online 中的就地电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="cc13a-153">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="cc13a-154">可以使用[Microsoft Exchange SERVER MAPI 编辑器](https://go.microsoft.com/fwlink/p/?linkId=204086)访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="cc13a-154">The mailbox is accessed by using the [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086).</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="cc13a-155">用户邮箱和共享邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-155">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="cc13a-156">下表介绍了可用于用户邮箱和共享邮箱的邮箱审核日志记录中的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-156">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="cc13a-157">一个复选标记 (</span><span class="sxs-lookup"><span data-stu-id="cc13a-157">A check mark (</span></span> ![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="cc13a-159">) 表示可以为登录类型记录邮箱操作 (并非所有操作都适用于所有登录类型)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-159">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="cc13a-160">在复选标记<sup>\*</sup>后面有一个星号 () 表示邮箱操作在默认情况下会记录在登录类型中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-160">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="cc13a-161">请记住, 对邮箱具有完全访问权限的管理员被视为代理。</span><span class="sxs-lookup"><span data-stu-id="cc13a-161">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="cc13a-162">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="cc13a-162">**Mailbox action**</span></span>|<span data-ttu-id="cc13a-163">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc13a-163">**Description**</span></span>|<span data-ttu-id="cc13a-164">**管理员**</span><span class="sxs-lookup"><span data-stu-id="cc13a-164">**Admin**</span></span>|<span data-ttu-id="cc13a-165">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="cc13a-165">**Delegate**</span></span>|<span data-ttu-id="cc13a-166">**所有者**</span><span class="sxs-lookup"><span data-stu-id="cc13a-166">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="cc13a-167">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="cc13a-167">**AddFolderPermissions**</span></span>|<span data-ttu-id="cc13a-168">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-168">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="cc13a-169">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-169">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="cc13a-170">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="cc13a-170">**ApplyRecord**</span></span>|<span data-ttu-id="cc13a-171">项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-171">An item is labeled as a record.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-175">**复制**</span><span class="sxs-lookup"><span data-stu-id="cc13a-175">**Copy**</span></span>|<span data-ttu-id="cc13a-176">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc13a-176">A message was copied to another folder.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="cc13a-178">**创建**</span><span class="sxs-lookup"><span data-stu-id="cc13a-178">**Create**</span></span>|<span data-ttu-id="cc13a-179">在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建了一个项目 (例如, 创建了一个新的会议请求)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-179">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="cc13a-180">请注意, 不会审核创建、发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-180">Note that creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="cc13a-181">此外, 还不会审核创建邮箱文件夹的情况。</span><span class="sxs-lookup"><span data-stu-id="cc13a-181">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="cc13a-182">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-182">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-183">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-183">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-185">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="cc13a-185">**FolderBind**</span></span>|<span data-ttu-id="cc13a-186">已访问某个邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc13a-186">A mailbox folder was accessed.</span></span> <span data-ttu-id="cc13a-187">当管理员或委派打开邮箱时, 也会记录此操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-187">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="cc13a-188">**注意**: 代理执行的文件夹绑定操作的审核记录已合并。</span><span class="sxs-lookup"><span data-stu-id="cc13a-188">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="cc13a-189">在24小时内为单个文件夹访问生成一个审核记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-189">One audit record is generated for individual folder access within 24 hour period.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="cc13a-192">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="cc13a-192">**HardDelete**</span></span>|<span data-ttu-id="cc13a-193">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="cc13a-193">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="cc13a-194">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-194">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-195">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-195">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-196">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-196">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-197">**Mailboxlogin 该值**</span><span class="sxs-lookup"><span data-stu-id="cc13a-197">**MailboxLogin**</span></span>|<span data-ttu-id="cc13a-198">用户已登录到其邮箱。</span><span class="sxs-lookup"><span data-stu-id="cc13a-198">The user signed into their mailbox.</span></span> |||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-200">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="cc13a-200">**MessageBind**</span></span>|<span data-ttu-id="cc13a-201">**注意**: 此操作已从 Exchange Online 中弃用, 不再可添加到管理员邮箱操作列表中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-201">**Note**: This action has been deprecated from Exchange Online, and is no longer available to add to the list of admin mailbox actions.</span></span><br/><br/> <span data-ttu-id="cc13a-202">在预览窗格查看邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-202">A message was viewed in the preview pane or opened.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="cc13a-204">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="cc13a-204">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="cc13a-205">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-205">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="cc13a-206">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-206">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="cc13a-207">**移动**</span><span class="sxs-lookup"><span data-stu-id="cc13a-207">**Move**</span></span>|<span data-ttu-id="cc13a-208">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc13a-208">A message was moved to another folder.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-212">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="cc13a-212">**MoveToDeletedItems**</span></span>|<span data-ttu-id="cc13a-213">邮件已被删除并移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc13a-213">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="cc13a-214">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-214">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-215">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-215">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-216">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-216">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-217">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="cc13a-217">**RecordDelete**</span></span>|<span data-ttu-id="cc13a-218">标记为记录的项目已软删除 (移动到 "可恢复的项目" 文件夹)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-218">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="cc13a-219">标记为记录的项目无法永久删除 (从 "可恢复的项目" 文件夹中清除)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-219">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="cc13a-223">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="cc13a-223">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="cc13a-224">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-224">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="cc13a-225">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-225">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="cc13a-226">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="cc13a-226">**SendAs**</span></span>|<span data-ttu-id="cc13a-227">邮件是使用 SendAs 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="cc13a-227">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="cc13a-228">这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="cc13a-228">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="cc13a-229">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-229">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-230">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-230">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="cc13a-231">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="cc13a-231">**SendOnBehalf**</span></span>|<span data-ttu-id="cc13a-232">邮件是使用 SendOnBehalf 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="cc13a-232">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="cc13a-233">这表示另一个用户代表邮箱所有者发送了邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-233">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="cc13a-234">该邮件指示收件人代表发送邮件的收件人和实际发送邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="cc13a-234">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="cc13a-235">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-235">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-236">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-236">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="cc13a-237">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="cc13a-237">**SoftDelete**</span></span>|<span data-ttu-id="cc13a-238">邮件已从 "已删除邮件" 文件夹中永久删除或删除。</span><span class="sxs-lookup"><span data-stu-id="cc13a-238">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="cc13a-239">软删除的项目将移动到 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-239">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="cc13a-240">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-240">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-241">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-241">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-242">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-242">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-243">**更新**</span><span class="sxs-lookup"><span data-stu-id="cc13a-243">**Update**</span></span>|<span data-ttu-id="cc13a-244">更改了邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="cc13a-244">A message or its properties was changed.</span></span>|<span data-ttu-id="cc13a-245">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-245">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-246">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-246">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-247">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-247">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-248">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="cc13a-248">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="cc13a-249">向邮箱分配了日历委派。</span><span class="sxs-lookup"><span data-stu-id="cc13a-249">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="cc13a-250">日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。</span><span class="sxs-lookup"><span data-stu-id="cc13a-250">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="cc13a-251">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-251">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||<span data-ttu-id="cc13a-252">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-252">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-253">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="cc13a-253">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="cc13a-254">更改了文件夹权限。</span><span class="sxs-lookup"><span data-stu-id="cc13a-254">A folder permission was changed.</span></span> <span data-ttu-id="cc13a-255">文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-255">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="cc13a-256">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-256">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-257">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-257">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-258">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-258">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-259">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="cc13a-259">**UpdateInboxRules**</span></span>|<span data-ttu-id="cc13a-260">添加、删除或更改了收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="cc13a-260">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="cc13a-261">"收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-261">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="cc13a-262">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-262">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-263">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-263">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-264">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-264">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="cc13a-265">如果您在组织中对邮箱操作进行自定义, 以便在默认情况下在邮箱审核启用*前*对任何登录类型进行审核, 则这些自定义设置将保留在邮箱中, 且不会被默认邮箱操作覆盖为本节中所述。</span><span class="sxs-lookup"><span data-stu-id="cc13a-265">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="cc13a-266">若要将审核邮箱操作还原为其默认值 (可在任何时候执行), 请参阅本主题后面的[还原默认邮箱操作](#restore-the-default-mailbox-actions)部分。</span><span class="sxs-lookup"><span data-stu-id="cc13a-266">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a><span data-ttu-id="cc13a-267">适用于 Office 365 组邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-267">Mailbox actions for Office 365 Group mailboxes</span></span>

<span data-ttu-id="cc13a-268">默认情况下的邮箱审核会将邮箱审核日志记录提供给 Office 365 组邮箱, 但不能自定义要记录的内容 (您无法添加或删除为任何登录类型记录的邮箱操作)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-268">Mailbox auditing on by default brings mailbox audit logging to Office 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="cc13a-269">下表介绍了默认情况下在每个登录类型的 Office 365 组邮箱上记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-269">The following table describes the mailbox actions that are logged by default on Office 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="cc13a-270">请记住, 对 Office 365 组邮箱具有完全访问权限的管理员被视为代理。</span><span class="sxs-lookup"><span data-stu-id="cc13a-270">Remember, an admin with Full Access permission to an Office 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="cc13a-271">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="cc13a-271">**Mailbox action**</span></span>|<span data-ttu-id="cc13a-272">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc13a-272">**Description**</span></span>|<span data-ttu-id="cc13a-273">**管理员**</span><span class="sxs-lookup"><span data-stu-id="cc13a-273">**Admin**</span></span>|<span data-ttu-id="cc13a-274">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="cc13a-274">**Delegate**</span></span>|<span data-ttu-id="cc13a-275">**所有者**</span><span class="sxs-lookup"><span data-stu-id="cc13a-275">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="cc13a-276">**创建**</span><span class="sxs-lookup"><span data-stu-id="cc13a-276">**Create**</span></span>|<span data-ttu-id="cc13a-277">创建日历项目。</span><span class="sxs-lookup"><span data-stu-id="cc13a-277">Creation of a calendar Item.</span></span> <span data-ttu-id="cc13a-278">请注意, 不会审核创建、发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-278">Note that creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="cc13a-279">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-279">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-280">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-280">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="cc13a-281">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="cc13a-281">**HardDelete**</span></span>|<span data-ttu-id="cc13a-282">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="cc13a-282">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="cc13a-283">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-283">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-284">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-284">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-285">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-285">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-286">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="cc13a-286">**MoveToDeletedItems**</span></span>|<span data-ttu-id="cc13a-287">邮件已被删除并移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc13a-287">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="cc13a-288">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-288">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-289">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-289">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-290">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-290">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-291">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="cc13a-291">**SendAs**</span></span>|<span data-ttu-id="cc13a-292">邮件是使用 SendAs 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="cc13a-292">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="cc13a-293">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-293">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-294">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-294">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="cc13a-295">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="cc13a-295">**SendOnBehalf**</span></span>|<span data-ttu-id="cc13a-296">邮件是使用 SendOnBehalf 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="cc13a-296">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="cc13a-297">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-297">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-298">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-298">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="cc13a-299">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="cc13a-299">**SoftDelete**</span></span>|<span data-ttu-id="cc13a-300">邮件已从 "已删除邮件" 文件夹中永久删除或删除。</span><span class="sxs-lookup"><span data-stu-id="cc13a-300">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="cc13a-301">软删除的项目将移动到 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-301">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="cc13a-302">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-302">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-303">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-303">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-304">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-304">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="cc13a-305">**更新**</span><span class="sxs-lookup"><span data-stu-id="cc13a-305">**Update**</span></span>|<span data-ttu-id="cc13a-306">更改了邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="cc13a-306">A message or its properties was changed.</span></span>|<span data-ttu-id="cc13a-307">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-307">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-308">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-308">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="cc13a-309">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cc13a-309">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="cc13a-310">验证是否为每个登录类型记录了默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-310">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="cc13a-311">默认情况之下的邮箱审核将新的*DefaultAuditSet*属性添加到所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="cc13a-311">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="cc13a-312">此属性的值指示是否在邮箱上审核默认邮箱操作 (由 Microsoft 管理)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-312">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="cc13a-313">若要在用户邮箱或共享邮箱上显示值, \<请\>将 MailboxIdentity 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名), 并在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-313">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="cc13a-314">若要在 Office 365 组邮箱中显示值, \<请\>将 MailboxIdentity 替换为共享邮箱的名称、别名或电子邮件地址, 并在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-314">To display the value on Office 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="cc13a-315">该值`Admin, Delegate, Owner`指示:</span><span class="sxs-lookup"><span data-stu-id="cc13a-315">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="cc13a-316">审核所有三种登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-316">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="cc13a-317">请注意, 这是你将在 Office 365 组邮箱中看到的唯一值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-317">Note that this is the only value you'll see on Office 365 Group mailboxes.</span></span>

- <span data-ttu-id="cc13a-318">管理员尚未\*\* 更改用户邮箱或共享邮箱上任何登录类型的已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-318">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="cc13a-319">注释默认情况下, 这是在组织中最初启用邮箱审核之后的默认状态。</span><span class="sxs-lookup"><span data-stu-id="cc13a-319">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="cc13a-320">如果管理员曾更改过为登录类型审核的邮箱操作 (通过使用**设置邮箱**cmdlet 上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数), 则该属性值将有所不同。</span><span class="sxs-lookup"><span data-stu-id="cc13a-320">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="cc13a-321">例如, 用户邮箱或`Owner`共享邮箱上的*DefaultAuditSet*属性的值表示:</span><span class="sxs-lookup"><span data-stu-id="cc13a-321">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="cc13a-322">审核邮箱所有者的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-322">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="cc13a-323">已从默认操作更改了`Delegate`和`Admin`登录类型的已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-323">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="cc13a-324">*DefaultAuditSet*属性的空值表示已在用户邮箱或共享邮箱上更改了所有三种登录类型的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-324">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="cc13a-325">有关详细信息, 请参阅本主题中的 "[更改或还原在默认情况下记录的邮箱操作](#change-or-restore-mailbox-actions-logged-by-default)" 部分</span><span class="sxs-lookup"><span data-stu-id="cc13a-325">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="cc13a-326">显示正在登录邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-326">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="cc13a-327">若要查看当前登录用户邮箱或共享邮箱的邮箱操作, 请将 MailboxIdentity \<\>替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名), 并运行以下一个或多个Exchange Online PowerShell 中的命令。</span><span class="sxs-lookup"><span data-stu-id="cc13a-327">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="cc13a-328">虽然您可以将此`-GroupMailbox`开关添加到 Office 365 组邮箱的以下**Get 邮箱**命令中, 但不相信您看到的值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-328">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Office 365 Group mailboxes, don't believe the values you see.</span></span> <span data-ttu-id="cc13a-329">本主题前面的 " [office 365 组邮箱的邮箱操作](#mailbox-actions-for-office-365-group-mailboxes)" 一节中介绍了为 Office 365 组邮箱审核的默认和静态邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-329">The default and static mailbox actions that are audited for Office 365 Group mailboxes are described in the [Mailbox actions for Office 365 Group mailboxes](#mailbox-actions-for-office-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="cc13a-330">所有者操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-330">Owner actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="cc13a-331">委派操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-331">Delegate actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="cc13a-332">管理操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-332">Admin actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="cc13a-333">更改或还原默认情况下记录的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-333">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="cc13a-334">如前所述, 默认情况下启用邮箱审核的主要好处之一是: 无需管理已审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-334">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="cc13a-335">Microsoft 为你执行此操作, 我们将在默认情况下自动添加要审核的新邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-335">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="cc13a-336">但是, 您的组织可能需要审核用户邮箱和共享邮箱的一组不同的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-336">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="cc13a-337">本部分中的过程介绍如何更改针对每种登录类型进行审核的邮箱操作, 以及如何还原为 Microsoft 托管的默认操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-337">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc13a-338">如果使用以下过程自定义登录用户邮箱或共享邮箱的邮箱操作, 则任何由 Microsoft 发布的新默认邮箱操作都不会在这些邮箱上自动进行审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-338">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="cc13a-339">您需要将任何新邮箱操作手动添加到自定义的操作列表中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-339">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="cc13a-340">更改要审核的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-340">Change the mailbox actions to audit</span></span>

<span data-ttu-id="cc13a-341">您可以使用**设置邮箱**cmdlet 上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数更改为用户邮箱和共享邮箱审核的邮箱操作 (针对 Office 365 组的已审核操作无法自定义邮箱。</span><span class="sxs-lookup"><span data-stu-id="cc13a-341">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Office 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="cc13a-342">您可以使用两种不同的方法来指定邮箱操作:</span><span class="sxs-lookup"><span data-stu-id="cc13a-342">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="cc13a-343">*Replace*(使用以下语法来覆盖) 现有邮箱操作: `action1,action2,...actionN`。</span><span class="sxs-lookup"><span data-stu-id="cc13a-343">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="cc13a-344">使用以下语法在不影响其他现有值的情况下*添加或删除*邮箱操作: `@{Add="action1","action2",..."actionN"}`或`@{Remove="action1","action2",..."actionN"}`。</span><span class="sxs-lookup"><span data-stu-id="cc13a-344">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="cc13a-345">此示例通过使用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为 "Gabriela Laureano" 的邮箱的管理员邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-345">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="cc13a-346">本示例将 Mailboxlogin 该值 owner 操作添加到邮箱 laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="cc13a-346">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="cc13a-347">本示例删除工作组讨论邮箱的 MoveToDeletedItems 委派操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-347">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="cc13a-348">无论使用哪种方法, 自定义对用户邮箱或共享邮箱的审核邮箱操作都有以下结果:</span><span class="sxs-lookup"><span data-stu-id="cc13a-348">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="cc13a-349">对于您自定义的登录类型, 已审核的邮箱操作不再由 Microsoft 进行管理。</span><span class="sxs-lookup"><span data-stu-id="cc13a-349">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="cc13a-350">您自定义的登录类型不再像[前面所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)的那样显示在邮箱的*DefaultAuditSet*属性值中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-350">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="cc13a-351">还原默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="cc13a-351">Restore the default mailbox actions</span></span>

<span data-ttu-id="cc13a-352">如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作, 则可以使用以下语法还原一种或多种登录类型的默认邮箱操作:</span><span class="sxs-lookup"><span data-stu-id="cc13a-352">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="cc13a-353">可以指定用逗号分隔的多个*DefaultAuditSet*值</span><span class="sxs-lookup"><span data-stu-id="cc13a-353">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="cc13a-354">**注意**: 以下过程不适用于 Office 365 组邮箱 (仅限于[此处](#mailbox-actions-for-office-365-group-mailboxes)所述的默认操作)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-354">**Note**: The following procedures don't apply to Office 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-office-365-group-mailboxes)).</span></span>

<span data-ttu-id="cc13a-355">本示例将还原邮箱 mark@contoso.onmicrosoft.com 上所有登录类型的默认审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-355">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="cc13a-356">本示例将还原邮箱 chris@contoso.onmicrosoft.com 上的管理员登录类型的默认审核邮箱操作, 但保留代理和所有者登录类型的自定义已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-356">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="cc13a-357">为登录类型还原默认的已审核邮箱操作的结果如下:</span><span class="sxs-lookup"><span data-stu-id="cc13a-357">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="cc13a-358">邮箱操作的当前列表将替换为登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-358">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="cc13a-359">由 Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的已审核操作列表中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-359">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="cc13a-360">邮箱的*DefaultAuditSet*属性值将更新, 以包含已还原的登录类型。</span><span class="sxs-lookup"><span data-stu-id="cc13a-360">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="cc13a-361">为你的组织默认关闭邮箱审核</span><span class="sxs-lookup"><span data-stu-id="cc13a-361">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="cc13a-362">您可以通过在 Exchange Online PowerShell 中运行以下命令, 在默认情况下为整个组织关闭邮箱审核:</span><span class="sxs-lookup"><span data-stu-id="cc13a-362">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="cc13a-363">默认情况下, 禁用邮箱审核具有以下结果:</span><span class="sxs-lookup"><span data-stu-id="cc13a-363">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="cc13a-364">对您的组织禁用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-364">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="cc13a-365">从您禁用邮箱审核时, 默认情况下不会审核任何邮箱操作, 即使在邮箱上启用了审核 (邮箱上的*AuditEnabled*属性为 True) 也是**如此**。</span><span class="sxs-lookup"><span data-stu-id="cc13a-365">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="cc13a-366">邮箱审核没有为新邮箱启用, 并将新邮箱或现有邮箱的*AuditEnabled*属性设置为**True**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cc13a-366">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="cc13a-367">任何邮箱审核绕过关联设置 (使用**get-mailboxauditbypassassociation** cmdlet 配置) 都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cc13a-367">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="cc13a-368">现有邮箱审核记录将一直保留, 直到记录的审核日志期限过期为止。</span><span class="sxs-lookup"><span data-stu-id="cc13a-368">Existing mailbox audit records are retained until the audit log age limit for the the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="cc13a-369">默认情况下启用邮箱审核</span><span class="sxs-lookup"><span data-stu-id="cc13a-369">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="cc13a-370">若要为您的组织重新启用邮箱审核, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-370">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="cc13a-371">绕过邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="cc13a-371">Bypass mailbox audit logging</span></span>

<span data-ttu-id="cc13a-372">目前, 在组织中启用默认邮箱审核时, 不能禁用特定邮箱的邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="cc13a-372">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="cc13a-373">例如, 将*AuditEnabled*邮箱属性设置为**False**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cc13a-373">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="cc13a-374">但是, 您仍可以使用 Exchange Online PowerShell 中的**get-mailboxauditbypassassociation** cmdlet 来阻止记录指定用户的*任何*邮箱操作, 而不考虑这些操作在何处发生。</span><span class="sxs-lookup"><span data-stu-id="cc13a-374">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="cc13a-375">例如：</span><span class="sxs-lookup"><span data-stu-id="cc13a-375">For example:</span></span>

- <span data-ttu-id="cc13a-376">不记录绕过用户执行的邮箱所有者操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-376">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="cc13a-377">委派由其他用户的邮箱 (包括共享邮箱) 执行的绕过用户执行的操作不会记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-377">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="cc13a-378">不会记录绕过用户执行的管理操作。</span><span class="sxs-lookup"><span data-stu-id="cc13a-378">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="cc13a-379">若要绕过特定用户的邮箱审核日志记录\<,\>请将 MailboxIdentity 替换为用户的名称、电子邮件地址、别名或用户主体名称 (用户名), 并运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-379">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="cc13a-380">若要验证是否对指定用户跳过审核, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="cc13a-380">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="cc13a-381">如果值**为 True** , 则表示对用户绕过邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-381">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="cc13a-382">更多信息</span><span class="sxs-lookup"><span data-stu-id="cc13a-382">More information</span></span>

- <span data-ttu-id="cc13a-383">默认情况下, 邮箱审核日志记录会在被删除前的90天后保留。</span><span class="sxs-lookup"><span data-stu-id="cc13a-383">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="cc13a-384">您可以使用 Exchange Online PowerShell 中的 "**设置邮箱**" cmdlet 上的*AuditLogAgeLimit*参数更改审核日志记录的期限。</span><span class="sxs-lookup"><span data-stu-id="cc13a-384">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="cc13a-385">但是, 增加此值不会允许您在 Microsoft 365 审核日志中搜索超过90天的事件。</span><span class="sxs-lookup"><span data-stu-id="cc13a-385">However, increasing this value doesn't allow you to search for events that are older than 90 days in the Microsoft 365 audit log.</span></span>

  <span data-ttu-id="cc13a-386">如果增加期限, 则需要使用 Exchange Online PowerShell 中的[search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet 在用户的邮箱审核日志中搜索早于90天的记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-386">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="cc13a-387">如果您已在邮箱审核之前对邮箱的*AuditLogAgeLimit*属性进行了更改, 则该邮箱的现有审核日志期限不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="cc13a-387">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="cc13a-388">换言之, 默认情况下邮箱审核不会影响邮箱审核记录的当前期限。</span><span class="sxs-lookup"><span data-stu-id="cc13a-388">In other words, mailbox auditing on by default doesn't effect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="cc13a-389">若要更改 Office 365 组邮箱上的*AuditLogAgeLimit*值, 需要将该`-GroupMailbox`开关包含在 "**设置邮箱**" 命令中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-389">To change the *AuditLogAgeLimit* value on an Office 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="cc13a-390">邮箱审核日志记录存储在每个用户邮箱的 "可恢复的项目" 文件夹中的子文件夹 (称为*审核*) 中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-390">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="cc13a-391">请记住以下有关邮箱审核记录和 "可恢复的项目" 文件夹的事项:</span><span class="sxs-lookup"><span data-stu-id="cc13a-391">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="cc13a-392">邮箱审核记录根据 "可恢复的项目" 文件夹的存储配额进行计数, 默认情况下 30GB (警告配额为 20 GB)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-392">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="cc13a-393">在以下情况时, 存储配额会自动增加到 100 GB (使用 90 GB 警告配额):</span><span class="sxs-lookup"><span data-stu-id="cc13a-393">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="cc13a-394">邮箱上放置了保留项。</span><span class="sxs-lookup"><span data-stu-id="cc13a-394">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="cc13a-395">将邮箱分配给合规中心中的保留策略。</span><span class="sxs-lookup"><span data-stu-id="cc13a-395">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="cc13a-396">邮箱审核记录也会对["可恢复的项目" 文件夹的文件夹限制进行](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)计数。</span><span class="sxs-lookup"><span data-stu-id="cc13a-396">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="cc13a-397">最多可以将3000000个项目 (审核记录) 存储在 "审核" 子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cc13a-397">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cc13a-398">邮箱默认情况下的审核不太可能会影响存储配额或 "可恢复的项目" 文件夹的文件夹限制。</span><span class="sxs-lookup"><span data-stu-id="cc13a-398">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="cc13a-399">您可以在 Exchange Online PowerShell 中运行以下命令, 以在 "可恢复的项目" 文件夹的 "审核" 子文件夹中显示项目的大小和数量:</span><span class="sxs-lookup"><span data-stu-id="cc13a-399">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="cc13a-400">您不能直接访问 "可恢复的项目" 文件夹中的审核日志记录;相反, 您可以使用**search-mailboxauditlog** cmdlet 或搜索 Microsoft 365 审核日志来查找和查看邮箱审核记录。</span><span class="sxs-lookup"><span data-stu-id="cc13a-400">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the Microsoft 365 audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="cc13a-401">如果将邮箱置于保留或分配到合规中心中的保留策略, 则在邮箱的*AuditLogAgeLimit*属性定义的持续时间内仍会保留审核日志记录 (默认情况下为90天)。</span><span class="sxs-lookup"><span data-stu-id="cc13a-401">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="cc13a-402">若要延长保留邮箱的审核日志记录, 您需要增加邮箱的*AuditLogAgeLimit*值。</span><span class="sxs-lookup"><span data-stu-id="cc13a-402">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>
