---
title: 创建、报告和删除多个内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何通过 Office 365 安全&amp;合规中心中的 PowerShell 脚本来自动执行内容搜索任务, 如创建搜索和运行报告。
ms.openlocfilehash: 740f3384e5d4f26e09512cc846ad8779bcbc31ef
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670657"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="ca15d-103">创建、报告和删除多个内容搜索</span><span class="sxs-lookup"><span data-stu-id="ca15d-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="ca15d-104">当你尝试了解基础数据以及搜索的丰富程度和质量时, 快速创建和报告发现搜索通常是电子数据展示和调查中的重要步骤。</span><span class="sxs-lookup"><span data-stu-id="ca15d-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="ca15d-105">为帮助你执行此操作, 安全&amp;合规性中心提供了一组 Windows PowerShell cmdlet, 以自动执行耗时的内容搜索任务。</span><span class="sxs-lookup"><span data-stu-id="ca15d-105">To help you do this, the Security &amp; Compliance Center offers a set of Windows PowerShell cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="ca15d-106">这些脚本提供了创建大量搜索的快速、简便的方法, 然后运行估计的搜索结果报告, 这些报告可帮助您确定所讨论的数据量。</span><span class="sxs-lookup"><span data-stu-id="ca15d-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="ca15d-107">您还可以使用脚本来创建不同版本的搜索, 以比较每个搜索结果所产生的结果。</span><span class="sxs-lookup"><span data-stu-id="ca15d-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="ca15d-108">这些脚本可帮助您快速高效地识别和挑选数据。</span><span class="sxs-lookup"><span data-stu-id="ca15d-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ca15d-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="ca15d-109">Before you begin</span></span>

- <span data-ttu-id="ca15d-110">您必须是安全&amp;合规中心中的电子数据展示管理器角色组的成员, 才能运行本主题中所述的脚本。</span><span class="sxs-lookup"><span data-stu-id="ca15d-110">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="ca15d-111">若要收集组织中可添加到 CSV 文件的 onedrive for business 网站的 url 列表, 请参阅在[组织中创建所有 OneDrive 位置的列表](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="ca15d-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="ca15d-112">请务必将您在本主题中创建的所有文件保存到同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="ca15d-113">这将使运行脚本变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="ca15d-113">That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="ca15d-114">这些脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="ca15d-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="ca15d-115">其主要目的是快速创建、报告和删除多个内容搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="ca15d-p104">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="ca15d-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="ca15d-121">步骤 1: 创建包含有关要运行的搜索的信息的 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="ca15d-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="ca15d-122">在此步骤中创建的逗号分隔值 (CSV) 文件中, 每个要搜索的用户都包含一行。</span><span class="sxs-lookup"><span data-stu-id="ca15d-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="ca15d-123">您可以搜索用户的 Exchange Online 邮箱 (包括存档邮箱 (如果已启用) 和 OneDrive for business 网站。</span><span class="sxs-lookup"><span data-stu-id="ca15d-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="ca15d-124">或者, 您可以仅搜索邮箱或 OneDrive for business 网站。</span><span class="sxs-lookup"><span data-stu-id="ca15d-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="ca15d-125">您还可以在 SharePoint Online 组织中搜索任何网站。</span><span class="sxs-lookup"><span data-stu-id="ca15d-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="ca15d-126">您在步骤3中运行的脚本将为 CSV 文件中的每一行创建单独的搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="ca15d-127">使用记事本将以下文本复制并粘贴到一个 .txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="ca15d-128">将此文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="ca15d-129">此外, 还会将其他脚本保存到此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-129">You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="ca15d-130">文件的第一行 (即标题行) 列出将由**new-compliancesearch** cmdlet 使用的参数 (在步骤3的脚本中) 以创建新的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="ca15d-131">每个参数名称都用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="ca15d-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="ca15d-132">请确保标题行中没有任何空格。</span><span class="sxs-lookup"><span data-stu-id="ca15d-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="ca15d-133">标题行下的每一行表示每个搜索的参数值。</span><span class="sxs-lookup"><span data-stu-id="ca15d-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="ca15d-134">请务必将 CSV 文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="ca15d-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="ca15d-135">在 Excel 中打开 .txt 文件, 然后使用下表中的信息编辑包含每个搜索的信息的文件。</span><span class="sxs-lookup"><span data-stu-id="ca15d-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="ca15d-136">**参数**</span><span class="sxs-lookup"><span data-stu-id="ca15d-136">**Parameter**</span></span>|<span data-ttu-id="ca15d-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="ca15d-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="ca15d-138">用户邮箱的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="ca15d-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="ca15d-139">用户的 OneDrive for business 网站的 url 或组织中任何网站的 url。</span><span class="sxs-lookup"><span data-stu-id="ca15d-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="ca15d-140">对于 OneDrive for business 网站的 URL, 请使用以下格式: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。</span><span class="sxs-lookup"><span data-stu-id="ca15d-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="ca15d-141">例如，  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>  <br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="ca15d-142">搜索的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="ca15d-142">The search query for the search.</span></span> <span data-ttu-id="ca15d-143">有关创建搜索查询的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="ca15d-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>  <br/> |
    | `StartDate` <br/> |<span data-ttu-id="ca15d-144">对于电子邮件, 收件人接收或发送邮件的日期或发件人发送邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="ca15d-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="ca15d-145">对于 SharePoint 或 OneDrive for business 网站上的文档, 上次修改文档的日期或文档之后的日期。</span><span class="sxs-lookup"><span data-stu-id="ca15d-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="ca15d-146">对于电子邮件, 由用户发送的邮件发送的日期或之前的日期。</span><span class="sxs-lookup"><span data-stu-id="ca15d-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="ca15d-147">对于 SharePoint 或 OneDrive for business 网站上的文档, 上次修改文档的日期或之前的日期。</span><span class="sxs-lookup"><span data-stu-id="ca15d-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="ca15d-148">将 Excel 文件作为 CSV 文件保存到本地计算机上的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="ca15d-149">您在步骤3中创建的脚本将使用此 CSV 文件中的信息来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="ca15d-150">步骤 2: 连接到安全 & 合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca15d-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="ca15d-151">下一步是将 Windows PowerShell 连接到组织的&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="ca15d-151">The next step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="ca15d-152">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-152">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> <span data-ttu-id="ca15d-153">将文件保存到在步骤1中保存 CSV 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca15d-153">Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="ca15d-154">在本地计算机上, 打开 Windows PowerShell, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="ca15d-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="ca15d-155">步骤 3: 运行脚本以创建并启动搜索</span><span class="sxs-lookup"><span data-stu-id="ca15d-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="ca15d-156">此步骤中的脚本将为您在步骤1中创建的 CSV 文件中的每一行创建单独的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-156">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="ca15d-157">运行此脚本时, 系统将提示您输入两个值:</span><span class="sxs-lookup"><span data-stu-id="ca15d-157">When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="ca15d-158">**搜索组 ID** -此名称提供了一种简单的方法来组织从 CSV 文件创建的搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-158">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="ca15d-159">创建的每个搜索都使用搜索组 ID 命名, 然后将数字追加到搜索名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-159">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="ca15d-160">例如, 如果您为搜索组 ID 输入**ContosoCase** , 则会将搜索命名为**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**等等。</span><span class="sxs-lookup"><span data-stu-id="ca15d-160">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="ca15d-161">请注意, 键入的名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ca15d-161">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="ca15d-162">在第4步和第5步中使用搜索组 ID 时, 必须使用与创建时相同的大小写。</span><span class="sxs-lookup"><span data-stu-id="ca15d-162">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="ca15d-163">**csv 文件**-您在步骤1中创建的 CSV 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-163">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="ca15d-164">确保包含使用完整文件名, 包括 .csv 文件扩展名;例如, `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-164">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="ca15d-165">若要运行该脚本，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ca15d-165">To run the script:</span></span>

1. <span data-ttu-id="ca15d-166">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `CreateSearches.ps1`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-166">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="ca15d-167">将文件保存到保存其他文件的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-167">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. <span data-ttu-id="ca15d-168">在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="ca15d-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="ca15d-169">在**搜索组 ID**提示符处, 键入搜索组名称, 然后按**enter**键;例如, `ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-169">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="ca15d-170">请注意, 此名称区分大小写, 因此必须在后续步骤中以相同的方式键入此名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-170">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="ca15d-171">在**源 CSV 文件**提示符处, 键入 csv 文件的名称, 包括 .csv 文件扩展名;例如, `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="ca15d-172">按**enter**以继续运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="ca15d-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="ca15d-173">该脚本将显示创建和运行搜索的进度。</span><span class="sxs-lookup"><span data-stu-id="ca15d-173">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="ca15d-174">脚本完成后, 将返回到提示窗口。</span><span class="sxs-lookup"><span data-stu-id="ca15d-174">When the script is complete, it returns to the prompt.</span></span> 
    
    ![运行该脚本以创建多个合规性搜索的示例输出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="ca15d-176">步骤 4: 运行脚本以报告搜索估计值</span><span class="sxs-lookup"><span data-stu-id="ca15d-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="ca15d-177">创建搜索后, 下一步是运行一个脚本, 该脚本显示在步骤3中创建的每个搜索的搜索命中次数的简单报告。</span><span class="sxs-lookup"><span data-stu-id="ca15d-177">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="ca15d-178">该报告还包括每个搜索的结果大小, 以及所有搜索的总点击数和总大小。</span><span class="sxs-lookup"><span data-stu-id="ca15d-178">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="ca15d-179">运行报告脚本时, 系统会提示输入搜索组 ID, 如果您想要将报告保存到 csv 文件中, 则会提示您输入 csv 文件名。</span><span class="sxs-lookup"><span data-stu-id="ca15d-179">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="ca15d-180">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `SearchReport.ps1`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-180">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="ca15d-181">将文件保存到保存其他文件的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-181">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. <span data-ttu-id="ca15d-182">在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="ca15d-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="ca15d-183">在**搜索组 ID**提示符处, 键入搜索组名称, 然后按**enter**键;例如`ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-183">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="ca15d-184">请注意, 此名称区分大小写, 因此您必须按照在第3步中运行脚本时的相同方式键入此名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-184">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="ca15d-185">如果要将报告保存**到 csv 文件 (保留为空以显示报告)** 提示符, 请在要将报告保存到 csv 文件中时, 键入完整文件名 path (包括 .csv 文件扩展名) 的文件名。</span><span class="sxs-lookup"><span data-stu-id="ca15d-185">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="ca15d-186">csv 文件的名称, 包括 .csv 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="ca15d-186">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="ca15d-187">例如, 可以键入`ContosoCaseReport.csv`将其保存到当前目录中, 也可以键入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`以将其保存到其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca15d-187">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="ca15d-188">您也可以将提示留空以显示报告, 但不将其保存到文件中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-188">You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="ca15d-189">按 Enter\*\*\*\* 键。</span><span class="sxs-lookup"><span data-stu-id="ca15d-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="ca15d-190">该脚本将显示创建和运行搜索的进度。</span><span class="sxs-lookup"><span data-stu-id="ca15d-190">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="ca15d-191">脚本完成后, 将显示报告。</span><span class="sxs-lookup"><span data-stu-id="ca15d-191">When the script is complete, the report is displayed.</span></span> 
    
    ![运行搜索报告以显示对搜索组的估计](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="ca15d-193">如果在搜索组中的多个搜索中将相同的邮箱或网站指定为内容位置, 则在报告中估计的总结果 (对于项目数和总大小) 可能包含相同项目的结果。</span><span class="sxs-lookup"><span data-stu-id="ca15d-193">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="ca15d-194">这是因为, 如果与搜索组中的不同搜索的查询相匹配, 则相同的电子邮件或文档将被多次计数。</span><span class="sxs-lookup"><span data-stu-id="ca15d-194">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="ca15d-195">步骤 5: 运行脚本以删除搜索</span><span class="sxs-lookup"><span data-stu-id="ca15d-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="ca15d-196">由于您可能要创建大量搜索, 因此此最后的脚本可以轻松地快速删除在步骤3中创建的搜索。</span><span class="sxs-lookup"><span data-stu-id="ca15d-196">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="ca15d-197">与其他脚本一样, 这也会提示您输入搜索组 ID。</span><span class="sxs-lookup"><span data-stu-id="ca15d-197">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="ca15d-198">运行此脚本时, 搜索名称中包含搜索组 ID 的所有搜索都将被删除。</span><span class="sxs-lookup"><span data-stu-id="ca15d-198">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="ca15d-199">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `DeleteSearches.ps1`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-199">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="ca15d-200">将文件保存到保存其他文件的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ca15d-200">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. <span data-ttu-id="ca15d-201">在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="ca15d-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="ca15d-202">在**搜索组 ID**提示符处, 键入要删除的搜索的搜索组名称, 然后按**enter**;例如, `ContosoCase`。</span><span class="sxs-lookup"><span data-stu-id="ca15d-202">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="ca15d-203">请注意, 此名称区分大小写, 因此您必须按照在第3步中运行脚本时的相同方式键入此名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-203">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="ca15d-204">该脚本显示删除的每个搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="ca15d-204">The script displays the name of each search that's deleted.</span></span>
    
    ![运行该脚本以删除搜索组中的搜索](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
