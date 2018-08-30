---
title: 创建、报告和删除多个内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 了解如何自动执行内容搜索任务，如创建搜索和 Office 365 安全性的 PowerShell 脚本通过运行报告&amp;合规性中心。
ms.openlocfilehash: 2baa569c28ed5324e6674addeac688b854a65ed8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525056"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>创建、报告和删除多个内容搜索

 快速创建并报告发现搜索通常是电子数据展示和调查的一个重要步骤时您尝试了解基础数据，和丰富程度和搜索的质量。可帮助您执行此操作，安全&amp;合规性中心提供一组的 Windows PowerShell cmdlet 可自动处理耗时的内容搜索任务。这些脚本提供快速简便的方法来创建的搜索，然后再运行报告可帮助您确定的问题的数据量的估计的搜索结果。脚本还可用于创建不同版本的搜索以比较每个生成的结果。这些脚本可帮助您快速、 高效地确定并挑选数据。 
  
## <a name="before-you-begin"></a>准备工作

- 您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行本主题中所述的脚本。 
    
- 若要为 OneDrive for Business 网站，您可以将它们添加到在步骤 1 中的 CSV 文件的组织中收集的 url 列表，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。 
    
- 请务必保存您在本主题与同一文件夹中创建的所有文件。将更加轻松地运行脚本。
    
- 脚本包含最少的错误处理。它们的主要用途是快速创建、 报告和删除多个内容搜索。
    
- 本主题中提供的示例脚本不支持在任何 Microsoft 标准支持程序或服务。是按原样提供的示例脚本，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>步骤 1： 创建 CSV 文件包含有关搜索要运行的信息

在此步骤中创建的以逗号分隔的值 (CSV) 文件包含为每个用户想要搜索的行。您可以搜索用户的 Exchange Online 邮箱包括存档邮箱中，如果已启用） 和 OneDrive for Business 站点。或者您可以搜索只邮箱或 OneDrive for Business 站点。您还可以在 SharePoint Online 组织中搜索的任何网站。步骤 3 中运行的脚本将在 CSV 文件中创建单独的搜索对于每个行。 
  
1. 复制并粘贴到使用记事本.txt 文件的以下文本。在本地计算机上将此文件保存到一个文件夹。您将将其他脚本保存到此文件夹以及。
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    第一行的标题行，该文件列出了**新建 ComplianceSearch** cmdlet （在步骤 3 中的脚本） 将用于创建新的内容搜索参数。每个参数名称并用逗号分隔。请确保在标题行中没有任何空格。在标题行下的每一行代表参数值为每个搜索。确保 CSV 文件中的占位符数据替换为实际数据。 
    
2. 在 Excel 中，打开.txt 文件，然后使用下表中的信息以编辑每个搜索信息的文件。 
    
    |**参数**|**说明**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |用户的邮箱的 SMTP 地址。  <br/> |
    | `SharePointLocation` <br/> |用户的 OneDrive for Business 站点或组织中的任何网站的 URL 的 URL。为 onedrive for Business 站点 URL，使用以下格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。例如， `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。<br/> |
    | `ContentMatchQuery` <br/> |搜索的搜索查询。有关创建搜索查询的详细信息，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。<br/> |
    | `StartDate` <br/> |为电子邮件，或后一条消息的日期已接收的收件人或发件人发送。上 SharePoint 或 OneDrive for Business 站点的文档，上次修改日期当天或之后文档。  <br/> |
    | `EndDate` <br/> |日期或之前一条消息发送的电子邮件，发送的用户。上 SharePoint 或 OneDrive for Business 站点的文档，上次修改日期或之前文档。  <br/> |
   
3. 在本地计算机上将 Excel 文件保存为 CSV 文件的文件夹。您在步骤 3 中创建的脚本将使用此 CSV 文件中的信息来创建搜索。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步骤 2： 连接到安全性和合规性中心 PowerShell

下一步是将 Windows PowerShell 连接到安全性&amp;的组织的合规性中心。
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `ConnectSCC.ps1`。将文件保存到您在步骤 1 中保存为 CSV 文件的同一文件夹中。
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. 本地计算机上打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行脚本。例如：
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>步骤 3： 运行脚本以创建和启动搜索

此步骤中的脚本将在您在步骤 1 中创建的 CSV 文件中创建单独的内容搜索对于每个行。运行此脚本时，系统将提示您的两个值：
  
- **搜索组 ID** -此名称可以轻松组织从 CSV 文件创建的搜索。每次搜索所创建的名为具有搜索组 ID，然后数字追加到的搜索名称。例如，如果**ContosoCase**输入搜索组 ID，然后搜索被命名为**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**，等等。请注意，您键入的名称区分大小写。使用步骤 4 和步骤 5 中的搜索组 ID 时，您需要使用相同的大小写，就像您在创建时。 
    
- **CSV 文件**-步骤 1 中创建 CSV 文件的名称。请务必包括使用完整的文件名，包括.csv 文件扩展名;例如， `ContosoCase.csv`。
    
若要运行该脚本，请执行下列操作：

1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `CreateSearches.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。
    
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

2. 在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：
    
    ```
    .\CreateSearches.ps1
    ```

3. 在**搜索组 ID**提示符处，键入搜索组名，，，然后按**Enter**;例如， `ContosoCase`。请记住，此名称区分大小写，因此您必须在后续步骤中键入相同的方式。
    
4. 在**源 CSV 文件**提示符处，键入的 CSV 文件，包括.csv 文件扩展名; 名称例如， `ContosoCase.csv`。
    
5. 按**Enter**以继续运行该脚本。 
    
    该脚本显示创建和运行搜索的进度。完成该脚本后，它将返回的提示。 
    
    ![运行该脚本以创建多个合规性搜索的示例输出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>步骤 4： 运行该脚本报告搜索估计

创建搜索后下, 一步是运行显示为在步骤 3 中创建的每个搜索的搜索点击次数的简单报告的脚本。此报告还包括每个搜索和命中总数和总大小的所有搜索结果的大小。当您运行报告脚本时，您将提示输入搜索组 ID 和 CSV 文件名这是如果您想要将报告保存到 CSV 文件。
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `SearchReport.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。
    
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

2. 在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：
    
    ```
    .\SearchReport.ps1
    ```

3. 在**搜索组 ID**提示符处，键入搜索组名，，，然后按**Enter**;例如`ContosoCase`。请记住此名称区分大小写，因此必须将其键入相同的方式执行步骤 3 中运行该脚本时。
    
4. 在**文件路径到 CSV 文件 （保留空白以只显示报告） 报告的保存**提示符处，键入完整文件名路径 （包括.csv 文件扩展名） 的文件名称，如果您想要将报告保存到 CSV 文件。CSV 文件，包括.csv 文件扩展名的名称。例如，您可以键入`ContosoCaseReport.csv`将其保存到当前目录，也可以键入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`以将其保存到不同的文件夹。您还可以将提示留空，以显示报告，但不是将其保存到文件。 
    
5. 按**输入**。
    
    该脚本显示创建和运行搜索的进度。完成该脚本后，将显示报表。 
    
    ![运行搜索报告以显示对搜索组的估计](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 如果同一邮箱或网站指定为多个搜索中搜索组中的内容位置，（对于的项目数和总大小） 报表中的总结果评估可能包含相同的项目的结果。这是因为文档的同一个电子邮件将被计算在内多次如果符合搜索组中的不同搜索的查询。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>步骤 5： 运行脚本以删除搜索

您可能正在创建大量的搜索，因为此最后一个脚本只是更加方便要快速删除您在步骤 3 中创建的搜索。像其他脚本，此还会提示您输入搜索组 id。运行此脚本时，将删除所有搜索与搜索名称中的搜索组 ID。 
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `DeleteSearches.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。
    
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

2. 在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：
    
    ```
    .\DeleteSearches.ps1
    ```

3. 在**搜索组 ID**提示符处，键入您想要删除的搜索的搜索组名称，然后按**Enter**;例如， `ContosoCase`。请记住此名称区分大小写，因此必须将其键入相同的方式执行步骤 3 中运行该脚本时。
    
    该脚本显示删除每个搜索的名称。
    
    ![运行该脚本以删除搜索组中的搜索](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
