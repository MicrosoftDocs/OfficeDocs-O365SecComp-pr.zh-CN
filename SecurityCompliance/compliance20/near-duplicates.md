---
title: 近似重复检测
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: a3f5945ee4ba0a1bc78ab6c8ccc9af934d392232
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607438"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="adb20-102">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="adb20-102">Near duplicate detection</span></span>

<span data-ttu-id="adb20-p101">请考虑一组文档审阅基于相同的模板和具有主要相同样本的语言，具有此处和存在一些差异子集。如果审阅者无法确定此子集、 全面，查看其中之一和查看 rest 的差异，它们将不错过任何唯一信息时，使只有一小部分时间可能需要花费以便读取封面到封面的所有文档。Near 重复检测组合在一起可帮助您让您查看过程更加高效的文本上类似文档。</span><span class="sxs-lookup"><span data-stu-id="adb20-p101">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there. If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="adb20-106">它是如何运行的？</span><span class="sxs-lookup"><span data-stu-id="adb20-106">How does it work?</span></span>

<span data-ttu-id="adb20-p102">重复检测附近运行时，系统将分析与文本的每个文档。然后，它将每个针对其他以确定其相似性是否大于设置阈值的文档进行比较。如果是，文档组合在一起。一旦已比较所有文档和分组，每个组中的一个文档标记为"数据透视表";中查看文档，您可以先查看数据透视表，并查看中近乎重复组相同的其他文档将重点放在数据透视表中查看的文档之间的差异。</span><span class="sxs-lookup"><span data-stu-id="adb20-p102">When near duplicate detection is run, the system parses every document with text. Then, it compares every document against each other to determine whether their similarity is greater than the set threshold. If it is, the documents are grouped together. Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>