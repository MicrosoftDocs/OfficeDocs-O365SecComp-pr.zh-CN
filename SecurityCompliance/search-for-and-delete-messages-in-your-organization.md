---
title: 在 Office 365 组织中搜索和删除电子邮件-管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用 Office 365 安全&amp;合规中心中的 "搜索和清除" 功能搜索和删除组织中所有邮箱的电子邮件。
ms.openlocfilehash: ecdacd4e484d6de267e029b8e3fcdafc9b1fce4d
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223611"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>在 Office 365 组织中搜索和删除电子邮件-管理员帮助

**本文适用于管理员。您是否正在尝试查找您要删除的邮箱中的项目？请参阅[使用即时搜索查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
您可以使用 Office 365 中的内容搜索功能搜索和删除组织中所有邮箱的电子邮件。这可帮助你查找和删除可能有害或高风险的电子邮件, 例如:
  
- 包含危险附件或病毒的邮件
    
- 网络仿冒邮件
    
- 包含敏感数据的邮件
    
> [!CAUTION]
> 搜索和清除是一项强大的功能, 允许分配有必要权限的任何人从组织中的邮箱中删除电子邮件。 
  
## <a name="before-you-begin"></a>准备工作

- 若要创建和运行内容搜索, 您必须是**电子数据展示管理器**角色组的成员, 或分配有**合规性搜索**管理角色。若要删除邮件, 您必须是 "**组织管理**" 角色组的成员, 或者分配有 "**搜索和清除**" 管理角色。有关向角色组添加用户的信息, 请参阅[为用户提供对 Office 365 Security & 合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。
    
- 您必须使用 Security & 合规性中心 PowerShell 删除邮件。有关如何连接的说明, 请参阅[步骤 2](#step-2-connect-to-security-amp-compliance-center-powershell) 。
    
- 每个邮箱最多可以一次删除10个项目。因为搜索和删除邮件的功能旨在作为事件响应工具, 所以此限制有助于确保快速从邮箱中删除邮件。此功能不适用于清理用户邮箱。若要删除10个以上的项目, 您可以使用 Exchange Online PowerShell 中的**搜索-邮箱-DeleteContent**命令。请参阅[搜索和删除邮件-管理员帮助](search-for-and-delete-messagesadmin-help.md)。
    
- 通过执行搜索和清除操作, 可以在内容搜索中删除项目的最大邮箱数为50000。如果在[第1步](#step-1-create-a-content-search-to-find-the-message-to-delete)中创建的内容搜索的源邮箱多于50000个, 则清除操作 (在步骤3中创建) 将会失败。有关在50000以上邮箱上执行搜索和清除操作的提示, 请参阅[详细信息](#more-information)部分。 
    
- 本文中的过程仅可用于删除 Exchange Online 邮箱和公用文件夹中的项目。您不能使用它从 SharePoint 或 OneDrive for business 网站中删除内容。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步骤 1：创建内容搜索来查找要删除的邮件

第一步是创建并运行内容搜索, 以查找要从组织中的邮箱中删除的邮件。您可以使用安全&amp;合规性中心或通过运行**new-compliancesearch**和**new-compliancesearch** cmdlet 来创建搜索。通过在[步骤 3](#step-3-delete-the-message)中运行**new-compliancesearchaction-清除**命令, 与此搜索的查询相匹配的邮件将被删除。有关创建内容搜索和配置搜索查询的信息, 请参阅下列主题: 
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for business 网站。只能在将用于电子邮件的内容搜索中包含邮箱和公用文件夹。如果内容搜索包括网站, 则在运行**new-compliancesearchaction** cmdlet 时, 您将在步骤3中收到错误。 
  
### <a name="tips-for-finding-messages-to-remove"></a>查找要删除的邮件的提示

搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：
  
- 如果您知道邮件的主题行中使用的确切文本或短语, 请在搜索查询中使用**subject**属性。 
    
- 如果您知道邮件的确切日期（或日期范围），请在搜索查询中包括 **Received** 属性。 
    
- 如果您知道邮件的发件人，请在搜索查询中包括 **From** 属性。 
    
- 预览搜索结果以验证搜索是否仅返回您想要删除的一个或一封邮件。
    
- 使用搜索估计统计信息 (在安全&amp;合规性中心中的搜索的细节窗格中显示, 或使用[new-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) 获取总结果数的计数。 
    
以下是查找可疑电子邮件的两个查询示例。
  
- 此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>步骤 2: 连接到安全 & 合规中心 PowerShell

下一步是连接到组织的安全 & 合规中心 PowerShell。有关分步说明, 请参阅[连接到 Office 365 安全&amp;合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果您的 Office 365 帐户使用多重身份验证 (MFA) 或联合身份验证, 则不能使用上一主题中有关连接到安全 & 合规中心 PowerShell 的说明。有关使用多重身份验证的主题中的说明, 请参阅[连接到 Office 365 Security & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)中的说明。
  
## <a name="step-3-delete-the-message"></a>步骤 3: 删除邮件

创建并优化内容搜索后, 若要返回要删除并连接到安全&amp;合规中心 PowerShell 的邮件, 最后一步是运行**new-compliancesearchaction** cmdlet 以删除该邮件。您可以软或硬删除邮件。软删除的邮件将移至用户的 "可恢复的项目" 文件夹并保留, 直到已删除项目的保留期过期。硬删除的邮件被标记为从邮箱永久删除, 并且在下次邮箱由托管文件夹助理处理时将被永久删除。如果为邮箱启用了单个项目恢复, 则删除的项目保留期过期后, 将永久删除硬删除的项目。如果将邮箱置于保留状态, 则会保留已删除邮件, 直到项目的保留期过期或从邮箱中删除保留期间为止。
  
在下面的示例中, 该命令将软删除名为 "删除仿冒邮件" 的内容搜索返回的搜索结果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

若要硬删除 "删除仿冒邮件" 内容搜索返回的项目, 请运行以下命令:

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

请注意, 在运行以前的命令以软删除或硬删除邮件时, 由*SearchName*参数指定的搜索是您在步骤1中创建的内容搜索。 
  
有关详细信息, 请参阅[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。

## <a name="more-information"></a>更多信息

- **如何获取搜索和删除操作的状态？**

    运行**new-compliancesearchaction**以获取有关删除操作的状态。请注意, 在运行**new-compliancesearchaction** cmdlet 时创建的对象是使用以下格式命名的: `<name of Content Search>_Purge`。 
    
- **删除邮件后会发生什么情况？**

   使用该`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令删除的邮件将移至 "清除" 文件夹, 用户不能访问该邮件。将邮件移动到 "清除" 文件夹后, 如果为该邮箱启用了单个项目恢复, 则邮件将保留已删除项目的保留期的持续时间。(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次邮箱由托管文件夹助理处理时从 Office 365 中清除。 

   如果使用此`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令, 则邮件将移至用户的 "可恢复的项目" 文件夹中的 "删除" 文件夹。它不会立即从 Office 365 中清除。用户可以根据为邮箱配置的已删除邮件保留期, 在 "已删除邮件" 文件夹中恢复邮件的持续时间。此保留期到期后 (或者, 如果用户在邮件过期之前清除邮件), 则会将邮件移至 "清除" 文件夹, 并且用户无法再访问该邮件。在 "清除" 文件夹中, 如果为邮箱启用了单个项目恢复, 则将根据为邮箱配置的已删除项目保留期来保留邮件的持续时间。(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次该邮箱由托管文件夹助理处理时从 Office 365 中清除。 
    
- **如果您必须删除超过50000个邮箱的邮件, 该怎么办？**

    如前面所述, 您可以对最多50000个邮箱执行搜索和清除操作。如果您必须对超过50000个邮箱执行搜索和清除操作, 请考虑创建临时搜索权限筛选器, 这将减少搜索到低于50000邮箱的邮箱数。例如, 如果您的组织包含不同部门、州或国家/地区的邮箱, 则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器, 以搜索组织中的邮箱子集。创建搜索权限筛选器之后, 您将创建搜索 (在步骤1中介绍), 然后删除该邮件 (如步骤3中所述)。然后, 您可以编辑筛选器以搜索和清除不同组邮箱中的邮件。有关创建搜索权限筛选器的详细信息, 请参阅[Configure 权限筛选以进行内容搜索](permissions-filtering-for-content-search.md)。
    
- **是否将删除搜索结果中包含的未编制索引的项目？**

    否, "new-compliancesearchaction-清除" 命令不会删除未编制索引的项目。 
    
- **如果从已置于就地保留或诉讼保留中的邮箱中删除邮件或将其分配给 Office 365 保留策略, 将会发生什么情况？**

    清除邮件并将其移动到 "清除" 文件夹后, 邮件将一直保留到保留持续时间过期。如果保留持续时间不受限制, 则在删除保留或更改保留期之前, 将保留项目。
    
- **为什么在不同的安全 & 合规中心角色组之间划分搜索和删除工作流？**

    如前所述, 某个人必须是电子数据展示管理器角色组的成员, 或者被分配了合规性搜索管理角色以搜索邮箱。若要删除邮件, 某个人必须是 "组织管理" 角色组的成员, 或被分配了 "搜索和清除" 管理角色。这样, 就可以控制谁可以搜索组织中的邮箱以及谁可以删除邮件。 
