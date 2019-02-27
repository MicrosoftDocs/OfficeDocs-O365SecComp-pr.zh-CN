---
title: 使用内容搜索在邮箱和 OneDrive for Business 站点中搜索用户列表
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: 使用内容搜索和本文中的脚本在邮箱和 OneDrive for business 网站中搜索一组用户。
ms.openlocfilehash: 1d180d4b6deefd59a26b1e93f354c72810030718
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295495"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="10340-103">使用内容搜索在邮箱和 OneDrive for Business 站点中搜索用户列表</span><span class="sxs-lookup"><span data-stu-id="10340-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="10340-p101">Office 365 安全&amp;合规性中心提供了许多 Windows PowerShell cmdlet, 可让您自动执行耗时的电子数据展示相关任务。目前, 在安全&amp;合规中心中创建内容搜索以搜索大量的保管人内容位置需要花费时间和准备。在创建搜索之前, 您必须收集每个 OneDrive for business 网站的 URL, 然后将每个邮箱和 O neDrive for business 网站添加到搜索中。在将来的版本中, 这在安全&amp;合规中心中的工作更简单。在此之前, 可以使用本文中的脚本自动执行此过程。此脚本会提示您组织的 "我的用户" 域的名称 (例如\*\*\*\* , URL https://contoso-my.sharepoint.com)中的 contoso、用户电子邮件地址的列表、新内容搜索的名称以及要使用的搜索查询)。该脚本将获取列表中每个用户的 OneDrive for business URL, 然后使用您提供的搜索查询, 创建并启动搜索该列表中每个用户的邮箱和 OneDrive for business 网站的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="10340-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="10340-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="10340-111">Before you begin</span></span>

- <span data-ttu-id="10340-112">您必须是安全&amp;合规性中心中的电子数据展示管理器角色组的成员, SharePoint Online 全局管理员才能在步骤3中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="10340-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="10340-p102">请务必将您在步骤2中创建的用户列表和步骤3中的脚本保存到同一个文件夹中。这将使脚本运行变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="10340-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="10340-p103">该脚本包括最少的错误处理。其主要目的是快速轻松地搜索每个用户的邮箱和 OneDrive for business 网站。</span><span class="sxs-lookup"><span data-stu-id="10340-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="10340-p104">在任何 Microsoft standard 支持计划或服务下, 不支持本主题中提供的示例脚本。示例脚本按原样提供, 无需任何种类的担保。Microsoft 进一步拒绝所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)的 mplied 担保, 包括但不限于对适销性或特定用途适用性的任何暗示担保。因使用或性能示例脚本和文档而产生的全部风险都将保留给您。在任何情况下, Microsoft、其作者或对脚本的创建、生产或交付的其他任何人都有责任承担任何损害 (包括但不限于业务利润损失、业务中断和丢失造成的损失)。因使用或无法使用示例脚本或文档而引起的业务信息或其他 pecuniary 丢失, 即使 Microsoft 已被告知可能发生此类损坏的情况也是如此。</span><span class="sxs-lookup"><span data-stu-id="10340-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="10340-122">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="10340-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="10340-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="10340-123"></span></span>

<span data-ttu-id="10340-p105">第一步是安装 SharePoint Online 命令行管理程序。您不必在此过程中使用命令行管理程序, 但必须安装它, 因为它包含您在步骤3中运行的脚本所需的必备组件。这些先决条件允许脚本与 SharePoint Online 通信, 以获取 OneDrive for business 网站的 url。</span><span class="sxs-lookup"><span data-stu-id="10340-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="10340-127">转到[设置 sharepoint online 命令行管理程序 Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318)并执行步骤1和步骤 2, 安装 sharepoint online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="10340-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="10340-128">步骤 2: 生成用户列表</span><span class="sxs-lookup"><span data-stu-id="10340-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="10340-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="10340-129"></span></span>

<span data-ttu-id="10340-p106">步骤3中的脚本将创建内容搜索, 以便在邮箱和 OneDrive 帐户中搜索用户列表。您可以只在文本文件中键入电子邮件地址, 也可以在 Windows PowerShell 中运行命令, 以获取电子邮件地址列表, 并将其保存到文件中 (位于步骤3中将脚本保存到的同一文件夹中)。</span><span class="sxs-lookup"><span data-stu-id="10340-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="10340-132">下面是一个[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令, 您可以 runt 以获取组织中所有用户的电子邮件地址列表, 并将其保存到名为`Users.txt`的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="10340-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="10340-p107">运行此命令后, 请确保打开文件并删除包含属性名称的标头`PrimarySmtpAddress`。文本文件只应包含电子邮件地址列表, 不包含任何其他内容。请确保电子邮件地址列表前面或后面没有空行。</span><span class="sxs-lookup"><span data-stu-id="10340-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="10340-136">步骤 3: 运行脚本以创建并启动搜索</span><span class="sxs-lookup"><span data-stu-id="10340-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="10340-p108">在此步骤中运行脚本时, 它将提示您提供以下信息。在运行脚本之前, 请务必准备好此信息。</span><span class="sxs-lookup"><span data-stu-id="10340-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="10340-139">**您的用户凭据**-脚本将使用您的凭据访问 SharePoint Online, 以获取 OneDrive for business url, 并使用远程 PowerShell 连接&amp;到安全合规性中心。</span><span class="sxs-lookup"><span data-stu-id="10340-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="10340-p109">**您的 "我的网站" 域的名称**-"我的网站" 域是包含组织中所有 OneDrive for business 网站的域。例如, 如果您的 "我的用户" 域**https://contoso-my.sharepoint.com**的 URL 为, 那么`contoso`当脚本提示您输入您的 "我的用户" 域的名称时, 您就会输入该 URL。</span><span class="sxs-lookup"><span data-stu-id="10340-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="10340-p110">**第2步中的文本文件的路径名**-您在步骤2中创建的文本文件的路径名。如果文本文件和脚本位于同一文件夹中, 则输入文本文件的名称。否则, 请输入文本文件的完整路径名。</span><span class="sxs-lookup"><span data-stu-id="10340-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="10340-145">**内容搜索的名称**-将由脚本创建的内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="10340-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="10340-p111">**搜索查询**-将在其中创建和运行与内容搜索一起使用的搜索查询。有关搜索查询的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="10340-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="10340-148">**运行脚本:**</span><span class="sxs-lookup"><span data-stu-id="10340-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="10340-p112">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `SearchEXOOD4B.ps1`。将该文件保存到您在步骤2中保存用户列表的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="10340-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="10340-151">打开 Windows PowerShell 并转到您在其中保存脚本的文件夹和步骤2中的用户列表。</span><span class="sxs-lookup"><span data-stu-id="10340-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="10340-152">启动脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="10340-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="10340-153">当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="10340-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="10340-p113">当脚本提示时, 请输入以下信息。键入每条信息, 然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="10340-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="10340-156">您的 "我的用户" 域的名称。</span><span class="sxs-lookup"><span data-stu-id="10340-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="10340-157">包含用户列表的文本文件的路径名。</span><span class="sxs-lookup"><span data-stu-id="10340-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="10340-158">内容搜索的名称。</span><span class="sxs-lookup"><span data-stu-id="10340-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="10340-159">搜索查询 (将其留空可返回内容位置中的所有项)。</span><span class="sxs-lookup"><span data-stu-id="10340-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="10340-p114">此脚本获取每个 OneDrive for business 网站的 url, 然后创建并启动搜索。可以在 security & 合规性中心 PowerShell 中运行**new-compliancesearch** cmdlet 以显示搜索统计信息和结果, 也可以转到安全&amp;合规中心中的 "**内容搜索**" 页以查看有关搜索的信息。</span><span class="sxs-lookup"><span data-stu-id="10340-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
