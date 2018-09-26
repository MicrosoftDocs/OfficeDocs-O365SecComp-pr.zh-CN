---
title: 使用电子数据展示中心搜索所有邮箱和网站
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 56e2978f-71b6-4141-b769-ad856d31bbec
description: 在 Office 365 的电子数据展示中心，您可以搜索所有 Exchange Online 邮箱、 SharePoint Online 网站和 OneDrive 单个电子数据展示都搜索中的业务网站。若要搜索组织中的所有内容源，电子数据展示经理必须分配适当的电子数据展示权限的每个内容源。
ms.openlocfilehash: 5612faf6113ceef292f90b49ec70ad7b30905646
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038095"
---
# <a name="search-all-mailboxes-and-sites-using-the-ediscovery-center"></a><span data-ttu-id="17c92-104">使用电子数据展示中心搜索所有邮箱和网站</span><span class="sxs-lookup"><span data-stu-id="17c92-104">Search all mailboxes and sites using the eDiscovery Center</span></span>

<span data-ttu-id="17c92-p102">在 Office 365 的电子数据展示中心，您可以搜索所有 Exchange Online 邮箱、 SharePoint Online 网站和 OneDrive 单个电子数据展示都搜索中的业务网站。若要搜索组织中的所有内容源，电子数据展示经理必须分配适当的电子数据展示权限的每个内容源。</span><span class="sxs-lookup"><span data-stu-id="17c92-p102">In the eDiscovery Center in Office 365, you can search all Exchange Online mailboxes, SharePoint Online sites, and OneDrive for Business sites in a single eDiscovery search. To search all content sources in the organization, an eDiscovery manager must be assigned the appropriate eDiscovery permissions for each content source.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="17c92-107">开始之前</span><span class="sxs-lookup"><span data-stu-id="17c92-107">Before you begin</span></span>

- <span data-ttu-id="17c92-p103">必须为电子数据展示管理器分配搜索内容源的适当权限。有关分配访问邮箱和网站的电子数据展示权限的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="17c92-p103">An eDiscovery manager must be assigned the appropriate permissions to search a content source. For more information about assigning eDiscovery permissions to mailboxes and sites, see the following:</span></span> 
    
  - [<span data-ttu-id="17c92-110">在 Exchange 中分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="17c92-110">Assign eDiscovery permissions in Exchange</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526886)
    
  - [<span data-ttu-id="17c92-111">在 SharePoint Online 中分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="17c92-111">Assign eDiscovery permissions in SharePoint Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=526885)
    
  - [<span data-ttu-id="17c92-112">为 OneDrive for Business 站点分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="17c92-112">Assign eDiscovery permissions to OneDrive for Business sites</span></span>](assign-permissions-to-onedrive-for-business-sites.md)
    
- <span data-ttu-id="17c92-p104">单个电子数据展示搜索查询中，您可以搜索最多 10,000 个邮箱和数量不限的 SharePoint Online 和 OneDrive for Business 站点。但是，如果您指定要搜索的特定网站，限制为 100 个网站。</span><span class="sxs-lookup"><span data-stu-id="17c92-p104">You can search a maximum of 10,000 mailboxes and an unlimited number of SharePoint Online and OneDrive for Business sites in a single eDiscovery search query. However, if you specify the specific sites to search, the limit is 100 sites.</span></span>
    
- <span data-ttu-id="17c92-115">搜索所有邮箱和网站时查看结果时，请参阅有关限制的说明[详细信息](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo)部分。</span><span class="sxs-lookup"><span data-stu-id="17c92-115">See the [More information](search-all-mailboxes-and-sites-with-ediscovery.md#moreinfo) section for a description of the limits when viewing the results when searching all mailboxes and sites.</span></span> 
    
- <span data-ttu-id="17c92-116">有关在电子数据展示中心中创建搜索查询的详细信息，请参阅[创建和运行电子数据展示查询](https://go.microsoft.com/fwlink/p/?LinkID=404032)。</span><span class="sxs-lookup"><span data-stu-id="17c92-116">For more information about creating search queries in the eDiscovery Center, see [Create and run eDiscovery queries](https://go.microsoft.com/fwlink/p/?LinkID=404032).</span></span>
    
## <a name="search-all-locations"></a><span data-ttu-id="17c92-117">搜索所有位置</span><span class="sxs-lookup"><span data-stu-id="17c92-117">Search all locations</span></span>

1. <span data-ttu-id="17c92-118">在电子数据展示中心，打开您要对其运行搜索查询的那个电子数据展示案例。</span><span class="sxs-lookup"><span data-stu-id="17c92-118">In the eDiscovery Center, open the eDiscovery case that you want to run the search query for.</span></span>
    
2. <span data-ttu-id="17c92-119">在**搜索和导出**中，单击现有查询或单击要创建新的搜索查询的**新项**。</span><span class="sxs-lookup"><span data-stu-id="17c92-119">Under **Search and Export**, click an existing query or click **New item** to create a new search query.</span></span> 
    
3. <span data-ttu-id="17c92-120">在搜索查询页的**源**部分中，单击**修改查询范围**。</span><span class="sxs-lookup"><span data-stu-id="17c92-120">On the search query page, in the **Sources** section, click **Modify Query Scope**.</span></span>
    
4. <span data-ttu-id="17c92-121">在**修改查询范围**页中，单击**搜索所有内容**，并选择要搜索的内容位置。</span><span class="sxs-lookup"><span data-stu-id="17c92-121">On the **Modify Query Scope** page, click **Search everything**, and select the content locations to search.</span></span>
    
  - <span data-ttu-id="17c92-122">选择**Exchange**搜索所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="17c92-122">Select **Exchange** to search all mailboxes.</span></span> 
    
  - <span data-ttu-id="17c92-123">选择**SharePoint**搜索所有与 SharePoint Online 和 OneDrive 业务网站。</span><span class="sxs-lookup"><span data-stu-id="17c92-123">Select **SharePoint** to search all SharePoint Online and OneDrive for Business sites.</span></span> 
    
  - <span data-ttu-id="17c92-124">选择**Exchange**和**SharePoint**搜索您的组织中的所有内容位置。</span><span class="sxs-lookup"><span data-stu-id="17c92-124">Select both **Exchange** and **SharePoint** to search all content locations in your organization.</span></span> 
    
![搜索所有邮箱和站点](media/e1f919ab-5596-43bb-a3c9-626cd41067b3.gif)
  
5. <span data-ttu-id="17c92-126">单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="17c92-126">Click **OK** to save the changes.</span></span> 
    
6. <span data-ttu-id="17c92-p105">完成或修改搜索查询页上，如关键字查询、 日期范围，或收缩的特定类型的内容搜索的其他信息。准备好运行查询后，单击**搜索**。</span><span class="sxs-lookup"><span data-stu-id="17c92-p105">Complete or revise other information on the search query page, such as the keyword query, the date range, or narrowing the specific types of content to search for. When you're ready to run the query, click **Search**.</span></span> 
    
## <a name="more-information"></a><span data-ttu-id="17c92-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="17c92-129">More information</span></span>
<span data-ttu-id="17c92-130"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="17c92-130"></span></span>

- <span data-ttu-id="17c92-131">顶部 500 邮箱和大多数结果的顶部 500 网站在**查询**页上列出在**源**下。</span><span class="sxs-lookup"><span data-stu-id="17c92-131">The top 500 mailboxes and the top 500 sites with the most results are listed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="17c92-132">在所有内容源中找到的总项目数和其组合的总大小都显示在**源**下，在**查询**页上。</span><span class="sxs-lookup"><span data-stu-id="17c92-132">The total number of items found in all content sources and their combined total size are displayed under **Sources** on the **Query** page.</span></span> 
    
- <span data-ttu-id="17c92-133">您可以预览“查询”\*\*\*\* 页面上位于 Exchange 邮箱或 SharePoint 站点中的 200 个最新的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="17c92-133">You can preview the 200 most recent search results located in Exchange mailboxes or SharePoint sites on the **Query** page.</span></span> 
    
    <span data-ttu-id="17c92-134">下面的屏幕快照显示搜索所有邮箱和网站时，在**查询**页上显示都搜索结果的示例。</span><span class="sxs-lookup"><span data-stu-id="17c92-134">The following screenshot shows an example of the search results displayed on the **Query** page when you search all mailboxes and sites.</span></span> 
    
    ![所有位置的搜索结果的屏幕截图](media/4bf430f6-41ab-4bf6-afa9-33c3f6fd8b16.gif)
  

