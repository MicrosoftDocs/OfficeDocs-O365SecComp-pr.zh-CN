---
title: 将就地保留置于 Exchange Online 中的软删除邮箱上
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
description: 了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。
ms.openlocfilehash: 226929764fe39b99f526301029d4a41e2fa486cc
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027609"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="cda2f-104">将就地保留置于 Exchange Online 中的软删除邮箱上</span><span class="sxs-lookup"><span data-stu-id="cda2f-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="cda2f-p102">了解如何为软删除邮箱创建就地保留，以将其变为非活动邮箱并保留其内容。然后可以使用 Microsoft 电子数据展示工具来搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cda2f-p103">我们已推迟创建新的就地保留在 Exchange Online （在 Office 365 和 Exchange Online 独立计划） 的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。作为使用就地保留的替代方法，您可以使用[电子数据展示事例](https://go.microsoft.com/fwlink/?linkid=780738)或[保留策略](https://go.microsoft.com/fwlink/?linkid=827811)在 Office 365 安全性&amp;合规性中心。我们停用新就地保留后，您仍可以修改现有的就地保留，并创建新的就地保留在 Exchange Server 2013 和 Exchange 混合部署仍会支持。然后您将仍然能够将邮箱置于诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds in Exchange Online (in Office 365 and Exchange Online standalone plans). But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. As an alternative to using In-Place Holds, you can use [eDiscovery cases](https://go.microsoft.com/fwlink/?linkid=780738) or [retention policies](https://go.microsoft.com/fwlink/?linkid=827811) in the Office 365 Security &amp; Compliance Center. After we decommission new In-Place Holds, you'll still be able to modify existing In-Place Holds, and creating new In-Place Holds in Exchange Server 2013 and Exchange hybrid deployments will still be supported. And, you'll still be able to place mailboxes on Litigation Hold.</span></span> 
  
<span data-ttu-id="cda2f-p104">您可能必须其中联系人已离开组织和其相应的用户帐户和邮箱已删除的情况。然后，您认识到需要保留的邮箱中的信息。您可以做什么？如果没有过期的已删除的邮箱保留期，您可以将 （称为软删除邮箱） 的已删除邮箱置于就地保留，并使其非活动邮箱。*非活动邮箱*用于保留以前员工的电子邮件，他/她离开组织之后。非活动邮箱的内容会保留的已就地保留的持续时间置于软删除邮箱时已处于非活动状态。非活动邮箱后，您可以在 Exchange Online 中，Office 365 安全性内容搜索使用就地电子数据展示搜索邮箱&amp;合规性中心或 SharePoint Online 中的电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p104">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox. An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Office 365 Security &amp; Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cda2f-p105">在 Exchange Online 中，软删除邮箱是指已删除但可以在特定保留期内恢复的邮箱。Exchange Online 中的软删除邮箱保留期为 30 天。这意味着该邮箱可以在删除后 30 天内进行恢复（或变为非活动邮箱）。30 天后，软删除邮箱将标记为永久删除并且无法恢复或变为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="cda2f-123">准备工作</span><span class="sxs-lookup"><span data-stu-id="cda2f-123">Before you begin</span></span>
<span data-ttu-id="cda2f-124"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="cda2f-124"></span></span>

- <span data-ttu-id="cda2f-p106">您必须使用 Windows PowerShell 中的**New-mailboxsearch** cmdlet 可以将软删除邮箱置于就地保留。不能使用 Exchange 管理员中心 (EAC) 或 SharePoint Online 中的电子数据展示中心。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 
    
- <span data-ttu-id="cda2f-127">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="cda2f-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="cda2f-128">运行以下命令获取组织中软删除邮箱的标识信息。</span><span class="sxs-lookup"><span data-stu-id="cda2f-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 
    
  ```
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="cda2f-129">有关非活动邮箱的详细信息，请参阅 [Exchange Online 中的非活动邮箱](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cda2f-129">For more information about inactive mailboxes, see [Inactive mailboxes in Exchange Online](http://technet.microsoft.com/library/2f2948c5-1c5a-4643-865c-b36e4ac1414b.aspx).</span></span>
    
## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="cda2f-130">将就地保留置于软删除邮箱以使其变为非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="cda2f-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>
<span data-ttu-id="cda2f-131"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="cda2f-131"></span></span>

<span data-ttu-id="cda2f-p107">使用 **New-MailboxSearch** cmdlet 将软删除邮箱变为非活动邮箱。有关详细信息，请参阅 [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](http://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="cda2f-134">创建包含软删除邮箱的属性的变量。</span><span class="sxs-lookup"><span data-stu-id="cda2f-134">Create a variable that contains the properties of the soft-deleted mailbox.</span></span> 
    
  ```
  $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
  ```

    > [!IMPORTANT]
    > <span data-ttu-id="cda2f-p108">在上一命令中，使用**DistinguishedName**或**ExchangeGuid**属性的值标识软删除邮箱。这些属性是唯一的组织中的每个邮箱，而可以主动邮箱和软删除邮箱可能具有的相同的主 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="cda2f-p109">创建就地保留并将其置于软删除邮箱上。在此示例中，未指定保留持续时间。这意味着项目将被无限期保留或一直保留到将该保留从非活动邮箱中删除为止。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
  
  ```

    <span data-ttu-id="cda2f-p110">还可以在创建就地保留时指定保留持续时间。此示例保留非活动邮箱中的项目近 7 年。</span><span class="sxs-lookup"><span data-stu-id="cda2f-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>
    
  ```
  New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
  ```

3. <span data-ttu-id="cda2f-142">一段时间后，运行下列命令之一，验证软删除邮箱是否为非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="cda2f-142">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly
  ```

    <span data-ttu-id="cda2f-143">或</span><span class="sxs-lookup"><span data-stu-id="cda2f-143">Or</span></span>
    
  ```
  Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
  ```

## <a name="more-information"></a><span data-ttu-id="cda2f-144">详细信息</span><span class="sxs-lookup"><span data-stu-id="cda2f-144">More information</span></span>
<span data-ttu-id="cda2f-145"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="cda2f-145"></span></span>

<span data-ttu-id="cda2f-p111">在将软删除邮箱变为非活动邮箱后，有多种方法可以管理该邮箱。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="cda2f-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="cda2f-148">在 Exchange Online 中更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="cda2f-148">Change the hold duration for an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/96eb634e-af2f-454e-8014-b698396811c4.aspx)
    
- [<span data-ttu-id="cda2f-149">恢复 Exchange Online 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="cda2f-149">Recover an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/283838b4-66ba-4c34-b221-e1a3875e1d29.aspx)
    
- [<span data-ttu-id="cda2f-150">还原 Exchange Online 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="cda2f-150">Restore an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/1fb02feb-49e5-4485-aec5-9f1537b772b6.aspx)
    
- [<span data-ttu-id="cda2f-151">从 Exchange Online 中的非活动邮箱删除保留</span><span class="sxs-lookup"><span data-stu-id="cda2f-151">Remove a hold from an inactive mailbox in Exchange Online</span></span>](http://technet.microsoft.com/library/930a98c3-cd81-4aaa-8e22-19714cb2b731.aspx)
    

