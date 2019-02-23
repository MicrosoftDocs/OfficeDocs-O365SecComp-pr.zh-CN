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
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍了如何使用 Office 365 Security & 合规中心中的新数据调查 (预览版) 工具管理数据外泄事件。
ms.openlocfilehash: 93cbbed8763f0af31ab8d4e32348f01bfda17a2a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218122"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="7d653-103">在 Microsoft 365 中管理数据外泄事件</span><span class="sxs-lookup"><span data-stu-id="7d653-103">Manage a data spillage incident in Microsoft 365</span></span> 

<span data-ttu-id="7d653-p101">数据外泄是将机密文档发布到不受信任的环境时。检测到 data 外泄事件时, 务必要快速评估外泄的大小和位置, 检查其周围的用户活动, 然后从系统中永久清除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="7d653-p101">Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it, and then permanently purge the spilled data from the system.</span></span>

## <a name="scope-of-this-article"></a><span data-ttu-id="7d653-106">本文的范围</span><span class="sxs-lookup"><span data-stu-id="7d653-106">Scope of this article</span></span>

<span data-ttu-id="7d653-107">本文提供了有关如何从 Office 365 邮箱中永久删除项目, 以便用户或管理员无法再访问或恢复这些项目的说明的列表。</span><span class="sxs-lookup"><span data-stu-id="7d653-107">This article provides a list of instructions on how to permanently remove items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="7d653-108">删除位于 SharePoint 或 OneDrive for business 网站中的项目时, 它们将在从其原始位置删除它们的时间内保留93天。</span><span class="sxs-lookup"><span data-stu-id="7d653-108">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="7d653-109">方案</span><span class="sxs-lookup"><span data-stu-id="7d653-109">Scenario</span></span>

<span data-ttu-id="7d653-p102">您会收到一条数据外泄事件, 其中员工在不知情的情况下通过电子邮件与多个人共享高度机密的文档。您希望快速评估在您的组织内部和外部收到此文档的用户。在调查事件之后, 您计划与其他调查人员共享您的发现以进行查看, 然后从 Office 365 中永久删除溢出的数据。调查完成后, 您想要删除所有证据。</span><span class="sxs-lookup"><span data-stu-id="7d653-p102">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email. You want to quickly assess who received this document, both inside and outside of your organization. After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from Office 365. After the investigation is complete, you want to remove all evidence.</span></span> 

## <a name="workflow"></a><span data-ttu-id="7d653-114">工作流</span><span class="sxs-lookup"><span data-stu-id="7d653-114">Workflow</span></span>

<span data-ttu-id="7d653-115">以下是使用数据调查 (预览版) 管理数据外泄事件的工作流:</span><span class="sxs-lookup"><span data-stu-id="7d653-115">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="7d653-116">创建数据调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-116">Create a data investigation.</span></span>

2.  <span data-ttu-id="7d653-117">搜索溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="7d653-117">Search for the spilled data.</span></span>

3.  <span data-ttu-id="7d653-118">查看并调查事件。</span><span class="sxs-lookup"><span data-stu-id="7d653-118">Review and investigate the incident.</span></span>

4.  <span data-ttu-id="7d653-119">永久删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="7d653-119">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="7d653-120">关闭或删除调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-120">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="7d653-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="7d653-121">Before you begin</span></span>

- <span data-ttu-id="7d653-p103">您将使用 Office 365 安全 & 合规中心中的 "数据调查 (预览)" 工具创建调查, 搜索溢出的数据, 并对其进行查看和分析。然后, 使用安全 & 合规性中心 PowerShell 从 Office 365 中永久删除溢出的数据。</span><span class="sxs-lookup"><span data-stu-id="7d653-p103">You'll use the Data Investigations (Preview) tool in the Office 365 Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it. Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="7d653-124">若要创建调查, 您必须是 Security & 合规性中心中合规性管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="7d653-124">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="7d653-p104">若要删除邮件, 您必须是 Security & 合规性中心中的 "组织管理" 角色组的成员, 或者分配有 "搜索和清除" 角色。有关向角色组添加用户的信息, 请参阅[为用户提供对安全 & 合规性中心的访问权限](../grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p104">To delete messages, you have to be a member of the Organization Management role group in the Security & Compliance Center or be assigned the Search and Purge role. For information about adding users to a role group, see [Give users access to the Security & Compliance Center](../grant-access-to-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="7d653-p105">若要控制调查人员可以搜索哪些用户邮箱和 OneDrive 帐户, 您的组织可以设置合规性边界。有关详细信息, 请为[电子数据展示调查设置合规性边界](../set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p105">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries. For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="7d653-129">步骤 1: 创建数据调查</span><span class="sxs-lookup"><span data-stu-id="7d653-129">Step 1: Create a data investigation</span></span>

<span data-ttu-id="7d653-130">若要创建数据调查, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="7d653-130">To create a data investigation:</span></span>

1. <span data-ttu-id="7d653-131">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="7d653-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="7d653-132">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7d653-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="7d653-133">在安全 & 合规性中心中, 单击 "**数据调查**"。</span><span class="sxs-lookup"><span data-stu-id="7d653-133">In the Security & Compliance Center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="7d653-134">在 "**数据调查 (预览)** " 页上, 单击 "**创建新调查**"。</span><span class="sxs-lookup"><span data-stu-id="7d653-134">On the **Data Investigations (Preview)** page, click **Create a new investigation**.</span></span>
    
5. <span data-ttu-id="7d653-p106">在 "**新建数据调查**" 飞出页面上, 将调查命名为 "(必需)", 然后键入可选调查编号和说明。请注意, 该名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7d653-p106">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description. Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="7d653-137">在 "是否要在**创建此调查后配置其他设置？**" 下, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="7d653-137">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="7d653-p107">单击 **"是"** 创建调查, 并在新事例中显示 "**设置**" 页。这样, 您就可以将成员添加到调查中。</span><span class="sxs-lookup"><span data-stu-id="7d653-p107">Click **Yes** to create the investigation, and display the **Settings** page in the new case. This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="7d653-p108">单击 "**否**" 仅创建调查并将其显示在 "**数据调查 (预览)** " 页上的事例列表中。如果选择此选项, 则将作为调查的唯一成员添加, 并且将使用默认搜索和分析设置。您可以在创建调查之后随时添加成员或更改设置。</span><span class="sxs-lookup"><span data-stu-id="7d653-p108">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page. If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used. You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="7d653-143">单击 "**保存**" 以创建调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-143">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="7d653-144">新调查显示在 "**数据调查 (预览)** " 页面上的列表中。</span><span class="sxs-lookup"><span data-stu-id="7d653-144">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="7d653-145">若要打开调查, 请单击调查的名称。</span><span class="sxs-lookup"><span data-stu-id="7d653-145">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="7d653-146">将显示调查的 "**主页**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7d653-146">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="7d653-147">考虑建立调查的命名约定, 并在名称和说明中提供尽可能多的信息, 以便在将来需要时可以找到并参考。</span><span class="sxs-lookup"><span data-stu-id="7d653-147">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="7d653-148">步骤 2: 搜索溢出的数据</span><span class="sxs-lookup"><span data-stu-id="7d653-148">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="7d653-p109">如果您知道要在哪些用户中搜索溢出的数据, 则可以将其添加为感兴趣的人, 以将他们的数据源映射到调查并快速搜索其邮箱和 OneDrive 帐户。若要添加调查的相关人员, 请单击 "**感兴趣的人员**", 然后单击 "**添加感兴趣的人员**"。</span><span class="sxs-lookup"><span data-stu-id="7d653-p109">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account. To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> 

<span data-ttu-id="7d653-p110">在 "**搜索**" 选项卡上, 您可以创建搜索以查找溢出的数据。您将使用用于查找溢出数据的搜索查询, 以在[步骤 4](##step-4:-permanently-delete-the-spilled-data)中删除这些相同的邮件。有关创建搜索的详细信息, 请参阅[创建搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p110">On the **Searches** tab, you can create searches to find the spilled data. You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](##step-4:-permanently-delete-the-spilled-data). For more information about creating searches, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="7d653-p111">运行搜索后, 可以预览搜索结果的示例并查看搜索统计信息, 以评估搜索查询的有效性。确定要从 Office 365 中删除的项目后, 可以单击 "**事件**" 选项卡, 然后创建一个事件并添加包含这些项目的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="7d653-p111">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query. Once you identify the items that you want to delete from Office 365, you can click the **Incidents** tab, and then create an incident and add search results that contain those items.</span></span> 

<span data-ttu-id="7d653-p112">若要执行此操作, 请单击要调查的搜索。在弹出页面上, 单击 "**将结果添加到事件**", 然后按照说明操作。然后, 在事件中, 可以查看各个文档、调查谁有权访问文档以及导出文档。若要仅删除文档而不是查看文档, 请转到[步骤 4](##step-4:-permanently-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p112">To do this, click the search that you want to investigate. On the flyout page, click **Add results to incident** and follow the instructions. Then in the incident, you can review individual documents, investigate who had access to documents, and export the documents. To simply delete the documents instead of reviewing them, go to [Step 4](##step-4:-permanently-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="7d653-p113">您在搜索查询中使用的关键字可能包含要搜索的实际溢出数据。例如, 如果您搜索包含社会保险号码的文档, 并将其用作搜索查询中的关键字, 则必须随后删除该查询以避免进一步外泄。您可以在[步骤 5](##step-5:-close-or-delete-investigation)中删除搜索或删除整个调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-p113">The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage. You can delete search or delete the entire investigation in [Step 5](##step-5:-close-or-delete-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="7d653-163">步骤 3: 审阅和调查</span><span class="sxs-lookup"><span data-stu-id="7d653-163">Step 3: Review and investigate</span></span> 

<span data-ttu-id="7d653-p114">在调查中, 转到 "**事件**" 选项卡, 然后单击您在上一步中创建的事件。完成处理作业并将搜索结果添加到事件后, 可以查看以本机格式、文本格式或接近本机格式的单个文档。您可以创建其他查询来进一步缩小文档列表的范围, 并标记文档以指示调查中的结果。</span><span class="sxs-lookup"><span data-stu-id="7d653-p114">In the investigation, go to **Incidents** tab and click on the incident that you created in the previous step. After the processing job is completed and the search results are added to the incident, you can review individual documents in their native format, text format, or a near-native format. You can create additional queries to further narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span>

<span data-ttu-id="7d653-p115">若要对文档进行分组并获取更多的审阅帮助, 请单击 "**管理事件**"。在**分析**磁贴中, 单击 "**分析**"。这将运行高级分析, 例如重复检测、电子邮件线程和主题分析。有关详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="7d653-p115">To group documents and get more assistance for your review, click **Manage incident**. In the **Analytics** tile, click **Analyze**. This will run advanced analytics such as duplicate detection, email threading, and theme analysis. For more information, see:</span></span>

- [<span data-ttu-id="7d653-171">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="7d653-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="7d653-172">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="7d653-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="7d653-173">主题</span><span class="sxs-lookup"><span data-stu-id="7d653-173">Themes</span></span>](themes.md)

<span data-ttu-id="7d653-p116">若要确定数据外泄中涉及哪些用户, 可以在事件中创建一个新查询, 然后使用发件人/作者和收件人条件。这将创建在已添加到事件中的已收集数据中找到的所有发件人、收件人和作者的列表。请务必检查列表以确定列表中是否有任何外部用户。有关详细信息, 请参阅[搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p116">To determine which users are involved in the data spillage, you can create a new query in the incident and then use the Sender/Author and Recipients conditions. This will create a list of all senders, recipients and authors found in collected data that was added to the incident. Be sure to examine the list to determine if there are any external users in the list. For more information, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-permanently-delete-the-spilled-data"></a><span data-ttu-id="7d653-178">步骤 4: 永久删除溢出的数据</span><span class="sxs-lookup"><span data-stu-id="7d653-178">Step 4: Permanently delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="7d653-179">删除邮箱项目</span><span class="sxs-lookup"><span data-stu-id="7d653-179">Deleting mailbox items</span></span>

<span data-ttu-id="7d653-p117">在您查看并验证搜索结果只包含必须删除的电子邮件后, 您可以通过在安全 & 合规性中运行**new-compliancesearchaction-PurgeType HardDelete**命令来永久删除它们。Center PowerShell。有关说明, 请参阅[搜索和删除电子邮件](../search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p117">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell. For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="7d653-p118">请注意, 如果为组织中的邮箱启用了单个项目恢复, 则永久删除的项目将保留在用户的 "可恢复的项目" 文件夹中 (并由管理员访问), 直到已删除项目的保留期结束 (默认为14天)。此外, 如果包含溢出数据的任何邮箱处于合法保留或分配给保留策略, 则清除的邮件将保留在 "可恢复的项目" 文件夹中, 直到删除保留或邮箱从保留策略中排除。若要立即删除邮件, 您需要执行添加任务。有关说明, 请参阅[在保留时, 删除基于云的邮箱的 "可恢复的项目" 文件夹中的项目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p118">Note that if single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (default is 14 days). Additionally, if any of the mailboxes that contain spilled data are on a legal hold or assigned to a retention policy, purged message will be retained in Recoverable items folder until the hold is removed or the mailbox is excluded from retention policies. To hard delete messages immediately, you need to perform addition tasks. For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="7d653-p119">在删除保留策略或保留策略之前, 请与您的记录管理或法律部门进行确认。您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。</span><span class="sxs-lookup"><span data-stu-id="7d653-p119">Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="7d653-188">删除网站项</span><span class="sxs-lookup"><span data-stu-id="7d653-188">Deleting site items</span></span>

<span data-ttu-id="7d653-p120">若要从 SharePoint 网站或 OneDrive for business 帐户中永久删除文档, 必须将其删除, 然后必须从网站中删除该文档, 然后再将其从网站集回收站中删除。有关说明, 请参阅[删除 SharePoint 和 OneDrive 中的文档](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p120">To permanently delete a document from a SharePoint site or OneDrive for Business account, you have to delete it and then you have to delete from the site and then delete it from the site collection Recycle Bin. For instructions, see [Delete documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="7d653-p121">或者, 您可以删除可能包含溢出数据的整个网站集。有关说明, 请参阅[删除网站集](https://docs.microsoft.com/sharepoint/delete-site-collection)。</span><span class="sxs-lookup"><span data-stu-id="7d653-p121">Alternatively, you can delete an entire site collection that might contained spilled data. For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="7d653-193">步骤 5: 关闭或删除调查</span><span class="sxs-lookup"><span data-stu-id="7d653-193">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="7d653-p122">删除源内容位置 (邮箱或网站) 中的文档后, 您仍将拥有您在调查过程中添加到事件的这些文档的副本。若要避免进一步的数据外泄, 应考虑删除调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-p122">After you delete documents in the source content locations (mailboxes or sites), you will still have copies of these documents that you added to incidents as part of your investigation. To avoid further data spillage, you should consider deleting the investigation.</span></span>

<span data-ttu-id="7d653-196">若要删除调查, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="7d653-196">To delete an investigation:</span></span>

1. <span data-ttu-id="7d653-197">在 "**设置**" 选项卡上, 单击 "**调查信息**"。</span><span class="sxs-lookup"><span data-stu-id="7d653-197">On the **Settings** tab, click **Investigation information**.</span></span>

2. <span data-ttu-id="7d653-198">单击 "**删除大小写**"。</span><span class="sxs-lookup"><span data-stu-id="7d653-198">Click  **Delete case**.</span></span> 

<span data-ttu-id="7d653-p123">如果不需要删除调查, 或者要保存在调查过程中收集的信息, 则可以单击 "**关闭事例**"。稍后, 您可以重新打开已关闭的调查。</span><span class="sxs-lookup"><span data-stu-id="7d653-p123">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**. At a later date, you can re-open closed investigations.</span></span>