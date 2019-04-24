---
title: 克隆内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 脚本, 可以在 Office 365 或 Microsoft 365 中的合规性中心快速克隆现有的内容搜索。 当您克隆搜索时, 将创建一个新的搜索 (具有新的名称), 其中包含与原始搜索相同的属性。 然后, 您可以编辑新的搜索 (通过更改关键字查询或日期范围), 然后运行它。
ms.openlocfilehash: b08ccb6fbaf2dc9d92e0814fe9f92ea77c731147
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243343"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="96914-105">克隆内容搜索</span><span class="sxs-lookup"><span data-stu-id="96914-105">Clone a Content Search</span></span>

<span data-ttu-id="96914-106">在 Office 365 或 Microsoft 365 中的合规性中心内创建内容搜索, 以搜索大量邮箱或 SharePoint 和 OneDrive for business 网站可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="96914-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="96914-107">如果错误键入 URL, 则指定要搜索的网站也很容易出错。</span><span class="sxs-lookup"><span data-stu-id="96914-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="96914-108">若要避免这些问题, 您可以使用本文中的 Windows PowerShell 脚本快速克隆现有的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="96914-109">当您克隆搜索时, 会创建一个新的搜索 (名称不同), 其中包含与原始搜索相同的属性 (如内容位置和搜索查询)。</span><span class="sxs-lookup"><span data-stu-id="96914-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="96914-110">然后, 您可以编辑新的搜索 (通过更改关键字查询或日期范围) 并运行它。</span><span class="sxs-lookup"><span data-stu-id="96914-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="96914-111">为什么要克隆内容搜索？</span><span class="sxs-lookup"><span data-stu-id="96914-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="96914-112">比较不同关键字搜索查询的结果在相同的内容位置运行。</span><span class="sxs-lookup"><span data-stu-id="96914-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="96914-113">在创建新的搜索时, 不必重新输入大量的内容位置。</span><span class="sxs-lookup"><span data-stu-id="96914-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="96914-114">减小搜索结果的大小;例如, 如果您的搜索返回过多要导出的结果, 则可以克隆搜索, 然后根据日期范围添加搜索条件, 以减少搜索结果的数量。</span><span class="sxs-lookup"><span data-stu-id="96914-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="96914-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="96914-115">Before you begin</span></span>

- <span data-ttu-id="96914-116">您必须是 Security & 合规中心中的电子数据展示管理器角色组的成员, 才能运行本主题中所述的脚本。</span><span class="sxs-lookup"><span data-stu-id="96914-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="96914-117">该脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="96914-117">The script includes minimal error handling.</span></span> <span data-ttu-id="96914-118">脚本的主要用途是快速克隆内容搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="96914-119">该脚本会创建新的内容搜索, 但不会启动它。</span><span class="sxs-lookup"><span data-stu-id="96914-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="96914-120">此脚本将考虑您要克隆的内容搜索是否与电子数据展示事例相关联。</span><span class="sxs-lookup"><span data-stu-id="96914-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="96914-121">如果搜索与某一事例相关联, 则新的搜索也将与同一事例相关联。</span><span class="sxs-lookup"><span data-stu-id="96914-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="96914-122">如果现有搜索不与事例相关联, 则新搜索将在合规性中心的**内容搜索**页中列出。</span><span class="sxs-lookup"><span data-stu-id="96914-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="96914-123">在任何 Microsoft standard 支持计划或服务下, 本主题中提供的示例脚本不受支持。</span><span class="sxs-lookup"><span data-stu-id="96914-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="96914-124">示例脚本按原样提供, 而不提供任何种类的担保。</span><span class="sxs-lookup"><span data-stu-id="96914-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="96914-125">Microsoft 也不提供任何默示担保，包括但不仅限于对适销性或针对特定目的的适用性的默示担保。</span><span class="sxs-lookup"><span data-stu-id="96914-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="96914-126">因使用或性能示例脚本和文档而导致的全部风险都将保留给您。</span><span class="sxs-lookup"><span data-stu-id="96914-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="96914-127">对于因使用或无法使用示例脚本或文档产生的任何损害（包括但不仅限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者以及参与脚本创建、生成或交付的任何人均不承担任何责任，即使 Microsoft 已被告知此类损害的可能性也是如此。</span><span class="sxs-lookup"><span data-stu-id="96914-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="96914-128">步骤 1: 运行脚本以克隆搜索</span><span class="sxs-lookup"><span data-stu-id="96914-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="96914-129">此步骤中的脚本将通过克隆现有内容搜索来创建新的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="96914-130">运行此脚本时, 系统将提示您输入以下信息:</span><span class="sxs-lookup"><span data-stu-id="96914-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="96914-131">**你的用户凭据**-脚本将使用你的凭据连接到使用 Windows PowerShell 的 Office 365 组织的安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="96914-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="96914-132">如前所述, 您必须是 Security & compCompliance Center 中的 "电子数据展示管理器" 角色组的成员才能运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="96914-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="96914-133">**现有搜索的名称**-这是要克隆的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="96914-134">**将创建的新搜索的名称**-如果将此值保留为空, 则脚本将为新搜索创建一个名称, 该名称基于您要克隆的搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="96914-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="96914-135">若要克隆搜索, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="96914-135">To clone a search:</span></span>
  
1. <span data-ttu-id="96914-136">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="96914-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="96914-137">打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="96914-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="96914-138">运行脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="96914-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="96914-139">当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="96914-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="96914-140">当脚本提示时, 请输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="96914-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="96914-141">键入每条信息, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="96914-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="96914-142">现有搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="96914-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="96914-143">新搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="96914-143">The name of the new search.</span></span>
    
    <span data-ttu-id="96914-144">该脚本会创建新的内容搜索, 但不会启动它。</span><span class="sxs-lookup"><span data-stu-id="96914-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="96914-145">这使您有机会在下一步中编辑和运行搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="96914-146">您可以通过运行**new-compliancesearch** cmdlet 或转到合规中心中的**内容搜索**或**电子数据展示**页来查看新搜索的属性, 具体取决于新搜索是否与案例相关联。</span><span class="sxs-lookup"><span data-stu-id="96914-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="96914-147">步骤 2: 在合规中心中编辑和运行克隆的搜索</span><span class="sxs-lookup"><span data-stu-id="96914-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="96914-148">在运行脚本以克隆现有内容搜索之后, 下一步是转到 "合规中心" 以编辑并运行新的搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="96914-149">如前所述, 可以通过更改关键字搜索查询和添加或删除搜索条件来编辑搜索。</span><span class="sxs-lookup"><span data-stu-id="96914-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="96914-150">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="96914-150">For more information, see:</span></span>
  
- [<span data-ttu-id="96914-151">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="96914-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="96914-152">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="96914-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="96914-153">电子数据展示事例</span><span class="sxs-lookup"><span data-stu-id="96914-153">eDiscovery cases</span></span>](ediscovery-cases.md)
