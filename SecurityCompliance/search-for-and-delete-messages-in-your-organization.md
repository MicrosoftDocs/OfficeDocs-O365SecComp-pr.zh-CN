---
title: 在 Office 365 组织中搜索并删除电子邮件 - 管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用 Office 365 的安全与合规中心内的搜索和清除功能在组织中的所有邮箱中搜索并删除电子邮件。
ms.openlocfilehash: 318a7deeedb6bd4875a7a2ca0f5e33b764bdbac3
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854626"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>在 Office 365 组织中搜索并删除电子邮件 - 管理员帮助

**本文适用于管理员。你是否尝试在邮箱中查找要删除的项目？请参阅[使用“即时搜索”查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
你可以使用 Office365 中的内容搜索功能在组织中的所有邮箱中搜索并删除电子邮件。 这可以帮助你查找并删除可能有害或高风险的电子邮件，例如：
  
- 包含危险附件或病毒的邮件
    
- 网络仿冒邮件
    
- 包含敏感数据的邮件
    
> [!CAUTION]
> 搜索和清除是一项强大的功能，允许分配有必要权限的任意用户从组织的邮箱中删除电子邮件。 
  
## <a name="before-you-begin"></a>准备工作

- 若要创建并运行内容搜索，你必须是**电子数据展示管理员**角色组的成员，或者分配有**合规性搜索**管理角色。 若要删除邮件，你必须是**组织管理**角色组的成员或分配有**搜索并清除**管理角色。 有关将用户添加到角色组的信息，请参阅[向用户授予对安全与合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。
    
- 你必须使用安全与合规中心 PowerShell 删除邮件。 有关如何连接的说明，请参阅[步骤 2](#step-2-connect-to-security--compliance-center-powershell)。
    
- 一次最多可以删除每个邮箱的 10 封邮件。 因为搜索和删除邮件的功能是用作事件响应工具，所以此限制可帮助确保从邮箱中快速删除邮件。 此功能并不用于清理用户邮箱。 若要删除 10 个以上的项目，可以使用 Exchange Online PowerShell 中的 **Search-Mailbox -DeleteContent** 命令。 请参阅[搜索和删除邮件 - 管理员帮助](search-for-and-delete-messagesadmin-help.md)。
    
- 在内容搜索中，可通过搜索和清除操作删除其内项目的最大邮箱数为 50,000。 如果内容搜索（在[步骤 1](#step-1-create-a-content-search-to-find-the-message-to-delete) 中创建）具有超过 50,000 个源邮箱，则清除操作（在步骤 3 中创建）将失败。 请参阅[详细信息](#more-information)部分，以了解有关对超过 50,000 个邮箱执行搜索和清除操作的提示。 
    
- 本文中所述的步骤只能用于删除 Exchange Online 邮箱和公用文件夹中的项目。 无法将其用于删除 SharePoint 或 OneDrive for Business 网站中的内容。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步骤 1：创建内容搜索来查找要删除的邮件

第一步是创建并运行内容搜索以查找您想要从组织的邮箱中删除的邮件。 你可以通过使用安全与合规中心或运行 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlet 来创建搜索。 与此搜索的查询匹配的邮件将通过在[步骤 3](#step-3-delete-the-message) 中运行 **New-ComplianceSearchAction -Purge** 命令来删除。 有关创建内容搜索和配置搜索查询的信息，请参阅下列主题： 
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for Business 网站。 只能在内容搜索中包含将用于电子邮件的邮箱和公用文件夹。 如果内容搜索包含网站，则在运行 **New-ComplianceSearchAction** cmdlet 时，你将在步骤 3 中收到错误消息。 
  
### <a name="tips-for-finding-messages-to-remove"></a>查找要删除的邮件的提示

搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：
  
- 如果你知道邮件的主题行中使用的确切文本或短语，请在搜索查询中使用**主题**属性。 
    
- 如果你知道邮件的确切日期（或日期范围），请搜索查询中包括**接收日期**属性。 
    
- 如果你知道邮件的发件人，请在搜索查询中包括**收件人**属性。 
    
- 预览搜索结果以验证搜索是否仅返回你想要删除的邮件。
    
- 使用搜索估计统计信息（在安全与合规中心内的搜索的详细信息窗格中显示，或使用 [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet）获取结果总数。 
    
以下是查找可疑电子邮件的两个查询示例。
  
- 此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步骤 2：连接到安全与合规中心 PowerShell

下一步是连接到组织的安全与合规中心 PowerShell。 有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果你的 Office 365 帐户使用多重身份验证 (MFA) 或联合身份验证，则无法使用上一主题中有关连接到安全与合规中心 PowerShell 的说明。 请改为参阅主题[使用多重身份验证连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell) 中的说明。
  
## <a name="step-3-delete-the-message"></a>步骤 3：删除邮件

创建并优化内容搜索以返回你想要删除的邮件并且连接到安全与合规中心 PowerShell 后，最后一步是运行 **New-ComplianceSearchAction** cmdlet 来删除邮件。 可对邮件进行软删除或硬删除。 软删除的邮件将移至用户的“可恢复的项目”文件夹并保留，直到已删除项目的保留期到期。 硬删除的邮件被标记为从邮箱中永久删除，并在托管文件夹助理下次处理邮箱时永久删除。 如果为邮箱启用了单个项目恢复，则在已删除项目的保留期到期后，将永久删除硬删除的项目。 如果邮箱处于保留状态，则会保留已删除的邮件，直到该项目的保留期到期或从邮箱中删除保留为止。
  
在以下示例中，该命令将软删除名为“删除网络钓鱼邮件”的内容搜索返回的搜索结果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

若要硬删除由“删除网络钓鱼邮件”内容搜索返回的项目，你需要运行以下命令：

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

请注意，当你运行上一个命令以软删除或硬删除邮件时，*SearchName* 参数是你在步骤 1 中创建的内容搜索。 
  
有关详细信息，请参阅 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。

## <a name="more-information"></a>详细信息

- **如何获取有关搜索和删除操作的状态？**

    运行 **Get-ComplianceSearchAction** 以获取有关删除操作的状态。 请注意，运行 **New-ComplianceSearchAction** cmdlet 时创建的对象使用以下格式命名：`<name of Content Search>_Purge`。 
    
- **删除邮件后会发生什么情况？**

   使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令删除的邮件将移至“清除”文件夹，用户无法访问这些邮件。 将邮件移至“清除”文件夹后，如果为邮箱启用了单个项目恢复，则会在已删除的邮件保留期内保留邮件。 （在 Office 365 中，创建新邮箱时将默认启用单个项目恢复。）已删除项目的保留期到期后，邮件将标记为永久删除，并在托管文件夹助手下次处理邮箱时从 Office 365 中清除。 

   如果使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，邮件将移至用户的“可恢复的项目”文件夹内的“删除”文件夹中。 它不会立即从 Office 365 中清除。 在基于为邮箱配置的已删除邮件保留期的持续时间内，用户可以恢复“已删除邮件”文件夹中的邮件。 此保留期过期（或如果用户在过期之前清除邮件）后，邮件将移动到“清除”文件夹，用户将无法再访问。 进入“清除”文件夹后，如果启用了邮箱的单个邮件恢复，则邮件将保留一段时间，该时间取决于为邮箱配置的已删除邮件保留期。 （在 Office 365 中，创建新邮箱时将默认启用单个项目恢复。）已删除项目的保留期到期后，邮件将标记为永久删除，并在托管文件夹助手下次处理邮箱时从 Office 365 中清除。 
    
- **如果必须删除超过 50,000 个邮箱中的邮件，该怎么办？**

    如前文所述，你可以对最多 50,000 个邮箱执行搜索和清除操作。 如果必须对超过 50,000 个邮箱执行搜索和清除操作，请考虑创建临时搜索权限筛选器，这会将要搜索的邮箱数减少到低于 50,000 个。 例如，如果你的组织包含不同部门、州或国家/地区的邮箱，则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器，以搜索组织内的邮箱子集。 创建搜索权限筛选器后，将创建搜索（如步骤 1 中所述），然后删除邮件（如步骤 3 中所述）。 然后，你可以编辑筛选器以搜索和清除不同邮箱集中的邮件。 有关创建搜索权限筛选器的详细信息，请参阅[配置内容搜索的权限筛选](permissions-filtering-for-content-search.md)。
    
- **是否会删除搜索结果中包含的未编制索引的项目？**

    不会，New-ComplianceSearchAction -Purge 命令不会删除未编制索引的项目。 
    
- **如果从处于就地保留或诉讼保留状态的邮箱中删除邮件或为邮件分配 Office 365 保留策略，会发生什么情况？**

    清除邮件并将其移至“清除”文件夹后，将保留邮件，直到保留期到期为止。 如果为无限期的保留期，则这些项目会一直保留到你删除保留设置或更改保留期。
    
- **为什么在不同的安全与合规中心角色组之间划分搜索和删除工作流？**

    如前所述，必须是电子数据展示管理员角色组的成员或者分配有合规性搜索管理角色的用户才能搜索邮箱。 若要删除邮件，必须是组织管理角色组的成员，或分配有“搜索并清除”管理角色。 这就使得可以控制哪些人可以搜索组织中的邮箱以及哪些人可以删除邮件。 
