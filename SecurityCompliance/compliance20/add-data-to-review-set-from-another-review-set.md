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
ms.openlocfilehash: 3a4d0d309daa5af9830f98215ca09321429785ee
ms.sourcegitcommit: 25595bc8fae96bc23b7b6d7102a22f37878987c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "33641642"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="b338d-102">从另一个评审集向评审集添加数据</span><span class="sxs-lookup"><span data-stu-id="b338d-102">Add data to a review set from another review set</span></span>

<span data-ttu-id="b338d-103">在某些情况下, 可能需要从一次审阅集中 carve 文档的一部分, 并在另一个审阅集中单独使用它们。</span><span class="sxs-lookup"><span data-stu-id="b338d-103">In some cases, it may be necessary to carve out a portion of documents from one review set and work with them individually in another review set.</span></span>  <span data-ttu-id="b338d-104">如果您已在审阅集中 culled 内容并希望对数据子集运行分析, 这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="b338d-104">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="b338d-105">请遵循本文中的工作流, 将内容从一个审阅集添加到另一个评审集。</span><span class="sxs-lookup"><span data-stu-id="b338d-105">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b338d-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="b338d-106">Before you begin</span></span>

<span data-ttu-id="b338d-107">在开始之前, 您需要创建新的审阅集以将数据添加到。</span><span class="sxs-lookup"><span data-stu-id="b338d-107">Before you start, you'll need to create a new review set to add the data to.</span></span>  <span data-ttu-id="b338d-108">可以在案例的 "**审阅集**" 选项卡上添加新的审阅集。</span><span class="sxs-lookup"><span data-stu-id="b338d-108">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="b338d-109">有关详细信息, 请参阅[创建审阅集](managing-review-sets.md#create-a-review-set)。</span><span class="sxs-lookup"><span data-stu-id="b338d-109">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="b338d-110">步骤 1: 确定要添加到另一评审集的内容</span><span class="sxs-lookup"><span data-stu-id="b338d-110">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="b338d-111">您可以通过选择源评审集或 b seleting 中的特定文档, 将内容从一个评审集添加到另一个评审集。</span><span class="sxs-lookup"><span data-stu-id="b338d-111">You can add content from one review set to another one by selecting specific documents in the source review set or b seleting all items returned by review set query.</span></span>  <span data-ttu-id="b338d-112">如果要添加选定项, 请选择相应项, 单击 "**操作**", 然后单击 "**添加到另一个评审集**"。</span><span class="sxs-lookup"><span data-stu-id="b338d-112">If you're adding selected items, select the items, click **Action**, and then click **Add to another review set**.</span></span>

![添加到另一评审集](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="b338d-114">步骤 2: 指定用于添加到另一评审集的选项</span><span class="sxs-lookup"><span data-stu-id="b338d-114">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="b338d-115">在 "**添加到另一张审阅集选项**" 飞出页面中, 选择要将项目添加到的审阅集。</span><span class="sxs-lookup"><span data-stu-id="b338d-115">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="b338d-116">选择是否添加**所有搜索结果**或**选定的项目**。</span><span class="sxs-lookup"><span data-stu-id="b338d-116">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="b338d-117">其他信息提供选项以包括项目中的所有元数据, 以及在将文档添加到新评审集时是否将标记 (通过选中 "**标签**" 复选框) 包括在源评审集中。</span><span class="sxs-lookup"><span data-stu-id="b338d-117">Additional information provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** checkbox) from the source review set when the documents are added to the new review set.</span></span>  

![添加到另一评审集](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="b338d-119">单击 **"确定"** 后, 将创建一个新作业 (名为 "**将数据添加到另一个审阅集**"), 以将内容添加到另一个审阅集。</span><span class="sxs-lookup"><span data-stu-id="b338d-119">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to a another review set.</span></span>  <span data-ttu-id="b338d-120">您可以转到 "**作业**" 选项卡并监视此作业的进度。</span><span class="sxs-lookup"><span data-stu-id="b338d-120">You can go to **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="b338d-121">有关详细信息, 请参阅[管理作业](managing-jobs-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="b338d-121">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
