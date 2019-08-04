---
title: Office 365 中的内容搜索
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
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 使用 Office 365 或 Microsoft 365 合规中心中的内容搜索工具搜索邮箱、SharePoint Online 网站、OneDrive 帐户、Microsoft Teams、Office 365 组 和 Skype for Business 对话中的内容。 可以使用关键字搜索查询和搜索条件来缩小搜索结果。 然后预览并导出搜索结果。 内容搜索也是一款有效的工具，可用于搜索与 GDPR 数据主题请求相关的内容。
ms.openlocfilehash: 3df1ee02cc7b31a8dd316bac5ccd4455c26922c5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048184"
---
# <a name="content-search-in-office-365"></a>Office 365 中的内容搜索

可以使用 Office 365 或 Microsoft 365 合规中心中的内容搜索电子数据展示工具来搜索相应的项，例如电子邮件、文档和 Office 365 组织中的即时消息对话。 使用此工具搜索以下 Office 365 服务中的项：
  
- Exchange Online 邮箱和公共文件夹
    
- SharePoint Online 网站和 OneDrive for Business 帐户
    
- Skype for Business 对话
    
- Microsoft Teams 
    
- Office 365 组
    
运行内容搜索后，内容位置的数量和搜索结果的估计数量将会显示在搜索配置文件中。 还可以快速查看统计信息，例如具有与搜索查询匹配的项的内容位置。 运行搜索后，可预览结果或将其导出到本地计算机。

## <a name="create-a-search"></a>创建搜索

若要访问**内容搜索**页面以运行搜索和预览并导出搜索结果，管理员、合规专员或电子数据展示管理者必须是安全与合规中心的电子数据展示管理者角色组中的成员。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
  
1. 转至 [https://protection.office.com](https://protection.office.com) 并使用 Office 365 电子邮件地址和密码登录。
    
2. 单击“**搜索**”\>“**内容搜索**”。
    
3. 在“**搜索**”页面，单击“![添加](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)”图标“**新建搜索**”旁边的箭头。 
    
    ![“新建搜索”下拉列表](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    可以选择以下选项之一：
    
    - **引导式搜索 — 选择此选择将会启动一个向导，用于指导你创建搜索。 用于选择内容位置和构建搜索查询的用户界面与“**新建搜搜**”选项相同。 
    
    - **新建搜索** – 选择此选项将显示一个用于创建搜索的更新用户界面。 如果单击“**新建搜索**”，则此选项为默认选项。
    
    - **按 ID 列表搜索** – 选择此选项使你可以使用 Exchange ID 列表搜索特定电子邮件消息和其他邮箱项。 若要创建 ID 列表搜索（先前称为定向搜索），你可以提交一个用于标识要搜索的特定邮箱项的逗号分隔符值 (CSV) 文件。 有关说明，请参阅[为 Office 365 中的 ID 列表内容搜索准备 CSV 文件](csv-file-for-an-id-list-content-search.md)。
    
    此流程的其余步骤遵循默认的新建搜索工作流。
    
4. 在下拉列表中单击“**新建搜索**”。 
    
5. 在“**搜索查询**”下，指定以下内容：
    
    ![指定要搜索的关键字、条件和位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **要搜索的关键字** – 在“**关键字**”框中键入搜索查询。 您可以指定关键字、邮件属性（例如发送和接收日期）或文档属性（例如文件名或上次更改文档的日期）。 可以使用采用布尔运算符的更复杂查询，例如 **AND**、**OR**、**NOT** 和 **NEAR**。 还可以搜索文档中的敏感信息（如社会保险号），或者搜索已外部共享的文档。 如果将关键字框留空，则指定内容位置中的所有内容都将包括在搜索结果中。
    
      或者，可以单击“**显示关键字列表**”复选框，然后在每一行键入一个关键字。 如果执行此操作，则每行上的关键字将由逻辑运算符连接 (**c:s**)，类似于所创建的搜索创建中的 **OR** 运算符功能。 
    
      为什么使用关键字列表？ 可以获取与每个关键字匹配的项数量的统计信息。 这可以帮助你快速标识哪些关键字最有效和最无效。 还可以在行中使用关键字短语（使用括号包围）。 有关搜索统计信息的更多信息，请参阅[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。

     > [!NOTE]
     > 为了帮助减少因海量关键字列表导致的问题，现在，已将关键字列表中的最大行数限制为 20 行。
    
    - **条件** – 可以添加搜索条件来缩小搜索范围并返回更精确的结果集。 每个条件向开始搜索时创建和运行的搜索查询添加一个子句。 可通过使用功能类似于 **AND** 运算符的逻辑运算符 (**c:c**) 在逻辑上将条件连接至关键字查询（在关键字框中指定）。 这意味着，项必须满足关键字查询和要在结果中包括的一个或多个条件。 这就是条件如何帮助缩小结果范围的原理。 有关可以在搜索查询中使用的条件列表和描述，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的“搜索条件”部分。
    
       - **位置** – 选择要搜索的内容位置。
    
      - **所有位置** – 使用此选项搜索组织中的所有内容位置。 这包括所有 Exchange 邮箱中的电子邮件（包括所有非活动邮箱、所有 Office 365 组邮箱、所有 Microsoft Teams 邮箱）、所有 Skype for Business 对话、所有 SharePoint 和 OneDrive for Business 网站（包括所有 Office 365 组和 Microsoft Teams 网站）以及所有 Exchange 公共文件夹中的项。
    
      - **特定位置** – 使用此选项搜索特定内容位置。 可以搜索特定 Office 365 服务的所有内容位置（例如搜索所有 Exchange 邮箱或搜索所有 SharePoint 网站），或者在显示的任何 Office 365 服务中的特定位置。 
    
        ![用于选择要搜索的内容位置的用户界面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         还可以将通讯组添加至要搜索的 Exchange 邮箱列表中。 对于通讯组，将搜索组成员的邮箱。 不支持动态通讯组。
    
       > [!NOTE]
       > 搜索所有邮箱位置或仅特定邮箱，导出内容搜索结果时，保存至用户邮箱的其他 Office 365 应用程序数据将包括在内。 此数据将不会包括在估计的搜索结果中，并且也不可用于预览。 导入和下载搜索结果时，此数据将包括在内。 有关详细信息，请参阅 [Exchange Online 邮箱中存储的内容](what-is-stored-in-exo-mailbox.md)。

    
6. 设置搜索查询之后，请单击“**保存并返回**”。
    
7. 在“**保存搜索**”页面上，键入搜索名称以及帮助标识搜索的可选描述。 搜索名称在你的组织中必须保持唯一。 
    
8. 单击“**保存**”以开始搜索。 
    
    保存并运行搜索之后，搜索返回的任何结果都将会显示在结果窗格中。 搜索结果将会显示或者需要单击“**预览结果**”才能查看它们，具体取决于所配置的预览设置。 有关详细信息，请参阅下一节。 
    
若要再次访问此内容搜索或者访问“**内容搜索**”页面上列出的其他内容搜索，请选择搜索，然后单击“**打开**”。 
  
若要清除结果或者创建其他搜索，请单击“![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)”“**新建搜索**”。 

  
## <a name="preview-search-results"></a>预览搜索结果

具有两种预览搜索结果配置设置。 运行新搜索或者打开现有搜索之后，请单击 **单独的结果** 以查看以下预览设置： 
  
![预览搜索结果设置](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **自动预览结果** – 此设置将在运行搜索之后显示搜索结果。
    
2. **手动预览结果** – 此设置将在搜索结果窗格中显示占位符，并显示“**预览结果**”按钮，必须单击此按钮才能显示搜索结果。 这是默认设置。 这有助于增强搜索性能，因为它不会在你打开现有搜索时自动显示搜索结果。 
    
可供预览的项数量具有限制。 有关详细信息，请参阅[内容搜索限制](limits-for-content-search.md)。 
  
有关可预览的受支持文件类型列表，请参阅“有关内容搜索的详细信息”部分的[预览搜索结果](#previewing-search-results)。 如果文件类型不支持预览或者下载文档副本，则可以单击“**下载原始文件**”以将其下载到本地计算机。 对于 .aspx Web 页面，尽管你可能没有访问该页面的权限，但该页面的 URL 将包括在内。 
  
另请注意，未编入索引的项不提供预览。
  
## <a name="view-information-and-statistics-about-a-search"></a>查看与搜索相关的信息和统计信息

创建并运行内容搜索之后，可以查看与估计的搜索结果相关的统计信息。 其中包括搜索结果摘要、查询统计信息（如与搜索查询匹配的项内的内容位置数）以及具有最多匹配项的内容位置的名称。 可以显示一个或多个内容搜索的统计信息。 你可以通过它快速比较多个搜索的结果，并确定搜索查询的有效性。
  
还可以将搜索统计信息和关键字统计信息下载为 CSV 文件。 此操作使你能够使用 Excel 中的筛选和排序功能来比较结果，并准备搜索结果报告。
  
若要查看搜索统计信息：
  
1. 在“**内容搜索**”页面上，单击“**打开**”，然后单击想要查看其统计信息的搜索。 
    
2. 在浮出页面上，单击“**打开查询**”。 
    
3. 在“**单独的结果**”下拉列表中，单击“**搜索配置文件**”。
    
4. 在“**类型**”下拉列表中，根据想要查看的搜索统计信息单击以下选项之一。 
    
  - **摘要** – 显示所搜索的每种内容位置类型的统计信息。 这包括包含与搜索查询匹配的项的内容位置数，以及搜索结果项的总数和大小。 这是默认设置。
    
  - **查询** – 显示与搜索查询相关的统计信息。 这包括查询统计信息所适用的内容位置类型、统计信息所适用的搜索查询部分（请注意，“**主要**”表示整个搜索查询）、包含与搜索查询匹配的项的内容位置数量以及与搜索查询匹配（在指定内容位置）的项总数和大小。 还会显示与未编入索引的项的统计信息（也称为“*部分索引项*）。 但是，只有邮箱中的部分索引项将会包括在统计信息中。 SharePoint 和 OneDrive 中的部分索引项不会包括在统计信息中。
    
  - **热门位置** – 显示与每个内容位置中的搜索查询匹配的项数量。 将会显示前 1,000 个位置。
    
有关搜索统计信息的详细信息，请参阅[查看内容搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。
  
  
## <a name="export-search-results"></a>导出搜索结果

成功运行搜索之后，你可以将搜索结果导出至本地计算机。 导出电子邮件结果时，它们将以 PST 文件或单独邮件的形式下载到你的计算机。 当你从 SharePoint 和 OneDrive 网站导出内容时，将导出本地 Office 文档副本。 导出的搜索结果中还包含其他文档和报告。 也可以导出搜索结果报告，而不是实际项。
  
若要导出搜索结果：
  
1. 在“**内容搜索**”页面上，单击想要导出其搜索结果的搜索。 
    
2. 在浮出页面上，单击“![导出搜索结果](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)”图标“**更多**”，然后单击“**导出结果**”。 还可以导出搜索结果报告。
    
3. 完成“**导出结果**”浮出页面上的部分。 请务必使用滚动条查看所有导出选项。 
    
有关更多详细说明和疑难解答提示，请参阅:
  
- [导出内容搜索结果](export-search-results.md)
    
- [导出内容搜索报告](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>有关内容搜索的详细信息

请参阅以下各部分，以获取与内容搜索相关的详细信息。
  
[内容搜索限制](#content-search-limits)
  
[构建搜索查询](#building-a-search-query)
  
[搜索 OneDrive 帐户](#searching-onedrive-accounts)
  
[搜索 Microsoft Teams 和 Office 365 组](#searching-microsoft-teams-and-office-365-groups)
  
[搜索非活动邮箱](#searching-inactive-mailboxes)
  
[预览搜索结果](#previewing-search-results)
  
[部分索引项](#partially-indexed-items)
  
### <a name="content-search-limits"></a>内容搜索限制

- 有关适用于内容搜索功能的限制的说明，请参阅[内容搜索限制](limits-for-content-search.md)。
    
- Microsoft 将会收集所有 Office 365 组织运行的内容搜索性能信息。 尽管搜索查询的复杂性可能会影响搜索项，但是影响搜索所需时长的最大因素仍然是搜索的邮箱数。 尽管 Microsoft 未为搜索时间提供服务级别协议，但是下表根据搜索中所含的邮箱数列出了内容搜索的平均搜索时间。
    
|**邮箱数**|**平均搜索时间**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4 分钟  <br/> |
|25,000  <br/> |10 分钟  <br/> |
|50,000  <br/> |20 分钟  <br/> |
|100,000  <br/> |25 分钟  <br/> |
  
### <a name="building-a-search-query"></a>构建搜索查询

有关创建搜索查询、使用布尔搜索运算符和搜索条件以及搜索敏感信息类型及与组织外部用户共享的内容的详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md)。
  
使用关键字列表创建搜索查询时，请注意以下内容。
  
- 必须选中“**显示关键字列表**”复选框并在单独行中键入每个关键字，才能创建每行中的关键字以 **OR** 运算符连接的搜索查询。 如果将关键字列表粘贴至关键字框或者在键入关键字之后按 **Enter** 键，则它们将不会以 **OR** 运算符连接。 以下是添加关键字列表的错误和正确示例。 
    
    **错误**
    
    ![设置关键字列表格式的不正确方式（通过将列表粘贴至关键字框）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **正确**
    
    ![设置关键字列表格式的正确方式（在选中复选框后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- 还可以在 Excel 文件或纯文本文件中准备关键字或关键字短语列表，然后将你的列表复制粘贴至关键字列表。 若要执行此操作，你必须选中“**显示关键字列表**”复选框。 然后，单击关键字列表中的第一行并粘贴你的列表。 Excel 或文本文件中的每一行均会粘贴至关键字列表中的单独行中。 
    
- 使用关键字列表创建查询后，最好验证搜索查询语法，确保搜索查询适合你的需求。 在详细信息窗格的“**查询**”下显示的搜索查询中，关键字将以文本 **(c:s)** 分隔。 这表示关键字由功能类似于 **OR** 运算符的逻辑运算符连接。 同样，如果搜索查询中包含条件，则关键字和条件将以 **(c:c)** 分隔。 这表示关键字由功能类似于 **AND** 运算符的逻辑运算符连接到条件。 以下是使用关键字列表和条件时创建的搜索查询（显示在详细信息窗格中）示例。 
    
    ![使用关键字列表和条件时创建的查询示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- 运行内容搜索时，Office 365 将会自动检查搜索查询中是否存在不受支持的字符以及未大写的布尔运算符。 不受支持的字符往往会被隐藏，并且通常会引发搜索错误或者返回意外结果。 有关检查到的不受支持字符的详细信息，请参阅[检查内容搜索查询中是否存在错误](check-your-content-search-query-for-errors.md)。
    
- 如果搜索查询中包含非英语字符（例如中文字符）关键字，则可以单击“**查询语言-国家/地区**”“![内容搜索中的查询语言-国家/地区](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)”并为该搜索选择语言-国家/地区文化代码值。 默认语言/区域是中性的。 如何判断是否需要更改内容搜索的语言设置？ 如果确定要搜索的内容位置包含非英语字符，但搜索没有返回结果，则可能是语言设置的原因。 
  
### <a name="searching-onedrive-accounts"></a>搜索 OneDrive 帐户

- 若要收集组织中的 OneDrive 网站 URL 列表，请参阅[在组织中创建所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。 本文中的脚本将创建包含所有 OneDrive 网站的文本文件。 若要运行此脚本，必须安装并使用 SharePoint Online Management Shell。 请务必将你组织的 MySite 域的 URL 附加到你想要搜索的每个 OneDrive 网站。 这是包含你所有的 OneDrive 的域；例如，`https://contoso-my.sharepoint.com`。 下面是用户的 OneDrive 网站的 URL示例：`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    
    在少数用户主体名称 (UPN) 发生更改的情况下，OneDrive 位置的 URL 将发生更改，以包含新的 UPN。 如果发生这种情况，则必须通过添加用户的新 OneDrive URL 并删除旧 URL 来修改内容搜索。
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>搜索 Microsoft Teams 和 Office 365 组

可以搜索与 Office 365 组或 Microsoft Teams 关联的邮箱。 Microsoft Teams 构建于 Office 365 组之上，因此，搜索方法类似。 在这两种情况下，只会搜索组或团队邮箱。 不会搜索组或团队成员的邮箱。 若要搜索它们，必须将它们专门添加到搜索中。
  
搜索 Microsoft Teams 和 Office 365 组中的内容时，请注意以下内容。
  
- 若要搜索 Teams 和 Office 365 组中的内容，必须指定与团队或组关联的邮箱和 SharePoint 网站。
    
- 在 Exchange Online 中运行 **Get-UnifiedGroup** cmdlet，以查看团队或 Office 365 组的属性。 这是一种获取与团队或组关联的网站 URL 的好方法。 例如，以下命令显示名为高层领导团队的 Office 365 组的选定属性： 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroup** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。 
  
- 搜索用户邮箱时，不会搜索用户是其成员的任何团队或 Office 365 组。 类似地，在搜索团队或 Office 365 组时，只会搜索指定的组邮箱和组网站。 不会搜索组成员的邮箱和 OneDrive for Business 帐户，除非你将其显式添加到搜索中。
    
- 若要获取团队或 Office 365 组的成员列表，则可以查看 Microsoft 365 管理中心 **“主页”“\>组**”页面上的属性。 或者，可以在 Exchange Online PowerShell 中运行以下命令： 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 若要运行 **Get-UnifiedGroupLinks** cmdlet，则你必须在 Exchange Online 中分配有仅查看收件人角色或者是分配有仅查看收件人角色的角色组的成员。 
  
- 属于 Teams 渠道的对话将存储在与团队关联的邮箱中。 同样，团队成员在渠道中共享的文件将存储在团队的 SharePoint 网站上。 因此，必须将团队邮箱和 SharePoint 网站作为内容位置添加到搜索渠道中的对话和文件。
    
- 或者，属于 Teams 中聊天列表的对话将存储在参与该聊天的用户的 Exchange Online 邮箱中。 用户在聊天对话中共享的文件将存储在共享该文件的用户的 OneDrive for Business 帐户中。 因此，必须将单独的用户邮箱和 OneDrive for Business 帐户作为内容位置添加到聊天列表中的搜索对话和文件中。
    
    > [!NOTE]
    > 在 Exchange 混合部署中，拥有本地邮箱的用户可以参与属于 Teams 中的聊天列表的对话。 在这种情况下，这些对话中的也可搜索，因为对于拥有本地邮箱的用户来说，它已保存至拥有本地邮箱的用户的基于云的存储区（称为*本地用户的基于云的邮箱*）。 有关详细信息，请参阅[为 Office 365 中的本地用户搜索基于云的邮箱](search-cloud-based-mailboxes-for-on-premises-users.md)。
  
- 每个团队或团队渠道均包含一个用于做笔记和协作的 Wiki。 Wiki 内容将会自动保存至采用 .mht 格式的文件。 此文件存储在团队 SharePoint 网站的 Teams Wiki 数据文档库中。 可以使用内容搜索工具来搜索 Wiki，方法是将团队的 SharePoint 网站指定为要搜索的内容位置。 
    
    > [!NOTE]
    > 搜索团队或渠道 Wiki 的功能（在搜索团队 SharePoint 网站时）已于 2017 年 6 月 22 日发布。 可以对在该日期或之后保存或更新的 Wiki 页面进行搜索。 不可搜索最后保存或更新时间早于该日期的 Wiki 页面。 
 
- Teams 渠道中的会议和呼叫摘要信息也保存在拨入会议或呼叫的用户的邮箱中。 这意味着你可以使用内容搜索来搜索这些摘要记录。 摘要信息包括： 
  
  - 日期、开始时间、结束时间和会议或呼叫时长

  - 每个参与者加入或离开会议或呼叫的日期和时间

  - 发送到语音信箱的呼叫

  - 未接呼叫

  - 表示为两次单独呼叫的呼叫转移

  可能需要最多 8 小时之后才能搜索会议和呼叫摘要记录。

  在搜索结果中，会议摘要在“**类型字段**”将标识为“**会议**”，呼叫摘要将标识为“**呼叫**”。 此外，属于 Teams 渠道和 1xN 聊天的对话在“**类型**”字段将标识为 **IM**。
  
  ![Teams 会议、呼叫和 1xN 聊天将在“类型”字段中标识](media/O365-ContentSearch-Teams-MessageKind.png)

- 可以使用“**类型**”电子邮件属性或“**邮件类型**”搜索条件来搜索 Teams 中的特定内容。 
  
  - 若要将“**类型**”属性用作关键字搜索查询的一部分，请在搜索查询的“**关键字**”框中键入 `kind:microsoftteams`。

    ![在关键字框中键入 kind:microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - 若要使用搜索条件，请添加“**邮件类型**”条件并使用值 `microsoftteams`。 

    ![搭配使用“邮件类型”条件和值 microsoftteams。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

请注意，条件将通过 **AND** 运算符在逻辑上连接至关键字查询。 这意味着项必须与关键字查询和搜索条件匹配才能在搜索结果中返回。 有关详细信息，请参阅[内容搜索的关键字查询和搜索条件](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)中的“使用条件指南”一节。

  
### <a name="searching-inactive-mailboxes"></a>搜索非活动邮箱

可以在内容搜索中搜索非活动邮箱。 若要获取组织中的非活动邮箱列表，请在 Exchange Online PowerShell 中运行命令 `Get-Mailbox -InactiveMailboxOnly`。 或者，你可以转至安全与合规中心中的“**数据管理**”\>“**保留**”，然后单击“**更多**”“![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)”\>“**非活动邮箱**”。
  
以下是在搜索非活动邮箱时应记住的一些事项。
  
- 如果内容搜索包括用户邮箱，且该邮箱随后变成非活动状态，那么在该邮箱转变为非活动状态后重新运行搜索时，内容搜索将继续搜索非活动邮箱。
    
- 有时候，用户可能具有 SMTP 地址相同的活动邮箱和非活动邮箱。 在这种情况下，将仅搜索你选为内容搜索位置的特定邮箱。 换言之，如果将用户邮箱添加到搜索中，则无法假定搜索的是其活动和非活动邮箱。 只会搜索已显式添加到搜索中的邮箱。
    
- 强烈建议避免活动邮箱和非活动邮箱具有相同的 SMTP 地址。 如果需要重新使用分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或将非活动邮箱中的内容还原到活动邮箱中（或活动邮箱的存档中），然后删除非活动邮箱。 有关详细信息，请参阅下列主题之一：
    
  - [恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)
    
  - [还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)
    
  - [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>预览搜索结果

可以在预览窗格中预览受支持的文件类型。 如果文件类型不受支持，则必须将该文件的副本下载到本地计算机才能查看它。 以下是受支持的文件类型，可以在搜索结果窗格中对其进行预览。
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，还支持以下文件容器类型。 可以在预览窗格中查看容器中的文件列表。
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>部分索引项

- 如前面所述，邮箱中的部分索引项将包括在估计的搜索结果中。 SharePoint 和 OneDrive 中的部分索引项不会包括在估计的搜索结果中。 
    
- 如果部分索引项符合搜索查询（因为其他邮件或文档属性满足搜索条件），则它不会包含在未编入索引的项目的估计数中。 如果部分索引项被搜索条件排除在外，则它不会包括在未索引项的估计数中。 有关详细信息，请参阅 [Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)。
