---
title: Office 365 中的监督策略
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: 了解 Office 365 中的监督策略
ms.openlocfilehash: 3259620e16b626c81c9c0f71f7be1f627e9c6bc9
ms.sourcegitcommit: 3f3f3ecb28ef65d023f3573f9a4e09a0586d8f53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "36490759"
---
# <a name="supervision-policies-in-office-365"></a>Office 365 中的监督策略

Office 365 中的监督策略使您可以捕获指定审阅者进行检查的员工通信。 您可以定义用于捕获组织中的内部和外部电子邮件、Microsoft 团队或第三方通信的特定策略。 然后, 审阅者可以检查这些邮件, 以确保它们符合组织的邮件标准, 并使用分类类型解决这些问题。 

这些策略还可以帮助您解决诸多新式合规性挑战, 包括:

- 监视日益增长的通信信道类型
- 邮件数据量的增加
- 法规实施 & 受到罚款的风险

在某些组织中, IT 支持与合规性管理组之间可能存在的职责分离。 Office 365 支持将监督策略功能配置与策略的配置与捕获的通信相分离。 例如, 组织的 IT 组可能负责设置角色权限和组, 以支持由组织的合规性团队配置和管理的监督策略。

有关监督策略的快速概述, 请参阅[Microsoft 机械通道](https://www.youtube.com/user/OfficeGarageSeries)上的[监督策略视频](https://youtu.be/C3Y8WZ7o_dI)。

若要了解有关即将推出的监察功能改进和可用性的详细信息, 请参阅[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap)。

## <a name="scenarios-for-supervision-policies"></a>监督策略的应用场景

监督策略可帮助监视组织中的多个方面的通信:

- **公司策略**

    员工必须遵守其所有与业务相关的通信中的可接受使用、道德标准和其他公司政策。 监督策略可以检测到策略违规, 并帮助您采取纠正措施来帮助缓解这些类型的事件。 例如, 您可以监视组织中的潜在人资源违规 (如骚扰或在员工通信中使用不适当或攻击性的语言)。

- **风险管理**

    组织负责在其基础结构和公司网络系统中分布的所有通信。 使用监督策略来帮助确定和管理潜在的法律暴露和风险, 可帮助最大限度地减少风险, 然后再损坏公司运营。 例如, 您可以监视组织以实现机密项目的未经授权的通信, 例如即将进行的收购、合并、收益披露、reorganizations 或领导团队更改。

- **合规性**

    大多数组织必须符合其正常操作过程中的某些类型的法规遵从性标准。 这些法规通常要求组织为适合其行业的邮件服务实施某种类型的监督或监督过程。 金融行业规章机构 (FINRA) 规则3110是组织实现监管过程的一个很好的示例, 可监视其员工的活动以及它所参与的业务类型。 另一个示例可能是监视组织中的经纪人代理商以防止潜在的 laundering、内幕交易、collusion 或 bribery 活动的需要。 监督策略可通过提供监控和报告公司通信的过程来帮助您的组织满足这些要求。

## <a name="components"></a>组件

### <a name="supervision-policy"></a>监督策略

在合规中心中创建监督策略。 这些策略定义要在组织中查看哪些通信和用户, 定义通信必须满足的自定义条件, 并指定应执行审阅的用户。 监管审核角色组中包括的用户可以设置策略和分配此角色的任何人都可以访问合规中心中的监督页面。

### <a name="supervised-users"></a>受监督用户

在开始使用监督之前, 您必须确定哪些用户需要查看其通信。 在策略中, 用户电子邮件地址标识要监督的个人或人员组。 这些组的一些示例包括 Office 365 组、基于 Exchange 的通讯组列表和 Microsoft 团队频道。 您还可以将特定用户或组从监督的组或组列表中排除。

> [!IMPORTANT]
> 监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证, 或包含在 Office 365 企业版 E5 订阅中。如果你没有现有的企业版 E5 计划, 并且想要尝试监督, 则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。

### <a name="reviewers"></a>Reviewers

当您创建监督策略时, 您必须确定将对受监督用户的邮件执行审查的用户。 在该策略中, 用户电子邮件地址标识了要查看受监督的通信的个人或人员组。 所有审阅者都必须在 Exchange Online 上托管邮箱。

### <a name="groups-for-supervised-users-and-reviewers"></a>受监督的用户和审阅者的组

若要简化设置, 请为需要查看其通信的用户创建组, 并为查看这些通信的用户分组。 如果使用的是组, 可能需要多个。 例如, 如果要监视两个不同的人员组之间的通信, 或者要指定未受监督的组。

当您为受监督的用户选择 Office 365 组时, 该策略将监视共享 Office 365 邮箱的内容以及与该组关联的 Microsoft 团队频道。 当您选择通讯组列表时, 该策略将监视单个用户邮箱。

### <a name="supported-communication-types"></a>支持的通信类型

使用监督策略, 您可以选择监视以下一个或多个通信平台中的邮件:

- **Exchange 电子邮件:** 作为 Office 365 订阅的一部分托管在 Exchange Online 上的邮箱都有资格进行邮件监督。 与监察策略条件匹配的电子邮件和附件可立即用于监控和监控报告。 受支持的监督附件类型与[Exchange 邮件流规则内容检查支持的文件类型](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)相同。

- **Microsoft 团队:** 可以监督公共和私有 Microsoft 团队频道和个人聊天中的聊天通信和相关附件。 团队聊天匹配监督策略条件每24小时处理一次, 然后可在监督报告中进行监视。 使用以下组管理配置监督团队中的个人用户聊天和通道通信:

    - **对于团队聊天监督:** 为单个用户分配或向监督策略分配一个[通讯组](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)。 这适用于1对1或一对多用户/聊天的关系。
    - **对于团队渠道通信:** 将您想要监视的每个 Microsoft 团队频道或 Office 365 组分配给监督策略, 其中包含特定用户。 如果将同一用户添加到其他 Microsoft 团队频道或 Office 365 组, 请确保将这些新的频道和组添加到监督策略中。

- **Skype For Business Online:** 可以监督 Skype for Business Online 中的聊天通信和相关附件。 Skype for Business Online 聊天匹配监督策略条件每24小时处理一次, 然后可在监督报告中进行监视。 受监督聊天对话源于[以前在 Skype for Business Online 中保存的对话](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)。  使用以下组管理配置监督 Skype for Business Online 中的用户聊天通信:

    - **对于 Skype For Business Online 研讨监察:** 为单个用户分配或向监督策略分配一个[通讯组](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE)。 这适用于1对1或一对多用户/聊天的关系。

- **第三方来源:** 您可以监督来自第三方源 (如 Facebook 或 DropBox) 的通信, 以了解导入到组织中的 Office 365 邮箱中的数据。 [了解如何将第三方数据导入 Office 365](https://docs.microsoft.com/office365/securitycompliance/archiving-third-party-data)。

默认情况下, 跨这些平台捕获的通信每个策略保留7年, 即使用户离开组织并删除了其邮箱也是如此。

### <a name="policy-settings"></a>策略设置

#### <a name="direction"></a>Direction

默认情况下, 显示**方向是**条件, 不能删除。 策略中的通信方向设置分别或一起选择:

- **入站**: 可以选择 "**入站**" 以查看发送**到**您选择的人员的通信, 以便**通过**未包含在策略中的人员进行监督。
- **出站**: 如果想要查看**从**你选择的人员发送到未包含在策略中的**** 人员的通信, 可以选择 "**出站**"。
- **Internal**: 可以选择 "**内部**" 以查看在策略中标识的人员**之间**发送的通信。

#### <a name="sensitive-information-types"></a>敏感信息类型

您可以选择将敏感信息类型作为监督策略的一部分包括在内。 敏感信息类型可以是预定义的, 也可以是自定义的数据类型, 可帮助确定和保护信用卡号码、银行帐号、护照号码等。 作为 Office 365[数据丢失防护 (DLP)](data-loss-prevention-policies.md)的一部分, 敏感信息配置可以使用模式、字符邻近度、可信度和偶数自定义数据类型, 以帮助识别和标记可能敏感的内容。 默认的敏感信息类型为:

- 财务
- 医疗和运行状况
- 隐私
- 自定义信息类型

若要了解有关敏感信息详细信息和默认类型中包含的模式的详细信息, 请参阅[要查找的敏感信息类型](what-the-sensitive-information-types-look-for.md)。

#### <a name="custom-keyword-dictionaries"></a>自定义关键字词典

配置自定义关键字词典 (或词典), 以提供特定于您的组织或行业的关键字的简单管理。 关键字词典支持每个字典最高为100000个术语。 如果需要, 您可以将多个自定义关键字词典应用于单个策略或每个策略包含一个关键字词典。 这些词典在监督策略中分配, 可从文件 (如 .csv 或 .txt 列表) 或可以[在合规中心中导入](create-a-keyword-dictionary.md)的列表中获得。

#### <a name="offensive-language"></a>冒犯性语言

监视组织中发送或接收的电子邮件是否带有攻击性的语言。 模型使用机器学习、人工智能和关键字的组合来识别电子邮件中的语言, 这可能会违反反骚扰和威胁策略。 冒犯性语言模型目前支持英语关键字, 并监视电子邮件的正文。

> [!NOTE]
> 创建一个[数据丢失防护策略](create-test-tune-dlp-policy.md), 其中包含阻止术语的[自定义关键字词典](create-a-keyword-dictionary.md), 如果需要执行以下操作:
>
> - 监视组织中适用于攻击性语言的 Microsoft 团队通信
> - 阻止或阻止组织中的通信中的冒犯性语言

请注意, 该模型不提供冒犯性语言的详尽列表。 此外, 语言和文化标准不断变化, 而在这些现实中, Microsoft 保留以其自己的意愿更新模型的权利。 虽然模型可以帮助组织监视攻击性语言, 但该模型并不旨在提供组织的唯一方法来监视或解决此类语言。 您的组织 (而不是 Microsoft) 仍负责与监控和阻止冒犯性语言相关的所有决策。

冒犯性语言模型监视与以下语言类型相关的看法电子邮件:

|**类型**|**说明**|
|:-----|:-----|
| **Profanities** | Embarrass 大多数人的表达式。 |
| **Slurs** | 针对特定组 (例如, 种族、ethnicity、色情方向、残疾人士) 表达 prejudice 的表达式。 |
| **Taunts** | Taunt、condemn、ridicule 或可能导致 anger 或暴力的表达式。 |
| **伪装的表达式** | 含义或发音与另一个更具冒犯性术语的表达式相同。 |

#### <a name="conditional-settings"></a>条件设置
<a name="ConditionalSettings"> </a>

您为策略选择的条件适用于来自组织中的电子邮件和第三方源的通信 (如 Facebook 或 DropBox)。

下表对每个条件进行了详细说明。
  
|**Condition**|**如何使用此条件**|
|:-----|:-----|
| **从这些域中的任何域接收邮件**  <br><br> **不从这些域中的任何域接收邮件** | 应用该策略以在接收的邮件中包含或排除特定域或电子邮件地址。 输入每个域或电子邮件地址, 并使用逗号分隔多个域或电子邮件地址。 输入的每个域或电子邮件地址将单独应用, 只有一个域或电子邮件地址必须应用于该邮件的策略。 <br><br> 如果要监视来自特定域的所有电子邮件, 但又要排除不需要审阅的邮件 (新闻稿、通知等), 则必须配置以下条件:**邮件未从任何这些域的任何条件收到**, 其中排除了电子邮件地址 (示例 "newsletter@contoso.com")。 |
| **将邮件发送到这些域中的任何域**  <br><br> **邮件不会发送到这些域中的任何域** | 应用该策略以在已发送邮件中包含或排除特定域或电子邮件地址。 输入每个域或电子邮件地址, 并使用逗号分隔多个域或电子邮件地址。 每个域或电子邮件地址单独应用, 只有一个域或电子邮件地址必须申请策略才能应用于邮件。 <br><br> 如果要监视发送到特定域的所有电子邮件, 但要排除不需要审阅的已发送邮件, 则必须配置两个条件: <br> -将**消息发送到**定义域的任何域条件 ("contoso.com"), 并 <br> -**邮件不会发送到任何**不包括电子邮件地址 ("subscriptions@contoso.com") 的域条件。 |
| **邮件使用以下任何标签进行分类**  <br><br> **不使用这些标签中的任何一个对邮件进行分类** | 在邮件中包含或排除某些保留标签时应用策略。 必须单独配置保留标签, 并在此条件中选择已配置的标签。 您选择的每个标签都将单独应用 (必须只有其中一个标签适用于该策略应用于邮件)。 有关配置保留标签的详细信息, 请参阅[保留标签概述](https://docs.microsoft.com/office365/securitycompliance/labels)。|
| **邮件包含以下任何词语**  <br><br> **邮件不包含以下任何词语** | 若要在邮件中包含或排除某些字词或短语时应用策略, 请在单独的行中输入每个单词或短语。 您输入的每一行都将单独应用 (必须只有其中一个行适用于策略应用于邮件)。 若要详细了解如何输入字词或短语，请参阅下一部分[Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords)。|
| **附件包含这些词语中的任何一个**  <br><br> **附件中不包含任何词语** | 若要在邮件附件 (如 Word 文档) 中包含或排除某些字词或短语时应用策略, 请在单独的行中输入每个单词或短语。 您输入的每一行都将单独应用 (只有一条线路必须适用于该策略应用于附件)。 若要详细了解如何输入字词或短语，请参阅下一部分[Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords)。|
| **附件是这些文件类型中的任何一种**  <br><br> **附件是这些文件类型中的任何一种** | 若要监督包含或排除特定类型附件的通信, 请输入文件扩展名 (如 .exe 或 .pdf)。 如果要包含或排除多个文件扩展名, 请在单独的行上输入这些扩展名。 要应用的策略仅有一个附件扩展名必须匹配。|
| **邮件大小大于**  <br><br> **邮件大小不大于** | 若要查看基于特定大小的邮件, 请使用这些条件来指定邮件在被审阅前可以达到的最大或最小大小。 例如, 如果您指定的**邮件大小大于** \> **1.0 mb**, 则所有 1.01 MB 和更大的邮件都将被审阅。 这种情况下，您可以选择字节、千字节、兆字节或千兆字节。|
| **附件大于**  <br><br> **附件不大于** | 若要根据附件的大小查看邮件, 请指定邮件之前的附件的最大或最小大小, 并且其附件可能会被审阅。 例如, 如果指定**附件大于** \> **2.0 mb**, 则所有附件为 2.01 mb 的邮件都将被审阅。 这种情况下，您可以选择字节、千字节、兆字节或千兆字节。|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>将字词和短语与电子邮件或附件匹配
<a name="Matchwords"></a>您输入的每一行都将单独应用 (只有一条线路必须适用策略条件, 才能应用于电子邮件或附件)。 例如, 我们使用条件,**邮件包含这些词语中的任何词语**, 关键字 "银行家" 和 "内幕交易" 在单独的行上。 该策略适用于任何包含 "银行家" 或短语 "内幕交易" 的邮件。 只有出现其中一个字词或短语，才能应用此策略条件。 邮件或附件中的单词必须与您输入的内容完全匹配。

若要扫描相同关键字的电子邮件和附件, 请为您要监视的术语创建一个包含[自定义关键字词典](create-a-keyword-dictionary.md)的[数据丢失防护策略](create-test-tune-dlp-policy.md)。 此策略配置标识在电子邮件**或**电子邮件附件中显示的已定义关键字。 使用标准条件策略设置 (*邮件包含以下任何词语*和*附件包含这些词语中的*任何词语) 标识邮件中和附件中的术语需要这些术语**同时**存在于邮件和附着.
  
##### <a name="enter-multiple-conditions"></a>输入多个条件

如果你输入了多个条件, Office 365 将使用所有条件共同确定何时将策略应用于通信项。 在设置多个条件时, 必须满足所有条件, 才能应用策略, 除非您输入了异常。 例如, 如果邮件包含 "商贸" 一词, 并且大于 2 MB, 则需要适用的策略。 但是, 如果邮件还包含 "由 Contoso 财务财务批准" 这一词, 则该策略不应应用。 因此, 在这种情况下, 三个条件将如下所示:
  
- **邮件包含这些词语中的任何词语**, 关键字为 "商贸"

- **邮件大小大于**, 值为 2 MB

- **邮件不包含这些词语**, 关键字 "由 Contoso 财务团队批准"

#### <a name="review-percentage"></a>审阅百分比

如果要减少要查看的内容量, 可以指定监督策略控制的所有通信的百分比。 从符合所选策略条件的内容的总百分比中选择内容的实时、随机样本。 如果您希望审阅者审阅所有项目, 则可以在监督策略中输入**100%** 。

## <a name="monitor--manage"></a>监视 & 管理

可以轻松监视监督策略的结果并应用解决方案标记。 您可以快速查看:

- 已审阅项目的状态
- 受监督的用户和组
- 指定为审阅者的用户和组

### <a name="supervision-policy-dashboard"></a>监督策略仪表板

使用监督策略仪表板管理监督策略结果和解决未完成项目。 此仪表板允许审阅者查看需要审阅的项目, 对项目执行操作, 并查看每个监督策略的以前查看和解决的项目的结果。 **** > 您可以访问合规性中心的监察策略仪表板, 即**打开***您的自定义策略* > 。

#### <a name="dashboard-home"></a>仪表板主页

仪表板**主页**包含多个部分, 可帮助您快速对监管策略进行操作。 您可以在此处执行以下操作:

- 快速查看本周的挂起和解决的突出显示内容
- 查看所选策略的受监督用户和受监督组的列表
- 查看所选策略的审阅者和审阅团队的列表
- 查看哪些通信平台在监督策略下有内容

#### <a name="review-tab"></a>审阅选项卡

**审核**选项卡是审阅者对所选策略标识的项目进行分类和解析的位置。 您可以在此处执行以下操作:

- 按挂起、合规、不兼容和可疑项目进行筛选。
- 将单个项目标记为兼容、不符合或不必要。 您还可以记录项目注释以帮助阐明所执行的标记操作。
- 将多个项目批量标记为合规性、不符合或不值得怀疑。 您还可以录制包含多个项目的注释, 以帮助阐明所执行的标记操作。
- 查看单个项目的标记历史记录。 包括解析项目的收件人、操作的日期和时间、解析标记以及任何包含的注释。
- 将之前审阅过的项目重新分类为合规性、不合规或可疑。 您还可以录制包含单个或多个项目的注释, 以帮助阐明所执行的重新分类操作。

#### <a name="resolved-items-tab"></a>"已解决项目" 选项卡

"**已解决的项目**" 选项卡是审阅者可以在其中查看所选策略的所有以前已解决的项目。 您可以在此处执行以下操作:

- 快速查看和排序已解决的项目的主题、发件人和日期
- 查看任何选定项目的分类和注释历史记录

## <a name="reports"></a>报表

使用监督报告可查看策略和审阅者级别的审阅活动。 对于每个策略, 您还可以查看当前状态的 "审阅活动" 的实时统计信息。 您可以使用监督报告执行以下操作:
  
- 验证您的策略是否按预期运行。
- 了解需要查看的通信数。
- 了解有多少通信不符合标准, 哪些通信通过审阅。 此信息可帮助您决定是微调策略还是更改审阅者数。

### <a name="view-the-supervision-report"></a>查看监督报告

1. 使用具有查看监督报告的权限的管理员帐户的凭据登录[合规性中心](https://compliance.microsoft.com)。
2. 请转到 "**报告** \> "**仪表板**或 "**监督**" 查看监督报告小组件, 了解当前监督策略活动的摘要。
3. 选择**监督**小组件以打开 "详细报告" 页。

> [!NOTE]
> 如果您无法访问 "**报告**" 页, 请检查您是否是监管审核角色组的成员, 如组织中的 "[使监督功能在组织中可用](configure-supervision-policies.md)" 中所述。 包含在此角色组中, 您可以创建和管理监督策略并运行报告。
  
### <a name="how-to-use-the-report"></a>如何使用报表

此报告列出了审核过程中每个阶段的每个策略和通信数。 使用报告可执行以下操作:
  
- 查看所有或特定策略的数据。
- 查看按标记类型、审阅者或邮件类型分组的数据。
- 根据活动日期、策略和审阅者活动将数据导出到 CSV 文件。
- 根据活动日期、标记类型、审阅者和邮件类型筛选数据。

以下是 "**标记类型**" 列中显示的值的细目。
  
|**标记类型**|**含义**|
|:-----|:-----|
| **未审阅** | 尚未审阅的电子邮件数。 这些电子邮件在 "Office 365 监督" 仪表板中等待审阅。
| **Compliant** | 已审阅并标记为合规的电子邮件数。 这些邮件仍需要解析。 |
| **Questionable** | 审阅并标记为可疑的电子邮件数量。 用作其他审阅者的标志, 以帮助检查电子邮件是否需要调查合规性。 这些邮件仍需要解析。 |
| **不符合 (活动)** | 审阅者当前正在调查的不合规电子邮件数。 |
| **不符合 (已解决)** | 审阅者调查和解析的不合规电子邮件数。 |
| **命中策略** | 来自 Exchange、团队和第三方数据源的邮件的总数 (每日) 与监督策略中定义的一个或多个条件相匹配 |
| **在 Purview** | 监督策略扫描的来自 Exchange、团队和第三方数据源的邮件的总数 (每日) |
| **解析** | 已分类为 "**已解决**" 的 Exchange、团队和第三方数据源中的邮件总数|

> [!NOTE]
> 必须先设置监督策略, 然后才能将其显示在报告中。 如果删除策略, 则仍显示历史数据。 但是, 它们被指示为 "不存在的策略", 并且**导出**功能不可用。

## <a name="audit"></a>跟踪

在某些情况下, 您必须向法规或合规性审核人员提供信息, 以证明员工活动和通信的监督。 这可能是与定义的策略相关的所有监管活动的摘要, 也可能随时受监督策略更改。 监督策略具有内置审核跟踪, 可以实现内部或外部审核的完整就绪状态。 监督策略监视的每个操作的详细审核历史记录都提供监督过程证明。

在统一的 Office 365 审核日志中审核并提供以下监察策略活动:

|**活动**|**关联命令**|
|:-----|:-----|
| **创建策略** | [新 SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2) <br> [新 SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule) |
| **编辑策略** | [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2) <br> [SupervisoryReviewRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule) |
| **删除策略** | [SupervisoryReviewPolicyV2](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2) |

在统一审核日志中查看审核活动, 或使用[UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) PowerShell cmdlet 查看审核活动。

例如, 以下示例返回所有监管审核活动 (策略和规则) 的活动, 并列出每个活动的详细信息:

```
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

除了监督报告和日志中提供的信息之外, 您还可以使用[SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity?view=exchange-ps) PowerShell cmdlet 来返回所有监察策略活动的完整详细列表。

## <a name="ready-to-get-started"></a>准备好开始了吗？

若要为你的组织配置监督策略, 请参阅[配置监督策略](configure-supervision-policies.md)。