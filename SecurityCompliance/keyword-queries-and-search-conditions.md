---
title: 内容搜索的关键字查询和搜索条件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: '了解可以使用 Office 365 安全&amp;合规中心中的内容搜索工具在 Exchange Online 邮箱和 SharePoint 或 OneDrive for business 网站中搜索的电子邮件和文件属性。  '
ms.openlocfilehash: b3d0e7bb18513765c48bfc5ca324f13e5abc4c27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214072"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>内容搜索的关键字查询和搜索条件

本主题介绍了在 Exchange Online 中的电子邮件项目和在 SharePoint 和 OneDrive for business 网站上使用内容搜索功能在 SharePoint 和 OneDrive for business 网站上搜索的电子邮件和文档属性&amp; 。在 Office 365 安全合规性中使用内容搜索功能置.您还可以在安全&amp;合规中心 PowerShell 中使用** \*-new-compliancesearch** cmdlet 搜索这些属性。本主题还介绍了以下内容:   
  
- 使用布尔搜索运算符、搜索条件和其他搜索查询技术来优化搜索结果。
    
- 在 SharePoint 和 OneDrive for business 中搜索敏感数据类型和自定义敏感数据类型。
    
- 搜索与组织外部用户共享的网站内容
    
有关如何创建内容搜索的分步说明, 请参阅[Office 365 中的内容搜索](content-search.md)。

  
> [!NOTE]
> 安全&amp;合规性中心中的内容搜索和安全&amp;合规性中心 PowerShell 中的相应** \*-new-compliancesearch** cmdlet 使用关键字查询语言 (KQL)。有关更多详细信息, 请参阅[关键字查询语言语法参考](https://go.microsoft.com/fwlink/?LinkId=269603)。 
  
## <a name="searchable-email-properties"></a>可搜索的电子邮件属性

下表列出了可以使用安全&amp;合规性中心中的内容搜索功能或通过使用**new-compliancesearch**或**new-compliancesearch** cmdlet 搜索的电子邮件属性。该表包括属性的一个示例: 每个属性的_值_语法和示例返回的搜索结果的说明。您可以在 " `property:value`关键字" 框中为内容搜索键入这些对。 
  
|**属性**|**属性描述**|**示例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames|附加到电子邮件的文件名称。|`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual*`|含有名为 annualreport.ppt 的附加文件的邮件。在第二个示例中，使用通配符返回附件名中带有单词“annual”的邮件。|
|Bcc|电子邮件的"密件抄送"字段。<sup>1</sup>|`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`|所有示例都返回"密件抄送"字段中包含"Pilar Pinilla"的邮件。|
|Category| 要搜索的类别。用户可以使用 outlook 或 web 上的 outlook (以前称为 Outlook web App) 定义类别。可能的值为:  <br/><br/>  蓝色  <br/>  绿色  <br/>  橙色  <br/>  紫色  <br/>  红色  <br/>  黄色|`category:"Red Category"`|在源邮箱中已指定红色类别的邮件。|
|抄送|电子邮件的"抄送"字段。<sup>1</sup>|`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`|在以上两个示例中，在"抄送"字段中指定了含有"Pilar Pinilla"的邮件。|
|Folderid|特定邮箱文件夹的文件夹 ID (GUID)。如果使用此属性, 请务必搜索指定文件夹所在的邮箱。请注意, 将仅搜索指定的文件夹。不会搜索文件夹中的所有子文件夹。若要搜索子文件夹, 您需要使用要搜索的子文件夹的 Folderid 属性。<br/> 有关搜索 Folderid 属性和使用脚本获取特定邮箱的文件夹 id 的详细信息, 请参阅[在 Office 365 中使用内容搜索查找目标集合](use-content-search-for-targeted-collections.md)。|`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`|第一个示例返回指定邮箱文件夹中的所有项目。第二个示例返回指定邮箱文件夹中由 garthf@contoso.com 发送或接收的所有项目。|
|发件人|电子邮件的发件人。<sup>1</sup>|`from:pilarp@contoso.com`  <br/> `from:contoso.com`|由指定用户或指定域发送的邮件。|
|HasAttachment|指示邮件是否包含附件。使用值**true**或**false**。|`from:pilar@contoso.com AND hasattachment:true`|由指定用户发送的包含附件的邮件。|
|Importance|发件人在发送邮件时可以指定的电子邮件的重要性。默认情况下, 邮件以正常重要性发送, 除非发件人将重要性设置为**高**或**低**。|`importance:high`  <br/> `importance:medium`  <br/> `importance:low`|将重要性标记为高、中等或低的邮件。|
|IsRead|指示是否已读取邮件。使用值**true**或**false**。|`isread:true`  <br/> `isread:false`|第一个示例返回 IsRead 属性设置为**True**的邮件。第二个示例返回 IsRead 属性设置为**False**的邮件。|
|ItemClass|使用此属性可搜索组织导入到 Office 365 中的特定第三方数据类型。对此属性使用以下语法:`itemclass:ipm.externaldata.<third-party data type>*`|`itemclass:ipm.externaldata.Facebook* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter* AND from:"Ann Beebe" AND "Northwind Traders"`|第一个示例返回在 Subject 属性中包含 "contoso" 一词的 Facebook 项目。第二个示例返回由王小姐 Beebe 发布且包含关键字短语 "罗斯文商贸" 的 Twitter 项目。<br/> 有关 ItemClass 属性的第三方数据类型要使用的值的完整列表, 请参阅[使用内容搜索来搜索导入到 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)。|
|Kind| 要搜索的电子邮件的类型。可能的值:  <br/>  联系人  <br/>  文档  <br/>  电子邮件  <br/>  externaldata  <br/>  传真  <br/>  即时消息  <br/>  日志  <br/>  会议  <br/>  microsoftteams (返回 Microsoft 团队中的聊天、会议和呼叫中的项目)  <br/>  注释  <br/>  公告  <br/>  RSS 源  <br/>  任务  <br/>  语音邮件|`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`|第一个示例返回满足搜索条件的电子邮件。第二个示例返回电子邮件、即时消息对话 (包括 Microsoft 团队中的 Skype for business 对话和聊天) 以及符合搜索条件的语音邮件。第三个示例返回从第三方数据源 (如 Twitter、Facebook 和 Cisco Jabber) 导入到 Office 365 中的邮箱的项目, 这些项目符合搜索条件。有关详细信息, 请参阅[在 Office 365 中存档第三方数据](https://go.microsoft.com/fwlink/p/?linkid=716918)。|
|参与者|电子邮件中的所有人员字段；这些字段分别为：发件人、收件人、抄送和密件抄送。<sup>1</sup>|`participants:garthf@contoso.com`  <br/> `participants:contoso.com`|发送自/到 garthf@contoso.com 的邮件。第二个示例返回 contoso.com 域中的用户发送的所有邮件或发送至 contoso.com 域中的用户的所有邮件。|
|Received|收件人接收电子邮件的日期。|`received:04/15/2016`  <br/> `received>=01/01/2016 AND received<=03/31/2016`|2016年4月15日收到的邮件。第二个示例返回在2016年1月1日到2016年3月31日之间收到的所有邮件。|
|收件人|电子邮件中的所有收件人字段；这些字段分别为：收件人、抄送和密件抄送。<sup>1</sup>|`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`|发送到 garthf@contoso.com 的邮件。第二个示例返回发送至 contoso.com 域中任何收件人的邮件。|
|Sent|发件人发送电子邮件的日期。|`sent:07/01/2016`  <br/> `sent>=06/01/2016 AND sent<=07/01/2016`|在指定日期或指定日期范围内发送的邮件。|
|Size|邮件的大小（以字节为单位）。|`size>26214400`  <br/> `size:1..1048567`|大于25的邮件？？10mb.第二个示例返回大小介于1到1048567字节 (1 MB) 之间的邮件。|
|Subject|电子邮件主题行中的文本。  <br/> **注意:** 在查询中使用 Subject 属性时, ???the 搜索将返回 "主题" 行中包含您要搜索的文本的所有邮件。换言之, 查询不会仅返回那些具有完全匹配的邮件。例如, 如果您搜索`subject:"Quarterly Financials"`, 则结果将包含主题为 "季度财务 2018" 的邮件。|`subject:"Quarterly Financials"`  <br/> `subject:northwind`|在主题行文本中的任意位置包含短语 "季度财务" 的邮件。第二个示例返回主题行中包含 "northwind" 一词的所有邮件。|
|收件人|电子邮件的"收件人"字段。<sup>1</sup>|`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`|所有示例返回在"收件人:"行中指定为 Ann Beebe 的邮件。|
   
> [!NOTE]
> <sup>1</sup>对于收件人属性的值, 可以使用电子邮件地址 (也称为 "*用户主体名称*" 或 "UPN")、"显示名称" 或 "别名" 来指定用户。例如, 您可以使用 annb@contoso.com、annb 或 "王小姐 Beebe" 来指定用户王小姐 Beebe。<br/><br/>在搜索任何收件人属性 (发件人、收件人、抄送、密件抄送、参与者和收件人) 时, Office 365 将尝试通过在 Azure Active Directory 中进行查找来扩展每个用户的标识。 如果用户在 Azure Active Directory 中找到, 则查询将扩展, 以包含用户的电子邮件地址 (或 UPN)、别名、显示名称和 LegacyExchangeDN。<br/><br/>例如, `participants:ronnie@contoso.com`扩展到`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`的查询。

## <a name="searchable-site-properties"></a>可搜索网站属性

下表列出了一些 SharePoint 和 OneDrive for business 属性, 可以使用安全&amp;合规性中心中的内容搜索功能搜索, 或者通过使用**new-compliancesearch**或**new-compliancesearch** cmdlet。该表包括属性的一个示例: 每个属性的_值_语法和示例返回的搜索结果的说明。 
  
有关可搜索的 SharePoint 属性的完整列表, 请参阅[sharepoint 中的已爬网和托管属性概述](https://go.microsoft.com/fwlink/p/?LinkId=331599)。可以在可**查询**的列中搜索 **"是" 标记为 "是"** 的属性。 
  
|**属性**|**属性描述**|**示例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|Author|Office 文档中的 "作者" 字段, 这是在复制文档时保持的。例如, 如果用户创建一个文档, 并将其发送给其他人, 然后再将其上载到 SharePoint, 则该文档仍将保留原作者。请务必对此属性使用用户的显示名称。|`author:"Garth Fort"`|所有文档的作者均为 Garth Fort。|
|ContentType|项目的 SharePoint 内容类型, 如项目、文档或视频。|`contenttype:document`|将返回所有文档。|
|Created|创建项目的日期。|`created\>=06/01/2016`|在2016年6月1日或之后创建的所有项目。|
|CreatedBy|创建或上传项目的人员。请务必对此属性使用用户的显示名称。|`createdby:"Garth Fort"`|所有项目均由 Garth Fort 创建或上载。|
|DetectedLanguage|项目的语言。|`detectedlanguage:english`|所有项目均为英语。|
|FileExtension|文件的扩展名;例如, .docx、one、.pptx 或 .xlsx。|`fileextension:xlsx`|所有 excel 文件 (excel 2007 及更高版本)|
|FileName|文件的名称。|`filename:"marketing plan"`  <br/> `filename:estimate`|第一个示例返回标题中具有完全匹配短语“marketing plan”的文件。第二个示例返回文件名中具有单词“estimate”的文件。|
|LastModifiedTime|项目的上次更改日期。|`lastmodifiedtime>=05/01/2016`  <br/> `lastmodifiedtime>=05/10/2016 AND lastmodifiedtime<=06/1/2016`|第一个示例返回在2016年5月1日或之后更改的项。第二个示例返回在5月1日、2016和6月1日之间更改的项目2016。|
|ModifiedBy|上次更改项目的人员。请务必对此属性使用用户的显示名称。|`modifiedby:"Garth Fort"`|由 Garth Fort 最后更改的所有项目。|
|路径|SharePoint 或 OneDrive for business 网站上特定文件夹的路径 (URL)。如果使用此属性, 请务必搜索指定文件夹所在的网站。<br/> 若要返回在为 path 属性指定的文件夹中的子文件夹中的项目, 您必须添加/\*到指定文件夹的 URL。例如,`path: "https://contoso.sharepoint.com/Shared Documents/*"`  <br/> <br/> **注意:** 使用该`Path`属性搜索 OneDrive 位置不会在搜索结果中返回媒体文件, 如 .png、tiff 或 .wav 文件。在搜索查询中使用不同的 site 属性搜索 OneDrive 文件夹中的媒体文件。<br/> <br/> 有关搜索 Path 属性和使用脚本获取特定网站上的文件夹的路径 url 的详细信息, 请参阅[在 Office 365 中使用内容搜索查找目标集合](use-content-search-for-targeted-collections.md)。|`path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private"`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/*" AND filename:confidential`|第一个示例返回指定的 OneDrive for business 文件夹中的所有项目。第二个示例在指定的网站文件夹 (和所有子文件夹) 中返回文件名中包含单词 "保密信息" 的文档。|
|SharedWithUsersOWSUser|与指定用户共享并显示在用户的 OneDrive for business 网站中的 "**与我共享**" 页上的文档。这些文档已与组织中的其他人员明确与指定的用户共享。当您导出与使用 SharedWithUsersOWSUser 属性的搜索查询匹配的文档时, 文档将从与指定用户共享文档的人员的原始内容位置导出。有关更多详细信息, 请参阅[搜索组织中共享的网站内容](keyword-queries-and-search-conditions.md#internal)。|`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`|这两个示例都将返回所有已与 Garth Fort 显式共享且显示在 Garth Fort 的 OneDrive for business 帐户中的 "**与我共享**" 页上的内部文档。|
|Site|组织中站点或站点组的 URL。|`site:"https://contoso-my.sharepoint.com"`  <br/> `site:"https://contoso.sharepoint.com/sites/teams"`|第一个示例返回组织中所有用户的 OneDrive for business 网站中的项目。第二个示例返回所有团队网站中的项。|
|Size|邮件的大小（以字节为单位）。|`size>=1`  <br/> `size:1..10000`|第一个示例返回大于 1 字节的项目。第二个示例返回大小介于 1 到 10,000 字节之间的项目。|
|标题|文档的标题。Title 属性是在 Microsoft Office 文档中指定的元数据。它不同于文档的文件名。|`title:"communication plan"`|Office 文档的 Title 元数据属性中包含短语“communication plan”的任何文档。|
   
## <a name="searchable-contact-properties"></a>可搜索联系人属性

下表列出了已编制索引且您可以搜索使用内容搜索的联系人属性。这些是可供用户为位于用户邮箱的个人通讯簿中的联系人配置的属性 (也称为 "个人联系人")。若要搜索联系人, 可以选择要搜索的邮箱, 然后在关键字查询中使用一个或多个联系人属性。
  
> [!TIP]
> 若要搜索包含空格或特殊字符的值, 请使用双引号 ("") 来包含短语;例如, `businessaddress:"123 Main Street"`。 
  
|**属性**|**属性描述**|
|:-----|:-----|
|BusinessAddress|"**商务地址**" 属性中的地址。该属性也称为 "联系人属性" 页上的 "**工作**地址"。|
|BusinessPhone|任何**业务电话**号码属性中的电话号码。|
|CompanyName|**Company**属性中的名称。|
|部门|**部门**属性中的名称。|
|DisplayName|联系人的显示名称。这是联系人的 "**全名**" 属性中的名称。|
|EmailAddress|联系人的任何电子邮件地址属性的地址。请注意, 用户可以添加联系人的多个电子邮件地址。使用此属性将返回与联系人的任何电子邮件地址相匹配的联系人。|
|FileAs|**File as**属性。此属性用于指定联系人在用户的联系人列表中的列出方式。例如, 可以将联系人列为*firstname、lastname*或*lastname、名字*。|
|GivenName|" **First name** " 属性中的名称。|
|HomeAddress|任何 "**住宅**地址" 属性中的地址。|
|HomePhone|任何 "**住宅**电话号码" 属性中的电话号码。|
|IMAddress|IM 地址属性, 通常是用于即时消息的电子邮件地址。|
|称谓|**中间**名属性中的名称。|
|MobilePhone|"**移动**电话号码" 属性中的电话号码。|
|Nickname|**昵称**属性中的名称。|
|OfficeLocation|**office**或**office location**属性中的值。|
|OtherAddress|**其他**地址属性的值。|
|Surname|" **Last** name" 属性中的名称。|
|标题|"职务" 属性**** 中的标题。|
   

## <a name="searchable-sensitive-data-types"></a>可搜索敏感数据类型

您可以使用安全&amp;合规中心中的内容搜索功能来搜索存储在 SharePoint 和 OneDrive for business 网站上的文档中的敏感数据 (如信用卡号或社会保险号)。可以通过在关键字查询中使用`SensitiveType`属性和敏感信息类型的名称来执行此操作。例如, 查询`SensitiveType:"Credit Card Number"`返回包含信用卡号的文档。查询`SensitiveType:"U.S. Social Security Number (SSN)"`返回包含美国社会保险号的文档。若要查看您可以搜索的敏感数据类型的列表, &amp;请转到安全合规性中心中的 "**分类** \> **敏感信息类型**"。或者, 您可以使用**** 安全&amp;合规中心 PowerShell 中的 DlpSensitiveInformationType cmdlet 来显示敏感信息类型的列表。 
  
您还可以使用`SensitiveType`属性来搜索您 (或其他管理员) 为您的组织创建的自定义敏感信息类型的名称。请注意, &amp;您可以使用安全合规性中心 (或 PowerShell 中的**Publisher**属性) 中的 "**敏感信息类型**" 页上的 "**发布者**" 列来区分内置和自定义的敏感信息类型。有关详细信息, 请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。
  
有关使用`SensitiveType`属性创建查询的详细信息, 请参阅[窗体 a 查询来查找存储在网站上的敏感数据](form-a-query-to-find-sensitive-data-stored-on-sites.md)。
  
## <a name="search-operators"></a>搜索运算符

布尔搜索运算符 (如**AND**、 **OR**和**NOT**) 可帮助您通过在搜索查询中包含或排除特定单词来定义更精确的搜索。其他技术 (如使用属性运算符 (如\>= 或.)、引号、括号和通配符) 可帮助您优化搜索查询。下表列出了可用于缩小或拓宽搜索结果范围的运算符。 
  
|**运算符**|**用法**|**说明**|
|:-----|:-----|:-----|
|AND|keyword1 AND keyword2|返回包含所有指定关键字或`property:value`表达式的项。例如, `from:"Ann Beebe" AND subject:northwind`将返回王小姐 Beebe 发送的所有邮件, 其中包含 "主题" 行中的 "罗斯文" 一词。<sup>2</sup>|
|+|keyword1 + keyword2 + keyword3|返回包含** `keyword2`或`keyword3` ** 同时包含的项目`keyword1`。因此, 此示例等同于查询`(keyword2 OR keyword3) AND keyword1`。  <br/> 请注意, 该`keyword1 + keyword2`查询 ( **+** 符号后面有一个空格) 与使用 * * 和 * * 运算符的作用不同。此查询等效于`"keyword1 + keyword2"`并返回精确阶段`"keyword1 + keyword2"`的项。|
|OR|keyword1 OR keyword2|返回包含一个或多个指定关键字或`property:value`表达式的项。<sup>2</sup>|
|NOT|keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> 不是种类: im|排除由关键字或`property:value`表达式指定的项目。在第二个示例中, 排除王小姐 Beebe 发送的邮件。第三个示例排除了所有即时消息对话, 例如保存到对话历史记录邮箱文件夹中的 Skype for business 对话。<sup>2</sup>|
|-|keyword1 -keyword2|与**NOT**运算符相同。因此, 此查询将返回包含`keyword1`和将排除包含`keyword2`的项的项。|
|NEAR|keyword1 NEAR(n) keyword2|返回彼此接近的单词, 其中 n 表示单词的数量相隔。例如, `best NEAR(5) worst`返回任何一个 "最差" 为 "最佳" 的五个字中的项。如果未指定任何数字, 则默认距离为8个字。<sup>2</sup>|
|ONEAR|keyword1 ONEAR(n) keyword2|类似于**near**, 但以指定的顺序返回彼此相邻的单词的项。例如, `best ONEAR(5) worst`返回在单词 "最差" 之前出现 "最佳" 的任何项目, 并且两个单词在彼此之间的五个单词之间。如果未指定任何数字, 则默认距离为8个字。<sup>2</sup> <br/> > [!NOTE]> 搜索邮箱时不支持**ONEAR**运算符;它仅在搜索 SharePoint 和 OneDrive for business 网站时有效。如果要在同一搜索中搜索邮箱和网站, 并且查询包含**ONEAR**运算符, 则搜索将返回邮箱项目, 就像您使用的是**NEAR**运算符一样。换言之, 搜索返回的项目, 其中指定的单词彼此接近, 而不考虑单词出现的顺序。|
|:|property:value|冒号 (:)在语法`property:value`中, 指定要搜索的属性的值包含指定的值。例如, `recipients:garthf@contoso.com`返回发送到 garthf@contoso.com 的任何消息。|
|=|property=value|与 **:** 运算符相同。|
|\<|property\<value|表示正在搜索的属性小于指定的值。<sup>1</sup>|
|\>|property\>value|表示正在搜索的属性大于指定的值。<sup>1</sup>|
|\<=|property\<=value|表示正在搜索的属性小于等于指定的值。<sup>1</sup>|
|\>=|property\>=value|表示正在搜索的属性大于等于指定的值。<sup>1</sup>|
|..|属性: value1。value2|表示正在搜索的属性大于等于 value1，小于等于 value2。<sup>1</sup>|
|"  "|"fair value"  <br/> subject:"Quarterly Financials"|使用双引号 ("") 搜索关键字和`property:value`搜索查询中的确切短语或字词。|
|\*|cat\*  <br/> subject:set\*|前缀通配符搜索 (星号放在单词末尾) 匹配关键字或`property:value`查询中的零个或多个字符。例如, `title:set*`返回文档标题中包含 word set、setup 和 setting (以及以 "set" 开头的其他单词) 的文档。<br/><br/> **注意:** 只能使用前缀通配符搜索;例如, **cat\* **或**set\***。后缀搜索 ( ** \*cat** )、中缀搜索 **(\*c t** ) 和子字符串搜索** \*(\* cat** ) 不受支持。|
|(  )| (fair OR free) AND (from:contoso.com)  <br/> (IPO OR initial) AND (stock OR shares)  <br/> (quarterly financials)|括号将布尔短语、 `property:value` 项目和关键字结合到一起。例如，  `(quarterly financials)` 返回包含单词"quarterly"和"financials"的项目。  |
   
> [!NOTE]
> <sup>1</sup> 为含有日期或数值的属性使用此运算符。<br/> <sup>2</sup>布尔搜索运算符必须为大写形式;例如**和**。如果使用小写运算符 (例如**和**), 它将被视为搜索查询中的关键字。 
  
## <a name="search-conditions"></a>搜索条件

您可以向搜索查询中添加条件以缩小搜索范围, 并返回一组更细化的结果。每个条件都会向 KQL 搜索查询中添加一个子句, 该子句在您开始搜索时创建并运行。
  
[通用属性的条件 ](#conditions-for-common-properties)

[邮件属性的条件](#conditions-for-mail-properties)

[文档属性的条件](#conditions-for-document-properties)

[与条件一起使用的运算符](#operators-used-with-conditions)

[使用条件的准则](#guidelines-for-using-conditions)

[示例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>通用属性的条件 

使用通用属性在同一搜索中搜索邮箱和网站时创建条件。下表列出了添加条件时要使用的可用属性。
  
|**条件**|**说明**|
|:-----|:-----|
|日期|对于电子邮件, 收件人接收邮件或发件人发送邮件的日期。对于文档, 是上次修改文档的日期。|
|发件人/作者|对于电子邮件, 发送邮件的人。对于文档, 是在 "作者" 字段中从 Office 文档中引用的人。可以键入多个名称, 以逗号分隔。两个或多个值通过**or**运算符逻辑连接。|
|大小 (以字节为单位)|对于电子邮件和文档而言，是项目的大小（以字节为单位）。|
|主题/标题|对于电子邮件, 邮件的主题行中的文本。对于文档, 为文档的标题。如上文所述, Title 属性是在 Microsoft Office 文档中指定的元数据。您可以键入多个主题/标题的名称, 以逗号分隔。两个或多个值通过**or**运算符逻辑连接。|
|合规性标记|对于电子邮件和文档, 已由用户手动分配的标签策略或标签自动分配给邮件和文档的标签。标签用于根据标签定义的分类对电子邮件和文档进行分类, 并强制执行保留规则。您可以键入部分标签名称并使用通配符或键入完整的标签名称。有关详细信息, 请参阅[Office 365 中的标签概述](labels.md)。|
  
### <a name="conditions-for-mail-properties"></a>邮件属性的条件

搜索邮箱或公用文件夹时使用邮件属性创建条件。下表列出了可以用于条件的电子邮件属性。请注意，这些属性是先前描述的电子邮件属性的子集；为了方便你使用，这里将重复这些说明。
  
|**条件**|**说明**|
|:-----|:-----|
|邮件类型| 要搜索的邮件类型。这与 Kind 电子邮件属性的属性相同。可能的值:  <br/><br/>  联系人  <br/>  文档  <br/>  电子邮件  <br/>  externaldata  <br/>  传真  <br/>  即时消息  <br/>  日志  <br/>  会议  <br/>  microsoftteams  <br/>  注释  <br/>  公告  <br/>  RSS 源  <br/>  任务  <br/>  语音邮件|
|Participants|电子邮件中的所有人员字段；这些字段分别为：发件人、收件人、抄送和密件抄送。|
|类型|电子邮件项目的邮件类属性。这是 ItemClass 电子邮件属性的相同属性。它也是一个多值条件。因此, 若要选择多个邮件类, 请按住**CTRL**键, 然后在下拉列表中单击要添加到条件的两个或多个邮件类。在列表中选择的每个邮件类别将在相应的搜索查询中通过**OR**运算符逻辑连接。<br/> 有关 Exchange 使用的邮件类别 (及其相应的邮件类 ID) 的列表, 可以在**邮件类**列表中选择, 请参阅[项目类型和邮件类](https://go.microsoft.com/fwlink/?linkid=848143)。|
|Received|收件人接收电子邮件的日期。此属性与“Received”电子邮件属性相同。|
|收件人|向其发送电子邮件的人员。这是与电子邮件属性相同的属性。|
|Sender|电子邮件的发件人。|
|Sent|发件人发送电子邮件的日期。这与已发送的电子邮件属性的属性相同。|
|Subject|电子邮件主题行中的文本。|
|收件人|电子邮件的收件人。|
  
### <a name="conditions-for-document-properties"></a>文档属性的条件

在 SharePoint 和 OneDrive for business 网站上搜索文档时使用文档属性创建条件。下表列出了可用于条件的文档属性。请注意, 这些属性是之前所述的网站属性的子集;为方便起见, 将重复这些说明。
  
|**条件**|**说明**|
|:-----|:-----|
|Author|Office 文档中的 "作者" 字段, 这是在复制文档时保持的。例如, 如果用户创建一个文档, 并将其发送给其他人, 然后再将其上载到 SharePoint, 则该文档仍将保留原作者。|
|标题|文档的标题。Title 属性是在 Office 文档中指定的元数据。它与文档的文件名不同。|
|已创建|创建文档的日期。|
|上次修改时间|上次修改文档的日期。|
|文件类型|文件的扩展名;例如, .docx、one、.pptx 或 .xlsx。这与文件扩展名网站属性的属性相同。|
  
### <a name="operators-used-with-conditions"></a>与条件一起使用的运算符

当您添加一个条件时，您可以选择与该条件的属性类型相关的运算符。下表描述了与条件一起使用的运算符，并列出了在搜索查询中使用的等效项。
  
|**运算符**|**查询等效项**|**说明**|
|:-----|:-----|:-----|
|之后|`property>date`|使用日期条件。返回在指定日期后发送、接收或修改的项。 |
|之前|`property<date`|使用日期条件。返回在指定日期前发送、接收或修改的项。|
|介于|`date..date`|与日期和大小条件一起使用。在与日期条件一起使用时, 返回在指定日期范围内已发送、接收或修改的项。当与大小条件一起使用时, 将返回大小在指定范围内的项目。|
|包含任意|`(property:value) OR (property:value)`|与用于指定字符串值的属性的条件一起使用。返回包含一个或多个指定的字符串值的任何部分的项。|
|不包含任何|`-property:value`  <br/> `NOT property:value`|与指定字符串值的属性条件一起使用。返回不包含指定字符串值任何部分的项目。|
|不等于任何
|`-property=value`  <br/> `NOT property=value`|与指定字符串值的属性条件一起使用。返回不包含特定字符串的项目。|
|等于|`size=value`|返回与指定大小相等的项目。<sup>1</sup>|
|等于任何|`(property=value) OR (property=value)`|与指定字符串值的属性条件一起使用。返回完全匹配一个或多个指定字符串值的项目。|
|大于|`size>value`|返回指定属性大于指定值的项。<sup>1</sup>|
|大于或等于|`size>=value`|返回指定属性大于或等于指定值的项。<sup>1</sup>|
|小于|`size<value`|返回大于或等于指定值的项。<sup>1</sup>|
|小于或等于|`size<=value`|返回大于或等于指定值的项。<sup>1</sup>|
|不等于|`size<>value`| 返回与指定大小不相等的项目。<sup>1</sup>|
   
> [!NOTE]
> <sup>1</sup>此运算符仅适用于使用 Size 属性的条件。 
  
### <a name="guidelines-for-using-conditions"></a>使用条件的准则

在使用搜索条件时，请牢记以下几点。
  
- **and**运算符在逻辑上将一个条件连接到关键字查询 (在关键字框中指定)。这意味着项目必须同时满足关键字查询和条件才能包含在结果中。这就是条件如何帮助缩小结果范围的方法。 
    
- 如果向搜索查询添加两个或更多个唯一条件 (指定不同属性的条件), 则这些条件通过**AND**运算符逻辑连接。这意味着只返回满足所有条件的项目 (除了 any 关键字查询)。 
    
- 如果为同一个属性添加多个条件, 则这些条件将通过**OR**运算符逻辑连接。这意味着满足关键字查询和任意一个条件的项目将返回。因此, 通过**OR**运算符将相同条件的组相互连接, 然后由**and**运算符连接不同条件的集合。 
    
- 如果将多个值 (用逗号或分号分隔) 添加到单个条件中, 则这些值由**or**运算符连接。这意味着, 如果在条件中包含任何指定的属性值, 则将返回项目。 
    
- 使用 "关键字" 框和条件创建的搜索查询将显示在 "**搜索**" 页上所选搜索的详细信息窗格中。在查询中, 表示法`(c:c)`右侧的一切都表示添加到查询中的条件。 
    
- 条件仅向搜索查询添加属性;不添加运算符。这就是在详细信息窗格中显示的查询不显示`(c:c)`表示法右侧的运算符的原因。在执行查询时, KQL 将添加逻辑运算符 (根据前面所述的规则)。 
    
- 可以使用拖放控件将条件顺序重新排序。只需单击控件即可查看条件并将其上移或下移。
    
- 如前所述, 一些条件属性允许您键入多个值。每个值通过**OR**运算符逻辑连接。这将生成相同条件的多个实例的相同逻辑, 其中每个实例都有一个值。下图显示了一个包含多个值的单个条件的示例, 以及一个值为多个条件的示例 (相同的属性)。这两个示例都将产生相同的查询:`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![一个条件具有多个值](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![同一属性的多个搜索条件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果条件接受多个值，则建议您使用一个条件，并指定多个值（用逗号或分号分隔）。这有助于确保所应用的查询逻辑就是您想要的。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>示例

下面的示例展示了包含条件的搜索查询的基于 GUI 的版本、搜索查询语法, 这些语法显示在所选搜索的细节窗格中 (也由**new-compliancesearch** cmdlet 返回), 逻辑对应的 KQL 查询。 
  
#### <a name="example-1"></a>示例 1

本示例返回 SharePoint 和 OneDrive for business 网站上包含信用卡号的文档, 并且在2016年1月1日之前进行了最后修改。
  
 **GUI**
  
![第一个搜索条件示例](media/099515ba-d4ee-474e-af25-3aa48816b87b.gif)
  
 **搜索查询语法**
  
 `SensitiveType:"Credit Card Number(c:c)(lastmodifiedtime<2016-01-01)`
  
 **搜索查询逻辑**
  
 `SensitiveType:"Credit Card Number" AND (lastmodifiedtime<2016-01-01)`
  
#### <a name="example-2"></a>示例 2

本示例返回包含关键字“report”且在 2105 年 4 月 1 日之前发送或创建的电子邮件项目或文档，且电子邮件的主题字段或文档的标题属性中包含词语“northwind”。查询不包括符合其他搜索条件的网页。 
  
 **GUI**
  
![第二个搜索条件示例](media/fe07d495-df81-42da-8106-3cdb409c6e7f.gif)
  
 **搜索查询语法**
  
 `report(c:c)(date<2016-04-01)(subjecttitle:"northwind")(-filetype="aspx")`
  
 **搜索查询逻辑**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>示例 3
<a name="conditionexamples"> </a>

本示例返回在12/1/2016 和11/30/2016 之间发送的、包含以 "phone" 或 "smartphone" 开头的单词的电子邮件或日历会议。
  
 **GUI**
  
![搜索条件示例三](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜索查询语法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜索查询逻辑**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>搜索与外部用户共享的网站内容

您还可以使用安全&amp;合规中心中的内容搜索功能来搜索存储在 SharePoint 和 OneDrive for business 网站上的文档, 这些文档已与组织外部的人员共享。这可以帮助您识别在您的组织外部共享的敏感信息或专有信息。可以通过在关键字查询中使用`ViewableByExternalUsers`属性来执行此操作。此属性将返回使用以下共享方法之一与外部用户共享的文档或网站: 
  
- 要求用户以经过身份验证的用户身份登录组织的共享邀请。
    
- 匿名来宾链接, 它允许具有此链接的任何人访问资源, 而无需进行身份验证。
    
此处为一些示例：
  
- 查询`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`将返回与组织外部的人员共享的所有项目, 并包含信用卡号码。 
    
- 查询`ViewableByExternalUsers:true AND ContentType:document AND site:"https://contoso.sharepoint.com/Sites/Teams"`将返回组织中与外部用户共享的所有团队网站上的文档列表。 
    
> [!TIP]
> 搜索查询 (如`ViewableByExternalUsers:true AND ContentType:document`可能会在搜索结果中返回大量 .aspx 文件)。若要消除这些 (或其他类型的文件), 可以使用`FileExtension`属性排除特定的文件类型;例如`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`。 
  
什么是与组织外部的人员共享的内容？组织的 SharePoint 和 OneDrive for business 网站中的文档, 这些网站通过发送共享邀请或在公共位置共享共享来共享。例如, 以下用户活动将导致外部用户可查看的内容:
  
- 用户与组织外部的人员共享文件或文件夹。

    
- 用户创建共享文件的链接并将其发送给组织外部的人员。此链接允许外部用户查看 (或编辑) 文件。
    
- 用户向组织外部的人员发送共享邀请或来宾链接以查看（或编辑）共享文件。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>使用 ViewableByExternalUsers 属性的问题

虽然该`ViewableByExternalUsers`属性表示文档或网站与外部用户共享的状态, 但对此属性的功能和不反映的情况有一些注意事项。在以下方案中, 不会更新`ViewableByExternalUsers`属性的值, 并且使用此属性的内容搜索查询的结果可能不准确。 
  
- 对共享策略的更改, 例如关闭网站或组织的外部共享。该属性仍会将以前的共享文档显示为外部可访问, 即使外部访问可能已被吊销也是如此。
    
- 对组成员身份的更改, 如向 Office 365 组或 office 365 安全组添加或删除外部用户。对于组有权访问的项目, 该属性不会自动更新。
    
- 向外部用户发送共享邀请, 其中收件人尚未接受邀请, 因此尚未访问内容。
    
在这些情况下, `ViewableByExternalUsers`该属性将不会反映当前的共享状态, 直到重新对网站或文档库进行重新爬网并对其重新编制索引。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜索组织中共享的网站内容

如前所述, 您可以使用`SharedWithUsersOWSUser`属性, 以便搜索组织中的人员之间共享的文档。当某人与组织内的其他用户共享文件 (或文件夹) 时, 共享文件的链接将出现在共享文件的人员的 OneDrive for business 帐户中的 "**与我共享**" 页上。例如, 若要搜索已与 Sara Davis 共享的文档, 可以使用查询`SharedWithUsersOWSUser:"sarad@contoso.com"`。如果导出此搜索的结果, 则会下载原始文档 (位于使用 Sara 共享文档的人员的内容位置)。
  
请注意, 在使用`SharedWithUsersOWSUser`属性时, 必须与特定用户显式共享文档以在搜索结果中返回。例如, 当某个人在其 OneDrive 帐户中共享文档时, 可以选择与任何人 (在组织内部或外部) 共享它, 也可以与组织内的用户共享它, 或与特定人员共享该文档。以下是 OneDrive 中的 "**共享**" 窗口的屏幕截图, 其中显示了三个共享选项。 
  
![使用 SharedWithUsersOWSUser 属性的搜索查询将仅返回与特定人员共享的文件](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
使用`SharedWithUsersOWSUser`属性的搜索查询将仅返回使用第三个选项共享的文档 (与**特定人员**共享)。 

## <a name="searching-for-skype-for-business-conversations"></a>正在搜索 Skype for business 对话

您可以使用以下关键字查询专门搜索 Skype for business 对话中的内容:

```
kind:im
```

注释以前的搜索查询还将从 Microsoft 团队中返回聊天。若要防止出现这种情况, 您可以通过使用以下关键字查询缩小搜索结果, 以仅包括 Skype for business 对话:

```
kind:im AND subject:conversation
```

以前的关键字查询在 Microsoft 团队中排除了聊天, 因为 Skype for business 对话以电子邮件的形式保存, 主题行以单词 "对话" 开头。

若要搜索在特定日期范围内发生的 Skype for business 对话, 请使用以下关键字查询:

```
kind:im AND subject:conversation AND (received=startdate..enddate)
```

## <a name="search-tips-and-tricks"></a>搜索提示和技巧

- 关键字搜索不区分大小写。例如， **cat** 和 **CAT** 将返回相同的结果。 
    
- 布尔运算符**AND**、 **OR**、 **NOT**、 **NEAR**和**ONEAR**必须为大写。 
    
- 两个关键字或两个`property:value`表达式之间的空格与使用**和**相同。例如, 返回`from:"Sara Davis" subject:reorganization`在 "主题" 行中包含 "重组" 一词的 "Sara Davis" 发送的所有邮件。 
    
- 使用与`property:value`格式相匹配的语法。值不区分大小写, 并且在运算符后面不能有空格。如果有空格, 则您的预期值将只是全文搜索。例如`to: pilarp` , 搜索 "pilarp" 作为关键字, 而不是发送到 pilarp 的邮件。 
    
- 在搜索收件人属性（如 To、From、Cc 或 Recipients）时，您可以使用 SMTP 地址、别名或显示名来表示收件人。例如，您可以使用 pilarp@contoso.com、pilarp 或"Pilar Pinilla"。
    
- 只能使用前缀通配符搜索;例如, **cat\* **或**set\***。后缀搜索 ( ** \*cat** )、中缀搜索 **(\*c t** ) 和子字符串搜索** \*(\* cat** ) 不受支持。 
    
- 在搜索属性时, 如果搜索值包含多个单词, 则使用双引号 ("")。例如`subject:budget Q1` , 返回在主题行中包含**预算**的邮件, 并在邮件或任何邮件属性中的任何位置包含**Q1** 。使用`subject:"budget Q1"`返回 "主题" 行中任意位置包含**预算 Q1**的所有邮件。 
    
- 若要从搜索结果中排除标记有某个属性值的内容, 请在该属性名称前面放置一个减号 (-)。例如, `-from:"Sara Davis"`将排除由 Sara Davis 发送的所有邮件。

- 您可以基于邮件类型导出项目。例如, 若要在 Microsoft 团队中导出 Skype 对话和聊天, 请使用`kind:im`语法。若要仅返回电子邮件, 请使用`kind:email`。若要在 Microsoft 团队中返回聊天、会议和呼叫, `kind:microsoftteams`请使用。
