---
title: 在 Office 365 安全&amp;合规中心搜索审核日志
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: '使用 Office 365 安全性 & 合规性中心搜索统一的审核日志，以查看 Office 365 组织中的用户和管理员的活动。 '
ms.openlocfilehash: 848dbbdeb8b7cd9abd664b5ac401f6afde31c1e1
ms.sourcegitcommit: c40eee4ef3890056da58649e4617283b0b9d1673
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2019
ms.locfileid: "29735464"
---
# <a name="search-the-audit-log-in-the-office-365-security--compliance-center"></a>Office 365 安全性 & 合规性中心中的搜索审核日志

是否要查找是否用户查看特定文档或清除其邮箱中的项目？如果是，可以使用 Office 365 安全性&amp;搜索统一的审核日志，以查看 Office 365 组织中的用户和管理员的活动的合规性中心。为什么统一的审核日志？因为您可以搜索以下类型的用户和管理 Office 365 中的活动：
  
- SharePoint Online 和 OneDrive for Business 内的用户活动
    
- Exchange Online 中的用户活动 （Exchange 邮箱审核日志记录）
    
    > [!IMPORTANT]
    > 邮箱审核日志记录必须打开每个用户邮箱的 Exchange Online 中的用户活动将会记录之前。有关详细信息，请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。
  
- SharePoint Online 中管理活动
    
- 管理 Azure Active Directory （Office 365 的目录服务） 中的活动
    
- Exchange Online 中的管理活动 （Exchange 管理员审核日志记录）
    
- Sway 中的用户和管理活动
    
- Office 365 安全性 & 合规性中心中的电子数据展示活动
    
- Power BI 中的用户和管理活动
    
- 在 Microsoft 团队中的用户和管理活动

- Dynamics 365 中的用户和管理活动
    
- Yammer 中的用户和管理活动
 
- Microsoft 流中的用户和管理活动
    
- Microsoft 流中的用户和管理活动
    
   
## <a name="before-you-begin"></a>准备工作

请务必阅读以下各项开始搜索 Office 365 之前审核日志。
  
- 审核日志记录可以开始搜索的 Office 365 审核日志之前必须先打开您 （或其他管理员）。要将其打开，只需单击**开始录制用户和管理活动**的**审核日志搜索**页上，在安全&amp;合规性中心。（如果您看不到此链接，具有已打开审核为您的组织。）您将其打开后，将显示一条消息，指出正在准备审核日志和，您可以在几个小时准备完毕后运行搜索。您只需执行一次。 
    
    > [!NOTE]
    > 我们启用审计默认情况下的过程。之前，您可以将其打开如上文所述。 
  
- 您必须分配仅查看审核日志或审核日志角色在 Exchange Online 要搜索的 Office 365 审核日志。默认情况下，这些角色分配给 Exchange 管理中心中的**权限**页上合规性管理和组织管理角色组。若要使用户能够搜索的 Office 365 审核日志的最小的权限级别，可以自定义角色组 Exchange Online 中创建、 添加仅查看审核日志或审核日志角色，然后将用户添加新角色组的成员。有关详细信息，请参阅[管理角色组在 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=730688)。
    
    > [!IMPORTANT]
    > 如果您安全中**权限**页上的仅查看审核日志或审核日志角色分配用户&amp;合规性中心，它们将无法搜索的 Office 365 审核日志。您必须分配 Exchange Online 中的权限。这是因为基础 cmdlet 用于搜索的审核日志是 Exchange Online cmdlet。 
  
- 时由用户或管理员执行审核的活动，则审核记录生成并存储在您的组织的 Office 365 审核日志中。审计记录是保留 （并且可在审核日志中搜索） 的时间长度取决于您的 Office 365 订阅和专门分配给特定用户的许可证的类型。

     - **Office 365 E3** -审核记录保留 90 天。这意味着您可以搜索审核日志的最近 90 天内执行的活动。

     - **Office 365 E5** -审核记录保留 for 365 天 （一年）。这意味着您可以搜索活动执行去年之内的审核日志。一年时间保留审核记录也是可供用户分配一个 E3/Exchange Online 计划 1 许可证且具有的 Office 365 高级合规性附加许可证。

        > [!NOTE]
        > E5 组织 （或高级合规性加载项许可证已 E3 公司） 的审核记录的一年保持期目前仅作为专用的预览计划的一部分。要在此预览计划中注册，请文件与[Microsoft 支持](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fcontact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online)的请求，并包括以下内容作为需要帮助的说明： 长期 Office 365 审核日志专用预览版。

- 如果您想要关闭为您的组织的 Office 365 中的审核日志搜索，您可以在远程 PowerShell 连接到 Exchange Online 组织中运行以下命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    若要再次打开审核搜索，可以在 Exchange Online PowerShell 中运行以下命令：
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    有关详细信息，请参阅[关闭 Office 365 中的审核日志搜索](turn-audit-log-search-on-or-off.md)。
    
- 如前面所述，用于搜索的审核日志的基础 cmdlet 为 Exchange Online cmdlet，即**搜索 UnifiedAuditLog**。这意味着您可以使用此 cmdlet 可以搜索而不是在安全使用**审核日志搜索**页上的 Office 365 审核日志&amp;合规性中心。您必须在连接到 Exchange Online 组织的远程 PowerShell 中运行此 cmdlet。有关详细信息，请参阅[搜索 UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776)。
    
- 如果您想要以编程方式下载 Office 365 审核日志中的数据，我们建议您使用 Office 365 管理活动 API，而不是使用 PowerShell 脚本。Office 365 管理活动 API 可用于开发操作、 安全性和合规性贵组织的监控解决方案的 REST web 服务。有关详细信息，请参阅[Office 365 管理活动 API 参考 （英文）](https://go.microsoft.com/fwlink/?linkid=852309)。
    
- 它可能需要 30 分钟或设置为 24 小时事件之后发生相应的审核日志条目要显示在搜索结果中。下表显示了 Office 365 中的不同服务所花的时间。
    
    |**Office 365 服务**|**30 分钟**|**24 小时**|
    |:-----|:-----|:-----|
    |高级的威胁保护和威胁智能  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
    |Azure Active Directory （用户登录事件）  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Azure Active Directory （admin 事件）  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
    |Azure Active Directory （用户登录事件）  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |数据丢失防护  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Dynamics 365 CRM <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |电子数据展示  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Exchange Online  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Microsoft Flow  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Forms  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Project  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Stream  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Teams  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Power BI  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |安全&amp;合规性中心  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |SharePoint Online 和 OneDrive for Business  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Sway  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Yammer  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure AD) 是 Office 365 的目录服务。统一的审核日志包含用户、 组、 应用程序、 域和目录执行 Office 365 管理中心中或在 Azure 中的活动管理门户。Azure AD 事件的完整列表，请参阅[Azure Active Directory 审核报表事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)。
    
- Exchange Online 审核日志包含两种类型的事件： Exchange admin 事件 （由管理员执行的操作） 和邮箱事件 （邮箱上的用户采取的操作）。请注意，不默认启用邮箱审核。它必须是邮箱事件可以在 Office 365 的审核日志搜索的每个用户邮箱启用。有关邮箱审核和邮箱审核记录的操作的详细信息，请参阅[启用邮箱审核 Office 365 中](enable-mailbox-auditing.md)。
    
- 默认情况下不启用审核日志记录的 Power BI。若要搜索的 Office 365 审核日志中的 Power BI 活动，您必须在 Power BI 管理门户中启用审核。有关说明，请参阅[Power BI 管理门户](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)中的"审核日志"一节。
    
    
## <a name="search-the-audit-log"></a>搜索审核日志

下面是在 Office 365 中搜索审核日志的过程。
  
[步骤 1： 运行审核日志搜索](#step-1-run-an-audit-log-search)
  
[步骤 2： 查看搜索结果](#step-2-view-the-search-results)

[步骤 3： 筛选搜索结果](#step-3-filter-the-search-results)

[步骤 4： 将搜索结果导出到文件](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>步骤 1： 运行审核日志搜索

1. 转到 [https://protection.office.com](https://protection.office.com)。
    
    > [!TIP]
    > 专用浏览会话 （不正则会话） 用于访问 Office 365 安全性&amp;合规性中心，因为这将阻止您当前登录与从正在使用的凭据。若要打开 Internet Explorer 或 Microsoft 边缘 InPrivate 浏览会话，只需按 CTRL + SHIFT + P。要打开私有浏览会话中 Google Chrome （称为 incognito 窗口），请按 CTRL + SHIFT + N。 
  
2. 使用工作或学校帐户登录到 Office 365。
    
3. 安全的左窗格中&amp;合规性中心，单击**搜索&amp;调查**，然后单击**审核日志搜索**。
    
    将显示**审核日志搜索**页。 
    
    ![配置条件，然后单击搜索运行报告](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > 您具有对第一个打开审核日志记录，然后才能运行审核日志搜索。如果显示**开始录制用户和管理活动**链接，请单击它以启用审核。如果您看不到此链接，审核已打开您的组织。 
  
4. 配置以下搜索条件：
    
    a.**活动**单击下拉列表以显示您可以搜索活动。用户和管理活动进行组织到组的相关活动。您可以选择特定的活动，或者您可以单击选择组中的所有活动的活动组名称。您还可以单击以清除选定内容的所选的活动。运行搜索后，将显示仅的审核日志条目的所选的活动。选择**显示所有活动的结果**将显示由所选的用户或用户组执行的所有活动的结果。 
    
    Office 365 审核日志记录 100 多个用户和管理活动。单击在这篇文章，请参阅的每个活动中的每个不同的 Office 365 服务说明主题**Audited 活动**选项卡。 
    
    默认情况下选中 b.**开始日期**和**结束日期**最近七天。选择要显示在该时间段内发生的事件日期和时间范围。以协调世界时 (UTC) 格式显示日期和时间。您可以指定的最大的日期范围是 90 天。如果选定的日期范围大于 90 天，则显示错误。 
    
    > [!TIP]
    > 如果您使用的 90 天的最大的日期范围，选择当前时间的**开始日期**。否则，您会收到错误消息的开始日期早于的结束日期。如果您已打开审核最近 90 天内，打开已审核的日期之前，无法开始的最大的日期范围。 
  
    c.**用户**在此框，然后选择一个或多个用户通过单击以显示搜索结果。通过在此框中选择的用户执行所选活动审核日志条目的结果列表中显示。将此框保留为空返回组织中的所有用户 （和服务帐户） 的条目。 
    
    d.**文件、 文件夹或网站**键入一些或全部文件或文件夹名称搜索与包含指定的关键字的文件夹的文件相关的活动。您还可以指定文件或文件夹的 URL。如果您使用的 URL，确保类型的完整的 URL 路径或如果您只需键入 URL 的任何部分不包括任何特殊字符或空格。 
    
    将此框保留为空返回组织中的所有文件和文件夹的条目。
    
    > [!TIP]
    > 如果您正在寻找与**网站**相关的所有活动，添加通配符 (\*) 后返回该网站; 的所有条目的 URL例如， **"https://contoso-my.sharepoint.com/personal/*"**。
    
5. 单击**搜索**以运行搜索使用您的搜索条件。 
    
    加载搜索结果，并在片刻后它们都显示在**结果**下。完成搜索后，将显示找到的结果数。请注意，最多 5000 个事件会显示在**结果**窗格中的 150 事件，则增量如果 5,000 多个事件符合搜索条件，会显示最近 5000 个事件。 
    
    ![完成搜索后显示的结果数](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>搜索审核日志的提示

- 您可以选择特定的活动搜索通过单击活动的名称。或者，您可以通过单击组名来搜索 （如**文件和文件夹活动**） 组中的所有活动。如果选择活动，则可以单击它以取消选择。您可以使用搜索框以显示包含您键入的关键字的活动。
    
    ![单击以选择所有活动的活动组名称](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- 您必须选择**活动**列表以显示来自 Exchange 管理员审核日志的事件中的**显示所有活动的结果**。此审核日志中的事件在结果中的**活动**列中显示 cmdlet 名称 （例如，**设置邮箱**）。有关详细信息，本主题中的**Audited 活动**选项卡，然后单击**Exchange 管理员活动**。
    
    同样，有一些不具有对应项**活动**列表中的审核活动。如果您知道这些活动的操作的名称，您可以搜索所有活动，然后通过在**活动**列的框中键入操作的名称筛选结果。请参阅[步骤 3： 筛选搜索结果](#step-3-filter-the-search-results)有关对结果进行筛选的详细信息。 
    
- 单击**清除**以清除当前的搜索条件。日期范围返回到最近七天的默认值。您还可以单击**清除所有以显示所有活动的结果**以取消所有选定的活动。 
    
- 如果找到 5000 个结果，您可能可以假定有符合搜索条件的 5,000 多个事件。可以优化搜索条件并重新运行搜索以返回更少的结果，也可以通过选择**导出结果**中导出所有搜索结果的\>**下载所有结果**。

  
### <a name="step-2-view-the-search-results"></a>步骤 2： 查看搜索结果

在**结果**下**审核日志搜索**页上显示审核日志搜索的结果。如上文所述增量为 150 事件显示最多 5000 个 （最新） 的事件。要显示多个事件可以在**结果**窗格中使用滚动条，或您可以按**Shift + End**可显示下一步 150 事件。 
  
结果包含以下有关搜索返回的每个事件的信息。
  
- **日期：** 日期和时间 （采用 UTC 格式） 时事件发生。 
    
- **IP 地址：** 活动已记录时所使用的设备的 IP 地址。IP 地址被显示在 IPv4 或 IPv6 地址格式。 
    
- **用户：** 用户 （或服务帐户） 执行触发该事件的操作的人员。 
    
- **活动：** 执行用户的活动。此值对应于您在**活动**下拉列表中选择的活动。Exchange 管理员审核日志中的事件，此列中的值是 Exchange cmdlet。 
    
- **项：** 创建或修改由于相应的活动对象。例如，查看或修改的文件或已更新的用户帐户。并非所有活动都具有此列中的值。 
    
- **详细信息：** 有关活动的其他详细信息。同样，并非所有活动将都具有的值。 
    
> [!TIP]
> 在**结果**对结果进行排序，请单击列标题。您可以从 A 到 Z 或 Z 的结果进行排序答： 依次单击**Date**标头从旧的结果进行排序为最新的或降序。 
  
#### <a name="view-the-details-for-a-specific-event"></a>查看特定事件的详细信息

您可以通过单击事件记录的搜索结果列表中查看有关事件的更多详细信息。**详细信息**页将显示一个包含事件记录的详细的属性。显示属性取决于 Office 365 服务发生该事件。若要显示这些详细信息，请单击**详细信息**。有关说明，请参阅[Office 365 中的详细的属性审核日志](detailed-properties-in-the-office-365-audit-log.md)。
  
![单击查看审核日志事件记录的详细的属性的详细信息](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>步骤 3： 筛选搜索结果

除了排序，您还可以筛选审核日志搜索的结果。这是一项强大功能，可帮助您快速筛选特定用户或活动的结果。可以最初创建范围的搜索，然后快速筛选结果以查看特定的事件。然后可以缩小范围的搜索条件并重新运行搜索以返回较小的、 更简洁的结果集。
  
若要筛选结果：
  
1. 运行审核日志搜索。
    
2. 结果显示后，单击**筛选结果**。
    
    关键字框都显示在每个列标题下。
    
3. 单击其中一个框列标题下，键入的字词或短语，具体取决于您要筛选的列。结果将动态重新调整以显示与筛选器匹配的事件。
    
    ![键入的词在筛选器以显示筛选器匹配的事件](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. 若要清除筛选器，请单击筛选器框中的**X** ，或只需单击**隐藏筛选**。
    
> [!TIP]
> 若要显示 Exchange 管理员审核日志中的事件，键入**-**（划线） 在**活动**筛选框。这将显示 cmdlet 名称，Exchange 管理员事件的**活动**列中显示。然后您可以对 cmdlet 名称按字母顺序进行排序。 

### <a name="step-4-export-the-search-results-to-a-file"></a>步骤 4： 将搜索结果导出到文件

您可以到本地计算机上的逗号分隔的值 (CSV) 文件导出审核日志搜索的结果。您可以在 Microsoft Excel 中打开此文件并用功能，如搜索、 排序、 筛选和拆分单列 （它包含的多值单元格） 到多个列。
  
1. 运行审核日志搜索，，然后再修订的搜索条件，直到您拥有所需的结果。
    
2. 单击**导出结果**，然后选择以下选项之一： 
    
  - **保存已加载的结果**选择此选项可仅显示在**结果**下的条目导出 * * 审核日志搜索 * * 页。下载的 CSV 文件包含相同列 （和数据） 显示在上 （日期、 用户、 活动、 项目和详细信息）。包含审核日志条目的详细信息的 CSV 文件中包含 （名为**多个**） 其他列。您正在导出已加载 （且可查看） 相同的结果导出**审核日志搜索**页上，最多 5,000 项。 
    
  - **下载所有结果**选择此选项可导出符合搜索条件的 Office 365 审核日志中的所有条目。搜索结果的一大组，选择此选项，除了可以显示在**审核日志搜索**页的 5,000 结果审核日志中下载的所有条目。此选项将中审核日志中下载的原始数据到 CSV 文件，并包含名为**AuditData**的列中的审核日志条目的其他信息。可能需要长下载文件，如果您选择此导出选项，因为文件可能比下载，如果您选择其他选项的一个大得多。
    
    > [!IMPORTANT]
    > 您可以从单个审核日志搜索到 CSV 文件下载最多 50,000 条目。如果 50,000 条目下载到 CSV 文件中，您可能可以假定有超过 50,000 个的满足搜索条件的事件。若要导出超过此限制，请尝试使用日期范围减少审核日志条目的数量。您可能需要使用较小要导出超过 50,000 个条目的日期范围运行多个搜索。 
  
3. 选择导出选项后，将提示您打开 CSV 文件，将其保存到下载文件夹中，或将其保存到特定文件夹的窗口底部显示一条消息。

  
#### <a name="more-information-about-exporting-audit-log-search-results"></a>有关导出审核日志搜索结果的详细信息

- **下载所有结果**选项到 CSV 文件下载 Office 365 审核日志中的原始数据。此文件包含不同的列名称 （CreationDate、 Userid、 操作、 AuditData） 比如果选择了**已加载的结果保存**选项下载的文件。同一个活动的两个不同 CSV 文件中的值也可能不同。例如，在 CSV**操作**列中的活动文件和可能的值不同**审核日志搜索**页面; 上的**活动**列中显示的"用户友好"版本例如，MailboxLogin 与用户登录到邮箱。
    
- 下载所有结果，如果 CSV 文件将包含名为**AuditData**，其中包含有关每个事件的其他信息的列。如前面所述，此列包含多个属性的审核日志记录的多值属性。此多值属性中的**属性： 值**对的每个用逗号分隔。您可以使用 Excel 中的 Power 查询将此列拆分为多个列，以使每个属性具有其自己的列。这将允许您进行排序和上一个或多个属性筛选器。若要了解如何执行此操作，请参阅[拆分文本 （电源查询） 的列](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)中的"拆分列分隔符由"一节。
    
    拆分**AuditData**列后，可以在**操作**列中显示活动的特定类型的详细的属性中进行筛选。 
    
- 没有显示在审核记录的**AuditData**字段中的数据的 3,060 字符限制。如果超过 3,060 字符限制，则此字段中的数据被截断。 
    
- 当您从包含来自不同 Office 365 服务的事件的搜索查询下载所有结果时，CSV 文件中的**AuditData**列包含根据服务操作中执行的不同属性。例如，从 Exchange 和 Azure AD 的审核日志条目包含一个名为**ResultStatus**指示如果操作是成功还是失败属性。此属性不包含在 SharePoint 中的事件。同样，SharePoint 事件具有标识的网站的属性相关的活动，文件和文件夹的 URL。若要减轻此行为，请考虑使用不同的搜索从单个服务导出活动的结果。 
    
    一个适用于时下载所有结果和服务均为 CSV 文件中的**AuditData**列中列出的属性的说明，请参阅[Office 365 中的详细的属性审核日志](detailed-properties-in-the-office-365-audit-log.md)。

## <a name="audited-activities"></a>审核的活动

本节中的表介绍了审核 Office 365 中的活动。您可以搜索这些通过搜索审核的事件日志中安全&amp;合规性中心。单击**搜索审核日志**选项卡的分步说明。 
  
这些表组相关的活动或特定的 Office 365 服务中的活动。表包括**活动**下拉列表中显示的友好名称和相应操作时导出搜索结果显示在审核记录的详细信息和 CSV 文件的名称。有关详细信息的说明，请参阅[Office 365 中的详细的属性审核日志](detailed-properties-in-the-office-365-audit-log.md)。
  
单击以下链接以转到特定表之一。
  
||||
|:-----|:-----|:-----|
|[文件和页上的活动](#file-and-page-activities)<br/> |[文件夹活动](#folder-activities)<br/> |[共享和访问请求活动](#sharing-and-access-request-activities)<br/> |
|[同步活动](#synchronization-activities)<br/> |[网站管理活动](#site-administration-activities)<br/> |[Exchange 邮箱活动](#exchange-mailbox-activities)<br/> |
|[Sway 活动](#sway-activities) <br/> |[用户管理活动](#user-administration-activities) <br/> |[Azure AD 组管理活动](#azure-ad-group-administration-activities) <br/> |
|[应用程序管理活动](#application-administration-activities) <br/> |[角色管理活动](#role-administration-activities) <br/> |[目录管理活动](#directory-administration-activities) <br/> |
|[电子数据展示活动](#ediscovery-activities) <br/> |[Power BI 活动](#power-bi-activities) <br/> |[Microsoft 团队活动](#microsoft-teams-activities) <br/> |
|[Yammer 活动](#yammer-activities) <br/> |[Microsoft Flow](#microsoft-flow) <br/> |[Microsoft Stream](#microsoft-stream) <br/>|
|[Exchange 管理员审核日志](#exchange-admin-audit-log) <br/> |
   
  
### <a name="file-and-page-activities"></a>文件和页上的活动
  
下表介绍 SharePoint Online 和 OneDrive for Business 中的文件和页上活动。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|访问的文件  <br/> |FileAccessed  <br/> |用户或系统帐户访问文件。  <br/> |
|（无）  <br/> |FileAccessedExtended  <br/> |这与"访问文件"相关 (FileAccessed) 活动。较长时间 （最多为 3 小时） 的同一个人不断访问过的文件时，将记录 FileAccessedExtended 事件。记录 FileAccessedExtended 事件的目的是减少 FileAccessed 不断访问文件时记录的事件数。这有助于减少噪音是什么本质上是相同的多个 FileAccessed 记录的用户活动，并允许您关注的初始 （和更重要） FileAccessed 事件。  <br/> |
|已签入文件  <br/> |FileCheckedIn  <br/> |用户签入他们从文档库中签出文档。  <br/> |
|签出文件  <br/> |FileCheckedOut  <br/> |用户签出文档位于文档库中。用户可以签出并对已与他们共享的文档进行更改。  <br/> |
|复制的文件  <br/> |FileCopied  <br/> |用户将文档复制从网站中。复制的文件可以保存到网站上的另一个文件夹。  <br/> |
|已删除的文件  <br/> |FileDeleted  <br/> |用户从网站删除文档。  <br/> |
|从回收站中的已删除的文件  <br/> |FileDeletedFirstStageRecycleBin  <br/> |用户从网站的回收站中删除文件。  <br/> |
|从第二阶段回收站删除的文件  <br/> |FileDeletedSecondStageRecycleBin  <br/> |用户从网站的第二阶段回收站中删除文件。  <br/> |
|文件中检测到恶意软件  <br/> |FileMalwareDetected  <br/> |SharePoint 防病毒引擎检测到文件中的恶意软件。  <br/> |
|丢弃的文件的签出  <br/> |FileCheckOutDiscarded  <br/> |用户放弃（或撤消） 签出的文件。这意味着将放弃签出文件时对其所做的所有更改，并且不会保存到文档库中的文档版本。  <br/> |
|下载的文件  <br/> |FileDownloaded  <br/> |用户从网站下载文档。  <br/> |
|已修改的文件  <br/> |已修改文件  <br/> |用户或系统帐户修改内容或网站上文档的属性。  <br/> |
|（无）  <br/> |FileModifiedExtended  <br/> |这与相关的"修改文件"（已修改文件） 活动。较长的时间 （最多为 3 小时） 为同一个人不断修改过的文件时，将记录 FileModifiedExtended 事件。记录 FileModifiedExtended 事件的目的是减少不断修改文件时记录的已修改文件事件数。这有助于减少噪音是什么本质上是相同的多个已修改文件记录的用户活动，并允许您关注的初始 （和更重要） 的已修改文件事件。  <br/> |
|移动的文件  <br/> |FileMoved  <br/> |用户移动文档从其当前位置网站上为新的位置。  <br/> |
|都已回收文件的所有次要版本  <br/> |FileVersionsAllMinorsRecycled  <br/> |用户从一个文件的版本历史记录中删除所有次要版本。删除的版本移至网站的回收站。  <br/> |
|都已回收文件的所有版本  <br/> |FileVersionsAllRecycled  <br/> |用户从一个文件的版本历史记录中删除所有版本。删除的版本移至网站的回收站。  <br/> |
|已回收的文件版本  <br/> |FileVersionRecycled  <br/> |用户删除文件的版本历史记录的版本。已删除的版本移动到该网站的回收站。  <br/> |
|重命名的文件  <br/> |FileRenamed  <br/> |用户重命名的网站上的文档。  <br/> |
|还原的文件  <br/> |FileRestored  <br/> |用户从网站的回收站还原文档。  <br/> |
|上载的文件  <br/> |FileUploaded  <br/> |用户将文档上载到网站上的文件夹。  <br/> |
|查看的页  <br/> |PageViewed  <br/> |用户查看网站上的页面。这不包括使用 Web 浏览器查看位于文档库中的文件。  <br/> |
|（无）  <br/> |PageViewedExtended  <br/> |这与"查看页面"(PageViewed) 活动。同一个人将不断查看一段的时间 （最多为 3 小时） 的网页时，将记录 PageViewedExtended 事件。记录 PageViewedExtended 事件的目的是减少 PageViewed 不断查看页面时记录的事件数。这有助于减少噪音是什么本质上是相同的多个 PageViewed 记录的用户活动，并允许您关注的初始 （和更重要） PageViewed 事件。  <br/> |
  
### <a name="folder-activities"></a>文件夹活动
  
下表介绍了 SharePoint Online 和 OneDrive for Business 中的文件夹活动。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|复制的文件夹  <br/> |FolderCopied  <br/> |用户将文件夹从网站复制到 SharePoint 或 OneDrive for Business 中的另一个位置。  <br/> |
|创建的文件夹  <br/> |FolderCreated  <br/> |用户在网站上创建一个文件夹。  <br/> |
|已删除的文件夹  <br/> |FolderDeleted  <br/> |用户从网站中删除一个文件夹。  <br/> |
|从回收站中的已删除的文件夹  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |用户可从网站上的回收站中删除一个文件夹。  <br/> |
|从第二阶段回收站删除的文件夹  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |用户可从网站上的第二阶段回收站删除文件夹。  <br/> |
|已修改的文件夹  <br/> |FolderModified  <br/> |用户修改的站点上的文件夹。这包括更改文件夹元数据，如更改标记和属性。  <br/> |
|移动的文件夹  <br/> |FolderMoved  <br/> |用户在网站上移动到其他位置的文件夹。  <br/> |
|重命名的文件夹  <br/> |FolderRenamed  <br/> |用户重命名的网站上的文件夹。  <br/> |
|还原的文件夹  <br/> |FolderRestored  <br/> |用户从网站上的回收站还原已删除的文件夹。  <br/> |
  
### <a name="sharing-and-access-request-activities"></a>共享和访问请求活动
  
下表介绍了 SharePoint Online 和 OneDrive for Business 中的用户共享和访问请求活动。对于共享事件，在**结果**下的**详细信息**列标识的用户或组与已共享项目的名称以及该用户或组是一个成员或您的组织中的来宾。有关详细信息，请参阅[使用共享 Office 365 审核日志中的审核功能](use-sharing-auditing.md)。
  
> [!NOTE]
> 用户可以是*成员*或*来宾*基于用户对象的 UserType 属性。成员通常是一名员工，并且来宾通常是组织之外的合作者。当用户接受共享邀请 （并且已不属于您的组织） 时，来宾帐户将为其创建贵组织的目录中。一旦来宾用户目录中拥有帐户，可能 （而无需邀请） 直接与他们共享资源。 
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|接受访问请求  <br/> |AccessRequestAccepted  <br/> |为网站、 文件夹或文档的访问请求被接受，并请求用户有权访问。  <br/> |
|接受共享邀请  <br/> |SharingInvitationAccepted  <br/> |用户 （成员或来宾） 接受共享邀请并授予对资源的访问。此事件包括有关受邀用户和用于接受邀请的电子邮件地址的信息 （它们可能会不同）。介绍如何用户授予访问资源，例如，将用户添加到有权访问该资源组的第二个事件通常会附带此活动。  <br/> |
|添加了的权限级别设置为网站集  <br/> |PermissionLevelAdded  <br/> |权限级别已添加到网站集。  <br/> |
|用户添加到安全链接  <br/> |AddedToSecureLink  <br/> |用户已添加到可以使用此安全共享链接的实体列表。  <br/> |
|阻止共享邀请  <br/> |SharingInvitationBlocked  <br/> | 由于允许或拒绝外部共享基于目标用户的域的外部共享策略，由您组织内的用户发送共享邀请而被阻止。在这种情况下，共享邀请已阻止因为：<br/>  目标用户的域不包含在允许的域的列表。  <br/>  或者  <br/>  目标用户的域将包含在列表中被阻止的域。  <br/>  有关允许或阻止外部共享基于域的详细信息，请参阅[SharePoint Online 和 OneDrive for Business 中共享的受限的域](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9)。  <br/> |
|中断权限级别继承  <br/> |PermissionLevelsInheritanceBroken  <br/> |项目已更改，以便它不再从其父网站继承权限级别。  <br/> |
|中断共享继承  <br/> |SharingInheritanceBroken  <br/> |项目已更改，以便它不再从其父级继承共享的权限。  <br/> |
|创建公司可共享链接  <br/> |CompanyLinkCreated  <br/> |用户创建的资源的公司范围内链接。公司范围内链接仅可由组织中的成员。他们无法使用来宾。  <br/> |
|创建访问请求  <br/> |AccessRequestCreated  <br/> |用户请求访问它们没有访问权限的网站、 文件夹或文档。  <br/> |
|创建一个匿名的链接  <br/> |AnonymousLinkCreated  <br/> |创建对某资源的匿名链接的用户。与此链接的任何人都可以访问的资源，而无需进行身份验证。  <br/> |
|创建安全链接  <br/> |SecureLinkCreated  <br/> |为此项已创建共享的安全链接。  <br/> |
|创建共享邀请  <br/> |SharingInvitationCreated  <br/> |用户不在贵组织的目录中的用户与共享中 SharePoint Online 或 OneDrive for Business 的资源。  <br/> |
|已删除的安全链接  <br/> |SecureLinkDeleted  <br/> |共享的安全链接已删除。  <br/> |
|拒绝访问请求  <br/> |AccessRequestDenied  <br/> |为网站、 文件夹或文档的访问请求被拒绝。  <br/> |
|网站集上的修改的权限级别  <br/> |PermissionLevelModified  <br/> |在网站集上更改了权限级别。  <br/> |
|删除公司可共享链接  <br/> |CompanyLinkRemoved  <br/> |删除用户的资源的公司范围内链接。链接不再可用来访问资源。  <br/> |
|删除匿名链接  <br/> |AnonymousLinkRemoved  <br/> |对某资源的匿名链接删除用户。链接不再可用来访问资源。  <br/> |
|从网站集合中删除权限级别  <br/> |PermissionLevelRemoved  <br/> |从网站集已删除的权限级别。  <br/> |
|还原共享继承  <br/> |SharingInheritanceReset  <br/> |已更改，以便项目继承其父共享的权限。  <br/> |
|共享的文件、 文件夹或网站  <br/> |SharingSet  <br/> |用户 （成员或来宾） 与贵组织的目录中的用户共享文件、 文件夹或 SharePoint 或 OneDrive for Business 中的网站。此活动的**详细信息**列中的值标识与共享资源的用户和该用户是否成员或来宾的名称。此活动通常会附带介绍用户如何授予访问资源; 第二个事件例如，将用户添加到有权访问该资源的组。<br/> |
|更新的访问请求  <br/> |AccessRequestUpdated  <br/> |已更新到项目的访问请求。  <br/> |
|更新的匿名链接  <br/> |AnonymousLinkUpdated  <br/> |更新用户的匿名链接到一个资源。导出搜索结果时，将 EventData 属性中包含更新域。  <br/> |
|更新的共享邀请  <br/> |SharingInvitationUpdated  <br/> |外部共享邀请已进行了更新。  <br/> |
|使用匿名链接  <br/> |AnonymousLinkUsed  <br/> |匿名用户通过使用匿名链接访问资源。用户的标识可能有未知，但您可以获取其他详细信息，例如用户的 IP 地址。  <br/> |
|取消共享的文件、 文件夹或网站  <br/> |SharingRevoked  <br/> |（成员或来宾） 的用户不共享文件、 文件夹或以前与其他用户共享的网站。  <br/> |
|使用公司可共享链接  <br/> |CompanyLinkUsed  <br/> |用户通过使用公司范围内链接访问资源。  <br/> |
|使用安全链接  <br/> |SecureLinkUsed  <br/> |用户使用的安全链接。  <br/> |
|用户添加到安全链接  <br/> |AddedToSecureLink  <br/> |用户已添加到可以使用的安全共享链接的实体列表。  <br/> |
|从安全链接中移除用户  <br/> |RemovedFromSecureLink  <br/> |可以使用的安全共享链接的实体的列表中删除用户。  <br/> |
|Withdrew 共享邀请  <br/> |SharingInvitationRevoked  <br/> |用户 withdrew 资源共享邀请。  <br/> |
  
### <a name="synchronization-activities"></a>同步活动
  
下表列出了 SharePoint Online 和 OneDrive for Business 中的文件同步活动。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|允许对同步文件的计算机  <br/> |ManagedSyncClientAllowed  <br/> |用户成功建立与网站的同步关系。同步关系是成功，因为用户的计算机是域已添加到可以访问您的组织中的文档库的域 （称为*安全收件人列表*） 的列表的成员。<br/> 有关此功能的详细信息，请参阅[Use Windows PowerShell cmdlet 来启用的域安全收件人列表所 OneDrive 同步](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|阻止从同步文件的计算机  <br/> |UnmanagedSyncClientBlocked  <br/> |用户尝试建立与对网站进行的不是您组织的域的成员计算机同步关系或尚未添加到域的列表的域的成员 (称为*安全收件人列表)* ，可以访问文档您的组织中的库。不允许同步关系，并在用户计算机阻止同步、 下载或上载的文档库上的文件。<br/> 有关此功能的信息，请参阅[Use Windows PowerShell cmdlet 来启用的域安全收件人列表所 OneDrive 同步](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|下载的文件复制到计算机  <br/> |FileSyncDownloadedFull  <br/> |用户建立同步关系和成功下载文件的第一次到其计算机从文档库。  <br/> |
|对计算机下载的文件更改  <br/> |FileSyncDownloadedPartial  <br/> |用户成功下载的任何更改为文件从文档库。此活动指示对文档库中的文件所做的任何更改已下载到用户的计算机上。仅更改已下载，因为用户 （如由**下载文件复制到计算机**活动） 已先前下载的文档库。<br/> |
|上载到文档库的文件  <br/> |FileSyncUploadedFull  <br/> |用户建立同步关系，并成功将文件上载到文档库首次从其计算机。  <br/> |
|上载的文件更改到文档库  <br/> |FileSyncUploadedPartial  <br/> |用户成功将更改上载到文档库上的文件。此事件表示从文档库对文件的本地版本所做任何更改都成功上载到文档库。仅更改是卸载，因为这些文件之前已上载的用户 (由 * * 文件上载到文档库 * * 活动)。  <br/> |
  
### <a name="site-administration-activities"></a>网站管理活动
  
下表列出了从 SharePoint Online 中的网站管理任务结果的事件。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加免除用户代理  <br/> |ExemptUserAgentSet  <br/> |SharePoint 或全局管理员向 SharePoint 管理中心中的免除用户代理的列表中添加一个用户代理。  <br/> |
|添加的网站集管理员  <br/> |SiteCollectionAdminAdded  <br/> |网站集管理员或所有者将用户添加为网站的网站集管理员。网站集管理员具有完全控制权限的网站集和所有子网站。管理员使自己访问用户的 OneDrive 帐户 （通过编辑 SharePoint 管理中心或[使用 Office 365 管理中心](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data#part-1---get-access-to-the-former-employees-onedrive-for-business-documents)中的用户配置文件） 时，也会记录此活动。<br/> |
|（无）  <br/> |SiteCollectionAdminRemoved <br/> |网站集管理员或所有者删除作为网站集管理员网站的人员。管理自己从列表中删除的网站集管理员的用户的 OneDrive 帐户 （通过编辑 SharePoint 管理中心中的用户配置文件） 时，也会记录此活动。 请注意，若要在审核日志搜索结果中返回此活动，您需要的所有活动搜索。 <br/> |
|添加的用户或组的 SharePoint 组  <br/> |AddedToGroup  <br/> |用户添加到 SharePoint 组的成员或来宾。这可能已有意操作或另一个活动，例如共享的事件的结果。  <br/> |
|允许用户创建组  <br/> |AllowGroupCreationSet  <br/> |网站管理员或所有者添加权限级别的网站的允许用户分配的权限创建该网站组。  <br/> |
|已取消的站点地理位置移动  <br/> |SiteGeoMoveCancelled  <br/> |SharePoint 或全局管理员成功取消 SharePoint 或 OneDrive 网站地理位置移动。多地理位置功能允许 Office 365 组织跨越多个 Office 365 数据中心地域，称为 geo。有关详细信息，请参阅[OneDrive 和 Office 365 中 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|更改共享策略  <br/> |SharingPolicyChanged  <br/> |SharePoint 或全局管理员更改 SharePoint 共享策略，通过使用 Office 365 管理门户、 SharePoint 管理门户或 SharePoint Online Management Shell。将记录对您的组织中的共享策略中的设置的任何更改。在事件记录的详细属性的**ModifiedProperties**字段中标识已更改的策略。<br/> |
|更改设备访问策略  <br/> |DeviceAccessPolicyChanged  <br/> |SharePoint 或全局管理员更改您的组织的非托管的设备策略。此策略控制对 SharePoint、 OneDrive 和 Office 365 未加入您的组织的设备的访问。配置此策略需要企业移动 + 安全订阅。有关详细信息，请参阅[从非托管设备控制访问](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622)。<br/> |
|更改免除用户代理  <br/> |CustomizeExemptUsers  <br/> |SharePoint 或全局管理员自定义 SharePoint 管理中心中的免除用户代理的列表。您可以从接收到索引整个网页免除指定哪些用户代理。这意味着您已指定为免除遇到 InfoPath 表单用户代理时，窗体将返回为 XML 文件，而不是整个网页。这使索引的 InfoPath 表单的速度更快。  <br/> |
|更改网络访问策略  <br/> |NetworkAccessPolicyChanged  <br/> |SharePoint 或全局管理员更改在 SharePoint 管理中心或使用 SharePoint Online PowerShell 中的基于位置的访问策略 （也称为受信任的网络边界）。此类型的策略控制可以访问您的组织根据您指定的授权 IP 地址范围中的 SharePoint 和 OneDrive 资源。有关详细信息，请参阅[控制他人对 SharePoint Online 和 OneDrive 根据网络位置的数据访问](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f)。<br/> |
|已完成的站点地理位置移动  <br/> |SiteGeoMoveCompleted  <br/> |计划在组织中的全局管理员站点地理位置移动已成功完成。多地理位置功能允许 Office 365 组织跨越多个 Office 365 数据中心地域，称为 geo。有关详细信息，请参阅[OneDrive 和 Office 365 中 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|创建的组  <br/> |GroupAdded  <br/> |网站管理员或所有者创建一组网站，或执行任务的结果中要创建的组。例如，第一次用户创建一个链接，用于共享文件，将系统组添加到用户的 OneDrive for Business 站点。此事件也可以为用户创建与链接的结果编辑权限对共享文件。  <br/> |
|创建的发送到连接  <br/> |SendToConnectionAdded  <br/> |SharePoint 或全局管理员在 SharePoint 管理中心的记录管理页上创建新发送到连接。发送到连接指定的文档库或记录中心的设置。当创建发送到连接时，内容管理器可以提交到指定的位置的文档。  <br/> |
|创建的网站集  <br/> |SiteCollectionCreated  <br/> |SharePoint 或全局管理员在 SharePoint Online 组织中创建新的网站集，或者用户设置 OneDrive for Business 站点。  <br/> |
|删除的组  <br/> |GroupRemoved  <br/> |用户从网站中删除的组。  <br/> |
|已删除发送到连接  <br/> |SendToConnectionRemoved  <br/> |SharePoint 或全局管理员删除 SharePoint 管理中心中记录管理页上的发送到连接。  <br/> |
|已删除的网站  <br/> |SiteDeleted  <br/> |网站管理员删除网站。  <br/> |
|启用文档预览  <br/> |PreviewModeEnabledSet  <br/> |网站管理员启用文档预览的网站。  <br/> |
|启用旧的工作流  <br/> |LegacyWorkflowEnabledSet  <br/> |网站管理员或所有者将 SharePoint 2013 工作流任务内容类型添加到网站。全局管理员还可以在 SharePoint 管理中心中启用整个组织的工作流。  <br/> |
|已启用的 Office on Demand  <br/> |OfficeOnDemandSet  <br/> |网站管理员能够让 Office on Demand，使用户可以访问 Office 桌面应用程序的最新版本。Office on Demand 在 SharePoint 管理中心中启用，并且需要包括完全安装的 Office 应用程序的 Office 365 订阅。  <br/> |
|启用的 RSS 源  <br/> |NewsFeedEnabledSet  <br/> |网站管理员或所有者使网站的 RSS 源。全局管理员可以使 SharePoint 管理中心中的整个组织的 RSS 源。  <br/> |
|修改的访问请求设置  <br/> |WebRequestAccessModified  <br/> |在网站上已修改的访问请求设置。  <br/> |
|已修改的成员可以共享设置  <br/> |WebMembersCanShareModified  <br/> |在网站上进行了修改的**成员可以共享**设置。  <br/> |
|修改的网站权限  <br/> |SitePermissionsModified  <br/> |网站管理员或所有者 （或系统帐户） 更改分配给网站上的组的权限级别。如果从组中删除所有权限，也会记录此活动。<br/> > [!NOTE]此操作已被弃用 SharePoint Online 中的 >。要查找相关的事件，您可以搜索如**添加了网站集管理员**、**添加用户或组的 SharePoint 组**，**允许用户创建组**，**创建组**和**Deleted 其他权限相关的活动组。**         |
|从 SharePoint 组中删除用户或组  <br/> |RemovedFromGroup  <br/> |用户从 SharePoint 组中删除一个成员或来宾。这可能已有意操作或另一个活动，如取消事件的结果。  <br/> |
|重命名的网站  <br/> |SiteRenamed  <br/> |网站管理员或所有者重命名的网站  <br/> |
|请求的网站管理员权限  <br/> |SiteAdminChangeRequest  <br/> |若要添加为网站集的网站集管理员的用户请求。网站集管理员具有完全控制权限的网站集和所有子网站。  <br/> |
|计划的网站地理位置移动  <br/> |SiteGeoMoveScheduled  <br/> |SharePoint 或全局管理员成功安排 SharePoint 或 OneDrive 网站地理位置移动。多地理位置功能允许 Office 365 组织跨越多个 Office 365 数据中心地域，称为 geo。有关详细信息，请参阅[OneDrive 和 Office 365 中 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。<br/> |
|主机网站集  <br/> |HostSiteSet  <br/> |SharePoint 或全局管理员更改指定的网站以承载个人或 OneDrive 业务网站。  <br/> |
|更新的组  <br/> |GroupUpdated  <br/> |网站管理员或所有者更改网站的组的设置。这可能包括更改组的名称，用户可以查看或编辑组成员身份，并确定如何处理成员资格请求。  <br/> |
  
### <a name="exchange-mailbox-activities"></a>Exchange 邮箱活动
  
下表列出的活动，可以记录邮箱的审核日志记录。将记录邮箱所有者、 委派的用户或管理员执行的邮箱活动。默认情况下，Office 365 中的邮箱审核功能不被打开的。邮箱审核日志记录必须打开每个邮箱之前将记录邮箱活动。有关详细信息，请参阅[启用邮箱审核 Office 365 中](https://go.microsoft.com/fwlink/p/?LinkID=626109)。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加的代理邮箱权限  <br/> |添加 MailboxPermission  <br/> |管理员分配给其他人的邮箱的 FullAccess 邮箱权限为用户 （称为代理）。FullAccess 权限允许代理打开其他人的邮箱，并阅读和管理邮箱的内容。  <br/> |
|复制到另一个文件夹的邮件  <br/> |Copy  <br/> |已将某个邮件复制到另一个文件夹。  <br/> |
|创建的邮箱项目  <br/> |Create  <br/> |邮箱; 中的日历、 联系人、 备注或任务文件夹中创建项目例如，创建一个新的会议请求。请注意，不审核创建、 发送或接收邮件。此外，不审核创建邮箱文件夹。  <br/> |
|删除已删除邮件文件夹的邮件  <br/> |SoftDelete  <br/> |邮件被永久删除或从已删除邮件文件夹中删除。这些项目将移动到可恢复邮件文件夹中。当用户选择它，并按**Shift + Delete**，邮件还会移动到可恢复邮件文件夹。<br/> |
|将邮件移到另一个文件夹  <br/> |Move  <br/> |已将某个邮件移至另一个文件夹。  <br/> |
|移动到已删除邮件文件夹的邮件  <br/> |MoveToDeletedItems  <br/> |已将某个邮件删除并移至“已删除邮件”文件夹。  <br/> |
|已修改的文件夹权限  <br/> |UpdateFolderPermissions  <br/> |文件夹的权限已更改。您的组织中哪些用户可以访问邮箱文件夹和文件夹中的邮件文件夹权限控制。  <br/> |
|从邮箱的已清除的邮件  <br/> |HardDelete  <br/> |消息被清除从 （永久从邮箱中删除） 可恢复邮件文件夹中。  <br/> |
|删除的代理邮箱权限  <br/> |Remove-mailboxpermission  <br/> |管理员已删除一个人的邮箱的 FullAccess 权限 （且已分配给代理人）。删除的 FullAccess 权限后，代理无法打开其他人的邮箱或访问其任何内容。  <br/> |
|发送邮件使用 Send As 权限  <br/> |SendAs  <br/> |已使用 SendAs 权限发送某个邮件。这表示另一个用户发送了邮件，而该邮件就好像来自于邮箱所有者。  <br/> |
|发送邮件使用代表发送权限  <br/> |SendOnBehalf  <br/> |已使用 SendOnBehalf 权限发送某个邮件。这表示另一个用户代表邮箱所有者发送了邮件。此邮件向收件人表明，此邮件是代表谁发送的以及实际发送此邮件的是谁。  <br/> |
|更新的代理访问权限日历文件夹  <br/> |UpdateCalendarDelegation  <br/> |日历委派已分配给某个邮箱。日历委派提供相同的组织权限，以管理邮箱所有者的日历中的其他人。  <br/> |
|更新的消息  <br/> |Update  <br/> |已更改某个邮件或其属性。  <br/> |
|登录到邮箱的用户  <br/> |MailboxLogin  <br/> |用户登录其邮箱。  <br/> |
|（无）  <br/> |UpdateInboxRules  <br/> |已添加、 删除或更改收件箱规则。收件箱规则用于处理基于指定条件的用户的收件箱中的邮件，并执行操作，达到规则的条件时，例如将邮件移到指定的文件夹或删除一条消息。<br/> 若要返回的收件箱规则操作的条目，您必须在**活动**列表中选择**显示所有活动的结果**。使用日期范围框和**用户**列表来缩小搜索结果。<br/> |
  
### <a name="sway-activities"></a>Sway 活动
  
下表列出了 Sway 中的用户和管理活动。Sway 是 Office 365 应用程序，可帮助用户收集、 格式，并共享想法、 情景和交互式、 基于 web 的画布上的演示文稿。有关详细信息，请参阅[有关 Sway-管理帮助的常见问题](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075)。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|更改的 Sway 共享级别  <br/> |SwayChangeShareLevel  <br/> |在用户更改 Sway 共享级别。此事件可捕获用户更改共享 Sway; 相关联的范围例如，公共与组织内部。  <br/> |
|创建的 Sway  <br/> |SwayCreate  <br/> |用户创建 Sway。  <br/> |
|已删除的 Sway  <br/> |SwayDelete  <br/> |用户删除 Sway。  <br/> |
|禁用的 Sway 重复  <br/> |SwayDisableDuplication  <br/> |用户禁用 Sway 的重复。  <br/> |
|重复的 Sway  <br/> |SwayDuplicate  <br/> |用户重复 Sway。  <br/> |
|编辑的 Sway  <br/> |SwayEdit  <br/> |用户编辑 Sway。  <br/> |
|启用的 Sway 重复  <br/> |EnableDuplication  <br/> |用户允许重复的 Sway;默认情况下启用为用户启用的 Sway 重复的功能。  <br/> |
|已吊销 Sway 共享  <br/> |SwayRevokeShare  <br/> |用户停止共享 Sway 撤消对其进行访问。撤消访问更改 Sway 相关联的链接。  <br/> |
|共享的 Sway  <br/> |SwayShare  <br/> |用户想要共享 Sway。此事件可捕获单击 Sway 共享菜单中的特定共享目标的用户的操作。该事件不会指示用户是否已完成的共享操作。  <br/> |
|关闭 Sway 外部共享  <br/> |SwayExternalSharingOff  <br/> |管理员禁用外部 Sway 共享整个组织使用 Office 365 管理中心。  <br/> |
|开启 Sway 外部共享  <br/> |SwayExternalSharingOn  <br/> |管理员启用外部 Sway 共享整个组织使用 Office 365 管理中心。  <br/> |
|关闭 Sway 服务  <br/> |SwayServiceOff  <br/> |管理员通过使用 Office 365 管理中心，为整个组织中禁用 Sway。  <br/> |
|开启 Sway 服务  <br/> |SwayServiceOn  <br/> |管理员使用 Office 365 管理中心内 (默认情况下启用服务 Sway) 整个组织启用 Sway。  <br/> |
|查看的 Sway  <br/> |SwayView  <br/> |用户可查看 Sway。  <br/> |

  
### <a name="user-administration-activities"></a>用户管理活动
  
下表列出了管理员添加或更改通过使用 Office 365 管理中心或 Azure 管理门户的用户帐户时都会被记录的用户管理活动。
  
|**活动**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加的用户  <br/> |添加用户  <br/> |创建 Office 365 用户帐户。  <br/> |
|已更改的用户许可证  <br/> |更改用户许可证  <br/> |许可证分配给用户更改内容。若要查看哪些许可证已更改，请参阅的相应**更新了用户**活动。<br/> |
|更改的用户密码  <br/> |更改用户密码  <br/> |管理员更改密码的用户的密码。  <br/> |
|已删除的用户  <br/> |Delete user  <br/> |Office 365 用户帐户已被删除。  <br/> |
|重置用户密码  <br/> |重置用户密码  <br/> |管理员重置用户的密码。  <br/> |
|设置强制用户更改密码的属性  <br/> |设置强制更改用户密码  <br/> |管理员设置强制用户更改其密码下一次用户登录到 Office 365 的属性。  <br/> |
|设置许可证属性  <br/> |设置许可证属性  <br/> |管理员修改许可分配给用户的属性。  <br/> |
|更新的用户  <br/> |更新用户  <br/> |管理员将更改的用户帐户的一个或多个属性。有关可更新的用户属性的列表，请参阅在[Azure Active Directory 审核报表事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)中的"更新用户属性"部分。<br/> |
  
### <a name="azure-ad-group-administration-activities"></a>Azure AD 组管理活动
  
下表列出了管理员或用户创建或更改 Office 365 组时或管理员通过使用 Office 365 管理中心或 Azure 管理门户中创建安全组时记录的组管理活动。有关 Office 365 中的组的详细信息，请参阅[查看、 创建和删除 Office 365 管理中心中的组](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7)。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加的组  <br/> |添加组  <br/> |已创建的组。  <br/> |
|向组添加的成员  <br/> |将成员添加到组  <br/> |已将成员添加到组中。  <br/> |
|删除的组  <br/> |删除组  <br/> |已删除的组。  <br/> |
|从组删除的成员  <br/> |从组中删除成员  <br/> |已从组中删除成员。  <br/> |
|更新的组  <br/> |更新组  <br/> |已更改的一组属性。  <br/> |
   
### <a name="application-administration-activities"></a>应用程序管理活动
  
下表列出了管理员添加或更改的 Azure AD 中注册应用程序时都会被记录的应用程序管理活动。必须在目录中注册依赖 Azure AD 身份验证的任何应用程序。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加了的委派条目  <br/> |添加委派条目  <br/> |身份验证权限已创建/授予 Azure AD 中的应用程序。  <br/> |
|添加了的服务主体  <br/> |添加服务主体  <br/> |Azure AD 中注册应用程序。由在目录中的服务主体表示应用程序。  <br/> |
|添加了的服务主体凭据  <br/> |添加服务主体凭据  <br/> |凭据已添加到服务主体中 Azure AD。服务原则表示的目录中的应用程序。  <br/> |
|删除的委派条目  <br/> |删除委派条目  <br/> |从 Azure AD 中的应用程序中移除了身份验证权限。  <br/> |
|从目录中删除的服务主体  <br/> |删除服务主体  <br/> |应用程序已从 Azure AD 中删除/注销。由在目录中的服务主体表示应用程序。  <br/> |
|从服务主体的已删除的凭据  <br/> |删除服务主体凭据  <br/> |从服务主体 Azure AD 中移除了凭据。服务原则表示的目录中的应用程序。  <br/> |
|设置委派条目  <br/> |设置委派条目  <br/> |身份验证的权限已更新的 Azure AD 中的应用程序。  <br/> |

### <a name="role-administration-activities"></a>角色管理活动
  
下表列出了管理员管理管理员角色或 Azure 管理门户中 Office 365 管理中心时都会被记录的 Azure AD 角色管理活动。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|将成员添加到角色  <br/> |将角色成员添加到角色  <br/> |将某个用户添加到 Office 365 管理员角色。  <br/> |
|从目录角色中删除用户  <br/> |从角色中移除角色成员  <br/> |Office 365 中删除用户从管理员角色。  <br/> |
|设置公司联系人信息  <br/> |设置公司联系人信息  <br/> |更新 Office 365 组织的公司级别联系人首选项。这包括订阅相关的电子邮件发送的 Office 365，以及有关 Office 365 服务的技术通知的电子邮件地址。  <br/> |
   
### <a name="directory-administration-activities"></a>目录管理活动
  
下表列出 Azure AD 目录和域相关的管理员可以管理其 Office 365 组织或 Azure 管理门户中 Office 365 管理中心时都会被记录的活动。
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加到公司的域  <br/> |将域添加到公司  <br/> |添加到 Office 365 组织的域。  <br/> |
|合作伙伴添加到目录  <br/> |将伙伴添加到公司  <br/> |添加到 Office 365 组织的合作伙伴 （委派管理员）。  <br/> |
|删除从公司的域  <br/> |从公司中删除域  <br/> |从 Office 365 组织中删除域。  <br/> |
|从目录中删除合作伙伴  <br/> |删除公司合作伙伴  <br/> |从 Office 365 组织中删除的合作伙伴 （委派管理员）。  <br/> |
|设置公司信息  <br/> |设置公司信息  <br/> |更新 Office 365 组织的公司信息。这包括订阅相关的电子邮件发送的 Office 365，以及有关 Office 365 服务的技术通知的电子邮件地址。  <br/> |
|设置域身份验证  <br/> |设置域身份验证  <br/> |更改您的 Office 365 组织的域身份验证设置。  <br/> |
|更新域的联合身份验证设置  <br/> |设置域上的联合身份验证  <br/> |更改您的 Office 365 组织的联合身份验证 （外部共享） 设置。  <br/> |
|设置密码策略  <br/> |设置密码策略  <br/> |更改您的 Office 365 组织中的用户密码的长度和字符约束。  <br/> |
|开启 Azure AD 同步  <br/> |对公司设置 DirSyncEnabled 标志  <br/> |设置为 Azure AD 同步启用目录的属性。  <br/> |
|更新后的域  <br/> |更新域  <br/> |更新 Office 365 组织中域的设置。  <br/> |
|已验证的域  <br/> |验证域  <br/> |验证您的组织是域的所有者。  <br/> |
|验证电子邮件已验证的域  <br/> |验证电子邮件已验证的域  <br/> |使用电子邮件验证来验证您的组织是域的所有者。  <br/> |
   
### <a name="ediscovery-activities"></a>电子数据展示活动
  
内容搜索和 Office 365 安全性执行的电子数据展示相关的活动&amp;合规性中心或通过运行相应的 Windows PowerShell cmdlet 会在 Office 365 的审核日志记录。这包括以下活动：
  
- 创建和管理电子数据展示事例
    
- 创建、 启动和编辑内容搜索
    
- 执行内容搜索操作，如预览，导出，并删除搜索结果
    
- 配置内容搜索筛选的权限
    
- 管理电子数据展示管理员角色
    
列表和记录的电子数据展示活动的详细的说明，请参阅[Office 365 中的电子数据展示活动搜索审核日志](search-for-ediscovery-activities-in-the-audit-log.md)。
  
> [!NOTE]
> 计最多 30 分钟的事件的结果从列在**活动**下拉列表将显示在搜索结果中的**电子数据展示活动**下的活动。相反，它采用达 24 小时的相应发生的事件的电子数据展示 cmdlet 活动显示在搜索结果中。 
  
### <a name="power-bi-activities"></a>Power BI 活动
  
Power BI 中，您可以搜索活动的审核日志。有关 Power BI 活动的信息，请参阅中[使用审核贵组织中](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi)的"活动审核电源 Power BI"一节。
  
请注意，不默认启用审核日志记录的 Power BI。若要搜索的 Office 365 审核日志中的 Power BI 活动，您必须在 Power BI 管理门户中启用审核。有关说明，请参阅[Power BI 管理门户](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)中的"审核日志"一节。
  
### <a name="microsoft-teams-activities"></a>Microsoft 团队活动
  
下表列出用户和管理员在登录 Office 365 的 Microsoft 团队中的活动审核日志。Microsoft 团队是 Office 365 中的聊天居中工作区。汇集团队对话、 会议、 文件和 notes 到一个位置。有关详细信息和链接的帮助主题，请参阅：
  
- [有关常见问题的 Microsoft 团队-管理帮助](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Microsoft 团队帮助](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|添加了自动程序给团队  <br/> |BotAddedToTeam  <br/> |用户将自动程序添加到团队。  <br/> |
|添加了的通道  <br/> |ChannelAdded  <br/> |用户将添加到团队的通道。  <br/> |
|添加了的连接器  <br/> |ConnectorAdded  <br/> |用户将连接符添加到通道。  <br/> |
|添加到团队的成员  <br/> |MemberAdded  <br/> |工作组负责人向团队的成员。  <br/> |
|添加的选项卡  <br/> |TabAdded  <br/> |用户向通道添加一个 tab。  <br/> |
|更改通道设置  <br/> |ChannelSettingChanged  <br/> | 当团队成员执行以下活动时，将记录 ChannelSettingChanged 操作。对于每个这些活动，将审核日志搜索结果中的**项目**列中显示设置已更改 （如括号下面所示） 的说明。<br/> <br/>-更改团队通道 （**通道名称**） 的名称。  <br/>  <br/>-更改团队通道 （**通道说明**） 的说明。  <br/> |
|更改组织设置  <br/> |TeamsTenantSettingChanged  <br/> | （使用 Office 365 管理中心）; 是全局管理员通过执行以下活动时，将记录 TeamsTenantSettingChanged 操作请注意，这些活动影响组织范围内的 Microsoft 团队设置。有关详细信息，请参阅[Microsoft 团队的管理员设置](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2)。<br/>  对于每个这些活动，将审核日志搜索结果中的**项目**列中显示设置已更改 （如括号下面所示） 的说明。  <br/><br/>-启用或禁用组织 （ **Microsoft 团队**） 的 Microsoft 团队。  <br/><br/>-启用或禁用 Microsoft 团队之间 for Business 的 Skype 的互操作性组织 ( **Skype 的业务互操作性**)。<br/><br/>-启用或禁用 Microsoft 团队客户端 （**组织图表视图**） 中的组织结构图视图。  <br/><br/>-启用或禁用团队成员安排专用会议 （**专用会议安排**） 的功能。  <br/><br/>-启用或禁用团队成员安排通道会议 （**通道会议安排**） 的功能。  <br/><br/>-启用或禁用视频中的呼叫的团队 （ **Skype 会议视频**） 会议。  <br/><br/>-启用或禁用组织 （**屏幕共享 Skype 会议**） 的 Microsoft 团队 meetups 中共享的屏幕。  <br/><br/>-启用或禁用该功能添加动画效果的图像 （称为 Giphys） 到团队的对话 （**动态图像**）。  <br/><br/>-更改分级组织 （**内容评级**） 设置的内容。内容的分级限制可以显示对话中的动画图像的类型。<br/><br/>-启用或禁用从 Internet 到团队的对话 （**来自 Internet 的可自定义图像**） 的工作组成员添加可自定义图像 （称为自定义 memes） 的功能。  <br/><br/>-启用或禁用到团队的对话 （**可编辑的图像**） 的工作组成员添加可编辑的图像 （称为标签） 的功能。<br/><br/>-启用或禁用工作组成员使用自动程序的 Microsoft 团队聊天和通道 (**组织范围内自动程序**) 中的功能。<br/><br/>-启用特定 bot Microsoft 团队;这不包括 T Bot 中，这是组织 (**单个 bot**) 启用自动程序时，可团队帮助 bot。  <br/><br/>-启用或禁用工作组成员添加扩展或选项卡 （**扩展或选项卡**） 的功能。  <br/><br/>-启用或禁用 Microsoft 团队 （**端加载自动程序**） 的专有 Bot 端加载。  <br/><br/>-启用或禁用用户向 (**通道电子邮件**) 的 Microsoft 团队通道发送电子邮件的功能。  <br/> |
|更改的团队中的成员角色  <br/> |MemberRoleChanged  <br/> |团队所有者更改团队中的成员的角色。下列值指示分配给用户的角色类型。<br/><br/><br/> **1** -指示所有者角色。<br/>**2** -指示成员角色。 <br/>**3** -指示的来宾角色。 <br/>Members 属性还包括您的组织和成员的电子邮件地址的名称。  <br/> |
|更改团队设置  <br/> |TeamSettingChanged  <br/> | 当团队所有者执行以下活动时，将记录 TeamSettingChanged 操作。对于每个这些活动，将审核日志搜索结果中的**项目**列中显示设置已更改 （如括号下面所示） 的说明。<br/><br/>-更改为团队的访问类型。团队可以设置为私有或公共 （**团队访问类型**）。当团队是专用 （默认设置），用户可以访问团队只能由邀请。公共团队，时，可发现的任何人。<br/><br/>-更改信息分类实现的工作组 （**团队分类**）。  <br/>  例如，团队数据可归为高业务影响、 中型企业影响或较低的业务影响。<br/><br/>-更改团队 （**工作组名称**） 的名称。  <br/><br/>-更改团队说明 （**团队说明**）。 <br/><br/>-对任何团队设置所做的更改。团队所有者可以通过右键单击团队，单击**管理团队**，然后单击**设置**选项卡访问团队客户端中的这些设置。对于这些活动，审核日志搜索结果中**项目**列中均显示已更改的设置的名称。<br/> |
|创建的团队  <br/> |TeamCreated  <br/> |用户创建新的团队。  <br/> |
|已删除的通道  <br/> |ChannelDeleted  <br/> |用户从团队删除通道。  <br/> |
|已删除的团队  <br/> |TeamDeleted  <br/> |团队所有者删除工作组。  <br/> |
|删除自动程序来自团队  <br/> |BotRemovedFromTeam  <br/> |用户从团队删除自动程序。  <br/> |
|已删除的连接器  <br/> |ConnectorRemoved  <br/> |用户从渠道删除连接器。  <br/> |
|来自团队的已删除的成员  <br/> |MemberRemoved  <br/> |团队所有者删除团队的成员。  <br/> |
|已删除的选项卡  <br/> |TabRemoved  <br/> |用户删除通道选项卡。  <br/> |
|更新了的连接器  <br/> |ConnectorUpdated  <br/> |用户修改通道中的连接器。  <br/> |
|更新选项卡  <br/> |TabUpdated  <br/> |用户修改通道中的一个选项卡。  <br/> |
|用户登录到团队  <br/> |TeamsSessionStarted  <br/> |一个用户登录到 Microsoft 团队客户端。  <br/> |

### <a name="yammer-activities"></a>Yammer 活动
  
下表列出了用户并在 Yammer 中的登录 Office 365 管理活动，审核日志。若要返回与 Yammer 相关的活动，从 Office 365 审核日志，您必须在**活动**列表中选择**显示所有活动的结果**。使用日期范围框和**用户**列表来缩小搜索结果。 
  
|**易记名称**|**Operation**|**说明**|
|:-----|:-----|:-----|
|更改的数据保留策略  <br/> |SoftDeleteSettingsUpdated  <br/> |验证的管理员更新到硬盘驱动器中删除或软删除网络数据保留策略的设置。仅验证的管理员才能执行此操作。  <br/> |
|已更改的网络配置  <br/> |NetworkConfigurationUpdated  <br/> |网络或已验证的管理员来更改的 Yammer 网络配置。这包括设置导出数据和启用聊天的时间间隔。  <br/> |
|已更改的网络配置文件设置  <br/> |ProcessProfileFields  <br/> |网络或已验证的管理员更改网络用户网络成员配置文件中显示的信息。  <br/> |
|更改内容的专用模式  <br/> |SupervisorAdminToggled  <br/> |验证的管理员启用或禁用的*私有内容模式*。管理视图中专用组和视图私信单个用户 （或用户组） 之间投递此模式使可以。仅验证的管理员只执行此操作。<br/> |
|已更改的安全配置  <br/> |NetworkSecurityConfigurationUpdated  <br/> |验证的管理更新的 Yammer 网络安全配置。这包括设置密码到期策略和 IP 地址上的限制。仅验证的管理员才能执行此操作。  <br/> |
|创建的文件  <br/> |FileCreated  <br/> |用户上载文件。  <br/> |
|创建的组  <br/> |GroupCreation  <br/> |用户创建新的组。  <br/> |
|删除的组  <br/> |GroupDeletion  <br/> |从 Yammer 中删除组。  <br/> |
|已删除的邮件  <br/> |MessageDeleted  <br/> |用户删除一条消息。  <br/> |
|下载的文件  <br/> |FileDownloaded  <br/> |用户下载文件。  <br/> |
|导出的数据  <br/> |数据导出  <br/> |验证的管理员导出 Yammer 网络数据。仅验证的管理员才能执行此操作。  <br/> |
|共享的文件  <br/> |FileShared  <br/> |用户与其他用户共享文件。  <br/> |
|挂起的网络用户  <br/> |NetworkUserSuspended  <br/> |网络或已验证的管理员挂起 （停用） Yammer 用户。  <br/> |
|挂起的用户  <br/> |UserSuspension  <br/> |挂起用户帐户 （停用）。  <br/> |
|更新的文件说明  <br/> |FileUpdateDescription  <br/> |用户更改文件的说明。  <br/> |
|更新的文件名称  <br/> |FileUpdateName  <br/> |在用户更改文件的名称。  <br/> |
|查看的文件  <br/> |FileVisited  <br/> |用户可查看文件。  <br/> |
   
### <a name="microsoft-flow"></a>Microsoft Flow

Microsoft 流中，您可以搜索活动的审核日志。这些活动包括创建、 编辑和删除流和更改流权限。有关审核流活动的信息，请参阅博客[Microsoft 流审核事件目前在合规中心的 Office 365 安全性 & 中可用](https://flow.microsoft.com/blog/security-and-compliance-center)。


### <a name="microsoft-stream"></a>Microsoft Stream
  
您可以在 Microsoft 流中搜索活动的审核日志。这些活动包括由用户、 组频道活动和管理活动，如管理用户、 管理组织设置和导出报告执行的视频活动。有关这些活动的说明，请参阅[Microsoft 流中的审核日志](https://docs.microsoft.com/stream/audit-logs)中的"在 Microsoft 流中记录活动"一节。
  
### <a name="exchange-admin-audit-log"></a>Exchange 管理员审核日志
  
Exchange 管理员审核日志记录 — 其 Office 365 中的默认情况下启用 — 管理员 （或已分配有管理权限的用户） 与 Exchange Online 组织中进行更改时，Office 365 审核日志中记录一个事件。Exchange 管理员审核日志记录使用 Exchange 管理中心或 Windows PowerShell 中运行 cmdlet 所做的更改。更多详细信息管理员审核日志记录在 Exchange，请参阅[管理员审核日志记录](https://go.microsoft.com/fwlink/p/?LinkID=619225)。
  
以下是一些用于搜索的 Exchange 管理员审核日志中的活动：
  
- 若要返回从 Exchange 管理员审核日志条目，您必须在**活动**列表中选择**显示所有活动的结果**。使用日期范围框和**用户**列表来缩小搜索结果由特定 Exchange 管理员在特定日期范围内运行的 cmdlet。 
    
- 若要显示 Exchange 管理员审核日志中的事件，筛选搜索结果以及类型**-**（划线） 在**活动**筛选框。这将显示 cmdlet 名称，Exchange 管理员事件的**活动**列中显示。然后您可以对 cmdlet 名称按字母顺序进行排序。 
    
    ![在活动框来筛选 Exchange 管理员事件中键入短划线](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- 若要获取有关哪些 cmdlet 运行、 已使用的参数和参数的值，以及哪些对象已受影响的信息，您将必须导出搜索结果，并选择**下载所有结果**选项。 
    
- 您还可以使用 Exchange 管理中心 Exchange 管理员审核日志中查看事件。有关说明，请参阅[查看管理员审核日志](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)。
  
## <a name="frequently-asked-questions"></a>常见问题

**在哪里可以找到有关 Office 365 中的审核服务提供的功能？**

有关 Office 365 中可用的审核和报告功能的详细信息，请参阅[审核和 Office 365 中的报告](office-365-auditing-and-reporting-overview.md)。 

**当前审核的不同 Office 365 服务有哪些？**

最常用的 Office 365 服务类似于 Exchange Online、 SharePoint、 OneDrive、 Azure Active Directory、 Microsoft 团队、 CRM、 高级威胁保护和数据丢失防护制约。请参阅本文的完整列表中的[简介](#search-the-audit-log-in-the-office-365-security-amp-compliance-center)一节。

**通过审核 Office 365 中的服务审核哪些操作？**

请参阅本文的列表和审核 Office 365 中的活动的说明中的[Audited 活动](#audited-activities)一节。

**长长时间的审核记录可事件之后发生？**

大多数审核数据可用在 30 分钟内但可能需要达 24 小时后事件发生相应的审核日志条目要显示在搜索结果中。请参阅本文表明花费的时间不同的 Office 365 服务中的事件的可[开始之前](#before-you-begin)部分中的表。

**多长时间的保留审核记录？**

如前所述，审核记录的保留期取决于组织的 Office 365 订阅。  

- **Office 365 E3** -审核记录保留 90 天。

- **Office 365 E5** -审核记录保留 for 365 天 （一年）。一年时间保留审核记录也是可供组织已 E3 订阅和 Office 365 高级合规性加载项订阅。

     > [!NOTE]
     > 如上文所述，E5 组织 （或高级合规性加载项许可证已 E3 公司） 的审核记录的一年保持期目前仅作为专用的预览计划的一部分。要在此预览计划中注册，请文件与[Microsoft 支持](https://docs.microsoft.com/en-us/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fcontact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online)的请求，并包括以下内容作为需要帮助的说明： 长期 Office 365 审核日志专用预览版。

另请注意，审核记录的保留时间段的持续时间基于每个用户授权。例如，如果您的组织中的用户分配一个 Office 365 E3 许可证，然后执行该用户的活动的审核记录保留 90 天。如果其他用户分配一个 Office 365 E5 许可证，其审核记录保留一年时间。 

**可以以编程方式访问的审计数据？**

是的。Office 365 管理活动 API 用于以编程方式获取审核日志。 若要开始，请参阅[开始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。

**是否有其他方法来获取审核日志，而不使用 Office 365 安全 & 合规性中心或 Office 365 管理活动 API？**

不。这些是从 Office 365 审核服务中获取数据的只有两个方法。 

**是否需要单独启用每个服务，我希望捕获审核日志中的审核功能？**

在大多数 Office 365 服务中，启用审核默认情况下您最初启用审核功能为您的 Office 365 组织 （如本文中的[开始之前](#before-you-begin)一节中所述） 后。但是，您必须启用邮箱审核您想要审核的每个邮箱的 Exchange Online。  我们正在启用邮箱审核默认情况下，Office 365 组织中的所有邮箱。有关详细信息，请参阅"Exchange 邮箱审核将默认情况下启用" [Microsoft 安全、 隐私和合规性博客 （英文）](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Exchange-Mailbox-Auditing-will-be-enabled-by-default/ba-p/215171)中。

**Office 365 审核服务支持消除重复的记录？**

不。审核服务管道是接近实时，，因此无法支持消除。
 
**Office 365 审核数据流经地理区域？**

不。我们当前具有审核 NA （北美洲）、 （欧洲、 中东和非洲） EMEA 和 APAC （亚太地区） 区域中的管道部署。但是，我们可能数据流经这些区域的负载平衡和仅在 live 网站问题。当我们执行执行这些操作时，在传输过程中的数据进行加密。   
 
**审核加密的数据？**

审核数据存储在其中部署审核管道同一区域中的 Exchange 邮箱 （静态数据）。此数据未加密。但是，始终加密在传输过程中的数据。 












