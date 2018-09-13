---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当不再需要保留的 Office 365 非活动邮箱内容时，可以永久删除非活动邮箱中删除该保留。后删除保留，非活动邮箱标记为删除，则在处理后将被永久删除。
ms.openlocfilehash: a7284be650d7ec6c89a6fdc43d8614603d6f1e19
ms.sourcegitcommit: 82fd4c85b952819157fbb13175c7b2dbbdff510f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965249"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="d6c34-104">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="d6c34-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="d6c34-p102">非活动邮箱用于保留以前员工的电子邮件，他/她离开组织之后。当不再需要保留的非活动邮箱内容时，可以永久删除非活动邮箱中删除该保留。另外，还有可能多个保留中可能置于非活动邮箱。例如，可能会在诉讼保留和上一个或多个就地保留放非活动邮箱。此外，Office 365 保留策略 (在 Office 365 安全性中创建&amp;合规性中心) 可能应用于非活动邮箱。您必须将其删除非活动邮箱中删除所有保留项和 Office 365 保留策略。删除保留和保留策略后，非活动邮箱标记为删除，则在处理后将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p102">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. Additionally, an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) might be applied to the inactive mailbox. You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it. After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d6c34-p103">我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="d6c34-117">请参阅[详细信息](delete-an-inactive-mailbox.md#moreinfo)部分了解从非活动邮箱删除保留后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d6c34-117">See the [More information](delete-an-inactive-mailbox.md#moreinfo) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d6c34-118">开始之前</span><span class="sxs-lookup"><span data-stu-id="d6c34-118">Before you begin</span></span>

- <span data-ttu-id="d6c34-p104">您必须使用 Exchange Online PowerShell 中，从非活动邮箱中删除诉讼保留。不能使用 Exchange 管理员中心 (EAC)。有关分步说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。您可以使用 Exchange Online PowerShell 中或 EAC 从非活动邮箱删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p104">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the Exchange admin center (EAC). For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="d6c34-p105">删除保留和删除非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱。有关详细信息，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p105">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox. For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="d6c34-p106">如果从非活动邮箱删除保留或 Office 365 保留策略和邮箱软删除邮箱保留期内已过期，则将永久删除邮箱。删除后，将无法恢复。删除保留之前，请确保您不再需要的邮箱中的内容。如果您想要重新激活非活动邮箱，则可以恢复它。有关详细信息，请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p106">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted. After it's deleted, it can't be recovered. Before you remove the hold, be sure that you no longer need the contents in the mailbox. If you want to re-activate an inactive mailbox, you can recover it. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="d6c34-130">有关非活动邮箱的详细信息，请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="d6c34-131">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="d6c34-p107">如前面所述，可能上非活动邮箱置于诉讼保留、 就地保留，或 Office 365 的保留策略。第一步是确定在非活动邮箱保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="d6c34-134">运行以下命令，显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="d6c34-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="d6c34-p108">**LitigationHoldEnabled**属性的值为**True**指示非活动邮箱位于诉讼保留。如果放置在非活动邮箱就地保留，保留项的 GUID 显示为**InPlaceHolds**属性的值。例如，两个非活动邮箱的以下结果显示诉讼保留将置于 Ann Beebe 和的两个就地保留被放置在 Pilar Pinilla。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="d6c34-p109">如果大量的就地保留被放置在非活动邮箱中，将显示不是所有就地保留 Guid。您可以运行以下命令以显示所有就地保留 Guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="d6c34-p109">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed. You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="d6c34-140">步骤 2：从非活动邮箱删除保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="d6c34-p110">在确定了非活动邮箱上设置的保留类型（以及是否存在多个保留）后，接下来是删除邮箱上的保留。如前所述，您必须删除所有保留后方可永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="d6c34-143">删除诉讼保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="d6c34-p111">如前所述，您必须使用 Windows PowerShell 从非活动邮箱删除诉讼保留。不能使用 EAC。运行以下命令以删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="d6c34-p112">若要识别非活动邮箱，最好的方法是通过其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外地指定了错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="d6c34-149">删除就地保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="d6c34-150">有两种方法可以从非活动邮箱删除就地保留：</span><span class="sxs-lookup"><span data-stu-id="d6c34-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="d6c34-151">**删除就地保留对象**如果您想要永久删除非活动邮箱是就地保留的唯一源邮箱，您可以只删除就地保留对象。</span><span class="sxs-lookup"><span data-stu-id="d6c34-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="d6c34-p113">您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="d6c34-154">**删除非活动邮箱作为源邮箱的就地保留**如果您想要保留的就地保留的其他源邮箱，您可以从的源邮箱列表中删除非活动邮箱并保留就地保留对象。</span><span class="sxs-lookup"><span data-stu-id="d6c34-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="d6c34-155">使用 EAC 删除就地保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="d6c34-p114">如果您知晓要删除的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取想要永久删除的非活动邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="d6c34-159">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="d6c34-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="d6c34-160">选择您想要删除就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="d6c34-161">在**就地电子数据展示&amp;保留**属性页上，单击**就地保留**，取消选中**选定的邮箱中的搜索查询匹配上的位置内容保留**框中，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d6c34-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="d6c34-162">在**就地电子数据展示&amp;保留**页上，再次选择就地保留命令，然后单击**删除**![删除图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="d6c34-163">在警告框中，单击**是**以删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="d6c34-164">使用 Exchange Online PowerShell 中删除就地保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="d6c34-p115">创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="d6c34-167">禁用就地保留上的该保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="d6c34-168">删除该就地保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="d6c34-169">使用 EAC 从就地保留删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="d6c34-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="d6c34-p116">如果您知晓非活动邮箱上设置的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取该邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="d6c34-173">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="d6c34-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="d6c34-174">选择放置在非活动邮箱，就地保留，然后单击**编辑**![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="d6c34-175">在**就地电子数据展示&amp;保留**属性页上，单击**源**。</span><span class="sxs-lookup"><span data-stu-id="d6c34-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="d6c34-176">在源邮箱的列表中，单击您想要删除非活动邮箱的名称，然后单击**删除**![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="d6c34-p117">单击**保存**以保存更改。将显示一条消息，告知操作已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="d6c34-179">重复步骤 1 至 6 以删除非活动邮箱上设置的其他就地保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="d6c34-180">使用 Exchange Online PowerShell 中删除非活动邮箱就地保留</span><span class="sxs-lookup"><span data-stu-id="d6c34-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="d6c34-p118">如果就地保留包含大量的源邮箱，则可能不会在 EAC 中的**源**页上列出非活动邮箱。最多 3000 邮箱时将显示在**源**页上，编辑就地保留。如果非活动邮箱不在**源**页上列出，您可以使用 Exchange Online PowerShell 中删除就地保留从。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="d6c34-p119">创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](delete-an-inactive-mailbox.md#step1) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](delete-an-inactive-mailbox.md#step1).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="d6c34-186">验证非活动邮箱是否作为就地保留的源邮箱列出。</span><span class="sxs-lookup"><span data-stu-id="d6c34-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="d6c34-p120">**注意：** 就地保留的*源*属性由其*LegacyExchangeDN*属性标识的源邮箱。因为此属性用于唯一标识非活动邮箱，使用就地保留的*源*属性有助于防止删除错误的邮箱。这还有助于避免出现问题，如果两个邮箱具有相同的别名或 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p120">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="d6c34-p121">从变量中的源邮箱列表中删除非活动邮箱。请务必使用上一步中的命令返回非活动邮箱**LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="d6c34-192">验证非活动邮箱已从变量中的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="d6c34-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="d6c34-193">使用源邮箱的更新列表（其中不包括非活动邮箱）修改就地保留。</span><span class="sxs-lookup"><span data-stu-id="d6c34-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="d6c34-194">验证非活动邮箱已从就地保留的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="d6c34-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="d6c34-195">更多信息</span><span class="sxs-lookup"><span data-stu-id="d6c34-195">More information</span></span>

- <span data-ttu-id="d6c34-p122">**非活动邮箱是一种软删除邮箱。** 在 Exchange Online 中，软删除邮箱是已删除，但可以在特定的保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着正在软删除 30 天内，可以恢复邮箱。30 天后软删除邮箱标记为永久删除，并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="d6c34-p123">**删除非活动邮箱的保留项后，会发生什么情况？** 邮箱视为其他软删除邮箱和 30 天软删除邮箱保留期过后标记为永久删除。此保留期启动邮箱首先建立时处于非活动状态的日期。此日期称为软删除日期，是已删除相应的 Office 365 用户帐户或使用**Remove-mailbox** cmdlet 删除 Exchange Online 邮箱时的日期。软删除日期不是您在其删除保留项的日期。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="d6c34-p124">**立即后删除该保留永久删除非活动邮箱？** 如果非活动邮箱的软删除日期已超过 30 天，只要删除保留，不会永久删除邮箱。邮箱将标记为永久删除，并删除的下次处理。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="d6c34-p125">**软删除邮箱保留期如何影响非活动邮箱？** 如果非活动邮箱的软删除日期为 30 天保留已删除的日期之前，邮箱为永久删除标记。但是，如果非活动邮箱已最近 30 天内的软删除日期，并且您删除保留，直到软删除邮箱保留期到期，则可以恢复邮箱。有关详细信息，请参阅[删除或还原 Exchange 在 Online 用户邮箱](https://go.microsoft.com/fwlink/?linkid=856835)。软删除邮箱保留期过后，您已按照非活动邮箱恢复过程。有关详细信息，请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p125">**How does the soft-deleted mailbox retention period affect inactive mailboxes?** If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion. But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires. For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox. For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="d6c34-p126">**保留被删除之后如何显示有关非活动邮箱的信息？** 保留被删除和非活动邮箱恢复为软删除邮箱后，它不会返回*InactiveMailboxOnly*参数使用**Get-mailbox** cmdlet。但您可以通过使用**Get-mailbox SoftDeletedMailbox**命令显示有关邮箱的信息。例如：</span><span class="sxs-lookup"><span data-stu-id="d6c34-p126">**How do you display information about an inactive mailbox after the hold is removed?** After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet. But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command. For example:</span></span> 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
<span data-ttu-id="d6c34-p127">在上述示例中， *WhenSoftDeleted*属性标识的软删除日期，它在本例中为 2014 年 10 月 30 日。如果此软删除邮箱以前为其保留已删除非活动邮箱，它将永久删除 30 天后*WhenSoftDeleted*属性的值。在这种情况下，邮箱之后 2014 年 11 月 30 日永久删除。</span><span class="sxs-lookup"><span data-stu-id="d6c34-p127">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014. If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property. In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

