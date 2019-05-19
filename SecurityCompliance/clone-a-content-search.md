---
title: 克隆内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: 使用本文中的 Windows PowerShell 脚本, 可以在 Office 365 或 Microsoft 365 中的合规性中心快速克隆现有的内容搜索。 当您克隆搜索时, 将创建一个新的搜索 (具有新的名称), 其中包含与原始搜索相同的属性。 然后, 您可以编辑新的搜索 (通过更改关键字查询或日期范围), 然后运行它。
ms.openlocfilehash: 2622b77045d3b4a92ad2e8a1852e1ddbaaca3368
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155314"
---
# <a name="clone-a-content-search"></a>克隆内容搜索

在 Office 365 或 Microsoft 365 中的合规性中心内创建内容搜索, 以搜索大量邮箱或 SharePoint 和 OneDrive for business 网站可能需要一段时间。 如果错误键入 URL, 则指定要搜索的网站也很容易出错。 若要避免这些问题, 您可以使用本文中的 Windows PowerShell 脚本快速克隆现有的内容搜索。 当您克隆搜索时, 会创建一个新的搜索 (名称不同), 其中包含与原始搜索相同的属性 (如内容位置和搜索查询)。 然后, 您可以编辑新的搜索 (通过更改关键字查询或日期范围) 并运行它。
  
为什么要克隆内容搜索？
  
- 比较不同关键字搜索查询的结果在相同的内容位置运行。
    
- 在创建新的搜索时, 不必重新输入大量的内容位置。
    
- 减小搜索结果的大小;例如, 如果您的搜索返回过多要导出的结果, 则可以克隆搜索, 然后根据日期范围添加搜索条件, 以减少搜索结果的数量。
  
## <a name="before-you-begin"></a>开始之前

- 您必须是 Security & 合规中心中的电子数据展示管理器角色组的成员, 才能运行本主题中所述的脚本。
    
- 该脚本包括最少的错误处理。 脚本的主要用途是快速克隆内容搜索。
    
- 该脚本会创建新的内容搜索, 但不会启动它。
    
- 此脚本将考虑您要克隆的内容搜索是否与电子数据展示事例相关联。 如果搜索与某一事例相关联, 则新的搜索也将与同一事例相关联。 如果现有搜索不与事例相关联, 则新搜索将在合规性中心的**内容搜索**页中列出。 
    
- 在任何 Microsoft standard 支持计划或服务下, 本主题中提供的示例脚本不受支持。 示例脚本按原样提供, 而不提供任何种类的担保。 Microsoft 也不提供任何默示担保，包括但不仅限于对适销性或针对特定目的的适用性的默示担保。 因使用或性能示例脚本和文档而导致的全部风险都将保留给您。 对于因使用或无法使用示例脚本或文档产生的任何损害（包括但不仅限于商业利润损失、业务中断、业务信息丢失或其他金钱损失），Microsoft、脚本作者以及参与脚本创建、生成或交付的任何人均不承担任何责任，即使 Microsoft 已被告知此类损害的可能性也是如此。
  
## <a name="step-1-run-the-script-to-clone-a-search"></a>步骤 1: 运行脚本以克隆搜索

此步骤中的脚本将通过克隆现有内容搜索来创建新的内容搜索。 运行此脚本时, 系统将提示您输入以下信息:
  
- **你的用户凭据**-脚本将使用你的凭据连接到使用 Windows PowerShell 的 Office 365 组织的安全 _AMP_ 合规性中心。 如前所述, 您必须是 Security & compCompliance Center 中的 "电子数据展示管理器" 角色组的成员才能运行该脚本。 
    
- **现有搜索的名称**-这是要克隆的内容搜索。 
    
- **将创建的新搜索的名称**-如果将此值保留为空, 则脚本将为新搜索创建一个名称, 该名称基于您要克隆的搜索的名称。 
    
若要克隆搜索, 请执行以下操作:
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `CloneSearch.ps1`。
    
  ```
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
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
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
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
    
3. 运行脚本;例如:
    
    ```
    .\CloneSearch.ps1
    ```

4. 当系统提示你输入凭据时, 请输入你的电子邮件地址和密码, 然后单击 **"确定"**。
    
5. 当脚本提示时, 请输入以下信息。 键入每条信息, 然后按**enter**。
    
    - 现有搜索的名称。
    
    - 新搜索的名称。
    
    该脚本会创建新的内容搜索, 但不会启动它。 这使您有机会在下一步中编辑和运行搜索。 您可以通过运行**new-compliancesearch** cmdlet 或转到合规中心中的**内容搜索**或**电子数据展示**页来查看新搜索的属性, 具体取决于新搜索是否与案例相关联。 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a>步骤 2: 在合规中心中编辑和运行克隆的搜索

在运行脚本以克隆现有内容搜索之后, 下一步是转到 "合规中心" 以编辑并运行新的搜索。 如前所述, 可以通过更改关键字搜索查询和添加或删除搜索条件来编辑搜索。 有关详细信息，请参阅：
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)
    
- [电子数据展示事例](ediscovery-cases.md)
