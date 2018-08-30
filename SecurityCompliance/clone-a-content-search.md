---
title: 克隆的内容搜索结果中的 Office 365 安全性&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 脚本能够快速克隆现有内容安全中搜索&amp;Compliane 中心搜索。当您克隆搜索时，新的搜索 （具有新的名称） 创建包含与原始搜索相同的属性。然后您可以编辑 （通过更改关键字查询或日期范围），新搜索，然后运行它。
ms.openlocfilehash: a4f801e3de281e8caf8aeb7d1c2bd48f0facb77c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525276"
---
# <a name="clone-a-content-search-in-the-office-365-security-amp-compliance-center"></a>克隆的内容搜索结果中的 Office 365 安全性&amp;合规性中心

在 Office 365 安全性中创建内容搜索&amp;搜索大量邮箱或 SharePoint 的合规性中心和 OneDrive for Business 网站可能需要一段时间。指定要搜索的网站也可能是容易出错如果键入 URL。若要避免这些问题，您可以使用 Windows PowerShell 脚本本文中能够快速克隆现有内容搜索。当您克隆搜索时，新的搜索 （具有不同的名称） 创建包含与原始搜索相同属性 （如内容的位置和搜索查询）。然后您可以编辑新搜索 （通过更改关键字查询或日期范围），并运行它。
  
为什么克隆内容搜索？
  
- 若要比较结果的不同关键字搜索查询运行在相同的内容位置。
    
- 保存您无需重新输入大量内容位置，当您创建一个新的搜索。
    
- 以减小大小的搜索结果;例如，如果您有返回要导出结果太多的搜索，您可以克隆搜索，然后添加基于日期范围以减少的搜索结果的搜索条件。
  
## <a name="before-you-begin"></a>准备工作

- 您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行脚本本主题中所述。
    
- 该脚本包括最少的错误处理。脚本的主要用途是快速克隆内容的搜索。
    
- 脚本创建一个新的内容搜索，但是无法启动它。
    
- 此脚本将考虑是否正在克隆内容搜索与电子数据展示事例相关联。如果搜索是与案例相关联，新的搜索还将与相同的大小写。如果现有搜索不与案例相关联，将安全中**内容的搜索**页面上列出的新搜索&amp;合规性中心。 
    
- 本主题中提供的示例脚本不支持任何 Microsoft 标准支持程序或服务。示例脚本原样提供，没有任何形式的担保。Microsoft 进一步否认所有默示的担保，包括但不限于，任何暗示对适销性或针对特定用途的适用性的担保。因使用或性能的示例脚本和文档的全部风险您自己承担。在任何事件应 Microsoft、 作者，或创建、 生产或脚本传递 else 所涉及的任何人都都不对因任何损害向 （包括但不限于损失业务损失、 业务中断丢失业务信息或其他 pecuniary 丢失） 因使用或不能使用的示例脚本或文档，即使 Microsoft 已被告知此类损害的可能性。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步骤 1： 运行脚本以克隆搜索

此步骤中的脚本将创建一个新的内容搜索通过克隆现有。运行此脚本时，系统将提示您输入以下信息：
  
- **您的用户凭据**-脚本将使用您的凭据来连接到安全性&amp;使用 Windows PowerShell 为 Office 365 组织的合规性中心。如上文所述，您必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心以运行脚本。 
    
- **现有搜索的名称**-这是您想要克隆的内容搜索。 
    
- **将创建的新搜索条件的名称**-如果您保留此值为空，该脚本将创建基于您克隆搜索的名称的新搜索的名称。 
    
若要克隆搜索：
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `CloneSearch.ps1`。
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 Security &amp; Compliance Center
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. 打开 Windows PowerShell 并转到保存该脚本的文件夹。
    
3. 运行脚本。例如：
    
    ```
    .\CloneSearch.ps1
    ```

4. 当提示输入凭据，输入您的电子邮件地址和密码，，，然后单击**确定**。
    
5. 输入以下信息脚本出现提示时。键入每条信息，然后按**Enter**。
    
    - 现有搜索的名称。
    
    - 新搜索条件的名称。
    
    脚本创建新的内容搜索，但是无法启动它。这样，您可以编辑并在下一步中运行搜索的机会。您可以查看新的搜索的属性，通过运行**Get ComplianceSearch** cmdlet 或转到安全的**内容搜索**或**电子数据展示**页&amp;合规性中心，具体取决于是否是新的搜索与案例相关联。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-security-amp-compliance-center"></a>步骤 2： 编辑和安全中运行的克隆的搜索&amp;合规性中心

您已运行脚本来克隆现有内容搜索后下, 一步是转到安全&amp;合规性中心以编辑和运行新的搜索。如上文所述，您可以编辑搜索通过更改查询关键字搜索并添加或删除搜索条件。有关详细信息，请参阅：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
    
- [Office 365 安全性的电子数据展示事例&amp;合规性中心](ediscovery-cases.md)
