---
title: 设置 Office 365 组织中邮箱的存档和删除策略
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: 创建自动将项目移至用户的存档邮箱的 Office 365 中归档和删除策略。
ms.openlocfilehash: 903a91c590c47ad5de0b89ae51a25983221d2ffe
ms.sourcegitcommit: 031781d0eecf33baabcd03ea53546d41076062b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240575"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="fabfd-103">设置 Office 365 组织中邮箱的存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="fabfd-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="fabfd-p101">在 Office 365 中，管理员可以创建自动将项目移至用户的存档邮箱并自动从邮箱中删除项目的存档和删除策略。管理员创建保留策略分配给邮箱，并将项目移至用户的存档邮箱后一段时间，并且还会删除项目从邮箱后达到特定期限限制来达到此目的。确定哪些项目的实际规则移动或删除并且出现这种情况称为的保留标记。保留标记链接到反过来分配给用户的邮箱的保留策略。保留标记适用于单个消息和用户的邮箱中的文件夹的保留设置。它定义一条消息的邮箱中保留的时间长度和当消息到达指定的保持期所采取的操作。当一条消息到达其保留时间时，它也移动到用户的存档邮箱或将其删除。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p101">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox. The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit. The actual rules that determine what items are moved or deleted and when that happens are called retention tags. Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox. A retention tag applies retention settings to individual messages and folders in a user's mailbox. It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age. When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="fabfd-p102">本文中的步骤将设置名为 Alpine House 虚拟组织的存档和保留策略。设置此策略包括以下任务：</span><span class="sxs-lookup"><span data-stu-id="fabfd-p102">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House. Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="fabfd-p103">启用存档邮箱的组织中的每个用户。这为用户提供了添加邮箱存储，并需要，以便将保留策略可以将项目移动到存档邮箱。它还我们通过移动用户存储存档信息项存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p103">Enabling an archive mailbox for every user in the organization. This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox. It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="fabfd-116">创建三个自定义保留标记，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fabfd-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="fabfd-p104">自动移动旧用户的存档邮箱的 3 年的项目。将项目移动到存档邮箱释放空间用户的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p104">Automatically moves items that are 3 years old to the user's archive mailbox. Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="fabfd-p105">自动删除旧的 5 年中的已删除邮件文件夹的项目。这还释放空间用户的主邮箱中。用户将有机会来恢复这些项目，如有必要。请参阅有关详细信息[详细信息](#more-information)部分中的脚注。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p105">Automatically deletes items that are 5 years old from the Deleted Items folder. This also frees up space in the user's primary mailbox. User's will have the opportunity to recover these items if necessary. See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="fabfd-p106">自动 （并永久） 删除旧从两个主 7 年和存档邮箱的项目。合规性要求，因为一些组织需要一段时间保留电子邮件。此时间段后，组织可能想要永久删除这些项目用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p106">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox. Because of compliance regulations, some organization's are required to retain email for a certain period of time. After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="fabfd-p107">创建新的保留策略，并向其中添加新的自定义保留标记。此外，还将添加到新的保留策略的内置保留标记。这包括用户可以分配给他们的邮箱中的项目的个人标记。您还将添加一个将项目从用户的主邮箱中可恢复邮件文件夹移至其存档邮箱中可恢复邮件文件夹的保留标记。此帮助释放空间用户的可恢复项目文件夹中，当其邮箱置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p107">Creating a new retention policy and adding the new custom retention tags to it. Additionally, you'll also add built-in retention tags to the new retention policy. This includes personal tags that users can assign to items in their mailbox. You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox. This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="fabfd-p108">您可以按照部分或全部这篇文章，设置对自己组织中邮箱的存档和删除策略中的步骤。我们建议您在组织中的所有邮箱上实现它之前测试此过程在几个邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p108">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization. We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="fabfd-133">准备工作</span><span class="sxs-lookup"><span data-stu-id="fabfd-133">Before you begin</span></span>

- <span data-ttu-id="fabfd-134">您必须是 Office 365 组织中全局管理员才能执行此主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="fabfd-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="fabfd-p109">当您在 Office 365 中创建新的用户帐户，并将该用户分配一个 Exchange Online 的许可证时，自动为用户创建邮箱。创建邮箱后，它具有自动分配名为默认 MRM 策略的默认保留策略。在本文中，您将创建新的保留策略，然后将其分配到用户邮箱，替换默认 MRM 策略。邮箱都可以在任何时刻分配给它的只有一个保留策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p109">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user. When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy. In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy. A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="fabfd-139">若要详细了解保留标记和保留策略在 Exchange Online，请参阅[保留标记和保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404424)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="fabfd-140">步骤 1： 启用存档邮箱的用户</span><span class="sxs-lookup"><span data-stu-id="fabfd-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="fabfd-p110">第一步是启用为在组织中的每个用户的存档邮箱。用户的存档邮箱必须启用，以便保留时间过后，具有"移动到存档"保留操作的保留标记可以移动项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p110">The first step is to enable the archive mailbox for each user in your organization. A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="fabfd-p111">只要它们之前完成该过程启用某个时刻，可以随时在此过程中，启用存档邮箱。如果没有启用存档邮箱，任何有为其分配的存档策略的项不采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p111">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process. If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="fabfd-145">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="fabfd-146">登录到 Office 365 使用全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="fabfd-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="fabfd-147">安全中&amp;合规性中心中，转到**数据调控** \> **存档**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-147">In the Security &amp; Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="fabfd-148">将显示您的组织中邮箱的列表和相应的存档邮箱是启用还是禁用。</span><span class="sxs-lookup"><span data-stu-id="fabfd-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="fabfd-149">通过单击第一个在列表中，按住**Shift**键，然后单击列表中的最后一个选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="fabfd-p112">此步骤假定已启用没有存档邮箱。如果您有任何邮箱启用存档，请按住**Ctrl**键并单击每个已禁用的存档邮箱的邮箱。或者您可以单击**存档邮箱**列标题，基于是否启用或禁用以使其更轻松地选择邮箱的存档邮箱的行进行排序。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p112">This step assumes that no archive mailboxes are enabled. If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox. Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="fabfd-153">在详细信息窗格中，在**批量编辑**单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="fabfd-p113">显示一则警告反映超过两年的项目，将移动到新的存档邮箱。这是因为已在创建时分配新的用户邮箱的默认保留策略具有 2 年保留时间存档默认策略标记。您将在步骤 2 中创建自定义存档默认策略标记有 3 年保留时间。这意味着 3 年的项目或更低将被移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p113">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox. This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years. The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years. That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="fabfd-158">单击**是**以关闭警告消息并启动启用每个选定邮箱的存档邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="fabfd-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="fabfd-159">在过程完成后，单击**刷新**![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png)更新**存档**页上的列表。</span><span class="sxs-lookup"><span data-stu-id="fabfd-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="fabfd-160">为所有用户的组织中启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![与启用存档邮箱的邮箱的列表](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="fabfd-p114">保留债券&amp;合规性中心打开。您将在下一步中使用它。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p114">Leave the Security &amp; Compliance Center open. You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="fabfd-164">步骤 2： 创建新的存档和删除策略的保留标记</span><span class="sxs-lookup"><span data-stu-id="fabfd-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="fabfd-165">在此步骤中，您将创建以前介绍的三个自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="fabfd-166">Alpine House 3 年将移动到存档 （自定义存档策略）</span><span class="sxs-lookup"><span data-stu-id="fabfd-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="fabfd-167">Alpine House 7 年永久删除 （自定义删除策略）</span><span class="sxs-lookup"><span data-stu-id="fabfd-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="fabfd-168">Alpine 所删除项目 5 年删除并允许恢复 （自定义标记为已删除邮件文件夹）</span><span class="sxs-lookup"><span data-stu-id="fabfd-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="fabfd-169">若要创建新的保留标记，您将 Exchange Online 组织中使用 Exchange 管理员中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="fabfd-170">安全中&amp;合规性中心，单击左上角，应用程序启动器，然后单击**管理员**图块。</span><span class="sxs-lookup"><span data-stu-id="fabfd-170">In the Security &amp; Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="fabfd-171">在 Office 365 管理中心的左侧的导航窗格中，单击**管理中心**，，然后单击**Exchange**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-171">In the left navigation pane of the Office 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![Screenshot shows the Office 365 admin center with the Admin centers option expanded and Exchange selected.](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="fabfd-173">在 EAC 中，转到**合规性管理** \> **保留标记**</span><span class="sxs-lookup"><span data-stu-id="fabfd-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="fabfd-174">将显示为您的组织的保留标记的列表。</span><span class="sxs-lookup"><span data-stu-id="fabfd-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="fabfd-175">创建自定义存档默认策略标记</span><span class="sxs-lookup"><span data-stu-id="fabfd-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="fabfd-176">首先，您将创建将将项目 3 年后移动到存档邮箱的自定义存档默认策略标记 (DPT)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="fabfd-177">在**保留标记**页上，单击**新标记**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然后选择**自动于整个邮箱 （默认值）**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="fabfd-178">在**新标记应用于整个邮箱 （默认值） 自动**页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="fabfd-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![若要创建新的存档默认策略标记的设置](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="fabfd-180">**名称**键入新的保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="fabfd-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="fabfd-181">**保留操作**选择**移动到存档**保留期到期时，将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="fabfd-p115">**保留期\*\*\*\*项目到达的以下时间 （天） 时**，选择，然后输入的保留期的持续时间。对于此方案中，项目将被移动到存档邮箱后 1095 天 （3 年）。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p115">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="fabfd-184">**注释**（可选）键入说明的自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="fabfd-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="fabfd-185">单击**保存**以创建自定义存档 DPT。</span><span class="sxs-lookup"><span data-stu-id="fabfd-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="fabfd-186">新的存档 DPT 将显示在列表中的保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="fabfd-187">创建自定义删除默认策略标记</span><span class="sxs-lookup"><span data-stu-id="fabfd-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="fabfd-188">接下来，您将创建另一个自定义的 DPT，但此将永久删除项目，7 年后删除策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="fabfd-189">在**保留标记**页上，单击**新标记**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然后选择**自动于整个邮箱 （默认值）**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="fabfd-190">在**新标记应用于整个邮箱 （默认值） 自动**页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="fabfd-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![若要创建新的删除默认策略标记的设置](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="fabfd-192">**名称**键入新的保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="fabfd-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="fabfd-193">**保留操作**选择**永久删除**保留期到期时清除邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="fabfd-p116">**保留期\*\*\*\*项目到达的以下时间 （天） 时**，选择，然后输入的保留期的持续时间。对于此方案中，将 2555 天 （7 年） 后清除项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p116">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="fabfd-196">**注释**（可选）键入说明的自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="fabfd-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="fabfd-197">单击**保存**以创建自定义删除操作的 DPT。</span><span class="sxs-lookup"><span data-stu-id="fabfd-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="fabfd-198">新的删除 DPT 将显示在列表中的保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="fabfd-199">创建自定义保留策略标记为已删除邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="fabfd-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="fabfd-p117">您将创建的最后一个保留标记自定义保留策略标记 （报表） 的已删除邮件文件夹。此标记 5 年后，将删除已删除邮件文件夹中的项目，并提供用户时使用恢复已删除邮件工具来恢复项目恢复期。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p117">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder. This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="fabfd-202">在**保留标记**页上，单击**新标记**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)，然后选择**自动于默认文件夹**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="fabfd-203">在**新标记自动于默认文件夹**页上，填写以下字段：</span><span class="sxs-lookup"><span data-stu-id="fabfd-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![设置，以创建新的保留策略标记为已删除邮件文件夹](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="fabfd-205">**名称**键入新的保留标记的名称。</span><span class="sxs-lookup"><span data-stu-id="fabfd-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="fabfd-206">**应用此标记添加到下面的默认文件夹**在下拉列表中，选择**已删除邮件**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="fabfd-207">**保留操作**选择**删除和允许恢复**删除项目时保留期过期，但允许用户 （其默认情况下为 14 天） 的已删除的邮件保留期内恢复已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="fabfd-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="fabfd-p118">**保留期\*\*\*\*项目到达的以下时间 （天） 时**，选择，然后输入的保留期的持续时间。对于此方案中，将 1825 天 （5 年） 后删除项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p118">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period. For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="fabfd-210">**注释**（可选）键入说明的自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="fabfd-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="fabfd-211">单击**保存**以创建自定义报表已删除邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="fabfd-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="fabfd-212">新报表将显示在列表中的保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="fabfd-213">步骤 3： 创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="fabfd-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="fabfd-p119">创建自定义保留标记后下, 一步是创建新的保留策略并添加的保留标记。您将添加您在步骤 2 中创建的三个自定义保留标记和在第一节中提到的内置标记。在步骤 4，您将对用户邮箱分配此新的保留策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p119">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags. You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section. In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="fabfd-217">在 EAC 中，转到**合规性管理** \> **保留策略**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="fabfd-218">在**保留策略**页上，单击**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="fabfd-219">在**名称**框中，键入新的保留策略; 名称例如， **Alpine House 归档和删除策略**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="fabfd-220">在**保留标记**，下单击**添加**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="fabfd-p120">将显示在您的组织中的保留标记的列表。请注意显示您在步骤 2 中创建的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p120">A list of the retention tags in your organization is displayed. Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="fabfd-p121">在下面的屏幕快照 （在[详细信息](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo)部分中详细介绍这些标记） 中添加高调 9 保留标记。若要添加的保留标记，请选择它，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p121">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](set-up-an-archive-and-deletion-policy-for-mailboxes.md#moreinfo) section). To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![添加新的保留策略的保留标记](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="fabfd-226">您可以通过按住**Ctrl**键，然后单击每个标记选择多个保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="fabfd-227">添加的保留标记后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="fabfd-228">在**新保留策略**页上，单击**保存**创建新策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="fabfd-p122">在列表中显示新的保留策略。选择要显示详细信息窗格中链接到它的保留标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p122">The new retention policy is displayed in the list. Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新的保留策略和链接的保留标记的列表](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="fabfd-232">步骤 4： 将新的保留策略分配给用户邮箱</span><span class="sxs-lookup"><span data-stu-id="fabfd-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="fabfd-p123">创建一个新的邮箱后，名为默认 MRM 策略的保留策略分配给它默认情况下。在此步骤，您将替换此保留策略 （因为邮箱可以分配给它的保留策略只有一个） 通过分配您在步骤 3 到用户的邮箱在组织中创建新的保留策略。此步骤假定您将新策略为分配所有邮箱在组织中。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p123">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default. In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization. This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="fabfd-236">在 EAC 中，依次转到“收件人”\*\*\*\*\>“邮箱”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fabfd-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="fabfd-237">将显示您的组织中的所有用户邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="fabfd-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="fabfd-238">通过单击第一个在列表中，按住**Shift**键，然后单击列表中的最后一个选择所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="fabfd-239">在 EAC 中，在**批量编辑**右侧细节窗格中单击**更多选项**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="fabfd-240">**保留策略**，下单击**更新**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="fabfd-241">在**批量分配保留策略**页上，在**选择保留策略**下拉列表中，选择您在步骤 3; 创建保留策略例如， **Alpine House 存档和保留策略**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="fabfd-242">单击**保存**以保存新的保留策略分配。</span><span class="sxs-lookup"><span data-stu-id="fabfd-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="fabfd-243">若要验证新的保留策略已分配给邮箱，您可以执行以下操作： 选择邮箱页上的邮箱，然后单击编辑。</span><span class="sxs-lookup"><span data-stu-id="fabfd-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="fabfd-244">选择**邮箱**页上的邮箱，然后单击**编辑**![编辑](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="fabfd-245">在所选用户邮箱属性页上，单击**邮箱功能**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="fabfd-246">在**保留策略**下拉列表中显示分配给邮箱的新策略的名称。</span><span class="sxs-lookup"><span data-stu-id="fabfd-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="fabfd-247">（可选）步骤 5： 运行托管文件夹助理应用新设置</span><span class="sxs-lookup"><span data-stu-id="fabfd-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="fabfd-p124">将新的保留策略应用于步骤 4 中的邮箱后，可能需要多达 7 天在 Exchange Online 的新的保留设置要应用于邮箱。这是因为过程调用的托管文件夹助理流程邮箱 7 天一次。而不是等待托管文件夹助理运行，您可以强制此选项可通过运行**Start-managedfolderassistant** cmdlet 在 Exchange Online PowerShell 发生。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p124">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes. This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days. Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="fabfd-p125">**当您运行托管文件夹助理时，会发生什么情况？** 它通过检查邮箱中的项目并确定是否它们受到保留应用保留策略的设置。它然后用相应的保留标记，标记受到保留的项目，然后承担超过其保留时间的项目指定的保留操作。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p125">**What happens when you run the Managed Folder Assistant?** It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention. It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="fabfd-254">下面是连接到 Exchange Online PowerShell 中，然后运行您的组织中的每个邮箱上的托管文件夹助理的步骤。</span><span class="sxs-lookup"><span data-stu-id="fabfd-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="fabfd-255">在本地计算机上，打开 Windows PowerShell 并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fabfd-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="fabfd-256">**Windows PowerShell 凭据请求**对话框中，键入用户名和在 Office 365 全局管理员帐户的密码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="fabfd-257">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fabfd-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="fabfd-258">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fabfd-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="fabfd-259">要验证您是否已连接至您的 Exchange Online 组织，请运行以下命令获取组织中所有邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="fabfd-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="fabfd-260">有关详细信息或如果您有连接到 Exchange Online 组织的问题，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="fabfd-261">运行以下两个命令启动您的组织中的托管文件夹助理的所有用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="fabfd-p126">就是这样！您已设置 Alpine House 组织的存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p126">That's it! You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="fabfd-264">（可选）步骤 6： 使新的保留策略的默认值为您的组织</span><span class="sxs-lookup"><span data-stu-id="fabfd-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="fabfd-p127">在步骤 4，您需要将新的保留策略分配给现有邮箱。但是，您可以配置 Exchange Online 使新的保留策略分配给将来创建的新邮箱。使用 Exchange Online PowerShell 中更新组织的默认邮箱计划执行此操作。*邮箱计划*已自动新邮箱配置的属性的模板。 在此可选步骤，您可以替换当前分配给您在步骤 3 中创建的保留策略 （默认情况下，默认 MRM 策略） 的邮箱计划的保留策略。更新邮箱计划后，新的保留策略将分配给新邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p127">In Step 4, you have to assign the new retention policy to existing mailboxes. But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future. You do this by using Exchange Online PowerShell to update your organization's default mailbox plan. A *mailbox plan* is a template that automatically configures properties on new mailboxes.  In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3. After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="fabfd-271">[连接到 Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?LinkId=517283)或，请参阅第 5 步。</span><span class="sxs-lookup"><span data-stu-id="fabfd-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="fabfd-272">运行以下命令以显示组织中的有关邮箱计划的信息。</span><span class="sxs-lookup"><span data-stu-id="fabfd-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="fabfd-273">请注意设置为默认邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="fabfd-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="fabfd-p128">向默认邮箱计划运行以下命令以分配在步骤 3 （例如， **Alpine House 存档和保留策略**） 中创建新的保留策略。此示例假定默认邮箱计划的名称是**ExchangeOnlineEnterprise**。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p128">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan. This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="fabfd-276">步骤 2 以检查已更改分配给默认邮箱计划的保留策略中，可以重新运行该命令。</span><span class="sxs-lookup"><span data-stu-id="fabfd-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="fabfd-277">更多信息</span><span class="sxs-lookup"><span data-stu-id="fabfd-277">More information</span></span>

- <span data-ttu-id="fabfd-p129">保留时间的计算方式？邮箱项目的保留期限的计算公式从传递的日期或等不发送的邮件草稿项创建的日期，但由用户创建。在托管文件夹助理处理邮箱中的项时，它标记开始日期和具有与删除但允许恢复或永久删除保留操作的保留标记的所有项目的到期日期。使用 move date 被标有存档标记的项。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p129">How is retention age calculated? The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user. When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action. Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="fabfd-282">下表提供了有关每个保留标记添加到按照本主题中的步骤创建的自定义保留策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fabfd-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="fabfd-283">**保留标记**</span><span class="sxs-lookup"><span data-stu-id="fabfd-283">**Retention tag**</span></span>|<span data-ttu-id="fabfd-284">**此标记的用途**</span><span class="sxs-lookup"><span data-stu-id="fabfd-284">**What this tag does**</span></span>|<span data-ttu-id="fabfd-285">**内置或自定义？**</span><span class="sxs-lookup"><span data-stu-id="fabfd-285">**Built-in or custom?**</span></span>|<span data-ttu-id="fabfd-286">**类型**</span><span class="sxs-lookup"><span data-stu-id="fabfd-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="fabfd-287">Alpine House 3 年移动到存档</span><span class="sxs-lookup"><span data-stu-id="fabfd-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="fabfd-288">将项目的 1095 天 （3 年） 到存档邮箱移动。</span><span class="sxs-lookup"><span data-stu-id="fabfd-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="fabfd-289">自定义 (请参阅[步骤 2： 创建新的存档和删除策略的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="fabfd-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="fabfd-290">默认策略标记 （存档）;此标记将自动应用到整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-291">Alpine House 7 年永久删除</span><span class="sxs-lookup"><span data-stu-id="fabfd-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="fabfd-292">他们何时 7 岁中永久删除主邮箱或存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="fabfd-293">自定义 (请参阅[步骤 2： 创建新的存档和删除策略的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="fabfd-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="fabfd-294">默认策略标记 （删除）;此标记将自动应用到整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-295">Alpine House 删除项目 5 年删除但允许恢复</span><span class="sxs-lookup"><span data-stu-id="fabfd-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="fabfd-p130">从已删除邮件文件夹的旧 5 年中删除项目。用户可以恢复 up 14 天后他们正在删除这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fabfd-p130">Deletes items from the Deleted Items folder that are 5 years old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="fabfd-298">自定义 (请参阅[步骤 2： 创建新的存档和删除策略的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="fabfd-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="fabfd-299">保留策略标记 （已删除项）;此标记自动应用于已删除邮件文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-300">可恢复邮件 14 天后移动到存档</span><span class="sxs-lookup"><span data-stu-id="fabfd-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="fabfd-301">将已在可恢复邮件文件夹中的存档邮箱中的可恢复的项目文件夹的 14 天内的项目移动。</span><span class="sxs-lookup"><span data-stu-id="fabfd-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="fabfd-302">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-302">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-303">保留策略标记 （可恢复的项目）;此标记自动应用于可恢复邮件文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-304">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="fabfd-304">Junk Email</span></span>  <br/> |<span data-ttu-id="fabfd-p131">永久删除已在垃圾邮件文件夹中 30 天的项目。用户可以恢复 up 14 天后他们正在删除这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fabfd-p131">Permanently deletes items that have been in the Junk Email folder for 30 days. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="fabfd-307">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-307">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-308">保留策略标记 （垃圾邮件）;此标记将自动应用到垃圾邮件文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="fabfd-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-309">1 个月后删除</span><span class="sxs-lookup"><span data-stu-id="fabfd-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="fabfd-p132">永久删除 30 天之内的项目。用户可以恢复 up 14 天后他们正在删除这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fabfd-p132">Permanently deletes items that are 30 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="fabfd-312">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-312">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-313">个人;可以由用户应用此标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-314">1 年后删除</span><span class="sxs-lookup"><span data-stu-id="fabfd-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="fabfd-p133">永久删除 365 天之内的项目。用户可以恢复 up 14 天后他们正在删除这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fabfd-p133">Permanently deletes items that are 365 days old. Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="fabfd-317">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-317">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-318">个人;可以由用户应用此标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-319">从不删除</span><span class="sxs-lookup"><span data-stu-id="fabfd-319">Never Delete</span></span>  <br/> |<span data-ttu-id="fabfd-320">此标记，则会阻止项目删除保留策略。</span><span class="sxs-lookup"><span data-stu-id="fabfd-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="fabfd-321">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-321">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-322">个人;可以由用户应用此标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="fabfd-323">个人 1 年后移动到存档</span><span class="sxs-lookup"><span data-stu-id="fabfd-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="fabfd-324">将项目 1 年后移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="fabfd-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="fabfd-325">内置</span><span class="sxs-lookup"><span data-stu-id="fabfd-325">Built-in</span></span>  <br/> |<span data-ttu-id="fabfd-326">个人;可以由用户应用此标记。</span><span class="sxs-lookup"><span data-stu-id="fabfd-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="fabfd-p134"><sup>\*</sup>用户可以使用 Outlook 和 Outlook Web App 中的恢复已删除邮件工具已删除的邮件保留期，即默认情况下 14 天在 Exchange Online 中恢复已删除的邮件。管理员可以使用 Windows PowerShell 以增加最多 30 天内的已删除的邮件保留期限。有关详细信息，请参阅：[恢复已删除的 Outlook for Windows 中的项目](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)和[更改在 Exchange Online 邮箱的已删除的邮件保留期限](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="fabfd-p134"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook Web App to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online. An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days. For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="fabfd-p135">使用**可恢复邮件 14 天后移动到存档**保留标记可帮助免费设置用户的主邮箱中的可恢复的项目文件夹中的存储空间。当用户邮箱置于保持状态，这表示没有以往永久删除用户邮箱，这很有用。不将项目移动到存档邮箱，则可能将联系主邮箱中的可恢复项目文件夹的存储配额。有关此以及如何避免它的详细信息，请参阅[提高可恢复的项目上的邮箱配额保留](https://go.microsoft.com/fwlink/p/?LinkId=786479)。</span><span class="sxs-lookup"><span data-stu-id="fabfd-p135">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox. This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox. Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached. For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
