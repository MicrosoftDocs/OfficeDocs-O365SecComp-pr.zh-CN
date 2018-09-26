---
title: 克隆的内容搜索结果中的 Office 365 安全性&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 脚本能够快速克隆现有内容安全中搜索&amp;Compliane 中心搜索。当您克隆搜索时，新的搜索 （具有新的名称） 创建包含与原始搜索相同的属性。然后您可以编辑 （通过更改关键字查询或日期范围），新搜索，然后运行它。
ms.openlocfilehash: fd2ea0d8fa812d23e7479b664b13c786a62d5a38
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038045"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="8aeaf-105">克隆的内容搜索结果中的 Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="8aeaf-105">Clone a Content Search in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="8aeaf-p102">在 Office 365 安全性中创建内容搜索&amp;搜索大量邮箱或 SharePoint 的合规性中心和 OneDrive for Business 网站可能需要一段时间。指定要搜索的网站也可能是容易出错如果键入 URL。若要避免这些问题，您可以使用 Windows PowerShell 脚本本文中能够快速克隆现有内容搜索。当您克隆搜索时，新的搜索 （具有不同的名称） 创建包含与原始搜索相同属性 （如内容的位置和搜索查询）。然后您可以编辑新搜索 （通过更改关键字查询或日期范围），并运行它。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p102">Creating a Content Search in Office 365 Security &amp; Compliance Center that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile. Specifying the sites to search can also be prone to errors if you mistype a URL. To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search. When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search. Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="8aeaf-111">为什么克隆内容搜索？</span><span class="sxs-lookup"><span data-stu-id="8aeaf-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="8aeaf-112">若要比较结果的不同关键字搜索查询运行在相同的内容位置。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="8aeaf-113">保存您无需重新输入大量内容位置，当您创建一个新的搜索。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="8aeaf-114">以减小大小的搜索结果;例如，如果您有返回要导出结果太多的搜索，您可以克隆搜索，然后添加基于日期范围以减少的搜索结果的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="8aeaf-115">准备工作</span><span class="sxs-lookup"><span data-stu-id="8aeaf-115">Before you begin</span></span>

- <span data-ttu-id="8aeaf-116">您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行脚本本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-116">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="8aeaf-p103">该脚本包括最少的错误处理。脚本的主要用途是快速克隆内容的搜索。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p103">The script includes minimal error handling. The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="8aeaf-119">脚本创建一个新的内容搜索，但是无法启动它。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="8aeaf-p104">此脚本将考虑是否正在克隆内容搜索与电子数据展示事例相关联。如果搜索是与案例相关联，新的搜索还将与相同的大小写。如果现有搜索不与案例相关联，将安全中**内容的搜索**页面上列出的新搜索&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p104">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case. If the search is associated with a case, the new search will also be associated with the same case. If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the Security &amp; Compliance Center.</span></span> 
    
- <span data-ttu-id="8aeaf-p105">本主题中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p105">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="8aeaf-128">步骤 1： 运行脚本以克隆搜索</span><span class="sxs-lookup"><span data-stu-id="8aeaf-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="8aeaf-p106">此步骤中的脚本将创建一个新的内容搜索通过克隆现有。运行此脚本时，系统将提示您输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p106">The script in this step will create a new Content Search by cloning an existing one. When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="8aeaf-p107">**您的用户凭据**-脚本将使用您的凭据来连接到安全性&amp;使用 Windows PowerShell 为 Office 365 组织的合规性中心。如上文所述，您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p107">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center for your Office 365 organization with Windows PowerShell. As previously stated, you have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script.</span></span> 
    
- <span data-ttu-id="8aeaf-133">**现有搜索的名称**-这是您想要克隆的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="8aeaf-134">**将创建的新搜索条件的名称**-如果您保留此值为空，该脚本将创建基于您克隆搜索的名称的新搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="8aeaf-135">若要克隆搜索：</span><span class="sxs-lookup"><span data-stu-id="8aeaf-135">To clone a search:</span></span>
  
1. <span data-ttu-id="8aeaf-136">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `CloneSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
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
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
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

2. <span data-ttu-id="8aeaf-137">打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="8aeaf-138">运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="8aeaf-138">Run the script; for example:</span></span>
    
    ```
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="8aeaf-139">当提示输入凭据，输入您的电子邮件地址和密码，，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8aeaf-p108">输入以下信息脚本出现提示时。键入每条信息，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p108">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="8aeaf-142">现有搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="8aeaf-143">新搜索条件的名称。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-143">The name of the new search.</span></span>
    
    <span data-ttu-id="8aeaf-p109">脚本创建新的内容搜索，但是无法启动它。这样，您可以编辑并在下一步中运行搜索的机会。您可以查看新的搜索的属性，通过运行**Get ComplianceSearch** cmdlet 或转到安全的**内容搜索**或**电子数据展示**页&amp;合规性中心，具体取决于是否是新的搜索与案例相关联。</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p109">The script creates the new Content Search, but doesn't start it. This gives you a chance to edit and run the search in the next step. You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the Security &amp; Compliance Center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a><span data-ttu-id="8aeaf-147">步骤 2： 编辑和安全中运行的克隆的搜索&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="8aeaf-147">Step 2: Edit and run the cloned search in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="8aeaf-p110">您已运行脚本来克隆现有内容搜索后下, 一步是转到安全&amp;合规性中心以编辑和运行新的搜索。如上文所述，您可以编辑搜索通过更改查询关键字搜索并添加或删除搜索条件。有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="8aeaf-p110">After the you've run the script to clone an existing Content Search, the next step is to go to the Security &amp; Compliance Center to edit and run the new search. As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions. For more information, see:</span></span>
  
- [<span data-ttu-id="8aeaf-151">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="8aeaf-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="8aeaf-152">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="8aeaf-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="8aeaf-153">Office 365 安全性的电子数据展示事例&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="8aeaf-153">eDiscovery cases in the Office 365 Security &amp; Compliance Center</span></span>](ediscovery-cases.md)
