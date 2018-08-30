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
search.appverid:
- MET150
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 脚本来在 Exchange Online 中基于在 Office 365 安全性中创建搜索创建就地电子数据展示搜索&amp;合规性中心。 '
ms.openlocfilehash: d2f4f845e8c819eed67c3a234bff208a11fb571c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525466"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="8e0ae-103">在电子数据展示工作流中使用内容搜索</span><span class="sxs-lookup"><span data-stu-id="8e0ae-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="8e0ae-p101">Office 365 安全性内容的搜索功能&amp;合规性中心允许您搜索您的组织中的所有邮箱。与 Exchange Online （其中可以搜索最多 10,000 个邮箱） 中的就地电子数据展示，不同有的单个搜索中的目标邮箱数量没有限制。对于需要执行组织范围内搜索的方案，您可以使用内容搜索搜索所有邮箱。然后您可以使用就地电子数据展示的工作流功能执行其他电子数据展示相关的任务，如上的放置邮箱保留和导出搜索结果。例如，假设您需要搜索所有邮箱标识特定响应法律案件的管理员。您可以使用中的安全的内容搜索&amp;合规性中心，以确定响应大小写的那些贵组织中的搜索所有邮箱。然后可以使用 custodian 邮箱的列表为源邮箱的 Exchange Online 中的就地电子数据展示搜索。使用就地电子数据展示还允许这些源邮箱置于保留、 将搜索结果复制到发现邮箱，并将搜索结果导出。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p101">The Content Search feature in the Office 365 Security &amp; Compliance Center allows you to search all mailboxes in your organization. Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search. For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes. Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results. For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case. You can use Content Search in the Security &amp; Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case. Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online. Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="8e0ae-p102">本主题包含脚本，您可以运行在 Exchange Online 中使用的源邮箱和搜索查询从搜索中安全创建列表创建就地电子数据展示搜索&amp;合规性中心。下面是过程概述：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p102">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security &amp; Compliance Center. Here's an overview of the process:</span></span>
  
[<span data-ttu-id="8e0ae-114">步骤 1：创建内容搜索来搜索组织中的所有邮箱</span><span class="sxs-lookup"><span data-stu-id="8e0ae-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="8e0ae-115">步骤 2： 连接到安全性&amp;合规性中心和 Exchange Online 中的单个的远程 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="8e0ae-115">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="8e0ae-116">步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="8e0ae-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="8e0ae-117">步骤 4：启动就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="8e0ae-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="8e0ae-118">步骤 1：创建内容搜索来搜索组织中的所有邮箱</span><span class="sxs-lookup"><span data-stu-id="8e0ae-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="8e0ae-p103">第一步是使用安全&amp;合规性中心 （或安全与合规性中心 PowerShell） 创建在您的组织中搜索所有邮箱的内容搜索。没有为单一内容搜索的邮箱数的限制。指定相应的关键字查询 （或敏感信息类型的查询），以便搜索返回与调查相关这些源邮箱。如有必要，优化搜索查询来缩小搜索结果以及返回的源邮箱的范围。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p103">The first step is to use the Security &amp; Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization. There's no limit for the number of mailboxes for a single Content Search. Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation. If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e0ae-p104">如果源内容搜索未返回任何结果，则当您在步骤 3 中运行该脚本时不会创建就地电子数据展示。您可能必须修改搜索查询然后重新运行内容搜索来返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security-amp-compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="8e0ae-125">使用安全&amp;合规性中心搜索所有邮箱</span><span class="sxs-lookup"><span data-stu-id="8e0ae-125">Use the Security &amp; Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="8e0ae-126">[转到 Office 365 安全性&amp;合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-126">[Go to the Office 365 Security &amp; Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="8e0ae-127">单击**搜索&amp;调查**，单击**内容搜索**，然后单击**新建**![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-127">Click **Search &amp; investigation**, click **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="8e0ae-128">在**新的搜索**页上，键入内容的搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="8e0ae-129">在**您其中是否要查找我们？**，单击**搜索所有邮箱**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="8e0ae-p105">在下框**希望什么我们查找？**，在框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用更复杂的查询不使用布尔运算符，例如 AND、 OR 或 NEAR，或者您还可以搜索在邮件中的敏感信息 （如社会保险号码）。有关创建搜索查询的详细信息，请参阅[内容搜索的关键字查询](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p105">In the box under **What do you want us to look for?**, type a search query in the box. You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed. You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages. For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="8e0ae-134">单击**搜索**以保存的搜索设置并开始搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="8e0ae-p106">一段时间之后, 所估计的搜索结果显示详细信息窗格中。评估中包括的总大小和搜索结果的项目数。搜索完成后，您可以预览搜索结果。如有必要，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p106">After a while, an estimate of the search results displayed in the details pane. The estimate includes the total size and number of items for the search results. After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="8e0ae-139">如有必要，请优化搜索查询以缩小搜索结果的范围，然后重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="8e0ae-140">使用安全性和合规性中心 PowerShell 搜索所有邮箱</span><span class="sxs-lookup"><span data-stu-id="8e0ae-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="8e0ae-p107">**新建 ComplianceSearch** cmdlet 还可用于搜索您的组织中所有邮箱。第一步是为[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p107">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization. The first step is to [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="8e0ae-p108">下面是使用 PowerShell 搜索您的组织中所有邮箱的一个示例。搜索查询返回 2015 年 1 月 1 日和 2015 年 6 月 30 日之间发送的所有邮件并包含短语"财务报告"的主题行中。第一个命令创建搜索，和第二个命令运行搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p108">Here's an example of using PowerShell to search all mailboxes in your organization. The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line. The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="8e0ae-146">有关详细信息，请参阅 [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="8e0ae-147">验证内容搜索中的源邮箱数</span><span class="sxs-lookup"><span data-stu-id="8e0ae-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="8e0ae-p109">内容搜索返回最多 1000 个包含搜索结果的源邮箱。如果有包含与搜索查询匹配的内容的数目超过 1,000 个邮箱，仅与大多数搜索结果的顶部 1,000 个邮箱都包括您在上一步中创建在内容搜索。因此，如果超过 1000 个邮箱包含搜索结果，这些邮箱的一些不会复制到在步骤 3 中创建新的就地电子数据展示搜索的源邮箱的列表中包含。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p109">A Content Search returns a maximum of 1,000 source mailboxes that contain search results. If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step. So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="8e0ae-151">为了帮助您创建的不超过 1,000 源邮箱的内容搜索，按照以下步骤运行脚本的显示您在步骤 1 中创建内容搜索返回的源邮箱 （包含搜索结果） 的数目。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="8e0ae-p110">将以下文本保存到的 PowerShell 脚本文件中，使用.ps1 filename 后缀。例如，您无法将其保存到一个名为文件`SourceMailboxes.ps1`。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p110">Save the following text to a PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
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

2. <span data-ttu-id="8e0ae-154">安全性和合规性中心 PowerShell，在中，转到上一步中创建的脚本所在的文件夹，然后再运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="8e0ae-155">当脚本提示时，请键入您在步骤 1 中创建的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="8e0ae-156">该脚本会显示包含搜索结果的源邮箱数。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="8e0ae-p111">如果有数目超过 1,000 个源邮箱，请尝试创建两个 （或多个） 的内容搜索。例如，在一个内容搜索和其他内容的搜索功能中的其他部分搜索组织的邮箱的一半。您还可以更改搜索条件以减少包含搜索结果的邮箱数。例如，您可能包括日期范围或优化关键字查询。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p111">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches. For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search. You could also change the search criteria to reduce the number of mailboxes that contain search results. For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security-amp-compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="8e0ae-161">步骤 2： 连接到安全性&amp;合规性中心和 Exchange Online 中的单个的远程 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="8e0ae-161">Step 2: Connect to the Security &amp; Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="8e0ae-p112">下一步是将 Windows PowerShell 连接到两个安全&amp;合规性中心和 Exchange Online 组织。这是必要的因为您在步骤 3 中运行的脚本需要访问安全中的内容搜索 cmdlet&amp;合规性中心和 Exchange Online 中的就地电子数据展示 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p112">The next step is to connect Windows PowerShell to both the Security &amp; Compliance Center and to your Exchange Online organization. This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security &amp; Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="8e0ae-p113">将以下文本保存到的 Windows PowerShell 脚本文件中，使用.ps1 filename 后缀。例如，您无法将其保存到一个名为文件`ConnectEXO-CC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1. For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="8e0ae-166">本地计算机上打开 Windows PowerShell，转到您在上一步中创建的脚本所在的文件夹，然后运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="8e0ae-p114">您如何知道是否这有效？运行脚本，cmdlet 从安全后&amp;合规性中心和 Exchange Online 导入本地 PowerShell 会话。如果未收到任何错误，您将成功连接。快速测试是运行安全&amp;合规性中心 cmdlet — 例如，**安装 UnifiedCompliancePrerequisite** — 和 Exchange Online cmdlet，如**Get-mailbox**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p114">How do you know if this worked? After you run the script, cmdlets from the Security &amp; Compliance Center and Exchange Online are imported into your local PowerShell session. If you don't receive any errors, you connected successfully. A quick test is to run a Security &amp; Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="8e0ae-171">步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="8e0ae-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="8e0ae-p115">在步骤 2 中创建双 PowerShell 会话后下, 一步是运行脚本，将转换为就地电子数据展示搜索的现有内容搜索。下面是该脚本的用途：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p115">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search. Here's what the script does:</span></span>
  
- <span data-ttu-id="8e0ae-174">提示您输入要转换的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="8e0ae-p116">验证内容搜索是否已完成运行。如果内容搜索未返回任何结果，将不会创建就地电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="8e0ae-177">将内容搜索中包含搜索结果的源邮箱列表保存为一个变量。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="8e0ae-p117">使用以下属性创建新的就地电子数据展示搜索。请注意，新的搜索未启动。您将在步骤 4 中启动该搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="8e0ae-p118">**名称**-新搜索条件的名称使用这种格式：\<名称的内容搜索\>_MBSearch1。如果您再次运行该脚本，并使用相同的源内容搜索，将名为搜索\<名称的内容搜索\>_MBSearch2。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p118">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1. If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="8e0ae-183">**源邮箱**的内容搜索包含搜索结果的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="8e0ae-p119">**搜索查询**的新搜索使用内容搜索中的搜索查询。如果内容搜索中包括所有内容 （其中搜索查询为空） 新的搜索还将具有空搜索查询，并将包括在源邮箱中找到的所有内容。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p119">**Search query** - The new search uses the search query from the Content Search. If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="8e0ae-p120">**估计仅搜索**-新搜索标记为仅估计的搜索。启动它之后，它不会将搜索结果复制到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p120">**Estimate only search** - The new search is marked as an estimate-only search. It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="8e0ae-p121">将以下文本保存到的 Windows PowerShell 脚本文件中，使用 ps1 filename 后缀。例如，您无法将其保存到一个名为文件`CreateMBSearchFromComplianceSearch.ps1`。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1. For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="8e0ae-190">在步骤 2 中创建的 Windows PowerShell 会话，在中，转到您在上一步中创建的脚本所在的文件夹，然后再运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="8e0ae-191">出现提示时脚本，键入要转换为就地电子数据展示搜索 （例如，您在步骤 1 中创建搜索），内容搜索的名称，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="8e0ae-p122">如果成功脚本，新的就地电子数据展示搜索创建**为 NotStarted**的状态。运行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`来显示新的搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p122">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**. Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="8e0ae-194">步骤 4：启动就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="8e0ae-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="8e0ae-p123">您在步骤 3 中运行的脚本将创建一个新的就地电子数据展示搜索，但不会启动该搜索。下一步是启动该搜索，以便您可以获取搜索结果的估计值。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="8e0ae-197">在 Exchange 管理员中心 (EAC) 中，转到**合规性管理** \> **就地电子数据展示&amp;保留**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="8e0ae-198">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="8e0ae-199">单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **估计搜索结果**开始搜索并返回估计总大小和搜索返回的项目数。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="8e0ae-p124">在细节窗格中显示估计值。单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)以更新的详细信息窗格中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p124">The estimates are displayed in the details pane. Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="8e0ae-202">若要预览结果，搜索完成后，单击详细信息窗格中的**预览搜索结果**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="8e0ae-203">创建和运行就地电子数据展示搜索后接下来的步骤</span><span class="sxs-lookup"><span data-stu-id="8e0ae-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="8e0ae-204">创建并启动由步骤 3 中的脚本创建的就地电子数据展示搜索后，您可以使用普通的就地电子数据展示工作流对搜索结果执行不同的电子数据展示操作。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="8e0ae-205">创建就地保留</span><span class="sxs-lookup"><span data-stu-id="8e0ae-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="8e0ae-206">在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="8e0ae-207">在列表视图中，选择您在步骤 3 中创建就地电子数据展示搜索，然后单击**编辑**![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="8e0ae-208">在**就地保留**页上，选择**选定的邮箱中的搜索查询匹配上的位置内容保留**复选框，然后选择以下选项之一:</span><span class="sxs-lookup"><span data-stu-id="8e0ae-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="8e0ae-p125">**无限期保留**-选择此选项可放置置于无限期保留搜索返回的项目。保留项将被保留，直到您从搜索中删除邮箱或删除搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p125">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold. Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="8e0ae-p126">**指定天数保留项目相对于其接收日期**-选择此选项可在特定时间保留项目。接收或创建邮箱项目时，将从日期计算持续时间。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p126">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period. The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="8e0ae-213">单击**保存**以创建就地保留和重新开始搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="8e0ae-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="8e0ae-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="8e0ae-215">复制搜索结果</span><span class="sxs-lookup"><span data-stu-id="8e0ae-215">Copy the search results</span></span>

1. <span data-ttu-id="8e0ae-216">在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="8e0ae-217">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="8e0ae-218">单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)，然后从下拉列表中单击**复制搜索结果**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="8e0ae-219">在**复制搜索结果**中，选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="8e0ae-220">**包括不可搜索的项目**-选中此复选框，以包含无法搜索 （例如，通过 Exchange 搜索无法编制索引的文件类型的附件的邮件） 的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="8e0ae-p127">**启用重复数据删除**-选中此复选框可排除重复的邮件。仅一条消息的单个实例将复制到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p127">**Enable de-duplication** - Select this check box to exclude duplicate messages. Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="8e0ae-223">**启用完整的日志记录**-选中此复选框以在搜索结果中包含完整的日志。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="8e0ae-224">**发送邮件时完成的复制**-选中此复选框，若要完成搜索时获得的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="8e0ae-225">**复制到此发现邮箱的结果**-单击**浏览**以选择要在其中搜索结果的发现邮箱复制到。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="8e0ae-226">单击**复制**以启动的过程将搜索结果复制到指定的发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="8e0ae-227">单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)要更新的详细信息窗格中显示的复制状态的信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="8e0ae-228">复制完成后，单击**打开**以打开要查看搜索结果的发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="8e0ae-229">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="8e0ae-229">Export the search results</span></span>

1. <span data-ttu-id="8e0ae-230">在 EAC 中，转到"合规管理"****"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="8e0ae-231">在列表视图中，选择您在步骤 3 中创建就地电子数据展示搜索，然后单击**导出到 PST 文件**。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="8e0ae-232">在**电子数据展示 PST 导出工具**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e0ae-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="8e0ae-233">单击**浏览**以指定要下载 PST 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="8e0ae-p128">单击**启用消除**复选框来排除重复的邮件。仅一条消息的单个实例将包含在 PST 文件中。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="8e0ae-p129">单击**包括不可搜索的项目**复选框，以包含无法搜索 （例如，通过 Exchange 搜索无法编制索引的文件类型的附件的邮件） 的邮箱项目。不可搜索的项目导出到一个单独的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="8e0ae-238">单击**启动**以将搜索结果导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="8e0ae-239">将显示一个窗口，其中包含有关导出过程的状态信息。</span><span class="sxs-lookup"><span data-stu-id="8e0ae-239">A window is displayed that contains status information about the export process.</span></span>
