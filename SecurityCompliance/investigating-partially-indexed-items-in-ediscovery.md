---
title: 使用 Office 365 电子数据展示调查部分索引项
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分，索引项目 （还呼叫未编制索引项） 是 Exchange 邮箱项目和 SharePoint 上的文档和 OneDrive 网站的某种原因或者没有完全内容搜索编制索引。本文中，您可以了解项为什么不能用于搜索索引和部分索引项目以返回，识别部分已索引项，搜索错误并使用 PowerShell 脚本来确定贵组织的遭受部分索引的电子邮件项目。
ms.openlocfilehash: 4e8e8c31e6c5450a9b84a1240c2ae8d891c1bd6f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525951"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="9e0f8-104">使用 Office 365 电子数据展示调查部分索引项</span><span class="sxs-lookup"><span data-stu-id="9e0f8-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="9e0f8-p102">从 Office 365 安全性运行内容搜索&amp;合规性中心自动包括部分索引的项目中估计的搜索结果时运行的搜索。部分索引的项目是 Exchange 邮箱项目和 SharePoint 和 OneDrive 上的一些原因或者没有完全编制索引以搜索业务网站的文档。大多数电子邮件和网站文档因为它们归属于[索引限制的电子邮件](limits-for-content-search.md#indexinglimits)成功编制索引。但是，某些项可能会超过这些索引限制，并将部分编制索引。下面是其他原因项不能用于搜索索引以及当您运行内容搜索部分索引项目以返回：</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p102">A Content Search that you run from the Office 365 Security &amp; Compliance Center automatically includes partially indexed items in the estimated search results when you run a search. Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search. Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexinglimits). However, some items may exceed these indexing limits, and will be partially indexed. Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="9e0f8-110">电子邮件有文件类型无法进行索引; 附加的的文件在大多数情况下，文件类型是[无法识别或不受支持的索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="9e0f8-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="9e0f8-111">电子邮件有有效的处理程序中，不附加的文件，如图像文件;这是部分索引的电子邮件项目的最常见原因</span><span class="sxs-lookup"><span data-stu-id="9e0f8-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="9e0f8-112">文件太多附加到电子邮件</span><span class="sxs-lookup"><span data-stu-id="9e0f8-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="9e0f8-113">附加到电子邮件的文件是太大</span><span class="sxs-lookup"><span data-stu-id="9e0f8-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="9e0f8-114">文件类型支持检索，但是特定文件出现检索错误</span><span class="sxs-lookup"><span data-stu-id="9e0f8-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="9e0f8-p103">尽管各不相同，大多数 Office 365 组织客户可以通过音量和小于 12%的内容具有按部分编制索引的大小小于 1%的内容。与大小卷之间的差异的原因是较大的文件具有更高版本包含不能完全编制索引的内容的概率。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p103">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed. The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="9e0f8-117">部分索引的项计数搜索为何更改？</span><span class="sxs-lookup"><span data-stu-id="9e0f8-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="9e0f8-p104">Office 365 安全性运行内容搜索后&amp;的详细统计信息中显示的搜索结果统计信息中列出合规性中心、 总数和搜索的位置中的部分索引项目的大小搜索。请注意这些称为*未编制索引的项*中的搜索统计信息。下面是会影响搜索结果中返回的部分索引项的数目的几个事项：</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p104">After you run a Content Search in the Office 365 Security &amp; Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search. Note these are called  *unindexed items*  in the search statistics. Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="9e0f8-p105">如果部分编制索引和搜索查询匹配的项目，它包含在计数 （和大小） 的搜索结果项目和部分索引的项。但是，当导出的同一个搜索结果，项是只包括在组搜索结果;它不包含为部分索引项。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p105">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items. However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="9e0f8-p106">如果您指定一个日期范围的搜索查询 （包括其关键字查询中） 或使用条件，与日期范围不匹配任何部分索引的项不包含的部分索引的项计数。仅在日期范围内的部分索引的项目包含在部分索引项的计数。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p106">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items. Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="9e0f8-p107">**注意：** 位于 SharePoint 中的部分索引的项目和 OneDrive 网站*不*包括在搜索的详细统计信息中显示的部分索引项目估计。但是，当您将导出的内容的搜索结果，则可以导出部分索引的项目。例如，如果您仅网站在搜索中搜索内容，估计数目部分索引的项目将为零。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p107">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search. However, partially indexed items can be exported when you export the results of a Content Search. For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="9e0f8-128">计算贵组织中的部分索引项目的比率</span><span class="sxs-lookup"><span data-stu-id="9e0f8-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="9e0f8-p108">若要了解部分索引项目的组织的风险，可以搜索所有内容中运行的所有邮箱 （通过使用空白关键字查询）。在下面的以下示例中，有 56,208 (4,830 MB) 完全编制索引项和 470 (316 MB) 部分，索引项目。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p108">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query). In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![搜索统计信息显示的示例部分索引项](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="9e0f8-132">您可以使用以下计算确定部分索引项目的百分比。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="9e0f8-133">**计算贵组织中的部分索引项的比例：**</span><span class="sxs-lookup"><span data-stu-id="9e0f8-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="9e0f8-134">使用上面的示例中，从搜索结果。 部分编制索引的所有邮箱项目 84%。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="9e0f8-135">**计算贵组织中的部分索引项目大小的百分比：**</span><span class="sxs-lookup"><span data-stu-id="9e0f8-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="9e0f8-p109">因此，在上一示例中，6.54%的邮箱项目的总大小为从部分索引项。如上文所述，大多数客户可以通过音量和小于 12%的内容按部分编制索引的大小的小于 1%的内容的 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p109">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items. As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="9e0f8-138">部分使用索引项</span><span class="sxs-lookup"><span data-stu-id="9e0f8-138">Working with partially indexed items</span></span>

<span data-ttu-id="9e0f8-p110">在情况下时您需要检查部分项目以验证它们不包含相关信息，您可以[导出内容的搜索报告](export-a-content-search-report.md)包含有关部分索引项目的信息。导出内容的搜索报告时，务必选择包括部分索引的项目导出选项之一。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p110">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items. When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![选择导出部分索引的项目的第二个或第三个选项](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="9e0f8-p111">导出内容的搜索结果或内容的搜索报告使用以下选项之一时，导出包括名为未编制索引 Items.csv 的报告。此报告包括大部分相同的信息的 ResultsLog.csv 文件;但是，未编制索引 Items.csv 文件还包括相关的部分索引项目的两个字段：**错误标记**和**Error 属性**。这些字段包含有关每个部分索引项的索引错误的信息。使用这两个字段中的信息可帮助您确定针对特定的索引错误影响您调查。如果是这样，您可以执行目标内容搜索和导出和检索特定的电子邮件和 SharePoint 或 OneDrive 文档，以便您可以检查它们来确定它们是否与调查相关。有关分步说明，请参阅[Prepare 目标内容搜索 Office 365 中的 CSV 文件](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p111">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv. This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**. These fields contain information about the indexing error for each partially indexed item. Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation. If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation. For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="9e0f8-p112">**注意：** 未编制索引 Items.csv 文件还包含名为**错误类型**和**错误消息**的字段。这些是包含信息类似于在**错误标记**和**Error 属性**字段中，但不是详细信息的信息的旧字段。您可以安全地忽略这些旧的字段。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p112">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**. These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information. You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="9e0f8-151">与部分索引项目相关的错误</span><span class="sxs-lookup"><span data-stu-id="9e0f8-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="9e0f8-p113">错误标记的信息、 错误和文件类型的两个部分组成。例如，在此错误/filetype 对：</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p113">Error tags are made up of two pieces of information, the error and the file type. For example, in this error/filetype pair:</span></span>

```
 parseroutputsize_xls
```

   
 <span data-ttu-id="9e0f8-p114">`parseroutputsize`错误和`xls`发生的错误的文件类型的文件类型。在情况下已未识别的文件类型或文件类型不适用于该错误，您将看到值`noformat`替换的文件类型。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p114">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on. In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="9e0f8-156">以下是原因的索引错误和警告的错误可能的说明的列表。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="9e0f8-157">**错误标记**</span><span class="sxs-lookup"><span data-stu-id="9e0f8-157">**Error tag**</span></span>|<span data-ttu-id="9e0f8-158">**说明**</span><span class="sxs-lookup"><span data-stu-id="9e0f8-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="9e0f8-159">电子邮件有附件太多，并且这些附件的一些或者没有处理。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="9e0f8-p115">内容检索器和文档分析程序找到嵌套在其他附件的附件太多的级别。一些这些附件未处理。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p115">The content retriever and document parser found too many levels of attachments nested inside other attachments. Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="9e0f8-162">附件失败，因为受 RMS 保护解码。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="9e0f8-163">附加到电子邮件的文件太大，无法进行处理。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="9e0f8-p116">编写时处理的电子邮件到索引，编制索引的属性之一太大，已被截断。错误属性字段中列出的截断的属性。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p116">When writing the processed email message to the index, one of the indexable properties was too large and was truncated. The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="9e0f8-p117">电子邮件包含无法处理为有效的 Unicode 的文本。针对此项目编制索引可能不完整。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p117">An email message contained text that couldn't be processed as valid Unicode. Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="9e0f8-168">附件或电子邮件的内容进行加密，和 Office 365 无法对内容进行解码。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="9e0f8-p118">在分析过程中出现未知的错误。这通常会导致从软件错误或服务崩溃。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p118">An unknown error occurred during parsing. This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="9e0f8-171">附件已被太大，分析程序处理，并解析该附件未发生或未完成。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="9e0f8-p119">附件格式不正确，无法由分析程序处理。此结果从可以旧文件格式，由不兼容的软件或病毒伪装以外声明为内容创建的文件。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p119">An attachment was malformed and couldn't be handled by the parser. This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="9e0f8-174">附件的分析的输出太大，且必须被截断。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="9e0f8-175">附件具有 Office 365 无法检测的文件类型。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="9e0f8-176">附件具有 Office 365could 检测，但分析该文件类型不受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="9e0f8-p120">电子邮件属性的值在 Exchange 存储区是太大，无法检索和无法处理邮件。这通常只发生一封电子邮件的正文属性。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p120">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed. This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="9e0f8-179">内容检索器失败进行解码受 RMS 保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="9e0f8-p121">在编制索引过程，文档中标识词太多。属性的处理停止时达到此限制，并且属性会被截断。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p121">Too many words were identified in the document during indexing. Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="9e0f8-p122">错误字段介绍哪些字段影响在错误标记字段中列出的处理错误。如果您要搜索的属性，如`subject`或`participants`，邮件的正文中的错误不会影响您的搜索结果。确定完全您可能需要进一步调查哪些部分索引的项目时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p122">Error fields describe which fields are affected by the processing error listed in the Error Tags field. If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search. This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="9e0f8-185">使用 PowerShell 脚本来确定贵组织的遭受部分索引的电子邮件项目</span><span class="sxs-lookup"><span data-stu-id="9e0f8-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="9e0f8-p123">以下步骤演示如何运行搜索所有项目中所有 Exchange 邮箱，然后生成有关贵组织的比率的部分索引的电子邮件项目的报告 （按计数和大小） 并显示的项目数的 PowerShell 脚本 （和其文件类型） 的每个索引所发生的错误。使用在上一节中的错误标记说明标识检索错误。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-p123">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs. Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="9e0f8-188">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `PartiallyIndexedItems.ps1`。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
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
   
2. <span data-ttu-id="9e0f8-189">[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-189">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="9e0f8-190">安全性&amp;合规性中心 PowerShell 中，转到步骤 1 中保存该脚本的位置的文件夹，然后运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="9e0f8-190">In Security &amp; Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
<span data-ttu-id="9e0f8-191">下面是一个示例 fo 脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-191">Here's an example fo the output returned by the script.</span></span>
  
![从部分生成您的组织暴露程度报告的脚本的输出示例编制索引的电子邮件项目](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="9e0f8-193">请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="9e0f8-193">Note the following:</span></span>
  
1. <span data-ttu-id="9e0f8-194">总数和电子邮件项目的大小和您的组织比部分索引的电子邮件项目 （按计数和大小）</span><span class="sxs-lookup"><span data-stu-id="9e0f8-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="9e0f8-195">列表错误标记和发生错误的相应的文件类型。</span><span class="sxs-lookup"><span data-stu-id="9e0f8-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e0f8-196">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0f8-196">See also</span></span>

[<span data-ttu-id="9e0f8-197">处理 Office 365 内容搜索中的部分索引项</span><span class="sxs-lookup"><span data-stu-id="9e0f8-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
