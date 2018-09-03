---
title: Office 365 中的无限制存档的概述
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 了解自动扩展 Office 365 中的存档，从而提高了对不受限制的存档存储为 Exchange Online 邮箱。
ms.openlocfilehash: a762a0fb8295a645957404c1c88881f40329f7a1
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782119"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="30374-103">Office 365 中的无限制存档的概述</span><span class="sxs-lookup"><span data-stu-id="30374-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="30374-p101">Office 365 中的存档邮箱向用户提供其他邮箱存储空间。启用用户的存档邮箱后，最多 100 GB 的额外是存储的可用。当达到 100 GB 存储配额时，组织必须与 Microsoft 联系到存档邮箱的请求额外的存储空间。不再是这样。（称为*自动扩展存档*） 的 Office 365 中的新的无限制存档功能提供存档邮箱中存储无限的的量。现在，当达到存储配额的存档邮箱中时，Office 365 自动增加存档，这意味着用户不会运行邮箱存储空间不足，且管理员无法请求其他存储存档邮箱的大小.</span><span class="sxs-lookup"><span data-stu-id="30374-p101">In Office 365, archive mailboxes provide users with additional mailbox storage space. After a user's archive mailbox is enabled, up to 100 GB of additional storage is available. When the 100 GB storage quota is reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox. That's no longer the case. The new unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides an unlimited amount of storage in archive mailboxes. Now, when the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>
  
<span data-ttu-id="30374-110">有关分步说明开启自动扩展存档，请参阅[启用无限制存档的 Office 365](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="30374-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="30374-p102">自动扩展存档还支持共享的邮箱。若要共享邮箱的存档，请使用 Exchange Online Archiving 的许可证的 Exchange Online 计划 1 许可证或 Exchange Online 计划 2 许可证，则需要。</span><span class="sxs-lookup"><span data-stu-id="30374-p102">Auto-expanding archiving also supports shared mailboxes. To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span> 
  
## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="30374-113">如何自动扩展存档工作原理</span><span class="sxs-lookup"><span data-stu-id="30374-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="30374-p103">为前面所述、 其他邮箱启用用户的存档邮箱后创建的存储空间。当启用自动扩展存档时，Office 365 定期检查存档邮箱的大小。当存档邮箱获取接近其存储限制时，Office 365 自动创建额外的存储空间为存档。如果用户运行此额外的存储空间不足，Office 365 用户的存档添加更多存储空间。此过程会自动进行，这意味着管理员无需请求其他存档存储或管理自动扩展存档。</span><span class="sxs-lookup"><span data-stu-id="30374-p103">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled. When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox. When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive. If the user runs out of this additional storage space, Office 365 adds more storage space to the user's archive. This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span> 
  
<span data-ttu-id="30374-119">下面是过程的快速概述。</span><span class="sxs-lookup"><span data-stu-id="30374-119">Here's a quick overview of the process.</span></span>
  
![自动扩展存档过程概述](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. <span data-ttu-id="30374-p104">对用户邮箱或共享的邮箱启用存档。创建存档邮箱与 100 GB 的存储空间，并存档邮箱的警告配额设置为 90 GB。</span><span class="sxs-lookup"><span data-stu-id="30374-p104">Archiving is enabled for a user mailbox or a shared mailbox. An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>
    
2. <span data-ttu-id="30374-p105">管理员启用自动扩展存档邮箱。然后，当存档邮箱 （包括可恢复邮件文件夹） 到达 90 GB，它将转换为自动扩展存档和 Office 365 添加到存档存储空间。请注意，可能需要额外的存储空间设置为最多 30 天。</span><span class="sxs-lookup"><span data-stu-id="30374-p105">An administrator enables auto-expanding archiving for the mailbox. Then, when the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive. Note that it can take up to 30 days for the additional storage space to be provisioned.</span></span>
    
3. <span data-ttu-id="30374-126">Office 365 自动存档在必要时添加更多存储空间。</span><span class="sxs-lookup"><span data-stu-id="30374-126">Office 365 automatically adds more storage space to the archive when necessary.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="30374-p106">如果邮箱置于保持状态或者分配给 Office 365 保留策略，存档 maibox 的存储配额增加到 110 GB 启用自动扩展存档。同样，存档警告配额增加到 100 GB。</span><span class="sxs-lookup"><span data-stu-id="30374-p106">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive maibox is increased to 110 GB when auto-expanding archiving is enabled. Similarly, the archive warning quota is increased to 100 GB.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="30374-129">什么获取移动到其他存档存储空间？</span><span class="sxs-lookup"><span data-stu-id="30374-129">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="30374-p107">若要使高效地利用自动扩展存档存储，可能会获取移动文件夹。Office 365 确定哪些文件夹获取移动到存档中添加其他存储时。当移动文件夹时，会自动在 Outlook 中的文件夹列表的存档部分的原始文件夹下创建子文件夹。此新的子文件夹指向已移动的项。此文件夹命名为 Office 365 使用的命名约定为**\<文件夹名称\>_yyyy （上创建 mmm dd，yyyy h_mm）**，其中：</span><span class="sxs-lookup"><span data-stu-id="30374-p107">To make efficient use of auto-expanding archive storage, folders might get moved. Office 365 determines which folders get moved when additional storage is added to the archive. When a folder is moved, a subfolder is automatically created under the original folder in the archive portion of the folder list in Outlook. This new subfolder points to the items that were moved. The naming convention that Office 365 uses to name this folder is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span> 
  
- <span data-ttu-id="30374-135">**yyyy**是文件夹中的邮件已收到的年份。</span><span class="sxs-lookup"><span data-stu-id="30374-135">**yyyy** is the year the messages in the folder were received.</span></span> 
    
- <span data-ttu-id="30374-136">**mmm dd，yyyy h_m**是日期和时间的 UTC 格式，基于用户的时区和 Outlook 中的区域设置 Office 365 中，创建子文件夹。</span><span class="sxs-lookup"><span data-stu-id="30374-136">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span> 
    
<span data-ttu-id="30374-137">以下屏幕截图显示文件夹列表之前和之后邮件移自动扩展存档中。</span><span class="sxs-lookup"><span data-stu-id="30374-137">The following screen shots show a folder list before and after messages are moved in an auto-expanded archive.</span></span>
  
 <span data-ttu-id="30374-138">**之前添加额外的存储空间**</span><span class="sxs-lookup"><span data-stu-id="30374-138">**Before additional storage is added**</span></span>
  
![存档邮箱之前设置自动扩展存档文件夹列表](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 <span data-ttu-id="30374-140">**添加额外的存储空间后**</span><span class="sxs-lookup"><span data-stu-id="30374-140">**After additional storage is added**</span></span>
  
![文件夹列表中的存档邮箱后自动扩展存档设置](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="30374-142">用于访问自动扩展存档中的项目的 outlook 要求</span><span class="sxs-lookup"><span data-stu-id="30374-142">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="30374-143">若要访问存储在自动扩展存档的消息，用户必须使用以下 Outlook 客户端之一：</span><span class="sxs-lookup"><span data-stu-id="30374-143">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>
  
- <span data-ttu-id="30374-144">Outlook 2016 for Windows</span><span class="sxs-lookup"><span data-stu-id="30374-144">Outlook 2016 for Windows</span></span>
    
- <span data-ttu-id="30374-145">Web 上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="30374-145">Outlook on the web</span></span> 
    
- <span data-ttu-id="30374-146">Outlook 2016 for Mac</span><span class="sxs-lookup"><span data-stu-id="30374-146">Outlook 2016 for Mac</span></span> 
    
> [!NOTE]
> <span data-ttu-id="30374-p108">Outlook 2013 用户可以仅在最初存储其存档邮箱中的 access 项目。他们也不能以访问移动到其他存档存储的项目。</span><span class="sxs-lookup"><span data-stu-id="30374-p108">Outlook 2013 users can only access items that were originally stored in their archive mailbox. They won't be able to access items that are moved to additional archive storage.</span></span> 
  
<span data-ttu-id="30374-149">以下是使用 Outlook 或 Outlook web 访问邮件中自动扩展存档存储上的时要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="30374-149">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>
  
- <span data-ttu-id="30374-150">您可以访问存档邮箱，包括那些被移动到的自动扩展存储区中的任何文件夹。</span><span class="sxs-lookup"><span data-stu-id="30374-150">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>
    
- <span data-ttu-id="30374-p109">您可以搜索仅通过搜索文件夹本身，已将它们移动到其他存储区的项目。这意味着您必须在文件夹列表中选择的搜索范围作为**当前文件夹**选项中选择存档文件夹。同样，如果自动扩展存储区中的文件夹中包含子文件夹，您需要单独搜索每个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="30374-p109">You can search for items that were moved to an additional storage area only by searching the folder itself. This means you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope. Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span> 
    
- <span data-ttu-id="30374-154">在 Outlook 中的项计数和自动扩展存档中 （在 Outlook 和 Outlook web 上的） 的读取/未读取计数可能不准确。</span><span class="sxs-lookup"><span data-stu-id="30374-154">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web ) in an auto-expanded archive might not be accurate.</span></span>
    
- <span data-ttu-id="30374-155">您可以删除自动扩展存储区域中，指向子文件夹中的项目，但不能删除该文件夹本身。</span><span class="sxs-lookup"><span data-stu-id="30374-155">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>
    
- <span data-ttu-id="30374-156">恢复已删除邮件功能不能用于恢复已删除自动扩展存储区域中的项。</span><span class="sxs-lookup"><span data-stu-id="30374-156">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="30374-157">自动扩展存档和其他 Office 365 合规性功能</span><span class="sxs-lookup"><span data-stu-id="30374-157">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="30374-158">本节介绍之间自动扩展存档其他 Office 365 合规性和数据管理功能的功能。</span><span class="sxs-lookup"><span data-stu-id="30374-158">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>
  
- <span data-ttu-id="30374-159">**电子数据展示**-当您使用 Office 365 电子数据展示工具，如内容搜索或就地电子数据展示，自动扩展存档中的其他存储区域还搜索。</span><span class="sxs-lookup"><span data-stu-id="30374-159">**eDiscovery** - When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>
    
- <span data-ttu-id="30374-160">**保留**-当您在 Exchange Online 中使用工具，例如诉讼保留将邮箱置于保持状态或电子数据展示事例包含和 Office 365 安全性的保留策略&amp;合规性中心位于自动扩展存档的内容还是置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="30374-160">**Retention** - When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the Office 365 Security &amp; Compliance Center, content located in an auto-expanded archive is also placed on hold.</span></span>
    
- <span data-ttu-id="30374-161">也会删除**消息记录管理 (MRM)** -如果在 Exchange Online 中使用 MRM 删除策略永久删除过期的邮箱项目，位于自动扩展存档的过期项目。</span><span class="sxs-lookup"><span data-stu-id="30374-161">**Messaging records management (MRM)** - If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>
    
- <span data-ttu-id="30374-p110">**导入服务**-您可以使用导入 Office 365 服务 PST 文件导入用户的自动扩展存档。您可以从导入数据的最多 100 GB PST 文件到用户的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="30374-p110">**Import service** - You can use the Office 365 Import service to import PST files to a user's auto-expanded archive. You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span> 

## <a name="more-information"></a><span data-ttu-id="30374-164">详细信息</span><span class="sxs-lookup"><span data-stu-id="30374-164">More information</span></span>

<span data-ttu-id="30374-165">有关更多技术详细信息自动扩展存档，请参阅[Office 365： 自动扩展存档常见问题](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="30374-165">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>