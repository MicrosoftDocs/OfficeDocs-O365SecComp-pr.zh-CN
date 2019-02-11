---
title: 管理保留项中高级电子数据展示 （预览）
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
description: ''
ms.openlocfilehash: 476ea80e61b5354c53368613e29a79c55a50276f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695178"
---
# <a name="manage-holds-in-advanced-ediscovery-preview"></a><span data-ttu-id="195a9-102">管理保留项中高级电子数据展示 （预览）</span><span class="sxs-lookup"><span data-stu-id="195a9-102">Manage holds in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="195a9-p101">高级电子数据展示 （预览） 案例可用于创建保留项以保留可能与您的案例相关的内容。使用高级电子数据展示 （预览） 保留功能，就可以保留对管理员和它们的数据源。此外，您可以置于非监控保留邮箱和 OneDrive for Business 站点。您还可以进行保留组邮箱、 SharePoint 网站和 OneDrive for Business 站点 for Office 365 组。同样，您可以置于保留的邮箱和关联的 Microsoft 团队使用的网站。当您将内容位置置于保持状态时，内容将保存，直到释放 custodian、 删除一个特定的数据的位置，或完全删除保留策略。</span><span class="sxs-lookup"><span data-stu-id="195a9-p101">You can use an Advanced eDiscovery (Preview) case to create holds to preserve content that might be relevant to your case. Using the Advanced eDiscovery (Preview) hold capabilities, you can place holds on custodians and their data sources. Additionally, you can place a non-custodial hold on mailboxes and OneDrive for Business sites. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you release the custodian, remove a specific data location, or delete the hold policy entirely.</span></span>

## <a name="manage-custodian-based-holds"></a><span data-ttu-id="195a9-109">管理基于 custodian 保留项</span><span class="sxs-lookup"><span data-stu-id="195a9-109">Manage custodian-based holds</span></span>

<span data-ttu-id="195a9-p102">在某些情况下，您可能必须选择保留和一组数据管理员的标识。在高级电子数据展示 （预览），这些管理员置于保持状态时用户和其所选的数据源将自动添加到管理员保留策略。</span><span class="sxs-lookup"><span data-stu-id="195a9-p102">In some cases, you may have a set of data custodians that you have identified and choosen to preserve. In Advanced eDiscovery (Preview), when these custodians are placed on hold, the user and their selected data sources are automatically added to a custodian hold policy.</span></span> 

<span data-ttu-id="195a9-112">若要查看 custodian 保留策略：</span><span class="sxs-lookup"><span data-stu-id="195a9-112">To view the custodian hold policy:</span></span>

1. <span data-ttu-id="195a9-113">在**安全 & 合规性中心**中，单击**电子数据展示 > 高级电子数据展示 （预览）** 以显示组织中的情况下列表。</span><span class="sxs-lookup"><span data-stu-id="195a9-113">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
   
2. <span data-ttu-id="195a9-p103">转到**管理员**选项卡添加您的案例中的管理员。若要了解如何添加和置于高级电子数据展示 （预览） 案例中保持状态的管理员，请参阅[的高级电子数据展示 （预览） 添加管理员案例](add-custodians-to-case.md)。如果您已经添加管理员并置于保持状态，请转到步骤 3。</span><span class="sxs-lookup"><span data-stu-id="195a9-p103">Go to the **Custodians** tab to add custodians within your case. To learn how you can add and place custodians on hold within an Advanced eDiscovery (Preview) case, see [Add Custodians to an Advanced eDiscovery (Preview) Case](add-custodians-to-case.md). If you have already added custodians and placed them on hold, go to step 3.</span></span>
   
3. <span data-ttu-id="195a9-117">转到**保留**选项卡，并选择 Custodian 策略。</span><span class="sxs-lookup"><span data-stu-id="195a9-117">Go to the **Holds** tab and select the 'Custodian Policy'.</span></span>
   
4. <span data-ttu-id="195a9-p104">在弹出页上，您可以看到保留策略的统计信息。您还可以执行操作类似于您基于 custodian 保留查询。有关创建保留查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](../keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="195a9-p104">In the flyout page, you can see hold statistics for the policy. You can also perform actions like apply a query to your custodian-based hold. For more information about creating a hold query and using conditions, see [Keyword queries and search conditions for Content Search](../keyword-queries-and-search-conditions.md).</span></span>
 
## <a name="manage-non-custodial-holds"></a><span data-ttu-id="195a9-121">管理非监控保留项</span><span class="sxs-lookup"><span data-stu-id="195a9-121">Manage non-custodial holds</span></span>

<span data-ttu-id="195a9-122">创建保留项时，您具有以下选项范围保留在指定的内容位置的内容：</span><span class="sxs-lookup"><span data-stu-id="195a9-122">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>

  - <span data-ttu-id="195a9-p105">创建所有内容将都置于保持状态无限期保留。或者，您可以创建基于查询的保留匹配一个搜索查询的唯一内容置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="195a9-p105">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
  - <span data-ttu-id="195a9-p106">您可以指定日期范围以保留内容发送、 接收，或创建的日期范围内。此外，您可以保留无论时发送、 接收，或创建的所有内容。</span><span class="sxs-lookup"><span data-stu-id="195a9-p106">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>

<span data-ttu-id="195a9-127">创建高级电子数据展示 （预览） 用例保留：</span><span class="sxs-lookup"><span data-stu-id="195a9-127">To create a hold for an Advanced eDiscovery (Preview) case:</span></span>

1. <span data-ttu-id="195a9-128">在**安全 & 合规性中心**中，单击**电子数据展示 > 高级电子数据展示 （预览）** 以显示组织中的情况下列表。</span><span class="sxs-lookup"><span data-stu-id="195a9-128">In the **Security & Compliance Center**, click **eDiscovery > Advanced eDiscovery (Preview)** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="195a9-129">单击旁边的情况下，您想要创建保留项中的**打开**。</span><span class="sxs-lookup"><span data-stu-id="195a9-129">Click **Open** next to the case that you want to create the holds in.</span></span>
  
3. <span data-ttu-id="195a9-130">从用例主页页中，单击**保存**选项卡。</span><span class="sxs-lookup"><span data-stu-id="195a9-130">From the home page for the case, click the **Holds** tab.</span></span>
  
4. <span data-ttu-id="195a9-131">在**保存**选项卡中，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="195a9-131">On the **Holds** tab, click **Create**.</span></span>
  
5. <span data-ttu-id="195a9-p107">在**名称您保留**页中，赋予保留项的名称。保留项的名称必须是您的组织中唯一的。</span><span class="sxs-lookup"><span data-stu-id="195a9-p107">On the **Name your hold** page, give the hold a name. The name of the hold must be unique in your organization.</span></span>
 
6. <span data-ttu-id="195a9-134">（可选）在**说明**框中，添加的保留项的说明。</span><span class="sxs-lookup"><span data-stu-id="195a9-134">(Optional) In the **Description** box, add a description of the hold.</span></span>
  
7. <span data-ttu-id="195a9-135">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="195a9-135">Click **Next**.</span></span>
  
8. <span data-ttu-id="195a9-p108">选择您想要置于内容位置保留。您可以将置于保持状态的邮箱、 网站和公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="195a9-p108">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.</span></span>

   <span data-ttu-id="195a9-p109">答： **Exchange 电子邮件**-单击**选择用户、 组或团队**，，然后单击**选择用户、 组或团队**再次指定邮箱置于保留。使用搜索框查找用户邮箱和通讯组 （用于组成员的邮箱置于保留） 以将置于保持状态。此外可以为 Office 365 组或 Microsoft 团队对关联的邮箱进行保留。选择用户、 组和团队复选框，单击**选择**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="195a9-p109">a. **Exchange email** - Click **Choose users, groups, or teams** and then click **Choose users, groups, or teams** again to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="195a9-p110">当您单击**选择用户、 组或团队**以指定要将置于保持状态的邮箱，显示邮箱选取器为空。这是设计以提高性能。要将联系人添加到此列表中，请在搜索框中键入名称 （最少的 3 个字符）。</span><span class="sxs-lookup"><span data-stu-id="195a9-p110">When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span>

    <span data-ttu-id="195a9-p111">b. **SharePoint 网站**-单击**选择站点**，然后单击再次要指定 SharePoint 和 OneDrive for Business 站点置于保留的**选择网站**。键入您想要将置于保持状态的每个网站的 URL。您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。单击**选择**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="195a9-p111">b. **SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
    
     <span data-ttu-id="195a9-151">请参阅上放置置于保持状态的 Office 365 组和 Microsoft 团队的提示和技巧**常见问题**一节。</span><span class="sxs-lookup"><span data-stu-id="195a9-151">See the **FAQ** section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span>

    > [!NOTE]
    > <span data-ttu-id="195a9-p112">在已更改的人员的用户主体名称 (UPN) 极少数情况下，其 OneDrive 帐户的 URL 也将更改为合并新的 UPN。如果发生这种情况，您将需要通过添加用户的新 OneDrive URL 和删除旧修改保留项。</span><span class="sxs-lookup"><span data-stu-id="195a9-p112">In the rare case that a person's user principal name (UPN) has changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one.</span></span>

     <span data-ttu-id="195a9-p113">c. **Exchange 公用文件夹**-在将移动到的所有位置将所有公用文件夹放入在 Exchange Online 组织上的保留的切换开关。请注意，不能选择特定的公用文件夹，以将置于保持状态。保留设置为**None** ，如果您不想要保留置于公用文件夹切换开关。</span><span class="sxs-lookup"><span data-stu-id="195a9-p113">c. **Exchange public folders** - Move the toggle switch to the All position to put all public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the toggle switch set to **None** if you don't want to put a hold on public folders.</span></span>

9. <span data-ttu-id="195a9-158">完成添加到保留项的内容位置后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="195a9-158">When you're done adding content locations to the hold, click **Next**.</span></span>
  
10. <span data-ttu-id="195a9-p114">若要创建基于查询的保留与条件，完成以下。否则，只需单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="195a9-p114">To create a query-based hold with conditions, complete the following. Otherwise, just click **Next**.</span></span>
    
    - <span data-ttu-id="195a9-p115">在在**关键字**下框中，键入搜索查询的框中，以便仅符合搜索条件的内容置于保留。您可以指定关键字、 消息属性或文档属性，如文件名。您还可以使用或不使用布尔运算符，例如 AND、 OR 的更复杂的查询。如果您保留关键字框为空，则位于指定的内容位置的所有内容将都置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="195a9-p115">In the box under **Keywords**, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as AND, OR, or NOT. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span>

    - <span data-ttu-id="195a9-p116">单击**添加**条件以添加一个或多个条件以缩小范围的搜索查询的保留项。每个条件将子句添加到 KQL 搜索查询创建和运行时创建保留项。例如可以指定日期范围，以便电子邮件或网站的日期范围内创建的文档置于保持状态。条件逻辑 AND 运算符通过连接到 （在关键字框中指定） 的关键字查询。意味着项目需要满足关键字查询和条件的置于保持状态。</span><span class="sxs-lookup"><span data-stu-id="195a9-p116">Click  **Add** conditions to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the AND operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span>

     <span data-ttu-id="195a9-170">有关创建搜索查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)。</span><span class="sxs-lookup"><span data-stu-id="195a9-170">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions).</span></span>

12. <span data-ttu-id="195a9-171">后配置基于查询的保留，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="195a9-171">After configuring a query-based hold, click **Next**.</span></span>
 
13. <span data-ttu-id="195a9-172">检查您的设置，然后单击**创建此保留**。</span><span class="sxs-lookup"><span data-stu-id="195a9-172">Review your settings, and then click **Create this hold**.</span></span>


## <a name="view-hold-statistics"></a><span data-ttu-id="195a9-173">查看保留统计信息</span><span class="sxs-lookup"><span data-stu-id="195a9-173">View hold statistics</span></span>

<span data-ttu-id="195a9-p117">段时间后的所选保留**保留**选项卡上详细信息窗格中显示有关新保留的信息。此信息包括的邮箱数和上的网站保留统计信息的内容的已置于保留，如置于保持状态的总数量和大小的项目和上一次的保留计算的统计信息。这些保留统计信息帮助您确定要保留与电子数据展示案例相关的内容量。</span><span class="sxs-lookup"><span data-stu-id="195a9-p117">After some time, information about the new hold is displayed in the details pane on the **Holds** tab for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span>

<span data-ttu-id="195a9-177">注意有关保留统计信息并按以下几点：</span><span class="sxs-lookup"><span data-stu-id="195a9-177">Keep the following things in mind about hold statistics:</span></span>

- <span data-ttu-id="195a9-p118">置于保留状态的项目总数指示置于保持状态的所有内容源中的项目数。如果您已创建基于查询的保留，此统计信息指示与查询匹配的项目数。</span><span class="sxs-lookup"><span data-stu-id="195a9-p118">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
  
- <span data-ttu-id="195a9-p119">置于保留状态的项目数还包括内容的位置中找到的未编制索引的项。请注意，是否创建基于查询的保留，但内容的位置中的所有未编制索引的项目置于保持状态。这包括与搜索条件的基于查询的保留不匹配的未编制索引的项和可能属于外部日期范围条件的未编制索引的项。这是不同于运行内容的搜索，在其中未编制索引的项不匹配的搜索查询或排除的日期范围条件不包括在搜索结果时，会发生什么情况。有关未编制索引的项目的详细信息，请参阅[部分，索引项目在 Office 365 中的内容搜索](../partially-indexed-items-in-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="195a9-p119">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365](../partially-indexed-items-in-content-search.md).</span></span> 

- <span data-ttu-id="195a9-185">您可以通过单击更新统计信息以重新运行计算当前置于保持状态的项目数的搜索估计获取的最新的保留统计信息。</span><span class="sxs-lookup"><span data-stu-id="195a9-185">You can get the latest hold statistics by clicking Update statistics to re-run a search estimate that calculates the current number of items on hold.</span></span>

- <span data-ttu-id="195a9-186">如有必要，单击在工具栏中更新的详细信息窗格中的保留统计信息的刷新。</span><span class="sxs-lookup"><span data-stu-id="195a9-186">If necessary, click Refresh in the toolbar to update the hold statistics in the details pane.</span></span>

- <span data-ttu-id="195a9-187">它的普通上的项目数保留来提高随着时间的推移，因为其邮箱或网站处于保留状态的用户通常发送或接收新电子邮件并创建新的 SharePoint 和 OneDrive 的业务文档。</span><span class="sxs-lookup"><span data-stu-id="195a9-187">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>

- <span data-ttu-id="195a9-p120">如果将 SharePoint 网站或 OneDrive 帐户移动到多地理环境中的不同区域，该网站的统计信息不会包含在保留统计信息。但是，网站中的内容仍将置于保持状态。此外，如果网站移至不同的区域将不会更新保留项中显示的 URL。您将需要编辑保留和更新 URL。</span><span class="sxs-lookup"><span data-stu-id="195a9-p120">If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="195a9-192">常见问题</span><span class="sxs-lookup"><span data-stu-id="195a9-192">Frequently asked questions</span></span>

- <span data-ttu-id="195a9-p121">如何将其他的 Office 365 组或 Microsoft 团队网站映射到 custodian **？和什么样的培训发出非监控保留对 Office 365 组和 Microsoft 团队？** 在 Office 365 组上构建的 Microsoft 团队。因此，将它们放在保留中电子数据展示事例是非常类似。将 Office 365 组和上的 Microsoft 团队保留时保留记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="195a9-p121">**How do I map an additional Office 365 Groups or Microsoft Teams site to a custodian? And what about placing a non-Custodial hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span>
  - <span data-ttu-id="195a9-197">若要放置内容位于 Office 365 组和 Microsoft 团队置于保持状态，您必须指定邮箱和 SharePoint 网站的组或团队相关联。</span><span class="sxs-lookup"><span data-stu-id="195a9-197">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
  
  - <span data-ttu-id="195a9-p122">Exchange Online 的 Office 365 组或 Microsoft 团队查看属性中运行**Get UnifiedGroup** cmdlet。这是一个好方法获取与 Office 365 组或 Microsoft 团队相关联的网站的 URL。例如，下面的命令的一个名为高级领导团队的 Office 365 组显示所选的属性：</span><span class="sxs-lookup"><span data-stu-id="195a9-p122">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span>


    ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > <span data-ttu-id="195a9-201">若要运行 Get UnifiedGroup cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。</span><span class="sxs-lookup"><span data-stu-id="195a9-201">To run the Get-UnifiedGroup cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

 - <span data-ttu-id="195a9-p123">用户的邮箱搜索，搜索时不会搜索任何 Office 365 组或 Microsoft 团队的成员的用户。同样，将 Office 365 组或 Microsoft 团队保持状态并置于组邮箱和组网站时保留;除非您明确将它们作为管理员添加或将其数据源保留，邮箱和 OneDrive for Business 网站组成员的不被置于保持状态。因此，如果您需要将 Office 365 组或 Microsoft 团队置于保留为特定的管理员，请考虑映射到 custodian （请参阅管理管理员高级电子数据展示 (Preview) 中） 的组网站和组邮箱。如果不属于单个管理员的 Office 365 组或 Microsoft 团队，请考虑添加到非监控源保留。</span><span class="sxs-lookup"><span data-stu-id="195a9-p123">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them as custodians or place their data sources hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a specific custodian, consider mapping the group site and group mailbox to the custodian (See Managing Custodians in Advanced eDiscovery (Preview)). If the Office 365 Group or Microsoft Team is not attributable to a single custodian, consider adding the source to a non-custodial hold.</span></span> 
 
 - <span data-ttu-id="195a9-p124">若要获取 Office 365 组或 Microsoft 团队的成员的列表，您可以在 Office 365 管理中心主页 > 组页上查看属性。此外，还可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="195a9-p124">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the Home > Groups page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span>

   ``` 
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > <span data-ttu-id="195a9-208">若要运行**Get UnifiedGroupLinks** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。</span><span class="sxs-lookup"><span data-stu-id="195a9-208">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span>

- <span data-ttu-id="195a9-p125">与团队具有关联的邮箱中存储的一部分的 Microsoft 团队通道通道对话。同样，在频道的工作组成员共享的文件存储团队的 SharePoint 网站上。因此，您必须放置的 Microsoft 团队邮箱和 SharePoint 网站上的保留保留对话和通道中的文件。</span><span class="sxs-lookup"><span data-stu-id="195a9-p125">Channel conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
  
- <span data-ttu-id="195a9-p126">此外，对话中的 Microsoft 团队的聊天列表的一部分存储在用户的邮箱的用户参与聊天。 用户共享聊天对话中的文件存储在 OneDrive for Business 站点的用户的共享文件。因此，您必须将单个用户邮箱和 OneDrive for Business 站点上保留保留对话和聊天列表中的文件。</span><span class="sxs-lookup"><span data-stu-id="195a9-p126">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat.  Files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list.</span></span> 
  
- <span data-ttu-id="195a9-p127">每个通道，Microsoft 团队或团队包含 Wiki 笔记记录和协作。Wiki 内容将自动保存到.mht 格式的文件时。此文件存储在团队的 SharePoint 网站上的团队 Wiki 数据文档库。通过将置于保持状态的团队的 SharePoint 网站，可以保持在 Wiki 中放置内容。</span><span class="sxs-lookup"><span data-stu-id="195a9-p127">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>

  > [!NOTE]
  > <span data-ttu-id="195a9-p128">2017 年 6 月 22，发布功能时要保留的 Microsoft 团队或团队通道 Wiki 内容 （团队的 SharePoint 网站将置于保持状态时）。如果工作组网站上保留的 Wiki 将保留内容，在该日期开始。但是，如果工作组网站处于保留状态，Wiki 内容已被删除之前 2017 年 6 月 22，已将不会为保留 Wiki 内容。</span><span class="sxs-lookup"><span data-stu-id="195a9-p128">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span>
