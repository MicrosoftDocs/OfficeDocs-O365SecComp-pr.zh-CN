---
title: 使用 Office 365 中的目标集合的内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: 在 Office 365 安全性中使用内容搜索&amp;合规性中心，以执行目标的集合。目标的集合表示您确信案例做出迅速响应项目或特权的项目位于特定邮箱或网站文件夹中。使用本文中脚本以获取文件夹 ID 或您要搜索的特定邮箱或网站文件夹的路径。
ms.openlocfilehash: 094fa4de4b8de9782a9bafb2eb8fb6ef3c52b46b
ms.sourcegitcommit: 06ae71741875f604bcc7a4e01b0b62cc768cbe97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27245059"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>使用 Office 365 中的目标集合的内容搜索

Office 365 安全性内容的搜索功能&amp;合规性中心没有提供在 UI 中的直接方法业务网站 Exchange 邮箱或 SharePoint 和 OneDrive 中搜索特定的文件夹。但是，就可以通过在实际的搜索查询语法指定的文件夹 ID 或路径来搜索特定的文件夹 （称为*目标集合*）。当您确信案例做出迅速响应项目或特权的项目位于特定邮箱或网站文件夹中，使用内容搜索执行目标的集合很有用。可以使用本文中的脚本来获取邮箱文件夹的文件夹 ID 或业务网站上的 SharePoint 和 OneDrive 文件夹的路径。然后您可以使用的文件夹 ID 或路径搜索查询中返回项目位于的文件夹中。
  
## <a name="before-you-begin"></a>准备工作

- 您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心在步骤 1 中运行脚本。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
    
    此外，您必须在 Exchange Online 组织中的 Mail Recipients 角色分配。这需要运行**Get-mailboxfolderstatistics** cmdlet，包括在步骤 1 中的脚本。默认情况下 Mail Recipients 角色分配给组织管理和 Recipient Management 角色组在 Exchange Online。有关分配 Exchange Online 中的权限的详细信息，请参阅[管理角色组成员](https://go.microsoft.com/fwlink/p/?linkid=692102)。您可能还创建自定义角色组、 Mail Recipients 角色分配，，然后添加需要在步骤 1 中运行脚本的成员。有关详细信息，请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。
    
- 每次您在步骤 1 中，运行该脚本被创建一个新的远程 PowerShell 会话。因此，您可以使用向上所有远程 PowerShell 会话可供您。若要防止此发生，可以运行以下命令以断开活动远程 PowerShell 会话。
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    有关详细信息，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).。
    
- 该脚本包括最少的错误处理。脚本的主要用途是快速显示邮箱文件夹 Id 的列表或网站可用于在搜索查询语法中的内容搜索执行目标的集合的路径。
    
- 本主题中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步骤 1： 运行脚本以获得邮箱或网站的文件夹的列表

在此步骤中第一个运行的脚本将返回邮箱文件夹的列表或 SharePoint 或 OneDrive for Business 文件夹和相应文件夹 ID 或每个文件夹的路径。运行此脚本时，它将提示您输入以下信息。
  
- **电子邮件地址或网站 URL**键入 custodian 返回 Exchange 邮箱文件夹和文件夹 Id 的列表的电子邮件地址。或键入 SharePoint 网站的 URL 或 OneDrive for Business 站点，可返回指定网站的路径的列表。下面是一些示例： 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **您的用户凭据**-脚本将使用您的凭据来连接到 Exchange Online 和安全&amp;使用远程 PowerShell 合规性中心。如前所述，您需要分配适当的权限，才能成功运行此脚本。
    
要显示的邮箱文件夹的列表或网站路径名称：
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `GetFolderSearchParameters.ps1`。
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appended to the folder ID or path ID to use in a Content Search.               #
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

2. 在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。
    
3. 运行脚本。例如：
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. 输入该脚本将提示您输入的信息。
    
    该脚本显示邮箱文件夹或网站文件夹指定用户的列表。允许此窗口打开，以便可以复制文件夹 ID 或路径名称，并将其中粘贴到在步骤 2 中的搜索查询。
    
    > [!TIP]
    > 而不是计算机屏幕上显示的文件夹的列表，您可以重定向到文本文件脚本的输出。此文件将保存到该脚本所在的文件夹。例如，若要重定向到文本文件输出的脚本，请运行以下命令在步骤 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` ，然后您可以从要搜索查询中使用的文件复制文件夹 ID 或路径。
  
### <a name="script-output-for-mailbox-folders"></a>邮箱文件夹的脚本输出

如果您收到了邮箱文件夹 Id，该脚本将使用远程 PowerShell 连接到 Exchange Online、 运行**Get MailboxFolderStatisics** cmdlet，然后显示从指定的邮箱文件夹的列表。对于邮箱中每个文件夹，脚本**FolderPath**列和文件夹 ID 在**FolderQuery**列中显示的文件夹的名称。此外，该脚本将**文件夹 Id** （这是邮箱属性的名称） 的前缀添加到文件夹 id。由于**文件夹 id**属性是可搜索的属性，您可以使用`folderid:<folderid>`搜索查询在步骤 2 中搜索该文件夹中。 
  
下面是一个示例返回邮箱文件夹的脚本的输出。
  
![邮箱文件夹和文件夹脚本返回的 Id 的列表的示例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步骤 2 中的示例演示用于搜索用户的可恢复项目文件夹中的清除子文件夹的查询。
  
### <a name="script-output-for-site-folders"></a>站点文件夹的脚本输出

如果您收到了路径从 SharePoint 或 OneDrive for Business 站点，该脚本将连接到安全性&amp;合规性中心，使用远程 PowerShell 创建新的内容搜索的搜索文件夹的网站，然后显示的文件夹的列表位于指定的网站。该脚本显示每个文件夹的名称，并将**路径**（它是网站属性的名称） 的前缀添加到文件夹的 URL。**Path**属性是一个可搜索的属性，因为您要使用`path:<path>`搜索查询在步骤 2 中搜索该文件夹中。 
  
下面是一个示例返回网站的文件夹的脚本的输出。
  
![为网站返回脚本的文件夹的路径名称的列表的示例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>步骤 2： 使用文件夹 ID 或路径执行目标的集合

您已运行脚本以收集文件夹 Id 或特定用户的路径的列表后，下一步步骤以转到安全&amp;合规性中心并创建新的内容搜索来搜索特定文件夹。您可以使用`folderid:<folderid>`或`path:<path>`配置内容搜索关键字框中 （或作为*ContentMatchQuery*参数，如果您使用**新建 ComplianceSearch** cmdlet 的值） 在搜索查询的属性。可以组合`folderid`或`path`属性与其他搜索参数，或搜索条件。如果只包括`folderid`或`path`查询中的属性，搜索将返回位于指定文件夹中的所有项目。 
  
> [!NOTE]
> 使用`path`属性来搜索 OneDrive 位置不会在搜索结果中返回媒体文件，如.png、.tiff 或.wav 文件。 
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用的帐户和用于在步骤 1 中运行脚本的凭据。
    
3. 安全的左窗格中&amp;合规性中心，单击**搜索&amp;调查** \> **内容搜索**，然后单击**新建**和![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
4. 在**新的搜索**页上，键入内容的搜索的名称。此名称必须是唯一组织中。 
    
5. 在**希望在何处我们来看**，请执行以下一基于您是否搜索邮箱文件夹或网站文件夹：
    
    - 单击**选择要搜索的特定邮箱**，然后添加指定您在步骤 1 中运行该脚本时的同一邮箱。 
    
      或
    
    - 单击**选择特定网站搜索**以搜索，然后添加您在步骤 1 中运行该脚本时指定的网站相同的 URL。 
    
6. 单击"下一步"。
    
7. 在**希望什么我们查找内容**页上的关键字框中，粘贴`folderid:<folderid>`或`path:<path>`步骤 1 中的脚本返回的值。 
    
    例如，下面的屏幕快照中的查询将搜索的用户的可恢复项目文件夹中的清除子文件夹中的任何项目 (的值`folderid`清除子文件夹属性在步骤 1 中的屏幕截图中所示):
    
    ![粘贴文件夹 id 或搜索查询的关键字框中的路径](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 单击**搜索**以启动目标的集合搜索。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>目标集合的搜索查询的示例

下面是一些示例使用的`folderid`和`path`搜索查询执行目标的集合中的属性。请注意，占位符用于`folderid:<folderid>`和`path:<path>`以节省空间。 
  
- 本示例搜索三个不同的邮箱文件夹。您可以使用类似的查询语法搜索用户的可恢复项目文件夹中隐藏的文件夹。
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本示例搜索包含准确的短语的项目与邮箱文件夹。
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本示例搜索包含字母"保密协议"标题中的文档的网站文件夹 （及其所有子）。
    
  ```
  path:<path> AND filename:nda
  ```

- 本示例搜索站点文件夹 （或任何子） 的文档存在已更改的日期范围内。
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>更多信息

使用本文中的脚本来执行目标的集合时，请记住以下事项。
  
- 脚本不从结果中删除任何文件夹。因此有些文件夹中列出结果可能不可搜索 （或返回零项） 因为它们包含系统生成的内容。
    
- 此脚本只返回用户的主邮箱文件夹信息。它不在用户的存档邮箱中返回有关文件夹的信息。
    
- 在搜索邮箱文件夹，只有指定的文件夹时 (由其`folderid`属性) 将搜索。不会搜索子文件夹。若要搜索的子文件夹，您需要文件夹 ID 用于要搜索的子文件夹。 
    
- 在搜索网站文件夹，该文件夹时 (由其`path`属性)，以及将搜索所有子文件夹。 
    
- 如前面所述，不能使用`path`属性对于媒体文件，如.png、.tiff 或.wav 文件，搜索位于 OneDrive 位置。使用不同的[站点属性](keyword-queries-and-search-conditions.md#searchable-site-properties)搜索 OneDrive 文件夹中的媒体文件。 

- 导出的顺序您仅指定的搜索结果时`folderid`中搜索查询的属性，您可以选择首次导出选项，"所有项目，但不包括那些具有无法识别的格式，进行加密，或出于其他原因无法编制索引。"始终将被文件夹中的所有项目都导出无论其索引状态，因为文件夹 ID 始终编制索引。
