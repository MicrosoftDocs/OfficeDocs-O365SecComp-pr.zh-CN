---
title: 查看高级电子数据展示中的对话
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
ms.openlocfilehash: 62f0dc9e32e89954b2838b70757d3a7c17d79cc4
ms.sourcegitcommit: 6302a43d947a908dd10a8e40550b806f491692fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/13/2019
ms.locfileid: "35672953"
---
# <a name="review-conversations-in-advanced-ediscovery"></a><span data-ttu-id="c2de0-102">查看高级电子数据展示中的对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-102">Review conversations in Advanced eDiscovery</span></span> 

<span data-ttu-id="c2de0-103">即时消息是一种方便的方法, 可以在大型访问群体中提问、分享想法或快速通信。</span><span class="sxs-lookup"><span data-stu-id="c2de0-103">Instant messaging is a convenient way to ask questions, share ideas, or quickly communicate across large audiences.</span></span> <span data-ttu-id="c2de0-104">作为即时消息平台 (如 Microsoft 团队) 成为企业协作的核心, 组织必须评估其电子数据展示工作流如何解决这些新的通信和协作形式。</span><span class="sxs-lookup"><span data-stu-id="c2de0-104">As instant messaging platforms, like Microsoft Teams, become core to enterprise collaboration, organizations must evaluate how their eDiscovery workflow addresses these new forms of communication and collaboration.</span></span> 

<span data-ttu-id="c2de0-105">高级电子数据展示中的会话重建功能旨在帮助您识别上下文内容并生成独特的对话视图。</span><span class="sxs-lookup"><span data-stu-id="c2de0-105">The Conversation Reconstruction feature in Advanced eDiscovery is designed to help you identify contextual content and produce distinct conversation views.</span></span> <span data-ttu-id="c2de0-106">通过此功能, 您可以高效快速地查看在 Microsoft 团队等平台中生成的完整即时消息对话 (也称为 "*线索对话*")。</span><span class="sxs-lookup"><span data-stu-id="c2de0-106">This capability allows you to efficiently and rapidly review complete instant message conversations (also called *threaded conversations*) that are generated in platforms like Microsoft Teams.</span></span>

<span data-ttu-id="c2de0-107">通过对话重建, 可以使用内置功能来重建、审阅和导出线程对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-107">With Conversation Reconstruction, you can use built-in capabilities to reconstruct, review, and export threaded conversations.</span></span> <span data-ttu-id="c2de0-108">将高级电子数据展示对话重建为以下内容:</span><span class="sxs-lookup"><span data-stu-id="c2de0-108">Use Advanced eDiscovery Conversation Reconstruction to:</span></span>

- <span data-ttu-id="c2de0-109">在会话内的所有邮件中保留唯一的邮件级元数据。</span><span class="sxs-lookup"><span data-stu-id="c2de0-109">Preserve unique message-level metadata across all messages within a conversation.</span></span>

- <span data-ttu-id="c2de0-110">收集有关搜索结果的上下文邮件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-110">Collect contextual messages around your search results.</span></span>

- <span data-ttu-id="c2de0-111">审阅、批注和密文串接的对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-111">Review, annotate, and redact threaded conversations.</span></span>

- <span data-ttu-id="c2de0-112">导出单个邮件或线索对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-112">Export individual messages or threaded conversations</span></span>

## <a name="terminology"></a><span data-ttu-id="c2de0-113">术语</span><span class="sxs-lookup"><span data-stu-id="c2de0-113">Terminology</span></span>

<span data-ttu-id="c2de0-114">下面是一些定义, 可帮助你开始使用对话重建。</span><span class="sxs-lookup"><span data-stu-id="c2de0-114">Here are few definitions to help you get start using Conversation Reconstruction.</span></span>

- <span data-ttu-id="c2de0-115">**邮件:** 表示对话的最小单位。</span><span class="sxs-lookup"><span data-stu-id="c2de0-115">**Messages:** Represent the smallest unit of a conversation.</span></span> <span data-ttu-id="c2de0-116">邮件的大小、结构和元数据可能各不相同。</span><span class="sxs-lookup"><span data-stu-id="c2de0-116">Messages may vary in size, structure, and metadata.</span></span> 

- <span data-ttu-id="c2de0-117">**对话:** 代表一个或多个邮件的分组。</span><span class="sxs-lookup"><span data-stu-id="c2de0-117">**Conversation:** Represents a grouping of one or more messages.</span></span> <span data-ttu-id="c2de0-118">在不同的应用程序中, 对话可能以不同的方式表示。</span><span class="sxs-lookup"><span data-stu-id="c2de0-118">Across different applications, conversations may be represented in different ways.</span></span> <span data-ttu-id="c2de0-119">在某些应用程序中, 通过答复现有邮件产生的显式操作。</span><span class="sxs-lookup"><span data-stu-id="c2de0-119">In some applications, there is an explicit action that results from replying to an existing message.</span></span> <span data-ttu-id="c2de0-120">对话是作为此用户操作的结果而显式形成的。</span><span class="sxs-lookup"><span data-stu-id="c2de0-120">Conversations are formed explicitly as a result of this user action.</span></span> <span data-ttu-id="c2de0-121">例如, 下面是 Microsoft 团队中的频道对话的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="c2de0-121">For example, here is a screenshot of a channel conversation in Microsoft Teams.</span></span>

   ![Microsoft 团队频道对话](../media/threadedchat.png)

   <span data-ttu-id="c2de0-123">在其他应用程序 (例如, 工作组中的1xN 聊天邮件) 中, 没有正式的答复链, 而是在单个线程中显示为 "简单消息化的邮件"。</span><span class="sxs-lookup"><span data-stu-id="c2de0-123">In other apps (such as 1xN chat messages in Teams), there is not a formal reply chain and instead messages appear as a "flat river of messages" within a single thread.</span></span> <span data-ttu-id="c2de0-124">在这些类型的应用程序中, 将从在特定时间内发生的一组邮件中推断对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-124">In these types apps, conversations are inferred from a group of messages that occur within a certain time.</span></span> <span data-ttu-id="c2de0-125">邮件的这种 "软分组" (而不是 "回复链") 表示有关特定主题的 "前后" 讨论。</span><span class="sxs-lookup"><span data-stu-id="c2de0-125">This "soft-grouping" of messages (as opposed to a reply chain) represent the "back and forth" conversation about a specific topic of interest.</span></span> 

## <a name="step-1-run-a-search"></a><span data-ttu-id="c2de0-126">步骤 1: 运行搜索</span><span class="sxs-lookup"><span data-stu-id="c2de0-126">Step 1: Run a search</span></span>

<span data-ttu-id="c2de0-127">在确定了相关保管人和内容位置之后, 可以创建搜索以查找潜在的相关内容。</span><span class="sxs-lookup"><span data-stu-id="c2de0-127">After you have identified relevant custodians and content locations, you can create a search to find potentially relevant content.</span></span> <span data-ttu-id="c2de0-128">在高级电子数据展示事例的 "**搜索**" 选项卡上, 您可以通过单击 "**新建搜索**" 并按照向导来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="c2de0-128">On the **Searches** tab in the Advanced eDiscovery case, you can create a search by clicking **New search** and following the wizard.</span></span> <span data-ttu-id="c2de0-129">有关如何创建搜索、构建搜索查询和查看搜索结果的信息, 请参阅[为事例收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="c2de0-129">For information about how you can create a search, build a search query, and view the search results, see [Collect data for a case](create-search-to-collect-data.md).</span></span>

## <a name="step-2-create-a-conversation-review-set"></a><span data-ttu-id="c2de0-130">步骤 2: 创建对话评审集</span><span class="sxs-lookup"><span data-stu-id="c2de0-130">Step 2: Create a conversation review set</span></span>

<span data-ttu-id="c2de0-131">在审阅集中, 您可以搜索、标记、批注和密文文档、电子邮件和聊天对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-131">In a review set, you can search, tag, annotate, and redact documents, email messages, and chat conversations.</span></span> <span data-ttu-id="c2de0-132">在高级电子数据展示中, 可以基于单个邮件或线索对话自定义您对对话的审阅。</span><span class="sxs-lookup"><span data-stu-id="c2de0-132">In Advanced eDiscovery, you can customize your review of conversations, based in individual messages or threaded conversations.</span></span> <span data-ttu-id="c2de0-133">这取决于您将在步骤1中创建的搜索结果添加到的审查集的类型。</span><span class="sxs-lookup"><span data-stu-id="c2de0-133">This is determined by the type of review set that you add the results of the search created in Step 1 to.</span></span> <span data-ttu-id="c2de0-134">有两种不同类型的审阅集:</span><span class="sxs-lookup"><span data-stu-id="c2de0-134">There are two different types of review sets:</span></span> 
  
  - <span data-ttu-id="c2de0-135">**标准审阅集:** 将处理对话中的邮件并将其显示为单个项目。</span><span class="sxs-lookup"><span data-stu-id="c2de0-135">**Standard review sets:** Messages in conversations are processed and displayed as individual items.</span></span> 
  
  -  <span data-ttu-id="c2de0-136">**对话查看集:** 对话中的邮件单独处理, 但在对话视图中显示。</span><span class="sxs-lookup"><span data-stu-id="c2de0-136">**Conversation review sets:** Messages in conversations are processed individually but displayed in a conversation view.</span></span> <span data-ttu-id="c2de0-137">在对话审阅集中, 您可以在 "线程对话" 视图中对邮件添加批注、标记和标记密文。</span><span class="sxs-lookup"><span data-stu-id="c2de0-137">In a conversation review set, you can annotate, tag, and redact messages in a threaded conversation view.</span></span> 

<span data-ttu-id="c2de0-138">若要详细了解如何查看和管理审阅集中的内容, 请参阅[管理审阅集](managing-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="c2de0-138">For more information about how to review and manage content in a review set, see [Manage review sets](managing-review-sets.md).</span></span> 

## <a name="step-3-enable-conversation-retrieval-options"></a><span data-ttu-id="c2de0-139">步骤 3: 启用对话检索选项</span><span class="sxs-lookup"><span data-stu-id="c2de0-139">Step 3: Enable conversation retrieval options</span></span>

<span data-ttu-id="c2de0-140">检查并完成搜索查询后, 可以将搜索结果添加到审阅集。</span><span class="sxs-lookup"><span data-stu-id="c2de0-140">After you have reviewed and finalized your search query, you can add the search results to a review set.</span></span> <span data-ttu-id="c2de0-141">将搜索结果添加到评审集时, 会将原始数据复制到 Azure 存储区, 以促进审阅和分析过程。</span><span class="sxs-lookup"><span data-stu-id="c2de0-141">When you add your search results into a review set, the original data is copied to an Azure Storage area to facilitate the review and analysis process.</span></span> <span data-ttu-id="c2de0-142">有关将搜索结果添加到审阅集的详细信息, 请参阅[将搜索结果添加到审阅集](add-data-to-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="c2de0-142">For more information about adding search results to a review set, see [Add search results to a review set](add-data-to-review-set.md).</span></span> 

<span data-ttu-id="c2de0-143">将数据从对话添加到审阅集时, 可以使用对话检索选项来扩展搜索并包含上下文相关邮件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-143">When you add data from conversations to a review set, you can use the conversation retrieval options to expand your search and include contextual messages.</span></span> <span data-ttu-id="c2de0-144">设置对话检索选项后, 可能会发生以下情况:</span><span class="sxs-lookup"><span data-stu-id="c2de0-144">After you set the conversation retrieval options, the following things can happen:</span></span>

  ![对话检索](../media/messagesandconversations.png)
  
1. <span data-ttu-id="c2de0-146">使用关键字和日期范围查询, 搜索会在*邮件 3*上返回一个命中。</span><span class="sxs-lookup"><span data-stu-id="c2de0-146">Using a keyword and date range query, the search returned a hit on *Message 3*.</span></span> <span data-ttu-id="c2de0-147">此邮件是更大的对话的一部分, 如*CRC1*所示。</span><span class="sxs-lookup"><span data-stu-id="c2de0-147">This message was part of a larger conversation, illustrated by *CRC1*.</span></span> 
  
2. <span data-ttu-id="c2de0-148">当您将数据添加到审阅集中并启用对话检索选项时, 高级电子数据展示将返回并收集*CRC1*中的其他项目。</span><span class="sxs-lookup"><span data-stu-id="c2de0-148">When you add the data into a review set and enable the conversation retrieval options, Advanced eDiscovery will go back and collect other items in *CRC1*.</span></span> 
  
3. <span data-ttu-id="c2de0-149">将项目添加到审阅集后, 可以查看*CRC1*中的所有单个邮件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-149">After the items have been added to the review set, you can review all the individual messages from *CRC1*.</span></span> 



<span data-ttu-id="c2de0-150">启用对话检索:</span><span class="sxs-lookup"><span data-stu-id="c2de0-150">To enable conversation retrieval:</span></span>
  
1. <span data-ttu-id="c2de0-151">在高级电子数据展示事例的 "**搜索**" 选项卡上, 选择一个搜索, 然后单击弹出页面上的 "**添加到审阅集**"。</span><span class="sxs-lookup"><span data-stu-id="c2de0-151">On the **Searches** tab in the Advanced eDiscovery case, select a search, and then click **Add to review set** on the flyout page.</span></span>
  
2. <span data-ttu-id="c2de0-152">选择现有的审阅集或创建审阅集。</span><span class="sxs-lookup"><span data-stu-id="c2de0-152">Select an existing review set or create a review set.</span></span> <span data-ttu-id="c2de0-153">将搜索结果添加到标准或对话评审集时, 可以配置检索选项。</span><span class="sxs-lookup"><span data-stu-id="c2de0-153">You can configure retrieval options when adding search results to a standard or a conversation review set.</span></span>
  
3. <span data-ttu-id="c2de0-154">为您希望在搜索中展开的内容源配置对话检索选项, 然后单击 "**添加**" 以启动该过程。</span><span class="sxs-lookup"><span data-stu-id="c2de0-154">Configure the conversation retrieval options for the content sources that you would like to expand in your search, and then click **Add** to start the process.</span></span>  
  
4. <span data-ttu-id="c2de0-155">完成 "**作业**" 选项卡上的 "**添加到审阅集**" 作业后, 即可开始查看对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-155">After the **Add to review set** job on the **Jobs** tab has finished, you can start reviewing the conversations.</span></span>

## <a name="step-4-review-conversations-in-the-review-set"></a><span data-ttu-id="c2de0-156">步骤 4: 查看评审集中的对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-156">Step 4: Review conversations in the review set</span></span>

<span data-ttu-id="c2de0-157">在处理完内容并将其添加到审阅集后, 即可开始查看评审集中的数据。</span><span class="sxs-lookup"><span data-stu-id="c2de0-157">After the content has been processed and added to the review set, you can start reviewing the data in the review set.</span></span> <span data-ttu-id="c2de0-158">审阅功能会有所不同, 具体取决于内容是添加到标准审阅集还是对话评审集。</span><span class="sxs-lookup"><span data-stu-id="c2de0-158">The review capabilities are different depending on whether the content was added to a standard review set or a conversation review set.</span></span> 

### <a name="reviewing-conversations-in-a-standard-review-set"></a><span data-ttu-id="c2de0-159">查看标准审阅集中的对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-159">Reviewing conversations in a standard review Set</span></span>

<span data-ttu-id="c2de0-160">在标准审阅集中, 邮件将作为单个项目进行处理和显示, 就像它们存储在邮箱文件夹中的方式一样。</span><span class="sxs-lookup"><span data-stu-id="c2de0-160">In a standard review set, messages are processed and displayed as individual items, similar to how they're stored in a mailbox folder.</span></span> <span data-ttu-id="c2de0-161">在此工作流中, 每封邮件都作为一个单独的项目处理。</span><span class="sxs-lookup"><span data-stu-id="c2de0-161">In this workflow, each message is processed as a separate item.</span></span> <span data-ttu-id="c2de0-162">因此, "线程摘要" 和 "导出" 选项在标准审阅集中不可用。</span><span class="sxs-lookup"><span data-stu-id="c2de0-162">As a result, the threaded summary and export options aren't available in a standard review set.</span></span> 

### <a name="reviewing-conversations-in-a-conversation-review-set"></a><span data-ttu-id="c2de0-163">查看对话审阅集中的对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-163">Reviewing conversations in a conversation review set</span></span>

<span data-ttu-id="c2de0-164">在对话审阅集中, 各个邮件将串接在一起, 并显示为对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-164">In a conversation review set, individual messages are threaded together and presented as conversations.</span></span> <span data-ttu-id="c2de0-165">这将允许您查看和导出上下文对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-165">This lets you review and export contextual conversations.</span></span> <span data-ttu-id="c2de0-166">以下各节介绍了如何在对话评审集中审阅和导出对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-166">The following sections describe reviewing and exporting conversations in a conversation review set.</span></span>

#### <a name="reviewing-conversations"></a><span data-ttu-id="c2de0-167">查看对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-167">Reviewing conversations</span></span>

<span data-ttu-id="c2de0-168">在对话审阅集中, 您可以使用以下选项来促进审核过程。</span><span class="sxs-lookup"><span data-stu-id="c2de0-168">In a conversation review set, you can use the following options to facilitate the review process.</span></span>

- <span data-ttu-id="c2de0-169">**按会话分组:** 将同一对话中的邮件组合在一起, 以帮助用户简化和加快其审阅过程。</span><span class="sxs-lookup"><span data-stu-id="c2de0-169">**Group by conversation:** Groups messages within the same conversation together to help users simplify and expedite their review process.</span></span> 

- <span data-ttu-id="c2de0-170">**摘要视图:** 显示线程对话。</span><span class="sxs-lookup"><span data-stu-id="c2de0-170">**Summary view:** Displays the threaded conversation.</span></span> <span data-ttu-id="c2de0-171">在此视图中, 您可以查看整个对话, 还可以访问每个邮件的元数据。</span><span class="sxs-lookup"><span data-stu-id="c2de0-171">In this view, you can see the entire conversation and also access the metadata for each individual message.</span></span>  
  
   - <span data-ttu-id="c2de0-172">查看单个邮件的元数据</span><span class="sxs-lookup"><span data-stu-id="c2de0-172">View metadata for individual messages</span></span>
   
   - <span data-ttu-id="c2de0-173">下载单个邮件</span><span class="sxs-lookup"><span data-stu-id="c2de0-173">Download individual messages</span></span>

- <span data-ttu-id="c2de0-174">**文本视图:** 为整个对话提供提取的文本。</span><span class="sxs-lookup"><span data-stu-id="c2de0-174">**Text view:** Provides the extracted text for the entire conversation.</span></span> 

- <span data-ttu-id="c2de0-175">**批注视图:** 允许您标记对话的线程视图。</span><span class="sxs-lookup"><span data-stu-id="c2de0-175">**Annotate view:** Lets you markup a threaded view of the conversation.</span></span> <span data-ttu-id="c2de0-176">对话中的所有邮件共享相同的批注文档。</span><span class="sxs-lookup"><span data-stu-id="c2de0-176">All messages in the conversation share the same annotated document.</span></span>

- <span data-ttu-id="c2de0-177">**标记:** 在审阅集中查看对话时, 可以通过单击 "**编码" 面板**查看和应用标签。</span><span class="sxs-lookup"><span data-stu-id="c2de0-177">**Tag:** When viewing conversations in a review set, you can view and apply tags by clicking the **Coding panel**.</span></span>

- <span data-ttu-id="c2de0-178">**重新运行对话转换:** 将邮件添加到对话评审集时, 将自动运行转换作业以创建带线索的摘要和批注视图。</span><span class="sxs-lookup"><span data-stu-id="c2de0-178">**Rerun conversation conversion:** When messages are added to a conversation review set, a conversion job is automatically run to create the threaded summary and annotate views.</span></span> <span data-ttu-id="c2de0-179">如果会话重建作业失败, 您可以通过单击 "操作" > "在审阅集中**创建对话 pdf** " 来重新运行转换作业。</span><span class="sxs-lookup"><span data-stu-id="c2de0-179">If the Conversation Reconstruction job fails, you can rerun the conversion job by clicking **Action > Create conversation PDFs** in the review set.</span></span>


#### <a name="exporting-conversations"></a><span data-ttu-id="c2de0-180">导出对话</span><span class="sxs-lookup"><span data-stu-id="c2de0-180">Exporting conversations</span></span>

<span data-ttu-id="c2de0-181">在对话审阅集中, 您可以设置以下选项以导出对话:</span><span class="sxs-lookup"><span data-stu-id="c2de0-181">In a conversation review set, you can set the following options to export conversations:</span></span>

![导出](../media/export.png)

<span data-ttu-id="c2de0-183">a.</span><span class="sxs-lookup"><span data-stu-id="c2de0-183">a.</span></span> <span data-ttu-id="c2de0-184">元数据选项</span><span class="sxs-lookup"><span data-stu-id="c2de0-184">Metadata options</span></span>

   - <span data-ttu-id="c2de0-185">**加载文件:** 每个单独的邮件、电子邮件和文档包含元数据。</span><span class="sxs-lookup"><span data-stu-id="c2de0-185">**Load file:** Metadata is included for each individual message, email, and document.</span></span> <span data-ttu-id="c2de0-186">会话中的每个邮件都有一行。</span><span class="sxs-lookup"><span data-stu-id="c2de0-186">There is one row for each message in a conversation.</span></span> 

   - <span data-ttu-id="c2de0-187">**标记:** 您的审阅过程中的标记包含在元数据文件中。</span><span class="sxs-lookup"><span data-stu-id="c2de0-187">**Tags:** Tags from your review process are included in the metadata file.</span></span> <span data-ttu-id="c2de0-188">对话中的邮件共享相同的标签。</span><span class="sxs-lookup"><span data-stu-id="c2de0-188">Messages in a conversation share the same tags.</span></span> 

<span data-ttu-id="c2de0-189">b.</span><span class="sxs-lookup"><span data-stu-id="c2de0-189">b.</span></span> <span data-ttu-id="c2de0-190">对话选项</span><span class="sxs-lookup"><span data-stu-id="c2de0-190">Conversation options</span></span>
  
   - <span data-ttu-id="c2de0-191">**对话文件:** 当您导出对话文件时, 批注视图将转换为 PDF 文件, 并下载到导出文件夹。</span><span class="sxs-lookup"><span data-stu-id="c2de0-191">**Conversation files:** When you export conversation files, the annotated view is converted to a PDF file and downloaded to the export folder.</span></span> <span data-ttu-id="c2de0-192">一个会话文件中的邮件指向同一个对话文件的 PDF 版本。</span><span class="sxs-lookup"><span data-stu-id="c2de0-192">Messages in one conversation file point to the PDF version of the same conversation file.</span></span>  
  
   - <span data-ttu-id="c2de0-193">**个人聊天消息:** 导出单个邮件时, 会将对话中的每个唯一邮件导出为独立的项目。</span><span class="sxs-lookup"><span data-stu-id="c2de0-193">**Individual chat messages:** When you export individual messages, each unique message in the conversation is exported as a standalone item.</span></span> <span data-ttu-id="c2de0-194">将导出文件, 其格式与在邮箱中保存时的格式相同。</span><span class="sxs-lookup"><span data-stu-id="c2de0-194">The file is exported in the same format that it was saved as in the mailbox.</span></span> <span data-ttu-id="c2de0-195">对于特定对话, 您将收到多个 .msg 文件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-195">For a specific conversation, you receive multiple .msg files.</span></span> 

     >[!NOTE]
     > <span data-ttu-id="c2de0-196">如果对对话文件应用了批注, 则不会将这些批注转移到各个邮件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-196">If you applied annotations to the conversation file, these annotations won't be transferred to the individual messages.</span></span> 

<span data-ttu-id="c2de0-197">c.</span><span class="sxs-lookup"><span data-stu-id="c2de0-197">c.</span></span> <span data-ttu-id="c2de0-198">其他选项</span><span class="sxs-lookup"><span data-stu-id="c2de0-198">Other options</span></span>

   - <span data-ttu-id="c2de0-199">**为所有导出的内容生成文本文件:** 为从评审集导出的每个对话生成一个文本文件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-199">**Generate text files for all exported content:** Generates a text file for each conversation exported from the review set.</span></span> 

   - <span data-ttu-id="c2de0-200">将**导出的内容替换为编辑 pdf:** 如果在审阅过程中生成编辑对话文件, 则这些文件在导出过程中可用。</span><span class="sxs-lookup"><span data-stu-id="c2de0-200">**Replace exported content with redacted PDFs:** If redacted conversation files are generated during the review process, then these files are available during export.</span></span> <span data-ttu-id="c2de0-201">您可以决定是仅导出本机文件 (不选择此选项), 还是将本机文件替换为本机文件的编辑版本 (选择此选项), 这些文件将导出为 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="c2de0-201">You can decided whether to export only the native files (by not selecting this option) or to replace the native files with the redacted versions of the native files (by selecting this option), which are exported as PDF files.</span></span>

## <a name="more-information"></a><span data-ttu-id="c2de0-202">更多信息</span><span class="sxs-lookup"><span data-stu-id="c2de0-202">More information</span></span>

<span data-ttu-id="c2de0-203">若要了解有关如何在高级电子数据展示中查看事例数据的详细信息, 请参阅以下文章:</span><span class="sxs-lookup"><span data-stu-id="c2de0-203">To learn more about how to review case data in Advanced eDiscovery, see the following articles:</span></span>

- [<span data-ttu-id="c2de0-204">查看事例数据</span><span class="sxs-lookup"><span data-stu-id="c2de0-204">View case data</span></span>](view-documents-in-review-set.md) 

- [<span data-ttu-id="c2de0-205">分析事例数据</span><span class="sxs-lookup"><span data-stu-id="c2de0-205">Analyze case data</span></span>](analyzing-data-in-review-set.md)

- [<span data-ttu-id="c2de0-206">导出事例数据</span><span class="sxs-lookup"><span data-stu-id="c2de0-206">Export case data</span></span>](exporting-data-ediscover20.md)
