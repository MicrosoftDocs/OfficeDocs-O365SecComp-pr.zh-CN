---
title: Office 365 中的无限制存档概述
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解 Office 365 中的自动扩展存档, 该存档为 Exchange Online 邮箱提供无限制的存档存储。
ms.openlocfilehash: 21489683bbb9f3e2addb5e95a38d8f8a418639de
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36231076"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="ebd00-103">Office 365 中的无限制存档概述</span><span class="sxs-lookup"><span data-stu-id="ebd00-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="ebd00-104">在 Office 365 中, 存档邮箱为用户提供额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="ebd00-105">启用用户的存档邮箱后, 最多可有 100 GB 的附加存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="ebd00-106">过去, 当达到 100 GB 的存储配额时, 组织必须与 Microsoft 联系以请求存档邮箱的额外存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-106">In the past, when the 100 GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="ebd00-107">这就不再是这样。</span><span class="sxs-lookup"><span data-stu-id="ebd00-107">That's no longer the case.</span></span>

<span data-ttu-id="ebd00-108">Office 365 中的无限制存档功能 (称为*自动扩展存档*) 在存档邮箱中提供了不受限制的存储量。</span><span class="sxs-lookup"><span data-stu-id="ebd00-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes.</span></span> <span data-ttu-id="ebd00-109">现在, 当达到存档邮箱中的存储配额时, Office 365 会自动增加存档大小, 这意味着用户将不会用尽邮箱存储空间, 并且管理员无需为存档邮箱请求额外的存储空间.</span><span class="sxs-lookup"><span data-stu-id="ebd00-109">Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="ebd00-110">有关启用自动扩展存档的分步说明, 请参阅[在 Office 365 中启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="ebd00-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ebd00-111">自动扩展存档还支持共享邮箱。</span><span class="sxs-lookup"><span data-stu-id="ebd00-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="ebd00-112">若要为共享邮箱启用存档, 需要具有 Exchange Online 存档许可证的 Exchange Online 计划2许可证或 Exchange Online 计划1许可证。</span><span class="sxs-lookup"><span data-stu-id="ebd00-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="ebd00-113">自动扩展存档的工作方式</span><span class="sxs-lookup"><span data-stu-id="ebd00-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="ebd00-114">如前所述, 在启用用户的存档邮箱时, 会创建额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="ebd00-115">启用自动扩展存档后, Office 365 将定期检查存档邮箱的大小。</span><span class="sxs-lookup"><span data-stu-id="ebd00-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="ebd00-116">当存档邮箱接近其存储限制时, Office 365 会自动为存档创建额外的存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="ebd00-117">如果用户在此额外的存储空间中耗尽, Office 365 将为用户的存档增加更多的存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-117">If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="ebd00-118">此过程会自动发生, 这意味着管理员无需请求额外存档存储或管理自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="ebd00-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="ebd00-119">以下是此过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="ebd00-119">Here's a quick overview of the process.</span></span>
  
![自动扩展存档过程概述](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="ebd00-121">对用户邮箱或共享邮箱启用存档。</span><span class="sxs-lookup"><span data-stu-id="ebd00-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="ebd00-122">将创建一个具有 100 GB 存储空间的存档邮箱, 并将存档邮箱的警告配额设置为 90 GB。</span><span class="sxs-lookup"><span data-stu-id="ebd00-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="ebd00-123">管理员可自动展开邮箱的存档。</span><span class="sxs-lookup"><span data-stu-id="ebd00-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="ebd00-124">然后, 当存档邮箱 (包括 "可恢复的项目" 文件夹) 达到 90 GB 时, 它将转换为自动扩展存档, 而 Office 365 会将存储空间添加到存档中。</span><span class="sxs-lookup"><span data-stu-id="ebd00-124">Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="ebd00-125">请注意, 要设置额外的存储空间, 可能需要长达30天的时间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-125">Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="ebd00-126">必要时, Office 365 会自动向存档中添加更多的存储空间。</span><span class="sxs-lookup"><span data-stu-id="ebd00-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebd00-127">如果将邮箱置于保留状态或分配到 Office 365 保留策略, 则在启用自动扩展存档时, 存档 maibox 的存储配额将增加到 110 GB。</span><span class="sxs-lookup"><span data-stu-id="ebd00-127">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="ebd00-128">同样, 存档警告配额增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="ebd00-128">Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="ebd00-129">移动到其他存档存储空间的内容是什么？</span><span class="sxs-lookup"><span data-stu-id="ebd00-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="ebd00-130">为了高效地使用自动扩展存档存储, 文件夹可能会移动。</span><span class="sxs-lookup"><span data-stu-id="ebd00-130">To make efficient use of auto-expanding archive storage, folders might get moved.</span></span> <span data-ttu-id="ebd00-131">Office 365 确定在将其他存储添加到存档中时哪些文件夹发生移动。</span><span class="sxs-lookup"><span data-stu-id="ebd00-131">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="ebd00-132">移动文件夹时, 将自动在 Outlook 的文件夹列表的存档部分中的原始文件夹下创建子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ebd00-132">When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook.</span></span> <span data-ttu-id="ebd00-133">这个新的子文件夹指向已移动的项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-133">This new subfolder points to the items that were moved.</span></span> <span data-ttu-id="ebd00-134">Office 365 用来为此文件夹命名的命名约定是\*\* \<文件夹名称\>_yyyy (在 mmm dd, yyyy h_mm 创建)\*\*, 其中:</span><span class="sxs-lookup"><span data-stu-id="ebd00-134">The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="ebd00-135">**yyyy**是接收文件夹中邮件的年份。</span><span class="sxs-lookup"><span data-stu-id="ebd00-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="ebd00-136">**mmm dd, yyyy h_m**是 Office 365 创建子文件夹的日期和时间, 以 UTC 格式表示, 基于用户的时区和 Outlook 中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="ebd00-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="ebd00-137">下面的屏幕截图显示在自动展开的存档中移动邮件前后的文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="ebd00-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="ebd00-138">**添加额外的存储之前**</span><span class="sxs-lookup"><span data-stu-id="ebd00-138">**Before additional storage is added**</span></span>
  
![预配自动扩展存档之前的存档邮箱的文件夹列表](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="ebd00-140">**添加额外的存储后**</span><span class="sxs-lookup"><span data-stu-id="ebd00-140">**After additional storage is added**</span></span>
  
![预配自动扩展存档后存档邮箱的文件夹列表](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="ebd00-142">用于访问自动扩展存档中的项目的 Outlook 要求</span><span class="sxs-lookup"><span data-stu-id="ebd00-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="ebd00-143">若要访问存储在自动扩展的存档中的邮件, 用户必须使用以下 Outlook 客户端之一:</span><span class="sxs-lookup"><span data-stu-id="ebd00-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="ebd00-144">Outlook 2016 或 Outlook 2019 for Windows</span><span class="sxs-lookup"><span data-stu-id="ebd00-144">Outlook 2016 or Outlook 2019 for Windows</span></span>
    
- <span data-ttu-id="ebd00-145">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="ebd00-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="ebd00-146">Outlook 2016 或 Outlook 2019 for Mac</span><span class="sxs-lookup"><span data-stu-id="ebd00-146">Outlook 2016 or Outlook 2019 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="ebd00-147">Outlook 2013 用户只能访问最初存储在其存档邮箱中的项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-147">Outlook 2013 users can only access items that were originally stored in their archive mailbox.</span></span> <span data-ttu-id="ebd00-148">他们将无法访问移动到其他存档存储的项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-148">They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="ebd00-149">以下是在使用 Outlook 或 web 上的 Outlook 访问存储在自动扩展的存档中的邮件时需要考虑的一些事项。</span><span class="sxs-lookup"><span data-stu-id="ebd00-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="ebd00-150">您可以访问存档邮箱中的任何文件夹, 包括已移动到自动扩展存储区域的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ebd00-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="ebd00-151">您可以仅通过搜索文件夹本身来搜索已移动到其他存储区域的项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-151">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="ebd00-152">这意味着您必须在文件夹列表中选择 "存档" 文件夹, 以选择**当前文件夹**选项作为搜索范围。</span><span class="sxs-lookup"><span data-stu-id="ebd00-152">This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="ebd00-153">同样, 如果自动扩展存储区域中的文件夹包含子文件夹, 则必须单独搜索每个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="ebd00-153">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="ebd00-154">Outlook 中的项目计数和可读/未读的计数 (在 Outlook 和 web 上的 outlook 中) 在自动展开的存档中可能不准确。</span><span class="sxs-lookup"><span data-stu-id="ebd00-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="ebd00-155">您可以删除子文件夹中指向自动扩展存储区域的项目, 但不能删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="ebd00-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="ebd00-156">无法使用 "恢复已删除邮件" 功能恢复从自动扩展的存储区域中删除的项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="ebd00-157">自动扩展存档和其他 Office 365 合规性功能</span><span class="sxs-lookup"><span data-stu-id="ebd00-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="ebd00-158">本部分介绍自动扩展存档和其他 Office 365 合规性和数据管理功能之间的功能。</span><span class="sxs-lookup"><span data-stu-id="ebd00-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="ebd00-159">**电子数据展示**-当您使用 Office 365 电子数据展示工具 (如内容搜索或就地电子数据展示) 时, 还会搜索自动扩展存档中的其他存储区域。</span><span class="sxs-lookup"><span data-stu-id="ebd00-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="ebd00-160">**保留**-通过在 Exchange Online 或电子数据展示事例保留和合规性中心中使用诉讼保留等工具将邮箱置于保留状态时, 位于自动扩展存档中的内容也会置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="ebd00-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="ebd00-161">**邮件记录管理 (MRM)** -如果您使用 Exchange Online 中的 MRM 删除策略以永久删除过期的邮箱项目, 则也会删除位于自动展开的存档中的已过期项目。</span><span class="sxs-lookup"><span data-stu-id="ebd00-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="ebd00-162">**导入服务**-您可以使用 Office 365 导入服务将 PST 文件导入到用户的自动扩展存档中。</span><span class="sxs-lookup"><span data-stu-id="ebd00-162">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="ebd00-163">你可以将 PST 文件中的最大为 100 GB 的数据导入用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="ebd00-163">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="ebd00-164">更多信息</span><span class="sxs-lookup"><span data-stu-id="ebd00-164">More information</span></span>

<span data-ttu-id="ebd00-165">有关自动扩展存档的更多技术详细信息, 请参阅[Office 365: 自动扩展存档常见问题解答](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="ebd00-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>