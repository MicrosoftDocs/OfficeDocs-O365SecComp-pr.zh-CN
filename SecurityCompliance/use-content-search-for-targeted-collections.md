---
title: 使用 Office 365 中的目标集合的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/19/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 在 Office 365 安全性中使用内容搜索&amp;合规性中心，以执行目标的集合。目标的集合表示您确信案例做出迅速响应项目或特权的项目位于特定邮箱或网站文件夹中。使用本文中脚本以获取文件夹 ID 或您要搜索的特定邮箱或网站文件夹的路径。
ms.openlocfilehash: bb808e38f24ebf09a975b3082ef1dc61bc6344c4
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038295"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="9e23e-105">使用 Office 365 中的目标集合的内容搜索</span><span class="sxs-lookup"><span data-stu-id="9e23e-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="9e23e-p102">Office 365 安全性内容的搜索功能&amp;合规性中心没有提供在 UI 中的直接方法业务网站 Exchange 邮箱或 SharePoint 和 OneDrive 中搜索特定的文件夹。但是，就可以通过在实际的搜索查询语法指定的文件夹 ID 或路径来搜索特定的文件夹 （称为目标的集合）。当您确信案例做出迅速响应项目或特权的项目位于特定邮箱或网站文件夹中，使用内容搜索执行目标的集合很有用。可以使用本文中的脚本来获取邮箱文件夹的文件夹 ID 或业务网站上的 SharePoint 和 OneDrive 文件夹的路径。然后您可以使用的文件夹 ID 或路径搜索查询中返回项目位于的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it is possible to search specific folders (called a targeted collection) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="9e23e-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="9e23e-111">Before you begin</span></span>

- <span data-ttu-id="9e23e-p103">您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心在步骤 1 中运行脚本。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="9e23e-p104">此外，您必须在 Exchange Online 组织中的 Mail Recipients 角色分配。这需要运行**Get-mailboxfolderstatistics** cmdlet，包括在步骤 1 中的脚本。默认情况下 Mail Recipients 角色分配给组织管理和 Recipient Management 角色组在 Exchange Online。有关分配 Exchange Online 中的权限的详细信息，请参阅[管理角色组成员](https://go.microsoft.com/fwlink/p/?linkid=692102)。您可能还创建自定义角色组、 Mail Recipients 角色分配，，然后添加需要在步骤 1 中运行脚本的成员。有关详细信息，请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="9e23e-p105">每次您在步骤 1 中，运行该脚本被创建一个新的远程 PowerShell 会话。因此，您可以使用向上所有远程 PowerShell 会话可供您。若要防止此发生，可以运行以下命令以断开活动远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="9e23e-123">有关详细信息，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).。</span><span class="sxs-lookup"><span data-stu-id="9e23e-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="9e23e-p106">该脚本包括最少的错误处理。脚本的主要用途是快速显示邮箱文件夹 Id 的列表或网站可用于在搜索查询语法中的内容搜索执行目标的集合的路径。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="9e23e-p107">本主题中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="9e23e-131">步骤 1： 运行脚本以获得邮箱或网站的文件夹的列表</span><span class="sxs-lookup"><span data-stu-id="9e23e-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="9e23e-p108">在此步骤中第一个运行的脚本将返回邮箱文件夹的列表或 SharePoint 或 OneDrive for Business 文件夹和相应文件夹 ID 或每个文件夹的路径。运行此脚本时，它将提示您输入以下信息。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="9e23e-p109">**电子邮件地址或网站 URL**键入要返回的 Exchange 邮箱文件夹列表并折叠 Id custodian 电子邮件地址。或键入 SharePoint 网站的 URL 或 OneDrive for Business 站点，可返回指定网站的路径的列表。下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="9e23e-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and fold IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="9e23e-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9e23e-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="9e23e-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="9e23e-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="9e23e-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="9e23e-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="9e23e-p110">**您的用户凭据**-脚本将使用您的凭据来连接到 Exchange Online 和安全&amp;使用远程 PowerShell 合规性中心。如前所述，您需要分配适当的权限，才能成功运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="9e23e-142">要显示的邮箱文件夹的列表或网站路径名称：</span><span class="sxs-lookup"><span data-stu-id="9e23e-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="9e23e-143">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="9e23e-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appeneded to the folder ID or path ID to use in a Content Search.              #
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
  # Authenticate with Exchange Online and the Security &amp; Complaince Center (Exchange Online Protection - EOP)
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
      # Authenticate with the Security &amp; Complaince Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the the script was aborted, the search we created might not have been deleted.  Try to do so now.
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
          # Create a Complinace Search Action and wait for it to complete. The folders will be listed in the .Results parameter
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
              Write-Host "path:""$rawUrl"""
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

2. <span data-ttu-id="9e23e-144">在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e23e-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="9e23e-145">运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="9e23e-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="9e23e-146">输入该脚本将提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="9e23e-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="9e23e-p111">该脚本显示邮箱文件夹或网站文件夹指定用户的列表。允许此窗口打开，以便可以复制文件夹 ID 或路径名称，并将其中粘贴到在步骤 2 中的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="9e23e-p112">而不是计算机屏幕上显示的文件夹的列表，您可以重定向到文本文件脚本的输出。此文件将保存到该脚本所在的文件夹。例如，若要重定向到文本文件输出的脚本，请运行以下命令在步骤 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` ，然后您可以从要搜索查询中使用的文件复制文件夹 ID 或路径。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="9e23e-152">邮箱文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="9e23e-152">Script output for mailbox folders</span></span>

<span data-ttu-id="9e23e-p113">如果您收到了邮箱文件夹 Id，该脚本将使用远程 PowerShell 连接到 Exchange Online、 运行**Get MailboxFolderStatisics** cmdlet，然后显示从指定的邮箱文件夹的列表。对于邮箱中每个文件夹，脚本**FolderPath**列和文件夹 ID 在**FolderQuery**列中显示的文件夹的名称。此外，该脚本将**文件夹 Id** （这是邮箱属性的名称） 的前缀添加到文件夹 id。由于**文件夹 id**属性是可搜索的属性，您可以使用`folderid:<folderid>`搜索查询在步骤 2 中搜索该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="9e23e-157">下面是一个示例返回邮箱文件夹的脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="9e23e-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![邮箱文件夹和文件夹脚本返回的 Id 的列表的示例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="9e23e-159">步骤 2 中的示例演示用于搜索用户的可恢复项目文件夹中的清除子文件夹的查询。</span><span class="sxs-lookup"><span data-stu-id="9e23e-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="9e23e-160">站点文件夹的脚本输出</span><span class="sxs-lookup"><span data-stu-id="9e23e-160">Script output for site folders</span></span>

<span data-ttu-id="9e23e-p114">如果您收到了路径从 SharePoint 或 OneDrive for Business 站点，该脚本将连接到安全性&amp;合规性中心，使用远程 PowerShell 创建新的内容搜索的搜索文件夹的网站，然后显示的文件夹的列表位于指定的网站。该脚本显示每个文件夹的名称，并将**路径**（它是网站属性的名称） 的前缀添加到文件夹的 URL。**Path**属性是一个可搜索的属性，因为您要使用`path:<path>`搜索查询在步骤 2 中搜索该文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="9e23e-164">下面是一个示例返回网站的文件夹的脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="9e23e-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![为网站返回脚本的文件夹的路径名称的列表的示例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="9e23e-166">步骤 2： 使用文件夹 ID 或路径执行目标的集合</span><span class="sxs-lookup"><span data-stu-id="9e23e-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="9e23e-p115">您已运行脚本以收集文件夹 Id 或特定用户的路径的列表后，下一步步骤以转到安全&amp;合规性中心并创建新的内容搜索来搜索特定文件夹。您可以使用`folderid:<folderid>`或`path:<path>`配置内容搜索关键字框中 （或作为*ContentMatchQuery*参数，如果您使用**新建 ComplianceSearch** cmdlet 的值） 在搜索查询的属性。可以组合`folderid`或`path`属性与其他搜索参数，或搜索条件。如果只包括`folderid`或`path`查询中的属性，搜索将返回位于指定文件夹中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9e23e-171">使用`path`属性来搜索 OneDrive 位置不会在搜索结果中返回媒体文件，如.png、.tiff 或.wav 文件。</span><span class="sxs-lookup"><span data-stu-id="9e23e-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="9e23e-172">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9e23e-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9e23e-173">登录到 Office 365 使用的帐户和用于在步骤 1 中运行脚本的凭据。</span><span class="sxs-lookup"><span data-stu-id="9e23e-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="9e23e-174">安全的左窗格中&amp;合规性中心，单击**搜索&amp;调查** \> **内容搜索**，然后单击**新建**和![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="9e23e-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="9e23e-p116">在**新的搜索**页上，键入内容的搜索的名称。此名称必须是唯一组织中。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="9e23e-177">在**希望在何处我们来看**，请执行以下一基于是否您搜索与邮箱文件夹或网站文件夹：</span><span class="sxs-lookup"><span data-stu-id="9e23e-177">Under **Where do you want us to look**, do one of the following, based on whether your searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="9e23e-178">单击**选择要搜索的特定邮箱**，然后添加指定您在步骤 1 中运行该脚本时的同一邮箱。</span><span class="sxs-lookup"><span data-stu-id="9e23e-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="9e23e-179">或者</span><span class="sxs-lookup"><span data-stu-id="9e23e-179">Or</span></span>
    
    - <span data-ttu-id="9e23e-180">单击**选择特定网站搜索**以搜索，然后添加您在步骤 1 中运行该脚本时指定的网站相同的 URL。</span><span class="sxs-lookup"><span data-stu-id="9e23e-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="9e23e-181">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="9e23e-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="9e23e-182">在**希望什么我们查找内容**页上的关键字框中，粘贴`folderid:<folderid>`或`path:<path>`步骤 1 中的脚本返回的值。</span><span class="sxs-lookup"><span data-stu-id="9e23e-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="9e23e-183">例如，下面的屏幕快照中的查询将搜索的用户的可恢复项目文件夹中的清除子文件夹中的任何项目 (的值`folderid`清除子文件夹属性在步骤 1 中的屏幕截图中所示):</span><span class="sxs-lookup"><span data-stu-id="9e23e-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![粘贴文件夹 id 或搜索查询的关键字框中的路径](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="9e23e-185">单击**搜索**以启动目标的集合搜索。</span><span class="sxs-lookup"><span data-stu-id="9e23e-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="9e23e-186">目标集合的搜索查询的示例</span><span class="sxs-lookup"><span data-stu-id="9e23e-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="9e23e-p117">下面是一些示例使用的`folderid`和`path`搜索查询执行目标的集合中的属性。请注意，占位符用于`folderid:<folderid>`和`path:<path>`以节省空间。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="9e23e-p118">本示例搜索三个不同的邮箱文件夹。您可以使用类似的查询语法搜索用户的可恢复项目文件夹中隐藏的文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="9e23e-191">本示例搜索包含准确的短语的项目与邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e23e-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="9e23e-192">本示例搜索包含字母"保密协议"标题中的文档的网站文件夹 （及其所有子）。</span><span class="sxs-lookup"><span data-stu-id="9e23e-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="9e23e-193">本示例搜索站点文件夹 （或任何子） 的文档存在已更改的日期范围内。</span><span class="sxs-lookup"><span data-stu-id="9e23e-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="9e23e-194">更多信息</span><span class="sxs-lookup"><span data-stu-id="9e23e-194">More information</span></span>

<span data-ttu-id="9e23e-195">使用本文中的脚本和执行目标集合时，请保留记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="9e23e-195">Keep the following things in mind when using the script in this article and performing targeted collections.</span></span>
  
- <span data-ttu-id="9e23e-p119">脚本不从结果中删除任何文件夹。因此有些文件夹中列出结果可能不可搜索 （或返回零项） 因为它们包含系统生成的内容。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="9e23e-p120">此脚本只返回用户的主邮箱文件夹信息。它不在用户的存档邮箱中返回有关文件夹的信息。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="9e23e-p121">在搜索邮箱文件夹，只有指定的文件夹时 (由其`folderid`属性) 将搜索。不会搜索子文件夹。若要搜索的子文件夹，您需要使用`folderid`，您想要搜索的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  `folderid` for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="9e23e-203">在搜索网站文件夹，该文件夹时 (由其`path`属性)，以及将搜索所有子文件夹。</span><span class="sxs-lookup"><span data-stu-id="9e23e-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="9e23e-p122">如前面所述，不能使用`path`属性对于媒体文件，如.png、.tiff 或.wav 文件，搜索位于 OneDrive 位置。使用不同的[站点属性](keyword-queries-and-search-conditions.md#searchable-site-properties)搜索 OneDrive 文件夹中的媒体文件。</span><span class="sxs-lookup"><span data-stu-id="9e23e-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 
