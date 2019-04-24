---
title: 创建诉讼保留
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
ms.openlocfilehash: e4cb614167f89cb6e99d96aa94027ba90d86543e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258362"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="3bc96-102">创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="3bc96-102">Create a Litigation Hold</span></span>

<span data-ttu-id="3bc96-103">您可以将邮箱置于诉讼保留状态, 以保留所有邮箱内容, 包括已删除项目和已修改项目的原始版本。</span><span class="sxs-lookup"><span data-stu-id="3bc96-103">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="3bc96-104">将用户邮箱置于诉讼保留状态时, 用户的存档邮箱 (如果已启用) 中的内容也会保留。</span><span class="sxs-lookup"><span data-stu-id="3bc96-104">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="3bc96-105">创建保留时, 可以指定保留持续时间 (也称为*基于时间的保留*), 以便在指定时间段内保留已删除和已修改的项目, 然后从邮箱中永久删除。</span><span class="sxs-lookup"><span data-stu-id="3bc96-105">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="3bc96-106">或者, 也可以无限期保留内容 (称为*无限保留*), 或者直到删除诉讼保留。</span><span class="sxs-lookup"><span data-stu-id="3bc96-106">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="3bc96-107">如果您指定保留持续时间段, 则它将根据接收邮件的日期或创建邮箱项目计算得出。</span><span class="sxs-lookup"><span data-stu-id="3bc96-107">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="3bc96-108">以下是创建诉讼保留时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="3bc96-108">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="3bc96-109">被用户永久删除的项目将保留在用户邮箱中的 "可恢复的项目" 文件夹中的保留期。</span><span class="sxs-lookup"><span data-stu-id="3bc96-109">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="3bc96-110">用户在 "可恢复的项目" 文件夹中清除的项目将在保留期间保留。</span><span class="sxs-lookup"><span data-stu-id="3bc96-110">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="3bc96-111">"可恢复的项目" 文件夹的存储配额从 30 gb 增加到 110 gb。</span><span class="sxs-lookup"><span data-stu-id="3bc96-111">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="3bc96-112">用户主和存档邮箱中的项目将保留</span><span class="sxs-lookup"><span data-stu-id="3bc96-112">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="3bc96-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="3bc96-113">Before you begin</span></span>

- <span data-ttu-id="3bc96-114">若要在诉讼保留中放置 Exchange online 邮箱, 必须为其分配 exchange online 计划2许可证。</span><span class="sxs-lookup"><span data-stu-id="3bc96-114">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="3bc96-115">如果向某个邮箱分配了 Exchange Online 计划1许可证, 则必须为其分配一个单独的 Exchange online 存档许可证以将其置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="3bc96-115">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="3bc96-116">将邮箱置于诉讼保留</span><span class="sxs-lookup"><span data-stu-id="3bc96-116">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="3bc96-117">以下是使用 Exchange 管理中心将邮箱置于诉讼保留状态的步骤。</span><span class="sxs-lookup"><span data-stu-id="3bc96-117">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="3bc96-118">转到[https://outlook.office.com/ecp](https://outlook.office.com/ecp)并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3bc96-118">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="3bc96-119">单击左侧导航窗格中的 "**收件人 > 邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-119">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="3bc96-120">选择要置于诉讼保留状态的邮箱, 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-120">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="3bc96-121">在邮箱属性页上, 单击 "**邮箱功能**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-121">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="3bc96-122">在 "**诉讼保留: 已禁用**" 下, 单击 "**启用**" 以将邮箱置于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="3bc96-122">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="3bc96-123">在 "**诉讼保留**" 页上, 输入以下可选信息:</span><span class="sxs-lookup"><span data-stu-id="3bc96-123">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="3bc96-124">**诉讼保留持续时间 (天)** -使用此框可以创建基于时间的保留, 并指定在将邮箱置于诉讼保留状态时邮箱项目的保留时间。</span><span class="sxs-lookup"><span data-stu-id="3bc96-124">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="3bc96-125">持续时间从接收或创建邮箱项目的日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="3bc96-125">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="3bc96-126">当特定项目的保留持续时间过期时, 将不再保留该项目。</span><span class="sxs-lookup"><span data-stu-id="3bc96-126">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="3bc96-127">如果将此框保留为空, 则会无限期保留项目或删除保留。</span><span class="sxs-lookup"><span data-stu-id="3bc96-127">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="3bc96-128">使用天指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="3bc96-128">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="3bc96-129">**注意**-使用此框可通知用户其邮箱处于诉讼保留状态。</span><span class="sxs-lookup"><span data-stu-id="3bc96-129">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="3bc96-130">如果用户使用的是 Outlook 2010 或更高版本, 注释将显示在用户邮箱中的 "帐户信息" 页面上。</span><span class="sxs-lookup"><span data-stu-id="3bc96-130">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="3bc96-131">若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-131">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="3bc96-132">**URL** -使用此框可将用户定向到网站, 以获取有关诉讼保留的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3bc96-132">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="3bc96-133">如果用户使用的是 Outlook 2010 或更高版本, 则此 URL 将显示在用户邮箱中的 "帐户信息" 页面上。</span><span class="sxs-lookup"><span data-stu-id="3bc96-133">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="3bc96-134">若要访问此页面, 用户可以在 Outlook 中单击 "**文件**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-134">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="3bc96-135">单击 "**诉讼保留**" 页上的 "**保存**", 然后单击 "邮箱属性" 页上的 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="3bc96-135">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="3bc96-136">使用 PowerShell 创建诉讼保留</span><span class="sxs-lookup"><span data-stu-id="3bc96-136">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="3bc96-137">您还可以通过在[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中运行以下命令来创建诉讼保留:</span><span class="sxs-lookup"><span data-stu-id="3bc96-137">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="3bc96-138">由于未指定保留持续时间, 上一个命令将无限期保留项目。</span><span class="sxs-lookup"><span data-stu-id="3bc96-138">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="3bc96-139">若要创建基于时间的保留, 请使用以下命令:</span><span class="sxs-lookup"><span data-stu-id="3bc96-139">To created a time-based hold, using the following command:</span></span>

```
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="3bc96-140">有关详细信息, 请参阅[设置邮箱](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="3bc96-140">For more information, see [Set-Mailbox](https://docs.microsoft.com/en-us/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="3bc96-141">诉讼保留的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="3bc96-141">How does Litigation Hold work?</span></span>

<span data-ttu-id="3bc96-142">在正常的已删除邮件工作流中，当用户永久删除 (Shift + Delete) 或从已删除邮件文件夹中删除某个邮箱项目时，会将该项目移动到"可恢复的项目"文件夹中的"删除"子文件夹。</span><span class="sxs-lookup"><span data-stu-id="3bc96-142">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="3bc96-143">当保留期到期时，删除策略（这是使用删除保留操作配置的保留标记）也将项目移动到"删除"子文件夹。</span><span class="sxs-lookup"><span data-stu-id="3bc96-143">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="3bc96-144">当用户清除"可恢复的项目"文件夹中的某个项目时或者当某个项目的已删除邮件保留期到期时，该项目将被移动到"可恢复的项目"文件夹中的"清除"子文件夹并标记为永久删除。</span><span class="sxs-lookup"><span data-stu-id="3bc96-144">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="3bc96-145">下一次通过托管文件夹助理 (MFA) 处理邮箱时，将从 Exchange 中清除该邮箱。</span><span class="sxs-lookup"><span data-stu-id="3bc96-145">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="3bc96-p108">如果邮箱置于诉讼保留状态，在由诉讼保留指定的保留期限内会保留"清除"子文件中的项目。保留期限自接收或创建项目的原始日期算起，并且定义了保留"清除"子文件中的项目的时长。"清除"子文件中的某个项目的保留期限到期时，将该项目标记为永久删除，并且下一次通过 MFA 处理邮箱时该项目将从 Exchange 中清除。如果邮箱中设置了无限期保留，则永远不会将项目从"清除"子文件中清除。</span><span class="sxs-lookup"><span data-stu-id="3bc96-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="3bc96-150">下图显示了"可恢复的项目"文件夹中的子文件夹和保留工作流程。</span><span class="sxs-lookup"><span data-stu-id="3bc96-150">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![诉讼保留生命周期](media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="3bc96-152">如果将与电子数据展示事例关联的保留放在邮箱中, 清除的项目将从 "删除" 子文件夹移动到 "DiscoveryHolds" 子文件夹, 并在邮箱从电子数据展示保留中释放之前保留。</span><span class="sxs-lookup"><span data-stu-id="3bc96-152">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
  