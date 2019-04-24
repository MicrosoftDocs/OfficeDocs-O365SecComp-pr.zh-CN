---
title: 删除 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: 当不再需要保留 Office 365 非活动邮箱的内容时, 可以通过删除保留永久删除非活动邮箱。 删除保留后, 非活动邮箱将标记为删除, 并在处理后被永久删除。
ms.openlocfilehash: f1aa29b0e40d02e4b6450202c0b2a34ae3075677
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257102"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="506fb-104">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="506fb-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="506fb-105">非活动邮箱用于在之前的员工离开公司之后保留其电子邮件。</span><span class="sxs-lookup"><span data-stu-id="506fb-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="506fb-106">如果您不再需要保留非活动邮箱的内容，可以通过删除保留永久性地删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="506fb-107">此外，还可以对非活动邮箱设置多个保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="506fb-108">例如，非活动邮箱上可以设置诉讼保留以及一个或多个就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="506fb-109">此外, office 365 保留策略 (在 office 365 或 Microsoft 365 的安全性和合规性中心中创建) 可能会应用于非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="506fb-110">您必须从非活动邮箱中删除所有保留和 Office 365 保留策略, 才能将其删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="506fb-111">删除保留和保留策略后, 非活动邮箱将标记为删除, 并在处理之后永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="506fb-112">我们推迟了最后期限，在 2017 年 7 月 1 后，仍可通过新建就地保留创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-112">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive.</span></span> <span data-ttu-id="506fb-113">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="506fb-113">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="506fb-114">在这段时间, 仅可使用诉讼保留和 Office 365 保留策略来创建非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-114">At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox.</span></span> <span data-ttu-id="506fb-115">不过，处于就地保留的现有非活动邮箱仍受支持，可以继续管理这些非活动邮箱的就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-115">However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes.</span></span> <span data-ttu-id="506fb-116">这包括更改就地保留的持续时间，以及通过删除就地保留来永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-116">This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
<span data-ttu-id="506fb-117">请参阅[More information](#more-information)部分了解从非活动邮箱删除保留后会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="506fb-117">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="506fb-118">开始之前</span><span class="sxs-lookup"><span data-stu-id="506fb-118">Before you begin</span></span>

- <span data-ttu-id="506fb-119">您必须使用 Exchange Online PowerShell 从非活动邮箱删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-119">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="506fb-120">不能使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="506fb-120">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="506fb-121">有关分步说明, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="506fb-121">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="506fb-122">您可以使用 Exchange Online PowerShell 或 EAC 从非活动邮箱中删除就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-122">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="506fb-123">在删除保留设置和非活动邮箱之前，您可以将非活动邮箱的内容复制到另一个邮箱中。</span><span class="sxs-lookup"><span data-stu-id="506fb-123">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="506fb-124">有关详细信息, 请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="506fb-124">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="506fb-125">如果从非活动邮箱中删除保留策略或 Office 365 保留策略, 并且邮箱的软删除邮箱保留期已过期, 则邮箱将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-125">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="506fb-126">在此邮箱删除后，您将无法恢复。</span><span class="sxs-lookup"><span data-stu-id="506fb-126">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="506fb-127">在删除保留设置之前，请确保您不再需要此邮箱中的内容。</span><span class="sxs-lookup"><span data-stu-id="506fb-127">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="506fb-128">如果您想重新激活非活动邮箱，则可以恢复它。</span><span class="sxs-lookup"><span data-stu-id="506fb-128">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="506fb-129">有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="506fb-129">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="506fb-130">有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="506fb-130">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="506fb-131">第 1 步：识别非活动邮箱上设置的保留</span><span class="sxs-lookup"><span data-stu-id="506fb-131">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="506fb-132">如前面所述, 诉讼保留、就地保留或 Office 365 保留策略可能位于非活动邮箱上。</span><span class="sxs-lookup"><span data-stu-id="506fb-132">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="506fb-133">第一步是识别非活动邮箱上设置的保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-133">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="506fb-134">运行以下命令，显示组织中所有非活动邮箱的保留信息。</span><span class="sxs-lookup"><span data-stu-id="506fb-134">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="506fb-135">如果 **LitigationHoldEnabled** 属性的值为 **True** ，则表示非活动邮箱被置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="506fb-135">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="506fb-136">如果非活动邮箱被置于就地保留状态，则保留的 GUID 会显示为 **InPlaceHolds** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="506fb-136">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="506fb-137">例如，以下两个非活动邮箱的结果显示 Ann Beebe 设置的是诉讼保留，而 Pilar Pinilla 设置了两个就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-137">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="506fb-138">如果非活动邮箱上设置了许多就地保留，则不会显示所有的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="506fb-138">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="506fb-139">您可以运行以下命令来显示所有就地保留 guid:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="506fb-139">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="506fb-140">步骤 2：从非活动邮箱删除保留</span><span class="sxs-lookup"><span data-stu-id="506fb-140">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="506fb-p110">在确定了非活动邮箱上设置的保留类型（以及是否存在多个保留）后，接下来是删除邮箱上的保留。如前所述，您必须删除所有保留后方可永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="506fb-143">删除诉讼保留</span><span class="sxs-lookup"><span data-stu-id="506fb-143">Remove a Litigation Hold</span></span>

<span data-ttu-id="506fb-p111">如前所述，您必须使用 Windows PowerShell 从非活动邮箱删除诉讼保留。不能使用 EAC。运行以下命令以删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="506fb-p112">若要识别非活动邮箱，最好的方法是通过其可分辨名称或 Exchange GUID 值。使用下列值之一有助于防止意外地指定了错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="506fb-149">删除就地保留</span><span class="sxs-lookup"><span data-stu-id="506fb-149">Remove In-Place Holds</span></span>

 <span data-ttu-id="506fb-150">有两种方法可以从非活动邮箱删除就地保留：</span><span class="sxs-lookup"><span data-stu-id="506fb-150">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="506fb-151">**删除就地保留对象**如果要永久删除的非活动邮箱是就地保留的唯一源邮箱, 则只需删除就地保留对象即可。</span><span class="sxs-lookup"><span data-stu-id="506fb-151">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="506fb-p113">您必须先禁用该保留，然后才能删除就地保留对象。如果尝试删除启用了该保留的就地保留对象，您将收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="506fb-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="506fb-154">**删除非活动邮箱作为就地保留的源邮箱**如果要保留对就地保留的其他源邮箱, 可以从源邮箱列表中删除非活动邮箱, 并保留就地保留对象。</span><span class="sxs-lookup"><span data-stu-id="506fb-154">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="506fb-155">使用 EAC 删除就地保留</span><span class="sxs-lookup"><span data-stu-id="506fb-155">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="506fb-p114">如果您知晓要删除的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取想要永久删除的非活动邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="506fb-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="506fb-159">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="506fb-159">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="506fb-160">选择要删除的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。</span><span class="sxs-lookup"><span data-stu-id="506fb-160">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="506fb-161">在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**就地保留**", 取消选中 "**将与所选邮箱中的搜索查询匹配的内容置于保留**状态" 框中, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="506fb-161">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="506fb-162">在 "**就地电子数据展示&amp;保留**" 页上, 再次选择就地保留, 然后单击 "**删除**![删除图标](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)"。</span><span class="sxs-lookup"><span data-stu-id="506fb-162">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="506fb-163">在警告框中，单击“是”\*\*\*\* 删除该就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-163">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="506fb-164">使用 Exchange Online PowerShell 删除就地保留</span><span class="sxs-lookup"><span data-stu-id="506fb-164">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="506fb-p115">创建一个变量，其中包含您想要删除的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="506fb-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="506fb-167">禁用就地保留上的该保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-167">Disable the hold on the In-Place Hold.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. <span data-ttu-id="506fb-168">删除该就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-168">Delete the In-Place Hold.</span></span>
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="506fb-169">使用 EAC 从就地保留删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="506fb-169">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="506fb-p116">如果您知晓非活动邮箱上设置的就地保留的名称，则可前往下一步。否则，请运行以下命令以获取该邮箱上设置的就地保留的名称。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="506fb-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. <span data-ttu-id="506fb-173">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="506fb-173">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="506fb-174">选择非活动邮箱上放置的就地保留, 然后单击 "**编辑** ![编辑图标](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)"。</span><span class="sxs-lookup"><span data-stu-id="506fb-174">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="506fb-175">在 "**就地电子数据展示&amp;保留**属性" 页上, 单击 "**源**"。</span><span class="sxs-lookup"><span data-stu-id="506fb-175">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="506fb-176">在源邮箱列表中, 单击要删除的非活动邮箱的名称, 然后单击 "**删除**![删除图标](media/adf01106-cc79-475c-8673-065371c1897b.gif)"。</span><span class="sxs-lookup"><span data-stu-id="506fb-176">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="506fb-177">单击“保存”\*\*\*\* 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="506fb-177">Click **Save** to save the change.</span></span> <span data-ttu-id="506fb-178">这将显示一条消息，提示已成功完成该操作。</span><span class="sxs-lookup"><span data-stu-id="506fb-178">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="506fb-179">重复步骤 1 至 6 以删除非活动邮箱上设置的其他就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-179">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="506fb-180">使用 Exchange Online PowerShell 从就地保留中删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="506fb-180">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="506fb-181">如果就地保留中包含大量的源邮箱，则非活动邮箱有可能不会列在 EAC 的“源”页面上\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="506fb-181">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="506fb-182">在编辑就地保留时，“源”\*\*\*\* 页面上最多显示 3000 个邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-182">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="506fb-183">如果未在 "**源**" 页上列出非活动邮箱, 则可以使用 Exchange Online PowerShell 将其从就地保留中删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-183">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="506fb-p119">创建一个变量，其中包含非活动邮箱上设置的就地保留的属性。使用您在[步骤 1：识别非活动邮箱上设置的保留](#step-1-identify-the-holds-on-an-inactive-mailbox) 中获得的就地保留 GUID。</span><span class="sxs-lookup"><span data-stu-id="506fb-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. <span data-ttu-id="506fb-186">验证非活动邮箱是否作为就地保留的源邮箱列出。</span><span class="sxs-lookup"><span data-stu-id="506fb-186">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
```
  $InPlaceHold.Sources
```

   <span data-ttu-id="506fb-187">**注意:** 就地\*\* 保留的 source 属性通过其*LegacyExchangeDN*属性标识源邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-187">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="506fb-188">由于此属性唯一标识非活动邮箱, 因此使用就地保留中的*源*属性有助于防止删除错误的邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-188">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="506fb-189">如果两个邮箱具有相同的别名或 SMTP 地址，这还有助于避免出现问题。</span><span class="sxs-lookup"><span data-stu-id="506fb-189">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="506fb-190">从变量中的源邮箱列表删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-190">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="506fb-191">请务必使用上一步中的命令返回的非活动邮箱的**LegacyExchangeDN** 。</span><span class="sxs-lookup"><span data-stu-id="506fb-191">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. <span data-ttu-id="506fb-192">验证非活动邮箱已从变量中的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
```
  $InPlaceHold.Sources
```

5. <span data-ttu-id="506fb-193">使用源邮箱的更新列表（其中不包括非活动邮箱）修改就地保留。</span><span class="sxs-lookup"><span data-stu-id="506fb-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. <span data-ttu-id="506fb-194">验证非活动邮箱已从就地保留的源邮箱列表中删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a><span data-ttu-id="506fb-195">详细信息</span><span class="sxs-lookup"><span data-stu-id="506fb-195">More information</span></span>

- <span data-ttu-id="506fb-196">**非活动邮箱是一种软删除邮箱。**</span><span class="sxs-lookup"><span data-stu-id="506fb-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="506fb-197">在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="506fb-198">Exchange Online 中的软删除邮箱保留期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="506fb-198">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="506fb-199">这意味着该邮箱可以在软删除后 30 天内进行恢复。</span><span class="sxs-lookup"><span data-stu-id="506fb-199">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="506fb-200">30 天后，软删除邮箱将标记为永久删除并且无法恢复。</span><span class="sxs-lookup"><span data-stu-id="506fb-200">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="506fb-201">**如果删除非活动邮箱的保留设置，后面会怎么样？**</span><span class="sxs-lookup"><span data-stu-id="506fb-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="506fb-202">系统会将此邮箱与其他软删除邮箱视为一类，并在 30 天软删除邮箱保留期过期后将其标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="506fb-203">此保留期的起始日以该邮箱初次变为非活动状态的日期为准。</span><span class="sxs-lookup"><span data-stu-id="506fb-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="506fb-204">此日期称为软删除日期, 即在删除相应的 Office 365 用户帐户时, 或者在使用**删除邮箱**cmdlet 删除 Exchange Online 邮箱时的日期。</span><span class="sxs-lookup"><span data-stu-id="506fb-204">This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="506fb-205">软删除日期不是您删除保留的日期。</span><span class="sxs-lookup"><span data-stu-id="506fb-205">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="506fb-206">**在您删除非活动邮箱的保留设置后，系统会立即永久删除此邮箱吗？**</span><span class="sxs-lookup"><span data-stu-id="506fb-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="506fb-207">如果非活动邮箱的软删除日期是在 30 天之前，则系统不会在您删除保留设置后立即永久删除此邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-207">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="506fb-208">该邮箱将标记为永久删除，并在下次处理时删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-208">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="506fb-209">**软删除邮箱保留期对非活动邮箱有何影响？**</span><span class="sxs-lookup"><span data-stu-id="506fb-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="506fb-210">如果非活动邮箱的软删除日期距离之后的保留设置删除日期有 30 多天，则系统会将此邮箱标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="506fb-211">不过，如果距离非活动邮箱的软删除日期还不到 30 天并且您删除保留设置，则您可以在软删除邮箱保留期过期之前恢复此邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="506fb-212">有关详细信息, 请参阅[删除或还原 Exchange Online 中的用户邮箱](https://go.microsoft.com/fwlink/?linkid=856835)。</span><span class="sxs-lookup"><span data-stu-id="506fb-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="506fb-213">在软删除邮箱保留期过期后，您可以按照相关步骤操作，恢复非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-213">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="506fb-214">有关详细信息, 请参阅[恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="506fb-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="506fb-215">**在删除保留设置后，如何显示非活动邮箱的相关信息？**</span><span class="sxs-lookup"><span data-stu-id="506fb-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="506fb-216">在删除保留并将非活动邮箱还原为软删除邮箱后, 不会通过将*InactiveMailboxOnly*参数与**Get 邮箱**cmdlet 一起使用来返回该邮箱。</span><span class="sxs-lookup"><span data-stu-id="506fb-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="506fb-217">不过, 您可以使用**SoftDeletedMailbox**命令显示有关邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="506fb-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="506fb-218">例如：</span><span class="sxs-lookup"><span data-stu-id="506fb-218">For example:</span></span> 
    
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
  
<span data-ttu-id="506fb-219">在上面的示例中, *WhenSoftDeleted*属性标识软删除日期, 在此示例中为2014年10月30日。</span><span class="sxs-lookup"><span data-stu-id="506fb-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="506fb-220">如果此软删除邮箱之前已删除保留的非活动邮箱, 则它将在*WhenSoftDeleted*属性值之后的30天内永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="506fb-221">在本例中，该邮箱将在 2014 年 11 月 30 日之后永久删除。</span><span class="sxs-lookup"><span data-stu-id="506fb-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

