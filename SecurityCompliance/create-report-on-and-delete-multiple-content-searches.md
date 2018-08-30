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
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="adb13-103">创建、报告和删除多个内容搜索</span><span class="sxs-lookup"><span data-stu-id="adb13-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="adb13-p101">快速创建并报告发现搜索通常是电子数据展示和调查的一个重要步骤时您尝试了解基础数据，和丰富程度和搜索的质量。可帮助您执行此操作，安全&amp;合规性中心提供一组的 Windows PowerShell cmdlet 可自动处理耗时的内容搜索任务。这些脚本提供快速简便的方法来创建的搜索，然后再运行报告可帮助您确定的问题的数据量的估计的搜索结果。脚本还可用于创建不同版本的搜索以比较每个生成的结果。这些脚本可帮助您快速、 高效地确定并挑选数据。</span><span class="sxs-lookup"><span data-stu-id="adb13-p101">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches. To help you do this, the Security &amp; Compliance Center offers a set of Windows PowerShell cmdlets to automate time-consuming Content Search tasks. These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question. You can also use the scripts to create different versions of searches to compare the results each one produces. These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="adb13-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="adb13-109">Before you begin</span></span>

- <span data-ttu-id="adb13-110">您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行本主题中所述的脚本。</span><span class="sxs-lookup"><span data-stu-id="adb13-110">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="adb13-111">若要为 OneDrive for Business 网站，您可以将它们添加到在步骤 1 中的 CSV 文件的组织中收集的 url 列表，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)。</span><span class="sxs-lookup"><span data-stu-id="adb13-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="adb13-p102">请务必保存您在本主题与同一文件夹中创建的所有文件。将更加轻松地运行脚本。</span><span class="sxs-lookup"><span data-stu-id="adb13-p102">Be sure to save all the files that you create in this topic to the same folder. That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="adb13-p103">脚本包含最少的错误处理。它们的主要用途是快速创建、 报告和删除多个内容搜索。</span><span class="sxs-lookup"><span data-stu-id="adb13-p103">The scripts include minimal error handling. Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="adb13-p104">本主题中提供的示例脚本不支持在任何 Microsoft 标准支持程序或服务。是按原样提供的示例脚本，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。</span><span class="sxs-lookup"><span data-stu-id="adb13-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="adb13-121">步骤 1： 创建 CSV 文件包含有关搜索要运行的信息</span><span class="sxs-lookup"><span data-stu-id="adb13-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="adb13-p105">在此步骤中创建的以逗号分隔的值 (CSV) 文件包含为每个用户想要搜索的行。您可以搜索用户的 Exchange Online 邮箱包括存档邮箱中，如果已启用） 和 OneDrive for Business 站点。或者您可以搜索只邮箱或 OneDrive for Business 站点。您还可以在 SharePoint Online 组织中搜索的任何网站。步骤 3 中运行的脚本将在 CSV 文件中创建单独的搜索对于每个行。</span><span class="sxs-lookup"><span data-stu-id="adb13-p105">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search. You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site. Or you can search just the mailbox or the OneDrive for Business site. You can also search any site in your SharePoint Online organization. The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="adb13-p106">复制并粘贴到使用记事本.txt 文件的以下文本。在本地计算机上将此文件保存到一个文件夹。您将将其他脚本保存到此文件夹以及。</span><span class="sxs-lookup"><span data-stu-id="adb13-p106">Copy and paste the following text into a .txt file using NotePad. Save this file to a folder on your local computer. You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="adb13-p107">第一行的标题行，该文件列出了**新建 ComplianceSearch** cmdlet （在步骤 3 中的脚本） 将用于创建新的内容搜索参数。每个参数名称并用逗号分隔。请确保在标题行中没有任何空格。在标题行下的每一行代表参数值为每个搜索。确保 CSV 文件中的占位符数据替换为实际数据。</span><span class="sxs-lookup"><span data-stu-id="adb13-p107">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches. Each parameter name is separated by a comma. Make sure there aren't any spaces in the header row. Each row under the header row represents the parameter values for each search. Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="adb13-135">在 Excel 中，打开.txt 文件，然后使用下表中的信息以编辑每个搜索信息的文件。</span><span class="sxs-lookup"><span data-stu-id="adb13-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="adb13-136">**参数**</span><span class="sxs-lookup"><span data-stu-id="adb13-136">**Parameter**</span></span>|<span data-ttu-id="adb13-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="adb13-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="adb13-138">用户的邮箱的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="adb13-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="adb13-p108">用户的 OneDrive for Business 站点或组织中的任何网站的 URL 的 URL。为 onedrive for Business 站点 URL，使用以下格式： ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。例如， `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="adb13-p108">The URL for the user's OneDrive for Business site or the URL for any site in your organization. For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  </span></span><br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="adb13-p109">搜索的搜索查询。有关创建搜索查询的详细信息，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="adb13-p109">The search query for the search. For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).  </span></span><br/> |
    | `StartDate` <br/> |<span data-ttu-id="adb13-p110">为电子邮件，或后一条消息的日期已接收的收件人或发件人发送。上 SharePoint 或 OneDrive for Business 站点的文档，上次修改日期当天或之后文档。</span><span class="sxs-lookup"><span data-stu-id="adb13-p110">For email, the date on or after a message was received by a recipient or sent by the sender. For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="adb13-p111">日期或之前一条消息发送的电子邮件，发送的用户。上 SharePoint 或 OneDrive for Business 站点的文档，上次修改日期或之前文档。</span><span class="sxs-lookup"><span data-stu-id="adb13-p111">For email, the date on or before a message was sent by a sent by the user. For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="adb13-p112">在本地计算机上将 Excel 文件保存为 CSV 文件的文件夹。您在步骤 3 中创建的脚本将使用此 CSV 文件中的信息来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="adb13-p112">Save the Excel file as a CSV file to a folder on your local computer. The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="adb13-150">步骤 2： 连接到安全性和合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="adb13-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="adb13-151">下一步是将 Windows PowerShell 连接到安全性&amp;的组织的合规性中心。</span><span class="sxs-lookup"><span data-stu-id="adb13-151">The next step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="adb13-p113">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `ConnectSCC.ps1`。将文件保存到您在步骤 1 中保存为 CSV 文件的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="adb13-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`. Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="adb13-154">本地计算机上打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="adb13-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="adb13-155">步骤 3： 运行脚本以创建和启动搜索</span><span class="sxs-lookup"><span data-stu-id="adb13-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="adb13-p114">此步骤中的脚本将在您在步骤 1 中创建的 CSV 文件中创建单独的内容搜索对于每个行。运行此脚本时，系统将提示您的两个值：</span><span class="sxs-lookup"><span data-stu-id="adb13-p114">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1. When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="adb13-p115">**搜索组 ID** -此名称可以轻松组织从 CSV 文件创建的搜索。每次搜索所创建的名为具有搜索组 ID，然后数字追加到的搜索名称。例如，如果**ContosoCase**输入搜索组 ID，然后搜索被命名为**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**，等等。请注意，您键入的名称区分大小写。使用步骤 4 和步骤 5 中的搜索组 ID 时，您需要使用相同的大小写，就像您在创建时。</span><span class="sxs-lookup"><span data-stu-id="adb13-p115">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file. Each search that's created is named with the Search Group ID, and then a number is appended to the search name. For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on. Note that the name you type is case sensitive. When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="adb13-p116">**CSV 文件**-步骤 1 中创建 CSV 文件的名称。请务必包括使用完整的文件名，包括.csv 文件扩展名;例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="adb13-p116">**CSV file** - The name of the CSV file that you created in Step 1. Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="adb13-165">若要运行该脚本，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="adb13-165">To run the script:</span></span>

1. <span data-ttu-id="adb13-p117">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `CreateSearches.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="adb13-p117">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="adb13-168">在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="adb13-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="adb13-p118">在**搜索组 ID**提示符处，键入搜索组名，，，然后按**Enter**;例如， `ContosoCase`。请记住，此名称区分大小写，因此您必须在后续步骤中键入相同的方式。</span><span class="sxs-lookup"><span data-stu-id="adb13-p118">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="adb13-171">在**源 CSV 文件**提示符处，键入的 CSV 文件，包括.csv 文件扩展名; 名称例如， `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="adb13-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="adb13-172">按**Enter**以继续运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="adb13-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="adb13-p119">该脚本显示创建和运行搜索的进度。完成该脚本后，它将返回的提示。</span><span class="sxs-lookup"><span data-stu-id="adb13-p119">The script displays the progress of creating and running the searches. When the script is complete, it returns to the prompt.</span></span> 
    
    ![运行该脚本以创建多个合规性搜索的示例输出](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="adb13-176">步骤 4： 运行该脚本报告搜索估计</span><span class="sxs-lookup"><span data-stu-id="adb13-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="adb13-p120">创建搜索后下, 一步是运行显示为在步骤 3 中创建的每个搜索的搜索点击次数的简单报告的脚本。此报告还包括每个搜索和命中总数和总大小的所有搜索结果的大小。当您运行报告脚本时，您将提示输入搜索组 ID 和 CSV 文件名这是如果您想要将报告保存到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="adb13-p120">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3. The report also includes the size of results for each search, and the total number of hits and total size of all searches. When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="adb13-p121">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `SearchReport.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="adb13-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="adb13-182">在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="adb13-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="adb13-p122">在**搜索组 ID**提示符处，键入搜索组名，，，然后按**Enter**;例如`ContosoCase`。请记住此名称区分大小写，因此必须将其键入相同的方式执行步骤 3 中运行该脚本时。</span><span class="sxs-lookup"><span data-stu-id="adb13-p122">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="adb13-p123">在**文件路径到 CSV 文件 （保留空白以只显示报告） 报告的保存**提示符处，键入完整文件名路径 （包括.csv 文件扩展名） 的文件名称，如果您想要将报告保存到 CSV 文件。CSV 文件，包括.csv 文件扩展名的名称。例如，您可以键入`ContosoCaseReport.csv`将其保存到当前目录，也可以键入`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`以将其保存到不同的文件夹。您还可以将提示留空，以显示报告，但不是将其保存到文件。</span><span class="sxs-lookup"><span data-stu-id="adb13-p123">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file. name of the CSV file, including the .csv file extension. For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder. You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="adb13-189">按**输入**。</span><span class="sxs-lookup"><span data-stu-id="adb13-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="adb13-p124">该脚本显示创建和运行搜索的进度。完成该脚本后，将显示报表。</span><span class="sxs-lookup"><span data-stu-id="adb13-p124">The script displays the progress of creating and running the searches. When the script is complete, the report is displayed.</span></span> 
    
    ![运行搜索报告以显示对搜索组的估计](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="adb13-p125">如果同一邮箱或网站指定为多个搜索中搜索组中的内容位置，（对于的项目数和总大小） 报表中的总结果评估可能包含相同的项目的结果。这是因为文档的同一个电子邮件将被计算在内多次如果符合搜索组中的不同搜索的查询。</span><span class="sxs-lookup"><span data-stu-id="adb13-p125">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items. That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="adb13-195">步骤 5： 运行脚本以删除搜索</span><span class="sxs-lookup"><span data-stu-id="adb13-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="adb13-p126">您可能正在创建大量的搜索，因为此最后一个脚本只是更加方便要快速删除您在步骤 3 中创建的搜索。像其他脚本，此还会提示您输入搜索组 id。运行此脚本时，将删除所有搜索与搜索名称中的搜索组 ID。</span><span class="sxs-lookup"><span data-stu-id="adb13-p126">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3. Like the other scripts, this one also prompts you for the Search Group ID. All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="adb13-p127">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `DeleteSearches.ps1`。将文件保存到其他文件的保存位置的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="adb13-p127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
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

2. <span data-ttu-id="adb13-201">在 Windows PowerShell 中，转到上一步，保存该脚本的位置的文件夹，然后再运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="adb13-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="adb13-p128">在**搜索组 ID**提示符处，键入您想要删除的搜索的搜索组名称，然后按**Enter**;例如， `ContosoCase`。请记住此名称区分大小写，因此必须将其键入相同的方式执行步骤 3 中运行该脚本时。</span><span class="sxs-lookup"><span data-stu-id="adb13-p128">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="adb13-204">该脚本显示删除每个搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="adb13-204">The script displays the name of each search that's deleted.</span></span>
    
    ![运行该脚本以删除搜索组中的搜索](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
