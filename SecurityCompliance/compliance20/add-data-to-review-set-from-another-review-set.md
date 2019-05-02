---
title: 将数据从一个评审集添加到另一个评审集
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
ms.openlocfilehash: 025fd90373313f762ce1d1dab8d48286e32e3cbb
ms.sourcegitcommit: 4ce350f8f3eb597587945a8ac9b33e9793440c64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2019
ms.locfileid: "33527120"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="d5a89-102">从另一个评审集向评审集添加数据</span><span class="sxs-lookup"><span data-stu-id="d5a89-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="d5a89-103">在某些情况下, 可能需要从一次审阅集中 carve 文档的一部分, 并在另一个审阅集中单独使用它们。</span><span class="sxs-lookup"><span data-stu-id="d5a89-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="d5a89-104">如果您已在审阅集中 culled 内容并希望对数据子集运行分析, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="d5a89-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="d5a89-105">使用以下工作流可将内容从一个审阅集添加到另一个审阅集。</span><span class="sxs-lookup"><span data-stu-id="d5a89-105">Use the following workflow to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d5a89-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="d5a89-106">Before you begin</span></span>

<span data-ttu-id="d5a89-107">在开始之前, 您需要创建新的审阅集以将数据添加到。</span><span class="sxs-lookup"><span data-stu-id="d5a89-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="d5a89-108">可以在案例的 "**审阅集**" 选项卡上添加新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="d5a89-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="d5a89-109">有关详细信息, 请参阅[管理审阅集](managing-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a89-109">For more information, see [Manage review sets](managing-review-sets.md).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="d5a89-110">步骤 1: 确定要添加到另一评审集的内容</span><span class="sxs-lookup"><span data-stu-id="d5a89-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="d5a89-111">您可以通过选择文档网格中的电子邮件和文档或搜索结果中的所有项目, 将内容添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="d5a89-111">You can add content to a review set by selecting emails and documents in the document grid or all items in a search result.</span></span>  <span data-ttu-id="d5a89-112">如果选择添加选定项, 请选择相应项, 单击 "**操作**", 然后单击 "**添加到另一个评审集**"。</span><span class="sxs-lookup"><span data-stu-id="d5a89-112">If choosing to add selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![添加到另一评审集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="d5a89-114">步骤 2: 指定用于添加到另一评审集的选项</span><span class="sxs-lookup"><span data-stu-id="d5a89-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="d5a89-115">在 "**添加到另一个审阅集**" 飞出页面中, 选择要将项目添加到的审阅集。</span><span class="sxs-lookup"><span data-stu-id="d5a89-115">In the **Add to another review set** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="d5a89-116">选择是否添加**所有搜索结果**或**选定的项目**。</span><span class="sxs-lookup"><span data-stu-id="d5a89-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="d5a89-117">其他信息提供选项以包括项目中的所有元数据, 以及是否应将文档标记包含在新的审阅集中。</span><span class="sxs-lookup"><span data-stu-id="d5a89-117">Additional information provides options to include all metadata from the items and finally whether or not the document tags should be included in the new review set.</span></span>  <span data-ttu-id="d5a89-118">单击 **"确定"** 后, 将创建一个新作业, 以将内容添加到审阅集;您可以在 "**作业**" 选项卡上监视该作业的进度。有关详细信息, 请参阅[管理作业](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="d5a89-118">After clicking **Ok** a new job will be created to add the content to a review set; you can monitor the progress of that job on the **Job** tab. For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>

![添加到另一评审集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)
