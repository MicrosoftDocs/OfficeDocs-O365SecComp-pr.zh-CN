---
title: 了解 Office 365 高级电子数据展示中的文档相似性
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '查看 Office 365 高级电子数据展示中的文档相似性值，最少的两个文件被视为近乎重复的类似级别工作原理。 '
ms.openlocfilehash: 39cd8c31204f0164f6b52c71fa707253cb22758a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525234"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="df545-103">了解 Office 365 高级电子数据展示中的文档相似性</span><span class="sxs-lookup"><span data-stu-id="df545-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="df545-p101">高级电子数据展示需要为您的组织使用的高级合规性加载项或 E5 订阅 Office 365 E3。如果您不具有该计划，并且想要尝试高级电子数据展示，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="df545-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="df545-106">在高级电子数据展示，文档相似性是类似的所需的两个文档都视为近乎重复项的最低级别。</span><span class="sxs-lookup"><span data-stu-id="df545-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="df545-p102">对于大多数业务应用程序，建议使用相似性值的 60%-75%。对于很差的质量光学字符识别 (OCR) 材料可以应用较低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="df545-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="df545-109">它已设置并运行给定情况后，无法更改的相似性值。</span><span class="sxs-lookup"><span data-stu-id="df545-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="df545-p103">集中 Near 副本 （和），可能有文档类似低于相似性阈值级别。加入和组中，为文档中必须有至少一个文档具有类似超出相似性级别设置和。</span><span class="sxs-lookup"><span data-stu-id="df545-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="df545-112">例如，假定相似性设置为 80%，文档 F1 类似于文档 F2 85%的级别，文档 F2 类似于文档 F3 90%的级别。</span><span class="sxs-lookup"><span data-stu-id="df545-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="df545-p104">但是，文档 F1 可能类似于文档 F3 仅 70%，低于的阈值级别。不过，此示例中，在文档 F1、 F2 和 F3 所有显示在一个和设置。同样，使用相似性值的 80%，我们可能已创建两组，EquiSet 1 和 EquiSet 2。EquiSet 1 包含文档 E1 和 E2。Equiset 2 包含文档 F1、 F2 和 F3。</span><span class="sxs-lookup"><span data-stu-id="df545-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="df545-118">级别的类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="df545-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文档相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="df545-p105">假定另一个文档，X1，则现在插入。X1 和 E3 之间类似是 87%。同样，之间 X1 和 F1 类似是 92%。因此，EquiSet-1、-2，EquiSet 和 X1 现在合并到一个和设置。</span><span class="sxs-lookup"><span data-stu-id="df545-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文档相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="df545-125">如果任何两个文档或分配给和一，它们仍保留在一起在和一组相同，即使其他文档添加到集中如果合并集。</span><span class="sxs-lookup"><span data-stu-id="df545-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="df545-126">设置将合并后，新文档添加到一组时，可以更改数据透视表文档。</span><span class="sxs-lookup"><span data-stu-id="df545-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="df545-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df545-127">See also</span></span>

[<span data-ttu-id="df545-128">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="df545-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="df545-129">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="df545-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="df545-130">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="df545-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="df545-131">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="df545-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="df545-132">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="df545-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

