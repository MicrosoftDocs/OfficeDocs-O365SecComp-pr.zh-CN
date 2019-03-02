---
title: 将 Office 365 中的内容搜索用于目标集合
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 在 Office 365 安全&amp;合规中心中使用内容搜索来执行目标集合。目标集合意味着您确信项目响应的是事例或特权项目位于特定的邮箱或站点文件夹中。使用本文中的脚本获取要搜索的特定邮箱或网站文件夹的文件夹 ID 或路径。
ms.openlocfilehash: 6c41069a268991553f03763ae80dea032d5db202
ms.sourcegitcommit: 03054baf50c1dd5cd9ca6a9bd5d056f3db98f964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30354684"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="5349b-105">将 Office 365 中的内容搜索用于目标集合</span><span class="sxs-lookup"><span data-stu-id="5349b-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="5349b-p102">Office 365 安全&amp;合规中心中的内容搜索功能不会在 UI 中直接提供用于搜索 Exchange 邮箱或 SharePoint 和 OneDrive for business 网站中特定文件夹的直接方法。但是, 通过在实际搜索查询语法中指定文件夹 ID 或路径, 可以搜索特定文件夹 (称为*目标集合*)。当您确信项目响应的情况或特权项目位于特定邮箱或站点文件夹中时, 使用内容搜索来执行目标集合非常有用。您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID, 或 SharePoint 和 OneDrive for business 网站上的文件夹的路径。然后, 您可以在搜索查询中使用文件夹 ID 或路径返回文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="5349b-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="5349b-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="5349b-111">Before you begin</span></span>

- <span data-ttu-id="5349b-p103">您必须是安全&amp;合规中心中的电子数据展示管理器角色组的成员, 才能在第1步中运行该脚本。有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="5349b-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="5349b-p104">此外, 还必须在 Exchange Online 组织中为 "邮件收件人" 角色分配。这是运行**get-mailboxfolderstatistics** cmdlet (包含在步骤1中的脚本中) 所必需的。默认情况下, 将 "邮件收件人" 角色分配给 Exchange Online 中的 "组织管理" 和 "收件人管理" 角色组。有关在 Exchange Online 中分配权限的详细信息, 请参阅[Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102)。您还可以创建自定义角色组, 将 "邮件收件人" 角色分配给该角色组, 然后添加需要在步骤1中运行该脚本的成员。有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="5349b-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="5349b-p105">每次在第1步中运行脚本时, 都会创建一个新的远程 PowerShell 会话。因此, 你可以使用所有可供你使用的远程 PowerShell 会话。若要防止这种情况发生, 可以运行以下命令来断开活动的远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="5349b-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="5349b-123">有关详细信息，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).。</span><span class="sxs-lookup"><span data-stu-id="5349b-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="5349b-p106">该脚本包括最少的错误处理。脚本的主要用途是快速显示邮箱文件夹 id 或网站路径的列表, 该列表可用于内容搜索的搜索查询语法以执行目标集合。</span><span class="sxs-lookup"><span data-stu-id="5349b-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="5349b-p107">在任何 Microsoft standard 支持计划或服务下, 本主题中提供的示例脚本不受支持。示例脚本按原样提供, 而不提供任何种类的担保。Microsoft 进一步拒绝所有暗示的担保, 包括但不限于对适销性或特定用途适用性的任何暗示担保。因使用或性能示例脚本和文档而导致的全部风险都将保留给您。在任何情况下, Microsoft、其作者或对脚本的创建、生产或交付的其他任何人都有责任承担任何损害 (包括但不限于业务利润损失、业务中断和丢失造成的损失)。因使用或无法使用示例脚本或文档而引起的业务信息或其他 pecuniary 丢失, 即使 Microsoft 已被告知可能发生此类损坏的情况也是如此。</span><span class="sxs-lookup"><span data-stu-id="5349b-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="5349b-131">步骤 1: 运行脚本以获取邮箱或网站的文件夹列表</span><span class="sxs-lookup"><span data-stu-id="5349b-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="5349b-p108">您在此第一步中运行的脚本将返回邮箱文件夹或 SharePoint 或 OneDrive for business 文件夹的列表, 以及每个文件夹对应的文件夹 ID 或路径。运行此脚本时, 它将提示您提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="5349b-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="5349b-p109">**电子邮件地址或网站 URL**键入保管人的电子邮件地址, 以返回 Exchange 邮箱文件夹和文件夹 id 的列表。或者键入 SharePoint 网站或 OneDrive for business 网站的 URL, 以返回指定网站的路径列表。下面是一些示例:</span><span class="sxs-lookup"><span data-stu-id="5349b-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="5349b-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="5349b-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="5349b-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="5349b-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="5349b-139">**OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="5349b-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="5349b-p110">**你的用户凭据**-脚本将使用你的凭据连接到 Exchange Online 和与远程&amp; PowerShell 的安全合规性中心。如前面所述, 您必须分配适当的权限才能成功运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="5349b-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="5349b-142">若要显示邮箱文件夹或网站 documentlink (路径) 名称的列表, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="5349b-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="5349b-143">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="5349b-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security &amp; Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security &amp; Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. <span data-ttu-id="5349b-144">在本地计算机上, 打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349b-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="5349b-145">运行脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="5349b-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="5349b-146">输入脚本提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="5349b-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="5349b-p111">该脚本将显示指定用户的邮箱文件夹或网站文件夹的列表。让此窗口打开, 以便您可以复制文件夹 ID 或路径名称, 并将其粘贴到步骤2中的搜索查询中。</span><span class="sxs-lookup"><span data-stu-id="5349b-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="5349b-p112">您可以将脚本的输出重新定向到文本文件, 而不是在计算机屏幕上显示文件夹的列表。此文件将保存到脚本所在的文件夹中。例如, 若要将脚本输出重定向到文本文件, 请在第3步中运行以下命令`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` : 然后, 可以从文件中复制文件夹 ID 或路径, 以在搜索查询中使用。</span><span class="sxs-lookup"><span data-stu-id="5349b-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="5349b-152">邮箱文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="5349b-152">Script output for mailbox folders</span></span>

<span data-ttu-id="5349b-p113">如果你获取的是邮箱文件夹 id, 脚本将使用远程 PowerShell 连接到 Exchange Online, 运行**MailboxFolderStatisics** cmdlet, 然后显示指定邮箱中的文件夹列表。对于邮箱中的每个文件夹, 该脚本都会在 " **FolderPath** " 列中显示文件夹的名称, 并在 " **FolderQuery** " 列中显示文件夹 ID。此外, 该脚本还会将**folderId**的前缀 (即邮箱属性的名称) 添加到文件夹 ID。由于**folderid**属性是一个可搜索的属性, 因此您`folderid:<folderid>`将在步骤2中的搜索查询中使用搜索该文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349b-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="5349b-157">下面的示例展示了邮箱文件夹的脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="5349b-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![脚本返回的邮箱文件夹和文件夹 id 列表的示例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="5349b-159">步骤2中的示例显示了用于在用户的 "可恢复的项目" 文件夹中搜索 "清除" 子文件夹的查询。</span><span class="sxs-lookup"><span data-stu-id="5349b-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="5349b-160">网站文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="5349b-160">Script output for site folders</span></span>

<span data-ttu-id="5349b-p114">如果从 SharePoint 或 OneDrive for business 网站获取 documentlinks, 则该脚本将使用远程 PowerShell 连接&amp;到安全合规中心, 并创建一个新的内容搜索, 以搜索网站中的文件夹, 然后显示位于指定网站中的文件夹。该脚本将显示每个文件夹的名称, 并将**路径**(网站属性的名称) 的前缀添加到文件夹 URL。由于**path**属性是一个可搜索的属性, 因此您`path:<path>`将在步骤2中的搜索查询中使用搜索该文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349b-p114">If you're getting documentlinks from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="5349b-164">下面的示例展示了网站文件夹的脚本返回的输出。</span><span class="sxs-lookup"><span data-stu-id="5349b-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![脚本返回的网站文件夹的 documentlink 名称列表示例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="5349b-166">步骤 2: 使用文件夹 ID 或 documentlink 执行目标集合</span><span class="sxs-lookup"><span data-stu-id="5349b-166">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="5349b-p115">在运行脚本以收集特定用户的文件夹 id 或 documentlinks 的列表后, 下一步是转到安全&amp;符合性中心并创建新的内容搜索以搜索特定文件夹。您将在 " `folderid:<folderid>`内容`documentlink:<path>`搜索关键字" 框中配置的搜索查询中使用或属性 (如果使用**new-compliancesearch** cmdlet, 则为*ContentMatchQuery*参数的值)。您可以将`folderid`或`documentlink`属性与其他搜索参数或搜索条件结合使用。如果只在查询中`folderid`包括`documentlink`或属性, 则搜索将返回位于指定文件夹中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="5349b-p115">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions. If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="5349b-171">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="5349b-171">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="5349b-172">使用在步骤1中运行脚本时使用的帐户和凭据登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="5349b-172">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="5349b-173">在&amp;安全合规性中心的左侧窗格中, 单击 **" &amp;搜索调查** \> **内容搜索**", 然后\*\*\*\* ![单击 "新建](media/O365-MDM-CreatePolicy-AddIcon.gif)添加图标"。</span><span class="sxs-lookup"><span data-stu-id="5349b-173">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="5349b-p116">在 "**新建搜索**" 页上, 键入内容搜索的名称。此名称在您的组织中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5349b-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="5349b-176">在 "**您希望我们在哪里进行查找**" 下, 根据您搜索的是邮箱文件夹还是站点文件夹, 执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="5349b-176">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="5349b-177">单击 "**选择要搜索的特定邮箱**", 然后添加您在步骤1中运行脚本时指定的相同邮箱。</span><span class="sxs-lookup"><span data-stu-id="5349b-177">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="5349b-178">或者</span><span class="sxs-lookup"><span data-stu-id="5349b-178">Or</span></span>
    
    - <span data-ttu-id="5349b-179">单击 "**选择要搜索的特定网站**" 搜索, 然后添加在步骤1中运行脚本时指定的相同网站 URL。</span><span class="sxs-lookup"><span data-stu-id="5349b-179">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="5349b-180">单击“下一步”。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5349b-180">Click **Next**.</span></span>
    
7. <span data-ttu-id="5349b-181">在 "**您希望我们在什么情况下查找**" 页上的 "关键字" 框`folderid:<folderid>`中`documentlink:<path>` , 粘贴步骤1中的脚本返回的 or 值。</span><span class="sxs-lookup"><span data-stu-id="5349b-181">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="5349b-182">例如, 下面的屏幕截图中的查询将搜索用户的 "可恢复项目" 文件夹中的 "清除" 子文件夹中的任何项目`folderid` ("清除" 子文件夹的属性值显示在步骤1中的屏幕截图中):</span><span class="sxs-lookup"><span data-stu-id="5349b-182">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="5349b-184">单击 "**搜索**" 以启动目标集合搜索。</span><span class="sxs-lookup"><span data-stu-id="5349b-184">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="5349b-185">目标集合的搜索查询示例</span><span class="sxs-lookup"><span data-stu-id="5349b-185">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="5349b-p117">下面是在搜索查询中使用`folderid`和`documentlink`属性执行目标集合的一些示例。请注意, 占位符用于`folderid:<folderid>` `documentlink:<path>`节省空间。</span><span class="sxs-lookup"><span data-stu-id="5349b-p117">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="5349b-p118">本示例将搜索三个不同的邮箱文件夹。可以使用类似的查询语法搜索用户的 "可恢复的项目" 文件夹中的隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349b-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="5349b-190">本示例将在邮箱文件夹中搜索包含精确短语的项目。</span><span class="sxs-lookup"><span data-stu-id="5349b-190">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="5349b-191">本示例在标题中搜索包含字母 "NDA" 的文档的网站文件夹 (和任何子文件夹)。</span><span class="sxs-lookup"><span data-stu-id="5349b-191">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="5349b-192">本示例搜索某个日期范围内已更改的文档的网站文件夹 (和任何子文件夹)。</span><span class="sxs-lookup"><span data-stu-id="5349b-192">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="5349b-193">更多信息</span><span class="sxs-lookup"><span data-stu-id="5349b-193">More information</span></span>

<span data-ttu-id="5349b-194">在使用本文中的脚本执行目标集合时, 请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="5349b-194">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="5349b-p119">脚本不会从结果中删除任何文件夹。因此, 结果中列出的某些文件夹可能是不可搜索的 (或返回零个项目), 因为它们包含系统生成的内容。</span><span class="sxs-lookup"><span data-stu-id="5349b-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="5349b-p120">此脚本仅返回用户的主邮箱的文件夹信息。它不会返回有关用户存档邮箱中的文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="5349b-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="5349b-p121">搜索邮箱文件夹时, 将仅搜索指定的文件夹 (由`folderid`其属性标识)。不搜索子文件夹。若要搜索子文件夹, 您需要使用要搜索的子文件夹的文件夹 ID。</span><span class="sxs-lookup"><span data-stu-id="5349b-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="5349b-202">搜索站点文件夹时, 将搜索文件夹 (由其`documentlink`属性标识) 和所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="5349b-202">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="5349b-p122">当您在搜索查询中导出仅指定`folderid`属性的搜索结果时, 可以选择第一个导出选项 "。所有项目 (不包括具有不可识别的格式的项目) 已加密, 或未对其他原因编制索引。将始终导出文件夹中的所有项目 (无论其索引状态如何), 因为文件夹 ID 始终编制索引。</span><span class="sxs-lookup"><span data-stu-id="5349b-p122">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons." All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
