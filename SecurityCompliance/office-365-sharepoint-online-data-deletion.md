---
title: Office 365 SharePoint Online 数据删除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online 中的数据删除的说明。
ms.openlocfilehash: 8a84859ce170a4c3ca713c751aef2b6d5b911c55
ms.sourcegitcommit: 29ba4c36af8e90ddc8d885863ef25bac2cffbe94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2018
ms.locfileid: "27411158"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="a444b-103">Office 365 中的 SharePoint Online 数据删除</span><span class="sxs-lookup"><span data-stu-id="a444b-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="a444b-p101">SharePoint Online 作为抽象代码中应用程序数据库存储对象。如果用户将文件上载到 SharePoint Online，该文件为分解和翻译应用程序代码，并跨多个数据库存储在多个表中。在 SharePoint Online 中，客户上载的所有内容分成块的大小，（可能使用多个 AES 256 位键中） 加密和分布在数据中心。有关分块和加密过程的详细信息，请参阅[Microsoft 云中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a444b-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span> 

<span data-ttu-id="a444b-p102">SharePoint Online 中的项目的保留从其原始位置从删除时间 93 天。他们随时了解最新网站回收站的整个时间，除非某人从中删除这些或清空的回收站。在这种情况下，项目转到网站集回收站中，其中他们保持 93 天的其余部分。有关还原已删除的项目的信息，请参阅[还原 SharePoint 网站的回收站中的项目](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
)，并[恢复已删除网站集回收站中的项](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。回收站保留时间不是 SharePoint Online 中配置的。</span><span class="sxs-lookup"><span data-stu-id="a444b-p102">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location. They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin. In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days. For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/en-us/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="a444b-113">删除网站集时，还正在删除网站集和其中的所有内容中的层次结构：</span><span class="sxs-lookup"><span data-stu-id="a444b-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>
- <span data-ttu-id="a444b-114">文档和文档库</span><span class="sxs-lookup"><span data-stu-id="a444b-114">Documents and document libraries</span></span>
- <span data-ttu-id="a444b-115">列表和列表数据</span><span class="sxs-lookup"><span data-stu-id="a444b-115">Lists and list data</span></span>
- <span data-ttu-id="a444b-116">网站配置设置</span><span class="sxs-lookup"><span data-stu-id="a444b-116">Site configuration settings</span></span>
- <span data-ttu-id="a444b-117">与网站或子网站相关的角色和安全信息</span><span class="sxs-lookup"><span data-stu-id="a444b-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="a444b-118">子网站的顶级网站、 其内容和用户信息</span><span class="sxs-lookup"><span data-stu-id="a444b-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="a444b-119">如果您意外删除网站集，它可以还原的全局或 SharePoint 管理员使用 SharePoint 管理中心。</span><span class="sxs-lookup"><span data-stu-id="a444b-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span> 

<span data-ttu-id="a444b-p103">当用户从网站集回收站中，清除已删除的邮件保留期和备份期到期时, 或管理员永久删除网站集使用[Remove-spodeletedsite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)时，将发生硬删除。当用户硬删除 （永久删除，或清除） 从 SharePoint Online 内容，所有的已删除的块的加密密钥也将被删除。以前存储已删除的块的磁盘上的块被标记为未使用并且可供重复使用。</span><span class="sxs-lookup"><span data-stu-id="a444b-p103">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
