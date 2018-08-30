---
title: 在 Office 365 中搜索内部部署用户的基于云的邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Office 365 安全性中的内容搜索工具&amp;合规性中心搜索和导出 Exchange 混合部署中的内部部署用户 MicrosoftTeams 聊天数据 （称为 1xN 聊天）。
ms.openlocfilehash: a504dfcf4c82bec036137b90312c01a0b2326ccc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525213"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="c1abc-103">在 Office 365 中搜索内部部署用户的基于云的邮箱</span><span class="sxs-lookup"><span data-stu-id="c1abc-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="c1abc-p101">如果您的组织具有 Exchange 混合部署，并且已启用的 Microsoft 团队，用户可以使用团队聊天应用程序的即时消息。对于基于云的用户，（也称为 1xN 聊天） 团队聊天数据保存到其主的基于云的邮箱。内部部署用户使用的工作组聊天应用程序，其主邮箱时位于内部部署。若要解决此限制，Microsoft 已发布在其中创建 （称为内部部署用户的基于云的邮箱） 的基于云的存储区存储团队的内部部署用户的聊天数据的新功能。这使您可以在 Office 365 安全性使用内容搜索工具&amp;合规性中心搜索和导出团队需要内部部署用户的聊天数据。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p101">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging. For the cloud-based user, the Teams chat data (also called 1xN chats) is saved to their primary cloud-based mailbox. When an on-premises user uses the Team chat application, their primary mailbox is located on-premises. To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users. This lets you use the Content Search tool in the Office 365 Security &amp; Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="c1abc-109">下面是要求和限制的设置，并可设置和搜索内部部署用户的基于云的邮箱：</span><span class="sxs-lookup"><span data-stu-id="c1abc-109">Here are the requirements and limitation for setting up and to set up and search cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="c1abc-p102">必须与 Azure Active Directory 的 Office 365 中的目录服务同步您的本地目录服务 （如 Active Directory) 中的用户帐户。也就是说，邮件用户帐户在 Office 365 中创建并且与主邮箱位于内部部署组织中的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p102">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365. This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>
    
- <span data-ttu-id="c1abc-p103">内部部署用户的基于云的邮箱使用的唯一存储团队聊天数据。内部部署用户不能登录到基于云的邮箱，或者访问以任何方式。它不能用于发送或接收的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p103">The cloud-based mailbox for on-premises users is used only store Teams chat data. An on-premises user can't sign in to the cloud-based mailbox or access in any way. It can't be used to send or receive email messages.</span></span> 
    
- <span data-ttu-id="c1abc-p104">您必须提交到 Microsoft 支持的请求，以让您的组织搜索团队聊天数据在内部部署用户的基于云的邮箱中。请参阅[归档与 Microsoft 支持的请求，若要启用此功能的安全&amp;合规性中心](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center)本文中。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p104">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users. See [Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center) in this article.</span></span> 
    
 <span data-ttu-id="c1abc-p105">**注意：** 团队通道对话始终存储在与团队相关联的基于云的邮箱。这意味着您可以使用内容搜索来搜索通道对话缺少具有文件支持请求。有关搜索团队频道对话，请参阅[搜索 Microsoft 团队和 Office 365 组](content-search.md#searching-microsoft-teams-and-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p105">**Note:** Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team. That means you can use Content Search to search channel conversations without have to file a support request. For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="c1abc-120">如何工作</span><span class="sxs-lookup"><span data-stu-id="c1abc-120">How it works</span></span>

<span data-ttu-id="c1abc-p106">如果 Microsoft 团队启用用户具有内部部署邮箱且其用户帐户/标识包含已同步到云，Microsoft 将创建基于云的邮箱存储 1xN 团队聊天数据。团队聊天数据存储在基于云的邮箱后，会将其编制索引的搜索。使您能够使用内容搜索 （和电子数据展示事例相关联的搜索） 要搜索预览，并将内部部署用户的团队聊天数据导出。您还可以使用**\*ComplianceSearch** Office 365 安全性 cmdlet&amp;合规性中心 PowerShell，可以搜索团队的内部部署用户的聊天数据。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p106">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data. After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search. This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users. You can also use **\*ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="c1abc-125">下图显示了如何团队聊天内部部署用户的数据的工作流是可用于搜索、 预览和导出。</span><span class="sxs-lookup"><span data-stu-id="c1abc-125">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![内部部署中的用户的 Microsoft 团队的基于云的存储](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="c1abc-127">除了这项新功能，您仍可用内容搜索来搜索、 预览和导出的基于云的 SharePoint 网站和 Exchange 邮箱中的内容与每个 Microsoft 团队和 1xN 团队中的 Exchange Online 邮箱的聊天数据相关联的团队基于云的用户。</span><span class="sxs-lookup"><span data-stu-id="c1abc-127">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a><span data-ttu-id="c1abc-128">存档与 Microsoft 支持的请求，若要启用此功能的安全&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="c1abc-128">Filing a request with Microsoft Support to enable this feature in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="c1abc-p107">您必须文件与 Microsoft 支持的请求，以让您的组织使用安全中的图形用户界面&amp;合规性中心搜索团队聊天数据在内部部署用户的基于云的邮箱。请注意，此功能都在 Office 365 安全性&amp;合规性中心 PowerShell。您无需提交支持请求以使用 PowerShell 搜索的内部部署用户的工作组聊天数据。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p107">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users. Note that this feature is available in Office 365 Security &amp; Compliance Center PowerShell. You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="c1abc-132">提交到 Microsoft 支持的请求时，包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="c1abc-132">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="c1abc-133">Office 365 组织默认域名。</span><span class="sxs-lookup"><span data-stu-id="c1abc-133">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="c1abc-p108">租户名称和 Office 365 组织的租户 ID。您可以找到这些 Azure Active Directory 门户中 (在**管理**下\>**属性**)。请参阅[查找您的 Office 365 租户 ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p108">The tenant name and tenant ID of your Office 365 organization. You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**). See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="c1abc-p109">下面的标题或支持请求的用途的说明:"启用应用程序内容搜索内部部署用户"。这有助于将请求路由到 Office 365 电子数据展示工程团队将实现请求。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p109">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="c1abc-p110">工程设计更改后，Microsoft 支持将向您发送估计的部署日期。请注意，部署过程，通常采用 2 到 3 周后提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p110">After the engineering change is made, Microsoft Support will send you an estimated deployment date. Note that the deployment process usually takes 2-3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="c1abc-141">启用此功能后，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="c1abc-141">What happens after this feature is enabled?</span></span>

<span data-ttu-id="c1abc-142">此功能 Office 365 组织中部署后，以下更改在内容搜索进行以及相关联的电子数据展示搜索中 case 安全中&amp;合规性中心：</span><span class="sxs-lookup"><span data-stu-id="c1abc-142">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security &amp; Compliance Center:</span></span>
  
- <span data-ttu-id="c1abc-143">**本地用户添加 Office 应用程序内容**复选框将添加下内容搜索中的**位置**。</span><span class="sxs-lookup"><span data-stu-id="c1abc-143">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    !["添加内部部署用户的 Office 应用程序内容"复选框添加到内容搜索 UI](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="c1abc-145">用于选择要搜索的用户邮箱的内容位置选取器中显示内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="c1abc-145">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="c1abc-146">搜索内部部署用户的基于云的邮箱中内容的团队聊天</span><span class="sxs-lookup"><span data-stu-id="c1abc-146">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="c1abc-147">在启用该功能后，可以使用在安全的内容搜索&amp;合规性中心搜索团队聊天数据在内部部署用户的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-147">After the feature has been enabled, you can use Content Search in the Security &amp; Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="c1abc-148">安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **内容搜索**</span><span class="sxs-lookup"><span data-stu-id="c1abc-148">In the Security &amp; Compliance Center, go to **Search &amp; investigation** \> **Content search**</span></span>
    
2. <span data-ttu-id="c1abc-149">在**搜索**页上单击![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜索**。</span><span class="sxs-lookup"><span data-stu-id="c1abc-149">On the **Search** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="c1abc-p111">如前所述，**位置**下显示**添加 Office 应用程序内容的内部部署用户**复选框。请注意，它默认选中状态。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p111">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**. Note that it is selected by default.</span></span>
    
3. <span data-ttu-id="c1abc-p112">创建关键字查询并根据需要向搜索查询添加条件。仅搜索团队聊天数据，您可以在**关键字**框中添加以下查询：</span><span class="sxs-lookup"><span data-stu-id="c1abc-p112">Create the keyword query and add conditions to the search query if necessary. To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 
    
    ```
    kind:im
    ``` 

4. <span data-ttu-id="c1abc-154">此时，您可以选择**位置**下的以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="c1abc-154">At this point, you can choose one of the following options under **Locations**:</span></span>
    
    - <span data-ttu-id="c1abc-p113">**所有位置**-选择此选项可搜索您的组织中的所有用户邮箱。选中此复选框后，还将搜索内部部署用户的所有基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p113">**All locations** - Select this option to search the mailboxes of all users in your organization. When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 
    
    - <span data-ttu-id="c1abc-p114">**特定位置**-选择此选项，然后单击**修改**\>选择用户、 组或团队，搜索特定邮箱。如前所述，位置选取器会让您搜索内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p114">**Specific locations** - Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes. As previously explained, the locations picker will let you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="c1abc-p115">保存并运行搜索。可以与任何其他搜索结果一样预览任何搜索结果从内部部署用户的基于云的邮箱。此外，您可以您可以将 （包括任何团队聊天数据） 的搜索结果导出到 PST 文件。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1abc-p115">Save and run the search. Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results. Additionally, you can you can export the search results (including any Teams chat data) to a PST file. For more information, see:</span></span> 
    
    - [<span data-ttu-id="c1abc-163">创建新的搜索</span><span class="sxs-lookup"><span data-stu-id="c1abc-163">Create a new search</span></span>](content-search.md#create-a-new-search)
    
    - [<span data-ttu-id="c1abc-164">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="c1abc-164">Preview search results</span></span>](content-search.md#preview-search-results)
    
    - [<span data-ttu-id="c1abc-165">从 Office 365 安全性导出内容的搜索结果&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="c1abc-165">Export Content Search results from the Office 365 Security &amp; Compliance Center</span></span>](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="c1abc-166">使用 PowerShell 搜索团队聊天数据在内部部署用户的基于云的邮箱</span><span class="sxs-lookup"><span data-stu-id="c1abc-166">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="c1abc-p116">您可以在 Office 365 安全性使用**新建 ComplianceSearch**和**设置 ComplianceSearch** cmdlet&amp;合规性中心 PowerShell 搜索内部部署用户的基于云的邮箱。如前所述，您无需提交支持请求以使用 PowerShell 搜索的内部部署用户的工作组聊天数据。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p116">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Office 365 Security &amp; Compliance Center PowerShell to search the cloud-based mailbox for on-premises users. As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="c1abc-169">[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c1abc-169">[Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="c1abc-170">运行以下 PowerShell 命令以创建新的内容搜索内部部署用户的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-170">Run the following PowerShell command to create a new content searches the cloud-based mailboxes of on-premises users.</span></span>
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    <span data-ttu-id="c1abc-p117">*IncludeUserAppContent*参数用于指定用户或由*ExchangeLocation*参数指定用户的基于云的邮箱。*AllowNotFoundExchangeLocationsEnabled*允许的内部部署用户的基于云的邮箱。当您使用`$true`此参数，搜索值不尝试运行之前验证邮箱是否存在。这是必需的因为这些类型的邮箱不解析为正则邮箱搜索内部部署用户的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p117">The  *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter. The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users. When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs. This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 
    
    <span data-ttu-id="c1abc-175">下面的示例搜索聊天 （即即时消息） 包含关键字"redstone"的基于云的邮箱中的 Sara Davis，属于 Contoso 组织中的内部部署用户的团队。</span><span class="sxs-lookup"><span data-stu-id="c1abc-175">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="c1abc-176">创建新的搜索后，请务必使用**开始 ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="c1abc-176">After you create a new search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="c1abc-177">使用这些 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1abc-177">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="c1abc-178">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="c1abc-178">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [<span data-ttu-id="c1abc-179">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="c1abc-179">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [<span data-ttu-id="c1abc-180">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="c1abc-180">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a><span data-ttu-id="c1abc-181">已知问题</span><span class="sxs-lookup"><span data-stu-id="c1abc-181">Known issues</span></span>

- <span data-ttu-id="c1abc-p118">目前，您还可以仅搜索、 预览和导出内容的基于云的邮箱中的本地用户。发出的内部部署用户的基于云的邮箱保留与电子数据展示案例或将其分配给 Office 365 保留策略不支持。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p118">Currently, you can only search, preview, and export content in cloud-based mailboxes for on-premises users. Placing a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case or assigning it to an Office 365 retention policy is not supported.</span></span> 
    
- <span data-ttu-id="c1abc-p119">电子数据展示内容位置选取器包含显示在本地用户，并且会让您选择它们。但是，如上文所述保留不会应用到内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p119">The content location picker for eDiscovery holds displays on-premises users and will let you select them. However, as previously explained the hold will not be applied to the on-premises user.</span></span>
    
## <a name="frequently-asked-questions"></a><span data-ttu-id="c1abc-186">常见问题</span><span class="sxs-lookup"><span data-stu-id="c1abc-186">Frequently asked questions</span></span>

 <span data-ttu-id="c1abc-187">**内部部署用户的基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="c1abc-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="c1abc-188">创建和存储在 Office 365 组织相同的数据中心中的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="c1abc-189">**是否有提交支持请求之外的任何其他要求？**</span><span class="sxs-lookup"><span data-stu-id="c1abc-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="c1abc-p120">如前所述，必须进行具有 prem 上邮箱的用户的身份同步到基于云的组织，以便为 Office 365 中每个内部部署用户帐户创建相应的邮件用户帐户。此外，您的组织必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、 E3 或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p120">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365. Additionally, your organization must have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="c1abc-192">**是否存在丢失团队聊天数据，如果用户的内部部署邮箱迁移到云中的风险？**</span><span class="sxs-lookup"><span data-stu-id="c1abc-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="c1abc-p121">不。内部部署用户的主邮箱迁移到云中时，该用户的工作组聊天数据将迁移到其新的基于云的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p121">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="c1abc-195">**可以将应用电子数据展示保留或 Office 365 保留策略到内部部署用户？**</span><span class="sxs-lookup"><span data-stu-id="c1abc-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="c1abc-196">不能。</span><span class="sxs-lookup"><span data-stu-id="c1abc-196">No.</span></span>
  
 <span data-ttu-id="c1abc-197">**内容搜索查找旧团队聊天的内部部署用户的时间之前我的组织可以提交请求以启用此功能？**</span><span class="sxs-lookup"><span data-stu-id="c1abc-197">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="c1abc-p122">Microsoft 启动上 2018 年 1 月 31，存储在本地用户的工作组聊天数据。因此，如果此日期后，在本地团队用户的标识具有 Active Directory 和 Azure Active Directory 之间同步，然后其团队聊天数据将存储在基于云的邮箱，将可搜索使用内容搜索。Microsoft 正在在内部部署用户的基于云的邮箱中存储从之前 2018 年 1 月 31，团队聊天数据。很快就会提供相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1abc-p122">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data will be stored in a cloud-based mailbox and will be searchable using Content Search. Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users. More information about this will be available soon.</span></span>
