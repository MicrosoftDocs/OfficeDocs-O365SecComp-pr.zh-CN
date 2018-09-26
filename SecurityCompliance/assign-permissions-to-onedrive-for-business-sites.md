---
title: 为 OneDrive for Business 站点分配电子数据展示权限
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: 可以使用 SharePoint Online 中的电子数据展示中心搜索特定关键字、 敏感信息和其他搜索条件组织中的所有 OneDrive for Business 站点。您的组织中的每个用户是 OneDrive for Business 站点，位于名为网站集的所有者https://domain-my.sharepoint.com。默认情况下，Office 365 全局管理员或合规性管理器无法使用 SharePoint Online 中的电子数据展示中心搜索任何 OneDrive for Business 站点。若要搜索的 OneDrive for Business 站点、 管理员或合规性管理员必须是网站集管理员的 onedrive for Business 站点。
ms.openlocfilehash: 61f068a03bcce599d9f1b7eb62d7b317b7feab68
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038085"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a><span data-ttu-id="84929-106">为 OneDrive for Business 站点分配电子数据展示权限</span><span class="sxs-lookup"><span data-stu-id="84929-106">Assign eDiscovery permissions to OneDrive for Business sites</span></span>

<span data-ttu-id="84929-p102">可以使用 SharePoint Online 中的电子数据展示中心搜索特定关键字、 敏感信息和其他搜索条件组织中的所有 OneDrive for Business 站点。您的组织中的每个用户是 OneDrive for Business 站点，位于名为网站集的所有者https://domain-my.sharepoint.com。默认情况下，Office 365 全局管理员或合规性管理器无法使用 SharePoint Online 中的电子数据展示中心搜索任何 OneDrive for Business 站点。若要搜索的 OneDrive for Business 站点、 管理员或合规性管理员必须是网站集管理员的 onedrive for Business 站点。</span><span class="sxs-lookup"><span data-stu-id="84929-p102">You can use the eDiscovery Center in SharePoint Online to search all OneDrive for Business sites in your organization for certain keywords, sensitive information, and other search criteria. Each user in your organization is the owner of their OneDrive for Business site, which is located in the site collection named https://domain-my.sharepoint.com. By default, an Office 365 global administrator or compliance manager can't use the eDiscovery Center in SharePoint Online to search any OneDrive for Business sites. To search a OneDrive for Business site, administrators or compliance managers must be a site collection administrator for that OneDrive for Business site.</span></span> 
  
<span data-ttu-id="84929-111">本文将指导您完成使管理员或合规性组织中每个 onedrive for Business 网站的网站集管理员经理的步骤。</span><span class="sxs-lookup"><span data-stu-id="84929-111">This article guides you through the steps to make an administrator or compliance manager a site collection administrator for every OneDrive for Business site in your organization.</span></span> 
  
<span data-ttu-id="84929-112">请参阅有关本文中，包括修改步骤 3，以删除用户作为网站集管理员 OneDrive for Business 站点中的脚本中使用脚本提示的[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="84929-112">See the [More information](#more-information) section for tips about using the script in this article, including revising the script in Step 3 to remove a user as a site collection administrator from OneDrive for Business sites.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="84929-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="84929-113">Before you begin</span></span>

- <span data-ttu-id="84929-p103">安装 SharePoint Online 命令行管理程序。有关信息，请参阅 [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318)（设置 SharePoint Online 命令行管理程序 Windows PowerShell 环境）。</span><span class="sxs-lookup"><span data-stu-id="84929-p103">Install the SharePoint Online Management Shell. For information, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span></span>
    
- <span data-ttu-id="84929-116">步骤 3 中每的次您想要将用户作为网站集管理员分配给任何 OneDrive for Business 组织中的网站运行脚本。</span><span class="sxs-lookup"><span data-stu-id="84929-116">Run the script in Step 3 each time you want to assign a user as a site collection administrator to any OneDrive for Business sites in your organization.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="84929-p104">管理员或合规性属于网站集管理员 onedrive for Business 站点可以打开用户的 OneDrive for Business 文档库并执行与所有者相同的任务管理器。是非常重要的控件并已分配有电子数据展示权限到 OneDrive 中您的组织的业务网站的监视器。</span><span class="sxs-lookup"><span data-stu-id="84929-p104">An administrator or compliance manager who is a site collection administrator for OneDrive for Business sites can open users' OneDrive for Business document libraries and perform the same tasks as the owner. It's important to control and monitor who has been assigned eDiscovery permissions to OneDrive for Business sites in your organization.</span></span> 
  
- <span data-ttu-id="84929-p105">本文中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本的传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。</span><span class="sxs-lookup"><span data-stu-id="84929-p105">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a><span data-ttu-id="84929-124">步骤 1： 收集所有 OneDrive for Business 站点的列表</span><span class="sxs-lookup"><span data-stu-id="84929-124">Step 1: Collect a list of all OneDrive for Business sites</span></span>

<span data-ttu-id="84929-p106">第一步是创建您的组织中所有 OneDrive for Business 站点的列表。有关说明，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此脚本将创建一个包含所有 OneDrive 网站的列表的文本文件。步骤 3 中运行的脚本将指定的用户作为网站集管理员分配给每个 OneDrive for Business 站点，在此步骤中创建的文本文件中列出。下面的文本提供如何设置的此文件中的网站列表格式的示例。如有必要，可以将网站删除此文件。</span><span class="sxs-lookup"><span data-stu-id="84929-p106">The first step is to create a list of all OneDrive for Business sites in your organization. For instructions, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. The script that you run in Step 3 assigns a specified user as a site collection administrator to each OneDrive for Business site listed in the text file that's created in this step. The following text provides an example of how the list of sites in this file should be formatted. You can remove sites from this file if necessary.</span></span>

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a><span data-ttu-id="84929-131">步骤 2： 连接到您的组织的 SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="84929-131">Step 2: Connect SharePoint Online Management Shell to your organization</span></span>

1. <span data-ttu-id="84929-132">在本地计算机上打开 SharePoint Online 命令行管理程序，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="84929-132">On your local computer, open the SharePoint Online Management Shell, and run the following command:</span></span>

    ```
    $credentials = Get-Credential
    ```

2. <span data-ttu-id="84929-133">在"Windows PowerShell 凭据请求"对话框中，键入您的 Office 365 全局管理员帐户的用户名和密码，然后单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="84929-133">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global administrator account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="84929-134">运行以下命令，将命令行管理程序连接到您的 SharePoint Online 组织：</span><span class="sxs-lookup"><span data-stu-id="84929-134">Run the following command to connect the Shell to your SharePoint Online organization:</span></span>
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. <span data-ttu-id="84929-135">要验证您是否已连接至您的 SharePoint Online 组织，请运行以下命令获取组织中所有站点的列表：</span><span class="sxs-lookup"><span data-stu-id="84929-135">To verify that you are connected to your SharePoint Online organization, run the following command to get a list of all the sites in your organization:</span></span>
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a><span data-ttu-id="84929-136">步骤 3：分配一个用户作为 OneDrive for Business 站点的站点集合管理员</span><span class="sxs-lookup"><span data-stu-id="84929-136">Step 3: Assign a user as a site collection administrator to OneDrive for Business sites</span></span>

<span data-ttu-id="84929-p107">下一步是运行脚本为每个 onedrive for Business 组织中的网站的网站集管理员分配指定的用户的。此脚本使用您在步骤 1 中创建的业务网站 OneDrive 的列表。如前面所述，您必须要为用户分配为网站集管理员 OneDrive for Business 站点每次运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="84929-p107">The next step is to run a script that assigns a specified user as a site collection administrator in every OneDrive for Business site in your organization. This script uses the list of OneDrive for Business sites that you created in Step 1. As previously stated, you have to run this script each time that you want to assign a user as a site collection administrator to OneDrive for Business sites.</span></span>
  
1. <span data-ttu-id="84929-p108">将以下文本保存到文本文件中。例如，您可以将其保存至名为 OD4BAssignSCA.txt 的文件。</span><span class="sxs-lookup"><span data-stu-id="84929-p108">Save the following text to a text file. For example, you could save it to a file named OD4BAssignSCA.txt.</span></span>

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. <span data-ttu-id="84929-p109">编辑以下变量中的脚本文件，开始并使用特定于您的组织的信息。以下示例假定您的组织的域名称是 contoso.onmicrosoft.com。请务必包围与双引号变量的值 ("")。</span><span class="sxs-lookup"><span data-stu-id="84929-p109">Edit the following variables in the beginning of the script file, and use information that's specific to your organization. The following examples assume that the domain name of your organization is contoso.onmicrosoft.com. Be sure to surround the values for the variables with double-quotation marks (" ").</span></span>
    
    - <span data-ttu-id="84929-145">**$AdminURI** -这指定的 URI 为 SharePoint Online 管理服务，例如， `"https://contoso-admin.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="84929-145">**$AdminURI** - This specifies the URI for your SharePoint Online admin service, for example,  `"https://contoso-admin.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="84929-146">**$AdminAccount** -此选项指定全局管理员帐户 Office 365 组织，例如， `"admin@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="84929-146">**$AdminAccount** - This specifies a global administrator account in your Office 365 organization, for example,  `"admin@contoso.onmicrosoft.com"`.</span></span>
    
    - <span data-ttu-id="84929-147">**$eDiscoveryUser** -此选项指定管理员的用户帐户或合规性管理器将为每个 onedrive for Business 组织中的网站的网站集管理员，如分配`"annb@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="84929-147">**$eDiscoveryUser** - This specifies the user account of an administrator or compliance manager who will be assigned as a site collection administrator for every OneDrive for Business site in your organization, for example,  `"annb@contoso.onmicrosoft.com"`.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="84929-148">更改由 **$eDiscoveryUser**变量指定的用户帐户并重新运行脚本以将不同的用户作为网站集管理员分配给 OneDrive for Business 由 **$MySiteListFile**变量指定的网站。</span><span class="sxs-lookup"><span data-stu-id="84929-148">Change the user account specified by the **$eDiscoveryUser** variable and re-run the script to assign a different user as a site collection administrator to the OneDrive for Business sites that are specified by the **$MySiteListFile** variable.</span></span> 
  
    - <span data-ttu-id="84929-p110">**$MySitePrefix**此选项指定您所在组织的 MySite 域名的 URL。这是例如，包含所有 OneDrive for Business 网站在组织中的域`"https://contoso-my.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="84929-p110">**$MySitePrefix**This specifies the URL for your organization's MySite domain. This is the domain that contains all the OneDrive for Business sites in your organization, for example,  `"https://contoso-my.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="84929-p111">**$MySiteListFile**此选项指定您在步骤 1 中创建的文本文件的完整路径。此文件包含为在组织中的业务网站 OneDrive 的列表如`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。请务必包围单引号与此变量的值 ()。请注意，您应指定您在步骤 1 中保存到文本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="84929-p111">**$MySiteListFile**This specifies the full path of the text file that you created in Step 1. This file contains a list of OneDrive for Business sites in your organization, for example,  `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Be sure to surround the value for this variable with single-quotation marks (' '). Note that you should specify the location that you saved the text file to in Step 1.</span></span>
    
3. <span data-ttu-id="84929-p112">通过将文本文件的名称后缀改为 .ps1 将其另存为 PowerShell 脚本文件。例如，将文件 OD4BAssignSCA.txt 另存为 OD4BAssignSCA.ps1。</span><span class="sxs-lookup"><span data-stu-id="84929-p112">Save the text file as a PowerShell script file by changing the file name suffix to .ps1. For example, save the file OD4BAssignSCA.txt as OD4BAssignSCA.ps1.</span></span>
    
4. <span data-ttu-id="84929-157">在 SharePoint Online 命令行管理程序中，转到上一步中创建的 PowerShell 脚本所在的文件夹，然后运行该脚本，例如：</span><span class="sxs-lookup"><span data-stu-id="84929-157">In SharePoint Online Management Shell, go to the folder that contains the PowerShell script that you created in the previous step, and then run the script, for example:</span></span>
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    <span data-ttu-id="84929-p113">系统将提示您输入的脚本中指定的管理员帐户的密码。如果该脚本运行成功，邮件`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"`每个 onedrive for Business 站点 **$MySiteListFile**指定输入文件中列出的显示。</span><span class="sxs-lookup"><span data-stu-id="84929-p113">You will be prompted to enter the password for the administrator account that you specified in the script. If the script runs successfully, the message `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` is displayed for each OneDrive for Business site that's listed in the input file specified by **$MySiteListFile**.</span></span>

## <a name="more-information"></a><span data-ttu-id="84929-160">更多信息</span><span class="sxs-lookup"><span data-stu-id="84929-160">More information</span></span>

- <span data-ttu-id="84929-p114">您在步骤 3 中运行的脚本使用**集 SPOUser** cmdlet 将指定的用户作为网站集管理员分配给每个 OneDrive for Business 内 **$MySiteListFile**变量指定的文件中列出。如果您拥有数千名用户的大型组织，请考虑以下内容以使其更易于管理电子数据展示权限的分配。</span><span class="sxs-lookup"><span data-stu-id="84929-p114">The script that you ran in Step 3 uses the **Set-SPOUser** cmdlet to assign the specified user as a site collection administrator to every OneDrive for Business that's listed in the file specified by the **$MySiteListFile** variable. If you have a very large organization with thousands of users, consider doing the following to make it easier to manage assigning eDiscovery permissions.</span></span> 
    
  - <span data-ttu-id="84929-163">编辑包含业务网站 OneDrive 的列表，使其包含的网站的用户是活动的法律案件所涉及的步骤 1 中创建的文件。</span><span class="sxs-lookup"><span data-stu-id="84929-163">Edit the file that you created in Step 1 that contains the list of OneDrive for Business sites so that it includes only the sites for users are that are involved in active legal cases.</span></span>
    
  - <span data-ttu-id="84929-p115">将权限分配给不超过 2500 OneDrive for Business 网站每日。例如，假设您的组织中具有 10,000 OneDrive for Business 站点。您可以在步骤 1，收集所有网站中创建列表。然后您无法使用该文件创建每个包含 2500 用户的四个文件。第一天，将在步骤 3，以将权限分配给首先 2500 OneDrive for Business 站点运行脚本。在第二个一天，将运行该脚本为下一步 2500 OneDrive for Business 站点，依此类推。</span><span class="sxs-lookup"><span data-stu-id="84929-p115">Assign permissions to no more than 2,500 OneDrive for Business sites per day. For example, let's say you have 10,000 OneDrive for Business sites in your organization. You could create the list in Step 1 to collect all the sites. Then you could use that file to create four files that each contain 2,500 users. On the first day, you would run the script in Step 3 to assign permissions to the first 2,500 OneDrive for Business sites. On the second day, you would run the script for the next 2,500 OneDrive for Business sites, and so on.</span></span>
    
- <span data-ttu-id="84929-p116">保留的 OneDrive for Business 站点电子数据展示权限和被指定为网站集管理员的用户分配的记录。例如，分配权限后，您可以保存包含的 OneDrive for Business 站点的列表的文本文件，并将行添加到其标识指定为网站集管理员的用户。</span><span class="sxs-lookup"><span data-stu-id="84929-p116">Keep a record of the OneDrive for Business sites that were assigned eDiscovery permissions and the user who is assigned as the site collection administrator. For example, after you assign permissions, you can save the text file that contains the list of OneDrive for Business sites and add a line to it that identifies the user who is assigned as the site collection administrator.</span></span>
    
- <span data-ttu-id="84929-p117">为 OneDrive for Business 站点，用户可以查看网站集管理员的列表。用户是其自己的 onedrive for Business 网站的网站集管理员，因为它们可以移除网站集管理员。请考虑以下操作来缓解删除是电子数据展示权限分配给 OneDrive for Business 站点的用户的用户的机会。</span><span class="sxs-lookup"><span data-stu-id="84929-p117">Users can view the list of site collection administators for their OneDrive for Business site. Because users are site collection administrator for their own OneDrive for Business site, they can remove site collection administrators. Consider doing the following to mitigate the chance of users removing the user who is assigned eDiscovery permissions to OneDrive for Business sites.</span></span>
    
  - <span data-ttu-id="84929-175">与用户沟通，为了电子数据展示和合规性，合规部主管已分配为网站集管理员到 OneDrive 中您的组织的业务网站。</span><span class="sxs-lookup"><span data-stu-id="84929-175">Communicate to users that for eDiscovery and compliance purposes, a compliance officer has been assigned as a site collection administrator to OneDrive for Business sites in your organization.</span></span>
    
  - <span data-ttu-id="84929-176">重新在步骤 3 中，运行该脚本如有必要，以重新将用户指定为网站集的管理员 onedrive for Business 站点。</span><span class="sxs-lookup"><span data-stu-id="84929-176">Re-run the script in Step 3, if necessary, to re-assign a user as the site collection administrator for OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="84929-p118">您还可以使用您在步骤 3 中运行的脚本以删除用户作为网站集管理员 OneDrive for Business 站点。若要删除的用户作为网站集管理员，您必须从更改 （附近脚本末尾） 的以下命令：</span><span class="sxs-lookup"><span data-stu-id="84929-p118">You can also use the script that you ran in Step 3 to remove a user as the site collection administrator from OneDrive for Business sites. To remove a user as a site collection administrator, you have to change the following command (near the end of the script) from:</span></span> 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    <span data-ttu-id="84929-179">更改为：</span><span class="sxs-lookup"><span data-stu-id="84929-179">to:</span></span>
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    <span data-ttu-id="84929-180">您还可以将脚本中的以下行从：</span><span class="sxs-lookup"><span data-stu-id="84929-180">You can also change the following line in the script from:</span></span>

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    <span data-ttu-id="84929-181">更改为：</span><span class="sxs-lookup"><span data-stu-id="84929-181">to:</span></span>
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    <span data-ttu-id="84929-182">进行这些更改后，将脚本保存与一个不同的名称，例如 OD4BRemoveSCA.ps1，并将其从一组 OneDrive for Business 站点删除作为网站集管理员的用户。</span><span class="sxs-lookup"><span data-stu-id="84929-182">After you make these changes, save the script with a different name, such as OD4BRemoveSCA.ps1, and then use it to remove a user as a site collection administrator from a group of OneDrive for Business sites.</span></span>
