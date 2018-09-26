---
title: 使用脚本来将用户添加到保留项中 Office 365 安全性电子数据展示事例&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: 运行脚本以快速添加邮箱和 OneDrive for Business 站点到新的保留项与 Office 365 安全性电子数据展示事例相关联的&amp;合规性中心。
ms.openlocfilehash: 2c93deb14bc8c1f89dab7bb054d2e94db06cfbd5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038255"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a>使用脚本来将用户添加到保留项中 Office 365 安全性电子数据展示事例&amp;合规性中心

Office 365 安全性&amp;合规性中心提供了大量让您的 Windows PowerShell cmdlet 自动执行耗时的任务与创建和管理电子数据展示事例。目前，在安全中使用电子数据展示案例工具&amp;合规性中心，以将置于保持状态的大量 custodian 内容位置需要花费时间并准备。例如，在创建保留项之前，您需要收集的每个 OneDrive for Business 站点您想要将置于保持状态的 URL。然后为每个用户，您想要将置于保持状态，您必须将其邮箱和 OneDrive for Business 站点添加到保留项。在将来版本的安全&amp;合规性中心，这会更轻松地执行操作。之前，您可以使用该脚本本文中自动执行此过程。
  
该脚本会提示您输入您的组织 MySite 域的名称 (例如， **contoso**在 URL https://contoso-my.sharepoint.com)、 的现有电子数据展示事例的名称、 新的保留项的名称与案例关联、 所需的用户的电子邮件地址列表要将置于保持状态，并使用如果您想要创建基于查询的保留的搜索查询。脚本然后获取 OneDrive for Business 站点列表中每个用户的 URL、 创建新的保留，，然后添加了邮箱和 OneDrive 列表中的每个用户的业务网站到保留项。脚本还会生成日志文件包含有关新保留的信息。 
  
下面是做到这一点的步骤：
  
[步骤 1：安装 SharePoint Online 命令行管理程序](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[步骤 2： 生成用户的列表](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[步骤 3： 运行脚本来创建保留项，并添加用户](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>准备工作

- 您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心和 SharePoint Online 全局管理员才能在步骤 3 中运行该脚本。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
    
- 最多 1000 个邮箱和 100 个网站可以添加到保留项与安全中电子数据展示事例相关联的&amp;合规性中心。假定您想要将置于保持状态的每个用户具有的 OneDrive for Business 站点，您可以最多 100 个用户添加到保留项使用本文中的脚本。 
    
- 请务必保存您在步骤 2 和步骤 3 中的脚本保存到同一文件夹中创建的用户列表。将更加轻松地运行脚本。
    
- 该脚本将用户列表添加到新的保留项与现有用例。确保运行脚本之前创建的情况下，您想要将与保留项相关联。
    
- 该脚本包括最少的错误处理。其主要用途是快速、 方便地放置邮箱和 OneDrive for Business 站点上的每个用户的保留。
    
- 本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>步骤 1：安装 SharePoint Online 命令行管理程序

第一步是安装 SharePoint Online Management Shell，如果您的本地计算机上尚未安装。您无需在此过程中，使用命令行管理程序，但您必须安装，因为它包含必备组件所需的步骤 3 中运行的脚本。这些先决条件允许脚本与 SharePoint Online，从而获得 OneDrive for Business 站点的 Url 进行通信。
  
转到[设置 SharePoint Online Management Shell Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318)并执行步骤 1 和步骤 2 以在本地计算机上安装 SharePoint Online Management Shell。 

## <a name="step-2-generate-a-list-of-users"></a>步骤 2： 生成用户的列表
<a name="step2"> </a>

步骤 3 中的脚本将创建保留项具有与关联的电子数据展示事例，并添加邮箱和 OneDrive for Business 站点的用户迁移到保留项的列表。在文本文件中，只需键入电子邮件地址或您可以在 Windows PowerShell，可以获取的电子邮件地址列表，并将其保存到文件 （位于相同将在步骤 3 中保存到脚本的文件夹中） 运行命令。
  
下面是 PowerShell 命令 （即运行使用远程 PowerShell 连接到 Exchange Online 组织时） 获取组织中的所有用户的电子邮件地址列表，并将其保存到文本文件名为 HoldUsers.txt。
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

在运行此命令，打开文本文件并删除包含属性名称的标头后`PrimarySmtpAddress`。然后删除除了您想要添加到保留项的步骤 3 中，您将创建的用户属性的所有电子邮件地址。请确保没有空白行之前或之后的电子邮件地址列表。
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>步骤 3： 运行脚本来创建保留项，并添加用户
<a name="step3"> </a>

在此步骤中运行该脚本时，它将提示您输入以下信息。请务必在运行脚本之前已准备好此信息。
  
- **您的用户凭据**-脚本将使用您的凭据来连接到安全性&amp;使用远程 PowerShell 合规性中心。它会将这些凭据以访问 SharePoint Online 获取 OneDrive 业务 Url 的用户列表。
    
- **我的网站域的名称**-我的网站域是包含所有 OneDrive for Business 组织中的网站的域。例如，如果您我的网站的域的 URL 是**https://contoso-my.sharepoint.com**，然后输入`contoso`时脚本提示您进行 MySite 域的名称。 
    
- **用例的名称**-现有用例的名称。该脚本将创建新保留与这种情况下相关联。
    
- **保留项的名称**-保留该脚本将创建并将与指定用例的名称。
    
- **基于查询的搜索查询保留**-您可以创建基于查询的保留，以便满足指定的搜索条件的内容置于保持状态。若要将置于保持状态的所有内容，只需按**Enter**时提示您进行搜索查询。 
    
- **是否启用保留**-您可以在创建或您可以创建保留项而使其该脚本后打开保留项的脚本。如果您没有打开保留项的脚本，您可以将其打开安全更高版本中&amp;合规性中心或通过运行以下 PowerShell 命令： 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **使用的用户列表的文本文件的名称**-从步骤 2 包含用户添加到保留项列表的文本文件的名称。如果此文件位于为脚本的同一文件夹中，只需键入文件 (例如，HoldUsers.txt) 的名称。如果该文本文件位于另一个文件夹中，键入文件的完整路径名。
    
您已收集了该脚本将提示您输入的信息后，最后一步是运行脚本以创建新的保留并向其添加用户。
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `AddUsersToHold.ps1`。
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Office 365 Security &amp; Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Office 365 Security &amp; Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
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
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. 在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。
    
3. 运行脚本。例如：
    
      ```
    .\AddUsersToHold.ps1
      ```

4. 输入该脚本将提示您输入的信息。
    
    脚本连接到安全性和合规性中心 PowerShell 中，然后创建新的保留项中电子数据展示事例并添加列表中的用户的邮箱和 OneDrive for Business。您可以转到这种情况在安全的**电子数据展示**页上&amp;合规性中心以查看新的保留。 
    
完成该脚本后运行，创建以下日志文件，并将其保存到该脚本所在的文件夹。
  
- **LocationsOnHold.txt** -包含脚本成功置于保留的业务网站邮箱和 OneDrive 的列表。
    
- **LocationsNotOnHold.txt** -包含脚本不会置于保持状态的业务网站邮箱和 OneDrive 的列表。如果用户具有邮箱，但不是 OneDrive for Business 站点，用户将包含不置于保持状态的业务网站 OneDrive 的列表中。
    
- **GetCaseHoldPolicy.txt** -包含的新保留，创建新的保留项后运行该脚本**Get CaseHoldPolicy** cmdlet 的输出。使用此 cmdlet 返回的信息包括其邮箱和 OneDrive for Business 站点被置于保持状态并保留项是启用还是禁用的用户的列表。 
    
- **GetCaseHoldRule.txt** -包含的新保留，创建新的保留项后运行该脚本**Get CaseHoldRule** cmdlet 的输出。如果您使用脚本来创建基于查询的保留，则此 cmdlet 返回的信息包括搜索查询。 
