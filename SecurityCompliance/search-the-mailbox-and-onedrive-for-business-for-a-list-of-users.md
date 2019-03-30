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
ms.openlocfilehash: 2f0954bf7822ca6c82165ad20b2c732ab0594257
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001275"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>使用内容搜索在邮箱和 OneDrive for Business 站点中搜索用户列表

Security & 合规性中心提供了许多 Windows PowerShell cmdlet, 可让您自动执行耗时和电子数据展示相关的任务。 目前, 在安全 & 合规中心中创建内容搜索, 以搜索大量的保管人内容位置并准备时间。 在创建搜索之前, 您必须收集每个 OneDrive for business 网站的 URL, 然后将每个邮箱和 O neDrive for business 网站添加到搜索中。 在将来的版本中, 这在安全 & 合规中心中的工作更简单。 在此之前, 可以使用本文中的脚本自动执行此过程。 此脚本会提示您组织的 "我的用户" 域的名称 (例如**** , URL https://contoso-my.sharepoint.com)中的 contoso、用户电子邮件地址的列表、新内容搜索的名称以及要使用的搜索查询)。 该脚本将获取列表中每个用户的 OneDrive for business URL, 然后使用您提供的搜索查询, 创建并启动搜索该列表中每个用户的邮箱和 OneDrive for business 网站的内容搜索。 
  
## <a name="before-you-begin"></a>开始之前

- 您必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员, SharePoint Online 全局管理员才能在步骤3中运行该脚本。
    
- 请务必将您在步骤2中创建的用户列表和步骤3中的脚本保存到同一个文件夹中。 这将使脚本运行变得更加简单。
    
- 该脚本包括最少的错误处理。 其主要目的是快速轻松地搜索每个用户的邮箱和 OneDrive for business 网站。
    
- 在任何 Microsoft standard 支持计划或服务下, 不支持本主题中提供的示例脚本。 示例脚本按原样提供，不提供任何类型的担保。 Microsoft 进一步拒绝所有我[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)的 mplied 担保, 包括但不限于对适销性或特定用途适用性的任何暗示担保。 因使用或执行示例脚本和文档的风险均由您自己承担。 对于因使用或无法使用示例脚本或文档产生的任何损害（包括但不仅限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者以及参与脚本创建、生成或交付的任何人均不承担任何责任，即使 Microsoft 已被告知此类损害的可能性也是如此。
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序
<a name="step1"> </a>

第一步是安装 SharePoint Online 命令行管理程序。 您不必在此过程中使用命令行管理程序, 但必须安装它, 因为它包含您在步骤3中运行的脚本所需的必备组件。 这些先决条件允许脚本与 SharePoint Online 通信, 以获取 OneDrive for business 网站的 url。
  
转到[设置 sharepoint online 命令行管理程序 Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318)并执行步骤1和步骤 2, 安装 sharepoint online 命令行管理程序。
  
## <a name="step-2-generate-a-list-of-users"></a>步骤 2: 生成用户列表
<a name="step2"> </a>

步骤3中的脚本将创建内容搜索, 以便在邮箱和 OneDrive 帐户中搜索用户列表。 您可以只在文本文件中键入电子邮件地址, 也可以在 Windows PowerShell 中运行命令, 以获取电子邮件地址列表, 并将其保存到文件中 (位于步骤3中将脚本保存到的同一文件夹中)。
  
下面是一个[Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)命令, 您可以 runt 以获取组织中所有用户的电子邮件地址列表, 并将其保存到名为`Users.txt`的文本文件中。 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

运行此命令后, 请确保打开文件并删除包含属性名称的标头`PrimarySmtpAddress`。 文本文件只应包含电子邮件地址列表, 不包含任何其他内容。 请确保电子邮件地址列表前面或后面没有空行。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>步骤 3: 运行脚本以创建并启动搜索

在此步骤中运行脚本时, 它将提示您提供以下信息。 在运行脚本之前, 请务必准备好此信息。
  
- **你的用户凭据**-脚本将使用你的凭据访问 SharePoint Online 以获取 OneDrive for business url, 并使用远程 PowerShell 连接到安全 & 合规性中心。 
    
- **您的 "我的网站" 域的名称**-"我的网站" 域是包含组织中所有 OneDrive for business 网站的域。 例如, 如果您的 "我的用户" 域**https://contoso-my.sharepoint.com**的 URL 为, 那么`contoso`当脚本提示您输入您的 "我的用户" 域的名称时, 您就会输入该 URL。 
    
- **第2步中的文本文件的路径名**-您在步骤2中创建的文本文件的路径名。 如果文本文件和脚本位于同一文件夹中, 则输入文本文件的名称。 否则, 请输入文本文件的完整路径名。 
    
- **内容搜索的名称**-将由脚本创建的内容搜索的名称。 
    
- **搜索查询**-将在其中创建和运行与内容搜索一起使用的搜索查询。 有关搜索查询的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。


**若要运行该脚本，请执行下列操作：**
    
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `SearchEXOOD4B.ps1`。 将该文件保存到您在步骤2中保存用户列表的同一文件夹中。
    
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

2. 打开 Windows PowerShell 并转到您在其中保存脚本的文件夹和步骤2中的用户列表。
    
3. 启动脚本;例如:
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. 当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。 
    
5. 当脚本提示时, 请输入以下信息。 键入每条信息, 然后按**enter**。
    
    - 您的 "我的用户" 域的名称。 
    
    - 包含用户列表的文本文件的路径名。
    
    - 内容搜索的名称。
    
    - 搜索查询 (将其留空可返回内容位置中的所有项)。
    
    此脚本获取每个 OneDrive for business 网站的 url, 然后创建并启动搜索。 您可以在 security & 合规中心 PowerShell 中运行**new-compliancesearch** cmdlet 以显示搜索统计信息和结果, 也可以转到 security & 合规性中心中的 "**内容搜索**" 页以查看信息关于搜索。 
