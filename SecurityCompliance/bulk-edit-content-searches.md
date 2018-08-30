---
title: 批量编辑 Office 365 安全性内容搜索&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: 在 Office 365 安全性使用批量搜索编辑器&amp;合规性中心，可以快速更改了一个或多个内容搜索的查询和内容的位置。
ms.openlocfilehash: 45c9a3fc4bcc5e5d8ce9945d3094bfb4a39d6dcf
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525289"
---
# <a name="bulk-edit-content-searches-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="f28cd-103">批量编辑 Office 365 安全性内容搜索&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="f28cd-103">Bulk edit Content Searches in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="f28cd-p101">您可以使用批量搜索编辑器中 Office 365 安全性&amp;合规性中心以同时编辑多个内容搜索。使用此工具，可以快速更改了一个或多个搜索的查询和内容的位置。然后您可以重新运行搜索和修订后的搜索获取新的估计的搜索结果。在编辑器还可以复制和粘贴查询和从 Microsoft Excel 文件或文本文件的内容位置。这意味着您可以使用搜索统计信息工具以查看一个或多个搜索的统计信息、 导出到 CSV 文件可以编辑的查询和 Excel 中的内容位置的统计信息。然后您可以使用批量搜索编辑器将修订后的查询和内容位置添加到搜索。已修订了一个或多个搜索后，您可以重新启动它们并获取新的估计的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p101">You can use the Bulk Search Editor in the Office 365 Security &amp; Compliance Center to edit multiple Content Searches at the same time. Using this tool lets you quickly change the query and content locations for one or more searches. Then you can re-run the searches and get new estimated search results for the revised searches. The editor also lets you copy and paste queries and content locations from a Microsoft Excel file or text file. This means you can use the Search Statistics tool to view the statistics of one or more searches, export the statistics to a CSV file where you can edit the queries and content locations in Excel. Then you use the Bulk Search Editor to add the revised queries and content locations to the searches. After you've revised one or more searches, you can re-start them and get new estimated search results.</span></span>
  
<span data-ttu-id="f28cd-111">有关使用搜索统计信息工具的详细信息，请参阅[视图的内容的搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="f28cd-111">For more information about using the Search Statistics tool, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a><span data-ttu-id="f28cd-112">使用批量搜索编辑器来更改查询</span><span class="sxs-lookup"><span data-stu-id="f28cd-112">Use the Bulk Search Editor to change queries</span></span>

1. <span data-ttu-id="f28cd-113">安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **内容搜索**。</span><span class="sxs-lookup"><span data-stu-id="f28cd-113">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**.</span></span>
    
2. <span data-ttu-id="f28cd-114">在搜索的列表中，选择一个或多个搜索，然后单击**批量搜索编辑器**![批量搜索编辑器按钮](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png)。</span><span class="sxs-lookup"><span data-stu-id="f28cd-114">In the list of searches, select one or more searches, and then click **Bulk Search Editor** ![Bulk Search Editor button](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png).</span></span>
    
    ![选择一个或多个搜索，然后单击批量搜索编辑器](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    <span data-ttu-id="f28cd-116">批量搜索编辑器的**查询**页面上将显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="f28cd-116">The following information is displayed on the **Queries** page of the Bulk Search Editor.</span></span> 
    
    ![批量搜索编辑器页上显示所选的搜索查询](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    <span data-ttu-id="f28cd-p102">答：**搜索**列显示的内容的搜索的名称。如前面所述，您可以编辑多个搜索查询。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p102">a. The **Search** column displays the name of the Content Search. As previously stated, you can edit the query for multiple searches.</span></span> 
    
    <span data-ttu-id="f28cd-p103">b.**查询**列显示在**搜索**列中列出的内容搜索查询。如果已创建的查询使用关键字列表功能，将关键字分隔文本 * * `(c:s)` **。这指示关键字进行连接的**OR**运算符。此外，如果查询包括条件，关键字和条件使用分隔文本 * * `(c:c)` **。这指示的关键字 （或关键字阶段） 进行连接的情况的**AND**运算符。例如，在以前的屏幕截图搜索 ContosoSearch1，将以 KQL 查询的等效于`customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)`采用`(customer OR pricing) AND (date=2002-01-01..2016-09-30)`。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p103">b. The **Query** column displays the query for the Content Search listed in the **Search** column. If the query was created using the keyword list feature, the keywords are separated by the text ** `(c:s)`**. This indicates that the keywords are connected by the **OR** operator. Additionally, if the query includes conditions, the keywords and the conditions are separated by the text ** `(c:c)`**. This indicates that the keywords (or keyword phases) are connected to the conditions by the **AND** operator. For example, in the previous screenshot the for search ContosoSearch1, the KQL query that is equivalent to  `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` would be  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.</span></span>
    
3. <span data-ttu-id="f28cd-p104">要编辑的查询，单击要更改，并执行以下操作之一，该查询的单元格中。请注意，单元格界定由蓝框中，单击它时。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p104">To edit a query, click in the cell of the query that you want to change and doing one of the following things. Note that the cell is bordered by a blue box when you click it.</span></span>
    
   - <span data-ttu-id="f28cd-p105">在单元格中键入新查询。请注意，不能编辑的查询部分。您必须键入整个查询。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p105">Type the new query in the cell. Note that you can't edit a portion of the query. You have to type the entire query.</span></span>
    
      <span data-ttu-id="f28cd-131">或</span><span class="sxs-lookup"><span data-stu-id="f28cd-131">Or</span></span>
    
    - <span data-ttu-id="f28cd-p106">将一个新的查询粘贴的单元格中。本示例假定您已从一个文件，如文本文件或 Excel 文件复制的查询文本。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p106">Paste a new query in the cell. This assumes that you've copied the query text from a file, such as a text file or an Excel file.</span></span>
    
4. <span data-ttu-id="f28cd-134">已编辑的**查询**页面上的一个或多个查询后，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f28cd-134">After you've edited one or more queries on the **Queries** page, click **Save**.</span></span>
    
    <span data-ttu-id="f28cd-135">所选搜索的**查询**列中显示修订后的查询。</span><span class="sxs-lookup"><span data-stu-id="f28cd-135">The revised query is displayed in the **Query** column for the selected search.</span></span> 
    
5. <span data-ttu-id="f28cd-136">单击**关闭**以关闭批量搜索编辑器。</span><span class="sxs-lookup"><span data-stu-id="f28cd-136">Click **Close** to close the Bulk Search Editor.</span></span> 
    
6. <span data-ttu-id="f28cd-137">在**内容搜索**页上，选择编辑，搜索，然后单击**开始**搜索以重新启动搜索使用修改后的查询。</span><span class="sxs-lookup"><span data-stu-id="f28cd-137">On the **Content search** page, select the search that you edited, and click **Start** search to restart the search using the revised query.</span></span> 
    
<span data-ttu-id="f28cd-138">以下是一些用于编辑使用批量搜索编辑器查询：</span><span class="sxs-lookup"><span data-stu-id="f28cd-138">Here are some tips for editing queries using the Bulk Search Editor:</span></span>
  
- <span data-ttu-id="f28cd-p107">将现有查询 （通过使用**Ctrl C** ） 复制到文本文件。在文本文件中，编辑查询然后复制修订后的查询并粘贴 （使用**Ctrl V** ） 返回到**查询**页面上的单元格。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p107">Copy the existing query (by using **Ctrl C** ) to a text file. Edit the query in the text file, and then copy the revised query and paste it (using **Ctrl V** ) back into the cell on the **Queries** page.</span></span> 
    
- <span data-ttu-id="f28cd-p108">您还可以从其他应用程序 （如 Microsoft Word 或 Microsoft Excel） 复制查询。但请注意可能无意中将不支持的字符添加到使用批量搜索编辑器的查询。防止不受支持的字符的最佳方式是，只需键入中**查询**页面上的单元格的查询。此外，您可以从 Word 或 Excel 复制查询，然后将其文件 Microsoft 记事本之类的纯文本编辑器中粘贴。然后将该文本文件保存，并选择**编码**下拉列表中的**ANSI** 。这将删除任何格式和不受支持的字符。然后您可以复制并粘贴到**查询**页上的查询的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p108">You can also copy queries from other applications (such as Microsoft Word or Microsoft Excel). However, be aware that you might inadvertently add unsupported characters to a query using the Bulk Search Editor. The best way to prevent unsupported characters is to just type the query in a cell on the **Queries** page. Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad. Then save the text file and select **ANSI** in the **Encoding** drop-down list. This will remove any formatting and unsupported characters. Then you can copy and paste the query from the text file to the **Queries** page.</span></span> 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a><span data-ttu-id="f28cd-148">使用批量搜索编辑器来更改内容的位置</span><span class="sxs-lookup"><span data-stu-id="f28cd-148">Use the Bulk Search Editor to change content locations</span></span>

1. <span data-ttu-id="f28cd-149">在批量搜索编辑器中的一个或多个选定搜索，单击**启用批量位置编辑器**，然后单击页面显示的**位置**链接。</span><span class="sxs-lookup"><span data-stu-id="f28cd-149">In the Bulk Search Editor for one or more selected searches, click **Enable bulk location editor**, and then click the **Locations** link that is displayed on the page.</span></span> 
    
    <span data-ttu-id="f28cd-150">批量搜索编辑器的**位置**页上将显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="f28cd-150">The following information is displayed on the **Locations** page of the Bulk Search Editor.</span></span> 
    
    ![单击启用批量位置编辑器，然后单击添加或删除内容位置的位置](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    <span data-ttu-id="f28cd-p109">a.**邮箱搜索**此部分显示列的每个选定的内容搜索和搜索中包括每个邮箱的行。复选标记指示邮箱包括在搜索。在空行中键入邮箱的电子邮件地址，然后单击内容搜索您要将其添加到的复选框，可以向搜索中添加其他邮箱。您可以从或删除邮箱搜索通过清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p109">a. **Mailboxes to search**This section displays a column for each selected Content Search, and row for each mailbox that's included in the search. A checkmark indicates that the mailbox is included in the search. You can add additional mailboxes to a search by typing the email address of the mailbox in a blank row and then clicking the checkbox for the Content Search that you want to add it to. Or you can remove a mailbox from a search by clearing the checkbox.</span></span>
    
    <span data-ttu-id="f28cd-p110">b. **SharePoint 网站能够搜索**此部分显示为包含在每个每个 SharePoint 和 OneDrive 站点的行所选内容的搜索。复选标记指示网站包括在搜索。您可以通过在空行中键入网站的 URL 添加到搜索其他网站，并单击要为内容搜索的复选框将其添加到。您可以从或删除网站搜索通过清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p110">b. **SharePoint sites to search**This section displays a row for each SharePoint and OneDrive site that included in each selected Content Search. A checkmark indicates that the site is included in the search. You can add additional sites to a search by typing the URL for the site in a blank row and then and clicking the checkbox for the Content Search that you want to add it to. Or you can remove a site from a search by clearing the checkbox.</span></span>
    
    <span data-ttu-id="f28cd-p111">c.**其他搜索选项**本节指示是否在搜索中包含未编制索引的项目和公用文件夹。若要包含这些，确保选中此复选框。要删除其，请清除该复选框。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p111">c. **Other search options**This section indicates whether unindexed items and public folders are included in the search. To include these, make sure the checkbox is selected. To remove them, clear the checkbox.</span></span>
    
2. <span data-ttu-id="f28cd-166">已编辑的一个或多个**位置**页上的部分后，单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f28cd-166">After you've edited one or more of the sections on the **Locations** page, click **Save**.</span></span>
    
    <span data-ttu-id="f28cd-167">所选的搜索相应部分中显示修订后的内容位置。</span><span class="sxs-lookup"><span data-stu-id="f28cd-167">The revised content locations are displayed in the appropriate section for the selected searches.</span></span>
    
3. <span data-ttu-id="f28cd-168">单击**关闭**以关闭批量搜索编辑器。</span><span class="sxs-lookup"><span data-stu-id="f28cd-168">Click **Close** to close the Bulk Search Editor.</span></span> 
    
4. <span data-ttu-id="f28cd-169">在**内容搜索**页上，选择编辑，搜索，然后单击**开始**搜索以重新启动搜索使用的修订后的内容位置。</span><span class="sxs-lookup"><span data-stu-id="f28cd-169">On the **Content search** page, select the search that you edited, and click **Start** search to restart the search using the revised content locations.</span></span> 
    
<span data-ttu-id="f28cd-170">以下是一些用于编辑使用批量搜索编辑器的内容位置：</span><span class="sxs-lookup"><span data-stu-id="f28cd-170">Here are some tips for editing content locations using the Bulk Search Editor:</span></span>
  
- <span data-ttu-id="f28cd-171">您可以编辑内容搜索来搜索所有邮箱或网站组织中的**邮箱搜索**或**SharePoint 网站能够都搜索**部分的空行中输入**所有**，然后单击复选框。</span><span class="sxs-lookup"><span data-stu-id="f28cd-171">You can edit Content Searches to search all mailboxes or sites in the organization by typing **All** in a blank row in the **Mailboxes to search** or **SharePoint sites to search** section and then clicking the checkbox.</span></span> 
    
- <span data-ttu-id="f28cd-p112">通过从文本文件或 Excel 文件复制多个行，然后将其粘贴到**位置**页上的部分，可以向一个或多个搜索中添加多个内容位置。添加新位置后，请务必选中为每个搜索要添加到的位置复选框。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p112">You can add multiple content locations to one or more searches by copying multiple rows from a text file or an Excel file and then pasting them to a section on the **Locations** page. After you add new locations, be sure to select the checkbox for each search that you want add the location to.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="f28cd-p113">若要生成您的组织中的所有用户的电子邮件地址列表，请运行在步骤 2 中[使用内容搜索的邮箱和 OneDrive for Business 站点的用户列表](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2)中的 PowerShell 命令。或[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)中使用脚本生成您的组织中的所有 OneDrive for Business 站点的列表。请注意，您必须追加的 URL 您的组织的 MySite 域 (例如，https://contoso-my.sharepoint.com)到 OneDrive for Business 站点创建脚本。列表的电子邮件地址或 OneDrive 业务网站后，您可以复制，并将它们粘贴到**位置**页中批量搜索编辑器。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p113">To generate a list of email addresses for all the users in your organization, run the PowerShell command in Step 2 in [Use Content Search to search the mailbox and OneDrive for Business site for a list of users](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step2). Or use the script in [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a) to generate a list of all OneDrive for Business sites in your organization. Note that you'll have to append the URL for your's organization's MySite domain (for example, https://contoso-my.sharepoint.com) to the OneDrive for Business sites that's created by the script. After you have list of email addresses or OneDrive for Business sites, you can copy and paste them to the **Locations** page in the Bulk Search Editor.</span></span> 
  
- <span data-ttu-id="f28cd-p114">您单击**保存**以保存在批量搜索编辑器中的更改后，将验证添加到搜索的邮箱的电子邮件地址。如果不存在的电子邮件地址，反映该邮箱找不到显示一条错误消息。请注意未验证的网站的 Url。</span><span class="sxs-lookup"><span data-stu-id="f28cd-p114">After you click **Save** to save changes in Bulk Search Editor, the email address for mailboxes that you added to a search will be validated. If the email address doesn't exist, an error message is displayed saying the mailbox can't be located. Note that URLs for sites aren't validated.</span></span> 
  

