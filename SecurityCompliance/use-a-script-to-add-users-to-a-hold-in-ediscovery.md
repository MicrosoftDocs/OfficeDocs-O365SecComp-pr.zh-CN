---
title: 使用脚本将用户添加到安全 & 合规性中心的电子数据展示事例中的保留项
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: 运行脚本以将邮箱和 OneDrive for business 网站快速添加到与安全 & 合规中心中的电子数据展示事例关联的新保留中。
ms.openlocfilehash: 992fddad3bfbc9f08855bd85d87b0edf92b3cdbe
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263974"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a><span data-ttu-id="b23c2-103">使用脚本将用户添加到安全 & 合规性中心的电子数据展示事例中的保留项</span><span class="sxs-lookup"><span data-stu-id="b23c2-103">Use a script to add users to a hold in an eDiscovery case in the Security & Compliance Center</span></span>

<span data-ttu-id="b23c2-104">Security & 合规性中心提供了大量 Windows PowerShell cmdlet, 可让您自动执行与创建和管理电子数据展示事例相关的耗时任务。</span><span class="sxs-lookup"><span data-stu-id="b23c2-104">The Security & Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="b23c2-105">目前, 使用安全 & 合规中心中的电子数据展示区分大小写工具将大量的保管人内容位置置于保留状态需要花费时间和准备。</span><span class="sxs-lookup"><span data-stu-id="b23c2-105">Currently, using the eDiscovery case tool in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="b23c2-106">例如, 在创建保留之前, 您必须收集要置于保留状态的每个 OneDrive for business 网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="b23c2-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="b23c2-107">然后, 对于要置于保留状态的每个用户, 都必须将其邮箱及其 OneDrive for business 网站添加到保留中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="b23c2-108">在未来版本的 Security & 合规性中心中, 这将变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="b23c2-108">In future releases of the Security & Compliance Center, this will get easier to do.</span></span> <span data-ttu-id="b23c2-109">在此之前, 可以使用本文中的脚本自动执行此过程。</span><span class="sxs-lookup"><span data-stu-id="b23c2-109">Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="b23c2-110">该脚本会提示您组织的 "我的用户" 域的名称 (例如\*\*\*\* , URL https://contoso-my.sharepoint.com)中的 contoso、现有电子数据展示事例的名称、与该事例关联的新保留的名称、所需用户的电子邮件地址的列表)将置于保留状态, 如果要创建基于查询的保留, 则使用搜索查询。</span><span class="sxs-lookup"><span data-stu-id="b23c2-110">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="b23c2-111">然后, 该脚本获取列表中每个用户的 OneDrive for business 网站的 URL, 创建新保留, 然后将列表中每个用户的邮箱和 OneDrive for business 网站添加到保留。</span><span class="sxs-lookup"><span data-stu-id="b23c2-111">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="b23c2-112">该脚本还会生成包含有关新保留的信息的日志文件。</span><span class="sxs-lookup"><span data-stu-id="b23c2-112">The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="b23c2-113">下面介绍了实现这一点的步骤:</span><span class="sxs-lookup"><span data-stu-id="b23c2-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="b23c2-114">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="b23c2-114">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="b23c2-115">步骤 2: 生成用户列表</span><span class="sxs-lookup"><span data-stu-id="b23c2-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="b23c2-116">步骤 3: 运行脚本以创建保留项并添加用户</span><span class="sxs-lookup"><span data-stu-id="b23c2-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="b23c2-117">准备工作</span><span class="sxs-lookup"><span data-stu-id="b23c2-117">Before you begin</span></span>

- <span data-ttu-id="b23c2-118">您必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员, SharePoint Online 全局管理员才能在步骤3中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="b23c2-118">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span> <span data-ttu-id="b23c2-119">有关详细信息, 请参阅[在 Office 365 安全 & 合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b23c2-119">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="b23c2-120">最多可以将1000个邮箱和100网站添加到与 Security & 合规性中心中的电子数据展示事例相关联的保留中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-120">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="b23c2-121">假定您要置于保留状态的每个用户都有 OneDrive for business 网站, 则可以使用本文中的脚本将最多100个用户添加到保留中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-121">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="b23c2-122">请务必将您在步骤2中创建的用户列表和步骤3中的脚本保存到同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-122">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="b23c2-123">这将使脚本运行变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="b23c2-123">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="b23c2-124">该脚本将用户列表添加到与现有事例相关联的新保留中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-124">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="b23c2-125">在运行脚本之前, 请确保已创建要与保留关联的事例。</span><span class="sxs-lookup"><span data-stu-id="b23c2-125">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="b23c2-126">该脚本包括最少的错误处理。</span><span class="sxs-lookup"><span data-stu-id="b23c2-126">The script includes minimal error handling.</span></span> <span data-ttu-id="b23c2-127">其主要目的是快速轻松地将每个用户的邮箱和 OneDrive for business 网站置于保留状态。</span><span class="sxs-lookup"><span data-stu-id="b23c2-127">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="b23c2-p108">本主题中的示例脚本不受任何 Microsoft 标准支持计划或服务支持。示例脚本按原样提供，不提供任何种类的担保。Microsoft 进一步声明，不提供任何默示担保，包括但不限于适销性或特定用途适用性的默示担保。使用或运行示例脚本和文档所产生的任何风险均由你自己承担。对于因使用或无法使用示例脚本或文档而产生的任何损失（包括但不限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者或参与创建、生成或交付脚本的任何人都不承担任何责任，即使 Microsoft 已被告知存在这种损失的可能性，也不例外。</span><span class="sxs-lookup"><span data-stu-id="b23c2-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="b23c2-133">步骤 1：安装 SharePoint Online 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="b23c2-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="b23c2-134">第一步是安装 SharePoint Online 命令行管理程序 (如果它尚未安装在本地计算机上)。</span><span class="sxs-lookup"><span data-stu-id="b23c2-134">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="b23c2-135">您不必在此过程中使用命令行管理程序, 但必须安装它, 因为它包含您在步骤3中运行的脚本所需的必备组件。</span><span class="sxs-lookup"><span data-stu-id="b23c2-135">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="b23c2-136">这些先决条件允许脚本与 SharePoint Online 通信, 以获取 OneDrive for business 网站的 url。</span><span class="sxs-lookup"><span data-stu-id="b23c2-136">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="b23c2-137">转到[设置 sharepoint online 命令行管理程序 Windows PowerShell 环境](https://go.microsoft.com/fwlink/p/?LinkID=286318), 并执行步骤1和步骤 2, 在本地计算机上安装 sharepoint online 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b23c2-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="b23c2-138">步骤 2: 生成用户列表</span><span class="sxs-lookup"><span data-stu-id="b23c2-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="b23c2-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="b23c2-139"></span></span>

<span data-ttu-id="b23c2-140">步骤3中的脚本将创建与电子数据展示事例相关联的保留, 并将用户列表中的邮箱和 OneDrive for business 网站添加到保留。</span><span class="sxs-lookup"><span data-stu-id="b23c2-140">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="b23c2-141">您可以只在文本文件中键入电子邮件地址, 也可以在 Windows PowerShell 中运行命令, 以获取电子邮件地址列表, 并将其保存到文件中 (位于步骤3中将脚本保存到的同一文件夹中)。</span><span class="sxs-lookup"><span data-stu-id="b23c2-141">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="b23c2-142">下面是一个 PowerShell 命令 (通过使用连接到 Exchange Online 组织的远程 PowerShell 运行) 来获取组织中所有用户的电子邮件地址列表, 并将其保存到名为 HoldUsers 的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="b23c2-143">运行此命令后, 打开文本文件并删除包含属性名称的标头`PrimarySmtpAddress`。</span><span class="sxs-lookup"><span data-stu-id="b23c2-143">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="b23c2-144">然后删除除您要添加到您在步骤3中创建的保留项的用户之外的所有电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b23c2-144">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="b23c2-145">请确保电子邮件地址列表前面或后面没有空行。</span><span class="sxs-lookup"><span data-stu-id="b23c2-145">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="b23c2-146">步骤 3: 运行脚本以创建保留项并添加用户</span><span class="sxs-lookup"><span data-stu-id="b23c2-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="b23c2-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="b23c2-147"></span></span>

<span data-ttu-id="b23c2-148">在此步骤中运行脚本时, 它将提示您提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="b23c2-148">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="b23c2-149">在运行脚本之前, 请务必准备好此信息。</span><span class="sxs-lookup"><span data-stu-id="b23c2-149">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="b23c2-150">**你的用户凭据**-脚本将使用你的凭据通过远程 PowerShell 连接到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="b23c2-150">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="b23c2-151">此外, 它还将使用这些凭据访问 SharePoint Online, 以获取用户列表的 OneDrive for business url。</span><span class="sxs-lookup"><span data-stu-id="b23c2-151">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="b23c2-152">**您的 "我的网站" 域的名称**-"我的网站" 域是包含组织中所有 OneDrive for business 网站的域。</span><span class="sxs-lookup"><span data-stu-id="b23c2-152">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="b23c2-153">例如, 如果您的 "我的用户" 域**https://contoso-my.sharepoint.com**的 URL 为, 那么`contoso`当脚本提示您输入您的 "我的用户" 域的名称时, 您就会输入该 URL。</span><span class="sxs-lookup"><span data-stu-id="b23c2-153">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="b23c2-154">**事例的名称**-现有事例的名称。</span><span class="sxs-lookup"><span data-stu-id="b23c2-154">**Name of the case** - The name of an existing case.</span></span> <span data-ttu-id="b23c2-155">该脚本将创建与此事例关联的新保留。</span><span class="sxs-lookup"><span data-stu-id="b23c2-155">The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="b23c2-156">**保留的名称**-将创建脚本的保留名称, 并将其与指定的事例相关联。</span><span class="sxs-lookup"><span data-stu-id="b23c2-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="b23c2-157">**基于查询的保留的搜索查询**-您可以创建基于查询的保留, 以便在保留时仅放置满足指定搜索条件的内容。</span><span class="sxs-lookup"><span data-stu-id="b23c2-157">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="b23c2-158">若要将所有内容置于保留状态, 只需在收到搜索查询时按**enter** 。</span><span class="sxs-lookup"><span data-stu-id="b23c2-158">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="b23c2-159">**是否打开保留**-您可以让脚本在创建保留后将其关闭, 也可以让脚本在不启用保留的情况下创建保留。</span><span class="sxs-lookup"><span data-stu-id="b23c2-159">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="b23c2-160">如果没有启用保留的脚本, 可以稍后在 Security & 合规性中心中打开它, 也可以运行以下 PowerShell 命令:</span><span class="sxs-lookup"><span data-stu-id="b23c2-160">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="b23c2-161">包含**用户列表的文本文件的名称**-步骤2中包含要添加到保留的用户列表的文本文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b23c2-161">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="b23c2-162">如果此文件与脚本位于同一文件夹中, 只需键入该文件的名称 (例如, HoldUsers)。</span><span class="sxs-lookup"><span data-stu-id="b23c2-162">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="b23c2-163">如果文本文件在另一个文件夹中, 请键入该文件的完整路径名。</span><span class="sxs-lookup"><span data-stu-id="b23c2-163">If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="b23c2-164">收集脚本将提示输入的信息后, 最后一步是运行脚本以创建新的保留并向其添加用户。</span><span class="sxs-lookup"><span data-stu-id="b23c2-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="b23c2-165">使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `AddUsersToHold.ps1`。</span><span class="sxs-lookup"><span data-stu-id="b23c2-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
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

2. <span data-ttu-id="b23c2-166">在本地计算机上, 打开 Windows PowerShell 并转到保存该脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b23c2-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="b23c2-167">运行脚本;例如:</span><span class="sxs-lookup"><span data-stu-id="b23c2-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="b23c2-168">输入脚本提示您输入的信息。</span><span class="sxs-lookup"><span data-stu-id="b23c2-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="b23c2-169">该脚本将连接到安全 & 合规中心 PowerShell, 然后在电子数据展示事例中创建新的保留, 并为列表中的用户添加邮箱和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="b23c2-169">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="b23c2-170">您可以转到 Security & 合规性中心中的**电子数据展示**页面上的事例, 以查看新的保留。</span><span class="sxs-lookup"><span data-stu-id="b23c2-170">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="b23c2-171">脚本运行完毕后, 它会创建以下日志文件, 并将其保存到脚本所在的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="b23c2-172">**LocationsOnHold** -包含脚本成功置于保留状态的邮箱和 OneDrive for business 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="b23c2-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="b23c2-173">**LocationsNotOnHold** -包含该脚本未置于保留状态的邮箱和 OneDrive for business 网站的列表。</span><span class="sxs-lookup"><span data-stu-id="b23c2-173">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="b23c2-174">如果用户具有邮箱, 而不是 onedrive for business 网站, 则该用户将包含在未置于保留状态的 OneDrive for business 网站列表中。</span><span class="sxs-lookup"><span data-stu-id="b23c2-174">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="b23c2-175">**GetCaseHoldPolicy** -包含新保留的**CaseHoldPolicy** cmdlet 的输出, 在创建新保留后, 脚本将运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b23c2-175">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="b23c2-176">此 cmdlet 返回的信息包括其邮箱和 OneDrive for business 网站置于保留状态以及是否启用或禁用保留的用户列表。</span><span class="sxs-lookup"><span data-stu-id="b23c2-176">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="b23c2-177">**GetCaseHoldRule** -包含新保留的**new-caseholdrule** cmdlet 的输出, 在创建新保留后, 脚本将运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b23c2-177">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="b23c2-178">如果您使用脚本创建基于查询的保留, 则此 cmdlet 返回的信息包括搜索查询。</span><span class="sxs-lookup"><span data-stu-id="b23c2-178">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
