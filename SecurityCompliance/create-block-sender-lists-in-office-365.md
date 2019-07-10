---
title: 在 Office 365 中创建阻止发件人列表
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: 阻止发件人列表选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 传输规则 (Etr) 也称为邮件流规则。
ms.openlocfilehash: 861fa0e47980a6bc295672cf1e8e35954c6f1dfb
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599988"
---
# <a name="create-block-sender-lists-in-office-365"></a><span data-ttu-id="e12a0-103">在 Office 365 中创建阻止发件人列表</span><span class="sxs-lookup"><span data-stu-id="e12a0-103">Create block sender lists in Office 365</span></span>

<span data-ttu-id="e12a0-104">有时, 有必要阻止发件人发来的不需要的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e12a0-104">Sometimes it’s necessary to block unwanted email from senders.</span></span> <span data-ttu-id="e12a0-105">有几种方法可供选择。</span><span class="sxs-lookup"><span data-stu-id="e12a0-105">There are several methods available to choose from.</span></span> <span data-ttu-id="e12a0-106">这些选项包括 Outlook 阻止的发件人、反垃圾邮件发件人/域阻止列表、IP 阻止列表和 Exchange 传输规则 (Etr, 也称为邮件流规则)。</span><span class="sxs-lookup"><span data-stu-id="e12a0-106">These options include Outlook Blocked Senders, Anti-Spam Sender/Domain Block Lists, IP Block Lists, and Exchange Transport Rules (ETRs, which are also known as mail flow rules).</span></span>

> [!NOTE]
> <span data-ttu-id="e12a0-107">虽然可以使用组织阻止列表来解决漏报 (丢失的垃圾邮件), 但还应将那些候选人提交给 Microsoft 进行分析。</span><span class="sxs-lookup"><span data-stu-id="e12a0-107">While organization block lists can be used to address false negatives (missed spam), those candidates should also be submitted to Microsoft for analysis.</span></span> <span data-ttu-id="e12a0-108">使用阻止列表管理漏报会显著增加管理开销。</span><span class="sxs-lookup"><span data-stu-id="e12a0-108">Managing false negatives by using block lists significantly increases your administrative overhead.</span></span> <span data-ttu-id="e12a0-109">如果要使用阻止列表来实现此目的, 则在准备好时, 还需要保留将[垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)的文章。</span><span class="sxs-lookup"><span data-stu-id="e12a0-109">If you will use a block list for this purpose, you will need to also keep the article for [submitting spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/en-us/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), at the ready.</span></span>

<span data-ttu-id="e12a0-110">配置被阻止的发件人列表的适当方法取决于影响的范围。</span><span class="sxs-lookup"><span data-stu-id="e12a0-110">The proper method to configure blocked sender lists varies depending on the scope of the impact.</span></span> <span data-ttu-id="e12a0-111">对于单用户影响, 正确的解决方案可以是使用 Outlook 阻止的发件人, 但如果多个用户或所有用户受到影响, 则其他选项之一更合适。</span><span class="sxs-lookup"><span data-stu-id="e12a0-111">For single user impact, the right solution could be to use Outlook Blocked Senders, but if multiple users or all users are being impacted, one of the other options would be more appropriate.</span></span>

## <a name="options-from-least-to-broadest-scope"></a><span data-ttu-id="e12a0-112">从最小到最广泛的范围的选项</span><span class="sxs-lookup"><span data-stu-id="e12a0-112">Options from least to broadest scope</span></span>

<span data-ttu-id="e12a0-113">创建阻止列表时, 一定要根据影响的范围 (将影响多少人) 选择适当的方法, 以使其与阻止方法的广度相匹配。</span><span class="sxs-lookup"><span data-stu-id="e12a0-113">When creating a Block list it's important to pick the appropriate method based on the scope of the impact (how many people will be impacted), so that it matches the breadth of the blocking method.</span></span> <span data-ttu-id="e12a0-114">下面列出的选项按作用域和广度进行排序。</span><span class="sxs-lookup"><span data-stu-id="e12a0-114">The options listed below are ranked by both scope and breadth.</span></span> <span data-ttu-id="e12a0-115">列表从窄到范围, 但阅读完整建议的*细节*。</span><span class="sxs-lookup"><span data-stu-id="e12a0-115">The list goes from narrow to broad, but *read the specifics* for full recommendations.</span></span>

- <span data-ttu-id="e12a0-116">Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="e12a0-116">Outlook Blocked Senders</span></span>
- <span data-ttu-id="e12a0-117">反垃圾邮件策略: 发件人/域阻止列表</span><span class="sxs-lookup"><span data-stu-id="e12a0-117">Anti-Spam policy: Sender/Domain Block lists</span></span>
- <span data-ttu-id="e12a0-118">Exchange 传输规则 (Etr 也称为邮件流规则)</span><span class="sxs-lookup"><span data-stu-id="e12a0-118">Exchange Transport Rules (ETRs also called mail-flow rules)</span></span>
- <span data-ttu-id="e12a0-119">反垃圾邮件策略: IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="e12a0-119">Anti-Spam policy: IP Block Lists</span></span>

## <a name="use-outlook-blocked-senders"></a><span data-ttu-id="e12a0-120">使用 Outlook 阻止的发件人</span><span class="sxs-lookup"><span data-stu-id="e12a0-120">Use Outlook Blocked Senders</span></span>

<span data-ttu-id="e12a0-121">如果只有少量用户受到影响, 则应使用 Outlook 阻止的发件人, 因为这只会影响向其发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e12a0-121">When only a small number of users are impacted, that's when Outlook Blocked Senders should be used, because this will only impact mail being sent to them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e12a0-122">如果不需要的邮件是来自可信且可识别的来源的新闻快递, 则取消订阅该电子邮件是另一个选项, 阻止用户将来收到该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e12a0-122">If the unwanted messages are newsletters from a reputable and recognizable source, unsubscribing from the email is another option to stop the user from getting the emails in the future.</span></span>

<span data-ttu-id="e12a0-123">设置此设置的步骤在[Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46)和[outlook 客户端](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)之间有所不同。</span><span class="sxs-lookup"><span data-stu-id="e12a0-123">The steps to set this up are different between [Outlook Web App](https://support.office.com/en-us/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) and the [Outlook client](https://support.office.com/en-us/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span> <span data-ttu-id="e12a0-124">**当邮件由于被阻止的发件人而成功被阻止时, 您将在 X Forefront-反垃圾邮件中看到 SFV: BLK** , 这表明该邮件已被阻止。</span><span class="sxs-lookup"><span data-stu-id="e12a0-124">**When messages are successfully blocked due to Blocked Senders you will see SFV:BLK in the X-Forefront-Antispam-Report** which indicates that the message is being blocked.</span></span>

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a><span data-ttu-id="e12a0-125">使用反垃圾邮件策略发件人/域阻止列表</span><span class="sxs-lookup"><span data-stu-id="e12a0-125">Use Anti-Spam Policy Sender/Domain Block lists</span></span>

<span data-ttu-id="e12a0-126">当多个用户受到影响时, 范围将变宽, 您需要使用公司范围内的发件人/域阻止列表反垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="e12a0-126">When multiple users are being impacted, the scope is wider, and you need to use a company-wide sender/domain block list Anti-Spam policy.</span></span> <span data-ttu-id="e12a0-127">可在[配置垃圾邮件筛选器策略](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)文档中找到详细步骤。</span><span class="sxs-lookup"><span data-stu-id="e12a0-127">The detailed steps can be found in [Configure your spam filter policies](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) document.</span></span> <span data-ttu-id="e12a0-128">通过此方法阻止的任何邮件都将遵循策略中配置的垃圾邮件操作。</span><span class="sxs-lookup"><span data-stu-id="e12a0-128">Any messages blocked through this method will follow the spam action as configured in the policy.</span></span>

<span data-ttu-id="e12a0-129">这些列表的最大限制约为1000个条目。</span><span class="sxs-lookup"><span data-stu-id="e12a0-129">The maximum limit for these lists is approximately 1000 entries.</span></span>

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a><span data-ttu-id="e12a0-130">使用 Exchange 传输规则 (Etr) 阻止特定发件人</span><span class="sxs-lookup"><span data-stu-id="e12a0-130">Use Exchange Transport Rules (ETRs) to Block specific senders</span></span>

<span data-ttu-id="e12a0-131">如果需要阻止发送到特定用户或整个组织的邮件, 则可以使用 Etr (也称为邮件流规则)。</span><span class="sxs-lookup"><span data-stu-id="e12a0-131">If it's necessary to block messages being sent to specific users or across the entire organization, ETRs (also called mail flow rules) can be used.</span></span> <span data-ttu-id="e12a0-132">Etr 更灵活, 因为它们可以触发发件人电子邮件地址或域, 以及邮件中的关键词语和其他属性。</span><span class="sxs-lookup"><span data-stu-id="e12a0-132">ETRs are more flexible because they can trigger off the sender Email Address or Domain as well as key words and other properties  in the message.</span></span> <span data-ttu-id="e12a0-133">这种灵活性使您能够创建部分到完整的块。</span><span class="sxs-lookup"><span data-stu-id="e12a0-133">This flexibility will let you create partial- to complete blocks.</span></span> <span data-ttu-id="e12a0-134">[请单击以查看创建 ETR 的步骤, 也称为邮件流规则](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)。</span><span class="sxs-lookup"><span data-stu-id="e12a0-134">[Please click for the steps to create an ETR, also known as a mail-flow rules](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e12a0-135">创建的规则非常简单, 因为这\*\* 会导致所使用的条件尽可能具体, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="e12a0-135">It's easy to create rules that are *overly* aggressive, as a result it's important the criteria being used is as specific as possible.</span></span> <span data-ttu-id="e12a0-136">此外, 请确保对所创建的规则启用审核并进行测试, 以确保一切按预期工作。</span><span class="sxs-lookup"><span data-stu-id="e12a0-136">Also, be sure that you enable auditing on the rule you create and do testing to ensure everything works as expected.</span></span>

## <a name="use-anti-spam-policy-ip-block-lists"></a><span data-ttu-id="e12a0-137">使用反垃圾邮件策略 IP 阻止列表</span><span class="sxs-lookup"><span data-stu-id="e12a0-137">Use Anti-Spam Policy IP Block lists</span></span>

<span data-ttu-id="e12a0-138">如果不能使用其他选项之一阻止发件人,*则*可以使用反垃圾邮件策略 IP 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="e12a0-138">When it’s not possible to use one of the other options to block a sender, *then* the Anti-Spam Policy IP Block List can be used.</span></span> <span data-ttu-id="e12a0-139">[可以在配置连接筛选器策略一文中找到详细步骤](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy)。</span><span class="sxs-lookup"><span data-stu-id="e12a0-139">[Detailed steps can be found in the article Configure the connection filter policy](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-the-connection-filter-policy).</span></span> <span data-ttu-id="e12a0-140">建议不要将阻止 Ip 的列表保持在*最少*, 并且在此处使用 IP 地址范围,*不*建议这样做。</span><span class="sxs-lookup"><span data-stu-id="e12a0-140">It's important to keep the list of blocked IPs to a *minimum* and using IP address ranges here is *not* recommended.</span></span>

<span data-ttu-id="e12a0-141">您应该*特别*避免添加属于消费者服务或共享基础结构的 ip 地址范围, 还应确保在定期维护过程中查看允许的 ip 地址列表。</span><span class="sxs-lookup"><span data-stu-id="e12a0-141">You should *especially* avoid adding IP address ranges that belong to consumer services or shared infrastructures, and also ensure that you review the list of allowed IP addresses as part of regular maintenance.</span></span> <span data-ttu-id="e12a0-142">**由于允许条目可以打开用于攻击的路由, 因此您必须仔细管理此列表, 并定期删除不再需要的允许条目。**</span><span class="sxs-lookup"><span data-stu-id="e12a0-142">**Because allows-entries can open up routes for attack, you must closely manage this list and regularly remove the allows-entries that are no longer needed.**</span></span> <span data-ttu-id="e12a0-143">此外, 如果您将允许在安全发件人列表中使用, 请务必阅读并了解在*[Office 365 中创建安全发件人列表](create-safe-sender-lists-in-office-365.md)* 中的风险和注意事项。</span><span class="sxs-lookup"><span data-stu-id="e12a0-143">Also, if you will make allows in a Safe-Sender list be sure to read and understand the risks and precautions in *[Create Safe-Sender lists in Office 365](create-safe-sender-lists-in-office-365.md)*.</span></span>
