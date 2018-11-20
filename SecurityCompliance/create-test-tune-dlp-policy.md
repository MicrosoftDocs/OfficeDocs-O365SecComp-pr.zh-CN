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
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="f8de1-103">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f8de1-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="f8de1-104">**主体作者**</span><span class="sxs-lookup"><span data-stu-id="f8de1-104">**Principal author**</span></span> </br>
<span data-ttu-id="f8de1-105">Paul Cunningham，Microsoft MVP</span><span class="sxs-lookup"><span data-stu-id="f8de1-105">Paul Cunningham, Microsoft MVP</span></span> </br>
[<span data-ttu-id="f8de1-106">实践 365</span><span class="sxs-lookup"><span data-stu-id="f8de1-106">Practical 365</span></span>](https://practical365.com/) </br>
[<span data-ttu-id="f8de1-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="f8de1-107">@Practical365</span></span>](https://twitter.com/practical365)</br>
__________________________________________________

<span data-ttu-id="f8de1-p101">数据丢失防护是旨在帮助防止有意或无意公开的敏感信息不需要方贵组织的 Office 365 合规性功能。DLP 具有其根中 Exchange Server 和 Exchange Online 中，并且还适用于 SharePoint Online 和 OneDrive for Business。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p101">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties. DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="f8de1-p102">DLP 使用内容分析引擎来检查电子邮件和文件的内容，寻找敏感信息，如信用卡号和个人身份信息 (PII)。敏感信息通常不应发送电子邮件，或包含在文档中，不采用如加密电子邮件或文件的其他步骤。使用 DLP 可以检测敏感信息，并执行操作，例如：</span><span class="sxs-lookup"><span data-stu-id="f8de1-p102">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII). Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files. Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="f8de1-113">登录不但的事件</span><span class="sxs-lookup"><span data-stu-id="f8de1-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="f8de1-114">向最终用户正在发送电子邮件或共享文件显示警告</span><span class="sxs-lookup"><span data-stu-id="f8de1-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="f8de1-115">主动阻止电子邮件或文件共享从正在进行</span><span class="sxs-lookup"><span data-stu-id="f8de1-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="f8de1-p103">有时客户消除 DLP，因为它们不考虑具有需要保护的数据的类型。假设是敏感数据，如医疗记录或财务信息仅存在类似医疗行业或运行联机存储的公司。但任何业务可处理定期，敏感信息，即使它们不实现它。员工名称的电子表格和出生日期是作为客户名称和信用卡详细信息的电子表格只需为敏感。和此类信息倾向于 float 周围的详细信息比您预想，如员工安静安装转有关其一天的任务，思考 nothing 导出 CSV 文件从系统，并向某人发送该电子邮件。您也可能是惊讶频率员工发送电子邮件，而不考虑后果包含信用卡或银行业详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p103">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting. The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores. But any business can handle sensitive information on a regular basis, even if they don't realize it. A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details. And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone. You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="f8de1-122">如何检测到的 DLP 敏感信息</span><span class="sxs-lookup"><span data-stu-id="f8de1-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="f8de1-p104">由正则表达式 (RegEx) 模式匹配，结合使用如邻近其他指标的特定关键字匹配模式与标识敏感信息。此示例是信用卡号。VISA 信用卡号具有 16 位数字。但是，这些数字可以编写以不同的方式，如 1111年-1111年--1111，1111年 1111年 1111年 1111，或 1111111111111111。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p104">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns. An example of this is credit card numbers. A VISA credit card number has 16 digits. However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="f8de1-p105">任何 16 数字的字符串不一定是信用卡号，可能是票证编号从帮助台系统或硬件的序列号。以告知信用卡号和条无不良后果的 16 位的数字字符串之间的差异，计算是执行 （校验和） 以确认号码与各种信用卡品牌从已知的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p105">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware. To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="f8de1-129">此外，还视为为日期值可能会信用卡到期日期，如"VISA"或"AMEX"以及邻近关键字的邻近性做出决策数据是否是信用卡号。</span><span class="sxs-lookup"><span data-stu-id="f8de1-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="f8de1-130">换句话说，DLP 有通常足够的智能识别电子邮件中的以下两个文本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="f8de1-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="f8de1-p106">"可以您订购我新便携式计算机。使用-1111年-1111年-1111，到期 11 月 22 日，我 VISA 号码和估计的交货日期如果您有发送给我"。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p106">“Can you order me a new laptop. Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="f8de1-p107">"我的便携式计算机序列号是 2222年 2222年 2222年 2222年并购 2010 年 11 月。顺便说一下，我差旅 visa 批准尚未？"</span><span class="sxs-lookup"><span data-stu-id="f8de1-p107">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010. By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="f8de1-135">参考资料保留书签是介绍如何检测每种信息类型本[主题对敏感信息类型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="f8de1-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="f8de1-136">从何处着手数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="f8de1-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="f8de1-p108">当数据泄露的风险不完全明显时，很难出其中完全首先应实施 DLP 工作。幸运的是，可以在"测试模式"，从而使您以衡量其有效性和准确性，然后再将其打开运行 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p108">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP. Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="f8de1-p109">可以通过 Exchange 管理员中心管理 Exchange Online 的 DLP 策略。但是，您可以配置通过安全性和合规性中心的所有工作负荷的 DLP 策略，因此我将使用的本文中的演示。安全性和合规性中心中，您会发现在**数据丢失防护**下的 DLP 策略 > **策略**。单击**创建策略**，以启动。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p109">DLP policies for Exchange Online can be managed through the Exchange admin center. But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article. In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**. Click on **Create a policy** to start.</span></span>

<span data-ttu-id="f8de1-p110">Office 365 提供的[DLP 策略模板](what-the-dlp-policy-templates-include.md)可用于创建 DLP 策略的区域。让我们假设您正在澳大利亚业务。您可以筛选策略模板显示仅与澳大利亚，相关的那些属于的财务、 医疗和运行状况和隐私的常规类别。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p110">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies. Let's say that you're an Australian business. You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![选择国家或地区选项](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="f8de1-147">本演示我将选择澳大利亚个人可识别信息 (PII) 数据，其中包括澳大利亚税文件数 (TFN) 和驱动程序的许可证数量的信息类型。</span><span class="sxs-lookup"><span data-stu-id="f8de1-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![选项可选择一个策略模板](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="f8de1-p111">指定新 DLP 策略名称。默认名称将匹配 DLP 策略模板，但因为可以从同一模板创建多个策略，您应选择您自己的更具描述性名称。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p111">Give your new DLP policy a name. The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![选项以命名您的策略](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="f8de1-p112">选择该策略将应用到的位置。DLP 策略可应用于 Exchange Online、 SharePoint Online 和 OneDrive for Business 中。我要保留配置为将应用于所有位置此策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p112">Choose the locations that the policy will apply to. DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business. I am going to leave this policy configured to apply to all locations.</span></span>

![选择所有位置选项](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="f8de1-p113">只的第一个**策略设置**步骤现在接受默认设置。自定义可在 DLP 策略中实现了很多，但默认值为开始的好地方。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p113">At the first **Policy Settings** step just accept the defaults for now. There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![自定义要保护的内容类型的选项](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="f8de1-p114">单击**下一步**后您将看到与多个自定义选项的其他**策略设置**页。您刚要测试的策略，下面是您可以开始进行一些调整。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p114">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options. For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="f8de1-p115">我已关闭的现在，这是合理的步骤，您只需您测试的内容，并且不希望尚未向用户显示任何内容时要执行的策略提示。策略提示向它们将要违反 DLP 策略的用户显示警告。例如，Outlook 用户将看到他们已附加的文件包含信用卡号的警告，并将导致其电子邮件被拒绝。策略提示的目标是发生之前停止不符合标准的行为。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p115">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet. Policy tips display warnings to users that they're about to violate a DLP policy. For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected. The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="f8de1-165">我还已降低为 1，10 实例数，以便此策略将检测任何澳大利亚 PII 数据共享，不只是批量数据的共享。</span><span class="sxs-lookup"><span data-stu-id="f8de1-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="f8de1-166">事件报告电子邮件还添加另一个收件人。</span><span class="sxs-lookup"><span data-stu-id="f8de1-166">I've also added another recipient to the incident report email.</span></span>

![其他策略设置](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="f8de1-p116">最后，已配置此策略，可最初在测试模式下运行。请注意还有一个选项以禁用在测试模式下的策略提示。这样，您可以具有的策略中, 启用的策略提示，但然后决定是显示还是隐藏它们在测试过程中的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p116">Finally, I've configured this policy to run in test mode initially. Notice there's also an option here to disable policy tips while in test mode. This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![首先检验策略选项](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="f8de1-172">最终评审屏幕上单击**创建**以完成策略创建。</span><span class="sxs-lookup"><span data-stu-id="f8de1-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="f8de1-173">测试 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f8de1-173">Test a DLP policy</span></span>

<span data-ttu-id="f8de1-p117">新 DLP 策略将开始内约为 1 小时才会生效。您可以 sit 并等待它触发由普通用户活动或您可以尝试自己触发。前面我链接到本[主题对敏感信息类型](what-the-sensitive-information-types-look-for.md)，其中提供了有关如何触发 DLP 匹配项的信息。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p117">Your new DLP policy will begin to take effect within about 1 hour. You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself. Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="f8de1-p118">例如，本文中创建的 DLP 策略将检测澳大利亚税文件编号 (TFN)。本文档中，根据以下条件基于匹配项。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p118">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN). According to the documentation, the match is based on the following criteria.</span></span>

![澳大利亚税号上的文档](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="f8de1-p119">而是钝方式演示 TFN 检测，与单词"税号"电子邮件和接近 9 的数字字符串将 sail 通过毫无任何问题。它不会触发 DLP 策略的原因是 9 位数字字符串必须通过指示有效 TFN 并不只是条无不良后果数字字符串的校验和。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p119">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues. The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![澳大利亚税号，不传递校验和](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="f8de1-p120">相比之下，与单词"税号"电子邮件和传递校验和有效 TFN 将触发策略。对于条记录，我使用的 TFN 拍摄从网站生成的有效的但不是正版，TFNs。有类似生成[有效但假信用卡号](http://www.fakecreditcardgenerator.net/)的网站。此类网站是非常有用，因为测试 DLP 策略时，最常见的错误之一使用假号码不是有效和不传递校验和 （并因此不会触发策略）。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p120">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy. For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs. There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/). Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![澳大利亚税号将传递校验和](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="f8de1-188">事件报告电子邮件包括的已检测到的敏感信息类型、 检测多少个实例，和检测的可信度。</span><span class="sxs-lookup"><span data-stu-id="f8de1-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![检测到事件报告显示税号](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="f8de1-p121">如果在测试模式下保留 DLP 策略，并分析事件报告电子邮件，您可以开始体会 DLP 策略和如何有效它时将强制执行它的准确性。除了事件报告，您可以[使用 DLP 报告](view-the-dlp-reports.md)可以查看您的租户中的策略的匹配项的聚合的视图。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p121">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced. In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="f8de1-192">调整 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f8de1-192">Tune a DLP policy</span></span>

<span data-ttu-id="f8de1-p122">分析策略命中，您可能想要进行一些调整到策略的行为方式。作为一个简单示例，您可能决定电子邮件中的一个 TFN 不 （我认为仍为，但我们使用它为了演示） 问题，但两个或多个实例是问题。多个实例可能如员工通过电子邮件发送给第三方，例如外部会计服务从 HR 数据库 CSV 导出 risky 方案。肯定某些内容您想要检测和阻止。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p122">As you analyze your policy hits you might want to make some adjustments to how the policies behave. As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem. Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service. Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="f8de1-197">安全性和合规性中心中，您可以编辑现有策略以调整行为。</span><span class="sxs-lookup"><span data-stu-id="f8de1-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![编辑策略选项](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="f8de1-199">您可以调整位置设置，以便只对特定工作负载，或特定的网站和帐户应用策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![选择特定位置的选项](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="f8de1-201">您还可以调整的策略设置和编辑您的需求的使其更适合的规则。</span><span class="sxs-lookup"><span data-stu-id="f8de1-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![编辑规则选项](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="f8de1-203">编辑 DLP 策略中的规则时可以更改：</span><span class="sxs-lookup"><span data-stu-id="f8de1-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="f8de1-204">条件，包括类型和数量实例将触发规则的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="f8de1-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="f8de1-205">如限制对内容的访问所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="f8de1-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="f8de1-206">用户通知，会向用户在其电子邮件客户端或 web 浏览器中显示的策略提示。</span><span class="sxs-lookup"><span data-stu-id="f8de1-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="f8de1-207">用户重写，从而确定用户是否可以选择其电子邮件或文件共享仍然继续。</span><span class="sxs-lookup"><span data-stu-id="f8de1-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="f8de1-208">事件报告，以通知管理员。</span><span class="sxs-lookup"><span data-stu-id="f8de1-208">Incident reports, to notify administrators.</span></span>

![若要编辑的规则的部件的选项](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="f8de1-p123">本演示我已将用户通知添加到策略中 （注意此操作没有足够的用户知识培训的），并允许用户能够替代策略与的业务理由或标记为误报。请注意，您还可以自定义电子邮件和策略提示文本是否您想要包括有关您组织的策略，任何其他信息或提示用户如果他们有问题与支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p123">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive. Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![用户通知和替代选项](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="f8de1-p124">策略包含两个规则的处理较大和音量太低，因此一定要编辑都具有所需的操作。这是将不同根据其特征的情况下有机会。例如，您可能允许音量太低冲突的覆盖，但不是允许覆盖的较大冲突。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p124">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want. This is an opportunity to treat cases differently depending on their characteristics. For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![一个规则高容量和一个规则音量太低](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="f8de1-217">此外，如果您想要实际阻止或限制对违反了策略中的内容的访问，您需要配置规则这样的操作。</span><span class="sxs-lookup"><span data-stu-id="f8de1-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![选项可限制对内容的访问](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="f8de1-p125">将这些更改保存对策略设置后，我还需要将返回到主设置页上的策略，并启用在测试模式下策略时向用户显示策略提示的选项。这是有效地向最终用户中, 引入 DLP 策略和执行用户知识培训，而不会影响其工作效率的太多误报面临的风险。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p125">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode. This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![选项，可以在测试模式下显示策略提示](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="f8de1-p126">在服务器端 （或云端如果您更喜欢） 更改可能不会立即生效，由于各种处理间隔。如果您要发起将向用户显示新的策略提示的 DLP 策略更改，用户可能无法看到更改在其 Outlook 客户端，每 24 小时检查策略更改会立即生效。如果您希望测试的速度以为，可以使用此注册表固定到[清除从 PolicyNudges 项的上次下载时间戳](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。Outlook 将下载的最新的策略信息下次您重新启动它并开始撰写电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p126">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals. If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours. If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="f8de1-226">如果必须启用的策略提示，用户将开始，请参阅在 Outlook 中的提示，并且可以发生时向您报告误报。</span><span class="sxs-lookup"><span data-stu-id="f8de1-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![带有报告误报选项的策略提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="f8de1-228">调查误报</span><span class="sxs-lookup"><span data-stu-id="f8de1-228">Investigate false positives</span></span>

<span data-ttu-id="f8de1-p127">DLP 策略模板不直接现成完美。很可能您会发现出现在环境中，这是非常重要，以便您能够简化 DLP 部署到的原因，某些误报花时间充分测试和优化您的策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p127">DLP policy templates are not perfect straight out of the box. It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="f8de1-p128">下面是误报的一个示例。非常条无不良后果此电子邮件。用户是向某人，提供其移动电话号码，包括其电子邮件签名。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p128">Here's an example of a false positive. This email is quite harmless. The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![显示 false 正信息的电子邮件](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="f8de1-235">用户看到策略提示警告电子邮件包含敏感信息，但具体而言，澳大利亚驾驶证号码。</span><span class="sxs-lookup"><span data-stu-id="f8de1-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![报表中策略提示误报选项](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="f8de1-p129">用户可以报告为误报，以及管理员可以查看到在发生的原因。在事件报告电子邮件，则该电子邮件被标记为误报。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p129">The user can report the false positive, and the administrator can look into why it has occurred. In the incident report email, the email is flagged as a false positive.</span></span>

![事件报告显示误报](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="f8de1-p130">此驱动程序的许可情况是一个很好的示例细化。此误报内出现了这是任何 9 位数字字符串 （甚至是一种是 10 位数字字符串的一部分），将触发类型的"澳大利亚驾驶证许可证"300 个字符的关键字"悉尼 nsw"接近的原因 （不区分大小写）。以便它时触发的电话号码和电子邮件签名，只是因为用户碰巧悉尼中。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p130">This driver's license case is a good example to dig into. The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive). So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="f8de1-p131">有趣的是，如果"悉尼，NSW"有逗号，则不会触发 DLP 策略。我也不知道为什么逗号将此处的任何差异也为什么中的关键字澳大利亚驱动程序的许可证信息类型，不包含其他城市 （英文） 和状态澳大利亚中的但存在您转。因此，我们如何有关该产品？没有几个选项。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p131">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered. I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go. So, what can we do about it? There's a couple of options.</span></span>

<span data-ttu-id="f8de1-p132">一种选择是从策略中删除澳大利亚驱动程序的许可证信息类型。它是在那里因为它是一部分的 DLP 策略模板，但我们不强制使用它。如果您仅感兴趣税费文件编号和不驱动程序的许可证，您可以只删除它。例如，您可以从音量太低规则在策略，将其删除，但保留在高容量规则，以便仍然检测到多个驱动因素许可证的列表。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p132">One option is to remove the Australian driver's license information type from the policy. It's in there because it's part of the DLP policy template, but we're not forced to use it. If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it. For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![选项以删除规则的敏感信息类型](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="f8de1-252">另一个选项是简单地增加实例计数，以便在多个实例时，仅检测到低的驱动程序的许可证数量。</span><span class="sxs-lookup"><span data-stu-id="f8de1-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![编辑实例计数选项](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="f8de1-p133">除了更改实例计数，还可以调整匹配准确性 （或可信度）。如果您的敏感信息类型有多个模式，您可以在规则中，调整匹配准确性，以便您规则匹配特定的模式。例如，为了帮助减少误报，可以设置规则匹配准确性，使其匹配仅具有最高可信度级别的模式。了解如何计算可信度有点复杂 （及其他认证实战这篇文章的作用域），但下面是有关[如何使用可信度将规则调整](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的良好说明。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p133">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level). If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns. For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level. Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).</span></span>

<span data-ttu-id="f8de1-p134">最后，如果您想要获取甚至更多高级，您可以自定义任何敏感信息类型 — 例如，您可以从[澳大利亚驾驶证许可证](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)，以消除误报触发上方的关键字列表中删除"悉尼 NSW"。若要了解如何使用 XML 和 PowerShell 执行此操作，请参阅[自定义内置的敏感信息类型](customize-a-built-in-sensitive-information-type.md)上的本主题。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p134">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), to eliminate the false positive triggered above. To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="f8de1-260">禁用 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="f8de1-260">Turn off a DLP policy</span></span>

<span data-ttu-id="f8de1-261">当您对感到满意 DLP 策略是准确和有效地检测敏感信息类型，并且您的最终用户准备处理正在就地的策略，然后您可以启用此策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![选项以启用策略](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="f8de1-263">如果您正在等待批准，以查看策略将才会生效，[连接到 Office 365 安全性和合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)并运行[Get DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)以查看 DistributionStatus 时。</span><span class="sxs-lookup"><span data-stu-id="f8de1-263">If you're waiting to see when the policy will take effect, [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中运行 cmdlet](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="f8de1-p135">后打开 DLP 策略，您应运行一些最终测试您自己进行的确保正在进行的预期的策略操作。如果您正在尝试测试等信用卡数据，有网站 online 与如何生成示例信用卡信息或其他个人信息的将传递校验和并触发您的策略。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p135">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring. If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="f8de1-267">允许用户重写的策略将向该选项用户显示策略提示的一部分。</span><span class="sxs-lookup"><span data-stu-id="f8de1-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允许用户替代的策略提示](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="f8de1-269">限制内容的策略将作为一部分的策略提示，向用户显示警告和防止它们发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f8de1-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![策略提示的内容被限制](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="f8de1-271">摘要</span><span class="sxs-lookup"><span data-stu-id="f8de1-271">Summary</span></span>

<span data-ttu-id="f8de1-p136">数据丢失预防策略可用于所有类型的组织。测试一些 DLP 策略是由于对等策略提示、 最终用户替代和事件报告的控制低风险练习。以安静模式可以测试一些 DLP 策略，以查看在组织中的已发生冲突的类型，然后制作出策略与低 false 正率，告知用户在什么是允许和不允许，然后推出到您的 DLP 策略组织。</span><span class="sxs-lookup"><span data-stu-id="f8de1-p136">Data loss prevention policies are useful for organizations of all types. Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports. You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
