---
title: 从原始位置删除项目
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍如何使用安全 & 合规性中心中的新数据调查 (预览版) 工具删除其原始位置中的项目。
ms.openlocfilehash: 9c8b7c0707183e9bd0f423790b47f9aa60e35912
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36654111"
---
# <a name="delete-items-from-their-original-location-preview"></a><span data-ttu-id="6f2f6-103">从原始位置删除项目 (预览)</span><span class="sxs-lookup"><span data-stu-id="6f2f6-103">Delete items from their original location (Preview)</span></span>

<span data-ttu-id="6f2f6-104">将项目从其原始位置删除的功能位于预览模式中。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-104">The feature to delete items from their original location is in Preview.</span></span>

<span data-ttu-id="6f2f6-105">使用数据调查, 可以从其原始位置删除项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-105">Using data investigations, you can delete items from their original locations.</span></span> <span data-ttu-id="6f2f6-106">这意味着您可以在组织中删除 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户中的项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-106">This means you can delete items from  Exchange mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="6f2f6-107">由于已将项目作为证据收集, 因此您拥有在证据集内保留的项目的副本以供进一步调查或保留为参考。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-107">Because you collected items as evidence, you have copies of the items retained in the evidence set for further investigation or keep as reference.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6f2f6-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="6f2f6-108">Before you begin</span></span>

- <span data-ttu-id="6f2f6-109">若要删除项目, 您必须在安全 & 合规性中心中为其分配**搜索和清除**角色。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-109">To delete items, you have to be assigned the **Search And Purge** role in the Security & Compliance Center.</span></span> <span data-ttu-id="6f2f6-110">默认情况下, 此角色分配给内置的 "数据调查者" 角色组。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-110">This role is assigned by default to the built-in Data Investigator role group.</span></span> 

- <span data-ttu-id="6f2f6-111">本主题中的过程假定您已运行与调查相关的搜索并将搜索结果添加到证据集。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-111">The procedure in this topic assumes that you have run a search associated with an investigation and added the search results to an evidence set.</span></span> <span data-ttu-id="6f2f6-112">在搜索结果位于证据中之后, 您可以选择一个或多个要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-112">After the search results are in evidence, you can select one or more items to delete.</span></span> <span data-ttu-id="6f2f6-113">有关详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-113">For more information, see [Search for data in an investigation](search-for-data.md).</span></span>

- <span data-ttu-id="6f2f6-114">请务必记住, 只有原始内容位置 (如 Exchange 邮箱、SharePoint 网站和 OneDrive 帐户) 中的项目会被删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-114">It's important to keep in mind that only the items in the original content locations (such as Exchange mailboxes, SharePoint sites, and OneDrive accounts) are deleted.</span></span> <span data-ttu-id="6f2f6-115">这些项目不会从证据集中删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-115">These items aren't deleted from the evidence set.</span></span> <span data-ttu-id="6f2f6-116">这是因为证据集中的项目是原始的副本。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-116">That's because the items in an evidence set are copies of the original.</span></span> <span data-ttu-id="6f2f6-117">将搜索结果添加到证据集时, 会复制这些项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-117">These items are copied when you added the results of a search to an evidence set.</span></span>

## <a name="delete-items"></a><span data-ttu-id="6f2f6-118">删除项目</span><span class="sxs-lookup"><span data-stu-id="6f2f6-118">Delete items</span></span>

<span data-ttu-id="6f2f6-119">执行以下步骤以从其原始位置删除项目:</span><span class="sxs-lookup"><span data-stu-id="6f2f6-119">Perform the following steps to delete items from their original location:</span></span>

1. <span data-ttu-id="6f2f6-120">在 "**数据调查**" 工具中, 打开包含要删除的项目的数据调查, 然后单击 "**证据**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-120">In the **Data Investigations** tool, open the data investigation that contains the items you want to delete, and then click the **Evidence** tab.</span></span>

2. <span data-ttu-id="6f2f6-121">选择要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-121">Select the items that you want to delete.</span></span> <span data-ttu-id="6f2f6-122">您可以选择证据集内的所有项目, 也可以仅选择项目的子集。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-122">You can select all items in the evidence set or select just a subset of items.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="6f2f6-123">如果在 SharePoint 和 OneDrive 中选择了电子邮件附件或附加到文档的文件, 则当项目从其原始位置删除时, 父项目也将被选中并被删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-123">If you select the attachments of an email or a file attached to a document in SharePoint and OneDrive, the parent item will be also be selected and deleted when the item is deleted from its original location.</span></span> <span data-ttu-id="6f2f6-124">同样, 如果选择包含附件的项, 则会删除父项项目和所有附件。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-124">Similarly, if you select an item that has attachments, the parent item item and all attachments are deleted.</span></span>
 
2. <span data-ttu-id="6f2f6-125">单击 "**操作**", 然后单击 "**从原始位置删除项目**"。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-125">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![单击 "操作", 然后单击 "从原始位置删除项目"](../media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="6f2f6-127">在弹出页面上, 验证要删除的项目和相关子文档的数目, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-127">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

   ![浮出控件页面显示选定要删除的项目数和所有附加的文档](../media/DataInvestigationsDeleteItems2.png)

   > [!NOTE]
   > <span data-ttu-id="6f2f6-129">在上面的屏幕快照中, 项目数指示选定要删除的项目数。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-129">In the previous screenshot, the number of items indicates the number of items that are selected for deletion.</span></span> <span data-ttu-id="6f2f6-130">文档数指示包含附加到父项目的任何文件的项目总数。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-130">The number of documents indicates to total number of items including any files that are attached to a parent item.</span></span> <span data-ttu-id="6f2f6-131">例如, 如果您选择一封电子邮件, 并且该邮件包含附加的 Word 文档, 则 "**选定的文档**" 下显示的项目数和文档数将为**1 个项目 (2 个文档)**。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-131">For example, if you select one email message and that message has an attached Word document, the number of items and documents displayed under **Selected documents only** would be **1 items (2 documents)**.</span></span>

<span data-ttu-id="6f2f6-132">您可以在 "**作业**" 选项卡上跟踪 "**从原始位置删除项目**" 作业的进度。单击该作业以显示弹出页面。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-132">You can track the progress of the **Delete items from original locations** job on the **Jobs** tab. Click the job to display the flyout page.</span></span> 

![用于从原始位置作业中删除项目的飞出页面](../media/DataInvestigationsDeleteItems3.png)

<span data-ttu-id="6f2f6-134">删除作业中的项目时, 作业状态将设置为 "**成功**"。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-134">When the items in the job are deleted, the job status is set to **Successful**.</span></span> <span data-ttu-id="6f2f6-135">还会显示已完成作业的时间和日期。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-135">The time and date of the completed job is also displayed.</span></span> 

![已完成的 "删除项目" 作业](../media/DataInvestigationsDeleteItems4.png)

> [!NOTE]
> <span data-ttu-id="6f2f6-137">您可能会收到**来自原始位置**作业的 "删除项目"**部分成功**的状态。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-137">You may receive a status of **Partially Successful** for the **Delete items from original locations** job.</span></span> <span data-ttu-id="6f2f6-138">有很多情况会导致此作业状态。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-138">There are a number of situations that result in this job status.</span></span> <span data-ttu-id="6f2f6-139">有关详细信息, 请参阅本文中的[部分成功删除](#partially-successful-deletions)部分。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-139">For more information, see the [Partially successful deletions](#partially-successful-deletions) section in this article.</span></span>

## <a name="what-happens-when-you-delete-items"></a><span data-ttu-id="6f2f6-140">删除项目时发生的情况</span><span class="sxs-lookup"><span data-stu-id="6f2f6-140">What happens when you delete items</span></span>

<span data-ttu-id="6f2f6-141">目前, 当您从原始内容位置删除项目时, 这些项目会*软删除*。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-141">At this time, when you delete items from their original content location, the items are *soft-deleted*.</span></span> <span data-ttu-id="6f2f6-142">这意味着项目将移至特殊位置并保留, 直到已删除项目的保留期过期, 并将项目标记为从 Office 365 永久删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-142">This means that items are moved to special location and retained until the deleted item retention period expires and an item is marked for permanent deletion from Office 365.</span></span> <span data-ttu-id="6f2f6-143">软删除项目意味着, 在保留期到期之前, 用户仍可以恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-143">Soft-deleting items means that users can still recover these items until the retention period expires.</span></span> <span data-ttu-id="6f2f6-144">以下是有关从 Exchange 邮箱和 SharePoint 和 OneDrive for business 网站中软删除项目以及用户在从其原始位置删除项目后可以执行的操作的说明。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-144">Here are descriptions about what happens when items are soft-deleted from Exchange mailboxes and SharePoint and OneDrive for Business sites, and what users can do after items are deleted from their original locations.</span></span>

- <span data-ttu-id="6f2f6-145">**邮箱:** 将邮箱项目软删除时, 会将其移动到邮箱中的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-145">**Mailboxes:** When a mailbox item is soft-deleted, it's moved to the Recoverable Items folder in the mailbox.</span></span> <span data-ttu-id="6f2f6-146">当用户从 "已删除邮件" 文件夹中删除项目或通过按 Shift + Delete 永久删除项目时, 此行为类似。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-146">This behavior is similar to when a user deletes an item from the Deleted Items folder or permanently deletes an item by pressing Shift + Delete.</span></span> <span data-ttu-id="6f2f6-147">此时, 用户可以恢复项目, 直到已删除项目的保留期过期。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-147">At this point, the user can recover the item up until the deleted item retention period expires.</span></span> <span data-ttu-id="6f2f6-148">在 Office 365 中, 默认情况下, 已删除项目的保留期为14天, 但管理员可以将保留期增加到30天。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-148">In Office 365, the deleted item retention period is 14 days by default, but an admin can increase the retention period to 30 days.</span></span> <span data-ttu-id="6f2f6-149">保留期到期后, 项目将移至隐藏文件夹 (称为 "*清除*" 文件夹)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-149">After the retention period expires, the item is moved to a hidden folder (called the *Purges* folder).</span></span> <span data-ttu-id="6f2f6-150">下次处理邮箱时, 将从 Office 365 中永久删除该项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-150">The item is permanently removed from Office 365 the next time the mailbox is processed.</span></span> <span data-ttu-id="6f2f6-151">每七天处理一次邮箱)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-151">Mailboxes are processed once every seven days).</span></span>

- <span data-ttu-id="6f2f6-152">**SharePoint 和 OneDrive 网站:** 当网站上的文件或文档软删除时, 它会被移动到网站的回收站 (也称为*第一阶段*回收站)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-152">**SharePoint and OneDrive sites:** When a file or document on a site is soft-deleted, it's moved to the site's Recycle Bin (also called the *first-stage* Recycle Bin).</span></span> <span data-ttu-id="6f2f6-153">项目将保留在回收站中的93天 (Office 365 中的网站的已删除项目保留期)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-153">The item remains in the Recycle Bin for 93 days (the deleted item retention period for sites in Office 365).</span></span> <span data-ttu-id="6f2f6-154">在93天内, 仍可由 SharePoint 中的网站集管理员或 OneDrive 中的用户或管理员恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-154">During the 93-day period, deleted items can still be recovered by a site collection administrator in SharePoint or by the user or admin in OneDrive.</span></span> <span data-ttu-id="6f2f6-155">也可以从第一阶段回收站中删除项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-155">Items can also be deleted from the first-stage recycle bin.</span></span> <span data-ttu-id="6f2f6-156">当发生这种情况时, 会将项目移到网站集的回收站中, 该网站集称为*第二阶段*回收站。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-156">When that happens, the items are moved to the Recycle Bin for the site collection, which is called the *second-stage* Recycle Bin.</span></span> <span data-ttu-id="6f2f6-157">对于第一阶段和第二阶段回收站, 保留期为93天。这意味着第二阶段回收站保留在最初删除项目时开始。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-157">The retention period is 93 days for both the first-stage and second-stage recycle bins. That means the second-stage Recycle Bin retention starts when the item is initially deleted.</span></span> <span data-ttu-id="6f2f6-158">这意味着两个回收站的总保留时间总为93天。如果从第二阶段回收站中删除某个项目 (由管理员手动或在保留期过期后自动进行), 则管理员将无法再访问该项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-158">That means the total maximum retention time is 93 days for both recycle bins. If an item is deleted from the second-stage Recycle Bin (either manually by an admin or automatically when the retention period expires), it's no longer accessible by an admin.</span></span>

## <a name="what-happens-if-a-content-location-is-on-hold"></a><span data-ttu-id="6f2f6-159">如果内容位置处于保留状态, 会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="6f2f6-159">What happens if a content location is on hold</span></span>

<span data-ttu-id="6f2f6-160">在 Office 365 中, 可以将邮箱和网站置于保留或分配给保留策略。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-160">In Office 365, mailboxes and sites can be placed on hold or assigned to a retention policy.</span></span> <span data-ttu-id="6f2f6-161">这意味着在项目的保留期过期或删除保留期之前, 不会永久删除任何内容。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-161">This means that nothing is permanently removed until the retention period for an item expires or until the hold is removed.</span></span> <span data-ttu-id="6f2f6-162">即使从原始位置删除某个项目, 该项目也可能不会从 Office 365 中永久删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-162">Even if you delete an item from its original location, the item may not be permanently removed from Office 365.</span></span> <span data-ttu-id="6f2f6-163">例如, 如果邮箱处于保留状态, 则会最终移动软删除的项目以清除或 DiscoveryHold "可恢复的项目" 文件夹中的子文件夹, 并保留该文件夹, 直到保留期或保留期过期。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-163">For example, if a mailbox is on hold, soft-deleted items are eventually moved to Purges or DiscoveryHold subfolders in the Recoverable Items folder and retained until the hold duration or retention period expires.</span></span> <span data-ttu-id="6f2f6-164">对于网站, 移动到回收站中的项的副本将复制到在网站上放置保留策略时创建的保留保留库。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-164">For sites, a copy of the item that's moved to the Recycle Bin is copied to the Preservation Hold library that's created when a hold or retention policy is placed on a site.</span></span>

## <a name="partially-successful-deletions"></a><span data-ttu-id="6f2f6-165">部分成功删除</span><span class="sxs-lookup"><span data-stu-id="6f2f6-165">Partially successful deletions</span></span>

<span data-ttu-id="6f2f6-166">在原始位置作业的 "**删除项目**" 完成运行后, 可能会收到 "**部分成功**" 作业状态。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-166">After the **Delete items from original locations** job has completed running, you may received a job status of **Partially Successful**.</span></span> <span data-ttu-id="6f2f6-167">通常情况下, 此状态表示作业成功运行, 但并不是所有项目都软删除。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-167">In general, this status indicates that the job ran successfully, but not all items were soft-deleted.</span></span> <span data-ttu-id="6f2f6-168">下面列出了导致部分成功删除的原因:</span><span class="sxs-lookup"><span data-stu-id="6f2f6-168">Here's a list of reasons that result in partially successful deletions:</span></span>

- <span data-ttu-id="6f2f6-169">邮箱项目已经位于源邮箱的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-169">A mailbox item was already located in the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="6f2f6-170">已从源邮箱的 "可恢复的项目" 文件夹中清除邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-170">A mailbox item was purged from the Recoverable Items folder in the source mailbox.</span></span>

- <span data-ttu-id="6f2f6-171">文档已位于 SharePoint 或 OneDrive 网站的第一阶段回收站中。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-171">A document was already located in the first-stage Recycle Bin in a SharePoint or OneDrive site.</span></span>

- <span data-ttu-id="6f2f6-172">将文档添加到证据集后, 该文档被移动到其他 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-172">A document was moved to a different SharePoint site after it was added to the evidence set.</span></span> <span data-ttu-id="6f2f6-173">在这种情况下, 不会将文档移到已移动到的网站的回收站中。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-173">In this case, the document isn't moved to the Recycle Bin in the site it was moved to.</span></span>

- <span data-ttu-id="6f2f6-174">在将文档添加到证据集后, 该文档会在 SharePoint 或 OneDrive 中永久删除 (移至第二阶段回收站)。</span><span class="sxs-lookup"><span data-stu-id="6f2f6-174">A document was permanently deleted in SharePoint or OneDrive (moved to the second-stage Recycle Bin) after it was added to the evidence set.</span></span>
