---
title: 管理邮箱审核
ms.author: chrisda
author: chrisda
manager: dansimp
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
description: 默认情况下, 邮箱审核日志记录在 Office 365 中处于打开状态 (也称为默认邮箱审核或邮箱审核, 默认情况下)。 这意味着邮箱所有者、代理人和管理员执行的某些操作将自动记录在邮箱审核日志中, 在此日志中可以搜索在邮箱上执行的活动。
ms.openlocfilehash: 049b9fe79ae3389e09fb07017fd2deb810640f35
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649907"
---
# <a name="manage-mailbox-auditing"></a><span data-ttu-id="71688-104">管理邮箱审核</span><span class="sxs-lookup"><span data-stu-id="71688-104">Manage mailbox auditing</span></span>

<span data-ttu-id="71688-105">从2019年1月起, Microsoft 将默认为所有 Office 365 组织启用邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="71688-105">Starting in January 2019, Microsoft is turning on mailbox audit logging by default for all Office 365 organizations.</span></span> <span data-ttu-id="71688-106">这意味着邮箱所有者、代理人和管理员执行的某些操作将会自动记录, 当您在邮箱审核日志中搜索时, 相应的邮箱审核记录将可用。</span><span class="sxs-lookup"><span data-stu-id="71688-106">This means that certain actions performed by mailbox owners, delegates, and admins are automatically logged, and the corresponding mailbox audit records will be available when you search for them in the mailbox audit log.</span></span> <span data-ttu-id="71688-107">默认情况下, 邮箱审核启用前, 您必须为组织中的每个用户邮箱手动启用它。</span><span class="sxs-lookup"><span data-stu-id="71688-107">Before mailbox auditing was turned on by default, you had to manually enable it for every user mailbox in your organization.</span></span>

<span data-ttu-id="71688-108">以下是邮箱审核在默认情况下的一些优点:</span><span class="sxs-lookup"><span data-stu-id="71688-108">Here are some benefits of mailbox auditing on by default:</span></span>

- <span data-ttu-id="71688-109">当您创建新邮箱时, 将自动启用审核。</span><span class="sxs-lookup"><span data-stu-id="71688-109">Auditing is automatically enabled when you create a new mailbox.</span></span> <span data-ttu-id="71688-110">您无需为新用户手动启用它。</span><span class="sxs-lookup"><span data-stu-id="71688-110">You don't need to manually enable it for new users.</span></span>

- <span data-ttu-id="71688-111">您无需管理已审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-111">You don't need to manage the mailbox actions that are audited.</span></span> <span data-ttu-id="71688-112">默认情况下, 会为每个登录类型 (管理员、代理和所有者) 审核一组预定义的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-112">A predefined set of mailbox actions are audited by default for each logon type (Admin, Delegate, and Owner).</span></span>

- <span data-ttu-id="71688-113">当 Microsoft 发布新邮箱操作 (尤其是帮助保护组织并帮助进行法庭调查的操作) 时, 会自动将该操作添加到默认情况下审核的邮箱操作列表中。</span><span class="sxs-lookup"><span data-stu-id="71688-113">When Microsoft releases a new mailbox action (particularly actions that help protect your organization and help with forensic investigations), the action is automatically added to the list of mailbox actions that are audited by default.</span></span> <span data-ttu-id="71688-114">这意味着您无需监视对邮箱添加的新操作。</span><span class="sxs-lookup"><span data-stu-id="71688-114">This means you don't need to monitor add new actions on mailboxes.</span></span>

- <span data-ttu-id="71688-115">您的组织中有一致的邮箱审核策略 (因为您正在审核对所有邮箱的相同操作)。</span><span class="sxs-lookup"><span data-stu-id="71688-115">You have a consistent mailbox auditing policy across your organization (because you're auditing the same actions for all mailboxes).</span></span>

> [!NOTE]
><span data-ttu-id="71688-116">•默认情况下, 有关邮箱审核发布的重要事项是: 不需要执行任何操作来管理邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="71688-116">• The important thing to remember about the release of mailbox auditing on by default is: you don't need to do anything to manage mailbox auditing.</span></span> <span data-ttu-id="71688-117">但是, 若要了解详细信息, 自定义邮箱审核的默认设置, 或将其全部关闭, 本主题可为你有所帮助。</span><span class="sxs-lookup"><span data-stu-id="71688-117">However, to learn more, customize mailbox auditing from the default settings, or turn it off altogether, this topic can help you.</span></span> <br><br><span data-ttu-id="71688-118">•在默认情况下启用邮箱审核时, 您可能会注意到, 在安全 & 合规性中心或通过 Office 365 管理活动 API 审核日志搜索中找不到某些用户的邮箱审核事件。</span><span class="sxs-lookup"><span data-stu-id="71688-118">• Even when mailbox auditing on by default is turned on, you might notice that mailbox audit events for some users aren't found in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span> <span data-ttu-id="71688-119">有关详细信息, 请参阅本主题中的[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="71688-119">For more information, see the [More information](#more-information) section in this topic.</span></span>

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a><span data-ttu-id="71688-120">默认情况下验证邮箱审核启用</span><span class="sxs-lookup"><span data-stu-id="71688-120">Verify mailbox auditing on by default is turned on</span></span>

<span data-ttu-id="71688-121">若要验证您的组织的默认邮箱审核是否已启用, 请在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-121">To verify that mailbox auditing on by default is turned on for your organization, run the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Get-OrganizationConfig | Format-List AuditDisabled
```

<span data-ttu-id="71688-122">值**为 False**表示对组织启用默认情况下邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="71688-122">The value **False** indicates that mailbox auditing on by default is enabled for the organization.</span></span> <span data-ttu-id="71688-123">默认情况下, 此设置将覆盖特定邮箱上的邮箱审核设置。</span><span class="sxs-lookup"><span data-stu-id="71688-123">This on by default organizational value overrides the mailbox auditing setting on specific mailboxes.</span></span> <span data-ttu-id="71688-124">例如, 如果对邮箱禁用了邮箱审核 (邮箱上的*AuditEnabled*属性为**False** ), 则仍将审核邮箱的默认邮箱操作, 因为默认情况下邮箱审核启用了组织.</span><span class="sxs-lookup"><span data-stu-id="71688-124">For example, if mailbox auditing is disabled for a mailbox (the *AuditEnabled* property is **False** on the mailbox), the default mailbox actions will still be audited for the mailbox, because mailbox auditing on by default is enabled for the organization.</span></span>

<span data-ttu-id="71688-125">若要将特定邮箱的邮箱审核功能保持为禁用状态, 请为邮箱所有者和已委派邮箱访问权限的其他用户配置邮箱审核旁路。</span><span class="sxs-lookup"><span data-stu-id="71688-125">To keep mailbox auditing disabled for specific mailboxes, you configure mailbox auditing bypass for the mailbox owner and other users who have been delegated access to the mailbox.</span></span> <span data-ttu-id="71688-126">有关详细信息, 请参阅本主题中的[绕过邮箱审核日志记录](#bypass-mailbox-audit-logging)一节。</span><span class="sxs-lookup"><span data-stu-id="71688-126">For more information, see the [Bypass mailbox audit logging](#bypass-mailbox-audit-logging) section in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="71688-127">如果为组织启用了默认情况下的邮箱审核, 则受影响的邮箱的*AuditEnabled*属性不会从**False**更改为**True**。</span><span class="sxs-lookup"><span data-stu-id="71688-127">When mailbox auditing on by default is turned on for the organization, the *AuditEnabled* property for affected mailboxes won't be changed from **False** to **True**.</span></span> <span data-ttu-id="71688-128">换言之, 默认情况下邮箱审核将忽略邮箱上的*AuditEnabled*属性。</span><span class="sxs-lookup"><span data-stu-id="71688-128">In other words, mailbox auditing on by default ignores the *AuditEnabled* property on mailboxes.</span></span>

## <a name="supported-mailbox-types"></a><span data-ttu-id="71688-129">支持的邮箱类型</span><span class="sxs-lookup"><span data-stu-id="71688-129">Supported mailbox types</span></span>

<span data-ttu-id="71688-130">下表显示了默认情况下邮箱审核当前支持的邮箱类型:</span><span class="sxs-lookup"><span data-stu-id="71688-130">The following table shows the mailbox types that are currently supported by mailbox auditing on by default:</span></span>

|<span data-ttu-id="71688-131">**邮箱类型**</span><span class="sxs-lookup"><span data-stu-id="71688-131">**Mailbox type**</span></span>|<span data-ttu-id="71688-132">**支持**</span><span class="sxs-lookup"><span data-stu-id="71688-132">**Supported**</span></span>|<span data-ttu-id="71688-133">**不支持**</span><span class="sxs-lookup"><span data-stu-id="71688-133">**Not supported**</span></span>|
|:---------|:---------:|:---------:|
|<span data-ttu-id="71688-134">用户邮箱</span><span class="sxs-lookup"><span data-stu-id="71688-134">User mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="71688-136">共享邮箱</span><span class="sxs-lookup"><span data-stu-id="71688-136">Shared mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="71688-138">Office 365 组邮箱</span><span class="sxs-lookup"><span data-stu-id="71688-138">Office 365 Group mailboxes</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="71688-140">资源邮箱</span><span class="sxs-lookup"><span data-stu-id="71688-140">Resource mailboxes</span></span>||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-142">公用文件夹邮箱</span><span class="sxs-lookup"><span data-stu-id="71688-142">Public folder mailboxes</span></span>||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a><span data-ttu-id="71688-144">登录类型和邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-144">Logon types and mailbox actions</span></span>

<span data-ttu-id="71688-145">登录类型对对邮箱执行了审核操作的用户进行分类。</span><span class="sxs-lookup"><span data-stu-id="71688-145">Logon types classify the user that did the audited actions on the mailbox.</span></span> <span data-ttu-id="71688-146">以下列表介绍了邮箱审核日志记录中使用的登录类型:</span><span class="sxs-lookup"><span data-stu-id="71688-146">The following list describes the logon types that are used in mailbox audit logging:</span></span>

- <span data-ttu-id="71688-147">**Owner**: 邮箱所有者 (与邮箱关联的帐户)。</span><span class="sxs-lookup"><span data-stu-id="71688-147">**Owner**: The mailbox owner (the account that's associated with the mailbox).</span></span>

- <span data-ttu-id="71688-148">**委派**:</span><span class="sxs-lookup"><span data-stu-id="71688-148">**Delegate**:</span></span>

  - <span data-ttu-id="71688-149">向另一个邮箱分配了 SendAs、SendOnBehalf 或 FullAccess 权限的用户。</span><span class="sxs-lookup"><span data-stu-id="71688-149">A user who's been assigned the SendAs, SendOnBehalf, or FullAccess permission to another mailbox.</span></span>

  - <span data-ttu-id="71688-150">为用户的邮箱分配了 FullAccess 权限的管理员。</span><span class="sxs-lookup"><span data-stu-id="71688-150">An admin who's been assigned the FullAccess permission to a user's mailbox.</span></span>

- <span data-ttu-id="71688-151">**管理员**:</span><span class="sxs-lookup"><span data-stu-id="71688-151">**Admin**:</span></span>

  - <span data-ttu-id="71688-152">使用以下其中一种 Microsoft 电子数据展示工具搜索邮箱:</span><span class="sxs-lookup"><span data-stu-id="71688-152">The mailbox is searched with one of the following Microsoft eDiscovery tools:</span></span>

    - <span data-ttu-id="71688-153">合规性中心中的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="71688-153">Content Search in the Compliance center.</span></span>

    - <span data-ttu-id="71688-154">合规中心中的电子数据展示或高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="71688-154">eDiscovery or Advanced eDiscovery in the Compliance center.</span></span>

    - <span data-ttu-id="71688-155">Exchange Online 中的就地电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="71688-155">In-Place eDiscovery in Exchange Online.</span></span>

  - <span data-ttu-id="71688-156">可以使用[Microsoft Exchange SERVER MAPI 编辑器](https://go.microsoft.com/fwlink/p/?linkId=204086)访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="71688-156">The mailbox is accessed by using the [Microsoft Exchange Server MAPI Editor](https://go.microsoft.com/fwlink/p/?linkId=204086).</span></span>

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a><span data-ttu-id="71688-157">用户邮箱和共享邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-157">Mailbox actions for user mailboxes and shared mailboxes</span></span>

<span data-ttu-id="71688-158">下表介绍了可用于用户邮箱和共享邮箱的邮箱审核日志记录中的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-158">The following table describes the mailbox actions that are available in mailbox audit logging for user mailboxes and shared mailboxes.</span></span>

- <span data-ttu-id="71688-159">一个复选标记 (</span><span class="sxs-lookup"><span data-stu-id="71688-159">A check mark (</span></span> ![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<span data-ttu-id="71688-161">) 表示可以为登录类型记录邮箱操作 (并非所有操作都适用于所有登录类型)。</span><span class="sxs-lookup"><span data-stu-id="71688-161">) indicates the mailbox action can be logged for the logon type (not all actions are available for all logon types).</span></span>

- <span data-ttu-id="71688-162">在复选标记<sup>\*</sup>后面有一个星号 () 表示邮箱操作在默认情况下会记录在登录类型中。</span><span class="sxs-lookup"><span data-stu-id="71688-162">An asterisk ( <sup>\*</sup> ) after the check mark indicates the mailbox action is logged by default for the logon type.</span></span>

- <span data-ttu-id="71688-163">请记住, 对邮箱具有完全访问权限的管理员被视为代理。</span><span class="sxs-lookup"><span data-stu-id="71688-163">Remember, an admin with Full Access permission to a mailbox is considered a delegate.</span></span>

|<span data-ttu-id="71688-164">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="71688-164">**Mailbox action**</span></span>|<span data-ttu-id="71688-165">**说明**</span><span class="sxs-lookup"><span data-stu-id="71688-165">**Description**</span></span>|<span data-ttu-id="71688-166">**管理员**</span><span class="sxs-lookup"><span data-stu-id="71688-166">**Admin**</span></span>|<span data-ttu-id="71688-167">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="71688-167">**Delegate**</span></span>|<span data-ttu-id="71688-168">**所有者**</span><span class="sxs-lookup"><span data-stu-id="71688-168">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="71688-169">**AddFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="71688-169">**AddFolderPermissions**</span></span>|<span data-ttu-id="71688-170">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="71688-170">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="71688-171">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="71688-171">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="71688-172">**ApplyRecord**</span><span class="sxs-lookup"><span data-stu-id="71688-172">**ApplyRecord**</span></span>|<span data-ttu-id="71688-173">项目标记为记录。</span><span class="sxs-lookup"><span data-stu-id="71688-173">An item is labeled as a record.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-177">**复制**</span><span class="sxs-lookup"><span data-stu-id="71688-177">**Copy**</span></span>|<span data-ttu-id="71688-178">已将某个邮件复制到另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="71688-178">A message was copied to another folder.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="71688-180">**创建**</span><span class="sxs-lookup"><span data-stu-id="71688-180">**Create**</span></span>|<span data-ttu-id="71688-181">在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建了一个项目 (例如, 创建了一个新的会议请求)。</span><span class="sxs-lookup"><span data-stu-id="71688-181">An item was created in the Calendar, Contacts, Notes, or Tasks folder in the mailbox (for example, a new meeting request is created).</span></span> <span data-ttu-id="71688-182">请注意, 不会审核创建、发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-182">Note that creating, sending, or receiving a message isn't audited.</span></span> <span data-ttu-id="71688-183">此外, 还不会审核创建邮箱文件夹的情况。</span><span class="sxs-lookup"><span data-stu-id="71688-183">Also, creating a mailbox folder is not audited.</span></span>|<span data-ttu-id="71688-184">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-184">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-185">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-185">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-187">**FolderBind**</span><span class="sxs-lookup"><span data-stu-id="71688-187">**FolderBind**</span></span>|<span data-ttu-id="71688-188">已访问某个邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="71688-188">A mailbox folder was accessed.</span></span> <span data-ttu-id="71688-189">当管理员或委派打开邮箱时, 也会记录此操作。</span><span class="sxs-lookup"><span data-stu-id="71688-189">This action is also logged when the admin or delegate opens the mailbox.</span></span> <br/><br/> <span data-ttu-id="71688-190">**注意**: 代理执行的文件夹绑定操作的审核记录已合并。</span><span class="sxs-lookup"><span data-stu-id="71688-190">**Note**: Audit records for folder bind actions performed by delegates are consolidated.</span></span> <span data-ttu-id="71688-191">在24小时内为单个文件夹访问生成一个审核记录。</span><span class="sxs-lookup"><span data-stu-id="71688-191">One audit record is generated for individual folder access within 24 hour period.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|<span data-ttu-id="71688-194">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="71688-194">**HardDelete**</span></span>|<span data-ttu-id="71688-195">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="71688-195">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="71688-196">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-196">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-197">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-197">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-198">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-198">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-199">**Mailboxlogin 该值**</span><span class="sxs-lookup"><span data-stu-id="71688-199">**MailboxLogin**</span></span>|<span data-ttu-id="71688-200">用户已登录到其邮箱。</span><span class="sxs-lookup"><span data-stu-id="71688-200">The user signed into their mailbox.</span></span> |||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-202">**MessageBind**</span><span class="sxs-lookup"><span data-stu-id="71688-202">**MessageBind**</span></span>|<span data-ttu-id="71688-203">在预览窗格查看邮件或打开邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-203">A message was viewed in the preview pane or opened.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|<span data-ttu-id="71688-205">**ModifyFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="71688-205">**ModifyFolderPermissions**</span></span>|<span data-ttu-id="71688-206">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="71688-206">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="71688-207">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="71688-207">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="71688-208">**移动**</span><span class="sxs-lookup"><span data-stu-id="71688-208">**Move**</span></span>|<span data-ttu-id="71688-209">已将某个邮件移至另一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="71688-209">A message was moved to another folder.</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-213">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="71688-213">**MoveToDeletedItems**</span></span>|<span data-ttu-id="71688-214">邮件已被删除并移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="71688-214">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="71688-215">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-215">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-216">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-216">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-217">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-217">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-218">**RecordDelete**</span><span class="sxs-lookup"><span data-stu-id="71688-218">**RecordDelete**</span></span>|<span data-ttu-id="71688-219">标记为记录的项目已软删除 (移动到 "可恢复的项目" 文件夹)。</span><span class="sxs-lookup"><span data-stu-id="71688-219">An item that's labeled as a record was soft-deleted (moved to the Recoverable Items folder).</span></span> <span data-ttu-id="71688-220">标记为记录的项目无法永久删除 (从 "可恢复的项目" 文件夹中清除)。</span><span class="sxs-lookup"><span data-stu-id="71688-220">Items labeled as records can't be permanently deleted (purged from the Recoverable Items folder).</span></span>|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="71688-224">**RemoveFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="71688-224">**RemoveFolderPermissions**</span></span>|<span data-ttu-id="71688-225">**注意**: 虽然此值被接受为邮箱操作, 但它已包含在**UpdateFolderPermissions**操作中, 并且不会单独审核。</span><span class="sxs-lookup"><span data-stu-id="71688-225">**Note**: Although this value is accepted as a mailbox action, it's already included in the **UpdateFolderPermissions** action and isn't audited separately.</span></span> <span data-ttu-id="71688-226">换言之, 请勿使用此值。</span><span class="sxs-lookup"><span data-stu-id="71688-226">In other words, don't use this value.</span></span>||||
|<span data-ttu-id="71688-227">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="71688-227">**SendAs**</span></span>|<span data-ttu-id="71688-228">邮件是使用 SendAs 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="71688-228">A message was sent using the SendAs permission.</span></span> <span data-ttu-id="71688-229">这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。</span><span class="sxs-lookup"><span data-stu-id="71688-229">This means another user sent the message as though it came from the mailbox owner.</span></span>|<span data-ttu-id="71688-230">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-230">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-231">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-231">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="71688-232">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="71688-232">**SendOnBehalf**</span></span>|<span data-ttu-id="71688-233">邮件是使用 SendOnBehalf 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="71688-233">A message was sent using the SendOnBehalf permission.</span></span> <span data-ttu-id="71688-234">这表示另一个用户代表邮箱所有者发送了邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-234">This means another user sent the message on behalf of the mailbox owner.</span></span> <span data-ttu-id="71688-235">该邮件指示收件人代表发送邮件的收件人和实际发送邮件的收件人。</span><span class="sxs-lookup"><span data-stu-id="71688-235">The message indicates to the recipient who the message was sent on behalf of and who actually sent the message.</span></span>|<span data-ttu-id="71688-236">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-236">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-237">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-237">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="71688-238">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="71688-238">**SoftDelete**</span></span>|<span data-ttu-id="71688-239">邮件已从 "已删除邮件" 文件夹中永久删除或删除。</span><span class="sxs-lookup"><span data-stu-id="71688-239">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="71688-240">软删除的项目将移动到 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71688-240">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="71688-241">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-241">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-242">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-242">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-243">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-243">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-244">**更新**</span><span class="sxs-lookup"><span data-stu-id="71688-244">**Update**</span></span>|<span data-ttu-id="71688-245">更改了邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="71688-245">A message or its properties was changed.</span></span>|<span data-ttu-id="71688-246">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-246">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-247">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-247">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-248">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-248">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-249">**UpdateCalendarDelegation**</span><span class="sxs-lookup"><span data-stu-id="71688-249">**UpdateCalendarDelegation**</span></span>|<span data-ttu-id="71688-250">向邮箱分配了日历委派。</span><span class="sxs-lookup"><span data-stu-id="71688-250">A calendar delegation was assigned to a mailbox.</span></span> <span data-ttu-id="71688-251">日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。</span><span class="sxs-lookup"><span data-stu-id="71688-251">Calendar delegation gives someone else in the same organization permissions to manage the mailbox owner's calendar.</span></span>|<span data-ttu-id="71688-252">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-252">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||<span data-ttu-id="71688-253">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-253">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-254">**UpdateFolderPermissions**</span><span class="sxs-lookup"><span data-stu-id="71688-254">**UpdateFolderPermissions**</span></span>|<span data-ttu-id="71688-255">更改了文件夹权限。</span><span class="sxs-lookup"><span data-stu-id="71688-255">A folder permission was changed.</span></span> <span data-ttu-id="71688-256">文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-256">Folder permissions control which users in your organization can access folders in a mailbox and the messages located in those folders.</span></span>|<span data-ttu-id="71688-257">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-257">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-258">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-258">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-259">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-259">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-260">**UpdateInboxRules**</span><span class="sxs-lookup"><span data-stu-id="71688-260">**UpdateInboxRules**</span></span>|<span data-ttu-id="71688-261">添加、删除或更改了收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="71688-261">An inbox rule was added, removed, or changed.</span></span> <span data-ttu-id="71688-262">"收件箱" 规则用于根据指定的条件处理用户收件箱中的邮件, 并在满足规则条件时采取操作, 例如将邮件移动到指定文件夹或删除邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-262">Inbox rules are used to process messages in the user's Inbox based on the specified conditions and take actions when the conditions of a rule are met, such as moving a message to a specified folder or deleting a message.</span></span>|<span data-ttu-id="71688-263">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-263">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-264">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-264">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-265">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-265">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

> [!IMPORTANT]
> <span data-ttu-id="71688-266">如果您在组织中对邮箱操作进行自定义, 以便在默认情况下在邮箱审核启用*前*对任何登录类型进行审核, 则这些自定义设置将保留在邮箱中, 且不会被默认邮箱操作覆盖为本节中所述。</span><span class="sxs-lookup"><span data-stu-id="71688-266">If you customized the mailbox actions to audit for any logon type *before* mailbox auditing on by default was enabled in your organization, the customized settings are preserved on the mailbox and aren't overwritten by the default mailbox actions as described in this section.</span></span> <span data-ttu-id="71688-267">若要将审核邮箱操作还原为其默认值 (可在任何时候执行), 请参阅本主题后面的[还原默认邮箱操作](#restore-the-default-mailbox-actions)部分。</span><span class="sxs-lookup"><span data-stu-id="71688-267">To revert the audit mailbox actions to their default values (which you can do at any time), see the [Restore the default mailbox actions](#restore-the-default-mailbox-actions) section later in this topic.</span></span>

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a><span data-ttu-id="71688-268">适用于 Office 365 组邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-268">Mailbox actions for Office 365 Group mailboxes</span></span>

<span data-ttu-id="71688-269">默认情况下的邮箱审核会将邮箱审核日志记录提供给 Office 365 组邮箱, 但不能自定义要记录的内容 (您无法添加或删除为任何登录类型记录的邮箱操作)。</span><span class="sxs-lookup"><span data-stu-id="71688-269">Mailbox auditing on by default brings mailbox audit logging to Office 365 Group mailboxes, but you can't customize what's being logged (you can't add or remove mailbox actions that are logged for any logon type).</span></span>

<span data-ttu-id="71688-270">下表介绍了默认情况下在每个登录类型的 Office 365 组邮箱上记录的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-270">The following table describes the mailbox actions that are logged by default on Office 365 Group mailboxes for each logon type.</span></span>

<span data-ttu-id="71688-271">请记住, 对 Office 365 组邮箱具有完全访问权限的管理员被视为代理。</span><span class="sxs-lookup"><span data-stu-id="71688-271">Remember, an admin with Full Access permission to an Office 365 Group mailbox is considered a delegate.</span></span>

|<span data-ttu-id="71688-272">**邮箱操作**</span><span class="sxs-lookup"><span data-stu-id="71688-272">**Mailbox action**</span></span>|<span data-ttu-id="71688-273">**说明**</span><span class="sxs-lookup"><span data-stu-id="71688-273">**Description**</span></span>|<span data-ttu-id="71688-274">**管理员**</span><span class="sxs-lookup"><span data-stu-id="71688-274">**Admin**</span></span>|<span data-ttu-id="71688-275">**委派用户**</span><span class="sxs-lookup"><span data-stu-id="71688-275">**Delegate**</span></span>|<span data-ttu-id="71688-276">**所有者**</span><span class="sxs-lookup"><span data-stu-id="71688-276">**Owner**</span></span>|
|:---------|:---------|:---------:|:---------:|:---------:|
|<span data-ttu-id="71688-277">**创建**</span><span class="sxs-lookup"><span data-stu-id="71688-277">**Create**</span></span>|<span data-ttu-id="71688-278">创建日历项目。</span><span class="sxs-lookup"><span data-stu-id="71688-278">Creation of a calendar Item.</span></span> <span data-ttu-id="71688-279">请注意, 不会审核创建、发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="71688-279">Note that creating, sending, or receiving a message isn't audited.</span></span>|<span data-ttu-id="71688-280">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-280">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-281">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-281">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="71688-282">**HardDelete**</span><span class="sxs-lookup"><span data-stu-id="71688-282">**HardDelete**</span></span>|<span data-ttu-id="71688-283">已将某个邮件从"已恢复邮件"文件夹中清除。</span><span class="sxs-lookup"><span data-stu-id="71688-283">A message was purged from the Recoverable Items folder.</span></span>|<span data-ttu-id="71688-284">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-284">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-285">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-285">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-286">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-286">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-287">**MoveToDeletedItems**</span><span class="sxs-lookup"><span data-stu-id="71688-287">**MoveToDeletedItems**</span></span>|<span data-ttu-id="71688-288">邮件已被删除并移动到 "已删除邮件" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="71688-288">A message was deleted and moved to the Deleted Items folder.</span></span>|<span data-ttu-id="71688-289">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-289">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-290">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-290">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-291">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-291">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-292">**SendAs**</span><span class="sxs-lookup"><span data-stu-id="71688-292">**SendAs**</span></span>|<span data-ttu-id="71688-293">邮件是使用 SendAs 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="71688-293">A message was sent using the SendAs permission.</span></span>|<span data-ttu-id="71688-294">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-294">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-295">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-295">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="71688-296">**SendOnBehalf**</span><span class="sxs-lookup"><span data-stu-id="71688-296">**SendOnBehalf**</span></span>|<span data-ttu-id="71688-297">邮件是使用 SendOnBehalf 权限发送的。</span><span class="sxs-lookup"><span data-stu-id="71688-297">A message was sent using the SendOnBehalf permission.</span></span> |<span data-ttu-id="71688-298">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-298">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-299">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-299">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>||
|<span data-ttu-id="71688-300">**SoftDelete**</span><span class="sxs-lookup"><span data-stu-id="71688-300">**SoftDelete**</span></span>|<span data-ttu-id="71688-301">邮件已从 "已删除邮件" 文件夹中永久删除或删除。</span><span class="sxs-lookup"><span data-stu-id="71688-301">A message was permanently deleted or deleted from the Deleted Items folder.</span></span> <span data-ttu-id="71688-302">软删除的项目将移动到 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71688-302">Soft-deleted items are moved to the Recoverable Items folder.</span></span>|<span data-ttu-id="71688-303">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-303">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-304">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-304">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-305">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-305">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|
|<span data-ttu-id="71688-306">**更新**</span><span class="sxs-lookup"><span data-stu-id="71688-306">**Update**</span></span>|<span data-ttu-id="71688-307">更改了邮件或其属性。</span><span class="sxs-lookup"><span data-stu-id="71688-307">A message or its properties was changed.</span></span>|<span data-ttu-id="71688-308">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-308">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-309">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-309">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|<span data-ttu-id="71688-310">![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71688-310">![Check mark](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup></span></span>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a><span data-ttu-id="71688-311">验证是否为每个登录类型记录了默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-311">Verify that default mailbox actions are being logged for each logon type</span></span>

<span data-ttu-id="71688-312">默认情况之下的邮箱审核将新的*DefaultAuditSet*属性添加到所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="71688-312">Mailbox auditing on by defaults adds a new *DefaultAuditSet* property to all mailboxes.</span></span> <span data-ttu-id="71688-313">此属性的值指示是否在邮箱上审核默认邮箱操作 (由 Microsoft 管理)。</span><span class="sxs-lookup"><span data-stu-id="71688-313">The value of this property indicates whether the default mailbox actions (managed by Microsoft) are being audited on the mailbox.</span></span>

<span data-ttu-id="71688-314">若要在用户邮箱或共享邮箱上显示值, \<请\>将 MailboxIdentity 替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名), 并在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-314">To display the value on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

<span data-ttu-id="71688-315">若要在 Office 365 组邮箱中显示值, \<请\>将 MailboxIdentity 替换为共享邮箱的名称、别名或电子邮件地址, 并在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-315">To display the value on Office 365 group mailboxes, replace \<MailboxIdentity\> with the name, alias, or email address of the shared mailbox and run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

<span data-ttu-id="71688-316">该值`Admin, Delegate, Owner`指示:</span><span class="sxs-lookup"><span data-stu-id="71688-316">The value `Admin, Delegate, Owner` indicates:</span></span>

- <span data-ttu-id="71688-317">审核所有三种登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-317">The default mailbox actions for all three logon types are being audited.</span></span> <span data-ttu-id="71688-318">请注意, 这是你将在 Office 365 组邮箱中看到的唯一值。</span><span class="sxs-lookup"><span data-stu-id="71688-318">Note that this is the only value you'll see on Office 365 Group mailboxes.</span></span>

- <span data-ttu-id="71688-319">管理员尚未\*\* 更改用户邮箱或共享邮箱上任何登录类型的已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-319">An admin *has not* changed the audited mailbox actions for any logon type on a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="71688-320">注释默认情况下, 这是在组织中最初启用邮箱审核之后的默认状态。</span><span class="sxs-lookup"><span data-stu-id="71688-320">Note this is the default state after mailbox auditing on by default is initially turned on in your organization.</span></span>

<span data-ttu-id="71688-321">如果管理员曾更改过为登录类型审核的邮箱操作 (通过使用**设置邮箱**cmdlet 上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数), 则该属性值将有所不同。</span><span class="sxs-lookup"><span data-stu-id="71688-321">If an admin has ever changed the mailbox actions that are audited for a logon type (by using the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet), the property value will be different.</span></span>

<span data-ttu-id="71688-322">例如, 用户邮箱或`Owner`共享邮箱上的*DefaultAuditSet*属性的值表示:</span><span class="sxs-lookup"><span data-stu-id="71688-322">For example, the value `Owner` for the *DefaultAuditSet* property on a user mailbox or shared mailbox indicates:</span></span>

- <span data-ttu-id="71688-323">审核邮箱所有者的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-323">The default mailbox actions for the mailbox owner are being audited.</span></span>

- <span data-ttu-id="71688-324">已从默认操作更改了`Delegate`和`Admin`登录类型的已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-324">The audited mailbox actions for the `Delegate` and `Admin` logon types have been changed from the default actions.</span></span>

<span data-ttu-id="71688-325">*DefaultAuditSet*属性的空值表示已在用户邮箱或共享邮箱上更改了所有三种登录类型的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-325">A blank value for the *DefaultAuditSet* property indicates the mailbox actions for all three logon types have been changed on the user mailbox or a shared mailbox.</span></span>

<span data-ttu-id="71688-326">有关详细信息, 请参阅本主题中的 "[更改或还原在默认情况下记录的邮箱操作](#change-or-restore-mailbox-actions-logged-by-default)" 部分</span><span class="sxs-lookup"><span data-stu-id="71688-326">For more information, see the [Change or restore mailbox actions logged by default](#change-or-restore-mailbox-actions-logged-by-default) section in this topic</span></span>

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a><span data-ttu-id="71688-327">显示正在登录邮箱的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-327">Display the mailbox actions that are being logged on mailboxes</span></span>

<span data-ttu-id="71688-328">若要查看当前登录用户邮箱或共享邮箱的邮箱操作, 请将 MailboxIdentity \<\>替换为邮箱的名称、别名、电子邮件地址或用户主体名称 (用户名), 并运行以下一个或多个Exchange Online PowerShell 中的命令。</span><span class="sxs-lookup"><span data-stu-id="71688-328">To see the mailbox actions that are currently being logged on user mailboxes or shared mailboxes, replace \<MailboxIdentity\> with the name, alias, email address, or user principal name (username) of the mailbox, and run one or more of the following commands in Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="71688-329">虽然您可以将此`-GroupMailbox`开关添加到 Office 365 组邮箱的以下**Get 邮箱**命令中, 但不相信您看到的值。</span><span class="sxs-lookup"><span data-stu-id="71688-329">Although you can add the `-GroupMailbox` switch to the following **Get-Mailbox** commands for Office 365 Group mailboxes, don't believe the values you see.</span></span> <span data-ttu-id="71688-330">本主题前面的 " [office 365 组邮箱的邮箱操作](#mailbox-actions-for-office-365-group-mailboxes)" 一节中介绍了为 Office 365 组邮箱审核的默认和静态邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-330">The default and static mailbox actions that are audited for Office 365 Group mailboxes are described in the [Mailbox actions for Office 365 Group mailboxes](#mailbox-actions-for-office-365-group-mailboxes) section earlier in this topic.</span></span>

#### <a name="owner-actions"></a><span data-ttu-id="71688-331">所有者操作</span><span class="sxs-lookup"><span data-stu-id="71688-331">Owner actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a><span data-ttu-id="71688-332">委派操作</span><span class="sxs-lookup"><span data-stu-id="71688-332">Delegate actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a><span data-ttu-id="71688-333">管理操作</span><span class="sxs-lookup"><span data-stu-id="71688-333">Admin actions</span></span>

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a><span data-ttu-id="71688-334">更改或还原默认情况下记录的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-334">Change or restore mailbox actions logged by default</span></span>

<span data-ttu-id="71688-335">如前所述, 默认情况下启用邮箱审核的主要好处之一是: 无需管理已审核的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-335">As previously explained, one of the key benefits of having mailbox auditing on by default is: you don't need to manage the mailboxes actions that are audited.</span></span> <span data-ttu-id="71688-336">Microsoft 为你执行此操作, 我们将在默认情况下自动添加要审核的新邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-336">Microsoft does this for you and we'll automatically add new mailbox actions to be audited by default as they're released.</span></span>

<span data-ttu-id="71688-337">但是, 您的组织可能需要审核用户邮箱和共享邮箱的一组不同的邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-337">However, your organization might be required to audit a different set of mailbox actions for user mailboxes and shared mailboxes.</span></span> <span data-ttu-id="71688-338">本部分中的过程介绍如何更改针对每种登录类型进行审核的邮箱操作, 以及如何还原为 Microsoft 托管的默认操作。</span><span class="sxs-lookup"><span data-stu-id="71688-338">The procedures in this section show you how to change the mailbox actions that are audited for each logon type, and how to revert back to the Microsoft-managed default actions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71688-339">如果使用以下过程自定义登录用户邮箱或共享邮箱的邮箱操作, 则任何由 Microsoft 发布的新默认邮箱操作都不会在这些邮箱上自动进行审核。</span><span class="sxs-lookup"><span data-stu-id="71688-339">If you use the following procedures to customize the mailbox actions that are logged on user mailboxes or shared mailboxes, any new default mailbox actions released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="71688-340">您需要将任何新邮箱操作手动添加到自定义的操作列表中。</span><span class="sxs-lookup"><span data-stu-id="71688-340">You'll need to manually add any new mailbox actions to your customized list of actions.</span></span>

### <a name="change-the-mailbox-actions-to-audit"></a><span data-ttu-id="71688-341">更改要审核的邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-341">Change the mailbox actions to audit</span></span>

<span data-ttu-id="71688-342">您可以使用**设置邮箱**cmdlet 上的*AuditAdmin*、 *AuditDelegate*或*AuditOwner*参数更改为用户邮箱和共享邮箱审核的邮箱操作 (针对 Office 365 组的已审核操作无法自定义邮箱。</span><span class="sxs-lookup"><span data-stu-id="71688-342">You can use the *AuditAdmin*, *AuditDelegate*, or *AuditOwner* parameters on the **Set-Mailbox** cmdlet to change the mailbox actions that are audited for user mailboxes and shared mailboxes (audited actions for Office 365 group mailboxes can't be customized).</span></span>

<span data-ttu-id="71688-343">您可以使用两种不同的方法来指定邮箱操作:</span><span class="sxs-lookup"><span data-stu-id="71688-343">You can use two different methods to specify the mailbox actions:</span></span>

- <span data-ttu-id="71688-344">*Replace*(使用以下语法来覆盖) 现有邮箱操作: `action1,action2,...actionN`。</span><span class="sxs-lookup"><span data-stu-id="71688-344">*Replace* (overwrite) the existing mailbox actions by using this syntax: `action1,action2,...actionN`.</span></span>

- <span data-ttu-id="71688-345">使用以下语法在不影响其他现有值的情况下*添加或删除*邮箱操作: `@{Add="action1","action2",..."actionN"}`或`@{Remove="action1","action2",..."actionN"}`。</span><span class="sxs-lookup"><span data-stu-id="71688-345">*Add or remove* mailbox actions without affecting other existing values by using this syntax: `@{Add="action1","action2",..."actionN"}` or `@{Remove="action1","action2",..."actionN"}`.</span></span>

<span data-ttu-id="71688-346">此示例通过使用 SoftDelete 和 HardDelete 覆盖默认操作来更改名为 "Gabriela Laureano" 的邮箱的管理员邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-346">This example changes the admin mailbox actions for the mailbox named "Gabriela Laureano" by overwriting the default actions with SoftDelete and HardDelete.</span></span>

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

<span data-ttu-id="71688-347">本示例将 Mailboxlogin 该值 owner 操作添加到邮箱 laura@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="71688-347">This example adds the MailboxLogin owner action to the mailbox laura@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

<span data-ttu-id="71688-348">本示例删除工作组讨论邮箱的 MoveToDeletedItems 委派操作。</span><span class="sxs-lookup"><span data-stu-id="71688-348">This example removes the MoveToDeletedItems delegate action for the Team Discussion mailbox.</span></span>

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

<span data-ttu-id="71688-349">无论使用哪种方法, 自定义对用户邮箱或共享邮箱的审核邮箱操作都有以下结果:</span><span class="sxs-lookup"><span data-stu-id="71688-349">Regardless of the method you use, customizing the audited mailbox actions on user mailboxes or shared mailboxes has the following results:</span></span>

- <span data-ttu-id="71688-350">对于您自定义的登录类型, 已审核的邮箱操作不再由 Microsoft 进行管理。</span><span class="sxs-lookup"><span data-stu-id="71688-350">For the logon type that you customized, the audited mailbox actions are no longer managed by Microsoft.</span></span>

- <span data-ttu-id="71688-351">您自定义的登录类型不再像[前面所述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)的那样显示在邮箱的*DefaultAuditSet*属性值中。</span><span class="sxs-lookup"><span data-stu-id="71688-351">The logon type that you customized is no longer displayed in the *DefaultAuditSet* property value for the mailbox as [previously described](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type).</span></span>

### <a name="restore-the-default-mailbox-actions"></a><span data-ttu-id="71688-352">还原默认邮箱操作</span><span class="sxs-lookup"><span data-stu-id="71688-352">Restore the default mailbox actions</span></span>

<span data-ttu-id="71688-353">如果自定义了在用户邮箱或共享邮箱上审核的邮箱操作, 则可以使用以下语法还原一种或多种登录类型的默认邮箱操作:</span><span class="sxs-lookup"><span data-stu-id="71688-353">If you customized the mailbox actions that are audited on a user mailbox or a shared mailbox, you can restore the default mailbox actions for one or all logon types by using this syntax:</span></span>

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

<span data-ttu-id="71688-354">可以指定用逗号分隔的多个*DefaultAuditSet*值</span><span class="sxs-lookup"><span data-stu-id="71688-354">You can specify multiple *DefaultAuditSet* values separated by commas</span></span>

<span data-ttu-id="71688-355">**注意**: 以下过程不适用于 Office 365 组邮箱 (仅限于[此处](#mailbox-actions-for-office-365-group-mailboxes)所述的默认操作)。</span><span class="sxs-lookup"><span data-stu-id="71688-355">**Note**: The following procedures don't apply to Office 365 Group mailboxes (they're limited to the default actions as described [here](#mailbox-actions-for-office-365-group-mailboxes)).</span></span>

<span data-ttu-id="71688-356">本示例将还原邮箱 mark@contoso.onmicrosoft.com 上所有登录类型的默认审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-356">This example restores the default audited mailbox actions for all logon types on the mailbox mark@contoso.onmicrosoft.com.</span></span>

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

<span data-ttu-id="71688-357">本示例将还原邮箱 chris@contoso.onmicrosoft.com 上的管理员登录类型的默认审核邮箱操作, 但保留代理和所有者登录类型的自定义已审核邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-357">This example restores the default audited mailbox actions for the Admin logon type on the mailbox chris@contoso.onmicrosoft.com, but leaves the customized audited mailbox actions for the Delegate and Owner logon types.</span></span>

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

<span data-ttu-id="71688-358">为登录类型还原默认的已审核邮箱操作的结果如下:</span><span class="sxs-lookup"><span data-stu-id="71688-358">Restoring he default audited mailbox actions for a logon type has the following results:</span></span>

- <span data-ttu-id="71688-359">邮箱操作的当前列表将替换为登录类型的默认邮箱操作。</span><span class="sxs-lookup"><span data-stu-id="71688-359">The current list of mailbox actions is replaced with the default mailbox actions for the logon type.</span></span>

- <span data-ttu-id="71688-360">由 Microsoft 发布的任何新邮箱操作都会自动添加到登录类型的已审核操作列表中。</span><span class="sxs-lookup"><span data-stu-id="71688-360">Any new mailbox actions that are released by Microsoft are automatically added to the list of audited actions for the logon type.</span></span>

- <span data-ttu-id="71688-361">邮箱的*DefaultAuditSet*属性值将更新, 以包含已还原的登录类型。</span><span class="sxs-lookup"><span data-stu-id="71688-361">The *DefaultAuditSet* property value for the mailbox is updated to include the restored logon type.</span></span>

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a><span data-ttu-id="71688-362">为你的组织默认关闭邮箱审核</span><span class="sxs-lookup"><span data-stu-id="71688-362">Turn off mailbox auditing on by default for your organization</span></span>

<span data-ttu-id="71688-363">您可以通过在 Exchange Online PowerShell 中运行以下命令, 在默认情况下为整个组织关闭邮箱审核:</span><span class="sxs-lookup"><span data-stu-id="71688-363">You can turn off mailbox auditing on by default for your entire organization by running the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $true
```

<span data-ttu-id="71688-364">默认情况下, 禁用邮箱审核具有以下结果:</span><span class="sxs-lookup"><span data-stu-id="71688-364">Turning off mailbox auditing on by default has the following results:</span></span>

- <span data-ttu-id="71688-365">对您的组织禁用邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="71688-365">Mailbox auditing is disabled for your organization.</span></span>

- <span data-ttu-id="71688-366">从您禁用邮箱审核时, 默认情况下不会审核任何邮箱操作, 即使在邮箱上启用了审核 (邮箱上的*AuditEnabled*属性为 True) 也是**如此**。</span><span class="sxs-lookup"><span data-stu-id="71688-366">From the time you disabled mailbox auditing on by default, no mailbox actions are audited, even if auditing is enabled on a mailbox (the *AuditEnabled* property on the mailbox is **True**).</span></span>

- <span data-ttu-id="71688-367">邮箱审核没有为新邮箱启用, 并将新邮箱或现有邮箱的*AuditEnabled*属性设置为**True**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="71688-367">Mailbox auditing is not enabled for new mailboxes and setting the *AuditEnabled* property on a new or existing mailbox to **True** will be ignored.</span></span>

- <span data-ttu-id="71688-368">任何邮箱审核绕过关联设置 (使用**get-mailboxauditbypassassociation** cmdlet 配置) 都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="71688-368">Any mailbox audit bypass association settings (configured by using the **Set-MailboxAuditBypassAssociation** cmdlet) are ignored.</span></span>

- <span data-ttu-id="71688-369">现有邮箱审核记录将一直保留, 直到记录的审核日志期限过期为止。</span><span class="sxs-lookup"><span data-stu-id="71688-369">Existing mailbox audit records are retained until the audit log age limit for the the record expires.</span></span>

### <a name="turn-on-mailbox-auditing-on-by-default"></a><span data-ttu-id="71688-370">默认情况下启用邮箱审核</span><span class="sxs-lookup"><span data-stu-id="71688-370">Turn on mailbox auditing on by default</span></span>

<span data-ttu-id="71688-371">若要为您的组织重新启用邮箱审核, 请在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-371">To turn mailbox auditing back on for your organization, run the following command in Exchange Online PowerShell:</span></span>

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a><span data-ttu-id="71688-372">绕过邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="71688-372">Bypass mailbox audit logging</span></span>

<span data-ttu-id="71688-373">目前, 在组织中启用默认邮箱审核时, 不能禁用特定邮箱的邮箱审核。</span><span class="sxs-lookup"><span data-stu-id="71688-373">Currently, you can't disable mailbox auditing for specific mailboxes when mailbox auditing on by default is turned on in your organization.</span></span> <span data-ttu-id="71688-374">例如, 将*AuditEnabled*邮箱属性设置为**False**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="71688-374">For example, setting the *AuditEnabled* mailbox property to **False** is ignored.</span></span>

<span data-ttu-id="71688-375">但是, 您仍可以使用 Exchange Online PowerShell 中的**get-mailboxauditbypassassociation** cmdlet 来阻止记录指定用户的*任何*邮箱操作, 而不考虑这些操作在何处发生。</span><span class="sxs-lookup"><span data-stu-id="71688-375">However, you can still use the **Set-MailboxAuditBypassAssociation** cmdlet in Exchange Online PowerShell to prevent *any and all* mailbox actions by the specified users from being logged, regardless where the actions occur.</span></span> <span data-ttu-id="71688-376">例如：</span><span class="sxs-lookup"><span data-stu-id="71688-376">For example:</span></span>

- <span data-ttu-id="71688-377">不记录绕过用户执行的邮箱所有者操作。</span><span class="sxs-lookup"><span data-stu-id="71688-377">Mailbox owner actions performed by the bypassed users aren't logged.</span></span>

- <span data-ttu-id="71688-378">委派由其他用户的邮箱 (包括共享邮箱) 执行的绕过用户执行的操作不会记录。</span><span class="sxs-lookup"><span data-stu-id="71688-378">Delegate actions performed by the bypassed users on other users' mailboxes (including shared mailboxes) aren't logged.</span></span>

- <span data-ttu-id="71688-379">不会记录绕过用户执行的管理操作。</span><span class="sxs-lookup"><span data-stu-id="71688-379">Admin actions performed by the bypassed users aren't logged.</span></span>

<span data-ttu-id="71688-380">若要绕过特定用户的邮箱审核日志记录\<,\>请将 MailboxIdentity 替换为用户的名称、电子邮件地址、别名或用户主体名称 (用户名), 并运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-380">To bypass mailbox audit logging for a specific user, replace \<MailboxIdentity\> with the name, email address, alias, or user principal name (username) of the user and run the following command:</span></span>

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

<span data-ttu-id="71688-381">若要验证是否对指定用户跳过审核, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="71688-381">To verify that auditing is bypassed for the specified user, run the following command:</span></span>

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

<span data-ttu-id="71688-382">如果值**为 True** , 则表示对用户绕过邮箱审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="71688-382">The value **True** indicates that mailbox audit logging is bypassed for the user.</span></span>

## <a name="more-information"></a><span data-ttu-id="71688-383">更多信息</span><span class="sxs-lookup"><span data-stu-id="71688-383">More information</span></span>

- <span data-ttu-id="71688-384">只有在管理员手动启用了邮箱审核日志记录的用户使用 E5 许可证或邮箱时, 才会在安全 & 合规中心或通过 Office 365 管理活动 API 中返回审核日志搜索中的邮箱审核日志事件。</span><span class="sxs-lookup"><span data-stu-id="71688-384">Only users with E5 licenses or mailboxes where mailbox audit logging was manually enabled by an admin will return mailbox audit log events in audit log searches in the Security & Compliance Center or via the Office 365 Management Activity API.</span></span>

  <span data-ttu-id="71688-385">若要检索没有 E5 许可证的用户的邮箱审核日志条目, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="71688-385">To retrieve mailbox audit log entries for users without E5 licenses, you can:</span></span>

  - <span data-ttu-id="71688-386">在 Exchange Online PowerShell 中使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="71688-386">Use the following cmdlets in Exchange Online PowerShell:</span></span>

    - <span data-ttu-id="71688-387">[搜索-search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)以搜索特定用户的邮箱审核日志。</span><span class="sxs-lookup"><span data-stu-id="71688-387">[Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) to search the mailbox audit log for specific users.</span></span>

    - <span data-ttu-id="71688-388">[New-mailboxauditlogsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch)搜索特定用户的邮箱审核日志, 并将结果通过电子邮件发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="71688-388">[New-MailboxAuditLogSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch) to search the mailbox audit log for specific users and to have the results sent via email to specified recipients.</span></span>

  - <span data-ttu-id="71688-389">使用 exchange Online 中的 Exchange 管理中心 (EAC) 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="71688-389">Use the Exchange admin center (EAC) in Exchange Online to do the following:</span></span>

    - [<span data-ttu-id="71688-390">导出邮箱审核日志</span><span class="sxs-lookup"><span data-stu-id="71688-390">Export mailbox audit logs</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [<span data-ttu-id="71688-391">运行非所有者邮箱访问报告</span><span class="sxs-lookup"><span data-stu-id="71688-391">Run a non-owner mailbox access report</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- <span data-ttu-id="71688-392">默认情况下, 邮箱审核日志记录会在被删除前的90天后保留。</span><span class="sxs-lookup"><span data-stu-id="71688-392">By default, mailbox audit log records are retained for 90 days before they're deleted.</span></span> <span data-ttu-id="71688-393">您可以使用 Exchange Online PowerShell 中的 "**设置邮箱**" cmdlet 上的*AuditLogAgeLimit*参数更改审核日志记录的期限。</span><span class="sxs-lookup"><span data-stu-id="71688-393">You can change the age limit for audit log records by using the *AuditLogAgeLimit* parameter on the **Set-Mailbox** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="71688-394">但是, 增加此值不会允许您在 Office 365 审核日志中搜索超过90天的事件。</span><span class="sxs-lookup"><span data-stu-id="71688-394">However, increasing this value doesn't allow you to search for events that are older than 90 days in the Office 365 audit log.</span></span>

  <span data-ttu-id="71688-395">如果增加期限, 则需要使用 Exchange Online PowerShell 中的[search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet 在用户的邮箱审核日志中搜索早于90天的记录。</span><span class="sxs-lookup"><span data-stu-id="71688-395">If you increase the age limit, you need to use the [Search-MailboxAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet in Exchange Online PowerShell to search the user's mailbox audit log for records that are older than 90 days.</span></span>

- <span data-ttu-id="71688-396">如果您已在邮箱审核之前对邮箱的*AuditLogAgeLimit*属性进行了更改, 则该邮箱的现有审核日志期限不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="71688-396">If you've changed the *AuditLogAgeLimit* property for a mailbox prior to mailbox auditing on by default being turned on for organization, the mailbox's existing audit log age limit isn't changed.</span></span> <span data-ttu-id="71688-397">换言之, 默认情况下邮箱审核不会影响邮箱审核记录的当前期限。</span><span class="sxs-lookup"><span data-stu-id="71688-397">In other words, mailbox auditing on by default doesn't effect the current age limit for mailbox audit records.</span></span>

- <span data-ttu-id="71688-398">若要更改 Office 365 组邮箱上的*AuditLogAgeLimit*值, 需要将该`-GroupMailbox`开关包含在 "**设置邮箱**" 命令中。</span><span class="sxs-lookup"><span data-stu-id="71688-398">To change the *AuditLogAgeLimit* value on an Office 365 Group mailbox, you need to include the `-GroupMailbox` switch in the **Set-Mailbox** command.</span></span>

- <span data-ttu-id="71688-399">邮箱审核日志记录存储在每个用户邮箱的 "可恢复的项目" 文件夹中的子文件夹 (称为*审核*) 中。</span><span class="sxs-lookup"><span data-stu-id="71688-399">Mailbox audit log records are stored in a subfolder (named *Audits*) in the Recoverable Items folder in each user's mailbox.</span></span> <span data-ttu-id="71688-400">请记住以下有关邮箱审核记录和 "可恢复的项目" 文件夹的事项:</span><span class="sxs-lookup"><span data-stu-id="71688-400">Keep the following things in mind about mailbox audit records and the Recoverable Items folder:</span></span>

  - <span data-ttu-id="71688-401">邮箱审核记录根据 "可恢复的项目" 文件夹的存储配额进行计数, 默认情况下 30GB (警告配额为 20 GB)。</span><span class="sxs-lookup"><span data-stu-id="71688-401">Mailbox audit records count against the storage quota of the Recoverable Items folder, which is 30GB by default (the warning quota is 20 GB).</span></span> <span data-ttu-id="71688-402">在以下情况时, 存储配额会自动增加到 100 GB (使用 90 GB 警告配额):</span><span class="sxs-lookup"><span data-stu-id="71688-402">The storage quota is automatically increased to 100 GB (with a 90 GB warning quota) when:</span></span>

    - <span data-ttu-id="71688-403">邮箱上放置了保留项。</span><span class="sxs-lookup"><span data-stu-id="71688-403">A hold is placed on a mailbox.</span></span>

    - <span data-ttu-id="71688-404">将邮箱分配给合规中心中的保留策略。</span><span class="sxs-lookup"><span data-stu-id="71688-404">The mailbox is assigned to a retention policy in the Compliance Center.</span></span>

  - <span data-ttu-id="71688-405">邮箱审核记录也会对["可恢复的项目" 文件夹的文件夹限制进行](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)计数。</span><span class="sxs-lookup"><span data-stu-id="71688-405">Mailbox audit records also count against the [folder limit for the Recoverable Items folder](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits).</span></span> <span data-ttu-id="71688-406">最多可以将3000000个项目 (审核记录) 存储在 "审核" 子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71688-406">A maximum of 3 million items (audit records) can be stored in the Audits subfolder.</span></span>

    > [!NOTE]
    > <span data-ttu-id="71688-407">邮箱默认情况下的审核不太可能会影响存储配额或 "可恢复的项目" 文件夹的文件夹限制。</span><span class="sxs-lookup"><span data-stu-id="71688-407">It's unlikely that mailbox auditing on by default will impact the storage quota or the folder limit for the Recoverable Items folder.</span></span>

    - <span data-ttu-id="71688-408">您可以在 Exchange Online PowerShell 中运行以下命令, 以在 "可恢复的项目" 文件夹的 "审核" 子文件夹中显示项目的大小和数量:</span><span class="sxs-lookup"><span data-stu-id="71688-408">You can run the following command in Exchange Online PowerShell to display the size and number of items in the Audits subfolder in the Recoverable Items folder:</span></span>

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - <span data-ttu-id="71688-409">您不能直接访问 "可恢复的项目" 文件夹中的审核日志记录;相反, 您可以使用**search-mailboxauditlog** cmdlet 或搜索 Office 365 审核日志来查找和查看邮箱审核记录。</span><span class="sxs-lookup"><span data-stu-id="71688-409">You can't directly access an audit log record in the Recoverable Items folder; instead, you use the **Search-MailboxAuditLog** cmdlet or search the Office 365 audit log to find and view mailbox audit records.</span></span>

- <span data-ttu-id="71688-410">如果将邮箱置于保留或分配到合规中心中的保留策略, 则在邮箱的*AuditLogAgeLimit*属性定义的持续时间内仍会保留审核日志记录 (默认情况下为90天)。</span><span class="sxs-lookup"><span data-stu-id="71688-410">If a mailbox is placed on hold or assigned to a retention policy in the Compliance Center, audit log records are still retained for the duration that's defined by the mailbox's *AuditLogAgeLimit* property (90 days by default).</span></span> <span data-ttu-id="71688-411">若要延长保留邮箱的审核日志记录, 您需要增加邮箱的*AuditLogAgeLimit*值。</span><span class="sxs-lookup"><span data-stu-id="71688-411">To retain audit log records longer for mailboxes on hold, you need to increase mailbox's *AuditLogAgeLimit* value.</span></span>
