---
title: 在 Office 365 中搜索本地用户的基于云的邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用安全 & 合规中心中的内容搜索工具在 Exchange 混合部署中搜索和导出本地用户的 MicrosoftTeams 聊天数据 (称为1xN 聊天)。
ms.openlocfilehash: 0c68023fdd4e1c9e06596937247270861cdbd2b3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260994"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a><span data-ttu-id="ef135-103">在 Office 365 中搜索本地用户的基于云的邮箱</span><span class="sxs-lookup"><span data-stu-id="ef135-103">Searching cloud-based mailboxes for on-premises users in Office 365</span></span>

<span data-ttu-id="ef135-104">如果你的组织具有 Exchange 混合部署, 并且已启用 Microsoft 团队, 则用户可以使用团队聊天应用程序进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="ef135-104">If your organization has an Exchange hybrid deployment and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="ef135-105">对于基于云的用户, 团队聊天数据 (也称为1xN 聊天) 保存到其主要的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ef135-105">For the cloud-based user, the Teams chat data (also called 1xN chats) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="ef135-106">当本地用户使用团队聊天应用程序时, 其主邮箱位于本地。</span><span class="sxs-lookup"><span data-stu-id="ef135-106">When an on-premises user uses the Team chat application, their primary mailbox is located on-premises.</span></span> <span data-ttu-id="ef135-107">为了避免此限制, Microsoft 已发布了一个新功能, 其中创建了基于云的存储区域 (称为本地用户的基于云的邮箱), 以存储本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users.</span></span> <span data-ttu-id="ef135-108">这样, 您就可以使用安全 & 合规中心中的内容搜索工具搜索和导出本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-108">This lets you use the Content Search tool in the Security & Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ef135-109">以下是为本地用户设置和搜索基于云的邮箱的要求和限制:</span><span class="sxs-lookup"><span data-stu-id="ef135-109">Here are the requirements and limitation for setting up and to set up and search cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="ef135-110">您的本地目录服务 (如 Active directory) 中的用户帐户必须与 Azure Active directory (Office 365 中的目录服务) 同步。</span><span class="sxs-lookup"><span data-stu-id="ef135-110">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Office 365.</span></span> <span data-ttu-id="ef135-111">这意味着将在 Office 365 中创建一个邮件用户帐户, 并将其主邮箱位于内部部署组织中的用户关联。</span><span class="sxs-lookup"><span data-stu-id="ef135-111">This means that a mail user account is created in Office 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>
    
- <span data-ttu-id="ef135-112">本地用户的基于云的邮箱仅用于存储团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-112">The cloud-based mailbox for on-premises users is used only store Teams chat data.</span></span> <span data-ttu-id="ef135-113">本地用户无法以任何方式登录到基于云的邮箱或访问。</span><span class="sxs-lookup"><span data-stu-id="ef135-113">An on-premises user can't sign in to the cloud-based mailbox or access in any way.</span></span> <span data-ttu-id="ef135-114">它不能用于发送或接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ef135-114">It can't be used to send or receive email messages.</span></span> 
    
- <span data-ttu-id="ef135-115">您必须向 Microsoft 支持部门提交请求, 以使您的组织能够在基于云的邮箱中搜索团队对话数据, 以供本地用户使用。</span><span class="sxs-lookup"><span data-stu-id="ef135-115">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ef135-116">请参阅将[请求与 Microsoft 支持一起存档, 以在本文中启用此功能](#filing-a-request-with-microsoft-support-to-enable-this-feature)。</span><span class="sxs-lookup"><span data-stu-id="ef135-116">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span> 
    
 <span data-ttu-id="ef135-117">**注意:** 团队频道对话始终存储在与团队相关联的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="ef135-117">**Note:** Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="ef135-118">这意味着您可以使用内容搜索来搜索频道对话, 而无需将其作为支持请求的文件。</span><span class="sxs-lookup"><span data-stu-id="ef135-118">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="ef135-119">有关搜索团队频道对话的详细信息, 请参阅[搜索 Microsoft 团队和 Office 365 组](content-search.md#searching-microsoft-teams-and-office-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="ef135-119">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Office 365 Groups](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="ef135-120">运作方式</span><span class="sxs-lookup"><span data-stu-id="ef135-120">How it works</span></span>

<span data-ttu-id="ef135-121">如果启用了 microsoft 团队的用户具有本地邮箱, 并且其用户帐户/标识已同步到云, Microsoft 将创建一个基于云的邮箱来存储1xN 团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-121">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data.</span></span> <span data-ttu-id="ef135-122">在将团队聊天数据存储在基于云的邮箱中之后, 将为搜索编制索引。</span><span class="sxs-lookup"><span data-stu-id="ef135-122">After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search.</span></span> <span data-ttu-id="ef135-123">这样, 您就可以使用内容搜索 (和与电子数据展示事例关联的搜索) 来搜索、预览和导出本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-123">This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="ef135-124">您还可以使用\*\* \*\*\* Security & 合规性中心 PowerShell 中的 new-compliancesearch cmdlet 搜索本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-124">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ef135-125">下图显示了团队如何聊天本地用户数据的工作流, 以供搜索、预览和导出。</span><span class="sxs-lookup"><span data-stu-id="ef135-125">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft 团队中的本地用户的基于云的存储](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="ef135-127">除了这一新功能之外, 您仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft 团队关联的 exchange 邮箱中的 exchange 邮箱中搜索、预览和导出团队内容, 以及1xN 团队与 exchange Online 邮箱中的数据进行聊天。基于云的用户。</span><span class="sxs-lookup"><span data-stu-id="ef135-127">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="ef135-128">将请求与 Microsoft 支持一起存档以启用此功能</span><span class="sxs-lookup"><span data-stu-id="ef135-128">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="ef135-129">您必须将请求与 Microsoft 支持文件一起使用, 以使组织能够在安全 & 合规性中心中使用图形用户界面搜索本地用户的基于云的邮箱中的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-129">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ef135-130">请注意, 安全 & 合规中心 PowerShell 中提供了此功能。</span><span class="sxs-lookup"><span data-stu-id="ef135-130">Note that this feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="ef135-131">您无需提交支持请求即可使用 PowerShell 搜索本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-131">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="ef135-132">向 Microsoft 支持部门提交请求时, 请包含以下信息:</span><span class="sxs-lookup"><span data-stu-id="ef135-132">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="ef135-133">Office 365 组织的默认域名。</span><span class="sxs-lookup"><span data-stu-id="ef135-133">The default domain name of your Office 365 organization.</span></span>
    
- <span data-ttu-id="ef135-134">Office 365 组织的租户名称和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="ef135-134">The tenant name and tenant ID of your Office 365 organization.</span></span> <span data-ttu-id="ef135-135">您可以在 Azure Active Directory 门户中找到这些文件 (在 "**管理** \> **属性**" 下)。</span><span class="sxs-lookup"><span data-stu-id="ef135-135">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="ef135-136">请参阅[查找 Office 365 租户 ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="ef135-136">See [Find your Office 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>
    
- <span data-ttu-id="ef135-137">支持请求的用途的以下标题或说明: "启用本地用户的应用程序内容搜索"。</span><span class="sxs-lookup"><span data-stu-id="ef135-137">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="ef135-138">这将有助于将请求路由到将实现请求的 Office 365 电子数据展示工程团队。</span><span class="sxs-lookup"><span data-stu-id="ef135-138">This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span> 
    
<span data-ttu-id="ef135-139">在进行工程更改之后, Microsoft 支持将向您发送估计的部署日期。</span><span class="sxs-lookup"><span data-stu-id="ef135-139">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="ef135-140">请注意, 在提交支持请求后, 部署过程通常需要2-3 周。</span><span class="sxs-lookup"><span data-stu-id="ef135-140">Note that the deployment process usually takes 2-3 weeks after you submit the support request.</span></span> 
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="ef135-141">启用此功能后, 会发生什么？</span><span class="sxs-lookup"><span data-stu-id="ef135-141">What happens after this feature is enabled?</span></span>

<span data-ttu-id="ef135-142">在 Office 365 组织中部署此功能后, 将在内容搜索和与 Security & 合规中心中的电子数据展示事例相关的搜索中进行以下更改:</span><span class="sxs-lookup"><span data-stu-id="ef135-142">After this feature is deployed in your Office 365 organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="ef135-143">"为**本地用户添加 Office 应用内容**" 复选框将添加到内容搜索中的**位置**下。</span><span class="sxs-lookup"><span data-stu-id="ef135-143">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span> 
    
    !["为本地用户添加 Office 应用内容" 复选框已添加到内容搜索 UI](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="ef135-145">内部部署用户将显示在用于选择要搜索的用户邮箱的内容位置选取器中。</span><span class="sxs-lookup"><span data-stu-id="ef135-145">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span> 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="ef135-146">搜索团队在基于云的邮箱中为本地用户聊天内容</span><span class="sxs-lookup"><span data-stu-id="ef135-146">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="ef135-147">启用此功能后, 您可以使用安全 & 合规中心中的内容搜索来搜索团队对话中的用户的基于云的邮箱中的数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-147">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> 
  
1. <span data-ttu-id="ef135-148">在安全 & 合规性中心中, 转到 "**搜索** \> **内容搜索**"</span><span class="sxs-lookup"><span data-stu-id="ef135-148">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>
    
2. <span data-ttu-id="ef135-149">在 "**搜索**" 页上![, 单击](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) "添加图标" "**新建搜索**"。</span><span class="sxs-lookup"><span data-stu-id="ef135-149">On the **Search** page, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>
    
    <span data-ttu-id="ef135-150">如前所述, "为**本地用户添加 Office 应用内容**" 复选框将显示在 "**位置**" 下。</span><span class="sxs-lookup"><span data-stu-id="ef135-150">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="ef135-151">请注意, 默认情况下它处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="ef135-151">Note that it is selected by default.</span></span>
    
3. <span data-ttu-id="ef135-152">创建关键字查询, 并在必要时向搜索查询添加条件。</span><span class="sxs-lookup"><span data-stu-id="ef135-152">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="ef135-153">若要仅搜索工作组聊天数据, 您可以在 "**关键字**" 框中添加以下查询:</span><span class="sxs-lookup"><span data-stu-id="ef135-153">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span> 
    
    ```
    kind:im
    ``` 

4. <span data-ttu-id="ef135-154">此时, 您可以在 "**位置**" 下选择以下选项之一:</span><span class="sxs-lookup"><span data-stu-id="ef135-154">At this point, you can choose one of the following options under **Locations**:</span></span>
    
    - <span data-ttu-id="ef135-155">**所有位置**-选择此选项可搜索组织中所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-155">**All locations** - Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="ef135-156">选中此复选框后, 还将搜索本地用户的所有基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-156">When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span> 
    
    - <span data-ttu-id="ef135-157">**特定位置**-选择此选项, 然后单击 "**修改** \> ", 选择 "用户"、"组" 或 "团队" 以搜索特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-157">**Specific locations** - Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="ef135-158">如前所述, 位置选取器可让你搜索内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="ef135-158">As previously explained, the locations picker will let you search for on-premises users.</span></span> 
    
5. <span data-ttu-id="ef135-159">保存并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="ef135-159">Save and run the search.</span></span> <span data-ttu-id="ef135-160">从基于云的邮箱对本地用户的任何搜索结果都可以像在任何其他搜索结果中一样进行预览。</span><span class="sxs-lookup"><span data-stu-id="ef135-160">Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="ef135-161">此外, 还可以将搜索结果 (包括任何团队聊天数据) 导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="ef135-161">Additionally, you can you can export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="ef135-162">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="ef135-162">For more information, see:</span></span> 
    
    - [<span data-ttu-id="ef135-163">创建新的搜索</span><span class="sxs-lookup"><span data-stu-id="ef135-163">Create a new search</span></span>](content-search.md#create-a-new-search)
    
    - [<span data-ttu-id="ef135-164">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="ef135-164">Preview search results</span></span>](content-search.md#preview-search-results)
    
    - [<span data-ttu-id="ef135-165">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="ef135-165">Export Content Search results</span></span>](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="ef135-166">使用 PowerShell 搜索团队对话数据在基于云的邮箱中用于本地用户</span><span class="sxs-lookup"><span data-stu-id="ef135-166">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="ef135-167">您可以使用 Security & 合规性中心 PowerShell 中的**new-compliancesearch**和**new-compliancesearch** cmdlet 在基于云的邮箱中搜索本地用户。</span><span class="sxs-lookup"><span data-stu-id="ef135-167">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search the cloud-based mailbox for on-premises users.</span></span> <span data-ttu-id="ef135-168">如前所述, 您无需提交支持请求即可使用 PowerShell 搜索本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-168">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="ef135-169">[连接到安全 & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="ef135-169">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="ef135-170">运行以下 PowerShell 命令创建新的内容搜索内部部署用户的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-170">Run the following PowerShell command to create a new content searches the cloud-based mailboxes of on-premises users.</span></span>
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    <span data-ttu-id="ef135-171">*IncludeUserAppContent*参数用于为用户或由*ExchangeLocation*参数指定的用户指定基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-171">The  *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="ef135-172">*AllowNotFoundExchangeLocationsEnabled*允许本地用户的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-172">The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ef135-173">当您使用此`$true`参数的值时, 搜索在运行前不会尝试验证邮箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="ef135-173">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="ef135-174">为本地用户搜索基于云的邮箱时, 这是必需的, 因为这些类型的邮箱不会解析为常规邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-174">This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span> 
    
    <span data-ttu-id="ef135-175">下面的示例在基于云的 redstone Davis (Contoso 组织中的本地用户) 的邮箱中搜索包含关键字 "" 的团队聊天 (这是即时消息)。</span><span class="sxs-lookup"><span data-stu-id="ef135-175">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="ef135-176">在创建新的搜索后, 请务必使用**new-compliancesearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="ef135-176">After you create a new search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="ef135-177">有关使用这些 cmdlet 的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="ef135-177">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="ef135-178">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ef135-178">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [<span data-ttu-id="ef135-179">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ef135-179">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [<span data-ttu-id="ef135-180">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="ef135-180">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a><span data-ttu-id="ef135-181">已知问题</span><span class="sxs-lookup"><span data-stu-id="ef135-181">Known issues</span></span>

- <span data-ttu-id="ef135-182">目前, 您只能在基于云的邮箱中搜索、预览和导出本地用户的内容。</span><span class="sxs-lookup"><span data-stu-id="ef135-182">Currently, you can only search, preview, and export content in cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ef135-183">不支持在与电子数据展示案例关联的保留中为本地用户放置基于云的邮箱, 或将其分配给 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="ef135-183">Placing a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case or assigning it to an Office 365 retention policy is not supported.</span></span> 
    
- <span data-ttu-id="ef135-184">电子数据展示保留的内容位置选取器显示本地用户, 并允许您选择它们。</span><span class="sxs-lookup"><span data-stu-id="ef135-184">The content location picker for eDiscovery holds displays on-premises users and will let you select them.</span></span> <span data-ttu-id="ef135-185">但是, 如前面所述, 保留将不会应用于内部部署用户。</span><span class="sxs-lookup"><span data-stu-id="ef135-185">However, as previously explained the hold will not be applied to the on-premises user.</span></span>
    
## <a name="frequently-asked-questions"></a><span data-ttu-id="ef135-186">常见问题</span><span class="sxs-lookup"><span data-stu-id="ef135-186">Frequently asked questions</span></span>

 <span data-ttu-id="ef135-187">**本地用户的基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="ef135-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="ef135-188">将创建基于云的邮箱并将其存储在与 Office 365 组织相同的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="ef135-188">Cloud-based mailboxes are created and stored in the same datacenter as your Office 365 organization.</span></span> 
  
 <span data-ttu-id="ef135-189">**除了提交支持请求之外, 是否还有其他任何要求？**</span><span class="sxs-lookup"><span data-stu-id="ef135-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="ef135-190">如前所述, 具有本地邮箱的用户的标识必须同步到您的基于云的组织, 以便为 Office 365 中的每个本地用户帐户创建相应的邮件用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ef135-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="ef135-191">此外, 您的组织必须具有 office 365 企业版订阅, 例如 office 365 企业版 E1、E3 或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="ef135-191">Additionally, your organization must have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span> 
  
 <span data-ttu-id="ef135-192">**如果将用户的内部部署邮箱迁移到云, 是否有丢失团队聊天数据的风险？**</span><span class="sxs-lookup"><span data-stu-id="ef135-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="ef135-193">不可以。</span><span class="sxs-lookup"><span data-stu-id="ef135-193">No.</span></span> <span data-ttu-id="ef135-194">当您将本地用户的主邮箱迁移到云时, 该用户的团队聊天数据将迁移到其新的基于云的主邮箱。</span><span class="sxs-lookup"><span data-stu-id="ef135-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="ef135-195">**我可以将电子数据展示保留或 Office 365 保留策略应用于本地用户吗？**</span><span class="sxs-lookup"><span data-stu-id="ef135-195">**Can I apply an eDiscovery hold or Office 365 retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="ef135-196">不可以。</span><span class="sxs-lookup"><span data-stu-id="ef135-196">No.</span></span>
  
 <span data-ttu-id="ef135-197">**在我的组织提交请求以启用此功能之前, 内容搜索是否可以查找本地用户的较早的团队聊天？**</span><span class="sxs-lookup"><span data-stu-id="ef135-197">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="ef135-198">Microsoft 开始在2018年1月31日存储本地用户的团队聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ef135-198">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="ef135-199">因此, 如果在此日期之后, 本地团队用户的标识在 active directory 和 Azure active directory 之间进行了同步, 则其团队聊天数据将存储在基于云的邮箱中, 并将使用内容搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="ef135-199">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data will be stored in a cloud-based mailbox and will be searchable using Content Search.</span></span> <span data-ttu-id="ef135-200">Microsoft 还在为本地用户的基于云的邮箱中存储团队聊天数据 (从2018年1月31日到1月31日)。</span><span class="sxs-lookup"><span data-stu-id="ef135-200">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="ef135-201">有关此功能的详细信息即将推出。</span><span class="sxs-lookup"><span data-stu-id="ef135-201">More information about this will be available soon.</span></span>
