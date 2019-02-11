---
title: 创建和管理 Office 365 中的非活动邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: 通过将保持或 Office 365 保留策略应用于邮箱，然后删除相应的 Office 365 用户帐户，您可以在 Office 365 中创建非活动邮箱。非活动邮箱中的项目，将保留其进行非活动状态之前对其应用保留或保留策略的持续时间内。若要永久删除非活动邮箱，只需删除保留或保留策略。
ms.openlocfilehash: de67068ded30f63e46a8a94c1030d45a12b56a2e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29740834"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a><span data-ttu-id="9d23c-105">创建和管理 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-105">Create and manage inactive mailboxes in Office 365</span></span>

<span data-ttu-id="9d23c-p102">Office 365 使您可以保留已删除邮箱的内容。此功能称为[非活动邮箱](inactive-mailboxes-in-office-365.md)。非活动邮箱，您可以在它们离开组织后保留以前员工的电子邮件。诉讼保留或 Office 365 保留策略时，邮箱变为非活动状态 (在 Office 365 安全性中创建&amp;合规性中心) 中删除相应的 Office 365 用户帐户之前应用于邮箱。非活动邮箱的内容将保留在邮箱发出，已处于非活动状态的保留项的持续时间。这允许管理员、 合规部主管和记录管理者中安全使用内容搜索&amp;合规性中心搜索和导出的非活动邮箱内容。非活动邮箱无法接收电子邮件和您的组织共享的通讯簿或其他列表中未显示。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p102">Office 365 makes it possible for you to retain the contents of deleted mailboxes. This feature is called [inactive mailboxes](inactive-mailboxes-in-office-365.md). Inactive mailboxes allow you to retain former employees' email after they leave your organization. A mailbox becomes inactive when a Litigation Hold or an Office 365 retention policy (created in the Office 365 Security &amp; Compliance Center) is applied to the mailbox before the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. This allows administrators, compliance officers, and records managers to use Content Search in the Security &amp; Compliance Center to search and export the contents of an inactive mailbox. Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d23c-p103">我们已推迟创建新的就地保留进行非活动邮箱的 2017 年 7 月 1，最后期限。但今年或早期明年，您将无法创建新的就地保留在 Exchange Online。此时，仅诉讼保留和 Office 365 的保留策略可用于创建非活动邮箱。但是，仍会支持现有的非活动邮箱上就地保留的并且您可以继续管理非活动邮箱上就地保留。这包括更改的就地保留持续时间，并通过删除就地保留中永久删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="9d23c-118">准备工作</span><span class="sxs-lookup"><span data-stu-id="9d23c-118">Before you begin</span></span>

- <span data-ttu-id="9d23c-p104">若要使非活动邮箱，必须将它分配的 Exchange Online 计划 2 许可证，以便诉讼保留或 Office 365 保留策略可应用于邮箱被删除之前。Exchange Online 计划 2 许可证是 Office 365 企业版 E3 和 E5 订阅的一部分。如果邮箱已分配的 Exchange Online 计划 1 许可证 （它是 Office 365 企业版 E1 订阅的一部分），您将需要以便保留可应用于邮箱被删除之前将其分配单独的 Exchange Online Archiving 许可证。有关详细信息，请参阅[Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p104">To make a mailbox inactive, it must be assigned an Exchange Online Plan 2 license so that a Litigation Hold or an Office 365 retention policy can be applied to the mailbox before it's deleted. Exchange Online Plan 2 licenses are part of an Office 365 Enterprise E3 and E5 subscriptions. If a mailbox is assigned an Exchange Online Plan 1 license (which is part of an Office 365 Enterprise E1 subscription), you would have to assign it a separate Exchange Online Archiving license so that a hold can be applied to the mailbox before it's deleted. For more information, see [Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153).</span></span>
    
- <span data-ttu-id="9d23c-p105">删除相应的 Office 365 用户帐户后，将可与 Exchange Online 的已删除邮箱关联的许可证。然后可以[将对业务的 Office 365 中的用户的许可证分配](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)给其他用户。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p105">The license associated with the deleted Exchange Online mailbox will be available after you delete the corresponding Office 365 user account. You can then [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) to another user.</span></span> 
    
- <span data-ttu-id="9d23c-p106">如果诉讼保留或 Office 365 保留策略不应用于邮箱被删除之前，邮箱的内容不会保留或可供搜索。但是，可以删除，30 天内恢复已删除的邮箱的邮箱，其内容将被永久删除 30 天后如果它不可恢复。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p106">If a Litigation Hold or an Office 365 retention policy isn't applied to a mailbox before it's deleted, the contents of the mailbox won't be retained or discoverable. However, the deleted mailbox can be recovered within 30 days of deletion, but the mailbox and its contents will be permanently deleted after 30 days if it isn't recovered.</span></span>
    
- <span data-ttu-id="9d23c-p107">有关诉讼保留的详细信息，请参阅[就地保留和诉讼保留](https://go.microsoft.com/fwlink/p/?LinkId=846124)。有关 Office 365 中安全性的保留策略的详细信息&amp;合规性中心，请参阅[Overview of Office 365 中的保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p107">For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). For more information about Office 365 retention policies in the Security &amp; Compliance Center, see [Overview of retention policies in Office 365](retention-policies.md).</span></span>
  
## <a name="create-an-inactive-mailbox"></a><span data-ttu-id="9d23c-129">创建非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-129">Create an inactive mailbox</span></span>

<span data-ttu-id="9d23c-p108">使非活动邮箱涉及两个步骤： 1） 发出邮箱诉讼保留或将 Office 365 保留策略应用于，和 2） 删除邮箱或相应的 Office 365 用户帐户。邮箱处于非活动状态后，将保留其内容，直到删除保留或保留策略。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p108">Making a mailbox inactive involves two steps: 1) placing the mailbox on Litigation Hold or applying an Office 365 retention policy to it, and 2) deleting the mailbox or corresponding Office 365 user account. After the mailbox is inactive, its contents are retained until the hold or retention policy is removed.</span></span>
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a><span data-ttu-id="9d23c-132">步骤 1： 将邮箱置于诉讼保留或 Office 365 保留策略应用</span><span class="sxs-lookup"><span data-stu-id="9d23c-132">Step 1: Place a mailbox on Litigation Hold or apply an Office 365 retention policy</span></span>

<span data-ttu-id="9d23c-p109">将邮箱置于诉讼保留或将 Office 365 保留策略应用将被删除之前保留的邮箱中的内容。两种类型的保留将保留所有邮箱内容，包括已删除的项目和已修改的项目的原始版本。为指定的时间段，或者直到取消，永久删除非活动邮箱中删除应用于非活动邮箱的保留或保留策略在非活动邮箱中保留已删除和修改项目。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p109">Placing a mailbox on Litigation Hold or applying an Office 365 retention policy retains the contents in the mailbox before it's deleted. Both types of holds will retain all mailbox content, including deleted items and original versions of modified items. Deleted and modified items are retained in the inactive mailbox for a specified period, or until you permanently delete the inactive mailbox by removing the hold or retention policy that's applied to the inactive mailbox.</span></span>
  
<span data-ttu-id="9d23c-136">如果保留已置于邮箱，或者已应用于邮箱的 Office 365 保留策略，您只需执行操作是删除相应的 Office 365 用户帐户，如在步骤 2 中所述。</span><span class="sxs-lookup"><span data-stu-id="9d23c-136">If a hold is already placed on a mailbox, or if an Office 365 retention policy is already applied to a mailbox, then all you have to do is delete the corresponding Office 365 user account as explained in Step 2.</span></span>
  
<span data-ttu-id="9d23c-137">有关将邮箱置于诉讼保留或将 Office 365 保留策略应用的分步过程，请参阅：</span><span class="sxs-lookup"><span data-stu-id="9d23c-137">For step-by-step procedures for placing a mailbox on Litigation Hold or applying an Office 365 retention policy, see:</span></span>
  
- [<span data-ttu-id="9d23c-138">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="9d23c-138">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [<span data-ttu-id="9d23c-139">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="9d23c-139">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
> [!NOTE]
> <span data-ttu-id="9d23c-p110">诉讼保留和 Office 365 保留策略，您可以创建无限期保留，或基于时间的保留。无限期保留，在非活动邮箱的内容将下去，保留或直到保留被删除或更改保留持续时间。保持或保留策略已 （假定指定邮箱已删除超过 30 天） 后，非活动邮箱将标记为永久删除和保留或可供搜索，将不再是邮箱的内容。在基于时间的保留或 Office 365 保留策略中，您可以指定保留项的持续时间。此持续时间在每项基础和接收或创建邮箱项目从日期计算。保留项过期邮箱项目，并且该项目移动到或非活动邮箱中可恢复邮件文件夹位于后，项目被永久删除 （清除） 从非活动邮箱已删除的邮件保留期过后。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p110">For Litigation Holds and Office 365 retention policies, you can create an indefinite hold or on a time-based hold. In an indefinite hold, the contents of the inactive mailbox will be retained forever, or until the hold is removed or until the hold duration is changed. After the hold or retention policy is removed (assuming that the mailbox was deleted more than 30 days ago), the inactive mailbox will be marked for permanent deletion and the contents of the mailbox will no longer be retained or discoverable. In a time-based hold or Office 365 retention policy, you specify the duration of the hold. This duration is on a per-item basis and is calculated from the date a mailbox item was received or created. After the hold expires for a mailbox item, and that item moved to or is located in the Recoverable Items folder in the inactive mailbox, the item is permanently deleted (purged) from the inactive mailbox after the deleted item retention period expires.</span></span> 
  
### <a name="step-2-delete-the-mailbox"></a><span data-ttu-id="9d23c-146">步骤 2：删除邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-146">Step 2: Delete the mailbox</span></span>

<span data-ttu-id="9d23c-p111">邮箱置于保持状态或 Office 365 保留策略应用于其后下, 一步是删除邮箱。删除邮箱的最佳方式是删除 Office 365 管理中心中的相应 Office 365 用户帐户。有关删除 Office 365 用户帐户的信息，请参阅[删除用户从您的组织](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p111">After the mailbox is placed on hold or an Office 365 retention policy is applied to it, the next step is to delete the mailbox. The best way to delete a mailbox is to delete the corresponding Office 365 user account in the Office 365 admin center. For information about deleting Office 365 user accounts, see [Delete a user from your organization](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d23c-p112">您也可以在 Exchange Online PowerShell 中使用**Remove-mailbox** cmdlet 删除邮箱。有关详细信息，请参阅[删除或还原 Exchange 在 Online 用户邮箱](https://go.microsoft.com/fwlink/?linkid=856287)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p112">You can also delete the mailbox by using the **Remove-Mailbox** cmdlet in Exchange Online PowerShell. For more information, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287).</span></span> 
  

## <a name="view-a-list-of-inactive-mailboxes"></a><span data-ttu-id="9d23c-152">查看列表的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-152">View a list of inactive mailboxes</span></span>


<span data-ttu-id="9d23c-153">若要查看组织中的非活动邮箱的列表：</span><span class="sxs-lookup"><span data-stu-id="9d23c-153">To view a list of the inactive mailboxes in your organization:</span></span>
  
1. <span data-ttu-id="9d23c-154">转到[https://protection.office.com/](https://protection.office.com/)和使用 Office 365 组织中的管理员帐户凭据登录。</span><span class="sxs-lookup"><span data-stu-id="9d23c-154">Go to [https://protection.office.com/](https://protection.office.com/) and sign in using the credentials for an administrator account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="9d23c-155">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> \* \* 保留 \* \*。</span><span class="sxs-lookup"><span data-stu-id="9d23c-155">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> \*\* Retention \*\*.</span></span>
    
3. <span data-ttu-id="9d23c-156">在**保留**页上，单击**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)，，然后单击**非活动邮箱**。</span><span class="sxs-lookup"><span data-stu-id="9d23c-156">On the **Retention** page, click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif), and then click **Inactive mailboxes**.</span></span>
    
    ![在保留页上，单击更多，然后单击非活动邮箱显示非活动邮箱的列表](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    <span data-ttu-id="9d23c-p113">显示**非活动邮箱**页。请注意显示您的组织中的非活动邮箱总数。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p113">The **Inactive mailboxes** page is displayed. Note the total number of inactive mailboxes in your organization is displayed.</span></span> 
    
    ![将显示您的组织中的所有非活动邮箱的列表](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
<span data-ttu-id="9d23c-161">此外，还可以运行以下命令在 Exchange Online PowerShell，可以显示非活动邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="9d23c-161">Alternatively, you can run the following command in Exchange Online PowerShell to display the list of inactive mailboxes.</span></span>

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

<span data-ttu-id="9d23c-162">您可以单击![导出搜索结果图标](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**导出**以查看或下载 CSV 文件包含有关您的组织中的非活动邮箱的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9d23c-162">You can click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export** to view or download a CSV file that contains additional information about the inactive mailboxes in your organization.</span></span> 
  
<span data-ttu-id="9d23c-p114">您还可以运行以下命令以将非活动邮箱的列表和其他信息导出到 CSV 文件。本示例中，在当前目录中创建 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p114">You can also run the following command to export the list of inactive mailboxes and other information to a CSV file. In this example, the CSV file is created in the current directory.</span></span>

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> <span data-ttu-id="9d23c-p115">则可能非活动邮箱，可能为活动用户邮箱中的相同的 SMTP 地址。在这种情况下，可以使用的**可分辨名称**或**ExchangeGuid**属性的值来唯一地标识非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p115">It's possible that an inactive mailbox may have the same SMTP address as an active user mailbox. In this case, the value of the **DistinguishedName** or **ExchangeGuid** property can be used to uniquely identify an inactive mailbox.</span></span> 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a><span data-ttu-id="9d23c-167">搜索和导出内容的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-167">Search and export the contents of an inactive mailbox</span></span>

<span data-ttu-id="9d23c-p116">可以通过使用中的安全的内容搜索工具访问的非活动邮箱内容&amp;合规性中心。搜索非活动邮箱时，您可以创建关键字搜索查询来搜索特定项，或者您可以返回非活动邮箱的全部内容。您可以预览搜索结果，或将搜索结果导出到 Outlook 数据 (PST) 文件或作为单个电子邮件。用于搜索邮箱和导出搜索结果的分步过程，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="9d23c-p116">You can access the contents of the inactive mailbox by using the Content Search tool in the Security &amp; Compliance Center. When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:</span></span>
  
- [<span data-ttu-id="9d23c-172">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="9d23c-172">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="9d23c-173">从 Office 365 安全性导出内容的搜索结果&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="9d23c-173">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
<span data-ttu-id="9d23c-174">下面是要搜索非活动邮箱时，请记住的几个事项。</span><span class="sxs-lookup"><span data-stu-id="9d23c-174">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="9d23c-175">如果内容搜索包含用户邮箱，并且该邮箱由处于非活动状态，内容搜索将继续在它变为非活动状态后重新运行搜索时搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d23c-175">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="9d23c-p117">在某些情况下，用户可能有活动邮箱和非活动邮箱，具有相同的 SMTP 地址。在这种情况下，将搜索仅特定邮箱的选择作为内容搜索的位置。换句话说，如果您将用户邮箱添加到搜索，您不能假设，将搜索其活动和非活动邮箱;将搜索的明确添加到搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p117">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="9d23c-p118">我们强烈建议您避免使用活动邮箱和非活动邮箱具有相同的 SMTP 地址。如果您需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或非活动邮箱的内容还原到活动邮箱 （或活动邮箱的存档），然后删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p118">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span>
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="9d23c-181">更改非活动邮箱的保留期</span><span class="sxs-lookup"><span data-stu-id="9d23c-181">Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="9d23c-p119">非活动邮箱后，您可以更改保留或 Office 365 保留策略应用于非活动邮箱的持续时间。有关分步步骤说明，请参阅[更改在 Office 365 中的非活动邮箱的保留持续时间](change-the-hold-duration-for-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p119">After a mailbox is made inactive, you can change the duration of the hold or the Office 365 retention policy applied to the inactive mailbox. For step-by-step procedures, see [Change the hold duration for an inactive mailbox in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).</span></span>
  
## <a name="recover-an-inactive-mailbox"></a><span data-ttu-id="9d23c-184">恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-184">Recover an inactive mailbox</span></span>

<span data-ttu-id="9d23c-p120">如果以前员工返回给您的组织，或新员工加入才能离开员工职责，您可以恢复非活动邮箱的内容。非活动邮箱恢复时，邮箱转换为新邮箱，将保留内容和非活动邮箱文件夹结构，以及邮箱链接到新的用户帐户。将在恢复之后，非活动邮箱不再存在。分步过程和详细信息发生非活动邮箱恢复时，请参阅[Office 365 中的非活动邮箱恢复](recover-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p120">If a former employee returns to your organization, or if a new employee is hired to take on the job responsibilities of the departed employee, you can recover the contents of the inactive mailbox. When you recover an inactive mailbox, the mailbox is converted to a new mailbox, the contents and folder structure of the inactive mailbox are retained, and the mailbox is linked to a new user account. After it's recovered, the inactive mailbox no longer exists. For step-by-step procedures and more information about happens when you recover an inactive mailbox, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a><span data-ttu-id="9d23c-189">将非活动邮箱的内容还原到另一个邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-189">Restore the contents of an inactive mailbox to another mailbox</span></span>

<span data-ttu-id="9d23c-p121">如果另一个雇员承担的前员工职责或其他人需要访问非活动邮箱的内容，您可以还原 （或合并） 到现有邮箱的非活动邮箱的内容。非活动邮箱还原时，内容复制到另一个邮箱。非活动邮箱保留，并保持非活动邮箱。仍可使用电子数据展示搜索非活动邮箱，可在其内容还原到另一个邮箱或恢复或删除以后。有关分步步骤说明，请参阅[还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p121">If another employee takes on the job responsibilities of a former employee, or if another person needs access to the contents of the inactive mailbox, you can restore (or merge) the contents of the inactive mailbox to an existing mailbox. When you restore an inactive mailbox, the contents are copied to another mailbox. The inactive mailbox is retained and remains an inactive mailbox. The inactive mailbox can still be searched using eDiscovery, its contents can be restored to another mailbox, or it can be recovered or deleted at a later date. For step-by-step procedures, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
  
## <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="9d23c-195">删除非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="9d23c-195">Delete an inactive mailbox</span></span>

<span data-ttu-id="9d23c-p122">如果您不再需要保留的非活动邮箱内容，您可以通过删除保留或移除 Office 365 保留策略应用于非活动邮箱中永久删除非活动邮箱。如果邮箱已删除超过 30 天，邮箱将标记为永久删除后删除保留，并且邮箱将变为不可恢复。如果最近 30 天内已删除邮箱，仍可以恢复后删除保留或保留策略的邮箱。有关删除保留或 Office 365 保留策略永久删除非活动邮箱的分步过程，请参阅[删除非活动邮箱 Office 365 中](delete-an-inactive-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="9d23c-p122">If you no longer need to retain the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold or removing the Office 365 retention policy applied to the inactive mailbox. If the mailbox was deleted more than 30 days ago, the mailbox will be marked for permanent deletion after you remove the hold, and the mailbox will become non-recoverable. If the mailbox was deleted within the last 30 days, you can still recover the mailbox after removing the hold or retention policy. For step-by-step procedures for removing a hold or a Office 365 retention policy to permanently delete an inactive mailbox, see [Delete an inactive mailbox in Office 365](delete-an-inactive-mailbox.md).</span></span>