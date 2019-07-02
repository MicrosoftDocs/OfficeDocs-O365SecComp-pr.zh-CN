---
title: 从审阅集中导出文档
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
ms.openlocfilehash: 7c1daccab799b3967c6b8c1d577060d062c05a70
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703785"
---
# <a name="export-documents-from-a-review-set"></a><span data-ttu-id="fddbb-102">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="fddbb-102">Export documents from a review set</span></span>

<span data-ttu-id="fddbb-103">您可以通过以下方法之一从审阅集导出演示文稿或外部审阅的内容:</span><span class="sxs-lookup"><span data-stu-id="fddbb-103">You can export content for presentation or external review from a review set by one of the following methods:</span></span>

- [<span data-ttu-id="fddbb-104">下载文档</span><span class="sxs-lookup"><span data-stu-id="fddbb-104">Download documents</span></span>](#download-documents-from-a-review-set)
 
- [<span data-ttu-id="fddbb-105">导出文档</span><span class="sxs-lookup"><span data-stu-id="fddbb-105">Export documents</span></span>](#export-documents-from-a-review-set)

## <a name="download-documents-from-a-review-set"></a><span data-ttu-id="fddbb-106">从审阅集中下载文档</span><span class="sxs-lookup"><span data-stu-id="fddbb-106">Download documents from a review set</span></span>

<span data-ttu-id="fddbb-107">下载提供了一种从以本机格式的审阅集下载内容的简单方法。</span><span class="sxs-lookup"><span data-stu-id="fddbb-107">Download offers a simple way to download content from a review set in Native format.</span></span> <span data-ttu-id="fddbb-108">它利用浏览器的数据传输功能, 以便在下载准备就绪后会出现浏览器提示。</span><span class="sxs-lookup"><span data-stu-id="fddbb-108">It leverages the browser’s data transfer features so a browser prompt will appear once a download is ready.</span></span> <span data-ttu-id="fddbb-109">使用此方法下载的文件将压缩到一个容器文件中, 并将成为项目级文件。</span><span class="sxs-lookup"><span data-stu-id="fddbb-109">Files downloaded using this method will be zipped into a container file and will be item level files.</span></span> <span data-ttu-id="fddbb-110">这意味着, 如果选择了附件, 您将自动收到包含附件的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fddbb-110">This means that if you select an attachment, you will automatically receive the email with the attachment included.</span></span> <span data-ttu-id="fddbb-111">同样, 如果您选择嵌入在 word 文档中的 excel 电子表格, 您将收到嵌入 excel 电子表格的 word 文档。</span><span class="sxs-lookup"><span data-stu-id="fddbb-111">Similarly, if you select an excel spreadsheet that was embedded in a word document, you will receive the word document with the excel spreadsheet embedded.</span></span> <span data-ttu-id="fddbb-112">已下载项目将保留上次修改日期, 可将其视为文件属性。</span><span class="sxs-lookup"><span data-stu-id="fddbb-112">Downloaded items will preserve the last modified date which can be viewed as a file property.</span></span>

<span data-ttu-id="fddbb-113">若要从审阅集中下载内容, 请先选择要下载的文件, 然后选择 "操作" 菜单下的 "下载"。</span><span class="sxs-lookup"><span data-stu-id="fddbb-113">To download content from a review set, start by selecting the files you want to download then select “Download” under the Actions menu.</span></span>

![自动生成的计算机说明的屏幕截图](../media/eDiscoDownload.png)

## <a name="export-documents-from-a-review-set"></a><span data-ttu-id="fddbb-115">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="fddbb-115">Export documents from a review set</span></span>

<span data-ttu-id="fddbb-116">导出允许用户自定义下载包中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="fddbb-116">Export allows users to customize the content that is included in the download package.</span></span> <span data-ttu-id="fddbb-117">它提供具有以下设置的配置页:</span><span class="sxs-lookup"><span data-stu-id="fddbb-117">It provides a configuration page with the following settings:</span></span>

### <a name="metadata-file"></a><span data-ttu-id="fddbb-118">元数据文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-118">Metadata file</span></span>

<span data-ttu-id="fddbb-119">可以将其视为包含与导出的文件相关联的元数据的 "加载文件"。</span><span class="sxs-lookup"><span data-stu-id="fddbb-119">This can be considered your “load file” that contains metadata associated with the files you exported.</span></span> <span data-ttu-id="fddbb-120">有关元数据文件中可用字段的列表, 请参阅\[链接\]。</span><span class="sxs-lookup"><span data-stu-id="fddbb-120">For a list of fields available in the metadata file, see \[link\].</span></span> <span data-ttu-id="fddbb-121">此文件通常可由3个<sup>rd</sup>方引入的后续工具进行。</span><span class="sxs-lookup"><span data-stu-id="fddbb-121">This file can typically be ingested by 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="tag-data"></a><span data-ttu-id="fddbb-122">标记数据</span><span class="sxs-lookup"><span data-stu-id="fddbb-122">Tag data</span></span>

<span data-ttu-id="fddbb-123">此内容将作为字段添加到元数据文件中。</span><span class="sxs-lookup"><span data-stu-id="fddbb-123">This content would be added as fields in the metadata file.</span></span> <span data-ttu-id="fddbb-124">它包含在审阅集中应用的所有标记信息。</span><span class="sxs-lookup"><span data-stu-id="fddbb-124">It contains all of the tag information applied in review sets.</span></span>

### <a name="text-files"></a><span data-ttu-id="fddbb-125">文本文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-125">Text files</span></span>

<span data-ttu-id="fddbb-126">可以为从评审集导出的每个文件生成文本文件。</span><span class="sxs-lookup"><span data-stu-id="fddbb-126">Text files can be generated for each file exported from a review set.</span></span> <span data-ttu-id="fddbb-127">通常, 服务合作伙伴会将这些文件作为 ingesting 数据的一部分提供给3个<sup>rd</sup>方参与方工具。</span><span class="sxs-lookup"><span data-stu-id="fddbb-127">Often times these files are required by service partners as part of ingesting data into 3<sup>rd</sup> party tools downstream.</span></span>

### <a name="redacted-files"></a><span data-ttu-id="fddbb-128">编辑文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-128">Redacted files</span></span>

<span data-ttu-id="fddbb-129">如果在审阅过程中生成编辑 Pdf, 则这些文件在导出过程中可用。</span><span class="sxs-lookup"><span data-stu-id="fddbb-129">If redacted PDFs are generated during review, these files are available during export.</span></span> <span data-ttu-id="fddbb-130">用户可以决定是仅导出本机文件, 还是将具有密文的 natives 替换为 Pdf 中的刻录文件。</span><span class="sxs-lookup"><span data-stu-id="fddbb-130">Users can decide whether to export native files only or to replace natives that have redactions with the burned in PDFs.</span></span>

### <a name="export-location"></a><span data-ttu-id="fddbb-131">导出位置</span><span class="sxs-lookup"><span data-stu-id="fddbb-131">Export Location</span></span>

<span data-ttu-id="fddbb-132">导出的内容将传递给 Microsoft 提供的 Azure blob, 如果导出时提供了详细信息, 则可以使用客户的 blob。</span><span class="sxs-lookup"><span data-stu-id="fddbb-132">Exported content is delivered to either a Microsoft provided Azure blob or a customer’s blob can be used if the details are provided at export.</span></span>

### <a name="export-structure"></a><span data-ttu-id="fddbb-133">导出结构</span><span class="sxs-lookup"><span data-stu-id="fddbb-133">Export Structure</span></span>

<span data-ttu-id="fddbb-134">从审阅集导出内容时, 将按以下结构组织内容。</span><span class="sxs-lookup"><span data-stu-id="fddbb-134">When content is exported from a review set, the content is organized in the following structure.</span></span>

  - <span data-ttu-id="fddbb-135">根文件夹–下载 ID</span><span class="sxs-lookup"><span data-stu-id="fddbb-135">Root folder – Download ID</span></span>
    
      - <span data-ttu-id="fddbb-136">Export\_load\_file .csv = metadata 文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-136">Export\_load\_file.csv = metadata file</span></span>
    
      - <span data-ttu-id="fddbb-137">摘要 .txt = 带有导出统计信息的摘要文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-137">Summary.txt = a summary file with export statistics</span></span>
    
      - <span data-ttu-id="fddbb-138">输入\_或本机\_文件 = 包含所有本机文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-138">Input\_or native\_files = contains all native files</span></span>
    
      - <span data-ttu-id="fddbb-139">错误\_文件 = 包含导出中包含的任何错误文件</span><span class="sxs-lookup"><span data-stu-id="fddbb-139">Error\_files = contains any error files included in the export</span></span>
        
          - <span data-ttu-id="fddbb-140">ExtractionError –包含未从父文件正确提取的任何可用文件元数据的 csv</span><span class="sxs-lookup"><span data-stu-id="fddbb-140">ExtractionError – a csv that contains any available metadata of files that were not properly extracted from parent files</span></span>
        
          - <span data-ttu-id="fddbb-141">ProcessingError –包含处理错误的内容。</span><span class="sxs-lookup"><span data-stu-id="fddbb-141">ProcessingError – content with processing errors.</span></span> <span data-ttu-id="fddbb-142">此内容是项目级别意味着, 如果附件遇到处理错误, 则包含附件的电子邮件将包含在此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fddbb-142">This content is item level meaning if an attachment experienced a processing error, the email that contains the attachment will be included in this folder.</span></span>
    
      - <span data-ttu-id="fddbb-143">提取\_的\_文本文件 = 包含处理过程中生成的所有提取的文本文件。</span><span class="sxs-lookup"><span data-stu-id="fddbb-143">Extracted\_text\_files = contains all of the extracted text files generated at processing.</span></span>