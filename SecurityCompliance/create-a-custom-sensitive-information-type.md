---
title: 创建自定义敏感信息类型
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心的图形用户界面中为 DLP 创建、修改、删除和测试自定义敏感信息类型。
ms.openlocfilehash: de7bbc8ee624fe9468dc64a9811db31d529984bf
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999085"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="cbae8-103">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cbae8-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="cbae8-p101">Office 365 中的数据丢失防护 (DLP) 包含许多内置[敏感信息类型](what-the-sensitive-information-types-look-for.md)，可供用于 DLP 策略。这些内置类型可有助于标识和保护信用卡号、银行帐号、护照号等。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p101">Data loss prevention (DLP) in Office 365 includes many built-in [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="cbae8-106">不过，如果需要标识和保护其他类型的敏感信息（例如，使用组织专用格式的员工 ID 或项目编号），可创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cbae8-106">But if you need to identify and protect a different type of sensitive information (for example, employee IDs or project numbers that uses a format specific to your organization) you can create a custom sensitive information type.</span></span>

<span data-ttu-id="cbae8-107">自定义敏感信息类型的基本组成部分是：</span><span class="sxs-lookup"><span data-stu-id="cbae8-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="cbae8-108">**主要模式**：员工 ID 号、项目编号等。这通常是由正则表达式 (RegEx) 标识，但也可以是关键字列表。</span><span class="sxs-lookup"><span data-stu-id="cbae8-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="cbae8-p102">**额外证据**：假设要查找 9 位数员工 ID 号。由于并非所有 9 位数都是员工 ID 号，因此可查找其他文本：“员工”、“徽章”、“ID”等关键字或其他基于额外正则表达式的文本模式。此支持性证据（亦称为_支持性_或_确证性_证据）提高了在内容中找到的 9 位数确实是员工 ID 号的可能性。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="cbae8-p103">**字符临近度**：主要模式和支持性证据越临近，检测到的内容就越有可能是要查找的内容。可指定主要模式和支持性证据之间的字符距离（亦称为_临近度窗口_），如下图所示：</span><span class="sxs-lookup"><span data-stu-id="cbae8-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![确证性证据和临近度窗口的关系图](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="cbae8-p104">**可信度**：支持性证据越多，匹配结果就越有可能包含要查找的敏感信息。可以为使用更多证据检测到的匹配结果指定更高可信度。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="cbae8-p105">如果符合，模式会返回可用于 DLP 策略条件的计数和可信度。向 DLP 策略添加用于检测敏感信息类型的条件时，可编辑计数和可信度，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="cbae8-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![“实例计数”和“匹配准确度”选项](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="cbae8-120">若要在安全与合规中心内创建自定义敏感信息类型，可使用以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="cbae8-120">To create custom sensitive information types in the Office 365 Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="cbae8-p106">**使用 UI**：此方法更便捷，但配置选项比 PowerShell 少。本主题的其余部分将介绍这些过程。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="cbae8-p107">**使用 PowerShell**：此方法要求，必须先创建包含一个或多个敏感信息类型的 XML 文件（称为_规则包_），再使用 PowerShell 导入规则包（与创建规则包相比，导入规则包无关紧要）。虽然此方法比 UI 复杂得多，但配置选项更多。有关说明，请参阅[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="cbae8-126">下表列出了关键区别：</span><span class="sxs-lookup"><span data-stu-id="cbae8-126">The key differences are described in the following table:</span></span>

|<span data-ttu-id="cbae8-127">**UI 中的自定义敏感信息类型**</span><span class="sxs-lookup"><span data-stu-id="cbae8-127">**Custom sensitive information types in the UI**</span></span>|<span data-ttu-id="cbae8-128">**PowerShell 中的自定义敏感信息类型**</span><span class="sxs-lookup"><span data-stu-id="cbae8-128">**Custom sensitive information types in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbae8-129">名称和说明采用一种语言。</span><span class="sxs-lookup"><span data-stu-id="cbae8-129">Name and Description are in one language.</span></span>|<span data-ttu-id="cbae8-130">支持名称和说明的多种语言。</span><span class="sxs-lookup"><span data-stu-id="cbae8-130">Supports multiple languages for Name and Description.</span></span>|
|<span data-ttu-id="cbae8-131">支持一个模式。</span><span class="sxs-lookup"><span data-stu-id="cbae8-131">Supports one pattern.</span></span>|<span data-ttu-id="cbae8-132">支持多个模式。</span><span class="sxs-lookup"><span data-stu-id="cbae8-132">Supports multiple patterns.</span></span>|
|<span data-ttu-id="cbae8-133">支持性证据可以是：</span><span class="sxs-lookup"><span data-stu-id="cbae8-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="cbae8-134">• 正则表达式</span><span class="sxs-lookup"><span data-stu-id="cbae8-134">• Regular expressions</span></span> <br/><span data-ttu-id="cbae8-135">• 关键字</span><span class="sxs-lookup"><span data-stu-id="cbae8-135">• Keywords</span></span> <br/><span data-ttu-id="cbae8-136">• 关键字字典</span><span class="sxs-lookup"><span data-stu-id="cbae8-136">• Keyword dictionaries</span></span>|<span data-ttu-id="cbae8-137">支持性证据可以是：</span><span class="sxs-lookup"><span data-stu-id="cbae8-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="cbae8-138">• 正则表达式</span><span class="sxs-lookup"><span data-stu-id="cbae8-138">• Regular expressions</span></span> <br/><span data-ttu-id="cbae8-139">• 关键字</span><span class="sxs-lookup"><span data-stu-id="cbae8-139">• Keywords</span></span> <br/><span data-ttu-id="cbae8-140">• 关键字字典</span><span class="sxs-lookup"><span data-stu-id="cbae8-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="cbae8-141">• [内置 DLP 函数](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="cbae8-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="cbae8-142">将自定义敏感信息类型添加到名为 Microsoft.SCCManaged.CustomRulePack 的规则包中</span><span class="sxs-lookup"><span data-stu-id="cbae8-142">Custom sensitive information types are added to the rule package named Microsoft.SCCManaged.CustomRulePack</span></span>|<span data-ttu-id="cbae8-143">最多可创建 10 个包含自定义敏感信息类型的规则包。</span><span class="sxs-lookup"><span data-stu-id="cbae8-143">You can create up to 10 rule packages that contain custom sensitive information types.</span></span>|
|<span data-ttu-id="cbae8-144">模式匹配需要检测主模式和所有支持性证据（使用隐式 AND 运算符）。</span><span class="sxs-lookup"><span data-stu-id="cbae8-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="cbae8-145">模式匹配需要检测主要模式和一组数量可配置的支持性证据（可使用隐式 AND 和 OR 运算符）。</span><span class="sxs-lookup"><span data-stu-id="cbae8-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cbae8-146">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="cbae8-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cbae8-147">若要打开安全与合规中心，请参阅[转到安全与合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-147">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="cbae8-p108">自定义敏感信息类型需要熟悉正则表达式 (RegEx)。有关用于处理文本的 Boost.RegEx（以前称为 RegEx++）引擎的详细信息，请参阅 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="cbae8-p109">Microsoft 客户服务和支持人员无法协助提供自定义内容匹配定义（创建自定义分类或正则表达式模式）。支持工程师可提供有限的功能支持（例如，出于测试目的提供示例正则表达式模式，或协助排查未按预期触发的现有正则表达式模式），但无法保证任何自定义内容匹配开发能够满足你的需求或履行你的义务。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="cbae8-p110">DLP 使用搜索爬网程序标识并分类 SharePoint Online 和 OneDrive for Business 网站中的敏感信息。若要在现有内容中标识新自定义敏感信息类型，必须对内容进行重新爬网。虽然内容重新爬网是按日程安排进行，但你也可以手动对网站集、列表或库的内容进行重新爬网。有关详细信息，请参阅[手动请求对网站、库或列表进行爬网和重新编制索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="cbae8-156">在安全与合规中心内创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cbae8-156">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="cbae8-157">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-157">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="cbae8-158">设置的含义相当显而易见，而且向导中的相关页也对这些设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="cbae8-158">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="cbae8-159">**名称**</span><span class="sxs-lookup"><span data-stu-id="cbae8-159">**Name**</span></span>

- <span data-ttu-id="cbae8-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="cbae8-160">**Description**</span></span>

- <span data-ttu-id="cbae8-161">**临近度**</span><span class="sxs-lookup"><span data-stu-id="cbae8-161">**Proximity**</span></span>

- <span data-ttu-id="cbae8-162">**可信度**</span><span class="sxs-lookup"><span data-stu-id="cbae8-162">**Confidence level**</span></span>

- <span data-ttu-id="cbae8-163">**主要模式元素**（关键字、正则表达式或字典）</span><span class="sxs-lookup"><span data-stu-id="cbae8-163">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="cbae8-164">可选**支持性模式元素**（关键字、正则表达式或字典）和相应**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="cbae8-164">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="cbae8-p111">应用场景如下：需要创建能够在内容中检测 9 位数员工编号的自定义敏感信息类型，以及关键字“员工”、“ID”和“徽章”。若要创建此自定义敏感信息类型，请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cbae8-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="cbae8-167">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-167">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![“敏感信息类型”和“创建”按钮的位置](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="cbae8-169">在随即打开的“选择名称和说明”\*\*\*\* 页中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="cbae8-169">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="cbae8-170">**名称**：员工 ID。</span><span class="sxs-lookup"><span data-stu-id="cbae8-170">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="cbae8-171">**说明**：检测 9 位数 Contoso 员工 ID 号。</span><span class="sxs-lookup"><span data-stu-id="cbae8-171">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名称和说明页](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="cbae8-173">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-173">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="cbae8-174">在随即打开的“匹配要求”\*\*\*\* 页中，单击“添加元素”\*\*\*\*，以配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="cbae8-174">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="cbae8-175">**检测内容包含**：</span><span class="sxs-lookup"><span data-stu-id="cbae8-175">**Detect content containing**:</span></span>
 
      <span data-ttu-id="cbae8-p112">a. 单击“任意内容”\*\*\*\*，再选择“正则表达式”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="cbae8-p113">b. 在正则表达式框中，输入“`(\s)(\d{9})(\s)`”（两边是空格的 9 位数）。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="cbae8-180">**支持性元素**：单击“添加支持性元素”\*\*\*\*，再选择“包含此关键字列表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-180">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="cbae8-181">在随即显示的“包含此关键字列表”\*\*\*\* 区域中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="cbae8-181">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="cbae8-182">**关键字列表**：输入以下值：员工、ID、徽章。</span><span class="sxs-lookup"><span data-stu-id="cbae8-182">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="cbae8-183">**最小计数**：保留默认值 1。</span><span class="sxs-lookup"><span data-stu-id="cbae8-183">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="cbae8-184">保留“可信度”\*\*\*\* 默认值 60。</span><span class="sxs-lookup"><span data-stu-id="cbae8-184">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="cbae8-185">保留“字符临近度”\*\*\*\* 默认值 300。</span><span class="sxs-lookup"><span data-stu-id="cbae8-185">Leave the default **Character proximity** value 300.</span></span>

    ![匹配页面要求](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="cbae8-187">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="cbae8-188">在随即打开的“检查并最终确定”\*\*\*\* 页中，检查设置并单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-188">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![检查并完成页面](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="cbae8-p114">下一页建议通过单击“是”\*\*\*\* 测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。若要稍后测试规则，请单击“否”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p114">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![测试建议页](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cbae8-194">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="cbae8-194">How do you know this worked?</span></span>

<span data-ttu-id="cbae8-195">若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cbae8-195">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="cbae8-196">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并验证新自定义敏感信息类型是否已列出。</span><span class="sxs-lookup"><span data-stu-id="cbae8-196">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="cbae8-p115">测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="cbae8-199">在安全与合规中心内修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cbae8-199">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="cbae8-200">**注意**：</span><span class="sxs-lookup"><span data-stu-id="cbae8-200">**Notes**:</span></span>

- <span data-ttu-id="cbae8-p116">只能修改自定义敏感信息类型；不能修改内置敏感信息类型。不过，可使用 PowerShell 导出内置自定义敏感信息类型，然后自定义它们，并将它们作为自定义敏感信息类型导入。有关详细信息，请参阅[自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p116">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="cbae8-p117">只能修改在 UI 中创建的自定义敏感信息类型。如果使用 [PowerShell 过程](create-a-custom-sensitive-information-type-in-scc-powershell.md)导入自定义敏感信息类型规则包，将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p117">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="cbae8-206">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，选择要修改的自定义敏感信息类型，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-206">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![“敏感信息类型”和“编辑”按钮的位置](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="cbae8-p118">随后看到的选项与在安全与合规中心内创建自定义敏感信息类型时相同。有关详细信息，请参阅[在安全与合规中心内创建自定义敏感信息类型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p118">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cbae8-210">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="cbae8-210">How do you know this worked?</span></span>

<span data-ttu-id="cbae8-211">若要验证是否已成功修改敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cbae8-211">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="cbae8-212">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证修改后的自定义敏感信息类型的属性。</span><span class="sxs-lookup"><span data-stu-id="cbae8-212">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="cbae8-p119">测试修改后的自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p119">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="cbae8-215">在安全与合规中心内删除自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cbae8-215">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="cbae8-216">**注意**：</span><span class="sxs-lookup"><span data-stu-id="cbae8-216">**Notes**:</span></span>

- <span data-ttu-id="cbae8-217">只能删除自定义敏感信息类型；不能删除内置敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cbae8-217">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="cbae8-218">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cbae8-218">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="cbae8-219">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并选择一个或多个要删除的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="cbae8-219">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="cbae8-220">在随即打开的弹出窗口中，单击“删除”\*\*\*\*（或“删除多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="cbae8-220">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![“敏感信息类型”和“删除”按钮的位置](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="cbae8-222">在随即显示的警告消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-222">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cbae8-223">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="cbae8-223">How do you know this worked?</span></span>

<span data-ttu-id="cbae8-224">若要验证是否已成功删除自定义敏感信息类型，请依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证自定义敏感信息类型是否已不再列出。</span><span class="sxs-lookup"><span data-stu-id="cbae8-224">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="cbae8-225">在安全与合规中心内测试自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="cbae8-225">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="cbae8-226">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-226">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="cbae8-p120">选择要测试的一个或多个自定义敏感信息类型。在随即打开的弹出窗口中，单击“测试类型”\*\*\*\*（或“测试多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="cbae8-p120">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![“敏感信息类型”和“测试类型”按钮的位置](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="cbae8-230">在随即打开的“上传测试文件”\*\*\*\* 页面上，拖放文件或单击“浏览”\*\*\*\* 并选择文件，以上传要测试的文档。</span><span class="sxs-lookup"><span data-stu-id="cbae8-230">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![“上传测试文件”页](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="cbae8-232">单击“测试”\*\*\*\* 按钮，以测试文档的模式匹配情况。</span><span class="sxs-lookup"><span data-stu-id="cbae8-232">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="cbae8-233">在“匹配结果”\*\*\*\* 页上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cbae8-233">On the **Match results** page, click **Finish**.</span></span>

    ![匹配结果](media/scc-cust-sens-info-type-test-results.png)