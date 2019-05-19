---
title: 将就地保留置于 Exchange Online 中的软删除邮箱上
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。
ms.openlocfilehash: ce4121e6187a765b5a9e23d6e6e11d8cc2640161
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157274"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="acd4a-104">将就地保留置于 Exchange Online 中的软删除邮箱上</span><span class="sxs-lookup"><span data-stu-id="acd4a-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="acd4a-p102">了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="acd4a-107">我们已推迟在 Exchange Online 中创建新的就地保留的截止时间 (在 Office 365 和 Exchange Online 独立计划中)。</span><span class="sxs-lookup"><span data-stu-id="acd4a-107">We've postponed the deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans).</span></span> <span data-ttu-id="acd4a-108">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="acd4a-108">But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="acd4a-109">作为使用就地保留的替代方法, 可以使用安全 & 合规性中心中的[电子数据展示案例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留策略](https://go.microsoft.com/fwlink/?linkid=827811)。</span><span class="sxs-lookup"><span data-stu-id="acd4a-109">As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Security & Compliance Center.</span></span> <span data-ttu-id="acd4a-110">After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported.</span><span class="sxs-lookup"><span data-stu-id="acd4a-110">After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported.</span></span> <span data-ttu-id="acd4a-111">And, you'll still be able to place mailboxes on Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="acd4a-111">And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="acd4a-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="acd4a-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="acd4a-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="acd4a-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="acd4a-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="acd4a-114">What can you do?</span></span> <span data-ttu-id="acd4a-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="acd4a-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="acd4a-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="acd4a-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="acd4a-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="acd4a-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="acd4a-118">将邮箱设为非活动状态后, 可以使用 Exchange Online 中的就地电子数据展示、安全 & 合规性中心中的内容搜索或 SharePoint Online 中的电子数据展示中心来搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="acd4a-p105">在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着该邮箱可以在删除后 30 天内进行恢复（或变为非活动邮箱）。30 天后，软删除邮箱将标记为永久删除并且无法恢复或变为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="acd4a-123">开始之前</span><span class="sxs-lookup"><span data-stu-id="acd4a-123">Before you begin</span></span>

- <span data-ttu-id="acd4a-124">您必须在 Windows PowerShell 中使用**new-mailboxsearch** cmdlet 在软删除的邮箱上放置就地保留。</span><span class="sxs-lookup"><span data-stu-id="acd4a-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="acd4a-125">不能使用 SharePoint Online 中的 Exchange 管理中心 (EAC) 或电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="acd4a-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="acd4a-126">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="acd4a-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="acd4a-127">运行以下命令获取组织中软删除邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="acd4a-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="acd4a-128">有关非活动邮箱的详细信息, 请参阅[Office 365 中的非活动邮箱概述](inactive-mailboxes-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="acd4a-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="acd4a-129">将就地保留置于软删除邮箱以使其变为非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="acd4a-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="acd4a-130">使用**new-mailboxsearch** cmdlet 可将软删除的邮箱设置为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="acd4a-131">有关详细信息，请参阅 [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="acd4a-131">For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="acd4a-132">创建包含软删除邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="acd4a-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
   ```
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="acd4a-133">在上一个命令中, 使用**DistinguishedName**或**ExchangeGuid**属性的值来标识软删除的邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="acd4a-134">这些属性对于组织中的每个邮箱都是唯一的，但活动邮箱和软删除邮箱可能具有相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="acd4a-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="acd4a-p109">创建就地保留并将其置于软删除邮箱上。在此示例中，未指定保留持续时间。这意味着项目将被无限期保留或一直保留到将该保留从非活动邮箱中删除为止。</span><span class="sxs-lookup"><span data-stu-id="acd4a-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```
   <span data-ttu-id="acd4a-p110">还可以在创建就地保留时指定保留持续时间。此示例保留非活动邮箱中的项目近 7 年。</span><span class="sxs-lookup"><span data-stu-id="acd4a-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
   ```
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="acd4a-140">一段时间后，运行下列命令之一，验证软删除邮箱是否为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="acd4a-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="acd4a-141">或</span><span class="sxs-lookup"><span data-stu-id="acd4a-141">Or</span></span>
    
   ```
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="acd4a-142">详细信息</span><span class="sxs-lookup"><span data-stu-id="acd4a-142">More information</span></span>

<span data-ttu-id="acd4a-p111">在将软删除邮箱变为非活动邮箱后，有多种方法可以管理该邮箱。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="acd4a-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="acd4a-145">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="acd4a-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)
    
- [<span data-ttu-id="acd4a-146">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="acd4a-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)
    
- [<span data-ttu-id="acd4a-147">还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="acd4a-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)
    
- <span data-ttu-id="acd4a-148">[删除非活动邮箱](delete-an-inactive-mailbox.md)(通过删除保留)</span><span class="sxs-lookup"><span data-stu-id="acd4a-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
