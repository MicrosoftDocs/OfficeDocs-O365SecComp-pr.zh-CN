---
title: 在 Office 365 高级电子数据展示中运行流程模块
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: '了解使用 office 365 高级电子数据展示为分析准备 office 365 数据的大小写文件的指南。  '
ms.openlocfilehash: 19d50bda21f752ec7c22fe52b6fa7272592de128
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261030"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="2da65-103">在 Office 365 高级电子数据展示中运行流程模块</span><span class="sxs-lookup"><span data-stu-id="2da65-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="2da65-104">在**准备** \> **过程**中, 将事例文件加载到高级电子数据展示中。</span><span class="sxs-lookup"><span data-stu-id="2da65-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2da65-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2da65-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="2da65-107">指南: 为高级电子数据展示准备数据</span><span class="sxs-lookup"><span data-stu-id="2da65-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="2da65-108">**Quality**: 明确标识与事例相关的事例文件填充。</span><span class="sxs-lookup"><span data-stu-id="2da65-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="2da65-109">**加载**: 将文件加载到高级电子数据展示可访问的位置。</span><span class="sxs-lookup"><span data-stu-id="2da65-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="2da65-110">**文件 ID**: 高级电子数据展示中的唯一文件标识符。</span><span class="sxs-lookup"><span data-stu-id="2da65-110">**File ID**: A unique file identifier in Advanced eDiscovery.</span></span> <span data-ttu-id="2da65-111">如果未导入任何文件标识符, 高级电子数据展示将自动生成 ID。</span><span class="sxs-lookup"><span data-stu-id="2da65-111">If no file identifier is imported, Advanced eDiscovery automatically generates the ID.</span></span> <span data-ttu-id="2da65-112">如果在后续进程加载中映射 ID, 并映射与初始进程加载不同的路径, 则高级电子数据展示将替换路径 (而不是添加新的文件条目)。</span><span class="sxs-lookup"><span data-stu-id="2da65-112">If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry).</span></span> <span data-ttu-id="2da65-113">该 ID 可用作导出过程中的引用。</span><span class="sxs-lookup"><span data-stu-id="2da65-113">The ID can be used as a reference in the Export process.</span></span> <span data-ttu-id="2da65-114">ID 值不应为 "-1"。</span><span class="sxs-lookup"><span data-stu-id="2da65-114">The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="2da65-115">**MD5**: 此签名用于区分文件 (两个文件不被视为完全重复项, 除非它们具有相同的 MD5)。</span><span class="sxs-lookup"><span data-stu-id="2da65-115">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5).</span></span> <span data-ttu-id="2da65-116">默认情况下, 高级电子数据展示计算文件的 MD5。</span><span class="sxs-lookup"><span data-stu-id="2da65-116">By default, Advanced eDiscovery calculates the MD5 of files.</span></span> <span data-ttu-id="2da65-117">当加载的文件是文本文件时, 建议加载并映射原始 MD5 值, 而不是在高级电子数据展示中对其进行计算。</span><span class="sxs-lookup"><span data-stu-id="2da65-117">When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="2da65-118">**文件类型和名称**:</span><span class="sxs-lookup"><span data-stu-id="2da65-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="2da65-119">高级电子数据展示可以处理各种格式的文件, 并将加载的本机文件提取为标准\*格式, 例如。TXT、HTML 或。XML.</span><span class="sxs-lookup"><span data-stu-id="2da65-119">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML.</span></span> <span data-ttu-id="2da65-120">文本文件的处理速度比本机文件更快。</span><span class="sxs-lookup"><span data-stu-id="2da65-120">Processing of text files is faster than native files.</span></span> <span data-ttu-id="2da65-121">提取的文本文件存储在事例文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2da65-121">Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="2da65-122">不加载无法提取的文件, 如系统文件或图形图像。</span><span class="sxs-lookup"><span data-stu-id="2da65-122">Do not load files that cannot be extracted, such as system files or graphic images.</span></span> <span data-ttu-id="2da65-123">这些文件可能会延迟处理。</span><span class="sxs-lookup"><span data-stu-id="2da65-123">These files may delay processing.</span></span>
    
  - <span data-ttu-id="2da65-124">验证文件名是否具有明显名称和路径是否正确。</span><span class="sxs-lookup"><span data-stu-id="2da65-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="2da65-125">**文件路径**: 高级电子数据展示可以加载最长为400个字符的路径长度的文件。</span><span class="sxs-lookup"><span data-stu-id="2da65-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="2da65-126">**文本提取**: 从本机文件中提取文本时, 除了常规文本之外, 还会提取以下内容: 隐藏文本 (excel 和 .doc)、隐藏列 (Excel)、跟踪更改 (.doc)、演讲者备注 (.ppt)、嵌入对象 (例如,.ppt 中的 Excel 对象)。</span><span class="sxs-lookup"><span data-stu-id="2da65-126">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt).</span></span> <span data-ttu-id="2da65-127">可以在文本编辑器中查看这些内容。</span><span class="sxs-lookup"><span data-stu-id="2da65-127">These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="2da65-128">**Ignore Text**: 此可选功能是在运行进程之后和分析前定义的。</span><span class="sxs-lookup"><span data-stu-id="2da65-128">**Ignore Text**: This optional feature is defined after Process is run and before Analyze.</span></span> <span data-ttu-id="2da65-129">应谨慎使用 "忽略" 文本, 因为它的使用可能会降低文件分析的性能。</span><span class="sxs-lookup"><span data-stu-id="2da65-129">Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="2da65-130">**多语言文本**: 高级电子数据展示当前不处理标记、保管人和问题的多语言名称。</span><span class="sxs-lookup"><span data-stu-id="2da65-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="2da65-131">**元数据**: 确定是否要在事例数据库中保存要保存的元数据, 以供将来参考, 如日期范围、文件大小、文件类型、管理员和主题。</span><span class="sxs-lookup"><span data-stu-id="2da65-131">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject.</span></span> <span data-ttu-id="2da65-132">在已加载文件而不重新运行清单或添加重新处理开销之后, 可以加载元数据。</span><span class="sxs-lookup"><span data-stu-id="2da65-132">Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="2da65-133">如果文件最初是按路径加载, 则在随后导入元数据时映射 "路径" 列。</span><span class="sxs-lookup"><span data-stu-id="2da65-133">If the files were originally loaded by path, map the path column when later importing metadata.</span></span> <span data-ttu-id="2da65-134">可以按 ID 引用文件并映射不同的路径。</span><span class="sxs-lookup"><span data-stu-id="2da65-134">It is possible to refer to the file by ID and to map a different path.</span></span> <span data-ttu-id="2da65-135">当文件路径发生更改时, 这是一种非常有用的方案。</span><span class="sxs-lookup"><span data-stu-id="2da65-135">This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="2da65-136">如果文件最初是按文件 ID 加载, 则在加载元数据时映射 ID 列。</span><span class="sxs-lookup"><span data-stu-id="2da65-136">If the files were originally loaded by File ID, map the ID column when loading metadata.</span></span> <span data-ttu-id="2da65-137">通过路径 (而不是 ID) 引用文件将导致使用不同的 id 重新加载文件。</span><span class="sxs-lookup"><span data-stu-id="2da65-137">Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID.</span></span> <span data-ttu-id="2da65-138">高级电子数据展示将创建文件副本, 而不是加载现有文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="2da65-138">Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="2da65-139">**系列**: 无法加载没有其父 (系列头部) 的家庭。</span><span class="sxs-lookup"><span data-stu-id="2da65-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="2da65-140">**文件大小**: 加载到高级电子数据展示的文件大小没有限制。</span><span class="sxs-lookup"><span data-stu-id="2da65-140">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery.</span></span> <span data-ttu-id="2da65-141">对于分析 (分析、相关性等), 限制为5242880个提取文本的字符。</span><span class="sxs-lookup"><span data-stu-id="2da65-141">For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text.</span></span> <span data-ttu-id="2da65-142">将忽略较大的文件 (例如, 在相关性中, 文件不参与相关性培训过程, 也不会在批量计算后收到相关性分数)。</span><span class="sxs-lookup"><span data-stu-id="2da65-142">Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="2da65-143">**文件数量**: 对于可在单个情况下处理的文件数, 没有建议的限制。</span><span class="sxs-lookup"><span data-stu-id="2da65-143">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case.</span></span> <span data-ttu-id="2da65-144">性能取决于系统的资源。</span><span class="sxs-lookup"><span data-stu-id="2da65-144">Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="2da65-145">筛选文件</span><span class="sxs-lookup"><span data-stu-id="2da65-145">Filtering files</span></span>

<span data-ttu-id="2da65-146">用户定义的标签可与一组文件相关联, 以从进程或其他任务中排除它们。</span><span class="sxs-lookup"><span data-stu-id="2da65-146">A user-defined label can be associated with a set of files to exclude them from Process or other tasks.</span></span> <span data-ttu-id="2da65-147">每个进程会话都与一个批次 ID 相关联。</span><span class="sxs-lookup"><span data-stu-id="2da65-147">Each Process session is associated with a batch ID.</span></span> <span data-ttu-id="2da65-148">尽管批 ID 对相关专家不可见, 但可使用搜索实用程序来完成此操作, 方法是为当前批处理添加筛选器, 并使用用户定义的标签标记所有相应的文件。</span><span class="sxs-lookup"><span data-stu-id="2da65-148">Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2da65-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2da65-149">See also</span></span>

[<span data-ttu-id="2da65-150">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="2da65-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="2da65-151">运行进程模块并加载数据</span><span class="sxs-lookup"><span data-stu-id="2da65-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="2da65-152">查看流程模块结果</span><span class="sxs-lookup"><span data-stu-id="2da65-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

