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
ms.openlocfilehash: c33fe53797f86208e7cd033029949737a5c84d2f
ms.sourcegitcommit: 397a5fe594e4cf4bb64c0c6f233d310ef3cbd922
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25540418"
---
# <a name="overview-of-data-loss-prevention-policies"></a><span data-ttu-id="958f3-103">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="958f3-103">Overview of data loss prevention policies</span></span>

<span data-ttu-id="958f3-p101">若要遵守业务标准和行业法规，组织需要保护敏感信息和防止其无意中泄漏。您可能希望阻止泄漏组织外部的敏感信息的示例包括财务数据或如信用卡号、 社会保险号码或运行状况记录的个人身份信息 (PII)。与 Office 365 安全性的数据丢失防护 (DLP) 策略&amp;合规性中心，您可以确定、 监视和自动跨 Office 365 中保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="958f3-p101">To comply with business standards and industry regulations, organizations need to protect sensitive information and prevent its inadvertent disclosure. Examples of sensitive information that you might want to prevent from leaking outside your organization include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="958f3-107">您可以使用 DLP 策略实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="958f3-107">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="958f3-108">**跨多个位置，例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 标识敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="958f3-108">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, and OneDrive for Business.**</span></span>
    
    <span data-ttu-id="958f3-109">例如，可以标识包含信用卡号码存储在任何 OneDrive for Business 站点中的任何文档或可以监视只需特定的某个人的 OneDrive 网站。</span><span class="sxs-lookup"><span data-stu-id="958f3-109">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="958f3-110">**防止意外共享敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="958f3-110">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="958f3-111">例如，您可以识别的所有文档或电子邮件包含与组织外部的人员共享的健康记录，然后自动阻止对该文档的访问或阻止发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="958f3-111">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="958f3-112">**监视和保护桌面版本的 Excel 2016、PowerPoint 2016 和 Word 2016 中的敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="958f3-112">**Monitor and protect sensitive information in the desktop versions of Excel 2016, PowerPoint 2016, and Word 2016.**</span></span>
    
    <span data-ttu-id="958f3-p102">就像在 Exchange Online、 SharePoint Online 和 OneDrive for Business，这些 Office 2016 桌面程序包括相同的功能，以确定敏感信息并应用 DLP 策略。DLP 提供连续监控时人员共享这些 Office 2016 程序中的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p102">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office 2016 desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office 2016 programs.</span></span>
    
- <span data-ttu-id="958f3-115">**帮助用户了解如何保持符合性，同时不会中断工作流。**</span><span class="sxs-lookup"><span data-stu-id="958f3-115">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="958f3-p103">您可以告知用户在 DLP 策略，并帮助他们不阻止其工作保持兼容。例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以同时向他们发送的电子邮件通知并将其显示策略提示允许其在他们有业务替代策略的文档库的上下文中理由。在 Outlook 中的 web、 Outlook 2013 和更高版本，Excel 2016、 PowerPoint 2016 和 Word 2016 上也会显示相同的策略提示。</span><span class="sxs-lookup"><span data-stu-id="958f3-p103">You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook 2013 and later, Excel 2016, PowerPoint 2016, and Word 2016.</span></span>
    
- <span data-ttu-id="958f3-119">**查看 DLP 报告显示内容相匹配您的组织的 DLP 策略。**</span><span class="sxs-lookup"><span data-stu-id="958f3-119">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="958f3-p104">若要评估贵组织遵守 DLP 策略，您可以看到多少匹配的每个策略和规则均具有随着时间的推移。如果 DLP 策略允许用户覆盖策略提示并报告为误报，您还可以查看用户已报告。</span><span class="sxs-lookup"><span data-stu-id="958f3-p104">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="958f3-122">创建和管理 Office 365 安全性数据丢失防护页上的 DLP 策略&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="958f3-122">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 安全性的数据丢失防护页&amp;合规性中心](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="958f3-124">DLP 策略包含的内容</span><span class="sxs-lookup"><span data-stu-id="958f3-124">What a DLP policy contains</span></span>

<span data-ttu-id="958f3-125">DLP 策略包含以下基本内容：</span><span class="sxs-lookup"><span data-stu-id="958f3-125">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="958f3-126">若要保护的内容-**位置**例如 Exchange Online、 SharePoint Online 和 OneDrive for Business 站点的位置。</span><span class="sxs-lookup"><span data-stu-id="958f3-126">Where to protect the content - **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites.</span></span> 
    
- <span data-ttu-id="958f3-127">何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容：</span><span class="sxs-lookup"><span data-stu-id="958f3-127">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="958f3-128">**条件**内容都匹配时才会强制执行规则-例如，只查找包含社会保险号码已与您的组织外部的人员共享的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-128">**Conditions** the content must match before the rule is enforced -- for example, look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="958f3-129">找到满足条件的内容时您希望规则自动执行的**操作**。例如，阻止访问文档，以及向用户和合规部主管发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="958f3-129">**Actions** that you want the rule to take automatically when content matching the conditions is found -- for example, block access to the document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="958f3-130">您可以使用规则以满足特定保护要求，并将 DLP 策略以便组合在一起常见保护要求，如全部所需遵守特定法规的规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-130">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="958f3-p105">例如，您可能必须 DLP 策略，可帮助您检测存在受约束的健康保险便利和义务法案 (HIPAA) 的信息。此 DLP 策略可以帮助保护跨所有 SharePoint Online 网站和所有 OneDrive for Business 站点 （在何处） HIPAA 数据 （功能） 的查找包含与 (贵组织外部的人员共享此敏感信息的任何文档条件），然后阻止对文档的访问并发送通知 （操作）。这些要求存储为各个规则而组合在一起以简化管理和报告的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="958f3-p105">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA). This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions). These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![图表显示了 DLP 策略包含位置和规则](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="958f3-135">位置</span><span class="sxs-lookup"><span data-stu-id="958f3-135">Locations</span></span>

<span data-ttu-id="958f3-p106">DLP 策略可以查找和保护敏感信息跨 Office 365，是否位于 Exchange Online、 SharePoint Online，或 OneDrive for Business 中的信息。您可以轻松地选择保护所有 SharePoint 网站或 OneDrive 帐户，只需特定站点或帐户或所有邮箱。请注意，它尚未可以选择仅特定用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="958f3-p106">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, or OneDrive for Business. You can easily choose to protect all SharePoint sites or OneDrive accounts, just specific sites or accounts, or all mailboxes. Note that it's not yet possible to select just the mailboxes of specific users.</span></span>
  
![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="958f3-p107">请注意，如果您选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户，则 DLP 策略可以包含不超过 100 此类包含和排除规则。尽管存在此限制，了解您可以通过应用组织范围的策略或适用于整个位置策略超过此限制。</span><span class="sxs-lookup"><span data-stu-id="958f3-p107">Note that if you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions. Although this limit exists, understand that you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="958f3-142">规则</span><span class="sxs-lookup"><span data-stu-id="958f3-142">Rules</span></span>

<span data-ttu-id="958f3-p108">规则是什么强制实施业务要求您组织的内容。一个策略包含一个或多个规则，并每个规则组成条件和操作。对于每个规则，当满足的条件，则采取操作自动。启动与每个策略中的最高优先级规则按顺序，执行规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-p108">Rules are what enforce your business requirements on your organization's content. A policy contains one or more rules, and each rule consists of conditions and actions. For each rule, when the conditions are met, the actions are taken automatically. Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="958f3-147">规则还提供选项以通知 （使用策略提示和电子邮件通知） 的用户和管理员 （与电子邮件事件报告） 的内容具有匹配的规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-147">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="958f3-148">下面是一个规则的组件，每个如下所述。</span><span class="sxs-lookup"><span data-stu-id="958f3-148">Here are the components of a rule, each explained below.</span></span>
  
![DLP 规则编辑器部分](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="958f3-150">条件</span><span class="sxs-lookup"><span data-stu-id="958f3-150">Conditions</span></span>

<span data-ttu-id="958f3-p109">条件非常重要，因为它们确定哪些类型的信息要寻找，以及何时执行操作。例如，您可能选择内容包含多个十个此类号码并将其与您的组织外部的人员共享忽略内容包含护照号码。</span><span class="sxs-lookup"><span data-stu-id="958f3-p109">Conditions are important because they determine what types of information you're looking for, and when to take an action. For example, you might choose to ignore content containing passport numbers unless the content contains more than ten such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="958f3-p110">条件侧重于**内容**，例如，要查找什么类型的敏感信息以及还**上下文**，如文档与共享谁。您可以使用条件来将不同的操作分配给不同的风险级别--例如，内部共享的敏感内容可能会降低风险和需要较少操作比敏感内容与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="958f3-p110">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with. You can use conditions to assign different actions to different risk levels -- for example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![显示可用的 DLP 条件的列表](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="958f3-156">现在的可用条件可以确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="958f3-156">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="958f3-157">内容包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="958f3-157">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="958f3-p111">内容包含标签。有关详细信息，请参阅以下部分[使用 DLP 策略中，以状态标签](data-loss-prevention-policies.md#label)。</span><span class="sxs-lookup"><span data-stu-id="958f3-p111">Content contains a label. For more information, see the below section [Using a label as a condition in a DLP policy](data-loss-prevention-policies.md#label).</span></span>
    
- <span data-ttu-id="958f3-160">内容是与您组织的外部还是内部人员共享。</span><span class="sxs-lookup"><span data-stu-id="958f3-160">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="958f3-161">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="958f3-161">Types of sensitive information</span></span>

<span data-ttu-id="958f3-p112">DLP 策略可以帮助保护敏感信息，定义为**敏感信息类型**。Office 365 跨多个可供您使用，如信用卡号、 银行帐号、 国家/地区 ID 编号和护照号码的不同区域包括许多常见的敏感信息类型定义。</span><span class="sxs-lookup"><span data-stu-id="958f3-p112">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**. Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用敏感信息类型列表](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="958f3-p113">当 DLP 策略查找如信用卡号的敏感信息类型时，它不只是查找一个 16 位数字。每种敏感信息类型定义，通过使用的组合检测到：</span><span class="sxs-lookup"><span data-stu-id="958f3-p113">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number. Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="958f3-167">关键字</span><span class="sxs-lookup"><span data-stu-id="958f3-167">Keywords</span></span>
    
- <span data-ttu-id="958f3-168">用于验证校验和或撰写的内部函数</span><span class="sxs-lookup"><span data-stu-id="958f3-168">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="958f3-169">用于查找模式匹配的正则表达式评估</span><span class="sxs-lookup"><span data-stu-id="958f3-169">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="958f3-170">其他内容检查</span><span class="sxs-lookup"><span data-stu-id="958f3-170">Other content examination</span></span>
    
<span data-ttu-id="958f3-171">这有助于减少的误报可以中断人们的工作时实现准确性很大程度的 DLP 检测。</span><span class="sxs-lookup"><span data-stu-id="958f3-171">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="958f3-172">操作</span><span class="sxs-lookup"><span data-stu-id="958f3-172">Actions</span></span>

<span data-ttu-id="958f3-173">当内容都匹配规则中的条件时，可以应用操作以自动保护的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-173">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用 DLP 操作列表](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="958f3-175">使用现已推出的操作，您可以：</span><span class="sxs-lookup"><span data-stu-id="958f3-175">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="958f3-p114">**限制对内容的访问**对于网站内容，这意味着的文档权限被限制网站集主管理员、 文档所有者和上次修改文档的人员之外的任何用户。这些人员可以从文档中移除敏感信息或采取其他补救措施。合规性文档时，将自动还原原始的权限。时将阻止对文档的访问，与网站上的库中的特殊策略提示图标显示文档。</span><span class="sxs-lookup"><span data-stu-id="958f3-p114">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document. These people can remove the sensitive information from the document or take other remedial action. When the document is in compliance, the original permissions will be automatically restored. When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![显示文档访问被拦截的策略提示](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="958f3-p115">电子邮件内容，此操作阻止发送邮件。根据 DLP 规则的配置方式，发件人将看到 NDR 或 （如果此规则使用通知） 的策略提示和/或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="958f3-p115">For email content, this action blocks the message from being sent. Depending on how the DLP rule is configured, the sender will see an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![警告未经授权的收件人必须从邮件中删除](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="958f3-184">用户通知和用户重写</span><span class="sxs-lookup"><span data-stu-id="958f3-184">User notifications and user overrides</span></span>

<span data-ttu-id="958f3-p116">您可以使用通知和重写以告知用户在 DLP 策略，并帮助他们不阻止其工作保持兼容。例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以同时向他们发送的电子邮件通知并将其显示策略提示允许其在他们有业务替代策略的文档库的上下文中理由。</span><span class="sxs-lookup"><span data-stu-id="958f3-p116">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![用户通知和用户替代 DLP 规则编辑器部分](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="958f3-p117">电子邮件可以通知发送、 共享，或上次修改的内容和，为网站内容、 网站集主管理员和文档所有者的人员。此外，您可以添加或删除何人您选择电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="958f3-p117">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="958f3-190">除了发送的电子邮件通知，通知用户显示的策略提示：</span><span class="sxs-lookup"><span data-stu-id="958f3-190">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="958f3-191">在 Outlook 2013 及更高版本和 Outlook web 上。</span><span class="sxs-lookup"><span data-stu-id="958f3-191">In Outlook 2013 and later and Outlook on the web.</span></span>
    
- <span data-ttu-id="958f3-192">针对业务网站上的 SharePoint Online 或 OneDrive 文档。</span><span class="sxs-lookup"><span data-stu-id="958f3-192">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="958f3-193">在 Excel 2016 PowerPoint 2016 和 Word 2016，当文档存储在网站上包含在 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="958f3-193">In Excel 2016, PowerPoint 2016, and Word 2016, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="958f3-p118">电子邮件通知和策略提示介绍内容与某个 DLP 策略冲突的原因。如果您选择，电子邮件通知和策略提示可以允许用户能够替代规则报告误报或提供的业务理由。这可以帮助您让用户了解您的 DLP 策略和实施这些不阻止它们的工作人员。有关重写和误报信息还用于报告 （参见下面有关 DLP 报告） 记录和事件中包含报告 （下一节），以便合规部主管可以定期查看此信息。</span><span class="sxs-lookup"><span data-stu-id="958f3-p118">The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="958f3-198">下面是策略提示的外观中的 OneDrive for Business 帐户。</span><span class="sxs-lookup"><span data-stu-id="958f3-198">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![策略提示中的 OneDrive 帐户文档](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="958f3-200">事件报告</span><span class="sxs-lookup"><span data-stu-id="958f3-200">Incident reports</span></span>

<span data-ttu-id="958f3-p119">时匹配的规则时，可以与该事件的详细信息事件报告发送到您合规部主管 （或您选择的任何人）。此报表包含有关匹配，该规则和上次修改内容的人员的名称匹配的实际内容项的信息。对于电子邮件报告还包括作为附件原始邮件匹配 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="958f3-p119">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event. This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content. For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![用于配置事件报告的页面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="958f3-205">分组和逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="958f3-205">Grouping and logical operators</span></span>

<span data-ttu-id="958f3-p120">通常 DLP 策略具有变得非常简单的要求，例如，若要确定包含美国社会保障号的所有内容。但是，在其他情况下，您的 DLP 策略可能需要确定更松散定义的数据。</span><span class="sxs-lookup"><span data-stu-id="958f3-p120">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number. However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="958f3-208">例如，若要确定内容受美国健康保险法案 (HIPAA)，您需要查找：</span><span class="sxs-lookup"><span data-stu-id="958f3-208">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="958f3-209">包含敏感信息，如美国社会保障号或药品实施机构 (DEA) 号码的特定类型的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-209">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="958f3-210">AND</span><span class="sxs-lookup"><span data-stu-id="958f3-210">AND</span></span>
    
- <span data-ttu-id="958f3-p121">内容的是更加难以确定，如 communications 有关患者的医护或医疗服务提供的说明。标识此内容需要匹配非常大的关键字列表，如国际分类的科 （ICD 9 厘米或 ICD 10 厘米） 中的关键字。</span><span class="sxs-lookup"><span data-stu-id="958f3-p121">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided. Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="958f3-p122">使用分组和逻辑运算符 (AND、 OR)，可以轻松地识别此类松散定义的数据。创建 DLP 策略时，您可以：</span><span class="sxs-lookup"><span data-stu-id="958f3-p122">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR). When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="958f3-215">组敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="958f3-215">Group sensitive information types.</span></span>
    
- <span data-ttu-id="958f3-216">选择自己的组之间以及组中的敏感信息类型之间的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="958f3-216">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="958f3-217">选择组中的运算符</span><span class="sxs-lookup"><span data-stu-id="958f3-217">Choosing the operator within a group</span></span>

<span data-ttu-id="958f3-218">在组中，您可以选择是否必须为要与规则匹配的内容满足任何或所有该组中的条件。</span><span class="sxs-lookup"><span data-stu-id="958f3-218">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![组显示组中的运算符](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="958f3-220">添加组</span><span class="sxs-lookup"><span data-stu-id="958f3-220">Adding a group</span></span>

<span data-ttu-id="958f3-221">您可以快速添加一组，都可以具有自己的条件和该组中的运算符。</span><span class="sxs-lookup"><span data-stu-id="958f3-221">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![添加组按钮](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="958f3-223">选择组之间的运算符</span><span class="sxs-lookup"><span data-stu-id="958f3-223">Choosing the operator between groups</span></span>

<span data-ttu-id="958f3-224">之间组，您可以选择要与规则匹配的内容是否必须满足中只有一个组或所有的组的条件。</span><span class="sxs-lookup"><span data-stu-id="958f3-224">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="958f3-225">例如，内置的**美国 HIPAA**策略具有的规则，以便它标识包含的内容使用**AND**运算符之间的组：</span><span class="sxs-lookup"><span data-stu-id="958f3-225">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="958f3-226">从组**PII 标识符**(至少一个 SSN number**或**DEA)</span><span class="sxs-lookup"><span data-stu-id="958f3-226">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="958f3-227">**AND**</span><span class="sxs-lookup"><span data-stu-id="958f3-227">**AND**</span></span>
    
- <span data-ttu-id="958f3-228">从组**医疗条款**（至少一个 ICD 9 厘米关键字**或**ICD-10-CM 关键字）</span><span class="sxs-lookup"><span data-stu-id="958f3-228">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![组显示组之间的运算符](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="958f3-230">按其处理规则优先级</span><span class="sxs-lookup"><span data-stu-id="958f3-230">The priority by which rules are processed</span></span>

<span data-ttu-id="958f3-p123">在策略中创建规则时，每个规则分配顺序在其中创建-这意味着，创建的规则首先具有最高优先级的优先级，第二创建的规则具有第二个优先级，依此类推。创建规则后，不能更改其优先级，通过删除并重新创建除外。</span><span class="sxs-lookup"><span data-stu-id="958f3-p123">When you create rules in a policy, each rule is assigned a priority in the order in which it's created - meaning, the rule created first has first priority, the rule created second has second priority, and so on. After you create a rule, its priority can't be changed, except by deleting and re-creating it.</span></span>
  
![规则优先级顺序](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="958f3-p124">时根据规则评估内容，以优先级顺序处理规则。如果内容与多个规则相匹配，规则优先级顺序中进行处理，并强制最严格的操作。例如，如果内容匹配的所有以下规则，因为它是最高优先级、 最严格的规则，将强制执行规则 3:</span><span class="sxs-lookup"><span data-stu-id="958f3-p124">When content is evaluated against rules, the rules are processed in priority order. If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced. For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="958f3-237">规则 1： 只将通知用户</span><span class="sxs-lookup"><span data-stu-id="958f3-237">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="958f3-238">规则 2： 通知用户，限制访问，并允许用户重写</span><span class="sxs-lookup"><span data-stu-id="958f3-238">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="958f3-239">规则 3： 将通知用户，限制访问，并且不允许用户重写</span><span class="sxs-lookup"><span data-stu-id="958f3-239">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="958f3-240">规则 4： 仅通知用户</span><span class="sxs-lookup"><span data-stu-id="958f3-240">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="958f3-241">规则 5： 限制访问</span><span class="sxs-lookup"><span data-stu-id="958f3-241">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="958f3-242">规则 6： 将通知用户，限制访问，并且不允许用户重写</span><span class="sxs-lookup"><span data-stu-id="958f3-242">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="958f3-243">本示例中，请注意，匹配的所有规则的审核日志中记录显示在 DLP 报告中，尽管在实施只最严格的规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-243">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="958f3-244">对于策略提示，请注意:</span><span class="sxs-lookup"><span data-stu-id="958f3-244">With respect to policy tips, note that:</span></span>
  
- <span data-ttu-id="958f3-p125">仅从最高优先级的策略提示，将显示最严格的规则。例如，从规则阻止访问内容将显示通过策略提示从只发送通知的规则的策略提示。这将阻止用户查看策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="958f3-p125">Only the policy tip from the highest priority, most restrictive rule will be shown. For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification. This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="958f3-248">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-248">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="958f3-249">调整规则以使其更容易或更加复杂，以匹配</span><span class="sxs-lookup"><span data-stu-id="958f3-249">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="958f3-250">人员创建和打开其 DLP 策略后，它们是有时会遇到这些问题的过程：</span><span class="sxs-lookup"><span data-stu-id="958f3-250">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="958f3-251">**不是**敏感信息匹配的规则-换句话说，太多误报太多内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-251">Too much content that **is not** sensitive information matches the rules - in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="958f3-252">太少的内容**为**敏感信息匹配规则-换句话说，保护不被强制执行的操作的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="958f3-252">Too little content that **is** sensitive information matches the rules - in other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="958f3-p126">为了解决这些问题，您可以通过调整实例计数优化您的规则和匹配准确性，使其更加复杂或更轻松地与规则匹配内容。在规则使用每个敏感信息类型具有两个实例对变量计数和匹配准确性。</span><span class="sxs-lookup"><span data-stu-id="958f3-p126">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules. Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="958f3-255">实例计数</span><span class="sxs-lookup"><span data-stu-id="958f3-255">Instance count</span></span>

<span data-ttu-id="958f3-p127">实例计数只是表示特定类型的敏感信息出现多少次必须存在以内容的规则匹配。例如，内容将与下面显示是否 1 到 9 唯一美国或英国之间标识护照号码的规则匹配。</span><span class="sxs-lookup"><span data-stu-id="958f3-p127">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule. For example, content will match the rule shown below if between 1 and 9 unique U.S. or U.K. passport numbers are identified.</span></span>
  
<span data-ttu-id="958f3-p128">请注意，实例计数包括仅**唯一**匹配敏感信息类型和关键字。例如，如果电子邮件中包含 10 个相同的信用卡号，这些 10 个匹配项计数为信用卡号的单个实例。</span><span class="sxs-lookup"><span data-stu-id="958f3-p128">Note that the instance count includes only **unique** matches for sensitive information types and keywords. For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="958f3-261">若要使用实例计数调整规则，指南非常简单：</span><span class="sxs-lookup"><span data-stu-id="958f3-261">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="958f3-p129">若要使规则更轻松地匹配，降低的**分钟**数和/或增加**最大**的计数。您还可以设置**最大**到**任何**通过删除数值。</span><span class="sxs-lookup"><span data-stu-id="958f3-p129">To make the rule easier to match, decrease the **min** count and/or increase the **max** count. You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="958f3-264">若要使规则匹配更加复杂，增加的**分钟**数。</span><span class="sxs-lookup"><span data-stu-id="958f3-264">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="958f3-p130">通常，使用限制较少的操作，如发送用户通知，在规则与较低的实例计数 (例如，1-9)。并使用更严格的操作，如限制对内容的访问，但不允许用户重写规则具有更高版本 （例如，任何 10） 实例计数中。</span><span class="sxs-lookup"><span data-stu-id="958f3-p130">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9). And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![在规则编辑器中计数实例](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="958f3-268">匹配准确性</span><span class="sxs-lookup"><span data-stu-id="958f3-268">Match accuracy</span></span>

<span data-ttu-id="958f3-p131">如上所述，定义和使用的不同类型的证据组合检测到的敏感信息类型。通常，由多个此类组合，调用模式定义的敏感信息类型。需要较少证据模式具有较低的匹配准确性 （或可信度） 时要求更多的证据具有匹配准确度 （或可信度） 的模式。若要了解有关的实际模式和每个敏感信息类型使用的可信度级别的详细信息，请参阅[查找敏感信息类型](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="958f3-p131">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence. Commonly, a sensitive information type is defined by multiple such combinations, called patterns. A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level). To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="958f3-273">例如，名为信用卡号的敏感信息类型由两种模式进行定义：</span><span class="sxs-lookup"><span data-stu-id="958f3-273">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="958f3-274">需要的 65%自信地模式：</span><span class="sxs-lookup"><span data-stu-id="958f3-274">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="958f3-275">信用卡号的格式的数字。</span><span class="sxs-lookup"><span data-stu-id="958f3-275">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="958f3-276">一个数字，将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="958f3-276">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="958f3-277">需要的 85%自信地模式：</span><span class="sxs-lookup"><span data-stu-id="958f3-277">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="958f3-278">信用卡号的格式的数字。</span><span class="sxs-lookup"><span data-stu-id="958f3-278">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="958f3-279">一个数字，将传递校验和。</span><span class="sxs-lookup"><span data-stu-id="958f3-279">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="958f3-280">关键字或右格式的到期日期。</span><span class="sxs-lookup"><span data-stu-id="958f3-280">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="958f3-p132">您可以使用这些在规则中可信度级别 （或匹配准确性）。通常，使用限制较少的操作，如发送用户通知，在规则与较低的匹配准确性。并使用更严格的操作，如限制对内容的访问，但不允许用户重写中具有更高版本匹配准确性的规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-p132">You can use these confidence levels (or match accuracy) in your rules. Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy. And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="958f3-284">非常重要了解如果特定类型的敏感信息，如信用卡号码，在内容中确定的则返回仅单个可信度级别：</span><span class="sxs-lookup"><span data-stu-id="958f3-284">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="958f3-285">如果所有匹配项的单个模式，则返回该模式的置信。</span><span class="sxs-lookup"><span data-stu-id="958f3-285">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="958f3-p133">如果有多个模式匹配 （即，有两个不同可信度级别的匹配项），返回的可信度级别高于任何单独的单个模式。这是复杂的一部分。例如，对于信用卡号，如果的 65%和 85%的模式匹配的置信返回的敏感信息类型是超过 90%，因为多个证据意味着更多可信度。</span><span class="sxs-lookup"><span data-stu-id="958f3-p133">If there are matches for more than one pattern (i.e., there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned. This is the tricky part. For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="958f3-p134">因此，如果您想要创建信用卡，一个用于 65%匹配准确性，一个用于 85%匹配准确性的两个是互斥的规则匹配准确性的范围将如下所示。第一个规则选取 65%模式的仅匹配项。**至少一个**85%匹配和**都可能具有**与其他较低可信度匹配项，第二个规则拾取相匹配。</span><span class="sxs-lookup"><span data-stu-id="958f3-p134">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this. The first rule picks up only matches of the 65% pattern. The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![使用的匹配准确性的不同范围的两个规则](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="958f3-293">出于以上原因，使用不同的匹配准确性创建规则的指南是：</span><span class="sxs-lookup"><span data-stu-id="958f3-293">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="958f3-294">最低可信度通常使用**min**和**max** （而不是范围） 相同的值。</span><span class="sxs-lookup"><span data-stu-id="958f3-294">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="958f3-295">最高可信度通常是介于正上方较低可信度级别为 100。</span><span class="sxs-lookup"><span data-stu-id="958f3-295">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="958f3-296">任何中间可信度级别通常的范围从较低可信度到紧邻下方较高可信度级别的紧上方。</span><span class="sxs-lookup"><span data-stu-id="958f3-296">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="958f3-297">将标签用作 DLP 策略中的条件</span><span class="sxs-lookup"><span data-stu-id="958f3-297">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="958f3-298">您可以创建标签，然后：</span><span class="sxs-lookup"><span data-stu-id="958f3-298">You can create a label and then:</span></span>
  
- <span data-ttu-id="958f3-299">**发布**，以便最终用户可以查看和手动将标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-299">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="958f3-300">**自动应用**您选择的条件匹配其内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-300">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="958f3-301">若要详细了解标签，请参阅[标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="958f3-301">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
<span data-ttu-id="958f3-p135">创建标签后，您可以使用该标签为条件 DLP 策略中。例如，您可能需要这样做是因为：</span><span class="sxs-lookup"><span data-stu-id="958f3-p135">After you create a label, you can then use that label as a condition in your DLP policies. For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="958f3-p136">您发布一个名为**2 私有 3 机密**，标签，以便您的组织中的人员可以手动将标签应用于机密电子邮件和文档。通过使用此标签作为 DLP 策略中的条件，您可以限制标记**2 私有 3 机密**与您的组织外部的人员共享的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p136">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents. By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="958f3-p137">您创建一个名为该名称的项目的**Alpine House**标签，然后应用该标签自动于包含关键字"Alpine House"的内容。通过使用此标签作为 DLP 策略中的条件，您可以为最终用户显示策略提示时将要与组织外部的某个人共享此内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p137">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House". By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="958f3-p138">您发布一个名为**税记录**，标签，以便记录管理员可以手动将标签应用于需要归类为记录的内容。通过使用此标签作为 DLP 策略中的条件，您可以查看带结合使用与其他类型的敏感信息，如 ITINs 或 Ssn; 此标签的内容将保护操作应用于内容标记**税记录**;有关 DLP 策略的详细的活动报告获得 DLP 报告，并审核日志数据。</span><span class="sxs-lookup"><span data-stu-id="958f3-p138">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record. By using this label as a condition in your DLP policy, you can look for content with this label in conjunction with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="958f3-p139">发布到 Exchange 邮箱和 OneDrive 帐户的执行官一组命名**Executive 领导团队-敏感**的标签。通过使用此标签作为 DLP 策略中的条件，您可以实施保留和保护操作的同一子集的内容和用户。</span><span class="sxs-lookup"><span data-stu-id="958f3-p139">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives. By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="958f3-312">通过使用标签中 DLP 规则条件相同，可以您有选择地实施一组特定的内容、 位置或用户的保护操作。</span><span class="sxs-lookup"><span data-stu-id="958f3-312">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![为条件的标签](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="958f3-314">此功能与其他功能的方式</span><span class="sxs-lookup"><span data-stu-id="958f3-314">How this feature relates to other features</span></span>

<span data-ttu-id="958f3-315">多个功能可以应用于包含敏感信息的内容：</span><span class="sxs-lookup"><span data-stu-id="958f3-315">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="958f3-316">[应用自动根据条件标签][保留标签](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)都可以强制对此内容的**保留**操作。</span><span class="sxs-lookup"><span data-stu-id="958f3-316">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions)[Applying a label automatically based on conditions] and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="958f3-p140">DLP 策略可以强制实施此内容**保护**操作。和强制实施这些操作之前, 的 DLP 策略可能需要其他条件满足除了包含标签的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p140">A DLP policy can enforce **protection** actions on this content. And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![可以将应用于敏感信息的功能的关系图](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="958f3-p141">请注意，DLP 策略比标签或保留策略应用于敏感信息的更丰富的检测功能。DLP 策略可以强制实施内容包含敏感信息保护措施，并从内容中移除敏感信息，这些保护操作是否撤消下次内容的扫描。但如果保留策略或标签应用于包含敏感信息的内容，这是不被撤消，即使的敏感信息中删除一个一次性操作。</span><span class="sxs-lookup"><span data-stu-id="958f3-p141">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information. A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned. But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information's removed.</span></span>
  
<span data-ttu-id="958f3-p142">通过使用一个标签作为 DLP 策略中的条件，您可以实施保留和保护功能对与该标签的内容的操作。您可以将内容包含标签完全一样包含敏感信息的内容-标签和敏感信息类型是用于分类的内容，以便您可以强制实施操作对该内容的属性。</span><span class="sxs-lookup"><span data-stu-id="958f3-p142">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label. You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![为条件中使用标签的 DLP 策略的关系图](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="958f3-326">简单设置与高级设置</span><span class="sxs-lookup"><span data-stu-id="958f3-326">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="958f3-327">创建 DLP 策略时，您将简单或高级设置之间进行选择：</span><span class="sxs-lookup"><span data-stu-id="958f3-327">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="958f3-328">**简单的设置**，使轻松创建无需使用规则编辑器来创建或修改规则的 DLP 策略的最常见类型。</span><span class="sxs-lookup"><span data-stu-id="958f3-328">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="958f3-329">**高级设置**使用规则编辑器使您可以完全控制您的 DLP 策略的每个设置。</span><span class="sxs-lookup"><span data-stu-id="958f3-329">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="958f3-p143">不要担心，隐式，简单的设置和高级的设置完全相同，通过强制执行规则组成条件和操作-仅使用简单的设置，请看不到规则编辑器。它是一种创建 DLP 策略的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="958f3-p143">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor. It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="958f3-332">简单的设置</span><span class="sxs-lookup"><span data-stu-id="958f3-332">Simple settings</span></span>

<span data-ttu-id="958f3-p144">到目前为止，最常见的 DLP 方案创建策略来帮助保护与可以访问内容，您的组织，以及采取自动的补救措施，如限制外部用户共享的内容包含敏感信息发送最终用户或管理员通知和审核更高版本的调查的事件。人使用 DLP 防止无意泄露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="958f3-p144">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation. People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="958f3-p145">为了简化实现此目的，当您创建的 DLP 策略时，您可以选择**使用简单的设置**。这些设置提供了您需要实现的最常见的 DLP 策略，而无需进入规则编辑器的全部内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p145">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**. These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP 简单和高级设置选项](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="958f3-338">高级设置</span><span class="sxs-lookup"><span data-stu-id="958f3-338">Advanced settings</span></span>

<span data-ttu-id="958f3-339">如果您需要创建更多的自定义的 DLP 策略，则可以选择**使用高级设置**。</span><span class="sxs-lookup"><span data-stu-id="958f3-339">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="958f3-340">高级的设置为您提供了规则编辑器，您可以完全控制每个可能的选项，包括实例计数和匹配准确性 （可信度） 为每个规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-340">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="958f3-341">若要快速跳到部分，单击规则编辑器转到下面的部分的顶部导航栏中的项目。</span><span class="sxs-lookup"><span data-stu-id="958f3-341">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 规则编辑器的顶部导航菜单](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="958f3-343">DLP 策略模板</span><span class="sxs-lookup"><span data-stu-id="958f3-343">DLP policy templates</span></span>

<span data-ttu-id="958f3-p146">创建 DLP 策略的第一步在选择要保护的信息。通过在开始使用 DLP 模板，您将保存生成一组新的规则从头开始，并找出哪些类型的信息应包含默认情况下的工作。然后可以添加或修改这些要求才能微调规则以满足您组织的特定要求。</span><span class="sxs-lookup"><span data-stu-id="958f3-p146">The first step in creating a DLP policy is choosing what information to protect. By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default. You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="958f3-p147">预配置的 DLP 策略模板可帮助您检测特定类型的敏感信息，如 HIPAA 数据、 PCI-DSS 数据、 格雷姆-里奇-比利雷法案数据，甚至是特定于区域设置的个人身份信息 (P.I.)。若要使您方便地查找和保护常见的敏感信息类型，已包含 Office 365 中的策略模板包含需要为您要开始的最常见敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="958f3-p147">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.). To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![数据丢失防护策略模板列表，重点放在美国模板上爱国者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="958f3-p148">您的组织可能还有自己的特定要求，这种情况下您可以从头开始创建 DLP 策略通过选择**自定义策略**选项。自定义策略为空，并且包含没有预制的规则。</span><span class="sxs-lookup"><span data-stu-id="958f3-p148">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option. A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="958f3-352">在测试模式下逐步部署 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="958f3-352">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="958f3-p149">创建您的 DLP 策略时，您应考虑推出逐步评估它们的影响，并在全面执行前测试其有效性。例如，您不希望新 DLP 策略无意中阻止访问数以千计的人员才能完成其工作需要访问的文档。</span><span class="sxs-lookup"><span data-stu-id="958f3-p149">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="958f3-355">如果您正在创建 DLP 策略的大型的潜在影响，建议遵循此序列：</span><span class="sxs-lookup"><span data-stu-id="958f3-355">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="958f3-p150">**在不使用策略提示的情况下测试模式下的开始**，然后使用 DLP 报告和评估影响的所有事件都报告。DLP 报告可用于查看数量、 位置、 类型和策略的匹配项的严重性。基于结果，您可以微调规则根据需要。在测试模式下 DLP 策略不会影响您的组织中的人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="958f3-p150">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="958f3-p151">**将移动到测试模式下使用通知和策略提示**，以便您可以开始教有关合规性策略的用户并做准备要应用的规则。在此阶段，您还可以要求用户，以便您可以进一步改进规则报告误报。</span><span class="sxs-lookup"><span data-stu-id="958f3-p151">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="958f3-p152">**启动完全实施策略**，以便应用规则中的操作和内容的受保护。继续监视 DLP 报告任何事件报告或通知，以确保结果预想。</span><span class="sxs-lookup"><span data-stu-id="958f3-p152">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="958f3-p153">您可以在任何时候，这会影响策略中的所有规则将关闭 DLP 策略。但是，每个规则可以还关闭单独通过切换在规则编辑器中的状态。</span><span class="sxs-lookup"><span data-stu-id="958f3-p153">You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![关闭策略中的规则的选项](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="958f3-368">DLP 报告</span><span class="sxs-lookup"><span data-stu-id="958f3-368">DLP reports</span></span>

<span data-ttu-id="958f3-p154">创建和打开您的 DLP 策略后，您需要确认他们正在作为您的预期工作，并帮助您保持兼容。使用 DLP 报告，您可以快速查看 DLP 策略的数量和规则匹配通过时间和误报数和替代。每个报表，您可以筛选按位置，时间范围，这些匹配和甚至将其缩小到特定的策略、 规则或操作。</span><span class="sxs-lookup"><span data-stu-id="958f3-p154">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant. With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides. For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="958f3-372">使用 DLP 报告，您可以获取业务见解并了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="958f3-372">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="958f3-373">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="958f3-373">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="958f3-374">发现违反组织的合规性策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="958f3-374">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="958f3-375">了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="958f3-375">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="958f3-376">此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="958f3-376">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全性和合规性中心中的报告仪表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="958f3-378">DLP 策略的工作原理</span><span class="sxs-lookup"><span data-stu-id="958f3-378">How DLP policies work</span></span>

<span data-ttu-id="958f3-p155">DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。</span><span class="sxs-lookup"><span data-stu-id="958f3-p155">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="958f3-383">策略会进行同步</span><span class="sxs-lookup"><span data-stu-id="958f3-383">Policies are synced</span></span>

<span data-ttu-id="958f3-384">在安全中创建的 DLP 策略后&amp;合规性中心，它具有存储在中央策略存储区，然后同步到各种内容源，其中包括：</span><span class="sxs-lookup"><span data-stu-id="958f3-384">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="958f3-385">Exchange Online，和从 web 上的 Outlook 和 Outlook 2013 存在及更高版本</span><span class="sxs-lookup"><span data-stu-id="958f3-385">Exchange Online, and from there to Outlook on the web and Outlook 2013 and later</span></span>
    
- <span data-ttu-id="958f3-386">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="958f3-386">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="958f3-387">SharePoint Online 站点</span><span class="sxs-lookup"><span data-stu-id="958f3-387">SharePoint Online sites</span></span>
    
- <span data-ttu-id="958f3-388">Office 2016 桌面程序（Excel 2016、PowerPoint 2016 和 Word 2016）</span><span class="sxs-lookup"><span data-stu-id="958f3-388">Office 2016 desktop programs (Excel 2016, PowerPoint 2016, and Word 2016)</span></span>
    
<span data-ttu-id="958f3-389">策略的同步到右的位置后，启动评估内容和强制实施操作。</span><span class="sxs-lookup"><span data-stu-id="958f3-389">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="958f3-390">OneDrive for Business 和 SharePoint Online 站点中的策略评估</span><span class="sxs-lookup"><span data-stu-id="958f3-390">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="958f3-p156">在所有 SharePoint Online 网站和 OneDrive for Business 站点，文档不断都变化 — 它们不断创建、 编辑、 共享和等。这意味着文档可以发生冲突或任何时候成为符合 DLP 策略。例如，联系人可以上载文档不包含敏感信息到其工作组网站，但更高版本，另一个人可以编辑同一文档并向其添加敏感信息。</span><span class="sxs-lookup"><span data-stu-id="958f3-p156">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on. This means documents can conflict or become compliant with a DLP policy at any time. For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="958f3-p157">为此，DLP 策略经常检查后台中是否包含与策略相符的文档。您可以将这视为异步策略评估。</span><span class="sxs-lookup"><span data-stu-id="958f3-p157">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation.</span></span>
  
<span data-ttu-id="958f3-p158">下面是它的工作方式。人员添加或更改其网站中的文档，如搜索引擎将扫描内容，以便可以为其搜索更高版本。时出现这种情况的内容还扫描的敏感信息，并检查是否共享。找到任何敏感信息是安全存储在搜索索引中，以便仅合规性团队可以访问它，但不是典型的用户。您已打开的每个 DLP 策略在后台运行 （异步），检查经常任何相匹配的内容策略，请在搜索和应用操作，以防止无意泄漏。</span><span class="sxs-lookup"><span data-stu-id="958f3-p158">Here's how it works. As people add or change documents in their sites, the search engine scans the content, so that you can search for it later. While this is happening, the content's also scanned for sensitive information and to check if it's shared. Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users. Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![显示如何 DLP 策略评估内容以异步方式的图示](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="958f3-p159">最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。</span><span class="sxs-lookup"><span data-stu-id="958f3-p159">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="958f3-p160">DLP 计算可进行索引的任何内容。有关哪些文件类型进行爬网，默认情况下的详细信息，请参阅[默认爬网文件扩展名和分析 SharePoint Server 2013 中的文件类型](https://go.microsoft.com/fwlink/p/?LinkID=627430)。</span><span class="sxs-lookup"><span data-stu-id="958f3-p160">DLP evaluates any content that can be indexed. For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server 2013](https://go.microsoft.com/fwlink/p/?LinkID=627430).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-2013-and-later-and-outlook-on-the-web"></a><span data-ttu-id="958f3-407">Exchange Online、 Outlook 2013 及更高版本，和 web 上的 Outlook 中的策略评估</span><span class="sxs-lookup"><span data-stu-id="958f3-407">Policy evaluation in Exchange Online, Outlook 2013 and later, and Outlook on the web</span></span>

<span data-ttu-id="958f3-408">创建包含为位置 Exchange Online 的 DLP 策略时，该策略的同步从 Office 365 安全性&amp;合规性中心到 Exchange Online，然后从 web 上的 Outlook 和 Outlook 2013 及更高版本 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="958f3-408">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook 2013 and later.</span></span>
  
<span data-ttu-id="958f3-p161">时要在 Outlook 中撰写邮件，用户可以看到策略提示，如针对 DLP 策略评估正在创建的内容。和发送一条消息后，其计算针对 DLP 策略为正常邮件流，以及 Exchange 传输规则和在 Exchange 管理中心中创建的 DLP 策略的一部分 （请参阅下一节的详细信息）。DLP 策略扫描邮件和任何附件。</span><span class="sxs-lookup"><span data-stu-id="958f3-p161">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies. And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange transport rules and DLP policies created in the Exchange Admin Center (see the next section for more info). DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-2016-desktop-programs"></a><span data-ttu-id="958f3-412">Office 2016 桌面程序中的策略评估</span><span class="sxs-lookup"><span data-stu-id="958f3-412">Policy evaluation in the Office 2016 desktop programs</span></span>

<span data-ttu-id="958f3-p162">Excel 2016、 PowerPoint 2016 和 Word 2016 包括确定敏感信息并将作为 SharePoint Online 和 OneDrive for Business 应用 DLP 策略的相同功能。这些 Office 2016 程序同步直接从中央策略存储，其 DLP 策略，然后在当用户从网站中的 DLP 策略包含打开的文档处理时持续评估针对 DLP 策略的内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p162">Excel 2016, PowerPoint 2016, and Word 2016 include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business. These Office 2016 programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="958f3-p163">在 Office 2016 DLP 策略评估旨在不会影响性能的程序或内容的人员的工作效率。如果他们正在处理大型文档，或在用户计算机正忙，可能需要几秒钟的策略提示显示。</span><span class="sxs-lookup"><span data-stu-id="958f3-p163">DLP policy evaluation in Office 2016 is designed not to affect the performance of the programs or the productivity of people working on content. If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>
  
## <a name="permissions"></a><span data-ttu-id="958f3-417">权限</span><span class="sxs-lookup"><span data-stu-id="958f3-417">Permissions</span></span>

<span data-ttu-id="958f3-p164">将创建 DLP 策略的合规性团队成员需要安全权限&amp;合规性中心。默认情况下，租户管理员将具有对此位置的访问，并且可以授予安全性合规部主管及其他人访问&amp;合规性中心，但不授予所有的租户管理员权限为此，我们建议您：</span><span class="sxs-lookup"><span data-stu-id="958f3-p164">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center. By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="958f3-420">在 Office 365 中创建组并向其添加合规部主管。</span><span class="sxs-lookup"><span data-stu-id="958f3-420">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="958f3-421">创建角色组的安全**权限**页上&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="958f3-421">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="958f3-422">将 Office 365 组添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="958f3-422">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="958f3-423">有关详细信息，请参阅[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="958f3-423">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="958f3-p165">只有在创建和应用 DLP 策略时才需要这些权限。策略执行不需要访问此内容。</span><span class="sxs-lookup"><span data-stu-id="958f3-p165">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="958f3-426">查找 DLP cmdlet</span><span class="sxs-lookup"><span data-stu-id="958f3-426">Find the DLP cmdlets</span></span>

<span data-ttu-id="958f3-427">要用于安全的大部分 cmdlet&amp;合规性中心，您需要：</span><span class="sxs-lookup"><span data-stu-id="958f3-427">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="958f3-428">使用远程 PowerShell 连接到 Office 365 安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="958f3-428">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. <span data-ttu-id="958f3-429">使用下列任一[Office 365 安全性&amp;合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="958f3-429">Use any of these [Office 365 Security &amp; Compliance Center cmdlets](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)</span></span>
    
<span data-ttu-id="958f3-p166">但是，DLP 报告需要拉跨 Office 365，包括 Exchange Online 中的数据。因此，DLP 报告的 cmdlet 可在 Exchange Online Powershell-不在安全&amp;合规性中心 Powershell。因此，若要使用 DLP 报告 cmdlet，您需要：</span><span class="sxs-lookup"><span data-stu-id="958f3-p166">However, DLP reports need pull data from across Office 365, including Exchange Online. For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell. Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="958f3-433">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="958f3-433">Connect to Exchange Online using remote PowerShell</span></span>](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. <span data-ttu-id="958f3-434">使用这些 cmdlet 的任何 DLP 报告：</span><span class="sxs-lookup"><span data-stu-id="958f3-434">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="958f3-435">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="958f3-435">Get-DlpDetectionsReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
  - [<span data-ttu-id="958f3-436">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="958f3-436">Get-DlpDetailReport</span></span>](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    
## <a name="more-information"></a><span data-ttu-id="958f3-437">更多信息</span><span class="sxs-lookup"><span data-stu-id="958f3-437">More information</span></span>

- [<span data-ttu-id="958f3-438">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="958f3-438">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="958f3-439">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="958f3-439">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="958f3-440">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="958f3-440">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="958f3-441">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="958f3-441">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="958f3-442">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="958f3-442">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="958f3-443">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="958f3-443">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="958f3-444">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="958f3-444">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

