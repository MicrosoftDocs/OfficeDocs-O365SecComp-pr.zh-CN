---
title: 在 Office 365 中搜索内部部署用户的基于云的邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Office 365 安全性中的内容搜索工具&amp;合规性中心搜索和导出 Exchange 混合部署中的内部部署用户 MicrosoftTeams 聊天数据 （称为 1xN 聊天）。
ms.openlocfilehash: a504dfcf4c82bec036137b90312c01a0b2326ccc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525213"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>在 Office 365 中搜索内部部署用户的基于云的邮箱

如果您的组织具有 Exchange 混合部署，并且已启用的 Microsoft 团队，用户可以使用团队聊天应用程序的即时消息。对于基于云的用户，（也称为 1xN 聊天） 团队聊天数据保存到其主的基于云的邮箱。内部部署用户使用的工作组聊天应用程序，其主邮箱时位于内部部署。若要解决此限制，Microsoft 已发布在其中创建 （称为内部部署用户的基于云的邮箱） 的基于云的存储区存储团队的内部部署用户的聊天数据的新功能。这使您可以在 Office 365 安全性使用内容搜索工具&amp;合规性中心搜索和导出团队需要内部部署用户的聊天数据。 
  
下面是要求和限制的设置，并可设置和搜索内部部署用户的基于云的邮箱：
  
- 必须与 Azure Active Directory 的 Office 365 中的目录服务同步您的本地目录服务 （如 Active Directory) 中的用户帐户。也就是说，邮件用户帐户在 Office 365 中创建并且与主邮箱位于内部部署组织中的用户相关联。
    
- 内部部署用户的基于云的邮箱使用的唯一存储团队聊天数据。内部部署用户不能登录到基于云的邮箱，或者访问以任何方式。它不能用于发送或接收的电子邮件。 
    
- 您必须提交到 Microsoft 支持的请求，以让您的组织搜索团队聊天数据在内部部署用户的基于云的邮箱中。请参阅[归档与 Microsoft 支持的请求，若要启用此功能的安全&amp;合规性中心](#filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center)本文中。 
    
 **注意：** 团队通道对话始终存储在与团队相关联的基于云的邮箱。这意味着您可以使用内容搜索来搜索通道对话缺少具有文件支持请求。有关搜索团队频道对话，请参阅[搜索 Microsoft 团队和 Office 365 组](content-search.md#searching-microsoft-teams-and-office-365-groups)。
  
## <a name="how-it-works"></a>如何工作

如果 Microsoft 团队启用用户具有内部部署邮箱且其用户帐户/标识包含已同步到云，Microsoft 将创建基于云的邮箱存储 1xN 团队聊天数据。团队聊天数据存储在基于云的邮箱后，会将其编制索引的搜索。使您能够使用内容搜索 （和电子数据展示事例相关联的搜索） 要搜索预览，并将内部部署用户的团队聊天数据导出。您还可以使用**\*ComplianceSearch** Office 365 安全性 cmdlet&amp;合规性中心 PowerShell，可以搜索团队的内部部署用户的聊天数据。 
  
下图显示了如何团队聊天内部部署用户的数据的工作流是可用于搜索、 预览和导出。
  
![内部部署中的用户的 Microsoft 团队的基于云的存储](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
除了这项新功能，您仍可用内容搜索来搜索、 预览和导出的基于云的 SharePoint 网站和 Exchange 邮箱中的内容与每个 Microsoft 团队和 1xN 团队中的 Exchange Online 邮箱的聊天数据相关联的团队基于云的用户。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature-in-the-security-amp-compliance-center"></a>存档与 Microsoft 支持的请求，若要启用此功能的安全&amp;合规性中心

您必须文件与 Microsoft 支持的请求，以让您的组织使用安全中的图形用户界面&amp;合规性中心搜索团队聊天数据在内部部署用户的基于云的邮箱。请注意，此功能都在 Office 365 安全性&amp;合规性中心 PowerShell。您无需提交支持请求以使用 PowerShell 搜索的内部部署用户的工作组聊天数据。 
  
提交到 Microsoft 支持的请求时，包括以下信息：
  
- Office 365 组织默认域名。
    
- 租户名称和 Office 365 组织的租户 ID。您可以找到这些 Azure Active Directory 门户中 (在**管理**下\>**属性**)。请参阅[查找您的 Office 365 租户 ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。
    
- 下面的标题或支持请求的用途的说明:"启用应用程序内容搜索内部部署用户"。这有助于将请求路由到 Office 365 电子数据展示工程团队将实现请求。 
    
工程设计更改后，Microsoft 支持将向您发送估计的部署日期。请注意，部署过程，通常采用 2 到 3 周后提交支持请求。 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>启用此功能后，会发生什么情况？

此功能 Office 365 组织中部署后，以下更改在内容搜索进行以及相关联的电子数据展示搜索中 case 安全中&amp;合规性中心：
  
- **本地用户添加 Office 应用程序内容**复选框将添加下内容搜索中的**位置**。 
    
    !["添加内部部署用户的 Office 应用程序内容"复选框添加到内容搜索 UI](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 用于选择要搜索的用户邮箱的内容位置选取器中显示内部部署用户。 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>搜索内部部署用户的基于云的邮箱中内容的团队聊天

在启用该功能后，可以使用在安全的内容搜索&amp;合规性中心搜索团队聊天数据在内部部署用户的基于云的邮箱。 
  
1. 安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **内容搜索**
    
2. 在**搜索**页上单击![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜索**。
    
    如前所述，**位置**下显示**添加 Office 应用程序内容的内部部署用户**复选框。请注意，它默认选中状态。
    
3. 创建关键字查询并根据需要向搜索查询添加条件。仅搜索团队聊天数据，您可以在**关键字**框中添加以下查询： 
    
    ```
    kind:im
    ``` 

4. 此时，您可以选择**位置**下的以下选项之一：
    
    - **所有位置**-选择此选项可搜索您的组织中的所有用户邮箱。选中此复选框后，还将搜索内部部署用户的所有基于云的邮箱。 
    
    - **特定位置**-选择此选项，然后单击**修改**\>选择用户、 组或团队，搜索特定邮箱。如前所述，位置选取器会让您搜索内部部署用户。 
    
5. 保存并运行搜索。可以与任何其他搜索结果一样预览任何搜索结果从内部部署用户的基于云的邮箱。此外，您可以您可以将 （包括任何团队聊天数据） 的搜索结果导出到 PST 文件。有关详细信息，请参阅： 
    
    - [创建新的搜索](content-search.md#create-a-new-search)
    
    - [预览搜索结果](content-search.md#preview-search-results)
    
    - [从 Office 365 安全性导出内容的搜索结果&amp;合规性中心](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>使用 PowerShell 搜索团队聊天数据在内部部署用户的基于云的邮箱

您可以在 Office 365 安全性使用**新建 ComplianceSearch**和**设置 ComplianceSearch** cmdlet&amp;合规性中心 PowerShell 搜索内部部署用户的基于云的邮箱。如前所述，您无需提交支持请求以使用 PowerShell 搜索的内部部署用户的工作组聊天数据。 
  
1. [连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
    
2. 运行以下 PowerShell 命令以创建新的内容搜索内部部署用户的基于云的邮箱。
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    *IncludeUserAppContent*参数用于指定用户或由*ExchangeLocation*参数指定用户的基于云的邮箱。*AllowNotFoundExchangeLocationsEnabled*允许的内部部署用户的基于云的邮箱。当您使用`$true`此参数，搜索值不尝试运行之前验证邮箱是否存在。这是必需的因为这些类型的邮箱不解析为正则邮箱搜索内部部署用户的基于云的邮箱。 
    
    下面的示例搜索聊天 （即即时消息） 包含关键字"redstone"的基于云的邮箱中的 Sara Davis，属于 Contoso 组织中的内部部署用户的团队。
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   创建新的搜索后，请务必使用**开始 ComplianceSearch** cmdlet 运行搜索。 
  
使用这些 cmdlet 的详细信息，请参阅：
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>已知问题

- 目前，您还可以仅搜索、 预览和导出内容的基于云的邮箱中的本地用户。发出的内部部署用户的基于云的邮箱保留与电子数据展示案例或将其分配给 Office 365 保留策略不支持。 
    
- 电子数据展示内容位置选取器包含显示在本地用户，并且会让您选择它们。但是，如上文所述保留不会应用到内部部署用户。
    
## <a name="frequently-asked-questions"></a>常见问题

 **内部部署用户的基于云的邮箱位于何处？**
  
创建和存储在 Office 365 组织相同的数据中心中的基于云的邮箱。 
  
 **是否有提交支持请求之外的任何其他要求？**
  
 如前所述，必须进行具有 prem 上邮箱的用户的身份同步到基于云的组织，以便为 Office 365 中每个内部部署用户帐户创建相应的邮件用户帐户。此外，您的组织必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、 E3 或 E5 订阅。 
  
 **是否存在丢失团队聊天数据，如果用户的内部部署邮箱迁移到云中的风险？**
  
不。内部部署用户的主邮箱迁移到云中时，该用户的工作组聊天数据将迁移到其新的基于云的主邮箱。
  
 **可以将应用电子数据展示保留或 Office 365 保留策略到内部部署用户？**
  
不能。
  
 **内容搜索查找旧团队聊天的内部部署用户的时间之前我的组织可以提交请求以启用此功能？**
  
Microsoft 启动上 2018 年 1 月 31，存储在本地用户的工作组聊天数据。因此，如果此日期后，在本地团队用户的标识具有 Active Directory 和 Azure Active Directory 之间同步，然后其团队聊天数据将存储在基于云的邮箱，将可搜索使用内容搜索。Microsoft 正在在内部部署用户的基于云的邮箱中存储从之前 2018 年 1 月 31，团队聊天数据。很快就会提供相关详细信息。
