---
title: Office 365 SharePoint Online 数据删除
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: SharePoint Online 中的数据删除的说明。
ms.openlocfilehash: 97f3eaea471c08ba61c0fc749b806c1960c0182f
ms.sourcegitcommit: ee1d7037d9ad14d7f0dbc53114177a3d04614d6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25402036"
---
# <a name="sharepoint-online-data-deletion-in-office-365"></a><span data-ttu-id="21c8a-103">Office 365 中的 SharePoint Online 数据删除</span><span class="sxs-lookup"><span data-stu-id="21c8a-103">SharePoint Online Data Deletion in Office 365</span></span>

<span data-ttu-id="21c8a-p101">SharePoint Online 作为抽象代码中应用程序数据库存储对象。如果用户将文件上载到 SharePoint Online，该文件为分解和翻译应用程序代码，并跨多个数据库存储在多个表中。在 SharePoint Online 中，客户上载的所有内容分成块的大小，（可能使用多个 AES 256 位键中） 加密和分布在数据中心。有关分块和加密过程的详细信息，请参阅[Microsoft 云中的加密](office-365-encryption-in-the-microsoft-cloud-overview.md)。提供数据保护服务以防止的 SharePoint Online 数据丢失。具体而言，备份的执行每 12 个小时，并且保留 14 天。</span><span class="sxs-lookup"><span data-stu-id="21c8a-p101">SharePoint Online stores objects as abstracted code within application databases. When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases. In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter. For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](office-365-encryption-in-the-microsoft-cloud-overview.md). Data protection services are provided to prevent the loss of SharePoint Online data. Specifically, backups are performed every 12 hours and retained for 14 days.</span></span>

<span data-ttu-id="21c8a-p102">从 SharePoint Online 网站中删除内容时，它不会立即删除。如果需要它是发送到网站回收站，其中可以还原它。（请参阅[还原已删除网站集回收站项目](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b)还原步骤。）默认网站回收站保留时间为大约 90 天。如果从网站回收站中删除内容，它是发送到网站集回收站，上面有 93 天的保留时间。可以配置保留在回收站中的操作的时间长度由管理员，但不存在的默认保留期大约 90 天。网站 recycle bin 存储计算针对网站集存储配额和[列表视图阈值](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59)。</span><span class="sxs-lookup"><span data-stu-id="21c8a-p102">When you delete content from a SharePoint Online site, it's not deleted immediately. It's sent to a Site Recycle Bin, where it can be restored, if needed. (See [Restore deleted items from the site collection recycle bin](https://support.office.com/article/Restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b) for restore steps.) The default Site Recycle Bin retention time is about 90 days. If you delete content from a Site Recycle Bin, it's sent to the Site Collection Recycle Bin, which has a retention time of 93 days. The length of time to keep things in the recycle bin can be configured by an administrator, but in the absence of that, the default retention period is about 90 days. The site recycle bin storage counts against site collection storage quota and the [List View Threshold](https://support.office.com/article/List-View-Threshold-b8588dae-9387-48c2-9248-c24122f07c59).</span></span>

<span data-ttu-id="21c8a-116">删除网站集时，您还正在删除在集合中，包括所有内容和用户信息的网站的层次结构：</span><span class="sxs-lookup"><span data-stu-id="21c8a-116">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, including all content and user information:</span></span>
- <span data-ttu-id="21c8a-117">文档和文档库</span><span class="sxs-lookup"><span data-stu-id="21c8a-117">Documents and document libraries</span></span>
- <span data-ttu-id="21c8a-118">列表和列表数据</span><span class="sxs-lookup"><span data-stu-id="21c8a-118">Lists and list data</span></span>
- <span data-ttu-id="21c8a-119">网站配置设置</span><span class="sxs-lookup"><span data-stu-id="21c8a-119">Site configuration settings</span></span>
- <span data-ttu-id="21c8a-120">与网站或子网站相关的角色和安全信息</span><span class="sxs-lookup"><span data-stu-id="21c8a-120">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="21c8a-121">子网站的顶级网站、 其内容和用户信息</span><span class="sxs-lookup"><span data-stu-id="21c8a-121">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="21c8a-p103">删除网站集之前，我们建议您查看您的计划，概述了 SharePoint Online 网站由 Microsoft 维护的数据备份计划的 SharePoint Online 服务说明。请注意，可以从备份还原都会仅对网站集或子网站，而不用于文件、 列表或库。如果您需要恢复那些，请使用回收站。如果您意外删除网站集，它可以从还原网站集回收站由网站集管理员 93 天内。</span><span class="sxs-lookup"><span data-stu-id="21c8a-p103">Before you delete a site collection, we recommend you review the SharePoint Online Service Description for your plan, which outlines the data backup schedule maintained by Microsoft for SharePoint Online sites. Also note that restorations from backups can are only for site collections or sub-sites, not for files, lists, or libraries. If you need to recover those, use the Recycle Bin. If you accidentally delete a site collection, it can be restored from the Site Collection Recycle Bin by a Site Collection Administrator within 93 days.</span></span>

<span data-ttu-id="21c8a-p104">当用户清除已删除的项目从网站回收站，并且的保留期和备份期间过期，或者当管理员永久删除网站集使用[Remove-spodeletedsite cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)，发生此事件硬删除。当用户硬删除 （永久删除，或清除） 从 SharePoint Online 内容，所有的已删除的块的加密密钥也将被删除。以前存储已删除的块的磁盘上的块被标记为未使用并且可供重复使用。</span><span class="sxs-lookup"><span data-stu-id="21c8a-p104">Hard deletion occurs when a user purges deleted items from the Site Recycle Bin, and the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](https://docs.microsoft.com/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted. The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
