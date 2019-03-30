---
title: Office 365 中的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 或 Microsoft 365 中的合规性中心中的内容搜索工具搜索邮箱、SharePoint Online 网站、OneDrive 帐户、Microsoft 团队、Office 365 组和 Skype for business 对话中的内容。 您可以使用关键字搜索查询和搜索条件来缩小搜索结果的范围。 然后, 您可以预览和导出搜索结果。 内容搜索也是一个有效的工具, 可用于搜索可能与 GDPR 数据主体请求相关的内容。
ms.openlocfilehash: c9cbf135ce44f26322ca3a6972e0d8a7b749fc8c
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001015"
---
# <a name="content-search-in-office-365"></a><span data-ttu-id="418db-106">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="418db-106">Content Search in Office 365</span></span>

<span data-ttu-id="418db-107">您可以使用 office 365 或 Microsoft 365 中的合规性中心中的内容搜索电子数据展示工具在 office 365 组织中搜索就地项目, 如电子邮件、文档和即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="418db-107">You can use the Content Search eDiscovery tool in the compliance center in Office 365 or Microsoft 365 to search for in-place items such as email, documents, and instant messaging conversations in your Office 365 organization.</span></span> <span data-ttu-id="418db-108">使用此工具搜索这些 Office 365 服务中的项目:</span><span class="sxs-lookup"><span data-stu-id="418db-108">Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="418db-109">Exchange Online 邮箱和公用文件夹</span><span class="sxs-lookup"><span data-stu-id="418db-109">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="418db-110">SharePoint Online 网站和 OneDrive for business 帐户</span><span class="sxs-lookup"><span data-stu-id="418db-110">SharePoint Online sites and OneDrive for Business accounts</span></span>
    
- <span data-ttu-id="418db-111">Skype for business 对话</span><span class="sxs-lookup"><span data-stu-id="418db-111">Skype for Business conversations</span></span>
    
- <span data-ttu-id="418db-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="418db-112">Microsoft Teams</span></span> 
    
- <span data-ttu-id="418db-113">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="418db-113">Office 365 Groups</span></span>
    
<span data-ttu-id="418db-114">在运行内容搜索之后, 内容位置的数量和估计的搜索结果数将显示在搜索配置文件中。</span><span class="sxs-lookup"><span data-stu-id="418db-114">After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the search profile.</span></span> <span data-ttu-id="418db-115">您还可以快速查看统计信息, 例如与搜索查询匹配项最多的内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-115">You can also quickly view statistics, such as the content locations that have the most items that match the search query.</span></span> <span data-ttu-id="418db-116">运行搜索后, 可以预览结果或将其导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="418db-116">After you run a search, you can preview the results or export them to a local computer.</span></span>


## <a name="create-a-new-search"></a><span data-ttu-id="418db-117">创建新的搜索</span><span class="sxs-lookup"><span data-stu-id="418db-117">Create a new search</span></span>

<span data-ttu-id="418db-118">若要访问**内容搜索**页以运行搜索和预览和导出搜索结果, 管理员、合规专员或电子数据展示管理器必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="418db-118">To have access to the **Content search** page to run searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="418db-119">有关详细信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-119">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
1. <span data-ttu-id="418db-120">转到[https://compliance.microsoft.com](https://compliance.microsoft.com)并使用 Office 365 电子邮件地址和密码登录。</span><span class="sxs-lookup"><span data-stu-id="418db-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using your Office 365 email address and password.</span></span>
    
2. <span data-ttu-id="418db-121">单击 "**搜索** \> **内容搜索**"。</span><span class="sxs-lookup"><span data-stu-id="418db-121">Click **Search** \> **Content search**.</span></span>
    
3. <span data-ttu-id="418db-122">在 "**搜索**" 页上, 单击 " ![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新搜索**" 旁边的箭头。</span><span class="sxs-lookup"><span data-stu-id="418db-122">On the **Search** page, click the arrow next to ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span> 
    
    !["新建搜索" 下拉列表](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    <span data-ttu-id="418db-124">解析内部邮件传递的邮件服务器地址时，使用“内部 DNS 查找”选项卡可以指定是使用该服务器上安装的网络适配器上配置的 DNS 服务器，还是使用特定的 DNS 服务器。内部 DNS 服务器用于解析组织内部服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="418db-124">You can choose one of the following options:</span></span>
    
    - <span data-ttu-id="418db-125">**引导式搜索**-此选项将启动一个向导, 引导您完成创建搜索的向导。</span><span class="sxs-lookup"><span data-stu-id="418db-125">**Guided search** - This option starts a wizard that guides you through the creating the search.</span></span> <span data-ttu-id="418db-126">用于选择内容位置和构建搜索查询的用户界面与**新的搜索**选项相同。</span><span class="sxs-lookup"><span data-stu-id="418db-126">The user interface to select content locations and build the search query are the same as the **New search** option.</span></span> 
    
    - <span data-ttu-id="418db-127">**新搜索**-此选项显示一个已更新的用户界面, 以创建新的搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-127">**New search** - This option displays an updated user interface to create a new search.</span></span> <span data-ttu-id="418db-128">如果单击 "**新建搜索**", 这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="418db-128">This is the default option if you click **New search**.</span></span>
    
    - <span data-ttu-id="418db-129">**按 ID 列表搜索**-此选项允许您使用 Exchange id 列表搜索特定的电子邮件和其他邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="418db-129">**Search by ID List** - This option lets you search for specific email messages and other mailbox items using a list of Exchange IDs.</span></span> <span data-ttu-id="418db-130">若要创建 ID 列表搜索 (正式称为目标搜索), 请提交一个逗号分隔值 (CSV) 文件, 该文件标识要搜索的特定邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="418db-130">To create an ID list search (formally called a targeted search), you submit a comma separated value (CSV) file that identifies the specific mailbox items to search for.</span></span> <span data-ttu-id="418db-131">有关说明, 请参阅[在 Office 365 中准备用于 ID 列表内容搜索的 CSV 文件](csv-file-for-an-id-list-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-131">For instructions, see [Prepare a CSV file for an ID list Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
    
    <span data-ttu-id="418db-132">此过程中的其余步骤将遵循默认的新搜索工作流。</span><span class="sxs-lookup"><span data-stu-id="418db-132">The remainder of the steps in this procedure will follow the default new search workflow.</span></span>
    
4. <span data-ttu-id="418db-133">在下拉列表中单击 "**新建搜索**"。</span><span class="sxs-lookup"><span data-stu-id="418db-133">Click **New search** in the drop-down list.</span></span> 
    
5. <span data-ttu-id="418db-134">在 "**搜索查询**" 下, 指定以下内容。</span><span class="sxs-lookup"><span data-stu-id="418db-134">Under **Search query**, specify the following things.</span></span>
    
    ![指定要搜索的关键字、条件和位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - <span data-ttu-id="418db-136">**要**在 "**关键字**" 框中键入搜索查询的关键字。</span><span class="sxs-lookup"><span data-stu-id="418db-136">**Keywords to search for** - Type a search query in **Keywords** box.</span></span> <span data-ttu-id="418db-137">您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="418db-137">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="418db-138">您可以使用更复杂的查询, 这些查询使用布尔运算符, 例如**AND**、 **OR**、 **NOT**和**NEAR**。</span><span class="sxs-lookup"><span data-stu-id="418db-138">You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="418db-139">您还可以在文档中搜索敏感信息 (如社会保险号), 或搜索在外部共享的文档。</span><span class="sxs-lookup"><span data-stu-id="418db-139">You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally.</span></span> <span data-ttu-id="418db-140">如果将 "关键字" 框留空, 则位于指定内容位置的所有内容都将包含在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="418db-140">If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span>
    
      <span data-ttu-id="418db-141">或者, 也可以单击 "**显示关键字列表**" 复选框, 并在每行中键入关键字。</span><span class="sxs-lookup"><span data-stu-id="418db-141">Alternatively, you can click the **Show keyword list** checkbox and the type a keyword in each row.</span></span> <span data-ttu-id="418db-142">如果这样做, 每行上的关键字都将通过逻辑运算符 ( **c:s**) 连接, 该运算符在创建的搜索查询中的**OR**运算符的功能类似。</span><span class="sxs-lookup"><span data-stu-id="418db-142">If you do this, the keywords on each row are connected by a logical operator ( **c:s**) that is similar in functionality to the **OR** operator in the search query that's created.</span></span> 
    
      <span data-ttu-id="418db-143">为什么要使用关键字列表？</span><span class="sxs-lookup"><span data-stu-id="418db-143">Why use the keyword list?</span></span> <span data-ttu-id="418db-144">您可以获取显示与每个关键字匹配的项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-144">You can get statistics that show how many items match each keyword.</span></span> <span data-ttu-id="418db-145">这可以帮助您快速确定哪些关键字最有效 (最少)。</span><span class="sxs-lookup"><span data-stu-id="418db-145">This can help you quickly identify which keywords are the most (and least) effective.</span></span> <span data-ttu-id="418db-146">您还可以在行中使用关键字短语 (括在括号中)。</span><span class="sxs-lookup"><span data-stu-id="418db-146">You can also use a keyword phrase (surrounded by parentheses) in a row.</span></span> <span data-ttu-id="418db-147">有关搜索统计信息的详细信息, 请参阅[查看内容搜索结果的关键字统计](view-keyword-statistics-for-content-search.md)信息。</span><span class="sxs-lookup"><span data-stu-id="418db-147">For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="418db-148">为了帮助减少由大型关键字列表导致的问题, 您现在限制为关键字列表中的最多20行。</span><span class="sxs-lookup"><span data-stu-id="418db-148">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list.</span></span>
    
    - <span data-ttu-id="418db-149">**条件**-您可以添加搜索条件以缩小搜索范围, 并返回一组更细化的结果。</span><span class="sxs-lookup"><span data-stu-id="418db-149">**Conditions** - You can add search conditions to narrow a search and return a more refined set of results.</span></span> <span data-ttu-id="418db-150">每个条件都会向搜索查询添加一个子句, 该子句在您开始搜索时创建并运行。</span><span class="sxs-lookup"><span data-stu-id="418db-150">Each condition adds a clause to the search query that is created and run when you start the search.</span></span> <span data-ttu-id="418db-151">条件以逻辑方式连接到关键字查询 (在 "关键字" 框中指定), 逻辑运算符 ( **c:c**) 与**AND**运算符的功能相似。</span><span class="sxs-lookup"><span data-stu-id="418db-151">A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator ( **c:c**) that is similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="418db-152">这意味着项目必须同时满足关键字查询和要包含在结果中的一个或多个条件。</span><span class="sxs-lookup"><span data-stu-id="418db-152">That means that items have to satisfy both the keyword query and one or more conditions to be included in the results.</span></span> <span data-ttu-id="418db-153">这就是条件如何帮助缩小结果范围的原理。</span><span class="sxs-lookup"><span data-stu-id="418db-153">This is how conditions help to narrow your results.</span></span> <span data-ttu-id="418db-154">有关可在搜索查询中使用的条件的列表和说明, 请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的 "搜索条件" 部分。</span><span class="sxs-lookup"><span data-stu-id="418db-154">For a list and description of conditions that you can use in a search query, see the "Search conditions" section in [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md#search-conditions).</span></span>
    
       - <span data-ttu-id="418db-155">**位置**-选择要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-155">**Locations** - Choose the content locations to search.</span></span>
    
      - <span data-ttu-id="418db-156">**所有位置**-使用此选项可搜索组织中的所有内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-156">**All locations** - Use this option to search all content locations in your organization.</span></span> <span data-ttu-id="418db-157">这包括所有 Exchange 邮箱中的电子邮件 (包括所有非活动邮箱、所有 Office 365 组的邮箱、所有 Microsoft 团队的邮箱)、所有 Skype for business 对话、所有 SharePoint 和 OneDrive for business 网站 (包括网站对于所有 Office 365 组和 Microsoft 团队) 和所有 Exchange 公用文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="418db-157">This includes email in all Exchange mailboxes (including all inactive mailboxes, mailboxes for all Office 365 Groups, mailboxes for all Microsoft Teams), all Skype for Business conversations, all SharePoint and OneDrive for Business sites (including the sites for all Office 365 Groups and Microsoft Teams), and items in all Exchange public folders.</span></span>
    
      - <span data-ttu-id="418db-158">**特定位置**-使用此选项可搜索特定的内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-158">**Specific locations** - Use this option to search specific content locations.</span></span> <span data-ttu-id="418db-159">您可以搜索特定 Office 365 服务的所有内容位置 (例如, 搜索所有 Exchange 邮箱或搜索所有 SharePoint 网站), 也可以在显示的任何 Office 365 服务中搜索特定位置。</span><span class="sxs-lookup"><span data-stu-id="418db-159">You can search all content locations for a specific Office 365 service (such as searching all Exchange mailboxes or search all SharePoint sites) or you can search specific locations in any of the Office 365 services that are displayed.</span></span> 
    
        ![用于选择要搜索的内容位置的用户界面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         <span data-ttu-id="418db-161">请注意, 您还可以向要搜索的 Exchange 邮箱列表中添加通讯组。</span><span class="sxs-lookup"><span data-stu-id="418db-161">Note that you can also add distribution groups to the list of Exchange mailboxes to search.</span></span> <span data-ttu-id="418db-162">对于通讯组, 将搜索组成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-162">For distribution groups, the mailboxes of group members are searched.</span></span> <span data-ttu-id="418db-163">请注意, 不支持动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="418db-163">Note that dynamic distribution groups aren't supported.</span></span>
    
       <span data-ttu-id="418db-164">**重要说明:** 当您搜索所有邮箱位置或仅搜索特定邮箱时, 当您导出内容搜索的结果时, 将包含 MyAnalytics 中的数据以及保存到用户邮箱的其他 Office 365 应用程序中的数据。</span><span class="sxs-lookup"><span data-stu-id="418db-164">**Important:** When you search all mailbox locations or just specific mailboxes, data from MyAnalytics and other Office 365 applications that's saved to user mailboxes will be included when you export the results of a Content Search.</span></span> <span data-ttu-id="418db-165">此数据不会包括在估计的搜索结果中, 也不会对预览提供支持。</span><span class="sxs-lookup"><span data-stu-id="418db-165">This data will not be included in the estimated search results and it won't be available for preview.</span></span> <span data-ttu-id="418db-166">它将仅在导出和下载搜索结果时包括;有关内容搜索的详细信息, 请参阅[从 MyAnalytics 和其他 Office 365 应用程序中导出数据](#exporting-data-from-myanalytics-and-other-office-365-applications)一节。</span><span class="sxs-lookup"><span data-stu-id="418db-166">It will only be included when you export and download the search results; see [Exporting data from MyAnalytics and other Office 365 applications](#exporting-data-from-myanalytics-and-other-office-365-applications) in the "More information about content search" section.</span></span> 
    
6. <span data-ttu-id="418db-167">设置完搜索查询后, 请单击 "**保存&amp;运行**"。</span><span class="sxs-lookup"><span data-stu-id="418db-167">After you've set up your search query, click **Save &amp; run**.</span></span>
    
7. <span data-ttu-id="418db-168">在 "**保存搜索**" 页上, 键入搜索的名称和可帮助标识搜索的可选说明。</span><span class="sxs-lookup"><span data-stu-id="418db-168">On the **Save search** page, type a name for the search, and an optional description that helps identify the search.</span></span> <span data-ttu-id="418db-169">请注意, 搜索的名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="418db-169">Note that the name of the search has to be unique in your organization.</span></span> 
    
8. <span data-ttu-id="418db-170">单击 "**保存**" 以启动搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-170">Click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="418db-171">在保存并运行搜索后, 搜索返回的任何结果都将显示在结果窗格中。</span><span class="sxs-lookup"><span data-stu-id="418db-171">After you save and run the search, any results returned by the search are displayed in the results pane.</span></span> <span data-ttu-id="418db-172">根据您配置预览设置的方式, 可以显示搜索结果, 也可以单击 "**预览结果**" 进行查看。</span><span class="sxs-lookup"><span data-stu-id="418db-172">Depending on how you have the preview setting configured, the search results are display or you have to click **Preview results** to view them.</span></span> <span data-ttu-id="418db-173">有关详细信息, 请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="418db-173">See the next section for details.</span></span> 
    
<span data-ttu-id="418db-174">若要再次访问此内容搜索或访问 "**内容搜索**" 页上列出的其他内容搜索, 请选择搜索, 然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="418db-174">To access this content search again or access other content searches listed on the **Content search** page, select the search and then click **Open**.</span></span> 
  
<span data-ttu-id="418db-175">若要清除结果或创建新搜索, 请单击!["添加](media/O365-MDM-CreatePolicy-AddIcon.gif)图标" "**新建搜索**"。</span><span class="sxs-lookup"><span data-stu-id="418db-175">To clear the results or create a new search, click ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **New search**.</span></span> 

  
## <a name="preview-search-results"></a><span data-ttu-id="418db-176">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="418db-176">Preview search results</span></span>

<span data-ttu-id="418db-177">预览搜索结果有两个配置设置。</span><span class="sxs-lookup"><span data-stu-id="418db-177">There are two configuration settings for previewing search results.</span></span> <span data-ttu-id="418db-178">在运行新的新搜索或打开现有搜索后, 单击 "\* \* 单个结果 \* \*" 以查看以下预览设置:</span><span class="sxs-lookup"><span data-stu-id="418db-178">After you run a new a new search or open an existing search, click \*\* Individual results \*\* to view the following preview settings:</span></span> 
  
![预览搜索结果设置](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. <span data-ttu-id="418db-180">"**自动预览结果**"-此设置将在您运行搜索后显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="418db-180">**Preview results automatically** - This setting displays the search results after you a run a search.</span></span>
    
2. <span data-ttu-id="418db-181">"**手动预览结果**"-此设置在 "搜索结果" 窗格中显示占位符, 并显示您必须单击以显示搜索结果的 "**预览结果**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="418db-181">**Preview results manually** - This setting displays placeholders in the search results pane, and displays the **Preview results** button that you have to click to display the search results.</span></span> <span data-ttu-id="418db-182">这是默认设置;它有助于提高搜索性能, 因为打开现有搜索时不会自动显示搜索结果。</span><span class="sxs-lookup"><span data-stu-id="418db-182">This is the default setting; it helps enhance search performance by not automatically displaying the search results when you open an existing search.</span></span> 
    
<span data-ttu-id="418db-183">与可预览的项目数相关的限制。</span><span class="sxs-lookup"><span data-stu-id="418db-183">There are limits related to how many items are available to be previewed.</span></span> <span data-ttu-id="418db-184">有关详细信息, 请参阅[对内容搜索的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-184">For more information, see [Limits for Content Search](limits-for-content-search.md).</span></span> 
  
<span data-ttu-id="418db-185">有关可预览的受支持文件类型的列表, 请参阅在 "有关内容搜索的详细信息" 部分[预览搜索结果](#previewing-search-results)。</span><span class="sxs-lookup"><span data-stu-id="418db-185">For a list of supported file types that can be previewed, see [Previewing search results](#previewing-search-results) in the "More information about content search" section.</span></span> <span data-ttu-id="418db-186">如果文件类型不支持预览或下载文档的副本, 则可以单击 "**下载原始文件**" 将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="418db-186">If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer.</span></span> <span data-ttu-id="418db-187">对于 .aspx 网页, 如果您可能没有访问该页面的权限, 则会包含该页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="418db-187">For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
  
<span data-ttu-id="418db-188">另请注意, 未编制索引的项目不能进行预览。</span><span class="sxs-lookup"><span data-stu-id="418db-188">Also note that unindexed items aren't available for previewing.</span></span>
  
## <a name="view-information-and-statistics-about-a-search"></a><span data-ttu-id="418db-189">查看有关搜索的信息和统计信息</span><span class="sxs-lookup"><span data-stu-id="418db-189">View information and statistics about a search</span></span>

<span data-ttu-id="418db-190">在创建和运行内容搜索之后, 您可以查看有关估计的搜索结果的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-190">After you create and run a content search, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="418db-191">其中包括搜索结果的摘要、查询统计信息 (如包含与搜索查询匹配的项目的内容位置数) 以及具有最匹配项的内容位置的名称。</span><span class="sxs-lookup"><span data-stu-id="418db-191">This includes a summary of the search results, the query statistics such as the number of content locations with items that match the search query, and the name of content locations that have the most matching items.</span></span> <span data-ttu-id="418db-192">您可以显示一个或多个内容搜索的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-192">You can display statistics for one or more content searches.</span></span> <span data-ttu-id="418db-193">这样, 您就可以快速比较多个搜索的结果, 并做出有关搜索查询有效性的决定。</span><span class="sxs-lookup"><span data-stu-id="418db-193">This lets you to quickly compare the results for multiple searches and make decisions about the effectiveness of your search queries.</span></span>
  
<span data-ttu-id="418db-194">您还可以将搜索统计信息和关键字统计信息下载到 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="418db-194">You can also download the search statistics and keyword statistics to a CSV file.</span></span> <span data-ttu-id="418db-195">这使您可以使用 Excel 中的筛选和排序功能比较结果, 并准备您的搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="418db-195">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
<span data-ttu-id="418db-196">查看搜索统计信息:</span><span class="sxs-lookup"><span data-stu-id="418db-196">To view search statistics:</span></span>
  
1. <span data-ttu-id="418db-197">在 "**内容搜索**" 页上, 单击 "**打开**", 然后单击要查看其统计信息的搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-197">On the **Content search** page, click **Open** and then click the search that you want to view the statistic for.</span></span> 
    
2. <span data-ttu-id="418db-198">在 "飞出" 页面上, 单击 "**打开查询**"。</span><span class="sxs-lookup"><span data-stu-id="418db-198">On the fly out page, click **Open query**.</span></span> 
    
3. <span data-ttu-id="418db-199">在 "**单个结果**" 下拉列表中, 单击 "**搜索配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="418db-199">In the **Individual results** drop down list, click **Search profile**.</span></span>
    
4. <span data-ttu-id="418db-200">在 "**类型**" 下拉列表中, 根据您要查看的搜索统计信息, 单击下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="418db-200">In the **Type** drop down list, click one of the following options depending on the search statistics you want to view.</span></span> 
    
  - <span data-ttu-id="418db-201">**摘要**-显示搜索的每个类型的内容位置的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-201">**Summary** - Displays statistics for each type of content locations searched.</span></span> <span data-ttu-id="418db-202">此内容包含与搜索查询匹配的项目的内容位置数, 以及搜索结果项目的总数和大小。</span><span class="sxs-lookup"><span data-stu-id="418db-202">This contents the number of content locations that contained items that matched the search query, and the total number and size of search result items.</span></span> <span data-ttu-id="418db-203">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="418db-203">This is the default setting.</span></span>
    
  - <span data-ttu-id="418db-204">**查询**-显示有关搜索查询的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-204">**Queries** - Displays statistics about the search query.</span></span> <span data-ttu-id="418db-205">这包括查询统计信息适用的内容位置的类型, 这些统计信息适用于的搜索查询部分 (请注意,**主要**是指整个搜索查询), 包含的项目的内容位置数匹配搜索查询, 以及与搜索查询匹配的已找到的 (在指定的内容位置) 的总数量和大小以及项目。</span><span class="sxs-lookup"><span data-stu-id="418db-205">This includes the type of content location the query statistics are applicable to, part of the search query the statistics are applicable to (note that **Primary** indicates the entire search query), the number of the content locations that contain items that match the search query, and the total number and size and items that were found (in the specified content location) that match the search query.</span></span> <span data-ttu-id="418db-206">请注意, 还会显示未编制索引的项目 (也称为部分索引项目) 的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-206">Note that statistics for unindexed items (also called partially indexed items) are also displayed.</span></span> <span data-ttu-id="418db-207">但是, 只有来自邮箱的部分索引项才包含在统计信息中。</span><span class="sxs-lookup"><span data-stu-id="418db-207">However, only partially indexed items from mailboxes are included in the statistics.</span></span> <span data-ttu-id="418db-208">来自 SharePoint 和 OneDrive 的部分索引项目不包括在统计中。</span><span class="sxs-lookup"><span data-stu-id="418db-208">Partially indexed items from SharePoint and OneDrive are not included in the statistics.</span></span>
    
  - <span data-ttu-id="418db-209">**顶部位置**-显示与搜索查询在搜索的每个内容位置中的搜索查询匹配的项目数的统计信息。</span><span class="sxs-lookup"><span data-stu-id="418db-209">**Top locations** - Displays statistics about the number of items that match the search query in each content location that was searched.</span></span> <span data-ttu-id="418db-210">将显示顶部的1000位置。</span><span class="sxs-lookup"><span data-stu-id="418db-210">The top 1,000 locations are displayed.</span></span>
    
<span data-ttu-id="418db-211">有关搜索统计信息的详细信息, 请参阅[查看内容搜索结果的关键字统计](view-keyword-statistics-for-content-search.md)信息。</span><span class="sxs-lookup"><span data-stu-id="418db-211">For more detailed information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
  
## <a name="export-search-results"></a><span data-ttu-id="418db-212">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="418db-212">Export search results</span></span>

<span data-ttu-id="418db-213">成功运行搜索后, 可以将搜索结果导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="418db-213">After a search is successfully run, you can export the search results to a local computer.</span></span> <span data-ttu-id="418db-214">导出电子邮件结果时, 可以将其作为 PST 文件或单个邮件 (.msg 文件) 下载到您的计算机上。</span><span class="sxs-lookup"><span data-stu-id="418db-214">When you export email results, they can be downloaded to your computer as PST files or as individual messages (.msg files).</span></span> <span data-ttu-id="418db-215">当您从 SharePoint 和 OneDrive 网站导出内容时, 会导出本机 Office 文档的副本。</span><span class="sxs-lookup"><span data-stu-id="418db-215">When you export content from SharePoint and OneDrive sites, copies of native Office documents are exported.</span></span> <span data-ttu-id="418db-216">导出的搜索结果中还包含其他文档和报告。</span><span class="sxs-lookup"><span data-stu-id="418db-216">There are also additional documents and reports that are included with the exported search results.</span></span> <span data-ttu-id="418db-217">此外, 您还可以导出搜索结果报告, 而不是导出实际项目。</span><span class="sxs-lookup"><span data-stu-id="418db-217">You can also just export the search results report and not the actual items.</span></span>
  
<span data-ttu-id="418db-218">若要导出搜索结果:</span><span class="sxs-lookup"><span data-stu-id="418db-218">To export search results:</span></span>
  
1. <span data-ttu-id="418db-219">在 "**内容搜索**" 页上, 单击要为其导出搜索结果的搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-219">On the **Content search** page, click the search that you want to export the search results for.</span></span> 
    
2. <span data-ttu-id="418db-220">在 "飞出" 页面上![, 单击 "](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **更多**" "导出搜索结果" 图标, 然后单击 "**导出结果**"。</span><span class="sxs-lookup"><span data-stu-id="418db-220">On the fly out page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Export results**.</span></span> <span data-ttu-id="418db-221">请注意, 您还可以导出搜索结果报告。</span><span class="sxs-lookup"><span data-stu-id="418db-221">Note that you can also export a search results report.</span></span>
    
3. <span data-ttu-id="418db-222">完成 "**导出结果**" 飞出页面上的部分。</span><span class="sxs-lookup"><span data-stu-id="418db-222">Complete the sections on the **Export results** fly out page.</span></span> <span data-ttu-id="418db-223">请务必使用滚动条查看所有导出选项。</span><span class="sxs-lookup"><span data-stu-id="418db-223">Be sure to use the scroll bar to view all export options.</span></span> 
    
<span data-ttu-id="418db-224">有关更多详细说明和疑难解答提示, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="418db-224">For more detailed instructions and troubleshooting tips, see:</span></span>
  
- [<span data-ttu-id="418db-225">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="418db-225">Export Content Search results</span></span>](export-search-results.md)
    
- [<span data-ttu-id="418db-226">导出内容搜索报告</span><span class="sxs-lookup"><span data-stu-id="418db-226">Export a Content Search report</span></span>](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a><span data-ttu-id="418db-227">有关内容搜索的详细信息</span><span class="sxs-lookup"><span data-stu-id="418db-227">More information about content search</span></span>

<span data-ttu-id="418db-228">有关内容搜索的详细信息, 请参阅以下各节。</span><span class="sxs-lookup"><span data-stu-id="418db-228">See the following sections for more information about content searches.</span></span>
  
[<span data-ttu-id="418db-229">内容搜索限制</span><span class="sxs-lookup"><span data-stu-id="418db-229">Content search limits</span></span>](#content-search-limits)
  
[<span data-ttu-id="418db-230">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="418db-230">Building a search query</span></span>](#building-a-search-query)
  
[<span data-ttu-id="418db-231">搜索 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="418db-231">Searching OneDrive accounts</span></span>](#searching-onedrive-accounts)
  
[<span data-ttu-id="418db-232">搜索 Microsoft 团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="418db-232">Searching Microsoft Teams and Office 365 Groups</span></span>](#searching-microsoft-teams-and-office-365-groups)
  
[<span data-ttu-id="418db-233">搜索非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="418db-233">Searching inactive mailboxes</span></span>](#searching-inactive-mailboxes)
  
[<span data-ttu-id="418db-234">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="418db-234">Previewing search results</span></span>](#previewing-search-results)
  
[<span data-ttu-id="418db-235">部分索引项目</span><span class="sxs-lookup"><span data-stu-id="418db-235">Partially indexed items</span></span>](#partially-indexed-items)
  
[<span data-ttu-id="418db-236">从 MyAnalytics 和其他 Office 365 应用程序导出数据</span><span class="sxs-lookup"><span data-stu-id="418db-236">Exporting data from MyAnalytics and other Office 365 applications</span></span>](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a><span data-ttu-id="418db-237">内容搜索限制</span><span class="sxs-lookup"><span data-stu-id="418db-237">Content search limits</span></span>

- <span data-ttu-id="418db-238">有关应用于内容搜索功能的限制的说明, 请参阅[对内容搜索的限制](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-238">For a description of the limits that are applied to the Content Search feature, see [Limits for Content Search](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="418db-239">Microsoft 收集由所有 Office 365 组织运行的内容搜索的性能信息。</span><span class="sxs-lookup"><span data-stu-id="418db-239">Microsoft collects performance information for Content Searches run by all Office 365 organizations.</span></span> <span data-ttu-id="418db-240">虽然搜索查询的复杂性可能会影响搜索时间, 但影响搜索所用时间的最大因素是搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="418db-240">While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched.</span></span> <span data-ttu-id="418db-241">尽管 Microsoft 不提供搜索时间的服务级别协议, 但下表根据搜索中包括的邮箱数量列出了内容搜索的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="418db-241">Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="418db-242">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="418db-242">**Number of mailboxes**</span></span>|<span data-ttu-id="418db-243">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="418db-243">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="418db-244">100</span><span class="sxs-lookup"><span data-stu-id="418db-244">100</span></span>  <br/> |<span data-ttu-id="418db-245">30 秒</span><span class="sxs-lookup"><span data-stu-id="418db-245">30 seconds</span></span>  <br/> |
|<span data-ttu-id="418db-246">1,000</span><span class="sxs-lookup"><span data-stu-id="418db-246">1,000</span></span>  <br/> |<span data-ttu-id="418db-247">45秒</span><span class="sxs-lookup"><span data-stu-id="418db-247">45 seconds</span></span>  <br/> |
|<span data-ttu-id="418db-248">10,000</span><span class="sxs-lookup"><span data-stu-id="418db-248">10,000</span></span>  <br/> |<span data-ttu-id="418db-249">4 分钟</span><span class="sxs-lookup"><span data-stu-id="418db-249">4 minutes</span></span>  <br/> |
|<span data-ttu-id="418db-250">25000</span><span class="sxs-lookup"><span data-stu-id="418db-250">25,000</span></span>  <br/> |<span data-ttu-id="418db-251">10 分钟</span><span class="sxs-lookup"><span data-stu-id="418db-251">10 minutes</span></span>  <br/> |
|<span data-ttu-id="418db-252">50000</span><span class="sxs-lookup"><span data-stu-id="418db-252">50,000</span></span>  <br/> |<span data-ttu-id="418db-253">20 分钟</span><span class="sxs-lookup"><span data-stu-id="418db-253">20 minutes</span></span>  <br/> |
|<span data-ttu-id="418db-254">100,000</span><span class="sxs-lookup"><span data-stu-id="418db-254">100,000</span></span>  <br/> |<span data-ttu-id="418db-255">25 分钟</span><span class="sxs-lookup"><span data-stu-id="418db-255">25 minutes</span></span>  <br/> |
  
### <a name="building-a-search-query"></a><span data-ttu-id="418db-256">生成搜索查询</span><span class="sxs-lookup"><span data-stu-id="418db-256">Building a search query</span></span>

<span data-ttu-id="418db-257">有关创建搜索查询、使用布尔搜索运算符和搜索条件以及搜索与组织外部用户共享的敏感信息类型和内容的详细信息, 请参阅[关键字查询和搜索条件用于内容搜索](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-257">For detailed information about creating a search query, using Boolean search operators and search conditions, and searching for sensitive information types and content shared with users outside your organization, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="418db-258">在使用关键字列表创建搜索查询时, 请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="418db-258">Keeping the following things in mind when using the keyword list to create a search query.</span></span>
  
- <span data-ttu-id="418db-259">您必须选择 "**显示关键字列表**" 复选框, 然后在单独的行中键入每个关键字, 以创建搜索查询, 在该查询中, 每行中的关键字 (或关键字短语) 通过**or**运算符连接。</span><span class="sxs-lookup"><span data-stu-id="418db-259">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator.</span></span> <span data-ttu-id="418db-260">如果只是将关键字列表粘贴到关键字框中或在键入关键字后按**enter**键, 则不会通过**or**运算符连接。</span><span class="sxs-lookup"><span data-stu-id="418db-260">If you just paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator.</span></span> <span data-ttu-id="418db-261">下面是添加关键字列表的错误和正确示例。</span><span class="sxs-lookup"><span data-stu-id="418db-261">Here are incorrect and correct example of adding a list of keywords.</span></span> 
    
    <span data-ttu-id="418db-262">**不正确**</span><span class="sxs-lookup"><span data-stu-id="418db-262">**Incorrect**</span></span>
    
    ![设置关键字列表格式的错误方法 (通过将列表粘贴到关键字框中)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="418db-264">**正确**</span><span class="sxs-lookup"><span data-stu-id="418db-264">**Correct**</span></span>
    
    ![设置关键字列表格式的正确方法 (通过选中 "checkbox" 和 "粘贴" 列表)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- <span data-ttu-id="418db-266">您还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语列表, 然后将列表复制并粘贴到关键字列表中。</span><span class="sxs-lookup"><span data-stu-id="418db-266">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list in to the keyword list.</span></span> <span data-ttu-id="418db-267">若要执行此操作, 必须选中 "**显示关键字列表**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="418db-267">To do this, you have to select the **Show keyword list** check box.</span></span> <span data-ttu-id="418db-268">然后, 单击 "关键字" 列表中的第一行并粘贴列表。</span><span class="sxs-lookup"><span data-stu-id="418db-268">Then, click the first row in the keyword list and paste your list.</span></span> <span data-ttu-id="418db-269">Excel 或文本文件中的每一行将粘贴到关键字列表中单独的行中。</span><span class="sxs-lookup"><span data-stu-id="418db-269">Each line from the Excel or text file will be pasted in to separate row in the keyword list.</span></span> 
    
- <span data-ttu-id="418db-270">使用关键字列表创建查询之后, 最好验证搜索查询语法, 以使搜索查询成为您预期的结果。</span><span class="sxs-lookup"><span data-stu-id="418db-270">After you create a query using the keyword list, it's a good idea to verify the search query syntax to make the search query is what you intended.</span></span> <span data-ttu-id="418db-271">在 "详细信息" 窗格的 "**查询**" 下显示的搜索查询中, 关键字由文本 **(c:s)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="418db-271">In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**.</span></span> <span data-ttu-id="418db-272">这表示关键字通过类似于功能的逻辑运算符连接到**OR**运算符。</span><span class="sxs-lookup"><span data-stu-id="418db-272">This indicates that the keywords are connected by a logical operator similar in functionality to the **OR** operator.</span></span> <span data-ttu-id="418db-273">同样, 如果您的搜索查询包含条件, 关键字和条件由文本 **(c:c)** 分隔。</span><span class="sxs-lookup"><span data-stu-id="418db-273">Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**.</span></span> <span data-ttu-id="418db-274">这表示关键字连接到了与**and**运算符的功能类似的逻辑运算符的条件。</span><span class="sxs-lookup"><span data-stu-id="418db-274">This indicates that the keywords are connected to the conditions with a logical operator similar in functionality to the **AND** operator.</span></span> <span data-ttu-id="418db-275">下面的示例展示了在使用关键字列表和条件时生成的搜索查询 (在详细信息窗格中)。</span><span class="sxs-lookup"><span data-stu-id="418db-275">Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用关键字列表和条件时创建的查询示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- <span data-ttu-id="418db-277">运行内容搜索时, Office 365 将自动检查您的搜索查询中是否有不受支持的字符, 以及可能不大写的布尔运算符。</span><span class="sxs-lookup"><span data-stu-id="418db-277">When you run a content search, Office 365 automatically checks your search query for unsupported characters and for Boolean operators that might not be capitalized.</span></span> <span data-ttu-id="418db-278">不受支持的字符通常是隐藏的, 通常会导致搜索错误或返回意外的结果。</span><span class="sxs-lookup"><span data-stu-id="418db-278">Unsupported characters are often hidden and typically cause a search error or return unintended results.</span></span> <span data-ttu-id="418db-279">有关检查不受支持的字符的详细信息, 请参阅[检查内容搜索查询是否有错误](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-279">For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
- <span data-ttu-id="418db-280">如果您有包含非英语字符关键字的搜索查询 (如中文字符), 您可以在内容搜索](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)中单击 "**查询语言-国家/地区**![查询语言-国家/地区" 图标, 然后选择language-搜索的国家/地区区域性代码值。</span><span class="sxs-lookup"><span data-stu-id="418db-280">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you can click **Query language-country/region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) and select a language-country culture code value for the search.</span></span> <span data-ttu-id="418db-281">请注意, 默认语言/区域是非特定的。</span><span class="sxs-lookup"><span data-stu-id="418db-281">Note that the default language/region is neutral.</span></span> <span data-ttu-id="418db-282">如何判断是否需要更改内容搜索的语言设置？</span><span class="sxs-lookup"><span data-stu-id="418db-282">How can you tell if you need to change the language setting for a content search?</span></span> <span data-ttu-id="418db-283">如果您是某些内容位置包含您要搜索的非英语字符, 但搜索不返回任何结果, 则可能是语言设置可能导致的原因。</span><span class="sxs-lookup"><span data-stu-id="418db-283">If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span> 
  
### <a name="searching-onedrive-accounts"></a><span data-ttu-id="418db-284">搜索 OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="418db-284">Searching OneDrive accounts</span></span>

- <span data-ttu-id="418db-285">若要收集组织中的 onedrive 网站的 url 列表, 请参阅[创建组织中所有 onedrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="418db-285">To collect a list of the URLs for the OneDrive sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> <span data-ttu-id="418db-286">本文中的此脚本创建一个文本文件, 其中包含所有 OneDrive 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="418db-286">This script in this article creates a text file that contains a list of all OneDrive sites.</span></span> <span data-ttu-id="418db-287">若要运行此脚本, 您必须安装并使用 SharePoint Online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="418db-287">To run this script, you'll have to install and use the SharePoint Online Management Shell.</span></span> <span data-ttu-id="418db-288">请务必将组织的 "我的网站" 域的 URL 追加到要搜索的每个 OneDrive 站点。</span><span class="sxs-lookup"><span data-stu-id="418db-288">Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search.</span></span> <span data-ttu-id="418db-289">这是包含所有 OneDrive 的域;例如, `https://contoso-my.sharepoint.com`。</span><span class="sxs-lookup"><span data-stu-id="418db-289">This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`.</span></span> <span data-ttu-id="418db-290">下面的示例展示了用户的 OneDrive 网站的 URL: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="418db-290">Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    
    <span data-ttu-id="418db-291">在极少数情况下, 某人的用户主体名称 (UPN) 发生更改时, 其 OneDrive 位置的 URL 也将更改以包含新的 UPN。</span><span class="sxs-lookup"><span data-stu-id="418db-291">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive location will also be changed to incorporate the new UPN.</span></span> <span data-ttu-id="418db-292">如果发生这种情况, 您必须通过添加用户的新 OneDrive URL 并删除旧 URL 来修改内容搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-292">If this happens, you'll have to modify a content search by adding the user's new OneDrive URL and removing the old one.</span></span>
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="418db-293">搜索 Microsoft 团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="418db-293">Searching Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="418db-294">您可以搜索与 Office 365 组或 Microsoft 团队相关联的邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-294">You can search the mailbox that's associated with an Office 365 Group or a Microsoft Team.</span></span> <span data-ttu-id="418db-295">由于 Microsoft 团队是基于 Office 365 组构建的, 因此搜索它们非常相似。</span><span class="sxs-lookup"><span data-stu-id="418db-295">Because Microsoft Teams are built on Office 365 Groups, searching them is very similar.</span></span> <span data-ttu-id="418db-296">在这两种情况下, 仅搜索组或工作组邮箱;不搜索组或工作组成员的邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-296">In both cases, only the group or team mailbox is searched; the mailboxes of the group or team members aren't searched.</span></span> <span data-ttu-id="418db-297">若要搜索这些文件, 您必须将其专门添加到搜索中。</span><span class="sxs-lookup"><span data-stu-id="418db-297">To search them, you have to specifically add them to the search.</span></span>
  
<span data-ttu-id="418db-298">在 Microsoft 团队和 Office 365 组中搜索内容时, 请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="418db-298">Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
  
- <span data-ttu-id="418db-299">若要搜索位于 Microsoft 团队和 Office 365 组中的内容, 您必须指定与团队或组相关联的邮箱和 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="418db-299">To search for content located in Microsoft Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
- <span data-ttu-id="418db-300">在 Exchange Online 中运行**remove-unifiedgroup** cmdlet, 以查看 Microsoft 团队或 Office 365 组的属性。</span><span class="sxs-lookup"><span data-stu-id="418db-300">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a Microsoft Team or an Office 365 Group.</span></span> <span data-ttu-id="418db-301">如果要获取与团队或组相关联的网站的 URL, 这是一种很好的方法。</span><span class="sxs-lookup"><span data-stu-id="418db-301">This is a good way to get the URL for the site that's associated with a team or a group.</span></span> <span data-ttu-id="418db-302">例如, 以下命令将显示名为 "高级领导" 团队的 Office 365 组的选定属性:</span><span class="sxs-lookup"><span data-stu-id="418db-302">For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="418db-303">若要运行**remove-unifiedgroup** cmdlet, 您必须在 Exchange Online 中分配 "仅查看收件人" 角色, 或者是分配了 "仅查看收件人" 角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="418db-303">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="418db-304">在搜索用户的邮箱时, 不会搜索用户是其成员的任何 Microsoft 团队或 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="418db-304">When a user's mailbox is searched, any Microsoft Team or Office 365 Group that the user is a member of won't be searched.</span></span> <span data-ttu-id="418db-305">同样, 当您搜索 Microsoft 团队或 Office 365 组时, 仅搜索您指定的组邮箱和组网站;除非将组成员的邮箱和 OneDrive for business 帐户显式添加到搜索中, 否则不会搜索这些帐户。</span><span class="sxs-lookup"><span data-stu-id="418db-305">Similarly, when you search a Microsoft Team or an Office 365 Group, only the group mailbox and group site that you specify is searched; the mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
- <span data-ttu-id="418db-306">若要获取 microsoft 团队或 Office 365 组成员的列表, 您可以在 Microsoft 365 管理中心的 "**家庭\>组**" 页上查看属性。</span><span class="sxs-lookup"><span data-stu-id="418db-306">To get a list of the members of a Microsoft Team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="418db-307">或者, 您可以在 Exchange Online PowerShell 中运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="418db-307">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="418db-308">若要运行**UnifiedGroupLinks** cmdlet, 您必须在 Exchange Online 中分配 "仅查看收件人" 角色, 或者是分配了 "仅查看收件人" 角色的角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="418db-308">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
- <span data-ttu-id="418db-309">属于 microsoft 团队渠道的对话存储在与 microsoft 团队相关联的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="418db-309">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team.</span></span> <span data-ttu-id="418db-310">同样, 在频道中共享的工作组成员的文件存储在团队的 SharePoint 网站上。</span><span class="sxs-lookup"><span data-stu-id="418db-310">Similarly, files that team members share in a channel are stored on the team's SharePoint site.</span></span> <span data-ttu-id="418db-311">因此, 您必须将 Microsoft 团队邮箱和 SharePoint 网站添加为内容位置, 以便在频道中搜索对话和文件。</span><span class="sxs-lookup"><span data-stu-id="418db-311">Therefore, you have to add the Microsoft Team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
- <span data-ttu-id="418db-312">或者, 在 Microsoft 团队中作为聊天列表一部分的对话存储在参与聊天的用户的 Exchange Online 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="418db-312">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the Exchange Online mailbox of the users who participate in the chat.</span></span> <span data-ttu-id="418db-313">以及用户在聊天对话中共享的文件存储在共享该文件的用户的 OneDrive for business 帐户中。</span><span class="sxs-lookup"><span data-stu-id="418db-313">And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file.</span></span> <span data-ttu-id="418db-314">因此, 您必须将单个用户邮箱和 OneDrive for business 帐户添加为在聊天列表中搜索对话和文件的内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-314">Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="418db-315">在 Exchange 混合部署中, 具有本地邮箱的用户可能会参与属于 Microsoft 团队中的聊天列表的对话。</span><span class="sxs-lookup"><span data-stu-id="418db-315">In an Exchange hybrid deployment, users with an on-premises mailbox might participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="418db-316">在这种情况下, 这些对话中的内容也是可搜索的, 因为它保存到基于云的存储区域 (称为*本地用户的基于云的邮箱*), 以供拥有本地邮箱的用户使用。</span><span class="sxs-lookup"><span data-stu-id="418db-316">In this case, content from these conversations is also searchable because it's saved to a cloud-based storage area (called a *cloud-based mailbox for on-premises users*) for users who have an on-premises mailbox.</span></span> <span data-ttu-id="418db-317">有关详细信息, 请参阅在[Office 365 中搜索本地用户的基于云的邮箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-317">For more information, see [Searching cloud-based mailboxes for on-premises users in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>
  
- <span data-ttu-id="418db-318">每个 Microsoft 团队或团队频道都包含用于笔记记录和协作的 Wiki。</span><span class="sxs-lookup"><span data-stu-id="418db-318">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration.</span></span> <span data-ttu-id="418db-319">Wiki 内容将自动保存到格式为 .mht 的文件中。</span><span class="sxs-lookup"><span data-stu-id="418db-319">The Wiki content is automatically saved to a file with a .mht format.</span></span> <span data-ttu-id="418db-320">此文件存储在团队的 SharePoint 网站上的 "团队 Wiki 数据" 文档库中。</span><span class="sxs-lookup"><span data-stu-id="418db-320">This file is stored in the Teams Wiki Data document library on the team's SharePoint site.</span></span> <span data-ttu-id="418db-321">您可以使用内容搜索工具来搜索 Wiki, 具体方法是将团队的 SharePoint 网站指定为要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="418db-321">You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="418db-322">在 Microsoft 团队或频道中搜索 Wiki 的功能 (在搜索团队的 SharePoint 网站时) 在2017年6月22日发布。</span><span class="sxs-lookup"><span data-stu-id="418db-322">The capability to search the Wiki for a Microsoft Team or Channel (when you search the team's SharePoint site) was released on June 22, 2017.</span></span> <span data-ttu-id="418db-323">在该日期或之后保存或更新的 Wiki 页面可供搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-323">Wiki pages that were saved or updated on that date or after are available to be searched.</span></span> <span data-ttu-id="418db-324">上次保存或更新的 Wiki 页面在该日期不可用于搜索之前。</span><span class="sxs-lookup"><span data-stu-id="418db-324">Wiki pages last saved or updated before that date aren't available for search.</span></span> 
 
- <span data-ttu-id="418db-325">Microsoft 团队频道中的会议和呼叫的摘要信息也存储在拨入会议或呼叫的用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="418db-325">Summary information for meetings and calls in a Microsoft Teams channel are also stored in the mailboxes of users who dialed into the meeting or call.</span></span> <span data-ttu-id="418db-326">这意味着您可以使用内容搜索来搜索这些摘要记录。</span><span class="sxs-lookup"><span data-stu-id="418db-326">This means you can use Content Search to search these summary records.</span></span> <span data-ttu-id="418db-327">摘要信息包括:</span><span class="sxs-lookup"><span data-stu-id="418db-327">Summary information includes:</span></span> 
  - <span data-ttu-id="418db-328">日期、开始时间、结束时间和会议或呼叫的持续时间</span><span class="sxs-lookup"><span data-stu-id="418db-328">Date, start time, end time, and duration of a meeting or call</span></span>

  - <span data-ttu-id="418db-329">每个参与者加入或离开会议或呼叫的日期和时间</span><span class="sxs-lookup"><span data-stu-id="418db-329">The date and time when each participant joined or left the meeting or call</span></span>

  - <span data-ttu-id="418db-330">发送给语音邮件的呼叫</span><span class="sxs-lookup"><span data-stu-id="418db-330">Calls sent to voice mail</span></span>

  - <span data-ttu-id="418db-331">未接或未应答的呼叫</span><span class="sxs-lookup"><span data-stu-id="418db-331">Missed or unanswered calls</span></span>

  - <span data-ttu-id="418db-332">呼叫转移, 表示为两个单独的呼叫</span><span class="sxs-lookup"><span data-stu-id="418db-332">Call transfers, which are represented as two separate calls</span></span>

  <span data-ttu-id="418db-333">请注意, 会议最长可能需要8个小时, 并且呼叫摘要记录可供搜索。</span><span class="sxs-lookup"><span data-stu-id="418db-333">Note that it can take up to 8 hours for meeting and call summary records to be available to be searched.</span></span>

  <span data-ttu-id="418db-334">在搜索结果中, 在 "**类型" 字段**中将会议摘要标识为 "**会议**";呼叫摘要标识为 "**呼叫**"。</span><span class="sxs-lookup"><span data-stu-id="418db-334">In the search results, meeting summaries are identified as **Meeting** in the **Type field**; call summaries are identified as **Call**.</span></span> <span data-ttu-id="418db-335">此外, 属于团队频道和1xN 聊天的对话在 "**类型**" 字段中被标识为**IM** 。</span><span class="sxs-lookup"><span data-stu-id="418db-335">Additionally, conversations that are part of a Teams channel and 1xN chats are identified as **IM** in the **Type** field.</span></span>
  
  ![团队会议、通话和1xN 聊天在 "类型" 字段中进行标识](media/O365-ContentSearch-Teams-MessageKind.png)

- <span data-ttu-id="418db-337">您可以使用**Kind**电子邮件属性或**邮件类型**搜索条件专门搜索 Microsoft 团队中的内容。</span><span class="sxs-lookup"><span data-stu-id="418db-337">You can use the **Kind** email property or the **Message kind** search condition to search specifically for content in Microsoft Teams.</span></span> 
  - <span data-ttu-id="418db-338">若要将**Kind**属性用作关键字搜索查询的一部分, 请在搜索查询的 "**关键字**" 框中键入`kind:microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="418db-338">To use the **Kind** property as part of the keyword search query, in the **Keywords** box of a search query, type `kind:microsoftteams`.</span></span>

    ![在 "关键字" 框中使用类型: microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - <span data-ttu-id="418db-340">若要使用搜索条件, 请添加**邮件类型**条件并使用值`microsoftteams`。</span><span class="sxs-lookup"><span data-stu-id="418db-340">To use a search condition, add the **Message kind** condition and use the value `microsoftteams`.</span></span> 

    ![将邮件类型条件与值 microsoftteams 一起使用。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

<span data-ttu-id="418db-342">请注意, **and**运算符将条件以逻辑方式连接到关键字查询。</span><span class="sxs-lookup"><span data-stu-id="418db-342">Note that conditions are logically connected to the keyword query by the **AND** operator.</span></span> <span data-ttu-id="418db-343">这意味着项目必须同时匹配关键字查询和搜索结果中要返回的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="418db-343">That means an item must match both the keyword query and the search condition to be returned in the search results.</span></span> <span data-ttu-id="418db-344">有关详细信息, 请参阅关键字查询和搜索条件中的 "使用条件指南" 部分的[内容搜索的关键字查询和搜索条件。](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span><span class="sxs-lookup"><span data-stu-id="418db-344">For more information, see the "Guidelines for using conditions" section in [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)</span></span>

  
### <a name="searching-inactive-mailboxes"></a><span data-ttu-id="418db-345">搜索非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="418db-345">Searching inactive mailboxes</span></span>

<span data-ttu-id="418db-346">可以在内容搜索中搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-346">You can search inactive mailboxes in a content search.</span></span> <span data-ttu-id="418db-347">若要获取组织中非活动邮箱的列表, 请在 Exchange Online `Get-Mailbox -InactiveMailboxOnly` PowerShell 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="418db-347">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell.</span></span> <span data-ttu-id="418db-348">或者, 您可以转到 Security & 合规性中心中的 "**数据管理** \> "**保留**, 然后单击 "**更多**![导航栏椭圆](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非活动邮箱**"。</span><span class="sxs-lookup"><span data-stu-id="418db-348">Alternatively, you can go to **Data governance** \> **Retention** in the Security & Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
  
<span data-ttu-id="418db-349">以下是在搜索非活动邮箱时要牢记的一些事项。</span><span class="sxs-lookup"><span data-stu-id="418db-349">Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="418db-350">如果内容搜索包括用户邮箱, 并且该邮箱随后变为非活动状态, 则当您在搜索变为非活动状态后重新运行该搜索时, 内容搜索将继续搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-350">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="418db-351">在某些情况下, 用户可能有一个活动邮箱和一个具有相同 SMTP 地址的非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-351">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address.</span></span> <span data-ttu-id="418db-352">在这种情况下, 将仅搜索您选择作为内容搜索的位置的特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-352">In this case, only the specific mailbox that you select as a location for a content search will be searched.</span></span> <span data-ttu-id="418db-353">换句话说, 如果将用户的邮箱添加到搜索, 则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-353">In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="418db-354">强烈建议您避免使用相同 SMTP 地址的活动邮箱和非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-354">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address.</span></span> <span data-ttu-id="418db-355">如果需要重用当前分配给非活动邮箱的 SMTP 地址, 我们建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱的存档) 中, 然后删除非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="418db-355">If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox.</span></span> <span data-ttu-id="418db-356">有关详细信息, 请参阅下列主题之一:</span><span class="sxs-lookup"><span data-stu-id="418db-356">For more information, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="418db-357">在 Office 365 中恢复非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="418db-357">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="418db-358">在 Office 365 中还原非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="418db-358">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="418db-359">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="418db-359">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a><span data-ttu-id="418db-360">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="418db-360">Previewing search results</span></span>

<span data-ttu-id="418db-361">您可以在预览窗格中预览受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="418db-361">You can preview supported file types in the preview pane.</span></span> <span data-ttu-id="418db-362">如果文件类型不受支持, 则必须将该文件的副本下载到本地计算机以进行查看。</span><span class="sxs-lookup"><span data-stu-id="418db-362">If a file type isn't supported, you'll have to download a copy of the file to your local computer to view it.</span></span> <span data-ttu-id="418db-363">支持以下文件类型, 并可在搜索结果窗格中进行预览。</span><span class="sxs-lookup"><span data-stu-id="418db-363">The following file types are supported and can be previewed in the search results pane.</span></span>
  
- <span data-ttu-id="418db-364">.txt、.html、mhtml</span><span class="sxs-lookup"><span data-stu-id="418db-364">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="418db-365">.eml</span><span class="sxs-lookup"><span data-stu-id="418db-365">.eml</span></span>
    
- <span data-ttu-id="418db-366">.doc、.docx、. .docm</span><span class="sxs-lookup"><span data-stu-id="418db-366">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="418db-367">. .pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="418db-367">.pptm, .pptx</span></span>
    
- <span data-ttu-id="418db-368">.pdf</span><span class="sxs-lookup"><span data-stu-id="418db-368">.pdf</span></span>
    
<span data-ttu-id="418db-369">此外, 还支持以下文件容器类型。</span><span class="sxs-lookup"><span data-stu-id="418db-369">Additionally, the following file container types are supported.</span></span> <span data-ttu-id="418db-370">您可以在预览窗格中查看容器中的文件列表。</span><span class="sxs-lookup"><span data-stu-id="418db-370">You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="418db-371">.zip</span><span class="sxs-lookup"><span data-stu-id="418db-371">.zip</span></span>
    
- <span data-ttu-id="418db-372">gzip</span><span class="sxs-lookup"><span data-stu-id="418db-372">.gzip</span></span>
    
### <a name="partially-indexed-items"></a><span data-ttu-id="418db-373">部分索引项目</span><span class="sxs-lookup"><span data-stu-id="418db-373">Partially indexed items</span></span>

- <span data-ttu-id="418db-374">如前所述, 邮箱中部分索引的项目包含在估计的搜索结果中;来自 SharePoint 和 OneDrive 的部分索引项目不包含在估计的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="418db-374">As previously explained, partially indexed items in mailboxes are included in the estimated search results; partially indexed items from SharePoint and OneDrive are not included in the estimated search results.</span></span> 
    
- <span data-ttu-id="418db-375">如果部分项目与搜索查询匹配 (因为其他邮件或文档属性满足搜索条件), 则不会将其包含在未编制索引项目的估计数量中。</span><span class="sxs-lookup"><span data-stu-id="418db-375">If a partially item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items.</span></span> <span data-ttu-id="418db-376">如果搜索条件排除了部分项目, 它也不会包含在部分索引项目的估计数量中。</span><span class="sxs-lookup"><span data-stu-id="418db-376">If an partially item is excluded by the search criteria, it also won't be included in the estimated number of partially indexed items.</span></span> <span data-ttu-id="418db-377">有关详细信息, 请参阅[Office 365 中的内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="418db-377">For more information, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a><span data-ttu-id="418db-378">从 MyAnalytics 和其他 Office 365 应用程序导出数据</span><span class="sxs-lookup"><span data-stu-id="418db-378">Exporting data from MyAnalytics and other Office 365 applications</span></span>

- <span data-ttu-id="418db-379">来自 MyAnalytics 的数据 (例如, 用户如何根据邮箱中的邮件和日历数据使用其时间的见解) 和来自其他 Office 365 应用程序的数据都保存在用户的基于云的邮箱的隐藏位置 (在非 IPM 子树中)。</span><span class="sxs-lookup"><span data-stu-id="418db-379">Data from MyAnalytics (such as insights on how users spend their time based on mail and calendar data in their mailbox) and data from other Office 365 applications is a saved to a hidden location (in a non-IPM subtree) in user's cloud-based mailbox.</span></span> <span data-ttu-id="418db-380">在运行内容搜索后, 这些数据不会包括在估计的搜索结果、查询统计信息中, 也不能用于预览。</span><span class="sxs-lookup"><span data-stu-id="418db-380">After you run a Content Search, this data isn't included in the estimated search results, the query statistics, and it isn't available for preview.</span></span> <span data-ttu-id="418db-381">但是, 当您导出搜索结果时, 将导出此数据。</span><span class="sxs-lookup"><span data-stu-id="418db-381">However this data will be exported when you export the results of a search.</span></span>
    
- <span data-ttu-id="418db-382">MyAnalytics 数据和其他 office 365 应用程序中的数据将被导出到名为 "其他 office 365 data" 的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="418db-382">The MyAnalytics data and the data from other Office 365 applications is exported to a folder named "Other Office 365 data".</span></span> <span data-ttu-id="418db-383">此文件夹包括每个用户的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="418db-383">This folder includes subfolders for each user.</span></span>
  
