---
title: 运行 Office 365 安全性内容的搜索&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ComplianceSearch
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 61852fd9-fe8a-4880-a339-cb19ed3bff4a
description: '在 Office 365 安全性中使用内容搜索&amp;合规性中心以搜索邮箱、 SharePoint Online 网站和 OneDrive for Business 位置。 '
ms.openlocfilehash: 61c6c3933a75567acb04f793cb6815322fb3fada
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525247"
---
# <a name="run-a-content-search-in-the-office-365-security-amp-compliance-center"></a>运行 Office 365 安全性内容的搜索&amp;合规性中心

您可以在 Office 365 安全性使用内容搜索电子数据展示工具&amp;合规性中心搜索如电子邮件、 文档和即时消息对话 Office 365 组织中的项目。使用此工具来搜索这些 Office 365 服务中的项：
  
- Exchange Online 邮箱和公用文件夹
    
- SharePoint Online 和 OneDrive for Business 站点
    
- 业务对话的的 Skype
    
- Microsoft Teams 
    
- Office 365 组
    
内容搜索是一个新的电子数据展示搜索工具，使用新的和改进缩放和性能的功能。内容搜索用于运行非常大的电子数据展示搜索。您可以搜索所有邮箱，所有 Exchange 公用文件夹和所有 SharePoint Online 网站和 OneDrive 中单个内容都搜索业务帐户。可搜索的内容位置的数量没有限制。还有没有限制可以同时运行的搜索数。后运行内容搜索，内容位置数和**内容的搜索**页面上的详细信息窗格中显示搜索结果的估计的数目。运行搜索后您可以预览结果，关键字统计信息获得一个或多个搜索批量编辑内容搜索和结果导出到本地计算机。 
  
 **目录**
  
[创建搜索](run-a-content-search-in-the-security-and-compliance-center.md#create)
  
[导出搜索结果](run-a-content-search-in-the-security-and-compliance-center.md#export)
  
[预览搜索结果](run-a-content-search-in-the-security-and-compliance-center.md#preview)
  
[更新搜索结果](run-a-content-search-in-the-security-and-compliance-center.md#restart)
  
[编辑搜索](run-a-content-search-in-the-security-and-compliance-center.md#edit)
  
[重试搜索](run-a-content-search-in-the-security-and-compliance-center.md#retry)
  

  
## <a name="before-you-begin"></a>准备工作

- 信息和指导构建搜索查询和使用布尔搜索运算符，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。本文还包含有关搜索敏感信息类型和搜索与您的组织内外的人员共享的内容的信息。
    
- 若要有权访问要执行搜索和预览，并将搜索结果导出的**内容搜索**页，管理员、 合规部主管，还是电子数据展示管理员必须是安全中的电子数据展示管理员角色组的成员&amp;合规性中心。您无需分配其他搜索权限在 Exchange Online 中，SharePoint Online，或 onedrive for Business 站点。有关详细信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
    
- 有限制应用于内容的搜索来维护的运行状况和质量提供给 Office 365 组织的服务。在大多数情况下，不能修改这些限制，但是，以便您可以考虑这些限制时规划、 运行和解决搜索您应了解它们。有关详细信息，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。
    
- 请参阅估计的搜索时间基于单个内容搜索中搜索的邮箱数。 
    
- 如前面所述，您可以使用内容搜索来搜索 Office 365 组和 Microsoft 团队中的内容。这意味着您可以搜索组邮箱、 共享的日历和与 Office 365 组和 Microsoft 团队关联的 SharePoint 网站。此外，您可以在 Microsoft 团队搜索通道对话。有关 Office 365 组和 Microsoft 团队的信息，请参阅：
    
  - [了解 Office 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
    
  - [Microsoft 团队帮助](https://support.office.com/article/23156c0c-2c6e-49dd-8b7b-7c564b76508c)
    
    请参阅为 Office 365 组和 Microsoft 团队中的内容搜索提示部分。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="create-a-search"></a>创建搜索
<a name="create"> </a>

1. 转到[https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用工作或学校帐户。
    
3. 在安全与合规中心的左侧窗格中，单击“搜索和调查”****\>****“内容搜索”。
    
4. 单击**新建**![添加图标](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
5. 在**新的搜索**页上，键入内容的搜索的名称。此名称必须是唯一组织中。 
    
6. 选择您要搜索的内容位置。您可以在同一个搜索中搜索邮箱、 网站和公用文件夹。
    
    ![选择您要搜索的内容位置](media/da32e3f9-6cd6-4a26-8217-e97a5a7071e4.png)
  
1. **搜索无处不在**选择此选项可搜索您的组织中的所有内容的位置。时选择此选项，您可以选择搜索 （包括非活动邮箱和邮箱的所有 Office 365 组和 Microsoft 团队） 的所有邮箱的所有 SharePoint 和 OneDrive for Business 站点 (包括 Office 365 中的所有组的网站和Microsoft 团队） 和所有公用文件夹。
    
    ![单击搜索无处不在选项可搜索的所有内容位置](media/86f132f1-0a2a-4048-900c-9f219d909ef2.png)
  
2. **自定义位置选择**选择此选项可选择的邮箱和您要搜索的网站。如果选择此选项时，必须以搜索特定服务 （如搜索所有 Exchange 邮箱） 的所有内容位置的灵活性，也可以搜索 Office 365 服务的特定内容的位置。
    
    添加要搜索的内容位置时，请牢记以下：
    
    **邮箱**
    
  - 单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)若要指定要搜索的邮箱，显示邮箱选取器为空。这是设计以提高性能。若要将收件人添加到此列表中，在搜索框中键入名称 （最少的 3 个字符） 并单击**搜索**![搜索图标](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)。
    
  - 您可以将非活动邮箱和通讯组添加到要搜索的邮箱列表中。通讯组的组成员的邮箱中搜索。请注意，不支持动态通讯组。
    
  - 若要获取组织中的非活动邮箱的列表，请运行命令`Get-Mailbox -InactiveMailboxOnly`在 Exchange Online PowerShell。此外，您可以转到**数据调控**\>安全中**保留**&amp;合规性中心，然后单击**更多**![导航栏省略号](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **非活动邮箱**。
    
  - 您还可以添加与 Office 365 组或 Microsoft 团队相关联的邮箱。在这种情况下，搜索仅组或团队邮箱;不搜索的邮箱的组或团队成员。若要搜索他们，您必须明确将它们添加到搜索。
    
  - 如果您不想要包括到搜索所有邮箱，选择**要搜索的选择特定邮箱**，但不将邮箱添加到列表。
    
    **网站**
    
  - 单击**添加**![添加图标](media/ITPro-EAC-AddIcon.gif)将站点添加到搜索。键入要搜索的每个网站的 URL。内容搜索工具将验证 URL，并将其添加到网站搜索的列表。 
    
  - 您可以添加具有相关联的 Office 365 组或 Microsoft 团队的 SharePoint。请参阅有关如何查找组或团队的 URL 的指南。 
    
  - 如果您不想要在搜索中包括的任何网站，选择**选择特定网站搜索**，但不将网站添加到列表。
    
    **公用文件夹**
    
    有关公用文件夹，您可以选择搜索 Exchange Online 组织中的所有公用文件夹或不搜索任何公用文件夹。
    
7. 单击"下一步"。
    
8. 在“**新搜索**”页上，您可以添加用于创建搜索查询的关键字和条件。 
    
    ![使用关键字和条件创建搜索查询](media/1b7cf7b5-f1e1-471a-ad5c-48aad8435b00.png)
  
1. 在下框**希望什么我们查找？**，在框中键入搜索查询。您可以指定关键字，消息属性，如发送和接收日期或文档属性，如文件名或上次更改文档的日期。您可以使用使用布尔运算符，例如**AND**、**或**、**不**、 **NEAR**或**ONEAR**更复杂的查询。您还可以搜索文档或搜索外部共享的文档中的敏感信息 （如社会保险号码）。如果保留关键字框为空，则将在搜索结果中包含位于指定的内容位置的所有内容。 
    
2. 您可以单击**显示关键字列表**复选框，键入每行中的关键字。如果这样做，每个行的关键字进行连接的**OR**运算符创建搜索查询中。 
    
    ![您可以在关键字列表中的某行中键入关键字或关键字阶段](media/aea1a361-639d-4a82-8c3c-48645ef3fc05.png)
  
    为什么使用关键字列表？您可以获取显示的项目数与每个关键字匹配的统计信息。这可以帮助您快速识别的关键字是最 （和至少） 有效。行中，您还可以使用关键字短语 （用括号括起来）。有关搜索统计信息的详细信息，请参阅[视图的内容的搜索结果的关键字统计信息](view-keyword-statistics-for-content-search.md)。
    
    有关使用关键字列表，请参阅指南部分。 
    
3. 单击**检查错误的查询**来检查您的查询不支持的字符和不可能大写的布尔运算符。不支持的字符通常隐藏和通常会导致搜索错误或返回意外的结果。有关检查不支持的字符的详细信息，请参阅[检查错误内容的搜索查询](check-your-content-search-query-for-errors.md)。
    
4. 在**条件**下将添加到搜索查询来缩小搜索范围并返回一组多精简的结果的条件。每个条件向 KQL 搜索查询创建和启动搜索时运行一个子句。条件逻辑**AND**运算符通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的条件。这是如何帮助条件以缩小结果。 
    
||
|:-----|
|有关创建搜索查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](keyword-queries-and-search-conditions.md)。 |
   
9. 单击**搜索**以保存的搜索设置并开始搜索。 
    
    启动搜索。完成搜索后，将详细信息窗格中显示以下信息。
    
    ![在所选内容的搜索的详细信息窗格中显示搜索统计信息](media/2046bb5e-f4cb-4ba7-b7fc-8e5e53dae567.png)
  
1. 日期和时间的上次运行搜索。
    
2. 号码 （和总大小） 的项找到的匹配搜索查询。项目类型的示例包括电子邮件、 日历项和文档。如果项目中包含的关键字搜索的多个实例，它是仅计算一次中的总项目数。例如，如果您搜索单词"库存"或"tip"和电子邮件包含单词"库存"的三个实例，它是仅计算一次**项目**字段中。 
    
3. 数量和未编制索引中的项目已搜索的内容位置的总大小。不满足搜索条件的未编制索引项的数目将包括在细节窗格中显示的搜索统计信息。如果未编制索引的项匹配的搜索查询 （因为其他消息或文档属性符合搜索条件），它不会包含在未编制索引的项的估计数目。但是，如果未编制索引的项目中排除的搜索条件，它不会包含在未编制索引的项的估计值中。
    
4. 每种类型的内容位置的搜索数。邮箱，请注意，已搜索的邮箱总数中包含的存档邮箱。在上面的示例中，搜索四个用户邮箱并启用这些用户的存档邮箱。这就是为什么八个邮箱中搜索统计信息的引用。
    
5. 链接预览搜索结果，或运行搜索再次更新搜索统计信息。
    
    如有必要，单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)更新所选搜索的详细信息窗格中的信息。 
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="export-search-results"></a>导出搜索结果
<a name="export"> </a>

搜索成功运行后，您可以将搜索结果导出到本地计算机。导出电子邮件结果时，他们正在下载到您的计算机作为 PST 文件。导出时内容来自 SharePoint 和 OneDrive for Business 站点，导出本机 Office 文档的副本。还有其他文档和导出的搜索结果中包含的报告。有关详细信息，请参阅[导出搜索结果从 Office 365 安全性&amp;合规性中心](export-search-results.md)。
  
## <a name="preview-search-results"></a>预览搜索结果
<a name="preview"> </a>

搜索成功完成后，您可以预览搜索结果。有多个与预览内容搜索结果相关的限制。有关详细信息，请参阅[Limits for Office 365 安全性搜索&amp;合规性中心](limits-for-content-search.md)。请注意未编制索引的项目不可用的预览。
  
1. 在**内容搜索**页上，选择搜索。 
    
2. 在详细信息窗格中，在**结果**框中，单击**预览搜索结果**。**预览搜索结果**页打开，并包含搜索结果项的列表。 
    
    您可以单击列标题基于主题、 类型、 发件人或项目已接收的源邮箱中的日期对结果进行排序。
    
3. 单击要预览的项目。
    
    在预览窗格中打开项目时。
    
4. 如果为预览或下载文档的副本，则不受支持的文件类型，则可以单击**下载原始文件**下载到本地计算机。对于.aspx 网页，页面的 URL 是包含，但您可能没有访问页上的权限。 
    
> [!NOTE]
> 如果预览上次运行超过 7 天的搜索的搜索结果时，将提示您要更新的搜索结果。重新运行搜索以获得满足搜索查询的最新结果。 
  
### <a name="file-types-that-can-be-previewed"></a>可以预览的文件类型

您可以预览预览窗格中的受支持的文件类型。如果不支持的文件类型，必须将文件的副本下载到本地计算机进行查看。以下文件类型支持并且可以预览在**预览搜索结果**页。 
  
- .txt、.html、.mhtml
    
- .eml
    
- .doc、.docx、.docm
    
- .pptm、.pptx
    
- .pdf
    
此外，也支持以下文件容器类型。您可以查看文件的列表中预览窗格中的容器。
  
- .zip
    
- .gzip
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="update-search-results"></a>更新搜索结果
<a name="restart"> </a>

您更新现有内容搜索的结果，重新上指定的所有内容位置运行搜索查询。更新搜索结果的明显原因是要获取最新的数据。
  
1. 在**内容搜索**页上，选择您要更新的结果的搜索。 
    
2. 在详细信息窗格中，在**结果**框中，单击**更新搜索结果**。
    
    状态消息显示反映正在检索结果。完成搜索后，更新的信息在**结果**显示详细信息窗格中。请注意详细信息窗格中的**搜索**字段中的日期已更新到当前日期和时间。要刷新列表中的内容搜索的信息，请单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[Return to top](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="edit-a-search"></a>编辑搜索
<a name="edit"> </a>

您可以更改现有内容搜索的源邮箱和搜索查询。
  
1. 在**内容搜索**页上，选择搜索。 
    
2. 在详细信息窗格中，在**查询**下单击**编辑搜索**。
    
3. 在**位置**页中，可以更改哪些邮箱、 组、 SharePoint 网站或 OneDrive for Business 站点搜索。您还可以选择 （或未选择） 搜索 Exchange 中的所有公用文件夹。 
    
4. 在**查询**页中，您可以编辑搜索查询。 
    
5. 要开始修订后的搜索，请单击**源**或**位置**页上的**搜索**。 
    
    启动修订后的搜索。搜索完成后，预计的修订后的搜索结果将显示在详细信息窗格中。
    
## <a name="retry-a-search"></a>重试搜索
<a name="retry"> </a>

如果搜索返回任何错误，您无需重新搜索所有内容的位置。可以重新运行搜索，以便仅失败的内容的位置是搜索再次。若要重新搜索所有内容的位置，您可以更新的搜索结果。
  
1. 在**内容搜索**页上，选择包含您要重新搜索的内容位置的搜索。 
    
2. 在细节窗格中，在**错误**下单击**重试搜索**。
    
    状态消息显示反映正在检索结果。完成搜索时，更新的信息在**结果**显示详细信息窗格中。请注意详细信息窗格中的**搜索**字段中的日期已更新到当前日期和时间。要刷新列表中的搜索的信息，请单击**刷新**![刷新图标](media/O365-MDM-Policy-RefreshIcon.gif)。
    
[返回顶部](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
## <a name="more-information"></a>详细信息
<a name="moreinfo"> </a>

下面是有关内容搜索的详细信息。
  
[限制和性能](run-a-content-search-in-the-security-and-compliance-center.md#limits)
  
[未编制索引的项目](run-a-content-search-in-the-security-and-compliance-center.md#unindexeditems)
  
[Microsoft 团队和 Office 365 组](run-a-content-search-in-the-security-and-compliance-center.md#teams)
  
[OneDrive for Business](run-a-content-search-in-the-security-and-compliance-center.md#onedrive)
  
[搜索查询](run-a-content-search-in-the-security-and-compliance-center.md#queries)
  
[搜索的非活动邮箱](run-a-content-search-in-the-security-and-compliance-center.md#inactivemailboxes)
  
[其他](run-a-content-search-in-the-security-and-compliance-center.md#misc)
  
[（返回页首）](run-a-content-search-in-the-security-and-compliance-center.md#top)
  
 **限制和性能**
  
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
   

  
 **未编制索引的项目**
  
- 为要搜索的内容位置中的前面所述，未编制索引的项目中包含估计的搜索结果。如果未编制索引的项匹配的搜索查询 （因为其他消息或文档属性符合搜索条件），它不会包含在未编制索引的项的估计数目。如果未编制索引的项目中排除的搜索条件，它也不会包含中未编制索引的项的估计数目。有关详细信息，请参阅[内容搜索中的未编制索引的项](https://go.microsoft.com/fwlink/p/?LinkId=780739)。
    

  
 **Microsoft 团队和 Office 365 组**
  
- 在 Office 365 组上构建的 Microsoft 团队。因此，搜索它们是非常类似。搜索的 Microsoft 团队和 Office 365 组中的内容时，请记住以下事项。
    
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
    
  - 
    
    此外，参与聊天的用户的 Exchange Online 邮箱中存储是在 Microsoft 团队中的聊天列表的一部分的对话。和用户共享聊天对话中的文件存储在 OneDrive for Business 帐户的用户的共享文件。因此，您需要将单个用户邮箱和 OneDrive 业务帐户添加为聊天列表中搜索对话和文件的内容位置。
    
    > [!NOTE]
    > 参与对话中的 Microsoft 团队的聊天列表的一部分的用户必须具有 Exchange Online （基于云的） 使您可以搜索聊天邮箱。这是因为对话的一部分的聊天列表存储在基于云的邮箱的聊天参与者。如果聊天参与者没有 Exchange Online 邮箱，您将无法搜索聊天。例如，在 Exchange 混合部署，具有内部部署邮箱的用户可能能够参与对话中的 Microsoft 团队的聊天列表的一部分。但是在这种情况下，从这些对话的内容不搜索因为用户没有基于云的邮箱。 
  
  - 每个通道，Microsoft 团队或团队包含 Wiki 笔记记录和协作。Wiki 内容将自动保存到.mht 格式的文件时。此文件存储在团队的 SharePoint 网站上的团队 Wiki 数据文档库。内容搜索工具可用于通过指定为要搜索的内容位置的团队的 SharePoint 网站中搜索 Wiki。 
    
    > [!NOTE]
    > 2017 年 6 月 22，发布 （时搜索团队的 SharePoint 网站） 的 Microsoft 团队或通道搜索 Wiki 的功能。Wiki 网页保存或更新的日期或之后可供搜索。Wiki 网页上一次保存或更新的日期之前不可供搜索。 
  

  
 **OneDrive for Business **
  
- 若要为 OneDrive for Business 组织中的网站中收集的 url 列表，请参阅[创建您的组织中的所有 OneDrive 位置的列表](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)。本文中的脚本创建包含所有 OneDrive for Business 网站的列表的文本文件。若要运行此脚本，您将需要安装和使用 SharePoint Online Management Shell。一定要追加到每个 OneDrive for Business 站点您想要搜索的组织的 MySite 域的 URL。这是包含所有您 OneDrive for Business; 的域例如， `https://contoso-my.sharepoint.com`。下面是用户的 onedrive for Business 站点的 URL 的一个示例： `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。
    

  
 **搜索查询**
  
- 使用关键字列表创建的搜索查询时，请确保记住以下事项。
    
  - 您必须选择**显示关键字列表**复选框，然后在单独的行以创建的搜索查询中键入每个关键字其中每一行中的关键字 （或关键字短语） 进行连接的**OR**运算符。如果您只在关键字框中粘贴的关键字列表，或键入关键字后按**Enter**键，它们不会通过**OR**运算符进行连接。下面是添加的关键字列表的不正确，并正确的示例。 
    
    **不正确**
    
    ![不正确的方式设置关键字列表格式 （通过关键字框中粘贴的列表）](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **正确**
    
    ![正确的方式设置关键字列表格式 （通过选择复选框，然后粘贴列表）](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
  - 您可以还准备一组关键字或关键字短语中的 Excel 文件或一个纯文本文件，然后复制并粘贴到关键字列表中的列表。若要执行此操作，您必须选择**显示关键字列表**复选框。然后，单击关键字列表中的第一行并粘贴您的列表。从 Excel 或文本文件每行将中粘贴到单独的关键字列表中的行。 
    
  - 创建查询使用关键字列表后，它是确认搜索查询语法 （在所选搜索的详细信息窗格中），最好在搜索查询是您的用途。在搜索查询中的详细信息窗格中显示在**查询**下，使用文本 **(c:s)** 分隔的关键字。 这表示关键字进行连接的**OR**运算符。同样，如果您的搜索查询包含条件，关键字和条件使用分隔文本 **(c:c)**。 这表示关键字进行连接的情况的**AND**运算符。下面是一个示例 （显示详细信息窗格中） 的搜索查询的结果时使用关键字列表和条件。 
    
    ![使用关键字列表和条件时创建的查询的示例](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
  - 如果您有包含非英文字符 （例如中文字符） 的关键字的搜索查询，您可能需要使用**集 ComplianceSearch** cmdlet 可以配置内容搜索的语言属性。当您创建内容搜索中安全使用 GUI&amp;合规中心的默认语言是中性。 
    
    您如何知道您是否需要更改内容的搜索的语言设置？如果您是某些内容位置包含要搜索的非英语字符，但搜索未返回任何结果，则可能原因的语言设置。
    
    若要更改现有的内容搜索的语言设置，请运行以下命令在安全&amp;合规性中心 PowerShell:
    
  ```
  Set-ComplianceSearch <name of content search> -Language <culture code value>
  ```

    例如，若要更改为中文语言设置，需要使用`zh-CN`区域性代码值。更改语言设置后，您将需要重新运行搜索。可能的区域性代码值的列表，请参阅[CultureInfo 类](https://go.microsoft.com/fwlink/p/?LinkID=184859)。内容搜索，我们建议您的语言设置; 的值使用两部分区域性代码例如， `ja-JP` ，而不`ja`。
    

  
 **搜索的非活动邮箱**
  
如前面所述，您可以在内容搜索中搜索非活动邮箱。下面是要搜索非活动邮箱时，请记住的几个事项。
  
- 如果内容搜索包含用户邮箱，并且该邮箱由处于非活动状态，内容搜索将继续在它变为非活动状态后重新运行搜索时搜索非活动邮箱。
    
- 在某些情况下，用户可能有活动邮箱和非活动邮箱，具有相同的 SMTP 地址。在这种情况下，将搜索仅特定邮箱的选择作为内容搜索的位置。换句话说，如果您将用户邮箱添加到搜索，您不能假设，将搜索其活动和非活动邮箱;将搜索的明确添加到搜索邮箱。
    
- 我们强烈建议您避免使用活动邮箱和非活动邮箱具有相同的 SMTP 地址。如果您需要重用当前分配给非活动邮箱的 SMTP 地址，我们建议恢复非活动邮箱或非活动邮箱的内容还原到活动邮箱 （或活动邮箱的存档），然后删除非活动邮箱。有关详细信息，请参阅以下主题：
    
  - [恢复 Office 365 中的非活动邮箱](recover-an-inactive-mailbox.md)
    
  - [还原 Office 365 中的非活动邮箱](restore-an-inactive-mailbox.md)
    
  - [删除 Office 365 中的非活动邮箱](delete-an-inactive-mailbox.md)
    

  
 **其他**
  
- 内容在安全的**内容搜索**页上创建搜索&amp;合规性中心不会显示在**就地电子数据展示&amp;保留**Exchange 管理中心中的页。这是因为安全中创建的内容搜索体系结构和的搜索对象&amp;合规性中心是完全不同于 Exchange Online 中的就地电子数据展示功能。 
    
    同样，搜索**内容的搜索**页上创建不会显示在**搜索**页上的安全中电子数据展示事例&amp;合规性中心。 
    
- 重新启动和重新尝试搜索之间的区别是什么？重新启动搜索后，在搜索中指定的所有内容位置中新的预览搜索再次搜索。但是，您重试搜索，唯一的搜索上次运行时失败的内容的位置会搜索再次。
   

