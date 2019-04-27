---
title: 数据丢失防护策略概述
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/11/2019
ms.audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用 office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 策略, 可以在 office 365 中识别、监视和自动保护敏感信息。
ms.openlocfilehash: fedb48c20720a7eaa66cd0ea7d2184dd3dc4df55
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362050"
---
# <a name="overview-of-data-loss-prevention-policies"></a>数据丢失防护策略概述

为了符合业务标准和行业法规，组织需要保护敏感信息，防止由于疏忽而泄露。 您可能想要防止泄漏到组织外部的敏感信息的示例包括财务数据或个人身份信息 (PII)，如信用卡号、社会保险号或健康记录。 使用 office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 策略, 可以在 office 365 中识别、监视和自动保护敏感信息。
  
您可以使用 DLP 策略实现以下功能：
  
- **在许多位置 (如 Exchange online、SharePoint online、OneDrive for business 和 Microsoft 团队) 标识敏感信息。**
    
    例如, 您可以标识任何包含存储在任何 OneDrive for business 网站中的信用卡号的文档, 也可以仅监视特定人员的 onedrive 站点。
    
- **防止意外共享敏感信息**。 
    
    例如, 您可以标识任何包含与组织外部人员共享的运行状况记录的文档或电子邮件, 然后自动阻止对该文档的访问或阻止发送该电子邮件。
    
- **监视和保护桌面版本的 Excel、PowerPoint 和 Word 中的敏感信息。**
    
    就像在 Exchange online、SharePoint online 和 OneDrive for business 中一样, 这些 Office 桌面程序都包含用于识别敏感信息和应用 DLP 策略的相同功能。 当用户共享这些 Office 程序中的内容时, DLP 提供连续监控。
    
- **帮助用户了解如何保持兼容性，同时不会中断工作流。**
    
    您可以向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。 例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。 outlook 网页、outlook、Excel、PowerPoint 和 Word 中也会显示相同的策略提示。
    
- **查看显示与组织的 DLP 策略匹配的内容的 DLP 报告。**
    
    要评估您的组织遵守 DLP 策略的情况，您可以查看随着时间推移符合每个策略和每条规则的次数。 如果 DLP 策略允许用户覆盖策略提示并报告误报, 则还可以查看用户报告的内容。
    
您可以在 Office 365 安全&amp;合规中心中的 "数据丢失防护" 页上创建和管理 DLP 策略。
  
![Office 365 安全&amp;合规中心中的 "数据丢失防护" 页](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>DLP 策略包含的内容

DLP 策略包含以下基本内容：
  
- 在何处保护内容:**位置**(如 Exchange Online、SharePoint online 和 OneDrive for business 网站), 以及 Microsoft 团队聊天和频道。 
    
- 何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容： 
    
  - 在强制执行规则之前内容必须匹配的**条件**。 例如, 规则可能配置为仅查找包含与您的组织外部人员共享的社会安全号码的内容。 
    
  - 当找到与条件匹配的内容时, 您希望规则自动执行的**操作**。 例如, 可以将规则配置为阻止对文档的访问, 并同时向用户和合规性监察官发送电子邮件通知。 
    
您可以使用规则来满足特定的保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如要符合特定法规所需的所有规则。
  
例如，DLP 策略可能会帮助您检测是否存在受 Health Insurance Portability and Accountability Act (HIPAA) 约束的信息。 此 DLP 策略可以通过查找包含与组织外部人员共享的这些敏感信息的任何文档来帮助保护所有 SharePoint Online 网站和所有 OneDrive for business 网站 (在 where) 上的 HIPAA 数据 (这些内容)。条件), 然后阻止对文档的访问和发送通知 (操作)。 这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。
  
![图表显示了 DLP 策略包含位置和规则](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>位置

DLP 策略可以跨 Office 365 查找和保护敏感信息, 无论这些信息位于 Exchange online、SharePoint online、OneDrive for business 中还是 Microsoft 团队中。 您可以选择保护 Exchange 电子邮件、Microsoft 团队聊天和频道、所有 SharePoint 或 OneDrive 库中的内容, 或选择策略的特定位置。
  
![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
请注意, 如果选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户, DLP 策略不能包含100以上的包含和排除项。 尽管此限制存在, 但请通过应用组织范围的策略或适用于整个位置的策略, 了解您可以超过此限制。
  
### <a name="rules"></a>Rules

规则是在组织内容中实施业务需求的。 策略包含一条或多条规则，每条规则由多个条件和操作组成。 对于每条规则，只要满足了条件，就会自动执行操作。 规则是按顺序执行的, 从每个策略中的最高优先级规则开始。
  
规则还提供通知用户 (带有策略提示和电子邮件通知) 和管理员 (电子邮件事件报告) 内容与规则匹配的选项。
  
以下是规则的组件, 如下所述。
  
![DLP 规则编辑器的各个部分](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>条件

条件非常重要, 因为它们决定了要查找的信息类型以及何时执行操作。 例如, 您可以选择忽略包含护照号码的内容, 除非内容包含10个以上的号码, 并且与组织外部的人员共享。
  
条件侧重于**内容**, 如要查找的敏感信息类型以及**上下文**(例如, 与谁共享文档的用户)。 您可以使用条件将不同的操作分配给不同的风险级别, 例如, 内部共享的敏感内容可能会降低风险, 并且需要的操作比与组织外部人员共享的敏感内容更少。 
  
![显示可用的 DLP 条件的列表](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
现在的可用条件可以确定以下内容：
  
- 内容包含一种敏感信息。
    
- 内容包含标签。 有关详细信息, 请参阅下一节在[DLP 策略中使用标签作为条件](#using-a-label-as-a-condition-in-a-dlp-policy)。
    
- 内容是与您组织的外部还是内部人员共享。
    
#### <a name="types-of-sensitive-information"></a>敏感信息类型

DLP 策略可帮助保护定义为**敏感信息类型**的敏感信息。 Office 365 包含对多个不同地区供您使用的众多常见敏感信息类型的定义，例如信用卡号、银行账号、国民身份证号及护照号等。 
  
![可用敏感信息类型列表](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
当 DLP 策略查找敏感信息类型 (如信用卡号) 时, 它并不只是查找16位的数字。 通过以下组合对每种敏感信息类型进行定义和检测：
  
- 关键字
    
- 用于验证校验和或撰写的内部函数
    
- 用于查找模式匹配的正则表达式评估
    
- 其他内容检查
    
这有助于 DLP 检测实现高度准确性, 同时减少可能中断工作的误报数。
  
#### <a name="actions"></a>Actions

当内容与规则中的条件相匹配时, 您可以将操作应用于自动保护内容。
  
![可用 DLP 操作列表](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
现在可以使用操作, 可以执行以下操作:
  
- **限制对内容的访问**对于 "网站内容", 这意味着对文档的权限仅限于主网站集管理员、文档所有者和上次修改文档的人员之外的所有用户。 这些用户可以从文档中删除敏感信息或执行其他补救操作。 如果文档符合规则，则会自动恢复原始权限。 当对文档的访问受到阻止时，文档将在网站的库中显示一个特殊的策略提示图标。 
    
    ![显示文档访问被拦截的策略提示](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    对于电子邮件内容, 此操作阻止发送邮件。 根据配置 DLP 规则的方式, 发件人将看到一个 NDR 或 (如果该规则使用通知) 策略提示和/或电子邮件通知。
    
    ![警告: 必须从邮件中删除未经授权的收件人](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>用户通知和用户替代

您可以使用通知和替代来向用户介绍 DLP 策略, 并帮助他们保持合规性, 而不阻止其工作。 例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。
  
![DLP 规则编辑器的用户通知和用户替代部分](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
电子邮件可通知发送、共享或上次修改内容的人员, 以及网站内容、网站内容、主网站集管理员和文档所有者。 此外, 还可以在电子邮件通知中添加或删除您选择的人。
  
除了发送电子邮件通知之外, 用户通知还会显示策略提示:
  
- 在 outlook 和 web 上的 outlook 中。
    
- 对于 SharePoint Online 或 OneDrive for business 网站上的文档。
    
- 在 Excel、PowerPoint 和 Word 中, 当文档存储在包含在 DLP 策略中的网站上时。
    
电子邮件通知和策略提示说明了内容与 DLP 策略冲突的原因。 如果您选择，电子邮件通知和策略提示可以允许用户通过报告误报或提供业务理由来替代规则。 这可以帮助您让用户了解您的 DLP 策略和强制执行它们，而不会阻止用户完成其工作。 有关替代和误报的信息还记录报告（请参阅下文提供的 DLP 报告）并且包含在事件报告（下一节）中，以便合规部主管可以定期查看此信息。
  
以下是策略提示在 OneDrive for business 帐户中的外观。
  
![OneDrive 帐户中文档的策略提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>事件报告

匹配规则时, 可以使用事件详细信息向合规专员 (或任何人选择的任何人) 发送事件报告。 此报告包含有关匹配项目、与规则匹配的实际内容以及上次修改内容的人员的姓名的信息。 对于电子邮件, 该报告还包括与 DLP 策略匹配的原始邮件的附件。
  
![用于配置事件报告的页面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>分组和逻辑运算符

您的 DLP 策略通常具有一个简单的要求, 例如, 标识所有包含美国社会保险号码的内容。 但是, 在其他情况下, 您的 DLP 策略可能需要标识更松散定义的数据。
  
例如, 若要确定符合美国卫生保险业法案 (HIPAA) 的内容, 您需要查找以下内容:
  
- 包含特定类型的敏感信息的内容, 如美国社会保险号或药品强制代理 (DEA) 号码。
    
    AND
    
- 较难识别的内容, 如有关患者护理的通信或提供的医疗服务说明。 标识此内容需要匹配非常大的关键字列表中的匹配关键字, 如 Diseases 的国际分类 (ICD-9-cm 或 icd-10 厘米)。
    
您可以通过使用分组和逻辑运算符 (and 和 OR) 轻松地识别这些松散定义的数据。 创建 DLP 策略时, 可以执行以下操作:
  
- 对敏感信息类型进行分组。
    
- 选择组中的敏感信息类型与组本身之间的逻辑运算符。
    
### <a name="choosing-the-operator-within-a-group"></a>在组中选择运算符

在组中, 可以选择是否必须满足该组中的任何或所有条件, 才能匹配该规则的内容。
  
![显示组中的运算符的组](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>添加组

您可以快速添加组, 该组将其自己的条件和运算符放在该组中。
  
!["添加组" 按钮](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>在组之间选择运算符

在组之间, 可以选择仅一个组中的条件, 还是必须满足所有组中的条件, 以匹配该规则的内容。
  
例如, 内置的**美国 HIPAA**策略有一条规则, 该规则在组之间使用**AND**运算符, 以便识别包含以下内容的内容: 
  
- 来自组**PII 标识符**(至少一个 SSN 号码**或**DEA 号码) 
    
    **AND**
    
- 来自 group**医学条款**(至少有一个 ICD-9 cm 关键字**或**ICD-10 cm 关键字) 
    
![显示组之间的运算符的组](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>处理规则的优先级

当您在策略中创建规则时, 每个规则都会按其创建顺序分配一个优先级, 即最初创建的规则具有第一个优先级, 创建的规则第二个优先级为第二个, 依此类推。 
  
![优先级顺序中的规则](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
设置多个 DLP 策略后, 可以更改一个或多个策略的优先级。 若要执行此操作, 请选择策略, 选择 "**编辑策略**", 并使用 "**优先级**" 列表来指定其优先级。

![设置策略的优先级](media/dlp-set-policy-priority.png)

按照规则对内容进行评估时, 将按优先级顺序处理规则。 如果内容与多个规则匹配, 将按优先级顺序处理规则, 并强制执行限制性最强的操作。 例如, 如果内容与以下所有规则相匹配, 则强制执行规则 3, 因为它的优先级最高, 最受限制的规则如下:
  
- 规则 1: 仅通知用户
    
- 规则 2: 通知用户、限制访问并允许用户重写
    
- 规则 3: 通知用户、限制访问和不允许用户替代
    
- 规则 4: 仅通知用户
    
- 规则 5: 限制访问
    
- 规则 6: 通知用户、限制访问和不允许用户替代
    
在此示例中, 请注意, 所有规则的匹配项都记录在审核日志中, 并显示在 DLP 报告中, 即使仅强制实施最严格的规则也是如此。
  
对于策略提示, 请注意:
  
- 仅来自最高优先级的策略提示将显示最受限制的规则。 例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。 这会让用户看不到策略提示的级联方式。
    
- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>调整规则以使其更易于或更难匹配

在用户创建并打开其 DLP 策略后, 它们有时会遇到以下问题:
  
- 太多**不**敏感的内容信息与规则相匹配, 也就是说, 误报过多。 
    
- 与规则匹配的**** 内容太少, 敏感信息太少。 换句话说, 保护性操作不会对敏感信息强制实施。 
    
若要解决这些问题, 您可以调整实例数和匹配精度以使内容更难或更轻松地与规则相匹配, 从而调整规则。 规则中使用的每种敏感信息类型都具有实例计数和匹配精度。
  
### <a name="instance-count"></a>实例计数

"实例计数" 表示内容必须有多少个特定类型的敏感信息, 才能匹配该规则。 例如, 如果在1和9唯一的美国或英国之间, 则内容将与下面显示的规则匹配 识别护照号码。
  
请注意, 实例计数只包含敏感信息类型和关键字的**唯一**匹配项。 例如, 如果电子邮件包含10个相同信用卡号码, 则这些10个事件将计为一个信用卡号码的单个实例。 
  
若要使用实例计数来调整规则, 本指南非常简单:
  
- 若要使规则更易于匹配, 请减小**最小**计数和/或增加**最大**计数。 您还可以通过删除数值将**max**设置为**any** 。 
    
- 若要使规则更难匹配, 请增加**最小**计数。 
    
通常情况下, 在具有较低实例计数的规则 (例如, 1-9) 中使用限制性更少的操作 (如发送用户通知)。 并且, 在具有更高实例计数的规则 (例如, 10-any) 中使用限制性更强的操作, 例如限制对内容的访问而不允许用户覆盖。
  
![规则编辑器中的实例计数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>匹配精确性

如上文所述, 使用不同类型的证据定义和检测敏感信息类型。 通常, 敏感信息类型由多个此类组合 (称为 "模式") 定义。 需要较少证据的模式具有较低的匹配精度 (或置信度级别), 而需要更多证据的模式具有更高的匹配精度 (或置信度级别)。 若要了解有关每种敏感信息类型使用的实际模式和可信度级别的详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。
  
例如, 名为 "信用卡号码" 的敏感信息类型由两种模式定义:
  
- 具有 65% 可信度的模式, 需要满足以下条件:
    
  - 信用卡号码格式的数字。
    
  - 传递校验和的数字。
    
- 具有 85% 可信度的模式, 需要满足以下条件:
    
  - 信用卡号码格式的数字。
    
  - 传递校验和的数字。
    
  - 使用正确的格式的关键字或过期日期。
    
您可以在规则中使用这些可信度级别 (或 "匹配精度")。 通常情况下, 在匹配精度较低的规则中使用限制性更少的操作 (如发送用户通知)。 您可以使用限制性更强的操作 (如在不允许用户替代的情况下限制对内容的访问), 在具有更高的匹配精确性的规则中。
  
请务必了解, 如果内容中标识了特定类型的敏感信息 (如信用卡号), 则仅返回一个置信度:
  
- 如果所有匹配项都针对单个模式, 则返回该模式的置信度级别。
    
- 如果有多个模式的匹配项 (即, 有两个不同的可信度级别的匹配项), 则将返回比单独任意单个模式更高的可信度级别。 这是一个棘手的部分。 例如, 对于信用卡, 如果 65% 和 85% 两个模式都匹配, 则为该敏感信息类型返回的置信度级别将大于 90%, 因为更多的证据意味着更自信。
    
因此, 如果要为信用卡创建两个相互排斥的规则, 一个是 65% 匹配精度, 另一个为 85% 匹配精度, 则匹配精度的范围将如下所示。 第一条规则仅选取 65% 模式的匹配项。 第二个规则将选取与**至少一个**85% 匹配的匹配项, 并且**可能会有**其他较低可信度的匹配项。 
  
![具有不同范围的两个规则匹配精确性](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
出于这些原因, 使用不同的匹配精度创建规则的指南如下:
  
- 最低置信度通常对**min**和**max** (不是区域) 使用相同的值。 
    
- 最高置信度通常是从较低置信度到100的范围。
    
- 任何置信度级别通常都介于较低置信度级别的正上方和低于较高置信度的下方。
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>在 DLP 策略中使用标签作为条件

您可以创建一个标签, 然后执行以下操作:
  
- **发布**, 以便最终用户可以查看和手动将标签应用于内容。 
    
- **自动将其应用**于与您选择的条件相匹配的内容。 
    
有关标签的详细信息, 请参阅[保留标签概述](labels.md)。
  
创建标签后, 可以将该标签用作 DLP 策略中的条件。 例如, 您可能希望执行此操作, 因为:
  
- 您发布了一个名为 "**机密**" 的标签, 以便组织中的人员可以手动将该标签应用于机密电子邮件和文档。 通过将此标签用作 DLP 策略中的条件, 可以将标记为 "**机密**" 的内容限制为与组织外部的人员共享。 
    
- 您为该名称的项目创建了一个名为**Alpine 房子**的标签, 然后将该标签自动应用于包含关键字 "Alpine 房子" 的内容。 通过将此标签用作 DLP 策略中的条件, 可以在即将与组织外部的人员共享此内容时向最终用户显示策略提示。 
    
- 您发布了一个名为 "**税收 record**" 的标签, 以便您的记录管理员可以手动将该标签应用于需要分类为记录的内容。 通过将此标签用作 DLP 策略中的条件, 可以使用此标签以及其他类型的敏感信息 (如 ITINs 或 ssn) 查找内容。将保护操作应用于标记为 "**税收记录**" 的内容;并从 dlp 报告和审核日志数据中获取有关 dlp 策略的详细活动报告。 
    
- 您发布了一个名为**Executive 领导团队**的标签-对一组主管的 Exchange 邮箱和 OneDrive 帐户敏感。 通过将此标签用作 DLP 策略中的条件, 可以同时对同一子集的内容和用户实施保留和保护操作。 
    
通过将标签用作 DLP 规则中的条件, 可以有选择地对一组特定的内容、位置或用户强制实施保护操作。
  
![标签作为条件](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a>对敏感度标签的支持即将推出

请注意, 当前可以仅将保留标签用作条件, 不能使用[敏感度标签](sensitivity-labels.md)。 目前, 我们正在为在此条件中使用灵敏度标签提供支持。
  
### <a name="how-this-feature-relates-to-other-features"></a>此功能与其他功能的关联方式

可将多个功能应用于包含敏感信息的内容:
  
- [保留标签](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)均可对此内容强制执行**保留**操作。 
    
- DLP 策略可以对此内容强制实施**保护**操作。 在强制执行这些操作之前, DLP 策略可能需要满足其他条件, 除了包含标签的内容。 
    
![可应用于敏感信息的功能的关系图](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
请注意, DLP 策略具有更丰富的检测功能, 而不是应用于敏感信息的标签或保留策略。 DLP 策略可以对包含敏感信息的内容强制执行保护操作, 如果从内容中删除了敏感信息, 则下次扫描内容时将撤消这些保护操作。 但是, 如果保留策略或标签应用于包含敏感信息的内容, 则即使删除了敏感信息, 也不会撤消此一次性操作。
  
通过将标签用作 DLP 策略中的条件, 可以使用该标签对内容强制执行保留和保护操作。 您可以考虑包含标签的内容与包含敏感信息的内容完全一样-标签和敏感信息类型都是用于对内容进行分类的属性, 以便您可以对该内容强制执行操作。
  
![使用 label 作为条件的 DLP 策略关系图](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>简单设置与高级设置

当您创建 DLP 策略时, 您将在简单或高级设置之间进行选择:
  
- **简单设置**使您可以轻松地创建最常用类型的 DLP 策略, 而无需使用规则编辑器来创建或修改规则。 
    
- **高级设置**使用规则编辑器为您提供对 DLP 策略的每个设置的完全控制。 
    
无需担心, "简单设置" 和 "高级" 设置的工作方式完全相同, 只是通过使用简单设置来强制执行包含条件和操作的规则, 而不会看到 "规则编辑器"。 这是创建 DLP 策略的快速方法。
  
### <a name="simple-settings"></a>简单设置

到目前为止, 最常见的 DLP 方案是创建一个策略, 以帮助保护包含敏感信息的内容与组织外部的人员共享, 并采取自动补救措施, 如限制谁可以访问内容,发送最终用户或管理员通知, 并审核事件以供日后调查。 用户使用 DLP 有助于防止无意中泄露敏感信息。
  
若要简化实现此目标的目的, 在创建 DLP 策略时, 可以选择 "**使用简单设置**"。 这些设置提供了实现最常用 DLP 策略所需的一切, 而无需进入规则编辑器。
  
![适用于简单和高级设置的 DLP 选项](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>高级设置

如果您需要创建更多自定义的 DLP 策略, 则可以选择 "**使用高级设置**"。
  
高级设置向您提供规则编辑器, 在其中可以完全控制每个可能的选项, 包括每个规则的实例计数和匹配精度 (置信度级别)。
  
若要快速跳转到某一节, 请单击规则编辑器顶部导航中的某个项目, 以转到下面的部分。
  
![DLP 规则编辑器的顶部导航菜单](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 策略模板

创建 DLP 策略的第一步是选择要保护的信息。 通过从 DLP 模板开始, 可以保存从头开始创建一组新的规则的工作, 并在默认情况下, 找出应包含哪些类型的信息。 然后, 您可以添加或修改这些要求, 以微调规则以满足组织的特定要求。
  
预配置的 DLP 策略模板可帮助您检测特定类型的敏感信息, 如 HIPAA 数据、PCI-DSS 数据、格雷姆-比利雷 Act 数据, 甚至是特定于区域设置的个人身份信息 (P.I.)。 要使您能够轻松地查找和保护常见类型的敏感信息，包含在 Office 365 中的策略模板已包含您要开始构建策略所需的最常见的敏感信息类型。
  
![数据丢失防护策略模板列表，重点放在美国模板上爱国者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
您的组织可能还具有自己的特定要求, 在这种情况下, 您可以通过选择 "**自定义策略**" 选项从头开始创建 DLP 策略。 自定义策略为空且不包含任何 premade 规则。 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>在测试模式下逐步部署 DLP 策略

创建 DLP 策略时，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。 例如, 您不希望新的 DLP 策略无意中阻止用户需要访问的数千个文档的访问权限, 以便完成其工作。
  
如果您创建的 DLP 策略具有很大的潜在影响, 我们建议按照以下顺序进行操作:
  
1. **在测试模式下启动 (不带策略提示**), 然后使用 DLP 报告和任何事件报告来评估影响。 您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。 根据结果，您可以在需要时微调规则。 在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。 
    
2. **移动到使用通知和策略提示的测试模式**，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。 
    
3. **对策略启动完全强制**, 以便应用规则中的操作和内容受保护。 继续监视 DLP 报告及任何事件报告或通知，确保结果是您所期望的。 
    
![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
您可以随时禁用 DLP 策略，这会影响策略中的所有规则。 但是, 也可以通过在规则编辑器中切换每条规则的状态来单独关闭这些规则。
  
![关闭策略中的规则的选项](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

您还可以更改策略中的多个规则的优先级。 若要执行此操作, 请打开策略以进行编辑。 在某个规则的行中, 选择省略号 (**...**), 然后选择一个选项, 如 "下移" 或 " **** **置于最后**"。

![设置规则优先级](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a>DLP 报告

创建并打开 DLP 策略后, 您需要验证它们是否按预期工作, 并帮助您保持合规性。 使用 DLP 报告，您可以快速查看随着时间的推移 DLP 策略和规则匹配的次数，以及误报和替代数。 对于每个报告，您都可以按位置、时间范围，甚至缩小为特定的策略、规则或操作来筛选这些匹配项。
  
使用 DLP 报告，您可以获取业务见解并了解以下内容：
  
- 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
- 发现违反组织的合规性策略的业务流程。
    
- 了解 DLP 策略的任何业务影响。
    
此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。
  
![安全与合规中心中的报告仪表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 策略的工作原理

DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。
  
### <a name="policies-are-synced"></a>策略会进行同步

在安全&amp;合规中心中创建 DLP 策略后, 它将存储在一个中央策略存储中, 然后同步到各种内容源, 其中包括:
  
- Exchange Online, 并从 web 上的 outlook 和 outlook 打开
    
- OneDrive for Business 站点
    
- SharePoint Online 站点
    
- Office 桌面程序 (Excel、PowerPoint 和 Word)

- Microsoft Teams 频道和聊天
    
在将该策略同步到正确的位置之后, 它将开始评估内容并强制执行操作。
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>OneDrive for Business 和 SharePoint Online 站点中的策略评估

在所有 SharePoint Online 网站和 OneDrive for business 网站中, 文档会不断变化, 它们将不断地被创建、编辑、共享, 等等。 这意味着文档可能随时会与 DLP 策略发生冲突，或变为合规状态。 例如，一个用户上载的文档可能不包含与团队站点相关的敏感信息，但之后，另一个用户可能会编辑同一文档，并向文档添加敏感信息。
  
为此，DLP 策略经常检查后台中是否包含与策略相符的文档。 您可以将这视为异步策略评估。
  
#### <a name="how-it-works"></a>运作方式
 
当用户在其网站中添加或更改文档时, 搜索引擎会对内容进行扫描, 以便以后可以对其进行搜索。 在这种情况下, 还会对内容进行扫描以查找敏感信息, 并检查是否已共享。 找到的任何敏感信息都将安全存储在搜索索引中, 以便只有合规性团队可以访问它, 而不是典型用户。 您已启用的每个 DLP 策略都将在后台运行 (异步), 检查与策略匹配的任何内容的搜索频率, 并应用操作以防止意外泄漏。
  
![显示 DLP 策略异步评估内容方式的关系图](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。
  
DLP 评估可编制索引的任何内容。 有关默认情况下进行爬网的文件类型的详细信息, 请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange Online、outlook 和 outlook 网页版中的策略评估

在创建包含 Exchange online 作为位置的 DLP 策略时, 该策略将从 Office 365 安全&amp;合规中心同步到 Exchange online, 然后从 exchange online 同步到 web 上的 outlook 和 outlook。
  
在 Outlook 中撰写邮件时, 如果要创建的内容是根据 DLP 策略进行评估, 则用户可以查看策略提示。 在邮件发送之后, 它将根据 DLP 策略进行评估, 作为邮件流的正常部分, 以及 exchange 邮件流规则 (也称为传输规则) 和在 exchange 管理中心中创建的 DLP 策略。 DLP 策略同时扫描邮件和所有附件。
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 桌面程序中的策略评估

Excel、PowerPoint 和 Word 包含标识敏感信息的相同功能, 并将 DLP 策略应用为 SharePoint Online 和 OneDrive for business。 这些 Office 程序直接从中央策略存储同步其 DLP 策略, 然后在用户处理从包含在 DLP 策略中的网站中打开的文档时, 将继续评估 dlp 策略的内容。
  
Office 中的 DLP 策略评估设计不会影响程序的性能或对内容进行处理的人员的工作效率。 如果他们正在处理大型文档, 或者用户的计算机忙, 可能需要几秒钟的时间才能显示策略提示。

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft 团队中的策略评估
 
在创建包含 Microsoft 团队作为位置的 DLP 策略时, 该策略将从 Office 365 安全&amp;合规中心同步到用户帐户以及 Microsoft 团队频道和聊天。 当有人尝试在 Microsoft 团队聊天或频道中共享敏感信息时, 可能会阻止或取消邮件, 具体取决于配置 DLP 策略的方式。 而且, 包含敏感信息且与来宾共享的文档 (外部用户) 将不会为这些用户打开。 若要了解详细信息, 请参阅[数据丢失防护和 Microsoft 团队](dlp-microsoft-teams.md)。
 
## <a name="permissions"></a>权限

要创建 DLP 策略的合规性团队的成员需要安全&amp;合规中心的权限。 默认情况下, 你的租户管理员将有权访问此位置, 并且可以向合规专员和其他人授予&amp;对安全合规中心的访问权限, 而无需为其授予租户管理员的所有权限。为此, 我们建议您执行以下操作:
  
1. 在 Office 365 中创建组并向其添加合规部主管。
    
2. 在安全&amp;合规性中心的 "**权限**" 页上创建角色组。 
    
3. 将 Office 365 组添加到角色组。
    
有关详细信息，请参阅[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。
  
只有在创建和应用 DLP 策略时才需要这些权限。 策略执行不需要访问此内容。
  
## <a name="find-the-dlp-cmdlets"></a>查找 DLP cmdlet

若要将大多数 cmdlet 用于安全&amp;合规性中心, 您需要执行以下操作:
  
1. [使用远程 PowerShell 连接到 Office 365 安全与合规中心](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. 使用任何[符合策略和合规性的 dlp cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)
    
但是, DLP 报告需要跨 Office 365 请求获取数据, 包括 Exchange Online。 出于此原因, 在**Exchange Online powershell 中提供了 DLP 报告的 cmdlet--不在安全&amp;合规中心 powershell**中。 因此, 若要使用 DLP 报告的 cmdlet, 需要执行以下操作:
  
1. [Connect to Exchange Online using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. 为 DLP 报告使用以下任一 cmdlet:
    
  - [get-dlpdetectionsreport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [get-dlpdetailreport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a>更多信息

- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
    
- [发送通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [创建 DLP 策略来保护具有 FCI 或其他属性的文档](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
    
- [敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)
    
- [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)
    
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
    

