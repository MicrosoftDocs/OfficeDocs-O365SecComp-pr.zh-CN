---
title: EOP 功能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 下表提供了 Exchange Online Protection (EOP) 托管的电子邮件筛选服务中可用的功能列表。
ms.openlocfilehash: 764ee616467cba29126139fdbf43f278dad30769
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026669"
---
# <a name="eop-features"></a>EOP 功能

下表提供了 Exchange Online Protection (EOP) 托管的电子邮件筛选服务中可用的功能列表。 
  
> [!TIP]
> [适用于企业的 Office 365 路线图](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)在找到有关即将推出的新功能的信息方面是不错的资源。有关不同 EOP 订阅计划中的可用功能的更全面介绍，请参阅 [Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。 
  
|||
|:-----|:-----|
|**功能** <br/> |**说明** <br/> |
|**反垃圾邮件保护** <br/> ||
|入站垃圾邮件检测  <br/> |入站反垃圾邮件保护始终处于启用状态，不能禁用。您可以通过连接筛选器和内容筛选器策略配置自定义设置。  <br/> 为独立 EOP 客户： 默认情况下，EOP 内容筛选器将垃圾邮件检测到的邮件发送到每个收件人的垃圾邮件文件夹。但是，为了帮助确保**移动到垃圾邮件文件夹的邮件**操作将处理的本地邮箱，必须配置两个 Exchange 传输规则来检测垃圾邮件邮件头由 EOP 添加您的本地服务器上。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。           |
|出站垃圾邮件检测  <br/> |如果您使用服务来发送出站电子邮件，从而帮助保护使用本服务和及其目标的收件人的组织，则始终启用出站反垃圾邮件保护。类似于入站筛选，出站垃圾邮件筛选组成连接筛选和内容筛选。出站垃圾邮件筛选设置不是可配置的但有出站垃圾邮件可用于配置可疑和阻止的出站邮件的管理员通知的策略设置。有关详细信息，请参阅[配置出站垃圾邮件策略](../configure-the-outbound-spam-policy.md)。<br/> |
|NDR 退信保护  <br/> |NDR 退信有关详细信息，请参阅设置[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)以及[退信消息和 EOP](../backscatter-messages-and-eop.md)中的 NDR 退信。  <br/> |
|批量邮件筛选  <br/> |EOP 已增强检测方法用于标识批量电子邮件。您可以配置要标记批量邮件通过用户界面的服务。您还可以通过搜索批量邮件消息标头戳创建更多的目的筛选批量邮件传输规则。有关批量电子邮件的详细信息，请参阅[垃圾邮件和批量邮件之间的区别是什么？](../what-s-the-difference-between-junk-email-and-bulk-email.md)和及其关联的副标题。<br/> |
|恶意 URL 阻止列表  <br/> |EOP 使用多个 URL 阻止列表，帮助检测邮件中的已知恶意链接。  <br/> |
|防钓鱼保护  <br/> |EOP 包括 750,000 个已知垃圾邮件制造者的域。  <br/> |
|**垃圾邮件管理** <br/> ||
|配置连接筛选器 IP 允许和 IP 阻止列表的能力  <br/> |在连接筛选器中指定的 IP 地址针对单个 IP 地址和 CIDR IP 地址范围。服务还支持 IPv6 地址。有关详细信息，请参阅[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。<br/> |
|按照用户、组或域来自定义内容筛选器策略的能力  <br/> |粒度，您可以创建自定义内容筛选器策略，并将它们应用于指定的用户、 组或域中您的组织。自定义策略始终优先于默认策略，但您可以更改您的自定义策略的优先级 （即运行顺序）。有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。<br/> |
|配置对内容经过筛选的邮件进行的操作的能力  <br/> |有多个可配置的操作。例如，可以删除经过内容筛选的邮件或将它们发送到垃圾邮件文件夹或隔离邮箱。有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。<br/> |
|配置高级选项以实现积极的垃圾邮件筛选的能力  <br/> |有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)（这是您在其中配置这些） 和[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)（它提供有关每个选项的用途的特定详细信息）。  <br/> |
|国际垃圾邮件筛选  <br/> |您可以配置 EOP 来筛选以特定语言撰写或从特定国家或地区发送的邮件。您可以配置最多 86 不同的语言和 250 不同的区域。该服务将应用高可信度垃圾邮件配置的操作。有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。<br/> |
|通过 Outlook 或 Outlook Web App (OWA) 管理垃圾邮件  <br/> |管理员和最终用户可以创建安全发件人列表和阻止发件人列表。详细信息  <br/> OWA：参阅[阻止或允许（垃圾邮件设置）](https://go.microsoft.com/fwlink/p/?LinkId=294862)。  <br/> Outlook：参阅[垃圾邮件筛选器概述](https://go.microsoft.com/fwlink/p/?LinkId=270065)。  <br/> 如果您使用 EOP 保护本地邮箱，请务必使用目录同步来帮助确保这些设置都会同步到服务。有关设置目录同步的详细信息，请参阅在[EOP 中的管理邮件用户](manage-mail-users-in-eop.md)的"使用目录同步管理邮件用户"。           |
|通过 Microsoft Office Outlook 的垃圾邮件报告加载项的垃圾邮件提交  <br/> |您可以向允许您提交垃圾邮件提交给 Microsoft 进行分析的 Outlook 外接程序下载。有关下载和使用此工具的详细信息，请参阅[启用报告消息加载项](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)。<br/> 如果您正在使用 Exchange Server 2013 与 EOP，您也可以右键单击在 OWA 中提交垃圾邮件[报告垃圾邮件和网络钓鱼诈骗在 web 上的 Outlook](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中所述。  <br/> |
|通过电子邮件别名的垃圾邮件和垃圾邮件提交  <br/> |您可以提交垃圾邮件 （垃圾） 和 （非垃圾邮件） 的非垃圾邮件提交给 Microsoft 通过电子邮件。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。<br/> |
|通过 OWA 垃圾邮件报告的垃圾邮件和非垃圾邮件提交  <br/> |您可以提交垃圾邮件和非垃圾邮件提交给 Microsoft 通过 OWA 垃圾邮件报告。有关详细信息，请参阅[报告垃圾邮件和网络钓鱼诈骗在 web 上的 Outlook 中](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。<br/> 此功能当前适用于将通过 EOP 筛选其 Exchange Server 2013 SP1 邮箱的 Outlook Web App (OWA) 客户。Exchange Online OWA 客户不久也将拥有此功能。           |
|最终用户垃圾邮件隔离通知  <br/> |最终用户可以释放其自己的垃圾邮件隔离邮件并 （可选） 将其报告为非垃圾邮件通过最终用户垃圾邮件通知消息。必须配置并[配置最终用户垃圾邮件通知在 Exchange Online](../configure-end-user-spam-notifications-in-exchange-online.md)或[在 EOP 中的配置最终用户垃圾邮件通知](../configure-end-user-spam-notifications-in-eop.md)中所述，由管理员，启用这些通知电子邮件。<br/> |
|最终用户垃圾邮件隔离通知频率  <br/> |默认情况下此频率为 3 天，可配置为 1 到 15 天。  <br/> |
|管理员配置最终用户垃圾邮件隔离通知的语言的能力  <br/> |对最终用户和管理员可用。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  <br/> |
|通过网页访问和管理隔离中的邮件  <br/> |对最终用户和管理员可用。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  <br/> |
|可以搜索隔离邮箱  <br/> |管理员和最终用户均可搜索隔离邮箱，以查找特定的垃圾邮件。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  <br/> |
|从 Exchange 管理中心查看作为垃圾邮件隔离的邮件头  <br/> |在隔离中查看邮件头后，您还可以复制邮件头文本并将其粘贴到[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)中，其中介绍了邮件发生了什么。  <br/> |
|**反恶意软件保护** <br/> ||
|多引擎反恶意软件保护  <br/> |多引擎反恶意软件保护可始终自动保护我们的客户。  <br/> |
|禁用恶意软件筛选的选项  <br/> |因为我们将对通过此服务发送的所有电子邮件强制进行反恶意软件扫描，因此您无法禁用恶意软件筛选。我们相信，为我们的所有客户提供一致且严格的保护级别是深度防御策略的关键部分，该策略是保护电子邮件环境所必需的。因此，对所有客户自动启用恶意软件筛选。  <br/> |
|邮件正文和附件的恶意软件检查  <br/> |服务可检测邮件正文中的活动有效负载和所有邮件附件是否存在恶意软件。  <br/> |
|默认或自定义恶意软件警报通知  <br/> |您可以选择时邮件被检测为恶意软件和未送达向发件人或管理员发送通知电子邮件。删除整个邮件时，仅会发送这些通知。有关详细信息，请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。<br/> |
|在检测到恶意软件时删除附件的选项  <br/> |管理员可以选择是要删除整个邮件，还是删除附件并向收件人发送自定义的消息。有关详细信息，请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。<br/> |
|反间谍软件保护  <br/> |反恶意软件保护包括反病毒保护和反间谍软件保护。  <br/> |
|按照用户、组或域来自定义恶意软件筛选器策略的能力  <br/> |粒度，可以创建自定义恶意软件筛选器策略并将它们应用于指定的用户、 组或域中您的组织。自定义策略始终优先于默认策略，但您可以更改您的自定义策略的优先级 （即运行顺序）。有关详细信息，请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。<br/> |
|**邮件路由与连接器** <br/> ||
|有条件的邮件路由  <br/> |有关详细信息，请参阅[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)。  <br/> |
|机会型或强制 TLS  <br/> |连接器提供机会型或强制 TLS。机会型 TLS 尝试 TLS 连接，但如果 TLS 连接失败使用的 SMTP 连接。强制 TLS 强制 TLS 连接，这意味着，如果 TLS 连接失败，邮件被拒绝。有关 TLS、 安全性和连接器的详细信息，请参阅[设置用于与合作伙伴组织的安全邮件流的连接器](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。<br/> |
|区域路由（将邮件流限制到指定区域）  <br/> |有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"部分。  <br/> |
|SMTP 连接检查程序工具  <br/> |有关使用此工具测试邮件流的详细信息，请参阅[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)。  <br/> |
|匹配子域  <br/> |有关发送至接受域的子域或从其发送的电子邮件流的详细信息，请参阅[在 EOP 中为子域启用电子邮件流](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)。  <br/> |
|**传输规则** <br/> ||
|基于策略的筛选和操作  <br/> |自定义策略基于 Exchange 传输规则。您可以通过域、 关键字、 文件名、 文件类型、 主题行、 邮件正文、 发件人、 收件人、 标头和 IP 地址进行筛选。有关详细信息，请参阅[Mail flow 规则 （传输规则） 在 Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。<br/> |
|按文本模式进行筛选  <br/> |传输规则可以使用数组或正则表达式匹配文本。您也可以使用一个字符串或字符串数组匹配多个邮件属性，例如地址、主题、正文或附件名称。有关详细信息，请参阅[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)。<br/> |
|自定义词典  <br/> |传输规则可包括文本和关键字的长列表，提供与自定义词典相同的功能。  <br/> |
|每个域策略规则  <br/> |传输规则的范围可以自定义，以匹配发件人或收件人域名称、IP 地址范围，地址关键字或模式、组成员关系及其他条件。有关详细信息，请参阅[Transport Rule Conditions (Predicates)](http://technet.microsoft.com/library/04edeaba-afd4-4207-b2cb-51bcc44e483c.aspx)。<br/> |
|附件扫描  <br/> |可以创建规则，以扫描附件的文件名、扩展名和内容。  <br/> |
|向发件人发送策略规则通知  <br/> |您可以拒绝邮件，并向发件人通过**拒绝该邮件并提供说明**或**拒绝具有以下增强的状态代码邮件**操作发送未送达报告 (NDR)。有关详细信息，请参阅[传输规则操作](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。<br/> |
|将邮件发送到固定地址（如重定向或将邮件复制到特定地址）  <br/> |传输规则可以重定向收件人、通过抄送或密件抄送添加收件人、仅添加收件人，还有其他选项。有关详细信息，请参阅[Transport rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。<br/> |
|轻松调整多个规则的优先级的能力  <br/> |使用 Exchange 管理中心更改规则的处理顺序。有关详细信息，请参阅[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx)。  <br/> |
|筛选邮件并更改邮件的路由或属性的能力  <br/> |您可以根据各种条件筛选邮件，并将一系列操作应用于每封邮件。有关详细信息，请参阅[Mail flow 规则 （传输规则） 在 Exchange Online Protection](mail-flow-rules-transport-rules-0.md)。<br/> |
|按照规则更改邮件的垃圾邮件可信度。  <br/> |您可以检查中转消息，并将垃圾邮件可信度级别分配给它根据您选择的条件。有关详细信息，请参阅[使用邮件流规则设置垃圾邮件可信度 (SCL) 中的邮件](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。<br/> |
|检查邮件附件  <br/> |您可以检查附件内容或附加文件的特性，并根据结果定义要采取的操作。有关详细信息，请参阅[Using transport rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。  <br/> |
|**管理** <br/> ||
|基于 Web 的管理  <br/> |EOP 管理员可以管理该服务通过 60 种语言支持的 Exchange 管理员中心 (EAC) 接口。有关详细信息，请参阅[Exchange 管理中心在 Exchange Online Protection ](../exchange-admin-center-in-exchange-online-protection-eop.md)。<br/> |
|目录同步  <br/> |目录同步通过 Azure Active Directory 同步工具提供。有关详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中的"使用目录同步管理邮件用户"部分。  <br/> |
|基于目录的边缘阻止 (DBEB)  <br/> |通过 DBEB 功能，您可以在服务网络外围拒绝发送至无效收件人的邮件。DBEB 可让管理员向 Office 365 添加已启用邮件的收件人，并阻止发送到 Office 365 中不存在的电子邮件地址的所有邮件。有关配置 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。  <br/> |
|远程 Windows PowerShell 访问  <br/> |远程 Windows PowerShell 提供完整的 EOP 功能。有关详细信息，请参阅 [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)。  <br/> |
|**报告和日志记录** <br/> ||
|邮件跟踪  <br/> |邮件跟踪功能使您可以作为管理员在邮件经过服务时对邮件进行跟踪。该功能有助于您确定目标邮件是否被接收、拒绝、推迟或由 Exchange 服务进行了传递。这使得您可以有效回答用户的问题，解决邮件流问题，验证策略更改，并减少联系技术支持寻求帮助的需要。有关详细信息，请参阅[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。  <br/> |
|基于 Web 的报告  <br/> |Office 365 管理中心的邮件保护报告提供邮件数据。例如，您可以监控检测到多少垃圾邮件和恶意软件，或者传输规则匹配的频率如何。通过这些交互式报告，您可以快速获取摘要数据的可视报告，并进一步了解每封邮件的详细信息（可回溯 90 天）。有关详细信息，请参阅[Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)。  <br/> |
|通过 Excel 报告工作簿进行详细报告  <br/> |另外还提供 Excel 2013 报告工作簿格式的电子邮件保护报告。但是，我们建议转为使用增强的 Office 365 管理中心报告。Excel 2013 报告工作簿计划将在未来弃用。  <br/> |
|审核日志记录  <br/> |向 EOP 管理员提供管理员角色组报告和管理员审核日志。有关详细信息，请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。  <br/> |
|**服务级别协议 (SLA) 及支持** <br/> ||
|垃圾邮件有效性 SLA  <br/> |\>99%  <br/> |
|误报率 SLA  <br/> |\<1:250,000  <br/> |
|病毒检测和阻止 SLA  <br/> |100% 的已知病毒  <br/> |
|每月运行时间 SLA  <br/> |99.999%  <br/> |
|24 小时全天候电话和网络技术支持  <br/> |有关 EOP 帮助和支持选项的详细信息，请参阅 [EOP 帮助与支持](help-and-support-for-eop.md)。  <br/> |
|**其他功能** <br/> ||
|服务器的地理位置冗余全局网络  <br/> |EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"一节。  <br/> |
|内部部署服务器无法接受邮件时的邮件队列  <br/> |延期的邮件将在我们的队列中保留 2 天。重试发送邮件的依据为从收件人的邮件系统返回的错误。邮件一般每 5 分钟重试发送一次。有关详细信息，请参阅 [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)。  <br/> |
|Office 365 邮件加密可作为附加服务使用  <br/> |有关详细信息，请参阅 [Office 365 中的加密](https://technet.microsoft.com/en-us/library/dn569286.aspx)。  <br/> |
   

