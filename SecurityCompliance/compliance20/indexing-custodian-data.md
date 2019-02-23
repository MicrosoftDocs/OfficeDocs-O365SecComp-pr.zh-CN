---
title: 保管人数据的高级索引
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f8f1a92f001bf8f9e23f54bbb05fbbcf443bf4b9
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218662"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="b92ea-102">保管人数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="b92ea-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="b92ea-p101">将管理员添加到高级电子数据展示 (预览版) 时, 将重新处理 Office 365 中被视为部分索引的任何内容, 以使其完全可搜索。 此过程称为 "*高级索引*"。可以对内容进行部分索引, 其中包括图像存在、不受支持的文件类型或在遇到索引文件大小限制时的原因。 若要了解有关部分索引项目的详细信息, 请参阅[在 Office 365 中的内容搜索中的部分索引项目](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)。</span><span class="sxs-lookup"><span data-stu-id="b92ea-p101">When a custodian is added to an Advanced eDiscovery (Preview) case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.  This process is called *Advanced indexing*. Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.  To learn more about partially indexed items, see [Partially indexed items in Content Search in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search).</span></span>

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="b92ea-107">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="b92ea-107">Viewing Advanced indexing results</span></span>

<span data-ttu-id="b92ea-p102">完成高级索引过程后, 您可以了解重新处理的有效性。 在管理员索引视图中, 图形列出了添加到*混合索引*中的所有项目。 混合索引是高级电子数据展示 (预览版) 存储重新处理的内容的位置。</span><span class="sxs-lookup"><span data-stu-id="b92ea-p102">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.  In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.  The hybrid index is where Advanced eDiscovery (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="b92ea-p103">该图还包括需要修正的项目数, 以及按文件类型列出的错误的另一个关系图。有关详细信息, 请参阅[处理数据时的错误修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="b92ea-p103">The graph also includes the number of items that require remediation and another graph of errors by file type. For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="b92ea-113">更新保管人的高级索引</span><span class="sxs-lookup"><span data-stu-id="b92ea-113">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="b92ea-p104">将管理员添加到高级电子数据展示 (预览) 的情况下, 将重新处理所有部分索引项目。但是, 随着时间的推移, 可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。 如果需要, 可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="b92ea-p104">When a custodian is added to an Advanced eDiscovery (Preview) case, all partially indexed items are re-processed. However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.  When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="b92ea-p105">更新保管人索引是一个长时间运行的过程。建议您在一种情况下每天不将索引更新一次以上。</span><span class="sxs-lookup"><span data-stu-id="b92ea-p105">Updating custodian indexes is a long running process. It's recommended that you don't update indexes more than once per day in a case.</span></span>
