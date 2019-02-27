---
title: 近似重复检测
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
ms.openlocfilehash: 941809193a3342d8c7b9de991370848aee4af070
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30294935"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="2248a-102">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="2248a-102">Near duplicate detection</span></span>

<span data-ttu-id="2248a-p101">考虑要审阅的一组文档, 其中子集基于同一个模板, 大多数采用相同的样本语言, 但此处和此处有一些差异。如果某个审阅者可以识别此子集, 请仔细查看其中一项, 并查看 rest 的不同之处, 他们不会错过任何独特的信息, 而只需要花费一小时间来阅读所有文档封面。临近的重复检测将多个类似的文档组合在一起, 以帮助您更有效地查看您的审阅过程。</span><span class="sxs-lookup"><span data-stu-id="2248a-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="2248a-106">它是如何运行的？</span><span class="sxs-lookup"><span data-stu-id="2248a-106">How does it work?</span></span>

<span data-ttu-id="2248a-p102">在接近重复检测运行时, 系统会使用文本分析每个文档。然后, 它将每个文档进行比较, 以确定它们的相似性是否大于设定的阈值。如果是, 则将文档组合在一起。对所有文档进行了比较和分组后, 每个组中的一个文档将标记为 "pivot";在审阅文档中, 可以先查看数据透视, 并查看相同临近重复集的其他文档, 重点介绍正在审阅的数据透视和文档之间的差异。</span><span class="sxs-lookup"><span data-stu-id="2248a-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>