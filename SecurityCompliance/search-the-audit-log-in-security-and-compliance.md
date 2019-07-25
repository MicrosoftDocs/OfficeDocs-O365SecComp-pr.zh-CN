---
title: 在安全 & 合规性中心中搜索审核日志
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
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
description: '使用安全 & 合规中心搜索统一审核日志, 以查看 Office 365 组织中的用户和管理员活动。 '
ms.openlocfilehash: 5ba3659f8e6b004020b5270b62a40415e64ba96c
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854806"
---
# <a name="search-the-audit-log-in-the-security--compliance-center"></a>在安全 & 合规性中心中搜索审核日志

## <a name="introduction"></a>简介

需要查找用户是否查看了特定文档或清除了其邮箱中的项目？ 如果是这样, 您可以使用 Office 365 安全&amp;合规中心搜索统一审核日志, 以查看 Office 365 组织中的用户和管理员活动。 为什么要使用统一审核日志？ 由于您可以在 Office 365 中搜索以下类型的用户和管理员活动:
  
- SharePoint Online 和 OneDrive for business 中的用户活动
    
- Exchange Online 中的用户活动 (Exchange 邮箱审核日志记录)
  
- SharePoint Online 中的管理员活动
    
- Azure Active Directory 中的管理活动 (Office 365 的目录服务)
    
- Exchange Online 中的管理员活动 (Exchange 管理员审核日志记录)
    
- Sway 中的用户和管理员活动
    
- 安全与合规中心中的电子数据展示活动
    
- Power BI 中的用户和管理员活动
    
- Microsoft 团队中的用户和管理员活动

- Dynamics 365 中的用户和管理员活动
    
- Yammer 中的用户和管理员活动
 
- Microsoft Flow 中的用户和管理员活动
    
- Microsoft Stream 中的用户和管理员活动

- Microsoft 工作区分析中的分析师和管理员活动

- Microsoft PowerApps 中的用户和管理员活动
    
   
## <a name="before-you-begin"></a>开始之前

在开始搜索 Office 365 审核日志之前, 请务必阅读以下各项。
  
- 您 (或另一个管理员) 必须先启用审核日志记录, 然后才能开始搜索 Office 365 审核日志。 若要打开它, 请单击安全性 & 合规性中心中的 "**审核日志搜索**" 页上的 "**开始记录用户和管理员活动**"。 (如果看不到此链接, 表明已为您的组织启用了审核。)打开后, 会显示一条消息, 指出正在准备审核日志, 并且您可以在准备完成后的几小时内运行搜索。 您只需执行一次此操作。 
    
    > [!NOTE]
    > 默认情况下, 我们正在启用审核。 在此之前, 你可以按照前面所述将其打开。 
  
- 您必须在 Exchange Online 中向您分配 "仅查看审核日志" 或 "审核日志" 角色, 才能搜索 Office 365 审核日志。 默认情况下, 将这些角色分配给 Exchange 管理中心中 "**权限**" 页上的 "合规性管理" 和 "组织管理" 角色组。 注意: Office 365 和 Microsoft 365 中的全局管理员将自动添加为 Exchange Online 中的 "组织管理" 角色组的成员。 若要使用户能够使用最低级别的权限搜索 Office 365 审核日志, 您可以在 Exchange Online 中创建自定义角色组, 添加仅查看审核日志或审核日志角色, 然后将该用户添加为新角色组的成员。 有关详细信息, 请参阅[在 Exchange Online 中管理角色组](https://go.microsoft.com/fwlink/p/?LinkID=730688)。
    
    > [!IMPORTANT]
    > 如果在 Security & 合规性中心中向用户分配 "**权限**" 页上的 "仅查看" "审核日志" 或 "审核日志" 角色, 则他们将无法搜索 Office 365 审核日志。 您必须在 Exchange Online 中分配权限。 这是因为用于搜索审核日志的基础 cmdlet 是 Exchange Online cmdlet。 
  
- 当用户或管理员执行了审核的活动时, 将生成审核记录并将其存储在组织的 Office 365 审核日志中。 审核记录保留的时间长度 (并可在审核日志中搜索) 取决于您的 Office 365 订阅, 以及分配给特定用户的许可证类型。

     - **Office 365 E3:** 审核记录将保留90天。 这意味着, 您可以在审核日志中搜索在过去的90天内执行的活动。

     - **Office 365 E5:** 审核记录还会保留90天。 保留一年的审核记录可能最终适用于拥有 E3 许可证和 Office 365 高级合规性附加许可证的 E5 用户和用户。

        > [!NOTE]
        > 用于 E5 组织 (或具有高级合规性附加许可证的 E3 组织中的用户) 的审核记录的为期一年保留期的专用预览计划将关闭到新的注册。 此文章将在公开预览版中的一年保留期可用或发布以用于正式可用性时进行更新。

- 如果要关闭组织的 Office 365 中的审核日志搜索, 可以在连接到 Exchange Online 组织的远程 PowerShell 中运行以下命令:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
  ```

    若要再次启用审核搜索, 您可以在 Exchange Online PowerShell 中运行以下命令:
    
  ```
  Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
  ```

    有关详细信息, 请参阅[在 Office 365 中关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。
    
- 如前面所述, 用于搜索审核日志的基础 cmdlet 是**UnifiedAuditLog**的 Exchange Online cmdlet。 这意味着您可以使用此 cmdlet 搜索 Office 365 审核日志, 而不是使用安全 & 合规性中心中的 "**审核日志搜索**" 页。 您必须在连接到 Exchange Online 组织的远程 PowerShell 中运行此 cmdlet。 有关详细信息, 请参阅[UnifiedAuditLog](https://go.microsoft.com/fwlink/p/?linkid=834776)。 

    有关将**UnifiedAuditLog** cmdlet 返回的搜索结果导出到 CSV 文件中的信息, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)中的 "导出和查看审核日志的提示" 一节。  

- 如果要以编程方式从 Office 365 审核日志中下载数据, 我们建议使用 Office 365 管理活动 API, 而不是使用 PowerShell 脚本。 Office 365 管理活动 API 是 REST web 服务, 可用于为组织开发操作、安全性和合规性监视解决方案。 有关详细信息, 请参阅[Office 365 管理活动 API 参考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。
    
- 在事件发生后, 将在搜索结果中显示相应的审核日志条目, 最长可能需要30分钟或最长24小时。 下表显示了 Office 365 中的不同服务所需的时间。
    
    |**Office 365 服务**|**30 分钟**|**24 小时制**|
    |:-----|:-----|:-----|
    |高级威胁防护和威胁智能  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)| |
    |Azure Active Directory (用户登录事件)  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |Azure Active Directory (管理员事件)  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) |
    |数据丢失防护  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)       <br/>| |
    |Dynamics 365 CRM <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |电子数据展示  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Exchange Online  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Microsoft Flow  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Project  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Stream  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |Microsoft Teams  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Power BI  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/>| |
    |安全与合规中心  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |SharePoint Online 和 OneDrive for Business  <br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> ||
    |Sway  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
    |工作区分析<br/> |![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> || 
    |Yammer  <br/> ||![复选标记](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> |
   
- Azure Active Directory (Azure AD) 是 Office 365 的目录服务。 统一审核日志包含在 Microsoft 365 管理中心或在 Azure 管理门户中执行的用户、组、应用程序、域和目录活动。 有关 Azure AD 事件的完整列表, 请参阅[Azure Active Directory 审核报告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)。
    
- Power BI 的审核日志记录默认情况下不启用。 若要在 Office 365 审核日志中搜索 Power BI 活动, 您必须在 Power BI 管理门户中启用审核。 有关说明, 请参阅[POWER BI 管理门户](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)中的 "审核日志" 部分。
    
    
## <a name="search-the-audit-log"></a>搜索审核日志

以下是在 Office 365 中搜索审核日志的过程。
  
[步骤 1: 运行审核日志搜索](#step-1-run-an-audit-log-search)
  
[步骤 2: 查看搜索结果](#step-2-view-the-search-results)

[步骤 3: 筛选搜索结果](#step-3-filter-the-search-results)

[步骤 4: 将搜索结果导出到文件](#step-4-export-the-search-results-to-a-file)
  
### <a name="step-1-run-an-audit-log-search"></a>步骤 1: 运行审核日志搜索

1. 转到 [https://protection.office.com](https://protection.office.com)。
    
    > [!TIP]
    > 使用专用浏览会话 (而非常规会话) 访问安全 & 合规性中心, 因为这将阻止当前登录的凭据正在使用。 若要在 Internet Explorer 或 Microsoft Edge 中打开 InPrivate 浏览会话, 只需按 CTRL + SHIFT + P。 若要在 Google Chrome 中打开一个专用浏览会话 (称为 incognito 窗口), 请按 CTRL + SHIFT + N。 
  
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全性 & 合规性中心的左侧窗格中, 单击 "**搜索**", 然后单击 "**审核日志搜索**"。
    
    将显示 "**审核日志搜索**" 页。 
    
    ![配置条件, 然后单击 "搜索" 以运行报告](media/8639d09c-2843-44e4-8b4b-9f45974ff7f1.png)
  
    > [!NOTE]
    > 您必须先启用审核日志记录, 然后才能运行审核日志搜索。 如果显示 "**开始记录用户和管理员活动**" 链接, 请单击它以启用审核。 如果您看不到此链接, 表明已为您的组织启用了审核。 
  
4. 配置以下搜索条件:
    
    a. **活动**单击下拉列表以显示您可以搜索的活动。 用户和管理员活动组织到相关活动的组中。 您可以选择特定的活动, 也可以单击活动组名称以选择组中的所有活动。 您还可以单击所选活动以清除所选内容。 运行搜索后, 仅显示所选活动的审核日志条目。 选择 "**显示所有活动的结果**" 将显示所选用户或用户组执行的所有活动的结果。 
    
    100以上的用户和管理员活动记录在 Office 365 审核日志中。 单击本文主题中的 "已**审核的活动**" 选项卡, 查看每个不同的 Office 365 服务中的每个活动的说明。 
    
    b. 默认情况下, 将选择 "**开始日期**" 和 "**结束日期**" 最后七天。 选择要显示在该时间段内发生的事件的日期和时间范围。 日期和时间以协调通用时间 (UTC) 格式显示。 您可以指定的最大日期范围为90天。 如果所选日期范围大于90天, 则显示错误。 
    
    > [!TIP]
    > 如果使用的最大日期范围是90天, 请选择 "**开始日期**" 的当前时间。 否则, 您将收到一条错误消息, 指出开始日期早于结束日期。 如果您在最近90天内启用了审核, 则在启用审核的日期之前, 最大日期范围无法开始。 
  
    c. **用户**在此框中单击, 然后选择要为其显示搜索结果的一个或多个用户。 您在此框中选择的用户执行的选定活动的审核日志条目将显示在结果列表中。 将此框保留为空将返回组织中所有用户 (和服务帐户) 的条目。 
    
    d. **文件、文件夹或网站**键入文件或文件夹名称的部分或全部, 以搜索与包含指定关键字的文件夹文件相关的活动。 您还可以指定文件或文件夹的 URL。 如果使用 URL, 请确保键入完整的 URL 路径, 或者如果键入 URL 的一部分, 请勿包含任何特殊字符或空格。 
    
    将此框保留为空将返回组织中的所有文件和文件夹的条目。
    
   **几点**

   - 如果要查找与**网站**相关的所有活动, 请在 URL 后面添加通配符 (\*) 以返回该网站的所有条目;例如, **https://contoso-my.sharepoint.com/personal/"*"**。

   - 如果要查找与**文件**相关的所有活动, 请在文件名前面添加通配符 (\*) 以返回该文件的所有条目;例如, **"* Customer_Profitability_Sample"**。
    

    
5. 单击 "**搜索**" 以使用搜索条件运行搜索。 
    
    搜索结果将被加载, 并在几分钟后显示在 "**结果**" 下。 搜索完成后, 将显示找到的结果数。 在**结果**窗格中, 最多可显示5000个事件, 并增加150个事件。 如果超过5000个事件满足搜索条件, 则显示最新的5000事件。 
    
    ![搜索完成后显示的结果数](media/986216f1-ca2f-4747-9480-e232b5bf094c.png)
  
  
#### <a name="tips-for-searching-the-audit-log"></a>有关搜索审核日志的提示

- 您可以通过单击活动名称来选择要搜索的特定活动。 或者, 您可以通过单击组名称来搜索组中的所有活动 (如**文件和文件夹活动**)。 如果已选择活动, 则可以单击它以取消选择。 您还可以使用搜索框显示包含您键入的关键字的活动。
    
    ![单击 "活动组名称" 以选择所有活动](media/3cde97cb-6f35-47c0-8612-ecd9c6ac36a3.png)
  
- 您必须在 "**活动**" 列表中选择 "**显示所有活动的结果**" 以显示 Exchange 管理员审核日志中的事件。 此审核日志中的事件在结果的 "**活动**" 列中显示 cmdlet 名称 (例如, "**集-邮箱**")。 有关详细信息, 请单击本主题中的 "已**审核的活动**" 选项卡, 然后单击 " **Exchange 管理活动**"。
    
    同样, 有些审核活动在 "**活动**" 列表中没有对应的项。 如果您知道这些活动的操作的名称, 则可以搜索所有活动, 然后通过在 "**活动**" 列的框中键入操作的名称来筛选结果。 有关筛选结果的详细信息, 请参阅[第3步: 筛选搜索结果](#step-3-filter-the-search-results)。 
    
- 单击 "**清除**" 以清除当前搜索条件。 日期范围将恢复为最近七天的默认值。 您还可以单击 "全部**清除" 以显示所有活动的结果**, 以取消所有选定活动。 
    
- 如果找到了5000结果, 可能假设有超过5000个事件满足搜索条件。 您可以优化搜索条件, 然后重新运行搜索以返回较少的结果, 也可以通过选择 "**导出结果** \> " "**下载所有结果**" 来导出所有搜索结果。

  
### <a name="step-2-view-the-search-results"></a>步骤 2: 查看搜索结果

审核日志搜索的结果将显示在 "**审核日志搜索**" 页上的 "**结果**" 下。 如前所述, 最大值为 5000 (最新) 事件以150个事件为增量显示。 若要显示更多事件, 可以使用 "**结果**" 窗格中的滚动条, 也可以按**Shift + End**显示接下来的150事件。 
  
结果中包含有关搜索返回的每个事件的以下信息。
  
- **日期:** 事件发生时的日期和时间 (采用 UTC 格式)。 
    
- **IP 地址:** 记录活动时使用的设备的 IP 地址。 IP 地址显示为 IPv4 或 IPv6 地址格式。 
    
- **用户:** 执行触发事件的操作的用户 (或服务帐户)。 
    
- **活动:** 用户执行的活动。 此值与您在 "**活动**" 下拉列表中选择的活动相对应。 对于来自 Exchange 管理员审核日志的事件, 此列中的值为 Exchange cmdlet。 
    
- **项:** 作为对应活动的结果创建或修改的对象。 例如, 已查看或修改的文件或已更新的用户帐户。 此列中并非所有活动都具有值。 
    
- **详细信息:** 有关活动的其他信息。 同样, 并非所有活动都具有值。 
    
> [!TIP]
> 单击 "**结果**" 下的列标题以对结果进行排序。 您可以按从 A 到 Z 或从 Z 到 A 对结果进行排序。单击**日期**标头可将结果从 "最旧" 或 "降序" 更新为 "最旧"。 
  
#### <a name="view-the-details-for-a-specific-event"></a>查看特定事件的详细信息

您可以通过单击搜索结果列表中的事件记录来查看有关事件的更多详细信息。 将显示 "**详细信息**" 页, 其中包含事件记录中的详细属性。 显示的属性取决于事件发生时所采用的 Office 365 服务。 若要显示这些详细信息, 请单击 "**详细信息**"。 有关说明, 请参阅[Office 365 审核日志中的详细属性](detailed-properties-in-the-office-365-audit-log.md)。
  
![单击 "详细信息" 查看审核日志事件记录的详细属性](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)

  
### <a name="step-3-filter-the-search-results"></a>步骤 3: 筛选搜索结果

除了排序之外, 您还可以筛选审核日志搜索的结果。 这是一个很好的功能, 可帮助您快速筛选特定用户或活动的结果。 您可以先创建宽搜索, 然后快速筛选结果以查看特定事件。 然后, 您可以缩小搜索条件并重新运行搜索以返回更简单、更简明的结果集。
  
筛选结果:
  
1. 运行审核日志搜索。
    
2. 显示结果后, 单击 "**筛选结果**"。
    
    关键字框显示在每个列标题下。
    
3. 单击列标题下的一个框, 并根据要筛选的列键入一个词或短语。 结果将会动态调整, 以显示与您的筛选器匹配的事件。
    
    ![在 filter 中键入 word 以显示与筛选器匹配的事件](media/542dc323-a997-402c-934b-cc5e218e50bc.png)
  
4. 若要清除筛选器, 请单击 "筛选器" 框中的 " **X** " 或单击 "**隐藏筛选**"。
    
> [!TIP]
> 若要显示 Exchange 管理员审核日志中的事件, 请**-** 在 "**活动**筛选器" 框中键入 a (短线)。 这将显示在 Exchange 管理员事件的 "**活动**" 列中显示的 cmdlet 名称。 然后, 您可以按字母顺序对 cmdlet 名称进行排序。 

### <a name="step-4-export-the-search-results-to-a-file"></a>步骤 4: 将搜索结果导出到文件

您可以将审核日志搜索的结果导出到本地计算机上的逗号分隔值 (CSV) 文件中。 可以在 Microsoft Excel 中打开此文件, 并使用诸如搜索、排序、筛选和拆分单个列 (包含多个属性) 的多个列中的功能。
  
1. 运行审核日志搜索, 然后修改搜索条件, 直到获得所需的结果。
    
2. 单击 "**导出结果**", 然后选择下列选项之一: 
    
     - **保存加载的结果:** 选择此选项可仅导出在 "**审核日志搜索**" 页上的 "**结果**" 下显示的条目。 下载的 CSV 文件包含页面上显示的相同列 (和数据) (日期、用户、活动、项和详细信息)。 CSV 文件中包含一个额外的列 (称为**more**), 其中包含来自审核日志条目的详细信息。 因为您要导出的结果与在**审核日志搜索**页面上加载 (和查看) 的结果相同, 所以最多可以导出5000个条目。 
    
     - **下载所有结果:** 选择此选项可导出符合搜索条件的 Office 365 审核日志中的所有条目。 对于较大的搜索结果集, 请选择此选项从审核日志中下载所有条目, 除了可在 "**审核日志搜索**" 页上显示的5000审核记录。 此选项将原始数据从审核日志下载到 CSV 文件, 并包含来自名为**AuditData**的列中的审核日志条目的其他信息。 如果选择此导出选项, 可能需要较长时间下载文件, 因为如果选择其他选项, 文件可能会比下载的文件大得多。
    
       > [!IMPORTANT]
       > 您可以从单个审核日志搜索中最多将50000个条目下载到 CSV 文件中。 如果将50000条目下载到 CSV 文件中, 您可能会假定有超过50000个事件满足搜索条件。 若要导出超过此限制, 请尝试使用日期范围来减少审核日志条目的数量。 您可能需要运行包含较小日期范围的多个搜索以导出50000个以上的条目。 
  
3. 选择 "导出" 选项后, 将在窗口底部显示一条消息, 提示您打开 CSV 文件, 将其保存到 "下载" 文件夹中, 或将其保存到特定文件夹中。
 
#### <a name="more-information-about-exporting-and-viewing-audit-log-search-results"></a>有关导出和查看审核日志搜索结果的详细信息

- 如果下载所有搜索结果, 则 CSV 文件中包含一个名为 " **AuditData**" 的列, 其中包含有关每个事件的其他信息。 此列中的数据由一个 JSON 对象组成, 该对象包含审核日志记录中的多个属性。 JSON 对象中的每个*属性: 值*对由逗号分隔。 您可以使用 Excel 中 Power Query 编辑器中的 JSON 转换工具将**AuditData**列拆分为多个列, 以便 JSON 对象中的每个属性都有自己的列。 这样, 您就可以对其中一个或多个属性进行排序和筛选。 有关使用 Power Query 编辑器转换 JSON 对象的分步说明, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。
    
    拆分**AuditData**列后, 可以在 "**操作**" 列上进行筛选, 以显示特定类型的活动的详细属性。 
    
- "**下载所有结果**" 选项将原始数据从 Office 365 审核日志下载到 CSV 文件。 如果您选择 "**保存加载的结果**" 选项, 则此文件包含的列名称 (CreationDate、UserIds、Operation、AuditData) 不同。 同一活动的两个不同的 CSV 文件中的值也可能不同。 例如, CSV 文件的 "**操作**" 列中的活动与 "**审核日志搜索**" 页上 "**活动**" 列中显示的 "用户友好" 名称可能会不同。 例如, Mailboxlogin 该值与登录到邮箱的用户。

- 从包含来自不同 Office 365 服务的事件的搜索查询中下载所有结果时, CSV 文件中的 " **AuditData** " 列包含不同的属性, 具体取决于执行操作所使用的服务。 例如, Exchange 和 Azure AD 审核日志中的条目包含一个名为**ResultStatus**的属性, 用于指示操作是否成功。 此属性不包含在 SharePoint 中的事件中。 同样, SharePoint 事件具有一个属性, 用于标识与文件和文件夹相关的活动的网站 URL。 若要缓解此行为, 请考虑使用不同的搜索从单个服务中导出活动的结果。 
    
    有关在下载所有结果和每个结果适用的服务时, 在 CSV 文件的**AuditData**列中列出的许多属性的说明, 请参阅[Office 365 审核日志中的详细属性](detailed-properties-in-the-office-365-audit-log.md)。

## <a name="audited-activities"></a>审核的活动

本节中的表介绍了在 Office 365 中审核的活动。 您可以通过在安全与合规中心中搜索审核日志来搜索这些事件。
  
这些表对相关活动或特定 Office 365 服务中的活动进行分组。 这些表包括在 "**活动**" 下拉列表中显示的友好名称, 以及在导出搜索结果时, 在审核记录的详细信息和 CSV 文件中显示的相应操作的名称。 有关详细信息的说明, 请参阅[Office 365 审核日志中的详细属性](detailed-properties-in-the-office-365-audit-log.md)。
  
单击下列链接之一以转到特定表。
  
||||
|:-----|:-----|:-----|
|[文件和页面活动](#file-and-page-activities)<br/> |[文件夹活动](#folder-activities)<br/> |[SharePoint 列表活动](#sharepoint-list-activities)<br/>|
|[共享和访问请求活动](#sharing-and-access-request-activities)<br/> |[同步活动](#synchronization-activities)<br/> |[网站权限活动](#site-permissions-activities)<br/> |
|[网站管理活动](#site-administration-activities)<br/> |[Exchange 邮箱活动](#exchange-mailbox-activities)<br/> |[Sway 活动](#sway-activities) <br/> |
|[用户管理活动](#user-administration-activities) <br/> |[Azure AD 组管理活动](#azure-ad-group-administration-activities) <br/> |[应用程序管理活动](#application-administration-activities) <br/> |
|[角色管理活动](#role-administration-activities) <br/> |[目录管理活动](#directory-administration-activities) <br/>|[电子数据展示活动](#ediscovery-activities) <br/> |
|[高级电子数据展示活动](#advanced-ediscovery-activities)<br/> |[Power BI 活动](#power-bi-activities) <br/> |[Microsoft 工作区分析](#microsoft-workplace-analytics-activities)<br/>|
|[Microsoft 团队活动](#microsoft-teams-activities) <br/> |[Yammer 活动](#yammer-activities) <br/> |[Microsoft 流活动](#microsoft-flow-activities) <br/>|
|[Microsoft PowerApps 活动](#microsoft-powerapps)<br/>|[Microsoft Stream 活动](#microsoft-stream-activities) <br/>|[Exchange 管理活动](#exchange-admin-audit-log)<br/>|
||||
  
### <a name="file-and-page-activities"></a>文件和页面活动
  
下表介绍了 SharePoint Online 和 OneDrive for Business 中的文件和页面活动。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|访问的文件  <br/> |FileAccessed  <br/> |用户或系统帐户访问文件。  <br/> |
|（无）  <br/> |FileAccessedExtended  <br/> |这与 "访问的文件" (FileAccessed) 活动相关。 当同一人持续访问某个文件长时间 (最长为3小时) 时, 将记录 FileAccessedExtended 事件。 记录 FileAccessedExtended 事件的目的是减少在连续访问文件时记录的 FileAccessed 事件数。 这有助于减少多个 FileAccessed 记录在本质上是相同的用户活动的噪音, 并让您重点关注最初的 (更重要的) FileAccessed 事件。  <br/> |
|更改了合规性策略标签<br/> |ComplianceSettingChanged<br/> |保留标签应用于文档或从文档中删除。 手动或自动将保留标签应用于邮件时, 将触发此事件。<br/> |
|将记录状态更改为 "已锁定"<br/> |LockRecord<br/> |将文档分类为记录的保留标签的记录状态被锁定。 这意味着无法修改或删除该文档。 只有为网站至少分配了 "参与者" 权限的用户才能更改文档的记录状态。<br/> |
|将记录状态更改为 "已解锁"<br/> |UnlockRecord<br/> |将文档分类为记录的保留标签的记录状态被解除锁定。 这意味着可以修改或删除文档。 只有为网站至少分配了 "参与者" 权限的用户才能更改文档的记录状态。<br/><br/> |
|签入文件  <br/> |FileCheckedIn  <br/> |用户签入文档库中签出的文档。  <br/> |
|签出文件  <br/> |FileCheckedOut  <br/> |用户签出位于文档库中的文档。 用户可以对与其共享的文档执行签出和更改操作。  <br/> |
|复制的文件  <br/> |FileCopied  <br/> |用户从网站复制文档。 可以将复制的文件保存到网站上的另一个文件夹。  <br/> |
|删除的文件  <br/> |FileDeleted  <br/> |用户从网站中删除文档。  <br/> |
|从回收站删除的文件  <br/> |FileDeletedFirstStageRecycleBin  <br/> |用户从网站的回收站中删除文件。  <br/> |
|从第二阶段回收站删除的文件  <br/> |FileDeletedSecondStageRecycleBin  <br/> |用户从网站的第二阶段回收站中删除文件。  <br/> |
|已删除记录合规性策略标签<br/> |ComplianceRecordDelete<br/> |已删除作为记录分类的文档。 在将内容分类为记录的保留标签应用于文档时, 该文档被视为一条记录。 <br/> |
|检测到的文档敏感度不匹配 <br/>|DocumentSensitivityMismatchDetected<br/>|用户上载使用敏感度标签分级的文档, 该文档的优先级高于将文档上载到的网站所应用的敏感度标签。 如果应用于网站的敏感度标签的优先级高于应用于上载到网站的文档的敏感度标签, 则不会触发此事件。 有关敏感度标签优先级的详细信息, 请参阅[敏感度标签概述](sensitivity-labels.md#label-priority-order-matters)中的 "标签优先级" 一节。<br/>|
|在文件中检测到恶意软件  <br/> |FileMalwareDetected  <br/> |SharePoint 防病毒引擎可检测文件中的恶意软件。  <br/> |
|放弃文件签出  <br/> |FileCheckOutDiscarded  <br/> |用户放弃（或撤消）签出的文件。这意味着将放弃签出文件时对其所做的更改，而不将其保存到文档库中的文档版本。  <br/> |
|下载文件  <br/> |FileDownloaded  <br/> |用户从网站下载文档。  <br/> |
|修改的文件  <br/> |FileModified  <br/> |用户或系统帐户修改网站上文档的内容或属性。  <br/> |
|（无）  <br/> |FileModifiedExtended  <br/> |这与 "修改的文件" (FileModified) 活动相关。 当同一人持续修改某个文件的时间延长 (最长为3小时) 时, 将记录 FileModifiedExtended 事件。 记录 FileModifiedExtended 事件的目的是减少文件被连续修改时记录的 FileModified 事件的数量。 这有助于减少多个 FileModified 记录在本质上是相同的用户活动的噪音, 并让您重点关注最初的 (更重要的) FileModified 事件。  <br/> |
|移动的文件  <br/> |FileMoved  <br/> |用户将文档从其在网站上的当前位置移动到新位置。  <br/> |
|（无）  <br/> |FilePreviewed  <br/> |用户在 SharePoint 或 OneDrive for business 网站上预览文件。 这些事件通常发生在基于单个活动 (如查看图像库) 的高卷中。  <br/> |
|已回收文件的所有次要版本  <br/> |FileVersionsAllMinorsRecycled  <br/> |用户从文件的版本历史记录中删除所有次要版本。 已删除的版本将移至网站的回收站。  <br/> |
|文件的所有版本都已回收  <br/> |FileVersionsAllRecycled  <br/> |用户从文件的版本历史记录中删除所有版本。 已删除的版本将移至网站的回收站。  <br/> |
|文件的已回收版本  <br/> |FileVersionRecycled  <br/> |用户从文件的版本历史记录中删除版本。 删除的版本将移至网站的回收站。  <br/> |
|重命名文件  <br/> |FileRenamed  <br/> |用户重命名网站上的文档。  <br/> |
|还原的文件  <br/> |FileRestored  <br/> |用户从网站的回收站还原文档。  <br/> |
|上载的文件  <br/> |FileUploaded  <br/> |用户将文档上载到网站上的文件夹。  <br/> |
|查看页面  <br/> |PageViewed  <br/> |用户查看网站上的页面。 这不包括使用 Web 浏览器查看位于文档库中的文件。  <br/> |
|（无）  <br/> |PageViewedExtended  <br/> |这与 "查看过的页面" (PageViewed) 活动相关。 当同一个人连续查看网页长时间 (最长3小时) 时, 将记录 PageViewedExtended 事件。 记录 PageViewedExtended 事件的目的是减少在连续查看页面时记录的 PageViewed 事件数。 这有助于减少多个 PageViewed 记录在本质上是相同的用户活动的噪音, 并让您重点关注最初的 (更重要的) PageViewed 事件。  <br/> |
|查看客户端的信号 <br/>|ClientViewSignaled<br/>|用户的客户端 (如网站或移动应用程序) 已通知用户已查看指定的页面。 此活动通常会在页面的 PagePrefetched 事件后记录下来。 <br/><br/>**注意**: 由于 ClientViewSignaled 事件由客户端 (而不是服务器) 发出通知, 因此该事件可能不会被服务器记录, 因此可能不会出现在审核日志中。 审核记录中的信息也可能不可信。 但是, 由于用户的标识由用于创建信号的令牌进行验证, 因此相应的审核记录中列出的用户标识是准确的。 |
|（无） <br/>|PagePrefetched<br/>|用户的客户端 (如网站或移动应用程序) 已请求指示的页面, 以便在用户浏览到它时帮助提高性能。 记录此事件以指示页面内容已向用户的客户端提供服务。 此事件不是用户导航到页面的明确指示。 当客户端呈现页面内容时 (根据用户的请求), 应生成一个 ClientViewSignaled 事件。 并非所有客户端都支持指示预回迁, 因此某些预回迁的活动可能改为作为 PageViewed 事件进行记录。<br/>|
||||
  
### <a name="folder-activities"></a>文件夹活动
  
下表介绍了 SharePoint Online 和 OneDrive for Business 中的文件夹活动。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|复制的文件夹  <br/> |FolderCopied  <br/> |用户将文件夹从网站复制到 SharePoint 或 OneDrive for Business 中的其他位置。  <br/> |
|创建的文件夹  <br/> |FolderCreated  <br/> |用户在网站上创建一个文件夹。  <br/> |
|已删除文件夹  <br/> |FolderDeleted  <br/> |用户从网站中删除文件夹。  <br/> |
|回收站中已删除的文件夹  <br/> |FolderDeletedFirstStageRecycleBin  <br/> |用户从网站的回收站中删除文件夹。  <br/> |
|从第二阶段回收站删除的文件夹  <br/> |FolderDeletedSecondStageRecycleBin  <br/> |用户从网站的第二阶段回收站中删除文件夹。  <br/> |
|修改的文件夹  <br/> |FolderModified  <br/> |用户修改网站上的文件夹。 这包括更改文件夹元数据, 例如更改标记和属性。  <br/> |
|移动文件夹  <br/> |FolderMoved  <br/> |用户将文件夹移动到网站上的其他位置。  <br/> |
|重命名文件夹  <br/> |FolderRenamed  <br/> |用户重命名网站上的文件夹。  <br/> |
|已还原文件夹  <br/> |FolderRestored  <br/> |用户从网站的回收站还原已删除文件夹。  <br/> |
||||
  
### <a name="sharepoint-list-activities"></a>SharePoint 列表活动
  
下表介绍与用户与 SharePoint Online 中的列表和列表项进行交互时的相关活动。

|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
| 创建的列表              | ListCreated              | 用户创建了 SharePoint 列表。|
| 创建的列表列       | ListColumnCreated        | 用户创建了 SharePoint 列表列。 列表列是附加到一个或多个 SharePoint 列表的列。 |
| 创建的列表内容类型 | ListContentTypeCreated   | 用户创建了列表内容类型。 列表内容类型是附加到一个或多个 SharePoint 列表的内容类型。|
| 创建的列表项         | ListItemCreated          | 用户在现有 SharePoint 列表中创建了一个项。|
| 创建的网站栏       | SiteColumnCreated        | 用户创建了 SharePoint 网站栏。 网站栏是不附加到列表的列。 网站栏也是可由给定 web 中的任何列表使用的元数据结构。|
| 创建的网站内容类型 | 已创建网站 ContentType | 用户创建了一个网站内容类型。 "网站内容类型" 是附加到父网站的内容类型。|
| 删除的列表              | ListDeleted              | 用户已删除 SharePoint 列表。|
| 已删除的列表列       | 列表栏已删除      | 用户删除了 SharePoint 列表列。|
| 已删除的列表内容类型 | ListContentTypeDeleted   | 用户删除了列表内容类型。 |
| 删除的列表项         | 列表项已删除        | 用户已删除 SharePoint 列表项。|
| 已删除网站栏       | SiteColumnDeleted        | 用户删除了 SharePoint 网站栏。 |
| 已删除网站内容类型 | SiteContentTypeDeleted   | 用户已删除网站内容类型。|
| 回收列表项        | ListItemRecycled         | 用户将 SharePoint 列表项移动到回收站。|
| 还原的列表             | ListRestored             | 用户从回收站还原了 SharePoint 列表。|
| 还原的列表项        | ListItemRestored         | 用户从回收站还原了 SharePoint 列表项。|
| 更新的列表              | ListUpdated              | 用户通过修改一个或多个属性更新 SharePoint 列表。|
| 更新的列表列       | ListColumnUpdated        | 用户通过修改一个或多个属性更新了 SharePoint 列表列。|
| 更新的列表内容类型 | ListContentTypeUpdated   | 用户通过修改一个或多个属性更新了列表内容类型。|
| 更新的列表项         | ListItemUpdated          | 用户通过修改一个或多个属性更新了 SharePoint 列表项。|  
| 更新的网站栏       | SiteColumnUpdated        | 用户通过修改一个或多个属性更新了 SharePoint 网站栏。|
| 更新的网站内容类型 | SiteContentTypeUpdated   | 用户通过修改一个或多个属性更新网站内容类型。|
||||

### <a name="sharing-and-access-request-activities"></a>共享和访问请求活动
  
下表介绍了 SharePoint Online 和 OneDrive for Business 中的用户共享和访问请求活动。 对于共享事件, "**结果**" 下的 "**详细信息**" 列标识与该项目共享的用户或组的名称, 以及该用户或组是否为组织中的成员或来宾。 有关详细信息, 请参阅[在 Office 365 审核日志中使用共享审核](use-sharing-auditing.md)。
  
> [!NOTE]
> 根据 user 对象的 UserType 属性, 用户可以是*成员*或*来宾*。 成员通常是员工, 而来宾通常是组织外部的合作者。 当用户接受共享邀请 (而不是组织的一部分) 时, 将在组织的目录中为其创建来宾帐户。 一旦来宾用户在目录中拥有帐户, 资源就可以直接与他们共享 (无需邀请)。 
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|向网站集添加了权限级别  <br/> |PermissionLevelAdded  <br/> |向网站集添加了权限级别。  <br/> |
|接受的访问请求  <br/> |AccessRequestAccepted  <br/> |接受对网站、文件夹或文档的访问请求, 并向请求用户授予访问权限。  <br/> |
|接受的共享邀请  <br/> |SharingInvitationAccepted  <br/> |用户 (成员或来宾) 接受了共享邀请, 并且已被授予对资源的访问权限。 此事件包括受邀的用户的相关信息, 以及用于接受邀请的电子邮件地址 (可以是不同的)。 此活动通常附带第二个事件, 该事件描述了如何向用户授予对资源的访问权限, 例如, 将用户添加到有权访问该资源的组。  <br/> |
|阻止的共享邀请  <br/> |SharingInvitationBlocked  <br/> | 由于外部共享策略允许或拒绝基于目标用户的域的外部共享, 因此组织中的用户发送的共享邀请被阻止。 在这种情况下, 共享邀请被阻止, 因为:  <br/>  目标用户的域不包含在允许的域的列表中。  <br/>  或  <br/>  目标用户的域包含在阻止域的列表中。  <br/>  有关允许或阻止基于域的外部共享的详细信息, 请参阅[SharePoint Online 和 OneDrive For business 中的受限制域共享](https://support.office.com/article/5d7589cd-0997-4a00-a2ba-2320ec49c4e9)。  <br/> |
|创建的访问请求  <br/> |AccessRequestCreated  <br/> |用户请求访问网站、文件夹或文档不具有访问权限的权限。  <br/> |
|创建公司可共享的链接  <br/> |CompanyLinkCreated  <br/> |用户创建了指向资源的公司范围的链接。 公司范围内的链接仅可由组织中的成员使用。 来宾无法使用它们。  <br/> |
|创建了匿名链接  <br/> |AnonymousLinkCreated  <br/> |用户创建了指向资源的匿名链接。 具有此链接的任何人都可以访问该资源, 而无需进行身份验证。  <br/> |
|已创建安全链接  <br/> |SecureLinkCreated  <br/> |已创建对此项目的安全共享链接。  <br/> |
|已创建共享邀请  <br/> |SharingInvitationCreated  <br/> |用户在 SharePoint Online 或 OneDrive for Business 中共享了与组织目录中不存在的用户的资源。  <br/> |
|已删除安全链接  <br/> |SecureLinkDeleted  <br/> |已删除安全共享链接。  <br/> |
|拒绝访问请求  <br/> |AccessRequestDenied  <br/> |对网站、文件夹或文档的访问请求被拒绝。  <br/> |
|删除了公司可共享的链接  <br/> |CompanyLinkRemoved  <br/> |用户已删除指向资源的公司范围的链接。 无法再使用该链接访问该资源。  <br/> |
|删除了匿名链接  <br/> |AnonymousLinkRemoved  <br/> |用户删除了指向资源的匿名链接。 无法再使用该链接访问该资源。  <br/> |
|共享文件、文件夹或网站  <br/> |SharingSet  <br/> |用户 (成员或来宾) 在 SharePoint 或 OneDrive for Business 中与组织目录中的用户共享文件、文件夹或网站。 此活动的**详细信息**列中的值标识了与之共享资源的用户的名称, 以及此用户是否为成员或来宾。 此活动通常附带第二个事件, 该事件描述了如何向用户授予对资源的访问权限。 例如, 将用户添加到有权访问该资源的组中。  <br/> |
|更新了访问请求  <br/> |AccessRequestUpdated  <br/> |更新了对项目的访问请求。  <br/> |
|更新了匿名链接  <br/> |AnonymousLinkUpdated  <br/> |用户更新了指向资源的匿名链接。 当您导出搜索结果时, 更新的字段包含在 EventData 属性中。  <br/> |
|更新了共享邀请  <br/> |SharingInvitationUpdated  <br/> |更新了外部共享邀请。  <br/> |
|使用匿名链接  <br/> |AnonymousLinkUsed  <br/> |匿名用户通过使用匿名链接访问资源。 用户的标识可能是未知的, 但您可以获取其他详细信息, 如用户的 IP 地址。  <br/> |
|非共享文件、文件夹或网站  <br/> |SharingRevoked  <br/> |用户 (成员或来宾) 取消共享以前与其他用户共享的文件、文件夹或网站。  <br/> |
|使用公司可共享的链接  <br/> |CompanyLinkUsed  <br/> |用户使用公司范围的链接访问资源。  <br/> |
|使用的安全链接  <br/> |SecureLinkUsed  <br/> |用户使用安全链接。  <br/> |
|用户已添加到安全链接  <br/> |AddedToSecureLink  <br/> |已将用户添加到可以使用安全共享链接的实体列表中。  <br/> |
|用户已从安全链接中删除  <br/> |RemovedFromSecureLink  <br/> |从可以使用安全共享链接的实体列表中删除了用户。  <br/> |
|Withdrew 共享邀请  <br/> |SharingInvitationRevoked  <br/> |用户 withdrew 对资源的共享邀请。  <br/> |
||||
  
### <a name="synchronization-activities"></a>同步活动
  
下表列出了 SharePoint Online 和 OneDrive for Business 中的文件同步活动。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|允许的计算机同步文件  <br/> |ManagedSyncClientAllowed  <br/> |用户与网站成功建立同步关系。 同步关系成功, 因为用户的计算机是已添加到可以访问组织中的文档库的域列表 (称为 "*安全收件人列表*") 的域的成员。  <br/> 有关此功能的详细信息，请参阅[使用 Windows PowerShell cmdlet 为安全收件人列表中的域启用 OneDrive 同步](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|阻止的计算机同步文件  <br/> |UnmanagedSyncClientBlocked  <br/> |用户尝试与不是组织域成员的计算机或域的成员建立同步关系, 而该计算机尚未添加到可以访问文档的域列表 (称为*安全收件人列表)* 。组织中的库。 不允许同步关系，并阻止用户计算机在文档库上同步、下载或上传文件。  <br/> 有关此功能的信息，请参阅[使用 Windows PowerShell cmdlet 为安全收件人列表中的域启用 OneDrive 同步](https://go.microsoft.com/fwlink/p/?LinkID=534609)。  <br/> |
|将文件下载到计算机  <br/> |FileSyncDownloadedFull  <br/> |用户建立同步关系, 并首次成功从文档库中将文件下载到其计算机。  <br/> |
|已将文件更改下载到计算机  <br/> |FileSyncDownloadedPartial  <br/> |用户成功地从文档库中下载对文件所做的任何更改。 此活动指示对文档库中的文件所做的任何更改都将下载到用户的计算机上。 仅下载了所做的更改, 因为文档库先前已由用户下载 (由**下载的文件到计算机**活动中所示)。  <br/> |
|将文件上载到文档库  <br/> |FileSyncUploadedFull  <br/> |用户建立同步关系, 并将第一次成功地将文件从计算机上载到文档库。  <br/> |
|将文件更改上载到文档库  <br/> |FileSyncUploadedPartial  <br/> |用户成功地将更改上载到文档库上的文件。 此事件表明对文档库文件的本地版本所做的任何更改都已成功上传到文档库。 仅上载更改, 因为用户之前已上载这些文件 (由 "**上载的文件到文档库**" 活动中所示)。  <br/> |
||||

### <a name="site-permissions-activities"></a>网站权限活动

下表列出了与在 SharePoint 中分配权限以及使用组授予 (和废除) 对网站的访问权限的事件。

|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了网站集管理员  <br/> |SiteCollectionAdminAdded  <br/> |网站集管理员或所有者向网站的网站集管理员添加人员。 网站集管理员具有网站集和所有子网站的完全控制权限。 当管理员为自己提供了对用户的 OneDrive 帐户的访问权限 (通过在 SharePoint 管理中心中编辑用户配置文件或[使用 Microsoft 365 管理中心](https://docs.microsoft.com/office365/admin/add-users/get-access-to-and-back-up-a-former-user-s-data#part-1---get-access-to-the-former-employees-onedrive-for-business-documents)) 时, 也会记录此活动。 <br/> |
|向 SharePoint 组添加用户或组  <br/> |AddedToGroup  <br/> |用户向 SharePoint 组添加了成员或来宾。 这可能是一个有意的操作, 也可能是另一个活动 (如共享事件) 的结果。  <br/> |
|中断权限级别继承  <br/> |PermissionLevelsInheritanceBroken  <br/> |更改了某个项目, 因此它不再继承其父项的权限级别。  <br/> |
|中断共享继承  <br/> |SharingInheritanceBroken  <br/> |更改了某个项目, 因此它不再继承其父项的共享权限。  <br/> |
|创建的组  <br/> |GroupAdded  <br/> |网站管理员或所有者为网站创建一个组, 或执行一项将导致组创建的任务。 例如，当用户首次创建共享文件的链接时，系统组会被添加到用户的 OneDrive for Business 网站中。 此事件也可以是用户使用编辑权限创建共享文件链接的结果。  <br/> |
|删除的组  <br/> |GroupRemoved  <br/> |用户从网站中删除组。  <br/> |
|修改的访问请求设置  <br/> |WebRequestAccessModified  <br/> |已在网站上修改访问请求设置。  <br/> |
|修改的 "成员可以共享" 设置  <br/> |WebMembersCanShareModified  <br/> |**成员可以共享**设置已在网站上修改。  <br/> |
|网站集上的修改的权限级别  <br/> |PermissionLevelModified  <br/> |在网站集上更改了权限级别。  <br/> |
|修改的网站权限  <br/> |SitePermissionsModified  <br/> |网站管理员或所有者 (或系统帐户) 更改分配给网站上的组的权限级别。 如果从组中删除了所有权限, 也会记录此活动。  <br/><br/> **注意**: 此操作已在 SharePoint Online 中弃用。 若要查找相关事件, 可以搜索其他与权限相关的活动, 如**添加的网站集管理员**、向**SharePoint 组添加用户或组**、**允许用户创建组**、**创建组**和**删除组。**|
|从网站集删除权限级别  <br/> |PermissionLevelRemoved  <br/> |从网站集中删除了权限级别。  <br/> |
|已删除网站集管理员  <br/> |SiteCollectionAdminRemoved <br/> |网站集管理员或所有者将用户作为网站的网站集管理员删除。 当管理员从用户的 OneDrive 帐户的网站集管理员列表中删除自己 (通过在 SharePoint 管理中心中编辑用户配置文件) 时, 也会记录此活动。  若要在审核日志搜索结果中返回此活动, 您必须搜索所有活动。 <br/> |
|从 SharePoint 组中删除了用户或组  <br/> |RemovedFromGroup  <br/> |用户从 SharePoint 组中删除了成员或来宾。 这可能是一个有意的操作, 也可能是另一个活动的结果, 如 "取消共享" 事件。  <br/> |
|请求的网站管理员权限  <br/> |SiteAdminChangeRequest  <br/> |要添加为网站集的网站集管理员的用户请求。 网站集管理员具有网站集和所有子网站的完全控制权限。  <br/> |
|已还原的共享继承  <br/> |SharingInheritanceReset  <br/> |进行了更改, 以便项目继承其父级的共享权限。  <br/> |
|更新的组  <br/> |GroupUpdated  <br/> |网站管理员或所有者更改网站组的设置。 这可能包括更改组名、可以查看或编辑组成员身份的人员，以及成员身份请求的处理方式。  <br/> |
||||

  
### <a name="site-administration-activities"></a>网站管理活动
  
下表列出了 SharePoint Online 中的网站管理任务所产生的事件。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了允许的数据位置<br/>|AllowedDataLocationAdded|SharePoint 或全局管理员在多地理位置环境中添加了允许的数据位置。 <br/>|
|添加了豁免用户代理  <br/> |ExemptUserAgentSet  <br/> |SharePoint 或全局管理员向 SharePoint 管理中心内的豁免用户代理列表中添加了一个用户代理。  <br/> |
|添加了地理位置管理员<br/>|GeoAdminAdded<br/>|SharePoint 或全局管理员将用户添加为位置的地理位置管理员。 <br/>|
|允许用户创建组  <br/> |AllowGroupCreationSet  <br/> |网站管理员或所有者向网站添加权限级别, 允许分配该权限的用户为该网站创建组。  <br/> |
|取消的网站地理位置移动  <br/> |SiteGeoMoveCancelled  <br/> |SharePoint 或全局管理员成功取消 SharePoint 或 OneDrive 站点地理位置移动。 多地理位置功能可让 Office 365 组织跨多个 Office 365 数据中心地理位置, 这些地理位置称为信息。 有关详细信息, 请参阅[Office 365 中的 OneDrive 和 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。  <br/> |
|更改了共享策略  <br/> |SharingPolicyChanged  <br/> |SharePoint 或全局管理员使用 Office 365 管理门户、SharePoint 管理门户或 SharePoint Online 命令行管理程序更改了 SharePoint 共享策略。 将记录对组织中共享策略中的设置所做的任何更改。 已更改的策略在事件记录的详细属性中的 " **ModifiedProperties** " 字段中进行标识。  <br/> |
|已更改设备访问策略  <br/> |DeviceAccessPolicyChanged  <br/> |SharePoint 或全局管理员更改了贵组织的非托管设备策略。 此策略可控制不加入您的组织的设备对 SharePoint、OneDrive 和 Office 365 的访问权限。 配置此策略需要企业移动性 + 安全性订阅。 有关详细信息，请参阅[控制非托管设备的访问](https://support.office.com/article/5ae550c4-bd20-4257-847b-5c20fb053622)。  <br/> |
|已更改的豁免用户代理  <br/> |CustomizeExemptUsers  <br/> |SharePoint 或全局管理员自定义了 SharePoint 管理中心内的豁免用户代理列表。 您可以指定哪些用户代理免于接收整个网页进行索引编制。 这意味着当您指定为豁免的用户代理遇到 InfoPath 表单时, 该表单将作为 XML 文件而不是整个网页返回。 这可以加速对 InfoPath 表单编制索引。  <br/> |
|更改了网络访问策略  <br/> |NetworkAccessPolicyChanged  <br/> |SharePoint 或全局管理员在 SharePoint 管理中心或通过使用 SharePoint Online PowerShell 更改了基于位置的访问策略 (也称为 "受信任的网络边界")。 此类型的策略控制谁可以根据您指定的授权 IP 地址范围访问组织中的 SharePoint 和 OneDrive 资源。 有关详细信息, 请参阅[基于网络位置控制对 SharePoint Online 和 OneDrive 数据的访问](https://support.office.com/article/b5a5f1f1-1174-4c6b-91d0-9273a6b6971f)。  <br/> |
|完成的网站地理位置移动  <br/> |SiteGeoMoveCompleted  <br/> |组织中的全局管理员安排的网站地理位置移动已成功完成。 多地理位置功能可让 Office 365 组织跨多个 Office 365 数据中心地理位置, 这些地理位置称为信息。 有关详细信息, 请参阅[Office 365 中的 OneDrive 和 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。  <br/> |
|已创建发送到连接  <br/> |SendToConnectionAdded  <br/> |SharePoint 或全局管理员在 SharePoint 管理中心的 "记录管理" 页上创建新的 "发送至" 连接。 “发送至”连接指定文档存储库或记录中心设置。 创建“发送至”连接时，内容管理器可以将文档提交到指定位置。  <br/> |
|创建的网站集  <br/> |SiteCollectionCreated  <br/> |SharePoint 或全局管理员在您的 SharePoint Online 组织中创建一个网站集, 或者用户预配其 OneDrive for business 网站。  <br/> |
|已删除孤立中心网站<br/>|HubSiteOrphanHubDeleted<br/>|SharePoint 或全局管理员删除了一个孤立的中心网站, 该站点是一个不具有任何与之关联的站点的中心网站。 孤立的集线器可能是由于删除了原始中心网站造成的。 <br/>|
|删除已发送到连接  <br/> |SendToConnectionRemoved  <br/> |SharePoint 或全局管理员在 SharePoint 管理中心的 "记录管理" 页上删除 "发送至" 连接。  <br/> |
|删除的网站  <br/> |SiteDeleted  <br/> |网站管理员删除网站。  <br/> |
|启用文档预览  <br/> |PreviewModeEnabledSet  <br/> |网站管理员启用网站的文档预览。  <br/> |
|已启用旧版工作流  <br/> |LegacyWorkflowEnabledSet  <br/> |网站管理员或所有者将 SharePoint 2013 工作流任务内容类型添加到网站。 全局管理员还可以在 SharePoint 管理中心中启用整个组织的工作流。  <br/> |
|启用 Office on Demand  <br/> |OfficeOnDemandSet  <br/> |网站管理员启用 Office on Demand，允许用户访问最新版本的 Office 桌面应用程序。 SharePoint 管理中心启用了 Office on Demand，并需要包括全套已安装的 Office 应用程序的 Office 365 订阅。  <br/> |
|人员搜索的已启用结果源<br/>|PeopleResultsScopeSet<br/>|网站管理员为人员搜索网站的结果创建结果源。<br/>|
|已启用 RSS 源  <br/> |NewsFeedEnabledSet  <br/> |网站管理员或所有者为网站启用 RSS 源。 全局管理员可以在 SharePoint 管理中心中对整个组织启用 RSS 源。  <br/> |
|将网站加入中心网站<br/>|HubSiteJoined<br/>|网站所有者将其网站与中心网站相关联。<br/>|
|注册中心网站<br/>|HubSiteRegistered<br/>|SharePoint 或全局管理员创建中心网站。 结果是, 该网站被注册为中心网站。 <br/>|
|删除了允许的数据位置<br/>|AllowedDataLocationDeleted<br/>|SharePoint 或全局管理员在多地理位置环境中删除了允许的数据位置。<br/>|
|已删除地理位置管理员<br/>|GeoAdminDeleted<br/>|SharePoint 或全局管理员将用户删除为位置的地理位置管理员。<br/>|
|重命名网站  <br/> |SiteRenamed  <br/> |网站管理员或所有者重命名网站  <br/> |
|计划的网站地理位置移动  <br/> |SiteGeoMoveScheduled  <br/> |SharePoint 或全局管理员成功安排 SharePoint 或 OneDrive 站点地理位置移动。 多地理位置功能可让 Office 365 组织跨多个 Office 365 数据中心地理位置, 这些地理位置称为信息。 有关详细信息, 请参阅[Office 365 中的 OneDrive 和 SharePoint Online 中的多地理位置功能](https://go.microsoft.com/fwlink/?linkid=860840)。  <br/> |
|设置主机网站  <br/> |HostSiteSet  <br/> |SharePoint 或全局管理员将指定的网站更改为托管个人或 OneDrive for Business 网站。  <br/> |
|设置地理位置的存储配额  <br/> |GeoQuotaAllocated<br/> |SharePoint 或全局管理员为多地理位置环境中的地理位置配置了存储配额。<br/> |
|从中心网站中脱离网站<br/>|HubSiteUnjoined<br/>|网站所有者将其网站与中心网站解除相关。<br/>|
|未注册的中心网站<br/>|HubSiteUnregistered<br/>|SharePoint 或全局管理员将网站注销为中心网站。 当取消注册中心网站时, 它将不再作为中心网站工作。 <br/>|
||||
  
### <a name="exchange-mailbox-activities"></a>Exchange 邮箱活动
  
下表列出了邮箱审核日志记录可以记录的活动。 邮箱所有者、委派用户或管理员执行的邮箱活动将自动记录在最长90天的 Office 365 审核日志中。 管理员可以为组织中的所有用户关闭邮箱审核日志记录。 在这种情况下, 不会记录任何用户的邮箱操作。 有关详细信息, 请参阅[管理邮箱审核](enable-mailbox-auditing.md)。

 您还可以使用 Exchange Online PowerShell 中的[search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) cmdlet 搜索邮箱活动。 
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了委派邮箱权限  <br/> |AddMailboxPermissions  <br/> |管理员向其他人的邮箱分配了对用户 (称为代理) 的 FullAccess 邮箱权限。 FullAccess 权限允许代理打开其他人的邮箱, 并读取和管理邮箱的内容。  <br/> |
|添加或删除了具有 "代理访问日历" 文件夹的用户<br/> |UpdateCalendarDelegation<br/> |将用户添加或删除为对其他用户邮箱的日历的代理。 日历委派向同一组织中的其他人授予对邮箱所有者日历的管理权限。 <br/> |
|向文件夹添加了权限<br/> |AddFolderPermissions<br/> |添加了一个文件夹权限。 文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。<br/> |
|将邮件复制到另一个文件夹  <br/> |Copy  <br/> |已将某个邮件复制到另一个文件夹。  <br/> |
|创建的邮箱项目  <br/> |Create  <br/> |在邮箱中的 "日历"、"联系人"、"便笺" 或 "任务" 文件夹中创建项目。 例如, 创建一个新的会议请求。 不会审核创建、发送或接收邮件的情况。 此外, 还不会审核创建邮箱文件夹的情况。  <br/> |
|在 Outlook web app 中创建了新的收件箱规则  <br/> |NewInboxRule<br/> |邮箱所有者或对邮箱具有访问权限的其他用户已在 Outlook web app 中创建收件箱规则。<br/> |
|从 "已删除邮件" 文件夹中删除邮件  <br/> |SoftDelete  <br/> |邮件已从 "已删除邮件" 文件夹中永久删除或删除。 这些项目将移动到 "可恢复的项目" 文件夹中。 当用户选择邮件并按**Shift + Delete**时, 邮件也会移动到 "可恢复的项目" 文件夹中。  <br/> |
|将邮件标记为记录  <br/> |ApplyRecordLabel<br/> |邮件被分类为记录。 当手动或自动应用将内容分类为记录时, 将发生这种情况。<br/> |
|将邮件移动到另一个文件夹  <br/> |Move  <br/> |已将某个邮件移至另一个文件夹。  <br/> |
|将邮件移动到 "已删除邮件" 文件夹  <br/> |MoveToDeletedItems  <br/> |邮件已被删除并移动到 "已删除邮件" 文件夹。  <br/> |
|修改的文件夹权限  <br/> |UpdateFolderPermissions  <br/> |更改了文件夹权限。 文件夹权限控制组织中的哪些用户可以访问邮箱文件夹和文件夹中的邮件。  <br/> |
|从 Outlook web app 修改的收件箱规则<br/> |SetInboxRule<br/> |邮箱所有者或对邮箱具有访问权限的其他用户使用 Outlook web app 修改了收件箱规则。<br/> |
|已清除邮箱中的邮件  <br/> |HardDelete  <br/> |从 "可恢复的项目" 文件夹中清除邮件 (从邮箱中永久删除)。  <br/> |
|已删除委派邮箱权限  <br/> |Add-mailboxpermission  <br/> |管理员从某人的邮箱中删除了 FullAccess 权限 (已分配给代理)。 删除 FullAccess 权限后, 代理将无法打开其他人的邮箱或访问其中的任何内容。  <br/> |
|从文件夹删除权限<br/> |RemoveFolderPermissions<br/> |已删除文件夹权限。 文件夹权限控制组织中的哪些用户可以访问邮箱中的文件夹和位于这些文件夹中的邮件。<br/> |
|使用 "代理发送" 权限发送邮件  <br/> |SendAs  <br/> |邮件是使用 SendAs 权限发送的。 这意味着其他用户发送邮件, 就好像它来自邮箱所有者。  <br/> |
|使用 "代表发送" 权限发送的邮件  <br/> |SendOnBehalf  <br/> |邮件是使用 SendOnBehalf 权限发送的。 这意味着其他用户代表邮箱所有者发送邮件。 该邮件指示收件人代表发送邮件的收件人和实际发送邮件的收件人。  <br/> |
|更新了 Outlook 客户端中的收件箱规则<br/> |UpdateInboxRules<br/> |邮箱所有者或对邮箱具有访问权限的其他用户修改了 Outlook 客户端中的收件箱规则。<br/> |
|更新的邮件  <br/> |Update  <br/> |更改了邮件或其属性。  <br/> |
|登录到邮箱的用户  <br/> |Mailboxlogin 该值  <br/> |用户登录其邮箱。  <br/> |
||||

### <a name="sway-activities"></a>Sway 活动
  
下表列出了 Sway 中的用户和管理员活动。 Sway 是 Office 365 应用程序, 可帮助用户在基于 web 的交互式画布上收集、格式化和共享想法、情景和演示文稿。 有关详细信息, 请参阅[有关 Sway 的常见问题-管理员帮助](https://support.office.com/article/446380fa-25bf-47b2-996c-e12cb2f9d075)。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|更改了 Sway 共享级别  <br/> |SwayChangeShareLevel  <br/> |用户更改 Sway 的共享级别。 此事件将捕获用户更改与 Sway 关联的共享范围;例如, 公共与组织内部。  <br/> |
|已创建 Sway  <br/> |SwayCreate  <br/> |用户创建 Sway。  <br/> |
|删除的 Sway  <br/> |SwayDelete  <br/> |用户删除 Sway。  <br/> |
|禁用 Sway 复制  <br/> |SwayDisableDuplication  <br/> |用户禁用重复的 Sway。  <br/> |
|重复的 Sway  <br/> |SwayDuplicate  <br/> |用户复制 Sway。  <br/> |
|编辑 Sway  <br/> |SwayEdit  <br/> |用户编辑 Sway。  <br/> |
|启用 Sway 复制  <br/> |EnableDuplication  <br/> |用户可以复制 Sway。 默认情况下启用用户启用 Sway 复制的功能。  <br/> |
|吊销的 Sway 共享  <br/> |SwayRevokeShare  <br/> |用户通过撤销对 Sway 的访问来停止共享该 Sway。 撤销访问更改与 Sway 关联的链接。  <br/> |
|共享 Sway  <br/> |SwayShare  <br/> |用户打算共享 Sway。 此事件将捕获在 Sway 共享菜单中单击特定共享目标的用户操作。 该事件并不指示用户是否已完成共享操作。  <br/> |
|关闭 Sway 的外部共享  <br/> |SwayExternalSharingOff  <br/> |管理员使用 Microsoft 365 管理中心为整个组织禁用外部 Sway 共享。  <br/> |
|已启用 Sway 的外部共享  <br/> |SwayExternalSharingOn  <br/> |管理员使用 Microsoft 365 管理中心为整个组织启用外部 Sway 共享。  <br/> |
|已关闭 Sway 服务  <br/> |SwayServiceOff  <br/> |管理员通过使用 Microsoft 365 管理中心为整个组织禁用 Sway。  <br/> |
|已启用 Sway 服务  <br/> |SwayServiceOn  <br/> |管理员使用 Microsoft 365 管理中心为整个组织启用 Sway (默认情况下, Sway 服务处于启用状态)。  <br/> |
|查看 Sway  <br/> |SwayView  <br/> |用户查看 Sway。  <br/> |
||||

  
### <a name="user-administration-activities"></a>用户管理活动
  
下表列出了在管理员使用 Microsoft 365 管理中心或 Azure 管理门户添加或更改用户帐户时记录的用户管理活动。
  
|**活动**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了用户  <br/> |添加用户  <br/> |已创建 Office 365 用户帐户。  <br/> |
|更改的用户许可证  <br/> |更改用户许可证  <br/> |分配给用户的许可证已更改。 若要查看更改了哪些许可证, 请参阅相应**更新的用户**活动。  <br/> |
|更改了用户密码  <br/> |更改用户密码  <br/> |管理员更改了用户的密码。  <br/> |
|删除的用户  <br/> |删除用户  <br/> |删除了 Office 365 用户帐户。  <br/> |
|重置用户密码  <br/> |重置用户密码  <br/> |管理员重置用户的密码。  <br/> |
|设置强制用户更改密码的属性  <br/> |设置强制更改用户密码  <br/> |管理员设置强制用户在用户下次登录 Office 365 时更改其密码的属性。  <br/> |
|设置许可证属性  <br/> |设置许可证属性  <br/> |管理员修改已分配给用户的已授权属性。  <br/> |
|更新的用户  <br/> |更新用户  <br/> |管理员更改用户帐户的一个或多个属性。 有关可更新的用户属性的列表, 请参阅[Azure Active Directory 审核报告事件](https://go.microsoft.com/fwlink/p/?LinkID=616549)中的 "更新用户属性" 一节。  <br/> |
||||
  
### <a name="azure-ad-group-administration-activities"></a>Azure AD 组管理活动
  
下表列出了在管理员或用户创建或更改 Office 365 组时或者当管理员使用 Microsoft 365 管理中心或 Azure 管理门户创建安全组时记录的组管理活动。 有关 Office 365 中的组的详细信息, 请参阅在[Microsoft 365 管理中心中查看、创建和删除组](https://support.office.com/article/a6360120-2fc4-46af-b105-6a04dc5461c7)。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了组  <br/> |添加组  <br/> |已创建组。  <br/> |
|向组添加了成员  <br/> |将成员添加到组  <br/> |向组添加成员。  <br/> |
|删除的组  <br/> |删除组  <br/> |组已删除。  <br/> |
|已从组中删除成员  <br/> |从组中删除成员  <br/> |成员已从组中删除。  <br/> |
|更新的组  <br/> |更新组  <br/> |更改了组的属性。  <br/> |
||||
   
### <a name="application-administration-activities"></a>应用程序管理活动
  
下表列出了在管理员添加或更改在 Azure AD 中注册的应用程序时记录的应用程序管理活动。 必须在目录中注册依赖 Azure AD 进行身份验证的任何应用程序。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|添加了委派条目  <br/> |添加委派条目  <br/> |已创建/授予 Azure AD 中的应用程序的身份验证权限。  <br/> |
|添加了服务主体  <br/> |添加服务主体  <br/> |在 Azure AD 中注册应用程序。 应用程序由目录中的服务主体表示。  <br/> |
|向服务主体添加了凭据  <br/> |添加服务主体凭据  <br/> |向 Azure AD 中的服务主体添加了凭据。 服务主体表示目录中的应用程序。  <br/> |
|已删除委派条目  <br/> |删除委派条目  <br/> |从 Azure AD 中的应用程序中删除了身份验证权限。  <br/> |
|从目录中删除了服务主体  <br/> |删除服务主体  <br/> |从 Azure AD 删除/注销了应用程序。 应用程序由目录中的服务主体表示。  <br/> |
|从服务主体删除凭据  <br/> |删除服务主体凭据  <br/> |凭据已从 Azure AD 中的服务主体中删除。 服务主体表示目录中的应用程序。  <br/> |
|设置委派项  <br/> |设置委派项  <br/> |为 Azure AD 中的应用程序更新了身份验证权限。  <br/> |
||||

### <a name="role-administration-activities"></a>角色管理活动
  
下表列出了在管理员管理 Microsoft 365 管理中心或 Azure 管理门户中的管理员角色时记录的 Azure AD 角色管理活动。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|将成员添加到角色  <br/> |向角色添加角色成员  <br/> |向 Office 365 中的管理员角色添加了用户。  <br/> |
|从目录角色中删除了用户  <br/> |从角色中删除角色成员  <br/> |从 Office 365 中的管理员角色中删除了用户。  <br/> |
|设置公司联系人信息  <br/> |设置公司联系人信息  <br/> |更新了 Office 365 组织的公司级别联系人首选项。 这包括 Office 365 发送的与订阅相关的电子邮件的电子邮件地址, 以及有关 Office 365 服务的技术通知。  <br/> |
||||
   
### <a name="directory-administration-activities"></a>目录管理活动
  
下表列出了管理员在 Microsoft 365 管理中心或 Azure 管理门户中管理其 Office 365 组织时记录的 Azure AD 目录和与域相关的活动。
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|向公司添加了域  <br/> |向公司添加域  <br/> |向 Office 365 组织添加了域。  <br/> |
|向目录添加了合作伙伴  <br/> |向公司添加合作伙伴  <br/> |向 Office 365 组织添加了合作伙伴 (委派管理员)。  <br/> |
|从公司中删除了域  <br/> |从公司中删除域  <br/> |从 Office 365 组织中删除了一个域。  <br/> |
|从目录中删除了合作伙伴  <br/> |从公司中删除合作伙伴  <br/> |从 Office 365 组织中删除合作伙伴 (委派管理员)。  <br/> |
|设置公司信息  <br/> |设置公司信息  <br/> |更新了 Office 365 组织的公司信息。 这包括 Office 365 发送的与订阅相关的电子邮件的电子邮件地址, 以及有关 Office 365 服务的技术通知。  <br/> |
|设置域身份验证  <br/> |设置域身份验证  <br/> |更改了 Office 365 组织的域身份验证设置。  <br/> |
|更新了域的联合身份验证设置  <br/> |在域上设置联盟设置  <br/> |更改了 Office 365 组织的联合身份验证 (外部共享) 设置。  <br/> |
|设置密码策略  <br/> |设置密码策略  <br/> |更改了 Office 365 组织中用户密码的长度和字符约束。  <br/> |
|已启用 Azure AD 同步  <br/> |在公司上设置 DirSyncEnabled 标志  <br/> |设置为 Azure AD 同步启用目录的属性。  <br/> |
|更新域  <br/> |更新域  <br/> |更新了 Office 365 组织中的域的设置。  <br/> |
|验证域  <br/> |验证域  <br/> |已验证您的组织是否为域的所有者。  <br/> |
|已验证电子邮件验证域  <br/> |验证电子邮件验证域  <br/> |使用电子邮件验证来验证您的组织是否为域的所有者。  <br/> |
||||
   
### <a name="ediscovery-activities"></a>电子数据展示活动
  
在安全与合规中心中或通过运行相应的 PowerShell cmdlet 在审核日志中执行的内容搜索和电子数据展示相关的活动将记录在审核日志中。 这包括以下活动:
  
- 创建和管理电子数据展示事例
    
- 创建、启动和编辑内容搜索
    
- 执行内容搜索操作, 如预览、导出和删除搜索结果
    
- 配置内容搜索的权限筛选
    
- 管理电子数据展示管理员角色
    
有关记录的电子数据展示活动的列表和详细说明, 请参阅[在 Office 365 审核日志中搜索电子数据展示活动](search-for-ediscovery-activities-in-the-audit-log.md)。
  
> [!NOTE]
> 在搜索结果中显示的 "**活动**" 下拉列表中的 "**电子数据展示活动**" 下列出的活动最长需要30分钟的时间。 相反, 电子数据展示 cmdlet 活动中的相应事件需要长达24小时才会显示在搜索结果中。 
  
### <a name="advanced-ediscovery-activities"></a>高级电子数据展示活动

下表列出了 IT 和法律专业人员在 Microsoft 365 中的高级电子数据展示中执行任务所产生的活动。 有关详细信息, 请参阅[Microsoft 365 中的高级电子数据展示解决方案概述](compliance20/overview-ediscovery-20.md)。

|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
| 向另一个评审集添加了数据<br/>         | AddWorkingSetQueryToWorkingSet<br/>  |  用户将文档从一个审阅集添加到不同的审阅集。<br/>|
| 向评审集添加了数据 <br/>                | AddQueryToWorkingSet<br/>            |  用户将搜索结果从与高级电子数据展示事例关联的内容搜索添加到评审集。<br/>|
| 将非 Office 365 数据添加到评审集<br/>  | AddNonOffice365DataToWorkingSet<br/> |  用户将非 Office 365 数据添加到评审集。<br/>|
| 向评审集添加了已修正的文档<br/> | AddRemediatedData<br/>               |  用户上载的文档包含已修复到审阅集的索引错误。<br/>|
| 评审集合中的已分析数据 <br/>             | RunAlgo<br/>                         |  用户对审阅集中的文档运行分析。 <br/>|
| 评审设置中的批注文档 <br/>        | AnnotateDocument<br/>                |  用户在审阅集中批注了文档。 批注在文档中包含 redacting 内容。 <br/>|
| 比较的加载集 <br/>                      | LoadComparisonJob<br/>               |用户比较评审集中的两个不同的加载集。 加载集是指将与事例关联的内容搜索中的数据添加到审阅集。  <br/>|
| 将编辑文档转换为 PDF<br/>      | BurnJob<br/>                         |用户将审阅集中的所有编辑文档都转换为 PDF 文件。<br/>|
| 创建的审阅集<br/>                       | CreateWorkingSet<br/>                |用户创建了一个审阅集。<br/>|
| 创建的审阅集搜索<br/>                | CreateWorkingSetSearch<br/>          |用户创建了搜索查询, 该查询在审阅集中搜索文档。 <br/>|
| 创建的标记<br/>                              | CreateTag<br/>                       |用户在审阅集中创建了一个标记组。 一个标记组可以包含一个或多个子标记。 然后, 这些标记用于在审阅集中标记文档。<br/>|
| 已删除的审阅集搜索 <br/>               | DeleteWorkingSetSearch<br/>          |用户在审阅集中删除了搜索查询。<br/>|
| 删除的标记<br/>                              | DeleteTag<br/>                       |用户在审阅集中删除了标记或标记组。<br/>|
| 下载的文档<br/>                      | DownloadDocument<br/>                |用户从审阅集下载了文档。<br/>|
| 编辑过的标记 <br/>                              | DownloadDocument<br/>                |用户更改了审阅集中的标记。<br/>|
| 从审阅集导出的文档 <br/>      | ExportJob<br/>                       |用户从审阅集中导出文档。<br/>|
| 修改的大小写设置 <br/>                   | UpdateCaseSettings<br/>              | 用户修改了案例的设置。 事例设置包括用于控制搜索和分析行为的大小写信息、访问权限和设置。<br/>|
| 修改的审阅集搜索<br/>               | UpdateWorkingSetSearch<br/>          |  用户在审阅集中编辑了搜索查询。<br/>|
| 预览审阅集搜索 <br/>             | PreviewWorkingSetSearch<br/>         |  用户在审阅集中预览搜索查询的结果。<br/>|
| 修正的错误文档 <br/>              | ErrorRemediationJob<br/>             |  用户修复了包含索引错误的文件。 <br/>|
| 加标签的文档<br/>                          | TagFiles<br/>                        |  用户在审阅集中标记文档。<br/>|
| 查询的标记结果<br/>                | TagJob<br/>                          |  用户标记与审阅集中的搜索查询条件匹配的所有文档。<br/>|
| 查看评审设置中的文档<br/>            | ViewDocument<br/>                    |  用户在审阅集中查看文档。<br/>|
|||

### <a name="power-bi-activities"></a>Power BI 活动
  
可以在审核日志中搜索 Power BI 中的活动。 有关 Power BI 活动的信息, 请参阅在[组织中使用审核](https://docs.microsoft.com/power-bi/service-admin-auditing#activities-audited-by-power-bi)中的 "power bi 审核的活动" 部分。
  
Power BI 的审核日志记录默认情况下不启用。 若要在 Office 365 审核日志中搜索 Power BI 活动, 您必须在 Power BI 管理门户中启用审核。 有关说明, 请参阅[POWER BI 管理门户](https://docs.microsoft.com/power-bi/service-admin-portal#audit-logs)中的 "审核日志" 部分。
  
### <a name="microsoft-workplace-analytics-activities"></a>Microsoft Workplace Analytics 活动

工作区分析可深入了解如何在您的 Office 365 组织中进行组协作。 下表列出了在工作区分析中分配了管理员角色或分析师角色的用户所执行的活动。 分配了分析员角色的用户具有对所有服务功能的完全访问权限, 并使用产品进行分析。 分配了管理员角色的用户可以配置隐私设置和系统默认设置, 并可以准备、上传和验证工作区分析中的组织数据。 有关详细信息, 请参阅[Workplace Analytics](https://docs.microsoft.com/en-us/workplace-analytics/index-orig)。

|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|访问过的 OData 链接 <br/> |AccessedOdataLink <br/> |分析师访问了查询的 OData 链接。|
|已取消查询 <br/> |CanceledQuery <br/> |分析师取消了一个正在运行的查询。|
|已创建会议排除 <br/> |MeetingExclusionCreated <br/> |分析师创建了会议排除规则。|
|删除的结果 <br/> |DeletedResult <br/> |分析师删除了查询结果。|
|已下载报告 <br/> |DownloadedReport <br/> |分析师下载了一个查询结果文件。|
|执行的查询 <br/> |ExecutedQuery <br/> |分析师运行查询。|
|更新的数据访问设置 <br/> |UpdatedDataAccessSetting <br/> |管理员更新的数据访问设置。|
|更新的隐私设置 <br/> |UpdatedPrivacySetting <br/> |管理员更新的隐私设置;例如, 最小组大小。|
|已上载的组织数据 <br/> |UploadedOrgData <br/> |管理员已上载组织数据文件。|
|查看浏览 <br/> |ViewedExplore <br/> |分析家在一个或多个浏览页选项卡中查看了可视化项。|
||||

### <a name="microsoft-teams-activities"></a>Microsoft 团队活动
  
下表列出了 Microsoft 团队中记录的 Office 365 审核日志中的用户和管理员活动。 Microsoft 团队是 Office 365 中一个聊天中心的工作区。 它将团队的对话、会议、文件和笔记集中到一个位置。 有关详细信息和指向帮助主题的链接, 请参阅:
  
- [有关 Microsoft 团队的常见问题-管理员帮助](https://support.office.com/article/05cbe533-2181-4e95-a4b0-52cd7695fafc)
    
- [Microsoft 团队帮助](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|向团队添加了机器人  <br/> |BotAddedToTeam  <br/> |用户向团队中添加机器人。  <br/> |
|添加了频道  <br/> |ChannelAdded  <br/> |用户向团队添加频道。  <br/> |
|添加了连接器  <br/> |ConnectorAdded  <br/> |用户将连接器添加到频道。  <br/> |
|向团队添加了成员  <br/> |MemberAdded  <br/> |团队所有者向团队添加成员。  <br/> |
|添加了选项卡  <br/> |TabAdded  <br/> |用户将选项卡添加到频道。  <br/> |
|更改了频道设置  <br/> |ChannelSettingChanged  <br/> | 当团队成员执行以下活动时, 将记录 ChannelSettingChanged 操作。 对于这些活动中的每个活动, 在审核日志搜索结果中的**项**列中显示了已更改的设置 (如下面的括号中所示) 的说明。  <br/> <br/>-更改团队频道的名称 (**通道名称**)。  <br/>  <br/>-更改团队频道的说明 (**通道说明**)。  <br/> |
|已更改的组织设置  <br/> |TeamsTenantSettingChanged  <br/> | 当全局管理员 (使用 Microsoft 365 管理中心) 执行以下活动时, 将记录 TeamsTenantSettingChanged 操作。请注意, 这些活动会影响组织范围的 Microsoft 团队设置。 有关详细信息, 请参阅[Microsoft 团队的管理员设置](https://support.office.com/article/3966a3f5-7e0f-4ea9-a402-41888f455ba2)。  <br/>  对于这些活动中的每个活动, 在审核日志搜索结果中的**项**列中显示了已更改的设置 (如下面的括号中所示) 的说明。  <br/><br/>-为组织 (**Microsoft 团队**) 启用或禁用 Microsoft 团队。  <br/><br/>-为组织启用或禁用 Microsoft 团队和 Skype for business 之间的互操作性 (**Skype For business 互操作性**)。<br/><br/>-启用或禁用 Microsoft 团队客户端 (组织图表视图) 中的组织结构图视图 **。 -<br/>或禁用工作组成员安排私人会议的能力 (私人会议计划<br/>****)。 -<br/>或禁用工作组成员安排频道会议的能力 (渠道会议计划<br/>**)。  <br/><br/>-启用或禁用团队会议中的视频呼叫 (Skype 会议的视频 **)。 -<br/>Microsoft 团队 meetups for the 组织启用或禁用屏幕共享 (Skype 会议的屏幕共享<br/>****)。 -<br/>或禁用将动画图像 (称为 giphy) 添加到团队对话 (动画图像) 的<br/>功能**。  <br/><br/>-更改组织的内容评级设置 (**内容评级**)。 内容分级限制可在对话中显示的动画图像的类型。  <br/><br/>-启用或禁用团队成员从 Internet 向团队对话中添加可自定义的图像 (称为自定义 meme) 的功能 (来自 Internet 的可自定义图像 **)。 -<br/>或禁用工作组成员向团队对话 (可编辑的图像) 中添加可编辑图像 (称为不干胶标签) 的<br/>功能****。-<br/>或禁用团队成员在 Microsoft 团队聊天和频道 (组织范围内的 bot) 中使用 bot 的<br/>功能**。<br/><br/>-为 Microsoft 团队启用特定的 bot。 这不包括 T-机器人, 这是在为组织 (**单个 bot**) 启用 bot 时可使用的团队的帮助机器人。  <br/><br/>-启用或禁用工作组成员添加分机或选项卡 (**分机或选项卡**) 的功能。  <br/><br/>-启用或禁用 Microsoft 团队的专用 Bot 的侧面加载 (**bot 的侧面加载**)。  <br/><br/>-启用或禁用用户向 Microsoft 团队频道 (**通道电子邮件**) 发送电子邮件的功能。  <br/> |
|更改了团队中成员的角色  <br/> |MemberRoleChanged  <br/> |团队所有者更改团队中成员的角色。 以下值表示分配给用户的角色类型。  <br/><br/><br/> **1** -指示所有者角色。<br/>**2** -指示成员角色。 <br/>**3** -指示来宾角色。 <br/>Members 属性还包括您的组织的名称和成员的电子邮件地址。  <br/> |
|更改了团队设置  <br/> |TeamSettingChanged  <br/> | 当团队所有者执行以下活动时, 将记录 TeamSettingChanged 操作。 对于这些活动中的每个活动, 在审核日志搜索结果中的**项**列中显示了已更改的设置 (如下面的括号中所示) 的说明。  <br/><br/>-更改团队的访问类型。 可以将团队设置为私有或公共 (**团队访问类型**)。 当团队为私有时 (默认设置), 用户只能通过邀请访问团队。 如果团队是公共的, 则任何人都能发现。  <br/><br/>-更改团队的信息分类 (**团队分类**)。  <br/>  例如, 可以将团队数据分类为业务影响高、业务影响或业务影响较低。<br/><br/>-更改团队的名称 (**团队名称**)。  <br/><br/>-更改团队说明 (团队说明 * *)。 <br/><br/>-对任何团队设置所做的更改。 团队所有者可以通过右键单击团队, 单击 "**管理团队**", 然后单击 "**设置**" 选项卡来访问团队客户端中的这些设置。对于这些活动, 已更改的设置的名称将显示在审核日志搜索结果中的**项目**列中。  <br/> |
|创建的团队  <br/> |TeamCreated  <br/> |用户创建团队。  <br/> |
|删除的频道  <br/> |ChannelDeleted  <br/> |用户从团队中删除频道。  <br/> |
|已删除团队  <br/> |TeamDeleted  <br/> |团队所有者删除团队。  <br/> |
|从团队中删除机器人  <br/> |BotRemovedFromTeam  <br/> |用户从团队中删除机器人。  <br/> |
|已删除连接器  <br/> |ConnectorRemoved  <br/> |用户从频道中删除连接器。  <br/> |
|从团队中删除了成员  <br/> |MemberRemoved  <br/> |团队所有者从团队中删除成员。  <br/> |
|已删除选项卡  <br/> |TabRemoved  <br/> |用户从频道中删除选项卡。  <br/> |
|更新的连接器  <br/> |ConnectorUpdated  <br/> |用户修改了频道中的连接器。  <br/> |
|更新的选项卡  <br/> |TabUpdated  <br/> |用户修改了频道中的选项卡。  <br/> |
|用户已登录到团队  <br/> |TeamsSessionStarted  <br/> |用户登录到 Microsoft 团队客户端。  <br/> |
||||

### <a name="yammer-activities"></a>Yammer 活动
  
下表列出了 Yammer 中记录的 Office 365 审核日志中的用户和管理员活动。 若要从 Office 365 审核日志中返回 Yammer 相关的活动, 必须在 "**活动**" 列表中选择 "**显示所有活动的结果**"。 使用 "日期范围" 框和 "**用户**" 列表缩小搜索结果的范围。 
  
|**易记名称**|**操作**|**说明**|
|:-----|:-----|:-----|
|已更改的数据保留策略  <br/> |SoftDeleteSettingsUpdated  <br/> |已验证管理员将网络数据保留策略的设置更新为 "硬删除" 或 "软删除"。 只有经过验证的管理员才能执行此操作。  <br/> |
|更改了网络配置  <br/> |NetworkConfigurationUpdated  <br/> |网络或经验证的管理员更改 Yammer 网络的配置。 这包括设置导出数据和启用聊天的时间间隔。  <br/> |
|更改了网络配置文件设置  <br/> |ProcessProfileFields  <br/> |网络或经验证的管理员更改网络用户网络的成员配置文件上显示的信息。  <br/> |
|更改了私人内容模式  <br/> |SupervisorAdminToggled  <br/> |已验证管理员打开或关闭 "*私人内容模式*"。 此模式允许管理员查看专用组中的帖子, 并查看单个用户 (或用户组) 之间的专用消息。 仅经过验证的管理员才可以执行此操作。  <br/> |
|更改了安全配置  <br/> |NetworkSecurityConfigurationUpdated  <br/> |经过验证的管理员将更新 Yammer 网络的安全配置。 这包括设置密码过期策略和对 IP 地址的限制。 只有经过验证的管理员才能执行此操作。  <br/> |
|创建的文件  <br/> |FileCreated  <br/> |用户上传文件。  <br/> |
|创建的组  <br/> |GroupCreation  <br/> |用户创建一个组。  <br/> |
|删除的组  <br/> |GroupDeletion  <br/> |将从 Yammer 中删除组。  <br/> |
|已删除邮件  <br/> |MessageDeleted  <br/> |用户删除邮件。  <br/> |
|下载文件  <br/> |FileDownloaded  <br/> |用户下载文件。  <br/> |
|导出的数据  <br/> |DataExport  <br/> |已验证管理员导出 Yammer 网络数据。 只有经过验证的管理员才能执行此操作。  <br/> |
|共享文件  <br/> |FileShared  <br/> |用户与其他用户共享文件。  <br/> |
|挂起的网络用户  <br/> |NetworkUserSuspended  <br/> |网络或经认证的管理员挂起 (停用) Yammer 中的用户。  <br/> |
|挂起的用户  <br/> |UserSuspension  <br/> |用户帐户已挂起 (已停用)。  <br/> |
|更新的文件说明  <br/> |FileUpdateDescription  <br/> |用户更改文件的说明。  <br/> |
|更新的文件名  <br/> |FileUpdateName  <br/> |用户更改文件的名称。  <br/> |
|查看文件  <br/> |FileVisited  <br/> |用户查看文件。  <br/> |
||||
   
### <a name="microsoft-flow-activities"></a>Microsoft 流活动

可以在审核日志中搜索 Microsoft Flow 中的活动。 这些活动包括创建、编辑和删除流以及更改流权限。 有关流活动审核的信息, 请参阅现已[在安全 & 合规中心中提供的博客 Microsoft 流审核事件](https://flow.microsoft.com/blog/security-and-compliance-center)。

### <a name="microsoft-powerapps"></a>Microsoft PowerApps

您可以在 PowerApps 中搜索与应用程序相关的活动的审核日志。 这些活动包括创建、启动和发布应用程序。 还会审核对应用程序分配权限。 有关所有 PowerApps 活动的说明, 请参阅[powerapps 的活动日志记录](https://docs.microsoft.com/en-us/power-platform/admin/logging-powerapps#what-events-are-audited)。

### <a name="microsoft-stream-activities"></a>Microsoft Stream 活动
  
可以在审核日志中搜索 Microsoft Stream 中的活动。 这些活动包括用户执行的视频活动、组频道活动和管理活动, 如管理用户、管理组织设置和导出报告。 有关这些活动的说明, 请参阅[Microsoft stream 中的审核日志](https://docs.microsoft.com/stream/audit-logs)中的 "microsoft stream 中记录的活动" 部分。

### <a name="exchange-admin-audit-log"></a>Exchange 管理员审核日志
  
Exchange 管理员审核日志记录 (默认情况下在 Office 365 中启用) 当管理员 (或已分配管理权限的用户) 在 Exchange Online 组织中进行更改时, 将在 Office 365 审核日志中记录一个事件。 通过使用 Exchange 管理中心或通过在 Exchange Online PowerShell 中运行 cmdlet 所做的更改将记录在 Exchange 管理员审核日志中。 以谓词**Get**、 **Search**或**Test**开头的 cmdlet 不会记录在 Office 365 审核日志中。 有关 Exchange 中的管理员审核日志记录的更多详细信息, 请参阅[管理员审核日志记录](https://go.microsoft.com/fwlink/p/?LinkID=619225)。

> [!IMPORTANT]
> 某些不在 Exchange 管理员审核日志 (或 Office 365 审核日志) 中记录的 Exchange Online cmdlet。 这些 cmdlet 中的许多与维护 Exchange Online 服务相关, 由 Microsoft 数据中心人员或服务帐户运行。 由于这些 cmdlet 会导致大量的 "嘈杂" 审核事件, 因此不会记录这些 cmdlet。 如果有未经审核的 Exchange Online cmdlet, 请在[Office 365 安全 & 合规性用户语音论坛](https://office365.uservoice.com/forums/289138-office-365-security-compliance)中提交建议, 并请求启用审核。 您还可以将设计更改请求 (DCR) 提交到 Microsoft 支持部门。
  
以下是在搜索 Office 365 审核日志时搜索 Exchange 管理员活动的一些提示:
  
- 若要从 Exchange 管理员审核日志中返回条目, 您必须在 "**活动**" 列表中选择 "**显示所有活动的结果**"。 使用 "日期范围" 框和 "**用户**" 列表可缩小特定日期范围内特定 Exchange 管理员运行的 cmdlet 的搜索结果。 
    
- 若要显示来自 Exchange 管理员审核日志的事件, 请筛选搜索结果并在**-** "**活动**筛选器" 框中键入 a (划线)。 这将显示在 Exchange 管理员事件的 "**活动**" 列中显示的 cmdlet 名称。 然后, 您可以按字母顺序对 cmdlet 名称进行排序。 
    
    ![在 "活动" 框中键入一个短划线以筛选 Exchange 管理员事件](media/7628e7aa-6263-474a-a28b-2dcf5694bb27.png)
  
- 若要获取有关运行什么 cmdlet、使用的参数和参数值以及受影响的对象的信息, 您可以通过选择 "**下载所有结果**" 选项导出搜索结果。 有关详细信息, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。 
    
- 您还可以使用 Exchange `Search-UnifiedAuditLog -RecordType ExchangeAdmin` Online PowerShell 中的命令仅返回 Exchange 管理员审核日志中的审核记录。 在运行 Exchange cmdlet 后, 可能需要长达30分钟, 才能在搜索结果中返回相应的审核日志条目。 有关详细信息, 请参阅[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog)。 有关将**UnifiedAuditLog** cmdlet 返回的搜索结果导出到 CSV 文件中的信息, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md#tips-for-exporting-and-viewing-the-audit-log)中的 "导出和查看审核日志的提示" 一节。

- 您还可以使用 Exchange 管理中心或在 Exchange Online PowerShell 中运行**搜索 search-adminauditlog** , 以查看 exchange 管理员审核日志中的事件。 有关说明，请参阅：
   - [查看管理员审核日志](https://technet.microsoft.com/library/dn342832%28v=exchg.150%29.aspx)。 
   
   -  [搜索-Search-adminauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-adminauditlog)
   
   请注意, exchange 管理员审核日志和 Office 365 审核日志中都记录了相同的 Exchange 管理员活动。
  
## <a name="frequently-asked-questions"></a>常见问题

**在哪里可以找到由 Office 365 中的审计服务提供的功能？**

有关 Office 365 中提供的审核和报告功能的详细信息, 请参阅[office 365 中的审核和报告](office-365-auditing-and-reporting-overview.md)。 

**目前已审核的 Office 365 服务有什么不同？**

审核最常用的 Office 365 服务, 如 Exchange Online、SharePoint Online、OneDrive for Business、Azure Active Directory、Microsoft 团队、Dynamics 365、高级威胁防护和 Power BI。 若要审核的服务列表, 请参阅[本文的开头部分](search-the-audit-log-in-security-and-compliance.md)。

**哪些活动由 Office 365 中的审核服务进行审核？**

请参阅本文中的 "[审核的活动](#audited-activities)" 一节, 以获取 Office 365 中审核的活动的列表和说明。

**在事件发生后, 审核记录需要多长时间才能使用？**

大多数审核数据在30分钟内可用, 但在事件发生后, 可能需要长达24小时才能在搜索结果中显示相应的审核日志条目。 请参阅本文的 "[开始之前](#before-you-begin)" 一节中的表, 其中显示了不同 Office 365 服务中的事件所需的时间。

**审核记录保留多长时间？**

正如前面所述, 审核记录的保留期取决于组织的 Office 365 订阅。  

- **Office 365 E3:** 审核记录将保留90天。

- **Office 365 E5:** 审核记录还会保留90天。 保留一年的审核记录可能最终适用于拥有 E3 许可证和 Office 365 高级合规性附加许可证的 E5 用户和用户。

     > [!NOTE]
     > 如前所述, 针对 E5 组织的审核记录的为期一年的专用预览计划 (或具有高级合规性附加许可证的 E3 组织) 已关闭到新的注册。 此文章将在公开预览版中的一年保留期可用或发布以用于正式可用性时进行更新。

另请注意, 审核记录的保留期的持续时间基于每用户许可。 例如, 如果为组织中的某个用户分配了 Office 365 E3 或 E5 许可证, 则该用户执行的活动的审核记录将保留90天。

**我是否可以以编程方式访问审核数据？**

是。 Office 365 管理活动 API 用于以编程方式提取审核日志。  若要开始, 请参阅[Office 365 管理 api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)入门。

**是否有其他方法可以获取除使用安全和合规中心或 Office 365 管理活动 API 之外的审核日志？**

否。 下面是从 Office 365 审核服务中获取数据的两种方法。 

**我是否需要在每个要为其捕获审核日志的服务中单独启用审核？**

在大多数 Office 365 服务中, 在您最初为 Office 365 组织启用审核 (如本文的 "[开始之前](#before-you-begin)" 一节中所述) 后, 默认情况下将启用审核功能。

**Office 365 审核服务是否支持对记录进行重复数据消除？**

否。 审核服务管道接近实时, 因此无法支持重复数据消除。
 
**Office 365 是否跨地理位置审核数据流？**

否。 我们目前在 NA (北美)、EMEA (欧洲、中东和非洲) 和 APAC (亚太地区) 区域中审核管道部署。 但是, 我们可能会在这些区域之间传输数据以进行负载平衡, 并且仅在实时站点问题中流动。 当我们执行这些活动时, 将对传输中的数据进行加密。   
 
**审核数据是否已加密？**

审核数据存储在部署审核管道的同一区域中的 Exchange 邮箱 (静态数据) 中。 此数据不加密。 但是, 传输中的数据总是加密的。 
