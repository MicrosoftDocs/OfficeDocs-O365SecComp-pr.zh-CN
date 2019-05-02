---
title: 从审阅集中导出文档
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
ms.openlocfilehash: ea9db6d95b003b5a741ae8a235fc5f06087f87d6
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527117"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="9f161-102">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="9f161-102">Export documents from a review set</span></span>

<span data-ttu-id="9f161-103">可以通过3种不同的方法来导出评审集的内容:</span><span class="sxs-lookup"><span data-stu-id="9f161-103">Exporting content from a review set can be accomplished via 3 different methods:</span></span>

## <a name="download"></a><span data-ttu-id="9f161-104">下载</span><span class="sxs-lookup"><span data-stu-id="9f161-104">Download</span></span>

<span data-ttu-id="9f161-105">下载提供了一种从以本机格式的审阅集下载内容的简单方法。</span><span class="sxs-lookup"><span data-stu-id="9f161-105">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="9f161-106">它利用浏览器的数据传输功能, 以便在下载准备就绪后会出现浏览器提示。</span><span class="sxs-lookup"><span data-stu-id="9f161-106">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="9f161-107">使用此方法下载的文件将压缩到一个容器文件中, 并将成为项目级文件。</span><span class="sxs-lookup"><span data-stu-id="9f161-107">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="9f161-108">这意味着, 如果选择了附件, 您将自动收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9f161-108">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="9f161-109">同样, 如果您选择嵌入在 word 文档中的 excel 电子表格, 您将收到嵌入 excel 电子表格的 word 文档。</span><span class="sxs-lookup"><span data-stu-id="9f161-109">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="9f161-110">已下载项目将保留上次修改日期, 可将其视为文件属性。</span><span class="sxs-lookup"><span data-stu-id="9f161-110">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="9f161-111">若要从审阅集中下载内容, 请先选择要下载的文件, 然后选择 "操作" 菜单下的 "下载"。</span><span class="sxs-lookup"><span data-stu-id="9f161-111">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![自动生成的计算机说明的屏幕截图](../media/eDiscoDownload.png)

## <a name="export"></a><span data-ttu-id="9f161-113">导出</span><span class="sxs-lookup"><span data-stu-id="9f161-113">Export</span></span>

<span data-ttu-id="9f161-114">导出允许用户自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="9f161-114">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="9f161-115">它提供具有以下设置的配置页:</span><span class="sxs-lookup"><span data-stu-id="9f161-115">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="9f161-116">元数据文件</span><span class="sxs-lookup"><span data-stu-id="9f161-116">Metadata file</span></span>

> <span data-ttu-id="9f161-117">可以将其视为包含与导出的文件相关联的元数据的 "加载文件"。</span><span class="sxs-lookup"><span data-stu-id="9f161-117">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="9f161-118">有关元数据文件中可用字段的列表, 请参阅\[链接\]。</span><span class="sxs-lookup"><span data-stu-id="9f161-118">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="9f161-119">此文件通常可由3个<sup>rd</sup>方引入的后续工具进行。</span><span class="sxs-lookup"><span data-stu-id="9f161-119">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="9f161-120">标记数据</span><span class="sxs-lookup"><span data-stu-id="9f161-120">Tag data</span></span>

> <span data-ttu-id="9f161-121">此内容将作为字段添加到元数据文件中。</span><span class="sxs-lookup"><span data-stu-id="9f161-121">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="9f161-122">它包含在审阅集中应用的所有标记信息。</span><span class="sxs-lookup"><span data-stu-id="9f161-122">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="9f161-123">文本文件</span><span class="sxs-lookup"><span data-stu-id="9f161-123">Text files</span></span>

> <span data-ttu-id="9f161-124">可以为从评审集导出的每个文件生成文本文件。</span><span class="sxs-lookup"><span data-stu-id="9f161-124">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="9f161-125">通常, 服务合作伙伴会将这些文件作为 ingesting 数据的一部分提供给3个<sup>rd</sup>方参与方工具。</span><span class="sxs-lookup"><span data-stu-id="9f161-125">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="9f161-126">编辑文件</span><span class="sxs-lookup"><span data-stu-id="9f161-126">Redacted files</span></span>

> <span data-ttu-id="9f161-127">如果在审阅过程中生成编辑 Pdf, 则这些文件在导出过程中可用。</span><span class="sxs-lookup"><span data-stu-id="9f161-127">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="9f161-128">用户可以决定是仅导出本机文件, 还是将具有密文的 natives 替换为 Pdf 中的刻录文件。</span><span class="sxs-lookup"><span data-stu-id="9f161-128">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="9f161-129">导出位置</span><span class="sxs-lookup"><span data-stu-id="9f161-129">Export Location</span></span>

> <span data-ttu-id="9f161-130">导出的内容将传递给 Microsoft 提供的 Azure blob, 如果导出时提供了详细信息, 则可以使用客户的 blob。</span><span class="sxs-lookup"><span data-stu-id="9f161-130">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

## <a name="export-structure"></a><span data-ttu-id="9f161-131">导出结构</span><span class="sxs-lookup"><span data-stu-id="9f161-131">Export Structure</span></span>

<span data-ttu-id="9f161-132">从审阅集导出内容时, 将按以下结构组织内容。</span><span class="sxs-lookup"><span data-stu-id="9f161-132">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="9f161-133">根文件夹–下载 ID</span><span class="sxs-lookup"><span data-stu-id="9f161-133">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="9f161-134">Export\_load\_file .csv = metadata 文件</span><span class="sxs-lookup"><span data-stu-id="9f161-134">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="9f161-135">摘要 .txt = 带有导出统计信息的摘要文件</span><span class="sxs-lookup"><span data-stu-id="9f161-135">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="9f161-136">输入\_或本机\_文件 = 包含所有本机文件</span><span class="sxs-lookup"><span data-stu-id="9f161-136">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="9f161-137">错误\_文件 = 包含导出中包含的任何错误文件</span><span class="sxs-lookup"><span data-stu-id="9f161-137">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="9f161-138">ExtractionError –包含未从父文件正确提取的任何可用文件元数据的 csv</span><span class="sxs-lookup"><span data-stu-id="9f161-138">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="9f161-139">ProcessingError –包含处理错误的内容。</span><span class="sxs-lookup"><span data-stu-id="9f161-139">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="9f161-140">此内容是项目级别意味着, 如果附件遇到处理错误, 则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9f161-140">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="9f161-141">提取\_的\_文本文件 = 包含处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="9f161-141">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>

## <a name="review-set"></a><span data-ttu-id="9f161-142">查看设置</span><span class="sxs-lookup"><span data-stu-id="9f161-142">review set</span></span>

<span data-ttu-id="9f161-143">可将内容添加到另一个评审集。</span><span class="sxs-lookup"><span data-stu-id="9f161-143">Content can be added to another review set.</span></span>