---
title: 在安全与合规中心内创建自定义敏感信息类型
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在安全与合规中心的图形用户界面中为 DLP 创建、修改、删除和测试自定义敏感信息类型。
ms.openlocfilehash: c291d7265df460113769b997aae49b5295d8727f
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478211"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="b4191-103">在安全与合规中心内创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

## <a name="summary"></a><span data-ttu-id="b4191-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b4191-104">Summary</span></span>

<span data-ttu-id="b4191-105">阅读本文，以在安全与合规中心 ([https://protection.office.com](https://protection.office.com)) 内创建[自定义敏感信息类型](custom-sensitive-info-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b4191-105">Read this article to create a [custom sensitive information type](custom-sensitive-info-types.md) in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="b4191-106">使用此方法创建的自定义敏感信息类型将添加到名为 `Microsoft.SCCManaged.CustomRulePack` 的规则包中。</span><span class="sxs-lookup"><span data-stu-id="b4191-106">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="b4191-107">此外，还可以使用 PowerShell 和精确的数据匹配功能创建自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b4191-107">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="b4191-108">若要了解有关这些方法的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b4191-108">To learn more about those methods, see:</span></span>
- <span data-ttu-id="b4191-109">[使用安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="b4191-109">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>
- [<span data-ttu-id="b4191-110">使用精确数据匹配 (EDM) 为 DLP 创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-110">Create a custom sensitive information type with Exact Data Match (Preview)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="before-you-begin"></a><span data-ttu-id="b4191-111">开始之前...</span><span class="sxs-lookup"><span data-stu-id="b4191-111">Before you begin</span></span>

- <span data-ttu-id="b4191-112">组织必须具有包含数据丢失防护 (DLP) 的订阅（如 Office 365 企业版）。</span><span class="sxs-lookup"><span data-stu-id="b4191-112">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="b4191-113">请参阅[邮件策略和合规性服务说明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc)。</span><span class="sxs-lookup"><span data-stu-id="b4191-113">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="b4191-p104">自定义敏感信息类型需要熟悉正则表达式 (RegEx)。有关用于处理文本的 Boost.RegEx（以前称为 RegEx++）引擎的详细信息，请参阅 [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/)。</span><span class="sxs-lookup"><span data-stu-id="b4191-p104">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="b4191-116">在创建自定义分类或正则表达式模式时，不可从 Microsoft 客户服务和支持获取帮助。</span><span class="sxs-lookup"><span data-stu-id="b4191-116">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="b4191-117">支持工程师可对功能提供有限的支持，例如提供用于测试目的的示例正则表达式，或者帮助排查未如期触发的现有正则表达式模式的问题，但无法保证所有自定义内容匹配开发都将满足你的要求或义务。</span><span class="sxs-lookup"><span data-stu-id="b4191-117">Microsoft Customer Service & Support can't assist with providing custom content-matching definitions (creating custom classifications or regular expression patterns). Support engineers can provide limited support for the feature (for example, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected), but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="b4191-118">DLP 使用搜索爬网程序来确定 SharePoint Online 和 OneDrive for Business 网站中的敏感信息并对其分类。</span><span class="sxs-lookup"><span data-stu-id="b4191-118">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="b4191-119">要确定现有内容中新的自定义敏感信息类型，必须对该内容重新爬网。</span><span class="sxs-lookup"><span data-stu-id="b4191-119">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="b4191-120">根据计划对内容进行爬网，但你可手动重新爬网内容来查找网站集、列表或库。</span><span class="sxs-lookup"><span data-stu-id="b4191-120">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="b4191-121">有关详细信息，请参阅[Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content)（手动请求对网站、库或列表进行爬网和重新编制索引）。</span><span class="sxs-lookup"><span data-stu-id="b4191-121">For more information, see [Manually request crawling and re-indexing of a site, a library or a listhttp://go.microsoft.com/fwlink/p/?LinkID=627457](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="b4191-122">在安全与合规中心内创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-122">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="b4191-123">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-123">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="b4191-124">设置的含义相当显而易见，而且向导中的相关页也对这些设置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="b4191-124">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="b4191-125">**名称**</span><span class="sxs-lookup"><span data-stu-id="b4191-125">**Name**</span></span>

- <span data-ttu-id="b4191-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b4191-126">**Description**</span></span>

- <span data-ttu-id="b4191-127">**临近度**</span><span class="sxs-lookup"><span data-stu-id="b4191-127">**Proximity**</span></span>

- <span data-ttu-id="b4191-128">**可信度**</span><span class="sxs-lookup"><span data-stu-id="b4191-128">**Confidence level**</span></span>

- <span data-ttu-id="b4191-129">**主要模式元素**（关键字、正则表达式或字典）</span><span class="sxs-lookup"><span data-stu-id="b4191-129">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="b4191-130">可选**支持性模式元素**（关键字、正则表达式或字典）和相应**最低成本**值。</span><span class="sxs-lookup"><span data-stu-id="b4191-130">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="b4191-p107">应用场景如下：需要创建能够在内容中检测 9 位数员工编号的自定义敏感信息类型，以及关键字“员工”、“ID”和“徽章”。若要创建此自定义敏感信息类型，请按以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b4191-p107">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="b4191-133">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，再单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-133">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![“敏感信息类型”和“创建”按钮的位置](media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="b4191-135">在随即打开的“选择名称和说明”\*\*\*\* 页中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="b4191-135">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="b4191-136">**名称**：员工 ID。</span><span class="sxs-lookup"><span data-stu-id="b4191-136">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="b4191-137">**说明**：检测 9 位数 Contoso 员工 ID 号。</span><span class="sxs-lookup"><span data-stu-id="b4191-137">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![名称和说明页](media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="b4191-139">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-139">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="b4191-140">在随即打开的“匹配要求”\*\*\*\* 页中，单击“添加元素”\*\*\*\*，以配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="b4191-140">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="b4191-141">**检测内容包含**：</span><span class="sxs-lookup"><span data-stu-id="b4191-141">**Detect content containing**:</span></span>
 
      <span data-ttu-id="b4191-p108">a. 单击“任意内容”\*\*\*\*，再选择“正则表达式”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-p108">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="b4191-p109">b. 在正则表达式框中，输入“`(\s)(\d{9})(\s)`”（两边是空格的 9 位数）。</span><span class="sxs-lookup"><span data-stu-id="b4191-p109">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="b4191-146">**支持性元素**：单击“添加支持性元素”\*\*\*\*，再选择“包含此关键字列表”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-146">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="b4191-147">在随即显示的“包含此关键字列表”\*\*\*\* 区域中，配置下列设置：</span><span class="sxs-lookup"><span data-stu-id="b4191-147">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="b4191-148">**关键字列表**：输入以下值：员工、ID、徽章。</span><span class="sxs-lookup"><span data-stu-id="b4191-148">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="b4191-149">**最小计数**：保留默认值 1。</span><span class="sxs-lookup"><span data-stu-id="b4191-149">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="b4191-150">保留“可信度”\*\*\*\* 默认值 60。</span><span class="sxs-lookup"><span data-stu-id="b4191-150">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="b4191-151">保留“字符临近度”\*\*\*\* 默认值 300。</span><span class="sxs-lookup"><span data-stu-id="b4191-151">Leave the default **Character proximity** value 300.</span></span>

    ![匹配页面要求](media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="b4191-153">完成后，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b4191-154">在随即打开的“检查并最终确定”\*\*\*\* 页中，检查设置并单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-154">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![检查并完成页面](media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="b4191-p110">下一页建议通过单击“是”\*\*\*\* 测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。若要稍后测试规则，请单击“否”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-p110">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![测试建议页](media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b4191-160">如何知道操作成功？</span><span class="sxs-lookup"><span data-stu-id="b4191-160">How do you know this worked?</span></span>

<span data-ttu-id="b4191-161">若要验证是否已成功新建敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b4191-161">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="b4191-162">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并验证新自定义敏感信息类型是否已列出。</span><span class="sxs-lookup"><span data-stu-id="b4191-162">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="b4191-p111">测试新自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="b4191-p111">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="b4191-165">在安全与合规中心内修改自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-165">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="b4191-166">**注意**：</span><span class="sxs-lookup"><span data-stu-id="b4191-166">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type https://docs.microsoft.com/en-us/office365/securitycompliance/customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="b4191-p112">只能修改自定义敏感信息类型；不能修改内置敏感信息类型。不过，可使用 PowerShell 导出内置自定义敏感信息类型，然后自定义它们，并将它们作为自定义敏感信息类型导入。有关详细信息，请参阅[自定义内置敏感信息类型](customize-a-built-in-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="b4191-p112">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="b4191-p113">只能修改在 UI 中创建的自定义敏感信息类型。如果使用 [PowerShell 过程](create-a-custom-sensitive-information-type-in-scc-powershell.md)导入自定义敏感信息类型规则包，将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="b4191-p113">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="b4191-172">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，选择要修改的自定义敏感信息类型，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-172">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![“敏感信息类型”和“编辑”按钮的位置](media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="b4191-p114">随后看到的选项与在安全与合规中心内创建自定义敏感信息类型时相同。有关详细信息，请参阅[在安全与合规中心内创建自定义敏感信息类型](#create-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="b4191-p114">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b4191-176">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="b4191-176">How do you know this worked?</span></span>

<span data-ttu-id="b4191-177">若要验证是否已成功修改敏感信息类型，请按以下任一步骤操作：</span><span class="sxs-lookup"><span data-stu-id="b4191-177">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="b4191-178">依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证修改后的自定义敏感信息类型的属性。</span><span class="sxs-lookup"><span data-stu-id="b4191-178">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="b4191-p115">测试修改后的自定义敏感信息类型。有关详细信息，请参阅[在安全与合规中心内测试自定义敏感信息类型](#test-custom-sensitive-information-types-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="b4191-p115">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="b4191-181">在安全与合规中心内删除自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-181">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="b4191-182">**注意**：</span><span class="sxs-lookup"><span data-stu-id="b4191-182">**Notes**:</span></span>

- <span data-ttu-id="b4191-183">只能删除自定义敏感信息类型；不能删除内置敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b4191-183">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="b4191-184">删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b4191-184">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="b4191-185">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，并选择一个或多个要删除的自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b4191-185">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="b4191-186">在随即打开的弹出窗口中，单击“删除”\*\*\*\*（或“删除多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="b4191-186">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![“敏感信息类型”和“删除”按钮的位置](media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="b4191-188">在随即显示的警告消息中，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-188">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b4191-189">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="b4191-189">How do you know this worked?</span></span>

<span data-ttu-id="b4191-190">若要验证是否已成功删除自定义敏感信息类型，请依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*，以验证自定义敏感信息类型是否已不再列出。</span><span class="sxs-lookup"><span data-stu-id="b4191-190">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="b4191-191">在安全与合规中心内测试自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="b4191-191">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="b4191-192">在安全与合规中心内，依次转到“分类”\*\*\*\*\>“敏感信息类型”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-192">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="b4191-p116">选择要测试的一个或多个自定义敏感信息类型。在随即打开的弹出窗口中，单击“测试类型”\*\*\*\*（或“测试多个敏感信息类型”\*\*\*\*，如果选择了多个类型的话）。</span><span class="sxs-lookup"><span data-stu-id="b4191-p116">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![“敏感信息类型”和“测试类型”按钮的位置](media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="b4191-196">在随即打开的“上传测试文件”\*\*\*\* 页面上，拖放文件或单击“浏览”\*\*\*\* 并选择文件，以上传要测试的文档。</span><span class="sxs-lookup"><span data-stu-id="b4191-196">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![“上传测试文件”页](media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="b4191-198">单击“测试”\*\*\*\* 按钮，以测试文档的模式匹配情况。</span><span class="sxs-lookup"><span data-stu-id="b4191-198">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="b4191-199">在“匹配结果”\*\*\*\* 页上，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b4191-199">On the **Match results** page, click **Finish**.</span></span>

    ![匹配结果](media/scc-cust-sens-info-type-test-results.png)