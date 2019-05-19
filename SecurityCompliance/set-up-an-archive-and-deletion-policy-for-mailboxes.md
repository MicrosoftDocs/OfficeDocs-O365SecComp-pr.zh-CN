---
title: 为 Office 365 组织中的邮箱设置存档和删除策略
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
description: 在 Office 365 中创建可自动将项目移动到用户的存档邮箱的存档和删除策略。
ms.openlocfilehash: ca43498d785f1a5525a8159e7e553bd36257a7c2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156704"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-office-365-organization"></a><span data-ttu-id="32147-103">为 Office 365 组织中的邮箱设置存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="32147-103">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>

 <span data-ttu-id="32147-104">在 Office 365 中, 管理员可以创建存档和删除策略, 以自动将项目移动到用户的存档邮箱, 并自动删除邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-104">In Office 365, admins can create an archiving and deletion policy that automatically moves items to a user's archive mailbox and automatically deletes items from the mailbox.</span></span> <span data-ttu-id="32147-105">管理员通过创建分配给邮箱的保留策略, 并在一段时间后将项目移动到用户的存档邮箱来实现此功能, 并在达到一定期限后从邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="32147-105">The admin does this by creating a retention policy that's assigned to mailboxes, and moves items to a user's archive mailbox after a certain period of time and that also deletes items from the mailbox after they reach a certain age limit.</span></span> <span data-ttu-id="32147-106">确定要移动或删除的项目以及发生此问题的实际规则称为保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-106">The actual rules that determine what items are moved or deleted and when that happens are called retention tags.</span></span> <span data-ttu-id="32147-107">保留标记链接到保留策略, 后者又分配给用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-107">Retention tags are linked to a retention policy, that in turn is assigned to a user's mailbox.</span></span> <span data-ttu-id="32147-108">保留标记将保留设置应用于用户邮箱中的单个邮件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="32147-108">A retention tag applies retention settings to individual messages and folders in a user's mailbox.</span></span> <span data-ttu-id="32147-109">它定义邮件在邮箱中保留的时间, 以及当邮件达到指定的保留期限时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="32147-109">It defines how long a message remains in the mailbox and what action is taken when the message reaches the specified retention age.</span></span> <span data-ttu-id="32147-110">当邮件达到其保留期限时, 会将其移动到用户的存档邮箱或将其删除。</span><span class="sxs-lookup"><span data-stu-id="32147-110">When a message reaches its retention age, it's either moved to the user's archive mailbox or it's deleted.</span></span> 
  
<span data-ttu-id="32147-111">本文中的步骤将设置名为 Alpine 房子的虚拟组织的存档和保留策略。</span><span class="sxs-lookup"><span data-stu-id="32147-111">The steps in this article will set up an archiving and retention policy for a fictitious organization named Alpine House.</span></span> <span data-ttu-id="32147-112">设置此策略包含以下任务:</span><span class="sxs-lookup"><span data-stu-id="32147-112">Setting up this policy includes the following tasks:</span></span>
  
- <span data-ttu-id="32147-113">为组织中的每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-113">Enabling an archive mailbox for every user in the organization.</span></span> <span data-ttu-id="32147-114">这样, 用户便可以添加邮箱存储, 并要求保留策略将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-114">This gives users addition mailbox storage, and is required so that a retention policy can move items to the archive mailbox.</span></span> <span data-ttu-id="32147-115">它还允许用户通过将项目移动到其存档邮箱来存储存档信息。</span><span class="sxs-lookup"><span data-stu-id="32147-115">It also let's a user store archival information by moving items to their archive mailbox.</span></span> 
    
- <span data-ttu-id="32147-116">创建三个用于执行以下操作的自定义保留标记:</span><span class="sxs-lookup"><span data-stu-id="32147-116">Creating three custom retention tags that do the following:</span></span> 
    
  - <span data-ttu-id="32147-117">自动将早于3年的项目移动到用户的存档邮箱中。</span><span class="sxs-lookup"><span data-stu-id="32147-117">Automatically moves items that are 3 years old to the user's archive mailbox.</span></span> <span data-ttu-id="32147-118">将项目移动到存档邮箱可释放用户主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="32147-118">Moving items to the archive mailbox frees up space in a user's primary mailbox.</span></span>
    
  - <span data-ttu-id="32147-119">自动从 "已删除邮件" 文件夹中删除5年以前的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-119">Automatically deletes items that are 5 years old from the Deleted Items folder.</span></span> <span data-ttu-id="32147-120">这还将释放用户的主邮箱中的空间。</span><span class="sxs-lookup"><span data-stu-id="32147-120">This also frees up space in the user's primary mailbox.</span></span> <span data-ttu-id="32147-121">如果需要, 用户将有机会恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="32147-121">User's will have the opportunity to recover these items if necessary.</span></span> <span data-ttu-id="32147-122">有关更多详细信息, 请参阅 "[详细信息](#more-information)" 部分中的脚注。</span><span class="sxs-lookup"><span data-stu-id="32147-122">See the footnote in the [More information](#more-information) section for more details.</span></span> 
    
  - <span data-ttu-id="32147-123">自动 (和永久) 从主邮箱和存档邮箱中删除7年以前的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-123">Automatically (and permanently) deletes items that are 7 years old from both the primary and archive mailbox.</span></span> <span data-ttu-id="32147-124">由于合规性管理法规的原因, 某些组织需要在一定时间内保留电子邮件。</span><span class="sxs-lookup"><span data-stu-id="32147-124">Because of compliance regulations, some organization's are required to retain email for a certain period of time.</span></span> <span data-ttu-id="32147-125">此时间段到期后, 组织可能希望永久删除这些项目用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-125">After this time period expires, an organization might want to permanently remove these items user mailboxes.</span></span> 
    
- <span data-ttu-id="32147-126">创建新的保留策略并向其添加新的自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-126">Creating a new retention policy and adding the new custom retention tags to it.</span></span> <span data-ttu-id="32147-127">此外, 还将向新的保留策略中添加内置保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-127">Additionally, you'll also add built-in retention tags to the new retention policy.</span></span> <span data-ttu-id="32147-128">这包括用户可分配给其邮箱中的项目的个人标记。</span><span class="sxs-lookup"><span data-stu-id="32147-128">This includes personal tags that users can assign to items in their mailbox.</span></span> <span data-ttu-id="32147-129">您还将添加保留标记, 将项目从用户主邮箱中的 "可恢复的项目" 文件夹移动到其存档邮箱中的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="32147-129">You'll also add a retention tag that moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="32147-130">这有助于在用户的 "可恢复的项目" 文件夹中的邮箱置于保留状态时释放这些空间。</span><span class="sxs-lookup"><span data-stu-id="32147-130">This helps free up space in a user's Recoverable Items folder when their mailbox is placed on hold.</span></span>
    
<span data-ttu-id="32147-131">您可以按照本文中的部分或全部步骤操作, 为自己组织中的邮箱设置存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="32147-131">You can follow some or all of the steps in this article to set up an archive and deletion policy for mailboxes in your own organization.</span></span> <span data-ttu-id="32147-132">我们建议您先对几个邮箱测试此过程, 然后再在组织中的所有邮箱上实施此过程。</span><span class="sxs-lookup"><span data-stu-id="32147-132">We recommend that you test this process on a few mailboxes before implementing it on all mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="32147-133">开始之前</span><span class="sxs-lookup"><span data-stu-id="32147-133">Before you begin</span></span>

- <span data-ttu-id="32147-134">您必须是 Office 365 组织中的全局管理员才能执行本主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="32147-134">You have to be a global administrator in your Office 365 organization to perform the steps in this topic.</span></span> 
    
-  <span data-ttu-id="32147-135">当您在 Office 365 中创建新用户帐户并为用户分配 Exchange Online 许可证时, 系统会自动为该用户创建一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-135">When you create a new user account in Office 365 and assign the user an Exchange Online license, a mailbox is automatically created for the user.</span></span> <span data-ttu-id="32147-136">创建邮箱后, 会自动为其分配一个名为 "默认 MRM 策略" 的默认保留策略。</span><span class="sxs-lookup"><span data-stu-id="32147-136">When the mailbox is created, it's automatically assigned a default retention policy, named Default MRM Policy.</span></span> <span data-ttu-id="32147-137">在本文中, 您将创建一个新的保留策略, 然后将其分配给用户邮箱, 替换默认的 MRM 策略。</span><span class="sxs-lookup"><span data-stu-id="32147-137">In this article, you will create a new retention policy and then assign it to user mailboxes, replacing the Default MRM policy.</span></span> <span data-ttu-id="32147-138">每次只能向一个邮箱分配一个保留策略。</span><span class="sxs-lookup"><span data-stu-id="32147-138">A mailbox can have only one retention policy assigned to it at any one time.</span></span>
    
- <span data-ttu-id="32147-139">若要了解有关 Exchange Online 中的保留标记和保留策略的详细信息, 请参阅[保留标记和保留策略](https://go.microsoft.com/fwlink/p/?LinkId=404424)。</span><span class="sxs-lookup"><span data-stu-id="32147-139">To learn more about retention tags and retention policies in Exchange Online, see [Retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424).</span></span>
    
## <a name="step-1-enable-archive-mailboxes-for-users"></a><span data-ttu-id="32147-140">步骤 1: 为用户启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="32147-140">Step 1: Enable archive mailboxes for users</span></span>

<span data-ttu-id="32147-141">第一步是为组织中的每个用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-141">The first step is to enable the archive mailbox for each user in your organization.</span></span> <span data-ttu-id="32147-142">必须启用用户的存档邮箱, 这样, 具有 "移动到存档" 保留操作的保留标记可以在保留期限到期后移动项目。</span><span class="sxs-lookup"><span data-stu-id="32147-142">A user's archive mailbox has to be enabled so that a retention tag with a "Move to Archive" retention action can move the item after the retention age expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="32147-143">您可以在此过程中的任何时间启用存档邮箱, 只要在完成该过程之前在某个时刻启用了这些邮箱即可。</span><span class="sxs-lookup"><span data-stu-id="32147-143">You can enable archive mailboxes any time during this process, just as long as they're enabled at some point before you complete the process.</span></span> <span data-ttu-id="32147-144">如果未启用存档邮箱, 则不会对分配有存档策略的任何项目执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="32147-144">If an archive mailbox isn't enabled, no action is taken on any items that have an archive policy assigned to it.</span></span> 
  
1. <span data-ttu-id="32147-145">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="32147-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="32147-146">Sign in to Office 365 using your global administrator account.</span><span class="sxs-lookup"><span data-stu-id="32147-146">Sign in to Office 365 using your global administrator account.</span></span>
    
    
3. <span data-ttu-id="32147-147">在安全 & 合规性中心中, 转到 "**数据调控** \> **存档**"。</span><span class="sxs-lookup"><span data-stu-id="32147-147">In the Security & Compliance Center, go to **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="32147-148">将显示组织中的邮箱列表以及相应的存档邮箱是否已启用或已禁用。</span><span class="sxs-lookup"><span data-stu-id="32147-148">A list of the mailboxes in your organization is displayed and whether the corresponding archive mailbox is enabled or disabled.</span></span> 
    
4. <span data-ttu-id="32147-149">通过单击列表中的第一个邮箱来选择所有邮箱, 按住**Shift**键, 然后单击列表中的最后一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-149">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="32147-150">此步骤假定未启用任何存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-150">This step assumes that no archive mailboxes are enabled.</span></span> <span data-ttu-id="32147-151">如果有任何邮箱启用了存档, 请按住**Ctrl**键, 然后单击每个具有已禁用的存档邮箱的邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-151">If you have any mailboxes with the archive enabled, hold down the **Ctrl** key and click each mailbox that has a disabled archive mailbox.</span></span> <span data-ttu-id="32147-152">或者, 可以单击 "**存档邮箱**" 列标题, 根据是否启用或禁用存档邮箱来对行进行排序, 以便更轻松地选择邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-152">Or you can click the **Archive mailbox** column header to sort the rows based on whether the archive mailbox is enabled or disabled to make it easier to select mailboxes.</span></span> 
  
5. <span data-ttu-id="32147-153">在详细信息窗格中的 "**批量编辑**" 下, 单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="32147-153">In the details pane, under **Bulk Edit**, click **Enable**.</span></span>
    
    <span data-ttu-id="32147-154">将显示一条警告, 指出早于两年的项目将移至新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-154">A warning is displayed saying that items that are older than two years will be moved to the new archive mailbox.</span></span> <span data-ttu-id="32147-155">这是因为, 在创建新的用户邮箱时, 为其分配的默认保留策略具有保留期为2年的存档默认策略标记。</span><span class="sxs-lookup"><span data-stu-id="32147-155">This is because the default retention policy that's assigned a new user mailbox when it's created has an archive default policy tag that has a retention age of 2 years.</span></span> <span data-ttu-id="32147-156">您将在步骤2中创建的自定义存档默认策略标记的保留时间为3年。</span><span class="sxs-lookup"><span data-stu-id="32147-156">The custom archive default policy tag that you'll create in Step 2 has a retention age of 3 years.</span></span> <span data-ttu-id="32147-157">这表示3年或更早的项目将移至存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-157">That means items that are 3 years or older will be moved to the archive mailbox.</span></span>
    
6. <span data-ttu-id="32147-158">单击 **"是"** 关闭警告消息, 并启动启用每个所选邮箱的存档邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="32147-158">Click **Yes** to close the warning message and start the process to enable the archive mailbox for each selected mailbox.</span></span> 
    
7. <span data-ttu-id="32147-159">完成该过程后, 单击 "**刷新** ![刷新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) " 以更新 "**存档**" 页上的列表。</span><span class="sxs-lookup"><span data-stu-id="32147-159">When the process is complete, click **Refresh** ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) to update the list on the **Archive** page.</span></span> 
    
    <span data-ttu-id="32147-160">为组织中的所有用户启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-160">The archive mailbox is enabled for all user's in your organization.</span></span>
    
    ![已启用存档邮箱的邮箱的列表](media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)
  
8. <span data-ttu-id="32147-162">保持安全 & 合规性中心处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="32147-162">Leave the Security & Compliance Center open.</span></span> <span data-ttu-id="32147-163">你将在下一步中使用它。</span><span class="sxs-lookup"><span data-stu-id="32147-163">You'll use it in the next step.</span></span>
    
## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a><span data-ttu-id="32147-164">步骤 2: 为存档和删除策略创建新的保留标记</span><span class="sxs-lookup"><span data-stu-id="32147-164">Step 2: Create new retention tags for the archive and deletion policies</span></span>

<span data-ttu-id="32147-165">在此步骤中, 您将创建前面所述的三个自定义保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-165">In this step, you'll create the three custom retention tags that were previously described.</span></span>
  
- <span data-ttu-id="32147-166">Alpine 房屋3年后移动到存档 (自定义存档策略)</span><span class="sxs-lookup"><span data-stu-id="32147-166">Alpine House 3 Year Move to Archive (custom archive policy)</span></span>
    
- <span data-ttu-id="32147-167">Alpine 住宅7年永久删除 (自定义删除策略)</span><span class="sxs-lookup"><span data-stu-id="32147-167">Alpine House 7 Year Permanently Delete (custom deletion policy)</span></span>
    
- <span data-ttu-id="32147-168">Alpine 房子删除的项目5年删除并允许恢复 ("已删除邮件" 文件夹的自定义标记)</span><span class="sxs-lookup"><span data-stu-id="32147-168">Alpine House Deleted Items 5 Years Delete and Allow Recovery (custom tag for the Deleted Items folder)</span></span>
    
<span data-ttu-id="32147-169">若要创建新的保留标记, 您将在 Exchange Online 组织中使用 Exchange 管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="32147-169">To create new retention tags, you'll use the Exchange admin center (EAC) in your Exchange Online organization.</span></span>
  
1. <span data-ttu-id="32147-170">在 "安全 & 合规性中心" 中, 单击左上角的应用启动器, 然后单击 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="32147-170">In the Security & Compliance Center, click the app launcher  in the upper left corner, and then click the **Admin** tile .</span></span> 
    
2. <span data-ttu-id="32147-171">在 Microsoft 365 管理中心的左侧导航窗格中, 单击 "**管理中心**", 然后单击 " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="32147-171">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers**, and then click **Exchange**.</span></span>
    
    ![屏幕截图显示了使用 "管理中心" 选项展开并选择 "Exchange" 的 Microsoft 365 管理中心。](media/47399df2-0bc4-42e2-b183-07750a46bc68.png)
  
3. <span data-ttu-id="32147-173">在 EAC 中, 转到 "**合规性管理** \> " "**保留标记**"</span><span class="sxs-lookup"><span data-stu-id="32147-173">In the EAC, go to **Compliance management** \> **Retention tags**</span></span>
    
    <span data-ttu-id="32147-174">将显示您的组织的保留标记列表。</span><span class="sxs-lookup"><span data-stu-id="32147-174">A list of the retention tags for your organization is displayed.</span></span>
    
### <a name="create-a-custom-archive-default-policy-tag"></a><span data-ttu-id="32147-175">创建自定义存档默认策略标记</span><span class="sxs-lookup"><span data-stu-id="32147-175">Create a custom archive default policy tag</span></span>
  
<span data-ttu-id="32147-176">首先, 创建一个自定义存档默认策略标记 (DPT), 该标记将在3年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-176">First, you'll create a custom archive default policy tag (DPT) that will move items to the archive mailbox after 3 years.</span></span> 
  
1. <span data-ttu-id="32147-177">在 "**保留标记**" 页上, 单击 "**新建标记**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)", 然后选择 "**自动应用于整个邮箱 (默认)**"。</span><span class="sxs-lookup"><span data-stu-id="32147-177">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="32147-178">在 "**自动应用于整个邮箱 (默认)** " 页上, 填写下列字段:</span><span class="sxs-lookup"><span data-stu-id="32147-178">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![创建新存档的设置默认策略标记](media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
1. <span data-ttu-id="32147-180">**名称**为新的保留标记键入一个名称。</span><span class="sxs-lookup"><span data-stu-id="32147-180">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="32147-181">**保留操作**选择 "**移动到存档**" 可在保留期到期时将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-181">**Retention action** Select **Move to Archive** to move items to the archive mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="32147-182">**保留期**选择 **"当项目达到以下期限 (天)**", 然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="32147-182">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="32147-183">在这种情况下, 项目将在1095天 (3 年) 后移至存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-183">For this scenario, items will be moved to the archive mailbox after 1095 days (3 years).</span></span>
    
4. <span data-ttu-id="32147-184">**注释**Optional键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="32147-184">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="32147-185">单击 "**保存**" 以创建自定义存档 DPT。</span><span class="sxs-lookup"><span data-stu-id="32147-185">Click **Save** to create the custom archive DPT.</span></span> 
    
    <span data-ttu-id="32147-186">新的存档 DPT 显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="32147-186">The new archive DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-deletion-default-policy-tag"></a><span data-ttu-id="32147-187">创建自定义删除默认策略标记</span><span class="sxs-lookup"><span data-stu-id="32147-187">Create a custom deletion default policy tag</span></span>
  
<span data-ttu-id="32147-188">接下来, 你将创建另一个自定义 DPT, 但此操作将成为一个删除策略, 该策略将在7年后永久删除项目。</span><span class="sxs-lookup"><span data-stu-id="32147-188">Next, you'll create another custom DPT but this one will be a deletion policy that permanently deletes items after 7 years.</span></span>
  
1. <span data-ttu-id="32147-189">在 "**保留标记**" 页上, 单击 "**新建标记**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)", 然后选择 "**自动应用于整个邮箱 (默认)**"。</span><span class="sxs-lookup"><span data-stu-id="32147-189">On the **Retention tags** page, click **New tag**![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to entire mailbox (default)**.</span></span> 
    
2. <span data-ttu-id="32147-190">在 "**自动应用于整个邮箱 (默认)** " 页上, 填写下列字段:</span><span class="sxs-lookup"><span data-stu-id="32147-190">On the **New tag applied automatically to entire mailbox (default)** page, complete the following fields:</span></span> 
    
    ![创建新的删除默认策略标记的设置](media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
1. <span data-ttu-id="32147-192">**名称**为新的保留标记键入一个名称。</span><span class="sxs-lookup"><span data-stu-id="32147-192">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="32147-193">**保留操作**选择 "**永久删除**", 以便在保留期到期时清除邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-193">**Retention action** Select **Permanently Delete** to purge items from the mailbox when the retention period expires.</span></span> 
    
3. <span data-ttu-id="32147-194">**保留期**选择 **"当项目达到以下期限 (天)**", 然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="32147-194">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="32147-195">在这种情况下, 将在2555天 (7 年) 后清除项目。</span><span class="sxs-lookup"><span data-stu-id="32147-195">For this scenario, items will be purged after 2555 days (7 years).</span></span>
    
4. <span data-ttu-id="32147-196">**注释**Optional键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="32147-196">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="32147-197">单击 "**保存**" 以创建自定义删除 DPT。</span><span class="sxs-lookup"><span data-stu-id="32147-197">Click **Save** to create the custom deletion DPT.</span></span> 
    
    <span data-ttu-id="32147-198">新的删除 DPT 将显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="32147-198">The new deletion DPT is displayed in the list of retention tags.</span></span>
    
### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a><span data-ttu-id="32147-199">为 "已删除邮件" 文件夹创建自定义保留策略标记</span><span class="sxs-lookup"><span data-stu-id="32147-199">Create a custom retention policy tag for the Deleted Items folder</span></span>
  
<span data-ttu-id="32147-200">您要创建的最后一个保留标记是 "已删除邮件" 文件夹的自定义保留策略标记 (RPT)。</span><span class="sxs-lookup"><span data-stu-id="32147-200">The last retention tag that you'll create is a custom retention policy tag (RPT) for the Deleted Items folder.</span></span> <span data-ttu-id="32147-201">此标记将在5年后删除 "已删除邮件" 文件夹中的项目, 并在用户可以使用 "恢复已删除邮件" 工具恢复项目时提供恢复期。</span><span class="sxs-lookup"><span data-stu-id="32147-201">This tag will delete items in the Deleted Items folder after 5 years, and provides a recovery period when users can use the Recover Deleted Items tool to recover an item.</span></span>
  
1. <span data-ttu-id="32147-202">在 "**保留标记**" 页上, 单击 "**新建标记** ![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)", 然后选择 "**自动应用到默认文件夹**"。</span><span class="sxs-lookup"><span data-stu-id="32147-202">On the **Retention tags** page, click **New tag** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif), and then select **applied automatically to a default folder**.</span></span> 
    
2. <span data-ttu-id="32147-203">在 "**自动应用于默认文件夹**" 页上的 "新标记" 中, 填写下列字段:</span><span class="sxs-lookup"><span data-stu-id="32147-203">On the **New tag applied automatically to a default folder** page, complete the following fields:</span></span> 
    
    ![为 "已删除邮件" 文件夹创建新的保留策略标记的设置](media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
1. <span data-ttu-id="32147-205">**名称**为新的保留标记键入一个名称。</span><span class="sxs-lookup"><span data-stu-id="32147-205">**Name** Type a name for the new retention tag.</span></span> 
    
2. <span data-ttu-id="32147-206">**将此标记应用于以下默认文件夹**在下拉列表中, 选择 "**已删除邮件**"。</span><span class="sxs-lookup"><span data-stu-id="32147-206">**Apply this tag to the following default folder** In the drop-down list, select **Deleted Items**.</span></span>
    
3. <span data-ttu-id="32147-207">**保留操作**选择 "**删除并允许恢复**" 在保留期到期时删除项目, 但允许用户恢复已删除项目保留期 (默认为14天) 内的已删除项目。</span><span class="sxs-lookup"><span data-stu-id="32147-207">**Retention action** Select **Delete and Allow Recovery** to delete items when the retention period expires, but allow users to recover a deleted item within the deleted item retention period (which by default is 14 days).</span></span> 
    
4. <span data-ttu-id="32147-208">**保留期**选择 **"当项目达到以下期限 (天)**", 然后输入保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="32147-208">**Retention period** Select **When the item reaches the following age (in days)**, and then enter the duration of the retention period.</span></span> <span data-ttu-id="32147-209">在这种情况下, 将在1825天 (5 年) 后删除项目。</span><span class="sxs-lookup"><span data-stu-id="32147-209">For this scenario, items will be deleted after 1825 days (5 years).</span></span>
    
5. <span data-ttu-id="32147-210">**注释**Optional键入说明自定义保留标记用途的注释。</span><span class="sxs-lookup"><span data-stu-id="32147-210">**Comment** (Optional) Type a comment that explains the purpose of the custom retention tag.</span></span> 
    
3. <span data-ttu-id="32147-211">单击 "**保存**" 为 "已删除邮件" 文件夹创建自定义 RPT。</span><span class="sxs-lookup"><span data-stu-id="32147-211">Click **Save** to create the custom RPT for the Deleted Items folder.</span></span> 
    
    <span data-ttu-id="32147-212">新 RPT 将显示在保留标记列表中。</span><span class="sxs-lookup"><span data-stu-id="32147-212">The new RPT is displayed in the list of retention tags.</span></span>

## <a name="step-3-create-a-new-retention-policy"></a><span data-ttu-id="32147-213">步骤 3: 创建新的保留策略</span><span class="sxs-lookup"><span data-stu-id="32147-213">Step 3: Create a new retention policy</span></span>

<span data-ttu-id="32147-214">创建自定义保留标记后, 下一步是创建新的保留策略并添加保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-214">After you create the custom retention tags, the next step is to create a new retention policy and add the retention tags.</span></span> <span data-ttu-id="32147-215">您将添加您在步骤2中创建的三个自定义保留标记, 以及在第一节中提到的内置标记。</span><span class="sxs-lookup"><span data-stu-id="32147-215">You'll add the three custom retention tags that you created in Step 2, and the built-in tags that were mentioned in the first section.</span></span> <span data-ttu-id="32147-216">在步骤4中, 将此新的保留策略分配给用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-216">In Step 4, you'll assign this new retention policy to user mailboxes.</span></span>
  
1. <span data-ttu-id="32147-217">在 EAC 中, 转到 "**合规性管理** \> "**保留策略**。</span><span class="sxs-lookup"><span data-stu-id="32147-217">In the EAC, go to **Compliance management** \> **Retention policies**.</span></span>
    
2. <span data-ttu-id="32147-218">在 "**保留策略**" 页上\*\*\*\* ![, 单击 "](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)新建新图标"。</span><span class="sxs-lookup"><span data-stu-id="32147-218">On the **Retention policies** page, click **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
3. <span data-ttu-id="32147-219">在 "**名称**" 框中, 为新的保留策略键入一个名称;例如, **Alpine 房屋存档和删除策略**。</span><span class="sxs-lookup"><span data-stu-id="32147-219">In the **Name** box, type a name for the new retention policy; for example, **Alpine House Archive and Deletion Policy**.</span></span> 
    
4. <span data-ttu-id="32147-220">在 **"保留标记**" 下, 单击](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)"**添加** ![新图标"。</span><span class="sxs-lookup"><span data-stu-id="32147-220">Under **Retention tags**, click **Add** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif).</span></span>
    
    <span data-ttu-id="32147-221">将显示组织中的保留标记列表。</span><span class="sxs-lookup"><span data-stu-id="32147-221">A list of the retention tags in your organization is displayed.</span></span> <span data-ttu-id="32147-222">注释将显示您在步骤2中创建的自定义标记。</span><span class="sxs-lookup"><span data-stu-id="32147-222">Note the custom tags that you created in Step 2 are displayed.</span></span>
    
5. <span data-ttu-id="32147-223">添加以下屏幕截图中突出显示的9个保留标记 ("[详细信息](#more-information)" 部分中将更详细地介绍这些标记)。</span><span class="sxs-lookup"><span data-stu-id="32147-223">Add the 9 retention tags that are highlighted in the following screenshot (these tags are described in more detail in the [More information](#more-information) section).</span></span> <span data-ttu-id="32147-224">若要添加保留标记, 请将其选中, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="32147-224">To add a retention tag, select it and then click **Add**.</span></span> 
    
    ![将保留标记添加到新的保留策略](media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > <span data-ttu-id="32147-226">您可以选择多个保留标记, 方法是按住**Ctrl**键, 然后单击每个标记。</span><span class="sxs-lookup"><span data-stu-id="32147-226">You can select multiple retention tags by holding down the **Ctrl** key and then clicking each tag.</span></span> 
  
6. <span data-ttu-id="32147-227">添加保留标记后, 单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="32147-227">After you've added the retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="32147-228">在 "**新建保留策略**" 页上, 单击 "**保存**" 以创建新策略。</span><span class="sxs-lookup"><span data-stu-id="32147-228">On the **New retention policy** page, click **Save** to create the new policy.</span></span> 
    
    <span data-ttu-id="32147-229">新的保留策略将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="32147-229">The new retention policy is displayed in the list.</span></span> <span data-ttu-id="32147-230">选择它可在详细信息窗格中显示链接到它的保留标记。</span><span class="sxs-lookup"><span data-stu-id="32147-230">Select it to display the retention tags linked to it in the details pane.</span></span>
    
    ![新的保留策略和链接的保留标记列表](media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a><span data-ttu-id="32147-232">步骤 4: 将新的保留策略分配给用户邮箱</span><span class="sxs-lookup"><span data-stu-id="32147-232">Step 4: Assign the new retention policy to user mailboxes</span></span>

<span data-ttu-id="32147-233">创建新邮箱时, 默认情况下会为其分配一个名为 "默认 MRM 策略" 的保留策略。</span><span class="sxs-lookup"><span data-stu-id="32147-233">When a new mailbox is created, a retention policy named Default MRM policy is assigned to it by default.</span></span> <span data-ttu-id="32147-234">在此步骤中, 您将替换此保留策略 (因为一个邮箱只能分配有一个保留策略), 方法是将您在步骤3中创建的新保留策略分配给组织中的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-234">In this step, you'll replace this retention policy (because a mailbox can have only one retention policy assigned to it) by assigning the new retention policy that you created in Step 3 to the user mailboxes in your organization.</span></span> <span data-ttu-id="32147-235">此步骤假定您将新策略分配给组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-235">This step assumes that you'll assign the new policy to all mailboxes in your organization.</span></span>
  
1. <span data-ttu-id="32147-236">在 EAC 中, 转到 "**收件人** \> " "**邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="32147-236">In the EAC, go to **Recipients** \> **Mailboxes**.</span></span>
    
    <span data-ttu-id="32147-237">将显示组织中所有用户邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="32147-237">A list of all user mailboxes in your organization is displayed.</span></span> 
    
2. <span data-ttu-id="32147-238">通过单击列表中的第一个邮箱来选择所有邮箱, 按住**Shift**键, 然后单击列表中的最后一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-238">Select all the mailboxes by clicking on the first one in the list, holding down the **Shift** key, and then clicking the last one in the list.</span></span> 
    
3. <span data-ttu-id="32147-239">在 EAC 右侧的 "详细信息" 窗格中的 "**批量编辑**" 下, 单击 "**更多选项**"。</span><span class="sxs-lookup"><span data-stu-id="32147-239">In the details pane on the right side of the EAC, under **Bulk Edit**, click **More options**.</span></span>
    
4. <span data-ttu-id="32147-240">在“保留策略”\*\*\*\* 下，单击“更新”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="32147-240">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="32147-241">在 "**批量分配保留策略**" 页上的 "**选择保留策略"** 下拉列表中, 选择您在步骤3中创建的保留策略;例如, **Alpine 房子存档和保留策略**。</span><span class="sxs-lookup"><span data-stu-id="32147-241">On the **Bulk assign retention policy** page, in the **Select the retention policy** drop-down list, select the retention policy that you created in Step 3; for example, **Alpine House Archive and Retention Policy**.</span></span>
    
6. <span data-ttu-id="32147-242">单击 "**保存**" 以保存新的保留策略分配。</span><span class="sxs-lookup"><span data-stu-id="32147-242">Click **Save** to save the new retention policy assignment.</span></span> 
    
7. <span data-ttu-id="32147-243">若要验证是否已将新的保留策略分配给邮箱, 您可以执行以下操作: 在 "邮箱" 页上选择一个邮箱, 然后单击 "编辑"。</span><span class="sxs-lookup"><span data-stu-id="32147-243">To verify that the new retention policy was assigned to mailboxes, you can do the following: select a mailbox on the Mailboxes page, and then click Edit.</span></span> 
    
1. <span data-ttu-id="32147-244">在 "**邮箱**" 页上选择一个邮箱, 然后单击 "](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png)**编辑** ![编辑"。</span><span class="sxs-lookup"><span data-stu-id="32147-244">Select a mailbox on the **Mailboxes** page, and then click **Edit** ![Edit](media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png).</span></span> 
    
2. <span data-ttu-id="32147-245">在所选用户的 "邮箱属性" 页上, 单击 "**邮箱功能**"。</span><span class="sxs-lookup"><span data-stu-id="32147-245">On the mailbox properties page for the selected user, click **Mailbox features**.</span></span>
    
    <span data-ttu-id="32147-246">分配给邮箱的新策略的名称将显示在 "**保留策略**" 下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="32147-246">The name of the new policy assigned to the mailbox is displayed in the **Retention policy** drop-down list.</span></span> 

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a><span data-ttu-id="32147-247">Optional步骤 5: 运行托管文件夹助理以应用新设置</span><span class="sxs-lookup"><span data-stu-id="32147-247">(Optional) Step 5: Run the Managed Folder Assistant to apply the new settings</span></span>

<span data-ttu-id="32147-248">在步骤4中对邮箱应用新的保留策略后, 在 Exchange Online 中最长可能需要7天, 才能将新的保留设置应用于邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-248">After you apply the new retention policy to mailboxes in Step 4, it can take up to 7 days in Exchange Online for the new retention settings to be applied to the mailboxes.</span></span> <span data-ttu-id="32147-249">这是因为称为 "托管文件夹助理" 的进程每7天处理一次邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-249">This is because a process called the Managed Folder Assistant processes mailboxes once every 7 days.</span></span> <span data-ttu-id="32147-250">您可以通过在 Exchange Online PowerShell 中运行**start-managedfolderassistant** cmdlet 来强制执行此操作, 而不是等待托管文件夹助理运行。</span><span class="sxs-lookup"><span data-stu-id="32147-250">Instead of waiting for the Managed Folder Assistant to run, you can force this to happen by running the **Start-ManagedFolderAssistant** cmdlet in Exchange Online PowerShell.</span></span> 
  
 <span data-ttu-id="32147-251">**运行托管文件夹助理时, 会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="32147-251">**What happens when you run the Managed Folder Assistant?**</span></span> <span data-ttu-id="32147-252">它通过检查邮箱中的项目并确定它们是否受保留, 来应用保留策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="32147-252">It applies the settings in the retention policy by inspecting items in the mailbox and determining whether they're subject to retention.</span></span> <span data-ttu-id="32147-253">然后, 该示例使用适当的保留标记将受保留的项目标记为保留, 然后对超过保留期限的项目执行指定的保留操作。</span><span class="sxs-lookup"><span data-stu-id="32147-253">It then stamps items subject to retention with the appropriate retention tag, and then takes the specified retention action on items past their retention age.</span></span> 
  
<span data-ttu-id="32147-254">以下是连接到 Exchange Online PowerShell 的步骤, 然后在组织中的每个邮箱上运行托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="32147-254">Here are the steps to connect to Exchange Online PowerShell, and then run the Managed Folder Assistant on every mailbox in your organization.</span></span>
  
1. <span data-ttu-id="32147-255">在本地计算机上，打开 Windows PowerShell 并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="32147-255">On your local computer, open Windows PowerShell and run the following command.</span></span>
    
    ```
    $UserCredential = Get-Credential
    ```

    <span data-ttu-id="32147-256">在 " **Windows PowerShell 凭据请求**" 对话框中, 键入 Office 365 全局管理员帐户的用户名和密码, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="32147-256">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
2. <span data-ttu-id="32147-257">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="32147-257">Run the following command.</span></span>
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. <span data-ttu-id="32147-258">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="32147-258">Run the following command.</span></span>
    
    ```
    Import-PSSession $Session
    ```

4. <span data-ttu-id="32147-259">要验证您是否已连接至您的 Exchange Online 组织，请运行以下命令获取组织中所有邮箱的列表。</span><span class="sxs-lookup"><span data-stu-id="32147-259">To verify that you're connected to your Exchange Online organization, run the following command to get a list of all the mailboxes in your organization.</span></span>
    
    ```
    Get-Mailbox
    ```

    > [!NOTE]
    > <span data-ttu-id="32147-260">有关详细信息, 或者如果您在连接到 Exchange Online 组织时遇到问题, 请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)。</span><span class="sxs-lookup"><span data-stu-id="32147-260">For more information or if you have problems connecting to your Exchange Online organization, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283).</span></span> 
  
5. <span data-ttu-id="32147-261">运行以下两个命令, 为组织中的所有用户邮箱启动托管文件夹助理。</span><span class="sxs-lookup"><span data-stu-id="32147-261">Run the following two commands to start the Managed Folder Assistant for all user mailboxes in your organization.</span></span>
    
    ```
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

<span data-ttu-id="32147-262">就是这么简单。</span><span class="sxs-lookup"><span data-stu-id="32147-262">That's it!</span></span> <span data-ttu-id="32147-263">您已为 Alpine 房子组织设置存档和删除策略。</span><span class="sxs-lookup"><span data-stu-id="32147-263">You've set up an archive and deletion policy for the Alpine House organization.</span></span>
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a><span data-ttu-id="32147-264">Optional步骤 6: 将新的保留策略设为您的组织的默认策略</span><span class="sxs-lookup"><span data-stu-id="32147-264">(Optional) Step 6: Make the new retention policy the default for your organization</span></span>

<span data-ttu-id="32147-265">在步骤4中, 必须将新的保留策略分配给现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-265">In Step 4, you have to assign the new retention policy to existing mailboxes.</span></span> <span data-ttu-id="32147-266">但您可以配置 Exchange Online, 以便将新的保留策略分配给将来创建的新邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-266">But you can configure Exchange Online so that the new retention policy is assigned to new mailboxes that are created in the future.</span></span> <span data-ttu-id="32147-267">可通过使用 Exchange Online PowerShell 更新组织的默认邮箱计划来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="32147-267">You do this by using Exchange Online PowerShell to update your organization's default mailbox plan.</span></span> <span data-ttu-id="32147-268">*邮箱计划*是一个模板, 可自动配置新邮箱的属性。</span><span class="sxs-lookup"><span data-stu-id="32147-268">A *mailbox plan* is a template that automatically configures properties on new mailboxes.</span></span>  <span data-ttu-id="32147-269">在此可选步骤中, 您可以使用您在步骤3中创建的保留策略替换分配给邮箱计划的当前保留策略 (默认情况下是默认的 MRM 策略)。</span><span class="sxs-lookup"><span data-stu-id="32147-269">In this optional step, you can replace the current retention policy that's assigned to the mailbox plan (by default, the Default MRM Policy) with the retention policy that you created in Step 3.</span></span> <span data-ttu-id="32147-270">更新邮箱计划后, 新的保留策略将分配给新邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-270">After you update the mailbox plan, the new retention policy will be assigned to new mailboxes.</span></span>

1. <span data-ttu-id="32147-271">[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)或参阅第5步。</span><span class="sxs-lookup"><span data-stu-id="32147-271">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) or see Step 5.</span></span>

2. <span data-ttu-id="32147-272">运行以下命令以显示组织中的邮箱计划的相关信息。</span><span class="sxs-lookup"><span data-stu-id="32147-272">Run the following command to display information about the mailbox plans in your organization.</span></span>

    ```
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    <span data-ttu-id="32147-273">记下设置为默认的邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="32147-273">Note the mailbox plan that's set as the default.</span></span>

3. <span data-ttu-id="32147-274">运行以下命令, 将您在步骤3中创建的新保留策略 (例如, **Alpine 房子存档和保留策略**) 分配给默认邮箱计划。</span><span class="sxs-lookup"><span data-stu-id="32147-274">Run the following command to assign the new retention policy that you created in Step 3 (for example, **Alpine House Archive and Retention Policy**) to the default mailbox plan.</span></span> <span data-ttu-id="32147-275">本示例假定默认邮箱计划的名称为**ExchangeOnlineEnterprise**。</span><span class="sxs-lookup"><span data-stu-id="32147-275">This example assumes the name of the default mailbox plan is **ExchangeOnlineEnterprise**.</span></span>

    ```
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```
4. <span data-ttu-id="32147-276">您可以在步骤2中重新运行该命令, 以验证分配给默认邮箱计划的保留策略是否已更改。</span><span class="sxs-lookup"><span data-stu-id="32147-276">You can re-run the command in step 2 to verify that the retention policy assigned to the default mailbox plan was changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="32147-277">更多信息</span><span class="sxs-lookup"><span data-stu-id="32147-277">More information</span></span>

- <span data-ttu-id="32147-278">保留期限是如何计算的？</span><span class="sxs-lookup"><span data-stu-id="32147-278">How is retention age calculated?</span></span> <span data-ttu-id="32147-279">邮箱项目的保留期限是根据传递日期或邮件的创建日期计算的, 例如未发送但由用户创建的草稿邮件。</span><span class="sxs-lookup"><span data-stu-id="32147-279">The retention age of mailbox items is calculated from the date of delivery or the date of creation for items such as draft messages that aren't sent but are created by the user.</span></span> <span data-ttu-id="32147-280">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span><span class="sxs-lookup"><span data-stu-id="32147-280">When the Managed Folder Assistant processes items in a mailbox, it stamps a start date and an expiration date for all items that have retention tags with the Delete and Allow Recovery or Permanently Delete retention action.</span></span> <span data-ttu-id="32147-281">具有存档标记的项目标记有移动日期。</span><span class="sxs-lookup"><span data-stu-id="32147-281">Items that have an archive tag are stamped with a move date.</span></span> 
    
- <span data-ttu-id="32147-282">下表提供了有关添加到自定义保留策略的每个保留标记的详细信息, 该保留策略是按照本主题中的步骤创建的。</span><span class="sxs-lookup"><span data-stu-id="32147-282">The following table provides more information about each retention tag that is added to the custom retention policy that was created by following the steps in this topic.</span></span>
    
    |<span data-ttu-id="32147-283">**保留标记**</span><span class="sxs-lookup"><span data-stu-id="32147-283">**Retention tag**</span></span>|<span data-ttu-id="32147-284">**此标记执行的操作**</span><span class="sxs-lookup"><span data-stu-id="32147-284">**What this tag does**</span></span>|<span data-ttu-id="32147-285">**内置的还是自定义的？**</span><span class="sxs-lookup"><span data-stu-id="32147-285">**Built-in or custom?**</span></span>|<span data-ttu-id="32147-286">**Type**</span><span class="sxs-lookup"><span data-stu-id="32147-286">**Type**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="32147-287">Alpine 住宅3年后移动到存档</span><span class="sxs-lookup"><span data-stu-id="32147-287">Alpine House 3 Year Move to Archive</span></span>  <br/> |<span data-ttu-id="32147-288">将1095天 (3 年) 的项目移至存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-288">Moves items that are 1095 days (3 years) old to the archive mailbox.</span></span>  <br/> |<span data-ttu-id="32147-289">自定义 (请参阅[第2步: 为存档和删除策略创建新的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="32147-289">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="32147-290">默认策略标记 (存档);此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-290">Default Policy Tag (archive); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="32147-291">Alpine 住宅7年永久删除</span><span class="sxs-lookup"><span data-stu-id="32147-291">Alpine House 7 Year Permanently Delete</span></span>  <br/> |<span data-ttu-id="32147-292">将主邮箱或存档邮箱中的项目永久删除 (如果有7年)。</span><span class="sxs-lookup"><span data-stu-id="32147-292">Permanently deletes items in the primary mailbox or the archive mailbox when they are 7 years old.</span></span>  <br/> |<span data-ttu-id="32147-293">自定义 (请参阅[第2步: 为存档和删除策略创建新的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="32147-293">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="32147-294">默认策略标记 (删除);此标记将自动应用于整个邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-294">Default Policy Tag (deletion); this tag is automatically applied to the entire mailbox.</span></span>  <br/> |
    |<span data-ttu-id="32147-295">Alpine 房子删除的项目5年删除并允许恢复</span><span class="sxs-lookup"><span data-stu-id="32147-295">Alpine House Deleted Items 5 Years Delete and Allow Recovery</span></span>  <br/> |<span data-ttu-id="32147-296">从 "已删除邮件" 文件夹中删除5年的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-296">Deletes items from the Deleted Items folder that are 5 years old.</span></span> <span data-ttu-id="32147-297">用户在删除这些项目后, 可以在14天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="32147-297">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="32147-298">自定义 (请参阅[第2步: 为存档和删除策略创建新的保留标记](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span><span class="sxs-lookup"><span data-stu-id="32147-298">Custom (See [Step 2: Create new retention tags for the archive and deletion policies](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))</span></span>  <br/> |<span data-ttu-id="32147-299">保留策略标记 (已删除的项目);此标记将自动应用于 "已删除邮件" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-299">Retention Policy Tag (Deleted Items); this tag is automatically applied to items in the Deleted items folder.</span></span>  <br/> |
    |<span data-ttu-id="32147-300">可恢复的项目14天后移动到存档</span><span class="sxs-lookup"><span data-stu-id="32147-300">Recoverable Items 14 days Move to Archive</span></span>  <br/> |<span data-ttu-id="32147-301">将 "可恢复的项目" 文件夹中已有14天的项目移动到存档邮箱中的 "可恢复的项目" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="32147-301">Moves items that have been in the Recoverable Items folder for 14 days to the Recoverable Items folder in the archive mailbox.</span></span>  <br/> |<span data-ttu-id="32147-302">内置</span><span class="sxs-lookup"><span data-stu-id="32147-302">Built-in</span></span>  <br/> |<span data-ttu-id="32147-303">保留策略标记 (可恢复的项目);此标记将自动应用于 "可恢复的项目" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-303">Retention Policy Tag (Recoverable Items); this tag is automatically applied to items in the Recoverable Items folder.</span></span>  <br/> |
    |<span data-ttu-id="32147-304">垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="32147-304">Junk Email</span></span>  <br/> |<span data-ttu-id="32147-305">将 "垃圾邮件" 文件夹中的项目永久删除30天。</span><span class="sxs-lookup"><span data-stu-id="32147-305">Permanently deletes items that have been in the Junk Email folder for 30 days.</span></span> <span data-ttu-id="32147-306">用户在删除这些项目后, 可以在14天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="32147-306">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="32147-307">内置</span><span class="sxs-lookup"><span data-stu-id="32147-307">Built-in</span></span>  <br/> |<span data-ttu-id="32147-308">保留策略标记 (垃圾邮件);此标记将自动应用于 "垃圾邮件" 文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-308">Retention Policy Tag (Junk Email); this tag is automatically applied to items in Junk Email folder.</span></span>  <br/> |
    |<span data-ttu-id="32147-309">1 个月后删除</span><span class="sxs-lookup"><span data-stu-id="32147-309">1 Month Delete</span></span>  <br/> |<span data-ttu-id="32147-310">永久删除30天之前的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-310">Permanently deletes items that are 30 days old.</span></span> <span data-ttu-id="32147-311">用户在删除这些项目后, 可以在14天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="32147-311">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="32147-312">内置</span><span class="sxs-lookup"><span data-stu-id="32147-312">Built-in</span></span>  <br/> |<span data-ttu-id="32147-313">Personal用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="32147-313">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="32147-314">1 年后删除</span><span class="sxs-lookup"><span data-stu-id="32147-314">1 Year Delete</span></span>  <br/> |<span data-ttu-id="32147-315">永久删除365天以前的项目。</span><span class="sxs-lookup"><span data-stu-id="32147-315">Permanently deletes items that are 365 days old.</span></span> <span data-ttu-id="32147-316">用户在删除这些项目后, 可以在14天内恢复这些项目。<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="32147-316">Users can recover these items for up 14 days after they're deleted.<sup>\*</sup></span></span> <br/> |<span data-ttu-id="32147-317">内置</span><span class="sxs-lookup"><span data-stu-id="32147-317">Built-in</span></span>  <br/> |<span data-ttu-id="32147-318">Personal用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="32147-318">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="32147-319">从不删除</span><span class="sxs-lookup"><span data-stu-id="32147-319">Never Delete</span></span>  <br/> |<span data-ttu-id="32147-320">此标记阻止保留策略删除项目。</span><span class="sxs-lookup"><span data-stu-id="32147-320">This tag prevent items from being deleted by a retention policy.</span></span>  <br/> |<span data-ttu-id="32147-321">内置</span><span class="sxs-lookup"><span data-stu-id="32147-321">Built-in</span></span>  <br/> |<span data-ttu-id="32147-322">Personal用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="32147-322">Personal; this tag can be applied by users.</span></span>  <br/> |
    |<span data-ttu-id="32147-323">个人 1 年后移动到存档</span><span class="sxs-lookup"><span data-stu-id="32147-323">Personal 1 year move to archive</span></span>  <br/> |<span data-ttu-id="32147-324">在1年后将项目移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-324">Moves items to the archive mailbox after 1 year.</span></span>  <br/> |<span data-ttu-id="32147-325">内置</span><span class="sxs-lookup"><span data-stu-id="32147-325">Built-in</span></span>  <br/> |<span data-ttu-id="32147-326">Personal用户可以应用此标记。</span><span class="sxs-lookup"><span data-stu-id="32147-326">Personal; this tag can be applied by users.</span></span>  <br/> |
   
    > <span data-ttu-id="32147-327"><sup>\*</sup>用户可以使用 Outlook 和 web 上的 Outlook 中的 "恢复已删除邮件" 工具 (以前称为 "Outlook Web App") 在已删除项目的保留期内恢复已删除的项目, 这在 Exchange Online 中默认为14天。</span><span class="sxs-lookup"><span data-stu-id="32147-327"><sup>\*</sup> Users can use the Recover Deleted Items tool in Outlook and Outlook on the web (formerly known as Outlook Web App) to recover a deleted item within the deleted item retention period, which by default is 14 days in Exchange Online.</span></span> <span data-ttu-id="32147-328">管理员可以使用 Windows PowerShell 将已删除项目的保留期增加到最多30天。</span><span class="sxs-lookup"><span data-stu-id="32147-328">An administrator can use Windows PowerShell to increase the deleted item retention period to a maximum of 30 days.</span></span> <span data-ttu-id="32147-329">有关详细信息, 请参阅:[在 Outlook For Windows 中恢复已删除项目](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)并[在 Exchange Online 中更改邮箱的已删除邮件保留期](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span><span class="sxs-lookup"><span data-stu-id="32147-329">For more information, see: [Recover deleted items in Outlook for Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) and [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940)</span></span>
  
- <span data-ttu-id="32147-330">使用**可恢复的项目14天后移动到存档**保留标记有助于释放用户主邮箱中的 "可恢复的项目" 文件夹中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="32147-330">Using the **Recoverable Items 14 days Move to Archive** retention tag helps free up storage space in the Recoverable Items folder in the user's primary mailbox.</span></span> <span data-ttu-id="32147-331">当用户的邮箱置于保留状态时, 这很有用, 这意味着永远不会永久删除该用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="32147-331">This is useful when a user's mailbox is placed on hold, which means nothing is ever permanently deleted the user's mailbox.</span></span> <span data-ttu-id="32147-332">如果不将项目移动到存档邮箱, 则可能会达到主邮箱中的 "可恢复的项目" 文件夹的存储配额。</span><span class="sxs-lookup"><span data-stu-id="32147-332">Without moving items to the archive mailbox, it's possible the storage quota for the Recoverable Items folder in the primary mailbox will be reached.</span></span> <span data-ttu-id="32147-333">有关此操作以及如何避免此情况的详细信息, 请参阅[增大保留邮箱的可恢复邮件配额](https://go.microsoft.com/fwlink/p/?LinkId=786479)。</span><span class="sxs-lookup"><span data-stu-id="32147-333">For more information about this and how to avoid it, see [Increase the Recoverable Items quota for mailboxes on hold](https://go.microsoft.com/fwlink/p/?LinkId=786479).</span></span>
