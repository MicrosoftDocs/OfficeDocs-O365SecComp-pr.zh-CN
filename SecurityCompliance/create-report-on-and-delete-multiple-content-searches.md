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
ms.openlocfilehash: c61a62c7b31d24346fd58b7562872a7c45d1c65d
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213232"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>创建、报告和删除多个内容搜索

 当你尝试了解基础数据以及搜索的丰富程度和质量时, 快速创建和报告发现搜索通常是电子数据展示和调查中的重要步骤。为帮助你执行此操作, 安全&amp;合规性中心提供了一组 Windows PowerShell cmdlet, 以自动执行耗时的内容搜索任务。这些脚本提供了创建大量搜索的快速、简便的方法, 然后运行估计的搜索结果报告, 这些报告可帮助您确定所讨论的数据量。您还可以使用脚本来创建不同版本的搜索, 以比较每个搜索结果所产生的结果。这些脚本可帮助您快速高效地识别和挑选数据。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须是安全&amp;合规中心中的电子数据展示管理器角色组的成员, 才能运行本主题中所述的脚本。 
    
- 若要收集组织中可添加到 CSV 文件的 onedrive for business 网站的 url 列表, 请参阅在[组织中创建所有 OneDrive 位置的列表](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。 
    
- 请务必将您在本主题中创建的所有文件保存到同一个文件夹中。这将使运行脚本变得更加简单。
    
- 这些脚本包括最少的错误处理。其主要目的是快速创建、报告和删除多个内容搜索。
    
- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步骤 1: 创建包含有关要运行的搜索的信息的 CSV 文件

在此步骤中创建的逗号分隔值 (CSV) 文件中, 每个要搜索的用户都包含一行。您可以搜索用户的 Exchange Online 邮箱 (包括存档邮箱 (如果已启用) 和 OneDrive for business 网站。或者, 您可以仅搜索邮箱或 OneDrive for business 网站。您还可以在 SharePoint Online 组织中搜索任何网站。您在步骤3中运行的脚本将为 CSV 文件中的每一行创建单独的搜索。 
  
1. 使用记事本将以下文本复制并粘贴到一个 .txt 文件中。将此文件保存到本地计算机上的文件夹中。此外, 还会将其他脚本保存到此文件夹中。
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    文件的第一行 (即标题行) 列出将由**new-compliancesearch** cmdlet 使用的参数 (在步骤3的脚本中) 以创建新的内容搜索。每个参数名称之间用逗号分隔。请确保标题行中没有任何空格。标题行下的每一行表示每个搜索的参数值。请务必将 CSV 文件中的占位符数据替换为实际数据。 
    
2. 在 Excel 中打开 .txt 文件, 然后使用下表中的信息编辑包含每个搜索的信息的文件。 
    
    |**参数**|**说明**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |用户邮箱的 SMTP 地址。  <br/> |
    | `SharePointLocation` <br/> |用户的 OneDrive for business 网站的 url 或组织中任何网站的 url。对于 OneDrive for business 网站的 URL, 请使用以下格式: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。例如, `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。<br/> |
    | `ContentMatchQuery` <br/> |搜索的搜索查询。有关创建搜索查询的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。<br/> |
    | `StartDate` <br/> |对于电子邮件, 收件人接收或发送邮件的日期或发件人发送邮件的日期。对于 SharePoint 或 OneDrive for business 网站上的文档, 上次修改文档的日期或文档之后的日期。  <br/> |
    | `EndDate` <br/> |对于电子邮件, 由用户发送的邮件发送的日期或之前的日期。对于 SharePoint 或 OneDrive for business 网站上的文档, 上次修改文档的日期或之前的日期。  <br/> |
   
3. 将 Excel 文件作为 CSV 文件保存到本地计算机上的文件夹中。您在步骤3中创建的脚本将使用此 CSV 文件中的信息来创建搜索。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步骤 2: 连接到安全 & 合规中心 PowerShell

下一步是将 Windows PowerShell 连接到组织的&amp;安全合规中心。
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `ConnectSCC.ps1`。将文件保存到在步骤1中保存 CSV 文件的文件夹。
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. 在本地计算机上, 打开 Windows PowerShell, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步骤 3: 运行脚本以创建并启动搜索

此步骤中的脚本将为您在步骤1中创建的 CSV 文件中的每一行创建单独的内容搜索。运行此脚本时, 系统将提示您输入两个值:
  
- **搜索组 ID** -此名称提供了一种简单的方法来组织从 CSV 文件创建的搜索。创建的每个搜索都使用搜索组 ID 命名, 然后将数字追加到搜索名称。例如, 如果您为搜索组 ID 输入**ContosoCase** , 则会将搜索命名为**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**等等。请注意, 键入的名称区分大小写。在第4步和第5步中使用搜索组 ID 时, 必须使用与创建时相同的大小写。 
    
- **csv 文件**-您在步骤1中创建的 CSV 文件的名称。确保包含使用完整文件名, 包括 .csv 文件扩展名;例如, `ContosoCase.csv`。
    
若要运行该脚本，请执行下列操作：

1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `CreateSearches.ps1`。将文件保存到保存其他文件的同一文件夹中。
    
  ```
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

2. 在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:
    
    ```
    .\CreateSearches.ps1
    ```

3. 在**搜索组 ID**提示符处, 键入搜索组名称, 然后按**enter**键;例如, `ContosoCase`。请注意, 此名称区分大小写, 因此必须在后续步骤中以相同的方式键入此名称。
    
4. 在**源 CSV 文件**提示符处, 键入 csv 文件的名称, 包括 .csv 文件扩展名;例如, `ContosoCase.csv`。
    
5. 按**enter**以继续运行该脚本。 
    
    该脚本将显示创建和运行搜索的进度。脚本完成后, 将返回到提示窗口。 
    
    ![运行该脚本以创建多个合规性搜索的示例输出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步骤 4: 运行脚本以报告搜索估计值

创建搜索后, 下一步是运行一个脚本, 该脚本显示在步骤3中创建的每个搜索的搜索命中次数的简单报告。该报告还包括每个搜索的结果大小, 以及所有搜索的总点击数和总大小。运行报告脚本时, 系统会提示输入搜索组 ID, 如果您想要将报告保存到 csv 文件中, 则会提示您输入 csv 文件名。
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `SearchReport.ps1`。将文件保存到保存其他文件的同一文件夹中。
    
  ```
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

2. 在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:
    
    ```
    .\SearchReport.ps1
    ```

3. 在**搜索组 ID**提示符处, 键入搜索组名称, 然后按**enter**键;例如`ContosoCase`。请注意, 此名称区分大小写, 因此您必须按照在第3步中运行脚本时的相同方式键入此名称。
    
4. 如果要将报告保存**到 csv 文件 (保留为空以显示报告)** 提示符, 请在要将报告保存到 csv 文件中时, 键入完整文件名 path (包括 .csv 文件扩展名) 的文件名。csv 文件的名称, 包括 .csv 文件扩展名。例如, 可以键入`ContosoCaseReport.csv`将其保存到当前目录中, 也可以键入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`以将其保存到其他文件夹。您也可以将提示留空以显示报告, 但不将其保存到文件中。 
    
5. 按**enter**。
    
    该脚本将显示创建和运行搜索的进度。脚本完成后, 将显示报告。 
    
    ![运行搜索报告以显示对搜索组的估计](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 如果在搜索组中的多个搜索中将相同的邮箱或网站指定为内容位置, 则在报告中估计的总结果 (对于项目数和总大小) 可能包含相同项目的结果。这是因为, 如果与搜索组中的不同搜索的查询相匹配, 则相同的电子邮件或文档将被多次计数。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>步骤 5: 运行脚本以删除搜索

由于您可能要创建大量搜索, 因此此最后的脚本可以轻松地快速删除在步骤3中创建的搜索。与其他脚本一样, 这也会提示您输入搜索组 ID。运行此脚本时, 搜索名称中包含搜索组 ID 的所有搜索都将被删除。 
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `DeleteSearches.ps1`。将文件保存到保存其他文件的同一文件夹中。
    
  ```
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

2. 在 Windows PowerShell 中, 转到上一步中保存脚本的文件夹, 然后运行该脚本;例如:
    
    ```
    .\DeleteSearches.ps1
    ```

3. 在**搜索组 ID**提示符处, 键入要删除的搜索的搜索组名称, 然后按**enter**;例如, `ContosoCase`。请注意, 此名称区分大小写, 因此您必须按照在第3步中运行脚本时的相同方式键入此名称。
    
    该脚本显示删除的每个搜索的名称。
    
    ![运行该脚本以删除搜索组中的搜索](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
