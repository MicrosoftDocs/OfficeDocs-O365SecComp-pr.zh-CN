---
title: 运行 Office 365 安全性内容的搜索&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '在 Office 365 安全性中使用内容搜索&amp;合规性中心以搜索邮箱、 SharePoint Online 网站和 OneDrive for Business 位置。 '
ms.openlocfilehash: 61c6c3933a75567acb04f793cb6815322fb3fada
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525247"
---
# <a name="run-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="83196-103">运行 Office 365 安全性内容的搜索&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="83196-103">Run a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="83196-p101">您可以在 Office 365 安全性使用内容搜索电子数据展示工具&amp;合规性中心搜索如电子邮件、 文档和即时消息对话 Office 365 组织中的项目。使用此工具来搜索这些 Office 365 服务中的项：</span><span class="sxs-lookup"><span data-stu-id="83196-p101">You can use the Content Search eDiscovery tool in the Office 365 Security &amp; Compliance Center to search for items such as email, documents, and instant messaging conversations in your Office 365 organization. Use this tool to search for items in these Office 365 services:</span></span>
  
- <span data-ttu-id="83196-106">Exchange Online 邮箱和公用文件夹</span><span class="sxs-lookup"><span data-stu-id="83196-106">Exchange Online mailboxes and public folders</span></span>
    
- <span data-ttu-id="83196-107">SharePoint Online 和 OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="83196-107">SharePoint Online and OneDrive for Business sites</span></span>
    
- <span data-ttu-id="83196-108">业务对话的的 Skype</span><span class="sxs-lookup"><span data-stu-id="83196-108">Skype for Business conversations</span></span>
    
- <span data-ttu-id="83196-109">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83196-109">Microsoft Teams</span></span> 
    
- <span data-ttu-id="83196-110">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="83196-110">Office 365 Groups</span></span>
    
<span data-ttu-id="83196-p102">内容搜索是一个新的电子数据展示搜索工具，使用新的和改进缩放和性能的功能。内容搜索用于运行非常大的电子数据展示搜索。您可以搜索所有邮箱，所有 Exchange 公用文件夹和所有 SharePoint Online 网站和 OneDrive 中单个内容都搜索业务帐户。可搜索的内容位置的数量没有限制。还有没有限制可以同时运行的搜索数。后运行内容搜索，内容位置数和**内容的搜索**页面上的详细信息窗格中显示搜索结果的估计的数目。运行搜索后您可以预览结果，关键字统计信息获得一个或多个搜索批量编辑内容搜索和结果导出到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="83196-p102">Content Search is a new eDiscovery search tool with new and improved scaling and performance capabilities. Use Content Search to run very large eDiscovery searches. You can search all mailboxes, all Exchange public folders, and all SharePoint Online sites and OneDrive for Business accounts in a single Content Search. There are no limits on the number of content locations that you can search. There are also no limits on the number of searches that can run at the same time. After you run a Content Search, the number of content locations and an estimated number of search results are displayed in the details pane on the **Content search** page. After you run a search you can preview the results, get keyword statistics for one or more searches, bulk-edit content searches, and export the results to a local computer.</span></span> 
  
 <span data-ttu-id="83196-118">**目录**</span><span class="sxs-lookup"><span data-stu-id="83196-118">**Contents**</span></span>
  
[<span data-ttu-id="83196-119">创建搜索</span><span class="sxs-lookup"><span data-stu-id="83196-119">Create a search</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[<span data-ttu-id="83196-120">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-120">Export search results</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[<span data-ttu-id="83196-121">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-121">Preview search results</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[<span data-ttu-id="83196-122">更新搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-122">Update search results</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[<span data-ttu-id="83196-123">编辑搜索</span><span class="sxs-lookup"><span data-stu-id="83196-123">Edit a search</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[<span data-ttu-id="83196-124">重试搜索</span><span class="sxs-lookup"><span data-stu-id="83196-124">Retry a search</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a><span data-ttu-id="83196-125">准备工作</span><span class="sxs-lookup"><span data-stu-id="83196-125">Before you begin</span></span>

- <span data-ttu-id="83196-p103">信息和指导构建搜索查询和使用布尔搜索运算符，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。本文还包含有关搜索敏感信息类型和搜索与您的组织内外的人员共享的内容的信息。</span><span class="sxs-lookup"><span data-stu-id="83196-p103">For information and guidance about building search queries and using Boolean search operators, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md). This article also contains information about searching for sensitive information types and searching for content that's shared with people inside and outside of your organization.</span></span>
    
- <span data-ttu-id="83196-p104">若要有权访问要执行搜索和预览，并将搜索结果导出的**内容搜索**页，管理员、 合规部主管，还是电子数据展示管理员必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心。您无需分配其他搜索权限在 Exchange Online 中，SharePoint Online，或 onedrive for Business 站点。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-p104">To have access to the **Content search** page to perform searches and preview and export search results, an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center. You don't have to assign additional search permissions in Exchange Online, SharePoint Online, or for OneDrive for Business sites. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="83196-p105">有限制应用于内容的搜索来维护的运行状况和质量提供给 Office 365 组织的服务。在大多数情况下，不能修改这些限制，但是，以便您可以考虑这些限制时规划、 运行和解决搜索您应了解它们。有关详细信息，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-p105">There are limits applied to Content Search to maintain the health and quality of services provided to Office 365 organizations. In most cases, you can't modify these limits, but you should be aware of them so that you can take these limits into consideration when planning, running, and troubleshooting searches. For more information, see [Limits for Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="83196-134">请参阅估计的搜索时间基于单个内容搜索中搜索的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="83196-134">See the  section for estimated search times based on the number of mailboxes that are searched in a single Content Search.</span></span> 
    
- <span data-ttu-id="83196-p106">如前面所述，您可以使用内容搜索来搜索 Office 365 组和 Microsoft 团队中的内容。这意味着您可以搜索组邮箱、 共享的日历和与 Office 365 组和 Microsoft 团队关联的 SharePoint 网站。此外，您可以在 Microsoft 团队搜索通道对话。有关 Office 365 组和 Microsoft 团队的信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="83196-p106">As previously stated, you can use Content Search to search for content in Office 365 Groups and Microsoft Teams. This means you can search the group mailbox, shared calendar, and SharePoint sites associated with an Office 365 Group and a Microsoft Team. Additionally, you can search the channel conversations in a Microsoft Team. For information about Office 365 Groups and Microsoft Teams, see:</span></span>
    
  - [<span data-ttu-id="83196-139">了解 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="83196-139">Learn about Office 365 groups</span></span>](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [<span data-ttu-id="83196-140">Microsoft 团队帮助</span><span class="sxs-lookup"><span data-stu-id="83196-140">Microsoft Teams help</span></span>](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    <span data-ttu-id="83196-141">请参阅为 Office 365 组和 Microsoft 团队中的内容搜索提示部分。</span><span class="sxs-lookup"><span data-stu-id="83196-141">See the  section for tips on searching for content in Office 365 Groups and Microsoft Teams.</span></span> 
    
[<span data-ttu-id="83196-142">Return to top</span><span class="sxs-lookup"><span data-stu-id="83196-142">Return to top</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a><span data-ttu-id="83196-143">创建搜索</span><span class="sxs-lookup"><span data-stu-id="83196-143">Create a search</span></span>
<span data-ttu-id="83196-144"><a name="create"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-144"></span></span>

1. <span data-ttu-id="83196-145">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="83196-145">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="83196-146">登录到 Office 365 使用工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="83196-146">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="83196-147">在安全与合规中心的左侧窗格中，单击“搜索和调查”****\>****“内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="83196-147">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**.</span></span>
    
4. <span data-ttu-id="83196-148">单击**新建**![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="83196-148">Click **New**![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
5. <span data-ttu-id="83196-p107">在**新的搜索**页上，键入内容的搜索的名称。此名称必须是唯一组织中。</span><span class="sxs-lookup"><span data-stu-id="83196-p107">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
6. <span data-ttu-id="83196-p108">选择您要搜索的内容位置。您可以在同一个搜索中搜索邮箱、 网站和公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="83196-p108">Choose the content locations that you want to search. You can search mailboxes, sites, and public folders in the same search.</span></span>
    
    ![选择您要搜索的内容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. <span data-ttu-id="83196-p109">**搜索无处不在**选择此选项可搜索您的组织中的所有内容的位置。时选择此选项，您可以选择搜索 （包括非活动邮箱和邮箱的所有 Office 365 组和 Microsoft 团队） 的所有邮箱的所有 SharePoint 和 OneDrive for Business 站点 (包括 Office 365 中的所有组的网站和Microsoft 团队） 和所有公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="83196-p109">**Search everywhere**Select this option to search all content locations in your organization. When you select this option, you can choose to search all mailboxes (including inactive mailboxes and the mailboxes for all Office 365 Groups and Microsoft Teams), all SharePoint and OneDrive for Business sites (which includes the sites for all Office 365 groups and Microsoft Teams), and all public folders.</span></span>
    
    ![单击搜索无处不在选项可搜索的所有内容位置](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. <span data-ttu-id="83196-p110">**自定义位置选择**选择此选项可选择的邮箱和您要搜索的网站。如果选择此选项时，必须以搜索特定服务 （如搜索所有 Exchange 邮箱） 的所有内容位置的灵活性，也可以搜索 Office 365 服务的特定内容的位置。</span><span class="sxs-lookup"><span data-stu-id="83196-p110">**Custom location selection**Select this option to select the mailboxes and sites that you want to search. If you choose this option, you have flexibility to search all content locations for a specific service (such as searching all Exchange mailboxes) or you can search specific content locations for an Office 365 service.</span></span>
    
    <span data-ttu-id="83196-159">添加要搜索的内容位置时，请牢记以下：</span><span class="sxs-lookup"><span data-stu-id="83196-159">Keep the following in mind when adding content locations to search:</span></span>
    
    <span data-ttu-id="83196-160">**邮箱**</span><span class="sxs-lookup"><span data-stu-id="83196-160">**Mailboxes**</span></span>
    
  - <span data-ttu-id="83196-p111">单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)若要指定要搜索的邮箱，显示邮箱选取器为空。这是设计以提高性能。若要将收件人添加到此列表中，在搜索框中键入名称 （最少的 3 个字符） 并单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。</span><span class="sxs-lookup"><span data-stu-id="83196-p111">When you click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to specify mailboxes to search, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add recipients to this list, type a name (a minimum of 3 characters) in the search box and click **Search**![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif).</span></span>
    
  - <span data-ttu-id="83196-p112">您可以将非活动邮箱和通讯组添加到要搜索的邮箱列表中。通讯组的组成员的邮箱中搜索。请注意，不支持动态通讯组。</span><span class="sxs-lookup"><span data-stu-id="83196-p112">You can add inactive mailboxes and distribution groups to the list of mailboxes to search. For distribution groups, the mailboxes of group members are searched. Note that dynamic distribution groups aren't supported.</span></span>
    
  - <span data-ttu-id="83196-p113">若要获取组织中的非活动邮箱的列表，请运行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。此外，您可以转到**数据调控**\>安全中**保留**&amp;合规性中心，然后单击**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非活动邮箱**。</span><span class="sxs-lookup"><span data-stu-id="83196-p113">To get a list of the inactive mailboxes in your organization, run the command  `Get-Mailbox -InactiveMailboxOnly` in Exchange Online PowerShell. Alternatively, you can go to **Data governance** \> **Retention** in the Security &amp; Compliance Center, and then click **More**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inactive mailboxes**.</span></span>
    
  - <span data-ttu-id="83196-p114">您还可以添加与 Office 365 组或 Microsoft 团队相关联的邮箱。在这种情况下，搜索仅组或团队邮箱;不搜索的邮箱的组或团队成员。若要搜索他们，您必须明确将它们添加到搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-p114">You can also add the mailbox that's associated with an Office 365 Group or a Microsoft Team. In this case, only the group or team mailbox is searched; the mailboxes of the group or team members aren't searched. To search them, you have to specifically add them to the search.</span></span>
    
  - <span data-ttu-id="83196-172">如果您不想要包括到搜索所有邮箱，选择**要搜索的选择特定邮箱**，但不将邮箱添加到列表。</span><span class="sxs-lookup"><span data-stu-id="83196-172">If you don't want to include any mailboxes to the search, select **Choose specific mailboxes to search**, but don't add a mailbox to the list.</span></span>
    
    <span data-ttu-id="83196-173">**网站**</span><span class="sxs-lookup"><span data-stu-id="83196-173">**Sites**</span></span>
    
  - <span data-ttu-id="83196-p115">单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)将站点添加到搜索。键入要搜索的每个网站的 URL。内容搜索工具将验证 URL，并将其添加到网站搜索的列表。</span><span class="sxs-lookup"><span data-stu-id="83196-p115">Click **Add**![Add Icon](media/ITPro-EAC-AddIcon.gif) to add sites to the search. Type the URL for each site that you want to search. The Content Search tool will validate the URL, and then add it to the list of sites to search.</span></span> 
    
  - <span data-ttu-id="83196-p116">您可以添加具有相关联的 Office 365 组或 Microsoft 团队的 SharePoint。请参阅有关如何查找组或团队的 URL 的指南。</span><span class="sxs-lookup"><span data-stu-id="83196-p116">You can add the SharePoint that's associated with an Office 365 Group or a Microsoft Team. See the  section for guidance about how to find the URL for group or team.</span></span> 
    
  - <span data-ttu-id="83196-179">如果您不想要在搜索中包括的任何网站，选择**选择特定网站搜索**，但不将网站添加到列表。</span><span class="sxs-lookup"><span data-stu-id="83196-179">If you don't want to include any sites in a search, select **Choose specific sites to search**, but don't add a site to the list.</span></span>
    
    <span data-ttu-id="83196-180">**公用文件夹**</span><span class="sxs-lookup"><span data-stu-id="83196-180">**Public folders**</span></span>
    
    <span data-ttu-id="83196-181">有关公用文件夹，您可以选择搜索 Exchange Online 组织中的所有公用文件夹或不搜索任何公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="83196-181">For public folders, you can choose to search all public folders in your Exchange Online organization or not search any public folders.</span></span>
    
7. <span data-ttu-id="83196-182">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="83196-182">Click **Next**.</span></span>
    
8. <span data-ttu-id="83196-183">在“**新搜索**”页上，您可以添加用于创建搜索查询的关键字和条件。</span><span class="sxs-lookup"><span data-stu-id="83196-183">On the **New search** page, you can add keywords and conditions to create the search query.</span></span> 
    
    ![使用关键字和条件创建搜索查询](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. <span data-ttu-id="83196-p117">在下框**希望什么我们查找？**，在框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用使用布尔运算符，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**更复杂的查询。您还可以搜索文档或搜索外部共享的文档中的敏感信息 （如社会保险号码）。如果保留关键字框为空，则将在搜索结果中包含位于指定的内容位置的所有内容。</span><span class="sxs-lookup"><span data-stu-id="83196-p117">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, **NEAR**, or **ONEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span> 
    
2. <span data-ttu-id="83196-p118">您可以单击**显示关键字列表**复选框，键入每行中的关键字。如果这样做，每个行的关键字进行连接的**OR**运算符创建搜索查询中。</span><span class="sxs-lookup"><span data-stu-id="83196-p118">You can click the **Show keyword list** checkbox and the type a keyword in each row. If you do this, the keywords on each row are connected by the **OR** operator in the search query that's created.</span></span> 
    
    ![您可以在关键字列表中的某行中键入关键字或关键字阶段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    <span data-ttu-id="83196-p119">为什么使用关键字列表？您可以获取显示的项目数与每个关键字匹配的统计信息。这可以帮助您快速识别的关键字是最 （和至少） 有效。行中，您还可以使用关键字短语 （用括号括起来）。有关搜索统计信息的详细信息，请参阅[视图的内容的搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-p119">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
    
    <span data-ttu-id="83196-198">有关使用关键字列表，请参阅指南部分。</span><span class="sxs-lookup"><span data-stu-id="83196-198">See the  section for guidance on using the keyword list.</span></span> 
    
3. <span data-ttu-id="83196-p120">单击**检查错误的查询**来检查您的查询不支持的字符和不可能大写的布尔运算符。不支持的字符通常隐藏和通常会导致搜索错误或返回意外的结果。有关检查不支持的字符的详细信息，请参阅[检查错误内容的搜索查询](check-your-content-search-query-for-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-p120">Click **Check query for typos** to check your query for unsupported characters and for Boolean operators that might not be capitalized. Unsupported characters are often hidden and typically cause a search error or return unintended results. For more information about the unsupported characters that are checked, see [Check your Content Search query for errors](check-your-content-search-query-for-errors.md).</span></span>
    
4. <span data-ttu-id="83196-p121">在**条件**下将添加到搜索查询来缩小搜索范围并返回一组多精简的结果的条件。每个条件向 KQL 搜索查询创建和启动搜索时运行一个子句。条件逻辑**AND**运算符通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的条件。这是如何帮助条件以缩小结果。</span><span class="sxs-lookup"><span data-stu-id="83196-p121">Under **Conditions**, add conditions to a search query to narrow a search and return a more refined set of results. Each condition adds a clause to the KQL search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be included in the results. This is how conditions help to narrow your results.</span></span> 
    
||
|:-----|
|<span data-ttu-id="83196-207">有关创建搜索查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-207">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search ](keyword-queries-and-search-conditions.md).</span></span> |
   
9. <span data-ttu-id="83196-208">单击**搜索**以保存的搜索设置并开始搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-208">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="83196-p122">启动搜索。完成搜索后，将详细信息窗格中显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="83196-p122">The search is started. When the search is completed, the following information is displayed in the details pane.</span></span>
    
    ![在所选内容的搜索的详细信息窗格中显示搜索统计信息](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. <span data-ttu-id="83196-212">日期和时间的上次运行搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-212">The date and time that the search was last run.</span></span>
    
2. <span data-ttu-id="83196-p123">号码 （和总大小） 的项找到的匹配搜索查询。项目类型的示例包括电子邮件、 日历项和文档。如果项目中包含的关键字搜索的多个实例，它是仅计算一次中的总项目数。例如，如果您搜索单词"库存"或"tip"和电子邮件包含单词"库存"的三个实例，它是仅计算一次**项目**字段中。</span><span class="sxs-lookup"><span data-stu-id="83196-p123">The number (and total size) of items that were found that matched the search query. Examples of item types include email messages, calendar items, and documents. If an item contains multiple instances of a keyword that is being searched for, it's only counted once in the total number of items. For example, if you're searching for words "stock" or "tip" and an email message contains three instances of the word "stock", it's only counted once in the **Items** field.</span></span> 
    
3. <span data-ttu-id="83196-p124">数量和未编制索引中的项目已搜索的内容位置的总大小。不满足搜索条件的未编制索引项的数目将包括在细节窗格中显示的搜索统计信息。如果未编制索引的项匹配的搜索查询 （因为其他消息或文档属性符合搜索条件），它不会包含在未编制索引的项的估计数目。但是，如果未编制索引的项目中排除的搜索条件，它不会包含在未编制索引的项的估计值中。</span><span class="sxs-lookup"><span data-stu-id="83196-p124">The number and total size of unindexed items in the content locations that were searched. The number of unindexed items that don't meet the search criteria will be included in the search statistics displayed in the details pane. If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. However, if an unindexed item is excluded by the search criteria, it won't be included in the estimate of unindexed items.</span></span>
    
4. <span data-ttu-id="83196-p125">每种类型的内容位置的搜索数。邮箱，请注意，已搜索的邮箱总数中包含的存档邮箱。在上面的示例中，搜索四个用户邮箱并启用这些用户的存档邮箱。这就是为什么八个邮箱中搜索统计信息的引用。</span><span class="sxs-lookup"><span data-stu-id="83196-p125">The number of each type of content location that was searched. For mailboxes, note that archive mailboxes are included in the total number of mailboxes that were searched. In the previous example, four user mailboxes were searched and the archive mailbox for each of these users is enabled. That's why eight mailboxes are cited in the search statistics.</span></span>
    
5. <span data-ttu-id="83196-225">链接预览搜索结果，或运行搜索再次更新搜索统计信息。</span><span class="sxs-lookup"><span data-stu-id="83196-225">Links to preview the search results or run the search again to update the search statistics.</span></span>
    
    <span data-ttu-id="83196-226">如有必要，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)更新所选搜索的详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="83196-226">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane for the selected search.</span></span> 
    
[<span data-ttu-id="83196-227">Return to top</span><span class="sxs-lookup"><span data-stu-id="83196-227">Return to top</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a><span data-ttu-id="83196-228">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-228">Export search results</span></span>
<span data-ttu-id="83196-229"><a name="export"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-229"></span></span>

<span data-ttu-id="83196-p126">搜索成功运行后，您可以将搜索结果导出到本地计算机。导出电子邮件结果时，他们正在下载到您的计算机作为 PST 文件。导出时内容来自 SharePoint 和 OneDrive for Business 站点，导出本机 Office 文档的副本。还有其他文档和导出的搜索结果中包含的报告。有关详细信息，请参阅[导出搜索结果从 Office 365 安全性&amp;合规性中心](export-search-results.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-p126">After a search is successfully run, you can export the search results to a local computer. When you export email results, they're downloaded to your computer as PST files. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents are exported. There are also additional documents and reports that are included with the exported search results. For more information, see [Export search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
  
## <a name="preview-search-results"></a><span data-ttu-id="83196-235">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-235">Preview search results</span></span>
<span data-ttu-id="83196-236"><a name="preview"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-236"></span></span>

<span data-ttu-id="83196-p127">搜索成功完成后，您可以预览搜索结果。有多个与预览内容搜索结果相关的限制。有关详细信息，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。请注意未编制索引的项目不可用的预览。</span><span class="sxs-lookup"><span data-stu-id="83196-p127">After a search is successfully completed, you can preview the search results. There are a number of limits related to previewing Content Search results. For more information, see [Limits for Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md). Note that unindexed items aren't available for previewing.</span></span>
  
1. <span data-ttu-id="83196-241">在**内容搜索**页上，选择搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-241">On the **Content search** page, select a search.</span></span> 
    
2. <span data-ttu-id="83196-p128">在详细信息窗格中，在**结果**框中，单击**预览搜索结果**。**预览搜索结果**页打开，并包含搜索结果项的列表。</span><span class="sxs-lookup"><span data-stu-id="83196-p128">In the details pane, under **Results**, click **Preview search results**. The **Preview search results** page opens, and contains a list of the search result items.</span></span> 
    
    <span data-ttu-id="83196-244">您可以单击列标题基于主题、 类型、 发件人或项目已接收的源邮箱中的日期对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="83196-244">You can click a column header to sort the results based on subject, type, sender, or the date an item was received in the source mailbox.</span></span>
    
3. <span data-ttu-id="83196-245">单击要预览的项目。</span><span class="sxs-lookup"><span data-stu-id="83196-245">Click an item to preview.</span></span>
    
    <span data-ttu-id="83196-246">在预览窗格中打开项目时。</span><span class="sxs-lookup"><span data-stu-id="83196-246">The item is opened in the preview pane.</span></span>
    
4. <span data-ttu-id="83196-p129">如果为预览或下载文档的副本，则不受支持的文件类型，则可以单击**下载原始文件**下载到本地计算机。对于.aspx 网页，页面的 URL 是包含，但您可能没有访问页上的权限。</span><span class="sxs-lookup"><span data-stu-id="83196-p129">If a file type isn't supported for preview or to download a copy of a document, you can click **Download original file** to download it to your local computer. For .aspx Web pages, the URL for the page is included though you might not have permissions to access the page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="83196-p130">如果预览上次运行超过 7 天的搜索的搜索结果时，将提示您要更新的搜索结果。重新运行搜索以获得满足搜索查询的最新结果。</span><span class="sxs-lookup"><span data-stu-id="83196-p130">If you preview the search results for a search that was last run more than 7 days ago, you will be prompted to update the search results. The search is rerun to get the most current results that meet the search query.</span></span> 
  
### <a name="file-types-that-can-be-previewed"></a><span data-ttu-id="83196-251">可以预览的文件类型</span><span class="sxs-lookup"><span data-stu-id="83196-251">File types that can be previewed</span></span>

<span data-ttu-id="83196-p131">您可以预览预览窗格中的受支持的文件类型。如果不支持的文件类型，必须将文件的副本下载到本地计算机进行查看。以下文件类型支持并且可以预览在**预览搜索结果**页。</span><span class="sxs-lookup"><span data-stu-id="83196-p131">You can preview supported file types in the preview pane. If a file type isn't supported, you'll have to download a copy of the file to your local computer to view it. The following file types are supported and can be previewed on the **Preview search results** page.</span></span> 
  
- <span data-ttu-id="83196-255">.txt、.html、.mhtml</span><span class="sxs-lookup"><span data-stu-id="83196-255">.txt, .html, .mhtml</span></span>
    
- <span data-ttu-id="83196-256">.eml</span><span class="sxs-lookup"><span data-stu-id="83196-256">.eml</span></span>
    
- <span data-ttu-id="83196-257">.doc、.docx、.docm</span><span class="sxs-lookup"><span data-stu-id="83196-257">.doc, .docx, .docm</span></span>
    
- <span data-ttu-id="83196-258">.pptm、.pptx</span><span class="sxs-lookup"><span data-stu-id="83196-258">.pptm, .pptx</span></span>
    
- <span data-ttu-id="83196-259">.pdf</span><span class="sxs-lookup"><span data-stu-id="83196-259">.pdf</span></span>
    
<span data-ttu-id="83196-p132">此外，也支持以下文件容器类型。您可以查看文件的列表中预览窗格中的容器。</span><span class="sxs-lookup"><span data-stu-id="83196-p132">Additionally, the following file container types are supported. You can view the list of files in the container in the preview pane.</span></span>
  
- <span data-ttu-id="83196-262">.zip</span><span class="sxs-lookup"><span data-stu-id="83196-262">.zip</span></span>
    
- <span data-ttu-id="83196-263">.gzip</span><span class="sxs-lookup"><span data-stu-id="83196-263">.gzip</span></span>
    
[<span data-ttu-id="83196-264">Return to top</span><span class="sxs-lookup"><span data-stu-id="83196-264">Return to top</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a><span data-ttu-id="83196-265">更新搜索结果</span><span class="sxs-lookup"><span data-stu-id="83196-265">Update search results</span></span>
<span data-ttu-id="83196-266"><a name="restart"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-266"></span></span>

<span data-ttu-id="83196-p133">您更新现有内容搜索的结果，重新上指定的所有内容位置运行搜索查询。更新搜索结果的明显原因是要获取最新的数据。</span><span class="sxs-lookup"><span data-stu-id="83196-p133">When you update the results of an existing Content Search, the search query is rerun on all specified content locations. The obvious reason to update search results is to get the most recent data.</span></span>
  
1. <span data-ttu-id="83196-269">在**内容搜索**页上，选择您要更新的结果的搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-269">On the **Content search** page, select the search that you want to update the results for.</span></span> 
    
2. <span data-ttu-id="83196-270">在详细信息窗格中，在**结果**框中，单击**更新搜索结果**。</span><span class="sxs-lookup"><span data-stu-id="83196-270">In the details pane, under **Results**, click **Update search results**.</span></span>
    
    <span data-ttu-id="83196-p134">状态消息显示反映正在检索结果。完成搜索后，更新的信息在**结果**显示详细信息窗格中。请注意详细信息窗格中的**搜索**字段中的日期已更新到当前日期和时间。要刷新列表中的内容搜索的信息，请单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="83196-p134">A status messages is displayed saying that the results are being retrieved. When the search is finished, updated information is displayed under **Results** in the details pane. Note that the date in the **Searched on** field in the details pane is updated to the current date and time. To refresh the information in the list of Content Searches, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif).</span></span>
    
[<span data-ttu-id="83196-275">Return to top</span><span class="sxs-lookup"><span data-stu-id="83196-275">Return to top</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a><span data-ttu-id="83196-276">编辑搜索</span><span class="sxs-lookup"><span data-stu-id="83196-276">Edit a search</span></span>
<span data-ttu-id="83196-277"><a name="edit"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-277"></span></span>

<span data-ttu-id="83196-278">您可以更改现有内容搜索的源邮箱和搜索查询。</span><span class="sxs-lookup"><span data-stu-id="83196-278">You can change the source mailboxes and the search query for an existing Content Search.</span></span>
  
1. <span data-ttu-id="83196-279">在**内容搜索**页上，选择搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-279">On the **Content search** page, select a search.</span></span> 
    
2. <span data-ttu-id="83196-280">在详细信息窗格中，在**查询**下单击**编辑搜索**。</span><span class="sxs-lookup"><span data-stu-id="83196-280">In the details pane, under **Query**, click **Edit search**.</span></span>
    
3. <span data-ttu-id="83196-p135">在**位置**页中，可以更改哪些邮箱、 组、 SharePoint 网站或 OneDrive for Business 站点搜索。您还可以选择 （或未选择） 搜索 Exchange 中的所有公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="83196-p135">On the **Locations** page, you can change which mailboxes, groups, SharePoint sites, or OneDrive for Business sites to search. You can also select (or un-select) to search all public folders in Exchange.</span></span> 
    
4. <span data-ttu-id="83196-283">在**查询**页中，您可以编辑搜索查询。</span><span class="sxs-lookup"><span data-stu-id="83196-283">On the **Query** page, you can edit the search query.</span></span> 
    
5. <span data-ttu-id="83196-284">要开始修订后的搜索，请单击**源**或**位置**页上的**搜索**。</span><span class="sxs-lookup"><span data-stu-id="83196-284">To start the revised search, click **Search** on either the **Sources** or **Locations** page.</span></span> 
    
    <span data-ttu-id="83196-p136">启动修订后的搜索。搜索完成后，预计的修订后的搜索结果将显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="83196-p136">The revised search is started. When the search is completed, the estimated results for the revised search are displayed in the details pane.</span></span>
    
## <a name="retry-a-search"></a><span data-ttu-id="83196-287">重试搜索</span><span class="sxs-lookup"><span data-stu-id="83196-287">Retry a search</span></span>
<span data-ttu-id="83196-288"><a name="retry"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-288"></span></span>

<span data-ttu-id="83196-p137">如果搜索返回任何错误，您无需重新搜索所有内容的位置。可以重新运行搜索，以便仅失败的内容的位置是搜索再次。若要重新搜索所有内容的位置，您可以更新的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="83196-p137">If a search returns any errors, you don't have to re-search all of the content locations. You can rerun the search so that only the content locations that failed are search again. To re-search all content locations, you can update the search results.</span></span>
  
1. <span data-ttu-id="83196-292">在**内容搜索**页上，选择包含您要重新搜索的内容位置的搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-292">On the **Content search** page, select the search that contains the content locations that you want to re-search.</span></span> 
    
2. <span data-ttu-id="83196-293">在细节窗格中，在**错误**下单击**重试搜索**。</span><span class="sxs-lookup"><span data-stu-id="83196-293">In the details pane, under **Error**, click **Retry search**.</span></span>
    
    <span data-ttu-id="83196-p138">状态消息显示反映正在检索结果。完成搜索时，更新的信息在**结果**显示详细信息窗格中。请注意详细信息窗格中的**搜索**字段中的日期已更新到当前日期和时间。要刷新列表中的搜索的信息，请单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="83196-p138">A status messages is displayed saying that the results are being retrieved. When the search is complete, updated information is displayed under **Results** in the details pane. Note that the date in the **Searched on** field in the details pane is updated to the current date and time. To refresh the information in the list of searches, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif).</span></span>
    
[<span data-ttu-id="83196-298">返回顶部</span><span class="sxs-lookup"><span data-stu-id="83196-298">Return to top</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a><span data-ttu-id="83196-299">详细信息</span><span class="sxs-lookup"><span data-stu-id="83196-299">More information</span></span>
<span data-ttu-id="83196-300"><a name="moreinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="83196-300"></span></span>

<span data-ttu-id="83196-301">下面是有关内容搜索的详细信息。</span><span class="sxs-lookup"><span data-stu-id="83196-301">Here's more information about Content Searches.</span></span>
  
[<span data-ttu-id="83196-302">限制和性能</span><span class="sxs-lookup"><span data-stu-id="83196-302">Limits and performance</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#limits)
  
[<span data-ttu-id="83196-303">未编制索引的项目</span><span class="sxs-lookup"><span data-stu-id="83196-303">Unindexed items</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#unindexeditems)
  
[<span data-ttu-id="83196-304">Microsoft 团队和 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="83196-304">Microsoft Teams and Office 365 Groups</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#teams)
  
[<span data-ttu-id="83196-305">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="83196-305">OneDrive for Business</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#onedrive)
  
[<span data-ttu-id="83196-306">搜索查询</span><span class="sxs-lookup"><span data-stu-id="83196-306">Search queries</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#queries)
  
[<span data-ttu-id="83196-307">搜索的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="83196-307">Searching inactive mailboxes</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#inactivemailboxes)
  
[<span data-ttu-id="83196-308">其他</span><span class="sxs-lookup"><span data-stu-id="83196-308">Miscellaneous</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#misc)
  
[<span data-ttu-id="83196-309">（返回页首）</span><span class="sxs-lookup"><span data-stu-id="83196-309">(Return to top)</span></span>](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
 <span data-ttu-id="83196-310">**限制和性能**</span><span class="sxs-lookup"><span data-stu-id="83196-310">**Limits and performance**</span></span>
  
- <span data-ttu-id="83196-311">应用于的内容的搜索功能的限制的说明，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="83196-311">For a description of the limits that are applied to the Content Search feature, see [Limits for Search in the Office 365 Security &amp; Compliance Center](limits-for-content-search.md).</span></span>
    
- <span data-ttu-id="83196-p139">Microsoft 收集有关运行所有 Office 365 组织的内容搜索的性能信息。时搜索查询的复杂性会影响搜索时间，搜索会影响搜索收回长是邮箱数的最大因子。虽然 Microsoft 没有搜索时间提供服务级别协议下, 表将列出内容搜索基于包括在搜索的邮箱数的平均搜索时间。</span><span class="sxs-lookup"><span data-stu-id="83196-p139">Microsoft collects performance information for Content Searches run by all Office 365 organizations. While the complexity of the search query can impact search times, the biggest factor that affects how long searches take is the number of mailboxes searched. Although Microsoft doesn't provide a Service Level Agreement for search times, the following table lists average search times for a Content Search based on the number of mailboxes included in the search.</span></span>
    
|<span data-ttu-id="83196-315">**邮箱数**</span><span class="sxs-lookup"><span data-stu-id="83196-315">**Number of mailboxes**</span></span>|<span data-ttu-id="83196-316">**平均搜索时间**</span><span class="sxs-lookup"><span data-stu-id="83196-316">**Average search time**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83196-317">100</span><span class="sxs-lookup"><span data-stu-id="83196-317">100</span></span>  <br/> |<span data-ttu-id="83196-318">30 秒</span><span class="sxs-lookup"><span data-stu-id="83196-318">30 seconds</span></span>  <br/> |
|<span data-ttu-id="83196-319">1,000</span><span class="sxs-lookup"><span data-stu-id="83196-319">1,000</span></span>  <br/> |<span data-ttu-id="83196-320">45 秒</span><span class="sxs-lookup"><span data-stu-id="83196-320">45 seconds</span></span>  <br/> |
|<span data-ttu-id="83196-321">10,000</span><span class="sxs-lookup"><span data-stu-id="83196-321">10,000</span></span>  <br/> |<span data-ttu-id="83196-322">4 分钟</span><span class="sxs-lookup"><span data-stu-id="83196-322">4 minutes</span></span>  <br/> |
|<span data-ttu-id="83196-323">25000</span><span class="sxs-lookup"><span data-stu-id="83196-323">25,000</span></span>  <br/> |<span data-ttu-id="83196-324">此参数指定在关闭连接之前，已打开的、与目标邮件传递服务器的 SMTP 连接可以保持空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="83196-324">10 minutes</span></span>  <br/> |
|<span data-ttu-id="83196-325">50,000 个</span><span class="sxs-lookup"><span data-stu-id="83196-325">50,000</span></span>  <br/> |<span data-ttu-id="83196-326">20 分钟</span><span class="sxs-lookup"><span data-stu-id="83196-326">20 minutes</span></span>  <br/> |
|<span data-ttu-id="83196-327">100,000</span><span class="sxs-lookup"><span data-stu-id="83196-327">100,000</span></span>  <br/> |<span data-ttu-id="83196-328">25 分钟</span><span class="sxs-lookup"><span data-stu-id="83196-328">25 minutes</span></span>  <br/> |
   

  
 <span data-ttu-id="83196-329">**未编制索引的项目**</span><span class="sxs-lookup"><span data-stu-id="83196-329">**Unindexed items**</span></span>
  
- <span data-ttu-id="83196-p140">为要搜索的内容位置中的前面所述，未编制索引的项目中包含估计的搜索结果。如果未编制索引的项匹配的搜索查询 （因为其他消息或文档属性符合搜索条件），它不会包含在未编制索引的项的估计数目。如果未编制索引的项目中排除的搜索条件，它也不会包含中未编制索引的项的估计数目。有关详细信息，请参阅[内容搜索中的未编制索引的项](https://go.microsoft.com/fwlink/p/?LinkId=780739)。</span><span class="sxs-lookup"><span data-stu-id="83196-p140">As previously explained, unindexed items in content locations that are searched are included in the estimated search results. If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. If an unindexed item is excluded by the search criteria, it also won't be included in the estimated number of unindexed items. For more information, see [Unindexed items in Content Search](https://go.microsoft.com/fwlink/p/?LinkId=780739).</span></span>
    

  
 <span data-ttu-id="83196-334">**Microsoft 团队和 Office 365 组**</span><span class="sxs-lookup"><span data-stu-id="83196-334">**Microsoft Teams and Office 365 Groups**</span></span>
  
- <span data-ttu-id="83196-p141">在 Office 365 组上构建的 Microsoft 团队。因此，搜索它们是非常类似。搜索的 Microsoft 团队和 Office 365 组中的内容时，请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="83196-p141">Microsoft Teams are built on Office 365 Groups. Therefore, searching them is very similar. Keep the following things in mind when searching for content in Microsoft Teams and Office 365 Groups.</span></span>
    
  - <span data-ttu-id="83196-338">若要搜索的内容位于 Microsoft 团队和 Office 365 组中，您必须指定的邮箱和与团队或组关联的 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="83196-338">To search for content located in Microsoft Teams and Office 365 Groups, you have to specify the mailbox and SharePoint site that are associated with a team or group.</span></span>
    
  - <span data-ttu-id="83196-p142">运行在 Exchange Online 中的 Microsoft 团队或 Office 365 组查看属性**获取 UnifiedGroup** cmdlet。这是一个好方法获取与团队或一组相关联的网站的 URL。例如，下面的命令的一个名为高级领导团队的 Office 365 组显示所选的属性：</span><span class="sxs-lookup"><span data-stu-id="83196-p142">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for a Microsoft Team or an Office 365 Group. This is a good way to get the URL for the site that's associated with a team or a group. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > <span data-ttu-id="83196-342">若要运行**Get UnifiedGroup** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。</span><span class="sxs-lookup"><span data-stu-id="83196-342">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="83196-p143">用户的邮箱搜索，搜索时不会搜索任何 Microsoft 团队或 Office 365 组的成员的用户。同样，搜索当您搜索 Microsoft 团队或 Office 365 组中，只有组邮箱和组网站指定;除非您明确将它们添加到搜索，不搜索的邮箱和 OneDrive for Business 的组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="83196-p143">When a user's mailbox is searched, any Microsoft Team or Office 365 Group that the user is a member of won't be searched. Similarly, when you search a Microsoft Team or an Office 365 Group, only the group mailbox and group site that you specify is searched; the mailboxes and OneDrive for Business accounts of group members aren't searched unless you explicitly add them to the search.</span></span>
    
  - <span data-ttu-id="83196-p144">若要获取的 Microsoft 团队或 Office 365 组成员的列表，可以查看属性在**主页\>组**Office 365 管理中心中的页。此外，还可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="83196-p144">To get a list of the members of a Microsoft Team or an Office 365 Group, you can view the properties on the **Home \> Groups** page in the Office 365 admin center. Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > <span data-ttu-id="83196-347">若要运行**Get UnifiedGroupLinks** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。</span><span class="sxs-lookup"><span data-stu-id="83196-347">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="83196-p145">与 Microsoft 团队相关联的邮箱中存储的一部分的 Microsoft 团队通道对话。同样，在频道的工作组成员共享的文件存储团队的 SharePoint 网站上。因此，您需要将 Microsoft 团队邮箱和 SharePoint 网站添加为通道中搜索对话和文件的内容位置。</span><span class="sxs-lookup"><span data-stu-id="83196-p145">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to add the Microsoft Team mailbox and SharePoint site as a content location to search conversations and files in a channel.</span></span>
    
  - 
    
    <span data-ttu-id="83196-p146">此外，参与聊天的用户的 Exchange Online 邮箱中存储是在 Microsoft 团队中的聊天列表的一部分的对话。和用户共享聊天对话中的文件存储在 OneDrive for Business 帐户的用户的共享文件。因此，您需要将单个用户邮箱和 OneDrive 业务帐户添加为聊天列表中搜索对话和文件的内容位置。</span><span class="sxs-lookup"><span data-stu-id="83196-p146">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the Exchange Online mailbox of the users who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business account of the user who shares the file. Therefore, you have to add the individual user mailboxes and OneDrive for Business accounts as content locations to search conversations and files in the Chat list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83196-p147">参与对话中的 Microsoft 团队的聊天列表的一部分的用户必须具有 Exchange Online （基于云的） 使您可以搜索聊天邮箱。这是因为对话的一部分的聊天列表存储在基于云的邮箱的聊天参与者。如果聊天参与者没有 Exchange Online 邮箱，您将无法搜索聊天。例如，在 Exchange 混合部署，具有内部部署邮箱的用户可能能够参与对话中的 Microsoft 团队的聊天列表的一部分。但是在这种情况下，从这些对话的内容不搜索因为用户没有基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="83196-p147">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox in order for you to search chat conversations. That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, you won't be able to search chat conversations. For example, in an Exchange hybrid deployment, users with an on-premises mailbox might be able to participate in conversations that are part of the Chat list in Microsoft Teams. However in this case, content from these conversation aren't searchable because the users don't have cloud-based mailboxes.</span></span> 
  
  - <span data-ttu-id="83196-p148">每个通道，Microsoft 团队或团队包含 Wiki 笔记记录和协作。Wiki 内容将自动保存到.mht 格式的文件时。此文件存储在团队的 SharePoint 网站上的团队 Wiki 数据文档库。内容搜索工具可用于通过指定为要搜索的内容位置的团队的 SharePoint 网站中搜索 Wiki。</span><span class="sxs-lookup"><span data-stu-id="83196-p148">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can use the Content Search tool to search the Wiki by specifying the team's SharePoint site as the content location to search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="83196-p149">2017 年 6 月 22，发布 （时搜索团队的 SharePoint 网站） 的 Microsoft 团队或通道搜索 Wiki 的功能。Wiki 网页保存或更新的日期或之后可供搜索。Wiki 网页上一次保存或更新的日期之前不可供搜索。</span><span class="sxs-lookup"><span data-stu-id="83196-p149">The capability to search the Wiki for a Microsoft Team or Channel (when you search the team's SharePoint site) was released on June 22, 2017. Wiki pages that were saved or updated on that date or after are available to be searched. Wiki pages last saved or updated before that date aren't available for search.</span></span> 
  

  
 <span data-ttu-id="83196-366">**OneDrive for Business **</span><span class="sxs-lookup"><span data-stu-id="83196-366">**OneDrive for Business **</span></span>
  
- <span data-ttu-id="83196-p150">若要为 OneDrive for Business 组织中的网站中收集的 url 列表，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的脚本创建包含所有 OneDrive for Business 网站的列表的文本文件。若要运行此脚本，您将需要安装和使用 SharePoint Online Management Shell。一定要追加到每个 OneDrive for Business 站点您想要搜索的组织的 MySite 域的 URL。这是包含所有您 OneDrive for Business; 的域例如， `https://contoso-my.sharepoint.com`。下面是用户的 onedrive for Business 站点的 URL 的一个示例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="83196-p150">To collect a list of the URLs for the OneDrive for Business sites in your organization, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). The script in this article creates a text file that contains a list of all OneDrive for Business sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive for Business site that you want to search. This is the domain that contains all your OneDrive for Business; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive for Business site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
    

  
 <span data-ttu-id="83196-373">**搜索查询**</span><span class="sxs-lookup"><span data-stu-id="83196-373">**Search queries**</span></span>
  
- <span data-ttu-id="83196-374">使用关键字列表创建的搜索查询时，请确保记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="83196-374">Keeping the following things in mind when using the keyword list to create a search query.</span></span>
    
  - <span data-ttu-id="83196-p151">您必须选择**显示关键字列表**复选框，然后在单独的行以创建的搜索查询中键入每个关键字其中每一行中的关键字 （或关键字短语） 进行连接的**OR**运算符。如果您只在关键字框中粘贴的关键字列表，或键入关键字后按**Enter**键，它们不会通过**OR**运算符进行连接。下面是添加的关键字列表的不正确，并正确的示例。</span><span class="sxs-lookup"><span data-stu-id="83196-p151">You have to select the **Show keyword list** checkbox and then type each keyword in a separate row to create a search query where the keywords (or keyword phrases) in each row are connected by the **OR** operator. If you just paste a list of keywords in the keyword box or press the **Enter** key after typing a keyword, they won't be connected by the **OR** operator. Here are incorrect and correct example of adding a list of keywords.</span></span> 
    
    <span data-ttu-id="83196-378">**不正确**</span><span class="sxs-lookup"><span data-stu-id="83196-378">**Incorrect**</span></span>
    
    ![不正确的方式设置关键字列表格式 （通过关键字框中粘贴的列表）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    <span data-ttu-id="83196-380">**正确**</span><span class="sxs-lookup"><span data-stu-id="83196-380">**Correct**</span></span>
    
    ![正确的方式设置关键字列表格式 （通过选择复选框，然后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - <span data-ttu-id="83196-p152">您可以还准备一组关键字或关键字短语中的 Excel 文件或一个纯文本文件，然后复制并粘贴到关键字列表中的列表。若要执行此操作，您必须选择**显示关键字列表**复选框。然后，单击关键字列表中的第一行并粘贴您的列表。从 Excel 或文本文件每行将中粘贴到单独的关键字列表中的行。</span><span class="sxs-lookup"><span data-stu-id="83196-p152">You can also prepare a list of keywords or keyword phrases in an Excel file or a plain text file, and then copy and paste your list in to the keyword list. To do this, you have to select the **Show keyword list** check box. Then, click the first row in the keyword list and paste your list. Each line from the Excel or text file will be pasted in to separate row in the keyword list.</span></span> 
    
  - <span data-ttu-id="83196-p153">创建查询使用关键字列表后，它是确认搜索查询语法 （在所选搜索的详细信息窗格中），最好在搜索查询是您的用途。在搜索查询中的详细信息窗格中显示在**查询**下，使用文本 **(c:s)** 分隔的关键字。 这表示关键字进行连接的**OR**运算符。同样，如果您的搜索查询包含条件，关键字和条件使用分隔文本 **(c:c)**。 这表示关键字进行连接的情况的**AND**运算符。下面是一个示例 （显示详细信息窗格中） 的搜索查询的结果时使用关键字列表和条件。</span><span class="sxs-lookup"><span data-stu-id="83196-p153">After you create a query using the keyword list, it's a good idea to verify the search query syntax (in the details pane of the selected search) to make the search query is what you intended. In the search query that's displayed under **Query** in the details pane, the keywords are separated by the text **(c:s)**. This indicates that the keywords are connected by the **OR** operator. Similarly, if your search query includes conditions, the keywords and the conditions are separated by the text **(c:c)**. This indicates that the keywords are connected to the conditions by the **AND** operator. Here's an example of the search query (displayed in the Details pane) that results when using the keyword list and a condition.</span></span> 
    
    ![使用关键字列表和条件时创建的查询的示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - <span data-ttu-id="83196-p154">如果您有包含非英文字符 （例如中文字符） 的关键字的搜索查询，您可能需要使用**集 ComplianceSearch** cmdlet 可以配置内容搜索的语言属性。当您创建内容搜索中安全使用 GUI&amp;合规中心的默认语言是中性。</span><span class="sxs-lookup"><span data-stu-id="83196-p154">If you have a search query that contains keywords for non-English characters (such as Chinese characters), you might have to use the **Set-ComplianceSearch** cmdlet to configure the language property for the content search. When you create a content search using the GUI in the Security &amp; Compliance Center, the default language is neutral.</span></span> 
    
    <span data-ttu-id="83196-p155">您如何知道您是否需要更改内容的搜索的语言设置？如果您是某些内容位置包含要搜索的非英语字符，但搜索未返回任何结果，则可能原因的语言设置。</span><span class="sxs-lookup"><span data-stu-id="83196-p155">How can you tell if you need to change the language setting for a content search? If you're certain content locations contain the non-English characters you're searching for, but the search returns no results, the language setting might be the cause.</span></span>
    
    <span data-ttu-id="83196-397">若要更改现有的内容搜索的语言设置，请运行以下命令在安全&amp;合规性中心 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83196-397">To change the language setting for an existing content search, run the following command in Security &amp; Compliance Center PowerShell:</span></span>
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    <span data-ttu-id="83196-p156">例如，若要更改为中文语言设置，需要使用`zh-CN`区域性代码值。更改语言设置后，您将需要重新运行搜索。可能的区域性代码值的列表，请参阅[CultureInfo 类](https://go.microsoft.com/fwlink/p/?LinkID=184859)。内容搜索，我们建议您的语言设置; 的值使用两部分区域性代码例如， `ja-JP` ，而不`ja`。</span><span class="sxs-lookup"><span data-stu-id="83196-p156">For example, to change the language setting to Chinese, you would use  `zh-CN` for the culture code value. After you change the language setting, you'll have to re-run the search. For a list of possible culture code values, see [CultureInfo Class](https://go.microsoft.com/fwlink/p/?LinkID=184859). For content searches, we recommend that you use two-part culture codes for the value of the language setting; for example,  `ja-JP` and not  `ja`.</span></span>
    

  
 <span data-ttu-id="83196-402">**搜索的非活动邮箱**</span><span class="sxs-lookup"><span data-stu-id="83196-402">**Searching inactive mailboxes**</span></span>
  
<span data-ttu-id="83196-p157">如前面所述，您可以在内容搜索中搜索非活动邮箱。下面是要搜索非活动邮箱时，请记住的几个事项。</span><span class="sxs-lookup"><span data-stu-id="83196-p157">As previously stated, you can search inactive mailboxes in a content search. Here are a few things to keep in mind when searching inactive mailboxes.</span></span>
  
- <span data-ttu-id="83196-405">如果内容搜索包含用户邮箱，并且该邮箱由处于非活动状态，内容搜索将继续在它变为非活动状态后重新运行搜索时搜索非活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="83196-405">If a content search includes a user mailbox and that mailbox is then made inactive, the content search will continue to search the inactive mailbox when you re-run the search after it becomes inactive.</span></span>
    
- <span data-ttu-id="83196-p158">在某些情况下，用户可能有活动邮箱和非活动邮箱，具有相同的 SMTP 地址。在这种情况下，将搜索仅特定邮箱的选择作为内容搜索的位置。换句话说，如果您将用户邮箱添加到搜索，您不能假设，将搜索其活动和非活动邮箱;将搜索的明确添加到搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="83196-p158">In some cases, a user may have an active mailbox and an inactive mailbox that have the same SMTP address. In this case, only the specific mailbox that you select as a location for a content search will be searched. In other words, if you add a user's mailbox to a search, you can't assume that both their active and inactive mailboxes will be searched; only the mailbox that you explicitly add to the search will be searched.</span></span>
    
- <span data-ttu-id="83196-p159">我们强烈建议您避免使用活动邮箱和非活动邮箱具有相同的 SMTP 地址。如果您需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或非活动邮箱的内容还原到活动邮箱 （或活动邮箱的存档），然后删除非活动邮箱。有关详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="83196-p159">We strongly recommend that you avoid having an active mailbox and inactive mailbox with the same SMTP address. If you need to reuse the SMTP address that is currently assigned to an inactive mailbox, we recommend that you recover the inactive mailbox or restore the contents of an inactive mailbox to an active mailbox (or the archive of an active mailbox), and then delete the inactive mailbox. For more information, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="83196-412">恢复 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="83196-412">Recover an inactive mailbox in Office 365</span></span>](recover-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="83196-413">还原 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="83196-413">Restore an inactive mailbox in Office 365</span></span>](restore-an-inactive-mailbox.md)
    
  - [<span data-ttu-id="83196-414">删除 Office 365 中的非活动邮箱</span><span class="sxs-lookup"><span data-stu-id="83196-414">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)
    

  
 <span data-ttu-id="83196-415">**其他**</span><span class="sxs-lookup"><span data-stu-id="83196-415">**Miscellaneous**</span></span>
  
- <span data-ttu-id="83196-p160">内容在安全的**内容搜索**页上创建搜索&amp;合规性中心不会显示在**就地电子数据展示&amp;保留**Exchange 管理中心中的页。这是因为安全中创建的内容搜索体系结构和的搜索对象&amp;合规性中心是完全不同于 Exchange Online 中的就地电子数据展示功能。</span><span class="sxs-lookup"><span data-stu-id="83196-p160">Content searches created on the **Content search** page in the Security &amp; Compliance Center aren't displayed on the **In-Place eDiscovery &amp; Hold** page in the Exchange admin center. This is because the Content Search architecture and the search objects created in the Security &amp; Compliance Center are completely different than the In-Place eDiscovery feature in Exchange Online.</span></span> 
    
    <span data-ttu-id="83196-418">同样，搜索**内容的搜索**页上创建不会显示在**搜索**页上的安全中电子数据展示事例&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="83196-418">For the same reason, searches created on the **Content search** page aren't displayed on the **Searches** page of an eDiscovery case in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="83196-p161">重新启动和重新尝试搜索之间的区别是什么？重新启动搜索后，在搜索中指定的所有内容位置中新的预览搜索再次搜索。但是，您重试搜索，唯一的搜索上次运行时失败的内容的位置会搜索再次。</span><span class="sxs-lookup"><span data-stu-id="83196-p161">What is the difference between restarting and retrying a search? When you restart a search, all content locations that are specified in the search are searched again in a new preview search. However, when you retry a search, only the content locations that failed when the search was last run are searched again.</span></span>
   

