---
title: 在电子数据展示工作流中使用内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 脚本来在 Exchange Online 中基于在 Office 365 安全性中创建搜索创建就地电子数据展示搜索&amp;合规性中心。 '
ms.openlocfilehash: 42af94ce850736dede52e619c240bb9e0a6f7031
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038065"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a>在电子数据展示工作流中使用内容搜索

Office 365 安全性内容的搜索功能&amp;合规性中心允许您搜索您的组织中的所有邮箱。与 Exchange Online （其中可以搜索最多 10,000 个邮箱） 中的就地电子数据展示，不同有的单个搜索中的目标邮箱数量没有限制。对于需要执行组织范围内搜索的方案，您可以使用内容搜索搜索所有邮箱。然后您可以使用就地电子数据展示的工作流功能执行其他电子数据展示相关的任务，如上的放置邮箱保留和导出搜索结果。例如，假设您需要搜索所有邮箱标识特定响应法律案件的管理员。您可以使用中的安全的内容搜索&amp;合规性中心，以确定响应大小写的那些贵组织中的搜索所有邮箱。然后可以使用 custodian 邮箱的列表为源邮箱的 Exchange Online 中的就地电子数据展示搜索。使用就地电子数据展示还允许这些源邮箱置于保留、 将搜索结果复制到发现邮箱，并将搜索结果导出。
  
本主题包含脚本，您可以运行在 Exchange Online 中使用的源邮箱和搜索查询从搜索中安全创建列表创建就地电子数据展示搜索&amp;合规性中心。下面是过程概述：
  
[步骤 1：创建内容搜索来搜索组织中的所有邮箱](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[步骤 2： 连接到安全性&amp;合规性中心和 Exchange Online 中的单个的远程 PowerShell 会话](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[步骤 4：启动就地电子数据展示搜索](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a>步骤 1：创建内容搜索来搜索组织中的所有邮箱

第一步是使用安全&amp;合规性中心 （或安全与合规性中心 PowerShell） 创建在您的组织中搜索所有邮箱的内容搜索。没有为单一内容搜索的邮箱数的限制。指定相应的关键字查询 （或敏感信息类型的查询），以便搜索返回与调查相关这些源邮箱。如有必要，优化搜索查询来缩小搜索结果以及返回的源邮箱的范围。
  
> [!NOTE]
> 如果源内容搜索未返回任何结果，则当您在步骤 3 中运行该脚本时不会创建就地电子数据展示。您可能必须修改搜索查询然后重新运行内容搜索来返回搜索结果。 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a>使用安全&amp;合规性中心搜索所有邮箱

1. [转到 Office 365 安全性&amp;合规性中心](go-to-the-securitycompliance-center.md)。 
    
2. 单击**搜索&amp;调查**，单击**内容搜索**，然后单击**新建**![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
3. 在**新的搜索**页上，键入内容的搜索的名称。 
    
4. 在**您其中是否要查找我们？**，单击**搜索所有邮箱**，然后单击**下一步**。
    
5. 在下框**希望什么我们查找？**，在框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用更复杂的查询不使用布尔运算符，例如 AND、 OR 或 NEAR，或者您还可以搜索在邮件中的敏感信息 （如社会保险号码）。有关创建搜索查询的详细信息，请参阅[内容搜索的关键字查询](keyword-queries-and-search-conditions.md)。
    
6. 单击**搜索**以保存的搜索设置并开始搜索。 
    
    一段时间之后, 所估计的搜索结果显示详细信息窗格中。评估中包括的总大小和搜索结果的项目数。搜索完成后，您可以预览搜索结果。如有必要，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中的信息。 
    
7.  如有必要，请优化搜索查询以缩小搜索结果的范围，然后重新启动搜索。 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a>使用安全性和合规性中心 PowerShell 搜索所有邮箱

**新建 ComplianceSearch** cmdlet 还可用于搜索您的组织中所有邮箱。第一步是为[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。
  
下面是使用 PowerShell 搜索您的组织中所有邮箱的一个示例。搜索查询返回 2015 年 1 月 1 日和 2015 年 6 月 30 日之间发送的所有邮件并包含短语"财务报告"的主题行中。第一个命令创建搜索，和第二个命令运行搜索。 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

有关详细信息，请参阅 [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a>验证内容搜索中的源邮箱数

内容搜索返回最多 1000 个包含搜索结果的源邮箱。如果有包含与搜索查询匹配的内容的数目超过 1,000 个邮箱，仅与大多数搜索结果的顶部 1,000 个邮箱都包括您在上一步中创建在内容搜索。因此，如果超过 1000 个邮箱包含搜索结果，这些邮箱的一些不会复制到在步骤 3 中创建新的就地电子数据展示搜索的源邮箱的列表中包含。 
  
为了帮助您创建的不超过 1,000 源邮箱的内容搜索，按照以下步骤运行脚本的显示您在步骤 1 中创建内容搜索返回的源邮箱 （包含搜索结果） 的数目。 
  
1. 将以下文本保存到的 PowerShell 脚本文件中，使用.ps1 filename 后缀。例如，您无法将其保存到一个名为文件`SourceMailboxes.ps1`。
    
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

2. 安全性和合规性中心 PowerShell，在中，转到上一步中创建的脚本所在的文件夹，然后再运行脚本。例如：
    
    ```
    .\SourceMailboxes.ps1
    ```

3. 当脚本提示时，请键入您在步骤 1 中创建的内容搜索的名称。
    
    该脚本会显示包含搜索结果的源邮箱数。
    
如果有数目超过 1,000 个源邮箱，请尝试创建两个 （或多个） 的内容搜索。例如，在一个内容搜索和其他内容的搜索功能中的其他部分搜索组织的邮箱的一半。您还可以更改搜索条件以减少包含搜索结果的邮箱数。例如，您可能包括日期范围或优化关键字查询。
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>步骤 2： 连接到安全性&amp;合规性中心和 Exchange Online 中的单个的远程 PowerShell 会话

下一步是将 Windows PowerShell 连接到两个安全&amp;合规性中心和 Exchange Online 组织。这是必要的因为您在步骤 3 中运行的脚本需要访问安全中的内容搜索 cmdlet&amp;合规性中心和 Exchange Online 中的就地电子数据展示 cmdlet。
  
1. 将以下文本保存到的 Windows PowerShell 脚本文件中，使用.ps1 filename 后缀。例如，您无法将其保存到一个名为文件`ConnectEXO-CC.ps1`。
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. 本地计算机上打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行脚本。例如：
    
    ```
    .\ConnectEXO-CC.ps1
    ```

您如何知道是否这有效？运行脚本，cmdlet 从安全后&amp;合规性中心和 Exchange Online 导入本地 PowerShell 会话。如果未收到任何错误，您将成功连接。快速测试是运行安全&amp;合规性中心 cmdlet — 例如，**安装 UnifiedCompliancePrerequisite** — 和 Exchange Online cmdlet，如**Get-mailbox**。 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a>步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索

在步骤 2 中创建双 PowerShell 会话后下, 一步是运行脚本，将转换为就地电子数据展示搜索的现有内容搜索。下面是该脚本的用途：
  
- 提示您输入要转换的内容搜索的名称。
    
- 验证内容搜索是否已完成运行。如果内容搜索未返回任何结果，将不会创建就地电子数据展示。
    
- 将内容搜索中包含搜索结果的源邮箱列表保存为一个变量。
    
- 使用以下属性创建新的就地电子数据展示搜索。请注意，新的搜索未启动。您将在步骤 4 中启动该搜索。
    
  - **名称**-新搜索条件的名称使用这种格式：\<名称的内容搜索\>_MBSearch1。如果您再次运行该脚本，并使用相同的源内容搜索，将名为搜索\<名称的内容搜索\>_MBSearch2。
    
  - **源邮箱**的内容搜索包含搜索结果的所有邮箱。 
    
  - **搜索查询**的新搜索使用内容搜索中的搜索查询。如果内容搜索中包括所有内容 （其中搜索查询为空） 新的搜索还将具有空搜索查询，并将包括在源邮箱中找到的所有内容。 
    
  - **估计仅搜索**-新搜索标记为仅估计的搜索。启动它之后，它不会将搜索结果复制到发现邮箱。 
    
1. 将以下文本保存到的 Windows PowerShell 脚本文件中，使用 ps1 filename 后缀。例如，您无法将其保存到一个名为文件`CreateMBSearchFromComplianceSearch.ps1`。
    
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

2. 在步骤 2 中创建的 Windows PowerShell 会话，在中，转到您在上一步中创建的脚本所在的文件夹，然后再运行脚本。例如：
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. 出现提示时脚本，键入要转换为就地电子数据展示搜索 （例如，您在步骤 1 中创建搜索），内容搜索的名称，然后按**Enter**。
    
    如果成功脚本，新的就地电子数据展示搜索创建**为 NotStarted**的状态。运行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`来显示新的搜索的属性。 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a>步骤 4：启动就地电子数据展示搜索

您在步骤 3 中运行的脚本将创建一个新的就地电子数据展示搜索，但不会启动该搜索。下一步是启动该搜索，以便您可以获取搜索结果的估计值。
  
1. 在 Exchange 管理员中心 (EAC) 中，转到**合规性管理** \> **就地电子数据展示&amp;保留**。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。
    
3. 单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **估计搜索结果**开始搜索并返回估计总大小和搜索返回的项目数。 
    
    在细节窗格中显示估计值。单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新的详细信息窗格中显示的信息。 
    
4. 若要预览结果，搜索完成后，单击详细信息窗格中的**预览搜索结果**。
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a>创建和运行就地电子数据展示搜索后接下来的步骤

创建并启动由步骤 3 中的脚本创建的就地电子数据展示搜索后，您可以使用普通的就地电子数据展示工作流对搜索结果执行不同的电子数据展示操作。
  
### <a name="create-an-in-place-hold"></a>创建就地保留

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中，选择您在步骤 3 中创建就地电子数据展示搜索，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)。
    
3. 在**就地保留**页上，选择**选定的邮箱中的搜索查询匹配上的位置内容保留**复选框，然后选择以下选项之一: 
    
  - **无限期保留**-选择此选项可放置置于无限期保留搜索返回的项目。保留项将被保留，直到您从搜索中删除邮箱或删除搜索。 
    
  - **指定天数保留项目相对于其接收日期**-选择此选项可在特定时间保留项目。接收或创建邮箱项目时，将从日期计算持续时间。 
    
4. 单击**保存**以创建就地保留和重新开始搜索。 
    
[Return to top](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a>复制搜索结果

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。
    
3. 单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)，然后从下拉列表中单击**复制搜索结果**。 
    
4. 在**复制搜索结果**中，选择以下选项：
    
    - **包括不可搜索的项目**-选中此复选框，以包含无法搜索 （例如，通过 Exchange 搜索无法编制索引的文件类型的附件的邮件） 的邮箱项目。 
    
    - **启用重复数据删除**-选中此复选框可排除重复的邮件。仅一条消息的单个实例将复制到发现邮箱。 
    
    - **启用完整的日志记录**-选中此复选框以在搜索结果中包含完整的日志。 
    
    - **发送邮件时完成的复制**-选中此复选框，若要完成搜索时获得的电子邮件通知。 
    
    - **复制到此发现邮箱的结果**-单击**浏览**以选择要在其中搜索结果的发现邮箱复制到。 
    
5. 单击**复制**以启动的过程将搜索结果复制到指定的发现邮箱。 
    
6. 单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中显示的复制状态的信息。 
    
7. 复制完成后，单击**打开**以打开要查看搜索结果的发现邮箱。 
  
### <a name="export-the-search-results"></a>导出搜索结果

1. 在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。
    
2. 在列表视图中，选择您在步骤 3 中创建就地电子数据展示搜索，然后单击**导出到 PST 文件**。
    
3. 在**电子数据展示 PST 导出工具**窗口中，执行以下操作： 
    
    - 单击**浏览**以指定要下载 PST 文件的位置。 
    
    - 单击**启用消除**复选框来排除重复的邮件。仅一条消息的单个实例将包含在 PST 文件中。 
    
    - 单击**包括不可搜索的项目**复选框，以包含无法搜索 （例如，通过 Exchange 搜索无法编制索引的文件类型的附件的邮件） 的邮箱项目。不可搜索的项目导出到一个单独的 PST 文件。 
    
4. 单击**启动**以将搜索结果导出到 PST 文件。 
    
    将显示一个窗口，其中包含有关导出过程的状态信息。
