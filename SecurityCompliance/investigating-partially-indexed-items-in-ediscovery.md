---
title: 使用 Office 365 电子数据展示调查部分索引项
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分索引项目 (也称为未编制索引项) 是 SharePoint 和 OneDrive 网站上的 Exchange 邮箱项目和文档, 由于某些原因未完全为内容搜索编制索引。 在本文中, 您可以了解为什么无法将项目编入搜索, 并作为部分索引项目返回, 确定部分索引项目的搜索错误, 以及使用 PowerShell 脚本确定组织的部分索引电子邮件的公开程度。items.
ms.openlocfilehash: d6b1326498780a5d40e49ff22aa1ac7d16bee8e4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254116"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="d6c1f-104">使用 Office 365 电子数据展示调查部分索引项</span><span class="sxs-lookup"><span data-stu-id="d6c1f-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="d6c1f-105">从安全 & 合规中心运行的内容搜索会在运行搜索时自动在估计的搜索结果中包含部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-105">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="d6c1f-106">部分索引项目是指 SharePoint 和 OneDrive for business 网站上的 Exchange 邮箱项目和文档, 因为某些原因未完全编制搜索索引。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-106">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="d6c1f-107">大多数电子邮件和网站文档都已成功编制索引, 因为它们位于[电子邮件的索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)内。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-107">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="d6c1f-108">但是, 某些项目可能超出这些索引限制, 将对其进行部分索引。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-108">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="d6c1f-109">以下是在运行内容搜索时无法将项目编入索引并作为部分索引项目返回的其他原因:</span><span class="sxs-lookup"><span data-stu-id="d6c1f-109">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="d6c1f-110">电子邮件包含无法编制索引的文件类型的附加文件;在大多数情况下,[无法识别或不支持对文件类型进行索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="d6c1f-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="d6c1f-111">电子邮件有一个没有有效处理程序的附加文件, 如图像文件;这是部分索引的电子邮件项目的最常见原因</span><span class="sxs-lookup"><span data-stu-id="d6c1f-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="d6c1f-112">附加到电子邮件的文件过多</span><span class="sxs-lookup"><span data-stu-id="d6c1f-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="d6c1f-113">附加到电子邮件的文件过大</span><span class="sxs-lookup"><span data-stu-id="d6c1f-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="d6c1f-114">文件类型支持索引, 但特定文件发生索引错误</span><span class="sxs-lookup"><span data-stu-id="d6c1f-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="d6c1f-115">尽管它不同, 但大多数 Office 365 组织客户的内容数量少于 1%, 而按部分索引的大小少于 12% 的内容。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-115">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="d6c1f-116">卷与大小之间的差异在于, 较大的文件包含无法完全编制索引的内容的可能性较高。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-116">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="d6c1f-117">对于搜索, 部分索引项目数的变化是什么？</span><span class="sxs-lookup"><span data-stu-id="d6c1f-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="d6c1f-118">在 Security & 合规中心中运行内容搜索后, 搜索的位置中的部分索引项目的总数和大小将列在搜索结果统计信息中, 并显示在搜索的详细统计信息中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-118">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="d6c1f-119">请注意, 这些项在搜索统计信息中称为未*编制索引的项*。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-119">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="d6c1f-120">下面几项操作将影响在搜索结果中返回的部分已编制索引项的数目:</span><span class="sxs-lookup"><span data-stu-id="d6c1f-120">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="d6c1f-121">如果项目已部分编制了索引, 并且与搜索查询相匹配, 则会将其包含在搜索结果项的计数 (和大小) 和部分索引项中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-121">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="d6c1f-122">但是, 当导出相同搜索的结果时, 该项目仅包含在一组搜索结果中;它不包含为部分索引项。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-122">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="d6c1f-123">如果为搜索查询指定日期范围 (通过将其包含在关键字查询中或使用条件), 则任何不符合日期范围的部分索引项都不会包含在部分索引项的计数中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-123">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="d6c1f-124">只有位于日期范围内的部分索引项才包含在部分索引项的计数中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-124">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="d6c1f-125">**注意:** 位于 SharePoint 和 OneDrive 网站中的部分索引项*不*包含在搜索的详细统计信息中显示的部分索引项的估计中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-125">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="d6c1f-126">但是, 当您导出内容搜索的结果时, 可以导出部分索引的项目。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-126">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="d6c1f-127">例如, 如果您仅搜索内容搜索中的网站, 估计的数字部分索引项将为零。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-127">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="d6c1f-128">计算组织中部分索引项目的比率</span><span class="sxs-lookup"><span data-stu-id="d6c1f-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="d6c1f-129">若要了解组织对部分索引项目的暴露程度, 可以对所有邮箱中的所有内容运行搜索 (通过使用空白的关键字查询)。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-129">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="d6c1f-130">在下面的示例中, 有 56208 (4830 MB) 的完全索引项和 470 (316 MB) 部分索引项。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-130">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![显示部分索引项目的搜索统计信息示例](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="d6c1f-132">您可以使用以下计算来确定部分索引项目的百分比。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="d6c1f-133">**若要计算组织中部分索引项目的比率, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="d6c1f-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="d6c1f-134">通过使用上一示例中的搜索结果, 将对所有邮箱项目的 84% 进行部分索引。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="d6c1f-135">**若要计算组织中部分索引项目大小的百分比, 请执行以下操作:**</span><span class="sxs-lookup"><span data-stu-id="d6c1f-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="d6c1f-136">所以在上一示例中, 邮箱项目总大小的 6.54% 来自部分索引项目。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-136">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="d6c1f-137">如前所述, 大多数 Office 365 组织客户的内容少于 1%, 而按部分索引的大小少于 12% 的内容。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-137">As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="d6c1f-138">使用部分索引项目</span><span class="sxs-lookup"><span data-stu-id="d6c1f-138">Working with partially indexed items</span></span>

<span data-ttu-id="d6c1f-139">在需要检查部分项目以验证它们不包含相关信息的情况下, 您可以导出包含部分索引项目相关信息的[内容搜索报告](export-a-content-search-report.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-139">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="d6c1f-140">导出内容搜索报告时, 请务必选择包含部分索引项目的导出选项之一。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-140">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![选择第二个或第三个选项以导出部分索引项目](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="d6c1f-142">当您使用其中一个选项导出内容搜索结果或内容搜索报告时, 导出将包含一个名为 "未编制索引的项目 .csv" 的报告。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-142">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="d6c1f-143">此报告包含与 ResultsLog 文件相同的大部分信息;但是, 未编制索引的项目 .csv 文件还包含与部分索引项目相关的两个字段:**错误标记**和**错误属性**。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-143">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="d6c1f-144">这些字段包含有关每个部分索引项的索引错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-144">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="d6c1f-145">使用这两个字段中的信息可帮助您确定您的调查是否有特定影响的索引错误。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-145">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="d6c1f-146">如果这样做, 您可以执行目标内容搜索并检索和导出特定的电子邮件和 SharePoint 或 OneDrive 文档, 以便您可以对其进行检查以确定它们是否与您的调查相关。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-146">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="d6c1f-147">有关分步说明, 请参阅[在 Office 365 中准备用于目标内容搜索的 CSV 文件](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-147">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="d6c1f-148">**注意:** 未编制索引的项目 .csv 文件还包含名为 "**错误类型**" 和 "**错误消息**" 的字段。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-148">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="d6c1f-149">这些字段包含的信息与 "**错误标记**" 和 "**错误属性**" 字段中的信息类似, 但详细信息较少。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-149">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="d6c1f-150">您可以安全地忽略这些旧字段。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-150">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="d6c1f-151">与部分索引项目相关的错误</span><span class="sxs-lookup"><span data-stu-id="d6c1f-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="d6c1f-152">错误标记由两条信息组成, 即错误和文件类型。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-152">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="d6c1f-153">例如, 在此错误/文件对:</span><span class="sxs-lookup"><span data-stu-id="d6c1f-153">For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="d6c1f-154">`parseroutputsize`是错误, `xls`是发生错误的文件的文件类型。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-154">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="d6c1f-155">如果无法识别文件类型或文件类型不适用于该错误, 您将看到替换文件类型的值`noformat` 。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-155">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="d6c1f-156">下面列出了索引错误和可能的错误原因的说明。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="d6c1f-157">**错误标记**</span><span class="sxs-lookup"><span data-stu-id="d6c1f-157">**Error tag**</span></span>|<span data-ttu-id="d6c1f-158">**Description**</span><span class="sxs-lookup"><span data-stu-id="d6c1f-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="d6c1f-159">电子邮件的附件过多, 其中一些附件未处理。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="d6c1f-160">内容检索器和文档分析程序发现嵌套在其他附件中的附件级别过多。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-160">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="d6c1f-161">其中一些附件未处理。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-161">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="d6c1f-162">由于受 RMS 保护, 附件无法进行解码。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="d6c1f-163">附加到电子邮件的文件太大, 无法处理。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="d6c1f-164">将已处理的电子邮件写入索引时, 其中一个可索引的属性太大, 已被截尾取整。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-164">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="d6c1f-165">截断的属性在 "错误属性" 字段中列出。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-165">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="d6c1f-166">电子邮件包含无法处理为有效 Unicode 的文本。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-166">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="d6c1f-167">此项的索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-167">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="d6c1f-168">附件或电子邮件的内容已加密, Office 365 无法对内容进行解码。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="d6c1f-169">分析过程中出现未知错误。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-169">An unknown error occurred during parsing.</span></span> <span data-ttu-id="d6c1f-170">这通常是由于软件错误或服务崩溃造成的。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-170">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="d6c1f-171">由于附件太大, 分析程序无法处理该附件, 并且该附件的分析未发生或未完成。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="d6c1f-172">附件格式不正确, 无法由分析器进行处理。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-172">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="d6c1f-173">此结果来自旧文件格式、由不兼容软件创建的文件, 或假装为非声明内容的病毒。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-173">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="d6c1f-174">对附件解析的输出太大, 必须将其截断。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="d6c1f-175">附件的文件类型为 Office 365 无法检测到的文件类型。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="d6c1f-176">附件具有 Office 365could 检测的文件类型, 但不支持解析该文件类型。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="d6c1f-177">Exchange 存储中的电子邮件属性的值太大, 无法检索, 并且无法处理邮件。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-177">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="d6c1f-178">这通常只发生在电子邮件的 body 属性中。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-178">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="d6c1f-179">内容检索器无法对受 RMS 保护的邮件进行解码。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="d6c1f-180">编制索引期间在文档中标识了过多的单词。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-180">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="d6c1f-181">属性处理在达到限制时停止, 属性被截断。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-181">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="d6c1f-182">"错误" 域说明 "错误标记" 字段中列出的处理错误会影响哪些字段。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-182">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="d6c1f-183">如果您正在搜索属性 (例如`subject`或`participants`), 则邮件正文中的错误不会影响您的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-183">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="d6c1f-184">当准确确定可能需要进一步调查的部分已编制索引项时, 这可能很有用。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-184">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="d6c1f-185">使用 PowerShell 脚本确定组织部分索引的电子邮件项的公开程度</span><span class="sxs-lookup"><span data-stu-id="d6c1f-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="d6c1f-186">下面的步骤演示了如何运行 PowerShell 脚本, 以搜索所有 Exchange 邮箱中的所有项目, 然后生成有关组织的部分索引的电子邮件项目 (按计数和按大小) 的比率的报告, 并显示项目数 (和它们的文件类型), 用于发生的每个索引错误。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-186">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="d6c1f-187">使用上一节中的错误标记说明来标识索引错误。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-187">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="d6c1f-188">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `PartiallyIndexedItems.ps1`。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. <span data-ttu-id="d6c1f-189">[连接到安全 & 合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-189">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="d6c1f-190">在 Security & 合规性中心 PowerShell 中, 转到在步骤1中保存脚本的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="d6c1f-190">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="d6c1f-191">下面的示例展示了脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-191">Here's an example fo the output returned by the script.</span></span>
  
![生成来自组织公开的报告的脚本的输出示例, 以部分索引的电子邮件项目](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="d6c1f-193">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="d6c1f-193">Note the following:</span></span>
  
1. <span data-ttu-id="d6c1f-194">电子邮件项目的总数和大小, 以及组织的部分索引的电子邮件项目的比率 (按计数和按大小)</span><span class="sxs-lookup"><span data-stu-id="d6c1f-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="d6c1f-195">列表错误标记以及发生错误的相应文件类型。</span><span class="sxs-lookup"><span data-stu-id="d6c1f-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6c1f-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6c1f-196">See also</span></span>

[<span data-ttu-id="d6c1f-197">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="d6c1f-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
