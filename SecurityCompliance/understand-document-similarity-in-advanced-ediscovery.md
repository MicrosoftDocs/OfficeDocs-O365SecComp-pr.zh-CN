---
title: 了解 Office 365 高级电子数据展示中的文档相似性
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: '查看 "文档相似性" 值 (两个文件的最小 resemblance 级别, 将其视为邻近的重复项) 在 Office 365 高级电子数据展示中起作用。 '
ms.openlocfilehash: eb8f07ceedb10bd0152693dd1e82a28797d86a5a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220422"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="89cee-103">了解 Office 365 高级电子数据展示中的文档相似性</span><span class="sxs-lookup"><span data-stu-id="89cee-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="89cee-p101">若要使用高级电子数据展示，组织必须订阅随附高级合规性加载项的 Office 365 E3，或订阅 E5。如果没有此计划，但又要试用高级电子数据展示，可以[注册 Office 365 企业版 E5 试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="89cee-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="89cee-106">在高级电子数据展示中, "文档相似性" 是两个文档被视为临近重复项所需的最低级别的 resemblance。</span><span class="sxs-lookup"><span data-stu-id="89cee-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="89cee-p102">对于大多数业务应用程序, 建议使用相似性值 60%-75%。对于质量非常差的光学字符识别 (OCR) 材料, 可以应用较低的相似性值。</span><span class="sxs-lookup"><span data-stu-id="89cee-p102">For most business applications, it is recommended to use a Similarity value of 60%-75%. For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="89cee-109">在设置和运行给定的事例后, 不能更改相似性值。</span><span class="sxs-lookup"><span data-stu-id="89cee-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="89cee-p103">在接近重复 (ND) 集内, 可能存在低于相似性阈值的 resemblance 级别的文档。对于要加入 nd 集的文档, 在 nd 集中必须至少有一个文档的 resemblance 级别超过相似性。</span><span class="sxs-lookup"><span data-stu-id="89cee-p103">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold. For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="89cee-112">例如, 假设相似性设置为 80%, 文档 F1 类似于 85% 级别的文档 f2, 文档 f2 类似于文档 F3 的级别为 90%。</span><span class="sxs-lookup"><span data-stu-id="89cee-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="89cee-p104">但是, 文档 F1 在仅为 70% 的级别 (低于阈值) 可能会类似于文档 F3。尽管如此, 在此示例中, 文档 F1、F2 和 F3 都显示在一对等设置中。同样, 使用相似性值 80%, 我们可能创建了两个集合, EquiSet-1 和 EquiSet。EquiSet-1 包含文档 E1 和 E2。Equiset-2 包含文档 F1、F2 和 F3。</span><span class="sxs-lookup"><span data-stu-id="89cee-p104">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold. Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set. Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2. EquiSet-1 contains documents E1 and E2. Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="89cee-118">resemblance 的级别如下所示:</span><span class="sxs-lookup"><span data-stu-id="89cee-118">The levels of resemblance are illustrated as follows:</span></span>
  
![文档相似性](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="89cee-p105">假定现在已插入另一个文档 X1。X1 和 E3 之间的 resemblance 为 87%。同样, X1 和 F1 之间的 resemblance 为 92%。因此, EquiSet-1、EquiSet-2 和 X1 现已组合到一个 ND 集中。</span><span class="sxs-lookup"><span data-stu-id="89cee-p105">Assume that another document, X1, is now inserted. The resemblance between X1 and E3 is 87%. Similarly, the resemblance between X1 and F1 is 92%. As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![文档相似性](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="89cee-125">如果将任意两个文档分配给一个 nd 集, 它们将保持在相同的 nd 集中, 即使其他文档添加到了该集或者合并了这些集也是如此。</span><span class="sxs-lookup"><span data-stu-id="89cee-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="89cee-126">合并设置后, 在将新文档添加到集合中时, 数据透视文档可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="89cee-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="89cee-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89cee-127">See also</span></span>

[<span data-ttu-id="89cee-128">Office 365 高级电子数据展示</span><span class="sxs-lookup"><span data-stu-id="89cee-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="89cee-129">设置分析选项</span><span class="sxs-lookup"><span data-stu-id="89cee-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89cee-130">设置忽略文本</span><span class="sxs-lookup"><span data-stu-id="89cee-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89cee-131">设置分析高级设置</span><span class="sxs-lookup"><span data-stu-id="89cee-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="89cee-132">查看分析结果</span><span class="sxs-lookup"><span data-stu-id="89cee-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

