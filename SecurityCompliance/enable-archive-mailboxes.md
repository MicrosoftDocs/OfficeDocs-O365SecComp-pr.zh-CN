---
title: Office 365 安全性的存档邮箱启用&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
description: 使用 Office 365 安全性&amp;合规性中心以启用存档邮箱以支持组织的邮件保留，电子数据展示，并保留要求。
ms.openlocfilehash: 5ba578ba611f619194ac4f475121bd485b75f9e0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525495"
---
# <a name="enable-archive-mailboxes-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="24bc4-103">Office 365 安全性的存档邮箱启用&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="24bc4-103">Enable archive mailboxes in the Office 365 Security &amp; Compliance Center</span></span>
  
<span data-ttu-id="24bc4-p101">存档 （也称为就地存档） 的 Office 365 中为用户提供其他邮箱存储空间。存档邮箱中打开后，用户可以访问并在其存档邮箱中存储的邮件，使用 Microsoft Outlook 和 Outlook Web 应用程序用户也可以移动或复制其主邮箱和其存档邮箱之间的邮件。他们可以通过使用恢复已删除邮件工具从其存档邮箱中可恢复邮件文件夹恢复已删除的项目。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p101">Archiving in Office 365 (also called In-Place Archiving) provides users with additional mailbox storage space. After you turn on archive mailboxes, users can access and store messages in their archive mailboxes by using Microsoft Outlook and Outlook Web App. Users can also move or copy messages between their primary mailbox and their archive mailbox. They can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="24bc4-p102">Office 365 提供与自动扩展存档功能的存档存储无限的量。时自动扩展存档处于打开状态，然后达到用户的存档邮箱中的初始存储配额，Office 365 会自动添加额外的存储空间。这意味着，用户不运行邮箱存储空间不足，并且您不必最初后管理任何启用存档邮箱，并打开自动扩展您的组织的存档。有关详细信息，请参阅[Overview of Office 365 中的无限制存档](unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p102">Office 365 provides an unlimited amount of archive storage with the auto-expanding archiving feature. When auto-expanding archiving is turned on, and then the initial storage quota in a user's archive mailbox is reached, Office 365 automatically adds additional storage space. This means that users won't run out of mailbox storage space and you won't have to manage anything after you initially enable the archive mailbox and turn on auto-expanding archiving for your organization. For more information, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="24bc4-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="24bc4-112">Before you begin</span></span>

<span data-ttu-id="24bc4-p103">您必须分配 Mail Recipients 角色在 Exchange Online 以启用或禁用存档邮箱。默认情况下，此角色分配给 Exchange 管理中心中的**权限**页上的收件人管理和组织管理角色组。如果您看不到安全中的**存档**页上&amp;合规性中心，请让管理员为您分配所需的权限。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p103">You have to be assigned the Mail Recipients role in Exchange Online to enable or disable archive mailboxes. By default, this role is assigned to the Recipient Management and Organization Management role groups on the **Permissions** page in the Exchange admin center. If you don't see the **Archive** page in the Security &amp; Compliance Center, ask your administrator to assign you the necessary permissions.</span></span> 
  
## <a name="enable-an-archive-mailbox"></a><span data-ttu-id="24bc4-116">启用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="24bc4-116">Enable an archive mailbox</span></span>
  
1. <span data-ttu-id="24bc4-117">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="24bc4-117">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="24bc4-118">登录到 Office 365 使用工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="24bc4-118">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="24bc4-119">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **存档**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-119">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="24bc4-p104">显示**存档**页。**存档邮箱**列指示是否启用或禁用每个用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p104">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="24bc4-122">在邮箱的列表中，选择要启用存档邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="24bc4-122">In the list of mailboxes, select the user that you want to enable the archive mailbox for.</span></span>
    
    ![在所选用户启用存档邮箱的详细信息窗格中单击启用](media/8b53cdec-d5c9-4c28-af11-611f95c37b34.png)
  
5. <span data-ttu-id="24bc4-124">在所选用户的详细信息窗格中，单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-124">In the details pane for the selected user, click **Enable**.</span></span> 
    
    <span data-ttu-id="24bc4-p105">显示一则警告说，是否您启用存档邮箱，超过分配给邮箱的存档策略的用户的邮箱内的项目将被移动到新的存档邮箱。默认存档策略分配给 Exchange Online 邮箱的保留策略的一部分将项目移动到存档邮箱项目已传递到邮箱或由用户创建的日期之后的两年。有关详细信息，请参阅本文中的**详细信息**一节。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p105">A warning is displayed saying that if you enable the archive mailbox, items in the user's mailbox that are older than the archiving policy assigned to the mailbox will be moved to the new archive mailbox. The default archive policy that is part of the retention policy assigned to Exchange Online mailboxes moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user. For more information, see the **More info** section in this article.</span></span> 
    
6. <span data-ttu-id="24bc4-128">单击**是**以启用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-128">Click **Yes** to enable the archive mailbox.</span></span> 
    
    <span data-ttu-id="24bc4-p106">可能需要一些时间来创建存档邮箱。当创建它时，**存档邮箱： 启用**所选用户的详细信息窗格中显示。您可能需要单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p106">It might take a few moments to create the archive mailbox. When it's created, **Archive mailbox: enabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="24bc4-p107">您可以还批量启用存档通过选择多个用户的邮箱禁用存档邮箱 （使用 Shift 或 Ctrl 键）。在选择多个邮箱后，单击详细信息窗格中的**启用**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p107">You can also bulk-enable archive mailboxes by selecting multiple users with disabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Enable** in the details pane.</span></span> 
  
## <a name="disable-an-archive-mailbox"></a><span data-ttu-id="24bc4-134">禁用存档邮箱</span><span class="sxs-lookup"><span data-stu-id="24bc4-134">Disable an archive mailbox</span></span>
  
<span data-ttu-id="24bc4-p108">您还可以在安全使用**存档**页上&amp;合规性中心以禁用用户的存档邮箱。禁用存档邮箱后，您可以将其重新连接到用户的主邮箱禁用它 30 天内。在这种情况下，还原存档邮箱的原始内容。30 天后，原始的存档邮箱的内容被永久删除，并且无法恢复。因此，如果您重新启用存档超过 30 天后禁用它，将创建新的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p108">You can also use the **Archive** page in the Security &amp; Compliance Center to disable a user's archive mailbox. After you disable an archive mailbox, you can reconnect it to the user's primary mailbox within 30 days of disabling it. In this case, the original contents of the archive mailbox are restored. After 30 days, the contents of the original archive mailbox are permanently deleted and can't be recovered. So if you re-enable the archive more than 30 days after disabling it, a new archive mailbox is created.</span></span> 
  
<span data-ttu-id="24bc4-p109">传递的默认存档策略分配到用户的邮箱移动到存档邮箱的项目两个年后项目的注释。如果您禁用用户的存档邮箱时，将邮箱项目上执行任何操作，并将保持在用户的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p109">Note that the default archive policy assigned to users' mailboxes moves items to the archive mailbox two years after the date the item is delivered. If you disable a user's archive mailbox, no action will be taken on mailbox items and they will remain in the user's primary mailbox.</span></span>
  
<span data-ttu-id="24bc4-142">若要禁用存档邮箱：</span><span class="sxs-lookup"><span data-stu-id="24bc4-142">To disable an archive mailbox:</span></span>
  
1. <span data-ttu-id="24bc4-143">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="24bc4-143">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="24bc4-144">登录到 Office 365 使用工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="24bc4-144">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="24bc4-145">在左侧窗格中的安全&amp;合规性中心，单击**数据调控** \> **存档**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-145">In the left pane of the Security &amp; Compliance Center, click **Data governance** \> **Archive**.</span></span>
    
    <span data-ttu-id="24bc4-p110">显示**存档**页。**存档邮箱**列指示是否启用或禁用每个用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p110">The **Archive** page is displayed. The **Archive mailbox** column indicates whether an archive mailbox is enabled or disabled for each user.</span></span> 
    
4. <span data-ttu-id="24bc4-148">在邮箱的列表中，选择要禁用存档邮箱的用户。</span><span class="sxs-lookup"><span data-stu-id="24bc4-148">In the list of mailboxes, select the user that you want to disable the archive mailbox for.</span></span>
    
5. <span data-ttu-id="24bc4-149">在详细信息窗格中，单击**禁用**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-149">In the details pane, click **Disable**.</span></span> 
    
    <span data-ttu-id="24bc4-150">将显示一条警告消息，告知您必须重新启用存档邮箱中，30 天内的 30 天后存档中的所有信息将被永久都删除。</span><span class="sxs-lookup"><span data-stu-id="24bc4-150">A warning message is displayed saying that you'll have 30 days to re-enable the archive mailbox, and that after 30 days, all information in the archive will be permanently deleted.</span></span> 
    
6. <span data-ttu-id="24bc4-151">单击**是**以禁用存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-151">Click **Yes** to disable the archive mailbox.</span></span> 
    
    <span data-ttu-id="24bc4-p111">可能需要一些时间来禁用存档邮箱。禁用它时，**存档邮箱： 禁用**所选用户的详细信息窗格中显示。您可能需要单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p111">It might take a few moments to disable the archive mailbox. When it's disabled, **Archive mailbox: disabled** is displayed in the details pane for the selected user. You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
> [!TIP]
> <span data-ttu-id="24bc4-p112">您可以也批量-禁用通过选择多个用户 （使用 Shift 或 Ctrl 键） 启用的存档邮箱与存档邮箱。在选择多个邮箱后，单击详细信息窗格中的**禁用**。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p112">You can also bulk-disable archive mailboxes by selecting multiple users with enabled archive mailboxes (use the Shift or Ctrl keys). After selecting multiple mailboxes, click **Disable** in the details pane.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="24bc4-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="24bc4-157">More information</span></span>
  
- <span data-ttu-id="24bc4-p113">存档邮箱帮助您和您的用户以满足组织的保留、 电子数据展示，并按住要求。例如，贵组织的 Exchange 保留策略可用于将邮箱内容移动到用户的存档邮箱。当您使用内容搜索工具中安全&amp;还将搜索合规性中心以搜索特定内容，用户的存档邮箱的用户的邮箱。和，当您放置诉讼保留或 Office 365 保留策略应用到用户的邮箱，也将保留存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p113">Archive mailboxes help you and your users to meet your organization's retention, eDiscovery, and hold requirements. For example, you can use your organization's Exchange retention policy to move mailbox content to users' archive mailbox. When you use the Content Search tool in the Security &amp; Compliance Center to search a user's mailbox for specific content, the user's archive mailbox will also be searched. And, when you place a Litigation Hold or apply an Office 365 retention policy to a user's mailbox, items in the archive mailbox are also retained.</span></span>
  
- <span data-ttu-id="24bc4-p114">启用存档邮箱后，用户可以在其存档邮箱中存储的邮件。用户可以访问其存档邮箱使用 Microsoft Outlook 和 Outlook Web 应用程序使用这些客户端应用程序之一，用户可以查看其存档邮箱中的邮件和移动或复制其主邮箱和其存档邮箱之间的消息。用户可以恢复已删除的项目从其存档邮箱中可恢复邮件文件夹使用恢复已删除邮件工具。</span><span class="sxs-lookup"><span data-stu-id="24bc4-p114">When an archive mailbox is enabled, users can store messages in their archive mailbox. Users can access their archive mailboxes by using Microsoft Outlook and Outlook Web App. Using either of these client applications, users can view messages in their archive mailbox and move or copy messages between their primary mailbox and their archive mailbox. Users can also recover deleted items from the Recoverable Items folder in their archive mailbox by using the Recover Deleted Items tool.</span></span> 
  
- <span data-ttu-id="24bc4-p115">启用邮箱的存档后, 您的组织可以充分利用的默认 Exchange 保留策略 （也称为邮件记录管理或 MRM 策略） 的自动分配给每个邮箱。启用存档邮箱后，将默认 Exchange 保留策略自动执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="24bc4-p115">After archive mailboxes are enabled, your organization can take advantage of the default Exchange retention policy (also called Messaging Records Management or MRM policy) that is automatically assigned to every mailbox. When an archive mailbox is enabled, the default Exchange retention policy automatically does the following:</span></span> 
  
    - <span data-ttu-id="24bc4-168">将两年或以上的邮件从用户主邮箱移动到存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="24bc4-168">Moves items that are two years or older from a user's primary mailbox to their archive mailbox.</span></span> 
    
    - <span data-ttu-id="24bc4-169">将 14 天或以上的邮件从用户主邮箱的"可恢复的项目"文件夹移动到存档邮箱中的"可恢复的项目"文件夹。</span><span class="sxs-lookup"><span data-stu-id="24bc4-169">Moves items that are 14 days or older from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in their archive mailbox.</span></span>
    
- <span data-ttu-id="24bc4-170">有关存档邮箱和 Exchange 保留策略的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="24bc4-170">For more information about archive mailboxes and Exchange retention policies, see:</span></span>
  
  - [<span data-ttu-id="24bc4-171">Exchange Online 中的存档邮箱</span><span class="sxs-lookup"><span data-stu-id="24bc4-171">Archive mailboxes in Exchange Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=404421)
    
  - [<span data-ttu-id="24bc4-172">保留标记和保留策略</span><span class="sxs-lookup"><span data-stu-id="24bc4-172">Retention tags and retention policies</span></span>](https://go.microsoft.com/fwlink/?LinkId=404424)
    
  - [<span data-ttu-id="24bc4-173">默认值保留策略在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24bc4-173">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/?linkid=839418)
    
  - [<span data-ttu-id="24bc4-174">设置 Office 365 组织中邮箱的存档和删除策略</span><span class="sxs-lookup"><span data-stu-id="24bc4-174">Set up an archive and deletion policy for mailboxes in your Office 365 organization</span></span>](set-up-an-archive-and-deletion-policy-for-mailboxes.md)
