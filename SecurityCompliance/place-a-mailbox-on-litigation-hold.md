---
title: 将邮箱放到诉讼保留中
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: '将邮箱置于"诉讼保留"以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。 '
ms.openlocfilehash: 8f440f5fc0bc7dafd639bdf8136808aa2f3bd35f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026439"
---
# <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="b5665-103">将邮箱放到诉讼保留中</span><span class="sxs-lookup"><span data-stu-id="b5665-103">Place a mailbox on Litigation Hold</span></span>
 
<span data-ttu-id="b5665-p101">将邮箱置于“诉讼保留”以保留所有的邮箱内容，包括已删除项和已修改项的原始版本。当您将用户邮箱置于诉讼保留状态时，用户的存档邮箱（如果已启用）中的内容也会置于保留状态。已删除和修改的项会在指定时段内保留，或直到您将邮箱从“诉讼保留”中删除。所有此类邮箱项目均会返回到[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx)搜索中。</span><span class="sxs-lookup"><span data-stu-id="b5665-p101">Place a mailbox on Litigation Hold to preserve all mailbox content, including deleted items and original versions of modified items. When you place a user' mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also placed on hold. Deleted and modified items are preserved for a specified period, or until you remove the mailbox from Litigation Hold. All such mailbox items are returned in an [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) search.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5665-p102">诉讼保留保留用户邮箱中可恢复邮件文件夹中的项目。根据数量和大小的已删除或修改的项目，可能会快速增加的邮箱的可恢复邮件文件夹大小。默认情况下，可恢复邮件文件夹配置使用高配额。在 Exchange Online 中，您将邮箱置于诉讼保留时自动增加此配额。在 Exchange Server 2013，我们建议您监视置于诉讼保留每周执行以确保它们不达到的可恢复的项目配额限制的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5665-p102">Litigation Hold preserves items in the Recoverable Items folder in the user's mailbox. Depending on number and size of items deleted or modified, the size of the Recoverable Items folder of the mailbox may increase quickly. The Recoverable Items folder is configured with a high quota by default. In Exchange Online, this quota is automatically increased when you place a mailbox on Litigation Hold. In Exchange Server 2013, we recommend that you monitor mailboxes that are placed on Litigation Hold on a weekly basis to ensure they don't reach the limits of the Recoverable Items quotas.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5665-113">在开始之前，需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="b5665-113">What do you need to know before you begin?</span></span>
<span data-ttu-id="b5665-114"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-114"></span></span>

- <span data-ttu-id="b5665-115">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="b5665-115">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="b5665-116">“诉讼保留”设置可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="b5665-116">The Litigation Hold setting may take up to 60 minutes to take effect.</span></span>
    
- <span data-ttu-id="b5665-p103">您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [邮件策略和遵从性权限](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主题中的"就地保留"条目。</span><span class="sxs-lookup"><span data-stu-id="b5665-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "In-Place Hold" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="b5665-p104">若要将 Exchange Online 邮箱置于诉讼保留状态，必须将它分配的 Exchange Online (计划 2) 许可证。如果邮箱已分配的 Exchange Online (计划 1) 许可证，您必须将其单独 Exchange Online Archiving 的许可证将它置于保留分配。</span><span class="sxs-lookup"><span data-stu-id="b5665-p104">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online (Plan 2) license. If a mailbox is assigned an Exchange Online (Plan 1) license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    
- <span data-ttu-id="b5665-p105">如前所述，当您置于诉讼保留用户邮箱中用户的存档邮箱的内容将还置于保持状态。如果您置于诉讼保留 Exchange 混合部署中的本地主邮箱，（如果已启用） 的基于云的存档邮箱还将置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="b5665-p105">As previously explained, when you place a Litigation Hold on a user's mailbox, content in the user's archive mailbox is also placed on hold. If you place a Litigation Hold on an on-premises primary mailbox in an Exchange hybrid deployment, the cloud-based archive mailbox (if enabled) is also placed on hold.</span></span>
    
- <span data-ttu-id="b5665-p106">在 Exchange Online 中，可恢复邮件文件夹的配额自动增加到 100 GB 时您将邮箱置于诉讼保留。此文件夹的默认大小为 30 GB。</span><span class="sxs-lookup"><span data-stu-id="b5665-p106">In Exchange Online, the quota for the Recoverable Items folder is automatically increased to 100 GB when you place a mailbox on Litigation Hold. The default size of this folder is 30 GB.</span></span>
    
- <span data-ttu-id="b5665-p107">诉讼保留保留已删除的项目，并还保留已修改的项目的原始版本，直到保留被删除。您可以选择指定指定的持续时间段内保留邮箱项目保留持续时间。如果指定保留持续时间段，它是从计算日期收到一条消息，或创建邮箱项目。若要保留符合指定的条件的项目，请使用就地保留来创建基于查询的保留。有关详细信息，请参阅[创建或删除就地保留](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5665-p107">Litigation Hold preserves deleted items and also preserves original versions of modified items until the hold is removed. You can optionally specify a hold duration, which preserves a mailbox item for the specified duration period. If you specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created. To preserve items that meet your specified criteria, use an In-Place Hold to create a query-based hold. For details, see [Create or Remove an In-Place Hold](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx).</span></span>
    
- <span data-ttu-id="b5665-p108">若要使用命令行管理程序将 Exchange Online 邮箱置于保留状态，您必须使用 Exchange Online PowerShell 中。有关详细信息，请参阅[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5665-p108">To use the Shell to place an Exchange Online mailbox on hold, you have to use Exchange Online PowerShell. For more information, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="b5665-p109">不支持将公用文件夹邮箱置于诉讼保留状态。必须使用就地保留来将公用文件夹置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="b5665-p109">Placing a Litigation Hold on a public folder mailbox isn't supported. You have to use In-Place Hold to place a hold on public folders.</span></span>
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="b5665-134">使用 EAC 将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b5665-134">Use the EAC to place a mailbox on Litigation Hold</span></span>
<span data-ttu-id="b5665-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-135"></span></span>

1. <span data-ttu-id="b5665-136">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="b5665-136">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="b5665-137">在用户邮箱列表中，单击您想要将置于诉讼保留状态，邮箱，然后单击**编辑**![编辑图标](media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="b5665-137">In the list of user mailboxes, click the mailbox that you want to place on Litigation Hold, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="b5665-138">在邮箱属性页上，单击**邮箱功能。**</span><span class="sxs-lookup"><span data-stu-id="b5665-138">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="b5665-139">在**诉讼保留： 已禁用**，单击**启用**以将置于诉讼保留状态的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5665-139">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span> 
    
5. <span data-ttu-id="b5665-140">在**诉讼保留**页上，输入以下可选信息：</span><span class="sxs-lookup"><span data-stu-id="b5665-140">On the **Litigation Hold** page, enter the following optional information:</span></span> 
    
  - <span data-ttu-id="b5665-p110">**诉讼保留持续时间 （天）** 使用此框可以指定当邮箱置于诉讼保留多长时间保留邮箱项目。接收或创建邮箱项目时，将从日期计算持续时间。如果将此框保留为空，项目保留无限期或直到保留被删除。使用天指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="b5665-p110">**Litigation hold duration (days)** Use this box to specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span> 
    
  - <span data-ttu-id="b5665-p111">**注释**使用此框通知用户其邮箱位于诉讼保留。如果他们正在使用 Outlook 2010 或更高版本，注释将显示在用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="b5665-p111">**Note** Use this box to inform the user their mailbox is on Litigation Hold. The note will appear in the user's mailbox if they're using Outlook 2010 or later.</span></span> 
    
  - <span data-ttu-id="b5665-p112">**URL**使用此框可以将用户定向到有关诉讼保留的详细信息的网站。如果他们使用 Outlook 2010 或更高版本，此 URL 将出现在用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b5665-p112">**URL** Use this box to direct the user to a website for more information about Litigation Hold. This URL appears in the user's mailbox if they are using Outlook 2010 or later.</span></span> 
    
6. <span data-ttu-id="b5665-149">在**诉讼保留**页上，单击**保存**，然后单击邮箱属性页上的**保存**。</span><span class="sxs-lookup"><span data-stu-id="b5665-149">Click **Save** on the **Litigation Hold** page, and then click **Save** on the mailbox properties page.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a><span data-ttu-id="b5665-150">使用命令行管理程序将邮箱无限期置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b5665-150">Use the Shell to place a mailbox on Litigation Hold indefinitely</span></span>
<span data-ttu-id="b5665-151"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-151"></span></span>

<span data-ttu-id="b5665-p113">此示例将邮箱 bsuneja@contoso.com 置于诉讼保留状态。邮箱中的项目将无限期保留或保留到删除该保留。</span><span class="sxs-lookup"><span data-stu-id="b5665-p113">This example places the mailbox bsuneja@contoso.com on Litigation Hold. Items in the mailbox are held indefinitely or until the hold is removed.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> <span data-ttu-id="b5665-154">当您将邮箱无限期置于诉讼保留状态时（不指定持续时间），将  _LitigationHoldDuration_ 属性邮箱的值设置为  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="b5665-154">When you place a mailbox on Litigation Hold indefinitely (by not specifying a duration period), the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span> 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a><span data-ttu-id="b5665-155">使用命令行管理程序将邮箱置于诉讼保留状态并将项目保留指定的持续时间</span><span class="sxs-lookup"><span data-stu-id="b5665-155">Use the Shell to place a mailbox on Litigation Hold and preserve items for a specified duration</span></span>
<span data-ttu-id="b5665-156"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-156"></span></span>

<span data-ttu-id="b5665-157">此示例将邮箱 bsuneja@contoso.com 置于诉讼保留状态，并将项目保留 2555 天（大约 7 年）。</span><span class="sxs-lookup"><span data-stu-id="b5665-157">This example places the mailbox bsuneja@contoso.com on Litigation Hold and preserves items for 2555 days (approximately 7 years).</span></span> 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a><span data-ttu-id="b5665-158">使用命令行管理程序在指定持续时间内将所有邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="b5665-158">Use the Shell to place all mailboxes on Litigation Hold for a specified duration</span></span>
<span data-ttu-id="b5665-159"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-159"></span></span>

<span data-ttu-id="b5665-p114">您的组织可能需要将所有邮箱数据保存一段指定的时间。在您将组织中的所有邮箱置于诉讼保留状态之前，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="b5665-p114">Your organization may require that all mailbox data be preserved for a specific period of time. Before you place all mailboxes in an organization on Litigation Hold, consider the following:</span></span>
  
<span data-ttu-id="b5665-162">本示例将组织中的所有用户邮箱置于诉讼保留状态，时间为 1 年（365 天）。</span><span class="sxs-lookup"><span data-stu-id="b5665-162">This example places all user mailboxes in the organization on Litigation Hold for one year (365 days).</span></span>
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

<span data-ttu-id="b5665-163">本示例使用 [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet 检索组织中的所有邮箱，指定收件人筛选器以包含所有用户邮箱，然后将邮箱列表输出到 [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet 以启用诉讼保留和保留持续时间。</span><span class="sxs-lookup"><span data-stu-id="b5665-163">The example uses the [Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) cmdlet to retrieve all mailboxes in the organization, specifies a recipient filter to include all user mailboxes, and then pipes the list of mailboxes to the [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) cmdlet to enable the Litigation Hold and hold duration.</span></span> 
  
<span data-ttu-id="b5665-164">要将所有用户邮箱置于无限期保留状态，请运行以前的命令，但不包含  _LitigationHoldDuration_ 参数。</span><span class="sxs-lookup"><span data-stu-id="b5665-164">To place all user mailboxes on an indefinite hold, run the previous command but don't include the  _LitigationHoldDuration_ parameter.</span></span> 
  
<span data-ttu-id="b5665-165">请参阅[详细信息](#moreinfo.md)部分，查看在筛选器中使用其他收件人属性以包含或排除一个或多个邮箱的示例。</span><span class="sxs-lookup"><span data-stu-id="b5665-165">See the [More information](#moreinfo.md) section for examples of using other recipient properties in a filter to include or exclude one or more mailboxes.</span></span> 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a><span data-ttu-id="b5665-166">使用命令行管理程序将邮箱从诉讼保留中删除</span><span class="sxs-lookup"><span data-stu-id="b5665-166">Use the Shell to remove a mailbox from Litigation Hold</span></span>
<span data-ttu-id="b5665-167"><a name="sectionSection5"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-167"></span></span>

<span data-ttu-id="b5665-168">此示例将邮箱 bsuneja@contoso.com 从诉讼保留中删除。</span><span class="sxs-lookup"><span data-stu-id="b5665-168">This example removes the mailbox bsuneja@contoso.com from Litigation Hold.</span></span>
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

<span data-ttu-id="b5665-169">P</span><span class="sxs-lookup"><span data-stu-id="b5665-169">P</span></span>
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b5665-170">您如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="b5665-170">How do you know this worked?</span></span>
<span data-ttu-id="b5665-171"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-171"></span></span>

<span data-ttu-id="b5665-172">要确认已成功地将邮箱置于诉讼保留状态，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="b5665-172">To verify that you have successfully placed a mailbox on Litigation Hold, do the one of the following:</span></span>
  
- <span data-ttu-id="b5665-173">在 EAC 中：</span><span class="sxs-lookup"><span data-stu-id="b5665-173">In the EAC:</span></span>
    
1. <span data-ttu-id="b5665-174">转到" **收件人**"\>" **邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="b5665-174">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="b5665-175">在用户邮箱列表中，单击您想要验证的诉讼保留设置的邮箱，然后单击**编辑**![编辑图标](media/ITPro-EAC-EditIcon.png)。</span><span class="sxs-lookup"><span data-stu-id="b5665-175">In the list of user mailboxes, click the mailbox that you want to verify Litigation Hold settings for, and then click **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>
    
3. <span data-ttu-id="b5665-176">在邮箱属性页上，单击**邮箱功能。**</span><span class="sxs-lookup"><span data-stu-id="b5665-176">On the mailbox properties page, click **Mailbox features.**</span></span>
    
4. <span data-ttu-id="b5665-177">在**诉讼保留**，验证已启用保留。</span><span class="sxs-lookup"><span data-stu-id="b5665-177">Under **Litigation hold**, verify that hold is enabled.</span></span>
    
5. <span data-ttu-id="b5665-p115">单击**查看详细信息**，以验证邮箱已发出以及由谁应答上诉讼保留时。您还可以验证或更改在可选值**诉讼保留持续时间 （天）**，**请注意**，和**URL**框。</span><span class="sxs-lookup"><span data-stu-id="b5665-p115">Click **View details** to verify when the mailbox was placed on Litigation Hold and by whom. You can also verify or change the values in the optional **Litigation hold duration (days)**, **Note**, and **URL** boxes.</span></span> 
    
- <span data-ttu-id="b5665-180">在命令行管理程序中，运行以下命令之一：</span><span class="sxs-lookup"><span data-stu-id="b5665-180">In the Shell, run one of the following commands:</span></span>
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    <span data-ttu-id="b5665-181">或者</span><span class="sxs-lookup"><span data-stu-id="b5665-181">or</span></span>
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    <span data-ttu-id="b5665-182">如果邮箱无限期置于诉讼保留状态，则将  _LitigationHoldDuration_ 邮箱属性的值设置为  `Unlimited`。</span><span class="sxs-lookup"><span data-stu-id="b5665-182">If a mailbox is placed on Litigation Hold indefinitely, the value for the  _LitigationHoldDuration_ property mailbox is set to  `Unlimited`.</span></span>
    
## <a name="more-information"></a><span data-ttu-id="b5665-183">详细信息</span><span class="sxs-lookup"><span data-stu-id="b5665-183">More information</span></span>
<span data-ttu-id="b5665-184"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="b5665-184"></span></span>

- <span data-ttu-id="b5665-185">如果您的组织要求在特定时间段内保留所有邮箱数据，则在将组织中的所有邮箱置于诉讼保留状态之前请考虑以下事项。</span><span class="sxs-lookup"><span data-stu-id="b5665-185">If your organization requires that all mailbox data has to preserved for a specific period of time, consider the following before you place all mailboxes in an organization on Litigation Hold.</span></span>
    
  - <span data-ttu-id="b5665-p116">当您使用以前的命令将组织中的所有邮箱（或匹配指定收件人筛选器的邮箱子集）置于保留状态时，只有在您运行该命令时已存在的邮箱才会置于保留状态。如果您稍后创建了新的邮箱，必须再次运行该命令以将其置于保留状态。如果您频繁地创建新邮箱，您可以将该命令作为一个计划任务，按照所需的频率运行。</span><span class="sxs-lookup"><span data-stu-id="b5665-p116">When you use the previous command to place a hold on all mailboxes in an organization (or a subset of mailboxes matching a specified recipient filter) only mailboxes that exist at the time that you run the command are placed on hold. If you create new mailboxes later, you have to run the command again to place the new mailboxes on hold. If you create new mailboxes often, you can run the command as a scheduled task as frequently as required.</span></span>
    
  - <span data-ttu-id="b5665-p117">发出的所有邮箱置于诉讼保留状态，可能会显著影响邮箱大小。组织 Exchange Server 2013 中规划足够的存储，以满足组织的保留要求。</span><span class="sxs-lookup"><span data-stu-id="b5665-p117">Placing all mailboxes on Litigation Hold can significantly impact mailbox sizes. In an Exchange Server 2013 organization, plan for adequate storage to meet your organization's preservation requirements.</span></span>
    
  - <span data-ttu-id="b5665-p118">可恢复邮件文件夹具有自己的存储限制，因此文件夹中的项目不计入邮箱存储限制。如前所述，长时间内保留邮箱数据将结果中的用户的邮箱中可恢复邮件文件夹的增长和存档。若要容纳这种增加在 Exchange Online，可恢复邮件文件夹的配额自动增加从 30 GB 为 100 GB 时您将邮箱置于诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="b5665-p118">The Recoverable Items folder has its own storage limit, so items in the folder don't count towards the mailbox storage limit. As previously explained, preserving mailbox data for a long period of time will result in growth of the Recoverable Items folder in a user's mailbox and archive. To accommodate for this increase in Exchange Online, the quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when you place a mailbox on Litigation Hold.</span></span> 
    
    <span data-ttu-id="b5665-p119">在 Exchange Server 2013，可恢复邮件文件夹的默认存储限制也是 30 GB。我们建议您定期监视以确保不会超过此限制此文件夹的大小。有关详细信息，请参阅[Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5665-p119">In Exchange Server 2013, the default storage limit for the Recoverable Items folder is also 30 GB. We recommend that you periodically monitor the size of this folder to ensure it doesn't reach the limit. For more information, see [Recoverable Items Folder](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx).</span></span>
    
- <span data-ttu-id="b5665-p120">前面的命令以将所有邮箱置于的保留使用返回的所有用户邮箱的收件人筛选器。您可以使用其他收件人的属性返回您可以通过管道到**Set-mailbox** cmdlet 以置于诉讼保留这些邮箱的特定邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="b5665-p120">The previous command to place a hold on all mailboxes uses a recipient filter that returns all user mailboxes. You can use other recipient properties to return a list of specific mailboxes that you can then pipe to the **Set-Mailbox** cmdlet to place a Litigation Hold on those mailboxes.</span></span> 
    
    <span data-ttu-id="b5665-p121">下面是根据常规用户或邮箱属性，使用 **Get-Mailbox** 和 **Get-Recipient** cmdlet 返回部分邮箱的一些示例。这些示例假设已填充相关的邮箱属性（例如  _CustomAttributeN_ 或  _Department_）。</span><span class="sxs-lookup"><span data-stu-id="b5665-p121">Here are some examples of using the **Get-Mailbox** and **Get-Recipient** cmdlets to return a subset of mailboxes based on common user or mailbox properties. These examples assume that relevant mailbox properties (such as  _CustomAttributeN_ or  _Department_) have been populated.</span></span>
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    <span data-ttu-id="b5665-p122">您可以在筛选器中使用其他用户邮箱属性来添加或排除邮箱。有关详细信息，请参阅[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5665-p122">You can use other user mailbox properties in a filter to include or exclude mailboxes. For details, see [Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx).</span></span>
    

