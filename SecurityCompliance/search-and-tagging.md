---
title: 搜索和标记
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 在高级电子数据展示中, 搜索和标记模块使您能够在您的案例中搜索、预览和组织文档。目前, 此模块在 beta 版中。
ms.openlocfilehash: 58913a01f30b4169470592f5fc271e3ce785ac5d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222961"
---
# <a name="search-and-tagging"></a><span data-ttu-id="24445-104">搜索和标记</span><span class="sxs-lookup"><span data-stu-id="24445-104">Search and Tagging</span></span>

<span data-ttu-id="24445-p102">在高级电子数据展示中, 搜索和标记模块使您能够在您的案例中搜索、预览和组织文档。目前, 此模块在 beta 版中。有关搜索和标记的简短演示, 请参阅[使用高级电子数据展示视频管理数据](https://www.youtube.com/watch?v=VaPYL3DHP6I)。</span><span class="sxs-lookup"><span data-stu-id="24445-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta. For a brief demonstration of searching and tagging, see the [Manage your data with Advanced eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) video.</span></span>

> [!NOTE]
> <span data-ttu-id="24445-p103">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="24445-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="24445-110">在你的案例中搜索文档</span><span class="sxs-lookup"><span data-stu-id="24445-110">Search the documents in your case</span></span>

<span data-ttu-id="24445-p104">在高级电子数据展示案例中处理文档 (并根据需要运行分析或相关性模块) 后, 您可以使用搜索和标记来搜索文档, 然后通过应用大小写特定的标记 (也称为 "标签") 来组织这些文档。您可以使用提供的条件卡或使用关键字条件卡中类似 KQL 的查询语言来定义搜索查询。常用 KQL 语法, 如 AND、OR、NOT 和 NEAR (n), 以及尾部多字符通配符 (\*)。</span><span class="sxs-lookup"><span data-stu-id="24445-p104">After you have processed documents in an Advanced eDiscovery case (and optionally run the Analyze or Relevance module), you can use the Search and Tagging to search documents and then organize them by applying case-specific tags (also called labels). You can define a search query using the provided condition cards or by using a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*).</span></span> 

<span data-ttu-id="24445-p105">下表列出了您可以使用 KQL 关键字查询搜索的属性。或者, 您可以使用高级电子数据展示搜索工具中的条件卡将条件 (对于选定的属性) 添加到搜索查询中。</span><span class="sxs-lookup"><span data-stu-id="24445-p105">The following table lists the properties that you can search for using a KQL keyword query. Alternatively, you can use a condition card for in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query.</span></span>

|<span data-ttu-id="24445-116">**属性**</span><span class="sxs-lookup"><span data-stu-id="24445-116">**Property**</span></span>|<span data-ttu-id="24445-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="24445-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="24445-118">**caselabel**</span><span class="sxs-lookup"><span data-stu-id="24445-118">**caselabel**</span></span> <br/> | <span data-ttu-id="24445-119">标记文档时创建/应用的标记的名称。</span><span class="sxs-lookup"><span data-stu-id="24445-119">The name of the tag created/applied when a document is tagged.</span></span> <br/> |
|<span data-ttu-id="24445-120">**保管人**</span><span class="sxs-lookup"><span data-stu-id="24445-120">**custodian**</span></span> <br/> | <span data-ttu-id="24445-121">与文档关联的保管人;受限制。</span><span class="sxs-lookup"><span data-stu-id="24445-121">The custodian associated with a document; subject to limitations.</span></span> <br/> |
|<span data-ttu-id="24445-122">**结束**</span><span class="sxs-lookup"><span data-stu-id="24445-122">**date**</span></span> <br/> | <span data-ttu-id="24445-123">电子邮件的发送日期;网站文档的修改日期。</span><span class="sxs-lookup"><span data-stu-id="24445-123">Sent date for email; the modified date for site documents.</span></span> <br/> |
|<span data-ttu-id="24445-124">**fileid**</span><span class="sxs-lookup"><span data-stu-id="24445-124">**fileid**</span></span> <br/> | <span data-ttu-id="24445-125">事例中的文件 ID。</span><span class="sxs-lookup"><span data-stu-id="24445-125">The File ID within the case.</span></span> <br/> |
|<span data-ttu-id="24445-126">**类型**</span><span class="sxs-lookup"><span data-stu-id="24445-126">**filetype**</span></span> <br/> | <span data-ttu-id="24445-127">本机文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="24445-127">The native file extension.</span></span> <br/> |
|<span data-ttu-id="24445-128">**fileclass**</span><span class="sxs-lookup"><span data-stu-id="24445-128">**fileclass**</span></span> <br/> | <span data-ttu-id="24445-129">电子邮件、文档或附件。</span><span class="sxs-lookup"><span data-stu-id="24445-129">Email, document, or attachment.</span></span> <br/> |
|<span data-ttu-id="24445-130">**senderauthor**</span><span class="sxs-lookup"><span data-stu-id="24445-130">**senderauthor**</span></span> <br/> | <span data-ttu-id="24445-131">电子邮件的发件人;网站文档的作者。</span><span class="sxs-lookup"><span data-stu-id="24445-131">The sender for email; the author for site documents.</span></span> <br/> |
|<span data-ttu-id="24445-132">**字体**</span><span class="sxs-lookup"><span data-stu-id="24445-132">**size**</span></span> <br/> | <span data-ttu-id="24445-133">文件大小 (以 KB 为单位)。</span><span class="sxs-lookup"><span data-stu-id="24445-133">The size of the file in KB.</span></span> <br/> |
|<span data-ttu-id="24445-134">**subjecttitle**</span><span class="sxs-lookup"><span data-stu-id="24445-134">**subjecttitle**</span></span> <br/> | <span data-ttu-id="24445-135">电子邮件的主题;网站文档的标题。</span><span class="sxs-lookup"><span data-stu-id="24445-135">The subject for email; the title for site documents.</span></span> <br/> |
|<span data-ttu-id="24445-136">**bcc**</span><span class="sxs-lookup"><span data-stu-id="24445-136">**bcc**</span></span> <br/> | <span data-ttu-id="24445-137">电子邮件的 "密件抄送" 字段。</span><span class="sxs-lookup"><span data-stu-id="24445-137">The Bcc field of an email.</span></span> <br/> |
|<span data-ttu-id="24445-138">**cc**</span><span class="sxs-lookup"><span data-stu-id="24445-138">**cc**</span></span> <br/> | <span data-ttu-id="24445-139">电子邮件的 "抄送" 字段。</span><span class="sxs-lookup"><span data-stu-id="24445-139">The Cc field of an email.</span></span> <br/> |
|<span data-ttu-id="24445-140">**参与者**</span><span class="sxs-lookup"><span data-stu-id="24445-140">**participants**</span></span> <br/> | <span data-ttu-id="24445-141">电子邮件线索中所有参与者的电子邮件地址, 包括缺少的链接。</span><span class="sxs-lookup"><span data-stu-id="24445-141">The email address of all participants in an email thread, including for missing links.</span></span> <br/> |
|<span data-ttu-id="24445-142">**收到**</span><span class="sxs-lookup"><span data-stu-id="24445-142">**received**</span></span> <br/> | <span data-ttu-id="24445-143">接收电子邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="24445-143">The date an email was received.</span></span> <br/> |
|<span data-ttu-id="24445-144">**发送**</span><span class="sxs-lookup"><span data-stu-id="24445-144">**recipients**</span></span> <br/> | <span data-ttu-id="24445-145">电子邮件的收件人, 包括在 "收件人"、"抄送" 或 "密件抄送" 字段中。</span><span class="sxs-lookup"><span data-stu-id="24445-145">Recipients of an email, included on the To, Cc, or Bcc fields.</span></span> <br/> |
|<span data-ttu-id="24445-146">**sender**</span><span class="sxs-lookup"><span data-stu-id="24445-146">**sender**</span></span> <br/> | <span data-ttu-id="24445-147">电子邮件的发件人。</span><span class="sxs-lookup"><span data-stu-id="24445-147">The sender of an email.</span></span> <br/> |
|<span data-ttu-id="24445-148">**lastmodifieddate**</span><span class="sxs-lookup"><span data-stu-id="24445-148">**lastmodifieddate**</span></span> <br/> | <span data-ttu-id="24445-149">网站文档的上次修改日期。</span><span class="sxs-lookup"><span data-stu-id="24445-149">The last modified date of a site document.</span></span> <br/> |
|<span data-ttu-id="24445-150">**送**</span><span class="sxs-lookup"><span data-stu-id="24445-150">**sent**</span></span> <br/> | <span data-ttu-id="24445-151">电子邮件的发送日期。</span><span class="sxs-lookup"><span data-stu-id="24445-151">The sent date of an email.</span></span> <br/> |
|<span data-ttu-id="24445-152">**自**</span><span class="sxs-lookup"><span data-stu-id="24445-152">**to**</span></span> <br/> | <span data-ttu-id="24445-153">在电子邮件的 "收件人" 字段中列出的收件人。</span><span class="sxs-lookup"><span data-stu-id="24445-153">The recipient listed in the To field of an email.</span></span> <br/> |
|<span data-ttu-id="24445-154">**编写**</span><span class="sxs-lookup"><span data-stu-id="24445-154">**author**</span></span> <br/> | <span data-ttu-id="24445-155">网站文档的作者。</span><span class="sxs-lookup"><span data-stu-id="24445-155">The author of a site document.</span></span> <br/> |
|<span data-ttu-id="24445-156">**title**</span><span class="sxs-lookup"><span data-stu-id="24445-156">**title**</span></span> <br/> | <span data-ttu-id="24445-157">网站文档的标题。</span><span class="sxs-lookup"><span data-stu-id="24445-157">The title of a site document.</span></span> <br/> |
|<span data-ttu-id="24445-158">**dominanttheme**\*</span><span class="sxs-lookup"><span data-stu-id="24445-158">**dominanttheme**\*</span></span> <br/> | <span data-ttu-id="24445-159">项目的主要主题。</span><span class="sxs-lookup"><span data-stu-id="24445-159">The dominant theme of an item.</span></span> <br/> |
|<span data-ttu-id="24445-160">**themeslist**\*</span><span class="sxs-lookup"><span data-stu-id="24445-160">**themeslist**\*</span></span> <br/> | <span data-ttu-id="24445-161">与项目相关联的主题。</span><span class="sxs-lookup"><span data-stu-id="24445-161">Themes that are associated with an item.</span></span> <br/> |
|<span data-ttu-id="24445-162">**readpercentile_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="24445-162">**readpercentile_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="24445-163">项目的已读百分点值, 针对 [issuenum] 定义的问题。</span><span class="sxs-lookup"><span data-stu-id="24445-163">The read percentile of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="24445-164">**relevancescore_ [issuenum]**\*\*</span><span class="sxs-lookup"><span data-stu-id="24445-164">**relevancescore_[issuenum]**\*\*</span></span> <br/> | <span data-ttu-id="24445-165">项目的相关性分数, 针对 [issuenum] 定义的问题。</span><span class="sxs-lookup"><span data-stu-id="24445-165">The relevance score of an item, for the issue defined by [issuenum].</span></span> <br/> |
|<span data-ttu-id="24445-166">**relevancetag_ [tagname]**\*\*</span><span class="sxs-lookup"><span data-stu-id="24445-166">**relevancetag_[tagname]**\*\*</span></span> <br/> | <span data-ttu-id="24445-167">如果已手动为项目标记相关性, 则由 [tagname] 定义的标记。</span><span class="sxs-lookup"><span data-stu-id="24445-167">If an item has been manually tagged for relevance, the tag defined by  [tagname].</span></span> <br/> |
|||

<span data-ttu-id="24445-168">\*仅当主题模块已运行时才可用。</span><span class="sxs-lookup"><span data-stu-id="24445-168">\* Only available if the Themes module has been run.</span></span>

<span data-ttu-id="24445-169">\*\*仅在已运行相关性模块时可用。</span><span class="sxs-lookup"><span data-stu-id="24445-169">\*\* Only available if the Relevance module has been run.</span></span>

<span data-ttu-id="24445-p106">或者, 您可以使用高级电子数据展示搜索工具中的条件卡向搜索查询添加条件 (对于选定的属性)。下面的屏幕截图显示了可以添加到查询中的条件。"**组**" 列指示属性是应用于电子邮件、网站文档还是两者 (由*常见*值表示)。此列还标识了在运行相关性模块后可用的可搜索属性。</span><span class="sxs-lookup"><span data-stu-id="24445-p106">Alternatively, you can use a condition card in the Advanced eDiscovery Search tool to add a condition (for selected properties) to a search query. The following screenshot shows the conditions that can be added to a query. The **Group** column indicates whether the property applies to email, site documents, or both (indicated by the value *Common*). This column also identifies the searchable properties that are available after you run the Relevance module.</span></span>

![高级电子数据展示搜索工具中的搜索条件](media/AeDSearchConditions.png)

<span data-ttu-id="24445-175">有关可搜索属性的详细信息, 请参阅[关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="24445-175">For more information about searchable properties, see [Keyword queries and search conditions](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24445-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24445-176">See also</span></span>

[<span data-ttu-id="24445-177">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="24445-177">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-178">了解相关性方面的评估</span><span class="sxs-lookup"><span data-stu-id="24445-178">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-179">标记和评估</span><span class="sxs-lookup"><span data-stu-id="24445-179">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-180">标记和相关性培训</span><span class="sxs-lookup"><span data-stu-id="24445-180">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-181">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="24445-181">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-182">根据结果做出决定</span><span class="sxs-lookup"><span data-stu-id="24445-182">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="24445-183">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="24445-183">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

