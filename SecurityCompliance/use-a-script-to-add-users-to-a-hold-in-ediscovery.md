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
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="a5718-103">使用脚本来将用户添加到保留项中 Office 365 安全性电子数据展示事例&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="a5718-103">Use a script to add users to a hold in an eDiscovery case in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="a5718-p101">Office 365 安全性&amp;合规性中心提供了大量让您的 Windows PowerShell cmdlet 自动执行耗时的任务与创建和管理电子数据展示事例。目前，在安全中使用电子数据展示案例工具&amp;合规性中心，以将置于保持状态的大量 custodian 内容位置需要花费时间并准备。例如，在创建保留项之前，您需要收集的每个 OneDrive for Business 站点您想要将置于保持状态的 URL。然后为每个用户，您想要将置于保持状态，您必须将其邮箱和 OneDrive for Business 站点添加到保留项。在将来版本的安全&amp;合规性中心，这会更轻松地执行操作。之前，您可以使用该脚本本文中自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="a5718-p101">The Office 365 Security &amp; Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases. Currently, using the eDiscovery case tool in the Security &amp; Compliance Center to place a large number of custodian content locations on hold takes time and preparation. For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold. Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold. In future releases of the Security &amp; Compliance Center, this will get easier to do. Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="a5718-p102">该脚本会提示您输入您的组织 MySite 域的名称 (例如， **contoso**在 URL https://contoso-my.sharepoint.com)、 的现有电子数据展示事例的名称、 新的保留项的名称与案例关联、 所需的用户的电子邮件地址列表要将置于保持状态，并使用如果您想要创建基于查询的保留的搜索查询。脚本然后获取 OneDrive for Business 站点列表中每个用户的 URL、 创建新的保留，，然后添加了邮箱和 OneDrive 列表中的每个用户的业务网站到保留项。脚本还会生成日志文件包含有关新保留的信息。</span><span class="sxs-lookup"><span data-stu-id="a5718-p102">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold. The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold. The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="a5718-113">下面是做到这一点的步骤：</span><span class="sxs-lookup"><span data-stu-id="a5718-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="a5718-114">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="a5718-114">Step 1: Install the SharePoint Online Management Shell</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[<span data-ttu-id="a5718-115">步骤 2： 生成用户的列表</span><span class="sxs-lookup"><span data-stu-id="a5718-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="a5718-116">步骤 3： 运行脚本来创建保留项，并添加用户</span><span class="sxs-lookup"><span data-stu-id="a5718-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="a5718-117">准备工作</span><span class="sxs-lookup"><span data-stu-id="a5718-117">Before you begin</span></span>

- <span data-ttu-id="a5718-p103">您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心和 SharePoint Online 全局管理员才能在步骤 3 中运行该脚本。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="a5718-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="a5718-p104">最多 1000 个邮箱和 100 个网站可以添加到保留项与安全中电子数据展示事例相关联的&amp;合规性中心。假定您想要将置于保持状态的每个用户具有的 OneDrive for Business 站点，您可以最多 100 个用户添加到保留项使用本文中的脚本。</span><span class="sxs-lookup"><span data-stu-id="a5718-p104">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security &amp; Compliance Center. Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="a5718-p105">请务必保存您在步骤 2 和步骤 3 中的脚本保存到同一文件夹中创建的用户列表。将更加轻松地运行脚本。</span><span class="sxs-lookup"><span data-stu-id="a5718-p105">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="a5718-p106">该脚本将用户列表添加到新的保留项与现有用例。确保运行脚本之前创建的情况下，您想要将与保留项相关联。</span><span class="sxs-lookup"><span data-stu-id="a5718-p106">The script adds the list of users to a new hold that is associated with an existing case. Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="a5718-p107">该脚本包括最少的错误处理。其主要用途是快速、 方便地放置邮箱和 OneDrive for Business 站点上的每个用户的保留。</span><span class="sxs-lookup"><span data-stu-id="a5718-p107">The script includes minimal error handling. Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="a5718-p108">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="a5718-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="a5718-133">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="a5718-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="a5718-p109">第一步是安装 SharePoint Online Management Shell，如果您的本地计算机上尚未安装。您无需在此过程中，使用命令行管理程序，但您必须安装，因为它包含必备组件所需的步骤 3 中运行的脚本。这些先决条件允许脚本与 SharePoint Online，从而获得 OneDrive for Business 站点的 Url 进行通信。</span><span class="sxs-lookup"><span data-stu-id="a5718-p109">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="a5718-137">转到[设置 SharePoint Online Management Shell Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318)并执行步骤 1 和步骤 2 以在本地计算机上安装 SharePoint Online Management Shell。</span><span class="sxs-lookup"><span data-stu-id="a5718-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="a5718-138">步骤 2： 生成用户的列表</span><span class="sxs-lookup"><span data-stu-id="a5718-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="a5718-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="a5718-139"></span></span>

<span data-ttu-id="a5718-p110">步骤 3 中的脚本将创建保留项具有与关联的电子数据展示事例，并添加邮箱和 OneDrive for Business 站点的用户迁移到保留项的列表。在文本文件中，只需键入电子邮件地址或您可以在 Windows PowerShell，可以获取的电子邮件地址列表，并将其保存到文件 （位于相同将在步骤 3 中保存到脚本的文件夹中） 运行命令。</span><span class="sxs-lookup"><span data-stu-id="a5718-p110">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="a5718-142">下面是 PowerShell 命令 （即运行使用远程 PowerShell 连接到 Exchange Online 组织时） 获取组织中的所有用户的电子邮件地址列表，并将其保存到文本文件名为 HoldUsers.txt。</span><span class="sxs-lookup"><span data-stu-id="a5718-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="a5718-p111">在运行此命令，打开文本文件并删除包含属性名称的标头后`PrimarySmtpAddress`。然后删除除了您想要添加到保留项的步骤 3 中，您将创建的用户属性的所有电子邮件地址。请确保没有空白行之前或之后的电子邮件地址列表。</span><span class="sxs-lookup"><span data-stu-id="a5718-p111">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`. Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="a5718-146">步骤 3： 运行脚本来创建保留项，并添加用户</span><span class="sxs-lookup"><span data-stu-id="a5718-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="a5718-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="a5718-147"></span></span>

<span data-ttu-id="a5718-p112">在此步骤中运行该脚本时，它将提示您输入以下信息。请务必在运行脚本之前已准备好此信息。</span><span class="sxs-lookup"><span data-stu-id="a5718-p112">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="a5718-p113">**您的用户凭据**-脚本将使用您的凭据来连接到安全性&amp;使用远程 PowerShell 合规性中心。它会将这些凭据以访问 SharePoint Online 获取 OneDrive 业务 Url 的用户列表。</span><span class="sxs-lookup"><span data-stu-id="a5718-p113">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center with remote PowerShell. It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="a5718-p114">**我的网站域的名称**-我的网站域是包含所有 OneDrive for Business 组织中的网站的域。例如，如果您我的网站的域的 URL 是**https://contoso-my.sharepoint.com**，然后输入`contoso`时脚本提示您进行 MySite 域的名称。</span><span class="sxs-lookup"><span data-stu-id="a5718-p114">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="a5718-p115">**用例的名称**-现有用例的名称。该脚本将创建新保留与这种情况下相关联。</span><span class="sxs-lookup"><span data-stu-id="a5718-p115">**Name of the case** - The name of an existing case. The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="a5718-156">**保留项的名称**-保留该脚本将创建并将与指定用例的名称。</span><span class="sxs-lookup"><span data-stu-id="a5718-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="a5718-p116">**基于查询的搜索查询保留**-您可以创建基于查询的保留，以便满足指定的搜索条件的内容置于保持状态。若要将置于保持状态的所有内容，只需按**Enter**时提示您进行搜索查询。</span><span class="sxs-lookup"><span data-stu-id="a5718-p116">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold. To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="a5718-p117">**是否启用保留**-您可以在创建或您可以创建保留项而使其该脚本后打开保留项的脚本。如果您没有打开保留项的脚本，您可以将其打开安全更高版本中&amp;合规性中心或通过运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="a5718-p117">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it. If you don't have the script turn on the hold, you can turn it on later in the Security &amp; Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="a5718-p118">**使用的用户列表的文本文件的名称**-从步骤 2 包含用户添加到保留项列表的文本文件的名称。如果此文件位于为脚本的同一文件夹中，只需键入文件 (例如，HoldUsers.txt) 的名称。如果该文本文件位于另一个文件夹中，键入文件的完整路径名。</span><span class="sxs-lookup"><span data-stu-id="a5718-p118">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold. If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt). If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="a5718-164">您已收集了该脚本将提示您输入的信息后，最后一步是运行脚本以创建新的保留并向其添加用户。</span><span class="sxs-lookup"><span data-stu-id="a5718-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="a5718-165">使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `AddUsersToHold.ps1`。</span><span class="sxs-lookup"><span data-stu-id="a5718-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
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

2. <span data-ttu-id="a5718-166">在本地计算机上打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a5718-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="a5718-167">运行脚本。例如：</span><span class="sxs-lookup"><span data-stu-id="a5718-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="a5718-168">输入该脚本将提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="a5718-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="a5718-p119">脚本连接到安全性和合规性中心 PowerShell 中，然后创建新的保留项中电子数据展示事例并添加列表中的用户的邮箱和 OneDrive for Business。您可以转到这种情况在安全的**电子数据展示**页上&amp;合规性中心以查看新的保留。</span><span class="sxs-lookup"><span data-stu-id="a5718-p119">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list. You can go to the case on the **eDiscovery** page in the Security &amp; Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="a5718-171">完成该脚本后运行，创建以下日志文件，并将其保存到该脚本所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a5718-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="a5718-172">**LocationsOnHold.txt** -包含脚本成功置于保留的业务网站邮箱和 OneDrive 的列表。</span><span class="sxs-lookup"><span data-stu-id="a5718-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="a5718-p120">**LocationsNotOnHold.txt** -包含脚本不会置于保持状态的业务网站邮箱和 OneDrive 的列表。如果用户具有邮箱，但不是 OneDrive for Business 站点，用户将包含不置于保持状态的业务网站 OneDrive 的列表中。</span><span class="sxs-lookup"><span data-stu-id="a5718-p120">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold. If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="a5718-p121">**GetCaseHoldPolicy.txt** -包含的新保留，创建新的保留项后运行该脚本**Get CaseHoldPolicy** cmdlet 的输出。使用此 cmdlet 返回的信息包括其邮箱和 OneDrive for Business 站点被置于保持状态并保留项是启用还是禁用的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="a5718-p121">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="a5718-p122">**GetCaseHoldRule.txt** -包含的新保留，创建新的保留项后运行该脚本**Get CaseHoldRule** cmdlet 的输出。如果您使用脚本来创建基于查询的保留，则此 cmdlet 返回的信息包括搜索查询。</span><span class="sxs-lookup"><span data-stu-id="a5718-p122">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
