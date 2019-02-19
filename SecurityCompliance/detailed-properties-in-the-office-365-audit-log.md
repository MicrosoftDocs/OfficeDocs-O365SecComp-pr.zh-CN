---
title: Office 365 审核日志中的属性详细信息
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Office 365 审核日志记录中包含的其他属性的说明。
ms.openlocfilehash: e2450f8d4f9a613d6b21e373d2a2de841cfc7ca0
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2019
ms.locfileid: "29890043"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Office 365 审核日志中的属性详细信息

从 Office 365 安全&amp;合规中心导出审核日志搜索的结果时, 您可以选择下载符合搜索条件的所有结果。为此, 请选择 "**导出结果** \> " "下载安全&amp;合规性中心中的**审核日志搜索**页上的**所有结果**"。有关详细信息, 请参阅[在 Office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。
  
 当您导出审核日志搜索的所有结果时, 将把来自 Office 365 统一审核日志的原始数据复制到逗号分隔值 (CSV) 文件中, 该文件将下载到您的本地计算机上。此文件包含来自名为**Detail**的列中的审核日志条目的其他信息。此列包含来自审核日志记录的多个属性的多值属性。此多值属性中的每个**属性: 值**对都用逗号分隔开。 
  
下表介绍了多属性**详细信息**列中的每个事件所包含的属性 (具体情况取决于发生某个事件的 Office 365 服务)。**具有此属性列的 Office 365 服务**指示包含该属性的活动的服务和类型 (用户或管理员)。有关这些属性的详细信息或有关本主题中可能未列出的属性的详细信息, 请参阅[Office 365 管理活动 API 架构](https://go.microsoft.com/fwlink/p/?LinkId=717993)。
  
> [!TIP]
> 您可以使用 Excel 中的 Power Query 将此列拆分为多个列, 这样每个属性都将拥有自己的列。这将允许您对其中一个或多个属性进行排序和筛选。若要了解如何执行此操作, 请参阅[拆分一列文本 (Power Query)](https://support.office.com/article/5282d425-6dd0-46ca-95bf-8e0da9539662)中的 "按分隔符拆分列" 一节。 
  
|**属性**|**说明**|**具有此属性的 Office 365 服务**|
|:-----|:-----|:-----|
|主角  <br/> |执行操作的用户或服务帐户。 |Azure Active Directory  <br/> |
|AddOnName  <br/> |在团队中添加、删除或更新的加载项的名称。Microsoft 团队中的加载项类型为 bot、连接器或选项卡。  <br/> |Microsoft Teams  <br/> |
|AddOnType  <br/> |在团队中添加、删除或更新的加载项的类型。以下值指示加载项的类型。<br/> **1** -表示机器人。<br/> **2** -指示连接器。<br/> **3** -指示一个选项卡。 |Microsoft Teams  <br/> |
|AzureActiveDirectoryEventType  <br/> |Azure Active Directory 事件的类型。以下值指示事件的类型。<br/> **0** -指示帐户登录事件。<br/> **1** -指示 Azure 应用程序安全事件。 |Azure Active Directory  <br/> |
|ChannelGuid  <br/> |Microsoft 团队频道的 ID。通道所在的团队由**TeamName**和**TeamGuid**属性标识。<br/> |Microsoft Teams  <br/> |
|ChannelName  <br/> |Microsoft 团队频道的名称。通道所在的团队由**TeamName**和**TeamGuid**属性标识。<br/> |Microsoft Teams  <br/> |
|客户端  <br/> |用于登录事件的客户端设备、设备 OS 和设备浏览器 (例如, Nokia Lumia 920;Windows Phone 8;IE 移动 11)。  <br/> |Azure Active Directory  <br/> |
|ClientInfoString  <br/> |有关用于执行此操作的电子邮件客户端的信息, 例如浏览器版本、Outlook 版本和移动设备信息  <br/> |Exchange (邮箱活动)  <br/> |
|ClientIP  <br/> |记录活动时使用的设备的 IP 地址。IP 地址以 IPv4 或 IPv6 地址格式显示。  <br/> |Exchange 和 Azure Active Directory  <br/> |
|ClientIPAddress  <br/> |与 ClientIP 相同。  <br/> |SharePoint  <br/> |
|CreationTime  <br/> |用户执行活动时的日期和时间 (采用协调通用时间 (UTC))。  <br/> |全部  <br/> |
|DestinationFileExtension  <br/> |复制或移动的文件的文件扩展名。仅对 FileCopied 和 FileMoved 用户活动显示此属性。  <br/> |SharePoint  <br/> |
|destinationfilename 所  <br/> |复制或移动文件的名称。仅对 FileCopied 和 FileMoved 操作显示此属性。  <br/> |SharePoint  <br/> |
|DestinationRelativeUrl  <br/> |复制或移动文件的目标文件夹的 URL。**SiteURL**、 **DestinationRelativeURL**和**destinationfilename 所**属性的值的组合与**ObjectID**属性的值相同, 后者是复制的文件的完整路径的名称。仅对 FileCopied 和 FileMoved 用户活动显示此属性。<br/> |SharePoint  <br/> |
|EventSource  <br/> |标识在 SharePoint 中发生的事件。可能的值为**SharePoint**和**ObjectModel**。<br/> |SharePoint  <br/> |
|ExternalAccess  <br/> |对于 Exchange 管理员活动, 指定是由组织中的用户、Microsoft 数据中心人员或数据中心服务帐户还是由委派的管理员运行 cmdlet。值**False**表示该 cmdlet 由组织中的某个用户运行。值**True**表示 cmdlet 由数据中心人员、数据中心服务帐户或委派管理员运行。<br/> 对于 "Exchange 邮箱活动", 指定是否由组织外部的用户访问邮箱。  <br/> |Exchange  <br/> |
|ExtendedProperties  <br/> |Azure Active Directory 事件的扩展属性。  <br/> |Azure Active Directory  <br/> |
|ID  <br/> |报告条目的 ID。ID 唯一标识报告条目。  <br/> |全部  <br/> |
|InternalLogonType  <br/> |保留以供内部使用。  <br/> |Exchange (邮箱活动)  <br/> |
|ItemType  <br/> |已访问或修改的对象的类型。可能的值包括**文件**、**文件夹**、 **Web**、**网站**、**租户**和**DocumentLibrary**。<br/> |SharePoint  <br/> |
|LoginStatus  <br/> |标识可能已发生的登录失败。  <br/> |Azure Active Directory  <br/> |
|LogonType  <br/> |邮箱访问的类型。以下值指示访问邮箱的用户的类型。<br/><br/> **0** -指示邮箱所有者。<br/> **1** -指示管理员。<br/> **2** -指示一个代理。 <br/>**3** -指示 Microsoft 数据中心中的传输服务。<br/> **4** -表示 Microsoft 数据中心中的服务帐户。 <br/>**6** -表示委派管理员。 |Exchange (邮箱活动)  <br/> |
|MailboxGuid  <br/> |已访问的邮箱的 Exchange GUID。  <br/> |Exchange (邮箱活动)  <br/> |
|MailboxOwnerUPN  <br/> |拥有所访问邮箱的人员的电子邮件地址。  <br/> |Exchange (邮箱活动)  <br/> |
|成员  <br/> |列出已在团队中添加或删除的用户。以下值表示分配给用户的角色类型。<br/><br/> **1** -指示所有者角色。<br/> **2** -指示成员角色。<br/> **3** -指示来宾角色。 <br/><br/>Members 属性还包括您的组织的名称和成员的电子邮件地址。  <br/> |Microsoft Teams  <br/> |
|ModifiedProperties (Name、NewValue、OldValue)  <br/> |此属性包含在管理员事件中, 例如将用户添加为网站成员或网站集管理员组。该属性包括已修改的属性的名称 (例如, 网站管理员组) 已修改属性的新值 (如添加为网站管理员的用户, 以及已修改对象的以前的值)。  <br/> |全部 (管理活动)  <br/> |
|ObjectID  <br/> |对于 Exchange 管理员审核日志记录, 该 cmdlet 修改的对象的名称。  <br/> 对于 SharePoint 活动, 是由用户访问的文件或文件夹的完整 URL 路径名称。  <br/> 对于 Azure AD 活动, 为已修改的用户帐户的名称。  <br/> |全部  <br/> |
|Operation  <br/> |用户或管理员活动的名称。此属性的值对应于在 "**活动**" 下拉列表中选择的值。如果选择了 "**显示所有活动的结果**", 则报告将包含所有服务的所有用户和管理员活动的条目。有关在 office 365 审核日志中记录的操作/活动的说明, 请参阅在[office 365 安全&amp;合规中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)中的 "**审核的活动**" 选项卡。<br/> 对于 Exchange 管理员活动, 此属性标识所运行的 cmdlet 的名称。  <br/> |全部  <br/> |
|OrganizationID  <br/> |Office 365 组织的 GUID。  <br/> |全部  <br/> |
|路径  <br/> |所访问邮件所在的邮箱文件夹的名称。此属性还标识在其中创建或复制/移动邮件的文件夹。  <br/> |Exchange (邮箱活动)  <br/> |
|Parameters  <br/> |对于 Exchange 管理员活动, 与在 Operation 属性中标识的 cmdlet 一起使用的所有参数的名称和值。  <br/> |Exchange (管理员活动)  <br/> |
|RecordType  <br/> |由记录指示的操作的类型。以下值指示记录类型。<br/><br/> **1** -指示 Exchange 管理员审核日志中的记录。 <br/>**2** -指示对 singled 邮箱项目执行的操作的 Exchange 邮箱审核日志中的记录。 <br/>**3** -还指示 Exchange 邮箱审核日志中的记录。此记录类型指示对源邮箱中的多个项目执行的操作 (例如, 将多个项目移动到 "已删除邮件" 文件夹或永久删除多个项目)。<br/>**4** -指示 SharePoint 中的网站管理员操作, 例如管理员或用户分配对网站的权限。 <br/>**6** -指示 SharePoint 中与文件或文件夹相关的操作, 例如用户查看或修改文件。 <br/>**8** -指示在 Azure Active Directory 中执行的管理员操作。 <br/>**9** -指示 Azure Active Directory 中的 OrgId 登录事件。此记录类型已被弃用。<br/>**10** -指示由 Microsoft 人员在数据中心执行的安全 cmdlet 事件。 <br/>**11** -指示 SharePoint 中的数据丢失保护 (DLP) 事件。<br/> **12** -指示 Sway 事件。 <br/>**13** -当使用统一的 DLP 策略进行配置时, 指示 Exchange 中的 DLP 事件。不支持基于 Exchange 传输规则的 DLP 事件。<br>**14** -指示 SharePoint 中的共享事件。<br/> **15** -指示 Azure Active Directory 中的安全令牌服务 (STS) 登录事件。 <br/>**18** -表示安全&amp;合规中心事件。 <br/>**20** -指示 Power BI 事件。 <br/>**21**-指示 Dynamics 365 事件。<br/>**22** -指示 Yammer 事件。 <br/>**23** -指示 Skype for business 事件。 <br/>**24** -指示电子数据展示事件。此记录类型指示通过在安全&amp;合规中心中运行内容搜索和管理电子数据展示事例所执行的活动。有关详细信息, 请参阅在 Office 365 审核日志中搜索电子数据展示活动。<br/>**25、26或 27** -表示 Microsoft 团队活动。 <br/>**28** -指示来自 Exchange Online Protection 和 Office 365 高级威胁防护事件的网络钓鱼和恶意软件事件。<br/> **30** -指示 Microsoft Flow 事件。<br/> **32** -指示 Microsoft Stream 事件。<br/> **35** -指示 Microsoft 项目事件。 <br/> **36** -指示 SharePoint 列表事件。<br/> **40** -指示安全性和合规性警报信号中产生的事件。<br/> **41** -指示 Office 365 高级威胁防护中的安全链接时间段和阻止覆盖事件。<br/>**44** -指示 Workplace Analytics 事件。 <br/>**47** -指示 SharePoint、OneDrive 和 Microsoft 团队中的文件的来自 Office 365 高级威胁防护的网络钓鱼和恶意软件事件。 |全部  <br/> |
|ResultStatus  <br/> |指示操作 (在**Operation**属性中指定) 是否成功。  <br/> 对于 Exchange 管理员活动, 值可以为**True** (成功) 或**False** (失败)。  <br/> |全部  <br/>|
|SecurityComplianceCenterEventType  <br/> |指示活动是安全&amp;合规中心事件。所有安全&amp;合规性中心活动的值都为此属性的值为**0** 。<br/> |Office 365 安全与合规中心  <br/> |
|SharingType  <br/> |分配给用户的共享权限类型, 该用户是与资源共享的。此用户在**UserSharedWith**属性中进行标识。<br/> |SharePoint  <br/> |
|网站  <br/> |用户访问的文件或文件夹所在的网站的 GUID。  <br/> |SharePoint  <br/> |
|SiteUrl  <br/> |用户访问的文件或文件夹所在的网站的 URL。  <br/> |SharePoint  <br/> |
|SourceFileExtension  <br/> |用户访问的文件的文件扩展名。如果访问的对象是一个文件夹, 则此属性为空。  <br/> |SharePoint  <br/> |
|SourceFileName  <br/> |用户访问的文件或文件夹的名称。  <br/> |SharePoint  <br/> |
|SourceRelativeUrl  <br/> |包含用户访问的文件的文件夹的 URL。**SiteURL**、 **SourceRelativeURL**和**SourceFileName**属性的值的组合与**ObjectID**属性的值相同, 后者是用户访问的文件的完整路径名称)。<br/> |SharePoint  <br/> |
|Subject  <br/> |访问的邮件的主题行。  <br/> |Exchange (邮箱活动)  <br/> |
|TabType  <br/> | 在团队中添加、删除或更新的选项卡的类型。此属性的可能值为:<br/><br/> **Excelpin** -Excel 选项卡。  <br/> **扩展**-所有第一方和第三方应用;如 Planner、VSTS 和表单。  <br/> **备注**-OneNote 选项卡。  <br/> **Pdfpin** -PDF 选项卡。  <br/> **powerbi** -一个 Powerbi 选项卡。  <br/> **Powerpointpin** -一个 PowerPoint 选项卡。  <br/> **Sharepointfiles** -A SharePoint 选项卡。  <br/> **网页**-"固定的网站" 选项卡。  <br/> **wiki-选项卡**-wiki 选项卡。  <br/> **Wordpin** -一个 Word 选项卡。  <br/> |Microsoft Teams  <br/> |
|目标  <br/> |对其执行操作 (在**操作**属性中标识) 的用户。例如, 如果将来宾用户添加到 SharePoint 或 Microsoft 团队, 则该用户将在此属性中列出。<br/> |Azure Active Directory  <br/> |
|TeamGuid  <br/> |Microsoft 团队中的团队的 ID。  <br/> |Microsoft Teams  <br/> |
|TeamName  <br/> |Microsoft 团队中的团队的名称。  <br/> |Microsoft Teams  <br/> |
|UserAgent  <br/> |有关用户浏览器的信息。此信息由浏览器提供。  <br/> |SharePoint  <br/> |
|UserDomain  <br/> |有关执行操作的用户 (主角) 的租户组织的标识信息。  <br/> |Azure Active Directory  <br/> |
|UserID  <br/> |执行操作 (在**Operation**属性中指定) 导致记录记录的用户。请注意, 审核日志中还包含由系统帐户 (如 SHAREPOINT\system 或 NT AUTHORITY\SYSTEM) 执行的活动记录。<br/> |全部  <br/> |
|UserKey  <br/> |在**UserID**属性中标识的用户的替代 ID。例如, 此属性填充 SharePoint 中用户执行的事件的 passport 唯一 ID (PUID)。此属性还可能指定与其他服务和系统帐户执行的事件中发生的事件的**UserID**属性相同的值。<br/> |全部  <br/> |
|UserSharedWith  <br/> |与之共享资源的用户。如果**Operation**属性的值为**SharingSet**, 则包含此属性。此用户也在报告中的 "**共享与**" 列中列出。<br/> |SharePoint  <br/> |
|UserType  <br/> |执行此操作的用户的类型。以下值指示用户类型。<br/> <br/> **0** -常规用户。 <br/>**2** -Office 365 组织中的管理员。 <br/>**3** -Microsoft 数据中心管理员或数据中心系统帐户。 <br/>**4** -系统帐户。 <br/>**5** -应用程序。 <br/>**6** -服务主体。<br/>**7** -自定义策略。<br/>**8** -系统策略。 |全部  <br/> |
|版本  <br/> |指示已记录的活动的版本号 (由**操作**属性标识)。  <br/> |全部  <br/> |
|工作负荷  <br/> |发生活动的 Office 365 服务。此属性的可能值为:<br/> <br/>**SharePoint<br/>OneDrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>合规<br/>性<br/>Sway Skype for<br/>business<br/>SecurityComplianceCenter<br/>PowerBI CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>项目<br/>PowerApps<br/>工作区分析**|全部  <br/> |
||||
   
请注意, 当查看特定事件的详细信息时, 如果单击 "**详细信息**", 也会显示上面介绍的属性。 
  
![单击 "详细信息" 查看审核日志事件记录的详细属性](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  

