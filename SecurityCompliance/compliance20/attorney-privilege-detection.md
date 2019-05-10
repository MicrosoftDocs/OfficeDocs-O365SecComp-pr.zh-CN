---
title: 在高级电子数据展示中设置律师-客户端特权检测
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 6838203a500a4fe600d8186a4b848beed0730665
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835062"
---
# <a name="set-up-attorney-client-privilege-detection-preview-in-advanced-ediscovery"></a><span data-ttu-id="a3dc4-102">在高级电子数据展示中设置律师-客户端特权检测 (预览)</span><span class="sxs-lookup"><span data-stu-id="a3dc4-102">Set up attorney-client privilege detection (preview) in Advanced eDiscovery</span></span>

<span data-ttu-id="a3dc4-103">任何发现过程的审阅部分的主要和昂贵的方面是查看特权内容。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-103">A major and costly aspect of the review portion of any discovery process is reviewing for privileged content.</span></span> <span data-ttu-id="a3dc4-104">高级电子数据展示在您的案例中提供了一种基于 AI 的特权内容检测, 以便您可以更高效地执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-104">Advanced eDiscovery provides an AI-based detection of privileged content in your case so that you can make this process more efficient.</span></span> <span data-ttu-id="a3dc4-105">由于此功能目前在 beta 中, 因此电子数据展示管理员必须选择使用该功能。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-105">As this feature is currently in beta, an eDiscovery Administrator has to opt into the feature to use it.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="a3dc4-106">它是如何运行的？</span><span class="sxs-lookup"><span data-stu-id="a3dc4-106">How does it work?</span></span>

<span data-ttu-id="a3dc4-107">启用此功能后, 当您在一种情况下分析评审集时, 所有文档都通过律师-客户端权限检测模型运行。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-107">With the feature turned on, when you analyze a review set within a case, all documents run through the attorney-client privilege detection model.</span></span> <span data-ttu-id="a3dc4-108">模型看上去有两个问题:</span><span class="sxs-lookup"><span data-stu-id="a3dc4-108">The model looks at two things:</span></span>

- <span data-ttu-id="a3dc4-109">内容: ML 模型确定文档内容在本质上是合法的可能性。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-109">Content: the ML model determines the likelihood of the document's content being legal in nature.</span></span>

- <span data-ttu-id="a3dc4-110">参与者: 如果存在租户的用户上传的律师列表, 模型会将文档的参与者与列表进行比较, 以确定文档是否至少有一个律师参与者。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-110">Participants: if there is a user-uploaded list of attorneys for the tenant, the model compares the participants of the document against the list to determine whether the document has at least one attorney participant.</span></span>
<span data-ttu-id="a3dc4-111">模型输出每个文档的三个值, 所有这些值都可在审阅集中进行搜索:</span><span class="sxs-lookup"><span data-stu-id="a3dc4-111">The model outputs three values for every document, all of which will be searchable within a review set:</span></span>

- <span data-ttu-id="a3dc4-112">内容分数: 文档本质上是法律的可能性 (0 到1之间的分数)</span><span class="sxs-lookup"><span data-stu-id="a3dc4-112">Content score: the likelihood of the document being legal in nature (score between 0 and 1)</span></span>

- <span data-ttu-id="a3dc4-113">拥有律师: 如果在上传的律师列表中找到了一个参与者, 则为 True, 否则为 false, 或者没有律师列表。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-113">Has Attorney: True if one of the participants is found in the uploaded attorney list, false otherwise, or if there is no attorney list.</span></span>

-  <span data-ttu-id="a3dc4-114">可能的特权: 如果内容得分高于阈值或有律师参与者, 则为 True, 否则为 false。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-114">Potentially Privileged: True if content score is above threshold or has an attorney participant, false otherwise.</span></span>

## <a name="opting-into-attorney-client-privilege-detection"></a><span data-ttu-id="a3dc4-115">选择加入律师-客户端特权检测</span><span class="sxs-lookup"><span data-stu-id="a3dc4-115">Opting into Attorney-client privilege detection</span></span>

### <a name="step-1-opt-into-attorney-client-privilege-detection-ediscovery-admin"></a><span data-ttu-id="a3dc4-116">步骤 1: 自愿加入律师-客户端权限检测 (电子数据展示管理)</span><span class="sxs-lookup"><span data-stu-id="a3dc4-116">Step 1: Opt into Attorney-client privilege detection (eDiscovery Admin)</span></span>

<span data-ttu-id="a3dc4-117">由于律师-客户端特权检测是预览功能, 因此, 您的电子数据展示管理员需要选择让该功能在你的案例中可用。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-117">Because Attorney-client privilege detection is a preview feature, your eDiscovery Administrator needs to opt in to make the feature available in your cases.</span></span>

- <span data-ttu-id="a3dc4-118">转到高级电子数据展示页面中的 "配置实验功能"</span><span class="sxs-lookup"><span data-stu-id="a3dc4-118">Go to "Configure experimental features" from Advanced eDiscovery page</span></span>

- <span data-ttu-id="a3dc4-119">单击 "管理律师-客户端特权检测"。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-119">Click on "Manage Attorney-Client Privilege detection".</span></span>

- <span data-ttu-id="a3dc4-120">单击切换以打开该功能。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-120">Click on the toggle to turn the feature on.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="a3dc4-121">步骤 2: 上传律师列表 (可选)</span><span class="sxs-lookup"><span data-stu-id="a3dc4-121">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="a3dc4-122">为了充分利用律师-客户端特权检测, 我们建议提供公司工作的电子邮件地址 (律师) 列表或法律角色。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-122">In order to take full advantage of attorney-client privilege detection we recommend providing a list of email addresses lawyers or legal personas who work for the company.</span></span> <span data-ttu-id="a3dc4-123">此列表应为不带标题的 CSV, 每行包含一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-123">The list should be a header-less CSV, with one email address per line.</span></span>

## <a name="leveraging-attorney-client-privilege-detection"></a><span data-ttu-id="a3dc4-124">利用律师-客户端特权检测</span><span class="sxs-lookup"><span data-stu-id="a3dc4-124">Leveraging attorney-client privilege detection</span></span> 

### <a name="step-1-analyze-a-review-set"></a><span data-ttu-id="a3dc4-125">步骤 1: 分析审阅集</span><span class="sxs-lookup"><span data-stu-id="a3dc4-125">Step 1: Analyze a review set</span></span>

<span data-ttu-id="a3dc4-126">分析您的审查集时, 也将运行律师-客户端权限检测。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-126">When you analyze your review set, attorney-client privilege detection will be run as well.</span></span> <span data-ttu-id="a3dc4-127">若要了解有关分析评审集中的数据的详细信息, 请参阅[在高级电子数据展示中分析评审集中的数据](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-127">To learn more about analyzing data in review set, please refer to [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-2-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="a3dc4-128">步骤 2: 创建具有律师-客户端权限检测模型的智能标记组</span><span class="sxs-lookup"><span data-stu-id="a3dc4-128">Step 2: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="a3dc4-129">您可以通过使用智能标记组, 在审查过程中使用律师-客户端权限检测的结果之一主要方法之一。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-129">One of the main ways you can consume the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="a3dc4-130">智能标记组采用 ML 模型的结果, 并在标记旁显示模型的结果, 以便您可以轻松地使用模型的结果 (如果相关), 并在您的审阅过程中使用标记, 就像您在 "标记" 面板中进行任何其他标记一样。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-130">Smart tag groups take the results of an ML model and show the results of the model in-line next to the tags, so that you can easily consume the results of the model where relevant, and use the tags in your review process as you would any other tags in your tagging panel.</span></span>

- <span data-ttu-id="a3dc4-131">在 "管理标记" 中, 单击 "添加智能标记部分"。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-131">In "Manage tags", click on "Add smart tag section".</span></span>

- <span data-ttu-id="a3dc4-132">选择 "律师-客户端特权检测"。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-132">Select "Attorney-client privilege detection".</span></span> <span data-ttu-id="a3dc4-133">你将看到, 已创建与模型的可能结果对应的标记组和两个标记。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-133">You will see that a tag group and two tags, corresponding to the possible results of the model, have been created.</span></span>

- <span data-ttu-id="a3dc4-134">根据您的审阅情况, 重命名标签组和标签。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-134">Rename the tag group and tags as you see fit for your review.</span></span>

### <a name="step-3-use-the-smart-tag-group-for-privilege-review"></a><span data-ttu-id="a3dc4-135">步骤 3: 使用智能标记组进行权限审阅</span><span class="sxs-lookup"><span data-stu-id="a3dc4-135">Step 3: Use the smart tag group for privilege review</span></span>

<span data-ttu-id="a3dc4-136">查看文档时, 如果模型已确定文档具有潜在权限, 则相应的智能标记将公开结果:</span><span class="sxs-lookup"><span data-stu-id="a3dc4-136">When you review a document, if the model has determined that the document is potentially privileged, the corresponding smart tag will expose the result:</span></span>

- <span data-ttu-id="a3dc4-137">如果文档的内容本身可能是合法的, 则会在相应的智能标记旁边显示 "法律内容" 标签。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-137">If the document has content that may be legal in nature, a "Legal content" label will appear next to the corresponding smart tag.</span></span>

- <span data-ttu-id="a3dc4-138">如果文档具有在上载的律师列表中找到的参与者, 则 "律师" 标签将显示在相应的智能标记旁边。</span><span class="sxs-lookup"><span data-stu-id="a3dc4-138">If the document has a participant that is found in the uploaded attorney list, an "Attorney" label will appear next to the corresponding smart tag.</span></span>