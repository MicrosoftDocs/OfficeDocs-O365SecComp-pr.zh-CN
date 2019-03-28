---
title: 在 Office 365 中搜索本地用户的基于云的邮箱
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/4/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 使用 Office 365 安全&amp;合规中心中的内容搜索工具在 Exchange 混合部署中搜索和导出本地用户的 MicrosoftTeams 聊天数据 (称为 "1xN 聊天")。
ms.openlocfilehash: b277557285df6944217b493bf0c5a11759f9d76b
ms.sourcegitcommit: 54a2cbe5d13f448e0c28655bdf88deb9e5434cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30935227"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users-in-office-365"></a>在 Office 365 中搜索本地用户的基于云的邮箱

如果你的组织具有 Exchange 混合部署, 并且已启用 Microsoft 团队, 则用户可以使用团队聊天应用程序进行即时消息传递。 对于基于云的用户, 团队聊天数据 (也称为1xN 聊天) 保存到其主要的基于云的邮箱中。 当本地用户使用团队聊天应用程序时, 其主邮箱位于本地。 为了避免此限制, Microsoft 已发布了一个新功能, 其中创建了基于云的存储区域 (称为本地用户的基于云的邮箱), 以存储本地用户的团队聊天数据。 这使您可以使用 Office 365 安全&amp;合规中心中的内容搜索工具搜索和导出本地用户的团队聊天数据。 
  
以下是为本地用户设置和搜索基于云的邮箱的要求和限制:
  
- 您的本地目录服务 (如 Active directory) 中的用户帐户必须与 Azure Active directory (Office 365 中的目录服务) 同步。 这意味着将在 Office 365 中创建一个邮件用户帐户, 并将其主邮箱位于内部部署组织中的用户关联。
    
- 本地用户的基于云的邮箱仅用于存储团队聊天数据。 本地用户无法以任何方式登录到基于云的邮箱或访问。 它不能用于发送或接收电子邮件。 
    
- 您必须向 Microsoft 支持部门提交请求, 以使您的组织能够在基于云的邮箱中搜索团队对话数据, 以供本地用户使用。 请参阅将[请求与 Microsoft 支持一起存档, 以在本文中启用此功能](#filing-a-request-with-microsoft-support-to-enable-this-feature)。 
    
 **注意:** 团队频道对话始终存储在与团队相关联的基于云的邮箱中。 这意味着您可以使用内容搜索来搜索频道对话, 而无需将其作为支持请求的文件。 有关搜索团队频道对话的详细信息, 请参阅[搜索 Microsoft 团队和 Office 365 组](content-search.md#searching-microsoft-teams-and-office-365-groups)。
  
## <a name="how-it-works"></a>工作原理

如果启用了 microsoft 团队的用户具有本地邮箱, 并且其用户帐户/标识已同步到云, Microsoft 将创建一个基于云的邮箱来存储1xN 团队聊天数据。 在将团队聊天数据存储在基于云的邮箱中之后, 将为搜索编制索引。 这样, 您就可以使用内容搜索 (和与电子数据展示事例关联的搜索) 来搜索、预览和导出本地用户的团队聊天数据。 您还可以使用** \*** Office 365 安全&amp;合规中心 PowerShell 中的 new-compliancesearch cmdlet 来搜索本地用户的团队聊天数据。 
  
下图显示了团队如何聊天本地用户数据的工作流, 以供搜索、预览和导出。
  
![Microsoft 团队中的本地用户的基于云的存储](media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
除了这一新功能之外, 您仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft 团队关联的 exchange 邮箱中的 exchange 邮箱中搜索、预览和导出团队内容, 以及1xN 团队与 exchange Online 邮箱中的数据进行聊天。基于云的用户。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>将请求与 Microsoft 支持一起存档以启用此功能

您必须将请求与 Microsoft 支持文件一起使用, 以使组织能够在安全&amp;合规中心中使用图形用户界面在基于云的邮箱中搜索团队对话数据, 以供本地用户使用。 请注意, 此功能在 Office 365 安全&amp;合规中心 PowerShell 中可用。 您无需提交支持请求即可使用 PowerShell 搜索本地用户的团队聊天数据。 
  
向 Microsoft 支持部门提交请求时, 请包含以下信息:
  
- Office 365 组织的默认域名。
    
- Office 365 组织的租户名称和租户 ID。 您可以在 Azure Active Directory 门户中找到这些文件 (在 "**管理** \> **属性**" 下)。 请参阅[查找 Office 365 租户 ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。
    
- 支持请求的用途的以下标题或说明: "启用本地用户的应用程序内容搜索"。 这将有助于将请求路由到将实现请求的 Office 365 电子数据展示工程团队。 
    
在进行工程更改之后, Microsoft 支持将向您发送估计的部署日期。 请注意, 在提交支持请求后, 部署过程通常需要2-3 周。 
  
### <a name="what-happens-after-this-feature-is-enabled"></a>启用此功能后, 会发生什么？

在 Office 365 组织中部署此功能之后, 在内容搜索以及与安全&amp;合规性中心中与电子数据展示事例相关联的搜索中将进行以下更改:
  
- "为**本地用户添加 Office 应用内容**" 复选框将添加到内容搜索中的**位置**下。 
    
    !["为本地用户添加 Office 应用内容" 复选框已添加到内容搜索 UI](media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- 内部部署用户将显示在用于选择要搜索的用户邮箱的内容位置选取器中。 
    

  
## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>搜索团队在基于云的邮箱中为本地用户聊天内容

启用此功能后, 您可以使用安全&amp;合规中心中的内容搜索, 在基于云的邮箱中搜索团队对话数据, 以供本地用户使用。 
  
1. 在安全&amp;合规性中心中, 转**到&amp;搜索调查** \> **内容搜索**
    
2. 在 "**搜索**" 页上![, 单击](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) "添加图标" "**新建搜索**"。
    
    如前所述, "为**本地用户添加 Office 应用内容**" 复选框将显示在 "**位置**" 下。 请注意, 默认情况下它处于选中状态。
    
3. 创建关键字查询, 并在必要时向搜索查询添加条件。 若要仅搜索工作组聊天数据, 您可以在 "**关键字**" 框中添加以下查询: 
    
    ```
    kind:im
    ``` 

4. 此时, 您可以在 "**位置**" 下选择以下选项之一:
    
    - **所有位置**-选择此选项可搜索组织中所有用户的邮箱。 选中此复选框后, 还将搜索本地用户的所有基于云的邮箱。 
    
    - **特定位置**-选择此选项, 然后单击 "**修改** \> ", 选择 "用户"、"组" 或 "团队" 以搜索特定邮箱。 如前所述, 位置选取器可让你搜索内部部署用户。 
    
5. 保存并运行搜索。 从基于云的邮箱对本地用户的任何搜索结果都可以像在任何其他搜索结果中一样进行预览。 此外, 还可以将搜索结果 (包括任何团队聊天数据) 导出到 PST 文件。 有关详细信息，请参阅： 
    
    - [创建新的搜索](content-search.md#create-a-new-search)
    
    - [预览搜索结果](content-search.md#preview-search-results)
    
    - [从 Office 365 安全&amp;合规中心导出内容搜索结果](export-search-results.md)
    
## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>使用 PowerShell 搜索团队对话数据在基于云的邮箱中用于本地用户

您可以使用 Office 365 安全&amp;合规中心 PowerShell 中的**new-compliancesearch**和**new-compliancesearch** cmdlet 在基于云的邮箱中搜索本地用户。 如前所述, 您无需提交支持请求即可使用 PowerShell 搜索本地用户的团队聊天数据。 
  
1. [连接到 Office 365 安全&amp;合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
    
2. 运行以下 PowerShell 命令创建新的内容搜索内部部署用户的基于云的邮箱。
    
    ```
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```
   
    *IncludeUserAppContent*参数用于为用户或由*ExchangeLocation*参数指定的用户指定基于云的邮箱。 *AllowNotFoundExchangeLocationsEnabled*允许本地用户的基于云的邮箱。 当您使用此`$true`参数的值时, 搜索在运行前不会尝试验证邮箱是否存在。 为本地用户搜索基于云的邮箱时, 这是必需的, 因为这些类型的邮箱不会解析为常规邮箱。 
    
    下面的示例在基于云的 redstone Davis (Contoso 组织中的本地用户) 的邮箱中搜索包含关键字 "" 的团队聊天 (这是即时消息)。
  
    ```
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   在创建新的搜索后, 请务必使用**new-compliancesearch** cmdlet 运行搜索。 
  
有关使用这些 cmdlet 的详细信息, 请参阅:
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)
    
- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)
    

## <a name="known-issues"></a>已知问题

- 目前, 您只能在基于云的邮箱中搜索、预览和导出本地用户的内容。 不支持在与电子数据展示案例关联的保留中为本地用户放置基于云的邮箱, 或将其分配给 Office 365 保留策略。 
    
- 电子数据展示保留的内容位置选取器显示本地用户, 并允许您选择它们。 但是, 如前面所述, 保留将不会应用于内部部署用户。
    
## <a name="frequently-asked-questions"></a>常见问题

 **本地用户的基于云的邮箱位于何处？**
  
将创建基于云的邮箱并将其存储在与 Office 365 组织相同的数据中心中。 
  
 **除了提交支持请求之外, 是否还有其他任何要求？**
  
 如前所述, 具有本地邮箱的用户的标识必须同步到您的基于云的组织, 以便为 Office 365 中的每个本地用户帐户创建相应的邮件用户帐户。 此外, 您的组织必须具有 office 365 企业版订阅, 例如 office 365 企业版 E1、E3 或 E5 订阅。 
  
 **如果将用户的内部部署邮箱迁移到云, 是否有丢失团队聊天数据的风险？**
  
不可以。 当您将本地用户的主邮箱迁移到云时, 该用户的团队聊天数据将迁移到其新的基于云的主邮箱。
  
 **我可以将电子数据展示保留或 Office 365 保留策略应用于本地用户吗？**
  
不可以。
  
 **在我的组织提交请求以启用此功能之前, 内容搜索是否可以查找本地用户的较早的团队聊天？**
  
Microsoft 开始在2018年1月31日存储本地用户的团队聊天数据。 因此, 如果在此日期之后, 本地团队用户的标识在 active directory 和 Azure active directory 之间进行了同步, 则其团队聊天数据将存储在基于云的邮箱中, 并将使用内容搜索进行搜索。 Microsoft 还在为本地用户的基于云的邮箱中存储团队聊天数据 (从2018年1月31日到1月31日)。 有关此功能的详细信息即将推出。
