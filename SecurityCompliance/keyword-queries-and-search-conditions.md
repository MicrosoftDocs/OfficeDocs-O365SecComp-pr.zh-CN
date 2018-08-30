---
title: 内容搜索的关键字查询和搜索条件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.SearchQueryLearnMore
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: c4639c2e-7223-4302-8e0d-b6e10f1c3be3
description: '了解电子邮件和文件属性，您可以在 Office 365 安全性使用内容搜索工具的业务网站搜索在 Exchange Online 邮箱和 SharePoint 或 OneDrive&amp;合规性中心。  '
ms.openlocfilehash: c043b6667e6847ff944b05e6bbe91df8ed2f600c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525562"
---
# <a name="keyword-queries-and-search-conditions-for-content-search"></a>内容搜索的关键字查询和搜索条件

本主题介绍您可以在 Exchange Online 和存储在 SharePoint 上的文档中的电子邮件项目中搜索的电子邮件和文档属性和使用 Office 365 安全性中的内容的搜索功能的 OneDrive for Business 站点&amp;合规性中心。您还可以使用**\*-ComplianceSearch**安全性 cmdlet&amp;合规性中心 PowerShell，可以搜索这些属性。主题还介绍： 
  
- 使用布尔搜索运算符、 搜索条件和其他搜索查询技术来优化搜索结果。
    
- 搜索敏感数据类型和 SharePoint 和 OneDrive for Business 中的自定义的敏感数据类型。
    
- 搜索与组织外部的用户共享的网站内容
    
有关如何创建内容的搜索的分步说明，请参阅[Office 365 中的内容搜索](content-search.md)。 |

  
> [!NOTE]
> 内容安全中的搜索&amp;合规性中心和相应**\*-ComplianceSearch**安全性 cmdlet&amp;合规性中心 PowerShell 使用关键字查询语言 (KQL)。有关详细信息，请参阅[关键字查询语言语法参考 （英文）](https://go.microsoft.com/fwlink/?LinkId=269603)。 
  
## <a name="searchable-email-properties"></a>可搜索的电子邮件属性

下表列出了电子邮件属性可通过使用中的安全的内容搜索功能搜索&amp;合规性中心或使用**新建 ComplianceSearch**或**集 ComplianceSearch** cmdlet。表包含每个属性和说明的示例返回的搜索结果的_属性： 值_语法的示例。您可以键入这些`property:value`对关键字中的内容的搜索框。 
  
|**属性**|**属性描述**|**示例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|AttachmentNames  <br/> |附加到电子邮件的文件名称。  <br/> |`attachmentnames:annualreport.ppt`  <br/> `attachmentnames:annual\*`  <br/> |含有名为 annualreport.ppt 的附加文件的邮件。在第二个示例中，使用通配符返回附件名中带有单词“annual”的邮件。  <br/> |
|Bcc  <br/> |电子邮件的"密件抄送"字段。<sup>1</sup> <br/> |`bcc:pilarp@contoso.com`  <br/> `bcc:pilarp`  <br/> `bcc:"Pilar Pinilla"`  <br/> |所有示例都返回"密件抄送"字段中包含"Pilar Pinilla"的邮件。  <br/> |
|Category  <br/> | 搜索类别。用户可以使用 Outlook 或 Outlook Web App 定义类别。可能的值是：  <br/><br/>  蓝色  <br/>  绿色  <br/>  橙色  <br/>  紫色  <br/>  红色  <br/>  黄色  <br/> |`category:"Red Category"`  <br/> |在源邮箱中已指定红色类别的邮件。  <br/> |
|抄送  <br/> |电子邮件的"抄送"字段。<sup>1</sup> <br/> |`cc:pilarp@contoso.com`  <br/> `cc:"Pilar Pinilla"`  <br/> |在以上两个示例中，在"抄送"字段中指定了含有"Pilar Pinilla"的邮件。  <br/> |
|Folderid  <br/> |文件夹的特定邮箱文件夹的 ID (GUID)。如果您使用此属性，请务必搜索指定的文件夹位于中的邮箱。请注意，将搜索指定的文件夹。不会搜索的文件夹中的任何子文件夹。若要搜索的子文件夹，您需要使用要搜索的子文件夹的文件夹 Id 属性。<br/> 关于搜索文件夹 Id 属性和使用脚本来获取特定邮箱的文件夹 Id 的详细信息，请参阅[使用 Office 365 的目标集合中的内容搜索](use-content-search-for-targeted-collections.md)。  <br/> |`folderid:4D6DD7F943C29041A65787E30F02AD1F00000000013A0000`  <br/> `folderid:2370FB455F82FC44BE31397F47B632A70000000001160000 AND participants:garthf@contoso.com`  <br/> |第一个示例返回指定的邮箱文件夹中的所有项目。第二个示例返回指定的邮箱文件夹的已发送或接收的 garthf@contoso.com 中的所有项目。  <br/> |
|发件人  <br/> |电子邮件的发件人。<sup>1</sup> <br/> |`from:pilarp@contoso.com`  <br/> `from:contoso.com`  <br/> |由指定用户或指定域发送的邮件。  <br/> |
|HasAttachment  <br/> |指示邮件包含附件。使用值 **，则返回 true**或**false**。<br/> |`from:pilar@contoso.com AND hasattachment:true`  <br/> |由指定用户发送具有附件的邮件。  <br/> |
|Importance  <br/> |发送邮件时，可以指定发件人电子邮件的重要性。默认情况下，邮件除非发件人将重要性设置**高**或**较低**重要性正常发送。<br/> |`importance:high`  <br/> `importance:medium`  <br/> `importance:low`  <br/> |将重要性标记为高、中等或低的邮件。  <br/> |
|IsRead  <br/> |指示已读消息。使用值 **，则返回 true**或**false**。<br/> |`isread:true`  <br/> `isread:false`  <br/> |第一个示例返回邮件 IsRead 属性设置为**True**。第二个示例返回邮件 IsRead 属性设置为**False**。<br/> |
|ItemClass  <br/> |此属性用于搜索组织导入到 Office 365 的特定第三方数据类型。此属性使用以下语法：`itemclass:ipm.externaldata.<third-party data type>*` <br/> |`itemclass:ipm.externaldata.Facebook\* AND subject:contoso`  <br/> `itemclass:ipm.externaldata.Twitter\* AND from:"Ann Beebe" AND "Northwind Traders"`  <br/> |第一个示例返回 Facebook 项包含单词"contoso"的使用者属性中。第二个示例返回 Twitter 项的已发布的 Ann Beebe 且包含关键字短语"Northwind Traders"。<br/> 用于 ItemClass 属性的第三方数据类型的值的完整列表，请参阅[使用内容搜索的已导入到 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)。  <br/> |
|Kind  <br/> | 若要搜索的电子邮件的类型。可能的值：  <br/>  联系人  <br/>  文档  <br/>  电子邮件  <br/>  externaldata  <br/>  传真  <br/>  即时消息  <br/>  日志  <br/>  会议  <br/>  microsoftteams （从聊天、 会议和呼叫中的 Microsoft 团队返回项）  <br/>  注释  <br/>  公告  <br/>  RSS 源  <br/>  任务  <br/>  语音邮件  <br/> |`kind:email`  <br/> `kind:email OR kind:im OR kind:voicemail`  <br/> `kind:externaldata`  <br/> |第一个示例返回符合搜索条件的邮件。第二个示例返回电子邮件、 即时消息对话和符合搜索条件的语音邮件。第三个示例返回已导入到 Office 365 中的邮箱从第三方数据源，如 Twitter、 Facebook，和 Cisco Jabber，符合搜索条件的项目。有关详细信息，请参阅[Office 365 中的存档第三方数据](https://go.microsoft.com/fwlink/p/?linkid=716918)。<br/> |
|参与者  <br/> |电子邮件中的所有人员字段；这些字段分别为：发件人、收件人、抄送和密件抄送。<sup>1</sup> <br/> |`participants:garthf@contoso.com`  <br/> `participants:contoso.com`  <br/> |发送自/到 garthf@contoso.com 的邮件。第二个示例返回 contoso.com 域中的用户发送的所有邮件或发送至 contoso.com 域中的用户的所有邮件。  <br/> |
|Received  <br/> |收件人接收电子邮件的日期。  <br/> |`received:04/15/2016`  <br/> `received\>=01/01/2016 AND received\<=03/31/2016`  <br/> |2016 年 4 月 15，接收到的邮件。第二个示例返回所有 2016 年 1 月 1，之间 2016 年 3 月 31，接收的消息。  <br/> |
|收件人  <br/> |电子邮件中的所有收件人字段；这些字段分别为：收件人、抄送和密件抄送。<sup>1</sup> <br/> |`recipients:garthf@contoso.com`  <br/> `recipients:contoso.com`  <br/> |发送到 garthf@contoso.com 的邮件。第二个示例返回发送至 contoso.com 域中任何收件人的邮件。  <br/> |
|Sent  <br/> |发件人发送电子邮件的日期。  <br/> |`sent:07/01/2016`  <br/> `sent\>=06/01/2016 AND sent\<=07/01/2016`  <br/> |在指定日期或指定日期范围内发送的邮件。  <br/> |
|Size  <br/> |邮件的大小（以字节为单位）。  <br/> |`size\>26214400`  <br/> `size:1..1048567`  <br/> |邮件大小不超过 25 概览MB。第二个示例返回介于 1 至 1,048,567 字节数 (1 MB) 大小的邮件。  <br/> |
|Subject  <br/> |电子邮件主题行中的文本。  <br/> **注意：** 当您在查询中使用 Subject 属性时，???the 搜索未返回所有邮件的主题行中包含您要搜索的文本。换句话说，查询不返回仅那些具有完全匹配的邮件。例如，如果您搜索`subject:"Quarterly Financials"`，则结果将包括邮件主题为"季度财务 2018"。<br/> |`subject:"Quarterly Financials"`  <br/> `subject:northwind`  <br/> |包含短语"Quarterly Financials"任意位置中的主题行文本的邮件。第二个示例返回包含 word northwind 的主题行中的所有邮件。  <br/> |
|收件人  <br/> |电子邮件的"收件人"字段。<sup>1</sup> <br/> |`to:annb@contoso.com`  <br/> `to:annb ` <br/> `to:"Ann Beebe"`  <br/> |所有示例返回在"收件人:"行中指定为 Ann Beebe 的邮件。  <br/> |
   
> [!NOTE]
> <sup>1</sup>对于收件人属性的值，您可以使用电子邮件地址 （也称为的*用户主体名称*或 UPN）、 显示名称或指定用户的别名。例如，您可以使用 annb@contoso.com、 annb 或"Ann Beebe"可指定 Ann Beebe 的用户。<br/><br/>搜索任意时 Office 365 尝试通过查看展开每个用户的标识 （From、 To、 Cc、 密件抄送、 参与者和收件人） 的收件人属性，其安装在 Azure Active Directory 中。 如果在 Azure Active Directory 中找到该用户，则查询将展开以包括用户的电子邮件地址 （或 UPN），别名、 显示名称和 LegacyExchangeDN。<br/><br/>例如，如查询`participants:ronnie@contoso.com`将扩展到`participants:ronnie@contoso.com OR participants:ronnie OR participants:"Ronald Nelson" OR participants:"<LegacyExchangeDN>"`。

## <a name="searchable-site-properties"></a>可搜索网站属性

下表列出的某些 SharePoint 和 OneDrive 业务属性可通过使用中的安全的内容搜索功能搜索&amp;合规性中心或使用**新建 ComplianceSearch**或**设置 ComplianceSearch** cmdlet。表包含每个属性和说明的示例返回的搜索结果的_属性： 值_语法的示例。 
  
SharePoint 属性可搜索的完整列表，请参阅[Overview of 爬网和托管 SharePoint 中的属性](https://go.microsoft.com/fwlink/p/?LinkId=331599)。可搜索标有**是****可查询**列中的属性。 
  
|**属性**|**属性描述**|**示例**|**示例返回的搜索结果**|
|:-----|:-----|:-----|:-----|
|Author  <br/> |仍然存在，如果复制文档作者字段从 Office 文档。例如，如果用户创建文档和电子邮件它向其他人某人然后将其上载到 SharePoint，文档将仍保留原始作者。请务必使用此属性的用户的显示名称。  <br/> |`author:"Garth Fort"`  <br/> |所有文档的作者均为 Garth Fort。  <br/> |
|ContentType  <br/> |SharePoint 内容类型的项目，如项目、 文档或视频。  <br/> |`contenttype:document`  <br/> |将返回所有文档。  <br/> |
|Created  <br/> |创建项目的日期。  <br/> |`created\>=06/01/2016`  <br/> |创建或 2016 年 6 月 1 之后, 的所有项。  <br/> |
|CreatedBy  <br/> |创建或上载一个项目的人员。请务必使用此属性的用户的显示名称。  <br/> |`createdby:"Garth Fort"`  <br/> |所有项目均由 Garth Fort 创建或上载。  <br/> |
|DetectedLanguage  <br/> |项目的语言。  <br/> |`detectedlanguage:english`  <br/> |所有项目均为英语。  <br/> |
|FileExtension  <br/> |文件; 扩展名例如，docx、 一个、 pptx 或 xlsx。  <br/> |`fileextension:xlsx`  <br/> |所有的 Excel 文件 (Excel 2007 和更高版本)  <br/> |
|FileName  <br/> |文件的名称。  <br/> |`filename:"marketing plan"`  <br/> `filename:estimate`  <br/> |第一个示例返回标题中具有完全匹配短语“marketing plan”的文件。第二个示例返回文件名中具有单词“estimate”的文件。  <br/> |
|LastModifiedTime  <br/> |项目的上次更改日期。  <br/> |`lastmodifiedtime\>=05/01/2016`  <br/> `lastmodifiedtime\>=05/10/2016 AND lastmodifiedtime\<=06/1/2016`  <br/> |第一个示例返回当天或之后 2016 年 5 月 1，已发生更改的项目。第二个示例返回 2016 年 5 月 1 和 2016 年 6 月 1，之间修改的项。  <br/> |
|ModifiedBy  <br/> |上次更改项目的人员。请务必使用此属性的用户的显示名称。  <br/> |`modifiedby:"Garth Fort"`  <br/> |由 Garth Fort 最后更改的所有项目。  <br/> |
|路径  <br/> |上 SharePoint 或 OneDrive for Business 站点的特定文件夹的路径 (URL)。如果您使用此属性，请务必搜索指定的文件夹位于中的网站。<br/> 若要返回位于路径属性指定的文件夹中的子文件夹中的项，您必须添加 /\*到 URL 指定的文件夹中。例如， `path: https://contoso.sharepoint.com/Shared Documents/*`。  <br/> <br/> **注意：** 使用`Path`属性来搜索 OneDrive 位置不会在搜索结果中返回媒体文件，如.png、.tiff 或.wav 文件。使用不同网站属性在搜索查询中搜索 OneDrive 文件夹中的媒体文件。<br/> <br/> 有关为 Path 属性搜索和使用脚本来获取特定网站上的文件夹的路径 Url 的详细信息，请参阅[使用 Office 365 的目标集合中的内容搜索](use-content-search-for-targeted-collections.md)。  <br/> |`path:https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Private`  <br/> `path:"https://contoso-my.sharepoint.com/personal/garthf_contoso_com/Documents/Shared with Everyone/\*" AND filename:confidential`  <br/> |第一个示例返回在指定 OneDrive for Business 文件夹中的所有项。第二个示例返回指定的网站文件夹 （及其所有子文件夹） 中包含单词"confidential"的文件名称中的文档。  <br/> |
|SharedWithUsersOWSUser  <br/> |已与指定的用户共享和显示在用户的 OneDrive for Business 站点**与我共享**页上的文档。这些是已明确共享与指定用户的其他人在组织中的文档。导出的匹配搜索查询使用 SharedWithUsersOWSUser 属性的文档时，文档将导出从与指定的用户共享文档的人员的原始内容的位置。有关详细信息，请参阅[您的组织内共享的搜索网站内容](keyword-queries-and-search-conditions.md#internal)。<br/> |`sharedwithusersowsuser:garthf`  <br/> `sharedwithusersowsuser:"garthf@contoso.com"`  <br/> |这两个示例返回所有内部的文档的已明确共享与李军和的李军的**与我共享**页上显示的 OneDrive for Business 帐户。  <br/> |
|Site  <br/> |组织中站点或站点组的 URL。  <br/> |`site:https://contoso-my.sharepoint.com`  <br/> `site:https://contoso.sharepoint.com/sites/teams`  <br/> |第一个示例返回从 OneDrive for Business 站点的组织中的所有用户的项。第二个示例返回所有工作组网站中的项。  <br/> |
|Size  <br/> |邮件的大小（以字节为单位）。  <br/> |`size\>=1`  <br/> `size:1..10000`  <br/> |第一个示例返回大于 1 字节的项目。第二个示例返回大小介于 1 到 10,000 字节之间的项目。  <br/> |
|Title  <br/> |文档的标题。Title 属性是在 Microsoft Office 文档中指定的元数据。它是文档的不同文件名。  <br/> |`title:"communication plan"`  <br/> |Office 文档的 Title 元数据属性中包含短语“communication plan”的任何文档。  <br/> |
   
## <a name="searchable-contact-properties"></a>搜索联系人属性

下表列出了联系人编制索引的属性和，您可以使用内容搜索中搜索。这些是可供用户为位于用户邮箱的个人通讯簿中的联系人 （也称为个人联系人） 配置的属性。若要搜索联系人，您可以选择要搜索，然后使用关键字查询中的一个或多个联系人的属性的邮箱。
  
> [!TIP]
> 若要搜索的值包含空格，使用双引号 ("??") 包含短语;例如， `businessaddress:"123 Main Street"`。 
  
|**属性**|**属性描述**|
|:-----|:-----|
|BusinessAddress  <br/> |**业务地址**属性中的地址。在联系人的属性页上，属性也称为**工作**地址。<br/> |
|BusinessPhone  <br/> |**商务电话**任一中的电话号码数字属性。  <br/> |
|公司名称  <br/> |在**公司**属性名称。  <br/> |
|Department  <br/> |在**部门**属性名称。  <br/> |
|DisplayName  <br/> |联系人的显示名称。这是该联系人的**完整名称**属性中的名称。<br/> |
|EmailAddress  <br/> |该联系人的任何电子邮件地址属性的地址。请注意，用户可以添加多个联系人的电子邮件地址。使用此属性将返回匹配任何联系人的电子邮件地址的联系人。  <br/> |
|FileAs  <br/> |该**文件另存为**属性。此属性用于指定如何为用户的联系人列表中列出该联系人。例如，无法为*FirstName、 LastName*或*LastName、 FirstName*列出联系人。<br/> |
|GivenName  <br/> |在**名字**属性名称。  <br/> |
|HomeAddress  <br/> |任何**主页**地址属性中的地址。  <br/> |
|住宅电话  <br/> |任何**住宅**电话号码的电话号码数字属性。  <br/> |
|IMAddress  <br/> |IM 地址属性，它通常用于即时消息的电子邮件地址。  <br/> |
|MiddleName  <br/> |**中间**的 name 属性中的名称。  <br/> |
|MobilePhone  <br/> |**移动**电话中的电话号码数字属性。  <br/> |
|Nickname  <br/> |**Nickname**属性中的名称。  <br/> |
|OfficeLocation  <br/> |**Office**或**办公地点**属性中的值。  <br/> |
|OtherAddress  <br/> |**其他**地址属性的值。  <br/> |
|Surname  <br/> |在**最近**的名称属性名称。  <br/> |
|Title  <br/> |**职务**属性中的标题。  <br/> |
   

## <a name="searchable-sensitive-data-types"></a>可搜索敏感数据类型

您可以使用的内容的搜索功能中安全&amp;合规中心的敏感数据，例如信用卡号或社会保险号码，存储在 SharePoint 和 OneDrive 业务网站的文档中的搜索。您可以执行此操作使用`SensitiveType`属性和名称的敏感信息类型关键字查询中。例如，查询`SensitiveType:"Credit Card Number"`返回包含信用卡号的文档。查询`SensitiveType:"U.S. Social Security Number (SSN)"`返回包含美国社会保障号的文档。若要查看可以搜索敏感数据类型的列表，请转到**分类**\>安全中的**敏感信息类型**&amp;合规性中心。您可以使用**Get-DlpSensitiveInformationType** cmdlet 中的安全或者&amp;合规性中心 PowerShell，可以显示的敏感信息类型列表。 
  
您还可以使用`SensitiveType`属性来搜索您 （或其他管理员） 为您的组织创建自定义的敏感信息类型的名称。请注意，可以使用安全中**敏感信息类型**页上的**Publisher**列&amp;合规性中心 （或在 PowerShell 中的**Publisher**属性） 区分内置和自定义敏感信息类型。有关详细信息，请参阅[创建自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)。
  
有关创建使用查询的详细信息`SensitiveType`属性，请参阅[表单查询以查找存储在网站上的敏感数据](form-a-query-to-find-sensitive-data-stored-on-sites.md)。
  
## <a name="search-operators"></a>搜索运算符

布尔搜索运算符，例如**AND**、 **OR**、 和****，帮助您定义更精确搜索包括或排除搜索查询中的特定单词。其他方法，如使用的属性运算符 (如\>= 或...)，引号、 圆括号和通配符，帮助您优化搜索查询。下表列出了可用于缩小或扩大搜索结果范围的运算符。 
  
|**运算符**|**用法**|**说明**|
|:-----|:-----|:-----|
|AND  <br/> |keyword1 AND keyword2  <br/> |返回项目，包括所有指定的关键字或`property:value`表达式。例如，`from:"Ann Beebe" AND subject:northwind`会返回发送包含 word northwind 的主题行中的 Ann Beebe 的所有邮件。<sup>2</sup> <br/> |
|+  <br/> |keyword1 概览+ keyword2 概览+ keyword3  <br/> |返回包含*是*项`keyword2`或`keyword3`*和*还包含`keyword1`。因此，本示例为等同于查询`(keyword2 OR keyword3) AND keyword1`。  <br/> 请注意，查询`keyword1 + keyword2`(与之后的空格**+** 符号) 不相同使用 * * 和 * * 运算符。此查询将等价于`"keyword1 + keyword2"`，并返回项目的确切阶段`"keyword1 + keyword2"`。<br/> |
|OR  <br/> |keyword1 OR keyword2  <br/> |返回包含一个或多个指定关键字的项，或`property:value`表达式。<sup>2</sup> <br/> |
|NOT  <br/> |keyword1 NOT keyword2  <br/> NOT from:"Ann Beebe"  <br/> 不类型： im  <br/> |排除指定关键字的项目或`property:value`表达式。在第二个示例排除发送 Ann Beebe 的邮件。第三个示例排除任何即时消息对话，如 Skype 保存到对话历史记录邮箱文件夹的业务对话。<sup>2</sup> <br/> |
|-  <br/> |keyword1 -keyword2  <br/> |与**NOT**运算符相同。此查询返回包含的项以便`keyword1`和将排除项包含的`keyword2`。<br/> |
|NEAR  <br/> |keyword1 NEAR(n) keyword2  <br/> |返回项目的词彼此靠近，其中 n 等于分离的单词数。例如，`best NEAR(5) worst`返回任何项，其中的单词"差"是中的"最佳"的五个单词。如果未指定编号，默认的距离为八个单词。<sup>2</sup> <br/> |
|ONEAR  <br/> |keyword1 ONEAR(n) keyword2  <br/> |类似于**附近**，但它返回项目中指定的顺序彼此靠近的单词。例如，`best ONEAR(5) worst`返回任何项，其中的单词"最佳"发生之前的单词"最差值"并且两个单词中的每个其他的五个单词。如果未指定编号，默认的距离为八个单词。<sup>2</sup> <br/> > [!NOTE]> 搜索邮箱; 时，不支持**ONEAR**运算符仅适用于搜索业务网站 SharePoint 和 OneDrive 时。如果您在同一个搜索中搜索邮箱和网站，并且该查询包括**ONEAR**运算符，搜索将像使用**NEAR**运算符返回的邮箱项目。换句话说，搜索返回的项目中指定的词彼此靠近无论单词发生的顺序。           |
|:  <br/> |property:value  <br/> |中的冒号 （:）`property:value`语法指定搜索的属性的值包含指定的值。例如，`recipients:garthf@contoso.com`返回发送到 garthf@contoso.com 所有邮件。<br/> |
|=  <br/> |property=value  <br/> |与 **:** 运算符相同。  <br/> |
|\<  <br/> |property\<value  <br/> |表示正在搜索的属性小于指定的值。<sup>1</sup> <br/> |
|\>  <br/> |property\>value  <br/> |表示正在搜索的属性大于指定的值。<sup>1</sup> <br/> |
|\<=  <br/> |property\<=value  <br/> |表示正在搜索的属性小于等于指定的值。<sup>1</sup> <br/> |
|\>=  <br/> |property\>=value  <br/> |表示正在搜索的属性大于等于指定的值。<sup>1</sup> <br/> |
|..  <br/> |属性： value1 正在value2  <br/> |表示正在搜索的属性大于等于 value1，小于等于 value2。<sup>1</sup> <br/> |
|"  "  <br/> |"fair value"  <br/> subject:"Quarterly Financials"  <br/> |使用双引号 ("") 来搜索精确短语或关键字中的术语和`property:value`搜索查询。  <br/> |
|\*  <br/> |cat\*  <br/> subject:set\*  <br/> |前缀 （星号的放置位置单词的末尾处） 的通配符搜索匹配的关键字零个或多个字符或`property:value`查询。例如，`title:set*`文档标题中返回包含单词设置、 设置和设置 （和其他"设置"开头的单词） 的文档。<br/><br/> **注意：** 您可以使用仅前缀通配符搜索;例如， **cat\*** 或**设置\***。后缀搜索 ( ** \*cat** ) 中, 缀搜索 ( **c\*t** )，和子字符串搜索 ( ** \*cat\* ** ) 不受支持。           |
|(  )  <br/> | (fair OR free) AND (from:contoso.com)  <br/> (IPO OR initial) AND (stock OR shares)  <br/> (quarterly financials)  <br/> |括号将布尔短语、 `property:value` 项目和关键字结合到一起。例如，  `(quarterly financials)` 返回包含单词"quarterly"和"financials"的项目。  <br/> |
   
> [!NOTE]
> <sup>1</sup>??????Use 此运算符具有日期或数字值的属性。> <sup>2</sup>??????Boolean 搜索运算符必须大写;例如，为**AND**。如果您使用小写运算符，如**和**，它将被视为搜索查询中的关键字。 
  
## <a name="search-conditions"></a>搜索条件

您可以将条件添加到搜索查询来缩小搜索范围并返回更精确的结果集。每个条件向 KQL 搜索查询创建和启动搜索时运行一个子句。
  
[通用属性的条件 ](#conditions-for-common-properties)

[邮件属性的条件](#conditions-for-mail-properties)

[文档属性的条件](#conditions-for-document-properties)

[与条件一起使用的运算符](#operators-used-with-conditions)

[使用条件的准则](#guidelines-for-using-conditions)

[示例](#examples-of-using-conditions-in-search-queries)
  
### <a name="conditions-for-common-properties"></a>通用属性的条件 

创建一个条件时在同一个搜索中搜索邮箱和网站使用常见的属性。下表列出了可用的属性添加条件时要使用。
  
|**条件**|**说明**|
|:-----|:-----|
|日期  <br/> |为电子邮件，一条消息的日期已接收的收件人或发件人发送。对于文档，文档的上次修改的日期。  <br/> |
|发件人/作者  <br/> |为电子邮件，发送一条消息的人员。对于文档，Office 文档中的作者字段中所引用的人员。您可键入多个名称，以逗号分隔。逻辑上位于由**OR**运算符连接两个或多个值。<br/> |
|大小 （以字节为单位）  <br/> |对于电子邮件和文档而言，是项目的大小（以字节为单位）。  <br/> |
|主题/标题  <br/> |为电子邮件，一条消息的主题行中的文本。对于文档，文档的标题。如前所述，Title 属性是在 Microsoft Office 文档中指定的元数据。您可键入多个主题/标题，以逗号分隔的名称。逻辑上位于由**OR**运算符连接两个或多个值。<br/> |
|合规性标记  <br/> |有关电子邮件和文档，用户已手动分配已分配给邮件和文档自动标签策略或标签的标签。标签用于分类电子邮件和数据管理的文档和强制实施保留规则定义标签的分类。您可以键入一部分的标签名称和使用通配符或键入完整的标签名称。有关详细信息，请参阅[Overview of Office 365 中的标签](labels.md)。<br/> |
  
### <a name="conditions-for-mail-properties"></a>邮件属性的条件

搜索邮箱或公用文件夹时使用邮件属性创建条件。下表列出了可以用于条件的电子邮件属性。请注意，这些属性是先前描述的电子邮件属性的子集；为了方便你使用，这里将重复这些说明。
  
|**条件**|**说明**|
|:-----|:-----|
|消息类型  <br/> | 要搜索的消息类型。这是作为 Kind 电子邮件属性相同的属性。可能的值：  <br/><br/>  联系人  <br/>  文档  <br/>  电子邮件  <br/>  externaldata  <br/>  传真  <br/>  即时消息  <br/>  日志  <br/>  会议  <br/>  microsoftteams  <br/>  注释  <br/>  公告  <br/>  RSS 源  <br/>  任务  <br/>  语音邮件  <br/> |
|Participants  <br/> |电子邮件中的所有人员字段；这些字段分别为：发件人、收件人、抄送和密件抄送。  <br/> |
|类型  <br/> |电子邮件项的邮件类属性。这是作为 ItemClass 电子邮件属性相同的属性。它也是一个多值条件。因此，要选择多个邮件类，请按住**CTRL**键，然后单击您想要添加到的条件的下拉列表中的两个或多个邮件类。在列表中选择每个邮件类将由相应的搜索查询中的**或**运算符逻辑连接。<br/> 所使用的 Exchange 和您可以在**邮件类**列表中选择的邮件类 （和其对应的邮件类 ID） 的列表，请参阅[Item Types and Message Classes](https://go.microsoft.com/fwlink/?linkid=848143)。  <br/> |
|Received  <br/> |收件人接收电子邮件的日期。此属性与“Received”电子邮件属性相同。  <br/> |
|收件人  <br/> |此人的电子邮件发送给。这是作为收件人电子邮件属性相同的属性。  <br/> |
|Sender  <br/> |电子邮件的发件人。  <br/> |
|Sent  <br/> |发件人发送一封电子邮件的日期。这是作为发送电子邮件属性相同的属性。  <br/> |
|Subject  <br/> |电子邮件主题行中的文本。  <br/> |
|To  <br/> |电子邮件的收件人。  <br/> |
  
### <a name="conditions-for-document-properties"></a>文档属性的条件

创建搜索业务网站上 SharePoint 和 OneDrive 文档时使用文档属性的条件。下表列出了可用于条件的文档属性。请注意，这些属性是之前描述; 站点属性的子集为方便起见重复这些说明。
  
|**条件**|**说明**|
|:-----|:-----|
|Author  <br/> |仍然存在，如果复制文档作者字段从 Office 文档。例如，如果用户创建文档和电子邮件它向其他人某人然后将其上载到 SharePoint，文档将仍保留原始作者。  <br/> |
|Title  <br/> |文档的标题。Title 属性是在 Office 文档中指定的元数据。它是文档的不同文件名。  <br/> |
|已创建  <br/> |创建文档的日期。  <br/> |
|上次修改时间  <br/> |上次修改文档的日期。  <br/> |
|文件类型  <br/> |文件; 扩展名例如，docx、 一个、 pptx 或 xlsx。这是作为文件扩展名站点属性相同的属性。  <br/> |
  
### <a name="operators-used-with-conditions"></a>与条件一起使用的运算符

当您添加一个条件时，您可以选择与该条件的属性类型相关的运算符。下表描述了与条件一起使用的运算符，并列出了在搜索查询中使用的等效项。
  
|**运算符**|**查询等效项**|**说明**|
|:-----|:-----|:-----|
|之后  <br/> |`property\>date`  <br/> |使用日期条件。返回在指定日期后发送、接收或修改的项。   <br/> |
|之前  <br/> |`property\<date`  <br/> |使用日期条件。返回在指定日期前发送、接收或修改的项。  <br/> |
|介于  <br/> |`date..date`  <br/> |使用日期和大小的条件。如果使用日期条件，那里返回项目已发送、 接收，或指定的日期范围内修改。如果使用的大小条件，返回其大小为指定范围内的项目。  <br/> |
|包含任意  <br/> |`(property:value) OR (property:value)`  <br/> |用于指定一个字符串值的属性的条件。返回包含一个或多个指定的字符串任何的值部分的项。  <br/> |
|不包含任何  <br/> |`-property:value`  <br/> `NOT property:value`  <br/> |与指定字符串值的属性条件一起使用。返回不包含指定字符串值任何部分的项目。  <br/> |
|不等于任何
  <br/> |`-property=value`  <br/> `NOT property=value`  <br/> |与指定字符串值的属性条件一起使用。返回不包含特定字符串的项目。  <br/> |
|等于  <br/> |`size=value`  <br/> |返回与指定大小相等的项目。<sup>1</sup> <br/> |
|等于任何  <br/> |`(property=value) OR (property=value)`  <br/> |与指定字符串值的属性条件一起使用。返回完全匹配一个或多个指定字符串值的项目。  <br/> |
|大于  <br/> |`size>value`  <br/> |返回指定属性大于指定值的项。<sup>1</sup> <br/> |
|大于或等于  <br/> |`size>=value`  <br/> |返回指定属性大于或等于指定值的项。<sup>1</sup> <br/> |
|小于  <br/> |`size<value`  <br/> |返回大于或等于指定值的项。<sup>1</sup> <br/> |
|小于或等于  <br/> |`size<=value`  <br/> |返回大于或等于指定值的项。<sup>1</sup> <br/> |
|不等于  <br/> |`size<>value`  <br/> | 返回与指定大小不相等的项目。<sup>1</sup> <br/> |
   
> [!NOTE]
> <sup>1</sup>仅适用于使用 Size 属性的条件是该运算符。 
  
### <a name="guidelines-for-using-conditions"></a>使用条件的准则

在使用搜索条件时，请牢记以下几点。
  
- 条件逻辑**AND**运算符通过连接到 （在关键字框中指定） 的关键字查询。这意味着项目需要满足关键字查询和结果中包含的条件。这是如何帮助条件以缩小结果。 
    
- 如果您将两个或多个唯一条件添加到搜索查询 （指定不同的属性的条件），这些条件逻辑**AND**运算符的连接。这意味着返回满足 （即除了以外的任何关键字查询） 的所有条件的项目。 
    
- 如果您添加为同一属性的多个条件，这些条件逻辑上位于由**OR**运算符连接。这意味着返回满足关键字查询和条件之一的项目。因此，通过**OR**运算符连接到每个其他组相同的条件，然后通过**AND**运算符连接的唯一的条件集。 
    
- 如果您将多个值 （用逗号或分号隔开） 添加到一个条件，这些值进行连接的**OR**运算符。也就是说，如果它们包含任何指定的值在条件中的属性返回的项目。 
    
- 创建通过使用关键字框和条件的搜索查询所选搜索的详细信息窗格中的**搜索**页上显示。在查询中，所有右侧的表示法`(c:c)`指示添加到查询的条件。 
    
- 条件仅将属性添加到搜索查询。不添加运算符。这就是为什么不显示运算符的右侧的详细信息窗格中显示查询`(c:c)`标记。KQL 添加逻辑运算符 （根据前面所述的规则） 时执行的查询。 
    
- 您可以使用拖放控件进行重新排序条件的顺序。只需单击条件的控件，然后将其移向上或向下。
    
- 如前所述，某些条件属性允许您键入多个值。逻辑上通过**OR**运算符连接的每个值。这将导致为具有多个实例的相同的条件，其中每个都有一个值相同的逻辑。下图显示了一个条件具有多个值的示例和使用单一值 （对于相同的属性） 的多个条件的示例。这两个示例在同一查询结果：`(filetype="docx") OR (filetype="pptx") OR (filetype="xlsx")`
    
    ![一个条件具有多个值](media/9880aa29-d117-4531-be20-6d53f1d21341.gif)
  
    ![同一属性的多个搜索条件](media/1e63d37d-6d8d-4c9b-a509-a7e1c3a05193.gif)
  
> [!TIP]
> 如果条件接受多个值，则建议您使用一个条件，并指定多个值（用逗号或分号分隔）。这有助于确保所应用的查询逻辑就是您想要的。 
  
### <a name="examples-of-using-conditions-in-search-queries"></a>示例

下面的示例演示基于 GUI 条件，选定搜索 （这还使用**Get-ComplianceSearch** cmdlet 返回） 的详细信息窗格中显示的搜索查询语法搜索查询的版本和逻辑相应的 KQL 查询。 
  
#### <a name="example-1"></a>示例 1

本示例将返回在 SharePoint 和 OneDrive for Business 站点都包含信用卡号和上次修改之前 2016 年 1 月 1，文档。
  
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
  
 `report???(c:c)??????(date<2016-04-01)??????(subjecttitle:"northwind")??????(-filetype="aspx")???`
  
 **搜索查询逻辑**
  
 `report AND (date<2016-04-01) AND (subjecttitle:"northwind") NOT (filetype="aspx")`
  
#### <a name="example-3"></a>示例 3
<a name="conditionexamples"> </a>

本示例返回电子邮件或日历会议 12/1/2016年和 11/30/2016年之间发送的并且包含以"电话"或"smartphone"开头的单词。
  
 **GUI**
  
![搜索条件示例三](media/973d45fc-0923-43d6-9d0a-25e4a625f057.gif)
  
 **搜索查询语法**
  
 `phone* OR smartphone*(c:c)(sent=2016-12-01..2016-11-30)(kind="email")(kind="meetings")`
  
 **搜索查询逻辑**
  
 `phone* OR smartphone* AND (sent=2016-12-01..2016-11-30) AND ((kind="email") OR (kind="meetings"))`
  
## <a name="searching-for-site-content-shared-with-external-users"></a>搜索与外部用户共享的网站内容

此外可以在安全中使用的内容的搜索功能&amp;合规性中心要搜索的文档存储在 SharePoint 和 OneDrive 业务网站已与组织外部的人员共享。这可以帮助您确定敏感或专有共享您的组织之外的信息。您可以执行此操作使用`ViewableByExternalUsers`关键字查询中的属性。此属性将返回文档或网站的已共享与外部用户通过使用下列共享方法之一： 
  
- 要求用户登录到您的组织作为经过身份验证的用户共享邀请。
    
- 允许与此链接可访问该资源，而无需进行身份验证的任何人都匿名来宾链接。
    
下面是一些示例：
  
- 查询`ViewableByExternalUsers:true AND SensitiveType:"Credit Card Number"`将返回与组织外部的人员共享且包含信用卡号的所有项。 
    
- 查询`ViewableByExternalUsers:true AND ContentType:document AND Site:https://contoso.sharepoint.com/Sites/Teams`将返回组织中与外部用户共享的所有工作组网站上的文档的列表。 
    
> [!TIP]
> 搜索查询，如`ViewableByExternalUsers:true AND ContentType:document`可能会在搜索结果中返回大量的.aspx 文件。若要消除这些 （或其他类型的文件），您可以使用`FileExtension`属性来排除特定文件类型;例如`ViewableByExternalUsers:true AND ContentType:document NOT FileExtension:aspx`。 
  
什么被视为与组织外部的人员共享的内容？贵组织的 SharePoint 和 OneDrive 中的业务网站的共享的发送共享邀请或在公共位置共享的文档。例如，以下用户活动产生外部用户可以查看的内容：
  
- 用户与组织外部的人员共享文件或文件夹。

    
- 用户创建，并发送给组织外部的人员共享文件的链接。此链接允许外部用户可以查看 （或编辑） 文件。
    
- 用户向组织外部的人员发送共享邀请或来宾链接以查看（或编辑）共享文件。
    
### <a name="issues-using-the-viewablebyexternalusers-property"></a>问题使用 ViewableByExternalUsers 属性

时`ViewableByExternalUsers`属性表示是否与外部用户共享文档或网站的状态、 有为此属性的用途的一些注意事项和 doesn???t 反映。在下列情况下的值`ViewableByExternalUsers`属性不会更新，并使用此属性的内容的搜索查询的结果可能不准确。 
  
- 为共享策略，如关闭外部共享网站或组织的更改。属性仍会显示为正在可从外部访问，尽管可能已撤销外部访问权限的以前共享的文档。
    
- 更改组成员身份，如添加或删除外部用户与 Office 365 组或 Office 365 安全组。该属性不会自动更新组有权访问的项目。
    
- 发送共享邀请外部用户，其中收件人尚未接受邀请，并因此尚不具有对内容进行访问。
    
在这些情况下，`ViewableByExternalUsers`属性将不会反映共享的当前状态，直到网站或文档库是重新爬网和重新编制索引。 

## <a name="searching-for-site-content-shared-within-your-organization"></a>搜索组织内共享的网站内容

如前所述，您可以使用`SharedWithUsersOWSUser`属性，以便搜索已在组织中的人员之间共享的文档。人员与组织内的其他用户共享文件 （或文件夹），OneDrive for Business 帐户与共享的文件的人员**与我共享**页上将出现共享的文件的链接。例如，若要搜索已与 Sara Davis 共享文档，可以使用查询`SharedWithUsersOWSUser:"sarad@contoso.com"`。如果导出此搜索的结果时，将下载的原始文档 （位于与 Sara 共享文档的人员的内容位置）。
  
请注意，必须使用特定的用户能够使用时，搜索结果中返回显式共享文档`SharedWithUsersOWSUser`属性。例如，如果某人共享其 OneDrive 帐户中的文档，他们可以选择共享与任何人 （内部或外部组织）、 共享只能与组织内部人员或与特定人员共享。下面是 OneDrive，显示三个共享选项中的**共享**窗口的屏幕截图。 
  
![仅与特定的某个人共享的文件将返回 searcj 查询使用 SharedWithUsersOWSUser 属性](media/469a4b61-68bd-4ab0-b612-ab6302973886.png)
  
仅使用第三个选项 （与**特定人员**共享） 共享的文档将返回的搜索查询使用`SharedWithUsersOWSUser`属性。 

## <a name="search-tips-and-tricks"></a>搜索提示和技巧

- 关键字搜索不区分大小写。例如， **cat** 和 **CAT** 将返回相同的结果。 
    
- 布尔运算符**和**、**或**、**不**、 **NEAR**和**ONEAR**必须大写。 
    
- 间距两个关键字或两个`property:value`表达式是用**AND**相同。例如，`from:"Sara Davis" subject:reorganization`返回发送的 Sara Davis 包含 word 重组的主题行中的所有邮件。 
    
- 使用匹配的语法`property:value`格式。值不区分大小写，并且他们不能运算符后具有一个空格。如果没有空格，则您预期的值只需将全文搜索。例如`to: pilarp`搜索的关键字，"pilarp"而不是为到 pilarp 发送的邮件。 
    
- 在搜索收件人属性（如 To、From、Cc 或 Recipients）时，您可以使用 SMTP 地址、别名或显示名来表示收件人。例如，您可以使用 pilarp@contoso.com、pilarp 或"Pilar Pinilla"。
    
- 您可以使用仅前缀通配符搜索;例如， **cat\*** 或**设置\***。后缀搜索 ( ** \*cat** ) 中, 缀搜索 ( **c\*t** )，和子字符串搜索 ( ** \*cat\* ** ) 不受支持。 
    
- 搜索时属性，则使用双引号 ("") 如果搜索值包含多个单词。例如`subject:budget Q1`返回包含**预算**中的邮件的主题行和包含**第 1 季度**无处不在邮件或任何消息属性。使用`subject:"budget Q1"`返回包含的主题行中的任意位置的**预算第 1 季度**的所有邮件。 
    
- 若要排除从搜索结果的某些属性值与标记的内容，请将属性的名称之前减号 （-）。例如，`-from:"Sara Davis"`会排除任何由 Sara Davis 发送的消息。 
