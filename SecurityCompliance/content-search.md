---
title: Office 365 中的内容搜索
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
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: 在 Office 365 安全性使用内容搜索&amp;合规性中心业务对话搜索邮箱、 SharePoint Online 网站、 OneDrive 帐户、 Microsoft 团队、 Office 365 组和 Skype 中的内容。您可以使用关键字搜索查询和搜索条件以缩小搜索结果的范围。然后您可以预览和导出搜索结果。内容搜索也是有效的工具搜索可能与 GDPR 数据主题请求相关的内容。
ms.openlocfilehash: befd2060e65cea73d3c8432b77727e27dd91b82a
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686113"
---
# <a name="content-search-in-office-365"></a>Office 365 中的内容搜索

您可以在 Office 365 安全性使用内容搜索电子数据展示工具&amp;合规性中心就地项目，如电子邮件、 文档和即时消息会话在 Office 365 组织中的进行搜索。使用此工具来搜索这些 Office 365 服务中的项：
  
- Exchange Online 邮箱和公用文件夹
    
- SharePoint Online 网站和 OneDrive for Business 帐户
    
- 业务对话的的 Skype
    
- Microsoft Teams 
    
- Office 365 组
    
后运行内容搜索，内容位置数和搜索配置文件中显示搜索结果的估计的数目。快速，您可以查看统计信息，如具有匹配的搜索查询的大多数项目的内容位置。运行搜索后，您可以预览结果，或将其导出到本地计算机上。


## <a name="create-a-new-search"></a>创建新的搜索

若要有权访问要运行搜索和预览，并将搜索结果导出的**内容搜索**页，管理员、 合规部主管，还是电子数据展示管理员必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用您的 Office 365 电子邮件地址和密码登录。 
    
3. 安全中&amp;合规性中心，单击**搜索&amp;调查** \> **内容搜索**。
    
4. 在**搜索**页上，单击箭头下一步为![添加图标](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**新的搜索**。 
    
    ![新的搜索下拉列表](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    可选择下列选项之一：
    
  - **引导式搜索**-此选项将启动一个向导，引导您完成创建搜索。用户界面来选择内容位置和构建搜索查询都作为**新的搜索**选项相同。 
    
  - **新的搜索**-此选项显示一个更新的用户界面创建新的搜索。如果您单击**新搜索**，这是默认选项。
    
  - **按 ID 列表搜索**-此选项允许您搜索特定的电子邮件和使用 Exchange Id 的列表的其他邮箱项目。若要创建 （正式称为目标的搜索） 的 ID 列表搜索，您可以提交标识要搜索的特定邮箱项目以逗号分隔的值 (CSV) 文件。有关说明，请参阅[Prepare ID 列表在 Office 365 中的内容搜索的 CSV 文件](csv-file-for-an-id-list-content-search.md)。
    
    在此过程的步骤的其余部分将按照默认新搜索工作流。
    
5. 单击下拉列表中的**新的搜索**。 
    
6. 在**搜索查询**，指定以下内容。
    
    ![指定关键字、 条件和要搜索的位置](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
- **若要搜索的关键字**-在**关键字**框中的搜索查询的类型。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用使用布尔运算符，例如**AND**、**或**、 ****，和**NEAR**更复杂的查询。您还可以搜索文档或搜索外部共享的文档中的敏感信息 （如社会保险号码）。如果保留关键字框为空，则将在搜索结果中包含位于指定的内容位置的所有内容。
    
    或者，您可以单击**显示关键字列表**复选框，键入每行中的关键字。如果这样做，每个行的关键字进行连接的逻辑运算符 ( **c:s**) 中创建的搜索查询的**OR**运算符功能类似的。 
    
    为什么使用关键字列表？您可以获取显示的项目数与每个关键字匹配的统计信息。这可以帮助您快速识别的关键字是最 （和至少） 有效。行中，您还可以使用关键字短语 （用括号括起来）。有关搜索统计信息的详细信息，请参阅[视图的内容的搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。

    [!NOTE] 为了帮助减少所导致的大型关键字列表问题，您现在限制为最多 20 关键字列表中的行。
    
- **条件**-您可以添加搜索条件以缩小搜索范围并返回更精确的结果集。每个条件向搜索查询创建和启动搜索时运行一个子句。条件逻辑**AND**运算符功能类似的逻辑运算符 ( **c:c**) 通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的一个或多个条件。这是如何帮助条件以缩小结果。列表以及您可以使用搜索查询中的条件的说明，请参阅[关键字查询及搜索内容搜索条件](keyword-queries-and-search-conditions.md#search-conditions)中的"搜索条件"部分。
    
- **位置**-选择要搜索的内容位置。
    
  - **所有位置**-使用此选项可搜索您的组织中的所有内容的位置。这包括电子邮件 （包括所有非活动邮箱，所有 Office 365 组邮箱，所有的 Microsoft 团队的邮箱） 的所有 Exchange 邮箱，所有 Skype 进行业务对话时，所有 SharePoint 和 OneDrive for Business 网站 （包括网站对于所有 Office 365 组和 Microsoft 团队），以及所有 Exchange 公用文件夹中的项目。
    
  - **特定位置**-使用此选项可搜索特定内容的位置。您可以搜索特定的 Office 365 服务的所有内容位置 （如搜索所有 Exchange 邮箱，或搜索所有 SharePoint 网站），或者可以任意显示 Office 365 服务中都搜索特定位置。 
    
    ![选择要搜索的内容位置的用户界面](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
    请注意，还可以向 Exchange 邮箱搜索列表添加通讯组。通讯组的组成员的邮箱中搜索。请注意，不支持动态通讯组。
    
    **重要：** 在搜索所有邮箱位置或刚刚特定邮箱时，您将导出的内容的都搜索结果时将包含 MyAnalytics 和其他 Office 365 应用程序中的数据保存到用户邮箱。估计的搜索结果中将不会包含此数据，它不会可用的预览。它仅时将包含导出并下载搜索结果;请参阅[从 MyAnalytics 导出数据和其他 Office 365 应用程序](#exporting-data-from-myanalytics-and-other-office-365-applications)的"内容搜索详细信息"部分。 
    
7. 您已设置您的搜索查询后，单击**保存&amp;运行**。
    
8. 在**保存搜索**页上，键入搜索和可选说明，可帮助确定搜索的名称。请注意，搜索的名称必须是唯一组织中。 
    
9. 单击**保存**以开始搜索。 
    
    保存并运行搜索后，在结果窗格中显示搜索返回任何结果。根据配置的预览设置对，搜索结果显示或您必须单击**预览搜索结果**，以查看它们。请参阅下一节的详细信息。 
    
要再次访问此内容的搜索或访问其他内容的搜索列在**内容搜索**页上，选择搜索，然后单击**打开**。 
  
若要清除结果或创建一个新的搜索，请单击![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)**新的搜索**。 

  
## <a name="preview-search-results"></a>预览搜索结果

预览搜索结果有两个配置设置。运行一个新的新的搜索或打开现有搜索后，单击 * * 单个结果 * * 若要查看下列预览设置： 
  
![预览搜索结果设置](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **自动预览的结果**-此设置显示搜索结果后运行搜索结果。
    
2. **手动预览的结果**-此设置显示占位符中搜索结果窗格中，并显示您必须单击以显示搜索结果的**预览搜索结果**按钮。这是默认设置;有助于提高搜索性能，通过打开现有搜索时不会自动显示在搜索结果。 
    
有多少项可预览与相关的限制。有关详细信息，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。 
  
可以预览的受支持的文件类型的列表，请参阅"关于内容搜索的详细信息"部分中的[Previewing 搜索结果](#previewing-search-results)。如果为预览或下载文档的副本，则不受支持的文件类型，则可以单击**下载原始文件**下载到本地计算机。对于.aspx 网页，页面的 URL 是包含，但您可能没有访问页上的权限。 
  
还要注意未编制索引的项目不可用的预览。
  
## <a name="view-information-and-statistics-about-a-search"></a>查看信息以及有关搜索统计信息

创建和运行内容搜索后，您可以查看有关估计的搜索结果的统计信息。这包括搜索结果中，如内容位置与搜索查询，匹配项的数量和具有最匹配的项的内容位置的名称的查询统计信息的摘要。您可以显示一个或多个内容搜索统计的信息。这样可以快速比较多个搜索结果，并做出决策的有效性的搜索查询。
  
您还可以下载到 CSV 文件的搜索统计信息和关键字统计信息。这使您在 Excel 中使用的筛选和排序功能比较结果，并准备您的搜索结果的报告。
  
若要查看搜索统计信息：
  
1. 在安全的**内容搜索**页上&amp;合规性中心，单击**打开**，然后单击您想要查看的统计值为搜索。 
    
2. 在飞出页上，单击**打开查询**。 
    
3. 在**单个结果**下拉列表中，单击**搜索配置文件**。
    
4. 在**类型**下拉列表中单击具体取决于您想要查看的搜索统计信息的以下选项之一。 
    
  - 搜索**摘要**-每种类型的内容位置的显示统计信息。此内容的内容位置包含搜索查询匹配的项目数和的总数量和大小的搜索结果项。这是默认设置。
    
  - **查询**-显示有关搜索查询的统计信息。这包括查询统计信息都适用于内容位置的类型，搜索查询统计信息的一部分适用 （注意**主**指示整个搜索查询） 包含的内容位置的数量的项目匹配搜索查询的总数和大小和 （在指定的内容位置） 找到项相匹配的搜索查询。请注意也会显示未编制索引项 （也称为部分索引的项） 的统计信息。但是，仅从邮箱的部分索引的项目包含统计信息中。统计信息中不包括来自 SharePoint 和 OneDrive 部分索引的项。
    
  - **顶部的位置**-显示有关与每个搜索的内容位置中搜索查询匹配的项目数的统计信息。显示前 1000 位位置。
    
有关搜索统计信息的更多详细信息，请参阅[视图的内容的搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。
  
  
## <a name="export-search-results"></a>导出搜索结果

搜索成功运行后，您可以将搜索结果导出到本地计算机。导出电子邮件结果时，它们可以作为 PST 文件或单个邮件 （.msg 文件） 下载到您的计算机。从 SharePoint 和 OneDrive 网站导出内容时，导出本机 Office 文档的副本。还有其他文档和导出的搜索结果中包含的报告。您还可以导出搜索结果报告而不是实际的项目。
  
导出搜索结果：
  
1. 在安全的**内容搜索**页上&amp;合规性中心，单击**打开**，然后单击您想要导出的搜索结果的搜索。 
    
2. 在飞出页上，单击![导出搜索结果图标](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)**详细**，然后单击**导出结果**。请注意，您还可以导出搜索结果报告。
    
3. 完成“**导出结果**”飞出页面上的各个部分。请务必使用滚动条查看所有导出选项。 
    
有关详细的说明和疑难解答提示，请参阅：
  
- [从 Office 365 安全性导出搜索结果&amp;合规性中心](export-search-results.md)
    
- [导出内容搜索报告](export-a-content-search-report.md)
    

  
## <a name="more-information-about-content-search"></a>有关内容搜索的详细信息

请参阅以下各节内容搜索有关的详细信息。
  
[内容搜索限制](#content-search-limits)
  
[构建搜索查询](#building-a-search-query)
  
[搜索 OneDrive 帐户](#searching-onedrive-accounts)
  
[搜索的 Microsoft 团队和 Office 365 组](#searching-microsoft-teams-and-office-365-groups)
  
[搜索的非活动邮箱](#searching-inactive-mailboxes)
  
[预览搜索结果](#previewing-search-results)
  
[部分索引的项目](#partially-indexed-items)
  
[从 MyAnalytics 和其他 Office 365 应用程序中导出数据](#exporting-data-from-myanalytics-and-other-office-365-applications)
  
### <a name="content-search-limits"></a>内容搜索限制

- 应用于的内容的搜索功能的限制的说明，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。
    
- Microsoft 收集有关运行所有 Office 365 组织的内容搜索的性能信息。时搜索查询的复杂性会影响搜索时间，搜索会影响搜索收回长是邮箱数的最大因子。虽然 Microsoft 没有搜索时间提供服务级别协议下, 表将列出内容搜索基于包括在搜索的邮箱数的平均搜索时间。
    
|**邮箱数**|**平均搜索时间**|
|:-----|:-----|
|100  <br/> |30 秒  <br/> |
|1,000  <br/> |45 秒  <br/> |
|10,000  <br/> |4 分钟  <br/> |
|25000  <br/> |此参数指定在关闭连接之前，已打开的、与目标邮件传递服务器的 SMTP 连接可以保持空闲的最长时间。  <br/> |
|50,000 个  <br/> |20 分钟  <br/> |
|100,000  <br/> |25 分钟  <br/> |
  
### <a name="building-a-search-query"></a>构建搜索查询

有关创建搜索查询、 使用布尔搜索运算符和搜索条件和搜索敏感信息类型和与组织外部的用户共享的内容的详细信息，请参阅[Keyword queries 和搜索条件内容搜索](keyword-queries-and-search-conditions.md)。
  
使用关键字列表创建的搜索查询时，请确保记住以下事项。
  
- 您必须选择**显示关键字列表**复选框，然后在单独的行以创建的搜索查询中键入每个关键字其中每一行中的关键字 （或关键字短语） 进行连接的**OR**运算符。如果您只在关键字框中粘贴的关键字列表，或键入关键字后按**Enter**键，它们不会通过**OR**运算符进行连接。下面是添加的关键字列表的不正确，并正确的示例。 
    
    **不正确**
    
    ![不正确的方式设置关键字列表格式 （通过关键字框中粘贴的列表）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **更正**
    
    ![正确的方式设置关键字列表格式 （通过选择复选框，然后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- 您可以还准备一组关键字或关键字短语中的 Excel 文件或一个纯文本文件，然后复制并粘贴到关键字列表中的列表。若要执行此操作，您必须选择**显示关键字列表**复选框。然后，单击关键字列表中的第一行并粘贴您的列表。从 Excel 或文本文件每行将中粘贴到单独的关键字列表中的行。 
    
- 创建查询使用关键字列表后，最好验证您所能进行搜索查询的搜索查询语法。在搜索查询中的详细信息窗格中显示在**查询**下，使用文本 **(c:s)** 分隔的关键字。 这表示关键字进行连接的逻辑运算符**OR**运算符功能类似。同样，如果您的搜索查询包含条件，关键字和条件使用分隔文本 **(c:c)**。 这表示关键字已连接到使用逻辑运算符类似于**和**功能的条件运算符。下面是一个示例 （显示详细信息窗格中） 的搜索查询的结果时使用关键字列表和条件。 
    
    ![使用关键字列表和条件时创建的查询的示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- 内容搜索运行时，Office 365 自动检查您的搜索查询不支持的字符和不可能大写的布尔运算符。不支持的字符通常隐藏和通常会导致搜索错误或返回意外的结果。有关检查不支持的字符的详细信息，请参阅[检查错误内容的搜索查询](check-your-content-search-query-for-errors.md)。
    
- 如果您有包含非英文字符 （例如中文字符） 的关键字的搜索查询，则可以单击**查询语言-国家/地区**![内容搜索中的查询语言-国家/地区图标](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png)，然后选择搜索的语言-国家/地区区域性代码值。请注意，默认语言/区域中性。您如何知道您是否需要更改内容的搜索的语言设置？如果您是某些内容位置包含要搜索的非英语字符，但搜索未返回任何结果，则可能原因的语言设置。 
  
### <a name="searching-onedrive-accounts"></a>搜索 OneDrive 帐户

- 若要收集您的组织中的 OneDrive 网站的 Url 的列表，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的此脚本将创建一个包含所有 OneDrive 网站的列表的文本文件。若要运行此脚本，您将需要安装和使用 SharePoint Online Management Shell。请务必附加到您要搜索的每个 OneDrive 网站您所在组织的 MySite 域名的 URL。这是包含所有 OneDrive; 的域例如， `https://contoso-my.sharepoint.com`。下面是用户的 OneDrive 网站的 URL 的一个示例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    
    人员的用户主体名称 (UPN) 已更改的情况很少，其 OneDrive 位置的 URL 也将更改要合并的新的 UPN。如果发生这种情况，必须将修改添加用户的新 OneDrive URL 和删除旧内容的搜索。
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>搜索的 Microsoft 团队和 Office 365 组

您可以搜索与 Office 365 组或 Microsoft 团队相关联的邮箱。由于 Microsoft 团队基于 Office 365 组，因此搜索它们是非常类似。在这两种情况下，搜索仅组或团队邮箱;不搜索的邮箱的组或团队成员。若要搜索他们，您必须明确将它们添加到搜索。
  
搜索的 Microsoft 团队和 Office 365 组中的内容时，请记住以下事项。
  
- 若要搜索的内容位于 Microsoft 团队和 Office 365 组中，您必须指定的邮箱和与团队或组关联的 SharePoint 网站。
    
- 运行在 Exchange Online 中的 Microsoft 团队或 Office 365 组查看属性**获取 UnifiedGroup** cmdlet。这是一个好方法获取与团队或一组相关联的网站的 URL。例如，下面的命令的一个名为高级领导团队的 Office 365 组显示所选的属性： 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > 若要运行**Get UnifiedGroup** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。 
  
- 用户的邮箱搜索，搜索时不会搜索任何 Microsoft 团队或 Office 365 组的成员的用户。同样，搜索当您搜索 Microsoft 团队或 Office 365 组中，只有组邮箱和组网站指定;除非您明确将它们添加到搜索，不搜索的邮箱和 OneDrive for Business 的组成员的帐户。
    
- 若要获取的 Microsoft 团队或 Office 365 组成员的列表，可以查看属性在**主页\>组**Office 365 管理中心中的页。此外，还可以在 Exchange Online PowerShell 中运行以下命令： 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > 若要运行**Get UnifiedGroupLinks** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。 
  
- 与 Microsoft 团队相关联的邮箱中存储的一部分的 Microsoft 团队通道对话。同样，在频道的工作组成员共享的文件存储团队的 SharePoint 网站上。因此，您需要将 Microsoft 团队邮箱和 SharePoint 网站添加为通道中搜索对话和文件的内容位置。
    
- 此外，参与聊天的用户的 Exchange Online 邮箱中存储是在 Microsoft 团队中的聊天列表的一部分的对话。和用户共享聊天对话中的文件存储在 OneDrive for Business 帐户的用户的共享文件。因此，您需要将单个用户邮箱和 OneDrive 业务帐户添加为聊天列表中搜索对话和文件的内容位置。
    
    > [!NOTE]
    > Exchange 混合部署，具有内部部署邮箱的用户可能参与对话中的 Microsoft 团队的聊天列表的一部分。在这种情况下，这些对话的内容是还可搜索，因为它具有内部部署邮箱的用户将保存到 （称为*基于云的邮箱的内部部署用户*） 的基于云的存储区。有关详细信息，请参阅[搜索基于云的邮箱的内部部署 Office 365 中的用户](search-cloud-based-mailboxes-for-on-premises-users.md)。
  
- 每个通道，Microsoft 团队或团队包含 Wiki 笔记记录和协作。Wiki 内容将自动保存到.mht 格式的文件时。此文件存储在团队的 SharePoint 网站上的团队 Wiki 数据文档库。内容搜索工具可用于通过指定为要搜索的内容位置的团队的 SharePoint 网站中搜索 Wiki。 
    
    > [!NOTE]
    > 2017 年 6 月 22，发布 （时搜索团队的 SharePoint 网站） 的 Microsoft 团队或通道搜索 Wiki 的功能。Wiki 网页保存或更新的日期或之后可供搜索。Wiki 网页上一次保存或更新的日期之前不可供搜索。 
 
- 此外在开会或打电话到用户的邮箱中存储会议和呼叫中的 Microsoft 团队通道的摘要信息。这意味着您可以使用内容搜索搜索这些摘要的记录。摘要信息包括： 
  - 日期、 启动时间、 结束时间和持续时间开会或打电话

  - 日期和时间时每个参与者加入或离开会议或呼叫

  - 呼叫发送到语音邮件

  - 错过或未应答呼叫

  - 呼叫转移，表示为两个单独的调用

  请注意，可能需要为会议和呼叫摘要的记录，可为搜索最多为 8 小时。

  在搜索结果中，会议摘要被标识为**会议****类型字段**; 中呼叫摘要被标识为**呼叫**。此外，团队通道和 1xN 聊天一部分的对话被标识为**类型**字段中的**IM** 。
  
  ![在类型字段中识别团队会议、 通话和 1xN 聊天](media/O365-ContentSearch-Teams-MessageKind.png)

- 您可以使用**类型**email 属性或**消息类型**搜索条件搜索专门用于 Microsoft 团队中的内容。 
  - 若要使用的**类型**属性的搜索查询，**关键字**框中的关键字搜索查询的一部分键入`kind:microsoftteams`。

    ![在关键字框中使用类型： microsoftteams](media/O365-ContentSearch-Teams-Keywords.png)
  
  - 若要使用的搜索条件，添加**消息类型**条件，并将值`microsoftteams`。 

    ![使用值 microsoftteams 消息 kind 条件。](media/O365-ContentSearch-Teams-MessageKindCondition.png)

请注意条件逻辑通过**AND**运算符连接到关键字查询。这意味着项必须匹配关键字查询和搜索结果中返回的搜索条件。有关详细信息，请参阅中的"使用情况的指南"一节[关键字查询和内容搜索的搜索条件。](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions)

  
### <a name="searching-inactive-mailboxes"></a>搜索的非活动邮箱

您可以在内容搜索中搜索非活动邮箱。若要获取组织中的非活动邮箱的列表，请运行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。此外，您可以转到**数据调控**\>安全中**保留**&amp;合规性中心，然后单击**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非活动邮箱**。
  
下面是要搜索非活动邮箱时，请记住的几个事项。
  
- 如果内容搜索包含用户邮箱，并且该邮箱由处于非活动状态，内容搜索将继续在它变为非活动状态后重新运行搜索时搜索非活动邮箱。
    
- 在某些情况下，用户可能有活动邮箱和非活动邮箱，具有相同的 SMTP 地址。在这种情况下，将搜索仅特定邮箱的选择作为内容搜索的位置。换句话说，如果您将用户邮箱添加到搜索，您不能假设，将搜索其活动和非活动邮箱;将搜索的明确添加到搜索邮箱。
    
- 我们强烈建议您避免使用活动邮箱和非活动邮箱具有相同的 SMTP 地址。如果您需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或非活动邮箱的内容还原到活动邮箱 （或活动邮箱的存档），然后删除非活动邮箱。有关详细信息，请参阅以下主题：
    
  - [恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)
    
  - [还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)
    
  - [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)

  
### <a name="previewing-search-results"></a>预览搜索结果

您可以预览预览窗格中的受支持的文件类型。如果不支持的文件类型，必须将文件的副本下载到本地计算机进行查看。以下文件类型支持并且可以在搜索结果窗格中预览。
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，也支持以下文件容器类型。您可以查看文件的列表中预览窗格中的容器。
  
- .zip
    
- .gzip
    
### <a name="partially-indexed-items"></a>部分索引的项目

- 如前面所述，部分索引邮箱中的项目包含中估计的搜索结果;估计的搜索结果中不包含来自 SharePoint 和 OneDrive 部分索引的项。 
    
- 如果部分项匹配搜索查询 （因为其他消息或文档属性符合搜索条件），它不会包含在未编制索引的项的估计数目。如果部分项排除的搜索条件，它也不会包含在部分索引项的估计数目。有关详细信息，请参阅[部分索引在 Office 365 中的内容搜索的项目](partially-indexed-items-in-content-search.md)。
    
### <a name="exporting-data-from-myanalytics-and-other-office-365-applications"></a>从 MyAnalytics 和其他 Office 365 应用程序中导出数据

- 从 MyAnalytics （如用户如何花时间基于其邮箱中的邮件和日历数据的见解） 数据和其他 Office 365 应用程序中的数据保存到用户的基于云的邮箱中的隐藏位置 （非 IPM 子树） 中。在您运行内容的搜索，此数据不包括在估计的搜索结果中，查询统计信息，并不适用于预览。但是导出的搜索结果时，将导出此数据。
    
- MyAnalytics 数据和其他 Office 365 应用程序中的数据导出到名为"其他 Office 365 数据"的文件夹。此文件夹包含为每个用户的子文件夹。
  
