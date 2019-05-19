---
title: 在电子数据展示工作流中使用内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 脚本在 Exchange Online 中创建基于 Security & 合规性中心中创建的搜索的就地电子数据展示搜索。 '
ms.openlocfilehash: d021836a735d5c5dd12124e16e348729d88e6022
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157974"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>在电子数据展示工作流中使用内容搜索

通过 Security & 合规性中心中的内容搜索功能, 可以搜索组织中的所有邮箱。 与 Exchange Online 中的就地电子数据展示不同 (最多可以搜索10000个邮箱), 对单个搜索中的目标邮箱数没有限制。 对于需要您执行组织范围内搜索的方案，可以使用内容搜索来搜索所有邮箱。 然后, 您可以使用就地电子数据展示的工作流功能执行其他与电子数据展示相关的任务, 如将邮箱置于保留状态并导出搜索结果。 例如，假设您需要搜索所有邮箱以确定可以响应某法律案件的特定监护人。 您可以使用 Security & 合规中心中的内容搜索来搜索组织中的所有邮箱, 以确定那些对案例有响应的邮箱。 然后, 可以将该保管人邮箱列表用作 Exchange Online 中的就地电子数据展示搜索的源邮箱。 使用就地电子数据展示还允许您对这些源邮箱进行保留, 将搜索结果复制到发现邮箱, 并导出搜索结果。
  
本主题包含一个脚本, 可运行此脚本在 Exchange Online 中创建就地电子数据展示搜索, 具体方法是使用安全 & 合规性中心中创建的搜索中的源邮箱和搜索查询的列表。 以下是过程概述：
  
[步骤 1：创建内容搜索来搜索组织中的所有邮箱](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[步骤 2: 在单个远程 PowerShell \&会话中连接到安全合规性中心和 Exchange Online](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[Step 4: Start the In-Place eDiscovery search](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>步骤 1：创建内容搜索来搜索组织中的所有邮箱

第一步是使用安全 & 合规性中心 (或 Security & 合规性中心 PowerShell) 来创建搜索组织中所有邮箱的内容搜索。 对于单个内容搜索的邮箱数没有限制。 指定适当的关键字查询（或针对敏感信息类型的查询），以便搜索仅返回与您的调查相关的源邮箱。 如有必要，优化搜索查询来缩小返回的搜索结果以及源邮箱的范围。
  
> [!NOTE]
> 如果源内容搜索未返回任何结果，则当您在步骤 3 中运行该脚本时不会创建就地电子数据展示。您可能必须修改搜索查询然后重新运行内容搜索来返回搜索结果。 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a>使用安全与合规中心来搜索所有邮箱

1. [转到安全 _AMP_ 合规中心](go-to-the-securitycompliance-center.md)。 
    
2. 单击 "**搜索** > **内容搜索**", 然后单击 "**新建搜索** ![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)"。
    
3. 在“新建搜索”**** 页上，键入内容搜索的名称。 
    
4. 在****“您想要我们查找什么位置？”下，单击“搜索所有邮箱”****，然后单击“下一步”****。
    
5. 在“您想要我们查找哪些内容”**** 下的框中，键入搜索查询。 您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。 您可以使用更复杂的查询 (如 AND、OR、NOT 或 NEAR), 也可以在邮件中搜索敏感信息 (如社会保险号)。 有关创建搜索查询的详细信息，请参阅[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。
    
6. 单击****“搜索”保存搜索设置，然后启动搜索。 
    
    一段时间后, 在详细信息窗格中显示搜索结果的估计值。 估计值包括搜索结果的总大小和项目数。 完成搜索后，您可以预览搜索结果。 如有必要, ****![请单击 "](media/O365-MDM-Policy-RefreshIcon.gif)刷新刷新" 图标以更新详细信息窗格中的信息。 
    
7.  如有必要，请优化搜索查询以缩小搜索结果的范围，然后重新启动搜索。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>使用 Security & 合规性中心 PowerShell 搜索所有邮箱

您还可以使用 **New-ComplianceSearch** cmdlet 搜索组织中的所有邮箱。 第一步是[连接到安全 _AMP_ 合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
下面的示例展示了如何使用 PowerShell 搜索组织中的所有邮箱。 搜索查询将返回 2015 年 1 月 1 日和 2015 年 6 月 30 日之间发送的以及主题行中包含短语“财务报告”的所有邮件。 第一个命令创建搜索，第二个命令运行搜索。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

有关详细信息，请参阅 [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>验证内容搜索中的源邮箱数

内容搜索返回的最大值为1000个包含搜索结果的源邮箱。 如果包含与搜索查询匹配的内容的邮箱多于1000个, 则在上一步中创建的内容搜索中仅包含最上面包含最多搜索结果的前1000个邮箱。 因此, 如果超过1000个邮箱包含搜索结果, 则其中一些邮箱将不会包括在复制到在步骤3中创建的新就地电子数据展示搜索的源邮箱列表中。 
  
若要帮助您创建不超过1000源邮箱的内容搜索, 请按照以下步骤操作, 以运行一个显示您在步骤1中创建的内容搜索所返回的源邮箱数 (包含搜索结果) 的脚本。 
  
1. 使用文件名后缀. ps1 将以下文本保存到 PowerShell 脚本文件中。 例如, 可以将其保存到名为`SourceMailboxes.ps1`的文件中。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
                  "Please wait until the search finishes.";
                  break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
                  "The Content Search " + $SearchName + " didn't return any useful results.";
                  break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  "Number of mailboxes that have search hits: " + $mailboxes.Count
  ```

2. 在 Security & 合规性中心 PowerShell 中, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:
    
    ```
    .\SourceMailboxes.ps1
    ```

3. 当脚本提示时，请键入您在步骤 1 中创建的内容搜索的名称。
    
    该脚本会显示包含搜索结果的源邮箱数。
    
如果源邮箱多于1000个, 请尝试创建两个或更多的内容搜索。 例如，在一个内容搜索中搜索组织中一半的邮箱，在另一个内容搜索中搜索组织中的另一半邮箱。 您还可以更改搜索条件以减少包含搜索结果的邮箱数。 例如, 可以包括日期范围或精炼关键字查询。
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>步骤 2: 在单个远程 PowerShell \&会话中连接到安全合规性中心和 Exchange Online

下一步是将 Windows PowerShell 连接到安全 & 合规中心和 Exchange Online 组织。 这是必要的, 因为您在步骤3中运行的脚本需要访问安全 & 合规性中心中的内容搜索 cmdlet 和 Exchange Online 中的就地电子数据展示 cmdlet。
  
1. 使用 .ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本文件。 例如, 可以将其保存到名为`ConnectEXO-CC.ps1`的文件中。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 在本地计算机上, 打开 Windows PowerShell, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:
    
    ```
    .\ConnectEXO-CC.ps1
    ```

您如何知道这是否有效？ 运行该脚本后, 安全 & 合规中心和 Exchange Online 中的 cmdlet 将导入到您的本地 PowerShell 会话中。 如果未收到任何错误，说明连接成功。 快速测试是运行安全 & 合规性中心 cmdlet (例如, **UnifiedCompliancePrerequisite** ) 和 Exchange Online cmdlet (如**Get 邮箱**)。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索

在步骤2中创建双 PowerShell 会话之后, 下一步是运行脚本, 将现有内容搜索转换为就地电子数据展示搜索。 下面是脚本的用途：
  
- 提示您输入要转换的内容搜索的名称。
    
- 验证内容搜索是否已完成运行。如果内容搜索未返回任何结果，将不会创建就地电子数据展示。
    
- 将内容搜索中包含搜索结果的源邮箱列表保存为一个变量。
    
- 使用以下属性创建新的就地电子数据展示搜索。请注意，新的搜索未启动。您将在步骤 4 中启动该搜索。
    
  - **Name** -新搜索的名称使用以下格式: \<内容搜索\>_MBSearch1 的名称。 如果再次运行脚本并使用相同的源内容搜索, 则搜索将命名\<为内容搜索\>_MBSearch2 的名称。
    
  - **源邮箱**-包含搜索结果的内容搜索中的所有邮箱。 
    
  - **搜索查询**-新搜索将使用内容搜索中的搜索查询。 如果内容搜索中包括所有内容（其中搜索查询为空），则新搜索也将会有空的搜索查询并将包含源邮箱中找到的所有内容。 
    
  - **仅估计搜索**-新搜索被标记为 "仅估计" 搜索。 启动后，它不会将搜索结果复制到发现邮箱。 
    
1. 使用 ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本文件。 例如, 可以将其保存到名为`CreateMBSearchFromComplianceSearch.ps1`的文件中。
    
  ```
  [CmdletBinding()]
  Param(
      [Parameter(Mandatory=$True,Position=1)]
      [string]$SearchName,
      [switch]$original,
      [switch]$restoreOriginal
  )
  $search = Get-ComplianceSearch $SearchName
  if ($search.Status -ne "Completed")
  {
    "Please wait until the search finishes";
    break;
  }
  $results = $search.SuccessResults;
  if (($search.Items -le 0) -or ([string]::IsNullOrWhiteSpace($results)))
  {
    "The Content Search " + $SearchName + " didn't return any useful results";
    "A mailbox search object wasn't created";
    break;
  }
  $mailboxes = @();
  $lines = $results -split '[\r\n]+';
  foreach ($line in $lines)
  {
      if ($line -match 'Location: (\S+),.+Item count: (\d+)' -and $matches[2] -gt 0)
      {
          $mailboxes += $matches[1];
      }
  }
  $msPrefix = $SearchName + "_MBSearch";
  $I = 1;
  $mbSearches = Get-MailboxSearch;
  while ($true)
  {
      $found = $false;
      $mbsName = "$msPrefix$I";
      foreach ($mbs in $mbSearches)
      {
          if ($mbs.Name -eq $mbsName)
          {
              $found = $true;
              break;
          }
      }
      if (!$found)
      {
          break;
      }
      $I++;
  }
  $query = $search.KeywordQuery;
  if ([string]::IsNullOrWhiteSpace($query))
  {
      $query = $search.ContentMatchQuery;
  }
  if ([string]::IsNullOrWhiteSpace($query))
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -EstimateOnly;
  }
  else
  {
    New-MailboxSearch "$msPrefix$i" -SourceMailboxes $mailboxes -SearchQuery $query -EstimateOnly;
  }
  
  ```

2. 在您在步骤2中创建的 Windows PowerShell 会话中, 转到在上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. 当脚本提示时, 键入要转换为就地电子数据展示搜索的内容搜索的名称 (例如, 在步骤1中创建的搜索), 然后按**enter**。
    
    如果脚本成功，将创建新的就地电子数据展示搜索，状态为 **NotStarted**。 运行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以显示新搜索的属性。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>步骤 4：启动就地电子数据展示搜索

您在步骤 3 中运行的脚本将创建一个新的就地电子数据展示搜索，但不会启动该搜索。下一步是启动该搜索，以便您可以获取搜索结果的估计值。
  
1. 在 Exchange 管理中心 (EAC) 中, 转到 "**合规性管理** \> **就地电子数据&amp;展示保留**"。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。
    
3. 单击 "**搜索** ![搜索](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> " 图标 "**估计搜索结果**" 以启动搜索并返回由搜索返回的总大小和项目数的估计值。 
    
    估计值显示在详细信息窗格中。 单击 "**刷新** ![刷新](media/O365-MDM-Policy-RefreshIcon.gif) " 图标以更新详细信息窗格中显示的信息。 
    
4. 若要在完成搜索后预览结果，请单击**** 详细信息窗格中的“预览搜索结果”。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>创建和运行就地电子数据展示搜索后接下来的步骤

创建并启动由步骤 3 中的脚本创建的就地电子数据展示搜索后，您可以使用普通的就地电子数据展示工作流对搜索结果执行不同的电子数据展示操作。
  
### <a name="create-an-in-place-hold"></a>创建就地保留

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中, 选择您在步骤3中创建的就地电子数据展示搜索, 然后单击 "**编辑** ![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)"。
    
3. 在“就地保留”**** 页面上，选中“将与所选邮箱中的搜索查询匹配的内容置于保留状态”**** 复选框，然后选择以下选项之一： 
    
  - **无限期保留**-选择此选项可将搜索返回的项目放置在无限期保留中。 保留的项目将会保持，直到您从搜索中删除邮箱或删除搜索。 
    
  - **指定相对于接收日期保留项目的天数**-选择此选项可保留特定时段内的项目。 持续时间从接收或创建邮箱项目的日期开始计算。 
    
4. 单击****“保存”创建就地保留并重新启动搜索。 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>复制搜索结果

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。
    
3. 单击 "**搜索** ![搜索](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)" 图标, 然后从下拉列表中单击 "**复制搜索结果**"。 
    
4. 在“复制搜索结果”**** 中，从以下选项中进行选择：
    
    - **包含不可搜索项**-选中此复选框可包含无法搜索的邮箱项目 (例如, 包含无法由 Exchange 搜索编制索引的文件类型附件的邮件)。 
    
    - **启用重复数据**删除-选中此复选框以排除重复的邮件。 仅有邮件的单个实例将被复制到发现邮箱。 
    
    - **启用完整日志记录**-选中此复选框可在搜索结果中包含完整日志。 
    
    - **完成该副本后发送邮件**-选中此复选框可在搜索完成后收到电子邮件通知。 
    
    - **将结果复制到此发现邮箱**-单击 "**浏览**" 以选择要将搜索结果复制到其中的发现邮箱。 
    
5. 单击“复制”**** 开始将搜索结果复制到指定发现邮箱的过程。 
    
6. 单击 "**刷新** ![刷新](media/O365-MDM-Policy-RefreshIcon.gif) " 图标以更新有关在详细信息窗格中显示的复制状态的信息。 
    
7. 复制完成后，单击“打开”**** 打开发现邮箱查看搜索结果。 
  
### <a name="export-the-search-results"></a>导出搜索结果

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索，然后单击“导出到 PST 文件”****。
    
3. 在“电子数据展示 PST 导出工具”**** 窗口中，执行以下操作： 
    
    - 单击“浏览”**** 指定要下载 PST 文件的位置。 
    
    - Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file. 
    
    - Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file. 
    
4. 单击“开始”**** 将搜索结果导出到 PST 文件。 
    
    将显示一个窗口，其中包含有关导出过程的状态信息。
