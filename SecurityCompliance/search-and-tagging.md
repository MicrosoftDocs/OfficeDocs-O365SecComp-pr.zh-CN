---
title: 搜索和标记
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: 高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。
ms.openlocfilehash: fde887e496e9a40aa88d841053a0c66e48f04200
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525484"
---
# <a name="search-and-tagging"></a><span data-ttu-id="efbb1-104">搜索和标记</span><span class="sxs-lookup"><span data-stu-id="efbb1-104">Search and Tagging</span></span>

<span data-ttu-id="efbb1-p102">高级电子数据展示中, 搜索和添加标签模块，可以搜索、 预览和组织您的案例中的文档。目前，这一模块是 beta 中。</span><span class="sxs-lookup"><span data-stu-id="efbb1-p102">In Advanced eDiscovery, the Search and Tagging module enables you to search, preview, and organize the documents in your case. Currently, this module is in beta.</span></span>

> [!NOTE]
> <span data-ttu-id="efbb1-p103">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="efbb1-p103">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="search-the-documents-in-your-case"></a><span data-ttu-id="efbb1-109">在您的案例中搜索文档</span><span class="sxs-lookup"><span data-stu-id="efbb1-109">Search the documents in your case</span></span>

<span data-ttu-id="efbb1-p104">一旦您已处理高级电子数据展示中的文档和 （可选） 运行分析模块或相关性模块，您可以使用搜索和添加标签搜索通过这种情况中的文档并将它们组织使用特定于案例的标记。您可以定义查询使用提供的条件卡中，或通过关键字中的类似的 KQL 查询语言条件卡片。常见的 KQL 语法，例如 AND、 OR，NOT、 NEAR(n) 且受支持，以及尾随多字符通配符 （\*）。在查询语言属性名称中支持以下属性：</span><span class="sxs-lookup"><span data-stu-id="efbb1-p104">Once you have processed documents in Advanced eDiscovery and optionally run the Analyze module or the Relevance module, you can use Search and Tagging to search through the documents in the case and organize them using case-specific tags. You can define your queries using the provided condition cards, or through a KQL-like query language in the Keywords condition card. Common KQL syntax, such as AND, OR, NOT, and NEAR(n) are supported, as well as trailing multi-character wildcard (\*). These properties are supported in the query language property name:</span></span>

- <span data-ttu-id="efbb1-114">caselabel： 创建/应用标记中搜索和添加标签用于用例</span><span class="sxs-lookup"><span data-stu-id="efbb1-114">caselabel: tags created/applied in Search and Tagging for this case</span></span> 
- <span data-ttu-id="efbb1-115">管理员： 分配情况-受限制的管理员</span><span class="sxs-lookup"><span data-stu-id="efbb1-115">custodians: custodians assigned in the case - subject to limitations</span></span>
- <span data-ttu-id="efbb1-116">日期： 发送电子邮件的日期、 修改日期的文档</span><span class="sxs-lookup"><span data-stu-id="efbb1-116">date: sent date for email, modified date for documents</span></span>
- <span data-ttu-id="efbb1-117">fileid： 文件 ID 在这种情况</span><span class="sxs-lookup"><span data-stu-id="efbb1-117">fileid: file ID within the case</span></span>
- <span data-ttu-id="efbb1-118">filetype： 本机文件扩展名</span><span class="sxs-lookup"><span data-stu-id="efbb1-118">filetype: native file extension</span></span>
- <span data-ttu-id="efbb1-119">fileclass： 电子邮件、 文档或附件</span><span class="sxs-lookup"><span data-stu-id="efbb1-119">fileclass: email, document, or attachment</span></span>
- <span data-ttu-id="efbb1-120">senderauthor： 发件人的电子邮件，文档作者</span><span class="sxs-lookup"><span data-stu-id="efbb1-120">senderauthor: sender for emails, author for documents</span></span>
- <span data-ttu-id="efbb1-121">大小： kb 的文件的大小</span><span class="sxs-lookup"><span data-stu-id="efbb1-121">size: size of the file in KB</span></span>
- <span data-ttu-id="efbb1-122">subjecttitle： 的电子邮件，标题的文档主题</span><span class="sxs-lookup"><span data-stu-id="efbb1-122">subjecttitle: subject for emails, title for documents</span></span>
- <span data-ttu-id="efbb1-123">bcc</span><span class="sxs-lookup"><span data-stu-id="efbb1-123">bcc</span></span>
- <span data-ttu-id="efbb1-124">cc</span><span class="sxs-lookup"><span data-stu-id="efbb1-124">cc</span></span>
- <span data-ttu-id="efbb1-125">参与者： 电子邮件地址的电子邮件线程，包括缺失的链接中的所有参与者</span><span class="sxs-lookup"><span data-stu-id="efbb1-125">participants: Email addresses of all participants in an email thread, including for missing links</span></span>
- <span data-ttu-id="efbb1-126">接收： 接收日期</span><span class="sxs-lookup"><span data-stu-id="efbb1-126">received: received date</span></span>
- <span data-ttu-id="efbb1-127">收件人： 电子邮件收件人的名称或地址 （，抄送，密件抄送)</span><span class="sxs-lookup"><span data-stu-id="efbb1-127">recipients: email recipient names or addresses (to, cc, bcc)</span></span>
- <span data-ttu-id="efbb1-128">sender</span><span class="sxs-lookup"><span data-stu-id="efbb1-128">sender</span></span>
- <span data-ttu-id="efbb1-129">lastmodifieddate： 上次修改日期的文档</span><span class="sxs-lookup"><span data-stu-id="efbb1-129">lastmodifieddate: last modified date of a document</span></span>
- <span data-ttu-id="efbb1-130">发送： 发送的电子邮件的日期</span><span class="sxs-lookup"><span data-stu-id="efbb1-130">sent: sent date of an email</span></span>
- <span data-ttu-id="efbb1-131">至</span><span class="sxs-lookup"><span data-stu-id="efbb1-131">to</span></span>
- <span data-ttu-id="efbb1-132">作者： 作者的电子邮件</span><span class="sxs-lookup"><span data-stu-id="efbb1-132">author: author of an email</span></span>
- <span data-ttu-id="efbb1-133">标题： 文档的标题</span><span class="sxs-lookup"><span data-stu-id="efbb1-133">title: title of a document</span></span>
- <span data-ttu-id="efbb1-134">dominanttheme： 项目的基准主题\*</span><span class="sxs-lookup"><span data-stu-id="efbb1-134">dominanttheme: dominant theme of an item\*</span></span>
- <span data-ttu-id="efbb1-135">themeslist： 与项目相关联的主题\*</span><span class="sxs-lookup"><span data-stu-id="efbb1-135">themeslist: themes that are associated with an item\*</span></span>
- <span data-ttu-id="efbb1-136">readpercentile_ [issuenum]: 读取百分点值的项目问题 [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="efbb1-136">readpercentile_[issuenum]: read percentile of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="efbb1-137">relevancescore_ [issuenum]: [issuenum] 问题项目的相关性分数\*\*</span><span class="sxs-lookup"><span data-stu-id="efbb1-137">relevancescore_[issuenum]: relevance score of an item for issue [issuenum]\*\*</span></span>
- <span data-ttu-id="efbb1-138">relevancetag_ [issuenum]: 如果手动已项目标记为相关性，其标记 [issuenum]\*\*</span><span class="sxs-lookup"><span data-stu-id="efbb1-138">relevancetag_[issuenum]: if an item has been manually tagged for relevance, its tag for [issuenum]\*\*</span></span>

<span data-ttu-id="efbb1-139">\*如果已运行主题模块唯一可用\*\*唯一可用，如果已运行相关性模块</span><span class="sxs-lookup"><span data-stu-id="efbb1-139">\* Only available if the Themes module has been run \*\* Only available if the Relevance module has been run</span></span>
  
## <a name="see-also"></a><span data-ttu-id="efbb1-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efbb1-140">See also</span></span>

[<span data-ttu-id="efbb1-141">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="efbb1-141">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-142">了解评估中相关性</span><span class="sxs-lookup"><span data-stu-id="efbb1-142">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-143">标签和评估</span><span class="sxs-lookup"><span data-stu-id="efbb1-143">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-144">标签和相关性培训</span><span class="sxs-lookup"><span data-stu-id="efbb1-144">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-145">跟踪相关性分析</span><span class="sxs-lookup"><span data-stu-id="efbb1-145">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-146">决定基于结果</span><span class="sxs-lookup"><span data-stu-id="efbb1-146">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="efbb1-147">测试相关性分析</span><span class="sxs-lookup"><span data-stu-id="efbb1-147">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

