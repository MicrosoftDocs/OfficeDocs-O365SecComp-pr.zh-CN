---
title: 数据丢失防护策略概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 1966b2a7-d1e2-4d92-ab61-42efbb137f5e
description: 与 Office 365 安全性的数据丢失防护 (DLP) 策略&amp;合规性中心，您可以确定、 监视和自动跨 Office 365 中保护敏感信息。
ms.openlocfilehash: e9d033bc54aae6bc1c8089793dbc618f11bef273
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013736"
---
# <a name="overview-of-data-loss-prevention-policies"></a>数据丢失防护策略概述

若要遵守业务标准和行业法规，组织需要保护敏感信息和防止其无意中泄漏。您可能希望阻止泄漏组织外部的敏感信息的示例包括财务数据或如信用卡号、 社会保险号码或运行状况记录的个人身份信息 (PII)。与 Office 365 安全性的数据丢失防护 (DLP) 策略&amp;合规性中心，您可以确定、 监视和自动跨 Office 365 中保护敏感信息。
  
您可以使用 DLP 策略实现以下功能：
  
- **跨多个位置，例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 标识敏感信息。**
    
    例如，可以标识包含信用卡号码存储在任何 OneDrive for Business 站点中的任何文档或可以监视只需特定的某个人的 OneDrive 网站。
    
- **防止意外共享敏感信息**。 
    
    例如，您可以识别的所有文档或电子邮件包含与组织外部的人员共享的健康记录，然后自动阻止对该文档的访问或阻止发送的电子邮件。
    
- **监视和保护桌面版本的 Excel 2016、PowerPoint 2016 和 Word 2016 中的敏感信息。**
    
    就像在 Exchange Online、 SharePoint Online 和 OneDrive for Business，这些 Office 2016 桌面程序包括相同的功能，以确定敏感信息并应用 DLP 策略。DLP 提供连续监控时人员共享这些 Office 2016 程序中的内容。
    
- **帮助用户了解如何保持符合性，同时不会中断工作流。**
    
    您可以告知用户在 DLP 策略，并帮助他们不阻止其工作保持兼容。例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以同时向他们发送的电子邮件通知并将其显示策略提示允许其在他们有业务替代策略的文档库的上下文中理由。在 Outlook 中的 web、 Outlook 2013 和更高版本，Excel 2016、 PowerPoint 2016 和 Word 2016 上也会显示相同的策略提示。
    
- **查看 DLP 报告显示内容相匹配您的组织的 DLP 策略。**
    
    若要评估贵组织遵守 DLP 策略，您可以看到多少匹配的每个策略和规则均具有随着时间的推移。如果 DLP 策略允许用户覆盖策略提示并报告为误报，您还可以查看用户已报告。
    
创建和管理 Office 365 安全性数据丢失防护页上的 DLP 策略&amp;合规性中心。
  
![Office 365 安全性的数据丢失防护页&amp;合规性中心](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>DLP 策略包含的内容

DLP 策略包含以下基本内容：
  
- 若要保护的内容-**位置**例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 站点的位置。 
    
- 何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容： 
    
  - **条件**内容都匹配时才会强制执行规则-例如，只查找包含社会保险号码已与您的组织外部的人员共享的内容。 
    
  - 找到满足条件的内容时您希望规则自动执行的**操作**。例如，阻止访问文档，以及向用户和合规部主管发送电子邮件通知。 
    
您可以使用规则以满足特定保护要求，并将 DLP 策略以便组合在一起常见保护要求，如全部所需遵守特定法规的规则。
  
例如，您可能必须 DLP 策略，可帮助您检测存在受约束的健康保险便利和义务法案 (HIPAA) 的信息。此 DLP 策略可以帮助保护跨所有 SharePoint Online 网站和所有 OneDrive for Business 站点 （在何处） HIPAA 数据 （功能） 的查找包含与 (贵组织外部的人员共享此敏感信息的任何文档条件），然后阻止对文档的访问并发送通知 （操作）。这些要求存储为各个规则而组合在一起以简化管理和报告的 DLP 策略。
  
![图表显示了 DLP 策略包含位置和规则](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>位置

DLP 策略可以查找和保护敏感信息跨 Office 365，是否位于 Exchange Online、 SharePoint Online，或 OneDrive for Business 中的信息。您可以轻松地选择保护所有 SharePoint 网站或 OneDrive 帐户，只需特定站点或帐户或所有邮箱。请注意，它尚未可以选择仅特定用户的邮箱。
  
![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
请注意，如果您选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户，则 DLP 策略可以包含不超过 100 此类包含和排除规则。尽管存在此限制，了解您可以通过应用组织范围的策略或适用于整个位置策略超过此限制。
  
### <a name="rules"></a>规则

规则是什么强制实施业务要求您组织的内容。一个策略包含一个或多个规则，并每个规则组成条件和操作。对于每个规则，当满足的条件，则采取操作自动。启动与每个策略中的最高优先级规则按顺序，执行规则。
  
规则还提供选项以通知 （使用策略提示和电子邮件通知） 的用户和管理员 （与电子邮件事件报告） 的内容具有匹配的规则。
  
下面是一个规则的组件，每个如下所述。
  
![DLP 规则编辑器部分](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>条件

条件非常重要，因为它们确定哪些类型的信息要寻找，以及何时执行操作。例如，您可能选择内容包含多个十个此类号码并将其与您的组织外部的人员共享忽略内容包含护照号码。
  
条件侧重于**内容**，例如，要查找什么类型的敏感信息以及还**上下文**，如文档与共享谁。您可以使用条件来将不同的操作分配给不同的风险级别--例如，内部共享的敏感内容可能会降低风险和需要较少操作比敏感内容与组织外部的人员共享。 
  
![显示可用的 DLP 条件的列表](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
现在的可用条件可以确定以下内容：
  
- 内容包含敏感信息类型。
    
- 内容包含标签。有关详细信息，请参阅以下部分[使用 DLP 策略中，以状态标签](data-loss-prevention-policies.md#label)。
    
- 内容是与您组织的外部还是内部人员共享。
    
#### <a name="types-of-sensitive-information"></a>敏感信息类型

DLP 策略可以帮助保护敏感信息，定义为**敏感信息类型**。Office 365 跨多个可供您使用，如信用卡号、 银行帐号、 国家/地区 ID 编号和护照号码的不同区域包括许多常见的敏感信息类型定义。 
  
![可用敏感信息类型列表](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
当 DLP 策略查找如信用卡号的敏感信息类型时，它不只是查找一个 16 位数字。每种敏感信息类型定义，通过使用的组合检测到：
  
- 关键字
    
- 用于验证校验和或撰写的内部函数
    
- 用于查找模式匹配的正则表达式评估
    
- 其他内容检查
    
这有助于减少的误报可以中断人们的工作时实现准确性很大程度的 DLP 检测。
  
#### <a name="actions"></a>操作

当内容都匹配规则中的条件时，可以应用操作以自动保护的内容。
  
![可用 DLP 操作列表](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
使用现已推出的操作，您可以：
  
- **限制对内容的访问**对于网站内容，这意味着的文档权限被限制网站集主管理员、 文档所有者和上次修改文档的人员之外的任何用户。这些人员可以从文档中移除敏感信息或采取其他补救措施。合规性文档时，将自动还原原始的权限。时将阻止对文档的访问，与网站上的库中的特殊策略提示图标显示文档。 
    
    ![显示文档访问被拦截的策略提示](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    电子邮件内容，此操作阻止发送邮件。根据 DLP 规则的配置方式，发件人将看到 NDR 或 （如果此规则使用通知） 的策略提示和/或电子邮件通知。
    
    ![警告未经授权的收件人必须从邮件中删除](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>用户通知和用户重写

您可以使用通知和重写以告知用户在 DLP 策略，并帮助他们不阻止其工作保持兼容。例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以同时向他们发送的电子邮件通知并将其显示策略提示允许其在他们有业务替代策略的文档库的上下文中理由。
  
![用户通知和用户替代 DLP 规则编辑器部分](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
电子邮件可以通知发送、 共享，或上次修改的内容和，为网站内容、 网站集主管理员和文档所有者的人员。此外，您可以添加或删除何人您选择电子邮件通知。
  
除了发送的电子邮件通知，通知用户显示的策略提示：
  
- 在 Outlook 2013 及更高版本和 Outlook web 上。
    
- 针对业务网站上的 SharePoint Online 或 OneDrive 文档。
    
- 在 Excel 2016 PowerPoint 2016 和 Word 2016，当文档存储在网站上包含在 DLP 策略。
    
电子邮件通知和策略提示介绍内容与某个 DLP 策略冲突的原因。如果您选择，电子邮件通知和策略提示可以允许用户能够替代规则报告误报或提供的业务理由。这可以帮助您让用户了解您的 DLP 策略和实施这些不阻止它们的工作人员。有关重写和误报信息还用于报告 （参见下面有关 DLP 报告） 记录和事件中包含报告 （下一节），以便合规部主管可以定期查看此信息。
  
下面是策略提示的外观中的 OneDrive for Business 帐户。
  
![策略提示中的 OneDrive 帐户文档](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>事件报告

时匹配的规则时，可以与该事件的详细信息事件报告发送到您合规部主管 （或您选择的任何人）。此报表包含有关匹配，该规则和上次修改内容的人员的名称匹配的实际内容项的信息。对于电子邮件报告还包括作为附件原始邮件匹配 DLP 策略。
  
![用于配置事件报告的页面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>分组和逻辑运算符

通常 DLP 策略具有变得非常简单的要求，例如，若要确定包含美国社会保障号的所有内容。但是，在其他情况下，您的 DLP 策略可能需要确定更松散定义的数据。
  
例如，若要确定内容受美国健康保险法案 (HIPAA)，您需要查找：
  
- 包含敏感信息，如美国社会保障号或药品实施机构 (DEA) 号码的特定类型的内容。
    
    AND
    
- 内容的是更加难以确定，如 communications 有关患者的医护或医疗服务提供的说明。标识此内容需要匹配非常大的关键字列表，如国际分类的科 （ICD 9 厘米或 ICD 10 厘米） 中的关键字。
    
使用分组和逻辑运算符 (AND、 OR)，可以轻松地识别此类松散定义的数据。创建 DLP 策略时，您可以：
  
- 组敏感信息类型。
    
- 选择自己的组之间以及组中的敏感信息类型之间的逻辑运算符。
    
### <a name="choosing-the-operator-within-a-group"></a>选择组中的运算符

在组中，您可以选择是否必须为要与规则匹配的内容满足任何或所有该组中的条件。
  
![组显示组中的运算符](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>添加组

您可以快速添加一组，都可以具有自己的条件和该组中的运算符。
  
![添加组按钮](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>选择组之间的运算符

之间组，您可以选择要与规则匹配的内容是否必须满足中只有一个组或所有的组的条件。
  
例如，内置的**美国 HIPAA**策略具有的规则，以便它标识包含的内容使用**AND**运算符之间的组： 
  
- 从组**PII 标识符**(至少一个 SSN number**或**DEA) 
    
    **AND**
    
- 从组**医疗条款**（至少一个 ICD 9 厘米关键字**或**ICD-10-CM 关键字） 
    
![组显示组之间的运算符](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>按其处理规则优先级

在策略中创建规则时，每个规则分配顺序在其中创建-这意味着，创建的规则首先具有最高优先级的优先级，第二创建的规则具有第二个优先级，依此类推。创建规则后，不能更改其优先级，通过删除并重新创建除外。
  
![规则优先级顺序](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
时根据规则评估内容，以优先级顺序处理规则。如果内容与多个规则相匹配，规则优先级顺序中进行处理，并强制最严格的操作。例如，如果内容匹配的所有以下规则，因为它是最高优先级、 最严格的规则，将强制执行规则 3:
  
- 规则 1： 只将通知用户
    
- 规则 2： 通知用户，限制访问，并允许用户重写
    
- 规则 3： 将通知用户，限制访问，并且不允许用户重写
    
- 规则 4： 仅通知用户
    
- 规则 5： 限制访问
    
- 规则 6： 将通知用户，限制访问，并且不允许用户重写
    
本示例中，请注意，匹配的所有规则的审核日志中记录显示在 DLP 报告中，尽管在实施只最严格的规则。
  
对于策略提示，请注意:
  
- 仅从最高优先级的策略提示，将显示最严格的规则。例如，从规则阻止访问内容将显示通过策略提示从只发送通知的规则的策略提示。这将阻止用户查看策略提示的级联方式。
    
- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>调整规则以使其更容易或更加复杂，以匹配

人员创建和打开其 DLP 策略后，它们是有时会遇到这些问题的过程：
  
- **不是**敏感信息匹配的规则-换句话说，太多误报太多内容。 
    
- 太少的内容**为**敏感信息匹配规则-换句话说，保护不被强制执行的操作的敏感信息。 
    
为了解决这些问题，您可以通过调整实例计数优化您的规则和匹配准确性，使其更加复杂或更轻松地与规则匹配内容。在规则使用每个敏感信息类型具有两个实例对变量计数和匹配准确性。
  
### <a name="instance-count"></a>实例计数

实例计数只是表示特定类型的敏感信息出现多少次必须存在以内容的规则匹配。例如，内容将与下面显示是否 1 到 9 唯一美国或英国之间标识护照号码的规则匹配。
  
请注意，实例计数包括仅**唯一**匹配敏感信息类型和关键字。例如，如果电子邮件中包含 10 个相同的信用卡号，这些 10 个匹配项计数为信用卡号的单个实例。 
  
若要使用实例计数调整规则，指南非常简单：
  
- 若要使规则更轻松地匹配，降低的**分钟**数和/或增加**最大**的计数。您还可以设置**最大**到**任何**通过删除数值。 
    
- 若要使规则匹配更加复杂，增加的**分钟**数。 
    
通常，使用限制较少的操作，如发送用户通知，在规则与较低的实例计数 (例如，1-9)。并使用更严格的操作，如限制对内容的访问，但不允许用户重写规则具有更高版本 （例如，任何 10） 实例计数中。
  
![在规则编辑器中计数实例](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>匹配准确性

如上所述，定义和使用的不同类型的证据组合检测到的敏感信息类型。通常，由多个此类组合，调用模式定义的敏感信息类型。需要较少证据模式具有较低的匹配准确性 （或可信度） 时要求更多的证据具有匹配准确度 （或可信度） 的模式。若要了解有关的实际模式和每个敏感信息类型使用的可信度级别的详细信息，请参阅[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。
  
例如，名为信用卡号的敏感信息类型由两种模式进行定义：
  
- 需要的 65%自信地模式：
    
  - 信用卡号的格式的数字。
    
  - 一个数字，将传递校验和。
    
- 需要的 85%自信地模式：
    
  - 信用卡号的格式的数字。
    
  - 一个数字，将传递校验和。
    
  - 关键字或右格式的到期日期。
    
您可以使用这些在规则中可信度级别 （或匹配准确性）。通常，使用限制较少的操作，如发送用户通知，在规则与较低的匹配准确性。并使用更严格的操作，如限制对内容的访问，但不允许用户重写中具有更高版本匹配准确性的规则。
  
非常重要了解如果特定类型的敏感信息，如信用卡号码，在内容中确定的则返回仅单个可信度级别：
  
- 如果所有匹配项的单个模式，则返回该模式的置信。
    
- 如果有多个模式匹配 （即，有两个不同可信度级别的匹配项），返回的可信度级别高于任何单独的单个模式。这是复杂的一部分。例如，对于信用卡号，如果的 65%和 85%的模式匹配的置信返回的敏感信息类型是超过 90%，因为多个证据意味着更多可信度。
    
因此，如果您想要创建信用卡，一个用于 65%匹配准确性，一个用于 85%匹配准确性的两个是互斥的规则匹配准确性的范围将如下所示。第一个规则选取 65%模式的仅匹配项。**至少一个**85%匹配和**都可能具有**与其他较低可信度匹配项，第二个规则拾取相匹配。 
  
![使用的匹配准确性的不同范围的两个规则](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
出于以上原因，使用不同的匹配准确性创建规则的指南是：
  
- 最低可信度通常使用**min**和**max** （而不是范围） 相同的值。 
    
- 最高可信度通常是介于正上方较低可信度级别为 100。
    
- 任何中间可信度级别通常的范围从较低可信度到紧邻下方较高可信度级别的紧上方。
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>使用中的 DLP 策略条件相同的标签

您可以创建标签，然后：
  
- **发布**，以便最终用户可以查看和手动将标签应用于内容。 
    
- **自动应用**您选择的条件匹配其内容。 
    
有关标签的详细信息，请参阅[Overview of 标签](labels.md)。
  
创建标签后，您可以使用该标签为条件 DLP 策略中。例如，您可能需要这样做是因为：
  
- 您发布一个名为**2 私有 3 机密**，标签，以便您的组织中的人员可以手动将标签应用于机密电子邮件和文档。通过使用此标签作为 DLP 策略中的条件，您可以限制标记**2 私有 3 机密**与您的组织外部的人员共享的内容。 
    
- 您创建一个名为该名称的项目的**Alpine House**标签，然后应用该标签自动于包含关键字"Alpine House"的内容。通过使用此标签作为 DLP 策略中的条件，您可以为最终用户显示策略提示时将要与组织外部的某个人共享此内容。 
    
- 您发布一个名为**税记录**，标签，以便记录管理员可以手动将标签应用于需要归类为记录的内容。通过使用此标签作为 DLP 策略中的条件，您可以查看带结合使用与其他类型的敏感信息，如 ITINs 或 Ssn; 此标签的内容将保护操作应用于内容标记**税记录**;有关 DLP 策略的详细的活动报告获得 DLP 报告，并审核日志数据。 
    
- 发布到 Exchange 邮箱和 OneDrive 帐户的执行官一组命名**Executive 领导团队-敏感**的标签。通过使用此标签作为 DLP 策略中的条件，您可以实施保留和保护操作的同一子集的内容和用户。 
    
通过使用标签中 DLP 规则条件相同，可以您有选择地实施一组特定的内容、 位置或用户的保护操作。
  
![为条件的标签](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)
  
### <a name="how-this-feature-relates-to-other-features"></a>此功能与其他功能的方式

多个功能可以应用于包含敏感信息的内容：
  
- [应用条件自动基于标签](labels.md#applying-a-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)可以同时强制对此内容的**保留**操作。 
    
- DLP 策略可以强制实施此内容**保护**操作。和强制实施这些操作之前, 的 DLP 策略可能需要其他条件满足除了包含标签的内容。 
    
![可以将应用于敏感信息的功能的关系图](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
请注意，DLP 策略比标签或保留策略应用于敏感信息的更丰富的检测功能。DLP 策略可以强制实施内容包含敏感信息保护措施，并从内容中移除敏感信息，这些保护操作是否撤消下次内容的扫描。但如果保留策略或标签应用于包含敏感信息的内容，这是不被撤消，即使的敏感信息中删除一个一次性操作。
  
通过使用一个标签作为 DLP 策略中的条件，您可以实施保留和保护功能对与该标签的内容的操作。您可以将内容包含标签完全一样包含敏感信息的内容-标签和敏感信息类型是用于分类的内容，以便您可以强制实施操作对该内容的属性。
  
![为条件中使用标签的 DLP 策略的关系图](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>简单设置与高级设置

创建 DLP 策略时，您将简单或高级设置之间进行选择：
  
- **简单的设置**，使轻松创建无需使用规则编辑器来创建或修改规则的 DLP 策略的最常见类型。 
    
- **高级设置**使用规则编辑器使您可以完全控制您的 DLP 策略的每个设置。 
    
不要担心，隐式，简单的设置和高级的设置完全相同，通过强制执行规则组成条件和操作-仅使用简单的设置，请看不到规则编辑器。它是一种创建 DLP 策略的快捷方式。
  
### <a name="simple-settings"></a>简单的设置

到目前为止，最常见的 DLP 方案创建策略来帮助保护与可以访问内容，您的组织，以及采取自动的补救措施，如限制外部用户共享的内容包含敏感信息发送最终用户或管理员通知和审核更高版本的调查的事件。人使用 DLP 防止无意泄露敏感信息。
  
为了简化实现此目的，当您创建的 DLP 策略时，您可以选择**使用简单的设置**。这些设置提供了您需要实现的最常见的 DLP 策略，而无需进入规则编辑器的全部内容。
  
![DLP 简单和高级设置选项](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>高级设置

如果您需要创建更多的自定义的 DLP 策略，则可以选择**使用高级设置**。
  
高级的设置为您提供了规则编辑器，您可以完全控制每个可能的选项，包括实例计数和匹配准确性 （可信度） 为每个规则。
  
若要快速跳到部分，单击规则编辑器转到下面的部分的顶部导航栏中的项目。
  
![DLP 规则编辑器的顶部导航菜单](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 策略模板

创建 DLP 策略的第一步在选择要保护的信息。通过在开始使用 DLP 模板，您将保存生成一组新的规则从头开始，并找出哪些类型的信息应包含默认情况下的工作。然后可以添加或修改这些要求才能微调规则以满足您组织的特定要求。
  
预配置的 DLP 策略模板可帮助您检测特定类型的敏感信息，如 HIPAA 数据、 PCI-DSS 数据、 格雷姆-里奇-比利雷法案数据，甚至是特定于区域设置的个人身份信息 (P.I.)。若要使您方便地查找和保护常见的敏感信息类型，已包含 Office 365 中的策略模板包含需要为您要开始的最常见敏感信息类型。
  
![数据丢失防护策略模板列表，重点放在美国模板上爱国者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
您的组织可能还有自己的特定要求，这种情况下您可以从头开始创建 DLP 策略通过选择**自定义策略**选项。自定义策略为空，并且包含没有预制的规则。 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>在测试模式下逐步部署 DLP 策略

创建您的 DLP 策略时，您应考虑推出逐步评估它们的影响，并在全面执行前测试其有效性。例如，您不希望新 DLP 策略无意中阻止访问数以千计的人员才能完成其工作需要访问的文档。
  
如果您正在创建 DLP 策略的大型的潜在影响，建议遵循此序列：
  
1. **在不使用策略提示的情况下测试模式下的开始**，然后使用 DLP 报告和评估影响的所有事件都报告。DLP 报告可用于查看数量、 位置、 类型和策略的匹配项的严重性。基于结果，您可以微调规则根据需要。在测试模式下 DLP 策略不会影响您的组织中的人员的工作效率。 
    
2. **将移动到测试模式下使用通知和策略提示**，以便您可以开始教有关合规性策略的用户并做准备要应用的规则。在此阶段，您还可以要求用户，以便您可以进一步改进规则报告误报。 
    
3. **启动完全实施策略**，以便应用规则中的操作和内容的受保护。继续监视 DLP 报告任何事件报告或通知，以确保结果预想。 
    
![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
您可以在任何时候，这会影响策略中的所有规则将关闭 DLP 策略。但是，每个规则可以还关闭单独通过切换在规则编辑器中的状态。
  
![关闭策略中的规则的选项](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a>DLP 报告

创建和打开您的 DLP 策略后，您需要确认他们正在作为您的预期工作，并帮助您保持兼容。使用 DLP 报告，您可以快速查看 DLP 策略的数量和规则匹配通过时间和误报数和替代。每个报表，您可以筛选按位置，时间范围，这些匹配和甚至将其缩小到特定的策略、 规则或操作。
  
使用 DLP 报告，您可以获取业务见解并了解以下内容：
  
- 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
- 发现违反组织的合规性策略的业务流程。
    
- 了解 DLP 策略的任何业务影响。
    
此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。
  
![安全性和合规性中心中的报告仪表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 策略的工作原理

DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。
  
### <a name="policies-are-synced"></a>策略会进行同步

在安全中创建的 DLP 策略后&amp;合规性中心，它具有存储在中央策略存储区，然后同步到各种内容源，其中包括：
  
- Exchange Online，和从 web 上的 Outlook 和 Outlook 2013 存在及更高版本
    
- OneDrive for Business 站点
    
- SharePoint Online 站点
    
- Office 2016 桌面程序（Excel 2016、PowerPoint 2016 和 Word 2016）
    
策略的同步到右的位置后，启动评估内容和强制实施操作。
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>OneDrive for Business 和 SharePoint Online 站点中的策略评估

在所有 SharePoint Online 网站和 OneDrive for Business 站点，文档不断都变化 — 它们不断创建、 编辑、 共享和等。这意味着文档可以发生冲突或任何时候成为符合 DLP 策略。例如，联系人可以上载文档不包含敏感信息到其工作组网站，但更高版本，另一个人可以编辑同一文档并向其添加敏感信息。
  
为此，DLP 策略经常检查后台中是否包含与策略相符的文档。您可以将这视为异步策略评估。
  
下面是它的工作方式。人员添加或更改其网站中的文档，如搜索引擎将扫描内容，以便可以为其搜索更高版本。时出现这种情况的内容还扫描的敏感信息，并检查是否共享。找到任何敏感信息是安全存储在搜索索引中，以便仅合规性团队可以访问它，但不是典型的用户。您已打开的每个 DLP 策略在后台运行 （异步），检查经常任何相匹配的内容策略，请在搜索和应用操作，以防止无意泄漏。
  
![显示如何 DLP 策略评估内容以异步方式的图示](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。
  
DLP 计算可进行索引的任何内容。有关哪些文件类型进行爬网，默认情况下的详细信息，请参阅[默认爬网文件扩展名和分析 SharePoint Server 2013 中的文件类型](https://go.microsoft.com/fwlink/p/?LinkID=627430)。
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a>Exchange Online、 Outlook 2013 及更高版本，和 web 上的 Outlook 中的策略评估

创建包含为位置 Exchange Online 的 DLP 策略时，该策略的同步从 Office 365 安全性&amp;合规性中心到 Exchange Online，然后从 web 上的 Outlook 和 Outlook 2013 及更高版本 Exchange Online。
  
时要在 Outlook 中撰写邮件，用户可以看到策略提示，如针对 DLP 策略评估正在创建的内容。和发送一条消息后，其计算针对 DLP 策略为正常邮件流，以及 Exchange 传输规则和在 Exchange 管理中心中创建的 DLP 策略的一部分 （请参阅下一节的详细信息）。DLP 策略扫描邮件和任何附件。
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a>Office 2016 桌面程序中的策略评估

Excel 2016、 PowerPoint 2016 和 Word 2016 包括确定敏感信息并将作为 SharePoint Online 和 OneDrive for Business 应用 DLP 策略的相同功能。这些 Office 2016 程序同步直接从中央策略存储，其 DLP 策略，然后在当用户从网站中的 DLP 策略包含打开的文档处理时持续评估针对 DLP 策略的内容。
  
在 Office 2016 DLP 策略评估旨在不会影响性能的程序或内容的人员的工作效率。如果他们正在处理大型文档，或在用户计算机正忙，可能需要几秒钟的策略提示显示。
  
## <a name="permissions"></a>权限

将创建 DLP 策略的合规性团队成员需要安全权限&amp;合规性中心。默认情况下，租户管理员将具有对此位置的访问，并且可以授予安全性合规部主管及其他人访问&amp;合规性中心，但不授予所有的租户管理员权限为此，我们建议您：
  
1. 在 Office 365 中创建组并向其添加合规部主管。
    
2. 创建角色组的安全**权限**页上&amp;合规性中心。 
    
3. 将 Office 365 组添加到角色组。
    
有关详细信息，请参阅[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。
  
只有在创建和应用 DLP 策略时才需要这些权限。策略执行不需要访问此内容。
  
## <a name="find-the-dlp-cmdlets"></a>查找 DLP cmdlet

要用于安全的大部分 cmdlet&amp;合规性中心，您需要：
  
1. [连接到 Office 365 安全性&amp;合规性中心使用远程 PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用下列任一[Office 365 安全性&amp;合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
但是，DLP 报告需要拉跨 Office 365，包括 Exchange Online 中的数据。因此，DLP 报告的 cmdlet 可在 Exchange Online Powershell-不在安全&amp;合规性中心 Powershell。因此，若要使用 DLP 报告 cmdlet，您需要：
  
1. [Connect to Exchange Online using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 使用这些 cmdlet 的任何 DLP 报告：
    
  - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a>详细信息

- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
    
- [发送通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [创建 DLP 策略来保护具有 FCI 或其他属性的文档](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
    
- [敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)
    
- [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)
    
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
    
