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
ms.openlocfilehash: 51db286757ddb6a0d158a72196b48ff412d33e5f
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670667"
---
# <a name="eop-features"></a>EOP 功能

下表提供了 Exchange Online Protection (EOP) 托管的电子邮件筛选服务中可用的功能列表。 
  
> [!TIP]
> [适用于企业的 Office 365 路线图](https://office.microsoft.com/en-us/products/office-365-roadmap-FX104343353.aspx)在找到有关即将推出的新功能的信息方面是不错的资源。有关不同 EOP 订阅计划中的可用功能的更全面介绍，请参阅 [Exchange Online Protection 服务说明](https://go.microsoft.com/fwlink/p/?LinkId=320619)。 
  
|||
|:-----|:-----|
|**功能**|**说明**|
|**反垃圾邮件保护**||
|入站垃圾邮件检测|入站反垃圾邮件保护始终处于启用状态，不能禁用。您可以通过连接筛选器和内容筛选器策略配置自定义设置。  <br/> 对于 EOP 独立客户: 默认情况下, EOP 内容筛选器将检测到的垃圾邮件发送到每个收件人的 "垃圾邮件" 文件夹。 但是, 为了帮助确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 必须在您的本地服务器上配置两个 Exchange 邮件流规则 (也称为传输规则), 以检测添加的垃圾邮件头由 EOP。 有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。|
|出站垃圾邮件检测|如果您使用出站反垃圾邮件保护来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。 与入站筛选一样，出站垃圾邮件筛选由连接筛选和内容筛选组成。 出站垃圾邮件筛选设置不可配置，但您可以使用某些出站垃圾邮件策略设置来配置针对可疑和被阻止出站邮件的管理员通知。 有关详细信息, 请参阅[配置出站垃圾邮件策略](../configure-the-outbound-spam-policy.md)。|
|NDR 退信保护|有关 NDR 退信的详细信息, 请参阅[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)中的 ndr 退信设置以及[退信邮件和 EOP](../backscatter-messages-and-eop.md)。|
|批量邮件筛选|EOP 具有识别批量电子邮件的增强检测方法。 您可以将服务配置为通过用户界面标记批量电子邮件。 您还可以通过搜索批量邮件邮件头标记来创建邮件流规则, 以更严格地筛选批量邮件。 有关批量电子邮件的详细信息, 请参阅[垃圾邮件和批量电子邮件之间的区别是什么？](../what-s-the-difference-between-junk-email-and-bulk-email.md)及其关联的副标题。|
|恶意 URL 阻止列表|EOP 使用多个 URL 阻止列表，帮助检测邮件中的已知恶意链接。|
|防钓鱼保护|EOP 包括 750,000 个已知垃圾邮件制造者的域。|
|**垃圾邮件管理**||
|配置连接筛选器 IP 允许和 IP 阻止列表的能力|连接筛选器中指定的 IP 地址可以是单个 IP 地址和 CIDR IP 地址范围。 服务还支持 IPv6 地址。 有关详细信息，请参阅[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。|
|按照用户、组或域来自定义内容筛选器策略的能力|更精确地讲，您可以创建自定义内容筛选策略，并将其应用到组织中的特定用户、组或域。 虽然自定义策略的优先级始终高于默认策略，但可以更改自定义策略的优先级（即运行顺序）。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。|
|配置对内容经过筛选的邮件进行的操作的能力|有多个可配置的操作。 例如，您可以删除内容筛选的邮件或将其发送到"垃圾邮件"文件夹或隔离区。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。|
|配置高级选项以实现积极的垃圾邮件筛选的能力|有关详细信息, 请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)(即配置它们的位置) 和[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)(提供有关每个选项所执行操作的具体详细信息)。|
|国际垃圾邮件筛选|您可以将 EOP 配置为筛选以特定语言编写的邮件，或来自特定国家或地区的邮件。 您最多可以配置 86 种不同的语言和 250 种不同的区域。 该服务将针对高可信度垃圾邮件应用配置的操作。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。|
|通过 outlook 或 web 上的 outlook (以前称为 Outlook web App) 管理垃圾邮件|管理员和最终用户可以创建安全发件人列表和阻止发件人列表。 详细信息  <br/> Outlook 网页: 请参阅[阻止或允许 (垃圾邮件设置)](https://go.microsoft.com/fwlink/p/?LinkId=294862)。  <br/> Outlook：参阅[垃圾邮件筛选器概述](https://go.microsoft.com/fwlink/p/?LinkId=270065)。  <br/> 如果您使用 EOP 帮助保护本地邮箱, 请务必使用目录同步来帮助确保这些设置已同步到服务。 有关如何设置目录同步的详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中的"使用目录同步管理邮件用户"。|
|通过 Microsoft Office Outlook 的垃圾邮件报告加载项的垃圾邮件提交|您可以将加载项下载到 Outlook，以允许您将垃圾邮件提交给 Microsoft 进行分析。 有关下载和使用此工具的详细信息, 请参阅[Enable the Report Message 外接程序](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)。  <br/> 如果您使用的是 EOP 的 Exchange Server 2013 或更高版本, 您还可以在 web 上的 outlook 中右键单击以提交垃圾邮件, 如在[outlook 网页中报告垃圾电子邮件和网络钓鱼诈骗](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)中所述。|
|通过电子邮件别名的垃圾邮件和垃圾邮件提交|您可以通过电子邮件将垃圾邮件和非垃圾邮件提交给 Microsoft。 有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。|
|通过 web 上的 Outlook 进行的垃圾邮件和非垃圾邮件提交垃圾邮件报告|您可以通过 web 上的 Outlook 垃圾邮件报告将垃圾邮件和非垃圾邮件提交给 Microsoft。 有关详细信息，请参阅 [Report junk email and phishing scams in Outlook on the web](../report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)。  <br/> 此功能当前可供 Outlook 在其 Exchange Server 2013 SP1 或更高版本的邮箱正在通过 EOP 筛选的 web 客户上使用。 web 上的 Exchange Online Outlook 客户在不久的将来也将具有此功能。|
|最终用户垃圾邮件隔离通知|最终用户可以释放自己的垃圾邮件隔离邮件，并选择通过最终用户垃圾邮件通知邮件将其报告为非垃圾邮件。 必须由管理员配置和启用这些通知电子邮件, 如在[Exchange Online 中配置最终用户垃圾邮件通知](../configure-end-user-spam-notifications-in-exchange-online.md)或[在 EOP 中配置最终用户垃圾邮件通知](../configure-end-user-spam-notifications-in-eop.md)中所述。|
|最终用户垃圾邮件隔离通知频率|默认情况下此频率为 3 天，可配置为 1 到 15 天。|
|管理员配置最终用户垃圾邮件隔离通知的语言的能力|对最终用户和管理员可用。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|通过网页访问和管理隔离中的邮件|对最终用户和管理员可用。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|可以搜索隔离邮箱|管理员和最终用户均可搜索隔离邮箱，以查找特定的垃圾邮件。有关详细信息，请参阅[Find and release quarantined messages as an administrator](../find-and-release-quarantined-messages-as-an-administrator.md)或[Find and Release Quarantined Messages as an End User](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx)。  |
|从 Exchange 管理中心查看作为垃圾邮件隔离的邮件头|在隔离中查看邮件头后，您还可以复制邮件头文本并将其粘贴到[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)中，其中介绍了邮件发生了什么。|
|**反恶意软件保护**||
|多引擎反恶意软件保护|多引擎反恶意软件保护可始终自动保护我们的客户。|
|禁用恶意软件筛选的选项|因为我们将对通过此服务发送的所有电子邮件强制进行反恶意软件扫描，因此您无法禁用恶意软件筛选。我们相信，为我们的所有客户提供一致且严格的保护级别是深度防御策略的关键部分，该策略是保护电子邮件环境所必需的。因此，对所有客户自动启用恶意软件筛选。|
|邮件正文和附件的恶意软件检查|服务可检测邮件正文中的活动有效负载和所有邮件附件是否存在恶意软件。|
|默认或自定义恶意软件警报通知|您可以选择在未传送检测为恶意软件的邮件时，发送通知电子邮件给发件人或管理员。 删除整个邮件时，只会发送这些通知。 有关详细信息, 请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。|
|在检测到恶意软件时删除附件的选项|管理员可以选择是删除整个邮件，还是删除附件并向收件人发送一封自定义的邮件。 有关详细信息, 请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。|
|反间谍软件保护|反恶意软件保护包括反病毒保护和反间谍软件保护。|
|按照用户、组或域来自定义恶意软件筛选器策略的能力|更精确地讲，您可以创建自定义恶意软件筛选策略，并将其应用到组织中的特定用户、组或域。 自定义策略的优先级总是高于默认策略，但您可以更改自定义策略的优先级（即运行顺序）。 有关详细信息, 请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。|
|**邮件路由与连接器**||
|有条件的邮件路由|有关详细信息，请参阅[Create Connectors for Conditional Mail Routing](http://technet.microsoft.com/library/905dc235-1d2b-487e-a65a-516d92e88347.aspx)。|
|机会型或强制 TLS|机会型或强制 TLS 在连接器中可用。 机会型 TLS 尝试建立 TLS 连接，当 TLS 连接失败时，则使用 SMTP 连接。 强制 TLS 强制建立 TLS 连接，这意味着当 TLS 连接失败时，邮件将被拒绝。 有关 TLS、安全性以及连接器的详细信息，请参阅[Set up connectors for secure mail flow with a partner organization](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。|
|区域路由（将邮件流限制到指定区域）|有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"部分。|
|SMTP 连接检查程序工具|有关使用此工具测试邮件流的详细信息，请参阅[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)。|
|匹配子域|有关发送至接受域的子域或从其发送的电子邮件流的详细信息，请参阅[在 EOP 中为子域启用电子邮件流](http://technet.microsoft.com/library/b5684042-dadc-4111-95b3-c2fd06e368bf.aspx)。|
|**邮件流规则**||
|基于策略的筛选和操作|自定义策略基于 Exchange 邮件流规则。 您可以通过域、关键字、文件名、文件类型、主题行、邮件正文、发件人、收件人、邮件头和 IP 地址进行筛选。 有关详细信息, 请参阅[Exchange Online Protection 中的邮件流规则 (传输规则)](mail-flow-rules-transport-rules-0.md)。|
|按文本模式进行筛选|邮件流规则可以使用数组或正则表达式匹配文本。 您也可以使用一个字符串或字符串数组匹配多个邮件属性，例如地址、主题、正文或附件名称。 有关详细信息, 请参阅[Exchange Online Protection 中的邮件流规则 (传输规则)](mail-flow-rules-transport-rules-0.md)|
|自定义词典|邮件流规则可以包括长文本和关键字列表, 并提供与自定义词典相同的功能。|
|每个域策略规则|可以自定义邮件流规则的作用域, 以匹配发件人或收件人域名、IP 地址范围、地址关键字或模式、组成员身份以及其他条件。|
|附件扫描|可以创建规则，以扫描附件的文件名、扩展名和内容。|
|向发件人发送策略规则通知|You can reject messages and send a non-delivery report (NDR) to the sender via the **Reject the message with the explanation** or **Reject the message with the enhanced status code** action. 有关详细信息, 请参阅[Mail flow rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。|
|将邮件发送到固定地址（如重定向或将邮件复制到特定地址）|邮件流规则可以通过抄送或密件抄送添加收件人, 只需添加收件人和其他选项即可进行重定向。 有关详细信息, 请参阅[Mail flow rule actions](http://technet.microsoft.com/library/f8621ecb-a177-4025-9011-a6569999746a.aspx)。|
|轻松调整多个规则的优先级的能力|使用 Exchange 管理中心更改规则的处理顺序。|
|筛选邮件并更改邮件的路由或属性的能力|您可以根据多种条件筛选邮件，然后对每个邮件应用一系列操作。 有关详细信息, 请参阅[Exchange Online Protection 中的邮件流规则 (传输规则)](mail-flow-rules-transport-rules-0.md)。|
|按照规则更改邮件的垃圾邮件可信度。|您可以检测传输中的邮件并根据您选择条件，向其分配垃圾邮件可信度。 有关详细信息, 请参阅[使用邮件流规则在邮件中设置垃圾邮件可信度级别 (SCL)](../use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)。|
|检查邮件附件|您可以检查附件内容或附加文件的特性，并根据结果定义要采取的操作。 有关详细信息, 请参阅[使用邮件流规则检查邮件附件](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。|
|**管理**||
|基于 Web 的管理|EOP 管理员可以通过 Exchange 管理中心 (EAC) 界面（支持 60 种语言）管理服务。 有关详细信息, 请参阅 exchange [Online Protection 中的 exchange 管理中心](../exchange-admin-center-in-exchange-online-protection-eop.md)。|
|目录同步|目录同步通过 Azure Active Directory 同步工具提供。有关详细信息，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中的"使用目录同步管理邮件用户"部分。  |
|基于目录的边缘阻止 (DBEB)|通过 DBEB 功能，您可以在服务网络外围拒绝发送至无效收件人的邮件。DBEB 可让管理员向 Office 365 添加已启用邮件的收件人，并阻止发送到 Office 365 中不存在的电子邮件地址的所有邮件。有关配置 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。  |
|远程 Windows PowerShell 访问|远程 Windows PowerShell 提供完整的 EOP 功能。有关详细信息，请参阅 [Exchange Online Protection 中的 PowerShell](http://technet.microsoft.com/library/f7918a88-774a-405e-945b-bc2f5ee9f748.aspx)。  |
|**报告和日志记录**||
|邮件跟踪|邮件跟踪功能使您可以作为管理员在邮件经过服务时对邮件进行跟踪。该功能有助于您确定目标邮件是否被接收、拒绝、推迟或由 Exchange 服务进行了传递。这使得您可以有效回答用户的问题，解决邮件流问题，验证策略更改，并减少联系技术支持寻求帮助的需要。有关详细信息，请参阅[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。  |
|基于 Web 的报告|Microsoft 365 管理中心中的邮件保护报告提供了邮件传输数据。 例如, 您可以监视检测到的垃圾邮件和恶意软件的数量或邮件流规则匹配的频率。 通过这些交互式报告，您可以快速获取摘要数据的可视报告，并进一步了解每封邮件的详细信息（可回溯 90 天）。 有关详细信息，请参阅[Use mail protection reports in Office 365 to view data about malware, spam, and rule detections](http://technet.microsoft.com/library/bcef7984-4bfa-4ca8-9fa5-a65af8618f5d.aspx)。|
|通过 Excel 报告工作簿进行详细报告|另外还提供 Excel 2013 报告工作簿格式的电子邮件保护报告。 但是, 我们建议改为使用管理中心报告。 Excel 2013 报告工作簿计划将在未来弃用。|
|审核日志记录|向 EOP 管理员提供管理员角色组报告和管理员审核日志。有关详细信息，请参阅[EOP 中的审核报告](auditing-reports-in-eop.md)。  |
|**服务级别协议 (SLA) 及支持**||
|垃圾邮件有效性 SLA|\>99%|
|误报率 SLA|\<1:250,000|
|病毒检测和阻止 SLA|100% 的已知病毒|
|每月运行时间 SLA|99.999%|
|24 小时全天候电话和网络技术支持|有关 EOP 帮助和支持选项的详细信息，请参阅 [EOP 帮助与支持](help-and-support-for-eop.md)。|
|**其他功能**||
|服务器的地理位置冗余全局网络|EOP 在数据中心的全球网络中运行，旨在提供最好的可用性。有关详细信息，请参阅 [Exchange Online Protection 概述](exchange-online-protection-overview.md)中的"EOP 数据中心"一节。  |
|内部部署服务器无法接受邮件时的邮件队列|延期的邮件将在我们的队列中保留 2 天。重试发送邮件的依据为从收件人的邮件系统返回的错误。邮件一般每 5 分钟重试发送一次。有关详细信息，请参阅 [EOP 排队、延迟以及退回邮件的常见问题](eop-queued-deferred-and-bounced-messages-faq.md)。  |
|Office 365 邮件加密可作为附加服务使用|有关详细信息，请参阅 [Office 365 中的加密](https://technet.microsoft.com/en-us/library/dn569286.aspx)。|
   

