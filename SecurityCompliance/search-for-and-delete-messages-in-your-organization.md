---
title: 搜索并删除您的 Office 365 组织的管理员帮助中的电子邮件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用搜索和清除 Office 365 安全性功能&amp;合规性中心以搜索并删除从您的组织中的所有邮箱的电子邮件。
ms.openlocfilehash: d9ca212585f1cb7e98e5f577ce47fcdef7ea979f
ms.sourcegitcommit: 08f36794552e2213d0baf35180e47744d3e87fe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23531865"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>搜索并删除您的 Office 365 组织的管理员帮助中的电子邮件

**本文是针对管理员。您正在尝试查找您想要删除的邮箱中的项目吗？请参阅[查找邮件或即时搜索的项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|
   
可以使用 Office 365 中的内容的搜索功能搜索和您的组织中所有邮箱中删除电子邮件。这可以帮助您查找并删除可能有害或高风险电子邮件，如：
  
- 包含危险的附件或病毒的邮件
    
- 网络仿冒邮件
    
- 包含敏感数据的邮件
    
> [!CAUTION]
> 搜索和清除是强大功能，允许任何人都分配所需的权限从您的组织中的邮箱中删除电子邮件。 
  
## <a name="before-you-begin"></a>准备工作

- 若要创建和运行内容的搜索，您必须是**电子数据展示管理员**角色组的成员或**合规性搜索**管理角色分配。若要删除的邮件，您必须是**组织管理**角色组的成员或**搜索和清除**管理角色分配。有关将用户添加到角色组的信息，请参阅[向 Office 365 安全性授予用户访问&amp;合规性中心](grant-access-to-the-security-and-compliance-center.md)。
    
- 您必须使用安全&amp;合规性中心 PowerShell，可以删除邮件。有关如何将连接的说明，请参阅[Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) 。
    
- 每个邮箱的 10 项最多可以一次中删除。搜索并删除邮件的功能要用作事件响应工具，因为此限制有助于确保邮件快速将从邮箱中删除。此功能不适用于用户邮箱清理。若要删除 10 个以上的项目，可以在 Exchange Online PowerShell 中使用**Search-mailbox DeleteContent**命令。请参阅[搜索并删除邮件的管理员技术](search-for-and-delete-messagesadmin-help.md)。
    
- 在内容搜索，您可以通过执行搜索删除中的项目和清除操作的邮箱的最大数量为 50000。如果内容搜索 （即您在[步骤 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中创建） 具有超过 50,000 个源邮箱，则清除操作 （即您在步骤 3 中创建） 将失败。请参阅用于执行搜索提示的[详细信息](#more-information)部分和清除超过 50,000 个邮箱上的操作。 
    
- 本文中的过程只可用于删除 Exchange Online 邮箱和公用文件夹中的项目。不能用于业务网站删除 SharePoint 或 OneDrive 中的内容。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>步骤 1：创建内容搜索来查找要删除的邮件

第一步是创建和运行内容搜索以查找您想要从您的组织中的邮箱中删除的消息。您可以通过使用安全创建搜索&amp;合规性中心或通过运行**新建 ComplianceSearch**和**开始 ComplianceSearch** cmdlet。[步骤 3](#step-3-delete-the-message)中运行**新建 ComplianceSearchAction** cmdlet 将删除与此搜索查询匹配的邮件。有关创建内容搜索和配置搜索查询的信息，请参阅以下主题： 
  
- [Office 365 中的内容搜索](content-search.md)
    
- [内容搜索的关键字查询](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> 在此步骤中创建的内容搜索中搜索的内容位置的业务网站不能包含 SharePoint 或 OneDrive。可以将用于电子邮件内容搜索中包括仅邮箱和公用文件夹。如果内容搜索包括网站，您将步骤 3 中收到错误，当您运行**新建 ComplianceSearchAction** cmdlet。 
  
### <a name="tips-for-finding-messages-to-remove"></a>查找要删除的邮件提示

搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：
  
- 如果您知道确切文本或短语的邮件的主题行中使用，请搜索查询中使用**Subject**属性。 
    
- 如果您知道邮件的确切日期（或日期范围），请在搜索查询中包括 **Received** 属性。 
    
- 如果您知道邮件的发件人，请在搜索查询中包括 **From** 属性。 
    
- 预览搜索结果，以验证搜索返回仅邮件 （或消息） 所需删除。
    
- 使用搜索 estimate 统计信息 (安全中搜索的详细信息窗格中显示&amp;合规性中心或通过使用[Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) 以获取结果的总数的计数。 
    
以下是查找可疑电子邮件的两个查询示例。
  
- 此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- 此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security-amp-compliance-center-powershell"></a>步骤 2： 连接到安全&amp;合规性中心 PowerShell

下一步是连接到安全&amp;为您的组织的合规性中心 PowerShell。有关分步说明，请参阅[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
如果您的 Office 365 帐户使用多因素身份验证 (MFA) 或联合身份验证，则无法使用说明以前在连接到安全性主题中&amp;合规性中心 PowerShell。相反，请参阅主题中的说明[连接到 Office 365 安全性&amp;使用多因素身份验证的合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)。
  
## <a name="step-3-delete-the-message"></a>步骤 3： 删除邮件

您已创建并精简内容搜索以返回要删除并连接到安全的消息后&amp;合规性中心 PowerShell 中，最后一步是运行**新建 ComplianceSearchAction** cmdlet 删除邮件。已删除的邮件移动到用户的可恢复项目文件夹。 
  
在下面的示例中，该命令将删除名为“删除钓鱼邮件”的内容搜索返回的搜索结果。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```
  
*SearchName*参数指定搜索是您在步骤 1 中创建内容搜索。 
  
有关详细信息，请参阅[新建 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。
  

## <a name="more-information"></a>详细信息

- **您如何获取的搜索状态并删除操作？**

    运行**Get ComplianceSearchAction**若要获取的删除操作状态。请注意，使用以下格式命名该对象时运行**新建 ComplianceSearchAction** cmdlet 创建： `<name of Content Search>_Purge`。 
    
- **删除一条消息后，会发生什么情况？**

    通过删除一条消息`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令移动到用户的可恢复的项目文件夹中的删除文件夹。它不立即清除已从 Office 365。用户可以恢复基于配置邮箱的已删除的邮件保留期的持续时间内的已删除邮件文件夹中的邮件。此保留期 （或如果用户清除之前的邮件已到期） 后，邮件被移动到清除文件夹，并不再可以由用户访问。一次在清除文件夹中，消息是重新保留基于如果为邮箱启用单个项目恢复配置邮箱的已删除的邮件保留期的持续时间。（Office 365 中单个项目恢复为默认启用创建新邮箱时。）已删除的邮件保留期过后，邮件被标记为永久删除，并将被清除从 Office 365 下次由托管文件夹助理处理邮箱。 
    
- **您如何知道消息的删除和移动到用户的可恢复项目文件夹？**

    如果您运行相同的内容搜索后删除一条消息，您仍会看到相同数量的搜索结果 （并可能假定该邮件不从用户邮箱删除）。这是因为内容搜索中搜索可恢复邮件文件夹中，这是其中已删除的邮件移至运行后`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令。若要验证邮件已移动到可恢复邮件文件夹，可以运行 （步骤 1 中创建内容搜索，使用相同的源邮箱和搜索条件） 就地电子数据展示搜索，然后将搜索结果复制到发现邮箱。然后您可以的发现邮箱中查看搜索结果，并验证邮件已移动到可恢复邮件文件夹。创建使用源邮箱和从内容搜索的搜索查询的列表的就地电子数据展示搜索的详细信息，请参阅[使用电子数据展示工作流中的内容搜索](use-content-search-in-ediscovery.md)。 
    
- **如果您必须从超过 50,000 个邮箱中删除一条消息？**

    如前面所述，您可以执行搜索和清除 50,000 邮箱的最大操作。如果您需要执行搜索和清除超过 50,000 个邮箱上的操作，请考虑创建临时搜索权限筛选器会降低将到不超过 50,000 的邮箱搜索的邮箱数。例如，如果您的组织包含中不同部门、 州或国家/地区的邮箱，您可以创建基于其中一个邮箱属性搜索您的组织中的一部分邮箱的邮箱搜索权限筛选器。创建搜索权限筛选器后，您将创建搜索 （在步骤 1 中所述），然后删除邮件 （步骤 3 中所述）。然后您可以编辑的筛选器来搜索和清除一组不同的邮箱中的消息。有关创建搜索权限筛选器的详细信息，请参阅[筛选内容搜索配置权限](permissions-filtering-for-content-search.md)。
    
- **将删除未编制索引的项目包含在搜索结果？**

    否，`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令不删除未编制索引的项目。 
    
- **如果从已被置于就地保留或诉讼保留或已分配给 Office 365 保留策略的邮箱中删除一条消息，则会发生什么情况？**

    （由用户或已删除的邮件保留期过后） 清除邮件后，邮件保留，直到保留持续时间过期。如果是无限保留持续时间，然后直到保留被删除或更改保留持续时间也将保留项。
    
- **搜索和删除工作流是为什么划分不同的安全的是&amp;合规性中心角色组？**

    如前所述，人员必须是电子数据展示管理员角色组的成员，或者要搜索邮箱的合规性搜索管理角色分配。若要删除的邮件，人员必须是组织管理角色组的成员或搜索和清除管理角色分配。这便可以控制谁可以在组织中搜索邮箱和谁可以删除邮件。 
