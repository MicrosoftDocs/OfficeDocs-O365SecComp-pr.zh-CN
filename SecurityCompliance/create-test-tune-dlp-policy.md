---
title: 创建、测试和优化 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '开始使用 DLP 策略的最简单、 最常用方法是使用 Office 365 中的模板包括之一。 '
ms.openlocfilehash: 1d4697811a5d8dd426fed80d3d60bcd2fbea6335
ms.sourcegitcommit: 42c7ad69f95fc4d2de13293b39cc44931b9f82e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "26522784"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>创建、测试和优化 DLP 策略

**主体作者** </br>
Paul Cunningham，Microsoft MVP </br>
[实践 365](https://practical365.com/) </br>
[@Practical365](https://twitter.com/practical365)</br>
__________________________________________________

数据丢失防护是旨在帮助防止有意或无意公开的敏感信息不需要方贵组织的 Office 365 合规性功能。DLP 具有其根中 Exchange Server 和 Exchange Online 中，并且还适用于 SharePoint Online 和 OneDrive for Business。

DLP 使用内容分析引擎来检查电子邮件和文件的内容，寻找敏感信息，如信用卡号和个人身份信息 (PII)。敏感信息通常不应发送电子邮件，或包含在文档中，不采用如加密电子邮件或文件的其他步骤。使用 DLP 可以检测敏感信息，并执行操作，例如：

- 登录不但的事件
- 向最终用户正在发送电子邮件或共享文件显示警告
- 主动阻止电子邮件或文件共享从正在进行

有时客户消除 DLP，因为它们不考虑具有需要保护的数据的类型。假设是敏感数据，如医疗记录或财务信息仅存在类似医疗行业或运行联机存储的公司。但任何业务可处理定期，敏感信息，即使它们不实现它。员工名称的电子表格和出生日期是作为客户名称和信用卡详细信息的电子表格只需为敏感。和此类信息倾向于 float 周围的详细信息比您预想，如员工安静安装转有关其一天的任务，思考 nothing 导出 CSV 文件从系统，并向某人发送该电子邮件。您也可能是惊讶频率员工发送电子邮件，而不考虑后果包含信用卡或银行业详细信息。

## <a name="how-sensitive-information-is-detected-by-dlp"></a>如何检测到的 DLP 敏感信息

由正则表达式 (RegEx) 模式匹配，结合使用如邻近其他指标的特定关键字匹配模式与标识敏感信息。此示例是信用卡号。VISA 信用卡号具有 16 位数字。但是，这些数字可以编写以不同的方式，如 1111年-1111年--1111，1111年 1111年 1111年 1111，或 1111111111111111。

任何 16 数字的字符串不一定是信用卡号，可能是票证编号从帮助台系统或硬件的序列号。以告知信用卡号和条无不良后果的 16 位的数字字符串之间的差异，计算是执行 （校验和） 以确认号码与各种信用卡品牌从已知的模式匹配。

此外，还视为为日期值可能会信用卡到期日期，如"VISA"或"AMEX"以及邻近关键字的邻近性做出决策数据是否是信用卡号。

换句话说，DLP 有通常足够的智能识别电子邮件中的以下两个文本之间的差异：

- "可以您订购我新便携式计算机。使用-1111年-1111年-1111，到期 11 月 22 日，我 VISA 号码和估计的交货日期如果您有发送给我"。
- "我的便携式计算机序列号是 2222年 2222年 2222年 2222年并购 2010 年 11 月。顺便说一下，我差旅 visa 批准尚未？"

参考资料保留书签是介绍如何检测每种信息类型本[主题对敏感信息类型](what-the-sensitive-information-types-look-for.md)。

## <a name="where-to-start-with-data-loss-prevention"></a>从何处着手数据丢失防护

当数据泄露的风险不完全明显时，很难出其中完全首先应实施 DLP 工作。幸运的是，可以在"测试模式"，从而使您以衡量其有效性和准确性，然后再将其打开运行 DLP 策略。

可以通过 Exchange 管理员中心管理 Exchange Online 的 DLP 策略。但是，您可以配置通过安全性和合规性中心的所有工作负荷的 DLP 策略，因此我将使用的本文中的演示。安全性和合规性中心中，您会发现在**数据丢失防护**下的 DLP 策略 > **策略**。单击**创建策略**，以启动。

Office 365 提供的[DLP 策略模板](what-the-dlp-policy-templates-include.md)可用于创建 DLP 策略的区域。让我们假设您正在澳大利亚业务。您可以筛选策略模板显示仅与澳大利亚，相关的那些属于的财务、 医疗和运行状况和隐私的常规类别。

![选择国家或地区选项](media/DLP-create-test-tune-choose-country.png)

本演示我将选择澳大利亚个人可识别信息 (PII) 数据，其中包括澳大利亚税文件数 (TFN) 和驱动程序的许可证数量的信息类型。

![选项可选择一个策略模板](media/DLP-create-test-tune-choose-policy-template.png)

指定新 DLP 策略名称。默认名称将匹配 DLP 策略模板，但因为可以从同一模板创建多个策略，您应选择您自己的更具描述性名称。

![选项以命名您的策略](media/DLP-create-test-tune-name-policy.png)

选择该策略将应用到的位置。DLP 策略可应用于 Exchange Online、 SharePoint Online 和 OneDrive for Business 中。我要保留配置为将应用于所有位置此策略。

![选择所有位置选项](media/DLP-create-test-tune-choose-locations.png)

只的第一个**策略设置**步骤现在接受默认设置。自定义可在 DLP 策略中实现了很多，但默认值为开始的好地方。

![自定义要保护的内容类型的选项](media/DLP-create-test-tune-default-customization-settings.png)

单击**下一步**后您将看到与多个自定义选项的其他**策略设置**页。您刚要测试的策略，下面是您可以开始进行一些调整。

- 我已关闭的现在，这是合理的步骤，您只需您测试的内容，并且不希望尚未向用户显示任何内容时要执行的策略提示。策略提示向它们将要违反 DLP 策略的用户显示警告。例如，Outlook 用户将看到他们已附加的文件包含信用卡号的警告，并将导致其电子邮件被拒绝。策略提示的目标是发生之前停止不符合标准的行为。
- 我还已降低为 1，10 实例数，以便此策略将检测任何澳大利亚 PII 数据共享，不只是批量数据的共享。
- 事件报告电子邮件还添加另一个收件人。

![其他策略设置](media/DLP-create-test-tune-more-policy-settings.png)

最后，已配置此策略，可最初在测试模式下运行。请注意还有一个选项以禁用在测试模式下的策略提示。这样，您可以具有的策略中, 启用的策略提示，但然后决定是显示还是隐藏它们在测试过程中的灵活性。

![首先检验策略选项](media/DLP-create-test-tune-test-mode.png)

最终评审屏幕上单击**创建**以完成策略创建。

## <a name="test-a-dlp-policy"></a>测试 DLP 策略

新 DLP 策略将开始内约为 1 小时才会生效。您可以 sit 并等待它触发由普通用户活动或您可以尝试自己触发。前面我链接到本[主题对敏感信息类型](what-the-sensitive-information-types-look-for.md)，其中提供了有关如何触发 DLP 匹配项的信息。

例如，本文中创建的 DLP 策略将检测澳大利亚税文件编号 (TFN)。本文档中，根据以下条件基于匹配项。

![澳大利亚税号上的文档](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
而是钝方式演示 TFN 检测，与单词"税号"电子邮件和接近 9 的数字字符串将 sail 通过毫无任何问题。它不会触发 DLP 策略的原因是 9 位数字字符串必须通过指示有效 TFN 并不只是条无不良后果数字字符串的校验和。

![澳大利亚税号，不传递校验和](media/DLP-create-test-tune-email-test1.png)

相比之下，与单词"税号"电子邮件和传递校验和有效 TFN 将触发策略。对于条记录，我使用的 TFN 拍摄从网站生成的有效的但不是正版，TFNs。有类似生成[有效但假信用卡号](http://www.fakecreditcardgenerator.net/)的网站。此类网站是非常有用，因为测试 DLP 策略时，最常见的错误之一使用假号码不是有效和不传递校验和 （并因此不会触发策略）。

![澳大利亚税号将传递校验和](media/DLP-create-test-tune-email-test2.png)

事件报告电子邮件包括的已检测到的敏感信息类型、 检测多少个实例，和检测的可信度。

![检测到事件报告显示税号](media/DLP-create-test-tune-email-incident-report.png)

如果在测试模式下保留 DLP 策略，并分析事件报告电子邮件，您可以开始体会 DLP 策略和如何有效它时将强制执行它的准确性。除了事件报告，您可以[使用 DLP 报告](view-the-dlp-reports.md)可以查看您的租户中的策略的匹配项的聚合的视图。

## <a name="tune-a-dlp-policy"></a>调整 DLP 策略

分析策略命中，您可能想要进行一些调整到策略的行为方式。作为一个简单示例，您可能决定电子邮件中的一个 TFN 不 （我认为仍为，但我们使用它为了演示） 问题，但两个或多个实例是问题。多个实例可能如员工通过电子邮件发送给第三方，例如外部会计服务从 HR 数据库 CSV 导出 risky 方案。肯定某些内容您想要检测和阻止。

安全性和合规性中心中，您可以编辑现有策略以调整行为。

![编辑策略选项](media/DLP-create-test-tune-edit-policy.png)
 
您可以调整位置设置，以便只对特定工作负载，或特定的网站和帐户应用策略。

![选择特定位置的选项](media/DLP-create-test-tune-edit-locations.png)

您还可以调整的策略设置和编辑您的需求的使其更适合的规则。

![编辑规则选项](media/DLP-create-test-tune-edit-rule.png)

编辑 DLP 策略中的规则时可以更改：

- 条件，包括类型和数量实例将触发规则的敏感数据。
- 如限制对内容的访问所采取的操作。
- 用户通知，会向用户在其电子邮件客户端或 web 浏览器中显示的策略提示。
- 用户重写，从而确定用户是否可以选择其电子邮件或文件共享仍然继续。
- 事件报告，以通知管理员。

![若要编辑的规则的部件的选项](media/DLP-create-test-tune-editing-options.png)

本演示我已将用户通知添加到策略中 （注意此操作没有足够的用户知识培训的），并允许用户能够替代策略与的业务理由或标记为误报。请注意，您还可以自定义电子邮件和策略提示文本是否您想要包括有关您组织的策略，任何其他信息或提示用户如果他们有问题与支持部门联系。

![用户通知和替代选项](media/DLP-create-test-tune-user-notifications.png)

策略包含两个规则的处理较大和音量太低，因此一定要编辑都具有所需的操作。这是将不同根据其特征的情况下有机会。例如，您可能允许音量太低冲突的覆盖，但不是允许覆盖的较大冲突。

![一个规则高容量和一个规则音量太低](media/DLP-create-test-tune-two-rules.png)

此外，如果您想要实际阻止或限制对违反了策略中的内容的访问，您需要配置规则这样的操作。

![选项可限制对内容的访问](media/DLP-create-test-tune-restrict-access-action.png)

将这些更改保存对策略设置后，我还需要将返回到主设置页上的策略，并启用在测试模式下策略时向用户显示策略提示的选项。这是有效地向最终用户中, 引入 DLP 策略和执行用户知识培训，而不会影响其工作效率的太多误报面临的风险。

![选项，可以在测试模式下显示策略提示](media/DLP-create-test-tune-show-policy-tips.png)

在服务器端 （或云端如果您更喜欢） 更改可能不会立即生效，由于各种处理间隔。如果您要发起将向用户显示新的策略提示的 DLP 策略更改，用户可能无法看到更改在其 Outlook 客户端，每 24 小时检查策略更改会立即生效。如果您希望测试的速度以为，可以使用此注册表固定到[清除从 PolicyNudges 项的上次下载时间戳](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。Outlook 将下载的最新的策略信息下次您重新启动它并开始撰写电子邮件。

如果必须启用的策略提示，用户将开始，请参阅在 Outlook 中的提示，并且可以发生时向您报告误报。

![带有报告误报选项的策略提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>调查误报

DLP 策略模板不直接现成完美。很可能您会发现出现在环境中，这是非常重要，以便您能够简化 DLP 部署到的原因，某些误报花时间充分测试和优化您的策略。

下面是误报的一个示例。非常条无不良后果此电子邮件。用户是向某人，提供其移动电话号码，包括其电子邮件签名。

![显示 false 正信息的电子邮件](media/DLP-create-test-tune-false-positive-email.png)
 
用户看到策略提示警告电子邮件包含敏感信息，但具体而言，澳大利亚驾驶证号码。

![报表中策略提示误报选项](media/DLP-create-test-tune-policy-tip-closeup.png)

用户可以报告为误报，以及管理员可以查看到在发生的原因。在事件报告电子邮件，则该电子邮件被标记为误报。

![事件报告显示误报](media/DLP-create-test-tune-false-positive-incident-report.png)

此驱动程序的许可情况是一个很好的示例细化。此误报内出现了这是任何 9 位数字字符串 （甚至是一种是 10 位数字字符串的一部分），将触发类型的"澳大利亚驾驶证许可证"300 个字符的关键字"悉尼 nsw"接近的原因 （不区分大小写）。以便它时触发的电话号码和电子邮件签名，只是因为用户碰巧悉尼中。

有趣的是，如果"悉尼，NSW"有逗号，则不会触发 DLP 策略。我也不知道为什么逗号将此处的任何差异也为什么中的关键字澳大利亚驱动程序的许可证信息类型，不包含其他城市 （英文） 和状态澳大利亚中的但存在您转。因此，我们如何有关该产品？没有几个选项。

一种选择是从策略中删除澳大利亚驱动程序的许可证信息类型。它是在那里因为它是一部分的 DLP 策略模板，但我们不强制使用它。如果您仅感兴趣税费文件编号和不驱动程序的许可证，您可以只删除它。例如，您可以从音量太低规则在策略，将其删除，但保留在高容量规则，以便仍然检测到多个驱动因素许可证的列表。

![选项以删除规则的敏感信息类型](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
另一个选项是简单地增加实例计数，以便在多个实例时，仅检测到低的驱动程序的许可证数量。

![编辑实例计数选项](media/DLP-create-test-tune-edit-instance-count.png)

除了更改实例计数，还可以调整匹配准确性 （或可信度）。如果您的敏感信息类型有多个模式，您可以在规则中，调整匹配准确性，以便您规则匹配特定的模式。例如，为了帮助减少误报，可以设置规则匹配准确性，使其匹配仅具有最高可信度级别的模式。了解如何计算可信度有点复杂 （及其他认证实战这篇文章的作用域），但下面是有关[如何使用可信度将规则调整](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的良好说明。

最后，如果您想要获取甚至更多高级，您可以自定义任何敏感信息类型 — 例如，您可以从[澳大利亚驾驶证许可证](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)，以消除误报触发上方的关键字列表中删除"悉尼 NSW"。若要了解如何使用 XML 和 PowerShell 执行此操作，请参阅[自定义内置的敏感信息类型](customize-a-built-in-sensitive-information-type.md)上的本主题。

## <a name="turn-off-a-dlp-policy"></a>禁用 DLP 策略

当您对感到满意 DLP 策略是准确和有效地检测敏感信息类型，并且您的最终用户准备处理正在就地的策略，然后您可以启用此策略。

![选项以启用策略](media/DLP-create-test-tune-turn-on-policy.png)
 
如果您正在等待批准，以查看策略将才会生效，[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)并运行[Get DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)以查看 DistributionStatus 时。

![在 PowerShell 中运行 cmdlet](media/DLP-create-test-tune-PowerShell.png)

后打开 DLP 策略，您应运行一些最终测试您自己进行的确保正在进行的预期的策略操作。如果您正在尝试测试等信用卡数据，有网站 online 与如何生成示例信用卡信息或其他个人信息的将传递校验和并触发您的策略。

允许用户重写的策略将向该选项用户显示策略提示的一部分。

![允许用户替代的策略提示](media/DLP-create-test-tune-override-option.png)

限制内容的策略将作为一部分的策略提示，向用户显示警告和防止它们发送电子邮件。

![策略提示的内容被限制](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>摘要

数据丢失预防策略可用于所有类型的组织。测试一些 DLP 策略是由于对等策略提示、 最终用户替代和事件报告的控制低风险练习。以安静模式可以测试一些 DLP 策略，以查看在组织中的已发生冲突的类型，然后制作出策略与低 false 正率，告知用户在什么是允许和不允许，然后推出到您的 DLP 策略组织。
