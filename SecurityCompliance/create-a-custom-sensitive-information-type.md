---
title: 创建自定义敏感信息类型
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在 Office 365 安全与合规中心的图形用户界面中创建、修改、删除和测试 DLP 自定义敏感信息类型。
ms.openlocfilehash: cd7041ee9c20038fb7cb0c337f31d7cef7f7192d
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857290"
---
# <a name="create-a-custom-sensitive-information-type"></a><span data-ttu-id="f86d0-103">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-103">Create a custom sensitive information type</span></span>

<span data-ttu-id="f86d0-p101">Office 365 中的数据丢失防护 (DLP) 包含许多[敏感信息类型](what-the-sensitive-information-types-look-for.md)，可供用于 DLP 策略。这些内置类型可有助于标识和保护信用卡号、银行帐号、护照号等。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p101">Data loss prevention (DLP) in Office 365 includes many [sensitive information types](what-the-sensitive-information-types-look-for.md) that are ready for you to use in your DLP policies. These built-in types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more.</span></span> 

<span data-ttu-id="f86d0-106">不过，如果需要标识和保护其他类型的敏感信息（例如，使用组织专用格式的员工 ID 或项目编号），可创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f86d0-106">But if you need to identify and protect a different type of sensitive information - for example, an employee ID that uses a format specific to your organization - you can create a custom sensitive information type. A sensitive information type is defined in an XML file called a rule package.</span></span>

<span data-ttu-id="f86d0-107">自定义敏感信息类型的基本组成部分是：</span><span class="sxs-lookup"><span data-stu-id="f86d0-107">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="f86d0-108">**主要模式**：员工 ID 号、项目编号等。这通常是由正则表达式 (RegEx) 标识，但也可以是关键字列表。</span><span class="sxs-lookup"><span data-stu-id="f86d0-108">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="f86d0-p102">**额外证据**：假设要查找 9 位数员工 ID 号。由于并非所有 9 位数都是员工 ID 号，因此可查找其他文本：“员工”、“徽章”、“ID”等关键字或其他基于额外正则表达式的文本模式。此支持性证据（亦称为_支持性_或_确证性_证据）提高了在内容中找到的 9 位数确实是员工 ID 号的可能性。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p102">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="f86d0-p103">**字符临近度**：主要模式和支持性证据越临近，检测到的内容就越有可能是要查找的内容。可指定主要模式和支持性证据之间的字符距离（亦称为_临近度窗口_），如下图所示：</span><span class="sxs-lookup"><span data-stu-id="f86d0-p103">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![确证性证据和临近度窗口的关系图](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="f86d0-p104">**可信度**：支持性证据越多，匹配结果就越有可能包含要查找的敏感信息。可以为使用更多证据检测到的匹配结果指定更高可信度。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p104">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="f86d0-p105">如果符合，模式会返回可用于 DLP 策略条件的计数和可信度。向 DLP 策略添加用于检测敏感信息类型的条件时，可编辑计数和可信度，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="f86d0-p105">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policy. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown here. Confidence level (also called match accuracy) is explained later in this topic.</span></span>

    ![“实例计数”和“匹配准确度”选项](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

<span data-ttu-id="f86d0-120">若要在 Office 365 安全与合规中心内创建自定义敏感信息类型，可使用以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="f86d0-120">To create custom sensitive information types in the Office 365 Security & Compliance Center, you have the following options:</span></span>

- <span data-ttu-id="f86d0-p106">**使用 UI**：此方法更便捷，但配置选项比 PowerShell 少。本主题的其余部分将介绍这些过程。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p106">**Use the UI**: This method is easier and faster, but you have less configuration options than PowerShell. The rest of this topic describes these procedures.</span></span>

- <span data-ttu-id="f86d0-p107">**使用 PowerShell**：此方法要求，必须先创建包含一个或多个敏感信息类型的 XML 文件（称为_规则包_），再使用 PowerShell 导入规则包（与创建规则包相比，导入规则包无关紧要）。虽然此方法比 UI 复杂得多，但配置选项更多。有关说明，请参阅[使用 Office 365 安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p107">**Use PowerShell**: This method requires that you first create an XML file (called a _rule package_) that contains one or more sensitive information types, and then you use PowerShell to import the rule package (importing the rule package is trivial compared to creating the rule package. This method is much more complex than the UI, but you have more configuration options. For instructions, see [Create a custom sensitive information type in Office 365 Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

<span data-ttu-id="f86d0-126">下表列出了关键区别：</span><span class="sxs-lookup"><span data-stu-id="f86d0-126">The differences are described in the following list.</span></span>

|<span data-ttu-id="f86d0-127">使用 UI 创建的自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-127">Custom sensitive information types in the UI</span></span>|<span data-ttu-id="f86d0-128">使用 PowerShell 创建的自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-128">Custom sensitive information types in PowerShell</span></span>|
|:-----|:-----|
|<span data-ttu-id="f86d0-129">只支持“名称”和“说明”采用一种语言</span><span class="sxs-lookup"><span data-stu-id="f86d0-129">Name and Description are in one language</span></span>|<span data-ttu-id="f86d0-130">支持“名称”和“说明”采用多种语言</span><span class="sxs-lookup"><span data-stu-id="f86d0-130">Supports multiple languages for Name and Description</span></span>|
|<span data-ttu-id="f86d0-131">支持一个模式（主要模式）。</span><span class="sxs-lookup"><span data-stu-id="f86d0-131">Supports one pattern (the primary pattern).</span></span>|<span data-ttu-id="f86d0-132">除主要模式外，还支持多个模式。</span><span class="sxs-lookup"><span data-stu-id="f86d0-132">Supports multiple patterns in addition to the primary pattern.</span></span>|
|<span data-ttu-id="f86d0-133">支持性证据可以是：</span><span class="sxs-lookup"><span data-stu-id="f86d0-133">Supporting evidence can be:</span></span> <br/><span data-ttu-id="f86d0-134">• 正则表达式</span><span class="sxs-lookup"><span data-stu-id="f86d0-134">• Regular expressions</span></span> <br/><span data-ttu-id="f86d0-135">• 关键字</span><span class="sxs-lookup"><span data-stu-id="f86d0-135">• Keywords</span></span> <br/><span data-ttu-id="f86d0-136">• 关键字字典</span><span class="sxs-lookup"><span data-stu-id="f86d0-136">• Keyword dictionaries</span></span>|<span data-ttu-id="f86d0-137">支持性证据可以是：</span><span class="sxs-lookup"><span data-stu-id="f86d0-137">Supporting evidence can be:</span></span> <br/><span data-ttu-id="f86d0-138">• 正则表达式</span><span class="sxs-lookup"><span data-stu-id="f86d0-138">• Regular expressions</span></span> <br/><span data-ttu-id="f86d0-139">• 关键字</span><span class="sxs-lookup"><span data-stu-id="f86d0-139">• Keywords</span></span> <br/><span data-ttu-id="f86d0-140">• 关键字字典</span><span class="sxs-lookup"><span data-stu-id="f86d0-140">• Keyword dictionaries</span></span> <br/><span data-ttu-id="f86d0-141">• [内置 DLP 函数](what-the-dlp-functions-look-for.md)</span><span class="sxs-lookup"><span data-stu-id="f86d0-141">• [Built-in DLP functions](what-the-dlp-functions-look-for.md)</span></span>|
|<span data-ttu-id="f86d0-142">可以为敏感信息类型配置可信度。</span><span class="sxs-lookup"><span data-stu-id="f86d0-142">Confidence level is configurable for the sensitive information type.</span></span>|<span data-ttu-id="f86d0-143">可以为敏感信息类型及其中各个模式配置可信度。</span><span class="sxs-lookup"><span data-stu-id="f86d0-143">Confidence level is configurable for the sensitive information type and each individual pattern within.</span></span>|
|<span data-ttu-id="f86d0-144">模式匹配需要检测主要模式和所有支持性证据（使用的是隐式 AND 运算符）。</span><span class="sxs-lookup"><span data-stu-id="f86d0-144">Pattern match requires the detection of the primary pattern and all supporting evidence (the implicit AND operator is used).</span></span>|<span data-ttu-id="f86d0-145">模式匹配需要检测主要模式和一组数量可配置的支持性证据（可使用隐式 AND 和 OR 运算符）。</span><span class="sxs-lookup"><span data-stu-id="f86d0-145">Pattern match requires the detection of the primary pattern and a configurable amount of supporting evidence (implicit AND and OR operators can be used).</span></span>|

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f86d0-146">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="f86d0-146">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f86d0-147">若要打开安全与合规中心，请参阅[转到 Office 365 安全与合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-147">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="f86d0-p108">若要创建自定义敏感信息类型，需要熟悉正则表达式 (RegEx)。若要详细了解用于处理文本的 .NET RegEx 引擎，请参阅 [.NET 正则表达式](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p108">Custom sensitive information types require familiarity with regular expressions (RegEx). For additional information on the .NET RegEx engine that's used for processing the text, see [.NET Regular Expressions](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span></span>

  <span data-ttu-id="f86d0-p109">Microsoft 客户服务和支持人员无法协助提供自定义内容匹配定义（创建自定义分类或正则表达式模式）。支持工程师可提供有限的功能支持（例如，出于测试目的提供示例正则表达式模式，或协助排查未按预期触发的现有正则表达式模式），但无法保证任何自定义内容匹配开发能够满足你的需求或履行你的义务。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p109">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="f86d0-152">若要详细了解用于处理文本的 .NET RegEx 引擎，请参阅 [.NET 中的正则表达式](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-152">For additional information on the .NET regex engine that's used for processing the text, see the documentaiton on [Regular Expressions in .NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions).</span></span>

- <span data-ttu-id="f86d0-p110">DLP 使用搜索爬网程序标识并分类 SharePoint Online 和 OneDrive for Business 网站中的敏感信息。若要在现有内容中标识新自定义敏感信息类型，必须对内容进行重新爬网。虽然内容重新爬网是按日程安排进行，但你也可以手动对网站集、列表或库的内容进行重新爬网。有关详细信息，请参阅[手动请求对网站、库或列表进行爬网和重新编制索引](https://docs.microsoft.com/sharepoint/crawl-site-content)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p110">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites. To identify your new custom sensitive information type in existing content, the content must be recrawled. Content is recrawled based on a schedule, but you can manually recrawl content for a site collection, list, or library. For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="f86d0-157">在安全与合规中心内创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-157">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="f86d0-158">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-158">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="f86d0-159">设置的含义相当显而易见，而且向导中的相关页也对这些设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="f86d0-159">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="f86d0-160">**名称**</span><span class="sxs-lookup"><span data-stu-id="f86d0-160">**Name**</span></span>

- <span data-ttu-id="f86d0-161">**说明**</span><span class="sxs-lookup"><span data-stu-id="f86d0-161">**Description**</span></span>

- <span data-ttu-id="f86d0-162">**临近度**</span><span class="sxs-lookup"><span data-stu-id="f86d0-162">**Proximity**</span></span>

- <span data-ttu-id="f86d0-163">**可信度**</span><span class="sxs-lookup"><span data-stu-id="f86d0-163">**Confidence level**</span></span>

- <span data-ttu-id="f86d0-164">**主要模式元素**（关键字、正则表达式或字典）</span><span class="sxs-lookup"><span data-stu-id="f86d0-164">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="f86d0-165">可选**支持性模式元素**（关键字、正则表达式或字典）和相应**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="f86d0-165">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="f86d0-p111">应用场景如下：需要创建能够在内容中检测 9 位数员工编号的自定义敏感信息类型，以及关键字“员工”、“ID”和“徽章”。若要创建此自定义敏感信息类型，请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f86d0-p111">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="f86d0-168">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-168">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

2. <span data-ttu-id="f86d0-169">在随即打开的“选择名称和说明”\*\*\*\* 页中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="f86d0-169">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="f86d0-170">**名称**：员工 ID。</span><span class="sxs-lookup"><span data-stu-id="f86d0-170">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="f86d0-171">**说明**：检测 9 位数 Contoso 员工 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f86d0-171">**Description** Detect nine-digit Contoso employee ID numbers.</span></span>

  <span data-ttu-id="f86d0-172">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-172">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="f86d0-173">在随即打开的“匹配要求”\*\*\*\* 页中，单击“添加元素”\*\*\*\*，以配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="f86d0-173">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

  - <span data-ttu-id="f86d0-174">**检测内容包含**：</span><span class="sxs-lookup"><span data-stu-id="f86d0-174">**Detect content containing**:</span></span>
 
    <span data-ttu-id="f86d0-p112">a. 单击“任意内容”\*\*\*\*，再选择“正则表达式”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p112">a. Click **Any of these** and select **Regular expression**.</span></span>

    <span data-ttu-id="f86d0-p113">b. 在正则表达式框中，输入“`(\s)(\d{9})(\s)`”（两边是空格的 9 位数）</span><span class="sxs-lookup"><span data-stu-id="f86d0-p113">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space)</span></span>
  
  - <span data-ttu-id="f86d0-179">**支持性元素**：单击“添加支持性元素”\*\*\*\*，再选择“包含此关键字列表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-179">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

  - <span data-ttu-id="f86d0-180">在随即显示的“包含此关键字列表”\*\*\*\* 区域中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="f86d0-180">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

    - <span data-ttu-id="f86d0-181">**关键字列表**：输入以下值：员工、ID、徽章。</span><span class="sxs-lookup"><span data-stu-id="f86d0-181">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

    - <span data-ttu-id="f86d0-182">**最小计数**：保留默认值 1。</span><span class="sxs-lookup"><span data-stu-id="f86d0-182">**Minimum count**: Leave the default value 1.</span></span>

  - <span data-ttu-id="f86d0-183">保留“可信度”\*\*\*\* 默认值 60。</span><span class="sxs-lookup"><span data-stu-id="f86d0-183">Leave the default **Confidence level** value 60.</span></span> 

  - <span data-ttu-id="f86d0-184">保留“字符临近度”\*\*\*\* 默认值 300。</span><span class="sxs-lookup"><span data-stu-id="f86d0-184">Leave the default **Character proximity** value 300.</span></span>

  <span data-ttu-id="f86d0-185">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f86d0-186">在随即打开的“检查并最终确定”\*\*\*\* 页中，检查设置并单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-186">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

5. <span data-ttu-id="f86d0-p114">下一页建议测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。如果不想测试，请单击“取消”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p114">The next page encourages you to test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). Otherwise, click **Cancel**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f86d0-190">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="f86d0-190">How do you know this worked?</span></span>

<span data-ttu-id="f86d0-191">若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f86d0-191">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="f86d0-192">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并验证新自定义敏感信息类型是否已列出。</span><span class="sxs-lookup"><span data-stu-id="f86d0-192">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="f86d0-p115">测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p115">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="f86d0-195">在安全与合规中心内修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-195">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="f86d0-p116">**注意**：只能修改自定义敏感信息类型；不能修改内置敏感信息类型。不过，可使用 PowerShell 导出内置自定义敏感信息类型，然后自定义它们，并将它们作为自定义敏感信息类型导入。有关详细信息，请参阅[自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p116">**Note**: You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

<span data-ttu-id="f86d0-199">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并选择要修改的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f86d0-199">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select the custom sensitive information type that you want to modify.</span></span>

<span data-ttu-id="f86d0-p117">随后看到的选项与在安全与合规中心内创建自定义敏感信息类型时相同。有关详细信息，请参阅[在安全与合规中心内创建自定义敏感信息类型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p117">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f86d0-202">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="f86d0-202">How do you know this worked?</span></span>

<span data-ttu-id="f86d0-203">若要验证是否已成功修改敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f86d0-203">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="f86d0-204">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证修改后的自定义敏感信息类型的属性。</span><span class="sxs-lookup"><span data-stu-id="f86d0-204">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span>

  - <span data-ttu-id="f86d0-p118">测试修改后的自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p118">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="f86d0-207">在安全与合规中心内删除自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-207">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="f86d0-208">**注意**：</span><span class="sxs-lookup"><span data-stu-id="f86d0-208">**Notes**:</span></span>

- <span data-ttu-id="f86d0-209">只能删除自定义敏感信息类型；不能删除内置敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f86d0-209">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="f86d0-210">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f86d0-210">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="f86d0-211">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并选择一个或多个要删除的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f86d0-211">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="f86d0-212">在随即打开的弹出窗口中，单击“删除”\*\*\*\*（或“删除多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="f86d0-212">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="f86d0-213">在随即显示的警告消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-213">In the warning that appears, click yes.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f86d0-214">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="f86d0-214">How do you know this worked?</span></span>

<span data-ttu-id="f86d0-215">若要验证是否已成功删除自定义敏感信息类型，请依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证自定义敏感信息类型是否已不再列出。</span><span class="sxs-lookup"><span data-stu-id="f86d0-215">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>


## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="f86d0-216">在安全与合规中心内测试自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="f86d0-216">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="f86d0-217">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f86d0-217">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="f86d0-p119">选择要测试的一个或多个自定义敏感信息类型。在随即打开的弹出窗口中，单击“测试类型”\*\*\*\*（或“测试多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="f86d0-p119">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

3. <span data-ttu-id="f86d0-220">在随即打开的页面上，拖放文件或单击“浏览”\*\*\*\* 并选择文件，以上传要测试的文档。</span><span class="sxs-lookup"><span data-stu-id="f86d0-220">On the page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

4. <span data-ttu-id="f86d0-221">单击“测试”\*\*\*\* 按钮，以测试文档的模式匹配情况。</span><span class="sxs-lookup"><span data-stu-id="f86d0-221">Click the **Test** button to test the document for pattern matches in the file.</span></span>
