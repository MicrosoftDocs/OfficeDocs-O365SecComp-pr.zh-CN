---
title: 在高级电子数据展示中设置律师-客户端特权检测
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
description: 选择加入并使用律师-客户端权限检测模型, 在查看高级电子数据展示事例中的内容时, 使用基于机器学习的权限内容检测。
ms.openlocfilehash: 16a6a215484c35d20fbe071cac033133270b7ea6
ms.sourcegitcommit: e323610df2df71c84f536e8a38650d33d8069e41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34703852"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="f367a-103">在高级电子数据展示中设置律师-客户端特权检测</span><span class="sxs-lookup"><span data-stu-id="f367a-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="f367a-104">任何电子数据展示过程的审核阶段的主要和昂贵的方面是查看文档中的特权内容。</span><span class="sxs-lookup"><span data-stu-id="f367a-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="f367a-105">高级电子数据展示提供基于机器学习的权限内容检测, 以提高此过程的效率。</span><span class="sxs-lookup"><span data-stu-id="f367a-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="f367a-106">此功能称为 "*律师-客户端特权检测*"。</span><span class="sxs-lookup"><span data-stu-id="f367a-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="f367a-107">您必须选择使用律师-客户端权限检测模型, 然后才能使用它。</span><span class="sxs-lookup"><span data-stu-id="f367a-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="f367a-108">有关说明, 请参阅[步骤 1](#step-1-opt-in-to-attorney-client-privilege-detection) 。</span><span class="sxs-lookup"><span data-stu-id="f367a-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="f367a-109">它是如何运行的？</span><span class="sxs-lookup"><span data-stu-id="f367a-109">How does it work?</span></span>

<span data-ttu-id="f367a-110">如果启用律师-客户端特权检测, 则在分析评审集中[的数据](analyzing-data-in-review-set.md)时, 将由律师-客户端权限检测模型处理审阅集中的所有文档。</span><span class="sxs-lookup"><span data-stu-id="f367a-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="f367a-111">模型将查找两个事项:</span><span class="sxs-lookup"><span data-stu-id="f367a-111">The model looks for two things:</span></span>

- <span data-ttu-id="f367a-112">特权内容–模型使用机器学习来确定文档中包含法律性质的内容的可能性。</span><span class="sxs-lookup"><span data-stu-id="f367a-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="f367a-113">参与者–在设置律师-客户端权限检测的过程中, 您必须提交您的组织的律师列表。</span><span class="sxs-lookup"><span data-stu-id="f367a-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="f367a-114">然后, 模型将文档的参与者与律师列表进行比较, 以确定文档是否至少有一个律师参与者。</span><span class="sxs-lookup"><span data-stu-id="f367a-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="f367a-115">模型将为每个文档生成以下三个属性:</span><span class="sxs-lookup"><span data-stu-id="f367a-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="f367a-116">**AttorneyClientPrivilegeScore** –文档在本质上是合法的可能性;分数的值介于**0**和**1**之间。</span><span class="sxs-lookup"><span data-stu-id="f367a-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="f367a-117">**HasAttorney** –如果某个文档参与者在律师列表中列出, 则此属性设置为**true** ; 否则为 false。否则, 该值为**false**。</span><span class="sxs-lookup"><span data-stu-id="f367a-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="f367a-118">如果你的组织未上传律师列表, 则此值也设置为**false** 。</span><span class="sxs-lookup"><span data-stu-id="f367a-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="f367a-119">**IsPrivilege** –如果**AttorneyClientPrivilegeScore**的值高于阈值*或*文档有律师参与者, 则此属性设置为**true** ; 否则为 false。否则, 该值设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="f367a-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="f367a-120">这些属性 (及其对应的值) 将添加到审阅集中文档的文件元数据中, 如以下屏幕截图所示:</span><span class="sxs-lookup"><span data-stu-id="f367a-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![律师-文件元数据中显示的客户端权限属性](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="f367a-122">这三个属性也可在审阅集中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f367a-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="f367a-123">有关详细信息, 请参阅[在审阅集中查询数据](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="f367a-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="f367a-124">设置律师-客户端权限检测模型</span><span class="sxs-lookup"><span data-stu-id="f367a-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="f367a-125">若要启用律师-客户端权限检测模型, 您的组织必须选择加入并上传律师列表。</span><span class="sxs-lookup"><span data-stu-id="f367a-125">To enable the attorney-client privilege detection model, your organization has to opt-in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="f367a-126">步骤 1: 选择加入律师-客户端特权检测</span><span class="sxs-lookup"><span data-stu-id="f367a-126">Step 1: Opt-in to attorney-client privilege detection</span></span>

<span data-ttu-id="f367a-127">如前面所述, 律师-客户端特权检测模型处于预览阶段。</span><span class="sxs-lookup"><span data-stu-id="f367a-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="f367a-128">因此, 组织电子数据展示管理员 (电子数据展示管理器角色组中的电子数据展示管理员子组的成员) 的人员必须选择将模型提供给高级电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="f367a-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="f367a-129">在安全 & 合规性中心中, 转到**电子数据展示 > 高级电子数据展示**。</span><span class="sxs-lookup"><span data-stu-id="f367a-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="f367a-130">在**高级电子数据展示**主页上的 "**设置**" 磁贴中, 单击 "**配置实验功能**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**.</span></span>

   ![单击 "配置实验功能"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="f367a-132">在 "**实验功能**" 选项卡上, 单击 "**管理律师-客户端权限设置**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-132">On the **Experimental features** tab, click **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="f367a-133">在 "**律师-客户端权限**" 飞出页面上, 单击 "切换" 以打开功能, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-133">On the **Attorney-client privilege** flyout page, click the toggle to turn on the feature and then click **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="f367a-134">步骤 2: 上传律师列表 (可选)</span><span class="sxs-lookup"><span data-stu-id="f367a-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="f367a-135">若要充分利用律师-客户端特权检测模型, 并使用前面所述的 "**拥有律师**" 或 "具有**可能的特权**检测" 的结果, 我们建议您上载的电子邮件地址的列表。为你的组织工作的律师和法律员工。</span><span class="sxs-lookup"><span data-stu-id="f367a-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="f367a-136">若要上传律师列表以供律师-客户端权限检测模型使用, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f367a-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="f367a-137">创建一个 .csv 文件 (不带标题行), 并在单独的行中添加每个相应人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f367a-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="f367a-138">将此文件保存到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="f367a-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="f367a-139">在**高级电子数据展示**主页上的 "**设置**" 磁贴中, 单击 "**配置实验性功能**", 然后单击 "**管理律师-客户端权限设置**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**, and then click **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="f367a-140">将显示 "**律师-客户端权限**" 页, 并且启用了 "**律师-客户端权限检测**" 切换功能。</span><span class="sxs-lookup"><span data-stu-id="f367a-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![律师-客户端权限飞出页面](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="f367a-142">单击 "**浏览**", 然后查找并选择您在步骤1中创建的 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="f367a-142">Click **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="f367a-143">单击 "**保存**" 以上传律师列表。</span><span class="sxs-lookup"><span data-stu-id="f367a-143">Click **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="f367a-144">使用律师-客户端权限检测模型</span><span class="sxs-lookup"><span data-stu-id="f367a-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="f367a-145">按照此部分中的步骤操作, 对审阅集中的文档使用律师-客户端权限检测。</span><span class="sxs-lookup"><span data-stu-id="f367a-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="f367a-146">步骤 1: 创建具有律师-客户端权限检测模型的智能标记组</span><span class="sxs-lookup"><span data-stu-id="f367a-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="f367a-147">查看审查过程中的律师-客户端特权检测的结果之一是使用智能标记组的一种主要方式。</span><span class="sxs-lookup"><span data-stu-id="f367a-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="f367a-148">智能标记组指示律师-客户端权限检测的结果, 并在智能标记组中标记的旁边显示结果。</span><span class="sxs-lookup"><span data-stu-id="f367a-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="f367a-149">这使您可以在文档审阅过程中快速识别可能的特权文档。</span><span class="sxs-lookup"><span data-stu-id="f367a-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="f367a-150">此外, 还可以使用智能标记组中的标记将文档标记为特权或非特权。</span><span class="sxs-lookup"><span data-stu-id="f367a-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="f367a-151">有关智能标记的详细信息, 请参阅[在高级电子数据展示中设置智能标记](smart-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="f367a-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="f367a-152">在包含您在步骤1中分析的文档的审阅集中, 单击 "**管理审阅集**", 然后单击 "**管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-152">In the review set that contains the documents that you analyzed in Step 1, click **Manage review set** and then click **Manage tags**.</span></span>
 
2. <span data-ttu-id="f367a-153">在 "**标记**" 下, 单击 "**添加组**" 旁边的下拉下拉箭头, 然后单击 "**添加智能标记组**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-153">Under **Tags**, click the pull-down next to **Add group** and then click **Add smart tag group**.</span></span>

   ![单击 "添加智能标记组"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="f367a-155">在 "**选择智能标记的模型**" 页上, 单击 "**律师-客户端权限**" 旁边的 "**选择**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-155">On the **Choose a model for your smart tag** page, click **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="f367a-156">将显示名为 "**律师-客户端" 权限**的标记组。</span><span class="sxs-lookup"><span data-stu-id="f367a-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="f367a-157">它包含两个名为**正数**和**负数**的子标记, 它们对应于由模型生成的可能结果。</span><span class="sxs-lookup"><span data-stu-id="f367a-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![律师-客户端权限智能标记组](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="f367a-159">根据需要, 重命名标记组和标记以进行查看。</span><span class="sxs-lookup"><span data-stu-id="f367a-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="f367a-160">例如, 可以将**肯定**重命名为**特权**, 将**否定**重命名为 "**无权限**"。</span><span class="sxs-lookup"><span data-stu-id="f367a-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="f367a-161">步骤 2: 分析审阅集</span><span class="sxs-lookup"><span data-stu-id="f367a-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="f367a-162">在对审阅集中的文档进行分析时, 还将运行律师-客户端权限检测模型, 并且相应的属性 (在["工作原理"](#how-does-it-work)中进行了说明) 将添加到审阅集内的每个文档中。</span><span class="sxs-lookup"><span data-stu-id="f367a-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also be run and the corresponding properties (described in[How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="f367a-163">有关分析审阅集中的数据的详细信息, 请参阅[在高级电子数据展示中分析审阅集中的数据](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="f367a-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="f367a-164">步骤 3: 使用智能标记组查看特权内容</span><span class="sxs-lookup"><span data-stu-id="f367a-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="f367a-165">分析评审集并设置智能标记后, 下一步是查看文档。</span><span class="sxs-lookup"><span data-stu-id="f367a-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="f367a-166">如果模型已确定文档具有潜在权限, 则在 "**标记" 面板**中对应的智能标记将指示由律师-客户端权限检测产生的以下结果:</span><span class="sxs-lookup"><span data-stu-id="f367a-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="f367a-167">如果文档的内容本身可能是合法的, 则会在相应的智能标记 (在此示例中为默认的**正**则标记) 旁边显示标签**法律内容**。</span><span class="sxs-lookup"><span data-stu-id="f367a-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="f367a-168">如果文档具有在组织的律师列表中找到的参与者, 则标签**律师**将显示在相应的智能标记 (在此示例中也是默认的**正数**标记) 旁边。</span><span class="sxs-lookup"><span data-stu-id="f367a-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="f367a-169">如果文档的内容可能是合法的 *, 并且*在律师列表中找到了参与者, 则会同时显示**法律内容**和**律师**标签。</span><span class="sxs-lookup"><span data-stu-id="f367a-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="f367a-170">如果模型确定文档不包含性质为合法的内容或不包含律师列表中的参与者, 则在 "标记" 面板中不会显示任何标签。</span><span class="sxs-lookup"><span data-stu-id="f367a-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="f367a-171">例如, 下面的屏幕截图显示两个文档;第一个包含的内容在性质上是合法的, 并且在律师列表中找到了参与者;第二个不包含, 因此不显示任何标签。</span><span class="sxs-lookup"><span data-stu-id="f367a-171">For example, the following screenshots show two documents; the first one contains content that is legal in nature and has a participant found in the list of attorneys; the second contains neither and therefore doesn't display any labels.</span></span>

![包含律师和法律内容标签的文档](../media/AeDTaggingPanelLegalContentAttorney.png)

![不带任何标签的文档](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="f367a-174">查看文档以查看其是否包含特权内容之后, 可以使用相应的标记对文档进行标记。</span><span class="sxs-lookup"><span data-stu-id="f367a-174">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>