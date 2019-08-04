---
title: Office 365 中的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 或 Microsoft 365 合规中心中的内容搜索工具搜索邮箱、SharePoint Online 网站、OneDrive 帐户、Microsoft Teams、Office 365 组 和 Skype for Business 对话中的内容。 可以使用关键字搜索查询和搜索条件来缩小搜索结果。 然后预览并导出搜索结果。 内容搜索也是一款有效的工具，可用于搜索与 GDPR 数据主题请求相关的内容。
ms.openlocfilehash: 3df1ee02cc7b31a8dd316bac5ccd4455c26922c5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048184"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="5d467-106">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="5d467-106">Partially indexed items in Content Search in Office 365</span></span>

<span data-ttu-id="5d467-107">可以使用 Office 365 或 Microsoft 365 合规中心中的内容搜索电子数据展示工具来搜索相应的项，例如电子邮件、文档和 Office 365 组织中的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="5d467-107">You can use the Content Search eDiscovery tool in the compliance center in Office 365 or Microsoft 365 to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization.</span></span> <span data-ttu-id="5d467-108">使用此工具搜索以下 Office 365 服务中的项：</span><span class="sxs-lookup"><span data-stu-id="5d467-108">Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="5d467-109">Exchange Online 邮箱和公共文件夹</span><span class="sxs-lookup"><span data-stu-id="5d467-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="5d467-110">SharePoint Online 网站和 OneDrive for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="5d467-110">All SharePoint Online sites and OneDrive for Business accounts in your organization</span></span>
    
- <span data-ttu-id="5d467-111">Skype for Business 对话</span><span class="sxs-lookup"><span data-stu-id="5d467-111">im – Searches Skype for Business conversations</span></span>
    
- <span data-ttu-id="5d467-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5d467-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="5d467-113">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="5d467-113">Office 365 Groups</span></span>
    
<span data-ttu-id="5d467-114">运行内容搜索后，内容位置的数量和搜索结果的估计数量将会显示在搜索配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5d467-114">After you run a Content Search, the number of content sources and an estimated number of search results are displayed in the details pane on the Content search page.</span></span> <span data-ttu-id="5d467-115">还可以快速查看统计信息，例如具有与搜索查询匹配的项的内容位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-115">You can also quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="5d467-116">运行搜索后，可预览结果或将其导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5d467-116">After you run a compliance search, you can export the search results to a local computer.</span></span>

## <a name="create-a-search"></a><span data-ttu-id="5d467-117">创建搜索</span><span class="sxs-lookup"><span data-stu-id="5d467-117">Create a search</span></span>

<span data-ttu-id="5d467-118">若要访问**内容搜索**页面以运行搜索和预览并导出搜索结果，管理员、合规专员或电子数据展示管理者必须是安全与合规中心的电子数据展示管理者角色组中的成员。</span><span class="sxs-lookup"><span data-stu-id="5d467-118">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="5d467-119">有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-119">For more information, see [Assign eDiscovery permissions in Exchange](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="5d467-120">转至 [https://protection.office.com](https://protection.office.com) 并使用 Office 365 电子邮件地址和密码登录。</span><span class="sxs-lookup"><span data-stu-id="5d467-120">Go to [https://protection.office.com](https://protection.office.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="5d467-121">单击“**搜索**”\>“**内容搜索**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="5d467-122">在“**搜索**”页面，单击“![添加](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)”图标“**新建搜索**”旁边的箭头。</span><span class="sxs-lookup"><span data-stu-id="5d467-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    ![“新建搜索”下拉列表](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="5d467-124">可以选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="5d467-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="5d467-125">\*\*引导式搜索 — 选择此选择将会启动一个向导，用于指导你创建搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-125">\*\*Guided search — This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="5d467-126">用于选择内容位置和构建搜索查询的用户界面与“**新建搜搜**”选项相同。</span><span class="sxs-lookup"><span data-stu-id="5d467-126">The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="5d467-127">**新建搜索** – 选择此选项将显示一个用于创建搜索的更新用户界面。</span><span class="sxs-lookup"><span data-stu-id="5d467-127">**New search** – This option displays an updated user interface to create a search.</span></span> <span data-ttu-id="5d467-128">如果单击“**新建搜索**”，则此选项为默认选项。</span><span class="sxs-lookup"><span data-stu-id="5d467-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="5d467-129">**按 ID 列表搜索** – 选择此选项使你可以使用 Exchange ID 列表搜索特定电子邮件消息和其他邮箱项。</span><span class="sxs-lookup"><span data-stu-id="5d467-129">**Search by ID List** – This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="5d467-130">若要创建 ID 列表搜索（先前称为定向搜索），你可以提交一个用于标识要搜索的特定邮箱项的逗号分隔符值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="5d467-130">To create an ID list search (formally called a targeted search), you submit a comma-separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="5d467-131">有关说明，请参阅[为 Office 365 中的 ID 列表内容搜索准备 CSV 文件](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="5d467-132">此流程的其余步骤遵循默认的新建搜索工作流。</span><span class="sxs-lookup"><span data-stu-id="5d467-132">The remainder of the steps in this procedure follows the default new search workflow.</span></span>
    
4. <span data-ttu-id="5d467-133">在下拉列表中单击“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="5d467-134">在“**搜索查询**”下，指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="5d467-134">Under **Search query**, specify the following things:</span></span>
    
    ![指定要搜索的关键字、条件和位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="5d467-136">**要搜索的关键字** – 在“**关键字**”框中键入搜索查询。</span><span class="sxs-lookup"><span data-stu-id="5d467-136">**Keywords to search for** – Type a search query in **Keywords** box.</span></span> <span data-ttu-id="5d467-137">您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="5d467-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="5d467-138">可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。</span><span class="sxs-lookup"><span data-stu-id="5d467-138">You can  use a more complex queries that use a Boolean operator, such as AND, OR,  NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in  messages.</span></span> <span data-ttu-id="5d467-139">还可以搜索文档中的敏感信息（如社会保险号），或者搜索已外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="5d467-139">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="5d467-140">如果将关键字框留空，则指定内容位置中的所有内容都将包括在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5d467-140">If you leave this box empty, then all content  located in the specified  content sources will be included in  the search results.</span></span>
    
      <span data-ttu-id="5d467-141">或者，可以单击“**显示关键字列表**”复选框，然后在每一行键入一个关键字。</span><span class="sxs-lookup"><span data-stu-id="5d467-141">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="5d467-142">如果执行此操作，则每行上的关键字将由逻辑运算符连接 (**c:s**)，类似于所创建的搜索创建中的 **OR** 运算符功能。</span><span class="sxs-lookup"><span data-stu-id="5d467-142">If you do this, the keywords on each row are connected by a logical operator (**c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="5d467-143">为什么使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="5d467-143">Why use the keyword list?</span></span> <span data-ttu-id="5d467-144">可以获取与每个关键字匹配的项数量的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-144">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="5d467-145">这可以帮助你快速标识哪些关键字最有效和最无效。</span><span class="sxs-lookup"><span data-stu-id="5d467-145">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="5d467-146">还可以在行中使用关键字短语（使用括号包围）。</span><span class="sxs-lookup"><span data-stu-id="5d467-146">Keywords on each row are connected by the OR operator in the search query that's created. You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="5d467-147">有关搜索统计信息的更多信息，请参阅[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-147">For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="5d467-148">为了帮助减少因海量关键字列表导致的问题，现在，已将关键字列表中的最大行数限制为 20 行。</span><span class="sxs-lookup"><span data-stu-id="5d467-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="5d467-149">**条件** – 可以添加搜索条件来缩小搜索范围并返回更精确的结果集。</span><span class="sxs-lookup"><span data-stu-id="5d467-149">You can also add conditions to a search query to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="5d467-150">每个条件向开始搜索时创建和运行的搜索查询添加一个子句。</span><span class="sxs-lookup"><span data-stu-id="5d467-150">Each condition adds a clause to the KQL search query that is created and run when you start the search.</span></span> <span data-ttu-id="5d467-151">可通过使用功能类似于 **AND** 运算符的逻辑运算符 (**c:c**) 在逻辑上将条件连接至关键字查询（在关键字框中指定）。</span><span class="sxs-lookup"><span data-stu-id="5d467-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5d467-152">这意味着，项必须满足关键字查询和要在结果中包括的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="5d467-152">That means that items have to satisfy both the keyword query and the condition to be included in the results.</span></span> <span data-ttu-id="5d467-153">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="5d467-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="5d467-154">有关可以在搜索查询中使用的条件列表和描述，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的“搜索条件”部分。</span><span class="sxs-lookup"><span data-stu-id="5d467-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="5d467-155">**位置** – 选择要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-155">**Locations** – Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="5d467-156">**所有位置** – 使用此选项搜索组织中的所有内容位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-156">**All locations** – Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="5d467-157">这包括所有 Exchange 邮箱中的电子邮件（包括所有非活动邮箱、所有 Office 365 组邮箱、所有 Microsoft Teams 邮箱）、所有 Skype for Business 对话、所有 SharePoint 和 OneDrive for Business 网站（包括所有 Office 365 组和 Microsoft Teams 网站）以及所有 Exchange 公共文件夹中的项。</span><span class="sxs-lookup"><span data-stu-id="5d467-157">This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="5d467-158">**特定位置** – 使用此选项搜索特定内容位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-158">**Specific locations** – Use this option to search specific content locations.</span></span> <span data-ttu-id="5d467-159">可以搜索特定 Office 365 服务的所有内容位置（例如搜索所有 Exchange 邮箱或搜索所有 SharePoint 网站），或者在显示的任何 Office 365 服务中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-159">You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![用于选择要搜索的内容位置的用户界面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="5d467-161">还可以将通讯组添加至要搜索的 Exchange 邮箱列表中。</span><span class="sxs-lookup"><span data-stu-id="5d467-161">You can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="5d467-162">对于通讯组，将搜索组成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="5d467-163">不支持动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="5d467-163">Dynamic distribution groups aren't supported.</span></span>
    
       > [!NOTE]
       > <span data-ttu-id="5d467-164">搜索所有邮箱位置或仅特定邮箱，导出内容搜索结果时，保存至用户邮箱的其他 Office 365 应用程序数据将包括在内。</span><span class="sxs-lookup"><span data-stu-id="5d467-164">When you search all mailbox locations or just specific mailboxes, data from other Office 365 applications that's saved to user mailboxes is included when you export the results of a Content Search.</span></span> <span data-ttu-id="5d467-165">此数据将不会包括在估计的搜索结果中，并且也不可用于预览。</span><span class="sxs-lookup"><span data-stu-id="5d467-165">This data won't be included in the estimated search results and isn't available for preview.</span></span> <span data-ttu-id="5d467-166">导入和下载搜索结果时，此数据将包括在内。</span><span class="sxs-lookup"><span data-stu-id="5d467-166">It is included when you export and download the search results.</span></span> <span data-ttu-id="5d467-167">有关详细信息，请参阅 [Exchange Online 邮箱中存储的内容](what-is-stored-in-exo-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-167">For more information, see [Manage inactive mailboxes in Exchange Online](what-is-stored-in-exo-mailbox.md).</span></span>

    
6. <span data-ttu-id="5d467-168">设置搜索查询之后，请单击“**保存并返回**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-168">After you've set up your search query, click **Save & run**.</span></span>
    
7. <span data-ttu-id="5d467-169">在“**保存搜索**”页面上，键入搜索名称以及帮助标识搜索的可选描述。</span><span class="sxs-lookup"><span data-stu-id="5d467-169">On the **Save search** page, type a name for the search, and an optional description that helps identify the search.</span></span> <span data-ttu-id="5d467-170">搜索名称在你的组织中必须保持唯一。</span><span class="sxs-lookup"><span data-stu-id="5d467-170">The name of the case must be unique in your organization.</span></span> 
    
8. <span data-ttu-id="5d467-171">单击“**保存**”以开始搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-171">Click **ok** to start running the advanced search.</span></span> 
    
    <span data-ttu-id="5d467-172">保存并运行搜索之后，搜索返回的任何结果都将会显示在结果窗格中。</span><span class="sxs-lookup"><span data-stu-id="5d467-172">After you save and run the search, any results returned by the search are displayed in the results pane.</span></span> <span data-ttu-id="5d467-173">搜索结果将会显示或者需要单击“**预览结果**”才能查看它们，具体取决于所配置的预览设置。</span><span class="sxs-lookup"><span data-stu-id="5d467-173">Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them.</span></span> <span data-ttu-id="5d467-174">有关详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="5d467-174">See the next section for details and examples.</span></span> 
    
<span data-ttu-id="5d467-175">若要再次访问此内容搜索或者访问“**内容搜索**”页面上列出的其他内容搜索，请选择搜索，然后单击“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-175">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="5d467-176">若要清除结果或者创建其他搜索，请单击“![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)”“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-176">To clear the results or create another search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="5d467-177">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="5d467-177">Preview search results</span></span>

<span data-ttu-id="5d467-178">具有两种预览搜索结果配置设置。</span><span class="sxs-lookup"><span data-stu-id="5d467-178">There are two configuration settings for previewing search results.</span></span> <span data-ttu-id="5d467-179">运行新搜索或者打开现有搜索之后，请单击 **单独的结果** 以查看以下预览设置：</span><span class="sxs-lookup"><span data-stu-id="5d467-179">After you run a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![预览搜索结果设置](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="5d467-181">**自动预览结果** – 此设置将在运行搜索之后显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5d467-181">**Preview results automatically** – This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="5d467-182">**手动预览结果** – 此设置将在搜索结果窗格中显示占位符，并显示“**预览结果**”按钮，必须单击此按钮才能显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5d467-182">**Preview results manually** – This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results.</span></span> <span data-ttu-id="5d467-183">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="5d467-183">This is the default setting.</span></span> <span data-ttu-id="5d467-184">这有助于增强搜索性能，因为它不会在你打开现有搜索时自动显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="5d467-184">It helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="5d467-185">可供预览的项数量具有限制。</span><span class="sxs-lookup"><span data-stu-id="5d467-185">There are limits related to how many items are available to be previewed.</span></span> <span data-ttu-id="5d467-186">有关详细信息，请参阅[内容搜索限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-186">For more information, see [Keyword queries and search conditions for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="5d467-187">有关可预览的受支持文件类型列表，请参阅“有关内容搜索的详细信息”部分的[预览搜索结果](#previewing-search-results)。</span><span class="sxs-lookup"><span data-stu-id="5d467-187">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section.</span></span> <span data-ttu-id="5d467-188">如果文件类型不支持预览或者下载文档副本，则可以单击“**下载原始文件**”以将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5d467-188">If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer.</span></span> <span data-ttu-id="5d467-189">对于 .aspx Web 页面，尽管你可能没有访问该页面的权限，但该页面的 URL 将包括在内。</span><span class="sxs-lookup"><span data-stu-id="5d467-189">For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="5d467-190">另请注意，未编入索引的项不提供预览。</span><span class="sxs-lookup"><span data-stu-id="5d467-190">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="5d467-191">查看与搜索相关的信息和统计信息</span><span class="sxs-lookup"><span data-stu-id="5d467-191">View information and statistics about a search</span></span>

<span data-ttu-id="5d467-192">创建并运行内容搜索之后，可以查看与估计的搜索结果相关的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-192">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="5d467-193">其中包括搜索结果摘要、查询统计信息（如与搜索查询匹配的项内的内容位置数）以及具有最多匹配项的内容位置的名称。</span><span class="sxs-lookup"><span data-stu-id="5d467-193">This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="5d467-194">可以显示一个或多个内容搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-194">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="5d467-195">你可以通过它快速比较多个搜索的结果，并确定搜索查询的有效性。</span><span class="sxs-lookup"><span data-stu-id="5d467-195">This lets you quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="5d467-196">还可以将搜索统计信息和关键字统计信息下载为 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="5d467-196">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="5d467-197">此操作使你能够使用 Excel 中的筛选和排序功能来比较结果，并准备搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="5d467-197">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="5d467-198">若要查看搜索统计信息：</span><span class="sxs-lookup"><span data-stu-id="5d467-198">To view search statistics:</span></span>
  
1. <span data-ttu-id="5d467-199">在“**内容搜索**”页面上，单击“**打开**”，然后单击想要查看其统计信息的搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-199">On the **Content search** page, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="5d467-200">在浮出页面上，单击“**打开查询**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-200">On the flyout page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="5d467-201">在“**单独的结果**”下拉列表中，单击“**搜索配置文件**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-201">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="5d467-202">在“**类型**”下拉列表中，根据想要查看的搜索统计信息单击以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="5d467-202">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="5d467-203">**摘要** – 显示所搜索的每种内容位置类型的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-203">**Summary** – Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="5d467-204">这包括包含与搜索查询匹配的项的内容位置数，以及搜索结果项的总数和大小。</span><span class="sxs-lookup"><span data-stu-id="5d467-204">This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items.</span></span> <span data-ttu-id="5d467-205">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="5d467-205">This is the default setting.</span></span>
    
  - <span data-ttu-id="5d467-206">**查询** – 显示与搜索查询相关的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-206">**Queries** – Displays statistics about the search query.</span></span> <span data-ttu-id="5d467-207">这包括查询统计信息所适用的内容位置类型、统计信息所适用的搜索查询部分（请注意，“**主要**”表示整个搜索查询）、包含与搜索查询匹配的项的内容位置数量以及与搜索查询匹配（在指定内容位置）的项总数和大小。</span><span class="sxs-lookup"><span data-stu-id="5d467-207">This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query.</span></span> <span data-ttu-id="5d467-208">还会显示与未编入索引的项的统计信息（也称为“*部分索引项*）。</span><span class="sxs-lookup"><span data-stu-id="5d467-208">Statistics for unindexed items (also called *partially indexed items*) are also displayed.</span></span> <span data-ttu-id="5d467-209">但是，只有邮箱中的部分索引项将会包括在统计信息中。</span><span class="sxs-lookup"><span data-stu-id="5d467-209">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="5d467-210">SharePoint 和 OneDrive 中的部分索引项不会包括在统计信息中。</span><span class="sxs-lookup"><span data-stu-id="5d467-210">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="5d467-211">**热门位置** – 显示与每个内容位置中的搜索查询匹配的项数量。</span><span class="sxs-lookup"><span data-stu-id="5d467-211">**Top locations** – Displays statistics about the number of items that match the search query in each content location.</span></span> <span data-ttu-id="5d467-212">将会显示前 1,000 个位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-212">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="5d467-213">有关搜索统计信息的详细信息，请参阅[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-213">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="5d467-214">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="5d467-214">Export search results</span></span>

<span data-ttu-id="5d467-215">成功运行搜索之后，你可以将搜索结果导出至本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5d467-215">After a search is successfully run, you can  export the  search results to a local computer.</span></span> <span data-ttu-id="5d467-216">导出电子邮件结果时，它们将以 PST 文件或单独邮件的形式下载到你的计算机。</span><span class="sxs-lookup"><span data-stu-id="5d467-216">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="5d467-217">当你从 SharePoint 和 OneDrive 网站导出内容时，将导出本地 Office 文档副本。</span><span class="sxs-lookup"><span data-stu-id="5d467-217">When you export content from SharePoint and skydrive_pro sites, copies of native Office documents are  exported.</span></span> <span data-ttu-id="5d467-218">导出的搜索结果中还包含其他文档和报告。</span><span class="sxs-lookup"><span data-stu-id="5d467-218">There are also additional documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="5d467-219">也可以导出搜索结果报告，而不是实际项。</span><span class="sxs-lookup"><span data-stu-id="5d467-219">You can also export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="5d467-220">若要导出搜索结果：</span><span class="sxs-lookup"><span data-stu-id="5d467-220">To export search results:</span></span>
  
1. <span data-ttu-id="5d467-221">在“**内容搜索**”页面上，单击想要导出其搜索结果的搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-221">On the **Compliance search** page, select the search that you want to refresh the results for.</span></span> 
    
2. <span data-ttu-id="5d467-222">在浮出页面上，单击“![导出搜索结果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)”图标“**更多**”，然后单击“**导出结果**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-222">On the flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**.</span></span> <span data-ttu-id="5d467-223">还可以导出搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="5d467-223">You can also export a search results report.</span></span>
    
3. <span data-ttu-id="5d467-224">完成“**导出结果**”浮出页面上的部分。</span><span class="sxs-lookup"><span data-stu-id="5d467-224">Complete the sections on the **Export results** fly out page. Be sure to use the scroll bar to view all export options.</span></span> <span data-ttu-id="5d467-225">请务必使用滚动条查看所有导出选项。</span><span class="sxs-lookup"><span data-stu-id="5d467-225">Complete the sections on the Export results fly out page. Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="5d467-226">有关更多详细说明和疑难解答提示，请参阅:</span><span class="sxs-lookup"><span data-stu-id="5d467-226">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="5d467-227">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="5d467-227">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="5d467-228">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="5d467-228">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="5d467-229">有关内容搜索的详细信息</span><span class="sxs-lookup"><span data-stu-id="5d467-229">More information about content search</span></span>

<span data-ttu-id="5d467-230">请参阅以下各部分，以获取与内容搜索相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-230">See the following sections for more information about each option.</span></span>
  
[<span data-ttu-id="5d467-231">内容搜索限制</span><span class="sxs-lookup"><span data-stu-id="5d467-231">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="5d467-232">构建搜索查询</span><span class="sxs-lookup"><span data-stu-id="5d467-232">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="5d467-233">搜索 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="5d467-233">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="5d467-234">搜索 Microsoft Teams 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="5d467-234">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="5d467-235">搜索非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5d467-235">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="5d467-236">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="5d467-236">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="5d467-237">部分索引项</span><span class="sxs-lookup"><span data-stu-id="5d467-237">Partially indexed items in Content Search</span></span>](#partially-indexed-items)
  
### <a name="content-search-limits"></a><span data-ttu-id="5d467-238">内容搜索限制</span><span class="sxs-lookup"><span data-stu-id="5d467-238">Content search limits</span></span>

- <span data-ttu-id="5d467-239">有关适用于内容搜索功能的限制的说明，请参阅[内容搜索限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-239">For a description of the limits that are applied to the Content Search feature, see [Limits for Content Search](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="5d467-240">Microsoft 将会收集所有 Office 365 组织运行的内容搜索性能信息。</span><span class="sxs-lookup"><span data-stu-id="5d467-240">Microsoft collects performance information for Content Searches run by all Office 365 organizations.</span></span> <span data-ttu-id="5d467-241">尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="5d467-241">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="5d467-242">尽管 Microsoft 未为搜索时间提供服务级别协议，但是下表根据搜索中所含的邮箱数列出了内容搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="5d467-242">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="5d467-243">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="5d467-243">**Number of mailboxes**</span></span>|<span data-ttu-id="5d467-244">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="5d467-244">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5d467-245">100</span><span class="sxs-lookup"><span data-stu-id="5d467-245">100%</span></span>  <br/> |<span data-ttu-id="5d467-246">30 秒</span><span class="sxs-lookup"><span data-stu-id="5d467-246">30 seconds</span></span>  <br/> |
|<span data-ttu-id="5d467-247">1,000</span><span class="sxs-lookup"><span data-stu-id="5d467-247">1,000</span></span>  <br/> |<span data-ttu-id="5d467-248">45 秒</span><span class="sxs-lookup"><span data-stu-id="5d467-248">45 seconds</span></span>  <br/> |
|<span data-ttu-id="5d467-249">10,000</span><span class="sxs-lookup"><span data-stu-id="5d467-249">10,000</span></span>  <br/> |<span data-ttu-id="5d467-250">4 分钟</span><span class="sxs-lookup"><span data-stu-id="5d467-250">4 minutes</span></span>  <br/> |
|<span data-ttu-id="5d467-251">25,000</span><span class="sxs-lookup"><span data-stu-id="5d467-251">25,000</span></span>  <br/> |<span data-ttu-id="5d467-252">10 分钟</span><span class="sxs-lookup"><span data-stu-id="5d467-252">10 minutes</span></span>  <br/> |
|<span data-ttu-id="5d467-253">50,000</span><span class="sxs-lookup"><span data-stu-id="5d467-253">-500.00%</span></span>  <br/> |<span data-ttu-id="5d467-254">20 分钟</span><span class="sxs-lookup"><span data-stu-id="5d467-254">20 minutes</span></span>  <br/> |
|<span data-ttu-id="5d467-255">100,000</span><span class="sxs-lookup"><span data-stu-id="5d467-255">100,000</span></span>  <br/> |<span data-ttu-id="5d467-256">25 分钟</span><span class="sxs-lookup"><span data-stu-id="5d467-256">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="5d467-257">构建搜索查询</span><span class="sxs-lookup"><span data-stu-id="5d467-257">Run a search query</span></span>

<span data-ttu-id="5d467-258">有关创建搜索查询、使用布尔搜索运算符和搜索条件以及搜索敏感信息类型及与组织外部用户共享的内容的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-258">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="5d467-259">使用关键字列表创建搜索查询时，请注意以下内容。</span><span class="sxs-lookup"><span data-stu-id="5d467-259">Keep the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="5d467-260">必须选中“**显示关键字列表**”复选框并在单独行中键入每个关键字，才能创建每行中的关键字以 **OR** 运算符连接的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="5d467-260">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="5d467-261">如果将关键字列表粘贴至关键字框或者在键入关键字之后按 **Enter** 键，则它们将不会以 **OR** 运算符连接。</span><span class="sxs-lookup"><span data-stu-id="5d467-261">If you paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="5d467-262">以下是添加关键字列表的错误和正确示例。</span><span class="sxs-lookup"><span data-stu-id="5d467-262">Here are incorrect and correct examples of how to add a list of keywords.</span></span> 
    
    <span data-ttu-id="5d467-263">**错误**</span><span class="sxs-lookup"><span data-stu-id="5d467-263">**Incorrect:**</span></span>
    
    ![设置关键字列表格式的不正确方式（通过将列表粘贴至关键字框）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="5d467-265">**正确**</span><span class="sxs-lookup"><span data-stu-id="5d467-265">**Correct:**</span></span>
    
    ![设置关键字列表格式的正确方式（在选中复选框后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="5d467-267">还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语列表，然后将你的列表复制粘贴至关键字列表。</span><span class="sxs-lookup"><span data-stu-id="5d467-267">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list into the keyword list.</span></span> <span data-ttu-id="5d467-268">若要执行此操作，你必须选中“**显示关键字列表**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5d467-268">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="5d467-269">然后，单击关键字列表中的第一行并粘贴你的列表。</span><span class="sxs-lookup"><span data-stu-id="5d467-269">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="5d467-270">Excel 或文本文件中的每一行均会粘贴至关键字列表中的单独行中。</span><span class="sxs-lookup"><span data-stu-id="5d467-270">Each line from the Excel or text file is pasted into separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="5d467-271">使用关键字列表创建查询后，最好验证搜索查询语法，确保搜索查询适合你的需求。</span><span class="sxs-lookup"><span data-stu-id="5d467-271">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="5d467-272">在详细信息窗格的“**查询**”下显示的搜索查询中，关键字将以文本 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="5d467-272">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="5d467-273">这表示关键字由功能类似于 **OR** 运算符的逻辑运算符连接。</span><span class="sxs-lookup"><span data-stu-id="5d467-273">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="5d467-274">同样，如果搜索查询中包含条件，则关键字和条件将以 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="5d467-274">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="5d467-275">这表示关键字由功能类似于 **AND** 运算符的逻辑运算符连接到条件。</span><span class="sxs-lookup"><span data-stu-id="5d467-275">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="5d467-276">以下是使用关键字列表和条件时创建的搜索查询（显示在详细信息窗格中）示例。</span><span class="sxs-lookup"><span data-stu-id="5d467-276">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用关键字列表和条件时创建的查询示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="5d467-278">运行内容搜索时，Office 365 将会自动检查搜索查询中是否存在不受支持的字符以及未大写的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="5d467-278">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that may not be capitalized.</span></span> <span data-ttu-id="5d467-279">不受支持的字符往往会被隐藏，并且通常会引发搜索错误或者返回意外结果。</span><span class="sxs-lookup"><span data-stu-id="5d467-279">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="5d467-280">有关检查到的不受支持字符的详细信息，请参阅[检查内容搜索查询中是否存在错误](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-280">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="5d467-281">如果搜索查询中包含非英语字符（例如中文字符）关键字，则可以单击“**查询语言-国家/地区**”“![内容搜索中的查询语言-国家/地区](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)”并为该搜索选择语言-国家/地区文化代码值。</span><span class="sxs-lookup"><span data-stu-id="5d467-281">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="5d467-282">默认语言/区域是中性的。</span><span class="sxs-lookup"><span data-stu-id="5d467-282">The default language/region is neutral.</span></span> <span data-ttu-id="5d467-283">如何判断是否需要更改内容搜索的语言设置？</span><span class="sxs-lookup"><span data-stu-id="5d467-283">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="5d467-284">如果确定要搜索的内容位置包含非英语字符，但搜索没有返回结果，则可能是语言设置的原因。</span><span class="sxs-lookup"><span data-stu-id="5d467-284">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="5d467-285">搜索 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="5d467-285">Searching OneDrive accounts</span></span>

- <span data-ttu-id="5d467-286">若要收集组织中的 OneDrive 网站 URL 列表，请参阅[在组织中创建所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="5d467-286">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> <span data-ttu-id="5d467-287">本文中的脚本将创建包含所有 OneDrive 网站的文本文件。</span><span class="sxs-lookup"><span data-stu-id="5d467-287">This script creates a text file that contains a list of all skydrive_pro sites.</span></span> <span data-ttu-id="5d467-288">若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。</span><span class="sxs-lookup"><span data-stu-id="5d467-288">To run this script, you have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="5d467-289">请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。</span><span class="sxs-lookup"><span data-stu-id="5d467-289">Be sure to append the URL for your organization’s MySite domain to each skydrive_pro site that you want to search.</span></span> <span data-ttu-id="5d467-290">这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="5d467-290">This is the domain that contains all your skydrive_pro; for example, https://woodgrovebank-my.sharepoint.com.</span></span> <span data-ttu-id="5d467-291">下面是用户的 OneDrive 网站的 URL示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="5d467-291">Here's an example of a URL for a user's skydrive_pro site: https://woodgrovebank-my.sharepoint.com/personal/clayn_woodgrovebank_onmicrosoft.com.</span></span>
    
    <span data-ttu-id="5d467-292">在少数用户主体名称 (UPN) 发生更改的情况下，OneDrive 位置的 URL 将发生更改，以包含新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="5d467-292">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location is changed to incorporate the new UPN.</span></span> <span data-ttu-id="5d467-293">如果发生这种情况，则必须通过添加用户的新 OneDrive URL 并删除旧 URL 来修改内容搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-293">If this happens, you have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="5d467-294">搜索 Microsoft Teams 和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="5d467-294">Microsoft Teams and Office 365</span></span>

<span data-ttu-id="5d467-295">可以搜索与 Office 365 组或 Microsoft Teams 关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-295">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="5d467-296">Microsoft Teams 构建于 Office 365 组之上，因此，搜索方法类似。</span><span class="sxs-lookup"><span data-stu-id="5d467-296">Because Microsoft Teams is built on Office 365 Groups, searching them is similar.</span></span> <span data-ttu-id="5d467-297">在这两种情况下，只会搜索组或团队邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-297">In both cases, only the group or team mailbox is searched.</span></span> <span data-ttu-id="5d467-298">不会搜索组或团队成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-298">The mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="5d467-299">若要搜索它们，必须将它们专门添加到搜索中。</span><span class="sxs-lookup"><span data-stu-id="5d467-299">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="5d467-300">搜索 Microsoft Teams 和 Office 365 组中的内容时，请注意以下内容。</span><span class="sxs-lookup"><span data-stu-id="5d467-300">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="5d467-301">若要搜索 Teams 和 Office 365 组中的内容，必须指定与团队或组关联的邮箱和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="5d467-301">To search for content located in Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="5d467-302">在 Exchange Online 中运行 **Get-UnifiedGroup** cmdlet，以查看团队或 Office 365 组的属性。</span><span class="sxs-lookup"><span data-stu-id="5d467-302">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a team or an Office 365 Group.</span></span> <span data-ttu-id="5d467-303">这是一种获取与团队或组关联的网站 URL 的好方法。</span><span class="sxs-lookup"><span data-stu-id="5d467-303">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="5d467-304">例如，以下命令显示名为高层领导团队的 Office 365 组的选定属性：</span><span class="sxs-lookup"><span data-stu-id="5d467-304">For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="5d467-305">若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5d467-305">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5d467-306">搜索用户邮箱时，不会搜索用户是其成员的任何团队或 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="5d467-306">When a user's mailbox is searched, any team or Office 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="5d467-307">类似地，在搜索团队或 Office 365 组时，只会搜索指定的组邮箱和组网站。</span><span class="sxs-lookup"><span data-stu-id="5d467-307">Similarly, when you search a team or an Office 365 Group, only the group mailbox and group site that you specify is searched.</span></span> <span data-ttu-id="5d467-308">不会搜索组成员的邮箱和 OneDrive for Business 帐户，除非你将其显式添加到搜索中。</span><span class="sxs-lookup"><span data-stu-id="5d467-308">The mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="5d467-309">若要获取团队或 Office 365 组的成员列表，则可以查看 Microsoft 365 管理中心 **“主页”“\>组**”页面上的属性。</span><span class="sxs-lookup"><span data-stu-id="5d467-309">To get a list of the members of a team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5d467-310">或者，可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5d467-310">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="5d467-311">若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5d467-311">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="5d467-312">属于 Teams 渠道的对话将存储在与团队关联的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5d467-312">Conversations that are part of a Teams channel are stored in the mailbox that's associated with the team.</span></span> <span data-ttu-id="5d467-313">同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。</span><span class="sxs-lookup"><span data-stu-id="5d467-313">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="5d467-314">因此，必须将团队邮箱和 SharePoint 网站作为内容位置添加到搜索渠道中的对话和文件。</span><span class="sxs-lookup"><span data-stu-id="5d467-314">Therefore, you have to add the team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="5d467-315">或者，属于 Teams 中聊天列表的对话将存储在参与该聊天的用户的 Exchange Online 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5d467-315">Alternatively, conversations that are part of the Chat list in Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="5d467-316">用户在聊天对话中共享的文件将存储在共享该文件的用户的 OneDrive for Business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="5d467-316">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="5d467-317">因此，必须将单独的用户邮箱和 OneDrive for Business 帐户作为内容位置添加到聊天列表中的搜索对话和文件中。</span><span class="sxs-lookup"><span data-stu-id="5d467-317">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d467-318">在 Exchange 混合部署中，拥有本地邮箱的用户可以参与属于 Teams 中的聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="5d467-318">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Teams.</span></span> <span data-ttu-id="5d467-319">在这种情况下，这些对话中的也可搜索，因为对于拥有本地邮箱的用户来说，它已保存至拥有本地邮箱的用户的基于云的存储区（称为*本地用户的基于云的邮箱*）。</span><span class="sxs-lookup"><span data-stu-id="5d467-319">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="5d467-320">有关详细信息，请参阅[为 Office 365 中的本地用户搜索基于云的邮箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-320">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="5d467-321">每个团队或团队渠道均包含一个用于做笔记和协作的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="5d467-321">Every team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="5d467-322">Wiki 内容将会自动保存至采用 .mht 格式的文件。</span><span class="sxs-lookup"><span data-stu-id="5d467-322">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="5d467-323">此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。</span><span class="sxs-lookup"><span data-stu-id="5d467-323">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="5d467-324">可以使用内容搜索工具来搜索 Wiki，方法是将团队的 SharePoint 网站指定为要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="5d467-324">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5d467-325">搜索团队或渠道 Wiki 的功能（在搜索团队 SharePoint 网站时）已于 2017 年 6 月 22 日发布。</span><span class="sxs-lookup"><span data-stu-id="5d467-325">The capability to search the Wiki for a team or channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="5d467-326">可以对在该日期或之后保存或更新的 Wiki 页面进行搜索。</span><span class="sxs-lookup"><span data-stu-id="5d467-326">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="5d467-327">不可搜索最后保存或更新时间早于该日期的 Wiki 页面。</span><span class="sxs-lookup"><span data-stu-id="5d467-327">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="5d467-328">Teams 渠道中的会议和呼叫摘要信息也保存在拨入会议或呼叫的用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="5d467-328">Summary information for meetings and calls in a Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="5d467-329">这意味着你可以使用内容搜索来搜索这些摘要记录。</span><span class="sxs-lookup"><span data-stu-id="5d467-329">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="5d467-330">摘要信息包括：</span><span class="sxs-lookup"><span data-stu-id="5d467-330">Summary information includes:</span></span> 
  
  - <span data-ttu-id="5d467-331">日期、开始时间、结束时间和会议或呼叫时长</span><span class="sxs-lookup"><span data-stu-id="5d467-331">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="5d467-332">每个参与者加入或离开会议或呼叫的日期和时间</span><span class="sxs-lookup"><span data-stu-id="5d467-332">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="5d467-333">发送到语音信箱的呼叫</span><span class="sxs-lookup"><span data-stu-id="5d467-333">Calls sent to voice mail</span></span>

  - <span data-ttu-id="5d467-334">未接呼叫</span><span class="sxs-lookup"><span data-stu-id="5d467-334">Missed or unanswered calls</span></span>

  - <span data-ttu-id="5d467-335">表示为两次单独呼叫的呼叫转移</span><span class="sxs-lookup"><span data-stu-id="5d467-335">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="5d467-336">可能需要最多 8 小时之后才能搜索会议和呼叫摘要记录。</span><span class="sxs-lookup"><span data-stu-id="5d467-336">It can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="5d467-337">在搜索结果中，会议摘要在“**类型字段**”将标识为“**会议**”，呼叫摘要将标识为“**呼叫**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-337">In the search results, meeting summaries are identified as **Meeting** in the **Type field**, and call summaries are identified as **Call**.</span></span> <span data-ttu-id="5d467-338">此外，属于 Teams 渠道和 1xN 聊天的对话在“**类型**”字段将标识为 **IM**。</span><span class="sxs-lookup"><span data-stu-id="5d467-338">Also, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![Teams 会议、呼叫和 1xN 聊天将在“类型”字段中标识](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="5d467-340">可以使用“**类型**”电子邮件属性或“**邮件类型**”搜索条件来搜索 Teams 中的特定内容。</span><span class="sxs-lookup"><span data-stu-id="5d467-340">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Teams.</span></span> 
  
  - <span data-ttu-id="5d467-341">若要将“**类型**”属性用作关键字搜索查询的一部分，请在搜索查询的“**关键字**”框中键入 `kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="5d467-341">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在关键字框中键入 kind:microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="5d467-343">若要使用搜索条件，请添加“**邮件类型**”条件并使用值 `microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="5d467-343">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![搭配使用“邮件类型”条件和值 microsoftteams。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="5d467-345">请注意，条件将通过 **AND** 运算符在逻辑上连接至关键字查询。</span><span class="sxs-lookup"><span data-stu-id="5d467-345">Note that conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="5d467-346">这意味着项必须与关键字查询和搜索条件匹配才能在搜索结果中返回。</span><span class="sxs-lookup"><span data-stu-id="5d467-346">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="5d467-347">有关详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的“使用条件指南”一节。</span><span class="sxs-lookup"><span data-stu-id="5d467-347">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="5d467-348">搜索非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5d467-348">Searching inactive mailboxes</span></span>

<span data-ttu-id="5d467-349">可以在内容搜索中搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-349">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="5d467-350">若要获取组织中的非活动邮箱列表，请在 Exchange Online PowerShell 中运行命令 `Get-Mailbox -InactiveMailboxOnly`。</span><span class="sxs-lookup"><span data-stu-id="5d467-350">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="5d467-351">或者，你可以转至安全与合规中心中的“**数据管理**”\>“**保留**”，然后单击“**更多**”“![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)”\>“**非活动邮箱**”。</span><span class="sxs-lookup"><span data-stu-id="5d467-351">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="5d467-352">以下是在搜索非活动邮箱时应记住的一些事项。</span><span class="sxs-lookup"><span data-stu-id="5d467-352">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="5d467-353">如果内容搜索包括用户邮箱，且该邮箱随后变成非活动状态，那么在该邮箱转变为非活动状态后重新运行搜索时，内容搜索将继续搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-353">If a content search includes a user mailbox and that mailbox is, then made inactive, the content search will continue to search the inactive mailbox when you rerun the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="5d467-354">有时候，用户可能具有 SMTP 地址相同的活动邮箱和非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-354">Sometimes a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="5d467-355">在这种情况下，将仅搜索你选为内容搜索位置的特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-355">In this case, only the specific mailbox that you select as a location for a content search is searched.</span></span> <span data-ttu-id="5d467-356">换言之，如果将用户邮箱添加到搜索中，则无法假定搜索的是其活动和非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-356">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes are searched.</span></span> <span data-ttu-id="5d467-357">只会搜索已显式添加到搜索中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-357">Only the mailbox that you explicitly add to the search is searched.</span></span>
    
- <span data-ttu-id="5d467-358">强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="5d467-358">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="5d467-359">如果需要重新使用分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或将非活动邮箱中的内容还原到活动邮箱中（或活动邮箱的存档中），然后删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="5d467-359">If you need to reuse the SMTP address that is assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="5d467-360">有关详细信息，请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="5d467-360">For more information about upgrading your servers, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="5d467-361">恢复 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5d467-361">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="5d467-362">还原 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5d467-362">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="5d467-363">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="5d467-363">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="5d467-364">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="5d467-364">Previewing search results</span></span>

<span data-ttu-id="5d467-365">可以在预览窗格中预览受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="5d467-365">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="5d467-366">如果文件类型不受支持，则必须将该文件的副本下载到本地计算机才能查看它。</span><span class="sxs-lookup"><span data-stu-id="5d467-366">If a file type isn't supported, you have to download a copy of the file to your local computer to view it.</span></span> <span data-ttu-id="5d467-367">以下是受支持的文件类型，可以在搜索结果窗格中对其进行预览。</span><span class="sxs-lookup"><span data-stu-id="5d467-367">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="5d467-368">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="5d467-368">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="5d467-369">.eml</span><span class="sxs-lookup"><span data-stu-id="5d467-369">.eml</span></span>
    
- <span data-ttu-id="5d467-370">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="5d467-370">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="5d467-371">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="5d467-371">.pptm, .pptx</span></span>
    
- <span data-ttu-id="5d467-372">.pdf</span><span class="sxs-lookup"><span data-stu-id="5d467-372">.pdf</span></span>
    
<span data-ttu-id="5d467-373">此外，还支持以下文件容器类型。</span><span class="sxs-lookup"><span data-stu-id="5d467-373">Also, the following file container types are supported.</span></span> <span data-ttu-id="5d467-374">可以在预览窗格中查看容器中的文件列表。</span><span class="sxs-lookup"><span data-stu-id="5d467-374">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="5d467-375">.zip</span><span class="sxs-lookup"><span data-stu-id="5d467-375">Zip</span></span>
    
- <span data-ttu-id="5d467-376">.gzip</span><span class="sxs-lookup"><span data-stu-id="5d467-376">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="5d467-377">部分索引项</span><span class="sxs-lookup"><span data-stu-id="5d467-377">Partially indexed items</span></span>

- <span data-ttu-id="5d467-378">如前面所述，邮箱中的部分索引项将包括在估计的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5d467-378">As previously explained, partially indexed items in mailboxes are included in the estimated search results.</span></span> <span data-ttu-id="5d467-379">SharePoint 和 OneDrive 中的部分索引项不会包括在估计的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="5d467-379">Partially indexed items from SharePoint and OneDrive aren't included in the estimated search results.</span></span> 
    
- <span data-ttu-id="5d467-380">如果部分索引项符合搜索查询（因为其他邮件或文档属性满足搜索条件），则它不会包含在未编入索引的项目的估计数中。</span><span class="sxs-lookup"><span data-stu-id="5d467-380">If a partially indexed item matches the search query (because other message or document properties meet the search criteria), it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="5d467-381">如果部分索引项被搜索条件排除在外，则它不会包括在未索引项的估计数中。</span><span class="sxs-lookup"><span data-stu-id="5d467-381">If a partially indexed item is excluded by the search criteria, it isn't included in the estimated number of unindexed items.</span></span> <span data-ttu-id="5d467-382">有关详细信息，请参阅 [Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="5d467-382">[Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md)</span></span>
