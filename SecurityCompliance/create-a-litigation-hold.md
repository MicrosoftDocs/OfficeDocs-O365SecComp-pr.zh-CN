---
title: 在 Office 365 中创建诉讼保留
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
ms.openlocfilehash: f2d3793eac84e8f80158842c833c30986b0549c5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218652"
---
# <a name="create-a-litigation-hold-in-office-365"></a><span data-ttu-id="6105c-102">在 Office 365 中创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="6105c-102">Create a Litigation Hold in Office 365</span></span>

<span data-ttu-id="6105c-p101">您可以将邮箱置于诉讼保留状态, 以保留所有邮箱内容, 包括已删除项目和已修改项目的原始版本。将用户邮箱置于诉讼保留状态时, 用户的存档邮箱 (如果已启用) 中的内容也会保留。创建保留时, 可以指定保留持续时间 (也称为*基于时间的保留*), 以便在指定时间段内保留已删除和已修改的项目, 然后从邮箱中永久删除。或者, 也可以无限期保留内容 (称为*无限保留*), 或者直到删除诉讼保留。如果您指定保留持续时间段, 则它将根据接收邮件的日期或创建邮箱项目计算得出。</span><span class="sxs-lookup"><span data-stu-id="6105c-p101">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items. When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained. When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox. Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed. If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="6105c-108">以下是创建诉讼保留时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="6105c-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="6105c-109">被用户永久删除的项目将保留在用户邮箱中的 "可恢复的项目" 文件夹中的保留期。</span><span class="sxs-lookup"><span data-stu-id="6105c-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="6105c-110">用户在 "可恢复的项目" 文件夹中清除的项目将在保留期间保留。</span><span class="sxs-lookup"><span data-stu-id="6105c-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="6105c-111">"可恢复的项目" 文件夹的存储配额从 30 gb 增加到 110 gb。</span><span class="sxs-lookup"><span data-stu-id="6105c-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="6105c-112">用户主和存档邮箱中的项目将保留</span><span class="sxs-lookup"><span data-stu-id="6105c-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="6105c-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="6105c-113">Before you begin</span></span>

- <span data-ttu-id="6105c-p102">若要在诉讼保留中放置 Exchange online 邮箱, 必须为其分配 exchange online 计划2许可证。如果向某个邮箱分配了 Exchange Online 计划1许可证, 则必须为其分配一个单独的 Exchange online 存档许可证以将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="6105c-p102">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license. If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold-in-the-office-365-admin-center"></a><span data-ttu-id="6105c-116">在 Office 365 管理中心中将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="6105c-116">Place a mailbox on Litigation Hold in the Office 365 admin center</span></span>

<span data-ttu-id="6105c-117">以下是使用 Office 365 管理中心将 maibox 置于诉讼保留状态的步骤。</span><span class="sxs-lookup"><span data-stu-id="6105c-117">Here are the steps to place a maibox on Litigation Hold using the Office 365 admin center.</span></span>

1. <span data-ttu-id="6105c-118">转到https://portal.office.com/adminportal/home并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="6105c-118">Go to https://portal.office.com/adminportal/home and sign in using your global administrator account.</span></span>
2. <span data-ttu-id="6105c-119">单击左侧导航窗格中的 "**用户** > **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="6105c-119">Click **Users** > **Active users** in the left navigation pane.</span></span>
3. <span data-ttu-id="6105c-120">选择要将其邮箱置于诉讼保留状态的用户。</span><span class="sxs-lookup"><span data-stu-id="6105c-120">Select the user whose mailbox you want to place on Litigation Hold.</span></span>
4. <span data-ttu-id="6105c-121">在 "飞出" 页面上, 单击 "**邮件设置**", 然后单击 "**诉讼保留**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="6105c-121">On the fly-out page, click **Mail settings**, and then click **Edit** next to **Litigation hold**.</span></span>
5. <span data-ttu-id="6105c-122">在 "**诉讼保留**" 页上, 单击 "切换" 以启用诉讼保留并完成显示的以下可选设置:</span><span class="sxs-lookup"><span data-stu-id="6105c-122">On the **Litigation hold** page, click the toggle to turn on Litigation Hold and complete the following optional settings that are displayed:</span></span>
 
    ![O365_LitigationHold1](media/O365-LitigationHold1.png)

    <span data-ttu-id="6105c-p103">一.**保留持续时间 (天)** -使用此框可以创建基于时间的保留, 并指定在将邮箱置于诉讼保留状态时邮箱项目的保留时间。持续时间从接收或创建邮箱项目的日期开始计算。如果将此框保留为空, 则项目将无限期保留或在删除保留之前进行。使用 "天" 指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="6105c-p103">a. **Hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold. The duration is calculated from the date a mailbox item is received or created. If you leave this box blank, items are held indefinitely or until the hold is removed. Use days to specify the duration.</span></span>
    
    <span data-ttu-id="6105c-p104">b.**注意**-使用此框通知用户其邮箱处于诉讼保留状态。如果用户使用的是 Outlook 2010 或更高版本, 注释将显示在用户邮箱中的 "帐户信息" 页面上。若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="6105c-p104">b. **Note** - Use this box to inform the user their mailbox is on Litigation Hold. The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
     
    <span data-ttu-id="6105c-p105">c. 网页\*\*\*\* -使用此框将用户定向到网站, 以获取有关诉讼保留的详细信息。如果用户使用的是 Outlook 2010 或更高版本, 则此 URL 将显示在用户邮箱中的 "帐户信息" 页面上。若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="6105c-p105">c. **Web page** - Use this box to direct the user to a website for more information about Litigation Hold. This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later. To access this page, users can click **File** in Outlook.</span></span>
 
6. <span data-ttu-id="6105c-137">单击 "**保存**" 以创建诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="6105c-137">Click **Save** to create the Litigation Hold.</span></span>

<span data-ttu-id="6105c-138">创建保留后, 飞出页面上的邮件设置将显示所选用户的诉讼保留处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="6105c-138">After you create the hold, the mail settings on the fly-out page shows that Litigation Hold is turned on for the selected user.</span></span>

![O365_LitigationHold2](media/O365-LitigationHold2.png)

<span data-ttu-id="6105c-140">有关创建和管理诉讼保留和使用 Exchange Online PowerShell 批量创建诉讼保留的详细信息, 请参阅[将邮箱置于诉讼保留状态](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold)。</span><span class="sxs-lookup"><span data-stu-id="6105c-140">For more information about creating and managing Litigation Holds and using Exchange Online PowerShell to bulk-create Litigation Holds, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/office365/SecurityCompliance/place-a-mailbox-on-litigation-hold).</span></span>
