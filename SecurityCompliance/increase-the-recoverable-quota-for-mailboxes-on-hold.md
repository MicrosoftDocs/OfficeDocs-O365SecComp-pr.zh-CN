---
title: 为置于保留状态的邮箱增加可恢复项目的配额
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: '启用存档邮箱并启用自动扩展以增加的 Office 365 中的邮箱可恢复邮件文件夹大小的存档。 '
ms.openlocfilehash: 2e7149ef10152a11dc638c04b61a261440b539b8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524929"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="aedcb-103">为置于保留状态的邮箱增加可恢复项目的配额</span><span class="sxs-lookup"><span data-stu-id="aedcb-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="aedcb-p101">默认保留策略 — 名为默认 MRM 策略 — 即 Exchange Online 中的自动应用于新邮箱包含一个名为可恢复邮件 14 天后移动到存档的保留标记。此保留标记将项目从用户的主邮箱中可恢复邮件文件夹中用户的存档邮箱的可恢复项目文件夹后 14 天保留期项目。对于这种情况，必须启用用户的存档邮箱。如果没有启用存档邮箱，则不执行任何操作，这意味着 14 天保留期过后，在可恢复项目文件夹上的邮箱的保留的项目不会移动到存档邮箱。因为不会删除从邮箱置于保留状态，它有可能，可能会超过可恢复邮件文件夹的存储配额，尤其是用户的存档邮箱未启用。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p101">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive. This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item. For this to happen, the user's archive mailbox must be enabled. If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires. Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="aedcb-p102">为了帮助减少超过此限制的机会，可恢复邮件文件夹的存储配额自动增加从 30 GB 为 100 GB 保留发出时对邮箱在 Exchange Online。如果启用存档邮箱，则存档邮箱中可恢复邮件文件夹的存储配额还增加从 30 GB 为 100 GB。如果自动扩展存档功能在 Exchange Online 已启用，用户的存档中可恢复邮件文件夹的存储配额将不受限制。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p102">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online. If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB. If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="aedcb-112"> 下表总结了“可恢复项目”文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="aedcb-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="aedcb-113">**“可恢复的项目”文件夹的位置**</span><span class="sxs-lookup"><span data-stu-id="aedcb-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="aedcb-114">**未置于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="aedcb-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="aedcb-115">**置于保留状态的邮箱**</span><span class="sxs-lookup"><span data-stu-id="aedcb-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aedcb-116">主邮箱</span><span class="sxs-lookup"><span data-stu-id="aedcb-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="aedcb-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="aedcb-117">30 GB</span></span>  <br/> |<span data-ttu-id="aedcb-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="aedcb-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="aedcb-119">存档邮箱<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aedcb-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="aedcb-120">无限制</span><span class="sxs-lookup"><span data-stu-id="aedcb-120">Unlimited</span></span>  <br/> |<span data-ttu-id="aedcb-121">无限制</span><span class="sxs-lookup"><span data-stu-id="aedcb-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="aedcb-122">**“可恢复的项目”文件夹的总存储配额**</span><span class="sxs-lookup"><span data-stu-id="aedcb-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="aedcb-123">无限制</span><span class="sxs-lookup"><span data-stu-id="aedcb-123">Unlimited</span></span>  <br/> |<span data-ttu-id="aedcb-124">无限制</span><span class="sxs-lookup"><span data-stu-id="aedcb-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="aedcb-p103"><sup>\*</sup>存档邮箱的初始存储配额具有一个 Exchange Online (计划 2) 许可证的用户是 100 GB。但是，打开自动扩展存档后，用户的存档和存档中的可恢复邮件文件夹的存储配额为 unlimited。有关自动扩展存档，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p103"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license. However, when auto-expanding archiving is turned on, the storage quota for the user's archive and the Recoverable Items folder in the archive is unlimited. For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="aedcb-128">当置于保留状态的邮箱的主邮箱"可恢复的项目"文件夹的存储配额接近其限额时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aedcb-128">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="aedcb-p104">**启用存档邮箱，启用自动扩展存档**-只需通过启用存档邮箱并将其打开 Exchange 中的自动扩展的存档功能，可以启用不受限制的存储空间留给的可恢复邮件文件夹联机。这将导致 100 GB 的主邮箱和不限制的数量的存储容量用于在用户的存档可恢复邮件文件夹中可恢复邮件文件夹。请参阅如何： [Office 365 安全性启用存档邮箱&amp;合规性中心](enable-archive-mailboxes.md)和[启用 Office 365 中的无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p104">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online. This results in 100 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive. See how: [Enable archive mailboxes in the Office 365 Security &amp; Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aedcb-p105">启用存档以接近超出可恢复邮件文件夹的存储配额的邮箱后，您可能想要运行托管文件夹助理要手动触发助理处理邮箱，以便过期的项目移动可恢复项目文件夹中的存档邮箱。有关说明，请参阅[步骤 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) 。请注意，可能会将用户邮箱中的其他项移动到新的存档邮箱。请考虑告知用户这可能会发生后启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p105">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox. See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions. Note that other items in the user's mailbox might be moved to the new archive mailbox. Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="aedcb-p106">**创建自定义保留策略上邮箱保留**-除了启用存档邮箱和自动扩展的存档邮箱置于诉讼保留或就地保留，也可以在创建自定义保留策略的邮箱保留。这让我们您将保留策略应用于保持不同于默认 MRM 策略应用于不处于保持状态的邮箱的邮箱。这样可以应用专为置于保持状态的邮箱的保留标记。这包括创建一个新的保留标记为可恢复邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p106">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold. This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold. This lets you to apply retention tags that are specifically designed for mailboxes on hold. This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="aedcb-140">本主题的剩余部分介绍了为置于保留状态的邮箱创建自定义保留策略的分步步骤。</span><span class="sxs-lookup"><span data-stu-id="aedcb-140">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="aedcb-141">步骤 1：为“可恢复的项目”文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="aedcb-141">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="aedcb-142">[[步骤 2： 创建新的保留策略的邮箱置于保留状态](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="aedcb-142">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="aedcb-143">步骤 3：为置于保留状态的邮箱应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-143">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="aedcb-144">（可选）步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="aedcb-144">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="aedcb-145">步骤 1：为“可恢复的项目”文件夹创建自定义保留标记</span><span class="sxs-lookup"><span data-stu-id="aedcb-145">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="aedcb-p107">第一步是创建可恢复邮件文件夹的自定义保留标记 （称为保留策略标记或报表）。如前所述，该报表将项目从用户的主邮箱中可恢复邮件文件夹中用户的存档邮箱的可恢复项目文件夹。您需要使用 PowerShell 创建 RPT 可恢复邮件文件夹。不能使用 Exchange 管理员中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p107">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder. As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox. You have to use PowerShell to create an RPT for the Recoverable Items folder. You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="aedcb-150">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="aedcb-150">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="aedcb-151">运行以下命令可创建“可恢复的项目”文件夹的新 RPT： </span><span class="sxs-lookup"><span data-stu-id="aedcb-151">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="aedcb-p108">例如，以下命令将为保留期为 30 天的名为“可恢复的项目在保留邮箱中保留 30 天”的“可恢复的项目”文件夹创建 RPT。这意味着某个项目在“可恢复的项目”文件夹中存在 30 天后，将被移动到用户存档邮箱“可恢复的项目”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="aedcb-p109">我们建议可恢复项目报表的保留期 （由_AgeLimitForRetention_参数定义） 是报表将应用于邮箱已删除的邮件保留期限相同。这样，用户的整个已删除的邮件保留期恢复已删除的项目之前他们会移动到存档邮箱。在上面的示例中，保留期设置为 30 天假设的邮箱已删除的邮件保留期限还为 30 天。默认情况下，Exchange Online 邮箱配置为 14 天，保留已删除的项目。但是，您可以更改此设置为 30 天内的最大值。有关详细信息，请参阅[更改在 Exchange Online 邮箱的已删除的邮件保留期限](https://go.microsoft.com/fwlink/p/?LinkId=286940)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p109">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to. This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox. In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days. An Exchange Online mailbox is configured to retain deleted items for 14 days, by default. But you can change this setting to a maximum of 30 days. For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="aedcb-160">步骤 2：为置于保留状态的邮箱创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-160">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="aedcb-p110">下一步是创建新的保留策略，并为其添加保留标记，其中包括在步骤 1 中创建的“可恢复的项目”RPT。这项新策略将在下一步骤中应用于置于保留状态的邮箱。 </span><span class="sxs-lookup"><span data-stu-id="aedcb-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="aedcb-p111">创建新的保留策略之前，请确定你想要添加的其他保留标记。有关添加到“默认 MRM 策略”的保留标记列表，以及有关创建新的保留标记的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="aedcb-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="aedcb-165">默认值保留策略在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="aedcb-165">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="aedcb-166">支持保留策略标记的默认文件夹</span><span class="sxs-lookup"><span data-stu-id="aedcb-166">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="aedcb-167">[Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422)主题中的"创建保留标记"的部分。</span><span class="sxs-lookup"><span data-stu-id="aedcb-167">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="aedcb-168">您可以使用 EAC 或 Exchange Online PowerShell 中创建保留策略。</span><span class="sxs-lookup"><span data-stu-id="aedcb-168">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="aedcb-169">使用 EAC 创建保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-169">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="aedcb-170">在 EAC 中，转到**合规性管理** \> **保留策略**，然后单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-170">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="aedcb-171">在**新的保留策略**页上的在**名称**下，键入描述的保留策略; 目的的名称例如，为**MRM 策略的邮箱置于保留状态**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-171">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="aedcb-172">在**保留标记**，下单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-172">Under **Retention tags**, click **Add** ![Add Icon](media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="aedcb-173">在保留标记的列表中，选择您在步骤 1 中创建可恢复项目报表，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-173">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![选择自定义的“可恢复的项目”保留标记](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="aedcb-p112">选择要添加到该保留策略的其他保留标记。例如，可能要添加在默认的 MRM 策略中所含的相同的标记。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="aedcb-177">完成添加保留标记后，请单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-177">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="aedcb-178">单击**保存**以创建新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="aedcb-178">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="aedcb-179">请注意，在详细信息窗格中显示链接到保留策略的保留标记。</span><span class="sxs-lookup"><span data-stu-id="aedcb-179">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![在详细信息窗格中显示链接到保留策略的保留标记](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="aedcb-181">Exchange Online PowerShell 中用于创建保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-181">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="aedcb-182">若要为置于保留状态的邮箱创建新的保留策略，请运行以下命令： </span><span class="sxs-lookup"><span data-stu-id="aedcb-182">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="aedcb-183">例如，以下命令将创建保留策略以及上图中显示的链接的保留标记。</span><span class="sxs-lookup"><span data-stu-id="aedcb-183">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="aedcb-184">步骤 3：为置于保留状态的邮箱应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-184">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="aedcb-p113">最后一步是将应用您在步骤 2 到置于保持状态的邮箱在组织中创建新的保留策略。您可以使用 EAC 或 Exchange Online PowerShell 中将保留策略应用于单个邮箱或多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p113">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization. You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="aedcb-187">使用 EAC 应用新的保留策略</span><span class="sxs-lookup"><span data-stu-id="aedcb-187">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="aedcb-188">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="aedcb-188">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="aedcb-189">在列表视图中，选择要应用到，将保留策略的邮箱，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-189">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="aedcb-190">在**用户邮箱**页上，单击**邮箱功能**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-190">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="aedcb-191">**保留策略**，下选择您在步骤 2 中创建的保留策略，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-191">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="aedcb-192">此外，还可使用 EAC 将保留策略应用到多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-192">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="aedcb-193">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="aedcb-193">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="aedcb-194">在此列表视图中，使用 Shift 或 Ctrl 键选择多个邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-194">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="aedcb-195">在细节窗格中，单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-195">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="aedcb-196">**保留策略**，下单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-196">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="aedcb-197">在**批量分配保留策略**页上，选择您在步骤 2 中创建的保留策略，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="aedcb-197">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="aedcb-198">使用 Exchange Online PowerShell 中新的保留策略应用</span><span class="sxs-lookup"><span data-stu-id="aedcb-198">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="aedcb-p114">Exchange Online PowerShell 中可用于将新的保留策略应用于单个邮箱。但实际的 PowerShell 功能是您可以使用它来快速识别所有组织中的邮箱置于诉讼保留或就地保留，并然后应用于所有邮箱上的新的保留策略保留在单个命令。下面是使用 Exchange PowerShell 中将保留策略应用于一个或多个邮箱的一些示例。在步骤 2 中创建保留策略应用的所有示例。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p114">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox. But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command. Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes. All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="aedcb-203">本示例将新的保留策略应用于 Pilar Pinilla 的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-203">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="aedcb-204">本示例将新的保留策略应用于组织中置于诉讼保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-204">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="aedcb-205">本示例将新的保留策略应用于组织中置于就地保留状态的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-205">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="aedcb-206">可以使用 **Get-Mailbox** cmdlet 验证是否已应用新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="aedcb-206">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="aedcb-207">以下示例可确认之前示例中的命令已将“置于保留状态的邮箱的 MRM 策略”保留策略应用于置于诉讼保留和就地保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-207">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="aedcb-208">（可选）步骤 4：运行托管文件夹助理以应用新的保留设置</span><span class="sxs-lookup"><span data-stu-id="aedcb-208">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="aedcb-p115">将新的保留策略应用于置于保持状态的邮箱后，可能需要多达 7 天在 Exchange Online 的托管文件夹助理处理使用新的保留策略中设置这些邮箱。而不是等待托管文件夹助理运行，您可以使用**Start-managedfolderassistant** cmdlet 手动触发助理处理应用到新的保留策略的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p115">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy. Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="aedcb-211">运行以下命令，启动 Pilar Pinilla 邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="aedcb-211">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="aedcb-212">运行以下命令，启动置于保留状态的所有邮箱的托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="aedcb-212">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="aedcb-213">详细信息</span><span class="sxs-lookup"><span data-stu-id="aedcb-213">More information</span></span>

- <span data-ttu-id="aedcb-p116">启用用户的存档邮箱后，请考虑告知用户，他们的邮箱 （不只是项可恢复邮件文件夹中） 中的其他项可能将移动到存档邮箱。这是因为默认 MRM 策略，分配给 Exchange Online 邮箱包含一个将项目移动到存档邮箱项目已传递到邮箱或创建的日期之后的两年的保留标记 （移动命名默认 2 年进行存档）用户。有关详细信息，请参阅[Exchange Online 中的默认保留策略](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="aedcb-p116">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox. This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="aedcb-p117">启用用户的存档邮箱后，您可能还判断的用户，他们可以恢复已删除其存档邮箱中的可恢复项目文件夹中的项。它们可以通过实现此在 Outlook 中在存档邮箱中，选择**已删除邮件**文件夹，然后单击**主页**选项卡上的**从服务器恢复已删除邮件**。有关恢复已删除项目的详细信息，请参阅[恢复已删除的 Outlook for Windows 中的项目](https://go.microsoft.com/fwlink/p/?LinkId=624829)。</span><span class="sxs-lookup"><span data-stu-id="aedcb-p117">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox. They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
