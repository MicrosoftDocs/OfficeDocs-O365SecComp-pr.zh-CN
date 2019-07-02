---
title: 在高级电子数据展示中设置智能标记
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
ROBOTS: NOINDEX, NOFOLLOW
description: 智能标记允许您在阅读高级电子数据展示事例中的内容时应用机器学习功能。 使用智能标记组来显示机器学习检测模型的结果, 如律师-客户端权限模型。
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703825"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="69048-104">在高级电子数据展示中设置智能标记</span><span class="sxs-lookup"><span data-stu-id="69048-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="69048-105">在审阅集中审阅案例文档时, 高级电子数据展示中的机器学习 (ML) 功能可帮助您更高效地进行决策过程。</span><span class="sxs-lookup"><span data-stu-id="69048-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="69048-106">智能标记是将 ML 功能引入记录决策的一种方法: 在审阅过程中标记文档时。</span><span class="sxs-lookup"><span data-stu-id="69048-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="69048-107">创建智能标记组时, 与智能标记组关联的 ML 模型的结果将以内嵌方式与标记组中的标记显示在一起的决策。</span><span class="sxs-lookup"><span data-stu-id="69048-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="69048-108">当你查看特定文档时, 这有助于实时查看 ML 结果信息。</span><span class="sxs-lookup"><span data-stu-id="69048-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="69048-109">如何设置智能标记组</span><span class="sxs-lookup"><span data-stu-id="69048-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="69048-110">在审阅集中, 单击 "**管理审阅集**", 然后单击 "**管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="69048-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="69048-111">单击 "**添加标记组**", 然后选择 "**添加智能标记组**"。</span><span class="sxs-lookup"><span data-stu-id="69048-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="69048-112">选择要与标记组关联的 ML 模型。</span><span class="sxs-lookup"><span data-stu-id="69048-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="69048-113">这将创建一个标记组和*N*个子标记, 其中*N*是模型的可能输出的数目。</span><span class="sxs-lookup"><span data-stu-id="69048-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="69048-114">例如,[律师-客户端权限检测模型](attorney-privilege-detection.md)有两个可能的输出:</span><span class="sxs-lookup"><span data-stu-id="69048-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="69048-115">**肯定**–用于标记包含律师-客户端权限内容的文档。</span><span class="sxs-lookup"><span data-stu-id="69048-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="69048-116">**负**–用于标记不包含律师-客户端权限内容的文档。</span><span class="sxs-lookup"><span data-stu-id="69048-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="69048-117">如果选择此模型, 则会为审阅集创建包含两个子标签的标记组 (一个名为**正数**的子标记和另一个命名的**负数**)。</span><span class="sxs-lookup"><span data-stu-id="69048-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="69048-118">在此示例中, 每个子标记对应于律师-客户端权限检测模型中的一个可能的输出。</span><span class="sxs-lookup"><span data-stu-id="69048-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="69048-119">(可选) 您可以重命名标记组和子标记。</span><span class="sxs-lookup"><span data-stu-id="69048-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="69048-120">例如, 您可以将**正数**标记重命名为 "**特权**", 而**否定**标记为 "**无权限**"。</span><span class="sxs-lookup"><span data-stu-id="69048-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="69048-121">如何使用智能标记</span><span class="sxs-lookup"><span data-stu-id="69048-121">How to use smart tags</span></span>

<span data-ttu-id="69048-122">在审阅文档时, 该模型的结果将显示在相应的子标记旁边。</span><span class="sxs-lookup"><span data-stu-id="69048-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="69048-123">例如, 如果您有一个用于律师-客户端权限检测的智能标记组, 并且您查看的文档具有潜在权限, 则该结论的原因将显示在相应标记的旁边。</span><span class="sxs-lookup"><span data-stu-id="69048-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="69048-124">请务必注意, 标记不会自动应用于文档。</span><span class="sxs-lookup"><span data-stu-id="69048-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="69048-125">审阅者做出有关如何标记文档的决定。</span><span class="sxs-lookup"><span data-stu-id="69048-125">The reviewer makes the decision about how to tag the document.</span></span>