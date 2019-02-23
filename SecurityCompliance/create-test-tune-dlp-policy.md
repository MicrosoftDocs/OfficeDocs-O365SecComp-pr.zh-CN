---
title: 创建、测试和优化 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '开始使用 DLP 策略的最简单、最常用的方法是使用 Office 365 中包含的模板之一。 '
ms.openlocfilehash: 14582a6507d271bc569aeb0c5456a662962d20a9
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223741"
---
# <a name="create-test-and-tune-a-dlp-policy"></a><span data-ttu-id="b869a-103">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="b869a-103">Create, test, and tune a DLP policy</span></span>

<span data-ttu-id="b869a-104">**主体作者**</span><span class="sxs-lookup"><span data-stu-id="b869a-104">**Principal author**</span></span> <br/>
<span data-ttu-id="b869a-105">Paul Cunningham, Microsoft MVP</span><span class="sxs-lookup"><span data-stu-id="b869a-105">Paul Cunningham, Microsoft MVP</span></span> <br/>
[<span data-ttu-id="b869a-106">实用365</span><span class="sxs-lookup"><span data-stu-id="b869a-106">Practical 365</span></span>](https://practical365.com/) <br/>
[<span data-ttu-id="b869a-107">@Practical365</span><span class="sxs-lookup"><span data-stu-id="b869a-107">@Practical365</span></span>](https://twitter.com/practical365)<br/>
__________________________________________________

<span data-ttu-id="b869a-p101">数据丢失防护是 Office 365 的一项合规性功能, 旨在帮助您的组织防止对不需要的敏感信息进行有意或无意的暴露。DLP 的根在 exchange Server 和 exchange online 中, 也适用于 SharePoint online 和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="b869a-p101">Data loss prevention is a compliance feature of Office 365 that is designed to help your organization prevent the intentional or accidental exposure of sensitive information to unwanted parties. DLP has its roots in Exchange Server and Exchange Online, and is also applicable in SharePoint Online and OneDrive for Business.</span></span>

<span data-ttu-id="b869a-p102">DLP 使用内容分析引擎检查电子邮件和文件的内容, 查找敏感信息, 如信用卡号和个人身份信息 (PII)。敏感信息通常不应通过电子邮件发送, 也不应包含在文档中, 而无需执行其他步骤, 如加密电子邮件或文件。使用 DLP 可以检测敏感信息, 并采取如下操作:</span><span class="sxs-lookup"><span data-stu-id="b869a-p102">DLP uses a content analysis engine to examine the contents of email messages and files, looking for sensitive information such as credit card numbers and personally identifiable information (PII). Sensitive information should typically not be sent in email, or included in documents, without taking additional steps such as encrypting the email message or files. Using DLP you can detect sensitive information, and take action such as:</span></span>

- <span data-ttu-id="b869a-113">记录事件的审核目的</span><span class="sxs-lookup"><span data-stu-id="b869a-113">Log the event for auditing purposes</span></span>
- <span data-ttu-id="b869a-114">向发送电子邮件或共享文件的最终用户显示警告</span><span class="sxs-lookup"><span data-stu-id="b869a-114">Display a warning to the end user who is sending the email or sharing the file</span></span>
- <span data-ttu-id="b869a-115">主动阻止电子邮件或文件共享发生</span><span class="sxs-lookup"><span data-stu-id="b869a-115">Actively block the email or file sharing from taking place</span></span>

<span data-ttu-id="b869a-p103">有时客户会关闭 DLP, 因为他们不会认为自己需要保护的数据类型。假定敏感数据 (例如医疗记录或财务信息) 仅适用于卫生保健行业或运行在线商店的公司。但任何企业都可以定期处理敏感信息, 即使他们不知道也是如此。员工姓名和出生日期的电子表格与客户名称和信用卡详细信息的电子表格一样敏感。此外, 这种类型的信息可能会像你预期的那样浮动, 因为员工不知不觉地转到日常任务, 而不考虑从系统中导出 CSV 文件并向某人发送电子邮件的任何内容。如果员工在不考虑结果的情况下发送包含信用卡或银行详细信息的电子邮件, 您可能还会感到吃惊。</span><span class="sxs-lookup"><span data-stu-id="b869a-p103">Sometimes customers dismiss DLP because they don't consider themselves to have the type of data that needs protecting. The assumption is that sensitive data, such as medical records or financial information, only exists for industries like health care or for companies that run online stores. But any business can handle sensitive information on a regular basis, even if they don't realize it. A spreadsheet of employee names and dates of birth is just as sensitive as a spreadsheet of customer names and credit card details. And this type of information tends to float around more than you might expect, as employees quietly go about their day to day tasks, thinking nothing of export a CSV file from a system and emailing it to someone. You might also be surprised how often employees send emails containing credit card or banking details without considering the consequences.</span></span>

## <a name="how-sensitive-information-is-detected-by-dlp"></a><span data-ttu-id="b869a-122">DLP 如何检测敏感信息</span><span class="sxs-lookup"><span data-stu-id="b869a-122">How sensitive information is detected by DLP</span></span>

<span data-ttu-id="b869a-p104">敏感信息由正则表达式 (RegEx) 模式匹配标识, 并与其他指示符 (如特定关键字与匹配模式的接近程度) 相结合。这是信用卡号的一个示例。签证信用卡号有16位数字。但是, 可以用不同的方式 (例如, 1111-1111-1111-1111、1111 1111 1111 1111 或 1111111111111111) 编写这些数字。</span><span class="sxs-lookup"><span data-stu-id="b869a-p104">Sensitive information is identified by regular expression (RegEx) pattern matching, in combination with with other indicators such as the proximity of certain keywords to the matching patterns. An example of this is credit card numbers. A VISA credit card number has 16 digits. However, those digits can be written in different ways, such as 1111-1111-1111-1111, 1111 1111 1111 1111, or 1111111111111111.</span></span>

<span data-ttu-id="b869a-p105">任何16个数字字符串不一定是信用卡号, 它可以是来自技术支持系统的票证号, 也可以是一段硬件的序列号。若要说明信用卡号和无害的16位字符串之间的区别, 请执行计算 (校验和), 以确认这些号码与各种信用卡品牌中的已知模式相匹配。</span><span class="sxs-lookup"><span data-stu-id="b869a-p105">Any 16 digit string is not necessarily a credit card number, it could be a ticket number from a help desk system, or a serial number of a piece of hardware. To tell the difference between a credit card number and a harmless 16-digit string, a calculation is performed (checksum) to confirm that the numbers match a known pattern from the various credit card brands.</span></span>

<span data-ttu-id="b869a-129">此外, 关键字 (如 "签证" 或 "AMEX") 以及可能是信用卡到期日期的最接近日期值的临近也被认为是决定数据是否是信用卡号的决定。</span><span class="sxs-lookup"><span data-stu-id="b869a-129">Furthermore, the proximity of keywords such as “VISA” or “AMEX”, along with the proximity to date values that might be the credit card expiry date, is also considered to make a decision about whether the data is a credit card number or not.</span></span>

<span data-ttu-id="b869a-130">换句话说, DLP 通常非常智能, 足以识别电子邮件中这两个文本之间的差异:</span><span class="sxs-lookup"><span data-stu-id="b869a-130">In other words, DLP is usually smart enough to recognize the difference between these two texts in an email:</span></span>

- <span data-ttu-id="b869a-p106">"可以定购我一个新的便携式计算机。使用我的签证号码 1111-1111-1111-1111, 到期日期为 11/22, 并在你拥有它时向我发送估计的交货日期。</span><span class="sxs-lookup"><span data-stu-id="b869a-p106">“Can you order me a new laptop. Use my VISA number 1111-1111-1111-1111, expiry 11/22, and send me the estimated delivery date when you have it.”</span></span>
- <span data-ttu-id="b869a-p107">"我的膝上型电脑序列号是 2222-2222-2222-2222, 它是在11/2010 购买的。顺便说, 我的出差签证是否已批准？ "</span><span class="sxs-lookup"><span data-stu-id="b869a-p107">“My laptop serial number is 2222-2222-2222-2222 and it was purchased on 11/2010. By the way, is my travel visa approved yet?”</span></span>

<span data-ttu-id="b869a-135">有关 "保持书签" 的一个很有用的参考是[关于敏感信息类型的主题, 这些信息类型](what-the-sensitive-information-types-look-for.md)解释了如何检测每种信息类型。</span><span class="sxs-lookup"><span data-stu-id="b869a-135">A good reference to keep bookmarked is this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md) that explains how each information type is detected.</span></span>

## <a name="where-to-start-with-data-loss-prevention"></a><span data-ttu-id="b869a-136">从何处开始使用数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="b869a-136">Where to start with data loss prevention</span></span>

<span data-ttu-id="b869a-p108">如果数据泄露风险不是完全显而易见的, 则很难确切地使用实现 DLP 时应开始的情况。幸运的是, 可以在 "测试模式" 下运行 DLP 策略, 这样您就可以在将其转换为前评估其有效性和准确性。</span><span class="sxs-lookup"><span data-stu-id="b869a-p108">When the risks of data leakage aren't entirely obvious, it's difficult to work out where exactly you should start with implementing DLP. Fortunately, DLP policies can be run in “test mode”, allowing you to gauge their effectiveness and accuracy before you turn them on.</span></span>

<span data-ttu-id="b869a-p109">可以通过 exchange 管理中心管理 exchange Online 的 DLP 策略。但您可以通过 Security & 合规性中心为所有工作负载配置 DLP 策略, 因此, 我将在本文中使用此功能。在安全 & 合规性中心中, 你将在**数据丢失防护** > **策略**下找到 DLP 策略。单击 "**创建要启动的策略**"。</span><span class="sxs-lookup"><span data-stu-id="b869a-p109">DLP policies for Exchange Online can be managed through the Exchange admin center. But you can configure DLP policies for all workloads through the Security & Compliance Center, so that's what I'll use for demonstrations in this article. In the Security & Compliance Center you'll find the DLP policies under **Data loss prevention** > **Policy**. Click on **Create a policy** to start.</span></span>

<span data-ttu-id="b869a-p110">Office 365 提供了一系列可用于创建 dlp 策略的[dlp 策略模板](what-the-dlp-policy-templates-include.md)。假设你是澳大利亚的商业版。您可以筛选策略模板以仅显示与澳大利亚相关的人员, 这些模板属于财务、医疗和运行状况的一般类别和隐私。</span><span class="sxs-lookup"><span data-stu-id="b869a-p110">Office 365 provides a range of [DLP policy templates](what-the-dlp-policy-templates-include.md) you can use to create DLP policies. Let's say that you're an Australian business. You can filter the policy templates to display only those that are relevant to Australia, which fall into the general categories of Financial, Medical and Health, and Privacy.</span></span>

![选择国家或地区的选项](media/DLP-create-test-tune-choose-country.png)

<span data-ttu-id="b869a-147">在本演示中, 我将选择澳大利亚个人身份信息 (PII) 数据, 其中包括澳大利亚税收文件编号 (TFN) 和驾驶执照号码的信息类型。</span><span class="sxs-lookup"><span data-stu-id="b869a-147">For this demonstration I'll choose Australian Personally Identifiable Information (PII) Data, which includes the information types of Australian Tax File Number (TFN) and Driver's License Number.</span></span>

![选择策略模板的选项](media/DLP-create-test-tune-choose-policy-template.png)

<span data-ttu-id="b869a-p111">为新的 DLP 策略命名。默认名称将与 DLP 策略模板相匹配, 但您应选择一个更具描述性的名称, 因为可以从同一个模板中创建多个策略。</span><span class="sxs-lookup"><span data-stu-id="b869a-p111">Give your new DLP policy a name. The default name will match the DLP policy template, but you should choose a more descriptive name of your own, because multiple policies can be created from the same template.</span></span>

![用于命名策略的选项](media/DLP-create-test-tune-name-policy.png)

<span data-ttu-id="b869a-p112">选择策略将应用于的位置。DLP 策略可应用于 Exchange online、SharePoint online 和 OneDrive for business。我打算将此策略配置为应用于所有位置。</span><span class="sxs-lookup"><span data-stu-id="b869a-p112">Choose the locations that the policy will apply to. DLP policies can apply to Exchange Online, SharePoint Online, and OneDrive for Business. I am going to leave this policy configured to apply to all locations.</span></span>

![选择所有位置的选项](media/DLP-create-test-tune-choose-locations.png)

<span data-ttu-id="b869a-p113">在第一个 "**策略设置**" 步骤中, 只接受 "现在" 的默认值。您可以在 DLP 策略中进行大量的自定义, 但默认值是一个很好的启动位置。</span><span class="sxs-lookup"><span data-stu-id="b869a-p113">At the first **Policy Settings** step just accept the defaults for now. There is quite a lot of customization you can do in DLP policies, but the defaults are a fine place to start.</span></span>

![自定义要保护的内容类型的选项](media/DLP-create-test-tune-default-customization-settings.png)

<span data-ttu-id="b869a-p114">单击 "**下一步**" 后, 将显示其他具有更多自定义选项的**策略设置**页。对于您刚测试的策略, 可以从这里开始进行一些调整。</span><span class="sxs-lookup"><span data-stu-id="b869a-p114">After clicking **Next** you'll be presented with an additional **Policy Settings** page with more customization options. For a policy that you are just testing, here's where you can start to make some adjustments.</span></span>

- <span data-ttu-id="b869a-p115">我已经关闭了现在的策略提示, 如果只是在测试并不想向用户显示任何内容, 这是一项合理的步骤。策略提示向用户显示即将违反 DLP 策略的警告。例如, Outlook 用户将看到一条警告, 指出他们所附加的文件包含信用卡号码, 并将导致拒绝其电子邮件。策略提示的目标是在发生不兼容的行为之前将其停止。</span><span class="sxs-lookup"><span data-stu-id="b869a-p115">I've turned off policy tips for now, which is a reasonable step to take if you're just testing things out and don't want to display anything to users yet. Policy tips display warnings to users that they're about to violate a DLP policy. For example, an Outlook user will see a warning that the file they've attached contains credit card numbers and will cause their email to be rejected. The goal of policy tips is to stop the non-compliant behaviour before it happens.</span></span>
- <span data-ttu-id="b869a-165">我还将10的实例数从10减少到 1, 以便此策略将检测所有的澳大利亚 PII 数据共享, 而不只是批量共享数据。</span><span class="sxs-lookup"><span data-stu-id="b869a-165">I've also decreased the number of instances from 10 to 1, so that this policy will detect any sharing of Australian PII data, not just bulk sharing of the data.</span></span>
- <span data-ttu-id="b869a-166">我还向事件报告电子邮件添加了另一个收件人。</span><span class="sxs-lookup"><span data-stu-id="b869a-166">I've also added another recipient to the incident report email.</span></span>

![其他策略设置](media/DLP-create-test-tune-more-policy-settings.png)

<span data-ttu-id="b869a-p116">最后, 我已将此策略配置为先在测试模式下运行。请注意, 在下面的选项中, 还提供了在测试模式下禁用策略提示的选项。这使您可以灵活地在策略中启用策略提示, 但在测试过程中决定是显示还是隐藏它们。</span><span class="sxs-lookup"><span data-stu-id="b869a-p116">Finally, I've configured this policy to run in test mode initially. Notice there's also an option here to disable policy tips while in test mode. This gives you the flexibility to have policy tips enabled in the policy, but then decide whether to show or suppress them during your testing.</span></span>

![先测试策略的选项](media/DLP-create-test-tune-test-mode.png)

<span data-ttu-id="b869a-172">在最终审阅屏幕上, 单击 "**创建**" 以完成策略的创建。</span><span class="sxs-lookup"><span data-stu-id="b869a-172">On the final review screen click **Create** to finish creating the policy.</span></span>

## <a name="test-a-dlp-policy"></a><span data-ttu-id="b869a-173">测试 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="b869a-173">Test a DLP policy</span></span>

<span data-ttu-id="b869a-p117">新的 DLP 策略将在大约1小时内开始生效。可以坐下来等待, 等待正常的用户活动触发, 也可以尝试自己触发它。之前我已链接到有关[敏感信息类型](what-the-sensitive-information-types-look-for.md)的本主题, 其中提供了有关如何触发 DLP 匹配的信息。</span><span class="sxs-lookup"><span data-stu-id="b869a-p117">Your new DLP policy will begin to take effect within about 1 hour. You can sit and wait for it to be triggered by normal user activity, or you can try to trigger it yourself. Earlier I linked to this [topic on sensitive information types](what-the-sensitive-information-types-look-for.md), which provides you with information about how to trigger DLP matches.</span></span>

<span data-ttu-id="b869a-p118">例如, 我为本文创建的 DLP 策略将检测澳大利亚税文件编号 (TFN)。根据文档, 匹配项基于以下条件。</span><span class="sxs-lookup"><span data-stu-id="b869a-p118">As an example, the DLP policy I created for this article will detect Australian tax file numbers (TFN). According to the documentation, the match is based on the following criteria.</span></span>

![有关澳大利亚税文件编号的文档](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
<span data-ttu-id="b869a-p119">为了以一种不钝的方式展示 TFN 检测, 使用词语 "税收 file number" 和一个接近接近的9位字符串的电子邮件将 sail, 而不会出现任何问题。不触发 DLP 策略的原因是, 9 位数的字符串必须传递指示它是有效的 TFN 而不只是无害的数字字符串的校验和。</span><span class="sxs-lookup"><span data-stu-id="b869a-p119">To demonstrate TFN detection in a rather blunt manner, an email with the words “Tax file number” and a 9 digit string in close proximity will sail through without any issues. The reason it does not trigger the DLP policy is that the 9-digit string must pass the checksum that indicates it is a valid TFN and not just a harmless string of numbers.</span></span>

![不通过校验和的澳大利亚税收文件编号](media/DLP-create-test-tune-email-test1.png)

<span data-ttu-id="b869a-p120">相比之下, 带有 "税收 file number" 一词的电子邮件和传递校验和的有效 TFN 将触发该策略。对于此处的记录, 使用的 TFN 是从生成有效但不是正版的 TFNs 的网站获取的。有类似的网站生成[有效但假冒信用卡号](http://www.fakecreditcardgenerator.net/)。此类网站非常有用, 因为测试 DLP 策略时最常见的错误之一是使用无效的虚设号码, 而不会传递校验和 (因此不会触发策略)。</span><span class="sxs-lookup"><span data-stu-id="b869a-p120">In comparison, an email with the words “Tax file number” and a valid TFN that passes the checksum will trigger the policy. For the record here, the TFN I'm using was taken from a website that generates valid, but not genuine, TFNs. There are similar sites that generate [valid but fake credit card numbers](http://www.fakecreditcardgenerator.net/). Such sites are very useful because one of the most common mistakes when testing a DLP policy is using a fake number that's not valid and won't pass the checksum (and therefore won't trigger the policy).</span></span>

![传递校验和的澳大利亚税收文件编号](media/DLP-create-test-tune-email-test2.png)

<span data-ttu-id="b869a-188">事件报告电子邮件包括检测到的敏感信息类型、检测到的实例数以及检测的可信度。</span><span class="sxs-lookup"><span data-stu-id="b869a-188">The incident report email includes the type of sensitive information that was detected, how many instances were detected, and the confidence level of the detection.</span></span>

![显示了已检测到的税文件编号的事件报告](media/DLP-create-test-tune-email-incident-report.png)

<span data-ttu-id="b869a-p121">如果您将 DLP 策略保留在测试模式中并分析事件报告电子邮件, 则可以开始了解 DLP 策略的准确性以及强制实施它的效率。除了事件报告之外, 您还可以[使用 DLP 报告](view-the-dlp-reports.md)查看整个租户中策略匹配的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="b869a-p121">If you leave your DLP policy in test mode and analyze the incident report emails, you can start to get a feel for the accuracy of the DLP policy and how effective it will be when it is enforced. In addition to the incident reports, you can [use the DLP reports](view-the-dlp-reports.md) to see an aggregated view of policy matches across your tenant.</span></span>

## <a name="tune-a-dlp-policy"></a><span data-ttu-id="b869a-192">优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="b869a-192">Tune a DLP policy</span></span>

<span data-ttu-id="b869a-p122">在分析策略命中率时, 您可能希望对策略的行为方式进行一些调整。作为一个简单的示例, 您可以确定电子邮件中的一个 TFN 不是问题 (我认为它仍然是, 但为了便于演示, 我们可以使用它), 但两个或更多的实例是一个问题。多个实例可能是一种危险方案, 例如员工通过电子邮件将 CSV 导出从 HR 数据库发送到外部方, 例如外部会计服务。一定要检测并阻止的内容。</span><span class="sxs-lookup"><span data-stu-id="b869a-p122">As you analyze your policy hits you might want to make some adjustments to how the policies behave. As a simple example, you might determine that one TFN in email is not a problem (I think it still is, but let's go with it for the sake of demonstration), but two or more instances is a problem. Multiple instances could be a risky scenario such as an employee emailing a CSV export from the HR database to an external party, for example an external accounting service. Definitely something you would prefer to detect and block.</span></span>

<span data-ttu-id="b869a-197">在安全 & 合规性中心中, 可以编辑现有策略以调整行为。</span><span class="sxs-lookup"><span data-stu-id="b869a-197">In the Security & Compliance Center you can edit an existing policy to adjust the behaviour.</span></span>

![编辑策略的选项](media/DLP-create-test-tune-edit-policy.png)
 
<span data-ttu-id="b869a-199">您可以调整位置设置, 以便仅将策略应用于特定工作负载或特定网站和帐户。</span><span class="sxs-lookup"><span data-stu-id="b869a-199">You can adjust the location settings so that the policy is applied only to specific workloads, or to specific sites and accounts.</span></span>

![选择特定位置的选项](media/DLP-create-test-tune-edit-locations.png)

<span data-ttu-id="b869a-201">您还可以调整策略设置并编辑规则, 以更好地满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="b869a-201">You can also adjust the policy settings and edit the rules to better suit your needs.</span></span>

![编辑规则的选项](media/DLP-create-test-tune-edit-rule.png)

<span data-ttu-id="b869a-203">在 DLP 策略中编辑规则时, 您可以更改:</span><span class="sxs-lookup"><span data-stu-id="b869a-203">When editing a rule within a DLP policy you can change:</span></span>

- <span data-ttu-id="b869a-204">条件, 包括将触发规则的敏感数据的实例的类型和数量。</span><span class="sxs-lookup"><span data-stu-id="b869a-204">The conditions, including the type and number of instances of sensitive data that will trigger the rule.</span></span>
- <span data-ttu-id="b869a-205">执行的操作, 例如限制对内容的访问。</span><span class="sxs-lookup"><span data-stu-id="b869a-205">The actions that are taken, such as restricting access to the content.</span></span>
- <span data-ttu-id="b869a-206">用户通知, 这是在其电子邮件客户端或 web 浏览器中向用户显示的策略提示。</span><span class="sxs-lookup"><span data-stu-id="b869a-206">User notifications, which are policy tips that are displayed to the user in their email client or web browser.</span></span>
- <span data-ttu-id="b869a-207">用户覆盖, 用于确定用户是否可以选择继续进行电子邮件或文件共享。</span><span class="sxs-lookup"><span data-stu-id="b869a-207">User overrides, which determines whether users can choose to proceed with their email or file sharing anyway.</span></span>
- <span data-ttu-id="b869a-208">事件报告, 通知管理员。</span><span class="sxs-lookup"><span data-stu-id="b869a-208">Incident reports, to notify administrators.</span></span>

![编辑部分规则的选项](media/DLP-create-test-tune-editing-options.png)

<span data-ttu-id="b869a-p123">在本演示中, 我向策略添加了用户通知 (在没有充分的用户意识培训的情况下, 请注意这样做), 并允许用户通过业务理由或将其标记为误报来替代策略。请注意, 如果您想要包括有关组织策略的任何其他信息, 则还可以自定义电子邮件和策略提示文本, 如果有问题, 则提示用户联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="b869a-p123">For this demonstration I've added user notifications to the policy (be careful of doing this without adequate user awareness training), and allowed users to override the policy with a business justification or by flagging it as a false positive. Note that you can also customize the email and policy tip text if you want to include any additional information about your organization's policies, or prompt users to contact support if they have questions.</span></span>

![用户通知和覆盖的选项](media/DLP-create-test-tune-user-notifications.png)

<span data-ttu-id="b869a-p124">策略包含两个用于处理高容量和低音量的规则, 因此请务必使用所需的操作来编辑。这是根据其特征对事例进行不同处理的机会。例如, 您可能允许对较少的卷冲突 (但不允许对高批量冲突的重写) 进行重写。</span><span class="sxs-lookup"><span data-stu-id="b869a-p124">The policy contains two rules for handling of high volume and low volume, so be sure to edit both with the actions that you want. This is an opportunity to treat cases differently depending on their characteristics. For example, you might allow overrides for low volume violations, but not allow overrides for high volume violations.</span></span>

![对于高容量和低容量的规则, 一个规则](media/DLP-create-test-tune-two-rules.png)

<span data-ttu-id="b869a-217">此外, 如果要实际阻止或限制对违反策略的内容的访问权限, 则需要对规则配置操作以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b869a-217">Also, if you want to actually block or restrict access to content that is in violation of policy, you need to configure an action on the rule to do so.</span></span>

![限制对内容的访问权限的选项](media/DLP-create-test-tune-restrict-access-action.png)

<span data-ttu-id="b869a-p125">在将这些更改保存到策略设置后, 我还需要返回到策略的主设置页, 并启用在策略处于测试模式时向用户显示策略提示的选项。这是将 DLP 策略引入到最终用户并进行用户意识培训的有效方法, 而不会导致影响其工作效率的误报过多。</span><span class="sxs-lookup"><span data-stu-id="b869a-p125">After saving those changes to the policy settings, I also need to return to the main settings page for the policy and enable the option to show policy tips to users while the policy is in test mode. This is an effective way to introduce DLP policies to your end users, and do user awareness training, without risking too many false positives that impact their productivity.</span></span>

![在测试模式下显示策略提示的选项](media/DLP-create-test-tune-show-policy-tips.png)

<span data-ttu-id="b869a-p126">在服务器端 (如果需要, 则为云端) 上, 由于各种处理间隔, 更改可能不会立即生效。如果要进行 DLP 策略更改, 以向用户显示新的策略提示, 则用户可能看不到这些更改会立即在 Outlook 客户端中生效, 这将检查每24小时进行的策略更改。如果要加快测试速度, 可以使用此注册表修补程序[从 PolicyNudges 项中清除上次下载时间戳](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)。Outlook 将在您下次重新启动时下载最新的策略信息, 并开始撰写一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b869a-p126">On the server side (or cloud side if you prefer), the change may not take effect immediately, due to various processing intervals. If you're making a DLP policy change that will display new policy tips to a user, the user may not see the changes take effect immediately in their Outlook client, which checks for policy changes every 24 hours. If you want to speed things up for testing, you can use this registry fix to [clear the last download time stamp from the PolicyNudges key](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook will download the latest policy information the next time you restart it and begin composing an email message.</span></span>

<span data-ttu-id="b869a-226">如果启用了策略提示, 则用户将开始在 Outlook 中看到提示, 并且可以在发生时向您报告误报。</span><span class="sxs-lookup"><span data-stu-id="b869a-226">If you have policy tips enabled, the user will begin to see the tips in Outlook, and can report false positives to you when they occur.</span></span>

![带有报告误报的选项的策略提示](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a><span data-ttu-id="b869a-228">调查误报</span><span class="sxs-lookup"><span data-stu-id="b869a-228">Investigate false positives</span></span>

<span data-ttu-id="b869a-p127">DLP 策略模板不能完全直接从盒中得到。您可能会发现环境中出现误报, 这就是为什么要轻松实现 DLP 部署的重要原因, 这就是充分测试和调整策略的时间。</span><span class="sxs-lookup"><span data-stu-id="b869a-p127">DLP policy templates are not perfect straight out of the box. It's likely that you'll find some false positives occurring in your environment, which is why it's so important to ease your way into a DLP deployment, taking the time to adequately test and tune your policies.</span></span>

<span data-ttu-id="b869a-p128">下面是误报的一个示例。此电子邮件非常无害。用户向某人提供自己的移动电话号码, 并包括他们的电子邮件签名。</span><span class="sxs-lookup"><span data-stu-id="b869a-p128">Here's an example of a false positive. This email is quite harmless. The user is providing their mobile phone number to someone, and including their email signature.</span></span>

![显示误报信息的电子邮件](media/DLP-create-test-tune-false-positive-email.png)
 
<span data-ttu-id="b869a-235">但用户会看到策略提示警告他们, 电子邮件包含敏感信息, 尤其是澳大利亚驾驶执照号码。</span><span class="sxs-lookup"><span data-stu-id="b869a-235">But the user sees a policy tip warning them that the email contains sensitive information, specifically, an Australian driver's license number.</span></span>

![用于报告策略提示中误报的选项](media/DLP-create-test-tune-policy-tip-closeup.png)

<span data-ttu-id="b869a-p129">用户可以报告误报, 管理员可以查看它发生的原因。在事件报告电子邮件中, 将电子邮件标记为误报。</span><span class="sxs-lookup"><span data-stu-id="b869a-p129">The user can report the false positive, and the administrator can look into why it has occurred. In the incident report email, the email is flagged as a false positive.</span></span>

![显示误报的事件报告](media/DLP-create-test-tune-false-positive-incident-report.png)

<span data-ttu-id="b869a-p130">此驱动程序的许可证是深入研究的一个很有用的示例。出现这种误报的原因是, 在300个字符与关键字 "悉尼新南威尔士" (不区分大小写) 的任何9位数的字符串 (甚至是10个数字字符串的一部分) 中将触发 "澳大利亚 Driver License" 类型。因此, 它是由电话号码和电子邮件签名触发的, 仅因为用户在悉尼中的情况下。</span><span class="sxs-lookup"><span data-stu-id="b869a-p130">This driver's license case is a good example to dig into. The reason this false positive has occurred is that the “Australian Driver's License” type will be triggered by any 9-digit string (even one that is part of a 10-digit string), within 300 characters proximity to the keywords “sydney nsw” (not case sensitive). So it's triggered by the phone number and email signature, only because the user happens to be in Sydney.</span></span>

<span data-ttu-id="b869a-p131">有趣的是, 如果 "悉尼, 新南威尔士" 有一个逗号, 则不会触发 DLP 策略。我不知道为什么在这里使用逗号, 也不知道澳大利亚的其他城市和状态不包括在澳大利亚驾照的许可证信息类型的关键字中, 但你可以这样做。那么, 我们可以对它做些什么？有几个选项。</span><span class="sxs-lookup"><span data-stu-id="b869a-p131">Interestingly, if “Sydney, NSW” has a comma, the DLP policy is not triggered. I have no idea why a comma makes any difference here, nor why other cities and states in Australia aren't included in the keywords for the Australian driver's license information type, but there you go. So, what can we do about it? There's a couple of options.</span></span>

<span data-ttu-id="b869a-p132">一种方法是从策略中删除澳大利亚 driver 的许可证信息类型。由于它是 DLP 策略模板的一部分, 因此不会强制使用该模板。如果只对税文件号而不是驱动程序的许可证感兴趣, 则可以将其删除。例如, 您可以从策略中的 "低容量" 规则中删除它, 但将其保留在高容量规则中, 以便仍检测到多个驱动程序许可证的列表。</span><span class="sxs-lookup"><span data-stu-id="b869a-p132">One option is to remove the Australian driver's license information type from the policy. It's in there because it's part of the DLP policy template, but we're not forced to use it. If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it. For example, you can remove it from the low volume rule in the policy, but leave it in the high volume rule so that lists of multiple drivers licenses are still detected.</span></span>

![删除规则中的敏感信息类型的选项](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
<span data-ttu-id="b869a-252">另一种方法是简单地增加实例计数, 以便仅在有多个实例时, 才会检测到较小数量的驱动程序许可证。</span><span class="sxs-lookup"><span data-stu-id="b869a-252">Another option is to simply increase the instance count, so that a low volume of driver's licenses is only detected when there are multiple instances.</span></span>

![编辑实例计数的选项](media/DLP-create-test-tune-edit-instance-count.png)

<span data-ttu-id="b869a-p133">除了更改实例计数之外, 还可以调整匹配精度 (或置信度)。如果您的敏感信息类型有多种模式, 则可以调整规则中的匹配精度, 以便您的规则只匹配特定模式。例如, 若要帮助减少误报, 可以设置规则的匹配精度, 使其仅与具有最高可信度的模式相匹配。了解如何计算可信度是有点棘手的 (超出此文章的范围), 但下面是[有关如何使用可信度调整规则](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy)的一个很有用的说明。</span><span class="sxs-lookup"><span data-stu-id="b869a-p133">In addition to changing the instance count, you can also adjust the match accuracy (or confidence level). If your sensitive information type has multiple patterns, you can adjust the match accuracy in your rule, so that your rule matches only specific patterns. For example, to help reduce false positives, you can set the match accuracy of your rule so that it matches only the pattern with the highest confidence level. Understanding how confidence level is calculated is a bit tricky (and beyond the scope of this post), but here's a good explanation of [how to use confidence level to tune your rules](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies#match-accuracy).</span></span>

<span data-ttu-id="b869a-p134">最后, 如果您想要更多地获取更多的信息, 可以自定义任何敏感信息类型-例如, 可以从[澳大利亚驾照](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number)的关键字列表中删除 "悉尼新南威尔士", 以消除上述误报。若要了解如何使用 XML 和 PowerShell 执行此操作, 请参阅本主题关于[自定义内置的敏感信息类型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="b869a-p134">Finally, if you want to get even a bit more advanced, you can customize any sensitive information type -- for example, you can remove "Sydney NSW" from the list of keywords for [Australian Driver's License](https://docs.microsoft.com/en-us/office365/securitycompliance/what-the-sensitive-information-types-look-for#australia-drivers-license-number), to eliminate the false positive triggered above. To learn how to do this by using XML and PowerShell, see this topic on [customizing a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="b869a-260">禁用 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="b869a-260">Turn off a DLP policy</span></span>

<span data-ttu-id="b869a-261">当您感到您的 DLP 策略准确而有效地检测敏感信息类型, 并且最终用户准备好处理这些策略时, 您可以启用该策略。</span><span class="sxs-lookup"><span data-stu-id="b869a-261">When you're happy that your DLP policy is accurately and effectively detecting sensitive information types, and that your end users are ready to deal with the policies being in place, then you can enable the policy.</span></span>

![启用策略的选项](media/DLP-create-test-tune-turn-on-policy.png)
 
<span data-ttu-id="b869a-263">如果你正在等待查看策略将生效的时间, 请[连接到 Office 365 Security & 合规性中心 PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) , 并运行[DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps)以查看 DistributionStatus。</span><span class="sxs-lookup"><span data-stu-id="b869a-263">If you're waiting to see when the policy will take effect, [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) and run the [Get-DlpCompliancePolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) to see the DistributionStatus.</span></span>

![在 PowerShell 中运行 cmdlet](media/DLP-create-test-tune-PowerShell.png)

<span data-ttu-id="b869a-p135">打开 DLP 策略后, 您应运行自己的一些最终测试, 以确保预期的策略操作正在发生。如果你尝试测试信用卡数据之类的内容, 则会有一些网站联机, 其中包含有关如何生成示例信用卡或其他个人信息的信息, 这些信息将传递校验和并触发策略。</span><span class="sxs-lookup"><span data-stu-id="b869a-p135">After turning on the DLP policy, you should run some final tests of your own to make sure that the expected policy actions are occurring. If you're trying to test things like credit card data, there are websites online with information on how to generate sample credit card or other personal information that will pass checksums and trigger your policies.</span></span>

<span data-ttu-id="b869a-267">允许用户替代的策略将作为策略提示的一部分向用户显示该选项。</span><span class="sxs-lookup"><span data-stu-id="b869a-267">Policies that allow user overrides will present that option to the user as part of the policy tip.</span></span>

![允许用户替代的策略提示](media/DLP-create-test-tune-override-option.png)

<span data-ttu-id="b869a-269">限制内容的策略将以策略提示的一部分向用户显示警告, 并阻止他们发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b869a-269">Policies that restrict content will present the warning to the user as part of the policy tip, and prevent them from sending the email.</span></span>

![内容受限制的策略提示](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a><span data-ttu-id="b869a-271">摘要</span><span class="sxs-lookup"><span data-stu-id="b869a-271">Summary</span></span>

<span data-ttu-id="b869a-p136">数据丢失防护策略对于所有类型的组织都很有用。由于您对策略提示、最终用户覆盖和事件报告等的控制, 测试某些 DLP 策略是一个低风险的实践。您可以安静地测试一些 DLP 策略, 以查看组织中已发生的冲突类型, 然后使用较低的误报率手工创建策略, 向用户介绍允许和不允许的情况, 然后将 DLP 策略回滚到组织.</span><span class="sxs-lookup"><span data-stu-id="b869a-p136">Data loss prevention policies are useful for organizations of all types. Testing some DLP policies is a low risk exercise due to the control you have over things like policy tips, end user overrides, and incident reports. You can quietly test some DLP policies to see what type of violations are already occurring in your organization, and then craft policies with low false positive rates, educate your users on what is allowed and not allowed, and then roll out your DLP policies to the organization.</span></span>
