---
title: 数据丢失防护概述
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 通过安全 &amp; 合规中心的数据丢失防护 (DLP) 策略，可在 Office 365 内识别、监视和自动保护敏感数据。
ms.openlocfilehash: 1f82af2c61138fd33f849a5cb13fcee1259cafd7
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230766"
---
# <a name="overview-of-data-loss-prevention"></a>数据丢失防护概述

> [!NOTE]
> 对于具有 Office 365 高级合规版许可证的用户，最近为 Microsoft Teams 聊天和频道消息添加了数据丢失防护功能。它是一种独立选项，包含在 Office 365 E5 和 Microsoft 365 E5 合规版中。 若要了解有关许可要求的详细信息，请参阅 [Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。

为了符合业务标准和行业法规，组织必须保护敏感信息，防止由于疏忽而泄露。 敏感信息包括财务数据或个人身份信息 (PII)，如信用卡号、社会保险号或健康记录。 通过 Office 365 安全 &amp; 合规中心的数据丢失防护 (DLP) 策略，可在 Office 365 内识别、监视和自动保护敏感数据。
  
你可以使用 DLP 策略实现以下功能：
  
- **跨 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 等多个位置标识敏感信息。**
    
    例如，可以识别存储在任何 OneDrive for Business 站点中的包含信用卡号的任何文档，也可以仅监视特定人员的 OneDrive 站点。
    
- **防止意外共享敏感信息**。 
    
    例如，可识别出与组织外人员共享的文档或电子邮件是否包含医疗记录，然后自动阻止对该文档的访问或阻止发送该电子邮件。
    
- **监视和保护 Excel、PowerPoint 和 Word 桌面版中的敏感信息。**
    
    就像在 Exchange Online、SharePoint Online 和 OneDrive for Business 中一样，这些 Office 桌面程序都包含相同的功能以识别敏感信息和应用 DLP 策略。 当用户在这些 Office 程序中共享内容时，DLP 进行持续监视。
    
- **帮助用户了解如何保持兼容性，同时不会中断工作流。**
    
    您可以向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。 例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。 Outlook 网页版、Outlook、Excel、PowerPoint 和 Word 中显示了相同的策略提示。
    
- **查看 DLP 报告，了解符合组织的 DLP 策略的内容。**
    
    要评估组织遵守 DLP 策略的情况，可查看每个策略和每条规则拥有的匹配数随时间变化的情况。 如果 DLP 策略允许用户覆盖策略提示和发出误报，则还可查看用户报告的内容。
    
你可在 Office 365 安全 &amp; 合规中心的“数据丢失防护”页上创建和管理 DLP 策略。
  
![Office 365 安全 &amp; 合规中心的数据丢失防护页](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a>DLP 策略包含的内容

DLP 策略包含以下基本内容：
  
- 在何处保护内容：Exchange Online、SharePoint Online 和 OneDrive for Business 网站等**位置**，还包括 Microsoft Teams 聊天和频道消息。 
    
- 何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容： 
    
  - 在强制执行规则之前内容必须满足的**条件**。 例如，可将规则配置为只查找包含与组织外部人员共享的社会保险号的内容。 
    
  - 找到满足条件的内容时你希望规则自动执行的**操作**。 例如，可将规则配置为阻止访问文档，以及向用户和合规部主管发送电子邮件通知。 
    
可使用规则来满足特定保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如符合特定规则所需的所有规则。
  
例如，DLP 策略可能会帮助您检测是否存在受健康保险可携性与责任法案 (HIPAA) 约束的信息。 此 DLP 策略可以通过查找与你的组织外部人员共享的包含此敏感信息（条件）的任何文档，来帮助保护所有 SharePoint Online 站点和所有 OneDrive for Business 站点（位置）的 HIPAA 数据（对象），然后阻止对该文档的访问并发送通知（操作）。 这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。
  
![图表显示了 DLP 策略包含位置和规则](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a>位置

无论信息位于 Exchange Online、SharePoint Online、OneDrive for Business 还是 Microsoft Teams 中，DLP 策略均可查找和保护 Office 365 中的敏感信息。 你可以选择保护 Exchange 电子邮件、Microsoft Teams 聊天和频道消息以及所有 SharePoint 或 OneDrive 库中的内容，或为策略选择特定位置。
  
![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
如果你选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户，则 DLP 策略可包含不超过 100 个此类包含和排除项。 尽管存在此限制，你可应用组织范围策略或位置整体策略来超出此限制。
  
### <a name="rules"></a>规则

规则用于对组织的内容强制执行业务要求。 策略包含一条或多条规则，每条规则由多个条件和操作组成。 对于每条规则，只要满足了条件，就会自动执行操作。 规则按顺序执行，从每个策略中优先级最高的规则开始。
  
规则还提供一些选项，用于通知用户（使用策略提示和电子邮件通知）和管理员（使用电子邮件事件报告）内容与规则相匹配。
  
以下是规则的各组成部分，并提供了相应说明。
  
![DLP 规则编辑器的各部分](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>条件

条件非常重要，因为它们确定要查找的信息类型以及执行操作的时间。 例如，你可能会选择忽略包含护照号的内容，除非内容包含 10 个以上此类数字并与组织外部的人员进行了共享。
  
条件侧重于**内容**，例如要查找的敏感信息类型，还侧重于**上下文**，例如共享文档的人员。 你可以使用条件向不同的风险级别分配不同操作。 例如，相较与组织外部人员共享的敏感信息，可在内部共享的敏感内容的风险更低、需要执行的操作更少。 
  
![显示可用的 DLP 条件的列表](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
现在的可用条件可以确定以下内容：
  
- 包含某种敏感信息的内容。
    
- 包含标签的内容。 有关详细信息，请参阅下方的[在 DLP 策略中使用标签作为条件](#using-a-label-as-a-condition-in-a-dlp-policy)部分。
    
- 内容是与贵组织的外部还是内部人员共享。
    
#### <a name="types-of-sensitive-information"></a>敏感信息类型

DLP 策略可帮助保护定义为**敏感信息类型**的敏感信息。 Office 365 包含对多个不同地区供您使用的众多常见敏感信息类型的定义，例如信用卡号、银行账号、国民身份证号及护照号等。 
  
![可用敏感信息类型列表](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
当 DLP 策略查找信用卡号之类的敏感信息类型时，它不只是在查找 16 位数字。 通过以下组合对每种敏感信息类型进行定义和检测：
  
- 关键字
    
- 用于验证校验和或撰写的内部函数
    
- 用于查找模式匹配的正则表达式评估
    
- 其他内容检查
    
这将有助于实现高度准确的 DLP 检测，同时减少导致用户工作中断的误报数。
  
#### <a name="actions"></a>操作

当内容与规则中的条件匹配时，可应用操作以自动保护内容。
  
![可用 DLP 操作列表](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
借助可用操作，能够：
  
- **限制对内容的访问** 对于网站内容，这就意味着，除主要网站集管理员、文档所有者和上次修改文档的人员外，所有人访问该文档均受限。 这些用户可从文档中删除敏感信息或执行其他补救操作。 如果文档符合规则，则会自动恢复原始权限。 访问文档受阻时，文档将在网站的库中显示一个特殊策略提示图标。 
    
    ![显示文档访问被拦截的策略提示](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    对于电子邮件内容，此操作阻止发送该邮件。 根据 DLP 规则的配置方式，发件人将看到 NDR 或（如果规则使用通知）策略提示和/或电子邮件通知。
    
    ![警告：必须从邮件中删除未经授权的收件人](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>用户通知和用户覆盖

你可以使用通知和覆盖向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。 例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。
  
![DLP 规则编辑器的用户通知和用户覆盖部分](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
电子邮件可向发送、共享或最后修改内容的人员发送通知，对于网站内容，则可通知主要网站集管理员和文档所有者。 此外，还可向电子邮件通知中添加人员或删除所选人员。
  
除发送电子邮件通知外，用户通知还会显示一条策略提示：
  
- 在 Outlook 和 Outlook 网页版中。
    
- 对于 SharePoint Online 或 OneDrive for Business 网站上的文档。
    
- 在 Excel、PowerPoint 和 Word 中（如果文档存储在 DLP 策略中包含的网站上）。
    
电子邮件通知和策略提示解释内容与 DLP 策略相冲突的原因。 如果您选择，电子邮件通知和策略提示可以允许用户通过报告误报或提供业务理由来替代规则。 这可以帮助您让用户了解您的 DLP 策略和强制执行它们，而不会阻止用户完成其工作。 有关替代和误报的信息还记录报告（请参阅下文提供的 DLP 报告）并且包含在事件报告（下一节）中，以便合规部主管可以定期查看此信息。
  
以下是 OneDrive for Business 帐户中的策略提示。
  
![针对 OneDrive 帐户中文档的策略提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a>事件报告

当项目与规则相匹配时，可向合规负责人（或所选的任何人员）发送包含事件详情的事件报告。 此报告中的信息包括，匹配的项目的信息、与规则匹配的实际内容以及上次修改内容的人员的姓名。 对于电子邮件，报告还将与 DLP 策略匹配的原始邮件包含为附件。
  
![用于配置事件报告的页面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a>分组和逻辑运算符

DLP 策略的要求通常比较简单，例如标识包含美国社会安全号码的所有内容。 但在其他情况下，DLP 策略可能需要标识定义更松散的数据。
  
例如，若要标识应遵循美国健康保险法案 (HIPAA) 的内容，需要查找：
  
- 包含特定类型敏感信息的内容，例如美国。社会安全号码或毒品管制局 (DEA) 号码。
    
    AND
    
- 更难以标识的内容，例如有关患者护理的通信，或者提供的医疗服务说明。 识别此内容需要匹配极庞大的关键字列表中的关键字，如国际疾病分类（ICD-9-CM 或 ICD-10-CM）。
    
使用分组和逻辑运算符（AND、OR），可轻松标识此类定义松散的数据。 创建 DLP 策略时，可以执行以下操作：
  
- 对敏感信息类型进行分组。
    
- 选择组内敏感信息类型之间以及组与组之间的逻辑运算符。
    
### <a name="choosing-the-operator-within-a-group"></a>选择组内的运算符

在组中，可选择要将内容视为与规则匹配，是只需满足该组中的任一条件，还是必须满足所有条件。
  
![显示组内运算符的组](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>添加组

可以快速添加组，该组内可包含自己的条件和运算符。
  
![添加组按钮](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>选择组之间的运算符

在组之间，为使内容与规则匹配，可选择只需满足一个组中的条件，还是必须满足所有组的条件。
  
例如，内置“**美国 HIPAA**”政策有一项规则，规定在组之间使用 **AND** 运算符，因此它标识的内容将包括： 
  
- 从组“**PII 标识符**”（至少一个 SSN 数字 **OR** DEA 数字） 
    
    AND****
    
- 从组“**医疗条件**”（至少一个 ICD-9-CM 关键字 **OR** 一个 ICD-10-CM 关键字） 
    
![显示组之间运算符的组](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>处理规则的优先级

在策略中创建规则时，每条规则都按创建顺序分配了优先级 — 这意味着，首先创建的规则具有第一优先级，创建的第二条规则具有第二优先级，以此类推。 
  
![按优先级顺序排列的规则](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
设置多个 DLP 策略后，可以更改一个或多个策略的优先级。 若要执行此操作，请选择一个策略，选择“**编辑策略**”，然后使用“**优先级**”列表指定其优先级。

![设置策略的优先级](media/dlp-set-policy-priority.png)

对照规则评估内容时，按优先级顺序处理规则。 如果内容符合多个规则，按优先级顺序处理规则，并强制实施最严格的操作。 例如，如果内容符合以下所有规则，将实施规则 3，因为它具有最高优先级且最严格：
  
- 规则 1：仅通知用户
    
- 规则 2：通知用户、限制访问并允许用户替代
    
- 规则 3：通知用户、限制访问且不允许用户替代
    
- 规则 4：仅通知用户
    
- 规则 5：限制访问
    
- 规则 6：通知用户、限制访问且不允许用户替代
    
在此示例中，要注意的是尽管只实施最严格的规则，仍会将所有匹配的规则记录在审核日志中，并显示在 DLP 报表中。
  
对于策略提示，请注意:
  
- 仅显示来自最高优先级、最具限制性的规则的策略提示。 例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。 这会让用户看不到策略提示的级联方式。
    
- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>调整规则，使它们更易或更难匹配

用户创建并启用 DLP 策略后，他们有时会遇到以下问题：
  
- 太多**不是**敏感信息的内容与规则匹配 — 也就是说，太多误报。 
    
- 太少**是**敏感信息的内容与规则匹配。 也就是说，未对敏感信息强制执行保护操作。 
    
若要解决这些问题，可以通过调整实例计数和匹配准确度来调整规则，使内容更难或更易匹配规则。 规则中使用的每一类敏感信息都有实例计数和匹配准确度。
  
### <a name="instance-count"></a>实例计数

实例计数是指若要使内容与规则匹配，某类敏感信息必须出现的次数。 例如，如果将美国或英国护照号码标识为 1 到 9， 则内容将与如下所示的规则匹配。
  
请注意，实例计数仅包括敏感信息类型和关键字的**唯一**匹配项。 例如，如果一个电子邮件中相同的信用卡号码出现了 10 次，则这 10 次计为信用卡号码的单个实例。 
  
若要使用实例计数来调整规则，则指南非常简单：
  
- 若要使规则更易匹配，减少“**最小**”计数和/或增加“**最大**”计数。 也可以通过删除数值，将“**最大**”设置为“**任意**”。 
    
- 若要使规则更难匹配，增加“**最小**”计数。 
    
在实例计数较低（例如，1-9）的规则中，通常会使用较为宽松的操作，如发送用户通知。 在实例计数较高（例如，10–任意）的规则中，使用更严格的操作，如限制访问内容且不允许用户替代。
  
![规则编辑器中的实例计数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>匹配准确度

如上文所述，使用不同类型的证据组合定义并检测敏感信息类型。 敏感信息类型通常由多个此类组合（称为模式）定义。 需要越少证据的模式匹配准确度（即置信水平）越低，而需要越多证据的模式匹配准确度（即置信水平）更高。 若要了解每种敏感信息类型使用的实际模式和置信水平，请参阅[使用敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)。
  
例如，名为“信用卡号”的敏感信息类型由两种模式定义：
  
- 置信度为 65% 的模式需要：
    
  - 信用卡号格式的数字。
    
  - 传递校验和的数字。
    
- 置信度为 85% 的模式需要：
    
  - 信用卡号格式的数字。
    
  - 传递校验和的数字。
    
  - 格式正确的关键字或到期日期。
    
可在规则中使用这些置信水平（或匹配准确度）。 在匹配准确度较低的规则中通常使用较为宽松的操作，如发送用户通知。 在匹配准确度较高的规则中使用更严格的操作，如限制访问内容且不允许用户替代。
  
务必了解在内容中标识特定类型的敏感信息（如信用卡号）时，只会返回单个置信水平：
  
- 如果所有匹配项适用于单个模式，则返回该模式的置信水平。
    
- 如果存在多个模式的匹配项（即，存在具有两种不同置信水平的匹配项），则返回高于任一单个模式的置信水平。 这就是难点。 例如，对于信用卡号，如果同时匹配 65% 和 85% 模式，则该敏感信息类型返回的置信水平超过 90%，因为证据越多，置信度越高。
    
因此，如果要为信用卡创建两条互斥的规则，一条用于 65% 的匹配准确度，另一条用于 85% 的匹配准确度，匹配准确度的范围将如下所示。 第一条规则仅选取 65% 模式的匹配项。 第二条规则选取**至少一个** 85% 匹配项，并且**可能具有**其他置信度较低的匹配项。 
  
![两条具有不同匹配准确度范围的规则](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
由于以上原因，使用不同的匹配准确性创建规则的指南为：
  
- 最低置信水平通常使用相同的“**最小**”和“**最大**”值（而不是范围）。 
    
- 最高置信水平通常是一个范围，该范围为略高于置信水平下限到 100。
    
- 任何中间置信水平范围通常为略高于置信水平下限，略低于置信水平上限。
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a>将标签用作 DLP 策略中的条件

可创建一个标签，再执行以下操作：
  
- **发布**标签，让最终用户可看到此标签并可在内容中手动应用它。 
    
- 对匹配所选条件的内容**自动应用**标签。 
    
若要详细了解标签，请参阅[保留标签概述](labels.md)。
  
创建标签后，即可在 DLP 策略中使用该标签作为条件。 例如，可能基于以下原因执行此操作：
  
- 发布了名为“**机密**”的标签，使组织内部人员可在机密电子邮件和文档中手动应用该标签。 通过在 DLP 策略中使用此标签作为条件，可限制与组织外部人员共享标记为“**机密**”的内容。 
    
- 为名为“**Alpine House**”的项目创建了一个带此名称的标签，然后将此标签自动应用到包含关键字“Alpine House”的内容中。 通过在 DLP 策略中使用此标签作为条件，在最终用户要与组织外部人员共享此内容时，可向其显示一条策略提示。 
    
- 发布了名为“**税务记录**”的标签，使记录管理人员能够对需归类为记录的内容手动应用此标签。 通过在 DLP 策略中使用此标签作为条件，可查找带有此标签并包含其他类型敏感信息（例如 ITIN 或 SSN）的内容；对标记有“**税务记录**”的内容应用保护操作；并根据 DLP 报告和审核日志数据获取有关 DLP 策略的详细活动报告。 
    
- 对一组管理人员的 Exchange 邮箱和 OneDrive 帐户发布了名为“**高层管理团队 - 敏感**”的标签。 通过在 DLP 策略中使用此标签作为条件，可对同一部分内容和用户执行保留和保护操作。 
    
在 DLP 策略中使用标签作为条件之后，可对一组特定内容、位置或用户选择性地执行保护操作。
  
![用作条件的标签](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a>即将支持敏感度标签

目前，你只能将保留标签用作条件，而不能将[敏感度标签](sensitivity-labels.md)用作条件。 目前，我们正致力于支持在此条件中使用敏感度标签。
  
### <a name="how-this-feature-relates-to-other-features"></a>此功能与其他功能的联系

可对包含敏感信息的内容应用多个功能：
  
- [保留标签](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)均可对此内容执行**保留**操作。 
    
- DLP 策略可对此内容执行**保护**操作。 执行这些操作之前，DLP 策略可要求内容除包含标签之外还需满足其他条件。 
    
![可应用于敏感信息的功能图表](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
请注意，相较于对敏感信息应用的标签或保留策略，DLP 策略的检测功能更强。 DLP 策略可以对包含敏感信息的内容执行保护操作；从内容中删除敏感信息之后，这些保护操作会在下一次扫描内容时撤消。 但如果对包含敏感信息的内容应用了保留策略或标签，则该操作是一次性操作，即使删除了敏感信息也不会撤消该操作。
  
在 DLP 策略中使用标签作为条件之后，可对包含该标签的内容执行保留和保护操作。 可将带标签的内容完全视为包含敏感信息的内容；标签和敏感信息类型都是用于对内容进行分类的属性，以便对该内容执行操作。
  
![使用标签作为条件的 DLP 策略图表](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>简单设置与高级设置

创建 DLP 策略时，将在简单或高级设置中进行选择：
  
- **简单设置**，可轻松创建最常见类型的 DLP 策略，无需使用规则编辑器创建或修改规则。 
    
- **高级设置**，使用规则编辑器，让使用者可完全控制 DLP 策略的每个设置。 
    
不要担心，实际上简单设置和高级设置的工作方式完全相同，都是强制执行由条件和操作组成的规则，只是使用简单设置时，看不到规则编辑器。 这是快速创建 DLP 策略的方法。
  
### <a name="simple-settings"></a>简单设置

到目前为止，最常见的 DLP 方案是创建策略，帮助保护含敏感信息的内容，防止与组织外人员共享该内容，并采取自动补救措施，例如限制可访问内容的人员、向最终用户或管理员发送通知、对事件进行审核以备后续调查。 人们使用 DLP 防止意外泄露敏感信息。
  
为轻松实现这一目标，创建 DLP 策略时，可选择**使用简单设置**。 这些设置可提供实现最常见 DLP 策略所需的一切，无需使用规则编辑器。
  
![DLP 简单和高级设置选项](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>高级设置

如需创建自定义程度更高的 DLP 策略，可选择**使用高级设置**。
  
高级设置会显示规则编辑器，可通过它完全控制每个可能的选项，包括每个规则的实例计数和匹配准确度（可信度级别）。
  
若要快速跳转到某一部分，请单击规则编辑器顶部导航中的项，转到下面的部分。
  
![DLP 规则编辑器的顶部导航菜单](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP 策略模板

创建 DLP 策略的第一步是选择要保护的内容。 从 DLP 模板开始创建，无需从头构建一组新规则，无需指出默认应包含哪些信息类型。 然后即可添加或修改这些要求，微调规则以满足组织的特定要求。
  
预配置的 DLP 策略模板可帮助你检测特定类型的敏感信息，如 HIPAA 数据、PCI-DSS 数据、格雷姆-里奇-比利雷法案数据，甚至是特定区域设置的个人身份信息 (P.I.)。 要使您能够轻松地查找和保护常见类型的敏感信息，包含在 Office 365 中的策略模板已包含您要开始构建策略所需的最常见的敏感信息类型。
  
![数据丢失防护策略模板列表，重点放在美国爱国者法案模板上](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
组织可能还有自己特定的要求，在这种情况下可通过选择“**自定义策略**”选项从头创建 DLP 策略。 自定义策略为空，且不包含任何预制定的规则。 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a>在测试模式下逐步部署 DLP 策略

创建 DLP 策略时，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。 例如，你不希望新的 DLP 策略在无意中阻止用户访问需要进行访问才能完成工作所需的上千个文档。
  
如果你创建的 DLP 策略具有较大的潜在影响，建议你按以下顺序执行操作：
  
1. **在不使用策略提示的情况下启动测试模式**，然后使用 DLP 报告和任何事件报告评估影响。 您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。 根据结果，您可以在需要时微调规则。 在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。 
    
2. **移动到使用通知和策略提示的测试模式**，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。 
    
3. **开始完全强制执行策略**，以便应用规则中的操作，并保护内容。 继续监视 DLP 报告及任何事件报告或通知，确保结果是你所期望的。 
    
![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
你可以随时关闭 DLP 策略，这将影响此策略中的所有规则。 但是，也可以通过在规则编辑器中切换其状态来单独关闭每个规则。
  
![关闭策略中的规则的选项](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

你还可以更改策略中的多个规则的优先级。 若要执行此操作，请打开要编辑的策略。 在规则行中，选择省略号 (**...**)，然后选择一个选项，例如“**下移**”或“**移到最后**”。

![设置规则优先级](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a>DLP 报告

创建并启用 DLP 策略后，你会希望验证这些策略是否按预期工作，以及是否有助于保持合规性。 使用 DLP 报告，您可以快速查看随着时间的推移 DLP 策略和规则匹配的次数，以及误报和替代数。 对于每个报告，您都可以按位置、时间范围，甚至缩小为特定的策略、规则或操作来筛选这些匹配项。
  
使用 DLP 报告，您可以获取业务见解并了解以下内容：
  
- 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
- 发现违反贵组织的合规性策略的业务流程。
    
- 了解 DLP 策略的任何业务影响。
    
此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。
  
![安全与合规中心的报表仪表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>DLP 策略的工作原理

DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。
  
### <a name="policies-are-synced"></a>策略会进行同步

在安全 &amp; 合规中心创建 DLP 策略后，它将存储在中心策略存储中，然后同步到各种内容源，其中包括：
  
- Exchange Online，并从它同步到 Outlook 网页版和 Outlook
    
- OneDrive for Business 站点
    
- SharePoint Online 站点
    
- Office 桌面程序（Excel、PowerPoint 和 Word）

- Microsoft Teams 频道和聊天消息
    
该策略同步到正确的位置后，它将开始评估内容并强制执行操作。
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>OneDrive for Business 和 SharePoint Online 站点中的策略评估

文档在你的所有 SharePoint Online 站点和 OneDrive for Business 站点中会不断更改，用户会持续对文档执行创建、编辑、共享等操作。 这意味着文档可能随时会与 DLP 策略发生冲突，或变为合规状态。 例如，一个用户上载的文档可能不包含与团队站点相关的敏感信息，但之后，另一个客户可能会编辑同一文档，并向文档添加了敏感信息。
  
为此，DLP 策略经常检查后台中是否包含与策略相符的文档。 您可以将这视为异步策略评估。
  
#### <a name="how-it-works"></a>运作方式
 
在用户添加或更改其站点中的文档时，搜索引擎会扫描内容，以便你稍后对其进行搜索。 同时，还对此内容进行敏感信息扫描，以检查是否进行过共享。 找到的任何敏感信息都安全地存储在搜索索引中，以便仅供合规性团队而不是典型用户进行访问。 已启用的每个 DLP 策略在后台（异步）运行，它会经常检查搜索中是否包含与某个策略相符的内容，并应用操作以防止由于疏忽而导致泄漏。
  
![显示 DLP 策略如何异步计算内容的图表](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。
  
DLP 评估可编制索引的任何内容。 有关默认的爬网文件类型的详细信息，请参阅 [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Exchange Online、Outlook 和 Outlook 网页版中的策略评估

当创建一个将 Exchange Online 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到 Exchange Online，然后从 Exchange Online 同步到 Outlook 网页版和 Outlook。
  
在 Outlook 中撰写消息时，会显示策略提示，因为会根据 DLP 策略对创建的内容进行评估。 邮件发送后，会根据 DLP 策略对其进行评估，作为邮件流程的正常部分，还会使用 Exchange 管理中心中创建的 Exchange 邮件流规则（也称为传输规则）和 DLP 策略进行评估。 DLP 策略会扫描邮件及其所有附件。
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Office 桌面程序中的策略评估

Excel、PowerPoint 和 Word 包含相同的功能，可像 SharePoint Online 和 OneDrive for Business 一样识别敏感信息和应用 DLP 策略。 这些 Office 程序直接从中心策略存储同步其 DLP 策略，然后在用户处理从包含在 DLP 策略中的网站打开的文档时，不断根据 DLP 策略对内容进行评估。
  
Office 中的 DLP 策略评估旨在不对程序的性能或处理内容的用户的工作效率产生任何影响。 如果他们正在处理大型文档，或用户的计算机正忙，可能需要几秒钟才能显示策略提示。

### <a name="policy-evaluation-in-microsoft-teams"></a>Microsoft Teams 中的策略评估
 
当创建一个将 Microsoft Teams 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到用户帐户和 Microsoft Teams 频道和聊天消息。 根据 DLP 策略的配置方式，当某人尝试在 Microsoft Teams 聊天或频道消息中共享敏感信息时，可以阻止或撤消该消息。 并且，这些用户将无法打开包含敏感信息以及与来宾（外部用户）共享的文档。 若要了解详细信息，请参阅[数据丢失防护和 Microsoft Teams](dlp-microsoft-teams.md)。
 
## <a name="permissions"></a>权限

创建 DLP 策略的合规性团队成员需要具有对安全 &amp; 合规中心的访问权限。 默认情况下，租户管理员将有权访问此位置，并可授予合规部主管和其他人访问安全 &amp; 合规中心的权限，而不为其提供租户管理员的所有权限。为此，我们建议你：
  
1. 在 Office 365 中创建组并向其添加合规部主管。
    
2. 在安全 &amp; 合规中心的“**权限**”页面上创建一个角色组。 
    
3. 将 Office 365 组添加到角色组。
    
有关详细信息，请访问[向用户授予对 Office 365 合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。
  
只有在创建和应用 DLP 策略时才需要这些权限。 策略执行不需要访问此内容。
  
## <a name="find-the-dlp-cmdlets"></a>查找 DLP cmdlet

若要使用安全 &amp; 合规中心的大多数 cmdlet，你需要执行以下操作：
  
1. [使用远程 PowerShell 连接到 Office 365 安全 &amp; 合规中心](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. 使用任何[策略和合规性 dlp cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)
    
但是，DLP 报告需要从 Office 365（包括 Exchange Online）提取数据。 因此，**可以在 Exchange Online Powershell 中使用 DLP 报告的 cmdlet，而不能在安全 &amp; 合规中心 Powershell 中使用**。 因此，若要使用适用于 DLP 报告的 cmdlet，你需要执行以下操作：
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. 对 DLP 报告使用以下任意 cmdlet：
    
  - [Get-DlpDetectionsReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [Get-DlpDetailReport](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a>更多信息

- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md)
    
- [发送通知，并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)
    
- [创建 DLP 策略来保护具有 FCI 或其他属性的文档](protect-documents-that-have-fci-or-other-properties.md)
    
- [DLP 策略模板包含的内容](what-the-dlp-policy-templates-include.md)
    
- [使用敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)
    
- [DLP 函数查找的内容](what-the-dlp-functions-look-for.md)
    
- [创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)
    

