---
title: 管理 Microsoft 365 中的数据泄漏事件
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
description: 本文介绍如何使用 Office 365 安全性 & 合规性中心中新数据调查 （预览） 工具管理数据损耗情况事件。
ms.openlocfilehash: d863d87cc667b9695f9bf619c35575715dfa144e
ms.sourcegitcommit: 98ec28932ae20e848f9f489c3c78e4a7edab6d18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "29636610"
---
# <a name="managing-a-data-spillage-incident-in-microsoft-365"></a><span data-ttu-id="73660-103">管理 Microsoft 365 中的数据泄漏事件</span><span class="sxs-lookup"><span data-stu-id="73660-103">Managing a data spillage incident in Microsoft 365</span></span> 

<span data-ttu-id="73660-p101">机密文档发布到不受信任的环境时，数据泄漏。检测到数据泄漏事件时，务必快速评估的大小和位置的损耗情况、 检查周围的用户活动，然后在系统中永久清除溅入的数据。</span><span class="sxs-lookup"><span data-stu-id="73660-p101">Data spillage is when a confidential document is released into an untrusted environment. When a data spillage incident is detected, it's important to quickly assess the size and locations of the spillage, examine user activities around it, and then permanently purge the spilled data from the system.</span></span>

## <a name="scope-of-this-article"></a><span data-ttu-id="73660-106">本文的范围</span><span class="sxs-lookup"><span data-stu-id="73660-106">Scope of this article</span></span>

<span data-ttu-id="73660-107">本文提供有关如何从永久移除项 Office 365 邮箱，以使其无法再访问或由用户或管理员可恢复的说明的列表。</span><span class="sxs-lookup"><span data-stu-id="73660-107">This article provides a list of instructions on how to permanently remove items from Office 365 mailboxes so they are no longer accessible or recoverable by users or admins.</span></span> 

> [!NOTE]
> <span data-ttu-id="73660-108">如果删除项目位于中 SharePoint 或 OneDrive for Business 站点，他们将会保留 93 天从其原始位置从删除时间。</span><span class="sxs-lookup"><span data-stu-id="73660-108">When you delete items located in a SharePoint or OneDrive for Business site, they are retained for 93 days from the time you delete them from their original location.</span></span>

## <a name="scenario"></a><span data-ttu-id="73660-109">方案</span><span class="sxs-lookup"><span data-stu-id="73660-109">Scenario</span></span>

<span data-ttu-id="73660-p102">数据泄漏其中员工不知情的情况下共享的事件高度机密文档与多人通过电子邮件会通知您。您希望快速评估谁接收此组织内外的文档。您已调查事件后，您打算与其他调查员查看，，然后从 Office 365 永久移除溅入的数据共享您的发现。完成调查后，您想要删除所有证据。</span><span class="sxs-lookup"><span data-stu-id="73660-p102">You're informed of a data spillage incident where an employee unknowingly shared a highly-confidential document with multiple people through email. You want to quickly assess who received this document, both inside and outside of your organization. After you've investigate the incident, you plan to share your findings with other investigators to review, and then permanently remove the spilled data from Office 365. After the investigation is complete, you want to remove all evidence.</span></span> 

## <a name="workflow"></a><span data-ttu-id="73660-114">工作流</span><span class="sxs-lookup"><span data-stu-id="73660-114">Workflow</span></span>

<span data-ttu-id="73660-115">下面是使用数据调查 （预览） 来管理数据泄漏事件的工作流：</span><span class="sxs-lookup"><span data-stu-id="73660-115">Here's the workflow for using Data Investigations (Preview) to manage a data spillage incident:</span></span>

1.  <span data-ttu-id="73660-116">创建数据调查。</span><span class="sxs-lookup"><span data-stu-id="73660-116">Create a data investigation.</span></span>

2.  <span data-ttu-id="73660-117">搜索溅入数据。</span><span class="sxs-lookup"><span data-stu-id="73660-117">Search for the spilled data.</span></span>

3.  <span data-ttu-id="73660-118">查看并调查事件。</span><span class="sxs-lookup"><span data-stu-id="73660-118">Review and investigate the incident.</span></span>

4.  <span data-ttu-id="73660-119">永久删除溅入的数据。</span><span class="sxs-lookup"><span data-stu-id="73660-119">Permanently delete the spilled data.</span></span>

5.  <span data-ttu-id="73660-120">关闭或删除调查。</span><span class="sxs-lookup"><span data-stu-id="73660-120">Close or delete the investigation.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="73660-121">准备工作</span><span class="sxs-lookup"><span data-stu-id="73660-121">Before you begin</span></span>

- <span data-ttu-id="73660-p103">将使用在 Office 365 安全性 & 合规性中心数据调查 （预览） 工具创建调查、 搜索溅入的数据，并查看和对其进行分析。然后您将使用安全 & 合规性中心 PowerShell 从 Office 365 中永久删除溅入的数据。</span><span class="sxs-lookup"><span data-stu-id="73660-p103">You'll use the Data Investigations (Preview) tool in the Office 365 Security & Compliance Center to create an investigation, search for the spilled data, and review and analyze it. Then you'll use Security & Compliance Center PowerShell to permanently delete the spilled data from Office 365.</span></span> 

- <span data-ttu-id="73660-124">若要创建调查，您必须是安全 & 合规性中心中的合规性管理员角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="73660-124">To create an investigation, you have to be a member of the Compliance Administrator role group in the Security & Compliance Center.</span></span>

- <span data-ttu-id="73660-p104">若要删除的邮件，您必须是安全 & 合规性中心中的 Organization Management 角色组的成员，或者为其分配搜索和清除角色。有关将用户添加到角色组的信息，请参阅[授予用户对安全 & 合规中心的访问](../grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="73660-p104">To delete messages, you have to be a member of the Organization Management role group in the Security & Compliance Center or be assigned the Search and Purge role. For information about adding users to a role group, see [Give users access to the Security & Compliance Center](../grant-access-to-the-security-and-compliance-center.md).</span></span> 

- <span data-ttu-id="73660-p105">若要控制的用户邮箱和 OneDrive 帐户调查员可以搜索，您的组织可以设置合规性边界。有关详细信息，请参阅[设置电子数据展示调查的合规性边界](../set-up-compliance-boundaries.md)。</span><span class="sxs-lookup"><span data-stu-id="73660-p105">To control which user mailboxes and OneDrive accounts an investigator can search, your organization can set up compliance boundaries. For more information, [Set up compliance boundaries for eDiscovery investigations](../set-up-compliance-boundaries.md).</span></span> 

## <a name="step-1-create-a-data-investigation"></a><span data-ttu-id="73660-129">步骤 1： 创建数据调查</span><span class="sxs-lookup"><span data-stu-id="73660-129">Step 1: Create a data investigation</span></span>

<span data-ttu-id="73660-130">创建数据调查：</span><span class="sxs-lookup"><span data-stu-id="73660-130">To create a data investigation:</span></span>

1. <span data-ttu-id="73660-131">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="73660-131">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="73660-132">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="73660-132">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="73660-133">在安全 & 合规性中心中，单击**数据调查**。</span><span class="sxs-lookup"><span data-stu-id="73660-133">In the Security & Compliance Center, click **Data Investigations**.</span></span>
 
4. <span data-ttu-id="73660-134">在**数据调查 （预览）** 页上，单击**创建新的调查**。</span><span class="sxs-lookup"><span data-stu-id="73660-134">On the **Data Investigations (Preview)** page, click **Create a new investigation**.</span></span>
    
5. <span data-ttu-id="73660-p106">在**新数据调查**弹出页上，为调查指定一个名称 （必需）、，然后键入可选调查号和说明。请注意，必须在组织中的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="73660-p106">On the **New data investigation** flyout page, give the investigation a name (required), and then type an optional investigation number and description. Note that the name must be unique in your organization.</span></span>

6. <span data-ttu-id="73660-137">在**您想要创建此调查后配置其他设置？**，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="73660-137">Under **Do you want to configure additional settings after creating this investigation?**, do one of the following:</span></span>

    - <span data-ttu-id="73660-p107">单击**是**以创建调查，并在新的情况下显示**设置**页。这样，您将成员添加到调查。</span><span class="sxs-lookup"><span data-stu-id="73660-p107">Click **Yes** to create the investigation, and display the **Settings** page in the new case. This allows you to add members to the investigation.</span></span>
    
    - <span data-ttu-id="73660-p108">单击**否**刚创建调查，并显示在**数据调查 （预览）** 页上的情况下的列表中。如果您选择此选项，您将添加将使用调查和默认搜索和分析设置的唯一成员。您可以添加成员，或创建调查后随时更改设置。</span><span class="sxs-lookup"><span data-stu-id="73660-p108">Click **No** to just create the investigation and display it in the list of cases on the **Data Investigations (Preview)** page. If you choose this option, you will be added as the only member of the investigation and the default search and analytics settings will be used. You can add members or change settings any time after the investigation is created.</span></span>

7. <span data-ttu-id="73660-143">单击**保存**以创建调查。</span><span class="sxs-lookup"><span data-stu-id="73660-143">Click **Save** to create the investigation.</span></span>

    <span data-ttu-id="73660-144">在**数据调查 （预览）** 页上的列表中显示新的调查。</span><span class="sxs-lookup"><span data-stu-id="73660-144">The new investigation is displayed in the list on the **Data Investigations (Preview)** page.</span></span> 

8. <span data-ttu-id="73660-145">要打开调查，请单击调查的名称。</span><span class="sxs-lookup"><span data-stu-id="73660-145">To open an investigation, click the name of the investigation.</span></span> 

    <span data-ttu-id="73660-146">将显示调查的**主页**选项卡。</span><span class="sxs-lookup"><span data-stu-id="73660-146">The **Home** tab for the investigation is displayed.</span></span> 

> [!TIP]
> <span data-ttu-id="73660-147">请考虑建立调查的命名约定，并提供尽可能多的信息，您可以在名称和说明中，以便您可以找到并如有必要，以便将来参考。</span><span class="sxs-lookup"><span data-stu-id="73660-147">Consider establishing a naming convention for investigations and provide as much information as you can in the name and description so you can locate and refer to in the future if necessary.</span></span>
 
## <a name="step-2-search-for-the-spilled-data"></a><span data-ttu-id="73660-148">步骤 2： 搜索溅入数据</span><span class="sxs-lookup"><span data-stu-id="73660-148">Step 2: Search for the spilled data</span></span> 
 
<span data-ttu-id="73660-p109">如果您知道要搜索的溅入数据的用户，您可以为感兴趣的用户将其数据源映射到调查和快速搜索其邮箱和 OneDrive 帐户添加它们。若要添加到调查值得关注的人员，单击**值得关注的人员**，，然后单击**添加人员感兴趣的**。</span><span class="sxs-lookup"><span data-stu-id="73660-p109">If you know which users you want to search for spilled data, you can add them as people of interest to map their data sources to the investigation and quickly search their mailbox and OneDrive account. To add people of interest to the investigation, click **People of interest**, and then click **Add people of interest**.</span></span> 

<span data-ttu-id="73660-p110">在**搜索**选项卡，您可以创建搜索来查找溅入的数据。您将使用您用来查找要删除这些相同的[步骤 4](##step-4:-permanently-delete-the-spilled-data)中的邮件的溅入的数据的同一个搜索查询。有关创建搜索的详细信息，请参阅[Create 搜索以收集数据](create-search-to-collect-data.md)。</span><span class="sxs-lookup"><span data-stu-id="73660-p110">On the **Searches** tab, you can create searches to find the spilled data. You will use the same search query that you used to find the spilled data to delete those same messages in [Step 4](##step-4:-permanently-delete-the-spilled-data). For more information about creating searches, see [Create a search to collect data](create-search-to-collect-data.md).</span></span>

<span data-ttu-id="73660-p111">运行搜索后，您可以预览搜索结果以及查看搜索统计信息来评估您的搜索查询的有效性的示例。标识后您要从 Office 365 中删除的项目，您可以单击**事件**选项卡，然后创建一个事件，并添加包含这些项的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="73660-p111">After you run the search, you can preview samples of search results and view search statistics to evaluate the effectiveness of your search query. Once you identify the items that you want to delete from Office 365, you can click the **Incidents** tab, and then create an incident and add search results that contain those items.</span></span> 

<span data-ttu-id="73660-p112">若要执行此操作，单击您想要调查的搜索。在弹出页上，单击**添加到事件的结果**并按照说明进行操作。然后中事件，您可以查看各个文档、 调查曾访问文档，并导出文档。若要只删除而不是查看这些文档，请转到[步骤 4](##step-4:-permanently-delete-the-spilled-data)。</span><span class="sxs-lookup"><span data-stu-id="73660-p112">To do this, click the search that you want to investigate. On the flyout page, click **Add results to incident** and follow the instructions. Then in the incident, you can review individual documents, investigate who had access to documents, and export the documents. To simply delete the documents instead of reviewing them, go to [Step 4](##step-4:-permanently-delete-the-spilled-data).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="73660-p113">搜索查询中使用的关键字可能包含您要搜索的实际溅入的数据。例如，如果您搜索包含社会保险号码和您的文档将其用作搜索查询中的关键字，则必须删除查询以后避免进一步损耗情况。您可以删除搜索或删除整个调查中[的步骤 5](##step-5:-close-or-delete-investigation)。</span><span class="sxs-lookup"><span data-stu-id="73660-p113">The keywords that you use in the search query may contain the actual spilled data that you're searching for. For example, if you searching for documents containing a social security number and you use it as a keyword in the search query, you must delete the query afterwards to avoid further spillage. You can delete search or delete the entire investigation in [Step 5](##step-5:-close-or-delete-investigation).</span></span> 

## <a name="step-3-review-and-investigate"></a><span data-ttu-id="73660-163">步骤 3： 查看和调查</span><span class="sxs-lookup"><span data-stu-id="73660-163">Step 3: Review and investigate</span></span> 

<span data-ttu-id="73660-p114">在调查中，转到**事件**选项卡，然后单击您在上一步中创建的事件。完成处理作业和搜索结果添加到事件之后，您可以查看其本机格式、 文本格式或附近本机格式中的单个文档。您可以创建其他进一步缩小查询的文档和标记文档，以指明从您的调查研究结果列表。</span><span class="sxs-lookup"><span data-stu-id="73660-p114">In the investigation, go to **Incidents** tab and click on the incident that you created in the previous step. After the processing job is completed and the search results are added to the incident, you can review individual documents in their native format, text format, or a near-native format. You can create additional queries to further narrow the list of documents, and tag documents to indicate findings from your investigation.</span></span>

<span data-ttu-id="73660-p115">要组合文档和获取有关您进行审阅的更多帮助，请单击**管理事件**。在**分析**图块，单击**分析**。这将运行高级分析功能，如重复检测、 电子邮件超线程和主题分析。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="73660-p115">To group documents and get more assistance for your review, click **Manage incident**. In the **Analytics** tile, click **Analyze**. This will run advanced analytics such as duplicate detection, email threading, and theme analysis. For more information, see:</span></span>

- [<span data-ttu-id="73660-171">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="73660-171">Near duplicate detection</span></span>](near-duplicates.md)
- [<span data-ttu-id="73660-172">电子邮件会话</span><span class="sxs-lookup"><span data-stu-id="73660-172">Email threading</span></span>](email-threading.md)
- [<span data-ttu-id="73660-173">主题</span><span class="sxs-lookup"><span data-stu-id="73660-173">Themes</span></span>](themes.md)

<span data-ttu-id="73660-p116">若要确定哪些用户参与数据损耗情况，可以在事件中创建一个新的查询，并将发件人/作者和收件人条件。这将创建所有发件人、 收件人和收集的数据添加到事件中找到的作者的列表。请务必检查列表以确定列表是否有任何外部用户。有关详细信息，请参阅[搜索条件](../keyword-queries-and-search-conditions.md#search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="73660-p116">To determine which users are involved in the data spillage, you can create a new query in the incident and then use the Sender/Author and Recipients conditions. This will create a list of all senders, recipients and authors found in collected data that was added to the incident. Be sure to examine the list to determine if there are any external users in the list. For more information, see [Search conditions](../keyword-queries-and-search-conditions.md#search-conditions).</span></span>

## <a name="step-4-permanently-delete-the-spilled-data"></a><span data-ttu-id="73660-178">步骤 4： 永久删除溅入的数据</span><span class="sxs-lookup"><span data-stu-id="73660-178">Step 4: Permanently delete the spilled data</span></span>

### <a name="deleting-mailbox-items"></a><span data-ttu-id="73660-179">删除邮箱项目</span><span class="sxs-lookup"><span data-stu-id="73660-179">Deleting mailbox items</span></span>

<span data-ttu-id="73660-p117">查看并验证搜索结果包含必须要删除的电子邮件之后，可以永久删除它们通过运行**新建 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全 & 合规性中心 PowerShell。有关说明，请参阅[搜索和删除电子邮件](../search-for-and-delete-messages-in-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="73660-p117">After you review and validate that the search results contain only the email messages that must be deleted, you can permanently delete them by running the **New-ComplianceSearchAction -Purge -PurgeType HardDelete** command in Security & Compliance Center PowerShell. For instructions, see [Search for and delete email messages](../search-for-and-delete-messages-in-your-organization.md).</span></span> 

<span data-ttu-id="73660-p118">请注意，如果在组织中的邮箱启用单个项目恢复永久删除项目将被保留用户可恢复的项目文件夹中 （可由管理员访问） （默认值为 14 天） 的已删除的邮件保留期结束之前。此外，如果任何包含溅入的数据的邮箱的合法保留或分配给保留策略，清除的邮件将保留在可恢复的项目文件夹直到保留被删除或邮箱排除从保留策略。硬删除消息立即，您需要执行添加任务。有关说明，请参阅[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)。</span><span class="sxs-lookup"><span data-stu-id="73660-p118">Note that if single item recovery is enabled for mailboxes in your organization, permanently deleted items will be retained in the user's Recoverable items folder (and accessible by admins) until the deleted item retention period ends (default is 14 days). Additionally, if any of the mailboxes that contain spilled data are on a legal hold or assigned to a retention policy, purged message will be retained in Recoverable items folder until the hold is removed or the mailbox is excluded from retention policies. To hard delete messages immediately, you need to perform addition tasks. For instructions, see [Delete items in the Recoverable Items folder of cloud-based mailboxes on hold ](../delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md).</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="73660-p119">删除保留或保留策略之前，请与记录管理或法律部门。您的组织可能有定义上的邮箱是否保留策略或数据泄漏事件优先。</span><span class="sxs-lookup"><span data-stu-id="73660-p119">Check with your records management or legal departments before removing a hold or retention policy. Your organization may have a policy that defines whether a mailbox on hold or a data spillage incident takes priority.</span></span> 

### <a name="deleting-site-items"></a><span data-ttu-id="73660-188">删除网站项目</span><span class="sxs-lookup"><span data-stu-id="73660-188">Deleting site items</span></span>

<span data-ttu-id="73660-p120">业务帐户从 SharePoint 网站或 OneDrive 中永久删除文档，您必须将其删除，那么您需要从网站中删除，然后从网站集回收站中删除它。有关说明，请参阅[SharePoint 和 OneDrive 中的删除文档](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business)。</span><span class="sxs-lookup"><span data-stu-id="73660-p120">To permanently delete a document from a SharePoint site or OneDrive for Business account, you have to delete it and then you have to delete from the site and then delete it from the site collection Recycle Bin. For instructions, see [Deleting documents in SharePoint and OneDrive](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#deleting-documents-in-sharepoint-online-and-onedrive-for-business).</span></span>

<span data-ttu-id="73660-p121">或者，也可以删除整个网站集可能包含溅入的数据。有关说明，请参阅[删除网站集](https://docs.microsoft.com/sharepoint/delete-site-collection)。</span><span class="sxs-lookup"><span data-stu-id="73660-p121">Alternatively, you can delete an entire site collection that might contained spilled data. For instructions, see [Delete a site collection](https://docs.microsoft.com/sharepoint/delete-site-collection).</span></span>

## <a name="step-5-close-or-delete-the-investigation"></a><span data-ttu-id="73660-193">步骤 5： 关闭或删除调查</span><span class="sxs-lookup"><span data-stu-id="73660-193">Step 5: Close or delete the investigation</span></span>

<span data-ttu-id="73660-p122">删除源内容位置 （邮箱或网站） 中的文档后，您仍将具有这些作为调查的一部分添加到事件的文档的副本。若要避免进一步数据损耗情况，您应考虑删除调查。</span><span class="sxs-lookup"><span data-stu-id="73660-p122">After you delete documents in the source content locations (mailboxes or sites), you will still have copies of these documents that you added to incidents as part of your investigation. To avoid further data spillage, you should consider deleting the investigation.</span></span>

<span data-ttu-id="73660-196">删除调查：</span><span class="sxs-lookup"><span data-stu-id="73660-196">To delete an investigation:</span></span>

1. <span data-ttu-id="73660-197">在**设置**选项卡中，单击**调查信息**。</span><span class="sxs-lookup"><span data-stu-id="73660-197">On the **Settings** tab, click **Investigation information**.</span></span>
2. <span data-ttu-id="73660-198">单击**删除用例**。</span><span class="sxs-lookup"><span data-stu-id="73660-198">Click  **Delete case**.</span></span> 

<span data-ttu-id="73660-p123">如果您无需删除调查，或者如果您想要保存过程调查中收集的信息，您可以单击**关闭事例**。以后，您可以重新打开已关闭的调查。</span><span class="sxs-lookup"><span data-stu-id="73660-p123">If you don't need to delete the investigation or if you want to save the information that you collected during the investigation, you can click **Close case**. At a later date, you can re-open closed investigations.</span></span>