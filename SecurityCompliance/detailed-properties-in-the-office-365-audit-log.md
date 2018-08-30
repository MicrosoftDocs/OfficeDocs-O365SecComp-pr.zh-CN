---
title: Office 365 审核日志中的属性详细信息
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/8/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Office 365 中包含的其他属性的说明审核日志记录。
ms.openlocfilehash: 69c5565ac71715ba2cb22d93d80f7e5dd12c6440
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525450"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 审核日志中的属性详细信息

从 Office 365 安全性导出审核日志搜索的结果时&amp;合规性中心，您可以选择下载符合搜索条件的所有结果。执行此操作通过选择**导出结果**\>安全**审核日志搜索**页上的**下载所有结果**&amp;合规性中心。有关详细信息，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。
  
 当所有导出审核日志搜索的都结果时，从 Office 365 统一的审核日志复制到逗号分隔的原始数据分隔值 (CSV) 文件，这下载到本地计算机。此文件包含来自名为**详细信息**的列中的审核日志条目的其他信息。此列包含多个属性的审核日志记录的多值属性。此多值属性中的**属性： 值**对的每个用逗号分隔。 
  
下表介绍的属性包含 — 根据 Office 365 服务中发生事件 — 在多个属性的**详细信息**列。**Office 365 服务具有此属性的**列指示的服务和类型的包含属性的活动 （用户或管理员）。有关这些属性或可能不会列出本主题中的属性的详细信息，请参阅[Office 365 管理活动 API 架构](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以使用 Excel 中的 Power 查询将此列拆分为多个列，以使每个属性具有其自己的列。这将允许您进行排序和上一个或多个属性筛选器。若要了解如何执行此操作，请参阅[拆分文本 （电源查询） 的列](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)中的"拆分列分隔符由"一节。 
  
|**属性**|**说明**|**具有此属性的 office 365 服务**|
|:-----|:-----|:-----|
|Actor  <br/> |执行操作的用户或服务帐户。 |Azure Active Directory  <br/> |
|AddOnName  <br/> |已添加、 删除或更新团队中的加载项的名称。在 Microsoft 团队中的加载项的类型是自动程序、 连接线或选项卡。  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |已添加、 删除或更新团队中的加载项的类型。下列值指示的加载项的类型。<br/> **1** -指示自动程序。<br/> **2** -指示连接器。<br/> **3** -表示选项卡。 |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |Azure Active Directory 事件的类型。下列值指示事件的类型。<br/> **0** -指示的帐户登录事件。<br/> **1** -指示 Azure 应用程序安全事件。 |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |Microsoft 团队通道的 ID。由的**TeamName**和**TeamGuid**属性标识的团队的通道位于。<br/> |Microsoft Teams  <br/> |
|ChannelName  <br/> |Microsoft 团队通道的名称。由的**TeamName**和**TeamGuid**属性标识的团队的通道位于。<br/> |Microsoft Teams  <br/> |
|客户端  <br/> |客户端设备和设备操作系统，用于登录事件 (例如，Nokia Lumia 920; 设备浏览器Windows Phone 8;IE Mobile 11)。  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |有关电子邮件客户端用来执行操作，如浏览器版本、 Outlook 版本和移动设备信息的信息  <br/> |Exchange （邮箱活动）  <br/> |
|ClientIP  <br/> |活动已记录时所使用的设备的 IP 地址。IP 地址被显示在 IPv4 或 IPv6 地址格式。  <br/> |Exchange 和 Azure Active Directory  <br/> |
|ClientIPAddress  <br/> |ClientIP 相同。  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |日期和时间以协调世界时 (UTC) 用户执行活动时。  <br/> |All  <br/> |
|DestinationFileExtension  <br/> |文件复制或移动的文件扩展名。此属性仅显示 FileCopied 和 FileMoved 用户活动。  <br/> |SharePoint  <br/> |
|DestinationFileName  <br/> |复制或移动文件的名称。此属性仅显示 FileCopied 和 FileMoved 操作。  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |目标文件夹复制或移动文件的位置的 URL。**ObjectID**属性，它是已复制的文件的完整路径名称的值相同**SiteURL**、 **DestinationRelativeURL**，和**DestinationFileName**属性的值的组合。此属性仅显示 FileCopied 和 FileMoved 用户活动。<br/> |SharePoint  <br/> |
|EventSource  <br/> |标识 SharePoint 中发生事件。可能的值为**SharePoint**和**ObjectModel**。<br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |Exchange 管理活动，指定是否在您的组织，由 Microsoft 数据中心人员或数据中心服务帐户，用户通过或委派管理员已运行 cmdlet。**False**的值指示 cmdlet 运行您的组织中的人。值**True**表示由数据中心人员、 数据中心服务帐户或委派的管理员已运行 cmdlet。<br/> 对于 Exchange 邮箱活动，指定是否由组织外部用户访问邮箱。  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |扩展的属性的 Azure Active Directory 事件。  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |报告条目 ID。ID 唯一标识报告条目。  <br/> |All  <br/> |
|InternalLogonType  <br/> |保留供内部使用。  <br/> |Exchange （邮箱活动）  <br/> |
|ItemType  <br/> |访问或修改对象的类型。可能值包括**文件**、**文件夹**、 **Web**、**网站**、**租户**和**DocumentLibrary**。<br/> |SharePoint  <br/> |
|LoginStatus  <br/> |标识可能出现的登录失败。  <br/> |Azure Active Directory  <br/> |
|LogonType  <br/> |邮箱访问的类型。下面的值指示访问邮箱的用户的类型。<br/><br/> **0** -指示邮箱所有者。<br/> **1** -指示管理员。<br/> **2** -指示代理人。 <br/>**3** -指示 Microsoft 数据中心中的传输服务。<br/> **4** -表示 Microsoft 数据中心中的服务帐户。 <br/>**6** -指示委派的管理员。 |Exchange （邮箱活动）  <br/> |
|MailboxGuid  <br/> |访问邮箱的 Exchange GUID。  <br/> |Exchange （邮箱活动）  <br/> |
|MailboxOwnerUPN  <br/> |访问邮箱所有者的人员的电子邮件地址。  <br/> |Exchange （邮箱活动）  <br/> |
|成员  <br/> |列出已添加或从组中删除的用户。下列值指示分配给用户的角色类型。<br/><br/> **1** -指示所有者角色。<br/> **2** -指示成员角色。<br/> **3** -指示的来宾角色。 <br/><br/>Members 属性还包括您的组织和成员的电子邮件地址的名称。  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (名称、 NewValue，OldValue)  <br/> |该属性是包含用于管理事件，如添加用户作为网站或网站集管理员组的成员。属性包括名称 （例如，网站管理组） 修改的属性的新值的已修改的属性 （此类的用户已添加为网站管理员和已修改的对象的以前的值。  <br/> |所有 （管理活动）  <br/> |
|ObjectID  <br/> |Exchange 管理员审核日志记录，通过 cmdlet 修改对象的名称。  <br/> 对于 SharePoint 活动，文件或由用户访问的文件夹的完整 URL 路径名称。  <br/> Azure AD 活动，已修改的用户帐户的名称。  <br/> |All  <br/> |
|Operation  <br/> |用户或管理员活动的名称。此属性的值对应于中**活动**选定值下拉列表。如果选择了**的所有活动显示结果**，将包含该报表的所有服务的所有用户和管理活动的条目。Office 365 审核日志中记录操作/活动的说明，请参阅**Audited 活动**选项卡[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。<br/> Exchange 管理活动，此属性标识运行此 cmdlet 的名称。  <br/> |All  <br/> |
|组织 Id  <br/> |Office 365 组织的 GUID。  <br/> |All  <br/> |
|路径  <br/> |已访问的消息所在的邮箱文件夹的名称。此属性同时也会指出的位置的文件夹中创建或复制/移到一条消息。  <br/> |Exchange （邮箱活动）  <br/> |
|Parameters  <br/> |Exchange 管理活动、 名称和使用 cmdlet 中的操作属性标识使用的所有参数值。  <br/> |Exchange （管理活动）  <br/> |
|RecordType  <br/> |由 record 表示的操作的类型。下列值指示记录类型。<br/><br/> **1** -指示从 Exchange 管理员审核日志记录。 <br/>**2** -指示从意见邮箱项目执行的操作的 Exchange 邮箱审核日志记录。 <br/>**3** -还指示从 Exchange 邮箱审核日志记录。此记录类型指示对多个项目 （如将多个项目移动到已删除邮件文件夹或永久删除多个项目） 的源邮箱中执行操作。<br/>**4** -指示网站的管理操作在 SharePoint 中，如管理员或用户将权限分配给网站。 <br/>**6** -表示文件或在 SharePoint 中，如用户查看或修改文件的文件夹相关的操作。 <br/>**8** -指示在 Azure Active Directory 中执行管理操作。 <br/>**9** -指示 OrgId 登录 Azure Active Directory 中的新事件。此记录类型已被弃用。<br/>**10** -指示执行由 Microsoft 数据中心内的人员的安全 cmdlet 事件。 <br/>**11** -指示数据丢失保护 (DLP) SharePoint 中的新事件。<br/> **12** -指示 Sway 事件。 <br/>**14** -指示 SharePoint 中的共享事件。<br/> **15** -指示安全令牌服务 (STS) 登录 Azure Active Directory 中的新事件。 <br/>**18** -指示安全&amp;合规性中心事件。 <br/>**20** -指示 Power BI 事件。 <br/>**22** -指示 Yammer 事件。 <br/>**24** -指示电子数据展示事件。此记录类型指示通过运行内容搜索和管理电子数据展示事例安全中的执行的活动&amp;合规性中心。有关详细信息，请参阅 Office 365 中的电子数据展示活动的搜索审核日志。<br/>**25、 26 或 27** -指示 Microsoft 团队事件。 |All  <br/> |
|ResultStatus  <br/> |指示 （的**Operation**属性中指定） 的操作是成功还是失败。  <br/> 对于 Exchange 管理员活动，值为**True** （成功） 或**False** （失败）。  <br/> |All  <br/> |
|SecurityComplianceCenterEventType  <br/> |指示事件是安全&amp;合规性中心事件。所有安全&amp;合规性中心活动将具有的值为**0** ，此属性。<br/> |Office 365 安全性&amp;合规性中心  <br/> |
|SharingType  <br/> |已分配给用户的资源已与共享类型的共享的权限。此用户标识**UserSharedWith**属性中。<br/> |SharePoint  <br/> |
|网站  <br/> |由用户访问的文件夹的文件所在的网站的 GUID。  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |由用户访问的文件夹的文件所在的网站的 URL。  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |文件扩展名的文件的用户访问。此属性为空，如果访问该对象是一个文件夹。  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |文件或由用户访问的文件夹的名称。  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |包含由用户访问的文件的文件夹的 URL。**ObjectID**属性，它是由用户访问的文件的完整路径名称的值相同**SiteURL**、 **SourceRelativeURL**，和**SourceFileName**属性的值的组合。<br/> |SharePoint  <br/> |
|Subject  <br/> |访问邮件的主题行。  <br/> |Exchange （邮箱活动）  <br/> |
|选项卡类型  <br/> | 选项卡的类型添加、 删除或更新团队中。此属性的可能值包括：<br/><br/> **Excelpin** -Excel 选项卡。  <br/> **扩展**的所有第一方和第三方应用程序;如计划程序、 VSTS，和窗体。  <br/> **Notes** -OneNote 选项卡。  <br/> **Pdfpin** -PDF 选项卡。  <br/> **Powerbi** -PowerBI 选项卡。  <br/> **Powerpointpin** -A PowerPoint 选项卡。  <br/> **Sharepointfiles** -A SharePoint 选项卡。  <br/> **网页**的固定的网站选项卡。  <br/> **Wiki 选项卡**wiki 选项卡。  <br/> **Wordpin** -Word 选项卡。  <br/> |Microsoft Teams  <br/> |
|目标  <br/> |已执行的操作 （在**操作**属性标识） 的用户。例如，如果来宾用户添加到 SharePoint 或 Microsoft 团队，将此属性中列出该用户。<br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |在 Microsoft 团队中的工作组 ID。  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |在 Microsoft 团队中的工作组名称。  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |有关用户的浏览器的信息。在浏览器提供此信息。  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |标识信息 （参与者） 的用户的租户组织用户执行操作。  <br/> |Azure Active Directory  <br/> |
|用户 Id  <br/> |执行导致所记录的记录的操作 （在**操作**属性中指定） 的用户。请注意，审核日志中还包含由系统帐户 （例如，类似于 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM） 执行的活动记录。<br/> |All  <br/> |
|UserKey  <br/> |**UserID**属性中标识的用户的备用 ID。例如，此属性会填入 passport 事件执行由 SharePoint 中的用户的唯一 ID (PUID)。此外，此属性可能为其他服务和由系统帐户执行事件中发生事件的**UserID**属性指定相同的值。<br/> |All  <br/> |
|UserSharedWith  <br/> |与共享资源的用户。如果**操作**属性的值为**SharingSet**，此属性是包含。在**共享**列中报告中还列出此用户。<br/> |SharePoint  <br/> |
|UserType  <br/> |用户执行操作的类型。下列值指示用户类型。<br/> <br/> **0** -常规用户。 <br/>**2** -Office 365 组织中的管理员。 <br/>**3** -Microsoft 数据中心管理员或数据中心系统帐户。 <br/>**4** -系统帐户。 <br/>**5** -应用程序。 <br/>**6** -服务主体。 |All  <br/> |
|Version  <br/> |指示记录的活动 （由的**Operation**属性标识） 的版本号。  <br/> |All  <br/> |
|工作负荷  <br/> |Office 365 服务活动出现的位置。此属性的可能值包括：<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>合规性<br/>Sway<br/>SecurityComplianceCenter<br/>PowerBI<br/>MicrosoftTeams<br/>ThreatIntelligence**|All  <br/> |
   
查看特定事件的详细信息时单击**详细信息**时，请注意，上述属性也会显示。 
  
![单击查看审核日志事件记录的详细的属性的详细信息](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

