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
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
search.appverid:
- MET150
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: '开始使用 DLP 策略的最简单、 最常用方法是使用 Office 365 中的模板包括之一。 '
ms.openlocfilehash: 4e3a5d731538e4998858b5f9f7a296c43e6774ac
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525458"
---
# <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="4dc8c-103">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4dc8c-103">Create a DLP policy from a template</span></span>

<span data-ttu-id="4dc8c-p101">开始使用 DLP 策略的最简单、 最常用方法是使用 Office 365 中的模板包括之一。您可以使用这些模板一样，之一或自定义规则以满足您组织的特定合规性要求。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p101">The easiest, most common way to get started with DLP policies is to use one of the templates included in Office 365. You can use one of these templates as is, or customize the rules to meet your organization's specific compliance requirements.</span></span>
  
<span data-ttu-id="4dc8c-p102">Office 365 包括可以帮助您满足范围广泛的常见法规和业务策略需求的 40 多个随时可以使用的模板。例如，提供适用于以下法规的 DLP 策略模板：</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p102">Office 365 includes over 40 ready-to-use templates that can help you meet a wide range of common regulatory and business policy needs. For example, there are DLP policy templates for:</span></span>
  
- <span data-ttu-id="4dc8c-108">格雷姆-里奇-比利雷法案 (GLBA)</span><span class="sxs-lookup"><span data-stu-id="4dc8c-108">Gramm-Leach-Bliley Act (GLBA)</span></span>
    
- <span data-ttu-id="4dc8c-109">支付卡行业数据安全标准 (PCI-DSS)</span><span class="sxs-lookup"><span data-stu-id="4dc8c-109">Payment Card Industry Data Security Standard (PCI-DSS)</span></span>
    
- <span data-ttu-id="4dc8c-110">美国个人身份信息（美国 PII）</span><span class="sxs-lookup"><span data-stu-id="4dc8c-110">United States Personally Identifiable Information (U.S. PII)</span></span>
    
- <span data-ttu-id="4dc8c-111">美国健康保险法案 (HIPAA)</span><span class="sxs-lookup"><span data-stu-id="4dc8c-111">United States Health Insurance Act (HIPAA)</span></span>
    
<span data-ttu-id="4dc8c-p103">您可以通过修改任何现有的规则或添加新规则来微调模板。例如，您可以将新的敏感信息类型添加到规则中，以及修改规则中的计数以使其更难以触发或更易于触发，使用户通过提供业务理由替代规则中的操作，或更改要向其发送通知和事件报告的用户。对于许多常见的合规性方案来说，DLP 策略模板都是一个灵活的起点。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p103">You can fine tune a template by modifying any of the existing rules or adding new ones. For example, you can add new types of sensitive information to a rule, modify the counts in a rule to make it harder or easier to trigger, allow people to override the actions in a rule by providing a business justification, or change who notifications and incident reports are sent to. A DLP policy template is a flexible starting point for many common compliance scenarios.</span></span>
  
<span data-ttu-id="4dc8c-115">您还可以选择不带有任何默认规则的自定义模板，从头开始配置您的 DLP 策略以满足组织的特定合规性要求。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-115">You can also choose the Custom template, which has no default rules, and configure your DLP policy from scratch, to meet the specific compliance requirements for your organization.</span></span>
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a><span data-ttu-id="4dc8c-116">示例： 跨所有 OneDrive for Business 站点标识敏感信息和限制访问组织外部的人员</span><span class="sxs-lookup"><span data-stu-id="4dc8c-116">Example: Identify sensitive information across all OneDrive for Business sites and restrict access for people outside your organization</span></span>

<span data-ttu-id="4dc8c-p104">OneDrive for Business 帐户变得易如反掌人员跨组织协作和共享文档。但合规部主管的一个常见的问题是敏感信息存储在 OneDrive for Business 帐户可能与组织外部的人员无意中共享。DLP 策略可以帮助减轻此风险。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p104">OneDrive for Business accounts make it easy for people across your organization to collaborate and share documents. But a common concern for compliance officers is that sensitive information stored in OneDrive for Business accounts may be inadvertently shared with people outside your organization. A DLP policy can help mitigate this risk.</span></span>
  
<span data-ttu-id="4dc8c-p105">本示例中，您将创建 DLP 策略的标识美国 PII 数据，其中包括单个纳税人识别号码 （传送）、 社会保障号和美国护照号码。您将开始使用模板，然后修改该模板以满足您组织的合规性要求，具体而言，您将：</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p105">In this example, you'll create a DLP policy that identifies U.S. PII data, which includes Individual Taxpayer Identification Numbers (ITIN), Social Security Numbers, and U.S. passport numbers. You'll get started by using a template, and then you'll modify the template to meet your organization's compliance requirements—specifically, you'll:</span></span>
  
- <span data-ttu-id="4dc8c-122">添加几个的敏感 information—U.S。 银行帐户数字以及美国驱动程序的许可证的类型 — 以便 DLP 策略保护敏感数据的更多。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-122">Add a couple of types of sensitive information—U.S. bank account numbers and U.S. driver's license numbers—so that the DLP policy protects even more of your sensitive data.</span></span>
    
- <span data-ttu-id="4dc8c-123">策略更多敏感，以使单个匹配项的敏感信息足以限制外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-123">Make the policy more sensitive, so that a single occurrence of sensitive information is enough to restrict access for external users.</span></span>
    
- <span data-ttu-id="4dc8c-p106">允许用户通过提供的业务理由或报告误报重写操作。这种方式，您的 DLP 策略不会阻止组织获取其完成工作，前提是它们具有有效的业务原因共享敏感信息中的人员。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p106">Allow users to override the actions by providing a business justification or reporting a false positive. This way, your DLP policy won't prevent people in your organization from getting their work done, provided they have a valid business reason for sharing the sensitive information.</span></span>
    
### <a name="create-a-dlp-policy-from-a-template"></a><span data-ttu-id="4dc8c-126">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4dc8c-126">Create a DLP policy from a template</span></span>

1. <span data-ttu-id="4dc8c-127">转到[https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-127">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="4dc8c-p107">登录到 Office 365 使用工作或学校帐户。您现在正在使用的 Office 365 安全性&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p107">Sign in to Office 365 using your work or school account. You're now in the Office 365 Security &amp; Compliance Center.</span></span>
    
3. <span data-ttu-id="4dc8c-130">安全中&amp;合规性中心\>左侧导航栏\>**数据丢失防护** \> **策略** \> **+ 创建策略**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-130">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>
    
    ![创建策略按钮](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. <span data-ttu-id="4dc8c-132">选择保护的所需的敏感信息类型的 DLP 策略模板\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-132">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>
    
    <span data-ttu-id="4dc8c-133">本示例中，您可以选择**隐私** \> **美国个人可识别信息 (PII) 数据**因为它已包含的大多数您想要保护的敏感信息类型 — 您稍后将添加几。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-133">In this example, you'll select **Privacy** \> **U.S. Personally Identifiable Information ‎(PII)‎ Data** because it already includes most of the types of sensitive information that you want to protect—you'll add a couple later.</span></span> 
    
    <span data-ttu-id="4dc8c-134">选择模板时，您可以阅读右侧若要了解的敏感信息模板类型的保护的说明。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-134">When you select a template, you can read the description on the right to learn what types of sensitive information the template protects.</span></span>
    
    ![用于选择 DLP 策略模板页](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. <span data-ttu-id="4dc8c-136">策略命名\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-136">Name the policy \> **Next**.</span></span>
    
6. <span data-ttu-id="4dc8c-137">若要选择您想要保护的 DLP 策略的位置，请执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="4dc8c-137">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>
    
  - <span data-ttu-id="4dc8c-138">选择**Office 365 中的所有位置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-138">Choose **All locations in Office 365** \> **Next**.</span></span>
    
  - <span data-ttu-id="4dc8c-p108">选择**让我选择特定位置** \> **下一步**。对于此示例中，选择此选项。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p108">Choose **Let me choose specific locations** \> **Next**. For this example, choose this.</span></span>
    
    <span data-ttu-id="4dc8c-141">若要包括或排除整个的位置，如所有 Exchange 电子邮件或所有 OneDrive 帐户，切换**状态**的位置打开或关闭。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-141">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span> 
    
    <span data-ttu-id="4dc8c-p109">要包含对业务帐户的仅限特定的 SharePoint 网站或 OneDrive 上，切换到**状态**，然后单击**Include**以便选择特定的网站或帐户下的链接。当您将策略应用于网站，配置，策略自动应用于网站的所有子网站的规则。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p109">To include only specific SharePoint sites or OneDrive for Business accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts. When you apply a policy to a site, the rules configured in that policy are automatically applied to all subsites of that site.</span></span> 
    
    ![DLP 策略可以在其中应用的位置选项](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    <span data-ttu-id="4dc8c-145">在此示例中，要保护敏感信息存储在所有 OneDrive for Business 帐户，关闭**状态**， **Exchange 电子邮件**和**SharePoint 网站**，并为**OneDrive 帐户**上将**状态**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-145">In this example, to protect sensitive information stored in all OneDrive for Business accounts, turn off the **Status** for both **Exchange email** and **SharePoint sites**, and leave the **Status** on for **OneDrive accounts**.</span></span>
    
7. <span data-ttu-id="4dc8c-146">选择**使用高级设置** \> **下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-146">Choose **Use advanced settings** \> **Next**.</span></span>
    
8. <span data-ttu-id="4dc8c-p110">DLP 策略模板包含预定义的规则的条件和操作的检测并采取特定类型的敏感信息。您可以编辑、 删除或关闭的任何现有规则，或添加新的。完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p110">A DLP policy template contains predefined rules with conditions and actions that detect and act upon specific types of sensitive information. You can edit, delete, or turn off any of the existing rules, or add new ones. When done, click **Next**.</span></span>
    
    ![规则扩展在美国 PII 策略模板](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    <span data-ttu-id="4dc8c-151">本示例中，美国 PII 数据模板包括两个预定义的规则：</span><span class="sxs-lookup"><span data-stu-id="4dc8c-151">In this example, the U.S. PII Data template includes two predefined rules:</span></span>
    
  - <span data-ttu-id="4dc8c-p111">**低内容量检测到美国 PII**此规则查找包含之间的每个三种类型的敏感信息 （传送、 SSN 和美国护照号码），与组织外部的人员共享中的文件的 1 和 10 个匹配项的文件。如果找到，该规则向主网站集管理员，文档所有者中发送的电子邮件通知和上次修改人文档。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p111">**Low volume of content detected U.S. PII** This rule looks for files containing between 1 and 10 occurrences of each of three types of sensitive information (ITIN, SSN, and U.S. passport numbers), where the files are shared with people outside the organization. If found, the rule sends an email notification to the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
  - <span data-ttu-id="4dc8c-p112">**大量内容检测到美国 PII**此规则查找的文件包含 10 个或多个匹配项的每个相同的三个敏感信息类型，与组织外部的人员共享中的文件。如果找到，此操作还会发送电子邮件通知，加上其限制的文件的访问。Onedrive for Business 帐户的内容，这意味着的文档权限被限制网站集主管理员、 文档所有者和上次修改文档的人员之外的任何用户。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p112">**High volume of content detected U.S. PII** This rule looks for files containing 10 or more occurrences of each of the same three sensitive information types, where the files are shared with people outside the organization. If found, this action also sends an email notification, plus it restricts access to the file. For content in a OneDrive for Business account, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> 
    
    <span data-ttu-id="4dc8c-p113">以满足您组织的特定要求，您可能希望规则更轻松地触发器，以便敏感信息的一个匹配项足以阻止的外部用户访问。查看这些规则之后，您了解您无需低和高计数规则 — 需要仅阻止访问，如果找到任何匹配项的敏感信息的单一的规则。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p113">To meet your organization's specific requirements, you may want to make the rules easier to trigger, so that a single occurrence of sensitive information is enough to block access for external users. After looking at these rules, you understand that you don't need low and high count rules—you need only a single rule that blocks access if any occurrence of sensitive information is found.</span></span>
    
    <span data-ttu-id="4dc8c-159">展开名为**低内容量检测到美国 PII**的规则以便\>**删除规则**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-159">So you expand the rule named **Low volume of content detected U.S. PII** \> **Delete rule**.</span></span>
    
    ![删除规则按钮](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. <span data-ttu-id="4dc8c-p114">现在，在此示例中，您需要添加两个敏感信息类型 （美国银行帐号和美国驱动程序的许可证编号），使用户可以覆盖规则，并将计数更改任何匹配项。您可以执行所有这些操作通过编辑一个规则，请选择**大量内容检测到美国 PII** \> **编辑规则**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p114">Now, in this example, you need to add two sensitive information types (U.S. bank account numbers and U.S. driver's license numbers), allow people to override a rule, and change the count to any occurrence. You can do all of this by editing one rule, so select **High volume of content detected U.S. PII** \> **Edit rule**.</span></span>
    
    ![编辑规则按钮](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. <span data-ttu-id="4dc8c-p115">在**条件**部分中添加一个敏感信息类型， \> **添加或更改的类型**。然后，在**添加或更改的类型**下\>选择**添加**\>选择**美国银行帐号**和**美国驾驶证号码** \> **添加** \> **完成**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p115">To add a sensitive information type, in the **Conditions** section \> **Add or change types**. Then, under **Add or change types** \> choose **Add** \> select **U.S. Bank Account Number** and **U.S. Driver's License Number** \> **Add** \> **Done**.</span></span>
    
    ![添加或更改的类型选项](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![添加或更改类型窗格](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. <span data-ttu-id="4dc8c-p116">若要更改的计数 （的触发规则所需的敏感信息实例数） 下**实例计数**\>选择每种类型的**最小**值\>输入 1。最小计数不能为空。最大计数能为空;一个空**最大**值转换为**任何**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p116">To change the count (the number of instances of sensitive information required to trigger the rule), under **Instance count** \> choose the **min** value for each type \> enter 1. The minimum count cannot be empty. The maximum count can be empty; an empty **max** value convert to **any**.</span></span>
    
    <span data-ttu-id="4dc8c-p117">最大计数应该是**任何**和所有敏感信息类型的最小值计数完成后，应为**1** 。换句话说，这种类型的敏感信息的任何匹配项将满足此条件。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p117">When finished, the min count for all of the sensitive information types should be **1** and the max count should be **any**. In other words, any occurrence of this type of sensitive information will satisfy this condition.</span></span>
    
    ![敏感信息类型的实例计数](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. <span data-ttu-id="4dc8c-174">最后一个自定义项，您不希望您的 DLP 策略阻止，如果用户具有有效的业务理由或遇到误报，因此您希望用户通知，包括选项以覆盖阻止的操作执行其工作的人员。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-174">For the final customization, you don't want your DLP policies to block people from doing their work when they have a valid business justification or encounter a false positive, so you want the user notification to include options to override the blocking action.</span></span>
    
    <span data-ttu-id="4dc8c-175">在**用户通知**部分中，您可以看到的电子邮件通知和策略提示已打开默认情况下，在模板此规则。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-175">In the **User notifications** section, you can see that email notifications and policy tips are turned on by default for this rule in the template.</span></span> 
    
    <span data-ttu-id="4dc8c-p118">在**用户替代**部分中，您可以看到的业务理由覆盖已打开，但不是覆盖报告误报。选择**覆盖规则自动如果他们其报告为误报**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p118">In the **User overrides** section, you can see that overrides for a business justification are turned on, but overrides to report false positives are not. Choose **Override the rule automatically if they report it as a false positive**.</span></span>
    
    ![用户和用户通知一节将覆盖部分](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. <span data-ttu-id="4dc8c-179">顶部的规则编辑器中，更改此规则的名称从默认的**大量内容检测到美国 PII**为**美国 PII 使用检测到任何内容**因为现在由其敏感信息类型的任何匹配项。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-179">At the top of the rule editor, change the name of this rule from the default **High volume of content detected U.S. PII** to **Any content detected with U.S. PII** because it's now triggered by any occurrence of its sensitive information types.</span></span> 
    
14. <span data-ttu-id="4dc8c-180">在规则编辑器的底部\>**保存**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-180">At the bottom of the rule editor \> **Save**.</span></span>
    
15. <span data-ttu-id="4dc8c-181">查看的条件和操作此规则\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-181">Review the conditions and actions for this rule \> **Next**.</span></span>
    
    <span data-ttu-id="4dc8c-p119">在右侧，请注意**状态**切换的规则。如果关闭整个策略时，还应关闭该策略中包含的所有规则。但是，此处您可以关闭特定规则先关闭整个策略。当您需要调查生成的误报大量的规则时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p119">On the right, notice the **Status** switch for the rule. If you turn off an entire policy, all rules contained in the policy are also turned off. However, here you can turn off a specific rule without turning off the entire policy. This can be useful when you need to investigate a rule that is generating a large number of false positives.</span></span> 
    
16. <span data-ttu-id="4dc8c-186">在下一页上，阅读并了解以下内容，，，然后选择是否启用规则或检验首先\>**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-186">On the next page, read and understand the following, and then choose whether to turn on the rule or test it out first \> **Next**.</span></span>
    
     <span data-ttu-id="4dc8c-p120">创建您的 DLP 策略之前，您应考虑推出逐步评估及其影响和测试其有效性之前完全强制。例如，您不希望新 DLP 策略无意中阻止访问数以千计的人员需要完成其工作的文档。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p120">Before you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before you fully enforce them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require to get their work done.</span></span> 
    
    <span data-ttu-id="4dc8c-189">如果您正在创建 DLP 策略的大型的潜在影响，建议遵循此序列：</span><span class="sxs-lookup"><span data-stu-id="4dc8c-189">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
    
17. <span data-ttu-id="4dc8c-p121">在不使用策略提示的情况下启动测试模式，然后使用 DLP 报告评估影响。您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。根据结果，您可以在需要时微调规则。在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p121">Start in test mode without Policy Tips and then use the DLP reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
18. <span data-ttu-id="4dc8c-p122">移动到使用通知和策略提示的测试模式，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p122">Move to Test mode with notifications and Policy Tips so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span>
    
19. <span data-ttu-id="4dc8c-p123">启用策略以便会强制执行规则和内容的受保护。继续监视 DLP 报告任何事件报告或通知，以确保结果预想。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p123">Turn on the policies so that the rules are enforced and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 
    
    ![使用测试模式和启用策略的选项](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. <span data-ttu-id="4dc8c-199">检查此策略设置\>选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-199">Review your settings for this policy \> choose **Create**.</span></span>
    
<span data-ttu-id="4dc8c-200">创建和打开 DLP 策略后，它将部署到包含，如 SharePoint Online 站点或 OneDrive for Business 的帐户，该策略自动强制实施该内容在其规则开始位置任何内容源。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-200">After you create and turn on a DLP policy, it's deployed to any content sources that it includes, such as SharePoint Online sites or OneDrive for Business accounts, where the policy begins automatically enforcing its rules on that content.</span></span>
  
## <a name="view-the-status-of-a-dlp-policy"></a><span data-ttu-id="4dc8c-201">查看 DLP 策略的状态</span><span class="sxs-lookup"><span data-stu-id="4dc8c-201">View the status of a DLP policy</span></span>

<span data-ttu-id="4dc8c-p124">在任何时候中,，您可以查看您的 DLP 策略的状态在**策略**页的**数据丢失防护**部分的安全&amp;合规性中心。此处可以查找重要的信息，如成功启用或禁用策略或策略是否在测试模式下。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p124">At any time, you can view the status of your DLP policies on the **Policy** page in the **Data loss prevention** section of the Security &amp; Compliance Center. Here you can find important information, such as whether a policy was successfully enabled or disabled, or whether the policy is in test mode.</span></span> 
  
<span data-ttu-id="4dc8c-204">下面介绍了不同的状态及其含义。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-204">Here are the different statuses and what they mean.</span></span>
  
|<span data-ttu-id="4dc8c-205">**状态**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-205">**Status**</span></span>|<span data-ttu-id="4dc8c-206">**说明**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-206">**Explanation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4dc8c-207">**正在启用...**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-207">**Turning on…**</span></span> <br/> |<span data-ttu-id="4dc8c-p125">系统正在将策略部署到它所包含的内容源。策略尚未强制应用于所有源。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p125">The policy is being deployed to the content sources that it includes. The policy is not yet enforced on all sources.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-210">**测试并发送通知**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-210">**Testing, with notifications**</span></span> <br/> |<span data-ttu-id="4dc8c-p126">策略处于测试模式。不会应用规则中的操作，但可以收集策略匹配项，并通过使用 DLP 报告进行查看。有关策略匹配项的通知会发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p126">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-214">**测试但不发送通知**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-214">**Testing, without notifications**</span></span> <br/> |<span data-ttu-id="4dc8c-p127">策略处于测试模式。不会应用规则中的操作，但可以收集策略匹配项，并通过使用 DLP 报告进行查看。有关策略匹配项的通知不会发送给指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p127">The policy is in test mode. The actions in a rule are not applied, but policy matches are collected and can be viewed by using the DLP reports. Notifications about policy matches are not sent to the specified recipients.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-218">**启用**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-218">**On**</span></span> <br/> |<span data-ttu-id="4dc8c-p128">策略处于活动状态并且已强制应用。策略已成功部署到它的所有内容源。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p128">The policy is active and enforced. The policy was successfully deployed to all its content sources.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-221">**正在禁用...**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-221">**Turning off…**</span></span> <br/> |<span data-ttu-id="4dc8c-p129">系统正在将策略从它包含的内容源中移除。策略可能仍处于活动状态并在某些源上强制应用。禁用策略可能需要 45 分钟。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p129">The policy is being removed from the content sources that it includes. The policy may still be active and enforced on some sources. Turning off a policy may take up to 45 minutes.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-225">**禁用**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-225">**Off**</span></span> <br/> |<span data-ttu-id="4dc8c-p130">策略处于非活动状态且未强制应用。系统会保存策略的设置（源、关键字、持续时间等）。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p130">The policy is not active and not enforced. The settings for the policy (sources, keywords, duration, etc) are saved.</span></span>  <br/> |
|<span data-ttu-id="4dc8c-228">**正在删除…**</span><span class="sxs-lookup"><span data-stu-id="4dc8c-228">**Deleting…**</span></span> <br/> |<span data-ttu-id="4dc8c-p131">系统正在删除策略。策略处于非活动状态且未强制应用。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p131">The policy is in the process of being deleted. The policy is not active and not enforced.</span></span>  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a><span data-ttu-id="4dc8c-231">禁用 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4dc8c-231">Turn off a DLP policy</span></span>

<span data-ttu-id="4dc8c-p132">您可以编辑或任何时候关闭 DLP 策略。关闭策略禁用所有策略中的规则。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-p132">You can edit or turn off a DLP policy at any time. Turning off a policy disables all of the rules in the policy.</span></span>
  
<span data-ttu-id="4dc8c-234">若要编辑或关闭 DLP 策略，请在**策略**页上\>选择策略\>**编辑策略**。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-234">To edit or turn off a DLP policy, on the **Policy** page \> select the policy \> **Edit policy**.</span></span>
  
![编辑策略按钮](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
<span data-ttu-id="4dc8c-236">此外，您可以关闭每个规则单独通过编辑策略，然后切换关闭该规则，**状态**，如上面所述。</span><span class="sxs-lookup"><span data-stu-id="4dc8c-236">In addition, you can turn off each rule individually by editing the policy and then toggling off the **Status** of that rule, as described above.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="4dc8c-237">详细信息</span><span class="sxs-lookup"><span data-stu-id="4dc8c-237">More information</span></span>

- [<span data-ttu-id="4dc8c-238">数据丢失防护策略概述</span><span class="sxs-lookup"><span data-stu-id="4dc8c-238">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)
    
- [<span data-ttu-id="4dc8c-239">发送通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="4dc8c-239">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="4dc8c-240">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="4dc8c-240">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="4dc8c-241">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="4dc8c-241">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="4dc8c-242">敏感信息类型库存</span><span class="sxs-lookup"><span data-stu-id="4dc8c-242">Sensitive information types inventory</span></span>](what-the-sensitive-information-types-look-for.md)
    

