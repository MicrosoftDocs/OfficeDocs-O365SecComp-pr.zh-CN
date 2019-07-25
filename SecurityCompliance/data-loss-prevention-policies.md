---
title: 数据丢失防护概述
ms.author: deniseb
author: denisebmsft
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
description: 使用安全&amp;合规性中心中的数据丢失防护 (DLP) 策略, 可以识别、监视和自动保护 Office 365 之间的敏感信息。
ms.openlocfilehash: 35dbaf11685298f2db07c5c516f8d20237eaaf20
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854766"
---
# <a name="overview-of-data-loss-prevention"></a><span data-ttu-id="e4ffb-103">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="e4ffb-103">Overview of data loss prevention</span></span>

> [!NOTE]
> <span data-ttu-id="e4ffb-104">最近将数据丢失防护功能添加到 Microsoft 团队聊天和面向用户许可的 Office 365 高级合规性的频道消息 (可用作独立选项), 并包含在 Office 365 E5 和 Microsoft 365 E5 合规性中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-104">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="e4ffb-105">若要了解有关许可要求的详细信息, 请参阅[Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-105">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="e4ffb-106">若要遵守业务标准和行业管理法规, 组织必须保护敏感信息, 并防止无意中泄露。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-106">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="e4ffb-107">敏感信息可以包括财务数据或个人身份信息 (PII), 如信用卡号、社会保险号码或运行状况记录。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-107">Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="e4ffb-108">使用 Office 365 安全&amp;合规中心中的数据丢失防护 (DLP) 策略, 可以在 office 365 中识别、监视和自动保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-108">With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="e4ffb-109">您可以使用 DLP 策略实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-109">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="e4ffb-110">**跨 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 等多个位置标识敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="e4ffb-110">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**</span></span>
    
    <span data-ttu-id="e4ffb-111">例如, 您可以标识任何包含存储在任何 OneDrive for Business 网站中的信用卡号的文档, 也可以仅监视特定人员的 OneDrive 站点。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-111">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="e4ffb-112">**防止意外共享敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-112">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="e4ffb-113">例如, 您可以标识任何包含与组织外部人员共享的运行状况记录的文档或电子邮件, 然后自动阻止对该文档的访问或阻止发送该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-113">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="e4ffb-114">**监视和保护 Excel、PowerPoint 和 Word 桌面版中的敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="e4ffb-114">**Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**</span></span>
    
    <span data-ttu-id="e4ffb-115">就像在 Exchange Online、SharePoint Online 和 OneDrive for Business 中一样, 这些 Office 桌面程序都包含用于识别敏感信息和应用 DLP 策略的相同功能。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-115">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="e4ffb-116">当用户共享这些 Office 程序中的内容时, DLP 提供连续监控。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-116">DLP provides continuous monitoring when people share content in these Office programs.</span></span>
    
- <span data-ttu-id="e4ffb-117">**帮助用户了解如何保持兼容性，同时不会中断工作流。**</span><span class="sxs-lookup"><span data-stu-id="e4ffb-117">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="e4ffb-118">您可以向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-118">You can educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="e4ffb-119">例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-119">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span> <span data-ttu-id="e4ffb-120">Outlook 网页、Outlook、Excel、PowerPoint 和 Word 中也会显示相同的策略提示。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-120">The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.</span></span>
    
- <span data-ttu-id="e4ffb-121">**查看 DLP 报告，了解符合组织的 DLP 策略的内容。**</span><span class="sxs-lookup"><span data-stu-id="e4ffb-121">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="e4ffb-122">要评估您的组织遵守 DLP 策略的情况，您可以查看随着时间推移符合每个策略和每条规则的次数。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-122">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="e4ffb-123">如果 DLP 策略允许用户覆盖策略提示并报告误报, 则还可以查看用户报告的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-123">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="e4ffb-124">您可以在 Office 365 安全&amp;合规中心中的 "数据丢失防护" 页上创建和管理 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-124">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 安全&amp;合规中心中的 "数据丢失防护" 页](media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="e4ffb-126">DLP 策略包含的内容</span><span class="sxs-lookup"><span data-stu-id="e4ffb-126">What a DLP policy contains</span></span>

<span data-ttu-id="e4ffb-127">DLP 策略包含以下基本内容：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-127">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="e4ffb-128">在何处保护内容:**位置**(如 Exchange Online、SharePoint Online 和 OneDrive for business 网站), 以及 Microsoft 团队聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-128">Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages.</span></span> 
    
- <span data-ttu-id="e4ffb-129">何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-129">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="e4ffb-130">在强制执行规则之前内容必须匹配的**条件**。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-130">**Conditions** the content must match before the rule is enforced.</span></span> <span data-ttu-id="e4ffb-131">例如, 规则可能配置为仅查找包含与您的组织外部人员共享的社会安全号码的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-131">For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="e4ffb-132">当找到与条件匹配的内容时, 您希望规则自动执行的**操作**。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-132">**Actions** that you want the rule to take automatically when content matching the conditions is found.</span></span> <span data-ttu-id="e4ffb-133">例如, 可以将规则配置为阻止对文档的访问, 并同时向用户和合规性监察官发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-133">For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="e4ffb-134">您可以使用规则来满足特定的保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如要符合特定法规所需的所有规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-134">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="e4ffb-135">例如，DLP 策略可能会帮助您检测是否存在受 Health Insurance Portability and Accountability Act (HIPAA) 约束的信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-135">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="e4ffb-136">此 DLP 策略可以通过查找包含与组织外部人员共享的这些敏感信息的任何文档来帮助保护所有 SharePoint Online 网站和所有 OneDrive for Business 网站 (在 where) 上的 HIPAA 数据 (这些内容)。条件), 然后阻止对文档的访问和发送通知 (操作)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-136">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="e4ffb-137">这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-137">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![图中显示了 DLP 策略包含位置和规则](media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="e4ffb-139">位置</span><span class="sxs-lookup"><span data-stu-id="e4ffb-139">Locations</span></span>

<span data-ttu-id="e4ffb-140">DLP 策略可以跨 Office 365 查找和保护敏感信息, 无论这些信息位于 Exchange Online、SharePoint Online、OneDrive for Business 中还是 Microsoft 团队中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-140">A DLP policy can find and protect sensitive information across Office 365, whether that information is located in Exchange Online, SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="e4ffb-141">您可以选择保护 Exchange 电子邮件、Microsoft 团队聊天和频道消息中的内容, 以及所有 SharePoint 或 OneDrive 库, 或选择策略的特定位置。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-141">You can choose to protect content in Exchange email, Microsoft Teams chats and channel messages, and all SharePoint or OneDrive libraries, or select specific locations for a policy.</span></span>
  
![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
<span data-ttu-id="e4ffb-143">如果选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户, DLP 策略不能包含100以上的包含和排除项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-143">If you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="e4ffb-144">虽然这一限制存在, 但您可以通过应用组织范围策略或适用于整个位置的策略来超过此限制。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-144">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="e4ffb-145">规则</span><span class="sxs-lookup"><span data-stu-id="e4ffb-145">Rules</span></span>

<span data-ttu-id="e4ffb-146">规则是在组织内容中实施业务需求的。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-146">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="e4ffb-147">策略包含一条或多条规则，每条规则由多个条件和操作组成。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-147">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="e4ffb-148">对于每条规则，只要满足了条件，就会自动执行操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-148">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="e4ffb-149">规则是按顺序执行的, 从每个策略中的最高优先级规则开始。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-149">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="e4ffb-150">规则还提供通知用户 (带有策略提示和电子邮件通知) 和管理员 (电子邮件事件报告) 内容与规则匹配的选项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-150">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="e4ffb-151">以下是规则的组件, 如下所述。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-151">Here are the components of a rule, each explained below.</span></span>
  
![DLP 规则编辑器的各个部分](media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="e4ffb-153">条件</span><span class="sxs-lookup"><span data-stu-id="e4ffb-153">Conditions</span></span>

<span data-ttu-id="e4ffb-154">条件非常重要, 因为它们决定了要查找的信息类型以及何时执行操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-154">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="e4ffb-155">例如, 您可以选择忽略包含护照号码的内容, 除非内容包含10个以上的号码, 并且与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-155">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="e4ffb-156">条件侧重于**内容**, 如要查找的敏感信息类型以及**上下文**(例如, 与谁共享文档的用户)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-156">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="e4ffb-157">您可以使用条件将不同的操作分配给不同的风险级别。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-157">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="e4ffb-158">例如, 在内部共享的敏感内容可能会降低风险, 并且需要的操作比与组织外部人员共享的敏感内容更少。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-158">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![显示可用的 DLP 条件的列表](media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="e4ffb-160">现在的可用条件可以确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-160">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="e4ffb-161">内容包含一种敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-161">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="e4ffb-162">内容包含标签。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-162">Content contains a label.</span></span> <span data-ttu-id="e4ffb-163">有关详细信息, 请参阅下一节在[DLP 策略中使用标签作为条件](#using-a-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-163">For more information, see the below section [Using a label as a condition in a DLP policy](#using-a-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="e4ffb-164">内容是与您组织的外部还是内部人员共享。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-164">Content is shared with people outside or inside your organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="e4ffb-165">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e4ffb-165">Types of sensitive information</span></span>

<span data-ttu-id="e4ffb-166">DLP 策略可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-166">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="e4ffb-167">Office 365 包含对多个不同地区供您使用的众多常见敏感信息类型的定义，例如信用卡号、银行账号、国民身份证号及护照号等。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-167">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用敏感信息类型列表](media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="e4ffb-169">当 DLP 策略查找敏感信息类型 (如信用卡号) 时, 它并不只是查找16位的数字。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-169">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="e4ffb-170">通过以下组合对每种敏感信息类型进行定义和检测：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-170">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="e4ffb-171">关键字</span><span class="sxs-lookup"><span data-stu-id="e4ffb-171">Keywords</span></span>
    
- <span data-ttu-id="e4ffb-172">用于验证校验和或撰写的内部函数</span><span class="sxs-lookup"><span data-stu-id="e4ffb-172">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="e4ffb-173">用于查找模式匹配的正则表达式评估</span><span class="sxs-lookup"><span data-stu-id="e4ffb-173">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="e4ffb-174">其他内容检查</span><span class="sxs-lookup"><span data-stu-id="e4ffb-174">Other content examination</span></span>
    
<span data-ttu-id="e4ffb-175">这有助于 DLP 检测实现高度准确性, 同时减少可能中断工作的误报数。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-175">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="e4ffb-176">操作</span><span class="sxs-lookup"><span data-stu-id="e4ffb-176">Actions</span></span>

<span data-ttu-id="e4ffb-177">当内容与规则中的条件相匹配时, 您可以将操作应用于自动保护内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-177">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用 DLP 操作列表](media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="e4ffb-179">现在可以使用操作, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-179">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="e4ffb-180">**限制对内容的访问**对于 "网站内容", 这意味着对文档的权限仅限于主网站集管理员、文档所有者和上次修改文档的人员之外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-180">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="e4ffb-181">这些用户可以从文档中删除敏感信息或执行其他补救操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-181">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="e4ffb-182">当文档符合合规性时, 将自动还原原始权限。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-182">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="e4ffb-183">当对文档的访问受到阻止时，文档将在网站的库中显示一个特殊的策略提示图标。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-183">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![显示文档访问被拦截的策略提示](media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="e4ffb-185">对于电子邮件内容, 此操作阻止发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-185">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="e4ffb-186">根据配置 DLP 规则的方式, 发件人会看到一个 NDR 或 (如果该规则使用通知) 策略提示和/或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-186">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![警告: 必须从邮件中删除未经授权的收件人](media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="e4ffb-188">用户通知和用户替代</span><span class="sxs-lookup"><span data-stu-id="e4ffb-188">User notifications and user overrides</span></span>

<span data-ttu-id="e4ffb-189">您可以使用通知和替代来向用户介绍 DLP 策略, 并帮助他们保持合规性, 而不阻止其工作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-189">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="e4ffb-190">例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-190">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP 规则编辑器的用户通知和用户替代部分](media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="e4ffb-192">电子邮件可通知发送、共享或上次修改内容的人员, 以及网站内容、网站内容、主网站集管理员和文档所有者。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-192">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="e4ffb-193">此外, 还可以在电子邮件通知中添加或删除您选择的人。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-193">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="e4ffb-194">除了发送电子邮件通知之外, 用户通知还会显示策略提示:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-194">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="e4ffb-195">在 Outlook 和 web 上的 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-195">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="e4ffb-196">对于 SharePoint Online 或 OneDrive for business 网站上的文档。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-196">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="e4ffb-197">在 Excel、PowerPoint 和 Word 中, 当文档存储在包含在 DLP 策略中的网站上时。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-197">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="e4ffb-198">电子邮件通知和策略提示说明了内容与 DLP 策略冲突的原因。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-198">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="e4ffb-199">如果您选择，电子邮件通知和策略提示可以允许用户通过报告误报或提供业务理由来替代规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-199">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="e4ffb-200">这可以帮助您让用户了解您的 DLP 策略和强制执行它们，而不会阻止用户完成其工作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-200">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="e4ffb-201">有关替代和误报的信息还记录报告（请参阅下文提供的 DLP 报告）并且包含在事件报告（下一节）中，以便合规部主管可以定期查看此信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-201">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="e4ffb-202">以下是策略提示在 OneDrive for Business 帐户中的外观。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-202">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![OneDrive 帐户中文档的策略提示](media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)
  
#### <a name="incident-reports"></a><span data-ttu-id="e4ffb-204">事件报告</span><span class="sxs-lookup"><span data-stu-id="e4ffb-204">Incident reports</span></span>

<span data-ttu-id="e4ffb-205">匹配规则时, 可以使用事件详细信息向合规专员 (或任何人选择的任何人) 发送事件报告。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-205">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event.</span></span> <span data-ttu-id="e4ffb-206">此报告包含有关匹配项目、与规则匹配的实际内容以及上次修改内容的人员的姓名的信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-206">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="e4ffb-207">对于电子邮件, 该报告还包括与 DLP 策略匹配的原始邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-207">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![用于配置事件报告的页面](media/31c6da0e-981c-415e-91bf-d94ca391a893.png)
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="e4ffb-209">分组和逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="e4ffb-209">Grouping and logical operators</span></span>

<span data-ttu-id="e4ffb-210">您的 DLP 策略通常具有一个简单的要求, 例如, 标识所有包含美国社会保险号码的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-210">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="e4ffb-211">但是, 在其他情况下, 您的 DLP 策略可能需要标识更松散定义的数据。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-211">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="e4ffb-212">例如, 若要确定符合美国卫生保险业法案 (HIPAA) 的内容, 您需要查找以下内容:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-212">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="e4ffb-213">包含特定类型的敏感信息的内容, 如美国社会保险号或药品强制代理 (DEA) 号码。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-213">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="e4ffb-214">AND</span><span class="sxs-lookup"><span data-stu-id="e4ffb-214">AND</span></span>
    
- <span data-ttu-id="e4ffb-215">较难识别的内容, 如有关患者护理的通信或提供的医疗服务说明。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-215">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="e4ffb-216">标识此内容需要匹配非常大的关键字列表中的匹配关键字, 如 Diseases 的国际分类 (ICD-9-CM 或 ICD-10 厘米)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-216">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="e4ffb-217">您可以通过使用分组和逻辑运算符 (AND 和 OR) 轻松地识别这些松散定义的数据。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-217">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="e4ffb-218">创建 DLP 策略时, 可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-218">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="e4ffb-219">对敏感信息类型进行分组。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-219">Group sensitive information types.</span></span>
    
- <span data-ttu-id="e4ffb-220">选择组中的敏感信息类型与组本身之间的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-220">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="e4ffb-221">在组中选择运算符</span><span class="sxs-lookup"><span data-stu-id="e4ffb-221">Choosing the operator within a group</span></span>

<span data-ttu-id="e4ffb-222">在组中, 可以选择是否必须满足该组中的任何或所有条件, 才能匹配该规则的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-222">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![显示组中的运算符的组](media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="e4ffb-224">添加组</span><span class="sxs-lookup"><span data-stu-id="e4ffb-224">Adding a group</span></span>

<span data-ttu-id="e4ffb-225">您可以快速添加组, 该组将其自己的条件和运算符放在该组中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-225">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
!["添加组" 按钮](media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="e4ffb-227">在组之间选择运算符</span><span class="sxs-lookup"><span data-stu-id="e4ffb-227">Choosing the operator between groups</span></span>

<span data-ttu-id="e4ffb-228">在组之间, 可以选择仅一个组中的条件, 还是必须满足所有组中的条件, 以匹配该规则的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-228">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="e4ffb-229">例如, 内置的**美国 HIPAA**策略有一条规则, 该规则在组之间使用**AND**运算符, 以便识别包含以下内容的内容:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-229">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="e4ffb-230">来自组**PII 标识符**(至少一个 SSN 号码**或**DEA 号码)</span><span class="sxs-lookup"><span data-stu-id="e4ffb-230">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="e4ffb-231">**AND**</span><span class="sxs-lookup"><span data-stu-id="e4ffb-231">**AND**</span></span>
    
- <span data-ttu-id="e4ffb-232">来自 group**医学条款**(至少有一个 ICD-9 Cm 关键字**或**ICD-10 cm 关键字)</span><span class="sxs-lookup"><span data-stu-id="e4ffb-232">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![显示组之间的运算符的组](media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="e4ffb-234">处理规则的优先级</span><span class="sxs-lookup"><span data-stu-id="e4ffb-234">The priority by which rules are processed</span></span>

<span data-ttu-id="e4ffb-235">在策略中创建规则时, 将按创建顺序为每个规则分配一个优先级—也就是说, 首先创建的规则具有第一个优先级, 创建的规则第二个优先级为第二个优先级, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-235">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> 
  
![优先级顺序中的规则](media/f7dc06bf-bc6f-485c-bcdb-606edbcf6565.png)
  
<span data-ttu-id="e4ffb-237">设置多个 DLP 策略后, 可以更改一个或多个策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-237">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="e4ffb-238">若要执行此操作, 请选择策略, 选择 "**编辑策略**", 并使用 "**优先级**" 列表来指定其优先级。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-238">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

![设置策略的优先级](media/dlp-set-policy-priority.png)

<span data-ttu-id="e4ffb-240">按照规则对内容进行评估时, 将按优先级顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-240">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="e4ffb-241">如果内容与多个规则匹配, 将按优先级顺序处理规则, 并强制执行限制性最强的操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-241">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="e4ffb-242">例如, 如果内容与以下所有规则相匹配, 则强制执行规则 3, 因为它的优先级最高, 最受限制的规则如下:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-242">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="e4ffb-243">规则 1: 仅通知用户</span><span class="sxs-lookup"><span data-stu-id="e4ffb-243">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="e4ffb-244">规则 2: 通知用户、限制访问并允许用户重写</span><span class="sxs-lookup"><span data-stu-id="e4ffb-244">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="e4ffb-245">规则 3: 通知用户、限制访问和不允许用户替代</span><span class="sxs-lookup"><span data-stu-id="e4ffb-245">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="e4ffb-246">规则 4: 仅通知用户</span><span class="sxs-lookup"><span data-stu-id="e4ffb-246">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="e4ffb-247">规则 5: 限制访问</span><span class="sxs-lookup"><span data-stu-id="e4ffb-247">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="e4ffb-248">规则 6: 通知用户、限制访问和不允许用户替代</span><span class="sxs-lookup"><span data-stu-id="e4ffb-248">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="e4ffb-249">在此示例中, 请注意, 所有规则的匹配项都记录在审核日志中, 并显示在 DLP 报告中, 即使仅强制实施最严格的规则也是如此。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-249">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="e4ffb-250">有关策略提示, 请注意:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-250">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="e4ffb-251">仅来自最高优先级的策略提示将显示最受限制的规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-251">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="e4ffb-252">例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-252">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="e4ffb-253">这会让用户看不到策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-253">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="e4ffb-254">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-254">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="e4ffb-255">调整规则以使其更易于或更难匹配</span><span class="sxs-lookup"><span data-stu-id="e4ffb-255">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="e4ffb-256">在用户创建并打开其 DLP 策略后, 它们有时会遇到以下问题:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-256">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="e4ffb-257">太多**不**敏感的内容信息与规则相匹配, 换句话说, 误报太多。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-257">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="e4ffb-258">与规则匹配的\*\*\*\* 内容太少, 敏感信息太少。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-258">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="e4ffb-259">换句话说, 保护性操作不会对敏感信息强制实施。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-259">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="e4ffb-260">若要解决这些问题, 您可以调整实例数和匹配精度以使内容更难或更轻松地与规则相匹配, 从而调整规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-260">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="e4ffb-261">规则中使用的每种敏感信息类型都具有实例计数和匹配精度。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-261">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="e4ffb-262">实例计数</span><span class="sxs-lookup"><span data-stu-id="e4ffb-262">Instance count</span></span>

<span data-ttu-id="e4ffb-263">"实例计数" 表示内容必须有多少个特定类型的敏感信息, 才能匹配该规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-263">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="e4ffb-264">例如, 如果介于1和9唯一美国或英国, 则内容与下面显示的规则相匹配</span><span class="sxs-lookup"><span data-stu-id="e4ffb-264">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="e4ffb-265">识别护照号码。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-265">passport numbers are identified.</span></span>
  
<span data-ttu-id="e4ffb-266">请注意, 实例计数只包含敏感信息类型和关键字的**唯一**匹配项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-266">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="e4ffb-267">例如, 如果电子邮件包含10个相同信用卡号码, 则这些10个事件将计为一个信用卡号码的单个实例。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-267">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="e4ffb-268">若要使用实例计数来调整规则, 本指南非常简单:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-268">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="e4ffb-269">若要使规则更易于匹配, 请减小**最小**计数和/或增加**最大**计数。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-269">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="e4ffb-270">您还可以通过删除数值将**max**设置为**any** 。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-270">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="e4ffb-271">若要使规则更难匹配, 请增加**最小**计数。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-271">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="e4ffb-272">通常情况下, 在具有较低实例计数的规则 (例如, 1-9) 中使用限制性更少的操作 (如发送用户通知)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-272">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="e4ffb-273">并且, 在具有更高实例计数的规则 (例如, 10-any) 中使用限制性更强的操作, 例如限制对内容的访问而不允许用户覆盖。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-273">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![规则编辑器中的实例计数](media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="e4ffb-275">匹配精确性</span><span class="sxs-lookup"><span data-stu-id="e4ffb-275">Match accuracy</span></span>

<span data-ttu-id="e4ffb-276">如上文所述, 使用不同类型的证据定义和检测敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-276">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="e4ffb-277">通常, 敏感信息类型由多个此类组合 (称为 "模式") 定义。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-277">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="e4ffb-278">需要较少证据的模式具有较低的匹配精度 (或置信度级别), 而需要更多证据的模式具有更高的匹配精度 (或置信度级别)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-278">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="e4ffb-279">若要了解有关每种敏感信息类型使用的实际模式和可信度级别的详细信息, 请参阅[敏感信息类型查找的内容](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-279">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="e4ffb-280">例如, 名为 "信用卡号码" 的敏感信息类型由两种模式定义:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-280">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="e4ffb-281">具有 65% 可信度的模式, 需要满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-281">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="e4ffb-282">信用卡号码格式的数字。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-282">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="e4ffb-283">传递校验和的数字。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-283">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="e4ffb-284">具有 85% 可信度的模式, 需要满足以下条件:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-284">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="e4ffb-285">信用卡号码格式的数字。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-285">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="e4ffb-286">传递校验和的数字。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-286">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="e4ffb-287">使用正确的格式的关键字或过期日期。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-287">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="e4ffb-288">您可以在规则中使用这些可信度级别 (或 "匹配精度")。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-288">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="e4ffb-289">通常情况下, 在匹配精度较低的规则中使用限制性更少的操作 (如发送用户通知)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-289">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="e4ffb-290">您可以使用限制性更强的操作 (如在不允许用户替代的情况下限制对内容的访问), 在具有更高的匹配精确性的规则中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-290">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="e4ffb-291">请务必了解, 如果内容中标识了特定类型的敏感信息 (如信用卡号), 则仅返回一个置信度:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-291">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="e4ffb-292">如果所有匹配项都针对单个模式, 则返回该模式的置信度级别。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-292">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="e4ffb-293">如果有多个模式的匹配项 (即, 有两个不同的可信度级别的匹配项), 则将返回高于任何单个模式的置信度。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-293">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="e4ffb-294">这是一个棘手的部分。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-294">This is the tricky part.</span></span> <span data-ttu-id="e4ffb-295">例如, 对于信用卡, 如果 65% 和 85% 两个模式都匹配, 则为该敏感信息类型返回的置信度级别将大于 90%, 因为更多的证据意味着更自信。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-295">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="e4ffb-296">因此, 如果要为信用卡创建两个相互排斥的规则, 一个是 65% 匹配精度, 另一个为 85% 匹配精度, 则匹配精度的范围将如下所示。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-296">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="e4ffb-297">第一条规则仅选取 65% 模式的匹配项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-297">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="e4ffb-298">第二个规则将选取与**至少一个**85% 匹配的匹配项, 并且**可能会有**其他较低可信度的匹配项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-298">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![具有不同范围的两个规则匹配精确性](media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="e4ffb-300">出于这些原因, 使用不同的匹配精度创建规则的指南如下:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-300">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="e4ffb-301">最低置信度通常对**min**和**max** (不是区域) 使用相同的值。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-301">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="e4ffb-302">最高置信度通常是从较低置信度到100的范围。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-302">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="e4ffb-303">任何置信度级别通常都介于较低置信度级别的正上方和低于较高置信度的下方。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-303">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="e4ffb-304">在 DLP 策略中使用标签作为条件</span><span class="sxs-lookup"><span data-stu-id="e4ffb-304">Using a label as a condition in a DLP policy</span></span>

<span data-ttu-id="e4ffb-305">您可以创建一个标签, 然后执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-305">You can create a label and then:</span></span>
  
- <span data-ttu-id="e4ffb-306">**发布**, 以便最终用户可以查看和手动将标签应用于内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-306">**Publish** it, so that end users can see and manually apply the label to content.</span></span> 
    
- <span data-ttu-id="e4ffb-307">**自动将其应用**于与您选择的条件相匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-307">**Auto-apply** it to content that matches the conditions that you choose.</span></span> 
    
<span data-ttu-id="e4ffb-308">有关标签的详细信息, 请参阅[保留标签概述](labels.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-308">For more information about labels, see [Overview of retention labels](labels.md).</span></span>
  
<span data-ttu-id="e4ffb-309">创建标签后, 可以将该标签用作 DLP 策略中的条件。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-309">After you create a label, you can then use that label as a condition in your DLP policies.</span></span> <span data-ttu-id="e4ffb-310">例如, 您可能希望执行此操作, 因为:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-310">For example, you might want to do this because:</span></span>
  
- <span data-ttu-id="e4ffb-311">您发布了一个名为 "**机密**" 的标签, 以便组织中的人员可以手动将该标签应用于机密电子邮件和文档。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-311">You published a label named **Confidential**, so that people in your organization can manually apply the label to confidential email and documents.</span></span> <span data-ttu-id="e4ffb-312">通过将此标签用作 DLP 策略中的条件, 可以将标记为 "**机密**" 的内容限制为与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-312">By using this label as a condition in your DLP policy, you can restrict content labeled **Confidential** from being shared with people outside your organization.</span></span> 
    
- <span data-ttu-id="e4ffb-313">您为该名称的项目创建了一个名为**Alpine 房子**的标签, 然后将该标签自动应用于包含关键字 "Alpine 房子" 的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-313">You created a label named **Alpine House** for a project of that name, and then applied that label automatically to content containing the keywords "Alpine House".</span></span> <span data-ttu-id="e4ffb-314">通过将此标签用作 DLP 策略中的条件, 可以在即将与组织外部的人员共享此内容时向最终用户显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-314">By using this label as a condition in your DLP policy, you can show a policy tip to end users when they're about to share this content with someone outside your organization.</span></span> 
    
- <span data-ttu-id="e4ffb-315">您发布了一个名为 "**税收 record**" 的标签, 以便您的记录管理员可以手动将该标签应用于需要分类为记录的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-315">You published a label named **Tax record**, so that your records manager can manually apply the label to content that needs to be classified as a record.</span></span> <span data-ttu-id="e4ffb-316">通过将此标签用作 DLP 策略中的条件, 可以使用此标签以及其他类型的敏感信息 (如 ITINs 或 Ssn) 查找内容;将保护操作应用于标记为 "**税收记录**" 的内容;并从 DLP 报告和审核日志数据中获取有关 DLP 策略的详细活动报告。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-316">By using this label as a condition in your DLP policy, you can look for content with this label along with other types of sensitive information such as ITINs or SSNs; apply protection actions to content labeled **Tax record**; and get detailed activity reports about the DLP policy from the DLP reports and audit log data.</span></span> 
    
- <span data-ttu-id="e4ffb-317">您发布了一个名为**Executive 领导团队**的标签-对一组主管的 Exchange 邮箱和 OneDrive 帐户敏感。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-317">You published a label named **Executive Leadership Team - Sensitive** to the Exchange mailboxes and OneDrive accounts of a group of executives.</span></span> <span data-ttu-id="e4ffb-318">通过将此标签用作 DLP 策略中的条件, 可以同时对同一子集的内容和用户实施保留和保护操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-318">By using this label as a condition in your DLP policy, you can enforce both retention and protection actions on the same subset of content and users.</span></span> 
    
<span data-ttu-id="e4ffb-319">通过将标签用作 DLP 规则中的条件, 可以有选择地对一组特定的内容、位置或用户强制实施保护操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-319">By using labels as a condition in your DLP rules, can you selectively enforce protection actions on a specific set of content, locations, or users.</span></span>
  
![标签作为条件](media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="e4ffb-321">对敏感度标签的支持即将推出</span><span class="sxs-lookup"><span data-stu-id="e4ffb-321">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="e4ffb-322">当前可以仅将保留标签用作条件, 而不能使用[敏感度标签](sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-322">You can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="e4ffb-323">目前, 我们正在为在此条件中使用灵敏度标签提供支持。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-323">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="e4ffb-324">此功能与其他功能的关联方式</span><span class="sxs-lookup"><span data-stu-id="e4ffb-324">How this feature relates to other features</span></span>

<span data-ttu-id="e4ffb-325">可将多个功能应用于包含敏感信息的内容:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-325">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="e4ffb-326">[保留标签](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)均可对此内容强制执行**保留**操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-326">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="e4ffb-327">DLP 策略可以对此内容强制实施**保护**操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-327">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="e4ffb-328">在强制执行这些操作之前, DLP 策略可能需要满足其他条件, 除了包含标签的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-328">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![可应用于敏感信息的功能的关系图](media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="e4ffb-330">请注意, DLP 策略具有更丰富的检测功能, 而不是应用于敏感信息的标签或保留策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-330">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="e4ffb-331">DLP 策略可以对包含敏感信息的内容强制执行保护操作, 如果从内容中删除了敏感信息, 则下次扫描内容时将撤消这些保护操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-331">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="e4ffb-332">但是, 如果保留策略或标签应用于包含敏感信息的内容, 则即使删除了敏感信息, 也不会撤消该一次性操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-332">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="e4ffb-333">通过将标签用作 DLP 策略中的条件, 可以使用该标签对内容强制执行保留和保护操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-333">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="e4ffb-334">您可以考虑包含标签的内容与包含敏感信息的内容完全一样-标签和敏感信息类型都是用于对内容进行分类的属性, 以便您可以对该内容强制执行操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-334">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![使用 label 作为条件的 DLP 策略关系图](media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="e4ffb-336">简单设置与高级设置</span><span class="sxs-lookup"><span data-stu-id="e4ffb-336">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="e4ffb-337">当您创建 DLP 策略时, 您将在简单或高级设置之间进行选择:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-337">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="e4ffb-338">**简单设置**使您可以轻松地创建最常用类型的 DLP 策略, 而无需使用规则编辑器来创建或修改规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-338">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="e4ffb-339">**高级设置**使用规则编辑器为您提供对 DLP 策略的每个设置的完全控制。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-339">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="e4ffb-340">无需担心, "简单设置" 和 "高级" 设置的工作方式完全相同, 只是通过使用简单设置来强制执行包含条件和操作的规则, 而不会看到 "规则编辑器"。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-340">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="e4ffb-341">这是创建 DLP 策略的快速方法。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-341">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="e4ffb-342">简单设置</span><span class="sxs-lookup"><span data-stu-id="e4ffb-342">Simple settings</span></span>

<span data-ttu-id="e4ffb-343">到目前为止, 最常见的 DLP 方案是创建一个策略, 以帮助保护包含敏感信息的内容与组织外部的人员共享, 并采取自动补救措施, 如限制谁可以访问内容,发送最终用户或管理员通知, 并审核事件以供日后调查。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-343">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remedial action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="e4ffb-344">用户使用 DLP 有助于防止无意中泄露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-344">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="e4ffb-345">若要简化实现此目标的目的, 在创建 DLP 策略时, 可以选择 "**使用简单设置**"。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-345">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="e4ffb-346">这些设置提供了实现最常用 DLP 策略所需的一切, 而无需进入规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-346">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![适用于简单和高级设置的 DLP 选项](media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="e4ffb-348">高级设置</span><span class="sxs-lookup"><span data-stu-id="e4ffb-348">Advanced settings</span></span>

<span data-ttu-id="e4ffb-349">如果您需要创建更多自定义的 DLP 策略, 则可以选择 "**使用高级设置**"。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-349">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="e4ffb-350">高级设置向您提供规则编辑器, 在其中可以完全控制每个可能的选项, 包括每个规则的实例计数和匹配精度 (置信度级别)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-350">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="e4ffb-351">若要快速跳转到某一节, 请单击规则编辑器顶部导航中的某个项目, 以转到下面的部分。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-351">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 规则编辑器的顶部导航菜单](media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="e4ffb-353">DLP 策略模板</span><span class="sxs-lookup"><span data-stu-id="e4ffb-353">DLP policy templates</span></span>

<span data-ttu-id="e4ffb-354">创建 DLP 策略的第一步是选择要保护的信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-354">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="e4ffb-355">通过从 DLP 模板开始, 可以保存从头开始创建一组新的规则的工作, 并在默认情况下, 找出应包含哪些类型的信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-355">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="e4ffb-356">然后, 您可以添加或修改这些要求, 以微调规则以满足组织的特定要求。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-356">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="e4ffb-357">预配置的 DLP 策略模板可帮助您检测特定类型的敏感信息, 如 HIPAA 数据、PCI-DSS 数据、格雷姆-比利雷 Act 数据, 甚至是特定于区域设置的个人身份信息 (P.I.)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-357">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="e4ffb-358">要使您能够轻松地查找和保护常见类型的敏感信息，包含在 Office 365 中的策略模板已包含您要开始构建策略所需的最常见的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-358">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Office 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![数据丢失防护策略模板列表，重点放在美国模板上爱国者法案](media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="e4ffb-360">您的组织可能还具有自己的特定要求, 在这种情况下, 您可以通过选择 "**自定义策略**" 选项从头开始创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-360">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="e4ffb-361">自定义策略为空且不包含任何 premade 规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-361">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="e4ffb-362">在测试模式下逐步部署 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e4ffb-362">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="e4ffb-363">创建 DLP 策略时，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-363">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="e4ffb-364">例如, 您不希望新的 DLP 策略无意中阻止用户需要访问的数千个文档的访问权限, 以便完成其工作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-364">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="e4ffb-365">如果您创建的 DLP 策略具有很大的潜在影响, 我们建议按照以下顺序进行操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-365">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="e4ffb-366">**在测试模式下启动 (不带策略提示**), 然后使用 DLP 报告和任何事件报告来评估影响。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-366">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="e4ffb-367">您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-367">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="e4ffb-368">根据结果，您可以在需要时微调规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-368">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="e4ffb-369">在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-369">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="e4ffb-p156">**移动到使用通知和策略提示的测试模式**，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-p156">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="e4ffb-372">**对策略启动完全强制**, 以便应用规则中的操作和内容受保护。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-372">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="e4ffb-373">继续监视 DLP 报告及任何事件报告或通知，确保结果是您所期望的。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-373">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
<span data-ttu-id="e4ffb-375">您可以随时禁用 DLP 策略，这会影响策略中的所有规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-375">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="e4ffb-376">但是, 也可以通过在规则编辑器中切换每条规则的状态来单独关闭这些规则。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-376">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>
  
![关闭策略中的规则的选项](media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

<span data-ttu-id="e4ffb-378">您还可以更改策略中的多个规则的优先级。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-378">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="e4ffb-379">若要执行此操作, 请打开策略以进行编辑。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-379">To do that, open a policy for editing.</span></span> <span data-ttu-id="e4ffb-380">在某个规则的行中, 选择省略号 (**...**), 然后选择一个选项, 如 "下移" 或 " \*\*\*\* **置于最后**"。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-380">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

![设置规则优先级](media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="e4ffb-382">DLP 报告</span><span class="sxs-lookup"><span data-stu-id="e4ffb-382">DLP reports</span></span>

<span data-ttu-id="e4ffb-383">创建并打开 DLP 策略后, 您需要验证它们是否按预期工作, 并帮助您保持合规性。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-383">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="e4ffb-384">使用 DLP 报告，您可以快速查看随着时间的推移 DLP 策略和规则匹配的次数，以及误报和替代数。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-384">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="e4ffb-385">对于每个报告，您都可以按位置、时间范围，甚至缩小为特定的策略、规则或操作来筛选这些匹配项。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-385">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="e4ffb-386">使用 DLP 报告，您可以获取业务见解并了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="e4ffb-386">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="e4ffb-387">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-387">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="e4ffb-388">发现违反组织的合规性策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-388">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="e4ffb-389">了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-389">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="e4ffb-390">此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-390">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全与合规中心中的报告仪表板](media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="e4ffb-392">DLP 策略的工作原理</span><span class="sxs-lookup"><span data-stu-id="e4ffb-392">How DLP policies work</span></span>

<span data-ttu-id="e4ffb-p161">DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-p161">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="e4ffb-397">策略会进行同步</span><span class="sxs-lookup"><span data-stu-id="e4ffb-397">Policies are synced</span></span>

<span data-ttu-id="e4ffb-398">在安全&amp;合规中心中创建 DLP 策略后, 它将存储在一个中央策略存储中, 然后同步到各种内容源, 其中包括:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-398">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="e4ffb-399">Exchange Online, 并从 web 上的 Outlook 和 Outlook 打开</span><span class="sxs-lookup"><span data-stu-id="e4ffb-399">Exchange Online, and from there to Outlook on the web and Outlook</span></span>
    
- <span data-ttu-id="e4ffb-400">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="e4ffb-400">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="e4ffb-401">SharePoint Online 站点</span><span class="sxs-lookup"><span data-stu-id="e4ffb-401">SharePoint Online sites</span></span>
    
- <span data-ttu-id="e4ffb-402">Office 桌面程序 (Excel、PowerPoint 和 Word)</span><span class="sxs-lookup"><span data-stu-id="e4ffb-402">Office desktop programs (Excel, PowerPoint, and Word)</span></span>

- <span data-ttu-id="e4ffb-403">Microsoft 团队频道和聊天消息</span><span class="sxs-lookup"><span data-stu-id="e4ffb-403">Microsoft Teams channels and chat messages</span></span>
    
<span data-ttu-id="e4ffb-404">在将该策略同步到正确的位置之后, 它将开始评估内容并强制执行操作。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-404">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="e4ffb-405">OneDrive for Business 和 SharePoint Online 站点中的策略评估</span><span class="sxs-lookup"><span data-stu-id="e4ffb-405">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="e4ffb-406">在所有 SharePoint Online 网站和 OneDrive for business 网站中, 文档会不断变化, 它们将不断地被创建、编辑、共享, 等等。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-406">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="e4ffb-407">这意味着文档可能随时会与 DLP 策略发生冲突，或变为合规状态。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-407">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="e4ffb-408">例如，一个用户上载的文档可能不包含与团队站点相关的敏感信息，但之后，另一个用户可能会编辑同一文档，并向文档添加敏感信息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-408">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="e4ffb-409">为此，DLP 策略经常检查后台中是否包含与策略相符的文档。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-409">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="e4ffb-410">您可以将这视为异步策略评估。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-410">You can think of this as asynchronous policy evaluation.</span></span>
  
#### <a name="how-it-works"></a><span data-ttu-id="e4ffb-411">运作方式</span><span class="sxs-lookup"><span data-stu-id="e4ffb-411">How it works</span></span>
 
<span data-ttu-id="e4ffb-412">当用户在其网站中添加或更改文档时, 搜索引擎会对内容进行扫描, 以便以后可以对其进行搜索。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-412">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="e4ffb-413">在这种情况下, 还会对内容进行扫描以查找敏感信息, 并检查是否已共享。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-413">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="e4ffb-414">找到的任何敏感信息都将安全存储在搜索索引中, 以便只有合规性团队可以访问它, 而不是典型用户。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-414">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="e4ffb-415">您已启用的每个 DLP 策略都将在后台运行 (异步), 检查与策略匹配的任何内容的搜索频率, 并应用操作以防止意外泄漏。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-415">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![显示 DLP 策略异步评估内容方式的关系图](media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<span data-ttu-id="e4ffb-p165">最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-p165">Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="e4ffb-420">DLP 评估可编制索引的任何内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-420">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="e4ffb-421">有关默认情况下进行爬网的文件类型的详细信息, 请参阅[SharePoint Server 中的默认已爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-421">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="e4ffb-422">Exchange Online、Outlook 和 Outlook 网页版中的策略评估</span><span class="sxs-lookup"><span data-stu-id="e4ffb-422">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="e4ffb-423">在创建包含 Exchange Online 作为位置的 DLP 策略时, 该策略将从 Office 365 安全&amp;合规中心同步到 Exchange online, 然后从 exchange online 同步到 web 上的 Outlook 和 outlook。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-423">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="e4ffb-424">在 Outlook 中撰写邮件时, 如果要创建的内容是根据 DLP 策略进行评估, 则用户可以查看策略提示。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-424">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="e4ffb-425">在邮件发送之后, 它将根据 DLP 策略进行评估, 作为邮件流的正常部分, 以及 Exchange 邮件流规则 (也称为传输规则) 和在 Exchange 管理中心中创建的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-425">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="e4ffb-426">DLP 策略同时扫描邮件和所有附件。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-426">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="e4ffb-427">Office 桌面程序中的策略评估</span><span class="sxs-lookup"><span data-stu-id="e4ffb-427">Policy evaluation in the Office desktop programs</span></span>

<span data-ttu-id="e4ffb-428">Excel、PowerPoint 和 Word 包含标识敏感信息的相同功能, 并将 DLP 策略应用为 SharePoint Online 和 OneDrive for business。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-428">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="e4ffb-429">这些 Office 程序直接从中央策略存储同步其 DLP 策略, 然后在用户处理从包含在 DLP 策略中的网站中打开的文档时, 将继续评估 DLP 策略的内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-429">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="e4ffb-430">Office 中的 DLP 策略评估设计不会影响程序的性能或对内容进行处理的人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-430">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="e4ffb-431">如果他们正在处理大型文档, 或者用户的计算机忙, 可能需要几秒钟的时间才能显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-431">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="e4ffb-432">Microsoft 团队中的策略评估</span><span class="sxs-lookup"><span data-stu-id="e4ffb-432">Policy evaluation in Microsoft Teams</span></span>
 
<span data-ttu-id="e4ffb-433">在创建将 Microsoft 团队作为位置包含的 DLP 策略时, 该策略将从 Office 365 安全&amp;合规中心同步到用户帐户以及 Microsoft 团队频道和聊天消息。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-433">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="e4ffb-434">当有人尝试在 Microsoft 团队聊天或频道消息中共享敏感信息时, 可能会阻止或取消邮件, 具体取决于配置 DLP 策略的方式。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-434">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="e4ffb-435">而且, 包含敏感信息且与来宾共享的文档 (外部用户) 将不会为这些用户打开。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-435">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="e4ffb-436">若要了解详细信息, 请参阅[数据丢失防护和 Microsoft 团队](dlp-microsoft-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-436">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="e4ffb-437">权限</span><span class="sxs-lookup"><span data-stu-id="e4ffb-437">Permissions</span></span>

<span data-ttu-id="e4ffb-438">要创建 DLP 策略的合规性团队的成员需要安全&amp;合规中心的权限。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-438">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="e4ffb-439">默认情况下, 你的租户管理员将有权访问此位置, 并且可以向合规专员和其他人授予&amp;对安全合规中心的访问权限, 而无需为其授予租户管理员的所有权限。为此, 我们建议您执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-439">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="e4ffb-440">在 Office 365 中创建组并向其添加合规部主管。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-440">Create a group in Office 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="e4ffb-441">在安全&amp;合规性中心的 "**权限**" 页上创建角色组。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-441">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="e4ffb-442">将 Office 365 组添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-442">Add the Office 365 group to the role group.</span></span>
    
<span data-ttu-id="e4ffb-443">有关详细信息，请参阅[Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-443">For more information, see [Give users access to the Office 365 Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="e4ffb-444">只有在创建和应用 DLP 策略时才需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-444">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="e4ffb-445">策略执行不需要访问此内容。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-445">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="e4ffb-446">查找 DLP cmdlet</span><span class="sxs-lookup"><span data-stu-id="e4ffb-446">Find the DLP cmdlets</span></span>

<span data-ttu-id="e4ffb-447">若要将大多数 cmdlet 用于安全&amp;合规性中心, 您需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-447">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="e4ffb-448">使用远程 PowerShell 连接到 Office 365 安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="e4ffb-448">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. <span data-ttu-id="e4ffb-449">使用任何[符合策略和合规性的 dlp cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="e4ffb-449">Use any of these [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span></span>
    
<span data-ttu-id="e4ffb-450">但是, DLP 报告需要跨 Office 365 请求获取数据, 包括 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-450">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="e4ffb-451">出于此原因, 在**Exchange Online powershell 中提供了 DLP 报告的 cmdlet--不在安全&amp;合规中心 powershell**中。</span><span class="sxs-lookup"><span data-stu-id="e4ffb-451">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="e4ffb-452">因此, 若要使用 DLP 报告的 cmdlet, 需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-452">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="e4ffb-453">Connect to Exchange Online using remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4ffb-453">Connect to Exchange Online using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. <span data-ttu-id="e4ffb-454">为 DLP 报告使用以下任一 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e4ffb-454">Use any of these cmdlets for the DLP reports:</span></span>
    
  - [<span data-ttu-id="e4ffb-455">Get-dlpdetectionsreport</span><span class="sxs-lookup"><span data-stu-id="e4ffb-455">Get-DlpDetectionsReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)
    
  - [<span data-ttu-id="e4ffb-456">Get-dlpdetailreport</span><span class="sxs-lookup"><span data-stu-id="e4ffb-456">Get-DlpDetailReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a><span data-ttu-id="e4ffb-457">更多信息</span><span class="sxs-lookup"><span data-stu-id="e4ffb-457">More information</span></span>

- [<span data-ttu-id="e4ffb-458">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="e4ffb-458">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="e4ffb-459">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="e4ffb-459">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="e4ffb-460">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="e4ffb-460">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="e4ffb-461">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="e4ffb-461">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="e4ffb-462">敏感信息类型查找的内容</span><span class="sxs-lookup"><span data-stu-id="e4ffb-462">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="e4ffb-463">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="e4ffb-463">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="e4ffb-464">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="e4ffb-464">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
    

