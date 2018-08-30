---
title: 在 Office 365 高级电子数据展示中运行流程模块
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: dbc1e251-0596-443b-ac9b-f398ba955b73
description: '了解有关准备的案例文件的 Office 365 数据分析与 Office 365 高级电子数据展示的指导标准。  '
ms.openlocfilehash: 52b1dce9fb778c6628d90c39135f0c93f08134d7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525955"
---
# <a name="run-the-process-module-in-office-365-advanced-ediscovery"></a><span data-ttu-id="6542b-103">在 Office 365 高级电子数据展示中运行流程模块</span><span class="sxs-lookup"><span data-stu-id="6542b-103">Run the Process module in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="6542b-104">在**准备**期间案例文件加载到高级电子数据展示\>**过程**。</span><span class="sxs-lookup"><span data-stu-id="6542b-104">Case files are loaded into the Advanced eDiscovery during **Prepare** \> **Process**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6542b-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="6542b-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="guidelines-preparing-data-for-advanced-ediscovery"></a><span data-ttu-id="6542b-107">准则： 准备高级电子数据展示数据</span><span class="sxs-lookup"><span data-stu-id="6542b-107">Guidelines: Preparing data for Advanced eDiscovery</span></span>

- <span data-ttu-id="6542b-108">**质量**： 清楚地标识与案例相关的案例文件填充。</span><span class="sxs-lookup"><span data-stu-id="6542b-108">**Quality**: Clearly identify the case file population pertinent to the case.</span></span>
    
- <span data-ttu-id="6542b-109">**加载**： 将文件加载到高级电子数据展示可以访问的位置。</span><span class="sxs-lookup"><span data-stu-id="6542b-109">**Loads**: Load the files into a location that is accessible to Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="6542b-p102">**文件 ID**： 高级电子数据展示中的唯一的文件标识符。如果没有文件标识符导入，高级电子数据展示自动生成 id。如果您映射后续处理负载中的 ID，并将初始过程负载以外的其他路径，高级电子数据展示将取代路径 （而不添加一个新的文件项）。ID 可用作导出过程中的引用。ID 值不应为"-1"。</span><span class="sxs-lookup"><span data-stu-id="6542b-p102">**File ID**: A unique file identifier in Advanced eDiscovery. If no file identifier is imported, Advanced eDiscovery automatically generates the ID. If you map the ID in a subsequent Process load, and map a different path than in the initial Process load, Advanced eDiscovery will replace the path (rather than add a new file entry). The ID can be used as a reference in the Export process. The ID value should not be "-1".</span></span>
    
- <span data-ttu-id="6542b-p103">**MD5**： 此签名用于区分 （两个文件均不被视为完全重复除非他们拥有相同 MD5） 的文件。默认情况下，高级电子数据展示计算 MD5 的文件。当加载的文件文本文件时，建议加载并映射而不是计算高级电子数据展示中的原始 MD5 值。</span><span class="sxs-lookup"><span data-stu-id="6542b-p103">**MD5**: This signature is used to differentiate between files (two files are not considered exact duplicates unless they have the same MD5). By default, Advanced eDiscovery calculates the MD5 of files. When the loaded files are text files, it is recommended to load and map the original MD5 value instead of calculating it in Advanced eDiscovery.</span></span>
    
- <span data-ttu-id="6542b-118">**文件类型和名称**：</span><span class="sxs-lookup"><span data-stu-id="6542b-118">**File type and name**:</span></span>
    
  - <span data-ttu-id="6542b-p104">高级电子数据展示可以处理的各种格式的文件，并将加载本机文件解压缩到标准格式，如\*。TXT、 HTML，或。比本机文件 XML。 处理的文本文件。提取的文本文件存储的大小写的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6542b-p104">Advanced eDiscovery can process files of various formats and extract loaded native files into a standard format, such as \*.TXT, HTML, or .XML. Processing of text files is faster than native files. Extracted text files are stored in the case folder.</span></span>
    
  - <span data-ttu-id="6542b-p105">不加载无法提取，例如系统文件或图形的图像的文件。这些文件可能会延迟处理。</span><span class="sxs-lookup"><span data-stu-id="6542b-p105">Do not load files that cannot be extracted, such as system files or graphic images. These files may delay processing.</span></span>
    
  - <span data-ttu-id="6542b-124">验证显著名文件名和路径正确。</span><span class="sxs-lookup"><span data-stu-id="6542b-124">Verify that file names are significantly named and paths are correct.</span></span>
    
- <span data-ttu-id="6542b-125">**文件路径**： 高级电子数据展示可以加载文件路径长度最多 400 个字符。</span><span class="sxs-lookup"><span data-stu-id="6542b-125">**File path**: Advanced eDiscovery can load files with path lengths up to 400 characters.</span></span>
    
- <span data-ttu-id="6542b-p106">**文本提取**： 时从本机文件，除了普通文本提取文本还提取以下： 隐藏的文本 （Excel 和.doc），隐藏列 (Excel) （例如，跟踪更改 (.doc)，扬声器 notes (.ppt) 嵌入对象Excel 中的对象.ppt）。可以在文本编辑器中查看这些。</span><span class="sxs-lookup"><span data-stu-id="6542b-p106">**Text extraction**: When extracting text from native files, in addition to normal text, the following are also extracted: hidden text (Excel and .doc), hidden columns (Excel), track changes (.doc), speaker notes (.ppt), embedded objects (for example, Excel objects in a .ppt). These can be viewed in the Text editor.</span></span>
    
- <span data-ttu-id="6542b-p107">**忽略文本**： 运行过程之后，并在分析定义此可选功能。忽略应谨慎使用文本，因为其使用可能会降低文件分析的性能。</span><span class="sxs-lookup"><span data-stu-id="6542b-p107">**Ignore Text**: This optional feature is defined after Process is run and before Analyze. Ignore text should be used with caution because its use may reduce the performance of file analysis.</span></span>
    
- <span data-ttu-id="6542b-130">**多语言文本**： 高级电子数据展示当前未处理的标记、 custodian 和问题的多语言名称。</span><span class="sxs-lookup"><span data-stu-id="6542b-130">**Multilingual text**: Advanced eDiscovery does not currently handle multilingual names for tags, custodian, and issues.</span></span>
    
- <span data-ttu-id="6542b-p108">**元数据**： 确定是否要保存以供将来参考，日期范围，文件大小、 文件类型，如案例数据库中 custodian，并使用者的元数据。文件已加载无需重新运行库存或添加开销重新处理后，可以加载元数据。</span><span class="sxs-lookup"><span data-stu-id="6542b-p108">**Metadata**: Determine if there is metadata that you want to save in the case database for future reference, such as date range, file size, file type, custodian, and subject. Metadata can be loaded after files were already loaded without rerunning the inventory or adding reprocessing overhead.</span></span> 
    
  - <span data-ttu-id="6542b-p109">如果路径最初已加载的文件，将时更高版本导入元数据映射路径列。有可能，请参阅按 ID 文件并将映射其他路径。文件路径更改时，这是一个非常有用的方案。</span><span class="sxs-lookup"><span data-stu-id="6542b-p109">If the files were originally loaded by path, map the path column when later importing metadata. It is possible to refer to the file by ID and to map a different path. This is a useful scenario when the file paths change.</span></span>
    
  - <span data-ttu-id="6542b-p110">如果按文件 ID 最初已加载的文件，将在加载元数据时映射 ID 列。引用路径 （而不是 ID) 的文件将导致文件重新加载与一个不同的 id。高级电子数据展示创建文件的副本而不显示该加载元数据的现有文件。</span><span class="sxs-lookup"><span data-stu-id="6542b-p110">If the files were originally loaded by File ID, map the ID column when loading metadata. Referring to the file by path (instead of ID) will cause files to be re-loaded with a different ID. Advanced eDiscovery creates copies of the files rather that loading metadata of the existing files.</span></span>
    
- <span data-ttu-id="6542b-139">**系列**： 不能加载不 （标头的系列） 其父级的系列。</span><span class="sxs-lookup"><span data-stu-id="6542b-139">**Families**: It is not possible to load a family without its parent (head of family).</span></span> 
    
- <span data-ttu-id="6542b-p111">**文件大小**： 文件加载到高级电子数据展示的大小没有限制。分析 （分析、 相关性等），限制为 5,242,880 提取的文本的字符。较大的文件将被忽略 （例如，在相关性，文件不参与相关性培训进程和批次计算后将不会接收的相关性分数）。</span><span class="sxs-lookup"><span data-stu-id="6542b-p111">**File size**: There is no limitation on the size of files loaded to Advanced eDiscovery. For analysis (Analyze, Relevance, etc.), the limit is 5,242,880 characters of extracted text. Larger files are ignored (for example, in Relevance, files do not participate in the Relevance training process and do not receive a Relevance score after batch calculation).</span></span>
    
- <span data-ttu-id="6542b-p112">**文件数量**： 没有任何建议的限制，可以在单个案例中处理的文件数。性能取决于您的系统的资源。</span><span class="sxs-lookup"><span data-stu-id="6542b-p112">**File quantity**: There is no recommended limit on the number of files that can be handled in a single case. Performance depends on the resources of your system.</span></span> 
    
## <a name="filtering-files"></a><span data-ttu-id="6542b-145">筛选文件</span><span class="sxs-lookup"><span data-stu-id="6542b-145">Filtering files</span></span>

<span data-ttu-id="6542b-p113">用户定义的标签可与一组文件排除过程或其他任务关联。每个进程会话相关联批处理 id。尽管批处理 ID 不是对相关性专家可见的这可以使用搜索实用程序，通过添加当前批次的筛选器和标记所有相应文件的用户定义的标签。</span><span class="sxs-lookup"><span data-stu-id="6542b-p113">A user-defined label can be associated with a set of files to exclude them from Process or other tasks. Each Process session is associated with a batch ID. Although the batch ID is not visible to the expert in Relevance, this can be done using a search utility, by adding a filter for the current batch and tagging all appropriate files with a user-defined label.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6542b-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6542b-149">See also</span></span>

[<span data-ttu-id="6542b-150">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="6542b-150">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="6542b-151">运行进程模块并将数据加载</span><span class="sxs-lookup"><span data-stu-id="6542b-151">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6542b-152">查看过程模块结果</span><span class="sxs-lookup"><span data-stu-id="6542b-152">Viewing Process module results</span></span>](view-process-module-results-in-advanced-ediscovery.md)

