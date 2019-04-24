---
title: 在电子数据展示工作流中使用内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 55f31488-288a-473a-9b9e-831a11e3711a
description: '使用 PowerShell 脚本在 Exchange Online 中创建基于 Security & 合规性中心中创建的搜索的就地电子数据展示搜索。 '
ms.openlocfilehash: 2e4f1b3570ce2400472a0b2a9ddee886ffc4bab3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263794"
---
# <a name="use-content-search-in-your-ediscovery-workflow"></a><span data-ttu-id="51e2c-103">在电子数据展示工作流中使用内容搜索</span><span class="sxs-lookup"><span data-stu-id="51e2c-103">Use Content Search in your eDiscovery workflow</span></span>

<span data-ttu-id="51e2c-104">通过 Security & 合规性中心中的内容搜索功能, 可以搜索组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-104">The Content Search feature in the Security & Compliance Center allows you to search all mailboxes in your organization.</span></span> <span data-ttu-id="51e2c-105">与 Exchange Online 中的就地电子数据展示不同 (最多可以搜索10000个邮箱), 对单个搜索中的目标邮箱数没有限制。</span><span class="sxs-lookup"><span data-stu-id="51e2c-105">Unlike In-Place eDiscovery in Exchange Online (where you can search up to 10,000 mailboxes), there are no limits for the number of target mailboxes in a single search.</span></span> <span data-ttu-id="51e2c-106">对于需要您执行组织范围内搜索的方案，可以使用内容搜索来搜索所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-106">For scenarios that require you to perform organization-wide searches, you can use Content Search to search all mailboxes.</span></span> <span data-ttu-id="51e2c-107">然后, 您可以使用就地电子数据展示的工作流功能执行其他与电子数据展示相关的任务, 如将邮箱置于保留状态并导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51e2c-107">Then you can use the workflow features of In-Place eDiscovery to perform other eDiscovery-related tasks, such as placing mailboxes on hold and exporting search results.</span></span> <span data-ttu-id="51e2c-108">例如，假设您需要搜索所有邮箱以确定可以响应某法律案件的特定监护人。</span><span class="sxs-lookup"><span data-stu-id="51e2c-108">For example, let's say you have to search all mailboxes to identify specific custodians that are responsive to a legal case.</span></span> <span data-ttu-id="51e2c-109">您可以使用 Security & 合规中心中的内容搜索来搜索组织中的所有邮箱, 以确定那些对案例有响应的邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-109">You can use Content Search in the Security & Compliance Center to search all mailboxes in your organization to identify those that are responsive to the case.</span></span> <span data-ttu-id="51e2c-110">然后, 可以将该保管人邮箱列表用作 Exchange Online 中的就地电子数据展示搜索的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-110">Then you can use that list of custodian mailboxes as the source mailboxes for an In-Place eDiscovery search in Exchange Online.</span></span> <span data-ttu-id="51e2c-111">使用就地电子数据展示还允许您对这些源邮箱进行保留, 将搜索结果复制到发现邮箱, 并导出搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51e2c-111">Using In-Place eDiscovery also allows you to put a hold on those source mailboxes, copy search results to a discovery mailbox, and export the search results.</span></span>
  
<span data-ttu-id="51e2c-112">本主题包含一个脚本, 可运行此脚本在 Exchange Online 中创建就地电子数据展示搜索, 具体方法是使用安全 & 合规性中心中创建的搜索中的源邮箱和搜索查询的列表。</span><span class="sxs-lookup"><span data-stu-id="51e2c-112">This topic includes a script that you can run to create an In-Place eDiscovery search in Exchange Online by using the list of source mailboxes and search query from a search created in the Security & Compliance Center.</span></span> <span data-ttu-id="51e2c-113">以下是过程概述：</span><span class="sxs-lookup"><span data-stu-id="51e2c-113">Here's an overview of the process:</span></span>
  
[<span data-ttu-id="51e2c-114">步骤 1：创建内容搜索来搜索组织中的所有邮箱</span><span class="sxs-lookup"><span data-stu-id="51e2c-114">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>](#step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization)

[<span data-ttu-id="51e2c-115">步骤 2: 在单个远程 PowerShell \&会话中连接到安全合规性中心和 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51e2c-115">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>](#step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session)
  
[<span data-ttu-id="51e2c-116">步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="51e2c-116">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>](#step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search)

[<span data-ttu-id="51e2c-117">Step 4: Start the In-Place eDiscovery search</span><span class="sxs-lookup"><span data-stu-id="51e2c-117">Step 4: Start the In-Place eDiscovery search</span></span>](#step-4-start-the-in-place-ediscovery-search)

## <a name="step-1-create-a-content-search-to-search-all-mailboxes-in-your-organization"></a><span data-ttu-id="51e2c-118">步骤 1：创建内容搜索来搜索组织中的所有邮箱</span><span class="sxs-lookup"><span data-stu-id="51e2c-118">Step 1: Create a Content Search to search all mailboxes in your organization</span></span>

<span data-ttu-id="51e2c-119">第一步是使用安全 & 合规性中心 (或 security & 合规性中心 PowerShell) 来创建搜索组织中所有邮箱的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-119">The first step is to use the Security & Compliance Center (or Security & Compliance Center PowerShell) to create a Content Search that searches all mailboxes in your organization.</span></span> <span data-ttu-id="51e2c-120">对于单个内容搜索的邮箱数没有限制。</span><span class="sxs-lookup"><span data-stu-id="51e2c-120">There's no limit for the number of mailboxes for a single Content Search.</span></span> <span data-ttu-id="51e2c-121">指定适当的关键字查询（或针对敏感信息类型的查询），以便搜索仅返回与您的调查相关的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-121">Specify an appropriate keyword query (or a query for sensitive information types) so that the search returns only those source mailboxes that are relevant to your investigation.</span></span> <span data-ttu-id="51e2c-122">如有必要，优化搜索查询来缩小返回的搜索结果以及源邮箱的范围。</span><span class="sxs-lookup"><span data-stu-id="51e2c-122">If necessary, refine the search query to narrow the scope of search results and source mailboxes that are returned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51e2c-p104">如果源内容搜索未返回任何结果，则当您在步骤 3 中运行该脚本时不会创建就地电子数据展示。您可能必须修改搜索查询然后重新运行内容搜索来返回搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51e2c-p104">If the source Content Search doesn't return any results, an In-Place eDiscovery won't be created when you run the script in Step 3. You may have to revise the search query then rerun the Content Search to return search results.</span></span> 
  
### <a name="use-the-security--compliance-center-to-search-all-mailboxes"></a><span data-ttu-id="51e2c-125">使用安全与合规中心来搜索所有邮箱</span><span class="sxs-lookup"><span data-stu-id="51e2c-125">Use the Security & Compliance Center to search all mailboxes</span></span>

1. <span data-ttu-id="51e2c-126">[转到安全 & 合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-126">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span> 
    
2. <span data-ttu-id="51e2c-127">单击 "**搜索** > **内容搜索**", 然后单击 "**新建搜索** ![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-127">Click **Search** > **Content search**, and then click **New search** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
3. <span data-ttu-id="51e2c-128">在“新建搜索”\*\*\*\* 页上，键入内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="51e2c-128">On the **New search** page, type a name for the Content Search.</span></span> 
    
4. <span data-ttu-id="51e2c-129">在\*\*\*\*“您想要我们查找什么位置？”下，单击“搜索所有邮箱”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51e2c-129">Under **Where do you want us to look?**, click **Search all mailboxes**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="51e2c-130">在“您想要我们查找哪些内容”\*\*\*\* 下的框中，键入搜索查询。</span><span class="sxs-lookup"><span data-stu-id="51e2c-130">In the box under **What do you want us to look for?**, type a search query in the box.</span></span> <span data-ttu-id="51e2c-131">您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。</span><span class="sxs-lookup"><span data-stu-id="51e2c-131">You can specify keywords, message properties such as sent and received dates, or document properties such as file names or the date that a document was last changed.</span></span> <span data-ttu-id="51e2c-132">您可以使用更复杂的查询 (如 AND、OR、NOT 或 NEAR), 也可以在邮件中搜索敏感信息 (如社会保险号)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-132">You can use a more complex queries that use a Boolean operator, such as AND, OR, NOT or NEAR, or you can also search for sensitive information (such as social security numbers) in messages.</span></span> <span data-ttu-id="51e2c-133">有关创建搜索查询的详细信息，请参阅[Keyword queries for Content Search](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-133">For more information about creating search queries, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
6. <span data-ttu-id="51e2c-134">单击\*\*\*\*“搜索”保存搜索设置，然后启动搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-134">Click **Search** to save the search settings and start the search.</span></span> 
    
    <span data-ttu-id="51e2c-135">一段时间后, 在详细信息窗格中显示搜索结果的估计值。</span><span class="sxs-lookup"><span data-stu-id="51e2c-135">After a while, an estimate of the search results displayed in the details pane.</span></span> <span data-ttu-id="51e2c-136">估计值包括搜索结果的总大小和项目数。</span><span class="sxs-lookup"><span data-stu-id="51e2c-136">The estimate includes the total size and number of items for the search results.</span></span> <span data-ttu-id="51e2c-137">完成搜索后，您可以预览搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51e2c-137">After the search is completed, you can preview the search results.</span></span> <span data-ttu-id="51e2c-138">如有必要, \*\*\*\*![请单击 "](media/O365-MDM-Policy-RefreshIcon.gif)刷新刷新" 图标以更新详细信息窗格中的信息。</span><span class="sxs-lookup"><span data-stu-id="51e2c-138">If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
7.  <span data-ttu-id="51e2c-139">如有必要，请优化搜索查询以缩小搜索结果的范围，然后重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-139">If necessary, refine the search query to narrow the scope of search results and then restart the search.</span></span> 
    
### <a name="use-security--compliance-center-powershell-to-search-all-mailboxes"></a><span data-ttu-id="51e2c-140">使用 Security & 合规性中心 PowerShell 搜索所有邮箱</span><span class="sxs-lookup"><span data-stu-id="51e2c-140">Use Security & Compliance Center PowerShell to search all mailboxes</span></span>

<span data-ttu-id="51e2c-141">您还可以使用 **New-ComplianceSearch** cmdlet 搜索组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-141">You can also use the **New-ComplianceSearch** cmdlet to search all mailboxes in your organization.</span></span> <span data-ttu-id="51e2c-142">第一步是[连接到安全 & 合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-142">The first step is to [Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=627084).</span></span>
  
<span data-ttu-id="51e2c-143">下面的示例展示了如何使用 PowerShell 搜索组织中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-143">Here's an example of using PowerShell to search all mailboxes in your organization.</span></span> <span data-ttu-id="51e2c-144">搜索查询将返回 2015 年 1 月 1 日和 2015 年 6 月 30 日之间发送的以及主题行中包含短语“财务报告”的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="51e2c-144">The search query returns all messages sent between January 1, 2015 and June 30, 2015 and that contain the phrase "financial report" in the subject line.</span></span> <span data-ttu-id="51e2c-145">第一个命令创建搜索，第二个命令运行搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-145">The first command creates the search, and the second command runs the search.</span></span> 
  
```
New-ComplianceSearch -Name "Search All-Financial Report" -ExchangeLocation all -ContentMatchQuery 'sent>=01/01/2015 AND sent<=06/30/2015 AND subject:"financial report"'
```

```
Start-ComplianceSearch -Identity "Search All-Financial Report"
```

<span data-ttu-id="51e2c-146">有关详细信息，请参阅 [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-146">For more information, see [New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935).</span></span>
  
### <a name="verify-the-number-of-source-mailboxes-in-the-content-search"></a><span data-ttu-id="51e2c-147">验证内容搜索中的源邮箱数</span><span class="sxs-lookup"><span data-stu-id="51e2c-147">Verify the number of source mailboxes in the Content Search</span></span>

<span data-ttu-id="51e2c-148">内容搜索返回的最大值为1000个包含搜索结果的源邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-148">A Content Search returns a maximum of 1,000 source mailboxes that contain search results.</span></span> <span data-ttu-id="51e2c-149">如果包含与搜索查询匹配的内容的邮箱多于1000个, 则在上一步中创建的内容搜索中仅包含最上面包含最多搜索结果的前1000个邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-149">If there are more than 1,000 mailboxes that contain content that matches the search query, only the top 1,000 mailboxes with the most search results are included in the Content Search that you created in the previous step.</span></span> <span data-ttu-id="51e2c-150">因此, 如果超过1000个邮箱包含搜索结果, 则其中一些邮箱将不会包括在复制到在步骤3中创建的新就地电子数据展示搜索的源邮箱列表中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-150">So if more than 1,000 mailboxes contain search results, some of those mailboxes won't be included in the list of source mailboxes copied to the new In-Place eDiscovery search created in Step 3.</span></span> 
  
<span data-ttu-id="51e2c-151">若要帮助您创建不超过1000源邮箱的内容搜索, 请按照以下步骤操作, 以运行一个显示您在步骤1中创建的内容搜索所返回的源邮箱数 (包含搜索结果) 的脚本。</span><span class="sxs-lookup"><span data-stu-id="51e2c-151">To help you create a Content Search with no more than 1,000 source mailboxes, follow these steps to run a script that displays the number of source mailboxes (that contain search results) returned by the Content Search you created in Step 1.</span></span> 
  
1. <span data-ttu-id="51e2c-152">使用文件名后缀. ps1 将以下文本保存到 PowerShell 脚本文件中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-152">Save the following text to a PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="51e2c-153">例如, 可以将其保存到名为`SourceMailboxes.ps1`的文件中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-153">For example, you could save it to a file named `SourceMailboxes.ps1`.</span></span>
    
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

2. <span data-ttu-id="51e2c-154">在 Security & 合规性中心 PowerShell 中, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="51e2c-154">In Security & Compliance Center PowerShell, go to the folder where the script you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\SourceMailboxes.ps1
    ```

3. <span data-ttu-id="51e2c-155">当脚本提示时，请键入您在步骤 1 中创建的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="51e2c-155">When prompted by the script, type the name of the Content Search that you created in Step 1.</span></span>
    
    <span data-ttu-id="51e2c-156">该脚本会显示包含搜索结果的源邮箱数。</span><span class="sxs-lookup"><span data-stu-id="51e2c-156">The script displays the number of source mailboxes that contain search results.</span></span>
    
<span data-ttu-id="51e2c-157">如果源邮箱多于1000个, 请尝试创建两个或更多的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-157">If there are more than 1,000 source mailboxes, try creating two (or more) Content Searches.</span></span> <span data-ttu-id="51e2c-158">例如，在一个内容搜索中搜索组织中一半的邮箱，在另一个内容搜索中搜索组织中的另一半邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-158">For example, search half of your organization's mailboxes in one Content Search and the other half in another Content Search.</span></span> <span data-ttu-id="51e2c-159">您还可以更改搜索条件以减少包含搜索结果的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="51e2c-159">You could also change the search criteria to reduce the number of mailboxes that contain search results.</span></span> <span data-ttu-id="51e2c-160">例如, 可以包括日期范围或精炼关键字查询。</span><span class="sxs-lookup"><span data-stu-id="51e2c-160">For example, you could include a date range or refine the keyword query.</span></span>
  
## <a name="step-2-connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a><span data-ttu-id="51e2c-161">步骤 2: 在单个远程 PowerShell \&会话中连接到安全合规性中心和 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="51e2c-161">Step 2: Connect to the Security \& Compliance Center and Exchange Online in a single remote PowerShell session</span></span>

<span data-ttu-id="51e2c-162">下一步是将 Windows PowerShell 连接到安全 & 合规中心和 Exchange Online 组织。</span><span class="sxs-lookup"><span data-stu-id="51e2c-162">The next step is to connect Windows PowerShell to both the Security & Compliance Center and to your Exchange Online organization.</span></span> <span data-ttu-id="51e2c-163">这是必要的, 因为您在步骤3中运行的脚本需要访问安全 & 合规性中心中的内容搜索 cmdlet 和 Exchange Online 中的就地电子数据展示 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51e2c-163">This is necessary because the script that you run in Step 3 requires access to the Content Search cmdlets in the Security & Compliance Center and the In-Place eDiscovery cmdlets in Exchange Online.</span></span>
  
1. <span data-ttu-id="51e2c-164">使用 .ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="51e2c-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1.</span></span> <span data-ttu-id="51e2c-165">例如, 可以将其保存到名为`ConnectEXO-CC.ps1`的文件中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-165">For example, you could save it to a file named `ConnectEXO-CC.ps1`.</span></span>
    
    ```
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. <span data-ttu-id="51e2c-166">在本地计算机上, 打开 Windows PowerShell, 转到上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="51e2c-166">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectEXO-CC.ps1
    ```

<span data-ttu-id="51e2c-167">您如何知道这是否有效？</span><span class="sxs-lookup"><span data-stu-id="51e2c-167">How do you know if this worked?</span></span> <span data-ttu-id="51e2c-168">运行该脚本后, 安全 & 合规中心和 Exchange Online 中的 cmdlet 将导入到您的本地 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-168">After you run the script, cmdlets from the Security & Compliance Center and Exchange Online are imported into your local PowerShell session.</span></span> <span data-ttu-id="51e2c-169">如果未收到任何错误，说明连接成功。</span><span class="sxs-lookup"><span data-stu-id="51e2c-169">If you don't receive any errors, you connected successfully.</span></span> <span data-ttu-id="51e2c-170">快速测试是运行安全 & 合规性中心 cmdlet (例如, **UnifiedCompliancePrerequisite** ) 和 Exchange Online cmdlet (如**Get 邮箱**)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-170">A quick test is to run a Security & Compliance Center cmdlet—for example, **Install-UnifiedCompliancePrerequisite** —and an Exchange Online cmdlet, such as **Get-Mailbox**.</span></span> 
  
## <a name="step-3-run-the-script-to-create-an-in-place-ediscovery-search-from-the-content-search"></a><span data-ttu-id="51e2c-171">步骤 3：运行脚本以通过内容搜索创建就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="51e2c-171">Step 3: Run the script to create an In-Place eDiscovery search from the Content Search</span></span>

<span data-ttu-id="51e2c-172">在步骤2中创建双 PowerShell 会话之后, 下一步是运行脚本, 将现有内容搜索转换为就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-172">After you create the dual PowerShell session in Step 2, the next step is to run a script that will convert an existing Content Search to an In-Place eDiscovery search.</span></span> <span data-ttu-id="51e2c-173">下面是脚本的用途：</span><span class="sxs-lookup"><span data-stu-id="51e2c-173">Here's what the script does:</span></span>
  
- <span data-ttu-id="51e2c-174">提示您输入要转换的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="51e2c-174">Prompts you for the name of the Content Search to convert.</span></span>
    
- <span data-ttu-id="51e2c-p116">验证内容搜索是否已完成运行。如果内容搜索未返回任何结果，将不会创建就地电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="51e2c-p116">Verifies that the Content Search has completed running. If the Content Search doesn't return any results, and In-Place eDiscovery won't be created.</span></span>
    
- <span data-ttu-id="51e2c-177">将内容搜索中包含搜索结果的源邮箱列表保存为一个变量。</span><span class="sxs-lookup"><span data-stu-id="51e2c-177">Saves a list of the source mailboxes from the Content Search that contain search results to a variable.</span></span>
    
- <span data-ttu-id="51e2c-p117">使用以下属性创建新的就地电子数据展示搜索。请注意，新的搜索未启动。您将在步骤 4 中启动该搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-p117">Creates a new In-Place eDiscovery search, with the following properties. Note that the new search isn't started. You'll start it in step 4.</span></span>
    
  - <span data-ttu-id="51e2c-181">**Name** -新搜索的名称使用以下格式: \<内容搜索\>_MBSearch1 的名称。</span><span class="sxs-lookup"><span data-stu-id="51e2c-181">**Name** - The name of the new search uses this format: \<Name of Content Search\>_MBSearch1.</span></span> <span data-ttu-id="51e2c-182">如果再次运行脚本并使用相同的源内容搜索, 则搜索将命名\<为内容搜索\>_MBSearch2 的名称。</span><span class="sxs-lookup"><span data-stu-id="51e2c-182">If you run the script again and use the same source Content Search, the search will be named \<Name of Content Search\>_MBSearch2.</span></span>
    
  - <span data-ttu-id="51e2c-183">**源邮箱**-包含搜索结果的内容搜索中的所有邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-183">**Source mailboxes** - All mailboxes from the Content Search that contain search results.</span></span> 
    
  - <span data-ttu-id="51e2c-184">**搜索查询**-新搜索将使用内容搜索中的搜索查询。</span><span class="sxs-lookup"><span data-stu-id="51e2c-184">**Search query** - The new search uses the search query from the Content Search.</span></span> <span data-ttu-id="51e2c-185">如果内容搜索中包括所有内容（其中搜索查询为空），则新搜索也将会有空的搜索查询并将包含源邮箱中找到的所有内容。</span><span class="sxs-lookup"><span data-stu-id="51e2c-185">If the Content Search includes all content (where the search query is blank) the new search will also have a blank search query and will include all content found in the source mailboxes.</span></span> 
    
  - <span data-ttu-id="51e2c-186">**仅估计搜索**-新搜索被标记为 "仅估计" 搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-186">**Estimate only search** - The new search is marked as an estimate-only search.</span></span> <span data-ttu-id="51e2c-187">启动后，它不会将搜索结果复制到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-187">It won't copy search results to a discovery mailbox after you start it.</span></span> 
    
1. <span data-ttu-id="51e2c-188">使用 ps1 文件名后缀将以下文本保存到 Windows PowerShell 脚本文件。</span><span class="sxs-lookup"><span data-stu-id="51e2c-188">Save the following text to a Windows PowerShell script file by using a filename suffix of ps1.</span></span> <span data-ttu-id="51e2c-189">例如, 可以将其保存到名为`CreateMBSearchFromComplianceSearch.ps1`的文件中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-189">For example, you could save it to a file named `CreateMBSearchFromComplianceSearch.ps1`.</span></span>
    
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

2. <span data-ttu-id="51e2c-190">在您在步骤2中创建的 Windows PowerShell 会话中, 转到在上一步中创建的脚本所在的文件夹, 然后运行该脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="51e2c-190">In the Windows PowerShell session that you created in Step 2, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\CreateMBSearchFromComplianceSearch.ps1
    ```

3. <span data-ttu-id="51e2c-191">当脚本提示时, 键入要转换为就地电子数据展示搜索的内容搜索的名称 (例如, 在步骤1中创建的搜索), 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="51e2c-191">When prompted by the script, type the name of the Content Search that you want to covert to an In-Place eDiscovery search (for example, the search that you created in Step 1), and then press **Enter**.</span></span>
    
    <span data-ttu-id="51e2c-192">如果脚本成功，将创建新的就地电子数据展示搜索，状态为 **NotStarted**。</span><span class="sxs-lookup"><span data-stu-id="51e2c-192">If the script is successful, a new In-Place eDiscovery search is created with a status of **NotStarted**.</span></span> <span data-ttu-id="51e2c-193">运行命令`Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL`以显示新搜索的属性。</span><span class="sxs-lookup"><span data-stu-id="51e2c-193">Run the command  `Get-MailboxSearch <Name of Content Search>_MBSearch1 | FL` to display the properties of the new search.</span></span> 
  
## <a name="step-4-start-the-in-place-ediscovery-search"></a><span data-ttu-id="51e2c-194">步骤 4：启动就地电子数据展示搜索</span><span class="sxs-lookup"><span data-stu-id="51e2c-194">Step 4: Start the In-Place eDiscovery search</span></span>

<span data-ttu-id="51e2c-p123">您在步骤 3 中运行的脚本将创建一个新的就地电子数据展示搜索，但不会启动该搜索。下一步是启动该搜索，以便您可以获取搜索结果的估计值。</span><span class="sxs-lookup"><span data-stu-id="51e2c-p123">The script that you run in Step 3 creates a new In-Place eDiscovery search, but doesn't start it. The next step is to start the search so you can get an estimate of the search results.</span></span>
  
1. <span data-ttu-id="51e2c-197">在 Exchange 管理中心 (EAC) 中, 转到 "**合规性管理** \> **就地电子数据&amp;展示保留**"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-197">In the Exchange admin center (EAC), go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51e2c-198">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-198">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="51e2c-199">单击 "**搜索** ![搜索](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> " 图标 "**估计搜索结果**" 以启动搜索并返回由搜索返回的总大小和项目数的估计值。</span><span class="sxs-lookup"><span data-stu-id="51e2c-199">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif) \> **Estimate search results** to start the search and return an estimate of the total size and number of items returned by the search.</span></span> 
    
    <span data-ttu-id="51e2c-200">估计值显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-200">The estimates are displayed in the details pane.</span></span> <span data-ttu-id="51e2c-201">单击 "**刷新** ![刷新](media/O365-MDM-Policy-RefreshIcon.gif) " 图标以更新详细信息窗格中显示的信息。</span><span class="sxs-lookup"><span data-stu-id="51e2c-201">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information displayed in the details pane.</span></span> 
    
4. <span data-ttu-id="51e2c-202">若要在完成搜索后预览结果，请单击\*\*\*\* 详细信息窗格中的“预览搜索结果”。</span><span class="sxs-lookup"><span data-stu-id="51e2c-202">To preview the results after the search is completed, click **Preview search results** in the details pane.</span></span>
  
## <a name="next-steps-after-creating-and-running-the-in-place-ediscovery-search"></a><span data-ttu-id="51e2c-203">创建和运行就地电子数据展示搜索后接下来的步骤</span><span class="sxs-lookup"><span data-stu-id="51e2c-203">Next steps after creating and running the In-Place eDiscovery search</span></span>

<span data-ttu-id="51e2c-204">创建并启动由步骤 3 中的脚本创建的就地电子数据展示搜索后，您可以使用普通的就地电子数据展示工作流对搜索结果执行不同的电子数据展示操作。</span><span class="sxs-lookup"><span data-stu-id="51e2c-204">After you create and start the In-Place eDiscovery search that was created by the script in Step 3, you can use the normal In-Place eDiscovery workflow to perform different eDiscovery actions on the search results.</span></span>
  
### <a name="create-an-in-place-hold"></a><span data-ttu-id="51e2c-205">创建就地保留</span><span class="sxs-lookup"><span data-stu-id="51e2c-205">Create an In-Place Hold</span></span>

1. <span data-ttu-id="51e2c-206">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-206">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51e2c-207">在列表视图中, 选择您在步骤3中创建的就地电子数据展示搜索, 然后单击 "**编辑** ![编辑图标](media/O365_MDM_CreatePolicy_EditIcon.gif)"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-207">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Edit** ![Edit icon](media/O365_MDM_CreatePolicy_EditIcon.gif).</span></span>
    
3. <span data-ttu-id="51e2c-208">在“就地保留”\*\*\*\* 页面上，选中“将与所选邮箱中的搜索查询匹配的内容置于保留状态”\*\*\*\* 复选框，然后选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="51e2c-208">On the **In-Place Hold** page, select the **Place content matching the search query in selected mailboxes on hold** check box and then select one of the following options:</span></span> 
    
  - <span data-ttu-id="51e2c-209">**无限期保留**-选择此选项可将搜索返回的项目放置在无限期保留中。</span><span class="sxs-lookup"><span data-stu-id="51e2c-209">**Hold indefinitely** - Choose this option to place items returned by the search on an indefinite hold.</span></span> <span data-ttu-id="51e2c-210">保留的项目将会保持，直到您从搜索中删除邮箱或删除搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-210">Items on hold will be preserved until you remove the mailbox from the search or remove the search.</span></span> 
    
  - <span data-ttu-id="51e2c-211">**指定相对于接收日期保留项目的天数**-选择此选项可保留特定时段内的项目。</span><span class="sxs-lookup"><span data-stu-id="51e2c-211">**Specify number of days to hold items relative to their received date** - Choose this option to hold items for a specific period.</span></span> <span data-ttu-id="51e2c-212">持续时间从接收或创建邮箱项目的日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="51e2c-212">The duration is calculated from the date a mailbox item is received or created.</span></span> 
    
4. <span data-ttu-id="51e2c-213">单击\*\*\*\*“保存”创建就地保留并重新启动搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-213">Click **Save** to create the In-Place Hold and restart the search.</span></span> 
    
[<span data-ttu-id="51e2c-214">Return to top</span><span class="sxs-lookup"><span data-stu-id="51e2c-214">Return to top</span></span>](use-content-search-in-ediscovery.md#top)
  
### <a name="copy-the-search-results"></a><span data-ttu-id="51e2c-215">复制搜索结果</span><span class="sxs-lookup"><span data-stu-id="51e2c-215">Copy the search results</span></span>

1. <span data-ttu-id="51e2c-216">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-216">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51e2c-217">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索。</span><span class="sxs-lookup"><span data-stu-id="51e2c-217">In the list view, select the In-Place eDiscovery search that you created in Step 3.</span></span>
    
3. <span data-ttu-id="51e2c-218">单击 "**搜索** ![搜索](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)" 图标, 然后从下拉列表中单击 "**复制搜索结果**"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-218">Click **Search** ![Search icon](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif), and then click **Copy search results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="51e2c-219">在“复制搜索结果”\*\*\*\* 中，从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="51e2c-219">In **Copy Search Results**, select from the following options:</span></span>
    
    - <span data-ttu-id="51e2c-220">**包含不可搜索项**-选中此复选框可包含无法搜索的邮箱项目 (例如, 包含无法由 Exchange 搜索编制索引的文件类型附件的邮件)。</span><span class="sxs-lookup"><span data-stu-id="51e2c-220">**Include unsearchable items** - Select this check box to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search).</span></span> 
    
    - <span data-ttu-id="51e2c-221">**启用重复数据**删除-选中此复选框以排除重复的邮件。</span><span class="sxs-lookup"><span data-stu-id="51e2c-221">**Enable de-duplication** - Select this check box to exclude duplicate messages.</span></span> <span data-ttu-id="51e2c-222">仅有邮件的单个实例将被复制到发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-222">Only a single instance of a message will be copied to the discovery mailbox.</span></span> 
    
    - <span data-ttu-id="51e2c-223">**启用完整日志记录**-选中此复选框可在搜索结果中包含完整日志。</span><span class="sxs-lookup"><span data-stu-id="51e2c-223">**Enable full logging** - Select this check box to include a full log in search results.</span></span> 
    
    - <span data-ttu-id="51e2c-224">**完成该副本后发送邮件**-选中此复选框可在搜索完成后收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="51e2c-224">**Send me mail when the copy is completed** - Select this check box to get an email notification when the search is completed.</span></span> 
    
    - <span data-ttu-id="51e2c-225">**将结果复制到此发现邮箱**-单击 "**浏览**" 以选择要将搜索结果复制到其中的发现邮箱。</span><span class="sxs-lookup"><span data-stu-id="51e2c-225">**Copy results to this discovery mailbox** - Click **Browse** to select the discovery mailbox where you want the search results copied to.</span></span> 
    
5. <span data-ttu-id="51e2c-226">单击“复制”\*\*\*\* 开始将搜索结果复制到指定发现邮箱的过程。</span><span class="sxs-lookup"><span data-stu-id="51e2c-226">Click **Copy** to start the process to copy the search results to the specified discovery mailbox.</span></span> 
    
6. <span data-ttu-id="51e2c-227">单击 "**刷新** ![刷新](media/O365-MDM-Policy-RefreshIcon.gif) " 图标以更新有关在详细信息窗格中显示的复制状态的信息。</span><span class="sxs-lookup"><span data-stu-id="51e2c-227">Click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information about the copying status that is displayed in the details pane.</span></span> 
    
7. <span data-ttu-id="51e2c-228">复制完成后，单击“打开”\*\*\*\* 打开发现邮箱查看搜索结果。</span><span class="sxs-lookup"><span data-stu-id="51e2c-228">When copying is complete, click **Open** to open the discovery mailbox to view the search results.</span></span> 
  
### <a name="export-the-search-results"></a><span data-ttu-id="51e2c-229">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="51e2c-229">Export the search results</span></span>

1. <span data-ttu-id="51e2c-230">在 EAC 中，转到"合规管理"\*\*\*\*"就地电子数据展示和保留"。</span><span class="sxs-lookup"><span data-stu-id="51e2c-230">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
2. <span data-ttu-id="51e2c-231">在列表视图中，选择您在步骤 3 中创建的就地电子数据展示搜索，然后单击“导出到 PST 文件”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="51e2c-231">In the list view, select the In-Place eDiscovery search that you created in Step 3, and then click **Export to a PST file**.</span></span>
    
3. <span data-ttu-id="51e2c-232">在“电子数据展示 PST 导出工具”\*\*\*\* 窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="51e2c-232">In the **eDiscovery PST Export Tool** window, do the following:</span></span> 
    
    - <span data-ttu-id="51e2c-233">单击“浏览”\*\*\*\* 指定要下载 PST 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="51e2c-233">Click **Browse** to specify the location where you want to download the PST file.</span></span> 
    
    - <span data-ttu-id="51e2c-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span><span class="sxs-lookup"><span data-stu-id="51e2c-p128">Click the **Enable deduplication** checkbox to exclude duplicate messages. Only a single instance of a message will be included in the PST file.</span></span> 
    
    - <span data-ttu-id="51e2c-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span><span class="sxs-lookup"><span data-stu-id="51e2c-p129">Click the **Include unsearchable items** checkbox to include mailbox items that couldn't be searched (for example, messages with attachments of file types that couldn't be indexed by Exchange Search). Unsearchable items are exported to a separate PST file.</span></span> 
    
4. <span data-ttu-id="51e2c-238">单击“开始”\*\*\*\* 将搜索结果导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="51e2c-238">Click **Start** to export the search results to a PST file.</span></span> 
    
    <span data-ttu-id="51e2c-239">将显示一个窗口，其中包含有关导出过程的状态信息。</span><span class="sxs-lookup"><span data-stu-id="51e2c-239">A window is displayed that contains status information about the export process.</span></span>
