---
title: 查看证据中的数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 279d2117a69e889f9e605e0ab211c03c5842a59d
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31029920"
---
# <a name="review-data-in-evidence"></a><span data-ttu-id="c1fbd-102">查看证据中的数据</span><span class="sxs-lookup"><span data-stu-id="c1fbd-102">Review data in evidence</span></span>

<span data-ttu-id="c1fbd-103">**证据**是您收集的搜索结果的快照。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-103">**Evidence** is a snapshot of search results that you collected.</span></span> <span data-ttu-id="c1fbd-104">将搜索结果添加到证据中时, 将触发一个过程, 以提取文件、元数据和文本。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-104">When you add search results to evidence, a process is triggered to extract files, metadata, and text.</span></span> <span data-ttu-id="c1fbd-105">然后, 系统生成所有数据的新索引并添加到**证据**。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-105">Then, the system builds a new index of all the data and adds to **Evidence**.</span></span> 

<span data-ttu-id="c1fbd-106">对于任何时间敏感的事件, 这使您可以通过在原始位置删除数据, 同时调查隔离环境中重新创建的证据, 从而快速地包含环境。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-106">For any time-sensitive incidents, this allows you to quickly contain the environment by deleting data at original locations while investigating re-created evidence in a quarantined environment.</span></span> <span data-ttu-id="c1fbd-107">收集证据后, 可以查看以本机格式、文本格式或接近本机格式的单个文档。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-107">Once evidence is collected, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="c1fbd-108">此外, 还可以按时间范围、文件类型、数据所有者和许多其他条件卡片运行查询以缩小数据。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-108">Additionally, you can run queries to narrow the data by time range, file types, data owners, and many other condition cards.</span></span> <span data-ttu-id="c1fbd-109">使用作者/发件人/收件人条件卡, 可以快速检查溢出中涉及的人员以及是否有任何外部共享。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-109">Using Author/Sender/Recipient condition cards, you can quickly examine who are involved in the spill and if there have been any external shares.</span></span> <span data-ttu-id="c1fbd-110">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1fbd-110">For more information, see:</span></span>

  - [<span data-ttu-id="c1fbd-111">查询证据中的数据</span><span class="sxs-lookup"><span data-stu-id="c1fbd-111">Query the data in evidence</span></span>](evidence-query.md)

<span data-ttu-id="c1fbd-112">若要对文档进行分组并获取更多的审阅帮助, 请单击 "**管理证据**"。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-112">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="c1fbd-113">在**分析**磁贴中, 单击 "**分析**"。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-113">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="c1fbd-114">这将运行高级分析, 例如重复检测、电子邮件线程和主题分析。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="c1fbd-115">之后, 您可以查看数据的一般主题, 还可以通过电子邮件线索 (确切重复项和临近重复项) 组织文档, 以便于您进行调查。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, exact duplicates and near duplicates to facilitate your investigation.</span></span> <span data-ttu-id="c1fbd-116">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1fbd-116">For more information, see:</span></span>

  - [<span data-ttu-id="c1fbd-117">运行分析以加快检查速度</span><span class="sxs-lookup"><span data-stu-id="c1fbd-117">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)

## <a name="view-documents-in-evidence"></a><span data-ttu-id="c1fbd-118">查看证据中的文档</span><span class="sxs-lookup"><span data-stu-id="c1fbd-118">View documents in evidence</span></span>

<span data-ttu-id="c1fbd-119">数据调查 (预览) 通过几个具有不同用途的查看器显示内容。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-119">Data investigation (Preview) displays content via several viewers each with different purposes.</span></span> <span data-ttu-id="c1fbd-120">通过单击**证据**中的任何文档, 可以使用各种查看器。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-120">The various viewers can be used by clicking on any document in **Evidence**.</span></span> <span data-ttu-id="c1fbd-121">当前提供的查看者为:</span><span class="sxs-lookup"><span data-stu-id="c1fbd-121">The viewers currently provided are:</span></span>

- <span data-ttu-id="c1fbd-122">文件元数据</span><span class="sxs-lookup"><span data-stu-id="c1fbd-122">File metadata</span></span>
- <span data-ttu-id="c1fbd-123">本机视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-123">Native view</span></span>
- <span data-ttu-id="c1fbd-124">文本视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-124">Text view</span></span>
- <span data-ttu-id="c1fbd-125">批注视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-125">Annotate view</span></span>
- <span data-ttu-id="c1fbd-126">转换后的视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-126">Converted view</span></span>

## <a name="file-metadata"></a><span data-ttu-id="c1fbd-127">文件元数据</span><span class="sxs-lookup"><span data-stu-id="c1fbd-127">File metadata</span></span>

<span data-ttu-id="c1fbd-128">此面板可打开/关闭以显示与文档关联的各种元数据。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-128">This panel can be toggled on/off to display various metadata associated with the document.</span></span> <span data-ttu-id="c1fbd-129">尽管可以自定义搜索结果网格以显示特定元数据, 但在查看数据时, 水平滚动的情况也很难。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-129">Although the search results grid can be customized to display specific metadata, there are instances where scrolling horizontally can be difficult while reviewing data.</span></span> <span data-ttu-id="c1fbd-130">"文件元数据" 面板允许用户在查看器中切换视图。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-130">The File metadata panel allows a user to toggle on a view within the viewer.</span></span>

![<span data-ttu-id="c1fbd-131">文件元数据面板</span><span class="sxs-lookup"><span data-stu-id="c1fbd-131">File metadata panel</span></span>
](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="c1fbd-132">本机视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-132">Native view</span></span>

<span data-ttu-id="c1fbd-133">本机查看器显示文档的最丰富视图。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-133">The Native viewer displays the richest view of a document.</span></span> <span data-ttu-id="c1fbd-134">它支持数百种文件类型, 旨在将 truest 显示为可能的本机体验。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-134">It supports hundreds of file types and is meant to display the truest to native experience possible.</span></span> <span data-ttu-id="c1fbd-135">例如, 对于 Microsoft Office 文件, 查看器利用 Office Online 来显示文档注释、Excel 公式、隐藏的行/列、PowerPoint 备注等内容。有关 Office Online 查看器的详细信息, 请访问\[此处需要链接\]</span><span class="sxs-lookup"><span data-stu-id="c1fbd-135">For Microsoft Office files, for example, the viewer leverages Office Online in order to display content such as document comments, Excel formulas, hidden rows/columns, PowerPoint notes, etc. For more information regarding the Office Online viewers, visit here \[need link\]</span></span>

![<span data-ttu-id="c1fbd-136">本机视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-136">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="c1fbd-137">文本视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-137">Text view</span></span>

<span data-ttu-id="c1fbd-138">文本查看器提供了文件中提取的文本的视图。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-138">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="c1fbd-139">它将忽略任何嵌入的图像和格式, 但如果用户尝试快速了解内容, 将是一种非常强大的视图。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-139">It ignores any embedded images and formatting but will be a very performant view if a user is trying to understand the content quickly.</span></span> <span data-ttu-id="c1fbd-140">文本视图还包括其他功能:</span><span class="sxs-lookup"><span data-stu-id="c1fbd-140">Text view also includes other features:</span></span>

  - <span data-ttu-id="c1fbd-141">行计数器可更轻松地引用文档的特定部分</span><span class="sxs-lookup"><span data-stu-id="c1fbd-141">Line counter makes it easier to reference specific portions of a document</span></span>

  - <span data-ttu-id="c1fbd-142">将突出显示文档中的术语和滚动条的搜索词突出显示</span><span class="sxs-lookup"><span data-stu-id="c1fbd-142">Search hit highlighting that will highlight terms within the document as well as the scrollbar</span></span>

  - <span data-ttu-id="c1fbd-143">比较视图提供了比较视图, 可在查看临近重复文档时突出显示文本差异</span><span class="sxs-lookup"><span data-stu-id="c1fbd-143">Diff view provides a comparison view that highlights textual differences when viewing Near Duplicate documents</span></span>

![<span data-ttu-id="c1fbd-144">文本视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-144">Text view</span></span>
](../media/Reviewimage4.png)

![<span data-ttu-id="c1fbd-145">比较视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-145">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="c1fbd-146">批注视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-146">Annotate view</span></span>

<span data-ttu-id="c1fbd-147">"批注" 视图提供允许用户在调查过程中对文档应用标记的功能, 包括:</span><span class="sxs-lookup"><span data-stu-id="c1fbd-147">The Annotate view provides features that allow users to apply markup on a document during investigation including:</span></span>

  - <span data-ttu-id="c1fbd-148">区域密文–用户可以在文档中绘制一个框, 以便隐藏敏感内容</span><span class="sxs-lookup"><span data-stu-id="c1fbd-148">Area redactions – users can draw a box on the document in order to hide sensitive content</span></span>

  - <span data-ttu-id="c1fbd-149">铅笔–用户可以自由地在文档上绘图, 以便对文档的某些部分进行关注</span><span class="sxs-lookup"><span data-stu-id="c1fbd-149">Pencil – users can free-hand draw on a document in order to bring attention to certain portions of a document</span></span>

  - <span data-ttu-id="c1fbd-150">选择批注-用户可以在文档中选择批注, 以便删除</span><span class="sxs-lookup"><span data-stu-id="c1fbd-150">Select annotations - users can select annotations on a document in order to delete</span></span>

  - <span data-ttu-id="c1fbd-151">切换批注透明度–使批注半透明, 以便查看批注后面的内容</span><span class="sxs-lookup"><span data-stu-id="c1fbd-151">Toggle annotation transparency – makes annotations semi-transparent in order to view the content behind the annotation</span></span>

  - <span data-ttu-id="c1fbd-152">上一页–导航到上一页</span><span class="sxs-lookup"><span data-stu-id="c1fbd-152">Previous page – navigates to previous page</span></span>

  - <span data-ttu-id="c1fbd-153">下一页–导航到下一页</span><span class="sxs-lookup"><span data-stu-id="c1fbd-153">Next page – navigates to the next page</span></span>

  - <span data-ttu-id="c1fbd-154">转到页面–用户可以输入特定页码以导航到</span><span class="sxs-lookup"><span data-stu-id="c1fbd-154">Go to page – user can enter a specific page number to navigate to</span></span>

  - <span data-ttu-id="c1fbd-155">缩放–设置批注视图的缩放级别</span><span class="sxs-lookup"><span data-stu-id="c1fbd-155">Zoom – set zoom level for annotate view</span></span>

  - <span data-ttu-id="c1fbd-156">旋转–用户可以顺时针旋转文档</span><span class="sxs-lookup"><span data-stu-id="c1fbd-156">Rotate – user can rotate document clockwise</span></span>

  - <span data-ttu-id="c1fbd-157">搜索–用户可以在文档中进行搜索, 并导航到文档中的不同点击量</span><span class="sxs-lookup"><span data-stu-id="c1fbd-157">Search – user can search within a document and navigate to the various hits within the document</span></span>
    
    ![<span data-ttu-id="c1fbd-158">批注视图</span><span class="sxs-lookup"><span data-stu-id="c1fbd-158">Annotate view</span></span>
    ](../media/Reviewimage1.png)

<span data-ttu-id="c1fbd-159">请注意, 这些批注位于作为证据收集的数据上, 而不是在实际系统中的原始位置。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-159">Note that these annotations are on data collected as evidence, not at its original location in live system.</span></span> 

## <a name="more-information"></a><span data-ttu-id="c1fbd-160">更多信息</span><span class="sxs-lookup"><span data-stu-id="c1fbd-160">More information</span></span>

<span data-ttu-id="c1fbd-161">下表列出了对数据调查 (预览) 中的证据的限制。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-161">The following table lists the limits for evidence in Data Investigations (Preview).</span></span>  <span data-ttu-id="c1fbd-162">任何超过单个文件最大的项目将显示为处理错误。</span><span class="sxs-lookup"><span data-stu-id="c1fbd-162">Any items that exceed the single file maximums will show up as processing errors.</span></span>
    
  |<span data-ttu-id="c1fbd-163">**限制说明**</span><span class="sxs-lookup"><span data-stu-id="c1fbd-163">**Description of limit**</span></span>|<span data-ttu-id="c1fbd-164">**限制**</span><span class="sxs-lookup"><span data-stu-id="c1fbd-164">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="c1fbd-165">证据集合的最大数量</span><span class="sxs-lookup"><span data-stu-id="c1fbd-165">Maximum number of evidence collections</span></span>  <br/> |<span data-ttu-id="c1fbd-166">50</span><span class="sxs-lookup"><span data-stu-id="c1fbd-166">50</span></span>  <br/> |
  |<span data-ttu-id="c1fbd-167">可以引入为事例的文档总数 (针对调查中的所有证据集合)</span><span class="sxs-lookup"><span data-stu-id="c1fbd-167">Total number of documents that can be ingested into a case (for all evidence collections in the investigation)</span></span>  <br/> |<span data-ttu-id="c1fbd-168">1 百万</span><span class="sxs-lookup"><span data-stu-id="c1fbd-168">1 million</span></span>  <br/> |
  |<span data-ttu-id="c1fbd-169">每次加载的总文件大小</span><span class="sxs-lookup"><span data-stu-id="c1fbd-169">Total file size per load</span></span>  <br/> |<span data-ttu-id="c1fbd-170">100 GB</span><span class="sxs-lookup"><span data-stu-id="c1fbd-170">100 GB</span></span>  <br/> |
  |<span data-ttu-id="c1fbd-171">单个文件的最大大小</span><span class="sxs-lookup"><span data-stu-id="c1fbd-171">Maximum size of single file</span></span>   <br/> |<span data-ttu-id="c1fbd-172">100 MB</span><span class="sxs-lookup"><span data-stu-id="c1fbd-172">100 MB</span></span>  <br/> |
  |<span data-ttu-id="c1fbd-173">从单个文件提取的最大字符数</span><span class="sxs-lookup"><span data-stu-id="c1fbd-173">Maximum number of characters extracted from a single file</span></span>  <br/> |<span data-ttu-id="c1fbd-174">一千万</span><span class="sxs-lookup"><span data-stu-id="c1fbd-174">10 million</span></span>  <br/> |
  |<span data-ttu-id="c1fbd-175">文档中嵌入项目的深度</span><span class="sxs-lookup"><span data-stu-id="c1fbd-175">Depth of embedded items in a document</span></span>  <br/> |<span data-ttu-id="c1fbd-176">word</span><span class="sxs-lookup"><span data-stu-id="c1fbd-176">25</span></span>  <br/> |
  