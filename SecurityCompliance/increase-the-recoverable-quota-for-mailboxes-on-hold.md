---
title: 为置于保留状态的邮箱增加可恢复项目的配额
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '启用存档邮箱并打开自动扩展存档, 以增加 Office 365 中的 "可恢复的项目" 文件夹的大小。 '
ms.openlocfilehash: ebb052ba17ba8a84076e1e75a82713cc5cf437a1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218472"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="71e74-103">为置于保留状态的邮箱增加可恢复项目的配额</span><span class="sxs-lookup"><span data-stu-id="71e74-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="71e74-p101">将自动应用于 Exchange Online 中新邮箱的默认保留策略 (名为 "默认 MRM 策略") 包含一个名为 "可恢复的项目14天" 的保留标记, 可转移到存档中。此保留标记将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中, 在该项目的14天保留期到期之后。为此, 必须启用用户的存档邮箱。如果未启用存档邮箱, 则不会执行任何操作, 这意味着保留邮箱的 "可恢复的项目" 文件夹中的项目在14天保留期过期后不会移动到存档邮箱。由于保留邮箱时不会从邮箱中删除任何内容, 因此可能会超出 "可恢复的项目" 文件夹的存储配额, 尤其是在未启用用户的存档邮箱的情况下。</span><span class="sxs-lookup"><span data-stu-id="71e74-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="71e74-p102">为了帮助降低超出此限制的可能性, 在 Exchange Online 中的邮箱上放置保留时, "可恢复的项目" 文件夹的存储配额将自动从 30 gb 增加到 100 GB。如果启用存档邮箱, 则存档邮箱中的 "可恢复的项目" 文件夹的存储配额也会从 30 gb 增加到 100 GB。如果启用了 Exchange Online 中的自动扩展存档功能, 则用户存档中的 "可恢复的项目" 文件夹的存储配额将不受限制。</span><span class="sxs-lookup"><span data-stu-id="71e74-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="71e74-112"> 下表总结了“可恢复项目”文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="71e74-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="71e74-113">**“可恢复的项目”文件夹的位置**</span><span class="sxs-lookup"><span data-stu-id="71e74-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="71e74-114">**未置于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="71e74-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="71e74-115">**置于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="71e74-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71e74-116">主邮箱</span><span class="sxs-lookup"><span data-stu-id="71e74-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="71e74-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="71e74-117">30 GB</span></span>  <br/> |<span data-ttu-id="71e74-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="71e74-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="71e74-119">存档邮箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="71e74-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="71e74-120">无限制</span><span class="sxs-lookup"><span data-stu-id="71e74-120">Unlimited</span></span>  <br/> |<span data-ttu-id="71e74-121">无限制</span><span class="sxs-lookup"><span data-stu-id="71e74-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="71e74-122">**“可恢复的项目”文件夹的总存储配额**</span><span class="sxs-lookup"><span data-stu-id="71e74-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="71e74-123">无限制</span><span class="sxs-lookup"><span data-stu-id="71e74-123">Unlimited</span></span>  <br/> |<span data-ttu-id="71e74-124">无限制</span><span class="sxs-lookup"><span data-stu-id="71e74-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="71e74-p103"><sup>\*</sup>存档邮箱的初始存储配额为 100 GB (适用于具有 Exchange Online (计划 2) 许可证的用户。但是, 如果在保留时为邮箱启用自动扩展存档, 则存档邮箱和 "可恢复的项目" 文件夹的存储配额将增加到 110 GB。必要时将预配其他存档存储空间, 从而导致存档存储量不受限制。有关自动扩展存档的详细信息, 请参阅[Office 365 中的无限制存档概述](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="71e74-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB. Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="71e74-129">当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="71e74-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="71e74-p104">**启用存档邮箱并打开自动扩展存档**-您只需启用存档邮箱, 然后在 Exchange 中打开自动扩展存档功能, 即可为 "可恢复的项目" 文件夹启用无限制的存储容量隐私声明.这将导致主邮箱中的 "可恢复的项目" 文件夹的 110 GB 和用户存档中 "可恢复的项目" 文件夹的存储容量不受限制。请参阅如何:[在 office 365 安全&amp;合规中心中启用存档邮箱](enable-archive-mailboxes.md), 以及如何[在 office 365 中启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="71e74-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="71e74-p105">在为接近于 "可恢复的项目" 文件夹的存储配额的邮箱启用存档后, 您可能需要运行托管文件夹助理以手动触发助理来处理邮箱, 以便将过期的项目移到存档邮箱中的 "可恢复的项目" 文件夹。有关说明, 请参阅[步骤 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。请注意, 用户邮箱中的其他项目可能会移至新的存档邮箱。请考虑告诉用户在启用存档邮箱后可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="71e74-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="71e74-p106">在**保留时为邮箱创建自定义保留策略**, 除了在诉讼保留或就地保留中启用邮箱的存档邮箱和自动扩展存档外, 你可能还需要为上的邮箱创建自定义保留策略同时.这样, 你就可以将保留策略应用于保留的邮箱, 这不同于应用于不处于保留状态的邮箱的默认 MRM 策略。这样, 您就可以应用专门为邮箱处于保留状态而设计的保留标记。这包括为 "可恢复的项目" 文件夹创建新的保留标记。</span><span class="sxs-lookup"><span data-stu-id="71e74-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="71e74-141">本主题的剩余部分介绍了为置于保留状态的邮箱创建自定义保留策略的分步步骤。</span><span class="sxs-lookup"><span data-stu-id="71e74-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="71e74-142">步骤 1：为“可恢复的项目”文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="71e74-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="71e74-143">[[步骤 2: 为处于保留状态的邮箱创建新的保留策略](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="71e74-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="71e74-144">步骤 3：为置于保留状态的邮箱应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="71e74-145">（可选）步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="71e74-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="71e74-146">步骤 1：为“可恢复的项目”文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="71e74-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="71e74-p107">第一步是为 "可恢复的项目" 文件夹创建自定义保留标记 (称为保留策略标记或 RPT)。如前所述, 此 RPT 将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到用户的存档邮箱中的 "可恢复的项目" 文件夹中。您必须使用 PowerShell 为 "可恢复的项目" 文件夹创建 RPT。您不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="71e74-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="71e74-151">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="71e74-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="71e74-152">运行以下命令可创建“可恢复的项目”文件夹的新 RPT： </span><span class="sxs-lookup"><span data-stu-id="71e74-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="71e74-p108">例如，以下命令将为保留期为 30 天的名为“可恢复的项目在保留邮箱中保留 30 天”的“可恢复的项目”文件夹创建 RPT。这意味着某个项目在“可恢复的项目”文件夹中存在 30 天后，将被移动到用户存档邮箱“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="71e74-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="71e74-p109">我们建议可恢复项目 RPT 的保留期 (由_AgeLimitForRetention_参数定义) 与 RPT 将应用到的邮箱的已删除项目保留期相同。这允许用户整个已删除项目的保留期在将已删除邮件移至存档邮箱之前将其恢复。在上面的示例中, 假定邮箱的已删除邮件保留期也为30天, 则保留期已设置为30天。默认情况下, Exchange Online 邮箱配置为将已删除项目保留14天。但您最多可以将此设置更改为30天。有关详细信息, 请参阅[在 Exchange Online 中更改邮箱的已删除邮件保留期](https://go.microsoft.com/fwlink/p/?LinkId=286940)。</span><span class="sxs-lookup"><span data-stu-id="71e74-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="71e74-161">步骤 2：为置于保留状态的邮箱创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="71e74-p110">下一步是创建新的保留策略，并为其添加保留标记，其中包括在步骤 1 中创建的“可恢复的项目”RPT。这项新策略将在下一步骤中应用于置于保留状态的邮箱。 </span><span class="sxs-lookup"><span data-stu-id="71e74-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="71e74-p111">创建新的保留策略之前，请确定你想要添加的其他保留标记。有关添加到“默认 MRM 策略”的保留标记列表，以及有关创建新的保留标记的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="71e74-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="71e74-166">Exchange Online 中的默认保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="71e74-167">支持保留策略标记的默认文件夹</span><span class="sxs-lookup"><span data-stu-id="71e74-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="71e74-168">"[创建保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404422)" 主题中的 "创建保留标记" 部分。</span><span class="sxs-lookup"><span data-stu-id="71e74-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="71e74-169">您可以使用 EAC 或 Exchange Online PowerShell 创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="71e74-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="71e74-170">使用 EAC 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="71e74-171">在 EAC 中, 转到 **"合规性管理** \> **保留策略**", 然后单击 "](media/ITPro-EAC-AddIcon.gif)**添加** ![" "添加" 图标。</span><span class="sxs-lookup"><span data-stu-id="71e74-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="71e74-172">在 "**新建保留策略**" 页上的 "**名称**" 下, 键入描述保留策略用途的名称;例如, 处于**保留状态的邮箱的 MRM 策略**。</span><span class="sxs-lookup"><span data-stu-id="71e74-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="71e74-173">在 **"保留标记**" 下, 单击](media/ITPro-EAC-AddIcon.gif)"**添加** ![" "添加" 图标。</span><span class="sxs-lookup"><span data-stu-id="71e74-173">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="71e74-174">在 "保留标记" 列表中, 选择您在步骤1中创建的 "可恢复的项目" RPT, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![选择自定义的“可恢复的项目”保留标记](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="71e74-p112">选择要添加到该保留策略的其他保留标记。例如，可能要添加在默认的 MRM 策略中所含的相同的标记。</span><span class="sxs-lookup"><span data-stu-id="71e74-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="71e74-178">添加完保留标记后, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="71e74-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="71e74-179">单击 "**保存**" 以创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="71e74-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="71e74-180">请注意，在详细信息窗格中显示链接到保留策略的保留标记。</span><span class="sxs-lookup"><span data-stu-id="71e74-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![在详细信息窗格中显示链接到保留策略的保留标记](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="71e74-182">使用 Exchange Online PowerShell 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="71e74-183">若要为置于保留状态的邮箱创建新的保留策略，请运行以下命令： </span><span class="sxs-lookup"><span data-stu-id="71e74-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="71e74-184">例如，以下命令将创建保留策略以及上图中显示的链接的保留标记。</span><span class="sxs-lookup"><span data-stu-id="71e74-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="71e74-185">步骤 3：为置于保留状态的邮箱应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="71e74-p113">最后一步是将您在步骤2中创建的新的保留策略应用于组织中的 "保留中的邮箱"。您可以使用 EAC 或 Exchange Online PowerShell 将保留策略应用于单个邮箱或多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="71e74-188">使用 EAC 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="71e74-189">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="71e74-190">在列表视图中, 选择要应用保留策略的邮箱, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。</span><span class="sxs-lookup"><span data-stu-id="71e74-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="71e74-191">在 "**用户邮箱**" 页上, 单击 "**邮箱功能**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="71e74-192">在 "**保留策略**" 下, 选择您在步骤2中创建的保留策略, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="71e74-193">此外，还可使用 EAC 将保留策略应用到多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="71e74-194">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="71e74-195">在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="71e74-196">在详细信息窗格中, 单击 "**更多选项**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="71e74-197">在 "**保留策略**" 下, 单击 "**更新**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="71e74-198">在 "**批量分配保留策略**" 页上, 选择您在步骤2中创建的保留策略, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="71e74-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="71e74-199">使用 Exchange Online PowerShell 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="71e74-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="71e74-p114">您可以使用 Exchange Online PowerShell 将新的保留策略应用于单个邮箱。但是, PowerShell 真正的强大之处在于, 您可以使用它来快速标识组织中的所有处于诉讼保留或就地保留状态的邮箱, 然后在单个命令中将新的保留策略应用于处于保留状态的所有邮箱。下面是使用 Exchange PowerShell 将保留策略应用于一个或多个邮箱的一些示例。所有示例都应用在步骤2中创建的保留策略。</span><span class="sxs-lookup"><span data-stu-id="71e74-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="71e74-204">本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="71e74-205">本示例将新的保留策略应用于组织中置于诉讼保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="71e74-206">本示例将新的保留策略应用于组织中置于就地保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="71e74-207">可以使用 **Get-Mailbox** cmdlet 验证是否已应用新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="71e74-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="71e74-208">以下示例可确认之前示例中的命令已将“置于保留状态的邮箱的 MRM 策略”保留策略应用于置于诉讼保留和就地保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="71e74-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="71e74-209">（可选）步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="71e74-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="71e74-p115">将新的保留策略应用于保留邮箱后, 托管文件夹助理在 Exchange Online 中最长可能需要7天才能使用新的保留策略中的设置处理这些邮箱。您可以使用**start-managedfolderassistant** cmdlet 手动触发助理以处理应用新的保留策略的邮箱, 而不是等待托管文件夹助理运行。</span><span class="sxs-lookup"><span data-stu-id="71e74-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="71e74-212">运行以下命令，启动 Pilar Pinilla 邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="71e74-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="71e74-213">运行以下命令，启动置于保留状态的所有邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="71e74-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="71e74-214">更多信息</span><span class="sxs-lookup"><span data-stu-id="71e74-214">More information</span></span>

- <span data-ttu-id="71e74-p116">启用用户的存档邮箱后, 请考虑告诉用户其邮箱中的其他项目 (不仅仅是 "可恢复的项目" 文件夹中的项目) 可能会被移至存档邮箱。这是因为分配给 Exchange Online 邮箱的默认 MRM 策略包含一个保留标记 (名为 "默认2年移动到存档"), 该保留标记将项目移至存档邮箱, 然后在邮件传递到邮箱或由 "创建时间"user.有关详细信息, 请参阅[Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="71e74-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="71e74-p117">启用用户的存档邮箱后, 您可能还会告诉用户他们可以在其存档邮箱中的 "可恢复的项目" 文件夹中恢复已删除的邮件。在 Outlook 中, 可以通过选择存档邮箱中的 "**已删除邮件**" 文件夹, 然后在 "**开始**" 选项卡上单击 "**从服务器恢复已删除邮件**" 来执行此操作。有关恢复已删除项目的详细信息, 请参阅[在 Outlook for Windows 中恢复已删除的项目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="71e74-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
