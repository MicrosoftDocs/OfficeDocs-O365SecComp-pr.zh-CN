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
description: 在 Office 365 安全&amp;合规中心中使用内容搜索来执行目标集合。 目标集合意味着您确信项目响应的是事例或特权项目位于特定的邮箱或站点文件夹中。 使用本文中的脚本获取要搜索的特定邮箱或网站文件夹的文件夹 ID 或路径。
ms.openlocfilehash: 4cfdb95ef65f94bc46b79265f986ed8d9ada04da
ms.sourcegitcommit: c0d4fe3e43e22353f30034567ade28330266bcf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899992"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>将 Office 365 中的内容搜索用于目标集合

Office 365 安全&amp;合规中心中的内容搜索功能不会在 UI 中直接提供用于搜索 Exchange 邮箱或 SharePoint 和 OneDrive for business 网站中特定文件夹的直接方法。 但是, 通过为实际搜索查询语法中的网站的电子邮件或路径 (DocumentLink) 属性指定文件夹 ID 属性, 可以搜索特定文件夹 (称为*目标集合*)。 当您确信项目响应的情况或特权项目位于特定邮箱或站点文件夹中时, 使用内容搜索来执行目标集合非常有用。 您可以使用本文中的脚本获取邮箱文件夹的文件夹 ID 或 SharePoint 和 OneDrive for business 网站上的文件夹的路径 (DocumentLink)。 然后, 您可以在搜索查询中使用文件夹 ID 或路径返回文件夹中的项目。

> [!NOTE]
> 若要返回位于 SharePoint 或 OneDrive for business 网站中的文件夹中的内容, 本主题中的脚本使用 DocumentLink 托管属性而不是 Path 属性。 DocumentLink 属性比 Path 属性更可靠, 因为它将返回文件夹中的所有内容, 而 Path 属性将不会返回某些媒体文件。

## <a name="before-you-begin"></a>准备工作

- 您必须是安全&amp;合规中心中的电子数据展示管理器角色组的成员, 才能在第1步中运行该脚本。 有关详细信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
    此外, 还必须在 Exchange Online 组织中为 "邮件收件人" 角色分配。 这是运行**get-mailboxfolderstatistics** cmdlet (包含在步骤1中的脚本中) 所必需的。 默认情况下, 将 "邮件收件人" 角色分配给 Exchange Online 中的 "组织管理" 和 "收件人管理" 角色组。 有关在 Exchange Online 中分配权限的详细信息, 请参阅[Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102)。 您还可以创建自定义角色组, 将 "邮件收件人" 角色分配给该角色组, 然后添加需要在步骤1中运行该脚本的成员。 有关详细信息, 请参阅[管理角色组](https://go.microsoft.com/fwlink/p/?linkid=730688)。
    
- 每次在第1步中运行脚本时, 都会创建一个新的远程 PowerShell 会话。 因此, 你可以使用所有可供你使用的远程 PowerShell 会话。 若要防止这种情况发生, 可以运行以下命令来断开活动的远程 PowerShell 会话。
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)。
    
- 该脚本包括最少的错误处理。 脚本的主要用途是快速显示邮箱文件夹 id 或网站路径的列表, 该列表可用于内容搜索的搜索查询语法以执行目标集合。
    
- 在任何 Microsoft standard 支持计划或服务下, 本主题中提供的示例脚本不受支持。 示例脚本按原样提供, 而不提供任何种类的担保。 Microsoft 也不提供任何默示担保，包括但不仅限于对适销性或针对特定目的的适用性的默示担保。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 对于因使用或无法使用示例脚本或文档产生的任何损害（包括但不仅限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者以及参与脚本创建、生成或交付的任何人均不承担任何责任，即使 Microsoft 已被告知此类损害的可能性也是如此。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>步骤 1: 运行脚本以获取邮箱或网站的文件夹列表

您在此第一步中运行的脚本将返回邮箱文件夹或 SharePoint 和 OneDrive for business 文件夹的列表, 以及每个文件夹对应的文件夹 ID 或路径。 运行此脚本时, 它将提示您提供以下信息。
  
- **电子邮件地址或网站 URL**键入保管人的电子邮件地址, 以返回 Exchange 邮箱文件夹和文件夹 id 的列表。 或者键入 SharePoint 网站或 OneDrive for business 网站的 URL, 以返回指定网站的路径列表。 下面是一些示例： 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **你的用户凭据**-脚本将使用你的凭据连接到 Exchange Online 和与远程&amp; PowerShell 的安全合规性中心。 如前面所述, 您必须分配适当的权限才能成功运行此脚本。
    
若要显示邮箱文件夹或网站 documentlink (路径) 名称的列表, 请执行以下操作:
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `GetFolderSearchParameters.ps1`。
    
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

2. 在本地计算机上, 打开 Windows PowerShell 并转到保存该脚本的文件夹。
    
3. 运行脚本;例如:
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. 输入脚本提示您输入的信息。
    
    该脚本将显示指定用户的邮箱文件夹或网站文件夹的列表。 让此窗口打开, 以便您可以复制文件夹 ID 或 documentlink 名称, 并将其粘贴到第2步中的搜索查询中。
    
    > [!TIP]
    > 您可以将脚本的输出重新定向到文本文件, 而不是在计算机屏幕上显示文件夹的列表。 此文件将保存到脚本所在的文件夹中。 例如, 若要将脚本输出重定向到文本文件, 请在第3步中运行以下命令`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` : 然后, 可以从要在搜索查询中使用的文件中复制文件夹 ID 或 documentlink。
  
### <a name="script-output-for-mailbox-folders"></a>邮箱文件夹的脚本输出

如果你获取的是邮箱文件夹 id, 脚本将使用远程 PowerShell 连接到 Exchange Online, 运行**MailboxFolderStatisics** cmdlet, 然后显示指定邮箱中的文件夹列表。 对于邮箱中的每个文件夹, 该脚本都会在 " **FolderPath** " 列中显示文件夹的名称, 并在 " **FolderQuery** " 列中显示文件夹 ID。 此外, 该脚本还会将**folderId**的前缀 (即邮箱属性的名称) 添加到文件夹 ID。 由于**folderid**属性是一个可搜索的属性, 因此您`folderid:<folderid>`将在步骤2中的搜索查询中使用搜索该文件夹。 

> [!IMPORTANT]
> 本文中的脚本包含编码逻辑, 用于将**get-mailboxfolderstatistics**返回的64字符文件夹 Id 值转换为与为搜索编制索引的相同48字符格式。 如果您仅在 PowerShell 中运行**get-mailboxfolderstatistics** cmdlet 以获取文件夹 id (而不是在本文中运行脚本), 则使用该文件夹 id 值的搜索查询将失败。 您必须运行脚本才能获取可在内容搜索中使用的格式正确的文件夹 id。
  
下面的示例展示了邮箱文件夹的脚本返回的输出。
  
![脚本返回的邮箱文件夹和文件夹 id 列表的示例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
步骤2中的示例显示了用于在用户的 "可恢复的项目" 文件夹中搜索 "清除" 子文件夹的查询。
  
### <a name="script-output-for-site-folders"></a>网站文件夹的脚本输出

如果从 SharePoint 或 OneDrive for business 网站获取**documentlink**属性的路径, 则脚本将使用远程 PowerShell 连接到安全 & 合规中心, 并创建一个新的内容搜索, 以搜索网站中的文件夹。, 然后显示位于指定网站中的文件夹的列表。 该脚本将显示每个文件夹的名称, 并将**documentlink**的前缀添加到文件夹 URL 中。 由于**documentlink**属性是一个可搜索的属性, 因此您`documentlink:<path>`将在步骤2中的搜索查询中使用属性: value 对来搜索该文件夹。 
  
下面的示例展示了网站文件夹的脚本返回的输出。
  
![脚本返回的网站文件夹的 documentlink 名称列表示例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>步骤 2: 使用文件夹 ID 或 documentlink 执行目标集合

在运行脚本以收集特定用户的文件夹 id 或 documentlinks 的列表后, 下一步是转到 Security & 合规中心, 并创建新的内容搜索以搜索特定文件夹。 您将在 " `folderid:<folderid>`内容`documentlink:<path>`搜索关键字" 框中配置的搜索查询中使用或 "属性: 值" 对 (如果使用**new-compliancesearch** cmdlet, 则为*ContentMatchQuery*参数的值)。 您可以将`folderid`或`documentlink`属性与其他搜索参数或搜索条件结合使用。 如果只在查询中`folderid`包括`documentlink`或属性, 则搜索将返回位于指定文件夹中的所有项目。 
  
1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com)。
    
2. 使用在步骤1中运行脚本时使用的帐户和凭据登录 Office 365。
    
3. 在安全 & 合规性中心的左侧窗格中, 单击 "**搜索** \> **内容搜索**", 然后单击 "**新建** ![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)"。
    
4. 在“新建搜索”**** 页上，键入内容搜索的名称。 此名称在组织中必须是唯一的。 
    
5. 在 "**您希望我们在哪里进行查找**" 下, 根据您搜索的是邮箱文件夹还是站点文件夹, 执行下列操作之一:
    
    - 单击 "**选择要搜索的特定邮箱**", 然后添加您在步骤1中运行脚本时指定的相同邮箱。 
    
      或者
    
    - 单击 "**选择要搜索的特定网站**" 搜索, 然后添加在步骤1中运行脚本时指定的相同网站 URL。 
    
6. 单击“下一步”。****
    
7. 在 "**您希望我们在什么情况下查找**" 页上的 "关键字" 框`folderid:<folderid>`中`documentlink:<path>` , 粘贴步骤1中的脚本返回的 or 值。 
    
    例如, 下面的屏幕截图中的查询将搜索用户的 "可恢复项目" 文件夹中的 "清除" 子文件夹中的任何项目`folderid` ("清除" 子文件夹的属性值显示在步骤1中的屏幕截图中):
    
    ![将 folderid 或 documentlink 粘贴到搜索查询的关键字框中](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 单击 "**搜索**" 以启动目标集合搜索。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>目标集合的搜索查询示例

下面是在搜索查询中使用`folderid`和`documentlink`属性执行目标集合的一些示例。 请注意, 占位符用于`folderid:<folderid>` `documentlink:<path>`节省空间。 
  
- 本示例将搜索三个不同的邮箱文件夹。 可以使用类似的查询语法搜索用户的 "可恢复的项目" 文件夹中的隐藏文件夹。
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- 本示例将在邮箱文件夹中搜索包含精确短语的项目。
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- 本示例在标题中搜索包含字母 "NDA" 的文档的网站文件夹 (和任何子文件夹)。
    
  ```
  documentlink:<path> AND filename:nda
  ```

- 本示例搜索某个日期范围内已更改的文档的网站文件夹 (和任何子文件夹)。
    
  ```
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>详细信息

在使用本文中的脚本执行目标集合时, 请记住以下事项。
  
- 脚本不会从结果中删除任何文件夹。 因此, 结果中列出的某些文件夹可能是不可搜索的 (或返回零个项目), 因为它们包含系统生成的内容。
    
- 此脚本仅返回用户的主邮箱的文件夹信息。 它不会返回有关用户存档邮箱中的文件夹的信息。
    
- 搜索邮箱文件夹时, 将仅搜索指定的文件夹 (由`folderid`其属性标识);不搜索子文件夹。 若要搜索子文件夹, 您需要使用要搜索的子文件夹的文件夹 ID。 
    
- 搜索站点文件夹时, 将搜索文件夹 (由其`documentlink`属性标识) 和所有子文件夹。 
    
- 当您在搜索查询中导出仅指定`folderid`属性的搜索结果时, 可以选择第一个导出选项 "。所有项目 (不包括具有不可识别的格式的项目) 已加密, 或未对其他原因编制索引。 将始终导出文件夹中的所有项目 (无论其索引状态如何), 因为文件夹 ID 始终编制索引。
