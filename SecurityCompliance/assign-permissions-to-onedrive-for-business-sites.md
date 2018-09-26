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
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a>为 OneDrive for Business 站点分配电子数据展示权限

可以使用 SharePoint Online 中的电子数据展示中心搜索特定关键字、 敏感信息和其他搜索条件组织中的所有 OneDrive for Business 站点。您的组织中的每个用户是 OneDrive for Business 站点，位于名为网站集的所有者https://domain-my.sharepoint.com。默认情况下，Office 365 全局管理员或合规性管理器无法使用 SharePoint Online 中的电子数据展示中心搜索任何 OneDrive for Business 站点。若要搜索的 OneDrive for Business 站点、 管理员或合规性管理员必须是网站集管理员的 onedrive for Business 站点。 
  
本文将指导您完成使管理员或合规性组织中每个 onedrive for Business 网站的网站集管理员经理的步骤。 
  
请参阅有关本文中，包括修改步骤 3，以删除用户作为网站集管理员 OneDrive for Business 站点中的脚本中使用脚本提示的[详细信息](#more-information)部分。 
  
## <a name="before-you-begin"></a>准备工作

- 安装 SharePoint Online 命令行管理程序。有关信息，请参阅 [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318)（设置 SharePoint Online 命令行管理程序 Windows PowerShell 环境）。
    
- 步骤 3 中每的次您想要将用户作为网站集管理员分配给任何 OneDrive for Business 组织中的网站运行脚本。 
    
    > [!IMPORTANT]
    > 管理员或合规性属于网站集管理员 onedrive for Business 站点可以打开用户的 OneDrive for Business 文档库并执行与所有者相同的任务管理器。是非常重要的控件并已分配有电子数据展示权限到 OneDrive 中您的组织的业务网站的监视器。 
  
- 本文中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本的传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a>步骤 1： 收集所有 OneDrive for Business 站点的列表

第一步是创建您的组织中所有 OneDrive for Business 站点的列表。有关说明，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此脚本将创建一个包含所有 OneDrive 网站的列表的文本文件。步骤 3 中运行的脚本将指定的用户作为网站集管理员分配给每个 OneDrive for Business 站点，在此步骤中创建的文本文件中列出。下面的文本提供如何设置的此文件中的网站列表格式的示例。如有必要，可以将网站删除此文件。

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a>步骤 2： 连接到您的组织的 SharePoint Online Management Shell

1. 在本地计算机上打开 SharePoint Online 命令行管理程序，并运行以下命令：

    ```
    $credentials = Get-Credential
    ```

2. 在"Windows PowerShell 凭据请求"对话框中，键入您的 Office 365 全局管理员帐户的用户名和密码，然后单击"确定"。
    
3. 运行以下命令，将命令行管理程序连接到您的 SharePoint Online 组织：
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. 要验证您是否已连接至您的 SharePoint Online 组织，请运行以下命令获取组织中所有站点的列表：
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a>步骤 3：分配一个用户作为 OneDrive for Business 站点的站点集合管理员

下一步是运行脚本为每个 onedrive for Business 组织中的网站的网站集管理员分配指定的用户的。此脚本使用您在步骤 1 中创建的业务网站 OneDrive 的列表。如前面所述，您必须要为用户分配为网站集管理员 OneDrive for Business 站点每次运行此脚本。
  
1. 将以下文本保存到文本文件中。例如，您可以将其保存至名为 OD4BAssignSCA.txt 的文件。

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

2. 编辑以下变量中的脚本文件，开始并使用特定于您的组织的信息。以下示例假定您的组织的域名称是 contoso.onmicrosoft.com。请务必包围与双引号变量的值 ("")。
    
    - **$AdminURI** -这指定的 URI 为 SharePoint Online 管理服务，例如， `"https://contoso-admin.sharepoint.com"`。
    
    - **$AdminAccount** -此选项指定全局管理员帐户 Office 365 组织，例如， `"admin@contoso.onmicrosoft.com"`。
    
    - **$eDiscoveryUser** -此选项指定管理员的用户帐户或合规性管理器将为每个 onedrive for Business 组织中的网站的网站集管理员，如分配`"annb@contoso.onmicrosoft.com"`。
    
      > [!NOTE]
      > 更改由 **$eDiscoveryUser**变量指定的用户帐户并重新运行脚本以将不同的用户作为网站集管理员分配给 OneDrive for Business 由 **$MySiteListFile**变量指定的网站。 
  
    - **$MySitePrefix**此选项指定您所在组织的 MySite 域名的 URL。这是例如，包含所有 OneDrive for Business 网站在组织中的域`"https://contoso-my.sharepoint.com"`。
    
    - **$MySiteListFile**此选项指定您在步骤 1 中创建的文本文件的完整路径。此文件包含为在组织中的业务网站 OneDrive 的列表如`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。请务必包围单引号与此变量的值 ()。请注意，您应指定您在步骤 1 中保存到文本文件的位置。
    
3. 通过将文本文件的名称后缀改为 .ps1 将其另存为 PowerShell 脚本文件。例如，将文件 OD4BAssignSCA.txt 另存为 OD4BAssignSCA.ps1。
    
4. 在 SharePoint Online 命令行管理程序中，转到上一步中创建的 PowerShell 脚本所在的文件夹，然后运行该脚本，例如：
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    系统将提示您输入的脚本中指定的管理员帐户的密码。如果该脚本运行成功，邮件`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"`每个 onedrive for Business 站点 **$MySiteListFile**指定输入文件中列出的显示。

## <a name="more-information"></a>更多信息

- 您在步骤 3 中运行的脚本使用**集 SPOUser** cmdlet 将指定的用户作为网站集管理员分配给每个 OneDrive for Business 内 **$MySiteListFile**变量指定的文件中列出。如果您拥有数千名用户的大型组织，请考虑以下内容以使其更易于管理电子数据展示权限的分配。 
    
  - 编辑包含业务网站 OneDrive 的列表，使其包含的网站的用户是活动的法律案件所涉及的步骤 1 中创建的文件。
    
  - 将权限分配给不超过 2500 OneDrive for Business 网站每日。例如，假设您的组织中具有 10,000 OneDrive for Business 站点。您可以在步骤 1，收集所有网站中创建列表。然后您无法使用该文件创建每个包含 2500 用户的四个文件。第一天，将在步骤 3，以将权限分配给首先 2500 OneDrive for Business 站点运行脚本。在第二个一天，将运行该脚本为下一步 2500 OneDrive for Business 站点，依此类推。
    
- 保留的 OneDrive for Business 站点电子数据展示权限和被指定为网站集管理员的用户分配的记录。例如，分配权限后，您可以保存包含的 OneDrive for Business 站点的列表的文本文件，并将行添加到其标识指定为网站集管理员的用户。
    
- 为 OneDrive for Business 站点，用户可以查看网站集管理员的列表。用户是其自己的 onedrive for Business 网站的网站集管理员，因为它们可以移除网站集管理员。请考虑以下操作来缓解删除是电子数据展示权限分配给 OneDrive for Business 站点的用户的用户的机会。
    
  - 与用户沟通，为了电子数据展示和合规性，合规部主管已分配为网站集管理员到 OneDrive 中您的组织的业务网站。
    
  - 重新在步骤 3 中，运行该脚本如有必要，以重新将用户指定为网站集的管理员 onedrive for Business 站点。
    
- 您还可以使用您在步骤 3 中运行的脚本以删除用户作为网站集管理员 OneDrive for Business 站点。若要删除的用户作为网站集管理员，您必须从更改 （附近脚本末尾） 的以下命令： 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    更改为：
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    您还可以将脚本中的以下行从：

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    更改为：
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    进行这些更改后，将脚本保存与一个不同的名称，例如 OD4BRemoveSCA.ps1，并将其从一组 OneDrive for Business 站点删除作为网站集管理员的用户。
