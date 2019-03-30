---
title: 在安全与合规中心运行内容搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '使用安全 & 合规中心中的内容搜索来搜索邮箱、SharePoint Online 网站和 OneDrive for business 位置。 '
ms.openlocfilehash: 780a9eacc94985cf1f59993a1d5c2816474b8cb5
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000275"
---
# <a name="run-a-content-search-in-the-security--compliance-center"></a>在安全与合规中心运行内容搜索

您可以使用安全 & 合规中心中的内容搜索电子数据展示工具搜索 Office 365 组织中的项目, 如电子邮件、文档和即时消息对话。 使用此工具搜索这些 Office 365 服务中的项目:
  
- Exchange Online 邮箱和公用文件夹
    
- SharePoint Online 和 OneDrive for business 网站
    
- Skype for business 对话
    
- Microsoft Teams 
    
- Office 365 组
    
内容搜索是一个新的电子数据展示搜索工具，具有新增及改进的缩放和性能功能。 使用内容搜索运行非常大的电子数据展示搜索。 您可以在单个内容搜索中搜索所有邮箱、所有 Exchange 公用文件夹以及所有 SharePoint Online 网站和 OneDrive for business 帐户。 您可以搜索的内容位置的数量没有限制。 此外，对可以同时运行的搜索数也没有限制。 运行内容搜索之后, 内容**搜索**页的详细信息窗格中将显示内容位置数和估计的搜索结果数。 运行搜索后, 可以预览结果, 获取一个或多个搜索的关键字统计信息, 批量编辑内容搜索, 并将结果导出到本地计算机。 
  
 **内容**
  
[Create a search](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[导出搜索结果](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[Preview search results](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[更新搜索结果](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[Edit a search](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[重试搜索](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>开始之前

- 有关生成搜索查询和使用布尔搜索运算符的信息和指南, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。 本文还包含有关搜索敏感信息类型和搜索与组织内部和外部的人员共享的内容的信息。
    
- 若要访问**内容搜索**页以执行搜索和预览和导出搜索结果, 管理员、合规专员或电子数据展示管理器必须是 Security & 合规性中心中的电子数据展示管理器角色组的成员。 您无需在 Exchange online、SharePoint online 或 OneDrive for business 网站中分配其他搜索权限。 有关详细信息, 请参阅[在 Office 365 安全 & 合规中心中分配电子数据展示权限](assign-ediscovery-permissions.md)。
    
- 对内容搜索应用了限制, 以维护向 Office 365 组织提供的服务的运行状况和质量。 在大多数情况下, 不能修改这些限制, 但应了解这些限制, 以便在规划、运行和故障排除搜索时可以考虑这些限制。 有关详细信息, 请参阅[Security & 合规性中心中的搜索限制](limits-for-content-search.md)。
    
- 根据在单个内容搜索中搜索的邮箱数, 查看估计的搜索时间部分。 
    
- 如前所述, 您可以使用内容搜索来搜索 Office 365 组和 Microsoft 团队中的内容。 这意味着您可以搜索与 Office 365 组和 Microsoft 团队相关联的组邮箱、共享日历和 SharePoint 网站。 此外, 还可以在 Microsoft 团队中搜索频道对话。 有关 Office 365 组和 Microsoft 团队的信息, 请参阅:
    
  - [了解 Office 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Microsoft 团队帮助](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    有关在 Office 365 组和 Microsoft 团队中搜索内容的提示, 请参阅一节。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>Create a search
<a name="create"> </a>

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全 & 合规性中心的左侧窗格中, 单击 "**搜索** \> **内容搜索**"。
    
4. 单击 "**新建**![添加](media/O365-MDM-CreatePolicy-AddIcon.gif)图标"。
    
5. 在“新建搜索”**** 页上，键入内容搜索的名称。 此名称在组织中必须是唯一的。 
    
6. 选择要搜索的内容位置。 您可以在同一搜索中搜索邮箱、网站和公用文件夹。
    
    ![选择要搜索的内容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **搜索所有位置**选择此选项可搜索组织中的所有内容位置。 选择此选项时, 可以选择搜索所有邮箱 (包括非活动邮箱和所有 office 365 组和 Microsoft 团队的邮箱)、所有 SharePoint 和 OneDrive for business 网站 (包括所有 office 365 组的网站以及Microsoft 团队) 和所有公用文件夹。
    
    ![单击 "搜索所有位置" 选项以搜索所有内容位置](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **自定义位置选择**选择此选项可选择要搜索的邮箱和网站。 如果选择此选项, 则可以灵活地搜索特定服务 (如搜索所有 Exchange 邮箱) 的所有内容位置, 也可以搜索 Office 365 服务的特定内容位置。
    
    将内容位置添加到搜索时, 请记住以下几点:
    
    **邮箱**
    
  - 当您单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)添加图标以指定要搜索的邮箱时, 显示的邮箱选取器为空。 这种设计旨在增强性能。 若要将收件人添加到此列表, 请在搜索框中键入一个名称 (至少3个字符) ****![, 然后单击](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)"搜索搜索" 图标。
    
  - 您可以将非活动邮箱和通讯组添加到要搜索的邮箱列表中。 对于通讯组, 将搜索组成员的邮箱。 请注意, 不支持动态通讯组。
    
  - 若要获取组织中非活动邮箱的列表, 请在 Exchange Online `Get-Mailbox -InactiveMailboxOnly` PowerShell 中运行命令。 或者, 您可以转到 Security & 合规性中心中的 "**数据管理** \> "**保留**, 然后单击 "**更多**![导航栏椭圆](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非活动邮箱**"。
    
  - 您还可以添加与 Office 365 组或 Microsoft 团队相关联的邮箱。 在这种情况下, 仅搜索组或工作组邮箱;不搜索组或工作组成员的邮箱。 若要搜索这些文件, 您必须将其专门添加到搜索中。
    
  - 如果不希望在搜索中包含任何邮箱, 请选择 "**选择要搜索的特定邮箱**", 但不要将邮箱添加到列表中。
    
    **网站**
    
  - 单击 "**添加**!["](media/ITPro-EAC-AddIcon.gif)添加图标将网站添加到搜索。 键入要搜索的每个网站的 URL。 内容搜索工具将验证 URL, 然后将其添加到要搜索的网站列表中。 
    
  - 您可以添加与 Office 365 组或 Microsoft 团队相关联的 SharePoint。 有关如何查找组或团队的 URL 的指南, 请参阅一节。 
    
  - 如果不希望在搜索中包含任何网站, 请选择 "**选择要搜索的特定网站**", 但不要向列表中添加网站。
    
    **公用文件夹**
    
    对于公用文件夹, 您可以选择搜索 Exchange Online 组织中的所有公用文件夹, 或者不搜索任何公用文件夹。
    
7. 单击“下一步”。****
    
8. 在 "**新建搜索**" 页上, 您可以添加关键字和条件来创建搜索查询。 
    
    ![使用关键字和条件创建搜索查询](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. 在“您想要我们查找哪些内容”**** 下的框中，键入搜索查询。 您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。 您可以使用更复杂的查询, 这些查询使用布尔运算符, 例如**AND**、 **or**、 **NOT**、 **NEAR**或**ONEAR**。 您还可以在文档中搜索敏感信息 (如社会保险号), 或搜索在外部共享的文档。 如果将 "关键字" 框留空, 则位于指定内容位置的所有内容都将包含在搜索结果中。 
    
2. 您可以单击 "**显示关键字列表**" 复选框, 然后在每行中键入关键字。 如果执行此操作, 则每行上的关键字通过所创建的搜索查询中的**OR**运算符进行连接。 
    
    ![您可以在关键字列表的行中键入关键字或关键字阶段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    为什么要使用关键字列表？ 您可以获取显示与每个关键字匹配的项目数的统计信息。 这可以帮助您快速确定哪些关键字最有效 (最少)。 您还可以在行中使用关键字短语 (括在括号中)。 有关搜索统计信息的详细信息, 请参阅[查看内容搜索结果的关键字统计](view-keyword-statistics-for-content-search.md)信息。
    
    有关使用关键字列表的指南, 请参阅一节。 
    
3. 单击 "**检查查询以查找打字错误**" 以检查查询是否有不受支持的字符以及可能不大写的布尔运算符。 不受支持的字符通常是隐藏的, 通常会导致搜索错误或返回意外的结果。 有关检查不受支持的字符的详细信息, 请参阅[检查内容搜索查询是否有错误](check-your-content-search-query-for-errors.md)。
    
4. 在 "**条件**" 下, 向搜索查询添加条件以缩小搜索范围, 并返回一组更细化的结果。 每个条件都可以将一个子句添加到 KQL 搜索查询中，该搜索查询会在开始搜索时进行创建并运行。 条件在逻辑上通过 **AND** 运算符连接到关键字查询（在关键字框中指定）。 这意味着，项目必须满足关键字查询和要在结果中包括的条件。 这就是条件如何帮助缩小结果范围的原理。 
    
||
|:-----|
|有关创建搜索查询和使用条件的详细信息, 请参阅[用于内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。 |
   
9. 单击****“搜索”保存搜索设置，然后启动搜索。 
    
    搜索即启动。 搜索完成后, 详细信息窗格中将显示以下信息。
    
    ![搜索统计信息显示在所选内容搜索的细节窗格中](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. 上次运行搜索的日期和时间。
    
2. 找到的与搜索查询匹配的项目的数量 (以及总大小)。 项目类型的示例包括电子邮件、日历项和文档。 如果某个项目包含要搜索的关键字的多个实例, 则仅在总项目数中计算一次。 例如, 如果您搜索词 "股价" 或 "tip", 并且电子邮件包含 "stock" 一词的三个实例, 则在 "**项目**" 字段中只计算一次。 
    
3. 搜索的内容位置中未编制索引的项目的数量和总大小。 不符合搜索条件的未编制索引项目数将包含在详细信息窗格中显示的搜索统计信息中。 如果未编制索引的项目与搜索查询相匹配 (因为其他邮件或文档属性满足搜索条件), 则不会将其包含在未编制索引项目的估计数量中。 但是, 如果搜索条件排除未编制索引的项目, 则不会将其包含在未编制索引的项目的估计中。
    
4. 搜索的每个类型的内容位置的数目。 对于邮箱, 请注意, 存档邮箱包含在搜索的邮箱总数中。 在上面的示例中, 搜索了四个用户邮箱, 并为每个用户启用了存档邮箱。 这就是为什么在搜索统计信息中引用八个邮箱的原因。
    
5. 指向预览搜索结果或再次运行搜索以更新搜索统计信息的链接。
    
    如有必要, ****![请单击 "](media/O365-MDM-Policy-RefreshIcon.gif)刷新刷新" 图标以更新所选搜索的详细信息窗格中的信息。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>导出搜索结果
<a name="export"> </a>

成功运行搜索后, 可以将搜索结果导出到本地计算机。 导出电子邮件结果时, 会将其作为 PST 文件下载到您的计算机上。 当您从 SharePoint 和 OneDrive for business 网站导出内容时, 会导出本机 Office 文档的副本。 导出的搜索结果中还包含其他文档和报告。 有关详细信息, 请参阅[从 Security & 合规中心导出搜索结果](export-search-results.md)。
  
## <a name="preview-search-results"></a>预览搜索结果
<a name="preview"> </a>

成功完成搜索后，可以预览搜索结果。 与预览内容搜索结果相关的限制有很多。 有关详细信息, 请参阅[Security & 合规性中心中的搜索限制](limits-for-content-search.md)。 请注意, 未编制索引的项目不能进行预览。
  
1. 在 "**内容搜索**" 页上, 选择 "搜索"。 
    
2. 在详细信息窗格中的“结果”下****，单击“预览搜索结果”****。****“预览搜索结果”页面随即打开，并且包含搜索结果项目列表。 
    
    您可以单击一个列标题, 根据主题、类型、发件人或在源邮箱中接收项目的日期对结果进行排序。
    
3. 单击要预览的项目。
    
    项目在预览窗格中打开。
    
4. 如果文件类型不支持预览或下载文档的副本, 则可以单击 "**下载原始文件**" 将其下载到本地计算机。 对于 .aspx 网页, 如果您可能没有访问该页面的权限, 则会包含该页面的 URL。 
    
> [!NOTE]
> 如果您要预览 7 天之前运行的上一次搜索的搜索结果，系统将提示您更新搜索结果。 将重新运行搜索, 以获取最新符合搜索查询的结果。 
  
### <a name="file-types-that-can-be-previewed"></a>可预览的文件类型

您可以在预览窗格中预览受支持的文件类型。 如果文件类型不受支持, 则必须将该文件的副本下载到本地计算机以进行查看。 支持以下文件类型, 并且可以在 "**预览搜索结果**" 页上预览这些文件类型。 
  
- .txt、.html、mhtml
    
- .eml
    
- .doc、.docx、. .docm
    
- . .pptm、.pptx
    
- .pdf
    
此外, 还支持以下文件容器类型。 您可以在预览窗格中查看容器中的文件列表。
  
- .zip
    
- gzip
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>更新搜索结果
<a name="restart"> </a>

当您更新现有内容搜索的结果时, 将在所有指定的内容位置上重新运行搜索查询。 更新搜索结果的一个显而易见的原因是要获取最新的数据。
  
1. 在 "**内容搜索**" 页上, 选择要更新其结果的搜索。 
    
2. 在详细信息窗格中的“结果”**** 下，单击“更新搜索结果”****。
    
    将显示状态消息，指出正在检索结果。 完成搜索后，更新的信息将显示在详细信息窗格中的“结果”**** 下。 请注意，详细信息窗格中的“搜索时间”**** 字段中的日期将更新为当前日期和时间。 若要刷新内容搜索列表中的信息, 请单击 "**刷新**![刷新](media/O365-MDM-Policy-RefreshIcon.gif)" 图标。
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>编辑搜索
<a name="edit"> </a>

您可以更改源邮箱和现有内容搜索的搜索查询。
  
1. 在 "**内容搜索**" 页上, 选择 "搜索"。 
    
2. 在详细信息窗格中的“查询”下****，单击“编辑搜索”****。
    
3. 在 "**位置**" 页上, 您可以更改要搜索的邮箱、组、SharePoint 网站或 OneDrive for business 网站。 您还可以选择 (或取消选择) 以搜索 Exchange 中的所有公用文件夹。 
    
4. 在 "**查询**" 页上, 您可以编辑搜索查询。 
    
5. 若要启动修改后的搜索, 请在 "**源**" 或 "**位置**" 页上单击 "**搜索**"。 
    
    修改后的搜索即启动。 搜索完成后, 详细信息窗格中将显示修订搜索的估计结果。
    
## <a name="retry-a-search"></a>重试搜索
<a name="retry"> </a>

如果搜索返回任何错误, 则无需重新搜索所有内容位置。 您可以重新运行搜索, 以便仅搜索失败的内容位置。 若要重新搜索所有内容位置, 可以更新搜索结果。
  
1. 在 "**内容搜索**" 页上, 选择包含要重新搜索的内容位置的搜索。 
    
2. 在详细信息窗格中的 "**错误**" 下, 单击 "**重试搜索**"。
    
    将显示状态消息，指出正在检索结果。 完成搜索后，更新的信息将显示在详细信息窗格中的“**结果**”下。 请注意，详细信息窗格中的“**搜索时间**”字段中的日期将更新为当前日期和时间。 若要刷新搜索列表中的信息, 请单击 "**刷新**![刷新](media/O365-MDM-Policy-RefreshIcon.gif)" 图标。
    
[返回顶部](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>详细信息
<a name="moreinfo"> </a>

以下是有关内容搜索的详细信息。
  
[限制和性能](#limits-and-performance)
  
[未编制索引的项目](#unindexed-items) 
 
[Microsoft 团队和 Office 365 组](#microsoft-teams-and-office-365-groups)
  
[OneDrive for Business](#onedrive-for-business)
  
[搜索查询](#search-queries)
  
[搜索非活动邮箱](#searching-inactive-mailboxes)
  
[其他](#miscellaneous)
  
[Return to top](#before-you-begin)
  
### <a name="limits-and-performance"></a>限制和性能
  
- 有关应用于内容搜索功能的限制的说明, 请参阅[Security & 合规性中心中的搜索限制](limits-for-content-search.md)。
    
- Microsoft 收集由所有 Office 365 组织运行的内容搜索的性能信息。 虽然搜索查询的复杂性可能会影响搜索时间, 但影响搜索所用时间的最大因素是搜索的邮箱数。 尽管 Microsoft 不提供搜索时间的服务级别协议, 但下表根据搜索中包括的邮箱数量列出了内容搜索的平均搜索时间。
    
|**邮箱数**|**平均搜索时间**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45秒  <br/> |
|10,000  <br/> |4 分钟  <br/> |
|25000  <br/> |10 分钟  <br/> |
|50000  <br/> |20 分钟  <br/> |
|100,000  <br/> |25 分钟  <br/> |
   
  
### <a name="unindexed-items"></a>未编制索引的项目
  
- 如前所述, 搜索的内容位置中的未编制索引的项目包含在估计的搜索结果中。 如果未编制索引的项目与搜索查询相匹配 (因为其他邮件或文档属性满足搜索条件), 则不会将其包含在未编制索引项目的估计数量中。 如果搜索条件排除未编制索引的项目, 则它也不会包含在估计的未编制索引项目数中。 有关详细信息，请参阅[Unindexed items in Content Search](https://go.microsoft.com/fwlink/p/?LinkId=780739)。
    

  
### <a name="microsoft-teams-and-office-365-groups"></a>Microsoft 团队和 Office 365 组
  
- Microsoft 团队基于 Office 365 组构建。 因此, 搜索它们非常相似。 在 Microsoft 团队和 Office 365 组中搜索内容时, 请记住以下事项。
    
  - 若要搜索位于 Microsoft 团队和 Office 365 组中的内容, 您必须指定与团队或组相关联的邮箱和 SharePoint 网站。
    
  - 在 Exchange Online 中运行**remove-unifiedgroup** cmdlet, 以查看 Microsoft 团队或 Office 365 组的属性。 如果要获取与团队或组相关联的网站的 URL, 这是一种很好的方法。 例如, 以下命令将显示名为 "高级领导" 团队的 Office 365 组的选定属性: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 若要运行**remove-unifiedgroup** cmdlet, 您必须在 Exchange Online 中分配 "仅查看收件人" 角色, 或者是分配了 "仅查看收件人" 角色的角色组的成员。 
  
  - 在搜索用户的邮箱时, 不会搜索用户是其成员的任何 Microsoft 团队或 Office 365 组。 同样, 当您搜索 Microsoft 团队或 Office 365 组时, 仅搜索您指定的组邮箱和组网站;除非将组成员的邮箱和 OneDrive for business 帐户显式添加到搜索中, 否则不会搜索这些帐户。
    
  - 若要获取 microsoft 团队或 Office 365 组成员的列表, 您可以在 Microsoft 365 管理中心的 "**家庭\>组**" 页上查看属性。 或者, 您可以在 Exchange Online PowerShell 中运行以下命令: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 若要运行**UnifiedGroupLinks** cmdlet, 您必须在 Exchange Online 中分配 "仅查看收件人" 角色, 或者是分配了 "仅查看收件人" 角色的角色组的成员。 
  
  - 属于 microsoft 团队渠道的对话存储在与 microsoft 团队相关联的邮箱中。 同样, 在频道中共享的工作组成员的文件存储在团队的 SharePoint 网站上。 因此, 您必须将 Microsoft 团队邮箱和 SharePoint 网站添加为内容位置, 以便在频道中搜索对话和文件。
    
  - 
    
    或者, 在 Microsoft 团队中作为聊天列表一部分的对话存储在参与聊天的用户的 Exchange Online 邮箱中。 以及用户在聊天对话中共享的文件存储在共享该文件的用户的 OneDrive for business 帐户中。 因此, 您必须将单个用户邮箱和 OneDrive for business 帐户添加为在聊天列表中搜索对话和文件的内容位置。
    
    > [!NOTE]
    > 参与在 Microsoft 团队中作为聊天列表一部分的对话的用户必须具有 Exchange Online (基于云的) 邮箱, 您才能搜索对话对话。 这是因为聊天列表中的对话存储在聊天参与者的基于云的邮箱中。 如果聊天参与者没有 Exchange Online 邮箱, 将无法搜索对话对话。 例如, 在 Exchange 混合部署中, 具有本地邮箱的用户可能能够参与属于 Microsoft 团队中的聊天列表的对话。 但是在这种情况下, 无法搜索这些对话中的内容, 因为用户不具有基于云的邮箱。 
  
  - 每个 Microsoft 团队或团队频道都包含用于笔记记录和协作的 Wiki。 Wiki 内容将自动保存到格式为 .mht 的文件中。 此文件存储在团队的 SharePoint 网站上的 "团队 Wiki 数据" 文档库中。 您可以使用内容搜索工具来搜索 Wiki, 具体方法是将团队的 SharePoint 网站指定为要搜索的内容位置。 
    
    > [!NOTE]
    > 在 Microsoft 团队或频道中搜索 Wiki 的功能 (在搜索团队的 SharePoint 网站时) 在2017年6月22日发布。 在该日期或之后保存或更新的 Wiki 页面可供搜索。 上次保存或更新的 Wiki 页面在该日期不可用于搜索之前。 
  
### <a name="onedrive-for-business"></a>OneDrive for Business
  
- 若要收集组织中的 onedrive for business 网站的 url 列表, 请参阅[创建组织中所有 onedrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。 本文中的脚本创建一个文本文件, 其中包含所有 OneDrive for business 网站的列表。 若要运行此脚本, 您必须安装并使用 SharePoint Online 命令行管理程序。 请务必将组织的 "我的网站" 域的 URL 追加到要搜索的每个 OneDrive for business 网站。 这是包含所有 OneDrive for business 的域;例如, `https://contoso-my.sharepoint.com`。 下面的示例展示了用户的 OneDrive for business 网站的 URL: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    

### <a name="search-queries"></a>搜索查询
  
- 在使用关键字列表创建搜索查询时, 请记住以下事项。
    
  - 您必须选择 "**显示关键字列表**" 复选框, 然后在单独的行中键入每个关键字, 以创建搜索查询, 在该查询中, 每行中的关键字 (或关键字短语) 通过**or**运算符连接。 如果只是将关键字列表粘贴到关键字框中或在键入关键字后按**enter**键, 则不会通过**or**运算符连接。 下面是添加关键字列表的错误和正确示例。 
    
    **不正确**
    
    ![设置关键字列表格式的错误方法 (通过将列表粘贴到关键字框中)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **正确**
    
    ![设置关键字列表格式的正确方法 (通过选中 "checkbox" 和 "粘贴" 列表)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - 您还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语列表, 然后将列表复制并粘贴到关键字列表中。 若要执行此操作, 必须选中 "**显示关键字列表**" 复选框。 然后, 单击 "关键字" 列表中的第一行并粘贴列表。 Excel 或文本文件中的每一行将粘贴到关键字列表中单独的行中。 
    
  - 使用关键字列表创建查询之后, 最好验证搜索查询语法 (在所选搜索的细节窗格中), 以使搜索查询成为您预期的结果。 在 "详细信息" 窗格的 "**查询**" 下显示的搜索查询中, 关键字由文本 **(c:s)** 分隔。 这表示关键字是通过**OR**运算符连接的。 同样, 如果您的搜索查询包含条件, 关键字和条件由文本 **(c:c)** 分隔。 这表示关键字通过**and**运算符连接到条件。 下面的示例展示了在使用关键字列表和条件时生成的搜索查询 (在详细信息窗格中)。 
    
    ![使用关键字列表和条件时创建的查询示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - 如果您有包含非英语字符关键字的搜索查询 (如中文字符), 则您可能必须使用**new-compliancesearch** cmdlet 配置内容搜索的语言属性。 当您使用安全 & 合规中心中的 GUI 创建内容搜索时, 默认语言是非特定语言。 
    
    如何判断是否需要更改内容搜索的语言设置？ 如果您是某些内容位置包含您要搜索的非英语字符, 但搜索不返回任何结果, 则可能是语言设置可能导致的原因。
    
    若要更改现有内容搜索的语言设置, 请在 Security & 合规性中心 PowerShell 中运行以下命令:
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    例如, 若要将语言设置更改为中文, 应使用`zh-CN`区域性代码值。 更改语言设置后, 必须重新运行搜索。 有关可能的区域性代码值的列表, 请参阅[CultureInfo 类](https://go.microsoft.com/fwlink/p/?LinkID=184859)。 对于内容搜索, 我们建议您对语言设置的值使用两部分区域性代码;例如, `ja-JP`而不`ja`是。
    

### <a name="searching-inactive-mailboxes"></a>搜索非活动邮箱
  
如前所述, 您可以在内容搜索中搜索非活动邮箱。 以下是在搜索非活动邮箱时要牢记的一些事项。
  
- 如果内容搜索包括用户邮箱, 并且该邮箱随后变为非活动状态, 则当您在搜索变为非活动状态后重新运行该搜索时, 内容搜索将继续搜索非活动邮箱。
    
- 在某些情况下, 用户可能有一个活动邮箱和一个具有相同 SMTP 地址的非活动邮箱。 在这种情况下, 将仅搜索您选择作为内容搜索的位置的特定邮箱。 换句话说, 如果将用户的邮箱添加到搜索, 则不能假定将搜索其活动邮箱和非活动邮箱;将仅搜索您显式添加到搜索中的邮箱。
    
- 强烈建议您避免使用相同 SMTP 地址的活动邮箱和非活动邮箱。 如果需要重用当前分配给非活动邮箱的 SMTP 地址, 我们建议您恢复非活动邮箱或将非活动邮箱的内容还原到活动邮箱 (或活动邮箱的存档) 中, 然后删除非活动邮箱。 有关详细信息, 请参阅下列主题之一:
    
  - [在 Office 365 中恢复非活动邮箱](recover-an-inactive-mailbox.md)
    
  - [在 Office 365 中还原非活动邮箱](restore-an-inactive-mailbox.md)
    
  - [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)
    
### <a name="miscellaneous"></a>其他
  
- 在安全 & 合规中心中的 "**内容搜索**" 页上创建的内容搜索不会显示在 Exchange 管理中心中的 "**就地电子数据展示&amp;保留**" 页上。 这是因为在 Security & 合规性中心中创建的内容搜索体系结构和搜索对象与 Exchange Online 中的就地电子数据展示功能完全不同。 
    
    出于相同的原因, 在 "安全 & 合规中心" 的电子数据展示事例的 "**搜索**" 页上不会显示在 "**内容搜索**" 页上创建的搜索。 
    
- 重新启动和重试搜索之间的区别是什么？ 重新启动搜索时, 将会在新的预览搜索中再次搜索在搜索中指定的所有内容位置。 但是, 当您重试搜索时, 将再次搜索上次运行搜索时失败的内容位置。
   

