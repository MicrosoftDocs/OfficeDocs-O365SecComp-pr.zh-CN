---
title: 从模板创建 DLP 策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
description: '开始使用 DLP 策略的最简单、最常见方法是，使用包含在 Office 365 中的模板之一。 '
ms.openlocfilehash: 2a1802592edbc3cfbcc05f5db979a0b4c3988e0d
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410947"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="9f795-103">通过模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="9f795-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="9f795-104">开始使用 DLP 策略的最简单、最常见方法是，使用包含在 Office 365 中的模板之一。</span><span class="sxs-lookup"><span data-stu-id="9f795-104">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365.</span></span> <span data-ttu-id="9f795-105">您可以按自己的方式使用其中一个模板, 也可以自定义规则以满足组织的特定合规性要求。</span><span class="sxs-lookup"><span data-stu-id="9f795-105">You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="9f795-p102">Office 365 包括可以帮助您满足范围广泛的常见法规和业务策略需求的 40 多个随时可以使用的模板。例如，提供适用于以下法规的 DLP 策略模板：</span><span class="sxs-lookup"><span data-stu-id="9f795-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="9f795-108">格雷姆-里奇-比利雷法案 (GLBA)</span><span class="sxs-lookup"><span data-stu-id="9f795-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="9f795-109">支付卡行业数据安全标准 (PCI-DSS)</span><span class="sxs-lookup"><span data-stu-id="9f795-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="9f795-110">美国个人身份信息（美国 PII）</span><span class="sxs-lookup"><span data-stu-id="9f795-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="9f795-111">美国健康保险法案 (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="9f795-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="9f795-p103">您可以通过修改任何现有的规则或添加新规则来微调模板。例如，您可以将新的敏感信息类型添加到规则中，以及修改规则中的计数以使其更难以触发或更易于触发，使用户通过提供业务理由替代规则中的操作，或更改要向其发送通知和事件报告的用户。对于许多常见的合规性方案来说，DLP 策略模板都是一个灵活的起点。</span><span class="sxs-lookup"><span data-stu-id="9f795-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="9f795-115">您还可以选择不带有任何默认规则的自定义模板，从头开始配置您的 DLP 策略以满足组织的特定合规性要求。</span><span class="sxs-lookup"><span data-stu-id="9f795-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="9f795-116">示例: 标识所有 OneDrive for business 网站中的敏感信息, 并限制组织外部人员的访问权限</span><span class="sxs-lookup"><span data-stu-id="9f795-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="9f795-117">OneDrive for business 帐户使组织内的人员可以轻松协作和共享文档。</span><span class="sxs-lookup"><span data-stu-id="9f795-117">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents.</span></span> <span data-ttu-id="9f795-118">但对合规性监察官的常见关注是, 存储在 OneDrive for business 帐户中的敏感信息可能无意中与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="9f795-118">But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization.</span></span> <span data-ttu-id="9f795-119">DLP 策略可以帮助降低此风险。</span><span class="sxs-lookup"><span data-stu-id="9f795-119">A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="9f795-120">在此示例中, 您将创建一个用于标识美国 PII 数据的 DLP 策略, 其中包括单独的纳税人标识号 (ITIN)、社会保险号码和美国护照号码。</span><span class="sxs-lookup"><span data-stu-id="9f795-120">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers.</span></span> <span data-ttu-id="9f795-121">你将通过使用模板开始, 然后将修改模板以满足组织的合规性要求, 具体来说, 你将:</span><span class="sxs-lookup"><span data-stu-id="9f795-121">You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="9f795-122">添加几种类型的敏感信息—例如, 银行帐号和美国驾驶执照号码, 以便 DLP 策略可以保护更多敏感数据。</span><span class="sxs-lookup"><span data-stu-id="9f795-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="9f795-123">使策略更加敏感, 以便单个出现的敏感信息足以限制外部用户的访问。</span><span class="sxs-lookup"><span data-stu-id="9f795-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="9f795-124">允许用户通过提供业务理由或报告误报来替代这些操作。</span><span class="sxs-lookup"><span data-stu-id="9f795-124">Allow users to override the actions by providing a business justification or reporting a false positive.</span></span> <span data-ttu-id="9f795-125">这样一来, 你的 DLP 策略将不会阻止组织中的人员完成其工作, 前提是他们有一个有效的业务理由共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="9f795-125">This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="9f795-126">通过模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="9f795-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="9f795-127">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="9f795-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="9f795-128">使用工作或学校帐户登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9f795-128">Sign in to Office 365 using your work or school account.</span></span> <span data-ttu-id="9f795-129">现在你已处于 Office 365 安全&amp;合规中心。</span><span class="sxs-lookup"><span data-stu-id="9f795-129">You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="9f795-130">在安全&amp;合规\>中心左侧导航\> **数据丢失防护** \> **策略** \>中,**创建一个策略**。</span><span class="sxs-lookup"><span data-stu-id="9f795-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    !["创建策略" 按钮](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="9f795-132">选择保护您\> **接下来**需要的敏感信息类型的 DLP 策略模板。</span><span class="sxs-lookup"><span data-stu-id="9f795-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="9f795-133">在此示例中, 你将选择**隐私** \> (**美国) 个人身份信息 (PII) 数据**, 因为它已经包含了你要保护的大多数敏感信息类型, 你将在稍后添加一项。</span><span class="sxs-lookup"><span data-stu-id="9f795-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="9f795-134">在选择模板时, 可以阅读右侧的说明, 以了解模板保护的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="9f795-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![用于选择 DLP 策略模板的页面](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="9f795-136">将策略\>命名为**Next**。</span><span class="sxs-lookup"><span data-stu-id="9f795-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="9f795-137">若要选择要保护 DLP 策略的位置, 请执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="9f795-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="9f795-138">选择\> **下一步\*\*\*\*中的 "Office 365 中的所有位置"** 。</span><span class="sxs-lookup"><span data-stu-id="9f795-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="9f795-139">选择 "**让我选择** \> **下一处**的特定位置"。</span><span class="sxs-lookup"><span data-stu-id="9f795-139">Choose **Let me choose specific locations** \> **Next**.</span></span> <span data-ttu-id="9f795-140">对于此示例, 请选择此。</span><span class="sxs-lookup"><span data-stu-id="9f795-140">For this example, choose this.</span></span>
    
    <span data-ttu-id="9f795-141">若要包括或排除整个位置 (如所有 Exchange 电子邮件或所有 OneDrive 帐户), 请打开或关闭该位置的**状态**。</span><span class="sxs-lookup"><span data-stu-id="9f795-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="9f795-142">若要仅包含特定的 SharePoint 网站或 OneDrive for business 帐户, 请将**状态**切换到 "开", 然后单击 "**包括**" 下的链接以选择 "特定网站或帐户"。</span><span class="sxs-lookup"><span data-stu-id="9f795-142">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span> <span data-ttu-id="9f795-143">将策略应用到网站后，该策略中配置的规则将自动应用到该网站的所有子网站。</span><span class="sxs-lookup"><span data-stu-id="9f795-143">When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="9f795-145">在此示例中, 若要保护存储在所有 OneDrive for business 帐户中的敏感信息, 请关闭**Exchange 电子邮件**和**SharePoint 网站**的**状态**, 并为**OneDrive 帐户**保留**状态**"启用"。</span><span class="sxs-lookup"><span data-stu-id="9f795-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="9f795-146">选择 "**使用高级设置** \> "**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9f795-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="9f795-147">DLP 策略模板包含预定义的规则，这些规则具有对特定敏感信息类型进行检测和操作的条件与操作。</span><span class="sxs-lookup"><span data-stu-id="9f795-147">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information.</span></span> <span data-ttu-id="9f795-148">您可以编辑、删除或关闭任何现有规则, 也可以添加新规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-148">You can edit, delete, or turn off any of the existing rules, or add new ones.</span></span> <span data-ttu-id="9f795-149">完成后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="9f795-149">When done, click **Next**.</span></span>
    
    ![在美国 PII 策略模板中展开的规则](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="9f795-151">在此示例中, 美国 PII 数据模板包含两个预定义的规则:</span><span class="sxs-lookup"><span data-stu-id="9f795-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="9f795-152">**检测到的内容量较少 (美国 PII** )此规则查找包含三种类型的敏感信息 (ITIN、SSN 和美国护照号码) 中每种类型的1到10个匹配项的文件, 其中的文件与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="9f795-152">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization.</span></span> <span data-ttu-id="9f795-153">如果找到, 则该规则会向主网站集管理员、文档所有者和上次修改文档的人员发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="9f795-153">If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="9f795-154">**检测到的大量内容 (美国 PII** )此规则查找包含10个或更多个相同的三种敏感信息类型的文件, 其中文件与组织外部的人员共享的文件。</span><span class="sxs-lookup"><span data-stu-id="9f795-154">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization.</span></span> <span data-ttu-id="9f795-155">如果找到, 此操作还会发送一封电子邮件通知, 并限制对该文件的访问。</span><span class="sxs-lookup"><span data-stu-id="9f795-155">If found, this action also sends an email notification, plus it restricts access to the file.</span></span> <span data-ttu-id="9f795-156">对于 OneDrive for business 帐户中的内容, 这意味着对文档的权限受到限制, 仅限于主网站集管理员、文档所有者和上次修改文档的人员之外的所有用户。</span><span class="sxs-lookup"><span data-stu-id="9f795-156">For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="9f795-157">若要满足组织的特定要求, 您可能需要使规则更易于触发, 以便单个出现的敏感信息足以阻止外部用户的访问。</span><span class="sxs-lookup"><span data-stu-id="9f795-157">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users.</span></span> <span data-ttu-id="9f795-158">在查看这些规则之后, 您将了解不需要低和高计数规则的情况, 如果发现任何敏感信息, 则仅需要一个规则来阻止访问。</span><span class="sxs-lookup"><span data-stu-id="9f795-158">After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="9f795-159">因此, 你可以展开名为 "**低" 的内容批量检测美国 PII** \> **删除规则**的规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    !["删除规则" 按钮](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="9f795-161">现在, 在此示例中, 您需要添加两种敏感信息类型 (美国银行帐号和美国驾驶执照号码), 允许用户重写规则, 并将计数更改为任何匹配项。</span><span class="sxs-lookup"><span data-stu-id="9f795-161">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence.</span></span> <span data-ttu-id="9f795-162">您可以通过编辑一个规则来执行所有此操作, 因此请选择 "**检测到的大量内容的美国 PII** \> **编辑规则**"。</span><span class="sxs-lookup"><span data-stu-id="9f795-162">You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    !["编辑规则" 按钮](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="9f795-164">若要添加敏感信息类型, 请在 "**条件**" 部分\> **添加或更改类型**。</span><span class="sxs-lookup"><span data-stu-id="9f795-164">To add a sensitive information type, in the **Conditions** section \> **Add or change types**.</span></span> <span data-ttu-id="9f795-165">然后, 在 "**添加或更改类型** \> " 下, 选择 "**添加** \>选择**美国银行帐号**和**美国司机的许可证编号** \> **添加** \> **完成**"。</span><span class="sxs-lookup"><span data-stu-id="9f795-165">Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![添加或更改类型的选项](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    !["添加或更改类型" 窗格](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="9f795-168">若要更改计数 (触发规则所需的敏感信息的实例数), 请在 "**实例计数** \> " 中, 选择每个类型\> 1 的**最小**值。</span><span class="sxs-lookup"><span data-stu-id="9f795-168">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1.</span></span> <span data-ttu-id="9f795-169">最小计数不能为空。</span><span class="sxs-lookup"><span data-stu-id="9f795-169">The minimum count cannot be empty.</span></span> <span data-ttu-id="9f795-170">最大计数可以为空;空的**max**值将转换为**any**。</span><span class="sxs-lookup"><span data-stu-id="9f795-170">The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="9f795-171">完成后, 所有敏感信息类型的最小计数应为**1** , 最大值计数应为 "**任意**"。</span><span class="sxs-lookup"><span data-stu-id="9f795-171">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**.</span></span> <span data-ttu-id="9f795-172">换句话说, 这种类型的敏感信息的任何匹配项都将满足此条件。</span><span class="sxs-lookup"><span data-stu-id="9f795-172">In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![敏感信息类型的实例计数](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="9f795-174">对于最终自定义, 您不希望您的 DLP 策略阻止用户在其具有有效业务理由或遇到误报时执行其工作, 因此您希望用户通知包括替代阻止操作的选项。</span><span class="sxs-lookup"><span data-stu-id="9f795-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="9f795-175">在 "**用户通知**" 部分中, 您可以看到默认情况下, 此规则在模板中已启用电子邮件通知和策略提示。</span><span class="sxs-lookup"><span data-stu-id="9f795-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="9f795-176">在 "**用户替代**" 部分中, 您可以看到业务理由的替代已打开, 但不能覆盖报告误报。</span><span class="sxs-lookup"><span data-stu-id="9f795-176">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not.</span></span> <span data-ttu-id="9f795-177">**如果将规则报告为误报, 请选择 "自动替代规则"**。</span><span class="sxs-lookup"><span data-stu-id="9f795-177">Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    !["用户通知" 部分和 "用户替代" 部分](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="9f795-179">在规则编辑器的顶部, 将此规则的名称从 "检测到美国的默认**内容量" (美国 pii 检测**到的任何内容) 更改为 "**使用美国 pii**检测到的任何内容", 因为它现在是由其任何敏感信息类型的发生触发触发的。</span><span class="sxs-lookup"><span data-stu-id="9f795-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="9f795-180">在规则编辑器\>的底部**保存**。</span><span class="sxs-lookup"><span data-stu-id="9f795-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="9f795-181">请在\> **接下来**查看此规则的条件和操作。</span><span class="sxs-lookup"><span data-stu-id="9f795-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="9f795-182">在右侧, 请注意规则的**状态**开关。</span><span class="sxs-lookup"><span data-stu-id="9f795-182">On the right, notice the **Status** switch for the rule.</span></span> <span data-ttu-id="9f795-183">如果关闭整个策略, 则还会禁用该策略中包含的所有规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-183">If you turn off an entire policy, all rules contained in the policy are also turned off.</span></span> <span data-ttu-id="9f795-184">但是, 在这里, 您可以在不关闭整个策略的情况下关闭特定规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-184">However, here you can turn off a specific rule without turning off the entire policy.</span></span> <span data-ttu-id="9f795-185">当您需要调查生成大量误报的规则时，这一功能很有用。</span><span class="sxs-lookup"><span data-stu-id="9f795-185">This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="9f795-186">在下一页上, 阅读并理解以下各项, 然后选择是启用规则还是先\>将其测试到下一**步**。</span><span class="sxs-lookup"><span data-stu-id="9f795-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="9f795-187">在创建 DLP 策略之前，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。</span><span class="sxs-lookup"><span data-stu-id="9f795-187">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them.</span></span> <span data-ttu-id="9f795-188">例如, 您不希望新的 DLP 策略在无意中阻止对用户完成其工作所需的数千个文档的访问。</span><span class="sxs-lookup"><span data-stu-id="9f795-188">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="9f795-189">如果您创建的 DLP 策略具有很大的潜在影响, 我们建议按照以下顺序进行操作:</span><span class="sxs-lookup"><span data-stu-id="9f795-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="9f795-p121">在不使用策略提示的情况下启动测试模式，然后使用 DLP 报告评估影响。您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。根据结果，您可以在需要时微调规则。在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="9f795-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="9f795-p122">移动到使用通知和策略提示的测试模式，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="9f795-196">启用这些策略, 以便强制实施规则和保护内容。</span><span class="sxs-lookup"><span data-stu-id="9f795-196">Turn on the policies so that the rules are enforced and the content's protected.</span></span> <span data-ttu-id="9f795-197">继续监视 DLP 报告及任何事件报告或通知，确保结果是您所期望的。</span><span class="sxs-lookup"><span data-stu-id="9f795-197">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="9f795-199">查看此策略\>的设置。选择 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="9f795-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="9f795-200">创建并打开 DLP 策略后, 会将其部署到其包含的任何内容源 (如 SharePoint Online 网站或 OneDrive for business 帐户) 中, 策略将自动开始对该内容强制实施其规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="9f795-201">查看 DLP 策略的状态</span><span class="sxs-lookup"><span data-stu-id="9f795-201">View the status of a DLP policy</span></span>

<span data-ttu-id="9f795-202">您可以随时在安全&amp;合规中心的 "**数据丢失防护**" 部分中的 "**策略**" 页上查看 DLP 策略的状态。</span><span class="sxs-lookup"><span data-stu-id="9f795-202">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center.</span></span> <span data-ttu-id="9f795-203">您可以在此处找到以下重要信息，如策略是成功启用还是成功禁用，或者策略是否处于测试模式。</span><span class="sxs-lookup"><span data-stu-id="9f795-203">Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="9f795-204">下面介绍了不同的状态及其含义。</span><span class="sxs-lookup"><span data-stu-id="9f795-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="9f795-205">**状态**</span><span class="sxs-lookup"><span data-stu-id="9f795-205">**Status**</span></span>|<span data-ttu-id="9f795-206">**说明**</span><span class="sxs-lookup"><span data-stu-id="9f795-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f795-207">**正在启用...**</span><span class="sxs-lookup"><span data-stu-id="9f795-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="9f795-p125">系统正在将策略部署到它所包含的内容源。策略尚未强制应用于所有源。</span><span class="sxs-lookup"><span data-stu-id="9f795-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="9f795-210">**测试并发送通知**</span><span class="sxs-lookup"><span data-stu-id="9f795-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="9f795-p126">策略处于测试模式。不会应用规则中的操作，但可以收集策略匹配项，并通过使用 DLP 报告进行查看。有关策略匹配项的通知会发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="9f795-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="9f795-214">**测试但不发送通知**</span><span class="sxs-lookup"><span data-stu-id="9f795-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="9f795-p127">策略处于测试模式。不会应用规则中的操作，但可以收集策略匹配项，并通过使用 DLP 报告进行查看。有关策略匹配项的通知不会发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="9f795-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="9f795-218">**On**</span><span class="sxs-lookup"><span data-stu-id="9f795-218">**On**</span></span> <br/> |<span data-ttu-id="9f795-p128">策略处于活动状态并且已强制应用。策略已成功部署到它的所有内容源。</span><span class="sxs-lookup"><span data-stu-id="9f795-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="9f795-221">**正在禁用...**</span><span class="sxs-lookup"><span data-stu-id="9f795-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="9f795-p129">系统正在将策略从它包含的内容源中移除。策略可能仍处于活动状态并在某些源上强制应用。禁用策略可能需要 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="9f795-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="9f795-225">**关**</span><span class="sxs-lookup"><span data-stu-id="9f795-225">**Off**</span></span> <br/> |<span data-ttu-id="9f795-p130">策略处于非活动状态且未强制应用。系统会保存策略的设置（源、关键字、持续时间等）。</span><span class="sxs-lookup"><span data-stu-id="9f795-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="9f795-228">**删除 .。。**</span><span class="sxs-lookup"><span data-stu-id="9f795-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="9f795-p131">系统正在删除策略。策略处于非活动状态且未强制应用。</span><span class="sxs-lookup"><span data-stu-id="9f795-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="9f795-231">禁用 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="9f795-231">Turn off a DLP policy</span></span>

<span data-ttu-id="9f795-232">您可以随时编辑或关闭 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="9f795-232">You can edit or turn off a DLP policy at any time.</span></span> <span data-ttu-id="9f795-233">关闭策略将禁用该策略中的所有规则。</span><span class="sxs-lookup"><span data-stu-id="9f795-233">Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="9f795-234">若要编辑或关闭 DLP 策略, 请在 "**策略**" \>页上选择\> "策略"**编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="9f795-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
!["编辑策略" 按钮](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="9f795-236">此外, 您可以通过编辑策略并关闭该规则的**状态**来单独关闭每个规则, 如上文所述。</span><span class="sxs-lookup"><span data-stu-id="9f795-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="9f795-237">更多信息</span><span class="sxs-lookup"><span data-stu-id="9f795-237">More information</span></span>

- [<span data-ttu-id="9f795-238">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="9f795-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="9f795-239">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="9f795-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="9f795-240">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="9f795-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="9f795-241">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="9f795-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="9f795-242">敏感信息类型库存</span><span class="sxs-lookup"><span data-stu-id="9f795-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

