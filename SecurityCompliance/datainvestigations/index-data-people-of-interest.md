---
title: 调查数据的高级索引
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2e2077fa5ee5333a563470d5bcbb140364bc0ba2
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150774"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="540dc-102">调查数据的高级索引</span><span class="sxs-lookup"><span data-stu-id="540dc-102">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="540dc-103">可以对实时系统中的内容进行部分索引, 其中包括映像的存在、不受支持的文件类型或在遇到索引文件大小限制时遇到的多种原因。</span><span class="sxs-lookup"><span data-stu-id="540dc-103">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="540dc-104">当处理高风险数据溢出时, 您需要确保您的搜索捕获了要调查的所有数据。</span><span class="sxs-lookup"><span data-stu-id="540dc-104">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="540dc-105">当向数据调查中添加了感兴趣的人时, 将重新处理 Office 365 中被视为部分索引的任何内容, 以使其完全可搜索。</span><span class="sxs-lookup"><span data-stu-id="540dc-105">When a person of interest is added to a Data investigation, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="540dc-106">此过程称为 "*高级索引*"。</span><span class="sxs-lookup"><span data-stu-id="540dc-106">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="540dc-107">若要了解有关 Office 365 中的处理支持和部分索引项目的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="540dc-107">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="540dc-108">数据调查中支持的文件类型</span><span class="sxs-lookup"><span data-stu-id="540dc-108">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="540dc-109">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="540dc-109">Partially indexed items in Content Search in Office 365</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/partially-indexed-items-in-content-search)

- [<span data-ttu-id="540dc-110">由 Exchange 搜索编制索引的文件格式</span><span class="sxs-lookup"><span data-stu-id="540dc-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/en-us/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="540dc-111">SharePoint Server 中的默认爬网文件扩展名和分析文件类型</span><span class="sxs-lookup"><span data-stu-id="540dc-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/en-us/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="540dc-112">查看高级索引结果</span><span class="sxs-lookup"><span data-stu-id="540dc-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="540dc-113">完成高级索引过程后, 您可以了解重新处理的有效性。</span><span class="sxs-lookup"><span data-stu-id="540dc-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="540dc-114">在感兴趣的 "索引" 视图中, 图形列出了添加到*混合索引*中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="540dc-114">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="540dc-115">混合索引是数据调查 (预览) 存储重新处理的内容的地方。</span><span class="sxs-lookup"><span data-stu-id="540dc-115">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="540dc-116">该图还包括需要修正的项目数, 以及按文件类型列出的错误的另一个关系图。</span><span class="sxs-lookup"><span data-stu-id="540dc-116">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="540dc-117">有关详细信息, 请参阅[处理数据时的错误修正](error-remediation.md)。</span><span class="sxs-lookup"><span data-stu-id="540dc-117">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="540dc-118">为感兴趣的人员更新高级索引</span><span class="sxs-lookup"><span data-stu-id="540dc-118">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="540dc-119">当向数据调查中添加了感兴趣的人时, 将重新处理所有部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="540dc-119">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="540dc-120">但是, 随着时间的推移, 可以向用户的邮箱或 OneDrive 帐户中添加更多部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="540dc-120">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="540dc-121">如果需要, 可以更新索引。</span><span class="sxs-lookup"><span data-stu-id="540dc-121">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="540dc-122">更新感兴趣的人员索引是一个长时间运行的过程。</span><span class="sxs-lookup"><span data-stu-id="540dc-122">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="540dc-123">建议在调查中每日更新索引不超过一次。</span><span class="sxs-lookup"><span data-stu-id="540dc-123">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
