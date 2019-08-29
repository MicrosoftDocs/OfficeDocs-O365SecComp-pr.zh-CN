---
title: 在 Microsoft 365 中管理数据外泄事件
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
description: 本文介绍了如何使用安全 & 合规中心中的新数据调查 (预览版) 工具管理数据外泄事件。
ms.openlocfilehash: 93199ad1f548e999dce9ad79ab311a57345b8772
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649919"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="1872e-103">在 Microsoft 365 中管理数据外泄事件</span><span class="sxs-lookup"><span data-stu-id="1872e-103">Manage a data spillage incident in Microsoft 365</span></span>

<span data-ttu-id="1872e-104">数据外泄是在不受信任的环境中发布包含机密、敏感或恶意信息的文档时。</span><span class="sxs-lookup"><span data-stu-id="1872e-104">Data spillage is when a document containing confidential, sensitive, or malicious information is released in an untrusted environment.</span></span> <span data-ttu-id="1872e-105">检测到 data 外泄事件时, 重要的是要快速包含环境、评估外泄的大小和位置、检查其周围的用户活动, 然后从服务中删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-105">When a data spillage incident is detected, it's important to quickly contain the environment, assess the size and locations of the spillage, examine user activities around it, and then delete the spilled data from the service.</span></span> <span data-ttu-id="1872e-106">使用 "数据调查 (预览)" 工具, 您可以在 Office 365 中搜索敏感、恶意或误放的数据, 调查以了解所发生的情况, 然后采取相应的操作。</span><span class="sxs-lookup"><span data-stu-id="1872e-106">Using the Data Investigations (Preview) tool, you can search for sensitive, malicious, or misplaced data across Office 365, investigate to find out what happened, and then take appropriate actions.</span></span>  

## <a name="scope-of-this-article"></a><span data-ttu-id="1872e-107">本文的范围</span><span class="sxs-lookup"><span data-stu-id="1872e-107">Scope of this article</span></span>

<span data-ttu-id="1872e-108">本文提供了有关如何从 Office 365 邮箱中永久删除项目的说明列表, 以便用户或管理员无法再访问或恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-108">This article provides a list of instructions on how to permanently delete items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="1872e-109">删除位于 SharePoint 或 OneDrive for business 网站中的项目时, 它们将在从其原始位置删除它们的时间内保留93天。</span><span class="sxs-lookup"><span data-stu-id="1872e-109">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="1872e-110">应用场景</span><span class="sxs-lookup"><span data-stu-id="1872e-110">Scenario</span></span>

<span data-ttu-id="1872e-111">您会收到一条数据外泄事件, 其中员工在不知情的情况下通过电子邮件与多个人共享高度机密文档。</span><span class="sxs-lookup"><span data-stu-id="1872e-111">You're informed of a data spillage incident where an employee unknowingly shared a highly confidential document with multiple people through email.</span></span> <span data-ttu-id="1872e-112">您希望快速评估在您的组织内部和外部收到此文档的用户。</span><span class="sxs-lookup"><span data-stu-id="1872e-112">You want to quickly assess who received this document, both inside and outside of your organization.</span></span> <span data-ttu-id="1872e-113">在调查事件之后, 您计划与其他调查人员共享您的发现以进行查看, 然后从 Office 365 组织中永久删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-113">After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from your Office 365 organization.</span></span> <span data-ttu-id="1872e-114">调查完成后, 您想要删除所有证据。</span><span class="sxs-lookup"><span data-stu-id="1872e-114">After the investigation is complete, you want to remove all evidence.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1872e-115">虽然您能够在自己的组织中永久删除溢出的数据, 但不能使用这些功能删除任何溢出组织外部的数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-115">While you'll be able to permanently remove the spilled data within your own organization, any data spilled outside your organization can't be removed with these capabilities.</span></span>

## <a name="workflow"></a><span data-ttu-id="1872e-116">工作流</span><span class="sxs-lookup"><span data-stu-id="1872e-116">Workflow</span></span>

<span data-ttu-id="1872e-117">以下是使用数据调查 (预览版) 管理数据外泄事件的工作流:</span><span class="sxs-lookup"><span data-stu-id="1872e-117">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="1872e-118">创建数据调查。</span><span class="sxs-lookup"><span data-stu-id="1872e-118">Create a data investigation.</span></span>

2.  <span data-ttu-id="1872e-119">搜索敏感、恶意或放错位置的数据, 并将其作为证据收集。</span><span class="sxs-lookup"><span data-stu-id="1872e-119">Search for sensitive, malicious, or misplaced data and collect them as evidence.</span></span>

3.  <span data-ttu-id="1872e-120">查看并调查证据。</span><span class="sxs-lookup"><span data-stu-id="1872e-120">Review and investigate the evidence.</span></span>

4.  <span data-ttu-id="1872e-121">永久删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-121">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="1872e-122">关闭或删除调查。</span><span class="sxs-lookup"><span data-stu-id="1872e-122">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="1872e-123">开始之前</span><span class="sxs-lookup"><span data-stu-id="1872e-123">Before you begin</span></span>

- <span data-ttu-id="1872e-124">若要创建数据调查、搜索内容和删除溢出的数据, 您必须是 Security & 合规性中心中的 "数据调查员" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="1872e-124">To create a data investigation, search for content, and delete spilled data, you have to be a member of the Data Investigator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="1872e-125">若要控制调查人员可以搜索哪些用户邮箱和 OneDrive 帐户, 您的组织可以设置合规性边界。</span><span class="sxs-lookup"><span data-stu-id="1872e-125">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries.</span></span> <span data-ttu-id="1872e-126">有关详细信息, 请为[电子数据展示调查设置合规性边界](../set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="1872e-126">For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="1872e-127">步骤 1: 创建数据调查</span><span class="sxs-lookup"><span data-stu-id="1872e-127">Step 1: Create a data investigation</span></span>

<span data-ttu-id="1872e-128">若要在数据调查 (预览) 工具中创建调查, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1872e-128">To create an investigation in the Data Investigations (Preview) tool:</span></span>

1. <span data-ttu-id="1872e-129">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="1872e-129">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="1872e-130">使用属于数据调查员角色组成员的帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1872e-130">Sign in to Office 365 using an account that is a member of the Data Investigator role group.</span></span>
    
3. <span data-ttu-id="1872e-131">在 "安全与合规中心" 中, 单击 "**数据调查**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-131">In the security and compliance center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="1872e-132">在 "**数据调查 (预览)** " 页上, 单击 "**创建新调查**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-132">On the **Data Investigations (Preview)** page, click **Create new investigation**.</span></span>
    
5. <span data-ttu-id="1872e-133">在 "**新建数据调查**" 飞出页面上, 将调查命名为 "(必需)", 然后键入可选调查编号和说明。</span><span class="sxs-lookup"><span data-stu-id="1872e-133">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description.</span></span> <span data-ttu-id="1872e-134">名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1872e-134">The name must be unique in your organization.</span></span>

6. <span data-ttu-id="1872e-135">在 "是否要在**创建此调查后配置其他设置？**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="1872e-135">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="1872e-136">单击 **"是"** 创建调查, 并在新事例中显示 "**设置**" 页。</span><span class="sxs-lookup"><span data-stu-id="1872e-136">Click **Yes** to create the investigation, and display the **Settings** page in the new case.</span></span> <span data-ttu-id="1872e-137">这样, 您就可以将成员添加到调查中。</span><span class="sxs-lookup"><span data-stu-id="1872e-137">This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="1872e-138">单击 "**否**" 以创建调查并将其显示在 "**数据调查 (预览)** " 页面上的事例列表中。</span><span class="sxs-lookup"><span data-stu-id="1872e-138">Click **No** to create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page.</span></span> <span data-ttu-id="1872e-139">如果选择此选项, 则将作为调查的唯一成员添加, 并且将使用默认搜索和分析设置。</span><span class="sxs-lookup"><span data-stu-id="1872e-139">If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used.</span></span> <span data-ttu-id="1872e-140">创建调查后随时可以添加成员或更改设置。</span><span class="sxs-lookup"><span data-stu-id="1872e-140">You can add members or change settings anytime after the investigation is created.</span></span>

7. <span data-ttu-id="1872e-141">单击 "**保存**" 以创建调查。</span><span class="sxs-lookup"><span data-stu-id="1872e-141">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="1872e-142">新调查显示在 "**数据调查 (预览)** " 页面上的列表中。</span><span class="sxs-lookup"><span data-stu-id="1872e-142">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="1872e-143">若要打开调查, 请单击调查的名称。</span><span class="sxs-lookup"><span data-stu-id="1872e-143">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="1872e-144">将显示调查的 "**主页**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1872e-144">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="1872e-145">考虑建立调查的命名约定, 并在名称和说明中提供尽可能多的信息, 以便将来可以找到这些信息并对其进行引用 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="1872e-145">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to them in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="1872e-146">步骤 2: 搜索溢出的数据</span><span class="sxs-lookup"><span data-stu-id="1872e-146">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="1872e-147">如果您知道要在哪些用户中搜索溢出的数据, 则可以将其添加为感兴趣的人, 以将他们的数据源映射到调查并快速搜索其邮箱和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="1872e-147">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account.</span></span> <span data-ttu-id="1872e-148">若要添加调查的相关人员, 请单击 "**感兴趣的人员**", 然后单击 "**添加感兴趣的人员**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-148">To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> <span data-ttu-id="1872e-149">有关详细信息, 请参阅[管理感兴趣的人员](manage-people-of-interest.md)。</span><span class="sxs-lookup"><span data-stu-id="1872e-149">For more information, see [Manage people of interest](manage-people-of-interest.md).</span></span>

<span data-ttu-id="1872e-150">在 "**搜索**" 选项卡上, 您可以创建搜索以查找溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-150">On the **Searches** tab, you can create searches to find the spilled data.</span></span> <span data-ttu-id="1872e-151">有关创建搜索的详细信息, 请参阅[在调查中搜索数据](search-for-data.md)。</span><span class="sxs-lookup"><span data-stu-id="1872e-151">For more information about creating searches, see [Search for data in an investigation](search-for-data.md).</span></span>

<span data-ttu-id="1872e-152">运行搜索后, 可以预览搜索结果的示例并查看搜索统计信息, 以评估搜索查询的有效性。</span><span class="sxs-lookup"><span data-stu-id="1872e-152">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query.</span></span> <span data-ttu-id="1872e-153">在确定要从 Office 365 中删除的项目后, 可以将搜索结果添加到证据集。</span><span class="sxs-lookup"><span data-stu-id="1872e-153">After you identify the items that you want to delete from Office 365, you can add the search results to an evidence set.</span></span> <span data-ttu-id="1872e-154">若要执行此操作, 请单击要调查的搜索。</span><span class="sxs-lookup"><span data-stu-id="1872e-154">To do this, click the search that you want to investigate.</span></span> <span data-ttu-id="1872e-155">在弹出页面上, 单击 "**将结果添加到证据**" 并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="1872e-155">On the flyout page, click **Add results to evidence** and follow the instructions.</span></span> <span data-ttu-id="1872e-156">然后, 在证据集中, 您可以查看各个文档、调查谁有权访问文档以及导出文档。</span><span class="sxs-lookup"><span data-stu-id="1872e-156">Then in the evidence set, you can review individual documents, investigate who had access to documents, and export the documents.</span></span> <span data-ttu-id="1872e-157">若要删除文档 (或文档的子集) 而不是查看它们, 请转到[步骤 4](#step-4-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="1872e-157">To delete the documents (or a subset of documents) instead of reviewing them, go to [Step 4](#step-4-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1872e-158">您在搜索查询中使用的关键字可能包含要搜索的实际溢出数据。</span><span class="sxs-lookup"><span data-stu-id="1872e-158">The keywords that you use in the search query may contain the actual spilled data that you're searching for.</span></span> <span data-ttu-id="1872e-159">例如, 如果搜索包含社会保险号码的文档, 并将其用作搜索查询中的关键字, 则必须随后删除该查询以避免进一步外泄。</span><span class="sxs-lookup"><span data-stu-id="1872e-159">For example, if you search for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage.</span></span> <span data-ttu-id="1872e-160">您可以删除搜索或删除[步骤 5](#step-5-close-or-delete-the-investigation)中的整个调查。</span><span class="sxs-lookup"><span data-stu-id="1872e-160">You can delete the search or delete the entire investigation in [Step 5](#step-5-close-or-delete-the-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="1872e-161">步骤 3: 审阅和调查</span><span class="sxs-lookup"><span data-stu-id="1872e-161">Step 3: Review and investigate</span></span> 

<span data-ttu-id="1872e-162">在调查中, 转到 "**证据**" 选项卡, 然后单击您在上一步中创建的证据集。</span><span class="sxs-lookup"><span data-stu-id="1872e-162">In the investigation, go to the **Evidence** tab and click the evidence set that you created in the previous step.</span></span> <span data-ttu-id="1872e-163">完成处理作业并将搜索结果添加到证据之后, 可以查看以本机格式、文本格式或接近本机格式的单个文档。</span><span class="sxs-lookup"><span data-stu-id="1872e-163">After the processing job is completed and the search results are added to the evidence, you can review individual documents in their native format, text format, or a near-native format.</span></span> <span data-ttu-id="1872e-164">您可以创建其他查询来缩小文档列表的范围, 并标记文档以指示调查中的结果。</span><span class="sxs-lookup"><span data-stu-id="1872e-164">You can create additional queries to narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span> <span data-ttu-id="1872e-165">有关详细信息, 请参阅[查看证据中的数据](review-data-in-evidence.md)</span><span class="sxs-lookup"><span data-stu-id="1872e-165">For more information, see [Review data in evidence](review-data-in-evidence.md)</span></span>

<span data-ttu-id="1872e-166">若要对文档进行分组并获取更多的审阅帮助, 请单击 "**管理证据**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-166">To group documents and get more assistance for your review, click **Manage evidence**.</span></span> <span data-ttu-id="1872e-167">在**分析**磁贴中, 单击 "**分析**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-167">In the **Analytics** tile, click **Analyze**.</span></span> <span data-ttu-id="1872e-168">这将运行高级分析, 例如重复检测、电子邮件线程和主题分析。</span><span class="sxs-lookup"><span data-stu-id="1872e-168">This runs advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="1872e-169">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1872e-169">For more information, see:</span></span>

- [<span data-ttu-id="1872e-170">运行分析功能，加快调查</span><span class="sxs-lookup"><span data-stu-id="1872e-170">Run analytics to investigate faster</span></span>](run-analytics-to-investigate-faster.md)
- [<span data-ttu-id="1872e-171">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="1872e-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="1872e-172">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="1872e-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="1872e-173">主题</span><span class="sxs-lookup"><span data-stu-id="1872e-173">Themes</span></span>](themes.md)

<span data-ttu-id="1872e-174">若要确定数据外泄中涉及哪些用户, 可以在证据集中创建一个查询, 然后使用发件人/作者和收件人条件。</span><span class="sxs-lookup"><span data-stu-id="1872e-174">To determine which users are involved in the data spillage, you can create a query in the evidence set and then use the Sender/Author and Recipients conditions.</span></span> <span data-ttu-id="1872e-175">这将创建在已添加到证据的收集数据中找到的所有发件人、收件人和作者的列表。</span><span class="sxs-lookup"><span data-stu-id="1872e-175">This creates a list of all senders, recipients, and authors found in collected data that was added to the evidence.</span></span> <span data-ttu-id="1872e-176">请务必检查列表以确定是否存在外部用户。</span><span class="sxs-lookup"><span data-stu-id="1872e-176">Be sure to examine the list to determine if there are any external users.</span></span> <span data-ttu-id="1872e-177">有关使用条件来缩小搜索结果范围的详细信息, 请参阅[搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="1872e-177">For more information about using conditions to narrow search results, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-delete-the-spilled-data"></a><span data-ttu-id="1872e-178">步骤 4: 删除溢出的数据</span><span class="sxs-lookup"><span data-stu-id="1872e-178">Step 4: Delete the spilled data</span></span>

<span data-ttu-id="1872e-179">使用数据调查工具, 您可以从其原始位置删除项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-179">Using the data investigations tool, you can delete items from their original locations.</span></span> <span data-ttu-id="1872e-180">例如, 您可以在组织中删除邮箱、SharePoint 网站和 OneDrive 帐户中的项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-180">For example, you can delete items from mailboxes, SharePoint sites, and OneDrive accounts across your organization.</span></span> <span data-ttu-id="1872e-181">请注意, 由于你将项目作为证据进行收集 (通过将搜索结果添加到步骤2中的证据集), 你具有证据集中项目的副本, 以进一步调查或保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-181">Keep in mind that because you collected items as evidence (by adding the search results to the evidence set in Step 2), you have copies of the items in the evidence set to further investigate or preserve them.</span></span>

<span data-ttu-id="1872e-182">若要从其原始位置删除项目, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1872e-182">To delete items from their original locations:</span></span>

1. <span data-ttu-id="1872e-183">在 "证据集" 中, 选择要删除的项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-183">In the evidence set, select the items that you want to delete.</span></span> <span data-ttu-id="1872e-184">如果选择附加到电子邮件的项目, 则会同时选择并删除父电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1872e-184">If you select items that are attached to an email message, the parent email message will also be selected and deleted.</span></span> 
 
2. <span data-ttu-id="1872e-185">单击 "**操作**", 然后单击 "**从原始位置删除项目**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-185">Click **Action** and then click **Delete items from original locations**.</span></span>

   ![单击 "操作", 然后单击 "从原始位置删除项目"](../media/DataInvestigationsDeleteItems1.png)

3. <span data-ttu-id="1872e-187">在弹出页面上, 验证要删除的项目和相关子文档的数目, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-187">On the flyout page, verify the number of items and related child documents that will be deleted, and then click **Delete**.</span></span>

<span data-ttu-id="1872e-188">目前, 当您从原始位置删除项目时, 这些项目会软删除。</span><span class="sxs-lookup"><span data-stu-id="1872e-188">At this time, when you delete items from their original location, the items are soft-deleted.</span></span> <span data-ttu-id="1872e-189">这意味着将保留已删除的项目, 直到项目的已删除邮件恢复期过期。</span><span class="sxs-lookup"><span data-stu-id="1872e-189">This means that the deleted items will be retained until the deleted item recovery period for the item expires.</span></span> <span data-ttu-id="1872e-190">这也意味着用户可以恢复这些项目。</span><span class="sxs-lookup"><span data-stu-id="1872e-190">This also means it's possible for users to recover these items.</span></span> <span data-ttu-id="1872e-191">有关从邮箱和网站删除项目时所发生情况的详细信息, 请参阅[删除其原始位置中的项目](delete-items-from-original-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="1872e-191">For more information about what happens when items are deleted from mailboxes and sites, see [Delete items from their original location](delete-items-from-original-locations.md).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="1872e-192">步骤 5: 关闭或删除调查</span><span class="sxs-lookup"><span data-stu-id="1872e-192">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="1872e-193">在 live service 中删除源内容位置 (邮箱或网站) 中的文档后, 您仍将拥有在调查过程中添加到证据的这些文档的副本。</span><span class="sxs-lookup"><span data-stu-id="1872e-193">After you delete documents in the source content locations (mailboxes or sites) in the live service, you will still have copies of these documents that you added to evidence as part of your investigation.</span></span> <span data-ttu-id="1872e-194">若要避免进一步的数据外泄, 应考虑删除调查本身。</span><span class="sxs-lookup"><span data-stu-id="1872e-194">To avoid further data spillage, you should consider deleting the investigation itself.</span></span>

<span data-ttu-id="1872e-195">若要删除调查, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="1872e-195">To delete an investigation:</span></span>

1. <span data-ttu-id="1872e-196">在 "**设置**" 选项卡上, 单击 "**调查信息**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-196">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="1872e-197">单击 "**删除调查**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-197">Click  **Delete investigation**.</span></span> 

<span data-ttu-id="1872e-198">如果不需要删除调查, 或者要保存在调查过程中收集的信息, 则可以单击 "**关闭事例**"。</span><span class="sxs-lookup"><span data-stu-id="1872e-198">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**.</span></span> <span data-ttu-id="1872e-199">稍后, 您可以重新打开已关闭的调查。</span><span class="sxs-lookup"><span data-stu-id="1872e-199">Then later, you can reopen closed investigations.</span></span>
